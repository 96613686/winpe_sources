# SharingToken::ConvertStringToTokenId(ushort const *,_GUID &)

- ea: `0x180011a78`
- end: `0x180011b30`
- name: `?ConvertStringToTokenId@SharingToken@@SAJPEBGAEAU_GUID@@@Z`
- size: `184`
- prototype: `static int(const unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000da68`

## callees

- `0x1800041a0`
- `0x180006cb0`
- `0x180006d2c`
- `0x180006d54`
- `0x180006e54`
- `0x180006f78`
- `0x18000bf80`
- `0x180011a78`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180011ae8`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180011ae8`

## string_xrefs

- `0x180011b0a`: `SharingToken::ConvertStringToTokenId`

## pseudocode

```c
__int64 __fastcall SharingToken::ConvertStringToTokenId(const unsigned __int16 *a1, struct _GUID *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  HRESULT v7; // ebx
  DSLogger *v8; // rax
  HRESULT v10; // [rsp+20h] [rbp-38h]
  LPCOLESTR lpsz[5]; // [rsp+30h] [rbp-28h] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpsz);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           lpsz,
                           L"{",
                           1)
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           lpsz,
                           a1)
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           lpsz,
                           L"}",
                           1) )
  {
    v7 = -2147024882;
LABEL_6:
    v8 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                       v5,
                       v4,
                       v6);
    v10 = v7;
    DSLogger::LogError(v8, L"SharingToken::ConvertStringToTokenId", 0x68u, L"hr=0x%x.", v10);
    goto LABEL_7;
  }
  v7 = CLSIDFromString(lpsz[0], a2);
  if ( v7 < 0 )
    goto LABEL_6;
LABEL_7:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpsz);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180011a78  mov     [rsp+arg_0], rbx
0x180011a7d  push    rdi
0x180011a7e  sub     rsp, 50h
0x180011a82  mov     rdi, rcx
0x180011a85  mov     rbx, rdx
0x180011a88  lea     rcx, [rsp+58h+lpsz]
0x180011a8d  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180011a92  lea     rdx, asc_18002113C; "{"
0x180011a99  mov     r8d, 1
0x180011a9f  lea     rcx, [rsp+58h+lpsz]
0x180011aa4  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180011aa9  test    al, al
0x180011aab  jnz     short loc_180011AB4
0x180011aad  mov     ebx, 8007000Eh
0x180011ab2  jmp     short loc_180011AF4
0x180011ab4  mov     rdx, rdi
0x180011ab7  lea     rcx, [rsp+58h+lpsz]
0x180011abc  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180011ac1  test    al, al
0x180011ac3  jz      short loc_180011AAD
0x180011ac5  mov     r8d, 1
0x180011acb  lea     rdx, asc_180021140; "}"
0x180011ad2  lea     rcx, [rsp+58h+lpsz]
0x180011ad7  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180011adc  test    al, al
0x180011ade  jz      short loc_180011AAD
0x180011ae0  mov     rcx, [rsp+58h+lpsz]; lpsz
0x180011ae5  mov     rdx, rbx; pclsid
0x180011ae8  call    cs:__imp_CLSIDFromString
0x180011aee  mov     ebx, eax
0x180011af0  test    eax, eax
0x180011af2  jns     short loc_180011B19
0x180011af4  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180011af9  lea     r9, aHr0xX; "hr=0x%x."
0x180011b00  mov     [rsp+58h+var_38], ebx
0x180011b04  mov     r8d, 68h ; 'h'; unsigned int
0x180011b0a  lea     rdx, aSharingtokenCo_0; "SharingToken::ConvertStringToTokenId"
0x180011b11  mov     rcx, rax; this
0x180011b14  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180011b19  lea     rcx, [rsp+58h+lpsz]
0x180011b1e  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180011b23  mov     eax, ebx
0x180011b25  mov     rbx, [rsp+58h+arg_0]
0x180011b2a  add     rsp, 50h
0x180011b2e  pop     rdi
0x180011b2f  retn
```
