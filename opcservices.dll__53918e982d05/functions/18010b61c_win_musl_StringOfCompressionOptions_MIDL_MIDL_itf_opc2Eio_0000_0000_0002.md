# win_musl::StringOfCompressionOptions(__MIDL___MIDL_itf_opc2Eio_0000_0000_0002)

- ea: `0x18010b61c`
- end: `0x18010b665`
- name: `?StringOfCompressionOptions@win_musl@@YAPEB_WW4__MIDL___MIDL_itf_opc2Eio_0000_0000_0002@@@Z`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001486c`
- `0x180028cf0`

## callees

- `0x18010b61c`

## string_xrefs

- `0x18010b64d`: `CompressionOptions_Maximum`
- `0x18010b645`: `CompressionOptions_Fast`
- `0x18010b65d`: `CompressionOptions_NotCompressed`
- `0x18010b655`: `CompressionOptions_Normal`
- `0x18010b639`: `CompressionOptions_SuperFast`
- `0x18010b632`: `invalid CompressionOption!`

## pseudocode

```c
const wchar_t *__fastcall win_musl::StringOfCompressionOptions(int a1)
{
  const wchar_t *result; // rax

  switch ( a1 )
  {
    case -1:
      return L"CompressionOptions_NotCompressed";
    case 0:
      return L"CompressionOptions_Normal";
    case 1:
      return L"CompressionOptions_Maximum";
    case 2:
      return L"CompressionOptions_Fast";
  }
  result = L"CompressionOptions_SuperFast";
  if ( a1 != 3 )
    return L"invalid CompressionOption!";
  return result;
}

```

## disassembly

```asm
0x18010b61c  cmp     ecx, 0FFFFFFFFh
0x18010b61f  jz      short loc_18010B65D
0x18010b621  test    ecx, ecx
0x18010b623  jz      short loc_18010B655
0x18010b625  cmp     ecx, 1
0x18010b628  jz      short loc_18010B64D
0x18010b62a  cmp     ecx, 2
0x18010b62d  jz      short loc_18010B645
0x18010b62f  cmp     ecx, 3
0x18010b632  lea     rdx, aInvalidCompres; "invalid CompressionOption!"
0x18010b639  lea     rax, aCompressionopt_4; "CompressionOptions_SuperFast"
0x18010b640  cmovnz  rax, rdx
0x18010b644  retn
0x18010b645  lea     rax, aCompressionopt_0; "CompressionOptions_Fast"
0x18010b64c  retn
0x18010b64d  lea     rax, aCompressionopt_5; "CompressionOptions_Maximum"
0x18010b654  retn
0x18010b655  lea     rax, aCompressionopt; "CompressionOptions_Normal"
0x18010b65c  retn
0x18010b65d  lea     rax, aCompressionopt_1; "CompressionOptions_NotCompressed"
0x18010b664  retn
```
