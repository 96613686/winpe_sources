# HcsDestroyLayer

- ea: `0x180014330`
- end: `0x1800143f5`
- name: `HcsDestroyLayer`
- size: `197`
- prototype: `HRESULT __stdcall(PCWSTR layerPath)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180002690`
- `0x1800032b8`
- `0x1800084c0`
- `0x180008ce8`
- `0x18000a964`
- `0x18000f4a8`
- `0x18000ffd4`
- `0x180014330`
- `0x18001a5f4`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18001438f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18001438f`

## string_xrefs

- `0x180014364`: `ComputeStorage_HcsDestroyLayer`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
HRESULT __stdcall HcsDestroyLayer(PCWSTR layerPath)
{
  const unsigned __int16 *v2; // rdx
  _QWORD v4[42]; // [rsp+30h] [rbp-168h] BYREF

  memset_0(v4, 0, sizeof(v4));
  wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v4,
    (__int64)"ComputeStorage_HcsDestroyLayer");
  v4[0] = &ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsDestroyLayer::`vftable';
  ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsDestroyLayer::StartActivity((ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsDestroyLayer *)v4);
  if ( PathFileExistsW(layerPath) )
    ComputeStorageInternal::DeleteFolderWithReparsePoints((ComputeStorageInternal *)layerPath, v2);
  wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v4);
  v4[0] = &ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsDestroyLayer::`vftable';
  wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v4);
  wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v4);
  return 0;
}

```

## disassembly

```asm
0x180014330  mov     [rsp+arg_8], rbx
0x180014335  push    rdi
0x180014336  sub     rsp, 190h
0x18001433d  mov     rax, cs:__security_cookie
0x180014344  xor     rax, rsp
0x180014347  mov     [rsp+198h+var_18], rax
0x18001434f  mov     rbx, rcx
0x180014352  xor     edx, edx; Val
0x180014354  mov     r8d, 150h; Size
0x18001435a  lea     rcx, [rsp+198h+var_168]; void *
0x18001435f  call    memset_0
0x180014364  lea     rdx, aComputestorage_5; "ComputeStorage_HcsDestroyLayer"
0x18001436b  lea     rcx, [rsp+198h+var_168]
0x180014370  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180014375  lea     rdi, ??_7ComputeStorage_HcsDestroyLayer@TraceProvider@Diagnostics@ComputeStorage@@6B@; const ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsDestroyLayer::`vftable'
0x18001437c  mov     [rsp+198h+var_168], rdi
0x180014381  lea     rcx, [rsp+198h+var_168]; this
0x180014386  call    ?StartActivity@ComputeStorage_HcsDestroyLayer@TraceProvider@Diagnostics@ComputeStorage@@QEAAXXZ; ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsDestroyLayer::StartActivity(void)
0x18001438b  nop
0x18001438c  mov     rcx, rbx; pszPath
0x18001438f  call    cs:__imp_PathFileExistsW
0x180014396  nop     dword ptr [rax+rax+00h]
0x18001439b  test    eax, eax
0x18001439d  jz      short loc_1800143A7
0x18001439f  mov     rcx, rbx; this
0x1800143a2  call    ?DeleteFolderWithReparsePoints@ComputeStorageInternal@@YAXPEBG@Z; ComputeStorageInternal::DeleteFolderWithReparsePoints(ushort const *)
0x1800143a7  lea     rcx, [rsp+198h+var_168]
0x1800143ac  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800143b1  nop
0x1800143b2  mov     [rsp+198h+var_168], rdi
0x1800143b7  lea     rcx, [rsp+198h+var_168]
0x1800143bc  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800143c1  lea     rcx, [rsp+198h+var_168]
0x1800143c6  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800143cb  xor     eax, eax
0x1800143cd  jmp     short loc_1800143D3
0x1800143cf  mov     eax, [rsp+198h+var_178]
0x1800143d3  mov     rcx, [rsp+198h+var_18]
0x1800143db  xor     rcx, rsp; StackCookie
0x1800143de  call    __security_check_cookie
0x1800143e3  mov     rbx, [rsp+198h+arg_8]
0x1800143eb  add     rsp, 190h
0x1800143f2  pop     rdi
0x1800143f3  retn
```
