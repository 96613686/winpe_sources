# GuestStateFile::Open(ushort const *,GuestStateOpenFlags,ushort const *,ushort const *)

- ea: `0x180055ba0`
- end: `0x180055e23`
- name: `?Open@GuestStateFile@@UEAA_NPEBGW4GuestStateOpenFlags@@00@Z`
- size: `643`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180053b10`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x180009e8c`
- `0x1800136d0`
- `0x18001587c`
- `0x180020c90`
- `0x1800526dc`
- `0x180052930`
- `0x180053e24`
- `0x180054830`
- `0x180054890`
- `0x1800548e8`
- `0x180055ba0`
- `0x18005715c`
- `0x18005782c`
- `0x18005ae50`
- `0x18005b3c8`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180055d69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180055d69`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180055d2c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180055d2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180055d32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180055d32`
- `RPCRT4!UuidFromStringW` at `0x180055ca0`
- `RPCRT4!UuidFromStringW` at `0x180055ca0`

## string_xrefs

- `0x180055bf3`: `GuestStateFileOpen`
- `0x180055df9`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x180055e11`: `onecore\vm\common\gueststate\gueststatefile.cpp`
- `0x180055d6f`: `Opened file successfully.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall GuestStateFile::Open(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        __int64 a4,
        unsigned __int16 *StringUuid)
{
  bool v9; // zf
  char v10; // al
  __int64 v11; // r8
  _QWORD *v12; // rax
  void (__fastcall ***v13)(_QWORD, __int64); // rbx
  void (__fastcall ***v14)(_QWORD, __int64); // rsi
  char v15; // r15
  const struct _GUID *v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+20h] [rbp-E0h]
  void (__fastcall ***v19)(_QWORD, __int64); // [rsp+30h] [rbp-D0h] BYREF
  void (__fastcall ***v20)(_QWORD, __int64); // [rsp+38h] [rbp-C8h]
  UUID Uuid; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v22[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v23[42]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  memset_0(v23, 0, sizeof(v23));
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v23,
    "GuestStateFileOpen");
  v23[0] = &GuestStateFileTraceProvider::GuestStateFileOpen::`vftable';
  GuestStateFileTraceProvider::GuestStateFileOpen::StartActivity(
    (GuestStateFileTraceProvider::GuestStateFileOpen *)v23,
    StringUuid,
    a2,
    a3,
    v17);
  if ( !GuestStateFile::IsOpen((GuestStateFile *)a1)
    || (v9 = !GuestStateFile::IsTransient((GuestStateFile *)a1), v10 = 1, !v9) )
  {
    v10 = 0;
  }
  if ( v10 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1AC,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
      (const char *)0x80070032LL,
      v18);
  v22[0] = 0;
  v22[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v22[0]) = 0;
  Uuid = 0;
  if ( a4 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)(a4 + 2 * v11) );
    std::wstring::_Assign<unsigned short>(v22, a4);
  }
  if ( StringUuid && UuidFromStringW(StringUuid, &Uuid) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B8,
      (unsigned int)"onecore\\vm\\common\\gueststate\\gueststatefile.cpp",
      (const char *)0x80070057LL,
      v18);
  v20 = 0;
  if ( (*(_DWORD *)(a1 + 216) & 1) != 0 )
    v12 = (_QWORD *)GuestStateRawData::CreateInstance(&v19);
  else
    v12 = (_QWORD *)GuestStateData::CreateInstance(&v19);
  v13 = (void (__fastcall ***)(_QWORD, __int64))*v12;
  *v12 = 0;
  v20 = v13;
  if ( v19 )
    (**v19)(v19, 1);
  v14 = v13;
  v15 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, __int64), const unsigned __int16 *, _QWORD, __int64, unsigned __int16 *))(*v13)[1])(
          v13,
          a2,
          a3,
          a4,
          StringUuid);
  if ( v15 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 40));
    *(_DWORD *)(a1 + 48) = GetCurrentThreadId();
    v14 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 56);
    *(_QWORD *)(a1 + 56) = v13;
    std::wstring::operator=(a1 + 64, v22);
    *(UUID *)(a1 + 96) = Uuid;
    *(_DWORD *)(a1 + 48) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 40));
    GuestStateFile::LogDebugTrace((GuestStateFile *)a1, L"Opened file successfully.");
  }
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v23);
  if ( v14 )
    (**v14)(v14, 1);
  std::wstring::~wstring(v22);
  v23[0] = &GuestStateFileTraceProvider::GuestStateFileOpen::`vftable';
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v23);
  wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(v23);
  return v15;
}

