# TrustLabelAceHelpers::VerifyTrustSidPresentOnFilesystemObject(void *,void *,bool,bool *)

- ea: `0x1800afac4`
- end: `0x1800afc11`
- name: `?VerifyTrustSidPresentOnFilesystemObject@TrustLabelAceHelpers@@SAJPEAX0_NPEA_N@Z`
- size: `333`
- prototype: `__int64 __fastcall(HANDLE handle, PSID Sid1, bool, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800afe14`

## callees

- `0x18001e32c`
- `0x1800afac4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afafc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afafc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800afb1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800afb1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800afb0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800afb87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800afbed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800afb0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800afb87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800afbed`
- `ntdll!RtlFindAceByType` at `0x1800afba9`
- `ntdll!RtlFindAceByType` at `0x1800afba9`
- `ntdll!RtlEqualSid` at `0x1800afbd1`
- `ntdll!RtlEqualSid` at `0x1800afbd1`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1800afb54`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1800afb54`

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
  unsigned int v10; // [rsp+20h] [rbp-30h]
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
           v10);
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
0x1800afac4  mov     [rsp-28h+arg_0], rbx
0x1800afac9  mov     byte ptr [rsp-28h+arg_10], r8b
0x1800aface  push    rbp
0x1800afacf  push    rsi
0x1800afad0  push    rdi
0x1800afad1  push    r14
0x1800afad3  push    r15
0x1800afad5  mov     rbp, rsp
0x1800afad8  sub     rsp, 50h
0x1800afadc  mov     rsi, r9
0x1800afadf  mov     r15, rdx
0x1800afae2  mov     r14, rcx
0x1800afae5  mov     byte ptr [r9], 0
0x1800afae9  and     [rbp+var_10], 0
0x1800afaee  and     [rbp+hMem], 0
0x1800afaf3  mov     rdi, [rbp+hMem]
0x1800afaf7  test    rdi, rdi
0x1800afafa  jz      short loc_1800AFB28
0x1800afafc  call    cs:__imp_GetLastError
0x1800afb03  nop     dword ptr [rax+rax+00h]
0x1800afb08  mov     ebx, eax
0x1800afb0a  mov     rcx, rdi; hMem
0x1800afb0d  call    cs:__imp_LocalFree
0x1800afb14  nop     dword ptr [rax+rax+00h]
0x1800afb19  mov     ecx, ebx; dwErrCode
0x1800afb1b  call    cs:__imp_SetLastError
0x1800afb22  nop     dword ptr [rax+rax+00h]
0x1800afb27  nop
0x1800afb28  lea     rax, [rbp+hMem]
0x1800afb2c  mov     [rsp+50h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1800afb31  lea     rax, [rbp+var_10]
0x1800afb35  mov     [rsp+50h+ppSacl], rax; ppSacl
0x1800afb3a  and     [rsp+50h+var_28], 0
0x1800afb40  and     [rsp+50h+var_30], 0
0x1800afb46  xor     r9d, r9d; ppsidOwner
0x1800afb49  lea     edx, [r9+1]; ObjectType
0x1800afb4d  lea     r8d, [rdx+7Fh]; SecurityInfo
0x1800afb51  mov     rcx, r14; handle
0x1800afb54  call    cs:__imp_GetSecurityInfo
0x1800afb5b  nop     dword ptr [rax+rax+00h]
0x1800afb60  test    eax, eax
0x1800afb62  jz      short loc_1800AFB98
0x1800afb64  mov     rcx, [rbp+28h]; this
0x1800afb68  mov     r9d, eax; char *
0x1800afb6b  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\trust\\trustla"...
0x1800afb72  mov     edx, 24h ; '$'; void *
0x1800afb77  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800afb7c  mov     ebx, eax
0x1800afb7e  mov     rcx, [rbp+hMem]; hMem
0x1800afb82  test    rcx, rcx
0x1800afb85  jz      short loc_1800AFB94
0x1800afb87  call    cs:__imp_LocalFree
0x1800afb8e  nop     dword ptr [rax+rax+00h]
0x1800afb93  nop
0x1800afb94  mov     eax, ebx
0x1800afb96  jmp     short loc_1800AFBFC
0x1800afb98  and     [rbp+arg_10], 0
0x1800afb9c  lea     r8, [rbp+arg_10]
0x1800afba0  mov     edx, 14h
0x1800afba5  mov     rcx, [rbp+var_10]
0x1800afba9  call    cs:__imp_RtlFindAceByType
0x1800afbb0  nop     dword ptr [rax+rax+00h]
0x1800afbb5  test    rax, rax
0x1800afbb8  jz      short loc_1800AFBC0
0x1800afbba  test    byte ptr [rax+1], 8
0x1800afbbe  jz      short loc_1800AFBCA
0x1800afbc0  inc     [rbp+arg_10]
0x1800afbc3  test    rax, rax
0x1800afbc6  jnz     short loc_1800AFB9C
0x1800afbc8  jmp     short loc_1800AFBE4
0x1800afbca  lea     rdx, [rax+8]; Sid2
0x1800afbce  mov     rcx, r15; Sid1
0x1800afbd1  call    cs:__imp_RtlEqualSid
0x1800afbd8  nop     dword ptr [rax+rax+00h]
0x1800afbdd  test    al, al
0x1800afbdf  jz      short loc_1800AFBE4
0x1800afbe1  mov     byte ptr [rsi], 1
0x1800afbe4  mov     rcx, [rbp+hMem]; hMem
0x1800afbe8  test    rcx, rcx
0x1800afbeb  jz      short loc_1800AFBFA
0x1800afbed  call    cs:__imp_LocalFree
0x1800afbf4  nop     dword ptr [rax+rax+00h]
0x1800afbf9  nop
0x1800afbfa  xor     eax, eax
0x1800afbfc  mov     rbx, [rsp+50h+arg_0]
0x1800afc04  add     rsp, 50h
0x1800afc08  pop     r15
0x1800afc0a  pop     r14
0x1800afc0c  pop     rdi
0x1800afc0d  pop     rsi
0x1800afc0e  pop     rbp
0x1800afc0f  retn
```
