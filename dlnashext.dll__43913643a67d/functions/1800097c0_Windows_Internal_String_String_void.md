# Windows::Internal::String::~String(void)

- ea: `0x1800097c0`
- end: `0x1800097d9`
- name: `??1String@Internal@Windows@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(Windows::Internal::String *__hidden this)`
- caller_count: `48`
- callee_count: `1`
- tags: ``

## callers

- `0x180007b44`
- `0x18000cfd4`
- `0x18000d280`
- `0x18000e2c8`
- `0x18000e9cc`
- `0x1800104d8`
- `0x180018b94`
- `0x18001a8d8`
- `0x18001c744`
- `0x18001cc50`
- `0x18001eff0`
- `0x1800226f4`
- `0x1800234b0`
- `0x180026da0`
- `0x1800270b0`
- `0x180027260`
- `0x18002b708`
- `0x18002c40c`
- `0x18002c61c`
- `0x18002c844`
- `0x18002cc70`
- `0x18002cfb4`
- `0x18002d49c`
- `0x18002e550`
- `0x18002ef70`
- `0x18002f190`
- `0x18002f378`
- `0x18002f430`
- `0x18002f5d0`
- `0x18002f720`
- `0x18002fb7c`
- `0x1800304a8`
- `0x1800334b0`
- `0x1800335a0`
- `0x1800335c0`
- `0x1800335e0`
- `0x180033750`
- `0x180033830`
- `0x180033850`
- `0x180033a10`
- `0x180033bc3`
- `0x180033c2f`
- `0x180033c77`
- `0x180033d86`
- `0x180034187`
- `0x180034279`
- `0x18003428b`
- `0x1800345c6`

## callees

- `0x1800097c0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800097d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800097d1`

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
0x1800097c0  sub     rsp, 28h
0x1800097c4  mov     rcx, [rcx]; string
0x1800097c7  test    rcx, rcx
0x1800097ca  jnz     short loc_1800097D1
0x1800097cc  add     rsp, 28h
0x1800097d0  retn
0x1800097d1  call    cs:__imp_WindowsDeleteString
0x1800097d7  jmp     short loc_1800097CC
```
