# CscEnpWrite

- ea: `0x1400074bc`
- end: `0x140007ff0`
- name: `CscEnpWrite`
- size: `2868`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1400053f8`

## callees

- `0x140006a00`
- `0x1400074bc`
- `0x1400169d4`
- `0x140018930`
- `0x1400190ec`
- `0x1400197a0`
- `0x14001a494`
- `0x140029140`
- `0x1400293a4`
- `0x14002f140`
- `0x14002f440`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400075f0`
- `ntoskrnl!ExAllocatePool2` at `0x1400075f0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140007866`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400078fb`
- `ntoskrnl!ExReleaseResourceLite` at `0x140007866`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400078fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000787f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000787f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140007665`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140007d19`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140007665`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140007d19`

## pseudocode

```c
__int64 __fastcall CscEnpWrite(__int64 a1, __int64 a2, unsigned int a3, char *a4, __int64 a5, unsigned int *a6)
{
  unsigned int v6; // r15d
  __int64 v7; // r14
  char *v8; // r12
  __int64 v9; // rbx
  __int64 v10; // r8
  __int64 v11; // rdi
  int v12; // esi
  int v13; // edi
  signed __int64 v14; // r13
  __int64 v15; // rax
  signed __int64 v16; // rsi
  char v17; // al
  int v18; // r15d
  unsigned __int64 v19; // rdi
  unsigned int v20; // esi
  __int64 v21; // r13
  unsigned int v22; // r15d
  __int64 v23; // rdi
  signed __int64 v24; // r15
  unsigned int Length; // edi
  __int64 v26; // r15
  void *v27; // rax
  unsigned int v28; // r15d
  unsigned int v29; // r9d
  PDEVICE_OBJECT v30; // rcx
  __int64 v31; // rdx
  unsigned int v32; // r15d
  int v34; // [rsp+20h] [rbp-60h]
  int v35; // [rsp+50h] [rbp-30h]
  int v36; // [rsp+54h] [rbp-2Ch]
  char *P; // [rsp+58h] [rbp-28h]
  struct _ERESOURCE *Resource; // [rsp+60h] [rbp-20h]
  signed __int64 v39; // [rsp+68h] [rbp-18h]
  signed __int64 v40; // [rsp+78h] [rbp-8h]
  __int64 v42; // [rsp+D0h] [rbp+50h] BYREF

  v6 = 0;
  v7 = a3;
  v35 = 0;
  v8 = a4;
  LODWORD(v42) = 0;
  v9 = a2;
  v10 = a1;
  v11 = a5;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
  {
    WPP_SF_qqiDqqq(WPP_GLOBAL_Control->AttachedDevice, 30, a1, a1, *(_QWORD *)(a1 + 8), a2, v7, a4, a5, a6);
    v10 = a1;
  }
  if ( !(_DWORD)v7 )
  {
    v12 = 0;
    v13 = 1084;
    goto LABEL_161;
  }
  if ( !v8 )
  {
    v12 = -1073740768;
    v13 = 1090;
    goto LABEL_161;
  }
  v14 = v7 + v9;
  v39 = v7 + v9;
  if ( v7 + v9 < v7 )
  {
    v12 = -1073741811;
    v13 = 1106;
    goto LABEL_161;
  }
  v15 = *(_QWORD *)(v10 + 8);
  v16 = *(_QWORD *)(v15 + 328);
  Resource = *(struct _ERESOURCE **)(v15 + 184);
  v40 = v16;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
  {
    v17 = 89;
    if ( !v11 )
      v17 = 78;
    LOBYTE(v34) = v17;
    WPP_SF_ici(WPP_GLOBAL_Control->AttachedDevice, 78, v10, v16, v34, v7 + v9);
  }
  P = (char *)ExAllocatePool2(66, 4096, 557871939, a4);
  if ( !P )
  {
    v12 = -1073741670;
    v13 = 1123;
    goto LABEL_161;
  }
  v18 = v9 & 0xFFF;
  v36 = v18;
  if ( (v9 & 0xFFF) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids, v9 & 0xFFF);
    }
    ExAcquireResourceExclusiveLite(Resource, 1u);
    memset(P, 0, 0x1000u);
    v19 = v9 & 0xFFFFFFFFFFFFF000uLL;
    if ( v16 && (__int64)(v9 & 0xFFFFFFFFFFFFF000uLL) < v16 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids);
      }
      v12 = CscStorepLowIoReadWriteFileIrpEx(
              *(PFILE_OBJECT *)(*(_QWORD *)(a1 + 8) + 176LL),
              0,
              1,
              v19,
              0x1000u,
              0x1000u,
              P,
              0,
              (unsigned int *)&v42);
      if ( v12 < 0 )
      {
        v13 = 1184;
LABEL_46:
        ExReleaseResourceLite(Resource);
        goto LABEL_47;
      }
      v20 = v42;
      if ( (unsigned int)v42 > 0x1000 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            34,
            WPP_ae3c48fed8b43b056afaf76937463504_Traceguids,
            (unsigned int)v42);
        }
        v12 = -1073740768;
        v13 = 1194;
        goto LABEL_46;
      }
    }
    else
    {
      v20 = 0;
    }
    v21 = (unsigned int)(4096 - v18);
    if ( (unsigned int)v7 < (unsigned int)v21 )
      v21 = (unsigned int)v7;
    memmove(&P[v9 & 0xFFF], v8, (unsigned int)v21);
    v22 = v21 + v18;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    {
      WPP_SF_DDd(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids, v20, v21, v22);
    }
    if ( v22 < v20 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids);
      }
      v22 = v20;
    }
    v12 = CscStorepLowIoReadWriteFileIrpEx(
            *(PFILE_OBJECT *)(*(_QWORD *)(a1 + 8) + 176LL),
            1u,
            1,
            v19,
            v22,
            0x1000u,
            P,
            0,
            (unsigned int *)&v42);
    if ( v12 < 0 )
    {
      v13 = 1251;
      goto LABEL_46;
    }
    if ( (_DWORD)v42 != v22 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          37,
          WPP_ae3c48fed8b43b056afaf76937463504_Traceguids,
          (unsigned int)v42,
          v22);
      }
      v12 = -1073740768;
      v13 = 1258;
      goto LABEL_46;
    }
    v35 = v21;
    if ( (_DWORD)v21 == (_DWORD)v7 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids);
      }
      v13 = 1271;
      goto LABEL_46;
    }
    v23 = v9 + v21;
    LODWORD(v7) = v7 - v21;
    v8 += (unsigned int)v21;
    v24 = v9 + v21;
    if ( v9 + v21 <= v40 )
      v24 = v40;
    ExReleaseResourceLite(Resource);
    v9 += v21;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    {
      WPP_SF_Dq(
        WPP_GLOBAL_Control->AttachedDevice,
        39,
        WPP_ae3c48fed8b43b056afaf76937463504_Traceguids,
        (unsigned int)v7,
        v23);
    }
    v14 = v39;
  }
  else
  {
    v24 = v16;
    v12 = 0;
  }
  Length = v7 & 0xFFFFF000;
  if ( ((unsigned __int16)v8 & 0xFFF) == 0 && v14 >= v24 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids);
    }
    Length = v7;
  }
  if ( Length < 0x1000 )
  {
LABEL_124:
    ExAcquireResourceExclusiveLite(Resource, 1u);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          53,
          WPP_ae3c48fed8b43b056afaf76937463504_Traceguids,
          (unsigned int)v7);
      }
    }
    memset(P, 0, 0x1000u);
    v12 = CscStorepLowIoReadWriteFileIrpEx(
            *(PFILE_OBJECT *)(*(_QWORD *)(a1 + 8) + 176LL),
            0,
            1,
            v9,
            0x1000u,
            0x1000u,
            P,
            0,
            (unsigned int *)&v42);
    if ( (int)(v12 + 0x80000000) < 0 || v12 == -1073741807 )
    {
      v32 = v42;
      if ( (unsigned int)v42 > 0x1000 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            54,
            WPP_ae3c48fed8b43b056afaf76937463504_Traceguids,
            (unsigned int)v42);
        }
        v12 = -1073740768;
        v13 = 1617;
      }
      else
      {
        v13 = 0;
        memmove(P, v8, (unsigned int)v7);
        if ( (unsigned int)v7 >= v32 )
        {
          v32 = v7;
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids);
        }
        if ( v32 )
        {
          v12 = CscStorepLowIoReadWriteFileIrpEx(
                  *(PFILE_OBJECT *)(*(_QWORD *)(a1 + 8) + 176LL),
                  1u,
                  1,
                  v9,
                  v32,
                  0x1000u,
                  P,
                  0,
                  (unsigned int *)&v42);
          if ( v12 >= 0 )
          {
            if ( (_DWORD)v42 == v32 )
            {
              v35 += v7;
            }
            else
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
              {
                WPP_SF_Dd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  56,
                  WPP_ae3c48fed8b43b056afaf76937463504_Traceguids,
                  (unsigned int)v42,
                  v32);
              }
              v12 = -1073740768;
              v13 = 1655;
            }
          }
          else
          {
            v13 = 1648;
          }
        }
      }
    }
    else
    {
      v13 = 1606;
    }
    goto LABEL_46;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids);
  if ( ((unsigned __int8)v8 & 3) == 0 )
  {
    v26 = a5;
    if ( !a5 || !v36 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids);
      }
      if ( v26 )
        v27 = *(void **)(v26 + 32);
      else
        v27 = v8;
      v12 = CscStorepLowIoReadWriteFileIrpEx(
              *(PFILE_OBJECT *)(*(_QWORD *)(a1 + 8) + 176LL),
              1u,
              0,
              v9,
              Length,
              Length,
              v27,
              v26,
              (unsigned int *)&v42);
      if ( v12 < 0 )
      {
        v13 = 1402;
        goto LABEL_47;
      }
      if ( (_DWORD)v42 != Length )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
        {
          WPP_SF_Dd(
            WPP_GLOBAL_Control->AttachedDevice,
            43,
            WPP_ae3c48fed8b43b056afaf76937463504_Traceguids,
            (unsigned int)v42,
            Length);
        }
        v12 = -1073740768;
        v13 = 1409;
        goto LABEL_47;
      }
      v6 = Length + v35;
      v35 += Length;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids, Length, v42);
      }
      if ( Length == (_DWORD)v7 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids);
        }
        v13 = 1426;
        goto LABEL_48;
      }
      LODWORD(v7) = v7 - Length;
      v9 += Length;
      v8 += Length;
