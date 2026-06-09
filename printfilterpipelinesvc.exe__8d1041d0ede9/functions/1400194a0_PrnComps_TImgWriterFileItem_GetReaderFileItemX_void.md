# PrnComps::TImgWriterFileItem::GetReaderFileItemX(void)

- ea: `0x1400194a0`
- end: `0x1400198a9`
- name: `?GetReaderFileItemX@TImgWriterFileItem@PrnComps@@UEAAPEAUIImgFileItem@@XZ`
- size: `1033`
- prototype: `struct IImgFileItem *__fastcall(PrnComps::TImgWriterFileItem *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400193e0`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140005470`
- `0x1400071e8`
- `0x14000ea50`
- `0x140011728`
- `0x1400172e8`
- `0x1400177d0`
- `0x1400177f8`
- `0x140018bd0`
- `0x140018bf8`
- `0x1400194a0`
- `0x140019be0`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140046314`
- `0x14004650c`
- `0x14005c024`
- `0x140063010`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x1400195e6`
- `ADVAPI32!OpenThreadToken` at `0x1400195e6`
- `ADVAPI32!SetThreadToken` at `0x140019615`
- `ADVAPI32!SetThreadToken` at `0x14001967e`
- `ADVAPI32!SetThreadToken` at `0x140019615`
- `ADVAPI32!SetThreadToken` at `0x14001967e`
- `KERNEL32!GetLastError` at `0x1400195f0`
- `KERNEL32!GetLastError` at `0x1400195f0`
- `KERNEL32!LeaveCriticalSection` at `0x140019577`
- `KERNEL32!LeaveCriticalSection` at `0x140019577`
- `KERNEL32!SetFilePointerEx` at `0x1400197ba`
- `KERNEL32!SetFilePointerEx` at `0x1400197ba`
- `KERNEL32!CreateFileW` at `0x140019659`
- `KERNEL32!CreateFileW` at `0x140019659`
- `KERNEL32!GetCurrentThread` at `0x1400195aa`
- `KERNEL32!GetCurrentThread` at `0x1400195d1`
- `KERNEL32!GetCurrentThread` at `0x1400195aa`
- `KERNEL32!GetCurrentThread` at `0x1400195d1`

## string_xrefs

- `0x1400197fc`: `GetReaderFileItemX OpenThreadToken failed with unexpected error`
- `0x14001985f`: `GetReaderFileItemX OpenThreadToken failed with unexpected error`

## pseudocode

```c
struct IImgFileItem *__fastcall PrnComps::TImgWriterFileItem::GetReaderFileItemX(PrnComps::TImgWriterFileItem *this)
{
  PrnComps::TImgFileItemBase *v2; // rbx
  char *v3; // r13
  NCoreLibrary::TCriticalSection *v4; // rdi
  _QWORD *v5; // r8
  PrnComps::TImgFileItemBase *v6; // rsi
  PrnComps::TImgFileItemBase *v7; // r15
  void *v9; // rdx
  HANDLE CurrentThread; // rax
  void **v11; // r9
  unsigned int v12; // eax
  HANDLE v13; // rax
  NCoreLibrary *v14; // rcx
  HANDLE FileW; // rax
  NCoreLibrary *v16; // rcx
  unsigned int v17; // r8d
  const char *v18; // rdx
  PrnComps::TImgFileItemBase *v19; // rax
  char v20; // di
  void *v22; // rcx
  NCoreLibrary *v23; // rcx
  unsigned int v24; // eax
  int v25; // edx
  const char *v26; // r8
  unsigned int v27; // r9d
  NCoreLibrary *v28; // rcx
  unsigned int v29; // eax
  const struct SplException::TSystemException *v30; // r8
  const struct _GUID *v31; // r9
  unsigned int LastErrorAsFailHRNoBreak; // eax
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
  unsigned int v44; // eax
  int v45; // edx
  const char *v46; // r8
  unsigned int v47; // r9d
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  HINSTANCE hTemplateFile; // [rsp+30h] [rbp-D0h]
  LARGE_INTEGER liDistanceToMove; // [rsp+40h] [rbp-C0h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  PrnComps::TImgFileItemBase *v53; // [rsp+50h] [rbp-B0h] BYREF
  PrnComps::TImgFileItemBase *v54; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v55[160]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+100h] [rbp+0h] BYREF

  v2 = 0;
  v53 = 0;
  v3 = (char *)this - 48;
  v4 = (NCoreLibrary::TCriticalSection *)*((_QWORD *)this + 1);
  v54 = v4;
  NCoreLibrary::TCriticalSection::Enter(v4);
  v5 = (_QWORD *)*((_QWORD *)this + 6);
  *(_QWORD *)(v5[2] + 24LL) = v5[3];
  *(_QWORD *)(v5[3] + 16LL) = v5[2];
  v5[2] = v5;
  v5[3] = v5;
  if ( v5 == (_QWORD *)((char *)this + 24) )
    v5 = 0;
  if ( v5 )
  {
    v2 = (PrnComps::TImgFileItemBase *)v5[4];
    liDistanceToMove.QuadPart = 0;
    v53 = v2;
    PrnExcept::SmartAddRef<PrnComps::TImgWriterFileItem>(v2);
    PrnExcept::SmartRelease<PrnComps::TImgReaderFileItem>(&liDistanceToMove);
    (*(void (__fastcall **)(PrnComps::TImgFileItemBase *))(*(_QWORD *)v2 + 8LL))(v2);
    v6 = v2;
    v7 = v2;
  }
  else
  {
    v6 = 0;
    v7 = 0;
  }
  if ( (*((_DWORD *)v4 + 11))-- == 1 )
    *((_DWORD *)v4 + 10) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v4);
  if ( v6 )
  {
    liDistanceToMove.QuadPart = 0;
    v22 = (void *)*((_QWORD *)v7 + 4);
    if ( v22 == (void *)-1LL )
      v22 = 0;
    if ( !SetFilePointerEx(v22, liDistanceToMove, 0, 0) )
    {
      LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v23);
      SplException::RealThrowFromHR((SplException *)LastErrorAsFailHRNoBreak, v33, v34, v35);
    }
  }
  else
  {
    liDistanceToMove.QuadPart = -1;
    NCoreLibrary::TAutoHandleNT::TAutoHandleNT((NCoreLibrary::TAutoHandleNT *)&TokenHandle, v9);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
    {
      CurrentThread = GetCurrentThread();
      v12 = SecurityHelper::OpenThreadToken(CurrentThread, 0xCu, &TokenHandle, v11);
      if ( v12 && v12 != 1008 )
      {
        SplException::THResultException::THResultException((SplException::THResultException *)v55, "-", 0);
        v29 = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v28);
        SplException::TSystemException::InternalInit(
          (SplException::TSystemException *)v55,
          v29,
          v30,
          v31,
          dwCreationDisposition,
          dwFlagsAndAttributes,
          hTemplateFile);
        SplException::TSystemException::Message(
          (SplException::TSystemException *)v55,
          "GetReaderFileItemX OpenThreadToken failed with unexpected error");
        SplException::THResultException::THResultException(
          (SplException::THResultException *)pExceptionObject,
          (const struct SplException::THResultException *)v55);
        throw (SplException::THResultException *)pExceptionObject;
      }
    }
    else
    {
      v13 = GetCurrentThread();
      if ( !OpenThreadToken(v13, 0xCu, 0, &TokenHandle) && GetLastError() != 1008 )
      {
        SplException::THResultException::THResultException((SplException::THResultException *)v55, "-", 0);
        v37 = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v36);
        SplException::TSystemException::InternalInit(
          (SplException::TSystemException *)v55,
          v37,
          v38,
          v39,
          dwCreationDisposition,
          dwFlagsAndAttributes,
          hTemplateFile);
        SplException::TSystemException::Message(
          (SplException::TSystemException *)v55,
          "GetReaderFileItemX OpenThreadToken failed with unexpected error");
        SplException::THResultException::THResultException(
          (SplException::THResultException *)pExceptionObject,
          (const struct SplException::THResultException *)v55);
        throw (SplException::THResultException *)pExceptionObject;
      }
    }
    if ( TokenHandle != (void *)-1LL && TokenHandle && !SetThreadToken(0, 0) )
    {
      v40 = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v14);
      SplException::RealThrowFromHR((SplException *)v40, v41, v42, v43);
    }
    FileW = CreateFileW(
              *((LPCWSTR *)this + 13),
              0x80000000,
              *((_BYTE *)this + 124) != 0 ? 3 : 7,
              0,
              3u,
              *((_DWORD *)this + 28),
              0);
    NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Attach(
      &liDistanceToMove,
      FileW);
    v18 = (const char *)TokenHandle;
    if ( TokenHandle != (void *)-1LL && TokenHandle && !SetThreadToken(0, TokenHandle) )
    {
      v44 = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v16);
      SplException::RealThrowFromHR((SplException *)v44, v45, v46, v47);
    }
    if ( liDistanceToMove.QuadPart == -1 )
    {
      v24 = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v16);
      SplException::RealThrowFromHR((SplException *)v24, v25, v26, v27);
    }
    v19 = (PrnComps::TImgFileItemBase *)operator new(0x70u, v18, v17);
    v6 = v19;
    v54 = v19;
    if ( v19 )
    {
      v20 = *((_BYTE *)this + 124);
      PrnComps::TImgFileItemBase::TImgFileItemBase(v19);
      *(_QWORD *)v6 = &PrnComps::TImgReaderFileItem::`vftable'{for `PrnComps::TImgFileItemBase'};
      *((_QWORD *)v6 + 6) = &PrnComps::TImgReaderFileItem::`vftable'{for `IImgFileItem'};
      *((_QWORD *)v6 + 7) = v3;
      *((_DWORD *)v6 + 18) = 1802398836;
      *((_QWORD *)v6 + 10) = (char *)v6 + 64;
      *((_QWORD *)v6 + 11) = (char *)v6 + 64;
      *((_QWORD *)v6 + 8) = &PrnComps::TImgReaderFileItem::TEmbeddedLink::`vftable';
      *((_QWORD *)v6 + 12) = v6;
      *((_DWORD *)v6 + 26) = 1;
      *((_BYTE *)v6 + 108) = v20;
      PrnComps::TImgFileItemBase::SetFileHandle(v6, (void **)&liDistanceToMove);
    }
    else
    {
      v6 = 0;
    }
    v54 = v2;
    v53 = v6;
    PrnExcept::SmartRelease<PrnComps::TImgReaderFileItem>(&v54);
    NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&TokenHandle);
    NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&liDistanceToMove);
  }
  (*(void (__fastcall **)(PrnComps::TImgWriterFileItem *))(*(_QWORD *)this + 8LL))(this);
  v53 = 0;
  PrnExcept::SmartRelease<PrnComps::TImgReaderFileItem>(&v53);
  return (struct IImgFileItem *)(((unsigned __int64)v6 + 48) & -(__int64)(v6 != 0));
}

```

## disassembly

```asm
0x1400194a0  mov     [rsp-8+arg_8], rbx
0x1400194a5  mov     [rsp-8+arg_10], rsi
0x1400194aa  push    rbp
0x1400194ab  push    rdi
0x1400194ac  push    r13
0x1400194ae  push    r14
0x1400194b0  push    r15
0x1400194b2  lea     rbp, [rsp-0B0h]
0x1400194ba  sub     rsp, 1B0h
0x1400194c1  mov     rax, cs:__security_cookie
0x1400194c8  xor     rax, rsp
0x1400194cb  mov     [rbp+0D0h+var_30], rax
0x1400194d2  mov     r14, rcx
0x1400194d5  xor     ebx, ebx
0x1400194d7  mov     [rsp+1D0h+var_180], rbx
0x1400194dc  lea     r13, [rcx-30h]
0x1400194e0  mov     rdi, [r13+38h]
0x1400194e4  mov     [rsp+1D0h+var_178], rdi
0x1400194e9  mov     rcx, rdi; this
0x1400194ec  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x1400194f1  nop
0x1400194f2  lea     rdx, [r14+18h]
0x1400194f6  mov     r8, [rdx+18h]
0x1400194fa  mov     rcx, [r8+10h]
0x1400194fe  mov     rax, [r8+18h]
0x140019502  mov     [rcx+18h], rax
0x140019506  mov     rcx, [r8+18h]
0x14001950a  mov     rax, [r8+10h]
0x14001950e  mov     [rcx+10h], rax
0x140019512  mov     [r8+10h], r8
0x140019516  mov     [r8+18h], r8
0x14001951a  xor     eax, eax
0x14001951c  cmp     r8, rdx
0x14001951f  cmovz   r8, rax
0x140019523  test    r8, r8
0x140019526  jz      short loc_14001955F
0x140019528  mov     rbx, [r8+20h]
0x14001952c  mov     qword ptr [rsp+1D0h+liDistanceToMove], rax
0x140019531  mov     [rsp+1D0h+var_180], rbx
0x140019536  mov     rcx, rbx
0x140019539  call    ??$SmartAddRef@VTImgWriterFileItem@PrnComps@@@PrnExcept@@YAXPEAVTImgWriterFileItem@PrnComps@@@Z; PrnExcept::SmartAddRef<PrnComps::TImgWriterFileItem>(PrnComps::TImgWriterFileItem *)
0x14001953e  lea     rcx, [rsp+1D0h+liDistanceToMove]
0x140019543  call    ??$SmartRelease@VTImgReaderFileItem@PrnComps@@@PrnExcept@@YAXPEAPEAVTImgReaderFileItem@PrnComps@@@Z; PrnExcept::SmartRelease<PrnComps::TImgReaderFileItem>(PrnComps::TImgReaderFileItem * *)
0x140019548  mov     rax, [rbx]
0x14001954b  mov     rcx, rbx
0x14001954e  mov     rax, [rax+8]
0x140019552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019557  mov     rsi, rbx
0x14001955a  mov     r15, rbx
0x14001955d  jmp     short loc_140019564
0x14001955f  xor     esi, esi
0x140019561  xor     r15d, r15d
0x140019564  add     dword ptr [rdi+2Ch], 0FFFFFFFFh
0x140019568  mov     eax, [rdi+2Ch]
0x14001956b  jnz     short loc_140019574
0x14001956d  mov     dword ptr [rdi+28h], 0
0x140019574  mov     rcx, rdi; lpCriticalSection
0x140019577  call    cs:__imp_LeaveCriticalSection
0x14001957d  test    rsi, rsi
0x140019580  jnz     loc_140019798
0x140019586  mov     qword ptr [rsp+1D0h+liDistanceToMove], 0FFFFFFFFFFFFFFFFh
0x14001958f  lea     rcx, [rsp+1D0h+TokenHandle]; this
0x140019594  call    ??0TAutoHandleNT@NCoreLibrary@@QEAA@PEAX@Z; NCoreLibrary::TAutoHandleNT::TAutoHandleNT(void *)
0x140019599  nop
0x14001959a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x1400195a1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x1400195a6  test    al, al
0x1400195a8  jz      short loc_1400195D1
0x1400195aa  call    cs:__imp_GetCurrentThread
0x1400195b0  lea     r8, [rsp+1D0h+TokenHandle]; TokenHandle
0x1400195b5  lea     edx, [rsi+0Ch]; DesiredAccess
0x1400195b8  mov     rcx, rax; ThreadHandle
0x1400195bb  call    ?OpenThreadToken@SecurityHelper@@YAKPEAXKPEAPEAX@Z; SecurityHelper::OpenThreadToken(void *,ulong,void * *)
0x1400195c0  test    eax, eax
0x1400195c2  jz      short loc_140019601
0x1400195c4  cmp     eax, 3F0h
0x1400195c9  jnz     loc_1400197D6
0x1400195cf  jmp     short loc_140019601
0x1400195d1  call    cs:__imp_GetCurrentThread
0x1400195d7  lea     r9, [rsp+1D0h+TokenHandle]; TokenHandle
0x1400195dc  xor     r8d, r8d; OpenAsSelf
0x1400195df  lea     edx, [r8+0Ch]; DesiredAccess
0x1400195e3  mov     rcx, rax; ThreadHandle
0x1400195e6  call    cs:__imp_OpenThreadToken
0x1400195ec  test    eax, eax
0x1400195ee  jnz     short loc_140019601
0x1400195f0  call    cs:__imp_GetLastError
0x1400195f6  cmp     eax, 3F0h
0x1400195fb  jnz     loc_140019839
0x140019601  mov     rax, [rsp+1D0h+TokenHandle]
0x140019606  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001960a  jz      short loc_140019623
0x14001960c  test    rax, rax
0x14001960f  jz      short loc_140019623
0x140019611  xor     edx, edx; Token
0x140019613  xor     ecx, ecx; Thread
0x140019615  call    cs:__imp_SetThreadToken
0x14001961b  test    eax, eax
0x14001961d  jz      loc_14001988F
0x140019623  mov     al, [r14+7Ch]
0x140019627  neg     al
0x140019629  sbb     r8d, r8d
0x14001962c  and     r8d, 0FFFFFFFCh
0x140019630  add     r8d, 7; dwShareMode
0x140019634  mov     [rsp+1D0h+hTemplateFile], 0; hTemplateFile
0x14001963d  mov     eax, [r14+70h]
0x140019641  mov     dword ptr [rsp+1D0h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x140019645  mov     [rsp+1D0h+dwCreationDisposition], 3; dwCreationDisposition
0x14001964d  xor     r9d, r9d; lpSecurityAttributes
0x140019650  mov     edx, 80000000h; dwDesiredAccess
0x140019655  mov     rcx, [r14+68h]; lpFileName
0x140019659  call    cs:__imp_CreateFileW
0x14001965f  mov     rdx, rax
0x140019662  lea     rcx, [rsp+1D0h+liDistanceToMove]
0x140019667  call    ?Attach@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXPEAX@Z; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Attach(void *)
0x14001966c  mov     rdx, [rsp+1D0h+TokenHandle]; Token
0x140019671  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x140019675  jz      short loc_14001968C
0x140019677  test    rdx, rdx
0x14001967a  jz      short loc_14001968C
0x14001967c  xor     ecx, ecx; Thread
0x14001967e  call    cs:__imp_SetThreadToken
0x140019684  test    eax, eax
0x140019686  jz      loc_14001989C
0x14001968c  cmp     qword ptr [rsp+1D0h+liDistanceToMove], 0FFFFFFFFFFFFFFFFh
0x140019692  jz      loc_1400197C9
0x140019698  mov     ecx, 70h ; 'p'; unsigned __int64
0x14001969d  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1400196a2  mov     rsi, rax
0x1400196a5  mov     [rsp+1D0h+var_178], rax
0x1400196aa  test    rax, rax
0x1400196ad  jz      short loc_14001970F
0x1400196af  mov     dil, [r14+7Ch]
0x1400196b3  mov     rcx, rax; this
0x1400196b6  call    ??0TImgFileItemBase@PrnComps@@QEAA@XZ; PrnComps::TImgFileItemBase::TImgFileItemBase(void)
0x1400196bb  lea     rax, ??_7TImgReaderFileItem@PrnComps@@6BTImgFileItemBase@1@@; const PrnComps::TImgReaderFileItem::`vftable'{for `PrnComps::TImgFileItemBase'}
0x1400196c2  mov     [rsi], rax
0x1400196c5  lea     rax, ??_7TImgReaderFileItem@PrnComps@@6BIImgFileItem@@@; const PrnComps::TImgReaderFileItem::`vftable'{for `IImgFileItem'}
0x1400196cc  mov     [rsi+30h], rax
0x1400196d0  mov     [rsi+38h], r13
0x1400196d4  lea     rcx, [rsi+40h]
0x1400196d8  mov     dword ptr [rcx+8], 6B6E6C74h
0x1400196df  mov     [rcx+10h], rcx
0x1400196e3  mov     [rcx+18h], rcx
0x1400196e7  lea     rax, ??_7TEmbeddedLink@TImgReaderFileItem@PrnComps@@6B@; const PrnComps::TImgReaderFileItem::TEmbeddedLink::`vftable'
0x1400196ee  mov     [rcx], rax
0x1400196f1  mov     [rcx+20h], rsi
0x1400196f5  mov     dword ptr [rsi+68h], 1
0x1400196fc  mov     [rsi+6Ch], dil
0x140019700  lea     rdx, [rsp+1D0h+liDistanceToMove]; void **
0x140019705  mov     rcx, rsi; this
0x140019708  call    ?SetFileHandle@TImgFileItemBase@PrnComps@@QEAAXPEAPEAX@Z; PrnComps::TImgFileItemBase::SetFileHandle(void * *)
0x14001970d  jmp     short loc_140019711
0x14001970f  xor     esi, esi
0x140019711  mov     [rsp+1D0h+var_178], rbx
0x140019716  mov     [rsp+1D0h+var_180], rsi
0x14001971b  lea     rcx, [rsp+1D0h+var_178]
0x140019720  call    ??$SmartRelease@VTImgReaderFileItem@PrnComps@@@PrnExcept@@YAXPEAPEAVTImgReaderFileItem@PrnComps@@@Z; PrnExcept::SmartRelease<PrnComps::TImgReaderFileItem>(PrnComps::TImgReaderFileItem * *)
0x140019725  nop
0x140019726  lea     rcx, [rsp+1D0h+TokenHandle]
0x14001972b  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x140019730  nop
0x140019731  lea     rcx, [rsp+1D0h+liDistanceToMove]
0x140019736  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x14001973b  mov     rax, [r14]
0x14001973e  mov     rcx, r14
0x140019741  mov     rax, [rax+8]
0x140019745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001974a  mov     [rsp+1D0h+var_180], 0
0x140019753  lea     rcx, [rsi+30h]
0x140019757  neg     rsi
0x14001975a  sbb     rbx, rbx
0x14001975d  and     rbx, rcx
0x140019760  lea     rcx, [rsp+1D0h+var_180]
0x140019765  call    ??$SmartRelease@VTImgReaderFileItem@PrnComps@@@PrnExcept@@YAXPEAPEAVTImgReaderFileItem@PrnComps@@@Z; PrnExcept::SmartRelease<PrnComps::TImgReaderFileItem>(PrnComps::TImgReaderFileItem * *)
0x14001976a  mov     rax, rbx
0x14001976d  mov     rcx, [rbp+0D0h+var_30]
0x140019774  xor     rcx, rsp; StackCookie
0x140019777  call    __security_check_cookie
0x14001977c  lea     r11, [rsp+1D0h+var_20]
0x140019784  mov     rbx, [r11+38h]
0x140019788  mov     rsi, [r11+40h]
0x14001978c  mov     rsp, r11
0x14001978f  pop     r15
0x140019791  pop     r14
0x140019793  pop     r13
0x140019795  pop     rdi
0x140019796  pop     rbp
0x140019797  retn
0x140019798  mov     qword ptr [rsp+1D0h+liDistanceToMove], 0
0x1400197a1  mov     rcx, [r15+20h]
0x1400197a5  xor     eax, eax
0x1400197a7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400197ab  cmovz   rcx, rax; hFile
0x1400197af  xor     r9d, r9d; dwMoveMethod
0x1400197b2  xor     r8d, r8d; lpNewFilePointer
0x1400197b5  mov     rdx, qword ptr [rsp+1D0h+liDistanceToMove]; liDistanceToMove
0x1400197ba  call    cs:__imp_SetFilePointerEx
0x1400197c0  test    eax, eax
0x1400197c2  jz      short loc_14001982C
0x1400197c4  jmp     loc_14001973B
0x1400197c9  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1400197ce  mov     ecx, eax; this
0x1400197d0  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1400197d6  xor     r8d, r8d; unsigned int
0x1400197d9  lea     rdx, asc_1400696D8; "-"
0x1400197e0  lea     rcx, [rsp+1D0h+var_170]; this
0x1400197e5  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x1400197ea  nop
0x1400197eb  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1400197f0  mov     edx, eax; unsigned int
0x1400197f2  lea     rcx, [rsp+1D0h+var_170]; this
0x1400197f7  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x1400197fc  lea     rdx, aGetreaderfilei; "GetReaderFileItemX OpenThreadToken fail"...
0x140019803  lea     rcx, [rsp+1D0h+var_170]; this
0x140019808  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x14001980d  lea     rdx, [rsp+1D0h+var_170]; struct SplException::THResultException *
0x140019812  lea     rcx, [rbp+0D0h+pExceptionObject]; this
0x140019816  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14001981b  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140019822  lea     rcx, [rbp+0D0h+pExceptionObject]; pExceptionObject
0x140019826  call    _CxxThrowException_0
0x14001982c  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140019831  mov     ecx, eax; this
0x140019833  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140019839  xor     r8d, r8d; unsigned int
0x14001983c  lea     rdx, asc_1400696D8; "-"
0x140019843  lea     rcx, [rsp+1D0h+var_170]; this
0x140019848  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14001984d  nop
0x14001984e  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140019853  mov     edx, eax; unsigned int
0x140019855  lea     rcx, [rsp+1D0h+var_170]; this
0x14001985a  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x14001985f  lea     rdx, aGetreaderfilei; "GetReaderFileItemX OpenThreadToken fail"...
0x140019866  lea     rcx, [rsp+1D0h+var_170]; this
0x14001986b  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140019870  lea     rdx, [rsp+1D0h+var_170]; struct SplException::THResultException *
0x140019875  lea     rcx, [rbp+0D0h+pExceptionObject]; this
0x140019879  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14001987e  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140019885  lea     rcx, [rbp+0D0h+pExceptionObject]; pExceptionObject
0x140019889  call    _CxxThrowException_0
0x14001988f  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140019894  mov     ecx, eax; this
0x140019896  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14001989c  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1400198a1  mov     ecx, eax; this
0x1400198a3  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
```
