# CW32System::CreateIC(ushort const *,ushort const *,ushort const *,_devicemodeW const *)

- ea: `0x180042f94`
- end: `0x180042fc8`
- name: `?CreateIC@CW32System@@SAPEAUHDC__@@PEBG00PEBU_devicemodeW@@@Z`
- size: `52`
- prototype: `HDC __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const struct _devicemodeW *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b5e0`
- `0x18002bbe0`
- `0x18003ea4c`
- `0x18003f37c`
- `0x180084910`
- `0x180084ee0`

## callees

- `0x180042f94`
- `0x1800900c4`

## import_xrefs

- `GDI32!CreateICA` at `0x180042fb1`
- `GDI32!CreateICW` at `0x180042fa5`

## pseudocode

```c
HDC __fastcall CW32System::CreateIC(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        const struct _devicemodeW *a4)
{
  if ( CW32System::_dwPlatformId == 1 )
    return (HDC)CreateHDCAux(a1, a2, a3, (__int64)CreateICA);
  else
    return CreateICW(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180042f94  sub     rsp, 38h
0x180042f98  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x180042f9f  jz      short loc_180042FB1
0x180042fa1  add     rsp, 38h
0x180042fa5  jmp     cs:__imp_CreateICW
0x180042fb1  mov     rax, cs:__imp_CreateICA
0x180042fb8  mov     [rsp+38h+var_18], rax; __int64
0x180042fbd  call    CreateHDCAux
0x180042fc2  add     rsp, 38h
0x180042fc6  retn
```
