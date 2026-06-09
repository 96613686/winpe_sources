# CPerContext::TakeSem(ulong)

- ea: `0x18001a510`
- end: `0x18001a60e`
- name: `?TakeSem@CPerContext@@QEAAJK@Z`
- size: `254`
- prototype: `__int64 __fastcall(CPerContext *__hidden this, unsigned int)`
- caller_count: `12`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180019b20`
- `0x180019ee0`
- `0x18001b550`
- `0x180024720`
- `0x1800316d0`
- `0x180031770`
- `0x180031d40`
- `0x180035bb0`
- `0x180036fd0`
- `0x180038910`
- `0x18004d7f0`
- `0x18004e170`

## callees

- `0x18001a510`
- `0x18001b840`
- `0x180032aac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a5b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a5b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a522`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a522`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a599`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a599`

## pseudocode

```c
__int64 __fastcall CPerContext::TakeSem(CPerContext *this)
{
  DWORD CurrentThreadId; // eax
  DWORD v3; // ebx
  signed __int32 v4; // et0
  __int64 v5; // rcx
  signed int v6; // ebx
  __int64 v7; // rcx
  int v9; // edx
  DWORD v10; // eax
  signed int LastError; // eax

  CurrentThreadId = GetCurrentThreadId();
  v3 = CurrentThreadId;
  v4 = _InterlockedIncrement(*((volatile signed __int32 **)this + 14));
  v5 = *((_QWORD *)this + 14);
  if ( !v4 )
  {
    *(_DWORD *)(v5 + 4) = 1;
    *(_DWORD *)(*((_QWORD *)this + 14) + 8LL) = CurrentThreadId;
LABEL_3:
    v6 = 0;
    goto LABEL_4;
  }
  if ( *(_DWORD *)(v5 + 8) == CurrentThreadId )
  {
    ++*(_DWORD *)(v5 + 4);
    goto LABEL_3;
  }
  v10 = WaitForSingleObject(*((HANDLE *)this + 15), 0x124F80u);
  if ( !v10 || v10 == 128 )
  {
    *(_DWORD *)(*((_QWORD *)this + 14) + 4LL) = 1;
    *(_DWORD *)(*((_QWORD *)this + 14) + 8LL) = v3;
    goto LABEL_3;
  }
  if ( v10 == 258 )
    return 2147680512LL;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 < 0 )
    return (unsigned int)v6;
LABEL_4:
  v7 = *((_QWORD *)this + 11);
  if ( v7 )
  {
    v9 = **(_DWORD **)(v7 + 8);
    if ( v9 != *(_DWORD *)(v7 + 16) )
    {
      v6 = CSharedMemoryBlock::Commit((CSharedMemoryBlock *)v7, v9 - 24);
      if ( v6 < 0 )
        CDfMutex::Release((HANDLE *)this + 14);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001a510  mov     [rsp+arg_0], rbx
0x18001a515  mov     [rsp+arg_10], rsi
0x18001a51a  push    rdi
0x18001a51b  sub     rsp, 20h
0x18001a51f  mov     rsi, rcx
0x18001a522  call    cs:__imp_GetCurrentThreadId
0x18001a528  mov     rdx, [rsi+70h]
0x18001a52c  mov     ebx, eax
0x18001a52e  lock inc dword ptr [rdx]
0x18001a531  mov     rcx, [rsi+70h]
0x18001a535  jnz     short loc_18001A586
0x18001a537  mov     dword ptr [rcx+4], 1
0x18001a53e  mov     rcx, [rsi+70h]
0x18001a542  mov     [rcx+8], eax
0x18001a545  xor     ebx, ebx
0x18001a547  mov     rcx, [rsi+58h]; this
0x18001a54b  test    rcx, rcx
0x18001a54e  jnz     short loc_18001A562
0x18001a550  mov     eax, ebx
0x18001a552  mov     rbx, [rsp+28h+arg_0]
0x18001a557  mov     rsi, [rsp+28h+arg_10]
0x18001a55c  add     rsp, 20h
0x18001a560  pop     rdi
0x18001a561  retn
0x18001a562  mov     rax, [rcx+8]
0x18001a566  mov     edx, [rax]
0x18001a568  cmp     edx, [rcx+10h]
0x18001a56b  jz      short loc_18001A550
0x18001a56d  add     edx, 0FFFFFFE8h; unsigned int
0x18001a570  call    ?Commit@CSharedMemoryBlock@@QEAAJK@Z; CSharedMemoryBlock::Commit(ulong)
0x18001a575  mov     ebx, eax
0x18001a577  test    eax, eax
0x18001a579  jns     short loc_18001A550
0x18001a57b  lea     rcx, [rsi+70h]; this
0x18001a57f  call    ?Release@CDfMutex@@QEAAXXZ; CDfMutex::Release(void)
0x18001a584  jmp     short loc_18001A550
0x18001a586  cmp     [rcx+8], ebx
0x18001a589  jnz     short loc_18001A590
0x18001a58b  inc     dword ptr [rcx+4]
0x18001a58e  jmp     short loc_18001A545
0x18001a590  mov     rcx, [rsi+78h]; hHandle
0x18001a594  mov     edx, 124F80h; dwMilliseconds
0x18001a599  call    cs:__imp_WaitForSingleObject
0x18001a59f  test    eax, eax
0x18001a5a1  jz      short loc_18001A5F7
0x18001a5a3  cmp     eax, 80h
0x18001a5a8  jz      short loc_18001A5F7
0x18001a5aa  cmp     eax, 102h
0x18001a5af  jz      short loc_18001A5E0
0x18001a5b1  call    cs:__imp_GetLastError
0x18001a5b7  mov     ebx, eax
0x18001a5b9  test    eax, eax
0x18001a5bb  jle     short loc_18001A5C6
0x18001a5bd  movzx   ebx, ax
0x18001a5c0  or      ebx, 80070000h
0x18001a5c6  test    ebx, ebx
0x18001a5c8  jns     loc_18001A547
0x18001a5ce  mov     eax, ebx
0x18001a5d0  mov     rbx, [rsp+28h+arg_0]
0x18001a5d5  mov     rsi, [rsp+28h+arg_10]
0x18001a5da  add     rsp, 20h
0x18001a5de  pop     rdi
0x18001a5df  retn
0x18001a5e0  mov     rsi, [rsp+28h+arg_10]
0x18001a5e5  mov     ebx, 80030100h
0x18001a5ea  mov     eax, ebx
0x18001a5ec  mov     rbx, [rsp+28h+arg_0]
0x18001a5f1  add     rsp, 20h
0x18001a5f5  pop     rdi
0x18001a5f6  retn
0x18001a5f7  mov     rax, [rsi+70h]
0x18001a5fb  mov     dword ptr [rax+4], 1
0x18001a602  mov     rax, [rsi+70h]
0x18001a606  mov     [rax+8], ebx
0x18001a609  jmp     loc_18001A545
```
