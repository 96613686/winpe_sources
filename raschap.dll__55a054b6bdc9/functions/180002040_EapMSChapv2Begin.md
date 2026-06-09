# EapMSChapv2Begin

- ea: `0x180002040`
- end: `0x180002522`
- name: `EapMSChapv2Begin`
- size: `1250`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001210`
- `0x1800014c0`
- `0x180001520`
- `0x180002040`
- `0x180002530`
- `0x180002954`
- `0x180003bd0`
- `0x180004df0`
- `0x180006a20`
- `0x18000e120`
- `0x180014610`
- `0x1800147cc`
- `0x180025ee4`
- `0x180025efc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180002487`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180002487`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002357`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002415`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800024be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800024cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800024d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002357`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002415`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800024be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800024cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800024d4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000209a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002149`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000217b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002258`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000231a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000209a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002149`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000217b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002258`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000231a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000220a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000220a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000226a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000226a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002328`
- `ext-ms-win-raschapext-eap-l1-1-0!RasChapExt_GetConfigForceNotDomainJoined` at `0x180002396`
- `ext-ms-win-raschapext-eap-l1-1-0!RasChapExt_GetConfigForceNotDomainJoined` at `0x180002396`

## pseudocode

```c
__int64 __fastcall EapMSChapv2Begin(__int64 *a1, __int64 a2)
{
  HLOCAL v4; // rax
  __int64 v5; // rdi
  unsigned int UserData; // esi
  HLOCAL *v7; // r14
  SIZE_T v8; // rdx
  unsigned int v9; // ecx
  unsigned int v10; // esi
  HLOCAL v11; // rax
  _DWORD *v12; // rax
  const WCHAR *v13; // rsi
  SIZE_T v14; // rsi
  const void *v15; // r12
  int v16; // ebp
  size_t v17; // rbp
  _DWORD *v18; // rax
  _DWORD *v19; // rsi
  DWORD LastError; // eax
  DWORD v21; // ebp
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  unsigned int v24; // eax
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // r9
  _DWORD *v28; // rax
  int v29; // r12d
  DWORD v30; // eax
  __int64 v31; // r8
  _BYTE *v32; // rcx
  __int64 v33; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids);
  v4 = LocalAlloc(0x40u, 0x550u);
  v5 = (__int64)v4;
  if ( !v4 )
  {
    UserData = 8;
LABEL_76:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids, UserData);
    return UserData;
  }
  memset_0(v4, 0, 0x550u);
  if ( (*(_BYTE *)(a2 + 4) & 0x20) != 0 )
    *(_DWORD *)(v5 + 4) |= 8u;
  if ( (*(_DWORD *)(a2 + 4) & 0x800) != 0 )
    *(_DWORD *)(v5 + 4) |= 0x40u;
  if ( (*(_BYTE *)(a2 + 4) & 4) != 0 )
    *(_DWORD *)(v5 + 4) |= 0x80u;
  if ( (*(_BYTE *)(a2 + 4) & 2) != 0 )
    *(_DWORD *)(v5 + 4) |= 0x100u;
  if ( *(_DWORD *)(a2 + 8) )
  {
    if ( *(_QWORD *)(a2 + 88) && *(_DWORD *)(a2 + 96) >= 0x314u )
    {
      if ( !(unsigned int)IsMschapV2UserDataValid() )
      {
        UserData = 13;
        v7 = (HLOCAL *)(v5 + 24);
LABEL_71:
        if ( *v7 )
        {
          LODWORD(v33) = MschapV2UserPropBuffSize(*v7);
          v32 = *v7;
          v33 = (unsigned int)v33;
          if ( (_DWORD)v33 )
          {
            do
            {
              *v32++ = 0;
              --v33;
            }
            while ( v33 );
          }
          LocalFree(*v7);
        }
        LocalFree(*(HLOCAL *)(v5 + 1320));
        LocalFree((HLOCAL)v5);
        goto LABEL_76;
      }
      v8 = 0xFFFFFFFFLL;
      v9 = *(_DWORD *)(*(_QWORD *)(a2 + 88) + 784LL);
      if ( v9 + 788 >= v9 )
        v8 = v9 + 788;
      v10 = v8;
      v11 = LocalAlloc(0x40u, v8);
      *(_QWORD *)(v5 + 24) = v11;
      v7 = (HLOCAL *)(v5 + 24);
      if ( v11 )
      {
        memcpy_0(v11, *(const void **)(a2 + 88), v10);
LABEL_24:
        v7 = (HLOCAL *)(v5 + 24);
        goto LABEL_25;
      }
    }
    else
    {
      v12 = LocalAlloc(0x40u, 0x314u);
      *(_QWORD *)(v5 + 24) = v12;
      v7 = (HLOCAL *)(v5 + 24);
      if ( v12 )
      {
        *v12 = 3;
        *((_DWORD *)*v7 + 2) = 2;
        *((_DWORD *)*v7 + 1) |= 4u;
        goto LABEL_24;
      }
    }
    UserData = -2147024882;
    goto LABEL_71;
  }
  v7 = (HLOCAL *)(v5 + 24);
  UserData = ReadUserData(*(void **)(a2 + 104), *(unsigned int *)(a2 + 112));
  if ( UserData )
    goto LABEL_71;
  v24 = EapMsChapv2DecryptPassword((__int64)*v7, *(void **)(a2 + 56));
  UserData = v24;
  if ( v24 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_71;
    v26 = 16;
    v27 = v24;
LABEL_41:
    WPP_SF_d(v25[2], v26, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids, v27);
    goto LABEL_71;
  }
