# TrustLabelAceHelpers::VerifyTrustSidPresentOnFilesystemObject(void *,void *,bool,bool *)

- ea: `0x1800b1cd0`
- end: `0x1800b1e34`
- name: `?VerifyTrustSidPresentOnFilesystemObject@TrustLabelAceHelpers@@SAJPEAX0_NPEA_N@Z`
- size: `356`
- prototype: `__int64 __fastcall(HANDLE handle, PSID Sid1, bool, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800b203c`

## callees

- `0x18001eeb8`
- `0x1800b1cd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b1d2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b1d2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1d0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1d0e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b1d1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b1da7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b1e10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b1d1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b1da7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b1e10`
- `ntdll!RtlFindAceByType` at `0x1800b1dcc`
- `ntdll!RtlFindAceByType` at `0x1800b1dcc`
- `ntdll!RtlEqualSid` at `0x1800b1df4`
- `ntdll!RtlEqualSid` at `0x1800b1df4`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1800b1d74`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1800b1d74`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TrustLabelAceHelpers::VerifyTrustSidPresentOnFilesystemObject(
        HANDLE handle,
        PSID Sid1,
        char a3,
        bool *a4)
{
  DWORD SecurityInfo; // eax
  unsigned int v7; // ebx
  __int64 AceByType; // rax
  unsigned int ppsidGroup; // [rsp+20h] [rbp-30h]
  PACL ppSacl; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  int v13; // [rsp+90h] [rbp+40h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp+48h] BYREF

  LOBYTE(v13) = a3;
  *a4 = 0;
  ppSacl = 0;
  hMem = 0;
  SecurityInfo = GetSecurityInfo(handle, SE_FILE_OBJECT, 0x80u, 0, 0, 0, &ppSacl, &hMem);
  if ( SecurityInfo )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x24,
           (unsigned int)"onecore\\base\\appmodel\\trust\\trustlabelhelpersbase.cpp",
           (const char *)SecurityInfo,
           ppsidGroup);
    if ( hMem )
      LocalFree(hMem);
    return v7;
  }
  else
  {
    v13 = 0;
    while ( 1 )
    {
      AceByType = RtlFindAceByType(ppSacl, 20, &v13);
      if ( AceByType )
      {
        if ( (*(_BYTE *)(AceByType + 1) & 8) == 0 )
          break;
      }
      ++v13;
      if ( !AceByType )
        goto LABEL_12;
    }
    if ( RtlEqualSid(Sid1, (PSID)(AceByType + 8)) )
      *a4 = 1;
LABEL_12:
    if ( hMem )
      LocalFree(hMem);
    return 0;
  }
}

