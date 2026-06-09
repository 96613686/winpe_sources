# CAsyncHttp::Close(void)

- ea: `0x1800a67ac`
- end: `0x1800a68fa`
- name: `?Close@CAsyncHttp@@QEAAJXZ`
- size: `334`
- prototype: `__int64 __fastcall(CAsyncHttp *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800a620c`
- `0x1800a6f84`
- `0x1800ada04`
- `0x1800ae2a0`
- `0x1800af5c0`

## callees

- `0x1800a6744`
- `0x1800a67ac`
- `0x1800cd010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800a682b`
- `KERNEL32!WaitForSingleObject` at `0x1800a682b`
- `KERNEL32!CloseHandle` at `0x1800a6834`
- `KERNEL32!CloseHandle` at `0x1800a6834`
- `KERNEL32!LeaveCriticalSection` at `0x1800a6876`
- `KERNEL32!LeaveCriticalSection` at `0x1800a6876`
- `KERNEL32!EnterCriticalSection` at `0x1800a67cf`
- `KERNEL32!EnterCriticalSection` at `0x1800a67cf`
- `KERNEL32!SetEvent` at `0x1800a681f`
- `KERNEL32!SetEvent` at `0x1800a681f`
- `KERNEL32!OpenThread` at `0x1800a67e8`
- `KERNEL32!OpenThread` at `0x1800a67e8`
- `KERNEL32!GetExitCodeThread` at `0x1800a6806`
- `KERNEL32!GetExitCodeThread` at `0x1800a6806`
- `WININET!InternetCloseHandle` at `0x1800a684d`
- `WININET!InternetCloseHandle` at `0x1800a6864`
- `WININET!InternetCloseHandle` at `0x1800a684d`
- `WININET!InternetCloseHandle` at `0x1800a6864`

## pseudocode

```c
__int64 __fastcall CAsyncHttp::Close(CAsyncHttp *this)
{
  DWORD v2; // r8d
  HANDLE v3; // rax
  void *v4; // rdi
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  DWORD ExitCode; // [rsp+30h] [rbp+8h] BYREF

  CAsyncHttp::ChangeState(this, 10, 10);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v2 = *((_DWORD *)this + 698);
  if ( v2 )
  {
    v3 = OpenThread(0x100000u, 0, v2);
    v4 = v3;
    if ( v3 )
    {
      ExitCode = 0;
      GetExitCodeThread(v3, &ExitCode);
      if ( ExitCode == 259 )
      {
        v5 = (void *)*((_QWORD *)this + 11);
        if ( v5 )
          SetEvent(v5);
        WaitForSingleObject(v4, 0xFFFFFFFF);
      }
      CloseHandle(v4);
    }
    *((_DWORD *)this + 698) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 10);
  if ( v6 )
  {
    InternetCloseHandle(v6);
    *((_QWORD *)this + 10) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 9);
  if ( v7 )
  {
    InternetCloseHandle(v7);
    *((_QWORD *)this + 9) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( *((_QWORD *)this + 339) )
  {
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
    *((_QWORD *)this + 339) = 0;
  }
  if ( *((_QWORD *)this + 340) )
  {
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
    *((_QWORD *)this + 340) = 0;
  }
  *((_DWORD *)this + 692) = 1;
  CAsyncHttp::ChangeState(this, 0, 11);
  return 0;
}

```

## disassembly

