# TraceTokenSidInfo

- ea: `0x180028e84`
- end: `0x180028fd4`
- name: `TraceTokenSidInfo`
- size: `336`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180028cc0`

## callees

- `0x1800049ac`
- `0x18001722c`
- `0x180020680`
- `0x180028e84`

## import_xrefs

- `msvcrt!free` at `0x180028f7e`
- `msvcrt!free` at `0x180028fc2`
- `msvcrt!free` at `0x180028f7e`
- `msvcrt!free` at `0x180028fc2`
- `ADVAPI32!GetTokenInformation` at `0x180028ead`
- `ADVAPI32!GetTokenInformation` at `0x180028f33`
- `ADVAPI32!GetTokenInformation` at `0x180028ead`
- `ADVAPI32!GetTokenInformation` at `0x180028f33`
- `KERNEL32!GetLastError` at `0x180028eb3`
- `KERNEL32!GetLastError` at `0x180028ebe`
- `KERNEL32!GetLastError` at `0x180028f3d`
- `KERNEL32!GetLastError` at `0x180028eb3`
- `KERNEL32!GetLastError` at `0x180028ebe`
- `KERNEL32!GetLastError` at `0x180028f3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall TraceTokenSidInfo(HANDLE TokenHandle)
{
  DWORD v2; // eax
  char **v3; // rbx
  DWORD LastError; // eax
  DWORD TokenInformationLength; // [rsp+48h] [rbp+10h] BYREF
  char **v6; // [rsp+50h] [rbp+18h]

  TokenInformationLength = 0;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  if ( GetLastError() == 122 )
  {
    v3 = (char **)MmAllocate(TokenInformationLength);
    v6 = v3;
    if ( GetTokenInformation(TokenHandle, TokenUser, v3, TokenInformationLength, &TokenInformationLength) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
        WPP_SF__sid_(*((_QWORD *)WPP_GLOBAL_Control + 32), 0x1Fu, &WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids, *v3);
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 30, &WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids, LastError);
    }
    free(v3);
  }
  else
  {
    v2 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 29, &WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids, v2);
  }
}

```

## disassembly

```asm
0x180028e84  mov     [rsp+arg_0], rbx
0x180028e89  push    rdi
0x180028e8a  sub     rsp, 30h
0x180028e8e  mov     rdi, rcx
0x180028e91  mov     [rsp+38h+TokenInformationLength], 0
0x180028e99  lea     rax, [rsp+38h+TokenInformationLength]
0x180028e9e  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180028ea3  xor     r9d, r9d; TokenInformationLength
0x180028ea6  xor     r8d, r8d; TokenInformation
0x180028ea9  lea     edx, [r9+1]; TokenInformationClass
0x180028ead  call    cs:__imp_GetTokenInformation
0x180028eb3  call    cs:__imp_GetLastError
0x180028eb9  cmp     eax, 7Ah ; 'z'
0x180028ebc  jz      short loc_180028F08
0x180028ebe  call    cs:__imp_GetLastError
0x180028ec4  lea     rdx, WPP_GLOBAL_Control
0x180028ecb  mov     rcx, cs:WPP_GLOBAL_Control
0x180028ed2  cmp     rcx, rdx
0x180028ed5  jz      loc_180028FC9
0x180028edb  test    byte ptr [rcx+10Ch], 1
0x180028ee2  jz      loc_180028FC9
0x180028ee8  mov     edx, 1Dh
0x180028eed  mov     r9d, eax
0x180028ef0  lea     r8, WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids
0x180028ef7  mov     rcx, [rcx+100h]
0x180028efe  call    WPP_SF_d
0x180028f03  jmp     loc_180028FC9
0x180028f08  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x180028f0c  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180028f11  mov     rbx, rax
0x180028f14  mov     [rsp+38h+arg_10], rax
0x180028f19  lea     rax, [rsp+38h+TokenInformationLength]
0x180028f1e  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180028f23  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180028f28  mov     r8, rbx; TokenInformation
0x180028f2b  mov     edx, 1; TokenInformationClass
0x180028f30  mov     rcx, rdi; TokenHandle
0x180028f33  call    cs:__imp_GetTokenInformation
0x180028f39  test    eax, eax
0x180028f3b  jnz     short loc_180028F87
0x180028f3d  call    cs:__imp_GetLastError
0x180028f43  lea     rdx, WPP_GLOBAL_Control
0x180028f4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f51  cmp     rcx, rdx
0x180028f54  jz      short loc_180028F7B
0x180028f56  test    byte ptr [rcx+10Ch], 1
0x180028f5d  jz      short loc_180028F7B
0x180028f5f  mov     edx, 1Eh
0x180028f64  mov     r9d, eax
0x180028f67  lea     r8, WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids
0x180028f6e  mov     rcx, [rcx+100h]
0x180028f75  call    WPP_SF_d
0x180028f7a  nop
0x180028f7b  mov     rcx, rbx; Block
0x180028f7e  call    cs:__imp_free
0x180028f84  nop
0x180028f85  jmp     short loc_180028FC9
0x180028f87  lea     rdx, WPP_GLOBAL_Control
0x180028f8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f95  cmp     rcx, rdx
0x180028f98  jz      short loc_180028FBF
0x180028f9a  test    byte ptr [rcx+10Ch], 4
0x180028fa1  jz      short loc_180028FBF
0x180028fa3  mov     edx, 1Fh
0x180028fa8  mov     r9, [rbx]
0x180028fab  lea     r8, WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids
0x180028fb2  mov     rcx, [rcx+100h]; LoggerHandle
0x180028fb9  call    WPP_SF__sid_
0x180028fbe  nop
0x180028fbf  mov     rcx, rbx; Block
0x180028fc2  call    cs:__imp_free
0x180028fc8  nop
0x180028fc9  mov     rbx, [rsp+38h+arg_0]
0x180028fce  add     rsp, 30h
0x180028fd2  pop     rdi
0x180028fd3  retn
```
