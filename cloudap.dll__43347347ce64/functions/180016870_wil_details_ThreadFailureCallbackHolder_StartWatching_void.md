# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180016870`
- end: `0x180016991`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `289`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180011960`
- `0x180015ff0`
- `0x1800161dc`
- `0x180016844`
- `0x18002c6a0`

## callees

- `0x180016870`
- `0x18003dacc`
- `0x18004317c`
- `0x1800463d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800168a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016915`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800168a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016915`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  __int64 v2; // rsi
  DWORD CurrentThreadId; // ebx
  unsigned __int64 v4; // r8
  __int64 v5; // r14
  __int64 i; // rax
  _QWORD *v7; // rcx
  char *v8; // rax
  signed __int64 v9; // rdx
  signed __int64 v10; // rax
  const struct wil::FailureInfo *v11; // rdx
  _BYTE v12[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v12, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v12, v11);
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
        goto LABEL_8;
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
        v10 = *(_QWORD *)(v5 + v2);
        *(_QWORD *)(v9 + 8) = v10;
      }
      while ( v10 != _InterlockedCompareExchange64((volatile signed __int64 *)(v5 + v2), v9, v10) );
    }
    else
    {
      v7 = 0;
    }
LABEL_8:
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
0x180016870  mov     rax, rsp
0x180016873  push    rdi
0x180016874  sub     rsp, 0C0h
0x18001687b  cmp     dword ptr [rcx+18h], 0
0x18001687f  mov     rdi, rcx
0x180016882  jnz     loc_180016974
0x180016888  mov     [rax+10h], rsi
0x18001688c  mov     rsi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180016893  test    rsi, rsi
0x180016896  jz      loc_180016947
0x18001689c  mov     [rax+8], rbx
0x1800168a0  mov     [rax+18h], r14
0x1800168a4  call    cs:__imp_GetCurrentThreadId
0x1800168aa  mov     r8d, eax
0x1800168ad  mov     ebx, eax
0x1800168af  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800168b9  shr     r8, 2
0x1800168bd  mul     r8
0x1800168c0  shr     rdx, 3
0x1800168c4  lea     rcx, [rdx+rdx*4]
0x1800168c8  add     rcx, rcx
0x1800168cb  sub     r8, rcx; unsigned __int64
0x1800168ce  lea     r14, ds:0[r8*8]
0x1800168d6  mov     rax, [r14+rsi]
0x1800168da  nop     word ptr [rax+rax+00h]
0x1800168e0  test    rax, rax
0x1800168e3  jz      short loc_18001692F
0x1800168e5  cmp     [rax], ebx
0x1800168e7  jz      short loc_1800168EF
0x1800168e9  mov     rax, [rax+8]
0x1800168ed  jmp     short loc_1800168E0
0x1800168ef  lea     rcx, [rax+10h]
0x1800168f3  mov     r14, [rsp+0C8h+arg_10]
0x1800168fb  mov     rbx, [rsp+0C8h+arg_0]
0x180016903  mov     [rdi], rcx
0x180016906  test    rcx, rcx
0x180016909  jz      short loc_18001691E
0x18001690b  mov     rax, [rcx]
0x18001690e  mov     [rdi+10h], rax
0x180016912  mov     [rcx], rdi
0x180016915  call    cs:__imp_GetCurrentThreadId
0x18001691b  mov     [rdi+18h], eax
0x18001691e  mov     rsi, [rsp+0C8h+arg_8]
0x180016926  add     rsp, 0C0h
0x18001692d  pop     rdi
0x18001692e  retn
0x18001692f  mov     edx, 18h; dwBytes
0x180016934  xor     ecx, ecx; dwFlags
0x180016936  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001693b  mov     rdx, rax
0x18001693e  test    rax, rax
0x180016941  jnz     short loc_180016950
0x180016943  xor     ecx, ecx
0x180016945  jmp     short loc_1800168F3
0x180016947  mov     qword ptr [rcx], 0
0x18001694e  jmp     short loc_18001691E
0x180016950  mov     [rax], ebx
0x180016952  lea     rcx, [rdx+10h]
0x180016956  xor     eax, eax
0x180016958  mov     [rdx+4], eax
0x18001695b  mov     [rdx+8], rax
0x18001695f  mov     [rcx], rax
0x180016962  mov     rax, [r14+rsi]
0x180016966  mov     [rdx+8], rax
0x18001696a  lock cmpxchg [r14+rsi], rdx
0x180016970  jz      short loc_1800168F3
0x180016972  jmp     short loc_180016962
0x180016974  xor     edx, edx; Val
0x180016976  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18001697b  mov     r8d, 98h; Size
0x180016981  call    memset_0
0x180016986  lea     rcx, [rsp+0C8h+var_A8]; this
0x18001698b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
