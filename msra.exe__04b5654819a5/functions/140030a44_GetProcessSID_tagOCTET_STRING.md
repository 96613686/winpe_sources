# GetProcessSID(tagOCTET_STRING *)

- ea: `0x140030a44`
- end: `0x140030ca3`
- name: `?GetProcessSID@@YAJPEAUtagOCTET_STRING@@@Z`
- size: `607`
- prototype: `__int64 __fastcall(struct tagOCTET_STRING *)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14002f778`
- `0x14002f9f4`
- `0x1400302a0`
- `0x1400306f4`
- `0x140030cb0`

## callees

- `0x140002156`
- `0x140002463`
- `0x140030a44`
- `0x140034ce4`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x140030b64`
- `ADVAPI32!OpenProcessToken` at `0x140030b64`
- `ADVAPI32!GetTokenInformation` at `0x140030bc1`
- `ADVAPI32!GetTokenInformation` at `0x140030bc1`
- `ADVAPI32!GetLengthSid` at `0x140030bff`
- `ADVAPI32!GetLengthSid` at `0x140030bff`
- `KERNEL32!GetCurrentProcess` at `0x140030b13`
- `KERNEL32!GetCurrentProcess` at `0x140030b13`
- `KERNEL32!HeapFree` at `0x140030c81`
- `KERNEL32!HeapFree` at `0x140030c81`
- `KERNEL32!GetProcessHeap` at `0x140030aa4`
- `KERNEL32!GetProcessHeap` at `0x140030c0d`
- `KERNEL32!GetProcessHeap` at `0x140030c6d`
- `KERNEL32!GetProcessHeap` at `0x140030aa4`
- `KERNEL32!GetProcessHeap` at `0x140030c0d`
- `KERNEL32!GetProcessHeap` at `0x140030c6d`
- `KERNEL32!HeapAlloc` at `0x140030abd`
- `KERNEL32!HeapAlloc` at `0x140030c24`
- `KERNEL32!HeapAlloc` at `0x140030abd`
- `KERNEL32!HeapAlloc` at `0x140030c24`
- `KERNEL32!CloseHandle` at `0x140030c5c`
- `KERNEL32!CloseHandle` at `0x140030c5c`
- `KERNEL32!GetLastError` at `0x140030b7a`
- `KERNEL32!GetLastError` at `0x140030bd1`
- `KERNEL32!GetLastError` at `0x140030b7a`
- `KERNEL32!GetLastError` at `0x140030bd1`

## string_xrefs

- `0x140030a5e`: `GetProcessSID`
- `0x140030ae2`: `GetProcessSID`
- `0x140030b2f`: `GetProcessSID`

## pseudocode

```c
__int64 __fastcall GetProcessSID(struct tagOCTET_STRING *a1)
{
  HANDLE ProcessHeap; // rax
  PSID *v4; // rax
  CEventLogger *v5; // rcx
  PSID *v6; // rdi
  unsigned int v7; // r9d
  int v8; // ebx
  HANDLE CurrentProcess; // rax
  CEventLogger *v10; // rcx
  signed int LastError; // eax
  CEventLogger *v12; // rcx
  signed int v13; // eax
  CEventLogger *v14; // rcx
  size_t LengthSid; // rbp
  HANDLE v16; // rax
  BYTE *v17; // rax
  HANDLE v18; // rax
  DWORD ReturnLength; // [rsp+50h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+10h] BYREF

  if ( !a1 )
  {
    CEventLogger::LogError(
      0,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
      0x31u,
      L"GetProcessSID",
      0x80070057);
    return 2147942487LL;
  }
  TokenHandle = 0;
  ReturnLength = 0;
  ProcessHeap = GetProcessHeap();
  v4 = (PSID *)HeapAlloc(ProcessHeap, 0, 0x4000u);
  v6 = v4;
  if ( !v4 )
  {
    v7 = 60;
LABEL_5:
    v8 = -2147024882;
    CEventLogger::LogError(
      v5,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
      v7,
      L"GetProcessSID",
      0x8007000E);
    goto LABEL_23;
  }
  memset_0(v4, 0, 0x4000u);
  CurrentProcess = GetCurrentProcess();
  if ( CurrentProcess )
  {
    if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
    {
      v8 = 0;
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( v8 < 0 )
      {
        CEventLogger::LogError(
          v12,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
          0x47u,
          L"GetProcessSID",
          v8);
        goto LABEL_23;
      }
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, v6, 0x4000u, &ReturnLength) )
      goto LABEL_20;
    v13 = GetLastError();
    v8 = v13;
    if ( v13 > 0 )
      v8 = (unsigned __int16)v13 | 0x80070000;
    if ( v8 >= 0 )
    {
LABEL_20:
      LengthSid = GetLengthSid(*v6);
      v16 = GetProcessHeap();
      v17 = (BYTE *)HeapAlloc(v16, 8u, (unsigned int)LengthSid);
      a1->lpValue = v17;
      if ( !v17 )
      {
        v7 = 89;
        goto LABEL_5;
      }
      memcpy_0(v17, *v6, LengthSid);
      a1->dwLength = LengthSid;
    }
    else
    {
      CEventLogger::LogError(
        v14,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
        0x53u,
        L"GetProcessSID",
        v8);
    }
  }
  else
  {
    CEventLogger::LogError(
      v10,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
      0x40u,
      L"GetProcessSID",
      0);
    v8 = -2147467259;
  }
