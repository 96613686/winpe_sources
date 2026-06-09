# ProcessCommandLine(ushort *)

- ea: `0x1400084f8`
- end: `0x14000888d`
- name: `?ProcessCommandLine@@YAJPEAG@Z`
- size: `917`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14000e16c`

## callees

- `0x1400045f4`
- `0x140005c04`
- `0x1400072b8`
- `0x1400084f8`
- `0x140009524`
- `0x140009cd8`
- `0x14000a414`
- `0x14000def8`
- `0x14000df60`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1400085c9`
- `msvcrt!_wcsicmp` at `0x14000860e`
- `msvcrt!_wcsicmp` at `0x140008653`
- `msvcrt!_wcsicmp` at `0x140008698`
- `msvcrt!_wcsicmp` at `0x1400086dd`
- `msvcrt!_wcsicmp` at `0x1400085c9`
- `msvcrt!_wcsicmp` at `0x14000860e`
- `msvcrt!_wcsicmp` at `0x140008653`
- `msvcrt!_wcsicmp` at `0x140008698`
- `msvcrt!_wcsicmp` at `0x1400086dd`
- `OLEAUT32!__imp_SysStringLen` at `0x14000851b`
- `OLEAUT32!__imp_SysStringLen` at `0x14000851b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ProcessCommandLine(unsigned __int16 *a1)
{
  int v2; // r14d
  unsigned int v3; // r12d
  unsigned int v4; // esi
  const wchar_t **v5; // rax
  int v6; // ebx
  const wchar_t **v7; // rax
  int v8; // ebx
  const wchar_t **v9; // rax
  int v10; // ebx
  const wchar_t **v11; // rax
  int v12; // ebx
  const wchar_t **v13; // rax
  int v14; // ebx
  _QWORD *v15; // rax
  _BYTE *v16; // rdx
  _QWORD *v17; // rcx
  int *v18; // rbx
  __int64 v19; // rsi
  char v20; // al
  unsigned int v22; // [rsp+20h] [rbp-68h] BYREF
  __int64 v23; // [rsp+28h] [rbp-60h] BYREF
  __int64 v24; // [rsp+30h] [rbp-58h] BYREF
  __int64 v25; // [rsp+38h] [rbp-50h] BYREF
  __int64 v26; // [rsp+40h] [rbp-48h] BYREF
  __int64 v27; // [rsp+48h] [rbp-40h] BYREF
  __int64 v28; // [rsp+50h] [rbp-38h] BYREF
  __int64 v29[6]; // [rsp+58h] [rbp-30h] BYREF
  unsigned int v30; // [rsp+98h] [rbp+10h] BYREF
  char *v31; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v32; // [rsp+A8h] [rbp+20h] BYREF

  v2 = 0;
  v30 = 0;
  v3 = 0;
  if ( SysStringLen(a1) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_45cd2bf34f4235acf12ddc09e96c1ec9_Traceguids, a1);
    try
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v32,
        a1);
      v30 = 0;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
        &v32,
        &v31,
        L" ",
        &v30);
      while ( *(_WORD *)v31 )
      {
        v4 = *((_DWORD *)v31 - 4);
        v5 = (const wchar_t **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                                 &v31,
                                 &v23,
                                 v4);
        v6 = _wcsicmp(*v5, c_szCmdLineArgDockTop);
        ATL::CStringData::Release((ATL::CStringData *)(v23 - 24));
        if ( v6 )
        {
          v7 = (const wchar_t **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                                   &v31,
                                   &v24,
                                   v4);
          v8 = _wcsicmp(*v7, c_szCmdLineArgDockBottom);
          ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
          if ( v8 )
          {
            v9 = (const wchar_t **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                                     &v31,
                                     &v25,
                                     v4);
            v10 = _wcsicmp(*v9, c_szCmdLineArgNoUtilman);
            ATL::CStringData::Release((ATL::CStringData *)(v25 - 24));
            if ( v10 )
            {
              v11 = (const wchar_t **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                                        &v31,
                                        &v26,
                                        v4);
              v12 = _wcsicmp(*v11, c_szCmdLineArgPrimaryMonitor);
              ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
              if ( v12 )
              {
                v13 = (const wchar_t **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                                          &v31,
                                          &v27,
                                          v4);
                v14 = _wcsicmp(*v13, c_szCmdLineArgHardwareButtonLaunch);
                ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
                if ( v14 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                  {
                    v15 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                                      &v31,
                                      &v28,
                                      v4);
                    v2 |= 1u;
                    WPP_SF_S(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      11,
                      WPP_45cd2bf34f4235acf12ddc09e96c1ec9_Traceguids,
                      *v15);
                  }
                  if ( (v2 & 1) != 0 )
                  {
                    v2 &= ~1u;
                    ATL::CStringData::Release((ATL::CStringData *)(v28 - 24));
                  }
                }
                else
                {
                  byte_1400375B0 = 1;
                }
              }
              else
              {
                byte_1400375AF = 1;
              }
            }
            else
            {
              byte_1400375AE = 1;
            }
          }
          else
          {
            byte_1400375AD = 1;
          }
        }
        else
        {
          g_OSKCmdLineArgs = 1;
        }
        v16 = *(_BYTE **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                           &v32,
                           v29,
                           L" ",
                           &v30);
        v17 = v16 - 24;
        v18 = (int *)(v31 - 24);
        if ( v16 - 24 != v31 - 24 )
        {
          if ( v18[4] >= 0 && *v17 == *(_QWORD *)v18 )
          {
            v19 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v17);
            ATL::CStringData::Release((ATL::CStringData *)v18);
            v31 = (char *)(v19 + 24);
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v31, v16, *((_DWORD *)v16 - 4));
          }
        }
        ATL::CStringData::Release((ATL::CStringData *)(v29[0] - 24));
      }
      ATL::CStringData::Release((ATL::CStringData *)(v31 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v32 - 24));
    }
    catch ( ATL::CAtlException v22 )
    {
      v30 = v22;
      v3 = v22;
    }
    v20 = g_OSKCmdLineArgs;
    if ( g_OSKCmdLineArgs )
    {
      if ( byte_1400375AD )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_45cd2bf34f4235acf12ddc09e96c1ec9_Traceguids);
          v20 = g_OSKCmdLineArgs;
        }
        v3 = -2147024809;
      }
      if ( v20 )
        goto LABEL_36;
    }
    if ( byte_1400375AD )
LABEL_36:
      byte_1400375AE = 1;
  }
  return v3;
}

```

