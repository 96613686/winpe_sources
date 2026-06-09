# StartList::HandleFirstTime(ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CRegKey &)

- ea: `0x1400c860c`
- end: `0x1400c8abb`
- name: `?HandleFirstTime@StartList@@AEAAJAEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@AEAVCRegKey@3@@Z`
- size: `1199`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1401b99c8`

## callees

- `0x1400c860c`
- `0x1400c8e38`
- `0x1400c8e68`
- `0x1400c8ed8`
- `0x1400e1654`
- `0x14010e160`
- `0x14010ed90`
- `0x14016817c`
- `0x140194010`
- `0x14019bcc4`
- `0x1401b0624`
- `0x1401b6cbc`
- `0x1401b6d28`
- `0x1401b6e18`
- `0x1401b6ee8`
- `0x1401b73b0`
- `0x1401b76f0`
- `0x1401b79d0`
- `0x1401b8144`
- `0x1401b849c`
- `0x1401b8d8c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400c8952`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400c89b3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400c8a14`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400c8952`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400c89b3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400c8a14`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400c891c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400c8989`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400c89ea`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400c891c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400c8989`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400c89ea`

## string_xrefs

- `0x1400c873b`: `Configuration`
- `0x1400c865b`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility`

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
0x1400c860c  mov     [rsp-8+arg_0], rbx
0x1400c8611  push    rbp
0x1400c8612  push    rsi
0x1400c8613  push    rdi
0x1400c8614  push    r14
0x1400c8616  push    r15
0x1400c8618  lea     rbp, [rsp-1D0h]
0x1400c8620  sub     rsp, 2D0h
0x1400c8627  mov     rax, cs:__security_cookie
0x1400c862e  xor     rax, rsp
0x1400c8631  mov     [rbp+1F0h+var_30], rax
0x1400c8638  mov     rdi, r9
0x1400c863b  mov     r14, r8
0x1400c863e  mov     rsi, rdx
0x1400c8641  lea     rax, [rsp+2F0h+var_2B0]
0x1400c8646  mov     [rsp+2F0h+var_2B8], rax; unsigned int *
0x1400c864b  mov     [rsp+2F0h+var_2C8], 3; REGSAM
0x1400c8653  mov     [rsp+2F0h+var_2D0], 0; DWORD
0x1400c865b  lea     r8, ?_accessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400c8662  mov     r15, 0FFFFFFFF80000001h
0x1400c8669  mov     rdx, r15; hKey
0x1400c866c  mov     rcx, r9; this
0x1400c866f  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1400c8674  mov     ebx, eax
0x1400c8676  test    eax, eax
0x1400c8678  jz      short loc_1400C86BF
0x1400c867a  lea     rsi, WPP_GLOBAL_Control
0x1400c8681  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c8688  cmp     rcx, rsi
0x1400c868b  jz      short loc_1400C86AB
0x1400c868d  test    byte ptr [rcx+1Ch], 8
0x1400c8691  jz      short loc_1400C86AB
0x1400c8693  mov     edx, 29h ; ')'
0x1400c8698  mov     r9d, eax
0x1400c869b  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x1400c86a2  mov     rcx, [rcx+10h]
0x1400c86a6  call    WPP_SF_d
0x1400c86ab  test    ebx, ebx
0x1400c86ad  jle     short loc_1400C86B8
0x1400c86af  movzx   ebx, bx
0x1400c86b2  or      ebx, 80070000h
0x1400c86b8  mov     eax, ebx
0x1400c86ba  jmp     loc_1400C8A94
0x1400c86bf  xorps   xmm0, xmm0
0x1400c86c2  movdqu  [rbp+1F0h+var_270], xmm0
0x1400c86c7  mov     [rbp+1F0h+var_260], 0
0x1400c86cf  xorps   xmm1, xmm1
0x1400c86d2  movdqu  [rbp+1F0h+var_258], xmm1
0x1400c86d7  mov     [rbp+1F0h+var_248], 0Ah
0x1400c86de  mov     rax, [rsi]
0x1400c86e1  mov     qword ptr [rsp+2F0h+var_2B0], rax
0x1400c86e6  test    rax, rax
0x1400c86e9  jz      short loc_1400C871A
0x1400c86eb  lea     rdx, [rsp+2F0h+var_2B0]
0x1400c86f0  call    ?GetNext@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAPEAU__POSITION@@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GetNext(__POSITION * &)
0x1400c86f5  mov     rbx, rax
0x1400c86f8  mov     rcx, [rax]; unsigned __int16 *
0x1400c86fb  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x1400c8700  cmp     dword ptr [rax+50h], 1
0x1400c8704  jz      short loc_1400C8712
0x1400c8706  mov     rdx, [rbx]
0x1400c8709  lea     rcx, [rbp+1F0h+var_270]
0x1400c870d  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x1400c8712  cmp     qword ptr [rsp+2F0h+var_2B0], 0
0x1400c8718  jnz     short loc_1400C86EB
0x1400c871a  lea     rcx, [rsp+2F0h+var_290]
0x1400c871f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1400c8724  nop
0x1400c8725  lea     rdx, [rbp+1F0h+var_270]
0x1400c8729  lea     rcx, [rsp+2F0h+var_290]
0x1400c872e  call    ?BuildConfigString@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z; StartList::BuildConfigString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x1400c8733  mov     rbx, [rsp+2F0h+var_290]
0x1400c8738  mov     r8, rbx; unsigned __int16 *
0x1400c873b  lea     rdx, ?_configuration@StartList@@0PAGA; "Configuration"
0x1400c8742  mov     rcx, rdi; this
0x1400c8745  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x1400c874a  mov     edi, eax
0x1400c874c  test    eax, eax
0x1400c874e  jz      short loc_1400C8797
0x1400c8750  lea     rsi, WPP_GLOBAL_Control
0x1400c8757  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c875e  cmp     rcx, rsi
0x1400c8761  jz      short loc_1400C8781
0x1400c8763  test    byte ptr [rcx+1Ch], 8
0x1400c8767  jz      short loc_1400C8781
0x1400c8769  mov     edx, 2Ah ; '*'
0x1400c876e  mov     r9d, eax
0x1400c8771  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x1400c8778  mov     rcx, [rcx+10h]
0x1400c877c  call    WPP_SF_d
0x1400c8781  test    edi, edi
0x1400c8783  jle     loc_1400C881B
0x1400c8789  movzx   edi, di
0x1400c878c  or      edi, 80070000h
0x1400c8792  jmp     loc_1400C881B
0x1400c8797  mov     [rsp+2F0h+var_288], 0
0x1400c87a0  mov     [rsp+2F0h+var_280], 0
0x1400c87a9  mov     [rsp+2F0h+var_278], 0
0x1400c87b2  mov     r9d, 20019h; unsigned int
0x1400c87b8  lea     r8, aSoftwareMicros_101; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400c87bf  mov     rdx, r15; hKey
0x1400c87c2  lea     rcx, [rsp+2F0h+var_288]; this
0x1400c87c7  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1400c87cc  mov     edi, eax
0x1400c87ce  test    eax, eax
0x1400c87d0  jz      short loc_1400C8829
0x1400c87d2  lea     rsi, WPP_GLOBAL_Control
0x1400c87d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c87e0  cmp     rcx, rsi
0x1400c87e3  jz      short loc_1400C8803
0x1400c87e5  test    byte ptr [rcx+1Ch], 8
0x1400c87e9  jz      short loc_1400C8803
0x1400c87eb  mov     edx, 2Bh ; '+'
0x1400c87f0  mov     r9d, eax
0x1400c87f3  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x1400c87fa  mov     rcx, [rcx+10h]
0x1400c87fe  call    WPP_SF_d
0x1400c8803  test    edi, edi
0x1400c8805  jle     short loc_1400C8810
0x1400c8807  movzx   edi, di
0x1400c880a  or      edi, 80070000h
0x1400c8810  lea     rcx, [rsp+2F0h+var_288]; this
0x1400c8815  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400c881a  nop
0x1400c881b  lea     rcx, [rbx-18h]; this
0x1400c881f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400c8824  jmp     loc_1400C8A89
0x1400c8829  xor     edx, edx; Val
0x1400c882b  mov     r8d, 208h; Size
0x1400c8831  lea     rcx, [rbp+1F0h+var_240]; void *
0x1400c8835  call    memset_0
0x1400c883a  mov     [rsp+2F0h+var_2B0], 104h
0x1400c8842  lea     r9, [rsp+2F0h+var_2B0]; unsigned int *
0x1400c8847  lea     r8, [rbp+1F0h+var_240]; unsigned __int16 *
0x1400c884b  lea     rdx, aStartup; "Startup"
0x1400c8852  lea     rcx, [rsp+2F0h+var_288]; this
0x1400c8857  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x1400c885c  lea     rdx, [rbp+1F0h+var_240]
0x1400c8860  lea     rcx, [rsp+2F0h+lpFileName]
0x1400c8865  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400c886a  nop
0x1400c886b  lea     rdx, [rbp+1F0h+var_240]
0x1400c886f  lea     rcx, [rsp+2F0h+var_2A0]
0x1400c8874  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400c8879  nop
0x1400c887a  lea     rdx, [rbp+1F0h+var_240]
0x1400c887e  lea     rcx, [rsp+2F0h+var_2A8]
0x1400c8883  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1400c8888  nop
0x1400c8889  mov     r8d, 17h
0x1400c888f  lea     rdx, aOnScreenKeyboa; "\\On-Screen Keyboard.lnk"
0x1400c8896  lea     rcx, [rsp+2F0h+lpFileName]
0x1400c889b  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1400c88a0  mov     r8d, 0Dh
0x1400c88a6  lea     rdx, aNarratorLnk; "\\Narrator.lnk"
0x1400c88ad  lea     rcx, [rsp+2F0h+var_2A0]
0x1400c88b2  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1400c88b7  mov     r8d, 0Eh
0x1400c88bd  lea     rdx, aMagnifierLnk; "\\Magnifier.lnk"
0x1400c88c4  lea     rcx, [rsp+2F0h+var_2A8]
0x1400c88c9  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1400c88ce  lea     r15, [rbx-18h]
0x1400c88d2  mov     rdi, [r14]
0x1400c88d5  add     rdi, 0FFFFFFFFFFFFFFE8h
0x1400c88d9  cmp     r15, rdi
0x1400c88dc  jz      short loc_1400C8917
0x1400c88de  cmp     dword ptr [rdi+10h], 0
0x1400c88e2  jl      short loc_1400C8908
0x1400c88e4  mov     rax, [rdi]
0x1400c88e7  cmp     [r15], rax
0x1400c88ea  jnz     short loc_1400C8908
0x1400c88ec  mov     rcx, r15
0x1400c88ef  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1400c88f4  mov     rbx, rax
0x1400c88f7  mov     rcx, rdi; this
0x1400c88fa  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400c88ff  lea     rax, [rbx+18h]
0x1400c8903  mov     [r14], rax
0x1400c8906  jmp     short loc_1400C8917
0x1400c8908  mov     r8d, [rbx-10h]
0x1400c890c  mov     rdx, rbx
0x1400c890f  mov     rcx, r14
0x1400c8912  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400c8917  mov     rcx, [rsp+2F0h+lpFileName]; lpFileName
0x1400c891c  call    cs:__imp_GetFileAttributesW
0x1400c8923  nop     dword ptr [rax+rax+00h]
0x1400c8928  mov     bl, 10h
0x1400c892a  lea     rsi, WPP_GLOBAL_Control
0x1400c8931  or      edi, 0FFFFFFFFh
0x1400c8934  cmp     eax, edi
0x1400c8936  jz      short loc_1400C8984
0x1400c8938  mov     r8d, 4
0x1400c893e  lea     rdx, aOsk; ",osk"
0x1400c8945  mov     rcx, r14
0x1400c8948  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1400c894d  mov     rcx, [rsp+2F0h+lpFileName]; lpFileName
0x1400c8952  call    cs:__imp_DeleteFileW
0x1400c8959  nop     dword ptr [rax+rax+00h]
0x1400c895e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c8965  cmp     rcx, rsi
0x1400c8968  jz      short loc_1400C8984
0x1400c896a  test    [rcx+1Ch], bl
0x1400c896d  jz      short loc_1400C8984
0x1400c896f  mov     edx, 2Ch ; ','
0x1400c8974  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x1400c897b  mov     rcx, [rcx+10h]
0x1400c897f  call    WPP_SF_
0x1400c8984  mov     rcx, [rsp+2F0h+var_2A0]; lpFileName
0x1400c8989  call    cs:__imp_GetFileAttributesW
0x1400c8990  nop     dword ptr [rax+rax+00h]
0x1400c8995  cmp     eax, edi
0x1400c8997  jz      short loc_1400C89E5
0x1400c8999  mov     r8d, 9
0x1400c899f  lea     rdx, aNarrator; ",Narrator"
0x1400c89a6  mov     rcx, r14
0x1400c89a9  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1400c89ae  mov     rcx, [rsp+2F0h+var_2A0]; lpFileName
0x1400c89b3  call    cs:__imp_DeleteFileW
0x1400c89ba  nop     dword ptr [rax+rax+00h]
0x1400c89bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c89c6  cmp     rcx, rsi
0x1400c89c9  jz      short loc_1400C89E5
0x1400c89cb  test    [rcx+1Ch], bl
0x1400c89ce  jz      short loc_1400C89E5
0x1400c89d0  mov     edx, 2Dh ; '-'
0x1400c89d5  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x1400c89dc  mov     rcx, [rcx+10h]
0x1400c89e0  call    WPP_SF_
0x1400c89e5  mov     rcx, [rsp+2F0h+var_2A8]; lpFileName
0x1400c89ea  call    cs:__imp_GetFileAttributesW
0x1400c89f1  nop     dword ptr [rax+rax+00h]
0x1400c89f6  cmp     eax, edi
0x1400c89f8  jz      short loc_1400C8A47
0x1400c89fa  mov     r8d, 0Eh
0x1400c8a00  lea     rdx, aMagnifierpane; ",magnifierpane"
0x1400c8a07  mov     rcx, r14
0x1400c8a0a  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1400c8a0f  mov     rcx, [rsp+2F0h+var_2A8]; lpFileName
0x1400c8a14  call    cs:__imp_DeleteFileW
0x1400c8a1b  nop     dword ptr [rax+rax+00h]
0x1400c8a20  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c8a27  cmp     rcx, rsi
0x1400c8a2a  jz      short loc_1400C8A47
0x1400c8a2c  test    [rcx+1Ch], bl
0x1400c8a2f  jz      short loc_1400C8A47
0x1400c8a31  mov     edx, 2Eh ; '.'
0x1400c8a36  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x1400c8a3d  mov     rcx, [rcx+10h]
0x1400c8a41  call    WPP_SF_
0x1400c8a46  nop
0x1400c8a47  mov     rcx, [rsp+2F0h+var_2A8]
0x1400c8a4c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1400c8a50  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400c8a55  nop
0x1400c8a56  mov     rcx, [rsp+2F0h+var_2A0]
0x1400c8a5b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1400c8a5f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400c8a64  nop
0x1400c8a65  mov     rcx, [rsp+2F0h+lpFileName]
0x1400c8a6a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1400c8a6e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400c8a73  nop
0x1400c8a74  lea     rcx, [rsp+2F0h+var_288]; this
0x1400c8a79  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400c8a7e  nop
0x1400c8a7f  mov     rcx, r15; this
0x1400c8a82  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400c8a87  xor     edi, edi
0x1400c8a89  lea     rcx, [rbp+1F0h+var_270]
0x1400c8a8d  call    ?RemoveAll@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x1400c8a92  mov     eax, edi
0x1400c8a94  mov     rcx, [rbp+1F0h+var_30]
0x1400c8a9b  xor     rcx, rsp; StackCookie
0x1400c8a9e  call    __security_check_cookie
0x1400c8aa3  mov     rbx, [rsp+2F0h+arg_0]
0x1400c8aab  add     rsp, 2D0h
0x1400c8ab2  pop     r15
0x1400c8ab4  pop     r14
0x1400c8ab6  pop     rdi
0x1400c8ab7  pop     rsi
0x1400c8ab8  pop     rbp
0x1400c8ab9  retn
```
