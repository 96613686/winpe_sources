# ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForConn(ESIMPM::CoreFSM::_CoreFSMEvent)

- ea: `0x14002c0a0`
- end: `0x14002c521`
- name: `?fsmEventHandler_WaitSIMReadyForConn@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z`
- size: `1153`
- prototype: `void __fastcall(unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting`

## callers

- `0x14002a854`

## callees

- `0x140001bd4`
- `0x140002f60`
- `0x140013df8`
- `0x140014f64`
- `0x14001f988`
- `0x140023158`
- `0x1400240fc`
- `0x14002564c`
- `0x140026ef4`
- `0x140026f60`
- `0x1400271cc`
- `0x140027e3c`
- `0x1400296b4`
- `0x1400297c0`
- `0x14002984c`
- `0x14002c0a0`
- `0x14002d7c8`

## string_xrefs

- `0x14002c147`: `ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForConn`
- `0x14002c189`: `ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForConn`
- `0x14002c4cd`: `ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForConn`
- `0x14002c182`: `eSIM profile (%s) timed out to be ready`

## pseudocode

```c
void __fastcall ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForConn(unsigned int *a1, unsigned int a2)
{
  __int64 v2; // r8
  BOOL v4; // edi
  __int64 v5; // r8
  _QWORD *v6; // r9
  __int64 *v7; // rax
  __int64 *v8; // rax
  __int64 *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 *v13; // rax
  __int64 *v14; // rax
  __int64 *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // r8
  int v21; // [rsp+60h] [rbp-A0h] BYREF
  BOOL v22; // [rsp+64h] [rbp-9Ch] BYREF
  int v23; // [rsp+68h] [rbp-98h] BYREF
  __int64 v24; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v25; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v26; // [rsp+80h] [rbp-80h] BYREF
  __int64 v27; // [rsp+88h] [rbp-78h] BYREF
  __int64 v28; // [rsp+90h] [rbp-70h] BYREF
  int v29; // [rsp+98h] [rbp-68h]
  __int128 v30; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v31; // [rsp+B0h] [rbp-50h]
  __int128 v32; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v33; // [rsp+C8h] [rbp-38h]
  char *v34[4]; // [rsp+D0h] [rbp-30h] BYREF
  char *v35[4]; // [rsp+F0h] [rbp-10h] BYREF
  char *Src[4]; // [rsp+110h] [rbp+10h] BYREF

  v2 = a2;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  v4 = *((_BYTE *)a1 + 408) == 0;
  switch ( a2 )
  {
    case 0u:
      ESIMPM::Log::Warning(
        "ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForConn",
        (const struct _GUID *)(a1 + 46),
        L"state (%u) with event (%u), ignored",
        *a1,
        0);
      break;
    case 1u:
      v19 = 0;
      v20 = 1;
      goto LABEL_37;
    case 4u:
      v19 = 15;
      v20 = 4;
LABEL_37:
      ESIMPM::CoreFSM::fsmStateTransition(a1, v19, v20);
      break;
    case 5u:
      ESIMPM::CoreFSM::ProcessPolicyChangeEvent((ESIMPM::CoreFSM *)a1);
      break;
    case 6u:
      LOBYTE(v2) = 1;
      ESIMPM::CoreFSM::ProcessEsimProfileReadinessThenStartScan(a1, 6, v2);
      break;
    case 0x18u:
      ESIMPM::CoreFSM::BuildProfilePriorityInfoData((__int64)a1, (__int64)&v32);
      ESIMPM::PackEsimProfilePriorityInfoData(&v32, &v30);
      if ( (unsigned int)dword_140075040 > 5
        && (qword_140075050 & 0x800000000000LL) != 0
        && (qword_140075058 & 0x800000000000LL) == qword_140075058 )
      {
        v13 = (__int64 *)ESIMPM::AnonymizeIccId(v34);
        if ( (unsigned __int64)v13[3] > 7 )
          v13 = (__int64 *)*v13;
        v27 = (__int64)v13;
        v23 = *(_DWORD *)(*((_QWORD *)a1 + 40) + 16LL);
        v28 = v30;
        v29 = (unsigned __int16)(WORD4(v30) - v30);
        v22 = v4;
        v21 = 0;
        v14 = (__int64 *)ESIMPM::AnonymizeIccId(v35);
        if ( (unsigned __int64)v14[3] > 7 )
          v14 = (__int64 *)*v14;
        v26 = v14;
        v15 = (__int64 *)ESIMPM::AnonymizeIccId(Src);
        if ( (unsigned __int64)v15[3] > 7 )
          v15 = (__int64 *)*v15;
        v25 = v15;
        v24 = 16779264;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v16,
          (__int64)&dword_14006B7EC,
          v17,
          v18,
          (__int64)&v24,
          &v25,
          &v26,
          (__int64)&v21,
          (__int64)&v22,
          &v28,
          (__int64)&v23,
          (__int64 **)&v27);
        std::wstring::_Tidy_deallocate(Src);
        std::wstring::_Tidy_deallocate(v35);
        std::wstring::_Tidy_deallocate(v34);
      }
      v19 = 4;
      v20 = 24;
      goto LABEL_37;
    case 0x19u:
      v6 = (_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 40) + 24LL) + 40LL * a1[82]);
      if ( v6[3] > 7u )
        v6 = (_QWORD *)*v6;
      ESIMPM::Log::Error(
        "ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForConn",
        (wchar_t *)a1 + 92,
        L"eSIM profile (%s) timed out to be ready",
        v6);
      ESIMPM::CoreFSM::BuildProfilePriorityInfoData((__int64)a1, (__int64)&v32);
      ESIMPM::PackEsimProfilePriorityInfoData(&v32, &v30);
      if ( (unsigned int)dword_140075040 > 5
        && (qword_140075050 & 0x800000000000LL) != 0
        && (qword_140075058 & 0x800000000000LL) == qword_140075058 )
      {
        v7 = (__int64 *)ESIMPM::AnonymizeIccId(Src);
        if ( (unsigned __int64)v7[3] > 7 )
          v7 = (__int64 *)*v7;
        v24 = (__int64)v7;
        v21 = *(_DWORD *)(*((_QWORD *)a1 + 40) + 16LL);
        v28 = v30;
        v29 = (unsigned __int16)(WORD4(v30) - v30);
        v22 = v4;
        v23 = 1460;
        v8 = (__int64 *)ESIMPM::AnonymizeIccId(v35);
        if ( (unsigned __int64)v8[3] > 7 )
          v8 = (__int64 *)*v8;
        v25 = v8;
        v9 = (__int64 *)ESIMPM::AnonymizeIccId(v34);
        if ( (unsigned __int64)v9[3] > 7 )
          v9 = (__int64 *)*v9;
        v26 = v9;
        v27 = 16779264;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v10,
          (__int64)byte_14006B72B,
          v11,
          v12,
          (__int64)&v27,
          &v26,
          &v25,
          (__int64)&v23,
          (__int64)&v22,
          &v28,
          (__int64)&v21,
          (__int64 **)&v24);
        std::wstring::_Tidy_deallocate(v34);
        std::wstring::_Tidy_deallocate(v35);
        std::wstring::_Tidy_deallocate(Src);
      }
      ESIMPM::CoreFSM::FindNextProfileToEnable((__int64)a1, 0x19u, 0, 0);
      break;
    default:
      ESIMPM::Log::Verbose(
        "ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForConn",
        (const struct _GUID *)(a1 + 46),
        L"state (%u) with event (%u), ignored",
        *a1,
        a2);
      break;
  }
  std::wstring::operator=((char **)a1 + 52, (char **)a1 + 66, v5);
  std::vector<unsigned char>::~vector<unsigned char>((char **)&v30);
  std::vector<ESIMPM::_ESIM_PROFILE_PRIORITY_INFO>::~vector<ESIMPM::_ESIM_PROFILE_PRIORITY_INFO>((char **)&v32);
}

```

