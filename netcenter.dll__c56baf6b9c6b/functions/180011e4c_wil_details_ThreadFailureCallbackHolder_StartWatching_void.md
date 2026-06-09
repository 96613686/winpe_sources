# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180011e4c`
- end: `0x180011eb9`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180011acc`

## callees

- `0x180002c2c`
- `0x18000ac74`
- `0x180011e4c`
- `0x180013208`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011e9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011e9e`

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
0x180011e4c  push    rbx
0x180011e4e  sub     rsp, 0C0h
0x180011e55  cmp     dword ptr [rcx+18h], 0
0x180011e59  mov     rbx, rcx
0x180011e5c  jz      short loc_180011E7B
0x180011e5e  xor     edx, edx; Val
0x180011e60  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180011e65  mov     r8d, 98h; Size
0x180011e6b  call    memset_0
0x180011e70  lea     rcx, [rsp+0C8h+var_A8]; this
0x180011e75  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180011e7b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180011e83  jz      short loc_180011EA9
0x180011e85  mov     dl, 1
0x180011e87  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180011e8c  mov     [rbx], rax
0x180011e8f  test    rax, rax
0x180011e92  jz      short loc_180011EB0
0x180011e94  mov     rcx, [rax]
0x180011e97  mov     [rbx+10h], rcx
0x180011e9b  mov     [rax], rbx
0x180011e9e  call    cs:__imp_GetCurrentThreadId
0x180011ea4  mov     [rbx+18h], eax
0x180011ea7  jmp     short loc_180011EB0
0x180011ea9  mov     qword ptr [rcx], 0
0x180011eb0  add     rsp, 0C0h
0x180011eb7  pop     rbx
0x180011eb8  retn
```