LABEL_121:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_Dq(
          WPP_GLOBAL_Control->AttachedDevice,
          51,
          WPP_ae3c48fed8b43b056afaf76937463504_Traceguids,
          (unsigned int)v7,
          v9);
      }
      goto LABEL_124;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids);
  v6 = v35;
  while ( 1 )
  {
    if ( !Length )
    {
      if ( v6 == (_DWORD)v7 )
      {
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) == 0 )
        {
          goto LABEL_140;
        }
        v31 = 49;
      }
      else
      {
        if ( (_DWORD)v7 )
          goto LABEL_121;
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) == 0 )
        {
          goto LABEL_140;
        }
        v31 = 50;
      }
      WPP_SF_(v30->AttachedDevice, v31, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids);
LABEL_140:
      v13 = 1557;
      goto LABEL_48;
    }
    v28 = 4096;
    if ( Length < 0x1000 )
      v28 = Length;
    memmove(P, v8, v28);
    v12 = CscStorepLowIoReadWriteFileIrpEx(
            *(PFILE_OBJECT *)(*(_QWORD *)(a1 + 8) + 176LL),
            1u,
            1,
            v9,
            v28,
            0x1000u,
            P,
            0,
            (unsigned int *)&v42);
    if ( v12 < 0 )
    {
      v13 = 1492;
      goto LABEL_47;
    }
    v29 = v42;
    if ( (_DWORD)v42 != v28 )
      break;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    {
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids, v28, v42);
      v29 = v42;
    }
    LODWORD(v7) = v7 - v29;
    v6 = v29 + v35;
    v9 += v29;
    v35 += v29;
    v8 += v29;
    Length -= v29;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      47,
      WPP_ae3c48fed8b43b056afaf76937463504_Traceguids,
      (unsigned int)v42,
      v28);
  v12 = -1073740768;
  v13 = 1499;
