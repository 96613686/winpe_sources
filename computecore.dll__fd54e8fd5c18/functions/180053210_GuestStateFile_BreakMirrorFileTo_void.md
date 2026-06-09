# GuestStateFile::BreakMirrorFileTo(void)

- ea: `0x180053210`
- end: `0x18005345e`
- name: `?BreakMirrorFileTo@GuestStateFile@@UEAAXXZ`
- size: `590`
- prototype: `void __fastcall(GuestStateFile *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180053980`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x180009968`
- `0x180009e8c`
- `0x18001587c`
- `0x180027380`
- `0x1800526dc`
- `0x180052930`
- `0x180052bb4`
- `0x180053210`
- `0x180053e24`
- `0x180054180`
- `0x1800548e8`
- `0x18005633c`
- `0x18005782c`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800533c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800533c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800532df`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800532df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005334c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005334c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800532e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800532e5`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180053342`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180053342`
- `VirtDisk!BreakMirrorVirtualDisk` at `0x180053311`
- `VirtDisk!BreakMirrorVirtualDisk` at `0x180053311`

## string_xrefs

- `0x18005341f`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x180053434`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x18005344c`: `onecore\vm\common\gueststate\gueststatefile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall GuestStateFile::BreakMirrorFileTo(GuestStateFile *this)
{
  const unsigned __int16 *v2; // r14
  __int64 FilePath; // rax
  const unsigned __int16 *v4; // rdi
  unsigned int v5; // eax
  signed int LastError; // eax
  const struct _GUID *v7; // [rsp+20h] [rbp-E0h]
  unsigned int v8; // [rsp+20h] [rbp-E0h]
  struct _GUID v9; // [rsp+30h] [rbp-D0h] BYREF
  char *v10; // [rsp+40h] [rbp-C0h]
  char v11; // [rsp+48h] [rbp-B8h]
  DWORD NumberOfBytesTransferred; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v13[40]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v14[42]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  memset_0(v14, 0, sizeof(v14));
  if ( *((_QWORD *)this + 26) <= 7u )
    v2 = (const unsigned __int16 *)((char *)this + 184);
  else
    v2 = (const unsigned __int16 *)*((_QWORD *)this + 23);
  FilePath = GuestStateFile::GetFilePath(this, v13);
  v4 = (const unsigned __int16 *)FilePath;
  if ( *(_QWORD *)(FilePath + 24) > 7u )
    v4 = *(const unsigned __int16 **)FilePath;
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v14,
    "GuestStateFileBreakMirrorFileTo");
  v14[0] = &GuestStateFileTraceProvider::GuestStateFileBreakMirrorFileTo::`vftable';
  v9 = (struct _GUID)*((_OWORD *)this + 6);
  GuestStateFileTraceProvider::GuestStateFileBreakMirrorFileTo::StartActivity(
    (GuestStateFileTraceProvider::GuestStateFileBreakMirrorFileTo *)v14,
    &v9,
    v4,
    v2,
    v7);
  std::wstring::~wstring(v13);
  if ( !*((_QWORD *)this + 18) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x475,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
      (const char *)0x8007139FLL,
      v8);
  AcquireSRWLockExclusive((PSRWLOCK)this + 15);
  *((_DWORD *)this + 32) = GetCurrentThreadId();
  v10 = (char *)this + 120;
  v11 = 1;
  *(_QWORD *)v9.Data4 = 1;
  *(_QWORD *)&v9.Data1 = this;
  v5 = BreakMirrorVirtualDisk(*((_QWORD *)this + 17));
  if ( v5 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x483,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
      (const char *)v5,
      v8);
  NumberOfBytesTransferred = 0;
  if ( !GetOverlappedResult(*((HANDLE *)this + 17), (LPOVERLAPPED)((char *)this + 152), &NumberOfBytesTransferred, 1) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x48D,
        (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
        (const char *)(unsigned int)LastError,
        v8);
  }
  if ( *((_QWORD *)this + 25) )
  {
    std::wstring::wstring(v13, (char *)this + 184);
    (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 7) + 80LL))(*((_QWORD *)this + 7), (char *)this + 184);
    (*(void (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 7) + 96LL))(*((_QWORD *)this + 7), v13);
    std::wstring::~wstring(v13);
  }
  wil::details::lambda_call__lambda_e09bf96b7d5152de7ed2fa5fb53149e6___::_lambda_call__lambda_e09bf96b7d5152de7ed2fa5fb53149e6___(&v9);
  *((_DWORD *)this + 32) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)this + 15);
  GuestStateFile::LogDebugTrace(this, L"Broke mirror file.");
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v14);
  v14[0] = &GuestStateFileTraceProvider::GuestStateFileBreakMirrorFileTo::`vftable';
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v14);
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(v14);
}

