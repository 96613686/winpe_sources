# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180008f5c`
- end: `0x180008fc9`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180007648`
- `0x180008cbc`

## callees

- `0x18000527c`
- `0x180006798`
- `0x180008f5c`
- `0x180018a52`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008fae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008fae`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this,
        __int64 a2)
{
  const struct wil::FailureInfo *v3; // rdx
  _QWORD *Local; // rax
  _BYTE v5[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v5, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v5, v3);
  }
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(a2) = 1;
    Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                        this,
                        a2);
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
0x180008f5c  push    rbx
0x180008f5e  sub     rsp, 0C0h
0x180008f65  cmp     dword ptr [rcx+18h], 0
0x180008f69  mov     rbx, rcx
0x180008f6c  jz      short loc_180008F8B
0x180008f6e  xor     edx, edx; Val
0x180008f70  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180008f75  mov     r8d, 98h; Size
0x180008f7b  call    memset_0
0x180008f80  lea     rcx, [rsp+0C8h+var_A8]; this
0x180008f85  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180008f8b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180008f93  jz      short loc_180008FB9
0x180008f95  mov     dl, 1
0x180008f97  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180008f9c  mov     [rbx], rax
0x180008f9f  test    rax, rax
0x180008fa2  jz      short loc_180008FC0
0x180008fa4  mov     rcx, [rax]
0x180008fa7  mov     [rbx+10h], rcx
0x180008fab  mov     [rax], rbx
0x180008fae  call    cs:__imp_GetCurrentThreadId
0x180008fb4  mov     [rbx+18h], eax
0x180008fb7  jmp     short loc_180008FC0
0x180008fb9  mov     qword ptr [rcx], 0
0x180008fc0  add     rsp, 0C0h
0x180008fc7  pop     rbx
0x180008fc8  retn
```
