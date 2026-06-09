# EapLm::BaseEapLibraryManager::Initialize(EapHost::EapMethodType const &)

- ea: `0x18001b200`
- end: `0x18001b65c`
- name: `?Initialize@BaseEapLibraryManager@EapLm@@MEAAXAEBVEapMethodType@EapHost@@@Z`
- size: `1116`
- prototype: `void __fastcall(EapLm::BaseEapLibraryManager *__hidden this, const struct EapHost::EapMethodType *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180002a90`
- `0x18000343c`
- `0x18000349c`
- `0x180009dc4`
- `0x180009f70`
- `0x180010aa8`
- `0x1800118e8`
- `0x180011908`
- `0x18001a2f0`
- `0x18001a758`
- `0x18001b200`
- `0x18001c4f0`
- `0x18001c828`
- `0x18001c8b4`
- `0x1800300fc`
- `0x1800301fc`
- `0x18003044c`
- `0x180030564`

## string_xrefs

- `0x18001b29f`: `System\CurrentControlSet\Services\EapHost\Methods`
- `0x18001b3d8`: `System\CurrentControlSet\Services\EapHost\Methods`
- `0x18001b282`: `System\CurrentControlSet\Services\RasMan\PPP\EAP`

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
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // r10
  __int64 v17; // r8
  const EapHost::EapException *v18; // r15
  DWORD v19; // eax
  int v20; // ecx
  int v21; // r9d
  int v22; // ebx
  int v23; // edi
  unsigned __int8 v24; // si
  unsigned int v25; // r14d
  int v26; // eax
  __int64 v27; // r8
  const Exception *v28; // r15
  DWORD v29; // eax
  int v30; // ecx
  int v31; // r9d
  int v32; // ebx
  int v33; // edi
  unsigned __int8 v34; // si
  unsigned int v35; // r14d
  int v36; // eax
  __int64 v37; // r8
  __int64 v38; // [rsp+20h] [rbp-B38h]
  HKEY v39; // [rsp+40h] [rbp-B18h] BYREF
  int v40; // [rsp+48h] [rbp-B10h]
  HKEY v41; // [rsp+50h] [rbp-B08h] BYREF
  int v42; // [rsp+58h] [rbp-B00h]
  EapLm::BaseEapLibraryManager *v43; // [rsp+60h] [rbp-AF8h]
  const EapHost::EapException *v44; // [rsp+68h] [rbp-AF0h] BYREF
  const Exception *v45; // [rsp+70h] [rbp-AE8h] BYREF
  _BYTE v46[16]; // [rsp+78h] [rbp-AE0h] BYREF
  __int64 v47; // [rsp+88h] [rbp-AD0h]
  __int128 v48; // [rsp+98h] [rbp-AC0h] BYREF
  wchar_t v49[8]; // [rsp+A8h] [rbp-AB0h] BYREF
  __int128 v50; // [rsp+B8h] [rbp-AA0h]
  __int64 v51; // [rsp+C8h] [rbp-A90h]
  wchar_t Buffer[152]; // [rsp+D0h] [rbp-A88h] BYREF
  wchar_t v53[152]; // [rsp+200h] [rbp-958h] BYREF
  WCHAR v54[1024]; // [rsp+330h] [rbp-828h] BYREF

  v3 = this;
  v43 = this;
  memset_0(Buffer, 0, 0x12Cu);
  memset_0(v53, 0, 0x12Cu);
  v41 = 0;
  v42 = 1;
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
  v4 = RegistryKey::Open((__int64)&v41, HKEY_LOCAL_MACHINE, Buffer, 9);
  if ( v4 )
  {
    if ( (Microsoft_Windows_EapHostEnableBits & 8) != 0 )
    {
      LOBYTE(v8) = v4;
      McTemplateU0zc_EtwEventWriteTransfer(v6, v5, Buffer, v8);
    }
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, Buffer);
    }
  }
  else
  {
    v9 = *((_DWORD *)a2 + 6);
    if ( v9 )
    {
      v39 = 0;
      v40 = 1;
      LODWORD(v38) = v9;
      swprintf_s(v53, 0x96u, L"%ws\\%d", L"System\\CurrentControlSet\\Services\\EapHost\\Methods", v38);
      if ( (unsigned int)RegistryKey::Open((__int64)&v39, HKEY_LOCAL_MACHINE, v53, 9) )
      {
        if ( (Microsoft_Windows_EapHostEnableBits & 8) != 0 )
          McTemplateU0z_EtwEventWriteTransfer(v11, v10, v53);
        if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, v53);
        }
      }
      else
      {
        std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
          v46,
          v10,
          v12,
          v13);
        if ( (unsigned int)RegistryKey::ReadMuiString(&v39, L"Name", v46) )
          RegistryKey::QueryValue(&v39, L"Name", v46);
        if ( !v47 )
        {
          if ( (unsigned int)RegistryKey::ReadMuiString(&v39, &qword_18003C520, v46) )
            RegistryKey::QueryValue(&v39, &qword_18003C520, v46);
          if ( !v47 )
          {
            if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
            }
            *(_OWORD *)v49 = 0;
            v50 = 0;
            v51 = 0;
            swprintf_s(v49, 0x14u, L"AuthorId: %d", *((unsigned int *)a2 + 6));
            v14 = -1;
            do
              ++v14;
            while ( v49[v14] );
            std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::assign(v46, v49);
          }
        }
        if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v15 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
          WPP_SF_S(*(_QWORD *)(v16 + 16), 14, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, v15);
        }
        *(_WORD *)((char *)&v48 + 1) = 0;
        BYTE3(v48) = 0;
        *(_QWORD *)((char *)&v48 + 4) = 0;
        HIDWORD(v48) = *((_DWORD *)a2 + 6);
        LOBYTE(v48) = *((_BYTE *)a2 + 8);
        if ( (_BYTE)v48 == 0xFE )
          *(_QWORD *)((char *)&v48 + 4) = *(_QWORD *)((char *)a2 + 12);
        try
        {
          EapLm::BaseEapLibraryManager::AddOneEapMethod((__int64)v3, (__int64)&v41, &v48, (__int64)v46);
        }
        catch ( std::bad_alloc )
        {
          if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
            McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)OutOfMemory, v17, 1, (__int64)&v48);
          if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
          }
          throw;
        }
        catch ( const EapHost::EapException *v44 )
        {
          v18 = v44;
          v19 = (*(__int64 (__fastcall **)(const EapHost::EapException *))(*(_QWORD *)v44 + 16LL))(v44);
          FormatMessageW(0x1200u, 0, v19, 0, v54, 0x400u, 0);
          v22 = DWORD2(v48);
          v23 = DWORD1(v48);
          v24 = v48;
          v25 = HIDWORD(v48);
          if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
          {
            LOBYTE(v21) = v48;
            McTemplateU0quqqz_EtwEventWriteTransfer(
              v20,
              (unsigned int)EapExceptionEvent,
              HIDWORD(v48),
              v21,
              SBYTE4(v48),
              SBYTE8(v48),
              (__int64)v54);
          }
          if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v26 = (*(__int64 (__fastcall **)(const EapHost::EapException *))(*(_QWORD *)v18 + 16LL))(v18);
            WPP_SF_ddddD(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v27, v25, v24, v23, v22, v26);
          }
          v3 = v43;
        }
        catch ( const Exception *v45 )
        {
          v28 = v45;
          v29 = (*(__int64 (__fastcall **)(const Exception *))(*(_QWORD *)v45 + 16LL))(v45);
          FormatMessageW(0x1200u, 0, v29, 0, v54, 0x400u, 0);
          v32 = DWORD2(v48);
          v33 = DWORD1(v48);
          v34 = v48;
          v35 = HIDWORD(v48);
          if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
          {
            LOBYTE(v31) = v48;
            McTemplateU0quqqz_EtwEventWriteTransfer(
              v30,
              (unsigned int)ExceptionEvent,
              HIDWORD(v48),
              v31,
              SBYTE4(v48),
              SBYTE8(v48),
              (__int64)v54);
          }
          if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v36 = (*(__int64 (__fastcall **)(const Exception *))(*(_QWORD *)v28 + 16LL))(v28);
            WPP_SF_ddddD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v37, v35, v34, v33, v32, v36);
          }
          v3 = v43;
        }
        std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v46);
      }
      RegistryKey::Clear(&v39);
    }
    else
    {
      LOBYTE(v7) = *((_BYTE *)a2 + 8);
      EapLm::BaseEapLibraryManager::AddLegacyEapMethod(v3, (const struct RegistryKey *)&v41, v7, v8);
    }
    *((_BYTE *)v3 + 72) = 1;
  }
  RegistryKey::Clear(&v41);
}

