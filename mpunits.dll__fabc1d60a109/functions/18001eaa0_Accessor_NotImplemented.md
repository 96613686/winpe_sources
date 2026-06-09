# Accessor_NotImplemented

- ea: `0x18001eaa0`
- end: `0x18001eabb`
- name: `Accessor_NotImplemented`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001eaab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001eaab`

## string_xrefs

- `0x18001eaa4`: `Error, Accessor_NotImplemented, file:admin\wmi\winomi\mp\etw\level2.c, line:__LINE__`

## pseudocode

```c
__int64 Accessor_NotImplemented()
{
  OutputDebugStringW(L"Error, Accessor_NotImplemented, file:admin\\wmi\\winomi\\mp\\etw\\level2.c, line:__LINE__");
  return 7;
}

```

## disassembly

```asm
0x18001eaa0  sub     rsp, 28h
0x18001eaa4  lea     rcx, OutputString; "Error, Accessor_NotImplemented, file:ad"...
0x18001eaab  call    cs:__imp_OutputDebugStringW
0x18001eab1  mov     eax, 7
0x18001eab6  add     rsp, 28h
0x18001eaba  retn
```
