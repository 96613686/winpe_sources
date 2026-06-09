# SetSequencePointers(DIRECTCOLORCONVFRM *)

- ea: `0x180013490`
- end: `0x180013770`
- name: `?SetSequencePointers@@YAXPEAUDIRECTCOLORCONVFRM@@@Z`
- size: `736`
- prototype: `void __fastcall(struct DIRECTCOLORCONVFRM *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fe84`
- `0x180019ea4`
- `0x18001f874`

## callees

- `0x180011650`
- `0x180013490`

## pseudocode

```c
void __fastcall SetSequencePointers(struct DIRECTCOLORCONVFRM *a1)
{
  _DWORD *v1; // rbx
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  _DWORD *v18; // r10
  unsigned int v19; // eax
  int v20; // r8d
  _DWORD *v21; // r9
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  int v28; // eax
  int v29; // r11d
  int v30; // eax
  int v31; // eax
  bool v32; // zf
  int v33; // r8d
  int v34; // eax
  int v35; // eax
  int v36; // r9d
  int v37; // r8d
  int v38; // edx

  v1 = *(_DWORD **)a1;
  v2 = *(_DWORD *)(*(_QWORD *)a1 + 16LL);
  if ( v2 > 0x32595559 )
  {
    v10 = v2 - 909193814;
    if ( v10 )
    {
      v11 = v10 - 52700163;
      if ( v11 )
      {
        v12 = v11 - 383507968;
        if ( !v12 )
          goto LABEL_22;
        v13 = v12 - 0x4000000;
        if ( !v13 )
          goto LABEL_22;
        v14 = v13 - 0x10000;
        if ( !v14 )
          goto LABEL_22;
        v15 = v14 - 19341824;
        if ( !v15 )
          goto LABEL_22;
        v16 = v15 - 16515816;
        if ( !v16 )
          goto LABEL_22;
        v17 = v16 - 8;
        if ( v17 )
        {
          if ( v17 != 50397196 )
            goto LABEL_23;
          goto LABEL_22;
        }
      }
LABEL_12:
      *((_DWORD *)a1 + 6) = 1;
      goto LABEL_23;
    }
LABEL_22:
    *((_DWORD *)a1 + 6) = 0;
    goto LABEL_23;
  }
  if ( v2 == 844715353 )
    goto LABEL_22;
  if ( !v2 )
    goto LABEL_22;
  v3 = v2 - 3;
  if ( !v3 )
    goto LABEL_22;
  v4 = v3 - 808531027;
  if ( !v4 )
    goto LABEL_22;
  v5 = v4 - 65523;
  if ( !v5 )
    goto LABEL_12;
  v6 = v5 - 16711687;
  if ( !v6 )
    goto LABEL_12;
  v7 = v6 - 8702;
  if ( !v7 )
    goto LABEL_12;
  v8 = v7 - 0x1000000;
  if ( !v8 )
    goto LABEL_12;
  v9 = v8 - 11;
  if ( !v9 || v9 == 56823 )
    goto LABEL_12;
LABEL_23:
  v18 = (_DWORD *)*((_QWORD *)a1 + 1);
  v19 = v18[4];
  if ( v19 <= 0x32315659 )
  {
    if ( v19 != 842094169 )
    {
      if ( v19 && v19 != 3 && v19 != 808531030 )
      {
        if ( v19 != 808596553 && v19 != 825308240 && v19 != 825316942 && v19 != 842094158 )
          goto LABEL_33;
        goto LABEL_32;
      }
      goto LABEL_44;
    }
LABEL_32:
    *((_DWORD *)a1 + 7) = 1;
    goto LABEL_33;
  }
  v22 = v19 - 842150992;
  if ( !v22 )
    goto LABEL_32;
  v23 = v22 - 2564361;
  if ( v23 )
  {
    v24 = v23 - 64478461;
    if ( v24 )
    {
      v25 = v24 - 522724355;
      if ( v25 )
      {
        v26 = v25 - 16515816;
        if ( v26 )
        {
          v27 = v26 - 8;
          if ( v27 )
          {
            if ( v27 != 50397196 )
              goto LABEL_33;
            goto LABEL_44;
          }
          goto LABEL_32;
        }
      }
    }
  }
LABEL_44:
  *((_DWORD *)a1 + 7) = 0;
LABEL_33:
  v20 = -1;
  *((_QWORD *)a1 + 2) = v1;
  if ( !v1[4] || v1[4] == 3 )
  {
    v21 = (_DWORD *)((char *)a1 + 14556);
    v28 = -1;
    if ( (int)v1[2] <= 0 )
      v28 = 1;
    *((_DWORD *)a1 + 3637) = v28;
  }
  else
  {
    v21 = (_DWORD *)((char *)a1 + 14556);
    *((_DWORD *)a1 + 3637) = 1;
    if ( *((_DWORD *)a1 + 3639) )
      *((_DWORD *)a1 + 3637) = -1;
  }
  v29 = v1[1];
  *((_DWORD *)a1 + 3649) = v29;
  v30 = -v1[2];
  if ( (int)v1[2] > 0 )
    v30 = v1[2];
  *((_DWORD *)a1 + 3650) = v30;
  switch ( v1[4] )
  {
    case 0x30323449:
      goto LABEL_58;
    case 0x31313450:
      goto LABEL_65;
    case 0x3131564E:
      goto LABEL_58;
    case 0x3231564E:
      *((_DWORD *)a1 + 3651) = v29;
      break;
    case 0x32315659:
    case 0x32323450:
      goto LABEL_58;
    case 0x39555659:
LABEL_65:
      v31 = v29 / 4;
      goto LABEL_59;
    case 0x56555949:
LABEL_58:
      v31 = v29 / 2;
LABEL_59:
      *((_DWORD *)a1 + 3651) = v31;
      break;
  }
  if ( !v18[4] || v18[4] == 3 )
  {
    if ( (int)v18[2] <= 0 )
      v20 = 1;
  }
  else
  {
    v32 = *v21 == 0;
    *((_DWORD *)a1 + 3638) = 1;
    if ( v32 )
      goto LABEL_69;
  }
  *((_DWORD *)a1 + 3638) = v20;
LABEL_69:
  v33 = v18[1];
  *((_DWORD *)a1 + 3640) = v33;
  v34 = -v18[2];
  if ( (int)v18[2] > 0 )
    v34 = v18[2];
  *((_DWORD *)a1 + 3641) = v34;
  switch ( v18[4] )
  {
    case 0x30323449:
    case 0x31313450:
    case 0x3131564E:
      goto LABEL_78;
    case 0x3231564E:
      *((_DWORD *)a1 + 3642) = v33;
      break;
    case 0x32315659:
    case 0x32323450:
    case 0x56555949:
LABEL_78:
      *((_DWORD *)a1 + 3642) = v33 / 2;
      break;
  }
  v35 = *((_DWORD *)a1 + 3825);
  if ( !v35 )
    v35 = v18[2];
  v36 = *((_DWORD *)a1 + 3824);
  if ( !v36 )
    v36 = v18[1];
  v37 = *((_DWORD *)a1 + 3823);
  if ( !v37 )
    v37 = v1[2];
  v38 = *((_DWORD *)a1 + 3822);
  if ( !v38 )
    v38 = v1[1];
  ReSetSequencePointers(a1, v38, v37, v36, v35);
}

```

