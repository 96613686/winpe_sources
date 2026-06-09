# MapsBackgroundTransferJob::SetUserProxySettings(void)

- ea: `0x18000ef18`
- end: `0x18000f301`
- name: `?SetUserProxySettings@MapsBackgroundTransferJob@@AEAAJXZ`
- size: `1001`
- prototype: `__int64 __fastcall(MapsBackgroundTransferJob *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000bb70`

## callees

- `0x180001e70`
- `0x1800028e8`
- `0x1800033d4`
- `0x180008d3c`
- `0x18000ada8`
- `0x18000cd7c`
- `0x18000eae0`
- `0x18000ee60`
- `0x18000ef18`
- `0x18001074c`
- `0x180010954`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f1df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f1df`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000f1cb`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000f1cb`
- `ZTrace_Maps!ZTraceHelper` at `0x18000f21d`
- `ZTrace_Maps!ZTraceHelper` at `0x18000f2b2`
- `ZTrace_Maps!ZTraceHelper` at `0x18000f21d`
- `ZTrace_Maps!ZTraceHelper` at `0x18000f2b2`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000ef95`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000f182`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000f24e`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000ef95`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000f182`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000f24e`

## string_xrefs

- `0x18000f29b`: `BITS proxy HelperToken is set`
- `0x18000f1fd`: `Can't impersonate. Error: 0x%08X`
- `0x18000f214`: `Impersonator<struct ImpersonatorLoggedOnUserTraits>::Impersonator`

## pseudocode

