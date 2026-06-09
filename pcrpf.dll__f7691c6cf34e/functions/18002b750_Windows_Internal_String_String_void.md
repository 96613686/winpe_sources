# Windows::Internal::String::~String(void)

- ea: `0x18002b750`
- end: `0x18002b76e`
- name: `??1String@Internal@Windows@@QEAA@XZ`
- size: `30`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180057a02`
- `0x180057a14`
- `0x180057b79`
- `0x180057bc1`
- `0x1800584bc`
- `0x18005858b`
- `0x1800585c1`
- `0x18005863f`
- `0x18005877a`
- `0x18005879e`

## callees

- `0x18002b750`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b75c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b75c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18002b750  sub     rsp, 28h
0x18002b754  mov     rcx, [rcx]; string
0x18002b757  test    rcx, rcx
0x18002b75a  jz      short loc_18002B768
0x18002b75c  call    cs:__imp_WindowsDeleteString
0x18002b763  nop     dword ptr [rax+rax+00h]
0x18002b768  add     rsp, 28h
0x18002b76c  retn
```
