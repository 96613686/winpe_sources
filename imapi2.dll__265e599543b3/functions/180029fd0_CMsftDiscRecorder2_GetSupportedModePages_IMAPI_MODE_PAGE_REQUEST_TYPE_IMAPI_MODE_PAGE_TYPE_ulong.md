# CMsftDiscRecorder2::GetSupportedModePages(_IMAPI_MODE_PAGE_REQUEST_TYPE,_IMAPI_MODE_PAGE_TYPE * *,ulong *)

- ea: `0x180029fd0`
- end: `0x18002a68c`
- name: `?GetSupportedModePages@CMsftDiscRecorder2@@UEAAJW4_IMAPI_MODE_PAGE_REQUEST_TYPE@@PEAPEAW4_IMAPI_MODE_PAGE_TYPE@@PEAK@Z`
- size: `1724`
- prototype: `__int64 __fastcall(CMsftDiscRecorder2 *__hidden this, enum _IMAPI_MODE_PAGE_REQUEST_TYPE, enum _IMAPI_MODE_PAGE_TYPE **, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002fc8`
- `0x1800036f0`
- `0x18000ae3c`
- `0x180014134`
- `0x180016778`
- `0x1800236b4`
- `0x180029fd0`
- `0x18002cf74`
- `0x18004984a`
- `0x180049880`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002a646`
- `ole32!CoTaskMemFree` at `0x18002a646`
- `ole32!CoTaskMemAlloc` at `0x18002a4bf`
- `ole32!CoTaskMemAlloc` at `0x18002a4bf`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::GetSupportedModePages(
        void **this,
        unsigned int a2,
        enum _IMAPI_MODE_PAGE_TYPE **a3,
        unsigned int *a4)
{
  signed int v4; // ebx
  char v5; // di
  void *v6; // r12
  int v7; // eax
  PVOID *v10; // rcx
  __int64 v11; // r9
  unsigned int v12; // edx
  void *v13; // rdx
  int v14; // eax
  int *v15; // r9
  PVOID *v16; // r10
  unsigned __int8 *v17; // r9
  unsigned int v18; // edi
  unsigned int v19; // edx
  const struct _GUID *v20; // r8
  unsigned __int8 *v21; // rsi
  unsigned __int64 v22; // r15
  unsigned int v23; // r14d
  unsigned __int64 v24; // rax
  LPVOID v25; // rax
  __int64 v26; // r14
  _BYTE *v27; // rsi
  unsigned int v28; // r15d
  unsigned __int8 *v30; // [rsp+30h] [rbp-69h]
  unsigned int v31; // [rsp+38h] [rbp-61h]
  _BYTE v32[32]; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v33; // [rsp+70h] [rbp-29h] BYREF
  enum _IMAPI_MODE_PAGE_TYPE **v34; // [rsp+78h] [rbp-21h]
  unsigned int *v35; // [rsp+80h] [rbp-19h]
  struct _SENSE_DATA v36; // [rsp+88h] [rbp-11h] BYREF

  v4 = 0;
  v35 = a4;
  v5 = a2;
  v34 = a3;
  v6 = 0;
  v33 = 0;
  v7 = 0;
  if ( a2 < 4 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 142, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      v10 = (PVOID *)WPP_GLOBAL_Control;
      a3 = v34;
    }
    v4 = -2147024809;
    v7 = -2147024809;
  }
  if ( a3 )
  {
    *a3 = 0;
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 188) & 4) != 0 && *((_BYTE *)v10 + 185) >= 3u )
    {
      WPP_SF_(v10[22], 143, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    v4 = -2147467261;
    v7 = -2147467261;
  }
  if ( !a4 )
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 188) & 4) != 0 && *((_BYTE *)v10 + 185) >= 3u )
      WPP_SF_(v10[22], 144, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    v4 = -2147467261;
    goto LABEL_89;
  }
  *a4 = 0;
  if ( v7 < 0 )
  {
LABEL_89:
    CoTaskMemFree(v6);
    goto LABEL_90;
  }
  v11 = *((unsigned int *)this + 58);
  if ( (v11 & 2) == 0 )
  {
    v4 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        145,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        v11,
        -2147467259);
    }
    goto LABEL_89;
  }
  memset_0(this[27], 0, *((unsigned int *)this + 56));
  v12 = *((_DWORD *)this + 56);
  *(_OWORD *)&v32[16] = 0;
  v32[18] = (v5 << 6) | 0x3F;
  v32[23] = BYTE1(v12);
  v32[24] = v12;
  *(_WORD *)&v32[16] = 2138;
  v31 = v12;
  v13 = this[10];
  v30 = (unsigned __int8 *)this[27];
  memset(&v36, 0, sizeof(v36));
  v14 = CMsftDiscRecorder2::SendCommandHelper(
          (CMsftDiscRecorder2 *)(this - 1),
          v13,
          (const union _CDB *)&v32[16],
          0xAu,
          &v36,
          0xAu,
          v30,
          v31,
          &v33,
          1u);
  *(_DWORD *)v32 = v14;
  v4 = v14;
  if ( v14 >= 0 )
  {
    if ( v14 != 11141632 )
      goto LABEL_28;
    Imapi2Utility::TranslateSenseInfoToHResult(
      (Imapi2Utility *)&v32[16],
      (const union _CDB *)&v36,
      (const struct _SENSE_DATA *)v32,
      v15);
    v16 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      v4 = *(_DWORD *)v32;
      *(_DWORD *)&v32[18] = 0;
      *(_WORD *)&v32[16] = 18;
      *(_WORD *)&v32[22] = 0;
      *(_QWORD *)&v32[24] = &v36;
      WPP_SF_dDDD_HEX_(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        147,
        (unsigned int)&WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        *(_DWORD *)v32,
        *((_BYTE *)&v36 + 2) & 0xF,
        v36.AdditionalSenseCode,
        v36.AdditionalSenseCodeQualifier,
        (__int64)&v32[16]);
      goto LABEL_28;
    }
    v4 = *(_DWORD *)v32;
  }
  else
  {
    v16 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_DDDd(*((_QWORD *)WPP_GLOBAL_Control + 22), 146, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
LABEL_28:
      v16 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v4 < 0 )
    goto LABEL_89;
  if ( v33 < 0xA )
  {
    if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 188) & 4) != 0 && *((_BYTE *)v16 + 185) >= 3u )
    {
      WPP_SF_DDDd(v16[22], 148, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      v16 = (PVOID *)WPP_GLOBAL_Control;
    }
    v4 = -1062600191;
  }
  if ( v4 < 0 )
    goto LABEL_89;
  v17 = (unsigned __int8 *)this[27];
  v18 = 0;
  v19 = *((_DWORD *)this + 56);
  v20 = (const struct _GUID *)(v17[1] | (*v17 << 8));
  v21 = &v17[(v17[7] | ((unsigned __int64)v17[6] << 8)) + 8];
  if ( (unsigned int)v20 <= v19 )
    v19 = v17[1] | (*v17 << 8);
  v22 = (unsigned __int64)&v17[v19 - 2];
  while ( (unsigned __int64)v21 < v22 )
  {
    if ( (*v21 & 0x3F) == 0 )
    {
      if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 188) & 4) != 0 && *((_BYTE *)v16 + 185) >= 3u )
      {
        WPP_SF_(v16[22], 149, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
        v16 = (PVOID *)WPP_GLOBAL_Control;
      }
      break;
    }
    v23 = v21[1] + 2;
    if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 188) & 4) != 0 && *((_BYTE *)v16 + 185) >= 4u )
    {
      WPP_SF_DDDd(v16[22], 150, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      v16 = (PVOID *)WPP_GLOBAL_Control;
    }
    ++v18;
    v21 += v23;
  }
  if ( !v18 )
  {
    if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 188) & 4) != 0 && *((_BYTE *)v16 + 185) >= 3u )
    {
      WPP_SF_(v16[22], 151, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      v16 = (PVOID *)WPP_GLOBAL_Control;
    }
    v4 = -1062600191;
  }
  if ( v4 < 0 )
    goto LABEL_89;
  v24 = 4LL * v18;
  if ( v24 > 0xFFFFFFFF )
  {
    if ( v16 == &WPP_GLOBAL_Control )
    {
LABEL_75:
      v4 = -2147024882;
      goto LABEL_76;
    }
    if ( (*((_BYTE *)v16 + 188) & 4) != 0 && *((_BYTE *)v16 + 185) >= 3u )
    {
      WPP_SF_Dd(v16[22], 152, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, v18, v18);
      v16 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_71:
    if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 188) & 4) != 0 && *((_BYTE *)v16 + 185) >= 3u )
    {
      WPP_SF_(v16[22], 153, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      v16 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_75;
  }
  v25 = CoTaskMemAlloc((unsigned int)v24);
  v16 = (PVOID *)WPP_GLOBAL_Control;
  v6 = v25;
  if ( !v25 )
    goto LABEL_71;
LABEL_76:
  if ( v4 < 0 )
    goto LABEL_89;
  v26 = 0;
  v27 = (char *)this[27]
      + (*((unsigned __int8 *)this[27] + 7) | ((unsigned __int64)*((unsigned __int8 *)this[27] + 6) << 8))
      + 8;
  if ( v18 )
  {
    while ( 1 )
    {
      v28 = (unsigned __int8)v27[1] + 2;
      if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 188) & 4) != 0 && *((_BYTE *)v16 + 185) >= 5u )
        WPP_SF_DDDd(v16[22], 154, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      *((_DWORD *)v6 + v26) = *v27 & 0x3F;
      v27 += v28;
      v26 = (unsigned int)(v26 + 1);
      if ( (unsigned int)v26 >= v18 )
        break;
      v16 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  *v34 = (enum _IMAPI_MODE_PAGE_TYPE *)v6;
  *v35 = v18;
LABEL_90:
  if ( (v4 & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(v4, (int)&CLSID_MsftDiscRecorder2, v20);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180029fd0  push    rbp
0x180029fd2  push    rbx
0x180029fd3  push    rsi
0x180029fd4  push    rdi
0x180029fd5  push    r12
0x180029fd7  push    r13
0x180029fd9  push    r14
0x180029fdb  push    r15
0x180029fdd  lea     rbp, [rsp-1Fh]
0x180029fe2  sub     rsp, 0B8h
0x180029fe9  mov     rax, cs:__security_cookie
0x180029ff0  xor     rax, rsp
0x180029ff3  mov     [rbp+57h+var_50], rax
0x180029ff7  xor     ebx, ebx
0x180029ff9  mov     [rbp+57h+var_70], r9
0x180029ffd  mov     edi, edx
0x180029fff  mov     [rbp+57h+var_78], r8
0x18002a003  xor     r12d, r12d
0x18002a006  mov     [rbp+57h+var_80], ebx
0x18002a009  xor     eax, eax
0x18002a00b  lea     rdx, WPP_GLOBAL_Control
0x18002a012  lea     r15d, [rbx+3]
0x18002a016  mov     rsi, r9
0x18002a019  mov     r13, rcx
0x18002a01c  mov     r14b, 4
0x18002a01f  test    edi, edi
0x18002a021  jz      short loc_18002A083
0x18002a023  cmp     edi, 1
0x18002a026  jz      short loc_18002A083
0x18002a028  cmp     edi, 2
0x18002a02b  jz      short loc_18002A083
0x18002a02d  cmp     edi, r15d
0x18002a030  jz      short loc_18002A083
0x18002a032  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a039  cmp     rcx, rdx
0x18002a03c  jz      short loc_18002A07A
0x18002a03e  test    [rcx+0BCh], r14b
0x18002a045  jz      short loc_18002A07A
0x18002a047  cmp     [rcx+0B9h], r15b
0x18002a04e  jb      short loc_18002A07A
0x18002a050  mov     rcx, [rcx+0B0h]
0x18002a057  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002a05e  mov     edx, 8Eh
0x18002a063  call    WPP_SF_
0x18002a068  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a06f  lea     rdx, WPP_GLOBAL_Control
0x18002a076  mov     r8, [rbp+57h+var_78]
0x18002a07a  mov     ebx, 80070057h
0x18002a07f  mov     eax, ebx
0x18002a081  jmp     short loc_18002A08A
0x18002a083  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a08a  test    r8, r8
0x18002a08d  jnz     short loc_18002A0D5
0x18002a08f  cmp     rcx, rdx
0x18002a092  jz      short loc_18002A0CC
0x18002a094  test    [rcx+0BCh], r14b
0x18002a09b  jz      short loc_18002A0CC
0x18002a09d  cmp     [rcx+0B9h], r15b
0x18002a0a4  jb      short loc_18002A0CC
0x18002a0a6  mov     rcx, [rcx+0B0h]
0x18002a0ad  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002a0b4  mov     edx, 8Fh
0x18002a0b9  call    WPP_SF_
0x18002a0be  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a0c5  lea     rdx, WPP_GLOBAL_Control
0x18002a0cc  mov     ebx, 80004003h
0x18002a0d1  mov     eax, ebx
0x18002a0d3  jmp     short loc_18002A0DF
0x18002a0d5  mov     [r8], r12
0x18002a0d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a0df  test    rsi, rsi
0x18002a0e2  jnz     short loc_18002A11D
0x18002a0e4  cmp     rcx, rdx
0x18002a0e7  jz      short loc_18002A113
0x18002a0e9  test    [rcx+0BCh], r14b
0x18002a0f0  jz      short loc_18002A113
0x18002a0f2  cmp     [rcx+0B9h], r15b
0x18002a0f9  jb      short loc_18002A113
0x18002a0fb  mov     rcx, [rcx+0B0h]
0x18002a102  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002a109  mov     edx, 90h
0x18002a10e  call    WPP_SF_
0x18002a113  mov     ebx, 80004003h
0x18002a118  jmp     loc_18002A643
0x18002a11d  mov     [rsi], r12d
0x18002a120  test    eax, eax
0x18002a122  js      loc_18002A643
0x18002a128  mov     r9d, [r13+0E8h]
0x18002a12f  test    r9b, 2
0x18002a133  jz      loc_18002A604
0x18002a139  mov     r8d, [r13+0E0h]; Size
0x18002a140  xor     edx, edx; Val
0x18002a142  mov     rcx, [r13+0D8h]; void *
0x18002a149  call    memset_0
0x18002a14e  mov     edx, [r13+0E0h]
0x18002a155  lea     r8, [rbp+57h+var_A0+10h]; union _CDB *
0x18002a159  xor     eax, eax
0x18002a15b  mov     [rsp+0F0h+var_A8], 1; unsigned __int8
0x18002a160  mov     [rbp+57h+var_58], ax
0x18002a164  lea     rcx, [r13-8]; this
0x18002a168  mov     al, dil
0x18002a16b  xorps   xmm0, xmm0
0x18002a16e  shl     al, 6
0x18002a171  mov     esi, 0Ah
0x18002a176  or      al, 3Fh
0x18002a178  xorps   xmm1, xmm1
0x18002a17b  movups  xmmword ptr [rbp+57h+var_A0+10h], xmm0
0x18002a17f  mov     [rbp+57h+var_A0+12h], al
0x18002a182  mov     r9d, esi; unsigned int
0x18002a185  mov     eax, edx
0x18002a187  mov     [rbp+57h+var_A0+18h], dl
0x18002a18a  shr     eax, 8
0x18002a18d  mov     [rbp+57h+var_A0+17h], al
0x18002a190  mov     al, dl
0x18002a192  lea     rax, [rbp+57h+var_80]
0x18002a196  mov     word ptr [rbp+57h+var_A0+10h], 85Ah
0x18002a19c  mov     [rsp+0F0h+var_B0], rax; unsigned int *
0x18002a1a1  mov     rax, [r13+0D8h]
0x18002a1a8  mov     [rsp+0F0h+var_B8], edx; unsigned int
0x18002a1ac  mov     rdx, [r13+50h]; void *
0x18002a1b0  mov     [rsp+0F0h+var_C0], rax; unsigned __int8 *
0x18002a1b5  lea     rax, [rbp+57h+var_68]
0x18002a1b9  mov     [rsp+0F0h+var_C8], esi; unsigned int
0x18002a1bd  mov     [rsp+0F0h+var_D0], rax; struct _SENSE_DATA *
0x18002a1c2  movups  xmmword ptr [rbp+57h+var_68], xmm1
0x18002a1c6  call    ?SendCommandHelper@CMsftDiscRecorder2@@AEAA?BJQEAXPEBT_CDB@@KPEAU_SENSE_DATA@@KPEAEKPEAKE@Z; CMsftDiscRecorder2::SendCommandHelper(void * const,_CDB const *,ulong,_SENSE_DATA *,ulong,uchar *,ulong,ulong *,uchar)
0x18002a1cb  mov     dword ptr [rbp+57h+var_A0], eax
0x18002a1ce  mov     ebx, eax
0x18002a1d0  test    eax, eax
0x18002a1d2  jns     loc_18002A369
0x18002a1d8  mov     r10, cs:WPP_GLOBAL_Control
0x18002a1df  lea     r11, WPP_GLOBAL_Control
0x18002a1e6  cmp     r10, r11
0x18002a1e9  jz      short loc_18002A239
0x18002a1eb  test    [r10+0BCh], r14b
0x18002a1f2  jz      short loc_18002A239
0x18002a1f4  cmp     [r10+0B9h], r15b
0x18002a1fb  jb      short loc_18002A239
0x18002a1fd  mov     eax, [r13+0E0h]
0x18002a204  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002a20b  mov     rcx, [r10+0B0h]
0x18002a212  mov     edx, 92h
0x18002a217  mov     dword ptr [rsp+0F0h+var_C0], eax
0x18002a21b  mov     r9d, edi
0x18002a21e  mov     [rsp+0F0h+var_C8], eax
0x18002a222  mov     dword ptr [rsp+0F0h+var_D0], edi
0x18002a226  call    WPP_SF_DDDd
0x18002a22b  mov     r10, cs:WPP_GLOBAL_Control
0x18002a232  lea     r11, WPP_GLOBAL_Control
0x18002a239  test    ebx, ebx
0x18002a23b  js      loc_18002A643
0x18002a241  mov     eax, [rbp+57h+var_80]
0x18002a244  cmp     eax, esi
0x18002a246  jnb     short loc_18002A29E
0x18002a248  cmp     r10, r11
0x18002a24b  jz      short loc_18002A299
0x18002a24d  test    [r10+0BCh], r14b
0x18002a254  jz      short loc_18002A299
0x18002a256  cmp     [r10+0B9h], r15b
0x18002a25d  jb      short loc_18002A299
0x18002a25f  mov     r9d, [r13+0E0h]
0x18002a266  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002a26d  mov     rcx, [r10+0B0h]
0x18002a274  mov     edx, 94h
0x18002a279  mov     dword ptr [rsp+0F0h+var_C0], eax
0x18002a27d  mov     [rsp+0F0h+var_C8], eax
0x18002a281  mov     dword ptr [rsp+0F0h+var_D0], r9d
0x18002a286  call    WPP_SF_DDDd
0x18002a28b  mov     r10, cs:WPP_GLOBAL_Control
0x18002a292  lea     r11, WPP_GLOBAL_Control
0x18002a299  mov     ebx, 0C0AA0201h
0x18002a29e  test    ebx, ebx
0x18002a2a0  js      loc_18002A643
0x18002a2a6  mov     r9, [r13+0D8h]
0x18002a2ad  xor     edi, edi
0x18002a2af  mov     edx, [r13+0E0h]
0x18002a2b6  movzx   eax, byte ptr [r9+1]
0x18002a2bb  lea     rsi, [r9+8]
0x18002a2bf  movzx   r8d, byte ptr [r9]
0x18002a2c3  lea     r15, [r9-2]
0x18002a2c7  movzx   ecx, byte ptr [r9+6]
0x18002a2cc  shl     r8d, 8
0x18002a2d0  or      r8d, eax
0x18002a2d3  shl     rcx, 8
0x18002a2d7  movzx   eax, byte ptr [r9+7]
0x18002a2dc  or      rcx, rax
0x18002a2df  add     rsi, rcx
0x18002a2e2  cmp     r8d, edx
0x18002a2e5  cmovbe  edx, r8d
0x18002a2e9  mov     eax, edx
0x18002a2eb  add     r15, rax
0x18002a2ee  cmp     rsi, r15
0x18002a2f1  jnb     loc_18002A452
0x18002a2f7  test    byte ptr [rsi], 3Fh
0x18002a2fa  jz      loc_18002A416
0x18002a300  movzx   r14d, byte ptr [rsi+1]
0x18002a305  add     r14d, 2
0x18002a309  cmp     r10, r11
0x18002a30c  jz      short loc_18002A35F
0x18002a30e  test    byte ptr [r10+0BCh], 4
0x18002a316  jz      short loc_18002A35F
0x18002a318  cmp     byte ptr [r10+0B9h], 4
0x18002a320  jb      short loc_18002A35F
0x18002a322  movzx   r9d, byte ptr [rsi]
0x18002a326  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002a32d  mov     rcx, [r10+0B0h]
0x18002a334  and     r9d, 3Fh
0x18002a338  mov     dword ptr [rsp+0F0h+var_C0], r14d
0x18002a33d  mov     edx, 96h
0x18002a342  mov     [rsp+0F0h+var_C8], r14d
0x18002a347  mov     dword ptr [rsp+0F0h+var_D0], r9d
0x18002a34c  call    WPP_SF_DDDd
0x18002a351  mov     r10, cs:WPP_GLOBAL_Control
0x18002a358  lea     r11, WPP_GLOBAL_Control
0x18002a35f  inc     edi
0x18002a361  mov     eax, r14d
0x18002a364  add     rsi, rax
0x18002a367  jmp     short loc_18002A2EE
0x18002a369  cmp     eax, 0AA0200h
0x18002a36e  jnz     loc_18002A22B
0x18002a374  lea     r8, [rbp+57h+var_A0]; struct _SENSE_DATA *
0x18002a378  lea     rdx, [rbp+57h+var_68]; union _CDB *
0x18002a37c  lea     rcx, [rbp+57h+var_A0+10h]; this
0x18002a380  call    ?TranslateSenseInfoToHResult@Imapi2Utility@@YA?BEPEBT_CDB@@PEBU_SENSE_DATA@@PEAJ@Z; Imapi2Utility::TranslateSenseInfoToHResult(_CDB const *,_SENSE_DATA const *,long *)
0x18002a385  mov     r10, cs:WPP_GLOBAL_Control
0x18002a38c  lea     r11, WPP_GLOBAL_Control
0x18002a393  cmp     r10, r11
0x18002a396  jz      short loc_18002A40E
0x18002a398  test    [r10+0BCh], r14b
0x18002a39f  jz      short loc_18002A40E
0x18002a3a1  cmp     [r10+0B9h], r15b
0x18002a3a8  jb      short loc_18002A40E
0x18002a3aa  movzx   r8d, byte ptr [rbp+57h+var_68+2]
0x18002a3af  lea     r9, [rbp+57h+var_A0+10h]
0x18002a3b3  mov     ebx, dword ptr [rbp+57h+var_A0]
0x18002a3b6  xor     ecx, ecx
0x18002a3b8  mov     qword ptr [rsp+0F0h+var_B8], r9
0x18002a3bd  and     r8d, 0Fh
0x18002a3c1  mov     dword ptr [rbp+57h+var_A0+12h], ecx
0x18002a3c4  mov     eax, 12h
0x18002a3c9  mov     word ptr [rbp+57h+var_A0+10h], ax
0x18002a3cd  mov     edx, 93h
0x18002a3d2  lea     rax, [rbp+57h+var_68]
0x18002a3d6  mov     word ptr [rbp+57h+var_A0+16h], cx
0x18002a3da  movzx   ecx, byte ptr [rbp+57h+var_68+0Ch]
0x18002a3de  mov     r9d, ebx
0x18002a3e1  mov     qword ptr [rbp+57h+var_A0+18h], rax
0x18002a3e5  movzx   eax, byte ptr [rbp+57h+var_68+0Dh]
0x18002a3e9  mov     dword ptr [rsp+0F0h+var_C0], eax
0x18002a3ed  mov     [rsp+0F0h+var_C8], ecx
0x18002a3f1  mov     rcx, [r10+0B0h]
0x18002a3f8  mov     dword ptr [rsp+0F0h+var_D0], r8d
0x18002a3fd  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002a404  call    WPP_SF_dDDD_HEX_
0x18002a409  jmp     loc_18002A22B
0x18002a40e  mov     ebx, dword ptr [rbp+57h+var_A0]
0x18002a411  jmp     loc_18002A239
0x18002a416  mov     r14b, 4
0x18002a419  cmp     r10, r11
0x18002a41c  jz      short loc_18002A455
0x18002a41e  test    [r10+0BCh], r14b
0x18002a425  jz      short loc_18002A455
0x18002a427  cmp     byte ptr [r10+0B9h], 3
0x18002a42f  jb      short loc_18002A455
0x18002a431  mov     rcx, [r10+0B0h]
0x18002a438  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002a43f  mov     edx, 95h
0x18002a444  call    WPP_SF_
0x18002a449  mov     r10, cs:WPP_GLOBAL_Control
0x18002a450  jmp     short loc_18002A455
0x18002a452  mov     r14b, 4
0x18002a455  test    edi, edi
0x18002a457  jnz     short loc_18002A49E
0x18002a459  lea     rsi, WPP_GLOBAL_Control
0x18002a460  cmp     r10, rsi
0x18002a463  jz      short loc_18002A497
0x18002a465  test    [r10+0BCh], r14b
0x18002a46c  jz      short loc_18002A497
0x18002a46e  cmp     byte ptr [r10+0B9h], 3
0x18002a476  jb      short loc_18002A497
0x18002a478  mov     rcx, [r10+0B0h]
0x18002a47f  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002a486  mov     edx, 97h
0x18002a48b  call    WPP_SF_
0x18002a490  mov     r10, cs:WPP_GLOBAL_Control
0x18002a497  mov     ebx, 0C0AA0201h
0x18002a49c  jmp     short loc_18002A4A5
0x18002a49e  lea     rsi, WPP_GLOBAL_Control
0x18002a4a5  test    ebx, ebx
0x18002a4a7  js      loc_18002A643
0x18002a4ad  mov     eax, edi
0x18002a4af  mov     ecx, 0FFFFFFFFh
0x18002a4b4  shl     rax, 2
0x18002a4b8  cmp     rax, rcx
0x18002a4bb  ja      short loc_18002A4D6
0x18002a4bd  mov     ecx, eax; cb
0x18002a4bf  call    cs:__imp_CoTaskMemAlloc
0x18002a4c5  mov     r10, cs:WPP_GLOBAL_Control
0x18002a4cc  mov     r12, rax
0x18002a4cf  test    rax, rax
  ... truncated ...
```
