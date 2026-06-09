# PrnComps::TImgWriterFileItem::TImgWriterFileItem(NCoreLibrary::TCriticalSection &,PrnComps::TImgFilePool *,wchar_t const *,ulong,bool,bool)

- ea: `0x140018c3c`
- end: `0x140018ffa`
- name: `??0TImgWriterFileItem@PrnComps@@QEAA@AEAVTCriticalSection@NCoreLibrary@@PEAVTImgFilePool@1@PEB_WK_N3@Z`
- size: `958`
- prototype: `PrnComps::TImgWriterFileItem *__fastcall(PrnComps::TImgWriterFileItem *this, struct NCoreLibrary::TCriticalSection *, struct PrnComps::TImgFilePool *, const wchar_t *, unsigned int, bool, bool)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400182a0`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140005470`
- `0x1400071e8`
- `0x14000ea50`
- `0x140011728`
- `0x14001500c`
- `0x140018bd0`
- `0x140018bf8`
- `0x140018c3c`
- `0x140019be0`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x14004650c`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x140018d7f`
- `ADVAPI32!OpenThreadToken` at `0x140018daf`
- `ADVAPI32!OpenThreadToken` at `0x140018dde`
- `ADVAPI32!OpenThreadToken` at `0x140018d7f`
- `ADVAPI32!OpenThreadToken` at `0x140018daf`
- `ADVAPI32!OpenThreadToken` at `0x140018dde`
- `ADVAPI32!SetThreadToken` at `0x140018e12`
- `ADVAPI32!SetThreadToken` at `0x140018e94`
- `ADVAPI32!SetThreadToken` at `0x140018e12`
- `ADVAPI32!SetThreadToken` at `0x140018e94`
- `KERNEL32!GetLastError` at `0x140018d89`
- `KERNEL32!GetLastError` at `0x140018db9`
- `KERNEL32!GetLastError` at `0x140018de8`
- `KERNEL32!GetLastError` at `0x140018d89`
- `KERNEL32!GetLastError` at `0x140018db9`
- `KERNEL32!GetLastError` at `0x140018de8`
- `KERNEL32!CreateFileW` at `0x140018e70`
- `KERNEL32!CreateFileW` at `0x140018e70`
- `KERNEL32!GetCurrentThread` at `0x140018d6a`
- `KERNEL32!GetCurrentThread` at `0x140018d98`
- `KERNEL32!GetCurrentThread` at `0x140018dc9`
- `KERNEL32!GetCurrentThread` at `0x140018d6a`
- `KERNEL32!GetCurrentThread` at `0x140018d98`
- `KERNEL32!GetCurrentThread` at `0x140018dc9`
- `KERNEL32!CloseHandle` at `0x140018f0a`
- `KERNEL32!CloseHandle` at `0x140018f0a`

## string_xrefs

- `0x140018f52`: `TImgWriterFileItem CTOR OpenThreadToken failed with unexpected error`
- `0x140018fbd`: `TImgWriterFileItem CTOR OpenThreadToken failed with unexpected error`

## pseudocode

```c
PrnComps::TImgWriterFileItem *__fastcall PrnComps::TImgWriterFileItem::TImgWriterFileItem(
        PrnComps::TImgWriterFileItem *this,
        struct NCoreLibrary::TCriticalSection *a2,
        struct PrnComps::TImgFilePool *a3,
        const wchar_t *a4,
        unsigned int a5,
        bool a6,
        bool a7)
{
  int v11; // eax
  void *v12; // rdx
  const char *v13; // r8
  unsigned int v14; // r9d
  void *v15; // rdx
  HANDLE CurrentThread; // rax
  HANDLE v17; // rax
  HANDLE v18; // rax
  NCoreLibrary *v19; // rcx
  HANDLE FileW; // rax
  NCoreLibrary *v21; // rcx
  NCoreLibrary *v23; // rcx
  unsigned int v24; // eax
  int v25; // edx
  const char *v26; // r8
  unsigned int v27; // r9d
  NCoreLibrary *v28; // rcx
  unsigned int LastErrorAsFailHRNoBreak; // eax
  const struct SplException::TSystemException *v30; // r8
  const struct _GUID *v31; // r9
  unsigned int v32; // eax
  int v33; // edx
  const char *v34; // r8
  unsigned int v35; // r9d
  NCoreLibrary *v36; // rcx
  unsigned int v37; // eax
  const struct SplException::TSystemException *v38; // r8
  const struct _GUID *v39; // r9
  unsigned int v40; // eax
  int v41; // edx
  const char *v42; // r8
  unsigned int v43; // r9d
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  HINSTANCE hTemplateFile; // [rsp+30h] [rbp-D0h]
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  void *TokenHandle[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v49[160]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+100h] [rbp+0h] BYREF

  TokenHandle[1] = this;
  PrnComps::TImgFileItemBase::TImgFileItemBase(this);
  *(_QWORD *)this = &PrnComps::TImgWriterFileItem::`vftable'{for `PrnComps::TImgFileItemBase'};
  *((_QWORD *)this + 6) = &PrnComps::TImgWriterFileItem::`vftable'{for `IImgWriterFileItemX'};
  *((_QWORD *)this + 7) = a2;
  *((_DWORD *)this + 16) = 1953721460;
  *((_QWORD *)this + 9) = &NCoreLibrary::TLink::`vftable';
  *((_DWORD *)this + 20) = 1802398836;
  *((_QWORD *)this + 11) = (char *)this + 72;
  *((_QWORD *)this + 12) = (char *)this + 72;
  *((_DWORD *)this + 28) = 1802398836;
  *((_QWORD *)this + 15) = (char *)this + 104;
  *((_QWORD *)this + 16) = (char *)this + 104;
  *((_QWORD *)this + 13) = &PrnComps::TImgReaderFileItem::TEmbeddedLink::`vftable';
  *((_QWORD *)this + 17) = this;
  *((_QWORD *)this + 18) = a3;
  *((_QWORD *)this + 19) = &NCoreLibrary::TString::gszNullState;
  *((_DWORD *)this + 40) = a5;
  *((_BYTE *)this + 164) = 1;
  *((_DWORD *)this + 42) = 1;
  *((_BYTE *)this + 172) = a6;
  if ( a7 )
    *((_DWORD *)this + 42) = 0;
  v11 = NCoreLibrary::TString::Update((PrnComps::TImgWriterFileItem *)((char *)this + 152), a4);
  if ( v11 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v11, (int)v12, v13, v14);
  NCoreLibrary::TAutoHandleNT::TAutoHandleNT((NCoreLibrary::TAutoHandleNT *)&hObject, v12);
  NCoreLibrary::TAutoHandleNT::TAutoHandleNT((NCoreLibrary::TAutoHandleNT *)TokenHandle, v15);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xCu, 0, TokenHandle) && GetLastError() != 1008 )
    {
      v17 = GetCurrentThread();
      if ( !OpenThreadToken(v17, 0xCu, 1, TokenHandle) && GetLastError() != 1008 )
      {
        SplException::THResultException::THResultException((SplException::THResultException *)v49, "-", 0);
        LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v28);
        SplException::TSystemException::InternalInit(
          (SplException::TSystemException *)v49,
          LastErrorAsFailHRNoBreak,
          v30,
          v31,
          dwCreationDisposition,
          dwFlagsAndAttributes,
          hTemplateFile);
        SplException::TSystemException::Message(
          (SplException::TSystemException *)v49,
          "TImgWriterFileItem CTOR OpenThreadToken failed with unexpected error");
        SplException::THResultException::THResultException(
          (SplException::THResultException *)pExceptionObject,
          (const struct SplException::THResultException *)v49);
        throw (SplException::THResultException *)pExceptionObject;
      }
    }
  }
  else
  {
    v18 = GetCurrentThread();
    if ( !OpenThreadToken(v18, 0xCu, 0, TokenHandle) && GetLastError() != 1008 )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v49, "-", 0);
      v37 = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v36);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v49,
        v37,
        v38,
        v39,
        dwCreationDisposition,
        dwFlagsAndAttributes,
        hTemplateFile);
      SplException::TSystemException::Message(
        (SplException::TSystemException *)v49,
        "TImgWriterFileItem CTOR OpenThreadToken failed with unexpected error");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v49);
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  if ( TokenHandle[0] != (void *)-1LL && TokenHandle[0] && !SetThreadToken(0, 0) )
  {
    v40 = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v19);
    SplException::RealThrowFromHR((SplException *)v40, v41, v42, v43);
  }
  FileW = CreateFileW(
            *((LPCWSTR *)this + 19),
            0xC0000000,
            *((_BYTE *)this + 172) != 0 ? 3 : 7,
            0,
            2 * (unsigned int)a7 + 1,
            *((_DWORD *)this + 40) | (!a6 << 26),
            0);
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Attach(&hObject, FileW);
  if ( TokenHandle[0] != (void *)-1LL && TokenHandle[0] && !SetThreadToken(0, TokenHandle[0]) )
  {
    v23 = (NCoreLibrary *)hObject;
    if ( hObject != (HANDLE)-1LL && (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hObject);
      NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&hObject);
      hObject = (HANDLE)-1LL;
    }
    v24 = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v23);
    SplException::RealThrowFromHR((SplException *)v24, v25, v26, v27);
  }
  if ( hObject == (HANDLE)-1LL )
  {
    v32 = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v21);
    SplException::RealThrowFromHR((SplException *)v32, v33, v34, v35);
  }
  PrnComps::TImgFileItemBase::SetFileHandle(this, &hObject);
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(TokenHandle);
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&hObject);
  return this;
}