LABEL_47:
  v6 = v35;
LABEL_48:
  ExFreePoolWithTag(P, 0x21407343u);
LABEL_161:
  *a6 = v6;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    WPP_SF_DDd(WPP_GLOBAL_Control->AttachedDevice, 57, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids, v6, v12, v13);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400074bc  mov     r11, rsp
0x1400074bf  mov     [r11+10h], rbx
0x1400074c3  mov     [r11+8], rcx
0x1400074c7  push    rbp
0x1400074c8  push    rsi
0x1400074c9  push    rdi
0x1400074ca  push    r12
0x1400074cc  push    r13
0x1400074ce  push    r14
0x1400074d0  push    r15
0x1400074d2  mov     rbp, rsp
0x1400074d5  sub     rsp, 80h
0x1400074dc  xor     r15d, r15d
0x1400074df  mov     r14d, r8d
0x1400074e2  mov     [rbp+var_30], r15d
0x1400074e6  mov     r12, r9
0x1400074e9  mov     dword ptr [rbp+arg_10], r15d
0x1400074ed  mov     rbx, rdx
0x1400074f0  mov     r8, rcx
0x1400074f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400074fa  lea     r13, WPP_GLOBAL_Control
0x140007501  mov     rdi, [rbp+arg_20]
0x140007505  cmp     rcx, r13
0x140007508  jz      short loc_14000754A
0x14000750a  test    dword ptr [rcx+2Ch], 20000h
0x140007511  jz      short loc_14000754A
0x140007513  mov     rax, [rbp+arg_28]
0x140007517  lea     edx, [r15+1Eh]
0x14000751b  mov     rcx, [rcx+18h]
0x14000751f  mov     [r11-70h], rax
0x140007523  mov     rax, [r8+8]
0x140007527  mov     [r11-78h], rdi
0x14000752b  mov     [r11-80h], r9
0x14000752f  mov     r9, r8
0x140007532  mov     dword ptr [rsp+80h+var_50], r14d
0x140007537  mov     qword ptr [rsp+80h+Length], rbx
0x14000753c  mov     qword ptr [rsp+80h+var_60], rax
0x140007541  call    WPP_SF_qqiDqqq
0x140007546  mov     r8, [rbp+arg_0]
0x14000754a  test    r14d, r14d
0x14000754d  jnz     short loc_14000755B
0x14000754f  xor     esi, esi
0x140007551  mov     edi, 43Ch
0x140007556  jmp     loc_140007F96
0x14000755b  test    r12, r12
0x14000755e  jz      loc_140007F8C
0x140007564  lea     r13, [r14+rbx]
0x140007568  mov     [rbp+var_18], r13
0x14000756c  cmp     r13, r14
0x14000756f  jge     short loc_140007587
0x140007571  mov     esi, 0C000000Dh
0x140007576  mov     edi, 452h
0x14000757b  lea     r13, WPP_GLOBAL_Control
0x140007582  jmp     loc_140007F96
0x140007587  mov     rax, [r8+8]
0x14000758b  mov     rcx, [rax+0B8h]
0x140007592  mov     rsi, [rax+148h]
0x140007599  mov     [rbp+Resource], rcx
0x14000759d  mov     [rbp+var_8], rsi
0x1400075a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400075a8  lea     rax, WPP_GLOBAL_Control
0x1400075af  cmp     rcx, rax
0x1400075b2  jz      short loc_1400075E0
0x1400075b4  test    dword ptr [rcx+2Ch], 40000h
0x1400075bb  jz      short loc_1400075E0
0x1400075bd  mov     rcx, [rcx+18h]
0x1400075c1  mov     eax, 59h ; 'Y'
0x1400075c6  test    rdi, rdi
0x1400075c9  mov     qword ptr [rsp+80h+Length], r13
0x1400075ce  mov     r9, rsi
0x1400075d1  lea     edx, [rax-0Bh]
0x1400075d4  cmovz   eax, edx
0x1400075d7  mov     byte ptr [rsp+80h+var_60], al
0x1400075db  call    WPP_SF_ici
0x1400075e0  mov     edx, 1000h
0x1400075e5  mov     ecx, 42h ; 'B'
0x1400075ea  mov     r8d, 21407343h
0x1400075f0  call    cs:__imp_ExAllocatePool2
0x1400075f7  nop     dword ptr [rax+rax+00h]
0x1400075fc  mov     [rbp+P], rax
0x140007600  mov     rdi, rax
0x140007603  test    rax, rax
0x140007606  jnz     short loc_140007617
0x140007608  mov     esi, 0C000009Ah
0x14000760d  mov     edi, 463h
0x140007612  jmp     loc_14000757B
0x140007617  mov     r15d, ebx
0x14000761a  and     r15d, 0FFFh
0x140007621  mov     [rbp+var_2C], r15d
0x140007625  jz      loc_14000798E
0x14000762b  mov     rcx, cs:WPP_GLOBAL_Control
0x140007632  lea     r13, WPP_GLOBAL_Control
0x140007639  cmp     rcx, r13
0x14000763c  jz      short loc_14000765F
0x14000763e  test    dword ptr [rcx+2Ch], 40000h
0x140007645  jz      short loc_14000765F
0x140007647  mov     rcx, [rcx+18h]
0x14000764b  lea     r8, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids
0x140007652  mov     edx, 20h ; ' '
0x140007657  mov     r9d, r15d
0x14000765a  call    WPP_SF_d
0x14000765f  mov     rcx, [rbp+Resource]; Resource
0x140007663  mov     dl, 1; Wait
0x140007665  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000766c  nop     dword ptr [rax+rax+00h]
0x140007671  mov     eax, ebx
0x140007673  mov     [rbp+var_10], rbx
0x140007677  and     eax, 0FFFFF000h
0x14000767c  xor     edx, edx; Val
0x14000767e  mov     r8d, 1000h; Size
0x140007684  mov     dword ptr [rbp+var_10], eax
0x140007687  mov     rcx, rdi; void *
0x14000768a  call    memset
0x14000768f  mov     rdi, [rbp+var_10]
0x140007693  test    rsi, rsi
0x140007696  jz      loc_14000776D
0x14000769c  cmp     rdi, rsi
0x14000769f  jge     loc_14000776D
0x1400076a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400076ac  cmp     rcx, r13
0x1400076af  jz      short loc_1400076CF
0x1400076b1  test    dword ptr [rcx+2Ch], 40000h
0x1400076b8  jz      short loc_1400076CF
0x1400076ba  mov     rcx, [rcx+18h]
0x1400076be  lea     r8, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids
0x1400076c5  mov     edx, 21h ; '!'
0x1400076ca  call    WPP_SF_
0x1400076cf  mov     rcx, [rbp+arg_0]
0x1400076d3  lea     rax, [rbp+arg_10]
0x1400076d7  mov     [rsp+80h+var_40], rax; __int64
0x1400076dc  mov     r9, rdi
0x1400076df  mov     rax, [rbp+P]
0x1400076e3  mov     r8b, 1
0x1400076e6  mov     [rsp+80h+var_48], 0; __int64
0x1400076ef  xor     edx, edx
0x1400076f1  mov     rcx, [rcx+8]
0x1400076f5  mov     [rsp+80h+var_50], rax; __int64
0x1400076fa  mov     [rsp+80h+Length], 1000h; Length
0x140007702  mov     [rsp+80h+var_60], 1000h; int
0x14000770a  mov     rcx, [rcx+0B0h]; FileObject
0x140007711  call    CscStorepLowIoReadWriteFileIrpEx
0x140007716  mov     esi, eax
0x140007718  test    eax, eax
0x14000771a  jns     short loc_140007726
0x14000771c  mov     edi, 4A0h
0x140007721  jmp     loc_140007862
0x140007726  mov     esi, dword ptr [rbp+arg_10]
0x140007729  cmp     esi, 1000h
0x14000772f  jbe     short loc_14000776F
0x140007731  mov     rcx, cs:WPP_GLOBAL_Control
0x140007738  cmp     rcx, r13
0x14000773b  jz      short loc_14000775E
0x14000773d  test    dword ptr [rcx+2Ch], 10000h
0x140007744  jz      short loc_14000775E
0x140007746  mov     rcx, [rcx+18h]
0x14000774a  lea     r8, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids
0x140007751  mov     edx, 22h ; '"'
0x140007756  mov     r9d, esi
0x140007759  call    WPP_SF_d
0x14000775e  mov     esi, 0C0000420h
0x140007763  mov     edi, 4AAh
0x140007768  jmp     loc_140007862
0x14000776d  xor     esi, esi
0x14000776f  mov     r13d, 1000h
0x140007775  mov     ecx, r15d
0x140007778  sub     r13d, r15d
0x14000777b  mov     rdx, r12; Src
0x14000777e  cmp     r14d, r13d
0x140007781  cmovb   r13d, r14d
0x140007785  add     rcx, [rbp+P]; void *
0x140007789  mov     r8d, r13d; Size
0x14000778c  call    memmove
0x140007791  add     r15d, r13d
0x140007794  mov     rcx, cs:WPP_GLOBAL_Control
0x14000779b  lea     rax, WPP_GLOBAL_Control
0x1400077a2  cmp     rcx, rax
0x1400077a5  jz      short loc_1400077D9
0x1400077a7  test    dword ptr [rcx+2Ch], 40000h
0x1400077ae  jz      short loc_1400077D2
0x1400077b0  mov     rcx, [rcx+18h]
0x1400077b4  lea     r8, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids
0x1400077bb  mov     edx, 23h ; '#'
0x1400077c0  mov     [rsp+80h+Length], r15d
0x1400077c5  mov     r9d, esi
0x1400077c8  mov     [rsp+80h+var_60], r13d
0x1400077cd  call    WPP_SF_DDd
0x1400077d2  lea     rax, WPP_GLOBAL_Control
0x1400077d9  cmp     r15d, esi
0x1400077dc  jnb     short loc_14000780B
0x1400077de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400077e5  cmp     rcx, rax
0x1400077e8  jz      short loc_140007808
0x1400077ea  test    dword ptr [rcx+2Ch], 40000h
0x1400077f1  jz      short loc_140007808
0x1400077f3  mov     rcx, [rcx+18h]
0x1400077f7  lea     r8, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids
0x1400077fe  mov     edx, 24h ; '$'
0x140007803  call    WPP_SF_
0x140007808  mov     r15d, esi
0x14000780b  mov     rax, [rbp+arg_0]
0x14000780f  mov     r8b, 1
0x140007812  mov     r9, rdi
0x140007815  mov     dl, r8b
0x140007818  mov     rcx, [rax+8]
0x14000781c  lea     rax, [rbp+arg_10]
0x140007820  mov     [rsp+80h+var_40], rax; __int64
0x140007825  mov     rax, [rbp+P]
0x140007829  mov     [rsp+80h+var_48], 0; __int64
0x140007832  mov     rcx, [rcx+0B0h]; FileObject
0x140007839  mov     [rsp+80h+var_50], rax; __int64
0x14000783e  mov     [rsp+80h+Length], 1000h; Length
0x140007846  mov     [rsp+80h+var_60], r15d; int
0x14000784b  call    CscStorepLowIoReadWriteFileIrpEx
0x140007850  mov     esi, eax
0x140007852  test    eax, eax
0x140007854  jns     short loc_140007890
0x140007856  mov     edi, 4E3h
0x14000785b  lea     r13, WPP_GLOBAL_Control
0x140007862  mov     rcx, [rbp+Resource]; Resource
0x140007866  call    cs:__imp_ExReleaseResourceLite
0x14000786d  nop     dword ptr [rax+rax+00h]
0x140007872  mov     r15d, [rbp+var_30]
0x140007876  mov     rcx, [rbp+P]; P
0x14000787a  mov     edx, 21407343h; Tag
0x14000787f  call    cs:__imp_ExFreePoolWithTag
0x140007886  nop     dword ptr [rax+rax+00h]
0x14000788b  jmp     loc_140007F96
0x140007890  mov     r9d, dword ptr [rbp+arg_10]
0x140007894  cmp     r9d, r15d
0x140007897  jnz     loc_140007949
0x14000789d  mov     [rbp+var_30], r13d
0x1400078a1  cmp     r13d, r14d
0x1400078a4  jnz     short loc_1400078DE
0x1400078a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400078ad  lea     r13, WPP_GLOBAL_Control
0x1400078b4  cmp     rcx, r13
0x1400078b7  jz      short loc_1400078D7
0x1400078b9  test    dword ptr [rcx+2Ch], 40000h
0x1400078c0  jz      short loc_1400078D7
0x1400078c2  mov     rcx, [rcx+18h]
0x1400078c6  lea     r8, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids
0x1400078cd  mov     edx, 26h ; '&'
0x1400078d2  call    WPP_SF_
0x1400078d7  mov     edi, 4F7h
0x1400078dc  jmp     short loc_140007862
0x1400078de  mov     rcx, [rbp+Resource]; Resource
0x1400078e2  lea     rdi, [rbx+r13]
0x1400078e6  mov     eax, r13d
0x1400078e9  sub     r14d, r13d
0x1400078ec  add     r12, rax
0x1400078ef  mov     r15, rdi
0x1400078f2  cmp     rdi, [rbp+var_8]
0x1400078f6  cmovle  r15, [rbp+var_8]
0x1400078fb  call    cs:__imp_ExReleaseResourceLite
0x140007902  nop     dword ptr [rax+rax+00h]
0x140007907  mov     rcx, cs:WPP_GLOBAL_Control
0x14000790e  lea     rax, WPP_GLOBAL_Control
0x140007915  mov     rbx, rdi
0x140007918  cmp     rcx, rax
0x14000791b  jz      short loc_140007943
0x14000791d  test    dword ptr [rcx+2Ch], 40000h
0x140007924  jz      short loc_140007943
0x140007926  mov     rcx, [rcx+18h]
0x14000792a  lea     r8, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids
0x140007931  mov     edx, 27h ; '''
0x140007936  mov     qword ptr [rsp+80h+var_60], rdi
0x14000793b  mov     r9d, r14d
0x14000793e  call    WPP_SF_Dq
0x140007943  mov     r13, [rbp+var_18]
0x140007947  jmp     short loc_140007993
0x140007949  mov     rcx, cs:WPP_GLOBAL_Control
0x140007950  lea     r13, WPP_GLOBAL_Control
0x140007957  cmp     rcx, r13
0x14000795a  jz      short loc_14000797F
0x14000795c  test    dword ptr [rcx+2Ch], 10000h
0x140007963  jz      short loc_14000797F
0x140007965  mov     rcx, [rcx+18h]
0x140007969  lea     r8, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids
0x140007970  mov     edx, 25h ; '%'
0x140007975  mov     [rsp+80h+var_60], r15d
0x14000797a  call    WPP_SF_Dd
0x14000797f  mov     esi, 0C0000420h
0x140007984  mov     edi, 4EAh
0x140007989  jmp     loc_140007862
0x14000798e  mov     r15, rsi
0x140007991  xor     esi, esi
0x140007993  mov     edi, r14d
0x140007996  and     edi, 0FFFFF000h
0x14000799c  test    r12d, 0FFFh
0x1400079a3  jnz     short loc_1400079E0
0x1400079a5  cmp     r13, r15
0x1400079a8  jl      short loc_1400079E0
0x1400079aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400079b1  lea     r13, WPP_GLOBAL_Control
0x1400079b8  cmp     rcx, r13
0x1400079bb  jz      short loc_1400079DB
0x1400079bd  test    dword ptr [rcx+2Ch], 40000h
0x1400079c4  jz      short loc_1400079DB
0x1400079c6  mov     rcx, [rcx+18h]
0x1400079ca  lea     r8, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids
  ... truncated ...
```
