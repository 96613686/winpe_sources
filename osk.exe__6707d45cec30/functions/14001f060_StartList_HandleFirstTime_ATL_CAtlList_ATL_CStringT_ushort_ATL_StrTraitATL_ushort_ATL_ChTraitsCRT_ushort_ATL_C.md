# StartList::HandleFirstTime(ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CRegKey &)

- ea: `0x14001f060`
- end: `0x14001f4ea`
- name: `?HandleFirstTime@StartList@@AEAAJAEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@AEAVCRegKey@3@@Z`
- size: `1162`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14001f728`

## callees

- `0x140002de3`
- `0x1400045f4`
- `0x140004700`
- `0x140005c04`
- `0x140005c90`
- `0x140007e90`
- `0x140009524`
- `0x140009cd8`
- `0x14000def8`
- `0x14000df20`
- `0x1400170d8`
- `0x14001c508`
- `0x14001c8a8`
- `0x14001cb58`
- `0x14001dab0`
- `0x14001dc50`
- `0x14001eb04`
- `0x14001f060`
- `0x14001fe9c`
- `0x14002180c`
- `0x140025d70`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x14001f3a0`
- `KERNEL32!DeleteFileW` at `0x14001f3f5`
- `KERNEL32!DeleteFileW` at `0x14001f44a`
- `KERNEL32!DeleteFileW` at `0x14001f3a0`
- `KERNEL32!DeleteFileW` at `0x14001f3f5`
- `KERNEL32!DeleteFileW` at `0x14001f44a`
- `KERNEL32!GetFileAttributesW` at `0x14001f370`
- `KERNEL32!GetFileAttributesW` at `0x14001f3d1`
- `KERNEL32!GetFileAttributesW` at `0x14001f426`
- `KERNEL32!GetFileAttributesW` at `0x14001f370`
- `KERNEL32!GetFileAttributesW` at `0x14001f3d1`
- `KERNEL32!GetFileAttributesW` at `0x14001f426`

## string_xrefs

