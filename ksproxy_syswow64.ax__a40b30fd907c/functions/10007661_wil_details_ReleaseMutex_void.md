# wil::details::ReleaseMutex(void *)

- ea: `0x10007661`
- end: `0x10007689`
- name: `?ReleaseMutex@details@wil@@YGXPAX@Z`
- size: `40`
- prototype: `void __userpurge(wil::details *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1000fa6a`
- `0x1000fbc9`

## callees

- `0x100075eb`
- `0x10007661`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x10007669`
- `KERNEL32!ReleaseMutex` at `0x10007669`

## string_xrefs

- `0x1000767f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __userpurge wil::details::ReleaseMutex(wil::details *this, void *a2)
{
  void *retaddr; // [esp+4h] [ebp+4h]

  if ( !ReleaseMutex(this) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      2581,
      (wil::details::in1diag3 *)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h");
}

```

## disassembly

```asm
0x10007661  mov     edi, edi
0x10007663  push    ebp; void *
0x10007664  mov     ebp, esp
0x10007666  push    [ebp+hMutex]; hMutex
0x10007669  call    ds:__imp__ReleaseMutex@4; ReleaseMutex(x)
0x1000766f  test    eax, eax
0x10007671  jz      short loc_10007677
0x10007673  pop     ebp
0x10007674  retn    4
0x10007677  mov     ecx, [ebp+4]
0x1000767a  mov     edx, 0A15h
0x1000767f  push    offset aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x10007684  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YGXPAXIPBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
