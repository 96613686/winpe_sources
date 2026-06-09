# GuestStateFile::CancelMirrorFileTo(void)

- ea: `0x1800535e0`
- end: `0x1800537f8`
- name: `?CancelMirrorFileTo@GuestStateFile@@UEAAXXZ`
- size: `536`
- prototype: `void __fastcall(GuestStateFile *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x180009e8c`
- `0x18001017c`
- `0x18001587c`
- `0x1800526dc`
- `0x180052930`
- `0x180052fb8`
- `0x1800535e0`
- `0x180053e24`
- `0x180054180`
- `0x1800548e8`
- `0x180056464`
- `0x18005782c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005375e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005375e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800536ac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800536ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053724`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053724`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800536b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800536b2`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18005371a`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18005371a`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1800536ef`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1800536ef`

## string_xrefs

- `0x1800537b9`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x1800537cb`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x1800537e6`: `onecore\vm\common\gueststate\gueststatefile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall GuestStateFile::CancelMirrorFileTo(GuestStateFile *this)
{
  const unsigned __int16 *v2; // rsi
  __int64 FilePath; // rax
  const unsigned __int16 *v4; // rdi
  const char *v5; // r9
  signed int LastError; // eax
  const struct _GUID *v7; // [rsp+20h] [rbp-E0h]
  int v8; // [rsp+20h] [rbp-E0h]
  struct _GUID v9; // [rsp+30h] [rbp-D0h] BYREF
  char *v10; // [rsp+40h] [rbp-C0h] BYREF
  char v11; // [rsp+48h] [rbp-B8h]
  DWORD NumberOfBytesTransferred[4]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v13[42]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  memset_0(v13, 0, sizeof(v13));
  v2 = (const unsigned __int16 *)((char *)this + 184);
  if ( *((_QWORD *)this + 26) > 7u )
    v2 = *(const unsigned __int16 **)v2;
  FilePath = GuestStateFile::GetFilePath(this, &v10);
  v4 = (const unsigned __int16 *)FilePath;
  if ( *(_QWORD *)(FilePath + 24) > 7u )
    v4 = *(const unsigned __int16 **)FilePath;
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v13,
    "GuestStateFileCancelMirrorFileTo");
  v13[0] = &GuestStateFileTraceProvider::GuestStateFileCancelMirrorFileTo::`vftable';
  v9 = (struct _GUID)*((_OWORD *)this + 6);
  GuestStateFileTraceProvider::GuestStateFileCancelMirrorFileTo::StartActivity(
    (GuestStateFileTraceProvider::GuestStateFileCancelMirrorFileTo *)v13,
    &v9,
    v4,
    v2,
    v7);
  std::wstring::~wstring(&v10);
  if ( !*((_QWORD *)this + 18) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4A9,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
      (const char *)0x8007139FLL,
      v8);
  AcquireSRWLockExclusive((PSRWLOCK)this + 15);
  *((_DWORD *)this + 32) = GetCurrentThreadId();
  v10 = (char *)this + 120;
  v11 = 1;
  *(_QWORD *)v9.Data4 = 1;
  *(_QWORD *)&v9.Data1 = this;
  if ( !CancelIoEx(*((HANDLE *)this + 17), (LPOVERLAPPED)((char *)this + 152)) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x4B8,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
      v5);
  NumberOfBytesTransferred[0] = 0;
  if ( !GetOverlappedResult(*((HANDLE *)this + 17), (LPOVERLAPPED)((char *)this + 152), NumberOfBytesTransferred, 1) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError != -2147023901 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4C3,
        (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
        (const char *)(unsigned int)LastError,
        v8);
  }
  v9.Data4[0] = 0;
  lambda_79f78ae051578d5ff36608fbe1536026_::operator()(&v9);
  *((_DWORD *)this + 32) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)this + 15);
  GuestStateFile::LogDebugTrace(this, L"Cancelled mirror file.");
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v13);
  v13[0] = &GuestStateFileTraceProvider::GuestStateFileCancelMirrorFileTo::`vftable';
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v13);
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(v13);
}

```

## disassembly

