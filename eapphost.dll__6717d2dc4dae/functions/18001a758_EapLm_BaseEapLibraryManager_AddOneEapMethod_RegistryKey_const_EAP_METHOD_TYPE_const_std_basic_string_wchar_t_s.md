# EapLm::BaseEapLibraryManager::AddOneEapMethod(RegistryKey const &,_EAP_METHOD_TYPE const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)

- ea: `0x18001a758`
- end: `0x18001ac26`
- name: `?AddOneEapMethod@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@AEBU_EAP_METHOD_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z`
- size: `1230`
- prototype: `void __fastcall(__int64, __int64, __int128 *, __int64)`
- caller_count: `3`
- callee_count: `24`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180019fbc`
- `0x18001b200`
- `0x18001b7cc`

## callees

- `0x180002a90`
- `0x180003fa4`
- `0x180004988`
- `0x1800054c4`
- `0x180009dc4`
- `0x180009dec`
- `0x180009f70`
- `0x18000a0f4`
- `0x180010aa8`
- `0x1800118e8`
- `0x180011908`
- `0x180019548`
- `0x180019588`
- `0x1800195c8`
- `0x180019b7c`
- `0x180019e54`
- `0x180019f30`
- `0x18001a758`
- `0x18001c78c`
- `0x18002f93c`
- `0x180030294`
- `0x18003044c`
- `0x180030564`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aaf3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aaf3`

## pseudocode

```c
void __fastcall EapLm::BaseEapLibraryManager::AddOneEapMethod(__int64 a1, __int64 a2, __int128 *a3, __int64 a4)
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
  unsigned int v21; // esi
  EapHost::Peer::Host *v22; // rcx
  int v23; // ecx
  int v24; // r8d
  __int64 v25; // rax
  EapHost::Peer::Host *v26; // rcx
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
  v8 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  *(_QWORD *)&v30 = BasicSimpleString<wchar_t>::Copy(v8);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    v32,
    v9,
    v10,
    v11);
  v12 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  if ( (unsigned int)RegistryKey::ReadMuiString(a2, v12, v32) )
  {
    v15 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    RegistryKey::QueryValue(a2, v15, v32);
  }
  if ( v33 )
  {
    v16 = 3;
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v17 = std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(&v34, a4);
      LODWORD(v28) = 1;
      std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v36, v17, v32);
      v7 = 3;
      v18 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, v18);
    }
    if ( (v7 & 2) != 0 )
    {
      v7 &= ~2u;
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v36);
    }
    if ( (v7 & 1) != 0 )
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)&v34);
    v19 = std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(&v34, a4);
    std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v36, v19, v32);
    v20 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    *((_QWORD *)&v30 + 1) = BasicSimpleString<wchar_t>::Copy(v20);
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v36);
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)&v34);
    LODWORD(v28) = 0;
    RegistryKey::QueryValue(a2, L"Properties", &v28);
    LODWORD(v31) = v28;
    LODWORD(v28) = 0;
    RegistryKey::QueryValue(a2, L"TreatAsMsMethod", &v28);
    v21 = v28;
    if ( (_DWORD)v28 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          53,
          WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
          (unsigned int)v28);
        v22 = WPP_GLOBAL_Control;
      }
      v16 = v21;
    }
    else
    {
      v22 = WPP_GLOBAL_Control;
    }
    if ( !HIDWORD(v29) || !(_BYTE)v29 )
    {
      if ( v22 != (EapHost::Peer::Host *)&WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 1) != 0 )
        WPP_SF_dddd(
          *((_QWORD *)v22 + 2),
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
            v16,
            a2) )
    {
LABEL_20:
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v32);
      Free<HeapAllocator>((__int64)&v29);
      return;
    }
    if ( (Microsoft_Windows_EapHostEnableBits & 0x40) != 0 )
    {
      LOBYTE(v24) = v29;
      McTemplateU0uqqq_EtwEventWriteTransfer(
        v23,
        (unsigned int)MethodAdditionEvent,
        v24,
        HIDWORD(v29),
        SBYTE4(v29),
        SBYTE8(v29));
    }
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_dddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
        (unsigned __int8)v29,
        HIDWORD(v29),
        DWORD1(v29),
        DWORD2(v29));
    }
    v34 = 0;
    v28 = 0;
    SmartPointer<EapLm::IEapMethod>::operator=(&v34, &v28);
    v35 = v16;
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
      if ( WPP_GLOBAL_Control == (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_34;
      }
      v27 = 56;
    }
    else
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_34;
      }
      v27 = 57;
    }
    WPP_SF_(*((_QWORD *)v26 + 2), v27, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
LABEL_34:
    LeaveCriticalSection((LPCRITICAL_SECTION)(v28 + 16));
    if ( v34 )
      ReferenceCounted::Release(v34);
    goto LABEL_20;
  }
  if ( (byte_18004E841 & 1) != 0 )
  {
    LOBYTE(v14) = v29;
    McTemplateU0uqqq_EtwEventWriteTransfer(
      v13,
      (unsigned int)MethodAddFailed,
      v14,
      HIDWORD(v29),
      SBYTE4(v29),
      SBYTE8(v29));
  }
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_dddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52,
      WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
      (unsigned __int8)v29,
      HIDWORD(v29),
      DWORD1(v29),
      DWORD2(v29));
  }
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v32);
  Free<HeapAllocator>((__int64)&v29);
}

```

