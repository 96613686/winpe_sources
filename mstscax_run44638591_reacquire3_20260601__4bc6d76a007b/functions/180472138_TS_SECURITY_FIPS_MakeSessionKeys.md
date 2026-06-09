# TS_SECURITY_FIPS_MakeSessionKeys

- ea: `0x180472138`
- end: `0x18047288e`
- name: `TS_SECURITY_FIPS_MakeSessionKeys`
- size: `1878`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18016c150`

## callees

- `0x180001e8c`
- `0x180470f78`
- `0x18047108c`
- `0x180471454`
- `0x180471694`
- `0x180472138`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180472221`
- `KERNEL32!GetLastError` at `0x1804722cf`
- `KERNEL32!GetLastError` at `0x180472373`
- `KERNEL32!GetLastError` at `0x180472468`
- `KERNEL32!GetLastError` at `0x180472523`
- `KERNEL32!GetLastError` at `0x1804725c9`
- `KERNEL32!GetLastError` at `0x18047266c`
- `KERNEL32!GetLastError` at `0x180472768`
- `KERNEL32!GetLastError` at `0x180472221`
- `KERNEL32!GetLastError` at `0x1804722cf`
- `KERNEL32!GetLastError` at `0x180472373`
- `KERNEL32!GetLastError` at `0x180472468`
- `KERNEL32!GetLastError` at `0x180472523`
- `KERNEL32!GetLastError` at `0x1804725c9`
- `KERNEL32!GetLastError` at `0x18047266c`
- `KERNEL32!GetLastError` at `0x180472768`

## string_xrefs

