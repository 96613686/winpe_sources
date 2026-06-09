# GuestStateFile::Close(void)

- ea: `0x180053800`
- end: `0x18005397a`
- name: `?Close@GuestStateFile@@UEAAXXZ`
- size: `378`
- prototype: `void __fastcall(GuestStateFile *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x1800067c0`
- `0x180007438`
- `0x180009e8c`
- `0x1800526dc`
- `0x180052930`
- `0x180053800`
- `0x180053e24`
- `0x180054180`
- `0x1800548e8`
- `0x18005658c`
- `0x18005782c`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053934`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053934`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800538ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800538ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800538d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800538d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall GuestStateFile::Close(RTL_SRWLOCK *this)
{
  __int64 FilePath; // rbx
  void (__fastcall ***Ptr)(_QWORD, __int64); // rcx
  RTL_SRWLOCK *v4; // rcx
  __int128 v5; // [rsp+20h] [rbp-E0h] BYREF
  _OWORD v6[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v7[32]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v8[42]; // [rsp+70h] [rbp-90h] BYREF

  memset_0(v8, 0, sizeof(v8));
  FilePath = GuestStateFile::GetFilePath(this, v7);
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v8,
    "GuestStateFileClose");
  v8[0] = &GuestStateFileTraceProvider::GuestStateFileClose::`vftable';
  v6[0] = *(_OWORD *)FilePath;
  v6[1] = *(_OWORD *)(FilePath + 16);
  *(_QWORD *)(FilePath + 16) = 0;
  *(_QWORD *)(FilePath + 24) = 7;
  *(_WORD *)FilePath = 0;
  v5 = *(_OWORD *)&this[12].Ptr;
  GuestStateFileTraceProvider::GuestStateFileClose::StartActivity(v8, &v5, v6);
  std::wstring::~wstring(v7);
  GuestStateFile::LogDebugTrace((GuestStateFile *)this, L"Closing file.");
  AcquireSRWLockExclusive(this + 5);
  LODWORD(this[6].Ptr) = GetCurrentThreadId();
  (*(void (__fastcall **)(PVOID))(*(_QWORD *)this[7].Ptr + 32LL))(this[7].Ptr);
  Ptr = (void (__fastcall ***)(_QWORD, __int64))this[7].Ptr;
  this[7].Ptr = 0;
  if ( Ptr )
    (**Ptr)(Ptr, 1);
  v4 = this + 8;
  this[10].Ptr = 0;
  if ( this[11].Ptr > (PVOID)7 )
    v4 = (RTL_SRWLOCK *)v4->Ptr;
  LOWORD(v4->Ptr) = 0;
  *(_OWORD *)&this[12].Ptr = 0;
  LODWORD(this[6].Ptr) = 0;
  ReleaseSRWLockExclusive(this + 5);
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)v8);
  v8[0] = &GuestStateFileTraceProvider::GuestStateFileClose::`vftable';
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v8);
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(v8);
}

