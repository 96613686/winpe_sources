# UpdateDriverFileRefCnt

- ea: `0x18001de10`
- end: `0x18001e31a`
- name: `UpdateDriverFileRefCnt`
- size: `1290`
- prototype: `__int64 __fastcall(struct _INIENVIRONMENT *, struct _INIVERSION *, struct _INIDRIVER *, unsigned __int16 *, unsigned int, int)`
- caller_count: `5`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800685e4`
- `0x18006b71c`
- `0x180078910`
- `0x18007edcc`
- `0x1800be85c`

## callees

- `0x18000e12c`
- `0x18001dd54`
- `0x18001de10`
- `0x18001e320`
- `0x18001e470`
- `0x18001e5b0`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001e0f4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001e0f4`
- `SPOOLSS!DllFreeSplStr` at `0x18001e26e`
- `SPOOLSS!DllFreeSplStr` at `0x18001e2f5`
- `SPOOLSS!DllFreeSplStr` at `0x18001e26e`
- `SPOOLSS!DllFreeSplStr` at `0x18001e2f5`
- `SPOOLSS!DllFreeSplMem` at `0x18001df28`
- `SPOOLSS!DllFreeSplMem` at `0x18001df48`
- `SPOOLSS!DllFreeSplMem` at `0x18001e278`
- `SPOOLSS!DllFreeSplMem` at `0x18001e2b6`
- `SPOOLSS!DllFreeSplMem` at `0x18001e2fe`
- `SPOOLSS!DllFreeSplMem` at `0x18001df28`
- `SPOOLSS!DllFreeSplMem` at `0x18001df48`
- `SPOOLSS!DllFreeSplMem` at `0x18001e278`
- `SPOOLSS!DllFreeSplMem` at `0x18001e2b6`
- `SPOOLSS!DllFreeSplMem` at `0x18001e2fe`
- `SPOOLSS!DllAllocSplMem` at `0x18001e09f`
- `SPOOLSS!DllAllocSplMem` at `0x18001e0bd`
- `SPOOLSS!DllAllocSplMem` at `0x18001e11c`
- `SPOOLSS!DllAllocSplMem` at `0x18001e09f`
- `SPOOLSS!DllAllocSplMem` at `0x18001e0bd`
- `SPOOLSS!DllAllocSplMem` at `0x18001e11c`

## pseudocode

