# wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)

- ea: `0x1800177c0`
- end: `0x1800178b3`
- name: `??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z`
- size: `243`
- prototype: `__int64 __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this, struct wil::details::IFailureCallback *, struct wil::CallContextInfo *, bool)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018430`
- `0x18002ea20`
- `0x18002ef18`
- `0x180033cc0`
- `0x180033e98`
- `0x180033f58`
- `0x180044c44`
- `0x18004c390`
- `0x18004c448`
- `0x18004f97c`

## callees

- `0x180017430`
- `0x1800177c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800177f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017852`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800177f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017852`

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
0x1800177c0  push    rbx
0x1800177c2  push    rbp
0x1800177c3  push    rsi
0x1800177c4  push    rdi
0x1800177c5  push    r14
0x1800177c7  sub     rsp, 20h
0x1800177cb  mov     rbx, rcx
0x1800177ce  xor     ebp, ebp
0x1800177d0  mov     [rcx], rbp
0x1800177d3  mov     [rcx+8], rdx
0x1800177d7  mov     [rcx+10h], rbp
0x1800177db  mov     [rcx+18h], ebp
0x1800177de  mov     [rcx+20h], r8
0x1800177e2  mov     [rcx+28h], bpl
0x1800177e6  test    r9b, r9b
0x1800177e9  jz      short loc_180017861
0x1800177eb  mov     rsi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800177f2  test    rsi, rsi
0x1800177f5  jz      short loc_180017861
0x1800177f7  call    cs:__imp_GetCurrentThreadId
0x1800177fe  nop     dword ptr [rax+rax+00h]
0x180017803  mov     edi, eax
0x180017805  mov     r8d, eax
0x180017808  shr     r8, 2
0x18001780c  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180017816  mul     r8
0x180017819  shr     rdx, 3
0x18001781d  lea     rcx, [rdx+rdx*4]
0x180017821  add     rcx, rcx
0x180017824  sub     r8, rcx; unsigned __int64
0x180017827  lea     r14, ds:0[r8*8]
0x18001782f  mov     rax, [r14+rsi]
0x180017833  test    rax, rax
0x180017836  jz      short loc_180017876
0x180017838  cmp     [rax], edi
0x18001783a  jnz     short loc_180017870
0x18001783c  lea     rcx, [rax+10h]
0x180017840  mov     [rbx], rcx
0x180017843  test    rcx, rcx
0x180017846  jz      short loc_180017861
0x180017848  mov     rax, [rcx]
0x18001784b  mov     [rbx+10h], rax
0x18001784f  mov     [rcx], rbx
0x180017852  call    cs:__imp_GetCurrentThreadId
0x180017859  nop     dword ptr [rax+rax+00h]
0x18001785e  mov     [rbx+18h], eax
0x180017861  mov     rax, rbx
0x180017864  add     rsp, 20h
0x180017868  pop     r14
0x18001786a  pop     rdi
0x18001786b  pop     rsi
0x18001786c  pop     rbp
0x18001786d  pop     rbx
0x18001786e  retn
0x180017870  mov     rax, [rax+8]
0x180017874  jmp     short loc_180017833
0x180017876  mov     edx, 18h; dwBytes
0x18001787b  xor     ecx, ecx; dwFlags
0x18001787d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180017882  mov     rdx, rax
0x180017885  test    rax, rax
0x180017888  jnz     short loc_18001788F
0x18001788a  mov     rcx, rbp
0x18001788d  jmp     short loc_180017840
0x18001788f  mov     [rax], edi
0x180017891  xor     eax, eax
0x180017893  mov     [rdx+4], eax
0x180017896  mov     [rdx+8], rbp
0x18001789a  lea     rcx, [rdx+10h]
0x18001789e  mov     [rcx], rbp
0x1800178a1  mov     rax, [r14+rsi]
0x1800178a5  mov     [rdx+8], rax
0x1800178a9  lock cmpxchg [r14+rsi], rdx
0x1800178af  jnz     short loc_1800178A1
0x1800178b1  jmp     short loc_180017840
```