```c
__int64 __fastcall MapsBackgroundTransferJob::SetUserProxySettings(MapsBackgroundTransferJob *this)
{
  void *v2; // rsi
  int v3; // eax
  int v4; // r8d
  unsigned int v5; // edi
  __int64 v6; // rdx
  __int64 v7; // rax
  _OWORD *v8; // rax
  int BitsTokenOptionsWithProxyBlanket; // eax
  int v10; // r8d
  MapsBackgroundTransferJob *v11; // r9
  signed int LastError; // eax
  struct IBitsTokenOptions *v13; // rsi
  int v14; // eax
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  struct IBitsTokenOptions *v17; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v20[24]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[16]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v22; // [rsp+78h] [rbp-88h]
  _OWORD v23[4]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v24[1024]; // [rsp+D0h] [rbp-30h] BYREF

  v18 = 0;
  v19 = 0;
  memset(v20, 0, sizeof(v20));
  v2 = 0;
  if ( !qword_18001D618 )
    goto LABEL_7;
  v3 = (**(__int64 (__fastcall ***)(__int64, __int64 *))qword_18001D618)(qword_18001D618, &v19);
  if ( v3 >= 0 )
  {
    v2 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 24LL))(v19);
    LOBYTE(v6) = v2 != 0;
    v3 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)qword_18001D618 + 8LL))(qword_18001D618, v6);
    if ( v3 < 0 )
    {
      v4 = 1488;
      goto LABEL_4;
    }
LABEL_7:
    *(_OWORD *)&v20[8] = 0;
    *(_DWORD *)v20 = 2;
    v3 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(
           *((_QWORD *)this + 3),
           &GUID_54b50739_686f_45eb_9dff_d6a9a0faa9af,
           &v18);
    if ( v3 < 0 )
    {
      v4 = 1496;
      goto LABEL_4;
    }
    *(_DWORD *)&v20[4] = 4;
    v3 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v18 + 328LL))(v18, v20);
    if ( v3 < 0 )
    {
      v4 = 1500;
      goto LABEL_4;
    }
    *(_DWORD *)&v20[4] = 3;
    v3 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v18 + 328LL))(v18, v20);
    if ( v3 < 0 )
    {
      v4 = 1504;
      goto LABEL_4;
    }
    *(_DWORD *)&v20[4] = 5;
    v3 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v18 + 328LL))(v18, v20);
    if ( v3 < 0 )
    {
      v4 = 1508;
      goto LABEL_4;
    }
    v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 3) + 256LL))(
           *((_QWORD *)this + 3),
           0,
           0,
           0);
    if ( v3 < 0 )
    {
      v4 = 1510;
      goto LABEL_4;
    }
    v5 = 0;
    if ( !v2 )
      goto LABEL_41;
    v17 = 0;
    v23[0] = *(_OWORD *)L"Windows.GenericBackgroundClient";
    v23[1] = *(_OWORD *)L"GenericBackgroundClient";
    v23[2] = *(_OWORD *)L"ackgroundClient";
    v23[3] = *(_OWORD *)L"dClient";
    memset_0(v24, 0, sizeof(v24));
    v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 40LL))(v19);
    std::wstring::wstring(v21, v7);
    if ( v22 )
      v8 = (_OWORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
    else
      v8 = v23;
    BitsTokenOptionsWithProxyBlanket = StringCchPrintfW(v24, 0x400u, L"X-BM-AppPackage: %s\r\n", v8);
    if ( BitsTokenOptionsWithProxyBlanket >= 0 )
    {
      BitsTokenOptionsWithProxyBlanket = MapsBackgroundTransferJob::SetRequestHeaders(this, v24);
      if ( BitsTokenOptionsWithProxyBlanket >= 0 )
      {
        BitsTokenOptionsWithProxyBlanket = MapsBackgroundTransferJob::GetBitsTokenOptionsWithProxyBlanket(this, &v17);
        if ( BitsTokenOptionsWithProxyBlanket >= 0 )
        {
          v16 = -2147024875;
          if ( ImpersonateLoggedOnUser(v2) )
          {
            v16 = 0;
          }
          else
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            v16 = LastError;
            if ( LastError < 0 )
              ZTraceHelper(
                0,
                "Impersonator<struct ImpersonatorLoggedOnUserTraits>::Impersonator",
                21,
                &v16,
                "Can't impersonate. Error: 0x%08X",
                LastError);
          }
          v13 = v17;
          v14 = ((__int64 (__fastcall *)(struct IBitsTokenOptions *))v17->lpVtbl->SetHelperToken)(v17);
          if ( v14 < 0 )
          {
            v5 = ZTraceReportPropagation(v14, "MapsBackgroundTransferJob::SetUserProxySettings", 1536, this);
            Impersonator<ImpersonatorLoggedOnUserTraits>::Revert(&v16);
            goto LABEL_40;
          }
          Impersonator<ImpersonatorLoggedOnUserTraits>::Revert(&v16);
          BitsTokenOptionsWithProxyBlanket = ((__int64 (__fastcall *)(struct IBitsTokenOptions *, __int64))v13->lpVtbl->SetHelperTokenFlags)(
                                               v13,
                                               2);
          v11 = this;
          if ( BitsTokenOptionsWithProxyBlanket >= 0 )
          {
            ZTraceHelper(
              3,
              "MapsBackgroundTransferJob::SetUserProxySettings",
              1541,
              this,
              "BITS proxy HelperToken is set");
            goto LABEL_40;
          }
          v10 = 1539;
LABEL_24:
          v5 = ZTraceReportPropagation(
                 BitsTokenOptionsWithProxyBlanket,
                 "MapsBackgroundTransferJob::SetUserProxySettings",
                 v10,
                 v11);
LABEL_40:
          std::wstring::_Tidy_deallocate(v21);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
          goto LABEL_41;
        }
        v10 = 1530;
      }
      else
      {
        v10 = 1528;
      }
    }
    else
    {
      v10 = 1527;
    }
    v11 = this;
    goto LABEL_24;
  }
  v4 = 1484;
LABEL_4:
  v5 = ZTraceReportPropagation(v3, "MapsBackgroundTransferJob::SetUserProxySettings", v4, this);
LABEL_41:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
  return v5;
}

```

## disassembly

