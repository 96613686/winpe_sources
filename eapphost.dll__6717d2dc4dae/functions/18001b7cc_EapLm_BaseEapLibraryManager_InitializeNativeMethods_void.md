# EapLm::BaseEapLibraryManager::InitializeNativeMethods(void)

- ea: `0x18001b7cc`
- end: `0x18001bcfe`
- name: `?InitializeNativeMethods@BaseEapLibraryManager@EapLm@@AEAAXXZ`
- size: `1330`
- prototype: `void __fastcall(EapLm::BaseEapLibraryManager *__hidden this)`
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001ac7c`
- `0x18001b670`

## callees

- `0x180002a90`
- `0x18000349c`
- `0x180009dc4`
- `0x180009f70`
- `0x180010aa8`
- `0x1800118e8`
- `0x180011908`
- `0x18001755c`
- `0x1800197d8`
- `0x180019cf0`
- `0x180019fbc`
- `0x18001a758`
- `0x18001b7cc`
- `0x18001c4f0`
- `0x18001c828`
- `0x18001c8b4`
- `0x18001c95c`
- `0x18001ca1c`
- `0x1800300fc`
- `0x1800301fc`
- `0x18003044c`
- `0x180030564`
- `0x180030784`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001b9c3`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001bbc0`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001b9c3`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001bbc0`

## string_xrefs

- `0x18001b840`: `System\CurrentControlSet\Services\EapHost\Methods`

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
  __int64 v6; // r8
  __int64 v7; // r9
  _QWORD *v8; // rbx
  _QWORD *v9; // rbx
  const WCHAR *v10; // rax
  _QWORD *v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // r10
  __int64 v19; // r8
  __int64 v20; // r9
  _QWORD *v21; // rdi
  const WCHAR *v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // r10
  __int64 v29; // r8
  __int64 v30; // r8
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // r10
  const EapHost::EapException *v36; // r15
  DWORD v37; // eax
  int v38; // ecx
  int v39; // r9d
  int v40; // ebx
  int v41; // edi
  unsigned __int8 v42; // si
  unsigned int v43; // r14d
  int v44; // eax
  __int64 v45; // r8
  const Exception *v46; // r15
  DWORD v47; // eax
  int v48; // ecx
  int v49; // r9d
  int v50; // ebx
  int v51; // edi
  unsigned __int8 v52; // si
  unsigned int v53; // r14d
  int v54; // eax
  __int64 v55; // r8
  __int128 v56; // [rsp+40h] [rbp-908h] BYREF
  HKEY v57; // [rsp+50h] [rbp-8F8h] BYREF
  int v58; // [rsp+58h] [rbp-8F0h]
  _QWORD *v59; // [rsp+60h] [rbp-8E8h]
  _QWORD *v60; // [rsp+68h] [rbp-8E0h]
  EapLm::BaseEapLibraryManager *v61; // [rsp+70h] [rbp-8D8h]
  HKEY v62; // [rsp+78h] [rbp-8D0h] BYREF
  int v63; // [rsp+80h] [rbp-8C8h]
  _QWORD *v64; // [rsp+88h] [rbp-8C0h] BYREF
  _QWORD *v65; // [rsp+90h] [rbp-8B8h]
  __int64 v66; // [rsp+98h] [rbp-8B0h]
  _QWORD *v67; // [rsp+A0h] [rbp-8A8h] BYREF
  _QWORD *v68; // [rsp+A8h] [rbp-8A0h]
  __int64 v69; // [rsp+B0h] [rbp-898h]
  const EapHost::EapException *v70; // [rsp+B8h] [rbp-890h] BYREF
  const Exception *v71; // [rsp+C0h] [rbp-888h] BYREF
  _BYTE v72[16]; // [rsp+C8h] [rbp-880h] BYREF
  __int64 v73; // [rsp+D8h] [rbp-870h]
  HKEY v74; // [rsp+E8h] [rbp-860h] BYREF
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
  v2 = RegistryKey::Open((__int64)&v62, HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\EapHost\\Methods", 9);
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
    v8 = v67;
    v60 = v67;
    while ( v8 != v68 )
    {
      v57 = 0;
      v58 = 1;
      v10 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      if ( (unsigned int)RegistryKey::Open((__int64)&v57, v62, v10, 9) )
      {
        if ( (Microsoft_Windows_EapHostEnableBits & 8) != 0 )
        {
          v31 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
          McTemplateU0z_EtwEventWriteTransfer(v33, v32, v31);
        }
        if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v34 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
          WPP_SF_S(*(_QWORD *)(v35 + 16), 41, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, v34);
        }
      }
      else
      {
        std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(&v64);
        RegistryKey::SubKeys(&v57, &v64);
        v11 = v64;
        v59 = v64;
        LOBYTE(v56) = 0;
        *(_WORD *)((char *)&v56 + 1) = 0;
        BYTE3(v56) = 0;
        *(_QWORD *)((char *)&v56 + 4) = 0;
        v12 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
        HIDWORD(v56) = _o__wtol(v12);
        std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
          v72,
          v13,
          v14,
          v15);
        if ( (unsigned int)RegistryKey::ReadMuiString(&v57, L"Name", v72) )
          RegistryKey::QueryValue(&v57, L"Name", v72);
        if ( !v73 )
        {
          if ( (unsigned int)RegistryKey::ReadMuiString(&v57, &qword_18003C520, v72) )
            RegistryKey::QueryValue(&v57, &qword_18003C520, v72);
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
            swprintf_s(Buffer, 0x14u, L"AuthorId: %d", HIDWORD(v56));
            v16 = -1;
            do
              ++v16;
            while ( Buffer[v16] );
            std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::assign(v72, Buffer);
          }
        }
        if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v17 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
          WPP_SF_S(*(_QWORD *)(v18 + 16), 36, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, v17);
        }
        while ( v11 != v65 )
        {
          v74 = 0;
          v75 = 1;
          v22 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
          try
          {
            if ( (unsigned int)RegistryKey::Open((__int64)&v74, v57, v22, 9) )
            {
              if ( (Microsoft_Windows_EapHostEnableBits & 8) != 0 )
              {
                std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
                v24 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
                McTemplateU0zz_EtwEventWriteTransfer(v26, v25, v24);
              }
              if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
                v27 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
                WPP_SF_SS(
                  *(_QWORD *)(v28 + 16),
                  37,
                  (unsigned int)WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
                  v27,
                  v29);
              }
            }
            else
            {
              v23 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
              LOBYTE(v56) = _o__wtol(v23);
              if ( (_BYTE)v56 == 0xFE )
                EapLm::BaseEapLibraryManager::AddExpandedEapMethods((__int64)v1, &v74, HIDWORD(v56), (__int64)v72);
              else
                EapLm::BaseEapLibraryManager::AddOneEapMethod((__int64)v1, (__int64)&v74, &v56, (__int64)v72);
            }
            RegistryKey::Clear(&v74);
          }
          catch ( std::bad_alloc )
          {
            if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
              McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)OutOfMemory, v30, 1, (__int64)&v74);
            if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
            }
            throw;
          }
          catch ( const EapHost::EapException *v70 )
          {
            v36 = v70;
            v37 = (*(__int64 (__fastcall **)(const EapHost::EapException *))(*(_QWORD *)v70 + 16LL))(v70);
            FormatMessageW(0x1200u, 0, v37, 0, v79, 0x400u, 0);
            v40 = DWORD2(v56);
            v41 = DWORD1(v56);
            v42 = v56;
            v43 = HIDWORD(v56);
            if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
            {
              LOBYTE(v39) = v56;
              McTemplateU0quqqz_EtwEventWriteTransfer(
                v38,
                (unsigned int)EapExceptionEvent,
                HIDWORD(v56),
                v39,
                SBYTE4(v56),
                SBYTE8(v56),
                (__int64)v79);
            }
            if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v44 = (*(__int64 (__fastcall **)(const EapHost::EapException *))(*(_QWORD *)v36 + 16LL))(v36);
              WPP_SF_ddddD(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, v45, v43, v42, v41, v40, v44);
            }
            v1 = v61;
            v11 = v59;
            v8 = v60;
          }
          catch ( const Exception *v71 )
          {
            v46 = v71;
            v47 = (*(__int64 (__fastcall **)(const Exception *))(*(_QWORD *)v71 + 16LL))(v71);
            FormatMessageW(0x1200u, 0, v47, 0, v79, 0x400u, 0);
            v50 = DWORD2(v56);
            v51 = DWORD1(v56);
            v52 = v56;
            v53 = HIDWORD(v56);
            if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
            {
              LOBYTE(v49) = v56;
              McTemplateU0quqqz_EtwEventWriteTransfer(
                v48,
                (unsigned int)ExceptionEvent,
                HIDWORD(v56),
                v49,
                SBYTE4(v56),
                SBYTE8(v56),
                (__int64)v79);
            }
            if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v54 = (*(__int64 (__fastcall **)(const Exception *))(*(_QWORD *)v46 + 16LL))(v46);
              WPP_SF_ddddD(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, v55, v53, v52, v51, v50, v54);
            }
            v1 = v61;
            v11 = v59;
            v8 = v60;
          }
          v11 += 4;
          v59 = v11;
        }
        std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v72);
        v21 = v64;
        if ( v64 )
        {
          std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(
            v64,
            v65,
            v19,
            v20);
          std::_Deallocate<16>(v21, (v66 - (_QWORD)v21) & 0xFFFFFFFFFFFFFFE0uLL);
        }
      }
      v8 += 4;
      v60 = v8;
      RegistryKey::Clear(&v57);
    }
    v9 = v67;
    if ( v67 )
    {
      std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(
        v67,
        v68,
        v6,
        v7);
      std::_Deallocate<16>(v9, (v69 - (_QWORD)v9) & 0xFFFFFFFFFFFFFFE0uLL);
    }
  }
  RegistryKey::Clear(&v62);
}

```

