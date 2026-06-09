# Debugger::TargetComposition::DebugSources::DemandStreamMapManager::Initialize(void)

- ea: `0x1804b01d8`
- end: `0x1804b0355`
- name: `?Initialize@DemandStreamMapManager@DebugSources@TargetComposition@Debugger@@QEAAJXZ`
- size: `381`
- prototype: `__int64 __fastcall(Debugger::TargetComposition::DebugSources::DemandStreamMapManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1804afd18`

## callees

- `0x1800f13ec`
- `0x1800f1720`
- `0x1804b01d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1804b0201`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1804b024f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1804b0201`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1804b024f`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1804b02cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1804b02cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804b0216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804b0216`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1804b031d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1804b031d`

## pseudocode

```c
signed int __fastcall Debugger::TargetComposition::DebugSources::DemandStreamMapManager::Initialize(
        Debugger::TargetComposition::DebugSources::DemandStreamMapManager *this)
{
  HANDLE Semaphore; // rax
  signed int result; // eax
  HANDLE v4; // rax
  void *v5; // rax
  const struct std::nothrow_t *v6; // rdx
  void *v7; // rcx
  unsigned __int64 i; // rdx
  __int64 v9; // rcx
  unsigned __int64 j; // rdi
  HANDLE Thread; // rax

  Semaphore = CreateSemaphoreExW(0, 0, 16, 0, 0, 0x1F0003u);
  *((_QWORD *)this + 6) = Semaphore;
  if ( !Semaphore || (v4 = CreateSemaphoreExW(0, 16, 16, 0, 0, 0x1F0003u), (*((_QWORD *)this + 7) = v4) == 0) )
  {
LABEL_2:
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    goto LABEL_17;
  }
  v5 = operator new[](0x200u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = (void *)*((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = v5;
  if ( v7 )
    operator delete(v7, v6);
  if ( *((_QWORD *)this + 8) )
  {
    for ( i = 0; i < 0x10; ++i )
    {
      v9 = 32 * i;
      *(_QWORD *)(*((_QWORD *)this + 8) + v9 + 16) = 0;
      *(_DWORD *)(v9 + *((_QWORD *)this + 8) + 28) = 0;
    }
    for ( j = 0; j < 0x10; ++j )
    {
      *(_QWORD *)(*((_QWORD *)this + 8) + 32 * j + 16) = CreateEventA(0, 0, 0, 0);
      if ( !*(_QWORD *)(*((_QWORD *)this + 8) + 32 * j + 16) )
        goto LABEL_2;
    }
    Thread = CreateThread(
               0,
               0,
               Debugger::TargetComposition::DebugSources::DemandStreamMapManager::ReaderThreadTrampoline,
               this,
               0,
               0);
    *((_QWORD *)this + 5) = Thread;
    if ( Thread )
    {
      *((_DWORD *)this + 2) = 0;
      return 0;
    }
    goto LABEL_2;
  }
  result = -2147024882;
LABEL_17:
  *((_DWORD *)this + 2) = result;
  return result;
}

```

## disassembly

