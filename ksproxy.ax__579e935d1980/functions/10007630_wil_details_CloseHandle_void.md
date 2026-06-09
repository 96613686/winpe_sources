# wil::details::CloseHandle(void *)

- ea: `0x10007630`
- end: `0x1000765a`
- name: `?CloseHandle@details@wil@@YGXPAX@Z`
- size: `42`
- prototype: `void __stdcall(HANDLE hObject, void *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x10007aee`
- `0x10008c1d`
- `0x1000f6d4`
- `0x1000fa6a`
- `0x1000fc76`
- `0x1000fca1`
- `0x100379d7`
- `0x100380b7`

## callees

- `0x100075eb`
- `0x10007630`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x10007639`
- `KERNEL32!CloseHandle` at `0x10007639`

## string_xrefs

- `0x10007650`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c

```

## disassembly

```asm
0x10007630  mov     edi, edi
0x10007632  push    ebp; unsigned int
0x10007633  mov     ebp, esp
0x10007635  push    ecx; void *
0x10007636  push    [ebp+hObject]; hObject
0x10007639  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1000763f  test    eax, eax
0x10007641  jz      short loc_10007648
0x10007643  pop     ecx
0x10007644  pop     ebp
0x10007645  retn    4
0x10007648  mov     ecx, [ebp+4]
0x1000764b  mov     edx, 0A0Bh
0x10007650  push    offset aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x10007655  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YGXPAXIPBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