## disassembly

```asm
0x18001a758  push    rbp
0x18001a75a  push    rbx
0x18001a75b  push    rsi
0x18001a75c  push    rdi
0x18001a75d  push    r12
0x18001a75f  push    r13
0x18001a761  push    r14
0x18001a763  push    r15
0x18001a765  lea     rbp, [rsp-38h]
0x18001a76a  sub     rsp, 138h
0x18001a771  mov     rax, cs:__security_cookie
0x18001a778  xor     rax, rsp
0x18001a77b  mov     [rbp+70h+var_50], rax
0x18001a77f  mov     r13, r9
0x18001a782  mov     r12, rdx
0x18001a785  mov     r15, rcx
0x18001a788  xor     esi, esi
0x18001a78a  mov     dword ptr [rsp+170h+var_130], esi
0x18001a78e  xorps   xmm0, xmm0
0x18001a791  movups  [rsp+170h+var_128], xmm0
0x18001a796  movups  [rsp+170h+var_118], xmm0
0x18001a79b  movups  [rsp+170h+var_108], xmm0
0x18001a7a0  mov     al, [r8]
0x18001a7a3  mov     byte ptr [rsp+170h+var_128], al
0x18001a7a7  movzx   eax, word ptr [r8+1]
0x18001a7ac  mov     word ptr [rsp+170h+var_128+1], ax
0x18001a7b1  mov     al, [r8+3]
0x18001a7b5  mov     byte ptr [rsp+170h+var_128+3], al
0x18001a7b9  mov     eax, [r8+4]
0x18001a7bd  mov     dword ptr [rsp+170h+var_128+4], eax
0x18001a7c1  mov     eax, [r8+8]
0x18001a7c5  mov     dword ptr [rsp+170h+var_128+8], eax
0x18001a7c9  mov     eax, [r8+0Ch]
0x18001a7cd  mov     dword ptr [rsp+170h+var_128+0Ch], eax
0x18001a7d1  mov     rcx, r9
0x18001a7d4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001a7d9  mov     rcx, rax
0x18001a7dc  call    ?Copy@?$BasicSimpleString@_W@@SAPEA_WPEB_W@Z; BasicSimpleString<wchar_t>::Copy(wchar_t const *)
0x18001a7e1  mov     qword ptr [rsp+170h+var_118], rax
0x18001a7e6  lea     rcx, [rsp+170h+var_F8]
0x18001a7eb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x18001a7f0  nop
0x18001a7f1  lea     rcx, [r15+8]
0x18001a7f5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001a7fa  lea     r8, [rsp+170h+var_F8]
0x18001a7ff  mov     rdx, rax
0x18001a802  mov     rcx, r12
0x18001a805  call    ?ReadMuiString@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::ReadMuiString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001a80a  test    eax, eax
0x18001a80c  jz      short loc_18001A827
0x18001a80e  lea     rcx, [r15+8]
0x18001a812  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001a817  lea     r8, [rsp+170h+var_F8]
0x18001a81c  mov     rdx, rax
0x18001a81f  mov     rcx, r12
0x18001a822  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001a827  cmp     [rbp+70h+var_E8], 0
0x18001a82c  jz      loc_18001AB74
0x18001a832  lea     rbx, WPP_GLOBAL_Control
0x18001a839  mov     r14d, 3
0x18001a83f  lea     rdi, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001a846  mov     rax, cs:WPP_GLOBAL_Control
0x18001a84d  cmp     rax, rbx
0x18001a850  jz      short loc_18001A8A3
0x18001a852  test    byte ptr [rax+1Ch], 4
0x18001a856  jz      short loc_18001A8A3
0x18001a858  mov     rdx, r13
0x18001a85b  lea     rcx, [rbp+70h+var_D8]
0x18001a85f  call    ??$?H_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,wchar_t const * const)
0x18001a864  nop
0x18001a865  mov     dword ptr [rsp+170h+var_130], 1
0x18001a86d  lea     r8, [rsp+170h+var_F8]
0x18001a872  mov     rdx, rax
0x18001a875  lea     rcx, [rbp+70h+var_B8]
0x18001a879  call    ??$?H_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &&,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18001a87e  mov     esi, r14d
0x18001a881  mov     rcx, rax
0x18001a884  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001a889  lea     edx, [r14+30h]
0x18001a88d  mov     r9, rax
0x18001a890  mov     r8, rdi
0x18001a893  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a89a  mov     rcx, [rcx+10h]
0x18001a89e  call    WPP_SF_S
0x18001a8a3  test    sil, 2
0x18001a8a7  jz      short loc_18001A8B6
0x18001a8a9  and     esi, 0FFFFFFFDh
0x18001a8ac  lea     rcx, [rbp+70h+var_B8]
0x18001a8b0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001a8b5  nop
0x18001a8b6  test    sil, 1
0x18001a8ba  jz      short loc_18001A8C5
0x18001a8bc  lea     rcx, [rbp+70h+var_D8]
0x18001a8c0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001a8c5  mov     rdx, r13
0x18001a8c8  lea     rcx, [rbp+70h+var_D8]
0x18001a8cc  call    ??$?H_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &,wchar_t const * const)
0x18001a8d1  nop
0x18001a8d2  lea     r8, [rsp+170h+var_F8]
0x18001a8d7  mov     rdx, rax
0x18001a8da  lea     rcx, [rbp+70h+var_B8]
0x18001a8de  call    ??$?H_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &&,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18001a8e3  nop
0x18001a8e4  mov     rcx, rax
0x18001a8e7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001a8ec  mov     rcx, rax
0x18001a8ef  call    ?Copy@?$BasicSimpleString@_W@@SAPEA_WPEB_W@Z; BasicSimpleString<wchar_t>::Copy(wchar_t const *)
0x18001a8f4  mov     qword ptr [rsp+170h+var_118+8], rax
0x18001a8f9  lea     rcx, [rbp+70h+var_B8]
0x18001a8fd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001a902  nop
0x18001a903  lea     rcx, [rbp+70h+var_D8]
0x18001a907  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001a90c  xor     r13d, r13d
0x18001a90f  mov     dword ptr [rsp+170h+var_130], r13d
0x18001a914  lea     r8, [rsp+170h+var_130]
0x18001a919  lea     rdx, aProperties; "Properties"
0x18001a920  mov     rcx, r12
0x18001a923  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x18001a928  mov     eax, dword ptr [rsp+170h+var_130]
0x18001a92c  mov     dword ptr [rsp+170h+var_108], eax
0x18001a930  mov     dword ptr [rsp+170h+var_130], r13d
0x18001a935  lea     r8, [rsp+170h+var_130]
0x18001a93a  lea     rdx, aTreatasmsmetho; "TreatAsMsMethod"
0x18001a941  mov     rcx, r12
0x18001a944  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x18001a949  mov     esi, dword ptr [rsp+170h+var_130]
0x18001a94d  test    esi, esi
0x18001a94f  jz      short loc_18001A982
0x18001a951  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a958  cmp     rcx, rbx
0x18001a95b  jz      short loc_18001A97D
0x18001a95d  test    byte ptr [rcx+1Ch], 4
0x18001a961  jz      short loc_18001A97D
0x18001a963  lea     edx, [r13+35h]
0x18001a967  mov     r9d, esi
0x18001a96a  mov     r8, rdi
0x18001a96d  mov     rcx, [rcx+10h]
0x18001a971  call    WPP_SF_d
0x18001a976  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a97d  mov     r14d, esi
0x18001a980  jmp     short loc_18001A989
0x18001a982  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a989  movzx   eax, byte ptr [rsp+170h+var_128]
0x18001a98e  mov     r8d, dword ptr [rsp+170h+var_128+0Ch]
0x18001a993  test    r8d, r8d
0x18001a996  jz      loc_18001AB24
0x18001a99c  test    al, al
0x18001a99e  jz      loc_18001AB24
0x18001a9a4  mov     rax, [r15]
0x18001a9a7  mov     r9, r12
0x18001a9aa  mov     r8d, r14d
0x18001a9ad  lea     rdx, [rsp+170h+var_128]
0x18001a9b2  mov     rcx, r15
0x18001a9b5  mov     rax, [rax+38h]
0x18001a9b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9be  test    al, al
0x18001a9c0  jnz     short loc_18001A9DD
0x18001a9c2  lea     rcx, [rsp+170h+var_F8]
0x18001a9c7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001a9cc  nop
0x18001a9cd  lea     rcx, [rsp+170h+var_128]
0x18001a9d2  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<HeapAllocator>(_EAP_METHOD_INFO &)
0x18001a9d7  nop
0x18001a9d8  jmp     loc_18001AC06
0x18001a9dd  test    cs:Microsoft_Windows_EapHostEnableBits, 40h
0x18001a9e4  jz      short loc_18001AA0C
0x18001a9e6  mov     eax, dword ptr [rsp+170h+var_128+8]
0x18001a9ea  mov     [rsp+170h+var_148], eax
0x18001a9ee  mov     eax, dword ptr [rsp+170h+var_128+4]
0x18001a9f2  mov     [rsp+170h+var_150], eax
0x18001a9f6  mov     r9d, dword ptr [rsp+170h+var_128+0Ch]
0x18001a9fb  mov     r8b, byte ptr [rsp+170h+var_128]
0x18001aa00  lea     rdx, MethodAdditionEvent
0x18001aa07  call    McTemplateU0uqqq_EtwEventWriteTransfer
0x18001aa0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa13  cmp     rcx, rbx
0x18001aa16  jz      short loc_18001AA4D
0x18001aa18  test    byte ptr [rcx+1Ch], 4
0x18001aa1c  jz      short loc_18001AA4D
0x18001aa1e  movzx   r9d, byte ptr [rsp+170h+var_128]
0x18001aa24  mov     edx, 37h ; '7'
0x18001aa29  mov     eax, dword ptr [rsp+170h+var_128+8]
0x18001aa2d  mov     [rsp+170h+var_140], eax
0x18001aa31  mov     eax, dword ptr [rsp+170h+var_128+4]
0x18001aa35  mov     [rsp+170h+var_148], eax
0x18001aa39  mov     eax, dword ptr [rsp+170h+var_128+0Ch]
0x18001aa3d  mov     [rsp+170h+var_150], eax
0x18001aa41  mov     r8, rdi
0x18001aa44  mov     rcx, [rcx+10h]
0x18001aa48  call    WPP_SF_dddd
0x18001aa4d  mov     [rbp+70h+var_D8], r13
0x18001aa51  mov     [rsp+170h+var_130], r13
0x18001aa56  lea     rdx, [rsp+170h+var_130]
0x18001aa5b  lea     rcx, [rbp+70h+var_D8]
0x18001aa5f  call    ??4?$SmartPointer@UIEapMethod@EapLm@@@@QEAAAEAV0@AEBV0@@Z; SmartPointer<EapLm::IEapMethod>::operator=(SmartPointer<EapLm::IEapMethod> const &)
0x18001aa64  mov     [rbp+70h+var_D0], r14d
0x18001aa68  lea     rdx, [r15+50h]
0x18001aa6c  lea     rcx, [rsp+170h+var_130]
0x18001aa71  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x18001aa76  nop
0x18001aa77  lea     r8, [rbp+70h+var_D8]
0x18001aa7b  lea     rdx, [rsp+170h+var_128]
0x18001aa80  lea     rcx, [rbp+70h+var_90]
0x18001aa84  call    ??$?0AEAV?$crt_ref@U_EAP_METHOD_INFO@@@@AEAU_EapMethodSlot@EapLm@@$0A@@?$pair@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@QEAA@AEAV?$crt_ref@U_EAP_METHOD_INFO@@@@AEAU_EapMethodSlot@EapLm@@@Z; std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>(crt_ref<_EAP_METHOD_INFO> &,EapLm::_EapMethodSlot &)
0x18001aa89  nop
0x18001aa8a  lea     rcx, [r15+88h]
0x18001aa91  mov     r8, rax
0x18001aa94  lea     rdx, [rbp+70h+var_B8]
0x18001aa98  call    ??$insert@U?$pair@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@$0A@@?$map@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@U?$less@V?$crt_ref@U_EAP_METHOD_INFO@@@@@std@@V?$allocator@U?$pair@$$CBV?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@@5@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@1@@Z; std::map<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::insert<std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>,0>(std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot> &&)
0x18001aa9d  nop
0x18001aa9e  lea     rcx, [rbp+70h+var_90]
0x18001aaa2  call    ??1?$pair@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@QEAA@XZ; std::pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>::~pair<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot>(void)
0x18001aaa7  cmp     [rbp+70h+var_B0], r13b
0x18001aaab  jz      short loc_18001AAC6
0x18001aaad  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aab4  cmp     rcx, rbx
0x18001aab7  jz      short loc_18001AAEA
0x18001aab9  test    byte ptr [rcx+1Ch], 4
0x18001aabd  jz      short loc_18001AAEA
0x18001aabf  mov     edx, 38h ; '8'
0x18001aac4  jmp     short loc_18001AADD
0x18001aac6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aacd  cmp     rcx, rbx
0x18001aad0  jz      short loc_18001AAEA
0x18001aad2  test    byte ptr [rcx+1Ch], 4
0x18001aad6  jz      short loc_18001AAEA
0x18001aad8  mov     edx, 39h ; '9'
0x18001aadd  mov     r8, rdi
0x18001aae0  mov     rcx, [rcx+10h]
0x18001aae4  call    WPP_SF_
0x18001aae9  nop
0x18001aaea  mov     rcx, [rsp+170h+var_130]
0x18001aaef  add     rcx, 10h; lpCriticalSection
0x18001aaf3  call    cs:__imp_LeaveCriticalSection
0x18001aaf9  nop
0x18001aafa  mov     rcx, [rbp+70h+var_D8]; this
0x18001aafe  test    rcx, rcx
0x18001ab01  jz      short loc_18001AB09
0x18001ab03  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x18001ab08  nop
0x18001ab09  lea     rcx, [rsp+170h+var_F8]
0x18001ab0e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001ab13  nop
0x18001ab14  lea     rcx, [rsp+170h+var_128]
0x18001ab19  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<HeapAllocator>(_EAP_METHOD_INFO &)
0x18001ab1e  nop
0x18001ab1f  jmp     loc_18001AC06
0x18001ab24  cmp     rcx, rbx
0x18001ab27  jz      short loc_18001AB59
0x18001ab29  test    byte ptr [rcx+1Ch], 1
0x18001ab2d  jz      short loc_18001AB59
0x18001ab2f  mov     r9d, eax
0x18001ab32  mov     edx, 36h ; '6'
0x18001ab37  mov     eax, dword ptr [rsp+170h+var_128+8]
0x18001ab3b  mov     [rsp+170h+var_140], eax
0x18001ab3f  mov     eax, dword ptr [rsp+170h+var_128+4]
0x18001ab43  mov     [rsp+170h+var_148], eax
0x18001ab47  mov     [rsp+170h+var_150], r8d
0x18001ab4c  mov     r8, rdi
0x18001ab4f  mov     rcx, [rcx+10h]
0x18001ab53  call    WPP_SF_dddd
0x18001ab58  nop
0x18001ab59  lea     rcx, [rsp+170h+var_F8]
0x18001ab5e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001ab63  nop
0x18001ab64  lea     rcx, [rsp+170h+var_128]
0x18001ab69  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<HeapAllocator>(_EAP_METHOD_INFO &)
0x18001ab6e  nop
0x18001ab6f  jmp     loc_18001AC06
0x18001ab74  test    cs:byte_18004E841, 1
0x18001ab7b  jz      short loc_18001ABA3
0x18001ab7d  mov     eax, dword ptr [rsp+170h+var_128+8]
0x18001ab81  mov     [rsp+170h+var_148], eax
0x18001ab85  mov     eax, dword ptr [rsp+170h+var_128+4]
0x18001ab89  mov     [rsp+170h+var_150], eax
0x18001ab8d  mov     r9d, dword ptr [rsp+170h+var_128+0Ch]
0x18001ab92  mov     r8b, byte ptr [rsp+170h+var_128]
0x18001ab97  lea     rdx, MethodAddFailed
0x18001ab9e  call    McTemplateU0uqqq_EtwEventWriteTransfer
0x18001aba3  lea     rbx, WPP_GLOBAL_Control
0x18001abaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001abb1  cmp     rcx, rbx
0x18001abb4  jz      short loc_18001ABF0
0x18001abb6  test    byte ptr [rcx+1Ch], 1
0x18001abba  jz      short loc_18001ABF0
0x18001abbc  movzx   r9d, byte ptr [rsp+170h+var_128]
0x18001abc2  mov     edx, 34h ; '4'
0x18001abc7  mov     eax, dword ptr [rsp+170h+var_128+8]
0x18001abcb  mov     [rsp+170h+var_140], eax
0x18001abcf  mov     eax, dword ptr [rsp+170h+var_128+4]
0x18001abd3  mov     [rsp+170h+var_148], eax
0x18001abd7  mov     eax, dword ptr [rsp+170h+var_128+0Ch]
0x18001abdb  mov     [rsp+170h+var_150], eax
0x18001abdf  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001abe6  mov     rcx, [rcx+10h]
0x18001abea  call    WPP_SF_dddd
0x18001abef  nop
0x18001abf0  lea     rcx, [rsp+170h+var_F8]
0x18001abf5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
  ... truncated ...
```
