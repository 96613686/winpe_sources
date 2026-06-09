# GetCDPOIDFunctionValue(ushort const *)

- ea: `0x1800127c8`
- end: `0x1800128cf`
- name: `?GetCDPOIDFunctionValue@@YAPEAGPEBG@Z`
- size: `263`
- prototype: `unsigned __int16 *__fastcall(LPCWSTR pwszValueName)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800128d8`

## callees

- `0x180007c00`
- `0x18000a990`
- `0x1800127c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012868`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012868`
- `CRYPT32!CryptGetOIDFunctionValue` at `0x180012814`
- `CRYPT32!CryptGetOIDFunctionValue` at `0x18001289b`
- `CRYPT32!CryptGetOIDFunctionValue` at `0x180012814`
- `CRYPT32!CryptGetOIDFunctionValue` at `0x18001289b`

## string_xrefs

- `0x1800127f1`: `UrlDllGetObjectUrl`
- `0x18001287d`: `UrlDllGetObjectUrl`

## pseudocode

```c
unsigned __int16 *__fastcall GetCDPOIDFunctionValue(LPCWSTR pwszValueName)
{
  _WORD *pbValueData; // rbx
  __int64 v3; // rdi
  DWORD pcbValueData; // [rsp+68h] [rbp+10h] BYREF
  DWORD pdwValueType; // [rsp+70h] [rbp+18h] BYREF

  pbValueData = 0;
  pdwValueType = 0;
  pcbValueData = 0;
  if ( CryptGetOIDFunctionValue(1u, "UrlDllGetObjectUrl", (LPCSTR)2, pwszValueName, &pdwValueType, 0, &pcbValueData) )
  {
    v3 = pcbValueData >> 1;
    if ( pcbValueData >> 1 )
    {
      if ( pdwValueType - 1 <= 1 || pdwValueType == 7 )
      {
        pbValueData = operator new(saturated_mul((unsigned int)(v3 + 2), 2u));
        if ( pbValueData )
        {
          if ( CryptGetOIDFunctionValue(
                 1u,
                 "UrlDllGetObjectUrl",
                 (LPCSTR)2,
                 pwszValueName,
                 &pdwValueType,
                 (BYTE *)pbValueData,
                 &pcbValueData) )
          {
            pbValueData[v3] = 0;
            pbValueData[(unsigned int)(v3 + 1)] = 0;
          }
          else
          {
            operator delete(pbValueData);
            return 0;
          }
        }
        else
        {
          SetLastError(0x8007000E);
        }
      }
    }
  }
  return pbValueData;
}

```

## disassembly

```asm
0x1800127c8  mov     r11, rsp
0x1800127cb  mov     [r11+8], rbx
0x1800127cf  push    rsi
0x1800127d0  push    rdi
0x1800127d1  push    r15
0x1800127d3  sub     rsp, 40h
0x1800127d7  xor     ebx, ebx
0x1800127d9  mov     [rsp+58h+arg_10], 0
0x1800127e1  lea     rax, [r11+10h]
0x1800127e5  mov     [rsp+58h+arg_8], 0
0x1800127ed  mov     [r11-28h], rax
0x1800127f1  lea     rdx, pszFuncName; "UrlDllGetObjectUrl"
0x1800127f8  mov     rsi, rcx
0x1800127fb  mov     [r11-30h], rbx
0x1800127ff  lea     rax, [r11+18h]
0x180012803  mov     r9, rcx; pwszValueName
0x180012806  lea     r15d, [rbx+2]
0x18001280a  mov     [r11-38h], rax
0x18001280e  mov     r8d, r15d; pszOID
0x180012811  lea     ecx, [rbx+1]; dwEncodingType
0x180012814  call    cs:__imp_CryptGetOIDFunctionValue
0x18001281a  test    eax, eax
0x18001281c  jz      loc_1800128BE
0x180012822  mov     edi, [rsp+58h+arg_8]
0x180012826  shr     edi, 1
0x180012828  jz      loc_1800128BE
0x18001282e  mov     ecx, [rsp+58h+arg_10]
0x180012832  lea     eax, [rcx-1]
0x180012835  cmp     eax, 1
0x180012838  jbe     short loc_18001283F
0x18001283a  cmp     ecx, 7
0x18001283d  jnz     short loc_1800128BE
0x18001283f  lea     ecx, [rdi+2]
0x180012842  mov     rax, r15
0x180012845  mul     rcx
0x180012848  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001284f  cmovb   rax, rcx
0x180012853  mov     rcx, rax; uBytes
0x180012856  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001285b  mov     rbx, rax
0x18001285e  test    rax, rax
0x180012861  jnz     short loc_180012870
0x180012863  mov     ecx, 8007000Eh; dwErrCode
0x180012868  call    cs:__imp_SetLastError
0x18001286e  jmp     short loc_1800128BE
0x180012870  lea     rax, [rsp+58h+arg_8]
0x180012875  mov     r9, rsi; pwszValueName
0x180012878  mov     [rsp+58h+pcbValueData], rax; pcbValueData
0x18001287d  lea     rdx, pszFuncName; "UrlDllGetObjectUrl"
0x180012884  lea     rax, [rsp+58h+arg_10]
0x180012889  mov     [rsp+58h+pbValueData], rbx; pbValueData
0x18001288e  mov     r8, r15; pszOID
0x180012891  mov     [rsp+58h+pdwValueType], rax; pdwValueType
0x180012896  mov     ecx, 1; dwEncodingType
0x18001289b  call    cs:__imp_CryptGetOIDFunctionValue
0x1800128a1  test    eax, eax
0x1800128a3  jz      short loc_1800128B4
0x1800128a5  xor     eax, eax
0x1800128a7  lea     ecx, [rdi+1]
0x1800128aa  mov     [rbx+rdi*2], ax
0x1800128ae  mov     [rbx+rcx*2], ax
0x1800128b2  jmp     short loc_1800128BE
0x1800128b4  mov     rcx, rbx; hMem
0x1800128b7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800128bc  xor     ebx, ebx
0x1800128be  mov     rax, rbx
0x1800128c1  mov     rbx, [rsp+58h+arg_0]
0x1800128c6  add     rsp, 40h
0x1800128ca  pop     r15
0x1800128cc  pop     rdi
0x1800128cd  pop     rsi
0x1800128ce  retn
```
