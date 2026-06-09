# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x18000a4c4`
- end: `0x18000a618`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180013290`

## callees

- `0x18000a4c4`
- `0x180023010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18000a5cc`
- `KERNEL32!FreeLibrary` at `0x18000a5cc`
- `KERNEL32!CreateThread` at `0x18000a56a`
- `KERNEL32!CreateThread` at `0x18000a56a`
- `KERNEL32!CloseHandle` at `0x18000a5b5`
- `KERNEL32!CloseHandle` at `0x18000a5b5`
- `KERNEL32!GetLastError` at `0x18000a523`
- `KERNEL32!GetLastError` at `0x18000a57f`
- `KERNEL32!GetLastError` at `0x18000a523`
- `KERNEL32!GetLastError` at `0x18000a57f`
- `KERNEL32!ResumeThread` at `0x18000a600`
- `KERNEL32!ResumeThread` at `0x18000a600`
- `KERNEL32!GetModuleHandleExW` at `0x18000a515`
- `KERNEL32!GetModuleHandleExW` at `0x18000a515`

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
0x18000a4c4  mov     [rsp+arg_0], rbx
0x18000a4c9  mov     [rsp+arg_8], rsi
0x18000a4ce  push    rdi
0x18000a4cf  sub     rsp, 30h
0x18000a4d3  mov     rax, [rdx]
0x18000a4d6  lea     rsi, [rcx+30h]
0x18000a4da  mov     r9, rdx
0x18000a4dd  mov     rdi, rcx
0x18000a4e0  mov     r8, rsi
0x18000a4e3  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000a4ea  mov     rcx, r9
0x18000a4ed  mov     rax, [rax]
0x18000a4f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4f5  mov     ebx, eax
0x18000a4f7  test    eax, eax
0x18000a4f9  js      loc_18000A5A3
0x18000a4ff  cmp     dword ptr [rdi+10h], 0
0x18000a503  jz      short loc_18000A53C
0x18000a505  lea     r8, [rdi+18h]; phModule
0x18000a509  mov     ecx, 4; dwFlags
0x18000a50e  lea     rdx, cs:180000000h; lpModuleName
0x18000a515  call    cs:__imp_GetModuleHandleExW
0x18000a51b  test    eax, eax
0x18000a51d  jz      short loc_18000A523
0x18000a51f  xor     ebx, ebx
0x18000a521  jmp     short loc_18000A53C
0x18000a523  call    cs:__imp_GetLastError
0x18000a529  mov     ebx, eax
0x18000a52b  test    eax, eax
0x18000a52d  jle     short loc_18000A538
0x18000a52f  movzx   ebx, ax
0x18000a532  or      ebx, 80070000h
0x18000a538  test    ebx, ebx
0x18000a53a  js      short loc_18000A5A7
0x18000a53c  mov     rax, [rdi]
0x18000a53f  mov     rcx, rdi
0x18000a542  mov     rax, [rax+8]
0x18000a546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a54b  mov     r9, rdi; lpParameter
0x18000a54e  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18000a557  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x18000a55e  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x18000a566  xor     edx, edx; dwStackSize
0x18000a568  xor     ecx, ecx; lpThreadAttributes
0x18000a56a  call    cs:__imp_CreateThread
0x18000a570  mov     [rdi+28h], rax
0x18000a574  inc     rax
0x18000a577  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000a57d  jnz     short loc_18000A5A3
0x18000a57f  call    cs:__imp_GetLastError
0x18000a585  mov     ebx, eax
0x18000a587  test    eax, eax
0x18000a589  jle     short loc_18000A594
0x18000a58b  movzx   ebx, ax
0x18000a58e  or      ebx, 80070000h
0x18000a594  mov     rax, [rdi]
0x18000a597  mov     rcx, rdi
0x18000a59a  mov     rax, [rax+10h]
0x18000a59e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5a3  test    ebx, ebx
0x18000a5a5  jns     short loc_18000A5F7
0x18000a5a7  mov     rcx, [rdi+28h]; hObject
0x18000a5ab  lea     rax, [rcx-1]
0x18000a5af  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a5b3  ja      short loc_18000A5C3
0x18000a5b5  call    cs:__imp_CloseHandle
0x18000a5bb  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x18000a5c3  mov     rcx, [rdi+18h]; hLibModule
0x18000a5c7  test    rcx, rcx
0x18000a5ca  jz      short loc_18000A5DA
0x18000a5cc  call    cs:__imp_FreeLibrary
0x18000a5d2  mov     qword ptr [rdi+18h], 0
0x18000a5da  mov     rcx, [rsi]
0x18000a5dd  test    rcx, rcx
0x18000a5e0  jz      short loc_18000A606
0x18000a5e2  mov     rax, [rcx]
0x18000a5e5  mov     rax, [rax+10h]
0x18000a5e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5ee  mov     qword ptr [rsi], 0
0x18000a5f5  jmp     short loc_18000A606
0x18000a5f7  lock or [rsp+38h+var_38], 0
0x18000a5fc  mov     rcx, [rdi+28h]; hThread
0x18000a600  call    cs:__imp_ResumeThread
0x18000a606  mov     rsi, [rsp+38h+arg_8]
0x18000a60b  mov     eax, ebx
0x18000a60d  mov     rbx, [rsp+38h+arg_0]
0x18000a612  add     rsp, 30h
0x18000a616  pop     rdi
0x18000a617  retn
```
