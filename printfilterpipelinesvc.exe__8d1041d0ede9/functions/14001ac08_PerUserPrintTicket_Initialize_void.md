# PerUserPrintTicket::Initialize(void)

- ea: `0x14001ac08`
- end: `0x14001aeb2`
- name: `?Initialize@PerUserPrintTicket@@AEAAXXZ`
- size: `682`
- prototype: `void __fastcall(PerUserPrintTicket *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14001a79c`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140005358`
- `0x140009848`
- `0x14000d494`
- `0x14000fa68`
- `0x14000fb28`
- `0x140016740`
- `0x140016934`
- `0x14001a848`
- `0x14001ac08`
- `0x14002139c`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140046314`
- `0x14004650c`

## import_xrefs

- `WINSPOOL!DocumentPropertiesW` at `0x14001ac66`
- `WINSPOOL!DocumentPropertiesW` at `0x14001ad03`
- `WINSPOOL!DocumentPropertiesW` at `0x14001ac66`
- `WINSPOOL!DocumentPropertiesW` at `0x14001ad03`
- `prntvpt!__imp_PTOpenProvider` at `0x14001ae28`
- `prntvpt!__imp_PTOpenProvider` at `0x14001ae28`
- `prntvpt!__imp_PTCloseProvider` at `0x14001ae73`
- `prntvpt!__imp_PTCloseProvider` at `0x14001ae73`
- `prntvpt!__imp_PTConvertDevModeToPrintTicket` at `0x14001ae57`
- `prntvpt!__imp_PTConvertDevModeToPrintTicket` at `0x14001ae57`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall PerUserPrintTicket::Initialize(PerUserPrintTicket *this)
{
  LONG v2; // eax
  const char *v3; // rdx
  unsigned int v4; // r8d
  NCoreLibrary *v5; // rcx
  unsigned int LastErrorAsHResult; // eax
  const struct SplException::TSystemException *v7; // r8
  const struct _GUID *v8; // r9
  void *v9; // rax
  PDEVMODEW v10; // rsi
  NCoreLibrary *v11; // rcx
  unsigned int v12; // eax
  const struct SplException::TSystemException *v13; // r8
  const struct _GUID *v14; // r9
  const char *v15; // rdx
  unsigned int v16; // r8d
  UnlockedSpillBuffer *v17; // rax
  UnlockedSpillBuffer *v18; // rcx
  const char *v19; // rdx
  unsigned int v20; // r8d
  PrintWriteStreamToIStream *v21; // rax
  PrintWriteStreamToIStream *v22; // rcx
  void *v23; // rdi
  HRESULT v24; // eax
  int v25; // edx
  const char *v26; // r8
  unsigned int v27; // r9d
  HRESULT v28; // eax
  int v29; // edx
  const char *v30; // r8
  unsigned int v31; // r9d
  unsigned int pDevModeInput; // [rsp+20h] [rbp-E0h]
  unsigned int pDevModeInputa; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *fMode; // [rsp+28h] [rbp-D8h]
  const struct win_musl::TStringEllipseBase *fModea; // [rsp+28h] [rbp-D8h]
  HINSTANCE v36; // [rsp+30h] [rbp-D0h]
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  HPTPROVIDER phProvider; // [rsp+48h] [rbp-B8h] BYREF
  PDEVMODEW pDevModeOutput; // [rsp+50h] [rbp-B0h] BYREF
  UnlockedSpillBuffer *v40; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v41[160]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+100h] [rbp+0h] BYREF

  pDevModeOutput = 0;
  PrnExcept::ImpersonateTokenThroughScope::ImpersonateTokenThroughScope(&TokenHandle, *((HANDLE *)this + 8));
  v2 = DocumentPropertiesW(0, *((HANDLE *)this + 7), *((LPWSTR *)this + 6), 0, 0, 0);
  if ( v2 < 0 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v41, "-", 0);
    LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v5);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v41,
      LastErrorAsHResult,
      v7,
      v8,
      pDevModeInput,
      fMode,
      v36);
    SplException::TSystemException::Message((SplException::TSystemException *)v41, "DocumentProperties failed");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v41);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v9 = operator new(v2 + 200, v3, v4);
  NCoreLibrary::TAutoPtrArray<wchar_t>::operator=(&pDevModeOutput, v9);
  v10 = pDevModeOutput;
  if ( DocumentPropertiesW(0, *((HANDLE *)this + 7), *((LPWSTR *)this + 6), pDevModeOutput, 0, 2u) < 0 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v41, "-", 0);
    v12 = NCoreLibrary::GetLastErrorAsHResult(v11);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v41,
      v12,
      v13,
      v14,
      pDevModeInputa,
      fModea,
      v36);
    SplException::TSystemException::Message((SplException::TSystemException *)v41, "DocumentProperties failed");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v41);
    throw (SplException::THResultException *)pExceptionObject;
  }
  PrnExcept::ImpersonateTokenThroughScope::~ImpersonateTokenThroughScope(&TokenHandle);
  v17 = (UnlockedSpillBuffer *)operator new(0x50u, v15, v16);
  v40 = v17;
  if ( v17 )
    v18 = UnlockedSpillBuffer::UnlockedSpillBuffer(
            v17,
            *((struct IImgFilePool **)this + 3),
            *((struct IMemoryPool **)this + 4));
  else
    v18 = 0;
  TokenHandle = (void *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = v18;
  PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>((__int64 *)&TokenHandle);
  TokenHandle = 0;
  v21 = (PrintWriteStreamToIStream *)operator new(0x30u, v19, v20);
  v40 = v21;
  if ( v21 )
    v22 = PrintWriteStreamToIStream::PrintWriteStreamToIStream(
            v21,
            (struct IPrintWriteStream *)((*((_QWORD *)this + 5) + 16LL) & -(__int64)(*((_QWORD *)this + 5) != 0)));
  else
    v22 = 0;
  v23 = (void *)(((unsigned __int64)v22 + 16) & -(__int64)(v22 != 0));
  v40 = 0;
  TokenHandle = v23;
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)&v40);
  phProvider = 0;
  v24 = PTOpenProvider(*((PCWSTR *)this + 6), 1u, &phProvider);
  if ( v24 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v24, v25, v26, v27);
  v28 = PTConvertDevModeToPrintTicket(
          phProvider,
          v10->dmSize + v10->dmDriverExtra,
          (PDEVMODE)v10,
          kPTJobScope,
          (IStream *)v23);
  if ( v28 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v28, v29, v30, v31);
  if ( phProvider )
  {
    PTCloseProvider(phProvider);
    phProvider = 0;
  }
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)&TokenHandle);
  NCoreLibrary::TGenericSP<unsigned char,NCoreLibrary::TAutoPtrArray<unsigned char>,unsigned char *,0,unsigned char const *>::Reset(&pDevModeOutput);
}

