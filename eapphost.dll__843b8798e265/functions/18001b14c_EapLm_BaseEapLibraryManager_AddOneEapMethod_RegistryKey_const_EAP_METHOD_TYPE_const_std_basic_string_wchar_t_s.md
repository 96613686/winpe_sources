# EapLm::BaseEapLibraryManager::AddOneEapMethod(RegistryKey const &,_EAP_METHOD_TYPE const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)

- ea: `0x18001b14c`
- end: `0x18001b621`
- name: `?AddOneEapMethod@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@AEBU_EAP_METHOD_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z`
- size: `1237`
- prototype: ``
- caller_count: `3`
- callee_count: `24`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001a99c`
- `0x18001bc10`
- `0x18001c1e4`

## callees

- `0x180002af0`
- `0x1800040a8`
- `0x180004af8`
- `0x1800056cc`
- `0x18000a21c`
- `0x18000a24c`
- `0x18000a3e4`
- `0x18000a588`
- `0x180011218`
- `0x18001204c`
- `0x18001206c`
- `0x180019f30`
- `0x180019f70`
- `0x180019fb0`
- `0x18001a560`
- `0x18001a838`
- `0x18001a918`
- `0x18001b14c`
- `0x18001d1fc`
- `0x180030b08`
- `0x1800314c4`
- `0x18003165c`
- `0x180031778`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b4e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b4e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall EapLm::BaseEapLibraryManager::AddOneEapMethod(__int64 a1, __int64 a2, __int128 *a3, __int64 a4)
{
  char v7; // si
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rax
  int v13; // ecx
  int v14; // r8d
  __int64 v15; // rax
  unsigned int v16; // r14d
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned int v23; // esi
  EapHost::Peer::Host *v24; // rcx
  int v25; // ecx
  int v26; // r8d
  __int64 v28; // rax
  EapHost::Peer::Host *v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v32; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v33; // [rsp+58h] [rbp-A8h]
  __int128 v34; // [rsp+68h] [rbp-98h]
  _BYTE v35[16]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v36; // [rsp+88h] [rbp-78h]
  ReferenceCounted *v37; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v38; // [rsp+A0h] [rbp-60h]
  _BYTE v39[40]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v40[64]; // [rsp+E0h] [rbp-20h] BYREF

  v7 = 0;
  LODWORD(v31) = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v32 = *a3;
  v8 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a4);
  *(_QWORD *)&v33 = BasicSimpleString<wchar_t>::Copy(v8);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    v35,
    v9,
    v10,
    v11);
  v12 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 8);
  if ( (unsigned int)RegistryKey::ReadMuiString(a2, v12, v35) )
  {
    v15 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 8);
    RegistryKey::QueryValue(a2, v15, v35);
  }
  if ( v36 )
  {
    v16 = 3;
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v17 = std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(&v37, a4);
      LODWORD(v31) = 1;
      v18 = std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v39, v17, v35);
      v7 = 3;
      v19 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v18);
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, v19);
    }
    if ( (v7 & 2) != 0 )
    {
      v7 &= ~2u;
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v39);
    }
    if ( (v7 & 1) != 0 )
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(&v37);
    v20 = std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(&v37, a4);
    v21 = std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v39, v20, v35);
    v22 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v21);
    *((_QWORD *)&v33 + 1) = BasicSimpleString<wchar_t>::Copy(v22);
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v39);
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(&v37);
    LODWORD(v31) = 0;
    RegistryKey::QueryValue(a2, L"Properties", &v31);
    LODWORD(v34) = v31;
    LODWORD(v31) = 0;
    RegistryKey::QueryValue(a2, L"TreatAsMsMethod", &v31);
    v23 = v31;
    if ( (_DWORD)v31 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          53,
          WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
          (unsigned int)v31);
        v24 = WPP_GLOBAL_Control;
      }
      v16 = v23;
    }
    else
    {
      v24 = WPP_GLOBAL_Control;
    }
    if ( !HIDWORD(v32) || !(_BYTE)v32 )
    {
      if ( v24 != (EapHost::Peer::Host *)&WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 1) != 0 )
        WPP_SF_dddd(
          *((_QWORD *)v24 + 2),
          54,
          WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
          (unsigned __int8)v32,
          HIDWORD(v32),
          DWORD1(v32),
          DWORD2(v32));
      goto LABEL_20;
    }
    if ( !(*(unsigned __int8 (__fastcall **)(__int64, __int128 *, _QWORD, __int64))(*(_QWORD *)a1 + 56LL))(
            a1,
            &v32,
            v16,
            a2) )
    {
LABEL_20:
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v35);
      return Free<HeapAllocator>(&v32);
    }
    if ( (Microsoft_Windows_EapHostEnableBits & 0x40) != 0 )
    {
      LOBYTE(v26) = v32;
      McTemplateU0uqqq_EtwEventWriteTransfer(
        v25,
        (unsigned int)MethodAdditionEvent,
        v26,
        HIDWORD(v32),
        SBYTE4(v32),
        SBYTE8(v32));
    }
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_dddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
        (unsigned __int8)v32,
        HIDWORD(v32),
        DWORD1(v32),
        DWORD2(v32));
    }
    v37 = 0;
    v31 = 0;
    SmartPointer<EapLm::IEapMethod>::operator=(&v37, &v31);
    v38 = v16;
    LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(&v31, a1 + 80);
    v28 = std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>(
            v40,
            &v32,
            &v37);
    std::map<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::insert<std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>,0>(
      a1 + 136,
      v39,
      v28);
    std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::~pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>(v40);
    if ( v39[8] )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_34;
      }
      v30 = 56;
    }
    else
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_34;
      }
      v30 = 57;
    }
    WPP_SF_(*((_QWORD *)v29 + 2), v30, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
LABEL_34:
    LeaveCriticalSection((LPCRITICAL_SECTION)(v31 + 16));
    if ( v37 )
      ReferenceCounted::Release(v37);
    goto LABEL_20;
  }
  if ( (byte_18004F981 & 1) != 0 )
  {
    LOBYTE(v14) = v32;
    McTemplateU0uqqq_EtwEventWriteTransfer(
      v13,
      (unsigned int)MethodAddFailed,
      v14,
      HIDWORD(v32),
      SBYTE4(v32),
      SBYTE8(v32));
  }
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_dddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52,
      WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
      (unsigned __int8)v32,
      HIDWORD(v32),
      DWORD1(v32),
      DWORD2(v32));
  }
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v35);
  return Free<HeapAllocator>(&v32);
}

```

