# ESIMPM::WwanHelper::QueryModemInfo(ESIMPM::InternalModemInfo &)

- ea: `0x14002dfac`
- end: `0x14002e5ae`
- name: `?QueryModemInfo@WwanHelper@ESIMPM@@QEAAKAEAUInternalModemInfo@2@@Z`
- size: `1538`
- prototype: `unsigned int(ESIMPM::WwanHelper *__hidden this, struct ESIMPM::InternalModemInfo *)`
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, installer_update`

## callers

- `0x140024900`
- `0x140028a80`
- `0x14002de6c`

## callees

- `0x140001518`
- `0x1400015c4`
- `0x140002f60`
- `0x14000dd20`
- `0x140013df8`
- `0x140014f64`
- `0x140020620`
- `0x14002dfac`

## import_xrefs

- `wwapi!WwanQueryInterface` at `0x14002e011`
- `wwapi!WwanQueryInterface` at `0x14002e27f`
- `wwapi!WwanQueryInterface` at `0x14002e41f`
- `wwapi!WwanQueryInterface` at `0x14002e011`
- `wwapi!WwanQueryInterface` at `0x14002e27f`
- `wwapi!WwanQueryInterface` at `0x14002e41f`
- `wwapi!WwanFreeMemory` at `0x14002e4f8`
- `wwapi!WwanFreeMemory` at `0x14002e56e`
- `wwapi!WwanFreeMemory` at `0x14002e57f`
- `wwapi!WwanFreeMemory` at `0x14002e4f8`
- `wwapi!WwanFreeMemory` at `0x14002e56e`
- `wwapi!WwanFreeMemory` at `0x14002e57f`

## string_xrefs

- `0x14002e553`: `device type %d Embedded %d ControlCaps 0x%x eSIM capable %d OptionalServices 0x%x MultiSim Capable %d numSIMSlot %d uiccSlotState[0] %d for DSSA, uiccSlotState[1], activeSlot %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ESIMPM::WwanHelper::QueryModemInfo(ESIMPM::WwanHelper *this, struct ESIMPM::InternalModemInfo *a2)
{
  unsigned int v4; // esi
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int *v7; // rcx
  unsigned int v9; // ebx
  int v10; // r15d
  _WORD *v11; // rdx
  unsigned __int64 v12; // rsi
  unsigned __int64 v13; // r8
  _WORD *v14; // rdx
  unsigned int v15; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // rcx
  char v19; // si
  char *v20; // rdx
  unsigned int v21; // eax
  __int64 v22; // r8
  __int64 v23; // r9
  const char *v24; // rcx
  unsigned int v25; // eax
  __int64 v26; // [rsp+20h] [rbp-A9h]
  __int64 v27; // [rsp+28h] [rbp-A1h]
  __int64 v28; // [rsp+30h] [rbp-99h]
  __int64 v29; // [rsp+38h] [rbp-91h]
  const char *v30; // [rsp+70h] [rbp-59h] BYREF
  const char *v31; // [rsp+78h] [rbp-51h] BYREF
  unsigned int v32; // [rsp+80h] [rbp-49h] BYREF
  unsigned int v33; // [rsp+84h] [rbp-45h] BYREF
  unsigned int *v34; // [rsp+88h] [rbp-41h] BYREF
  _DWORD *v35; // [rsp+90h] [rbp-39h] BYREF
  unsigned int **v36; // [rsp+98h] [rbp-31h] BYREF
  char v37; // [rsp+A0h] [rbp-29h]
  __int128 v38; // [rsp+A8h] [rbp-21h] BYREF
  __m128i si128; // [rsp+B8h] [rbp-11h]
  __int128 v40; // [rsp+C8h] [rbp-1h] BYREF
  __m128i v41; // [rsp+D8h] [rbp+Fh]

  *((_BYTE *)a2 + 40) = 0;
  v32 = 0;
  v34 = 0;
  v4 = WwanQueryInterface(*(_QWORD *)this, a2, 62, 0, &v32, &v34, 0, 0);
  v36 = &v34;
  v37 = 1;
  if ( v4 )
  {
    if ( (unsigned int)dword_140075078 > 2 )
    {
      v30 = "ESIMPM::WwanHelper::QueryModemInfo";
      v31 = (const char *)a2;
      v33 = v4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
        (unsigned int)dword_140075078,
        (__int64)&dword_14006C3CC,
        v5,
        v6,
        (__int64)&v33,
        (__int64 *)&v31,
        (const unsigned __int16 **)&v30);
    }
    return v4;
  }
  v7 = v34;
  if ( !v34 )
  {
    if ( (unsigned int)dword_140075078 > 2 )
    {
      v31 = "ESIMPM::WwanHelper::QueryModemInfo";
      v30 = (const char *)a2;
      v33 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
        0,
        (__int64)byte_14006C379,
        v5,
        v6,
        (__int64)&v33,
        (__int64 *)&v30,
        (const unsigned __int16 **)&v31);
    }
    return 13;
  }
  if ( v32 >= 0x1C0 )
  {
    if ( (v34[24] & 0x100) == 0 )
    {
      if ( (unsigned int)dword_140075078 > 3 )
      {
        v31 = "ESIMPM::WwanHelper::QueryModemInfo";
        v30 = (const char *)a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
          (__int64)v34,
          (__int64)byte_14006C329,
          v5,
          v32,
          (__int64 *)&v30,
          (const unsigned __int16 **)&v31);
      }
      v7 = v34;
    }
    *((_DWORD *)a2 + 4) = v7[24];
    *((_DWORD *)a2 + 5) = v7[85];
    *((_DWORD *)a2 + 6) = 1;
    *(_QWORD *)((char *)a2 + 28) = 2;
    v10 = 9;
    *((_DWORD *)a2 + 9) = 9;
    v11 = v7 + 34;
    v38 = 0;
    si128 = 0;
    v12 = -1;
    v13 = -1;
    do
      ++v13;
    while ( v11[v13] );
    std::wstring::_Construct<1,unsigned short const *>(&v38, v11, v13);
    if ( (__int128 *)((char *)a2 + 48) != &v38 )
    {
      std::wstring::_Tidy_deallocate((char **)a2 + 6);
      *((_OWORD *)a2 + 3) = v38;
      *((__m128i *)a2 + 4) = si128;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v38) = 0;
    }
    std::wstring::_Tidy_deallocate((char **)&v38);
    v14 = v34 + 50;
    v40 = 0;
    v41 = 0;
    do
      ++v12;
    while ( v14[v12] );
    std::wstring::_Construct<1,unsigned short const *>(&v40, v14, v12);
    if ( (__int128 *)((char *)a2 + 80) != &v40 )
    {
      std::wstring::_Tidy_deallocate((char **)a2 + 10);
      *((_OWORD *)a2 + 5) = v40;
      *((__m128i *)a2 + 6) = v41;
      v41 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v40) = 0;
    }
    std::wstring::_Tidy_deallocate((char **)&v40);
    v32 = 0;
    v35 = 0;
    v15 = WwanQueryInterface(*(_QWORD *)this, a2, 46, 0, &v32, &v35, 0, 0);
    v18 = v15;
    if ( v15 == 50 )
    {
      v19 = 0;
      if ( (unsigned int)dword_140075078 <= 4 )
        goto LABEL_44;
      v20 = byte_14006C2D1;
LABEL_36:
      v30 = (const char *)a2;
      v31 = "ESIMPM::WwanHelper::QueryModemInfo";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
        v18,
        (__int64)v20,
        v16,
        v17,
        (__int64 *)&v30,
        (const unsigned __int16 **)&v31);
      goto LABEL_44;
    }
    if ( v15 == 5023 )
    {
      v19 = 0;
      if ( (unsigned int)dword_140075078 > 4 )
      {
        v31 = "ESIMPM::WwanHelper::QueryModemInfo";
        v30 = (const char *)a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
          v15,
          (__int64)&word_14006C26E,
          v16,
          v17,
          (__int64 *)&v30,
          (const unsigned __int16 **)&v31);
      }
      *((_DWORD *)a2 + 6) = 2;
      *((_DWORD *)a2 + 9) = 0;
    }
    else if ( v15 )
    {
      v19 = 0;
      if ( (unsigned int)dword_140075078 > 2 )
      {
        v31 = "ESIMPM::WwanHelper::QueryModemInfo";
        v30 = (const char *)a2;
        v33 = v15;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
          v15,
          (__int64)&dword_14006C20C,
          v16,
          v17,
          (__int64)&v33,
          (__int64 *)&v30,
          (const unsigned __int16 **)&v31);
      }
    }
    else
    {
      v18 = (__int64)v35;
      if ( !v35 )
      {
        v19 = 0;
        if ( (unsigned int)dword_140075078 <= 3 )
          goto LABEL_44;
        v20 = &byte_14006C1BF;
        goto LABEL_36;
      }
      v19 = 1;
      if ( v32 >= 4 )
      {
        if ( (unsigned int)(*v35 - 1) > 1 )
        {
          ESIMPM::Log::Error("ESIMPM::WwanHelper::QueryModemInfo", (wchar_t *)a2, L"dwNumberOfSIMSlots %d is invalid");
        }
        else
        {
          *((_DWORD *)a2 + 6) = *v35;
          *((_DWORD *)a2 + 8) = *(_DWORD *)(v18 + 4);
          if ( *(_DWORD *)v18 == 2 )
            v10 = *(_DWORD *)(v18 + 8);
          *((_DWORD *)a2 + 9) = v10;
        }
      }
      else
      {
        HIDWORD(v26) = 0;
        ESIMPM::Log::Error(
          "ESIMPM::WwanHelper::QueryModemInfo",
          (wchar_t *)a2,
          L"WwanIntfOpcodeDeviceCaps query return bad data: dwDataSize %d min size %d");
      }
    }
