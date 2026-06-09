# GetAttributeValue(IXmlReader *,ushort const *,ushort *,unsigned __int64)

- ea: `0x180011c88`
- end: `0x180011e31`
- name: `?GetAttributeValue@@YAJPEAUIXmlReader@@PEBGPEAG_K@Z`
- size: `425`
- prototype: `__int64 __fastcall(struct IXmlReader *, const unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180011e38`

## callees

- `0x180005424`
- `0x180006014`
- `0x180011c88`
- `0x180018434`
- `0x180019010`

## string_xrefs

- `0x180011cd1`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180011d5d`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180011dac`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180011de7`: `onecore\base\ntsetup\provpackageapi\lib\metadataxml.cpp`
- `0x180011dd5`: `    Failed to copy value string`

## pseudocode

```c
__int64 __fastcall GetAttributeValue(
        struct IXmlReader *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int64 a4)
{
  struct IXmlReaderVtbl *lpVtbl; // rax
  int v8; // eax
  unsigned int v9; // edi
  struct IXmlReaderVtbl *v10; // rax
  int v11; // eax
  int v12; // eax
  unsigned __int16 *v14; // [rsp+30h] [rbp-28h] BYREF
  wchar_t *String1; // [rsp+60h] [rbp+8h] BYREF
  const unsigned __int16 *v16; // [rsp+68h] [rbp+10h] BYREF

  v16 = a2;
  lpVtbl = a1->lpVtbl;
  String1 = 0;
  LODWORD(v16) = 0;
  v8 = ((__int64 (__fastcall *)(struct IXmlReader *, wchar_t **, const unsigned __int16 **))lpVtbl->GetLocalName)(
         a1,
         &String1,
         &v16);
  v9 = v8;
  if ( v8 >= 0 )
  {
    if ( (_DWORD)v16 == 5 && !wcsncmp_0(String1, L"Value", 5u) )
    {
      v10 = a1->lpVtbl;
      v14 = 0;
      v11 = ((__int64 (__fastcall *)(struct IXmlReader *, unsigned __int16 **, _QWORD))v10->GetValue)(a1, &v14, 0);
      v9 = v11;
      if ( v11 >= 0 )
      {
        v12 = StringCchCopyW(a3, a4, v14);
        v9 = v12;
        if ( v12 >= 0 )
          return 0;
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "GetAttributeValue",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
          295,
          v12);
        ProvPackageLog(3, L"    Failed to copy value string");
      }
      else
      {
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "GetAttributeValue",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
          292,
          v11);
        ProvPackageLog(3, L"    Failed to get value");
      }
    }
    else
    {
      v9 = -2147418113;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "GetAttributeValue",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
        286,
        -2147418113);
      ProvPackageLog(3, L"    Local name does not match");
    }
  }
  else
  {
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "GetAttributeValue",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\metadataxml.cpp",
      281,
      v8);
    ProvPackageLog(3, L"    Failed to get local name");
  }
  return v9;
}

