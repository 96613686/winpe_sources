# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180003c74`
- end: `0x180003dc8`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800071d0`

## callees

- `0x180003c74`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003d7c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003d7c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180003cc5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180003cc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d2f`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180003db0`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180003db0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180003d1a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180003d1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d65`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::CreateWorkerThread(CWinTaskHandler *this, struct IUnknown *a2)
{
  _QWORD *v2; // rsi
  signed int v4; // ebx
  signed int LastError; // eax
  HANDLE Thread; // rax
  signed int v7; // eax
  char *v8; // rcx
  HMODULE v9; // rcx
  signed __int32 v11[8]; // [rsp+0h] [rbp-38h] BYREF

  v2 = (_QWORD *)((char *)this + 48);
  v4 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
         (char *)this + 48);
  if ( v4 >= 0 )
  {
    if ( *((_DWORD *)this + 4) )
    {
      if ( GetModuleHandleExW(4u, &_ImageBase, (HMODULE *)this + 3) )
      {
        v4 = 0;
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( v4 < 0 )
          goto LABEL_13;
      }
    }
    (*(void (__fastcall **)(CWinTaskHandler *))(*(_QWORD *)this + 8LL))(this);
    Thread = CreateThread(0, 0, CWinTaskHandler::WorkerThreadProc, this, 4u, 0);
    *((_QWORD *)this + 5) = Thread;
    if ( (((unsigned __int64)Thread + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v7 = GetLastError();
      v4 = v7;
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
      (*(void (__fastcall **)(CWinTaskHandler *))(*(_QWORD *)this + 16LL))(this);
    }
  }
  if ( v4 >= 0 )
  {
    _InterlockedOr(v11, 0);
    ResumeThread(*((HANDLE *)this + 5));
    return (unsigned int)v4;
  }
LABEL_13:
  v8 = (char *)*((_QWORD *)this + 5);
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v8);
    *((_QWORD *)this + 5) = -1;
  }
  v9 = (HMODULE)*((_QWORD *)this + 3);
  if ( v9 )
  {
    FreeLibrary(v9);
    *((_QWORD *)this + 3) = 0;
  }
  if ( *v2 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
    *v2 = 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180003c74  mov     [rsp+arg_0], rbx
0x180003c79  mov     [rsp+arg_8], rsi
0x180003c7e  push    rdi
0x180003c7f  sub     rsp, 30h
0x180003c83  mov     rax, [rdx]
0x180003c86  lea     rsi, [rcx+30h]
0x180003c8a  mov     r9, rdx
0x180003c8d  mov     rdi, rcx
0x180003c90  mov     r8, rsi
0x180003c93  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180003c9a  mov     rcx, r9
0x180003c9d  mov     rax, [rax]
0x180003ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ca5  mov     ebx, eax
0x180003ca7  test    eax, eax
0x180003ca9  js      loc_180003D53
0x180003caf  cmp     dword ptr [rdi+10h], 0
0x180003cb3  jz      short loc_180003CEC
0x180003cb5  lea     r8, [rdi+18h]; phModule
0x180003cb9  mov     ecx, 4; dwFlags
0x180003cbe  lea     rdx, __ImageBase; lpModuleName
0x180003cc5  call    cs:__imp_GetModuleHandleExW
0x180003ccb  test    eax, eax
0x180003ccd  jz      short loc_180003CD3
0x180003ccf  xor     ebx, ebx
0x180003cd1  jmp     short loc_180003CEC
0x180003cd3  call    cs:__imp_GetLastError
0x180003cd9  mov     ebx, eax
0x180003cdb  test    eax, eax
0x180003cdd  jle     short loc_180003CE8
0x180003cdf  movzx   ebx, ax
0x180003ce2  or      ebx, 80070000h
0x180003ce8  test    ebx, ebx
0x180003cea  js      short loc_180003D57
0x180003cec  mov     rax, [rdi]
0x180003cef  mov     rcx, rdi
0x180003cf2  mov     rax, [rax+8]
0x180003cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cfb  mov     r9, rdi; lpParameter
0x180003cfe  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180003d07  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x180003d0e  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180003d16  xor     edx, edx; dwStackSize
0x180003d18  xor     ecx, ecx; lpThreadAttributes
0x180003d1a  call    cs:__imp_CreateThread
0x180003d20  mov     [rdi+28h], rax
0x180003d24  inc     rax
0x180003d27  test    rax, 0FFFFFFFFFFFFFFFEh
0x180003d2d  jnz     short loc_180003D53
0x180003d2f  call    cs:__imp_GetLastError
0x180003d35  mov     ebx, eax
0x180003d37  test    eax, eax
0x180003d39  jle     short loc_180003D44
0x180003d3b  movzx   ebx, ax
0x180003d3e  or      ebx, 80070000h
0x180003d44  mov     rax, [rdi]
0x180003d47  mov     rcx, rdi
0x180003d4a  mov     rax, [rax+10h]
0x180003d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d53  test    ebx, ebx
0x180003d55  jns     short loc_180003DA7
0x180003d57  mov     rcx, [rdi+28h]; hObject
0x180003d5b  lea     rax, [rcx-1]
0x180003d5f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003d63  ja      short loc_180003D73
0x180003d65  call    cs:__imp_CloseHandle
0x180003d6b  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180003d73  mov     rcx, [rdi+18h]; hLibModule
0x180003d77  test    rcx, rcx
0x180003d7a  jz      short loc_180003D8A
0x180003d7c  call    cs:__imp_FreeLibrary
0x180003d82  mov     qword ptr [rdi+18h], 0
0x180003d8a  mov     rcx, [rsi]
0x180003d8d  test    rcx, rcx
0x180003d90  jz      short loc_180003DB6
0x180003d92  mov     rax, [rcx]
0x180003d95  mov     rax, [rax+10h]
0x180003d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d9e  mov     qword ptr [rsi], 0
0x180003da5  jmp     short loc_180003DB6
0x180003da7  lock or [rsp+38h+var_38], 0
0x180003dac  mov     rcx, [rdi+28h]; hThread
0x180003db0  call    cs:__imp_ResumeThread
0x180003db6  mov     rsi, [rsp+38h+arg_8]
0x180003dbb  mov     eax, ebx
0x180003dbd  mov     rbx, [rsp+38h+arg_0]
0x180003dc2  add     rsp, 30h
0x180003dc6  pop     rdi
0x180003dc7  retn
```