LABEL_25:
  if ( *(char *)(a2 + 4) >= 0 )
  {
    v13 = *(const WCHAR **)(a2 + 24);
    if ( v13 )
    {
      if ( *v13 && wcscmp_0(*(const wchar_t **)(a2 + 24), L"****************") )
        WideCharToMultiByte(0, 0, v13, -1, (LPSTR)*v7 + 269, 257, 0, 0);
    }
  }
  v14 = *(unsigned int *)(a2 + 96);
  v15 = *(const void **)(a2 + 88);
  v16 = *(_DWORD *)(a2 + 4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids);
  if ( (unsigned int)v14 >= 8 && v15 )
  {
    v17 = v14;
    v18 = LocalAlloc(0x40u, v14);
    v19 = v18;
    if ( !v18 )
    {
      LastError = GetLastError();
      v21 = LastError;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_48;
      v23 = 14;
      goto LABEL_47;
    }
    memcpy_0(v18, v15, v17);
    if ( !(unsigned int)IsLogonCredAllowed() )
      v19[1] &= ~2u;
LABEL_63:
    *(_QWORD *)(v5 + 1320) = v19;
    LocalFree(0);
    goto LABEL_64;
  }
  v28 = LocalAlloc(0x40u, 8u);
  v19 = v28;
  if ( v28 )
  {
    v29 = 0;
    *v28 = 1;
    if ( (unsigned __int8)IsRasChapExt_GetConfigIgnoreIASLogonPresent() )
    {
      if ( !(unsigned int)RasChapExt_GetConfigForceNotDomainJoined() )
        v29 = isMachineJoinedToDomain();
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids);
    }
    if ( (v16 & 0x80u) != 0 && ((v16 & 0x20) != 0 || v29) && (unsigned int)IsLogonCredAllowed() )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids);
      v19[1] = 2;
    }
    goto LABEL_63;
  }
  LastError = GetLastError();
  v21 = LastError;
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_48;
  v23 = 11;
LABEL_47:
  WPP_SF_d(v22[2], v23, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids, LastError);
LABEL_48:
  LocalFree(0);
  if ( v21 )
  {
    UserData = v21;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_71;
    v26 = 17;
    v27 = v21;
    goto LABEL_41;
  }
