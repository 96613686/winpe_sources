# MountMgrQueryVolumePaths

- ea: `0x140013e70`
- end: `0x140014490`
- name: `MountMgrQueryVolumePaths`
- size: `1568`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *, int **, _DWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140013a20`
- `0x140013e70`

## callees

- `0x140001ae0`
- `0x140001b30`
- `0x140002f80`
- `0x140010ef0`
- `0x140012df0`
- `0x140013e70`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001402f`
- `ntoskrnl!ExAllocatePool2` at `0x140014147`
- `ntoskrnl!ExAllocatePool2` at `0x14001402f`
- `ntoskrnl!ExAllocatePool2` at `0x140014147`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014216`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001422e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014216`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001422e`

## pseudocode

```c
__int64 __fastcall MountMgrQueryVolumePaths(__int64 a1, _QWORD *a2, _QWORD *a3, int **a4, _DWORD *a5, _QWORD *a6)
{
  __int64 *v7; // r8
  __int64 *v9; // rdx
  __int64 v10; // r9
  __int64 *v11; // r10
  int VolumePaths; // r14d
  int v13; // r13d
  _WORD *v14; // rax
  _QWORD *v15; // rax
  __int64 *v16; // rbx
  _QWORD *v17; // rax
  _QWORD *v18; // rsi
  unsigned int v19; // ecx
  _QWORD *v20; // rax
  __int64 v21; // rax
  __int64 v22; // r12
  _QWORD *v23; // r9
  int *Pool2; // rax
  int *v25; // rdi
  __int64 v26; // rax
  PVOID *v27; // rcx
  int **v28; // rax
  _DWORD *v29; // rcx
  PVOID *v30; // rcx
  _QWORD *v31; // rcx
  _QWORD **v32; // rdx
  __int64 result; // rax
  __int64 v34; // r8
  __int64 v35; // rdx
  PDEVICE_OBJECT v36; // rcx
  __int64 v37; // rdx
  unsigned int i; // ebx
  _QWORD *v39; // r13
  int v40; // r10d
  unsigned int *v41; // rdx
  char *v42; // r12
  __int64 v43; // r15
  unsigned int *v44; // r8
  __int64 v45; // rcx
  char *v46; // r9
  int j; // [rsp+30h] [rbp-50h]
  unsigned int v48; // [rsp+34h] [rbp-4Ch]
  PVOID *P; // [rsp+38h] [rbp-48h]
  _QWORD *v50; // [rsp+40h] [rbp-40h]
  __int64 v51; // [rsp+48h] [rbp-38h]
  __int64 v52; // [rsp+50h] [rbp-30h]
  _QWORD *v53; // [rsp+58h] [rbp-28h] BYREF
  _QWORD **v54; // [rsp+60h] [rbp-20h]
  _QWORD *v55; // [rsp+68h] [rbp-18h]
  char *v57; // [rsp+C8h] [rbp+48h] BYREF
  int v58; // [rsp+D0h] [rbp+50h] BYREF
  int **v59; // [rsp+D8h] [rbp+58h]

  v59 = a4;
  v54 = &v53;
  v7 = a2 + 2;
  v55 = 0;
  v48 = 0;
  v53 = &v53;
  v9 = (__int64 *)a2[2];
  v10 = a1;
  v11 = 0;
  P = 0;
  VolumePaths = 0;
  v58 = 0;
  v13 = 2;
  while ( v9 != v7 )
  {
    v11 = v9;
    if ( *((_WORD *)v9 + 12) == 28 )
    {
      v14 = (_WORD *)v9[4];
      if ( *v14 == 92
        && v14[1] == 68
        && v14[2] == 111
        && v14[3] == 115
        && v14[4] == 68
        && v14[5] == 101
        && v14[6] == 118
        && v14[7] == 105
        && v14[8] == 99
        && v14[9] == 101
        && v14[10] == 115
        && v14[11] == 92
        && (unsigned __int16)(v14[12] - 65) <= 0x19u
        && v14[13] == 58
        && *((_BYTE *)v9 + 16) )
      {
        v13 = 8;
        break;
      }
    }
    v9 = (__int64 *)*v9;
  }
  v15 = (_QWORD *)*a3;
  v16 = 0;
  if ( v9 != v7 )
    v16 = v11;
  if ( v15 != a3 )
  {
    while ( (_QWORD *)v15[2] != a2 )
    {
      v15 = (_QWORD *)*v15;
      if ( v15 == a3 )
        goto LABEL_23;
    }
    v18 = a2 + 6;
LABEL_27:
    Pool2 = (int *)ExAllocatePool2(258, (unsigned int)(v13 + 4), 1098149453);
    v25 = Pool2;
    if ( Pool2 )
    {
      *Pool2 = v13;
      v58 = 0;
      if ( v16 )
      {
        v26 = v16[4];
        v18 = a2 + 6;
        LODWORD(v16) = 3;
        *((_WORD *)v25 + 2) = *(_WORD *)(v26 + 24);
        *(int *)((char *)v25 + 6) = 58;
        ++v58;
      }
      else
      {
        LODWORD(v16) = 0;
      }
      v27 = P;
      if ( P )
      {
        v39 = (_QWORD *)*v18;
        v40 = 0;
        for ( LODWORD(v57) = 0; v39 != v18; LODWORD(v57) = v40 )
        {
          v41 = (unsigned int *)v27[v40];
          v42 = (char *)&v27[v40];
          if ( (unsigned __int64)*v41 >> 1 != 1 )
          {
            v43 = 0;
            v44 = (unsigned int *)v27[v40];
            do
            {
              v45 = 2 * v43 + 4;
              v46 = (char *)v25 + 2 * (unsigned int)v16;
              if ( *(_WORD *)((char *)v41 + v45) )
              {
                *((_WORD *)v46 + 2) = *(_WORD *)((char *)v44 + v45);
              }
              else
              {
                memmove(v46 + 4, (const void *)v39[4], *((unsigned __int16 *)v39 + 12));
                v16 = (__int64 *)((*((unsigned __int16 *)v39 + 12) >> 1) + (int)v16);
                *((_WORD *)v25 + (_QWORD)v16 + 2) = 0;
                ++v58;
              }
              v41 = *(unsigned int **)v42;
              v43 = (unsigned int)(v43 + 1);
              LODWORD(v16) = (_DWORD)v16 + 1;
              v44 = *(unsigned int **)v42;
            }
            while ( (unsigned int)v43 < ((unsigned __int64)**(unsigned int **)v42 >> 1) - 1 );
            v27 = P;
            v40 = (int)v57;
          }
          v39 = (_QWORD *)*v39;
          ++v40;
        }
      }
      v28 = v59;
      *((_WORD *)v25 + (unsigned int)v16 + 2) = 0;
      v29 = a5;
      *v28 = v25;
      *v29 = v58;
    }
    else
    {
      VolumePaths = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 312);
    }
LABEL_33:
    v30 = P;
    if ( P )
    {
      for ( i = 0; i < v48; ++i )
      {
        if ( v30[i] )
        {
          ExFreePoolWithTag(v30[i], 0);
          v30 = P;
        }
      }
      ExFreePoolWithTag(v30, 0);
    }
    goto LABEL_34;
  }
