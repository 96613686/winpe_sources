# IsLicensedComponentAAC(void)

- ea: `0x180010b80`
- end: `0x180010bff`
- name: `?IsLicensedComponentAAC@@YAHXZ`
- size: `127`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010c10`

## callees

- `0x180010b80`
- `0x180067160`

## pseudocode

```c
_BOOL8 IsLicensedComponentAAC(void)
{
  _BOOL8 result; // rax
  DWORD pdwValue; // [rsp+30h] [rbp+8h] BYREF

  pdwValue = 0;
  result = 1;
  if ( SLGetWindowsInformationDWORD(L"msmpeg2adec-AACDecoderV2InSKU", &pdwValue) || !pdwValue )
  {
    pdwValue = 0;
    if ( SLGetWindowsInformationDWORD(L"msmpeg2adec-AACDecoderV2AddInEnable", &pdwValue) )
      return 0;
    if ( !pdwValue )
      return 0;
    pdwValue = 0;
    if ( SLGetWindowsInformationDWORD(L"msmpeg2adec-AACDecoderV2AddIn", &pdwValue) || !pdwValue )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180010b80  sub     rsp, 28h
0x180010b84  lea     rdx, [rsp+28h+pdwValue]; pdwValue
0x180010b89  mov     [rsp+28h+pdwValue], 0
0x180010b91  lea     rcx, pwszValueName; "msmpeg2adec-AACDecoderV2InSKU"
0x180010b98  call    SLGetWindowsInformationDWORD
0x180010b9d  test    eax, eax
0x180010b9f  jnz     short loc_180010BA8
0x180010ba1  cmp     [rsp+28h+pdwValue], 1
0x180010ba6  jnb     short loc_180010BEC
0x180010ba8  lea     rdx, [rsp+28h+pdwValue]; pdwValue
0x180010bad  mov     [rsp+28h+pdwValue], 0
0x180010bb5  lea     rcx, aMsmpeg2adecAac_0; "msmpeg2adec-AACDecoderV2AddInEnable"
0x180010bbc  call    SLGetWindowsInformationDWORD
0x180010bc1  test    eax, eax
0x180010bc3  jnz     short loc_180010BF7
0x180010bc5  cmp     [rsp+28h+pdwValue], 1
0x180010bca  jb      short loc_180010BF7
0x180010bcc  lea     rdx, [rsp+28h+pdwValue]; pdwValue
0x180010bd1  mov     [rsp+28h+pdwValue], eax
0x180010bd5  lea     rcx, aMsmpeg2adecAac_1; "msmpeg2adec-AACDecoderV2AddIn"
0x180010bdc  call    SLGetWindowsInformationDWORD
0x180010be1  test    eax, eax
0x180010be3  jnz     short loc_180010BF7
0x180010be5  cmp     [rsp+28h+pdwValue], 1
0x180010bea  jb      short loc_180010BF7
0x180010bec  mov     eax, 1
0x180010bf1  add     rsp, 28h
0x180010bf5  retn
0x180010bf7  xor     eax, eax
0x180010bf9  add     rsp, 28h
0x180010bfd  retn
```
