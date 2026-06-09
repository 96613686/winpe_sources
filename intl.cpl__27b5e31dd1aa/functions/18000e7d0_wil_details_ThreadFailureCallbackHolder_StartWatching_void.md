# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18000e7d0`
- end: `0x18000e83d`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000cf70`

## callees

- `0x180004efc`
- `0x1800066e8`
- `0x18000e7d0`
- `0x18002a112`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e822`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e822`

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
0x18000e7d0  push    rbx
0x18000e7d2  sub     rsp, 0C0h
0x18000e7d9  cmp     dword ptr [rcx+18h], 0
0x18000e7dd  mov     rbx, rcx
0x18000e7e0  jz      short loc_18000E7FF
0x18000e7e2  xor     edx, edx; Val
0x18000e7e4  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000e7e9  mov     r8d, 98h; Size
0x18000e7ef  call    memset_0
0x18000e7f4  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000e7f9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000e7ff  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000e807  jz      short loc_18000E82D
0x18000e809  mov     dl, 1
0x18000e80b  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000e810  mov     [rbx], rax
0x18000e813  test    rax, rax
0x18000e816  jz      short loc_18000E834
0x18000e818  mov     rcx, [rax]
0x18000e81b  mov     [rbx+10h], rcx
0x18000e81f  mov     [rax], rbx
0x18000e822  call    cs:__imp_GetCurrentThreadId
0x18000e828  mov     [rbx+18h], eax
0x18000e82b  jmp     short loc_18000E834
0x18000e82d  mov     qword ptr [rcx], 0
0x18000e834  add     rsp, 0C0h
0x18000e83b  pop     rbx
0x18000e83c  retn
```
