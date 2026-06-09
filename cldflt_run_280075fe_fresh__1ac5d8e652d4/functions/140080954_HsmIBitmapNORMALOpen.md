# HsmIBitmapNORMALOpen

- ea: `0x140080954`
- end: `0x14008112c`
- name: `HsmIBitmapNORMALOpen`
- size: `2008`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1400808f8`

## callees

- `0x140003c50`
- `0x140008b74`
- `0x140009d14`
- `0x14000a120`
- `0x14001880c`
- `0x14001886c`
- `0x1400189dc`
- `0x14001e280`
- `0x14003659c`
- `0x1400677b4`
- `0x140080954`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x140080fba`
- `ntoskrnl!RtlComputeCrc32` at `0x140080fba`
- `ntoskrnl!ExAllocatePool2` at `0x140080dbc`
- `ntoskrnl!ExAllocatePool2` at `0x140080f18`
- `ntoskrnl!ExAllocatePool2` at `0x140080fe9`
- `ntoskrnl!ExAllocatePool2` at `0x140080dbc`
- `ntoskrnl!ExAllocatePool2` at `0x140080f18`
- `ntoskrnl!ExAllocatePool2` at `0x140080fe9`
- `FLTMGR!FltInitializePushLock` at `0x140080eb7`
- `FLTMGR!FltInitializePushLock` at `0x140080ec7`
- `FLTMGR!FltInitializePushLock` at `0x140080eb7`
- `FLTMGR!FltInitializePushLock` at `0x140080ec7`

## pseudocode

