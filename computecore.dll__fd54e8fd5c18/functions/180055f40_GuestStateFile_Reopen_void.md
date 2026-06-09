# GuestStateFile::Reopen(void)

- ea: `0x180055f40`
- end: `0x1800560ac`
- name: `?Reopen@GuestStateFile@@UEAAXXZ`
- size: `364`
- prototype: `void __fastcall(GuestStateFile *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x180009e8c`
- `0x18001587c`
- `0x1800526dc`
- `0x180052930`
- `0x180053e24`
- `0x180054180`
- `0x1800548e8`
- `0x180055f40`
- `0x180057484`
- `0x18005782c`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005603d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005603d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180055ffd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180055ffd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056003`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056003`

## string_xrefs

- `0x180055f8a`: `GuestStateFileReopen`
- `0x180056097`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x180056043`: `Reopened file successfully.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall GuestStateFile::Reopen(RTL_SRWLOCK *this)
{
  __int64 FilePath; // rbx
  PVOID Ptr; // rcx
  int v4[4]; // [rsp+20h] [rbp-E0h] BYREF
  _OWORD v5[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v6[32]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v7[42]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  memset_0(v7, 0, sizeof(v7));
  FilePath = GuestStateFile::GetFilePath(this, v6);
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v7,
    "GuestStateFileReopen");
  v7[0] = &GuestStateFileTraceProvider::GuestStateFileReopen::`vftable';
  v5[0] = *(_OWORD *)FilePath;
  v5[1] = *(_OWORD *)(FilePath + 16);
  *(_QWORD *)(FilePath + 16) = 0;
  *(_QWORD *)(FilePath + 24) = 7;
  *(_WORD *)FilePath = 0;
  *(_OWORD *)v4 = *(_OWORD *)&this[12].Ptr;
  GuestStateFileTraceProvider::GuestStateFileReopen::StartActivity(v7, v4, v5);
  std::wstring::~wstring(v6);
  AcquireSRWLockExclusive(this + 5);
  LODWORD(this[6].Ptr) = GetCurrentThreadId();
  *(_QWORD *)v4 = this + 5;
  LOBYTE(v4[2]) = 1;
  Ptr = this[7].Ptr;
  if ( !Ptr )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F2,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
      (const char *)0x80070015LL,
      v4[0]);
  (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 24LL))(Ptr);
  LODWORD(this[6].Ptr) = 0;
  ReleaseSRWLockExclusive(this + 5);
  GuestStateFile::LogDebugTrace((GuestStateFile *)this, L"Reopened file successfully.");
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v7);
  v7[0] = &GuestStateFileTraceProvider::GuestStateFileReopen::`vftable';
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v7);
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(v7);
}