LABEL_23:
  v17 = (_QWORD *)a2[6];
  v18 = a2 + 6;
  v19 = 0;
  v48 = 0;
  if ( v17 == a2 + 6 )
    goto LABEL_24;
  do
  {
    v17 = (_QWORD *)*v17;
    ++v19;
  }
  while ( v17 != v18 );
  v48 = v19;
  if ( !v19 )
  {
LABEL_24:
    v20 = (_QWORD *)a3[1];
    v55 = a2;
    if ( (_QWORD *)*v20 != a3 )
      goto LABEL_89;
    v54 = (_QWORD **)v20;
    v53 = a3;
    *v20 = &v53;
    a3[1] = &v53;
    v21 = *(_QWORD *)(v10 + 336);
    v22 = a2[22];
    v23 = (_QWORD *)*v18;
    v52 = v22;
    v51 = v21;
    for ( j = 0; ; ++j )
    {
      v50 = v23;
      if ( v23 == v18 )
        goto LABEL_27;
      LOBYTE(v57) = 0;
      VolumePaths = MountMgrValidateBackPointer(v23, a2, &v57);
      if ( (int)VerifyEpoch(a1, v51, v22) < 0 )
      {
        VolumePaths = -1073741267;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 308, v34, 3221226029LL);
          goto LABEL_49;
        }
        goto LABEL_33;
      }
      if ( VolumePaths == -1073741810 )
        goto LABEL_48;
      if ( VolumePaths < 0 )
        goto LABEL_49;
      v35 = v50[2];
      if ( (_BYTE)v57 )
      {
        *a6 = v35;
LABEL_48:
        VolumePaths = -1073741267;
LABEL_49:
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          v37 = 309;
LABEL_52:
          WPP_SF_L(v36->AttachedDevice, v37, v34, (unsigned int)VolumePaths);
          goto LABEL_33;
        }
        goto LABEL_33;
      }
      v57 = (char *)&P[j];
      VolumePaths = MountMgrQueryVolumePaths(a1, v35, (_DWORD)a3, (int)P + 8 * j, (__int64)&v58, (__int64)a6);
      if ( (int)VerifyEpoch(a1, v51, v52) < 0 )
        break;
      if ( VolumePaths < 0 )
        goto LABEL_74;
      v22 = v52;
      v23 = (_QWORD *)*v50;
      v13 += **(_DWORD **)v57 + v58 * *((unsigned __int16 *)v50 + 12) - 2;
    }
    VolumePaths = -1073741267;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 310, v34, 3221226029LL);
