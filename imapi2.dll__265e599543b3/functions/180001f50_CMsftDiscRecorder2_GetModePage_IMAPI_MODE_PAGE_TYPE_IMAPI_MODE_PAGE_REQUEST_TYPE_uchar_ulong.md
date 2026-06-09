# CMsftDiscRecorder2::GetModePage(_IMAPI_MODE_PAGE_TYPE,_IMAPI_MODE_PAGE_REQUEST_TYPE,uchar * *,ulong *)

- ea: `0x180001f50`
- end: `0x180002749`
- name: `?GetModePage@CMsftDiscRecorder2@@UEAAJW4_IMAPI_MODE_PAGE_TYPE@@W4_IMAPI_MODE_PAGE_REQUEST_TYPE@@PEAPEAEPEAK@Z`
- size: `2041`
- prototype: `__int64 __fastcall(CMsftDiscRecorder2 *__hidden this, enum _IMAPI_MODE_PAGE_TYPE, enum _IMAPI_MODE_PAGE_REQUEST_TYPE, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001f50`
- `0x180002fc8`
- `0x1800036f0`
- `0x18000ae3c`
- `0x180012700`
- `0x1800140f4`
- `0x180014134`
- `0x180016778`
- `0x1800236b4`
- `0x1800237d8`
- `0x18002d188`
- `0x18002d388`
- `0x18004983e`
- `0x18004984a`
- `0x180049880`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800020d2`
- `ole32!CoTaskMemFree` at `0x1800021aa`
- `ole32!CoTaskMemFree` at `0x1800020d2`
- `ole32!CoTaskMemFree` at `0x1800021aa`
- `ole32!CoTaskMemAlloc` at `0x1800021b6`
- `ole32!CoTaskMemAlloc` at `0x1800021b6`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::GetModePage(
        CMsftDiscRecorder2 *this,
        unsigned int a2,
        const struct _GUID *a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  signed int v5; // edi
  unsigned __int8 *v6; // r13
  enum _IMAPI_MODE_PAGE_TYPE v7; // ebx
  unsigned int v9; // r15d
  PVOID *v11; // rcx
  __int64 v13; // r9
  unsigned int v14; // eax
  unsigned int v15; // r14d
  unsigned __int8 *v16; // rax
  int v17; // eax
  int *v18; // r9
  unsigned int v19; // r15d
  unsigned int v20; // edx
  unsigned __int8 *v21; // r12
  int v22; // ebx
  _OWORD *v23; // rax
  int v24; // edx
  __int64 v25; // rcx
  unsigned int v26; // ebx
  int v27; // eax
  unsigned int v28; // esi
  PVOID *v29; // rcx
  unsigned int v31; // [rsp+54h] [rbp-6Dh]
  int v32; // [rsp+58h] [rbp-69h]
  _BYTE v33[20]; // [rsp+5Ch] [rbp-65h] BYREF
  __int16 v34; // [rsp+70h] [rbp-51h] BYREF
  int v35; // [rsp+72h] [rbp-4Fh]
  __int16 v36; // [rsp+76h] [rbp-4Bh]
  struct _SENSE_DATA *v37; // [rsp+78h] [rbp-49h]
  CMsftDiscRecorder2 *v38; // [rsp+80h] [rbp-41h]
  unsigned __int8 **v39; // [rsp+88h] [rbp-39h]
  unsigned int *v40; // [rsp+90h] [rbp-31h]
  _BYTE v41[16]; // [rsp+98h] [rbp-29h] BYREF
  struct _SENSE_DATA v42; // [rsp+A8h] [rbp-19h] BYREF

  v5 = 0;
  v6 = 0;
  v39 = a4;
  v31 = (unsigned int)a3;
  v7 = a2;
  v38 = this;
  v40 = a5;
  v9 = (unsigned int)a3;
  if ( a2 - 1 <= 0x3D )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 105, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    v5 = -2147024809;
  }
  if ( v9 > 3 )
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 188) & 4) != 0 && *((_BYTE *)v11 + 185) >= 3u )
    {
      WPP_SF_(v11[22], 106, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    v5 = -2147024809;
  }
  if ( a4 )
  {
    *a4 = 0;
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 188) & 4) != 0 && *((_BYTE *)v11 + 185) >= 3u )
    {
      WPP_SF_(v11[22], 107, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    v5 = -2147467261;
  }
  if ( !a5 )
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 188) & 4) != 0 && *((_BYTE *)v11 + 185) >= 3u )
      WPP_SF_(v11[22], 108, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    v5 = -2147467261;
    goto LABEL_27;
  }
  *a5 = 0;
  if ( v5 < 0 )
    goto LABEL_27;
  v13 = *((unsigned int *)this + 58);
  if ( (v13 & 2) == 0 )
  {
    v5 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        109,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        v13,
        -2147467259);
    }
    goto LABEL_27;
  }
  v5 = 0;
  v14 = 0;
  v32 = 0;
  v15 = 16;
  while ( v14 < 2 )
  {
    *(_OWORD *)&v33[4] = 0;
    memset(&v42, 0, sizeof(v42));
    CoTaskMemFree(v6);
    v16 = (unsigned __int8 *)CoTaskMemAlloc(v15);
    v6 = v16;
    if ( !v16 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 22), 110, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, v15, v15);
      }
      v5 = -2147024882;
      goto LABEL_115;
    }
    memset_0(v16, 0, v15);
    v33[6] = v7 & 0x3F | ((_BYTE)v9 << 6);
    v33[11] = BYTE1(v15);
    memset(&v42, 0, sizeof(v42));
    *(_WORD *)&v33[4] = 2138;
    v33[12] = v15;
    v17 = CMsftDiscRecorder2::SendCommandHelper(
            (CMsftDiscRecorder2 *)((char *)v38 - 8),
            *((void *const *)v38 + 10),
            (const union _CDB *)&v33[4],
            0xAu,
            &v42,
            0xAu,
            v6,
            v15,
            (unsigned int *)v33,
            1u);
    *(_DWORD *)v33 = v17;
    v5 = v17;
    if ( v17 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
      {
        WPP_SF_dDdDdDd(*((_QWORD *)WPP_GLOBAL_Control + 22), 111, a3, (unsigned int)v7, v7, v9, v9, v15, v15, v32);
      }
      goto LABEL_115;
    }
    if ( v17 == 11141632 )
    {
      Imapi2Utility::TranslateSenseInfoToHResult(
        (Imapi2Utility *)&v33[4],
        (const union _CDB *)&v42,
        (const struct _SENSE_DATA *)v33,
        v18);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 185) < 3u )
      {
        v5 = *(_DWORD *)v33;
      }
      else
      {
        v5 = *(_DWORD *)v33;
        v35 = 0;
        v34 = 18;
        v36 = 0;
        v37 = &v42;
        WPP_SF_ddDdD_HEX_(
          *((_QWORD *)WPP_GLOBAL_Control + 22),
          0,
          (_DWORD)a3,
          *(_DWORD *)v33,
          v7,
          v7,
          v9,
          v9,
          (__int64)&v34);
      }
      goto LABEL_115;
    }
    v19 = v6[7] | (v6[6] << 8);
    v20 = v19 + 8;
    if ( (unsigned __int64)(v19 + 9) + 1 > v15 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 113, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, v19);
      }
      v5 = -1062599937;
      goto LABEL_114;
    }
    v21 = &v6[v20];
    v22 = v21[1];
    if ( v21[1] )
    {
      v26 = v22 + 2;
      v27 = v6[1];
      v28 = (v27 | (*v6 << 8)) + 2;
      if ( v32 )
      {
        if ( v15 == v28 )
        {
          if ( (unsigned __int64)v28 - 8 >= v26 )
          {
            v15 -= v20;
            if ( v15 > v26 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
              {
                WPP_SF_DDDd(*((_QWORD *)WPP_GLOBAL_Control + 22), 121, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
              }
              v15 = v26;
            }
            memmove_0(v6, v21, v15);
            memset_0(&v6[v15], 0, v28 - v15);
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
            {
              WPP_SF_DDDd(*((_QWORD *)WPP_GLOBAL_Control + 22), 120, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
            }
            v5 = -1062599937;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
          {
            WPP_SF_DDDd(*((_QWORD *)WPP_GLOBAL_Control + 22), 119, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
          }
          v5 = -2147467259;
        }
        goto LABEL_113;
      }
      if ( (v27 | (*v6 << 8)) != 6 )
      {
        v29 = (PVOID *)WPP_GLOBAL_Control;
LABEL_88:
        v15 = v28;
        if ( v28 < 8 )
        {
          if ( v29 != &WPP_GLOBAL_Control && (*((_BYTE *)v29 + 188) & 4) != 0 && *((_BYTE *)v29 + 185) >= 3u )
            WPP_SF_Dd(v29[22], 118, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, v28, v28);
          v5 = -2147418113;
        }
LABEL_113:
        v7 = a2;
        goto LABEL_114;
      }
      v29 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
      {
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 22),
          (v27 | (*v6 << 8)) + 109,
          &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
        v29 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v19 )
      {
        if ( v29 != &WPP_GLOBAL_Control && (*((_BYTE *)v29 + 188) & 4) != 0 && *((_BYTE *)v29 + 185) >= 3u )
          WPP_SF_(v29[22], 116, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
        v5 = -1062600191;
        goto LABEL_113;
      }
      v28 = v26 + 8;
      if ( v26 )
        goto LABEL_88;
      if ( v29 != &WPP_GLOBAL_Control && (*((_BYTE *)v29 + 188) & 4) != 0 )
      {
        v7 = a2;
        if ( *((_BYTE *)v29 + 185) >= 3u )
          WPP_SF_Dd(v29[22], v28 + 109, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, a2, a2);
        goto LABEL_69;
      }
LABEL_68:
      v7 = a2;
      goto LABEL_69;
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 185) < 3u )
    {
      goto LABEL_68;
    }
    v23 = (_OWORD *)LOG_BLOB(v41, v15, v6);
    v24 = v22 + 114;
    v7 = a2;
    v25 = *((_QWORD *)WPP_GLOBAL_Control + 22);
    *(_OWORD *)&v33[4] = *v23;
    WPP_SF_dD_HEX_(v25, v24, (unsigned int)&WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, a2, a2, (__int64)&v33[4]);
LABEL_69:
    v5 = -1062600191;
LABEL_114:
    v9 = v31;
LABEL_115:
    v14 = ++v32;
    if ( v5 < 0 )
      break;
  }
  if ( v5 < 0 )
  {
LABEL_27:
    CoTaskMemFree(v6);
    goto LABEL_28;
  }
  *v39 = v6;
  *v40 = v15;
LABEL_28:
  if ( (v5 & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(v5, (int)&CLSID_MsftDiscRecorder2, a3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180001f50  push    rbp
0x180001f52  push    rbx
0x180001f53  push    rsi
0x180001f54  push    rdi
0x180001f55  push    r12
0x180001f57  push    r13
0x180001f59  push    r14
0x180001f5b  push    r15
0x180001f5d  lea     rbp, [rsp-17h]
0x180001f62  sub     rsp, 0D8h
0x180001f69  mov     rax, cs:__security_cookie
0x180001f70  xor     rax, rsp
0x180001f73  mov     [rbp+4Fh+var_50], rax
0x180001f77  mov     r12, [rbp+4Fh+arg_20]
0x180001f7b  lea     eax, [rdx-1]
0x180001f7e  xor     edi, edi
0x180001f80  mov     [rbp+4Fh+var_C0], edx
0x180001f83  xor     r13d, r13d
0x180001f86  mov     [rbp+4Fh+var_88], r9
0x180001f8a  mov     [rbp+4Fh+var_BC], r8d
0x180001f8e  mov     ebx, edx
0x180001f90  mov     [rbp+4Fh+var_90], rcx
0x180001f94  mov     rsi, r9
0x180001f97  mov     [rbp+4Fh+var_80], r12
0x180001f9b  mov     r15d, r8d
0x180001f9e  lea     rdx, WPP_GLOBAL_Control
0x180001fa5  mov     r14, rcx
0x180001fa8  cmp     eax, 3Dh ; '='
0x180001fab  jbe     short loc_180001FF6
0x180001fad  mov     rcx, cs:WPP_GLOBAL_Control
0x180001fb4  cmp     rcx, rdx
0x180001fb7  jz      short loc_180001FEF
0x180001fb9  test    byte ptr [rcx+0BCh], 4
0x180001fc0  jz      short loc_180001FEF
0x180001fc2  cmp     byte ptr [rcx+0B9h], 3
0x180001fc9  jb      short loc_180001FEF
0x180001fcb  mov     rcx, [rcx+0B0h]
0x180001fd2  lea     edx, [rdi+69h]
0x180001fd5  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180001fdc  call    WPP_SF_
0x180001fe1  mov     rcx, cs:WPP_GLOBAL_Control
0x180001fe8  lea     rdx, WPP_GLOBAL_Control
0x180001fef  mov     edi, 80070057h
0x180001ff4  jmp     short loc_180001FFD
0x180001ff6  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ffd  cmp     r15d, 3
0x180002001  jbe     short loc_180002045
0x180002003  cmp     rcx, rdx
0x180002006  jz      short loc_180002040
0x180002008  test    byte ptr [rcx+0BCh], 4
0x18000200f  jz      short loc_180002040
0x180002011  cmp     byte ptr [rcx+0B9h], 3
0x180002018  jb      short loc_180002040
0x18000201a  mov     rcx, [rcx+0B0h]
0x180002021  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180002028  mov     edx, 6Ah ; 'j'
0x18000202d  call    WPP_SF_
0x180002032  mov     rcx, cs:WPP_GLOBAL_Control
0x180002039  lea     rdx, WPP_GLOBAL_Control
0x180002040  mov     edi, 80070057h
0x180002045  test    rsi, rsi
0x180002048  jnz     short loc_18000208C
0x18000204a  cmp     rcx, rdx
0x18000204d  jz      short loc_180002085
0x18000204f  test    byte ptr [rcx+0BCh], 4
0x180002056  jz      short loc_180002085
0x180002058  cmp     byte ptr [rcx+0B9h], 3
0x18000205f  jb      short loc_180002085
0x180002061  mov     rcx, [rcx+0B0h]
0x180002068  lea     edx, [rsi+6Bh]
0x18000206b  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180002072  call    WPP_SF_
0x180002077  mov     rcx, cs:WPP_GLOBAL_Control
0x18000207e  lea     rdx, WPP_GLOBAL_Control
0x180002085  mov     edi, 80004003h
0x18000208a  jmp     short loc_180002096
0x18000208c  mov     [rsi], r13
0x18000208f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002096  test    r12, r12
0x180002099  jnz     short loc_180002118
0x18000209b  cmp     rcx, rdx
0x18000209e  jz      short loc_1800020CA
0x1800020a0  test    byte ptr [rcx+0BCh], 4
0x1800020a7  jz      short loc_1800020CA
0x1800020a9  cmp     byte ptr [rcx+0B9h], 3
0x1800020b0  jb      short loc_1800020CA
0x1800020b2  mov     rcx, [rcx+0B0h]
0x1800020b9  lea     edx, [r12+6Ch]
0x1800020be  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x1800020c5  call    WPP_SF_
0x1800020ca  mov     edi, 80004003h
0x1800020cf  mov     rcx, r13; pv
0x1800020d2  call    cs:__imp_CoTaskMemFree
0x1800020d8  mov     ecx, edi
0x1800020da  and     ecx, 80FF0000h
0x1800020e0  cmp     ecx, 80AA0000h
0x1800020e6  jnz     short loc_1800020F6
0x1800020e8  lea     rdx, CLSID_MsftDiscRecorder2; int
0x1800020ef  mov     ecx, edi; dwMessageId
0x1800020f1  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x1800020f6  mov     eax, edi
0x1800020f8  mov     rcx, [rbp+4Fh+var_50]
0x1800020fc  xor     rcx, rsp; StackCookie
0x1800020ff  call    __security_check_cookie
0x180002104  add     rsp, 0D8h
0x18000210b  pop     r15
0x18000210d  pop     r14
0x18000210f  pop     r13
0x180002111  pop     r12
0x180002113  pop     rdi
0x180002114  pop     rsi
0x180002115  pop     rbx
0x180002116  pop     rbp
0x180002117  retn
0x180002118  mov     [r12], r13d
0x18000211c  mov     eax, 80004005h
0x180002121  test    edi, edi
0x180002123  js      short loc_180002177
0x180002125  mov     r9d, [r14+0E8h]
0x18000212c  test    r9b, 2
0x180002130  jz      short loc_18000213B
0x180002132  xor     edi, edi
0x180002134  xor     eax, eax
0x180002136  mov     [rbp+4Fh+var_B8], eax
0x180002139  jmp     short loc_180002184
0x18000213b  mov     edi, eax
0x18000213d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002144  cmp     rcx, rdx
0x180002147  jz      short loc_180002177
0x180002149  test    byte ptr [rcx+0BCh], 4
0x180002150  jz      short loc_180002177
0x180002152  cmp     byte ptr [rcx+0B9h], 3
0x180002159  jb      short loc_180002177
0x18000215b  mov     rcx, [rcx+0B0h]
0x180002162  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180002169  mov     edx, 6Dh ; 'm'
0x18000216e  mov     dword ptr [rsp+110h+var_F0], eax
0x180002172  call    WPP_SF_Dd
0x180002177  xor     eax, eax
0x180002179  mov     [rbp+4Fh+var_B8], eax
0x18000217c  test    edi, edi
0x18000217e  js      loc_1800020CF
0x180002184  mov     r14d, 10h
0x18000218a  cmp     eax, 2
0x18000218d  jnb     loc_18000272E
0x180002193  xorps   xmm0, xmm0
0x180002196  xorps   xmm1, xmm1
0x180002199  xor     eax, eax
0x18000219b  mov     rcx, r13; pv
0x18000219e  movups  xmmword ptr [rbp+4Fh+var_B4+4], xmm0
0x1800021a2  mov     [rbp+4Fh+var_58], ax
0x1800021a6  movups  xmmword ptr [rbp+4Fh+var_68], xmm1
0x1800021aa  call    cs:__imp_CoTaskMemFree
0x1800021b0  mov     ecx, r14d; cb
0x1800021b3  mov     esi, r14d
0x1800021b6  call    cs:__imp_CoTaskMemAlloc
0x1800021bc  mov     r13, rax
0x1800021bf  test    rax, rax
0x1800021c2  jnz     short loc_180002211
0x1800021c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800021cb  lea     r12, WPP_GLOBAL_Control
0x1800021d2  cmp     rcx, r12
0x1800021d5  jz      short loc_180002207
0x1800021d7  test    byte ptr [rcx+0BCh], 4
0x1800021de  jz      short loc_180002207
0x1800021e0  cmp     byte ptr [rcx+0B9h], 3
0x1800021e7  jb      short loc_180002207
0x1800021e9  mov     rcx, [rcx+0B0h]
0x1800021f0  lea     edx, [rax+6Eh]
0x1800021f3  mov     r9d, r14d
0x1800021f6  mov     dword ptr [rsp+110h+var_F0], r14d
0x1800021fb  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180002202  call    WPP_SF_Dd
0x180002207  mov     edi, 8007000Eh
0x18000220c  jmp     loc_18000271E
0x180002211  mov     r8, rsi; Size
0x180002214  xor     edx, edx; Val
0x180002216  mov     rcx, r13; void *
0x180002219  call    memset_0
0x18000221e  xor     eax, eax
0x180002220  mov     [rsp+110h+var_C8], 1; unsigned __int8
0x180002225  mov     [rbp+4Fh+var_58], ax
0x180002229  lea     rdx, [rbp+4Fh+var_B4]
0x18000222d  mov     [rsp+110h+var_D0], rdx; unsigned int *
0x180002232  lea     r8, [rbp+4Fh+var_B4+4]; union _CDB *
0x180002236  mov     al, bl
0x180002238  mov     [rsp+110h+var_D8], r14d; unsigned int
0x18000223d  and     al, 3Fh
0x18000223f  mov     [rsp+110h+var_E0], r13; unsigned __int8 *
0x180002244  mov     cl, r15b
0x180002247  mov     [rsp+110h+var_E8], 0Ah; unsigned int
0x18000224f  shl     cl, 6
0x180002252  lea     rdx, [rbp+4Fh+var_68]
0x180002256  or      cl, al
0x180002258  mov     [rsp+110h+var_F0], rdx; struct _SENSE_DATA *
0x18000225d  mov     eax, r14d
0x180002260  mov     [rbp+4Fh+var_B4+6], cl
0x180002263  shr     eax, 8
0x180002266  xorps   xmm0, xmm0
0x180002269  mov     [rbp+4Fh+var_B4+0Bh], al
0x18000226c  mov     r9d, 0Ah; unsigned int
0x180002272  mov     rax, [rbp+4Fh+var_90]
0x180002276  movups  xmmword ptr [rbp+4Fh+var_68], xmm0
0x18000227a  mov     word ptr [rbp+4Fh+var_B4+4], 85Ah
0x180002280  mov     [rbp+4Fh+var_B4+0Ch], r14b
0x180002284  mov     rdx, [rax+50h]; void *
0x180002288  lea     rcx, [rax-8]; this
0x18000228c  call    ?SendCommandHelper@CMsftDiscRecorder2@@AEAA?BJQEAXPEBT_CDB@@KPEAU_SENSE_DATA@@KPEAEKPEAKE@Z; CMsftDiscRecorder2::SendCommandHelper(void * const,_CDB const *,ulong,_SENSE_DATA *,ulong,uchar *,ulong,ulong *,uchar)
0x180002291  mov     dword ptr [rbp+4Fh+var_B4], eax
0x180002294  mov     edi, eax
0x180002296  test    eax, eax
0x180002298  jns     short loc_180002303
0x18000229a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800022a1  lea     rax, WPP_GLOBAL_Control
0x1800022a8  cmp     rcx, rax
0x1800022ab  jz      loc_18000271E
0x1800022b1  test    byte ptr [rcx+0BCh], 4
0x1800022b8  jz      loc_18000271E
0x1800022be  cmp     byte ptr [rcx+0B9h], 3
0x1800022c5  jb      loc_18000271E
0x1800022cb  mov     eax, [rbp+4Fh+var_B8]
0x1800022ce  mov     edx, 6Fh ; 'o'
0x1800022d3  mov     rcx, [rcx+0B0h]
0x1800022da  mov     r9d, ebx
0x1800022dd  mov     dword ptr [rsp+110h+var_C8], eax
0x1800022e1  mov     dword ptr [rsp+110h+var_D0], r14d
0x1800022e6  mov     [rsp+110h+var_D8], r14d
0x1800022eb  mov     dword ptr [rsp+110h+var_E0], r15d
0x1800022f0  mov     [rsp+110h+var_E8], r15d
0x1800022f5  mov     dword ptr [rsp+110h+var_F0], ebx
0x1800022f9  call    WPP_SF_dDdDdDd
0x1800022fe  jmp     loc_18000271E
0x180002303  cmp     eax, 0AA0200h
0x180002308  jnz     loc_180002398
0x18000230e  lea     r8, [rbp+4Fh+var_B4]; struct _SENSE_DATA *
0x180002312  lea     rdx, [rbp+4Fh+var_68]; union _CDB *
0x180002316  lea     rcx, [rbp+4Fh+var_B4+4]; this
0x18000231a  call    ?TranslateSenseInfoToHResult@Imapi2Utility@@YA?BEPEBT_CDB@@PEBU_SENSE_DATA@@PEAJ@Z; Imapi2Utility::TranslateSenseInfoToHResult(_CDB const *,_SENSE_DATA const *,long *)
0x18000231f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002326  lea     rax, WPP_GLOBAL_Control
0x18000232d  cmp     rcx, rax
0x180002330  jz      short loc_180002390
0x180002332  test    byte ptr [rcx+0BCh], 4
0x180002339  jz      short loc_180002390
0x18000233b  cmp     byte ptr [rcx+0B9h], 3
0x180002342  jb      short loc_180002390
0x180002344  mov     edi, dword ptr [rbp+4Fh+var_B4]
0x180002347  xor     edx, edx
0x180002349  mov     eax, 12h
0x18000234e  mov     [rbp+4Fh+var_9E], edx
0x180002351  mov     [rbp+4Fh+var_A0], ax
0x180002355  mov     r9d, edi
0x180002358  lea     rax, [rbp+4Fh+var_68]
0x18000235c  mov     [rbp+4Fh+var_9A], dx
0x180002360  mov     [rbp+4Fh+var_98], rax
0x180002364  lea     rax, [rbp+4Fh+var_A0]
0x180002368  mov     rcx, [rcx+0B0h]
0x18000236f  mov     [rsp+110h+var_D0], rax
0x180002374  mov     [rsp+110h+var_D8], r15d
0x180002379  mov     dword ptr [rsp+110h+var_E0], r15d
0x18000237e  mov     [rsp+110h+var_E8], ebx
0x180002382  mov     dword ptr [rsp+110h+var_F0], ebx
0x180002386  call    WPP_SF_ddDdD_HEX_
0x18000238b  jmp     loc_18000271E
0x180002390  mov     edi, dword ptr [rbp+4Fh+var_B4]
0x180002393  jmp     loc_18000271E
0x180002398  movzx   r15d, byte ptr [r13+6]
0x18000239d  movzx   eax, byte ptr [r13+7]
0x1800023a2  shl     r15d, 8
0x1800023a6  or      r15d, eax
0x1800023a9  lea     edx, [r15+8]
0x1800023ad  lea     ecx, [rdx+1]
0x1800023b0  inc     rcx
0x1800023b3  cmp     rcx, rsi
0x1800023b6  jbe     short loc_180002402
0x1800023b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023bf  lea     rax, WPP_GLOBAL_Control
0x1800023c6  cmp     rcx, rax
0x1800023c9  jz      short loc_1800023F8
0x1800023cb  test    byte ptr [rcx+0BCh], 4
0x1800023d2  jz      short loc_1800023F8
0x1800023d4  cmp     byte ptr [rcx+0B9h], 3
0x1800023db  jb      short loc_1800023F8
0x1800023dd  mov     rcx, [rcx+0B0h]
0x1800023e4  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x1800023eb  mov     edx, 71h ; 'q'
0x1800023f0  mov     r9d, r15d
0x1800023f3  call    WPP_SF_d
0x1800023f8  mov     edi, 0C0AA02FFh
0x1800023fd  jmp     loc_18000271A
0x180002402  mov     r12d, edx
0x180002405  add     r12, r13
0x180002408  movzx   ebx, byte ptr [r12+1]
0x18000240e  test    ebx, ebx
0x180002410  jnz     short loc_18000248D
0x180002412  mov     rax, cs:WPP_GLOBAL_Control
0x180002419  lea     rcx, WPP_GLOBAL_Control
0x180002420  cmp     rax, rcx
0x180002423  jz      short loc_180002480
0x180002425  test    byte ptr [rax+0BCh], 4
  ... truncated ...
```
