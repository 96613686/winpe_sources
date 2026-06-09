# ConvertFaultToHResult(ushort const *,ushort const *)

- ea: `0x18002ec6c`
- end: `0x18002f045`
- name: `?ConvertFaultToHResult@@YAJPEBG0@Z`
- size: `985`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180029ac4`

## callees

- `0x180002ae0`
- `0x1800141b0`
- `0x1800194e0`
- `0x18001e0b0`
- `0x180027e74`
- `0x18002ec6c`
- `0x180030804`

## string_xrefs

- `0x18002ee51`: `InternalServiceFault`
- `0x18002ee83`: `InvalidSecurity`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ConvertFaultToHResult(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  __int64 v4; // r8
  __int64 v5; // r8
  __int64 v7; // rcx
  unsigned int v8; // r8d
  _QWORD v9[2]; // [rsp+40h] [rbp-19h] BYREF
  void *v10[2]; // [rsp+50h] [rbp-9h] BYREF
  _WORD v11[8]; // [rsp+60h] [rbp+7h] BYREF
  void *Block[2]; // [rsp+70h] [rbp+17h] BYREF
  _WORD v13[24]; // [rsp+80h] [rbp+27h] BYREF
  int v14; // [rsp+C0h] [rbp+67h] BYREF
  int v15; // [rsp+D0h] [rbp+77h] BYREF
  __int16 v16; // [rsp+D4h] [rbp+7Bh]
  __int64 v17; // [rsp+D8h] [rbp+7Fh] BYREF

  v3 = -2145910776;
  v14 = -2145910776;
  v10[0] = v11;
  v10[1] = v11;
  v11[0] = 0;
  Block[0] = v13;
  Block[1] = v13;
  v13[0] = 0;
  v9[0] = "ConvertFaultToHResult";
  v9[1] = &v14;
  if ( a1 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a1[v4] );
  }
  else
  {
    v4 = 0;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v10,
                           a1,
                           v4) )
    goto LABEL_11;
  if ( !a2 )
    goto LABEL_17;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                          Block,
                          a2,
                          v5) )
  {
LABEL_17:
    if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find(
           v10,
           L"NotEligibleToRenew") == -1
      && utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find(
           Block,
           L"NotEligibleToRenew") == -1 )
    {
      if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find(
             v10,
             L"MessageFormat") == -1 )
      {
        if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find(
               v10,
               L"Authentication") == -1
          && utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find(
               v10,
               L"FailedAuthentication") == -1 )
        {
          if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find(
                 v10,
                 L"Authorization") == -1 )
          {
            if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find(
                   v10,
                   L"CertificateRequest") == -1
              && utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find(
                   v10,
                   L"CertificateAuthority") == -1 )
            {
              if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find(
                     v10,
                     L"EnrollmentServer") == -1 )
              {
                if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find(
                       v10,
                       L"InternalServiceFault") == -1
                  && utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find(
                       v10,
                       L"InternalServerFault") == -1 )
                {
                  if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find(
                         v10,
                         L"InvalidSecurity") == -1 )
                  {
                    if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find(
                           v10,
                           L"DeviceCapReached") == -1 )
                    {
                      if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find(
                             v10,
                             L"DeviceNotSupported") == -1 )
                      {
                        if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find(
                               v10,
                               L"NotSupported") == -1 )
                        {
                          if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find(
                                 v10,
                                 L"InMaintenance") == -1 )
                          {
                            if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find(
                                   v10,
                                   L"UserLicense") == -1 )
                            {
                              if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find(
                                     v10,
                                     L"InvalidEnrollmentData") == -1 )
                              {
                                v8 = *(_DWORD *)Feature_CustomServerError__descriptor;
                                if ( (*(_DWORD *)Feature_CustomServerError__descriptor & 4) == 0 )
                                {
                                  v17 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomServerError>::GetCachedFeatureEnabledState(
                                                     v7,
                                                     &v17);
                                  v8 = v17;
                                }
                                v15 = 0;
                                v16 = 3;
                                wil::details::ReportUsageToService(
                                  &qword_180070DF0,
                                  43044814,
                                  (v8 >> 10) & 1,
                                  (v8 >> 11) & 1,
                                  &v15,
                                  1);
                                if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find(
                                       v10,
                                       L"CustomServerError") != -1 )
                                  v3 = -2145910734;
                              }
                              else
                              {
                                v3 = -2145910759;
                              }
                            }
                            else
                            {
                              v3 = -2145910760;
                            }
                          }
                          else
                          {
                            v3 = -2145910761;
                          }
                        }
                        else
                        {
                          v3 = -2145910763;
                        }
                      }
                      else
                      {
                        v3 = -2145910764;
                      }
                    }
                    else
                    {
                      v3 = -2145910765;
                    }
                  }
                  else
                  {
                    v3 = -2145910777;
                  }
                }
                else
                {
                  v3 = -2145910778;
                }
              }
              else
              {
                v3 = -2145910779;
              }
            }
            else
            {
              v3 = -2145910780;
            }
          }
          else
          {
            v3 = -2145910781;
          }
        }
        else
        {
          v3 = -2145910782;
        }
      }
      else
      {
        v3 = -2145910783;
      }
    }
    else
    {
      v3 = -2145910762;
    }
    v14 = v3;
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v9);
    if ( Block[0] != v13 )
      operator delete(Block[0]);
    if ( v10[0] != v11 )
      operator delete(v10[0]);
    return v3;
  }
  else
  {
LABEL_11:
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v9);
    if ( Block[0] != v13 )
      operator delete(Block[0]);
    if ( v10[0] != v11 )
      operator delete(v10[0]);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18002ec6c  push    rbp
0x18002ec6e  push    rbx
0x18002ec6f  push    rsi
0x18002ec70  push    rdi
0x18002ec71  push    r14
0x18002ec73  lea     rbp, [rsp-37h]
0x18002ec78  sub     rsp, 90h
0x18002ec7f  mov     rdi, rdx
0x18002ec82  mov     ebx, 80180008h
0x18002ec87  mov     [rbp+57h+arg_0], ebx
0x18002ec8a  lea     rax, [rbp+57h+var_50]
0x18002ec8e  mov     [rbp+57h+var_60], rax
0x18002ec92  lea     rax, [rbp+57h+var_50]
0x18002ec96  mov     [rbp+57h+var_58], rax
0x18002ec9a  xor     r14d, r14d
0x18002ec9d  mov     [rbp+57h+var_50], r14w
0x18002eca2  lea     rax, [rbp+57h+var_30]
0x18002eca6  mov     [rbp+57h+Block], rax
0x18002ecaa  lea     rax, [rbp+57h+var_30]
0x18002ecae  mov     [rbp+57h+var_38], rax
0x18002ecb2  mov     [rbp+57h+var_30], r14w
0x18002ecb7  lea     rax, aConvertfaultto; "ConvertFaultToHResult"
0x18002ecbe  mov     [rbp+57h+var_70], rax
0x18002ecc2  lea     rax, [rbp+57h+arg_0]
0x18002ecc6  mov     [rbp+57h+var_68], rax
0x18002ecca  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002ecce  test    rcx, rcx
0x18002ecd1  jz      short loc_18002ECE2
0x18002ecd3  mov     r8, rsi
0x18002ecd6  inc     r8
0x18002ecd9  cmp     [rcx+r8*2], r14w
0x18002ecde  jnz     short loc_18002ECD6
0x18002ece0  jmp     short loc_18002ECE5
0x18002ece2  mov     r8, r14
0x18002ece5  mov     rdx, rcx
0x18002ece8  lea     rcx, [rbp+57h+var_60]
0x18002ecec  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18002ecf1  test    al, al
0x18002ecf3  jz      short loc_18002ED17
0x18002ecf5  test    rdi, rdi
0x18002ecf8  jz      short loc_18002ED5E
0x18002ecfa  mov     r8, rsi
0x18002ecfd  inc     r8
0x18002ed00  cmp     [rdi+r8*2], r14w
0x18002ed05  jnz     short loc_18002ECFD
0x18002ed07  mov     rdx, rdi
0x18002ed0a  lea     rcx, [rbp+57h+Block]
0x18002ed0e  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18002ed13  test    al, al
0x18002ed15  jnz     short loc_18002ED5E
0x18002ed17  lea     rcx, [rbp+57h+var_70]; this
0x18002ed1b  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18002ed20  nop
0x18002ed21  lea     rax, [rbp+57h+var_30]
0x18002ed25  mov     rcx, [rbp+57h+Block]; Block
0x18002ed29  cmp     rcx, rax
0x18002ed2c  jz      short loc_18002ED3B
0x18002ed2e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002ed35  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002ed3a  nop
0x18002ed3b  lea     rax, [rbp+57h+var_50]
0x18002ed3f  mov     rcx, [rbp+57h+var_60]; Block
0x18002ed43  cmp     rcx, rax
0x18002ed46  jz      short loc_18002ED54
0x18002ed48  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002ed4f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002ed54  mov     eax, 8007000Eh
0x18002ed59  jmp     loc_18002F036
0x18002ed5e  lea     rdx, aNoteligibletor; "NotEligibleToRenew"
0x18002ed65  lea     rcx, [rbp+57h+var_60]
0x18002ed69  call    ?find@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::find(ushort const *,unsigned __int64)
0x18002ed6e  cmp     rax, rsi
0x18002ed71  jnz     loc_18002EFEF
0x18002ed77  lea     rdx, aNoteligibletor; "NotEligibleToRenew"
0x18002ed7e  lea     rcx, [rbp+57h+Block]
0x18002ed82  call    ?find@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::find(ushort const *,unsigned __int64)
0x18002ed87  cmp     rax, rsi
0x18002ed8a  jnz     loc_18002EFEF
0x18002ed90  lea     rdx, aMessageformat; "MessageFormat"
0x18002ed97  lea     rcx, [rbp+57h+var_60]
0x18002ed9b  call    ?find@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::find(ushort const *,unsigned __int64)
0x18002eda0  cmp     rax, rsi
0x18002eda3  jz      short loc_18002EDAF
0x18002eda5  mov     ebx, 80180001h
0x18002edaa  jmp     loc_18002EFF4
0x18002edaf  lea     rdx, aAuthentication; "Authentication"
0x18002edb6  lea     rcx, [rbp+57h+var_60]
0x18002edba  call    ?find@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::find(ushort const *,unsigned __int64)
0x18002edbf  cmp     rax, rsi
0x18002edc2  jnz     loc_18002EFE8
0x18002edc8  lea     rdx, aFailedauthenti; "FailedAuthentication"
0x18002edcf  lea     rcx, [rbp+57h+var_60]
0x18002edd3  call    ?find@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::find(ushort const *,unsigned __int64)
0x18002edd8  cmp     rax, rsi
0x18002eddb  jnz     loc_18002EFE8
0x18002ede1  lea     rdx, aAuthorization; "Authorization"
0x18002ede8  lea     rcx, [rbp+57h+var_60]
0x18002edec  call    ?find@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::find(ushort const *,unsigned __int64)
0x18002edf1  cmp     rax, rsi
0x18002edf4  jz      short loc_18002EE00
0x18002edf6  mov     ebx, 80180003h
0x18002edfb  jmp     loc_18002EFF4
0x18002ee00  lea     rdx, aCertificatereq; "CertificateRequest"
0x18002ee07  lea     rcx, [rbp+57h+var_60]
0x18002ee0b  call    ?find@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::find(ushort const *,unsigned __int64)
0x18002ee10  cmp     rax, rsi
0x18002ee13  jnz     loc_18002EFE1
0x18002ee19  lea     rdx, aCertificateaut; "CertificateAuthority"
0x18002ee20  lea     rcx, [rbp+57h+var_60]
0x18002ee24  call    ?find@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::find(ushort const *,unsigned __int64)
0x18002ee29  cmp     rax, rsi
0x18002ee2c  jnz     loc_18002EFE1
0x18002ee32  lea     rdx, aEnrollmentserv_0; "EnrollmentServer"
0x18002ee39  lea     rcx, [rbp+57h+var_60]
0x18002ee3d  call    ?find@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::find(ushort const *,unsigned __int64)
0x18002ee42  cmp     rax, rsi
0x18002ee45  jz      short loc_18002EE51
0x18002ee47  mov     ebx, 80180005h
0x18002ee4c  jmp     loc_18002EFF4
0x18002ee51  lea     rdx, aInternalservic; "InternalServiceFault"
0x18002ee58  lea     rcx, [rbp+57h+var_60]
0x18002ee5c  call    ?find@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::find(ushort const *,unsigned __int64)
0x18002ee61  cmp     rax, rsi
0x18002ee64  jnz     loc_18002EFDA
0x18002ee6a  lea     rdx, aInternalserver; "InternalServerFault"
0x18002ee71  lea     rcx, [rbp+57h+var_60]
0x18002ee75  call    ?find@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::find(ushort const *,unsigned __int64)
0x18002ee7a  cmp     rax, rsi
0x18002ee7d  jnz     loc_18002EFDA
0x18002ee83  lea     rdx, aInvalidsecurit; "InvalidSecurity"
0x18002ee8a  lea     rcx, [rbp+57h+var_60]
0x18002ee8e  call    ?find@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::find(ushort const *,unsigned __int64)
0x18002ee93  cmp     rax, rsi
0x18002ee96  jz      short loc_18002EEA2
0x18002ee98  mov     ebx, 80180007h
0x18002ee9d  jmp     loc_18002EFF4
0x18002eea2  lea     rdx, aDevicecapreach; "DeviceCapReached"
0x18002eea9  lea     rcx, [rbp+57h+var_60]
0x18002eead  call    ?find@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::find(ushort const *,unsigned __int64)
0x18002eeb2  cmp     rax, rsi
0x18002eeb5  jz      short loc_18002EEC1
0x18002eeb7  mov     ebx, 80180013h
0x18002eebc  jmp     loc_18002EFF4
0x18002eec1  lea     rdx, aDevicenotsuppo; "DeviceNotSupported"
0x18002eec8  lea     rcx, [rbp+57h+var_60]
0x18002eecc  call    ?find@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::find(ushort const *,unsigned __int64)
0x18002eed1  cmp     rax, rsi
0x18002eed4  jz      short loc_18002EEE0
0x18002eed6  mov     ebx, 80180014h
0x18002eedb  jmp     loc_18002EFF4
0x18002eee0  lea     rdx, aNotsupported; "NotSupported"
0x18002eee7  lea     rcx, [rbp+57h+var_60]
0x18002eeeb  call    ?find@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::find(ushort const *,unsigned __int64)
0x18002eef0  cmp     rax, rsi
0x18002eef3  jz      short loc_18002EEFF
0x18002eef5  mov     ebx, 80180015h
0x18002eefa  jmp     loc_18002EFF4
0x18002eeff  lea     rdx, aInmaintenance; "InMaintenance"
0x18002ef06  lea     rcx, [rbp+57h+var_60]
0x18002ef0a  call    ?find@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::find(ushort const *,unsigned __int64)
0x18002ef0f  cmp     rax, rsi
0x18002ef12  jz      short loc_18002EF1E
0x18002ef14  mov     ebx, 80180017h
0x18002ef19  jmp     loc_18002EFF4
0x18002ef1e  lea     rdx, aUserlicense; "UserLicense"
0x18002ef25  lea     rcx, [rbp+57h+var_60]
0x18002ef29  call    ?find@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::find(ushort const *,unsigned __int64)
0x18002ef2e  cmp     rax, rsi
0x18002ef31  jz      short loc_18002EF3D
0x18002ef33  mov     ebx, 80180018h
0x18002ef38  jmp     loc_18002EFF4
0x18002ef3d  lea     rdx, aInvalidenrollm; "InvalidEnrollmentData"
0x18002ef44  lea     rcx, [rbp+57h+var_60]
0x18002ef48  call    ?find@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::find(ushort const *,unsigned __int64)
0x18002ef4d  cmp     rax, rsi
0x18002ef50  jz      short loc_18002EF5C
0x18002ef52  mov     ebx, 80180019h
0x18002ef57  jmp     loc_18002EFF4
0x18002ef5c  mov     rax, cs:Feature_CustomServerError__descriptor
0x18002ef63  mov     r8d, [rax]
0x18002ef66  test    r8b, 4
0x18002ef6a  jnz     short loc_18002EF7F
0x18002ef6c  lea     rdx, [rbp+57h+arg_18]
0x18002ef70  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CustomServerError@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomServerError>::GetCachedFeatureEnabledState(void)
0x18002ef75  mov     rcx, [rax]
0x18002ef78  mov     [rbp+57h+arg_18], rcx
0x18002ef7c  mov     r8d, ecx
0x18002ef7f  mov     [rbp+57h+arg_10], r14d
0x18002ef83  mov     [rbp+57h+arg_14], 3
0x18002ef89  mov     r9d, r8d
0x18002ef8c  shr     r9d, 0Bh
0x18002ef90  and     r9d, 1
0x18002ef94  shr     r8d, 0Ah
0x18002ef98  and     r8d, 1
0x18002ef9c  mov     [rsp+0B0h+var_88], 1
0x18002efa4  lea     rax, [rbp+57h+arg_10]
0x18002efa8  mov     [rsp+0B0h+var_90], rax
0x18002efad  mov     edx, 290CFCEh
0x18002efb2  lea     rcx, qword_180070DF0
0x18002efb9  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18002efbe  lea     rdx, aCustomserverer; "CustomServerError"
0x18002efc5  lea     rcx, [rbp+57h+var_60]
0x18002efc9  call    ?find@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::find(ushort const *,unsigned __int64)
0x18002efce  cmp     rax, rsi
0x18002efd1  jz      short loc_18002EFF4
0x18002efd3  mov     ebx, 80180032h
0x18002efd8  jmp     short loc_18002EFF4
0x18002efda  mov     ebx, 80180006h
0x18002efdf  jmp     short loc_18002EFF4
0x18002efe1  mov     ebx, 80180004h
0x18002efe6  jmp     short loc_18002EFF4
0x18002efe8  mov     ebx, 80180002h
0x18002efed  jmp     short loc_18002EFF4
0x18002efef  mov     ebx, 80180016h
0x18002eff4  mov     [rbp+57h+arg_0], ebx
0x18002eff7  lea     rcx, [rbp+57h+var_70]; this
0x18002effb  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18002f000  nop
0x18002f001  lea     rax, [rbp+57h+var_30]
0x18002f005  mov     rcx, [rbp+57h+Block]; Block
0x18002f009  cmp     rcx, rax
0x18002f00c  jz      short loc_18002F01B
0x18002f00e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002f015  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002f01a  nop
0x18002f01b  lea     rax, [rbp+57h+var_50]
0x18002f01f  mov     rcx, [rbp+57h+var_60]; Block
0x18002f023  cmp     rcx, rax
0x18002f026  jz      short loc_18002F034
0x18002f028  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002f02f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002f034  mov     eax, ebx
0x18002f036  add     rsp, 90h
0x18002f03d  pop     r14
0x18002f03f  pop     rdi
0x18002f040  pop     rsi
0x18002f041  pop     rbx
0x18002f042  pop     rbp
0x18002f043  retn
```
