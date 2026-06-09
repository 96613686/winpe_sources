# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180003a30`
- end: `0x180003b84`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180003c80`

## callees

- `0x180003a30`
- `0x18000a010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003a8f`
- `KERNEL32!GetLastError` at `0x180003aeb`
- `KERNEL32!GetLastError` at `0x180003a8f`
- `KERNEL32!GetLastError` at `0x180003aeb`
- `KERNEL32!GetModuleHandleExW` at `0x180003a81`
- `KERNEL32!GetModuleHandleExW` at `0x180003a81`
- `KERNEL32!ResumeThread` at `0x180003b6c`
- `KERNEL32!ResumeThread` at `0x180003b6c`
- `KERNEL32!CloseHandle` at `0x180003b21`
- `KERNEL32!CloseHandle` at `0x180003b21`
- `KERNEL32!CreateThread` at `0x180003ad6`
- `KERNEL32!CreateThread` at `0x180003ad6`
- `KERNEL32!FreeLibrary` at `0x180003b38`
- `KERNEL32!FreeLibrary` at `0x180003b38`

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
0x180003a30  mov     [rsp+arg_0], rbx
0x180003a35  mov     [rsp+arg_8], rsi
0x180003a3a  push    rdi
0x180003a3b  sub     rsp, 30h
0x180003a3f  mov     rax, [rdx]
0x180003a42  lea     rsi, [rcx+30h]
0x180003a46  mov     r9, rdx
0x180003a49  mov     rdi, rcx
0x180003a4c  mov     r8, rsi
0x180003a4f  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180003a56  mov     rcx, r9
0x180003a59  mov     rax, [rax]
0x180003a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a61  mov     ebx, eax
0x180003a63  test    eax, eax
0x180003a65  js      loc_180003B0F
0x180003a6b  cmp     dword ptr [rdi+10h], 0
0x180003a6f  jz      short loc_180003AA8
0x180003a71  lea     r8, [rdi+18h]; phModule
0x180003a75  mov     ecx, 4; dwFlags
0x180003a7a  lea     rdx, cs:180000000h; lpModuleName
0x180003a81  call    cs:__imp_GetModuleHandleExW
0x180003a87  test    eax, eax
0x180003a89  jz      short loc_180003A8F
0x180003a8b  xor     ebx, ebx
0x180003a8d  jmp     short loc_180003AA8
0x180003a8f  call    cs:__imp_GetLastError
0x180003a95  mov     ebx, eax
0x180003a97  test    eax, eax
0x180003a99  jle     short loc_180003AA4
0x180003a9b  movzx   ebx, ax
0x180003a9e  or      ebx, 80070000h
0x180003aa4  test    ebx, ebx
0x180003aa6  js      short loc_180003B13
0x180003aa8  mov     rax, [rdi]
0x180003aab  mov     rcx, rdi
0x180003aae  mov     rax, [rax+8]
0x180003ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ab7  mov     r9, rdi; lpParameter
0x180003aba  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180003ac3  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x180003aca  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180003ad2  xor     edx, edx; dwStackSize
0x180003ad4  xor     ecx, ecx; lpThreadAttributes
0x180003ad6  call    cs:__imp_CreateThread
0x180003adc  mov     [rdi+28h], rax
0x180003ae0  inc     rax
0x180003ae3  test    rax, 0FFFFFFFFFFFFFFFEh
0x180003ae9  jnz     short loc_180003B0F
0x180003aeb  call    cs:__imp_GetLastError
0x180003af1  mov     ebx, eax
0x180003af3  test    eax, eax
0x180003af5  jle     short loc_180003B00
0x180003af7  movzx   ebx, ax
0x180003afa  or      ebx, 80070000h
0x180003b00  mov     rax, [rdi]
0x180003b03  mov     rcx, rdi
0x180003b06  mov     rax, [rax+10h]
0x180003b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b0f  test    ebx, ebx
0x180003b11  jns     short loc_180003B63
0x180003b13  mov     rcx, [rdi+28h]; hObject
0x180003b17  lea     rax, [rcx-1]
0x180003b1b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003b1f  ja      short loc_180003B2F
0x180003b21  call    cs:__imp_CloseHandle
0x180003b27  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180003b2f  mov     rcx, [rdi+18h]; hLibModule
0x180003b33  test    rcx, rcx
0x180003b36  jz      short loc_180003B46
0x180003b38  call    cs:__imp_FreeLibrary
0x180003b3e  mov     qword ptr [rdi+18h], 0
0x180003b46  mov     rcx, [rsi]
0x180003b49  test    rcx, rcx
0x180003b4c  jz      short loc_180003B72
0x180003b4e  mov     rax, [rcx]
0x180003b51  mov     rax, [rax+10h]
0x180003b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b5a  mov     qword ptr [rsi], 0
0x180003b61  jmp     short loc_180003B72
0x180003b63  lock or [rsp+38h+var_38], 0
0x180003b68  mov     rcx, [rdi+28h]; hThread
0x180003b6c  call    cs:__imp_ResumeThread
0x180003b72  mov     rsi, [rsp+38h+arg_8]
0x180003b77  mov     eax, ebx
0x180003b79  mov     rbx, [rsp+38h+arg_0]
0x180003b7e  add     rsp, 30h
0x180003b82  pop     rdi
0x180003b83  retn
```
