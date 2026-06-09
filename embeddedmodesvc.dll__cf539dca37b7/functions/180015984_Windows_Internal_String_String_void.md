# Windows::Internal::String::~String(void)

- ea: `0x180015984`
- end: `0x18001599b`
- name: `??1String@Internal@Windows@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180015e98`
- `0x180019cd0`
- `0x180019d18`
- `0x180019d2a`

## callees

- `0x180015984`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015990`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015990`

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
0x180015984  sub     rsp, 28h
0x180015988  mov     rcx, [rcx]; string
0x18001598b  test    rcx, rcx
0x18001598e  jz      short loc_180015996
0x180015990  call    cs:__imp_WindowsDeleteString
0x180015996  add     rsp, 28h
0x18001599a  retn
```
