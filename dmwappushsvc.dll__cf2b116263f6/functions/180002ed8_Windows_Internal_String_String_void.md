# Windows::Internal::String::~String(void)

- ea: `0x180002ed8`
- end: `0x180002eef`
- name: `??1String@Internal@Windows@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800030e4`
- `0x18001192b`
- `0x18001193d`

## callees

- `0x180002ed8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002ee4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002ee4`

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
0x180002ed8  sub     rsp, 28h
0x180002edc  mov     rcx, [rcx]; string
0x180002edf  test    rcx, rcx
0x180002ee2  jz      short loc_180002EEA
0x180002ee4  call    cs:__imp_WindowsDeleteString
0x180002eea  add     rsp, 28h
0x180002eee  retn
```
