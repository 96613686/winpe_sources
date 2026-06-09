# TS_SECURITY_FIPS_MakeSessionKeys

- ea: `0x1800c59a4`
- end: `0x1800c60fa`
- name: `TS_SECURITY_FIPS_MakeSessionKeys`
- size: `1878`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800c5050`

## callees

- `0x180004970`
- `0x180078c20`
- `0x1800c48f0`
- `0x1800c4a4c`
- `0x1800c4e10`
- `0x1800c5060`
- `0x1800c59a4`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5a8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5b3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5bdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5cd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5d8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5e35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5ed8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5fd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5a8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5b3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5bdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5cd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5d8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5e35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5ed8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5fd4`

## string_xrefs

- `0x1800c5aaf`: `onecore\termsrv\rdpplatform\common\pal\win32\security\tssecurity.cpp`
- `0x1800c5b5d`: `onecore\termsrv\rdpplatform\common\pal\win32\security\tssecurity.cpp`
- `0x1800c5c01`: `onecore\termsrv\rdpplatform\common\pal\win32\security\tssecurity.cpp`
- `0x1800c5cf6`: `onecore\termsrv\rdpplatform\common\pal\win32\security\tssecurity.cpp`
- `0x1800c5db1`: `onecore\termsrv\rdpplatform\common\pal\win32\security\tssecurity.cpp`
- `0x1800c5e57`: `onecore\termsrv\rdpplatform\common\pal\win32\security\tssecurity.cpp`
- `0x1800c5efa`: `onecore\termsrv\rdpplatform\common\pal\win32\security\tssecurity.cpp`
- `0x1800c5ff6`: `onecore\termsrv\rdpplatform\common\pal\win32\security\tssecurity.cpp`
- `0x1800c5aa4`: `TS_SECURITY_FIPS_MakeSessionKeys`
- `0x1800c5b52`: `TS_SECURITY_FIPS_MakeSessionKeys`
- `0x1800c5bf6`: `TS_SECURITY_FIPS_MakeSessionKeys`
- `0x1800c5ceb`: `TS_SECURITY_FIPS_MakeSessionKeys`
- `0x1800c5da6`: `TS_SECURITY_FIPS_MakeSessionKeys`
- `0x1800c5e4c`: `TS_SECURITY_FIPS_MakeSessionKeys`
- `0x1800c5eef`: `TS_SECURITY_FIPS_MakeSessionKeys`
- `0x1800c5feb`: `TS_SECURITY_FIPS_MakeSessionKeys`
- `0x1800c5aba`: `CryptCreateHash failed with %u`
- `0x1800c5dbc`: `CryptCreateHash failed with %u`
- `0x1800c5d01`: `Error %x during CryptSetKeyParam!`
- `0x1800c6001`: `Error %x during CryptSetKeyParam!`

## pseudocode

