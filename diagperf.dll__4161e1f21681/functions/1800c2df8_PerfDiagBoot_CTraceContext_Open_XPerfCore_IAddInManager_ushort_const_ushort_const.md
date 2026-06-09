# PerfDiagBoot::CTraceContext::Open(XPerfCore::IAddInManager *,ushort const *,ushort const *)

- ea: `0x1800c2df8`
- end: `0x1800c3347`
- name: `?Open@CTraceContext@PerfDiagBoot@@QEAAJPEAUIAddInManager@XPerfCore@@PEBG1@Z`
- size: `1359`
- prototype: `__int64 __fastcall(PerfDiagBoot::CTraceContext *__hidden this, struct XPerfCore::IAddInManager *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800279d8`

## callees

- `0x180001034`
- `0x1800010e0`
- `0x180001198`
- `0x18001769c`
- `0x1800405ac`
- `0x180082b74`
- `0x1800c2d68`
- `0x1800c2df8`
- `0x1800cf080`
- `0x1800d6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c31c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c31c8`
- `KERNEL32!GetFileAttributesExW` at `0x1800c31ba`
- `KERNEL32!GetFileAttributesExW` at `0x1800c31ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PerfDiagBoot::CTraceContext::Open(
        PerfDiagBoot::CTraceContext *this,
        struct XPerfCore::IAddInManager *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 result; // rax
  _QWORD *v7; // rdi
  ATL::CStringData *v8; // rbx
  __int64 v9; // rcx
  DWORD LastError; // esi
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v14; // r8d
  int v15; // r9d
  int v16; // [rsp+50h] [rbp-39h] BYREF
  int v17; // [rsp+54h] [rbp-35h] BYREF
  DWORD v18; // [rsp+58h] [rbp-31h] BYREF
  int v19; // [rsp+5Ch] [rbp-2Dh] BYREF
  __int64 v20; // [rsp+60h] [rbp-29h] BYREF
  __int64 v21; // [rsp+68h] [rbp-21h] BYREF
  _QWORD v22[3]; // [rsp+70h] [rbp-19h] BYREF
  _OWORD FileInformation[2]; // [rsp+88h] [rbp-1h] BYREF
  int v24; // [rsp+A8h] [rbp+1Fh]

  v22[0] = a3;
  v22[1] = a4;
  result = XPerfCore::IAddInManager::CreateSession<XPerfCore::ISession>(
             (__int64)a2,
             2,
             (__int64)v22,
             (__int64)a4,
             (__int64)this);
  if ( (int)result >= 0 )
  {
    v7 = (_QWORD *)((char *)this + 16);
    result = (***(__int64 (__fastcall ****)(_QWORD, GUID *, char *))this)(
               *(_QWORD *)this,
               &GUID_3916f7a8_4ff4_48b5_82a9_e5fb6412e5af,
               (char *)this + 16);
    if ( (int)result >= 0 )
    {
      if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 216LL))(*v7)
        || (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 232LL))(*v7) )
      {
        v8 = (ATL::CStringData *)((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
        v22[2] = (char *)v8 + 24;
        memset(FileInformation, 0, sizeof(FileInformation));
        v24 = 0;
        if ( GetFileAttributesExW(a3, GetFileExInfoStandard, FileInformation) )
        {
          if ( (unsigned int)dword_1800FF858 > 1 && (unsigned __int8)tlgKeywordOn(v9, 0x200000020000LL) )
          {
            v20 = 0x1000000;
            v19 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 232LL))(*v7);
            v18 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 216LL))(*v7);
            v17 = v24;
            v16 = -2058022911;
            v21 = 0x2000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
              (unsigned int)&v21,
              (unsigned int)byte_1800EAC49,
              v14,
              v15,
              (__int64)&v21,
              (__int64)&v16,
              (__int64)&v17,
              (__int64)&v18,
              (__int64)&v19,
              (__int64)&v20);
          }
        }
        else
        {
          LastError = GetLastError();
          if ( (unsigned int)dword_1800FF858 > 1
            && (unsigned __int8)tlgKeywordOn((unsigned int)dword_1800FF858, 0x200000020000LL) )
          {
            v20 = 0x1000000;
            v16 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 232LL))(*v7);
            v17 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 216LL))(*v7);
            v18 = LastError;
            v19 = -2058022911;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
              v11,
              (unsigned int)word_1800EACB2,
              v12,
              v13,
              (__int64)&v19,
              (__int64)&v18,
              (__int64)&v17,
              (__int64)&v16,
              (__int64)&v20);
          }
        }
        ATL::CStringData::Release(v8);
        return 2236944385LL;
      }
      else
      {
        result = (*(__int64 (__fastcall **)(_QWORD, GUID *, GUID *, char *, _DWORD))(**(_QWORD **)this + 32LL))(
                   *(_QWORD *)this,
                   &GUID_23118026_0a24_4a84_9573_01f5a125fcaf,
                   &GUID_23118026_0a24_4a84_9573_01f5a125fcaf,
                   (char *)this + 8,
                   0);
        if ( (int)result >= 0 )
        {
          result = (*(__int64 (__fastcall **)(_QWORD, GUID *, GUID *, char *, _DWORD))(**(_QWORD **)this + 32LL))(
                     *(_QWORD *)this,
                     &GUID_c3fa949e_81e2_4213_b4bb_a503ff5af434,
                     &GUID_c3fa949e_81e2_4213_b4bb_a503ff5af434,
                     (char *)this + 24,
                     0);
          if ( (int)result >= 0 )
          {
            result = (*(__int64 (__fastcall **)(_QWORD, GUID *, GUID *, char *, _DWORD))(**(_QWORD **)this + 32LL))(
                       *(_QWORD *)this,
                       &GUID_3c176e8e_9f53_4559_900a_f68e9f35dcc4,
                       &GUID_3c176e8e_9f53_4559_900a_f68e9f35dcc4,
                       (char *)this + 32,
                       0);
            if ( (int)result >= 0 )
            {
              result = (*(__int64 (__fastcall **)(_QWORD, GUID *, GUID *, char *, _DWORD))(**(_QWORD **)this + 32LL))(
                         *(_QWORD *)this,
                         &GUID_073d04c8_d968_420f_8c03_71088a195868,
                         &GUID_073d04c8_d968_420f_8c03_71088a195868,
                         (char *)this + 40,
                         0);
              if ( (int)result >= 0 )
              {
                result = (*(__int64 (__fastcall **)(_QWORD, GUID *, GUID *, char *, _DWORD))(**(_QWORD **)this + 32LL))(
                           *(_QWORD *)this,
                           &GUID_ad7173cb_b650_4dd6_8f52_0a71f65f7dc7,
                           &GUID_ad7173cb_b650_4dd6_8f52_0a71f65f7dc7,
                           (char *)this + 48,
                           0);
                if ( (int)result >= 0 )
                {
                  result = (*(__int64 (__fastcall **)(_QWORD, GUID *, GUID *, char *, _DWORD))(**(_QWORD **)this + 32LL))(
                             *(_QWORD *)this,
                             &GUID_119a2062_8590_4103_89e2_5e88e4424698,
                             &GUID_119a2062_8590_4103_89e2_5e88e4424698,
                             (char *)this + 56,
                             0);
                  if ( (int)result >= 0 )
                  {
                    result = (*(__int64 (__fastcall **)(_QWORD, GUID *, GUID *, char *, _DWORD))(**(_QWORD **)this + 32LL))(
                               *(_QWORD *)this,
                               &GUID_5ecef1ae_9f5b_4770_a92a_1e65608127d6,
                               &GUID_5ecef1ae_9f5b_4770_a92a_1e65608127d6,
                               (char *)this + 64,
                               0);
                    if ( (int)result >= 0 )
                    {
                      result = (*(__int64 (__fastcall **)(_QWORD, GUID *, GUID *, char *, _DWORD))(**(_QWORD **)this
                                                                                                 + 32LL))(
                                 *(_QWORD *)this,
                                 &GUID_c934394e_728d_4e33_9208_2b01d02399d8,
                                 &GUID_c934394e_728d_4e33_9208_2b01d02399d8,
                                 (char *)this + 72,
                                 0);
                      if ( (int)result >= 0 )
                      {
                        result = (*(__int64 (__fastcall **)(_QWORD, GUID *, GUID *, char *, _DWORD))(**(_QWORD **)this + 32LL))(
                                   *(_QWORD *)this,
                                   &GUID_cee5669c_6509_4cbc_a82d_58438a1f6097,
                                   &GUID_cee5669c_6509_4cbc_a82d_58438a1f6097,
                                   (char *)this + 80,
                                   0);
                        if ( (int)result >= 0 )
                        {
                          result = (*(__int64 (__fastcall **)(_QWORD, GUID *, GUID *, char *, _DWORD))(**(_QWORD **)this + 32LL))(
                                     *(_QWORD *)this,
                                     &GUID_cf3690ce_f820_4ea3_9073_3412042d00ca,
                                     &GUID_cf3690ce_f820_4ea3_9073_3412042d00ca,
                                     (char *)this + 88,
                                     0);
                          if ( (int)result >= 0 )
                          {
                            result = (*(__int64 (__fastcall **)(_QWORD, GUID *, GUID *, char *, _DWORD))(**(_QWORD **)this + 32LL))(
                                       *(_QWORD *)this,
                                       &GUID_3860533e_7a69_458c_bf02_623687ca62a0,
                                       &GUID_3860533e_7a69_458c_bf02_623687ca62a0,
                                       (char *)this + 96,
                                       0);
                            if ( (int)result >= 0 )
                            {
                              result = (*(__int64 (__fastcall **)(_QWORD, GUID *, GUID *, char *, _DWORD))(**(_QWORD **)this + 32LL))(
                                         *(_QWORD *)this,
                                         &GUID_fd7df076_98b8_4a54_9166_1ebb141b7fc3,
                                         &GUID_fd7df076_98b8_4a54_9166_1ebb141b7fc3,
                                         (char *)this + 104,
                                         0);
                              if ( (int)result >= 0 )
                              {
                                result = (*(__int64 (__fastcall **)(_QWORD, GUID *, GUID *, char *, _DWORD))(**(_QWORD **)this + 32LL))(
                                           *(_QWORD *)this,
                                           &GUID_17de2555_dfa8_4df4_b428_e92a8492d4b1,
                                           &GUID_17de2555_dfa8_4df4_b428_e92a8492d4b1,
                                           (char *)this + 112,
                                           0);
                                if ( (int)result >= 0 )
                                {
                                  result = (*(__int64 (__fastcall **)(_QWORD, GUID *, GUID *, char *, _DWORD))(**(_QWORD **)this + 32LL))(
                                             *(_QWORD *)this,
                                             &GUID_b46e5b1c_5a57_4fe5_a7d8_08e14c399cd0,
                                             &GUID_b46e5b1c_5a57_4fe5_a7d8_08e14c399cd0,
                                             (char *)this + 120,
                                             0);
                                  if ( (int)result >= 0 )
                                  {
                                    result = (*(__int64 (__fastcall **)(_QWORD, GUID *, GUID *, char *, _DWORD))(**(_QWORD **)this + 32LL))(
                                               *(_QWORD *)this,
                                               &GUID_28851485_57f1_43c8_a704_a4c58082f7f5,
                                               &GUID_28851485_57f1_43c8_a704_a4c58082f7f5,
                                               (char *)this + 128,
                                               0);
                                    if ( (int)result >= 0 )
                                    {
                                      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetImpl'::`2'::impl)
                                        || (result = (*(__int64 (__fastcall **)(_QWORD, GUID *, GUID *, char *, _DWORD))(**(_QWORD **)this + 32LL))(
                                                       *(_QWORD *)this,
                                                       &GUID_2a6ec536_5679_48ee_b733_d8e9c2e58311,
                                                       &GUID_2a6ec536_5679_48ee_b733_d8e9c2e58311,
                                                       (char *)this + 136,
                                                       0),
                                            (int)result >= 0) )
                                      {
                                        result = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)this + 48LL))(
                                                   *(_QWORD *)this,
                                                   0);
                                        if ( (int)result >= 0 )
                                          return PerfDiagBoot::CTraceContext::IsCommonDataAvailable(this);
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800c2df8  push    rbp
0x1800c2dfa  push    rbx
0x1800c2dfb  push    rsi
0x1800c2dfc  push    rdi
0x1800c2dfd  push    r14
0x1800c2dff  lea     rbp, [rsp-37h]
0x1800c2e04  sub     rsp, 0C0h
0x1800c2e0b  mov     rax, cs:__security_cookie
0x1800c2e12  xor     rax, rsp
0x1800c2e15  mov     [rbp+57h+var_30], rax
0x1800c2e19  mov     rsi, r8
0x1800c2e1c  mov     rax, rdx
0x1800c2e1f  mov     rbx, rcx
0x1800c2e22  mov     [rbp+57h+var_70], r8
0x1800c2e26  mov     [rbp+57h+var_68], r9
0x1800c2e2a  mov     [rsp+0E0h+var_C0], rcx
0x1800c2e2f  lea     r8, [rbp+57h+var_70]
0x1800c2e33  mov     edx, 2
0x1800c2e38  mov     rcx, rax
0x1800c2e3b  call    ??$CreateSession@UISession@XPerfCore@@@IAddInManager@XPerfCore@@QEAAJ_KQEBQEBGKPEAPEAUISession@1@@Z; XPerfCore::IAddInManager::CreateSession<XPerfCore::ISession>(unsigned __int64,ushort const * const * const,ulong,XPerfCore::ISession * *)
0x1800c2e40  xor     r14d, r14d
0x1800c2e43  test    eax, eax
0x1800c2e45  js      loc_1800C332D
0x1800c2e4b  mov     rcx, [rbx]
0x1800c2e4e  lea     rdi, [rbx+10h]
0x1800c2e52  mov     rax, [rcx]
0x1800c2e55  mov     r8, rdi
0x1800c2e58  lea     rdx, _GUID_3916f7a8_4ff4_48b5_82a9_e5fb6412e5af
0x1800c2e5f  mov     rax, [rax]
0x1800c2e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2e67  test    eax, eax
0x1800c2e69  js      loc_1800C332D
0x1800c2e6f  mov     rcx, [rdi]
0x1800c2e72  mov     rax, [rcx]
0x1800c2e75  mov     rax, [rax+0D8h]
0x1800c2e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2e81  test    eax, eax
0x1800c2e83  jnz     loc_1800C317F
0x1800c2e89  mov     rcx, [rdi]
0x1800c2e8c  mov     rax, [rcx]
0x1800c2e8f  mov     rax, [rax+0E8h]
0x1800c2e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2e9b  test    eax, eax
0x1800c2e9d  jnz     loc_1800C317F
0x1800c2ea3  mov     rcx, [rbx]
0x1800c2ea6  mov     rax, [rcx]
0x1800c2ea9  lea     r9, [rbx+8]
0x1800c2ead  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x1800c2eb2  lea     rdx, _GUID_23118026_0a24_4a84_9573_01f5a125fcaf
0x1800c2eb9  mov     r8, rdx
0x1800c2ebc  mov     rax, [rax+20h]
0x1800c2ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2ec5  test    eax, eax
0x1800c2ec7  js      loc_1800C332D
0x1800c2ecd  mov     rcx, [rbx]
0x1800c2ed0  mov     rax, [rcx]
0x1800c2ed3  lea     r9, [rbx+18h]
0x1800c2ed7  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x1800c2edc  lea     rdx, _GUID_c3fa949e_81e2_4213_b4bb_a503ff5af434
0x1800c2ee3  mov     r8, rdx
0x1800c2ee6  mov     rax, [rax+20h]
0x1800c2eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2eef  test    eax, eax
0x1800c2ef1  js      loc_1800C332D
0x1800c2ef7  mov     rcx, [rbx]
0x1800c2efa  mov     rax, [rcx]
0x1800c2efd  lea     r9, [rbx+20h]
0x1800c2f01  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x1800c2f06  lea     rdx, _GUID_3c176e8e_9f53_4559_900a_f68e9f35dcc4
0x1800c2f0d  mov     r8, rdx
0x1800c2f10  mov     rax, [rax+20h]
0x1800c2f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2f19  test    eax, eax
0x1800c2f1b  js      loc_1800C332D
0x1800c2f21  mov     rcx, [rbx]
0x1800c2f24  mov     rax, [rcx]
0x1800c2f27  lea     r9, [rbx+28h]
0x1800c2f2b  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x1800c2f30  lea     rdx, _GUID_073d04c8_d968_420f_8c03_71088a195868
0x1800c2f37  mov     r8, rdx
0x1800c2f3a  mov     rax, [rax+20h]
0x1800c2f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2f43  test    eax, eax
0x1800c2f45  js      loc_1800C332D
0x1800c2f4b  mov     rcx, [rbx]
0x1800c2f4e  mov     rax, [rcx]
0x1800c2f51  lea     r9, [rbx+30h]
0x1800c2f55  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x1800c2f5a  lea     rdx, _GUID_ad7173cb_b650_4dd6_8f52_0a71f65f7dc7
0x1800c2f61  mov     r8, rdx
0x1800c2f64  mov     rax, [rax+20h]
0x1800c2f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2f6d  test    eax, eax
0x1800c2f6f  js      loc_1800C332D
0x1800c2f75  mov     rcx, [rbx]
0x1800c2f78  mov     rax, [rcx]
0x1800c2f7b  lea     r9, [rbx+38h]
0x1800c2f7f  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x1800c2f84  lea     rdx, _GUID_119a2062_8590_4103_89e2_5e88e4424698
0x1800c2f8b  mov     r8, rdx
0x1800c2f8e  mov     rax, [rax+20h]
0x1800c2f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2f97  test    eax, eax
0x1800c2f99  js      loc_1800C332D
0x1800c2f9f  mov     rcx, [rbx]
0x1800c2fa2  mov     rax, [rcx]
0x1800c2fa5  lea     r9, [rbx+40h]
0x1800c2fa9  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x1800c2fae  lea     rdx, _GUID_5ecef1ae_9f5b_4770_a92a_1e65608127d6
0x1800c2fb5  mov     r8, rdx
0x1800c2fb8  mov     rax, [rax+20h]
0x1800c2fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2fc1  test    eax, eax
0x1800c2fc3  js      loc_1800C332D
0x1800c2fc9  mov     rcx, [rbx]
0x1800c2fcc  mov     rax, [rcx]
0x1800c2fcf  lea     r9, [rbx+48h]
0x1800c2fd3  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x1800c2fd8  lea     rdx, _GUID_c934394e_728d_4e33_9208_2b01d02399d8
0x1800c2fdf  mov     r8, rdx
0x1800c2fe2  mov     rax, [rax+20h]
0x1800c2fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2feb  test    eax, eax
0x1800c2fed  js      loc_1800C332D
0x1800c2ff3  mov     rcx, [rbx]
0x1800c2ff6  mov     rax, [rcx]
0x1800c2ff9  lea     r9, [rbx+50h]
0x1800c2ffd  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x1800c3002  lea     rdx, _GUID_cee5669c_6509_4cbc_a82d_58438a1f6097
0x1800c3009  mov     r8, rdx
0x1800c300c  mov     rax, [rax+20h]
0x1800c3010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3015  test    eax, eax
0x1800c3017  js      loc_1800C332D
0x1800c301d  mov     rcx, [rbx]
0x1800c3020  mov     rax, [rcx]
0x1800c3023  lea     r9, [rbx+58h]
0x1800c3027  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x1800c302c  lea     rdx, _GUID_cf3690ce_f820_4ea3_9073_3412042d00ca
0x1800c3033  mov     r8, rdx
0x1800c3036  mov     rax, [rax+20h]
0x1800c303a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c303f  test    eax, eax
0x1800c3041  js      loc_1800C332D
0x1800c3047  mov     rcx, [rbx]
0x1800c304a  mov     rax, [rcx]
0x1800c304d  lea     r9, [rbx+60h]
0x1800c3051  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x1800c3056  lea     rdx, _GUID_3860533e_7a69_458c_bf02_623687ca62a0
0x1800c305d  mov     r8, rdx
0x1800c3060  mov     rax, [rax+20h]
0x1800c3064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3069  test    eax, eax
0x1800c306b  js      loc_1800C332D
0x1800c3071  mov     rcx, [rbx]
0x1800c3074  mov     rax, [rcx]
0x1800c3077  lea     r9, [rbx+68h]
0x1800c307b  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x1800c3080  lea     rdx, _GUID_fd7df076_98b8_4a54_9166_1ebb141b7fc3
0x1800c3087  mov     r8, rdx
0x1800c308a  mov     rax, [rax+20h]
0x1800c308e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3093  test    eax, eax
0x1800c3095  js      loc_1800C332D
0x1800c309b  mov     rcx, [rbx]
0x1800c309e  mov     rax, [rcx]
0x1800c30a1  lea     r9, [rbx+70h]
0x1800c30a5  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x1800c30aa  lea     rdx, _GUID_17de2555_dfa8_4df4_b428_e92a8492d4b1
0x1800c30b1  mov     r8, rdx
0x1800c30b4  mov     rax, [rax+20h]
0x1800c30b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c30bd  test    eax, eax
0x1800c30bf  js      loc_1800C332D
0x1800c30c5  mov     rcx, [rbx]
0x1800c30c8  mov     rax, [rcx]
0x1800c30cb  lea     r9, [rbx+78h]
0x1800c30cf  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x1800c30d4  lea     rdx, _GUID_b46e5b1c_5a57_4fe5_a7d8_08e14c399cd0
0x1800c30db  mov     r8, rdx
0x1800c30de  mov     rax, [rax+20h]
0x1800c30e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c30e7  test    eax, eax
0x1800c30e9  js      loc_1800C332D
0x1800c30ef  mov     rcx, [rbx]
0x1800c30f2  mov     rax, [rcx]
0x1800c30f5  lea     r9, [rbx+80h]
0x1800c30fc  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x1800c3101  lea     rdx, _GUID_28851485_57f1_43c8_a704_a4c58082f7f5
0x1800c3108  mov     r8, rdx
0x1800c310b  mov     rax, [rax+20h]
0x1800c310f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3114  test    eax, eax
0x1800c3116  js      loc_1800C332D
0x1800c311c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace> `wil::Feature<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::GetImpl(void)'::`2'::impl
0x1800c3123  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AddMemInfoToBootTrace@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddMemInfoToBootTrace>::__private_IsEnabled(void)
0x1800c3128  test    al, al
0x1800c312a  jz      short loc_1800C3159
0x1800c312c  mov     rcx, [rbx]
0x1800c312f  mov     rax, [rcx]
0x1800c3132  lea     r9, [rbx+88h]
0x1800c3139  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x1800c313e  lea     rdx, _GUID_2a6ec536_5679_48ee_b733_d8e9c2e58311
0x1800c3145  mov     r8, rdx
0x1800c3148  mov     rax, [rax+20h]
0x1800c314c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3151  test    eax, eax
0x1800c3153  js      loc_1800C332D
0x1800c3159  mov     rcx, [rbx]
0x1800c315c  mov     rax, [rcx]
0x1800c315f  xor     edx, edx
0x1800c3161  mov     rax, [rax+30h]
0x1800c3165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c316a  test    eax, eax
0x1800c316c  js      loc_1800C332D
0x1800c3172  mov     rcx, rbx; this
0x1800c3175  call    ?IsCommonDataAvailable@CTraceContext@PerfDiagBoot@@QEBAJXZ; PerfDiagBoot::CTraceContext::IsCommonDataAvailable(void)
0x1800c317a  jmp     loc_1800C332D
0x1800c317f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800c3186  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800c318d  mov     rax, [rax+18h]
0x1800c3191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3196  mov     rbx, rax
0x1800c3199  lea     rdx, [rax+18h]
0x1800c319d  mov     [rbp+57h+var_60], rdx
0x1800c31a1  xorps   xmm0, xmm0
0x1800c31a4  xor     eax, eax
0x1800c31a6  movups  [rbp+57h+FileInformation], xmm0
0x1800c31aa  movups  [rbp+57h+var_48], xmm0
0x1800c31ae  mov     [rbp+57h+var_38], eax
0x1800c31b1  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x1800c31b5  xor     edx, edx; fInfoLevelId
0x1800c31b7  mov     rcx, rsi; lpFileName
0x1800c31ba  call    cs:__imp_GetFileAttributesExW
0x1800c31c0  test    eax, eax
0x1800c31c2  jnz     loc_1800C3270
0x1800c31c8  call    cs:__imp_GetLastError
0x1800c31ce  mov     esi, eax
0x1800c31d0  mov     ecx, cs:dword_1800FF858
0x1800c31d6  cmp     ecx, 1
0x1800c31d9  jbe     loc_1800C3320
0x1800c31df  mov     rdx, 200000020000h
0x1800c31e9  call    _tlgKeywordOn
0x1800c31ee  test    al, al
0x1800c31f0  jz      loc_1800C3320
0x1800c31f6  mov     [rbp+57h+var_80], 1000000h
0x1800c31fe  mov     rcx, [rdi]
0x1800c3201  mov     rax, [rcx]
0x1800c3204  mov     rax, [rax+0E8h]
0x1800c320b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3210  mov     [rbp+57h+var_90], eax
0x1800c3213  mov     rcx, [rdi]
0x1800c3216  mov     rax, [rcx]
0x1800c3219  mov     rax, [rax+0D8h]
0x1800c3220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3225  mov     [rbp+57h+var_8C], eax
0x1800c3228  mov     [rbp+57h+var_88], esi
0x1800c322b  mov     [rbp+57h+var_84], 85551001h
0x1800c3232  lea     rax, [rbp+57h+var_80]
0x1800c3236  mov     [rsp+0E0h+var_A0], rax
0x1800c323b  lea     rax, [rbp+57h+var_90]
0x1800c323f  mov     [rsp+0E0h+var_A8], rax
0x1800c3244  lea     rax, [rbp+57h+var_8C]
0x1800c3248  mov     [rsp+0E0h+var_B0], rax
0x1800c324d  lea     rax, [rbp+57h+var_88]
0x1800c3251  mov     [rsp+0E0h+var_B8], rax
0x1800c3256  lea     rax, [rbp+57h+var_84]
0x1800c325a  mov     [rsp+0E0h+var_C0], rax
0x1800c325f  lea     rdx, word_1800EACB2
0x1800c3266  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800c326b  jmp     loc_1800C3320
0x1800c3270  mov     eax, cs:dword_1800FF858
0x1800c3276  cmp     eax, 1
0x1800c3279  jbe     loc_1800C3320
0x1800c327f  mov     rdx, 200000020000h
0x1800c3289  call    _tlgKeywordOn
0x1800c328e  test    al, al
0x1800c3290  jz      loc_1800C3320
0x1800c3296  mov     [rbp+57h+var_80], 1000000h
0x1800c329e  mov     rcx, [rdi]
0x1800c32a1  mov     rax, [rcx]
0x1800c32a4  mov     rax, [rax+0E8h]
0x1800c32ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c32b0  mov     [rbp+57h+var_84], eax
0x1800c32b3  mov     rcx, [rdi]
0x1800c32b6  mov     rax, [rcx]
0x1800c32b9  mov     rax, [rax+0D8h]
0x1800c32c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c32c5  mov     [rbp+57h+var_88], eax
0x1800c32c8  mov     eax, [rbp+57h+var_38]
0x1800c32cb  mov     [rbp+57h+var_8C], eax
0x1800c32ce  mov     [rbp+57h+var_90], 85551001h
0x1800c32d5  mov     [rbp+57h+var_78], 2000000h
0x1800c32dd  lea     rax, [rbp+57h+var_80]
0x1800c32e1  mov     [rsp+0E0h+var_98], rax
0x1800c32e6  lea     rax, [rbp+57h+var_84]
0x1800c32ea  mov     [rsp+0E0h+var_A0], rax
0x1800c32ef  lea     rax, [rbp+57h+var_88]
0x1800c32f3  mov     [rsp+0E0h+var_A8], rax
0x1800c32f8  lea     rcx, [rbp+57h+var_8C]
  ... truncated ...
```
