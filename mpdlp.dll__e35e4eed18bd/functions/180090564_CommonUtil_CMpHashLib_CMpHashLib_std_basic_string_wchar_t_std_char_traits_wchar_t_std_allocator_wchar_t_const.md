# CommonUtil::CMpHashLib::CMpHashLib(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180090564`
- end: `0x1800906cb`
- name: `??0CMpHashLib@CommonUtil@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `359`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180091450`
- `0x18014f210`
- `0x18014f420`

## callees

- `0x1800398a0`
- `0x18003d6c8`
- `0x180090564`
- `0x180090c70`
- `0x180090ea4`
- `0x180090f5c`
- `0x180105e54`
- `0x18010cb40`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x180090653`
- `bcrypt!BCryptCreateHash` at `0x180090653`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800906a2`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800906a2`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800905e9`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800905e9`
- `bcrypt!BCryptDestroyHash` at `0x180090690`
- `bcrypt!BCryptDestroyHash` at `0x180090690`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CommonUtil::CMpHashLib::CMpHashLib(__int64 a1, const WCHAR *a2)
{
  const WCHAR *v2; // rdi
  ULONG v4; // r9d
  char v5; // al
  NTSTATUS v6; // eax
  __int64 v7; // rcx
  unsigned int *v8; // r8
  unsigned int HashLength; // eax
  __int64 v10; // rcx
  unsigned int *v11; // r8
  unsigned int ObjectLength; // eax
  __int64 v13; // rcx
  NTSTATUS v14; // eax
  __int64 v15; // rcx
  int v17; // [rsp+40h] [rbp-40h] BYREF
  _DWORD v18[3]; // [rsp+44h] [rbp-3Ch] BYREF
  __int64 v19; // [rsp+50h] [rbp-30h]
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+60h] [rbp-20h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+68h] [rbp-18h] BYREF

  v2 = a2;
  v19 = a1;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  std::wstring::wstring(a1 + 32, a2);
  *(_BYTE *)(a1 + 64) = 0;
  if ( (unsigned int)MpIsWindows8OrGreater() )
  {
    *(_DWORD *)(a1 + 28) = 32;
    *(_DWORD *)(a1 + 24) = 32;
  }
  v4 = *(_DWORD *)(a1 + 28);
  if ( (v4 & 0x20) == 0 || (v5 = 1, (*(_BYTE *)(a1 + 24) & 0x20) == 0) )
    v5 = 0;
  *(_BYTE *)(a1 + 64) = v5;
  phAlgorithm = 0;
  if ( *((_QWORD *)v2 + 3) > 7u )
    v2 = *(const WCHAR **)v2;
  v6 = BCryptOpenAlgorithmProvider(&phAlgorithm, v2, 0, v4);
  CommonUtil::CCommonThrowHR::operator=(v7, v6 | 0x10000000u);
  v17 = 0;
  HashLength = CommonUtil::UtilBCryptGetHashLength((CommonUtil *)phAlgorithm, &v17, v8);
  CommonUtil::CCommonThrowHR::operator=(v10, HashLength);
  v18[0] = 0;
  ObjectLength = CommonUtil::UtilBCryptGetObjectLength((CommonUtil *)phAlgorithm, v18, v11);
  CommonUtil::CCommonThrowHR::operator=(v13, ObjectLength);
  phHash = 0;
  if ( *(_BYTE *)(a1 + 64) )
  {
    v14 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, *(_DWORD *)(a1 + 24));
    CommonUtil::CCommonThrowHR::operator=(v15, v14 | 0x10000000u);
  }
  CommonUtil::CUniqueHandle<CommonUtil::CAutoCloseBCryptHashHandle>::Swap(a1, &phAlgorithm);
  CommonUtil::CUniqueHandle<CommonUtil::CAutoCloseBCryptHashHandle>::Swap(a1 + 8, &phHash);
  *(_DWORD *)(a1 + 20) = v17;
  *(_DWORD *)(a1 + 16) = v18[0];
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return a1;
}

```

## disassembly

