# DDMGetRasDialingParams

- ea: `0x180068f50`
- end: `0x180069841`
- name: `DDMGetRasDialingParams`
- size: `2289`
- prototype: `__int64 __fastcall(__int64, const void *, const void **, _OWORD *, _DWORD *, __int64 *, _DWORD *, DWORD *, _OWORD *, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180001eb8`
- `0x18000b0f4`
- `0x180012f7c`
- `0x18004e580`
- `0x18004e5c0`
- `0x18004e984`
- `0x180068f50`
- `0x1800962b8`
- `0x180098d8c`
- `0x1800a55b4`
- `0x1800a64d4`
- `0x1800decee`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `msvcrt!malloc` at `0x180069182`
- `msvcrt!malloc` at `0x180069182`
- `msvcrt!wcsstr` at `0x180069040`
- `msvcrt!wcsstr` at `0x18006908f`
- `msvcrt!wcsstr` at `0x180069040`
- `msvcrt!wcsstr` at `0x18006908f`
- `msvcrt!_wcsicmp` at `0x18006905f`
- `msvcrt!_wcsicmp` at `0x1800690a5`
- `msvcrt!_wcsicmp` at `0x18006905f`
- `msvcrt!_wcsicmp` at `0x1800690a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800695f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800695f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006960a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006960a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800697c2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800697c2`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800694d5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800694d5`

## pseudocode

```c
__int64 __fastcall DDMGetRasDialingParams(
        __int64 a1,
        const void *a2,
        const void **a3,
        _OWORD *a4,
        _DWORD *a5,
        __int64 *a6,
        _DWORD *a7,
        DWORD *a8,
        _OWORD *a9,
        __int64 a10)
{
  wchar_t *v14; // rax
  wchar_t *v15; // rdi
  wchar_t *v16; // rax
  __int64 SizedNode; // rax
  __int64 v18; // r15
  _QWORD *v19; // rcx
  __int64 v21; // rdi
  void *v22; // rax
  __int64 v23; // r8
  _OWORD *v24; // rax
  __int64 v25; // rcx
  __int128 v26; // xmm1
  __int64 v27; // rax
  unsigned int v28; // ebx
  _QWORD *v29; // rcx
  _UNKNOWN **v30; // rdx
  int v31; // esi
  unsigned int v32; // ebx
  unsigned int v33; // ebx
  unsigned int v34; // ebx
  unsigned int v35; // ebx
  unsigned int v36; // ebx
  unsigned int v37; // ebx
  unsigned int v38; // ebx
  unsigned int v39; // ebx
  unsigned int v40; // ebx
  _WORD *v41; // rdx
  __int64 v42; // rax
  size_t v43; // rbx
  HRESULT Guid; // eax
  _QWORD *v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // r9
  int v48; // ecx
  HLOCAL v49; // rax
  void *v50; // rcx
  DWORD LastError; // eax
  unsigned int v52; // eax
  _DWORD *v53; // rax
  int v54; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v55; // [rsp+28h] [rbp-D8h]
  __int64 *v56; // [rsp+30h] [rbp-D0h]
  _DWORD *v57; // [rsp+38h] [rbp-C8h]
  DWORD *v58; // [rsp+40h] [rbp-C0h]
  _OWORD *v59; // [rsp+48h] [rbp-B8h]
  _DWORD Src[258]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Str[514]; // [rsp+45Ah] [rbp+35Ah] BYREF
  wchar_t String1[8]; // [rsp+85Eh] [rbp+75Eh] BYREF
  __int128 v63; // [rsp+86Eh] [rbp+76Eh]
  int v64; // [rsp+880h] [rbp+780h]

  v56 = a6;
  v57 = a7;
  v58 = a8;
  v59 = a9;
  v55 = a10;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 1167, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids);
  }
  v54 = 0;
  memcpy_0(Src, a2, 0x848u);
  Src[0] = 2120;
  if ( String1[0] )
  {
    v14 = wcsstr(Str, L"\\");
    v15 = v14;
    if ( v14 )
    {
      *v14 = 0;
      if ( !_wcsicmp(String1, Str) )
      {
        *(_OWORD *)String1 = 0;
        v63 = 0;
      }
      *v15 = 92;
    }
    else
    {
      v16 = wcsstr(Str, L"@");
      if ( v16 && !_wcsicmp(String1, v16 + 1) )
      {
        *(_OWORD *)String1 = 0;
        v63 = 0;
      }
    }
  }
  SizedNode = DtlCreateSizedNode(5648, 0);
  v18 = SizedNode;
  if ( !SizedNode )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1168, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 8);
        v19 = WPP_GLOBAL_Control;
      }
      if ( v19 != &WPP_GLOBAL_Control && (*((_DWORD *)v19 + 7) & 0x800) != 0 && *((_BYTE *)v19 + 25) >= 6u )
        WPP_SF_d(v19[2], 1169, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 8);
    }
    return 8;
  }
  v21 = *(_QWORD *)(SizedNode + 16);
  memset_0((void *)v21, 0, 0x1610u);
  *(_QWORD *)(v21 + 5472) = v21 + 5464;
  *(_QWORD *)(v21 + 5464) = v21 + 5464;
  *(_QWORD *)(v21 + 24) = v21 + 16;
  *(_QWORD *)(v21 + 16) = v21 + 16;
  v22 = malloc(0x3F0u);
  *(_QWORD *)(v21 + 1584) = v22;
  memset_0(v22, 0, 0x3F0u);
  v24 = *(_OWORD **)(v21 + 1584);
  v25 = 7;
  do
  {
    *v24 = *a4;
    v24[1] = a4[1];
    v24[2] = a4[2];
    v24[3] = a4[3];
    v24[4] = a4[4];
    v24[5] = a4[5];
    v24[6] = a4[6];
    v26 = a4[7];
    a4 += 8;
    v24[7] = v26;
    v24 += 8;
    --v25;
  }
  while ( v25 );
  *v24 = *a4;
  v24[1] = a4[1];
  v24[2] = a4[2];
  v24[3] = a4[3];
  v24[4] = a4[4];
  v24[5] = a4[5];
  v24[6] = a4[6];
  *(_DWORD *)(v21 + 5460) = 0;
  *(_DWORD *)(v21 + 5496) = 0;
  v64 = 1;
  *(_QWORD *)(v21 + 3732) = 0;
  v27 = *(_QWORD *)(v21 + 1584);
  *(_DWORD *)(v21 + 3744) = 2;
  v28 = *(_DWORD *)(v27 + 168);
  v29 = WPP_GLOBAL_Control;
  v30 = &WPP_GLOBAL_Control;
  LOBYTE(v23) = 5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1170, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v28);
    v29 = WPP_GLOBAL_Control;
    v30 = &WPP_GLOBAL_Control;
    LOBYTE(v23) = 5;
  }
  v31 = 8;
  if ( v28 <= 7 )
  {
    if ( v28 != 7 )
    {
      v32 = v28 - 1;
      if ( v32 )
      {
        v33 = v32 - 1;
        if ( v33 )
        {
          v34 = v33 - 1;
          if ( v34 )
          {
            v35 = v34 - 1;
            if ( v35 )
            {
              if ( v35 - 1 <= 1 )
              {
                if ( v29 != &WPP_GLOBAL_Control && (*((_DWORD *)v29 + 7) & 0x800) != 0 && *((_BYTE *)v29 + 25) >= 5u )
                  WPP_SF_(v29[2], 1172, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids);
                v31 = 14;
                goto LABEL_74;
              }
LABEL_46:
              if ( v29 != &WPP_GLOBAL_Control && (*((_DWORD *)v29 + 7) & 0x800) != 0 && *((_BYTE *)v29 + 25) >= 5u )
              {
                WPP_SF_(v29[2], 1176, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids);
                v29 = WPP_GLOBAL_Control;
                v30 = &WPP_GLOBAL_Control;
              }
              v40 = 87;
              if ( v29 != &WPP_GLOBAL_Control && (*((_DWORD *)v29 + 7) & 0x800) != 0 && *((_BYTE *)v29 + 25) >= 2u )
                WPP_SF_d(v29[2], 1177, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, 87);
              goto LABEL_54;
            }
          }
          goto LABEL_55;
        }
      }
      goto LABEL_60;
    }
    goto LABEL_69;
  }
  v36 = v28 - 8;
  if ( !v36 )
  {
LABEL_69:
    if ( v29 != &WPP_GLOBAL_Control && (*((_DWORD *)v29 + 7) & 0x800) != 0 && *((_BYTE *)v29 + 25) >= 5u )
      WPP_SF_(v29[2], 1174, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids);
    v31 = 15;
    goto LABEL_74;
  }
  v37 = v36 - 1;
  if ( v37 )
  {
    v38 = v37 - 3;
    if ( !v38 )
    {
LABEL_60:
      if ( v29 != &WPP_GLOBAL_Control && (*((_DWORD *)v29 + 7) & 0x800) != 0 && *((_BYTE *)v29 + 25) >= 5u )
        WPP_SF_(v29[2], 1171, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids);
      goto LABEL_74;
    }
    v39 = v38 - 1;
    if ( !v39 )
    {
LABEL_55:
      if ( v29 != &WPP_GLOBAL_Control && (*((_DWORD *)v29 + 7) & 0x800) != 0 && *((_BYTE *)v29 + 25) >= 5u )
        WPP_SF_(v29[2], 1173, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids);
      v31 = 9;
      goto LABEL_74;
    }
    if ( v39 != 1 )
      goto LABEL_46;
    goto LABEL_69;
  }
  if ( v29 != &WPP_GLOBAL_Control && (*((_DWORD *)v29 + 7) & 0x800) != 0 && *((_BYTE *)v29 + 25) >= 5u )
    WPP_SF_(v29[2], 1175, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids);
  v31 = 16;
