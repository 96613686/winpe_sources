# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180008bb0`
- end: `0x180008c24`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `116`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008b78`

## callees

- `0x180008bb0`
- `0x180008c30`
- `0x18001b4f0`
- `0x1800227f2`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008be5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008be5`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  _QWORD *Local; // rax
  const struct wil::FailureInfo *v3; // rdx
  _BYTE v4[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v4, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v4, v3);
  }
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                        (__int64)this,
                        1);
    *(_QWORD *)this = Local;
    if ( Local )
    {
      *((_QWORD *)this + 2) = *Local;
      *Local = this;
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
0x180008bb0  push    rbx
0x180008bb2  sub     rsp, 0C0h
0x180008bb9  cmp     dword ptr [rcx+18h], 0
0x180008bbd  mov     rbx, rcx
0x180008bc0  jnz     short loc_180008C07
0x180008bc2  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180008bca  jz      short loc_180008BFE
0x180008bcc  mov     dl, 1
0x180008bce  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180008bd3  mov     [rbx], rax
0x180008bd6  test    rax, rax
0x180008bd9  jz      short loc_180008BF4
0x180008bdb  mov     rcx, [rax]
0x180008bde  mov     [rbx+10h], rcx
0x180008be2  mov     [rax], rbx
0x180008be5  call    cs:__imp_GetCurrentThreadId
0x180008bec  nop     dword ptr [rax+rax+00h]
0x180008bf1  mov     [rbx+18h], eax
0x180008bf4  add     rsp, 0C0h
0x180008bfb  pop     rbx
0x180008bfc  retn
0x180008bfe  mov     qword ptr [rcx], 0
0x180008c05  jmp     short loc_180008BF4
0x180008c07  xor     edx, edx; Val
0x180008c09  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180008c0e  mov     r8d, 98h; Size
0x180008c14  call    memset_0
0x180008c19  lea     rcx, [rsp+0C8h+var_A8]; this
0x180008c1e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
