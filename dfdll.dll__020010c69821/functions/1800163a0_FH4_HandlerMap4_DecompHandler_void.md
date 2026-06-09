# FH4::HandlerMap4::DecompHandler(void)

- ea: `0x1800163a0`
- end: `0x180016528`
- name: `?DecompHandler@HandlerMap4@FH4@@AEAAXXZ`
- size: `392`
- prototype: `void __fastcall(FH4::HandlerMap4 *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015204`
- `0x180015700`
- `0x180015f08`

## callees

- `0x1800163a0`

## pseudocode

```c
void __fastcall FH4::HandlerMap4::DecompHandler(FH4::HandlerMap4 *this)
{
  char *v2; // rax
  char v3; // r10
  _BYTE *v4; // rdx
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rcx
  int *v8; // r9
  char v9; // al
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  char *v14; // r9
  __int64 v15; // rax
  int v16; // edx
  __int64 v17; // rcx
  _BYTE *v18; // r9
  int v19; // eax
  __int64 v20; // rcx
  _BYTE *v21; // r9
  int v22; // eax

  *((_BYTE *)this + 24) = 0;
  *(_QWORD *)((char *)this + 28) = 0;
  *(_QWORD *)((char *)this + 36) = 0;
  *((_OWORD *)this + 3) = 0;
  v2 = (char *)*((_QWORD *)this + 1);
  v3 = *v2;
  v4 = v2 + 1;
  *((_BYTE *)this + 24) = *v2;
  *((_QWORD *)this + 1) = v2 + 1;
  if ( (v3 & 1) != 0 )
  {
    v5 = *v4 & 0xF;
    v4 -= *((char *)&FH4::s_negLengthTab + v5);
    *((_DWORD *)this + 7) = *((_DWORD *)v4 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v5);
    *((_QWORD *)this + 1) = v4;
  }
  if ( (v3 & 2) != 0 )
  {
    v6 = *(_DWORD *)v4;
    v4 += 4;
    *((_QWORD *)this + 1) = v4;
    *((_DWORD *)this + 8) = v6;
  }
  if ( (v3 & 4) != 0 )
  {
    v7 = *v4 & 0xF;
    v4 -= *((char *)&FH4::s_negLengthTab + v7);
    *((_DWORD *)this + 9) = *((_DWORD *)v4 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v7);
    *((_QWORD *)this + 1) = v4;
  }
  v8 = (int *)(v4 + 4);
  *((_DWORD *)this + 10) = *(_DWORD *)v4;
  v9 = v3 & 0x30;
  *((_QWORD *)this + 1) = v4 + 4;
  if ( (v3 & 8) != 0 )
  {
    if ( v9 == 16 )
    {
      v10 = *v8;
      *((_QWORD *)this + 1) = v4 + 8;
      *((_QWORD *)this + 6) = v10;
      return;
    }
    if ( v9 == 32 )
    {
      v11 = *v8;
      *((_QWORD *)this + 1) = v4 + 8;
      *((_QWORD *)this + 6) = v11;
      v12 = *((int *)v4 + 2);
      *((_QWORD *)this + 1) = v4 + 12;
LABEL_16:
      *((_QWORD *)this + 7) = v12;
    }
  }
  else
  {
    if ( v9 == 16 )
    {
      v13 = *(_BYTE *)v8 & 0xF;
      v14 = (char *)v8 - *((char *)&FH4::s_negLengthTab + v13);
      v15 = (unsigned int)((*((_DWORD *)v14 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v13)) + *((_DWORD *)this + 18));
      *((_QWORD *)this + 1) = v14;
      *((_QWORD *)this + 6) = v15;
      return;
    }
    if ( v9 == 32 )
    {
      v16 = *((_DWORD *)this + 18);
      v17 = *(_BYTE *)v8 & 0xF;
      v18 = (char *)v8 - *((char *)&FH4::s_negLengthTab + v17);
      v19 = *((_DWORD *)v18 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v17);
      *((_QWORD *)this + 1) = v18;
      *((_QWORD *)this + 6) = (unsigned int)(v16 + v19);
      v20 = *v18 & 0xF;
      v21 = &v18[-*((char *)&FH4::s_negLengthTab + v20)];
      v22 = *((_DWORD *)v21 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v20);
      *((_QWORD *)this + 1) = v21;
      v12 = (unsigned int)(v16 + v22);
      goto LABEL_16;
    }
  }
}

```

## disassembly

