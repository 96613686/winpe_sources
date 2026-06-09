# GetTokenFromHwnd(HWND__ *,void * *,ulong)

- ea: `0x18008c16c`
- end: `0x18008c260`
- name: `?GetTokenFromHwnd@@YAJPEAUHWND__@@PEAPEAXK@Z`
- size: `244`
- prototype: `HRESULT __fastcall(HWND__ *hWnd, void **phToken, unsigned int hWnd)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019864`

## callees

- `0x18001c778`
- `0x18008c16c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c1fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008c1fc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008c1d1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008c1d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c22d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c241`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c22d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008c241`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008c1b2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008c1b2`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18008c1ec`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18008c1ec`
- `USER32!GetWindowThreadProcessId` at `0x18008c196`
- `USER32!GetWindowThreadProcessId` at `0x18008c196`

## pseudocode

```c
__int64 __fastcall GetTokenFromHwnd(HWND hWnd, void **phToken, unsigned int a3)
{
  unsigned int v3; // ebx
  void *v5; // rdi
  HANDLE v6; // rax
  signed int LastError; // eax
  void *hPrimaryToken; // [rsp+38h] [rbp+10h] BYREF
  unsigned int processID; // [rsp+40h] [rbp+18h] BYREF

  processID = 0;
  v3 = 0;
  *phToken = 0;
  hPrimaryToken = 0;
  v5 = 0;
  if ( !GetWindowThreadProcessId(hWnd, &processID)
    || (v6 = OpenProcess(0x400u, 0, processID), (v5 = v6) == 0)
    || !OpenProcessToken(v6, 0xEu, &hPrimaryToken)
    || !DuplicateToken(hPrimaryToken, SecurityImpersonation, phToken) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    OleInternalOriginateError(v3, 0x138u);
  }
  if ( hPrimaryToken )
    CloseHandle(hPrimaryToken);
  if ( v5 )
    CloseHandle(v5);
  return v3;
}

```

## disassembly

```asm
0x18008c16c  mov     rax, rsp
0x18008c16f  mov     [rax+8], rbx
0x18008c173  mov     [rax+20h], rsi
0x18008c177  mov     [rax+18h], r8d
0x18008c17b  push    rdi
0x18008c17c  sub     rsp, 20h
0x18008c180  and     dword ptr [rax+18h], 0
0x18008c184  xor     ebx, ebx
0x18008c186  and     [phToken], rbx
0x18008c189  mov     rsi, phToken
0x18008c18c  and     [rax+10h], rbx
0x18008c190  lea     phToken, [rax+18h]; lpdwProcessId
0x18008c194  xor     edi, edi
0x18008c196  call    cs:__imp_GetWindowThreadProcessId
0x18008c19d  nop     dword ptr [rax+rax+00h]
0x18008c1a2  test    eax, eax
0x18008c1a4  jz      short loc_18008C1FC
0x18008c1a6  mov     r8d, [rsp+28h+processID]; dwProcessId
0x18008c1ab  xor     edx, edx; bInheritHandle
0x18008c1ad  mov     ecx, 400h; dwDesiredAccess
0x18008c1b2  call    cs:__imp_OpenProcess
0x18008c1b9  nop     dword ptr [rax+rax+00h]
0x18008c1be  mov     rdi, rax
0x18008c1c1  test    rax, rax
0x18008c1c4  jz      short loc_18008C1FC
0x18008c1c6  lea     r8, [rsp+28h+hPrimaryToken]; TokenHandle
0x18008c1cb  mov     hWnd, rax; ProcessHandle
0x18008c1ce  lea     edx, [rbx+0Eh]; DesiredAccess
0x18008c1d1  call    cs:__imp_OpenProcessToken
0x18008c1d8  nop     dword ptr [rax+rax+00h]
0x18008c1dd  test    eax, eax
0x18008c1df  jz      short loc_18008C1FC
0x18008c1e1  mov     hWnd, [rsp+28h+hPrimaryToken]; ExistingTokenHandle
0x18008c1e6  lea     edx, [rbx+2]; ImpersonationLevel
0x18008c1e9  mov     r8, rsi; DuplicateTokenHandle
0x18008c1ec  call    cs:__imp_DuplicateToken
0x18008c1f3  nop     dword ptr [rax+rax+00h]
0x18008c1f8  test    eax, eax
0x18008c1fa  jnz     short loc_18008C223
0x18008c1fc  call    cs:__imp_GetLastError
0x18008c203  nop     dword ptr [rax+rax+00h]
0x18008c208  mov     ebx, eax
0x18008c20a  test    eax, eax
0x18008c20c  jle     short loc_18008C217
0x18008c20e  movzx   ebx, ax
0x18008c211  or      ebx, 80070000h
0x18008c217  mov     edx, 138h; messageID
0x18008c21c  mov     ecx, ebx; hr
0x18008c21e  call    ?OleInternalOriginateError@@YAXJG@Z; OleInternalOriginateError(long,ushort)
0x18008c223  mov     hWnd, [rsp+28h+hPrimaryToken]; hObject
0x18008c228  test    hWnd, hWnd
0x18008c22b  jz      short loc_18008C239
0x18008c22d  call    cs:__imp_CloseHandle
0x18008c234  nop     dword ptr [rax+rax+00h]
0x18008c239  test    rdi, rdi
0x18008c23c  jz      short loc_18008C24D
0x18008c23e  mov     hWnd, rdi; hObject
0x18008c241  call    cs:__imp_CloseHandle
0x18008c248  nop     dword ptr [rax+rax+00h]
0x18008c24d  mov     rsi, [rsp+28h+arg_18]
0x18008c252  mov     eax, ebx
0x18008c254  mov     rbx, [rsp+28h+arg_0]
0x18008c259  add     rsp, 20h
0x18008c25d  pop     rdi
0x18008c25e  retn
```
