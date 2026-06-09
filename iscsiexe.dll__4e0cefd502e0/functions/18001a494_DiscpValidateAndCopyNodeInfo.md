# DiscpValidateAndCopyNodeInfo

- ea: `0x18001a494`
- end: `0x18001ae64`
- name: `DiscpValidateAndCopyNodeInfo`
- size: `2512`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int, _DWORD *, _DWORD *, int *, unsigned int *, _QWORD *, __int64 *, __int64 *, char)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180019038`

## callees

- `0x180001cfe`
- `0x180018e80`
- `0x18001a494`

## import_xrefs

- `ISCSIUM!DiscpCopyString` at `0x18001a6aa`
- `ISCSIUM!DiscpCopyString` at `0x18001a73d`
- `ISCSIUM!DiscpCopyString` at `0x18001a6aa`
- `ISCSIUM!DiscpCopyString` at `0x18001a73d`
- `ISCSIUM!DiscpGetStringFromDataBlock` at `0x18001a6e5`
- `ISCSIUM!DiscpGetStringFromDataBlock` at `0x18001a778`
- `ISCSIUM!DiscpGetStringFromDataBlock` at `0x18001a6e5`
- `ISCSIUM!DiscpGetStringFromDataBlock` at `0x18001a778`
- `ISCSIUM!DiscpPadDataBlock` at `0x18001a60b`
- `ISCSIUM!DiscpPadDataBlock` at `0x18001a89c`
- `ISCSIUM!DiscpPadDataBlock` at `0x18001a958`
- `ISCSIUM!DiscpPadDataBlock` at `0x18001aaf0`
- `ISCSIUM!DiscpPadDataBlock` at `0x18001ac16`
- `ISCSIUM!DiscpPadDataBlock` at `0x18001aca2`
- `ISCSIUM!DiscpPadDataBlock` at `0x18001a60b`
- `ISCSIUM!DiscpPadDataBlock` at `0x18001a89c`
- `ISCSIUM!DiscpPadDataBlock` at `0x18001a958`
- `ISCSIUM!DiscpPadDataBlock` at `0x18001aaf0`
- `ISCSIUM!DiscpPadDataBlock` at `0x18001ac16`
- `ISCSIUM!DiscpPadDataBlock` at `0x18001aca2`

## pseudocode

```c
__int64 __fastcall DiscpValidateAndCopyNodeInfo(
        _QWORD *a1,
        unsigned int a2,
        _DWORD *a3,
        _DWORD *a4,
        int *a5,
        unsigned int *a6,
        _QWORD *a7,
        __int64 *a8,
        __int64 *a9,
        char a10)
{
  unsigned int StringFromDataBlock; // r10d
  char v11; // bl
  _QWORD *v12; // r11
  _QWORD *v13; // rsi
  __int64 v14; // rdi
  unsigned int v15; // r15d
  __int64 v16; // r13
  _DWORD *v17; // rcx
  unsigned int v18; // edx
  int v19; // r12d
  int v20; // r14d
  unsigned int v21; // r8d
  unsigned int v22; // eax
  char *v23; // rcx
  unsigned int v24; // eax
  unsigned int v25; // eax
  char *v26; // rdx
  char *v27; // rcx
  unsigned int v28; // eax
  unsigned int v29; // edx
  unsigned __int16 *v30; // rax
  unsigned int v31; // ecx
  unsigned int v32; // r13d
  unsigned int i; // r12d
  _WORD *v34; // rcx
  unsigned int v35; // eax
  unsigned int v36; // eax
  _WORD *v37; // rdx
  _WORD *v38; // rcx
  unsigned int v39; // eax
  unsigned int v40; // eax
  int v41; // r14d
  unsigned int v42; // eax
  unsigned int v44; // [rsp+40h] [rbp-C8h] BYREF
  int IPAddrFromDataBlock; // [rsp+44h] [rbp-C4h]
  __int64 v46; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int v47; // [rsp+50h] [rbp-B8h]
  int v48; // [rsp+54h] [rbp-B4h]
  int v49; // [rsp+58h] [rbp-B0h]
  int v50; // [rsp+5Ch] [rbp-ACh]
  int v51; // [rsp+60h] [rbp-A8h]
  unsigned int v52; // [rsp+64h] [rbp-A4h]
  unsigned int v53; // [rsp+68h] [rbp-A0h]
  _QWORD *v54; // [rsp+70h] [rbp-98h]
  _QWORD *v55; // [rsp+78h] [rbp-90h]
  __int64 v56; // [rsp+80h] [rbp-88h]
  __int64 v57; // [rsp+88h] [rbp-80h] BYREF
  __int64 v58; // [rsp+90h] [rbp-78h] BYREF
  __int64 v59; // [rsp+98h] [rbp-70h]
  __int64 v60; // [rsp+A0h] [rbp-68h]
  __int64 v61; // [rsp+A8h] [rbp-60h]
  __int64 v62; // [rsp+B0h] [rbp-58h]
  __int64 v63; // [rsp+B8h] [rbp-50h]
  _QWORD *v64; // [rsp+C0h] [rbp-48h]
  _QWORD *v65; // [rsp+110h] [rbp+8h] BYREF
  unsigned int v66; // [rsp+118h] [rbp+10h] BYREF
  _DWORD *v67; // [rsp+120h] [rbp+18h]
  _DWORD *v68; // [rsp+128h] [rbp+20h]

  v68 = a4;
  v67 = a3;
  v66 = a2;
  v65 = a1;
  StringFromDataBlock = 0;
  v58 = 0;
  v46 = 0;
  v57 = 0;
  v44 = 0;
  if ( a7 && a8 && a9 )
  {
    v11 = 1;
    v12 = (_QWORD *)*a7;
    v13 = (_QWORD *)*a7;
    v55 = (_QWORD *)*a7;
    v14 = *a8;
    v46 = *a9;
    v15 = (unsigned int)*a5 >> 1;
  }
  else
  {
    v15 = 0;
    v13 = 0;
    v55 = 0;
    v12 = 0;
    v14 = 0;
    v11 = 0;
  }
  a10 = v11;
  v56 = v14;
  v54 = v12;
  v47 = v15;
  if ( a2 >= 8 )
  {
    v59 = 0;
    v16 = *a1;
    v60 = *a1;
    v17 = a1 + 1;
    v65 = v17;
    v18 = a2 - 8;
    v66 = v18;
    if ( v18 >= 4 )
    {
      v19 = 0;
      v49 = 0;
      v20 = 0;
      v48 = 0;
      v21 = *v17;
      v53 = v21;
      v65 = v17 + 1;
      v66 = v18 - 4;
      v61 = v21 << 6;
      LODWORD(v62) = v21 << 6;
      *a6 = v21;
      v22 = 0;
      v50 = 0;
      while ( v22 < v21 )
      {
        if ( v11 )
        {
          memset_0(v13, 0, 0x40u);
          v13[7] = v14;
        }
        StringFromDataBlock = DiscpPadDataBlock(8, &v65, &v66);
        IPAddrFromDataBlock = StringFromDataBlock;
        if ( StringFromDataBlock )
          return StringFromDataBlock;
        if ( v11 )
        {
          *v13 = v16;
          if ( v66 < 8 )
            return StringFromDataBlock;
          v13[1] = *v65++;
          v66 -= 8;
        }
        else
        {
          if ( v66 < 8 )
            return StringFromDataBlock;
          ++v65;
          v66 -= 8;
        }
        if ( v11 )
        {
          v13[2] = v46;
          StringFromDataBlock = DiscpCopyString(&v46, &v44, &v65, v15, &v66);
          IPAddrFromDataBlock = StringFromDataBlock;
          v46 += 2LL * v44;
          v15 -= v44;
          v47 = v15;
        }
        else
        {
          StringFromDataBlock = DiscpGetStringFromDataBlock(&v57, &v44, &v65, &v66);
          IPAddrFromDataBlock = StringFromDataBlock;
          if ( !StringFromDataBlock )
          {
            v20 += v44 + 2;
            v48 = v20;
          }
        }
        if ( StringFromDataBlock )
          return StringFromDataBlock;
        if ( v11 )
        {
          v13[4] = v46;
          StringFromDataBlock = DiscpCopyString(&v46, &v44, &v65, v15, &v66);
          IPAddrFromDataBlock = StringFromDataBlock;
          v46 += 2LL * v44;
          v15 -= v44;
          v47 = v15;
        }
        else
        {
          StringFromDataBlock = DiscpGetStringFromDataBlock(&v57, &v44, &v65, &v66);
          IPAddrFromDataBlock = StringFromDataBlock;
          if ( !StringFromDataBlock )
          {
            v20 += v44 + 2;
            v48 = v20;
          }
        }
        if ( StringFromDataBlock )
          return StringFromDataBlock;
        if ( v11 )
        {
          if ( v66 < 2 )
            return StringFromDataBlock;
          *((_WORD *)v13 + 23) = *(_WORD *)v65;
          v23 = (char *)v65 + 2;
          v65 = (_QWORD *)((char *)v65 + 2);
          v24 = v66;
        }
        else
        {
          v24 = v66;
          if ( v66 < 2 )
            return StringFromDataBlock;
          v23 = (char *)v65 + 2;
          v65 = (_QWORD *)((char *)v65 + 2);
        }
        v25 = v24 - 2;
        v66 = v25;
        v26 = v23;
        if ( v11 )
        {
          if ( v25 < 6 )
            return StringFromDataBlock;
          *((_DWORD *)v13 + 10) = *(_DWORD *)v23;
          *((_WORD *)v13 + 22) = *((_WORD *)v23 + 2);
          v27 = (char *)v65 + 6;
          v65 = (_QWORD *)((char *)v65 + 6);
          v25 = v66;
        }
        else
        {
          if ( v25 < 6 )
            return StringFromDataBlock;
          v27 = v23 + 6;
          v65 = v26 + 6;
        }
        v28 = v25 - 6;
        v66 = v28;
        if ( v28 < 6 )
        {
          StringFromDataBlock = -268500967;
          IPAddrFromDataBlock = -268500967;
          return StringFromDataBlock;
        }
        v66 = v28 - 6;
        v65 = v27 + 6;
        StringFromDataBlock = DiscpPadDataBlock(4, &v65, &v66);
        IPAddrFromDataBlock = StringFromDataBlock;
        if ( StringFromDataBlock )
          return StringFromDataBlock;
        if ( v66 < 0x10 )
        {
          StringFromDataBlock = -268500967;
          IPAddrFromDataBlock = -268500967;
          return StringFromDataBlock;
        }
        v29 = v66 - 16;
        v66 = v29;
        v30 = (unsigned __int16 *)(v65 + 2);
        v65 += 2;
        if ( v29 < 2 )
          return StringFromDataBlock;
        v31 = *v30;
        v65 = v30 + 1;
        v66 = v29 - 2;
        v32 = v31;
        if ( v11 )
          *((_DWORD *)v13 + 12) = v31;
        v49 = v19 + 40 * v31;
        for ( i = 0; ; ++i )
        {
          v52 = i;
          if ( i >= v32 )
            break;
          if ( v11 )
          {
            *(_OWORD *)v14 = 0;
            *(_OWORD *)(v14 + 16) = 0;
            *(_QWORD *)(v14 + 32) = 0;
          }
          StringFromDataBlock = DiscpPadDataBlock(8, &v65, &v66);
          IPAddrFromDataBlock = StringFromDataBlock;
          if ( v11 )
          {
            *(_QWORD *)v14 = v60;
            if ( v66 < 8 )
              return StringFromDataBlock;
            *(_QWORD *)(v14 + 8) = *v65;
            v34 = ++v65;
            v35 = v66;
          }
          else
          {
            v35 = v66;
            if ( v66 < 8 )
              return StringFromDataBlock;
            v34 = ++v65;
          }
          v36 = v35 - 8;
          v66 = v36;
          v37 = v34;
          if ( v11 )
          {
            if ( v36 < 2 )
              return StringFromDataBlock;
            *(_WORD *)(v14 + 36) = *v34;
            v38 = (_WORD *)v65 + 1;
            v65 = (_QWORD *)((char *)v65 + 2);
            v36 = v66;
          }
          else
          {
            if ( v36 < 2 )
              return StringFromDataBlock;
            v38 = v34 + 1;
            v65 = v37 + 1;
          }
          v39 = v36 - 2;
          v66 = v39;
          if ( v39 < 0xE )
          {
            StringFromDataBlock = -268500967;
            IPAddrFromDataBlock = -268500967;
            return StringFromDataBlock;
          }
          v66 = v39 - 14;
          v65 = v38 + 7;
          if ( v11 )
          {
            *(_QWORD *)(v14 + 16) = v46;
            IPAddrFromDataBlock = DiscpGetIPAddrFromDataBlock(&v46, &v58, v15, &v65, &v66, &v44);
            v40 = v44;
            v15 -= v44;
            v47 = v15;
          }
          else
          {
            IPAddrFromDataBlock = DiscpGetIPAddrFromDataBlock(0, 0, 0, &v65, &v66, &v44);
            v40 = v44;
          }
          v41 = v20 + 2 * v40 + 2;
          v48 = v41;
          StringFromDataBlock = DiscpPadDataBlock(4, &v65, &v66);
          IPAddrFromDataBlock = StringFromDataBlock;
          if ( StringFromDataBlock )
            return StringFromDataBlock;
          if ( v11 )
          {
            if ( v66 < 4 )
              return StringFromDataBlock;
            v51 = *(_DWORD *)v65;
            v65 = (_QWORD *)((char *)v65 + 4);
            v66 -= 4;
            *(_WORD *)(v14 + 32) = v51;
          }
          else
          {
            if ( v66 < 4 )
              return StringFromDataBlock;
            v65 = (_QWORD *)((char *)v65 + 4);
            v66 -= 4;
          }
          if ( v11 )
          {
            *(_QWORD *)(v14 + 24) = v46;
            StringFromDataBlock = DiscpGetIPAddrFromDataBlock(&v46, &v58, v15, &v65, &v66, &v44);
            IPAddrFromDataBlock = StringFromDataBlock;
            v42 = v44;
            v15 -= v44;
            v47 = v15;
          }
          else
          {
            StringFromDataBlock = DiscpGetIPAddrFromDataBlock(0, 0, 0, &v65, &v66, &v44);
            IPAddrFromDataBlock = StringFromDataBlock;
            v42 = v44;
          }
          if ( StringFromDataBlock )
            return StringFromDataBlock;
          v20 = v41 + 2 * v42 + 2;
          v48 = v20;
          StringFromDataBlock = DiscpPadDataBlock(4, &v65, &v66);
          IPAddrFromDataBlock = StringFromDataBlock;
          if ( StringFromDataBlock )
            return StringFromDataBlock;
          if ( v11 )
          {
            if ( v66 < 4 )
              return StringFromDataBlock;
            v51 = *(_DWORD *)v65;
            v65 = (_QWORD *)((char *)v65 + 4);
            v66 -= 4;
            *(_WORD *)(v14 + 34) = v51;
          }
          else
          {
            if ( v66 < 4 )
              return StringFromDataBlock;
            v65 = (_QWORD *)((char *)v65 + 4);
            v66 -= 4;
          }
          StringFromDataBlock = DiscpPadDataBlock(8, &v65, &v66);
          IPAddrFromDataBlock = StringFromDataBlock;
          if ( StringFromDataBlock )
            return StringFromDataBlock;
          if ( v66 < 0xC )
          {
            StringFromDataBlock = -268500967;
            IPAddrFromDataBlock = -268500967;
            return StringFromDataBlock;
          }
          v66 -= 12;
          v65 = (_QWORD *)((char *)v65 + 12);
          v59 += 40;
          v63 = v59;
          v14 += 40;
          v56 = v14;
        }
        v54 += 8;
        v64 = v54;
        v13 += 8;
        v55 = v13;
        v22 = ++v50;
        v19 = v49;
        v21 = v53;
        v16 = v60;
      }
      if ( v11 )
      {
        *a7 = v13;
        *a8 = v14;
        *a9 = v46;
        *a5 = 2 * v15;
      }
      else
      {
        *v67 = v61;
        *v68 = v19;
        *a5 = v20;
      }
    }
  }
  return StringFromDataBlock;
}

