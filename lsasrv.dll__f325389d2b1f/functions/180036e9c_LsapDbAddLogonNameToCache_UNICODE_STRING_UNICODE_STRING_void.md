# LsapDbAddLogonNameToCache(_UNICODE_STRING *,_UNICODE_STRING *,void *)

- ea: `0x180036e9c`
- end: `0x180037075`
- name: `?LsapDbAddLogonNameToCache@@YAXPEAU_UNICODE_STRING@@0PEAX@Z`
- size: `473`
- prototype: `void __fastcall(PCUNICODE_STRING String1, struct _UNICODE_STRING *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18005c8b4`

## callees

- `0x18000c300`
- `0x180016f70`
- `0x180036e9c`
- `0x18003707c`
- `0x1800371a0`
- `0x1800bd6e0`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x180036fc9`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003705e`
- `ntdll!RtlSubAuthorityCountSid` at `0x180036fc9`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003705e`
- `ntdll!RtlLengthSid` at `0x180036f86`
- `ntdll!RtlLengthSid` at `0x180036fa8`
- `ntdll!RtlLengthSid` at `0x180036f86`
- `ntdll!RtlLengthSid` at `0x180036fa8`
- `ntdll!RtlEqualSid` at `0x180036f07`
- `ntdll!RtlEqualSid` at `0x180036f2c`
- `ntdll!RtlEqualSid` at `0x180036f51`
- `ntdll!RtlEqualSid` at `0x180036f07`
- `ntdll!RtlEqualSid` at `0x180036f2c`
- `ntdll!RtlEqualSid` at `0x180036f51`
- `ntdll!RtlLeaveCriticalSection` at `0x180037031`
- `ntdll!RtlLeaveCriticalSection` at `0x180037031`
- `ntdll!RtlEnterCriticalSection` at `0x180036fe5`
- `ntdll!RtlEnterCriticalSection` at `0x180036fe5`

## pseudocode

```c
void __fastcall LsapDbAddLogonNameToCache(PCUNICODE_STRING String1, struct _UNICODE_STRING *a2, void *a3)
{
  ULONG v5; // eax
  struct _RTL_BALANCED_NODE *v6; // rdi
  ULONG v7; // eax
  UCHAR v8; // si
  void *v9; // rdx
  _WORD v10[2]; // [rsp+40h] [rbp-20h] BYREF
  int v11; // [rsp+44h] [rbp-1Ch]
  PWSTR Buffer; // [rsp+48h] [rbp-18h]
  struct _RTL_BALANCED_NODE *v13; // [rsp+50h] [rbp-10h]
  unsigned __int8 v14; // [rsp+88h] [rbp+28h] BYREF
  struct _LSAP_DB_SID_CACHE_ENTRY *v15; // [rsp+98h] [rbp+38h] BYREF

  Buffer = a2->Buffer;
  v10[0] = a2->Length;
  v10[1] = a2->MaximumLength;
  v15 = 0;
  v11 = 0;
  v13 = 0;
  v14 = 0;
  if ( LsapSidCacheMaxSize )
  {
    if ( !RtlEqualSid(a3, *((PSID *)WellKnownSids + 90))
      && !RtlEqualSid(a3, *((PSID *)WellKnownSids + 108))
      && !RtlEqualSid(a3, *((PSID *)WellKnownSids + 162))
      && (int)LsapAccountIsFromLocalDatabase(a3, &v14) >= 0
      && !v14 )
    {
      v5 = RtlLengthSid(a3);
      v6 = (struct _RTL_BALANCED_NODE *)LsapAllocate(v5);
      if ( v6 )
      {
        v7 = RtlLengthSid(a3);
        memcpy_0(v6, a3, v7);
        v13 = v6;
        v8 = *RtlSubAuthorityCountSid(v6);
        if ( v8 > 1u )
          *RtlSubAuthorityCountSid(v6) = v8 - 1;
        RtlEnterCriticalSection(&LsapSidCacheLock);
        if ( (int)LsapDbAddOneSidToCache(a3, String1, SidTypeUser, (struct _LSAPR_TRUST_INFORMATION *)v10, 0, 0, &v15) >= 0 )
          ++*((_DWORD *)v15 + 25);
        RtlLeaveCriticalSection(&LsapSidCacheLock);
        LsapSubProv_FreeRoutine(v6, v9);
      }
    }
  }
}

