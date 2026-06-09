# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180018e0c`
- end: `0x180018e79`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `11`
- callee_count: `4`
- tags: ``

## callers

- `0x180017f68`
- `0x1800180ac`
- `0x1800181f4`
- `0x18001833c`
- `0x1800184b4`
- `0x18001862c`
- `0x1800187a4`
- `0x180018944`
- `0x180018abc`
- `0x180018bc0`
- `0x180018cc4`

## callees

- `0x180006340`
- `0x1800083c0`
- `0x180018e0c`
- `0x180033e9a`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018e41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018e41`

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
0x180018e0c  push    rbx
0x180018e0e  sub     rsp, 0C0h
0x180018e15  cmp     dword ptr [rcx+18h], 0
0x180018e19  mov     rbx, rcx
0x180018e1c  jnz     short loc_180018E5C
0x180018e1e  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180018e26  jz      short loc_180018E4C
0x180018e28  mov     dl, 1
0x180018e2a  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180018e2f  mov     [rbx], rax
0x180018e32  test    rax, rax
0x180018e35  jz      short loc_180018E53
0x180018e37  mov     rcx, [rax]
0x180018e3a  mov     [rbx+10h], rcx
0x180018e3e  mov     [rax], rbx
0x180018e41  call    cs:__imp_GetCurrentThreadId
0x180018e47  mov     [rbx+18h], eax
0x180018e4a  jmp     short loc_180018E53
0x180018e4c  mov     qword ptr [rcx], 0
0x180018e53  add     rsp, 0C0h
0x180018e5a  pop     rbx
0x180018e5b  retn
0x180018e5c  xor     edx, edx; Val
0x180018e5e  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180018e63  mov     r8d, 98h; Size
0x180018e69  call    memset_0
0x180018e6e  lea     rcx, [rsp+0C8h+var_A8]; this
0x180018e73  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
