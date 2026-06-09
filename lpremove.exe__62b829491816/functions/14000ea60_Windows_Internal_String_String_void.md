# Windows::Internal::String::~String(void)

- ea: `0x14000ea60`
- end: `0x14000ea77`
- name: `??1String@Internal@Windows@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001065c`

## callees

- `0x14000ea60`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000ea6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000ea6c`

## pseudocode

```c
void __fastcall Windows::Internal::String::~String(HSTRING *this)
{
  HSTRING v1; // rcx

  v1 = *this;
  if ( v1 )
    WindowsDeleteString(v1);
}

```

## disassembly

```asm
0x14000ea60  sub     rsp, 28h
0x14000ea64  mov     rcx, [rcx]; string
0x14000ea67  test    rcx, rcx
0x14000ea6a  jz      short loc_14000EA72
0x14000ea6c  call    cs:__imp_WindowsDeleteString
0x14000ea72  add     rsp, 28h
0x14000ea76  retn
```
