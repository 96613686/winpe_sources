# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180014c90`
- end: `0x180014dbe`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `302`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `8`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006a10`
- `0x180014c64`
- `0x180015690`
- `0x18002e908`
- `0x180033d80`
- `0x180034018`
- `0x18004763c`
- `0x180050c1c`

## callees

- `0x180014c90`
- `0x180017430`
- `0x180025eb4`
- `0x18003c870`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014cc4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014d2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014cc4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014d2f`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  __int64 v2; // rdi
  DWORD CurrentThreadId; // esi
  unsigned __int64 v4; // r8
  __int64 v5; // r14
  __int64 i; // rcx
  _QWORD *v7; // rcx
  char *v8; // rax
  signed __int64 v9; // r8
  const struct wil::FailureInfo *v10; // rdx
  signed __int64 v11; // rax
  _BYTE v12[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v12, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v12, v10);
  }
  v2 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
    v5 = 8 * v4;
    for ( i = *(_QWORD *)(8 * v4 + v2); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == CurrentThreadId )
      {
        v7 = (_QWORD *)(i + 16);
        goto LABEL_7;
      }
    }
    v8 = (char *)wil::details::ProcessHeapAlloc(0, 0x18u, v4);
    v9 = (signed __int64)v8;
    if ( v8 )
    {
      *(_DWORD *)v8 = CurrentThreadId;
      v7 = v8 + 16;
      *((_DWORD *)v8 + 1) = 0;
      *((_QWORD *)v8 + 1) = 0;
      *((_QWORD *)v8 + 2) = 0;
      do
      {
        v11 = *(_QWORD *)(v5 + v2);
        *(_QWORD *)(v9 + 8) = v11;
      }
      while ( v11 != _InterlockedCompareExchange64((volatile signed __int64 *)(v5 + v2), v9, v11) );
    }
    else
    {
      v7 = 0;
    }
LABEL_7:
    *(_QWORD *)this = v7;
    if ( v7 )
    {
      *((_QWORD *)this + 2) = *v7;
      *v7 = this;
      *((_DWORD *)this + 6) = GetCurrentThreadId();
    }
  }
  else
  {
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180014c90  mov     rax, rsp
0x180014c93  push    rbx
0x180014c94  sub     rsp, 0C0h
0x180014c9b  cmp     dword ptr [rcx+18h], 0
0x180014c9f  mov     rbx, rcx
0x180014ca2  jnz     loc_180014D77
0x180014ca8  mov     [rax+10h], rdi
0x180014cac  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180014cb3  test    rdi, rdi
0x180014cb6  jz      loc_180014D56
0x180014cbc  mov     [rax+8], rsi
0x180014cc0  mov     [rax+18h], r14
0x180014cc4  call    cs:__imp_GetCurrentThreadId
0x180014ccb  nop     dword ptr [rax+rax+00h]
0x180014cd0  mov     r8d, eax
0x180014cd3  mov     esi, eax
0x180014cd5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180014cdf  shr     r8, 2
0x180014ce3  mul     r8
0x180014ce6  shr     rdx, 3
0x180014cea  lea     rcx, [rdx+rdx*4]
0x180014cee  add     rcx, rcx
0x180014cf1  sub     r8, rcx; unsigned __int64
0x180014cf4  lea     r14, ds:0[r8*8]
0x180014cfc  mov     rcx, [r14+rdi]
0x180014d00  test    rcx, rcx
0x180014d03  jz      short loc_180014D5D
0x180014d05  cmp     [rcx], esi
0x180014d07  jnz     short loc_180014D50
0x180014d09  add     rcx, 10h
0x180014d0d  mov     r14, [rsp+0C8h+arg_10]
0x180014d15  mov     rsi, [rsp+0C8h+arg_0]
0x180014d1d  mov     [rbx], rcx
0x180014d20  test    rcx, rcx
0x180014d23  jz      short loc_180014D3E
0x180014d25  mov     rax, [rcx]
0x180014d28  mov     [rbx+10h], rax
0x180014d2c  mov     [rcx], rbx
0x180014d2f  call    cs:__imp_GetCurrentThreadId
0x180014d36  nop     dword ptr [rax+rax+00h]
0x180014d3b  mov     [rbx+18h], eax
0x180014d3e  mov     rdi, [rsp+0C8h+arg_8]
0x180014d46  add     rsp, 0C0h
0x180014d4d  pop     rbx
0x180014d4e  retn
0x180014d50  mov     rcx, [rcx+8]
0x180014d54  jmp     short loc_180014D00
0x180014d56  xor     edx, edx
0x180014d58  mov     [rcx], rdx
0x180014d5b  jmp     short loc_180014D3E
0x180014d5d  mov     edx, 18h; dwBytes
0x180014d62  xor     ecx, ecx; dwFlags
0x180014d64  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180014d69  mov     r8, rax
0x180014d6c  test    rax, rax
0x180014d6f  jnz     short loc_180014D94
0x180014d71  xor     edx, edx
0x180014d73  mov     ecx, edx
0x180014d75  jmp     short loc_180014D0D
0x180014d77  xor     edx, edx; Val
0x180014d79  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180014d7e  mov     r8d, 98h; Size
0x180014d84  call    memset_0
0x180014d89  lea     rcx, [rsp+0C8h+var_A8]; this
0x180014d8e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180014d94  mov     [rax], esi
0x180014d96  lea     rcx, [r8+10h]
0x180014d9a  xor     eax, eax
0x180014d9c  xor     edx, edx
0x180014d9e  mov     [r8+4], eax
0x180014da2  mov     [r8+8], rdx
0x180014da6  mov     [rcx], rdx
0x180014da9  mov     rax, [r14+rdi]
0x180014dad  mov     [r8+8], rax
0x180014db1  lock cmpxchg [r14+rdi], r8
0x180014db7  jnz     short loc_180014DA9
0x180014db9  jmp     loc_180014D0D
```