- `0x180472243`: `onecore\termsrv\rdpplatform\common\pal\win32\security\tssecurity.cpp`
- `0x1804722f1`: `onecore\termsrv\rdpplatform\common\pal\win32\security\tssecurity.cpp`
- `0x180472395`: `onecore\termsrv\rdpplatform\common\pal\win32\security\tssecurity.cpp`
- `0x18047248a`: `onecore\termsrv\rdpplatform\common\pal\win32\security\tssecurity.cpp`
- `0x180472545`: `onecore\termsrv\rdpplatform\common\pal\win32\security\tssecurity.cpp`
- `0x1804725eb`: `onecore\termsrv\rdpplatform\common\pal\win32\security\tssecurity.cpp`
- `0x18047268e`: `onecore\termsrv\rdpplatform\common\pal\win32\security\tssecurity.cpp`
- `0x18047278a`: `onecore\termsrv\rdpplatform\common\pal\win32\security\tssecurity.cpp`
- `0x18047224e`: `CryptCreateHash failed with %u`
- `0x180472550`: `CryptCreateHash failed with %u`
- `0x180472238`: `TS_SECURITY_FIPS_MakeSessionKeys`
- `0x1804722e6`: `TS_SECURITY_FIPS_MakeSessionKeys`
- `0x18047238a`: `TS_SECURITY_FIPS_MakeSessionKeys`
- `0x18047247f`: `TS_SECURITY_FIPS_MakeSessionKeys`
- `0x18047253a`: `TS_SECURITY_FIPS_MakeSessionKeys`
- `0x1804725e0`: `TS_SECURITY_FIPS_MakeSessionKeys`
- `0x180472683`: `TS_SECURITY_FIPS_MakeSessionKeys`
- `0x18047277f`: `TS_SECURITY_FIPS_MakeSessionKeys`
- `0x180472495`: `Error %x during CryptSetKeyParam!`
- `0x180472795`: `Error %x during CryptSetKeyParam!`

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
              if ( (unsigned int)dword_1808B5850 > 2 )
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
                  (unsigned int)qword_180884748,
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
              if ( (unsigned int)dword_1808B5850 > 2 )
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
                  (unsigned int)byte_1808846F3,
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
              if ( (unsigned int)dword_1808B5850 > 2 )
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
                  (unsigned int)qword_180884370,
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
              if ( (unsigned int)dword_1808B5850 > 2 )
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
                  (unsigned int)byte_18088431B,
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
        if ( (unsigned int)dword_1808B5850 > 2 )
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
            (unsigned int)byte_180884649,
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
      else if ( (unsigned int)dword_1808B5850 > 2 )
      {
        v51 = 959;
        v52 = GetLastError();
        v54 = "TS_SECURITY_FIPS_MakeSessionKeys";
        v53 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\security\\tssecurity.cpp";
        v55 = "CryptHashData failed with %u";
        v50 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v18,
          (unsigned int)&word_18088469E,
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
    else if ( (unsigned int)dword_1808B5850 > 2 )
    {
      v51 = 955;
      v52 = GetLastError();
      v54 = "TS_SECURITY_FIPS_MakeSessionKeys";
      v53 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\security\\tssecurity.cpp";
      v55 = "CryptHashData failed with %u";
      v50 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v14,
        (unsigned int)&byte_18088459F,
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
  else if ( (unsigned int)dword_1808B5850 > 2 )
  {
    v51 = 951;
    v50 = GetLastError();
    v55 = "TS_SECURITY_FIPS_MakeSessionKeys";
    v53 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\security\\tssecurity.cpp";
    v54 = "CryptCreateHash failed with %u";
    v52 = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v11,
      (unsigned int)&dword_1808845F4,
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
0x180472138  mov     [rsp-8+arg_10], rbx
0x18047213d  push    rbp
0x18047213e  push    rsi
0x18047213f  push    rdi
0x180472140  push    r12
0x180472142  push    r13
0x180472144  push    r14
0x180472146  push    r15
0x180472148  lea     rbp, [rsp-27h]
0x18047214d  sub     rsp, 0C0h
0x180472154  mov     rax, cs:__security_cookie
0x18047215b  xor     rax, rsp
0x18047215e  mov     [rbp+57h+var_40], rax
0x180472162  xor     eax, eax
0x180472164  xor     r14d, r14d
0x180472167  mov     [rbp+57h+var_60], eax
0x18047216a  xorps   xmm0, xmm0
0x18047216d  mov     [rbp+57h+var_48], eax
0x180472170  xorps   xmm1, xmm1
0x180472173  mov     eax, r9d
0x180472176  mov     qword ptr [rbp+57h+var_78], r14
0x18047217a  neg     eax
0x18047217c  mov     rsi, r8
0x18047217f  mov     r13, rdx
0x180472182  mov     rbx, rcx
0x180472185  sbb     rax, rax
0x180472188  and     rax, 0FFFFFFFFFFFFFFE0h
0x18047218c  add     rax, 0A0h
0x180472192  mov     [rbp+57h+var_90], rax
0x180472196  mov     eax, r9d
0x180472199  neg     eax
0x18047219b  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x18047219f  sbb     rax, rax
0x1804721a2  and     rax, 0FFFFFFFFFFFFFFE0h
0x1804721a6  add     rax, 98h
0x1804721ac  mov     [rbp+57h+var_88], rax
0x1804721b0  mov     eax, r9d
0x1804721b3  neg     eax
0x1804721b5  movups  xmmword ptr [rbp+57h+var_58], xmm1
0x1804721b9  sbb     r12, r12
0x1804721bc  and     r12d, 20h
0x1804721c0  sub     r12, 0FFFFFFFFFFFFFF80h
0x1804721c4  neg     r9d
0x1804721c7  sbb     r15, r15
0x1804721ca  and     r15d, 20h
0x1804721ce  add     r15, 78h ; 'x'
0x1804721d2  test    r8, r8
0x1804721d5  jz      short loc_1804721E5
0x1804721d7  cmp     [r8], r14d
0x1804721da  jz      short loc_1804721E5
0x1804721dc  lea     rdi, [rcx+8]
0x1804721e0  jmp     loc_1804724E2
0x1804721e5  lea     rdi, [rcx+8]
0x1804721e9  xor     r9d, r9d
0x1804721ec  mov     rcx, [rcx+70h]
0x1804721f0  lea     rax, [rbp+57h+var_78]
0x1804721f4  mov     [rsp+0F0h+var_D0], rax; unsigned int
0x1804721f9  xor     r8d, r8d
0x1804721fc  mov     rax, [rdi+40h]
0x180472200  mov     edx, 8004h
0x180472205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18047220a  test    eax, eax
0x18047220c  jnz     loc_1804722A0
0x180472212  mov     eax, cs:dword_1808B5850
0x180472218  cmp     eax, 2
0x18047221b  jbe     loc_180472864
0x180472221  call    cs:__imp_GetLastError
0x180472227  mov     [rbp+57h+var_9C], 3B7h
0x18047222e  lea     rdx, dword_1808845F4
0x180472235  mov     [rbp+57h+var_A0], eax
0x180472238  lea     rax, aTsSecurityFips_1; "TS_SECURITY_FIPS_MakeSessionKeys"
0x18047223f  mov     [rbp+57h+var_80], rax
0x180472243  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18047224a  mov     [rbp+57h+var_90], rax
0x18047224e  lea     rax, aCryptcreatehas_0; "CryptCreateHash failed with %u"
0x180472255  mov     [rbp+57h+var_88], rax
0x180472259  lea     rax, [rbp+57h+var_A0]
0x18047225d  mov     [rsp+0F0h+var_A8], rax
0x180472262  lea     rax, [rbp+57h+var_80]
0x180472266  mov     [rsp+0F0h+var_B0], rax
0x18047226b  lea     rax, [rbp+57h+var_9C]
0x18047226f  mov     [rsp+0F0h+var_B8], rax
0x180472274  lea     rax, [rbp+57h+var_90]
0x180472278  mov     [rsp+0F0h+var_C0], rax
0x18047227d  lea     rax, [rbp+57h+var_98]
0x180472281  mov     [rsp+0F0h+var_C8], rax
0x180472286  lea     rax, [rbp+57h+var_88]
0x18047228a  mov     [rbp+57h+var_98], 80004005h
0x180472291  mov     [rsp+0F0h+var_D0], rax
0x180472296  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18047229b  jmp     loc_180472864
0x1804722a0  mov     rcx, qword ptr [rbp+57h+var_78]
0x1804722a4  lea     rdx, [r13+10h]
0x1804722a8  mov     rax, [rbx+50h]
0x1804722ac  xor     r9d, r9d
0x1804722af  lea     r8d, [r9+10h]
0x1804722b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804722b8  test    eax, eax
0x1804722ba  jnz     loc_180472344
0x1804722c0  mov     eax, cs:dword_1808B5850
0x1804722c6  cmp     eax, 2
0x1804722c9  jbe     loc_180472864
0x1804722cf  call    cs:__imp_GetLastError
0x1804722d5  mov     [rbp+57h+var_9C], 3BBh
0x1804722dc  lea     rdx, byte_18088459F
0x1804722e3  mov     [rbp+57h+var_98], eax
0x1804722e6  lea     rax, aTsSecurityFips_1; "TS_SECURITY_FIPS_MakeSessionKeys"
0x1804722ed  mov     [rbp+57h+var_88], rax
0x1804722f1  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1804722f8  mov     [rbp+57h+var_90], rax
0x1804722fc  lea     rax, aCrypthashdataF_0; "CryptHashData failed with %u"
0x180472303  mov     [rbp+57h+var_80], rax
0x180472307  lea     rax, [rbp+57h+var_98]
0x18047230b  mov     [rsp+0F0h+var_A8], rax
0x180472310  lea     rax, [rbp+57h+var_88]
0x180472314  mov     [rsp+0F0h+var_B0], rax
0x180472319  lea     rax, [rbp+57h+var_9C]
0x18047231d  mov     [rsp+0F0h+var_B8], rax
0x180472322  lea     rax, [rbp+57h+var_90]
0x180472326  mov     [rsp+0F0h+var_C0], rax
0x18047232b  lea     rax, [rbp+57h+var_A0]
0x18047232f  mov     [rsp+0F0h+var_C8], rax
0x180472334  lea     rax, [rbp+57h+var_80]
0x180472338  mov     [rbp+57h+var_A0], 80004005h
0x18047233f  jmp     loc_180472291
0x180472344  mov     rcx, qword ptr [rbp+57h+var_78]
0x180472348  lea     rdx, [r13+30h]
0x18047234c  mov     rax, [rbx+50h]
0x180472350  xor     r9d, r9d
0x180472353  lea     r8d, [r9+10h]
0x180472357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18047235c  test    eax, eax
0x18047235e  jnz     loc_1804723E8
0x180472364  mov     eax, cs:dword_1808B5850
0x18047236a  cmp     eax, 2
0x18047236d  jbe     loc_180472864
0x180472373  call    cs:__imp_GetLastError
0x180472379  mov     [rbp+57h+var_9C], 3BFh
0x180472380  lea     rdx, word_18088469E
0x180472387  mov     [rbp+57h+var_98], eax
0x18047238a  lea     rax, aTsSecurityFips_1; "TS_SECURITY_FIPS_MakeSessionKeys"
0x180472391  mov     [rbp+57h+var_88], rax
0x180472395  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18047239c  mov     [rbp+57h+var_90], rax
0x1804723a0  lea     rax, aCrypthashdataF_0; "CryptHashData failed with %u"
0x1804723a7  mov     [rbp+57h+var_80], rax
0x1804723ab  lea     rax, [rbp+57h+var_98]
0x1804723af  mov     [rsp+0F0h+var_A8], rax
0x1804723b4  lea     rax, [rbp+57h+var_88]
0x1804723b8  mov     [rsp+0F0h+var_B0], rax
0x1804723bd  lea     rax, [rbp+57h+var_9C]
0x1804723c1  mov     [rsp+0F0h+var_B8], rax
0x1804723c6  lea     rax, [rbp+57h+var_90]
0x1804723ca  mov     [rsp+0F0h+var_C0], rax
0x1804723cf  lea     rax, [rbp+57h+var_A0]
0x1804723d3  mov     [rsp+0F0h+var_C8], rax
0x1804723d8  lea     rax, [rbp+57h+var_80]
0x1804723dc  mov     [rbp+57h+var_A0], 80004005h
0x1804723e3  jmp     loc_180472291
0x1804723e8  lea     r8, [rbp+57h+var_70]; unsigned __int8 *
0x1804723ec  mov     rcx, rdi; struct _CAPI_FUNCTION_TABLE *
0x1804723ef  lea     rdx, [rbp+57h+var_78]; unsigned __int64 *
0x1804723f3  call    ?DumpHashes@@YAHPEAU_CAPI_FUNCTION_TABLE@@PEA_KPEAEK@Z; DumpHashes(_CAPI_FUNCTION_TABLE *,unsigned __int64 *,uchar *,ulong)
0x1804723f8  test    eax, eax
0x1804723fa  jz      loc_180472864
0x180472400  mov     rdx, [rbx+70h]; unsigned __int64
0x180472404  lea     rcx, [rbp+57h+var_A0]
0x180472408  mov     [rsp+0F0h+var_C0], rcx; unsigned int *
0x18047240d  lea     rax, [r12+rbx]
0x180472411  add     r15, rbx
0x180472414  mov     [rbp+57h+var_A0], 18h
0x18047241b  mov     rcx, rdi; struct _CAPI_FUNCTION_TABLE *
0x18047241e  mov     [rsp+0F0h+var_C8], rax; unsigned __int8 *
0x180472423  lea     r9, [rbp+57h+var_70]; unsigned __int8 *
0x180472427  mov     r8, r15; unsigned __int64 *
0x18047242a  call    ?TS_SECURITY_FIPS_DeriveKey@@YAHPEAU_CAPI_FUNCTION_TABLE@@_KPEA_KPEAEK3PEAK@Z; TS_SECURITY_FIPS_DeriveKey(_CAPI_FUNCTION_TABLE *,unsigned __int64,unsigned __int64 *,uchar *,ulong,uchar *,ulong *)
0x18047242f  test    eax, eax
0x180472431  jz      loc_180472864
0x180472437  mov     rcx, [r15]
0x18047243a  lea     r8, ?rgbIV@@3PAEA; uchar near * rgbIV
0x180472441  mov     rax, [rbx+40h]
0x180472445  xor     r9d, r9d
0x180472448  lea     edx, [r9+1]
0x18047244c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180472451  test    eax, eax
0x180472453  jnz     loc_1804724DD
0x180472459  mov     eax, cs:dword_1808B5850
0x18047245f  cmp     eax, 2
0x180472462  jbe     loc_180472864
0x180472468  call    cs:__imp_GetLastError
0x18047246e  mov     [rbp+57h+var_9C], 3D0h
0x180472475  lea     rdx, byte_180884649
0x18047247c  mov     [rbp+57h+var_98], eax
0x18047247f  lea     rax, aTsSecurityFips_1; "TS_SECURITY_FIPS_MakeSessionKeys"
0x180472486  mov     [rbp+57h+var_88], rax
0x18047248a  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180472491  mov     [rbp+57h+var_90], rax
0x180472495  lea     rax, aErrorXDuringCr_3; "Error %x during CryptSetKeyParam!"
0x18047249c  mov     [rbp+57h+var_80], rax
0x1804724a0  lea     rax, [rbp+57h+var_98]
0x1804724a4  mov     [rsp+0F0h+var_A8], rax
0x1804724a9  lea     rax, [rbp+57h+var_88]
0x1804724ad  mov     [rsp+0F0h+var_B0], rax
0x1804724b2  lea     rax, [rbp+57h+var_9C]
0x1804724b6  mov     [rsp+0F0h+var_B8], rax
0x1804724bb  lea     rax, [rbp+57h+var_90]
0x1804724bf  mov     [rsp+0F0h+var_C0], rax
0x1804724c4  lea     rax, [rbp+57h+var_A0]
0x1804724c8  mov     [rsp+0F0h+var_C8], rax
0x1804724cd  lea     rax, [rbp+57h+var_80]
0x1804724d1  mov     [rbp+57h+var_A0], 80004005h
0x1804724d8  jmp     loc_180472291
0x1804724dd  test    rsi, rsi
0x1804724e0  jz      short loc_1804724EB
0x1804724e2  cmp     dword ptr [rsi], 1
0x1804724e5  jnz     loc_18047285E
0x1804724eb  mov     rcx, [rbx+70h]
0x1804724ef  lea     rax, [rbp+57h+var_78]
0x1804724f3  mov     [rsp+0F0h+var_D0], rax; unsigned int
0x1804724f8  xor     r9d, r9d
0x1804724fb  mov     rax, [rdi+40h]
0x1804724ff  xor     r8d, r8d
0x180472502  mov     edx, 8004h
0x180472507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18047250c  test    eax, eax
0x18047250e  jnz     loc_180472598
0x180472514  mov     eax, cs:dword_1808B5850
0x18047251a  cmp     eax, 2
0x18047251d  jbe     loc_180472864
0x180472523  call    cs:__imp_GetLastError
0x180472529  mov     [rbp+57h+var_9C], 3DBh
0x180472530  lea     rdx, qword_180884748
0x180472537  mov     [rbp+57h+var_98], eax
0x18047253a  lea     rax, aTsSecurityFips_1; "TS_SECURITY_FIPS_MakeSessionKeys"
0x180472541  mov     [rbp+57h+var_88], rax
0x180472545  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18047254c  mov     [rbp+57h+var_90], rax
0x180472550  lea     rax, aCryptcreatehas_0; "CryptCreateHash failed with %u"
0x180472557  mov     [rbp+57h+var_80], rax
0x18047255b  lea     rax, [rbp+57h+var_98]
0x18047255f  mov     [rsp+0F0h+var_A8], rax
0x180472564  lea     rax, [rbp+57h+var_88]
0x180472568  mov     [rsp+0F0h+var_B0], rax
0x18047256d  lea     rax, [rbp+57h+var_9C]
0x180472571  mov     [rsp+0F0h+var_B8], rax
0x180472576  lea     rax, [rbp+57h+var_90]
0x18047257a  mov     [rsp+0F0h+var_C0], rax
0x18047257f  lea     rax, [rbp+57h+var_A0]
0x180472583  mov     [rsp+0F0h+var_C8], rax
0x180472588  lea     rax, [rbp+57h+var_80]
0x18047258c  mov     [rbp+57h+var_A0], 80004005h
0x180472593  jmp     loc_180472291
0x180472598  mov     rcx, qword ptr [rbp+57h+var_78]
0x18047259c  xor     r9d, r9d
0x18047259f  mov     rax, [rbx+50h]
0x1804725a3  mov     rdx, r13
0x1804725a6  lea     r15d, [r9+10h]
0x1804725aa  mov     r8d, r15d
0x1804725ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804725b2  test    eax, eax
0x1804725b4  jnz     loc_18047263E
0x1804725ba  mov     eax, cs:dword_1808B5850
0x1804725c0  cmp     eax, 2
0x1804725c3  jbe     loc_180472864
0x1804725c9  call    cs:__imp_GetLastError
0x1804725cf  mov     [rbp+57h+var_9C], 3DFh
0x1804725d6  lea     rdx, byte_1808846F3
0x1804725dd  mov     [rbp+57h+var_98], eax
0x1804725e0  lea     rax, aTsSecurityFips_1; "TS_SECURITY_FIPS_MakeSessionKeys"
0x1804725e7  mov     [rbp+57h+var_88], rax
0x1804725eb  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1804725f2  mov     [rbp+57h+var_90], rax
0x1804725f6  lea     rax, aCrypthashdataF_0; "CryptHashData failed with %u"
0x1804725fd  mov     [rbp+57h+var_80], rax
0x180472601  lea     rax, [rbp+57h+var_98]
0x180472605  mov     [rsp+0F0h+var_A8], rax
0x18047260a  lea     rax, [rbp+57h+var_88]
0x18047260e  mov     [rsp+0F0h+var_B0], rax
0x180472613  lea     rax, [rbp+57h+var_9C]
0x180472617  mov     [rsp+0F0h+var_B8], rax
0x18047261c  lea     rax, [rbp+57h+var_90]
0x180472620  mov     [rsp+0F0h+var_C0], rax
0x180472625  lea     rax, [rbp+57h+var_A0]
0x180472629  mov     [rsp+0F0h+var_C8], rax
0x18047262e  lea     rax, [rbp+57h+var_80]
0x180472632  mov     [rbp+57h+var_A0], 80004005h
0x180472639  jmp     loc_180472291
0x18047263e  mov     rcx, qword ptr [rbp+57h+var_78]
0x180472642  lea     rdx, [r13+20h]
0x180472646  mov     rax, [rbx+50h]
0x18047264a  xor     r9d, r9d
0x18047264d  mov     r8d, r15d
0x180472650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180472655  test    eax, eax
0x180472657  jnz     loc_1804726E1
0x18047265d  mov     eax, cs:dword_1808B5850
0x180472663  cmp     eax, 2
0x180472666  jbe     loc_180472864
0x18047266c  call    cs:__imp_GetLastError
0x180472672  mov     [rbp+57h+var_9C], 3E3h
  ... truncated ...
```
