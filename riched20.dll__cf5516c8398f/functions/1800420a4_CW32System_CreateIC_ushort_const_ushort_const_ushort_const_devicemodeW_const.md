# CW32System::CreateIC(ushort const *,ushort const *,ushort const *,_devicemodeW const *)

- ea: `0x1800420a4`
- end: `0x1800420d2`
- name: `?CreateIC@CW32System@@SAPEAUHDC__@@PEBG00PEBU_devicemodeW@@@Z`
- size: `46`
- prototype: `HDC __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const struct _devicemodeW *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b440`
- `0x180031010`
- `0x18003dea4`
- `0x18003e7c8`
- `0x180082420`
- `0x1800829c0`

## callees

- `0x1800420a4`
- `0x18008d8c4`

## import_xrefs

- `GDI32!CreateICA` at `0x1800420bc`
- `GDI32!CreateICW` at `0x1800420b5`

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
0x1800420a4  sub     rsp, 38h
0x1800420a8  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x1800420af  jz      short loc_1800420BC
0x1800420b1  add     rsp, 38h
0x1800420b5  jmp     cs:__imp_CreateICW
0x1800420bc  mov     rax, cs:__imp_CreateICA
0x1800420c3  mov     [rsp+38h+var_18], rax; __int64
0x1800420c8  call    CreateHDCAux
0x1800420cd  add     rsp, 38h
0x1800420d1  retn
```