```asm
0x180090564  mov     [rsp-18h+arg_10], rbx
0x180090569  push    rbp
0x18009056a  push    rsi
0x18009056b  push    rdi
0x18009056c  mov     rbp, rsp
0x18009056f  sub     rsp, 80h
0x180090576  mov     rax, cs:__security_cookie
0x18009057d  xor     rax, rsp
0x180090580  mov     [rbp+var_10], rax
0x180090584  mov     rdi, rdx
0x180090587  mov     rbx, rcx
0x18009058a  mov     [rbp+var_30], rcx
0x18009058e  xor     esi, esi
0x180090590  mov     [rcx], rsi
0x180090593  mov     [rcx+8], rsi
0x180090597  mov     [rcx+18h], rsi
0x18009059b  add     rcx, 20h ; ' '
0x18009059f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800905a4  nop
0x1800905a5  mov     [rbx+40h], sil
0x1800905a9  call    MpIsWindows8OrGreater
0x1800905ae  lea     ecx, [rsi+20h]
0x1800905b1  test    eax, eax
0x1800905b3  jz      short loc_1800905BB
0x1800905b5  mov     [rbx+1Ch], ecx
0x1800905b8  mov     [rbx+18h], ecx
0x1800905bb  mov     r9d, [rbx+1Ch]; dwFlags
0x1800905bf  test    cl, r9b
0x1800905c2  jz      short loc_1800905CB
0x1800905c4  test    [rbx+18h], cl
0x1800905c7  mov     al, 1
0x1800905c9  jnz     short loc_1800905CE
0x1800905cb  mov     al, sil
0x1800905ce  mov     [rbx+40h], al
0x1800905d1  mov     [rbp+phAlgorithm], rsi
0x1800905d5  cmp     qword ptr [rdi+18h], 7
0x1800905da  jbe     short loc_1800905DF
0x1800905dc  mov     rdi, [rdi]
0x1800905df  xor     r8d, r8d; pszImplementation
0x1800905e2  mov     rdx, rdi; pszAlgId
0x1800905e5  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800905e9  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800905ef  mov     edi, 10000000h
0x1800905f4  or      eax, edi
0x1800905f6  mov     edx, eax
0x1800905f8  call    ??4CCommonThrowHR@CommonUtil@@QEAAXJ@Z; CommonUtil::CCommonThrowHR::operator=(long)
0x1800905fd  mov     [rbp+var_40], esi
0x180090600  lea     rdx, [rbp+var_40]; void *
0x180090604  mov     rcx, [rbp+phAlgorithm]; this
0x180090608  call    ?UtilBCryptGetHashLength@CommonUtil@@YAJPEAXAEAK@Z; CommonUtil::UtilBCryptGetHashLength(void *,ulong &)
0x18009060d  mov     edx, eax
0x18009060f  call    ??4CCommonThrowHR@CommonUtil@@QEAAXJ@Z; CommonUtil::CCommonThrowHR::operator=(long)
0x180090614  mov     [rbp+var_3C], esi
0x180090617  lea     rdx, [rbp+var_3C]; void *
0x18009061b  mov     rcx, [rbp+phAlgorithm]; this
0x18009061f  call    ?UtilBCryptGetObjectLength@CommonUtil@@YAJPEAXAEAK@Z; CommonUtil::UtilBCryptGetObjectLength(void *,ulong &)
0x180090624  mov     edx, eax
0x180090626  call    ??4CCommonThrowHR@CommonUtil@@QEAAXJ@Z; CommonUtil::CCommonThrowHR::operator=(long)
0x18009062b  mov     [rbp+phHash], rsi
0x18009062f  cmp     [rbx+40h], sil
0x180090633  jz      short loc_180090662
0x180090635  mov     eax, [rbx+18h]
0x180090638  mov     [rsp+80h+dwFlags], eax; dwFlags
0x18009063c  mov     [rsp+80h+cbSecret], esi; cbSecret
0x180090640  mov     [rsp+80h+pbSecret], rsi; pbSecret
0x180090645  xor     r9d, r9d; cbHashObject
0x180090648  xor     r8d, r8d; pbHashObject
0x18009064b  lea     rdx, [rbp+phHash]; phHash
0x18009064f  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180090653  call    cs:__imp_BCryptCreateHash
0x180090659  or      eax, edi
0x18009065b  mov     edx, eax
0x18009065d  call    ??4CCommonThrowHR@CommonUtil@@QEAAXJ@Z; CommonUtil::CCommonThrowHR::operator=(long)
0x180090662  lea     rdx, [rbp+phAlgorithm]
0x180090666  mov     rcx, rbx
0x180090669  call    ?Swap@?$CUniqueHandle@UCAutoCloseBCryptHashHandle@CommonUtil@@@CommonUtil@@QEAAXAEAV12@@Z; CommonUtil::CUniqueHandle<CommonUtil::CAutoCloseBCryptHashHandle>::Swap(CommonUtil::CUniqueHandle<CommonUtil::CAutoCloseBCryptHashHandle> &)
0x18009066e  lea     rcx, [rbx+8]
0x180090672  lea     rdx, [rbp+phHash]
0x180090676  call    ?Swap@?$CUniqueHandle@UCAutoCloseBCryptHashHandle@CommonUtil@@@CommonUtil@@QEAAXAEAV12@@Z; CommonUtil::CUniqueHandle<CommonUtil::CAutoCloseBCryptHashHandle>::Swap(CommonUtil::CUniqueHandle<CommonUtil::CAutoCloseBCryptHashHandle> &)
0x18009067b  mov     ecx, [rbp+var_40]
0x18009067e  mov     [rbx+14h], ecx
0x180090681  mov     eax, [rbp+var_3C]
0x180090684  mov     [rbx+10h], eax
0x180090687  mov     rcx, [rbp+phHash]; hHash
0x18009068b  test    rcx, rcx
0x18009068e  jz      short loc_180090697
0x180090690  call    cs:__imp_BCryptDestroyHash
0x180090696  nop
0x180090697  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18009069b  test    rcx, rcx
0x18009069e  jz      short loc_1800906A9
0x1800906a0  xor     edx, edx; dwFlags
0x1800906a2  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800906a8  nop
0x1800906a9  mov     rax, rbx
0x1800906ac  mov     rcx, [rbp+var_10]
0x1800906b0  xor     rcx, rsp; StackCookie
0x1800906b3  call    __security_check_cookie
0x1800906b8  mov     rbx, [rsp+80h+arg_10]
0x1800906c0  add     rsp, 80h
0x1800906c7  pop     rdi
0x1800906c8  pop     rsi
0x1800906c9  pop     rbp
0x1800906ca  retn
```