```

## disassembly

```asm
0x140018c3c  mov     [rsp-8+arg_8], rbx
0x140018c41  push    rbp
0x140018c42  push    rsi
0x140018c43  push    rdi
0x140018c44  push    r14
0x140018c46  push    r15
0x140018c48  lea     rbp, [rsp-0B0h]
0x140018c50  sub     rsp, 1B0h
0x140018c57  mov     rax, cs:__security_cookie
0x140018c5e  xor     rax, rsp
0x140018c61  mov     [rbp+0D0h+var_30], rax
0x140018c68  mov     r14, r9
0x140018c6b  mov     rdi, r8
0x140018c6e  mov     rbx, rdx
0x140018c71  mov     rsi, rcx
0x140018c74  mov     [rsp+1D0h+var_180], rcx
0x140018c79  call    ??0TImgFileItemBase@PrnComps@@QEAA@XZ; PrnComps::TImgFileItemBase::TImgFileItemBase(void)
0x140018c7e  nop
0x140018c7f  lea     rax, ??_7TImgWriterFileItem@PrnComps@@6BTImgFileItemBase@1@@; const PrnComps::TImgWriterFileItem::`vftable'{for `PrnComps::TImgFileItemBase'}
0x140018c86  mov     [rsi], rax
0x140018c89  lea     rax, ??_7TImgWriterFileItem@PrnComps@@6BIImgWriterFileItemX@@@; const PrnComps::TImgWriterFileItem::`vftable'{for `IImgWriterFileItemX'}
0x140018c90  mov     [rsi+30h], rax
0x140018c94  mov     [rsi+38h], rbx
0x140018c98  mov     dword ptr [rsi+40h], 74736C74h
0x140018c9f  lea     rax, [rsi+48h]
0x140018ca3  lea     rcx, ??_7TLink@NCoreLibrary@@6B@; const NCoreLibrary::TLink::`vftable'
0x140018caa  mov     [rax], rcx
0x140018cad  mov     ecx, 6B6E6C74h
0x140018cb2  mov     [rax+8], ecx
0x140018cb5  mov     [rax+10h], rax
0x140018cb9  mov     [rax+18h], rax
0x140018cbd  lea     rax, [rsi+68h]
0x140018cc1  mov     [rax+8], ecx
0x140018cc4  mov     [rax+10h], rax
0x140018cc8  mov     [rax+18h], rax
0x140018ccc  lea     rcx, ??_7TEmbeddedLink@TImgReaderFileItem@PrnComps@@6B@; const PrnComps::TImgReaderFileItem::TEmbeddedLink::`vftable'
0x140018cd3  mov     [rax], rcx
0x140018cd6  mov     [rax+20h], rsi
0x140018cda  mov     [rsi+90h], rdi
0x140018ce1  lea     rdi, [rsi+98h]
0x140018ce8  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PA_WA; wchar_t near * NCoreLibrary::TString::gszNullState
0x140018cef  mov     [rdi], rax
0x140018cf2  mov     eax, [rbp+0D0h+arg_20]
0x140018cf8  mov     [rsi+0A0h], eax
0x140018cfe  mov     byte ptr [rsi+0A4h], 1
0x140018d05  mov     dword ptr [rsi+0A8h], 1
0x140018d0f  movzx   r15d, [rbp+0D0h+arg_28]
0x140018d17  mov     [rsi+0ACh], r15b
0x140018d1e  cmp     [rbp+0D0h+arg_30], 0
0x140018d25  jz      short loc_140018D31
0x140018d27  mov     dword ptr [rsi+0A8h], 0
0x140018d31  mov     rdx, r14; wchar_t *
0x140018d34  mov     rcx, rdi; this
0x140018d37  call    ?Update@TString@NCoreLibrary@@QEAAJPEB_W@Z; NCoreLibrary::TString::Update(wchar_t const *)
0x140018d3c  test    eax, eax
0x140018d3e  js      loc_140018F8F
0x140018d44  lea     rcx, [rsp+1D0h+hObject]; this
0x140018d49  call    ??0TAutoHandleNT@NCoreLibrary@@QEAA@PEAX@Z; NCoreLibrary::TAutoHandleNT::TAutoHandleNT(void *)
0x140018d4e  nop
0x140018d4f  lea     rcx, [rsp+1D0h+TokenHandle]; this
0x140018d54  call    ??0TAutoHandleNT@NCoreLibrary@@QEAA@PEAX@Z; NCoreLibrary::TAutoHandleNT::TAutoHandleNT(void *)
0x140018d59  nop
0x140018d5a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x140018d61  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x140018d66  test    al, al
0x140018d68  jz      short loc_140018DC9
0x140018d6a  call    cs:__imp_GetCurrentThread
0x140018d70  lea     r9, [rsp+1D0h+TokenHandle]; TokenHandle
0x140018d75  xor     r8d, r8d; OpenAsSelf
0x140018d78  lea     edx, [r8+0Ch]; DesiredAccess
0x140018d7c  mov     rcx, rax; ThreadHandle
0x140018d7f  call    cs:__imp_OpenThreadToken
0x140018d85  test    eax, eax
0x140018d87  jnz     short loc_140018DFB
0x140018d89  call    cs:__imp_GetLastError
0x140018d8f  mov     ebx, 3F0h
0x140018d94  cmp     eax, ebx
0x140018d96  jz      short loc_140018DFB
0x140018d98  call    cs:__imp_GetCurrentThread
0x140018d9e  lea     r9, [rsp+1D0h+TokenHandle]; TokenHandle
0x140018da3  mov     edx, 0Ch; DesiredAccess
0x140018da8  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x140018dac  mov     rcx, rax; ThreadHandle
0x140018daf  call    cs:__imp_OpenThreadToken
0x140018db5  test    eax, eax
0x140018db7  jnz     short loc_140018DFB
0x140018db9  call    cs:__imp_GetLastError
0x140018dbf  cmp     eax, ebx
0x140018dc1  jnz     loc_140018F2C
0x140018dc7  jmp     short loc_140018DFB
0x140018dc9  call    cs:__imp_GetCurrentThread
0x140018dcf  lea     r9, [rsp+1D0h+TokenHandle]; TokenHandle
0x140018dd4  xor     r8d, r8d; OpenAsSelf
0x140018dd7  lea     edx, [r8+0Ch]; DesiredAccess
0x140018ddb  mov     rcx, rax; ThreadHandle
0x140018dde  call    cs:__imp_OpenThreadToken
0x140018de4  test    eax, eax
0x140018de6  jnz     short loc_140018DFB
0x140018de8  call    cs:__imp_GetLastError
0x140018dee  mov     ebx, 3F0h
0x140018df3  cmp     eax, ebx
0x140018df5  jnz     loc_140018F97
0x140018dfb  mov     rax, [rsp+1D0h+TokenHandle]
0x140018e00  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140018e04  cmp     rax, rbx
0x140018e07  jz      short loc_140018E20
0x140018e09  test    rax, rax
0x140018e0c  jz      short loc_140018E20
0x140018e0e  xor     edx, edx; Token
0x140018e10  xor     ecx, ecx; Thread
0x140018e12  call    cs:__imp_SetThreadToken
0x140018e18  test    eax, eax
0x140018e1a  jz      loc_140018FED
0x140018e20  mov     r9d, r15d
0x140018e23  xor     r9d, 1
0x140018e27  shl     r9d, 1Ah
0x140018e2b  or      r9d, [rsi+0A0h]
0x140018e32  movzx   eax, [rbp+0D0h+arg_30]
0x140018e39  lea     edx, ds:1[rax*2]
0x140018e40  mov     al, [rsi+0ACh]
0x140018e46  neg     al
0x140018e48  sbb     r8d, r8d
0x140018e4b  and     r8d, 0FFFFFFFCh
0x140018e4f  add     r8d, 7; dwShareMode
0x140018e53  mov     [rsp+1D0h+hTemplateFile], 0; hTemplateFile
0x140018e5c  mov     dword ptr [rsp+1D0h+dwFlagsAndAttributes], r9d; dwFlagsAndAttributes
0x140018e61  mov     [rsp+1D0h+dwCreationDisposition], edx; dwCreationDisposition
0x140018e65  xor     r9d, r9d; lpSecurityAttributes
0x140018e68  mov     edx, 0C0000000h; dwDesiredAccess
0x140018e6d  mov     rcx, [rdi]; lpFileName
0x140018e70  call    cs:__imp_CreateFileW
0x140018e76  mov     rdx, rax
0x140018e79  lea     rcx, [rsp+1D0h+hObject]
0x140018e7e  call    ?Attach@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXPEAX@Z; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Attach(void *)
0x140018e83  mov     rdx, [rsp+1D0h+TokenHandle]; Token
0x140018e88  cmp     rdx, rbx
0x140018e8b  jz      short loc_140018E9E
0x140018e8d  test    rdx, rdx
0x140018e90  jz      short loc_140018E9E
0x140018e92  xor     ecx, ecx; Thread
0x140018e94  call    cs:__imp_SetThreadToken
0x140018e9a  test    eax, eax
0x140018e9c  jz      short loc_140018EF6
0x140018e9e  cmp     [rsp+1D0h+hObject], rbx
0x140018ea3  jz      loc_140018F82
0x140018ea9  lea     rdx, [rsp+1D0h+hObject]; void **
0x140018eae  mov     rcx, rsi; this
0x140018eb1  call    ?SetFileHandle@TImgFileItemBase@PrnComps@@QEAAXPEAPEAX@Z; PrnComps::TImgFileItemBase::SetFileHandle(void * *)
0x140018eb6  nop
0x140018eb7  lea     rcx, [rsp+1D0h+TokenHandle]
0x140018ebc  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x140018ec1  nop
0x140018ec2  lea     rcx, [rsp+1D0h+hObject]
0x140018ec7  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x140018ecc  nop
0x140018ecd  mov     rax, rsi
0x140018ed0  mov     rcx, [rbp+0D0h+var_30]
0x140018ed7  xor     rcx, rsp; StackCookie
0x140018eda  call    __security_check_cookie
0x140018edf  mov     rbx, [rsp+1D0h+arg_8]
0x140018ee7  add     rsp, 1B0h
0x140018eee  pop     r15
0x140018ef0  pop     r14
0x140018ef2  pop     rdi
0x140018ef3  pop     rsi
0x140018ef4  pop     rbp
0x140018ef5  retn
0x140018ef6  mov     rcx, [rsp+1D0h+hObject]; hObject
0x140018efb  cmp     rcx, rbx
0x140018efe  jz      short loc_140018F1F
0x140018f00  lea     rax, [rcx-1]
0x140018f04  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140018f08  ja      short loc_140018F1F
0x140018f0a  call    cs:__imp_CloseHandle
0x140018f10  lea     rcx, [rsp+1D0h+hObject]
0x140018f15  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x140018f1a  mov     [rsp+1D0h+hObject], rbx
0x140018f1f  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140018f24  mov     ecx, eax; this
0x140018f26  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140018f2c  xor     r8d, r8d; unsigned int
0x140018f2f  lea     rdx, asc_1400696D8; "-"
0x140018f36  lea     rcx, [rsp+1D0h+var_170]; this
0x140018f3b  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140018f40  nop
0x140018f41  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140018f46  mov     edx, eax; unsigned int
0x140018f48  lea     rcx, [rsp+1D0h+var_170]; this
0x140018f4d  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140018f52  lea     rdx, aTimgwriterfile; "TImgWriterFileItem CTOR OpenThreadToken"...
0x140018f59  lea     rcx, [rsp+1D0h+var_170]; this
0x140018f5e  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140018f63  lea     rdx, [rsp+1D0h+var_170]; struct SplException::THResultException *
0x140018f68  lea     rcx, [rbp+0D0h+pExceptionObject]; this
0x140018f6c  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140018f71  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140018f78  lea     rcx, [rbp+0D0h+pExceptionObject]; pExceptionObject
0x140018f7c  call    _CxxThrowException_0
0x140018f82  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140018f87  mov     ecx, eax; this
0x140018f89  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140018f8f  mov     ecx, eax; this
0x140018f91  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140018f97  xor     r8d, r8d; unsigned int
0x140018f9a  lea     rdx, asc_1400696D8; "-"
0x140018fa1  lea     rcx, [rsp+1D0h+var_170]; this
0x140018fa6  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140018fab  nop
0x140018fac  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140018fb1  mov     edx, eax; unsigned int
0x140018fb3  lea     rcx, [rsp+1D0h+var_170]; this
0x140018fb8  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140018fbd  lea     rdx, aTimgwriterfile; "TImgWriterFileItem CTOR OpenThreadToken"...
0x140018fc4  lea     rcx, [rsp+1D0h+var_170]; this
0x140018fc9  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140018fce  lea     rdx, [rsp+1D0h+var_170]; struct SplException::THResultException *
0x140018fd3  lea     rcx, [rbp+0D0h+pExceptionObject]; this
0x140018fd7  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140018fdc  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140018fe3  lea     rcx, [rbp+0D0h+pExceptionObject]; pExceptionObject
0x140018fe7  call    _CxxThrowException_0
0x140018fed  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140018ff2  mov     ecx, eax; this
0x140018ff4  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
```
