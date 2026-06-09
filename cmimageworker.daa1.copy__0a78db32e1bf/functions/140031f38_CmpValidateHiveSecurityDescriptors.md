# CmpValidateHiveSecurityDescriptors

- ea: `0x140031f38`
- end: `0x1400323a7`
- name: `CmpValidateHiveSecurityDescriptors`
- size: `1135`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002a338`

## callees

- `0x140027730`
- `0x14002d7d4`
- `0x14002e3f0`
- `0x14002e8cc`
- `0x140031154`
- `0x140031378`
- `0x140031390`
- `0x140031990`
- `0x140031c44`
- `0x140031d54`
- `0x140031f38`
- `0x140033068`
- `0x140034010`

## pseudocode

```c
__int64 __fastcall CmpValidateHiveSecurityDescriptors(__int64 a1, unsigned int a2, _BYTE *a3, __int64 a4, __int64 a5)
{
  __int64 v6; // rdi
  __int64 v7; // rcx
  int v8; // ecx
  __int64 v9; // rdx
  __int64 CellFlat; // rax
  __int64 v11; // r13
  unsigned int v12; // r15d
  unsigned int v13; // r12d
  char IsCellAllocated; // al
  int v15; // r14d
  __int64 v16; // rax
  _DWORD *v17; // r12
  unsigned int v18; // eax
  __int64 v19; // rdx
  int v20; // eax
  int v21; // r9d
  __int64 v22; // rax
  unsigned int v23; // ecx
  void *v24; // rax
  void *v25; // rdi
  unsigned int v26; // r11d
  __int64 v27; // rdx
  __int64 CellPaged; // rax
  __int64 v29; // r15
  unsigned int v30; // r12d
  __int64 v31; // rdx
  int v32; // eax
  __int64 v33; // rcx
  int v35; // [rsp+20h] [rbp-28h]
  int v36; // [rsp+30h] [rbp-18h]
  _BYTE v37[4]; // [rsp+38h] [rbp-10h] BYREF
  _BYTE v38[12]; // [rsp+3Ch] [rbp-Ch] BYREF
  unsigned int v39; // [rsp+90h] [rbp+48h] BYREF
  char v40; // [rsp+94h] [rbp+4Ch] BYREF
  unsigned int v41; // [rsp+98h] [rbp+50h] BYREF
  _BYTE *v42; // [rsp+A0h] [rbp+58h]
  __int64 v43; // [rsp+A8h] [rbp+60h]

  v43 = a4;
  v42 = a3;
  v41 = a2;
  v6 = a4;
  HvpGetBinContextInitialize(&v40);
  HvpGetBinContextInitialize(v38);
  CmpInitSecurityCache(a1);
  v36 = *(_DWORD *)(a1 + 1888);
  if ( !(unsigned __int8)HvIsCellAllocated(v7, *(unsigned int *)(*(_QWORD *)(a1 + 64) + 36LL), 0) )
  {
    v8 = a5;
    if ( a5 )
      *(_DWORD *)(a5 + 240) = *(_DWORD *)(*(_QWORD *)(a1 + 64) + 36LL);
    v35 = 0;
    goto LABEL_71;
  }
  v9 = *(unsigned int *)(*(_QWORD *)(a1 + 64) + 36LL);
  if ( (*(_BYTE *)(a1 + 140) & 1) != 0 )
    CellFlat = HvpGetCellFlat(a1, v9, &v39);
  else
    CellFlat = HvpGetCellPaged(a1, v9, &v39);
  v11 = CellFlat;
  if ( !CellFlat )
  {
    v8 = a5;
    if ( a5 )
      *(_DWORD *)(a5 + 240) = *(_DWORD *)(*(_QWORD *)(a1 + 64) + 36LL);
    v35 = 16;
    goto LABEL_71;
  }
  if ( -4 - *(_DWORD *)(CellFlat - 4) < 76 )
  {
    v8 = a5;
    if ( a5 )
      *(_DWORD *)(a5 + 240) = *(_DWORD *)(*(_QWORD *)(a1 + 64) + 36LL);
    v35 = 24;
LABEL_71:
    v21 = -1073741492;
LABEL_72:
    SetFailureLocation(v8, 0, 9, v21, v35);
    return v26;
  }
  v12 = *(_DWORD *)(CellFlat + 44);
  v13 = v12;
  v39 = v12;
  v41 = 0;
  while ( 1 )
  {
    IsCellAllocated = HvIsCellAllocated(a1, v12, v6);
    v15 = a5;
    if ( !IsCellAllocated )
    {
      if ( v13 == v12 )
      {
        v35 = 128;
      }
      else
      {
LABEL_50:
        if ( !(unsigned __int8)HvIsCellAllocated(a1, *(unsigned int *)(v11 + 44), 0) )
        {
          v35 = 32;
          goto LABEL_70;
        }
        v27 = *(unsigned int *)(v11 + 44);
        if ( (*(_BYTE *)(a1 + 140) & 1) != 0 )
          CellPaged = HvpGetCellFlat(a1, v27, v37);
        else
          CellPaged = HvpGetCellPaged(a1, v27, v37);
        v29 = CellPaged;
        if ( CellPaged )
        {
          v30 = -4 - *(_DWORD *)(CellPaged - 4);
          if ( v30 < 0x14
            || (v31 = *(unsigned int *)(CellPaged + 16), (int)v31 + 20 < (unsigned int)v31)
            || (int)v31 + 20 > v30 )
          {
            v35 = 80;
          }
          else
          {
            if ( (unsigned __int8)((__int64 (__fastcall *)(__int64, __int64, _QWORD))ORValidRelativeSecurityDescriptor)(
                                    CellPaged + 20,
                                    v31,
                                    0) )
            {
              v20 = HvpAdjustHiveFreeDisplay();
              if ( v20 >= 0 )
              {
                v32 = *(_DWORD *)(v11 + 44);
                *(_DWORD *)(v29 + 8) = v32;
                *(_DWORD *)(v29 + 4) = v32;
                CmpDestroySecurityCache(a1);
                CmpInitSecurityCache(a1);
                v26 = -1073741267;
                v33 = *(_QWORD *)(a1 + 64);
                *v42 = 1;
                *(_DWORD *)(v33 + 4088) |= 4u;
                return v26;
              }
              v35 = 96;
              goto LABEL_31;
            }
            v35 = 64;
          }
        }
        else
        {
          v35 = 48;
        }
      }
LABEL_70:
      v8 = v15;
      goto LABEL_71;
    }
    if ( (*(_BYTE *)(a1 + 140) & 1) != 0 )
      v16 = HvpGetCellFlat(a1, v12, v37);
    else
      v16 = HvpGetCellPaged(a1, v12, v37);
    v17 = (_DWORD *)v16;
    if ( !v16 )
    {
      v35 = 144;
      goto LABEL_70;
    }
    v18 = -4 - *(_DWORD *)(v16 - 4);
    if ( v18 < 0x14 || (v19 = (unsigned int)v17[4], (int)v19 + 20 < (unsigned int)v19) || (int)v19 + 20 > v18 )
    {
      SetFailureLocation(v15, 1, 9, -1073741492, 152);
      goto LABEL_50;
    }
    if ( v12 != v39 && v17[2] != v41 )
    {
      v35 = 160;
      goto LABEL_70;
    }
    if ( !(unsigned __int8)((__int64 (__fastcall *)(_DWORD *, __int64, _QWORD))ORValidRelativeSecurityDescriptor)(
                             v17 + 5,
                             v19,
                             0) )
    {
      SetFailureLocation(v15, 1, 9, -1073741492, 168);
      goto LABEL_50;
    }
    if ( v36 )
    {
      v41 = 0;
      if ( !(unsigned __int8)CmpFindSecurityCellCacheIndex(a1, v12, &v41) )
      {
        v35 = 184;
        v21 = -1073741275;
        goto LABEL_32;
      }
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 1904) + 16LL * v41 + 8) + 28LL) = 0;
    }
    else
    {
      v20 = CmpAddSecurityCellToCache(a1, v12);
      if ( v20 < 0 )
      {
        v35 = 176;
LABEL_31:
        v21 = v20;
LABEL_32:
        v8 = v15;
        goto LABEL_72;
      }
    }
    v41 = v12;
    v12 = v17[1];
    v13 = v39;
    if ( v12 == v39 )
      break;
    v6 = v43;
  }
  if ( (*(_BYTE *)(a1 + 140) & 1) != 0 )
    v22 = HvpGetCellFlat(a1, v12, v37);
  else
    v22 = HvpGetCellPaged(a1, v12, v37);
  if ( *(_DWORD *)(v22 + 8) != v41 )
  {
    v35 = 200;
    goto LABEL_70;
  }
  if ( !v36 )
  {
    v23 = *(_DWORD *)(a1 + 1888);
    if ( v23 < *(_DWORD *)(a1 + 1892) )
    {
      v24 = (void *)(*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(a1 + 24))(16 * v23, 0, 1666403651);
      v25 = v24;
      if ( v24 )
      {
        memcpy_0(v24, *(const void **)(a1 + 1904), 16LL * *(unsigned int *)(a1 + 1888));
        (*(void (__fastcall **)(_QWORD, _QWORD))(a1 + 32))(
          *(_QWORD *)(a1 + 1904),
          (unsigned int)(16 * *(_DWORD *)(a1 + 1892)));
        *(_DWORD *)(a1 + 1892) = *(_DWORD *)(a1 + 1888);
        *(_QWORD *)(a1 + 1904) = v25;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140031f38  mov     [rsp-40h+arg_18], r9
0x140031f3d  mov     [rsp-40h+arg_10], r8
0x140031f42  mov     [rsp-40h+arg_8], edx
0x140031f46  push    rbp
0x140031f47  push    rbx
0x140031f48  push    rsi
0x140031f49  push    rdi
0x140031f4a  push    r12
0x140031f4c  push    r13
0x140031f4e  push    r14
0x140031f50  push    r15
0x140031f52  mov     rbp, rsp
0x140031f55  sub     rsp, 48h
0x140031f59  mov     rbx, rcx
0x140031f5c  mov     rdi, r9
0x140031f5f  lea     rcx, [rbp+arg_4]
0x140031f63  call    HvpGetBinContextInitialize
0x140031f68  lea     rcx, [rbp+var_C]
0x140031f6c  call    HvpGetBinContextInitialize
0x140031f71  mov     rcx, rbx
0x140031f74  call    CmpInitSecurityCache
0x140031f79  mov     rdx, [rbx+40h]
0x140031f7d  xor     r8d, r8d
0x140031f80  mov     eax, [rbx+760h]
0x140031f86  mov     [rbp+var_18], eax
0x140031f89  mov     edx, [rdx+24h]
0x140031f8c  call    HvIsCellAllocated
0x140031f91  test    al, al
0x140031f93  jnz     short loc_140031FC3
0x140031f95  mov     rcx, [rbp+arg_20]
0x140031f99  test    rcx, rcx
0x140031f9c  jz      short loc_140031FAB
0x140031f9e  mov     rax, [rbx+40h]
0x140031fa2  mov     edx, [rax+24h]
0x140031fa5  mov     [rcx+0F0h], edx
0x140031fab  mov     [rsp+48h+var_28], 0
0x140031fb3  mov     edi, 0C000014Ch
0x140031fb8  mov     r8d, 9
0x140031fbe  jmp     loc_140032385
0x140031fc3  test    byte ptr [rbx+8Ch], 1
0x140031fca  lea     r8, [rbp+arg_0]
0x140031fce  mov     rax, [rbx+40h]
0x140031fd2  mov     rcx, rbx
0x140031fd5  mov     edx, [rax+24h]
0x140031fd8  jz      short loc_140031FE1
0x140031fda  call    HvpGetCellFlat
0x140031fdf  jmp     short loc_140031FE6
0x140031fe1  call    HvpGetCellPaged
0x140031fe6  mov     r13, rax
0x140031fe9  test    rax, rax
0x140031fec  jnz     short loc_14003200E
0x140031fee  mov     rcx, [rbp+arg_20]
0x140031ff2  test    rcx, rcx
0x140031ff5  jz      short loc_140032004
0x140031ff7  mov     rax, [rbx+40h]
0x140031ffb  mov     edx, [rax+24h]
0x140031ffe  mov     [rcx+0F0h], edx
0x140032004  mov     [rsp+48h+var_28], 10h
0x14003200c  jmp     short loc_140031FB3
0x14003200e  mov     eax, 0FFFFFFFCh
0x140032013  sub     eax, [r13-4]
0x140032017  cmp     eax, 4Ch ; 'L'
0x14003201a  jge     short loc_14003203F
0x14003201c  mov     rcx, [rbp+arg_20]
0x140032020  test    rcx, rcx
0x140032023  jz      short loc_140032032
0x140032025  mov     rax, [rbx+40h]
0x140032029  mov     edx, [rax+24h]
0x14003202c  mov     [rcx+0F0h], edx
0x140032032  mov     [rsp+48h+var_28], 18h
0x14003203a  jmp     loc_140031FB3
0x14003203f  mov     r15d, [r13+2Ch]
0x140032043  mov     r12d, r15d
0x140032046  mov     [rbp+arg_0], r15d
0x14003204a  mov     [rbp+arg_8], 0
0x140032051  mov     r8, rdi
0x140032054  mov     edx, r15d
0x140032057  mov     rcx, rbx
0x14003205a  call    HvIsCellAllocated
0x14003205f  mov     r14, [rbp+arg_20]
0x140032063  mov     edi, 0C000014Ch
0x140032068  mov     esi, 9
0x14003206d  test    al, al
0x14003206f  jz      loc_14003229C
0x140032075  test    byte ptr [rbx+8Ch], 1
0x14003207c  lea     r8, [rbp+var_10]
0x140032080  mov     edx, r15d
0x140032083  mov     rcx, rbx
0x140032086  jz      short loc_14003208F
0x140032088  call    HvpGetCellFlat
0x14003208d  jmp     short loc_140032094
0x14003208f  call    HvpGetCellPaged
0x140032094  mov     r12, rax
0x140032097  test    rax, rax
0x14003209a  jz      loc_14003228F
0x1400320a0  mov     eax, 0FFFFFFFCh
0x1400320a5  sub     eax, [r12-4]
0x1400320aa  cmp     eax, 14h
0x1400320ad  jb      loc_140032285
0x1400320b3  mov     edx, [r12+10h]
0x1400320b8  lea     ecx, [rdx+14h]
0x1400320bb  cmp     ecx, edx
0x1400320bd  jb      loc_140032285
0x1400320c3  cmp     ecx, eax
0x1400320c5  ja      loc_140032285
0x1400320cb  cmp     r15d, [rbp+arg_0]
0x1400320cf  jz      short loc_1400320DF
0x1400320d1  mov     ecx, [rbp+arg_8]
0x1400320d4  cmp     [r12+8], ecx
0x1400320d9  jnz     loc_140032175
0x1400320df  mov     rax, cs:ORValidRelativeSecurityDescriptor
0x1400320e6  lea     rcx, [r12+14h]
0x1400320eb  xor     r8d, r8d
0x1400320ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400320f3  test    al, al
0x1400320f5  jz      loc_14003224A
0x1400320fb  cmp     [rbp+var_18], 0
0x1400320ff  mov     edx, r15d
0x140032102  mov     rcx, rbx
0x140032105  jnz     short loc_140032129
0x140032107  call    CmpAddSecurityCellToCache
0x14003210c  mov     r11d, eax
0x14003210f  test    eax, eax
0x140032111  jns     short loc_14003215A
0x140032113  mov     [rsp+48h+var_28], 0B0h
0x14003211b  mov     r9d, eax
0x14003211e  mov     r8d, esi
0x140032121  mov     rcx, r14
0x140032124  jmp     loc_14003238B
0x140032129  lea     r8, [rbp+arg_8]
0x14003212d  mov     [rbp+arg_8], 0
0x140032134  call    CmpFindSecurityCellCacheIndex
0x140032139  test    al, al
0x14003213b  jz      loc_140032234
0x140032141  mov     rax, [rbx+770h]
0x140032148  mov     ecx, [rbp+arg_8]
0x14003214b  add     rcx, rcx
0x14003214e  mov     rcx, [rax+rcx*8+8]
0x140032153  mov     dword ptr [rcx+1Ch], 0
0x14003215a  mov     [rbp+arg_8], r15d
0x14003215e  mov     r15d, [r12+4]
0x140032163  mov     r12d, [rbp+arg_0]
0x140032167  cmp     r15d, r12d
0x14003216a  jz      short loc_140032182
0x14003216c  mov     rdi, [rbp+arg_18]
0x140032170  jmp     loc_140032051
0x140032175  mov     [rsp+48h+var_28], 0A0h
0x14003217d  jmp     loc_14003237F
0x140032182  test    byte ptr [rbx+8Ch], 1
0x140032189  lea     r8, [rbp+var_10]
0x14003218d  mov     edx, r15d
0x140032190  mov     rcx, rbx
0x140032193  jz      short loc_14003219C
0x140032195  call    HvpGetCellFlat
0x14003219a  jmp     short loc_1400321A1
0x14003219c  call    HvpGetCellPaged
0x1400321a1  mov     ecx, [rbp+arg_8]
0x1400321a4  cmp     [rax+8], ecx
0x1400321a7  jz      short loc_1400321B6
0x1400321a9  mov     [rsp+48h+var_28], 0C8h
0x1400321b1  jmp     loc_14003237F
0x1400321b6  cmp     [rbp+var_18], 0
0x1400321ba  jnz     short loc_14003222C
0x1400321bc  mov     ecx, [rbx+760h]
0x1400321c2  cmp     ecx, [rbx+764h]
0x1400321c8  jnb     short loc_14003222C
0x1400321ca  mov     rax, [rbx+18h]
0x1400321ce  xor     edx, edx
0x1400321d0  shl     ecx, 4
0x1400321d3  mov     r8d, 63534D43h
0x1400321d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400321de  mov     rdi, rax
0x1400321e1  test    rax, rax
0x1400321e4  jz      short loc_14003222C
0x1400321e6  mov     r8d, [rbx+760h]
0x1400321ed  mov     rcx, rax; void *
0x1400321f0  mov     rdx, [rbx+770h]; Src
0x1400321f7  shl     r8, 4; Size
0x1400321fb  call    memcpy_0
0x140032200  mov     edx, [rbx+764h]
0x140032206  mov     rcx, [rbx+770h]
0x14003220d  mov     rax, [rbx+20h]
0x140032211  shl     edx, 4
0x140032214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032219  mov     eax, [rbx+760h]
0x14003221f  mov     [rbx+764h], eax
0x140032225  mov     [rbx+770h], rdi
0x14003222c  xor     r11d, r11d
0x14003222f  jmp     loc_140032392
0x140032234  mov     r11d, 0C0000225h
0x14003223a  mov     [rsp+48h+var_28], 0B8h
0x140032242  mov     r9d, r11d
0x140032245  jmp     loc_14003211E
0x14003224a  mov     [rsp+48h+var_28], 0A8h
0x140032252  mov     r9d, edi
0x140032255  mov     r8d, esi
0x140032258  mov     edx, 1
0x14003225d  mov     rcx, r14
0x140032260  call    SetFailureLocation
0x140032265  mov     edx, [r13+2Ch]
0x140032269  xor     r8d, r8d
0x14003226c  mov     rcx, rbx
0x14003226f  call    HvIsCellAllocated
0x140032274  test    al, al
0x140032276  jnz     short loc_1400322AE
0x140032278  mov     [rsp+48h+var_28], 20h ; ' '
0x140032280  jmp     loc_14003237F
0x140032285  mov     [rsp+48h+var_28], 98h
0x14003228d  jmp     short loc_140032252
0x14003228f  mov     [rsp+48h+var_28], 90h
0x140032297  jmp     loc_14003237F
0x14003229c  cmp     r12d, r15d
0x14003229f  jnz     short loc_140032265
0x1400322a1  mov     [rsp+48h+var_28], 80h
0x1400322a9  jmp     loc_14003237F
0x1400322ae  test    byte ptr [rbx+8Ch], 1
0x1400322b5  lea     r8, [rbp+var_10]
0x1400322b9  mov     edx, [r13+2Ch]
0x1400322bd  mov     rcx, rbx
0x1400322c0  jz      short loc_1400322C9
0x1400322c2  call    HvpGetCellFlat
0x1400322c7  jmp     short loc_1400322CE
0x1400322c9  call    HvpGetCellPaged
0x1400322ce  mov     r15, rax
0x1400322d1  test    rax, rax
0x1400322d4  jnz     short loc_1400322E3
0x1400322d6  mov     [rsp+48h+var_28], 30h ; '0'
0x1400322de  jmp     loc_14003237F
0x1400322e3  mov     r12d, 0FFFFFFFCh
0x1400322e9  sub     r12d, [r15-4]
0x1400322ed  cmp     r12d, 14h
0x1400322f1  jb      loc_140032377
0x1400322f7  mov     edx, [r15+10h]
0x1400322fb  lea     eax, [rdx+14h]
0x1400322fe  cmp     eax, edx
0x140032300  jb      short loc_140032377
0x140032302  cmp     eax, r12d
0x140032305  ja      short loc_140032377
0x140032307  mov     rax, cs:ORValidRelativeSecurityDescriptor
0x14003230e  lea     rcx, [r15+14h]
0x140032312  xor     r8d, r8d
0x140032315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003231a  test    al, al
0x14003231c  jnz     short loc_140032328
0x14003231e  mov     [rsp+48h+var_28], 40h ; '@'
0x140032326  jmp     short loc_14003237F
0x140032328  call    HvpAdjustHiveFreeDisplay
0x14003232d  mov     r11d, eax
0x140032330  test    eax, eax
0x140032332  jns     short loc_140032341
0x140032334  mov     [rsp+48h+var_28], 60h ; '`'
0x14003233c  jmp     loc_14003211B
0x140032341  mov     eax, [r13+2Ch]
0x140032345  mov     rcx, rbx
0x140032348  mov     [r15+8], eax
0x14003234c  mov     [r15+4], eax
0x140032350  call    CmpDestroySecurityCache
0x140032355  mov     rcx, rbx
0x140032358  call    CmpInitSecurityCache
0x14003235d  mov     rax, [rbp+arg_10]
0x140032361  mov     r11d, 0C000022Dh
0x140032367  mov     rcx, [rbx+40h]
0x14003236b  mov     byte ptr [rax], 1
0x14003236e  or      dword ptr [rcx+0FF8h], 4
0x140032375  jmp     short loc_140032392
0x140032377  mov     [rsp+48h+var_28], 50h ; 'P'
0x14003237f  mov     rcx, r14
0x140032382  mov     r8d, esi
0x140032385  mov     r11d, edi
0x140032388  mov     r9d, edi
0x14003238b  xor     edx, edx
0x14003238d  call    SetFailureLocation
0x140032392  mov     eax, r11d
0x140032395  add     rsp, 48h
0x140032399  pop     r15
0x14003239b  pop     r14
0x14003239d  pop     r13
0x14003239f  pop     r12
0x1400323a1  pop     rdi
0x1400323a2  pop     rsi
0x1400323a3  pop     rbx
0x1400323a4  pop     rbp
0x1400323a5  retn
```
