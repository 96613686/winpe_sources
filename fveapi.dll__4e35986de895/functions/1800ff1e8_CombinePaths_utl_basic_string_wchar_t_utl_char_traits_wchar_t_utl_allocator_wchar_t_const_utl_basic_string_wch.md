# CombinePaths(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x1800ff1e8`
- end: `0x1800ff505`
- name: `?CombinePaths@@YAJAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@0AEAV12@@Z`
- size: `797`
- prototype: `__int64 __fastcall(_QWORD *, __int16 **, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800ff50c`

## callees

- `0x180060196`
- `0x1800ff1e8`
- `0x1800ff88c`
- `0x1800ffa50`
- `0x1800ffb70`
- `0x1800ffbe4`
- `0x18011f010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x1800ff47a`
- `msvcrt!swprintf_s` at `0x1800ff47a`

## string_xrefs

- `0x1800ff22c`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800ff276`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800ff2a6`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800ff329`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800ff38f`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800ff403`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800ff4aa`: `onecore\base\servicing\overlayutil\read.cpp`
- `0x1800ff240`: `CombinePaths`
- `0x1800ff28a`: `CombinePaths`
- `0x1800ff2bf`: `CombinePaths`
- `0x1800ff342`: `CombinePaths`
- `0x1800ff3a6`: `CombinePaths`
- `0x1800ff41a`: `CombinePaths`
- `0x1800ff4c1`: `CombinePaths`
- `0x1800ff2cb`: `ULongAdd( static_cast<ULONG>(Path1.length()), PathLength, &PathLength)`
- `0x1800ff4cc`: `ULongAdd( static_cast<ULONG>(Path2.length()), PathLength, &PathLength)`
- `0x1800ff24c`: `Path1.length() > 0`
- `0x1800ff296`: `Path2.length() > 0`
- `0x1800ff34e`: `ModifiedPath2.resize(Path2.length())`
- `0x1800ff3b1`: `Path2.copy(ModifiedPath2.data(), Path2.length() - 1, 1)`
- `0x1800ff42f`: `FullPath.resize(PathLength)`

## pseudocode

