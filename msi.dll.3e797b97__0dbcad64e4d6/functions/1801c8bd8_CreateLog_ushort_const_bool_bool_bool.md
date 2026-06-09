# CreateLog(ushort const *,bool,bool,bool)

- ea: `0x1801c8bd8`
- end: `0x1801c9061`
- name: `?CreateLog@@YA_NPEBG_N11@Z`
- size: `1161`
- prototype: `bool __fastcall(const unsigned __int16 *, bool, bool, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18004dcac`
- `0x1801bb9b0`

## callees

- `0x1800811d8`
- `0x18014ae8c`
- `0x1801c8bd8`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x1801c8d48`
- `ADVAPI32!SetThreadToken` at `0x1801c8dd0`
- `ADVAPI32!SetThreadToken` at `0x1801c8d48`
- `ADVAPI32!SetThreadToken` at `0x1801c8dd0`
- `ADVAPI32!OpenThreadToken` at `0x1801c8d30`
- `ADVAPI32!OpenThreadToken` at `0x1801c8d30`
- `KERNEL32!CloseHandle` at `0x1801c8c0a`
- `KERNEL32!CloseHandle` at `0x1801c8c22`
- `KERNEL32!CloseHandle` at `0x1801c8de7`
- `KERNEL32!CloseHandle` at `0x1801c8fa0`
- `KERNEL32!CloseHandle` at `0x1801c8fc3`
- `KERNEL32!CloseHandle` at `0x1801c8c0a`
- `KERNEL32!CloseHandle` at `0x1801c8c22`
- `KERNEL32!CloseHandle` at `0x1801c8de7`
- `KERNEL32!CloseHandle` at `0x1801c8fa0`
- `KERNEL32!CloseHandle` at `0x1801c8fc3`
- `KERNEL32!GetLastError` at `0x1801c8cf3`
- `KERNEL32!GetLastError` at `0x1801c8ed0`
- `KERNEL32!GetLastError` at `0x1801c8cf3`
- `KERNEL32!GetLastError` at `0x1801c8ed0`
- `KERNEL32!GlobalAlloc` at `0x1801c8f79`
- `KERNEL32!GlobalAlloc` at `0x1801c8f79`
- `KERNEL32!WaitForSingleObject` at `0x1801c8ef1`
- `KERNEL32!WaitForSingleObject` at `0x1801c8ef1`
- `KERNEL32!GetCurrentThread` at `0x1801c8d08`
- `KERNEL32!GetCurrentThread` at `0x1801c8d08`
- `KERNEL32!GetSystemInfo` at `0x1801c9038`
- `KERNEL32!GetSystemInfo` at `0x1801c9038`
- `KERNEL32!lstrcmpiW` at `0x1801c8e55`
- `KERNEL32!lstrcmpiW` at `0x1801c8e55`
- `KERNEL32!CreateFileW` at `0x1801c8cb0`
- `KERNEL32!CreateFileW` at `0x1801c8d9c`
- `KERNEL32!CreateFileW` at `0x1801c8cb0`
- `KERNEL32!CreateFileW` at `0x1801c8d9c`
- `KERNEL32!SetFilePointer` at `0x1801c8e74`
- `KERNEL32!SetFilePointer` at `0x1801c8e74`
- `KERNEL32!Wow64DisableWow64FsRedirection` at `0x1801c8c63`
- `KERNEL32!Wow64DisableWow64FsRedirection` at `0x1801c8d69`
- `KERNEL32!Wow64DisableWow64FsRedirection` at `0x1801c8c63`
- `KERNEL32!Wow64DisableWow64FsRedirection` at `0x1801c8d69`
- `KERNEL32!Wow64RevertWow64FsRedirection` at `0x1801c8cd0`
- `KERNEL32!Wow64RevertWow64FsRedirection` at `0x1801c8dbc`
- `KERNEL32!Wow64RevertWow64FsRedirection` at `0x1801c8cd0`
- `KERNEL32!Wow64RevertWow64FsRedirection` at `0x1801c8dbc`
- `KERNEL32!WriteFile` at `0x1801c8ec0`
- `KERNEL32!WriteFile` at `0x1801c8ec0`
- `KERNEL32!GetOverlappedResult` at `0x1801c8f14`
- `KERNEL32!GetOverlappedResult` at `0x1801c8f14`

## pseudocode

```c
char __fastcall CreateLog(const unsigned __int16 *a1, unsigned __int8 a2, char a3, char a4)
{
  int v5; // r15d
  char v8; // di
  BOOL v9; // ebx
  DWORD v11; // eax
  _DWORD *v12; // rax
  _DWORD *v13; // rbx
  HANDLE v14; // rcx
  int v15; // edx
  void *TokenHandle; // [rsp+40h] [rbp-29h] BYREF
  void *Thread; // [rsp+48h] [rbp-21h] BYREF
  struct _SYSTEM_INFO Overlapped[2]; // [rsp+50h] [rbp-19h] BYREF
  PVOID OldValue; // [rsp+D0h] [rbp+67h] BYREF

  v5 = a2;
  if ( hObject )
    CloseHandle(hObject);
  if ( hMutex )
  {
    CloseHandle(hMutex);
    hMutex = 0;
  }
  if ( a1 )
  {
    if ( g_fWoW || !g_fWinNT64 )
    {
      v9 = 1;
      OldValue = 0;
      v8 = 0;
    }
    else
    {
      OldValue = 0;
      v8 = 1;
      v9 = Wow64DisableWow64FsRedirection(&OldValue);
    }
    hObject = CreateFileW(a1, 0x40000000u, 3u, 0, 2 * v5 + 2, 0x40100080u, 0);
    if ( v8 && v9 )
      Wow64RevertWow64FsRedirection(OldValue);
    if ( a4 )
    {
      if ( hObject != (HANDLE)-1LL )
        goto LABEL_32;
      if ( GetLastError() == 5 )
      {
        TokenHandle = (void *)-1LL;
        Thread = GetCurrentThread();
        if ( !OpenThreadToken(Thread, 0xEu, 1, &TokenHandle) || !SetThreadToken(0, 0) )
          goto LABEL_26;
        if ( v8 && v9 )
          v9 = Wow64DisableWow64FsRedirection(&OldValue);
        hObject = CreateFileW(a1, 0x40000000u, 3u, 0, 2 * v5 + 2, 0x40100080u, 0);
        if ( v8 && v9 )
          Wow64RevertWow64FsRedirection(OldValue);
        if ( !SetThreadToken(&Thread, TokenHandle) )
        {
          CloseHandle(hObject);
LABEL_26:
          hObject = 0;
          CHandle::~CHandle((CHandle *)&TokenHandle);
          return 0;
        }
        CHandle::~CHandle((CHandle *)&TokenHandle);
      }
    }
  }
  else
  {
    hObject = (HANDLE)-1LL;
  }
  if ( hObject == (HANDLE)-1LL )
  {
    hObject = 0;
    return 0;
  }
LABEL_32:
  if ( (_BYTE)v5 && lstrcmpiW(a1, L"NUL") )
  {
    v11 = SetFilePointer(hObject, 0, 0, 2u);
    if ( v11 == -1 )
      goto LABEL_48;
    if ( v11 )
      goto LABEL_42;
  }
  LOWORD(OldValue) = -257;
  LODWORD(TokenHandle) = 0;
  memset(Overlapped, 0, 32);
  if ( !WriteFile(hObject, &OldValue, 2u, (LPDWORD)&TokenHandle, (LPOVERLAPPED)Overlapped) )
  {
    if ( GetLastError() != 997 )
      goto LABEL_48;
    while ( Overlapped[0].dwOemId == 259 )
      WaitForSingleObject(hObject, 0xFFFFFFFF);
    if ( !GetOverlappedResult(hObject, (LPOVERLAPPED)Overlapped, (LPDWORD)&TokenHandle, 0) )
    {
LABEL_48:
      if ( hObject )
      {
        CloseHandle(hObject);
        hObject = 0;
      }
      if ( hMutex )
      {
        CloseHandle(hMutex);
        hMutex = 0;
      }
      return 0;
    }
  }
LABEL_42:
  if ( CreatePerUserFileLockMutex(a1, hObject, &hMutex) )
    qword_1803136F8 = 0x100000003LL;
  else
    qword_1803136F8 = 0;
  if ( !g_fFlushEachLine && !a3 )
  {
    v12 = GlobalAlloc(0x40u, 0x70u);
    *((_QWORD *)&xmmword_180313710 + 1) = v12;
    v13 = v12;
    if ( !v12 )
      goto LABEL_48;
    v14 = hObject;
    v15 = (unsigned __int8)byte_180313720;
    *(_QWORD *)v12 = 0;
    v12[2] = 0;
    v12[6] = 1;
    *((_QWORD *)v12 + 2) = v12 + 8;
    *((_QWORD *)v12 + 5) = 0;
    v12[12] = 0;
    *((_QWORD *)v12 + 7) = v12 + 18;
    v12[16] = 1;
    *((_QWORD *)v12 + 10) = v14;
    v12[26] = v15;
    v12[22] = 0;
    *((_BYTE *)v12 + 96) = 0;
    v12[25] = 0;
    memset(Overlapped, 0, 48);
    GetSystemInfo(Overlapped);
    v13[23] = Overlapped[0].dwPageSize;
  }
  return 1;
}

