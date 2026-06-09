# ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForEF(ESIMPM::CoreFSM::_CoreFSMEvent)

- ea: `0x14002c528`
- end: `0x14002ca29`
- name: `?fsmEventHandler_WaitSIMReadyForEF@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z`
- size: `1281`
- prototype: `void __fastcall(unsigned int *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x14002a854`

## callees

- `0x140001bd4`
- `0x140002f60`
- `0x140013df8`
- `0x14001f988`
- `0x140020620`
- `0x140022f0c`
- `0x140023158`
- `0x1400240fc`
- `0x14002564c`
- `0x140026ef4`
- `0x140026f60`
- `0x1400271cc`
- `0x1400296b4`
- `0x14002c528`
- `0x14002d7c8`

## string_xrefs

- `0x14002c5ad`: `ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForEF`
- `0x14002c7a6`: `ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForEF`
- `0x14002c972`: `ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForEF`
- `0x14002c99a`: `ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForEF`
- `0x14002c9d7`: `ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForEF`

## pseudocode

```c
void __fastcall ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForEF(unsigned int *a1, int a2)
{
  __int64 v3; // r8
  __int64 *v4; // rax
  __int64 *v5; // rax
  __int64 *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  const wchar_t **v10; // rdi
  const wchar_t **v11; // rsi
  const wchar_t *v12; // rdx
  size_t v13; // r8
  const wchar_t *v14; // rcx
  __int64 *v15; // rax
  __int64 *v16; // rax
  __int64 *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // r8
  int v23; // [rsp+60h] [rbp-A0h] BYREF
  int v24; // [rsp+64h] [rbp-9Ch] BYREF
  int v25; // [rsp+68h] [rbp-98h] BYREF
  __int64 v26; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v27; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v28; // [rsp+80h] [rbp-80h] BYREF
  __int64 v29; // [rsp+88h] [rbp-78h] BYREF
  __int64 v30; // [rsp+90h] [rbp-70h] BYREF
  int v31; // [rsp+98h] [rbp-68h]
  __int128 v32; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v33; // [rsp+B0h] [rbp-50h]
  __int128 v34; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v35; // [rsp+C8h] [rbp-38h]
  char *v36[4]; // [rsp+D0h] [rbp-30h] BYREF
  char *v37[4]; // [rsp+F0h] [rbp-10h] BYREF
  char *Src[4]; // [rsp+110h] [rbp+10h] BYREF

  v34 = 0;
  v35 = 0;
  v32 = 0;
  v33 = 0;
  switch ( a2 )
  {
    case 0:
      ESIMPM::Log::Warning(
        "ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForEF",
        (const struct _GUID *)(a1 + 46),
        L"state (%u) with event (%u), ignored",
        *a1,
        0);
      goto LABEL_48;
    case 1:
      v21 = 0;
      v22 = 1;
      goto LABEL_46;
    case 4:
      ESIMPM::Log::Warning(
        "ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForEF",
        (const struct _GUID *)(a1 + 46),
        L"state (%u) with event (%u)",
        *a1,
        4);
      v22 = 4;
      v21 = 15;
LABEL_46:
      ESIMPM::CoreFSM::fsmStateTransition(a1, v21, v22);
      goto LABEL_48;
  }
  if ( a2 != 24 )
  {
    if ( a2 == 25 )
    {
      ESIMPM::CoreFSM::BuildProfilePriorityInfoData((__int64)a1, (__int64)&v34);
      ESIMPM::PackEsimProfilePriorityInfoData(&v34, &v32);
      if ( (unsigned int)dword_140075040 > 5
        && (qword_140075050 & 0x800000000000LL) != 0
        && (qword_140075058 & 0x800000000000LL) == qword_140075058 )
      {
        v4 = (__int64 *)ESIMPM::AnonymizeIccId(Src);
        if ( (unsigned __int64)v4[3] > 7 )
          v4 = (__int64 *)*v4;
        v26 = (__int64)v4;
        v23 = *(_DWORD *)(*((_QWORD *)a1 + 40) + 16LL);
        v30 = v32;
        v31 = (unsigned __int16)(WORD4(v32) - v32);
        v24 = 2;
        v25 = 1460;
        v5 = (__int64 *)ESIMPM::AnonymizeIccId(v37);
        if ( (unsigned __int64)v5[3] > 7 )
          v5 = (__int64 *)*v5;
        v27 = v5;
        v6 = (__int64 *)ESIMPM::AnonymizeIccId(v36);
        if ( (unsigned __int64)v6[3] > 7 )
          v6 = (__int64 *)*v6;
        v28 = v6;
        v29 = 16779264;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v7,
          (__int64)byte_14006B459,
          v8,
          v9,
          (__int64)&v29,
          &v28,
          &v27,
          (__int64)&v25,
          (__int64)&v24,
          &v30,
          (__int64)&v23,
          (__int64 **)&v26);
        std::wstring::_Tidy_deallocate(v36);
        std::wstring::_Tidy_deallocate(v37);
        std::wstring::_Tidy_deallocate(Src);
      }
    }
    else
    {
      ESIMPM::Log::Verbose(
        "ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForEF",
        (const struct _GUID *)(a1 + 46),
        L"state (%u) with event (%u), ignored",
        *a1,
        a2);
    }
    goto LABEL_48;
  }
  v10 = (const wchar_t **)(a1 + 140);
  v11 = (const wchar_t **)(a1 + 132);
  if ( *((_QWORD *)a1 + 73) <= 7u )
    v12 = (const wchar_t *)(a1 + 140);
  else
    v12 = *v10;
  v13 = *((_QWORD *)a1 + 68);
  if ( *((_QWORD *)a1 + 69) <= 7u )
    v14 = (const wchar_t *)(a1 + 132);
  else
    v14 = *v11;
  if ( v13 == *((_QWORD *)a1 + 72) && (!v13 || !wmemcmp(v14, v12, v13)) )
  {
    *((_QWORD *)a1 + 72) = 0;
    if ( *((_QWORD *)a1 + 73) > 7u )
      v10 = (const wchar_t **)*v10;
    *(_WORD *)v10 = 0;
    ESIMPM::Log::Info(
      "ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForEF",
      (const struct _GUID *)(a1 + 46),
      L"state (%u) with event (%u)",
      *a1,
      24);
    ESIMPM::CoreFSM::BuildProfilePriorityInfoData((__int64)a1, (__int64)&v34);
    ESIMPM::PackEsimProfilePriorityInfoData(&v34, &v32);
    if ( (unsigned int)dword_140075040 > 5
      && (qword_140075050 & 0x800000000000LL) != 0
      && (qword_140075058 & 0x800000000000LL) == qword_140075058 )
    {
      v15 = (__int64 *)ESIMPM::AnonymizeIccId(v36);
      if ( (unsigned __int64)v15[3] > 7 )
        v15 = (__int64 *)*v15;
      v29 = (__int64)v15;
      v25 = *(_DWORD *)(*((_QWORD *)a1 + 40) + 16LL);
      v30 = v32;
      v31 = (unsigned __int16)(WORD4(v32) - v32);
      v24 = 2;
      v23 = 0;
      v16 = (__int64 *)ESIMPM::AnonymizeIccId(v37);
      if ( (unsigned __int64)v16[3] > 7 )
        v16 = (__int64 *)*v16;
      v28 = v16;
      v17 = (__int64 *)ESIMPM::AnonymizeIccId(Src);
      if ( (unsigned __int64)v17[3] > 7 )
        v17 = (__int64 *)*v17;
      v27 = v17;
      v26 = 16779264;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v18,
        (__int64)word_14006B51A,
        v19,
        v20,
        (__int64)&v26,
        &v27,
        &v28,
        (__int64)&v23,
        (__int64)&v24,
        &v30,
        (__int64)&v25,
        (__int64 **)&v29);
      std::wstring::_Tidy_deallocate(Src);
      std::wstring::_Tidy_deallocate(v37);
      std::wstring::_Tidy_deallocate(v36);
    }
    v21 = 11;
    v22 = 24;
    goto LABEL_46;
  }
  if ( *((_QWORD *)a1 + 69) > 7u )
    v11 = (const wchar_t **)*v11;
  if ( *((_QWORD *)a1 + 73) > 7u )
    v10 = (const wchar_t **)*v10;
  ESIMPM::Log::Warning(
    "ESIMPM::CoreFSM::fsmEventHandler_WaitSIMReadyForEF",
    (const struct _GUID *)(a1 + 46),
    L"state (%u) with event (%u), expecting %s, size %d; received %s, size %d ignored",
    *a1,
    24,
    v10,
    *((_QWORD *)a1 + 72),
    v11,
    *((_QWORD *)a1 + 68));
LABEL_48:
  std::wstring::operator=((char **)a1 + 52, (char **)a1 + 66, v3);
  std::vector<unsigned char>::~vector<unsigned char>((char **)&v32);
  std::vector<ESIMPM::_ESIM_PROFILE_PRIORITY_INFO>::~vector<ESIMPM::_ESIM_PROFILE_PRIORITY_INFO>((char **)&v34);
}

```

