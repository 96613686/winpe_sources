# HcsDetachLayerStorageFilter

- ea: `0x180014400`
- end: `0x18001450a`
- name: `HcsDetachLayerStorageFilter`
- size: `266`
- prototype: `HRESULT __stdcall(PCWSTR layerPath)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002690`
- `0x1800032b8`
- `0x1800084c0`
- `0x180008ce8`
- `0x180008fac`
- `0x18000a578`
- `0x18000a964`
- `0x18000f5d8`
- `0x18000ffd4`
- `0x1800127bc`
- `0x180014400`

## import_xrefs

- `wc_storage!WcDetachFilterEx` at `0x180014484`
- `wc_storage!WcDetachFilterEx` at `0x180014484`

## string_xrefs

- `0x180014434`: `ComputeStorage_HcsDetachLayerStorageFilter`
- `0x1800144f7`: `onecore\vm\compute\dll\storage\src\layer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __stdcall HcsDetachLayerStorageFilter(PCWSTR layerPath)
{
  char **v2; // rcx
  int v3; // eax
  const char *v4; // r9
  HRESULT result; // eax
  int v6; // [rsp+20h] [rbp-198h]
  char *Src[5]; // [rsp+28h] [rbp-190h] BYREF
  _QWORD v8[42]; // [rsp+50h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  memset_0(v8, 0, sizeof(v8));
  wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v8,
    (__int64)"ComputeStorage_HcsDetachLayerStorageFilter");
  v8[0] = &ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsDetachLayerStorageFilter::`vftable';
  ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsDetachLayerStorageFilter::StartActivity((ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsDetachLayerStorageFilter *)v8);
  try
  {
    Vml::CombineFilePath(Src, layerPath, L".\\");
    v2 = Src;
    if ( Src[3] > (char *)7 )
      v2 = (char **)Src[0];
    v3 = WcDetachFilterEx(v2, 0);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x17E,
        (unsigned int)"onecore\\vm\\compute\\dll\\storage\\src\\layer.cpp",
        (const char *)(unsigned int)v3,
        v6);
    std::wstring::~wstring(Src);
    wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)v8);
    v8[0] = &ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsDetachLayerStorageFilter::`vftable';
    wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v8);
    wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v8);
    result = 0;
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(
             retaddr,
             (void *)0x182,
             (unsigned int)"onecore\\vm\\compute\\dll\\storage\\src\\layer.cpp",
             v4);
  }
  return result;
}

```

## disassembly

```asm
0x180014400  mov     [rsp+arg_8], rbx
0x180014405  push    rdi
0x180014406  sub     rsp, 1B0h
0x18001440d  mov     rax, cs:__security_cookie
0x180014414  xor     rax, rsp
0x180014417  mov     [rsp+1B8h+var_18], rax
0x18001441f  mov     rbx, rcx
0x180014422  xor     edx, edx; Val
0x180014424  mov     r8d, 150h; Size
0x18001442a  lea     rcx, [rsp+1B8h+var_168]; void *
0x18001442f  call    memset_0
0x180014434  lea     rdx, aComputestorage_12; "ComputeStorage_HcsDetachLayerStorageFil"...
0x18001443b  lea     rcx, [rsp+1B8h+var_168]
0x180014440  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180014445  lea     rdi, ??_7ComputeStorage_HcsDetachLayerStorageFilter@TraceProvider@Diagnostics@ComputeStorage@@6B@; const ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsDetachLayerStorageFilter::`vftable'
0x18001444c  mov     [rsp+1B8h+var_168], rdi
0x180014451  lea     rcx, [rsp+1B8h+var_168]; this
0x180014456  call    ?StartActivity@ComputeStorage_HcsDetachLayerStorageFilter@TraceProvider@Diagnostics@ComputeStorage@@QEAAXXZ; ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsDetachLayerStorageFilter::StartActivity(void)
0x18001445b  nop
0x18001445c  lea     r8, pszMore; ".\\"
0x180014463  mov     rdx, rbx; pszPathIn
0x180014466  lea     rcx, [rsp+1B8h+Src]; Src
0x18001446b  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x180014470  nop
0x180014471  lea     rcx, [rsp+1B8h+Src]
0x180014476  cmp     [rsp+1B8h+var_178], 7
0x18001447c  cmova   rcx, [rsp+1B8h+Src]
0x180014482  xor     edx, edx
0x180014484  call    cs:__imp_WcDetachFilterEx
0x18001448b  nop     dword ptr [rax+rax+00h]
0x180014490  mov     rcx, [rsp+1B8h]; this
0x180014498  test    eax, eax
0x18001449a  js      short loc_1800144F4
0x18001449c  lea     rcx, [rsp+1B8h+Src]
0x1800144a1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800144a6  lea     rcx, [rsp+1B8h+var_168]
0x1800144ab  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800144b0  nop
0x1800144b1  mov     [rsp+1B8h+var_168], rdi
0x1800144b6  lea     rcx, [rsp+1B8h+var_168]
0x1800144bb  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800144c0  lea     rcx, [rsp+1B8h+var_168]
0x1800144c5  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800144ca  xor     eax, eax
0x1800144cc  jmp     short loc_1800144D2
0x1800144ce  mov     eax, [rsp+1B8h+var_198]
0x1800144d2  mov     rcx, [rsp+1B8h+var_18]
0x1800144da  xor     rcx, rsp; StackCookie
0x1800144dd  call    __security_check_cookie
0x1800144e2  mov     rbx, [rsp+1B8h+arg_8]
0x1800144ea  add     rsp, 1B0h
0x1800144f1  pop     rdi
0x1800144f2  retn
0x1800144f4  mov     r9d, eax; char *
0x1800144f7  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\dll\\storage\\src"...
0x1800144fe  mov     edx, 17Eh; void *
0x180014503  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
