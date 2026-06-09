# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180001b50`
- end: `0x180001ca4`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800023b0`

## callees

- `0x180001b50`
- `0x180003010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180001baf`
- `KERNEL32!GetLastError` at `0x180001c0b`
- `KERNEL32!GetLastError` at `0x180001baf`
- `KERNEL32!GetLastError` at `0x180001c0b`
- `KERNEL32!ResumeThread` at `0x180001c8c`
- `KERNEL32!ResumeThread` at `0x180001c8c`
- `KERNEL32!CloseHandle` at `0x180001c41`
- `KERNEL32!CloseHandle` at `0x180001c41`
- `KERNEL32!CreateThread` at `0x180001bf6`
- `KERNEL32!CreateThread` at `0x180001bf6`
- `KERNEL32!FreeLibrary` at `0x180001c58`
- `KERNEL32!FreeLibrary` at `0x180001c58`
- `KERNEL32!GetModuleHandleExW` at `0x180001ba1`
- `KERNEL32!GetModuleHandleExW` at `0x180001ba1`

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
0x180001b50  mov     [rsp+arg_0], rbx
0x180001b55  mov     [rsp+arg_8], rsi
0x180001b5a  push    rdi
0x180001b5b  sub     rsp, 30h
0x180001b5f  mov     rax, [rdx]
0x180001b62  lea     rsi, [rcx+30h]
0x180001b66  mov     r9, rdx
0x180001b69  mov     rdi, rcx
0x180001b6c  mov     r8, rsi
0x180001b6f  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180001b76  mov     rcx, r9
0x180001b79  mov     rax, [rax]
0x180001b7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b81  mov     ebx, eax
0x180001b83  test    eax, eax
0x180001b85  js      loc_180001C2F
0x180001b8b  cmp     dword ptr [rdi+10h], 0
0x180001b8f  jz      short loc_180001BC8
0x180001b91  lea     r8, [rdi+18h]; phModule
0x180001b95  mov     ecx, 4; dwFlags
0x180001b9a  lea     rdx, cs:180000000h; lpModuleName
0x180001ba1  call    cs:__imp_GetModuleHandleExW
0x180001ba7  test    eax, eax
0x180001ba9  jz      short loc_180001BAF
0x180001bab  xor     ebx, ebx
0x180001bad  jmp     short loc_180001BC8
0x180001baf  call    cs:__imp_GetLastError
0x180001bb5  mov     ebx, eax
0x180001bb7  test    eax, eax
0x180001bb9  jle     short loc_180001BC4
0x180001bbb  movzx   ebx, ax
0x180001bbe  or      ebx, 80070000h
0x180001bc4  test    ebx, ebx
0x180001bc6  js      short loc_180001C33
0x180001bc8  mov     rax, [rdi]
0x180001bcb  mov     rcx, rdi
0x180001bce  mov     rax, [rax+8]
0x180001bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bd7  mov     r9, rdi; lpParameter
0x180001bda  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180001be3  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x180001bea  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180001bf2  xor     edx, edx; dwStackSize
0x180001bf4  xor     ecx, ecx; lpThreadAttributes
0x180001bf6  call    cs:__imp_CreateThread
0x180001bfc  mov     [rdi+28h], rax
0x180001c00  inc     rax
0x180001c03  test    rax, 0FFFFFFFFFFFFFFFEh
0x180001c09  jnz     short loc_180001C2F
0x180001c0b  call    cs:__imp_GetLastError
0x180001c11  mov     ebx, eax
0x180001c13  test    eax, eax
0x180001c15  jle     short loc_180001C20
0x180001c17  movzx   ebx, ax
0x180001c1a  or      ebx, 80070000h
0x180001c20  mov     rax, [rdi]
0x180001c23  mov     rcx, rdi
0x180001c26  mov     rax, [rax+10h]
0x180001c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c2f  test    ebx, ebx
0x180001c31  jns     short loc_180001C83
0x180001c33  mov     rcx, [rdi+28h]; hObject
0x180001c37  lea     rax, [rcx-1]
0x180001c3b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180001c3f  ja      short loc_180001C4F
0x180001c41  call    cs:__imp_CloseHandle
0x180001c47  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180001c4f  mov     rcx, [rdi+18h]; hLibModule
0x180001c53  test    rcx, rcx
0x180001c56  jz      short loc_180001C66
0x180001c58  call    cs:__imp_FreeLibrary
0x180001c5e  mov     qword ptr [rdi+18h], 0
0x180001c66  mov     rcx, [rsi]
0x180001c69  test    rcx, rcx
0x180001c6c  jz      short loc_180001C92
0x180001c6e  mov     rax, [rcx]
0x180001c71  mov     rax, [rax+10h]
0x180001c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c7a  mov     qword ptr [rsi], 0
0x180001c81  jmp     short loc_180001C92
0x180001c83  lock or [rsp+38h+var_38], 0
0x180001c88  mov     rcx, [rdi+28h]; hThread
0x180001c8c  call    cs:__imp_ResumeThread
0x180001c92  mov     rsi, [rsp+38h+arg_8]
0x180001c97  mov     eax, ebx
0x180001c99  mov     rbx, [rsp+38h+arg_0]
0x180001c9e  add     rsp, 30h
0x180001ca2  pop     rdi
0x180001ca3  retn
```