LABEL_44:
    if ( *((_DWORD *)a2 + 6) != 2 )
    {
LABEL_58:
      *((_BYTE *)a2 + 40) = 1;
      LODWORD(v29) = v34[85];
      LODWORD(v28) = 1;
      LODWORD(v27) = v34[24];
      LODWORD(v26) = *v34 == 1;
      ESIMPM::Log::Info(
        "ESIMPM::WwanHelper::QueryModemInfo",
        (const struct _GUID *)a2,
        L"device type %d Embedded %d ControlCaps 0x%x eSIM capable %d OptionalServices 0x%x MultiSim Capable %d numSIMSlot"
         " %d uiccSlotState[0] %d for DSSA, uiccSlotState[1], activeSlot %d",
        *v34,
        v26,
        v27,
        v28,
        v29,
        1,
        *((_DWORD *)a2 + 6),
        *((_DWORD *)a2 + 8),
        *((_DWORD *)a2 + 9),
        *((_DWORD *)a2 + 7));
      if ( v19 )
      {
        WwanFreeMemory(v35);
        v35 = 0;
      }
      v9 = 0;
      goto LABEL_61;
    }
    v30 = 0;
    v21 = WwanQueryInterface(*(_QWORD *)this, a2, 47, 0, &v32, &v30, 0, 0);
    if ( v21 )
    {
      if ( (unsigned int)dword_140075078 > 2 )
      {
        v31 = "ESIMPM::WwanHelper::QueryModemInfo";
        v36 = (unsigned int **)a2;
        v33 = v21;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
          (unsigned int)dword_140075078,
          (__int64)&dword_14006C164,
          v22,
          v23,
          (__int64)&v33,
          (__int64 *)&v36,
          (const unsigned __int16 **)&v31);
      }
      goto LABEL_58;
    }
    v24 = v30;
    if ( !v30 )
    {
      if ( (unsigned int)dword_140075078 > 3 )
      {
        v36 = (unsigned int **)"ESIMPM::WwanHelper::QueryModemInfo";
        v31 = (const char *)a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
          0,
          (__int64)word_14006C10A,
          v22,
          v23,
          (__int64 *)&v31,
          (const unsigned __int16 **)&v36);
      }
      goto LABEL_58;
    }
    if ( v32 >= 0xC )
    {
      v25 = *((_DWORD *)v30 + 2);
      if ( v25 < 2 )
      {
        *((_DWORD *)a2 + 7) = v25;
        goto LABEL_57;
      }
      ESIMPM::Log::Error(
        "ESIMPM::WwanHelper::QueryModemInfo",
        (wchar_t *)a2,
        L"WwanIntfOpcodeMultiSIMSlotMaping query return bad uiccSlotID (%d)",
        v25);
    }
    else
    {
      HIDWORD(v26) = 0;
      ESIMPM::Log::Error(
        "ESIMPM::WwanHelper::QueryModemInfo",
        (wchar_t *)a2,
        L"WwanIntfOpcodeMultiSIMSlotMaping query return bad data: dwDataSize %d min size %d");
    }
    v24 = v30;