```

## disassembly

```asm
0x18001b200  mov     [rsp+arg_10], rbx
0x18001b205  mov     [rsp+arg_18], rsi
0x18001b20a  push    rdi
0x18001b20b  push    r14
0x18001b20d  push    r15
0x18001b20f  sub     rsp, 0B40h
0x18001b216  mov     rax, cs:__security_cookie
0x18001b21d  xor     rax, rsp
0x18001b220  mov     [rsp+0B58h+var_28], rax
0x18001b228  mov     rbx, rdx
0x18001b22b  mov     rdi, rcx
0x18001b22e  mov     [rsp+0B58h+var_AF8], rcx
0x18001b233  mov     esi, 12Ch
0x18001b238  mov     r8d, esi; Size
0x18001b23b  xor     edx, edx; Val
0x18001b23d  lea     rcx, [rsp+0B58h+Buffer]; void *
0x18001b245  call    memset_0
0x18001b24a  mov     r8d, esi; Size
0x18001b24d  xor     edx, edx; Val
0x18001b24f  lea     rcx, [rsp+0B58h+var_958]; void *
0x18001b257  call    memset_0
0x18001b25c  xor     r14d, r14d
0x18001b25f  mov     [rsp+0B58h+var_B08], r14
0x18001b264  mov     [rsp+0B58h+var_B00], 1
0x18001b26c  mov     ecx, [rbx+18h]
0x18001b26f  mov     esi, 96h
0x18001b274  mov     edx, esi; BufferCount
0x18001b276  test    ecx, ecx
0x18001b278  jnz     short loc_18001B29F
0x18001b27a  movzx   eax, byte ptr [rbx+8]
0x18001b27e  mov     dword ptr [rsp+0B58h+var_B38], eax
0x18001b282  lea     r9, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Ra"...
0x18001b289  lea     r8, aWsD; "%ws\\%d"
0x18001b290  lea     rcx, [rsp+0B58h+Buffer]; Buffer
0x18001b298  call    swprintf_s
0x18001b29d  jmp     short loc_18001B2FC
0x18001b29f  lea     r9, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Ea"...
0x18001b2a6  cmp     byte ptr [rbx+8], 0FEh
0x18001b2aa  jnz     short loc_18001B2DC
0x18001b2ac  mov     eax, [rbx+10h]
0x18001b2af  mov     [rsp+0B58h+var_B20], eax
0x18001b2b3  mov     eax, [rbx+0Ch]
0x18001b2b6  mov     [rsp+0B58h+var_B28], eax
0x18001b2ba  mov     [rsp+0B58h+var_B30], 0FEh
0x18001b2c2  mov     dword ptr [rsp+0B58h+var_B38], ecx
0x18001b2c6  lea     r8, aWsDDDD; "%ws\\%d\\%d\\%d\\%d"
0x18001b2cd  lea     rcx, [rsp+0B58h+Buffer]; Buffer
0x18001b2d5  call    swprintf_s
0x18001b2da  jmp     short loc_18001B2FC
0x18001b2dc  movzx   eax, byte ptr [rbx+8]
0x18001b2e0  mov     [rsp+0B58h+var_B30], eax
0x18001b2e4  mov     dword ptr [rsp+0B58h+var_B38], ecx
0x18001b2e8  lea     r8, aWsDD; "%ws\\%d\\%d"
0x18001b2ef  lea     rcx, [rsp+0B58h+Buffer]; Buffer
0x18001b2f7  call    swprintf_s
0x18001b2fc  lea     r15, WPP_GLOBAL_Control
0x18001b303  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b30a  cmp     rcx, r15
0x18001b30d  jz      short loc_18001B332
0x18001b30f  test    byte ptr [rcx+1Ch], 4
0x18001b313  jz      short loc_18001B332
0x18001b315  mov     edx, 0Bh
0x18001b31a  lea     r9, [rsp+0B58h+Buffer]
0x18001b322  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001b329  mov     rcx, [rcx+10h]
0x18001b32d  call    WPP_SF_S
0x18001b332  mov     r9d, 9
0x18001b338  lea     r8, [rsp+0B58h+Buffer]
0x18001b340  mov     rdx, 0FFFFFFFF80000002h
0x18001b347  lea     rcx, [rsp+0B58h+var_B08]
0x18001b34c  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001b351  test    eax, eax
0x18001b353  jz      short loc_18001B3AA
0x18001b355  test    cs:Microsoft_Windows_EapHostEnableBits, 8
0x18001b35c  jz      short loc_18001B36E
0x18001b35e  mov     r9b, al
0x18001b361  lea     r8, [rsp+0B58h+Buffer]
0x18001b369  call    McTemplateU0zc_EtwEventWriteTransfer
0x18001b36e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b375  cmp     rcx, r15
0x18001b378  jz      loc_18001B629
0x18001b37e  test    byte ptr [rcx+1Ch], 1
0x18001b382  jz      loc_18001B629
0x18001b388  mov     edx, 0Ch
0x18001b38d  lea     r9, [rsp+0B58h+Buffer]
0x18001b395  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001b39c  mov     rcx, [rcx+10h]
0x18001b3a0  call    WPP_SF_S
0x18001b3a5  jmp     loc_18001B629
0x18001b3aa  mov     eax, [rbx+18h]
0x18001b3ad  test    eax, eax
0x18001b3af  jnz     short loc_18001B3C7
0x18001b3b1  mov     r8b, [rbx+8]; unsigned __int8
0x18001b3b5  lea     rdx, [rsp+0B58h+var_B08]; struct RegistryKey *
0x18001b3ba  mov     rcx, rdi; this
0x18001b3bd  call    ?AddLegacyEapMethod@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@E@Z; EapLm::BaseEapLibraryManager::AddLegacyEapMethod(RegistryKey const &,uchar)
0x18001b3c2  jmp     loc_18001B625
0x18001b3c7  mov     [rsp+0B58h+var_B18], r14
0x18001b3cc  mov     [rsp+0B58h+var_B10], 1
0x18001b3d4  mov     dword ptr [rsp+0B58h+var_B38], eax
0x18001b3d8  lea     r9, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Ea"...
0x18001b3df  lea     r8, aWsD; "%ws\\%d"
0x18001b3e6  mov     rdx, rsi; BufferCount
0x18001b3e9  lea     rcx, [rsp+0B58h+var_958]; Buffer
0x18001b3f1  call    swprintf_s
0x18001b3f6  mov     r9d, 9
0x18001b3fc  lea     r8, [rsp+0B58h+var_958]
0x18001b404  mov     rdx, 0FFFFFFFF80000002h
0x18001b40b  lea     rcx, [rsp+0B58h+var_B18]
0x18001b410  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001b415  test    eax, eax
0x18001b417  jnz     loc_18001B5D5
0x18001b41d  lea     rcx, [rsp+0B58h+var_AE0]
0x18001b422  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x18001b427  nop
0x18001b428  lea     r8, [rsp+0B58h+var_AE0]
0x18001b42d  lea     rdx, aName; "Name"
0x18001b434  lea     rcx, [rsp+0B58h+var_B18]
0x18001b439  call    ?ReadMuiString@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::ReadMuiString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001b43e  test    eax, eax
0x18001b440  jz      short loc_18001B458
0x18001b442  lea     r8, [rsp+0B58h+var_AE0]
0x18001b447  lea     rdx, aName; "Name"
0x18001b44e  lea     rcx, [rsp+0B58h+var_B18]
0x18001b453  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001b458  cmp     [rsp+0B58h+var_AD0], r14
0x18001b460  jnz     loc_18001B52B
0x18001b466  lea     r8, [rsp+0B58h+var_AE0]
0x18001b46b  lea     rdx, qword_18003C520
0x18001b472  lea     rcx, [rsp+0B58h+var_B18]
0x18001b477  call    ?ReadMuiString@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::ReadMuiString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001b47c  test    eax, eax
0x18001b47e  jz      short loc_18001B496
0x18001b480  lea     r8, [rsp+0B58h+var_AE0]
0x18001b485  lea     rdx, qword_18003C520
0x18001b48c  lea     rcx, [rsp+0B58h+var_B18]
0x18001b491  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001b496  cmp     [rsp+0B58h+var_AD0], r14
0x18001b49e  jnz     loc_18001B52B
0x18001b4a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b4ab  cmp     rcx, r15
0x18001b4ae  jz      short loc_18001B4CB
0x18001b4b0  test    byte ptr [rcx+1Ch], 4
0x18001b4b4  jz      short loc_18001B4CB
0x18001b4b6  mov     edx, 0Dh
0x18001b4bb  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001b4c2  mov     rcx, [rcx+10h]
0x18001b4c6  call    WPP_SF_
0x18001b4cb  xorps   xmm0, xmm0
0x18001b4ce  xor     eax, eax
0x18001b4d0  movups  xmmword ptr [rsp+0B58h+var_AB0], xmm0
0x18001b4d8  movups  [rsp+0B58h+var_AA0], xmm0
0x18001b4e0  mov     [rsp+0B58h+var_A90], rax
0x18001b4e8  mov     r9d, [rbx+18h]
0x18001b4ec  lea     r8, aAuthoridD; "AuthorId: %d"
0x18001b4f3  lea     edx, [rax+14h]; BufferCount
0x18001b4f6  lea     rcx, [rsp+0B58h+var_AB0]; Buffer
0x18001b4fe  call    swprintf_s
0x18001b503  lea     rax, [rsp+0B58h+var_AB0]
0x18001b50b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001b50f  inc     r8
0x18001b512  cmp     [rax+r8*2], r14w
0x18001b517  jnz     short loc_18001B50F
0x18001b519  lea     rdx, [rsp+0B58h+var_AB0]
0x18001b521  lea     rcx, [rsp+0B58h+var_AE0]
0x18001b526  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAAAEAV12@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::assign(wchar_t const * const,unsigned __int64)
0x18001b52b  mov     r10, cs:WPP_GLOBAL_Control
0x18001b532  cmp     r10, r15
0x18001b535  jz      short loc_18001B560
0x18001b537  test    byte ptr [r10+1Ch], 4
0x18001b53c  jz      short loc_18001B560
0x18001b53e  lea     rcx, [rsp+0B58h+var_AE0]
0x18001b543  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001b548  mov     r9, rax
0x18001b54b  mov     edx, 0Eh
0x18001b550  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001b557  mov     rcx, [r10+10h]
0x18001b55b  call    WPP_SF_S
0x18001b560  xor     eax, eax
0x18001b562  mov     [rsp+0B58h+var_ABF], ax
0x18001b56a  mov     [rsp+0B58h+var_ABD], al
0x18001b571  mov     [rsp+0B58h+var_ABC], rax
0x18001b579  mov     eax, [rbx+18h]
0x18001b57c  mov     [rsp+0B58h+var_AB4], eax
0x18001b583  mov     al, [rbx+8]
0x18001b586  mov     [rsp+0B58h+var_AC0], al
0x18001b58d  cmp     al, 0FEh
0x18001b58f  jnz     short loc_18001B5A5
0x18001b591  mov     eax, [rbx+0Ch]
0x18001b594  mov     dword ptr [rsp+0B58h+var_ABC], eax
0x18001b59b  mov     eax, [rbx+10h]
0x18001b59e  mov     dword ptr [rsp+0B58h+var_ABC+4], eax
0x18001b5a5  lea     r9, [rsp+0B58h+var_AE0]
0x18001b5aa  lea     r8, [rsp+0B58h+var_AC0]
0x18001b5b2  lea     rdx, [rsp+0B58h+var_B08]
0x18001b5b7  mov     rcx, rdi
0x18001b5ba  call    ?AddOneEapMethod@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@AEBU_EAP_METHOD_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; EapLm::BaseEapLibraryManager::AddOneEapMethod(RegistryKey const &,_EAP_METHOD_TYPE const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18001b5bf  nop
0x18001b5c0  jmp     short loc_18001B5C9
0x18001b5c2  jmp     short $+2
0x18001b5c4  mov     rdi, [rsp+0B58h+var_AF8]
0x18001b5c9  lea     rcx, [rsp+0B58h+var_AE0]
0x18001b5ce  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001b5d3  jmp     short loc_18001B61B
0x18001b5d5  test    cs:Microsoft_Windows_EapHostEnableBits, 8
0x18001b5dc  jz      short loc_18001B5EB
0x18001b5de  lea     r8, [rsp+0B58h+var_958]
0x18001b5e6  call    McTemplateU0z_EtwEventWriteTransfer
0x18001b5eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b5f2  cmp     rcx, r15
0x18001b5f5  jz      short loc_18001B61B
0x18001b5f7  test    byte ptr [rcx+1Ch], 1
0x18001b5fb  jz      short loc_18001B61B
0x18001b5fd  mov     edx, 12h
0x18001b602  lea     r9, [rsp+0B58h+var_958]
0x18001b60a  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001b611  mov     rcx, [rcx+10h]
0x18001b615  call    WPP_SF_S
0x18001b61a  nop
0x18001b61b  lea     rcx, [rsp+0B58h+var_B18]; this
0x18001b620  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18001b625  mov     byte ptr [rdi+48h], 1
0x18001b629  lea     rcx, [rsp+0B58h+var_B08]; this
0x18001b62e  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18001b633  mov     rcx, [rsp+0B58h+var_28]
0x18001b63b  xor     rcx, rsp; StackCookie
0x18001b63e  call    __security_check_cookie
0x18001b643  lea     r11, [rsp+0B58h+var_18]
0x18001b64b  mov     rbx, [r11+30h]
0x18001b64f  mov     rsi, [r11+38h]
0x18001b653  mov     rsp, r11
0x18001b656  pop     r15
0x18001b658  pop     r14
0x18001b65a  pop     rdi
0x18001b65b  retn
```
