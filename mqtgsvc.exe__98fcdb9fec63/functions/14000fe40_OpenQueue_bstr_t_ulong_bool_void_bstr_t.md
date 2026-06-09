# OpenQueue(_bstr_t,ulong,bool,void * *,_bstr_t *)

- ea: `0x14000fe40`
- end: `0x140010189`
- name: `?OpenQueue@@YAJV_bstr_t@@K_NPEAPEAXPEAV1@@Z`
- size: `841`
- prototype: `__int64 __fastcall(_bstr_t *, DWORD, __int64, QUEUEHANDLE *, _bstr_t *)`
- caller_count: `2`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x140006478`
- `0x14000eb04`

## callees

- `0x1400030ac`
- `0x140003868`
- `0x140005f1c`
- `0x140006ac8`
- `0x140007594`
- `0x140007a18`
- `0x140007a64`
- `0x14000ed18`
- `0x14000f6a0`
- `0x14000fabc`
- `0x14000fbcc`
- `0x14000fda4`
- `0x14000fe40`
- `0x140010258`

## import_xrefs

- `msvcrt!free` at `0x14001004a`
- `msvcrt!free` at `0x1400100dc`
- `msvcrt!free` at `0x140010113`
- `msvcrt!free` at `0x14001004a`
- `msvcrt!free` at `0x1400100dc`
- `msvcrt!free` at `0x140010113`
- `mqrt!MQOpenQueue` at `0x14000ffd9`
- `mqrt!MQOpenQueue` at `0x140010108`
- `mqrt!MQOpenQueue` at `0x14000ffd9`
- `mqrt!MQOpenQueue` at `0x140010108`
- `mqrt!MQPathNameToFormatName` at `0x140010030`
- `mqrt!MQPathNameToFormatName` at `0x14001008a`
- `mqrt!MQPathNameToFormatName` at `0x140010030`
- `mqrt!MQPathNameToFormatName` at `0x14001008a`

## pseudocode

```c
__int64 __fastcall OpenQueue(_bstr_t *a1, DWORD a2, __int64 a3, QUEUEHANDLE *a4, _bstr_t *a5)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  HRESULT v10; // ebx
  volatile signed __int32 *v11; // rax
  volatile signed __int32 *v12; // rax
  char v13; // r12
  __int64 v14; // rdx
  _QWORD *v15; // rax
  bool v16; // si
  const struct _bstr_t::Data_t **v17; // rax
  int v18; // ebx
  volatile signed __int32 *v19; // rax
  const WCHAR *v20; // rcx
  HRESULT v21; // eax
  WCHAR *v22; // rsi
  const WCHAR *v23; // rcx
  WCHAR *v24; // rax
  const WCHAR *v25; // rcx
  const WCHAR *v26; // rcx
  WCHAR *v28; // [rsp+40h] [rbp-51h] BYREF
  DWORD dwFormatNameLength; // [rsp+48h] [rbp-49h] BYREF
  _QWORD v30[3]; // [rsp+50h] [rbp-41h] BYREF
  __int128 v31; // [rsp+68h] [rbp-29h]
  __int128 v32; // [rsp+78h] [rbp-19h]
  _BYTE v33[88]; // [rsp+88h] [rbp-9h] BYREF

  v30[1] = a1;
  dwFormatNameLength = 0;
  _bstr_t::operator=(a5, &ServiceName);
  v31 = 0;
  v32 = 0;
  if ( a2 - 1 > 1 && a2 != 32 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dddd(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, a2);
    v10 = -1072820735;
    goto LABEL_48;
  }
  v11 = *(volatile signed __int32 **)a1;
  v28 = (WCHAR *)v11;
  if ( v11 )
    _InterlockedIncrement(v11 + 4);
  if ( (unsigned int)IsSystemQueue(&v28) )
  {
    v13 = 1;
    v16 = 1;
    _bstr_t::operator=(a5, a1);
  }
  else
  {
    v12 = *(volatile signed __int32 **)a1;
    v28 = (WCHAR *)v12;
    if ( v12 )
      _InterlockedIncrement(v12 + 4);
    v13 = IsQueueLocal((_bstr_t *)&v28);
    if ( *(_QWORD *)a1 )
      v14 = **(_QWORD **)a1;
    else
      v14 = 0;
    v15 = (_QWORD *)std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(
                      v33,
                      v14);
    v16 = IsPrivateQPath(v15);
  }
  v17 = (const struct _bstr_t::Data_t **)_bstr_t::_bstr_t((_bstr_t *)&v28, &ServiceName);
  v18 = _bstr_t::_Compare((_bstr_t::Data_t **)a5, v17);
  _bstr_t::_Free((_bstr_t *)&v28);
  if ( !v18 )
  {
    v19 = *(volatile signed __int32 **)a1;
    v30[0] = v19;
    if ( v19 )
      _InterlockedIncrement(v19 + 4);
    v30[2] = v30;
    _bstr_t::_bstr_t((_bstr_t *)&v28, L"DIRECT=OS:");
    dwFormatNameLength = 1;
    _bstr_t::operator+=((struct _bstr_t *)&v28, (struct _bstr_t *)v30);
    _bstr_t::_Free((_bstr_t *)v30);
    _bstr_t::operator=(a5, &v28);
    _bstr_t::_Free((_bstr_t *)&v28);
  }
  if ( *(_QWORD *)a5 )
    v20 = **(const WCHAR ***)a5;
  else
    v20 = 0;
  v21 = MQOpenQueue(v20, a2, 0, a4);
  v10 = v21;
  if ( v21 >= 0 )
    goto LABEL_47;
  if ( v21 == -1072824288 && (v13 || !v16) )
  {
    dwFormatNameLength = 512;
    v22 = (WCHAR *)MmAllocate(0x402u);
    v28 = v22;
    if ( *(_QWORD *)a1 )
      v23 = **(const WCHAR ***)a1;
    else
      v23 = 0;
    v10 = MQPathNameToFormatName(v23, v22, &dwFormatNameLength);
    if ( v10 == -1072824289 )
    {
      v28 = 0;
      free(v22);
      v24 = (WCHAR *)MmAllocate(saturated_mul(dwFormatNameLength + 1, 2u));
      v22 = v24;
      v28 = v24;
      v25 = *(const WCHAR **)a1;
      if ( *(_QWORD *)a1 )
        v25 = *(const WCHAR **)v25;
      v10 = MQPathNameToFormatName(v25, v24, &dwFormatNameLength);
    }
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10);
      free(v22);
      goto LABEL_48;
    }
    _bstr_t::operator=(a5, v22);
    v26 = *(_QWORD *)a5 ? **(const WCHAR ***)a5 : 0LL;
    v10 = MQOpenQueue(v26, a2, 0, a4);
    free(v22);
    if ( v10 >= 0 )
    {
LABEL_47:
      v10 = 0;
      goto LABEL_48;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10);
