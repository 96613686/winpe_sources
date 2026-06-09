# wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)

- ea: `0x18001e3c0`
- end: `0x18001e4a6`
- name: `??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z`
- size: `230`
- prototype: `wil::details::ThreadFailureCallbackHolder *__fastcall(wil::details::ThreadFailureCallbackHolder *this, struct wil::details::IFailureCallback *, struct wil::CallContextInfo *, char)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001e308`
- `0x18002fc50`
- `0x180030a54`
- `0x1800335c4`
- `0x1800337dc`
- `0x180033898`
- `0x1800431d0`
- `0x180049e7c`
- `0x180049f34`
- `0x18004c958`

## callees

- `0x18001e3c0`
- `0x18001e4ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e3f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e44c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e3f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e44c`

## pseudocode

```c
wil::details::ThreadFailureCallbackHolder *__fastcall wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
        wil::details::ThreadFailureCallbackHolder *this,
        struct wil::details::IFailureCallback *a2,
        struct wil::CallContextInfo *a3,
        char a4)
{
  __int64 v5; // rsi
  DWORD CurrentThreadId; // edi
  unsigned __int64 v7; // r8
  __int64 v8; // r14
  __int64 i; // rax
  _QWORD *v10; // rcx
  char *v12; // rax
  signed __int64 v13; // rdx
  signed __int64 v14; // rax

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = a2;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = a3;
  *((_BYTE *)this + 40) = 0;
  if ( a4 )
  {
    v5 = wil::details::g_pThreadFailureCallbacks;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      CurrentThreadId = GetCurrentThreadId();
      v7 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
      v8 = 8 * v7;
      for ( i = *(_QWORD *)(8 * v7 + v5); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          v10 = (_QWORD *)(i + 16);
          goto LABEL_7;
        }
      }
      v12 = (char *)wil::details::ProcessHeapAlloc(0, 0x18u, v7);
      v13 = (signed __int64)v12;
      if ( v12 )
      {
        *(_DWORD *)v12 = CurrentThreadId;
        *((_DWORD *)v12 + 1) = 0;
        *((_QWORD *)v12 + 1) = 0;
        v10 = v12 + 16;
        *((_QWORD *)v12 + 2) = 0;
        do
        {
          v14 = *(_QWORD *)(v8 + v5);
          *(_QWORD *)(v13 + 8) = v14;
        }
        while ( v14 != _InterlockedCompareExchange64((volatile signed __int64 *)(v8 + v5), v13, v14) );
      }
      else
      {
        v10 = 0;
      }
LABEL_7:
      *(_QWORD *)this = v10;
      if ( v10 )
      {
        *((_QWORD *)this + 2) = *v10;
        *v10 = this;
        *((_DWORD *)this + 6) = GetCurrentThreadId();
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x18001e3c0  push    rbx
0x18001e3c2  push    rbp
0x18001e3c3  push    rsi
0x18001e3c4  push    rdi
0x18001e3c5  push    r14
0x18001e3c7  sub     rsp, 20h
0x18001e3cb  mov     rbx, rcx
0x18001e3ce  xor     ebp, ebp
0x18001e3d0  mov     [rcx], rbp
0x18001e3d3  mov     [rcx+8], rdx
0x18001e3d7  mov     [rcx+10h], rbp
0x18001e3db  mov     [rcx+18h], ebp
0x18001e3de  mov     [rcx+20h], r8
0x18001e3e2  mov     [rcx+28h], bpl
0x18001e3e6  test    r9b, r9b
0x18001e3e9  jz      short loc_18001E455
0x18001e3eb  mov     rsi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001e3f2  test    rsi, rsi
0x18001e3f5  jz      short loc_18001E455
0x18001e3f7  call    cs:__imp_GetCurrentThreadId
0x18001e3fd  mov     edi, eax
0x18001e3ff  mov     r8d, eax
0x18001e402  shr     r8, 2
0x18001e406  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001e410  mul     r8
0x18001e413  shr     rdx, 3
0x18001e417  lea     rcx, [rdx+rdx*4]
0x18001e41b  add     rcx, rcx
0x18001e41e  sub     r8, rcx; unsigned __int64
0x18001e421  lea     r14, ds:0[r8*8]
0x18001e429  mov     rax, [r14+rsi]
0x18001e42d  test    rax, rax
0x18001e430  jz      short loc_18001E469
0x18001e432  cmp     [rax], edi
0x18001e434  jnz     short loc_18001E463
0x18001e436  lea     rcx, [rax+10h]
0x18001e43a  mov     [rbx], rcx
0x18001e43d  test    rcx, rcx
0x18001e440  jz      short loc_18001E455
0x18001e442  mov     rax, [rcx]
0x18001e445  mov     [rbx+10h], rax
0x18001e449  mov     [rcx], rbx
0x18001e44c  call    cs:__imp_GetCurrentThreadId
0x18001e452  mov     [rbx+18h], eax
0x18001e455  mov     rax, rbx
0x18001e458  add     rsp, 20h
0x18001e45c  pop     r14
0x18001e45e  pop     rdi
0x18001e45f  pop     rsi
0x18001e460  pop     rbp
0x18001e461  pop     rbx
0x18001e462  retn
0x18001e463  mov     rax, [rax+8]
0x18001e467  jmp     short loc_18001E42D
0x18001e469  mov     edx, 18h; dwBytes
0x18001e46e  xor     ecx, ecx; dwFlags
0x18001e470  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001e475  mov     rdx, rax
0x18001e478  test    rax, rax
0x18001e47b  jnz     short loc_18001E482
0x18001e47d  mov     rcx, rbp
0x18001e480  jmp     short loc_18001E43A
0x18001e482  mov     [rax], edi
0x18001e484  xor     eax, eax
0x18001e486  mov     [rdx+4], eax
0x18001e489  mov     [rdx+8], rbp
0x18001e48d  lea     rcx, [rdx+10h]
0x18001e491  mov     [rcx], rbp
0x18001e494  mov     rax, [r14+rsi]
0x18001e498  mov     [rdx+8], rax
0x18001e49c  lock cmpxchg [r14+rsi], rdx
0x18001e4a2  jnz     short loc_18001E494
0x18001e4a4  jmp     short loc_18001E43A
```
