# Int_FwValidatePhase2AuthSuites

- ea: `0x180017044`
- end: `0x180017710`
- name: `Int_FwValidatePhase2AuthSuites`
- size: `1740`
- prototype: `__int64 __fastcall(unsigned int, struct _tag_FW_AUTH_SUITE *, enum _tag_FW_RULE_STATUS *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014cb0`

## callees

- `0x18000ccd4`
- `0x180014028`
- `0x18001476c`
- `0x180014b6c`
- `0x180017044`
- `0x180017d1c`
- `0x18001e1d0`
- `0x18002d930`
- `0x18002daf4`
- `0x18002f38c`

## string_xrefs

- `0x18001719c`: `MPSSVC.dll`

## pseudocode

```c
__int64 __fastcall Int_FwValidatePhase2AuthSuites(
        unsigned int a1,
        struct _tag_FW_AUTH_SUITE *a2,
        enum _tag_FW_RULE_STATUS *a3,
        __int16 a4)
{
  __int64 v7; // r9
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v11; // r12d
  int v12; // r13d
  int v13; // r8d
  unsigned int v14; // r14d
  unsigned int *v15; // rsi
  int v16; // edx
  struct _tag_FW_CERT_CRITERIA *v17; // rcx
  __int64 v18; // rax
  int v19; // ecx
  int v21; // [rsp+30h] [rbp-88h]
  int v22; // [rsp+34h] [rbp-84h]
  unsigned __int16 v23[2]; // [rsp+38h] [rbp-80h] BYREF
  __int16 v24; // [rsp+3Ch] [rbp-7Ch]
  int v25; // [rsp+40h] [rbp-78h]
  _OWORD v26[3]; // [rsp+48h] [rbp-70h] BYREF

  v24 = a4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 399, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids);
  v23[0] = 0;
  memset(v26, 0, 44);
  if ( a1 == 1 && *(_DWORD *)a2 == 1 )
  {
    v7 = 87;
    *(_DWORD *)a3 = 1052722;
    v8 = 87;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 400;
      goto LABEL_109;
    }
    return v8;
  }
  v25 = 0;
  v8 = 0;
  v22 = 0;
  v11 = 0;
  v21 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  if ( !a1 )
    goto LABEL_105;
  while ( 1 )
  {
    v15 = (unsigned int *)((char *)a2 + 24 * v14);
    if ( *v15 != 1 )
    {
      if ( *v15 == 6 )
        goto LABEL_31;
      if ( *v15 == 7 )
        goto LABEL_27;
      if ( *v15 != 8 )
      {
        if ( *v15 == 5 )
          goto LABEL_23;
        if ( *v15 != 10 )
        {
          v7 = 87;
          *(_DWORD *)a3 = 1052721;
          v8 = 87;
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v10 = 401;
            goto LABEL_109;
          }
          return v8;
        }
        if ( *v15 != 1 )
        {
          switch ( *v15 )
          {
            case 5u:
LABEL_23:
              if ( (v15[1] & 0x3E) != *((_WORD *)v15 + 2) )
              {
                v7 = 87;
                *(_DWORD *)a3 = 1052736;
                v8 = 87;
                v9 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v10 = 404;
                  goto LABEL_109;
                }
                return v8;
              }
              if ( (v15[1] & 2) == 0 )
              {
                v7 = 87;
                *(_DWORD *)a3 = 1052737;
                v8 = 87;
                v9 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v10 = 405;
                  goto LABEL_109;
                }
                return v8;
              }
              v8 = Int_FwValidateCAName(*((LPCWSTR *)v15 + 1), a3);
              if ( v8 )
              {
                v9 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                {
                  return v8;
                }
                v10 = 406;
LABEL_63:
                v7 = v8;
                goto LABEL_109;
              }
              v11 = 1;
LABEL_30:
              v13 = v21;
              goto LABEL_35;
            case 6u:
LABEL_31:
              v8 = Int_FwValidateKerbAuthSuite((struct _tag_FW_AUTH_SUITE *)((char *)a2 + 24 * v14), a3);
              if ( v8 )
              {
                v9 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                {
                  return v8;
                }
                v10 = 409;
                goto LABEL_63;
              }
              v13 = v21;
              goto LABEL_35;
            case 7u:
LABEL_27:
              if ( (v15[1] & 0x3C) != *((_WORD *)v15 + 2) )
              {
                v7 = 87;
                *(_DWORD *)a3 = 1052736;
                v8 = 87;
                v9 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v10 = 402;
                  goto LABEL_109;
                }
                return v8;
              }
              v8 = Int_FwValidateCAName(*((LPCWSTR *)v15 + 1), a3);
              if ( v8 )
              {
                v9 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                {
                  return v8;
                }
                v10 = 403;
                goto LABEL_63;
              }
              v12 = 1;
              goto LABEL_30;
          }
          if ( *v15 != 8 && *v15 != 10 )
          {
            MicrosoftTelemetryAssertTriggeredArgs("MPSSVC.dll", *v15, 0);
            v13 = v21;
            goto LABEL_35;
          }
        }
      }
    }
    if ( *((_WORD *)v15 + 2) )
    {
      v7 = 87;
      *(_DWORD *)a3 = 1052736;
      v8 = 87;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v8;
      v10 = 407;
      goto LABEL_109;
    }
    if ( *((_QWORD *)v15 + 1) )
    {
      v7 = 87;
      *(_DWORD *)a3 = 3670016;
      v8 = 87;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v8;
      v10 = 408;
      goto LABEL_109;
    }
LABEL_35:
    if ( *v15 == 5 )
    {
      v25 = 1;
LABEL_39:
      v8 = Int_FwValidateCrossSuiteSigning(a2, v14, v23, a3, 0);
      if ( v8 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v8;
        v10 = 411;
        goto LABEL_63;
      }
      v17 = (struct _tag_FW_CERT_CRITERIA *)*((_QWORD *)v15 + 2);
      if ( v17 )
      {
        if ( *(_WORD *)v17 != v24 )
        {
          v7 = 87;
          *(_DWORD *)a3 = 1052786;
          v8 = 87;
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v10 = 412;
            goto LABEL_109;
          }
          return v8;
        }
        v8 = Int_FwValidateCertificateCriteria(v17, a3);
        if ( v8 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            return v8;
          v10 = 413;
          goto LABEL_63;
        }
      }
      v13 = v21;
      goto LABEL_44;
    }
    if ( *v15 != 1 )
    {
      v16 = 1;
      v22 = 1;
      if ( *v15 != 7 )
        goto LABEL_45;
      goto LABEL_39;
    }
    if ( v13 == 1 )
      break;
    v13 = 1;
    v21 = 1;
LABEL_44:
    v16 = v22;
LABEL_45:
    v18 = (int)*v15;
    if ( (unsigned int)v18 <= 0xA )
    {
      v19 = 1346;
      if ( _bittest(&v19, v18) )
      {
        if ( *((_DWORD *)v26 + v18) == 1 )
        {
          v7 = 87;
          *(_DWORD *)a3 = 1052723;
          v8 = 87;
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v10 = 414;
            goto LABEL_109;
          }
          return v8;
        }
        *((_DWORD *)v26 + v18) = 1;
      }
    }
    if ( ++v14 >= a1 )
    {
      if ( v25 && v16 )
      {
        v7 = 87;
        *(_DWORD *)a3 = 1052784;
        v8 = 87;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 415;
          goto LABEL_109;
        }
        return v8;
      }
      if ( v11 && v12 )
      {
        v7 = 87;
        *(_DWORD *)a3 = 1052769;
        v8 = 87;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 416;
          goto LABEL_109;
        }
        return v8;
      }
LABEL_105:
      if ( (unsigned int)Int_FwCertSelectionValidationCrossSuiteValid(a1, a2) )
        return v8;
      v7 = 87;
      *(_DWORD *)a3 = 1052793;
      v8 = 87;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v8;
      v10 = 417;
LABEL_109:
      WPP_SF_d(v9[2], v10, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, v7);
      return v8;
    }
  }
  v7 = 87;
  *(_DWORD *)a3 = 1052722;
  v8 = 87;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 410;
    goto LABEL_109;
  }
  return v8;
}

```

