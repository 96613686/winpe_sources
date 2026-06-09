# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180011488`
- end: `0x1800114f5`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ff98`

## callees

- `0x180002f40`
- `0x180005fec`
- `0x180009738`
- `0x180011488`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800114da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800114da`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  const struct wil::FailureInfo *v2; // rdx
  _QWORD *Local; // rax
  _BYTE v4[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v4, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v4, v2);
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
0x180011488  push    rbx
0x18001148a  sub     rsp, 0C0h
0x180011491  cmp     dword ptr [rcx+18h], 0
0x180011495  mov     rbx, rcx
0x180011498  jz      short loc_1800114B7
0x18001149a  xor     edx, edx; Val
0x18001149c  lea     rcx, [rsp+0C8h+var_A8]; void *
0x1800114a1  mov     r8d, 98h; Size
0x1800114a7  call    memset_0
0x1800114ac  lea     rcx, [rsp+0C8h+var_A8]; this
0x1800114b1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800114b7  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800114bf  jz      short loc_1800114E5
0x1800114c1  mov     dl, 1
0x1800114c3  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800114c8  mov     [rbx], rax
0x1800114cb  test    rax, rax
0x1800114ce  jz      short loc_1800114EC
0x1800114d0  mov     rcx, [rax]
0x1800114d3  mov     [rbx+10h], rcx
0x1800114d7  mov     [rax], rbx
0x1800114da  call    cs:__imp_GetCurrentThreadId
0x1800114e0  mov     [rbx+18h], eax
0x1800114e3  jmp     short loc_1800114EC
0x1800114e5  mov     qword ptr [rcx], 0
0x1800114ec  add     rsp, 0C0h
0x1800114f3  pop     rbx
0x1800114f4  retn
```
