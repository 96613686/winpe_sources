# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x18000c6b4`
- end: `0x18000c808`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000edb0`

## callees

- `0x18000c6b4`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c7bc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c7bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000c705`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000c705`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c713`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c76f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c713`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c76f`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000c7f0`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000c7f0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c75a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c75a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c7a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c7a5`

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
0x18000c6b4  mov     [rsp+arg_0], rbx
0x18000c6b9  mov     [rsp+arg_8], rsi
0x18000c6be  push    rdi
0x18000c6bf  sub     rsp, 30h
0x18000c6c3  mov     rax, [rdx]
0x18000c6c6  lea     rsi, [rcx+30h]
0x18000c6ca  mov     r9, rdx
0x18000c6cd  mov     rdi, rcx
0x18000c6d0  mov     r8, rsi
0x18000c6d3  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000c6da  mov     rcx, r9
0x18000c6dd  mov     rax, [rax]
0x18000c6e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6e5  mov     ebx, eax
0x18000c6e7  test    eax, eax
0x18000c6e9  js      loc_18000C793
0x18000c6ef  cmp     dword ptr [rdi+10h], 0
0x18000c6f3  jz      short loc_18000C72C
0x18000c6f5  lea     r8, [rdi+18h]; phModule
0x18000c6f9  mov     ecx, 4; dwFlags
0x18000c6fe  lea     rdx, __ImageBase; lpModuleName
0x18000c705  call    cs:__imp_GetModuleHandleExW
0x18000c70b  test    eax, eax
0x18000c70d  jz      short loc_18000C713
0x18000c70f  xor     ebx, ebx
0x18000c711  jmp     short loc_18000C72C
0x18000c713  call    cs:__imp_GetLastError
0x18000c719  mov     ebx, eax
0x18000c71b  test    eax, eax
0x18000c71d  jle     short loc_18000C728
0x18000c71f  movzx   ebx, ax
0x18000c722  or      ebx, 80070000h
0x18000c728  test    ebx, ebx
0x18000c72a  js      short loc_18000C797
0x18000c72c  mov     rax, [rdi]
0x18000c72f  mov     rcx, rdi
0x18000c732  mov     rax, [rax+8]
0x18000c736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c73b  mov     r9, rdi; lpParameter
0x18000c73e  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18000c747  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x18000c74e  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x18000c756  xor     edx, edx; dwStackSize
0x18000c758  xor     ecx, ecx; lpThreadAttributes
0x18000c75a  call    cs:__imp_CreateThread
0x18000c760  mov     [rdi+28h], rax
0x18000c764  inc     rax
0x18000c767  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000c76d  jnz     short loc_18000C793
0x18000c76f  call    cs:__imp_GetLastError
0x18000c775  mov     ebx, eax
0x18000c777  test    eax, eax
0x18000c779  jle     short loc_18000C784
0x18000c77b  movzx   ebx, ax
0x18000c77e  or      ebx, 80070000h
0x18000c784  mov     rax, [rdi]
0x18000c787  mov     rcx, rdi
0x18000c78a  mov     rax, [rax+10h]
0x18000c78e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c793  test    ebx, ebx
0x18000c795  jns     short loc_18000C7E7
0x18000c797  mov     rcx, [rdi+28h]; hObject
0x18000c79b  lea     rax, [rcx-1]
0x18000c79f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c7a3  ja      short loc_18000C7B3
0x18000c7a5  call    cs:__imp_CloseHandle
0x18000c7ab  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x18000c7b3  mov     rcx, [rdi+18h]; hLibModule
0x18000c7b7  test    rcx, rcx
0x18000c7ba  jz      short loc_18000C7CA
0x18000c7bc  call    cs:__imp_FreeLibrary
0x18000c7c2  mov     qword ptr [rdi+18h], 0
0x18000c7ca  mov     rcx, [rsi]
0x18000c7cd  test    rcx, rcx
0x18000c7d0  jz      short loc_18000C7F6
0x18000c7d2  mov     rax, [rcx]
0x18000c7d5  mov     rax, [rax+10h]
0x18000c7d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7de  mov     qword ptr [rsi], 0
0x18000c7e5  jmp     short loc_18000C7F6
0x18000c7e7  lock or [rsp+38h+var_38], 0
0x18000c7ec  mov     rcx, [rdi+28h]; hThread
0x18000c7f0  call    cs:__imp_ResumeThread
0x18000c7f6  mov     rsi, [rsp+38h+arg_8]
0x18000c7fb  mov     eax, ebx
0x18000c7fd  mov     rbx, [rsp+38h+arg_0]
0x18000c802  add     rsp, 30h
0x18000c806  pop     rdi
0x18000c807  retn
```
