# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x18000b348`
- end: `0x18000b49c`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18000b2f0`

## callees

- `0x18000b348`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b450`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b450`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000b399`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000b399`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b403`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b403`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000b484`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000b484`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000b3ee`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000b3ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b439`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b439`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
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
0x18000b348  mov     [rsp+arg_0], rbx
0x18000b34d  mov     [rsp+arg_8], rsi
0x18000b352  push    rdi
0x18000b353  sub     rsp, 30h
0x18000b357  mov     rax, [rdx]
0x18000b35a  lea     rsi, [rcx+30h]
0x18000b35e  mov     r9, rdx
0x18000b361  mov     rdi, rcx
0x18000b364  mov     r8, rsi
0x18000b367  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000b36e  mov     rcx, r9
0x18000b371  mov     rax, [rax]
0x18000b374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b379  mov     ebx, eax
0x18000b37b  test    eax, eax
0x18000b37d  js      loc_18000B427
0x18000b383  cmp     dword ptr [rdi+10h], 0
0x18000b387  jz      short loc_18000B3C0
0x18000b389  lea     r8, [rdi+18h]; phModule
0x18000b38d  mov     ecx, 4; dwFlags
0x18000b392  lea     rdx, __ImageBase; lpModuleName
0x18000b399  call    cs:__imp_GetModuleHandleExW
0x18000b39f  test    eax, eax
0x18000b3a1  jz      short loc_18000B3A7
0x18000b3a3  xor     ebx, ebx
0x18000b3a5  jmp     short loc_18000B3C0
0x18000b3a7  call    cs:__imp_GetLastError
0x18000b3ad  mov     ebx, eax
0x18000b3af  test    eax, eax
0x18000b3b1  jle     short loc_18000B3BC
0x18000b3b3  movzx   ebx, ax
0x18000b3b6  or      ebx, 80070000h
0x18000b3bc  test    ebx, ebx
0x18000b3be  js      short loc_18000B42B
0x18000b3c0  mov     rax, [rdi]
0x18000b3c3  mov     rcx, rdi
0x18000b3c6  mov     rax, [rax+8]
0x18000b3ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3cf  mov     r9, rdi; lpParameter
0x18000b3d2  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18000b3db  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x18000b3e2  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x18000b3ea  xor     edx, edx; dwStackSize
0x18000b3ec  xor     ecx, ecx; lpThreadAttributes
0x18000b3ee  call    cs:__imp_CreateThread
0x18000b3f4  mov     [rdi+28h], rax
0x18000b3f8  inc     rax
0x18000b3fb  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000b401  jnz     short loc_18000B427
0x18000b403  call    cs:__imp_GetLastError
0x18000b409  mov     ebx, eax
0x18000b40b  test    eax, eax
0x18000b40d  jle     short loc_18000B418
0x18000b40f  movzx   ebx, ax
0x18000b412  or      ebx, 80070000h
0x18000b418  mov     rax, [rdi]
0x18000b41b  mov     rcx, rdi
0x18000b41e  mov     rax, [rax+10h]
0x18000b422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b427  test    ebx, ebx
0x18000b429  jns     short loc_18000B47B
0x18000b42b  mov     rcx, [rdi+28h]; hObject
0x18000b42f  lea     rax, [rcx-1]
0x18000b433  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b437  ja      short loc_18000B447
0x18000b439  call    cs:__imp_CloseHandle
0x18000b43f  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x18000b447  mov     rcx, [rdi+18h]; hLibModule
0x18000b44b  test    rcx, rcx
0x18000b44e  jz      short loc_18000B45E
0x18000b450  call    cs:__imp_FreeLibrary
0x18000b456  mov     qword ptr [rdi+18h], 0
0x18000b45e  mov     rcx, [rsi]
0x18000b461  test    rcx, rcx
0x18000b464  jz      short loc_18000B48A
0x18000b466  mov     rax, [rcx]
0x18000b469  mov     rax, [rax+10h]
0x18000b46d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b472  mov     qword ptr [rsi], 0
0x18000b479  jmp     short loc_18000B48A
0x18000b47b  lock or [rsp+38h+var_38], 0
0x18000b480  mov     rcx, [rdi+28h]; hThread
0x18000b484  call    cs:__imp_ResumeThread
0x18000b48a  mov     rsi, [rsp+38h+arg_8]
0x18000b48f  mov     eax, ebx
0x18000b491  mov     rbx, [rsp+38h+arg_0]
0x18000b496  add     rsp, 30h
0x18000b49a  pop     rdi
0x18000b49b  retn
```
