# Windows::Internal::String::~String(void)

- ea: `0x18001e314`
- end: `0x18001e32b`
- name: `??1String@Internal@Windows@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(Windows::Internal::String *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ebc8`
- `0x180025cac`

## callees

- `0x18001e314`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e320`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e320`

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
0x18001e314  sub     rsp, 28h
0x18001e318  mov     rcx, [rcx]; string
0x18001e31b  test    rcx, rcx
0x18001e31e  jz      short loc_18001E326
0x18001e320  call    cs:__imp_WindowsDeleteString
0x18001e326  add     rsp, 28h
0x18001e32a  retn
```
