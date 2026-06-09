# CWinTaskHandler::CreateWorkerThread(IUnknown *)

- ea: `0x180011924`
- end: `0x180011a78`
- name: `?CreateWorkerThread@CWinTaskHandler@@AEAAJPEAUIUnknown@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800143a0`

## callees

- `0x180011924`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180011a2c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180011a2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180011975`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180011975`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011983`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011983`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119df`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800119ca`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800119ca`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180011a60`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180011a60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011a15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011a15`

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
0x180011924  mov     [rsp+arg_0], rbx
0x180011929  mov     [rsp+arg_8], rsi
0x18001192e  push    rdi
0x18001192f  sub     rsp, 30h
0x180011933  mov     rax, [rdx]
0x180011936  lea     rsi, [rcx+30h]
0x18001193a  mov     r9, rdx
0x18001193d  mov     rdi, rcx
0x180011940  mov     r8, rsi
0x180011943  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x18001194a  mov     rcx, r9
0x18001194d  mov     rax, [rax]
0x180011950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011955  mov     ebx, eax
0x180011957  test    eax, eax
0x180011959  js      loc_180011A03
0x18001195f  cmp     dword ptr [rdi+10h], 0
0x180011963  jz      short loc_18001199C
0x180011965  lea     r8, [rdi+18h]; phModule
0x180011969  mov     ecx, 4; dwFlags
0x18001196e  lea     rdx, __ImageBase; lpModuleName
0x180011975  call    cs:__imp_GetModuleHandleExW
0x18001197b  test    eax, eax
0x18001197d  jz      short loc_180011983
0x18001197f  xor     ebx, ebx
0x180011981  jmp     short loc_18001199C
0x180011983  call    cs:__imp_GetLastError
0x180011989  mov     ebx, eax
0x18001198b  test    eax, eax
0x18001198d  jle     short loc_180011998
0x18001198f  movzx   ebx, ax
0x180011992  or      ebx, 80070000h
0x180011998  test    ebx, ebx
0x18001199a  js      short loc_180011A07
0x18001199c  mov     rax, [rdi]
0x18001199f  mov     rcx, rdi
0x1800119a2  mov     rax, [rax+8]
0x1800119a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119ab  mov     r9, rdi; lpParameter
0x1800119ae  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1800119b7  lea     r8, ?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z; lpStartAddress
0x1800119be  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x1800119c6  xor     edx, edx; dwStackSize
0x1800119c8  xor     ecx, ecx; lpThreadAttributes
0x1800119ca  call    cs:__imp_CreateThread
0x1800119d0  mov     [rdi+28h], rax
0x1800119d4  inc     rax
0x1800119d7  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800119dd  jnz     short loc_180011A03
0x1800119df  call    cs:__imp_GetLastError
0x1800119e5  mov     ebx, eax
0x1800119e7  test    eax, eax
0x1800119e9  jle     short loc_1800119F4
0x1800119eb  movzx   ebx, ax
0x1800119ee  or      ebx, 80070000h
0x1800119f4  mov     rax, [rdi]
0x1800119f7  mov     rcx, rdi
0x1800119fa  mov     rax, [rax+10h]
0x1800119fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a03  test    ebx, ebx
0x180011a05  jns     short loc_180011A57
0x180011a07  mov     rcx, [rdi+28h]; hObject
0x180011a0b  lea     rax, [rcx-1]
0x180011a0f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011a13  ja      short loc_180011A23
0x180011a15  call    cs:__imp_CloseHandle
0x180011a1b  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180011a23  mov     rcx, [rdi+18h]; hLibModule
0x180011a27  test    rcx, rcx
0x180011a2a  jz      short loc_180011A3A
0x180011a2c  call    cs:__imp_FreeLibrary
0x180011a32  mov     qword ptr [rdi+18h], 0
0x180011a3a  mov     rcx, [rsi]
0x180011a3d  test    rcx, rcx
0x180011a40  jz      short loc_180011A66
0x180011a42  mov     rax, [rcx]
0x180011a45  mov     rax, [rax+10h]
0x180011a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a4e  mov     qword ptr [rsi], 0
0x180011a55  jmp     short loc_180011A66
0x180011a57  lock or [rsp+38h+var_38], 0
0x180011a5c  mov     rcx, [rdi+28h]; hThread
0x180011a60  call    cs:__imp_ResumeThread
0x180011a66  mov     rsi, [rsp+38h+arg_8]
0x180011a6b  mov     eax, ebx
0x180011a6d  mov     rbx, [rsp+38h+arg_0]
0x180011a72  add     rsp, 30h
0x180011a76  pop     rdi
0x180011a77  retn
```
