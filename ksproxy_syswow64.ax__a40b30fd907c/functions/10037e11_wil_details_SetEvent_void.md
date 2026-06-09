# wil::details::SetEvent(void *)

- ea: `0x10037e11`
- end: `0x10037e3b`
- name: `?SetEvent@details@wil@@YGXPAX@Z`
- size: `42`
- prototype: `void __stdcall(HANDLE hEvent, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x10037ad5`
- `0x10038369`
- `0x100383b7`

## callees

- `0x100075eb`
- `0x10037e11`

## import_xrefs

- `KERNEL32!SetEvent` at `0x10037e1a`
- `KERNEL32!SetEvent` at `0x10037e1a`

## string_xrefs

- `0x10037e31`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
void __stdcall wil::details::SetEvent(HANDLE hEvent, void *a2)
{
  void *retaddr; // [esp+4h] [ebp+4h]

  if ( !SetEvent(hEvent) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      2561,
      (wil::details::in1diag3 *)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h");
}

```

## disassembly

```asm
0x10037e11  mov     edi, edi
0x10037e13  push    ebp; unsigned int
0x10037e14  mov     ebp, esp
0x10037e16  push    ecx; void *
0x10037e17  push    [ebp+hEvent]; hEvent
0x10037e1a  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10037e20  test    eax, eax
0x10037e22  jz      short loc_10037E29
0x10037e24  pop     ecx
0x10037e25  pop     ebp
0x10037e26  retn    4
0x10037e29  mov     ecx, [ebp+4]
0x10037e2c  mov     edx, 0A01h
0x10037e31  push    offset aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x10037e36  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YGXPAXIPBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
