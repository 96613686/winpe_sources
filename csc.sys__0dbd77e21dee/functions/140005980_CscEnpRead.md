# CscEnpRead

- ea: `0x140005980`
- end: `0x140006299`
- name: `CscEnpRead`
- size: `2329`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, char *, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x140004b90`

## callees

- `0x140005980`
- `0x140006a00`
- `0x1400169d4`
- `0x140018930`
- `0x1400190ec`
- `0x1400290cc`
- `0x1400293a4`
- `0x14002f140`
- `0x14002f440`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140005bde`
- `ntoskrnl!ExAllocatePool2` at `0x140005bde`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000620f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000620f`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140005a32`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140005a32`

## pseudocode

```c
__int64 __fastcall CscEnpRead(__int64 a1, __int64 a2, unsigned int a3, char *a4, __int64 a5, _DWORD *a6)
{
  int v6; // r12d
  bool v8; // r13
  char *v9; // rdi
  __int64 v10; // rbx
  __int64 v11; // r8
  __int64 v12; // r15
  int v13; // esi
  int v14; // edi
  PDEVICE_OBJECT RelatedDeviceObject; // rax
  ULONG SectorSize; // esi
  unsigned int Length; // edi
  ULONG v18; // r15d
  int v19; // r15d
  __int64 v20; // rcx
  unsigned int v21; // edi
  bool v22; // cf
  bool v23; // zf
  bool v24; // cc
  size_t v25; // r8
  unsigned int v26; // r15d
  int v27; // eax
  int v28; // eax
  ULONG v29; // esi
  unsigned int v30; // eax
  unsigned int v31; // ebx
  ULONG Size; // [rsp+50h] [rbp-20h]
  unsigned int Sizea; // [rsp+50h] [rbp-20h]
  unsigned int Size_4; // [rsp+54h] [rbp-1Ch]
  unsigned int Size_4a; // [rsp+54h] [rbp-1Ch]
  ULONG AlignmentRequirement; // [rsp+58h] [rbp-18h]
  char *Src; // [rsp+60h] [rbp-10h]
  size_t v39; // [rsp+68h] [rbp-8h]
  size_t v41; // [rsp+C0h] [rbp+50h] BYREF
  void *v42; // [rsp+C8h] [rbp+58h]

  v42 = a4;
  v6 = 0;
  v8 = 0;
  LODWORD(v41) = 0;
  v9 = a4;
  v10 = a2;
  v11 = a1;
  v12 = a5;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
  {
    WPP_SF_qqiDqqq(WPP_GLOBAL_Control->AttachedDevice, 10, a1, a1, *(_QWORD *)(a1 + 8), a2, a3, a4, a5, a6);
    v11 = a1;
  }
  if ( a3 )
  {
    if ( !v9 )
    {
      v13 = -1073740768;
      v14 = 218;
      goto LABEL_132;
    }
    RelatedDeviceObject = IoGetRelatedDeviceObject(*(PFILE_OBJECT *)(*(_QWORD *)(v11 + 8) + 176LL));
    SectorSize = RelatedDeviceObject->SectorSize;
    Size = SectorSize;
    if ( SectorSize > 0x1000 )
    {
      v13 = -1073741811;
      v14 = 242;
      goto LABEL_132;
    }
    AlignmentRequirement = RelatedDeviceObject->AlignmentRequirement;
    if ( v12 )
    {
      v13 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids);
      }
      Length = a3 & -Size;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          WPP_ae3c48fed8b43b056afaf76937463504_Traceguids,
          a3,
          a3 & -Size);
      }
      if ( Length )
      {
        v13 = CscStorepLowIoReadWriteFileIrpEx(
                *(PFILE_OBJECT *)(*(_QWORD *)(a1 + 8) + 176LL),
                Length,
                Length,
                0,
                v12,
                (__int64)&v41);
        if ( v13 < 0 )
        {
          v14 = 289;
          goto LABEL_129;
        }
        v6 = v41;
        if ( (unsigned int)v41 < Length )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids);
          }
          v14 = 313;
LABEL_129:
          if ( (v13 & 0xC0000000) != 0xC0000000 )
            goto LABEL_133;