## disassembly

```asm
0x14002c0a0  mov     [rsp-8+arg_10], rbx
0x14002c0a5  mov     [rsp-8+arg_18], rdi
0x14002c0aa  push    rbp
0x14002c0ab  lea     rbp, [rsp-40h]
0x14002c0b0  sub     rsp, 140h
0x14002c0b7  mov     rax, cs:__security_cookie
0x14002c0be  xor     rax, rsp
0x14002c0c1  mov     [rbp+40h+var_10], rax
0x14002c0c5  mov     r8d, edx
0x14002c0c8  mov     rbx, rcx
0x14002c0cb  xorps   xmm0, xmm0
0x14002c0ce  movdqu  [rbp+40h+var_88], xmm0
0x14002c0d3  mov     [rbp+40h+var_78], 0
0x14002c0db  movdqu  [rbp+40h+var_A0], xmm0
0x14002c0e0  mov     [rbp+40h+var_90], 0
0x14002c0e8  xor     edi, edi
0x14002c0ea  cmp     [rcx+198h], dil
0x14002c0f1  setz    dil
0x14002c0f5  mov     ecx, edx
0x14002c0f7  test    edx, edx
0x14002c0f9  jz      loc_14002C4B4
0x14002c0ff  sub     ecx, 1
0x14002c102  jz      loc_14002C4A4
0x14002c108  sub     ecx, 3
0x14002c10b  jz      loc_14002C499
0x14002c111  sub     ecx, 1
0x14002c114  jz      loc_14002C48F
0x14002c11a  sub     ecx, 1
0x14002c11d  jz      loc_14002C47D
0x14002c123  sub     ecx, 12h
0x14002c126  jz      loc_14002C30F
0x14002c12c  cmp     ecx, 1
0x14002c12f  jz      short loc_14002C158
0x14002c131  lea     rdx, [rbx+0B8h]; struct _GUID *
0x14002c138  mov     dword ptr [rsp+140h+var_120], r8d
0x14002c13d  mov     r9d, [rbx]
0x14002c140  lea     r8, aStateUWithEven; "state (%u) with event (%u), ignored"
0x14002c147  lea     rcx, aEsimpmCorefsmF_15; "ESIMPM::CoreFSM::fsmEventHandler_WaitSI"...
0x14002c14e  call    ?Verbose@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Verbose(char const *,_GUID const *,ushort const *,...)
0x14002c153  jmp     loc_14002C4D9
0x14002c158  mov     eax, [rbx+148h]
0x14002c15e  lea     rdx, [rax+rax*4]
0x14002c162  mov     rax, [rbx+140h]
0x14002c169  mov     rcx, [rax+18h]
0x14002c16d  lea     r9, [rcx+rdx*8]
0x14002c171  cmp     qword ptr [r9+18h], 7
0x14002c176  jbe     short loc_14002C17B
0x14002c178  mov     r9, [r9]
0x14002c17b  lea     rdx, [rbx+0B8h]; struct _GUID *
0x14002c182  lea     r8, aEsimProfileSTi; "eSIM profile (%s) timed out to be ready"
0x14002c189  lea     rcx, aEsimpmCorefsmF_15; "ESIMPM::CoreFSM::fsmEventHandler_WaitSI"...
0x14002c190  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x14002c195  lea     rdx, [rbp+40h+var_88]
0x14002c199  mov     rcx, rbx
0x14002c19c  call    ?BuildProfilePriorityInfoData@CoreFSM@ESIMPM@@AEAAXAEAV?$vector@U_ESIM_PROFILE_PRIORITY_INFO@ESIMPM@@V?$allocator@U_ESIM_PROFILE_PRIORITY_INFO@ESIMPM@@@std@@@std@@@Z; ESIMPM::CoreFSM::BuildProfilePriorityInfoData(std::vector<ESIMPM::_ESIM_PROFILE_PRIORITY_INFO> &)
0x14002c1a1  lea     rdx, [rbp+40h+var_A0]
0x14002c1a5  lea     rcx, [rbp+40h+var_88]
0x14002c1a9  call    ESIMPM__PackEsimProfilePriorityInfoData
0x14002c1ae  mov     eax, cs:dword_140075040
0x14002c1b4  cmp     eax, 5
0x14002c1b7  jbe     loc_14002C2F8
0x14002c1bd  mov     rdx, cs:qword_140075058
0x14002c1c4  mov     rax, cs:qword_140075050
0x14002c1cb  mov     rcx, 800000000000h
0x14002c1d5  test    rcx, rax
0x14002c1d8  jz      loc_14002C2F8
0x14002c1de  mov     rax, rdx
0x14002c1e1  and     rax, rcx
0x14002c1e4  cmp     rax, rdx
0x14002c1e7  jnz     loc_14002C2F8
0x14002c1ed  lea     rdx, [rbx+1E8h]
0x14002c1f4  lea     rcx, [rbp+40h+Src]; Src
0x14002c1f8  call    ?AnonymizeIccId@ESIMPM@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; ESIMPM::AnonymizeIccId(std::wstring const &)
0x14002c1fd  nop
0x14002c1fe  cmp     qword ptr [rax+18h], 7
0x14002c203  jbe     short loc_14002C208
0x14002c205  mov     rax, [rax]
0x14002c208  mov     [rsp+140h+var_D0], rax
0x14002c20d  mov     rax, [rbx+140h]
0x14002c214  mov     ecx, [rax+10h]
0x14002c217  mov     [rsp+140h+var_E0], ecx
0x14002c21b  mov     rcx, qword ptr [rbp+40h+var_A0]
0x14002c21f  mov     [rbp+40h+var_B0], rcx
0x14002c223  movzx   eax, word ptr [rbp+40h+var_A0+8]
0x14002c227  sub     ax, cx
0x14002c22a  movzx   eax, ax
0x14002c22d  mov     [rbp+40h+var_A8], eax
0x14002c230  mov     [rsp+140h+var_DC], edi
0x14002c234  mov     [rsp+140h+var_D8], 5B4h
0x14002c23c  lea     rdx, [rbx+210h]
0x14002c243  lea     rcx, [rbp+40h+var_50]; Src
0x14002c247  call    ?AnonymizeIccId@ESIMPM@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; ESIMPM::AnonymizeIccId(std::wstring const &)
0x14002c24c  nop
0x14002c24d  cmp     qword ptr [rax+18h], 7
0x14002c252  jbe     short loc_14002C257
0x14002c254  mov     rax, [rax]
0x14002c257  mov     [rsp+140h+var_C8], rax
0x14002c25c  lea     rdx, [rbx+1A0h]
0x14002c263  lea     rcx, [rbp+40h+var_70]; Src
0x14002c267  call    ?AnonymizeIccId@ESIMPM@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; ESIMPM::AnonymizeIccId(std::wstring const &)
0x14002c26c  cmp     qword ptr [rax+18h], 7
0x14002c271  jbe     short loc_14002C276
0x14002c273  mov     rax, [rax]
0x14002c276  mov     [rbp+40h+var_C0], rax
0x14002c27a  mov     [rbp+40h+var_B8], 1000800h
0x14002c282  lea     rax, [rsp+140h+var_D0]
0x14002c287  mov     [rsp+140h+var_E8], rax
0x14002c28c  lea     rax, [rsp+140h+var_E0]
0x14002c291  mov     [rsp+140h+var_F0], rax
0x14002c296  lea     rax, [rbp+40h+var_B0]
0x14002c29a  mov     [rsp+140h+var_F8], rax
0x14002c29f  lea     rax, [rsp+140h+var_DC]
0x14002c2a4  mov     [rsp+140h+var_100], rax
0x14002c2a9  lea     rax, [rsp+140h+var_D8]
0x14002c2ae  mov     [rsp+140h+var_108], rax
0x14002c2b3  lea     rax, [rsp+140h+var_C8]
0x14002c2b8  mov     [rsp+140h+var_110], rax
0x14002c2bd  lea     rax, [rbp+40h+var_C0]
0x14002c2c1  mov     [rsp+140h+var_118], rax
0x14002c2c6  lea     rax, [rbp+40h+var_B8]
0x14002c2ca  mov     [rsp+140h+var_120], rax
0x14002c2cf  lea     rdx, byte_14006B72B
0x14002c2d6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U3@U_tlgWrapperPtrSize@@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@5AEBU_tlgWrapperPtrSize@@54@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperPtrSize const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x14002c2db  lea     rcx, [rbp+40h+var_70]
0x14002c2df  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002c2e4  nop
0x14002c2e5  lea     rcx, [rbp+40h+var_50]
0x14002c2e9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002c2ee  nop
0x14002c2ef  lea     rcx, [rbp+40h+Src]
0x14002c2f3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002c2f8  xor     r9d, r9d
0x14002c2fb  xor     r8d, r8d
0x14002c2fe  lea     edx, [r9+19h]
0x14002c302  mov     rcx, rbx
0x14002c305  call    ?FindNextProfileToEnable@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@_N1@Z; ESIMPM::CoreFSM::FindNextProfileToEnable(ESIMPM::CoreFSM::_CoreFSMEvent,bool,bool)
0x14002c30a  jmp     loc_14002C4D9
0x14002c30f  lea     rdx, [rbp+40h+var_88]
0x14002c313  mov     rcx, rbx
0x14002c316  call    ?BuildProfilePriorityInfoData@CoreFSM@ESIMPM@@AEAAXAEAV?$vector@U_ESIM_PROFILE_PRIORITY_INFO@ESIMPM@@V?$allocator@U_ESIM_PROFILE_PRIORITY_INFO@ESIMPM@@@std@@@std@@@Z; ESIMPM::CoreFSM::BuildProfilePriorityInfoData(std::vector<ESIMPM::_ESIM_PROFILE_PRIORITY_INFO> &)
0x14002c31b  lea     rdx, [rbp+40h+var_A0]
0x14002c31f  lea     rcx, [rbp+40h+var_88]
0x14002c323  call    ESIMPM__PackEsimProfilePriorityInfoData
0x14002c328  mov     eax, cs:dword_140075040
0x14002c32e  cmp     eax, 5
0x14002c331  jbe     loc_14002C472
0x14002c337  mov     rdx, cs:qword_140075058
0x14002c33e  mov     rax, cs:qword_140075050
0x14002c345  mov     rcx, 800000000000h
0x14002c34f  test    rcx, rax
0x14002c352  jz      loc_14002C472
0x14002c358  mov     rax, rdx
0x14002c35b  and     rax, rcx
0x14002c35e  cmp     rax, rdx
0x14002c361  jnz     loc_14002C472
0x14002c367  lea     rdx, [rbx+1E8h]
0x14002c36e  lea     rcx, [rbp+40h+var_70]; Src
0x14002c372  call    ?AnonymizeIccId@ESIMPM@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; ESIMPM::AnonymizeIccId(std::wstring const &)
0x14002c377  nop
0x14002c378  cmp     qword ptr [rax+18h], 7
0x14002c37d  jbe     short loc_14002C382
0x14002c37f  mov     rax, [rax]
0x14002c382  mov     [rbp+40h+var_B8], rax
0x14002c386  mov     rax, [rbx+140h]
0x14002c38d  mov     ecx, [rax+10h]
0x14002c390  mov     [rsp+140h+var_D8], ecx
0x14002c394  mov     rcx, qword ptr [rbp+40h+var_A0]
0x14002c398  mov     [rbp+40h+var_B0], rcx
0x14002c39c  movzx   eax, word ptr [rbp+40h+var_A0+8]
0x14002c3a0  sub     ax, cx
0x14002c3a3  movzx   eax, ax
0x14002c3a6  mov     [rbp+40h+var_A8], eax
0x14002c3a9  mov     [rsp+140h+var_DC], edi
0x14002c3ad  mov     [rsp+140h+var_E0], 0
0x14002c3b5  lea     rdx, [rbx+210h]
0x14002c3bc  lea     rcx, [rbp+40h+var_50]; Src
0x14002c3c0  call    ?AnonymizeIccId@ESIMPM@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; ESIMPM::AnonymizeIccId(std::wstring const &)
0x14002c3c5  nop
0x14002c3c6  cmp     qword ptr [rax+18h], 7
0x14002c3cb  jbe     short loc_14002C3D0
0x14002c3cd  mov     rax, [rax]
0x14002c3d0  mov     [rbp+40h+var_C0], rax
0x14002c3d4  lea     rdx, [rbx+1A0h]
0x14002c3db  lea     rcx, [rbp+40h+Src]; Src
0x14002c3df  call    ?AnonymizeIccId@ESIMPM@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; ESIMPM::AnonymizeIccId(std::wstring const &)
0x14002c3e4  cmp     qword ptr [rax+18h], 7
0x14002c3e9  jbe     short loc_14002C3EE
0x14002c3eb  mov     rax, [rax]
0x14002c3ee  mov     [rsp+140h+var_C8], rax
0x14002c3f3  mov     [rsp+140h+var_D0], 1000800h
0x14002c3fc  lea     rax, [rbp+40h+var_B8]
0x14002c400  mov     [rsp+140h+var_E8], rax
0x14002c405  lea     rax, [rsp+140h+var_D8]
0x14002c40a  mov     [rsp+140h+var_F0], rax
0x14002c40f  lea     rax, [rbp+40h+var_B0]
0x14002c413  mov     [rsp+140h+var_F8], rax
0x14002c418  lea     rax, [rsp+140h+var_DC]
0x14002c41d  mov     [rsp+140h+var_100], rax
0x14002c422  lea     rax, [rsp+140h+var_E0]
0x14002c427  mov     [rsp+140h+var_108], rax
0x14002c42c  lea     rax, [rbp+40h+var_C0]
0x14002c430  mov     [rsp+140h+var_110], rax
0x14002c435  lea     rax, [rsp+140h+var_C8]
0x14002c43a  mov     [rsp+140h+var_118], rax
0x14002c43f  lea     rax, [rsp+140h+var_D0]
0x14002c444  mov     [rsp+140h+var_120], rax
0x14002c449  lea     rdx, dword_14006B7EC
0x14002c450  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U3@U_tlgWrapperPtrSize@@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@5AEBU_tlgWrapperPtrSize@@54@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperPtrSize const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x14002c455  lea     rcx, [rbp+40h+Src]
0x14002c459  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002c45e  nop
0x14002c45f  lea     rcx, [rbp+40h+var_50]
0x14002c463  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002c468  nop
0x14002c469  lea     rcx, [rbp+40h+var_70]
0x14002c46d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002c472  mov     edx, 4
0x14002c477  lea     r8d, [rdx+14h]
0x14002c47b  jmp     short loc_14002C4AA
0x14002c47d  mov     r8b, 1
0x14002c480  mov     edx, 6
0x14002c485  mov     rcx, rbx
0x14002c488  call    ?ProcessEsimProfileReadinessThenStartScan@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@_N@Z; ESIMPM::CoreFSM::ProcessEsimProfileReadinessThenStartScan(ESIMPM::CoreFSM::_CoreFSMEvent,bool)
0x14002c48d  jmp     short loc_14002C4D9
0x14002c48f  mov     rcx, rbx; this
0x14002c492  call    ?ProcessPolicyChangeEvent@CoreFSM@ESIMPM@@AEAAXXZ; ESIMPM::CoreFSM::ProcessPolicyChangeEvent(void)
0x14002c497  jmp     short loc_14002C4D9
0x14002c499  mov     edx, 0Fh
0x14002c49e  lea     r8d, [rdx-0Bh]
0x14002c4a2  jmp     short loc_14002C4AA
0x14002c4a4  xor     edx, edx
0x14002c4a6  lea     r8d, [rdx+1]
0x14002c4aa  mov     rcx, rbx
0x14002c4ad  call    ?fsmStateTransition@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMState@12@W4_CoreFSMEvent@12@K@Z; ESIMPM::CoreFSM::fsmStateTransition(ESIMPM::CoreFSM::_CoreFSMState,ESIMPM::CoreFSM::_CoreFSMEvent,ulong)
0x14002c4b2  jmp     short loc_14002C4D9
0x14002c4b4  lea     rdx, [rbx+0B8h]; struct _GUID *
0x14002c4bb  mov     dword ptr [rsp+140h+var_120], 0
0x14002c4c3  mov     r9d, [rbx]
0x14002c4c6  lea     r8, aStateUWithEven; "state (%u) with event (%u), ignored"
0x14002c4cd  lea     rcx, aEsimpmCorefsmF_15; "ESIMPM::CoreFSM::fsmEventHandler_WaitSI"...
0x14002c4d4  call    ?Warning@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Warning(char const *,_GUID const *,ushort const *,...)
0x14002c4d9  lea     rdx, [rbx+210h]
0x14002c4e0  lea     rcx, [rbx+1A0h]
0x14002c4e7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14002c4ec  nop
0x14002c4ed  lea     rcx, [rbp+40h+var_A0]
0x14002c4f1  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x14002c4f6  nop
0x14002c4f7  lea     rcx, [rbp+40h+var_88]
0x14002c4fb  call    ??1?$vector@U_ESIM_PROFILE_PRIORITY_INFO@ESIMPM@@V?$allocator@U_ESIM_PROFILE_PRIORITY_INFO@ESIMPM@@@std@@@std@@QEAA@XZ; std::vector<ESIMPM::_ESIM_PROFILE_PRIORITY_INFO>::~vector<ESIMPM::_ESIM_PROFILE_PRIORITY_INFO>(void)
0x14002c500  mov     rcx, [rbp+40h+var_10]
0x14002c504  xor     rcx, rsp; StackCookie
0x14002c507  call    __security_check_cookie
0x14002c50c  lea     r11, [rsp+140h+var_s0]
0x14002c514  mov     rbx, [r11+20h]
0x14002c518  mov     rdi, [r11+28h]
0x14002c51c  mov     rsp, r11
0x14002c51f  pop     rbp
0x14002c520  retn
```