```c
__int64 __fastcall TS_SECURITY_FIPS_MakeSessionKeys(__int64 a1, __int64 a2, _DWORD *a3, int a4)
{
  unsigned int v4; // r14d
  __int64 v8; // r12
  __int64 v9; // r15
  __int64 v10; // rdi
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  unsigned int v17; // r9d
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  unsigned __int64 v21; // rdx
  unsigned __int64 *v22; // r15
  DWORD v23; // eax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  DWORD LastError; // eax
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  DWORD v31; // eax
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  unsigned int v35; // r9d
  DWORD v36; // eax
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  unsigned __int64 v40; // rdx
  const char *v41; // r15
  unsigned int v42; // r9d
  DWORD v43; // eax
  int v44; // ecx
  int v45; // r8d
  int v46; // r9d
  unsigned int v47; // r9d
  unsigned int v49; // [rsp+28h] [rbp-71h]
  unsigned int v50; // [rsp+50h] [rbp-49h] BYREF
  int v51; // [rsp+54h] [rbp-45h] BYREF
  DWORD v52; // [rsp+58h] [rbp-41h] BYREF
  const char *v53; // [rsp+60h] [rbp-39h] BYREF
  const char *v54; // [rsp+68h] [rbp-31h] BYREF
  const char *v55; // [rsp+70h] [rbp-29h] BYREF
  unsigned int v56[2]; // [rsp+78h] [rbp-21h] BYREF
  unsigned __int8 v57[16]; // [rsp+80h] [rbp-19h] BYREF
  int v58; // [rsp+90h] [rbp-9h]
  unsigned __int8 v59[16]; // [rsp+98h] [rbp-1h] BYREF
  int v60; // [rsp+A8h] [rbp+Fh]

  v4 = 0;
  v58 = 0;
  v60 = 0;
  *(_QWORD *)v56 = 0;
  v53 = (const char *)((-(__int64)(a4 != 0) & 0xFFFFFFFFFFFFFFE0uLL) + 160);
  *(_OWORD *)v57 = 0;
  v54 = (const char *)((-(__int64)(a4 != 0) & 0xFFFFFFFFFFFFFFE0uLL) + 152);
  *(_OWORD *)v59 = 0;
  v8 = a4 != 0 ? 160LL : 128LL;
  v9 = a4 != 0 ? 152LL : 120LL;
  if ( a3 && *a3 )
  {
    v10 = a1 + 8;
    goto LABEL_20;
  }
  v10 = a1 + 8;
  if ( (*(unsigned int (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(a1 + 72))(*(_QWORD *)(a1 + 112), 32772, 0, 0) )
  {
    if ( (*(unsigned int (__fastcall **)(_QWORD, __int64, __int64))(a1 + 80))(*(_QWORD *)v56, a2 + 16, 16) )
    {
      if ( (*(unsigned int (__fastcall **)(_QWORD, __int64, __int64))(a1 + 80))(*(_QWORD *)v56, a2 + 48, 16) )
      {
        if ( !(unsigned int)DumpHashes((struct _CAPI_FUNCTION_TABLE *)v10, (unsigned __int64 *)v56, v57, v17) )
          return v4;
        v21 = *(_QWORD *)(a1 + 112);
        v22 = (unsigned __int64 *)(a1 + v9);
        v50 = 24;
        if ( !(unsigned int)TS_SECURITY_FIPS_DeriveKey(
                              (struct _CAPI_FUNCTION_TABLE *)v10,
                              v21,
                              v22,
                              v57,
                              (unsigned int)v56,
                              (unsigned __int8 *)(v8 + a1),
                              &v50) )
          return v4;
        if ( (*(unsigned int (__fastcall **)(unsigned __int64, __int64, unsigned __int8 near **))(a1 + 64))(
               *v22,
               1,
               &rgbIV) )
        {
          if ( !a3 )
          {
LABEL_21:
            if ( !(*(unsigned int (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(v10 + 64))(
                    *(_QWORD *)(a1 + 112),
                    32772,
                    0,
                    0) )
            {
              if ( (unsigned int)CallbackContext > 2 )
              {
                LastError = GetLastError();
                v51 = 987;
                v52 = LastError;
                v54 = "TS_SECURITY_FIPS_MakeSessionKeys";
                v53 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\security\\tssecurity.cpp";
                v55 = "CryptCreateHash failed with %u";
                v50 = -2147467259;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                  v28,
                  (unsigned int)qword_1801B86A0,
                  v29,
                  v30,
                  (__int64)&v55,
                  (__int64)&v50,
                  (__int64)&v53,
                  (__int64)&v51,
                  (__int64)&v54,
                  (__int64)&v52);
              }
              return v4;
            }
            if ( !(*(unsigned int (__fastcall **)(_QWORD, __int64, __int64))(a1 + 80))(*(_QWORD *)v56, a2, 16) )
            {
              if ( (unsigned int)CallbackContext > 2 )
              {
                v31 = GetLastError();
                v51 = 991;
                v52 = v31;
                v54 = "TS_SECURITY_FIPS_MakeSessionKeys";
                v53 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\security\\tssecurity.cpp";
                v55 = "CryptHashData failed with %u";
                v50 = -2147467259;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                  v32,
                  (unsigned int)byte_1801B864B,
                  v33,
                  v34,
                  (__int64)&v55,
                  (__int64)&v50,
                  (__int64)&v53,
                  (__int64)&v51,
                  (__int64)&v54,
                  (__int64)&v52);
              }
              return v4;
            }
            if ( !(*(unsigned int (__fastcall **)(_QWORD, __int64, __int64, _QWORD))(a1 + 80))(
                    *(_QWORD *)v56,
                    a2 + 32,
                    16,
                    0) )
            {
              if ( (unsigned int)CallbackContext > 2 )
              {
                v36 = GetLastError();
                v51 = 995;
                v52 = v36;
                v54 = "TS_SECURITY_FIPS_MakeSessionKeys";
                v53 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\security\\tssecurity.cpp";
                v55 = "CryptHashData failed with %u";
                v50 = -2147467259;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                  v37,
                  (unsigned int)&word_1801B85F6,
                  v38,
                  v39,
                  (__int64)&v55,
                  (__int64)&v50,
                  (__int64)&v53,
                  (__int64)&v51,
                  (__int64)&v54,
                  (__int64)&v52);
              }
              return v4;
            }
            if ( !(unsigned int)DumpHashes((struct _CAPI_FUNCTION_TABLE *)v10, (unsigned __int64 *)v56, v59, v35) )
              return v4;
            v40 = *(_QWORD *)(a1 + 112);
            v41 = &v54[a1];
            v50 = 24;
            if ( !(unsigned int)TS_SECURITY_FIPS_DeriveKey(
                                  (struct _CAPI_FUNCTION_TABLE *)v10,
                                  v40,
                                  (unsigned __int64 *)&v54[a1],
                                  v59,
                                  (unsigned int)v56,
                                  (unsigned __int8 *)&v53[a1],
                                  &v50) )
              return v4;
            if ( !(*(unsigned int (__fastcall **)(_QWORD, __int64, unsigned __int8 near **))(a1 + 64))(
                    *(_QWORD *)v41,
                    1,
                    &rgbIV) )
            {
              if ( (unsigned int)CallbackContext > 2 )
              {
                v43 = GetLastError();
                v51 = 1012;
                v52 = v43;
                v54 = "TS_SECURITY_FIPS_MakeSessionKeys";
                v53 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\security\\tssecurity.cpp";
                v55 = "Error %x during CryptSetKeyParam!";
                v50 = -2147467259;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                  v44,
                  (unsigned int)byte_1801B85A1,
                  v45,
                  v46,
                  (__int64)&v55,
                  (__int64)&v50,
                  (__int64)&v53,
                  (__int64)&v51,
                  (__int64)&v54,
                  (__int64)&v52);
              }
              return v4;
            }
            if ( !a3 )
            {
              if ( !(unsigned int)HashDataEx(
                                    (struct _CAPI_FUNCTION_TABLE *)(a1 + 8),
                                    *(_QWORD *)(a1 + 112),
                                    v59,
                                    v42,
                                    v57,
                                    v49,
                                    (unsigned __int64 *)v56) )
                return v4;
              if ( !(unsigned int)DumpHashes(
                                    (struct _CAPI_FUNCTION_TABLE *)(a1 + 8),
                                    (unsigned __int64 *)v56,
                                    (unsigned __int8 *)(a1 + 208),
                                    v47) )
                return v4;
              v4 = ImportKey(
                     (struct _CAPI_FUNCTION_TABLE *)(a1 + 8),
                     *(_QWORD *)(a1 + 112),
                     0x6602u,
                     (unsigned __int8 *)(a1 + 208),
                     0x14u,
                     0x100u,
                     (unsigned __int64 *)(a1 + 200));
              if ( !v4 )
                return v4;
            }
            return 1;
          }
LABEL_20:
          if ( *a3 != 1 )
            return 1;
          goto LABEL_21;
        }
        if ( (unsigned int)CallbackContext > 2 )
        {
          v23 = GetLastError();
          v51 = 976;
          v52 = v23;
          v54 = "TS_SECURITY_FIPS_MakeSessionKeys";
          v53 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\security\\tssecurity.cpp";
          v55 = "Error %x during CryptSetKeyParam!";
          v50 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v24,
            (unsigned int)byte_1801B86F5,
            v25,
            v26,
            (__int64)&v55,
            (__int64)&v50,
            (__int64)&v53,
            (__int64)&v51,
            (__int64)&v54,
            (__int64)&v52);
        }
      }
      else if ( (unsigned int)CallbackContext > 2 )
      {
        v51 = 959;
        v52 = GetLastError();
        v54 = "TS_SECURITY_FIPS_MakeSessionKeys";
        v53 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\security\\tssecurity.cpp";
        v55 = "CryptHashData failed with %u";
        v50 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v18,
          (unsigned int)word_1801B874A,
          v19,
          v20,
          (__int64)&v55,
          (__int64)&v50,
          (__int64)&v53,
          (__int64)&v51,
          (__int64)&v54,
          (__int64)&v52);
      }
    }
    else if ( (unsigned int)CallbackContext > 2 )
    {
      v51 = 955;
      v52 = GetLastError();
      v54 = "TS_SECURITY_FIPS_MakeSessionKeys";
      v53 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\security\\tssecurity.cpp";
      v55 = "CryptHashData failed with %u";
      v50 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v14,
        (unsigned int)&byte_1801B879F,
        v15,
        v16,
        (__int64)&v55,
        (__int64)&v50,
        (__int64)&v53,
        (__int64)&v51,
        (__int64)&v54,
        (__int64)&v52);
    }
  }
  else if ( (unsigned int)CallbackContext > 2 )
  {
    v51 = 951;
    v50 = GetLastError();
    v55 = "TS_SECURITY_FIPS_MakeSessionKeys";
    v53 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\security\\tssecurity.cpp";
    v54 = "CryptCreateHash failed with %u";
    v52 = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v11,
      (unsigned int)&dword_1801B87F4,
      v12,
      v13,
      (__int64)&v54,
      (__int64)&v52,
      (__int64)&v53,
      (__int64)&v51,
      (__int64)&v55,
      (__int64)&v50);
  }
  return v4;
}

```

