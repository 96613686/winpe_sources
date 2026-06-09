# CMediaTypeAttributes::SetMediaAttributes(KSMULTIPLE_ITEM *)

- ea: `0x10021de0`
- end: `0x10021e31`
- name: `?SetMediaAttributes@CMediaTypeAttributes@@UAGJPAUKSMULTIPLE_ITEM@@@Z`
- size: `81`
- prototype: `int __stdcall(CMediaTypeAttributes *__hidden this, struct KSMULTIPLE_ITEM *Src)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x10021de0`
- `0x1003bcf8`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x10021e09`
- `ole32!CoTaskMemAlloc` at `0x10021e09`
- `ole32!CoTaskMemFree` at `0x10021df3`
- `ole32!CoTaskMemFree` at `0x10021df3`

## pseudocode

```c
int __stdcall CMediaTypeAttributes::SetMediaAttributes(LPVOID *this, struct KSMULTIPLE_ITEM *Src)
{
  void *v2; // eax

  if ( this[1] )
  {
    CoTaskMemFree(this[1]);
    this[1] = 0;
  }
  if ( !Src )
    return 0;
  v2 = CoTaskMemAlloc(Src->Size);
  this[1] = v2;
  if ( v2 )
  {
    memcpy(v2, Src, Src->Size);
    return 0;
  }
  return -2147024882;
}

```

## disassembly

```asm
0x10021de0  mov     edi, edi
0x10021de2  push    ebp
0x10021de3  mov     ebp, esp
0x10021de5  push    esi
0x10021de6  push    edi
0x10021de7  mov     edi, [ebp+this]
0x10021dea  cmp     dword ptr [edi+4], 0
0x10021dee  jz      short loc_10021E00
0x10021df0  push    dword ptr [edi+4]; pv
0x10021df3  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10021df9  mov     dword ptr [edi+4], 0
0x10021e00  mov     esi, [ebp+Src]
0x10021e03  test    esi, esi
0x10021e05  jz      short loc_10021E22
0x10021e07  push    dword ptr [esi]; cb
0x10021e09  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10021e0f  mov     [edi+4], eax
0x10021e12  test    eax, eax
0x10021e14  jz      short loc_10021E2A
0x10021e16  push    dword ptr [esi]; Size
0x10021e18  push    esi; Src
0x10021e19  push    eax; void *
0x10021e1a  call    _memcpy
0x10021e1f  add     esp, 0Ch
0x10021e22  xor     eax, eax
0x10021e24  pop     edi
0x10021e25  pop     esi
0x10021e26  pop     ebp
0x10021e27  retn    8
0x10021e2a  mov     eax, 8007000Eh
0x10021e2f  jmp     short loc_10021E24
```