```

## disassembly

```asm
0x180011c88  mov     r11, rsp
0x180011c8b  mov     [r11+18h], rbx
0x180011c8f  mov     [r11+10h], rdx
0x180011c93  push    rbp
0x180011c94  push    rsi
0x180011c95  push    rdi
0x180011c96  sub     rsp, 40h
0x180011c9a  mov     rax, [rcx]
0x180011c9d  lea     rdx, [r11+8]
0x180011ca1  mov     rbp, r8
0x180011ca4  mov     qword ptr [r11+8], 0
0x180011cac  lea     r8, [r11+10h]
0x180011cb0  mov     dword ptr [rsp+58h+arg_8], 0
0x180011cb8  mov     rsi, r9
0x180011cbb  mov     rbx, rcx
0x180011cbe  mov     rax, [rax+70h]
0x180011cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cc7  mov     edi, eax
0x180011cc9  test    eax, eax
0x180011ccb  jns     short loc_180011D06
0x180011ccd  mov     [rsp+58h+var_30], eax
0x180011cd1  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180011cd8  mov     ebx, 3
0x180011cdd  mov     [rsp+58h+var_38], 119h
0x180011ce5  mov     ecx, ebx
0x180011ce7  lea     r8, aGetattributeva; "GetAttributeValue"
0x180011cee  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180011cf5  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180011cfa  lea     rdx, aFailedToGetLoc; "    Failed to get local name"
0x180011d01  jmp     loc_180011E1B
0x180011d06  mov     r8d, 5; MaxCount
0x180011d0c  cmp     dword ptr [rsp+58h+arg_8], r8d
0x180011d11  jnz     loc_180011DE2
0x180011d17  mov     rcx, [rsp+58h+String1]; String1
0x180011d1c  lea     rdx, aValue; "Value"
0x180011d23  call    wcsncmp_0
0x180011d28  test    eax, eax
0x180011d2a  jnz     loc_180011DE2
0x180011d30  mov     rax, [rbx]
0x180011d33  lea     rdx, [rsp+58h+var_28]
0x180011d38  xor     r8d, r8d
0x180011d3b  mov     [rsp+58h+var_28], 0
0x180011d44  mov     rcx, rbx
0x180011d47  mov     rax, [rax+80h]
0x180011d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d53  mov     edi, eax
0x180011d55  test    eax, eax
0x180011d57  jns     short loc_180011D92
0x180011d59  mov     [rsp+58h+var_30], eax
0x180011d5d  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180011d64  mov     ebx, 3
0x180011d69  mov     [rsp+58h+var_38], 124h
0x180011d71  mov     ecx, ebx
0x180011d73  lea     r8, aGetattributeva; "GetAttributeValue"
0x180011d7a  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180011d81  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180011d86  lea     rdx, aFailedToGetVal_0; "    Failed to get value"
0x180011d8d  jmp     loc_180011E1B
0x180011d92  mov     r8, [rsp+58h+var_28]; unsigned __int16 *
0x180011d97  mov     rdx, rsi; unsigned __int64
0x180011d9a  mov     rcx, rbp; unsigned __int16 *
0x180011d9d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011da2  mov     edi, eax
0x180011da4  test    eax, eax
0x180011da6  jns     short loc_180011DDE
0x180011da8  mov     [rsp+58h+var_30], eax
0x180011dac  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180011db3  mov     ebx, 3
0x180011db8  mov     [rsp+58h+var_38], 127h
0x180011dc0  mov     ecx, ebx
0x180011dc2  lea     r8, aGetattributeva; "GetAttributeValue"
0x180011dc9  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180011dd0  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180011dd5  lea     rdx, aFailedToCopyVa; "    Failed to copy value string"
0x180011ddc  jmp     short loc_180011E1B
0x180011dde  xor     eax, eax
0x180011de0  jmp     short loc_180011E24
0x180011de2  mov     edi, 8000FFFFh
0x180011de7  lea     r9, aOnecoreBaseNts_5; "onecore\\base\\ntsetup\\provpackageapi"...
0x180011dee  mov     ebx, 3
0x180011df3  mov     [rsp+58h+var_30], edi
0x180011df7  mov     ecx, ebx
0x180011df9  mov     [rsp+58h+var_38], 11Eh
0x180011e01  lea     r8, aGetattributeva; "GetAttributeValue"
0x180011e08  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180011e0f  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180011e14  lea     rdx, aLocalNameDoesN; "    Local name does not match"
0x180011e1b  mov     ecx, ebx
0x180011e1d  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180011e22  mov     eax, edi
0x180011e24  mov     rbx, [rsp+58h+arg_10]
0x180011e29  add     rsp, 40h
0x180011e2d  pop     rdi
0x180011e2e  pop     rsi
0x180011e2f  pop     rbp
0x180011e30  retn
```
