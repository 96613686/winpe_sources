# StartList::HandleFirstTime(ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CRegKey &)

- ea: `0x1400c1e60`
- end: `0x1400c22ea`
- name: `?HandleFirstTime@StartList@@AEAAJAEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@AEAVCRegKey@3@@Z`
- size: `1162`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *, ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1401bb3b0`

## callees

- `0x1400c1e60`
- `0x1400c25ec`
- `0x1400c261c`
- `0x1400c2688`
- `0x1400d9ebc`
- `0x1401040e0`
- `0x140104ce0`
- `0x14015d848`
- `0x140187e78`
- `0x14018f468`
- `0x1401b21e8`
- `0x1401b88d0`
- `0x1401b893c`
- `0x1401b8a24`
- `0x1401b8aec`
- `0x1401b8f94`
- `0x1401b92a0`
- `0x1401b9574`
- `0x1401b9cb4`
- `0x1401b9fc4`
- `0x1401ba86c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400c21a0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400c21f5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400c224a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400c21a0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400c21f5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400c224a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400c2170`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400c21d1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400c2226`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400c2170`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400c21d1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400c2226`

## string_xrefs

- `0x1400c1eaf`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility`
- `0x1400c1f8f`: `Configuration`

## pseudocode

```c
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
0x1400c1e60  mov     [rsp-8+arg_0], rbx
0x1400c1e65  push    rbp
0x1400c1e66  push    rsi
0x1400c1e67  push    rdi
0x1400c1e68  push    r14
0x1400c1e6a  push    r15
0x1400c1e6c  lea     rbp, [rsp-1D0h]
0x1400c1e74  sub     rsp, 2D0h
0x1400c1e7b  mov     rax, cs:__security_cookie
0x1400c1e82  xor     rax, rsp
0x1400c1e85  mov     [rbp+1F0h+var_30], rax
0x1400c1e8c  mov     rdi, r9
0x1400c1e8f  mov     r14, r8
0x1400c1e92  mov     rsi, rdx
0x1400c1e95  lea     rax, [rsp+2F0h+var_2B0]
0x1400c1e9a  mov     [rsp+2F0h+var_2B8], rax; unsigned int *
0x1400c1e9f  mov     [rsp+2F0h+var_2C8], 3; REGSAM
0x1400c1ea7  mov     [rsp+2F0h+var_2D0], 0; DWORD
0x1400c1eaf  lea     r8, ?_accessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400c1eb6  mov     r15, 0FFFFFFFF80000001h
0x1400c1ebd  mov     rdx, r15; hKey
0x1400c1ec0  mov     rcx, r9; this
0x1400c1ec3  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1400c1ec8  mov     ebx, eax
0x1400c1eca  test    eax, eax
0x1400c1ecc  jz      short loc_1400C1F13
0x1400c1ece  lea     rsi, WPP_GLOBAL_Control
0x1400c1ed5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c1edc  cmp     rcx, rsi
0x1400c1edf  jz      short loc_1400C1EFF
0x1400c1ee1  test    byte ptr [rcx+1Ch], 8
0x1400c1ee5  jz      short loc_1400C1EFF
0x1400c1ee7  mov     edx, 29h ; ')'
0x1400c1eec  mov     r9d, eax
0x1400c1eef  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x1400c1ef6  mov     rcx, [rcx+10h]
0x1400c1efa  call    WPP_SF_d
0x1400c1eff  test    ebx, ebx
0x1400c1f01  jle     short loc_1400C1F0C
0x1400c1f03  movzx   ebx, bx
0x1400c1f06  or      ebx, 80070000h
0x1400c1f0c  mov     eax, ebx
0x1400c1f0e  jmp     loc_1400C22C4
0x1400c1f13  xorps   xmm0, xmm0
0x1400c1f16  movdqu  [rbp+1F0h+var_270], xmm0
0x1400c1f1b  mov     [rbp+1F0h+var_260], 0
0x1400c1f23  xorps   xmm1, xmm1
0x1400c1f26  movdqu  [rbp+1F0h+var_258], xmm1
0x1400c1f2b  mov     [rbp+1F0h+var_248], 0Ah
0x1400c1f32  mov     rax, [rsi]
0x1400c1f35  mov     qword ptr [rsp+2F0h+var_2B0], rax
0x1400c1f3a  test    rax, rax
0x1400c1f3d  jz      short loc_1400C1F6E
0x1400c1f3f  lea     rdx, [rsp+2F0h+var_2B0]
0x1400c1f44  call    ?GetNext@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAPEAU__POSITION@@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GetNext(__POSITION * &)
0x1400c1f49  mov     rbx, rax
0x1400c1f4c  mov     rcx, [rax]; unsigned __int16 *
0x1400c1f4f  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x1400c1f54  cmp     dword ptr [rax+50h], 1
0x1400c1f58  jz      short loc_1400C1F66
0x1400c1f5a  mov     rdx, [rbx]
0x1400c1f5d  lea     rcx, [rbp+1F0h+var_270]
0x1400c1f61  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x1400c1f66  cmp     qword ptr [rsp+2F0h+var_2B0], 0
0x1400c1f6c  jnz     short loc_1400C1F3F
0x1400c1f6e  lea     rcx, [rsp+2F0h+var_290]
0x1400c1f73  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1400c1f78  nop
0x1400c1f79  lea     rdx, [rbp+1F0h+var_270]
0x1400c1f7d  lea     rcx, [rsp+2F0h+var_290]
0x1400c1f82  call    ?BuildConfigString@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x1400c1f87  mov     rbx, [rsp+2F0h+var_290]
0x1400c1f8c  mov     r8, rbx; unsigned __int16 *
0x1400c1f8f  lea     rdx, ?_configuration@StartList@@0PAGA; "Configuration"
0x1400c1f96  mov     rcx, rdi; this
0x1400c1f99  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x1400c1f9e  mov     edi, eax
0x1400c1fa0  test    eax, eax
0x1400c1fa2  jz      short loc_1400C1FEB
0x1400c1fa4  lea     rsi, WPP_GLOBAL_Control
0x1400c1fab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c1fb2  cmp     rcx, rsi
0x1400c1fb5  jz      short loc_1400C1FD5
0x1400c1fb7  test    byte ptr [rcx+1Ch], 8
0x1400c1fbb  jz      short loc_1400C1FD5
0x1400c1fbd  mov     edx, 2Ah ; '*'
0x1400c1fc2  mov     r9d, eax
0x1400c1fc5  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x1400c1fcc  mov     rcx, [rcx+10h]
0x1400c1fd0  call    WPP_SF_d
0x1400c1fd5  test    edi, edi
0x1400c1fd7  jle     loc_1400C206F
0x1400c1fdd  movzx   edi, di
0x1400c1fe0  or      edi, 80070000h
0x1400c1fe6  jmp     loc_1400C206F
0x1400c1feb  mov     [rsp+2F0h+var_288], 0
0x1400c1ff4  mov     [rsp+2F0h+var_280], 0
0x1400c1ffd  mov     [rsp+2F0h+var_278], 0
0x1400c2006  mov     r9d, 20019h; unsigned int
0x1400c200c  lea     r8, aSoftwareMicros_101; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400c2013  mov     rdx, r15; hKey
0x1400c2016  lea     rcx, [rsp+2F0h+var_288]; this
0x1400c201b  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1400c2020  mov     edi, eax
0x1400c2022  test    eax, eax
0x1400c2024  jz      short loc_1400C207D
0x1400c2026  lea     rsi, WPP_GLOBAL_Control
0x1400c202d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c2034  cmp     rcx, rsi
0x1400c2037  jz      short loc_1400C2057
0x1400c2039  test    byte ptr [rcx+1Ch], 8
0x1400c203d  jz      short loc_1400C2057
0x1400c203f  mov     edx, 2Bh ; '+'
0x1400c2044  mov     r9d, eax
0x1400c2047  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x1400c204e  mov     rcx, [rcx+10h]
0x1400c2052  call    WPP_SF_d
0x1400c2057  test    edi, edi
0x1400c2059  jle     short loc_1400C2064
0x1400c205b  movzx   edi, di
0x1400c205e  or      edi, 80070000h
0x1400c2064  lea     rcx, [rsp+2F0h+var_288]; this
0x1400c2069  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400c206e  nop
0x1400c206f  lea     rcx, [rbx-18h]; this
0x1400c2073  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400c2078  jmp     loc_1400C22B9
0x1400c207d  xor     edx, edx; Val
0x1400c207f  mov     r8d, 208h; Size
0x1400c2085  lea     rcx, [rbp+1F0h+var_240]; void *
0x1400c2089  call    memset_0
0x1400c208e  mov     [rsp+2F0h+var_2B0], 104h
0x1400c2096  lea     r9, [rsp+2F0h+var_2B0]; unsigned int *
0x1400c209b  lea     r8, [rbp+1F0h+var_240]; unsigned __int16 *
0x1400c209f  lea     rdx, aStartup; "Startup"
0x1400c20a6  lea     rcx, [rsp+2F0h+var_288]; this
0x1400c20ab  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x1400c20b0  lea     rdx, [rbp+1F0h+var_240]
0x1400c20b4  lea     rcx, [rsp+2F0h+lpFileName]
0x1400c20b9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400c20be  nop
0x1400c20bf  lea     rdx, [rbp+1F0h+var_240]
0x1400c20c3  lea     rcx, [rsp+2F0h+var_2A0]
0x1400c20c8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400c20cd  nop
0x1400c20ce  lea     rdx, [rbp+1F0h+var_240]
0x1400c20d2  lea     rcx, [rsp+2F0h+var_2A8]
0x1400c20d7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400c20dc  nop
0x1400c20dd  mov     r8d, 17h
0x1400c20e3  lea     rdx, aOnScreenKeyboa; "\\On-Screen Keyboard.lnk"
0x1400c20ea  lea     rcx, [rsp+2F0h+lpFileName]
0x1400c20ef  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1400c20f4  mov     r8d, 0Dh
0x1400c20fa  lea     rdx, aNarratorLnk; "\\Narrator.lnk"
0x1400c2101  lea     rcx, [rsp+2F0h+var_2A0]
0x1400c2106  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1400c210b  mov     r8d, 0Eh
0x1400c2111  lea     rdx, aMagnifierLnk; "\\Magnifier.lnk"
0x1400c2118  lea     rcx, [rsp+2F0h+var_2A8]
0x1400c211d  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1400c2122  lea     r15, [rbx-18h]
0x1400c2126  mov     rdi, [r14]
0x1400c2129  add     rdi, 0FFFFFFFFFFFFFFE8h
0x1400c212d  cmp     r15, rdi
0x1400c2130  jz      short loc_1400C216B
0x1400c2132  cmp     dword ptr [rdi+10h], 0
0x1400c2136  jl      short loc_1400C215C
0x1400c2138  mov     rax, [rdi]
0x1400c213b  cmp     [r15], rax
0x1400c213e  jnz     short loc_1400C215C
0x1400c2140  mov     rcx, r15
0x1400c2143  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1400c2148  mov     rbx, rax
0x1400c214b  mov     rcx, rdi; this
0x1400c214e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400c2153  lea     rax, [rbx+18h]
0x1400c2157  mov     [r14], rax
0x1400c215a  jmp     short loc_1400C216B
0x1400c215c  mov     r8d, [rbx-10h]
0x1400c2160  mov     rdx, rbx
0x1400c2163  mov     rcx, r14
0x1400c2166  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400c216b  mov     rcx, [rsp+2F0h+lpFileName]; lpFileName
0x1400c2170  call    cs:__imp_GetFileAttributesW
0x1400c2176  mov     bl, 10h
0x1400c2178  lea     rsi, WPP_GLOBAL_Control
0x1400c217f  or      edi, 0FFFFFFFFh
0x1400c2182  cmp     eax, edi
0x1400c2184  jz      short loc_1400C21CC
0x1400c2186  mov     r8d, 4
0x1400c218c  lea     rdx, aOsk; ",osk"
0x1400c2193  mov     rcx, r14
0x1400c2196  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1400c219b  mov     rcx, [rsp+2F0h+lpFileName]; lpFileName
0x1400c21a0  call    cs:__imp_DeleteFileW
0x1400c21a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c21ad  cmp     rcx, rsi
0x1400c21b0  jz      short loc_1400C21CC
0x1400c21b2  test    [rcx+1Ch], bl
0x1400c21b5  jz      short loc_1400C21CC
0x1400c21b7  mov     edx, 2Ch ; ','
0x1400c21bc  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x1400c21c3  mov     rcx, [rcx+10h]
0x1400c21c7  call    WPP_SF_
0x1400c21cc  mov     rcx, [rsp+2F0h+var_2A0]; lpFileName
0x1400c21d1  call    cs:__imp_GetFileAttributesW
0x1400c21d7  cmp     eax, edi
0x1400c21d9  jz      short loc_1400C2221
0x1400c21db  mov     r8d, 9
0x1400c21e1  lea     rdx, aNarrator; ",Narrator"
0x1400c21e8  mov     rcx, r14
0x1400c21eb  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1400c21f0  mov     rcx, [rsp+2F0h+var_2A0]; lpFileName
0x1400c21f5  call    cs:__imp_DeleteFileW
0x1400c21fb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c2202  cmp     rcx, rsi
0x1400c2205  jz      short loc_1400C2221
0x1400c2207  test    [rcx+1Ch], bl
0x1400c220a  jz      short loc_1400C2221
0x1400c220c  mov     edx, 2Dh ; '-'
0x1400c2211  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x1400c2218  mov     rcx, [rcx+10h]
0x1400c221c  call    WPP_SF_
0x1400c2221  mov     rcx, [rsp+2F0h+var_2A8]; lpFileName
0x1400c2226  call    cs:__imp_GetFileAttributesW
0x1400c222c  cmp     eax, edi
0x1400c222e  jz      short loc_1400C2277
0x1400c2230  mov     r8d, 0Eh
0x1400c2236  lea     rdx, aMagnifierpane; ",magnifierpane"
0x1400c223d  mov     rcx, r14
0x1400c2240  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1400c2245  mov     rcx, [rsp+2F0h+var_2A8]; lpFileName
0x1400c224a  call    cs:__imp_DeleteFileW
0x1400c2250  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c2257  cmp     rcx, rsi
0x1400c225a  jz      short loc_1400C2277
0x1400c225c  test    [rcx+1Ch], bl
0x1400c225f  jz      short loc_1400C2277
0x1400c2261  mov     edx, 2Eh ; '.'
0x1400c2266  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x1400c226d  mov     rcx, [rcx+10h]
0x1400c2271  call    WPP_SF_
0x1400c2276  nop
0x1400c2277  mov     rcx, [rsp+2F0h+var_2A8]
0x1400c227c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1400c2280  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400c2285  nop
0x1400c2286  mov     rcx, [rsp+2F0h+var_2A0]
0x1400c228b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1400c228f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400c2294  nop
0x1400c2295  mov     rcx, [rsp+2F0h+lpFileName]
0x1400c229a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1400c229e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400c22a3  nop
0x1400c22a4  lea     rcx, [rsp+2F0h+var_288]; this
0x1400c22a9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400c22ae  nop
0x1400c22af  mov     rcx, r15; this
0x1400c22b2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400c22b7  xor     edi, edi
0x1400c22b9  lea     rcx, [rbp+1F0h+var_270]
0x1400c22bd  call    ?RemoveAll@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x1400c22c2  mov     eax, edi
0x1400c22c4  mov     rcx, [rbp+1F0h+var_30]
0x1400c22cb  xor     rcx, rsp; StackCookie
0x1400c22ce  call    __security_check_cookie
0x1400c22d3  mov     rbx, [rsp+2F0h+arg_0]
0x1400c22db  add     rsp, 2D0h
0x1400c22e2  pop     r15
0x1400c22e4  pop     r14
0x1400c22e6  pop     rdi
0x1400c22e7  pop     rsi
0x1400c22e8  pop     rbp
0x1400c22e9  retn
```
