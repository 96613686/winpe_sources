# KpsKerbInit(void)

- ea: `0x180029e64`
- end: `0x18002a079`
- name: `?KpsKerbInit@@YAKXZ`
- size: `533`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002cf60`

## callees

- `0x18001ae0c`
- `0x18001ae38`
- `0x180029e64`
- `0x18002ea8c`

## import_xrefs

- `MSASN1!ASN1_CreateModule` at `0x180029ef2`
- `MSASN1!ASN1_CreateModule` at `0x180029ef2`
- `MSASN1!ASN1_CloseModule` at `0x180029fdd`
- `MSASN1!ASN1_CloseModule` at `0x180029fdd`
- `ntdll!RtlCreateHashTable` at `0x180029f5d`
- `ntdll!RtlCreateHashTable` at `0x180029f5d`
- `ntdll!RtlInitializeCriticalSection` at `0x180029f0c`
- `ntdll!RtlInitializeCriticalSection` at `0x180029f0c`
- `ntdll!RtlDeleteCriticalSection` at `0x180029fca`
- `ntdll!RtlDeleteCriticalSection` at `0x180029fca`

## pseudocode

```c
__int64 KpsKerbInit(void)
{
  NTSTATUS v0; // eax
  unsigned int v1; // ebx
  unsigned int (*v2)(struct _UNICODE_STRING *, struct _KPS_MIT_REALM *); // rcx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r9
  unsigned int MitRealms; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids);
  KRB5_Module = ASN1_CreateModule(0x10000, 1024, 4096, 81, off_1800332A0, off_180033010, off_180033530, "\b", 895644267);
  v0 = RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)((char *)&KpsGlobalKerbState + 8));
  v1 = v0;
  if ( v0 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        156,
        &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
        (unsigned int)v0);
    goto LABEL_18;
  }
  if ( !(unsigned __int8)RtlCreateHashTable(&qword_18003ACE8, 0, 0) )
  {
    v1 = 8;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_17;
    v4 = 157;
    v5 = 8;
LABEL_16:
    WPP_SF_D(v3[2], v4, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, v5);
LABEL_17:
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)&KpsGlobalKerbState + 8));
LABEL_18:
    ASN1_CloseModule(KRB5_Module);
    KRB5_Module = 0;
    qword_18003ACE8 = 0;
    KpsGlobalKerbState = 0;
    xmmword_18003ACC8 = 0;
    xmmword_18003ACD8 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 160, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, v1);
    return v1;
  }
  MitRealms = KpsReadMitRealms(v2);
  v1 = MitRealms;
  if ( MitRealms )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_17;
    v4 = 158;
    v5 = MitRealms;
    goto LABEL_16;
  }
  KpsGlobalKerbState = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x180029e64  mov     [rsp+arg_0], rbx