```c
__int64 __fastcall UpdateDriverFileRefCnt(
        struct _INIENVIRONMENT *a1,
        struct _INIVERSION *a2,
        struct _INIDRIVER *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        int a6)
{
  bool v7; // cf
  struct _INIENVIRONMENT *v10; // r15
  struct _DRVREFNODE *v11; // rdi
  const unsigned __int16 *v12; // rsi
  const unsigned __int16 *v13; // r14
  struct _DRVFILE *v14; // r15
  unsigned int v15; // r14d
  struct _DRVREFNODE *v16; // rcx
  char v17; // r14
  __int64 v18; // rdx
  int v19; // eax
  struct _DRVREFNODE *v21; // rsi
  char v22; // r14
  __int64 v23; // rcx
  struct _DRVFILE *i; // rcx
  struct _DRVFILE *v25; // rbx
  unsigned __int16 *v26; // r9
  const unsigned __int16 *v27; // r10
  int v28; // r8d
  unsigned __int16 v29; // cx
  unsigned __int16 v30; // dx
  __int64 v31; // rax
  struct _DRVFILE **v32; // rax
  struct _DRVREFNODE **v33; // rax
  struct _DRVREFNODE **v34; // rbx
  struct _DRVREFCNT *v35; // rax
  struct _DRVREFNODE *v36; // rax
  struct _DRVREFCNT *v37; // rax
  unsigned int v38; // edi
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 *v41; // rdi
  __int64 v42; // rbx
  unsigned int v43; // r14d
  struct _DRVREFNODE *v44; // [rsp+40h] [rbp-10h] BYREF
  struct _DRVFILE *v45; // [rsp+48h] [rbp-8h] BYREF
  int v47; // [rsp+A0h] [rbp+50h] BYREF

  v7 = *((_DWORD *)a3 + 59) < 4u;
  v44 = 0;
  v10 = a1;
  v45 = 0;
  v11 = 0;
  if ( !v7 )
    return 1;
  v12 = (const unsigned __int16 *)*((_QWORD *)a3 + 9);
  v13 = (const unsigned __int16 *)*((_QWORD *)a3 + 4);
  if ( !a6 )
  {
    v47 = 0;
    if ( v13 && *v13 )
    {
      if ( !DuplicateFile(&v45, v13, &v47) )
      {
LABEL_6:
        v14 = v45;
        goto LABEL_7;
      }
      if ( !v47 )
      {
        v36 = (struct _DRVREFNODE *)DllAllocSplMem(16);
        if ( !v36 )
          goto LABEL_6;
        *(_QWORD *)v36 = 0;
        v11 = v36;
        v44 = v36;
        v37 = DecrementFileRefCnt(a1, a2, a3, v13, a4, a5);
        *((_QWORD *)v11 + 1) = v37;
        if ( !v37 )
          goto LABEL_6;
        v10 = a1;
      }
    }
    v38 = a5;
    if ( !InternalDecrement(&v44, &v45, v10, a2, a3, *((const unsigned __int16 **)a3 + 5), a4, a5)
      || !InternalDecrement(&v44, &v45, v10, a2, a3, *((const unsigned __int16 **)a3 + 7), a4, v38)
      || !InternalDecrement(&v44, &v45, v10, a2, a3, *((const unsigned __int16 **)a3 + 6), a4, v38) )
    {
LABEL_77:
      v11 = v44;
      goto LABEL_6;
    }
    while ( v12 && *v12 )
    {
      if ( !InternalDecrement(&v44, &v45, v10, a2, a3, v12, a4, v38) )
        goto LABEL_77;
      v39 = -1;
      do
        ++v39;
      while ( v12[v39] );
      v12 += v39 + 1;
    }
    v11 = v44;
    v14 = v45;
    goto LABEL_15;
  }
  if ( !InternalIncrement(&v44, &v45, a2, *((const unsigned __int16 **)a3 + 4))
    || !InternalIncrement(&v44, &v45, a2, *((const unsigned __int16 **)a3 + 5))
    || !InternalIncrement(&v44, &v45, a2, *((const unsigned __int16 **)a3 + 7))
    || !InternalIncrement(&v44, &v45, a2, *((const unsigned __int16 **)a3 + 6)) )
  {
    v11 = v44;
    goto LABEL_6;
  }
  v11 = v44;
  v14 = v45;
  while ( 2 )
  {
    if ( !v12 || !*v12 )
    {
LABEL_15:
      v15 = 1;
      v21 = v11;
      if ( v11 )
      {
        v22 = a5;
        do
        {
          v23 = *((_QWORD *)v21 + 1);
          if ( v23 && !*(_DWORD *)(v23 + 16) && (v22 & 5) != 0 )
          {
            DllFreeSplStr(*(_QWORD *)(v23 + 8));
            DllFreeSplMem(*((_QWORD *)v21 + 1));
          }
          v11 = *(struct _DRVREFNODE **)v11;
          DllFreeSplMem(v21);
          v21 = v11;
        }
        while ( v11 );
        v15 = 1;
      }
      goto LABEL_21;
    }
    v25 = v14;
LABEL_32:
    if ( v25 )
    {
      if ( !*((_QWORD *)v25 + 1) )
        goto LABEL_39;
      v26 = (unsigned __int16 *)*((_QWORD *)v25 + 1);
      v27 = v12;
      v28 = 0;
      while ( 1 )
      {
        v29 = *v27;
        v30 = *v26;
        if ( *v27 == *v26 )
        {
          if ( !v29 )
            goto LABEL_38;
          goto LABEL_37;
        }
        if ( v29 && v30 )
        {
          if ( v29 > 0x7Fu || v30 > 0x7Fu )
          {
            v28 = 2;
            goto LABEL_37;
          }
          if ( (unsigned __int16)(v29 - 97) <= 0x19u )
            v29 -= 32;
          if ( (unsigned __int16)(v30 - 97) <= 0x19u )
            v30 -= 32;
          if ( v29 == v30 )
            goto LABEL_37;
        }
        v28 = 1;
LABEL_37:
        ++v27;
        ++v26;
        if ( v28 )
        {
LABEL_38:
          if ( v28 != 1 && (v28 != 2 || !lstrcmpiW(v12, *((LPCWSTR *)v25 + 1))) )
            goto LABEL_51;
LABEL_39:
          v25 = *(struct _DRVFILE **)v25;
          goto LABEL_32;
        }
      }
    }
    v32 = (struct _DRVFILE **)DllAllocSplMem(16);
    if ( v32 )
    {
      *v32 = v14;
      v14 = (struct _DRVFILE *)v32;
      v32[1] = (struct _DRVFILE *)v12;
      v33 = (struct _DRVREFNODE **)DllAllocSplMem(16);
      v34 = v33;
      if ( v33 )
      {
        *v33 = v11;
        v11 = (struct _DRVREFNODE *)v33;
        v35 = IncrementFileRefCnt(a2, v12);
        v34[1] = v35;
        if ( v35 )
        {
LABEL_51:
          v31 = -1;
          do
            ++v31;
          while ( v12[v31] );
          v12 += v31 + 1;
          continue;
        }
      }
    }
    break;
  }
LABEL_7:
  v47 = 0;
  v15 = 0;
  v16 = v11;
  if ( v11 )
  {
    v17 = a5;
    do
    {
      v18 = *((_QWORD *)v16 + 1);
      if ( v18 )
      {
        v19 = *(_DWORD *)(v18 + 16);
        if ( a6 )
        {
          *(_DWORD *)(v18 + 16) = v19 - 1;
        }
        else
        {
          *(_DWORD *)(v18 + 16) = v19 + 1;
          v40 = *((_QWORD *)v16 + 1);
          if ( *(_DWORD *)(v40 + 16) == 1 && (v17 & 5) != 0 )
          {
            *(_QWORD *)v40 = *((_QWORD *)a2 + 5);
            *((_QWORD *)a2 + 5) = *((_QWORD *)v16 + 1);
          }
        }
      }
      v11 = *(struct _DRVREFNODE **)v11;
      DllFreeSplMem(v16);
      v16 = v11;
    }
    while ( v11 );
    v15 = v47;
  }
  v41 = (__int64 *)((char *)a2 + 40);
  v42 = *((_QWORD *)a2 + 5);
  if ( v42 )
  {
    v43 = a5;
    do
    {
      if ( *(_DWORD *)(v42 + 16) || !v43 )
      {
        v41 = (__int64 *)v42;
      }
      else
      {
        *v41 = *(_QWORD *)v42;
        DllFreeSplStr(*(_QWORD *)(v42 + 8));
        DllFreeSplMem(v42);
      }
      v42 = *v41;
    }
    while ( *v41 );
    v15 = v47;
  }
LABEL_21:
  for ( i = v14; v14; i = v14 )
  {
    v14 = *(struct _DRVFILE **)v14;
    DllFreeSplMem(i);
  }
  return v15;
}

```

