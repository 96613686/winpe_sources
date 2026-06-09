# SplPipeline::GetFilePoolDirectory(void)

- ea: `0x140011310`
- end: `0x14001156e`
- name: `?GetFilePoolDirectory@SplPipeline@@YAPEA_WXZ`
- size: `606`
- prototype: `wchar_t *__fastcall(SplPipeline *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x140010c34`
- `0x140012404`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140005358`
- `0x140009848`
- `0x14000d494`
- `0x140010f04`
- `0x140011310`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140046314`

## import_xrefs

- `WINSPOOL!ClosePrinter` at `0x14001133f`
- `WINSPOOL!OpenPrinterW` at `0x14001135f`
- `WINSPOOL!OpenPrinterW` at `0x14001135f`
- `WINSPOOL!GetPrinterDataW` at `0x1400113eb`
- `WINSPOOL!GetPrinterDataW` at `0x1400114b6`
- `WINSPOOL!GetPrinterDataW` at `0x1400113eb`
- `WINSPOOL!GetPrinterDataW` at `0x1400114b6`

## string_xrefs

- `0x14001138f`: `OpenPrinter failed.`
- `0x1400113df`: `DefaultSpoolDirectory`
- `0x1400114aa`: `DefaultSpoolDirectory`

## pseudocode

```c
wchar_t *__fastcall SplPipeline::GetFilePoolDirectory(SplPipeline *this)
{
  NCoreLibrary *v1; // rcx
  unsigned int LastErrorAsHResult; // eax
  const struct SplException::TSystemException *v3; // r8
  const struct _GUID *v4; // r9
  signed int PrinterDataW; // eax
  unsigned int v6; // r8d
  unsigned int v7; // ebx
  const struct SplException::TSystemException *v8; // r8
  const struct _GUID *v9; // r9
  unsigned __int128 v10; // rax
  void *v11; // rax
  signed int v12; // eax
  unsigned int v13; // ebx
  const struct SplException::TSystemException *v14; // r8
  const struct _GUID *v15; // r9
  LPBYTE v16; // rbx
  DWORD nSize; // [rsp+20h] [rbp-E0h]
  DWORD nSizea; // [rsp+20h] [rbp-E0h]
  DWORD nSizeb; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *pcbNeeded; // [rsp+28h] [rbp-D8h]
  const struct win_musl::TStringEllipseBase *pcbNeededa; // [rsp+28h] [rbp-D8h]
  const struct win_musl::TStringEllipseBase *pcbNeededb; // [rsp+28h] [rbp-D8h]
  HINSTANCE v24; // [rsp+30h] [rbp-D0h]
  DWORD v25; // [rsp+40h] [rbp-C0h] BYREF
  LPBYTE pData; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE phPrinter[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v28[160]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+100h] [rbp+0h] BYREF

  phPrinter[0] = 0;
  phPrinter[1] = ClosePrinter;
  PrnExcept::SmartPrinterHandle::Free((PrnExcept::SmartPrinterHandle *)phPrinter);
  if ( !OpenPrinterW(0, phPrinter, 0) )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v28, "-", 0);
    LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v1);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v28,
      LastErrorAsHResult,
      v3,
      v4,
      nSize,
      pcbNeeded,
      v24);
    SplException::TSystemException::Message((SplException::TSystemException *)v28, "OpenPrinter failed.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v28);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v25 = 0;
  PrinterDataW = GetPrinterDataW(phPrinter[0], (LPWSTR)L"DefaultSpoolDirectory", 0, 0, 0, &v25);
  v7 = PrinterDataW;
  if ( PrinterDataW != 234 )
  {
    if ( PrinterDataW > 0 )
      v7 = (unsigned __int16)PrinterDataW | 0x80070000;
    SplException::THResultException::THResultException((SplException::THResultException *)v28, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v28,
      v7,
      v8,
      v9,
      nSizea,
      pcbNeededa,
      v24);
    SplException::TSystemException::Message((SplException::TSystemException *)v28, "Unexpected return value.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v28);
    throw (SplException::THResultException *)pExceptionObject;
  }
  pData = 0;
  v10 = ((unsigned __int64)v25 >> 1) * (unsigned __int128)2uLL;
  if ( !is_mul_ok((unsigned __int64)v25 >> 1, 2u) )
    *(_QWORD *)&v10 = -1;
  v11 = operator new(v10, *((const char **)&v10 + 1), v6);
  NCoreLibrary::TAutoPtrArray<wchar_t>::operator=(&pData, v11);
  v12 = GetPrinterDataW(phPrinter[0], (LPWSTR)L"DefaultSpoolDirectory", 0, pData, v25, &v25);
  v13 = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      v13 = (unsigned __int16)v12 | 0x80070000;
    SplException::THResultException::THResultException((SplException::THResultException *)v28, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v28,
      v13,
      v14,
      v15,
      nSizeb,
      pcbNeededb,
      v24);
    SplException::TSystemException::Message((SplException::TSystemException *)v28, "GetPrinterData failed.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v28);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v16 = 0;
  if ( pData )
  {
    v16 = pData;
    pData = 0;
  }
  NCoreLibrary::TGenericSP<unsigned char,NCoreLibrary::TAutoPtrArray<unsigned char>,unsigned char *,0,unsigned char const *>::Reset(&pData);
  PrnExcept::SmartPrinterHandle::Free((PrnExcept::SmartPrinterHandle *)phPrinter);
  return (wchar_t *)v16;
}

```