- `0x14001f18f`: `Configuration`
- `0x14001f0af`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall StartList::HandleFirstTime(__int64 a1, _QWORD *a2, _QWORD *a3, ATL::CRegKey *a4)
{
  unsigned int v7; // eax
  __int64 v8; // rcx
  int v9; // ebx
  const unsigned __int16 **Next; // rbx
  unsigned __int16 *v12; // rbx
  unsigned int v13; // r9d
  unsigned int v14; // eax
  signed int v15; // edi
  unsigned int v16; // eax
  ATL::CStringData *v17; // r15
  int *v18; // rdi
  __int64 v19; // rbx
  HKEY v20; // [rsp+30h] [rbp-D0h]
  unsigned int v21[2]; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR v22; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR v23; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v25; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v26[3]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v27; // [rsp+80h] [rbp-80h] BYREF
  __int64 v28; // [rsp+90h] [rbp-70h]
  __int128 v29; // [rsp+98h] [rbp-68h]
  int v30; // [rsp+A8h] [rbp-58h]
  unsigned __int16 v31[264]; // [rsp+B0h] [rbp-50h] BYREF

  v7 = ATL::CRegKey::Create(
         a4,
         HKEY_CURRENT_USER,
         StartList::_accessibilityKeyString,
         (unsigned __int16 *)a4,
         0,
         3u,
         v20,
         v21);
  v9 = v7;
  if ( !v7 )
  {
    v27 = 0;
    v28 = 0;
    v29 = 0;
    v30 = 10;
    *(_QWORD *)v21 = *a2;
    while ( *(_QWORD *)v21 )
    {
      Next = (const unsigned __int16 **)ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GetNext(
                                          v8,
                                          v21);
      if ( *((_DWORD *)Accommodation::Open(*Next) + 20) != 1 )
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
          &v27,
          *Next);
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v25);
    StartList::BuildConfigString(&v25, &v27);
    v12 = v25;
    v14 = ATL::CRegKey::SetStringValue(a4, StartList::_configuration, v25, v13);
    v15 = v14;
    if ( v14 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, v14);
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
    }
    else
    {
      memset(v26, 0, sizeof(v26));
      v16 = ATL::CRegKey::Open(
              (ATL::CRegKey *)v26,
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Shell Folders",
              0x20019u);
      v15 = v16;
      if ( !v16 )
      {
        memset_0(v31, 0, 0x208u);
        v21[0] = 260;
        ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v26, L"Startup", v31, v21);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &lpFileName,
          v31);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v23,
          v31);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v22,
          v31);
        ATL::CSimpleStringT<unsigned short,0>::Append(&lpFileName, L"\\On-Screen Keyboard.lnk", 23);
        ATL::CSimpleStringT<unsigned short,0>::Append(&v23, L"\\Narrator.lnk", 13);
        ATL::CSimpleStringT<unsigned short,0>::Append(&v22, L"\\Magnifier.lnk", 14);
        v17 = (ATL::CStringData *)(v12 - 12);
        v18 = (int *)(*a3 - 24LL);
        if ( v12 - 12 != (unsigned __int16 *)v18 )
        {
          if ( v18[4] >= 0 && *(_QWORD *)v17 == *(_QWORD *)v18 )
          {
            v19 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v12 - 12);
            ATL::CStringData::Release((ATL::CStringData *)v18);
            *a3 = v19 + 24;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(a3, v12, *((unsigned int *)v12 - 4));
          }
        }
        if ( GetFileAttributesW(lpFileName) != -1 )
        {
          ATL::CSimpleStringT<unsigned short,0>::Append(a3, L",osk", 4);
          DeleteFileW(lpFileName);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids);
        }
        if ( GetFileAttributesW(v23) != -1 )
        {
          ATL::CSimpleStringT<unsigned short,0>::Append(a3, L",Narrator", 9);
          DeleteFileW(v23);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids);
        }
        if ( GetFileAttributesW(v22) != -1 )
        {
          ATL::CSimpleStringT<unsigned short,0>::Append(a3, L",magnifierpane", 14);
          DeleteFileW(v22);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids);
        }
        ATL::CStringData::Release((ATL::CStringData *)(v22 - 12));
        ATL::CStringData::Release((ATL::CStringData *)(v23 - 12));
        ATL::CStringData::Release((ATL::CStringData *)(lpFileName - 12));
        ATL::CRegKey::Close((ATL::CRegKey *)v26);
        ATL::CStringData::Release(v17);
        v15 = 0;
        goto LABEL_44;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, v16);
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
      ATL::CRegKey::Close((ATL::CRegKey *)v26);
    }
    ATL::CStringData::Release((ATL::CStringData *)(v12 - 12));
LABEL_44:
    ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(&v27);
    return (unsigned int)v15;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, v7);
  if ( v9 > 0 )
    return (unsigned __int16)v9 | 0x80070000;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14001f060  mov     [rsp-8+arg_0], rbx