## disassembly

```asm
0x1400084f8  mov     [rsp+arg_0], rbx
0x1400084fd  push    rsi
0x1400084fe  push    rdi
0x1400084ff  push    r12
0x140008501  push    r14
0x140008503  push    r15
0x140008505  sub     rsp, 60h
0x140008509  mov     rbx, rcx
0x14000850c  xor     edi, edi
0x14000850e  mov     r14d, edi
0x140008511  mov     [rsp+88h+arg_8], edi
0x140008518  mov     r12d, edi
0x14000851b  call    cs:__imp_SysStringLen
0x140008521  test    eax, eax
0x140008523  jz      loc_140008875
0x140008529  lea     r15, WPP_GLOBAL_Control
0x140008530  mov     rcx, cs:WPP_GLOBAL_Control
0x140008537  cmp     rcx, r15
0x14000853a  jz      short loc_140008559
0x14000853c  test    byte ptr [rcx+1Ch], 10h
0x140008540  jz      short loc_140008559
0x140008542  lea     edx, [rdi+0Ah]
0x140008545  mov     r9, rbx
0x140008548  lea     r8, WPP_45cd2bf34f4235acf12ddc09e96c1ec9_Traceguids
0x14000854f  mov     rcx, [rcx+10h]
0x140008553  call    WPP_SF_S
0x140008558  nop
0x140008559  mov     rdx, rbx
0x14000855c  lea     rcx, [rsp+88h+arg_18]
0x140008564  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140008569  nop
0x14000856a  mov     [rsp+88h+arg_8], edi
0x140008571  lea     r9, [rsp+88h+arg_8]
0x140008579  lea     r8, asc_14002B110; " "
0x140008580  lea     rdx, [rsp+88h+arg_10]
0x140008588  lea     rcx, [rsp+88h+arg_18]
0x140008590  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x140008595  nop
0x140008596  mov     rcx, [rsp+88h+arg_10]
0x14000859e  cmp     [rcx], di
0x1400085a1  jz      loc_1400087EC
0x1400085a7  mov     esi, [rcx-10h]
0x1400085aa  mov     r8d, esi
0x1400085ad  lea     rdx, [rsp+88h+var_60]
0x1400085b2  lea     rcx, [rsp+88h+arg_10]
0x1400085ba  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x1400085bf  lea     rdx, ?c_szCmdLineArgDockTop@@3PAGA; "/docktop"
0x1400085c6  mov     rcx, [rax]; String1
0x1400085c9  call    cs:__imp__wcsicmp
0x1400085cf  mov     ebx, eax
0x1400085d1  mov     rcx, [rsp+88h+var_60]
0x1400085d6  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1400085da  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400085df  test    ebx, ebx
0x1400085e1  jnz     short loc_1400085EF
0x1400085e3  mov     cs:?g_OSKCmdLineArgs@@3UOSKCmdLineArgs@@A, 1; OSKCmdLineArgs g_OSKCmdLineArgs
0x1400085ea  jmp     loc_140008762
0x1400085ef  mov     r8d, esi
0x1400085f2  lea     rdx, [rsp+88h+var_58]
0x1400085f7  lea     rcx, [rsp+88h+arg_10]
0x1400085ff  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x140008604  lea     rdx, ?c_szCmdLineArgDockBottom@@3PAGA; "/dockbottom"
0x14000860b  mov     rcx, [rax]; String1
0x14000860e  call    cs:__imp__wcsicmp
0x140008614  mov     ebx, eax
0x140008616  mov     rcx, [rsp+88h+var_58]
0x14000861b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14000861f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140008624  test    ebx, ebx
0x140008626  jnz     short loc_140008634
0x140008628  mov     cs:byte_1400375AD, 1
0x14000862f  jmp     loc_140008762
0x140008634  mov     r8d, esi
0x140008637  lea     rdx, [rsp+88h+var_50]
0x14000863c  lea     rcx, [rsp+88h+arg_10]
0x140008644  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x140008649  lea     rdx, ?c_szCmdLineArgNoUtilman@@3PAGA; "/noutilman"
0x140008650  mov     rcx, [rax]; String1
0x140008653  call    cs:__imp__wcsicmp
0x140008659  mov     ebx, eax
0x14000865b  mov     rcx, [rsp+88h+var_50]
0x140008660  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140008664  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140008669  test    ebx, ebx
0x14000866b  jnz     short loc_140008679
0x14000866d  mov     cs:byte_1400375AE, 1
0x140008674  jmp     loc_140008762
0x140008679  mov     r8d, esi
0x14000867c  lea     rdx, [rsp+88h+var_48]
0x140008681  lea     rcx, [rsp+88h+arg_10]
0x140008689  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x14000868e  lea     rdx, ?c_szCmdLineArgPrimaryMonitor@@3PAGA; "/monitor"
0x140008695  mov     rcx, [rax]; String1
0x140008698  call    cs:__imp__wcsicmp
0x14000869e  mov     ebx, eax
0x1400086a0  mov     rcx, [rsp+88h+var_48]
0x1400086a5  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1400086a9  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400086ae  test    ebx, ebx
0x1400086b0  jnz     short loc_1400086BE
0x1400086b2  mov     cs:byte_1400375AF, 1
0x1400086b9  jmp     loc_140008762
0x1400086be  mov     r8d, esi
0x1400086c1  lea     rdx, [rsp+88h+var_40]
0x1400086c6  lea     rcx, [rsp+88h+arg_10]
0x1400086ce  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x1400086d3  lea     rdx, ?c_szCmdLineArgHardwareButtonLaunch@@3PAGA; "/hardwarebuttonlaunch"
0x1400086da  mov     rcx, [rax]; String1
0x1400086dd  call    cs:__imp__wcsicmp
0x1400086e3  mov     ebx, eax
0x1400086e5  mov     rcx, [rsp+88h+var_40]
0x1400086ea  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1400086ee  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400086f3  test    ebx, ebx
0x1400086f5  jnz     short loc_140008700
0x1400086f7  mov     cs:byte_1400375B0, 1
0x1400086fe  jmp     short loc_140008762
0x140008700  mov     rax, cs:WPP_GLOBAL_Control
0x140008707  cmp     rax, r15
0x14000870a  jz      short loc_14000874A
0x14000870c  test    byte ptr [rax+1Ch], 10h
0x140008710  jz      short loc_14000874A
0x140008712  mov     r8d, esi
0x140008715  lea     rdx, [rsp+88h+var_38]
0x14000871a  lea     rcx, [rsp+88h+arg_10]
0x140008722  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x140008727  or      r14d, 1
0x14000872b  mov     edx, 0Bh
0x140008730  mov     r9, [rax]
0x140008733  lea     r8, WPP_45cd2bf34f4235acf12ddc09e96c1ec9_Traceguids
0x14000873a  mov     rcx, cs:WPP_GLOBAL_Control
0x140008741  mov     rcx, [rcx+10h]
0x140008745  call    WPP_SF_S
0x14000874a  test    r14b, 1
0x14000874e  jz      short loc_140008762
0x140008750  and     r14d, 0FFFFFFFEh
0x140008754  mov     rcx, [rsp+88h+var_38]
0x140008759  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14000875d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140008762  lea     r9, [rsp+88h+arg_8]
0x14000876a  lea     r8, asc_14002B110; " "
0x140008771  lea     rdx, [rsp+88h+var_30]
0x140008776  lea     rcx, [rsp+88h+arg_18]
0x14000877e  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x140008783  nop
0x140008784  mov     rdx, [rax]
0x140008787  lea     rcx, [rdx-18h]
0x14000878b  mov     rbx, [rsp+88h+arg_10]
0x140008793  add     rbx, 0FFFFFFFFFFFFFFE8h
0x140008797  cmp     rcx, rbx
0x14000879a  jz      short loc_1400087D9
0x14000879c  cmp     [rbx+10h], edi
0x14000879f  jl      short loc_1400087C7
0x1400087a1  mov     rax, [rbx]
0x1400087a4  cmp     [rcx], rax
0x1400087a7  jnz     short loc_1400087C7
0x1400087a9  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1400087ae  mov     rsi, rax
0x1400087b1  mov     rcx, rbx; this
0x1400087b4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400087b9  lea     rax, [rsi+18h]
0x1400087bd  mov     [rsp+88h+arg_10], rax
0x1400087c5  jmp     short loc_1400087D9
0x1400087c7  mov     r8d, [rdx-10h]
0x1400087cb  lea     rcx, [rsp+88h+arg_10]
0x1400087d3  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400087d8  nop
0x1400087d9  mov     rcx, [rsp+88h+var_30]
0x1400087de  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1400087e2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400087e7  jmp     loc_140008596
0x1400087ec  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1400087f0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400087f5  nop
0x1400087f6  mov     rcx, [rsp+88h+arg_18]
0x1400087fe  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140008802  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140008807  nop
0x140008808  jmp     short loc_14000881B
0x14000880a  xor     edi, edi
0x14000880c  lea     r15, WPP_GLOBAL_Control
0x140008813  mov     r12d, [rsp+88h+arg_8]
0x14000881b  mov     al, cs:?g_OSKCmdLineArgs@@3UOSKCmdLineArgs@@A; OSKCmdLineArgs g_OSKCmdLineArgs
0x140008821  test    al, al
0x140008823  jz      short loc_140008865
0x140008825  cmp     cs:byte_1400375AD, dil
0x14000882c  jz      short loc_140008861
0x14000882e  mov     rcx, cs:WPP_GLOBAL_Control
0x140008835  cmp     rcx, r15
0x140008838  jz      short loc_14000885B
0x14000883a  test    byte ptr [rcx+1Ch], 10h
0x14000883e  jz      short loc_14000885B
0x140008840  mov     edx, 0Ch
0x140008845  lea     r8, WPP_45cd2bf34f4235acf12ddc09e96c1ec9_Traceguids
0x14000884c  mov     rcx, [rcx+10h]
0x140008850  call    WPP_SF_
0x140008855  mov     al, cs:?g_OSKCmdLineArgs@@3UOSKCmdLineArgs@@A; OSKCmdLineArgs g_OSKCmdLineArgs
0x14000885b  mov     r12d, 80070057h
0x140008861  test    al, al
0x140008863  jnz     short loc_14000886E
0x140008865  cmp     cs:byte_1400375AD, dil
0x14000886c  jz      short loc_140008875
0x14000886e  mov     cs:byte_1400375AE, 1
0x140008875  mov     eax, r12d
0x140008878  mov     rbx, [rsp+88h+arg_0]
0x140008880  add     rsp, 60h
0x140008884  pop     r15
0x140008886  pop     r14
0x140008888  pop     r12
0x14000888a  pop     rdi
0x14000888b  pop     rsi
0x14000888c  retn
```