LABEL_74:
  *(_DWORD *)(v21 + 5408) = v31;
  *(_DWORD *)(v21 + 5424) = 0;
  if ( a3 )
  {
    v41 = *a3;
    if ( *a3 )
    {
      v42 = -1;
      do
        ++v42;
      while ( v41[v42] );
      v43 = (unsigned int)(2 * v42 + 2);
      memcpy_0((void *)(v21 + 4030), v41, v43);
      memcpy_0((void *)(v21 + 3772), *a3, (unsigned int)v43);
    }
  }
  Guid = CoCreateGuid((GUID *)(v21 + 5540));
  if ( Guid )
  {
    v40 = (unsigned __int16)Guid;
    if ( !(_WORD)Guid )
      goto LABEL_54;
    v45 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_54;
    }
    v46 = 1178;
    v47 = (unsigned __int16)Guid;
LABEL_85:
    WPP_SF_d(v45[2], v46, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v47);
LABEL_54:
    DeleteRasconncbNodeCommon(v18, v30, v23);
    Free0(v18);
    goto LABEL_117;
  }
  *(_WORD *)(v21 + 4320) = 0;
  *(_QWORD *)(v21 + 3720) = 0;
  *(_DWORD *)(v21 + 3740) = 0;
  *(_DWORD *)(v21 + 3728) = 0;
  *(_QWORD *)(v21 + 4844) = 0;
  *(_QWORD *)(v21 + 4856) = 0;
  *(_DWORD *)(v21 + 4864) = 0;
  *(_QWORD *)(v21 + 4836) = 0;
  *(_DWORD *)(v21 + 4880) = 0;
  *(_QWORD *)(v21 + 1472) = *(_QWORD *)(a1 + 16);
  v48 = *(_DWORD *)(*(_QWORD *)(v21 + 1584) + 156LL);
  if ( !v48 )
    v48 = -1;
  *(_DWORD *)(v21 + 5480) = v48;
  memset_0((void *)(v21 + 384), 0, 0xE0u);
  *(_QWORD *)(v21 + 608) = -1;
  *(_DWORD *)(v21 + 388) = 720;
  *(_DWORD *)(v21 + 444) = 720;
  if ( *(_DWORD *)a1 >= 0x2Cu && *(_DWORD *)(a1 + 32) && *(_QWORD *)(a1 + 36) )
  {
    v49 = LocalAlloc(0x40u, *(unsigned int *)(a1 + 32));
    *(_QWORD *)(v21 + 5512) = v49;
    v50 = v49;
    if ( !v49 )
    {
      LastError = GetLastError();
      v40 = LastError;
      if ( !LastError )
        goto LABEL_54;
      v45 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_54;
      }
      v46 = 1179;
      goto LABEL_97;
    }
    v52 = *(_DWORD *)(a1 + 32);
    *(_DWORD *)(v21 + 5508) = v52;
    memcpy_0(v50, *(const void **)(a1 + 36), v52);
  }
  else
  {
    *(_DWORD *)(v21 + 5508) = 0;
    *(_QWORD *)(v21 + 5512) = 0;
  }
  memcpy_0((void *)(v21 + 1600), Src, Src[0]);
  EncodePasswordW(v21 + 3148);
  LastError = UpdateConfigParamsFromEntry(v21);
  v40 = LastError;
  if ( LastError )
  {
    v45 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_54;
    }
    v46 = 1180;
    goto LABEL_97;
  }
  LastError = GetConnectionParamsFromEntry(v21, &v54);
  v40 = LastError;
  if ( LastError )
  {
    v45 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_54;
    }
    v46 = 1181;
    goto LABEL_97;
  }
  if ( *(_DWORD *)(v21 + 4LL * *(unsigned int *)(v21 + 5424) + 5408) != 14 )
  {
    LastError = UpdateTunnelEndPointsInformation(v21);
    v40 = LastError;
    if ( LastError )
    {
      v45 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_54;
      }
      v46 = 1182;
LABEL_97:
      v47 = LastError;
      goto LABEL_85;
    }
  }
  StrncpyWtoA(v55, v21 + 4030, 129, 65001);
  *v56 = v18;
  v53 = v57;
  *a5 = *(_DWORD *)(v21 + 4LL * *(unsigned int *)(v21 + 5424) + 5408);
  *v53 = 0;
  *v58 = GetTickCount();
  *v59 = *(_OWORD *)(v21 + 5540);
