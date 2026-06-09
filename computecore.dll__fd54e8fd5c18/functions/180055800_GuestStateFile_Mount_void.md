# GuestStateFile::Mount(void)

- ea: `0x180055800`
- end: `0x18005596c`
- name: `?Mount@GuestStateFile@@UEAAXXZ`
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
- `0x180055800`
- `0x18005701c`
- `0x18005782c`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800558fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800558fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800558bd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800558bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800558c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800558c3`

## string_xrefs

- `0x18005584a`: `GuestStateFileMount`
- `0x180055957`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x180055903`: `Mounted file successfully.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall GuestStateFile::Mount(RTL_SRWLOCK *this)
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
    "GuestStateFileMount");
  v7[0] = &GuestStateFileTraceProvider::GuestStateFileMount::`vftable';
  v5[0] = *(_OWORD *)FilePath;
  v5[1] = *(_OWORD *)(FilePath + 16);
  *(_QWORD *)(FilePath + 16) = 0;
  *(_QWORD *)(FilePath + 24) = 7;
  *(_WORD *)FilePath = 0;
  *(_OWORD *)v4 = *(_OWORD *)&this[12].Ptr;
  GuestStateFileTraceProvider::GuestStateFileMount::StartActivity(v7, v4, v5);
  std::wstring::~wstring(v6);
  AcquireSRWLockExclusive(this + 5);
  LODWORD(this[6].Ptr) = GetCurrentThreadId();
  *(_QWORD *)v4 = this + 5;
  LOBYTE(v4[2]) = 1;
  Ptr = this[7].Ptr;
  if ( !Ptr )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E0,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
      (const char *)0x80070015LL,
      v4[0]);
  (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
  LODWORD(this[6].Ptr) = 0;
  ReleaseSRWLockExclusive(this + 5);
  GuestStateFile::LogDebugTrace((GuestStateFile *)this, L"Mounted file successfully.");
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v7);
  v7[0] = &GuestStateFileTraceProvider::GuestStateFileMount::`vftable';
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v7);
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(v7);
}

```

## disassembly

```asm
0x180055800  push    rbp
0x180055802  push    rbx
0x180055803  push    rsi
0x180055804  push    rdi
0x180055805  lea     rbp, [rsp-0D8h]
0x18005580d  sub     rsp, 1D8h
0x180055814  mov     rax, cs:__security_cookie
0x18005581b  xor     rax, rsp
0x18005581e  mov     [rbp+0F0h+var_30], rax
0x180055825  mov     rdi, rcx
0x180055828  xor     edx, edx; Val
0x18005582a  mov     r8d, 150h; Size
0x180055830  lea     rcx, [rsp+1F0h+var_180]; void *
0x180055835  call    memset_0
0x18005583a  lea     rdx, [rsp+1F0h+var_1A0]
0x18005583f  mov     rcx, rdi
0x180055842  call    ?GetFilePath@GuestStateFile@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GuestStateFile::GetFilePath(void)
0x180055847  mov     rbx, rax
0x18005584a  lea     rdx, aGueststatefile_2; "GuestStateFileMount"
0x180055851  lea     rcx, [rsp+1F0h+var_180]
0x180055856  call    ??0?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18005585b  lea     rsi, ??_7GuestStateFileMount@GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::GuestStateFileMount::`vftable'
0x180055862  mov     [rsp+1F0h+var_180], rsi
0x180055867  movups  xmm0, xmmword ptr [rbx]
0x18005586a  movups  [rsp+1F0h+var_1C0], xmm0
0x18005586f  movups  xmm1, xmmword ptr [rbx+10h]
0x180055873  movups  [rsp+1F0h+var_1B0], xmm1
0x180055878  mov     qword ptr [rbx+10h], 0
0x180055880  mov     qword ptr [rbx+18h], 7
0x180055888  xor     eax, eax
0x18005588a  mov     [rbx], ax
0x18005588d  movups  xmm0, xmmword ptr [rdi+60h]
0x180055891  movdqu  xmmword ptr [rsp+1F0h+var_1D0], xmm0
0x180055897  lea     r8, [rsp+1F0h+var_1C0]
0x18005589c  lea     rdx, [rsp+1F0h+var_1D0]
0x1800558a1  lea     rcx, [rsp+1F0h+var_180]
0x1800558a6  call    ?StartActivity@GuestStateFileMount@GuestStateFileTraceProvider@@QEAAXU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU3@@Z; GuestStateFileTraceProvider::GuestStateFileMount::StartActivity(_GUID,std::wstring,_GUID const *)
0x1800558ab  nop
0x1800558ac  lea     rcx, [rsp+1F0h+var_1A0]
0x1800558b1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800558b6  lea     rbx, [rdi+28h]
0x1800558ba  mov     rcx, rbx; SRWLock
0x1800558bd  call    cs:__imp_AcquireSRWLockExclusive
0x1800558c3  call    cs:__imp_GetCurrentThreadId
0x1800558c9  mov     [rbx+8], eax
0x1800558cc  mov     qword ptr [rsp+1F0h+var_1D0], rbx; int
0x1800558d1  mov     byte ptr [rsp+1F0h+var_1D0+8], 1
0x1800558d6  mov     rax, [rbp+0F8h]
0x1800558dd  mov     rcx, [rdi+38h]
0x1800558e1  test    rcx, rcx
0x1800558e4  jz      short loc_180055951
0x1800558e6  mov     rax, [rcx]
0x1800558e9  mov     rax, [rax+10h]
0x1800558ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800558f2  nop
0x1800558f3  mov     dword ptr [rbx+8], 0
0x1800558fa  mov     rcx, rbx; SRWLock
0x1800558fd  call    cs:__imp_ReleaseSRWLockExclusive
0x180055903  lea     rdx, aMountedFileSuc; "Mounted file successfully."
0x18005590a  mov     rcx, rdi; this
0x18005590d  call    ?LogDebugTrace@GuestStateFile@@IEBAXPEBG@Z; GuestStateFile::LogDebugTrace(ushort const *)
0x180055912  lea     rcx, [rsp+1F0h+var_180]
0x180055917  call    ?Stop@?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18005591c  nop
0x18005591d  mov     [rsp+1F0h+var_180], rsi
0x180055922  lea     rcx, [rsp+1F0h+var_180]
0x180055927  call    ?Destroy@?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18005592c  lea     rcx, [rsp+1F0h+var_180]
0x180055931  call    ??1?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180055936  mov     rcx, [rbp+0F0h+var_30]
0x18005593d  xor     rcx, rsp; StackCookie
0x180055940  call    __security_check_cookie
0x180055945  add     rsp, 1D8h
0x18005594c  pop     rdi
0x18005594d  pop     rsi
0x18005594e  pop     rbx
0x18005594f  pop     rbp
0x180055950  retn
0x180055951  mov     r9d, 80070015h; char *
0x180055957  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\gueststate\\guests"...
0x18005595e  mov     edx, 1E0h; void *
0x180055963  mov     rcx, rax; this
0x180055966  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