```asm
0x1800a67ac  mov     [rsp+arg_8], rbx
0x1800a67b1  mov     [rsp+arg_10], rsi
0x1800a67b6  push    rdi
0x1800a67b7  sub     rsp, 20h
0x1800a67bb  mov     edx, 0Ah
0x1800a67c0  mov     rbx, rcx
0x1800a67c3  mov     r8d, edx
0x1800a67c6  call    ?ChangeState@CAsyncHttp@@AEAAXW4ASYNCHTTP_STATE@@W4ASYNCHTTP_EVENT@@@Z; CAsyncHttp::ChangeState(ASYNCHTTP_STATE,ASYNCHTTP_EVENT)
0x1800a67cb  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800a67cf  call    cs:__imp_EnterCriticalSection
0x1800a67d5  mov     r8d, [rbx+0AE8h]; dwThreadId
0x1800a67dc  test    r8d, r8d
0x1800a67df  jz      short loc_1800A6844
0x1800a67e1  xor     edx, edx; bInheritHandle
0x1800a67e3  mov     ecx, 100000h; dwDesiredAccess
0x1800a67e8  call    cs:__imp_OpenThread
0x1800a67ee  mov     rdi, rax
0x1800a67f1  test    rax, rax
0x1800a67f4  jz      short loc_1800A683A
0x1800a67f6  lea     rdx, [rsp+28h+ExitCode]; lpExitCode
0x1800a67fb  mov     [rsp+28h+ExitCode], 0
0x1800a6803  mov     rcx, rax; hThread
0x1800a6806  call    cs:__imp_GetExitCodeThread
0x1800a680c  cmp     [rsp+28h+ExitCode], 103h
0x1800a6814  jnz     short loc_1800A6831
0x1800a6816  mov     rcx, [rbx+58h]; hEvent
0x1800a681a  test    rcx, rcx
0x1800a681d  jz      short loc_1800A6825
0x1800a681f  call    cs:__imp_SetEvent
0x1800a6825  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800a6828  mov     rcx, rdi; hHandle
0x1800a682b  call    cs:__imp_WaitForSingleObject
0x1800a6831  mov     rcx, rdi; hObject
0x1800a6834  call    cs:__imp_CloseHandle
0x1800a683a  mov     dword ptr [rbx+0AE8h], 0
0x1800a6844  mov     rcx, [rbx+50h]; hInternet
0x1800a6848  test    rcx, rcx
0x1800a684b  jz      short loc_1800A685B
0x1800a684d  call    cs:__imp_InternetCloseHandle
0x1800a6853  mov     qword ptr [rbx+50h], 0
0x1800a685b  mov     rcx, [rbx+48h]; hInternet
0x1800a685f  test    rcx, rcx
0x1800a6862  jz      short loc_1800A6872
0x1800a6864  call    cs:__imp_InternetCloseHandle
0x1800a686a  mov     qword ptr [rbx+48h], 0
0x1800a6872  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800a6876  call    cs:__imp_LeaveCriticalSection
0x1800a687c  mov     rdx, [rbx+0A98h]
0x1800a6883  test    rdx, rdx
0x1800a6886  jz      short loc_1800A68A6
0x1800a6888  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1800a688f  mov     rax, [rcx]
0x1800a6892  mov     rax, [rax+28h]
0x1800a6896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a689b  mov     qword ptr [rbx+0A98h], 0
0x1800a68a6  mov     rdx, [rbx+0AA0h]
0x1800a68ad  test    rdx, rdx
0x1800a68b0  jz      short loc_1800A68D0
0x1800a68b2  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1800a68b9  mov     rax, [rcx]
0x1800a68bc  mov     rax, [rax+28h]
0x1800a68c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a68c5  mov     qword ptr [rbx+0AA0h], 0
0x1800a68d0  xor     edx, edx
0x1800a68d2  mov     dword ptr [rbx+0AD0h], 1
0x1800a68dc  mov     rcx, rbx
0x1800a68df  lea     r8d, [rdx+0Bh]
0x1800a68e3  call    ?ChangeState@CAsyncHttp@@AEAAXW4ASYNCHTTP_STATE@@W4ASYNCHTTP_EVENT@@@Z; CAsyncHttp::ChangeState(ASYNCHTTP_STATE,ASYNCHTTP_EVENT)
0x1800a68e8  mov     rbx, [rsp+28h+arg_8]
0x1800a68ed  xor     eax, eax
0x1800a68ef  mov     rsi, [rsp+28h+arg_10]
0x1800a68f4  add     rsp, 20h
0x1800a68f8  pop     rdi
0x1800a68f9  retn
```