0x180029e69  mov     [rsp+arg_8], rsi
0x180029e6e  push    rdi
0x180029e6f  sub     rsp, 50h
0x180029e73  mov     rcx, cs:WPP_GLOBAL_Control
0x180029e7a  lea     rdi, WPP_GLOBAL_Control
0x180029e81  lea     rsi, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x180029e88  cmp     rcx, rdi
0x180029e8b  jz      short loc_180029EA4
0x180029e8d  test    byte ptr [rcx+1Ch], 20h
0x180029e91  jz      short loc_180029EA4
0x180029e93  mov     rcx, [rcx+10h]
0x180029e97  mov     edx, 9Bh
0x180029e9c  mov     r8, rsi
0x180029e9f  call    WPP_SF_
0x180029ea4  mov     [rsp+58h+var_18], 3562726Bh
0x180029eac  lea     rax, asc_180034760; "\b"
0x180029eb3  mov     [rsp+58h+var_20], rax
0x180029eb8  mov     edx, 400h
0x180029ebd  lea     rax, off_180033530
0x180029ec4  mov     ecx, 10000h
0x180029ec9  mov     [rsp+58h+var_28], rax
0x180029ece  mov     r9d, 51h ; 'Q'
0x180029ed4  lea     rax, off_180033010
0x180029edb  mov     r8d, 1000h
0x180029ee1  mov     [rsp+58h+var_30], rax
0x180029ee6  lea     rax, off_1800332A0
0x180029eed  mov     [rsp+58h+var_38], rax
0x180029ef2  call    cs:__imp_ASN1_CreateModule
0x180029ef9  nop     dword ptr [rax+rax+00h]
0x180029efe  lea     rcx, ?KpsGlobalKerbState@@3U_KPS_GLOBAL_KERB_STATE@@A+8; CriticalSection
0x180029f05  mov     cs:KRB5_Module, rax
0x180029f0c  call    cs:__imp_RtlInitializeCriticalSection
0x180029f13  nop     dword ptr [rax+rax+00h]
0x180029f18  mov     ebx, eax
0x180029f1a  test    eax, eax
0x180029f1c  jns     short loc_180029F51
0x180029f1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180029f25  cmp     rcx, rdi
0x180029f28  jz      loc_180029FD6
0x180029f2e  test    byte ptr [rcx+1Ch], 1
0x180029f32  jz      loc_180029FD6
0x180029f38  mov     rcx, [rcx+10h]
0x180029f3c  mov     edx, 9Ch
0x180029f41  mov     r9d, eax
0x180029f44  mov     r8, rsi
0x180029f47  call    WPP_SF_D
0x180029f4c  jmp     loc_180029FD6
0x180029f51  xor     r8d, r8d
0x180029f54  lea     rcx, qword_18003ACE8
0x180029f5b  xor     edx, edx
0x180029f5d  call    cs:__imp_RtlCreateHashTable
0x180029f64  nop     dword ptr [rax+rax+00h]
0x180029f69  test    al, al
0x180029f6b  jnz     short loc_180029F8E
0x180029f6d  mov     ebx, 8
0x180029f72  mov     rcx, cs:WPP_GLOBAL_Control
0x180029f79  cmp     rcx, rdi
0x180029f7c  jz      short loc_180029FC3
0x180029f7e  test    byte ptr [rcx+1Ch], 1
0x180029f82  jz      short loc_180029FC3
0x180029f84  mov     edx, 9Dh
0x180029f89  mov     r9d, ebx
0x180029f8c  jmp     short loc_180029FB7
0x180029f8e  call    ?KpsReadMitRealms@@YAKP6AKPEAU_UNICODE_STRING@@PEAU_KPS_MIT_REALM@@@Z@Z; KpsReadMitRealms(ulong (*)(_UNICODE_STRING *,_KPS_MIT_REALM *))
0x180029f93  mov     ebx, eax
0x180029f95  test    eax, eax
0x180029f97  jz      loc_18002A03C
0x180029f9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029fa4  cmp     rcx, rdi
0x180029fa7  jz      short loc_180029FC3
0x180029fa9  test    byte ptr [rcx+1Ch], 1
0x180029fad  jz      short loc_180029FC3
0x180029faf  mov     edx, 9Eh
0x180029fb4  mov     r9d, eax
0x180029fb7  mov     rcx, [rcx+10h]
0x180029fbb  mov     r8, rsi
0x180029fbe  call    WPP_SF_D
0x180029fc3  lea     rcx, ?KpsGlobalKerbState@@3U_KPS_GLOBAL_KERB_STATE@@A+8; CriticalSection
0x180029fca  call    cs:__imp_RtlDeleteCriticalSection
0x180029fd1  nop     dword ptr [rax+rax+00h]
0x180029fd6  mov     rcx, cs:KRB5_Module
0x180029fdd  call    cs:__imp_ASN1_CloseModule
0x180029fe4  nop     dword ptr [rax+rax+00h]
0x180029fe9  and     cs:KRB5_Module, 0
0x180029ff1  xorps   xmm0, xmm0
0x180029ff4  xor     eax, eax
0x180029ff6  mov     cs:qword_18003ACE8, rax
0x180029ffd  movups  cs:?KpsGlobalKerbState@@3U_KPS_GLOBAL_KERB_STATE@@A, xmm0; _KPS_GLOBAL_KERB_STATE KpsGlobalKerbState
0x18002a004  movups  cs:xmmword_18003ACC8, xmm0
0x18002a00b  movups  cs:xmmword_18003ACD8, xmm0
0x18002a012  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a019  cmp     rcx, rdi
0x18002a01c  jz      short loc_18002A038
0x18002a01e  test    byte ptr [rcx+1Ch], 20h
0x18002a022  jz      short loc_18002A038
0x18002a024  mov     rcx, [rcx+10h]
0x18002a028  mov     edx, 0A0h
0x18002a02d  mov     r9d, ebx
0x18002a030  mov     r8, rsi
0x18002a033  call    WPP_SF_D
0x18002a038  mov     eax, ebx
0x18002a03a  jmp     short loc_18002A068
0x18002a03c  mov     byte ptr cs:?KpsGlobalKerbState@@3U_KPS_GLOBAL_KERB_STATE@@A, 1; _KPS_GLOBAL_KERB_STATE KpsGlobalKerbState
0x18002a043  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a04a  cmp     rcx, rdi
0x18002a04d  jz      short loc_18002A066
0x18002a04f  test    byte ptr [rcx+1Ch], 20h
0x18002a053  jz      short loc_18002A066
0x18002a055  mov     rcx, [rcx+10h]
0x18002a059  mov     edx, 9Fh
0x18002a05e  mov     r8, rsi
0x18002a061  call    WPP_SF_
0x18002a066  xor     eax, eax
0x18002a068  mov     rbx, [rsp+58h+arg_0]
0x18002a06d  mov     rsi, [rsp+58h+arg_8]
0x18002a072  add     rsp, 50h
0x18002a076  pop     rdi
0x18002a077  retn
```
