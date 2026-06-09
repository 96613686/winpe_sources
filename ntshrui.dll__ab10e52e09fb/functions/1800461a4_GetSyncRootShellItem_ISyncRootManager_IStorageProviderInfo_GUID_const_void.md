# GetSyncRootShellItem(ISyncRootManager *,IStorageProviderInfo *,_GUID const &,void * *)

- ea: `0x1800461a4`
- end: `0x1800462d9`
- name: `?GetSyncRootShellItem@@YAJPEAUISyncRootManager@@PEAUIStorageProviderInfo@@AEBU_GUID@@PEAPEAX@Z`
- size: `309`
- prototype: `int(struct ISyncRootManager *, struct IStorageProviderInfo *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180045b7c`

## callees

- `0x18001d18c`
- `0x1800214cc`
- `0x1800461a4`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046215`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004627a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800462ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800462be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046215`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004627a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800462ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800462be`
- `SHELL32!SHCreateItemFromParsingName` at `0x180046292`
- `SHELL32!SHCreateItemFromParsingName` at `0x180046292`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetSyncRootShellItem(
        struct ISyncRootManager *a1,
        struct IStorageProviderInfo *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 (__fastcall *v7)(struct IStorageProviderInfo *, __int64); // rbx
  __int64 v8; // rax
  int v9; // eax
  HRESULT v10; // ebx
  __int64 (__fastcall *v12)(struct ISyncRootManager *, LPVOID, _QWORD, __int64); // rbx
  __int64 v13; // rax
  __int64 v14; // rdx
  int v15; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  PCWSTR pszPath; // [rsp+58h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+30h] BYREF

  pv = 0;
  v7 = *(__int64 (__fastcall **)(struct IStorageProviderInfo *, __int64))(*(_QWORD *)a2 + 24LL);
  v8 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
  v9 = v7(a2, v8);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\StorageProviderUtils.h",
      (const char *)(unsigned int)v9,
      v15);
LABEL_3:
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)v10;
  }
  pszPath = 0;
  v12 = *(__int64 (__fastcall **)(struct ISyncRootManager *, LPVOID, _QWORD, __int64))(*(_QWORD *)a1 + 136LL);
  v13 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszPath);
  v10 = v12(a1, pv, 0, v13);
  if ( v10 < 0 )
  {
    v14 = 228;
    goto LABEL_8;
  }
  v10 = SHCreateItemFromParsingName(pszPath, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, a4);
  if ( v10 < 0 )
  {
    v14 = 229;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\StorageProviderUtils.h",
      (const char *)(unsigned int)v10,
      v15);
    if ( pszPath )
      CoTaskMemFree((LPVOID)pszPath);
    goto LABEL_3;
  }
  if ( pszPath )
    CoTaskMemFree((LPVOID)pszPath);
  if ( pv )
    CoTaskMemFree(pv);
  return 0;
}

```

## disassembly

```asm
0x1800461a4  mov     [rsp-18h+arg_0], rbx
0x1800461a9  mov     [rsp-18h+arg_18], rsi
0x1800461ae  mov     [rsp-18h+pv], r8
0x1800461b3  push    rbp
0x1800461b4  push    rdi
0x1800461b5  push    r14
0x1800461b7  mov     rbp, rsp
0x1800461ba  sub     rsp, 30h
0x1800461be  mov     rsi, r9
0x1800461c1  mov     rdi, rdx
0x1800461c4  mov     r14, rcx
0x1800461c7  mov     [rbp+pv], 0
0x1800461cf  mov     rax, [rdx]
0x1800461d2  mov     rbx, [rax+18h]
0x1800461d6  lea     rcx, [rbp+pv]
0x1800461da  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1800461df  mov     rdx, rax
0x1800461e2  mov     rcx, rdi
0x1800461e5  mov     rax, rbx
0x1800461e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800461ed  mov     ebx, eax
0x1800461ef  test    eax, eax
0x1800461f1  jns     short loc_180046222
0x1800461f3  mov     rcx, [rbp+18h]; this
0x1800461f7  mov     r9d, eax; char *
0x1800461fa  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180046201  mov     edx, 0E1h; void *
0x180046206  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004620b  nop
0x18004620c  mov     rcx, [rbp+pv]; pv
0x180046210  test    rcx, rcx
0x180046213  jz      short loc_18004621B
0x180046215  call    cs:__imp_CoTaskMemFree
0x18004621b  mov     eax, ebx
0x18004621d  jmp     loc_1800462C6
0x180046222  mov     [rbp+pszPath], 0
0x18004622a  mov     rax, [r14]
0x18004622d  mov     rbx, [rax+88h]
0x180046234  lea     rcx, [rbp+pszPath]
0x180046238  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18004623d  mov     r9, rax
0x180046240  xor     r8d, r8d
0x180046243  mov     rdx, [rbp+pv]
0x180046247  mov     rcx, r14
0x18004624a  mov     rax, rbx
0x18004624d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046252  mov     ebx, eax
0x180046254  test    eax, eax
0x180046256  jns     short loc_180046282
0x180046258  mov     edx, 0E4h; void *
0x18004625d  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180046264  mov     r9d, ebx; char *
0x180046267  mov     rcx, [rbp+18h]; this
0x18004626b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046270  nop
0x180046271  mov     rcx, [rbp+pszPath]; pv
0x180046275  test    rcx, rcx
0x180046278  jz      short loc_18004620C
0x18004627a  call    cs:__imp_CoTaskMemFree
0x180046280  jmp     short loc_18004620C
0x180046282  mov     r9, rsi; ppv
0x180046285  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18004628c  xor     edx, edx; pbc
0x18004628e  mov     rcx, [rbp+pszPath]; pszPath
0x180046292  call    cs:__imp_SHCreateItemFromParsingName
0x180046298  mov     ebx, eax
0x18004629a  test    eax, eax
0x18004629c  jns     short loc_1800462A5
0x18004629e  mov     edx, 0E5h
0x1800462a3  jmp     short loc_18004625D
0x1800462a5  mov     rcx, [rbp+pszPath]; pv
0x1800462a9  test    rcx, rcx
0x1800462ac  jz      short loc_1800462B5
0x1800462ae  call    cs:__imp_CoTaskMemFree
0x1800462b4  nop
0x1800462b5  mov     rcx, [rbp+pv]; pv
0x1800462b9  test    rcx, rcx
0x1800462bc  jz      short loc_1800462C4
0x1800462be  call    cs:__imp_CoTaskMemFree
0x1800462c4  xor     eax, eax
0x1800462c6  mov     rbx, [rsp+30h+arg_0]
0x1800462cb  mov     rsi, [rsp+30h+arg_18]
0x1800462d0  add     rsp, 30h
0x1800462d4  pop     r14
0x1800462d6  pop     rdi
0x1800462d7  pop     rbp
0x1800462d8  retn
```
