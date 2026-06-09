# GuestStateFile::MakeTransient(void)

- ea: `0x180054b00`
- end: `0x180054d40`
- name: `?MakeTransient@GuestStateFile@@UEAAXXZ`
- size: `576`
- prototype: `void __fastcall(GuestStateFile *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180028ea0`

## callees

- `0x1800067c0`
- `0x1800067e4`
- `0x180007438`
- `0x180009e8c`
- `0x18001587c`
- `0x1800526dc`
- `0x180052930`
- `0x180053e24`
- `0x180054180`
- `0x180054890`
- `0x1800548e8`
- `0x180054b00`
- `0x180056ad4`
- `0x18005782c`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054cb2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054cb2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180054c37`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180054c37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054c3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054c3d`

## string_xrefs

- `0x180054d2e`: `onecore\vm\common\gueststate\gueststatefile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall GuestStateFile::MakeTransient(RTL_SRWLOCK *this)
{
  __int64 FilePath; // rbx
  _DWORD *v3; // rbx
  PVOID Ptr; // rcx
  PVOID v5; // rdi
  RTL_SRWLOCK *v6; // rcx
  int v7[4]; // [rsp+20h] [rbp-E0h] BYREF
  _OWORD v8[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v9[32]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v10[42]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  memset_0(v10, 0, sizeof(v10));
  FilePath = GuestStateFile::GetFilePath(this, v9);
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v10,
    "GuestStateFileMakeTransient");
  v10[0] = &GuestStateFileTraceProvider::GuestStateFileMakeTransient::`vftable';
  v8[0] = *(_OWORD *)FilePath;
  v8[1] = *(_OWORD *)(FilePath + 16);
  *(_QWORD *)(FilePath + 16) = 0;
  *(_QWORD *)(FilePath + 24) = 7;
  *(_WORD *)FilePath = 0;
  *(_OWORD *)v7 = *(_OWORD *)&this[12].Ptr;
  GuestStateFileTraceProvider::GuestStateFileMakeTransient::StartActivity(v10, v7, v8);
  std::wstring::~wstring(v9);
  if ( GuestStateFile::IsTransient((GuestStateFile *)this) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x278,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
      (const char *)0x80070032LL,
      v7[0]);
  GuestStateFile::LogDebugTrace((GuestStateFile *)this, L"Making file transient.");
  v3 = operator new(0x30u);
  v3[3] = 0;
  v3[11] = 0;
  *(_QWORD *)v3 = &GuestStateTransientData::`vftable';
  v3[2] = 4096;
  *((_QWORD *)v3 + 2) = 0;
  *((_QWORD *)v3 + 3) = 0;
  *((_QWORD *)v3 + 4) = 0;
  v3[10] = 0;
  *(_QWORD *)v7 = v3;
  AcquireSRWLockExclusive(this + 5);
  LODWORD(this[6].Ptr) = GetCurrentThreadId();
  *(_QWORD *)&v8[0] = this + 5;
  BYTE8(v8[0]) = 1;
  Ptr = this[7].Ptr;
  if ( Ptr && (*(unsigned int (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 104LL))(Ptr) )
    (*(void (__fastcall **)(_DWORD *, PVOID))(*(_QWORD *)v3 + 160LL))(v3, this[7].Ptr);
  v5 = this[7].Ptr;
  this[7].Ptr = v3;
  v6 = this + 8;
  this[10].Ptr = 0;
  if ( this[11].Ptr > (PVOID)7 )
    v6 = (RTL_SRWLOCK *)v6->Ptr;
  LOWORD(v6->Ptr) = 0;
  *(_OWORD *)&this[12].Ptr = 0;
  LODWORD(this[6].Ptr) = 0;
  ReleaseSRWLockExclusive(this + 5);
  if ( v5 )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)v5 + 32LL))(v5);
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v10);
  if ( v5 )
    (**(void (__fastcall ***)(PVOID, __int64))v5)(v5, 1);
  v10[0] = &GuestStateFileTraceProvider::GuestStateFileMakeTransient::`vftable';
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v10);
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(v10);
}

