# NotifyCaller

- ea: `0x18001348c`
- end: `0x180013986`
- name: `NotifyCaller`
- size: `1274`
- prototype: `HRESULT __fastcall(__int64, unsigned int, unsigned int *)`
- caller_count: `13`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800023c0`
- `0x18000442c`
- `0x18000b720`
- `0x18000c8d4`
- `0x18000e358`
- `0x18000e7a4`
- `0x18000ecac`
- `0x18001398c`
- `0x1800139cc`
- `0x180013b54`
- `0x180013e50`
- `0x180014ff8`
- `0x180015d28`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18000bdd0`
- `0x18001348c`
- `0x18001a254`
- `0x18002b0dc`
- `0x180034010`

## pseudocode

```c
unsigned int __fastcall NotifyCaller(__int64 a1, unsigned int a2, unsigned int *a3)
{
  unsigned int result; // eax
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
  int v61; // [rsp+28h] [rbp-D8h]
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
  if ( (byte_18004DF34 & 1) != 0 )
  {
    v7 = *(_QWORD *)(a1 + 16);
    LOWORD(v83) = 0;
    result = FormatRRASErrorString((wchar_t *)&v83, L"NotifyCaller(hPort=%d, dwMsgId=%d)", v7, a2);
    if ( (byte_18004DF34 & 1) != 0 )
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
          return ((__int64 (__fastcall *)(__int64, char *))qword_18004D438)(v8, v60);
        }
        return result;
      }
      v34 = v33 - 1;
      if ( !v34 )
      {
        if ( (*(_BYTE *)(a1 + 56) & 4) == 0 )
        {
          pszDest.m256i_i64[0] = *(_QWORD *)a3;
          return ((__int64 (__fastcall *)(__int64, char *))qword_18004D438)(v8, v60);
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
    result = (unsigned int)qword_18004DA60;
    if ( qword_18004DA60 )
      return qword_18004DA60(v60);
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
      return ((__int64 (__fastcall *)(_QWORD, _QWORD))qword_18004D438)(v8, v60);
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
                return ((__int64 (__fastcall *)(_QWORD, _QWORD))qword_18004D438)(v8, v60);
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
          return ((__int64 (__fastcall *)(_QWORD, _QWORD))qword_18004D438)(v8, v60);
        }
        return result;
      }
    }
LABEL_24:
    if ( (*(_BYTE *)(a1 + 56) & 4) == 0 )
      return ((__int64 (__fastcall *)(_QWORD, _QWORD))qword_18004D438)(v8, v60);
    return result;
  }
  if ( (*(_BYTE *)(a1 + 56) & 4) == 0 )
  {
    pszDest.m256i_i64[0] = *a3;
    return ((__int64 (__fastcall *)(_QWORD, _QWORD))qword_18004D438)(v8, v60);
  }
  return result;
}

```

## disassembly

