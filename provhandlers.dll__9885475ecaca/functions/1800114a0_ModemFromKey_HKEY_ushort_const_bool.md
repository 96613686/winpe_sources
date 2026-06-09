# ModemFromKey(HKEY__ *,ushort const *,bool)

- ea: `0x1800114a0`
- end: `0x18001187f`
- name: `?ModemFromKey@@YA?AV?$shared_ptr@UModem@@@std@@PEAUHKEY__@@PEBG_N@Z`
- size: `991`
- prototype: `__int64 *__fastcall(__int64 *, HKEY, char *, char)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18000fe50`

## callees

- `0x180002034`
- `0x180002c08`
- `0x18000e308`
- `0x18000f598`
- `0x18000f84c`
- `0x18000f8d0`
- `0x18000fc8c`
- `0x1800114a0`
- `0x180012390`
- `0x1800123b0`
- `0x180012b88`
- `0x180012e00`
- `0x18003b9a0`
- `0x18003f010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001180a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001180a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800117c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800117c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800115e4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800115e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011660`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011660`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800117f6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800117f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 *__fastcall ModemFromKey(__int64 *a1, HKEY a2, char *a3, char a4)
{
  int v8; // edi
  HKEY v9; // rax
  HKEY v10; // rbx
  unsigned __int64 v11; // r8
  unsigned int v12; // eax
  DWORD v13; // eax
  WCHAR *v14; // rbx
  DWORD v15; // r14d
  DWORD i; // edx
  unsigned int v17; // eax
  _QWORD *v18; // rdi
  __int64 v19; // r12
  __int64 v20; // r9
  __int64 v21; // r8
  __int64 v22; // r8
  unsigned __int64 v23; // r8
  unsigned __int64 v24; // r9
  unsigned __int64 v25; // rdx
  HKEY *v26; // r13
  HKEY v27; // rax
  __int64 v28; // rdi
  __int64 *v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rcx
  volatile signed __int32 *v32; // rdi
  unsigned int v33; // eax
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-E0h]
  unsigned int lpcSubKeysa; // [rsp+20h] [rbp-E0h]
  unsigned int lpcSubKeysb; // [rsp+20h] [rbp-E0h]
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-9Ch] BYREF
  int v40; // [rsp+68h] [rbp-98h]
  HKEY phkResult[4]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v42; // [rsp+90h] [rbp-70h] BYREF
  volatile signed __int32 *v43; // [rsp+98h] [rbp-68h]
  _BYTE v44[112]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  phkResult[1] = (HKEY)a1;
  v8 = 0;
  v40 = 0;
  v9 = (HKEY)operator new(0x78u);
  v10 = v9;
  phkResult[0] = v9;
  if ( v9 )
  {
    *((_QWORD *)v9 + 3) = 7;
    *((_QWORD *)v9 + 2) = 0;
    *(_WORD *)v9 = 0;
    if ( *(_WORD *)a3 )
    {
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)&a3[2 * v11] );
    }
    else
    {
      v11 = 0;
    }
    std::wstring::assign(v9, a3, v11);
    *((_QWORD *)v10 + 14) = 0;
    *((_QWORD *)v10 + 7) = 7;
    *((_QWORD *)v10 + 6) = 0;
    *((_WORD *)v10 + 16) = 0;
    *((_QWORD *)v10 + 8) = 0;
    *((_QWORD *)v10 + 9) = 0;
    *((_QWORD *)v10 + 10) = 0;
    *((_QWORD *)v10 + 11) = 0;
    *((_QWORD *)v10 + 12) = 0;
    *((_QWORD *)v10 + 13) = 0;
    v8 = 15;
    v40 = 15;
    *(_DWORD *)((char *)v10 + 114) = 0;
    *((_WORD *)v10 + 59) = 0;
  }
  else
  {
    v10 = 0;
  }
  *a1 = 0;
  a1[1] = 0;
  std::shared_ptr<Modem>::_Resetp<Modem>(a1, v10);
  v40 = v8 | 0x10;
  std::wstring::assign((_QWORD *)(*a1 + 32), (char *)L"350123450123456", 0xFu);
  *(_BYTE *)(*a1 + 112) = a4;
  cbMaxSubKeyLen = 0;
  v12 = RegQueryInfoKeyW(a2, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v12 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x20F,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
      (const char *)v12,
      lpcSubKeys);
  v13 = cbMaxSubKeyLen;
  if ( cbMaxSubKeyLen )
  {
    ++cbMaxSubKeyLen;
    v14 = (WCHAR *)operator new[](saturated_mul(v13 + 1, 2u));
    phkResult[2] = (HKEY)v14;
    v15 = 0;
    for ( i = 0; ; i = v15 )
    {
      cchName = cbMaxSubKeyLen;
      v33 = RegEnumKeyExW(a2, i, v14, &cchName, 0, 0, 0, 0);
      if ( v33 == 259 )
        break;
      if ( v33 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x220,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
          (const char *)v33,
          lpcSubKeysb);
      phkResult[0] = 0;
      v17 = RegOpenKeyExW(a2, v14, 0, 0x20019u, phkResult);
      if ( v17 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x224,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
          (const char *)v17,
          lpcSubKeysa);
      v18 = (_QWORD *)*a1;
      v19 = UiccFromKey(v44, phkResult[0]);
      v20 = v18[10];
      v21 = v18[9];
      if ( v21 == v20 && !((v20 - v21) >> 3) )
      {
        v22 = (v21 - v18[8]) >> 3;
        if ( v22 == 0x1FFFFFFFFFFFFFFFLL )
          std::vector<std::shared_ptr<CMvExtensionKey>>::_Xlen();
        v23 = v22 + 1;
        v24 = (v20 - v18[8]) >> 3;
        v25 = 0;
        if ( 0x1FFFFFFFFFFFFFFFLL - (v24 >> 1) >= v24 )
          v25 = v24 + (v24 >> 1);
        if ( v25 < v23 )
          v25 = v23;
        std::vector<nullable_any<Uicc>>::_Reallocate(v18 + 8, v25);
      }
      v26 = (HKEY *)v18[9];
      v27 = (HKEY)operator new(0x70u);
      phkResult[3] = v27;
      if ( v27 )
        v27 = (HKEY)Uicc::Uicc(v27, v19);
      *v26 = v27;
      v18[9] += 8LL;
      Uicc::~Uicc((Uicc *)v44);
      v28 = *(_QWORD *)(*(_QWORD *)(*a1 + 72) - 8LL);
      v29 = std::shared_ptr<CMvExtensionKey const>::shared_ptr<CMvExtensionKey const>(&v42, a1);
      v30 = v29[1];
      v29[1] = *(_QWORD *)(v28 + 88);
      *(_QWORD *)(v28 + 88) = v30;
      v31 = *v29;
      *v29 = *(_QWORD *)(v28 + 80);
      *(_QWORD *)(v28 + 80) = v31;
      v32 = v43;
      if ( v43 )
      {
        if ( _InterlockedExchangeAdd(v43 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
          if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
        }
      }
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*a1 + 72) - 8LL) + 96LL) = v15;
      if ( phkResult[0] )
        RegCloseKey(phkResult[0]);
      ++v15;
    }
    operator delete[](v14);
  }
  return a1;
}

```

