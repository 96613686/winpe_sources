# Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingHost(void)

- ea: `0x1800c7cec`
- end: `0x1800c7e4d`
- name: `??0ApiSamplingHost@ApiSampling@Inventory@Compat@Windows@@QEAA@XZ`
- size: `353`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::ApiSampling::ApiSamplingHost *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c8df0`
- `0x1800c8f70`
- `0x1800c9ec0`

## callees

- `0x1800c7b7c`
- `0x1800c7cec`
- `0x1800c7fe0`
- `0x1800c860c`
- `0x1800cc570`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7da6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7df3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7e1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7da6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7df3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7e1e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
Windows::Compat::Inventory::ApiSampling::ApiSamplingHost *__fastcall Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingHost(
        Windows::Compat::Inventory::ApiSampling::ApiSamplingHost *this)
{
  volatile signed __int32 *v2; // rdi
  void **v3; // rax
  void *v4; // rdx
  volatile signed __int32 *v5; // rdi
  void *v6; // rdi
  _BYTE v8[40]; // [rsp+20h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+18h] BYREF

  *(_QWORD *)this = &Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 10) = 0;
  *((_WORD *)this + 22) = 0;
  *((_BYTE *)this + 46) = 0;
  *((_QWORD *)this + 6) = 0;
  *(_OWORD *)((char *)this + 56) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 7;
  *((_WORD *)this + 28) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  if ( tipTest )
  {
    if ( !*((_QWORD *)tipTest + 31) && (*((_DWORD *)tipTest + 18) & 0x100) == 0 )
      goto LABEL_7;
    v2 = (volatile signed __int32 *)tipTest;
    tipTest = 0;
    if ( v2 )
    {
      if ( _InterlockedExchangeAdd(v2 + 84, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>::~merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>(v2);
        CoTaskMemFree((LPVOID)v2);
      }
LABEL_7:
      if ( tipTest )
        goto LABEL_14;
    }
  }
  v3 = (void **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>,>(&pv);
  v4 = *v3;
  *v3 = 0;
  v5 = (volatile signed __int32 *)tipTest;
  tipTest = v4;
  if ( v5 && _InterlockedExchangeAdd(v5 + 84, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>::~merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>(v5);
    CoTaskMemFree((LPVOID)v5);
  }
  v6 = pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 84, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>::~merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>(v6);
    CoTaskMemFree(v6);
  }
LABEL_14:
  tip2::details::shared_data<0,0,1>::start((char *)tipTest + 8, v8);
  Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingInitialize(this);
  return this;
}

```

## disassembly

