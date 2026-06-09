# CHidPairingPlugin::ParseOOBESettingsStore(IOOBESettingsStore *)

- ea: `0x1800250c0`
- end: `0x1800253e3`
- name: `?ParseOOBESettingsStore@CHidPairingPlugin@@UEAAJPEAUIOOBESettingsStore@@@Z`
- size: `803`
- prototype: `int(CHidPairingPlugin *__hidden this, struct IOOBESettingsStore *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callees

- `0x180019a38`
- `0x1800250c0`
- `0x180025e3c`
- `0x180025f70`
- `0x1800266a8`

## string_xrefs

- `0x18002517a`: `hidSetup/mouseErrorImagePath`
- `0x180025152`: `hidSetup/mouseImagePath`
- `0x180025217`: `hidSetup/keyboardPINImagePath`
- `0x1800251f1`: `hidSetup/keyboardImagePath`
- `0x180025263`: `hidSetup/accessoryTitle`
- `0x180025239`: `hidSetup/keyboardErrorImagePath`
- `0x1800252af`: `hidSetup/accessoryImagePath`
- `0x180025289`: `hidSetup/accessoryName`
- `0x1800252fb`: `hidSetup/accessoryErrorImagePath`
- `0x1800252d5`: `hidSetup/accessoryText`
- `0x180025347`: `hidSetup/accessorySuccessImage`
- `0x180025321`: `hidSetup/accessoryErrorText`
- `0x18002536d`: `hidSetup/accessorySuccessText`

## pseudocode

```c
__int64 __fastcall CHidPairingPlugin::ParseOOBESettingsStore(CHidPairingPlugin *this, struct IOOBESettingsStore *a2)
{
  int v4; // esi
  CHidPairingPlugin *v5; // rcx
  unsigned int v6; // ebx
  int OOBEXMLString; // eax
  unsigned __int16 *v9; // [rsp+20h] [rbp-E0h]
  unsigned __int16 **v10[41]; // [rsp+28h] [rbp-D8h]

  v4 = CHidPairingPlugin::_EnsureDefaultAltTextInitialized((CHidPairingPlugin *)((char *)this - 24), a2);
  v9 = L"hidSetup/title";
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 56);
  v10[0] = (unsigned __int16 **)((char *)this + 56);
  *((_QWORD *)this + 8) = -1;
  *((_QWORD *)this + 9) = -1;
  v10[1] = (unsigned __int16 **)L"hidSetup/mouseTitle";
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 80);
  *((_QWORD *)this + 11) = -1;
  *((_QWORD *)this + 12) = -1;
  v10[2] = (unsigned __int16 **)((char *)this + 80);
  v10[3] = (unsigned __int16 **)L"hidSetup/mouseName";
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 104);
  *((_QWORD *)this + 14) = -1;
  *((_QWORD *)this + 15) = -1;
  v10[4] = (unsigned __int16 **)((char *)this + 104);
  v10[5] = (unsigned __int16 **)L"hidSetup/mouseImagePath";
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 128);
  *((_QWORD *)this + 17) = -1;
  *((_QWORD *)this + 18) = -1;
  v10[6] = (unsigned __int16 **)((char *)this + 128);
  v10[7] = (unsigned __int16 **)L"hidSetup/mouseErrorImagePath";
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 176);
  *((_QWORD *)this + 23) = -1;
  *((_QWORD *)this + 24) = -1;
  v10[8] = (unsigned __int16 **)((char *)this + 176);
  v10[9] = (unsigned __int16 **)L"hidSetup/keyboardTitle";
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 224);
  *((_QWORD *)this + 29) = -1;
  *((_QWORD *)this + 30) = -1;
  v10[10] = (unsigned __int16 **)((char *)this + 224);
  v10[11] = (unsigned __int16 **)L"hidSetup/keyboardName";
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 248);
  *((_QWORD *)this + 32) = -1;
  *((_QWORD *)this + 33) = -1;
  v10[12] = (unsigned __int16 **)((char *)this + 248);
  v10[13] = (unsigned __int16 **)L"hidSetup/keyboardImagePath";
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 272);
  *((_QWORD *)this + 35) = -1;
  *((_QWORD *)this + 36) = -1;
  v10[14] = (unsigned __int16 **)((char *)this + 272);
  v10[15] = (unsigned __int16 **)L"hidSetup/keyboardPINImagePath";
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 320);
  *((_QWORD *)this + 41) = -1;
  *((_QWORD *)this + 42) = -1;
  v10[16] = (unsigned __int16 **)((char *)this + 320);
  v10[17] = (unsigned __int16 **)L"hidSetup/keyboardErrorImagePath";
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 368);
  *((_QWORD *)this + 47) = -1;
  *((_QWORD *)this + 48) = -1;
  v10[18] = (unsigned __int16 **)((char *)this + 368);
  v10[19] = (unsigned __int16 **)L"hidSetup/accessoryTitle";
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 416);
  *((_QWORD *)this + 53) = -1;
  *((_QWORD *)this + 54) = -1;
  v10[20] = (unsigned __int16 **)((char *)this + 416);
  v10[21] = (unsigned __int16 **)L"hidSetup/accessoryName";
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 440);
  *((_QWORD *)this + 56) = -1;
  *((_QWORD *)this + 57) = -1;
  v10[22] = (unsigned __int16 **)((char *)this + 440);
  v10[23] = (unsigned __int16 **)L"hidSetup/accessoryImagePath";
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 464);
  *((_QWORD *)this + 59) = -1;
  *((_QWORD *)this + 60) = -1;
  v10[24] = (unsigned __int16 **)((char *)this + 464);
  v10[25] = (unsigned __int16 **)L"hidSetup/accessoryText";
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 488);
  *((_QWORD *)this + 62) = -1;
  *((_QWORD *)this + 63) = -1;
  v10[26] = (unsigned __int16 **)((char *)this + 488);
  v10[27] = (unsigned __int16 **)L"hidSetup/accessoryErrorImagePath";
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 512);
  *((_QWORD *)this + 65) = -1;
  *((_QWORD *)this + 66) = -1;
  v10[28] = (unsigned __int16 **)((char *)this + 512);
  v10[29] = (unsigned __int16 **)L"hidSetup/accessoryErrorText";
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 536);
  *((_QWORD *)this + 68) = -1;
  *((_QWORD *)this + 69) = -1;
  v10[30] = (unsigned __int16 **)((char *)this + 536);
  v10[31] = (unsigned __int16 **)L"hidSetup/accessorySuccessImage";
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 560);
  *((_QWORD *)this + 71) = -1;
  *((_QWORD *)this + 72) = -1;
  v10[32] = (unsigned __int16 **)((char *)this + 560);
  v10[33] = (unsigned __int16 **)L"hidSetup/accessorySuccessText";
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 584);
  *((_QWORD *)this + 74) = -1;
  *((_QWORD *)this + 75) = -1;
  v10[34] = (unsigned __int16 **)((char *)this + 584);
  v6 = 0;
  if ( v4 >= 0 )
  {
    do
    {
      if ( v6 >= 0x12 )
        break;
      OOBEXMLString = CHidPairingPlugin::_ReadOOBEXMLString(
                        v5,
                        a2,
                        (const unsigned __int16 *)v10[2 * v6 - 1],
                        v10[2 * v6]);
      ++v6;
      v4 = OOBEXMLString;
    }
    while ( OOBEXMLString >= 0 );
  }
  CHidPairingPlugin::_EnsureSecondaryInitializationIfNecessary((CHidPairingPlugin *)((char *)this - 24));
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800250c0  push    rbp
0x1800250c2  push    rbx
0x1800250c3  push    rsi
0x1800250c4  push    rdi
0x1800250c5  push    r12
0x1800250c7  push    r14
0x1800250c9  push    r15
0x1800250cb  lea     rbp, [rsp-40h]
0x1800250d0  sub     rsp, 140h
0x1800250d7  mov     rdi, rcx
0x1800250da  mov     r15, rdx
0x1800250dd  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800250e1  call    ?_EnsureDefaultAltTextInitialized@CHidPairingPlugin@@AEAAJPEAUIOOBESettingsStore@@@Z; CHidPairingPlugin::_EnsureDefaultAltTextInitialized(IOOBESettingsStore *)
0x1800250e6  mov     esi, eax
0x1800250e8  lea     rbx, [rdi+38h]
0x1800250ec  lea     rax, aHidsetupTitle; "hidSetup/title"
0x1800250f3  mov     rcx, rbx
0x1800250f6  mov     [rsp+170h+var_150], rax
0x1800250fb  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180025100  or      r12, 0FFFFFFFFFFFFFFFFh
0x180025104  mov     [rsp+170h+var_148], rbx
0x180025109  mov     [rbx+8], r12
0x18002510d  lea     rax, aHidsetupMouset; "hidSetup/mouseTitle"
0x180025114  mov     [rbx+10h], r12
0x180025118  lea     rbx, [rdi+50h]
0x18002511c  mov     rcx, rbx
0x18002511f  mov     [rsp+170h+var_140], rax
0x180025124  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180025129  mov     [rbx+8], r12
0x18002512d  lea     rax, aHidsetupMousen; "hidSetup/mouseName"
0x180025134  mov     [rbx+10h], r12
0x180025138  mov     [rsp+170h+var_138], rbx
0x18002513d  lea     rbx, [rdi+68h]
0x180025141  mov     rcx, rbx
0x180025144  mov     [rsp+170h+var_130], rax
0x180025149  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002514e  mov     [rbx+8], r12
0x180025152  lea     rax, aHidsetupMousei; "hidSetup/mouseImagePath"
0x180025159  mov     [rbx+10h], r12
0x18002515d  mov     [rsp+170h+var_128], rbx
0x180025162  lea     rbx, [rdi+80h]
0x180025169  mov     rcx, rbx
0x18002516c  mov     [rsp+170h+var_120], rax
0x180025171  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180025176  mov     [rbx+8], r12
0x18002517a  lea     rax, aHidsetupMousee; "hidSetup/mouseErrorImagePath"
0x180025181  mov     [rbx+10h], r12
0x180025185  mov     [rsp+170h+var_118], rbx
0x18002518a  lea     rbx, [rdi+0B0h]
0x180025191  mov     rcx, rbx
0x180025194  mov     [rsp+170h+var_110], rax
0x180025199  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002519e  mov     [rbx+8], r12
0x1800251a2  lea     rax, aHidsetupKeyboa_3; "hidSetup/keyboardTitle"
0x1800251a9  mov     [rbx+10h], r12
0x1800251ad  mov     [rsp+170h+var_108], rbx
0x1800251b2  lea     rbx, [rdi+0E0h]
0x1800251b9  mov     rcx, rbx
0x1800251bc  mov     [rsp+170h+var_100], rax
0x1800251c1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800251c6  mov     [rbx+8], r12
0x1800251ca  lea     rax, aHidsetupKeyboa_5; "hidSetup/keyboardName"
0x1800251d1  mov     [rbx+10h], r12
0x1800251d5  mov     [rsp+170h+var_F8], rbx
0x1800251da  lea     rbx, [rdi+0F8h]
0x1800251e1  mov     rcx, rbx
0x1800251e4  mov     [rbp+70h+var_F0], rax
0x1800251e8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800251ed  mov     [rbx+8], r12
0x1800251f1  lea     rax, aHidsetupKeyboa_2; "hidSetup/keyboardImagePath"
0x1800251f8  mov     [rbx+10h], r12
0x1800251fc  mov     [rbp+70h+var_E8], rbx
0x180025200  lea     rbx, [rdi+110h]
0x180025207  mov     rcx, rbx
0x18002520a  mov     [rbp+70h+var_E0], rax
0x18002520e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180025213  mov     [rbx+8], r12
0x180025217  lea     rax, aHidsetupKeyboa; "hidSetup/keyboardPINImagePath"
0x18002521e  mov     [rbx+10h], r12
0x180025222  mov     [rbp+70h+var_D8], rbx
0x180025226  lea     rbx, [rdi+140h]
0x18002522d  mov     rcx, rbx
0x180025230  mov     [rbp+70h+var_D0], rax
0x180025234  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180025239  lea     rax, aHidsetupKeyboa_4; "hidSetup/keyboardErrorImagePath"
0x180025240  mov     [rbx+8], r12
0x180025244  mov     [rbx+10h], r12
0x180025248  mov     [rbp+70h+var_C8], rbx
0x18002524c  lea     rbx, [rdi+170h]
0x180025253  mov     [rbp+70h+var_C0], rax
0x180025257  mov     rcx, rbx
0x18002525a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002525f  mov     [rbx+8], r12
0x180025263  lea     rax, aHidsetupAccess_5; "hidSetup/accessoryTitle"
0x18002526a  mov     [rbx+10h], r12
0x18002526e  mov     [rbp+70h+var_B8], rbx
0x180025272  lea     rbx, [rdi+1A0h]
0x180025279  mov     rcx, rbx
0x18002527c  mov     [rbp+70h+var_B0], rax
0x180025280  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180025285  mov     [rbx+8], r12
0x180025289  lea     rax, aHidsetupAccess; "hidSetup/accessoryName"
0x180025290  mov     [rbx+10h], r12
0x180025294  mov     [rbp+70h+var_A8], rbx
0x180025298  lea     rbx, [rdi+1B8h]
0x18002529f  mov     rcx, rbx
0x1800252a2  mov     [rbp+70h+var_A0], rax
0x1800252a6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800252ab  mov     [rbx+8], r12
0x1800252af  lea     rax, aHidsetupAccess_1; "hidSetup/accessoryImagePath"
0x1800252b6  mov     [rbx+10h], r12
0x1800252ba  mov     [rbp+70h+var_98], rbx
0x1800252be  lea     rbx, [rdi+1D0h]
0x1800252c5  mov     rcx, rbx
0x1800252c8  mov     [rbp+70h+var_90], rax
0x1800252cc  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800252d1  mov     [rbx+8], r12
0x1800252d5  lea     rax, aHidsetupAccess_6; "hidSetup/accessoryText"
0x1800252dc  mov     [rbx+10h], r12
0x1800252e0  mov     [rbp+70h+var_88], rbx
0x1800252e4  lea     rbx, [rdi+1E8h]
0x1800252eb  mov     rcx, rbx
0x1800252ee  mov     [rbp+70h+var_80], rax
0x1800252f2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800252f7  mov     [rbx+8], r12
0x1800252fb  lea     rax, aHidsetupAccess_4; "hidSetup/accessoryErrorImagePath"
0x180025302  mov     [rbx+10h], r12
0x180025306  mov     [rbp+70h+var_78], rbx
0x18002530a  lea     rbx, [rdi+200h]
0x180025311  mov     rcx, rbx
0x180025314  mov     [rbp+70h+var_70], rax
0x180025318  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002531d  mov     [rbx+8], r12
0x180025321  lea     rax, aHidsetupAccess_0; "hidSetup/accessoryErrorText"
0x180025328  mov     [rbx+10h], r12
0x18002532c  mov     [rbp+70h+var_68], rbx
0x180025330  lea     rbx, [rdi+218h]
0x180025337  mov     rcx, rbx
0x18002533a  mov     [rbp+70h+var_60], rax
0x18002533e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180025343  mov     [rbx+8], r12
0x180025347  lea     rax, aHidsetupAccess_3; "hidSetup/accessorySuccessImage"
0x18002534e  mov     [rbx+10h], r12
0x180025352  mov     [rbp+70h+var_58], rbx
0x180025356  lea     rbx, [rdi+230h]
0x18002535d  mov     rcx, rbx
0x180025360  mov     [rbp+70h+var_50], rax
0x180025364  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180025369  mov     [rbx+8], r12
0x18002536d  lea     rax, aHidsetupAccess_2; "hidSetup/accessorySuccessText"
0x180025374  mov     [rbx+10h], r12
0x180025378  mov     [rbp+70h+var_48], rbx
0x18002537c  lea     rbx, [rdi+248h]
0x180025383  mov     rcx, rbx
0x180025386  mov     [rbp+70h+var_40], rax
0x18002538a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002538f  mov     [rbx+8], r12
0x180025393  mov     [rbx+10h], r12
0x180025397  mov     [rbp+70h+var_38], rbx
0x18002539b  xor     ebx, ebx
0x18002539d  test    esi, esi
0x18002539f  js      short loc_1800253C6
0x1800253a1  cmp     ebx, 12h
0x1800253a4  jnb     short loc_1800253C6
0x1800253a6  mov     r8d, ebx
0x1800253a9  mov     rdx, r15; struct IOOBESettingsStore *
0x1800253ac  add     r8, r8
0x1800253af  mov     r9, [rsp+r8*8+170h+var_148]; unsigned __int16 **
0x1800253b4  mov     r8, [rsp+r8*8+170h+var_150]; unsigned __int16 *
0x1800253b9  call    ?_ReadOOBEXMLString@CHidPairingPlugin@@AEAAJPEAUIOOBESettingsStore@@PEBGPEAPEAG@Z; CHidPairingPlugin::_ReadOOBEXMLString(IOOBESettingsStore *,ushort const *,ushort * *)
0x1800253be  inc     ebx
0x1800253c0  mov     esi, eax
0x1800253c2  test    eax, eax
0x1800253c4  jns     short loc_1800253A1
0x1800253c6  lea     rcx, [rdi-18h]; this
0x1800253ca  call    ?_EnsureSecondaryInitializationIfNecessary@CHidPairingPlugin@@AEAAXXZ; CHidPairingPlugin::_EnsureSecondaryInitializationIfNecessary(void)
0x1800253cf  mov     eax, esi
0x1800253d1  add     rsp, 140h
0x1800253d8  pop     r15
0x1800253da  pop     r14
0x1800253dc  pop     r12
0x1800253de  pop     rdi
0x1800253df  pop     rsi
0x1800253e0  pop     rbx
0x1800253e1  pop     rbp
0x1800253e2  retn
```
