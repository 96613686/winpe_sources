# VmFileUtilities::CreateEmptyRuntimeStateFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18003a6f0`
- end: `0x18003a9a9`
- name: `?CreateEmptyRuntimeStateFile@VmFileUtilities@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `697`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800290a0`

## callees

- `0x1800067c0`
- `0x1800067e4`
- `0x180007438`
- `0x18001587c`
- `0x180027380`
- `0x180039a94`
- `0x180039cd8`
- `0x18003a140`
- `0x18003a6f0`
- `0x18003aa98`
- `0x18003acfc`
- `0x18003bf6c`
- `0x18003c458`
- `0x180092dac`
- `0x180093020`
- `0x1800947d4`
- `0x180094ba0`
- `0x180095d70`
- `0x1800a3010`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18003a76c`
- `RPCRT4!UuidCreate` at `0x18003a76c`

## string_xrefs

- `0x18003a958`: `onecore\vm\common\vml\VmGuid.h`
- `0x18003a736`: `VmFileUtilities_CreateEmptyRuntimeStateFile`
- `0x18003a943`: `onecore\vm\compute\dll\lib\core\vmfileutilities.cpp`
- `0x18003a96d`: `onecore\vm\compute\dll\lib\core\vmfileutilities.cpp`
- `0x18003a982`: `onecore\vm\compute\dll\lib\core\vmfileutilities.cpp`
- `0x18003a997`: `onecore\vm\compute\dll\lib\core\vmfileutilities.cpp`
- `0x18003a87d`: `/configuration/properties/version`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall VmFileUtilities::CreateEmptyRuntimeStateFile(_QWORD *a1)
{
  unsigned int v2; // eax
  HyperVStorageRepository *v3; // rax
  HyperVStorageRepository *v4; // rdi
  void *v5; // rbx
  const struct type_info *v6; // rdx
  __int64 v7; // rbx
  const struct type_info *v8; // rdx
  int v9; // eax
  int v10; // edi
  int v11; // eax
  int v12; // eax
  int v13; // eax
  HyperVStorageRepository *v15; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v16; // [rsp+40h] [rbp-C0h]
  UUID Uuid; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v18[42]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  memset_0(v18, 0, sizeof(v18));
  wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v18,
    "VmFileUtilities_CreateEmptyRuntimeStateFile");
  v18[0] = &ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_CreateEmptyRuntimeStateFile::`vftable';
  ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_CreateEmptyRuntimeStateFile::StartActivity((ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_CreateEmptyRuntimeStateFile *)v18);
  Uuid = 0;
  v2 = UuidCreate(&Uuid);
  if ( v2 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x18D,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v2,
      0);
  v16 = 0;
  v3 = (HyperVStorageRepository *)operator new(0x10u);
  *(_OWORD *)v3 = 0;
  v4 = HyperVStorageRepository::HyperVStorageRepository(v3);
  v5 = operator new(0xD0u);
  memset_0(v5, 0, 0xD0u);
  v15 = v4;
  v7 = HyperVRepository::HyperVRepository(v5, &Uuid, &v15);
  if ( v15 )
    (**(void (__fastcall ***)(HyperVStorageRepository *, __int64))v15)(v15, 1);
  Vml::VmSharableObject::AddUserInternal((Vml::VmSharableObject *)(v7 + 8), v6);
  v16 = v7;
  Vml::VmSharableObject::AddUserInternal((Vml::VmSharableObject *)(v7 + 8), v8);
  v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 344LL))(v7, 1);
  v10 = v9;
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x93,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\vmfileutilities.cpp",
      (const char *)(unsigned int)v9,
      5);
  v11 = HyperVRepository::WriteInteger((HyperVRepository *)v7, L"/configuration/properties/version", 3075);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x95,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\vmfileutilities.cpp",
      (const char *)(unsigned int)v11,
      5);
  v12 = HyperVRepository::Commit((HyperVRepository *)v7);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\vmfileutilities.cpp",
      (const char *)(unsigned int)v12,
      5);
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  v13 = HyperVRepository::Store(v7, a1, 1025);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x97,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\vmfileutilities.cpp",
      (const char *)(unsigned int)v13,
      5);
  if ( v10 >= 0 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 40LL))(v7);
  Vml::VmSharableObject::DecrementUserCount((Vml::VmSharableObject *)(v7 + 8));
  wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v18);
  Vml::VmSharableObject::DecrementUserCount((Vml::VmSharableObject *)(v7 + 8));
  v18[0] = &ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_CreateEmptyRuntimeStateFile::`vftable';
  wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v18);
  return wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(v18);
}

```

## disassembly

