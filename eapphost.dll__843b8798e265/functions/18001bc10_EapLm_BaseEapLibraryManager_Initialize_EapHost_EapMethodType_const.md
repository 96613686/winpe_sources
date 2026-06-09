# EapLm::BaseEapLibraryManager::Initialize(EapHost::EapMethodType const &)

- ea: `0x18001bc10`
- end: `0x18001c06d`
- name: `?Initialize@BaseEapLibraryManager@EapLm@@MEAAXAEBVEapMethodType@EapHost@@@Z`
- size: `1117`
- prototype: `void __fastcall(EapLm::BaseEapLibraryManager *__hidden this, const struct EapHost::EapMethodType *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180002af0`
- `0x1800034cc`
- `0x18000352c`
- `0x18000a21c`
- `0x18000a3e4`
- `0x180011218`
- `0x18001204c`
- `0x18001206c`
- `0x18001acdc`
- `0x18001b14c`
- `0x18001bc10`
- `0x18001cf5c`
- `0x18001d298`
- `0x18001d328`
- `0x180031314`
- `0x180031424`
- `0x18003165c`
- `0x180031778`

## string_xrefs

- `0x18001bcaf`: `System\CurrentControlSet\Services\EapHost\Methods`
- `0x18001bde8`: `System\CurrentControlSet\Services\EapHost\Methods`
- `0x18001bc92`: `System\CurrentControlSet\Services\RasMan\PPP\EAP`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
  __int64 v12; // r9
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // r10
  __int64 v16; // r8
  const EapHost::EapException *v17; // r15
  DWORD v18; // eax
  int v19; // ecx
  int v20; // r9d
  int v21; // ebx
  int v22; // edi
  unsigned __int8 v23; // si
  unsigned int v24; // r14d
  int v25; // eax
  __int64 v26; // r8
  const Exception *v27; // r15
  DWORD v28; // eax
  int v29; // ecx
  int v30; // r9d
  int v31; // ebx
  int v32; // edi
  unsigned __int8 v33; // si
  unsigned int v34; // r14d
  int v35; // eax
  __int64 v36; // r8
  __int64 v37; // [rsp+20h] [rbp-B38h]
  __int64 v38; // [rsp+40h] [rbp-B18h] BYREF
  int v39; // [rsp+48h] [rbp-B10h]
  __int64 v40; // [rsp+50h] [rbp-B08h] BYREF
  int v41; // [rsp+58h] [rbp-B00h]
  EapLm::BaseEapLibraryManager *v42; // [rsp+60h] [rbp-AF8h]
  const EapHost::EapException *v43; // [rsp+68h] [rbp-AF0h] BYREF
  const Exception *v44; // [rsp+70h] [rbp-AE8h] BYREF
  _BYTE v45[16]; // [rsp+78h] [rbp-AE0h] BYREF
  __int64 v46; // [rsp+88h] [rbp-AD0h]
  unsigned __int8 v47; // [rsp+98h] [rbp-AC0h] BYREF
  __int16 v48; // [rsp+99h] [rbp-ABFh]
  char v49; // [rsp+9Bh] [rbp-ABDh]
  __int64 v50; // [rsp+9Ch] [rbp-ABCh]
  unsigned int v51; // [rsp+A4h] [rbp-AB4h]
  wchar_t v52[8]; // [rsp+A8h] [rbp-AB0h] BYREF
  __int128 v53; // [rsp+B8h] [rbp-AA0h]
  __int64 v54; // [rsp+C8h] [rbp-A90h]
  wchar_t Buffer[152]; // [rsp+D0h] [rbp-A88h] BYREF
  wchar_t v56[152]; // [rsp+200h] [rbp-958h] BYREF
  WCHAR v57[1024]; // [rsp+330h] [rbp-828h] BYREF

  v3 = this;
  v42 = this;
  memset_0(Buffer, 0, 0x12Cu);
  memset_0(v56, 0, 0x12Cu);
  v40 = 0;
  v41 = 1;
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
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, Buffer);
  }
  v4 = RegistryKey::Open((RegistryKey *)&v40, HKEY_LOCAL_MACHINE, Buffer, 9);
  if ( v4 )
  {
    if ( (Microsoft_Windows_EapHostEnableBits & 8) != 0 )
    {
      LOBYTE(v7) = v4;
      McTemplateU0zc_EtwEventWriteTransfer(v6, v5, Buffer, v7);
    }
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, Buffer);
    }
  }
  else
  {
    v8 = *((_DWORD *)a2 + 6);
    if ( v8 )
    {
      v38 = 0;
      v39 = 1;
      LODWORD(v37) = v8;
      swprintf_s(v56, 0x96u, L"%ws\\%d", L"System\\CurrentControlSet\\Services\\EapHost\\Methods", v37);
      if ( (unsigned int)RegistryKey::Open((RegistryKey *)&v38, HKEY_LOCAL_MACHINE, v56, 9) )
      {
        if ( (Microsoft_Windows_EapHostEnableBits & 8) != 0 )
          McTemplateU0z_EtwEventWriteTransfer(v10, v9, v56);
        if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, v56);
        }
      }
      else
      {
        std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
          v45,
          v9,
          v11,
          v12);
        if ( (unsigned int)RegistryKey::ReadMuiString(&v38, L"Name", v45) )
          RegistryKey::QueryValue(&v38, L"Name", v45);
        if ( !v46 )
        {
          if ( (unsigned int)RegistryKey::ReadMuiString(&v38, &qword_18003D520, v45) )
            RegistryKey::QueryValue(&v38, &qword_18003D520, v45);
          if ( !v46 )
          {
            if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
            }
            *(_OWORD *)v52 = 0;
            v53 = 0;
            v54 = 0;
            swprintf_s(v52, 0x14u, L"AuthorId: %d", *((unsigned int *)a2 + 6));
            v13 = -1;
            do
              ++v13;
            while ( v52[v13] );
            std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::assign(v45, v52);
          }
        }
        if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v14 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v45);
          WPP_SF_S(*(_QWORD *)(v15 + 16), 14, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, v14);
        }
        v48 = 0;
        v49 = 0;
        v50 = 0;
        v51 = *((_DWORD *)a2 + 6);
        v47 = *((_BYTE *)a2 + 8);
        if ( v47 == 0xFE )
          v50 = *(_QWORD *)((char *)a2 + 12);
        try
        {
          EapLm::BaseEapLibraryManager::AddOneEapMethod(v3, &v40, &v47, v45);
        }
        catch ( std::bad_alloc )
        {
          if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
            McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)OutOfMemory, v16, 1, (__int64)&v47);
          if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
          }
          throw;
        }
        catch ( const EapHost::EapException *v43 )
        {
          v17 = v43;
          v18 = (*(__int64 (__fastcall **)(const EapHost::EapException *))(*(_QWORD *)v43 + 16LL))(v43);
          FormatMessageW(0x1200u, 0, v18, 0, v57, 0x400u, 0);
          v21 = HIDWORD(v50);
          v22 = v50;
          v23 = v47;
          v24 = v51;
          if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
          {
            LOBYTE(v20) = v47;
            McTemplateU0quqqz_EtwEventWriteTransfer(
              v19,
              (unsigned int)EapExceptionEvent,
              v51,
              v20,
              v50,
              SBYTE4(v50),
              (__int64)v57);
          }
          if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v25 = (*(__int64 (__fastcall **)(const EapHost::EapException *))(*(_QWORD *)v17 + 16LL))(v17);
            WPP_SF_ddddD(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v26, v24, v23, v22, v21, v25);
          }
          v3 = v42;
        }
        catch ( const Exception *v44 )
        {
          v27 = v44;
          v28 = (*(__int64 (__fastcall **)(const Exception *))(*(_QWORD *)v44 + 16LL))(v44);
          FormatMessageW(0x1200u, 0, v28, 0, v57, 0x400u, 0);
          v31 = HIDWORD(v50);
          v32 = v50;
          v33 = v47;
          v34 = v51;
          if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
          {
            LOBYTE(v30) = v47;
            McTemplateU0quqqz_EtwEventWriteTransfer(
              v29,
              (unsigned int)ExceptionEvent,
              v51,
              v30,
              v50,
              SBYTE4(v50),
              (__int64)v57);
          }
          if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v35 = (*(__int64 (__fastcall **)(const Exception *))(*(_QWORD *)v27 + 16LL))(v27);
            WPP_SF_ddddD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v36, v34, v33, v32, v31, v35);
          }
          v3 = v42;
        }
        std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v45);
      }
      RegistryKey::Clear((RegistryKey *)&v38);
    }
    else
    {
      EapLm::BaseEapLibraryManager::AddLegacyEapMethod(v3, (const struct RegistryKey *)&v40, *((_BYTE *)a2 + 8));
    }
    *((_BYTE *)v3 + 72) = 1;
  }
  RegistryKey::Clear((RegistryKey *)&v40);
}