```c
__int64 __fastcall CombinePaths(_QWORD *a1, __int16 **a2, __int64 a3)
{
  __int64 v3; // r9
  __int64 v6; // rax
  const char *v8; // rax
  const char **v9; // rdx
  __int64 v10; // r8
  __int16 *v11; // r8
  __int64 v12; // rdx
  size_t v13; // rbx
  __int16 v14; // cx
  __int16 v15; // r8
  char v16; // r14
  const char **v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rsi
  unsigned int v20; // ebx
  const wchar_t *v21; // rsi
  __int16 *v22; // rax
  const char *v24; // [rsp+30h] [rbp-89h] BYREF
  const char *v25; // [rsp+38h] [rbp-81h]
  __int64 v26; // [rsp+40h] [rbp-79h]
  const char *v27; // [rsp+48h] [rbp-71h]
  const char *v28; // [rsp+50h] [rbp-69h] BYREF
  const char *v29; // [rsp+58h] [rbp-61h]
  __int64 v30; // [rsp+60h] [rbp-59h]
  const char *v31; // [rsp+68h] [rbp-51h]
  _QWORD v32[4]; // [rsp+70h] [rbp-49h] BYREF
  int v33; // [rsp+90h] [rbp-29h] BYREF
  wchar_t *Buffer[2]; // [rsp+98h] [rbp-21h] BYREF
  _WORD v35[8]; // [rsp+A8h] [rbp-11h] BYREF
  void *v36[2]; // [rsp+B8h] [rbp-1h] BYREF
  _WORD v37[8]; // [rsp+C8h] [rbp+Fh] BYREF

  v3 = a1[1];
  v33 = 0;
  v6 = (v3 - *a1) >> 1;
  if ( v6 )
  {
    v11 = *a2;
    v12 = a2[1] - *a2;
    if ( !v12 )
    {
      v26 = 157;
      v24 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
      v25 = "CombinePaths";
      v8 = "Path2.length() > 0";
      goto LABEL_3;
    }
    if ( (int)v6 + 2 < (unsigned int)v6 )
    {
      v26 = 165;
      v24 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
      v9 = &v24;
      v25 = "CombinePaths";
      v27 = "ULongAdd( static_cast<ULONG>(Path1.length()), PathLength, &PathLength)";
LABEL_29:
      v10 = 2147942934LL;
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
               &v33,
               v9,
               v10);
    }
    v13 = (unsigned int)(v6 + 2 + v12);
    if ( (unsigned int)v13 < (unsigned int)v12 )
    {
      v30 = 171;
      v28 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
      v9 = &v28;
      v29 = "CombinePaths";
      v31 = "ULongAdd( static_cast<ULONG>(Path2.length()), PathLength, &PathLength)";
      goto LABEL_29;
    }
    v14 = *(_WORD *)(v3 - 2);
    v15 = *v11;
    v16 = 0;
    v36[0] = v37;
    v36[1] = v37;
    v37[0] = 0;
    if ( v14 == 92 )
    {
      if ( v15 == 92 )
      {
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(v36) )
        {
          v26 = 182;
          v24 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
          v17 = &v24;
          v25 = "CombinePaths";
          v27 = "ModifiedPath2.resize(Path2.length())";
LABEL_17:
          v20 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                  &v33,
                  v17,
                  3221225495LL);
LABEL_27:
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v36);
          return v20;
        }
        v16 = 1;
        v18 = a2[1] - *a2;
        v19 = v18 - 1;
        if ( !v18 )
          __int2c();
        memcpy_0(v36[0], *a2 + 1, 2 * v19);
        if ( !v19 )
        {
          v32[2] = 183;
          v32[0] = "onecore\\base\\servicing\\overlayutil\\read.cpp";
          v17 = (const char **)v32;
          v32[1] = "CombinePaths";
          v32[3] = "Path2.copy(ModifiedPath2.data(), Path2.length() - 1, 1)";
          goto LABEL_17;
        }
        LODWORD(v13) = v13 - 1;
      }
    }
    else if ( v15 != 92 )
    {
      v21 = L"%ws\\%ws";
LABEL_20:
      Buffer[0] = v35;
      Buffer[1] = v35;
      v35[0] = 0;
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(Buffer) )
      {
        v22 = (__int16 *)v36[0];
        if ( !v16 )
          v22 = *a2;
        swprintf_s(Buffer[0], v13, v21, *a1, v22);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::swap(a3, Buffer);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(Buffer);
        v20 = 0;
      }
      else
      {
        v30 = 201;
        v28 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
        v29 = "CombinePaths";
        v31 = "FullPath.resize(PathLength)";
        v20 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                &v33,
                &v28,
                3221225495LL);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(Buffer);
      }
      goto LABEL_27;
    }
    v13 = (unsigned int)(v13 - 1);
    v21 = L"%ws%ws";
    goto LABEL_20;
  }
  v26 = 156;
  v24 = "onecore\\base\\servicing\\overlayutil\\read.cpp";
  v25 = "CombinePaths";
  v8 = "Path1.length() > 0";
LABEL_3:
  v27 = v8;
  v9 = &v24;
  v10 = 3221225485LL;
  return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
           &v33,
           v9,
           v10);
}

```

## disassembly