```

## disassembly

```asm
0x180055f40  push    rbp
0x180055f42  push    rbx
0x180055f43  push    rsi
0x180055f44  push    rdi
0x180055f45  lea     rbp, [rsp-0D8h]
0x180055f4d  sub     rsp, 1D8h
0x180055f54  mov     rax, cs:__security_cookie
0x180055f5b  xor     rax, rsp
0x180055f5e  mov     [rbp+0F0h+var_30], rax
0x180055f65  mov     rdi, rcx
0x180055f68  xor     edx, edx; Val
0x180055f6a  mov     r8d, 150h; Size
0x180055f70  lea     rcx, [rsp+1F0h+var_180]; void *
0x180055f75  call    memset_0
0x180055f7a  lea     rdx, [rsp+1F0h+var_1A0]
0x180055f7f  mov     rcx, rdi
0x180055f82  call    ?GetFilePath@GuestStateFile@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GuestStateFile::GetFilePath(void)
0x180055f87  mov     rbx, rax
0x180055f8a  lea     rdx, aGueststatefile_5; "GuestStateFileReopen"
0x180055f91  lea     rcx, [rsp+1F0h+var_180]
0x180055f96  call    ??0?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180055f9b  lea     rsi, ??_7GuestStateFileReopen@GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::GuestStateFileReopen::`vftable'
0x180055fa2  mov     [rsp+1F0h+var_180], rsi
0x180055fa7  movups  xmm0, xmmword ptr [rbx]
0x180055faa  movups  [rsp+1F0h+var_1C0], xmm0
0x180055faf  movups  xmm1, xmmword ptr [rbx+10h]
0x180055fb3  movups  [rsp+1F0h+var_1B0], xmm1
0x180055fb8  mov     qword ptr [rbx+10h], 0
0x180055fc0  mov     qword ptr [rbx+18h], 7
0x180055fc8  xor     eax, eax
0x180055fca  mov     [rbx], ax
0x180055fcd  movups  xmm0, xmmword ptr [rdi+60h]
0x180055fd1  movdqu  xmmword ptr [rsp+1F0h+var_1D0], xmm0
0x180055fd7  lea     r8, [rsp+1F0h+var_1C0]
0x180055fdc  lea     rdx, [rsp+1F0h+var_1D0]
0x180055fe1  lea     rcx, [rsp+1F0h+var_180]
0x180055fe6  call    ?StartActivity@GuestStateFileReopen@GuestStateFileTraceProvider@@QEAAXU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU3@@Z; GuestStateFileTraceProvider::GuestStateFileReopen::StartActivity(_GUID,std::wstring,_GUID const *)
0x180055feb  nop
0x180055fec  lea     rcx, [rsp+1F0h+var_1A0]
0x180055ff1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180055ff6  lea     rbx, [rdi+28h]
0x180055ffa  mov     rcx, rbx; SRWLock
0x180055ffd  call    cs:__imp_AcquireSRWLockExclusive
0x180056003  call    cs:__imp_GetCurrentThreadId
0x180056009  mov     [rbx+8], eax
0x18005600c  mov     qword ptr [rsp+1F0h+var_1D0], rbx; int
0x180056011  mov     byte ptr [rsp+1F0h+var_1D0+8], 1
0x180056016  mov     rax, [rbp+0F8h]
0x18005601d  mov     rcx, [rdi+38h]
0x180056021  test    rcx, rcx
0x180056024  jz      short loc_180056091
0x180056026  mov     rax, [rcx]
0x180056029  mov     rax, [rax+18h]
0x18005602d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056032  nop
0x180056033  mov     dword ptr [rbx+8], 0
0x18005603a  mov     rcx, rbx; SRWLock
0x18005603d  call    cs:__imp_ReleaseSRWLockExclusive
0x180056043  lea     rdx, aReopenedFileSu; "Reopened file successfully."
0x18005604a  mov     rcx, rdi; this
0x18005604d  call    ?LogDebugTrace@GuestStateFile@@IEBAXPEBG@Z; GuestStateFile::LogDebugTrace(ushort const *)
0x180056052  lea     rcx, [rsp+1F0h+var_180]
0x180056057  call    ?Stop@?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18005605c  nop
0x18005605d  mov     [rsp+1F0h+var_180], rsi
0x180056062  lea     rcx, [rsp+1F0h+var_180]
0x180056067  call    ?Destroy@?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18005606c  lea     rcx, [rsp+1F0h+var_180]
0x180056071  call    ??1?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180056076  mov     rcx, [rbp+0F0h+var_30]
0x18005607d  xor     rcx, rsp; StackCookie
0x180056080  call    __security_check_cookie
0x180056085  add     rsp, 1D8h
0x18005608c  pop     rdi
0x18005608d  pop     rsi
0x18005608e  pop     rbx
0x18005608f  pop     rbp
0x180056090  retn
0x180056091  mov     r9d, 80070015h; char *
0x180056097  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\gueststate\\guests"...
0x18005609e  mov     edx, 1F2h; void *
0x1800560a3  mov     rcx, rax; this
0x1800560a6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
