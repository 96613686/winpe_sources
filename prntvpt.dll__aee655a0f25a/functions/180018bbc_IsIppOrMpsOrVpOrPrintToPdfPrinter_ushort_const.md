# IsIppOrMpsOrVpOrPrintToPdfPrinter(ushort const *)

- ea: `0x180018bbc`
- end: `0x180018c91`
- name: `?IsIppOrMpsOrVpOrPrintToPdfPrinter@@YA_NPEBG@Z`
- size: `213`
- prototype: `char __fastcall(WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800188d8`

## callees

- `0x18000c8c4`
- `0x1800188b8`
- `0x180018bbc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180018c1f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180018c34`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180018c49`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180018c5e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180018c1f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180018c34`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180018c49`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180018c5e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018c73`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018c73`
- `WINSPOOL!OpenPrinterW` at `0x180018be5`
- `WINSPOOL!OpenPrinterW` at `0x180018be5`

## pseudocode

```c
char __fastcall IsIppOrMpsOrVpOrPrintToPdfPrinter(WCHAR *a1)
{
  char v1; // di
  struct _DRIVER_INFO_8W **v2; // r8
  int DriverInfo; // eax
  _QWORD *v4; // rbx
  struct _PRINTER_DEFAULTSW v6; // [rsp+20h] [rbp-28h] BYREF
  HANDLE hPrinter; // [rsp+58h] [rbp+10h] BYREF
  void *Block; // [rsp+60h] [rbp+18h] BYREF

  hPrinter = 0;
  memset(&v6, 0, sizeof(v6));
  v1 = 0;
  if ( OpenPrinterW(a1, &hPrinter, &v6) )
  {
    Block = 0;
    DriverInfo = PrintCore::GetDriverInfo(hPrinter, &Block, v2);
    v4 = Block;
    if ( DriverInfo >= 0
      && (!(unsigned int)_o__wcsicmp(*((_QWORD *)Block + 15), L"{B71661F4-A4DC-43DF-BC16-39D337D15A95}")
       || !(unsigned int)_o__wcsicmp(v4[15], L"{6D170653-5280-44C2-BA44-2C04BC9D46DA}")
       || !(unsigned int)_o__wcsicmp(v4[15], L"{C1F56D94-A46F-492E-A129-7F54D1EE2356}")
       || !(unsigned int)_o__wcsicmp(v4[15], L"{084f01fa-e634-4d77-83ee-074817c03581}")) )
    {
      v1 = 1;
    }
    if ( v4 )
      free(v4);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hPrinter);
  return v1;
}

```

## disassembly

```asm
0x180018bbc  mov     r11, rsp
0x180018bbf  mov     [r11+8], rbx
0x180018bc3  push    rdi
0x180018bc4  sub     rsp, 40h
0x180018bc8  xor     eax, eax
0x180018bca  lea     r8, [r11-28h]; pDefault
0x180018bce  xorps   xmm0, xmm0
0x180018bd1  mov     [r11+10h], rax
0x180018bd5  movups  xmmword ptr [rsp+48h+var_28.pDatatype], xmm0
0x180018bda  lea     rdx, [r11+10h]; phPrinter
0x180018bde  mov     [r11-18h], rax
0x180018be2  xor     dil, dil
0x180018be5  call    cs:__imp_OpenPrinterW
0x180018beb  test    eax, eax
0x180018bed  jz      loc_180018C79
0x180018bf3  mov     rcx, [rsp+48h+hPrinter]; hPrinter
0x180018bf8  lea     rdx, [rsp+48h+Block]; void *
0x180018bfd  mov     [rsp+48h+Block], 0
0x180018c06  call    ?GetDriverInfo@PrintCore@@YAJPEAXPEAPEAU_DRIVER_INFO_8W@@@Z; PrintCore::GetDriverInfo(void *,_DRIVER_INFO_8W * *)
0x180018c0b  mov     rbx, [rsp+48h+Block]
0x180018c10  test    eax, eax
0x180018c12  js      short loc_180018C6B
0x180018c14  mov     rcx, [rbx+78h]
0x180018c18  lea     rdx, aB71661f4A4dc43; "{B71661F4-A4DC-43DF-BC16-39D337D15A95}"
0x180018c1f  call    cs:__imp__o__wcsicmp
0x180018c25  test    eax, eax
0x180018c27  jz      short loc_180018C68
0x180018c29  mov     rcx, [rbx+78h]
0x180018c2d  lea     rdx, a6d170653528044; "{6D170653-5280-44C2-BA44-2C04BC9D46DA}"
0x180018c34  call    cs:__imp__o__wcsicmp
0x180018c3a  test    eax, eax
0x180018c3c  jz      short loc_180018C68
0x180018c3e  mov     rcx, [rbx+78h]
0x180018c42  lea     rdx, aC1f56d94A46f49; "{C1F56D94-A46F-492E-A129-7F54D1EE2356}"
0x180018c49  call    cs:__imp__o__wcsicmp
0x180018c4f  test    eax, eax
0x180018c51  jz      short loc_180018C68
0x180018c53  mov     rcx, [rbx+78h]
0x180018c57  lea     rdx, a084f01faE6344d; "{084f01fa-e634-4d77-83ee-074817c03581}"
0x180018c5e  call    cs:__imp__o__wcsicmp
0x180018c64  test    eax, eax
0x180018c66  jnz     short loc_180018C6B
0x180018c68  mov     dil, 1
0x180018c6b  test    rbx, rbx
0x180018c6e  jz      short loc_180018C79
0x180018c70  mov     rcx, rbx; Block
0x180018c73  call    cs:__imp_free
0x180018c79  lea     rcx, [rsp+48h+hPrinter]
0x180018c7e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180018c83  mov     rbx, [rsp+48h+arg_0]
0x180018c88  mov     al, dil
0x180018c8b  add     rsp, 40h
0x180018c8f  pop     rdi
0x180018c90  retn
```