```

## disassembly

```asm
0x18001bc10  mov     [rsp+arg_10], rbx
0x18001bc15  mov     [rsp+arg_18], rsi
0x18001bc1a  push    rdi
0x18001bc1b  push    r14
0x18001bc1d  push    r15
0x18001bc1f  sub     rsp, 0B40h
0x18001bc26  mov     rax, cs:__security_cookie
0x18001bc2d  xor     rax, rsp
0x18001bc30  mov     [rsp+0B58h+var_28], rax
0x18001bc38  mov     rbx, rdx
0x18001bc3b  mov     rdi, rcx
0x18001bc3e  mov     [rsp+0B58h+var_AF8], rcx
0x18001bc43  mov     esi, 12Ch
0x18001bc48  mov     r8d, esi; Size
0x18001bc4b  xor     edx, edx; Val
0x18001bc4d  lea     rcx, [rsp+0B58h+Buffer]; void *
0x18001bc55  call    memset_0
0x18001bc5a  mov     r8d, esi; Size
0x18001bc5d  xor     edx, edx; Val
0x18001bc5f  lea     rcx, [rsp+0B58h+var_958]; void *
0x18001bc67  call    memset_0
0x18001bc6c  xor     r14d, r14d
0x18001bc6f  mov     [rsp+0B58h+var_B08], r14
0x18001bc74  mov     [rsp+0B58h+var_B00], 1
0x18001bc7c  mov     ecx, [rbx+18h]
0x18001bc7f  mov     esi, 96h
0x18001bc84  mov     edx, esi; BufferCount
0x18001bc86  test    ecx, ecx
0x18001bc88  jnz     short loc_18001BCAF
0x18001bc8a  movzx   eax, byte ptr [rbx+8]
0x18001bc8e  mov     dword ptr [rsp+0B58h+var_B38], eax
0x18001bc92  lea     r9, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Ra"...
0x18001bc99  lea     r8, aWsD; "%ws\\%d"
0x18001bca0  lea     rcx, [rsp+0B58h+Buffer]; Buffer
0x18001bca8  call    swprintf_s
0x18001bcad  jmp     short loc_18001BD0C
0x18001bcaf  lea     r9, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Ea"...
0x18001bcb6  cmp     byte ptr [rbx+8], 0FEh
0x18001bcba  jnz     short loc_18001BCEC
0x18001bcbc  mov     eax, [rbx+10h]
0x18001bcbf  mov     [rsp+0B58h+var_B20], eax
0x18001bcc3  mov     eax, [rbx+0Ch]
0x18001bcc6  mov     [rsp+0B58h+var_B28], eax
0x18001bcca  mov     [rsp+0B58h+var_B30], 0FEh
0x18001bcd2  mov     dword ptr [rsp+0B58h+var_B38], ecx
0x18001bcd6  lea     r8, aWsDDDD; "%ws\\%d\\%d\\%d\\%d"
0x18001bcdd  lea     rcx, [rsp+0B58h+Buffer]; Buffer
0x18001bce5  call    swprintf_s
0x18001bcea  jmp     short loc_18001BD0C
0x18001bcec  movzx   eax, byte ptr [rbx+8]
0x18001bcf0  mov     [rsp+0B58h+var_B30], eax
0x18001bcf4  mov     dword ptr [rsp+0B58h+var_B38], ecx
0x18001bcf8  lea     r8, aWsDD; "%ws\\%d\\%d"
0x18001bcff  lea     rcx, [rsp+0B58h+Buffer]; Buffer
0x18001bd07  call    swprintf_s
0x18001bd0c  lea     r15, WPP_GLOBAL_Control
0x18001bd13  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd1a  cmp     rcx, r15
0x18001bd1d  jz      short loc_18001BD42
0x18001bd1f  test    byte ptr [rcx+1Ch], 4
0x18001bd23  jz      short loc_18001BD42
0x18001bd25  mov     edx, 0Bh
0x18001bd2a  lea     r9, [rsp+0B58h+Buffer]
0x18001bd32  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001bd39  mov     rcx, [rcx+10h]
0x18001bd3d  call    WPP_SF_S
0x18001bd42  mov     r9d, 9
0x18001bd48  lea     r8, [rsp+0B58h+Buffer]
0x18001bd50  mov     rdx, 0FFFFFFFF80000002h
0x18001bd57  lea     rcx, [rsp+0B58h+var_B08]
0x18001bd5c  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001bd61  test    eax, eax
0x18001bd63  jz      short loc_18001BDBA
0x18001bd65  test    cs:Microsoft_Windows_EapHostEnableBits, 8
0x18001bd6c  jz      short loc_18001BD7E
0x18001bd6e  mov     r9b, al
0x18001bd71  lea     r8, [rsp+0B58h+Buffer]
0x18001bd79  call    McTemplateU0zc_EtwEventWriteTransfer
0x18001bd7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd85  cmp     rcx, r15
0x18001bd88  jz      loc_18001C039
0x18001bd8e  test    byte ptr [rcx+1Ch], 1
0x18001bd92  jz      loc_18001C039
0x18001bd98  mov     edx, 0Ch
0x18001bd9d  lea     r9, [rsp+0B58h+Buffer]
0x18001bda5  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001bdac  mov     rcx, [rcx+10h]
0x18001bdb0  call    WPP_SF_S
0x18001bdb5  jmp     loc_18001C039
0x18001bdba  mov     eax, [rbx+18h]
0x18001bdbd  test    eax, eax
0x18001bdbf  jnz     short loc_18001BDD7
0x18001bdc1  mov     r8b, [rbx+8]; unsigned __int8
0x18001bdc5  lea     rdx, [rsp+0B58h+var_B08]; struct RegistryKey *
0x18001bdca  mov     rcx, rdi; this
0x18001bdcd  call    ?AddLegacyEapMethod@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@E@Z; EapLm::BaseEapLibraryManager::AddLegacyEapMethod(RegistryKey const &,uchar)
0x18001bdd2  jmp     loc_18001C035
0x18001bdd7  mov     [rsp+0B58h+var_B18], r14
0x18001bddc  mov     [rsp+0B58h+var_B10], 1
0x18001bde4  mov     dword ptr [rsp+0B58h+var_B38], eax
0x18001bde8  lea     r9, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Ea"...
0x18001bdef  lea     r8, aWsD; "%ws\\%d"
0x18001bdf6  mov     rdx, rsi; BufferCount
0x18001bdf9  lea     rcx, [rsp+0B58h+var_958]; Buffer
0x18001be01  call    swprintf_s
0x18001be06  mov     r9d, 9
0x18001be0c  lea     r8, [rsp+0B58h+var_958]
0x18001be14  mov     rdx, 0FFFFFFFF80000002h
0x18001be1b  lea     rcx, [rsp+0B58h+var_B18]
0x18001be20  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001be25  test    eax, eax
0x18001be27  jnz     loc_18001BFE5
0x18001be2d  lea     rcx, [rsp+0B58h+var_AE0]
0x18001be32  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x18001be37  nop
0x18001be38  lea     r8, [rsp+0B58h+var_AE0]
0x18001be3d  lea     rdx, aName; "Name"
0x18001be44  lea     rcx, [rsp+0B58h+var_B18]
0x18001be49  call    ?ReadMuiString@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::ReadMuiString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001be4e  test    eax, eax
0x18001be50  jz      short loc_18001BE68
0x18001be52  lea     r8, [rsp+0B58h+var_AE0]
0x18001be57  lea     rdx, aName; "Name"
0x18001be5e  lea     rcx, [rsp+0B58h+var_B18]
0x18001be63  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001be68  cmp     [rsp+0B58h+var_AD0], r14
0x18001be70  jnz     loc_18001BF3B
0x18001be76  lea     r8, [rsp+0B58h+var_AE0]
0x18001be7b  lea     rdx, qword_18003D520
0x18001be82  lea     rcx, [rsp+0B58h+var_B18]
0x18001be87  call    ?ReadMuiString@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::ReadMuiString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001be8c  test    eax, eax
0x18001be8e  jz      short loc_18001BEA6
0x18001be90  lea     r8, [rsp+0B58h+var_AE0]
0x18001be95  lea     rdx, qword_18003D520
0x18001be9c  lea     rcx, [rsp+0B58h+var_B18]
0x18001bea1  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001bea6  cmp     [rsp+0B58h+var_AD0], r14
0x18001beae  jnz     loc_18001BF3B
0x18001beb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bebb  cmp     rcx, r15
0x18001bebe  jz      short loc_18001BEDB
0x18001bec0  test    byte ptr [rcx+1Ch], 4
0x18001bec4  jz      short loc_18001BEDB
0x18001bec6  mov     edx, 0Dh
0x18001becb  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001bed2  mov     rcx, [rcx+10h]
0x18001bed6  call    WPP_SF_
0x18001bedb  xorps   xmm0, xmm0
0x18001bede  xor     eax, eax
0x18001bee0  movups  xmmword ptr [rsp+0B58h+var_AB0], xmm0
0x18001bee8  movups  [rsp+0B58h+var_AA0], xmm0
0x18001bef0  mov     [rsp+0B58h+var_A90], rax
0x18001bef8  mov     r9d, [rbx+18h]
0x18001befc  lea     r8, aAuthoridD; "AuthorId: %d"
0x18001bf03  lea     edx, [rax+14h]; BufferCount
0x18001bf06  lea     rcx, [rsp+0B58h+var_AB0]; Buffer
0x18001bf0e  call    swprintf_s
0x18001bf13  lea     rax, [rsp+0B58h+var_AB0]
0x18001bf1b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001bf1f  inc     r8
0x18001bf22  cmp     [rax+r8*2], r14w
0x18001bf27  jnz     short loc_18001BF1F
0x18001bf29  lea     rdx, [rsp+0B58h+var_AB0]
0x18001bf31  lea     rcx, [rsp+0B58h+var_AE0]
0x18001bf36  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAAAEAV12@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::assign(wchar_t const * const,unsigned __int64)
0x18001bf3b  mov     r10, cs:WPP_GLOBAL_Control
0x18001bf42  cmp     r10, r15
0x18001bf45  jz      short loc_18001BF70
0x18001bf47  test    byte ptr [r10+1Ch], 4
0x18001bf4c  jz      short loc_18001BF70
0x18001bf4e  lea     rcx, [rsp+0B58h+var_AE0]
0x18001bf53  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001bf58  mov     r9, rax
0x18001bf5b  mov     edx, 0Eh
0x18001bf60  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001bf67  mov     rcx, [r10+10h]
0x18001bf6b  call    WPP_SF_S
0x18001bf70  xor     eax, eax
0x18001bf72  mov     [rsp+0B58h+var_ABF], ax
0x18001bf7a  mov     [rsp+0B58h+var_ABD], al
0x18001bf81  mov     [rsp+0B58h+var_ABC], rax
0x18001bf89  mov     eax, [rbx+18h]
0x18001bf8c  mov     [rsp+0B58h+var_AB4], eax
0x18001bf93  mov     al, [rbx+8]
0x18001bf96  mov     [rsp+0B58h+var_AC0], al
0x18001bf9d  cmp     al, 0FEh
0x18001bf9f  jnz     short loc_18001BFB5
0x18001bfa1  mov     eax, [rbx+0Ch]
0x18001bfa4  mov     dword ptr [rsp+0B58h+var_ABC], eax
0x18001bfab  mov     eax, [rbx+10h]
0x18001bfae  mov     dword ptr [rsp+0B58h+var_ABC+4], eax
0x18001bfb5  lea     r9, [rsp+0B58h+var_AE0]
0x18001bfba  lea     r8, [rsp+0B58h+var_AC0]
0x18001bfc2  lea     rdx, [rsp+0B58h+var_B08]
0x18001bfc7  mov     rcx, rdi
0x18001bfca  call    ?AddOneEapMethod@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@AEBU_EAP_METHOD_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; EapLm::BaseEapLibraryManager::AddOneEapMethod(RegistryKey const &,_EAP_METHOD_TYPE const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18001bfcf  nop
0x18001bfd0  jmp     short loc_18001BFD9
0x18001bfd2  jmp     short $+2
0x18001bfd4  mov     rdi, [rsp+0B58h+var_AF8]
0x18001bfd9  lea     rcx, [rsp+0B58h+var_AE0]
0x18001bfde  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001bfe3  jmp     short loc_18001C02B
0x18001bfe5  test    cs:Microsoft_Windows_EapHostEnableBits, 8
0x18001bfec  jz      short loc_18001BFFB
0x18001bfee  lea     r8, [rsp+0B58h+var_958]
0x18001bff6  call    McTemplateU0z_EtwEventWriteTransfer
0x18001bffb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c002  cmp     rcx, r15
0x18001c005  jz      short loc_18001C02B
0x18001c007  test    byte ptr [rcx+1Ch], 1
0x18001c00b  jz      short loc_18001C02B
0x18001c00d  mov     edx, 12h
0x18001c012  lea     r9, [rsp+0B58h+var_958]
0x18001c01a  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001c021  mov     rcx, [rcx+10h]
0x18001c025  call    WPP_SF_S
0x18001c02a  nop
0x18001c02b  lea     rcx, [rsp+0B58h+var_B18]; this
0x18001c030  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18001c035  mov     byte ptr [rdi+48h], 1
0x18001c039  lea     rcx, [rsp+0B58h+var_B08]; this
0x18001c03e  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18001c043  mov     rcx, [rsp+0B58h+var_28]
0x18001c04b  xor     rcx, rsp; StackCookie
0x18001c04e  call    __security_check_cookie
0x18001c053  lea     r11, [rsp+0B58h+var_18]
0x18001c05b  mov     rbx, [r11+30h]
0x18001c05f  mov     rsi, [r11+38h]
0x18001c063  mov     rsp, r11
0x18001c066  pop     r15
0x18001c068  pop     r14
0x18001c06a  pop     rdi
0x18001c06b  retn
```