```asm
0x1800535e0  push    rbp
0x1800535e2  push    rbx
0x1800535e3  push    rsi
0x1800535e4  push    rdi
0x1800535e5  push    r12
0x1800535e7  push    r14
0x1800535e9  lea     rbp, [rsp-0D8h]
0x1800535f1  sub     rsp, 1D8h
0x1800535f8  mov     rax, cs:__security_cookie
0x1800535ff  xor     rax, rsp
0x180053602  mov     [rbp+100h+var_40], rax
0x180053609  mov     rbx, rcx
0x18005360c  xor     edx, edx; Val
0x18005360e  mov     r8d, 150h; Size
0x180053614  lea     rcx, [rsp+200h+var_190]; void *
0x180053619  call    memset_0
0x18005361e  lea     rsi, [rbx+0B8h]
0x180053625  cmp     qword ptr [rsi+18h], 7
0x18005362a  jbe     short loc_18005362F
0x18005362c  mov     rsi, [rsi]
0x18005362f  lea     rdx, [rsp+200h+var_1C0]
0x180053634  mov     rcx, rbx
0x180053637  call    ?GetFilePath@GuestStateFile@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GuestStateFile::GetFilePath(void)
0x18005363c  mov     rdi, rax
0x18005363f  cmp     qword ptr [rax+18h], 7
0x180053644  jbe     short loc_180053649
0x180053646  mov     rdi, [rax]
0x180053649  lea     rdx, aGueststatefile_13; "GuestStateFileCancelMirrorFileTo"
0x180053650  lea     rcx, [rsp+200h+var_190]
0x180053655  call    ??0?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18005365a  lea     r12, ??_7GuestStateFileCancelMirrorFileTo@GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::GuestStateFileCancelMirrorFileTo::`vftable'
0x180053661  mov     [rsp+200h+var_190], r12
0x180053666  movups  xmm0, xmmword ptr [rbx+60h]
0x18005366a  movdqu  xmmword ptr [rsp+200h+var_1D0.Data1], xmm0
0x180053670  mov     r9, rsi; unsigned __int16 *
0x180053673  mov     r8, rdi; unsigned __int16 *
0x180053676  lea     rdx, [rsp+200h+var_1D0]; struct _GUID
0x18005367b  lea     rcx, [rsp+200h+var_190]; this
0x180053680  call    ?StartActivity@GuestStateFileCancelMirrorFileTo@GuestStateFileTraceProvider@@QEAAXU_GUID@@PEBG1PEBU3@@Z; GuestStateFileTraceProvider::GuestStateFileCancelMirrorFileTo::StartActivity(_GUID,ushort const *,ushort const *,_GUID const *)
0x180053685  nop
0x180053686  lea     rcx, [rsp+200h+var_1C0]
0x18005368b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180053690  mov     rcx, [rbp+108h]; this
0x180053697  cmp     qword ptr [rbx+90h], 0
0x18005369f  jz      loc_1800537E0
0x1800536a5  lea     rdi, [rbx+78h]
0x1800536a9  mov     rcx, rdi; SRWLock
0x1800536ac  call    cs:__imp_AcquireSRWLockExclusive
0x1800536b2  call    cs:__imp_GetCurrentThreadId
0x1800536b8  mov     [rdi+8], eax
0x1800536bb  mov     [rsp+200h+var_1C0], rdi
0x1800536c0  mov     [rsp+200h+var_1B8], 1
0x1800536c5  xorps   xmm0, xmm0
0x1800536c8  movups  xmmword ptr [rsp+200h+var_1D0.Data1], xmm0
0x1800536cd  mov     qword ptr [rsp+200h+var_1D0.Data1], rbx
0x1800536d2  mov     [rsp+200h+var_1D0.Data4], 1
0x1800536d7  lea     r14, [rbx+98h]
0x1800536de  mov     rsi, [rbp+108h]
0x1800536e5  mov     rdx, r14; lpOverlapped
0x1800536e8  mov     rcx, [rbx+88h]; hFile
0x1800536ef  call    cs:__imp_CancelIoEx
0x1800536f5  test    eax, eax
0x1800536f7  jz      loc_1800537CB
0x1800536fd  mov     [rsp+200h+NumberOfBytesTransferred], 0
0x180053705  mov     r9d, 1; bWait
0x18005370b  lea     r8, [rsp+200h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180053710  mov     rdx, r14; lpOverlapped
0x180053713  mov     rcx, [rbx+88h]; hFile
0x18005371a  call    cs:__imp_GetOverlappedResult
0x180053720  test    eax, eax
0x180053722  jnz     short loc_180053744
0x180053724  call    cs:__imp_GetLastError
0x18005372a  test    eax, eax
0x18005372c  jle     short loc_180053736
0x18005372e  movzx   eax, ax
0x180053731  or      eax, 80070000h
0x180053736  mov     rcx, [rbp+108h]; this
0x18005373d  cmp     eax, 800703E3h
0x180053742  jnz     short loc_1800537B6
0x180053744  mov     [rsp+200h+var_1D0.Data4], 0
0x180053749  lea     rcx, [rsp+200h+var_1D0]
0x18005374e  call    _lambda_79f78ae051578d5ff36608fbe1536026___operator__
0x180053753  nop
0x180053754  mov     dword ptr [rdi+8], 0
0x18005375b  mov     rcx, rdi; SRWLock
0x18005375e  call    cs:__imp_ReleaseSRWLockExclusive
0x180053764  lea     rdx, aCancelledMirro; "Cancelled mirror file."
0x18005376b  mov     rcx, rbx; this
0x18005376e  call    ?LogDebugTrace@GuestStateFile@@IEBAXPEBG@Z; GuestStateFile::LogDebugTrace(ushort const *)
0x180053773  lea     rcx, [rsp+200h+var_190]
0x180053778  call    ?Stop@?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18005377d  nop
0x18005377e  mov     [rsp+200h+var_190], r12
0x180053783  lea     rcx, [rsp+200h+var_190]
0x180053788  call    ?Destroy@?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18005378d  lea     rcx, [rsp+200h+var_190]
0x180053792  call    ??1?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180053797  mov     rcx, [rbp+100h+var_40]
0x18005379e  xor     rcx, rsp; StackCookie
0x1800537a1  call    __security_check_cookie
0x1800537a6  add     rsp, 1D8h
0x1800537ad  pop     r14
0x1800537af  pop     r12
0x1800537b1  pop     rdi
0x1800537b2  pop     rsi
0x1800537b3  pop     rbx
0x1800537b4  pop     rbp
0x1800537b5  retn
0x1800537b6  mov     r9d, eax; char *
0x1800537b9  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\gueststate\\guests"...
0x1800537c0  mov     edx, 4C3h; void *
0x1800537c5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800537cb  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\gueststate\\guests"...
0x1800537d2  mov     edx, 4B8h; void *
0x1800537d7  mov     rcx, rsi; this
0x1800537da  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800537e0  mov     r9d, 8007139Fh; char *
0x1800537e6  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\gueststate\\guests"...
0x1800537ed  mov     edx, 4A9h; void *
0x1800537f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
