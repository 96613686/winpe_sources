# EapLm::BaseEapLibraryManager::InitializeNativeMethods(void)

- ea: `0x18002d040`
- end: `0x18002d572`
- name: `?InitializeNativeMethods@BaseEapLibraryManager@EapLm@@AEAAXXZ`
- size: `1330`
- prototype: `void __fastcall(EapLm::BaseEapLibraryManager *__hidden this)`
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002c728`
- `0x18002cec0`

## callees

- `0x1800017a0`
- `0x1800022e0`
- `0x180004ec0`
- `0x18000eb74`
- `0x18000eb94`
- `0x180011ff0`
- `0x180015818`
- `0x180016518`
- `0x1800165a4`
- `0x180016c54`
- `0x1800216dc`
- `0x18002a514`
- `0x18002a738`
- `0x18002a7dc`
- `0x18002a8dc`
- `0x18002ab2c`
- `0x18002ac44`
- `0x18002ae64`
- `0x18002b8dc`
- `0x18002c06c`
- `0x18002d040`
- `0x18002ddf4`
- `0x18002de9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18002d237`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18002d434`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18002d237`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18002d434`

## string_xrefs

- `0x18002d0b4`: `System\CurrentControlSet\Services\EapHost\Methods`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall EapLm::BaseEapLibraryManager::InitializeNativeMethods(EapLm::BaseEapLibraryManager *this)
{
  EapLm::BaseEapLibraryManager *v1; // r15
  int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r9
  _QWORD *v6; // rbx
  _QWORD *v7; // rbx
  __int64 v8; // rax
  _QWORD *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // r10
  _QWORD *v14; // rdi
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // r10
  __int64 v22; // r8
  int v23; // r8d
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // r10
  const EapHost::EapException *v29; // r15
  DWORD v30; // eax
  int v31; // ecx
  int v32; // r9d
  int v33; // ebx
  int v34; // edi
  unsigned __int8 v35; // si
  unsigned int v36; // r14d
  int v37; // eax
  __int64 v38; // r8
  const Exception *v39; // r15
  DWORD v40; // eax
  int v41; // ecx
  int v42; // r9d
  int v43; // ebx
  int v44; // edi
  unsigned __int8 v45; // si
  unsigned int v46; // r14d
  int v47; // eax
  __int64 v48; // r8
  unsigned __int8 v49; // [rsp+40h] [rbp-908h] BYREF
  __int16 v50; // [rsp+41h] [rbp-907h]
  char v51; // [rsp+43h] [rbp-905h]
  __int64 v52; // [rsp+44h] [rbp-904h]
  unsigned int v53; // [rsp+4Ch] [rbp-8FCh]
  HKEY v54; // [rsp+50h] [rbp-8F8h] BYREF
  int v55; // [rsp+58h] [rbp-8F0h]
  _QWORD *v56; // [rsp+60h] [rbp-8E8h]
  _QWORD *v57; // [rsp+68h] [rbp-8E0h]
  EapLm::BaseEapLibraryManager *v58; // [rsp+70h] [rbp-8D8h]
  HKEY v59; // [rsp+78h] [rbp-8D0h] BYREF
  int v60; // [rsp+80h] [rbp-8C8h]
  _QWORD *v61; // [rsp+88h] [rbp-8C0h] BYREF
  _QWORD *v62; // [rsp+90h] [rbp-8B8h]
  __int64 v63; // [rsp+98h] [rbp-8B0h]
  _QWORD *v64; // [rsp+A0h] [rbp-8A8h] BYREF
  _QWORD *v65; // [rsp+A8h] [rbp-8A0h]
  __int64 v66; // [rsp+B0h] [rbp-898h]
  const EapHost::EapException *v67; // [rsp+B8h] [rbp-890h] BYREF
  const Exception *v68; // [rsp+C0h] [rbp-888h] BYREF
  _BYTE v69[16]; // [rsp+C8h] [rbp-880h] BYREF
  __int64 v70; // [rsp+D8h] [rbp-870h]
  __int64 v71; // [rsp+E8h] [rbp-860h] BYREF
  int v72; // [rsp+F0h] [rbp-858h]
  wchar_t Buffer[8]; // [rsp+F8h] [rbp-850h] BYREF
  __int128 v74; // [rsp+108h] [rbp-840h]
  __int64 v75; // [rsp+118h] [rbp-830h]
  WCHAR v76[1024]; // [rsp+120h] [rbp-828h] BYREF

  v1 = this;
  v58 = this;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
  v59 = 0;
  v60 = 1;
  v2 = RegistryKey::Open((__int64)&v59, HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\EapHost\\Methods", 9);
  if ( v2 )
  {
    if ( (Microsoft_Windows_EapHostEnableBits & 8) != 0 )
    {
      LOBYTE(v5) = v2;
      McTemplateU0zc_EtwEventWriteTransfer(v4, v3, L"System\\CurrentControlSet\\Services\\EapHost\\Methods", v5);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids,
        L"System\\CurrentControlSet\\Services\\EapHost\\Methods");
  }
  else
  {
    std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(&v64);
    RegistryKey::SubKeys(&v59, &v64);
    v6 = v64;
    v57 = v64;
    while ( v6 != v65 )
    {
      v54 = 0;
      v55 = 1;
      v8 = ((__int64 (__fastcall *)(_QWORD *))std::_String_val<std::_Simple_types<wchar_t>>::_Myptr)(v6);
      if ( (unsigned int)RegistryKey::Open((__int64)&v54, v59, (const WCHAR *)v8, 9) )
      {
        if ( (Microsoft_Windows_EapHostEnableBits & 8) != 0 )
        {
          v24 = ((__int64 (__fastcall *)(_QWORD *))std::_String_val<std::_Simple_types<wchar_t>>::_Myptr)(v6);
          McTemplateU0z_EtwEventWriteTransfer(v26, v25, v24);
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v27 = ((__int64 (__fastcall *)(_QWORD *))std::_String_val<std::_Simple_types<wchar_t>>::_Myptr)(v6);
          WPP_SF_S(*(_QWORD *)(v28 + 16), 41, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, v27);
        }
      }
      else
      {
        std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(&v61);
        RegistryKey::SubKeys(&v54, &v61);
        v9 = v61;
        v56 = v61;
        v49 = 0;
        v50 = 0;
        v51 = 0;
        v52 = 0;
        v10 = ((__int64 (__fastcall *)(_QWORD *))std::_String_val<std::_Simple_types<wchar_t>>::_Myptr)(v6);
        v53 = _o__wtol(v10);
        std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v69);
        if ( (unsigned int)RegistryKey::ReadMuiString(&v54, L"Name", v69) )
          RegistryKey::QueryValue(&v54, L"Name", v69);
        if ( !v70 )
        {
          if ( (unsigned int)RegistryKey::ReadMuiString(&v54, &qword_18003A720, v69) )
            RegistryKey::QueryValue(&v54, &qword_18003A720, v69);
          if ( !v70 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
            *(_OWORD *)Buffer = 0;
            v74 = 0;
            v75 = 0;
            swprintf_s(Buffer, 0x14u, L"AuthorId: %d", v53);
            v11 = -1;
            do
              ++v11;
            while ( Buffer[v11] );
            std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::assign(v69, Buffer);
          }
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v12 = ((__int64 (__fastcall *)(_BYTE *))std::_String_val<std::_Simple_types<wchar_t>>::_Myptr)(v69);
          WPP_SF_S(*(_QWORD *)(v13 + 16), 36, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, v12);
        }
        while ( v9 != v62 )
        {
          v71 = 0;
          v72 = 1;
          v15 = ((__int64 (__fastcall *)(_QWORD *))std::_String_val<std::_Simple_types<wchar_t>>::_Myptr)(v9);
          try
          {
            if ( (unsigned int)RegistryKey::Open((__int64)&v71, v54, (const WCHAR *)v15, 9) )
            {
              if ( (Microsoft_Windows_EapHostEnableBits & 8) != 0 )
              {
                ((void (__fastcall *)(_QWORD *))std::_String_val<std::_Simple_types<wchar_t>>::_Myptr)(v6);
                v17 = ((__int64 (__fastcall *)(_QWORD *))std::_String_val<std::_Simple_types<wchar_t>>::_Myptr)(v9);
                McTemplateU0zz_EtwEventWriteTransfer(v19, v18, v17);
              }
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                ((void (__fastcall *)(_QWORD *))std::_String_val<std::_Simple_types<wchar_t>>::_Myptr)(v9);
                v20 = ((__int64 (__fastcall *)(_QWORD *))std::_String_val<std::_Simple_types<wchar_t>>::_Myptr)(v6);
                WPP_SF_SS(*(_QWORD *)(v21 + 16), 37, (int)WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, v20, v22);
              }
            }
            else
            {
              v16 = ((__int64 (__fastcall *)(_QWORD *))std::_String_val<std::_Simple_types<wchar_t>>::_Myptr)(v9);
              v49 = _o__wtol(v16);
              if ( v49 == 0xFE )
                EapLm::BaseEapLibraryManager::AddExpandedEapMethods((__int64)v1, &v71, v53, (__int64)v69);
              else
                EapLm::BaseEapLibraryManager::AddOneEapMethod(
                  (__int64)v1,
                  (__int64)&v71,
                  (__int128 *)&v49,
                  (__int64)v69);
            }
            RegistryKey::Clear((HKEY *)&v71);
          }
          catch ( std::bad_alloc )
          {
            if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
              McGenEventWrite_EtwEventWriteTransfer(
                (_QWORD *)(unsigned int)&eaphost_Context,
                (unsigned int)OutOfMemory,
                v23,
                1,
                (__int64)&v71);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
            throw;
          }
          catch ( const EapHost::EapException *v67 )
          {
            v29 = v67;
            v30 = (*(__int64 (__fastcall **)(const EapHost::EapException *))(*(_QWORD *)v67 + 16LL))(v67);
            FormatMessageW(0x1200u, 0, v30, 0, v76, 0x400u, 0);
            v33 = HIDWORD(v52);
            v34 = v52;
            v35 = v49;
            v36 = v53;
            if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
            {
              LOBYTE(v32) = v49;
              McTemplateU0quqqz_EtwEventWriteTransfer(
                v31,
                (int)EapExceptionEvent,
                v53,
                v32,
                v52,
                SBYTE4(v52),
                (__int64)v76);
            }
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v37 = (*(__int64 (__fastcall **)(const EapHost::EapException *))(*(_QWORD *)v29 + 16LL))(v29);
              WPP_SF_ddddD(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, v38, v36, v35, v34, v33, v37);
            }
            v1 = v58;
            v9 = v56;
            v6 = v57;
          }
          catch ( const Exception *v68 )
          {
            v39 = v68;
            v40 = (*(__int64 (__fastcall **)(const Exception *))(*(_QWORD *)v68 + 16LL))(v68);
            FormatMessageW(0x1200u, 0, v40, 0, v76, 0x400u, 0);
            v43 = HIDWORD(v52);
            v44 = v52;
            v45 = v49;
            v46 = v53;
            if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
            {
              LOBYTE(v42) = v49;
              McTemplateU0quqqz_EtwEventWriteTransfer(
                v41,
                (int)ExceptionEvent,
                v53,
                v42,
                v52,
                SBYTE4(v52),
                (__int64)v76);
            }
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v47 = (*(__int64 (__fastcall **)(const Exception *))(*(_QWORD *)v39 + 16LL))(v39);
              WPP_SF_ddddD(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, v48, v46, v45, v44, v43, v47);
            }
            v1 = v58;
            v9 = v56;
            v6 = v57;
          }
          v9 += 4;
          v56 = v9;
        }
        std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v69);
        v14 = v61;
        if ( v61 )
        {
          std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(
            v61,
            v62);
          std::_Deallocate<16>(v14, (v63 - (_QWORD)v14) & 0xFFFFFFFFFFFFFFE0uLL);
        }
      }
      v6 += 4;
      v57 = v6;
      RegistryKey::Clear(&v54);
    }
    v7 = v64;
    if ( v64 )
    {
      std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(
        v64,
        v65);
      std::_Deallocate<16>(v7, (v66 - (_QWORD)v7) & 0xFFFFFFFFFFFFFFE0uLL);
    }
  }
  RegistryKey::Clear(&v59);
}