## disassembly

```asm
0x18001b14c  push    rbp
0x18001b14e  push    rbx
0x18001b14f  push    rsi
0x18001b150  push    rdi
0x18001b151  push    r12
0x18001b153  push    r13
0x18001b155  push    r14
0x18001b157  push    r15
0x18001b159  lea     rbp, [rsp-38h]
0x18001b15e  sub     rsp, 138h
0x18001b165  mov     rax, cs:__security_cookie
0x18001b16c  xor     rax, rsp
0x18001b16f  mov     [rbp+70h+var_50], rax
0x18001b173  mov     r13, r9
0x18001b176  mov     r12, rdx
0x18001b179  mov     r15, rcx
0x18001b17c  xor     esi, esi
0x18001b17e  mov     dword ptr [rsp+170h+var_130], esi
0x18001b182  xorps   xmm0, xmm0
0x18001b185  movups  [rsp+170h+var_128], xmm0
0x18001b18a  movups  [rsp+170h+var_118], xmm0
0x18001b18f  movups  [rsp+170h+var_108], xmm0
0x18001b194  mov     al, [r8]
0x18001b197  mov     byte ptr [rsp+170h+var_128], al
0x18001b19b  movzx   eax, word ptr [r8+1]
0x18001b1a0  mov     word ptr [rsp+170h+var_128+1], ax
0x18001b1a5  mov     al, [r8+3]
0x18001b1a9  mov     byte ptr [rsp+170h+var_128+3], al
0x18001b1ad  mov     eax, [r8+4]
0x18001b1b1  mov     dword ptr [rsp+170h+var_128+4], eax
0x18001b1b5  mov     eax, [r8+8]
0x18001b1b9  mov     dword ptr [rsp+170h+var_128+8], eax
0x18001b1bd  mov     eax, [r8+0Ch]
0x18001b1c1  mov     dword ptr [rsp+170h+var_128+0Ch], eax
0x18001b1c5  mov     rcx, r9
0x18001b1c8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001b1cd  mov     rcx, rax
0x18001b1d0  call    ?Copy@?$BasicSimpleString@_W@@SAPEA_WPEB_W@Z; BasicSimpleString<wchar_t>::Copy(wchar_t const *)
0x18001b1d5  mov     qword ptr [rsp+170h+var_118], rax
0x18001b1da  lea     rcx, [rsp+170h+var_F8]
0x18001b1df  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x18001b1e4  nop
0x18001b1e5  lea     rcx, [r15+8]
0x18001b1e9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001b1ee  lea     r8, [rsp+170h+var_F8]
0x18001b1f3  mov     rdx, rax
0x18001b1f6  mov     rcx, r12
0x18001b1f9  call    ?ReadMuiString@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::ReadMuiString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001b1fe  test    eax, eax
0x18001b200  jz      short loc_18001B21B
0x18001b202  lea     rcx, [r15+8]
0x18001b206  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001b20b  lea     r8, [rsp+170h+var_F8]
0x18001b210  mov     rdx, rax
0x18001b213  mov     rcx, r12
0x18001b216  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001b21b  cmp     [rbp+70h+var_E8], 0
0x18001b220  jz      loc_18001B56E
0x18001b226  lea     rbx, WPP_GLOBAL_Control
0x18001b22d  mov     r14d, 3
0x18001b233  lea     rdi, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001b23a  mov     rax, cs:WPP_GLOBAL_Control
0x18001b241  cmp     rax, rbx
0x18001b244  jz      short loc_18001B297
0x18001b246  test    byte ptr [rax+1Ch], 4
0x18001b24a  jz      short loc_18001B297
0x18001b24c  mov     rdx, r13
0x18001b24f  lea     rcx, [rbp+70h+var_D8]
0x18001b253  call    ??$?H_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,wchar_t const * const)
0x18001b258  nop
0x18001b259  mov     dword ptr [rsp+170h+var_130], 1
0x18001b261  lea     r8, [rsp+170h+var_F8]
0x18001b266  mov     rdx, rax
0x18001b269  lea     rcx, [rbp+70h+var_B8]
0x18001b26d  call    ??$?H_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &&,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18001b272  mov     esi, r14d
0x18001b275  mov     rcx, rax
0x18001b278  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001b27d  lea     edx, [r14+30h]
0x18001b281  mov     r9, rax
0x18001b284  mov     r8, rdi
0x18001b287  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b28e  mov     rcx, [rcx+10h]
0x18001b292  call    WPP_SF_S
0x18001b297  test    sil, 2
0x18001b29b  jz      short loc_18001B2AA
0x18001b29d  and     esi, 0FFFFFFFDh
0x18001b2a0  lea     rcx, [rbp+70h+var_B8]
0x18001b2a4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b2a9  nop
0x18001b2aa  test    sil, 1
0x18001b2ae  jz      short loc_18001B2B9
0x18001b2b0  lea     rcx, [rbp+70h+var_D8]
0x18001b2b4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b2b9  mov     rdx, r13
0x18001b2bc  lea     rcx, [rbp+70h+var_D8]
0x18001b2c0  call    ??$?H_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,wchar_t const * const)
0x18001b2c5  nop
0x18001b2c6  lea     r8, [rsp+170h+var_F8]
0x18001b2cb  mov     rdx, rax
0x18001b2ce  lea     rcx, [rbp+70h+var_B8]
0x18001b2d2  call    ??$?H_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &&,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18001b2d7  nop
0x18001b2d8  mov     rcx, rax
0x18001b2db  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001b2e0  mov     rcx, rax
0x18001b2e3  call    ?Copy@?$BasicSimpleString@_W@@SAPEA_WPEB_W@Z; BasicSimpleString<wchar_t>::Copy(wchar_t const *)
0x18001b2e8  mov     qword ptr [rsp+170h+var_118+8], rax
0x18001b2ed  lea     rcx, [rbp+70h+var_B8]
0x18001b2f1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b2f6  nop
0x18001b2f7  lea     rcx, [rbp+70h+var_D8]
0x18001b2fb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b300  xor     r13d, r13d
0x18001b303  mov     dword ptr [rsp+170h+var_130], r13d
0x18001b308  lea     r8, [rsp+170h+var_130]
0x18001b30d  lea     rdx, aProperties; "Properties"
0x18001b314  mov     rcx, r12
0x18001b317  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x18001b31c  mov     eax, dword ptr [rsp+170h+var_130]
0x18001b320  mov     dword ptr [rsp+170h+var_108], eax
0x18001b324  mov     dword ptr [rsp+170h+var_130], r13d
0x18001b329  lea     r8, [rsp+170h+var_130]
0x18001b32e  lea     rdx, aTreatasmsmetho; "TreatAsMsMethod"
0x18001b335  mov     rcx, r12
0x18001b338  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x18001b33d  mov     esi, dword ptr [rsp+170h+var_130]
0x18001b341  test    esi, esi
0x18001b343  jz      short loc_18001B376
0x18001b345  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b34c  cmp     rcx, rbx
0x18001b34f  jz      short loc_18001B371
0x18001b351  test    byte ptr [rcx+1Ch], 4
0x18001b355  jz      short loc_18001B371
0x18001b357  lea     edx, [r13+35h]
0x18001b35b  mov     r9d, esi
0x18001b35e  mov     r8, rdi
0x18001b361  mov     rcx, [rcx+10h]
0x18001b365  call    WPP_SF_d
0x18001b36a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b371  mov     r14d, esi
0x18001b374  jmp     short loc_18001B37D
0x18001b376  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b37d  movzx   eax, byte ptr [rsp+170h+var_128]
0x18001b382  mov     r8d, dword ptr [rsp+170h+var_128+0Ch]
0x18001b387  test    r8d, r8d
0x18001b38a  jz      loc_18001B51E
0x18001b390  test    al, al
0x18001b392  jz      loc_18001B51E
0x18001b398  mov     rax, [r15]
0x18001b39b  mov     r9, r12
0x18001b39e  mov     r8d, r14d
0x18001b3a1  lea     rdx, [rsp+170h+var_128]
0x18001b3a6  mov     rcx, r15
0x18001b3a9  mov     rax, [rax+38h]
0x18001b3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3b2  test    al, al
0x18001b3b4  jnz     short loc_18001B3D1
0x18001b3b6  lea     rcx, [rsp+170h+var_F8]
0x18001b3bb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b3c0  nop
0x18001b3c1  lea     rcx, [rsp+170h+var_128]
0x18001b3c6  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<HeapAllocator>(_EAP_METHOD_INFO &)
0x18001b3cb  nop
0x18001b3cc  jmp     loc_18001B600
0x18001b3d1  test    cs:Microsoft_Windows_EapHostEnableBits, 40h
0x18001b3d8  jz      short loc_18001B400
0x18001b3da  mov     eax, dword ptr [rsp+170h+var_128+8]
0x18001b3de  mov     [rsp+170h+var_148], eax
0x18001b3e2  mov     eax, dword ptr [rsp+170h+var_128+4]
0x18001b3e6  mov     [rsp+170h+var_150], eax
0x18001b3ea  mov     r9d, dword ptr [rsp+170h+var_128+0Ch]
0x18001b3ef  mov     r8b, byte ptr [rsp+170h+var_128]
0x18001b3f4  lea     rdx, MethodAdditionEvent
0x18001b3fb  call    McTemplateU0uqqq_EtwEventWriteTransfer
0x18001b400  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b407  cmp     rcx, rbx
0x18001b40a  jz      short loc_18001B441
0x18001b40c  test    byte ptr [rcx+1Ch], 4
0x18001b410  jz      short loc_18001B441
0x18001b412  movzx   r9d, byte ptr [rsp+170h+var_128]
0x18001b418  mov     edx, 37h ; '7'
0x18001b41d  mov     eax, dword ptr [rsp+170h+var_128+8]
0x18001b421  mov     [rsp+170h+var_140], eax
0x18001b425  mov     eax, dword ptr [rsp+170h+var_128+4]
0x18001b429  mov     [rsp+170h+var_148], eax
0x18001b42d  mov     eax, dword ptr [rsp+170h+var_128+0Ch]
0x18001b431  mov     [rsp+170h+var_150], eax
0x18001b435  mov     r8, rdi
0x18001b438  mov     rcx, [rcx+10h]
0x18001b43c  call    WPP_SF_dddd
0x18001b441  mov     [rbp+70h+var_D8], r13
0x18001b445  mov     [rsp+170h+var_130], r13
0x18001b44a  lea     rdx, [rsp+170h+var_130]
0x18001b44f  lea     rcx, [rbp+70h+var_D8]
0x18001b453  call    ??4?$SmartPointer@UIEapMethod@EapLm@@@@QEAAAEAV0@AEBV0@@Z; SmartPointer<EapLm::IEapMethod>::operator=(SmartPointer<EapLm::IEapMethod> const &)
0x18001b458  mov     [rbp+70h+var_D0], r14d
0x18001b45c  lea     rdx, [r15+50h]
0x18001b460  lea     rcx, [rsp+170h+var_130]
0x18001b465  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x18001b46a  nop
0x18001b46b  lea     r8, [rbp+70h+var_D8]
0x18001b46f  lea     rdx, [rsp+170h+var_128]
0x18001b474  lea     rcx, [rbp+70h+var_90]
0x18001b478  call    ??$?0AEAV?$crt_ref@U_EAP_METHOD_INFO@@@@AEAU_EapMethodSlot@EapLm@@$0A@@?$pair@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@QEAA@AEAV?$crt_ref@U_EAP_METHOD_INFO@@@@AEAU_EapMethodSlot@EapLm@@@Z; std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>(crt_ref<_EAP_METHOD_INFO> &,EapLm::_EapMethodSlot &)
0x18001b47d  nop
0x18001b47e  lea     rcx, [r15+88h]
0x18001b485  mov     r8, rax
0x18001b488  lea     rdx, [rbp+70h+var_B8]
0x18001b48c  call    ??$insert@U?$pair@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@$0A@@?$map@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@U?$less@V?$crt_ref@U_EAP_METHOD_INFO@@@@@std@@V?$allocator@U?$pair@$$CBV?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@@5@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@1@@Z; std::map<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::insert<std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>,0>(std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot> &&)
0x18001b491  nop
0x18001b492  lea     rcx, [rbp+70h+var_90]
0x18001b496  call    ??1?$pair@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@QEAA@XZ; std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::~pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>(void)
0x18001b49b  cmp     [rbp+70h+var_B0], r13b
0x18001b49f  jz      short loc_18001B4BA
0x18001b4a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b4a8  cmp     rcx, rbx
0x18001b4ab  jz      short loc_18001B4DE
0x18001b4ad  test    byte ptr [rcx+1Ch], 4
0x18001b4b1  jz      short loc_18001B4DE
0x18001b4b3  mov     edx, 38h ; '8'
0x18001b4b8  jmp     short loc_18001B4D1
0x18001b4ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b4c1  cmp     rcx, rbx
0x18001b4c4  jz      short loc_18001B4DE
0x18001b4c6  test    byte ptr [rcx+1Ch], 4
0x18001b4ca  jz      short loc_18001B4DE
0x18001b4cc  mov     edx, 39h ; '9'
0x18001b4d1  mov     r8, rdi
0x18001b4d4  mov     rcx, [rcx+10h]
0x18001b4d8  call    WPP_SF_
0x18001b4dd  nop
0x18001b4de  mov     rcx, [rsp+170h+var_130]
0x18001b4e3  add     rcx, 10h; lpCriticalSection
0x18001b4e7  call    cs:__imp_LeaveCriticalSection
0x18001b4ee  nop     dword ptr [rax+rax+00h]
0x18001b4f3  nop
0x18001b4f4  mov     rcx, [rbp+70h+var_D8]; this
0x18001b4f8  test    rcx, rcx
0x18001b4fb  jz      short loc_18001B503
0x18001b4fd  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x18001b502  nop
0x18001b503  lea     rcx, [rsp+170h+var_F8]
0x18001b508  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b50d  nop
0x18001b50e  lea     rcx, [rsp+170h+var_128]
0x18001b513  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<HeapAllocator>(_EAP_METHOD_INFO &)
0x18001b518  nop
0x18001b519  jmp     loc_18001B600
0x18001b51e  cmp     rcx, rbx
0x18001b521  jz      short loc_18001B553
0x18001b523  test    byte ptr [rcx+1Ch], 1
0x18001b527  jz      short loc_18001B553
0x18001b529  mov     r9d, eax
0x18001b52c  mov     edx, 36h ; '6'
0x18001b531  mov     eax, dword ptr [rsp+170h+var_128+8]
0x18001b535  mov     [rsp+170h+var_140], eax
0x18001b539  mov     eax, dword ptr [rsp+170h+var_128+4]
0x18001b53d  mov     [rsp+170h+var_148], eax
0x18001b541  mov     [rsp+170h+var_150], r8d
0x18001b546  mov     r8, rdi
0x18001b549  mov     rcx, [rcx+10h]
0x18001b54d  call    WPP_SF_dddd
0x18001b552  nop
0x18001b553  lea     rcx, [rsp+170h+var_F8]
0x18001b558  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b55d  nop
0x18001b55e  lea     rcx, [rsp+170h+var_128]
0x18001b563  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<HeapAllocator>(_EAP_METHOD_INFO &)
0x18001b568  nop
0x18001b569  jmp     loc_18001B600
0x18001b56e  test    cs:byte_18004F981, 1
0x18001b575  jz      short loc_18001B59D
0x18001b577  mov     eax, dword ptr [rsp+170h+var_128+8]
0x18001b57b  mov     [rsp+170h+var_148], eax
0x18001b57f  mov     eax, dword ptr [rsp+170h+var_128+4]
0x18001b583  mov     [rsp+170h+var_150], eax
0x18001b587  mov     r9d, dword ptr [rsp+170h+var_128+0Ch]
0x18001b58c  mov     r8b, byte ptr [rsp+170h+var_128]
0x18001b591  lea     rdx, MethodAddFailed
0x18001b598  call    McTemplateU0uqqq_EtwEventWriteTransfer
0x18001b59d  lea     rbx, WPP_GLOBAL_Control
0x18001b5a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b5ab  cmp     rcx, rbx
0x18001b5ae  jz      short loc_18001B5EA
0x18001b5b0  test    byte ptr [rcx+1Ch], 1
0x18001b5b4  jz      short loc_18001B5EA
0x18001b5b6  movzx   r9d, byte ptr [rsp+170h+var_128]
0x18001b5bc  mov     edx, 34h ; '4'
0x18001b5c1  mov     eax, dword ptr [rsp+170h+var_128+8]
0x18001b5c5  mov     [rsp+170h+var_140], eax
0x18001b5c9  mov     eax, dword ptr [rsp+170h+var_128+4]
0x18001b5cd  mov     [rsp+170h+var_148], eax
0x18001b5d1  mov     eax, dword ptr [rsp+170h+var_128+0Ch]
0x18001b5d5  mov     [rsp+170h+var_150], eax
0x18001b5d9  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001b5e0  mov     rcx, [rcx+10h]
0x18001b5e4  call    WPP_SF_dddd
0x18001b5e9  nop
0x18001b5ea  lea     rcx, [rsp+170h+var_F8]
  ... truncated ...
```
