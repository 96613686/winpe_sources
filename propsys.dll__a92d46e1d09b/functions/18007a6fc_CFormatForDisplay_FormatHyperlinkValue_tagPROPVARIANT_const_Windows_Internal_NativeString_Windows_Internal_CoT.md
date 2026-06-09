# CFormatForDisplay::_FormatHyperlinkValue(tagPROPVARIANT const &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)

- ea: `0x18007a6fc`
- end: `0x18007a7c7`
- name: `?_FormatHyperlinkValue@CFormatForDisplay@@AEAAJAEBUtagPROPVARIANT@@AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d240`

## callees

- `0x18000ca30`
- `0x18000ccd0`
- `0x180017e30`
- `0x180041af0`
- `0x18007a6fc`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrIW` at `0x18007a761`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrIW` at `0x18007a78e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrIW` at `0x18007a761`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrIW` at `0x18007a78e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a7b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a7b2`

## pseudocode

```c
__int64 __fastcall CFormatForDisplay::_FormatHyperlinkValue(__int64 a1, const PROPVARIANT *a2, __int64 a3)
{
  int v5; // edi
  PWSTR v6; // rsi
  WCHAR *v7; // rbx
  PWSTR v8; // rax
  PWSTR v9; // rbp
  PWSTR v10; // rax
  PWSTR ppszOut; // [rsp+60h] [rbp+8h] BYREF

  ppszOut = 0;
  v5 = 0;
  v6 = 0;
  v7 = (WCHAR *)PropVariantToStringWithDefault(a2, 0);
  if ( !v7 )
  {
    v5 = PropVariantToStringAlloc(a2, &ppszOut);
    if ( v5 < 0 )
      return (unsigned int)v5;
    v6 = ppszOut;
    v7 = ppszOut;
  }
  do
  {
    if ( !v7 || !*v7 )
      break;
    v8 = StrChrIW(v7, 0x3Cu);
    v9 = v8;
    if ( v8 )
    {
      v5 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(a3, v7, v8 - v7);
      v10 = StrChrIW(v9 + 1, 0x3Eu);
      v7 = v10 + 1;
      if ( !v10 )
        v7 = 0;
    }
    else
    {
      v5 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(a3, v7);
      v7 = 0;
    }
  }
  while ( v5 >= 0 );
  CoTaskMemFree(v6);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18007a6fc  mov     [rsp+ppszOut], rcx
0x18007a701  push    rbx
0x18007a702  push    rbp
0x18007a703  push    rsi
0x18007a704  push    rdi
0x18007a705  push    r14
0x18007a707  push    r15
0x18007a709  sub     rsp, 28h
0x18007a70d  mov     rbp, rdx
0x18007a710  xor     r15d, r15d
0x18007a713  mov     rcx, rbp; propvarIn
0x18007a716  mov     [rsp+58h+ppszOut], r15
0x18007a71b  xor     edx, edx; pszDefault
0x18007a71d  mov     r14, r8
0x18007a720  mov     edi, r15d
0x18007a723  mov     esi, r15d
0x18007a726  call    PropVariantToStringWithDefault
0x18007a72b  mov     rbx, rax
0x18007a72e  test    rax, rax
0x18007a731  jnz     short loc_18007A74E
0x18007a733  lea     rdx, [rsp+58h+ppszOut]; ppszOut
0x18007a738  mov     rcx, rbp; propvar
0x18007a73b  call    PropVariantToStringAlloc
0x18007a740  mov     edi, eax
0x18007a742  test    eax, eax
0x18007a744  js      short loc_18007A7B8
0x18007a746  mov     rsi, [rsp+58h+ppszOut]
0x18007a74b  mov     rbx, rsi
0x18007a74e  test    rbx, rbx
0x18007a751  jz      short loc_18007A7AF
0x18007a753  cmp     [rbx], r15w
0x18007a757  jz      short loc_18007A7AF
0x18007a759  mov     edx, 3Ch ; '<'; wMatch
0x18007a75e  mov     rcx, rbx; pszStart
0x18007a761  call    cs:__imp_StrChrIW
0x18007a767  mov     rdx, rbx
0x18007a76a  mov     rcx, r14
0x18007a76d  mov     rbp, rax
0x18007a770  test    rax, rax
0x18007a773  jz      short loc_18007A7A1
0x18007a775  mov     r8, rax
0x18007a778  sub     r8, rbx
0x18007a77b  sar     r8, 1
0x18007a77e  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18007a783  mov     edx, 3Eh ; '>'; wMatch
0x18007a788  lea     rcx, [rbp+2]; pszStart
0x18007a78c  mov     edi, eax
0x18007a78e  call    cs:__imp_StrChrIW
0x18007a794  test    rax, rax
0x18007a797  lea     rbx, [rax+2]
0x18007a79b  cmovz   rbx, rax
0x18007a79f  jmp     short loc_18007A7AB
0x18007a7a1  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x18007a7a6  mov     edi, eax
0x18007a7a8  mov     rbx, r15
0x18007a7ab  test    edi, edi
0x18007a7ad  jns     short loc_18007A74E
0x18007a7af  mov     rcx, rsi; pv
0x18007a7b2  call    cs:__imp_CoTaskMemFree
0x18007a7b8  mov     eax, edi
0x18007a7ba  add     rsp, 28h
0x18007a7be  pop     r15
0x18007a7c0  pop     r14
0x18007a7c2  pop     rdi
0x18007a7c3  pop     rsi
0x18007a7c4  pop     rbp
0x18007a7c5  pop     rbx
0x18007a7c6  retn
```
