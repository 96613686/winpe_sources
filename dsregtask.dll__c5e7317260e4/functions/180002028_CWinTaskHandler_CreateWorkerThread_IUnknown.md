# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180002028`
- end: `0x18000217c`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800025c0`

## callees

- `0x180002028`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180002079`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180002079`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002130`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002130`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180002164`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180002164`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800020ce`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800020ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002087`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800020e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002087`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800020e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002119`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002119`

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
0x180002028  mov     [rsp+arg_0], rbx
0x18000202d  mov     [rsp+arg_8], rsi
0x180002032  push    rdi
0x180002033  sub     rsp, 30h
0x180002037  mov     rax, [rdx]
0x18000203a  lea     rsi, [rcx+30h]
0x18000203e  mov     r9, rdx
0x180002041  mov     rdi, rcx
0x180002044  mov     r8, rsi
0x180002047  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000204e  mov     rcx, r9
0x180002051  mov     rax, [rax]
0x180002054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002059  mov     ebx, eax
0x18000205b  test    eax, eax
0x18000205d  js      loc_180002107
0x180002063  cmp     dword ptr [rdi+10h], 0
0x180002067  jz      short loc_1800020A0
0x180002069  lea     r8, [rdi+18h]; phModule
0x18000206d  mov     ecx, 4; dwFlags
0x180002072  lea     rdx, cs:180000000h; lpModuleName
0x180002079  call    cs:__imp_GetModuleHandleExW
0x18000207f  test    eax, eax
0x180002081  jz      short loc_180002087
0x180002083  xor     ebx, ebx
0x180002085  jmp     short loc_1800020A0
0x180002087  call    cs:__imp_GetLastError
0x18000208d  mov     ebx, eax
0x18000208f  test    eax, eax
0x180002091  jle     short loc_18000209C
0x180002093  movzx   ebx, ax
0x180002096  or      ebx, 80070000h
0x18000209c  test    ebx, ebx
0x18000209e  js      short loc_18000210B
0x1800020a0  mov     rax, [rdi]
0x1800020a3  mov     rcx, rdi
0x1800020a6  mov     rax, [rax+8]
0x1800020aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020af  mov     r9, rdi; lpParameter
0x1800020b2  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1800020bb  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x1800020c2  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x1800020ca  xor     edx, edx; dwStackSize
0x1800020cc  xor     ecx, ecx; lpThreadAttributes
0x1800020ce  call    cs:__imp_CreateThread
0x1800020d4  mov     [rdi+28h], rax
0x1800020d8  inc     rax
0x1800020db  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800020e1  jnz     short loc_180002107
0x1800020e3  call    cs:__imp_GetLastError
0x1800020e9  mov     ebx, eax
0x1800020eb  test    eax, eax
0x1800020ed  jle     short loc_1800020F8
0x1800020ef  movzx   ebx, ax
0x1800020f2  or      ebx, 80070000h
0x1800020f8  mov     rax, [rdi]
0x1800020fb  mov     rcx, rdi
0x1800020fe  mov     rax, [rax+10h]
0x180002102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002107  test    ebx, ebx
0x180002109  jns     short loc_18000215B
0x18000210b  mov     rcx, [rdi+28h]; hObject
0x18000210f  lea     rax, [rcx-1]
0x180002113  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002117  ja      short loc_180002127
0x180002119  call    cs:__imp_CloseHandle
0x18000211f  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180002127  mov     rcx, [rdi+18h]; hLibModule
0x18000212b  test    rcx, rcx
0x18000212e  jz      short loc_18000213E
0x180002130  call    cs:__imp_FreeLibrary
0x180002136  mov     qword ptr [rdi+18h], 0
0x18000213e  mov     rcx, [rsi]
0x180002141  test    rcx, rcx
0x180002144  jz      short loc_18000216A
0x180002146  mov     rax, [rcx]
0x180002149  mov     rax, [rax+10h]
0x18000214d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002152  mov     qword ptr [rsi], 0
0x180002159  jmp     short loc_18000216A
0x18000215b  lock or [rsp+38h+var_38], 0
0x180002160  mov     rcx, [rdi+28h]; hThread
0x180002164  call    cs:__imp_ResumeThread
0x18000216a  mov     rsi, [rsp+38h+arg_8]
0x18000216f  mov     eax, ebx
0x180002171  mov     rbx, [rsp+38h+arg_0]
0x180002176  add     rsp, 30h
0x18000217a  pop     rdi
0x18000217b  retn
```