```asm
0x18001348c  mov     [rsp-8+arg_18], rbx
0x180013491  push    rbp
0x180013492  push    rsi
0x180013493  push    rdi
0x180013494  lea     rbp, [rsp-0E10h]
0x18001349c  sub     rsp, 0F10h
0x1800134a3  mov     rax, cs:__security_cookie
0x1800134aa  xor     rax, rsp
0x1800134ad  mov     [rbp+0E20h+var_20], rax
0x1800134b4  mov     rsi, r8
0x1800134b7  mov     ebx, edx
0x1800134b9  mov     rdi, rcx
0x1800134bc  xor     eax, eax
0x1800134be  xor     edx, edx; Val
0x1800134c0  mov     [rbp+0E20h+var_820], eax
0x1800134c6  mov     r8d, 7FCh; Size
0x1800134cc  lea     rcx, [rbp+0E20h+var_81C]; void *
0x1800134d3  call    memset_0
0x1800134d8  xor     edx, edx; Val
0x1800134da  lea     rcx, [rsp+0F20h+var_F00]; void *
0x1800134df  mov     r8d, 6D8h; Size
0x1800134e5  call    memset_0
0x1800134ea  test    cs:byte_18004DF34, 1
0x1800134f1  jz      short loc_180013539
0x1800134f3  mov     r8, [rdi+10h]
0x1800134f7  lea     rdx, aNotifycallerHp; "NotifyCaller(hPort=%d, dwMsgId=%d)"
0x1800134fe  xor     eax, eax
0x180013500  lea     rcx, [rbp+0E20h+var_820]
0x180013507  mov     r9d, ebx
0x18001350a  mov     word ptr [rbp+0E20h+var_820], ax
0x180013511  call    FormatRRASErrorString
0x180013516  test    cs:byte_18004DF34, 1
0x18001351d  jz      short loc_180013539
0x18001351f  lea     r8, [rbp+0E20h+var_820]
0x180013526  lea     rdx, RasPppTraceInfo
0x18001352d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013534  call    McTemplateU0z_EventWriteTransfer
0x180013539  mov     rcx, [rdi+10h]
0x18001353d  mov     [rsp+0F20h+var_EF0], rcx
0x180013542  mov     [rsp+0F20h+var_EF4], ebx
0x180013546  movups  xmm0, xmmword ptr [rdi+6B0h]
0x18001354d  movups  xmm1, xmmword ptr [rdi+6C0h]
0x180013554  movups  [rsp+0F20h+var_EE8], xmm0
0x180013559  movsd   xmm0, qword ptr [rdi+6D0h]
0x180013561  movsd   [rsp+0F20h+var_EC8], xmm0
0x180013567  movups  [rsp+0F20h+var_ED8], xmm1
0x18001356c  cmp     ebx, 0Bh
0x18001356f  ja      loc_1800136DC
0x180013575  jz      loc_1800136B9
0x18001357b  cmp     ebx, 5
0x18001357e  ja      loc_18001365F
0x180013584  jz      loc_180013699
0x18001358a  test    ebx, ebx
0x18001358c  jz      loc_180013699
0x180013592  sub     ebx, 1
0x180013595  jz      loc_180013645
0x18001359b  sub     ebx, 1
0x18001359e  jz      loc_180013699
0x1800135a4  sub     ebx, 1
0x1800135a7  jz      loc_180013699
0x1800135ad  cmp     ebx, 1
0x1800135b0  jnz     loc_180013955
0x1800135b6  test    byte ptr [rdi+38h], 4
0x1800135ba  jnz     loc_180013955
0x1800135c0  movups  xmm0, xmmword ptr [rsi]
0x1800135c3  movups  xmm1, xmmword ptr [rsi+10h]
0x1800135c7  movups  xmmword ptr [rsp+0F20h+pszDest], xmm0
0x1800135cc  movups  xmm0, xmmword ptr [rsi+20h]
0x1800135d0  movups  [rsp+0F20h+var_EB0], xmm1
0x1800135d5  movups  xmm1, xmmword ptr [rsi+30h]
0x1800135d9  movups  [rbp+0E20h+var_EA0], xmm0
0x1800135dd  movups  xmm0, xmmword ptr [rsi+40h]
0x1800135e1  movups  [rbp+0E20h+var_E90], xmm1
0x1800135e5  movups  xmm1, xmmword ptr [rsi+50h]
0x1800135e9  movups  [rbp+0E20h+var_E80], xmm0
0x1800135ed  movups  xmm0, xmmword ptr [rsi+60h]
0x1800135f1  movups  [rbp+0E20h+var_E70], xmm1
0x1800135f5  movups  xmm1, xmmword ptr [rsi+70h]
0x1800135f9  movups  [rbp+0E20h+var_E60], xmm0
0x1800135fd  movups  xmm0, xmmword ptr [rsi+80h]
0x180013604  movups  [rbp+0E20h+var_E50], xmm1
0x180013608  movups  xmm1, xmmword ptr [rsi+90h]
0x18001360f  movups  [rbp+0E20h+var_E40], xmm0
0x180013613  movups  xmm0, xmmword ptr [rsi+0A0h]
0x18001361a  movups  [rbp+0E20h+var_E30], xmm1
0x18001361e  movups  xmm1, xmmword ptr [rsi+0B0h]
0x180013625  movups  [rbp+0E20h+var_E20], xmm0
0x180013629  movups  xmm0, xmmword ptr [rsi+0C0h]
0x180013630  movups  [rbp+0E20h+var_E10], xmm1
0x180013634  movups  xmm1, xmmword ptr [rsi+0D0h]
0x18001363b  movups  [rbp+0E20h+var_E00], xmm0
0x18001363f  movups  [rbp+0E20h+var_DF0], xmm1
0x180013643  jmp     short loc_1800136A3
0x180013645  test    byte ptr [rdi+38h], 4
0x180013649  jnz     loc_180013955
0x18001364f  mov     eax, [rsi]
0x180013651  mov     dword ptr [rsp+0F20h+pszDest], eax
0x180013655  mov     dword ptr [rsp+0F20h+pszDest+4], 0
0x18001365d  jmp     short loc_1800136A3
0x18001365f  sub     ebx, 6
0x180013662  jz      short loc_180013699
0x180013664  sub     ebx, 1
0x180013667  jz      short loc_180013699
0x180013669  sub     ebx, 1
0x18001366c  jz      short loc_180013699
0x18001366e  sub     ebx, 1
0x180013671  jz      short loc_180013699
0x180013673  cmp     ebx, 1
0x180013676  jnz     loc_180013955
0x18001367c  mov     edx, [rdi+38h]
0x18001367f  test    dl, 4
0x180013682  jnz     loc_180013955
0x180013688  mov     eax, [rsi]
0x18001368a  shr     edx, 11h
0x18001368d  and     edx, ebx
0x18001368f  mov     [rsp+0F20h+var_EF8], eax
0x180013693  mov     dword ptr [rsp+0F20h+pszDest], edx
0x180013697  jmp     short loc_1800136A3
0x180013699  test    byte ptr [rdi+38h], 4
0x18001369d  jnz     loc_180013955
0x1800136a3  mov     rax, cs:qword_18004D438
0x1800136aa  lea     rdx, [rsp+0F20h+var_F00]
0x1800136af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136b4  jmp     loc_180013955
0x1800136b9  test    byte ptr [rdi+38h], 4
0x1800136bd  jnz     loc_180013955
0x1800136c3  mov     eax, [rsi]
0x1800136c5  movups  xmm0, xmmword ptr [rsi+8]
0x1800136c9  mov     dword ptr [rsp+0F20h+pszDest], eax
0x1800136cd  mov     eax, [rsi+4]
0x1800136d0  movdqu  xmmword ptr [rsp+0F20h+pszDest+8], xmm0
0x1800136d6  mov     dword ptr [rsp+0F20h+pszDest+4], eax
0x1800136da  jmp     short loc_1800136A3
0x1800136dc  cmp     ebx, 16h
0x1800136df  ja      loc_1800138ED
0x1800136e5  jz      loc_1800138A2
0x1800136eb  sub     ebx, 0Ch
0x1800136ee  jz      loc_18001387D
0x1800136f4  sub     ebx, 1
0x1800136f7  jz      loc_180013866
0x1800136fd  sub     ebx, 6
0x180013700  jz      loc_1800137D4
0x180013706  sub     ebx, 1
0x180013709  jz      short loc_18001376C
0x18001370b  cmp     ebx, 1
0x18001370e  jnz     loc_180013955
0x180013714  test    byte ptr [rdi+38h], 4
0x180013718  jz      loc_180013955
0x18001371e  movups  xmm0, xmmword ptr [rsi]
0x180013721  movups  xmm1, xmmword ptr [rsi+10h]
0x180013725  movups  xmmword ptr [rsp+0F20h+pszDest], xmm0
0x18001372a  movups  xmm0, xmmword ptr [rsi+20h]
0x18001372e  movups  [rsp+0F20h+var_EB0], xmm1
0x180013733  movups  xmm1, xmmword ptr [rsi+30h]
0x180013737  movups  [rbp+0E20h+var_EA0], xmm0
0x18001373b  movups  xmm0, xmmword ptr [rsi+40h]
0x18001373f  movups  [rbp+0E20h+var_E90], xmm1
0x180013743  movups  xmm1, xmmword ptr [rsi+50h]
0x180013747  movups  [rbp+0E20h+var_E80], xmm0
0x18001374b  movups  xmm0, xmmword ptr [rsi+60h]
0x18001374f  movups  [rbp+0E20h+var_E70], xmm1
0x180013753  movups  xmm1, xmmword ptr [rsi+70h]
0x180013757  movups  [rbp+0E20h+var_E60], xmm0
0x18001375b  movups  xmm0, xmmword ptr [rsi+7Ch]
0x18001375f  movups  [rbp+0E20h+var_E50], xmm1
0x180013763  movups  [rbp+0E20h+var_E50+0Ch], xmm0
0x180013767  jmp     loc_18001393F
0x18001376c  test    byte ptr [rdi+38h], 4
0x180013770  jz      loc_180013955
0x180013776  mov     r8, [rdi+8]
0x18001377a  mov     eax, [rsi]
0x18001377c  add     r8, 0D8h; pszSrc
0x180013783  mov     dword ptr [rsp+0F20h+pszDest], eax
0x180013787  cmp     byte ptr [r8], 0
0x18001378b  jz      short loc_18001379E
0x18001378d  mov     edx, 101h; cchDest
0x180013792  lea     rcx, [rsp+0F20h+pszDest+4]; pszDest
0x180013797  call    StringCchCopyA
0x18001379c  jmp     short loc_1800137A3
0x18001379e  mov     [rsp+0F20h+pszDest+4], 0
0x1800137a3  mov     r8, [rdi+8]
0x1800137a7  add     r8, 1D9h; pszSrc
0x1800137ae  cmp     byte ptr [r8], 0
0x1800137b2  jz      short loc_1800137C4
0x1800137b4  mov     edx, 10h; cchDest
0x1800137b9  lea     rcx, [rbp+0E20h+var_DBB]; pszDest
0x1800137bd  call    StringCchCopyA
0x1800137c2  jmp     short loc_1800137C8
0x1800137c4  mov     [rbp+0E20h+var_DBB], 0
0x1800137c8  mov     [rbp+0E20h+var_DA8], 1
0x1800137cf  jmp     loc_18001393F
0x1800137d4  test    byte ptr [rdi+38h], 4
0x1800137d8  jz      loc_180013955
0x1800137de  movups  xmm0, xmmword ptr [rsi]
0x1800137e1  movups  xmm1, xmmword ptr [rsi+10h]
0x1800137e5  movups  xmmword ptr [rsp+0F20h+pszDest], xmm0
0x1800137ea  movups  xmm0, xmmword ptr [rsi+20h]
0x1800137ee  movups  [rsp+0F20h+var_EB0], xmm1
0x1800137f3  movups  xmm1, xmmword ptr [rsi+30h]
0x1800137f7  movups  [rbp+0E20h+var_EA0], xmm0
0x1800137fb  movups  xmm0, xmmword ptr [rsi+40h]
0x1800137ff  movups  [rbp+0E20h+var_E90], xmm1
0x180013803  movups  xmm1, xmmword ptr [rsi+50h]
0x180013807  movups  [rbp+0E20h+var_E80], xmm0
0x18001380b  movups  xmm0, xmmword ptr [rsi+60h]
0x18001380f  movups  [rbp+0E20h+var_E70], xmm1
0x180013813  movups  xmm1, xmmword ptr [rsi+70h]
0x180013817  movups  [rbp+0E20h+var_E60], xmm0
0x18001381b  movups  xmm0, xmmword ptr [rsi+80h]
0x180013822  movups  [rbp+0E20h+var_E50], xmm1
0x180013826  movups  xmm1, xmmword ptr [rsi+90h]
0x18001382d  movups  [rbp+0E20h+var_E40], xmm0
0x180013831  movups  xmm0, xmmword ptr [rsi+0A0h]
0x180013838  movups  [rbp+0E20h+var_E30], xmm1
0x18001383c  movups  xmm1, xmmword ptr [rsi+0B0h]
0x180013843  movups  [rbp+0E20h+var_E20], xmm0
0x180013847  movups  xmm0, xmmword ptr [rsi+0C0h]
0x18001384e  movups  [rbp+0E20h+var_E10], xmm1
0x180013852  movups  xmm1, xmmword ptr [rsi+0D0h]
0x180013859  movups  [rbp+0E20h+var_E00], xmm0
0x18001385d  movups  [rbp+0E20h+var_DF0], xmm1
0x180013861  jmp     loc_18001393F
0x180013866  test    byte ptr [rdi+38h], 4
0x18001386a  jnz     loc_180013955
0x180013870  mov     rax, [rsi]
0x180013873  mov     qword ptr [rsp+0F20h+pszDest], rax
0x180013878  jmp     loc_1800136A3
0x18001387d  test    byte ptr [rdi+38h], 4
0x180013881  jnz     loc_180013955
0x180013887  mov     eax, [rsi]
0x180013889  mov     dword ptr [rsp+0F20h+pszDest], eax
0x18001388d  mov     eax, [rsi+4]
0x180013890  mov     dword ptr [rsp+0F20h+pszDest+4], eax
0x180013894  mov     rax, [rsi+8]
0x180013898  mov     qword ptr [rsp+0F20h+pszDest+8], rax
0x18001389d  jmp     loc_1800136A3
0x1800138a2  test    byte ptr [rdi+38h], 4
0x1800138a6  jz      loc_180013955
0x1800138ac  mov     r8, [rdi+8]
0x1800138b0  lea     rcx, [rsp+0F20h+pszDest]; pszDest
0x1800138b5  add     r8, 0D8h; pszSrc
0x1800138bc  mov     edx, 101h; cchDest
0x1800138c1  call    StringCchCopyA
0x1800138c6  mov     r8, [rdi+8]
0x1800138ca  lea     rcx, [rbp+0E20h+var_DBF]; pszDest
0x1800138ce  add     r8, 1D9h; pszSrc
0x1800138d5  mov     edx, 10h; cchDest
0x1800138da  call    StringCchCopyA
0x1800138df  mov     r10d, [rdi+38h]
0x1800138e3  and     r10d, 40h
0x1800138e7  mov     [rbp+0E20h+var_DAC], r10d
0x1800138eb  jmp     short loc_18001393F
0x1800138ed  mov     eax, ebx
0x1800138ef  sub     eax, 17h
0x1800138f2  jz      loc_180013978
0x1800138f8  sub     eax, 1
0x1800138fb  jz      short loc_18001390F
0x1800138fd  sub     eax, 1
0x180013900  jz      short loc_18001390F
0x180013902  cmp     eax, 2
0x180013905  jnz     short loc_180013955
0x180013907  test    byte ptr [rdi+38h], 4
0x18001390b  jz      short loc_180013955
0x18001390d  jmp     short loc_18001393F
0x18001390f  test    byte ptr [rdi+38h], 4
0x180013913  jz      short loc_180013955
0x180013915  cmp     ebx, 19h
0x180013918  jnz     short loc_18001393F
0x18001391a  mov     rdx, [rdi+0A0h]
0x180013921  lea     r8, [rsp+0F20h+pszDest]
0x180013926  call    ProcessNPSAuthAttributes
0x18001392b  mov     rcx, [rdi+8]
0x18001392f  mov     eax, [rcx+50h]
0x180013932  mov     [rcx+54h], eax
0x180013935  mov     rcx, [rdi+8]
0x180013939  mov     eax, dword ptr [rbp+0E20h+var_EA0+0Ch]
0x18001393c  mov     [rcx+50h], eax
0x18001393f  mov     rax, cs:qword_18004DA60
0x180013946  test    rax, rax
0x180013949  jz      short loc_180013955
0x18001394b  lea     rcx, [rsp+0F20h+var_F00]
0x180013950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013955  mov     rcx, [rbp+0E20h+var_20]
0x18001395c  xor     rcx, rsp; StackCookie
0x18001395f  call    __security_check_cookie
0x180013964  mov     rbx, [rsp+0F20h+arg_18]
0x18001396c  add     rsp, 0F10h
0x180013973  pop     rdi
0x180013974  pop     rsi
0x180013975  pop     rbp
0x180013976  retn
0x180013978  test    byte ptr [rdi+38h], 4
0x18001397c  jz      short loc_180013955
0x18001397e  mov     eax, [rsi]
0x180013980  mov     dword ptr [rsp+0F20h+pszDest], eax
0x180013984  jmp     short loc_18001393F
```
