# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180002614`
- end: `0x180002768`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180002b10`

## callees

- `0x180002614`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180002665`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180002665`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000271c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000271c`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180002750`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180002750`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800026ba`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800026ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002673`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800026cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002673`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800026cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002705`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002705`

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
0x180002614  mov     [rsp+arg_0], rbx
0x180002619  mov     [rsp+arg_8], rsi
0x18000261e  push    rdi
0x18000261f  sub     rsp, 30h
0x180002623  mov     rax, [rdx]
0x180002626  lea     rsi, [rcx+30h]
0x18000262a  mov     r9, rdx
0x18000262d  mov     rdi, rcx
0x180002630  mov     r8, rsi
0x180002633  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18000263a  mov     rcx, r9
0x18000263d  mov     rax, [rax]
0x180002640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002645  mov     ebx, eax
0x180002647  test    eax, eax
0x180002649  js      loc_1800026F3
0x18000264f  cmp     dword ptr [rdi+10h], 0
0x180002653  jz      short loc_18000268C
0x180002655  lea     r8, [rdi+18h]; phModule
0x180002659  mov     ecx, 4; dwFlags
0x18000265e  lea     rdx, __ImageBase; lpModuleName
0x180002665  call    cs:__imp_GetModuleHandleExW
0x18000266b  test    eax, eax
0x18000266d  jz      short loc_180002673
0x18000266f  xor     ebx, ebx
0x180002671  jmp     short loc_18000268C
0x180002673  call    cs:__imp_GetLastError
0x180002679  mov     ebx, eax
0x18000267b  test    eax, eax
0x18000267d  jle     short loc_180002688
0x18000267f  movzx   ebx, ax
0x180002682  or      ebx, 80070000h
0x180002688  test    ebx, ebx
0x18000268a  js      short loc_1800026F7
0x18000268c  mov     rax, [rdi]
0x18000268f  mov     rcx, rdi
0x180002692  mov     rax, [rax+8]
0x180002696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000269b  mov     r9, rdi; lpParameter
0x18000269e  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1800026a7  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x1800026ae  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x1800026b6  xor     edx, edx; dwStackSize
0x1800026b8  xor     ecx, ecx; lpThreadAttributes
0x1800026ba  call    cs:__imp_CreateThread
0x1800026c0  mov     [rdi+28h], rax
0x1800026c4  inc     rax
0x1800026c7  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800026cd  jnz     short loc_1800026F3
0x1800026cf  call    cs:__imp_GetLastError
0x1800026d5  mov     ebx, eax
0x1800026d7  test    eax, eax
0x1800026d9  jle     short loc_1800026E4
0x1800026db  movzx   ebx, ax
0x1800026de  or      ebx, 80070000h
0x1800026e4  mov     rax, [rdi]
0x1800026e7  mov     rcx, rdi
0x1800026ea  mov     rax, [rax+10h]
0x1800026ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026f3  test    ebx, ebx
0x1800026f5  jns     short loc_180002747
0x1800026f7  mov     rcx, [rdi+28h]; hObject
0x1800026fb  lea     rax, [rcx-1]
0x1800026ff  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002703  ja      short loc_180002713
0x180002705  call    cs:__imp_CloseHandle
0x18000270b  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180002713  mov     rcx, [rdi+18h]; hLibModule
0x180002717  test    rcx, rcx
0x18000271a  jz      short loc_18000272A
0x18000271c  call    cs:__imp_FreeLibrary
0x180002722  mov     qword ptr [rdi+18h], 0
0x18000272a  mov     rcx, [rsi]
0x18000272d  test    rcx, rcx
0x180002730  jz      short loc_180002756
0x180002732  mov     rax, [rcx]
0x180002735  mov     rax, [rax+10h]
0x180002739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000273e  mov     qword ptr [rsi], 0
0x180002745  jmp     short loc_180002756
0x180002747  lock or [rsp+38h+var_38], 0
0x18000274c  mov     rcx, [rdi+28h]; hThread
0x180002750  call    cs:__imp_ResumeThread
0x180002756  mov     rsi, [rsp+38h+arg_8]
0x18000275b  mov     eax, ebx
0x18000275d  mov     rbx, [rsp+38h+arg_0]
0x180002762  add     rsp, 30h
0x180002766  pop     rdi
0x180002767  retn
```
