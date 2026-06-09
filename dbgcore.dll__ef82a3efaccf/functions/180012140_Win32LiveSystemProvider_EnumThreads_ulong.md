# Win32LiveSystemProvider::EnumThreads(ulong *)

- ea: `0x180012140`
- end: `0x18001220b`
- name: `?EnumThreads@Win32LiveSystemProvider@@UEAAJPEAK@Z`
- size: `203`
- prototype: `__int64 __fastcall(Win32LiveSystemProvider *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180012140`
- `0x180012214`

## import_xrefs

- `ntdll!NtGetNextThread` at `0x180012195`
- `ntdll!NtGetNextThread` at `0x180012195`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800121cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800121d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800121cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800121d6`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1800121c2`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1800121c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800121a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800121a0`

## pseudocode

```c
__int64 __fastcall Win32LiveSystemProvider::EnumThreads(Win32LiveSystemProvider *this, unsigned int *a2)
{
  HANDLE *v4; // r14
  void *v5; // rbx
  int NextThread; // edi
  unsigned int v7; // edi
  DWORD ThreadId; // eax
  signed int LastError; // eax

  if ( *((_DWORD *)this + 205) )
    return Win32LiveSystemProvider::EnumThreadsUsingToolHelp(this, a2);
  if ( !*((_DWORD *)this + 204) )
    return 2147549183LL;
  v4 = (HANDLE *)((char *)this + 704);
  v5 = (void *)*((_QWORD *)this + 88);
  NextThread = NtGetNextThread(*((_QWORD *)this + 82), v5, 64);
  CloseHandle(v5);
  if ( NextThread >= 0 )
  {
    ThreadId = GetThreadId(*v4);
    if ( ThreadId )
    {
      *a2 = ThreadId;
      return 0;
    }
    else if ( GetLastError() )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      return (unsigned int)-2147467259;
    }
  }
  else if ( NextThread == -2147483622 )
  {
    return 1;
  }
  else
  {
    return NextThread | 0x10000000u;
  }
  return v7;
}

```

## disassembly

```asm
0x180012140  push    rbx
0x180012142  push    rsi
0x180012143  push    rdi
0x180012144  push    r14
0x180012146  sub     rsp, 38h
0x18001214a  cmp     dword ptr [rcx+334h], 0
0x180012151  mov     rsi, rdx
0x180012154  jnz     loc_1800121FC
0x18001215a  cmp     dword ptr [rcx+330h], 0
0x180012161  jnz     short loc_18001216D
0x180012163  mov     eax, 8000FFFFh
0x180012168  jmp     loc_180012201
0x18001216d  lea     r14, [rcx+2C0h]
0x180012174  xor     r9d, r9d
0x180012177  mov     rbx, [r14]
0x18001217a  mov     rcx, [rcx+290h]
0x180012181  mov     rdx, rbx
0x180012184  mov     [rsp+58h+var_30], r14
0x180012189  lea     r8d, [r9+40h]
0x18001218d  mov     [rsp+58h+var_38], 0
0x180012195  call    cs:__imp_NtGetNextThread
0x18001219b  mov     rcx, rbx; hObject
0x18001219e  mov     edi, eax
0x1800121a0  call    cs:__imp_CloseHandle
0x1800121a6  test    edi, edi
0x1800121a8  jns     short loc_1800121BF
0x1800121aa  cmp     edi, 8000001Ah
0x1800121b0  jnz     short loc_1800121B9
0x1800121b2  mov     edi, 1
0x1800121b7  jmp     short loc_1800121F8
0x1800121b9  bts     edi, 1Ch
0x1800121bd  jmp     short loc_1800121F8
0x1800121bf  mov     rcx, [r14]; Thread
0x1800121c2  call    cs:__imp_GetThreadId
0x1800121c8  test    eax, eax
0x1800121ca  jnz     short loc_1800121F4
0x1800121cc  call    cs:__imp_GetLastError
0x1800121d2  test    eax, eax
0x1800121d4  jz      short loc_1800121ED
0x1800121d6  call    cs:__imp_GetLastError
0x1800121dc  mov     edi, eax
0x1800121de  test    eax, eax
0x1800121e0  jle     short loc_1800121F8
0x1800121e2  movzx   edi, ax
0x1800121e5  or      edi, 80070000h
0x1800121eb  jmp     short loc_1800121F8
0x1800121ed  mov     edi, 80004005h
0x1800121f2  jmp     short loc_1800121F8
0x1800121f4  mov     [rsi], eax
0x1800121f6  xor     edi, edi
0x1800121f8  mov     eax, edi
0x1800121fa  jmp     short loc_180012201
0x1800121fc  call    ?EnumThreadsUsingToolHelp@Win32LiveSystemProvider@@AEAAJPEAK@Z; Win32LiveSystemProvider::EnumThreadsUsingToolHelp(ulong *)
0x180012201  add     rsp, 38h
0x180012205  pop     r14
0x180012207  pop     rdi
0x180012208  pop     rsi
0x180012209  pop     rbx
0x18001220a  retn
```