```

## disassembly

```asm
0x14001ac08  push    rbp
0x14001ac0a  push    rbx
0x14001ac0b  push    rsi
0x14001ac0c  push    rdi
0x14001ac0d  lea     rbp, [rsp-0B8h]
0x14001ac15  sub     rsp, 1B8h
0x14001ac1c  mov     rax, cs:__security_cookie
0x14001ac23  xor     rax, rsp
0x14001ac26  mov     [rbp+0D0h+var_30], rax
0x14001ac2d  mov     rbx, rcx
0x14001ac30  mov     [rsp+1D0h+pDevModeOutput], 0
0x14001ac39  mov     rdx, [rcx+40h]; Token
0x14001ac3d  lea     rcx, [rsp+1D0h+TokenHandle]; TokenHandle
0x14001ac42  call    ??0ImpersonateTokenThroughScope@PrnExcept@@QEAA@PEAX@Z; PrnExcept::ImpersonateTokenThroughScope::ImpersonateTokenThroughScope(void *)
0x14001ac47  nop
0x14001ac48  mov     dword ptr [rsp+1D0h+fMode], 0; struct win_musl::TStringEllipseBase *
0x14001ac50  mov     [rsp+1D0h+pDevModeInput], 0; unsigned int
0x14001ac59  xor     r9d, r9d; pDevModeOutput
0x14001ac5c  mov     r8, [rbx+30h]; pDeviceName
0x14001ac60  mov     rdx, [rbx+38h]; hPrinter
0x14001ac64  xor     ecx, ecx; hWnd
0x14001ac66  call    cs:__imp_DocumentPropertiesW
0x14001ac6c  test    eax, eax
0x14001ac6e  jns     short loc_14001ACC6
0x14001ac70  xor     r8d, r8d; unsigned int
0x14001ac73  lea     rdx, asc_1400696D8; "-"
0x14001ac7a  lea     rcx, [rsp+1D0h+var_170]; this
0x14001ac7f  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14001ac84  nop
0x14001ac85  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x14001ac8a  mov     edx, eax; unsigned int
0x14001ac8c  lea     rcx, [rsp+1D0h+var_170]; this
0x14001ac91  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x14001ac96  lea     rdx, aDocumentproper; "DocumentProperties failed"
0x14001ac9d  lea     rcx, [rsp+1D0h+var_170]; this
0x14001aca2  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x14001aca7  lea     rdx, [rsp+1D0h+var_170]; struct SplException::THResultException *
0x14001acac  lea     rcx, [rbp+0D0h+pExceptionObject]; this
0x14001acb0  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14001acb5  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x14001acbc  lea     rcx, [rbp+0D0h+pExceptionObject]; pExceptionObject
0x14001acc0  call    _CxxThrowException_0
0x14001acc6  add     eax, 0C8h
0x14001accb  movsxd  rcx, eax; unsigned __int64
0x14001acce  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x14001acd3  mov     rdx, rax
0x14001acd6  lea     rcx, [rsp+1D0h+pDevModeOutput]
0x14001acdb  call    ??4?$TAutoPtrArray@_W@NCoreLibrary@@QEAAPEA_WPEA_W@Z; NCoreLibrary::TAutoPtrArray<wchar_t>::operator=(wchar_t *)
0x14001ace0  mov     rsi, [rsp+1D0h+pDevModeOutput]
0x14001ace5  mov     dword ptr [rsp+1D0h+fMode], 2; struct win_musl::TStringEllipseBase *
0x14001aced  mov     [rsp+1D0h+pDevModeInput], 0; unsigned int
0x14001acf6  mov     r9, rsi; pDevModeOutput
0x14001acf9  mov     r8, [rbx+30h]; pDeviceName
0x14001acfd  mov     rdx, [rbx+38h]; hPrinter
0x14001ad01  xor     ecx, ecx; hWnd
0x14001ad03  call    cs:__imp_DocumentPropertiesW
0x14001ad09  test    eax, eax
0x14001ad0b  jns     short loc_14001AD63
0x14001ad0d  xor     r8d, r8d; unsigned int
0x14001ad10  lea     rdx, asc_1400696D8; "-"
0x14001ad17  lea     rcx, [rsp+1D0h+var_170]; this
0x14001ad1c  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14001ad21  nop
0x14001ad22  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x14001ad27  mov     edx, eax; unsigned int
0x14001ad29  lea     rcx, [rsp+1D0h+var_170]; this
0x14001ad2e  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x14001ad33  lea     rdx, aDocumentproper; "DocumentProperties failed"
0x14001ad3a  lea     rcx, [rsp+1D0h+var_170]; this
0x14001ad3f  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x14001ad44  lea     rdx, [rsp+1D0h+var_170]; struct SplException::THResultException *
0x14001ad49  lea     rcx, [rbp+0D0h+pExceptionObject]; this
0x14001ad4d  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14001ad52  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x14001ad59  lea     rcx, [rbp+0D0h+pExceptionObject]; pExceptionObject
0x14001ad5d  call    _CxxThrowException_0
0x14001ad63  lea     rcx, [rsp+1D0h+TokenHandle]; this
0x14001ad68  call    ??1ImpersonateTokenThroughScope@PrnExcept@@QEAA@XZ; PrnExcept::ImpersonateTokenThroughScope::~ImpersonateTokenThroughScope(void)
0x14001ad6d  mov     ecx, 50h ; 'P'; unsigned __int64
0x14001ad72  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x14001ad77  mov     [rsp+1D0h+var_178], rax
0x14001ad7c  test    rax, rax
0x14001ad7f  jz      short loc_14001AD96
0x14001ad81  mov     r8, [rbx+20h]; struct IMemoryPool *
0x14001ad85  mov     rdx, [rbx+18h]; struct IImgFilePool *
0x14001ad89  mov     rcx, rax; this
0x14001ad8c  call    ??0UnlockedSpillBuffer@@QEAA@PEAUIImgFilePool@@PEAUIMemoryPool@@@Z; UnlockedSpillBuffer::UnlockedSpillBuffer(IImgFilePool *,IMemoryPool *)
0x14001ad91  mov     rcx, rax
0x14001ad94  jmp     short loc_14001AD98
0x14001ad96  xor     ecx, ecx
0x14001ad98  mov     rax, [rbx+28h]
0x14001ad9c  mov     [rsp+1D0h+TokenHandle], rax
0x14001ada1  mov     [rbx+28h], rcx
0x14001ada5  lea     rcx, [rsp+1D0h+TokenHandle]
0x14001adaa  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x14001adaf  mov     [rsp+1D0h+TokenHandle], 0
0x14001adb8  mov     ecx, 30h ; '0'; unsigned __int64
0x14001adbd  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x14001adc2  mov     [rsp+1D0h+var_178], rax
0x14001adc7  test    rax, rax
0x14001adca  jz      short loc_14001ADEA
0x14001adcc  mov     rcx, [rbx+28h]
0x14001add0  lea     r8, [rcx+10h]
0x14001add4  neg     rcx
0x14001add7  sbb     rdx, rdx
0x14001adda  and     rdx, r8; struct IPrintWriteStream *
0x14001addd  mov     rcx, rax; this
0x14001ade0  call    ??0PrintWriteStreamToIStream@@QEAA@PEAUIPrintWriteStream@@@Z; PrintWriteStreamToIStream::PrintWriteStreamToIStream(IPrintWriteStream *)
0x14001ade5  mov     rcx, rax
0x14001ade8  jmp     short loc_14001ADEC
0x14001adea  xor     ecx, ecx
0x14001adec  lea     rax, [rcx+10h]
0x14001adf0  neg     rcx
0x14001adf3  sbb     rdi, rdi
0x14001adf6  and     rdi, rax
0x14001adf9  mov     [rsp+1D0h+var_178], 0
0x14001ae02  mov     [rsp+1D0h+TokenHandle], rdi
0x14001ae07  lea     rcx, [rsp+1D0h+var_178]
0x14001ae0c  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14001ae11  mov     [rsp+1D0h+phProvider], 0
0x14001ae1a  lea     r8, [rsp+1D0h+phProvider]; phProvider
0x14001ae1f  mov     edx, 1; dwVersion
0x14001ae24  mov     rcx, [rbx+30h]; pszPrinterName
0x14001ae28  call    cs:__imp_PTOpenProvider
0x14001ae2e  test    eax, eax
0x14001ae30  jns     short loc_14001AE3A
0x14001ae32  mov     ecx, eax; this
0x14001ae34  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14001ae3a  movzx   edx, word ptr [rsi+46h]
0x14001ae3e  movzx   eax, word ptr [rsi+44h]
0x14001ae42  add     edx, eax; cbDevmode
0x14001ae44  mov     [rsp+1D0h+pDevModeInput], rdi; pPrintTicket
0x14001ae49  mov     r9d, 2; scope
0x14001ae4f  mov     r8, rsi; pDevmode
0x14001ae52  mov     rcx, [rsp+1D0h+phProvider]; hProvider
0x14001ae57  call    cs:__imp_PTConvertDevModeToPrintTicket
0x14001ae5d  test    eax, eax
0x14001ae5f  jns     short loc_14001AE69
0x14001ae61  mov     ecx, eax; this
0x14001ae63  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14001ae69  mov     rcx, [rsp+1D0h+phProvider]; hProvider
0x14001ae6e  test    rcx, rcx
0x14001ae71  jz      short loc_14001AE82
0x14001ae73  call    cs:__imp_PTCloseProvider
0x14001ae79  mov     [rsp+1D0h+phProvider], 0
0x14001ae82  lea     rcx, [rsp+1D0h+TokenHandle]
0x14001ae87  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14001ae8c  nop
0x14001ae8d  lea     rcx, [rsp+1D0h+pDevModeOutput]
0x14001ae92  call    ?Reset@?$TGenericSP@EV?$TAutoPtrArray@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtrArray<uchar>,uchar *,0,uchar const *>::Reset(void)
0x14001ae97  mov     rcx, [rbp+0D0h+var_30]
0x14001ae9e  xor     rcx, rsp; StackCookie
0x14001aea1  call    __security_check_cookie
0x14001aea6  add     rsp, 1B8h
0x14001aead  pop     rdi
0x14001aeae  pop     rsi
0x14001aeaf  pop     rbx
0x14001aeb0  pop     rbp
0x14001aeb1  retn
```