```c
__int64 __fastcall HsmIBitmapNORMALOpen(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        unsigned int a6,
        __int64 *a7)
{
  __int64 v9; // rbx
  unsigned int v10; // r15d
  unsigned __int16 *v11; // r14
  unsigned int v12; // edi
  __int64 v13; // rax
  unsigned int v14; // r8d
  unsigned __int16 v15; // r9
  unsigned __int64 v16; // rdx
  unsigned int v17; // eax
  int v18; // r8d
  PDEVICE_OBJECT v19; // rcx
  int v20; // edx
  __int64 v21; // rax
  unsigned int v22; // r8d
  unsigned __int16 v23; // r9
  unsigned __int64 v24; // rdx
  unsigned int v25; // eax
  __int64 v26; // rax
  unsigned int v27; // r8d
  unsigned __int16 v28; // r9
  unsigned __int64 v29; // rdx
  unsigned int v30; // eax
  char *v31; // r15
  unsigned int v32; // r14d
  int v33; // ebx
  __int64 v34; // rax
  unsigned int v35; // r8d
  unsigned __int16 v36; // r9
  unsigned __int64 v37; // rdx
  unsigned int v38; // eax
  __int64 Pool2; // rax
  __int64 v40; // rsi
  int v41; // r8d
  _QWORD *v42; // rdx
  unsigned int v43; // ecx
  __int64 *v44; // rbx
  int v45; // eax
  __int64 v46; // r8
  int v47; // r12d
  void *v48; // rax
  int v49; // r8d
  __int64 v50; // rcx
  __int64 v51; // rbx
  void *v52; // rax
  int v53; // r8d
  unsigned __int8 v55; // [rsp+58h] [rbp-31h]
  unsigned __int8 v56; // [rsp+59h] [rbp-30h]
  unsigned __int16 *v57; // [rsp+60h] [rbp-29h]
  __int64 v58; // [rsp+68h] [rbp-21h]
  __int64 Parameter[8]; // [rsp+88h] [rbp-1h] BYREF
  char v61; // [rsp+E8h] [rbp+5Fh]
  int v62; // [rsp+F0h] [rbp+67h] BYREF

  v62 = a4;
  v61 = a3;
  v56 = 0;
  v55 = 0;
  v58 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qis(WPP_GLOBAL_Control->AttachedDevice, 93, a1, a1, a2, (__int64)&v62);
  }
  v9 = a5;
  v10 = a6;
  v11 = (unsigned __int16 *)(a5 + 14);
  v57 = (unsigned __int16 *)(a5 + 14);
  if ( a6 >= 0x18 )
  {
    v13 = *v11;
    if ( (unsigned __int16)v13 > 2u
      && (v14 = *(_DWORD *)(a5 + 8), v14 >= 0x28)
      && (v15 = *(_WORD *)(a5 + 32), v15 < 0x12u)
      && ((v16 = *(unsigned int *)(a5 + 36), !(_DWORD)v16) || v16 >= 8 * v13 + 16 && (unsigned int)v16 <= v14)
      && (v17 = *(unsigned __int16 *)(a5 + 34), v17 <= v14)
      && v17 + (unsigned int)v16 <= v14
      && v17 + (unsigned int)v16 >= (unsigned int)v16
      && v15 == 7
      && (_WORD)v17 == 1 )
    {
      v12 = 0;
      v56 = *(_BYTE *)(v16 + a5);
    }
    else
    {
      v12 = -1073741275;
    }
    v57 = (unsigned __int16 *)(a5 + 14);
  }
  else
  {
    v12 = -1073741275;
  }
  HsmDbgBreakOnStatus(v12);
  if ( (v12 & 0x80000000) != 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v20 = 94;
LABEL_26:
      WPP_SF_qisd(v19->AttachedDevice, v20, v18, a2, a3, (__int64)&v62, v12);
      return v12;
    }
    return v12;
  }
  if ( v10 >= 0x18
    && (v21 = *v11, (unsigned __int16)v21 > 1u)
    && (v22 = *(_DWORD *)(v9 + 8), v22 >= 0x20)
    && (v23 = *(_WORD *)(v9 + 24), v23 < 0x12u)
    && ((v24 = *(unsigned int *)(v9 + 28), !(_DWORD)v24) || v24 >= 8 * v21 + 16 && (unsigned int)v24 <= v22)
    && (v25 = *(unsigned __int16 *)(v9 + 26), v25 <= v22)
    && v25 + (unsigned int)v24 <= v22
    && v25 + (unsigned int)v24 >= (unsigned int)v24
    && v23 == 7
    && (_WORD)v25 == 1 )
  {
    v12 = 0;
    v55 = *(_BYTE *)(v24 + v9);
  }
  else
  {
    v12 = -1073741275;
  }
  HsmDbgBreakOnStatus(v12);
  if ( (v12 & 0x80000000) == 0 )
  {
    if ( v10 >= 0x18
      && (v26 = *v11, (unsigned __int16)v26 > 3u)
      && (v27 = *(_DWORD *)(v9 + 8), v27 >= 0x30)
      && (v28 = *(_WORD *)(v9 + 40), v28 < 0x12u)
      && ((v29 = *(unsigned int *)(v9 + 44), !(_DWORD)v29) || v29 >= 8 * v26 + 16 && (unsigned int)v29 <= v27)
      && (v30 = *(unsigned __int16 *)(v9 + 42), v30 <= v27)
      && v30 + (unsigned int)v29 >= (unsigned int)v29
      && v30 + (unsigned int)v29 <= v27
      && v28 == 6
      && v30 == 8 )
    {
      v12 = 0;
      v58 = *(_QWORD *)(v29 + v9);
    }
    else
    {
      v12 = -1073741275;
    }
    HsmDbgBreakOnStatus(v12);
    if ( (v12 & 0x80000000) != 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v20 = 96;
        goto LABEL_26;
      }
      return v12;
    }
    v31 = 0;
    v32 = 0;
    if ( a6 >= 0x18 )
    {
      v34 = *v57;
      if ( (unsigned __int16)v34 <= 4u
        || (v35 = *(_DWORD *)(v9 + 8), v35 < 0x38)
        || (v36 = *(_WORD *)(v9 + 48), v36 >= 0x12u)
        || (v37 = *(unsigned int *)(v9 + 52), (_DWORD)v37) && (v37 < 8 * v34 + 16 || (unsigned int)v37 > v35)
        || (v38 = *(unsigned __int16 *)(v9 + 50), v38 > v35)
        || v38 + (unsigned int)v37 > v35
        || v36 != 17
        || v38 + (unsigned int)v37 < (unsigned int)v37 )
      {
        v33 = -1073741275;
      }
      else
      {
        if ( (_DWORD)v37 && (_WORD)v38 )
          v31 = (char *)(v9 + v37);
        v32 = *(unsigned __int16 *)(v9 + 50);
        v33 = 0;
      }
      if ( v33 < 0 )
        v32 = 0;
    }
    else
    {
      v33 = -1073741275;
    }
    HsmDbgBreakOnStatus((unsigned int)v33);
    v12 = 0;
    if ( v33 != -1073741275 )
      v12 = v33;
    if ( v32 > 0x1000 )
    {
      v12 = -1073688830;
      HsmDbgBreakOnStatus(3221278466LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_DDd(
          WPP_GLOBAL_Control->AttachedDevice,
          98,
          WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids,
          v32,
          4096,
          -1073688830);
      }
      return v12;
    }
    if ( v55 && a3 > HsmiBitmapNORMALComputeMaxUserFileSize(1) )
    {
      v12 = -1073741595;
      HsmDbgBreakOnStatus(3221225701LL);
      return v12;
    }
    Pool2 = ExAllocatePool2(64, 168, 1833071432);
    v40 = Pool2;
    if ( !Pool2 )
    {
      v12 = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qisd(WPP_GLOBAL_Control->AttachedDevice, 99, v41, a2, a3, (__int64)&v62, 154);
      }
      return v12;
    }
    v42 = (_QWORD *)(Pool2 + 112);
    v43 = *(_DWORD *)(Pool2 + 16) & 0xFFFFFFF8;
    v44 = a7;
    *(_QWORD *)(Pool2 + 8) = a3;
    *(_QWORD *)Pool2 = a2;
    *v44 = 0;
    *(_DWORD *)(Pool2 + 16) = v43 ^ ((unsigned __int16)v43 ^ (v55 << 6)) & 0xFC0;
    *(_QWORD *)(Pool2 + 40) = a1;
    v45 = *(_DWORD *)(Pool2 + 16);
    *(_DWORD *)(v40 + 20) = 1;
    *(_DWORD *)(v40 + 16) = v45 ^ ((unsigned __int16)v45 ^ (unsigned __int16)(v56 << 12)) & 0x7000;
    *(_DWORD *)(v40 + 32) = v62;
    *(_QWORD *)(v40 + 144) = v58;
    *(_QWORD *)(v40 + 120) = v40 + 112;
    *(_QWORD *)(v40 + 112) = v40 + 112;
    *(_QWORD *)(v40 + 136) = v40 + 128;
    *(_QWORD *)(v40 + 128) = v40 + 128;
    v46 = *(_QWORD *)(v40 + 112);
    if ( *(_QWORD *)(v46 + 8) != v40 + 112 )
      __fastfail(3u);
    *(_QWORD *)(v40 + 72) = v46;
    *(_QWORD *)(v40 + 80) = v42;
    *(_QWORD *)(v46 + 8) = v40 + 72;
    *v42 = v40 + 72;
    FltInitializePushLock((PULONG_PTR)(v40 + 48));
    FltInitializePushLock((PULONG_PTR)(v40 + 64));
    if ( v31 && v32 - 1 <= 0xFFE )
    {
      v47 = *(_DWORD *)&v31[v32 - 4];
      if ( v47 == -1 && v32 == 4 )
      {
        *(_DWORD *)(v40 + 16) |= 0x10u;
LABEL_115:
        v44 = a7;
        goto LABEL_123;
      }
      v48 = (void *)ExAllocatePool2(256, 4096, 1833071432);
      *(_QWORD *)(v40 + 56) = v48;
      if ( v48 )
      {
        memmove(v48, v31, v32);
        while ( v32 < 0xFFC )
        {
          v50 = v32;
          v32 += 4;
          *(_DWORD *)(v50 + *(_QWORD *)(v40 + 56)) = v47;
        }
        v51 = *(_QWORD *)(v40 + 56);
        *(_DWORD *)(v51 + 4092) = RtlComputeCrc32(0, (PUCHAR)v51, 0xFFCu);
        goto LABEL_115;
      }
      v12 = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qisd(WPP_GLOBAL_Control->AttachedDevice, 100, v49, a2, v61, (__int64)&v62, 154);
      }
    }
    else
    {
      v52 = (void *)ExAllocatePool2(256, 4096, 1833071432);
      *(_QWORD *)(v40 + 56) = v52;
      if ( v52 )
      {
        memmove(v52, v31, v32);
LABEL_123:
        Parameter[0] = 0;
        HsmiBitmapNORMALGetNumberOfPlexCopies(v40);
        HsmExpandKernelStackAndCallout(HsmiBitmapNORMALOpenOnDiskCallout, Parameter);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qisdil(
            WPP_GLOBAL_Control->AttachedDevice,
            102,
            *(_QWORD *)v40,
            v40,
            *(_QWORD *)v40,
            v40 + 32,
            (*(_DWORD *)(v40 + 16) >> 12) & 7,
            *(_QWORD *)(v40 + 144),
            *(_DWORD *)(v40 + 24));
        }
        *v44 = v40;
        return v12;
      }
      v12 = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qisd(WPP_GLOBAL_Control->AttachedDevice, 101, v53, a2, a3, (__int64)&v62, 154);
      }
    }
    HsmpBitmapRelease(v40);
    return v12;
  }
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v20 = 95;
    goto LABEL_26;
  }
  return v12;
}

```

