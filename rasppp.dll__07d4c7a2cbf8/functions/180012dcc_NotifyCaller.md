# NotifyCaller

- ea: `0x180012dcc`
- end: `0x1800132c1`
- name: `NotifyCaller`
- size: `1269`
- prototype: ``
- caller_count: `13`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800023a8`
- `0x180004388`
- `0x18000b310`
- `0x18000c4ac`
- `0x18000df18`
- `0x18000e364`
- `0x18000e86c`
- `0x1800132c8`
- `0x180013308`
- `0x180013490`
- `0x18001378c`
- `0x1800148ec`
- `0x1800155b8`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x18000b9ac`
- `0x180012dcc`
- `0x1800198d8`
- `0x18002a138`
- `0x180033010`

## pseudocode

```c
ULONG __fastcall NotifyCaller(__int64 a1, unsigned int a2, unsigned int *a3)
{
  ULONG result; // eax
  __int64 v7; // r8
  __int64 v8; // rcx
  __int128 v9; // xmm1
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  unsigned int v26; // ebx
  unsigned int v27; // ebx
  unsigned int v28; // ebx
  unsigned int v29; // ebx
  unsigned int v30; // edx
  __int128 v31; // xmm0
  __int32 v32; // eax
  unsigned int v33; // ebx
  unsigned int v34; // ebx
  unsigned int v35; // ebx
  unsigned int v36; // ebx
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int128 v44; // xmm0
  const char *v45; // r8
  const char *v46; // r8
  __int128 v47; // xmm1
  __int128 v48; // xmm0
  __int128 v49; // xmm1
  __int128 v50; // xmm0
  __int128 v51; // xmm1
  __int128 v52; // xmm0
  __int128 v53; // xmm1
  __int128 v54; // xmm0
  __int128 v55; // xmm1
  __int128 v56; // xmm0
  __int128 v57; // xmm1
  __int128 v58; // xmm0
  __int128 v59; // xmm1
  char v60[8]; // [rsp+20h] [rbp-E0h] BYREF
  __int32 v61; // [rsp+28h] [rbp-D8h]
  unsigned int v62; // [rsp+2Ch] [rbp-D4h]
  __int64 v63; // [rsp+30h] [rbp-D0h]
  __int128 v64; // [rsp+38h] [rbp-C8h]
  __int128 v65; // [rsp+48h] [rbp-B8h]
  __int64 v66; // [rsp+58h] [rbp-A8h]
  __m256i pszDest; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v68; // [rsp+80h] [rbp-80h]
  __int128 v69; // [rsp+90h] [rbp-70h]
  __int128 v70; // [rsp+A0h] [rbp-60h]
  __int128 v71; // [rsp+B0h] [rbp-50h]
  __int128 v72; // [rsp+C0h] [rbp-40h]
  __m256i v73; // [rsp+D0h] [rbp-30h]
  __int128 v74; // [rsp+F0h] [rbp-10h]
  __int128 v75; // [rsp+100h] [rbp+0h]
  __int128 v76; // [rsp+110h] [rbp+10h]
  __int128 v77; // [rsp+120h] [rbp+20h]
  __int128 v78; // [rsp+130h] [rbp+30h]
  char v79[4]; // [rsp+161h] [rbp+61h] BYREF
  char v80[15]; // [rsp+165h] [rbp+65h] BYREF
  int v81; // [rsp+174h] [rbp+74h]
  int v82; // [rsp+178h] [rbp+78h]
  int v83; // [rsp+700h] [rbp+600h] BYREF
  char v84[2044]; // [rsp+704h] [rbp+604h] BYREF

  v83 = 0;
  memset_0(v84, 0, sizeof(v84));
  result = (unsigned int)memset_0(v60, 0, 0x6D8u);
  if ( (byte_18004CF34 & 1) != 0 )
  {
    v7 = *(_QWORD *)(a1 + 16);
    LOWORD(v83) = 0;
    result = FormatRRASErrorString(&v83, L"NotifyCaller(hPort=%d, dwMsgId=%d)", v7, a2);
    if ( (byte_18004CF34 & 1) != 0 )
      result = McTemplateU0z_EventWriteTransfer(
                 &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                 (const EVENT_DESCRIPTOR *)RasPppTraceInfo,
                 (const wchar_t *)&v83);
  }
  v8 = *(_QWORD *)(a1 + 16);
  v63 = v8;
  v62 = a2;
  v9 = *(_OWORD *)(a1 + 1728);
  v64 = *(_OWORD *)(a1 + 1712);
  v66 = *(_QWORD *)(a1 + 1744);
  v65 = v9;
  if ( a2 > 0xB )
  {
    if ( a2 > 0x16 )
    {
      result = a2 - 23;
      if ( a2 == 23 )
      {
        if ( (*(_BYTE *)(a1 + 56) & 4) == 0 )
          return result;
        pszDest.m256i_i32[0] = *a3;
      }
      else
      {
        result = a2 - 24;
        if ( a2 == 24 || (result = a2 - 25, a2 == 25) )
        {
          if ( (*(_BYTE *)(a1 + 56) & 4) == 0 )
            return result;
          if ( a2 == 25 )
          {
            ProcessNPSAuthAttributes(v8, *(_QWORD *)(a1 + 160), &pszDest);
            *(_DWORD *)(*(_QWORD *)(a1 + 8) + 84LL) = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 80LL);
            *(_DWORD *)(*(_QWORD *)(a1 + 8) + 80LL) = HIDWORD(v68);
          }
        }
        else if ( a2 != 27 || (*(_BYTE *)(a1 + 56) & 4) == 0 )
        {
          return result;
        }
      }
    }
    else if ( a2 == 22 )
    {
      if ( (*(_BYTE *)(a1 + 56) & 4) == 0 )
        return result;
      StringCchCopyA(pszDest.m256i_i8, 0x101u, (STRSAFE_LPCSTR)(*(_QWORD *)(a1 + 8) + 216LL));
      StringCchCopyA(v79, 0x10u, (STRSAFE_LPCSTR)(*(_QWORD *)(a1 + 8) + 473LL));
      v81 = *(_DWORD *)(a1 + 56) & 0x40;
    }
    else
    {
      v33 = a2 - 12;
      if ( !v33 )
      {
        if ( (*(_BYTE *)(a1 + 56) & 4) == 0 )
        {
          *(_OWORD *)pszDest.m256i_i8 = *(_OWORD *)a3;
          return ((__int64 (__fastcall *)(__int64, char *))qword_18004C438)(v8, v60);
        }
        return result;
      }
      v34 = v33 - 1;
      if ( !v34 )
      {
        if ( (*(_BYTE *)(a1 + 56) & 4) == 0 )
        {
          pszDest.m256i_i64[0] = *(_QWORD *)a3;
          return ((__int64 (__fastcall *)(__int64, char *))qword_18004C438)(v8, v60);
        }
        return result;
      }
      v35 = v34 - 6;
      if ( v35 )
      {
        v36 = v35 - 1;
        if ( v36 )
        {
          if ( v36 != 1 || (*(_BYTE *)(a1 + 56) & 4) == 0 )
            return result;
          v37 = *((_OWORD *)a3 + 1);
          *(_OWORD *)pszDest.m256i_i8 = *(_OWORD *)a3;
          v38 = *((_OWORD *)a3 + 2);
          *(_OWORD *)&pszDest.m256i_u64[2] = v37;
          v39 = *((_OWORD *)a3 + 3);
          v68 = v38;
          v40 = *((_OWORD *)a3 + 4);
          v69 = v39;
          v41 = *((_OWORD *)a3 + 5);
          v70 = v40;
          v42 = *((_OWORD *)a3 + 6);
          v71 = v41;
          v43 = *((_OWORD *)a3 + 7);
          v72 = v42;
          v44 = *(_OWORD *)(a3 + 31);
          *(_OWORD *)v73.m256i_i8 = v43;
          *(_OWORD *)((char *)&v73.m256i_u64[1] + 4) = v44;
        }
        else
        {
          if ( (*(_BYTE *)(a1 + 56) & 4) == 0 )
            return result;
          v45 = (const char *)(*(_QWORD *)(a1 + 8) + 216LL);
          pszDest.m256i_i32[0] = *a3;
          if ( *v45 )
            StringCchCopyA(&pszDest.m256i_i8[4], 0x101u, v45);
          else
            pszDest.m256i_i8[4] = 0;
          v46 = (const char *)(*(_QWORD *)(a1 + 8) + 473LL);
          if ( *v46 )
            StringCchCopyA(v80, 0x10u, v46);
          else
            v80[0] = 0;
          v82 = 1;
        }
      }
      else
      {
        if ( (*(_BYTE *)(a1 + 56) & 4) == 0 )
          return result;
        v47 = *((_OWORD *)a3 + 1);
        *(_OWORD *)pszDest.m256i_i8 = *(_OWORD *)a3;
        v48 = *((_OWORD *)a3 + 2);
        *(_OWORD *)&pszDest.m256i_u64[2] = v47;
        v49 = *((_OWORD *)a3 + 3);
        v68 = v48;
        v50 = *((_OWORD *)a3 + 4);
        v69 = v49;
        v51 = *((_OWORD *)a3 + 5);
        v70 = v50;
        v52 = *((_OWORD *)a3 + 6);
        v71 = v51;
        v53 = *((_OWORD *)a3 + 7);
        v72 = v52;
        v54 = *((_OWORD *)a3 + 8);
        *(_OWORD *)v73.m256i_i8 = v53;
        v55 = *((_OWORD *)a3 + 9);
        *(_OWORD *)&v73.m256i_u64[2] = v54;
        v56 = *((_OWORD *)a3 + 10);
        v74 = v55;
        v57 = *((_OWORD *)a3 + 11);
        v75 = v56;
        v58 = *((_OWORD *)a3 + 12);
        v76 = v57;
        v59 = *((_OWORD *)a3 + 13);
        v77 = v58;
        v78 = v59;
      }
    }
    result = (unsigned int)qword_18004CA60;
    if ( qword_18004CA60 )
      return qword_18004CA60(v60);
    return result;
  }
  if ( a2 == 11 )
  {
    if ( (*(_BYTE *)(a1 + 56) & 4) == 0 )
    {
      v31 = *(_OWORD *)(a3 + 2);
      pszDest.m256i_i32[0] = *a3;
      v32 = a3[1];
      *(_OWORD *)&pszDest.m256i_u64[1] = v31;
      pszDest.m256i_i32[1] = v32;
      return ((__int64 (__fastcall *)(_QWORD, _QWORD))qword_18004C438)(v8, v60);
    }
    return result;
  }
  if ( a2 > 5 )
  {
    v26 = a2 - 6;
    if ( v26 )
    {
      v27 = v26 - 1;
      if ( v27 )
      {
        v28 = v27 - 1;
        if ( v28 )
        {
          v29 = v28 - 1;
          if ( v29 )
          {
            if ( v29 == 1 )
            {
              v30 = *(_DWORD *)(a1 + 56);
              if ( (v30 & 4) == 0 )
              {
                v61 = *a3;
                pszDest.m256i_i32[0] = (v30 >> 17) & 1;
                return ((__int64 (__fastcall *)(_QWORD, _QWORD))qword_18004C438)(v8, v60);
              }
            }
            return result;
          }
        }
      }
    }
    goto LABEL_24;
  }
  if ( a2 == 5 || !a2 )
    goto LABEL_24;
  v10 = a2 - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( v12 )
      {
        if ( v12 == 1 && (*(_BYTE *)(a1 + 56) & 4) == 0 )
        {
          v13 = *((_OWORD *)a3 + 1);
          *(_OWORD *)pszDest.m256i_i8 = *(_OWORD *)a3;
          v14 = *((_OWORD *)a3 + 2);
          *(_OWORD *)&pszDest.m256i_u64[2] = v13;
          v15 = *((_OWORD *)a3 + 3);
          v68 = v14;
          v16 = *((_OWORD *)a3 + 4);
          v69 = v15;
          v17 = *((_OWORD *)a3 + 5);
          v70 = v16;
          v18 = *((_OWORD *)a3 + 6);
          v71 = v17;
          v19 = *((_OWORD *)a3 + 7);
          v72 = v18;
          v20 = *((_OWORD *)a3 + 8);
          *(_OWORD *)v73.m256i_i8 = v19;
          v21 = *((_OWORD *)a3 + 9);
          *(_OWORD *)&v73.m256i_u64[2] = v20;
          v22 = *((_OWORD *)a3 + 10);
          v74 = v21;
          v23 = *((_OWORD *)a3 + 11);
          v75 = v22;
          v24 = *((_OWORD *)a3 + 12);
          v76 = v23;
          v25 = *((_OWORD *)a3 + 13);
          v77 = v24;
          v78 = v25;
          return ((__int64 (__fastcall *)(_QWORD, _QWORD))qword_18004C438)(v8, v60);
        }
        return result;
      }
    }
LABEL_24:
    if ( (*(_BYTE *)(a1 + 56) & 4) == 0 )
      return ((__int64 (__fastcall *)(_QWORD, _QWORD))qword_18004C438)(v8, v60);
    return result;
  }
  if ( (*(_BYTE *)(a1 + 56) & 4) == 0 )
  {
    pszDest.m256i_i64[0] = *a3;
    return ((__int64 (__fastcall *)(_QWORD, _QWORD))qword_18004C438)(v8, v60);
  }
  return result;
}

```