```asm
0x18003a6f0  push    rbp
0x18003a6f2  push    rbx
0x18003a6f3  push    rsi
0x18003a6f4  push    rdi
0x18003a6f5  push    r13
0x18003a6f7  push    r14
0x18003a6f9  lea     rbp, [rsp-0C8h]
0x18003a701  sub     rsp, 1C8h
0x18003a708  mov     rax, cs:__security_cookie
0x18003a70f  xor     rax, rsp
0x18003a712  mov     [rbp+0F0h+var_40], rax
0x18003a719  mov     rsi, rcx
0x18003a71c  mov     [rsp+1F0h+var_1D0], 0; unsigned int
0x18003a724  xor     edx, edx; Val
0x18003a726  mov     r8d, 150h; Size
0x18003a72c  lea     rcx, [rsp+1F0h+var_190]; void *
0x18003a731  call    memset_0
0x18003a736  lea     rdx, aVmfileutilitie_3; "VmFileUtilities_CreateEmptyRuntimeState"...
0x18003a73d  lea     rcx, [rsp+1F0h+var_190]
0x18003a742  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeLib@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18003a747  lea     r13, ??_7VmFileUtilities_CreateEmptyRuntimeStateFile@TraceProvider@Diagnostics@ComputeLib@@6B@; const ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_CreateEmptyRuntimeStateFile::`vftable'
0x18003a74e  mov     [rsp+1F0h+var_190], r13
0x18003a753  lea     rcx, [rsp+1F0h+var_190]; this
0x18003a758  call    ?StartActivity@VmFileUtilities_CreateEmptyRuntimeStateFile@TraceProvider@Diagnostics@ComputeLib@@QEAAXXZ; ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_CreateEmptyRuntimeStateFile::StartActivity(void)
0x18003a75d  nop
0x18003a75e  xorps   xmm0, xmm0
0x18003a761  movdqa  xmmword ptr [rsp+1F0h+Uuid.Data1], xmm0
0x18003a767  lea     rcx, [rsp+1F0h+Uuid]; Uuid
0x18003a76c  call    cs:__imp_UuidCreate
0x18003a772  mov     rcx, [rbp+0F8h]; this
0x18003a779  test    eax, eax
0x18003a77b  jnz     loc_18003A955
0x18003a781  mov     [rsp+1F0h+var_1B0], 0
0x18003a78a  lea     ecx, [rax+10h]; Size
0x18003a78d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a792  mov     qword ptr [rsp+1F0h+var_1C8], rax
0x18003a797  xorps   xmm0, xmm0
0x18003a79a  movups  xmmword ptr [rax], xmm0
0x18003a79d  mov     rcx, rax; this
0x18003a7a0  call    ??0HyperVStorageRepository@@QEAA@XZ; HyperVStorageRepository::HyperVStorageRepository(void)
0x18003a7a5  mov     rdi, rax
0x18003a7a8  mov     qword ptr [rsp+1F0h+var_1C8], rax
0x18003a7ad  mov     [rsp+1F0h+var_1D0], 1
0x18003a7b5  mov     r14d, 0D0h
0x18003a7bb  mov     ecx, r14d; Size
0x18003a7be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a7c3  mov     rbx, rax
0x18003a7c6  mov     qword ptr [rsp+1F0h+var_1C8], rax
0x18003a7cb  mov     r8d, r14d; Size
0x18003a7ce  xor     edx, edx; Val
0x18003a7d0  mov     rcx, rax; void *
0x18003a7d3  call    memset_0
0x18003a7d8  mov     qword ptr [rsp+1F0h+var_1C8], 0
0x18003a7e1  mov     [rsp+1F0h+var_1B8], rdi
0x18003a7e6  lea     r8, [rsp+1F0h+var_1B8]
0x18003a7eb  lea     rdx, [rsp+1F0h+Uuid]
0x18003a7f0  mov     rcx, rbx
0x18003a7f3  call    ??0HyperVRepository@@QEAA@AEBU_GUID@@$$QEAV?$unique_ptr@VIHyperVRepositoryBackingStore@@U?$default_delete@VIHyperVRepositoryBackingStore@@@std@@@std@@@Z; HyperVRepository::HyperVRepository(_GUID const &,std::unique_ptr<IHyperVRepositoryBackingStore> &&)
0x18003a7f8  mov     rbx, rax
0x18003a7fb  mov     [rsp+1F0h+var_1D0], 1
0x18003a803  mov     rcx, [rsp+1F0h+var_1B8]
0x18003a808  test    rcx, rcx
0x18003a80b  jz      short loc_18003A81D
0x18003a80d  mov     rdx, [rcx]
0x18003a810  mov     rax, [rdx]
0x18003a813  mov     edx, 1
0x18003a818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a81d  lea     r14, [rbx+8]
0x18003a821  mov     rcx, r14; this
0x18003a824  call    ?AddUserInternal@VmSharableObject@Vml@@AEAAKAEBVtype_info@@@Z; Vml::VmSharableObject::AddUserInternal(type_info const &)
0x18003a829  mov     [rsp+1F0h+var_1D0], 5; int
0x18003a831  mov     [rsp+1F0h+var_1B0], rbx
0x18003a836  xorps   xmm0, xmm0
0x18003a839  movups  [rsp+1F0h+var_1C8], xmm0
0x18003a83e  mov     qword ptr [rsp+1F0h+var_1C8], rbx
0x18003a843  mov     rcx, r14; this
0x18003a846  call    ?AddUserInternal@VmSharableObject@Vml@@AEAAKAEBVtype_info@@@Z; Vml::VmSharableObject::AddUserInternal(type_info const &)
0x18003a84b  mov     rax, [rbx]
0x18003a84e  mov     edx, 1
0x18003a853  mov     rcx, rbx
0x18003a856  mov     rax, [rax+158h]
0x18003a85d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a862  mov     edi, eax
0x18003a864  mov     dword ptr [rsp+1F0h+var_1C8+8], eax
0x18003a868  mov     rcx, [rbp+0F8h]; this
0x18003a86f  test    eax, eax
0x18003a871  js      loc_18003A96A
0x18003a877  mov     r8d, 0C03h; __int64
0x18003a87d  lea     rdx, ?VIRTUAL_MACHINE_VERSION_XPATH@@3QBGB; "/configuration/properties/version"
0x18003a884  mov     rcx, rbx; this
0x18003a887  call    ?WriteInteger@HyperVRepository@@UEAAJPEBG_J@Z; HyperVRepository::WriteInteger(ushort const *,__int64)
0x18003a88c  mov     rcx, [rbp+0F8h]; this
0x18003a893  test    eax, eax
0x18003a895  js      loc_18003A97F
0x18003a89b  mov     rcx, rbx; this
0x18003a89e  call    ?Commit@HyperVRepository@@UEAAJXZ; HyperVRepository::Commit(void)
0x18003a8a3  mov     rcx, [rbp+0F8h]; this
0x18003a8aa  test    eax, eax
0x18003a8ac  js      loc_18003A994
0x18003a8b2  cmp     qword ptr [rsi+18h], 7
0x18003a8b7  jbe     short loc_18003A8BC
0x18003a8b9  mov     rsi, [rsi]
0x18003a8bc  mov     r8d, 401h
0x18003a8c2  mov     rdx, rsi
0x18003a8c5  mov     rcx, rbx
0x18003a8c8  call    ?Store@HyperVRepository@@QEAAJPEBGW4HyperVFileOpenFlags@@@Z; HyperVRepository::Store(ushort const *,HyperVFileOpenFlags)
0x18003a8cd  mov     rcx, [rbp+0F8h]; this
0x18003a8d4  test    eax, eax
0x18003a8d6  js      short loc_18003A940
0x18003a8d8  test    edi, edi
0x18003a8da  js      short loc_18003A8EB
0x18003a8dc  mov     rax, [rbx]
0x18003a8df  mov     rcx, rbx
0x18003a8e2  mov     rax, [rax+28h]
0x18003a8e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a8eb  mov     rcx, r14; this
0x18003a8ee  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x18003a8f3  nop
0x18003a8f4  lea     rcx, [rsp+1F0h+var_190]
0x18003a8f9  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLib@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18003a8fe  nop
0x18003a8ff  mov     rcx, r14; this
0x18003a902  call    ?DecrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::DecrementUserCount(void)
0x18003a907  nop
0x18003a908  mov     [rsp+1F0h+var_190], r13
0x18003a90d  lea     rcx, [rsp+1F0h+var_190]
0x18003a912  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeLib@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18003a917  lea     rcx, [rsp+1F0h+var_190]
0x18003a91c  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeLib@@$0A@$0EA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeLib::Diagnostics::TraceProvider,0,64,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18003a921  mov     rcx, [rbp+0F0h+var_40]
0x18003a928  xor     rcx, rsp; StackCookie
0x18003a92b  call    __security_check_cookie
0x18003a930  add     rsp, 1C8h
0x18003a937  pop     r14
0x18003a939  pop     r13
0x18003a93b  pop     rdi
0x18003a93c  pop     rsi
0x18003a93d  pop     rbx
0x18003a93e  pop     rbp
0x18003a93f  retn
0x18003a940  mov     r9d, eax; char *
0x18003a943  lea     r8, aOnecoreVmCompu; "onecore\\vm\\compute\\dll\\lib\\core\\v"...
0x18003a94a  mov     edx, 97h; void *
0x18003a94f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003a955  mov     r9d, eax; char *
0x18003a958  lea     r8, aOnecoreVmCommo_17; "onecore\\vm\\common\\vml\\VmGuid.h"
0x18003a95f  mov     edx, 18Dh; void *
0x18003a964  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003a96a  mov     r9d, edi; char *
0x18003a96d  lea     r8, aOnecoreVmCompu; "onecore\\vm\\compute\\dll\\lib\\core\\v"...
0x18003a974  mov     edx, 93h; void *
0x18003a979  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003a97f  mov     r9d, eax; char *
0x18003a982  lea     r8, aOnecoreVmCompu; "onecore\\vm\\compute\\dll\\lib\\core\\v"...
0x18003a989  mov     edx, 95h; void *
0x18003a98e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003a994  mov     r9d, eax; char *
0x18003a997  lea     r8, aOnecoreVmCompu; "onecore\\vm\\compute\\dll\\lib\\core\\v"...
0x18003a99e  mov     edx, 96h; void *
0x18003a9a3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