```

## disassembly

```asm
0x180053210  push    rbp
0x180053212  push    rbx
0x180053213  push    rsi
0x180053214  push    rdi
0x180053215  push    r14
0x180053217  push    r15
0x180053219  lea     rbp, [rsp-0E8h]
0x180053221  sub     rsp, 1E8h
0x180053228  mov     rax, cs:__security_cookie
0x18005322f  xor     rax, rsp
0x180053232  mov     [rbp+110h+var_40], rax
0x180053239  mov     rbx, rcx
0x18005323c  xor     edx, edx; Val
0x18005323e  mov     r8d, 150h; Size
0x180053244  lea     rcx, [rbp+110h+var_190]; void *
0x180053248  call    memset_0
0x18005324d  lea     rsi, [rbx+0B8h]
0x180053254  cmp     qword ptr [rsi+18h], 7
0x180053259  jbe     short loc_180053260
0x18005325b  mov     r14, [rsi]
0x18005325e  jmp     short loc_180053263
0x180053260  mov     r14, rsi
0x180053263  lea     rdx, [rsp+210h+var_1B8]
0x180053268  mov     rcx, rbx
0x18005326b  call    ?GetFilePath@GuestStateFile@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GuestStateFile::GetFilePath(void)
0x180053270  mov     rdi, rax
0x180053273  cmp     qword ptr [rax+18h], 7
0x180053278  jbe     short loc_18005327D
0x18005327a  mov     rdi, [rax]
0x18005327d  lea     rdx, aGueststatefile_4; "GuestStateFileBreakMirrorFileTo"
0x180053284  lea     rcx, [rbp+110h+var_190]
0x180053288  call    ??0?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18005328d  lea     r15, ??_7GuestStateFileBreakMirrorFileTo@GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::GuestStateFileBreakMirrorFileTo::`vftable'
0x180053294  mov     [rbp+110h+var_190], r15
0x180053298  movups  xmm0, xmmword ptr [rbx+60h]
0x18005329c  movdqu  xmmword ptr [rsp+210h+var_1E0.Data1], xmm0
0x1800532a2  mov     r9, r14; unsigned __int16 *
0x1800532a5  mov     r8, rdi; unsigned __int16 *
0x1800532a8  lea     rdx, [rsp+210h+var_1E0]; struct _GUID
0x1800532ad  lea     rcx, [rbp+110h+var_190]; this
0x1800532b1  call    ?StartActivity@GuestStateFileBreakMirrorFileTo@GuestStateFileTraceProvider@@QEAAXU_GUID@@PEBG1PEBU3@@Z; GuestStateFileTraceProvider::GuestStateFileBreakMirrorFileTo::StartActivity(_GUID,ushort const *,ushort const *,_GUID const *)
0x1800532b6  nop
0x1800532b7  lea     rcx, [rsp+210h+var_1B8]
0x1800532bc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800532c1  mov     rcx, [rbp+118h]; this
0x1800532c8  xor     r14d, r14d
0x1800532cb  cmp     [rbx+90h], r14
0x1800532d2  jz      loc_180053446
0x1800532d8  lea     rdi, [rbx+78h]
0x1800532dc  mov     rcx, rdi; SRWLock
0x1800532df  call    cs:__imp_AcquireSRWLockExclusive
0x1800532e5  call    cs:__imp_GetCurrentThreadId
0x1800532eb  mov     [rdi+8], eax
0x1800532ee  mov     [rsp+210h+var_1D0], rdi
0x1800532f3  mov     [rsp+210h+var_1C8], 1
0x1800532f8  xorps   xmm0, xmm0
0x1800532fb  movups  xmmword ptr [rsp+210h+var_1E0.Data1], xmm0
0x180053300  mov     qword ptr [rsp+210h+var_1E0.Data1], rbx
0x180053305  mov     [rsp+210h+var_1E0.Data4], 1
0x18005330a  mov     rcx, [rbx+88h]
0x180053311  call    cs:__imp_BreakMirrorVirtualDisk
0x180053317  mov     rcx, [rbp+118h]; this
0x18005331e  test    eax, eax
0x180053320  jnz     loc_180053431
0x180053326  mov     [rsp+210h+NumberOfBytesTransferred], r14d
0x18005332b  lea     rdx, [rbx+98h]; lpOverlapped
0x180053332  lea     r9d, [r14+1]; bWait
0x180053336  lea     r8, [rsp+210h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18005333b  mov     rcx, [rbx+88h]; hFile
0x180053342  call    cs:__imp_GetOverlappedResult
0x180053348  test    eax, eax
0x18005334a  jnz     short loc_18005336D
0x18005334c  call    cs:__imp_GetLastError
0x180053352  test    eax, eax
0x180053354  jle     short loc_18005335E
0x180053356  movzx   eax, ax
0x180053359  or      eax, 80070000h
0x18005335e  mov     rcx, [rbp+118h]; this
0x180053365  test    eax, eax
0x180053367  jnz     loc_18005341C
0x18005336d  cmp     [rbx+0C8h], r14
0x180053374  jz      short loc_1800533B6
0x180053376  mov     rdx, rsi
0x180053379  lea     rcx, [rsp+210h+var_1B8]
0x18005337e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180053383  mov     rcx, [rbx+38h]
0x180053387  mov     rax, [rcx]
0x18005338a  mov     rdx, rsi
0x18005338d  mov     rax, [rax+50h]
0x180053391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053396  mov     rcx, [rbx+38h]
0x18005339a  mov     rax, [rcx]
0x18005339d  lea     rdx, [rsp+210h+var_1B8]
0x1800533a2  mov     rax, [rax+60h]
0x1800533a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800533ab  lea     rcx, [rsp+210h+var_1B8]
0x1800533b0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800533b5  nop
0x1800533b6  lea     rcx, [rsp+210h+var_1E0]
0x1800533bb  call    wil__details__lambda_call__lambda_e09bf96b7d5152de7ed2fa5fb53149e6______lambda_call__lambda_e09bf96b7d5152de7ed2fa5fb53149e6___
0x1800533c0  nop
0x1800533c1  mov     [rdi+8], r14d
0x1800533c5  mov     rcx, rdi; SRWLock
0x1800533c8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800533ce  lea     rdx, aBrokeMirrorFil; "Broke mirror file."
0x1800533d5  mov     rcx, rbx; this
0x1800533d8  call    ?LogDebugTrace@GuestStateFile@@IEBAXPEBG@Z; GuestStateFile::LogDebugTrace(ushort const *)
0x1800533dd  lea     rcx, [rbp+110h+var_190]
0x1800533e1  call    ?Stop@?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800533e6  nop
0x1800533e7  mov     [rbp+110h+var_190], r15
0x1800533eb  lea     rcx, [rbp+110h+var_190]
0x1800533ef  call    ?Destroy@?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800533f4  lea     rcx, [rbp+110h+var_190]
0x1800533f8  call    ??1?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800533fd  mov     rcx, [rbp+110h+var_40]
0x180053404  xor     rcx, rsp; StackCookie
0x180053407  call    __security_check_cookie
0x18005340c  add     rsp, 1E8h
0x180053413  pop     r15
0x180053415  pop     r14
0x180053417  pop     rdi
0x180053418  pop     rsi
0x180053419  pop     rbx
0x18005341a  pop     rbp
0x18005341b  retn
0x18005341c  mov     r9d, eax; char *
0x18005341f  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\gueststate\\guests"...
0x180053426  mov     edx, 48Dh; void *
0x18005342b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180053431  mov     r9d, eax; char *
0x180053434  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\gueststate\\guests"...
0x18005343b  mov     edx, 483h; void *
0x180053440  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180053446  mov     r9d, 8007139Fh; char *
0x18005344c  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\gueststate\\guests"...
0x180053453  mov     edx, 475h; void *
0x180053458  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
