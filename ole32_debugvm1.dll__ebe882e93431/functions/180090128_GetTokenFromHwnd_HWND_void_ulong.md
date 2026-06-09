# GetTokenFromHwnd(HWND__ *,void * *,ulong)

- ea: `0x180090128`
- end: `0x1800901f6`
- name: `?GetTokenFromHwnd@@YAJPEAUHWND__@@PEAPEAXK@Z`
- size: `206`
- prototype: `HRESULT __fastcall(HWND__ *hWnd, void **phToken, unsigned int hWnd)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e034`

## callees

- `0x180019454`
- `0x180090128`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800901a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800901a5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180090184`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180090184`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800901d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800901de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800901d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800901de`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180090169`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180090169`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18009019b`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18009019b`
- `USER32!GetWindowThreadProcessId` at `0x180090153`
- `USER32!GetWindowThreadProcessId` at `0x180090153`

## pseudocode

```c
__int64 __fastcall GetTokenFromHwnd(HWND hWnd, void **phToken, unsigned int a3)
{
  void *v3; // rdi
  HANDLE v5; // rax
  unsigned int v6; // ebx
  signed int LastError; // eax
  void *hPrimaryToken; // [rsp+38h] [rbp+10h] BYREF
  unsigned int processID; // [rsp+40h] [rbp+18h] BYREF

  v3 = 0;
  processID = 0;
  *phToken = 0;
  hPrimaryToken = 0;
  if ( !GetWindowThreadProcessId(hWnd, &processID)
    || (v5 = OpenProcess(0x400u, 0, processID), (v3 = v5) == 0)
    || !OpenProcessToken(v5, 0xEu, &hPrimaryToken)
    || (v6 = 0, !DuplicateToken(hPrimaryToken, SecurityImpersonation, phToken)) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    OleInternalOriginateError(v6, 0x138u);
  }
  if ( hPrimaryToken )
    CloseHandle(hPrimaryToken);
  if ( v3 )
    CloseHandle(v3);
  return v6;
}

```

## disassembly

```asm
0x180090128  mov     rax, rsp
0x18009012b  mov     [rax+8], rbx
0x18009012f  mov     [rax+20h], rsi
0x180090133  mov     [rax+18h], r8d
0x180090137  push    rdi
0x180090138  sub     rsp, 20h
0x18009013c  xor     edi, edi
0x18009013e  mov     dword ptr [rax+18h], 0
0x180090145  mov     [phToken], rdi
0x180090148  mov     rsi, phToken
0x18009014b  lea     phToken, [rax+18h]; lpdwProcessId
0x18009014f  mov     [rax+10h], rdi
0x180090153  call    cs:__imp_GetWindowThreadProcessId
0x180090159  test    eax, eax
0x18009015b  jz      short loc_1800901A5
0x18009015d  mov     r8d, [rsp+28h+processID]; dwProcessId
0x180090162  xor     edx, edx; bInheritHandle
0x180090164  mov     ecx, 400h; dwDesiredAccess
0x180090169  call    cs:__imp_OpenProcess
0x18009016f  mov     rdi, rax
0x180090172  test    rax, rax
0x180090175  jz      short loc_1800901A5
0x180090177  lea     r8, [rsp+28h+hPrimaryToken]; TokenHandle
0x18009017c  mov     edx, 0Eh; DesiredAccess
0x180090181  mov     hWnd, rax; ProcessHandle
0x180090184  call    cs:__imp_OpenProcessToken
0x18009018a  test    eax, eax
0x18009018c  jz      short loc_1800901A5
0x18009018e  mov     hWnd, [rsp+28h+hPrimaryToken]; ExistingTokenHandle
0x180090193  xor     ebx, ebx
0x180090195  mov     r8, rsi; DuplicateTokenHandle
0x180090198  lea     edx, [rbx+2]; ImpersonationLevel
0x18009019b  call    cs:__imp_DuplicateToken
0x1800901a1  test    eax, eax
0x1800901a3  jnz     short loc_1800901C6
0x1800901a5  call    cs:__imp_GetLastError
0x1800901ab  mov     ebx, eax
0x1800901ad  test    eax, eax
0x1800901af  jle     short loc_1800901BA
0x1800901b1  movzx   ebx, ax
0x1800901b4  or      ebx, 80070000h
0x1800901ba  mov     edx, 138h; messageID
0x1800901bf  mov     ecx, ebx; hr
0x1800901c1  call    ?OleInternalOriginateError@@YAXJG@Z; OleInternalOriginateError(long,ushort)
0x1800901c6  mov     hWnd, [rsp+28h+hPrimaryToken]; hObject
0x1800901cb  test    hWnd, hWnd
0x1800901ce  jz      short loc_1800901D6
0x1800901d0  call    cs:__imp_CloseHandle
0x1800901d6  test    rdi, rdi
0x1800901d9  jz      short loc_1800901E4
0x1800901db  mov     hWnd, rdi; hObject
0x1800901de  call    cs:__imp_CloseHandle
0x1800901e4  mov     rsi, [rsp+28h+arg_18]
0x1800901e9  mov     eax, ebx
0x1800901eb  mov     rbx, [rsp+28h+arg_0]
0x1800901f0  add     rsp, 20h
0x1800901f4  pop     rdi
0x1800901f5  retn
```
