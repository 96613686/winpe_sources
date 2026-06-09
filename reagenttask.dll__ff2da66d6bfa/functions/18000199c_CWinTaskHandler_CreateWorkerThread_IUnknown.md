# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x18000199c`
- end: `0x180001b0f`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `371`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180001cd0`

## callees

- `0x18000199c`
- `0x180003010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800019ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800019ed`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001abc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001abc`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180001af0`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180001af0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180001a4b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180001a4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001aa2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001aa2`

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
0x18000199c  mov     [rsp+arg_0], rbx
0x1800019a1  mov     [rsp+arg_8], rsi
0x1800019a6  push    rdi
0x1800019a7  sub     rsp, 30h
0x1800019ab  mov     rax, [rdx]
0x1800019ae  lea     rsi, [rcx+30h]
0x1800019b2  mov     r9, rdx
0x1800019b5  mov     rdi, rcx
0x1800019b8  mov     r8, rsi
0x1800019bb  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x1800019c2  mov     rcx, r9
0x1800019c5  mov     rax, [rax]
0x1800019c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019cd  mov     ebx, eax
0x1800019cf  test    eax, eax
0x1800019d1  js      loc_180001A90
0x1800019d7  cmp     dword ptr [rdi+10h], 0
0x1800019db  jz      short loc_180001A20
0x1800019dd  lea     r8, [rdi+18h]; phModule
0x1800019e1  mov     ecx, 4; dwFlags
0x1800019e6  lea     rdx, cs:180000000h; lpModuleName
0x1800019ed  call    cs:__imp_GetModuleHandleExW
0x1800019f4  nop     dword ptr [rax+rax+00h]
0x1800019f9  test    eax, eax
0x1800019fb  jz      short loc_180001A01
0x1800019fd  xor     ebx, ebx
0x1800019ff  jmp     short loc_180001A20
0x180001a01  call    cs:__imp_GetLastError
0x180001a08  nop     dword ptr [rax+rax+00h]
0x180001a0d  mov     ebx, eax
0x180001a0f  test    eax, eax
0x180001a11  jle     short loc_180001A1C
0x180001a13  movzx   ebx, ax
0x180001a16  or      ebx, 80070000h
0x180001a1c  test    ebx, ebx
0x180001a1e  js      short loc_180001A94
0x180001a20  mov     rax, [rdi]
0x180001a23  mov     rcx, rdi
0x180001a26  mov     rax, [rax+8]
0x180001a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a2f  and     [rsp+38h+var_10], 0
0x180001a35  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x180001a3c  mov     r9, rdi; lpParameter
0x180001a3f  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180001a47  xor     edx, edx; dwStackSize
0x180001a49  xor     ecx, ecx; lpThreadAttributes
0x180001a4b  call    cs:__imp_CreateThread
0x180001a52  nop     dword ptr [rax+rax+00h]
0x180001a57  mov     [rdi+28h], rax
0x180001a5b  inc     rax
0x180001a5e  test    rax, 0FFFFFFFFFFFFFFFEh
0x180001a64  jnz     short loc_180001A90
0x180001a66  call    cs:__imp_GetLastError
0x180001a6d  nop     dword ptr [rax+rax+00h]
0x180001a72  mov     ebx, eax
0x180001a74  test    eax, eax
0x180001a76  jle     short loc_180001A81
0x180001a78  movzx   ebx, ax
0x180001a7b  or      ebx, 80070000h
0x180001a81  mov     rax, [rdi]
0x180001a84  mov     rcx, rdi
0x180001a87  mov     rax, [rax+10h]
0x180001a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a90  test    ebx, ebx
0x180001a92  jns     short loc_180001AE7
0x180001a94  mov     rcx, [rdi+28h]; hObject
0x180001a98  lea     rax, [rcx-1]
0x180001a9c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180001aa0  ja      short loc_180001AB3
0x180001aa2  call    cs:__imp_CloseHandle
0x180001aa9  nop     dword ptr [rax+rax+00h]
0x180001aae  or      qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180001ab3  mov     rcx, [rdi+18h]; hLibModule
0x180001ab7  test    rcx, rcx
0x180001aba  jz      short loc_180001ACD
0x180001abc  call    cs:__imp_FreeLibrary
0x180001ac3  nop     dword ptr [rax+rax+00h]
0x180001ac8  and     qword ptr [rdi+18h], 0
0x180001acd  mov     rcx, [rsi]
0x180001ad0  test    rcx, rcx
0x180001ad3  jz      short loc_180001AFC
0x180001ad5  mov     rax, [rcx]
0x180001ad8  mov     rax, [rax+10h]
0x180001adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ae1  and     qword ptr [rsi], 0
0x180001ae5  jmp     short loc_180001AFC
0x180001ae7  lock or [rsp+38h+var_38], 0
0x180001aec  mov     rcx, [rdi+28h]; hThread
0x180001af0  call    cs:__imp_ResumeThread
0x180001af7  nop     dword ptr [rax+rax+00h]
0x180001afc  mov     rsi, [rsp+38h+arg_8]
0x180001b01  mov     eax, ebx
0x180001b03  mov     rbx, [rsp+38h+arg_0]
0x180001b08  add     rsp, 30h
0x180001b0c  pop     rdi
0x180001b0d  retn
```
