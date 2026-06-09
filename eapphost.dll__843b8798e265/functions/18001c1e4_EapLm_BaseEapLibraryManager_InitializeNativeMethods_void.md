# EapLm::BaseEapLibraryManager::InitializeNativeMethods(void)

- ea: `0x18001c1e4`
- end: `0x18001c723`
- name: `?InitializeNativeMethods@BaseEapLibraryManager@EapLm@@AEAAXXZ`
- size: `1343`
- prototype: `void __fastcall(EapLm::BaseEapLibraryManager *__hidden this)`
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b67c`
- `0x18001c080`

## callees

- `0x180002af0`
- `0x18000352c`
- `0x18000a21c`
- `0x18000a3e4`
- `0x180011218`
- `0x18001204c`
- `0x18001206c`
- `0x180017e48`
- `0x18001a1c0`
- `0x18001a6d4`
- `0x18001a99c`
- `0x18001b14c`
- `0x18001c1e4`
- `0x18001cf5c`
- `0x18001d298`
- `0x18001d328`
- `0x18001d3d0`
- `0x18001d490`
- `0x180031314`
- `0x180031424`
- `0x18003165c`
- `0x180031778`
- `0x180031930`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001c3dc`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001c5df`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001c3dc`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001c5df`

## string_xrefs

- `0x18001c258`: `System\CurrentControlSet\Services\EapHost\Methods`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall EapLm::BaseEapLibraryManager::InitializeNativeMethods(EapLm::BaseEapLibraryManager *this)
{
  EapLm::BaseEapLibraryManager *v1; // r15
  int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r9
  __int64 v6; // rbx
  __int64 v7; // rbx
  const WCHAR *v8; // rax
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // r10
  __int64 v17; // rdi
  const WCHAR *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // r10
  __int64 v25; // r8
  __int64 v26; // r8
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // r10
  const EapHost::EapException *v32; // r15
  DWORD v33; // eax
  int v34; // ecx
  int v35; // r9d
  int v36; // ebx
  int v37; // edi
  unsigned __int8 v38; // si
  unsigned int v39; // r14d
  int v40; // eax
  __int64 v41; // r8
  const Exception *v42; // r15
  DWORD v43; // eax
  int v44; // ecx
  int v45; // r9d
  int v46; // ebx
  int v47; // edi
  unsigned __int8 v48; // si
  unsigned int v49; // r14d
  int v50; // eax
  __int64 v51; // r8
  unsigned __int8 v52; // [rsp+40h] [rbp-908h] BYREF
  __int16 v53; // [rsp+41h] [rbp-907h]
  char v54; // [rsp+43h] [rbp-905h]
  __int64 v55; // [rsp+44h] [rbp-904h]
  unsigned int v56; // [rsp+4Ch] [rbp-8FCh]
  HKEY v57; // [rsp+50h] [rbp-8F8h] BYREF
  int v58; // [rsp+58h] [rbp-8F0h]
  __int64 v59; // [rsp+60h] [rbp-8E8h]
  __int64 v60; // [rsp+68h] [rbp-8E0h]
  EapLm::BaseEapLibraryManager *v61; // [rsp+70h] [rbp-8D8h]
  HKEY v62; // [rsp+78h] [rbp-8D0h] BYREF
  int v63; // [rsp+80h] [rbp-8C8h]
  __int64 v64; // [rsp+88h] [rbp-8C0h] BYREF
  __int64 v65; // [rsp+90h] [rbp-8B8h]
  __int64 v66; // [rsp+98h] [rbp-8B0h]
  __int64 v67; // [rsp+A0h] [rbp-8A8h] BYREF
  __int64 v68; // [rsp+A8h] [rbp-8A0h]
  __int64 v69; // [rsp+B0h] [rbp-898h]
  const EapHost::EapException *v70; // [rsp+B8h] [rbp-890h] BYREF
  const Exception *v71; // [rsp+C0h] [rbp-888h] BYREF
  _BYTE v72[16]; // [rsp+C8h] [rbp-880h] BYREF
  __int64 v73; // [rsp+D8h] [rbp-870h]
  __int64 v74; // [rsp+E8h] [rbp-860h] BYREF
  int v75; // [rsp+F0h] [rbp-858h]
  wchar_t Buffer[8]; // [rsp+F8h] [rbp-850h] BYREF
  __int128 v77; // [rsp+108h] [rbp-840h]
  __int64 v78; // [rsp+118h] [rbp-830h]
  WCHAR v79[1024]; // [rsp+120h] [rbp-828h] BYREF

  v1 = this;
  v61 = this;
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
  }
  v62 = 0;
  v63 = 1;
  v2 = RegistryKey::Open(
         (RegistryKey *)&v62,
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\EapHost\\Methods",
         9);
  if ( v2 )
  {
    if ( (Microsoft_Windows_EapHostEnableBits & 8) != 0 )
    {
      LOBYTE(v5) = v2;
      McTemplateU0zc_EtwEventWriteTransfer(v4, v3, L"System\\CurrentControlSet\\Services\\EapHost\\Methods", v5);
    }
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
        L"System\\CurrentControlSet\\Services\\EapHost\\Methods");
    }
  }
  else
  {
    std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(&v67);
    RegistryKey::SubKeys(&v62, &v67);
    v6 = v67;
    v60 = v67;
    while ( v6 != v68 )
    {
      v57 = 0;
      v58 = 1;
      v8 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v6);
      if ( (unsigned int)RegistryKey::Open((RegistryKey *)&v57, v62, v8, 9) )
      {
        if ( (Microsoft_Windows_EapHostEnableBits & 8) != 0 )
        {
          v27 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v6);
          McTemplateU0z_EtwEventWriteTransfer(v29, v28, v27);
        }
        if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v30 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v6);
          WPP_SF_S(*(_QWORD *)(v31 + 16), 41, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, v30);
        }
      }
      else
      {
        std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(&v64);
        RegistryKey::SubKeys(&v57, &v64);
        v9 = v64;
        v59 = v64;
        v52 = 0;
        v53 = 0;
        v54 = 0;
        v55 = 0;
        v10 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v6);
        v56 = _o__wtol(v10);
        std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
          v72,
          v11,
          v12,
          v13);
        if ( (unsigned int)RegistryKey::ReadMuiString(&v57, L"Name", v72) )
          RegistryKey::QueryValue(&v57, L"Name", v72);
        if ( !v73 )
        {
          if ( (unsigned int)RegistryKey::ReadMuiString(&v57, &qword_18003D520, v72) )
            RegistryKey::QueryValue(&v57, &qword_18003D520, v72);
          if ( !v73 )
          {
            if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
            }
            *(_OWORD *)Buffer = 0;
            v77 = 0;
            v78 = 0;
            swprintf_s(Buffer, 0x14u, L"AuthorId: %d", v56);
            v14 = -1;
            do
              ++v14;
            while ( Buffer[v14] );
            std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::assign(v72, Buffer);
          }
        }
        if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v15 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v72);
          WPP_SF_S(*(_QWORD *)(v16 + 16), 36, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, v15);
        }
        while ( v9 != v65 )
        {
          v74 = 0;
          v75 = 1;
          v18 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v9);
          try
          {
            if ( (unsigned int)RegistryKey::Open((RegistryKey *)&v74, v57, v18, 9) )
            {
              if ( (Microsoft_Windows_EapHostEnableBits & 8) != 0 )
              {
                std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v6);
                v20 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v9);
                McTemplateU0zz_EtwEventWriteTransfer(v22, v21, v20);
              }
              if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v9);
                v23 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v6);
                WPP_SF_SS(
                  *(_QWORD *)(v24 + 16),
                  37,
                  (unsigned int)WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
                  v23,
                  v25);
              }
            }
            else
            {
              v19 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v9);
              v52 = _o__wtol(v19);
              if ( v52 == 0xFE )
                EapLm::BaseEapLibraryManager::AddExpandedEapMethods(v1, &v74, v56, v72);
              else
                EapLm::BaseEapLibraryManager::AddOneEapMethod(v1, &v74, &v52, v72);
            }
            RegistryKey::Clear((RegistryKey *)&v74);
          }
          catch ( std::bad_alloc )
          {
            if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
              McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)OutOfMemory, v26, 1, (__int64)&v74);
            if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
            }
            throw;
          }
          catch ( const EapHost::EapException *v70 )
          {
            v32 = v70;
            v33 = (*(__int64 (__fastcall **)(const EapHost::EapException *))(*(_QWORD *)v70 + 16LL))(v70);
            FormatMessageW(0x1200u, 0, v33, 0, v79, 0x400u, 0);
            v36 = HIDWORD(v55);
            v37 = v55;
            v38 = v52;
            v39 = v56;
            if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
            {
              LOBYTE(v35) = v52;
              McTemplateU0quqqz_EtwEventWriteTransfer(
                v34,
                (unsigned int)EapExceptionEvent,
                v56,
                v35,
                v55,
                SBYTE4(v55),
                (__int64)v79);
            }
            if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v40 = (*(__int64 (__fastcall **)(const EapHost::EapException *))(*(_QWORD *)v32 + 16LL))(v32);
              WPP_SF_ddddD(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, v41, v39, v38, v37, v36, v40);
            }
            v1 = v61;
            v9 = v59;
            v6 = v60;
          }
          catch ( const Exception *v71 )
          {
            v42 = v71;
            v43 = (*(__int64 (__fastcall **)(const Exception *))(*(_QWORD *)v71 + 16LL))(v71);
            FormatMessageW(0x1200u, 0, v43, 0, v79, 0x400u, 0);
            v46 = HIDWORD(v55);
            v47 = v55;
            v48 = v52;
            v49 = v56;
            if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
            {
              LOBYTE(v45) = v52;
              McTemplateU0quqqz_EtwEventWriteTransfer(
                v44,
                (unsigned int)ExceptionEvent,
                v56,
                v45,
                v55,
                SBYTE4(v55),
                (__int64)v79);
            }
            if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v50 = (*(__int64 (__fastcall **)(const Exception *))(*(_QWORD *)v42 + 16LL))(v42);
              WPP_SF_ddddD(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, v51, v49, v48, v47, v46, v50);
            }
            v1 = v61;
            v9 = v59;
            v6 = v60;
          }
          v9 += 32;
          v59 = v9;
        }
        std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v72);
        v17 = v64;
        if ( v64 )
        {
          std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(
            v64,
            v65);
          std::_Deallocate<16>(v17, (v66 - v17) & 0xFFFFFFFFFFFFFFE0uLL);
        }
      }
      v6 += 32;
      v60 = v6;
      RegistryKey::Clear((RegistryKey *)&v57);
    }
    v7 = v67;
    if ( v67 )
    {
      std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(
        v67,
        v68);
      std::_Deallocate<16>(v7, (v69 - v7) & 0xFFFFFFFFFFFFFFE0uLL);
    }
  }
  RegistryKey::Clear((RegistryKey *)&v62);
}

```

