# EapLm::BaseEapLibraryManager::AddOneEapMethod(RegistryKey const &,_EAP_METHOD_TYPE const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)

- ea: `0x18002c06c`
- end: `0x18002c53a`
- name: `?AddOneEapMethod@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@AEBU_EAP_METHOD_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z`
- size: `1230`
- prototype: `__int64 __fastcall(__int64, __int64, __int128 *, __int64)`
- caller_count: `3`
- callee_count: `24`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002b8dc`
- `0x18002ca50`
- `0x18002d040`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x180006ccc`
- `0x18000bf94`
- `0x18000eb74`
- `0x18000eb94`
- `0x180012c10`
- `0x180012d18`
- `0x18001647c`
- `0x1800165a4`
- `0x180016c54`
- `0x18001736c`
- `0x18002a974`
- `0x18002ab2c`
- `0x18002ac44`
- `0x18002b088`
- `0x18002b0c8`
- `0x18002b108`
- `0x18002b298`
- `0x18002b544`
- `0x18002b7d0`
- `0x18002b85c`
- `0x18002c06c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c407`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c407`

## pseudocode

```c
__int64 __fastcall EapLm::BaseEapLibraryManager::AddOneEapMethod(__int64 a1, __int64 a2, __int128 *a3, __int64 a4)
{
  char v7; // si
  __int64 v8; // rax
  __int64 v9; // rax
  int v10; // ecx
  int v11; // r8d
  __int64 v12; // rax
  unsigned int v13; // r14d
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  unsigned int v20; // esi
  _QWORD *v21; // rcx
  int v22; // ecx
  int v23; // r8d
  __int64 v25; // rax
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v29; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v30; // [rsp+58h] [rbp-A8h]
  __int128 v31; // [rsp+68h] [rbp-98h]
  _BYTE v32[16]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v33; // [rsp+88h] [rbp-78h]
  ReferenceCounted *v34; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v35; // [rsp+A0h] [rbp-60h]
  _BYTE v36[40]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v37[64]; // [rsp+E0h] [rbp-20h] BYREF

  v7 = 0;
  LODWORD(v28) = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v29 = *a3;
  v8 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a4);
  *(_QWORD *)&v30 = BasicSimpleString<wchar_t>::Copy(v8);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v32);
  v9 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 8);
  if ( (unsigned int)RegistryKey::ReadMuiString(a2, v9, v32) )
  {
    v12 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 8);
    RegistryKey::QueryValue(a2, v12, v32);
  }
  if ( v33 )
  {
    v13 = 3;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v14 = std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(&v34, a4);
      LODWORD(v28) = 1;
      v15 = std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v36, v14, v32);
      v7 = 3;
      v16 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v15);
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, v16);
    }
    if ( (v7 & 2) != 0 )
    {
      v7 &= ~2u;
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v36);
    }
    if ( (v7 & 1) != 0 )
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(&v34);
    v17 = std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(&v34, a4);
    v18 = std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v36, v17, v32);
    v19 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v18);
    *((_QWORD *)&v30 + 1) = BasicSimpleString<wchar_t>::Copy(v19);
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v36);
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(&v34);
    LODWORD(v28) = 0;
    RegistryKey::QueryValue(a2, L"Properties", &v28);
    LODWORD(v31) = v28;
    LODWORD(v28) = 0;
    RegistryKey::QueryValue(a2, L"TreatAsMsMethod", &v28);
    v20 = v28;
    if ( (_DWORD)v28 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          53,
          WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
          (unsigned int)v28);
        v21 = WPP_GLOBAL_Control;
      }
      v13 = v20;
    }
    else
    {
      v21 = WPP_GLOBAL_Control;
    }
    if ( !HIDWORD(v29) || !(_BYTE)v29 )
    {
      if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 1) != 0 )
        WPP_SF_dddd(
          v21[2],
          54,
          WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
          (unsigned __int8)v29,
          HIDWORD(v29),
          DWORD1(v29),
          DWORD2(v29));
      goto LABEL_20;
    }
    if ( !(*(unsigned __int8 (__fastcall **)(__int64, __int128 *, _QWORD, __int64))(*(_QWORD *)a1 + 56LL))(
            a1,
            &v29,
            v13,
            a2) )
    {
LABEL_20:
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v32);
      return Free<HeapAllocator>(&v29);
    }
    if ( (Microsoft_Windows_EapHostEnableBits & 0x40) != 0 )
    {
      LOBYTE(v23) = v29;
      McTemplateU0uqqq_EtwEventWriteTransfer(
        v22,
        (unsigned int)MethodAdditionEvent,
        v23,
        HIDWORD(v29),
        SBYTE4(v29),
        SBYTE8(v29));
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_dddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
        (unsigned __int8)v29,
        HIDWORD(v29),
        DWORD1(v29),
        DWORD2(v29));
    v34 = 0;
    v28 = 0;
    SmartPointer<EapLm::IEapMethod>::operator=(&v34, &v28);
    v35 = v13;
    LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(&v28, a1 + 80);
    v25 = std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>(
            v37,
            &v29,
            &v34);
    std::map<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::insert<std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>,0>(
      a1 + 136,
      v36,
      v25);
    std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::~pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>(v37);
    if ( v36[8] )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_34;
      v27 = 56;
    }
    else
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_34;
      v27 = 57;
    }
    WPP_SF_(v26[2], v27, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
LABEL_34:
    LeaveCriticalSection((LPCRITICAL_SECTION)(v28 + 16));
    if ( v34 )
      ReferenceCounted::Release(v34);
    goto LABEL_20;
  }
  if ( (byte_18004AF81 & 1) != 0 )
  {
    LOBYTE(v11) = v29;
    McTemplateU0uqqq_EtwEventWriteTransfer(
      v10,
      (unsigned int)MethodAddFailed,
      v11,
      HIDWORD(v29),
      SBYTE4(v29),
      SBYTE8(v29));
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_dddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52,
      WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
      (unsigned __int8)v29,
      HIDWORD(v29),
      DWORD1(v29),
      DWORD2(v29));
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v32);
  return Free<HeapAllocator>(&v29);
}