```

## disassembly

```asm
0x180054b00  push    rbp
0x180054b02  push    rbx
0x180054b03  push    rsi
0x180054b04  push    rdi
0x180054b05  push    r12
0x180054b07  push    r14
0x180054b09  lea     rbp, [rsp-0D8h]
0x180054b11  sub     rsp, 1D8h
0x180054b18  mov     rax, cs:__security_cookie
0x180054b1f  xor     rax, rsp
0x180054b22  mov     [rbp+100h+var_40], rax
0x180054b29  mov     rsi, rcx
0x180054b2c  xor     edx, edx; Val
0x180054b2e  mov     r8d, 150h; Size
0x180054b34  lea     rcx, [rsp+200h+var_190]; void *
0x180054b39  call    memset_0
0x180054b3e  lea     rdx, [rsp+200h+var_1B0]
0x180054b43  mov     rcx, rsi
0x180054b46  call    ?GetFilePath@GuestStateFile@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GuestStateFile::GetFilePath(void)
0x180054b4b  mov     rbx, rax
0x180054b4e  lea     rdx, aGueststatefile_7; "GuestStateFileMakeTransient"
0x180054b55  lea     rcx, [rsp+200h+var_190]
0x180054b5a  call    ??0?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180054b5f  lea     r12, ??_7GuestStateFileMakeTransient@GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::GuestStateFileMakeTransient::`vftable'
0x180054b66  mov     [rsp+200h+var_190], r12
0x180054b6b  movups  xmm0, xmmword ptr [rbx]
0x180054b6e  movups  [rsp+200h+var_1D0], xmm0
0x180054b73  movups  xmm1, xmmword ptr [rbx+10h]
0x180054b77  movups  [rsp+200h+var_1C0], xmm1
0x180054b7c  mov     qword ptr [rbx+10h], 0
0x180054b84  mov     qword ptr [rbx+18h], 7
0x180054b8c  xor     eax, eax
0x180054b8e  mov     [rbx], ax
0x180054b91  movups  xmm0, xmmword ptr [rsi+60h]
0x180054b95  movdqu  xmmword ptr [rsp+200h+var_1E0], xmm0; int
0x180054b9b  lea     r8, [rsp+200h+var_1D0]
0x180054ba0  lea     rdx, [rsp+200h+var_1E0]
0x180054ba5  lea     rcx, [rsp+200h+var_190]
0x180054baa  call    ?StartActivity@GuestStateFileMakeTransient@GuestStateFileTraceProvider@@QEAAXU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU3@@Z; GuestStateFileTraceProvider::GuestStateFileMakeTransient::StartActivity(_GUID,std::wstring,_GUID const *)
0x180054baf  nop
0x180054bb0  lea     rcx, [rsp+200h+var_1B0]
0x180054bb5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180054bba  mov     rcx, rsi; this
0x180054bbd  call    ?IsTransient@GuestStateFile@@UEBA_NXZ; GuestStateFile::IsTransient(void)
0x180054bc2  mov     rcx, [rbp+108h]; this
0x180054bc9  test    al, al
0x180054bcb  jnz     loc_180054D28
0x180054bd1  lea     rdx, aMakingFileTran; "Making file transient."
0x180054bd8  mov     rcx, rsi; this
0x180054bdb  call    ?LogDebugTrace@GuestStateFile@@IEBAXPEBG@Z; GuestStateFile::LogDebugTrace(ushort const *)
0x180054be0  mov     ecx, 30h ; '0'; Size
0x180054be5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180054bea  mov     rbx, rax
0x180054bed  mov     dword ptr [rax+0Ch], 0
0x180054bf4  mov     dword ptr [rax+2Ch], 0
0x180054bfb  lea     rax, ??_7GuestStateTransientData@@6B@; const GuestStateTransientData::`vftable'
0x180054c02  mov     [rbx], rax
0x180054c05  mov     dword ptr [rbx+8], 1000h
0x180054c0c  mov     qword ptr [rbx+10h], 0
0x180054c14  mov     qword ptr [rbx+18h], 0
0x180054c1c  mov     qword ptr [rbx+20h], 0
0x180054c24  mov     dword ptr [rbx+28h], 0
0x180054c2b  mov     qword ptr [rsp+200h+var_1E0], rbx
0x180054c30  lea     r14, [rsi+28h]
0x180054c34  mov     rcx, r14; SRWLock
0x180054c37  call    cs:__imp_AcquireSRWLockExclusive
0x180054c3d  call    cs:__imp_GetCurrentThreadId
0x180054c43  mov     [r14+8], eax
0x180054c47  mov     qword ptr [rsp+200h+var_1D0], r14
0x180054c4c  mov     byte ptr [rsp+200h+var_1D0+8], 1
0x180054c51  mov     rcx, [rsi+38h]
0x180054c55  test    rcx, rcx
0x180054c58  jz      short loc_180054C80
0x180054c5a  mov     rax, [rcx]
0x180054c5d  mov     rax, [rax+68h]
0x180054c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c66  test    eax, eax
0x180054c68  jz      short loc_180054C80
0x180054c6a  mov     rax, [rbx]
0x180054c6d  mov     rdx, [rsi+38h]
0x180054c71  mov     rcx, rbx
0x180054c74  mov     rax, [rax+0A0h]
0x180054c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c80  mov     rdi, [rsi+38h]
0x180054c84  mov     [rsi+38h], rbx
0x180054c88  lea     rcx, [rsi+40h]
0x180054c8c  mov     qword ptr [rcx+10h], 0
0x180054c94  cmp     qword ptr [rcx+18h], 7
0x180054c99  jbe     short loc_180054C9E
0x180054c9b  mov     rcx, [rcx]
0x180054c9e  xor     eax, eax
0x180054ca0  mov     [rcx], ax
0x180054ca3  xorps   xmm0, xmm0
0x180054ca6  movdqu  xmmword ptr [rsi+60h], xmm0
0x180054cab  mov     [r14+8], eax
0x180054caf  mov     rcx, r14; SRWLock
0x180054cb2  call    cs:__imp_ReleaseSRWLockExclusive
0x180054cb8  test    rdi, rdi
0x180054cbb  jz      short loc_180054CCC
0x180054cbd  mov     rax, [rdi]
0x180054cc0  mov     rcx, rdi
0x180054cc3  mov     rax, [rax+20h]
0x180054cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ccc  lea     rcx, [rsp+200h+var_190]
0x180054cd1  call    ?Stop@?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180054cd6  nop
0x180054cd7  test    rdi, rdi
0x180054cda  jz      short loc_180054CF0
0x180054cdc  mov     rax, [rdi]
0x180054cdf  mov     edx, 1
0x180054ce4  mov     rcx, rdi
0x180054ce7  mov     rax, [rax]
0x180054cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054cef  nop
0x180054cf0  mov     [rsp+200h+var_190], r12
0x180054cf5  lea     rcx, [rsp+200h+var_190]
0x180054cfa  call    ?Destroy@?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180054cff  lea     rcx, [rsp+200h+var_190]
0x180054d04  call    ??1?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180054d09  mov     rcx, [rbp+100h+var_40]
0x180054d10  xor     rcx, rsp; StackCookie
0x180054d13  call    __security_check_cookie
0x180054d18  add     rsp, 1D8h
0x180054d1f  pop     r14
0x180054d21  pop     r12
0x180054d23  pop     rdi
0x180054d24  pop     rsi
0x180054d25  pop     rbx
0x180054d26  pop     rbp
0x180054d27  retn
0x180054d28  mov     r9d, 80070032h; char *
0x180054d2e  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\gueststate\\guests"...
0x180054d35  mov     edx, 278h; void *
0x180054d3a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
