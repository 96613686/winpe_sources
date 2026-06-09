# wlansecurity::crypto::impl::HmacSha1<OwnedAlgoStore>(OwnedAlgoStore const &,utl::span<uchar const,-1>,utl::span<uchar const,-1>,utl::span<uchar,-1>)

- ea: `0x14000b888`
- end: `0x14000b9ea`
- name: `??$HmacSha1@VOwnedAlgoStore@@@impl@crypto@wlansecurity@@YAJAEBVOwnedAlgoStore@@V?$span@$$CBE$0?0@utl@@1V?$span@E$0?0@5@@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000b838`

## callees

- `0x14000b888`
- `0x14000b9f0`
- `0x14000bb48`
- `0x14000cbe8`
- `0x14001f17c`
- `0x14009bbf0`

## import_xrefs

- `ksecdd!BCryptHashData` at `0x14000b963`
- `ksecdd!BCryptHashData` at `0x14000b963`
- `ksecdd!BCryptCreateHash` at `0x14000b937`
- `ksecdd!BCryptCreateHash` at `0x14000b937`
- `ksecdd!BCryptFinishHash` at `0x14000b982`
- `ksecdd!BCryptFinishHash` at `0x14000b982`
- `ksecdd!BCryptDestroyHash` at `0x14000b9a1`
- `ksecdd!BCryptDestroyHash` at `0x14000b9b7`

## pseudocode

