# pplx::details::_ExceptionHolder::_RethrowUserException(void)

- ea: `0x1800ef248`
- end: `0x1800ef294`
- name: `?_RethrowUserException@_ExceptionHolder@details@pplx@@QEAAXXZ`
- size: `76`
- prototype: `void __fastcall __noreturn(pplx::details::_ExceptionHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800ef774`
- `0x1801669f4`

## callees

- `0x1800ef248`
- `0x1800f09f0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800ef278`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800ef278`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800ef28d`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800ef28d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn pplx::details::_ExceptionHolder::_RethrowUserException(
        pplx::details::_ExceptionHolder *this)
{
  __int128 v2; // [rsp+20h] [rbp-18h] BYREF

  if ( !(unsigned int)std::_Atomic_storage<long,4>::load(this, 5) )
    _InterlockedExchange((volatile __int32 *)this, 1);
  v2 = 0;
  __ExceptionPtrCopy(&v2, (char *)this + 8);
  __ExceptionPtrRethrow(&v2);
  JUMPOUT(0x1800EF293LL);
}

```

## disassembly

```asm
0x1800ef248  push    rbx
0x1800ef24a  sub     rsp, 30h
0x1800ef24e  mov     rbx, rcx
0x1800ef251  mov     edx, 5
0x1800ef256  call    ?load@?$_Atomic_storage@J$03@std@@QEBAJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::load(std::memory_order)
0x1800ef25b  test    eax, eax
0x1800ef25d  jnz     short loc_1800EF266
0x1800ef25f  mov     eax, 1
0x1800ef264  xchg    eax, [rbx]
0x1800ef266  xorps   xmm0, xmm0
0x1800ef269  movdqu  [rsp+38h+var_18], xmm0
0x1800ef26f  lea     rdx, [rbx+8]
0x1800ef273  lea     rcx, [rsp+38h+var_18]
0x1800ef278  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800ef27e  lea     rax, [rsp+38h+var_18]
0x1800ef283  mov     [rsp+38h+arg_0], rax
0x1800ef288  lea     rcx, [rsp+38h+var_18]
0x1800ef28d  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
```