## disassembly

```asm
0x18001de10  mov     [rsp-38h+arg_8], rbx
0x18001de15  mov     [rsp-38h+arg_0], rcx
0x18001de1a  push    rbp
0x18001de1b  push    rsi
0x18001de1c  push    rdi
0x18001de1d  push    r12
0x18001de1f  push    r13
0x18001de21  push    r14
0x18001de23  push    r15
0x18001de25  mov     rbp, rsp
0x18001de28  sub     rsp, 50h
0x18001de2c  xor     eax, eax
0x18001de2e  mov     r12, r9
0x18001de31  cmp     dword ptr [r8+0ECh], 4
0x18001de39  mov     rbx, r8
0x18001de3c  mov     r13, rdx
0x18001de3f  mov     [rbp+var_10], rax
0x18001de43  mov     r15, rcx
0x18001de46  mov     [rbp+var_8], rax
0x18001de4a  mov     edi, eax
0x18001de4c  jnb     loc_18001DEF3
0x18001de52  mov     rsi, [r8+48h]
0x18001de56  mov     r14, [r8+20h]
0x18001de5a  cmp     [rbp+arg_28], eax
0x18001de5d  jnz     short loc_18001DECF
0x18001de5f  mov     [rbp+arg_10], eax
0x18001de62  test    r14, r14
0x18001de65  jz      loc_18001DF71
0x18001de6b  cmp     [r14], ax
0x18001de6f  jz      loc_18001DF71
0x18001de75  lea     r8, [rbp+arg_10]; int *
0x18001de79  mov     rdx, r14; unsigned __int16 *
0x18001de7c  lea     rcx, [rbp+var_8]; struct _DRVFILE **
0x18001de80  call    ?DuplicateFile@@YAHPEAPEAU_DRVFILE@@PEBGPEAH@Z; DuplicateFile(_DRVFILE * *,ushort const *,int *)
0x18001de85  test    eax, eax
0x18001de87  jnz     loc_18001E10E
0x18001de8d  xor     r12d, r12d
0x18001de90  mov     r15, [rbp+var_8]
0x18001de94  mov     [rbp+arg_10], r12d
0x18001de98  mov     r14d, r12d
0x18001de9b  mov     rcx, rdi
0x18001de9e  test    rdi, rdi
0x18001dea1  jz      loc_18001E2CC
0x18001dea7  mov     r14d, [rbp+arg_20]
0x18001deab  mov     rdx, [rcx+8]
0x18001deaf  test    rdx, rdx
0x18001deb2  jz      loc_18001E2B0
0x18001deb8  mov     eax, [rdx+10h]
0x18001debb  cmp     [rbp+arg_28], r12d
0x18001debf  jz      loc_18001E28C
0x18001dec5  dec     eax
0x18001dec7  mov     [rdx+10h], eax
0x18001deca  jmp     loc_18001E2B0
0x18001decf  mov     r9, r14; unsigned __int16 *
0x18001ded2  lea     rdx, [rbp+var_8]; struct _DRVFILE **
0x18001ded6  mov     r8, r13; struct _INIVERSION *
0x18001ded9  lea     rcx, [rbp+var_10]; struct _DRVREFNODE **
0x18001dedd  call    ?InternalIncrement@@YAHPEAPEAU_DRVREFNODE@@PEAPEAU_DRVFILE@@PEAU_INIVERSION@@PEBG@Z; InternalIncrement(_DRVREFNODE * *,_DRVFILE * *,_INIVERSION *,ushort const *)
0x18001dee2  xor     r12d, r12d
0x18001dee5  test    eax, eax
0x18001dee7  jnz     loc_18001DF79
0x18001deed  mov     rdi, [rbp+var_10]
0x18001def1  jmp     short loc_18001DE90
0x18001def3  mov     eax, 1
0x18001def8  jmp     short loc_18001DF59
0x18001defa  mov     r14d, 1
0x18001df00  mov     rsi, rdi
0x18001df03  test    rdi, rdi
0x18001df06  jz      short loc_18001DF3A
0x18001df08  mov     r14d, [rbp+arg_20]
0x18001df0c  mov     rcx, [rsi+8]
0x18001df10  test    rcx, rcx
0x18001df13  jz      short loc_18001DF1F
0x18001df15  cmp     [rcx+10h], r12d
0x18001df19  jz      loc_18001E260
0x18001df1f  mov     rbx, [rdi]
0x18001df22  mov     rcx, rsi
0x18001df25  mov     rdi, rbx
0x18001df28  call    cs:__imp_DllFreeSplMem
0x18001df2e  mov     rsi, rbx
0x18001df31  test    rbx, rbx
0x18001df34  jnz     short loc_18001DF0C
0x18001df36  lea     r14d, [rbx+1]
0x18001df3a  mov     rcx, r15
0x18001df3d  test    r15, r15
0x18001df40  jz      short loc_18001DF56
0x18001df42  mov     rbx, [r15]
0x18001df45  mov     r15, rbx
0x18001df48  call    cs:__imp_DllFreeSplMem
0x18001df4e  mov     rcx, rbx
0x18001df51  test    rbx, rbx
0x18001df54  jnz     short loc_18001DF42
0x18001df56  mov     eax, r14d
0x18001df59  mov     rbx, [rsp+50h+arg_8]
0x18001df61  add     rsp, 50h
0x18001df65  pop     r15
0x18001df67  pop     r14
0x18001df69  pop     r13
0x18001df6b  pop     r12
0x18001df6d  pop     rdi
0x18001df6e  pop     rsi
0x18001df6f  pop     rbp
0x18001df70  retn
0x18001df71  xor     r14d, r14d
0x18001df74  jmp     loc_18001E16A
0x18001df79  mov     r9, [rbx+28h]; unsigned __int16 *
0x18001df7d  lea     rdx, [rbp+var_8]; struct _DRVFILE **
0x18001df81  mov     r8, r13; struct _INIVERSION *
0x18001df84  lea     rcx, [rbp+var_10]; struct _DRVREFNODE **
0x18001df88  call    ?InternalIncrement@@YAHPEAPEAU_DRVREFNODE@@PEAPEAU_DRVFILE@@PEAU_INIVERSION@@PEBG@Z; InternalIncrement(_DRVREFNODE * *,_DRVFILE * *,_INIVERSION *,ushort const *)
0x18001df8d  test    eax, eax
0x18001df8f  jz      loc_18001DEED
0x18001df95  mov     r9, [rbx+38h]; unsigned __int16 *
0x18001df99  lea     rdx, [rbp+var_8]; struct _DRVFILE **
0x18001df9d  mov     r8, r13; struct _INIVERSION *
0x18001dfa0  lea     rcx, [rbp+var_10]; struct _DRVREFNODE **
0x18001dfa4  call    ?InternalIncrement@@YAHPEAPEAU_DRVREFNODE@@PEAPEAU_DRVFILE@@PEAU_INIVERSION@@PEBG@Z; InternalIncrement(_DRVREFNODE * *,_DRVFILE * *,_INIVERSION *,ushort const *)
0x18001dfa9  test    eax, eax
0x18001dfab  jz      loc_18001DEED
0x18001dfb1  mov     r9, [rbx+30h]; unsigned __int16 *
0x18001dfb5  lea     rdx, [rbp+var_8]; struct _DRVFILE **
0x18001dfb9  mov     r8, r13; struct _INIVERSION *
0x18001dfbc  lea     rcx, [rbp+var_10]; struct _DRVREFNODE **
0x18001dfc0  call    ?InternalIncrement@@YAHPEAPEAU_DRVREFNODE@@PEAPEAU_DRVFILE@@PEAU_INIVERSION@@PEBG@Z; InternalIncrement(_DRVREFNODE * *,_DRVFILE * *,_INIVERSION *,ushort const *)
0x18001dfc5  test    eax, eax
0x18001dfc7  jz      loc_18001DEED
0x18001dfcd  mov     rdi, [rbp+var_10]
0x18001dfd1  mov     r15, [rbp+var_8]
0x18001dfd5  test    rsi, rsi
0x18001dfd8  jz      loc_18001DEFA
0x18001dfde  cmp     [rsi], r12w
0x18001dfe2  jz      loc_18001DEFA
0x18001dfe8  mov     rbx, r15
0x18001dfeb  test    rbx, rbx
0x18001dfee  jz      loc_18001E09A
0x18001dff4  mov     r11, [rbx+8]
0x18001dff8  test    r11, r11
0x18001dffb  jz      short loc_18001E02B
0x18001dffd  mov     r9, r11
0x18001e000  mov     r10, rsi
0x18001e003  mov     r8d, r12d
0x18001e006  movzx   ecx, word ptr [r10]
0x18001e00a  movzx   edx, word ptr [r9]
0x18001e00e  cmp     cx, dx
0x18001e011  jnz     short loc_18001E030
0x18001e013  test    cx, cx
0x18001e016  jz      short loc_18001E025
0x18001e018  add     r10, 2
0x18001e01c  add     r9, 2
0x18001e020  test    r8d, r8d
0x18001e023  jz      short loc_18001E006
0x18001e025  cmp     r8d, 1
0x18001e029  jnz     short loc_18001E079
0x18001e02b  mov     rbx, [rbx]
0x18001e02e  jmp     short loc_18001DFEB
0x18001e030  test    cx, cx
0x18001e033  jz      short loc_18001E065
0x18001e035  test    dx, dx
0x18001e038  jz      short loc_18001E065
0x18001e03a  cmp     cx, 7Fh
0x18001e03e  ja      loc_18001E103
0x18001e044  cmp     dx, 7Fh
0x18001e048  ja      loc_18001E103
0x18001e04e  lea     eax, [rcx-61h]
0x18001e051  cmp     ax, 19h
0x18001e055  jbe     short loc_18001E06D
0x18001e057  lea     eax, [rdx-61h]
0x18001e05a  cmp     ax, 19h
0x18001e05e  jbe     short loc_18001E073
0x18001e060  cmp     cx, dx
0x18001e063  jz      short loc_18001E018
0x18001e065  mov     r8d, 1
0x18001e06b  jmp     short loc_18001E018
0x18001e06d  sub     cx, 20h ; ' '
0x18001e071  jmp     short loc_18001E057
0x18001e073  sub     dx, 20h ; ' '
0x18001e077  jmp     short loc_18001E060
0x18001e079  cmp     r8d, 2
0x18001e07d  jz      short loc_18001E0EE
0x18001e07f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e083  inc     rax
0x18001e086  cmp     [rsi+rax*2], r12w
0x18001e08b  jnz     short loc_18001E083
0x18001e08d  lea     rsi, [rsi+rax*2]
0x18001e091  add     rsi, 2
0x18001e095  jmp     loc_18001DFD5
0x18001e09a  mov     ecx, 10h
0x18001e09f  call    cs:__imp_DllAllocSplMem
0x18001e0a5  test    rax, rax
0x18001e0a8  jz      loc_18001DE94
0x18001e0ae  mov     [rax], r15
0x18001e0b1  mov     ecx, 10h
0x18001e0b6  mov     r15, rax
0x18001e0b9  mov     [rax+8], rsi
0x18001e0bd  call    cs:__imp_DllAllocSplMem
0x18001e0c3  mov     rbx, rax
0x18001e0c6  test    rax, rax
0x18001e0c9  jz      loc_18001DE94
0x18001e0cf  mov     [rax], rdi
0x18001e0d2  mov     rdx, rsi; unsigned __int16 *
0x18001e0d5  mov     rcx, r13; struct _INIVERSION *
0x18001e0d8  mov     rdi, rax
0x18001e0db  call    ?IncrementFileRefCnt@@YAPEAU_DRVREFCNT@@PEAU_INIVERSION@@PEBG@Z; IncrementFileRefCnt(_INIVERSION *,ushort const *)
0x18001e0e0  mov     [rbx+8], rax
0x18001e0e4  test    rax, rax
0x18001e0e7  jnz     short loc_18001E07F
0x18001e0e9  jmp     loc_18001DE94
0x18001e0ee  mov     rdx, r11; lpString2
0x18001e0f1  mov     rcx, rsi; lpString1
0x18001e0f4  call    cs:__imp_lstrcmpiW
0x18001e0fa  test    eax, eax
0x18001e0fc  jz      short loc_18001E07F
0x18001e0fe  jmp     loc_18001E02B
0x18001e103  mov     r8d, 2
0x18001e109  jmp     loc_18001E018
0x18001e10e  cmp     [rbp+arg_10], edi
0x18001e111  jnz     loc_18001DF71
0x18001e117  mov     ecx, 10h
0x18001e11c  call    cs:__imp_DllAllocSplMem
0x18001e122  mov     r15, rax
0x18001e125  test    rax, rax
0x18001e128  jz      loc_18001DE8D
0x18001e12e  mov     rcx, [rbp+arg_0]; struct _INIENVIRONMENT *
0x18001e132  mov     r9, r14; unsigned __int16 *
0x18001e135  mov     [rax], rdi
0x18001e138  mov     r8, rbx; struct _INIDRIVER *
0x18001e13b  mov     rdi, rax
0x18001e13e  mov     [rbp+var_10], rax
0x18001e142  mov     eax, [rbp+arg_20]
0x18001e145  mov     rdx, r13; struct _INIVERSION *
0x18001e148  mov     dword ptr [rsp+50h+var_28], eax; unsigned int
0x18001e14c  mov     [rsp+50h+var_30], r12; unsigned __int16 *
0x18001e151  call    ?DecrementFileRefCnt@@YAPEAU_DRVREFCNT@@PEAU_INIENVIRONMENT@@PEAU_INIVERSION@@PEAU_INIDRIVER@@PEBG3K@Z; DecrementFileRefCnt(_INIENVIRONMENT *,_INIVERSION *,_INIDRIVER *,ushort const *,ushort const *,ulong)
0x18001e156  xor     r14d, r14d
0x18001e159  mov     [rdi+8], rax
0x18001e15d  test    rax, rax
0x18001e160  jz      loc_18001DE8D
0x18001e166  mov     r15, [rbp+arg_0]
0x18001e16a  mov     rax, [rbx+28h]
0x18001e16e  lea     rdx, [rbp+var_8]; struct _DRVFILE **
0x18001e172  mov     edi, [rbp+arg_20]
0x18001e175  lea     rcx, [rbp+var_10]; struct _DRVREFNODE **
0x18001e179  mov     [rsp+50h+var_18], edi; unsigned int
0x18001e17d  mov     r9, r13; struct _INIVERSION *
0x18001e180  mov     [rsp+50h+var_20], r12; unsigned __int16 *
0x18001e185  mov     r8, r15; struct _INIENVIRONMENT *
0x18001e188  mov     [rsp+50h+var_28], rax; unsigned __int16 *
0x18001e18d  mov     [rsp+50h+var_30], rbx; struct _INIDRIVER *
0x18001e192  call    ?InternalDecrement@@YAHPEAPEAU_DRVREFNODE@@PEAPEAU_DRVFILE@@PEAU_INIENVIRONMENT@@PEAU_INIVERSION@@PEAU_INIDRIVER@@PEBG5K@Z; InternalDecrement(_DRVREFNODE * *,_DRVFILE * *,_INIENVIRONMENT *,_INIVERSION *,_INIDRIVER *,ushort const *,ushort const *,ulong)
0x18001e197  test    eax, eax
0x18001e199  jz      loc_18001E283
0x18001e19f  mov     rax, [rbx+38h]
0x18001e1a3  lea     rdx, [rbp+var_8]; struct _DRVFILE **
0x18001e1a7  mov     [rsp+50h+var_18], edi; unsigned int
0x18001e1ab  lea     rcx, [rbp+var_10]; struct _DRVREFNODE **
0x18001e1af  mov     [rsp+50h+var_20], r12; unsigned __int16 *
0x18001e1b4  mov     r9, r13; struct _INIVERSION *
0x18001e1b7  mov     [rsp+50h+var_28], rax; unsigned __int16 *
0x18001e1bc  mov     r8, r15; struct _INIENVIRONMENT *
0x18001e1bf  mov     [rsp+50h+var_30], rbx; struct _INIDRIVER *
0x18001e1c4  call    ?InternalDecrement@@YAHPEAPEAU_DRVREFNODE@@PEAPEAU_DRVFILE@@PEAU_INIENVIRONMENT@@PEAU_INIVERSION@@PEAU_INIDRIVER@@PEBG5K@Z; InternalDecrement(_DRVREFNODE * *,_DRVFILE * *,_INIENVIRONMENT *,_INIVERSION *,_INIDRIVER *,ushort const *,ushort const *,ulong)
0x18001e1c9  test    eax, eax
0x18001e1cb  jz      loc_18001E283
0x18001e1d1  mov     rax, [rbx+30h]
0x18001e1d5  lea     rdx, [rbp+var_8]; struct _DRVFILE **
0x18001e1d9  mov     [rsp+50h+var_18], edi; unsigned int
0x18001e1dd  lea     rcx, [rbp+var_10]; struct _DRVREFNODE **
0x18001e1e1  mov     [rsp+50h+var_20], r12; unsigned __int16 *
0x18001e1e6  mov     r9, r13; struct _INIVERSION *
0x18001e1e9  mov     [rsp+50h+var_28], rax; unsigned __int16 *
0x18001e1ee  mov     r8, r15; struct _INIENVIRONMENT *
0x18001e1f1  mov     [rsp+50h+var_30], rbx; struct _INIDRIVER *
0x18001e1f6  call    ?InternalDecrement@@YAHPEAPEAU_DRVREFNODE@@PEAPEAU_DRVFILE@@PEAU_INIENVIRONMENT@@PEAU_INIVERSION@@PEAU_INIDRIVER@@PEBG5K@Z; InternalDecrement(_DRVREFNODE * *,_DRVFILE * *,_INIENVIRONMENT *,_INIVERSION *,_INIDRIVER *,ushort const *,ushort const *,ulong)
0x18001e1fb  test    eax, eax
0x18001e1fd  jz      loc_18001E283
0x18001e203  test    rsi, rsi
0x18001e206  jz      short loc_18001E250
0x18001e208  cmp     [rsi], r14w
0x18001e20c  jz      short loc_18001E250
0x18001e20e  mov     [rsp+50h+var_18], edi; unsigned int
0x18001e212  lea     rdx, [rbp+var_8]; struct _DRVFILE **
0x18001e216  mov     [rsp+50h+var_20], r12; unsigned __int16 *
0x18001e21b  lea     rcx, [rbp+var_10]; struct _DRVREFNODE **
0x18001e21f  mov     [rsp+50h+var_28], rsi; unsigned __int16 *
0x18001e224  mov     r9, r13; struct _INIVERSION *
0x18001e227  mov     r8, r15; struct _INIENVIRONMENT *
0x18001e22a  mov     [rsp+50h+var_30], rbx; struct _INIDRIVER *
0x18001e22f  call    ?InternalDecrement@@YAHPEAPEAU_DRVREFNODE@@PEAPEAU_DRVFILE@@PEAU_INIENVIRONMENT@@PEAU_INIVERSION@@PEAU_INIDRIVER@@PEBG5K@Z; InternalDecrement(_DRVREFNODE * *,_DRVFILE * *,_INIENVIRONMENT *,_INIVERSION *,_INIDRIVER *,ushort const *,ushort const *,ulong)
0x18001e234  test    eax, eax
0x18001e236  jz      short loc_18001E283
0x18001e238  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e23c  inc     rax
0x18001e23f  cmp     [rsi+rax*2], r14w
0x18001e244  jnz     short loc_18001E23C
0x18001e246  lea     rsi, [rsi+rax*2]
0x18001e24a  add     rsi, 2
0x18001e24e  jmp     short loc_18001E203
0x18001e250  mov     rdi, [rbp+var_10]
0x18001e254  xor     r12d, r12d
0x18001e257  mov     r15, [rbp+var_8]
  ... truncated ...
```