## disassembly

```asm
0x140080954  mov     rax, rsp
0x140080957  mov     [rax+10h], rbx
0x14008095b  mov     [rax+20h], r9d
0x14008095f  mov     [rax+18h], r8
0x140080963  mov     [rax+8], rcx
0x140080967  push    rbp
0x140080968  push    rsi
0x140080969  push    rdi
0x14008096a  push    r12
0x14008096c  push    r13
0x14008096e  push    r14
0x140080970  push    r15
0x140080972  lea     rbp, [rax-47h]
0x140080976  sub     rsp, 90h
0x14008097d  xor     r10d, r10d
0x140080980  mov     r12, r8
0x140080983  mov     [rbp+3Fh+var_6F], r10b
0x140080987  mov     r13, rdx
0x14008098a  mov     [rbp+3Fh+var_70], r10b
0x14008098e  mov     r8, rcx
0x140080991  mov     [rbp+3Fh+var_60], r10
0x140080995  mov     rcx, cs:WPP_GLOBAL_Control
0x14008099c  lea     rax, WPP_GLOBAL_Control
0x1400809a3  lea     r11d, [r10+1]
0x1400809a7  cmp     rcx, rax
0x1400809aa  jz      short loc_1400809DF
0x1400809ac  mov     eax, [rcx+2Ch]
0x1400809af  test    r11b, al
0x1400809b2  jz      short loc_1400809DF
0x1400809b4  cmp     byte ptr [rcx+29h], 4
0x1400809b8  jb      short loc_1400809DF
0x1400809ba  mov     rcx, [rcx+18h]
0x1400809be  lea     rax, [rbp+3Fh+arg_18]
0x1400809c2  mov     qword ptr [rsp+0C0h+var_98], rax
0x1400809c7  lea     edx, [r10+5Dh]
0x1400809cb  mov     r9, r8
0x1400809ce  mov     [rsp+0C0h+var_A0], r13
0x1400809d3  call    WPP_SF_qis
0x1400809d8  xor     r10d, r10d
0x1400809db  lea     r11d, [r10+1]
0x1400809df  mov     rbx, [rbp+3Fh+arg_20]
0x1400809e3  mov     ecx, 2
0x1400809e8  mov     r15d, [rbp+3Fh+arg_28]
0x1400809ec  mov     esi, 0C0000225h
0x1400809f1  lea     r14, [rbx+0Eh]
0x1400809f5  mov     [rbp+3Fh+var_68], r14
0x1400809f9  lea     edi, [rcx+5]
0x1400809fc  cmp     r15d, 18h
0x140080a00  jnb     short loc_140080A06
0x140080a02  mov     edi, esi
0x140080a04  jmp     short loc_140080A70
0x140080a06  movzx   eax, word ptr [r14]
0x140080a0a  cmp     cx, ax
0x140080a0d  jnb     short loc_140080A6A
0x140080a0f  mov     r8d, [rbx+8]
0x140080a13  cmp     r8d, 28h ; '('
0x140080a17  jb      short loc_140080A6A
0x140080a19  movzx   r9d, word ptr [rbx+20h]
0x140080a1e  cmp     r9w, 12h
0x140080a23  jnb     short loc_140080A6A
0x140080a25  mov     edx, [rbx+24h]
0x140080a28  test    edx, edx
0x140080a2a  jz      short loc_140080A3E
0x140080a2c  lea     rcx, ds:10h[rax*8]
0x140080a34  cmp     rdx, rcx
0x140080a37  jb      short loc_140080A6A
0x140080a39  cmp     edx, r8d
0x140080a3c  ja      short loc_140080A6A
0x140080a3e  movzx   eax, word ptr [rbx+22h]
0x140080a42  cmp     eax, r8d
0x140080a45  ja      short loc_140080A6A
0x140080a47  lea     ecx, [rax+rdx]
0x140080a4a  cmp     ecx, r8d
0x140080a4d  ja      short loc_140080A6A
0x140080a4f  cmp     ecx, edx
0x140080a51  jb      short loc_140080A6A
0x140080a53  cmp     r9w, di
0x140080a57  jnz     short loc_140080A6A
0x140080a59  cmp     ax, r11w
0x140080a5d  jnz     short loc_140080A6A
0x140080a5f  mov     al, [rdx+rbx]
0x140080a62  mov     edi, r10d
0x140080a65  mov     [rbp+3Fh+var_6F], al
0x140080a68  jmp     short loc_140080A6C
0x140080a6a  mov     edi, esi
0x140080a6c  mov     [rbp+3Fh+var_68], r14
0x140080a70  mov     ecx, edi
0x140080a72  call    HsmDbgBreakOnStatus
0x140080a77  xor     r10d, r10d
0x140080a7a  test    edi, edi
0x140080a7c  jns     short loc_140080AD1
0x140080a7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140080a85  lea     rax, WPP_GLOBAL_Control
0x140080a8c  cmp     rcx, rax
0x140080a8f  jz      loc_14008110E
0x140080a95  mov     eax, [rcx+2Ch]
0x140080a98  test    al, 1
0x140080a9a  jz      loc_14008110E
0x140080aa0  cmp     byte ptr [rcx+29h], 2
0x140080aa4  jb      loc_14008110E
0x140080aaa  lea     edx, [r10+5Eh]
0x140080aae  mov     dword ptr [rsp+0C0h+var_90], edi
0x140080ab2  mov     rcx, [rcx+18h]
0x140080ab6  lea     rax, [rbp+3Fh+arg_18]
0x140080aba  mov     qword ptr [rsp+0C0h+var_98], rax
0x140080abf  mov     r9, r13
0x140080ac2  mov     [rsp+0C0h+var_A0], r12
0x140080ac7  call    WPP_SF_qisd
0x140080acc  jmp     loc_14008110E
0x140080ad1  cmp     r15d, 18h
0x140080ad5  jb      short loc_140080B47
0x140080ad7  movzx   eax, word ptr [r14]
0x140080adb  mov     r11d, 1
0x140080ae1  cmp     r11w, ax
0x140080ae5  jnb     short loc_140080B47
0x140080ae7  mov     r8d, [rbx+8]
0x140080aeb  cmp     r8d, 20h ; ' '
0x140080aef  jb      short loc_140080B47
0x140080af1  movzx   r9d, word ptr [rbx+18h]
0x140080af6  cmp     r9w, 12h
0x140080afb  jnb     short loc_140080B47
0x140080afd  mov     edx, [rbx+1Ch]
0x140080b00  test    edx, edx
0x140080b02  jz      short loc_140080B16
0x140080b04  lea     rcx, ds:10h[rax*8]
0x140080b0c  cmp     rdx, rcx
0x140080b0f  jb      short loc_140080B47
0x140080b11  cmp     edx, r8d
0x140080b14  ja      short loc_140080B47
0x140080b16  movzx   eax, word ptr [rbx+1Ah]
0x140080b1a  cmp     eax, r8d
0x140080b1d  ja      short loc_140080B47
0x140080b1f  lea     ecx, [rax+rdx]
0x140080b22  cmp     ecx, r8d
0x140080b25  ja      short loc_140080B47
0x140080b27  cmp     ecx, edx
0x140080b29  jb      short loc_140080B47
0x140080b2b  mov     ecx, 7
0x140080b30  cmp     r9w, cx
0x140080b34  jnz     short loc_140080B47
0x140080b36  cmp     ax, r11w
0x140080b3a  jnz     short loc_140080B47
0x140080b3c  mov     al, [rdx+rbx]
0x140080b3f  mov     edi, r10d
0x140080b42  mov     [rbp+3Fh+var_70], al
0x140080b45  jmp     short loc_140080B49
0x140080b47  mov     edi, esi
0x140080b49  mov     ecx, edi
0x140080b4b  call    HsmDbgBreakOnStatus
0x140080b50  xor     r10d, r10d
0x140080b53  test    edi, edi
0x140080b55  jns     short loc_140080B8C
0x140080b57  mov     rcx, cs:WPP_GLOBAL_Control
0x140080b5e  lea     rax, WPP_GLOBAL_Control
0x140080b65  cmp     rcx, rax
0x140080b68  jz      loc_14008110E
0x140080b6e  mov     eax, [rcx+2Ch]
0x140080b71  test    al, 1
0x140080b73  jz      loc_14008110E
0x140080b79  cmp     byte ptr [rcx+29h], 2
0x140080b7d  jb      loc_14008110E
0x140080b83  lea     edx, [r10+5Fh]
0x140080b87  jmp     loc_140080AAE
0x140080b8c  mov     ecx, 3
0x140080b91  cmp     r15d, 18h
0x140080b95  jb      short loc_140080BFD
0x140080b97  movzx   eax, word ptr [r14]
0x140080b9b  cmp     cx, ax
0x140080b9e  jnb     short loc_140080BFD
0x140080ba0  mov     r8d, [rbx+8]
0x140080ba4  cmp     r8d, 30h ; '0'
0x140080ba8  jb      short loc_140080BFD
0x140080baa  movzx   r9d, word ptr [rbx+28h]
0x140080baf  cmp     r9w, 12h
0x140080bb4  jnb     short loc_140080BFD
0x140080bb6  mov     edx, [rbx+2Ch]
0x140080bb9  test    edx, edx
0x140080bbb  jz      short loc_140080BCF
0x140080bbd  lea     rcx, ds:10h[rax*8]
0x140080bc5  cmp     rdx, rcx
0x140080bc8  jb      short loc_140080BFD
0x140080bca  cmp     edx, r8d
0x140080bcd  ja      short loc_140080BFD
0x140080bcf  movzx   eax, word ptr [rbx+2Ah]
0x140080bd3  cmp     eax, r8d
0x140080bd6  ja      short loc_140080BFD
0x140080bd8  lea     ecx, [rax+rdx]
0x140080bdb  cmp     ecx, edx
0x140080bdd  jb      short loc_140080BFD
0x140080bdf  cmp     ecx, r8d
0x140080be2  ja      short loc_140080BFD
0x140080be4  cmp     r9w, 6
0x140080be9  jnz     short loc_140080BFD
0x140080beb  cmp     eax, 8
0x140080bee  jnz     short loc_140080BFD
0x140080bf0  mov     rax, [rdx+rbx]
0x140080bf4  mov     edi, r10d
0x140080bf7  mov     [rbp+3Fh+var_60], rax
0x140080bfb  jmp     short loc_140080BFF
0x140080bfd  mov     edi, esi
0x140080bff  mov     ecx, edi
0x140080c01  call    HsmDbgBreakOnStatus
0x140080c06  xor     r10d, r10d
0x140080c09  test    edi, edi
0x140080c0b  jns     short loc_140080C42
0x140080c0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140080c14  lea     rax, WPP_GLOBAL_Control
0x140080c1b  cmp     rcx, rax
0x140080c1e  jz      loc_14008110E
0x140080c24  mov     eax, [rcx+2Ch]
0x140080c27  test    al, 1
0x140080c29  jz      loc_14008110E
0x140080c2f  cmp     byte ptr [rcx+29h], 2
0x140080c33  jb      loc_14008110E
0x140080c39  lea     edx, [r10+60h]
0x140080c3d  jmp     loc_140080AAE
0x140080c42  cmp     [rbp+3Fh+arg_28], 18h
0x140080c46  mov     r15, r10
0x140080c49  mov     r14d, r10d
0x140080c4c  jnb     short loc_140080C52
0x140080c4e  mov     ebx, esi
0x140080c50  jmp     short loc_140080CCB
0x140080c52  mov     rax, [rbp+3Fh+var_68]
0x140080c56  mov     ecx, 4
0x140080c5b  movzx   eax, word ptr [rax]
0x140080c5e  cmp     cx, ax
0x140080c61  jnb     short loc_140080CC3
0x140080c63  mov     r8d, [rbx+8]
0x140080c67  cmp     r8d, 38h ; '8'
0x140080c6b  jb      short loc_140080CC3
0x140080c6d  movzx   r9d, word ptr [rbx+30h]
0x140080c72  cmp     r9w, 12h
0x140080c77  jnb     short loc_140080CC3
0x140080c79  mov     edx, [rbx+34h]
0x140080c7c  test    edx, edx
0x140080c7e  jz      short loc_140080C92
0x140080c80  lea     rcx, ds:10h[rax*8]
0x140080c88  cmp     rdx, rcx
0x140080c8b  jb      short loc_140080CC3
0x140080c8d  cmp     edx, r8d
0x140080c90  ja      short loc_140080CC3
0x140080c92  movzx   eax, word ptr [rbx+32h]
0x140080c96  cmp     eax, r8d
0x140080c99  ja      short loc_140080CC3
0x140080c9b  lea     ecx, [rax+rdx]
0x140080c9e  cmp     ecx, r8d
0x140080ca1  ja      short loc_140080CC3
0x140080ca3  cmp     r9w, 11h
0x140080ca8  jnz     short loc_140080CC3
0x140080caa  cmp     ecx, edx
0x140080cac  jb      short loc_140080CC3
0x140080cae  test    edx, edx
0x140080cb0  jz      short loc_140080CBB
0x140080cb2  test    ax, ax
0x140080cb5  jz      short loc_140080CBB
0x140080cb7  lea     r15, [rbx+rdx]
0x140080cbb  mov     r14d, eax
0x140080cbe  mov     ebx, r10d
0x140080cc1  jmp     short loc_140080CC5
0x140080cc3  mov     ebx, esi
0x140080cc5  test    ebx, ebx
0x140080cc7  cmovs   r14d, r10d
0x140080ccb  mov     ecx, ebx
0x140080ccd  call    HsmDbgBreakOnStatus
0x140080cd2  xor     ecx, ecx
0x140080cd4  cmp     ebx, esi
0x140080cd6  mov     edi, ecx
0x140080cd8  cmovnz  edi, ebx
0x140080cdb  test    edi, edi
0x140080cdd  jns     short loc_140080D15
0x140080cdf  mov     rcx, cs:WPP_GLOBAL_Control
0x140080ce6  lea     rax, WPP_GLOBAL_Control
0x140080ced  cmp     rcx, rax
0x140080cf0  jz      loc_14008110E
0x140080cf6  mov     eax, [rcx+2Ch]
0x140080cf9  test    al, 1
0x140080cfb  jz      loc_14008110E
0x140080d01  cmp     byte ptr [rcx+29h], 2
0x140080d05  jb      loc_14008110E
0x140080d0b  mov     edx, 61h ; 'a'
0x140080d10  jmp     loc_140080AAE
0x140080d15  cmp     r14d, 1000h
0x140080d1c  jbe     short loc_140080D7F
0x140080d1e  mov     edi, 0C000CF02h
0x140080d23  mov     ecx, edi
0x140080d25  call    HsmDbgBreakOnStatus
0x140080d2a  mov     rcx, cs:WPP_GLOBAL_Control
0x140080d31  lea     rax, WPP_GLOBAL_Control
0x140080d38  cmp     rcx, rax
0x140080d3b  jz      loc_14008110E
0x140080d41  mov     eax, [rcx+2Ch]
0x140080d44  test    al, 1
0x140080d46  jz      loc_14008110E
0x140080d4c  cmp     byte ptr [rcx+29h], 2
0x140080d50  jb      loc_14008110E
0x140080d56  mov     rcx, [rcx+18h]
0x140080d5a  lea     r8, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids
0x140080d61  mov     edx, 62h ; 'b'
0x140080d66  mov     [rsp+0C0h+var_98], edi
0x140080d6a  mov     r9d, r14d
  ... truncated ...
```