```

## disassembly

```asm
0x1801c8bd8  push    rbp
0x1801c8bda  push    rbx
0x1801c8bdb  push    rsi
0x1801c8bdc  push    rdi
0x1801c8bdd  push    r12
0x1801c8bdf  push    r13
0x1801c8be1  push    r14
0x1801c8be3  push    r15
0x1801c8be5  lea     rbp, [rsp-1Fh]
0x1801c8bea  sub     rsp, 88h
0x1801c8bf1  mov     rsi, rcx
0x1801c8bf4  movzx   r15d, dl
0x1801c8bf8  mov     rcx, cs:hObject; hObject
0x1801c8bff  mov     r14b, r9b
0x1801c8c02  mov     r13b, r8b
0x1801c8c05  test    rcx, rcx
0x1801c8c08  jz      short loc_1801C8C16
0x1801c8c0a  call    cs:__imp_CloseHandle
0x1801c8c11  nop     dword ptr [rax+rax+00h]
0x1801c8c16  mov     rcx, cs:hMutex; hObject
0x1801c8c1d  test    rcx, rcx
0x1801c8c20  jz      short loc_1801C8C39
0x1801c8c22  call    cs:__imp_CloseHandle
0x1801c8c29  nop     dword ptr [rax+rax+00h]
0x1801c8c2e  mov     cs:hMutex, 0
0x1801c8c39  test    rsi, rsi
0x1801c8c3c  jz      loc_1801C8E19
0x1801c8c42  cmp     cs:?g_fWoW@@3_NA, 0; bool g_fWoW
0x1801c8c49  jnz     short loc_1801C8C73
0x1801c8c4b  cmp     cs:?g_fWinNT64@@3_NA, 0; bool g_fWinNT64
0x1801c8c52  jz      short loc_1801C8C73
0x1801c8c54  lea     rcx, [rbp+57h+OldValue]; OldValue
0x1801c8c58  mov     [rbp+57h+OldValue], 0
0x1801c8c60  mov     dil, 1
0x1801c8c63  call    cs:__imp_Wow64DisableWow64FsRedirection
0x1801c8c6a  nop     dword ptr [rax+rax+00h]
0x1801c8c6f  mov     ebx, eax
0x1801c8c71  jmp     short loc_1801C8C83
0x1801c8c73  mov     ebx, 1
0x1801c8c78  mov     [rbp+57h+OldValue], 0
0x1801c8c80  xor     dil, dil
0x1801c8c83  xor     r9d, r9d; lpSecurityAttributes
0x1801c8c86  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x1801c8c8f  lea     r12d, ds:2[r15*2]
0x1801c8c97  mov     [rsp+0C0h+dwFlagsAndAttributes], 40100080h; dwFlagsAndAttributes
0x1801c8c9f  mov     edx, 40000000h; dwDesiredAccess
0x1801c8ca4  mov     [rsp+0C0h+dwCreationDisposition], r12d; dwCreationDisposition
0x1801c8ca9  mov     rcx, rsi; lpFileName
0x1801c8cac  lea     r8d, [r9+3]; dwShareMode
0x1801c8cb0  call    cs:__imp_CreateFileW
0x1801c8cb7  nop     dword ptr [rax+rax+00h]
0x1801c8cbc  mov     cs:hObject, rax
0x1801c8cc3  test    dil, dil
0x1801c8cc6  jz      short loc_1801C8CDC
0x1801c8cc8  test    ebx, ebx
0x1801c8cca  jz      short loc_1801C8CDC
0x1801c8ccc  mov     rcx, [rbp+57h+OldValue]; OlValue
0x1801c8cd0  call    cs:__imp_Wow64RevertWow64FsRedirection
0x1801c8cd7  nop     dword ptr [rax+rax+00h]
0x1801c8cdc  test    r14b, r14b
0x1801c8cdf  jz      loc_1801C8E24
0x1801c8ce5  cmp     cs:hObject, 0FFFFFFFFFFFFFFFFh
0x1801c8ced  jnz     loc_1801C8E3B
0x1801c8cf3  call    cs:__imp_GetLastError
0x1801c8cfa  nop     dword ptr [rax+rax+00h]
0x1801c8cff  cmp     eax, 5
0x1801c8d02  jnz     loc_1801C8E24
0x1801c8d08  call    cs:__imp_GetCurrentThread
0x1801c8d0f  nop     dword ptr [rax+rax+00h]
0x1801c8d14  mov     edx, 0Eh; DesiredAccess
0x1801c8d19  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1801c8d21  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1801c8d25  mov     [rbp+57h+Thread], rax
0x1801c8d29  mov     rcx, rax; ThreadHandle
0x1801c8d2c  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x1801c8d30  call    cs:__imp_OpenThreadToken
0x1801c8d37  nop     dword ptr [rax+rax+00h]
0x1801c8d3c  test    eax, eax
0x1801c8d3e  jz      loc_1801C8DF3
0x1801c8d44  xor     edx, edx; Token
0x1801c8d46  xor     ecx, ecx; Thread
0x1801c8d48  call    cs:__imp_SetThreadToken
0x1801c8d4f  nop     dword ptr [rax+rax+00h]
0x1801c8d54  test    eax, eax
0x1801c8d56  jz      loc_1801C8DF3
0x1801c8d5c  test    dil, dil
0x1801c8d5f  jz      short loc_1801C8D77
0x1801c8d61  test    ebx, ebx
0x1801c8d63  jz      short loc_1801C8D77
0x1801c8d65  lea     rcx, [rbp+57h+OldValue]; OldValue
0x1801c8d69  call    cs:__imp_Wow64DisableWow64FsRedirection
0x1801c8d70  nop     dword ptr [rax+rax+00h]
0x1801c8d75  mov     ebx, eax
0x1801c8d77  xor     r9d, r9d; lpSecurityAttributes
0x1801c8d7a  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x1801c8d83  mov     [rsp+0C0h+dwFlagsAndAttributes], 40100080h; dwFlagsAndAttributes
0x1801c8d8b  mov     edx, 40000000h; dwDesiredAccess
0x1801c8d90  mov     rcx, rsi; lpFileName
0x1801c8d93  mov     [rsp+0C0h+dwCreationDisposition], r12d; dwCreationDisposition
0x1801c8d98  lea     r8d, [r9+3]; dwShareMode
0x1801c8d9c  call    cs:__imp_CreateFileW
0x1801c8da3  nop     dword ptr [rax+rax+00h]
0x1801c8da8  mov     cs:hObject, rax
0x1801c8daf  test    dil, dil
0x1801c8db2  jz      short loc_1801C8DC8
0x1801c8db4  test    ebx, ebx
0x1801c8db6  jz      short loc_1801C8DC8
0x1801c8db8  mov     rcx, [rbp+57h+OldValue]; OlValue
0x1801c8dbc  call    cs:__imp_Wow64RevertWow64FsRedirection
0x1801c8dc3  nop     dword ptr [rax+rax+00h]
0x1801c8dc8  mov     rdx, [rbp+57h+TokenHandle]; Token
0x1801c8dcc  lea     rcx, [rbp+57h+Thread]; Thread
0x1801c8dd0  call    cs:__imp_SetThreadToken
0x1801c8dd7  nop     dword ptr [rax+rax+00h]
0x1801c8ddc  test    eax, eax
0x1801c8dde  jnz     short loc_1801C8E0E
0x1801c8de0  mov     rcx, cs:hObject; hObject
0x1801c8de7  call    cs:__imp_CloseHandle
0x1801c8dee  nop     dword ptr [rax+rax+00h]
0x1801c8df3  lea     rcx, [rbp+57h+TokenHandle]; this
0x1801c8df7  mov     cs:hObject, 0
0x1801c8e02  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x1801c8e07  xor     al, al
0x1801c8e09  jmp     loc_1801C904C
0x1801c8e0e  lea     rcx, [rbp+57h+TokenHandle]; this
0x1801c8e12  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x1801c8e17  jmp     short loc_1801C8E24
0x1801c8e19  mov     cs:hObject, 0FFFFFFFFFFFFFFFFh
0x1801c8e24  cmp     cs:hObject, 0FFFFFFFFFFFFFFFFh
0x1801c8e2c  jnz     short loc_1801C8E3B
0x1801c8e2e  mov     cs:hObject, 0
0x1801c8e39  jmp     short loc_1801C8E07
0x1801c8e3b  or      r14d, 0FFFFFFFFh
0x1801c8e3f  xor     edi, edi
0x1801c8e41  mov     ebx, 2
0x1801c8e46  test    r15b, r15b
0x1801c8e49  jz      short loc_1801C8E91
0x1801c8e4b  lea     rdx, aNul; "NUL"
0x1801c8e52  mov     rcx, rsi; lpString1
0x1801c8e55  call    cs:__imp_lstrcmpiW
0x1801c8e5c  nop     dword ptr [rax+rax+00h]
0x1801c8e61  test    eax, eax
0x1801c8e63  jz      short loc_1801C8E91
0x1801c8e65  mov     rcx, cs:hObject; hFile
0x1801c8e6c  mov     r9d, ebx; dwMoveMethod
0x1801c8e6f  xor     r8d, r8d; lpDistanceToMoveHigh
0x1801c8e72  xor     edx, edx; lDistanceToMove
0x1801c8e74  call    cs:__imp_SetFilePointer
0x1801c8e7b  nop     dword ptr [rax+rax+00h]
0x1801c8e80  cmp     eax, r14d
0x1801c8e83  jz      loc_1801C8F94
0x1801c8e89  test    eax, eax
0x1801c8e8b  jnz     loc_1801C8F24
0x1801c8e91  mov     rcx, cs:hObject; hFile
0x1801c8e98  lea     rax, [rbp+57h+Overlapped]
0x1801c8e9c  xorps   xmm0, xmm0
0x1801c8e9f  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; lpOverlapped
0x1801c8ea4  lea     r9, [rbp+57h+TokenHandle]; lpNumberOfBytesWritten
0x1801c8ea8  mov     word ptr [rbp+57h+OldValue], 0FEFFh
0x1801c8eae  mov     r8d, ebx; nNumberOfBytesToWrite
0x1801c8eb1  mov     dword ptr [rbp+57h+TokenHandle], edi
0x1801c8eb4  lea     rdx, [rbp+57h+OldValue]; lpBuffer
0x1801c8eb8  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x1801c8ebc  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x1801c8ec0  call    cs:__imp_WriteFile
0x1801c8ec7  nop     dword ptr [rax+rax+00h]
0x1801c8ecc  test    eax, eax
0x1801c8ece  jnz     short loc_1801C8F24
0x1801c8ed0  call    cs:__imp_GetLastError
0x1801c8ed7  nop     dword ptr [rax+rax+00h]
0x1801c8edc  cmp     eax, 3E5h
0x1801c8ee1  jnz     loc_1801C8F94
0x1801c8ee7  mov     ebx, 103h
0x1801c8eec  jmp     short loc_1801C8EFD
0x1801c8eee  mov     edx, r14d; dwMilliseconds
0x1801c8ef1  call    cs:__imp_WaitForSingleObject
0x1801c8ef8  nop     dword ptr [rax+rax+00h]
0x1801c8efd  mov     rcx, cs:hObject; hFile
0x1801c8f04  cmp     dword ptr [rbp+57h+Overlapped.Internal], ebx
0x1801c8f07  jz      short loc_1801C8EEE
0x1801c8f09  xor     r9d, r9d; bWait
0x1801c8f0c  lea     r8, [rbp+57h+TokenHandle]; lpNumberOfBytesTransferred
0x1801c8f10  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x1801c8f14  call    cs:__imp_GetOverlappedResult
0x1801c8f1b  nop     dword ptr [rax+rax+00h]
0x1801c8f20  test    eax, eax
0x1801c8f22  jz      short loc_1801C8F94
0x1801c8f24  mov     rdx, cs:hObject; void *
0x1801c8f2b  lea     r8, hMutex; void **
0x1801c8f32  mov     rcx, rsi; unsigned __int16 *
0x1801c8f35  call    ?CreatePerUserFileLockMutex@@YAKPEBGPEAXAEAPEAX@Z; CreatePerUserFileLockMutex(ushort const *,void *,void * &)
0x1801c8f3a  test    eax, eax
0x1801c8f3c  jnz     short loc_1801C8F47
0x1801c8f3e  mov     cs:qword_1803136F8, rdi
0x1801c8f45  jmp     short loc_1801C8F5B
0x1801c8f47  mov     dword ptr cs:qword_1803136F8, 3
0x1801c8f51  mov     dword ptr cs:qword_1803136F8+4, 1
0x1801c8f5b  cmp     cs:?g_fFlushEachLine@@3_NA, dil; bool g_fFlushEachLine
0x1801c8f62  jnz     loc_1801C904A
0x1801c8f68  test    r13b, r13b
0x1801c8f6b  jnz     loc_1801C904A
0x1801c8f71  mov     edx, 70h ; 'p'; dwBytes
0x1801c8f76  lea     ecx, [rdx-30h]; uFlags
0x1801c8f79  call    cs:__imp_GlobalAlloc
0x1801c8f80  nop     dword ptr [rax+rax+00h]
0x1801c8f85  mov     qword ptr cs:xmmword_180313710+8, rax
0x1801c8f8c  mov     rbx, rax
0x1801c8f8f  test    rax, rax
0x1801c8f92  jnz     short loc_1801C8FDB
0x1801c8f94  mov     rcx, cs:hObject; hObject
0x1801c8f9b  test    rcx, rcx
0x1801c8f9e  jz      short loc_1801C8FB3
0x1801c8fa0  call    cs:__imp_CloseHandle
0x1801c8fa7  nop     dword ptr [rax+rax+00h]
0x1801c8fac  mov     cs:hObject, rdi
0x1801c8fb3  mov     rcx, cs:hMutex; hObject
0x1801c8fba  test    rcx, rcx
0x1801c8fbd  jz      loc_1801C8E07
0x1801c8fc3  call    cs:__imp_CloseHandle
0x1801c8fca  nop     dword ptr [rax+rax+00h]
0x1801c8fcf  mov     cs:hMutex, rdi
0x1801c8fd6  jmp     loc_1801C8E07
0x1801c8fdb  mov     rcx, cs:hObject
0x1801c8fe2  xorps   xmm0, xmm0
0x1801c8fe5  movzx   edx, cs:byte_180313720
0x1801c8fec  mov     [rax], rdi
0x1801c8fef  mov     [rax+8], edi
0x1801c8ff2  mov     dword ptr [rax+18h], 1
0x1801c8ff9  add     rax, 20h ; ' '
0x1801c8ffd  mov     [rbx+10h], rax
0x1801c9001  lea     rax, [rbx+48h]
0x1801c9005  mov     [rbx+28h], rdi
0x1801c9009  mov     [rbx+30h], edi
0x1801c900c  mov     [rbx+38h], rax
0x1801c9010  mov     dword ptr [rbx+40h], 1
0x1801c9017  mov     [rbx+50h], rcx
0x1801c901b  lea     rcx, [rbp+57h+Overlapped]; lpSystemInfo
0x1801c901f  mov     [rbx+68h], edx
0x1801c9022  mov     [rbx+58h], edi
0x1801c9025  mov     [rbx+60h], dil
0x1801c9029  mov     [rbx+64h], edi
0x1801c902c  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x1801c9030  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x1801c9034  movups  [rbp+57h+var_50], xmm0
0x1801c9038  call    cs:__imp_GetSystemInfo
0x1801c903f  nop     dword ptr [rax+rax+00h]
0x1801c9044  mov     ecx, dword ptr [rbp+57h+Overlapped.Internal+4]
0x1801c9047  mov     [rbx+5Ch], ecx
0x1801c904a  mov     al, 1
0x1801c904c  add     rsp, 88h
0x1801c9053  pop     r15
0x1801c9055  pop     r14
0x1801c9057  pop     r13
0x1801c9059  pop     r12
0x1801c905b  pop     rdi
0x1801c905c  pop     rsi
0x1801c905d  pop     rbx
0x1801c905e  pop     rbp
0x1801c905f  retn
```
