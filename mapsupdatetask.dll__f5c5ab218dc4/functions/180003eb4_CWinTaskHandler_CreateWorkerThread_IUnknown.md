# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180003eb4`
- end: `0x180004008`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800069a0`

## callees

- `0x180003eb4`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180003f05`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180003f05`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003fbc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003fbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f6f`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180003ff0`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180003ff0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180003f5a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180003f5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fa5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fa5`

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
    Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CWinTaskHandler::WorkerThreadProc, this, 4u, 0);
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
0x180003eb4  mov     [rsp+arg_0], rbx
0x180003eb9  mov     [rsp+arg_8], rsi
0x180003ebe  push    rdi
0x180003ebf  sub     rsp, 30h
0x180003ec3  mov     rax, [rdx]
0x180003ec6  lea     rsi, [rcx+30h]
0x180003eca  mov     r9, rdx
0x180003ecd  mov     rdi, rcx
0x180003ed0  mov     r8, rsi
0x180003ed3  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180003eda  mov     rcx, r9
0x180003edd  mov     rax, [rax]
0x180003ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ee5  mov     ebx, eax
0x180003ee7  test    eax, eax
0x180003ee9  js      loc_180003F93
0x180003eef  cmp     dword ptr [rdi+10h], 0
0x180003ef3  jz      short loc_180003F2C
0x180003ef5  lea     r8, [rdi+18h]; phModule
0x180003ef9  mov     ecx, 4; dwFlags
0x180003efe  lea     rdx, __ImageBase; lpModuleName
0x180003f05  call    cs:__imp_GetModuleHandleExW
0x180003f0b  test    eax, eax
0x180003f0d  jz      short loc_180003F13
0x180003f0f  xor     ebx, ebx
0x180003f11  jmp     short loc_180003F2C
0x180003f13  call    cs:__imp_GetLastError
0x180003f19  mov     ebx, eax
0x180003f1b  test    eax, eax
0x180003f1d  jle     short loc_180003F28
0x180003f1f  movzx   ebx, ax
0x180003f22  or      ebx, 80070000h
0x180003f28  test    ebx, ebx
0x180003f2a  js      short loc_180003F97
0x180003f2c  mov     rax, [rdi]
0x180003f2f  mov     rcx, rdi
0x180003f32  mov     rax, [rax+8]
0x180003f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f3b  mov     r9, rdi; lpParameter
0x180003f3e  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180003f47  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x180003f4e  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180003f56  xor     edx, edx; dwStackSize
0x180003f58  xor     ecx, ecx; lpThreadAttributes
0x180003f5a  call    cs:__imp_CreateThread
0x180003f60  mov     [rdi+28h], rax
0x180003f64  inc     rax
0x180003f67  test    rax, 0FFFFFFFFFFFFFFFEh
0x180003f6d  jnz     short loc_180003F93
0x180003f6f  call    cs:__imp_GetLastError
0x180003f75  mov     ebx, eax
0x180003f77  test    eax, eax
0x180003f79  jle     short loc_180003F84
0x180003f7b  movzx   ebx, ax
0x180003f7e  or      ebx, 80070000h
0x180003f84  mov     rax, [rdi]
0x180003f87  mov     rcx, rdi
0x180003f8a  mov     rax, [rax+10h]
0x180003f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f93  test    ebx, ebx
0x180003f95  jns     short loc_180003FE7
0x180003f97  mov     rcx, [rdi+28h]; hObject
0x180003f9b  lea     rax, [rcx-1]
0x180003f9f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003fa3  ja      short loc_180003FB3
0x180003fa5  call    cs:__imp_CloseHandle
0x180003fab  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180003fb3  mov     rcx, [rdi+18h]; hLibModule
0x180003fb7  test    rcx, rcx
0x180003fba  jz      short loc_180003FCA
0x180003fbc  call    cs:__imp_FreeLibrary
0x180003fc2  mov     qword ptr [rdi+18h], 0
0x180003fca  mov     rcx, [rsi]
0x180003fcd  test    rcx, rcx
0x180003fd0  jz      short loc_180003FF6
0x180003fd2  mov     rax, [rcx]
0x180003fd5  mov     rax, [rax+10h]
0x180003fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fde  mov     qword ptr [rsi], 0
0x180003fe5  jmp     short loc_180003FF6
0x180003fe7  lock or [rsp+38h+var_38], 0
0x180003fec  mov     rcx, [rdi+28h]; hThread
0x180003ff0  call    cs:__imp_ResumeThread
0x180003ff6  mov     rsi, [rsp+38h+arg_8]
0x180003ffb  mov     eax, ebx
0x180003ffd  mov     rbx, [rsp+38h+arg_0]
0x180004002  add     rsp, 30h
0x180004006  pop     rdi
0x180004007  retn
```
