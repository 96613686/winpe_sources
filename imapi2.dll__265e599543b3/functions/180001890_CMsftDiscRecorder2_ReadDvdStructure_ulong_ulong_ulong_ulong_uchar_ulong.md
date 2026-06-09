# CMsftDiscRecorder2::ReadDvdStructure(ulong,ulong,ulong,ulong,uchar * *,ulong *)

- ea: `0x180001890`
- end: `0x180001f48`
- name: `?ReadDvdStructure@CMsftDiscRecorder2@@UEAAJKKKKPEAPEAEPEAK@Z`
- size: `1720`
- prototype: `__int64 __fastcall(CMsftDiscRecorder2 *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001890`
- `0x180002fc8`
- `0x1800036f0`
- `0x18000ae3c`
- `0x1800140f4`
- `0x180014134`
- `0x180014180`
- `0x180014250`
- `0x180016778`
- `0x1800236b4`
- `0x18002cdc8`
- `0x18002cec0`
- `0x180049832`
- `0x18004984a`
- `0x180049880`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180001bff`
- `ole32!CoTaskMemFree` at `0x180001bff`
- `ole32!CoTaskMemAlloc` at `0x180001ba3`
- `ole32!CoTaskMemAlloc` at `0x180001ba3`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::ReadDvdStructure(
        void **this,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  unsigned __int8 **v7; // rax
  signed int v10; // ebx
  unsigned int v11; // edi
  char v12; // r15
  unsigned int v13; // r13d
  PVOID *v14; // r10
  __int64 v15; // rdx
  __int64 v16; // r9
  unsigned __int8 *v17; // rsi
  unsigned int v18; // edi
  int v19; // ecx
  unsigned __int8 *v20; // rax
  unsigned __int8 *v21; // r14
  const struct _GUID *v22; // r8
  unsigned int v24; // edx
  void *v25; // rdx
  int v26; // eax
  int *v27; // r9
  int v28; // r9d
  unsigned int *v29; // rcx
  int v30; // [rsp+30h] [rbp-71h]
  unsigned __int8 *v31; // [rsp+30h] [rbp-71h]
  unsigned int v32; // [rsp+38h] [rbp-69h]
  _BYTE v33[32]; // [rsp+50h] [rbp-51h] BYREF
  unsigned __int8 **v34; // [rsp+70h] [rbp-31h]
  unsigned int *v35; // [rsp+78h] [rbp-29h]
  struct _SENSE_DATA v36; // [rsp+80h] [rbp-21h] BYREF

  v7 = a6;
  v35 = a7;
  v10 = 0;
  v34 = a6;
  v11 = 0;
  v12 = a4;
  v13 = a3;
  if ( a2 > 0xFF )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 185) < 2u )
    {
      goto LABEL_17;
    }
    v15 = 64;
    a4 = a2;
LABEL_16:
    WPP_SF_d(v14[22], v15, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, a4);
    v14 = (PVOID *)WPP_GLOBAL_Control;
    v7 = v34;
LABEL_17:
    v10 = -2147024809;
    goto LABEL_19;
  }
  if ( (unsigned int)a4 > 0xFF )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 185) < 2u )
    {
      goto LABEL_17;
    }
    v15 = 65;
    goto LABEL_16;
  }
  if ( a5 > 3 )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 185) < 2u )
    {
      goto LABEL_17;
    }
    v15 = 66;
    a4 = a5;
    goto LABEL_16;
  }
  v14 = (PVOID *)WPP_GLOBAL_Control;
LABEL_19:
  if ( v7 )
  {
    *v7 = 0;
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 188) & 4) != 0 && *((_BYTE *)v14 + 185) >= 2u )
    {
      WPP_SF_(v14[22], 67, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
    v10 = -2147467261;
  }
  if ( !v35 )
  {
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 188) & 4) != 0 && *((_BYTE *)v14 + 185) >= 2u )
    {
      WPP_SF_(v14[22], (unsigned int)((_DWORD)v35 + 68), &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
    v10 = -2147467261;
    goto LABEL_39;
  }
  *v35 = 0;
  if ( v10 < 0 )
  {
LABEL_38:
    v14 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_39;
  }
  v16 = *((unsigned int *)this + 58);
  if ( (v16 & 2) == 0 )
  {
    v10 = -2147467259;
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 185) < 3u )
    {
      goto LABEL_39;
    }
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 22),
      69,
      &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
      v16,
      -2147467259);
    goto LABEL_38;
  }
  memset_0(this[27], 0, *((unsigned int *)this + 56));
  v24 = *((_DWORD *)this + 56);
  *(_OWORD *)&v33[16] = 0;
  v33[18] = HIBYTE(v13);
  v33[19] = BYTE2(v13);
  v33[25] = v24;
  v33[20] = BYTE1(v13);
  v33[24] = BYTE1(v24);
  v33[16] = -83;
  v32 = v24;
  v25 = this[10];
  v31 = (unsigned __int8 *)this[27];
  memset(&v36, 0, sizeof(v36));
  v33[21] = v13;
  v33[22] = v12;
  v33[23] = a2;
  v33[26] = (_BYTE)a5 << 6;
  v26 = CMsftDiscRecorder2::SendCommandHelper(
          (CMsftDiscRecorder2 *)(this - 1),
          v25,
          (const union _CDB *)&v33[16],
          0xCu,
          &v36,
          0xAu,
          v31,
          v32,
          (unsigned int *)v33,
          1u);
  *(_DWORD *)v33 = v26;
  v10 = v26;
  if ( v26 < 0 )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 185) < 3u )
    {
      goto LABEL_81;
    }
    WPP_SF_ddD(
      *((_QWORD *)WPP_GLOBAL_Control + 22),
      70,
      &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
      *((unsigned int *)this + 56),
      *((_DWORD *)this + 56),
      v26);
    goto LABEL_80;
  }
  if ( v26 != 11141632 )
  {
    a3 = *((unsigned int *)this + 56);
    v11 = (HIBYTE(*(unsigned __int16 *)this[27]) | ((unsigned __int8)*(_WORD *)this[27] << 8)) + 2;
    if ( v11 > (unsigned __int64)(a3 - 4) )
    {
      v10 = -2147467259;
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 185) < 3u )
      {
        goto LABEL_39;
      }
      v30 = *((_DWORD *)this + 56);
      WPP_SF_DDDd(*((_QWORD *)WPP_GLOBAL_Control + 22), 72, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    }
    goto LABEL_80;
  }
  Imapi2Utility::TranslateSenseInfoToHResult(
    (Imapi2Utility *)&v33[16],
    (const union _CDB *)&v36,
    (const struct _SENSE_DATA *)v33,
    v27);
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
  {
    v28 = *((_DWORD *)this + 56);
    v10 = *(_DWORD *)v33;
    *(_WORD *)&v33[16] = 18;
    *(_QWORD *)&v33[24] = &v36;
    *(_DWORD *)&v33[18] = 0;
    *(_WORD *)&v33[22] = 0;
    WPP_SF_dDDDD_HEX_d(
      *((_QWORD *)WPP_GLOBAL_Control + 22),
      *((_BYTE *)&v36 + 2) & 0xF,
      (unsigned int)&v33[16],
      v28,
      v28,
      *((_BYTE *)&v36 + 2) & 0xF,
      v36.AdditionalSenseCode,
      v36.AdditionalSenseCodeQualifier,
      (__int64)&v33[16]);
LABEL_80:
    v14 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_81;
  }
  v10 = *(_DWORD *)v33;
LABEL_81:
  if ( v10 < 0 )
    goto LABEL_60;
  if ( v11 < 4 )
  {
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 188) & 4) != 0 && *((_BYTE *)v14 + 185) >= 3u )
    {
      WPP_SF_dDdDdD(
        v14[22],
        73,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        *((unsigned int *)this + 56),
        *((_DWORD *)this + 56),
        v11,
        v11,
        4,
        4);
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
    v10 = -1062600178;
  }
LABEL_39:
  if ( v10 < 0 )
    goto LABEL_60;
  v17 = (unsigned __int8 *)this[27];
  v18 = v11 - 4;
  if ( a2 == 48 && v18 < 0x28 )
  {
    v10 = -1062600178;
    if ( v14 == &WPP_GLOBAL_Control || (*((_BYTE *)v14 + 188) & 4) == 0 || *((_BYTE *)v14 + 185) < 3u )
      goto LABEL_60;
    WPP_SF_DdDdD(v14[22], &WPP_GLOBAL_Control, a3, v13, v18, v18, v30);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 < 0 )
    goto LABEL_60;
  if ( a2 == 48 )
  {
    v19 = v17[7] | ((v17[6] | ((v17[5] | (v17[4] << 8)) << 8)) << 8);
    if ( v19 != v13 )
    {
      v10 = -1062600178;
      if ( v14 == &WPP_GLOBAL_Control || (*((_BYTE *)v14 + 188) & 4) == 0 || *((_BYTE *)v14 + 185) < 3u )
        goto LABEL_60;
      WPP_SF_Dd(v14[22], 75, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, v13, v19);
    }
  }
  if ( v10 < 0 )
  {
LABEL_60:
    CoTaskMemFree(0);
    goto LABEL_61;
  }
  v20 = (unsigned __int8 *)CoTaskMemAlloc(v18);
  v21 = v20;
  if ( !v20 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 22), 76, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, v18, v18);
    }
    v10 = -2147024882;
    goto LABEL_60;
  }
  memcpy_0(v20, v17 + 4, v18);
  v29 = v35;
  *v34 = v21;
  *v29 = v18;
LABEL_61:
  if ( (v10 & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(v10, (int)&CLSID_MsftDiscRecorder2, v22);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180001890  push    rbp
0x180001892  push    rbx
0x180001893  push    rsi
0x180001894  push    rdi
0x180001895  push    r12
0x180001897  push    r13
0x180001899  push    r14
0x18000189b  push    r15
0x18000189d  lea     rbp, [rsp-7]
0x1800018a2  sub     rsp, 0A8h
0x1800018a9  mov     rax, cs:__security_cookie
0x1800018b0  xor     rax, rsp
0x1800018b3  mov     [rbp+3Fh+var_48], rax
0x1800018b7  mov     rax, [rbp+3Fh+arg_28]
0x1800018bb  mov     rsi, rcx
0x1800018be  mov     rcx, [rbp+3Fh+arg_30]
0x1800018c2  mov     r12d, edx
0x1800018c5  mov     r14d, [rbp+3Fh+arg_20]
0x1800018c9  lea     rdx, WPP_GLOBAL_Control
0x1800018d0  mov     [rbp+3Fh+var_68], rcx
0x1800018d4  xor     ebx, ebx
0x1800018d6  mov     ecx, 0FFh
0x1800018db  mov     [rbp+3Fh+var_70], rax
0x1800018df  xor     edi, edi
0x1800018e1  mov     r15d, r9d
0x1800018e4  mov     r13d, r8d
0x1800018e7  cmp     r12d, ecx
0x1800018ea  jbe     short loc_180001920
0x1800018ec  mov     r10, cs:WPP_GLOBAL_Control
0x1800018f3  cmp     r10, rdx
0x1800018f6  jz      loc_18000199F
0x1800018fc  test    byte ptr [r10+0BCh], 4
0x180001904  jz      loc_18000199F
0x18000190a  cmp     byte ptr [r10+0B9h], 2
0x180001912  jb      loc_18000199F
0x180001918  lea     edx, [rbx+40h]
0x18000191b  mov     r9d, r12d
0x18000191e  jmp     short loc_18000197A
0x180001920  cmp     r15d, ecx
0x180001923  jbe     short loc_18000194C
0x180001925  mov     r10, cs:WPP_GLOBAL_Control
0x18000192c  cmp     r10, rdx
0x18000192f  jz      short loc_18000199F
0x180001931  test    byte ptr [r10+0BCh], 4
0x180001939  jz      short loc_18000199F
0x18000193b  cmp     byte ptr [r10+0B9h], 2
0x180001943  jb      short loc_18000199F
0x180001945  mov     edx, 41h ; 'A'
0x18000194a  jmp     short loc_18000197A
0x18000194c  cmp     r14d, 3
0x180001950  jbe     short loc_1800019A6
0x180001952  mov     r10, cs:WPP_GLOBAL_Control
0x180001959  cmp     r10, rdx
0x18000195c  jz      short loc_18000199F
0x18000195e  test    byte ptr [r10+0BCh], 4
0x180001966  jz      short loc_18000199F
0x180001968  cmp     byte ptr [r10+0B9h], 2
0x180001970  jb      short loc_18000199F
0x180001972  mov     edx, 42h ; 'B'
0x180001977  mov     r9d, r14d
0x18000197a  mov     rcx, [r10+0B0h]
0x180001981  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180001988  call    WPP_SF_d
0x18000198d  mov     r10, cs:WPP_GLOBAL_Control
0x180001994  lea     rdx, WPP_GLOBAL_Control
0x18000199b  mov     rax, [rbp+3Fh+var_70]
0x18000199f  mov     ebx, 80070057h
0x1800019a4  jmp     short loc_1800019AD
0x1800019a6  mov     r10, cs:WPP_GLOBAL_Control
0x1800019ad  test    rax, rax
0x1800019b0  jnz     short loc_1800019F6
0x1800019b2  cmp     r10, rdx
0x1800019b5  jz      short loc_1800019EF
0x1800019b7  test    byte ptr [r10+0BCh], 4
0x1800019bf  jz      short loc_1800019EF
0x1800019c1  cmp     byte ptr [r10+0B9h], 2
0x1800019c9  jb      short loc_1800019EF
0x1800019cb  mov     rcx, [r10+0B0h]
0x1800019d2  lea     edx, [rax+43h]
0x1800019d5  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x1800019dc  call    WPP_SF_
0x1800019e1  mov     r10, cs:WPP_GLOBAL_Control
0x1800019e8  lea     rdx, WPP_GLOBAL_Control
0x1800019ef  mov     ebx, 80004003h
0x1800019f4  jmp     short loc_180001A00
0x1800019f6  mov     [rax], rdi
0x1800019f9  mov     r10, cs:WPP_GLOBAL_Control
0x180001a00  mov     rax, [rbp+3Fh+var_68]
0x180001a04  test    rax, rax
0x180001a07  jnz     short loc_180001A4D
0x180001a09  cmp     r10, rdx
0x180001a0c  jz      short loc_180001A46
0x180001a0e  test    byte ptr [r10+0BCh], 4
0x180001a16  jz      short loc_180001A46
0x180001a18  cmp     byte ptr [r10+0B9h], 2
0x180001a20  jb      short loc_180001A46
0x180001a22  mov     rcx, [r10+0B0h]
0x180001a29  lea     edx, [rax+44h]
0x180001a2c  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180001a33  call    WPP_SF_
0x180001a38  mov     r10, cs:WPP_GLOBAL_Control
0x180001a3f  lea     rdx, WPP_GLOBAL_Control
0x180001a46  mov     ebx, 80004003h
0x180001a4b  jmp     short loc_180001AB3
0x180001a4d  mov     [rax], edi
0x180001a4f  test    ebx, ebx
0x180001a51  js      short loc_180001AAC
0x180001a53  mov     r9d, [rsi+0E8h]
0x180001a5a  test    r9b, 2
0x180001a5e  jnz     loc_180001C45
0x180001a64  mov     ebx, 80004005h
0x180001a69  mov     r10, cs:WPP_GLOBAL_Control
0x180001a70  cmp     r10, rdx
0x180001a73  jz      short loc_180001AB3
0x180001a75  test    byte ptr [r10+0BCh], 4
0x180001a7d  jz      short loc_180001AB3
0x180001a7f  cmp     byte ptr [r10+0B9h], 3
0x180001a87  jb      short loc_180001AB3
0x180001a89  mov     rcx, [r10+0B0h]
0x180001a90  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180001a97  mov     edx, 45h ; 'E'
0x180001a9c  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180001aa0  call    WPP_SF_Dd
0x180001aa5  lea     rdx, WPP_GLOBAL_Control
0x180001aac  mov     r10, cs:WPP_GLOBAL_Control
0x180001ab3  test    ebx, ebx
0x180001ab5  js      loc_180001BFD
0x180001abb  mov     rsi, [rsi+0D8h]
0x180001ac2  add     edi, 0FFFFFFFCh
0x180001ac5  cmp     r12d, 30h ; '0'
0x180001ac9  jnz     short loc_180001B1F
0x180001acb  cmp     edi, 28h ; '('
0x180001ace  jnb     short loc_180001B1F
0x180001ad0  mov     ebx, 0C0AA020Eh
0x180001ad5  cmp     r10, rdx
0x180001ad8  jz      loc_180001BFD
0x180001ade  test    byte ptr [r10+0BCh], 4
0x180001ae6  jz      loc_180001BFD
0x180001aec  cmp     byte ptr [r10+0B9h], 3
0x180001af4  jb      loc_180001BFD
0x180001afa  mov     rcx, [r10+0B0h]
0x180001b01  mov     r9d, r13d
0x180001b04  mov     [rsp+0E0h+var_B8], edi
0x180001b08  mov     dword ptr [rsp+0E0h+var_C0], edi
0x180001b0c  call    WPP_SF_DdDdD
0x180001b11  mov     r10, cs:WPP_GLOBAL_Control
0x180001b18  lea     rdx, WPP_GLOBAL_Control
0x180001b1f  test    ebx, ebx
0x180001b21  js      loc_180001BFD
0x180001b27  cmp     r12d, 30h ; '0'
0x180001b2b  jnz     short loc_180001B9A
0x180001b2d  movzx   eax, byte ptr [rsi+5]
0x180001b31  movzx   ecx, byte ptr [rsi+4]
0x180001b35  shl     ecx, 8
0x180001b38  or      ecx, eax
0x180001b3a  movzx   eax, byte ptr [rsi+6]
0x180001b3e  shl     ecx, 8
0x180001b41  or      ecx, eax
0x180001b43  movzx   eax, byte ptr [rsi+7]
0x180001b47  shl     ecx, 8
0x180001b4a  or      ecx, eax
0x180001b4c  cmp     ecx, r13d
0x180001b4f  jz      short loc_180001B9A
0x180001b51  mov     ebx, 0C0AA020Eh
0x180001b56  cmp     r10, rdx
0x180001b59  jz      loc_180001BFD
0x180001b5f  test    byte ptr [r10+0BCh], 4
0x180001b67  jz      loc_180001BFD
0x180001b6d  cmp     byte ptr [r10+0B9h], 3
0x180001b75  jb      loc_180001BFD
0x180001b7b  mov     dword ptr [rsp+0E0h+var_C0], ecx
0x180001b7f  lea     edx, [r12+1Bh]
0x180001b84  mov     rcx, [r10+0B0h]
0x180001b8b  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180001b92  mov     r9d, r13d
0x180001b95  call    WPP_SF_Dd
0x180001b9a  test    ebx, ebx
0x180001b9c  js      short loc_180001BFD
0x180001b9e  mov     ecx, edi; cb
0x180001ba0  mov     r15d, edi
0x180001ba3  call    cs:__imp_CoTaskMemAlloc
0x180001ba9  mov     r14, rax
0x180001bac  test    rax, rax
0x180001baf  jnz     loc_180001F27
0x180001bb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180001bbc  lea     rax, WPP_GLOBAL_Control
0x180001bc3  cmp     rcx, rax
0x180001bc6  jz      short loc_180001BF8
0x180001bc8  test    byte ptr [rcx+0BCh], 4
0x180001bcf  jz      short loc_180001BF8
0x180001bd1  cmp     byte ptr [rcx+0B9h], 3
0x180001bd8  jb      short loc_180001BF8
0x180001bda  mov     rcx, [rcx+0B0h]
0x180001be1  lea     edx, [r14+4Ch]
0x180001be5  mov     r9d, edi
0x180001be8  mov     dword ptr [rsp+0E0h+var_C0], edi
0x180001bec  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180001bf3  call    WPP_SF_Dd
0x180001bf8  mov     ebx, 8007000Eh
0x180001bfd  xor     ecx, ecx; pv
0x180001bff  call    cs:__imp_CoTaskMemFree
0x180001c05  mov     ecx, ebx
0x180001c07  and     ecx, 80FF0000h
0x180001c0d  cmp     ecx, 80AA0000h
0x180001c13  jnz     short loc_180001C23
0x180001c15  lea     rdx, CLSID_MsftDiscRecorder2; int
0x180001c1c  mov     ecx, ebx; dwMessageId
0x180001c1e  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x180001c23  mov     eax, ebx
0x180001c25  mov     rcx, [rbp+3Fh+var_48]
0x180001c29  xor     rcx, rsp; StackCookie
0x180001c2c  call    __security_check_cookie
0x180001c31  add     rsp, 0A8h
0x180001c38  pop     r15
0x180001c3a  pop     r14
0x180001c3c  pop     r13
0x180001c3e  pop     r12
0x180001c40  pop     rdi
0x180001c41  pop     rsi
0x180001c42  pop     rbx
0x180001c43  pop     rbp
0x180001c44  retn
0x180001c45  mov     r8d, [rsi+0E0h]; Size
0x180001c4c  xor     edx, edx; Val
0x180001c4e  mov     rcx, [rsi+0D8h]; void *
0x180001c55  call    memset_0
0x180001c5a  mov     edx, [rsi+0E0h]
0x180001c60  lea     r8, [rbp+3Fh+var_90+10h]; union _CDB *
0x180001c64  xor     eax, eax
0x180001c66  mov     [rsp+0E0h+var_98], 1; unsigned __int8
0x180001c6b  mov     [rbp+3Fh+var_50], ax
0x180001c6f  lea     rcx, [rsi-8]; this
0x180001c73  mov     eax, r13d
0x180001c76  shl     r14b, 6
0x180001c7a  shr     eax, 18h
0x180001c7d  xorps   xmm0, xmm0
0x180001c80  movups  xmmword ptr [rbp+3Fh+var_90+10h], xmm0
0x180001c84  mov     [rbp+3Fh+var_90+12h], al
0x180001c87  mov     eax, r13d
0x180001c8a  shr     eax, 10h
0x180001c8d  xorps   xmm1, xmm1
0x180001c90  mov     [rbp+3Fh+var_90+13h], al
0x180001c93  mov     r9d, 0Ch; unsigned int
0x180001c99  mov     eax, r13d
0x180001c9c  mov     [rbp+3Fh+var_90+19h], dl
0x180001c9f  shr     eax, 8
0x180001ca2  mov     [rbp+3Fh+var_90+14h], al
0x180001ca5  mov     eax, edx
0x180001ca7  shr     eax, 8
0x180001caa  mov     [rbp+3Fh+var_90+18h], al
0x180001cad  mov     al, dl
0x180001caf  lea     rax, [rbp+3Fh+var_90]
0x180001cb3  mov     [rbp+3Fh+var_90+10h], 0ADh
0x180001cb7  mov     [rsp+0E0h+var_A0], rax; unsigned int *
0x180001cbc  mov     rax, [rsi+0D8h]
0x180001cc3  mov     [rsp+0E0h+var_A8], edx; unsigned int
0x180001cc7  mov     rdx, [rsi+50h]; void *
0x180001ccb  mov     [rsp+0E0h+var_B0], rax; unsigned __int8 *
0x180001cd0  lea     rax, [rbp+3Fh+var_60]
0x180001cd4  mov     [rsp+0E0h+var_B8], 0Ah; unsigned int
0x180001cdc  mov     [rsp+0E0h+var_C0], rax; struct _SENSE_DATA *
0x180001ce1  movups  xmmword ptr [rbp+3Fh+var_60], xmm1
0x180001ce5  mov     [rbp+3Fh+var_90+15h], r13b
0x180001ce9  mov     [rbp+3Fh+var_90+16h], r15b
0x180001ced  mov     [rbp+3Fh+var_90+17h], r12b
0x180001cf1  mov     [rbp+3Fh+var_90+1Ah], r14b
0x180001cf5  call    ?SendCommandHelper@CMsftDiscRecorder2@@AEAA?BJQEAXPEBT_CDB@@KPEAU_SENSE_DATA@@KPEAEKPEAKE@Z; CMsftDiscRecorder2::SendCommandHelper(void * const,_CDB const *,ulong,_SENSE_DATA *,ulong,uchar *,ulong,ulong *,uchar)
0x180001cfa  mov     dword ptr [rbp+3Fh+var_90], eax
0x180001cfd  mov     ebx, eax
0x180001cff  test    eax, eax
0x180001d01  jns     short loc_180001D63
0x180001d03  mov     r10, cs:WPP_GLOBAL_Control
0x180001d0a  lea     rdx, WPP_GLOBAL_Control
0x180001d11  cmp     r10, rdx
0x180001d14  jz      loc_180001EA9
0x180001d1a  test    byte ptr [r10+0BCh], 4
0x180001d22  jz      loc_180001EA9
0x180001d28  cmp     byte ptr [r10+0B9h], 3
0x180001d30  jb      loc_180001EA9
0x180001d36  mov     r9d, [rsi+0E0h]
0x180001d3d  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180001d44  mov     rcx, [r10+0B0h]
0x180001d4b  mov     edx, 46h ; 'F'
0x180001d50  mov     [rsp+0E0h+var_B8], eax
0x180001d54  mov     dword ptr [rsp+0E0h+var_C0], r9d
0x180001d59  call    WPP_SF_ddD
0x180001d5e  jmp     loc_180001E9B
0x180001d63  cmp     eax, 0AA0200h
0x180001d68  jnz     loc_180001E10
0x180001d6e  lea     r8, [rbp+3Fh+var_90]; struct _SENSE_DATA *
0x180001d72  lea     rdx, [rbp+3Fh+var_60]; union _CDB *
0x180001d76  lea     rcx, [rbp+3Fh+var_90+10h]; this
0x180001d7a  call    ?TranslateSenseInfoToHResult@Imapi2Utility@@YA?BEPEBT_CDB@@PEBU_SENSE_DATA@@PEAJ@Z; Imapi2Utility::TranslateSenseInfoToHResult(_CDB const *,_SENSE_DATA const *,long *)
0x180001d7f  mov     r10, cs:WPP_GLOBAL_Control
0x180001d86  lea     rdx, WPP_GLOBAL_Control
0x180001d8d  cmp     r10, rdx
0x180001d90  jz      short loc_180001E08
0x180001d92  test    byte ptr [r10+0BCh], 4
0x180001d9a  jz      short loc_180001E08
0x180001d9c  cmp     byte ptr [r10+0B9h], 3
  ... truncated ...
```