## disassembly

```asm
0x140011310  mov     [rsp-8+arg_0], rbx
0x140011315  push    rbp
0x140011316  lea     rbp, [rsp-0B0h]
0x14001131e  sub     rsp, 1B0h
0x140011325  mov     rax, cs:__security_cookie
0x14001132c  xor     rax, rsp
0x14001132f  mov     [rbp+0B0h+var_10], rax
0x140011336  mov     [rsp+1B0h+phPrinter], 0
0x14001133f  mov     rax, cs:__imp_ClosePrinter
0x140011346  mov     [rsp+1B0h+var_158], rax
0x14001134b  lea     rcx, [rsp+1B0h+phPrinter]; this
0x140011350  call    ?Free@SmartPrinterHandle@PrnExcept@@AEAAXXZ; PrnExcept::SmartPrinterHandle::Free(void)
0x140011355  xor     r8d, r8d; pDefault
0x140011358  lea     rdx, [rsp+1B0h+phPrinter]; phPrinter
0x14001135d  xor     ecx, ecx; pPrinterName
0x14001135f  call    cs:__imp_OpenPrinterW
0x140011365  test    eax, eax
0x140011367  jnz     short loc_1400113BF
0x140011369  xor     r8d, r8d; unsigned int
0x14001136c  lea     rdx, asc_1400696D8; "-"
0x140011373  lea     rcx, [rsp+1B0h+var_150]; this
0x140011378  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14001137d  nop
0x14001137e  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x140011383  mov     edx, eax; unsigned int
0x140011385  lea     rcx, [rsp+1B0h+var_150]; this
0x14001138a  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x14001138f  lea     rdx, aOpenprinterFai; "OpenPrinter failed."
0x140011396  lea     rcx, [rsp+1B0h+var_150]; this
0x14001139b  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x1400113a0  lea     rdx, [rsp+1B0h+var_150]; struct SplException::THResultException *
0x1400113a5  lea     rcx, [rbp+0B0h+pExceptionObject]; this
0x1400113a9  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x1400113ae  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1400113b5  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x1400113b9  call    _CxxThrowException_0
0x1400113bf  mov     [rsp+1B0h+var_170], 0
0x1400113c7  lea     rax, [rsp+1B0h+var_170]
0x1400113cc  mov     [rsp+1B0h+pcbNeeded], rax; struct win_musl::TStringEllipseBase *
0x1400113d1  mov     [rsp+1B0h+nSize], 0; unsigned int
0x1400113d9  xor     r9d, r9d; pData
0x1400113dc  xor     r8d, r8d; pType
0x1400113df  lea     rdx, pValueName; "DefaultSpoolDirectory"
0x1400113e6  mov     rcx, [rsp+1B0h+phPrinter]; hPrinter
0x1400113eb  call    cs:__imp_GetPrinterDataW
0x1400113f1  mov     ebx, eax
0x1400113f3  cmp     eax, 0EAh
0x1400113f8  jz      short loc_140011458
0x1400113fa  test    eax, eax
0x1400113fc  jle     short loc_140011407
0x1400113fe  movzx   ebx, ax
0x140011401  or      ebx, 80070000h
0x140011407  xor     r8d, r8d; unsigned int
0x14001140a  lea     rdx, asc_1400696D8; "-"
0x140011411  lea     rcx, [rsp+1B0h+var_150]; this
0x140011416  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14001141b  nop
0x14001141c  mov     edx, ebx; unsigned int
0x14001141e  lea     rcx, [rsp+1B0h+var_150]; this
0x140011423  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140011428  lea     rdx, aUnexpectedRetu; "Unexpected return value."
0x14001142f  lea     rcx, [rsp+1B0h+var_150]; this
0x140011434  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140011439  lea     rdx, [rsp+1B0h+var_150]; struct SplException::THResultException *
0x14001143e  lea     rcx, [rbp+0B0h+pExceptionObject]; this
0x140011442  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140011447  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x14001144e  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x140011452  call    _CxxThrowException_0
0x140011458  mov     [rsp+1B0h+pData], 0
0x140011461  mov     ecx, [rsp+1B0h+var_170]
0x140011465  shr     rcx, 1
0x140011468  mov     eax, 2
0x14001146d  mul     rcx
0x140011470  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140011477  cmovb   rax, rcx
0x14001147b  mov     rcx, rax; unsigned __int64
0x14001147e  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x140011483  mov     rdx, rax
0x140011486  lea     rcx, [rsp+1B0h+pData]
0x14001148b  call    ??4?$TAutoPtrArray@_W@NCoreLibrary@@QEAAPEA_WPEA_W@Z; NCoreLibrary::TAutoPtrArray<wchar_t>::operator=(wchar_t *)
0x140011490  mov     eax, [rsp+1B0h+var_170]
0x140011494  lea     rcx, [rsp+1B0h+var_170]
0x140011499  mov     [rsp+1B0h+pcbNeeded], rcx; struct win_musl::TStringEllipseBase *
0x14001149e  mov     [rsp+1B0h+nSize], eax; unsigned int
0x1400114a2  mov     r9, [rsp+1B0h+pData]; pData
0x1400114a7  xor     r8d, r8d; pType
0x1400114aa  lea     rdx, pValueName; "DefaultSpoolDirectory"
0x1400114b1  mov     rcx, [rsp+1B0h+phPrinter]; hPrinter
0x1400114b6  call    cs:__imp_GetPrinterDataW
0x1400114bc  mov     ebx, eax
0x1400114be  test    eax, eax
0x1400114c0  jz      short loc_14001151E
0x1400114c2  jle     short loc_1400114CD
0x1400114c4  movzx   ebx, ax
0x1400114c7  or      ebx, 80070000h
0x1400114cd  xor     r8d, r8d; unsigned int
0x1400114d0  lea     rdx, asc_1400696D8; "-"
0x1400114d7  lea     rcx, [rsp+1B0h+var_150]; this
0x1400114dc  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x1400114e1  nop
0x1400114e2  mov     edx, ebx; unsigned int
0x1400114e4  lea     rcx, [rsp+1B0h+var_150]; this
0x1400114e9  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x1400114ee  lea     rdx, aGetprinterdata; "GetPrinterData failed."
0x1400114f5  lea     rcx, [rsp+1B0h+var_150]; this
0x1400114fa  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x1400114ff  lea     rdx, [rsp+1B0h+var_150]; struct SplException::THResultException *
0x140011504  lea     rcx, [rbp+0B0h+pExceptionObject]; this
0x140011508  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14001150d  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140011514  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x140011518  call    _CxxThrowException_0
0x14001151e  xor     ebx, ebx
0x140011520  cmp     [rsp+1B0h+pData], rbx
0x140011525  jz      short loc_140011535
0x140011527  mov     rbx, [rsp+1B0h+pData]
0x14001152c  mov     [rsp+1B0h+pData], 0
0x140011535  lea     rcx, [rsp+1B0h+pData]
0x14001153a  call    ?Reset@?$TGenericSP@EV?$TAutoPtrArray@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtrArray<uchar>,uchar *,0,uchar const *>::Reset(void)
0x14001153f  nop
0x140011540  lea     rcx, [rsp+1B0h+phPrinter]; this
0x140011545  call    ?Free@SmartPrinterHandle@PrnExcept@@AEAAXXZ; PrnExcept::SmartPrinterHandle::Free(void)
0x14001154a  nop
0x14001154b  mov     rax, rbx
0x14001154e  mov     rcx, [rbp+0B0h+var_10]
0x140011555  xor     rcx, rsp; StackCookie
0x140011558  call    __security_check_cookie
0x14001155d  mov     rbx, [rsp+1B0h+arg_0]
0x140011565  add     rsp, 1B0h
0x14001156c  pop     rbp
0x14001156d  retn
```
