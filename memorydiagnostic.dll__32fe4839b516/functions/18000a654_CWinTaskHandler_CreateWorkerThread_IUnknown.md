# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x18000a654`
- end: `0x18000a7c7`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `371`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180013d90`

## callees

- `0x18000a654`
- `0x180024010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18000a774`
- `KERNEL32!FreeLibrary` at `0x18000a774`
- `KERNEL32!CreateThread` at `0x18000a703`
- `KERNEL32!CreateThread` at `0x18000a703`
- `KERNEL32!CloseHandle` at `0x18000a75a`
- `KERNEL32!CloseHandle` at `0x18000a75a`
- `KERNEL32!GetLastError` at `0x18000a6b9`
- `KERNEL32!GetLastError` at `0x18000a71e`
- `KERNEL32!GetLastError` at `0x18000a6b9`
- `KERNEL32!GetLastError` at `0x18000a71e`
- `KERNEL32!ResumeThread` at `0x18000a7a8`
- `KERNEL32!ResumeThread` at `0x18000a7a8`
- `KERNEL32!GetModuleHandleExW` at `0x18000a6a5`
- `KERNEL32!GetModuleHandleExW` at `0x18000a6a5`

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
0x18000a654  mov     [rsp+arg_0], rbx
0x18000a659  mov     [rsp+arg_8], rsi
0x18000a65e  push    rdi
0x18000a65f  sub     rsp, 30h
0x18000a663  mov     rax, [rdx]
0x18000a666  lea     rsi, [rcx+30h]
0x18000a66a  mov     r9, rdx
0x18000a66d  mov     rdi, rcx
0x18000a670  mov     r8, rsi
0x18000a673  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000a67a  mov     rcx, r9
0x18000a67d  mov     rax, [rax]
0x18000a680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a685  mov     ebx, eax
0x18000a687  test    eax, eax
0x18000a689  js      loc_18000A748
0x18000a68f  cmp     dword ptr [rdi+10h], 0
0x18000a693  jz      short loc_18000A6D8
0x18000a695  lea     r8, [rdi+18h]; phModule
0x18000a699  mov     ecx, 4; dwFlags
0x18000a69e  lea     rdx, cs:180000000h; lpModuleName
0x18000a6a5  call    cs:__imp_GetModuleHandleExW
0x18000a6ac  nop     dword ptr [rax+rax+00h]
0x18000a6b1  test    eax, eax
0x18000a6b3  jz      short loc_18000A6B9
0x18000a6b5  xor     ebx, ebx
0x18000a6b7  jmp     short loc_18000A6D8
0x18000a6b9  call    cs:__imp_GetLastError
0x18000a6c0  nop     dword ptr [rax+rax+00h]
0x18000a6c5  mov     ebx, eax
0x18000a6c7  test    eax, eax
0x18000a6c9  jle     short loc_18000A6D4
0x18000a6cb  movzx   ebx, ax
0x18000a6ce  or      ebx, 80070000h
0x18000a6d4  test    ebx, ebx
0x18000a6d6  js      short loc_18000A74C
0x18000a6d8  mov     rax, [rdi]
0x18000a6db  mov     rcx, rdi
0x18000a6de  mov     rax, [rax+8]
0x18000a6e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6e7  and     [rsp+38h+var_10], 0
0x18000a6ed  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x18000a6f4  mov     r9, rdi; lpParameter
0x18000a6f7  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x18000a6ff  xor     edx, edx; dwStackSize
0x18000a701  xor     ecx, ecx; lpThreadAttributes
0x18000a703  call    cs:__imp_CreateThread
0x18000a70a  nop     dword ptr [rax+rax+00h]
0x18000a70f  mov     [rdi+28h], rax
0x18000a713  inc     rax
0x18000a716  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000a71c  jnz     short loc_18000A748
0x18000a71e  call    cs:__imp_GetLastError
0x18000a725  nop     dword ptr [rax+rax+00h]
0x18000a72a  mov     ebx, eax
0x18000a72c  test    eax, eax
0x18000a72e  jle     short loc_18000A739
0x18000a730  movzx   ebx, ax
0x18000a733  or      ebx, 80070000h
0x18000a739  mov     rax, [rdi]
0x18000a73c  mov     rcx, rdi
0x18000a73f  mov     rax, [rax+10h]
0x18000a743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a748  test    ebx, ebx
0x18000a74a  jns     short loc_18000A79F
0x18000a74c  mov     rcx, [rdi+28h]; hObject
0x18000a750  lea     rax, [rcx-1]
0x18000a754  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a758  ja      short loc_18000A76B
0x18000a75a  call    cs:__imp_CloseHandle
0x18000a761  nop     dword ptr [rax+rax+00h]
0x18000a766  or      qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x18000a76b  mov     rcx, [rdi+18h]; hLibModule
0x18000a76f  test    rcx, rcx
0x18000a772  jz      short loc_18000A785
0x18000a774  call    cs:__imp_FreeLibrary
0x18000a77b  nop     dword ptr [rax+rax+00h]
0x18000a780  and     qword ptr [rdi+18h], 0
0x18000a785  mov     rcx, [rsi]
0x18000a788  test    rcx, rcx
0x18000a78b  jz      short loc_18000A7B4
0x18000a78d  mov     rax, [rcx]
0x18000a790  mov     rax, [rax+10h]
0x18000a794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a799  and     qword ptr [rsi], 0
0x18000a79d  jmp     short loc_18000A7B4
0x18000a79f  lock or [rsp+38h+var_38], 0
0x18000a7a4  mov     rcx, [rdi+28h]; hThread
0x18000a7a8  call    cs:__imp_ResumeThread
0x18000a7af  nop     dword ptr [rax+rax+00h]
0x18000a7b4  mov     rsi, [rsp+38h+arg_8]
0x18000a7b9  mov     eax, ebx
0x18000a7bb  mov     rbx, [rsp+38h+arg_0]
0x18000a7c0  add     rsp, 30h
0x18000a7c4  pop     rdi
0x18000a7c5  retn
```
