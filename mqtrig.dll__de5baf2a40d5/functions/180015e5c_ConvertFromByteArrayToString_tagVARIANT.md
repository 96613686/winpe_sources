# ConvertFromByteArrayToString(tagVARIANT *)

- ea: `0x180015e5c`
- end: `0x180015f32`
- name: `?ConvertFromByteArrayToString@@YAJPEAUtagVARIANT@@@Z`
- size: `214`
- prototype: `__int64 __fastcall(VARIANTARG *pvarg)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006ef0`

## callees

- `0x180015e5c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180015ed4`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180015ed4`
- `OLEAUT32!__imp_SysFreeString` at `0x180015f22`
- `OLEAUT32!__imp_SysFreeString` at `0x180015f22`
- `OLEAUT32!__imp_VariantClear` at `0x180015f03`
- `OLEAUT32!__imp_VariantClear` at `0x180015f03`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180015eb7`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180015eb7`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180015e9f`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180015e9f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180015e79`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180015e79`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180015ef4`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180015ef4`

## pseudocode

```c
__int64 __fastcall ConvertFromByteArrayToString(VARIANTARG *pvarg)
{
  HRESULT LBound; // ebx
  SAFEARRAY *parray; // rcx
  OLECHAR *v4; // rsi
  LONG plUbound; // [rsp+40h] [rbp+8h] BYREF
  LONG plLbound; // [rsp+48h] [rbp+10h] BYREF
  void *ppvData; // [rsp+50h] [rbp+18h] BYREF

  ppvData = 0;
  LBound = SafeArrayAccessData(pvarg->parray, &ppvData);
  if ( LBound >= 0 )
  {
    parray = pvarg->parray;
    v4 = 0;
    plLbound = 0;
    plUbound = 0;
    LBound = SafeArrayGetLBound(parray, 1u, &plLbound);
    if ( LBound >= 0 )
    {
      LBound = SafeArrayGetUBound(pvarg->parray, 1u, &plUbound);
      if ( LBound >= 0 )
      {
        v4 = SysAllocStringLen((const OLECHAR *)ppvData, (unsigned int)(plUbound - plLbound + 1) >> 1);
        if ( !v4 )
          LBound = -2147467259;
      }
    }
    if ( ppvData )
      LBound = SafeArrayUnaccessData(pvarg->parray);
    if ( LBound < 0 || (LBound = VariantClear(pvarg), LBound < 0) )
    {
      if ( v4 )
        SysFreeString(v4);
    }
    else
    {
      pvarg->vt = 8;
      pvarg->llVal = (LONGLONG)v4;
    }
  }
  return (unsigned int)LBound;
}

```

## disassembly

```asm
0x180015e5c  push    rbx
0x180015e5e  push    rsi
0x180015e5f  push    rdi
0x180015e60  sub     rsp, 20h
0x180015e64  mov     rdi, rcx
0x180015e67  mov     [rsp+38h+ppvData], 0
0x180015e70  mov     rcx, [rcx+8]; psa
0x180015e74  lea     rdx, [rsp+38h+ppvData]; ppvData
0x180015e79  call    cs:__imp_SafeArrayAccessData
0x180015e7f  mov     ebx, eax
0x180015e81  test    eax, eax
0x180015e83  js      loc_180015F28
0x180015e89  mov     rcx, [rdi+8]; psa
0x180015e8d  lea     r8, [rsp+38h+plLbound]; plLbound
0x180015e92  xor     esi, esi
0x180015e94  mov     [rsp+38h+plLbound], esi
0x180015e98  mov     [rsp+38h+plUbound], esi
0x180015e9c  lea     edx, [rsi+1]; nDim
0x180015e9f  call    cs:__imp_SafeArrayGetLBound
0x180015ea5  mov     ebx, eax
0x180015ea7  test    eax, eax
0x180015ea9  js      short loc_180015EE8
0x180015eab  mov     rcx, [rdi+8]; psa
0x180015eaf  lea     r8, [rsp+38h+plUbound]; plUbound
0x180015eb4  lea     edx, [rsi+1]; nDim
0x180015eb7  call    cs:__imp_SafeArrayGetUBound
0x180015ebd  mov     ebx, eax
0x180015ebf  test    eax, eax
0x180015ec1  js      short loc_180015EE8
0x180015ec3  mov     edx, [rsp+38h+plUbound]
0x180015ec7  sub     edx, [rsp+38h+plLbound]
0x180015ecb  mov     rcx, [rsp+38h+ppvData]; strIn
0x180015ed0  inc     edx
0x180015ed2  shr     edx, 1; ui
0x180015ed4  call    cs:__imp_SysAllocStringLen
0x180015eda  mov     rsi, rax
0x180015edd  mov     eax, 80004005h
0x180015ee2  test    rsi, rsi
0x180015ee5  cmovz   ebx, eax
0x180015ee8  cmp     [rsp+38h+ppvData], 0
0x180015eee  jz      short loc_180015EFC
0x180015ef0  mov     rcx, [rdi+8]; psa
0x180015ef4  call    cs:__imp_SafeArrayUnaccessData
0x180015efa  mov     ebx, eax
0x180015efc  test    ebx, ebx
0x180015efe  js      short loc_180015F1A
0x180015f00  mov     rcx, rdi; pvarg
0x180015f03  call    cs:__imp_VariantClear
0x180015f09  mov     ebx, eax
0x180015f0b  test    eax, eax
0x180015f0d  js      short loc_180015F1A
0x180015f0f  mov     word ptr [rdi], 8
0x180015f14  mov     [rdi+8], rsi
0x180015f18  jmp     short loc_180015F28
0x180015f1a  test    rsi, rsi
0x180015f1d  jz      short loc_180015F28
0x180015f1f  mov     rcx, rsi; bstrString
0x180015f22  call    cs:__imp_SysFreeString
0x180015f28  mov     eax, ebx
0x180015f2a  add     rsp, 20h
0x180015f2e  pop     rdi
0x180015f2f  pop     rsi
0x180015f30  pop     rbx
0x180015f31  retn
```