```asm
0x1800ff1e8  push    rbp
0x1800ff1ea  push    rbx
0x1800ff1eb  push    rsi
0x1800ff1ec  push    rdi
0x1800ff1ed  push    r12
0x1800ff1ef  push    r14
0x1800ff1f1  push    r15
0x1800ff1f3  lea     rbp, [rsp-27h]
0x1800ff1f8  sub     rsp, 0E0h
0x1800ff1ff  mov     rax, cs:__security_cookie
0x1800ff206  xor     rax, rsp
0x1800ff209  mov     [rbp+57h+var_38], rax
0x1800ff20d  mov     r9, [rcx+8]
0x1800ff211  mov     r12, r8
0x1800ff214  mov     rax, r9
0x1800ff217  mov     [rbp+57h+var_80], 0
0x1800ff21e  sub     rax, [rcx]
0x1800ff221  mov     rdi, rdx
0x1800ff224  sar     rax, 1
0x1800ff227  mov     r15, rcx
0x1800ff22a  jnz     short loc_1800FF267
0x1800ff22c  lea     rax, aOnecoreBaseSer; "onecore\\base\\servicing\\overlayutil\\"...
0x1800ff233  mov     [rbp+57h+var_D0], 9Ch
0x1800ff23b  mov     [rsp+110h+var_E0], rax
0x1800ff240  lea     rax, aCombinepaths; "CombinePaths"
0x1800ff247  mov     [rsp+110h+var_D8], rax
0x1800ff24c  lea     rax, aPath1Length0; "Path1.length() > 0"
0x1800ff253  mov     [rbp+57h+var_C8], rax
0x1800ff257  lea     rdx, [rsp+110h+var_E0]
0x1800ff25c  mov     r8d, 0C000000Dh
0x1800ff262  jmp     loc_1800FF4DD
0x1800ff267  mov     r8, [rdx]
0x1800ff26a  mov     rdx, [rdx+8]
0x1800ff26e  sub     rdx, r8
0x1800ff271  sar     rdx, 1
0x1800ff274  jnz     short loc_1800FF29F
0x1800ff276  lea     rax, aOnecoreBaseSer; "onecore\\base\\servicing\\overlayutil\\"...
0x1800ff27d  mov     [rbp+57h+var_D0], 9Dh
0x1800ff285  mov     [rsp+110h+var_E0], rax
0x1800ff28a  lea     rax, aCombinepaths; "CombinePaths"
0x1800ff291  mov     [rsp+110h+var_D8], rax
0x1800ff296  lea     rax, aPath2Length0; "Path2.length() > 0"
0x1800ff29d  jmp     short loc_1800FF253
0x1800ff29f  lea     ecx, [rax+2]
0x1800ff2a2  cmp     ecx, eax
0x1800ff2a4  jnb     short loc_1800FF2DB
0x1800ff2a6  lea     rax, aOnecoreBaseSer; "onecore\\base\\servicing\\overlayutil\\"...
0x1800ff2ad  mov     [rbp+57h+var_D0], 0A5h
0x1800ff2b5  mov     [rsp+110h+var_E0], rax
0x1800ff2ba  lea     rdx, [rsp+110h+var_E0]
0x1800ff2bf  lea     rax, aCombinepaths; "CombinePaths"
0x1800ff2c6  mov     [rsp+110h+var_D8], rax
0x1800ff2cb  lea     rax, aUlongaddStatic_0; "ULongAdd( static_cast<ULONG>(Path1.leng"...
0x1800ff2d2  mov     [rbp+57h+var_C8], rax
0x1800ff2d6  jmp     loc_1800FF4D7
0x1800ff2db  lea     ebx, [rcx+rdx]
0x1800ff2de  cmp     ebx, edx
0x1800ff2e0  jb      loc_1800FF4AA
0x1800ff2e6  movzx   ecx, word ptr [r9-2]
0x1800ff2eb  lea     rax, [rbp+57h+var_48]
0x1800ff2ef  movzx   r8d, word ptr [r8]
0x1800ff2f3  xor     r14b, r14b
0x1800ff2f6  mov     [rbp+57h+var_58], rax
0x1800ff2fa  lea     rax, [rbp+57h+var_48]
0x1800ff2fe  mov     [rbp+57h+var_50], rax
0x1800ff302  xor     eax, eax
0x1800ff304  mov     [rbp+57h+var_48], ax
0x1800ff308  cmp     cx, 5Ch ; '\'
0x1800ff30c  jnz     loc_1800FF44C
0x1800ff312  cmp     r8w, cx
0x1800ff316  jnz     loc_1800FF3D4
0x1800ff31c  lea     rcx, [rbp+57h+var_58]
0x1800ff320  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x1800ff325  test    al, al
0x1800ff327  jnz     short loc_1800FF35B
0x1800ff329  lea     rax, aOnecoreBaseSer; "onecore\\base\\servicing\\overlayutil\\"...
0x1800ff330  mov     [rbp+57h+var_D0], 0B6h
0x1800ff338  mov     [rsp+110h+var_E0], rax
0x1800ff33d  lea     rdx, [rsp+110h+var_E0]
0x1800ff342  lea     rax, aCombinepaths; "CombinePaths"
0x1800ff349  mov     [rsp+110h+var_D8], rax
0x1800ff34e  lea     rax, aModifiedpath2R; "ModifiedPath2.resize(Path2.length())"
0x1800ff355  mov     [rbp+57h+var_C8], rax
0x1800ff359  jmp     short loc_1800FF3BC
0x1800ff35b  mov     rdx, [rdi]
0x1800ff35e  mov     r14d, 1
0x1800ff364  mov     rax, [rdi+8]
0x1800ff368  sub     rax, rdx
0x1800ff36b  sar     rax, 1
0x1800ff36e  lea     rsi, [rax-1]
0x1800ff372  cmp     rax, r14
0x1800ff375  jnb     short loc_1800FF379
0x1800ff377  int     2Ch; Windows NT - assertion failure
0x1800ff379  mov     rcx, [rbp+57h+var_58]; void *
0x1800ff37d  lea     r8, [rsi+rsi]; Size
0x1800ff381  add     rdx, 2; Src
0x1800ff385  call    memcpy_0
0x1800ff38a  test    rsi, rsi
0x1800ff38d  jnz     short loc_1800FF3D2
0x1800ff38f  lea     rax, aOnecoreBaseSer; "onecore\\base\\servicing\\overlayutil\\"...
0x1800ff396  mov     [rbp+57h+var_90], 0B7h
0x1800ff39e  mov     [rbp+57h+var_A0], rax
0x1800ff3a2  lea     rdx, [rbp+57h+var_A0]
0x1800ff3a6  lea     rax, aCombinepaths; "CombinePaths"
0x1800ff3ad  mov     [rbp+57h+var_98], rax
0x1800ff3b1  lea     rax, aPath2CopyModif; "Path2.copy(ModifiedPath2.data(), Path2."...
0x1800ff3b8  mov     [rbp+57h+var_88], rax
0x1800ff3bc  mov     r8d, 0C0000017h
0x1800ff3c2  lea     rcx, [rbp+57h+var_80]
0x1800ff3c6  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800ff3cb  mov     ebx, eax
0x1800ff3cd  jmp     loc_1800FF49D
0x1800ff3d2  dec     ebx
0x1800ff3d4  dec     ebx
0x1800ff3d6  lea     rsi, aWsWs; "%ws%ws"
0x1800ff3dd  lea     rax, [rbp+57h+var_68]
0x1800ff3e1  mov     rdx, rbx
0x1800ff3e4  mov     [rbp+57h+Buffer], rax
0x1800ff3e8  lea     rcx, [rbp+57h+Buffer]
0x1800ff3ec  lea     rax, [rbp+57h+var_68]
0x1800ff3f0  mov     [rbp+57h+var_70], rax
0x1800ff3f4  xor     eax, eax
0x1800ff3f6  mov     [rbp+57h+var_68], ax
0x1800ff3fa  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x1800ff3ff  test    al, al
0x1800ff401  jnz     short loc_1800FF45C
0x1800ff403  lea     rax, aOnecoreBaseSer; "onecore\\base\\servicing\\overlayutil\\"...
0x1800ff40a  mov     [rbp+57h+var_B0], 0C9h
0x1800ff412  mov     [rbp+57h+var_C0], rax
0x1800ff416  lea     rdx, [rbp+57h+var_C0]
0x1800ff41a  lea     rax, aCombinepaths; "CombinePaths"
0x1800ff421  mov     r8d, 0C0000017h
0x1800ff427  mov     [rbp+57h+var_B8], rax
0x1800ff42b  lea     rcx, [rbp+57h+var_80]
0x1800ff42f  lea     rax, aFullpathResize; "FullPath.resize(PathLength)"
0x1800ff436  mov     [rbp+57h+var_A8], rax
0x1800ff43a  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800ff43f  lea     rcx, [rbp+57h+Buffer]
0x1800ff443  mov     ebx, eax
0x1800ff445  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x1800ff44a  jmp     short loc_1800FF49D
0x1800ff44c  cmp     r8w, 5Ch ; '\'
0x1800ff451  jz      short loc_1800FF3D4
0x1800ff453  lea     rsi, aWsWs_0; "%ws\\%ws"
0x1800ff45a  jmp     short loc_1800FF3DD
0x1800ff45c  mov     rax, [rbp+57h+var_58]
0x1800ff460  test    r14b, r14b
0x1800ff463  jnz     short loc_1800FF468
0x1800ff465  mov     rax, [rdi]
0x1800ff468  mov     r9, [r15]
0x1800ff46b  mov     r8, rsi; Format
0x1800ff46e  mov     rcx, [rbp+57h+Buffer]; Buffer
0x1800ff472  mov     rdx, rbx; BufferCount
0x1800ff475  mov     [rsp+110h+var_F0], rax
0x1800ff47a  call    cs:__imp_swprintf_s
0x1800ff481  nop     dword ptr [rax+rax+00h]
0x1800ff486  lea     rdx, [rbp+57h+Buffer]
0x1800ff48a  mov     rcx, r12
0x1800ff48d  call    ?swap@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAXAEAV12@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::swap(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800ff492  lea     rcx, [rbp+57h+Buffer]
0x1800ff496  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x1800ff49b  xor     ebx, ebx
0x1800ff49d  lea     rcx, [rbp+57h+var_58]
0x1800ff4a1  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x1800ff4a6  mov     eax, ebx
0x1800ff4a8  jmp     short loc_1800FF4E6
0x1800ff4aa  lea     rax, aOnecoreBaseSer; "onecore\\base\\servicing\\overlayutil\\"...
0x1800ff4b1  mov     [rbp+57h+var_B0], 0ABh
0x1800ff4b9  mov     [rbp+57h+var_C0], rax
0x1800ff4bd  lea     rdx, [rbp+57h+var_C0]
0x1800ff4c1  lea     rax, aCombinepaths; "CombinePaths"
0x1800ff4c8  mov     [rbp+57h+var_B8], rax
0x1800ff4cc  lea     rax, aUlongaddStatic; "ULongAdd( static_cast<ULONG>(Path2.leng"...
0x1800ff4d3  mov     [rbp+57h+var_A8], rax
0x1800ff4d7  mov     r8d, 80070216h
0x1800ff4dd  lea     rcx, [rbp+57h+var_80]
0x1800ff4e1  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800ff4e6  mov     rcx, [rbp+57h+var_38]
0x1800ff4ea  xor     rcx, rsp; StackCookie
0x1800ff4ed  call    __security_check_cookie
0x1800ff4f2  add     rsp, 0E0h
0x1800ff4f9  pop     r15
0x1800ff4fb  pop     r14
0x1800ff4fd  pop     r12
0x1800ff4ff  pop     rdi
0x1800ff500  pop     rsi
0x1800ff501  pop     rbx
0x1800ff502  pop     rbp
0x1800ff503  retn
```