## disassembly

```asm
0x1800114a0  mov     [rsp-8+arg_18], rbx
0x1800114a5  push    rbp
0x1800114a6  push    rsi
0x1800114a7  push    rdi
0x1800114a8  push    r12
0x1800114aa  push    r13
0x1800114ac  push    r14
0x1800114ae  push    r15
0x1800114b0  lea     rbp, [rsp-20h]
0x1800114b5  sub     rsp, 120h
0x1800114bc  mov     rax, cs:__security_cookie
0x1800114c3  xor     rax, rsp
0x1800114c6  mov     [rbp+50h+var_40], rax
0x1800114ca  mov     r12b, r9b
0x1800114cd  mov     r14, r8
0x1800114d0  mov     r15, rdx
0x1800114d3  mov     rsi, rcx
0x1800114d6  mov     [rsp+150h+var_D8], rcx
0x1800114db  xor     r13d, r13d
0x1800114de  mov     edi, r13d
0x1800114e1  mov     [rsp+150h+var_E8], r13d
0x1800114e6  lea     ecx, [r13+78h]; Size
0x1800114ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800114ef  mov     rbx, rax
0x1800114f2  mov     [rsp+150h+phkResult], rax
0x1800114f7  test    rax, rax
0x1800114fa  jz      short loc_18001156B
0x1800114fc  lea     edi, [r13+7]
0x180011500  mov     [rax+18h], rdi
0x180011504  mov     [rax+10h], r13
0x180011508  mov     [rax], r13w
0x18001150c  cmp     [r14], r13w
0x180011510  jnz     short loc_180011517
0x180011512  mov     r8d, r13d
0x180011515  jmp     short loc_180011525
0x180011517  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001151b  inc     r8
0x18001151e  cmp     [r14+r8*2], r13w
0x180011523  jnz     short loc_18001151B
0x180011525  mov     rdx, r14; Src
0x180011528  mov     rcx, rbx; void *
0x18001152b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180011530  xor     eax, eax
0x180011532  mov     [rbx+70h], rax
0x180011536  mov     [rbx+38h], rdi
0x18001153a  mov     [rbx+30h], r13
0x18001153e  mov     [rbx+20h], r13w
0x180011543  mov     [rbx+40h], r13
0x180011547  mov     [rbx+48h], r13
0x18001154b  mov     [rbx+50h], r13
0x18001154f  mov     [rbx+58h], r13
0x180011553  mov     [rbx+60h], r13
0x180011557  mov     [rbx+68h], r13
0x18001155b  lea     edi, [rax+0Fh]
0x18001155e  mov     [rsp+150h+var_E8], edi
0x180011562  mov     [rbx+72h], eax
0x180011565  mov     [rbx+76h], ax
0x180011569  jmp     short loc_18001156E
0x18001156b  mov     rbx, r13
0x18001156e  mov     [rsi], r13
0x180011571  mov     [rsi+8], r13
0x180011575  mov     rdx, rbx
0x180011578  mov     rcx, rsi
0x18001157b  call    ??$_Resetp@UModem@@@?$shared_ptr@UModem@@@std@@AEAAXPEAUModem@@@Z; std::shared_ptr<Modem>::_Resetp<Modem>(Modem *)
0x180011580  or      edi, 10h
0x180011583  mov     [rsp+150h+var_E8], edi
0x180011587  mov     rcx, [rsi]
0x18001158a  add     rcx, 20h ; ' '; void *
0x18001158e  mov     r8d, 0Fh
0x180011594  lea     rdx, a35012345012345; "350123450123456"
0x18001159b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800115a0  mov     rax, [rsi]
0x1800115a3  mov     [rax+70h], r12b
0x1800115a7  mov     [rsp+150h+cbMaxSubKeyLen], r13d
0x1800115ac  mov     [rsp+150h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1800115b1  mov     [rsp+150h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x1800115b6  mov     [rsp+150h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x1800115bb  mov     [rsp+150h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x1800115c0  mov     [rsp+150h+lpcValues], r13; lpcValues
0x1800115c5  mov     [rsp+150h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x1800115ca  lea     rax, [rsp+150h+cbMaxSubKeyLen]
0x1800115cf  mov     [rsp+150h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800115d4  mov     [rsp+150h+lpcSubKeys], r13; unsigned int
0x1800115d9  xor     r9d, r9d; lpReserved
0x1800115dc  xor     r8d, r8d; lpcchClass
0x1800115df  xor     edx, edx; lpClass
0x1800115e1  mov     rcx, r15; hKey
0x1800115e4  call    cs:__imp_RegQueryInfoKeyW
0x1800115ea  mov     rcx, [rbp+58h]; this
0x1800115ee  test    eax, eax
0x1800115f0  jnz     loc_180011864
0x1800115f6  mov     eax, [rsp+150h+cbMaxSubKeyLen]
0x1800115fa  test    eax, eax
0x1800115fc  jz      loc_180011810
0x180011602  inc     eax
0x180011604  mov     [rsp+150h+cbMaxSubKeyLen], eax
0x180011608  mov     ecx, eax
0x18001160a  mov     eax, 2
0x18001160f  mul     rcx
0x180011612  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180011619  cmovb   rax, rcx
0x18001161d  mov     rcx, rax; unsigned __int64
0x180011620  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180011625  mov     rbx, rax
0x180011628  mov     [rbp+50h+var_D0], rax
0x18001162c  mov     r14d, r13d
0x18001162f  xor     edx, edx
0x180011631  jmp     loc_1800117CF
0x180011636  mov     rcx, [rbp+58h]; this
0x18001163a  test    eax, eax
0x18001163c  jnz     loc_18001184F
0x180011642  mov     [rsp+150h+phkResult], r13
0x180011647  lea     rax, [rsp+150h+phkResult]
0x18001164c  mov     [rsp+150h+lpcSubKeys], rax; unsigned int
0x180011651  mov     r9d, 20019h; samDesired
0x180011657  xor     r8d, r8d; ulOptions
0x18001165a  mov     rdx, rbx; lpSubKey
0x18001165d  mov     rcx, r15; hKey
0x180011660  call    cs:__imp_RegOpenKeyExW
0x180011666  mov     rcx, [rbp+58h]; this
0x18001166a  test    eax, eax
0x18001166c  jnz     loc_18001183A
0x180011672  mov     rdi, [rsi]
0x180011675  mov     rdx, [rsp+150h+phkResult]
0x18001167a  lea     rcx, [rbp+50h+var_B0]
0x18001167e  call    ?UiccFromKey@@YA?AUUicc@@PEAUHKEY__@@@Z; UiccFromKey(HKEY__ *)
0x180011683  mov     r12, rax
0x180011686  mov     r9, [rdi+50h]
0x18001168a  mov     r8, [rdi+48h]
0x18001168e  cmp     r8, r9
0x180011691  jnz     short loc_1800116F6
0x180011693  mov     rax, r9
0x180011696  sub     rax, r8
0x180011699  sar     rax, 3
0x18001169d  cmp     rax, 1
0x1800116a1  jnb     short loc_1800116F6
0x1800116a3  sub     r8, [rdi+40h]
0x1800116a7  sar     r8, 3
0x1800116ab  mov     rcx, 1FFFFFFFFFFFFFFFh
0x1800116b5  mov     rax, rcx
0x1800116b8  sub     rax, r8
0x1800116bb  cmp     rax, 1
0x1800116bf  jb      loc_180011879
0x1800116c5  inc     r8
0x1800116c8  sub     r9, [rdi+40h]
0x1800116cc  sar     r9, 3
0x1800116d0  mov     rax, r9
0x1800116d3  shr     rax, 1
0x1800116d6  sub     rcx, rax
0x1800116d9  add     rax, r9
0x1800116dc  mov     rdx, r13
0x1800116df  cmp     rcx, r9
0x1800116e2  cmovnb  rdx, rax
0x1800116e6  cmp     rdx, r8
0x1800116e9  cmovb   rdx, r8
0x1800116ed  lea     rcx, [rdi+40h]
0x1800116f1  call    ?_Reallocate@?$vector@V?$nullable_any@UUicc@@@@V?$allocator@V?$nullable_any@UUicc@@@@@std@@@std@@IEAAX_K@Z; std::vector<nullable_any<Uicc>>::_Reallocate(unsigned __int64)
0x1800116f6  mov     r13, [rdi+48h]
0x1800116fa  mov     ecx, 70h ; 'p'; Size
0x1800116ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011704  mov     [rbp+50h+var_C8], rax
0x180011708  test    rax, rax
0x18001170b  jz      short loc_180011718
0x18001170d  mov     rdx, r12
0x180011710  mov     rcx, rax
0x180011713  call    ??0Uicc@@QEAA@$$QEAU0@@Z; Uicc::Uicc(Uicc &&)
0x180011718  mov     [r13+0], rax
0x18001171c  add     qword ptr [rdi+48h], 8
0x180011721  lea     rcx, [rbp+50h+var_B0]; this
0x180011725  call    ??1Uicc@@QEAA@XZ; Uicc::~Uicc(void)
0x18001172a  mov     rax, [rsi]
0x18001172d  mov     rcx, [rax+48h]
0x180011731  mov     rdi, [rcx-8]
0x180011735  mov     rdx, rsi
0x180011738  lea     rcx, [rbp+50h+var_C0]
0x18001173c  call    ??$?0VCMvExtensionKey@@@?$shared_ptr@$$CBVCMvExtensionKey@@@std@@QEAA@AEBV?$shared_ptr@VCMvExtensionKey@@@1@PEAPEAX@Z; std::shared_ptr<CMvExtensionKey const>::shared_ptr<CMvExtensionKey const>(std::shared_ptr<CMvExtensionKey> const &,void * *)
0x180011741  mov     rdx, rax
0x180011744  mov     rcx, [rax+8]
0x180011748  mov     rax, [rdi+58h]
0x18001174c  mov     [rdx+8], rax
0x180011750  mov     [rdi+58h], rcx
0x180011754  mov     rcx, [rdx]
0x180011757  mov     rax, [rdi+50h]
0x18001175b  mov     [rdx], rax
0x18001175e  mov     [rdi+50h], rcx
0x180011762  mov     rdi, [rbp+50h+var_B8]
0x180011766  xor     r13d, r13d
0x180011769  test    rdi, rdi
0x18001176c  jz      short loc_1800117AA
0x18001176e  or      r12, 0FFFFFFFFFFFFFFFFh
0x180011772  mov     eax, r12d
0x180011775  lock xadd [rdi+8], eax
0x18001177a  add     eax, r12d
0x18001177d  jnz     short loc_1800117AA
0x18001177f  mov     rax, [rdi]
0x180011782  mov     rcx, rdi
0x180011785  mov     rax, [rax]
0x180011788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001178d  mov     eax, r12d
0x180011790  lock xadd [rdi+0Ch], eax
0x180011795  add     eax, r12d
0x180011798  jnz     short loc_1800117AA
0x18001179a  mov     rax, [rdi]
0x18001179d  mov     rcx, rdi
0x1800117a0  mov     rax, [rax+8]
0x1800117a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117a9  nop
0x1800117aa  mov     rax, [rsi]
0x1800117ad  mov     rcx, [rax+48h]
0x1800117b1  mov     rax, [rcx-8]
0x1800117b5  mov     [rax+60h], r14d
0x1800117b9  mov     rcx, [rsp+150h+phkResult]; hKey
0x1800117be  test    rcx, rcx
0x1800117c1  jz      short loc_1800117C9
0x1800117c3  call    cs:__imp_RegCloseKey
0x1800117c9  inc     r14d
0x1800117cc  mov     edx, r14d; dwIndex
0x1800117cf  mov     [rsp+150h+lpcValues], r13; lpftLastWriteTime
0x1800117d4  mov     [rsp+150h+lpcbMaxClassLen], r13; lpcchClass
0x1800117d9  mov     [rsp+150h+lpcbMaxSubKeyLen], r13; lpClass
0x1800117de  mov     eax, [rsp+150h+cbMaxSubKeyLen]
0x1800117e2  mov     [rsp+150h+lpcSubKeys], r13; unsigned int
0x1800117e7  mov     [rsp+150h+cchName], eax
0x1800117eb  lea     r9, [rsp+150h+cchName]; lpcchName
0x1800117f0  mov     r8, rbx; lpName
0x1800117f3  mov     rcx, r15; hKey
0x1800117f6  call    cs:__imp_RegEnumKeyExW
0x1800117fc  cmp     eax, 103h
0x180011801  jnz     loc_180011636
0x180011807  mov     rcx, rbx
0x18001180a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180011810  mov     rax, rsi
0x180011813  mov     rcx, [rbp+50h+var_40]
0x180011817  xor     rcx, rsp; StackCookie
0x18001181a  call    __security_check_cookie
0x18001181f  mov     rbx, [rsp+150h+arg_18]
0x180011827  add     rsp, 120h
0x18001182e  pop     r15
0x180011830  pop     r14
0x180011832  pop     r13
0x180011834  pop     r12
0x180011836  pop     rdi
0x180011837  pop     rsi
0x180011838  pop     rbp
0x180011839  retn
0x18001183a  mov     r9d, eax; char *
0x18001183d  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180011844  mov     edx, 224h; void *
0x180011849  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001184f  mov     r9d, eax; char *
0x180011852  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180011859  mov     edx, 220h; void *
0x18001185e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180011864  mov     r9d, eax; char *
0x180011867  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001186e  mov     edx, 20Fh; void *
0x180011873  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180011879  call    ?_Xlen@?$vector@V?$shared_ptr@VCMvExtensionKey@@@std@@V?$allocator@V?$shared_ptr@VCMvExtensionKey@@@std@@@2@@std@@IEBAXXZ; std::vector<std::shared_ptr<CMvExtensionKey>>::_Xlen(void)
```