LABEL_132:
          v6 = 0;
          goto LABEL_133;
        }
      }
      if ( Length == a3 )
      {
        v14 = 325;
        goto LABEL_129;
      }
      a3 -= Length;
      v10 += Length;
      v9 = (char *)v42 + Length;
      v42 = v9;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids, a3);
      }
      SectorSize = Size;
    }
    Src = (char *)ExAllocatePool2(66, 4096, 557871939);
    if ( !Src )
    {
      v13 = -1073741670;
      v14 = 371;
      goto LABEL_132;
    }
    v18 = SectorSize - 1;
    Size_4 = v10 & (SectorSize - 1);
    if ( Size_4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids);
      }
      v19 = ~v18;
      v13 = CscStorepLowIoReadWriteFileIrpEx(
              *(PFILE_OBJECT *)(*(_QWORD *)(a1 + 8) + 176LL),
              SectorSize,
              SectorSize,
              (__int64)Src,
              0,
              (__int64)&v41);
      if ( v13 < 0 )
      {
        v14 = 416;
LABEL_128:
        ExFreePoolWithTag(Src, 0x21407343u);
        goto LABEL_129;
      }
      v20 = Size_4;
      if ( (unsigned int)v41 <= Size_4 )
      {
        v13 = -1073741807;
        v14 = 427;
        goto LABEL_128;
      }
      v21 = a3;
      if ( a3 >= Size - Size_4 )
        v21 = Size - Size_4;
      v22 = v21 < (unsigned int)v41 - Size_4;
      v23 = v21 == (_DWORD)v41 - Size_4;
      v24 = v21 <= (unsigned int)v41 - Size_4;
      Size_4a = v41 - Size_4;
      v25 = Size_4a;
      if ( v24 )
        v25 = v21;
      v8 = !v22 && !v23;
      v39 = v25;
      memmove(v42, &Src[v20], v25);
      v6 += v39;
      if ( v21 > Size_4a )
      {
        v14 = 471;
        goto LABEL_128;
      }
      if ( (_DWORD)v39 == a3 )
      {
        v14 = 482;
        goto LABEL_128;
      }
      a3 -= v39;
      v10 += v39;
      v9 = (char *)v42 + v39;
      v42 = (char *)v42 + v39;
    }
    else
    {
      v13 = 0;
      v19 = ~v18;
    }
    v26 = a3 & v19;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids, v26);
    }
    if ( v26 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids);
      }
      if ( (AlignmentRequirement & (unsigned int)v9) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids);
        }
        while ( v26 )
        {
          v29 = 4096;
          if ( v26 < 0x1000 )
            v29 = v26;
          Sizea = v29;
          memset(Src, 0, 0x1000u);
          v13 = CscStorepLowIoReadWriteFileIrpEx(
                  *(PFILE_OBJECT *)(*(_QWORD *)(a1 + 8) + 176LL),
                  v29,
                  v29,
                  (__int64)Src,
                  0,
                  (__int64)&v41);
          if ( v13 < 0 )
          {
            if ( v13 == -1073741807 && v6 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids);
              }
              v13 = 0;
              v14 = 742;
            }
            else
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  23,
                  WPP_ae3c48fed8b43b056afaf76937463504_Traceguids,
                  (unsigned int)v13);
              }
              v14 = 746;
            }
            goto LABEL_128;
          }
          v30 = Sizea;
          if ( (unsigned int)v41 < Sizea )
          {
            v30 = v41;
            v8 = 1;
            Sizea = v41;
          }
          memmove(v9, Src, v30);
          v6 += Sizea;
          if ( v8 )
          {
            v14 = 780;
            goto LABEL_128;
          }
          v9 += (unsigned int)v41;
          a3 -= v41;
          v10 += (unsigned int)v41;
          v42 = v9;
          v26 -= v41;
        }
        if ( a3 )
          goto LABEL_79;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids);
        }
        v14 = 822;
        goto LABEL_128;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids);
      }
      memset(v9, 0, v26);
      v27 = CscStorepLowIoReadWriteFileIrpEx(
              *(PFILE_OBJECT *)(*(_QWORD *)(a1 + 8) + 176LL),
              v26,
              v26,
              (__int64)v9,
              0,
              (__int64)&v41);
      v13 = v27;
      if ( v27 < 0 )
      {
        if ( v27 == -1073741807 && v6 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids);
          }
          v13 = 0;
          v14 = 619;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              20,
              WPP_ae3c48fed8b43b056afaf76937463504_Traceguids,
              (unsigned int)v27);
          }
          v14 = 623;
        }
        goto LABEL_128;
      }
      if ( (unsigned int)v41 < v26 )
      {
        v6 += v41;
        v8 = 1;
LABEL_75:
        v14 = 651;
        goto LABEL_128;
      }
      v6 += v26;
      if ( v8 )
        goto LABEL_75;
      if ( v26 == a3 )
      {
        v14 = 663;
        goto LABEL_128;
      }
      a3 -= v26;
      v42 = &v9[v26];
    }