```

## disassembly

```asm
0x180053800  push    rbp
0x180053802  push    rbx
0x180053803  push    rdi
0x180053804  push    r14
0x180053806  lea     rbp, [rsp-0D8h]
0x18005380e  sub     rsp, 1D8h
0x180053815  mov     rax, cs:__security_cookie
0x18005381c  xor     rax, rsp
0x18005381f  mov     [rbp+0F0h+var_30], rax
0x180053826  mov     rdi, rcx
0x180053829  xor     edx, edx; Val
0x18005382b  mov     r8d, 150h; Size
0x180053831  lea     rcx, [rsp+1F0h+var_180]; void *
0x180053836  call    memset_0
0x18005383b  lea     rdx, [rsp+1F0h+var_1A0]
0x180053840  mov     rcx, rdi
0x180053843  call    ?GetFilePath@GuestStateFile@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GuestStateFile::GetFilePath(void)
0x180053848  mov     rbx, rax
0x18005384b  lea     rdx, aGueststatefile_6; "GuestStateFileClose"
0x180053852  lea     rcx, [rsp+1F0h+var_180]
0x180053857  call    ??0?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18005385c  lea     r14, ??_7GuestStateFileClose@GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::GuestStateFileClose::`vftable'
0x180053863  mov     [rsp+1F0h+var_180], r14
0x180053868  movups  xmm0, xmmword ptr [rbx]
0x18005386b  movups  [rsp+1F0h+var_1C0], xmm0
0x180053870  movups  xmm1, xmmword ptr [rbx+10h]
0x180053874  movups  [rsp+1F0h+var_1B0], xmm1
0x180053879  mov     qword ptr [rbx+10h], 0
0x180053881  mov     qword ptr [rbx+18h], 7
0x180053889  xor     eax, eax
0x18005388b  mov     [rbx], ax
0x18005388e  movups  xmm0, xmmword ptr [rdi+60h]
0x180053892  movdqu  [rsp+1F0h+var_1D0], xmm0
0x180053898  lea     r8, [rsp+1F0h+var_1C0]
0x18005389d  lea     rdx, [rsp+1F0h+var_1D0]
0x1800538a2  lea     rcx, [rsp+1F0h+var_180]
0x1800538a7  call    ?StartActivity@GuestStateFileClose@GuestStateFileTraceProvider@@QEAAXU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU3@@Z; GuestStateFileTraceProvider::GuestStateFileClose::StartActivity(_GUID,std::wstring,_GUID const *)
0x1800538ac  nop
0x1800538ad  lea     rcx, [rsp+1F0h+var_1A0]
0x1800538b2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800538b7  lea     rdx, aClosingFile; "Closing file."
0x1800538be  mov     rcx, rdi; this
0x1800538c1  call    ?LogDebugTrace@GuestStateFile@@IEBAXPEBG@Z; GuestStateFile::LogDebugTrace(ushort const *)
0x1800538c6  lea     rcx, [rdi+28h]; SRWLock
0x1800538ca  call    cs:__imp_AcquireSRWLockExclusive
0x1800538d0  call    cs:__imp_GetCurrentThreadId
0x1800538d6  mov     [rdi+30h], eax
0x1800538d9  mov     rcx, [rdi+38h]
0x1800538dd  mov     rax, [rcx]
0x1800538e0  mov     rax, [rax+20h]
0x1800538e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800538e9  mov     rcx, [rdi+38h]
0x1800538ed  mov     qword ptr [rdi+38h], 0
0x1800538f5  test    rcx, rcx
0x1800538f8  jz      short loc_18005390A
0x1800538fa  mov     rax, [rcx]
0x1800538fd  mov     edx, 1
0x180053902  mov     rax, [rax]
0x180053905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005390a  lea     rcx, [rdi+40h]
0x18005390e  mov     qword ptr [rdi+50h], 0
0x180053916  cmp     qword ptr [rdi+58h], 7
0x18005391b  jbe     short loc_180053920
0x18005391d  mov     rcx, [rcx]
0x180053920  xor     eax, eax
0x180053922  mov     [rcx], ax
0x180053925  xorps   xmm0, xmm0
0x180053928  movdqu  xmmword ptr [rdi+60h], xmm0
0x18005392d  mov     [rdi+30h], eax
0x180053930  lea     rcx, [rdi+28h]; SRWLock
0x180053934  call    cs:__imp_ReleaseSRWLockExclusive
0x18005393a  lea     rcx, [rsp+1F0h+var_180]
0x18005393f  call    ?Stop@?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180053944  mov     [rsp+1F0h+var_180], r14
0x180053949  lea     rcx, [rsp+1F0h+var_180]
0x18005394e  call    ?Destroy@?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180053953  lea     rcx, [rsp+1F0h+var_180]
0x180053958  call    ??1?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18005395d  nop
0x18005395e  mov     rcx, [rbp+0F0h+var_30]
0x180053965  xor     rcx, rsp; StackCookie
0x180053968  call    __security_check_cookie
0x18005396d  add     rsp, 1D8h
0x180053974  pop     r14
0x180053976  pop     rdi
0x180053977  pop     rbx
0x180053978  pop     rbp
0x180053979  retn
```
