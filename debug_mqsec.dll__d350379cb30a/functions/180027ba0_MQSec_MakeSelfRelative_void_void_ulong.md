# MQSec_MakeSelfRelative(void *,void * *,ulong *)

- ea: `0x180027ba0`
- end: `0x180027c91`
- name: `?MQSec_MakeSelfRelative@@YAJPEAXPEAPEAXPEAK@Z`
- size: `241`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor, void **, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025eac`
- `0x180027ca0`
- `0x180027ed0`

## callees

- `0x1800049ac`
- `0x18001722c`
- `0x180027ba0`

## import_xrefs

- `ADVAPI32!MakeSelfRelativeSD` at `0x180027bc2`
- `ADVAPI32!MakeSelfRelativeSD` at `0x180027bf0`
- `ADVAPI32!MakeSelfRelativeSD` at `0x180027bc2`
- `ADVAPI32!MakeSelfRelativeSD` at `0x180027bf0`
- `KERNEL32!GetLastError` at `0x180027bca`
- `KERNEL32!GetLastError` at `0x180027bfa`
- `KERNEL32!GetLastError` at `0x180027bca`
- `KERNEL32!GetLastError` at `0x180027bfa`

## pseudocode

```c
__int64 __fastcall MQSec_MakeSelfRelative(
        PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor,
        void **a2,
        unsigned int *a3)
{
  BOOL SelfRelativeSD; // ebx
  DWORD LastError; // eax
  void *v8; // rax
  DWORD v9; // eax
  DWORD dwBufferLength; // [rsp+68h] [rbp+20h] BYREF

  dwBufferLength = 0;
  SelfRelativeSD = MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, 0, &dwBufferLength);
  LastError = GetLastError();
  if ( SelfRelativeSD || LastError != 122 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 14, &WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids, LastError);
    return 3222146052LL;
  }
  else
  {
    v8 = MmAllocate(dwBufferLength);
    *a2 = v8;
    if ( MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, v8, &dwBufferLength) )
    {
      if ( a3 )
        *a3 = dwBufferLength;
      return 0;
    }
    else
    {
      v9 = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 13, &WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids, v9);
      return 3222146075LL;
    }
  }
}

```

## disassembly

```asm
0x180027ba0  push    rbx
0x180027ba2  push    rsi
0x180027ba3  push    rdi
0x180027ba4  push    r14
0x180027ba6  sub     rsp, 28h
0x180027baa  mov     rdi, r8
0x180027bad  mov     [rsp+48h+dwBufferLength], 0
0x180027bb5  mov     r14, rdx
0x180027bb8  lea     r8, [rsp+48h+dwBufferLength]; lpdwBufferLength
0x180027bbd  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x180027bbf  mov     rsi, rcx
0x180027bc2  call    cs:__imp_MakeSelfRelativeSD
0x180027bc8  mov     ebx, eax
0x180027bca  call    cs:__imp_GetLastError
0x180027bd0  test    ebx, ebx
0x180027bd2  jnz     short loc_180027C4B
0x180027bd4  cmp     eax, 7Ah ; 'z'
0x180027bd7  jnz     short loc_180027C4B
0x180027bd9  mov     ecx, [rsp+48h+dwBufferLength]; unsigned __int64
0x180027bdd  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180027be2  lea     r8, [rsp+48h+dwBufferLength]; lpdwBufferLength
0x180027be7  mov     [r14], rax
0x180027bea  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x180027bed  mov     rcx, rsi; pAbsoluteSecurityDescriptor
0x180027bf0  call    cs:__imp_MakeSelfRelativeSD
0x180027bf6  test    eax, eax
0x180027bf8  jnz     short loc_180027C3C
0x180027bfa  call    cs:__imp_GetLastError
0x180027c00  mov     rcx, cs:WPP_GLOBAL_Control
0x180027c07  lea     rdx, WPP_GLOBAL_Control
0x180027c0e  cmp     rcx, rdx
0x180027c11  jz      short loc_180027C35
0x180027c13  test    byte ptr [rcx+10Ch], 1
0x180027c1a  jz      short loc_180027C35
0x180027c1c  mov     rcx, [rcx+100h]
0x180027c23  lea     edx, [rbx+0Dh]
0x180027c26  mov     r9d, eax
0x180027c29  lea     r8, WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids
0x180027c30  call    WPP_SF_d
0x180027c35  mov     eax, 0C00E0C1Bh
0x180027c3a  jmp     short loc_180027C87
0x180027c3c  test    rdi, rdi
0x180027c3f  jz      short loc_180027C47
0x180027c41  mov     eax, [rsp+48h+dwBufferLength]
0x180027c45  mov     [rdi], eax
0x180027c47  xor     eax, eax
0x180027c49  jmp     short loc_180027C87
0x180027c4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180027c52  lea     rdx, WPP_GLOBAL_Control
0x180027c59  cmp     rcx, rdx
0x180027c5c  jz      short loc_180027C82
0x180027c5e  test    byte ptr [rcx+10Ch], 1
0x180027c65  jz      short loc_180027C82
0x180027c67  mov     rcx, [rcx+100h]
0x180027c6e  lea     r8, WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids
0x180027c75  mov     edx, 0Eh
0x180027c7a  mov     r9d, eax
0x180027c7d  call    WPP_SF_d
0x180027c82  mov     eax, 0C00E0C04h
0x180027c87  add     rsp, 28h
0x180027c8b  pop     r14
0x180027c8d  pop     rdi
0x180027c8e  pop     rsi
0x180027c8f  pop     rbx
0x180027c90  retn
```