## disassembly

```asm
0x180012dcc  mov     [rsp-8+arg_18], rbx
0x180012dd1  push    rbp
0x180012dd2  push    rsi
0x180012dd3  push    rdi
0x180012dd4  lea     rbp, [rsp-0E10h]
0x180012ddc  sub     rsp, 0F10h
0x180012de3  mov     rax, cs:__security_cookie
0x180012dea  xor     rax, rsp
0x180012ded  mov     [rbp+0E20h+var_20], rax
0x180012df4  mov     rsi, r8
0x180012df7  mov     ebx, edx
0x180012df9  mov     rdi, rcx
0x180012dfc  xor     eax, eax
0x180012dfe  xor     edx, edx; Val
0x180012e00  mov     [rbp+0E20h+var_820], eax
0x180012e06  mov     r8d, 7FCh; Size
0x180012e0c  lea     rcx, [rbp+0E20h+var_81C]; void *
0x180012e13  call    memset_0
0x180012e18  xor     edx, edx; Val
0x180012e1a  lea     rcx, [rsp+0F20h+var_F00]; void *
0x180012e1f  mov     r8d, 6D8h; Size
0x180012e25  call    memset_0
0x180012e2a  test    cs:byte_18004CF34, 1
0x180012e31  jz      short loc_180012E79
0x180012e33  mov     r8, [rdi+10h]
0x180012e37  lea     rdx, aNotifycallerHp; "NotifyCaller(hPort=%d, dwMsgId=%d)"
0x180012e3e  xor     eax, eax
0x180012e40  lea     rcx, [rbp+0E20h+var_820]
0x180012e47  mov     r9d, ebx
0x180012e4a  mov     word ptr [rbp+0E20h+var_820], ax
0x180012e51  call    FormatRRASErrorString
0x180012e56  test    cs:byte_18004CF34, 1
0x180012e5d  jz      short loc_180012E79
0x180012e5f  lea     r8, [rbp+0E20h+var_820]
0x180012e66  lea     rdx, RasPppTraceInfo
0x180012e6d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180012e74  call    McTemplateU0z_EventWriteTransfer
0x180012e79  mov     rcx, [rdi+10h]
0x180012e7d  mov     [rsp+0F20h+var_EF0], rcx
0x180012e82  mov     [rsp+0F20h+var_EF4], ebx
0x180012e86  movups  xmm0, xmmword ptr [rdi+6B0h]
0x180012e8d  movups  xmm1, xmmword ptr [rdi+6C0h]
0x180012e94  movups  [rsp+0F20h+var_EE8], xmm0
0x180012e99  movsd   xmm0, qword ptr [rdi+6D0h]
0x180012ea1  movsd   [rsp+0F20h+var_EC8], xmm0
0x180012ea7  movups  [rsp+0F20h+var_ED8], xmm1
0x180012eac  cmp     ebx, 0Bh
0x180012eaf  ja      loc_18001301C
0x180012eb5  jz      loc_180012FF9
0x180012ebb  cmp     ebx, 5
0x180012ebe  ja      loc_180012F9F
0x180012ec4  jz      loc_180012FD9
0x180012eca  test    ebx, ebx
0x180012ecc  jz      loc_180012FD9
0x180012ed2  sub     ebx, 1
0x180012ed5  jz      loc_180012F85
0x180012edb  sub     ebx, 1
0x180012ede  jz      loc_180012FD9
0x180012ee4  sub     ebx, 1
0x180012ee7  jz      loc_180012FD9
0x180012eed  cmp     ebx, 1
0x180012ef0  jnz     loc_180013291
0x180012ef6  test    byte ptr [rdi+38h], 4
0x180012efa  jnz     loc_180013291
0x180012f00  movups  xmm0, xmmword ptr [rsi]
0x180012f03  movups  xmm1, xmmword ptr [rsi+10h]
0x180012f07  movups  xmmword ptr [rsp+0F20h+pszDest], xmm0
0x180012f0c  movups  xmm0, xmmword ptr [rsi+20h]
0x180012f10  movups  [rsp+0F20h+var_EB0], xmm1
0x180012f15  movups  xmm1, xmmword ptr [rsi+30h]
0x180012f19  movups  [rbp+0E20h+var_EA0], xmm0
0x180012f1d  movups  xmm0, xmmword ptr [rsi+40h]
0x180012f21  movups  [rbp+0E20h+var_E90], xmm1
0x180012f25  movups  xmm1, xmmword ptr [rsi+50h]
0x180012f29  movups  [rbp+0E20h+var_E80], xmm0
0x180012f2d  movups  xmm0, xmmword ptr [rsi+60h]
0x180012f31  movups  [rbp+0E20h+var_E70], xmm1
0x180012f35  movups  xmm1, xmmword ptr [rsi+70h]
0x180012f39  movups  [rbp+0E20h+var_E60], xmm0
0x180012f3d  movups  xmm0, xmmword ptr [rsi+80h]
0x180012f44  movups  [rbp+0E20h+var_E50], xmm1
0x180012f48  movups  xmm1, xmmword ptr [rsi+90h]
0x180012f4f  movups  [rbp+0E20h+var_E40], xmm0
0x180012f53  movups  xmm0, xmmword ptr [rsi+0A0h]
0x180012f5a  movups  [rbp+0E20h+var_E30], xmm1
0x180012f5e  movups  xmm1, xmmword ptr [rsi+0B0h]
0x180012f65  movups  [rbp+0E20h+var_E20], xmm0
0x180012f69  movups  xmm0, xmmword ptr [rsi+0C0h]
0x180012f70  movups  [rbp+0E20h+var_E10], xmm1
0x180012f74  movups  xmm1, xmmword ptr [rsi+0D0h]
0x180012f7b  movups  [rbp+0E20h+var_E00], xmm0
0x180012f7f  movups  [rbp+0E20h+var_DF0], xmm1
0x180012f83  jmp     short loc_180012FE3
0x180012f85  test    byte ptr [rdi+38h], 4
0x180012f89  jnz     loc_180013291
0x180012f8f  mov     eax, [rsi]
0x180012f91  mov     dword ptr [rsp+0F20h+pszDest], eax
0x180012f95  mov     dword ptr [rsp+0F20h+pszDest+4], 0
0x180012f9d  jmp     short loc_180012FE3
0x180012f9f  sub     ebx, 6
0x180012fa2  jz      short loc_180012FD9
0x180012fa4  sub     ebx, 1
0x180012fa7  jz      short loc_180012FD9
0x180012fa9  sub     ebx, 1
0x180012fac  jz      short loc_180012FD9
0x180012fae  sub     ebx, 1
0x180012fb1  jz      short loc_180012FD9
0x180012fb3  cmp     ebx, 1
0x180012fb6  jnz     loc_180013291
0x180012fbc  mov     edx, [rdi+38h]
0x180012fbf  test    dl, 4
0x180012fc2  jnz     loc_180013291
0x180012fc8  mov     eax, [rsi]
0x180012fca  shr     edx, 11h
0x180012fcd  and     edx, ebx
0x180012fcf  mov     [rsp+0F20h+var_EF8], eax
0x180012fd3  mov     dword ptr [rsp+0F20h+pszDest], edx
0x180012fd7  jmp     short loc_180012FE3
0x180012fd9  test    byte ptr [rdi+38h], 4
0x180012fdd  jnz     loc_180013291
0x180012fe3  mov     rax, cs:qword_18004C438
0x180012fea  lea     rdx, [rsp+0F20h+var_F00]
0x180012fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ff4  jmp     loc_180013291
0x180012ff9  test    byte ptr [rdi+38h], 4
0x180012ffd  jnz     loc_180013291
0x180013003  mov     eax, [rsi]
0x180013005  movups  xmm0, xmmword ptr [rsi+8]
0x180013009  mov     dword ptr [rsp+0F20h+pszDest], eax
0x18001300d  mov     eax, [rsi+4]
0x180013010  movdqu  xmmword ptr [rsp+0F20h+pszDest+8], xmm0
0x180013016  mov     dword ptr [rsp+0F20h+pszDest+4], eax
0x18001301a  jmp     short loc_180012FE3
0x18001301c  cmp     ebx, 16h
0x18001301f  ja      loc_18001322D
0x180013025  jz      loc_1800131E2
0x18001302b  sub     ebx, 0Ch
0x18001302e  jz      loc_1800131BD
0x180013034  sub     ebx, 1
0x180013037  jz      loc_1800131A6
0x18001303d  sub     ebx, 6
0x180013040  jz      loc_180013114
0x180013046  sub     ebx, 1
0x180013049  jz      short loc_1800130AC
0x18001304b  cmp     ebx, 1
0x18001304e  jnz     loc_180013291
0x180013054  test    byte ptr [rdi+38h], 4
0x180013058  jz      loc_180013291
0x18001305e  movups  xmm0, xmmword ptr [rsi]
0x180013061  movups  xmm1, xmmword ptr [rsi+10h]
0x180013065  movups  xmmword ptr [rsp+0F20h+pszDest], xmm0
0x18001306a  movups  xmm0, xmmword ptr [rsi+20h]
0x18001306e  movups  [rsp+0F20h+var_EB0], xmm1
0x180013073  movups  xmm1, xmmword ptr [rsi+30h]
0x180013077  movups  [rbp+0E20h+var_EA0], xmm0
0x18001307b  movups  xmm0, xmmword ptr [rsi+40h]
0x18001307f  movups  [rbp+0E20h+var_E90], xmm1
0x180013083  movups  xmm1, xmmword ptr [rsi+50h]
0x180013087  movups  [rbp+0E20h+var_E80], xmm0
0x18001308b  movups  xmm0, xmmword ptr [rsi+60h]
0x18001308f  movups  [rbp+0E20h+var_E70], xmm1
0x180013093  movups  xmm1, xmmword ptr [rsi+70h]
0x180013097  movups  [rbp+0E20h+var_E60], xmm0
0x18001309b  movups  xmm0, xmmword ptr [rsi+7Ch]
0x18001309f  movups  [rbp+0E20h+var_E50], xmm1
0x1800130a3  movups  [rbp+0E20h+var_E50+0Ch], xmm0
0x1800130a7  jmp     loc_18001327B
0x1800130ac  test    byte ptr [rdi+38h], 4
0x1800130b0  jz      loc_180013291
0x1800130b6  mov     r8, [rdi+8]
0x1800130ba  mov     eax, [rsi]
0x1800130bc  add     r8, 0D8h; pszSrc
0x1800130c3  mov     dword ptr [rsp+0F20h+pszDest], eax
0x1800130c7  cmp     byte ptr [r8], 0
0x1800130cb  jz      short loc_1800130DE
0x1800130cd  mov     edx, 101h; cchDest
0x1800130d2  lea     rcx, [rsp+0F20h+pszDest+4]; pszDest
0x1800130d7  call    StringCchCopyA
0x1800130dc  jmp     short loc_1800130E3
0x1800130de  mov     [rsp+0F20h+pszDest+4], 0
0x1800130e3  mov     r8, [rdi+8]
0x1800130e7  add     r8, 1D9h; pszSrc
0x1800130ee  cmp     byte ptr [r8], 0
0x1800130f2  jz      short loc_180013104
0x1800130f4  mov     edx, 10h; cchDest
0x1800130f9  lea     rcx, [rbp+0E20h+var_DBB]; pszDest
0x1800130fd  call    StringCchCopyA
0x180013102  jmp     short loc_180013108
0x180013104  mov     [rbp+0E20h+var_DBB], 0
0x180013108  mov     [rbp+0E20h+var_DA8], 1
0x18001310f  jmp     loc_18001327B
0x180013114  test    byte ptr [rdi+38h], 4
0x180013118  jz      loc_180013291
0x18001311e  movups  xmm0, xmmword ptr [rsi]
0x180013121  movups  xmm1, xmmword ptr [rsi+10h]
0x180013125  movups  xmmword ptr [rsp+0F20h+pszDest], xmm0
0x18001312a  movups  xmm0, xmmword ptr [rsi+20h]
0x18001312e  movups  [rsp+0F20h+var_EB0], xmm1
0x180013133  movups  xmm1, xmmword ptr [rsi+30h]
0x180013137  movups  [rbp+0E20h+var_EA0], xmm0
0x18001313b  movups  xmm0, xmmword ptr [rsi+40h]
0x18001313f  movups  [rbp+0E20h+var_E90], xmm1
0x180013143  movups  xmm1, xmmword ptr [rsi+50h]
0x180013147  movups  [rbp+0E20h+var_E80], xmm0
0x18001314b  movups  xmm0, xmmword ptr [rsi+60h]
0x18001314f  movups  [rbp+0E20h+var_E70], xmm1
0x180013153  movups  xmm1, xmmword ptr [rsi+70h]
0x180013157  movups  [rbp+0E20h+var_E60], xmm0
0x18001315b  movups  xmm0, xmmword ptr [rsi+80h]
0x180013162  movups  [rbp+0E20h+var_E50], xmm1
0x180013166  movups  xmm1, xmmword ptr [rsi+90h]
0x18001316d  movups  [rbp+0E20h+var_E40], xmm0
0x180013171  movups  xmm0, xmmword ptr [rsi+0A0h]
0x180013178  movups  [rbp+0E20h+var_E30], xmm1
0x18001317c  movups  xmm1, xmmword ptr [rsi+0B0h]
0x180013183  movups  [rbp+0E20h+var_E20], xmm0
0x180013187  movups  xmm0, xmmword ptr [rsi+0C0h]
0x18001318e  movups  [rbp+0E20h+var_E10], xmm1
0x180013192  movups  xmm1, xmmword ptr [rsi+0D0h]
0x180013199  movups  [rbp+0E20h+var_E00], xmm0
0x18001319d  movups  [rbp+0E20h+var_DF0], xmm1
0x1800131a1  jmp     loc_18001327B
0x1800131a6  test    byte ptr [rdi+38h], 4
0x1800131aa  jnz     loc_180013291
0x1800131b0  mov     rax, [rsi]
0x1800131b3  mov     qword ptr [rsp+0F20h+pszDest], rax
0x1800131b8  jmp     loc_180012FE3
0x1800131bd  test    byte ptr [rdi+38h], 4
0x1800131c1  jnz     loc_180013291
0x1800131c7  mov     eax, [rsi]
0x1800131c9  mov     dword ptr [rsp+0F20h+pszDest], eax
0x1800131cd  mov     eax, [rsi+4]
0x1800131d0  mov     dword ptr [rsp+0F20h+pszDest+4], eax
0x1800131d4  mov     rax, [rsi+8]
0x1800131d8  mov     qword ptr [rsp+0F20h+pszDest+8], rax
0x1800131dd  jmp     loc_180012FE3
0x1800131e2  test    byte ptr [rdi+38h], 4
0x1800131e6  jz      loc_180013291
0x1800131ec  mov     r8, [rdi+8]
0x1800131f0  lea     rcx, [rsp+0F20h+pszDest]; pszDest
0x1800131f5  add     r8, 0D8h; pszSrc
0x1800131fc  mov     edx, 101h; cchDest
0x180013201  call    StringCchCopyA
0x180013206  mov     r8, [rdi+8]
0x18001320a  lea     rcx, [rbp+0E20h+var_DBF]; pszDest
0x18001320e  add     r8, 1D9h; pszSrc
0x180013215  mov     edx, 10h; cchDest
0x18001321a  call    StringCchCopyA
0x18001321f  mov     r10d, [rdi+38h]
0x180013223  and     r10d, 40h
0x180013227  mov     [rbp+0E20h+var_DAC], r10d
0x18001322b  jmp     short loc_18001327B
0x18001322d  mov     eax, ebx
0x18001322f  sub     eax, 17h
0x180013232  jz      short loc_1800132B3
0x180013234  sub     eax, 1
0x180013237  jz      short loc_18001324B
0x180013239  sub     eax, 1
0x18001323c  jz      short loc_18001324B
0x18001323e  cmp     eax, 2
0x180013241  jnz     short loc_180013291
0x180013243  test    byte ptr [rdi+38h], 4
0x180013247  jz      short loc_180013291
0x180013249  jmp     short loc_18001327B
0x18001324b  test    byte ptr [rdi+38h], 4
0x18001324f  jz      short loc_180013291
0x180013251  cmp     ebx, 19h
0x180013254  jnz     short loc_18001327B
0x180013256  mov     rdx, [rdi+0A0h]
0x18001325d  lea     r8, [rsp+0F20h+pszDest]
0x180013262  call    ProcessNPSAuthAttributes
0x180013267  mov     rcx, [rdi+8]
0x18001326b  mov     eax, [rcx+50h]
0x18001326e  mov     [rcx+54h], eax
0x180013271  mov     rcx, [rdi+8]
0x180013275  mov     eax, dword ptr [rbp+0E20h+var_EA0+0Ch]
0x180013278  mov     [rcx+50h], eax
0x18001327b  mov     rax, cs:qword_18004CA60
0x180013282  test    rax, rax
0x180013285  jz      short loc_180013291
0x180013287  lea     rcx, [rsp+0F20h+var_F00]
0x18001328c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013291  mov     rcx, [rbp+0E20h+var_20]
0x180013298  xor     rcx, rsp; StackCookie
0x18001329b  call    __security_check_cookie
0x1800132a0  mov     rbx, [rsp+0F20h+arg_18]
0x1800132a8  add     rsp, 0F10h
0x1800132af  pop     rdi
0x1800132b0  pop     rsi
0x1800132b1  pop     rbp
0x1800132b2  retn
0x1800132b3  test    byte ptr [rdi+38h], 4
0x1800132b7  jz      short loc_180013291
0x1800132b9  mov     eax, [rsi]
0x1800132bb  mov     dword ptr [rsp+0F20h+pszDest], eax
0x1800132bf  jmp     short loc_18001327B
```
