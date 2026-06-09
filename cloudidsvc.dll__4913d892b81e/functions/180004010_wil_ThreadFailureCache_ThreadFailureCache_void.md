# wil::ThreadFailureCache::ThreadFailureCache(void)

- ea: `0x180004010`
- end: `0x1800040b5`
- name: `??0ThreadFailureCache@wil@@QEAA@XZ`
- size: `165`
- prototype: `wil::ThreadFailureCache *__fastcall(wil::ThreadFailureCache *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003eac`

## callees

- `0x1800024f0`
- `0x180004010`
- `0x1800059fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000409e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000409e`

## pseudocode

```c
wil::ThreadFailureCache *__fastcall wil::ThreadFailureCache::ThreadFailureCache(wil::ThreadFailureCache *this)
{
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // rcx
  _QWORD *v5; // rbx
  _QWORD *Local; // rax

  *(_QWORD *)this = &wil::ThreadFailureCache::`vftable';
  v2 = (_QWORD *)((char *)this + 8);
  v2[19] = 0;
  v2[20] = 0;
  memset_0(v2, 0, 0x98u);
  v5 = (_QWORD *)((char *)this + 176);
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = this;
  *((_QWORD *)this + 24) = 0;
  *((_DWORD *)this + 50) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_BYTE *)this + 216) = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(v3) = 1;
    Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                        v4,
                        v3);
    *v5 = Local;
    if ( Local )
    {
      *((_QWORD *)this + 24) = *Local;
      *Local = v5;
      *((_DWORD *)this + 50) = GetCurrentThreadId();
    }
  }
  return this;
}

```

## disassembly

```asm
0x180004010  mov     [rsp+arg_0], rbx
0x180004015  push    rdi
0x180004016  sub     rsp, 20h
0x18000401a  mov     rdi, rcx
0x18000401d  lea     rax, ??_7ThreadFailureCache@wil@@6B@; const wil::ThreadFailureCache::`vftable'
0x180004024  mov     [rcx], rax
0x180004027  add     rcx, 8; void *
0x18000402b  mov     qword ptr [rcx+98h], 0
0x180004036  mov     qword ptr [rcx+0A0h], 0
0x180004041  xor     edx, edx; Val
0x180004043  mov     r8d, 98h; Size
0x180004049  call    memset_0
0x18000404e  lea     rbx, [rdi+0B0h]
0x180004055  mov     qword ptr [rbx], 0
0x18000405c  mov     [rbx+8], rdi
0x180004060  mov     qword ptr [rbx+10h], 0
0x180004068  mov     dword ptr [rbx+18h], 0
0x18000406f  mov     qword ptr [rbx+20h], 0
0x180004077  mov     byte ptr [rbx+28h], 0
0x18000407b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004083  jz      short loc_1800040A7
0x180004085  mov     dl, 1
0x180004087  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000408c  mov     [rbx], rax
0x18000408f  test    rax, rax
0x180004092  jz      short loc_1800040A7
0x180004094  mov     rcx, [rax]
0x180004097  mov     [rbx+10h], rcx
0x18000409b  mov     [rax], rbx
0x18000409e  call    cs:__imp_GetCurrentThreadId
0x1800040a4  mov     [rbx+18h], eax
0x1800040a7  mov     rax, rdi
0x1800040aa  mov     rbx, [rsp+28h+arg_0]
0x1800040af  add     rsp, 20h
0x1800040b3  pop     rdi
0x1800040b4  retn
```
