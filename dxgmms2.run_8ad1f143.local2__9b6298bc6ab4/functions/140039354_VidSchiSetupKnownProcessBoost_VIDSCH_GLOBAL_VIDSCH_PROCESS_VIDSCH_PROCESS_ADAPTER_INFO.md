# VidSchiSetupKnownProcessBoost(_VIDSCH_GLOBAL *,_VIDSCH_PROCESS *,VIDSCH_PROCESS_ADAPTER_INFO *)

- ea: `0x140039354`
- end: `0x1400395e1`
- name: `?VidSchiSetupKnownProcessBoost@@YAJPEAU_VIDSCH_GLOBAL@@PEAU_VIDSCH_PROCESS@@PEAUVIDSCH_PROCESS_ADAPTER_INFO@@@Z`
- size: `653`
- prototype: `__int64 __fastcall(struct _VIDSCH_GLOBAL *, struct _VIDSCH_PROCESS *, struct VIDSCH_PROCESS_ADAPTER_INFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x14011a2cc`

## callees

- `0x140039354`
- `0x140058680`
- `0x1400d787c`

## import_xrefs

- `ntoskrnl!_strnicmp` at `0x1400393b9`
- `ntoskrnl!_strnicmp` at `0x1400393da`
- `ntoskrnl!_strnicmp` at `0x1400393b9`
- `ntoskrnl!_strnicmp` at `0x1400393da`
- `ntoskrnl!RtlCheckTokenMembership` at `0x140039437`
- `ntoskrnl!RtlCheckTokenMembership` at `0x14003958e`
- `ntoskrnl!RtlCheckTokenMembership` at `0x140039437`
- `ntoskrnl!RtlCheckTokenMembership` at `0x14003958e`
- `ntoskrnl!SeExports` at `0x14003941c`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140039474`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140039474`
- `ntoskrnl!RtlInitializeSid` at `0x1400394e0`
- `ntoskrnl!RtlInitializeSid` at `0x1400394e0`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400394f1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003950b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140039525`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003953f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140039559`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140039573`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400394f1`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003950b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140039525`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003953f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140039559`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140039573`
- `ntoskrnl!PsGetCurrentProcess` at `0x14003938d`
- `ntoskrnl!PsGetCurrentProcess` at `0x14003938d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400394b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400395c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400394b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400395c2`

## pseudocode

```c
__int64 __fastcall VidSchiSetupKnownProcessBoost(
        struct _VIDSCH_GLOBAL *a1,
        struct _VIDSCH_PROCESS *a2,
        struct VIDSCH_PROCESS_ADAPTER_INFO *a3)
{
  __int64 v5; // rbx
  const char *v6; // rcx
  char v8; // di
  char v9; // si
  int v10; // ebx
  ULONG v11; // eax
  void *v12; // rax
  void *v13; // rbx
  _BYTE v14[4]; // [rsp+20h] [rbp-30h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+24h] [rbp-2Ch] BYREF
  PVOID P; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v17[4]; // [rsp+38h] [rbp-18h] BYREF
  int v18; // [rsp+3Ch] [rbp-14h]