## disassembly

```asm
0x18001b7cc  mov     [rsp+arg_8], rbx
0x18001b7d1  mov     [rsp+arg_10], rsi
0x18001b7d6  push    rdi
0x18001b7d7  push    r14
0x18001b7d9  push    r15
0x18001b7db  sub     rsp, 930h
0x18001b7e2  mov     rax, cs:__security_cookie
0x18001b7e9  xor     rax, rsp
0x18001b7ec  mov     [rsp+948h+var_28], rax
0x18001b7f4  mov     r15, rcx
0x18001b7f7  mov     [rsp+948h+var_8D8], rcx
0x18001b7fc  lea     r14, WPP_GLOBAL_Control
0x18001b803  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b80a  cmp     rcx, r14
0x18001b80d  jz      short loc_18001B82A
0x18001b80f  test    byte ptr [rcx+1Ch], 4
0x18001b813  jz      short loc_18001B82A
0x18001b815  mov     edx, 21h ; '!'
0x18001b81a  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001b821  mov     rcx, [rcx+10h]
0x18001b825  call    WPP_SF_
0x18001b82a  xor     esi, esi
0x18001b82c  mov     [rsp+948h+var_8D0], rsi
0x18001b831  mov     [rsp+948h+var_8C8], 1
0x18001b83c  lea     r9d, [rsi+9]
0x18001b840  lea     rbx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Ea"...
0x18001b847  mov     r8, rbx
0x18001b84a  mov     rdx, 0FFFFFFFF80000002h
0x18001b851  lea     rcx, [rsp+948h+var_8D0]
0x18001b856  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001b85b  test    eax, eax
0x18001b85d  jz      short loc_18001B8A7
0x18001b85f  test    cs:Microsoft_Windows_EapHostEnableBits, 8
0x18001b866  jz      short loc_18001B873
0x18001b868  mov     r9b, al
0x18001b86b  mov     r8, rbx
0x18001b86e  call    McTemplateU0zc_EtwEventWriteTransfer
0x18001b873  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b87a  cmp     rcx, r14
0x18001b87d  jz      loc_18001B90E
0x18001b883  test    byte ptr [rcx+1Ch], 1
0x18001b887  jz      loc_18001B90E
0x18001b88d  mov     edx, 22h ; '"'
0x18001b892  mov     r9, rbx
0x18001b895  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001b89c  mov     rcx, [rcx+10h]
0x18001b8a0  call    WPP_SF_S
0x18001b8a5  jmp     short loc_18001B90E
0x18001b8a7  lea     rcx, [rsp+948h+var_8A8]
0x18001b8af  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(void)
0x18001b8b4  nop
0x18001b8b5  lea     rdx, [rsp+948h+var_8A8]
0x18001b8bd  lea     rcx, [rsp+948h+var_8D0]
0x18001b8c2  call    ?SubKeys@RegistryKey@@QEBAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@@Z; RegistryKey::SubKeys(std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18001b8c7  mov     rbx, [rsp+948h+var_8A8]
0x18001b8cf  mov     [rsp+948h+var_8E0], rbx
0x18001b8d4  mov     rdx, [rsp+948h+var_8A0]
0x18001b8dc  cmp     rbx, rdx
0x18001b8df  jnz     short loc_18001B941
0x18001b8e1  mov     rbx, [rsp+948h+var_8A8]
0x18001b8e9  test    rbx, rbx
0x18001b8ec  jz      short loc_18001B90E
0x18001b8ee  mov     rcx, rbx
0x18001b8f1  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> * const,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18001b8f6  mov     rdx, [rsp+948h+var_898]
0x18001b8fe  sub     rdx, rbx
0x18001b901  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18001b905  mov     rcx, rbx
0x18001b908  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001b90d  nop
0x18001b90e  lea     rcx, [rsp+948h+var_8D0]; this
0x18001b913  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18001b918  mov     rcx, [rsp+948h+var_28]
0x18001b920  xor     rcx, rsp; StackCookie
0x18001b923  call    __security_check_cookie
0x18001b928  lea     r11, [rsp+948h+var_18]
0x18001b930  mov     rbx, [r11+28h]
0x18001b934  mov     rsi, [r11+30h]
0x18001b938  mov     rsp, r11
0x18001b93b  pop     r15
0x18001b93d  pop     r14
0x18001b93f  pop     rdi
0x18001b940  retn
0x18001b941  mov     [rsp+948h+var_8F8], rsi
0x18001b946  mov     [rsp+948h+var_8F0], 1
0x18001b94e  mov     rcx, rbx
0x18001b951  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001b956  mov     r9d, 9
0x18001b95c  mov     r8, rax
0x18001b95f  mov     rdx, [rsp+948h+var_8D0]
0x18001b964  lea     rcx, [rsp+948h+var_8F8]
0x18001b969  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001b96e  test    eax, eax
0x18001b970  jnz     loc_18001BC99
0x18001b976  lea     rcx, [rsp+948h+var_8C0]
0x18001b97e  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(void)
0x18001b983  nop
0x18001b984  lea     rdx, [rsp+948h+var_8C0]
0x18001b98c  lea     rcx, [rsp+948h+var_8F8]
0x18001b991  call    ?SubKeys@RegistryKey@@QEBAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@@Z; RegistryKey::SubKeys(std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18001b996  mov     rdi, [rsp+948h+var_8C0]
0x18001b99e  mov     [rsp+948h+var_8E8], rdi
0x18001b9a3  mov     [rsp+948h+var_908], sil
0x18001b9a8  xor     eax, eax
0x18001b9aa  mov     [rsp+948h+var_907], ax
0x18001b9af  mov     [rsp+948h+var_905], al
0x18001b9b3  mov     [rsp+948h+var_904], rax
0x18001b9b8  mov     rcx, rbx
0x18001b9bb  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001b9c0  mov     rcx, rax
0x18001b9c3  call    cs:__imp__o__wtol
0x18001b9c9  mov     [rsp+948h+var_8FC], eax
0x18001b9cd  lea     rcx, [rsp+948h+var_880]
0x18001b9d5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x18001b9da  nop
0x18001b9db  lea     r8, [rsp+948h+var_880]
0x18001b9e3  lea     rdx, aName; "Name"
0x18001b9ea  lea     rcx, [rsp+948h+var_8F8]
0x18001b9ef  call    ?ReadMuiString@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::ReadMuiString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001b9f4  test    eax, eax
0x18001b9f6  jz      short loc_18001BA11
0x18001b9f8  lea     r8, [rsp+948h+var_880]
0x18001ba00  lea     rdx, aName; "Name"
0x18001ba07  lea     rcx, [rsp+948h+var_8F8]
0x18001ba0c  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001ba11  cmp     [rsp+948h+var_870], rsi
0x18001ba19  jnz     loc_18001BAEE
0x18001ba1f  lea     r8, [rsp+948h+var_880]
0x18001ba27  lea     rdx, qword_18003C520
0x18001ba2e  lea     rcx, [rsp+948h+var_8F8]
0x18001ba33  call    ?ReadMuiString@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::ReadMuiString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001ba38  test    eax, eax
0x18001ba3a  jz      short loc_18001BA55
0x18001ba3c  lea     r8, [rsp+948h+var_880]
0x18001ba44  lea     rdx, qword_18003C520
0x18001ba4b  lea     rcx, [rsp+948h+var_8F8]
0x18001ba50  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001ba55  cmp     [rsp+948h+var_870], rsi
0x18001ba5d  jnz     loc_18001BAEE
0x18001ba63  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba6a  cmp     rcx, r14
0x18001ba6d  jz      short loc_18001BA8A
0x18001ba6f  test    byte ptr [rcx+1Ch], 4
0x18001ba73  jz      short loc_18001BA8A
0x18001ba75  mov     edx, 23h ; '#'
0x18001ba7a  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001ba81  mov     rcx, [rcx+10h]
0x18001ba85  call    WPP_SF_
0x18001ba8a  xorps   xmm0, xmm0
0x18001ba8d  xor     eax, eax
0x18001ba8f  movups  xmmword ptr [rsp+948h+Buffer], xmm0
0x18001ba97  movups  [rsp+948h+var_840], xmm0
0x18001ba9f  mov     [rsp+948h+var_830], rax
0x18001baa7  mov     r9d, [rsp+948h+var_8FC]
0x18001baac  lea     r8, aAuthoridD; "AuthorId: %d"
0x18001bab3  lea     edx, [rax+14h]; BufferCount
0x18001bab6  lea     rcx, [rsp+948h+Buffer]; Buffer
0x18001babe  call    swprintf_s
0x18001bac3  lea     rax, [rsp+948h+Buffer]
0x18001bacb  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001bacf  inc     r8
0x18001bad2  cmp     [rax+r8*2], si
0x18001bad7  jnz     short loc_18001BACF
0x18001bad9  lea     rdx, [rsp+948h+Buffer]
0x18001bae1  lea     rcx, [rsp+948h+var_880]
0x18001bae9  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAAAEAV12@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::assign(wchar_t const * const,unsigned __int64)
0x18001baee  mov     r10, cs:WPP_GLOBAL_Control
0x18001baf5  cmp     r10, r14
0x18001baf8  jz      short loc_18001BB26
0x18001bafa  test    byte ptr [r10+1Ch], 4
0x18001baff  jz      short loc_18001BB26
0x18001bb01  lea     rcx, [rsp+948h+var_880]
0x18001bb09  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001bb0e  mov     r9, rax
0x18001bb11  mov     edx, 24h ; '$'
0x18001bb16  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001bb1d  mov     rcx, [r10+10h]
0x18001bb21  call    WPP_SF_S
0x18001bb26  cmp     rdi, [rsp+948h+var_8B8]
0x18001bb2e  jnz     short loc_18001BB7B
0x18001bb30  lea     rcx, [rsp+948h+var_880]
0x18001bb38  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001bb3d  nop
0x18001bb3e  mov     rdi, [rsp+948h+var_8C0]
0x18001bb46  test    rdi, rdi
0x18001bb49  jz      loc_18001BCE5
0x18001bb4f  mov     rdx, [rsp+948h+var_8B8]
0x18001bb57  mov     rcx, rdi
0x18001bb5a  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> * const,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18001bb5f  mov     rdx, [rsp+948h+var_8B0]
0x18001bb67  sub     rdx, rdi
0x18001bb6a  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18001bb6e  mov     rcx, rdi
0x18001bb71  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001bb76  jmp     loc_18001BCE5
0x18001bb7b  mov     [rsp+948h+var_860], rsi
0x18001bb83  mov     [rsp+948h+var_858], 1
0x18001bb8e  mov     rcx, rdi
0x18001bb91  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001bb96  mov     r9d, 9
0x18001bb9c  mov     r8, rax
0x18001bb9f  mov     rdx, [rsp+948h+var_8F8]
0x18001bba4  lea     rcx, [rsp+948h+var_860]
0x18001bbac  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001bbb1  test    eax, eax
0x18001bbb3  jnz     short loc_18001BBF9
0x18001bbb5  mov     rcx, rdi
0x18001bbb8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001bbbd  mov     rcx, rax
0x18001bbc0  call    cs:__imp__o__wtol
0x18001bbc6  mov     [rsp+948h+var_908], al
0x18001bbca  lea     r9, [rsp+948h+var_880]
0x18001bbd2  lea     rdx, [rsp+948h+var_860]
0x18001bbda  mov     rcx, r15
0x18001bbdd  cmp     al, 0FEh
0x18001bbdf  jnz     short loc_18001BBED
0x18001bbe1  mov     r8d, [rsp+948h+var_8FC]
0x18001bbe6  call    ?AddExpandedEapMethods@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; EapLm::BaseEapLibraryManager::AddExpandedEapMethods(RegistryKey const &,ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18001bbeb  jmp     short loc_18001BBF7
0x18001bbed  lea     r8, [rsp+948h+var_908]
0x18001bbf2  call    ?AddOneEapMethod@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@AEBU_EAP_METHOD_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; EapLm::BaseEapLibraryManager::AddOneEapMethod(RegistryKey const &,_EAP_METHOD_TYPE const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18001bbf7  jmp     short loc_18001BC61
0x18001bbf9  test    cs:Microsoft_Windows_EapHostEnableBits, 8
0x18001bc00  jz      short loc_18001BC1D
0x18001bc02  mov     rcx, rbx
0x18001bc05  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001bc0a  mov     r9, rax
0x18001bc0d  mov     rcx, rdi
0x18001bc10  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001bc15  mov     r8, rax
0x18001bc18  call    McTemplateU0zz_EtwEventWriteTransfer
0x18001bc1d  mov     r10, cs:WPP_GLOBAL_Control
0x18001bc24  cmp     r10, r14
0x18001bc27  jz      short loc_18001BC61
0x18001bc29  test    byte ptr [r10+1Ch], 1
0x18001bc2e  jz      short loc_18001BC61
0x18001bc30  mov     rcx, rdi
0x18001bc33  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001bc38  mov     r8, rax
0x18001bc3b  mov     rcx, rbx
0x18001bc3e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001bc43  mov     edx, 25h ; '%'
0x18001bc48  mov     [rsp+948h+var_928], r8
0x18001bc4d  mov     r9, rax
0x18001bc50  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001bc57  mov     rcx, [r10+10h]
0x18001bc5b  call    WPP_SF_SS
0x18001bc60  nop
0x18001bc61  lea     rcx, [rsp+948h+var_860]; this
0x18001bc69  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18001bc6e  nop
0x18001bc6f  jmp     short loc_18001BC8B
0x18001bc71  jmp     short $+2
0x18001bc73  mov     r15, [rsp+948h+var_8D8]
0x18001bc78  mov     rdi, [rsp+948h+var_8E8]
0x18001bc7d  mov     rbx, [rsp+948h+var_8E0]
0x18001bc82  xor     esi, esi
0x18001bc84  lea     r14, WPP_GLOBAL_Control
0x18001bc8b  add     rdi, 20h ; ' '
0x18001bc8f  mov     [rsp+948h+var_8E8], rdi
0x18001bc94  jmp     loc_18001BB26
0x18001bc99  test    cs:Microsoft_Windows_EapHostEnableBits, 8
0x18001bca0  jz      short loc_18001BCB2
0x18001bca2  mov     rcx, rbx
0x18001bca5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001bcaa  mov     r8, rax
0x18001bcad  call    McTemplateU0z_EtwEventWriteTransfer
0x18001bcb2  mov     r10, cs:WPP_GLOBAL_Control
0x18001bcb9  cmp     r10, r14
0x18001bcbc  jz      short loc_18001BCE5
0x18001bcbe  test    byte ptr [r10+1Ch], 1
0x18001bcc3  jz      short loc_18001BCE5
0x18001bcc5  mov     rcx, rbx
0x18001bcc8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001bccd  mov     edx, 29h ; ')'
0x18001bcd2  mov     r9, rax
0x18001bcd5  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001bcdc  mov     rcx, [r10+10h]
0x18001bce0  call    WPP_SF_S
0x18001bce5  add     rbx, 20h ; ' '
0x18001bce9  mov     [rsp+948h+var_8E0], rbx
0x18001bcee  lea     rcx, [rsp+948h+var_8F8]; this
0x18001bcf3  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18001bcf8  jmp     loc_18001B8D4
```
