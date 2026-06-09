# MrxSmbUnalignedDirEntryCopyTail

- ea: `0x140052fa0`
- end: `0x1400539de`
- name: `MrxSmbUnalignedDirEntryCopyTail`
- size: `2622`
- prototype: `__int64 __fastcall(__int64, int, __int64, int *, __int64)`
- caller_count: `3`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x14002a430`
- `0x140043368`
- `0x140043f88`

## callees

- `0x14000dc44`
- `0x14000dfd8`
- `0x14000e01c`
- `0x14000e52c`
- `0x14000e828`
- `0x14000e8e0`
- `0x14000e998`
- `0x14000eca8`
- `0x140016560`
- `0x1400166c0`
- `0x1400169c0`
- `0x1400283f8`
- `0x14002c3ac`
- `0x140052fa0`

## import_xrefs

- `ntoskrnl!RtlxOemStringToUnicodeSize` at `0x140053281`
- `ntoskrnl!RtlxOemStringToUnicodeSize` at `0x140053281`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400537ed`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400537ed`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x1400536f1`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x1400536f1`
- `ntoskrnl!RtlOemStringToCountedUnicodeString` at `0x14005346d`
- `ntoskrnl!RtlOemStringToCountedUnicodeString` at `0x14005346d`
- `ntoskrnl!RtlOemStringToUnicodeString` at `0x140053411`
- `ntoskrnl!RtlOemStringToUnicodeString` at `0x1400534f2`
- `ntoskrnl!RtlOemStringToUnicodeString` at `0x140053411`
- `ntoskrnl!RtlOemStringToUnicodeString` at `0x1400534f2`

## pseudocode

```c
__int64 __fastcall MrxSmbUnalignedDirEntryCopyTail(__int64 a1, int a2, __int64 a3, int *a4, __int64 a5)
{
  __int64 v6; // r14
  char *v7; // rdx
  unsigned int v8; // r15d
  _DWORD *v9; // r10
  unsigned int v10; // r12d
  __int64 v11; // r9
  unsigned int v12; // eax
  bool v13; // bl
  int v14; // ecx
  unsigned int v15; // r11d
  unsigned int v16; // r8d
  _DWORD *v17; // r10
  unsigned int v18; // eax
  unsigned int v19; // r14d
  unsigned int v20; // ecx
  __int64 v21; // rdx
  unsigned int v22; // r15d
  unsigned int v23; // eax
  CHAR *v24; // r8
  unsigned int v25; // ecx
  unsigned int v26; // edx
  unsigned int v27; // eax
  ULONG v28; // r15d
  int v29; // edx
  int v30; // r8d
  signed int v31; // r13d
  unsigned int v32; // r8d
  void *v33; // rcx
  char *v34; // rdx
  WCHAR *v35; // r9
  USHORT v36; // r15
  NTSTATUS v37; // eax
  char *v38; // r15
  __int64 v39; // r8
  unsigned int v40; // ebx
  __int64 v41; // r9
  __int64 v42; // r8
  __int16 v43; // r14
  const UNICODE_STRING *v44; // rcx
  int v45; // eax
  int v46; // eax
  char v48; // [rsp+30h] [rbp-178h]
  char v49; // [rsp+31h] [rbp-177h]
  char v50; // [rsp+32h] [rbp-176h]
  int v51; // [rsp+34h] [rbp-174h]
  unsigned int v52; // [rsp+3Ch] [rbp-16Ch]
  unsigned int v53; // [rsp+40h] [rbp-168h]
  unsigned int v54; // [rsp+44h] [rbp-164h]
  unsigned int v55; // [rsp+48h] [rbp-160h]
  unsigned int Size; // [rsp+4Ch] [rbp-15Ch]
  unsigned int Size_4; // [rsp+50h] [rbp-158h]
  unsigned int v59; // [rsp+68h] [rbp-140h]
  char *v60; // [rsp+70h] [rbp-138h]
  STRING SourceString; // [rsp+78h] [rbp-130h] BYREF
  unsigned int v62; // [rsp+88h] [rbp-120h]
  int v63; // [rsp+8Ch] [rbp-11Ch]
  int v64; // [rsp+90h] [rbp-118h]
  unsigned int v65; // [rsp+94h] [rbp-114h]
  STRING OemString; // [rsp+98h] [rbp-110h] BYREF
  __int64 v67; // [rsp+A8h] [rbp-100h]
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-F8h] BYREF
  struct _UNICODE_STRING v69; // [rsp+C0h] [rbp-E8h] BYREF
  unsigned int v70; // [rsp+D0h] [rbp-D8h]
  unsigned int v71; // [rsp+D4h] [rbp-D4h]
  unsigned int v72; // [rsp+D8h] [rbp-D0h]
  unsigned int v73; // [rsp+DCh] [rbp-CCh]
  __int64 v74; // [rsp+E0h] [rbp-C8h]
  __int64 v75; // [rsp+E8h] [rbp-C0h]
  void *v76; // [rsp+F0h] [rbp-B8h]
  __int64 v77; // [rsp+F8h] [rbp-B0h]
  void *Src; // [rsp+100h] [rbp-A8h]
  char *v79; // [rsp+108h] [rbp-A0h]
  int *v80; // [rsp+110h] [rbp-98h]
  __int64 v81; // [rsp+118h] [rbp-90h]
  __int64 v82; // [rsp+120h] [rbp-88h]
  int *v83; // [rsp+128h] [rbp-80h]
  __int64 v84; // [rsp+130h] [rbp-78h]
  __int64 v85; // [rsp+138h] [rbp-70h]
  __int64 v86; // [rsp+140h] [rbp-68h]
  _DWORD *v87; // [rsp+148h] [rbp-60h]
  char v88; // [rsp+150h] [rbp-58h] BYREF

  v80 = a4;
  v75 = a3;
  v6 = a1;
  v83 = a4;
  v84 = a1;
  v85 = a3;
  v86 = a5;
  v7 = 0;
  *(_QWORD *)&SourceString.Length = 0;
  v59 = *(unsigned __int16 *)(a5 + 56);
  v8 = *(unsigned __int16 *)(a5 + 54);
  Size = v8;
  v74 = *(_QWORD *)(a5 + 16);
  v81 = v74;
  v49 = *(_BYTE *)(a5 + 29);
  v48 = *(_BYTE *)(a5 + 30);
  v77 = a5 + 8;
  v67 = *(_QWORD *)(a5 + 8);
  v82 = v67;
  v9 = (_DWORD *)(a5 + 32);
  v10 = *(_DWORD *)(a5 + 32);
  v64 = v10;
  v87 = (_DWORD *)(a5 + 36);
  v11 = *(unsigned int *)(a5 + 36);
  Size_4 = *(_DWORD *)(a5 + 36);
  v65 = Size_4;
  v50 = *(_BYTE *)(a5 + 28);
  v12 = *(_DWORD *)(a5 + 40);
  v54 = v12;
  v73 = v12;
  v70 = v12;
  v13 = 0;
  v14 = *a4;
  v51 = *a4;
  v63 = *a4;
  v15 = 0;
  v52 = 0;
  v16 = 0;
  v55 = 0;
  while ( 1 )
  {
    DestinationString = 0;
    OemString = 0;
    if ( (unsigned int)v11 >= v12 )
    {
      v13 = 1;
      v10 = v16;
      goto LABEL_103;
    }
    v17 = (_DWORD *)(v74 + (unsigned int)v11);
    Src = v17;
    v18 = v70 - v11;
    if ( v48 )
    {
      if ( v18 < 0x1F )
        goto LABEL_61;
      v59 = 30;
      Size = 31;
      v19 = *((unsigned __int8 *)v17 + 30);
      v62 = *v17;
      v20 = v19 + 32;
      v79 = v7;
      v21 = 31;
    }
    else
    {
      if ( v8 > v18 )
        goto LABEL_61;
      v79 = 0;
      v19 = *(_DWORD *)((char *)v17 + v59);
      v62 = v17[1];
      v20 = *v17;
      v21 = v8;
      v15 = v52;
    }
    v22 = v20 + v11;
    v71 = v20 + v11;
    v23 = v11;
    if ( (unsigned int)v11 <= v20 )
      v23 = v20;
    if ( v22 < v23 || v22 > v54 )
    {
      v13 = 1;
      v10 = v16;
      v7 = *(char **)&SourceString.Length;
      v6 = a1;
      v14 = v51;
      goto LABEL_102;
    }
    v24 = (char *)v17 + v21;
    v76 = (char *)v17 + v21;
    v25 = v11 + v21;
    v26 = v11 + v21 + v19;
    v27 = v19;
    if ( v19 <= v25 )
      v27 = v25;
    if ( v26 < v27 || v26 > v54 )
      break;
    OemString.Buffer = v24;
    OemString.Length = v19;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids, v11, v15);
    if ( v49 )
    {
      v28 = v19;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_LDZ(WPP_GLOBAL_Control->AttachedDevice, v26, (_DWORD)v24, v19, v19, (__int64)&OemString);
      }
    }
    else
    {
      v28 = RtlxOemStringToUnicodeSize(&OemString) - 2;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_LLaZ(WPP_GLOBAL_Control->AttachedDevice, v29, v30, v19, v28, (__int64)&OemString);
      }
    }
    v31 = v28 + Size + 2;
    v14 = v51;
    if ( v31 > v51 )
    {
      v7 = *(char **)&SourceString.Length;
      LODWORD(v11) = Size_4;
      v6 = a1;
LABEL_101:
      v16 = v55;
LABEL_102:
      v9 = (_DWORD *)(a5 + 32);
LABEL_103:
      if ( v16 )
      {
LABEL_90:
        v40 = 0;
        *(_DWORD *)v7 = 0;
      }
      else
      {
        v40 = v13 ? -1073741802 : -2147483643;
      }
      v46 = 0;
      if ( v14 > 0 )
        v46 = v14;
      *v80 = v46;
      if ( v16 < v10 )
      {
        *v87 = v11;
        *v9 = v10 - v16;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
        {
          WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids, v6, a5);
        }
        MRxSmbDeallocateSideBuffer(v6, a5, "Tail");
        if ( v50 )
          *(_DWORD *)(a5 + 48) = -2147483642;
      }
      return v40;
    }
    v60 = (char *)(v75 + v52);
    v32 = ((v31 + 3) & 0xFFFFFFFC) + 4;
    if ( (char *)((unsigned __int64)&v60[((v31 + 3) & 0xFFFFFFFC) + 7] & 0xFFFFFFFFFFFFFFF8uLL) == &v60[(v31 + 3) & 0xFFFFFFFC] )
      v32 = (v31 + 3) & 0xFFFFFFFC;
    v53 = v32;
    v72 = v32;
    v33 = (void *)(v75 + v52);
    if ( v48 )
      memset(v33, 0, Size);
    else
      memmove(v33, Src, Size);
    v34 = v60;
    *(_DWORD *)v60 = v53;
    *(_DWORD *)&v60[v59] = v28;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    {
      WPP_SF_qLq(WPP_GLOBAL_Control->AttachedDevice, v60, &WPP_GLOBAL_Control, v75, v52, v60);
      v34 = v60;
    }
    v35 = (WCHAR *)&v34[Size];
    DestinationString.Buffer = v35;
    if ( v49 )
    {
      memmove(v35, OemString.Buffer, OemString.Length);
      DestinationString.Length = OemString.Length;
LABEL_57:
      v38 = v60;
      goto LABEL_58;
    }
    if ( v31 > v51 - 2 )
    {
      DestinationString.MaximumLength = v28;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids,
          v35,
          (unsigned __int16)v28);
      }
      v37 = RtlOemStringToCountedUnicodeString(&DestinationString, &OemString, 0);
    }
    else
    {
      v36 = v28 + 2;
      DestinationString.MaximumLength = v36;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids, v35, v36);
      }
      v37 = RtlOemStringToUnicodeString(&DestinationString, &OemString, 0);
    }
    if ( v37 )
      DestinationString.Length = 0;
    if ( a2 != 3 )
      goto LABEL_57;
    v38 = v60;
    if ( !v48 )
    {
      *(_QWORD *)&SourceString.Length = 0;
      *(_QWORD *)&v69.Length = 1572864;
      SourceString.Buffer = v60 + 70;
      SourceString.MaximumLength = v60[68];
      SourceString.Length = SourceString.MaximumLength;
      v69.Buffer = (PWSTR)&v88;
      if ( RtlOemStringToUnicodeString(&v69, &SourceString, 0) )
      {
        v60[68] = 0;
      }
      else
      {
        v60[68] = v69.Length;
        memmove(v60 + 70, v69.Buffer, v69.Length);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids, &v69);
      }
    }