0x14001f065  push    rbp
0x14001f066  push    rsi
0x14001f067  push    rdi
0x14001f068  push    r14
0x14001f06a  push    r15
0x14001f06c  lea     rbp, [rsp-1D0h]
0x14001f074  sub     rsp, 2D0h
0x14001f07b  mov     rax, cs:__security_cookie
0x14001f082  xor     rax, rsp
0x14001f085  mov     [rbp+1F0h+var_30], rax
0x14001f08c  mov     rdi, r9
0x14001f08f  mov     r14, r8
0x14001f092  mov     rsi, rdx
0x14001f095  lea     rax, [rsp+2F0h+var_2B0]
0x14001f09a  mov     [rsp+2F0h+var_2B8], rax; unsigned int *
0x14001f09f  mov     [rsp+2F0h+var_2C8], 3; REGSAM
0x14001f0a7  mov     [rsp+2F0h+var_2D0], 0; DWORD
0x14001f0af  lea     r8, ?_accessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14001f0b6  mov     r15, 0FFFFFFFF80000001h
0x14001f0bd  mov     rdx, r15; hKey
0x14001f0c0  mov     rcx, r9; this
0x14001f0c3  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x14001f0c8  mov     ebx, eax
0x14001f0ca  test    eax, eax
0x14001f0cc  jz      short loc_14001F113
0x14001f0ce  lea     rsi, WPP_GLOBAL_Control
0x14001f0d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f0dc  cmp     rcx, rsi
0x14001f0df  jz      short loc_14001F0FF
0x14001f0e1  test    byte ptr [rcx+1Ch], 8
0x14001f0e5  jz      short loc_14001F0FF
0x14001f0e7  mov     edx, 29h ; ')'
0x14001f0ec  mov     r9d, eax
0x14001f0ef  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14001f0f6  mov     rcx, [rcx+10h]
0x14001f0fa  call    WPP_SF_d
0x14001f0ff  test    ebx, ebx
0x14001f101  jle     short loc_14001F10C
0x14001f103  movzx   ebx, bx
0x14001f106  or      ebx, 80070000h
0x14001f10c  mov     eax, ebx
0x14001f10e  jmp     loc_14001F4C4
0x14001f113  xorps   xmm0, xmm0
0x14001f116  movdqu  [rbp+1F0h+var_270], xmm0
0x14001f11b  mov     [rbp+1F0h+var_260], 0
0x14001f123  xorps   xmm1, xmm1
0x14001f126  movdqu  [rbp+1F0h+var_258], xmm1
0x14001f12b  mov     [rbp+1F0h+var_248], 0Ah
0x14001f132  mov     rax, [rsi]
0x14001f135  mov     qword ptr [rsp+2F0h+var_2B0], rax
0x14001f13a  test    rax, rax
0x14001f13d  jz      short loc_14001F16E
0x14001f13f  lea     rdx, [rsp+2F0h+var_2B0]
0x14001f144  call    ?GetNext@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAPEAU__POSITION@@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GetNext(__POSITION * &)
0x14001f149  mov     rbx, rax
0x14001f14c  mov     rcx, [rax]; unsigned __int16 *
0x14001f14f  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x14001f154  cmp     dword ptr [rax+50h], 1
0x14001f158  jz      short loc_14001F166
0x14001f15a  mov     rdx, [rbx]
0x14001f15d  lea     rcx, [rbp+1F0h+var_270]
0x14001f161  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x14001f166  cmp     qword ptr [rsp+2F0h+var_2B0], 0
0x14001f16c  jnz     short loc_14001F13F
0x14001f16e  lea     rcx, [rsp+2F0h+var_290]
0x14001f173  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x14001f178  nop
0x14001f179  lea     rdx, [rbp+1F0h+var_270]
0x14001f17d  lea     rcx, [rsp+2F0h+var_290]
0x14001f182  call    ?BuildConfigString@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x14001f187  mov     rbx, [rsp+2F0h+var_290]
0x14001f18c  mov     r8, rbx; unsigned __int16 *
0x14001f18f  lea     rdx, ?_configuration@StartList@@0PAGA; "Configuration"
0x14001f196  mov     rcx, rdi; this
0x14001f199  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x14001f19e  mov     edi, eax
0x14001f1a0  test    eax, eax
0x14001f1a2  jz      short loc_14001F1EB
0x14001f1a4  lea     rsi, WPP_GLOBAL_Control
0x14001f1ab  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f1b2  cmp     rcx, rsi
0x14001f1b5  jz      short loc_14001F1D5
0x14001f1b7  test    byte ptr [rcx+1Ch], 8
0x14001f1bb  jz      short loc_14001F1D5
0x14001f1bd  mov     edx, 2Ah ; '*'
0x14001f1c2  mov     r9d, eax
0x14001f1c5  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14001f1cc  mov     rcx, [rcx+10h]
0x14001f1d0  call    WPP_SF_d
0x14001f1d5  test    edi, edi
0x14001f1d7  jle     loc_14001F26F
0x14001f1dd  movzx   edi, di
0x14001f1e0  or      edi, 80070000h
0x14001f1e6  jmp     loc_14001F26F
0x14001f1eb  mov     [rsp+2F0h+var_288], 0
0x14001f1f4  mov     [rsp+2F0h+var_280], 0
0x14001f1fd  mov     [rsp+2F0h+var_278], 0
0x14001f206  mov     r9d, 20019h; unsigned int
0x14001f20c  lea     r8, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14001f213  mov     rdx, r15; hKey
0x14001f216  lea     rcx, [rsp+2F0h+var_288]; this
0x14001f21b  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14001f220  mov     edi, eax
0x14001f222  test    eax, eax
0x14001f224  jz      short loc_14001F27D
0x14001f226  lea     rsi, WPP_GLOBAL_Control
0x14001f22d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f234  cmp     rcx, rsi
0x14001f237  jz      short loc_14001F257
0x14001f239  test    byte ptr [rcx+1Ch], 8
0x14001f23d  jz      short loc_14001F257
0x14001f23f  mov     edx, 2Bh ; '+'
0x14001f244  mov     r9d, eax
0x14001f247  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14001f24e  mov     rcx, [rcx+10h]
0x14001f252  call    WPP_SF_d
0x14001f257  test    edi, edi
0x14001f259  jle     short loc_14001F264
0x14001f25b  movzx   edi, di
0x14001f25e  or      edi, 80070000h
0x14001f264  lea     rcx, [rsp+2F0h+var_288]; this
0x14001f269  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001f26e  nop
0x14001f26f  lea     rcx, [rbx-18h]; this
0x14001f273  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001f278  jmp     loc_14001F4B9
0x14001f27d  xor     edx, edx; Val
0x14001f27f  mov     r8d, 208h; Size
0x14001f285  lea     rcx, [rbp+1F0h+var_240]; void *
0x14001f289  call    memset_0
0x14001f28e  mov     [rsp+2F0h+var_2B0], 104h
0x14001f296  lea     r9, [rsp+2F0h+var_2B0]; unsigned int *
0x14001f29b  lea     r8, [rbp+1F0h+var_240]; unsigned __int16 *
0x14001f29f  lea     rdx, aStartup; "Startup"
0x14001f2a6  lea     rcx, [rsp+2F0h+var_288]; this
0x14001f2ab  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x14001f2b0  lea     rdx, [rbp+1F0h+var_240]
0x14001f2b4  lea     rcx, [rsp+2F0h+lpFileName]
0x14001f2b9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001f2be  nop
0x14001f2bf  lea     rdx, [rbp+1F0h+var_240]
0x14001f2c3  lea     rcx, [rsp+2F0h+var_2A0]
0x14001f2c8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001f2cd  nop
0x14001f2ce  lea     rdx, [rbp+1F0h+var_240]
0x14001f2d2  lea     rcx, [rsp+2F0h+var_2A8]
0x14001f2d7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001f2dc  nop
0x14001f2dd  mov     r8d, 17h
0x14001f2e3  lea     rdx, aOnScreenKeyboa; "\\On-Screen Keyboard.lnk"
0x14001f2ea  lea     rcx, [rsp+2F0h+lpFileName]
0x14001f2ef  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14001f2f4  mov     r8d, 0Dh
0x14001f2fa  lea     rdx, aNarratorLnk; "\\Narrator.lnk"
0x14001f301  lea     rcx, [rsp+2F0h+var_2A0]
0x14001f306  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14001f30b  mov     r8d, 0Eh
0x14001f311  lea     rdx, aMagnifierLnk; "\\Magnifier.lnk"
0x14001f318  lea     rcx, [rsp+2F0h+var_2A8]
0x14001f31d  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14001f322  lea     r15, [rbx-18h]
0x14001f326  mov     rdi, [r14]
0x14001f329  add     rdi, 0FFFFFFFFFFFFFFE8h
0x14001f32d  cmp     r15, rdi
0x14001f330  jz      short loc_14001F36B
0x14001f332  cmp     dword ptr [rdi+10h], 0
0x14001f336  jl      short loc_14001F35C
0x14001f338  mov     rax, [rdi]
0x14001f33b  cmp     [r15], rax
0x14001f33e  jnz     short loc_14001F35C
0x14001f340  mov     rcx, r15
0x14001f343  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14001f348  mov     rbx, rax
0x14001f34b  mov     rcx, rdi; this
0x14001f34e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001f353  lea     rax, [rbx+18h]
0x14001f357  mov     [r14], rax
0x14001f35a  jmp     short loc_14001F36B
0x14001f35c  mov     r8d, [rbx-10h]
0x14001f360  mov     rdx, rbx
0x14001f363  mov     rcx, r14
0x14001f366  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001f36b  mov     rcx, [rsp+2F0h+lpFileName]; lpFileName
0x14001f370  call    cs:__imp_GetFileAttributesW
0x14001f376  mov     bl, 10h
0x14001f378  lea     rsi, WPP_GLOBAL_Control
0x14001f37f  or      edi, 0FFFFFFFFh
0x14001f382  cmp     eax, edi
0x14001f384  jz      short loc_14001F3CC
0x14001f386  mov     r8d, 4
0x14001f38c  lea     rdx, aOsk_0; ",osk"
0x14001f393  mov     rcx, r14
0x14001f396  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14001f39b  mov     rcx, [rsp+2F0h+lpFileName]; lpFileName
0x14001f3a0  call    cs:__imp_DeleteFileW
0x14001f3a6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f3ad  cmp     rcx, rsi
0x14001f3b0  jz      short loc_14001F3CC
0x14001f3b2  test    [rcx+1Ch], bl
0x14001f3b5  jz      short loc_14001F3CC
0x14001f3b7  mov     edx, 2Ch ; ','
0x14001f3bc  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14001f3c3  mov     rcx, [rcx+10h]
0x14001f3c7  call    WPP_SF_
0x14001f3cc  mov     rcx, [rsp+2F0h+var_2A0]; lpFileName
0x14001f3d1  call    cs:__imp_GetFileAttributesW
0x14001f3d7  cmp     eax, edi
0x14001f3d9  jz      short loc_14001F421
0x14001f3db  mov     r8d, 9
0x14001f3e1  lea     rdx, aNarrator; ",Narrator"
0x14001f3e8  mov     rcx, r14
0x14001f3eb  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14001f3f0  mov     rcx, [rsp+2F0h+var_2A0]; lpFileName
0x14001f3f5  call    cs:__imp_DeleteFileW
0x14001f3fb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f402  cmp     rcx, rsi
0x14001f405  jz      short loc_14001F421
0x14001f407  test    [rcx+1Ch], bl
0x14001f40a  jz      short loc_14001F421
0x14001f40c  mov     edx, 2Dh ; '-'
0x14001f411  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14001f418  mov     rcx, [rcx+10h]
0x14001f41c  call    WPP_SF_
0x14001f421  mov     rcx, [rsp+2F0h+var_2A8]; lpFileName
0x14001f426  call    cs:__imp_GetFileAttributesW
0x14001f42c  cmp     eax, edi
0x14001f42e  jz      short loc_14001F477
0x14001f430  mov     r8d, 0Eh
0x14001f436  lea     rdx, aMagnifierpane_0; ",magnifierpane"
0x14001f43d  mov     rcx, r14
0x14001f440  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14001f445  mov     rcx, [rsp+2F0h+var_2A8]; lpFileName
0x14001f44a  call    cs:__imp_DeleteFileW
0x14001f450  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f457  cmp     rcx, rsi
0x14001f45a  jz      short loc_14001F477
0x14001f45c  test    [rcx+1Ch], bl
0x14001f45f  jz      short loc_14001F477
0x14001f461  mov     edx, 2Eh ; '.'
0x14001f466  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14001f46d  mov     rcx, [rcx+10h]
0x14001f471  call    WPP_SF_
0x14001f476  nop
0x14001f477  mov     rcx, [rsp+2F0h+var_2A8]
0x14001f47c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001f480  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001f485  nop
0x14001f486  mov     rcx, [rsp+2F0h+var_2A0]
0x14001f48b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001f48f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001f494  nop
0x14001f495  mov     rcx, [rsp+2F0h+lpFileName]
0x14001f49a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001f49e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001f4a3  nop
0x14001f4a4  lea     rcx, [rsp+2F0h+var_288]; this
0x14001f4a9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001f4ae  nop
0x14001f4af  mov     rcx, r15; this
0x14001f4b2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001f4b7  xor     edi, edi
0x14001f4b9  lea     rcx, [rbp+1F0h+var_270]
0x14001f4bd  call    ?RemoveAll@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x14001f4c2  mov     eax, edi
0x14001f4c4  mov     rcx, [rbp+1F0h+var_30]
0x14001f4cb  xor     rcx, rsp; StackCookie
0x14001f4ce  call    __security_check_cookie
0x14001f4d3  mov     rbx, [rsp+2F0h+arg_0]
0x14001f4db  add     rsp, 2D0h
0x14001f4e2  pop     r15
0x14001f4e4  pop     r14
0x14001f4e6  pop     rdi
0x14001f4e7  pop     rsi
0x14001f4e8  pop     rbp
0x14001f4e9  retn
```