```

## disassembly

```asm
0x18002d040  mov     [rsp+arg_8], rbx
0x18002d045  mov     [rsp+arg_10], rsi
0x18002d04a  push    rdi
0x18002d04b  push    r14
0x18002d04d  push    r15
0x18002d04f  sub     rsp, 930h
0x18002d056  mov     rax, cs:__security_cookie
0x18002d05d  xor     rax, rsp
0x18002d060  mov     [rsp+948h+var_28], rax
0x18002d068  mov     r15, rcx
0x18002d06b  mov     [rsp+948h+var_8D8], rcx
0x18002d070  lea     r14, WPP_GLOBAL_Control
0x18002d077  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d07e  cmp     rcx, r14
0x18002d081  jz      short loc_18002D09E
0x18002d083  test    byte ptr [rcx+1Ch], 4
0x18002d087  jz      short loc_18002D09E
0x18002d089  mov     edx, 21h ; '!'
0x18002d08e  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18002d095  mov     rcx, [rcx+10h]
0x18002d099  call    WPP_SF_
0x18002d09e  xor     esi, esi
0x18002d0a0  mov     [rsp+948h+var_8D0], rsi
0x18002d0a5  mov     [rsp+948h+var_8C8], 1
0x18002d0b0  lea     r9d, [rsi+9]
0x18002d0b4  lea     rbx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Ea"...
0x18002d0bb  mov     r8, rbx
0x18002d0be  mov     rdx, 0FFFFFFFF80000002h
0x18002d0c5  lea     rcx, [rsp+948h+var_8D0]
0x18002d0ca  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18002d0cf  test    eax, eax
0x18002d0d1  jz      short loc_18002D11B
0x18002d0d3  test    cs:Microsoft_Windows_EapHostEnableBits, 8
0x18002d0da  jz      short loc_18002D0E7
0x18002d0dc  mov     r9b, al
0x18002d0df  mov     r8, rbx
0x18002d0e2  call    McTemplateU0zc_EtwEventWriteTransfer
0x18002d0e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d0ee  cmp     rcx, r14
0x18002d0f1  jz      loc_18002D182
0x18002d0f7  test    byte ptr [rcx+1Ch], 1
0x18002d0fb  jz      loc_18002D182
0x18002d101  mov     edx, 22h ; '"'
0x18002d106  mov     r9, rbx
0x18002d109  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18002d110  mov     rcx, [rcx+10h]
0x18002d114  call    WPP_SF_S
0x18002d119  jmp     short loc_18002D182
0x18002d11b  lea     rcx, [rsp+948h+var_8A8]
0x18002d123  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(void)
0x18002d128  nop
0x18002d129  lea     rdx, [rsp+948h+var_8A8]
0x18002d131  lea     rcx, [rsp+948h+var_8D0]
0x18002d136  call    ?SubKeys@RegistryKey@@QEBAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@@Z; RegistryKey::SubKeys(std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18002d13b  mov     rbx, [rsp+948h+var_8A8]
0x18002d143  mov     [rsp+948h+var_8E0], rbx
0x18002d148  mov     rdx, [rsp+948h+var_8A0]
0x18002d150  cmp     rbx, rdx
0x18002d153  jnz     short loc_18002D1B5
0x18002d155  mov     rbx, [rsp+948h+var_8A8]
0x18002d15d  test    rbx, rbx
0x18002d160  jz      short loc_18002D182
0x18002d162  mov     rcx, rbx
0x18002d165  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> * const,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18002d16a  mov     rdx, [rsp+948h+var_898]
0x18002d172  sub     rdx, rbx
0x18002d175  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18002d179  mov     rcx, rbx
0x18002d17c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002d181  nop
0x18002d182  lea     rcx, [rsp+948h+var_8D0]; this
0x18002d187  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18002d18c  mov     rcx, [rsp+948h+var_28]
0x18002d194  xor     rcx, rsp; StackCookie
0x18002d197  call    __security_check_cookie
0x18002d19c  lea     r11, [rsp+948h+var_18]
0x18002d1a4  mov     rbx, [r11+28h]
0x18002d1a8  mov     rsi, [r11+30h]
0x18002d1ac  mov     rsp, r11
0x18002d1af  pop     r15
0x18002d1b1  pop     r14
0x18002d1b3  pop     rdi
0x18002d1b4  retn
0x18002d1b5  mov     [rsp+948h+var_8F8], rsi
0x18002d1ba  mov     [rsp+948h+var_8F0], 1
0x18002d1c2  mov     rcx, rbx
0x18002d1c5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002d1ca  mov     r9d, 9
0x18002d1d0  mov     r8, rax
0x18002d1d3  mov     rdx, [rsp+948h+var_8D0]
0x18002d1d8  lea     rcx, [rsp+948h+var_8F8]
0x18002d1dd  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18002d1e2  test    eax, eax
0x18002d1e4  jnz     loc_18002D50D
0x18002d1ea  lea     rcx, [rsp+948h+var_8C0]
0x18002d1f2  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(void)
0x18002d1f7  nop
0x18002d1f8  lea     rdx, [rsp+948h+var_8C0]
0x18002d200  lea     rcx, [rsp+948h+var_8F8]
0x18002d205  call    ?SubKeys@RegistryKey@@QEBAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@@Z; RegistryKey::SubKeys(std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18002d20a  mov     rdi, [rsp+948h+var_8C0]
0x18002d212  mov     [rsp+948h+var_8E8], rdi
0x18002d217  mov     [rsp+948h+var_908], sil
0x18002d21c  xor     eax, eax
0x18002d21e  mov     [rsp+948h+var_907], ax
0x18002d223  mov     [rsp+948h+var_905], al
0x18002d227  mov     [rsp+948h+var_904], rax
0x18002d22c  mov     rcx, rbx
0x18002d22f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002d234  mov     rcx, rax
0x18002d237  call    cs:__imp__o__wtol
0x18002d23d  mov     [rsp+948h+var_8FC], eax
0x18002d241  lea     rcx, [rsp+948h+var_880]
0x18002d249  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x18002d24e  nop
0x18002d24f  lea     r8, [rsp+948h+var_880]
0x18002d257  lea     rdx, aName; "Name"
0x18002d25e  lea     rcx, [rsp+948h+var_8F8]
0x18002d263  call    ?ReadMuiString@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::ReadMuiString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18002d268  test    eax, eax
0x18002d26a  jz      short loc_18002D285
0x18002d26c  lea     r8, [rsp+948h+var_880]
0x18002d274  lea     rdx, aName; "Name"
0x18002d27b  lea     rcx, [rsp+948h+var_8F8]
0x18002d280  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18002d285  cmp     [rsp+948h+var_870], rsi
0x18002d28d  jnz     loc_18002D362
0x18002d293  lea     r8, [rsp+948h+var_880]
0x18002d29b  lea     rdx, qword_18003A720
0x18002d2a2  lea     rcx, [rsp+948h+var_8F8]
0x18002d2a7  call    ?ReadMuiString@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::ReadMuiString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18002d2ac  test    eax, eax
0x18002d2ae  jz      short loc_18002D2C9
0x18002d2b0  lea     r8, [rsp+948h+var_880]
0x18002d2b8  lea     rdx, qword_18003A720
0x18002d2bf  lea     rcx, [rsp+948h+var_8F8]
0x18002d2c4  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18002d2c9  cmp     [rsp+948h+var_870], rsi
0x18002d2d1  jnz     loc_18002D362
0x18002d2d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d2de  cmp     rcx, r14
0x18002d2e1  jz      short loc_18002D2FE
0x18002d2e3  test    byte ptr [rcx+1Ch], 4
0x18002d2e7  jz      short loc_18002D2FE
0x18002d2e9  mov     edx, 23h ; '#'
0x18002d2ee  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18002d2f5  mov     rcx, [rcx+10h]
0x18002d2f9  call    WPP_SF_
0x18002d2fe  xorps   xmm0, xmm0
0x18002d301  xor     eax, eax
0x18002d303  movups  xmmword ptr [rsp+948h+Buffer], xmm0
0x18002d30b  movups  [rsp+948h+var_840], xmm0
0x18002d313  mov     [rsp+948h+var_830], rax
0x18002d31b  mov     r9d, [rsp+948h+var_8FC]
0x18002d320  lea     r8, aAuthoridD; "AuthorId: %d"
0x18002d327  lea     edx, [rax+14h]; BufferCount
0x18002d32a  lea     rcx, [rsp+948h+Buffer]; Buffer
0x18002d332  call    swprintf_s
0x18002d337  lea     rax, [rsp+948h+Buffer]
0x18002d33f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002d343  inc     r8
0x18002d346  cmp     [rax+r8*2], si
0x18002d34b  jnz     short loc_18002D343
0x18002d34d  lea     rdx, [rsp+948h+Buffer]
0x18002d355  lea     rcx, [rsp+948h+var_880]
0x18002d35d  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAAAEAV12@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::assign(wchar_t const * const,unsigned __int64)
0x18002d362  mov     r10, cs:WPP_GLOBAL_Control
0x18002d369  cmp     r10, r14
0x18002d36c  jz      short loc_18002D39A
0x18002d36e  test    byte ptr [r10+1Ch], 4
0x18002d373  jz      short loc_18002D39A
0x18002d375  lea     rcx, [rsp+948h+var_880]
0x18002d37d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002d382  mov     r9, rax
0x18002d385  mov     edx, 24h ; '$'
0x18002d38a  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18002d391  mov     rcx, [r10+10h]
0x18002d395  call    WPP_SF_S
0x18002d39a  cmp     rdi, [rsp+948h+var_8B8]
0x18002d3a2  jnz     short loc_18002D3EF
0x18002d3a4  lea     rcx, [rsp+948h+var_880]
0x18002d3ac  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18002d3b1  nop
0x18002d3b2  mov     rdi, [rsp+948h+var_8C0]
0x18002d3ba  test    rdi, rdi
0x18002d3bd  jz      loc_18002D559
0x18002d3c3  mov     rdx, [rsp+948h+var_8B8]
0x18002d3cb  mov     rcx, rdi
0x18002d3ce  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> * const,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18002d3d3  mov     rdx, [rsp+948h+var_8B0]
0x18002d3db  sub     rdx, rdi
0x18002d3de  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18002d3e2  mov     rcx, rdi
0x18002d3e5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002d3ea  jmp     loc_18002D559
0x18002d3ef  mov     [rsp+948h+var_860], rsi
0x18002d3f7  mov     [rsp+948h+var_858], 1
0x18002d402  mov     rcx, rdi
0x18002d405  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002d40a  mov     r9d, 9
0x18002d410  mov     r8, rax
0x18002d413  mov     rdx, [rsp+948h+var_8F8]
0x18002d418  lea     rcx, [rsp+948h+var_860]
0x18002d420  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18002d425  test    eax, eax
0x18002d427  jnz     short loc_18002D46D
0x18002d429  mov     rcx, rdi
0x18002d42c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002d431  mov     rcx, rax
0x18002d434  call    cs:__imp__o__wtol
0x18002d43a  mov     [rsp+948h+var_908], al
0x18002d43e  lea     r9, [rsp+948h+var_880]
0x18002d446  lea     rdx, [rsp+948h+var_860]
0x18002d44e  mov     rcx, r15
0x18002d451  cmp     al, 0FEh
0x18002d453  jnz     short loc_18002D461
0x18002d455  mov     r8d, [rsp+948h+var_8FC]
0x18002d45a  call    ?AddExpandedEapMethods@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; EapLm::BaseEapLibraryManager::AddExpandedEapMethods(RegistryKey const &,ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18002d45f  jmp     short loc_18002D46B
0x18002d461  lea     r8, [rsp+948h+var_908]
0x18002d466  call    ?AddOneEapMethod@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@AEBU_EAP_METHOD_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; EapLm::BaseEapLibraryManager::AddOneEapMethod(RegistryKey const &,_EAP_METHOD_TYPE const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18002d46b  jmp     short loc_18002D4D5
0x18002d46d  test    cs:Microsoft_Windows_EapHostEnableBits, 8
0x18002d474  jz      short loc_18002D491
0x18002d476  mov     rcx, rbx
0x18002d479  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002d47e  mov     r9, rax
0x18002d481  mov     rcx, rdi
0x18002d484  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002d489  mov     r8, rax
0x18002d48c  call    McTemplateU0zz_EtwEventWriteTransfer
0x18002d491  mov     r10, cs:WPP_GLOBAL_Control
0x18002d498  cmp     r10, r14
0x18002d49b  jz      short loc_18002D4D5
0x18002d49d  test    byte ptr [r10+1Ch], 1
0x18002d4a2  jz      short loc_18002D4D5
0x18002d4a4  mov     rcx, rdi
0x18002d4a7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002d4ac  mov     r8, rax
0x18002d4af  mov     rcx, rbx
0x18002d4b2  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002d4b7  mov     edx, 25h ; '%'
0x18002d4bc  mov     [rsp+948h+var_928], r8
0x18002d4c1  mov     r9, rax
0x18002d4c4  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18002d4cb  mov     rcx, [r10+10h]
0x18002d4cf  call    WPP_SF_SS
0x18002d4d4  nop
0x18002d4d5  lea     rcx, [rsp+948h+var_860]; this
0x18002d4dd  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18002d4e2  nop
0x18002d4e3  jmp     short loc_18002D4FF
0x18002d4e5  jmp     short $+2
0x18002d4e7  mov     r15, [rsp+948h+var_8D8]
0x18002d4ec  mov     rdi, [rsp+948h+var_8E8]
0x18002d4f1  mov     rbx, [rsp+948h+var_8E0]
0x18002d4f6  xor     esi, esi
0x18002d4f8  lea     r14, WPP_GLOBAL_Control
0x18002d4ff  add     rdi, 20h ; ' '
0x18002d503  mov     [rsp+948h+var_8E8], rdi
0x18002d508  jmp     loc_18002D39A
0x18002d50d  test    cs:Microsoft_Windows_EapHostEnableBits, 8
0x18002d514  jz      short loc_18002D526
0x18002d516  mov     rcx, rbx
0x18002d519  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002d51e  mov     r8, rax
0x18002d521  call    McTemplateU0z_EtwEventWriteTransfer
0x18002d526  mov     r10, cs:WPP_GLOBAL_Control
0x18002d52d  cmp     r10, r14
0x18002d530  jz      short loc_18002D559
0x18002d532  test    byte ptr [r10+1Ch], 1
0x18002d537  jz      short loc_18002D559
0x18002d539  mov     rcx, rbx
0x18002d53c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002d541  mov     edx, 29h ; ')'
0x18002d546  mov     r9, rax
0x18002d549  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18002d550  mov     rcx, [r10+10h]
0x18002d554  call    WPP_SF_S
0x18002d559  add     rbx, 20h ; ' '
0x18002d55d  mov     [rsp+948h+var_8E0], rbx
0x18002d562  lea     rcx, [rsp+948h+var_8F8]; this
0x18002d567  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18002d56c  jmp     loc_18002D148
```
