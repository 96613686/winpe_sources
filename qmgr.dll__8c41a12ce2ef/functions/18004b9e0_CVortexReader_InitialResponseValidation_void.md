# CVortexReader::InitialResponseValidation(void)

- ea: `0x18004b9e0`
- end: `0x18004c31b`
- name: `?InitialResponseValidation@CVortexReader@@MEAAXXZ`
- size: `2363`
- prototype: `void __fastcall(CVortexReader *__hidden this)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180006640`
- `0x180008b70`
- `0x18000db20`
- `0x18004b9e0`
- `0x18004c324`
- `0x18004d5a0`
- `0x18009d024`
- `0x18009d1bc`
- `0x18009e9c8`
- `0x1800a3420`
- `0x1800a3444`
- `0x1800a3eac`
- `0x1800a7558`
- `0x1800ab7b0`
- `0x1800ab7fc`
- `0x1800de26c`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004beb6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004beb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bb00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bca2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bcac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bcb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bf5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c003`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bb00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bca2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bcac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bcb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bf5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c003`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004bf52`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004bf52`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall CVortexReader::InitialResponseValidation(CVortexReader *this)
{
  __int64 v2; // rdi
  int v3; // ecx
  __int64 v4; // rsi
  signed int LastError; // eax
  wchar_t *v6; // rdi
  unsigned int v7; // eax
  EVENT_LOG *v8; // rcx
  unsigned int RequestStatus; // eax
  _DWORD *v10; // rax
  signed int v11; // eax
  struct IHttpRequest *v12; // rcx
  unsigned __int64 ResponseContentLength; // rax
  unsigned __int64 v14; // rdi
  DWORD v15; // eax
  EVENT_LOG *v16; // rcx
  unsigned int v17; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v18; // [rsp+44h] [rbp-BCh] BYREF
  int v19; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v20[2]; // [rsp+50h] [rbp-B0h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v22; // [rsp+68h] [rbp-98h]
  __int64 v23; // [rsp+78h] [rbp-88h]
  _DWORD *v24; // [rsp+80h] [rbp-80h]
  __int64 v25; // [rsp+88h] [rbp-78h]
  void *v26; // [rsp+90h] [rbp-70h]
  wchar_t *v27; // [rsp+C0h] [rbp-40h] BYREF
  void **v28; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v29; // [rsp+D8h] [rbp-28h]
  int v30; // [rsp+E8h] [rbp-18h]
  int v31; // [rsp+ECh] [rbp-14h]
  int v32; // [rsp+F0h] [rbp-10h]
  wchar_t Format[12]; // [rsp+130h] [rbp+30h] BYREF

  *((_BYTE *)this + 263394) = 1;
  v2 = *((_QWORD *)this + 83);
  v17 = 0;
  (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, unsigned int *, _QWORD))(*(_QWORD *)v2 + 80LL))(
    v2,
    2147483670LL,
    0,
    0,
    &v17,
    0);
  v17 >>= 1;
  LODWORD(v20[0]) = 0;
  (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _QWORD *, _QWORD))(*(_QWORD *)v2 + 80LL))(
    v2,
    22,
    0,
    0,
    v20,
    0);
  v3 = (LODWORD(v20[0]) >> 1) + *(_DWORD *)(*((_QWORD *)this + 80) + 88LL) + v17 + 72;
  *((_DWORD *)this + 65882) = v3;
  *((_DWORD *)this + 31) += v3;
  v18 = 0;
  v19 = 0;
  v4 = *((_QWORD *)this + 83);
  v27 = 0;
  wcscpy(Format, L"HTTP/%.%u");
  v17 = 0;
  v20[0] = 0;
  (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, unsigned int *, _QWORD))(*(_QWORD *)v4 + 80LL))(
    v4,
    18,
    0,
    0,
    &v17,
    0);
  LastError = GetLastError();
  if ( LastError == 12150 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids);
    v22 = 0;
    pExceptionObject = &ComError::`vftable';
    v23 = 0xC578020001BLL;
    LODWORD(v24) = 1;
    throw (ComError *)&pExceptionObject;
  }
  if ( LastError == 12154 )
  {
    v22 = 0;
    pExceptionObject = &ComError::`vftable';
    v23 = 0xFA58020001BLL;
    LODWORD(v24) = 1;
    throw (ComError *)&pExceptionObject;
  }
  if ( LastError != 122 )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v22 = 0;
    pExceptionObject = &ComError::`vftable';
    v23 = (unsigned int)LastError | 0xFAA00000000LL;
    LODWORD(v24) = 1;
    throw (ComError *)&pExceptionObject;
  }
  if ( v17 > 0x40 )
  {
    v22 = 0;
    pExceptionObject = &ComError::`vftable';
    v23 = 0xFAF8020001BLL;
    LODWORD(v24) = 1;
    throw (ComError *)&pExceptionObject;
  }
  v6 = (wchar_t *)operator new(saturated_mul((unsigned __int64)v17 >> 1, 2u));
  v20[0] = v6;
  if ( !(*(unsigned int (__fastcall **)(__int64, __int64, _QWORD, wchar_t *, unsigned int *, _QWORD))(*(_QWORD *)v4 + 80LL))(
          v4,
          18,
          0,
          v6,
          &v17,
          0) )
  {
    if ( (int)GetLastError() > 0 )
      v7 = (unsigned __int16)GetLastError() | 0x80070000;
    else
      v7 = GetLastError();
    v22 = 0;
    pExceptionObject = &ComError::`vftable';
    v23 = v7 | 0xFB600000000LL;
    LODWORD(v24) = 1;
    throw (ComError *)&pExceptionObject;
  }
  v27 = v6;
  if ( swscanf(v6, Format, &v18, &v19) != 2 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids);
    v22 = 0;
    pExceptionObject = &ComError::`vftable';
    v23 = 0xC5D8020001BLL;
    LODWORD(v24) = 1;
    throw (ComError *)&pExceptionObject;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, &WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids, v18, v19);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v6 )
  {
    operator delete(v6, 2u);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v18 != 1 )
  {
    if ( v8 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 )
      WPP_SF_Dd(*((_QWORD *)v8 + 2), 33, &WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids, v18, v19);
    v22 = 0;
    pExceptionObject = &ComError::`vftable';
    v23 = 0x24D80200012LL;
    LODWORD(v24) = 1;
    throw (ComError *)&pExceptionObject;
  }
  RequestStatus = GetRequestStatus(*((struct IHttpRequest **)this + 83));
  if ( *((_QWORD *)this + 32918) && (RequestStatus == 200 || RequestStatus == 206) )
  {
    CSaveThreadToken::CSaveThreadToken((CSaveThreadToken *)&pExceptionObject);
    LOBYTE(v22) = 0;
    *((_QWORD *)&v22 + 1) = *((_QWORD *)this + 32913);
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL));
    v23 = 0;
    v10 = HeapAlloc(hBitsHeap, 8u, 4u);
    if ( !v10 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 4);
      v29 = 0;
      v28 = &ComError::`vftable';
      v30 = -2147024882;
      v31 = 0;
      v32 = 1;
      throw (ComError *)&v28;
    }
    *v10 = 1;
    v24 = v10;
    v25 = 0;
    _InterlockedIncrement(&dword_180145058);
    v26 = &GenericStringHandle<unsigned short>::s_EmptyString;
    if ( !(_BYTE)v22 )
    {
      if ( !ImpersonateLoggedOnUser(**((HANDLE **)&v22 + 1)) )
      {
        v11 = GetLastError();
        if ( v11 > 0 )
          v11 = (unsigned __int16)v11 | 0x80070000;
        v29 = 0;
        v28 = &ComError::`vftable';
        v30 = v11;
        v31 = 0;
        v32 = 1;
        throw (ComError *)&v28;
      }
      LOBYTE(v22) = 1;
    }
    v12 = (struct IHttpRequest *)*((_QWORD *)this + 83);
    if ( *((_DWORD *)this + 32) == 2 )
      ResponseContentLength = MaybeGetResponseContentLength(v12);
    else
      ResponseContentLength = GetResponseContentLength(v12);
    v14 = ResponseContentLength;
    LODWORD(v20[0]) = 0;
    v27 = 0;
    if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD *, wchar_t **))(**((_QWORD **)this + 32917)
                                                                                      + 32LL))(
           *((_QWORD *)this + 32917),
           *((_QWORD *)this + 32918),
           *((_QWORD *)this + 83),
           v20,
           &v27) )
    {
      v15 = GetLastError();
      if ( v15 == 8 )
      {
        if ( !byte_180145A37 )
        {
          byte_180145A37 = 1;
          CVortexReader::ReportP2PFailure(this, 8, 0);
        }
        v29 = 0;
        v28 = &ComError::`vftable';
        v30 = -2147024888;
        v31 = 650;
        v32 = 1;
        throw (ComError *)&v28;
      }
      byte_180145A37 = 0;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids, v15);
          v16 = WPP_GLOBAL_Control;
        }
        if ( v16 != (EVENT_LOG *)&WPP_GLOBAL_Control )
        {
          if ( (*((_DWORD *)v16 + 7) & 0x1000) != 0 )
          {
            WPP_SF_q(
              *((_QWORD *)v16 + 2),
              35,
              &WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids,
              *((_QWORD *)this + 32918));
            v16 = WPP_GLOBAL_Control;
          }
          if ( v16 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x1000) != 0 )
            WPP_SF_q(
              *((_QWORD *)v16 + 2),
              36,
              &WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids,
              *((_QWORD *)this + 32918));
        }
      }
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 32917) + 80LL))(
        *((_QWORD *)this + 32917),
        *((_QWORD *)this + 32918));
      *((_QWORD *)this + 32918) = 0;
      *((_BYTE *)this + 263392) = 1;
      *((_BYTE *)this + 263395) = 0;
      CNestedImpersonation::~CNestedImpersonation(&pExceptionObject);
    }
    else
    {
      if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 32917) + 40LL))(
             *((_QWORD *)this + 32917),
             *((_QWORD *)this + 32918)) )
      {
        *((_BYTE *)this + 263395) = 1;
        if ( v14 == -1 )
        {
          if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids);
          v29 = 0;
          v28 = &ComError::`vftable';
          v30 = -2145386479;
          v31 = 679;
          v32 = 1;
          throw (ComError *)&v28;
        }
        *((_QWORD *)this + 32919) = v14;
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        {
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            38,
            &WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids,
            *((_QWORD *)this + 32918),
            v14);
        }
        byte_180145A36 = 0;
      }
      else
      {
        *((_BYTE *)this + 263395) = 0;
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids);
        }
        *((_QWORD *)this + 32919) = 0;
        if ( !byte_180145A36 )
        {
          byte_180145A36 = 1;
          CVortexReader::ReportP2PFailure(this, 2147745808LL, 5);
        }
        if ( *((_BYTE *)this + 120) && !*((_BYTE *)this + 263392) )
        {
          *((_BYTE *)this + 263392) = 1;
          v29 = 0;
          v28 = &ComError::`vftable';
          v30 = -2147221488;
          v31 = 712;
          v32 = 1;
          throw (ComError *)&v28;
        }
        *((_BYTE *)this + 263392) = 1;
      }
      CNestedImpersonation::~CNestedImpersonation(&pExceptionObject);
    }
  }
  else if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids);
  }
}

