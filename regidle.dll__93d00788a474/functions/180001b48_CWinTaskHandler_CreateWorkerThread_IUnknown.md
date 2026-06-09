# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180001b48`
- end: `0x180001c9c`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180002040`

## callees

- `0x180001b48`
- `0x180003010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001c39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001c39`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180001b99`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180001b99`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001c50`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001c50`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180001bee`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180001bee`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180001c84`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180001c84`

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
      if ( GetModuleHandleExW(4u, (LPCWSTR)0x180000000LL, (HMODULE *)this + 3) )
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
0x180001b48  mov     [rsp+arg_0], rbx
0x180001b4d  mov     [rsp+arg_8], rsi
0x180001b52  push    rdi
0x180001b53  sub     rsp, 30h
0x180001b57  mov     rax, [rdx]
0x180001b5a  lea     rsi, [rcx+30h]
0x180001b5e  mov     r9, rdx
0x180001b61  mov     rdi, rcx
0x180001b64  mov     r8, rsi
0x180001b67  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180001b6e  mov     rcx, r9
0x180001b71  mov     rax, [rax]
0x180001b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b79  mov     ebx, eax
0x180001b7b  test    eax, eax
0x180001b7d  js      loc_180001C27
0x180001b83  cmp     dword ptr [rdi+10h], 0
0x180001b87  jz      short loc_180001BC0
0x180001b89  lea     r8, [rdi+18h]; phModule
0x180001b8d  mov     ecx, 4; dwFlags
0x180001b92  lea     rdx, cs:180000000h; lpModuleName
0x180001b99  call    cs:__imp_GetModuleHandleExW
0x180001b9f  test    eax, eax
0x180001ba1  jz      short loc_180001BA7
0x180001ba3  xor     ebx, ebx
0x180001ba5  jmp     short loc_180001BC0
0x180001ba7  call    cs:__imp_GetLastError
0x180001bad  mov     ebx, eax
0x180001baf  test    eax, eax
0x180001bb1  jle     short loc_180001BBC
0x180001bb3  movzx   ebx, ax
0x180001bb6  or      ebx, 80070000h
0x180001bbc  test    ebx, ebx
0x180001bbe  js      short loc_180001C2B
0x180001bc0  mov     rax, [rdi]
0x180001bc3  mov     rcx, rdi
0x180001bc6  mov     rax, [rax+8]
0x180001bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bcf  mov     r9, rdi; lpParameter
0x180001bd2  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180001bdb  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x180001be2  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180001bea  xor     edx, edx; dwStackSize
0x180001bec  xor     ecx, ecx; lpThreadAttributes
0x180001bee  call    cs:__imp_CreateThread
0x180001bf4  mov     [rdi+28h], rax
0x180001bf8  inc     rax
0x180001bfb  test    rax, 0FFFFFFFFFFFFFFFEh
0x180001c01  jnz     short loc_180001C27
0x180001c03  call    cs:__imp_GetLastError
0x180001c09  mov     ebx, eax
0x180001c0b  test    eax, eax
0x180001c0d  jle     short loc_180001C18
0x180001c0f  movzx   ebx, ax
0x180001c12  or      ebx, 80070000h
0x180001c18  mov     rax, [rdi]
0x180001c1b  mov     rcx, rdi
0x180001c1e  mov     rax, [rax+10h]
0x180001c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c27  test    ebx, ebx
0x180001c29  jns     short loc_180001C7B
0x180001c2b  mov     rcx, [rdi+28h]; hObject
0x180001c2f  lea     rax, [rcx-1]
0x180001c33  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180001c37  ja      short loc_180001C47
0x180001c39  call    cs:__imp_CloseHandle
0x180001c3f  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180001c47  mov     rcx, [rdi+18h]; hLibModule
0x180001c4b  test    rcx, rcx
0x180001c4e  jz      short loc_180001C5E
0x180001c50  call    cs:__imp_FreeLibrary
0x180001c56  mov     qword ptr [rdi+18h], 0
0x180001c5e  mov     rcx, [rsi]
0x180001c61  test    rcx, rcx
0x180001c64  jz      short loc_180001C8A
0x180001c66  mov     rax, [rcx]
0x180001c69  mov     rax, [rax+10h]
0x180001c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c72  mov     qword ptr [rsi], 0
0x180001c79  jmp     short loc_180001C8A
0x180001c7b  lock or [rsp+38h+var_38], 0
0x180001c80  mov     rcx, [rdi+28h]; hThread
0x180001c84  call    cs:__imp_ResumeThread
0x180001c8a  mov     rsi, [rsp+38h+arg_8]
0x180001c8f  mov     eax, ebx
0x180001c91  mov     rbx, [rsp+38h+arg_0]
0x180001c96  add     rsp, 30h
0x180001c9a  pop     rdi
0x180001c9b  retn
```
