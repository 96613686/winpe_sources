# FID_FileName(_ITEMIDLIST const *,uint,ushort *,uint)

- ea: `0x18002265c`
- end: `0x1800226f1`
- name: `?FID_FileName@@YAJPEFBU_ITEMIDLIST@@IPEAGI@Z`
- size: `149`
- prototype: `__int64 __fastcall(const struct _ITEMIDLIST *, ULONG, unsigned __int16 *)`
- caller_count: `11`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007154`
- `0x180010694`
- `0x180012110`
- `0x180012230`
- `0x1800122e8`
- `0x18001252c`
- `0x1800162c0`
- `0x18001d490`
- `0x1800226f8`
- `0x180026e20`
- `0x18002a614`

## callees

- `0x180006624`
- `0x1800167b8`
- `0x18002265c`

## import_xrefs

- `PROPSYS!VariantGetStringElem` at `0x1800226a9`
- `PROPSYS!VariantGetStringElem` at `0x1800226a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800226d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800226d9`
- `OLEAUT32!__imp_VariantClear` at `0x1800226b6`
- `OLEAUT32!__imp_VariantClear` at `0x1800226b6`

## pseudocode

```c
__int64 __fastcall FID_FileName(const struct _ITEMIDLIST *a1, ULONG a2, unsigned __int16 *a3)
{
  HRESULT PropertyFromIDList; // ebx
  PWSTR ppszVal; // [rsp+20h] [rbp-28h] BYREF
  VARIANT var; // [rsp+28h] [rbp-20h] BYREF

  ppszVal = 0;
  memset(&var, 0, sizeof(var));
  PropertyFromIDList = CItemIDFactory<FID,156830041>::GetPropertyFromIDList(a1, &PKEY_Fonts_FileNames, &var);
  if ( PropertyFromIDList >= 0 )
  {
    PropertyFromIDList = VariantGetStringElem(&var, a2, &ppszVal);
    VariantClear(&var);
    if ( PropertyFromIDList >= 0 )
    {
      PropertyFromIDList = StringCchCopyW(a3, 0x104u, ppszVal);
      CoTaskMemFree(ppszVal);
    }
  }
  return (unsigned int)PropertyFromIDList;
}

```

## disassembly

```asm
0x18002265c  mov     r11, rsp
0x18002265f  mov     [r11+8], rbx
0x180022663  mov     [r11+10h], rsi
0x180022667  push    rdi
0x180022668  sub     rsp, 40h
0x18002266c  xorps   xmm0, xmm0
0x18002266f  mov     qword ptr [r11-28h], 0
0x180022677  mov     rdi, r8
0x18002267a  mov     esi, edx
0x18002267c  xor     eax, eax
0x18002267e  lea     r8, [r11-20h]
0x180022682  movups  xmmword ptr [rsp+48h+var], xmm0
0x180022687  lea     rdx, PKEY_Fonts_FileNames
0x18002268e  mov     [r11-10h], rax
0x180022692  call    ?GetPropertyFromIDList@?$CItemIDFactory@UFID@@$0JFJAJFJ@@@SAJPEFBU_ITEMIDLIST@@AEBU_tagpropertykey@@PEAUtagVARIANT@@@Z; CItemIDFactory<FID,156830041>::GetPropertyFromIDList(_ITEMIDLIST const *,_tagpropertykey const &,tagVARIANT *)
0x180022697  mov     ebx, eax
0x180022699  test    eax, eax
0x18002269b  js      short loc_1800226DF
0x18002269d  lea     r8, [rsp+48h+ppszVal]; ppszVal
0x1800226a2  mov     edx, esi; iElem
0x1800226a4  lea     rcx, [rsp+48h+var]; var
0x1800226a9  call    cs:__imp_VariantGetStringElem
0x1800226af  lea     rcx, [rsp+48h+var]; pvarg
0x1800226b4  mov     ebx, eax
0x1800226b6  call    cs:__imp_VariantClear
0x1800226bc  test    ebx, ebx
0x1800226be  js      short loc_1800226DF
0x1800226c0  mov     r8, [rsp+48h+ppszVal]; unsigned __int16 *
0x1800226c5  mov     edx, 104h; unsigned __int64
0x1800226ca  mov     rcx, rdi; unsigned __int16 *
0x1800226cd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800226d2  mov     rcx, [rsp+48h+ppszVal]; pv
0x1800226d7  mov     ebx, eax
0x1800226d9  call    cs:__imp_CoTaskMemFree
0x1800226df  mov     rsi, [rsp+48h+arg_8]
0x1800226e4  mov     eax, ebx
0x1800226e6  mov     rbx, [rsp+48h+arg_0]
0x1800226eb  add     rsp, 40h
0x1800226ef  pop     rdi
0x1800226f0  retn
```