## disassembly

```asm
0x18001c1e4  mov     [rsp+arg_8], rbx
0x18001c1e9  mov     [rsp+arg_10], rsi
0x18001c1ee  push    rdi
0x18001c1ef  push    r14
0x18001c1f1  push    r15
0x18001c1f3  sub     rsp, 930h
0x18001c1fa  mov     rax, cs:__security_cookie
0x18001c201  xor     rax, rsp
0x18001c204  mov     [rsp+948h+var_28], rax
0x18001c20c  mov     r15, rcx
0x18001c20f  mov     [rsp+948h+var_8D8], rcx
0x18001c214  lea     r14, WPP_GLOBAL_Control
0x18001c21b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c222  cmp     rcx, r14
0x18001c225  jz      short loc_18001C242
0x18001c227  test    byte ptr [rcx+1Ch], 4
0x18001c22b  jz      short loc_18001C242
0x18001c22d  mov     edx, 21h ; '!'
0x18001c232  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001c239  mov     rcx, [rcx+10h]
0x18001c23d  call    WPP_SF_
0x18001c242  xor     esi, esi
0x18001c244  mov     [rsp+948h+var_8D0], rsi
0x18001c249  mov     [rsp+948h+var_8C8], 1
0x18001c254  lea     r9d, [rsi+9]
0x18001c258  lea     rbx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Ea"...
0x18001c25f  mov     r8, rbx
0x18001c262  mov     rdx, 0FFFFFFFF80000002h
0x18001c269  lea     rcx, [rsp+948h+var_8D0]
0x18001c26e  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001c273  test    eax, eax
0x18001c275  jz      short loc_18001C2BF
0x18001c277  test    cs:Microsoft_Windows_EapHostEnableBits, 8
0x18001c27e  jz      short loc_18001C28B
0x18001c280  mov     r9b, al
0x18001c283  mov     r8, rbx
0x18001c286  call    McTemplateU0zc_EtwEventWriteTransfer
0x18001c28b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c292  cmp     rcx, r14
0x18001c295  jz      loc_18001C326
0x18001c29b  test    byte ptr [rcx+1Ch], 1
0x18001c29f  jz      loc_18001C326
0x18001c2a5  mov     edx, 22h ; '"'
0x18001c2aa  mov     r9, rbx
0x18001c2ad  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001c2b4  mov     rcx, [rcx+10h]
0x18001c2b8  call    WPP_SF_S
0x18001c2bd  jmp     short loc_18001C326
0x18001c2bf  lea     rcx, [rsp+948h+var_8A8]
0x18001c2c7  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(void)
0x18001c2cc  nop
0x18001c2cd  lea     rdx, [rsp+948h+var_8A8]
0x18001c2d5  lea     rcx, [rsp+948h+var_8D0]
0x18001c2da  call    ?SubKeys@RegistryKey@@QEBAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@@Z; RegistryKey::SubKeys(std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18001c2df  mov     rbx, [rsp+948h+var_8A8]
0x18001c2e7  mov     [rsp+948h+var_8E0], rbx
0x18001c2ec  mov     rdx, [rsp+948h+var_8A0]
0x18001c2f4  cmp     rbx, rdx
0x18001c2f7  jnz     short loc_18001C35A
0x18001c2f9  mov     rbx, [rsp+948h+var_8A8]
0x18001c301  test    rbx, rbx
0x18001c304  jz      short loc_18001C326
0x18001c306  mov     rcx, rbx
0x18001c309  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> * const,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18001c30e  mov     rdx, [rsp+948h+var_898]
0x18001c316  sub     rdx, rbx
0x18001c319  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18001c31d  mov     rcx, rbx
0x18001c320  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001c325  nop
0x18001c326  lea     rcx, [rsp+948h+var_8D0]; this
0x18001c32b  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18001c330  mov     rcx, [rsp+948h+var_28]
0x18001c338  xor     rcx, rsp; StackCookie
0x18001c33b  call    __security_check_cookie
0x18001c340  lea     r11, [rsp+948h+var_18]
0x18001c348  mov     rbx, [r11+28h]
0x18001c34c  mov     rsi, [r11+30h]
0x18001c350  mov     rsp, r11
0x18001c353  pop     r15
0x18001c355  pop     r14
0x18001c357  pop     rdi
0x18001c358  retn
0x18001c35a  mov     [rsp+948h+var_8F8], rsi
0x18001c35f  mov     [rsp+948h+var_8F0], 1
0x18001c367  mov     rcx, rbx
0x18001c36a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001c36f  mov     r9d, 9
0x18001c375  mov     r8, rax
0x18001c378  mov     rdx, [rsp+948h+var_8D0]
0x18001c37d  lea     rcx, [rsp+948h+var_8F8]
0x18001c382  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001c387  test    eax, eax
0x18001c389  jnz     loc_18001C6BE
0x18001c38f  lea     rcx, [rsp+948h+var_8C0]
0x18001c397  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(void)
0x18001c39c  nop
0x18001c39d  lea     rdx, [rsp+948h+var_8C0]
0x18001c3a5  lea     rcx, [rsp+948h+var_8F8]
0x18001c3aa  call    ?SubKeys@RegistryKey@@QEBAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@@Z; RegistryKey::SubKeys(std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18001c3af  mov     rdi, [rsp+948h+var_8C0]
0x18001c3b7  mov     [rsp+948h+var_8E8], rdi
0x18001c3bc  mov     [rsp+948h+var_908], sil
0x18001c3c1  xor     eax, eax
0x18001c3c3  mov     [rsp+948h+var_907], ax
0x18001c3c8  mov     [rsp+948h+var_905], al
0x18001c3cc  mov     [rsp+948h+var_904], rax
0x18001c3d1  mov     rcx, rbx
0x18001c3d4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001c3d9  mov     rcx, rax
0x18001c3dc  call    cs:__imp__o__wtol
0x18001c3e3  nop     dword ptr [rax+rax+00h]
0x18001c3e8  mov     [rsp+948h+var_8FC], eax
0x18001c3ec  lea     rcx, [rsp+948h+var_880]
0x18001c3f4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x18001c3f9  nop
0x18001c3fa  lea     r8, [rsp+948h+var_880]
0x18001c402  lea     rdx, aName; "Name"
0x18001c409  lea     rcx, [rsp+948h+var_8F8]
0x18001c40e  call    ?ReadMuiString@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::ReadMuiString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001c413  test    eax, eax
0x18001c415  jz      short loc_18001C430
0x18001c417  lea     r8, [rsp+948h+var_880]
0x18001c41f  lea     rdx, aName; "Name"
0x18001c426  lea     rcx, [rsp+948h+var_8F8]
0x18001c42b  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001c430  cmp     [rsp+948h+var_870], rsi
0x18001c438  jnz     loc_18001C50D
0x18001c43e  lea     r8, [rsp+948h+var_880]
0x18001c446  lea     rdx, qword_18003D520
0x18001c44d  lea     rcx, [rsp+948h+var_8F8]
0x18001c452  call    ?ReadMuiString@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::ReadMuiString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001c457  test    eax, eax
0x18001c459  jz      short loc_18001C474
0x18001c45b  lea     r8, [rsp+948h+var_880]
0x18001c463  lea     rdx, qword_18003D520
0x18001c46a  lea     rcx, [rsp+948h+var_8F8]
0x18001c46f  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001c474  cmp     [rsp+948h+var_870], rsi
0x18001c47c  jnz     loc_18001C50D
0x18001c482  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c489  cmp     rcx, r14
0x18001c48c  jz      short loc_18001C4A9
0x18001c48e  test    byte ptr [rcx+1Ch], 4
0x18001c492  jz      short loc_18001C4A9
0x18001c494  mov     edx, 23h ; '#'
0x18001c499  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001c4a0  mov     rcx, [rcx+10h]
0x18001c4a4  call    WPP_SF_
0x18001c4a9  xorps   xmm0, xmm0
0x18001c4ac  xor     eax, eax
0x18001c4ae  movups  xmmword ptr [rsp+948h+Buffer], xmm0
0x18001c4b6  movups  [rsp+948h+var_840], xmm0
0x18001c4be  mov     [rsp+948h+var_830], rax
0x18001c4c6  mov     r9d, [rsp+948h+var_8FC]
0x18001c4cb  lea     r8, aAuthoridD; "AuthorId: %d"
0x18001c4d2  lea     edx, [rax+14h]; BufferCount
0x18001c4d5  lea     rcx, [rsp+948h+Buffer]; Buffer
0x18001c4dd  call    swprintf_s
0x18001c4e2  lea     rax, [rsp+948h+Buffer]
0x18001c4ea  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001c4ee  inc     r8
0x18001c4f1  cmp     [rax+r8*2], si
0x18001c4f6  jnz     short loc_18001C4EE
0x18001c4f8  lea     rdx, [rsp+948h+Buffer]
0x18001c500  lea     rcx, [rsp+948h+var_880]
0x18001c508  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAAAEAV12@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::assign(wchar_t const * const,unsigned __int64)
0x18001c50d  mov     r10, cs:WPP_GLOBAL_Control
0x18001c514  cmp     r10, r14
0x18001c517  jz      short loc_18001C545
0x18001c519  test    byte ptr [r10+1Ch], 4
0x18001c51e  jz      short loc_18001C545
0x18001c520  lea     rcx, [rsp+948h+var_880]
0x18001c528  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001c52d  mov     r9, rax
0x18001c530  mov     edx, 24h ; '$'
0x18001c535  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001c53c  mov     rcx, [r10+10h]
0x18001c540  call    WPP_SF_S
0x18001c545  cmp     rdi, [rsp+948h+var_8B8]
0x18001c54d  jnz     short loc_18001C59A
0x18001c54f  lea     rcx, [rsp+948h+var_880]
0x18001c557  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001c55c  nop
0x18001c55d  mov     rdi, [rsp+948h+var_8C0]
0x18001c565  test    rdi, rdi
0x18001c568  jz      loc_18001C70A
0x18001c56e  mov     rdx, [rsp+948h+var_8B8]
0x18001c576  mov     rcx, rdi
0x18001c579  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> * const,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18001c57e  mov     rdx, [rsp+948h+var_8B0]
0x18001c586  sub     rdx, rdi
0x18001c589  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18001c58d  mov     rcx, rdi
0x18001c590  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001c595  jmp     loc_18001C70A
0x18001c59a  mov     [rsp+948h+var_860], rsi
0x18001c5a2  mov     [rsp+948h+var_858], 1
0x18001c5ad  mov     rcx, rdi
0x18001c5b0  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001c5b5  mov     r9d, 9
0x18001c5bb  mov     r8, rax
0x18001c5be  mov     rdx, [rsp+948h+var_8F8]
0x18001c5c3  lea     rcx, [rsp+948h+var_860]
0x18001c5cb  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001c5d0  test    eax, eax
0x18001c5d2  jnz     short loc_18001C61E
0x18001c5d4  mov     rcx, rdi
0x18001c5d7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001c5dc  mov     rcx, rax
0x18001c5df  call    cs:__imp__o__wtol
0x18001c5e6  nop     dword ptr [rax+rax+00h]
0x18001c5eb  mov     [rsp+948h+var_908], al
0x18001c5ef  lea     r9, [rsp+948h+var_880]
0x18001c5f7  lea     rdx, [rsp+948h+var_860]
0x18001c5ff  mov     rcx, r15
0x18001c602  cmp     al, 0FEh
0x18001c604  jnz     short loc_18001C612
0x18001c606  mov     r8d, [rsp+948h+var_8FC]
0x18001c60b  call    ?AddExpandedEapMethods@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; EapLm::BaseEapLibraryManager::AddExpandedEapMethods(RegistryKey const &,ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18001c610  jmp     short loc_18001C61C
0x18001c612  lea     r8, [rsp+948h+var_908]
0x18001c617  call    ?AddOneEapMethod@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@AEBU_EAP_METHOD_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; EapLm::BaseEapLibraryManager::AddOneEapMethod(RegistryKey const &,_EAP_METHOD_TYPE const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18001c61c  jmp     short loc_18001C686
0x18001c61e  test    cs:Microsoft_Windows_EapHostEnableBits, 8
0x18001c625  jz      short loc_18001C642
0x18001c627  mov     rcx, rbx
0x18001c62a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001c62f  mov     r9, rax
0x18001c632  mov     rcx, rdi
0x18001c635  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001c63a  mov     r8, rax
0x18001c63d  call    McTemplateU0zz_EtwEventWriteTransfer
0x18001c642  mov     r10, cs:WPP_GLOBAL_Control
0x18001c649  cmp     r10, r14
0x18001c64c  jz      short loc_18001C686
0x18001c64e  test    byte ptr [r10+1Ch], 1
0x18001c653  jz      short loc_18001C686
0x18001c655  mov     rcx, rdi
0x18001c658  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001c65d  mov     r8, rax
0x18001c660  mov     rcx, rbx
0x18001c663  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001c668  mov     edx, 25h ; '%'
0x18001c66d  mov     [rsp+948h+var_928], r8
0x18001c672  mov     r9, rax
0x18001c675  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001c67c  mov     rcx, [r10+10h]
0x18001c680  call    WPP_SF_SS
0x18001c685  nop
0x18001c686  lea     rcx, [rsp+948h+var_860]; this
0x18001c68e  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18001c693  nop
0x18001c694  jmp     short loc_18001C6B0
0x18001c696  jmp     short $+2
0x18001c698  mov     r15, [rsp+948h+var_8D8]
0x18001c69d  mov     rdi, [rsp+948h+var_8E8]
0x18001c6a2  mov     rbx, [rsp+948h+var_8E0]
0x18001c6a7  xor     esi, esi
0x18001c6a9  lea     r14, WPP_GLOBAL_Control
0x18001c6b0  add     rdi, 20h ; ' '
0x18001c6b4  mov     [rsp+948h+var_8E8], rdi
0x18001c6b9  jmp     loc_18001C545
0x18001c6be  test    cs:Microsoft_Windows_EapHostEnableBits, 8
0x18001c6c5  jz      short loc_18001C6D7
0x18001c6c7  mov     rcx, rbx
0x18001c6ca  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001c6cf  mov     r8, rax
0x18001c6d2  call    McTemplateU0z_EtwEventWriteTransfer
0x18001c6d7  mov     r10, cs:WPP_GLOBAL_Control
0x18001c6de  cmp     r10, r14
0x18001c6e1  jz      short loc_18001C70A
0x18001c6e3  test    byte ptr [r10+1Ch], 1
0x18001c6e8  jz      short loc_18001C70A
0x18001c6ea  mov     rcx, rbx
0x18001c6ed  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001c6f2  mov     edx, 29h ; ')'
0x18001c6f7  mov     r9, rax
0x18001c6fa  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001c701  mov     rcx, [r10+10h]
0x18001c705  call    WPP_SF_S
0x18001c70a  add     rbx, 20h ; ' '
0x18001c70e  mov     [rsp+948h+var_8E0], rbx
0x18001c713  lea     rcx, [rsp+948h+var_8F8]; this
0x18001c718  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18001c71d  jmp     loc_18001C2EC
```
