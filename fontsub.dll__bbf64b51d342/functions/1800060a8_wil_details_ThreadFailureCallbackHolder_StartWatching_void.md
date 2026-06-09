# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x1800060a8`
- end: `0x180006115`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004004`

## callees

- `0x1800045dc`
- `0x1800060a8`
- `0x180006e78`
- `0x18001abfa`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800060fa`
- `KERNEL32!GetCurrentThreadId` at `0x1800060fa`

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
0x1800060a8  push    rbx
0x1800060aa  sub     rsp, 0C0h
0x1800060b1  cmp     dword ptr [rcx+18h], 0
0x1800060b5  mov     rbx, rcx
0x1800060b8  jz      short loc_1800060D7
0x1800060ba  xor     edx, edx; Val
0x1800060bc  lea     rcx, [rsp+0C8h+var_A8]; void *
0x1800060c1  mov     r8d, 98h; Size
0x1800060c7  call    memset_0
0x1800060cc  lea     rcx, [rsp+0C8h+var_A8]; this
0x1800060d1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800060d7  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800060df  jz      short loc_180006105
0x1800060e1  mov     dl, 1
0x1800060e3  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800060e8  mov     [rbx], rax
0x1800060eb  test    rax, rax
0x1800060ee  jz      short loc_18000610C
0x1800060f0  mov     rcx, [rax]
0x1800060f3  mov     [rbx+10h], rcx
0x1800060f7  mov     [rax], rbx
0x1800060fa  call    cs:__imp_GetCurrentThreadId
0x180006100  mov     [rbx+18h], eax
0x180006103  jmp     short loc_18000610C
0x180006105  mov     qword ptr [rcx], 0
0x18000610c  add     rsp, 0C0h
0x180006113  pop     rbx
0x180006114  retn
```
