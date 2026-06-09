# CNetDiagClient::ApplyRootCauseFilter(void)

- ea: `0x180018ed4`
- end: `0x180019225`
- name: `?ApplyRootCauseFilter@CNetDiagClient@@IEAAJXZ`
- size: `849`
- prototype: `__int64 __fastcall(CNetDiagClient *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x180019af8`

## callees

- `0x180018864`
- `0x180018ed4`
- `0x18001922c`
- `0x180019964`
- `0x18001a01c`
- `0x18001a610`
- `0x18001f646`
- `0x18001f690`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x180018fa8`
- `ADVAPI32!RegGetValueW` at `0x180018fa8`
- `ADVAPI32!RegOpenKeyExW` at `0x180018f5b`
- `ADVAPI32!RegOpenKeyExW` at `0x180018fef`
- `ADVAPI32!RegOpenKeyExW` at `0x180018f5b`
- `ADVAPI32!RegOpenKeyExW` at `0x180018fef`
- `ADVAPI32!RegCloseKey` at `0x1800191dc`
- `ADVAPI32!RegCloseKey` at `0x1800191ec`
- `ADVAPI32!RegCloseKey` at `0x1800191dc`
- `ADVAPI32!RegCloseKey` at `0x1800191ec`

## string_xrefs

- `0x180018f4d`: `SYSTEM\CurrentControlSet\Control\NetDiagFx\Config`

## pseudocode

```c
__int64 __fastcall CNetDiagClient::ApplyRootCauseFilter(CNetDiagClient *this)
{
  int v2; // eax
  LSTATUS v3; // eax
  signed int v4; // ebx
  LSTATUS ValueW; // eax
  LSTATUS v6; // eax
  unsigned int i; // eax
  int v8; // edx
  char *v9; // r14
  int CatchAllRootCauseReplacement; // eax
  __int64 *v11; // r12
  __int64 *v12; // r15
  __int64 *v13; // r13
  __int64 v14; // r8
  int phkResult; // [rsp+20h] [rbp-B8h]
  int v17; // [rsp+40h] [rbp-98h] BYREF
  int pvData; // [rsp+44h] [rbp-94h] BYREF
  unsigned int v19; // [rsp+48h] [rbp-90h]
  HKEY hkey; // [rsp+50h] [rbp-88h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-78h] BYREF
  struct _GUID v23; // [rsp+70h] [rbp-68h] BYREF
  _BYTE v24[16]; // [rsp+80h] [rbp-58h] BYREF
  GUID Buf2; // [rsp+90h] [rbp-48h] BYREF

  v17 = 2;
  hkey = 0;
  hKey = 0;
  pvData = 0;
  pcbData = 4;
  v2 = *((_DWORD *)this + 758);
  *((_DWORD *)this + 759) = v2;
  if ( v2 )
  {
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\NetDiagFx\\Config", 0, 0x20019u, &hkey);
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    if ( v4 >= 0 )
    {
      ValueW = RegGetValueW(hkey, 0, L"FilterMode", 0x10u, 0, &pvData, &pcbData);
      v4 = ValueW;
      if ( ValueW > 0 )
        v4 = (unsigned __int16)ValueW | 0x80070000;
      if ( v4 >= 0 )
      {
        if ( pvData == 1 )
        {
          v4 = 1;
          goto LABEL_40;
        }
        v6 = RegOpenKeyExW(hkey, L"RC", 0, 0x20019u, &hKey);
        v4 = v6;
        if ( v6 > 0 )
          v4 = (unsigned __int16)v6 | 0x80070000;
        if ( v4 >= 0 )
        {
          for ( i = 0; ; i = v19 + 1 )
          {
            v19 = i;
            if ( i >= *((_DWORD *)this + 758) )
            {
              *((_DWORD *)this + 760) = 1;
              break;
            }
            v8 = *((_DWORD *)this + 22 * i + 506);
            if ( (v8 & 4) == 0 )
            {
              v9 = (char *)this + 88 * i + 2000;
              if ( (v8 & 0x40000000) != 0 || !*((_WORD *)v9 + 28) )
              {
                *((_DWORD *)v9 + 6) = v8 | 0x80000000;
LABEL_18:
                --*((_DWORD *)this + 759);
                continue;
              }
              Buf2 = *(GUID *)(v9 + 8);
              v4 = IsRootCauseFiltered(hKey, &Buf2, (enum TriState *)&v17);
              if ( v4 < 0 )
                break;
              if ( v17 == 1 )
              {
LABEL_22:
                *((_DWORD *)v9 + 6) |= 0x80000000;
                goto LABEL_18;
              }
              if ( !v17 )
                goto LABEL_37;
              Buf2 = 0;
              CatchAllRootCauseReplacement = CNetDiagClient::FindCatchAllRootCauseReplacement(
                                               this,
                                               (struct tagRootCauseInfo *)v9,
                                               &Buf2);
              v4 = CatchAllRootCauseReplacement;
              if ( CatchAllRootCauseReplacement < 0 )
                break;
              if ( CatchAllRootCauseReplacement )
              {
                if ( pvData != 2 )
                  goto LABEL_22;
LABEL_37:
                RemoveTrailingCatchAllRepairs((struct tagRootCauseInfo *)v9);
                continue;
              }
              v11 = (__int64 *)*((_QWORD *)this + 14);
              v12 = (__int64 *)v11[1];
              v13 = v11;
              if ( !*((_BYTE *)v12 + 25) )
              {
                do
                {
                  if ( memcmp_0((char *)v12 + 28, &Buf2, 0x10u) >= 0 )
                  {
                    v13 = v12;
                    v12 = (__int64 *)*v12;
                  }
                  else
                  {
                    v12 = (__int64 *)v12[2];
                  }
                }
                while ( !*((_BYTE *)v12 + 25) );
                if ( v13 != v11 && memcmp_0(&Buf2, (char *)v13 + 28, 0x10u) >= 0 )
                {
                  *((_DWORD *)v9 + 6) |= 0x80000000;
                  goto LABEL_18;
                }
              }
              v23 = Buf2;
              v4 = ((int (__stdcall *)(CNetDiagClient *, struct tagRootCauseInfo *, struct _GUID *))CNetDiagClient::ConvertRootCauseToCatchAll)(
                     this,
                     (struct tagRootCauseInfo *)v9,
                     &v23);
              if ( v4 < 0 )
                break;
              if ( __eh34_try(-1, 0) )
              {
                __eh34_scope_strut(0);
                LOBYTE(phkResult) = byte_18002FEA0;
                std::_Tree<std::_Tset_traits<_GUID,GuidLessThan,std::allocator<_GUID>,0>>::_Insert_nohint<_GUID const &,std::_Nil>(
                  (char *)this + 112,
                  v24,
                  v14,
                  &Buf2,
                  phkResult);
              }
              if ( __eh34_catch(0) )
              {
                if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
                {
                  v17 = -2147024882;
                  v4 = -2147024882;
                  __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_1800191A4);
                  break;
                }
                if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', 0) )
                {
                  v17 = -2147467259;
                  v4 = -2147467259;
                  __eh34_try_continuation(0, &exception `RTTI Type Descriptor', &loc_1800191A4);
                  break;
                }
              }
            }
          }
        }
      }
    }
LABEL_40:
    if ( hkey )
      RegCloseKey(hkey);
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    return 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180018ed4  mov     [rsp+arg_8], rbx
0x180018ed9  mov     [rsp+arg_10], rsi
0x180018ede  push    rdi
0x180018edf  push    r12
0x180018ee1  push    r13
0x180018ee3  push    r14
0x180018ee5  push    r15
0x180018ee7  sub     rsp, 0B0h
0x180018eee  mov     rax, cs:__security_cookie
0x180018ef5  xor     rax, rsp
0x180018ef8  mov     [rsp+0D8h+var_38], rax
0x180018f00  mov     rsi, rcx
0x180018f03  mov     [rsp+0D8h+var_98], 2
0x180018f0b  xor     edi, edi
0x180018f0d  mov     [rsp+0D8h+hkey], rdi
0x180018f12  mov     [rsp+0D8h+hKey], rdi
0x180018f17  mov     [rsp+0D8h+var_94], edi
0x180018f1b  mov     [rsp+0D8h+var_80], 4
0x180018f23  mov     eax, [rcx+0BD8h]
0x180018f29  mov     [rcx+0BDCh], eax
0x180018f2f  test    eax, eax
0x180018f31  jz      loc_1800191F4
0x180018f37  lea     rax, [rsp+0D8h+hkey]
0x180018f3c  mov     [rsp+0D8h+phkResult], rax; phkResult
0x180018f41  mov     r15d, 20019h
0x180018f47  mov     r9d, r15d; samDesired
0x180018f4a  xor     r8d, r8d; ulOptions
0x180018f4d  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Net"...
0x180018f54  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018f5b  call    cs:__imp_RegOpenKeyExW
0x180018f61  mov     ebx, eax
0x180018f63  mov     r14d, 80070000h
0x180018f69  test    eax, eax
0x180018f6b  jle     short loc_180018F73
0x180018f6d  movzx   ebx, ax
0x180018f70  or      ebx, r14d
0x180018f73  test    ebx, ebx
0x180018f75  js      loc_1800191D2
0x180018f7b  lea     rax, [rsp+0D8h+var_80]
0x180018f80  mov     [rsp+0D8h+pcbData], rax; pcbData
0x180018f85  lea     rax, [rsp+0D8h+var_94]
0x180018f8a  mov     [rsp+0D8h+pvData], rax; pvData
0x180018f8f  mov     [rsp+0D8h+phkResult], rdi; pdwType
0x180018f94  mov     r9d, 10h; dwFlags
0x180018f9a  lea     r8, Value; "FilterMode"
0x180018fa1  xor     edx, edx; lpSubKey
0x180018fa3  mov     rcx, [rsp+0D8h+hkey]; hkey
0x180018fa8  call    cs:__imp_RegGetValueW
0x180018fae  mov     ebx, eax
0x180018fb0  test    eax, eax
0x180018fb2  jle     short loc_180018FBA
0x180018fb4  movzx   ebx, ax
0x180018fb7  or      ebx, r14d
0x180018fba  test    ebx, ebx
0x180018fbc  js      loc_1800191D2
0x180018fc2  cmp     [rsp+0D8h+var_94], 1
0x180018fc7  jnz     short loc_180018FD3
0x180018fc9  mov     ebx, 1
0x180018fce  jmp     loc_1800191D2
0x180018fd3  lea     rax, [rsp+0D8h+hKey]
0x180018fd8  mov     [rsp+0D8h+phkResult], rax; phkResult
0x180018fdd  mov     r9d, r15d; samDesired
0x180018fe0  xor     r8d, r8d; ulOptions
0x180018fe3  lea     rdx, aRc; "RC"
0x180018fea  mov     rcx, [rsp+0D8h+hkey]; hKey
0x180018fef  call    cs:__imp_RegOpenKeyExW
0x180018ff5  mov     ebx, eax
0x180018ff7  test    eax, eax
0x180018ff9  jle     short loc_180019001
0x180018ffb  movzx   ebx, ax
0x180018ffe  or      ebx, r14d
0x180019001  test    ebx, ebx
0x180019003  js      loc_1800191D2
0x180019009  mov     eax, edi
0x18001900b  mov     r15d, 80000000h
0x180019011  or      r12d, 0FFFFFFFFh
0x180019015  mov     [rsp+0D8h+var_90], eax
0x180019019  cmp     eax, [rsi+0BD8h]
0x18001901f  jnb     loc_1800191C8
0x180019025  mov     r8d, eax
0x180019028  lea     rax, [r8+17h]
0x18001902c  imul    rcx, rax, 58h ; 'X'
0x180019030  mov     edx, [rcx+rsi]
0x180019033  test    dl, 4
0x180019036  jnz     loc_1800191BD
0x18001903c  imul    r14, r8, 58h ; 'X'
0x180019040  add     r14, 7D0h
0x180019047  add     r14, rsi
0x18001904a  bt      edx, 1Eh
0x18001904e  jnb     short loc_180019063
0x180019050  or      edx, r15d
0x180019053  mov     [r14+18h], edx
0x180019057  add     [rsi+0BDCh], r12d
0x18001905e  jmp     loc_1800191BD
0x180019063  cmp     [r14+38h], di
0x180019068  jz      short loc_180019050
0x18001906a  movups  xmm0, xmmword ptr [r14+8]
0x18001906f  movdqu  [rsp+0D8h+Buf2], xmm0
0x180019078  lea     r8, [rsp+0D8h+var_98]; enum TriState *
0x18001907d  lea     rdx, [rsp+0D8h+Buf2]; rguid
0x180019085  mov     rcx, [rsp+0D8h+hKey]; hkey
0x18001908a  call    ?IsRootCauseFiltered@@YAJPEAUHKEY__@@U_GUID@@AEAW4TriState@@@Z; IsRootCauseFiltered(HKEY__ *,_GUID,TriState &)
0x18001908f  mov     ebx, eax
0x180019091  test    eax, eax
0x180019093  js      loc_1800191D2
0x180019099  cmp     [rsp+0D8h+var_98], 1
0x18001909e  jnz     short loc_1800190A6
0x1800190a0  or      [r14+18h], r15d
0x1800190a4  jmp     short loc_180019057
0x1800190a6  cmp     [rsp+0D8h+var_98], edi
0x1800190aa  jz      loc_1800191B5
0x1800190b0  xorps   xmm0, xmm0
0x1800190b3  movups  [rsp+0D8h+Buf2], xmm0
0x1800190bb  lea     r8, [rsp+0D8h+Buf2]; struct _GUID *
0x1800190c3  mov     rdx, r14; struct tagRootCauseInfo *
0x1800190c6  mov     rcx, rsi; this
0x1800190c9  call    ?FindCatchAllRootCauseReplacement@CNetDiagClient@@IEAAJAEAUtagRootCauseInfo@@AEAU_GUID@@@Z; CNetDiagClient::FindCatchAllRootCauseReplacement(tagRootCauseInfo &,_GUID &)
0x1800190ce  mov     ebx, eax
0x1800190d0  test    eax, eax
0x1800190d2  js      loc_1800191D2
0x1800190d8  jnz     loc_1800191AA
0x1800190de  mov     r12, [rsi+70h]
0x1800190e2  mov     r15, [r12+8]
0x1800190e7  mov     r13, r12
0x1800190ea  cmp     [r15+19h], dil
0x1800190ee  jnz     short loc_180019150
0x1800190f0  lea     rcx, [r15+1Ch]; Buf1
0x1800190f4  mov     r8d, 10h; Size
0x1800190fa  lea     rdx, [rsp+0D8h+Buf2]; Buf2
0x180019102  call    memcmp_0
0x180019107  test    eax, eax
0x180019109  jns     short loc_180019111
0x18001910b  mov     r15, [r15+10h]
0x18001910f  jmp     short loc_180019117
0x180019111  mov     r13, r15
0x180019114  mov     r15, [r15]
0x180019117  cmp     [r15+19h], dil
0x18001911b  jz      short loc_1800190F0
0x18001911d  cmp     r13, r12
0x180019120  jz      short loc_180019150
0x180019122  lea     rdx, [r13+1Ch]; Buf2
0x180019126  mov     r8d, 10h; Size
0x18001912c  lea     rcx, [rsp+0D8h+Buf2]; Buf1
0x180019134  call    memcmp_0
0x180019139  test    eax, eax
0x18001913b  js      short loc_180019150
0x18001913d  mov     r15d, 80000000h
0x180019143  or      [r14+18h], r15d
0x180019147  or      r12d, 0FFFFFFFFh
0x18001914b  jmp     loc_180019057
0x180019150  movaps  xmm0, [rsp+0D8h+Buf2]
0x180019158  movdqa  xmmword ptr [rsp+0D8h+var_68.Data1], xmm0
0x18001915e  lea     r8, [rsp+0D8h+var_68]; struct _GUID
0x180019163  mov     rdx, r14; struct tagRootCauseInfo *
0x180019166  mov     rcx, rsi; this
0x180019169  call    ?ConvertRootCauseToCatchAll@CNetDiagClient@@IEAAJAEAUtagRootCauseInfo@@U_GUID@@@Z; CNetDiagClient::ConvertRootCauseToCatchAll(tagRootCauseInfo &,_GUID)
0x18001916e  mov     ebx, eax
0x180019170  test    eax, eax
0x180019172  js      short loc_1800191D2
0x180019174  mov     al, cs:byte_18002FEA0
0x18001917a  mov     byte ptr [rsp+0D8h+phkResult], al
0x18001917e  lea     r9, [rsp+0D8h+Buf2]
0x180019186  lea     rdx, [rsp+0D8h+var_58]
0x18001918e  lea     rcx, [rsi+70h]
0x180019192  call    ??$_Insert_nohint@AEBU_GUID@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@U_GUID@@UGuidLessThan@@V?$allocator@U_GUID@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U_GUID@@@std@@@std@@@std@@_N@1@_NAEBU_GUID@@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<_GUID,GuidLessThan,std::allocator<_GUID>,0>>::_Insert_nohint<_GUID const &,std::_Nil>(bool,_GUID const &,std::_Nil)
0x180019197  nop
0x180019198  mov     r15d, 80000000h
0x18001919e  or      r12d, 0FFFFFFFFh
0x1800191a2  jmp     short loc_1800191BD
0x1800191a4  mov     ebx, [rsp+0D8h+var_98]
0x1800191a8  jmp     short loc_1800191D2
0x1800191aa  cmp     [rsp+0D8h+var_94], 2
0x1800191af  jnz     loc_1800190A0
0x1800191b5  mov     rcx, r14; struct tagRootCauseInfo *
0x1800191b8  call    ?RemoveTrailingCatchAllRepairs@@YAXAEAUtagRootCauseInfo@@@Z; RemoveTrailingCatchAllRepairs(tagRootCauseInfo &)
0x1800191bd  mov     eax, [rsp+0D8h+var_90]
0x1800191c1  inc     eax
0x1800191c3  jmp     loc_180019015
0x1800191c8  mov     dword ptr [rsi+0BE0h], 1
0x1800191d2  mov     rcx, [rsp+0D8h+hkey]; hKey
0x1800191d7  test    rcx, rcx
0x1800191da  jz      short loc_1800191E2
0x1800191dc  call    cs:__imp_RegCloseKey
0x1800191e2  mov     rcx, [rsp+0D8h+hKey]; hKey
0x1800191e7  test    rcx, rcx
0x1800191ea  jz      short loc_1800191F6
0x1800191ec  call    cs:__imp_RegCloseKey
0x1800191f2  jmp     short loc_1800191F6
0x1800191f4  mov     ebx, edi
0x1800191f6  mov     eax, ebx
0x1800191f8  mov     rcx, [rsp+0D8h+var_38]
0x180019200  xor     rcx, rsp; StackCookie
0x180019203  call    __security_check_cookie
0x180019208  lea     r11, [rsp+0D8h+var_28]
0x180019210  mov     rbx, [r11+38h]
0x180019214  mov     rsi, [r11+40h]
0x180019218  mov     rsp, r11
0x18001921b  pop     r15
0x18001921d  pop     r14
0x18001921f  pop     r13
0x180019221  pop     r12
0x180019223  pop     rdi
0x180019224  retn
```
