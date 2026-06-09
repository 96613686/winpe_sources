# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18000abe4`
- end: `0x18000ac58`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `116`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `13`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f7cc`
- `0x18000f8f0`
- `0x18000fa40`
- `0x18000fb90`
- `0x18000fc98`
- `0x18000fe54`
- `0x18000ff78`
- `0x1800100c8`
- `0x1800101ec`
- `0x1800102f4`
- `0x180020bc4`
- `0x18002bad0`
- `0x18002bbf4`

## callees

- `0x18000362c`
- `0x180007490`
- `0x18000abe4`
- `0x18000bb0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ac19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ac19`

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
0x18000abe4  push    rbx
0x18000abe6  sub     rsp, 0C0h
0x18000abed  cmp     dword ptr [rcx+18h], 0
0x18000abf1  mov     rbx, rcx
0x18000abf4  jnz     short loc_18000AC3B
0x18000abf6  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000abfe  jz      short loc_18000AC2A
0x18000ac00  mov     dl, 1
0x18000ac02  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000ac07  mov     [rbx], rax
0x18000ac0a  test    rax, rax
0x18000ac0d  jz      short loc_18000AC31
0x18000ac0f  mov     rcx, [rax]
0x18000ac12  mov     [rbx+10h], rcx
0x18000ac16  mov     [rax], rbx
0x18000ac19  call    cs:__imp_GetCurrentThreadId
0x18000ac20  nop     dword ptr [rax+rax+00h]
0x18000ac25  mov     [rbx+18h], eax
0x18000ac28  jmp     short loc_18000AC31
0x18000ac2a  mov     qword ptr [rcx], 0
0x18000ac31  add     rsp, 0C0h
0x18000ac38  pop     rbx
0x18000ac39  retn
0x18000ac3b  xor     edx, edx; Val
0x18000ac3d  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000ac42  mov     r8d, 98h; Size
0x18000ac48  call    memset_0
0x18000ac4d  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000ac52  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