```

## disassembly

```asm
0x18002c06c  push    rbp
0x18002c06e  push    rbx
0x18002c06f  push    rsi
0x18002c070  push    rdi
0x18002c071  push    r12
0x18002c073  push    r13
0x18002c075  push    r14
0x18002c077  push    r15
0x18002c079  lea     rbp, [rsp-38h]
0x18002c07e  sub     rsp, 138h
0x18002c085  mov     rax, cs:__security_cookie
0x18002c08c  xor     rax, rsp
0x18002c08f  mov     [rbp+70h+var_50], rax
0x18002c093  mov     r13, r9
0x18002c096  mov     r12, rdx
0x18002c099  mov     r15, rcx
0x18002c09c  xor     esi, esi
0x18002c09e  mov     dword ptr [rsp+170h+var_130], esi
0x18002c0a2  xorps   xmm0, xmm0
0x18002c0a5  movups  [rsp+170h+var_128], xmm0
0x18002c0aa  movups  [rsp+170h+var_118], xmm0
0x18002c0af  movups  [rsp+170h+var_108], xmm0
0x18002c0b4  mov     al, [r8]
0x18002c0b7  mov     byte ptr [rsp+170h+var_128], al
0x18002c0bb  movzx   eax, word ptr [r8+1]
0x18002c0c0  mov     word ptr [rsp+170h+var_128+1], ax
0x18002c0c5  mov     al, [r8+3]
0x18002c0c9  mov     byte ptr [rsp+170h+var_128+3], al
0x18002c0cd  mov     eax, [r8+4]
0x18002c0d1  mov     dword ptr [rsp+170h+var_128+4], eax
0x18002c0d5  mov     eax, [r8+8]
0x18002c0d9  mov     dword ptr [rsp+170h+var_128+8], eax
0x18002c0dd  mov     eax, [r8+0Ch]
0x18002c0e1  mov     dword ptr [rsp+170h+var_128+0Ch], eax
0x18002c0e5  mov     rcx, r9
0x18002c0e8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002c0ed  mov     rcx, rax
0x18002c0f0  call    ?Copy@?$BasicSimpleString@_W@@SAPEA_WPEB_W@Z; BasicSimpleString<wchar_t>::Copy(wchar_t const *)
0x18002c0f5  mov     qword ptr [rsp+170h+var_118], rax
0x18002c0fa  lea     rcx, [rsp+170h+var_F8]
0x18002c0ff  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x18002c104  nop
0x18002c105  lea     rcx, [r15+8]
0x18002c109  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002c10e  lea     r8, [rsp+170h+var_F8]
0x18002c113  mov     rdx, rax
0x18002c116  mov     rcx, r12
0x18002c119  call    ?ReadMuiString@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::ReadMuiString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18002c11e  test    eax, eax
0x18002c120  jz      short loc_18002C13B
0x18002c122  lea     rcx, [r15+8]
0x18002c126  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002c12b  lea     r8, [rsp+170h+var_F8]
0x18002c130  mov     rdx, rax
0x18002c133  mov     rcx, r12
0x18002c136  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18002c13b  cmp     [rbp+70h+var_E8], 0
0x18002c140  jz      loc_18002C488
0x18002c146  lea     rbx, WPP_GLOBAL_Control
0x18002c14d  mov     r14d, 3
0x18002c153  lea     rdi, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18002c15a  mov     rax, cs:WPP_GLOBAL_Control
0x18002c161  cmp     rax, rbx
0x18002c164  jz      short loc_18002C1B7
0x18002c166  test    byte ptr [rax+1Ch], 4
0x18002c16a  jz      short loc_18002C1B7
0x18002c16c  mov     rdx, r13
0x18002c16f  lea     rcx, [rbp+70h+var_D8]
0x18002c173  call    ??$?H_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,wchar_t const * const)
0x18002c178  nop
0x18002c179  mov     dword ptr [rsp+170h+var_130], 1
0x18002c181  lea     r8, [rsp+170h+var_F8]
0x18002c186  mov     rdx, rax
0x18002c189  lea     rcx, [rbp+70h+var_B8]
0x18002c18d  call    ??$?H_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &&,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18002c192  mov     esi, r14d
0x18002c195  mov     rcx, rax
0x18002c198  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002c19d  lea     edx, [r14+30h]
0x18002c1a1  mov     r9, rax
0x18002c1a4  mov     r8, rdi
0x18002c1a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c1ae  mov     rcx, [rcx+10h]
0x18002c1b2  call    WPP_SF_S
0x18002c1b7  test    sil, 2
0x18002c1bb  jz      short loc_18002C1CA
0x18002c1bd  and     esi, 0FFFFFFFDh
0x18002c1c0  lea     rcx, [rbp+70h+var_B8]
0x18002c1c4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18002c1c9  nop
0x18002c1ca  test    sil, 1
0x18002c1ce  jz      short loc_18002C1D9
0x18002c1d0  lea     rcx, [rbp+70h+var_D8]
0x18002c1d4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18002c1d9  mov     rdx, r13
0x18002c1dc  lea     rcx, [rbp+70h+var_D8]
0x18002c1e0  call    ??$?H_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,wchar_t const * const)
0x18002c1e5  nop
0x18002c1e6  lea     r8, [rsp+170h+var_F8]
0x18002c1eb  mov     rdx, rax
0x18002c1ee  lea     rcx, [rbp+70h+var_B8]
0x18002c1f2  call    ??$?H_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &&,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18002c1f7  nop
0x18002c1f8  mov     rcx, rax
0x18002c1fb  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002c200  mov     rcx, rax
0x18002c203  call    ?Copy@?$BasicSimpleString@_W@@SAPEA_WPEB_W@Z; BasicSimpleString<wchar_t>::Copy(wchar_t const *)
0x18002c208  mov     qword ptr [rsp+170h+var_118+8], rax
0x18002c20d  lea     rcx, [rbp+70h+var_B8]
0x18002c211  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18002c216  nop
0x18002c217  lea     rcx, [rbp+70h+var_D8]
0x18002c21b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18002c220  xor     r13d, r13d
0x18002c223  mov     dword ptr [rsp+170h+var_130], r13d
0x18002c228  lea     r8, [rsp+170h+var_130]
0x18002c22d  lea     rdx, aProperties; "Properties"
0x18002c234  mov     rcx, r12
0x18002c237  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x18002c23c  mov     eax, dword ptr [rsp+170h+var_130]
0x18002c240  mov     dword ptr [rsp+170h+var_108], eax
0x18002c244  mov     dword ptr [rsp+170h+var_130], r13d
0x18002c249  lea     r8, [rsp+170h+var_130]
0x18002c24e  lea     rdx, aTreatasmsmetho; "TreatAsMsMethod"
0x18002c255  mov     rcx, r12
0x18002c258  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x18002c25d  mov     esi, dword ptr [rsp+170h+var_130]
0x18002c261  test    esi, esi
0x18002c263  jz      short loc_18002C296
0x18002c265  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c26c  cmp     rcx, rbx
0x18002c26f  jz      short loc_18002C291
0x18002c271  test    byte ptr [rcx+1Ch], 4
0x18002c275  jz      short loc_18002C291
0x18002c277  lea     edx, [r13+35h]
0x18002c27b  mov     r9d, esi
0x18002c27e  mov     r8, rdi
0x18002c281  mov     rcx, [rcx+10h]
0x18002c285  call    WPP_SF_d
0x18002c28a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c291  mov     r14d, esi
0x18002c294  jmp     short loc_18002C29D
0x18002c296  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c29d  movzx   eax, byte ptr [rsp+170h+var_128]
0x18002c2a2  mov     r8d, dword ptr [rsp+170h+var_128+0Ch]
0x18002c2a7  test    r8d, r8d
0x18002c2aa  jz      loc_18002C438
0x18002c2b0  test    al, al
0x18002c2b2  jz      loc_18002C438
0x18002c2b8  mov     rax, [r15]
0x18002c2bb  mov     r9, r12
0x18002c2be  mov     r8d, r14d
0x18002c2c1  lea     rdx, [rsp+170h+var_128]
0x18002c2c6  mov     rcx, r15
0x18002c2c9  mov     rax, [rax+38h]
0x18002c2cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2d2  test    al, al
0x18002c2d4  jnz     short loc_18002C2F1
0x18002c2d6  lea     rcx, [rsp+170h+var_F8]
0x18002c2db  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18002c2e0  nop
0x18002c2e1  lea     rcx, [rsp+170h+var_128]
0x18002c2e6  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<HeapAllocator>(_EAP_METHOD_INFO &)
0x18002c2eb  nop
0x18002c2ec  jmp     loc_18002C51A
0x18002c2f1  test    cs:Microsoft_Windows_EapHostEnableBits, 40h
0x18002c2f8  jz      short loc_18002C320
0x18002c2fa  mov     eax, dword ptr [rsp+170h+var_128+8]
0x18002c2fe  mov     [rsp+170h+var_148], eax
0x18002c302  mov     eax, dword ptr [rsp+170h+var_128+4]
0x18002c306  mov     [rsp+170h+var_150], eax
0x18002c30a  mov     r9d, dword ptr [rsp+170h+var_128+0Ch]
0x18002c30f  mov     r8b, byte ptr [rsp+170h+var_128]
0x18002c314  lea     rdx, MethodAdditionEvent
0x18002c31b  call    McTemplateU0uqqq_EtwEventWriteTransfer
0x18002c320  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c327  cmp     rcx, rbx
0x18002c32a  jz      short loc_18002C361
0x18002c32c  test    byte ptr [rcx+1Ch], 4
0x18002c330  jz      short loc_18002C361
0x18002c332  movzx   r9d, byte ptr [rsp+170h+var_128]
0x18002c338  mov     edx, 37h ; '7'
0x18002c33d  mov     eax, dword ptr [rsp+170h+var_128+8]
0x18002c341  mov     [rsp+170h+var_140], eax
0x18002c345  mov     eax, dword ptr [rsp+170h+var_128+4]
0x18002c349  mov     [rsp+170h+var_148], eax
0x18002c34d  mov     eax, dword ptr [rsp+170h+var_128+0Ch]
0x18002c351  mov     [rsp+170h+var_150], eax
0x18002c355  mov     r8, rdi
0x18002c358  mov     rcx, [rcx+10h]
0x18002c35c  call    WPP_SF_dddd
0x18002c361  mov     [rbp+70h+var_D8], r13
0x18002c365  mov     [rsp+170h+var_130], r13
0x18002c36a  lea     rdx, [rsp+170h+var_130]
0x18002c36f  lea     rcx, [rbp+70h+var_D8]
0x18002c373  call    ??4?$SmartPointer@UIEapMethod@EapLm@@@@QEAAAEAV0@AEBV0@@Z; SmartPointer<EapLm::IEapMethod>::operator=(SmartPointer<EapLm::IEapMethod> const &)
0x18002c378  mov     [rbp+70h+var_D0], r14d
0x18002c37c  lea     rdx, [r15+50h]
0x18002c380  lea     rcx, [rsp+170h+var_130]
0x18002c385  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x18002c38a  nop
0x18002c38b  lea     r8, [rbp+70h+var_D8]
0x18002c38f  lea     rdx, [rsp+170h+var_128]
0x18002c394  lea     rcx, [rbp+70h+var_90]
0x18002c398  call    ??$?0AEAV?$crt_ref@U_EAP_METHOD_INFO@@@@AEAU_EapMethodSlot@EapLm@@$0A@@?$pair@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@QEAA@AEAV?$crt_ref@U_EAP_METHOD_INFO@@@@AEAU_EapMethodSlot@EapLm@@@Z; std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>(crt_ref<_EAP_METHOD_INFO> &,EapLm::_EapMethodSlot &)
0x18002c39d  nop
0x18002c39e  lea     rcx, [r15+88h]
0x18002c3a5  mov     r8, rax
0x18002c3a8  lea     rdx, [rbp+70h+var_B8]
0x18002c3ac  call    ??$insert@U?$pair@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@$0A@@?$map@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@U?$less@V?$crt_ref@U_EAP_METHOD_INFO@@@@@std@@V?$allocator@U?$pair@$$CBV?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@@5@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@1@@Z; std::map<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::insert<std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>,0>(std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot> &&)
0x18002c3b1  nop
0x18002c3b2  lea     rcx, [rbp+70h+var_90]
0x18002c3b6  call    ??1?$pair@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@QEAA@XZ; std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::~pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>(void)
0x18002c3bb  cmp     [rbp+70h+var_B0], r13b
0x18002c3bf  jz      short loc_18002C3DA
0x18002c3c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c3c8  cmp     rcx, rbx
0x18002c3cb  jz      short loc_18002C3FE
0x18002c3cd  test    byte ptr [rcx+1Ch], 4
0x18002c3d1  jz      short loc_18002C3FE
0x18002c3d3  mov     edx, 38h ; '8'
0x18002c3d8  jmp     short loc_18002C3F1
0x18002c3da  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c3e1  cmp     rcx, rbx
0x18002c3e4  jz      short loc_18002C3FE
0x18002c3e6  test    byte ptr [rcx+1Ch], 4
0x18002c3ea  jz      short loc_18002C3FE
0x18002c3ec  mov     edx, 39h ; '9'
0x18002c3f1  mov     r8, rdi
0x18002c3f4  mov     rcx, [rcx+10h]
0x18002c3f8  call    WPP_SF_
0x18002c3fd  nop
0x18002c3fe  mov     rcx, [rsp+170h+var_130]
0x18002c403  add     rcx, 10h; lpCriticalSection
0x18002c407  call    cs:__imp_LeaveCriticalSection
0x18002c40d  nop
0x18002c40e  mov     rcx, [rbp+70h+var_D8]; this
0x18002c412  test    rcx, rcx
0x18002c415  jz      short loc_18002C41D
0x18002c417  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x18002c41c  nop
0x18002c41d  lea     rcx, [rsp+170h+var_F8]
0x18002c422  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18002c427  nop
0x18002c428  lea     rcx, [rsp+170h+var_128]
0x18002c42d  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<HeapAllocator>(_EAP_METHOD_INFO &)
0x18002c432  nop
0x18002c433  jmp     loc_18002C51A
0x18002c438  cmp     rcx, rbx
0x18002c43b  jz      short loc_18002C46D
0x18002c43d  test    byte ptr [rcx+1Ch], 1
0x18002c441  jz      short loc_18002C46D
0x18002c443  mov     r9d, eax
0x18002c446  mov     edx, 36h ; '6'
0x18002c44b  mov     eax, dword ptr [rsp+170h+var_128+8]
0x18002c44f  mov     [rsp+170h+var_140], eax
0x18002c453  mov     eax, dword ptr [rsp+170h+var_128+4]
0x18002c457  mov     [rsp+170h+var_148], eax
0x18002c45b  mov     [rsp+170h+var_150], r8d
0x18002c460  mov     r8, rdi
0x18002c463  mov     rcx, [rcx+10h]
0x18002c467  call    WPP_SF_dddd
0x18002c46c  nop
0x18002c46d  lea     rcx, [rsp+170h+var_F8]
0x18002c472  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18002c477  nop
0x18002c478  lea     rcx, [rsp+170h+var_128]
0x18002c47d  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<HeapAllocator>(_EAP_METHOD_INFO &)
0x18002c482  nop
0x18002c483  jmp     loc_18002C51A
0x18002c488  test    cs:byte_18004AF81, 1
0x18002c48f  jz      short loc_18002C4B7
0x18002c491  mov     eax, dword ptr [rsp+170h+var_128+8]
0x18002c495  mov     [rsp+170h+var_148], eax
0x18002c499  mov     eax, dword ptr [rsp+170h+var_128+4]
0x18002c49d  mov     [rsp+170h+var_150], eax
0x18002c4a1  mov     r9d, dword ptr [rsp+170h+var_128+0Ch]
0x18002c4a6  mov     r8b, byte ptr [rsp+170h+var_128]
0x18002c4ab  lea     rdx, MethodAddFailed
0x18002c4b2  call    McTemplateU0uqqq_EtwEventWriteTransfer
0x18002c4b7  lea     rbx, WPP_GLOBAL_Control
0x18002c4be  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c4c5  cmp     rcx, rbx
0x18002c4c8  jz      short loc_18002C504
0x18002c4ca  test    byte ptr [rcx+1Ch], 1
0x18002c4ce  jz      short loc_18002C504
0x18002c4d0  movzx   r9d, byte ptr [rsp+170h+var_128]
0x18002c4d6  mov     edx, 34h ; '4'
0x18002c4db  mov     eax, dword ptr [rsp+170h+var_128+8]
0x18002c4df  mov     [rsp+170h+var_140], eax
0x18002c4e3  mov     eax, dword ptr [rsp+170h+var_128+4]
0x18002c4e7  mov     [rsp+170h+var_148], eax
0x18002c4eb  mov     eax, dword ptr [rsp+170h+var_128+0Ch]
0x18002c4ef  mov     [rsp+170h+var_150], eax
0x18002c4f3  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18002c4fa  mov     rcx, [rcx+10h]
0x18002c4fe  call    WPP_SF_dddd
0x18002c503  nop
0x18002c504  lea     rcx, [rsp+170h+var_F8]
0x18002c509  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
  ... truncated ...
```