```asm
0x1804b01d8  mov     [rsp+arg_0], rbx
0x1804b01dd  push    rdi
0x1804b01de  sub     rsp, 30h
0x1804b01e2  xor     r9d, r9d; lpName
0x1804b01e5  mov     rbx, rcx
0x1804b01e8  mov     edi, 1F0003h
0x1804b01ed  xor     edx, edx; lInitialCount
0x1804b01ef  mov     [rsp+38h+dwDesiredAccess], edi; dwDesiredAccess
0x1804b01f3  xor     ecx, ecx; lpSemaphoreAttributes
0x1804b01f5  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1804b01fd  lea     r8d, [r9+10h]; lMaximumCount
0x1804b0201  call    cs:__imp_CreateSemaphoreExW
0x1804b0208  nop     dword ptr [rax+rax+00h]
0x1804b020d  mov     [rbx+30h], rax
0x1804b0211  test    rax, rax
0x1804b0214  jnz     short loc_1804B0237
0x1804b0216  call    cs:__imp_GetLastError
0x1804b021d  nop     dword ptr [rax+rax+00h]
0x1804b0222  test    eax, eax
0x1804b0224  jle     loc_1804B0346
0x1804b022a  movzx   eax, ax
0x1804b022d  or      eax, 80070000h
0x1804b0232  jmp     loc_1804B0346
0x1804b0237  xor     r9d, r9d; lpName
0x1804b023a  mov     [rsp+38h+dwDesiredAccess], edi; dwDesiredAccess
0x1804b023e  xor     ecx, ecx; lpSemaphoreAttributes
0x1804b0240  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1804b0248  lea     edx, [r9+10h]; lInitialCount
0x1804b024c  mov     r8d, edx; lMaximumCount
0x1804b024f  call    cs:__imp_CreateSemaphoreExW
0x1804b0256  nop     dword ptr [rax+rax+00h]
0x1804b025b  mov     [rbx+38h], rax
0x1804b025f  test    rax, rax
0x1804b0262  jz      short loc_1804B0216
0x1804b0264  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1804b026b  mov     ecx, 200h; unsigned __int64
0x1804b0270  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1804b0275  mov     rcx, [rbx+40h]; void *
0x1804b0279  mov     [rbx+40h], rax
0x1804b027d  test    rcx, rcx
0x1804b0280  jz      short loc_1804B0287
0x1804b0282  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1804b0287  cmp     qword ptr [rbx+40h], 0
0x1804b028c  jz      loc_1804B0341
0x1804b0292  xor     edx, edx
0x1804b0294  mov     rax, [rbx+40h]
0x1804b0298  mov     rcx, rdx
0x1804b029b  shl     rcx, 5
0x1804b029f  inc     rdx
0x1804b02a2  mov     qword ptr [rax+rcx+10h], 0
0x1804b02ab  mov     rax, [rbx+40h]
0x1804b02af  mov     dword ptr [rcx+rax+1Ch], 0
0x1804b02b7  cmp     rdx, 10h
0x1804b02bb  jb      short loc_1804B0294
0x1804b02bd  xor     edi, edi
0x1804b02bf  xor     ecx, ecx; lpThreadAttributes
0x1804b02c1  cmp     rdi, 10h
0x1804b02c5  jnb     short loc_1804B0300
0x1804b02c7  xor     r9d, r9d; lpName
0x1804b02ca  xor     r8d, r8d; bInitialState
0x1804b02cd  xor     edx, edx; bManualReset
0x1804b02cf  call    cs:__imp_CreateEventA
0x1804b02d6  nop     dword ptr [rax+rax+00h]
0x1804b02db  mov     rcx, [rbx+40h]
0x1804b02df  mov     rdx, rdi
0x1804b02e2  shl     rdx, 5
0x1804b02e6  mov     [rcx+rdx+10h], rax
0x1804b02eb  mov     rax, [rbx+40h]
0x1804b02ef  cmp     qword ptr [rax+rdx+10h], 0
0x1804b02f5  jz      loc_1804B0216
0x1804b02fb  inc     rdi
0x1804b02fe  jmp     short loc_1804B02BF
0x1804b0300  mov     qword ptr [rsp+38h+dwDesiredAccess], 0; lpThreadId
0x1804b0309  lea     r8, ?ReaderThreadTrampoline@DemandStreamMapManager@DebugSources@TargetComposition@Debugger@@CAKPEAX@Z; lpStartAddress
0x1804b0310  mov     r9, rbx; lpParameter
0x1804b0313  mov     [rsp+38h+dwFlags], 0; dwCreationFlags
0x1804b031b  xor     edx, edx; dwStackSize
0x1804b031d  call    cs:__imp_CreateThread
0x1804b0324  nop     dword ptr [rax+rax+00h]
0x1804b0329  mov     [rbx+28h], rax
0x1804b032d  test    rax, rax
0x1804b0330  jz      loc_1804B0216
0x1804b0336  mov     dword ptr [rbx+8], 0
0x1804b033d  xor     eax, eax
0x1804b033f  jmp     short loc_1804B0349
0x1804b0341  mov     eax, 8007000Eh
0x1804b0346  mov     [rbx+8], eax
0x1804b0349  mov     rbx, [rsp+38h+arg_0]
0x1804b034e  add     rsp, 30h
0x1804b0352  pop     rdi
0x1804b0353  retn
```
