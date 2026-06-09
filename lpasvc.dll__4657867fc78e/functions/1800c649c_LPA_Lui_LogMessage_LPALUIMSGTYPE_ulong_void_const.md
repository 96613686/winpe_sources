# LPA::Lui::LogMessage(LPALUIMSGTYPE,ulong,void const *)

- ea: `0x1800c649c`
- end: `0x1800c6e3a`
- name: `?LogMessage@Lui@LPA@@CAXW4LPALUIMSGTYPE@@KPEBX@Z`
- size: `2462`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c5bc8`
- `0x1800ce1fc`

## callees

- `0x180006dfc`
- `0x180007198`
- `0x1800074f0`
- `0x18000762c`
- `0x180007804`
- `0x180007c78`
- `0x18000df90`
- `0x18000ebf4`
- `0x1800c649c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c690f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c6d1c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c690f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c6d1c`

## string_xrefs

- `0x1800c6523`: `LpaServiceLui`
- `0x1800c6758`: `LpaServiceLui`
- `0x1800c6922`: `LpaServiceLui`
- `0x1800c6bec`: `LpaServiceLui`

## pseudocode

```c
__int64 __fastcall LPA::Lui::LogMessage(int a1, int a2, __int64 a3, int a4)
{
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  __int64 result; // rax
  bool v10; // zf
  unsigned int v11; // edi
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // rcx
  __int128 v16; // xmm1
  __int128 v17; // xmm1
  __int128 v18; // xmm1
  unsigned int i; // r15d
  __int64 v20; // rcx
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  GUID v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  int v30; // [rsp+108h] [rbp-80h] BYREF
  unsigned __int64 v31; // [rsp+10Ch] [rbp-7Ch] BYREF
  __int32 v32; // [rsp+114h] [rbp-74h] BYREF
  int v33; // [rsp+118h] [rbp-70h] BYREF
  __int64 v34; // [rsp+11Ch] [rbp-6Ch] BYREF
  bool v35[4]; // [rsp+124h] [rbp-64h] BYREF
  int v36; // [rsp+128h] [rbp-60h] BYREF
  int v37; // [rsp+12Ch] [rbp-5Ch] BYREF
  int v38; // [rsp+130h] [rbp-58h] BYREF
  const char *v39; // [rsp+138h] [rbp-50h] BYREF
  const char *v40; // [rsp+140h] [rbp-48h] BYREF
  const char *p_sz; // [rsp+148h] [rbp-40h] BYREF
  const char *v42; // [rsp+150h] [rbp-38h] BYREF
  int v43; // [rsp+158h] [rbp-30h] BYREF
  int v44; // [rsp+15Ch] [rbp-2Ch] BYREF
  int v45; // [rsp+160h] [rbp-28h] BYREF
  int v46; // [rsp+164h] [rbp-24h] BYREF
  const char *v47; // [rsp+168h] [rbp-20h] BYREF
  const char *v48; // [rsp+170h] [rbp-18h] BYREF
  const char *v49; // [rsp+178h] [rbp-10h] BYREF
  __int64 v50; // [rsp+180h] [rbp-8h] BYREF
  int v51; // [rsp+188h] [rbp+0h] BYREF
  const char *v52; // [rsp+190h] [rbp+8h] BYREF
  const char *v53; // [rsp+198h] [rbp+10h] BYREF
  const char *v54; // [rsp+1A0h] [rbp+18h] BYREF
  __int64 v55; // [rsp+1A8h] [rbp+20h] BYREF
  __int128 v56; // [rsp+1B8h] [rbp+30h] BYREF
  __int128 v57; // [rsp+1C8h] [rbp+40h]
  __int128 v58; // [rsp+1D8h] [rbp+50h]
  __int128 v59; // [rsp+1E8h] [rbp+60h] BYREF
  GUID rguid; // [rsp+1F8h] [rbp+70h] BYREF
  __m256i v61; // [rsp+208h] [rbp+80h]
  __int64 v62; // [rsp+228h] [rbp+A0h]
  OLECHAR sz; // [rsp+238h] [rbp+B0h] BYREF
  _BYTE v64[78]; // [rsp+23Ah] [rbp+B2h] BYREF

  v6 = a1 - 3;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        if ( v8 == 3 )
        {
          result = (unsigned int)CallbackContext;
          if ( (unsigned int)CallbackContext > 4 )
          {
            HIDWORD(v31) = a2;
            v55 = a3 + 502;
            v51 = *(_DWORD *)(a3 + 1028);
            v43 = *(_DWORD *)(a3 + 1024);
            v52 = (const char *)(a3 + 494);
            v53 = (const char *)(a3 + 486);
            v10 = *(_DWORD *)(a3 + 8) == 0;
            v54 = (const char *)(a3 + 420);
            v47 = (const char *)(a3 + 290);
            v35[0] = !v10;
            v32 = 8;
            v48 = (const char *)(a3 + 160);
            v44 = *(_DWORD *)(a3 + 156);
            v45 = *(_DWORD *)(a3 + 152);
            v49 = (const char *)(a3 + 84);
            v46 = *(_DWORD *)(a3 + 80);
            v50 = a3 + 36;
            v37 = *(_DWORD *)(a3 + 32);
            p_sz = "LPA_PROFILE_INFO";
            v38 = *(_DWORD *)(a3 + 28);
            v36 = *(_DWORD *)(a3 + 24);
            v42 = "LPA_PROFILE_DETAILS";
            v33 = *(_DWORD *)(a3 + 20);
            LODWORD(v34) = *(_DWORD *)(a3 + 16);
            HIDWORD(v34) = *(_DWORD *)(a3 + 12);
            v30 = *(_DWORD *)(a3 + 4);
            LODWORD(v31) = *(_DWORD *)a3;
            v39 = "LPA::Lui::LogMessage";
            v40 = "LpaServiceLui";
            return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                     3,
                     (unsigned int)byte_180134185,
                     a3,
                     a4,
                     (__int64)&v40,
                     (__int64)&v39,
                     (__int64)&v32,
                     (__int64)&v31 + 4,
                     (__int64)&v31,
                     (__int64)&v30,
                     (__int64)v35,
                     (__int64)&v34 + 4,
                     (__int64)&v34,
                     (__int64)&v33,
                     (__int64)&v42,
                     (__int64)&v36,
                     (__int64)&v38,
                     (__int64)&p_sz,
                     (__int64)&v37,
                     (__int64)&v50,
                     (__int64)&v46,
                     (__int64)&v49,
                     (__int64)&v45,
                     (__int64)&v44,
                     (__int64)&v48,
                     (__int64)&v47,
                     (__int64)&v54,
                     (__int64)&v53,
                     (__int64)&v52,
                     (__int64)&v43,
                     (__int64)&v51,
                     (__int64)&v55);
          }
        }
      }
      else
      {
        result = (unsigned int)CallbackContext;
        if ( (unsigned int)CallbackContext > 4 )
        {
          v38 = a2;
          v40 = (const char *)(a3 + 478);
          v32 = *(_DWORD *)(a3 + 1004);
          HIDWORD(v31) = *(_DWORD *)(a3 + 1000);
          v39 = (const char *)(a3 + 470);
          v42 = (const char *)(a3 + 462);
          p_sz = (const char *)(a3 + 396);
          v50 = a3 + 266;
          v49 = (const char *)(a3 + 136);
          LODWORD(v31) = *(_DWORD *)(a3 + 132);
          v30 = *(_DWORD *)(a3 + 128);
          v48 = (const char *)(a3 + 60);
          HIDWORD(v34) = *(_DWORD *)(a3 + 56);
          v47 = (const char *)(a3 + 12);
          LODWORD(v34) = *(_DWORD *)(a3 + 8);
          v54 = "LPA_PROFILE_INFO";
          v33 = *(_DWORD *)(a3 + 4);
          v36 = *(_DWORD *)a3;
          v37 = 5;
          v53 = "LPA::Lui::LogMessage";
          v52 = "LpaServiceLui";
          return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                   0,
                   (unsigned int)byte_180134365,
                   a3,
                   a4,
                   (__int64)&v52,
                   (__int64)&v53,
                   (__int64)&v37,
                   (__int64)&v38,
                   (__int64)&v36,
                   (__int64)&v33,
                   (__int64)&v54,
                   (__int64)&v34,
                   (__int64)&v47,
                   (__int64)&v34 + 4,
                   (__int64)&v48,
                   (__int64)&v30,
                   (__int64)&v31,
                   (__int64)&v49,
                   (__int64)&v50,
                   (__int64)&p_sz,
                   (__int64)&v42,
                   (__int64)&v39,
                   (__int64)&v31 + 4,
                   (__int64)&v32,
                   (__int64)&v40);
        }
      }
    }
    else
    {
      v11 = 0;
      sz = 0;
      memset_0(v64, 0, sizeof(v64));
      StringFromGUID2((const GUID *const)(a3 + 80), &sz, 40);
      result = (unsigned int)CallbackContext;
      if ( (unsigned int)CallbackContext > 4 )
      {
        v44 = a2;
        v40 = (const char *)(a3 + 696);
        v32 = *(_DWORD *)(a3 + 692);
        v31 = *(_QWORD *)(a3 + 684);
        v30 = *(_DWORD *)(a3 + 680);
        v39 = (const char *)(a3 + 158);
        v42 = (const char *)(a3 + 116);
        v34 = *(_QWORD *)(a3 + 100);
        v33 = *(_DWORD *)(a3 + 96);
        p_sz = (const char *)&sz;
        v50 = a3 + 12;
        v36 = *(_DWORD *)(a3 + 8);
        v49 = "LPA_ESIM_INFO";
        v38 = *(_DWORD *)(a3 + 4);
        v37 = *(_DWORD *)a3;
        v46 = *(_DWORD *)(a3 + 112);
        v45 = *(_DWORD *)(a3 + 108);
        v43 = 4;
        v48 = "LPA::Lui::LogMessage";
        v47 = "LpaServiceLui";
        result = _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                   v12,
                   (unsigned int)&dword_180134504,
                   v13,
                   v14,
                   (__int64)&v47,
                   (__int64)&v48,
                   (__int64)&v43,
                   (__int64)&v44,
                   (__int64)&v45,
                   (__int64)&v46,
                   (__int64)&v37,
                   (__int64)&v38,
                   (__int64)&v49,
                   (__int64)&v36,
                   (__int64)&v50,
                   (__int64)&p_sz,
                   (__int64)&v33,
                   (__int64)&v34,
                   (__int64)&v34 + 4,
                   (__int64)&v42,
                   (__int64)&v39,
                   (__int64)&v30,
                   (__int64)&v31,
                   (__int64)&v31 + 4,
                   (__int64)&v32,
                   (__int64)&v40);
      }
      if ( (*(_BYTE *)(a3 + 4) & 1) != 0 && (*(_BYTE *)(a3 + 8) & 0x10) != 0 && *(_DWORD *)(a3 + 104) )
      {
        do
        {
          v15 = 120 * (v11 + 6LL);
          result = (unsigned int)CallbackContext;
          v16 = *(_OWORD *)(v15 + a3 + 16);
          v56 = *(_OWORD *)(v15 + a3);
          v57 = v16;
          v17 = *(_OWORD *)(v15 + a3 + 48);
          v58 = *(_OWORD *)(v15 + a3 + 32);
          v59 = v17;
          v18 = *(_OWORD *)(v15 + a3 + 80);
          rguid = *(GUID *)(v15 + a3 + 64);
          *(_OWORD *)v61.m256i_i8 = v18;
          v62 = *(_QWORD *)(v15 + a3 + 112);
          *(_OWORD *)&v61.m256i_u64[2] = *(_OWORD *)(v15 + a3 + 96);
          if ( (unsigned int)CallbackContext > 4 )
          {
            v31 = __PAIR64__(v56, a2);
            v40 = (char *)&v59 + 4;
            v32 = v59;
            v39 = (char *)&v56 + 4;
            v30 = 4;
            v42 = "LPA::Lui::LogMessage";
            p_sz = "LpaServiceLui";
            result = _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                       v15,
                       (unsigned int)&byte_1801342FF,
                       v13,
                       v14,
                       (__int64)&p_sz,
                       (__int64)&v42,
                       (__int64)&v30,
                       (__int64)&v31,
                       (__int64)&v31 + 4,
                       (__int64)&v39,
                       (__int64)&v32,
                       (__int64)&v40);
          }
          ++v11;
        }
        while ( v11 < *(_DWORD *)(a3 + 104) );
      }
    }
  }
  else
  {
    result = (unsigned int)CallbackContext;
    if ( (unsigned int)CallbackContext > 4 )
    {
      v32 = *(_DWORD *)(a3 + 16);
      v31 = *(_QWORD *)(a3 + 8);
      v30 = *(_DWORD *)(a3 + 4);
      HIDWORD(v34) = *(_DWORD *)a3;
      LODWORD(v34) = a2;
      v33 = 3;
      v40 = "LPA::Lui::LogMessage";
      v39 = "LpaServiceLui";
      result = _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                 0,
                 (unsigned int)&word_18013464E,
                 a3,
                 a4,
                 (__int64)&v39,
                 (__int64)&v40,
                 (__int64)&v33,
                 (__int64)&v34,
                 (__int64)&v34 + 4,
                 (__int64)&v30,
                 (__int64)&v31,
                 (__int64)&v31 + 4,
                 (__int64)&v32);
    }
    if ( (*(_BYTE *)(a3 + 4) & 4) != 0 )
    {
      for ( i = 0; i < *(_DWORD *)(a3 + 16); ++i )
      {
        v20 = 108LL * i;
        sz = 0;
        v21 = *(_OWORD *)(v20 + a3 + 36);
        v56 = *(_OWORD *)(v20 + a3 + 20);
        v22 = *(_OWORD *)(v20 + a3 + 52);
        v57 = v21;
        v23 = *(_OWORD *)(v20 + a3 + 68);
        v58 = v22;
        v24 = *(GUID *)(v20 + a3 + 84);
        v59 = v23;
        v25 = *(_OWORD *)(v20 + a3 + 100);
        rguid = v24;
        v26 = *(_OWORD *)(v20 + a3 + 112);
        *(_OWORD *)v61.m256i_i8 = v25;
        *(_OWORD *)((char *)&v61.m256i_u64[1] + 4) = v26;
        memset_0(v64, 0, sizeof(v64));
        StringFromGUID2((const GUID *const)rguid.Data4, &sz, 40);
        result = (unsigned int)CallbackContext;
        if ( (unsigned int)CallbackContext > 4 )
        {
          v32 = v61.m256i_i32[4];
          v31 = v61.m256i_u64[1];
          v40 = (const char *)&sz;
          v39 = (char *)&v56 + 4;
          v30 = v56;
          v34 = *(__int64 *)((char *)&v61.m256i_i64[2] + 4);
          v33 = a2;
          v36 = 3;
          v42 = "LPA::Lui::LogMessage";
          p_sz = "LpaServiceLui";
          result = _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                     v27,
                     (unsigned int)word_18013446A,
                     v28,
                     v29,
                     (__int64)&p_sz,
                     (__int64)&v42,
                     (__int64)&v36,
                     (__int64)&v33,
                     (__int64)&v34,
                     (__int64)&v34 + 4,
                     (__int64)&v30,
                     (__int64)&v39,
                     (__int64)&v40,
                     (__int64)&v31,
                     (__int64)&v31 + 4,
                     (__int64)&v32);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800c649c  mov     r11, rsp
0x1800c649f  mov     [r11+8], rbx
0x1800c64a3  mov     [r11+10h], rsi
0x1800c64a7  push    rbp
0x1800c64a8  push    rdi
0x1800c64a9  push    r12
0x1800c64ab  push    r14
0x1800c64ad  push    r15
0x1800c64af  lea     rbp, [r11-138h]
0x1800c64b6  sub     rsp, 290h
0x1800c64bd  mov     rax, cs:__security_cookie
0x1800c64c4  xor     rax, rsp
0x1800c64c7  mov     [rbp+130h+var_30], rax
0x1800c64ce  mov     rbx, r8
0x1800c64d1  mov     r12d, edx
0x1800c64d4  sub     ecx, 3
0x1800c64d7  jz      loc_1800C6BDF
0x1800c64dd  sub     ecx, 1
0x1800c64e0  jz      loc_1800C68E5
0x1800c64e6  sub     ecx, 1
0x1800c64e9  jz      loc_1800C672C
0x1800c64ef  cmp     ecx, 3
0x1800c64f2  jnz     loc_1800C6E0F
0x1800c64f8  mov     eax, cs:CallbackContext
0x1800c64fe  cmp     eax, 4
0x1800c6501  jbe     loc_1800C6E0F
0x1800c6507  lea     rax, [r8+1F6h]
0x1800c650e  mov     dword ptr [rbp+130h+var_1AC+4], edx
0x1800c6511  mov     [rbp+130h+var_110], rax
0x1800c6515  lea     rsi, aLpaLuiLogmessa; "LPA::Lui::LogMessage"
0x1800c651c  mov     eax, [r8+404h]
0x1800c6523  lea     r14, aLpaservicelui; "LpaServiceLui"
0x1800c652a  mov     [rbp+130h+var_130], eax
0x1800c652d  xor     edi, edi
0x1800c652f  mov     eax, [r8+400h]
0x1800c6536  mov     [rbp+130h+var_160], eax
0x1800c6539  lea     rax, [r8+1EEh]
0x1800c6540  mov     [rbp+130h+var_128], rax
0x1800c6544  lea     rax, [r8+1E6h]
0x1800c654b  mov     [rbp+130h+var_120], rax
0x1800c654f  lea     rax, [r8+1A4h]
0x1800c6556  cmp     [r8+8], edi
0x1800c655a  mov     [rbp+130h+var_118], rax
0x1800c655e  lea     rax, [r8+122h]
0x1800c6565  mov     [rbp+130h+var_150], rax
0x1800c6569  setnz   [rbp+130h+var_194]
0x1800c656d  lea     rax, [r8+0A0h]
0x1800c6574  mov     [rbp+130h+var_1A4], 8
0x1800c657b  mov     [rbp+130h+var_148], rax
0x1800c657f  mov     eax, [r8+9Ch]
0x1800c6586  mov     [rbp+130h+var_15C], eax
0x1800c6589  mov     eax, [r8+98h]
0x1800c6590  mov     [rbp+130h+var_158], eax
0x1800c6593  lea     rax, [r8+54h]
0x1800c6597  mov     [rbp+130h+var_140], rax
0x1800c659b  mov     eax, [r8+50h]
0x1800c659f  mov     [rbp+130h+var_154], eax
0x1800c65a2  lea     rax, [r8+24h]
0x1800c65a6  mov     [rbp+130h+var_138], rax
0x1800c65aa  mov     eax, [r8+20h]
0x1800c65ae  mov     [rbp+130h+var_18C], eax
0x1800c65b1  lea     rax, aLpaProfileInfo; "LPA_PROFILE_INFO"
0x1800c65b8  mov     [rbp+130h+var_170], rax
0x1800c65bc  mov     eax, [r8+1Ch]
0x1800c65c0  mov     [rbp+130h+var_188], eax
0x1800c65c3  mov     eax, [r8+18h]
0x1800c65c7  mov     [rbp+130h+var_190], eax
0x1800c65ca  lea     rax, aLpaProfileDeta; "LPA_PROFILE_DETAILS"
0x1800c65d1  mov     [rbp+130h+var_168], rax
0x1800c65d5  mov     eax, [r8+14h]
0x1800c65d9  mov     [rbp+130h+var_1A0], eax
0x1800c65dc  mov     eax, [r8+10h]
0x1800c65e0  mov     dword ptr [rbp+130h+var_19C], eax
0x1800c65e3  mov     eax, [r8+0Ch]
0x1800c65e7  mov     dword ptr [rbp+130h+var_19C+4], eax
0x1800c65ea  mov     eax, [r8+4]
0x1800c65ee  mov     [rbp+130h+var_1B0], eax
0x1800c65f1  mov     eax, [r8]
0x1800c65f4  mov     dword ptr [rbp+130h+var_1AC], eax
0x1800c65f7  lea     rax, [rbp+130h+var_110]
0x1800c65fb  mov     [r11-1C0h], rax
0x1800c6602  lea     rax, [rbp+130h+var_130]
0x1800c6606  mov     [r11-1C8h], rax
0x1800c660d  lea     rax, [rbp+130h+var_160]
0x1800c6611  mov     [r11-1D0h], rax
0x1800c6618  lea     rax, [rbp+130h+var_128]
0x1800c661c  mov     [r11-1D8h], rax
0x1800c6623  lea     rax, [rbp+130h+var_120]
0x1800c6627  mov     [r11-1E0h], rax
0x1800c662e  lea     rax, [rbp+130h+var_118]
0x1800c6632  mov     [r11-1E8h], rax
0x1800c6639  lea     rax, [rbp+130h+var_150]
0x1800c663d  mov     [r11-1F0h], rax
0x1800c6644  lea     rax, [rbp+130h+var_148]
0x1800c6648  mov     [r11-1F8h], rax
0x1800c664f  lea     rax, [rbp+130h+var_15C]
0x1800c6653  mov     [r11-200h], rax
0x1800c665a  lea     rax, [rbp+130h+var_158]
0x1800c665e  mov     [r11-208h], rax
0x1800c6665  lea     rax, [rbp+130h+var_140]
0x1800c6669  mov     [r11-210h], rax
0x1800c6670  lea     rax, [rbp+130h+var_154]
0x1800c6674  mov     [r11-218h], rax
0x1800c667b  lea     rax, [rbp+130h+var_138]
0x1800c667f  mov     [r11-220h], rax
0x1800c6686  mov     [rbp+130h+var_180], rsi
0x1800c668a  mov     [rbp+130h+var_178], r14
0x1800c668e  lea     rax, [rbp+130h+var_18C]
0x1800c6692  mov     [r11-228h], rax
0x1800c6699  lea     rdx, byte_180134185
0x1800c66a0  lea     rax, [rbp+130h+var_170]
0x1800c66a4  mov     [r11-230h], rax
0x1800c66ab  lea     rax, [rbp+130h+var_188]
0x1800c66af  mov     [r11-238h], rax
0x1800c66b6  lea     rax, [rbp+130h+var_190]
0x1800c66ba  mov     [rsp+2B0h+var_238], rax
0x1800c66bf  lea     rax, [rbp+130h+var_168]
0x1800c66c3  mov     [rsp+2B0h+var_240], rax
0x1800c66c8  lea     rax, [rbp+130h+var_1A0]
0x1800c66cc  mov     [rsp+2B0h+var_248], rax
0x1800c66d1  lea     rax, [rbp+130h+var_19C]
0x1800c66d5  mov     [rsp+2B0h+var_250], rax
0x1800c66da  lea     rax, [rbp+130h+var_19C+4]
0x1800c66de  mov     [rsp+2B0h+var_258], rax
0x1800c66e3  lea     rax, [rbp+130h+var_194]
0x1800c66e7  mov     [rsp+2B0h+var_260], rax
0x1800c66ec  lea     rax, [rbp+130h+var_1B0]
0x1800c66f0  mov     [rsp+2B0h+var_268], rax
0x1800c66f5  lea     rax, [rbp+130h+var_1AC]
0x1800c66f9  mov     [rsp+2B0h+var_270], rax
0x1800c66fe  lea     rax, [rbp+130h+var_1AC+4]
0x1800c6702  mov     [rsp+2B0h+var_278], rax
0x1800c6707  lea     rax, [rbp+130h+var_1A4]
0x1800c670b  mov     [rsp+2B0h+var_280], rax
0x1800c6710  lea     rax, [rbp+130h+var_180]
0x1800c6714  mov     [rsp+2B0h+var_288], rax
0x1800c6719  lea     rax, [rbp+130h+var_178]
0x1800c671d  mov     [rsp+2B0h+var_290], rax
0x1800c6722  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U?$_tlgWrapperByVal@$00@@U2@U2@U2@U1@U2@U2@U1@U2@U?$_tlgWrapSz@G@@U2@U4@U2@U2@U4@U4@U4@U4@U4@U2@U2@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@444AEBU?$_tlgWrapperByVal@$00@@44434434AEBU?$_tlgWrapSz@G@@464466666446@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800c6727  jmp     loc_1800C6E0F
0x1800c672c  mov     eax, cs:CallbackContext
0x1800c6732  cmp     eax, 4
0x1800c6735  jbe     loc_1800C6E0F
0x1800c673b  lea     rax, [r8+1DEh]
0x1800c6742  mov     [rbp+130h+var_188], r12d
0x1800c6746  mov     [rbp+130h+var_178], rax
0x1800c674a  lea     rsi, aLpaLuiLogmessa; "LPA::Lui::LogMessage"
0x1800c6751  mov     eax, [r8+3ECh]
0x1800c6758  lea     r14, aLpaservicelui; "LpaServiceLui"
0x1800c675f  mov     [rbp+130h+var_1A4], eax
0x1800c6762  mov     eax, [r8+3E8h]
0x1800c6769  mov     dword ptr [rbp+130h+var_1AC+4], eax
0x1800c676c  lea     rax, [r8+1D6h]
0x1800c6773  mov     [rbp+130h+var_180], rax
0x1800c6777  lea     rax, [r8+1CEh]
0x1800c677e  mov     [rbp+130h+var_168], rax
0x1800c6782  lea     rax, [r8+18Ch]
0x1800c6789  mov     [rbp+130h+var_170], rax
0x1800c678d  lea     rax, [r8+10Ah]
0x1800c6794  mov     [rbp+130h+var_138], rax
0x1800c6798  lea     rax, [r8+88h]
0x1800c679f  mov     [rbp+130h+var_140], rax
0x1800c67a3  mov     eax, [r8+84h]
0x1800c67aa  mov     dword ptr [rbp+130h+var_1AC], eax
0x1800c67ad  mov     eax, [r8+80h]
0x1800c67b4  mov     [rbp+130h+var_1B0], eax
0x1800c67b7  lea     rax, [r8+3Ch]
0x1800c67bb  mov     [rbp+130h+var_148], rax
0x1800c67bf  mov     eax, [r8+38h]
0x1800c67c3  mov     dword ptr [rbp+130h+var_19C+4], eax
0x1800c67c6  lea     rax, [r8+0Ch]
0x1800c67ca  mov     [rbp+130h+var_150], rax
0x1800c67ce  mov     eax, [r8+8]
0x1800c67d2  mov     dword ptr [rbp+130h+var_19C], eax
0x1800c67d5  lea     rax, aLpaProfileInfo; "LPA_PROFILE_INFO"
0x1800c67dc  mov     [rbp+130h+var_118], rax
0x1800c67e0  mov     eax, [r8+4]
0x1800c67e4  mov     [rbp+130h+var_1A0], eax
0x1800c67e7  mov     eax, [r8]
0x1800c67ea  mov     [rbp+130h+var_190], eax
0x1800c67ed  lea     rax, [rbp+130h+var_178]
0x1800c67f1  mov     [rsp+2B0h+var_1F0], rax
0x1800c67f9  lea     rax, [rbp+130h+var_1A4]
0x1800c67fd  mov     [rsp+2B0h+var_1F8], rax
0x1800c6805  lea     rax, [rbp+130h+var_1AC+4]
0x1800c6809  mov     [rsp+2B0h+var_200], rax
0x1800c6811  lea     rax, [rbp+130h+var_180]
0x1800c6815  mov     [rsp+2B0h+var_208], rax
0x1800c681d  lea     rax, [rbp+130h+var_168]
0x1800c6821  mov     [rsp+2B0h+var_210], rax
0x1800c6829  lea     rax, [rbp+130h+var_170]
0x1800c682d  mov     [rsp+2B0h+var_218], rax
0x1800c6835  lea     rax, [rbp+130h+var_138]
0x1800c6839  mov     [rsp+2B0h+var_220], rax
0x1800c6841  lea     rax, [rbp+130h+var_140]
0x1800c6845  mov     [rsp+2B0h+var_228], rax
0x1800c684d  lea     rax, [rbp+130h+var_1AC]
0x1800c6851  mov     [rsp+2B0h+var_230], rax
0x1800c6859  lea     rax, [rbp+130h+var_1B0]
0x1800c685d  mov     [rsp+2B0h+var_238], rax
0x1800c6862  lea     rax, [rbp+130h+var_148]
0x1800c6866  mov     [rsp+2B0h+var_240], rax
0x1800c686b  lea     rax, [rbp+130h+var_19C+4]
0x1800c686f  mov     [rsp+2B0h+var_248], rax
0x1800c6874  lea     rax, [rbp+130h+var_150]
0x1800c6878  mov     [rsp+2B0h+var_250], rax
0x1800c687d  lea     rax, [rbp+130h+var_19C]
0x1800c6881  mov     [rsp+2B0h+var_258], rax
0x1800c6886  lea     rax, [rbp+130h+var_118]
0x1800c688a  mov     [rsp+2B0h+var_260], rax
0x1800c688f  lea     rax, [rbp+130h+var_1A0]
0x1800c6893  mov     [rsp+2B0h+var_268], rax
0x1800c6898  lea     rax, [rbp+130h+var_190]
0x1800c689c  mov     [rsp+2B0h+var_270], rax
0x1800c68a1  lea     rax, [rbp+130h+var_188]
0x1800c68a5  mov     [rsp+2B0h+var_278], rax
0x1800c68aa  lea     rax, [rbp+130h+var_18C]
0x1800c68ae  mov     [rsp+2B0h+var_280], rax
0x1800c68b3  lea     rax, [rbp+130h+var_120]
0x1800c68b7  mov     [rsp+2B0h+var_288], rax
0x1800c68bc  lea     rax, [rbp+130h+var_128]
0x1800c68c0  mov     [rbp+130h+var_18C], 5
0x1800c68c7  mov     [rbp+130h+var_120], rsi
0x1800c68cb  mov     [rbp+130h+var_128], r14
0x1800c68cf  lea     rdx, byte_180134365
0x1800c68d6  mov     [rsp+2B0h+var_290], rax
0x1800c68db  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U1@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U2@U3@U3@U3@U3@U3@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@44434AEBU?$_tlgWrapSz@G@@454455555445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800c68e0  jmp     loc_1800C6E0F
0x1800c68e5  xor     edi, edi
0x1800c68e7  lea     rcx, [rbp+130h+var_7E]; void *
0x1800c68ee  xor     edx, edx; Val
0x1800c68f0  mov     [rbp+130h+sz], di
0x1800c68f7  lea     r8d, [rdi+4Eh]; Size
0x1800c68fb  call    memset_0
0x1800c6900  lea     rcx, [rbx+50h]; rguid
0x1800c6904  lea     r8d, [rdi+28h]; cchMax
0x1800c6908  lea     rdx, [rbp+130h+sz]; lpsz
0x1800c690f  call    cs:__imp_StringFromGUID2
0x1800c6915  mov     eax, cs:CallbackContext
0x1800c691b  lea     rsi, aLpaLuiLogmessa; "LPA::Lui::LogMessage"
0x1800c6922  lea     r14, aLpaservicelui; "LpaServiceLui"
0x1800c6929  cmp     eax, 4
0x1800c692c  jbe     loc_1800C6AC4
0x1800c6932  lea     rax, [rbx+2B8h]
0x1800c6939  mov     [rbp+130h+var_15C], r12d
0x1800c693d  mov     [rbp+130h+var_178], rax
0x1800c6941  mov     eax, [rbx+2B4h]
0x1800c6947  mov     [rbp+130h+var_1A4], eax
0x1800c694a  mov     eax, [rbx+2B0h]
0x1800c6950  mov     dword ptr [rbp+130h+var_1AC+4], eax
0x1800c6953  mov     eax, [rbx+2ACh]
0x1800c6959  mov     dword ptr [rbp+130h+var_1AC], eax
0x1800c695c  mov     eax, [rbx+2A8h]
0x1800c6962  mov     [rbp+130h+var_1B0], eax
0x1800c6965  lea     rax, [rbx+9Eh]
0x1800c696c  mov     [rbp+130h+var_180], rax
0x1800c6970  lea     rax, [rbx+74h]
0x1800c6974  mov     [rbp+130h+var_168], rax
0x1800c6978  mov     eax, [rbx+68h]
0x1800c697b  mov     dword ptr [rbp+130h+var_19C+4], eax
0x1800c697e  mov     eax, [rbx+64h]
0x1800c6981  mov     dword ptr [rbp+130h+var_19C], eax
0x1800c6984  mov     eax, [rbx+60h]
0x1800c6987  mov     [rbp+130h+var_1A0], eax
0x1800c698a  lea     rax, [rbp+130h+sz]
0x1800c6991  mov     [rbp+130h+var_170], rax
0x1800c6995  lea     rax, [rbx+0Ch]
0x1800c6999  mov     [rbp+130h+var_138], rax
0x1800c699d  mov     eax, [rbx+8]
0x1800c69a0  mov     [rbp+130h+var_190], eax
0x1800c69a3  lea     rax, aLpaEsimInfo; "LPA_ESIM_INFO"
0x1800c69aa  mov     [rbp+130h+var_140], rax
0x1800c69ae  mov     eax, [rbx+4]
0x1800c69b1  mov     [rbp+130h+var_188], eax
0x1800c69b4  mov     eax, [rbx]
0x1800c69b6  mov     [rbp+130h+var_18C], eax
0x1800c69b9  mov     eax, [rbx+70h]
0x1800c69bc  mov     [rbp+130h+var_154], eax
0x1800c69bf  mov     eax, [rbx+6Ch]
0x1800c69c2  mov     [rbp+130h+var_158], eax
0x1800c69c5  lea     rax, [rbp+130h+var_178]
0x1800c69c9  mov     [rsp+2B0h+var_1E8], rax
0x1800c69d1  lea     rax, [rbp+130h+var_1A4]
0x1800c69d5  mov     [rsp+2B0h+var_1F0], rax
0x1800c69dd  lea     rax, [rbp+130h+var_1AC+4]
0x1800c69e1  mov     [rsp+2B0h+var_1F8], rax
0x1800c69e9  lea     rax, [rbp+130h+var_1AC]
0x1800c69ed  mov     [rsp+2B0h+var_200], rax
0x1800c69f5  lea     rax, [rbp+130h+var_1B0]
0x1800c69f9  mov     [rsp+2B0h+var_208], rax
0x1800c6a01  lea     rax, [rbp+130h+var_180]
0x1800c6a05  mov     [rsp+2B0h+var_210], rax
0x1800c6a0d  lea     rax, [rbp+130h+var_168]
0x1800c6a11  mov     [rsp+2B0h+var_218], rax
0x1800c6a19  lea     rax, [rbp+130h+var_19C+4]
0x1800c6a1d  mov     [rsp+2B0h+var_220], rax
0x1800c6a25  lea     rax, [rbp+130h+var_19C]
0x1800c6a29  mov     [rsp+2B0h+var_228], rax
0x1800c6a31  lea     rax, [rbp+130h+var_1A0]
0x1800c6a35  mov     [rsp+2B0h+var_230], rax
  ... truncated ...
```
