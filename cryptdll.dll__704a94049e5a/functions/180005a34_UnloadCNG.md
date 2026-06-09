# UnloadCNG

- ea: `0x180005a34`
- end: `0x180005aae`
- name: `UnloadCNG`
- size: `122`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002240`
- `0x1800027a0`
- `0x1800034f0`
- `0x180005658`

## callees

- `0x180005a34`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180005a46`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180005a65`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180005a8e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180005a46`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180005a65`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180005a8e`

## pseudocode

```c
NTSTATUS UnloadCNG()
{
  NTSTATUS result; // eax

  if ( cshRngAlgHandle )
  {
    result = BCryptCloseAlgorithmProvider(cshRngAlgHandle, 0);
    cshRngAlgHandle = 0;
  }
  if ( cshAesAlgHandle )
  {
    result = BCryptCloseAlgorithmProvider(cshAesAlgHandle, 0);
    cshAesAlgHandle = 0;
  }
  LODWORD(cshAesKeyObjectSize) = 0;
  if ( cshHmacShaAlgHandle )
  {
    result = BCryptCloseAlgorithmProvider(cshHmacShaAlgHandle, 0);
    cshHmacShaAlgHandle = 0;
  }
  LODWORD(cshHmacShaObjectSize) = 0;
  return result;
}

```

## disassembly

```asm
0x180005a34  sub     rsp, 28h
0x180005a38  mov     rcx, cs:cshRngAlgHandle; hAlgorithm
0x180005a3f  test    rcx, rcx
0x180005a42  jz      short loc_180005A57
0x180005a44  xor     edx, edx; dwFlags
0x180005a46  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180005a4c  mov     cs:cshRngAlgHandle, 0
0x180005a57  mov     rcx, cs:cshAesAlgHandle; hAlgorithm
0x180005a5e  test    rcx, rcx
0x180005a61  jz      short loc_180005A76
0x180005a63  xor     edx, edx; dwFlags
0x180005a65  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180005a6b  mov     cs:cshAesAlgHandle, 0
0x180005a76  mov     rcx, cs:cshHmacShaAlgHandle; hAlgorithm
0x180005a7d  mov     cs:cshAesKeyObjectSize, 0
0x180005a87  test    rcx, rcx
0x180005a8a  jz      short loc_180005A9F
0x180005a8c  xor     edx, edx; dwFlags
0x180005a8e  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180005a94  mov     cs:cshHmacShaAlgHandle, 0
0x180005a9f  mov     cs:cshHmacShaObjectSize, 0
0x180005aa9  add     rsp, 28h
0x180005aad  retn
```