LABEL_23:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v6 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v6);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140030a44  mov     [rsp+arg_10], rbx
0x140030a49  mov     [rsp+arg_18], rbp
0x140030a4e  push    rsi
0x140030a4f  push    rdi
0x140030a50  push    r14
0x140030a52  sub     rsp, 30h
0x140030a56  mov     rsi, rcx
0x140030a59  test    rcx, rcx
0x140030a5c  jnz     short loc_140030A93
0x140030a5e  lea     rax, aGetprocesssid; "GetProcessSID"
0x140030a65  mov     [rsp+48h+var_20], 80070057h; unsigned int
0x140030a6d  lea     r9d, [rcx+31h]; unsigned int
0x140030a71  mov     [rsp+48h+ReturnLength], rax; unsigned __int16 *
0x140030a76  lea     r8, aBaseDiagnosisR_28; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x140030a7d  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140030a84  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140030a89  mov     eax, 80070057h
0x140030a8e  jmp     loc_140030C8F
0x140030a93  mov     [rsp+48h+TokenHandle], 0
0x140030a9c  mov     [rsp+48h+arg_0], 0
0x140030aa4  call    cs:__imp_GetProcessHeap
0x140030aab  nop     dword ptr [rax+rax+00h]
0x140030ab0  mov     ebp, 4000h
0x140030ab5  xor     edx, edx; dwFlags
0x140030ab7  mov     rcx, rax; hHeap
0x140030aba  mov     r8d, ebp; dwBytes
0x140030abd  call    cs:__imp_HeapAlloc
0x140030ac4  nop     dword ptr [rax+rax+00h]
0x140030ac9  mov     rdi, rax
0x140030acc  test    rax, rax
0x140030acf  jnz     short loc_140030B06
0x140030ad1  lea     r9d, [rax+3Ch]; unsigned int
0x140030ad5  mov     [rsp+48h+var_20], 8007000Eh; unsigned int
0x140030add  mov     ebx, 8007000Eh
0x140030ae2  lea     rax, aGetprocesssid; "GetProcessSID"
0x140030ae9  lea     r8, aBaseDiagnosisR_28; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x140030af0  mov     [rsp+48h+ReturnLength], rax; unsigned __int16 *
0x140030af5  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140030afc  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140030b01  jmp     loc_140030C52
0x140030b06  mov     r8, rbp; Size
0x140030b09  xor     edx, edx; Val
0x140030b0b  mov     rcx, rdi; void *
0x140030b0e  call    memset_0
0x140030b13  call    cs:__imp_GetCurrentProcess
0x140030b1a  nop     dword ptr [rax+rax+00h]
0x140030b1f  test    rax, rax
0x140030b22  jnz     short loc_140030B57
0x140030b24  mov     [rsp+48h+var_20], eax; unsigned int
0x140030b28  lea     r8, aBaseDiagnosisR_28; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x140030b2f  lea     rax, aGetprocesssid; "GetProcessSID"
0x140030b36  mov     r9d, 40h ; '@'; unsigned int
0x140030b3c  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140030b43  mov     [rsp+48h+ReturnLength], rax; unsigned __int16 *
0x140030b48  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140030b4d  mov     ebx, 80004005h
0x140030b52  jmp     loc_140030C52
0x140030b57  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x140030b5c  mov     edx, 20008h; DesiredAccess
0x140030b61  mov     rcx, rax; ProcessHandle
0x140030b64  call    cs:__imp_OpenProcessToken
0x140030b6b  nop     dword ptr [rax+rax+00h]
0x140030b70  mov     r14d, 80070000h
0x140030b76  test    eax, eax
0x140030b78  jnz     short loc_140030BA5
0x140030b7a  call    cs:__imp_GetLastError
0x140030b81  nop     dword ptr [rax+rax+00h]
0x140030b86  mov     ebx, eax
0x140030b88  test    eax, eax
0x140030b8a  jle     short loc_140030B92
0x140030b8c  movzx   ebx, ax
0x140030b8f  or      ebx, r14d
0x140030b92  test    ebx, ebx
0x140030b94  jns     short loc_140030BA7
0x140030b96  mov     [rsp+48h+var_20], ebx
0x140030b9a  mov     r9d, 47h ; 'G'
0x140030ba0  jmp     loc_140030AE2
0x140030ba5  xor     ebx, ebx
0x140030ba7  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x140030bac  lea     rax, [rsp+48h+arg_0]
0x140030bb1  mov     r9d, ebp; TokenInformationLength
0x140030bb4  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x140030bb9  mov     r8, rdi; TokenInformation
0x140030bbc  mov     edx, 1; TokenInformationClass
0x140030bc1  call    cs:__imp_GetTokenInformation
0x140030bc8  nop     dword ptr [rax+rax+00h]
0x140030bcd  test    eax, eax
0x140030bcf  jnz     short loc_140030BFC
0x140030bd1  call    cs:__imp_GetLastError
0x140030bd8  nop     dword ptr [rax+rax+00h]
0x140030bdd  mov     ebx, eax
0x140030bdf  test    eax, eax
0x140030be1  jle     short loc_140030BE9
0x140030be3  movzx   ebx, ax
0x140030be6  or      ebx, r14d
0x140030be9  test    ebx, ebx
0x140030beb  jns     short loc_140030BFC
0x140030bed  mov     [rsp+48h+var_20], ebx
0x140030bf1  mov     r9d, 53h ; 'S'
0x140030bf7  jmp     loc_140030AE2
0x140030bfc  mov     rcx, [rdi]; pSid
0x140030bff  call    cs:__imp_GetLengthSid
0x140030c06  nop     dword ptr [rax+rax+00h]
0x140030c0b  mov     ebp, eax
0x140030c0d  call    cs:__imp_GetProcessHeap
0x140030c14  nop     dword ptr [rax+rax+00h]
0x140030c19  mov     r8d, ebp; dwBytes
0x140030c1c  mov     edx, 8; dwFlags
0x140030c21  mov     rcx, rax; hHeap
0x140030c24  call    cs:__imp_HeapAlloc
0x140030c2b  nop     dword ptr [rax+rax+00h]
0x140030c30  mov     [rsi+8], rax
0x140030c34  test    rax, rax
0x140030c37  jnz     short loc_140030C42
0x140030c39  lea     r9d, [rax+59h]
0x140030c3d  jmp     loc_140030AD5
0x140030c42  mov     rdx, [rdi]; Src
0x140030c45  mov     r8, rbp; Size
0x140030c48  mov     rcx, rax; void *
0x140030c4b  call    memcpy_0
0x140030c50  mov     [rsi], ebp
0x140030c52  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x140030c57  test    rcx, rcx
0x140030c5a  jz      short loc_140030C68
0x140030c5c  call    cs:__imp_CloseHandle
0x140030c63  nop     dword ptr [rax+rax+00h]
0x140030c68  test    rdi, rdi
0x140030c6b  jz      short loc_140030C8D
0x140030c6d  call    cs:__imp_GetProcessHeap
0x140030c74  nop     dword ptr [rax+rax+00h]
0x140030c79  mov     r8, rdi; lpMem
0x140030c7c  xor     edx, edx; dwFlags
0x140030c7e  mov     rcx, rax; hHeap
0x140030c81  call    cs:__imp_HeapFree
0x140030c88  nop     dword ptr [rax+rax+00h]
0x140030c8d  mov     eax, ebx
0x140030c8f  mov     rbx, [rsp+48h+arg_10]
0x140030c94  mov     rbp, [rsp+48h+arg_18]
0x140030c99  add     rsp, 30h
0x140030c9d  pop     r14
0x140030c9f  pop     rdi
0x140030ca0  pop     rsi
0x140030ca1  retn
```
