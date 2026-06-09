# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180001c94`
- end: `0x180001de8`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180002ad0`

## callees

- `0x180001c94`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180001ce5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180001ce5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001d9c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001d9c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180001d3a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180001d3a`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180001dd0`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180001dd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001cf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001cf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001d85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001d85`

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
0x180001c94  mov     [rsp+arg_0], rbx
0x180001c99  mov     [rsp+arg_8], rsi
0x180001c9e  push    rdi
0x180001c9f  sub     rsp, 30h
0x180001ca3  mov     rax, [rdx]
0x180001ca6  lea     rsi, [rcx+30h]
0x180001caa  mov     r9, rdx
0x180001cad  mov     rdi, rcx
0x180001cb0  mov     r8, rsi
0x180001cb3  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180001cba  mov     rcx, r9
0x180001cbd  mov     rax, [rax]
0x180001cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cc5  mov     ebx, eax
0x180001cc7  test    eax, eax
0x180001cc9  js      loc_180001D73
0x180001ccf  cmp     dword ptr [rdi+10h], 0
0x180001cd3  jz      short loc_180001D0C
0x180001cd5  lea     r8, [rdi+18h]; phModule
0x180001cd9  mov     ecx, 4; dwFlags
0x180001cde  lea     rdx, __ImageBase; lpModuleName
0x180001ce5  call    cs:__imp_GetModuleHandleExW
0x180001ceb  test    eax, eax
0x180001ced  jz      short loc_180001CF3
0x180001cef  xor     ebx, ebx
0x180001cf1  jmp     short loc_180001D0C
0x180001cf3  call    cs:__imp_GetLastError
0x180001cf9  mov     ebx, eax
0x180001cfb  test    eax, eax
0x180001cfd  jle     short loc_180001D08
0x180001cff  movzx   ebx, ax
0x180001d02  or      ebx, 80070000h
0x180001d08  test    ebx, ebx
0x180001d0a  js      short loc_180001D77
0x180001d0c  mov     rax, [rdi]
0x180001d0f  mov     rcx, rdi
0x180001d12  mov     rax, [rax+8]
0x180001d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d1b  mov     r9, rdi; lpParameter
0x180001d1e  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180001d27  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x180001d2e  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180001d36  xor     edx, edx; dwStackSize
0x180001d38  xor     ecx, ecx; lpThreadAttributes
0x180001d3a  call    cs:__imp_CreateThread
0x180001d40  mov     [rdi+28h], rax
0x180001d44  inc     rax
0x180001d47  test    rax, 0FFFFFFFFFFFFFFFEh
0x180001d4d  jnz     short loc_180001D73
0x180001d4f  call    cs:__imp_GetLastError
0x180001d55  mov     ebx, eax
0x180001d57  test    eax, eax
0x180001d59  jle     short loc_180001D64
0x180001d5b  movzx   ebx, ax
0x180001d5e  or      ebx, 80070000h
0x180001d64  mov     rax, [rdi]
0x180001d67  mov     rcx, rdi
0x180001d6a  mov     rax, [rax+10h]
0x180001d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d73  test    ebx, ebx
0x180001d75  jns     short loc_180001DC7
0x180001d77  mov     rcx, [rdi+28h]; hObject
0x180001d7b  lea     rax, [rcx-1]
0x180001d7f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180001d83  ja      short loc_180001D93
0x180001d85  call    cs:__imp_CloseHandle
0x180001d8b  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180001d93  mov     rcx, [rdi+18h]; hLibModule
0x180001d97  test    rcx, rcx
0x180001d9a  jz      short loc_180001DAA
0x180001d9c  call    cs:__imp_FreeLibrary
0x180001da2  mov     qword ptr [rdi+18h], 0
0x180001daa  mov     rcx, [rsi]
0x180001dad  test    rcx, rcx
0x180001db0  jz      short loc_180001DD6
0x180001db2  mov     rax, [rcx]
0x180001db5  mov     rax, [rax+10h]
0x180001db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dbe  mov     qword ptr [rsi], 0
0x180001dc5  jmp     short loc_180001DD6
0x180001dc7  lock or [rsp+38h+var_38], 0
0x180001dcc  mov     rcx, [rdi+28h]; hThread
0x180001dd0  call    cs:__imp_ResumeThread
0x180001dd6  mov     rsi, [rsp+38h+arg_8]
0x180001ddb  mov     eax, ebx
0x180001ddd  mov     rbx, [rsp+38h+arg_0]
0x180001de2  add     rsp, 30h
0x180001de6  pop     rdi
0x180001de7  retn
```
