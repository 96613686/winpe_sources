# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x180009150`
- end: `0x1800091bd`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180008858`
- `0x180013648`

## callees

- `0x1800035a0`
- `0x180004efc`
- `0x1800068e8`
- `0x180009150`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800091a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800091a2`

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
0x180009150  push    rbx
0x180009152  sub     rsp, 0C0h
0x180009159  cmp     dword ptr [rcx+18h], 0
0x18000915d  mov     rbx, rcx
0x180009160  jz      short loc_18000917F
0x180009162  xor     edx, edx; Val
0x180009164  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180009169  mov     r8d, 98h; Size
0x18000916f  call    memset_0
0x180009174  lea     rcx, [rsp+0C8h+var_A8]; this
0x180009179  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000917f  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180009187  jz      short loc_1800091AD
0x180009189  mov     dl, 1
0x18000918b  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180009190  mov     [rbx], rax
0x180009193  test    rax, rax
0x180009196  jz      short loc_1800091B4
0x180009198  mov     rcx, [rax]
0x18000919b  mov     [rbx+10h], rcx
0x18000919f  mov     [rax], rbx
0x1800091a2  call    cs:__imp_GetCurrentThreadId
0x1800091a8  mov     [rbx+18h], eax
0x1800091ab  jmp     short loc_1800091B4
0x1800091ad  mov     qword ptr [rcx], 0
0x1800091b4  add     rsp, 0C0h
0x1800091bb  pop     rbx
0x1800091bc  retn
```
