# EapLm::BaseEapLibraryManager::Initialize(EapHost::EapMethodType const &)

- ea: `0x18002ca50`
- end: `0x18002ceac`
- name: `?Initialize@BaseEapLibraryManager@EapLm@@MEAAXAEBVEapMethodType@EapHost@@@Z`
- size: `1116`
- prototype: `void __fastcall(EapLm::BaseEapLibraryManager *__hidden this, const struct EapHost::EapMethodType *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800017a0`
- `0x18000213c`
- `0x1800022e0`
- `0x180004ec0`
- `0x18000eb74`
- `0x18000eb94`
- `0x180016518`
- `0x1800165a4`
- `0x180016c54`
- `0x1800216dc`
- `0x18002a7dc`
- `0x18002a8dc`
- `0x18002ab2c`
- `0x18002ac44`
- `0x18002bc04`
- `0x18002c06c`
- `0x18002ca50`
- `0x18002ddf4`

## string_xrefs

- `0x18002caef`: `System\CurrentControlSet\Services\EapHost\Methods`
- `0x18002cc28`: `System\CurrentControlSet\Services\EapHost\Methods`
- `0x18002cad2`: `System\CurrentControlSet\Services\RasMan\PPP\EAP`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall EapLm::BaseEapLibraryManager::Initialize(
        EapLm::BaseEapLibraryManager *this,
        const struct EapHost::EapMethodType *a2)
{
  EapLm::BaseEapLibraryManager *v3; // rdi
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r9
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // r10
  int v14; // r8d
  const EapHost::EapException *v15; // r15
  DWORD v16; // eax
  int v17; // ecx
  int v18; // r9d
  int v19; // ebx
  int v20; // edi
  unsigned __int8 v21; // si
  unsigned int v22; // r14d
  int v23; // eax
  __int64 v24; // r8
  const Exception *v25; // r15
  DWORD v26; // eax
  int v27; // ecx
  int v28; // r9d
  int v29; // ebx
  int v30; // edi
  unsigned __int8 v31; // si
  unsigned int v32; // r14d
  int v33; // eax
  __int64 v34; // r8
  __int64 v35; // [rsp+20h] [rbp-B38h]
  __int64 v36; // [rsp+40h] [rbp-B18h] BYREF
  int v37; // [rsp+48h] [rbp-B10h]
  __int64 v38; // [rsp+50h] [rbp-B08h] BYREF
  int v39; // [rsp+58h] [rbp-B00h]
  EapLm::BaseEapLibraryManager *v40; // [rsp+60h] [rbp-AF8h]
  const EapHost::EapException *v41; // [rsp+68h] [rbp-AF0h] BYREF
  const Exception *v42; // [rsp+70h] [rbp-AE8h] BYREF
  _BYTE v43[16]; // [rsp+78h] [rbp-AE0h] BYREF
  __int64 v44; // [rsp+88h] [rbp-AD0h]
  unsigned __int8 v45; // [rsp+98h] [rbp-AC0h] BYREF
  __int16 v46; // [rsp+99h] [rbp-ABFh]
  char v47; // [rsp+9Bh] [rbp-ABDh]
  __int64 v48; // [rsp+9Ch] [rbp-ABCh]
  unsigned int v49; // [rsp+A4h] [rbp-AB4h]
  wchar_t v50[8]; // [rsp+A8h] [rbp-AB0h] BYREF
  __int128 v51; // [rsp+B8h] [rbp-AA0h]
  __int64 v52; // [rsp+C8h] [rbp-A90h]
  wchar_t Buffer[152]; // [rsp+D0h] [rbp-A88h] BYREF
  wchar_t v54[152]; // [rsp+200h] [rbp-958h] BYREF
  WCHAR v55[1024]; // [rsp+330h] [rbp-828h] BYREF

  v3 = this;
  v40 = this;
  memset_0(Buffer, 0, 0x12Cu);
  memset_0(v54, 0, 0x12Cu);
  v38 = 0;
  v39 = 1;
  if ( *((_DWORD *)a2 + 6) )
  {
    if ( *((_BYTE *)a2 + 8) == 0xFE )
      swprintf_s(
        Buffer,
        0x96u,
        L"%ws\\%d\\%d\\%d\\%d",
        L"System\\CurrentControlSet\\Services\\EapHost\\Methods",
        *((_DWORD *)a2 + 6),
        254,
        *((_DWORD *)a2 + 3),
        *((_DWORD *)a2 + 4));
    else
      swprintf_s(
        Buffer,
        0x96u,
        L"%ws\\%d\\%d",
        L"System\\CurrentControlSet\\Services\\EapHost\\Methods",
        *((_DWORD *)a2 + 6),
        *((unsigned __int8 *)a2 + 8));
  }
  else
  {
    swprintf_s(
      Buffer,
      0x96u,
      L"%ws\\%d",
      L"System\\CurrentControlSet\\Services\\RasMan\\PPP\\EAP",
      *((unsigned __int8 *)a2 + 8));
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, Buffer);
  v4 = RegistryKey::Open((__int64)&v38, HKEY_LOCAL_MACHINE, Buffer, 9);
  if ( !v4 )
  {
    v8 = *((_DWORD *)a2 + 6);
    if ( !v8 )
    {
      EapLm::BaseEapLibraryManager::AddLegacyEapMethod(v3, (const struct RegistryKey *)&v38, *((_BYTE *)a2 + 8));
LABEL_42:
      *((_BYTE *)v3 + 72) = 1;
      goto LABEL_43;
    }
    v36 = 0;
    v37 = 1;
    LODWORD(v35) = v8;
    swprintf_s(v54, 0x96u, L"%ws\\%d", L"System\\CurrentControlSet\\Services\\EapHost\\Methods", v35);
    if ( (unsigned int)RegistryKey::Open((__int64)&v36, HKEY_LOCAL_MACHINE, v54, 9) )
    {
      if ( (Microsoft_Windows_EapHostEnableBits & 8) != 0 )
        McTemplateU0z_EtwEventWriteTransfer(v10, v9, v54);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, v54);
      goto LABEL_41;
    }
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v43);
    if ( (unsigned int)RegistryKey::ReadMuiString(&v36, L"Name", v43) )
      RegistryKey::QueryValue(&v36, L"Name", v43);
    if ( !v44 )
    {
      if ( (unsigned int)RegistryKey::ReadMuiString(&v36, &qword_18003A720, v43) )
        RegistryKey::QueryValue(&v36, &qword_18003A720, v43);
      if ( !v44 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
        *(_OWORD *)v50 = 0;
        v51 = 0;
        v52 = 0;
        swprintf_s(v50, 0x14u, L"AuthorId: %d", *((unsigned int *)a2 + 6));
        v11 = -1;
        do
          ++v11;
        while ( v50[v11] );
        std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::assign(v43, v50);
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v12 = ((__int64 (__fastcall *)(_BYTE *))std::_String_val<std::_Simple_types<wchar_t>>::_Myptr)(v43);
      WPP_SF_S(*(_QWORD *)(v13 + 16), 14, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, v12);
    }
    v46 = 0;
    v47 = 0;
    v48 = 0;
    v49 = *((_DWORD *)a2 + 6);
    v45 = *((_BYTE *)a2 + 8);
    if ( v45 == 0xFE )
      v48 = *(_QWORD *)((char *)a2 + 12);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      EapLm::BaseEapLibraryManager::AddOneEapMethod((__int64)v3, (__int64)&v38, (__int128 *)&v45, (__int64)v43);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
          McGenEventWrite_EtwEventWriteTransfer(
            (_QWORD *)(unsigned int)&eaphost_Context,
            (unsigned int)OutOfMemory,
            v14,
            1,
            (__int64)&v45);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
        throw;
      }
      if ( __eh34_catch_type(0, &EapHost::EapException `RTTI Type Descriptor', &v41) )
      {
        v15 = v41;
        v16 = (*(__int64 (__fastcall **)(const EapHost::EapException *))(*(_QWORD *)v41 + 16LL))(v41);
        FormatMessageW(0x1200u, 0, v16, 0, v55, 0x400u, 0);
        v19 = HIDWORD(v48);
        v20 = v48;
        v21 = v45;
        v22 = v49;
        if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
        {
          LOBYTE(v18) = v45;
          McTemplateU0quqqz_EtwEventWriteTransfer(v17, (int)EapExceptionEvent, v49, v18, v48, SBYTE4(v48), (__int64)v55);
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v23 = (*(__int64 (__fastcall **)(const EapHost::EapException *))(*(_QWORD *)v15 + 16LL))(v15);
          WPP_SF_ddddD(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v24, v22, v21, v20, v19, v23);
        }
        v3 = v40;
        __eh34_try_continuation(0, &EapHost::EapException `RTTI Type Descriptor', &loc_18002CE12);
        goto LABEL_35;
      }
      if ( __eh34_catch_type(0, &Exception `RTTI Type Descriptor', &v42) )
      {
        v25 = v42;
        v26 = (*(__int64 (__fastcall **)(const Exception *))(*(_QWORD *)v42 + 16LL))(v42);
        FormatMessageW(0x1200u, 0, v26, 0, v55, 0x400u, 0);
        v29 = HIDWORD(v48);
        v30 = v48;
        v31 = v45;
        v32 = v49;
        if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
        {
          LOBYTE(v28) = v45;
          McTemplateU0quqqz_EtwEventWriteTransfer(v27, (int)ExceptionEvent, v49, v28, v48, SBYTE4(v48), (__int64)v55);
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v33 = (*(__int64 (__fastcall **)(const Exception *))(*(_QWORD *)v25 + 16LL))(v25);
          WPP_SF_ddddD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v34, v32, v31, v30, v29, v33);
        }
        v3 = v40;
        __eh34_try_continuation(0, &Exception `RTTI Type Descriptor', &loc_18002CE14);
      }
    }
LABEL_35:
    std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v43);
