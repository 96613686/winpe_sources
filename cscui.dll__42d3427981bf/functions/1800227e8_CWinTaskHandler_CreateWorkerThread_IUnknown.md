# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x1800227e8`
- end: `0x18002293c`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800230d0`

## callees

- `0x1800227e8`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800228a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800228a3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002288e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002288e`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180022924`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180022924`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800228f0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800228f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180022839`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180022839`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800228d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800228d9`

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
0x1800227e8  mov     [rsp+arg_0], rbx
0x1800227ed  mov     [rsp+arg_8], rsi
0x1800227f2  push    rdi
0x1800227f3  sub     rsp, 30h
0x1800227f7  mov     rax, [rdx]
0x1800227fa  lea     rsi, [rcx+30h]
0x1800227fe  mov     r9, rdx
0x180022801  mov     rdi, rcx
0x180022804  mov     r8, rsi
0x180022807  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18002280e  mov     rcx, r9
0x180022811  mov     rax, [rax]
0x180022814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022819  mov     ebx, eax
0x18002281b  test    eax, eax
0x18002281d  js      loc_1800228C7
0x180022823  cmp     dword ptr [rdi+10h], 0
0x180022827  jz      short loc_180022860
0x180022829  lea     r8, [rdi+18h]; phModule
0x18002282d  mov     ecx, 4; dwFlags
0x180022832  lea     rdx, __ImageBase; lpModuleName
0x180022839  call    cs:__imp_GetModuleHandleExW
0x18002283f  test    eax, eax
0x180022841  jz      short loc_180022847
0x180022843  xor     ebx, ebx
0x180022845  jmp     short loc_180022860
0x180022847  call    cs:__imp_GetLastError
0x18002284d  mov     ebx, eax
0x18002284f  test    eax, eax
0x180022851  jle     short loc_18002285C
0x180022853  movzx   ebx, ax
0x180022856  or      ebx, 80070000h
0x18002285c  test    ebx, ebx
0x18002285e  js      short loc_1800228CB
0x180022860  mov     rax, [rdi]
0x180022863  mov     rcx, rdi
0x180022866  mov     rax, [rax+8]
0x18002286a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002286f  mov     r9, rdi; lpParameter
0x180022872  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18002287b  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x180022882  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x18002288a  xor     edx, edx; dwStackSize
0x18002288c  xor     ecx, ecx; lpThreadAttributes
0x18002288e  call    cs:__imp_CreateThread
0x180022894  mov     [rdi+28h], rax
0x180022898  inc     rax
0x18002289b  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800228a1  jnz     short loc_1800228C7
0x1800228a3  call    cs:__imp_GetLastError
0x1800228a9  mov     ebx, eax
0x1800228ab  test    eax, eax
0x1800228ad  jle     short loc_1800228B8
0x1800228af  movzx   ebx, ax
0x1800228b2  or      ebx, 80070000h
0x1800228b8  mov     rax, [rdi]
0x1800228bb  mov     rcx, rdi
0x1800228be  mov     rax, [rax+10h]
0x1800228c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228c7  test    ebx, ebx
0x1800228c9  jns     short loc_18002291B
0x1800228cb  mov     rcx, [rdi+28h]; hObject
0x1800228cf  lea     rax, [rcx-1]
0x1800228d3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800228d7  ja      short loc_1800228E7
0x1800228d9  call    cs:__imp_CloseHandle
0x1800228df  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x1800228e7  mov     rcx, [rdi+18h]; hLibModule
0x1800228eb  test    rcx, rcx
0x1800228ee  jz      short loc_1800228FE
0x1800228f0  call    cs:__imp_FreeLibrary
0x1800228f6  mov     qword ptr [rdi+18h], 0
0x1800228fe  mov     rcx, [rsi]
0x180022901  test    rcx, rcx
0x180022904  jz      short loc_18002292A
0x180022906  mov     rax, [rcx]
0x180022909  mov     rax, [rax+10h]
0x18002290d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022912  mov     qword ptr [rsi], 0
0x180022919  jmp     short loc_18002292A
0x18002291b  lock or [rsp+38h+var_38], 0
0x180022920  mov     rcx, [rdi+28h]; hThread
0x180022924  call    cs:__imp_ResumeThread
0x18002292a  mov     rsi, [rsp+38h+arg_8]
0x18002292f  mov     eax, ebx
0x180022931  mov     rbx, [rsp+38h+arg_0]
0x180022936  add     rsp, 30h
0x18002293a  pop     rdi
0x18002293b  retn
```
