# KerbMakeSignatureToken(_KERB_KERNEL_CONTEXT *,ulong,_SecBuffer *,ulong,uchar,unsigned __int64,ulong,_KERB_GSS_SIGNATURE * *,unsigned __int64 *)

- ea: `0x140027324`
- end: `0x140027664`
- name: `?KerbMakeSignatureToken@@YAJPEAU_KERB_KERNEL_CONTEXT@@KPEAU_SecBuffer@@KE_KKPEAPEAU_KERB_GSS_SIGNATURE@@PEA_K@Z`
- size: `832`
- prototype: `__int64 __fastcall(struct _KERB_KERNEL_CONTEXT *, unsigned int, struct _SecBuffer *, unsigned int, char, char, unsigned int, struct _KERB_GSS_SIGNATURE **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140026f70`
- `0x1400276c0`

## callees

- `0x1400084c4`
- `0x140008584`
- `0x140027324`
- `0x14002ddb8`

## pseudocode

```c
__int64 __fastcall KerbMakeSignatureToken(
        struct _KERB_KERNEL_CONTEXT *a1,
        int a2,
        struct _SecBuffer *a3,
        int a4,
        char a5,
        char a6,
        unsigned int a7,
        struct _KERB_GSS_SIGNATURE **a8,
        unsigned __int64 *a9)
{
  bool v9; // zf
  char v11; // si
  int v14; // edx
  __int16 v15; // r8
  unsigned int v16; // eax
  unsigned int v17; // r10d
  int v18; // ecx
  unsigned __int8 *pvBuffer; // rbx
  struct gss_OID_desc_struct *v20; // r11
  int v21; // edi
  int v22; // r9d
  int v23; // r10d
  struct gss_OID_desc_struct *v24; // r11
  unsigned int v25; // r15d
  unsigned __int8 *v26; // rbx
  int v27; // ecx
  int v28; // eax
  char *v29; // rdx
  int v30; // ecx
  __int64 v31; // rcx
  struct _KERB_GSS_SIGNATURE **v32; // rax
  unsigned int v34; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int8 *v35; // [rsp+60h] [rbp+18h] BYREF

  v9 = (*((_DWORD *)a1 + 38) & 0x600) == 0;
  v11 = a5;
  v34 = 0;
  if ( !v9 || !a5 )
    a4 = 0;
  v14 = *((_DWORD *)a1 + 28);
  v15 = a7;
  v16 = v14 - 17;
  if ( a5 )
  {
    if ( v16 > 1 )
    {
      v17 = a4 + 30;
      goto LABEL_12;
    }
    v18 = 26;
    if ( a2 != -2147483647 )
      v18 = a7 + 58;
  }
  else
  {
    v18 = 26;
    if ( v16 > 1 )
      v18 = 22;
  }
  v17 = v18 + a4;
LABEL_12:
  pvBuffer = (unsigned __int8 *)a3->pvBuffer;
  v35 = pvBuffer;
  if ( (unsigned int)(v14 - 17) <= 1 )
  {
    if ( a2 == -2147483647 && !a5 )
      return (unsigned int)-1073741811;
    v25 = v17 - a4 + 2;
    if ( a3->cbBuffer < v25 )
      return (unsigned int)-1073741789;
    v21 = 0;
    *pvBuffer = (a5 != 0) + 4;
    pvBuffer[1] = 4;
    v26 = pvBuffer + 2;
    *v26 = 0;
    if ( v11 )
    {
      v26[1] = -1;
      v26[2] = HIBYTE(v15);
      v26[3] = v15;
      *((_WORD *)v26 + 2) = 0;
    }
    else
    {
      *(_DWORD *)(v26 + 1) = -1;
      v26[5] = -1;
    }
    if ( (*((_DWORD *)a1 + 39) & 4) != 0 )
      *v26 |= 1u;
    if ( (*((_DWORD *)a1 + 39) & 0x400) != 0 )
      *v26 |= 4u;
    goto LABEL_52;
  }
  v20 = (struct gss_OID_desc_struct *)&unk_140018A40;
  if ( (*((_DWORD *)a1 + 39) & 0x10) == 0 )
    v20 = (struct gss_OID_desc_struct *)&unk_140018A10;
  v21 = g_token_size(v20, v17, &v34);
  if ( v21 >= 0 )
  {
    v25 = v34 - v22;
    if ( a3->cbBuffer < v34 - v22 )
      return (unsigned int)-1073741789;
    g_make_token_header(v24, v23, &v35, v11 != 0 ? 513 : 257);
    v26 = v35;
    v35[1] = 0;
    v27 = *((_DWORD *)a1 + 28);
    if ( (unsigned int)(v27 - 1) > 2 && v27 != -132 )
    {
      *v26 = 17;
      if ( v11 )
        *((_WORD *)v26 + 1) = 16;
      if ( a2 == -2147483647 )
      {
        if ( !v11 )
          return (unsigned int)-1073741811;
        *((_WORD *)v26 + 1) = -1;
        goto LABEL_37;
      }
LABEL_36:
      if ( !v11 )
      {
        *(_DWORD *)(v26 + 2) = -1;
        goto LABEL_41;
      }
LABEL_37:
      *((_WORD *)v26 + 2) = -1;
LABEL_41:
      *(_DWORD *)(v26 + 10) = -((*((_BYTE *)a1 + 156) & 4) != 0);
LABEL_52:
      v28 = *((_DWORD *)a1 + 38);
      if ( (v28 & 0x400) != 0 || (v29 = (char *)a1 + 136, (v28 & 0x1000C) == 0x10000) )
        v29 = &a6;
      v30 = *((_DWORD *)a1 + 28);
      if ( (unsigned int)(v30 - 17) <= 1 )
      {
        v31 = HIDWORD(*(_QWORD *)v29);
        v26[6] = HIBYTE(*(_QWORD *)v29);
        v26[7] = BYTE2(v31);
        v26[8] = BYTE1(v31);
        v26[9] = v31;
        v26[10] = v29[3];
        v26[11] = v29[2];
        v26[12] = v29[1];
        v26[13] = *v29;
      }
      else if ( (unsigned int)(v30 - 1) <= 2 || v30 == -132 )
      {
        v26[9] = v29[3];
        v26[8] = v29[2];
        v26[7] = v29[1];
        v26[6] = *v29;
      }
      else
      {
        v26[6] = v29[3];
        v26[7] = v29[2];
        v26[8] = v29[1];
        v26[9] = *v29;
      }
      ++*(_QWORD *)v29;
      *a9 = *(_QWORD *)(v26 + 6);
      if ( v11 && (unsigned int)(*((_DWORD *)a1 + 28) - 17) > 1 )
        CDGenerateRandomBits(v26 + 22, 8);
      v32 = a8;
      a3->cbBuffer = v25;
      *v32 = (struct _KERB_GSS_SIGNATURE *)v26;
      return (unsigned int)v21;
    }
    if ( v11 )
      *((_WORD *)v26 + 1) = 0;
    if ( a2 )
    {
      if ( a2 == 1 )
      {
        *v26 = 1;
        goto LABEL_36;
      }
      if ( a2 != 2 )
      {
        if ( a2 == 3 )
        {
          *v26 = 2;
          goto LABEL_36;
        }
        if ( a2 != -2147483647 || !v11 )
          return (unsigned int)-1073741811;
        *((_WORD *)v26 + 1) = -1;
      }
    }
    *v26 = 0;
    goto LABEL_36;
  }
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x140027324  mov     [rsp+arg_8], rbx
0x140027329  mov     [rsp+arg_18], rbp
0x14002732e  push    rsi
0x14002732f  push    rdi
0x140027330  push    r12
0x140027332  push    r14
0x140027334  push    r15
0x140027336  sub     rsp, 20h
0x14002733a  test    dword ptr [rcx+98h], 600h
0x140027344  mov     r12, r8
0x140027347  mov     sil, [rsp+48h+arg_20]
0x14002734c  mov     ebp, edx
0x14002734e  mov     r14, rcx
0x140027351  mov     [rsp+48h+arg_0], 0
0x140027359  jnz     short loc_140027360
0x14002735b  test    sil, sil
0x14002735e  jnz     short loc_140027363
0x140027360  xor     r9d, r9d
0x140027363  mov     edx, [rcx+70h]
0x140027366  mov     r8d, [rsp+48h+arg_30]
0x14002736e  lea     eax, [rdx-11h]
0x140027371  test    sil, sil
0x140027374  jz      short loc_140027394
0x140027376  cmp     eax, 1
0x140027379  jbe     short loc_140027381
0x14002737b  lea     r10d, [r9+1Eh]
0x14002737f  jmp     short loc_1400273A8
0x140027381  mov     ecx, 1Ah
0x140027386  cmp     ebp, 80000001h
0x14002738c  jz      short loc_1400273A4
0x14002738e  lea     rcx, [r8+3Ah]
0x140027392  jmp     short loc_1400273A4
0x140027394  mov     ecx, 1Ah
0x140027399  cmp     eax, 1
0x14002739c  lea     r10d, [rcx-4]
0x1400273a0  cmova   ecx, r10d
0x1400273a4  lea     r10d, [rcx+r9]
0x1400273a8  mov     rbx, [r12+8]
0x1400273ad  lea     eax, [rdx-11h]
0x1400273b0  mov     [rsp+48h+arg_10], rbx
0x1400273b5  cmp     eax, 1
0x1400273b8  jbe     loc_1400274DF
0x1400273be  mov     eax, [r14+9Ch]
0x1400273c5  lea     r11, unk_140018A40
0x1400273cc  test    al, 10h
0x1400273ce  lea     r8, [rsp+48h+arg_0]; unsigned int *
0x1400273d3  lea     rax, unk_140018A10
0x1400273da  mov     edx, r10d; unsigned int
0x1400273dd  cmovz   r11, rax
0x1400273e1  mov     rcx, r11; struct gss_OID_desc_struct *
0x1400273e4  call    ?g_token_size@@YAJPEAUgss_OID_desc_struct@@IPEAK@Z; g_token_size(gss_OID_desc_struct *,uint,ulong *)
0x1400273e9  mov     edi, eax
0x1400273eb  test    eax, eax
0x1400273ed  js      loc_14002764A
0x1400273f3  mov     r15d, [rsp+48h+arg_0]
0x1400273f8  sub     r15d, r9d
0x1400273fb  cmp     [r12], r15d
0x1400273ff  jnb     short loc_14002740B
0x140027401  mov     edi, 0C0000023h
0x140027406  jmp     loc_14002764A
0x14002740b  mov     al, sil
0x14002740e  lea     r8, [rsp+48h+arg_10]; unsigned __int8 **
0x140027413  neg     al
0x140027415  mov     edx, r10d; int
0x140027418  mov     rcx, r11; struct gss_OID_desc_struct *
0x14002741b  sbb     r9d, r9d
0x14002741e  and     r9d, 100h
0x140027425  add     r9d, 101h; int
0x14002742c  call    ?g_make_token_header@@YAXPEAUgss_OID_desc_struct@@HPEAPEAEH@Z; g_make_token_header(gss_OID_desc_struct *,int,uchar * *,int)
0x140027431  mov     rbx, [rsp+48h+arg_10]
0x140027436  mov     byte ptr [rbx+1], 0
0x14002743a  mov     ecx, [r14+70h]
0x14002743e  lea     eax, [rcx-1]
0x140027441  cmp     eax, 2
0x140027444  jbe     short loc_14002747B
0x140027446  cmp     ecx, 0FFFFFF7Ch
0x14002744c  jz      short loc_14002747B
0x14002744e  mov     byte ptr [rbx], 11h
0x140027451  test    sil, sil
0x140027454  jz      short loc_14002745C
0x140027456  mov     word ptr [rbx+2], 10h
0x14002745c  cmp     ebp, 80000001h
0x140027462  jnz     short loc_1400274AF
0x140027464  test    sil, sil
0x140027467  jnz     short loc_140027473
0x140027469  mov     edi, 0C000000Dh
0x14002746e  jmp     loc_14002764A
0x140027473  mov     word ptr [rbx+2], 0FFFFh
0x140027479  jmp     short loc_1400274B4
0x14002747b  test    sil, sil
0x14002747e  jz      short loc_140027486
0x140027480  mov     word ptr [rbx+2], 0
0x140027486  test    ebp, ebp
0x140027488  jz      short loc_1400274AC
0x14002748a  cmp     ebp, 1
0x14002748d  jz      short loc_1400274C1
0x14002748f  cmp     ebp, 2
0x140027492  jz      short loc_1400274AC
0x140027494  cmp     ebp, 3
0x140027497  jz      short loc_1400274BC
0x140027499  cmp     ebp, 80000001h
0x14002749f  jnz     short loc_140027469
0x1400274a1  test    sil, sil
0x1400274a4  jz      short loc_140027469
0x1400274a6  mov     word ptr [rbx+2], 0FFFFh
0x1400274ac  mov     byte ptr [rbx], 0
0x1400274af  test    sil, sil
0x1400274b2  jz      short loc_1400274C6
0x1400274b4  mov     word ptr [rbx+4], 0FFFFh
0x1400274ba  jmp     short loc_1400274CD
0x1400274bc  mov     byte ptr [rbx], 2
0x1400274bf  jmp     short loc_1400274AF
0x1400274c1  mov     byte ptr [rbx], 1
0x1400274c4  jmp     short loc_1400274AF
0x1400274c6  mov     dword ptr [rbx+2], 0FFFFFFFFh
0x1400274cd  mov     al, [r14+9Ch]
0x1400274d4  and     al, 4
0x1400274d6  neg     al
0x1400274d8  sbb     eax, eax
0x1400274da  mov     [rbx+0Ah], eax
0x1400274dd  jmp     short loc_14002755E
0x1400274df  cmp     ebp, 80000001h
0x1400274e5  jnz     short loc_1400274F0
0x1400274e7  test    sil, sil
0x1400274ea  jz      loc_140027469
0x1400274f0  sub     r10d, r9d
0x1400274f3  lea     r15d, [r10+2]
0x1400274f7  cmp     [r12], r15d
0x1400274fb  jb      loc_140027401
0x140027501  xor     edi, edi
0x140027503  test    sil, sil
0x140027506  setnz   al
0x140027509  add     al, 4
0x14002750b  mov     [rbx], al
0x14002750d  mov     byte ptr [rbx+1], 4
0x140027511  add     rbx, 2
0x140027515  mov     [rbx], dil
0x140027518  test    sil, sil
0x14002751b  jz      short loc_140027536
0x14002751d  mov     byte ptr [rbx+1], 0FFh
0x140027521  mov     eax, r8d
0x140027524  shr     eax, 8
0x140027527  mov     [rbx+2], al
0x14002752a  xor     eax, eax
0x14002752c  mov     [rbx+3], r8b
0x140027530  mov     [rbx+4], ax
0x140027534  jmp     short loc_140027540
0x140027536  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002753a  mov     [rbx+1], eax
0x14002753d  mov     [rbx+5], al
0x140027540  mov     eax, [r14+9Ch]
0x140027547  test    al, 4
0x140027549  jz      short loc_14002754E
0x14002754b  or      byte ptr [rbx], 1
0x14002754e  test    dword ptr [r14+9Ch], 400h
0x140027559  jz      short loc_14002755E
0x14002755b  or      byte ptr [rbx], 4
0x14002755e  mov     eax, [r14+98h]
0x140027565  bt      eax, 0Ah
0x140027569  jb      short loc_14002757E
0x14002756b  and     eax, 1000Ch
0x140027570  lea     rdx, [r14+88h]
0x140027577  cmp     eax, 10000h
0x14002757c  jnz     short loc_140027583
0x14002757e  lea     rdx, [rsp+48h+arg_28]
0x140027583  mov     ecx, [r14+70h]
0x140027587  lea     eax, [rcx-11h]
0x14002758a  cmp     eax, 1
0x14002758d  jbe     short loc_1400275D1
0x14002758f  lea     eax, [rcx-1]
0x140027592  cmp     eax, 2
0x140027595  jbe     short loc_1400275B8
0x140027597  cmp     ecx, 0FFFFFF7Ch
0x14002759d  jz      short loc_1400275B8
0x14002759f  mov     al, [rdx+3]
0x1400275a2  mov     [rbx+6], al
0x1400275a5  mov     al, [rdx+2]
0x1400275a8  mov     [rbx+7], al
0x1400275ab  mov     al, [rdx+1]
0x1400275ae  mov     [rbx+8], al
0x1400275b1  mov     al, [rdx]
0x1400275b3  mov     [rbx+9], al
0x1400275b6  jmp     short loc_14002760A
0x1400275b8  mov     al, [rdx+3]
0x1400275bb  mov     [rbx+9], al
0x1400275be  mov     al, [rdx+2]
0x1400275c1  mov     [rbx+8], al
0x1400275c4  mov     al, [rdx+1]
0x1400275c7  mov     [rbx+7], al
0x1400275ca  mov     al, [rdx]
0x1400275cc  mov     [rbx+6], al
0x1400275cf  jmp     short loc_14002760A
0x1400275d1  mov     rcx, [rdx]
0x1400275d4  shr     rcx, 20h
0x1400275d8  mov     eax, ecx
0x1400275da  shr     eax, 18h
0x1400275dd  mov     [rbx+6], al
0x1400275e0  mov     eax, ecx
0x1400275e2  shr     eax, 10h
0x1400275e5  mov     [rbx+7], al
0x1400275e8  mov     eax, ecx
0x1400275ea  shr     eax, 8
0x1400275ed  mov     [rbx+8], al
0x1400275f0  mov     [rbx+9], cl
0x1400275f3  mov     al, [rdx+3]
0x1400275f6  mov     [rbx+0Ah], al
0x1400275f9  mov     al, [rdx+2]
0x1400275fc  mov     [rbx+0Bh], al
0x1400275ff  mov     al, [rdx+1]
0x140027602  mov     [rbx+0Ch], al
0x140027605  mov     al, [rdx]
0x140027607  mov     [rbx+0Dh], al
0x14002760a  inc     qword ptr [rdx]
0x14002760d  mov     rax, [rsp+48h+arg_40]
0x140027615  mov     rcx, [rbx+6]
0x140027619  mov     [rax], rcx
0x14002761c  test    sil, sil
0x14002761f  jz      short loc_14002763B
0x140027621  mov     eax, [r14+70h]
0x140027625  sub     eax, 11h
0x140027628  cmp     eax, 1
0x14002762b  jbe     short loc_14002763B
0x14002762d  lea     rcx, [rbx+16h]
0x140027631  mov     edx, 8
0x140027636  call    CDGenerateRandomBits
0x14002763b  mov     rax, [rsp+48h+arg_38]
0x140027643  mov     [r12], r15d
0x140027647  mov     [rax], rbx
0x14002764a  mov     rbx, [rsp+48h+arg_8]
0x14002764f  mov     eax, edi
0x140027651  mov     rbp, [rsp+48h+arg_18]
0x140027656  add     rsp, 20h
0x14002765a  pop     r15
0x14002765c  pop     r14
0x14002765e  pop     r12
0x140027660  pop     rdi
0x140027661  pop     rsi
0x140027662  retn
```