```

## disassembly

```asm
0x180036e9c  mov     [rsp-18h+arg_0], rbx
0x180036ea1  mov     [rsp-18h+arg_10], rsi
0x180036ea6  push    rbp
0x180036ea7  push    rdi
0x180036ea8  push    r14
0x180036eaa  mov     rbp, rsp
0x180036ead  sub     rsp, 60h
0x180036eb1  cmp     cs:?LsapSidCacheMaxSize@@3KA, 0; ulong LsapSidCacheMaxSize
0x180036eb8  mov     rbx, r8
0x180036ebb  mov     rax, [rdx+8]
0x180036ebf  mov     r14, rcx
0x180036ec2  mov     [rbp+var_18], rax
0x180036ec6  movzx   eax, word ptr [rdx]
0x180036ec9  mov     [rbp+var_20], ax
0x180036ecd  movzx   eax, word ptr [rdx+2]
0x180036ed1  mov     [rbp+var_1E], ax
0x180036ed5  mov     [rbp+arg_18], 0
0x180036edd  mov     [rbp+var_1C], 0
0x180036ee4  mov     [rbp+var_10], 0
0x180036eec  mov     [rbp+arg_8], 0
0x180036ef0  jz      loc_180037045
0x180036ef6  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180036efd  mov     rcx, rbx; Sid1
0x180036f00  mov     rdx, [rdx+2D0h]; Sid2
0x180036f07  call    cs:__imp_RtlEqualSid
0x180036f0e  nop     dword ptr [rax+rax+00h]
0x180036f13  test    al, al
0x180036f15  jnz     loc_180037045
0x180036f1b  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180036f22  mov     rcx, rbx; Sid1
0x180036f25  mov     rdx, [rdx+360h]; Sid2
0x180036f2c  call    cs:__imp_RtlEqualSid
0x180036f33  nop     dword ptr [rax+rax+00h]
0x180036f38  test    al, al
0x180036f3a  jnz     loc_180037045
0x180036f40  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180036f47  mov     rcx, rbx; Sid1
0x180036f4a  mov     rdx, [rdx+510h]; Sid2
0x180036f51  call    cs:__imp_RtlEqualSid
0x180036f58  nop     dword ptr [rax+rax+00h]
0x180036f5d  test    al, al
0x180036f5f  jnz     loc_180037045
0x180036f65  lea     rdx, [rbp+arg_8]; unsigned __int8 *
0x180036f69  mov     rcx, rbx; Sid1
0x180036f6c  call    ?LsapAccountIsFromLocalDatabase@@YAJPEAXPEAE@Z; LsapAccountIsFromLocalDatabase(void *,uchar *)
0x180036f71  test    eax, eax
0x180036f73  js      loc_180037045
0x180036f79  cmp     [rbp+arg_8], 0
0x180036f7d  jnz     loc_180037045
0x180036f83  mov     rcx, rbx; Sid
0x180036f86  call    cs:__imp_RtlLengthSid
0x180036f8d  nop     dword ptr [rax+rax+00h]
0x180036f92  mov     ecx, eax
0x180036f94  call    LsapAllocate
0x180036f99  mov     rdi, rax
0x180036f9c  test    rax, rax
0x180036f9f  jz      loc_180037045
0x180036fa5  mov     rcx, rbx; Sid
0x180036fa8  call    cs:__imp_RtlLengthSid
0x180036faf  nop     dword ptr [rax+rax+00h]
0x180036fb4  mov     r8d, eax; Size
0x180036fb7  mov     rdx, rbx; Src
0x180036fba  mov     rcx, rdi; void *
0x180036fbd  call    memcpy_0
0x180036fc2  mov     rcx, rdi; Sid
0x180036fc5  mov     [rbp+var_10], rdi
0x180036fc9  call    cs:__imp_RtlSubAuthorityCountSid
0x180036fd0  nop     dword ptr [rax+rax+00h]
0x180036fd5  mov     sil, [rax]
0x180036fd8  cmp     sil, 1
0x180036fdc  ja      short loc_18003705B
0x180036fde  lea     rcx, ?LsapSidCacheLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180036fe5  call    cs:__imp_RtlEnterCriticalSection
0x180036fec  nop     dword ptr [rax+rax+00h]
0x180036ff1  lea     rax, [rbp+arg_18]
0x180036ff5  mov     r8d, 1; enum _SID_NAME_USE
0x180036ffb  mov     [rsp+60h+var_30], rax; struct _LSAP_DB_SID_CACHE_ENTRY **
0x180037000  lea     r9, [rbp+var_20]; struct _LSAPR_TRUST_INFORMATION *
0x180037004  mov     [rsp+60h+var_38], 0; unsigned int
0x18003700c  mov     rdx, r14; String1
0x18003700f  mov     rcx, rbx; Sid2
0x180037012  mov     [rsp+60h+var_40], 0; unsigned int
0x18003701a  call    ?LsapDbAddOneSidToCache@@YAJPEAXPEAU_UNICODE_STRING@@W4_SID_NAME_USE@@PEAU_LSAPR_TRUST_INFORMATION@@KKPEAPEAU_LSAP_DB_SID_CACHE_ENTRY@@@Z; LsapDbAddOneSidToCache(void *,_UNICODE_STRING *,_SID_NAME_USE,_LSAPR_TRUST_INFORMATION *,ulong,ulong,_LSAP_DB_SID_CACHE_ENTRY * *)
0x18003701f  test    eax, eax
0x180037021  js      short loc_18003702A
0x180037023  mov     rax, [rbp+arg_18]
0x180037027  inc     dword ptr [rax+64h]
0x18003702a  lea     rcx, ?LsapSidCacheLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180037031  call    cs:__imp_RtlLeaveCriticalSection
0x180037038  nop     dword ptr [rax+rax+00h]
0x18003703d  mov     rcx, rdi; struct _RTL_BALANCED_NODE *
0x180037040  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x180037045  lea     r11, [rsp+60h+var_s0]
0x18003704a  mov     rbx, [r11+20h]
0x18003704e  mov     rsi, [r11+30h]
0x180037052  mov     rsp, r11
0x180037055  pop     r14
0x180037057  pop     rdi
0x180037058  pop     rbp
0x180037059  retn
0x18003705b  mov     rcx, rdi; Sid
0x18003705e  call    cs:__imp_RtlSubAuthorityCountSid
0x180037065  nop     dword ptr [rax+rax+00h]
0x18003706a  dec     sil
0x18003706d  mov     [rax], sil
0x180037070  jmp     loc_180036FDE
```