## disassembly

```asm
0x180017044  mov     [rsp+arg_0], rbx
0x180017049  push    rbp
0x18001704a  push    rsi
0x18001704b  push    rdi
0x18001704c  push    r12
0x18001704e  push    r13
0x180017050  push    r14
0x180017052  push    r15
0x180017054  sub     rsp, 80h
0x18001705b  mov     rax, cs:__security_cookie
0x180017062  xor     rax, rsp
0x180017065  mov     [rsp+0B8h+var_40], rax
0x18001706a  mov     [rsp+0B8h+var_7C], r9w
0x180017070  mov     rdi, r8
0x180017073  mov     r15, rdx
0x180017076  mov     ebp, ecx
0x180017078  mov     rcx, cs:WPP_GLOBAL_Control
0x18001707f  lea     r11, WPP_GLOBAL_Control
0x180017086  cmp     rcx, r11
0x180017089  jz      short loc_1800170AD
0x18001708b  test    byte ptr [rcx+1Ch], 8
0x18001708f  jz      short loc_1800170AD
0x180017091  mov     rcx, [rcx+10h]
0x180017095  lea     r8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x18001709c  mov     edx, 18Fh
0x1800170a1  call    WPP_SF_
0x1800170a6  lea     r11, WPP_GLOBAL_Control
0x1800170ad  xor     r9d, r9d
0x1800170b0  xorps   xmm0, xmm0
0x1800170b3  movups  xmmword ptr [rsp+0B8h+var_60], xmm0
0x1800170b8  mov     [rsp+0B8h+var_80], r9w
0x1800170be  movups  [rsp+0B8h+var_70], xmm0
0x1800170c3  lea     r10d, [r9+1]
0x1800170c7  movups  xmmword ptr [rsp+0B8h+var_60+0Ch], xmm0
0x1800170cc  cmp     ebp, r10d
0x1800170cf  jnz     short loc_180017107
0x1800170d1  cmp     [r15], r10d
0x1800170d4  jnz     short loc_180017107
0x1800170d6  lea     r9d, [r10+56h]
0x1800170da  mov     dword ptr [rdi], 101032h
0x1800170e0  mov     ebx, r9d
0x1800170e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800170ea  cmp     rcx, r11
0x1800170ed  jz      loc_1800176E6
0x1800170f3  test    [rcx+1Ch], r10b
0x1800170f7  jz      loc_1800176E6
0x1800170fd  mov     edx, 190h
0x180017102  jmp     loc_1800176D6
0x180017107  mov     [rsp+0B8h+var_78], r9d
0x18001710c  mov     ebx, r9d
0x18001710f  mov     [rsp+0B8h+var_84], r9d
0x180017114  mov     r12d, r9d
0x180017117  mov     [rsp+0B8h+var_88], r9d
0x18001711c  mov     r13d, r9d
0x18001711f  mov     r8d, r9d
0x180017122  mov     r14d, r9d
0x180017125  test    ebp, ebp
0x180017127  jz      loc_18001769D
0x18001712d  mov     eax, r14d
0x180017130  lea     rcx, [rax+rax*2]
0x180017134  lea     rsi, [r15+rcx*8]
0x180017138  cmp     [rsi], r10d
0x18001713b  jz      loc_180017258
0x180017141  cmp     dword ptr [rsi], 6
0x180017144  jz      loc_180017235
0x18001714a  cmp     dword ptr [rsi], 7
0x18001714d  jz      loc_1800171FC
0x180017153  cmp     dword ptr [rsi], 8
0x180017156  jz      loc_180017258
0x18001715c  cmp     dword ptr [rsi], 5
0x18001715f  jz      short loc_1800171BE
0x180017161  cmp     dword ptr [rsi], 0Ah
0x180017164  jnz     loc_18001737F
0x18001716a  mov     ecx, [rsi]
0x18001716c  sub     ecx, 1
0x18001716f  jz      loc_180017258
0x180017175  sub     ecx, 4
0x180017178  jz      short loc_1800171BE
0x18001717a  sub     ecx, 1
0x18001717d  jz      loc_180017235
0x180017183  sub     ecx, 1
0x180017186  jz      short loc_1800171FC
0x180017188  sub     ecx, 1
0x18001718b  jz      loc_180017258
0x180017191  cmp     ecx, 2
0x180017194  jz      loc_180017258
0x18001719a  mov     edx, [rsi]; __annotation("Debug", "TelemetryAssert", "FALSE", "Invalid pSuites[dwIndex].Method")
0x18001719c  lea     rcx, aMpssvcDll; "MPSSVC.dll"
0x1800171a3  xor     r8d, r8d
0x1800171a6  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800171ab  mov     r8d, [rsp+0B8h+var_88]
0x1800171b0  mov     r10d, 1
0x1800171b6  xor     r9d, r9d
0x1800171b9  jmp     loc_18001726D
0x1800171be  movzx   eax, word ptr [rsi+4]
0x1800171c2  and     ax, 3Eh
0x1800171c6  cmp     ax, [rsi+4]
0x1800171ca  jnz     loc_180017421
0x1800171d0  test    byte ptr [rsi+4], 2
0x1800171d4  jz      loc_1800173E7
0x1800171da  mov     rcx, [rsi+8]; pszX500
0x1800171de  mov     rdx, rdi; enum _tag_FW_RULE_STATUS *
0x1800171e1  call    ?Int_FwValidateCAName@@YAKPEAGPEAW4_tag_FW_RULE_STATUS@@@Z; Int_FwValidateCAName(ushort *,_tag_FW_RULE_STATUS *)
0x1800171e6  xor     r9d, r9d
0x1800171e9  mov     ebx, eax
0x1800171eb  test    eax, eax
0x1800171ed  jnz     loc_1800173B9
0x1800171f3  lea     r10d, [rax+1]
0x1800171f7  mov     r12d, r10d
0x1800171fa  jmp     short loc_18001722E
0x1800171fc  movzx   eax, word ptr [rsi+4]
0x180017200  and     ax, 3Ch
0x180017204  cmp     ax, [rsi+4]
0x180017208  jnz     loc_180017486
0x18001720e  mov     rcx, [rsi+8]; pszX500
0x180017212  mov     rdx, rdi; enum _tag_FW_RULE_STATUS *
0x180017215  call    ?Int_FwValidateCAName@@YAKPEAGPEAW4_tag_FW_RULE_STATUS@@@Z; Int_FwValidateCAName(ushort *,_tag_FW_RULE_STATUS *)
0x18001721a  xor     r9d, r9d
0x18001721d  mov     ebx, eax
0x18001721f  test    eax, eax
0x180017221  jnz     loc_18001745B
0x180017227  lea     r10d, [rax+1]
0x18001722b  mov     r13d, r10d
0x18001722e  mov     r8d, [rsp+0B8h+var_88]
0x180017233  jmp     short loc_18001726D
0x180017235  mov     rdx, rdi; enum _tag_FW_RULE_STATUS *
0x180017238  mov     rcx, rsi; struct _tag_FW_AUTH_SUITE *
0x18001723b  call    ?Int_FwValidateKerbAuthSuite@@YAKPEBU_tag_FW_AUTH_SUITE@@PEAW4_tag_FW_RULE_STATUS@@@Z; Int_FwValidateKerbAuthSuite(_tag_FW_AUTH_SUITE const *,_tag_FW_RULE_STATUS *)
0x180017240  xor     r9d, r9d
0x180017243  mov     ebx, eax
0x180017245  test    eax, eax
0x180017247  jnz     loc_1800174C0
0x18001724d  mov     r8d, [rsp+0B8h+var_88]
0x180017252  lea     r10d, [rax+1]
0x180017256  jmp     short loc_18001726D
0x180017258  cmp     [rsi+4], r9w
0x18001725d  jnz     loc_18001766E
0x180017263  cmp     [rsi+8], r9
0x180017267  jnz     loc_18001763B
0x18001726d  cmp     dword ptr [rsi], 5
0x180017270  jnz     short loc_180017279
0x180017272  mov     [rsp+0B8h+var_78], r10d
0x180017277  jmp     short loc_18001728E
0x180017279  cmp     [rsi], r10d
0x18001727c  jz      loc_180017369
0x180017282  cmp     dword ptr [rsi], 7
0x180017285  mov     edx, r10d
0x180017288  mov     [rsp+0B8h+var_84], edx
0x18001728c  jnz     short loc_1800172EE
0x18001728e  mov     [rsp+0B8h+var_98], r9; int *
0x180017293  lea     r8, [rsp+0B8h+var_80]; unsigned __int16 *
0x180017298  mov     r9, rdi; enum _tag_FW_RULE_STATUS *
0x18001729b  mov     edx, r14d; unsigned int
0x18001729e  mov     rcx, r15; struct _tag_FW_AUTH_SUITE *
0x1800172a1  call    ?Int_FwValidateCrossSuiteSigning@@YAKPEAU_tag_FW_AUTH_SUITE@@KPEAGPEAW4_tag_FW_RULE_STATUS@@PEAH@Z; Int_FwValidateCrossSuiteSigning(_tag_FW_AUTH_SUITE *,ulong,ushort *,_tag_FW_RULE_STATUS *,int *)
0x1800172a6  xor     r9d, r9d
0x1800172a9  mov     ebx, eax
0x1800172ab  test    eax, eax
0x1800172ad  jnz     loc_180017550
0x1800172b3  mov     rcx, [rsi+10h]; struct _tag_FW_CERT_CRITERIA *
0x1800172b7  test    rcx, rcx
0x1800172ba  jz      short loc_1800172DF
0x1800172bc  movzx   eax, [rsp+0B8h+var_7C]
0x1800172c1  cmp     [rcx], ax
0x1800172c4  jnz     loc_180017516
0x1800172ca  mov     rdx, rdi; enum _tag_FW_RULE_STATUS *
0x1800172cd  call    ?Int_FwValidateCertificateCriteria@@YAKPEAU_tag_FW_CERT_CRITERIA@@PEAW4_tag_FW_RULE_STATUS@@@Z; Int_FwValidateCertificateCriteria(_tag_FW_CERT_CRITERIA *,_tag_FW_RULE_STATUS *)
0x1800172d2  xor     r9d, r9d
0x1800172d5  mov     ebx, eax
0x1800172d7  test    eax, eax
0x1800172d9  jnz     loc_1800174EB
0x1800172df  mov     r8d, [rsp+0B8h+var_88]
0x1800172e4  mov     r10d, 1
0x1800172ea  mov     edx, [rsp+0B8h+var_84]
0x1800172ee  movsxd  rax, dword ptr [rsi]
0x1800172f1  cmp     eax, 0Ah
0x1800172f4  ja      short loc_180017310
0x1800172f6  mov     ecx, 542h
0x1800172fb  bt      ecx, eax
0x1800172fe  jnb     short loc_180017310
0x180017300  cmp     dword ptr [rsp+rax*4+0B8h+var_70], r10d
0x180017305  jz      loc_18001757B
0x18001730b  mov     dword ptr [rsp+rax*4+0B8h+var_70], r10d
0x180017310  add     r14d, r10d
0x180017313  cmp     r14d, ebp
0x180017316  jb      loc_18001712D
0x18001731c  cmp     [rsp+0B8h+var_78], 0
0x180017321  jz      loc_1800175B5
0x180017327  test    edx, edx
0x180017329  jz      loc_1800175B5
0x18001732f  mov     r9d, 57h ; 'W'
0x180017335  mov     dword ptr [rdi], 101070h
0x18001733b  mov     ebx, r9d
0x18001733e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017345  lea     rax, WPP_GLOBAL_Control
0x18001734c  cmp     rcx, rax
0x18001734f  jz      loc_1800176E6
0x180017355  test    [rcx+1Ch], r10b
0x180017359  jz      loc_1800176E6
0x18001735f  mov     edx, 19Fh
0x180017364  jmp     loc_1800176D6
0x180017369  cmp     r8d, r10d
0x18001736c  jz      loc_180017601
0x180017372  mov     r8d, r10d
0x180017375  mov     [rsp+0B8h+var_88], r10d
0x18001737a  jmp     loc_1800172EA
0x18001737f  mov     r9d, 57h ; 'W'
0x180017385  mov     dword ptr [rdi], 101031h
0x18001738b  mov     ebx, r9d
0x18001738e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017395  lea     rax, WPP_GLOBAL_Control
0x18001739c  cmp     rcx, rax
0x18001739f  jz      loc_1800176E6
0x1800173a5  test    [rcx+1Ch], r10b
0x1800173a9  jz      loc_1800176E6
0x1800173af  mov     edx, 191h
0x1800173b4  jmp     loc_1800176D6
0x1800173b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800173c0  lea     rax, WPP_GLOBAL_Control
0x1800173c7  cmp     rcx, rax
0x1800173ca  jz      loc_1800176E6
0x1800173d0  test    byte ptr [rcx+1Ch], 1
0x1800173d4  jz      loc_1800176E6
0x1800173da  mov     edx, 196h
0x1800173df  mov     r9d, ebx
0x1800173e2  jmp     loc_1800176D6
0x1800173e7  mov     r9d, 57h ; 'W'
0x1800173ed  mov     dword ptr [rdi], 101041h
0x1800173f3  mov     ebx, r9d
0x1800173f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800173fd  lea     rax, WPP_GLOBAL_Control
0x180017404  cmp     rcx, rax
0x180017407  jz      loc_1800176E6
0x18001740d  test    [rcx+1Ch], r10b
0x180017411  jz      loc_1800176E6
0x180017417  mov     edx, 195h
0x18001741c  jmp     loc_1800176D6
0x180017421  mov     r9d, 57h ; 'W'
0x180017427  mov     dword ptr [rdi], 101040h
0x18001742d  mov     ebx, r9d
0x180017430  mov     rcx, cs:WPP_GLOBAL_Control
0x180017437  lea     rax, WPP_GLOBAL_Control
0x18001743e  cmp     rcx, rax
0x180017441  jz      loc_1800176E6
0x180017447  test    [rcx+1Ch], r10b
0x18001744b  jz      loc_1800176E6
0x180017451  mov     edx, 194h
0x180017456  jmp     loc_1800176D6
0x18001745b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017462  lea     rax, WPP_GLOBAL_Control
0x180017469  cmp     rcx, rax
0x18001746c  jz      loc_1800176E6
0x180017472  test    byte ptr [rcx+1Ch], 1
0x180017476  jz      loc_1800176E6
0x18001747c  mov     edx, 193h
0x180017481  jmp     loc_1800173DF
0x180017486  mov     r9d, 57h ; 'W'
0x18001748c  mov     dword ptr [rdi], 101040h
0x180017492  mov     ebx, r9d
0x180017495  mov     rcx, cs:WPP_GLOBAL_Control
0x18001749c  lea     rax, WPP_GLOBAL_Control
0x1800174a3  cmp     rcx, rax
0x1800174a6  jz      loc_1800176E6
0x1800174ac  test    [rcx+1Ch], r10b
0x1800174b0  jz      loc_1800176E6
0x1800174b6  mov     edx, 192h
0x1800174bb  jmp     loc_1800176D6
0x1800174c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800174c7  lea     rax, WPP_GLOBAL_Control
0x1800174ce  cmp     rcx, rax
0x1800174d1  jz      loc_1800176E6
0x1800174d7  test    byte ptr [rcx+1Ch], 1
0x1800174db  jz      loc_1800176E6
0x1800174e1  mov     edx, 199h
0x1800174e6  jmp     loc_1800173DF
0x1800174eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800174f2  lea     rax, WPP_GLOBAL_Control
0x1800174f9  cmp     rcx, rax
0x1800174fc  jz      loc_1800176E6
0x180017502  test    byte ptr [rcx+1Ch], 1
0x180017506  jz      loc_1800176E6
0x18001750c  mov     edx, 19Dh
0x180017511  jmp     loc_1800173DF
0x180017516  mov     r9d, 57h ; 'W'
0x18001751c  mov     dword ptr [rdi], 101072h
0x180017522  mov     ebx, r9d
0x180017525  mov     rcx, cs:WPP_GLOBAL_Control
0x18001752c  lea     rax, WPP_GLOBAL_Control
0x180017533  cmp     rcx, rax
0x180017536  jz      loc_1800176E6
0x18001753c  test    byte ptr [rcx+1Ch], 1
0x180017540  jz      loc_1800176E6
0x180017546  mov     edx, 19Ch
0x18001754b  jmp     loc_1800176D6
0x180017550  mov     rcx, cs:WPP_GLOBAL_Control
0x180017557  lea     rax, WPP_GLOBAL_Control
0x18001755e  cmp     rcx, rax
0x180017561  jz      loc_1800176E6
0x180017567  test    byte ptr [rcx+1Ch], 1
0x18001756b  jz      loc_1800176E6
  ... truncated ...
```