  if ( !*((_BYTE *)a1 + 7940) )
    return 0;
  v5 = *((_QWORD *)a2 + 332);
  if ( v5 != PsGetCurrentProcess(a1) )
    return 0;
  v6 = (const char *)*((_QWORD *)a2 + 331);
  if ( !v6 )
    return 0;
  if ( !_strnicmp(v6, "audiodg.exe", 0xBu) )
  {
    v8 = 0;
    v9 = 1;
  }
  else
  {
    if ( _strnicmp(*((const char **)a2 + 331), "svchost.exe", 0xBu) )
      return 0;
    v9 = 0;
    v8 = 1;
  }
  v14[0] = 0;
  v10 = RtlCheckTokenMembership(0, SeExports->SeLocalServiceSid, v14);
  if ( v10 >= 0 && v14[0] )
  {
    if ( v8 )
    {
      P = 0;
      v18 = 0;
      v11 = RtlLengthRequiredSid(6u);
      v12 = (void *)PagedPoolZeroedArray<unsigned char,1>::AllocateElements(&P, v11);
      v13 = v12;
      if ( !v12 )
      {
        v10 = -1073741801;
        goto LABEL_15;
      }
      *(_DWORD *)IdentifierAuthority.Value = 0;
      *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
      RtlInitializeSid(v12, &IdentifierAuthority, 6u);
      *RtlSubAuthoritySid(v13, 0) = 80;
      *RtlSubAuthoritySid(v13, 1u) = -379073292;
      *RtlSubAuthoritySid(v13, 2u) = 2104103821;
      *RtlSubAuthoritySid(v13, 3u) = -1247697674;
      *RtlSubAuthoritySid(v13, 4u) = 1811662266;
      *RtlSubAuthoritySid(v13, 5u) = 774708259;
      v10 = RtlCheckTokenMembership(0, v13, v14);
      if ( v10 < 0 || !v14[0] )
      {
        v10 = 0;
LABEL_15:
        if ( P != v17 )
        {
          if ( P )
            ExFreePoolWithTag(P, 0);
        }
        return (unsigned int)v10;
      }
      if ( P != v17 && P )
        ExFreePoolWithTag(P, 0);
    }
    *((_BYTE *)a3 + 5) = v9;
    *((_BYTE *)a3 + 4) = v8;
  }
  else
  {
    return 0;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140039354  mov     [rsp-18h+arg_0], rbx
0x140039359  mov     [rsp-18h+arg_18], rsi
0x14003935e  push    rbp
0x14003935f  push    rdi
0x140039360  push    r14
0x140039362  mov     rbp, rsp
0x140039365  sub     rsp, 50h
0x140039369  mov     rax, cs:__security_cookie
0x140039370  xor     rax, rsp
0x140039373  mov     [rbp+var_10], rax
0x140039377  cmp     byte ptr [rcx+1F04h], 0
0x14003937e  mov     r14, r8
0x140039381  mov     rdi, rdx
0x140039384  jz      short loc_1400393EA
0x140039386  mov     rbx, [rdx+0A60h]
0x14003938d  call    cs:__imp_PsGetCurrentProcess
0x140039394  nop     dword ptr [rax+rax+00h]
0x140039399  cmp     rbx, rax
0x14003939c  jnz     short loc_1400393EA
0x14003939e  mov     rcx, [rdi+0A58h]; Str1
0x1400393a5  test    rcx, rcx
0x1400393a8  jz      short loc_1400393EA
0x1400393aa  mov     ebx, 0Bh
0x1400393af  lea     rdx, Str2; "audiodg.exe"
0x1400393b6  mov     r8d, ebx; MaxCount
0x1400393b9  call    cs:__imp__strnicmp
0x1400393c0  nop     dword ptr [rax+rax+00h]
0x1400393c5  test    eax, eax
0x1400393c7  jz      short loc_14003940E
0x1400393c9  mov     rcx, [rdi+0A58h]; Str1
0x1400393d0  lea     rdx, aSvchostExe; "svchost.exe"
0x1400393d7  mov     r8d, ebx; MaxCount
0x1400393da  call    cs:__imp__strnicmp
0x1400393e1  nop     dword ptr [rax+rax+00h]
0x1400393e6  test    eax, eax
0x1400393e8  jz      short loc_140039416
0x1400393ea  xor     eax, eax
0x1400393ec  mov     rcx, [rbp+var_10]
0x1400393f0  xor     rcx, rsp; StackCookie
0x1400393f3  call    __security_check_cookie
0x1400393f8  lea     r11, [rsp+50h+var_s0]
0x1400393fd  mov     rbx, [r11+20h]
0x140039401  mov     rsi, [r11+38h]
0x140039405  mov     rsp, r11
0x140039408  pop     r14
0x14003940a  pop     rdi
0x14003940b  pop     rbp
0x14003940c  retn
0x14003940e  xor     dil, dil
0x140039411  mov     sil, 1
0x140039414  jmp     short loc_14003941C
0x140039416  xor     sil, sil
0x140039419  mov     dil, 1
0x14003941c  mov     rax, cs:__imp_SeExports
0x140039423  lea     r8, [rbp+var_30]
0x140039427  mov     [rbp+var_30], 0
0x14003942b  xor     ecx, ecx
0x14003942d  mov     rdx, [rax]
0x140039430  mov     rdx, [rdx+180h]
0x140039437  call    cs:__imp_RtlCheckTokenMembership
0x14003943e  nop     dword ptr [rax+rax+00h]
0x140039443  mov     ebx, eax
0x140039445  test    eax, eax
0x140039447  js      loc_1400395D8
0x14003944d  cmp     [rbp+var_30], 0
0x140039451  jz      loc_1400395D8
0x140039457  test    dil, dil
0x14003945a  jz      loc_1400395CE
0x140039460  mov     ecx, 6; SubAuthorityCount
0x140039465  mov     [rbp+P], 0
0x14003946d  mov     [rbp+var_14], 0
0x140039474  call    cs:__imp_RtlLengthRequiredSid
0x14003947b  nop     dword ptr [rax+rax+00h]
0x140039480  mov     edx, eax
0x140039482  lea     rcx, [rbp+P]
0x140039486  call    ?AllocateElements@?$PagedPoolZeroedArray@E$00@@QEAAPEAEI@Z; PagedPoolZeroedArray<uchar,1>::AllocateElements(uint)
0x14003948b  mov     rbx, rax
0x14003948e  test    rax, rax
0x140039491  jnz     short loc_1400394C9
0x140039493  mov     ebx, 0C0000017h
0x140039498  jmp     short loc_14003949C
0x14003949a  xor     ebx, ebx
0x14003949c  mov     rcx, [rbp+P]; P
0x1400394a0  lea     rax, [rbp+var_18]
0x1400394a4  cmp     rcx, rax
0x1400394a7  jz      loc_1400395DA
0x1400394ad  test    rcx, rcx
0x1400394b0  jz      loc_1400395DA
0x1400394b6  xor     edx, edx; Tag
0x1400394b8  call    cs:__imp_ExFreePoolWithTag
0x1400394bf  nop     dword ptr [rax+rax+00h]
0x1400394c4  jmp     loc_1400395DA
0x1400394c9  mov     r8b, 6; SubAuthorityCount
0x1400394cc  mov     dword ptr [rbp+IdentifierAuthority.Value], 0
0x1400394d3  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x1400394d7  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x1400394dd  mov     rcx, rbx; Sid
0x1400394e0  call    cs:__imp_RtlInitializeSid
0x1400394e7  nop     dword ptr [rax+rax+00h]
0x1400394ec  xor     edx, edx; SubAuthority
0x1400394ee  mov     rcx, rbx; Sid
0x1400394f1  call    cs:__imp_RtlSubAuthoritySid
0x1400394f8  nop     dword ptr [rax+rax+00h]
0x1400394fd  mov     edx, 1; SubAuthority
0x140039502  mov     rcx, rbx; Sid
0x140039505  mov     dword ptr [rax], 50h ; 'P'
0x14003950b  call    cs:__imp_RtlSubAuthoritySid
0x140039512  nop     dword ptr [rax+rax+00h]
0x140039517  mov     edx, 2; SubAuthority
0x14003951c  mov     rcx, rbx; Sid
0x14003951f  mov     dword ptr [rax], 0E967CCF4h
0x140039525  call    cs:__imp_RtlSubAuthoritySid
0x14003952c  nop     dword ptr [rax+rax+00h]
0x140039531  mov     edx, 3; SubAuthority
0x140039536  mov     rcx, rbx; Sid
0x140039539  mov     dword ptr [rax], 7D6A138Dh
0x14003953f  call    cs:__imp_RtlSubAuthoritySid
0x140039546  nop     dword ptr [rax+rax+00h]
0x14003954b  mov     edx, 4; SubAuthority
0x140039550  mov     rcx, rbx; Sid
0x140039553  mov     dword ptr [rax], 0B5A1A4F6h
0x140039559  call    cs:__imp_RtlSubAuthoritySid
0x140039560  nop     dword ptr [rax+rax+00h]
0x140039565  mov     edx, 5; SubAuthority
0x14003956a  mov     rcx, rbx; Sid
0x14003956d  mov     dword ptr [rax], 6BFBC5BAh
0x140039573  call    cs:__imp_RtlSubAuthoritySid
0x14003957a  nop     dword ptr [rax+rax+00h]
0x14003957f  lea     r8, [rbp+var_30]
0x140039583  mov     rdx, rbx
0x140039586  xor     ecx, ecx
0x140039588  mov     dword ptr [rax], 2E2D1C23h
0x14003958e  call    cs:__imp_RtlCheckTokenMembership
0x140039595  nop     dword ptr [rax+rax+00h]
0x14003959a  mov     ebx, eax
0x14003959c  test    eax, eax
0x14003959e  js      loc_14003949A
0x1400395a4  cmp     [rbp+var_30], 0
0x1400395a8  jz      loc_14003949A
0x1400395ae  mov     rcx, [rbp+P]; P
0x1400395b2  lea     rax, [rbp+var_18]
0x1400395b6  cmp     rcx, rax
0x1400395b9  jz      short loc_1400395CE
0x1400395bb  test    rcx, rcx
0x1400395be  jz      short loc_1400395CE
0x1400395c0  xor     edx, edx; Tag
0x1400395c2  call    cs:__imp_ExFreePoolWithTag
0x1400395c9  nop     dword ptr [rax+rax+00h]
0x1400395ce  mov     [r14+5], sil
0x1400395d2  mov     [r14+4], dil
0x1400395d6  jmp     short loc_1400395DA
0x1400395d8  xor     ebx, ebx
0x1400395da  mov     eax, ebx
0x1400395dc  jmp     loc_1400393EC
```
