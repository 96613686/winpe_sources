# ClasspTelemetryLogGetPhysicalElementStatusComplete

- ea: `0x140035ce4`
- end: `0x1400360cb`
- name: `ClasspTelemetryLogGetPhysicalElementStatusComplete`
- size: `999`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002e3f0`

## callees

- `0x140001008`
- `0x1400010f8`
- `0x140035ce4`
- `0x14003e430`

## pseudocode

```c
NTSTATUS __fastcall ClasspTelemetryLogGetPhysicalElementStatusComplete(unsigned __int64 a1, __int64 *a2, __int64 a3)
{
  int v3; // r15d
  unsigned int *v5; // r9
  unsigned int v6; // ebx
  int v7; // r11d
  char v8; // di
  unsigned __int64 v9; // r10
  __int64 v10; // rdx
  int v11; // ecx
  unsigned int v12; // edi
  _BYTE *v13; // rdx
  int v14; // ebx
  char v15; // r14
  unsigned __int64 v16; // r11
  __int64 v17; // r10
  int v18; // ecx
  char v19; // cl
  _BYTE *v20; // r11
  _BYTE *v21; // rbx
  unsigned int v22; // r10d
  char v23; // al
  char v24; // al
  NTSTATUS result; // eax
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  char v29; // [rsp+30h] [rbp-D0h] BYREF
  char v30; // [rsp+31h] [rbp-CFh] BYREF
  char v31; // [rsp+32h] [rbp-CEh] BYREF
  char v32; // [rsp+33h] [rbp-CDh] BYREF
  char v33; // [rsp+34h] [rbp-CCh] BYREF
  char v34; // [rsp+35h] [rbp-CBh] BYREF
  char v35; // [rsp+36h] [rbp-CAh] BYREF
  int v36; // [rsp+38h] [rbp-C8h] BYREF
  int v37; // [rsp+3Ch] [rbp-C4h] BYREF
  int v38; // [rsp+40h] [rbp-C0h] BYREF
  int v39; // [rsp+44h] [rbp-BCh] BYREF
  int v40; // [rsp+48h] [rbp-B8h] BYREF
  int v41; // [rsp+4Ch] [rbp-B4h] BYREF
  int v42; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+58h] [rbp-A8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v44; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v45; // [rsp+80h] [rbp-80h]
  __int64 v46; // [rsp+88h] [rbp-78h]
  int *v47; // [rsp+90h] [rbp-70h]
  __int64 v48; // [rsp+98h] [rbp-68h]
  char *v49; // [rsp+A0h] [rbp-60h]
  __int64 v50; // [rsp+A8h] [rbp-58h]
  int *v51; // [rsp+B0h] [rbp-50h]
  __int64 v52; // [rsp+B8h] [rbp-48h]
  char *v53; // [rsp+C0h] [rbp-40h]
  __int64 v54; // [rsp+C8h] [rbp-38h]
  char *v55; // [rsp+D0h] [rbp-30h]
  __int64 v56; // [rsp+D8h] [rbp-28h]
  int *v57; // [rsp+E0h] [rbp-20h]
  __int64 v58; // [rsp+E8h] [rbp-18h]
  int *v59; // [rsp+F0h] [rbp-10h]
  __int64 v60; // [rsp+F8h] [rbp-8h]
  int *v61; // [rsp+100h] [rbp+0h]
  __int64 v62; // [rsp+108h] [rbp+8h]
  int *v63; // [rsp+110h] [rbp+10h]
  __int64 v64; // [rsp+118h] [rbp+18h]
  int *v65; // [rsp+120h] [rbp+20h]
  __int64 v66; // [rsp+128h] [rbp+28h]
  char *v67; // [rsp+130h] [rbp+30h]
  __int64 v68; // [rsp+138h] [rbp+38h]
  char *v69; // [rsp+140h] [rbp+40h]
  __int64 v70; // [rsp+148h] [rbp+48h]
  char *v71; // [rsp+150h] [rbp+50h]
  __int64 v72; // [rsp+158h] [rbp+58h]
  char *v73; // [rsp+160h] [rbp+60h]
  __int64 v74; // [rsp+168h] [rbp+68h]

  v3 = a3;
  v5 = (unsigned int *)a1;
  if ( *(char *)(a1 + 3) >= 0 )
    goto LABEL_63;
  if ( *(_BYTE *)(a1 + 2) != 40 )
  {
    v13 = *(_BYTE **)(a1 + 32);
    LOBYTE(a3) = *(_BYTE *)(a1 + 11);
    goto LABEL_37;
  }
  LOBYTE(a3) = 0;
  if ( !*(_DWORD *)(a1 + 20) )
  {
    v6 = *(_DWORD *)(a1 + 56);
    if ( v6 )
    {
      v7 = 0;
      v8 = 0;
      while ( 1 )
      {
        a1 = v5[v7 + 30];
        if ( (unsigned int)a1 >= 0x80 )
        {
          v9 = v5[4];
          if ( (unsigned int)a1 < (unsigned int)v9 )
            break;
        }
LABEL_13:
        if ( ++v7 >= v6 )
          goto LABEL_18;
      }
      v10 = (unsigned int)a1;
      v11 = *(unsigned int *)((char *)v5 + a1) - 64;
      if ( !v11 )
        goto LABEL_11;
      a1 = (unsigned int)(v11 - 1);
      if ( (_DWORD)a1 )
      {
        if ( (_DWORD)a1 == 1 )
        {
LABEL_11:
          a1 = v10 + 40;
          if ( v10 + 40 <= v9 )
          {
            LOBYTE(a3) = *((_BYTE *)v5 + v10 + 9);
            goto LABEL_18;
          }
        }
      }
      else
      {
        a1 = v10 + 56;
        if ( v10 + 56 <= v9 )
        {
          LOBYTE(a3) = *((_BYTE *)v5 + v10 + 9);
          v8 = 1;
        }
      }
      if ( v8 )
        goto LABEL_18;
      goto LABEL_13;
    }
  }
LABEL_18:
  if ( v5[5] )
  {
    v13 = 0;
    goto LABEL_37;
  }
  v12 = v5[14];
  if ( !v12 )
    goto LABEL_63;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  while ( 1 )
  {
    a1 = v5[v14 + 30];
    if ( (unsigned int)a1 >= 0x80 )
    {
      v16 = v5[4];
      if ( (unsigned int)a1 < (unsigned int)v16 )
        break;
    }
LABEL_32:
    if ( ++v14 >= v12 )
      goto LABEL_37;
  }
  v17 = (unsigned int)a1;
  v18 = *(unsigned int *)((char *)v5 + a1) - 64;
  if ( v18 )
  {
    a1 = (unsigned int)(v18 - 1);
    if ( (_DWORD)a1 )
    {
      if ( (_DWORD)a1 == 1 )
      {
        a1 = v17 + 40;
        if ( v17 + 40 <= v16 )
        {
          v13 = *(_BYTE **)((char *)v5 + v17 + 24);
          goto LABEL_37;
        }
      }
    }
    else
    {
      a1 = v17 + 56;
      if ( v17 + 56 <= v16 )
      {
        v13 = *(_BYTE **)((char *)v5 + v17 + 16);
        v15 = 1;
      }
    }
    goto LABEL_31;
  }
  a1 = v17 + 40;
  if ( v17 + 40 > v16 )
  {
LABEL_31:
    if ( v15 )
      goto LABEL_37;
    goto LABEL_32;
  }
  v13 = *(_BYTE **)((char *)v5 + v17 + 16);
LABEL_37:
  if ( v13 && (_BYTE)a3 )
  {
    v19 = *v13 & 0x7F;
    v20 = (char *)a2 + 30;
    v21 = (char *)a2 + 29;
    if ( (unsigned __int8)(v19 - 114) <= 1u )
    {
      a1 = (unsigned __int64)&v13[(unsigned __int8)a3];
      if ( (unsigned __int64)(v13 + 8) <= a1 )
      {
        if ( a2 != (__int64 *)-29LL )
          *v21 = v13[1] & 0xF;
        if ( a2 != (__int64 *)-30LL )
          *v20 = v13[2];
        if ( a2 != (__int64 *)-31LL )
        {
          v24 = v13[3];
          goto LABEL_62;
        }
      }
    }
    else
    {
      LOBYTE(a1) = v19 - 112;
      if ( (unsigned __int8)a1 <= 1u )
      {
        a1 = (unsigned __int64)&v13[(unsigned __int8)a3];
        if ( (unsigned __int64)(v13 + 8) <= a1 )
        {
          v22 = (unsigned __int8)a3;
          if ( (unsigned int)(unsigned __int8)v13[7] + 8 <= (unsigned __int8)a3 )
            v22 = (unsigned __int8)v13[7] + 8;
          if ( a2 != (__int64 *)-29LL )
            *v21 = v13[2] & 0xF;
          if ( a2 != (__int64 *)-30LL )
          {
            a1 = (unsigned __int64)&v13[v22];
            if ( (unsigned __int64)(v13 + 13) > a1 )
              v23 = 0;
            else
              v23 = v13[12];
            *v20 = v23;
          }
          if ( a2 != (__int64 *)-31LL )
          {
            a1 = (unsigned __int64)&v13[v22];
            if ( (unsigned __int64)(v13 + 14) > a1 )
              v24 = 0;
            else
              v24 = v13[13];
LABEL_62:
            *((_BYTE *)a2 + 31) = v24;
          }
        }
      }
    }
  }
LABEL_63:
  result = dword_14004D060;
  if ( (unsigned int)dword_14004D060 > 5 )
  {
    result = tlgKeywordOn(a1, 0x400000000000LL, a3);
    if ( (_BYTE)result )
    {
      v43 = *a2;
      v45 = &v43;
      v47 = &v36;
      v29 = *(_BYTE *)(v28 + 3);
      v49 = &v29;
      v37 = *((_DWORD *)a2 + 2);
      v51 = &v37;
      v30 = *((_BYTE *)a2 + 12);
      v53 = &v30;
      v31 = *((_BYTE *)a2 + 13);
      v55 = &v31;
      v38 = *((_DWORD *)a2 + 8);
      v57 = &v38;
      v39 = *((_DWORD *)a2 + 9);
      v59 = &v39;
      v40 = *((_DWORD *)a2 + 4);
      v61 = &v40;
      v41 = *((_DWORD *)a2 + 5);
      v63 = &v41;
      v42 = *((_DWORD *)a2 + 6);
      v65 = &v42;
      v32 = *((_BYTE *)a2 + 28);
      v67 = &v32;
      v33 = *((_BYTE *)a2 + 29);
      v69 = &v33;
      v34 = *((_BYTE *)a2 + 30);
      v71 = &v34;
      v35 = *((_BYTE *)a2 + 31);
      v73 = &v35;
      v46 = 8;
      v36 = v3;
      v48 = 4;
      v50 = 1;
      v52 = 4;
      v54 = 1;
      v56 = 1;
      v58 = 4;
      v60 = 4;
      v62 = 4;
      v64 = 4;
      v66 = 4;
      v68 = 1;
      v70 = 1;
      v72 = 1;
      v74 = 1;
      return tlgWriteTransfer_EtwWriteTransfer(v26, (unsigned __int8 *)&dword_140048A4C, v27, v28, 0x11u, &v44);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140035ce4  push    rbp
0x140035ce6  push    rbx
0x140035ce7  push    rsi
0x140035ce8  push    rdi
0x140035ce9  push    r12
0x140035ceb  push    r13
0x140035ced  push    r14
0x140035cef  push    r15
0x140035cf1  lea     rbp, [rsp-88h]
0x140035cf9  sub     rsp, 188h
0x140035d00  mov     rax, cs:__security_cookie
0x140035d07  xor     rax, rsp
0x140035d0a  mov     [rbp+0C0h+var_50], rax
0x140035d0e  xor     r12d, r12d
0x140035d11  mov     r15d, r8d
0x140035d14  mov     rsi, rdx
0x140035d17  mov     r9, rcx
0x140035d1a  mov     r13d, 1
0x140035d20  cmp     [rcx+3], r12b
0x140035d24  jge     loc_140035F1A
0x140035d2a  cmp     byte ptr [rcx+2], 28h ; '('
0x140035d2e  jnz     loc_140035E3B
0x140035d34  mov     r8b, r12b
0x140035d37  cmp     [rcx+14h], r12d
0x140035d3b  jnz     short loc_140035DA8
0x140035d3d  mov     ebx, [rcx+38h]
0x140035d40  test    ebx, ebx
0x140035d42  jz      short loc_140035DA8
0x140035d44  mov     r11d, r12d
0x140035d47  mov     dil, r12b
0x140035d4a  mov     eax, r11d
0x140035d4d  mov     ecx, [r9+rax*4+78h]
0x140035d52  cmp     ecx, 80h
0x140035d58  jb      short loc_140035D86
0x140035d5a  mov     r10d, [r9+10h]
0x140035d5e  cmp     ecx, r10d
0x140035d61  jnb     short loc_140035D86
0x140035d63  mov     edx, ecx
0x140035d65  mov     ecx, [rcx+r9]
0x140035d69  sub     ecx, 40h ; '@'
0x140035d6c  jz      short loc_140035D78
0x140035d6e  sub     ecx, r13d
0x140035d71  jz      short loc_140035D90
0x140035d73  cmp     ecx, r13d
0x140035d76  jnz     short loc_140035D81
0x140035d78  lea     rcx, [rdx+28h]
0x140035d7c  cmp     rcx, r10
0x140035d7f  jbe     short loc_140035DA3
0x140035d81  test    dil, dil
0x140035d84  jnz     short loc_140035DA8
0x140035d86  add     r11d, r13d
0x140035d89  cmp     r11d, ebx
0x140035d8c  jb      short loc_140035D4A
0x140035d8e  jmp     short loc_140035DA8
0x140035d90  lea     rcx, [rdx+38h]
0x140035d94  cmp     rcx, r10
0x140035d97  ja      short loc_140035D81
0x140035d99  mov     r8b, [rdx+r9+9]
0x140035d9e  mov     dil, r13b
0x140035da1  jmp     short loc_140035D81
0x140035da3  mov     r8b, [rdx+r9+9]
0x140035da8  cmp     [r9+14h], r12d
0x140035dac  jnz     loc_140035E36
0x140035db2  mov     edi, [r9+38h]
0x140035db6  test    edi, edi
0x140035db8  jz      loc_140035F1A
0x140035dbe  mov     rdx, r12
0x140035dc1  mov     ebx, r12d
0x140035dc4  mov     r14b, r12b
0x140035dc7  mov     eax, ebx
0x140035dc9  mov     ecx, [r9+rax*4+78h]
0x140035dce  cmp     ecx, 80h
0x140035dd4  jb      short loc_140035E26
0x140035dd6  mov     r11d, [r9+10h]
0x140035dda  cmp     ecx, r11d
0x140035ddd  jnb     short loc_140035E26
0x140035ddf  mov     r10d, ecx
0x140035de2  mov     ecx, [rcx+r9]
0x140035de6  sub     ecx, 40h ; '@'
0x140035de9  jz      short loc_140035E18
0x140035deb  sub     ecx, r13d
0x140035dee  jz      short loc_140035E05
0x140035df0  cmp     ecx, r13d
0x140035df3  jnz     short loc_140035E21
0x140035df5  lea     rcx, [r10+28h]
0x140035df9  cmp     rcx, r11
0x140035dfc  ja      short loc_140035E21
0x140035dfe  mov     rdx, [r10+r9+18h]
0x140035e03  jmp     short loc_140035E43
0x140035e05  lea     rcx, [r10+38h]
0x140035e09  cmp     rcx, r11
0x140035e0c  ja      short loc_140035E21
0x140035e0e  mov     rdx, [r10+r9+10h]
0x140035e13  mov     r14b, r13b
0x140035e16  jmp     short loc_140035E21
0x140035e18  lea     rcx, [r10+28h]
0x140035e1c  cmp     rcx, r11
0x140035e1f  jbe     short loc_140035E2F
0x140035e21  test    r14b, r14b
0x140035e24  jnz     short loc_140035E43
0x140035e26  add     ebx, r13d
0x140035e29  cmp     ebx, edi
0x140035e2b  jb      short loc_140035DC7
0x140035e2d  jmp     short loc_140035E43
0x140035e2f  mov     rdx, [r10+r9+10h]
0x140035e34  jmp     short loc_140035E43
0x140035e36  mov     rdx, r12
0x140035e39  jmp     short loc_140035E43
0x140035e3b  mov     rdx, [rcx+20h]
0x140035e3f  mov     r8b, [rcx+0Bh]
0x140035e43  test    rdx, rdx
0x140035e46  jz      loc_140035F1A
0x140035e4c  test    r8b, r8b
0x140035e4f  jz      loc_140035F1A
0x140035e55  mov     cl, [rdx]
0x140035e57  lea     rdi, [rsi+1Fh]
0x140035e5b  and     cl, 7Fh
0x140035e5e  lea     r11, [rsi+1Eh]
0x140035e62  lea     rbx, [rsi+1Dh]
0x140035e66  lea     eax, [rcx-72h]
0x140035e69  cmp     al, r13b
0x140035e6c  jbe     short loc_140035EE9
0x140035e6e  sub     cl, 70h ; 'p'
0x140035e71  cmp     cl, r13b
0x140035e74  ja      loc_140035F1A
0x140035e7a  movzx   ecx, r8b
0x140035e7e  lea     rax, [rdx+8]
0x140035e82  add     rcx, rdx
0x140035e85  cmp     rax, rcx
0x140035e88  ja      loc_140035F1A
0x140035e8e  movzx   eax, byte ptr [rdx+7]
0x140035e92  add     eax, 8
0x140035e95  movzx   r10d, r8b
0x140035e99  cmp     eax, r10d
0x140035e9c  cmovbe  r10d, eax
0x140035ea0  test    rbx, rbx
0x140035ea3  jz      short loc_140035EAC
0x140035ea5  mov     al, [rdx+2]
0x140035ea8  and     al, 0Fh
0x140035eaa  mov     [rbx], al
0x140035eac  test    r11, r11
0x140035eaf  jz      short loc_140035ECB
0x140035eb1  mov     ecx, r10d
0x140035eb4  lea     rax, [rdx+0Dh]
0x140035eb8  add     rcx, rdx
0x140035ebb  cmp     rax, rcx
0x140035ebe  ja      short loc_140035EC5
0x140035ec0  mov     al, [rdx+0Ch]
0x140035ec3  jmp     short loc_140035EC8
0x140035ec5  mov     al, r12b
0x140035ec8  mov     [r11], al
0x140035ecb  test    rdi, rdi
0x140035ece  jz      short loc_140035F1A
0x140035ed0  mov     ecx, r10d
0x140035ed3  lea     rax, [rdx+0Eh]
0x140035ed7  add     rcx, rdx
0x140035eda  cmp     rax, rcx
0x140035edd  ja      short loc_140035EE4
0x140035edf  mov     al, [rdx+0Dh]
0x140035ee2  jmp     short loc_140035F18
0x140035ee4  mov     al, r12b
0x140035ee7  jmp     short loc_140035F18
0x140035ee9  movzx   ecx, r8b
0x140035eed  lea     rax, [rdx+8]
0x140035ef1  add     rcx, rdx
0x140035ef4  cmp     rax, rcx
0x140035ef7  ja      short loc_140035F1A
0x140035ef9  test    rbx, rbx
0x140035efc  jz      short loc_140035F05
0x140035efe  mov     al, [rdx+1]
0x140035f01  and     al, 0Fh
0x140035f03  mov     [rbx], al
0x140035f05  test    r11, r11
0x140035f08  jz      short loc_140035F10
0x140035f0a  mov     al, [rdx+2]
0x140035f0d  mov     [r11], al
0x140035f10  test    rdi, rdi
0x140035f13  jz      short loc_140035F1A
0x140035f15  mov     al, [rdx+3]
0x140035f18  mov     [rdi], al
0x140035f1a  mov     eax, cs:dword_14004D060
0x140035f20  cmp     eax, 5
0x140035f23  jbe     loc_1400360AA
0x140035f29  mov     rdx, 400000000000h
0x140035f33  call    _tlgKeywordOn
0x140035f38  test    al, al
0x140035f3a  jz      loc_1400360AA
0x140035f40  mov     rax, [rsi]
0x140035f43  lea     rdx, dword_140048A4C; int
0x140035f4a  mov     [rsp+1C0h+var_168], rax
0x140035f4f  lea     rax, [rsp+1C0h+var_168]
0x140035f54  mov     [rbp+0C0h+var_140], rax
0x140035f58  lea     rax, [rsp+1C0h+var_188]
0x140035f5d  mov     [rbp+0C0h+var_130], rax
0x140035f61  mov     al, [r9+3]
0x140035f65  mov     [rsp+1C0h+var_190], al
0x140035f69  lea     rax, [rsp+1C0h+var_190]
0x140035f6e  mov     [rbp+0C0h+var_120], rax
0x140035f72  mov     eax, [rsi+8]
0x140035f75  mov     [rsp+1C0h+var_184], eax
0x140035f79  lea     rax, [rsp+1C0h+var_184]
0x140035f7e  mov     [rbp+0C0h+var_110], rax
0x140035f82  mov     al, [rsi+0Ch]
0x140035f85  mov     [rsp+1C0h+var_18F], al
0x140035f89  lea     rax, [rsp+1C0h+var_18F]
0x140035f8e  mov     [rbp+0C0h+var_100], rax
0x140035f92  mov     al, [rsi+0Dh]
0x140035f95  mov     [rsp+1C0h+var_18E], al
0x140035f99  lea     rax, [rsp+1C0h+var_18E]
0x140035f9e  mov     [rbp+0C0h+var_F0], rax
0x140035fa2  mov     eax, [rsi+20h]
0x140035fa5  mov     [rsp+1C0h+var_180], eax
0x140035fa9  lea     rax, [rsp+1C0h+var_180]
0x140035fae  mov     [rbp+0C0h+var_E0], rax
0x140035fb2  mov     eax, [rsi+24h]
0x140035fb5  mov     [rsp+1C0h+var_17C], eax
0x140035fb9  lea     rax, [rsp+1C0h+var_17C]
0x140035fbe  mov     [rbp+0C0h+var_D0], rax
0x140035fc2  mov     eax, [rsi+10h]
0x140035fc5  mov     [rsp+1C0h+var_178], eax
0x140035fc9  lea     rax, [rsp+1C0h+var_178]
0x140035fce  mov     [rbp+0C0h+var_C0], rax
0x140035fd2  mov     eax, [rsi+14h]
0x140035fd5  mov     [rsp+1C0h+var_174], eax
0x140035fd9  lea     rax, [rsp+1C0h+var_174]
0x140035fde  mov     [rbp+0C0h+var_B0], rax
0x140035fe2  mov     eax, [rsi+18h]
0x140035fe5  mov     [rsp+1C0h+var_170], eax
0x140035fe9  lea     rax, [rsp+1C0h+var_170]
0x140035fee  mov     [rbp+0C0h+var_A0], rax
0x140035ff2  mov     al, [rsi+1Ch]
0x140035ff5  mov     [rsp+1C0h+var_18D], al
0x140035ff9  lea     rax, [rsp+1C0h+var_18D]
0x140035ffe  mov     [rbp+0C0h+var_90], rax
0x140036002  mov     al, [rsi+1Dh]
0x140036005  mov     [rsp+1C0h+var_18C], al
0x140036009  lea     rax, [rsp+1C0h+var_18C]
0x14003600e  mov     [rbp+0C0h+var_80], rax
0x140036012  mov     al, [rsi+1Eh]
0x140036015  mov     [rsp+1C0h+var_18B], al
0x140036019  lea     rax, [rsp+1C0h+var_18B]
0x14003601e  mov     [rbp+0C0h+var_70], rax
0x140036022  mov     al, [rsi+1Fh]
0x140036025  mov     [rsp+1C0h+var_18A], al
0x140036029  lea     rax, [rsp+1C0h+var_18A]
0x14003602e  mov     [rbp+0C0h+var_60], rax
0x140036032  lea     rax, [rsp+1C0h+var_160]
0x140036037  mov     [rsp+1C0h+var_198], rax; __int64
0x14003603c  mov     [rsp+1C0h+var_1A0], 11h; ULONG
0x140036044  mov     [rbp+0C0h+var_138], 8
0x14003604c  mov     [rsp+1C0h+var_188], r15d
0x140036051  mov     [rbp+0C0h+var_128], 4
0x140036059  mov     [rbp+0C0h+var_118], r13
0x14003605d  mov     [rbp+0C0h+var_108], 4
0x140036065  mov     [rbp+0C0h+var_F8], r13
0x140036069  mov     [rbp+0C0h+var_E8], r13
0x14003606d  mov     [rbp+0C0h+var_D8], 4
0x140036075  mov     [rbp+0C0h+var_C8], 4
0x14003607d  mov     [rbp+0C0h+var_B8], 4
0x140036085  mov     [rbp+0C0h+var_A8], 4
0x14003608d  mov     [rbp+0C0h+var_98], 4
0x140036095  mov     [rbp+0C0h+var_88], r13
0x140036099  mov     [rbp+0C0h+var_78], r13
0x14003609d  mov     [rbp+0C0h+var_68], r13
0x1400360a1  mov     [rbp+0C0h+var_58], r13
0x1400360a5  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400360aa  mov     rcx, [rbp+0C0h+var_50]
0x1400360ae  xor     rcx, rsp; StackCookie
0x1400360b1  call    __security_check_cookie
0x1400360b6  add     rsp, 188h
0x1400360bd  pop     r15
0x1400360bf  pop     r14
0x1400360c1  pop     r13
0x1400360c3  pop     r12
0x1400360c5  pop     rdi
0x1400360c6  pop     rsi
0x1400360c7  pop     rbx
0x1400360c8  pop     rbp
0x1400360c9  retn
```