LABEL_74:
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v37 = 311;
        goto LABEL_52;
      }
    }
    goto LABEL_33;
  }
  P = (PVOID *)ExAllocatePool2(256, 8 * v19, 1098149453);
  if ( P )
  {
    v10 = a1;
    goto LABEL_24;
  }
  VolumePaths = -1073741670;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 307);
LABEL_34:
  v31 = v53;
  if ( (_QWORD **)v53[1] != &v53 || (v32 = v54, *v54 != &v53) )
LABEL_89:
    __fastfail(3u);
  result = (unsigned int)VolumePaths;
  *v54 = v53;
  v31[1] = v32;
  return result;
}

```

## disassembly

```asm
0x140013e70  mov     [rsp-38h+arg_18], r9
0x140013e75  mov     [rsp-38h+arg_0], rcx
0x140013e7a  push    rbp
0x140013e7b  push    rbx
0x140013e7c  push    rdi
0x140013e7d  push    r12
0x140013e7f  push    r13
0x140013e81  push    r14
0x140013e83  push    r15
0x140013e85  mov     rbp, rsp
0x140013e88  sub     rsp, 80h
0x140013e8f  xor     r12d, r12d
0x140013e92  lea     rax, [rbp+var_28]
0x140013e96  mov     [rbp+var_20], rax
0x140013e9a  mov     rdi, r8
0x140013e9d  lea     r8, [rdx+10h]
0x140013ea1  mov     [rbp+var_18], r12
0x140013ea5  lea     rax, [rbp+var_28]
0x140013ea9  mov     [rbp+var_4C], r12d
0x140013ead  mov     r15, rdx
0x140013eb0  mov     [rbp+var_28], rax
0x140013eb4  mov     rdx, [r8]
0x140013eb7  mov     r9, rcx
0x140013eba  mov     r10d, r12d
0x140013ebd  mov     [rbp+P], r12
0x140013ec1  mov     r14d, r12d
0x140013ec4  mov     [rbp+arg_10], r12d
0x140013ec8  mov     r13d, 2
0x140013ece  cmp     rdx, r8
0x140013ed1  jz      loc_140013F99
0x140013ed7  cmp     word ptr [rdx+18h], 1Ch
0x140013edc  mov     r10, rdx
0x140013edf  jnz     loc_14001410C
0x140013ee5  mov     rax, [rdx+20h]
0x140013ee9  cmp     word ptr [rax], 5Ch ; '\'
0x140013eed  jnz     loc_14001410C
0x140013ef3  cmp     word ptr [rax+2], 44h ; 'D'
0x140013ef8  jnz     loc_14001410C
0x140013efe  cmp     word ptr [rax+4], 6Fh ; 'o'
0x140013f03  jnz     loc_14001410C
0x140013f09  cmp     word ptr [rax+6], 73h ; 's'
0x140013f0e  jnz     loc_14001410C
0x140013f14  cmp     word ptr [rax+8], 44h ; 'D'
0x140013f19  jnz     loc_14001410C
0x140013f1f  cmp     word ptr [rax+0Ah], 65h ; 'e'
0x140013f24  jnz     loc_14001410C
0x140013f2a  cmp     word ptr [rax+0Ch], 76h ; 'v'
0x140013f2f  jnz     loc_14001410C
0x140013f35  cmp     word ptr [rax+0Eh], 69h ; 'i'
0x140013f3a  jnz     loc_14001410C
0x140013f40  cmp     word ptr [rax+10h], 63h ; 'c'
0x140013f45  jnz     loc_14001410C
0x140013f4b  cmp     word ptr [rax+12h], 65h ; 'e'
0x140013f50  jnz     loc_14001410C
0x140013f56  cmp     word ptr [rax+14h], 73h ; 's'
0x140013f5b  jnz     loc_14001410C
0x140013f61  cmp     word ptr [rax+16h], 5Ch ; '\'
0x140013f66  jnz     loc_14001410C
0x140013f6c  movzx   ecx, word ptr [rax+18h]
0x140013f70  sub     cx, 41h ; 'A'
0x140013f74  cmp     cx, 19h
0x140013f78  ja      loc_14001410C
0x140013f7e  cmp     word ptr [rax+1Ah], 3Ah ; ':'
0x140013f83  jnz     loc_14001410C
0x140013f89  cmp     [rdx+10h], r12b
0x140013f8d  jz      loc_14001410C
0x140013f93  mov     r13d, 8
0x140013f99  mov     rax, [rdi]
0x140013f9c  cmp     rdx, r8
0x140013f9f  mov     rbx, r12
0x140013fa2  mov     [rsp+80h+var_8], rsi
0x140013fa7  cmovnz  rbx, r10
0x140013fab  cmp     rax, rdi
0x140013fae  jnz     loc_1400143E2
0x140013fb4  mov     rax, [r15+30h]
0x140013fb8  lea     rsi, [r15+30h]
0x140013fbc  mov     ecx, r12d
0x140013fbf  mov     [rbp+var_4C], ecx
0x140013fc2  cmp     rax, rsi
0x140013fc5  jnz     loc_140014120
0x140013fcb  mov     rax, [rdi+8]
0x140013fcf  mov     [rbp+var_18], r15
0x140013fd3  cmp     [rax], rdi
0x140013fd6  jnz     loc_140014489
0x140013fdc  mov     [rbp+var_20], rax
0x140013fe0  lea     rcx, [rbp+var_28]
0x140013fe4  mov     [rbp+var_28], rdi
0x140013fe8  mov     [rax], rcx
0x140013feb  lea     rax, [rbp+var_28]
0x140013fef  mov     [rdi+8], rax
0x140013ff3  mov     rax, [r9+150h]
0x140013ffa  mov     r12, [r15+0B0h]
0x140014001  mov     r9, [rsi]
0x140014004  mov     [rbp+var_30], r12
0x140014008  mov     [rbp+var_38], rax
0x14001400c  mov     [rbp+var_50], r14d
0x140014010  mov     [rbp+var_40], r9
0x140014014  cmp     r9, rsi
0x140014017  jnz     loc_140014169
0x14001401d  xor     r12d, r12d
0x140014020  lea     edx, [r13+4]
0x140014024  mov     ecx, 102h
0x140014029  mov     r8d, 41746E4Dh
0x14001402f  call    cs:__imp_ExAllocatePool2
0x140014036  nop     dword ptr [rax+rax+00h]
0x14001403b  mov     rdi, rax
0x14001403e  test    rax, rax
0x140014041  jz      short loc_140014099
0x140014043  mov     [rax], r13d
0x140014046  mov     [rbp+arg_10], r12d
0x14001404a  test    rbx, rbx
0x14001404d  jz      loc_140014114
0x140014053  mov     rax, [rbx+20h]
0x140014057  lea     rsi, [r15+30h]
0x14001405b  mov     ebx, 3
0x140014060  movzx   ecx, word ptr [rax+18h]
0x140014064  mov     [rdi+4], cx
0x140014068  mov     dword ptr [rdi+6], 3Ah ; ':'
0x14001406f  inc     [rbp+arg_10]
0x140014072  mov     rcx, [rbp+P]
0x140014076  test    rcx, rcx
0x140014079  jnz     loc_1400142C6
0x14001407f  mov     rax, [rbp+arg_18]
0x140014083  mov     ecx, ebx
0x140014085  mov     [rdi+rcx*2+4], r12w
0x14001408b  mov     rcx, [rbp+arg_20]
0x14001408f  mov     [rax], rdi
0x140014092  mov     eax, [rbp+arg_10]
0x140014095  mov     [rcx], eax
0x140014097  jmp     short loc_1400140B9
0x140014099  mov     r14d, 0C000009Ah
0x14001409f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400140a6  lea     r12, WPP_GLOBAL_Control
0x1400140ad  cmp     rcx, r12
0x1400140b0  jnz     loc_14001446B
0x1400140b6  xor     r12d, r12d
0x1400140b9  mov     rcx, [rbp+P]
0x1400140bd  test    rcx, rcx
0x1400140c0  jnz     loc_1400141FC
0x1400140c6  mov     rcx, [rbp+var_28]
0x1400140ca  lea     rax, [rbp+var_28]
0x1400140ce  cmp     [rcx+8], rax
0x1400140d2  jnz     loc_140014489
0x1400140d8  mov     rdx, [rbp+var_20]
0x1400140dc  lea     rax, [rbp+var_28]
0x1400140e0  cmp     [rdx], rax
0x1400140e3  jnz     loc_140014489
0x1400140e9  mov     rsi, [rsp+80h+var_8]
0x1400140ee  mov     eax, r14d
0x1400140f1  mov     [rdx], rcx
0x1400140f4  mov     [rcx+8], rdx
0x1400140f8  add     rsp, 80h
0x1400140ff  pop     r15
0x140014101  pop     r14
0x140014103  pop     r13
0x140014105  pop     r12
0x140014107  pop     rdi
0x140014108  pop     rbx
0x140014109  pop     rbp
0x14001410a  retn
0x14001410c  mov     rdx, [rdx]
0x14001410f  jmp     loc_140013ECE
0x140014114  mov     ebx, r12d
0x140014117  jmp     loc_140014072
0x140014120  mov     rax, [rax]
0x140014123  inc     ecx
0x140014125  cmp     rax, rsi
0x140014128  jnz     short loc_140014120
0x14001412a  mov     [rbp+var_4C], ecx
0x14001412d  test    ecx, ecx
0x14001412f  jz      loc_140013FCB
0x140014135  lea     edx, ds:0[rcx*8]
0x14001413c  mov     r8d, 41746E4Dh
0x140014142  mov     ecx, 100h
0x140014147  call    cs:__imp_ExAllocatePool2
0x14001414e  nop     dword ptr [rax+rax+00h]
0x140014153  mov     [rbp+P], rax
0x140014157  test    rax, rax
0x14001415a  jz      loc_140014382
0x140014160  mov     r9, [rbp+arg_0]
0x140014164  jmp     loc_140013FCB
0x140014169  lea     r8, [rbp+arg_8]
0x14001416d  mov     byte ptr [rbp+arg_8], 0
0x140014171  mov     rdx, r15
0x140014174  mov     rcx, r9
0x140014177  call    MountMgrValidateBackPointer
0x14001417c  mov     rdx, [rbp+var_38]
0x140014180  mov     r8, r12
0x140014183  mov     rcx, [rbp+arg_0]
0x140014187  mov     r14d, eax
0x14001418a  call    VerifyEpoch
0x14001418f  lea     r12, WPP_GLOBAL_Control
0x140014196  test    eax, eax
0x140014198  js      loc_140014431
0x14001419e  cmp     r14d, 0C000000Eh
0x1400141a5  jz      short loc_1400141C5
0x1400141a7  test    r14d, r14d
0x1400141aa  js      short loc_1400141CB
0x1400141ac  cmp     byte ptr [rbp+arg_8], 0
0x1400141b0  mov     rax, [rbp+var_40]
0x1400141b4  mov     rdx, [rax+10h]
0x1400141b8  jz      loc_14001423F
0x1400141be  mov     rax, [rbp+arg_28]
0x1400141c2  mov     [rax], rdx
0x1400141c5  mov     r14d, 0C000022Dh
0x1400141cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400141d2  cmp     rcx, r12
0x1400141d5  jz      loc_1400140B6
0x1400141db  mov     eax, [rcx+2Ch]
0x1400141de  test    al, 1
0x1400141e0  jz      loc_1400140B6
0x1400141e6  mov     edx, 135h
0x1400141eb  mov     rcx, [rcx+18h]
0x1400141ef  mov     r9d, r14d
0x1400141f2  call    WPP_SF_L
0x1400141f7  jmp     loc_1400140B6
0x1400141fc  mov     edi, [rbp+var_4C]
0x1400141ff  mov     ebx, r12d
0x140014202  test    edi, edi
0x140014204  jz      short loc_14001422C
0x140014206  mov     eax, ebx
0x140014208  mov     r8, [rcx+rax*8]
0x14001420c  test    r8, r8
0x14001420f  jz      short loc_140014226
0x140014211  xor     edx, edx; Tag
0x140014213  mov     rcx, r8; P
0x140014216  call    cs:__imp_ExFreePoolWithTag
0x14001421d  nop     dword ptr [rax+rax+00h]
0x140014222  mov     rcx, [rbp+P]; P
0x140014226  inc     ebx
0x140014228  cmp     ebx, edi
0x14001422a  jb      short loc_140014206
0x14001422c  xor     edx, edx; Tag
0x14001422e  call    cs:__imp_ExFreePoolWithTag
0x140014235  nop     dword ptr [rax+rax+00h]
0x14001423a  jmp     loc_1400140C6
0x14001423f  mov     eax, [rbp+var_50]
0x140014242  mov     r8, rdi
0x140014245  mov     rcx, [rbp+P]
0x140014249  lea     rcx, [rcx+rax*8]
0x14001424d  mov     rax, [rbp+arg_28]
0x140014251  mov     [rsp+80h+var_58], rax
0x140014256  mov     r9, rcx
0x140014259  lea     rax, [rbp+arg_10]
0x14001425d  mov     [rbp+arg_8], rcx
0x140014261  mov     rcx, [rbp+arg_0]
0x140014265  mov     [rsp+80h+var_60], rax
0x14001426a  call    MountMgrQueryVolumePaths
0x14001426f  mov     r8, [rbp+var_30]
0x140014273  mov     r14d, eax
0x140014276  mov     rdx, [rbp+var_38]
0x14001427a  mov     rcx, [rbp+arg_0]
0x14001427e  call    VerifyEpoch
0x140014283  lea     r12, WPP_GLOBAL_Control
0x14001428a  test    eax, eax
0x14001428c  js      loc_1400143FE
0x140014292  test    r14d, r14d
0x140014295  js      loc_1400143BD
0x14001429b  mov     r9, [rbp+var_40]
0x14001429f  mov     rax, [rbp+arg_8]
0x1400142a3  mov     r12, [rbp+var_30]
0x1400142a7  movzx   ecx, word ptr [r9+18h]
0x1400142ac  imul    ecx, [rbp+arg_10]
0x1400142b0  mov     rax, [rax]
0x1400142b3  mov     r9, [r9]
0x1400142b6  add     ecx, 0FFFFFFFEh
0x1400142b9  add     ecx, [rax]
0x1400142bb  add     r13d, ecx
0x1400142be  inc     [rbp+var_50]
0x1400142c1  jmp     loc_140014010
0x1400142c6  mov     r13, [rsi]
0x1400142c9  mov     r10d, r12d
0x1400142cc  mov     dword ptr [rbp+arg_8], r12d
0x1400142d0  cmp     r13, rsi
0x1400142d3  jz      loc_14001407F
0x1400142d9  mov     eax, r10d
0x1400142dc  mov     rdx, [rcx+rax*8]
0x1400142e0  lea     r12, [rcx+rax*8]
0x1400142e4  mov     eax, [rdx]
0x1400142e6  shr     rax, 1
0x1400142e9  cmp     rax, 1
0x1400142ed  jz      short loc_140014343
0x1400142ef  xor     r15d, r15d
0x1400142f2  mov     r8, rdx
0x1400142f5  nop     word ptr [rax+rax+00000000h]
0x140014300  mov     eax, ebx
0x140014302  lea     rcx, ds:4[r15*2]
0x14001430a  cmp     word ptr [rcx+rdx], 0
0x14001430f  lea     r9, [rdi+rax*2]
0x140014313  jz      short loc_14001435B
0x140014315  movzx   eax, word ptr [rcx+r8]
0x14001431a  mov     [r9+4], ax
0x14001431f  mov     rdx, [r12]
0x140014323  inc     r15d
0x140014326  inc     ebx
0x140014328  mov     eax, r15d
0x14001432b  mov     r8, rdx
0x14001432e  mov     ecx, [rdx]
0x140014330  shr     rcx, 1
0x140014333  dec     rcx
  ... truncated ...
```