```asm
0x1800163a0  xor     eax, eax
0x1800163a2  lea     r11, cs:180000000h
0x1800163a9  mov     [rcx+18h], al
0x1800163ac  xorps   xmm0, xmm0
0x1800163af  mov     [rcx+1Ch], rax
0x1800163b3  mov     r8, rcx
0x1800163b6  mov     [rcx+24h], rax
0x1800163ba  movups  xmmword ptr [rcx+30h], xmm0
0x1800163be  mov     rax, [rcx+8]
0x1800163c2  mov     r10b, [rax]
0x1800163c5  lea     rdx, [rax+1]
0x1800163c9  mov     [rcx+18h], r10b
0x1800163cd  mov     [rcx+8], rdx
0x1800163d1  test    r10b, 1
0x1800163d5  jz      short loc_1800163FE
0x1800163d7  movzx   ecx, byte ptr [rdx]
0x1800163da  and     ecx, 0Fh
0x1800163dd  movsx   rax, byte ptr [rcx+r11+21B70h]
0x1800163e6  mov     cl, [rcx+r11+21B80h]
0x1800163ee  sub     rdx, rax
0x1800163f1  mov     eax, [rdx-4]
0x1800163f4  shr     eax, cl
0x1800163f6  mov     [r8+1Ch], eax
0x1800163fa  mov     [r8+8], rdx
0x1800163fe  test    r10b, 2
0x180016402  jz      short loc_180016412
0x180016404  mov     eax, [rdx]
0x180016406  add     rdx, 4
0x18001640a  mov     [r8+8], rdx
0x18001640e  mov     [r8+20h], eax
0x180016412  test    r10b, 4
0x180016416  jz      short loc_18001643F
0x180016418  movzx   ecx, byte ptr [rdx]
0x18001641b  and     ecx, 0Fh
0x18001641e  movsx   rax, byte ptr [rcx+r11+21B70h]
0x180016427  mov     cl, [rcx+r11+21B80h]
0x18001642f  sub     rdx, rax
0x180016432  mov     eax, [rdx-4]
0x180016435  shr     eax, cl
0x180016437  mov     [r8+24h], eax
0x18001643b  mov     [r8+8], rdx
0x18001643f  mov     eax, [rdx]
0x180016441  lea     r9, [rdx+4]
0x180016445  mov     [r8+28h], eax
0x180016449  mov     al, r10b
0x18001644c  and     al, 30h
0x18001644e  mov     [r8+8], r9
0x180016452  test    r10b, 8
0x180016456  jz      short loc_180016493
0x180016458  cmp     al, 10h
0x18001645a  jnz     short loc_18001646C
0x18001645c  movsxd  rcx, dword ptr [r9]
0x18001645f  lea     rax, [r9+4]
0x180016463  mov     [r8+8], rax
0x180016467  mov     [r8+30h], rcx
0x18001646b  retn
0x18001646c  cmp     al, 20h ; ' '
0x18001646e  jnz     locret_180016527
0x180016474  movsxd  rax, dword ptr [r9]
0x180016477  lea     rdx, [r9+4]
0x18001647b  mov     [r8+8], rdx
0x18001647f  mov     [r8+30h], rax
0x180016483  lea     rax, [rdx+4]
0x180016487  movsxd  rcx, dword ptr [rdx]
0x18001648a  mov     [r8+8], rax
0x18001648e  jmp     loc_180016523
0x180016493  cmp     al, 10h
0x180016495  jnz     short loc_1800164C7
0x180016497  movzx   ecx, byte ptr [r9]
0x18001649b  and     ecx, 0Fh
0x18001649e  movsx   rax, byte ptr [rcx+r11+21B70h]
0x1800164a7  mov     cl, [rcx+r11+21B80h]
0x1800164af  sub     r9, rax
0x1800164b2  mov     eax, [r8+48h]
0x1800164b6  mov     edx, [r9-4]
0x1800164ba  shr     edx, cl
0x1800164bc  add     eax, edx
0x1800164be  mov     [r8+8], r9
0x1800164c2  mov     [r8+30h], rax
0x1800164c6  retn
0x1800164c7  cmp     al, 20h ; ' '
0x1800164c9  jnz     short locret_180016527
0x1800164cb  movzx   ecx, byte ptr [r9]
0x1800164cf  mov     edx, [r8+48h]
0x1800164d3  and     ecx, 0Fh
0x1800164d6  movsx   rax, byte ptr [rcx+r11+21B70h]
0x1800164df  mov     cl, [rcx+r11+21B80h]
0x1800164e7  sub     r9, rax
0x1800164ea  mov     eax, [r9-4]
0x1800164ee  shr     eax, cl
0x1800164f0  mov     [r8+8], r9
0x1800164f4  lea     ecx, [rdx+rax]
0x1800164f7  mov     [r8+30h], rcx
0x1800164fb  movzx   ecx, byte ptr [r9]
0x1800164ff  and     ecx, 0Fh
0x180016502  movsx   rax, byte ptr [rcx+r11+21B70h]
0x18001650b  mov     cl, [rcx+r11+21B80h]
0x180016513  sub     r9, rax
0x180016516  mov     eax, [r9-4]
0x18001651a  shr     eax, cl
0x18001651c  mov     [r8+8], r9
0x180016520  lea     ecx, [rdx+rax]
0x180016523  mov     [r8+38h], rcx
0x180016527  retn
```