LABEL_57:
    WwanFreeMemory(v24);
    goto LABEL_58;
  }
  ESIMPM::Log::Error(
    "ESIMPM::WwanHelper::QueryModemInfo",
    (wchar_t *)a2,
    L"WwanIntfOpcodeDeviceCaps query return bad data: dwDataSize %d min size %d");
  v9 = 13;
LABEL_61:
  WwanFreeMemory(v34);
  return v9;
}

```

## disassembly

```asm
0x14002dfac  mov     [rsp-8+arg_10], rbx
0x14002dfb1  push    rbp
0x14002dfb2  push    rsi
0x14002dfb3  push    rdi
0x14002dfb4  push    r12
0x14002dfb6  push    r13
0x14002dfb8  push    r14
0x14002dfba  push    r15
0x14002dfbc  lea     rbp, [rsp-27h]
0x14002dfc1  sub     rsp, 0F0h
0x14002dfc8  mov     rax, cs:__security_cookie
0x14002dfcf  xor     rax, rsp
0x14002dfd2  mov     [rbp+57h+var_38], rax
0x14002dfd6  mov     rbx, rdx
0x14002dfd9  mov     r12, rcx
0x14002dfdc  xor     r13d, r13d
0x14002dfdf  mov     [rdx+28h], r13b
0x14002dfe3  mov     [rbp+57h+var_A0], r13d
0x14002dfe7  mov     [rbp+57h+var_98], r13
0x14002dfeb  mov     [rsp+120h+var_E8], r13
0x14002dff0  mov     [rsp+120h+var_F0], r13
0x14002dff5  lea     rax, [rbp+57h+var_98]
0x14002dff9  mov     [rsp+120h+var_F8], rax
0x14002dffe  lea     rax, [rbp+57h+var_A0]
0x14002e002  mov     [rsp+120h+var_100], rax
0x14002e007  xor     r9d, r9d
0x14002e00a  lea     r8d, [r13+3Eh]
0x14002e00e  mov     rcx, [rcx]
0x14002e011  call    cs:__imp_WwanQueryInterface
0x14002e017  mov     esi, eax
0x14002e019  lea     rax, [rbp+57h+var_98]
0x14002e01d  mov     [rbp+57h+var_88], rax
0x14002e021  mov     [rbp+57h+var_80], 1
0x14002e025  test    esi, esi
0x14002e027  jz      short loc_14002E073
0x14002e029  mov     ecx, cs:dword_140075078
0x14002e02f  cmp     ecx, 2
0x14002e032  jbe     loc_14002E0C6
0x14002e038  lea     rdi, aEsimpmWwanhelp_10; "ESIMPM::WwanHelper::QueryModemInfo"
0x14002e03f  mov     [rbp+57h+var_B0], rdi
0x14002e043  mov     [rbp+57h+var_A8], rbx
0x14002e047  mov     [rbp+57h+var_9C], esi
0x14002e04a  lea     rax, [rbp+57h+var_B0]
0x14002e04e  mov     [rsp+120h+var_F0], rax
0x14002e053  lea     rax, [rbp+57h+var_A8]
0x14002e057  mov     [rsp+120h+var_F8], rax
0x14002e05c  lea     rax, [rbp+57h+var_9C]
0x14002e060  mov     [rsp+120h+var_100], rax
0x14002e065  lea     rdx, dword_14006C3CC
0x14002e06c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x14002e071  jmp     short loc_14002E0C6
0x14002e073  mov     rcx, [rbp+57h+var_98]
0x14002e077  test    rcx, rcx
0x14002e07a  jnz     short loc_14002E0CD
0x14002e07c  mov     eax, cs:dword_140075078
0x14002e082  cmp     eax, 2
0x14002e085  jbe     short loc_14002E0C1
0x14002e087  lea     rdi, aEsimpmWwanhelp_10; "ESIMPM::WwanHelper::QueryModemInfo"
0x14002e08e  mov     [rbp+57h+var_A8], rdi
0x14002e092  mov     [rbp+57h+var_B0], rbx
0x14002e096  mov     [rbp+57h+var_9C], r13d
0x14002e09a  lea     rax, [rbp+57h+var_A8]
0x14002e09e  mov     [rsp+120h+var_F0], rax
0x14002e0a3  lea     rax, [rbp+57h+var_B0]
0x14002e0a7  mov     [rsp+120h+var_F8], rax
0x14002e0ac  lea     rax, [rbp+57h+var_9C]
0x14002e0b0  mov     [rsp+120h+var_100], rax
0x14002e0b5  lea     rdx, byte_14006C379
0x14002e0bc  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x14002e0c1  mov     esi, 0Dh
0x14002e0c6  mov     eax, esi
0x14002e0c8  jmp     loc_14002E587
0x14002e0cd  mov     r9d, [rbp+57h+var_A0]
0x14002e0d1  mov     eax, 1C0h
0x14002e0d6  cmp     r9d, eax
0x14002e0d9  jnb     short loc_14002E100
0x14002e0db  mov     [rsp+120h+var_100], rax
0x14002e0e0  lea     r8, aWwanintfopcode_2; "WwanIntfOpcodeDeviceCaps query return b"...
0x14002e0e7  mov     rdx, rbx; struct _GUID *
0x14002e0ea  lea     rcx, aEsimpmWwanhelp_10; "ESIMPM::WwanHelper::QueryModemInfo"
0x14002e0f1  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x14002e0f6  mov     ebx, 0Dh
0x14002e0fb  jmp     loc_14002E57B
0x14002e100  lea     rdi, aEsimpmWwanhelp_10; "ESIMPM::WwanHelper::QueryModemInfo"
0x14002e107  test    dword ptr [rcx+60h], 100h
0x14002e10e  jnz     short loc_14002E145
0x14002e110  mov     eax, cs:dword_140075078
0x14002e116  cmp     eax, 3
0x14002e119  jbe     short loc_14002E141
0x14002e11b  mov     [rbp+57h+var_A8], rdi
0x14002e11f  mov     [rbp+57h+var_B0], rbx
0x14002e123  lea     rax, [rbp+57h+var_A8]
0x14002e127  mov     [rsp+120h+var_F8], rax
0x14002e12c  lea     rax, [rbp+57h+var_B0]
0x14002e130  mov     [rsp+120h+var_100], rax
0x14002e135  lea     rdx, byte_14006C329
0x14002e13c  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x14002e141  mov     rcx, [rbp+57h+var_98]
0x14002e145  mov     eax, [rcx+60h]
0x14002e148  mov     [rbx+10h], eax
0x14002e14b  mov     eax, [rcx+154h]
0x14002e151  mov     [rbx+14h], eax
0x14002e154  mov     dword ptr [rbx+18h], 1
0x14002e15b  mov     qword ptr [rbx+1Ch], 2
0x14002e163  mov     r15d, 9
0x14002e169  mov     [rbx+24h], r15d
0x14002e16d  lea     rdx, [rcx+88h]
0x14002e174  xorps   xmm0, xmm0
0x14002e177  movups  [rbp+57h+var_78], xmm0
0x14002e17b  xorps   xmm1, xmm1
0x14002e17e  movdqu  [rbp+57h+var_68], xmm1
0x14002e183  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14002e187  mov     r8, rsi
0x14002e18a  inc     r8
0x14002e18d  cmp     [rdx+r8*2], r13w
0x14002e192  jnz     short loc_14002E18A
0x14002e194  lea     rcx, [rbp+57h+var_78]
0x14002e198  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14002e19d  lea     r14, [rbx+30h]
0x14002e1a1  lea     rax, [rbp+57h+var_78]
0x14002e1a5  cmp     r14, rax
0x14002e1a8  jz      short loc_14002E1D5
0x14002e1aa  mov     rcx, r14
0x14002e1ad  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002e1b2  movups  xmm0, [rbp+57h+var_78]
0x14002e1b6  movups  xmmword ptr [r14], xmm0
0x14002e1ba  movups  xmm1, [rbp+57h+var_68]
0x14002e1be  movups  xmmword ptr [r14+10h], xmm1
0x14002e1c3  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14002e1cb  movdqu  [rbp+57h+var_68], xmm0
0x14002e1d0  mov     word ptr [rbp+57h+var_78], r13w
0x14002e1d5  lea     rcx, [rbp+57h+var_78]
0x14002e1d9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002e1de  mov     rdx, [rbp+57h+var_98]
0x14002e1e2  add     rdx, 0C8h
0x14002e1e9  xorps   xmm0, xmm0
0x14002e1ec  movups  [rbp+57h+var_58], xmm0
0x14002e1f0  xorps   xmm1, xmm1
0x14002e1f3  movdqu  [rbp+57h+var_48], xmm1
0x14002e1f8  inc     rsi
0x14002e1fb  cmp     [rdx+rsi*2], r13w
0x14002e200  jnz     short loc_14002E1F8
0x14002e202  mov     r8, rsi
0x14002e205  lea     rcx, [rbp+57h+var_58]
0x14002e209  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14002e20e  lea     rsi, [rbx+50h]
0x14002e212  lea     rax, [rbp+57h+var_58]
0x14002e216  cmp     rsi, rax
0x14002e219  jz      short loc_14002E244
0x14002e21b  mov     rcx, rsi
0x14002e21e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002e223  movups  xmm0, [rbp+57h+var_58]
0x14002e227  movups  xmmword ptr [rsi], xmm0
0x14002e22a  movups  xmm1, [rbp+57h+var_48]
0x14002e22e  movups  xmmword ptr [rsi+10h], xmm1
0x14002e232  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14002e23a  movdqu  [rbp+57h+var_48], xmm0
0x14002e23f  mov     word ptr [rbp+57h+var_58], r13w
0x14002e244  lea     rcx, [rbp+57h+var_58]
0x14002e248  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002e24d  mov     [rbp+57h+var_A0], r13d
0x14002e251  mov     [rbp+57h+var_90], r13
0x14002e255  mov     [rsp+120h+var_E8], r13
0x14002e25a  mov     [rsp+120h+var_F0], r13
0x14002e25f  lea     rax, [rbp+57h+var_90]
0x14002e263  mov     [rsp+120h+var_F8], rax
0x14002e268  lea     rax, [rbp+57h+var_A0]
0x14002e26c  mov     [rsp+120h+var_100], rax
0x14002e271  xor     r9d, r9d
0x14002e274  lea     r8d, [r9+2Eh]
0x14002e278  mov     rdx, rbx
0x14002e27b  mov     rcx, [r12]
0x14002e27f  call    cs:__imp_WwanQueryInterface
0x14002e285  mov     ecx, eax
0x14002e287  cmp     eax, 32h ; '2'
0x14002e28a  jnz     short loc_14002E2AA
0x14002e28c  mov     sil, r13b
0x14002e28f  mov     eax, cs:dword_140075078
0x14002e295  cmp     eax, 4
0x14002e298  jbe     loc_14002E3E7
0x14002e29e  lea     rdx, byte_14006C2D1
0x14002e2a5  jmp     loc_14002E365
0x14002e2aa  cmp     ecx, 139Fh
0x14002e2b0  jnz     short loc_14002E2F6
0x14002e2b2  mov     sil, r13b
0x14002e2b5  mov     eax, cs:dword_140075078
0x14002e2bb  cmp     eax, 4
0x14002e2be  jbe     short loc_14002E2E6
0x14002e2c0  mov     [rbp+57h+var_A8], rdi
0x14002e2c4  mov     [rbp+57h+var_B0], rbx
0x14002e2c8  lea     rax, [rbp+57h+var_A8]
0x14002e2cc  mov     [rsp+120h+var_F8], rax
0x14002e2d1  lea     rax, [rbp+57h+var_B0]
0x14002e2d5  mov     [rsp+120h+var_100], rax
0x14002e2da  lea     rdx, word_14006C26E
0x14002e2e1  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x14002e2e6  mov     dword ptr [rbx+18h], 2
0x14002e2ed  mov     [rbx+24h], r13d
0x14002e2f1  jmp     loc_14002E3E7
0x14002e2f6  test    ecx, ecx
0x14002e2f8  jz      short loc_14002E343
0x14002e2fa  mov     sil, r13b
0x14002e2fd  mov     eax, cs:dword_140075078
0x14002e303  cmp     eax, 2
0x14002e306  jbe     loc_14002E3E7
0x14002e30c  mov     [rbp+57h+var_A8], rdi
0x14002e310  mov     [rbp+57h+var_B0], rbx
0x14002e314  mov     [rbp+57h+var_9C], ecx
0x14002e317  lea     rax, [rbp+57h+var_A8]
0x14002e31b  mov     [rsp+120h+var_F0], rax
0x14002e320  lea     rax, [rbp+57h+var_B0]
0x14002e324  mov     [rsp+120h+var_F8], rax
0x14002e329  lea     rax, [rbp+57h+var_9C]
0x14002e32d  mov     [rsp+120h+var_100], rax
0x14002e332  lea     rdx, dword_14006C20C
0x14002e339  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x14002e33e  jmp     loc_14002E3E7
0x14002e343  mov     rcx, [rbp+57h+var_90]
0x14002e347  test    rcx, rcx
0x14002e34a  jnz     short loc_14002E386
0x14002e34c  mov     sil, r13b
0x14002e34f  mov     eax, cs:dword_140075078
0x14002e355  cmp     eax, 3
0x14002e358  jbe     loc_14002E3E7
0x14002e35e  lea     rdx, byte_14006C1BF
0x14002e365  lea     rax, [rbp+57h+var_A8]
0x14002e369  mov     [rsp+120h+var_F8], rax
0x14002e36e  lea     rax, [rbp+57h+var_B0]
0x14002e372  mov     [rsp+120h+var_100], rax
0x14002e377  mov     [rbp+57h+var_B0], rbx
0x14002e37b  mov     [rbp+57h+var_A8], rdi
0x14002e37f  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x14002e384  jmp     short loc_14002E3E7
0x14002e386  mov     sil, 1
0x14002e389  mov     r9d, [rbp+57h+var_A0]
0x14002e38d  cmp     r9d, 4
0x14002e391  jnb     short loc_14002E3B0
0x14002e393  mov     [rsp+120h+var_100], 4
0x14002e39c  lea     r8, aWwanintfopcode_2; "WwanIntfOpcodeDeviceCaps query return b"...
0x14002e3a3  mov     rdx, rbx; struct _GUID *
0x14002e3a6  mov     rcx, rdi; char *
0x14002e3a9  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x14002e3ae  jmp     short loc_14002E3E7
0x14002e3b0  mov     r9d, [rcx]
0x14002e3b3  lea     eax, [r9-1]
0x14002e3b7  cmp     eax, 1
0x14002e3ba  ja      short loc_14002E3D5
0x14002e3bc  mov     [rbx+18h], r9d
0x14002e3c0  mov     eax, [rcx+4]
0x14002e3c3  mov     [rbx+20h], eax
0x14002e3c6  cmp     dword ptr [rcx], 2
0x14002e3c9  jnz     short loc_14002E3CF
0x14002e3cb  mov     r15d, [rcx+8]
0x14002e3cf  mov     [rbx+24h], r15d
0x14002e3d3  jmp     short loc_14002E3E7
0x14002e3d5  lea     r8, aDwnumberofsims; "dwNumberOfSIMSlots %d is invalid"
0x14002e3dc  mov     rdx, rbx; struct _GUID *
0x14002e3df  mov     rcx, rdi; char *
0x14002e3e2  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x14002e3e7  cmp     dword ptr [rbx+18h], 2
0x14002e3eb  jnz     loc_14002E4FE
0x14002e3f1  mov     [rbp+57h+var_B0], r13
0x14002e3f5  mov     [rsp+120h+var_E8], r13
0x14002e3fa  mov     [rsp+120h+var_F0], r13
0x14002e3ff  lea     rax, [rbp+57h+var_B0]
0x14002e403  mov     [rsp+120h+var_F8], rax
0x14002e408  lea     rax, [rbp+57h+var_A0]
0x14002e40c  mov     [rsp+120h+var_100], rax
0x14002e411  xor     r9d, r9d
0x14002e414  lea     r8d, [r9+2Fh]
0x14002e418  mov     rdx, rbx
0x14002e41b  mov     rcx, [r12]
0x14002e41f  call    cs:__imp_WwanQueryInterface
0x14002e425  test    eax, eax
0x14002e427  jz      short loc_14002E46F
0x14002e429  mov     ecx, cs:dword_140075078
0x14002e42f  cmp     ecx, 2
0x14002e432  jbe     loc_14002E4FE
0x14002e438  mov     [rbp+57h+var_A8], rdi
0x14002e43c  mov     [rbp+57h+var_88], rbx
0x14002e440  mov     [rbp+57h+var_9C], eax
0x14002e443  lea     rax, [rbp+57h+var_A8]
0x14002e447  mov     [rsp+120h+var_F0], rax
0x14002e44c  lea     rax, [rbp+57h+var_88]
0x14002e450  mov     [rsp+120h+var_F8], rax
0x14002e455  lea     rax, [rbp+57h+var_9C]
0x14002e459  mov     [rsp+120h+var_100], rax
0x14002e45e  lea     rdx, dword_14006C164
0x14002e465  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x14002e46a  jmp     loc_14002E4FE
0x14002e46f  mov     rcx, [rbp+57h+var_B0]
0x14002e473  test    rcx, rcx
0x14002e476  jnz     short loc_14002E4AB
0x14002e478  mov     eax, cs:dword_140075078
0x14002e47e  cmp     eax, 3
0x14002e481  jbe     short loc_14002E4FE
0x14002e483  mov     [rbp+57h+var_88], rdi
0x14002e487  mov     [rbp+57h+var_A8], rbx
0x14002e48b  lea     rax, [rbp+57h+var_88]
0x14002e48f  mov     [rsp+120h+var_F8], rax
  ... truncated ...
```