## disassembly

```asm
0x14002c528  mov     [rsp-8+arg_10], rbx
0x14002c52d  push    rbp
0x14002c52e  push    rsi
0x14002c52f  push    rdi
0x14002c530  lea     rbp, [rsp-40h]
0x14002c535  sub     rsp, 140h
0x14002c53c  mov     rax, cs:__security_cookie
0x14002c543  xor     rax, rsp
0x14002c546  mov     [rbp+50h+var_20], rax
0x14002c54a  mov     r8d, edx
0x14002c54d  mov     rbx, rcx
0x14002c550  xorps   xmm0, xmm0
0x14002c553  movdqu  [rbp+50h+var_98], xmm0
0x14002c558  mov     [rbp+50h+var_88], 0
0x14002c560  movdqu  [rbp+50h+var_B0], xmm0
0x14002c565  mov     [rbp+50h+var_A0], 0
0x14002c56d  mov     ecx, edx
0x14002c56f  test    edx, edx
0x14002c571  jz      loc_14002C9BE
0x14002c577  sub     ecx, 1
0x14002c57a  jz      loc_14002C9AE
0x14002c580  sub     ecx, 3
0x14002c583  jz      loc_14002C980
0x14002c589  sub     ecx, 14h
0x14002c58c  jz      loc_14002C72A
0x14002c592  cmp     ecx, 1
0x14002c595  jz      short loc_14002C5BE
0x14002c597  lea     rdx, [rbx+0B8h]; struct _GUID *
0x14002c59e  mov     dword ptr [rsp+150h+var_130], r8d
0x14002c5a3  mov     r9d, [rbx]
0x14002c5a6  lea     r8, aStateUWithEven; "state (%u) with event (%u), ignored"
0x14002c5ad  lea     rcx, aEsimpmCorefsmF; "ESIMPM::CoreFSM::fsmEventHandler_WaitSI"...
0x14002c5b4  call    ?Verbose@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Verbose(char const *,_GUID const *,ushort const *,...)
0x14002c5b9  jmp     loc_14002C9E3
0x14002c5be  lea     rdx, [rbp+50h+var_98]
0x14002c5c2  mov     rcx, rbx
0x14002c5c5  call    ?BuildProfilePriorityInfoData@CoreFSM@ESIMPM@@AEAAXAEAV?$vector@U_ESIM_PROFILE_PRIORITY_INFO@ESIMPM@@V?$allocator@U_ESIM_PROFILE_PRIORITY_INFO@ESIMPM@@@std@@@std@@@Z; ESIMPM::CoreFSM::BuildProfilePriorityInfoData(std::vector<ESIMPM::_ESIM_PROFILE_PRIORITY_INFO> &)
0x14002c5ca  lea     rdx, [rbp+50h+var_B0]
0x14002c5ce  lea     rcx, [rbp+50h+var_98]
0x14002c5d2  call    ESIMPM__PackEsimProfilePriorityInfoData
0x14002c5d7  mov     eax, cs:dword_140075040
0x14002c5dd  cmp     eax, 5
0x14002c5e0  jbe     loc_14002C9E3
0x14002c5e6  mov     rdx, cs:qword_140075058
0x14002c5ed  mov     rax, cs:qword_140075050
0x14002c5f4  mov     rcx, 800000000000h
0x14002c5fe  test    rcx, rax
0x14002c601  jz      loc_14002C9E3
0x14002c607  mov     rax, rdx
0x14002c60a  and     rax, rcx
0x14002c60d  cmp     rax, rdx
0x14002c610  jnz     loc_14002C9E3
0x14002c616  lea     rdx, [rbx+1E8h]
0x14002c61d  lea     rcx, [rbp+50h+Src]; Src
0x14002c621  call    ?AnonymizeIccId@ESIMPM@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; ESIMPM::AnonymizeIccId(std::wstring const &)
0x14002c626  nop
0x14002c627  cmp     qword ptr [rax+18h], 7
0x14002c62c  jbe     short loc_14002C631
0x14002c62e  mov     rax, [rax]
0x14002c631  mov     [rsp+150h+var_E0], rax
0x14002c636  mov     rax, [rbx+140h]
0x14002c63d  mov     ecx, [rax+10h]
0x14002c640  mov     [rsp+150h+var_F0], ecx
0x14002c644  mov     rcx, qword ptr [rbp+50h+var_B0]
0x14002c648  mov     [rbp+50h+var_C0], rcx
0x14002c64c  movzx   eax, word ptr [rbp+50h+var_B0+8]
0x14002c650  sub     ax, cx
0x14002c653  movzx   eax, ax
0x14002c656  mov     [rbp+50h+var_B8], eax
0x14002c659  mov     [rsp+150h+var_EC], 2
0x14002c661  mov     [rsp+150h+var_E8], 5B4h
0x14002c669  lea     rdx, [rbx+210h]
0x14002c670  lea     rcx, [rbp+50h+var_60]; Src
0x14002c674  call    ?AnonymizeIccId@ESIMPM@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; ESIMPM::AnonymizeIccId(std::wstring const &)
0x14002c679  nop
0x14002c67a  cmp     qword ptr [rax+18h], 7
0x14002c67f  jbe     short loc_14002C684
0x14002c681  mov     rax, [rax]
0x14002c684  mov     [rsp+150h+var_D8], rax
0x14002c689  lea     rdx, [rbx+1A0h]
0x14002c690  lea     rcx, [rbp+50h+var_80]; Src
0x14002c694  call    ?AnonymizeIccId@ESIMPM@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; ESIMPM::AnonymizeIccId(std::wstring const &)
0x14002c699  cmp     qword ptr [rax+18h], 7
0x14002c69e  jbe     short loc_14002C6A3
0x14002c6a0  mov     rax, [rax]
0x14002c6a3  mov     [rbp+50h+var_D0], rax
0x14002c6a7  mov     [rbp+50h+var_C8], 1000800h
0x14002c6af  lea     rax, [rsp+150h+var_E0]
0x14002c6b4  mov     [rsp+150h+var_F8], rax
0x14002c6b9  lea     rax, [rsp+150h+var_F0]
0x14002c6be  mov     [rsp+150h+var_100], rax
0x14002c6c3  lea     rax, [rbp+50h+var_C0]
0x14002c6c7  mov     [rsp+150h+var_108], rax
0x14002c6cc  lea     rax, [rsp+150h+var_EC]
0x14002c6d1  mov     [rsp+150h+var_110], rax
0x14002c6d6  lea     rax, [rsp+150h+var_E8]
0x14002c6db  mov     [rsp+150h+var_118], rax
0x14002c6e0  lea     rax, [rsp+150h+var_D8]
0x14002c6e5  mov     [rsp+150h+var_120], rax
0x14002c6ea  lea     rax, [rbp+50h+var_D0]
0x14002c6ee  mov     [rsp+150h+var_128], rax
0x14002c6f3  lea     rax, [rbp+50h+var_C8]
0x14002c6f7  mov     [rsp+150h+var_130], rax
0x14002c6fc  lea     rdx, byte_14006B459
0x14002c703  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U3@U_tlgWrapperPtrSize@@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@5AEBU_tlgWrapperPtrSize@@54@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperPtrSize const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x14002c708  lea     rcx, [rbp+50h+var_80]
0x14002c70c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002c711  nop
0x14002c712  lea     rcx, [rbp+50h+var_60]
0x14002c716  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002c71b  nop
0x14002c71c  lea     rcx, [rbp+50h+Src]
0x14002c720  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002c725  jmp     loc_14002C9E3
0x14002c72a  lea     rdi, [rbx+230h]
0x14002c731  lea     rsi, [rbx+210h]
0x14002c738  cmp     qword ptr [rdi+18h], 7
0x14002c73d  jbe     short loc_14002C744
0x14002c73f  mov     rdx, [rdi]
0x14002c742  jmp     short loc_14002C747
0x14002c744  mov     rdx, rdi; S2
0x14002c747  mov     r8, [rsi+10h]; N
0x14002c74b  cmp     qword ptr [rsi+18h], 7
0x14002c750  jbe     short loc_14002C757
0x14002c752  mov     rcx, [rsi]
0x14002c755  jmp     short loc_14002C75A
0x14002c757  mov     rcx, rsi; S1
0x14002c75a  cmp     r8, [rdi+10h]
0x14002c75e  jnz     loc_14002C923
0x14002c764  test    r8, r8
0x14002c767  jz      short loc_14002C776
0x14002c769  call    wmemcmp
0x14002c76e  test    eax, eax
0x14002c770  jnz     loc_14002C923
0x14002c776  mov     qword ptr [rdi+10h], 0
0x14002c77e  cmp     qword ptr [rdi+18h], 7
0x14002c783  jbe     short loc_14002C788
0x14002c785  mov     rdi, [rdi]
0x14002c788  xor     eax, eax
0x14002c78a  mov     [rdi], ax
0x14002c78d  lea     rdx, [rbx+0B8h]; struct _GUID *
0x14002c794  mov     dword ptr [rsp+150h+var_130], 18h
0x14002c79c  mov     r9d, [rbx]
0x14002c79f  lea     r8, aStateUWithEven_1; "state (%u) with event (%u)"
0x14002c7a6  lea     rcx, aEsimpmCorefsmF; "ESIMPM::CoreFSM::fsmEventHandler_WaitSI"...
0x14002c7ad  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x14002c7b2  lea     rdx, [rbp+50h+var_98]
0x14002c7b6  mov     rcx, rbx
0x14002c7b9  call    ?BuildProfilePriorityInfoData@CoreFSM@ESIMPM@@AEAAXAEAV?$vector@U_ESIM_PROFILE_PRIORITY_INFO@ESIMPM@@V?$allocator@U_ESIM_PROFILE_PRIORITY_INFO@ESIMPM@@@std@@@std@@@Z; ESIMPM::CoreFSM::BuildProfilePriorityInfoData(std::vector<ESIMPM::_ESIM_PROFILE_PRIORITY_INFO> &)
0x14002c7be  lea     rdx, [rbp+50h+var_B0]
0x14002c7c2  lea     rcx, [rbp+50h+var_98]
0x14002c7c6  call    ESIMPM__PackEsimProfilePriorityInfoData
0x14002c7cb  mov     eax, cs:dword_140075040
0x14002c7d1  cmp     eax, 5
0x14002c7d4  jbe     loc_14002C915
0x14002c7da  mov     rdx, cs:qword_140075058
0x14002c7e1  mov     rax, cs:qword_140075050
0x14002c7e8  mov     rcx, 800000000000h
0x14002c7f2  test    rcx, rax
0x14002c7f5  jz      loc_14002C915
0x14002c7fb  mov     rax, rdx
0x14002c7fe  and     rax, rcx
0x14002c801  cmp     rax, rdx
0x14002c804  jnz     loc_14002C915
0x14002c80a  lea     rdx, [rbx+1E8h]
0x14002c811  lea     rcx, [rbp+50h+var_80]; Src
0x14002c815  call    ?AnonymizeIccId@ESIMPM@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; ESIMPM::AnonymizeIccId(std::wstring const &)
0x14002c81a  nop
0x14002c81b  cmp     qword ptr [rax+18h], 7
0x14002c820  jbe     short loc_14002C825
0x14002c822  mov     rax, [rax]
0x14002c825  mov     [rbp+50h+var_C8], rax
0x14002c829  mov     rax, [rbx+140h]
0x14002c830  mov     ecx, [rax+10h]
0x14002c833  mov     [rsp+150h+var_E8], ecx
0x14002c837  mov     rcx, qword ptr [rbp+50h+var_B0]
0x14002c83b  mov     [rbp+50h+var_C0], rcx
0x14002c83f  movzx   eax, word ptr [rbp+50h+var_B0+8]
0x14002c843  sub     ax, cx
0x14002c846  movzx   eax, ax
0x14002c849  mov     [rbp+50h+var_B8], eax
0x14002c84c  mov     [rsp+150h+var_EC], 2
0x14002c854  mov     [rsp+150h+var_F0], 0
0x14002c85c  mov     rdx, rsi
0x14002c85f  lea     rcx, [rbp+50h+var_60]; Src
0x14002c863  call    ?AnonymizeIccId@ESIMPM@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; ESIMPM::AnonymizeIccId(std::wstring const &)
0x14002c868  nop
0x14002c869  cmp     qword ptr [rax+18h], 7
0x14002c86e  jbe     short loc_14002C873
0x14002c870  mov     rax, [rax]
0x14002c873  mov     [rbp+50h+var_D0], rax
0x14002c877  lea     rdx, [rbx+1A0h]
0x14002c87e  lea     rcx, [rbp+50h+Src]; Src
0x14002c882  call    ?AnonymizeIccId@ESIMPM@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; ESIMPM::AnonymizeIccId(std::wstring const &)
0x14002c887  cmp     qword ptr [rax+18h], 7
0x14002c88c  jbe     short loc_14002C891
0x14002c88e  mov     rax, [rax]
0x14002c891  mov     [rsp+150h+var_D8], rax
0x14002c896  mov     [rsp+150h+var_E0], 1000800h
0x14002c89f  lea     rax, [rbp+50h+var_C8]
0x14002c8a3  mov     [rsp+150h+var_F8], rax
0x14002c8a8  lea     rax, [rsp+150h+var_E8]
0x14002c8ad  mov     [rsp+150h+var_100], rax
0x14002c8b2  lea     rax, [rbp+50h+var_C0]
0x14002c8b6  mov     [rsp+150h+var_108], rax
0x14002c8bb  lea     rax, [rsp+150h+var_EC]
0x14002c8c0  mov     [rsp+150h+var_110], rax
0x14002c8c5  lea     rax, [rsp+150h+var_F0]
0x14002c8ca  mov     [rsp+150h+var_118], rax
0x14002c8cf  lea     rax, [rbp+50h+var_D0]
0x14002c8d3  mov     [rsp+150h+var_120], rax
0x14002c8d8  lea     rax, [rsp+150h+var_D8]
0x14002c8dd  mov     [rsp+150h+var_128], rax
0x14002c8e2  lea     rax, [rsp+150h+var_E0]
0x14002c8e7  mov     [rsp+150h+var_130], rax
0x14002c8ec  lea     rdx, word_14006B51A
0x14002c8f3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U3@U_tlgWrapperPtrSize@@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@5AEBU_tlgWrapperPtrSize@@54@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperPtrSize const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x14002c8f8  lea     rcx, [rbp+50h+Src]
0x14002c8fc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002c901  nop
0x14002c902  lea     rcx, [rbp+50h+var_60]
0x14002c906  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002c90b  nop
0x14002c90c  lea     rcx, [rbp+50h+var_80]
0x14002c910  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002c915  mov     edx, 0Bh
0x14002c91a  lea     r8d, [rdx+0Dh]
0x14002c91e  jmp     loc_14002C9B4
0x14002c923  mov     rcx, [rbx+220h]
0x14002c92a  cmp     qword ptr [rsi+18h], 7
0x14002c92f  jbe     short loc_14002C934
0x14002c931  mov     rsi, [rsi]
0x14002c934  mov     rax, [rbx+240h]
0x14002c93b  cmp     qword ptr [rdi+18h], 7
0x14002c940  jbe     short loc_14002C945
0x14002c942  mov     rdi, [rdi]
0x14002c945  lea     rdx, [rbx+0B8h]; struct _GUID *
0x14002c94c  mov     [rsp+150h+var_110], rcx
0x14002c951  mov     [rsp+150h+var_118], rsi
0x14002c956  mov     [rsp+150h+var_120], rax
0x14002c95b  mov     [rsp+150h+var_128], rdi
0x14002c960  mov     dword ptr [rsp+150h+var_130], 18h
0x14002c968  mov     r9d, [rbx]
0x14002c96b  lea     r8, aStateUWithEven_6; "state (%u) with event (%u), expecting %"...
0x14002c972  lea     rcx, aEsimpmCorefsmF; "ESIMPM::CoreFSM::fsmEventHandler_WaitSI"...
0x14002c979  call    ?Warning@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Warning(char const *,_GUID const *,ushort const *,...)
0x14002c97e  jmp     short loc_14002C9E3
0x14002c980  lea     rdx, [rbx+0B8h]; struct _GUID *
0x14002c987  mov     edi, 4
0x14002c98c  mov     dword ptr [rsp+150h+var_130], edi
0x14002c990  mov     r9d, [rbx]
0x14002c993  lea     r8, aStateUWithEven_1; "state (%u) with event (%u)"
0x14002c99a  lea     rcx, aEsimpmCorefsmF; "ESIMPM::CoreFSM::fsmEventHandler_WaitSI"...
0x14002c9a1  call    ?Warning@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Warning(char const *,_GUID const *,ushort const *,...)
0x14002c9a6  mov     r8d, edi
0x14002c9a9  lea     edx, [rdi+0Bh]
0x14002c9ac  jmp     short loc_14002C9B4
0x14002c9ae  xor     edx, edx
0x14002c9b0  lea     r8d, [rdx+1]
0x14002c9b4  mov     rcx, rbx
0x14002c9b7  call    ?fsmStateTransition@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMState@12@W4_CoreFSMEvent@12@K@Z; ESIMPM::CoreFSM::fsmStateTransition(ESIMPM::CoreFSM::_CoreFSMState,ESIMPM::CoreFSM::_CoreFSMEvent,ulong)
0x14002c9bc  jmp     short loc_14002C9E3
0x14002c9be  lea     rdx, [rbx+0B8h]; struct _GUID *
0x14002c9c5  mov     dword ptr [rsp+150h+var_130], 0
0x14002c9cd  mov     r9d, [rbx]
0x14002c9d0  lea     r8, aStateUWithEven; "state (%u) with event (%u), ignored"
0x14002c9d7  lea     rcx, aEsimpmCorefsmF; "ESIMPM::CoreFSM::fsmEventHandler_WaitSI"...
0x14002c9de  call    ?Warning@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Warning(char const *,_GUID const *,ushort const *,...)
0x14002c9e3  lea     rdx, [rbx+210h]
0x14002c9ea  lea     rcx, [rbx+1A0h]
0x14002c9f1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14002c9f6  nop
0x14002c9f7  lea     rcx, [rbp+50h+var_B0]
0x14002c9fb  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x14002ca00  nop
0x14002ca01  lea     rcx, [rbp+50h+var_98]
0x14002ca05  call    ??1?$vector@U_ESIM_PROFILE_PRIORITY_INFO@ESIMPM@@V?$allocator@U_ESIM_PROFILE_PRIORITY_INFO@ESIMPM@@@std@@@std@@QEAA@XZ; std::vector<ESIMPM::_ESIM_PROFILE_PRIORITY_INFO>::~vector<ESIMPM::_ESIM_PROFILE_PRIORITY_INFO>(void)
0x14002ca0a  mov     rcx, [rbp+50h+var_20]
0x14002ca0e  xor     rcx, rsp; StackCookie
0x14002ca11  call    __security_check_cookie
0x14002ca16  mov     rbx, [rsp+150h+arg_10]
0x14002ca1e  add     rsp, 140h
0x14002ca25  pop     rdi
0x14002ca26  pop     rsi
0x14002ca27  pop     rbp
0x14002ca28  retn
```