LABEL_58:
    v39 = v67;
    if ( v67 )
    {
      if ( v19 > 0x200 )
        break;
      v41 = v62;
      *(_DWORD *)(v67 + 6) = v62;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids, v41);
        v39 = v67;
      }
      memmove((void *)(v39 + 12), v76, v19);
      v42 = v67;
      *(_BYTE *)(v19 + v67 + 12) = 0;
      if ( v49 )
      {
        *(_BYTE *)(v19 + 1 + v42 + 12) = 0;
        v43 = v19 + 14;
      }
      else
      {
        v43 = v19 + 13;
      }
      *(_WORD *)(*(_QWORD *)v77 + 528LL) = v43;
    }
    v7 = v38;
    *(_QWORD *)&SourceString.Length = v38;
    v76 = v38;
    if ( !v48 )
    {
      v13 = 0;
      goto LABEL_80;
    }
    v6 = a1;
    v44 = *(const UNICODE_STRING **)(a1 + 64);
    if ( *(_BYTE *)(a5 + 58) )
    {
      v13 = FsRtlIsNameInExpression((PUNICODE_STRING)&v44[5], &DestinationString, 1u, 0) == 0;
      v7 = *(char **)&SourceString.Length;
      v11 = Size_4;
      v14 = v51;
      v45 = v53;
    }
    else
    {
      if ( !RtlEqualUnicodeString(v44 + 5, &DestinationString, 1u) )
      {
        v13 = 1;
LABEL_78:
        v7 = v79;
        *(_QWORD *)&SourceString.Length = v79;
        goto LABEL_79;
      }
      v13 = 0;
      v7 = v38;
      v11 = Size_4;
      v14 = v51;
      v45 = v53;
    }
    if ( v13 )
      goto LABEL_78;
    if ( v45 > v14 )
      goto LABEL_101;
    MRxSmbTranslateLanManFindBuffer(a1, v38, Src, v11);
    v7 = *(char **)&SourceString.Length;