```

## disassembly

```asm
0x18001a494  mov     rax, rsp
0x18001a497  mov     [rax+20h], r9
0x18001a49b  mov     [rax+18h], r8
0x18001a49f  mov     [rax+10h], edx
0x18001a4a2  mov     [rax+8], rcx
0x18001a4a6  push    rbx
0x18001a4a7  push    rsi
0x18001a4a8  push    rdi
0x18001a4a9  push    r12
0x18001a4ab  push    r13
0x18001a4ad  push    r14
0x18001a4af  push    r15
0x18001a4b1  sub     rsp, 0D0h
0x18001a4b8  xor     r10d, r10d
0x18001a4bb  mov     [rax-78h], r10
0x18001a4bf  mov     [rsp+108h+var_C0], r10
0x18001a4c4  mov     [rax-80h], r10
0x18001a4c8  mov     [rsp+108h+var_C8], r10d
0x18001a4cd  mov     r9, [rsp+108h+arg_30]
0x18001a4d5  test    r9, r9
0x18001a4d8  jz      short loc_18001A51C
0x18001a4da  mov     rax, [rsp+108h+arg_38]
0x18001a4e2  test    rax, rax
0x18001a4e5  jz      short loc_18001A51C
0x18001a4e7  mov     r8, [rsp+108h+arg_40]
0x18001a4ef  test    r8, r8
0x18001a4f2  jz      short loc_18001A51C
0x18001a4f4  mov     bl, 1
0x18001a4f6  mov     r11, [r9]
0x18001a4f9  mov     rsi, r11
0x18001a4fc  mov     [rsp+108h+var_90], r11
0x18001a501  mov     rdi, [rax]
0x18001a504  mov     rax, [r8]
0x18001a507  mov     [rsp+108h+var_C0], rax
0x18001a50c  mov     r8, [rsp+108h+arg_20]
0x18001a514  mov     r15d, [r8]
0x18001a517  shr     r15d, 1
0x18001a51a  jmp     short loc_18001A52D
0x18001a51c  xor     r15d, r15d
0x18001a51f  xor     esi, esi
0x18001a521  mov     [rsp+108h+var_90], rsi
0x18001a526  xor     r11d, r11d
0x18001a529  xor     edi, edi
0x18001a52b  xor     bl, bl
0x18001a52d  mov     [rsp+108h+arg_48], bl
0x18001a534  mov     [rsp+108h+var_88], rdi
0x18001a53c  mov     [rsp+108h+var_98], r11
0x18001a541  mov     [rsp+108h+var_B8], r15d
0x18001a546  cmp     edx, 8
0x18001a549  jb      loc_18001AE4E
0x18001a54f  mov     [rsp+108h+var_70], r10
0x18001a557  mov     r13, [rcx]
0x18001a55a  mov     [rsp+108h+var_68], r13
0x18001a562  add     rcx, 8
0x18001a566  mov     [rsp+108h+arg_0], rcx
0x18001a56e  lea     eax, [rdx-8]
0x18001a571  mov     edx, eax
0x18001a573  mov     [rsp+108h+arg_8], eax
0x18001a57a  cmp     eax, 4
0x18001a57d  jb      loc_18001AE4E
0x18001a583  xor     r12d, r12d
0x18001a586  mov     [rsp+108h+var_B0], r12d
0x18001a58b  xor     r14d, r14d
0x18001a58e  mov     [rsp+108h+var_B4], r14d
0x18001a593  mov     r8d, [rcx]
0x18001a596  mov     [rsp+108h+var_A0], r8d
0x18001a59b  lea     rax, [rcx+4]
0x18001a59f  mov     [rsp+108h+arg_0], rax
0x18001a5a7  lea     eax, [rdx-4]
0x18001a5aa  mov     [rsp+108h+arg_8], eax
0x18001a5b1  mov     ecx, r8d
0x18001a5b4  shl     ecx, 6
0x18001a5b7  mov     [rsp+108h+var_60], rcx
0x18001a5bf  mov     dword ptr [rsp+108h+var_58], ecx
0x18001a5c6  mov     rax, [rsp+108h+arg_28]
0x18001a5ce  mov     [rax], r8d
0x18001a5d1  xor     eax, eax
0x18001a5d3  mov     [rsp+108h+var_AC], eax
0x18001a5d7  cmp     eax, r8d
0x18001a5da  jnb     loc_18001ADAE
0x18001a5e0  test    bl, bl
0x18001a5e2  jz      short loc_18001A5F6
0x18001a5e4  xor     edx, edx; Val
0x18001a5e6  lea     r8d, [rdx+40h]; Size
0x18001a5ea  mov     rcx, rsi; void *
0x18001a5ed  call    memset_0
0x18001a5f2  mov     [rsi+38h], rdi
0x18001a5f6  lea     r8, [rsp+108h+arg_8]
0x18001a5fe  lea     rdx, [rsp+108h+arg_0]
0x18001a606  mov     ecx, 8
0x18001a60b  call    cs:__imp_DiscpPadDataBlock
0x18001a611  mov     r10d, eax
0x18001a614  mov     [rsp+108h+var_C4], eax
0x18001a618  test    eax, eax
0x18001a61a  jnz     loc_18001AE4E
0x18001a620  test    bl, bl
0x18001a622  jz      short loc_18001A658
0x18001a624  mov     [rsi], r13
0x18001a627  cmp     [rsp+108h+arg_8], 8
0x18001a62f  jb      short loc_18001A653
0x18001a631  mov     rax, [rsp+108h+arg_0]
0x18001a639  mov     rcx, [rax]
0x18001a63c  mov     [rsi+8], rcx
0x18001a640  add     [rsp+108h+arg_0], 8
0x18001a649  add     [rsp+108h+arg_8], 0FFFFFFF8h
0x18001a651  jmp     short loc_18001A67B
0x18001a653  jmp     loc_18001AE4E
0x18001a658  mov     eax, [rsp+108h+arg_8]
0x18001a65f  cmp     eax, 8
0x18001a662  jb      loc_18001ADA9
0x18001a668  add     [rsp+108h+arg_0], 8
0x18001a671  add     eax, 0FFFFFFF8h
0x18001a674  mov     [rsp+108h+arg_8], eax
0x18001a67b  lea     r8, [rsp+108h+arg_0]
0x18001a683  lea     rdx, [rsp+108h+var_C8]
0x18001a688  test    bl, bl
0x18001a68a  jz      short loc_18001A6D5
0x18001a68c  mov     rax, [rsp+108h+var_C0]
0x18001a691  mov     [rsi+10h], rax
0x18001a695  lea     rax, [rsp+108h+arg_8]
0x18001a69d  mov     [rsp+108h+var_E8], rax
0x18001a6a2  mov     r9d, r15d
0x18001a6a5  lea     rcx, [rsp+108h+var_C0]
0x18001a6aa  call    cs:__imp_DiscpCopyString
0x18001a6b0  mov     r10d, eax
0x18001a6b3  mov     [rsp+108h+var_C4], eax
0x18001a6b7  mov     ecx, [rsp+108h+var_C8]
0x18001a6bb  mov     rax, [rsp+108h+var_C0]
0x18001a6c0  lea     rcx, [rax+rcx*2]
0x18001a6c4  mov     [rsp+108h+var_C0], rcx
0x18001a6c9  sub     r15d, [rsp+108h+var_C8]
0x18001a6ce  mov     [rsp+108h+var_B8], r15d
0x18001a6d3  jmp     short loc_18001A705
0x18001a6d5  lea     r9, [rsp+108h+arg_8]
0x18001a6dd  lea     rcx, [rsp+108h+var_80]
0x18001a6e5  call    cs:__imp_DiscpGetStringFromDataBlock
0x18001a6eb  mov     r10d, eax
0x18001a6ee  mov     [rsp+108h+var_C4], eax
0x18001a6f2  test    eax, eax
0x18001a6f4  jnz     short loc_18001A705
0x18001a6f6  mov     eax, [rsp+108h+var_C8]
0x18001a6fa  add     eax, 2
0x18001a6fd  add     r14d, eax
0x18001a700  mov     [rsp+108h+var_B4], r14d
0x18001a705  test    r10d, r10d
0x18001a708  jnz     loc_18001AE4E
0x18001a70e  lea     r8, [rsp+108h+arg_0]
0x18001a716  lea     rdx, [rsp+108h+var_C8]
0x18001a71b  test    bl, bl
0x18001a71d  jz      short loc_18001A768
0x18001a71f  mov     rax, [rsp+108h+var_C0]
0x18001a724  mov     [rsi+20h], rax
0x18001a728  lea     rax, [rsp+108h+arg_8]
0x18001a730  mov     [rsp+108h+var_E8], rax
0x18001a735  mov     r9d, r15d
0x18001a738  lea     rcx, [rsp+108h+var_C0]
0x18001a73d  call    cs:__imp_DiscpCopyString
0x18001a743  mov     r10d, eax
0x18001a746  mov     [rsp+108h+var_C4], eax
0x18001a74a  mov     ecx, [rsp+108h+var_C8]
0x18001a74e  mov     rax, [rsp+108h+var_C0]
0x18001a753  lea     rcx, [rax+rcx*2]
0x18001a757  mov     [rsp+108h+var_C0], rcx
0x18001a75c  sub     r15d, [rsp+108h+var_C8]
0x18001a761  mov     [rsp+108h+var_B8], r15d
0x18001a766  jmp     short loc_18001A798
0x18001a768  lea     r9, [rsp+108h+arg_8]
0x18001a770  lea     rcx, [rsp+108h+var_80]
0x18001a778  call    cs:__imp_DiscpGetStringFromDataBlock
0x18001a77e  mov     r10d, eax
0x18001a781  mov     [rsp+108h+var_C4], eax
0x18001a785  test    eax, eax
0x18001a787  jnz     short loc_18001A798
0x18001a789  mov     eax, [rsp+108h+var_C8]
0x18001a78d  add     eax, 2
0x18001a790  add     r14d, eax
0x18001a793  mov     [rsp+108h+var_B4], r14d
0x18001a798  test    r10d, r10d
0x18001a79b  jnz     loc_18001AE4E
0x18001a7a1  test    bl, bl
0x18001a7a3  jz      short loc_18001A7E0
0x18001a7a5  cmp     [rsp+108h+arg_8], 2
0x18001a7ad  jb      short loc_18001A7DB
0x18001a7af  mov     rax, [rsp+108h+arg_0]
0x18001a7b7  movzx   ecx, word ptr [rax]
0x18001a7ba  mov     [rsi+2Eh], cx
0x18001a7be  mov     rcx, [rsp+108h+arg_0]
0x18001a7c6  add     rcx, 2
0x18001a7ca  mov     [rsp+108h+arg_0], rcx
0x18001a7d2  mov     eax, [rsp+108h+arg_8]
0x18001a7d9  jmp     short loc_18001A804
0x18001a7db  jmp     loc_18001AE4E
0x18001a7e0  mov     eax, [rsp+108h+arg_8]
0x18001a7e7  cmp     eax, 2
0x18001a7ea  jb      loc_18001ADA4
0x18001a7f0  mov     rcx, [rsp+108h+arg_0]
0x18001a7f8  add     rcx, 2
0x18001a7fc  mov     [rsp+108h+arg_0], rcx
0x18001a804  add     eax, 0FFFFFFFEh
0x18001a807  mov     [rsp+108h+arg_8], eax
0x18001a80e  mov     rdx, rcx
0x18001a811  test    bl, bl
0x18001a813  jz      short loc_18001A849
0x18001a815  cmp     eax, 6
0x18001a818  jb      short loc_18001A844
0x18001a81a  mov     eax, [rcx]
0x18001a81c  mov     [rsi+28h], eax
0x18001a81f  movzx   eax, word ptr [rcx+4]
0x18001a823  mov     [rsi+2Ch], ax
0x18001a827  mov     rcx, [rsp+108h+arg_0]
0x18001a82f  add     rcx, 6
0x18001a833  mov     [rsp+108h+arg_0], rcx
0x18001a83b  mov     eax, [rsp+108h+arg_8]
0x18001a842  jmp     short loc_18001A85E
0x18001a844  jmp     loc_18001AE4E
0x18001a849  cmp     eax, 6
0x18001a84c  jb      loc_18001AD9F
0x18001a852  lea     rcx, [rdx+6]
0x18001a856  mov     [rsp+108h+arg_0], rcx
0x18001a85e  add     eax, 0FFFFFFFAh
0x18001a861  mov     [rsp+108h+arg_8], eax
0x18001a868  cmp     eax, 6
0x18001a86b  jb      loc_18001AD8F
0x18001a871  add     eax, 0FFFFFFFAh
0x18001a874  mov     [rsp+108h+arg_8], eax
0x18001a87b  lea     rax, [rcx+6]
0x18001a87f  mov     [rsp+108h+arg_0], rax
0x18001a887  lea     r8, [rsp+108h+arg_8]
0x18001a88f  lea     rdx, [rsp+108h+arg_0]
0x18001a897  mov     ecx, 4
0x18001a89c  call    cs:__imp_DiscpPadDataBlock
0x18001a8a2  mov     r10d, eax
0x18001a8a5  mov     [rsp+108h+var_C4], eax
0x18001a8a9  test    eax, eax
0x18001a8ab  jnz     loc_18001AE4E
0x18001a8b1  mov     edx, [rsp+108h+arg_8]
0x18001a8b8  cmp     edx, 10h
0x18001a8bb  jb      loc_18001AD7F
0x18001a8c1  add     edx, 0FFFFFFF0h
0x18001a8c4  mov     [rsp+108h+arg_8], edx
0x18001a8cb  mov     rax, [rsp+108h+arg_0]
0x18001a8d3  add     rax, 10h
0x18001a8d7  mov     [rsp+108h+arg_0], rax
0x18001a8df  cmp     edx, 2
0x18001a8e2  jb      loc_18001AD7A
0x18001a8e8  movzx   ecx, word ptr [rax]
0x18001a8eb  add     rax, 2
0x18001a8ef  mov     [rsp+108h+arg_0], rax
0x18001a8f7  lea     eax, [rdx-2]
0x18001a8fa  mov     [rsp+108h+arg_8], eax
0x18001a901  mov     r13d, ecx
0x18001a904  test    bl, bl
0x18001a906  jz      short loc_18001A90B
0x18001a908  mov     [rsi+30h], ecx
0x18001a90b  lea     eax, ds:0[rcx*4]
0x18001a912  add     eax, r13d
0x18001a915  lea     r12d, [r12+rax*8]
0x18001a919  mov     [rsp+108h+var_B0], r12d
0x18001a91e  xor     r12d, r12d
0x18001a921  mov     [rsp+108h+var_A4], r12d
0x18001a926  cmp     r12d, r13d
0x18001a929  jnb     loc_18001AD3A
0x18001a92f  test    bl, bl
0x18001a931  jz      short loc_18001A943
0x18001a933  xorps   xmm0, xmm0
0x18001a936  xor     eax, eax
0x18001a938  movups  xmmword ptr [rdi], xmm0
0x18001a93b  movups  xmmword ptr [rdi+10h], xmm0
0x18001a93f  mov     [rdi+20h], rax
0x18001a943  lea     r8, [rsp+108h+arg_8]
0x18001a94b  lea     rdx, [rsp+108h+arg_0]
0x18001a953  mov     ecx, 8
0x18001a958  call    cs:__imp_DiscpPadDataBlock
0x18001a95e  mov     r10d, eax
0x18001a961  mov     [rsp+108h+var_C4], eax
0x18001a965  test    bl, bl
0x18001a967  jz      short loc_18001A9AF
0x18001a969  mov     rax, [rsp+108h+var_68]
0x18001a971  mov     [rdi], rax
0x18001a974  cmp     [rsp+108h+arg_8], 8
0x18001a97c  jb      short loc_18001A9AA
0x18001a97e  mov     rax, [rsp+108h+arg_0]
0x18001a986  mov     rcx, [rax]
0x18001a989  mov     [rdi+8], rcx
0x18001a98d  mov     rcx, [rsp+108h+arg_0]
0x18001a995  add     rcx, 8
0x18001a999  mov     [rsp+108h+arg_0], rcx
0x18001a9a1  mov     eax, [rsp+108h+arg_8]
0x18001a9a8  jmp     short loc_18001A9D3
0x18001a9aa  jmp     loc_18001AE4E
0x18001a9af  mov     eax, [rsp+108h+arg_8]
0x18001a9b6  cmp     eax, 8
0x18001a9b9  jb      loc_18001AD35
0x18001a9bf  mov     rcx, [rsp+108h+arg_0]
0x18001a9c7  add     rcx, 8
0x18001a9cb  mov     [rsp+108h+arg_0], rcx
0x18001a9d3  add     eax, 0FFFFFFF8h
0x18001a9d6  mov     [rsp+108h+arg_8], eax
0x18001a9dd  mov     rdx, rcx
0x18001a9e0  test    bl, bl
  ... truncated ...
```