```

## disassembly

```asm
0x18004b9e0  mov     [rsp-8+arg_8], rbx
0x18004b9e5  mov     [rsp-8+arg_10], rsi
0x18004b9ea  push    rbp
0x18004b9eb  push    rdi
0x18004b9ec  push    r14
0x18004b9ee  lea     rbp, [rsp-50h]
0x18004b9f3  sub     rsp, 150h
0x18004b9fa  mov     rax, cs:__security_cookie
0x18004ba01  xor     rax, rsp
0x18004ba04  mov     [rbp+60h+var_18], rax
0x18004ba08  mov     rbx, rcx
0x18004ba0b  mov     byte ptr [rcx+404E2h], 1
0x18004ba12  mov     rdi, [rcx+298h]
0x18004ba19  xor     r14d, r14d
0x18004ba1c  mov     [rsp+160h+var_120], r14d
0x18004ba21  mov     rax, [rdi]
0x18004ba24  mov     [rsp+160h+var_138], r14
0x18004ba29  lea     rcx, [rsp+160h+var_120]
0x18004ba2e  mov     [rsp+160h+var_140], rcx
0x18004ba33  xor     r9d, r9d
0x18004ba36  xor     r8d, r8d
0x18004ba39  mov     edx, 80000016h
0x18004ba3e  mov     rcx, rdi
0x18004ba41  mov     rax, [rax+50h]
0x18004ba45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ba4a  shr     [rsp+160h+var_120], 1
0x18004ba4e  mov     dword ptr [rsp+160h+var_110], r14d
0x18004ba53  mov     rax, [rdi]
0x18004ba56  mov     [rsp+160h+var_138], r14
0x18004ba5b  lea     rcx, [rsp+160h+var_110]
0x18004ba60  mov     [rsp+160h+var_140], rcx
0x18004ba65  xor     r9d, r9d
0x18004ba68  xor     r8d, r8d
0x18004ba6b  mov     edx, 16h
0x18004ba70  mov     rcx, rdi
0x18004ba73  mov     rax, [rax+50h]
0x18004ba77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ba7c  mov     rax, [rbx+280h]
0x18004ba83  mov     ecx, dword ptr [rsp+160h+var_110]
0x18004ba87  shr     ecx, 1
0x18004ba89  mov     edx, [rax+58h]
0x18004ba8c  add     edx, ecx
0x18004ba8e  mov     ecx, [rsp+160h+var_120]
0x18004ba92  add     ecx, 48h ; 'H'
0x18004ba95  add     ecx, edx
0x18004ba97  mov     [rbx+40568h], ecx
0x18004ba9d  add     [rbx+7Ch], ecx
0x18004baa0  mov     [rsp+160h+var_11C], r14d
0x18004baa5  mov     [rsp+160h+var_118], r14d
0x18004baaa  mov     rsi, [rbx+298h]
0x18004bab1  mov     [rbp+60h+var_A0], r14
0x18004bab5  movups  xmm0, xmmword ptr cs:aHttpUU; "HTTP/%u.%u"
0x18004babc  movups  xmmword ptr [rbp+60h+Format], xmm0
0x18004bac0  movsd   xmm1, qword ptr cs:aHttpUU+0Eh; ".%u"
0x18004bac8  movsd   qword ptr [rbp+60h+Format+0Eh], xmm1
0x18004bacd  mov     [rsp+160h+var_120], r14d
0x18004bad2  mov     [rsp+160h+var_110], r14
0x18004bad7  mov     rax, [rsi]
0x18004bada  mov     [rsp+160h+var_138], r14
0x18004badf  lea     rcx, [rsp+160h+var_120]
0x18004bae4  mov     [rsp+160h+var_140], rcx
0x18004bae9  xor     r9d, r9d
0x18004baec  xor     r8d, r8d
0x18004baef  mov     edx, 12h
0x18004baf4  mov     rcx, rsi
0x18004baf7  mov     rax, [rax+50h]
0x18004bafb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bb00  call    cs:__imp_GetLastError
0x18004bb06  cmp     eax, 2F76h
0x18004bb0b  jnz     short loc_18004BB78
0x18004bb0d  lea     rsi, WPP_GLOBAL_Control
0x18004bb14  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bb1b  cmp     rcx, rsi
0x18004bb1e  jz      short loc_18004BB3B
0x18004bb20  test    byte ptr [rcx+1Ch], 4
0x18004bb24  jz      short loc_18004BB3B
0x18004bb26  mov     edx, 6Ch ; 'l'
0x18004bb2b  lea     r8, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids
0x18004bb32  mov     rcx, [rcx+10h]
0x18004bb36  call    WPP_SF_
0x18004bb3b  xorps   xmm0, xmm0
0x18004bb3e  movups  [rsp+160h+var_F8], xmm0
0x18004bb43  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18004bb4a  mov     [rsp+160h+pExceptionObject], rcx
0x18004bb4f  mov     dword ptr [rsp+160h+var_E8], 8020001Bh
0x18004bb57  mov     dword ptr [rsp+160h+var_E8+4], 0C57h
0x18004bb5f  mov     dword ptr [rbp+60h+var_E0], 1
0x18004bb66  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18004bb6d  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x18004bb72  call    _CxxThrowException_0
0x18004bb78  cmp     eax, 2F7Ah
0x18004bb7d  jnz     short loc_18004BBBC
0x18004bb7f  xorps   xmm0, xmm0
0x18004bb82  movups  [rsp+160h+var_F8], xmm0
0x18004bb87  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18004bb8e  mov     [rsp+160h+pExceptionObject], rcx
0x18004bb93  mov     dword ptr [rsp+160h+var_E8], 8020001Bh
0x18004bb9b  mov     dword ptr [rsp+160h+var_E8+4], 0FA5h
0x18004bba3  mov     dword ptr [rbp+60h+var_E0], 1
0x18004bbaa  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18004bbb1  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x18004bbb6  call    _CxxThrowException_0
0x18004bbbc  cmp     eax, 7Ah ; 'z'
0x18004bbbf  jz      short loc_18004BC06
0x18004bbc1  test    eax, eax
0x18004bbc3  jle     short loc_18004BBCD
0x18004bbc5  movzx   eax, ax
0x18004bbc8  or      eax, 80070000h
0x18004bbcd  xorps   xmm0, xmm0
0x18004bbd0  movups  [rsp+160h+var_F8], xmm0
0x18004bbd5  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18004bbdc  mov     [rsp+160h+pExceptionObject], rcx
0x18004bbe1  mov     dword ptr [rsp+160h+var_E8], eax
0x18004bbe5  mov     dword ptr [rsp+160h+var_E8+4], 0FAAh
0x18004bbed  mov     dword ptr [rbp+60h+var_E0], 1
0x18004bbf4  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18004bbfb  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x18004bc00  call    _CxxThrowException_0
0x18004bc06  mov     eax, [rsp+160h+var_120]
0x18004bc0a  cmp     eax, 40h ; '@'
0x18004bc0d  jbe     short loc_18004BC4C
0x18004bc0f  xorps   xmm0, xmm0
0x18004bc12  movups  [rsp+160h+var_F8], xmm0
0x18004bc17  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18004bc1e  mov     [rsp+160h+pExceptionObject], rcx
0x18004bc23  mov     dword ptr [rsp+160h+var_E8], 8020001Bh
0x18004bc2b  mov     dword ptr [rsp+160h+var_E8+4], 0FAFh
0x18004bc33  mov     dword ptr [rbp+60h+var_E0], 1
0x18004bc3a  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18004bc41  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x18004bc46  call    _CxxThrowException_0
0x18004bc4c  mov     rcx, rax
0x18004bc4f  shr     rcx, 1
0x18004bc52  mov     eax, 2
0x18004bc57  mul     rcx
0x18004bc5a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004bc61  cmovb   rax, rcx
0x18004bc65  mov     rcx, rax; dwBytes
0x18004bc68  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004bc6d  mov     rdi, rax
0x18004bc70  mov     [rsp+160h+var_110], rax
0x18004bc75  mov     rcx, [rsi]
0x18004bc78  mov     rax, [rcx+50h]
0x18004bc7c  mov     [rsp+160h+var_138], r14
0x18004bc81  lea     rcx, [rsp+160h+var_120]
0x18004bc86  mov     [rsp+160h+var_140], rcx
0x18004bc8b  mov     r9, rdi
0x18004bc8e  xor     r8d, r8d
0x18004bc91  mov     edx, 12h
0x18004bc96  mov     rcx, rsi
0x18004bc99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bc9e  test    eax, eax
0x18004bca0  jnz     short loc_18004BCFB
0x18004bca2  call    cs:__imp_GetLastError
0x18004bca8  test    eax, eax
0x18004bcaa  jg      short loc_18004BCB4
0x18004bcac  call    cs:__imp_GetLastError
0x18004bcb2  jmp     short loc_18004BCC2
0x18004bcb4  call    cs:__imp_GetLastError
0x18004bcba  movzx   eax, ax
0x18004bcbd  or      eax, 80070000h
0x18004bcc2  xorps   xmm0, xmm0
0x18004bcc5  movups  [rsp+160h+var_F8], xmm0
0x18004bcca  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18004bcd1  mov     [rsp+160h+pExceptionObject], rcx
0x18004bcd6  mov     dword ptr [rsp+160h+var_E8], eax
0x18004bcda  mov     dword ptr [rsp+160h+var_E8+4], 0FB6h
0x18004bce2  mov     dword ptr [rbp+60h+var_E0], 1
0x18004bce9  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18004bcf0  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x18004bcf5  call    _CxxThrowException_0
0x18004bcfb  mov     [rbp+60h+var_A0], rdi
0x18004bcff  lea     r9, [rsp+160h+var_118]
0x18004bd04  lea     r8, [rsp+160h+var_11C]
0x18004bd09  lea     rdx, [rbp+60h+Format]; Format
0x18004bd0d  mov     rcx, rdi; Buffer
0x18004bd10  call    swscanf
0x18004bd15  cmp     eax, 2
0x18004bd18  jz      short loc_18004BD85
0x18004bd1a  lea     rsi, WPP_GLOBAL_Control
0x18004bd21  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bd28  cmp     rcx, rsi
0x18004bd2b  jz      short loc_18004BD48
0x18004bd2d  test    byte ptr [rcx+1Ch], 4
0x18004bd31  jz      short loc_18004BD48
0x18004bd33  mov     edx, 6Dh ; 'm'
0x18004bd38  lea     r8, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids
0x18004bd3f  mov     rcx, [rcx+10h]
0x18004bd43  call    WPP_SF_
0x18004bd48  xorps   xmm0, xmm0
0x18004bd4b  movups  [rsp+160h+var_F8], xmm0
0x18004bd50  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18004bd57  mov     [rsp+160h+pExceptionObject], rcx
0x18004bd5c  mov     dword ptr [rsp+160h+var_E8], 8020001Bh
0x18004bd64  mov     dword ptr [rsp+160h+var_E8+4], 0C5Dh
0x18004bd6c  mov     dword ptr [rbp+60h+var_E0], 1
0x18004bd73  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18004bd7a  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x18004bd7f  call    _CxxThrowException_0
0x18004bd85  lea     rsi, WPP_GLOBAL_Control
0x18004bd8c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bd93  cmp     rcx, rsi
0x18004bd96  jz      short loc_18004BDCA
0x18004bd98  test    dword ptr [rcx+1Ch], 800h
0x18004bd9f  jz      short loc_18004BDCA
0x18004bda1  mov     edx, 6Eh ; 'n'
0x18004bda6  mov     eax, [rsp+160h+var_118]
0x18004bdaa  mov     dword ptr [rsp+160h+var_140], eax
0x18004bdae  mov     r9d, [rsp+160h+var_11C]
0x18004bdb3  lea     r8, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids
0x18004bdba  mov     rcx, [rcx+10h]
0x18004bdbe  call    WPP_SF_Dd
0x18004bdc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bdca  test    rdi, rdi
0x18004bdcd  jz      short loc_18004BDE3
0x18004bdcf  mov     edx, 2; unsigned __int64
0x18004bdd4  mov     rcx, rdi; void *
0x18004bdd7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004bddc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bde3  mov     r9d, [rsp+160h+var_11C]
0x18004bde8  cmp     r9d, 1
0x18004bdec  jz      short loc_18004BE53
0x18004bdee  cmp     rcx, rsi
0x18004bdf1  jz      short loc_18004BE16
0x18004bdf3  test    byte ptr [rcx+1Ch], 2
0x18004bdf7  jz      short loc_18004BE16
0x18004bdf9  mov     edx, 21h ; '!'
0x18004bdfe  mov     eax, [rsp+160h+var_118]
0x18004be02  mov     dword ptr [rsp+160h+var_140], eax
0x18004be06  lea     r8, WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids
0x18004be0d  mov     rcx, [rcx+10h]
0x18004be11  call    WPP_SF_Dd
0x18004be16  xorps   xmm0, xmm0
0x18004be19  movups  [rsp+160h+var_F8], xmm0
0x18004be1e  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18004be25  mov     [rsp+160h+pExceptionObject], rcx
0x18004be2a  mov     dword ptr [rsp+160h+var_E8], 80200012h
0x18004be32  mov     dword ptr [rsp+160h+var_E8+4], 24Dh
0x18004be3a  mov     dword ptr [rbp+60h+var_E0], 1
0x18004be41  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18004be48  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x18004be4d  call    _CxxThrowException_0
0x18004be53  mov     rcx, [rbx+298h]; struct IHttpRequest *
0x18004be5a  call    ?GetRequestStatus@@YAKPEAVIHttpRequest@@@Z; GetRequestStatus(IHttpRequest *)
0x18004be5f  cmp     qword ptr [rbx+404B0h], 0
0x18004be67  jz      loc_18004C2CD
0x18004be6d  cmp     eax, 0C8h
0x18004be72  jz      short loc_18004BE7F
0x18004be74  cmp     eax, 0CEh
0x18004be79  jnz     loc_18004C2CD
0x18004be7f  lea     rcx, [rsp+160h+pExceptionObject]; this
0x18004be84  call    ??0CSaveThreadToken@@QEAA@XZ; CSaveThreadToken::CSaveThreadToken(void)
0x18004be89  nop
0x18004be8a  mov     byte ptr [rsp+160h+var_F8], 0
0x18004be8f  mov     rax, [rbx+40488h]
0x18004be96  mov     qword ptr [rsp+160h+var_F8+8], rax
0x18004be9b  lock inc dword ptr [rax+8]
0x18004be9f  mov     [rsp+160h+var_E8], r14
0x18004bea4  mov     edx, 8; dwFlags
0x18004bea9  mov     r8d, 4; dwBytes
0x18004beaf  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18004beb6  call    cs:__imp_HeapAlloc
0x18004bebc  test    rax, rax
0x18004bebf  jnz     short loc_18004BF23
0x18004bec1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bec8  cmp     rcx, rsi
0x18004becb  jz      short loc_18004BEEE
0x18004becd  test    byte ptr [rcx+1Ch], 4
0x18004bed1  jz      short loc_18004BEEE
0x18004bed3  mov     edx, 0Ah
0x18004bed8  mov     r9d, 4
0x18004bede  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x18004bee5  mov     rcx, [rcx+10h]
0x18004bee9  call    WPP_SF_d
0x18004beee  xorps   xmm0, xmm0
0x18004bef1  movups  [rbp+60h+var_88], xmm0
0x18004bef5  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18004befc  mov     [rbp+60h+var_90], rcx
0x18004bf00  mov     [rbp+60h+var_78], 8007000Eh
0x18004bf07  mov     [rbp+60h+var_74], r14d
0x18004bf0b  mov     [rbp+60h+var_70], 1
0x18004bf12  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18004bf19  lea     rcx, [rbp+60h+var_90]; pExceptionObject
0x18004bf1d  call    _CxxThrowException_0
0x18004bf23  mov     dword ptr [rax], 1
0x18004bf29  mov     [rbp+60h+var_E0], rax
0x18004bf2d  mov     [rbp+60h+var_D8], r14
0x18004bf31  lock inc cs:dword_180145058
0x18004bf38  lea     rax, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x18004bf3f  mov     [rbp+60h+var_D0], rax
0x18004bf43  cmp     byte ptr [rsp+160h+var_F8], 0
0x18004bf48  jnz     short loc_18004BFA4
0x18004bf4a  mov     rcx, qword ptr [rsp+160h+var_F8+8]
0x18004bf4f  mov     rcx, [rcx]; hToken
0x18004bf52  call    cs:__imp_ImpersonateLoggedOnUser
0x18004bf58  test    eax, eax
0x18004bf5a  jnz     short loc_18004BF9F
0x18004bf5c  call    cs:__imp_GetLastError
0x18004bf62  test    eax, eax
0x18004bf64  jle     short loc_18004BF6E
  ... truncated ...
```