```

## disassembly

```asm
0x1800b1cd0  mov     [rsp-28h+arg_0], rbx
0x1800b1cd5  mov     byte ptr [rsp-28h+arg_10], r8b
0x1800b1cda  push    rbp
0x1800b1cdb  push    rsi
0x1800b1cdc  push    rdi
0x1800b1cdd  push    r14
0x1800b1cdf  push    r15
0x1800b1ce1  mov     rbp, rsp
0x1800b1ce4  sub     rsp, 50h
0x1800b1ce8  mov     rsi, r9
0x1800b1ceb  mov     r15, rdx
0x1800b1cee  mov     r14, rcx
0x1800b1cf1  mov     byte ptr [r9], 0
0x1800b1cf5  mov     [rbp+var_10], 0
0x1800b1cfd  mov     [rbp+hMem], 0
0x1800b1d05  mov     rdi, [rbp+hMem]
0x1800b1d09  test    rdi, rdi
0x1800b1d0c  jz      short loc_1800B1D3A
0x1800b1d0e  call    cs:__imp_GetLastError
0x1800b1d15  nop     dword ptr [rax+rax+00h]
0x1800b1d1a  mov     ebx, eax
0x1800b1d1c  mov     rcx, rdi; hMem
0x1800b1d1f  call    cs:__imp_LocalFree
0x1800b1d26  nop     dword ptr [rax+rax+00h]
0x1800b1d2b  mov     ecx, ebx; dwErrCode
0x1800b1d2d  call    cs:__imp_SetLastError
0x1800b1d34  nop     dword ptr [rax+rax+00h]
0x1800b1d39  nop
0x1800b1d3a  mov     [rbp+hMem], 0
0x1800b1d42  lea     rax, [rbp+hMem]
0x1800b1d46  mov     [rsp+50h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1800b1d4b  lea     rax, [rbp+var_10]
0x1800b1d4f  mov     [rsp+50h+ppSacl], rax; ppSacl
0x1800b1d54  mov     [rsp+50h+ppDacl], 0; ppDacl
0x1800b1d5d  mov     [rsp+50h+ppsidGroup], 0; unsigned int
0x1800b1d66  xor     r9d, r9d; ppsidOwner
0x1800b1d69  lea     edx, [r9+1]; ObjectType
0x1800b1d6d  lea     r8d, [rdx+7Fh]; SecurityInfo
0x1800b1d71  mov     rcx, r14; handle
0x1800b1d74  call    cs:__imp_GetSecurityInfo
0x1800b1d7b  nop     dword ptr [rax+rax+00h]
0x1800b1d80  test    eax, eax
0x1800b1d82  jz      short loc_1800B1DB8
0x1800b1d84  mov     rcx, [rbp+28h]; this
0x1800b1d88  mov     r9d, eax; char *
0x1800b1d8b  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appmodel\\trust\\trustla"...
0x1800b1d92  mov     edx, 24h ; '$'; void *
0x1800b1d97  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800b1d9c  mov     ebx, eax
0x1800b1d9e  mov     rcx, [rbp+hMem]; hMem
0x1800b1da2  test    rcx, rcx
0x1800b1da5  jz      short loc_1800B1DB4
0x1800b1da7  call    cs:__imp_LocalFree
0x1800b1dae  nop     dword ptr [rax+rax+00h]
0x1800b1db3  nop
0x1800b1db4  mov     eax, ebx
0x1800b1db6  jmp     short loc_1800B1E1F
0x1800b1db8  mov     [rbp+arg_10], 0
0x1800b1dbf  lea     r8, [rbp+arg_10]
0x1800b1dc3  mov     edx, 14h
0x1800b1dc8  mov     rcx, [rbp+var_10]
0x1800b1dcc  call    cs:__imp_RtlFindAceByType
0x1800b1dd3  nop     dword ptr [rax+rax+00h]
0x1800b1dd8  test    rax, rax
0x1800b1ddb  jz      short loc_1800B1DE3
0x1800b1ddd  test    byte ptr [rax+1], 8
0x1800b1de1  jz      short loc_1800B1DED
0x1800b1de3  inc     [rbp+arg_10]
0x1800b1de6  test    rax, rax
0x1800b1de9  jnz     short loc_1800B1DBF
0x1800b1deb  jmp     short loc_1800B1E07
0x1800b1ded  lea     rdx, [rax+8]; Sid2
0x1800b1df1  mov     rcx, r15; Sid1
0x1800b1df4  call    cs:__imp_RtlEqualSid
0x1800b1dfb  nop     dword ptr [rax+rax+00h]
0x1800b1e00  test    al, al
0x1800b1e02  jz      short loc_1800B1E07
0x1800b1e04  mov     byte ptr [rsi], 1
0x1800b1e07  mov     rcx, [rbp+hMem]; hMem
0x1800b1e0b  test    rcx, rcx
0x1800b1e0e  jz      short loc_1800B1E1D
0x1800b1e10  call    cs:__imp_LocalFree
0x1800b1e17  nop     dword ptr [rax+rax+00h]
0x1800b1e1c  nop
0x1800b1e1d  xor     eax, eax
0x1800b1e1f  mov     rbx, [rsp+50h+arg_0]
0x1800b1e27  add     rsp, 50h
0x1800b1e2b  pop     r15
0x1800b1e2d  pop     r14
0x1800b1e2f  pop     rdi
0x1800b1e30  pop     rsi
0x1800b1e31  pop     rbp
0x1800b1e32  retn
```
