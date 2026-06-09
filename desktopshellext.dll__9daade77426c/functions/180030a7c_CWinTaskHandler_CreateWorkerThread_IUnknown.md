# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180030a7c`
- end: `0x180030bd0`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180031780`

## callees

- `0x180030a7c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180030acd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180030acd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030b84`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030b84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030adb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030b37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030adb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030b37`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180030bb8`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180030bb8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180030b22`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180030b22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030b6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030b6d`

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
0x180030a7c  mov     [rsp+arg_0], rbx
0x180030a81  mov     [rsp+arg_8], rsi
0x180030a86  push    rdi
0x180030a87  sub     rsp, 30h
0x180030a8b  mov     rax, [rdx]
0x180030a8e  lea     rsi, [rcx+30h]
0x180030a92  mov     r9, rdx
0x180030a95  mov     rdi, rcx
0x180030a98  mov     r8, rsi
0x180030a9b  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180030aa2  mov     rcx, r9
0x180030aa5  mov     rax, [rax]
0x180030aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030aad  mov     ebx, eax
0x180030aaf  test    eax, eax
0x180030ab1  js      loc_180030B5B
0x180030ab7  cmp     dword ptr [rdi+10h], 0
0x180030abb  jz      short loc_180030AF4
0x180030abd  lea     r8, [rdi+18h]; phModule
0x180030ac1  mov     ecx, 4; dwFlags
0x180030ac6  lea     rdx, __ImageBase; lpModuleName
0x180030acd  call    cs:__imp_GetModuleHandleExW
0x180030ad3  test    eax, eax
0x180030ad5  jz      short loc_180030ADB
0x180030ad7  xor     ebx, ebx
0x180030ad9  jmp     short loc_180030AF4
0x180030adb  call    cs:__imp_GetLastError
0x180030ae1  mov     ebx, eax
0x180030ae3  test    eax, eax
0x180030ae5  jle     short loc_180030AF0
0x180030ae7  movzx   ebx, ax
0x180030aea  or      ebx, 80070000h
0x180030af0  test    ebx, ebx
0x180030af2  js      short loc_180030B5F
0x180030af4  mov     rax, [rdi]
0x180030af7  mov     rcx, rdi
0x180030afa  mov     rax, [rax+8]
0x180030afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b03  mov     r9, rdi; lpParameter
0x180030b06  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180030b0f  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x180030b16  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180030b1e  xor     edx, edx; dwStackSize
0x180030b20  xor     ecx, ecx; lpThreadAttributes
0x180030b22  call    cs:__imp_CreateThread
0x180030b28  mov     [rdi+28h], rax
0x180030b2c  inc     rax
0x180030b2f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180030b35  jnz     short loc_180030B5B
0x180030b37  call    cs:__imp_GetLastError
0x180030b3d  mov     ebx, eax
0x180030b3f  test    eax, eax
0x180030b41  jle     short loc_180030B4C
0x180030b43  movzx   ebx, ax
0x180030b46  or      ebx, 80070000h
0x180030b4c  mov     rax, [rdi]
0x180030b4f  mov     rcx, rdi
0x180030b52  mov     rax, [rax+10h]
0x180030b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b5b  test    ebx, ebx
0x180030b5d  jns     short loc_180030BAF
0x180030b5f  mov     rcx, [rdi+28h]; hObject
0x180030b63  lea     rax, [rcx-1]
0x180030b67  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180030b6b  ja      short loc_180030B7B
0x180030b6d  call    cs:__imp_CloseHandle
0x180030b73  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180030b7b  mov     rcx, [rdi+18h]; hLibModule
0x180030b7f  test    rcx, rcx
0x180030b82  jz      short loc_180030B92
0x180030b84  call    cs:__imp_FreeLibrary
0x180030b8a  mov     qword ptr [rdi+18h], 0
0x180030b92  mov     rcx, [rsi]
0x180030b95  test    rcx, rcx
0x180030b98  jz      short loc_180030BBE
0x180030b9a  mov     rax, [rcx]
0x180030b9d  mov     rax, [rax+10h]
0x180030ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ba6  mov     qword ptr [rsi], 0
0x180030bad  jmp     short loc_180030BBE
0x180030baf  lock or [rsp+38h+var_38], 0
0x180030bb4  mov     rcx, [rdi+28h]; hThread
0x180030bb8  call    cs:__imp_ResumeThread
0x180030bbe  mov     rsi, [rsp+38h+arg_8]
0x180030bc3  mov     eax, ebx
0x180030bc5  mov     rbx, [rsp+38h+arg_0]
0x180030bca  add     rsp, 30h
0x180030bce  pop     rdi
0x180030bcf  retn
```
