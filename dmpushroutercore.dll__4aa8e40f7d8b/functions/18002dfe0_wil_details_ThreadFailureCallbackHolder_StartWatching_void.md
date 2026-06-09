# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18002dfe0`
- end: `0x18002e04d`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18002dc14`
- `0x18002dd58`
- `0x18002de9c`

## callees

- `0x1800043a8`
- `0x180009580`
- `0x18000d1c0`
- `0x18002dfe0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e015`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e015`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this,
        __int64 a2)
{
  _QWORD *Local; // rax
  const struct wil::FailureInfo *v4; // rdx
  _BYTE v5[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v5, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v5, v4);
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
0x18002dfe0  push    rbx
0x18002dfe2  sub     rsp, 0C0h
0x18002dfe9  cmp     dword ptr [rcx+18h], 0
0x18002dfed  mov     rbx, rcx
0x18002dff0  jnz     short loc_18002E030
0x18002dff2  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18002dffa  jz      short loc_18002E020
0x18002dffc  mov     dl, 1
0x18002dffe  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18002e003  mov     [rbx], rax
0x18002e006  test    rax, rax
0x18002e009  jz      short loc_18002E027
0x18002e00b  mov     rcx, [rax]
0x18002e00e  mov     [rbx+10h], rcx
0x18002e012  mov     [rax], rbx
0x18002e015  call    cs:__imp_GetCurrentThreadId
0x18002e01b  mov     [rbx+18h], eax
0x18002e01e  jmp     short loc_18002E027
0x18002e020  mov     qword ptr [rcx], 0
0x18002e027  add     rsp, 0C0h
0x18002e02e  pop     rbx
0x18002e02f  retn
0x18002e030  xor     edx, edx; Val
0x18002e032  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18002e037  mov     r8d, 98h; Size
0x18002e03d  call    memset_0
0x18002e042  lea     rcx, [rsp+0C8h+var_A8]; this
0x18002e047  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