LABEL_41:
    RegistryKey::Clear((HKEY *)&v36);
    goto LABEL_42;
  }
  if ( (Microsoft_Windows_EapHostEnableBits & 8) != 0 )
  {
    LOBYTE(v7) = v4;
    McTemplateU0zc_EtwEventWriteTransfer(v6, v5, Buffer, v7);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, Buffer);
LABEL_43:
  RegistryKey::Clear((HKEY *)&v38);
}

```

## disassembly

```asm
0x18002ca50  mov     [rsp+arg_10], rbx
0x18002ca55  mov     [rsp+arg_18], rsi
0x18002ca5a  push    rdi
0x18002ca5b  push    r14
0x18002ca5d  push    r15
0x18002ca5f  sub     rsp, 0B40h
0x18002ca66  mov     rax, cs:__security_cookie
0x18002ca6d  xor     rax, rsp
0x18002ca70  mov     [rsp+0B58h+var_28], rax
0x18002ca78  mov     rbx, rdx
0x18002ca7b  mov     rdi, rcx
0x18002ca7e  mov     [rsp+0B58h+var_AF8], rcx
0x18002ca83  mov     esi, 12Ch
0x18002ca88  mov     r8d, esi; Size
0x18002ca8b  xor     edx, edx; Val
0x18002ca8d  lea     rcx, [rsp+0B58h+Buffer]; void *
0x18002ca95  call    memset_0
0x18002ca9a  mov     r8d, esi; Size
0x18002ca9d  xor     edx, edx; Val
0x18002ca9f  lea     rcx, [rsp+0B58h+var_958]; void *
0x18002caa7  call    memset_0
0x18002caac  xor     r14d, r14d
0x18002caaf  mov     [rsp+0B58h+var_B08], r14
0x18002cab4  mov     [rsp+0B58h+var_B00], 1
0x18002cabc  mov     ecx, [rbx+18h]
0x18002cabf  mov     esi, 96h
0x18002cac4  mov     edx, esi; BufferCount
0x18002cac6  test    ecx, ecx
0x18002cac8  jnz     short loc_18002CAEF
0x18002caca  movzx   eax, byte ptr [rbx+8]
0x18002cace  mov     dword ptr [rsp+0B58h+var_B38], eax
0x18002cad2  lea     r9, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Ra"...
0x18002cad9  lea     r8, aWsD; "%ws\\%d"
0x18002cae0  lea     rcx, [rsp+0B58h+Buffer]; Buffer
0x18002cae8  call    swprintf_s
0x18002caed  jmp     short loc_18002CB4C
0x18002caef  lea     r9, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Ea"...
0x18002caf6  cmp     byte ptr [rbx+8], 0FEh
0x18002cafa  jnz     short loc_18002CB2C
0x18002cafc  mov     eax, [rbx+10h]
0x18002caff  mov     [rsp+0B58h+var_B20], eax
0x18002cb03  mov     eax, [rbx+0Ch]
0x18002cb06  mov     [rsp+0B58h+var_B28], eax
0x18002cb0a  mov     [rsp+0B58h+var_B30], 0FEh
0x18002cb12  mov     dword ptr [rsp+0B58h+var_B38], ecx
0x18002cb16  lea     r8, aWsDDDD; "%ws\\%d\\%d\\%d\\%d"
0x18002cb1d  lea     rcx, [rsp+0B58h+Buffer]; Buffer
0x18002cb25  call    swprintf_s
0x18002cb2a  jmp     short loc_18002CB4C
0x18002cb2c  movzx   eax, byte ptr [rbx+8]
0x18002cb30  mov     [rsp+0B58h+var_B30], eax
0x18002cb34  mov     dword ptr [rsp+0B58h+var_B38], ecx
0x18002cb38  lea     r8, aWsDD; "%ws\\%d\\%d"
0x18002cb3f  lea     rcx, [rsp+0B58h+Buffer]; Buffer
0x18002cb47  call    swprintf_s
0x18002cb4c  lea     r15, WPP_GLOBAL_Control
0x18002cb53  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cb5a  cmp     rcx, r15
0x18002cb5d  jz      short loc_18002CB82
0x18002cb5f  test    byte ptr [rcx+1Ch], 4
0x18002cb63  jz      short loc_18002CB82
0x18002cb65  mov     edx, 0Bh
0x18002cb6a  lea     r9, [rsp+0B58h+Buffer]
0x18002cb72  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18002cb79  mov     rcx, [rcx+10h]
0x18002cb7d  call    WPP_SF_S
0x18002cb82  mov     r9d, 9
0x18002cb88  lea     r8, [rsp+0B58h+Buffer]
0x18002cb90  mov     rdx, 0FFFFFFFF80000002h
0x18002cb97  lea     rcx, [rsp+0B58h+var_B08]
0x18002cb9c  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18002cba1  test    eax, eax
0x18002cba3  jz      short loc_18002CBFA
0x18002cba5  test    cs:Microsoft_Windows_EapHostEnableBits, 8
0x18002cbac  jz      short loc_18002CBBE
0x18002cbae  mov     r9b, al
0x18002cbb1  lea     r8, [rsp+0B58h+Buffer]
0x18002cbb9  call    McTemplateU0zc_EtwEventWriteTransfer
0x18002cbbe  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cbc5  cmp     rcx, r15
0x18002cbc8  jz      loc_18002CE79
0x18002cbce  test    byte ptr [rcx+1Ch], 1
0x18002cbd2  jz      loc_18002CE79
0x18002cbd8  mov     edx, 0Ch
0x18002cbdd  lea     r9, [rsp+0B58h+Buffer]
0x18002cbe5  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18002cbec  mov     rcx, [rcx+10h]
0x18002cbf0  call    WPP_SF_S
0x18002cbf5  jmp     loc_18002CE79
0x18002cbfa  mov     eax, [rbx+18h]
0x18002cbfd  test    eax, eax
0x18002cbff  jnz     short loc_18002CC17
0x18002cc01  mov     r8b, [rbx+8]; unsigned __int8
0x18002cc05  lea     rdx, [rsp+0B58h+var_B08]; struct RegistryKey *
0x18002cc0a  mov     rcx, rdi; this
0x18002cc0d  call    ?AddLegacyEapMethod@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@E@Z; EapLm::BaseEapLibraryManager::AddLegacyEapMethod(RegistryKey const &,uchar)
0x18002cc12  jmp     loc_18002CE75
0x18002cc17  mov     [rsp+0B58h+var_B18], r14
0x18002cc1c  mov     [rsp+0B58h+var_B10], 1
0x18002cc24  mov     dword ptr [rsp+0B58h+var_B38], eax
0x18002cc28  lea     r9, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Ea"...
0x18002cc2f  lea     r8, aWsD; "%ws\\%d"
0x18002cc36  mov     rdx, rsi; BufferCount
0x18002cc39  lea     rcx, [rsp+0B58h+var_958]; Buffer
0x18002cc41  call    swprintf_s
0x18002cc46  mov     r9d, 9
0x18002cc4c  lea     r8, [rsp+0B58h+var_958]
0x18002cc54  mov     rdx, 0FFFFFFFF80000002h
0x18002cc5b  lea     rcx, [rsp+0B58h+var_B18]
0x18002cc60  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18002cc65  test    eax, eax
0x18002cc67  jnz     loc_18002CE25
0x18002cc6d  lea     rcx, [rsp+0B58h+var_AE0]
0x18002cc72  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x18002cc77  nop
0x18002cc78  lea     r8, [rsp+0B58h+var_AE0]
0x18002cc7d  lea     rdx, aName; "Name"
0x18002cc84  lea     rcx, [rsp+0B58h+var_B18]
0x18002cc89  call    ?ReadMuiString@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::ReadMuiString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18002cc8e  test    eax, eax
0x18002cc90  jz      short loc_18002CCA8
0x18002cc92  lea     r8, [rsp+0B58h+var_AE0]
0x18002cc97  lea     rdx, aName; "Name"
0x18002cc9e  lea     rcx, [rsp+0B58h+var_B18]
0x18002cca3  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18002cca8  cmp     [rsp+0B58h+var_AD0], r14
0x18002ccb0  jnz     loc_18002CD7B
0x18002ccb6  lea     r8, [rsp+0B58h+var_AE0]
0x18002ccbb  lea     rdx, qword_18003A720
0x18002ccc2  lea     rcx, [rsp+0B58h+var_B18]
0x18002ccc7  call    ?ReadMuiString@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::ReadMuiString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18002cccc  test    eax, eax
0x18002ccce  jz      short loc_18002CCE6
0x18002ccd0  lea     r8, [rsp+0B58h+var_AE0]
0x18002ccd5  lea     rdx, qword_18003A720
0x18002ccdc  lea     rcx, [rsp+0B58h+var_B18]
0x18002cce1  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18002cce6  cmp     [rsp+0B58h+var_AD0], r14
0x18002ccee  jnz     loc_18002CD7B
0x18002ccf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ccfb  cmp     rcx, r15
0x18002ccfe  jz      short loc_18002CD1B
0x18002cd00  test    byte ptr [rcx+1Ch], 4
0x18002cd04  jz      short loc_18002CD1B
0x18002cd06  mov     edx, 0Dh
0x18002cd0b  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18002cd12  mov     rcx, [rcx+10h]
0x18002cd16  call    WPP_SF_
0x18002cd1b  xorps   xmm0, xmm0
0x18002cd1e  xor     eax, eax
0x18002cd20  movups  xmmword ptr [rsp+0B58h+var_AB0], xmm0
0x18002cd28  movups  [rsp+0B58h+var_AA0], xmm0
0x18002cd30  mov     [rsp+0B58h+var_A90], rax
0x18002cd38  mov     r9d, [rbx+18h]
0x18002cd3c  lea     r8, aAuthoridD; "AuthorId: %d"
0x18002cd43  lea     edx, [rax+14h]; BufferCount
0x18002cd46  lea     rcx, [rsp+0B58h+var_AB0]; Buffer
0x18002cd4e  call    swprintf_s
0x18002cd53  lea     rax, [rsp+0B58h+var_AB0]
0x18002cd5b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002cd5f  inc     r8
0x18002cd62  cmp     [rax+r8*2], r14w
0x18002cd67  jnz     short loc_18002CD5F
0x18002cd69  lea     rdx, [rsp+0B58h+var_AB0]
0x18002cd71  lea     rcx, [rsp+0B58h+var_AE0]
0x18002cd76  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAAAEAV12@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::assign(wchar_t const * const,unsigned __int64)
0x18002cd7b  mov     r10, cs:WPP_GLOBAL_Control
0x18002cd82  cmp     r10, r15
0x18002cd85  jz      short loc_18002CDB0
0x18002cd87  test    byte ptr [r10+1Ch], 4
0x18002cd8c  jz      short loc_18002CDB0
0x18002cd8e  lea     rcx, [rsp+0B58h+var_AE0]
0x18002cd93  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002cd98  mov     r9, rax
0x18002cd9b  mov     edx, 0Eh
0x18002cda0  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18002cda7  mov     rcx, [r10+10h]
0x18002cdab  call    WPP_SF_S
0x18002cdb0  xor     eax, eax
0x18002cdb2  mov     [rsp+0B58h+var_ABF], ax
0x18002cdba  mov     [rsp+0B58h+var_ABD], al
0x18002cdc1  mov     [rsp+0B58h+var_ABC], rax
0x18002cdc9  mov     eax, [rbx+18h]
0x18002cdcc  mov     [rsp+0B58h+var_AB4], eax
0x18002cdd3  mov     al, [rbx+8]
0x18002cdd6  mov     [rsp+0B58h+var_AC0], al
0x18002cddd  cmp     al, 0FEh
0x18002cddf  jnz     short loc_18002CDF5
0x18002cde1  mov     eax, [rbx+0Ch]
0x18002cde4  mov     dword ptr [rsp+0B58h+var_ABC], eax
0x18002cdeb  mov     eax, [rbx+10h]
0x18002cdee  mov     dword ptr [rsp+0B58h+var_ABC+4], eax
0x18002cdf5  lea     r9, [rsp+0B58h+var_AE0]
0x18002cdfa  lea     r8, [rsp+0B58h+var_AC0]
0x18002ce02  lea     rdx, [rsp+0B58h+var_B08]
0x18002ce07  mov     rcx, rdi
0x18002ce0a  call    ?AddOneEapMethod@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@AEBU_EAP_METHOD_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; EapLm::BaseEapLibraryManager::AddOneEapMethod(RegistryKey const &,_EAP_METHOD_TYPE const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18002ce0f  nop
0x18002ce10  jmp     short loc_18002CE19
0x18002ce12  jmp     short $+2
0x18002ce14  mov     rdi, [rsp+0B58h+var_AF8]
0x18002ce19  lea     rcx, [rsp+0B58h+var_AE0]
0x18002ce1e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18002ce23  jmp     short loc_18002CE6B
0x18002ce25  test    cs:Microsoft_Windows_EapHostEnableBits, 8
0x18002ce2c  jz      short loc_18002CE3B
0x18002ce2e  lea     r8, [rsp+0B58h+var_958]
0x18002ce36  call    McTemplateU0z_EtwEventWriteTransfer
0x18002ce3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ce42  cmp     rcx, r15
0x18002ce45  jz      short loc_18002CE6B
0x18002ce47  test    byte ptr [rcx+1Ch], 1
0x18002ce4b  jz      short loc_18002CE6B
0x18002ce4d  mov     edx, 12h
0x18002ce52  lea     r9, [rsp+0B58h+var_958]
0x18002ce5a  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18002ce61  mov     rcx, [rcx+10h]
0x18002ce65  call    WPP_SF_S
0x18002ce6a  nop
0x18002ce6b  lea     rcx, [rsp+0B58h+var_B18]; this
0x18002ce70  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18002ce75  mov     byte ptr [rdi+48h], 1
0x18002ce79  lea     rcx, [rsp+0B58h+var_B08]; this
0x18002ce7e  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18002ce83  mov     rcx, [rsp+0B58h+var_28]
0x18002ce8b  xor     rcx, rsp; StackCookie
0x18002ce8e  call    __security_check_cookie
0x18002ce93  lea     r11, [rsp+0B58h+var_18]
0x18002ce9b  mov     rbx, [r11+30h]
0x18002ce9f  mov     rsi, [r11+38h]
0x18002cea3  mov     rsp, r11
0x18002cea6  pop     r15
0x18002cea8  pop     r14
0x18002ceaa  pop     rdi
0x18002ceab  retn
```