LABEL_48:
  _bstr_t::_Free(a1);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000fe40  mov     [rsp-8+arg_10], rbx
0x14000fe45  push    rbp
0x14000fe46  push    rsi
0x14000fe47  push    rdi
0x14000fe48  push    r12
0x14000fe4a  push    r13
0x14000fe4c  push    r14
0x14000fe4e  push    r15
0x14000fe50  lea     rbp, [rsp-1Fh]
0x14000fe55  sub     rsp, 0B0h
0x14000fe5c  mov     r13, r9
0x14000fe5f  mov     r15d, edx
0x14000fe62  mov     rdi, rcx
0x14000fe65  mov     r14, [rbp+4Fh+arg_20]
0x14000fe69  mov     [rbp+4Fh+var_88], rcx
0x14000fe6d  mov     [rbp+4Fh+dwFormatNameLength], 0
0x14000fe74  lea     rdx, ServiceName
0x14000fe7b  mov     rcx, r14
0x14000fe7e  call    ??4_bstr_t@@QEAAAEAV0@PEB_W@Z; _bstr_t::operator=(wchar_t const *)
0x14000fe83  xorps   xmm0, xmm0
0x14000fe86  movups  [rbp+4Fh+var_78], xmm0
0x14000fe8a  movups  [rbp+4Fh+var_68], xmm0
0x14000fe8e  lea     eax, [r15-1]
0x14000fe92  cmp     eax, 1
0x14000fe95  jbe     short loc_14000FECC
0x14000fe97  cmp     r15d, 20h ; ' '
0x14000fe9b  jz      short loc_14000FECC
0x14000fe9d  lea     rax, WPP_GLOBAL_Control
0x14000fea4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000feab  cmp     rcx, rax
0x14000feae  jz      short loc_14000FEC2
0x14000feb0  test    byte ptr [rcx+1Ch], 1
0x14000feb4  jz      short loc_14000FEC2
0x14000feb6  mov     r9d, r15d
0x14000feb9  mov     rcx, [rcx+10h]
0x14000febd  call    WPP_SF_dddd
0x14000fec2  mov     ebx, 0C00E0E01h
0x14000fec7  jmp     loc_140010164
0x14000fecc  mov     rax, [rdi]
0x14000fecf  mov     [rbp+4Fh+var_A0], rax
0x14000fed3  test    rax, rax
0x14000fed6  jz      short loc_14000FEDC
0x14000fed8  lock inc dword ptr [rax+10h]
0x14000fedc  lea     rcx, [rbp+4Fh+var_A0]
0x14000fee0  call    ?IsSystemQueue@@YA?AW4__MIDL___MIDL_itf_mqtrig_0000_0000_0002@@V_bstr_t@@@Z; IsSystemQueue(_bstr_t)
0x14000fee5  test    eax, eax
0x14000fee7  jnz     short loc_14000FF2A
0x14000fee9  mov     rax, [rdi]
0x14000feec  mov     [rbp+4Fh+var_A0], rax
0x14000fef0  test    rax, rax
0x14000fef3  jz      short loc_14000FEF9
0x14000fef5  lock inc dword ptr [rax+10h]
0x14000fef9  lea     rcx, [rbp+4Fh+var_A0]
0x14000fefd  call    ?IsQueueLocal@@YA_NV_bstr_t@@@Z; IsQueueLocal(_bstr_t)
0x14000ff02  mov     r12b, al
0x14000ff05  mov     rcx, [rdi]
0x14000ff08  test    rcx, rcx
0x14000ff0b  jz      short loc_14000FF12
0x14000ff0d  mov     rdx, [rcx]
0x14000ff10  jmp     short loc_14000FF14
0x14000ff12  xor     edx, edx
0x14000ff14  lea     rcx, [rbp+4Fh+var_58]
0x14000ff18  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(wchar_t const *)
0x14000ff1d  mov     rcx, rax
0x14000ff20  call    ?IsPrivateQPath@@YA_NV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@Z; IsPrivateQPath(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>)
0x14000ff25  mov     sil, al
0x14000ff28  jmp     short loc_14000FF3B
0x14000ff2a  mov     r12b, 1
0x14000ff2d  mov     sil, r12b
0x14000ff30  mov     rdx, rdi
0x14000ff33  mov     rcx, r14
0x14000ff36  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x14000ff3b  lea     rdx, ServiceName; wchar_t *
0x14000ff42  lea     rcx, [rbp+4Fh+var_A0]; this
0x14000ff46  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x14000ff4b  mov     rdx, rax; struct _bstr_t *
0x14000ff4e  mov     rcx, r14; this
0x14000ff51  call    ?_Compare@_bstr_t@@AEBAHAEBV1@@Z; _bstr_t::_Compare(_bstr_t const &)
0x14000ff56  mov     ebx, eax
0x14000ff58  lea     rcx, [rbp+4Fh+var_A0]; this
0x14000ff5c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14000ff61  test    ebx, ebx
0x14000ff63  jnz     short loc_14000FFC1
0x14000ff65  mov     rax, [rdi]
0x14000ff68  mov     [rbp+4Fh+var_90], rax
0x14000ff6c  test    rax, rax
0x14000ff6f  jz      short loc_14000FF75
0x14000ff71  lock inc dword ptr [rax+10h]
0x14000ff75  lea     rax, [rbp+4Fh+var_90]
0x14000ff79  mov     [rbp+4Fh+var_80], rax
0x14000ff7d  lea     rdx, aDirectOs; "DIRECT=OS:"
0x14000ff84  lea     rcx, [rbp+4Fh+var_A0]; this
0x14000ff88  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x14000ff8d  mov     [rbp+4Fh+dwFormatNameLength], 1
0x14000ff94  lea     rdx, [rbp+4Fh+var_90]; struct _bstr_t *
0x14000ff98  lea     rcx, [rbp+4Fh+var_A0]; struct _bstr_t *
0x14000ff9c  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x14000ffa1  nop
0x14000ffa2  lea     rcx, [rbp+4Fh+var_90]; this
0x14000ffa6  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14000ffab  lea     rdx, [rbp+4Fh+var_A0]
0x14000ffaf  mov     rcx, r14
0x14000ffb2  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x14000ffb7  nop
0x14000ffb8  lea     rcx, [rbp+4Fh+var_A0]; this
0x14000ffbc  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14000ffc1  mov     rax, [r14]
0x14000ffc4  test    rax, rax
0x14000ffc7  jz      short loc_14000FFCE
0x14000ffc9  mov     rcx, [rax]
0x14000ffcc  jmp     short loc_14000FFD0
0x14000ffce  xor     ecx, ecx; lpwcsFormatName
0x14000ffd0  mov     r9, r13; phQueue
0x14000ffd3  xor     r8d, r8d; dwShareMode
0x14000ffd6  mov     edx, r15d; dwAccess
0x14000ffd9  call    cs:__imp_MQOpenQueue
0x14000ffdf  mov     ebx, eax
0x14000ffe1  test    eax, eax
0x14000ffe3  jns     loc_140010162
0x14000ffe9  cmp     eax, 0C00E0020h
0x14000ffee  jnz     loc_14001011E
0x14000fff4  test    r12b, r12b
0x14000fff7  jnz     short loc_140010002
0x14000fff9  test    sil, sil
0x14000fffc  jnz     loc_14001011E
0x140010002  mov     [rbp+4Fh+dwFormatNameLength], 200h
0x140010009  mov     ecx, 402h; unsigned __int64
0x14001000e  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x140010013  mov     rsi, rax
0x140010016  mov     [rbp+4Fh+var_A0], rax
0x14001001a  mov     rax, [rdi]
0x14001001d  test    rax, rax
0x140010020  jz      short loc_140010027
0x140010022  mov     rcx, [rax]
0x140010025  jmp     short loc_140010029
0x140010027  xor     ecx, ecx; lpwcsPathName
0x140010029  lea     r8, [rbp+4Fh+dwFormatNameLength]; lpdwFormatNameLength
0x14001002d  mov     rdx, rsi; lpwcsFormatName
0x140010030  call    cs:__imp_MQPathNameToFormatName
0x140010036  mov     ebx, eax
0x140010038  cmp     eax, 0C00E001Fh
0x14001003d  jnz     short loc_140010092
0x14001003f  mov     [rbp+4Fh+var_A0], 0
0x140010047  mov     rcx, rsi; Block
0x14001004a  call    cs:__imp_free
0x140010050  nop
0x140010051  mov     ecx, [rbp+4Fh+dwFormatNameLength]
0x140010054  inc     ecx
0x140010056  mov     eax, 2
0x14001005b  mul     rcx
0x14001005e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140010065  cmovb   rax, rcx
0x140010069  mov     rcx, rax; unsigned __int64
0x14001006c  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x140010071  mov     rsi, rax
0x140010074  mov     [rbp+4Fh+var_A0], rax
0x140010078  mov     rcx, [rdi]
0x14001007b  test    rcx, rcx
0x14001007e  jz      short loc_140010083
0x140010080  mov     rcx, [rcx]; lpwcsPathName
0x140010083  lea     r8, [rbp+4Fh+dwFormatNameLength]; lpdwFormatNameLength
0x140010087  mov     rdx, rax; lpwcsFormatName
0x14001008a  call    cs:__imp_MQPathNameToFormatName
0x140010090  mov     ebx, eax
0x140010092  test    ebx, ebx
0x140010094  jns     short loc_1400100E5
0x140010096  lea     rax, WPP_GLOBAL_Control
0x14001009d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400100a4  cmp     rcx, rax
0x1400100a7  jz      short loc_1400100D9
0x1400100a9  test    byte ptr [rcx+1Ch], 1
0x1400100ad  jz      short loc_1400100D9
0x1400100af  mov     rax, [rdi]
0x1400100b2  test    rax, rax
0x1400100b5  jz      short loc_1400100BC
0x1400100b7  mov     r9, [rax]
0x1400100ba  jmp     short loc_1400100BF
0x1400100bc  xor     r9d, r9d
0x1400100bf  mov     edx, 0Dh
0x1400100c4  mov     dword ptr [rsp+0E0h+var_C0], ebx; char
0x1400100c8  lea     r8, WPP_f17d2b29d4b8365f8ea91b4848b968c5_Traceguids
0x1400100cf  mov     rcx, [rcx+10h]; LoggerHandle
0x1400100d3  call    WPP_SF_Sd
0x1400100d8  nop
0x1400100d9  mov     rcx, rsi; Block
0x1400100dc  call    cs:__imp_free
0x1400100e2  nop
0x1400100e3  jmp     short loc_140010164
0x1400100e5  mov     rdx, rsi
0x1400100e8  mov     rcx, r14
0x1400100eb  call    ??4_bstr_t@@QEAAAEAV0@PEB_W@Z; _bstr_t::operator=(wchar_t const *)
0x1400100f0  mov     rax, [r14]
0x1400100f3  test    rax, rax
0x1400100f6  jz      short loc_1400100FD
0x1400100f8  mov     rcx, [rax]
0x1400100fb  jmp     short loc_1400100FF
0x1400100fd  xor     ecx, ecx; lpwcsFormatName
0x1400100ff  mov     r9, r13; phQueue
0x140010102  xor     r8d, r8d; dwShareMode
0x140010105  mov     edx, r15d; dwAccess
0x140010108  call    cs:__imp_MQOpenQueue
0x14001010e  mov     ebx, eax
0x140010110  mov     rcx, rsi; Block
0x140010113  call    cs:__imp_free
0x140010119  nop
0x14001011a  test    ebx, ebx
0x14001011c  jns     short loc_140010162
0x14001011e  lea     rax, WPP_GLOBAL_Control
0x140010125  mov     rcx, cs:WPP_GLOBAL_Control
0x14001012c  cmp     rcx, rax
0x14001012f  jz      short loc_140010164
0x140010131  test    byte ptr [rcx+1Ch], 1
0x140010135  jz      short loc_140010164
0x140010137  mov     rax, [rdi]
0x14001013a  test    rax, rax
0x14001013d  jz      short loc_140010144
0x14001013f  mov     r9, [rax]
0x140010142  jmp     short loc_140010147
0x140010144  xor     r9d, r9d
0x140010147  mov     edx, 0Eh
0x14001014c  mov     dword ptr [rsp+0E0h+var_C0], ebx; char
0x140010150  lea     r8, WPP_f17d2b29d4b8365f8ea91b4848b968c5_Traceguids
0x140010157  mov     rcx, [rcx+10h]; LoggerHandle
0x14001015b  call    WPP_SF_Sd
0x140010160  jmp     short loc_140010164
0x140010162  xor     ebx, ebx
0x140010164  mov     rcx, rdi; this
0x140010167  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14001016c  mov     eax, ebx
0x14001016e  mov     rbx, [rsp+0E0h+arg_10]
0x140010176  add     rsp, 0B0h
0x14001017d  pop     r15
0x14001017f  pop     r14
0x140010181  pop     r13
0x140010183  pop     r12
0x140010185  pop     rdi
0x140010186  pop     rsi
0x140010187  pop     rbp
0x140010188  retn
```