LABEL_79:
    v14 = 0;
    if ( a3 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids, a3);
        }
      }
      memset(Src, 0, 0x1000u);
      v28 = CscStorepLowIoReadWriteFileIrpEx(
              *(PFILE_OBJECT *)(*(_QWORD *)(a1 + 8) + 176LL),
              4096,
              0x1000u,
              (__int64)Src,
              0,
              (__int64)&v41);
      v13 = v28;
      if ( v28 >= 0 )
      {
        v31 = v41;
        if ( (unsigned int)v41 >= a3 )
          v31 = a3;
        else
          v8 = 1;
        memmove(v42, Src, v31);
        v6 += v31;
      }
      else if ( v28 == -1073741807 && v6 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids);
        }
        v13 = 0;
        v14 = 876;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            28,
            WPP_ae3c48fed8b43b056afaf76937463504_Traceguids,
            (unsigned int)v28);
        }
        v14 = 880;
      }
    }
    goto LABEL_128;
  }
  v13 = 0;
  v14 = 212;
LABEL_133:
  *a6 = v6;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
  {
    LOBYTE(a4) = v8 ? 89 : 78;
    WPP_SF_cDDD(WPP_GLOBAL_Control->AttachedDevice, a2, v11, a4, v6, v13, v14);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140005980  mov     r11, rsp
0x140005983  mov     [r11+10h], rbx
0x140005987  mov     [r11+20h], r9
0x14000598b  mov     [r11+8], rcx
0x14000598f  push    rbp
0x140005990  push    rsi
0x140005991  push    rdi
0x140005992  push    r12
0x140005994  push    r13
0x140005996  push    r14
0x140005998  push    r15
0x14000599a  mov     rbp, rsp
0x14000599d  sub     rsp, 70h
0x1400059a1  xor     r12d, r12d
0x1400059a4  mov     r14d, r8d
0x1400059a7  xor     r13b, r13b
0x1400059aa  mov     dword ptr [rbp+arg_10], r12d
0x1400059ae  mov     rdi, r9
0x1400059b1  mov     rbx, rdx
0x1400059b4  mov     r8, rcx
0x1400059b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400059be  lea     rax, WPP_GLOBAL_Control
0x1400059c5  mov     r15, [rbp+arg_20]
0x1400059c9  cmp     rcx, rax
0x1400059cc  jz      short loc_140005A0D
0x1400059ce  test    dword ptr [rcx+2Ch], 20000h
0x1400059d5  jz      short loc_140005A0D
0x1400059d7  mov     rax, [rbp+arg_28]
0x1400059db  lea     edx, [r12+0Ah]
0x1400059e0  mov     rcx, [rcx+18h]
0x1400059e4  mov     [r11-60h], rax
0x1400059e8  mov     rax, [r8+8]
0x1400059ec  mov     [r11-68h], r15
0x1400059f0  mov     [r11-70h], r9
0x1400059f4  mov     r9, r8
0x1400059f7  mov     [r11-78h], r14d
0x1400059fb  mov     [r11-80h], rbx
0x1400059ff  mov     qword ptr [rsp+70h+var_50], rax
0x140005a04  call    WPP_SF_qqiDqqq
0x140005a09  mov     r8, [rbp+arg_0]
0x140005a0d  test    r14d, r14d
0x140005a10  jnz     short loc_140005A1E
0x140005a12  xor     esi, esi
0x140005a14  mov     edi, 0D4h
0x140005a19  jmp     loc_140006237
0x140005a1e  test    rdi, rdi
0x140005a21  jz      loc_14000622A
0x140005a27  mov     rcx, [r8+8]
0x140005a2b  mov     rcx, [rcx+0B0h]; FileObject
0x140005a32  call    cs:__imp_IoGetRelatedDeviceObject
0x140005a39  nop     dword ptr [rax+rax+00h]
0x140005a3e  movzx   esi, word ptr [rax+130h]
0x140005a45  mov     dword ptr [rbp+Size], esi
0x140005a48  cmp     esi, 1000h
0x140005a4e  jbe     short loc_140005A5F
0x140005a50  mov     esi, 0C000000Dh
0x140005a55  mov     edi, 0F2h
0x140005a5a  jmp     loc_140006234
0x140005a5f  mov     eax, [rax+98h]
0x140005a65  mov     [rbp+var_18], eax
0x140005a68  test    r15, r15
0x140005a6b  jz      loc_140005BCE
0x140005a71  xor     esi, esi
0x140005a73  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a7a  lea     rax, WPP_GLOBAL_Control
0x140005a81  cmp     rcx, rax
0x140005a84  jz      short loc_140005AA2
0x140005a86  test    dword ptr [rcx+2Ch], 40000h
0x140005a8d  jz      short loc_140005AA2
0x140005a8f  mov     rcx, [rcx+18h]
0x140005a93  lea     edx, [rsi+0Bh]
0x140005a96  lea     r8, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids
0x140005a9d  call    WPP_SF_
0x140005aa2  mov     edi, dword ptr [rbp+Size]
0x140005aa5  neg     edi
0x140005aa7  and     edi, r14d
0x140005aaa  mov     rcx, cs:WPP_GLOBAL_Control
0x140005ab1  lea     rax, WPP_GLOBAL_Control
0x140005ab8  cmp     rcx, rax
0x140005abb  jz      short loc_140005AE2
0x140005abd  test    dword ptr [rcx+2Ch], 40000h
0x140005ac4  jz      short loc_140005AE2
0x140005ac6  mov     rcx, [rcx+18h]
0x140005aca  lea     r8, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids
0x140005ad1  mov     edx, 0Ch
0x140005ad6  mov     [rsp+70h+var_50], edi
0x140005ada  mov     r9d, r14d
0x140005add  call    WPP_SF_Dd
0x140005ae2  test    edi, edi
0x140005ae4  jz      loc_140005B75
0x140005aea  mov     rcx, [rbp+arg_0]
0x140005aee  lea     rax, [rbp+arg_10]
0x140005af2  mov     [rsp+70h+var_30], rax; __int64
0x140005af7  mov     r9, rbx
0x140005afa  mov     [rsp+70h+var_38], r15; __int64
0x140005aff  xor     r8d, r8d
0x140005b02  mov     [rsp+70h+var_40], rsi; __int64
0x140005b07  xor     edx, edx
0x140005b09  mov     rcx, [rcx+8]
0x140005b0d  mov     [rsp+70h+Length], edi; Length
0x140005b11  mov     [rsp+70h+var_50], edi; int
0x140005b15  mov     rcx, [rcx+0B0h]; FileObject
0x140005b1c  call    CscStorepLowIoReadWriteFileIrpEx
0x140005b21  mov     esi, eax
0x140005b23  test    eax, eax
0x140005b25  jns     short loc_140005B31
0x140005b27  mov     edi, 121h
0x140005b2c  jmp     loc_14000621B
0x140005b31  mov     r12d, dword ptr [rbp+arg_10]
0x140005b35  cmp     r12d, edi
0x140005b38  jnb     short loc_140005B75
0x140005b3a  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b41  lea     r15, WPP_GLOBAL_Control
0x140005b48  cmp     rcx, r15
0x140005b4b  jz      short loc_140005B6B
0x140005b4d  test    dword ptr [rcx+2Ch], 40000h
0x140005b54  jz      short loc_140005B6B
0x140005b56  mov     rcx, [rcx+18h]
0x140005b5a  lea     r8, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids
0x140005b61  mov     edx, 0Dh
0x140005b66  call    WPP_SF_
0x140005b6b  mov     edi, 139h
0x140005b70  jmp     loc_14000621B
0x140005b75  cmp     edi, r14d
0x140005b78  jnz     short loc_140005B84
0x140005b7a  mov     edi, 145h
0x140005b7f  jmp     loc_14000621B
0x140005b84  mov     eax, edi
0x140005b86  sub     r14d, edi
0x140005b89  mov     rdi, [rbp+arg_18]
0x140005b8d  add     rbx, rax
0x140005b90  add     rdi, rax
0x140005b93  mov     [rbp+arg_18], rdi
0x140005b97  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b9e  lea     rax, WPP_GLOBAL_Control
0x140005ba5  cmp     rcx, rax
0x140005ba8  jz      short loc_140005BCB
0x140005baa  test    dword ptr [rcx+2Ch], 40000h
0x140005bb1  jz      short loc_140005BCB
0x140005bb3  mov     rcx, [rcx+18h]
0x140005bb7  lea     r8, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids
0x140005bbe  mov     edx, 0Eh
0x140005bc3  mov     r9d, r14d
0x140005bc6  call    WPP_SF_d
0x140005bcb  mov     esi, dword ptr [rbp+Size]
0x140005bce  mov     edx, 1000h
0x140005bd3  mov     ecx, 42h ; 'B'
0x140005bd8  mov     r8d, 21407343h
0x140005bde  call    cs:__imp_ExAllocatePool2
0x140005be5  nop     dword ptr [rax+rax+00h]
0x140005bea  mov     [rbp+Src], rax
0x140005bee  test    rax, rax
0x140005bf1  jnz     short loc_140005C02
0x140005bf3  mov     esi, 0C000009Ah
0x140005bf8  mov     edi, 173h
0x140005bfd  jmp     loc_140006234
0x140005c02  lea     r15d, [rsi-1]
0x140005c06  mov     eax, r15d
0x140005c09  and     eax, ebx
0x140005c0b  mov     dword ptr [rbp+Size+4], eax
0x140005c0e  jz      loc_140005D29
0x140005c14  mov     rcx, cs:WPP_GLOBAL_Control
0x140005c1b  lea     rax, WPP_GLOBAL_Control
0x140005c22  cmp     rcx, rax
0x140005c25  jz      short loc_140005C45
0x140005c27  test    dword ptr [rcx+2Ch], 40000h
0x140005c2e  jz      short loc_140005C45
0x140005c30  mov     rcx, [rcx+18h]
0x140005c34  lea     r8, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids
0x140005c3b  mov     edx, 0Fh
0x140005c40  call    WPP_SF_
0x140005c45  mov     [rbp+var_8], rbx
0x140005c49  not     r15d
0x140005c4c  mov     eax, r15d
0x140005c4f  mov     r8b, 1
0x140005c52  and     eax, ebx
0x140005c54  xor     edx, edx
0x140005c56  mov     dword ptr [rbp+var_8], eax
0x140005c59  mov     rax, [rbp+arg_0]
0x140005c5d  mov     r9, [rbp+var_8]
0x140005c61  mov     rcx, [rax+8]
0x140005c65  lea     rax, [rbp+arg_10]
0x140005c69  mov     [rsp+70h+var_30], rax; __int64
0x140005c6e  mov     rax, [rbp+Src]
0x140005c72  mov     [rsp+70h+var_38], 0; __int64
0x140005c7b  mov     rcx, [rcx+0B0h]; FileObject
0x140005c82  mov     [rsp+70h+var_40], rax; __int64
0x140005c87  mov     [rsp+70h+Length], esi; Length
0x140005c8b  mov     [rsp+70h+var_50], esi; int
0x140005c8f  call    CscStorepLowIoReadWriteFileIrpEx
0x140005c94  mov     esi, eax
0x140005c96  test    eax, eax
0x140005c98  jns     short loc_140005CA4
0x140005c9a  mov     edi, 1A0h
0x140005c9f  jmp     loc_140006206
0x140005ca4  mov     ecx, dword ptr [rbp+Size+4]
0x140005ca7  mov     edx, dword ptr [rbp+arg_10]
0x140005caa  cmp     edx, ecx
0x140005cac  ja      short loc_140005CBD
0x140005cae  mov     esi, 0C0000011h
0x140005cb3  mov     edi, 1ABh
0x140005cb8  jmp     loc_140006206
0x140005cbd  mov     eax, dword ptr [rbp+Size]
0x140005cc0  mov     edi, r14d
0x140005cc3  sub     eax, ecx
0x140005cc5  cmp     r14d, eax
0x140005cc8  cmovnb  edi, eax
0x140005ccb  sub     edx, ecx
0x140005ccd  cmp     edi, edx
0x140005ccf  mov     dword ptr [rbp+Size+4], edx
0x140005cd2  mov     r8d, edx
0x140005cd5  mov     rdx, rcx
0x140005cd8  mov     rcx, [rbp+arg_18]; void *
0x140005cdc  cmovbe  r8d, edi; Size
0x140005ce0  setnbe  r13b
0x140005ce4  mov     [rbp+var_8], r8
0x140005ce8  add     rdx, [rbp+Src]; Src
0x140005cec  call    memmove
0x140005cf1  mov     rax, [rbp+var_8]
0x140005cf5  add     r12d, eax
0x140005cf8  cmp     edi, dword ptr [rbp+Size+4]
0x140005cfb  jbe     short loc_140005D07
0x140005cfd  mov     edi, 1D7h
0x140005d02  jmp     loc_140006206
0x140005d07  cmp     eax, r14d
0x140005d0a  jnz     short loc_140005D16
0x140005d0c  mov     edi, 1E2h
0x140005d11  jmp     loc_140006206
0x140005d16  mov     rdi, [rbp+arg_18]
0x140005d1a  sub     r14d, eax
0x140005d1d  add     rbx, rax
0x140005d20  add     rdi, rax
0x140005d23  mov     [rbp+arg_18], rdi
0x140005d27  jmp     short loc_140005D2E
0x140005d29  xor     esi, esi
0x140005d2b  not     r15d
0x140005d2e  and     r15d, r14d
0x140005d31  mov     rcx, cs:WPP_GLOBAL_Control
0x140005d38  lea     rdx, WPP_GLOBAL_Control
0x140005d3f  cmp     rcx, rdx
0x140005d42  jz      short loc_140005D6C
0x140005d44  test    dword ptr [rcx+2Ch], 40000h
0x140005d4b  jz      short loc_140005D6C
0x140005d4d  mov     rcx, [rcx+18h]
0x140005d51  lea     r8, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids
0x140005d58  mov     edx, 10h
0x140005d5d  mov     r9d, r15d
0x140005d60  call    WPP_SF_d
0x140005d65  lea     rdx, WPP_GLOBAL_Control
0x140005d6c  test    r15d, r15d
0x140005d6f  jz      loc_140005EF7
0x140005d75  mov     rcx, cs:WPP_GLOBAL_Control
0x140005d7c  cmp     rcx, rdx
0x140005d7f  jz      short loc_140005DA6
0x140005d81  test    dword ptr [rcx+2Ch], 40000h
0x140005d88  jz      short loc_140005DA6
0x140005d8a  mov     rcx, [rcx+18h]
0x140005d8e  lea     r8, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids
0x140005d95  mov     edx, 11h
0x140005d9a  call    WPP_SF_
0x140005d9f  lea     rdx, WPP_GLOBAL_Control
0x140005da6  mov     eax, [rbp+var_18]
0x140005da9  test    rdi, rax
0x140005dac  jnz     loc_140006005
0x140005db2  mov     rcx, cs:WPP_GLOBAL_Control
0x140005db9  cmp     rcx, rdx
0x140005dbc  jz      short loc_140005DDC
0x140005dbe  test    dword ptr [rcx+2Ch], 40000h
0x140005dc5  jz      short loc_140005DDC
0x140005dc7  mov     rcx, [rcx+18h]
0x140005dcb  lea     r8, WPP_ae3c48fed8b43b056afaf76937463504_Traceguids
0x140005dd2  mov     edx, 12h
0x140005dd7  call    WPP_SF_
0x140005ddc  mov     r8d, r15d; Size
0x140005ddf  xor     edx, edx; Val
0x140005de1  mov     rcx, rdi; void *
0x140005de4  call    memset
0x140005de9  mov     rax, [rbp+arg_0]
0x140005ded  mov     r9, rbx
0x140005df0  xor     r8d, r8d
0x140005df3  xor     edx, edx
0x140005df5  mov     rcx, [rax+8]
0x140005df9  lea     rax, [rbp+arg_10]
0x140005dfd  mov     [rsp+70h+var_30], rax; __int64
0x140005e02  mov     [rsp+70h+var_38], 0; __int64
0x140005e0b  mov     [rsp+70h+var_40], rdi; __int64
0x140005e10  mov     rcx, [rcx+0B0h]; FileObject
0x140005e17  mov     [rsp+70h+Length], r15d; Length
0x140005e1c  mov     [rsp+70h+var_50], r15d; int
0x140005e21  call    CscStorepLowIoReadWriteFileIrpEx
0x140005e26  mov     esi, eax
0x140005e28  test    eax, eax
0x140005e2a  jns     loc_140005EB7
0x140005e30  cmp     eax, 0C0000011h
0x140005e35  jnz     short loc_140005E79
0x140005e37  test    r12d, r12d
0x140005e3a  jz      short loc_140005E79
0x140005e3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140005e43  lea     rax, WPP_GLOBAL_Control
0x140005e4a  cmp     rcx, rax
  ... truncated ...
```
