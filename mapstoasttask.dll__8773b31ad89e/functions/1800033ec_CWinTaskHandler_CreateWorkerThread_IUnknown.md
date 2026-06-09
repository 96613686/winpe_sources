# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x1800033ec`
- end: `0x180003540`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180005c50`

## callees

- `0x1800033ec`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000343d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000343d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800034f4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800034f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000344b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000344b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034a7`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180003528`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180003528`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180003492`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180003492`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034dd`

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
0x1800033ec  mov     [rsp+arg_0], rbx
0x1800033f1  mov     [rsp+arg_8], rsi
0x1800033f6  push    rdi
0x1800033f7  sub     rsp, 30h
0x1800033fb  mov     rax, [rdx]
0x1800033fe  lea     rsi, [rcx+30h]
0x180003402  mov     r9, rdx
0x180003405  mov     rdi, rcx
0x180003408  mov     r8, rsi
0x18000340b  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180003412  mov     rcx, r9
0x180003415  mov     rax, [rax]
0x180003418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000341d  mov     ebx, eax
0x18000341f  test    eax, eax
0x180003421  js      loc_1800034CB
0x180003427  cmp     dword ptr [rdi+10h], 0
0x18000342b  jz      short loc_180003464
0x18000342d  lea     r8, [rdi+18h]; phModule
0x180003431  mov     ecx, 4; dwFlags
0x180003436  lea     rdx, cs:180000000h; lpModuleName
0x18000343d  call    cs:__imp_GetModuleHandleExW
0x180003443  test    eax, eax
0x180003445  jz      short loc_18000344B
0x180003447  xor     ebx, ebx
0x180003449  jmp     short loc_180003464
0x18000344b  call    cs:__imp_GetLastError
0x180003451  mov     ebx, eax
0x180003453  test    eax, eax
0x180003455  jle     short loc_180003460
0x180003457  movzx   ebx, ax
0x18000345a  or      ebx, 80070000h
0x180003460  test    ebx, ebx
0x180003462  js      short loc_1800034CF
0x180003464  mov     rax, [rdi]
0x180003467  mov     rcx, rdi
0x18000346a  mov     rax, [rax+8]
0x18000346e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003473  mov     r9, rdi; lpParameter
0x180003476  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18000347f  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x180003486  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x18000348e  xor     edx, edx; dwStackSize
0x180003490  xor     ecx, ecx; lpThreadAttributes
0x180003492  call    cs:__imp_CreateThread
0x180003498  mov     [rdi+28h], rax
0x18000349c  inc     rax
0x18000349f  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800034a5  jnz     short loc_1800034CB
0x1800034a7  call    cs:__imp_GetLastError
0x1800034ad  mov     ebx, eax
0x1800034af  test    eax, eax
0x1800034b1  jle     short loc_1800034BC
0x1800034b3  movzx   ebx, ax
0x1800034b6  or      ebx, 80070000h
0x1800034bc  mov     rax, [rdi]
0x1800034bf  mov     rcx, rdi
0x1800034c2  mov     rax, [rax+10h]
0x1800034c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034cb  test    ebx, ebx
0x1800034cd  jns     short loc_18000351F
0x1800034cf  mov     rcx, [rdi+28h]; hObject
0x1800034d3  lea     rax, [rcx-1]
0x1800034d7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800034db  ja      short loc_1800034EB
0x1800034dd  call    cs:__imp_CloseHandle
0x1800034e3  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x1800034eb  mov     rcx, [rdi+18h]; hLibModule
0x1800034ef  test    rcx, rcx
0x1800034f2  jz      short loc_180003502
0x1800034f4  call    cs:__imp_FreeLibrary
0x1800034fa  mov     qword ptr [rdi+18h], 0
0x180003502  mov     rcx, [rsi]
0x180003505  test    rcx, rcx
0x180003508  jz      short loc_18000352E
0x18000350a  mov     rax, [rcx]
0x18000350d  mov     rax, [rax+10h]
0x180003511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003516  mov     qword ptr [rsi], 0
0x18000351d  jmp     short loc_18000352E
0x18000351f  lock or [rsp+38h+var_38], 0
0x180003524  mov     rcx, [rdi+28h]; hThread
0x180003528  call    cs:__imp_ResumeThread
0x18000352e  mov     rsi, [rsp+38h+arg_8]
0x180003533  mov     eax, ebx
0x180003535  mov     rbx, [rsp+38h+arg_0]
0x18000353a  add     rsp, 30h
0x18000353e  pop     rdi
0x18000353f  retn
```
