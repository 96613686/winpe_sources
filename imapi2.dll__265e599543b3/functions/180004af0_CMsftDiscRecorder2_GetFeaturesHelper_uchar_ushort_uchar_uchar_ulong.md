# CMsftDiscRecorder2::GetFeaturesHelper(uchar,ushort,uchar,uchar * *,ulong *)

- ea: `0x180004af0`
- end: `0x1800050f3`
- name: `?GetFeaturesHelper@CMsftDiscRecorder2@@AEAAJEGEPEAPEAEPEAK@Z`
- size: `1539`
- prototype: `__int64 __fastcall(CMsftDiscRecorder2 *__hidden this, unsigned __int8, unsigned __int16, unsigned __int8, unsigned __int8 **, unsigned int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180002da0`
- `0x1800053f0`
- `0x180029d10`

## callees

- `0x180004af0`
- `0x180005100`
- `0x1800140f4`
- `0x180014134`
- `0x180014180`
- `0x180016778`
- `0x18004983e`
- `0x18004984a`
- `0x180049880`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180004cd0`
- `ole32!CoTaskMemFree` at `0x180004cd0`
- `ole32!CoTaskMemAlloc` at `0x180004c38`
- `ole32!CoTaskMemAlloc` at `0x180004c38`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::GetFeaturesHelper(
        CMsftDiscRecorder2 *this,
        char a2,
        unsigned __int16 a3,
        char a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  int v7; // edi
  int v9; // r13d
  int v10; // ebx
  PVOID *v11; // rcx
  bool v12; // zf
  void *v13; // rdx
  int v14; // eax
  unsigned int v15; // esi
  _BYTE *v16; // rax
  _BYTE *v17; // rdi
  void *v18; // rdx
  CMsftDiscRecorder2 *v19; // rcx
  __int64 v21; // r9
  unsigned int v22; // esi
  unsigned int v24; // [rsp+44h] [rbp-74h] BYREF
  int v25; // [rsp+48h] [rbp-70h]
  int v26; // [rsp+50h] [rbp-68h] BYREF
  int v27; // [rsp+54h] [rbp-64h]
  __int128 v28; // [rsp+58h] [rbp-60h]
  __int64 v29; // [rsp+68h] [rbp-50h] BYREF

  v7 = a3;
  if ( a2 )
    v9 = a4 != 0;
  else
    v9 = 2;
  if ( a5 )
  {
    *a5 = 0;
    v10 = 0;
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 29, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    v10 = -2147467261;
  }
  if ( !a6 )
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 188) & 4) != 0 && *((_BYTE *)v11 + 185) >= 3u )
      WPP_SF_(v11[22], 30, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    return (unsigned int)-2147467261;
  }
  *a6 = 0;
  v12 = v10 == 0;
  if ( v10 < 0 )
    goto LABEL_7;
  v21 = *((unsigned int *)this + 60);
  if ( (v21 & 2) == 0 )
  {
    v10 = -2147467259;
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        31,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        v21,
        -2147467259);
    }
    v12 = 0;
LABEL_7:
    if ( !v12 )
      return (unsigned int)v10;
  }
  v24 = 0;
  v25 = v7;
  v26 = v7;
  v29 = 0;
  v13 = (void *)*((_QWORD *)this + 11);
  v28 = 0;
  v27 = v9;
  v14 = CMsftDiscRecorder2::SaferDeviceIoControl((CMsftDiscRecorder2 *)v11, v13, 0x24058u, &v26, 0x18u, &v29, 8u, &v24);
  v10 = v14;
  if ( v14 == -2147024895 )
  {
    v10 = -1062600180;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 32, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    }
  }
  else if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        33,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        (unsigned int)v14);
    }
  }
  else if ( v24 == 8 )
  {
    if ( !v14 )
    {
      v15 = (BYTE3(v29) | ((BYTE2(v29) | ((BYTE1(v29) | ((unsigned __int8)v29 << 8)) << 8)) << 8)) + 4;
      if ( v15 == v24 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 35, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
        }
        return (unsigned int)-1062600182;
      }
      else
      {
        v16 = CoTaskMemAlloc(v15);
        v17 = v16;
        if ( v16 )
        {
          v24 = 0;
          memset_0(v16, 0, v15);
          v18 = (void *)*((_QWORD *)this + 11);
          v26 = v25;
          v27 = v9;
          v28 = 0;
          v10 = CMsftDiscRecorder2::SaferDeviceIoControl(v19, v18, 0x24058u, &v26, 0x18u, v17, v15, &v24);
          if ( v10 == -2147024895 )
          {
            v10 = -1062600180;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 37, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
            }
          }
          else if ( v10 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
            {
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 22),
                38,
                &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
                v15,
                v10);
            }
          }
          else if ( v24 == v15 )
          {
            v22 = v15 - 8;
            memmove_0(v17, v17 + 8, v22);
            if ( a2 || !a4 || (v17[2] & 1) != 0 )
            {
              *a5 = v17;
              v10 = 0;
              *a6 = v22;
              return (unsigned int)v10;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 40, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
            }
            v10 = -1062600181;
          }
          else
          {
            v10 = -2147467259;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
            {
              WPP_SF_ddD(
                *((_QWORD *)WPP_GLOBAL_Control + 22),
                39,
                &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
                v24,
                v15,
                -2147467259);
            }
          }
          CoTaskMemFree(v17);
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
          {
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 22),
              36,
              &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
              v15,
              v15);
          }
          return (unsigned int)-2147024882;
        }
      }
    }
  }
  else
  {
    v10 = -1062600180;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_ddD(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        34,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        v24,
        8,
        -1062600180);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180004af0  mov     [rsp+arg_8], rbx
0x180004af5  push    rbp
0x180004af6  push    rsi
0x180004af7  push    rdi
0x180004af8  push    r12
0x180004afa  push    r13
0x180004afc  push    r14
0x180004afe  push    r15
0x180004b00  sub     rsp, 80h
0x180004b07  mov     rax, cs:__security_cookie
0x180004b0e  xor     rax, rsp
0x180004b11  mov     [rsp+0B8h+var_48], rax
0x180004b16  mov     r14, [rsp+0B8h+arg_20]
0x180004b1e  movzx   r12d, dl
0x180004b22  mov     r15, [rsp+0B8h+arg_28]
0x180004b2a  xor     edx, edx
0x180004b2c  movzx   edi, r8w
0x180004b30  movzx   eax, r9b
0x180004b34  mov     [rsp+0B8h+var_78], al
0x180004b38  mov     rbp, rcx
0x180004b3b  test    r12b, r12b
0x180004b3e  jnz     loc_180004E33
0x180004b44  mov     r13d, 2
0x180004b4a  lea     rsi, WPP_GLOBAL_Control
0x180004b51  test    r14, r14
0x180004b54  jz      loc_180004E41
0x180004b5a  mov     [r14], rdx
0x180004b5d  mov     ebx, edx
0x180004b5f  mov     rcx, cs:WPP_GLOBAL_Control; this
0x180004b66  test    r15, r15
0x180004b69  jz      loc_180004E8A
0x180004b6f  mov     [r15], edx
0x180004b72  test    ebx, ebx
0x180004b74  jns     loc_180004D00
0x180004b7a  jnz     loc_180004CD6
0x180004b80  mov     eax, edi
0x180004b82  mov     [rsp+0B8h+var_74], edx
0x180004b86  mov     [rsp+0B8h+var_70], eax
0x180004b8a  lea     r9, [rsp+0B8h+var_68]; void *
0x180004b8f  mov     [rsp+0B8h+var_68], eax
0x180004b93  xorps   xmm0, xmm0
0x180004b96  lea     rax, [rsp+0B8h+var_74]
0x180004b9b  mov     [rsp+0B8h+var_50], rdx
0x180004ba0  mov     rdx, [rbp+58h]; void *
0x180004ba4  mov     r8d, 24058h; unsigned int
0x180004baa  mov     [rsp+0B8h+var_80], rax; unsigned int *
0x180004baf  lea     rax, [rsp+0B8h+var_50]
0x180004bb4  mov     [rsp+0B8h+var_88], 8; unsigned int
0x180004bbc  mov     [rsp+0B8h+var_90], rax; void *
0x180004bc1  mov     [rsp+0B8h+var_98], 18h; unsigned int
0x180004bc9  movdqu  [rsp+0B8h+var_60], xmm0
0x180004bcf  mov     [rsp+0B8h+var_64], r13d
0x180004bd4  call    ?SaferDeviceIoControl@CMsftDiscRecorder2@@AEAA?BJQEAXKPEAXK1KPEAK@Z; CMsftDiscRecorder2::SaferDeviceIoControl(void * const,ulong,void *,ulong,void *,ulong,ulong *)
0x180004bd9  mov     ebx, eax
0x180004bdb  cmp     eax, 80070001h
0x180004be0  jz      loc_180004D9E
0x180004be6  test    eax, eax
0x180004be8  js      loc_180004EC3
0x180004bee  mov     r9d, [rsp+0B8h+var_74]
0x180004bf3  cmp     r9d, 8
0x180004bf7  jnz     loc_180004F0D
0x180004bfd  test    eax, eax
0x180004bff  jnz     loc_180004CD6
0x180004c05  movzx   eax, byte ptr [rsp+0B8h+var_50+1]
0x180004c0a  movzx   esi, byte ptr [rsp+0B8h+var_50]
0x180004c0f  shl     esi, 8
0x180004c12  or      esi, eax
0x180004c14  movzx   eax, byte ptr [rsp+0B8h+var_50+2]
0x180004c19  shl     esi, 8
0x180004c1c  or      esi, eax
0x180004c1e  movzx   eax, byte ptr [rsp+0B8h+var_50+3]
0x180004c23  shl     esi, 8
0x180004c26  or      esi, eax
0x180004c28  add     esi, 4
0x180004c2b  cmp     esi, r9d
0x180004c2e  jz      loc_180004DEA
0x180004c34  mov     ecx, esi; cb
0x180004c36  mov     ebx, esi
0x180004c38  call    cs:__imp_CoTaskMemAlloc
0x180004c3e  mov     rdi, rax
0x180004c41  test    rax, rax
0x180004c44  jz      loc_180004F69
0x180004c4a  mov     r8d, ebx; Size
0x180004c4d  mov     [rsp+0B8h+var_74], 0
0x180004c55  xor     edx, edx; Val
0x180004c57  mov     rcx, rax; void *
0x180004c5a  call    memset_0
0x180004c5f  mov     eax, [rsp+0B8h+var_70]
0x180004c63  lea     r9, [rsp+0B8h+var_68]; void *
0x180004c68  mov     rdx, [rbp+58h]; void *
0x180004c6c  xorps   xmm0, xmm0
0x180004c6f  mov     [rsp+0B8h+var_68], eax
0x180004c73  mov     r8d, 24058h; unsigned int
0x180004c79  lea     rax, [rsp+0B8h+var_74]
0x180004c7e  mov     [rsp+0B8h+var_64], r13d
0x180004c83  mov     [rsp+0B8h+var_80], rax; unsigned int *
0x180004c88  mov     [rsp+0B8h+var_88], esi; unsigned int
0x180004c8c  mov     [rsp+0B8h+var_90], rdi; void *
0x180004c91  mov     [rsp+0B8h+var_98], 18h; unsigned int
0x180004c99  movdqu  [rsp+0B8h+var_60], xmm0
0x180004c9f  call    ?SaferDeviceIoControl@CMsftDiscRecorder2@@AEAA?BJQEAXKPEAXK1KPEAK@Z; CMsftDiscRecorder2::SaferDeviceIoControl(void * const,ulong,void *,ulong,void *,ulong,ulong *)
0x180004ca4  mov     ebx, eax
0x180004ca6  cmp     eax, 80070001h
0x180004cab  jnz     loc_180004D59
0x180004cb1  mov     ebx, 0C0AA020Ch
0x180004cb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180004cbd  lea     rax, WPP_GLOBAL_Control
0x180004cc4  cmp     rcx, rax
0x180004cc7  jnz     loc_180004FB7
0x180004ccd  mov     rcx, rdi; pv
0x180004cd0  call    cs:__imp_CoTaskMemFree
0x180004cd6  mov     eax, ebx
0x180004cd8  mov     rcx, [rsp+0B8h+var_48]
0x180004cdd  xor     rcx, rsp; StackCookie
0x180004ce0  call    __security_check_cookie
0x180004ce5  mov     rbx, [rsp+0B8h+arg_8]
0x180004ced  add     rsp, 80h
0x180004cf4  pop     r15
0x180004cf6  pop     r14
0x180004cf8  pop     r13
0x180004cfa  pop     r12
0x180004cfc  pop     rdi
0x180004cfd  pop     rsi
0x180004cfe  pop     rbp
0x180004cff  retn
0x180004d00  mov     r9d, [rbp+0F0h]
0x180004d07  test    r9b, 2
0x180004d0b  jnz     loc_180004B80
0x180004d11  mov     ebx, 80004005h
0x180004d16  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d1d  cmp     rcx, rsi
0x180004d20  jz      short loc_180004D52
0x180004d22  test    byte ptr [rcx+0BCh], 4
0x180004d29  jz      short loc_180004D52
0x180004d2b  cmp     byte ptr [rcx+0B9h], 3
0x180004d32  jb      short loc_180004D52
0x180004d34  mov     rcx, [rcx+0B0h]
0x180004d3b  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180004d42  mov     edx, 1Fh
0x180004d47  mov     [rsp+0B8h+var_98], ebx
0x180004d4b  call    WPP_SF_Dd
0x180004d50  xor     edx, edx
0x180004d52  test    ebx, ebx
0x180004d54  jmp     loc_180004B7A
0x180004d59  test    ebx, ebx
0x180004d5b  js      loc_180004FEE
0x180004d61  mov     r9d, [rsp+0B8h+var_74]
0x180004d66  cmp     r9d, esi
0x180004d69  jnz     loc_180005043
0x180004d6f  add     esi, 0FFFFFFF8h
0x180004d72  lea     rdx, [rdi+8]; Src
0x180004d76  mov     r8d, esi; Size
0x180004d79  mov     rcx, rdi; void *
0x180004d7c  call    memmove_0
0x180004d81  test    r12b, r12b
0x180004d84  jnz     short loc_180004D91
0x180004d86  cmp     [rsp+0B8h+var_78], r12b
0x180004d8b  jnz     loc_1800050A2
0x180004d91  mov     [r14], rdi
0x180004d94  xor     ebx, ebx
0x180004d96  mov     [r15], esi
0x180004d99  jmp     loc_180004CD6
0x180004d9e  mov     ebx, 0C0AA020Ch
0x180004da3  mov     rcx, cs:WPP_GLOBAL_Control
0x180004daa  cmp     rcx, rsi
0x180004dad  jz      loc_180004CD6
0x180004db3  test    byte ptr [rcx+0BCh], 4
0x180004dba  jz      loc_180004CD6
0x180004dc0  cmp     byte ptr [rcx+0B9h], 3
0x180004dc7  jb      loc_180004CD6
0x180004dcd  mov     rcx, [rcx+0B0h]
0x180004dd4  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180004ddb  mov     edx, 20h ; ' '
0x180004de0  call    WPP_SF_
0x180004de5  jmp     loc_180004CD6
0x180004dea  mov     rcx, cs:WPP_GLOBAL_Control
0x180004df1  lea     rax, WPP_GLOBAL_Control
0x180004df8  cmp     rcx, rax
0x180004dfb  jnz     short loc_180004E07
0x180004dfd  mov     ebx, 0C0AA020Ah
0x180004e02  jmp     loc_180004CD6
0x180004e07  test    byte ptr [rcx+0BCh], 4
0x180004e0e  jz      short loc_180004DFD
0x180004e10  cmp     byte ptr [rcx+0B9h], 3
0x180004e17  jb      short loc_180004DFD
0x180004e19  mov     rcx, [rcx+0B0h]
0x180004e20  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180004e27  mov     edx, 23h ; '#'
0x180004e2c  call    WPP_SF_
0x180004e31  jmp     short loc_180004DFD
0x180004e33  test    al, al
0x180004e35  mov     r13d, edx
0x180004e38  setnz   r13b
0x180004e3c  jmp     loc_180004B4A
0x180004e41  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e48  cmp     rcx, rsi
0x180004e4b  jz      short loc_180004E80
0x180004e4d  test    byte ptr [rcx+0BCh], 4
0x180004e54  jz      short loc_180004E80
0x180004e56  cmp     byte ptr [rcx+0B9h], 3
0x180004e5d  jb      short loc_180004E80
0x180004e5f  mov     rcx, [rcx+0B0h]
0x180004e66  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180004e6d  mov     edx, 1Dh
0x180004e72  call    WPP_SF_
0x180004e77  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e7e  xor     edx, edx
0x180004e80  mov     ebx, 80004003h
0x180004e85  jmp     loc_180004B66
0x180004e8a  cmp     rcx, rsi
0x180004e8d  jz      short loc_180004EB9
0x180004e8f  test    byte ptr [rcx+0BCh], 4
0x180004e96  jz      short loc_180004EB9
0x180004e98  cmp     byte ptr [rcx+0B9h], 3
0x180004e9f  jb      short loc_180004EB9
0x180004ea1  mov     rcx, [rcx+0B0h]
0x180004ea8  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180004eaf  mov     edx, 1Eh
0x180004eb4  call    WPP_SF_
0x180004eb9  mov     ebx, 80004003h
0x180004ebe  jmp     loc_180004CD6
0x180004ec3  mov     rcx, cs:WPP_GLOBAL_Control
0x180004eca  cmp     rcx, rsi
0x180004ecd  jz      loc_180004CD6
0x180004ed3  test    byte ptr [rcx+0BCh], 4
0x180004eda  jz      loc_180004CD6
0x180004ee0  cmp     byte ptr [rcx+0B9h], 3
0x180004ee7  jb      loc_180004CD6
0x180004eed  mov     rcx, [rcx+0B0h]
0x180004ef4  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180004efb  mov     edx, 21h ; '!'
0x180004f00  mov     r9d, eax
0x180004f03  call    WPP_SF_d
0x180004f08  jmp     loc_180004CD6
0x180004f0d  mov     ebx, 0C0AA020Ch
0x180004f12  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f19  cmp     rcx, rsi
0x180004f1c  jz      loc_180004CD6
0x180004f22  test    byte ptr [rcx+0BCh], 4
0x180004f29  jz      loc_180004CD6
0x180004f2f  cmp     byte ptr [rcx+0B9h], 3
0x180004f36  jb      loc_180004CD6
0x180004f3c  mov     rcx, [rcx+0B0h]
0x180004f43  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180004f4a  mov     edx, 22h ; '"'
0x180004f4f  mov     dword ptr [rsp+0B8h+var_90], 0C0AA020Ch
0x180004f57  mov     [rsp+0B8h+var_98], 8
0x180004f5f  call    WPP_SF_ddD
0x180004f64  jmp     loc_180004CD6
0x180004f69  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f70  lea     rax, WPP_GLOBAL_Control
0x180004f77  cmp     rcx, rax
0x180004f7a  jz      short loc_180004FAD
0x180004f7c  test    byte ptr [rcx+0BCh], 4
0x180004f83  jz      short loc_180004FAD
0x180004f85  cmp     byte ptr [rcx+0B9h], 3
0x180004f8c  jb      short loc_180004FAD
0x180004f8e  mov     rcx, [rcx+0B0h]
0x180004f95  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180004f9c  mov     edx, 24h ; '$'
0x180004fa1  mov     [rsp+0B8h+var_98], esi
0x180004fa5  mov     r9d, esi
0x180004fa8  call    WPP_SF_Dd
0x180004fad  mov     ebx, 8007000Eh
0x180004fb2  jmp     loc_180004CD6
0x180004fb7  test    byte ptr [rcx+0BCh], 4
0x180004fbe  jz      loc_180004CCD
0x180004fc4  cmp     byte ptr [rcx+0B9h], 3
0x180004fcb  jb      loc_180004CCD
0x180004fd1  mov     rcx, [rcx+0B0h]
0x180004fd8  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180004fdf  mov     edx, 25h ; '%'
0x180004fe4  call    WPP_SF_
0x180004fe9  jmp     loc_180004CCD
0x180004fee  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ff5  lea     rax, WPP_GLOBAL_Control
0x180004ffc  cmp     rcx, rax
0x180004fff  jz      loc_180004CCD
0x180005005  test    byte ptr [rcx+0BCh], 4
0x18000500c  jz      loc_180004CCD
0x180005012  cmp     byte ptr [rcx+0B9h], 3
0x180005019  jb      loc_180004CCD
0x18000501f  mov     rcx, [rcx+0B0h]
0x180005026  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18000502d  mov     edx, 26h ; '&'
0x180005032  mov     [rsp+0B8h+var_98], ebx
0x180005036  mov     r9d, esi
0x180005039  call    WPP_SF_Dd
0x18000503e  jmp     loc_180004CCD
0x180005043  mov     ebx, 80004005h
0x180005048  mov     rcx, cs:WPP_GLOBAL_Control
0x18000504f  lea     rax, WPP_GLOBAL_Control
0x180005056  cmp     rcx, rax
0x180005059  jz      loc_180004CCD
0x18000505f  test    byte ptr [rcx+0BCh], 4
0x180005066  jz      loc_180004CCD
0x18000506c  cmp     byte ptr [rcx+0B9h], 3
0x180005073  jb      loc_180004CCD
0x180005079  mov     rcx, [rcx+0B0h]
0x180005080  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
  ... truncated ...
```
