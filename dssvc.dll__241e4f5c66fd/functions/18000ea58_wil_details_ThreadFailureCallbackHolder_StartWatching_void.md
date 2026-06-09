# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18000ea58`
- end: `0x18000eac5`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e91c`

## callees

- `0x180004e7c`
- `0x1800069c8`
- `0x18000ea58`
- `0x18001b30a`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eaaa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eaaa`

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
0x18000ea58  push    rbx
0x18000ea5a  sub     rsp, 0C0h
0x18000ea61  cmp     dword ptr [rcx+18h], 0
0x18000ea65  mov     rbx, rcx
0x18000ea68  jz      short loc_18000EA87
0x18000ea6a  xor     edx, edx; Val
0x18000ea6c  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000ea71  mov     r8d, 98h; Size
0x18000ea77  call    memset_0
0x18000ea7c  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000ea81  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000ea87  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000ea8f  jz      short loc_18000EAB5
0x18000ea91  mov     dl, 1
0x18000ea93  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000ea98  mov     [rbx], rax
0x18000ea9b  test    rax, rax
0x18000ea9e  jz      short loc_18000EABC
0x18000eaa0  mov     rcx, [rax]
0x18000eaa3  mov     [rbx+10h], rcx
0x18000eaa7  mov     [rax], rbx
0x18000eaaa  call    cs:__imp_GetCurrentThreadId
0x18000eab0  mov     [rbx+18h], eax
0x18000eab3  jmp     short loc_18000EABC
0x18000eab5  mov     qword ptr [rcx], 0
0x18000eabc  add     rsp, 0C0h
0x18000eac3  pop     rbx
0x18000eac4  retn
```