## disassembly

```asm
0x180013490  mov     [rsp+arg_0], rbx
0x180013495  mov     [rsp+arg_8], rbp
0x18001349a  push    rsi
0x18001349b  sub     rsp, 30h
0x18001349f  mov     rbx, [rcx]
0x1800134a2  mov     edx, 32595559h
0x1800134a7  mov     ebp, 1
0x1800134ac  mov     r9d, 301000Ch
0x1800134b2  mov     r8d, 0FC02E8h
0x1800134b8  mov     eax, [rbx+10h]
0x1800134bb  cmp     eax, edx
0x1800134bd  ja      short loc_1800134FE
0x1800134bf  jz      short loc_180013537
0x1800134c1  test    eax, eax
0x1800134c3  jz      short loc_180013537
0x1800134c5  sub     eax, 3
0x1800134c8  jz      short loc_180013537
0x1800134ca  sub     eax, 30313453h
0x1800134cf  jz      short loc_180013537
0x1800134d1  sub     eax, 0FFF3h
0x1800134d6  jz      short loc_1800134F9
0x1800134d8  sub     eax, 0FF0007h
0x1800134dd  jz      short loc_1800134F9
0x1800134df  sub     eax, 21FEh
0x1800134e4  jz      short loc_1800134F9
0x1800134e6  sub     eax, 1000000h
0x1800134eb  jz      short loc_1800134F9
0x1800134ed  sub     eax, 0Bh
0x1800134f0  jz      short loc_1800134F9
0x1800134f2  cmp     eax, 0DDF7h
0x1800134f7  jnz     short loc_18001353E
0x1800134f9  mov     [rcx+18h], ebp
0x1800134fc  jmp     short loc_18001353E
0x1800134fe  sub     eax, 36313256h
0x180013503  jz      short loc_180013537
0x180013505  sub     eax, 3242403h
0x18001350a  jz      short loc_1800134F9
0x18001350c  sub     eax, 16DBDE00h
0x180013511  jz      short loc_180013537
0x180013513  sub     eax, 4000000h
0x180013518  jz      short loc_180013537
0x18001351a  sub     eax, 10000h
0x18001351f  jz      short loc_180013537
0x180013521  sub     eax, 1272200h
0x180013526  jz      short loc_180013537
0x180013528  sub     eax, r8d
0x18001352b  jz      short loc_180013537
0x18001352d  sub     eax, 8
0x180013530  jz      short loc_1800134F9
0x180013532  cmp     eax, r9d
0x180013535  jnz     short loc_18001353E
0x180013537  mov     dword ptr [rcx+18h], 0
0x18001353e  mov     r10, [rcx+8]
0x180013542  mov     edx, 32315659h
0x180013547  mov     eax, [r10+10h]
0x18001354b  cmp     eax, edx
0x18001354d  ja      short loc_1800135B8
0x18001354f  jz      short loc_180013585
0x180013551  test    eax, eax
0x180013553  jz      loc_1800135E3
0x180013559  cmp     eax, 3
0x18001355c  jz      loc_1800135E3
0x180013562  cmp     eax, 30313456h
0x180013567  jz      short loc_1800135E3
0x180013569  cmp     eax, 30323449h
0x18001356e  jz      short loc_180013585
0x180013570  cmp     eax, 31313450h
0x180013575  jz      short loc_180013585
0x180013577  cmp     eax, 3131564Eh
0x18001357c  jz      short loc_180013585
0x18001357e  cmp     eax, 3231564Eh
0x180013583  jnz     short loc_180013588
0x180013585  mov     [rcx+1Ch], ebp
0x180013588  or      r8d, 0FFFFFFFFh
0x18001358c  mov     [rcx+10h], rbx
0x180013590  cmp     dword ptr [rbx+10h], 0
0x180013594  jz      short loc_1800135EC
0x180013596  cmp     dword ptr [rbx+10h], 3
0x18001359a  jz      short loc_1800135EC
0x18001359c  lea     r9, [rcx+38DCh]
0x1800135a3  mov     [rcx+38D4h], ebp
0x1800135a9  cmp     dword ptr [r9], 0
0x1800135ad  jz      short loc_180013603
0x1800135af  mov     [rcx+38D4h], r8d
0x1800135b6  jmp     short loc_180013603
0x1800135b8  sub     eax, 32323450h
0x1800135bd  jz      short loc_180013585
0x1800135bf  sub     eax, 272109h
0x1800135c4  jz      short loc_1800135E3
0x1800135c6  sub     eax, 3D7DCFDh
0x1800135cb  jz      short loc_1800135E3
0x1800135cd  sub     eax, 1F282403h
0x1800135d2  jz      short loc_1800135E3
0x1800135d4  sub     eax, r8d
0x1800135d7  jz      short loc_1800135E3
0x1800135d9  sub     eax, 8
0x1800135dc  jz      short loc_180013585
0x1800135de  cmp     eax, r9d
0x1800135e1  jnz     short loc_180013588
0x1800135e3  mov     dword ptr [rcx+1Ch], 0
0x1800135ea  jmp     short loc_180013588
0x1800135ec  cmp     dword ptr [rbx+8], 0
0x1800135f0  lea     r9, [rcx+38DCh]
0x1800135f7  mov     eax, r8d
0x1800135fa  cmovle  eax, ebp
0x1800135fd  mov     [rcx+38D4h], eax
0x180013603  mov     r11d, [rbx+4]
0x180013607  mov     esi, 2
0x18001360c  mov     [rcx+3904h], r11d
0x180013613  mov     eax, [rbx+8]
0x180013616  neg     eax
0x180013618  cmovs   eax, [rbx+8]
0x18001361c  mov     [rcx+3908h], eax
0x180013622  mov     edx, [rbx+10h]
0x180013625  sub     edx, 30323449h
0x18001362b  jz      short loc_180013662
0x18001362d  sub     edx, 0FF0007h
0x180013633  jz      short loc_180013693
0x180013635  sub     edx, 21FEh
0x18001363b  jz      short loc_180013662
0x18001363d  sub     edx, 1000000h
0x180013643  jz      short loc_18001368A
0x180013645  sub     edx, 0Bh
0x180013648  jz      short loc_180013662
0x18001364a  sub     edx, 0DDF7h
0x180013650  jz      short loc_180013662
0x180013652  sub     edx, 7232209h
0x180013658  jz      short loc_180013693
0x18001365a  cmp     edx, 1D0002F0h
0x180013660  jnz     short loc_18001366E
0x180013662  mov     eax, r11d
0x180013665  cdq
0x180013666  idiv    esi
0x180013668  mov     [rcx+390Ch], eax
0x18001366e  cmp     dword ptr [r10+10h], 0
0x180013673  jz      short loc_1800136A2
0x180013675  cmp     dword ptr [r10+10h], 3
0x18001367a  jz      short loc_1800136A2
0x18001367c  cmp     dword ptr [r9], 0
0x180013680  mov     [rcx+38D8h], ebp
0x180013686  jz      short loc_1800136B2
0x180013688  jmp     short loc_1800136AB
0x18001368a  mov     [rcx+390Ch], r11d
0x180013691  jmp     short loc_18001366E
0x180013693  mov     eax, r11d
0x180013696  mov     r11d, 4
0x18001369c  cdq
0x18001369d  idiv    r11d
0x1800136a0  jmp     short loc_180013668
0x1800136a2  cmp     dword ptr [r10+8], 0
0x1800136a7  cmovle  r8d, ebp
0x1800136ab  mov     [rcx+38D8h], r8d
0x1800136b2  mov     r8d, [r10+4]
0x1800136b6  mov     [rcx+38E0h], r8d
0x1800136bd  mov     eax, [r10+8]
0x1800136c1  neg     eax
0x1800136c3  cmovs   eax, [r10+8]
0x1800136c8  mov     [rcx+38E4h], eax
0x1800136ce  mov     edx, [r10+10h]
0x1800136d2  sub     edx, 30323449h
0x1800136d8  jz      short loc_180013707
0x1800136da  sub     edx, 0FF0007h
0x1800136e0  jz      short loc_180013707
0x1800136e2  sub     edx, 21FEh
0x1800136e8  jz      short loc_180013707
0x1800136ea  sub     edx, 1000000h
0x1800136f0  jz      short loc_180013767
0x1800136f2  sub     edx, 0Bh
0x1800136f5  jz      short loc_180013707
0x1800136f7  sub     edx, 0DDF7h
0x1800136fd  jz      short loc_180013707
0x1800136ff  cmp     edx, 242324F9h
0x180013705  jnz     short loc_180013713
0x180013707  mov     eax, r8d
0x18001370a  cdq
0x18001370b  idiv    esi
0x18001370d  mov     [rcx+38E8h], eax
0x180013713  mov     eax, [rcx+3BC4h]
0x180013719  test    eax, eax
0x18001371b  jnz     short loc_180013721
0x18001371d  mov     eax, [r10+8]
0x180013721  mov     r9d, [rcx+3BC0h]
0x180013728  test    r9d, r9d
0x18001372b  jnz     short loc_180013731
0x18001372d  mov     r9d, [r10+4]; int
0x180013731  mov     r8d, [rcx+3BBCh]
0x180013738  test    r8d, r8d
0x18001373b  jnz     short loc_180013741
0x18001373d  mov     r8d, [rbx+8]; int
0x180013741  mov     edx, [rcx+3BB8h]
0x180013747  test    edx, edx
0x180013749  jnz     short loc_18001374E
0x18001374b  mov     edx, [rbx+4]; int
0x18001374e  mov     [rsp+38h+var_18], eax; int
0x180013752  call    ?ReSetSequencePointers@@YAXPEAUDIRECTCOLORCONVFRM@@JJJJ@Z; ReSetSequencePointers(DIRECTCOLORCONVFRM *,long,long,long,long)
0x180013757  mov     rbx, [rsp+38h+arg_0]
0x18001375c  mov     rbp, [rsp+38h+arg_8]
0x180013761  add     rsp, 30h
0x180013765  pop     rsi
0x180013766  retn
0x180013767  mov     [rcx+38E8h], r8d
0x18001376e  jmp     short loc_180013713
```