LABEL_79:
    if ( v13 )
    {
      v64 = --v10;
      v16 = v55;
      v14 = v51;
      v15 = v52;
      goto LABEL_86;
    }
LABEL_80:
    v14 = v51 - v53;
    v51 = v14;
    v63 = v14;
    v16 = ++v55;
    v15 = v53 + v52;
    v52 += v53;
LABEL_86:
    v11 = v71;
    Size_4 = v71;
    v65 = v71;
    v6 = a1;
    v9 = (_DWORD *)(a5 + 32);
    if ( v16 >= v10 || v14 < 0 )
      goto LABEL_103;
    v8 = Size;
    v12 = v54;
    if ( *(_BYTE *)(a1 + 517) && v16 )
      goto LABEL_90;
  }
  v6 = a1;
LABEL_61:
  v40 = -1073741629;
  *(_DWORD *)(a5 + 48) = -1073741629;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids, v6, a5);
  MRxSmbDeallocateSideBuffer(v6, a5, "Tail");
  return v40;
}

```

## disassembly

```asm
0x140052fa0  mov     [rsp+arg_8], edx
0x140052fa4  push    rbx
0x140052fa5  push    rsi
0x140052fa6  push    rdi
0x140052fa7  push    r12
0x140052fa9  push    r13
0x140052fab  push    r14
0x140052fad  push    r15
0x140052faf  sub     rsp, 170h
0x140052fb6  mov     rax, cs:__security_cookie
0x140052fbd  xor     rax, rsp
0x140052fc0  mov     [rsp+1A8h+var_40], rax
0x140052fc8  mov     r11, r9
0x140052fcb  mov     [rsp+1A8h+var_98], r9
0x140052fd3  mov     rax, r8
0x140052fd6  mov     [rsp+1A8h+var_C0], rax
0x140052fde  mov     r14, rcx
0x140052fe1  mov     [rsp+1A8h+var_150], rcx
0x140052fe6  mov     [rsp+1A8h+var_80], r9
0x140052fee  mov     [rsp+1A8h+var_78], rcx
0x140052ff6  mov     [rsp+1A8h+var_70], rax
0x140052ffe  mov     rsi, [rsp+1A8h+arg_20]
0x140053006  mov     [rsp+1A8h+var_68], rsi
0x14005300e  xor     edi, edi
0x140053010  mov     edx, edi
0x140053012  mov     qword ptr [rsp+1A8h+SourceString.Length], rdx
0x140053017  movzx   eax, word ptr [rsi+38h]
0x14005301b  mov     [rsp+1A8h+var_140], eax
0x14005301f  movzx   r15d, word ptr [rsi+36h]
0x140053024  mov     dword ptr [rsp+1A8h+Size], r15d
0x140053029  mov     rax, [rsi+10h]
0x14005302d  mov     [rsp+1A8h+var_C8], rax
0x140053035  mov     [rsp+1A8h+var_90], rax
0x14005303d  mov     al, [rsi+1Dh]
0x140053040  mov     [rsp+1A8h+var_177], al
0x140053044  mov     [rsp+1A8h+var_16F], al
0x140053048  mov     al, [rsi+1Eh]
0x14005304b  mov     [rsp+1A8h+var_178], al
0x14005304f  mov     [rsp+1A8h+var_16E], al
0x140053053  lea     rax, [rsi+8]
0x140053057  mov     [rsp+1A8h+var_B0], rax
0x14005305f  mov     rax, [rax]
0x140053062  mov     [rsp+1A8h+var_100], rax
0x14005306a  mov     [rsp+1A8h+var_88], rax
0x140053072  lea     r10, [rsi+20h]
0x140053076  mov     [rsp+1A8h+var_148], r10
0x14005307b  mov     r12d, [r10]
0x14005307e  mov     [rsp+1A8h+var_118], r12d
0x140053086  lea     rax, [rsi+24h]
0x14005308a  mov     [rsp+1A8h+var_60], rax
0x140053092  mov     r9d, [rax]
0x140053095  mov     dword ptr [rsp+1A8h+Size+4], r9d
0x14005309a  mov     [rsp+1A8h+var_114], r9d
0x1400530a2  mov     al, [rsi+1Ch]
0x1400530a5  mov     [rsp+1A8h+var_176], al
0x1400530a9  mov     [rsp+1A8h+var_16D], al
0x1400530ad  mov     eax, [rsi+28h]
0x1400530b0  mov     [rsp+1A8h+var_164], eax
0x1400530b4  mov     [rsp+1A8h+var_CC], eax
0x1400530bb  mov     [rsp+1A8h+var_D8], eax
0x1400530c2  mov     bl, dil
0x1400530c5  mov     ecx, [r11]
0x1400530c8  mov     [rsp+1A8h+var_174], ecx
0x1400530cc  mov     [rsp+1A8h+var_11C], ecx
0x1400530d3  mov     r11d, edi
0x1400530d6  mov     [rsp+1A8h+var_16C], edi
0x1400530da  mov     r8d, edi
0x1400530dd  mov     [rsp+1A8h+var_160], edi
0x1400530e1  lea     r13, WPP_GLOBAL_Control
0x1400530e8  xorps   xmm0, xmm0
0x1400530eb  movups  xmmword ptr [rsp+1A8h+DestinationString.Length], xmm0
0x1400530f3  xorps   xmm1, xmm1
0x1400530f6  movups  xmmword ptr [rsp+1A8h+OemString.Length], xmm1
0x1400530fe  cmp     r9d, eax
0x140053101  jb      short loc_14005310D
0x140053103  mov     bl, 1
0x140053105  mov     r12d, r8d
0x140053108  jmp     loc_140053989
0x14005310d  mov     r10d, r9d
0x140053110  add     r10, [rsp+1A8h+var_C8]
0x140053118  mov     [rsp+1A8h+Src], r10
0x140053120  mov     eax, [rsp+1A8h+var_D8]
0x140053127  sub     eax, r9d
0x14005312a  cmp     [rsp+1A8h+var_178], dil
0x14005312f  jnz     short loc_140053163
0x140053131  cmp     r15d, eax
0x140053134  ja      loc_1400535BB
0x14005313a  mov     [rsp+1A8h+var_A0], rdi
0x140053142  mov     eax, [rsp+1A8h+var_140]
0x140053146  mov     r14d, [rax+r10]
0x14005314a  mov     r11d, [r10+4]
0x14005314e  mov     [rsp+1A8h+var_120], r11d
0x140053156  mov     ecx, [r10]
0x140053159  mov     edx, r15d
0x14005315c  mov     r11d, [rsp+1A8h+var_16C]
0x140053161  jmp     short loc_14005319C
0x140053163  cmp     eax, 1Fh
0x140053166  jb      loc_1400535BB
0x14005316c  mov     [rsp+1A8h+var_140], 1Eh
0x140053174  mov     dword ptr [rsp+1A8h+Size], 1Fh
0x14005317c  movzx   r14d, byte ptr [r10+1Eh]
0x140053181  mov     eax, [r10]
0x140053184  mov     [rsp+1A8h+var_120], eax
0x14005318b  lea     ecx, [r14+20h]
0x14005318f  mov     [rsp+1A8h+var_A0], rdx
0x140053197  mov     edx, 1Fh
0x14005319c  lea     r15d, [rcx+r9]
0x1400531a0  mov     [rsp+1A8h+var_D4], r15d
0x1400531a8  mov     eax, r9d
0x1400531ab  cmp     r9d, ecx
0x1400531ae  cmovbe  eax, ecx
0x1400531b1  cmp     r15d, eax
0x1400531b4  jb      loc_140053954
0x1400531ba  cmp     r15d, [rsp+1A8h+var_164]
0x1400531bf  ja      loc_140053954
0x1400531c5  lea     r8, [r10+rdx]
0x1400531c9  mov     [rsp+1A8h+var_B8], r8
0x1400531d1  mov     ecx, r8d
0x1400531d4  sub     ecx, dword ptr [rsp+1A8h+var_C8]
0x1400531db  lea     edx, [rcx+r14]
0x1400531df  mov     eax, r14d
0x1400531e2  cmp     r14d, ecx
0x1400531e5  cmovbe  eax, ecx
0x1400531e8  cmp     edx, eax
0x1400531ea  jb      loc_1400535B6
0x1400531f0  cmp     edx, [rsp+1A8h+var_164]
0x1400531f4  ja      loc_1400535B6
0x1400531fa  mov     [rsp+1A8h+OemString.Buffer], r8
0x140053202  mov     [rsp+1A8h+OemString.Length], r14w
0x14005320b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140053212  cmp     rcx, r13
0x140053215  jz      short loc_14005323A
0x140053217  test    dword ptr [rcx+2Ch], 400h
0x14005321e  jz      short loc_14005323A
0x140053220  mov     edx, 0Ch
0x140053225  mov     dword ptr [rsp+1A8h+var_188], r11d
0x14005322a  lea     r8, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids
0x140053231  mov     rcx, [rcx+18h]
0x140053235  call    WPP_SF_Dd
0x14005323a  cmp     [rsp+1A8h+var_177], dil
0x14005323f  jz      short loc_140053279
0x140053241  mov     r15d, r14d
0x140053244  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005324b  cmp     rcx, r13
0x14005324e  jz      short loc_1400532C4
0x140053250  test    dword ptr [rcx+2Ch], 400h
0x140053257  jz      short loc_1400532C4
0x140053259  lea     rax, [rsp+1A8h+OemString]
0x140053261  mov     [rsp+1A8h+var_180], rax
0x140053266  mov     dword ptr [rsp+1A8h+var_188], r14d
0x14005326b  mov     r9d, r14d
0x14005326e  mov     rcx, [rcx+18h]
0x140053272  call    WPP_SF_LDZ
0x140053277  jmp     short loc_1400532C4
0x140053279  lea     rcx, [rsp+1A8h+OemString]; OemString
0x140053281  call    cs:__imp_RtlxOemStringToUnicodeSize
0x140053288  nop     dword ptr [rax+rax+00h]
0x14005328d  lea     r15d, [rax-2]
0x140053291  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140053298  cmp     rcx, r13
0x14005329b  jz      short loc_1400532C4
0x14005329d  test    dword ptr [rcx+2Ch], 400h
0x1400532a4  jz      short loc_1400532C4
0x1400532a6  lea     rax, [rsp+1A8h+OemString]
0x1400532ae  mov     [rsp+1A8h+var_180], rax
0x1400532b3  mov     dword ptr [rsp+1A8h+var_188], r15d
0x1400532b8  mov     r9d, r14d
0x1400532bb  mov     rcx, [rcx+18h]
0x1400532bf  call    WPP_SF_LLaZ
0x1400532c4  mov     r10d, dword ptr [rsp+1A8h+Size]
0x1400532c9  lea     r13d, [r10+2]
0x1400532cd  add     r13d, r15d
0x1400532d0  mov     ecx, [rsp+1A8h+var_174]
0x1400532d4  cmp     r13d, ecx
0x1400532d7  jg      loc_140053969
0x1400532dd  lea     eax, [r13+3]
0x1400532e1  and     eax, 0FFFFFFFCh
0x1400532e4  mov     edx, eax
0x1400532e6  mov     r9d, [rsp+1A8h+var_16C]
0x1400532eb  add     r9, [rsp+1A8h+var_C0]
0x1400532f3  mov     [rsp+1A8h+var_138], r9
0x1400532f8  lea     rcx, [rax+r9]
0x1400532fc  lea     rax, [rcx+7]
0x140053300  and     rax, 0FFFFFFFFFFFFFFF8h
0x140053304  lea     r8d, [rdx+4]
0x140053308  cmp     rax, rcx
0x14005330b  cmovz   r8d, edx
0x14005330f  mov     [rsp+1A8h+var_168], r8d
0x140053314  mov     [rsp+1A8h+var_D0], r8d
0x14005331c  mov     ebx, r10d
0x14005331f  mov     r8d, ebx; Size
0x140053322  mov     rcx, r9; void *
0x140053325  cmp     [rsp+1A8h+var_178], dil
0x14005332a  jnz     short loc_14005333B
0x14005332c  mov     rdx, [rsp+1A8h+Src]; Src
0x140053334  call    memmove
0x140053339  jmp     short loc_140053342
0x14005333b  xor     edx, edx; Val
0x14005333d  call    memset
0x140053342  mov     rdx, [rsp+1A8h+var_138]
0x140053347  mov     eax, [rsp+1A8h+var_168]
0x14005334b  mov     [rdx], eax
0x14005334d  mov     eax, [rsp+1A8h+var_140]
0x140053351  mov     [rax+rdx], r15d
0x140053355  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005335c  lea     r8, WPP_GLOBAL_Control
0x140053363  cmp     rcx, r8
0x140053366  jz      short loc_14005339B
0x140053368  test    dword ptr [rcx+2Ch], 400h
0x14005336f  jz      short loc_14005339B
0x140053371  mov     [rsp+1A8h+var_180], rdx
0x140053376  mov     eax, [rsp+1A8h+var_16C]
0x14005337a  mov     dword ptr [rsp+1A8h+var_188], eax
0x14005337e  mov     r9, [rsp+1A8h+var_C0]
0x140053386  mov     rcx, [rcx+18h]
0x14005338a  call    WPP_SF_qLq
0x14005338f  mov     rdx, [rsp+1A8h+var_138]
0x140053394  lea     r8, WPP_GLOBAL_Control
0x14005339b  lea     r9, [rdx+rbx]
0x14005339f  mov     [rsp+1A8h+DestinationString.Buffer], r9
0x1400533a7  cmp     [rsp+1A8h+var_177], dil
0x1400533ac  jnz     loc_140053567
0x1400533b2  mov     eax, [rsp+1A8h+var_174]
0x1400533b6  add     eax, 0FFFFFFFEh
0x1400533b9  cmp     r13d, eax
0x1400533bc  jg      short loc_14005341F
0x1400533be  add     r15w, 2
0x1400533c3  mov     [rsp+1A8h+DestinationString.MaximumLength], r15w
0x1400533cc  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400533d3  cmp     rcx, r8
0x1400533d6  jz      short loc_1400533FE
0x1400533d8  test    dword ptr [rcx+2Ch], 400h
0x1400533df  jz      short loc_1400533FE
0x1400533e1  movzx   eax, r15w
0x1400533e5  mov     edx, 10h
0x1400533ea  mov     dword ptr [rsp+1A8h+var_188], eax
0x1400533ee  lea     r8, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids
0x1400533f5  mov     rcx, [rcx+18h]
0x1400533f9  call    WPP_SF_qD
0x1400533fe  xor     r8d, r8d; AllocateDestinationString
0x140053401  lea     rdx, [rsp+1A8h+OemString]; SourceString
0x140053409  lea     rcx, [rsp+1A8h+DestinationString]; DestinationString
0x140053411  call    cs:__imp_RtlOemStringToUnicodeString
0x140053418  nop     dword ptr [rax+rax+00h]
0x14005341d  jmp     short loc_140053479
0x14005341f  mov     [rsp+1A8h+DestinationString.MaximumLength], r15w
0x140053428  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005342f  cmp     rcx, r8
0x140053432  jz      short loc_14005345A
0x140053434  test    dword ptr [rcx+2Ch], 400h
0x14005343b  jz      short loc_14005345A
0x14005343d  movzx   eax, r15w
0x140053441  mov     edx, 11h
0x140053446  mov     dword ptr [rsp+1A8h+var_188], eax
0x14005344a  lea     r8, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids
0x140053451  mov     rcx, [rcx+18h]
0x140053455  call    WPP_SF_qD
0x14005345a  xor     r8d, r8d; AllocateDestinationString
0x14005345d  lea     rdx, [rsp+1A8h+OemString]; SourceString
0x140053465  lea     rcx, [rsp+1A8h+DestinationString]; DestinationString
0x14005346d  call    cs:__imp_RtlOemStringToCountedUnicodeString
0x140053474  nop     dword ptr [rax+rax+00h]
0x140053479  test    eax, eax
0x14005347b  jz      short loc_140053485
0x14005347d  mov     [rsp+1A8h+DestinationString.Length], di
0x140053485  cmp     [rsp+1A8h+arg_8], 3
0x14005348d  jnz     loc_140053590
0x140053493  mov     r15, [rsp+1A8h+var_138]
0x140053498  cmp     [rsp+1A8h+var_178], dil
0x14005349d  jnz     loc_140053595
0x1400534a3  xorps   xmm0, xmm0
0x1400534a6  movups  xmmword ptr [rsp+1A8h+SourceString.Length], xmm0
0x1400534ab  mov     qword ptr [rsp+1A8h+var_E8.Length], 180000h
0x1400534b7  lea     rbx, [r15+46h]
0x1400534bb  mov     [rsp+1A8h+SourceString.Buffer], rbx
0x1400534c3  movsx   eax, byte ptr [r15+44h]
0x1400534c8  mov     [rsp+1A8h+SourceString.MaximumLength], ax
0x1400534cd  mov     [rsp+1A8h+SourceString.Length], ax
0x1400534d2  lea     rax, [rsp+1A8h+var_58]
0x1400534da  mov     [rsp+1A8h+var_E8.Buffer], rax
0x1400534e2  xor     r8d, r8d; AllocateDestinationString
0x1400534e5  lea     rdx, [rsp+1A8h+SourceString]; SourceString
0x1400534ea  lea     rcx, [rsp+1A8h+var_E8]; DestinationString
0x1400534f2  call    cs:__imp_RtlOemStringToUnicodeString
0x1400534f9  nop     dword ptr [rax+rax+00h]
0x1400534fe  test    eax, eax
0x140053500  jnz     short loc_140053528
0x140053502  mov     al, byte ptr [rsp+1A8h+var_E8.Length]
0x140053509  mov     [r15+44h], al
0x14005350d  movzx   r8d, [rsp+1A8h+var_E8.Length]; Size
0x140053516  mov     rdx, [rsp+1A8h+var_E8.Buffer]; Src
0x14005351e  mov     rcx, rbx; void *
0x140053521  call    memmove
0x140053526  jmp     short loc_14005352C
0x140053528  mov     [r15+44h], dil
0x14005352c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140053533  lea     rax, WPP_GLOBAL_Control
0x14005353a  cmp     rcx, rax
0x14005353d  jz      short loc_140053595
0x14005353f  test    dword ptr [rcx+2Ch], 400h
  ... truncated ...
```