```

## disassembly

```asm
0x180055ba0  push    rbp
0x180055ba2  push    rbx
0x180055ba3  push    rsi
0x180055ba4  push    rdi
0x180055ba5  push    r12
0x180055ba7  push    r13
0x180055ba9  push    r14
0x180055bab  push    r15
0x180055bad  lea     rbp, [rsp-0D8h]
0x180055bb5  sub     rsp, 1D8h
0x180055bbc  mov     rax, cs:__security_cookie
0x180055bc3  xor     rax, rsp
0x180055bc6  mov     [rbp+110h+var_50], rax
0x180055bcd  mov     rdi, r9
0x180055bd0  mov     r13d, r8d
0x180055bd3  mov     r12, rdx
0x180055bd6  mov     r14, rcx
0x180055bd9  mov     r15, [rbp+110h+StringUuid]
0x180055be0  xor     edx, edx; Val
0x180055be2  mov     r8d, 150h; Size
0x180055be8  lea     rcx, [rsp+210h+var_1A0]; void *
0x180055bed  call    memset_0
0x180055bf2  nop
0x180055bf3  lea     rdx, aGueststatefile_9; "GuestStateFileOpen"
0x180055bfa  lea     rcx, [rsp+210h+var_1A0]
0x180055bff  call    ??0?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180055c04  lea     rax, ??_7GuestStateFileOpen@GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::GuestStateFileOpen::`vftable'
0x180055c0b  mov     [rsp+210h+var_1A0], rax
0x180055c10  mov     r9d, r13d; unsigned int
0x180055c13  mov     r8, r12; unsigned __int16 *
0x180055c16  mov     rdx, r15; unsigned __int16 *
0x180055c19  lea     rcx, [rsp+210h+var_1A0]; this
0x180055c1e  call    ?StartActivity@GuestStateFileOpen@GuestStateFileTraceProvider@@QEAAXPEBG0IPEBU_GUID@@@Z; GuestStateFileTraceProvider::GuestStateFileOpen::StartActivity(ushort const *,ushort const *,uint,_GUID const *)
0x180055c23  nop
0x180055c24  mov     rcx, r14; this
0x180055c27  call    ?IsOpen@GuestStateFile@@UEBA_NXZ; GuestStateFile::IsOpen(void)
0x180055c2c  xor     esi, esi
0x180055c2e  test    al, al
0x180055c30  jz      short loc_180055C40
0x180055c32  mov     rcx, r14; this
0x180055c35  call    ?IsTransient@GuestStateFile@@UEBA_NXZ; GuestStateFile::IsTransient(void)
0x180055c3a  test    al, al
0x180055c3c  mov     al, 1
0x180055c3e  jz      short loc_180055C43
0x180055c40  mov     al, sil
0x180055c43  mov     rcx, [rbp+118h]; this
0x180055c4a  test    al, al
0x180055c4c  jnz     loc_180055E0B
0x180055c52  xorps   xmm0, xmm0
0x180055c55  movups  [rsp+210h+var_1C0], xmm0
0x180055c5a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180055c62  movdqu  [rsp+210h+var_1B0], xmm1
0x180055c68  mov     word ptr [rsp+210h+var_1C0], si
0x180055c6d  movdqa  xmmword ptr [rsp+210h+Uuid.Data1], xmm0
0x180055c73  test    rdi, rdi
0x180055c76  jz      short loc_180055C93
0x180055c78  or      r8, 0FFFFFFFFFFFFFFFFh
0x180055c7c  inc     r8
0x180055c7f  cmp     [rdi+r8*2], si
0x180055c84  jnz     short loc_180055C7C
0x180055c86  mov     rdx, rdi
0x180055c89  lea     rcx, [rsp+210h+var_1C0]
0x180055c8e  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180055c93  test    r15, r15
0x180055c96  jz      short loc_180055CBA
0x180055c98  lea     rdx, [rsp+210h+Uuid]; Uuid
0x180055c9d  mov     rcx, r15; StringUuid
0x180055ca0  call    cs:__imp_UuidFromStringW
0x180055ca6  test    eax, eax
0x180055ca8  setnz   al
0x180055cab  mov     rcx, [rbp+118h]; this
0x180055cb2  test    al, al
0x180055cb4  jnz     loc_180055DF3
0x180055cba  mov     [rsp+210h+var_1D8], rsi
0x180055cbf  mov     edx, [r14+0D8h]
0x180055cc6  lea     rcx, [rsp+210h+var_1E0]
0x180055ccb  test    dl, 1
0x180055cce  jz      short loc_180055CD7
0x180055cd0  call    ?CreateInstance@GuestStateRawData@@SA?AV?$unique_ptr@VIGuestStateData@@U?$default_delete@VIGuestStateData@@@std@@@std@@W4GuestStateAccessFormat@@@Z; GuestStateRawData::CreateInstance(GuestStateAccessFormat)
0x180055cd5  jmp     short loc_180055CDC
0x180055cd7  call    ?CreateInstance@GuestStateData@@SA?AV?$unique_ptr@VIGuestStateData@@U?$default_delete@VIGuestStateData@@@std@@@std@@XZ; GuestStateData::CreateInstance(void)
0x180055cdc  mov     rbx, [rax]
0x180055cdf  mov     [rax], rsi
0x180055ce2  mov     rcx, [rsp+210h+var_1E0]
0x180055ce7  test    rcx, rcx
0x180055cea  mov     [rsp+210h+var_1D8], rbx
0x180055cef  jz      short loc_180055D01
0x180055cf1  mov     rax, [rcx]
0x180055cf4  mov     edx, 1
0x180055cf9  mov     rax, [rax]
0x180055cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055d01  mov     rsi, rbx
0x180055d04  mov     rax, [rbx]
0x180055d07  mov     [rsp+210h+var_1F0], r15
0x180055d0c  mov     r9, rdi
0x180055d0f  mov     r8d, r13d
0x180055d12  mov     rdx, r12
0x180055d15  mov     rcx, rbx
0x180055d18  mov     rax, [rax+8]
0x180055d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055d21  mov     r15b, al
0x180055d24  test    al, al
0x180055d26  jz      short loc_180055D7E
0x180055d28  lea     rcx, [r14+28h]; SRWLock
0x180055d2c  call    cs:__imp_AcquireSRWLockExclusive
0x180055d32  call    cs:__imp_GetCurrentThreadId
0x180055d38  mov     [r14+30h], eax
0x180055d3c  mov     rsi, [r14+38h]
0x180055d40  mov     [r14+38h], rbx
0x180055d44  lea     rcx, [r14+40h]
0x180055d48  lea     rdx, [rsp+210h+var_1C0]
0x180055d4d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180055d52  movaps  xmm0, xmmword ptr [rsp+210h+Uuid.Data1]
0x180055d57  movdqu  xmmword ptr [r14+60h], xmm0
0x180055d5d  mov     dword ptr [r14+30h], 0
0x180055d65  lea     rcx, [r14+28h]; SRWLock
0x180055d69  call    cs:__imp_ReleaseSRWLockExclusive
0x180055d6f  lea     rdx, aOpenedFileSucc; "Opened file successfully."
0x180055d76  mov     rcx, r14; this
0x180055d79  call    ?LogDebugTrace@GuestStateFile@@IEBAXPEBG@Z; GuestStateFile::LogDebugTrace(ushort const *)
0x180055d7e  lea     rcx, [rsp+210h+var_1A0]
0x180055d83  call    ?Stop@?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180055d88  nop
0x180055d89  test    rsi, rsi
0x180055d8c  jz      short loc_180055DA2
0x180055d8e  mov     rax, [rsi]
0x180055d91  mov     edx, 1
0x180055d96  mov     rcx, rsi
0x180055d99  mov     rax, [rax]
0x180055d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055da1  nop
0x180055da2  lea     rcx, [rsp+210h+var_1C0]
0x180055da7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180055dac  nop
0x180055dad  lea     rax, ??_7GuestStateFileOpen@GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::GuestStateFileOpen::`vftable'
0x180055db4  mov     [rsp+210h+var_1A0], rax
0x180055db9  lea     rcx, [rsp+210h+var_1A0]
0x180055dbe  call    ?Destroy@?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180055dc3  lea     rcx, [rsp+210h+var_1A0]
0x180055dc8  call    ??1?$ActivityBase@VGuestStateFileTraceProvider@@$0A@$0BAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<GuestStateFileTraceProvider,0,4096,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180055dcd  mov     al, r15b
0x180055dd0  mov     rcx, [rbp+110h+var_50]
0x180055dd7  xor     rcx, rsp; StackCookie
0x180055dda  call    __security_check_cookie
0x180055ddf  add     rsp, 1D8h
0x180055de6  pop     r15
0x180055de8  pop     r14
0x180055dea  pop     r13
0x180055dec  pop     r12
0x180055dee  pop     rdi
0x180055def  pop     rsi
0x180055df0  pop     rbx
0x180055df1  pop     rbp
0x180055df2  retn
0x180055df3  mov     r9d, 80070057h; char *
0x180055df9  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\gueststate\\guests"...
0x180055e00  mov     edx, 1B8h; void *
0x180055e05  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180055e0b  mov     r9d, 80070032h; char *
0x180055e11  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\gueststate\\guests"...
0x180055e18  mov     edx, 1ACh; void *
0x180055e1d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