LABEL_117:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1183, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v40);
  }
  return v40;
}

```

## disassembly

```asm
0x180068f50  mov     [rsp-8+arg_18], rbx
0x180068f55  push    rbp
0x180068f56  push    rsi
0x180068f57  push    rdi
0x180068f58  push    r12
0x180068f5a  push    r13
0x180068f5c  push    r14
0x180068f5e  push    r15
0x180068f60  lea     rbp, [rsp-7B0h]
0x180068f68  sub     rsp, 8B0h
0x180068f6f  mov     rax, cs:__security_cookie
0x180068f76  xor     rax, rsp
0x180068f79  mov     [rbp+7E0h+var_40], rax
0x180068f80  mov     rax, [rbp+7E0h+arg_28]
0x180068f87  mov     rbx, r9
0x180068f8a  mov     r13, [rbp+7E0h+arg_20]
0x180068f91  mov     r12, r8
0x180068f94  mov     [rsp+8E0h+var_8B0], rax
0x180068f99  mov     rdi, rdx
0x180068f9c  mov     rax, [rbp+7E0h+arg_30]
0x180068fa3  mov     r14, rcx
0x180068fa6  mov     [rsp+8E0h+var_8A8], rax
0x180068fab  mov     rax, [rbp+7E0h+arg_38]
0x180068fb2  mov     [rsp+8E0h+var_8A0], rax
0x180068fb7  mov     rax, [rbp+7E0h+arg_40]
0x180068fbe  mov     [rsp+8E0h+var_898], rax
0x180068fc3  mov     rax, [rbp+7E0h+arg_48]
0x180068fca  mov     [rsp+8E0h+var_8B8], rax
0x180068fcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180068fd6  lea     rax, WPP_GLOBAL_Control
0x180068fdd  cmp     rcx, rax
0x180068fe0  jz      short loc_180069006
0x180068fe2  test    dword ptr [rcx+1Ch], 800h
0x180068fe9  jz      short loc_180069006
0x180068feb  cmp     byte ptr [rcx+19h], 6
0x180068fef  jb      short loc_180069006
0x180068ff1  mov     rcx, [rcx+10h]
0x180068ff5  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180068ffc  mov     edx, 48Fh
0x180069001  call    WPP_SF_
0x180069006  mov     rdx, rdi; Src
0x180069009  lea     rcx, [rsp+8E0h+Src]; void *
0x18006900e  mov     edi, 848h
0x180069013  xor     esi, esi
0x180069015  mov     r8d, edi; Size
0x180069018  mov     [rsp+8E0h+var_8C0], esi
0x18006901c  call    memcpy_0
0x180069021  mov     [rsp+8E0h+Src], edi
0x180069025  cmp     [rbp+7E0h+String1], si
0x18006902c  jz      loc_1800690C0
0x180069032  lea     rdx, asc_1800E75F8; "\\"
0x180069039  lea     rcx, [rbp+7E0h+Str]; Str
0x180069040  call    cs:__imp_wcsstr
0x180069046  mov     rdi, rax
0x180069049  test    rax, rax
0x18006904c  jz      short loc_180069081
0x18006904e  lea     rdx, [rbp+7E0h+Str]; String2
0x180069055  mov     [rax], si
0x180069058  lea     rcx, [rbp+7E0h+String1]; String1
0x18006905f  call    cs:__imp__wcsicmp
0x180069065  test    eax, eax
0x180069067  jnz     short loc_18006907A
0x180069069  xorps   xmm0, xmm0
0x18006906c  movups  xmmword ptr [rbp+7E0h+String1], xmm0
0x180069073  movups  [rbp+7E0h+var_72], xmm0
0x18006907a  mov     word ptr [rdi], 5Ch ; '\'
0x18006907f  jmp     short loc_1800690C0
0x180069081  lea     rdx, asc_1800E78C8; "@"
0x180069088  lea     rcx, [rbp+7E0h+Str]; Str
0x18006908f  call    cs:__imp_wcsstr
0x180069095  test    rax, rax
0x180069098  jz      short loc_1800690C0
0x18006909a  lea     rdx, [rax+2]; String2
0x18006909e  lea     rcx, [rbp+7E0h+String1]; String1
0x1800690a5  call    cs:__imp__wcsicmp
0x1800690ab  test    eax, eax
0x1800690ad  jnz     short loc_1800690C0
0x1800690af  xorps   xmm0, xmm0
0x1800690b2  movups  xmmword ptr [rbp+7E0h+String1], xmm0
0x1800690b9  movups  [rbp+7E0h+var_72], xmm0
0x1800690c0  xor     edx, edx
0x1800690c2  mov     ecx, 1610h
0x1800690c7  call    DtlCreateSizedNode
0x1800690cc  mov     r15, rax
0x1800690cf  test    rax, rax
0x1800690d2  jnz     short loc_18006914B
0x1800690d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800690db  lea     rdi, WPP_GLOBAL_Control
0x1800690e2  lea     esi, [rax+8]
0x1800690e5  cmp     rcx, rdi
0x1800690e8  jz      short loc_180069144
0x1800690ea  test    dword ptr [rcx+1Ch], 800h
0x1800690f1  jz      short loc_180069118
0x1800690f3  cmp     byte ptr [rcx+19h], 2
0x1800690f7  jb      short loc_180069118
0x1800690f9  mov     rcx, [rcx+10h]
0x1800690fd  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180069104  mov     edx, 490h
0x180069109  mov     r9d, esi
0x18006910c  call    WPP_SF_d
0x180069111  mov     rcx, cs:WPP_GLOBAL_Control
0x180069118  cmp     rcx, rdi
0x18006911b  jz      short loc_180069144
0x18006911d  test    dword ptr [rcx+1Ch], 800h
0x180069124  jz      short loc_180069144
0x180069126  cmp     byte ptr [rcx+19h], 6
0x18006912a  jb      short loc_180069144
0x18006912c  mov     rcx, [rcx+10h]
0x180069130  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180069137  mov     edx, 491h
0x18006913c  mov     r9d, esi
0x18006913f  call    WPP_SF_d
0x180069144  mov     eax, esi
0x180069146  jmp     loc_180069817
0x18006914b  mov     rdi, [rax+10h]
0x18006914f  xor     edx, edx; Val
0x180069151  mov     rcx, rdi; void *
0x180069154  mov     r8d, 1610h; Size
0x18006915a  call    memset_0
0x18006915f  lea     rax, [rdi+1558h]
0x180069166  mov     esi, 3F0h
0x18006916b  mov     [rdi+1560h], rax
0x180069172  mov     ecx, esi; Size
0x180069174  mov     [rax], rax
0x180069177  lea     rax, [rdi+10h]
0x18006917b  mov     [rdi+18h], rax
0x18006917f  mov     [rax], rax
0x180069182  call    cs:__imp_malloc
0x180069188  mov     r8d, esi; Size
0x18006918b  xor     edx, edx; Val
0x18006918d  mov     rcx, rax; void *
0x180069190  mov     [rdi+630h], rax
0x180069197  call    memset_0
0x18006919c  mov     rax, [rdi+630h]
0x1800691a3  mov     ecx, 7
0x1800691a8  lea     edx, [rcx+79h]
0x1800691ab  movups  xmm0, xmmword ptr [rbx]
0x1800691ae  movups  xmmword ptr [rax], xmm0
0x1800691b1  movups  xmm1, xmmword ptr [rbx+10h]
0x1800691b5  movups  xmmword ptr [rax+10h], xmm1
0x1800691b9  movups  xmm0, xmmword ptr [rbx+20h]
0x1800691bd  movups  xmmword ptr [rax+20h], xmm0
0x1800691c1  movups  xmm1, xmmword ptr [rbx+30h]
0x1800691c5  movups  xmmword ptr [rax+30h], xmm1
0x1800691c9  movups  xmm0, xmmword ptr [rbx+40h]
0x1800691cd  movups  xmmword ptr [rax+40h], xmm0
0x1800691d1  movups  xmm1, xmmword ptr [rbx+50h]
0x1800691d5  movups  xmmword ptr [rax+50h], xmm1
0x1800691d9  movups  xmm0, xmmword ptr [rbx+60h]
0x1800691dd  movups  xmmword ptr [rax+60h], xmm0
0x1800691e1  movups  xmm1, xmmword ptr [rbx+70h]
0x1800691e5  add     rbx, rdx
0x1800691e8  movups  xmmword ptr [rax+70h], xmm1
0x1800691ec  add     rax, rdx
0x1800691ef  sub     rcx, 1
0x1800691f3  jnz     short loc_1800691AB
0x1800691f5  movups  xmm0, xmmword ptr [rbx]
0x1800691f8  movups  xmmword ptr [rax], xmm0
0x1800691fb  movups  xmm1, xmmword ptr [rbx+10h]
0x1800691ff  movups  xmmword ptr [rax+10h], xmm1
0x180069203  movups  xmm0, xmmword ptr [rbx+20h]
0x180069207  movups  xmmword ptr [rax+20h], xmm0
0x18006920b  movups  xmm1, xmmword ptr [rbx+30h]
0x18006920f  movups  xmmword ptr [rax+30h], xmm1
0x180069213  movups  xmm0, xmmword ptr [rbx+40h]
0x180069217  movups  xmmword ptr [rax+40h], xmm0
0x18006921b  movups  xmm1, xmmword ptr [rbx+50h]
0x18006921f  movups  xmmword ptr [rax+50h], xmm1
0x180069223  movups  xmm0, xmmword ptr [rbx+60h]
0x180069227  movups  xmmword ptr [rax+60h], xmm0
0x18006922b  xor     eax, eax
0x18006922d  mov     [rdi+1554h], eax
0x180069233  mov     [rdi+1578h], eax
0x180069239  mov     [rbp+7E0h+var_60], 1
0x180069243  mov     [rdi+0E94h], rax
0x18006924a  mov     rax, [rdi+630h]
0x180069251  mov     dword ptr [rdi+0EA0h], 2
0x18006925b  mov     ebx, [rax+0A8h]
0x180069261  mov     rcx, cs:WPP_GLOBAL_Control
0x180069268  lea     rdx, WPP_GLOBAL_Control
0x18006926f  mov     r8b, 5
0x180069272  mov     eax, 800h
0x180069277  cmp     rcx, rdx
0x18006927a  jz      short loc_1800692B5
0x18006927c  test    [rcx+1Ch], eax
0x18006927f  jz      short loc_1800692B5
0x180069281  cmp     [rcx+19h], r8b
0x180069285  jb      short loc_1800692B5
0x180069287  mov     rcx, [rcx+10h]
0x18006928b  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180069292  mov     edx, 492h
0x180069297  mov     r9d, ebx
0x18006929a  call    WPP_SF_d
0x18006929f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800692a6  lea     rdx, WPP_GLOBAL_Control
0x1800692ad  mov     eax, 800h
0x1800692b2  mov     r8b, 5
0x1800692b5  mov     esi, 8
0x1800692ba  cmp     ebx, 7
0x1800692bd  ja      short loc_180069322
0x1800692bf  jz      loc_18006944D
0x1800692c5  sub     ebx, 1
0x1800692c8  jz      loc_1800693FA
0x1800692ce  sub     ebx, 1
0x1800692d1  jz      loc_1800693FA
0x1800692d7  sub     ebx, 1
0x1800692da  jz      loc_1800693CE
0x1800692e0  sub     ebx, 1
0x1800692e3  jz      loc_1800693CE
0x1800692e9  sub     ebx, 1
0x1800692ec  jz      short loc_1800692F3
0x1800692ee  cmp     ebx, 1
0x1800692f1  jnz     short loc_18006934E
0x1800692f3  cmp     rcx, rdx
0x1800692f6  jz      short loc_180069318
0x1800692f8  test    [rcx+1Ch], eax
0x1800692fb  jz      short loc_180069318
0x1800692fd  cmp     [rcx+19h], r8b
0x180069301  jb      short loc_180069318
0x180069303  mov     rcx, [rcx+10h]
0x180069307  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006930e  mov     edx, 494h
0x180069313  call    WPP_SF_
0x180069318  mov     esi, 0Eh
0x18006931d  jmp     loc_180069477
0x180069322  sub     ebx, esi
0x180069324  jz      loc_18006944D
0x18006932a  sub     ebx, 1
0x18006932d  jz      loc_180069421
0x180069333  sub     ebx, 3
0x180069336  jz      loc_1800693FA
0x18006933c  sub     ebx, 1
0x18006933f  jz      loc_1800693CE
0x180069345  cmp     ebx, 1
0x180069348  jz      loc_18006944D
0x18006934e  cmp     rcx, rdx
0x180069351  jz      short loc_180069381
0x180069353  test    [rcx+1Ch], eax
0x180069356  jz      short loc_180069381
0x180069358  cmp     [rcx+19h], r8b
0x18006935c  jb      short loc_180069381
0x18006935e  mov     rcx, [rcx+10h]
0x180069362  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180069369  mov     edx, 498h
0x18006936e  call    WPP_SF_
0x180069373  mov     rcx, cs:WPP_GLOBAL_Control
0x18006937a  lea     rdx, WPP_GLOBAL_Control
0x180069381  mov     ebx, 57h ; 'W'
0x180069386  cmp     rcx, rdx
0x180069389  jz      short loc_1800693B2
0x18006938b  test    dword ptr [rcx+1Ch], 800h
0x180069392  jz      short loc_1800693B2
0x180069394  cmp     byte ptr [rcx+19h], 2
0x180069398  jb      short loc_1800693B2
0x18006939a  mov     rcx, [rcx+10h]
0x18006939e  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x1800693a5  mov     edx, 499h
0x1800693aa  mov     r9d, ebx
0x1800693ad  call    WPP_SF_d
0x1800693b2  lea     rdi, WPP_GLOBAL_Control
0x1800693b9  mov     rcx, r15
0x1800693bc  call    DeleteRasconncbNodeCommon
0x1800693c1  mov     rcx, r15
0x1800693c4  call    Free0
0x1800693c9  jmp     loc_1800697E2
0x1800693ce  cmp     rcx, rdx
0x1800693d1  jz      short loc_1800693F3
0x1800693d3  test    [rcx+1Ch], eax
0x1800693d6  jz      short loc_1800693F3
0x1800693d8  cmp     [rcx+19h], r8b
0x1800693dc  jb      short loc_1800693F3
0x1800693de  mov     rcx, [rcx+10h]
0x1800693e2  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x1800693e9  mov     edx, 495h
0x1800693ee  call    WPP_SF_
0x1800693f3  mov     esi, 9
0x1800693f8  jmp     short loc_180069477
0x1800693fa  cmp     rcx, rdx
0x1800693fd  jz      short loc_180069477
0x1800693ff  test    [rcx+1Ch], eax
0x180069402  jz      short loc_180069477
0x180069404  cmp     [rcx+19h], r8b
0x180069408  jb      short loc_180069477
0x18006940a  mov     rcx, [rcx+10h]
0x18006940e  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x180069415  mov     edx, 493h
0x18006941a  call    WPP_SF_
0x18006941f  jmp     short loc_180069477
0x180069421  cmp     rcx, rdx
0x180069424  jz      short loc_180069446
0x180069426  test    [rcx+1Ch], eax
0x180069429  jz      short loc_180069446
0x18006942b  cmp     [rcx+19h], r8b
0x18006942f  jb      short loc_180069446
0x180069431  mov     rcx, [rcx+10h]
0x180069435  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006943c  mov     edx, 497h
0x180069441  call    WPP_SF_
0x180069446  mov     esi, 10h
0x18006944b  jmp     short loc_180069477
  ... truncated ...
```
