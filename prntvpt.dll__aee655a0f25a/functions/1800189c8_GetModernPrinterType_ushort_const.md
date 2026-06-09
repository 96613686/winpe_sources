# GetModernPrinterType(ushort const *)

- ea: `0x1800189c8`
- end: `0x180018a33`
- name: `?GetModernPrinterType@@YA?AW4ModernPrinterType@PrintCore@@PEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(WCHAR *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180019300`
- `0x1800194e0`

## callees

- `0x1800188b8`
- `0x1800189c8`
- `0x180018aa0`
- `0x180018cd0`

## import_xrefs

- `WINSPOOL!OpenPrinterW` at `0x1800189f1`
- `WINSPOOL!OpenPrinterW` at `0x1800189f1`

## pseudocode

```c
__int64 __fastcall GetModernPrinterType(WCHAR *a1)
{
  int ModernPrinterType; // eax
  unsigned int v2; // r8d
  struct _PRINTER_DEFAULTSW v4; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int v6; // [rsp+58h] [rbp+10h] BYREF
  void *v7; // [rsp+60h] [rbp+18h] BYREF

  v6 = 0;
  v7 = 0;
  memset(&v4, 0, sizeof(v4));
  if ( OpenPrinterW(a1, &v7, &v4) )
  {
    ModernPrinterType = PrintCore::IppSelection::GetModernPrinterType(v7, (enum PrintCore::ModernPrinterType *)&v6);
    if ( ModernPrinterType < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x260,
        v2,
        (const char *)(unsigned int)ModernPrinterType,
        (int)v4.pDatatype);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v7);
  return v6;
}

```

## disassembly

```asm
0x1800189c8  mov     r11, rsp
0x1800189cb  sub     rsp, 48h
0x1800189cf  xor     eax, eax
0x1800189d1  mov     [rsp+48h+arg_8], 0
0x1800189d9  xorps   xmm0, xmm0
0x1800189dc  mov     [r11+18h], rax
0x1800189e0  movups  xmmword ptr [rsp+48h+var_28.pDatatype], xmm0; int
0x1800189e5  lea     r8, [r11-28h]; pDefault
0x1800189e9  mov     [r11-18h], rax
0x1800189ed  lea     rdx, [r11+18h]; phPrinter
0x1800189f1  call    cs:__imp_OpenPrinterW
0x1800189f7  test    eax, eax
0x1800189f9  jz      short loc_180018A20
0x1800189fb  mov     rcx, [rsp+48h+arg_10]; void *
0x180018a00  lea     rdx, [rsp+48h+arg_8]; enum PrintCore::ModernPrinterType *
0x180018a05  call    ?GetModernPrinterType@IppSelection@PrintCore@@SAJPEAXAEAW4ModernPrinterType@2@@Z; PrintCore::IppSelection::GetModernPrinterType(void *,PrintCore::ModernPrinterType &)
0x180018a0a  test    eax, eax
0x180018a0c  jns     short loc_180018A20
0x180018a0e  mov     rcx, [rsp+48h]; this
0x180018a13  mov     r9d, eax; char *
0x180018a16  mov     edx, 260h; void *
0x180018a1b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180018a20  lea     rcx, [rsp+48h+arg_10]
0x180018a25  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180018a2a  mov     eax, [rsp+48h+arg_8]
0x180018a2e  add     rsp, 48h
0x180018a32  retn
```
