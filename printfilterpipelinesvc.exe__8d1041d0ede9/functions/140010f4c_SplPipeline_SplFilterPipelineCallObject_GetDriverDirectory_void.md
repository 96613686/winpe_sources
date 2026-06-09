# SplPipeline::SplFilterPipelineCallObject::GetDriverDirectory(void)

- ea: `0x140010f4c`
- end: `0x14001112c`
- name: `?GetDriverDirectory@SplFilterPipelineCallObject@SplPipeline@@AEAAXXZ`
- size: `480`
- prototype: `void __fastcall(LPBYTE *this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140012404`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140005358`
- `0x140009848`
- `0x140010f4c`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140046314`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140010ff7`
- `KERNEL32!GetLastError` at `0x140010ff7`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x140010f99`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x1400110b1`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x140010f99`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x1400110b1`

## string_xrefs

- `0x140011032`: `GetPrinterDriverDirectory failed.`
- `0x1400110e1`: `GetPrinterDriverDirectory failed.`

## pseudocode

```c
void __fastcall SplPipeline::SplFilterPipelineCallObject::GetDriverDirectory(LPBYTE *this)
{
  const struct SplException::TSystemException *v2; // r8
  const struct _GUID *v3; // r9
  signed int LastError; // ebx
  unsigned int v5; // r8d
  const struct SplException::TSystemException *v6; // r8
  const struct _GUID *v7; // r9
  DWORD v8; // edi
  unsigned __int128 v9; // rax
  void *v10; // rax
  NCoreLibrary *v11; // rcx
  unsigned int LastErrorAsHResult; // eax
  const struct SplException::TSystemException *v13; // r8
  const struct _GUID *v14; // r9
  DWORD cbBuf; // [rsp+20h] [rbp-E0h]
  DWORD cbBufa; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *pcbNeeded; // [rsp+28h] [rbp-D8h]
  const struct win_musl::TStringEllipseBase *pcbNeededa; // [rsp+28h] [rbp-D8h]
  HINSTANCE v19; // [rsp+30h] [rbp-D0h]
  DWORD v20[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[160]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+F0h] [rbp-10h] BYREF

  v20[0] = 0;
  if ( GetPrinterDriverDirectoryW(0, 0, 1u, 0, 0, v20) )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v21, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v21,
      0x8000FFFF,
      v2,
      v3,
      cbBuf,
      pcbNeeded,
      v19);
    SplException::TSystemException::Message((SplException::TSystemException *)v21, "Unexpected return value.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v21);
    throw (SplException::THResultException *)pExceptionObject;
  }
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v21, "-", 0);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v21,
      LastError,
      v6,
      v7,
      cbBuf,
      pcbNeeded,
      v19);
    SplException::TSystemException::Message((SplException::TSystemException *)v21, "GetPrinterDriverDirectory failed.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v21);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v8 = v20[0] >> 1;
  v9 = (v20[0] >> 1) * (unsigned __int128)2uLL;
  if ( !is_mul_ok(v20[0] >> 1, 2u) )
    *(_QWORD *)&v9 = -1;
  v10 = operator new(v9, *((const char **)&v9 + 1), v5);
  NCoreLibrary::TAutoPtrArray<wchar_t>::operator=(this + 16, v10);
  if ( !GetPrinterDriverDirectoryW(0, 0, 1u, this[16], 2 * v8, v20) )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v21, "-", 0);
    LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v11);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v21,
      LastErrorAsHResult,
      v13,
      v14,
      cbBufa,
      pcbNeededa,
      v19);
    SplException::TSystemException::Message((SplException::TSystemException *)v21, "GetPrinterDriverDirectory failed.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v21);
    throw (SplException::THResultException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x140010f4c  push    rbp
0x140010f4e  push    rbx
0x140010f4f  push    rsi
0x140010f50  push    rdi
0x140010f51  lea     rbp, [rsp-0A8h]
0x140010f59  sub     rsp, 1A8h
0x140010f60  mov     rax, cs:__security_cookie
0x140010f67  xor     rax, rsp
0x140010f6a  mov     [rbp+0C0h+var_30], rax
0x140010f71  mov     rsi, rcx
0x140010f74  mov     [rsp+1C0h+var_180], 0
0x140010f7c  lea     rax, [rsp+1C0h+var_180]
0x140010f81  mov     [rsp+1C0h+pcbNeeded], rax; struct win_musl::TStringEllipseBase *
0x140010f86  mov     [rsp+1C0h+cbBuf], 0; unsigned int
0x140010f8e  xor     r9d, r9d; pDriverDirectory
0x140010f91  xor     edx, edx; pEnvironment
0x140010f93  xor     ecx, ecx; pName
0x140010f95  lea     r8d, [r9+1]; Level
0x140010f99  call    cs:__imp_GetPrinterDriverDirectoryW
0x140010f9f  test    eax, eax
0x140010fa1  jz      short loc_140010FF7
0x140010fa3  xor     r8d, r8d; unsigned int
0x140010fa6  lea     rdx, asc_1400696D8; "-"
0x140010fad  lea     rcx, [rsp+1C0h+var_170]; this
0x140010fb2  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140010fb7  nop
0x140010fb8  mov     edx, 8000FFFFh; unsigned int
0x140010fbd  lea     rcx, [rsp+1C0h+var_170]; this
0x140010fc2  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140010fc7  lea     rdx, aUnexpectedRetu; "Unexpected return value."
0x140010fce  lea     rcx, [rsp+1C0h+var_170]; this
0x140010fd3  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140010fd8  lea     rdx, [rsp+1C0h+var_170]; struct SplException::THResultException *
0x140010fdd  lea     rcx, [rbp+0C0h+pExceptionObject]; this
0x140010fe1  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140010fe6  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140010fed  lea     rcx, [rbp+0C0h+pExceptionObject]; pExceptionObject
0x140010ff1  call    _CxxThrowException_0
0x140010ff7  call    cs:__imp_GetLastError
0x140010ffd  mov     ebx, eax
0x140010fff  cmp     eax, 7Ah ; 'z'
0x140011002  jz      short loc_140011062
0x140011004  xor     r8d, r8d; unsigned int
0x140011007  lea     rdx, asc_1400696D8; "-"
0x14001100e  lea     rcx, [rsp+1C0h+var_170]; this
0x140011013  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140011018  nop
0x140011019  test    ebx, ebx
0x14001101b  jle     short loc_140011026
0x14001101d  movzx   ebx, bx
0x140011020  or      ebx, 80070000h
0x140011026  mov     edx, ebx; unsigned int
0x140011028  lea     rcx, [rsp+1C0h+var_170]; this
0x14001102d  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140011032  lea     rdx, aGetprinterdriv; "GetPrinterDriverDirectory failed."
0x140011039  lea     rcx, [rsp+1C0h+var_170]; this
0x14001103e  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140011043  lea     rdx, [rsp+1C0h+var_170]; struct SplException::THResultException *
0x140011048  lea     rcx, [rbp+0C0h+pExceptionObject]; this
0x14001104c  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140011051  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140011058  lea     rcx, [rbp+0C0h+pExceptionObject]; pExceptionObject
0x14001105c  call    _CxxThrowException_0
0x140011062  mov     edi, [rsp+1C0h+var_180]
0x140011066  shr     edi, 1
0x140011068  mov     eax, 2
0x14001106d  mul     rdi
0x140011070  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140011077  cmovb   rax, rcx
0x14001107b  mov     rcx, rax; unsigned __int64
0x14001107e  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x140011083  lea     rbx, [rsi+80h]
0x14001108a  mov     rdx, rax
0x14001108d  mov     rcx, rbx
0x140011090  call    ??4?$TAutoPtrArray@_W@NCoreLibrary@@QEAAPEA_WPEA_W@Z; NCoreLibrary::TAutoPtrArray<wchar_t>::operator=(wchar_t *)
0x140011095  lea     eax, [rdi+rdi]
0x140011098  lea     rcx, [rsp+1C0h+var_180]
0x14001109d  mov     [rsp+1C0h+pcbNeeded], rcx; struct win_musl::TStringEllipseBase *
0x1400110a2  mov     [rsp+1C0h+cbBuf], eax; unsigned int
0x1400110a6  mov     r9, [rbx]; pDriverDirectory
0x1400110a9  xor     edx, edx; pEnvironment
0x1400110ab  xor     ecx, ecx; pName
0x1400110ad  lea     r8d, [rdx+1]; Level
0x1400110b1  call    cs:__imp_GetPrinterDriverDirectoryW
0x1400110b7  test    eax, eax
0x1400110b9  jnz     short loc_140011111
0x1400110bb  xor     r8d, r8d; unsigned int
0x1400110be  lea     rdx, asc_1400696D8; "-"
0x1400110c5  lea     rcx, [rsp+1C0h+var_170]; this
0x1400110ca  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x1400110cf  nop
0x1400110d0  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x1400110d5  mov     edx, eax; unsigned int
0x1400110d7  lea     rcx, [rsp+1C0h+var_170]; this
0x1400110dc  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x1400110e1  lea     rdx, aGetprinterdriv; "GetPrinterDriverDirectory failed."
0x1400110e8  lea     rcx, [rsp+1C0h+var_170]; this
0x1400110ed  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x1400110f2  lea     rdx, [rsp+1C0h+var_170]; struct SplException::THResultException *
0x1400110f7  lea     rcx, [rbp+0C0h+pExceptionObject]; this
0x1400110fb  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140011100  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140011107  lea     rcx, [rbp+0C0h+pExceptionObject]; pExceptionObject
0x14001110b  call    _CxxThrowException_0
0x140011111  mov     rcx, [rbp+0C0h+var_30]
0x140011118  xor     rcx, rsp; StackCookie
0x14001111b  call    __security_check_cookie
0x140011120  add     rsp, 1A8h
0x140011127  pop     rdi
0x140011128  pop     rsi
0x140011129  pop     rbx
0x14001112a  pop     rbp
0x14001112b  retn
```