```asm
0x1800c7cec  mov     [rsp+arg_0], rcx
0x1800c7cf1  push    rbx
0x1800c7cf2  push    rsi
0x1800c7cf3  push    rdi
0x1800c7cf4  sub     rsp, 30h
0x1800c7cf8  mov     rbx, rcx
0x1800c7cfb  lea     rax, ??_7ApiSamplingHost@ApiSampling@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::`vftable'
0x1800c7d02  mov     [rcx], rax
0x1800c7d05  xor     esi, esi
0x1800c7d07  mov     [rcx+8], rsi
0x1800c7d0b  mov     [rcx+10h], rsi
0x1800c7d0f  mov     [rcx+18h], rsi
0x1800c7d13  mov     [rcx+20h], rsi
0x1800c7d17  mov     [rcx+28h], esi
0x1800c7d1a  mov     [rcx+2Ch], si
0x1800c7d1e  mov     [rcx+2Eh], sil
0x1800c7d22  xor     eax, eax
0x1800c7d24  mov     [rcx+30h], rax
0x1800c7d28  xorps   xmm0, xmm0
0x1800c7d2b  movups  xmmword ptr [rcx+38h], xmm0
0x1800c7d2f  mov     [rcx+48h], rsi
0x1800c7d33  mov     qword ptr [rcx+50h], 7
0x1800c7d3b  mov     [rcx+38h], si
0x1800c7d3f  mov     [rcx+58h], rsi
0x1800c7d43  mov     [rcx+60h], rsi
0x1800c7d47  mov     [rcx+68h], rsi
0x1800c7d4b  mov     [rcx+70h], rsi
0x1800c7d4f  mov     [rcx+78h], rsi
0x1800c7d53  mov     [rcx+80h], rsi
0x1800c7d5a  mov     rax, cs:?tipTest@@3V?$tip_test@V?$merged_data@U_tip_ApiSamplingInvSvcTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@A; tip2::tip_test<tip2::details::merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>> tipTest
0x1800c7d61  test    rax, rax
0x1800c7d64  jz      short loc_1800C7DB5
0x1800c7d66  cmp     [rax+0F8h], rsi
0x1800c7d6d  jnz     short loc_1800C7D78
0x1800c7d6f  test    dword ptr [rax+48h], 100h
0x1800c7d76  jz      short loc_1800C7DAC
0x1800c7d78  mov     rdi, cs:?tipTest@@3V?$tip_test@V?$merged_data@U_tip_ApiSamplingInvSvcTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@A; tip2::tip_test<tip2::details::merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>> tipTest
0x1800c7d7f  mov     cs:?tipTest@@3V?$tip_test@V?$merged_data@U_tip_ApiSamplingInvSvcTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@A, rsi; tip2::tip_test<tip2::details::merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>> tipTest
0x1800c7d86  test    rdi, rdi
0x1800c7d89  jz      short loc_1800C7DB5
0x1800c7d8b  or      eax, 0FFFFFFFFh
0x1800c7d8e  lock xadd [rdi+150h], eax
0x1800c7d96  cmp     eax, 1
0x1800c7d99  jnz     short loc_1800C7DAC
0x1800c7d9b  mov     rcx, rdi
0x1800c7d9e  call    ??1?$merged_data@U_tip_ApiSamplingInvSvcTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>::~merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>(void)
0x1800c7da3  mov     rcx, rdi; pv
0x1800c7da6  call    cs:__imp_CoTaskMemFree
0x1800c7dac  cmp     cs:?tipTest@@3V?$tip_test@V?$merged_data@U_tip_ApiSamplingInvSvcTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@A, rsi; tip2::tip_test<tip2::details::merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>> tipTest
0x1800c7db3  jnz     short loc_1800C7E24
0x1800c7db5  lea     rcx, [rsp+48h+pv]
0x1800c7dba  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_ApiSamplingInvSvcTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_ApiSamplingInvSvcTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>,>(void)
0x1800c7dbf  mov     rdx, [rax]
0x1800c7dc2  mov     [rax], rsi
0x1800c7dc5  mov     rdi, cs:?tipTest@@3V?$tip_test@V?$merged_data@U_tip_ApiSamplingInvSvcTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@A; tip2::tip_test<tip2::details::merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>> tipTest
0x1800c7dcc  mov     cs:?tipTest@@3V?$tip_test@V?$merged_data@U_tip_ApiSamplingInvSvcTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@A, rdx; tip2::tip_test<tip2::details::merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>> tipTest
0x1800c7dd3  test    rdi, rdi
0x1800c7dd6  jz      short loc_1800C7DF9
0x1800c7dd8  or      eax, 0FFFFFFFFh
0x1800c7ddb  lock xadd [rdi+150h], eax
0x1800c7de3  cmp     eax, 1
0x1800c7de6  jnz     short loc_1800C7DF9
0x1800c7de8  mov     rcx, rdi
0x1800c7deb  call    ??1?$merged_data@U_tip_ApiSamplingInvSvcTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>::~merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>(void)
0x1800c7df0  mov     rcx, rdi; pv
0x1800c7df3  call    cs:__imp_CoTaskMemFree
0x1800c7df9  mov     rdi, [rsp+48h+pv]
0x1800c7dfe  test    rdi, rdi
0x1800c7e01  jz      short loc_1800C7E24
0x1800c7e03  or      eax, 0FFFFFFFFh
0x1800c7e06  lock xadd [rdi+150h], eax
0x1800c7e0e  cmp     eax, 1
0x1800c7e11  jnz     short loc_1800C7E24
0x1800c7e13  mov     rcx, rdi
0x1800c7e16  call    ??1?$merged_data@U_tip_ApiSamplingInvSvcTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>::~merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>(void)
0x1800c7e1b  mov     rcx, rdi; pv
0x1800c7e1e  call    cs:__imp_CoTaskMemFree
0x1800c7e24  mov     rcx, cs:?tipTest@@3V?$tip_test@V?$merged_data@U_tip_ApiSamplingInvSvcTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@A; tip2::tip_test<tip2::details::merged_data<_tip_ApiSamplingInvSvcTest_attributes,tip2::test_data_basic>> tipTest
0x1800c7e2b  add     rcx, 8
0x1800c7e2f  lea     rdx, [rsp+48h+var_28]
0x1800c7e34  call    ?start@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,1>::start(void)
0x1800c7e39  mov     rcx, rbx; this
0x1800c7e3c  call    ?ApiSamplingInitialize@ApiSamplingHost@ApiSampling@Inventory@Compat@Windows@@AEAAXXZ; Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingInitialize(void)
0x1800c7e41  nop
0x1800c7e42  mov     rax, rbx
0x1800c7e45  add     rsp, 30h
0x1800c7e49  pop     rdi
0x1800c7e4a  pop     rsi
0x1800c7e4b  pop     rbx
0x1800c7e4c  retn
```
