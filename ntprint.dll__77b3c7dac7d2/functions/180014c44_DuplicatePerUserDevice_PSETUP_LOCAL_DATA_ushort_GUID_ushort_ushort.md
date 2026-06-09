# DuplicatePerUserDevice(_PSETUP_LOCAL_DATA *,ushort *,_GUID *,ushort *,ushort *)

- ea: `0x180014c44`
- end: `0x180014cf0`
- name: `?DuplicatePerUserDevice@@YAHPEAU_PSETUP_LOCAL_DATA@@PEAGPEAU_GUID@@11@Z`
- size: `172`
- prototype: `int(struct _PSETUP_LOCAL_DATA *, unsigned __int16 *, struct _GUID *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180013804`

## callees

- `0x180012f34`
- `0x180012ff8`
- `0x180014c44`
- `0x180016ce4`

## import_xrefs

- `WINSPOOL!OpenPrinterW` at `0x180014c93`
- `WINSPOOL!OpenPrinterW` at `0x180014c93`
- `WINSPOOL!ClosePrinter` at `0x180014cc5`
- `WINSPOOL!ClosePrinter` at `0x180014cc5`

## pseudocode

```c
__int64 __fastcall DuplicatePerUserDevice(LPBYTE *a1, BYTE *a2, BYTE *a3, unsigned __int16 *a4, unsigned __int16 *a5)
{
  unsigned int v8; // ebx
  HANDLE phPrinter; // [rsp+30h] [rbp-18h] BYREF
  LPWSTR pPrinterName[2]; // [rsp+38h] [rbp-10h] BYREF
  unsigned __int16 *v12; // [rsp+68h] [rbp+20h] BYREF

  v12 = a4;
  phPrinter = 0;
  pPrinterName[0] = 0;
  if ( (int)wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short *,unsigned short [2],unsigned short *>(
              pPrinterName,
              &a5,
              a3,
              &v12) >= 0
    && OpenPrinterW(pPrinterName[0], &phPrinter, 0) )
  {
    SetPnPInfoForPrinter(phPrinter, a2, a1[4], a1[5], a1[6], a3);
    ClosePrinter(phPrinter);
    v8 = 1;
  }
  else
  {
    v8 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(pPrinterName);
  return v8;
}

```

## disassembly

```asm
0x180014c44  mov     rax, rsp
0x180014c47  mov     [rax+8], rbx
0x180014c4b  mov     [rax+10h], rsi
0x180014c4f  mov     [rax+20h], r9
0x180014c53  push    rdi
0x180014c54  sub     rsp, 40h
0x180014c58  mov     rsi, rdx
0x180014c5b  mov     qword ptr [rax-18h], 0
0x180014c63  mov     rbx, rcx
0x180014c66  mov     qword ptr [rax-10h], 0
0x180014c6e  lea     rdx, [rax+28h]
0x180014c72  mov     rdi, r8
0x180014c75  lea     rcx, [rax-10h]
0x180014c79  lea     r9, [rax+20h]
0x180014c7d  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAG$$BY01GPEAG@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBQEAGAEAY01$$CBG1@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort *,ushort [2],ushort *>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort * const &,ushort const (&)[2],ushort * const &)
0x180014c82  test    eax, eax
0x180014c84  js      short loc_180014CD2
0x180014c86  mov     rcx, [rsp+48h+pPrinterName]; pPrinterName
0x180014c8b  lea     rdx, [rsp+48h+phPrinter]; phPrinter
0x180014c90  xor     r8d, r8d; pDefault
0x180014c93  call    cs:__imp_OpenPrinterW
0x180014c99  test    eax, eax
0x180014c9b  jz      short loc_180014CD2
0x180014c9d  mov     rax, [rbx+30h]
0x180014ca1  mov     rdx, rsi; pData
0x180014ca4  mov     r9, [rbx+28h]; LPBYTE
0x180014ca8  mov     r8, [rbx+20h]; LPBYTE
0x180014cac  mov     rcx, [rsp+48h+phPrinter]; hPrinter
0x180014cb1  mov     [rsp+48h+var_20], rdi; LPBYTE
0x180014cb6  mov     [rsp+48h+var_28], rax; LPBYTE
0x180014cbb  call    SetPnPInfoForPrinter
0x180014cc0  mov     rcx, [rsp+48h+phPrinter]; hPrinter
0x180014cc5  call    cs:__imp_ClosePrinter
0x180014ccb  mov     ebx, 1
0x180014cd0  jmp     short loc_180014CD4
0x180014cd2  xor     ebx, ebx
0x180014cd4  lea     rcx, [rsp+48h+pPrinterName]
0x180014cd9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180014cde  mov     rsi, [rsp+48h+arg_8]
0x180014ce3  mov     eax, ebx
0x180014ce5  mov     rbx, [rsp+48h+arg_0]
0x180014cea  add     rsp, 40h
0x180014cee  pop     rdi
0x180014cef  retn
```
