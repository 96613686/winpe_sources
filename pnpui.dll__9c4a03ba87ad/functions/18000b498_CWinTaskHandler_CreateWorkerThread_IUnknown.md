# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x18000b498`
- end: `0x18000b5ec`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000c260`

## callees

- `0x18000b498`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b4f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b553`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b4f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b553`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000b4e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000b4e9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b5a0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b5a0`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000b5d4`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000b5d4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000b53e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000b53e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b589`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b589`

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
0x18000b498  mov     [rsp+arg_0], rbx
0x18000b49d  mov     [rsp+arg_8], rsi
0x18000b4a2  push    rdi
0x18000b4a3  sub     rsp, 30h
0x18000b4a7  mov     rax, [rdx]
0x18000b4aa  lea     rsi, [rcx+30h]
0x18000b4ae  mov     r9, rdx
0x18000b4b1  mov     rdi, rcx
0x18000b4b4  mov     r8, rsi
0x18000b4b7  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000b4be  mov     rcx, r9
0x18000b4c1  mov     rax, [rax]
0x18000b4c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4c9  mov     ebx, eax
0x18000b4cb  test    eax, eax
0x18000b4cd  js      loc_18000B577
0x18000b4d3  cmp     dword ptr [rdi+10h], 0
0x18000b4d7  jz      short loc_18000B510
0x18000b4d9  lea     r8, [rdi+18h]; phModule
0x18000b4dd  mov     ecx, 4; dwFlags
0x18000b4e2  lea     rdx, __ImageBase; lpModuleName
0x18000b4e9  call    cs:__imp_GetModuleHandleExW
0x18000b4ef  test    eax, eax
0x18000b4f1  jz      short loc_18000B4F7
0x18000b4f3  xor     ebx, ebx
0x18000b4f5  jmp     short loc_18000B510
0x18000b4f7  call    cs:__imp_GetLastError
0x18000b4fd  mov     ebx, eax
0x18000b4ff  test    eax, eax
0x18000b501  jle     short loc_18000B50C
0x18000b503  movzx   ebx, ax
0x18000b506  or      ebx, 80070000h
0x18000b50c  test    ebx, ebx
0x18000b50e  js      short loc_18000B57B
0x18000b510  mov     rax, [rdi]
0x18000b513  mov     rcx, rdi
0x18000b516  mov     rax, [rax+8]
0x18000b51a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b51f  mov     r9, rdi; lpParameter
0x18000b522  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18000b52b  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x18000b532  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x18000b53a  xor     edx, edx; dwStackSize
0x18000b53c  xor     ecx, ecx; lpThreadAttributes
0x18000b53e  call    cs:__imp_CreateThread
0x18000b544  mov     [rdi+28h], rax
0x18000b548  inc     rax
0x18000b54b  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000b551  jnz     short loc_18000B577
0x18000b553  call    cs:__imp_GetLastError
0x18000b559  mov     ebx, eax
0x18000b55b  test    eax, eax
0x18000b55d  jle     short loc_18000B568
0x18000b55f  movzx   ebx, ax
0x18000b562  or      ebx, 80070000h
0x18000b568  mov     rax, [rdi]
0x18000b56b  mov     rcx, rdi
0x18000b56e  mov     rax, [rax+10h]
0x18000b572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b577  test    ebx, ebx
0x18000b579  jns     short loc_18000B5CB
0x18000b57b  mov     rcx, [rdi+28h]; hObject
0x18000b57f  lea     rax, [rcx-1]
0x18000b583  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b587  ja      short loc_18000B597
0x18000b589  call    cs:__imp_CloseHandle
0x18000b58f  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x18000b597  mov     rcx, [rdi+18h]; hLibModule
0x18000b59b  test    rcx, rcx
0x18000b59e  jz      short loc_18000B5AE
0x18000b5a0  call    cs:__imp_FreeLibrary
0x18000b5a6  mov     qword ptr [rdi+18h], 0
0x18000b5ae  mov     rcx, [rsi]
0x18000b5b1  test    rcx, rcx
0x18000b5b4  jz      short loc_18000B5DA
0x18000b5b6  mov     rax, [rcx]
0x18000b5b9  mov     rax, [rax+10h]
0x18000b5bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5c2  mov     qword ptr [rsi], 0
0x18000b5c9  jmp     short loc_18000B5DA
0x18000b5cb  lock or [rsp+38h+var_38], 0
0x18000b5d0  mov     rcx, [rdi+28h]; hThread
0x18000b5d4  call    cs:__imp_ResumeThread
0x18000b5da  mov     rsi, [rsp+38h+arg_8]
0x18000b5df  mov     eax, ebx
0x18000b5e1  mov     rbx, [rsp+38h+arg_0]
0x18000b5e6  add     rsp, 30h
0x18000b5ea  pop     rdi
0x18000b5eb  retn
```