LABEL_64:
  v30 = EapChapBeginCommon(
          26,
          *(_DWORD *)(*(_QWORD *)(v5 + 1320) + 4LL) & 2,
          *((_DWORD *)*v7 + 2),
          v5,
          (_QWORD *)(v5 + 1328),
          a2);
  UserData = v30;
  if ( v30 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_71;
    v26 = 18;
    v27 = v30;
    goto LABEL_41;
  }
  v31 = *(_QWORD *)(a2 + 16);
  if ( v31 )
    _o_wcsncpy_s(v5 + 290, 513, v31, 512);
  *a1 = v5;
  return UserData;
}

```

## disassembly

```asm
0x180002040  push    rbx
0x180002042  push    rdi
0x180002043  push    r13
0x180002045  push    r15
0x180002047  sub     rsp, 48h
0x18000204b  mov     rbx, rdx
0x18000204e  mov     r15, rcx
0x180002051  mov     rcx, cs:WPP_GLOBAL_Control
0x180002058  lea     r13, WPP_GLOBAL_Control
0x18000205f  cmp     rcx, r13
0x180002062  jz      short loc_180002079
0x180002064  mov     rcx, [rcx+10h]
0x180002068  lea     r8, WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids
0x18000206f  mov     edx, 0Fh
0x180002074  call    WPP_SF_
0x180002079  mov     [rsp+68h+arg_0], rbp
0x18000207e  mov     edx, 550h; uBytes
0x180002083  mov     [rsp+68h+arg_8], rsi
0x180002088  mov     ecx, 40h ; '@'; uFlags
0x18000208d  mov     [rsp+68h+arg_10], r12
0x180002095  mov     [rsp+68h+var_28], r14
0x18000209a  call    cs:__imp_LocalAlloc
0x1800020a0  mov     rdi, rax
0x1800020a3  test    rax, rax
0x1800020a6  jnz     short loc_1800020B2
0x1800020a8  mov     esi, 8
0x1800020ad  jmp     loc_1800024DA
0x1800020b2  xor     edx, edx; Val
0x1800020b4  mov     r8d, 550h; Size
0x1800020ba  mov     rcx, rdi; void *
0x1800020bd  call    memset_0
0x1800020c2  test    byte ptr [rbx+4], 20h
0x1800020c6  jz      short loc_1800020CC
0x1800020c8  or      dword ptr [rdi+4], 8
0x1800020cc  test    dword ptr [rbx+4], 800h
0x1800020d3  jz      short loc_1800020D9
0x1800020d5  or      dword ptr [rdi+4], 40h
0x1800020d9  test    byte ptr [rbx+4], 4
0x1800020dd  jz      short loc_1800020E6
0x1800020df  or      dword ptr [rdi+4], 80h
0x1800020e6  test    byte ptr [rbx+4], 2
0x1800020ea  jz      short loc_1800020F3
0x1800020ec  or      dword ptr [rdi+4], 100h
0x1800020f3  cmp     dword ptr [rbx+8], 0
0x1800020f7  jz      loc_18000228C
0x1800020fd  mov     rcx, [rbx+58h]
0x180002101  test    rcx, rcx
0x180002104  jz      short loc_180002171
0x180002106  mov     edx, [rbx+60h]
0x180002109  cmp     edx, 314h
0x18000210f  jb      short loc_180002171
0x180002111  call    IsMschapV2UserDataValid
0x180002116  test    eax, eax
0x180002118  jnz     short loc_180002128
0x18000211a  mov     esi, 0Dh
0x18000211f  lea     r14, [rdi+18h]
0x180002123  jmp     loc_180002497
0x180002128  mov     rax, [rbx+58h]
0x18000212c  mov     edx, 0FFFFFFFFh
0x180002131  mov     ecx, [rax+310h]
0x180002137  lea     eax, [rcx+314h]
0x18000213d  cmp     eax, ecx
0x18000213f  mov     ecx, 40h ; '@'; uFlags
0x180002144  cmovnb  edx, eax; uBytes
0x180002147  mov     esi, edx
0x180002149  call    cs:__imp_LocalAlloc
0x18000214f  mov     [rdi+18h], rax
0x180002153  lea     r14, [rdi+18h]
0x180002157  test    rax, rax
0x18000215a  jz      loc_180002492
0x180002160  mov     rdx, [rbx+58h]; Src
0x180002164  mov     r8d, esi; Size
0x180002167  mov     rcx, rax; void *
0x18000216a  call    memcpy_0
0x18000216f  jmp     short loc_1800021A9
0x180002171  mov     edx, 314h; uBytes
0x180002176  mov     ecx, 40h ; '@'; uFlags
0x18000217b  call    cs:__imp_LocalAlloc
0x180002181  mov     [rdi+18h], rax
0x180002185  lea     r14, [rdi+18h]
0x180002189  test    rax, rax
0x18000218c  jz      loc_180002492
0x180002192  mov     dword ptr [rax], 3
0x180002198  mov     rax, [r14]
0x18000219b  mov     dword ptr [rax+8], 2
0x1800021a2  mov     rax, [r14]
0x1800021a5  or      dword ptr [rax+4], 4
0x1800021a9  lea     r14, [rdi+18h]
0x1800021ad  test    byte ptr [rbx+4], 80h
0x1800021b1  jnz     short loc_180002210
0x1800021b3  mov     rsi, [rbx+18h]
0x1800021b7  test    rsi, rsi
0x1800021ba  jz      short loc_180002210
0x1800021bc  cmp     word ptr [rsi], 0
0x1800021c0  jz      short loc_180002210
0x1800021c2  lea     rdx, String2; "****************"
0x1800021c9  mov     rcx, rsi; String1
0x1800021cc  call    wcscmp_0
0x1800021d1  test    eax, eax
0x1800021d3  jz      short loc_180002210
0x1800021d5  mov     rax, [r14]
0x1800021d8  mov     r9d, 0FFFFFFFFh; cchWideChar
0x1800021de  mov     [rsp+68h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800021e7  add     rax, 10Dh
0x1800021ed  mov     [rsp+68h+lpDefaultChar], 0; lpDefaultChar
0x1800021f6  mov     r8, rsi; lpWideCharStr
0x1800021f9  mov     [rsp+68h+cbMultiByte], 101h; cbMultiByte
0x180002201  xor     edx, edx; dwFlags
0x180002203  xor     ecx, ecx; CodePage
0x180002205  mov     [rsp+68h+lpMultiByteStr], rax; lpMultiByteStr
0x18000220a  call    cs:__imp_WideCharToMultiByte
0x180002210  mov     esi, [rbx+60h]
0x180002213  mov     r12, [rbx+58h]
0x180002217  mov     ebp, [rbx+4]
0x18000221a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002221  cmp     rcx, r13
0x180002224  jz      short loc_18000223B
0x180002226  mov     rcx, [rcx+10h]
0x18000222a  lea     r8, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x180002231  mov     edx, 0Ah
0x180002236  call    WPP_SF_
0x18000223b  cmp     esi, 8
0x18000223e  jb      loc_180002310
0x180002244  test    r12, r12
0x180002247  jz      loc_180002310
0x18000224d  mov     rdx, rsi; uBytes
0x180002250  mov     ecx, 40h ; '@'; uFlags
0x180002255  mov     rbp, rsi
0x180002258  call    cs:__imp_LocalAlloc
0x18000225e  mov     rsi, rax
0x180002261  test    rax, rax
0x180002264  jnz     loc_1800022EC
0x18000226a  call    cs:__imp_GetLastError
0x180002270  mov     ebp, eax
0x180002272  mov     rcx, cs:WPP_GLOBAL_Control
0x180002279  cmp     rcx, r13
0x18000227c  jz      loc_180002354
0x180002282  mov     edx, 0Eh
0x180002287  jmp     loc_180002341
0x18000228c  mov     edx, [rbx+70h]; Size
0x18000228f  lea     r14, [rdi+18h]
0x180002293  mov     rcx, [rbx+68h]; Src
0x180002297  mov     r8, r14
0x18000229a  call    ReadUserData
0x18000229f  mov     esi, eax
0x1800022a1  test    eax, eax
0x1800022a3  jnz     loc_180002497
0x1800022a9  mov     rdx, [rbx+38h]
0x1800022ad  mov     rcx, [r14]
0x1800022b0  call    EapMsChapv2DecryptPassword
0x1800022b5  mov     esi, eax
0x1800022b7  test    eax, eax
0x1800022b9  jz      loc_1800021AD
0x1800022bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800022c6  cmp     rcx, r13
0x1800022c9  jz      loc_180002497
0x1800022cf  mov     edx, 10h
0x1800022d4  mov     r9d, eax
0x1800022d7  mov     rcx, [rcx+10h]
0x1800022db  lea     r8, WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids
0x1800022e2  call    WPP_SF_d
0x1800022e7  jmp     loc_180002497
0x1800022ec  mov     r8, rbp; Size
0x1800022ef  mov     rdx, r12; Src
0x1800022f2  mov     rcx, rsi; void *
0x1800022f5  call    memcpy_0
0x1800022fa  call    IsLogonCredAllowed
0x1800022ff  test    eax, eax
0x180002301  jnz     loc_18000240C
0x180002307  and     dword ptr [rsi+4], 0FFFFFFFDh
0x18000230b  jmp     loc_18000240C
0x180002310  mov     edx, 8; uBytes
0x180002315  mov     ecx, 40h ; '@'; uFlags
0x18000231a  call    cs:__imp_LocalAlloc
0x180002320  mov     rsi, rax
0x180002323  test    rax, rax
0x180002326  jnz     short loc_180002384
0x180002328  call    cs:__imp_GetLastError
0x18000232e  mov     ebp, eax
0x180002330  mov     rcx, cs:WPP_GLOBAL_Control
0x180002337  cmp     rcx, r13
0x18000233a  jz      short loc_180002354
0x18000233c  mov     edx, 0Bh
0x180002341  mov     rcx, [rcx+10h]
0x180002345  lea     r8, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x18000234c  mov     r9d, eax
0x18000234f  call    WPP_SF_d
0x180002354  mov     rcx, rsi; hMem
0x180002357  call    cs:__imp_LocalFree
0x18000235d  test    ebp, ebp
0x18000235f  jz      loc_18000241B
0x180002365  mov     esi, ebp
0x180002367  mov     rcx, cs:WPP_GLOBAL_Control
0x18000236e  cmp     rcx, r13
0x180002371  jz      loc_180002497
0x180002377  mov     edx, 11h
0x18000237c  mov     r9d, ebp
0x18000237f  jmp     loc_1800022D7
0x180002384  xor     r12d, r12d
0x180002387  mov     dword ptr [rax], 1
0x18000238d  call    IsRasChapExt_GetConfigIgnoreIASLogonPresent
0x180002392  test    al, al
0x180002394  jz      short loc_1800023AA
0x180002396  call    cs:__imp_RasChapExt_GetConfigForceNotDomainJoined
0x18000239c  test    eax, eax
0x18000239e  jnz     short loc_1800023CB
0x1800023a0  call    isMachineJoinedToDomain
0x1800023a5  mov     r12d, eax
0x1800023a8  jmp     short loc_1800023CB
0x1800023aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023b1  cmp     rcx, r13
0x1800023b4  jz      short loc_1800023CB
0x1800023b6  mov     rcx, [rcx+10h]
0x1800023ba  lea     r8, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x1800023c1  mov     edx, 0Ch
0x1800023c6  call    WPP_SF_
0x1800023cb  test    bpl, bpl
0x1800023ce  jns     short loc_18000240C
0x1800023d0  test    bpl, 20h
0x1800023d4  jnz     short loc_1800023DB
0x1800023d6  test    r12d, r12d
0x1800023d9  jz      short loc_18000240C
0x1800023db  call    IsLogonCredAllowed
0x1800023e0  test    eax, eax
0x1800023e2  jz      short loc_18000240C
0x1800023e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023eb  cmp     rcx, r13
0x1800023ee  jz      short loc_180002405
0x1800023f0  mov     rcx, [rcx+10h]
0x1800023f4  lea     r8, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x1800023fb  mov     edx, 0Dh
0x180002400  call    WPP_SF_
0x180002405  mov     dword ptr [rsi+4], 2
0x18000240c  xor     ecx, ecx; hMem
0x18000240e  mov     [rdi+528h], rsi
0x180002415  call    cs:__imp_LocalFree
0x18000241b  mov     rax, [rdi+528h]
0x180002422  lea     rcx, [rdi+530h]
0x180002429  mov     r8, [r14]
0x18000242c  mov     r9, rdi
0x18000242f  mov     qword ptr [rsp+68h+cbMultiByte], rbx
0x180002434  mov     [rsp+68h+lpMultiByteStr], rcx
0x180002439  mov     ecx, 1Ah
0x18000243e  mov     edx, [rax+4]
0x180002441  mov     r8d, [r8+8]
0x180002445  and     edx, 2
0x180002448  call    EapChapBeginCommon
0x18000244d  mov     esi, eax
0x18000244f  test    eax, eax
0x180002451  jz      short loc_18000246C
0x180002453  mov     rcx, cs:WPP_GLOBAL_Control
0x18000245a  cmp     rcx, r13
0x18000245d  jz      short loc_180002497
0x18000245f  mov     edx, 12h
0x180002464  mov     r9d, eax
0x180002467  jmp     loc_1800022D7
0x18000246c  mov     r8, [rbx+10h]
0x180002470  test    r8, r8
0x180002473  jz      short loc_18000248D
0x180002475  lea     rcx, [rdi+122h]
0x18000247c  mov     edx, 201h
0x180002481  mov     r9d, 200h
0x180002487  call    cs:__imp__o_wcsncpy_s
0x18000248d  mov     [r15], rdi
0x180002490  jmp     short loc_1800024FE
0x180002492  mov     esi, 8007000Eh
0x180002497  mov     rcx, [r14]
0x18000249a  test    rcx, rcx
0x18000249d  jz      short loc_1800024C4
0x18000249f  call    MschapV2UserPropBuffSize
0x1800024a4  mov     rcx, [r14]
0x1800024a7  mov     eax, eax
0x1800024a9  test    rax, rax
0x1800024ac  jz      short loc_1800024BB
0x1800024ae  mov     byte ptr [rcx], 0
0x1800024b1  lea     rcx, [rcx+1]
0x1800024b5  sub     rax, 1
0x1800024b9  jnz     short loc_1800024AE
0x1800024bb  mov     rcx, [r14]; hMem
0x1800024be  call    cs:__imp_LocalFree
0x1800024c4  mov     rcx, [rdi+528h]; hMem
0x1800024cb  call    cs:__imp_LocalFree
0x1800024d1  mov     rcx, rdi; hMem
0x1800024d4  call    cs:__imp_LocalFree
0x1800024da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024e1  cmp     rcx, r13
0x1800024e4  jz      short loc_1800024FE
0x1800024e6  mov     rcx, [rcx+10h]
0x1800024ea  lea     r8, WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids
0x1800024f1  mov     edx, 13h
0x1800024f6  mov     r9d, esi
0x1800024f9  call    WPP_SF_d
0x1800024fe  mov     r14, [rsp+68h+var_28]
0x180002503  mov     eax, esi
0x180002505  mov     rsi, [rsp+68h+arg_8]
0x18000250a  mov     r12, [rsp+68h+arg_10]
0x180002512  mov     rbp, [rsp+68h+arg_0]
0x180002517  add     rsp, 48h
0x18000251b  pop     r15
0x18000251d  pop     r13
  ... truncated ...
```