```asm
0x18000ef18  push    rbp
0x18000ef1a  push    rbx
0x18000ef1b  push    rsi
0x18000ef1c  push    rdi
0x18000ef1d  lea     rbp, [rsp-7E8h]
0x18000ef25  sub     rsp, 8E8h
0x18000ef2c  mov     rax, cs:__security_cookie
0x18000ef33  xor     rax, rsp
0x18000ef36  mov     [rbp+800h+var_30], rax
0x18000ef3d  mov     rbx, rcx
0x18000ef40  mov     [rsp+900h+var_8C0], 0
0x18000ef49  mov     [rsp+900h+var_8B8], 0
0x18000ef52  xorps   xmm0, xmm0
0x18000ef55  xor     eax, eax
0x18000ef57  movups  [rsp+900h+var_8B0], xmm0
0x18000ef5c  mov     [rsp+900h+var_8A0], rax
0x18000ef61  xor     esi, esi
0x18000ef63  mov     rcx, cs:qword_18001D618
0x18000ef6a  test    rcx, rcx
0x18000ef6d  jz      short loc_18000EFDB
0x18000ef6f  mov     rax, [rcx]
0x18000ef72  lea     rdx, [rsp+900h+var_8B8]
0x18000ef77  mov     rax, [rax]
0x18000ef7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef7f  test    eax, eax
0x18000ef81  jns     short loc_18000EFA2
0x18000ef83  mov     r8d, 5CCh
0x18000ef89  mov     r9, rbx
0x18000ef8c  lea     rdx, aMapsbackground_31; "MapsBackgroundTransferJob::SetUserProxy"...
0x18000ef93  mov     ecx, eax
0x18000ef95  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000ef9b  mov     edi, eax
0x18000ef9d  jmp     loc_18000F2CF
0x18000efa2  mov     rcx, [rsp+900h+var_8B8]
0x18000efa7  mov     rax, [rcx]
0x18000efaa  mov     rax, [rax+18h]
0x18000efae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efb3  mov     rsi, rax
0x18000efb6  mov     rcx, cs:qword_18001D618
0x18000efbd  mov     r8, [rcx]
0x18000efc0  test    rax, rax
0x18000efc3  setnz   dl
0x18000efc6  mov     rax, [r8+8]
0x18000efca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efcf  test    eax, eax
0x18000efd1  jns     short loc_18000EFDB
0x18000efd3  mov     r8d, 5D0h
0x18000efd9  jmp     short loc_18000EF89
0x18000efdb  xorps   xmm0, xmm0
0x18000efde  movdqu  [rsp+900h+var_8B0+8], xmm0
0x18000efe4  mov     dword ptr [rsp+900h+var_8B0], 2
0x18000efec  mov     rcx, [rbx+18h]
0x18000eff0  mov     rax, [rcx]
0x18000eff3  lea     r8, [rsp+900h+var_8C0]
0x18000eff8  lea     rdx, _GUID_54b50739_686f_45eb_9dff_d6a9a0faa9af
0x18000efff  mov     rax, [rax]
0x18000f002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f007  nop
0x18000f008  test    eax, eax
0x18000f00a  jns     short loc_18000F017
0x18000f00c  mov     r8d, 5D8h
0x18000f012  jmp     loc_18000EF89
0x18000f017  mov     dword ptr [rsp+900h+var_8B0+4], 4
0x18000f01f  mov     rcx, [rsp+900h+var_8C0]
0x18000f024  mov     rax, [rcx]
0x18000f027  lea     rdx, [rsp+900h+var_8B0]
0x18000f02c  mov     rax, [rax+148h]
0x18000f033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f038  test    eax, eax
0x18000f03a  jns     short loc_18000F047
0x18000f03c  mov     r8d, 5DCh
0x18000f042  jmp     loc_18000EF89
0x18000f047  mov     dword ptr [rsp+900h+var_8B0+4], 3
0x18000f04f  mov     rcx, [rsp+900h+var_8C0]
0x18000f054  mov     rax, [rcx]
0x18000f057  lea     rdx, [rsp+900h+var_8B0]
0x18000f05c  mov     rax, [rax+148h]
0x18000f063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f068  test    eax, eax
0x18000f06a  jns     short loc_18000F077
0x18000f06c  mov     r8d, 5E0h
0x18000f072  jmp     loc_18000EF89
0x18000f077  mov     dword ptr [rsp+900h+var_8B0+4], 5
0x18000f07f  mov     rcx, [rsp+900h+var_8C0]
0x18000f084  mov     rax, [rcx]
0x18000f087  lea     rdx, [rsp+900h+var_8B0]
0x18000f08c  mov     rax, [rax+148h]
0x18000f093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f098  test    eax, eax
0x18000f09a  jns     short loc_18000F0A7
0x18000f09c  mov     r8d, 5E4h
0x18000f0a2  jmp     loc_18000EF89
0x18000f0a7  mov     rcx, [rbx+18h]
0x18000f0ab  mov     rax, [rcx]
0x18000f0ae  xor     r9d, r9d
0x18000f0b1  xor     r8d, r8d
0x18000f0b4  xor     edx, edx
0x18000f0b6  mov     rax, [rax+100h]
0x18000f0bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0c2  test    eax, eax
0x18000f0c4  jns     short loc_18000F0D1
0x18000f0c6  mov     r8d, 5E6h
0x18000f0cc  jmp     loc_18000EF89
0x18000f0d1  xor     edi, edi
0x18000f0d3  test    rsi, rsi
0x18000f0d6  jz      loc_18000F2CF
0x18000f0dc  mov     [rsp+900h+var_8C8], rdi
0x18000f0e1  movaps  xmm0, xmmword ptr cs:aWindowsGeneric; "Windows.GenericBackgroundClient"
0x18000f0e8  movaps  [rbp+800h+var_870], xmm0
0x18000f0ec  movaps  xmm1, xmmword ptr cs:aWindowsGeneric+10h; "GenericBackgroundClient"
0x18000f0f3  movaps  [rbp+800h+var_860], xmm1
0x18000f0f7  movaps  xmm0, xmmword ptr cs:aWindowsGeneric+20h; "ackgroundClient"
0x18000f0fe  movaps  [rbp+800h+var_850], xmm0
0x18000f102  movaps  xmm1, xmmword ptr cs:aWindowsGeneric+30h; "dClient"
0x18000f109  movaps  [rbp+800h+var_840], xmm1
0x18000f10d  xor     edx, edx; Val
0x18000f10f  mov     r8d, 800h; Size
0x18000f115  lea     rcx, [rbp+800h+var_830]; void *
0x18000f119  call    memset_0
0x18000f11e  mov     rcx, [rsp+900h+var_8B8]
0x18000f123  mov     rax, [rcx]
0x18000f126  mov     rax, [rax+28h]
0x18000f12a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f12f  mov     rdx, rax
0x18000f132  lea     rcx, [rsp+900h+var_898]
0x18000f137  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000f13c  nop
0x18000f13d  cmp     [rsp+900h+var_888], rdi
0x18000f142  jnz     short loc_18000F14A
0x18000f144  lea     rax, [rbp+800h+var_870]
0x18000f148  jmp     short loc_18000F154
0x18000f14a  lea     rcx, [rsp+900h+var_898]
0x18000f14f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000f154  mov     r9, rax
0x18000f157  lea     r8, aXBmApppackageS; "X-BM-AppPackage: %s\r\n"
0x18000f15e  mov     edx, 400h; unsigned __int64
0x18000f163  lea     rcx, [rbp+800h+var_830]; unsigned __int16 *
0x18000f167  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f16c  test    eax, eax
0x18000f16e  jns     short loc_18000F18F
0x18000f170  mov     r8d, 5F7h
0x18000f176  mov     r9, rbx
0x18000f179  lea     rdx, aMapsbackground_31; "MapsBackgroundTransferJob::SetUserProxy"...
0x18000f180  mov     ecx, eax
0x18000f182  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000f188  mov     edi, eax
0x18000f18a  jmp     loc_18000F2B9
0x18000f18f  lea     rdx, [rbp+800h+var_830]; unsigned __int16 *
0x18000f193  mov     rcx, rbx; this
0x18000f196  call    ?SetRequestHeaders@MapsBackgroundTransferJob@@UEAAJPEBG@Z; MapsBackgroundTransferJob::SetRequestHeaders(ushort const *)
0x18000f19b  test    eax, eax
0x18000f19d  jns     short loc_18000F1A7
0x18000f19f  mov     r8d, 5F8h
0x18000f1a5  jmp     short loc_18000F176
0x18000f1a7  lea     rdx, [rsp+900h+var_8C8]; struct IBitsTokenOptions **
0x18000f1ac  mov     rcx, rbx; this
0x18000f1af  call    ?GetBitsTokenOptionsWithProxyBlanket@MapsBackgroundTransferJob@@AEAAJPEAPEAUIBitsTokenOptions@@@Z; MapsBackgroundTransferJob::GetBitsTokenOptionsWithProxyBlanket(IBitsTokenOptions * *)
0x18000f1b4  test    eax, eax
0x18000f1b6  jns     short loc_18000F1C0
0x18000f1b8  mov     r8d, 5FAh
0x18000f1be  jmp     short loc_18000F176
0x18000f1c0  mov     [rsp+900h+var_8D0], 80070015h
0x18000f1c8  mov     rcx, rsi; hToken
0x18000f1cb  call    cs:__imp_ImpersonateLoggedOnUser
0x18000f1d1  test    eax, eax
0x18000f1d3  jz      short loc_18000F1DF
0x18000f1d5  mov     [rsp+900h+var_8D0], 0
0x18000f1dd  jmp     short loc_18000F224
0x18000f1df  call    cs:__imp_GetLastError
0x18000f1e5  test    eax, eax
0x18000f1e7  jle     short loc_18000F1F1
0x18000f1e9  movzx   eax, ax
0x18000f1ec  or      eax, 80070000h
0x18000f1f1  mov     [rsp+900h+var_8D0], eax
0x18000f1f5  test    eax, eax
0x18000f1f7  jns     short loc_18000F224
0x18000f1f9  mov     [rsp+900h+var_8D8], eax
0x18000f1fd  lea     rax, aCanTImpersonat; "Can't impersonate. Error: 0x%08X"
0x18000f204  mov     [rsp+900h+var_8E0], rax
0x18000f209  lea     r9, [rsp+900h+var_8D0]
0x18000f20e  mov     r8d, 15h
0x18000f214  lea     rdx, aImpersonatorSt; "Impersonator<struct ImpersonatorLoggedO"...
0x18000f21b  xor     ecx, ecx
0x18000f21d  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18000f223  nop
0x18000f224  mov     rsi, [rsp+900h+var_8C8]
0x18000f229  mov     rax, [rsi]
0x18000f22c  mov     rcx, rsi
0x18000f22f  mov     rax, [rax+28h]
0x18000f233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f238  test    eax, eax
0x18000f23a  jns     short loc_18000F263
0x18000f23c  mov     r9, rbx
0x18000f23f  mov     r8d, 600h
0x18000f245  lea     rdx, aMapsbackground_31; "MapsBackgroundTransferJob::SetUserProxy"...
0x18000f24c  mov     ecx, eax
0x18000f24e  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000f254  mov     edi, eax
0x18000f256  lea     rcx, [rsp+900h+var_8D0]
0x18000f25b  call    ?Revert@?$Impersonator@UImpersonatorLoggedOnUserTraits@@@@QEAAXXZ; Impersonator<ImpersonatorLoggedOnUserTraits>::Revert(void)
0x18000f260  nop
0x18000f261  jmp     short loc_18000F2B9
0x18000f263  lea     rcx, [rsp+900h+var_8D0]
0x18000f268  call    ?Revert@?$Impersonator@UImpersonatorLoggedOnUserTraits@@@@QEAAXXZ; Impersonator<ImpersonatorLoggedOnUserTraits>::Revert(void)
0x18000f26d  nop
0x18000f26e  mov     rax, [rsi]
0x18000f271  mov     edx, 2
0x18000f276  mov     rcx, rsi
0x18000f279  mov     rax, [rax+18h]
0x18000f27d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f282  mov     r9, rbx
0x18000f285  lea     rdx, aMapsbackground_31; "MapsBackgroundTransferJob::SetUserProxy"...
0x18000f28c  test    eax, eax
0x18000f28e  jns     short loc_18000F29B
0x18000f290  mov     r8d, 603h
0x18000f296  jmp     loc_18000F180
0x18000f29b  lea     rax, aBitsProxyHelpe; "BITS proxy HelperToken is set"
0x18000f2a2  mov     [rsp+900h+var_8E0], rax
0x18000f2a7  mov     r8d, 605h
0x18000f2ad  mov     ecx, 3
0x18000f2b2  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18000f2b8  nop
0x18000f2b9  lea     rcx, [rsp+900h+var_898]
0x18000f2be  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f2c3  nop
0x18000f2c4  lea     rcx, [rsp+900h+var_8C8]
0x18000f2c9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000f2ce  nop
0x18000f2cf  lea     rcx, [rsp+900h+var_8B8]
0x18000f2d4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000f2d9  nop
0x18000f2da  lea     rcx, [rsp+900h+var_8C0]
0x18000f2df  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000f2e4  mov     eax, edi
0x18000f2e6  mov     rcx, [rbp+800h+var_30]
0x18000f2ed  xor     rcx, rsp; StackCookie
0x18000f2f0  call    __security_check_cookie
0x18000f2f5  add     rsp, 8E8h
0x18000f2fc  pop     rdi
0x18000f2fd  pop     rsi
0x18000f2fe  pop     rbx
0x18000f2ff  pop     rbp
0x18000f300  retn
```