## disassembly

```asm
0x1800c59a4  mov     [rsp-8+arg_10], rbx
0x1800c59a9  push    rbp
0x1800c59aa  push    rsi
0x1800c59ab  push    rdi
0x1800c59ac  push    r12
0x1800c59ae  push    r13
0x1800c59b0  push    r14
0x1800c59b2  push    r15
0x1800c59b4  lea     rbp, [rsp-27h]
0x1800c59b9  sub     rsp, 0C0h
0x1800c59c0  mov     rax, cs:__security_cookie
0x1800c59c7  xor     rax, rsp
0x1800c59ca  mov     [rbp+57h+var_40], rax
0x1800c59ce  xor     eax, eax
0x1800c59d0  xor     r14d, r14d
0x1800c59d3  mov     [rbp+57h+var_60], eax
0x1800c59d6  xorps   xmm0, xmm0
0x1800c59d9  mov     [rbp+57h+var_48], eax
0x1800c59dc  xorps   xmm1, xmm1
0x1800c59df  mov     eax, r9d
0x1800c59e2  mov     qword ptr [rbp+57h+var_78], r14
0x1800c59e6  neg     eax
0x1800c59e8  mov     rsi, r8
0x1800c59eb  mov     r13, rdx
0x1800c59ee  mov     rbx, rcx
0x1800c59f1  sbb     rax, rax
0x1800c59f4  and     rax, 0FFFFFFFFFFFFFFE0h
0x1800c59f8  add     rax, 0A0h
0x1800c59fe  mov     [rbp+57h+var_90], rax
0x1800c5a02  mov     eax, r9d
0x1800c5a05  neg     eax
0x1800c5a07  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x1800c5a0b  sbb     rax, rax
0x1800c5a0e  and     rax, 0FFFFFFFFFFFFFFE0h
0x1800c5a12  add     rax, 98h
0x1800c5a18  mov     [rbp+57h+var_88], rax
0x1800c5a1c  mov     eax, r9d
0x1800c5a1f  neg     eax
0x1800c5a21  movups  xmmword ptr [rbp+57h+var_58], xmm1
0x1800c5a25  sbb     r12, r12
0x1800c5a28  and     r12d, 20h
0x1800c5a2c  sub     r12, 0FFFFFFFFFFFFFF80h
0x1800c5a30  neg     r9d
0x1800c5a33  sbb     r15, r15
0x1800c5a36  and     r15d, 20h
0x1800c5a3a  add     r15, 78h ; 'x'
0x1800c5a3e  test    r8, r8
0x1800c5a41  jz      short loc_1800C5A51
0x1800c5a43  cmp     [r8], r14d
0x1800c5a46  jz      short loc_1800C5A51
0x1800c5a48  lea     rdi, [rcx+8]
0x1800c5a4c  jmp     loc_1800C5D4E
0x1800c5a51  lea     rdi, [rcx+8]
0x1800c5a55  xor     r9d, r9d
0x1800c5a58  mov     rcx, [rcx+70h]
0x1800c5a5c  lea     rax, [rbp+57h+var_78]
0x1800c5a60  mov     [rsp+0F0h+var_D0], rax; unsigned int
0x1800c5a65  xor     r8d, r8d
0x1800c5a68  mov     rax, [rdi+40h]
0x1800c5a6c  mov     edx, 8004h
0x1800c5a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5a76  test    eax, eax
0x1800c5a78  jnz     loc_1800C5B0C
0x1800c5a7e  mov     eax, cs:CallbackContext
0x1800c5a84  cmp     eax, 2
0x1800c5a87  jbe     loc_1800C60D0
0x1800c5a8d  call    cs:__imp_GetLastError
0x1800c5a93  mov     [rbp+57h+var_9C], 3B7h
0x1800c5a9a  lea     rdx, dword_1801B87F4
0x1800c5aa1  mov     [rbp+57h+var_A0], eax
0x1800c5aa4  lea     rax, aTsSecurityFips_1; "TS_SECURITY_FIPS_MakeSessionKeys"
0x1800c5aab  mov     [rbp+57h+var_80], rax
0x1800c5aaf  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800c5ab6  mov     [rbp+57h+var_90], rax
0x1800c5aba  lea     rax, aCryptcreatehas_0; "CryptCreateHash failed with %u"
0x1800c5ac1  mov     [rbp+57h+var_88], rax
0x1800c5ac5  lea     rax, [rbp+57h+var_A0]
0x1800c5ac9  mov     [rsp+0F0h+var_A8], rax
0x1800c5ace  lea     rax, [rbp+57h+var_80]
0x1800c5ad2  mov     [rsp+0F0h+var_B0], rax
0x1800c5ad7  lea     rax, [rbp+57h+var_9C]
0x1800c5adb  mov     [rsp+0F0h+var_B8], rax
0x1800c5ae0  lea     rax, [rbp+57h+var_90]
0x1800c5ae4  mov     [rsp+0F0h+var_C0], rax
0x1800c5ae9  lea     rax, [rbp+57h+var_98]
0x1800c5aed  mov     [rsp+0F0h+var_C8], rax
0x1800c5af2  lea     rax, [rbp+57h+var_88]
0x1800c5af6  mov     [rbp+57h+var_98], 80004005h
0x1800c5afd  mov     [rsp+0F0h+var_D0], rax
0x1800c5b02  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800c5b07  jmp     loc_1800C60D0
0x1800c5b0c  mov     rcx, qword ptr [rbp+57h+var_78]
0x1800c5b10  lea     rdx, [r13+10h]
0x1800c5b14  mov     rax, [rbx+50h]
0x1800c5b18  xor     r9d, r9d
0x1800c5b1b  lea     r8d, [r9+10h]
0x1800c5b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5b24  test    eax, eax
0x1800c5b26  jnz     loc_1800C5BB0
0x1800c5b2c  mov     eax, cs:CallbackContext
0x1800c5b32  cmp     eax, 2
0x1800c5b35  jbe     loc_1800C60D0
0x1800c5b3b  call    cs:__imp_GetLastError
0x1800c5b41  mov     [rbp+57h+var_9C], 3BBh
0x1800c5b48  lea     rdx, byte_1801B879F
0x1800c5b4f  mov     [rbp+57h+var_98], eax
0x1800c5b52  lea     rax, aTsSecurityFips_1; "TS_SECURITY_FIPS_MakeSessionKeys"
0x1800c5b59  mov     [rbp+57h+var_88], rax
0x1800c5b5d  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800c5b64  mov     [rbp+57h+var_90], rax
0x1800c5b68  lea     rax, aCrypthashdataF; "CryptHashData failed with %u"
0x1800c5b6f  mov     [rbp+57h+var_80], rax
0x1800c5b73  lea     rax, [rbp+57h+var_98]
0x1800c5b77  mov     [rsp+0F0h+var_A8], rax
0x1800c5b7c  lea     rax, [rbp+57h+var_88]
0x1800c5b80  mov     [rsp+0F0h+var_B0], rax
0x1800c5b85  lea     rax, [rbp+57h+var_9C]
0x1800c5b89  mov     [rsp+0F0h+var_B8], rax
0x1800c5b8e  lea     rax, [rbp+57h+var_90]
0x1800c5b92  mov     [rsp+0F0h+var_C0], rax
0x1800c5b97  lea     rax, [rbp+57h+var_A0]
0x1800c5b9b  mov     [rsp+0F0h+var_C8], rax
0x1800c5ba0  lea     rax, [rbp+57h+var_80]
0x1800c5ba4  mov     [rbp+57h+var_A0], 80004005h
0x1800c5bab  jmp     loc_1800C5AFD
0x1800c5bb0  mov     rcx, qword ptr [rbp+57h+var_78]
0x1800c5bb4  lea     rdx, [r13+30h]
0x1800c5bb8  mov     rax, [rbx+50h]
0x1800c5bbc  xor     r9d, r9d
0x1800c5bbf  lea     r8d, [r9+10h]
0x1800c5bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5bc8  test    eax, eax
0x1800c5bca  jnz     loc_1800C5C54
0x1800c5bd0  mov     eax, cs:CallbackContext
0x1800c5bd6  cmp     eax, 2
0x1800c5bd9  jbe     loc_1800C60D0
0x1800c5bdf  call    cs:__imp_GetLastError
0x1800c5be5  mov     [rbp+57h+var_9C], 3BFh
0x1800c5bec  lea     rdx, word_1801B874A
0x1800c5bf3  mov     [rbp+57h+var_98], eax
0x1800c5bf6  lea     rax, aTsSecurityFips_1; "TS_SECURITY_FIPS_MakeSessionKeys"
0x1800c5bfd  mov     [rbp+57h+var_88], rax
0x1800c5c01  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800c5c08  mov     [rbp+57h+var_90], rax
0x1800c5c0c  lea     rax, aCrypthashdataF; "CryptHashData failed with %u"
0x1800c5c13  mov     [rbp+57h+var_80], rax
0x1800c5c17  lea     rax, [rbp+57h+var_98]
0x1800c5c1b  mov     [rsp+0F0h+var_A8], rax
0x1800c5c20  lea     rax, [rbp+57h+var_88]
0x1800c5c24  mov     [rsp+0F0h+var_B0], rax
0x1800c5c29  lea     rax, [rbp+57h+var_9C]
0x1800c5c2d  mov     [rsp+0F0h+var_B8], rax
0x1800c5c32  lea     rax, [rbp+57h+var_90]
0x1800c5c36  mov     [rsp+0F0h+var_C0], rax
0x1800c5c3b  lea     rax, [rbp+57h+var_A0]
0x1800c5c3f  mov     [rsp+0F0h+var_C8], rax
0x1800c5c44  lea     rax, [rbp+57h+var_80]
0x1800c5c48  mov     [rbp+57h+var_A0], 80004005h
0x1800c5c4f  jmp     loc_1800C5AFD
0x1800c5c54  lea     r8, [rbp+57h+var_70]; unsigned __int8 *
0x1800c5c58  mov     rcx, rdi; struct _CAPI_FUNCTION_TABLE *
0x1800c5c5b  lea     rdx, [rbp+57h+var_78]; unsigned __int64 *
0x1800c5c5f  call    ?DumpHashes@@YAHPEAU_CAPI_FUNCTION_TABLE@@PEA_KPEAEK@Z; DumpHashes(_CAPI_FUNCTION_TABLE *,unsigned __int64 *,uchar *,ulong)
0x1800c5c64  test    eax, eax
0x1800c5c66  jz      loc_1800C60D0
0x1800c5c6c  mov     rdx, [rbx+70h]; unsigned __int64
0x1800c5c70  lea     rcx, [rbp+57h+var_A0]
0x1800c5c74  mov     [rsp+0F0h+var_C0], rcx; unsigned int *
0x1800c5c79  lea     rax, [r12+rbx]
0x1800c5c7d  add     r15, rbx
0x1800c5c80  mov     [rbp+57h+var_A0], 18h
0x1800c5c87  mov     rcx, rdi; struct _CAPI_FUNCTION_TABLE *
0x1800c5c8a  mov     [rsp+0F0h+var_C8], rax; unsigned __int8 *
0x1800c5c8f  lea     r9, [rbp+57h+var_70]; unsigned __int8 *
0x1800c5c93  mov     r8, r15; unsigned __int64 *
0x1800c5c96  call    ?TS_SECURITY_FIPS_DeriveKey@@YAHPEAU_CAPI_FUNCTION_TABLE@@_KPEA_KPEAEK3PEAK@Z; TS_SECURITY_FIPS_DeriveKey(_CAPI_FUNCTION_TABLE *,unsigned __int64,unsigned __int64 *,uchar *,ulong,uchar *,ulong *)
0x1800c5c9b  test    eax, eax
0x1800c5c9d  jz      loc_1800C60D0
0x1800c5ca3  mov     rcx, [r15]
0x1800c5ca6  lea     r8, ?rgbIV@@3PAEA; uchar near * rgbIV
0x1800c5cad  mov     rax, [rbx+40h]
0x1800c5cb1  xor     r9d, r9d
0x1800c5cb4  lea     edx, [r9+1]
0x1800c5cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5cbd  test    eax, eax
0x1800c5cbf  jnz     loc_1800C5D49
0x1800c5cc5  mov     eax, cs:CallbackContext
0x1800c5ccb  cmp     eax, 2
0x1800c5cce  jbe     loc_1800C60D0
0x1800c5cd4  call    cs:__imp_GetLastError
0x1800c5cda  mov     [rbp+57h+var_9C], 3D0h
0x1800c5ce1  lea     rdx, byte_1801B86F5
0x1800c5ce8  mov     [rbp+57h+var_98], eax
0x1800c5ceb  lea     rax, aTsSecurityFips_1; "TS_SECURITY_FIPS_MakeSessionKeys"
0x1800c5cf2  mov     [rbp+57h+var_88], rax
0x1800c5cf6  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800c5cfd  mov     [rbp+57h+var_90], rax
0x1800c5d01  lea     rax, aErrorXDuringCr_3; "Error %x during CryptSetKeyParam!"
0x1800c5d08  mov     [rbp+57h+var_80], rax
0x1800c5d0c  lea     rax, [rbp+57h+var_98]
0x1800c5d10  mov     [rsp+0F0h+var_A8], rax
0x1800c5d15  lea     rax, [rbp+57h+var_88]
0x1800c5d19  mov     [rsp+0F0h+var_B0], rax
0x1800c5d1e  lea     rax, [rbp+57h+var_9C]
0x1800c5d22  mov     [rsp+0F0h+var_B8], rax
0x1800c5d27  lea     rax, [rbp+57h+var_90]
0x1800c5d2b  mov     [rsp+0F0h+var_C0], rax
0x1800c5d30  lea     rax, [rbp+57h+var_A0]
0x1800c5d34  mov     [rsp+0F0h+var_C8], rax
0x1800c5d39  lea     rax, [rbp+57h+var_80]
0x1800c5d3d  mov     [rbp+57h+var_A0], 80004005h
0x1800c5d44  jmp     loc_1800C5AFD
0x1800c5d49  test    rsi, rsi
0x1800c5d4c  jz      short loc_1800C5D57
0x1800c5d4e  cmp     dword ptr [rsi], 1
0x1800c5d51  jnz     loc_1800C60CA
0x1800c5d57  mov     rcx, [rbx+70h]
0x1800c5d5b  lea     rax, [rbp+57h+var_78]
0x1800c5d5f  mov     [rsp+0F0h+var_D0], rax; unsigned int
0x1800c5d64  xor     r9d, r9d
0x1800c5d67  mov     rax, [rdi+40h]
0x1800c5d6b  xor     r8d, r8d
0x1800c5d6e  mov     edx, 8004h
0x1800c5d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5d78  test    eax, eax
0x1800c5d7a  jnz     loc_1800C5E04
0x1800c5d80  mov     eax, cs:CallbackContext
0x1800c5d86  cmp     eax, 2
0x1800c5d89  jbe     loc_1800C60D0
0x1800c5d8f  call    cs:__imp_GetLastError
0x1800c5d95  mov     [rbp+57h+var_9C], 3DBh
0x1800c5d9c  lea     rdx, qword_1801B86A0
0x1800c5da3  mov     [rbp+57h+var_98], eax
0x1800c5da6  lea     rax, aTsSecurityFips_1; "TS_SECURITY_FIPS_MakeSessionKeys"
0x1800c5dad  mov     [rbp+57h+var_88], rax
0x1800c5db1  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800c5db8  mov     [rbp+57h+var_90], rax
0x1800c5dbc  lea     rax, aCryptcreatehas_0; "CryptCreateHash failed with %u"
0x1800c5dc3  mov     [rbp+57h+var_80], rax
0x1800c5dc7  lea     rax, [rbp+57h+var_98]
0x1800c5dcb  mov     [rsp+0F0h+var_A8], rax
0x1800c5dd0  lea     rax, [rbp+57h+var_88]
0x1800c5dd4  mov     [rsp+0F0h+var_B0], rax
0x1800c5dd9  lea     rax, [rbp+57h+var_9C]
0x1800c5ddd  mov     [rsp+0F0h+var_B8], rax
0x1800c5de2  lea     rax, [rbp+57h+var_90]
0x1800c5de6  mov     [rsp+0F0h+var_C0], rax
0x1800c5deb  lea     rax, [rbp+57h+var_A0]
0x1800c5def  mov     [rsp+0F0h+var_C8], rax
0x1800c5df4  lea     rax, [rbp+57h+var_80]
0x1800c5df8  mov     [rbp+57h+var_A0], 80004005h
0x1800c5dff  jmp     loc_1800C5AFD
0x1800c5e04  mov     rcx, qword ptr [rbp+57h+var_78]
0x1800c5e08  xor     r9d, r9d
0x1800c5e0b  mov     rax, [rbx+50h]
0x1800c5e0f  mov     rdx, r13
0x1800c5e12  lea     r15d, [r9+10h]
0x1800c5e16  mov     r8d, r15d
0x1800c5e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5e1e  test    eax, eax
0x1800c5e20  jnz     loc_1800C5EAA
0x1800c5e26  mov     eax, cs:CallbackContext
0x1800c5e2c  cmp     eax, 2
0x1800c5e2f  jbe     loc_1800C60D0
0x1800c5e35  call    cs:__imp_GetLastError
0x1800c5e3b  mov     [rbp+57h+var_9C], 3DFh
0x1800c5e42  lea     rdx, byte_1801B864B
0x1800c5e49  mov     [rbp+57h+var_98], eax
0x1800c5e4c  lea     rax, aTsSecurityFips_1; "TS_SECURITY_FIPS_MakeSessionKeys"
0x1800c5e53  mov     [rbp+57h+var_88], rax
0x1800c5e57  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800c5e5e  mov     [rbp+57h+var_90], rax
0x1800c5e62  lea     rax, aCrypthashdataF; "CryptHashData failed with %u"
0x1800c5e69  mov     [rbp+57h+var_80], rax
0x1800c5e6d  lea     rax, [rbp+57h+var_98]
0x1800c5e71  mov     [rsp+0F0h+var_A8], rax
0x1800c5e76  lea     rax, [rbp+57h+var_88]
0x1800c5e7a  mov     [rsp+0F0h+var_B0], rax
0x1800c5e7f  lea     rax, [rbp+57h+var_9C]
0x1800c5e83  mov     [rsp+0F0h+var_B8], rax
0x1800c5e88  lea     rax, [rbp+57h+var_90]
0x1800c5e8c  mov     [rsp+0F0h+var_C0], rax
0x1800c5e91  lea     rax, [rbp+57h+var_A0]
0x1800c5e95  mov     [rsp+0F0h+var_C8], rax
0x1800c5e9a  lea     rax, [rbp+57h+var_80]
0x1800c5e9e  mov     [rbp+57h+var_A0], 80004005h
0x1800c5ea5  jmp     loc_1800C5AFD
0x1800c5eaa  mov     rcx, qword ptr [rbp+57h+var_78]
0x1800c5eae  lea     rdx, [r13+20h]
0x1800c5eb2  mov     rax, [rbx+50h]
0x1800c5eb6  xor     r9d, r9d
0x1800c5eb9  mov     r8d, r15d
0x1800c5ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5ec1  test    eax, eax
0x1800c5ec3  jnz     loc_1800C5F4D
0x1800c5ec9  mov     eax, cs:CallbackContext
0x1800c5ecf  cmp     eax, 2
0x1800c5ed2  jbe     loc_1800C60D0
0x1800c5ed8  call    cs:__imp_GetLastError
0x1800c5ede  mov     [rbp+57h+var_9C], 3E3h
  ... truncated ...
```
