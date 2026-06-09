# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180002db8`
- end: `0x180002f0c`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800030d0`

## callees

- `0x180002db8`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e73`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180002ef4`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180002ef4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180002e5e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180002e5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002ea9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002ea9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180002e09`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180002e09`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002ec0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002ec0`

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
0x180002db8  mov     [rsp+arg_0], rbx
0x180002dbd  mov     [rsp+arg_8], rsi
0x180002dc2  push    rdi
0x180002dc3  sub     rsp, 30h
0x180002dc7  mov     rax, [rdx]
0x180002dca  lea     rsi, [rcx+30h]
0x180002dce  mov     r9, rdx
0x180002dd1  mov     rdi, rcx
0x180002dd4  mov     r8, rsi
0x180002dd7  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180002dde  mov     rcx, r9
0x180002de1  mov     rax, [rax]
0x180002de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002de9  mov     ebx, eax
0x180002deb  test    eax, eax
0x180002ded  js      loc_180002E97
0x180002df3  cmp     dword ptr [rdi+10h], 0
0x180002df7  jz      short loc_180002E30
0x180002df9  lea     r8, [rdi+18h]; phModule
0x180002dfd  mov     ecx, 4; dwFlags
0x180002e02  lea     rdx, cs:180000000h; lpModuleName
0x180002e09  call    cs:__imp_GetModuleHandleExW
0x180002e0f  test    eax, eax
0x180002e11  jz      short loc_180002E17
0x180002e13  xor     ebx, ebx
0x180002e15  jmp     short loc_180002E30
0x180002e17  call    cs:__imp_GetLastError
0x180002e1d  mov     ebx, eax
0x180002e1f  test    eax, eax
0x180002e21  jle     short loc_180002E2C
0x180002e23  movzx   ebx, ax
0x180002e26  or      ebx, 80070000h
0x180002e2c  test    ebx, ebx
0x180002e2e  js      short loc_180002E9B
0x180002e30  mov     rax, [rdi]
0x180002e33  mov     rcx, rdi
0x180002e36  mov     rax, [rax+8]
0x180002e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e3f  mov     r9, rdi; lpParameter
0x180002e42  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180002e4b  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x180002e52  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180002e5a  xor     edx, edx; dwStackSize
0x180002e5c  xor     ecx, ecx; lpThreadAttributes
0x180002e5e  call    cs:__imp_CreateThread
0x180002e64  mov     [rdi+28h], rax
0x180002e68  inc     rax
0x180002e6b  test    rax, 0FFFFFFFFFFFFFFFEh
0x180002e71  jnz     short loc_180002E97
0x180002e73  call    cs:__imp_GetLastError
0x180002e79  mov     ebx, eax
0x180002e7b  test    eax, eax
0x180002e7d  jle     short loc_180002E88
0x180002e7f  movzx   ebx, ax
0x180002e82  or      ebx, 80070000h
0x180002e88  mov     rax, [rdi]
0x180002e8b  mov     rcx, rdi
0x180002e8e  mov     rax, [rax+10h]
0x180002e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e97  test    ebx, ebx
0x180002e99  jns     short loc_180002EEB
0x180002e9b  mov     rcx, [rdi+28h]; hObject
0x180002e9f  lea     rax, [rcx-1]
0x180002ea3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002ea7  ja      short loc_180002EB7
0x180002ea9  call    cs:__imp_CloseHandle
0x180002eaf  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180002eb7  mov     rcx, [rdi+18h]; hLibModule
0x180002ebb  test    rcx, rcx
0x180002ebe  jz      short loc_180002ECE
0x180002ec0  call    cs:__imp_FreeLibrary
0x180002ec6  mov     qword ptr [rdi+18h], 0
0x180002ece  mov     rcx, [rsi]
0x180002ed1  test    rcx, rcx
0x180002ed4  jz      short loc_180002EFA
0x180002ed6  mov     rax, [rcx]
0x180002ed9  mov     rax, [rax+10h]
0x180002edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ee2  mov     qword ptr [rsi], 0
0x180002ee9  jmp     short loc_180002EFA
0x180002eeb  lock or [rsp+38h+var_38], 0
0x180002ef0  mov     rcx, [rdi+28h]; hThread
0x180002ef4  call    cs:__imp_ResumeThread
0x180002efa  mov     rsi, [rsp+38h+arg_8]
0x180002eff  mov     eax, ebx
0x180002f01  mov     rbx, [rsp+38h+arg_0]
0x180002f06  add     rsp, 30h
0x180002f0a  pop     rdi
0x180002f0b  retn
```