```c
__int64 __fastcall wlansecurity::crypto::impl::HmacSha1<OwnedAlgoStore>(void *a1, __int64 a2, __int64 a3, __int64 a4)
{
  NTSTATUS v7; // ebx
  UCHAR *v9; // r12
  UCHAR *v10; // r14
  ULONG v11; // r15d
  ULONG v12; // esi
  UCHAR *pbSecret; // [rsp+20h] [rbp-50h]
  ULONG cbSecret; // [rsp+28h] [rbp-48h]
  __int64 v15; // [rsp+40h] [rbp-30h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+48h] [rbp-28h]
  BCRYPT_HASH_HANDLE *p_hHash; // [rsp+50h] [rbp-20h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+58h] [rbp-18h] BYREF
  char v19; // [rsp+60h] [rbp-10h]
  BCRYPT_HASH_HANDLE hHash; // [rsp+A0h] [rbp+30h] BYREF

  hHash = a1;
  OwnedAlgoStore::GetHmacSha1Algo(a1, &v15);
  if ( v15 && hAlgorithm )
  {
    v9 = *(UCHAR **)a2;
    v10 = *(UCHAR **)a4;
    v11 = *(_DWORD *)(a4 + 8);
    v12 = *(_DWORD *)(a2 + 8);
    p_hHash = &hHash;
    cbSecret = *(_DWORD *)(a3 + 8);
    pbSecret = *(UCHAR **)a3;
    hHash = 0;
    phHash = 0;
    v19 = 1;
    v7 = BCryptCreateHash(hAlgorithm, &phHash, 0, 0, pbSecret, cbSecret, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_hHash);
    if ( v7 < 0 || (v7 = BCryptHashData(hHash, v9, v12, 0), v7 < 0) )
    {
      wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
    }
    else
    {
      v7 = BCryptFinishHash(hHash, v10, v11, 0);
      if ( v7 >= 0 )
      {
        if ( hHash )
          ((void (__fastcall *)(BCRYPT_HASH_HANDLE))BCryptDestroyHash)(hHash);
        v7 = 0;
      }
      else if ( hHash )
      {
        ((void (__fastcall *)(BCRYPT_HASH_HANDLE))BCryptDestroyHash)(hHash);
      }
    }
  }
  else
  {
    v7 = -1073741436;
  }
  __1__unique_storage_U__resource_policy_PEAVGlobalOperationGuard__P6AXPEAV1___E_1_ReleaseReference_1_SAX0_ZU__integral_constant__K_00_wistd__PEAV1_PEAV1__0A___T_details_wil___details_wil__QEAA_XZ(&v15);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000b888  mov     [rsp-28h+arg_8], rbx
0x14000b88d  mov     [rsp-28h+arg_10], rsi
0x14000b892  mov     [rsp-28h+hHash], rcx
0x14000b897  push    rbp
0x14000b898  push    rdi
0x14000b899  push    r12
0x14000b89b  push    r14
0x14000b89d  push    r15
0x14000b89f  mov     rbp, rsp
0x14000b8a2  sub     rsp, 70h
0x14000b8a6  mov     rsi, rdx
0x14000b8a9  mov     rbx, r9
0x14000b8ac  lea     rdx, [rbp+var_30]
0x14000b8b0  mov     rdi, r8
0x14000b8b3  call    ?GetHmacSha1Algo@OwnedAlgoStore@@QEBA?AVAlgoReference@1@XZ; OwnedAlgoStore::GetHmacSha1Algo(void)
0x14000b8b8  cmp     [rbp+var_30], 0
0x14000b8bd  jnz     loc_14000B9CA
0x14000b8c3  mov     ebx, 0C0000184h
0x14000b8c8  lea     rcx, [rbp+var_30]
0x14000b8cc  call    ??1?$unique_storage@U?$resource_policy@PEAVGlobalOperationGuard@@P6AXPEAV1@@_E$1?ReleaseReference@1@SAX0@ZU?$integral_constant@_K$00@wistd@@PEAV1@PEAV1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000b8d1  lea     r11, [rsp+70h+var_s0]
0x14000b8d6  mov     eax, ebx
0x14000b8d8  mov     rbx, [r11+38h]
0x14000b8dc  mov     rsi, [r11+40h]
0x14000b8e0  mov     rsp, r11
0x14000b8e3  pop     r15
0x14000b8e5  pop     r14
0x14000b8e7  pop     r12
0x14000b8e9  pop     rdi
0x14000b8ea  pop     rbp
0x14000b8eb  retn
0x14000b8ed  mov     r12, [rsi]
0x14000b8f0  lea     rax, [rbp+hHash]
0x14000b8f4  mov     r14, [rbx]
0x14000b8f7  lea     rdx, [rbp+phHash]; phHash
0x14000b8fb  mov     r15d, [rbx+8]
0x14000b8ff  xor     r9d, r9d; cbHashObject
0x14000b902  mov     esi, [rsi+8]
0x14000b905  xor     r8d, r8d; pbHashObject
0x14000b908  mov     [rbp+var_20], rax
0x14000b90c  mov     eax, [rdi+8]
0x14000b90f  mov     [rsp+70h+dwFlags], 0; dwFlags
0x14000b917  mov     [rsp+70h+cbSecret], eax; cbSecret
0x14000b91b  mov     rax, [rdi]
0x14000b91e  mov     [rsp+70h+pbSecret], rax; pbSecret
0x14000b923  mov     [rbp+hHash], 0
0x14000b92b  mov     [rbp+phHash], 0
0x14000b933  mov     [rbp+var_10], 1
0x14000b937  call    cs:__imp_BCryptCreateHash
0x14000b93e  nop     dword ptr [rax+rax+00h]
0x14000b943  lea     rcx, [rbp+var_20]
0x14000b947  mov     ebx, eax
0x14000b949  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x14000b94e  test    ebx, ebx
0x14000b950  js      loc_14000B9DC
0x14000b956  mov     rcx, [rbp+hHash]; hHash
0x14000b95a  xor     r9d, r9d; dwFlags
0x14000b95d  mov     r8d, esi; cbInput
0x14000b960  mov     rdx, r12; pbInput
0x14000b963  call    cs:__imp_BCryptHashData
0x14000b96a  nop     dword ptr [rax+rax+00h]
0x14000b96f  mov     ebx, eax
0x14000b971  test    eax, eax
0x14000b973  js      short loc_14000B9DC
0x14000b975  mov     rcx, [rbp+hHash]; hHash
0x14000b979  xor     r9d, r9d; dwFlags
0x14000b97c  mov     r8d, r15d; cbOutput
0x14000b97f  mov     rdx, r14; pbOutput
0x14000b982  call    cs:__imp_BCryptFinishHash
0x14000b989  nop     dword ptr [rax+rax+00h]
0x14000b98e  mov     rcx, [rbp+hHash]
0x14000b992  mov     ebx, eax
0x14000b994  test    eax, eax
0x14000b996  jns     short loc_14000B9B2
0x14000b998  test    rcx, rcx
0x14000b99b  jz      loc_14000B8C8
0x14000b9a1  mov     rax, cs:__imp_BCryptDestroyHash
0x14000b9a8  call    _guard_dispatch_icall
0x14000b9ad  jmp     loc_14000B8C8
0x14000b9b2  test    rcx, rcx
0x14000b9b5  jz      short loc_14000B9C3
0x14000b9b7  mov     rax, cs:__imp_BCryptDestroyHash
0x14000b9be  call    _guard_dispatch_icall
0x14000b9c3  xor     ebx, ebx
0x14000b9c5  jmp     loc_14000B8C8
0x14000b9ca  mov     rcx, [rbp+hAlgorithm]; hAlgorithm
0x14000b9ce  test    rcx, rcx
0x14000b9d1  jz      loc_14000B8C3
0x14000b9d7  jmp     loc_14000B8ED
0x14000b9dc  lea     rcx, [rbp+hHash]
0x14000b9e0  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000b9e5  jmp     loc_14000B8C8
```
