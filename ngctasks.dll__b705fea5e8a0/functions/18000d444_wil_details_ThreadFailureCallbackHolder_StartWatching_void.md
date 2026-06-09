# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18000d444`
- end: `0x18000d4b1`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d1c4`
- `0x18000d318`

## callees

- `0x180006e9c`
- `0x18000a784`
- `0x18000d444`
- `0x18000e9d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d496`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d496`

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
0x18000d444  push    rbx
0x18000d446  sub     rsp, 0C0h
0x18000d44d  cmp     dword ptr [rcx+18h], 0
0x18000d451  mov     rbx, rcx
0x18000d454  jz      short loc_18000D473
0x18000d456  xor     edx, edx; Val
0x18000d458  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000d45d  mov     r8d, 98h; Size
0x18000d463  call    memset_0
0x18000d468  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000d46d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000d473  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000d47b  jz      short loc_18000D4A1
0x18000d47d  mov     dl, 1
0x18000d47f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000d484  mov     [rbx], rax
0x18000d487  test    rax, rax
0x18000d48a  jz      short loc_18000D4A8
0x18000d48c  mov     rcx, [rax]
0x18000d48f  mov     [rbx+10h], rcx
0x18000d493  mov     [rax], rbx
0x18000d496  call    cs:__imp_GetCurrentThreadId
0x18000d49c  mov     [rbx+18h], eax
0x18000d49f  jmp     short loc_18000D4A8
0x18000d4a1  mov     qword ptr [rcx], 0
0x18000d4a8  add     rsp, 0C0h
0x18000d4af  pop     rbx
0x18000d4b0  retn
```
