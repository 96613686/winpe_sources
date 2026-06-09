# HsmIBitmapNORMALOpen

- ea: `0x140080af4`
- end: `0x1400812cc`
- name: `HsmIBitmapNORMALOpen`
- size: `2008`
- prototype: `__int64 __fastcall(__int64, __int64, signed __int64, int, __int64, unsigned int, __int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140080a98`

## callees

- `0x140003c50`
- `0x140008b74`
- `0x140009d14`
- `0x14000a120`
- `0x14001888c`
- `0x1400188ec`
- `0x140018a5c`
- `0x14001e300`
- `0x14003659c`
- `0x1400678d4`
- `0x140080af4`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x14008115a`
- `ntoskrnl!RtlComputeCrc32` at `0x14008115a`
- `ntoskrnl!ExAllocatePool2` at `0x140080f5c`
- `ntoskrnl!ExAllocatePool2` at `0x1400810b8`
- `ntoskrnl!ExAllocatePool2` at `0x140081189`
- `ntoskrnl!ExAllocatePool2` at `0x140080f5c`
- `ntoskrnl!ExAllocatePool2` at `0x1400810b8`
- `ntoskrnl!ExAllocatePool2` at `0x140081189`
- `FLTMGR!FltInitializePushLock` at `0x140081057`
- `FLTMGR!FltInitializePushLock` at `0x140081067`
- `FLTMGR!FltInitializePushLock` at `0x140081057`
- `FLTMGR!FltInitializePushLock` at `0x140081067`

## pseudocode

```c
__int64 __fastcall HsmIBitmapNORMALOpen(
        __int64 a1,
        __int64 a2,
        signed __int64 a3,
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
    HsmDbgBreakOnStatus(v33);
    v12 = 0;
    if ( v33 != -1073741275 )
      v12 = v33;
    if ( v32 > 0x1000 )
    {
      v12 = -1073688830;
      HsmDbgBreakOnStatus(-1073688830);
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
    if ( v55 && a3 > (__int64)HsmiBitmapNORMALComputeMaxUserFileSize(1, 1 << v55) )
    {
      v12 = -1073741595;
      HsmDbgBreakOnStatus(-1073741595);
      return v12;
    }
    Pool2 = ExAllocatePool2(64, 168, 1833071432);
    v40 = Pool2;
    if ( !Pool2 )
    {
      v12 = -1073741670;
      HsmDbgBreakOnStatus(-1073741670);
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
      HsmDbgBreakOnStatus(-1073741670);
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
        HsmExpandKernelStackAndCallout(HsmiBitmapNORMALOpenOnDiskCallout, (NTSTATUS *)Parameter);
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
      HsmDbgBreakOnStatus(-1073741670);
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
0x140080af4  mov     rax, rsp
0x140080af7  mov     [rax+10h], rbx
0x140080afb  mov     [rax+20h], r9d
0x140080aff  mov     [rax+18h], r8
0x140080b03  mov     [rax+8], rcx
0x140080b07  push    rbp
0x140080b08  push    rsi
0x140080b09  push    rdi
0x140080b0a  push    r12
0x140080b0c  push    r13
0x140080b0e  push    r14
0x140080b10  push    r15
0x140080b12  lea     rbp, [rax-47h]
0x140080b16  sub     rsp, 90h
0x140080b1d  xor     r10d, r10d
0x140080b20  mov     r12, r8
0x140080b23  mov     [rbp+3Fh+var_6F], r10b
0x140080b27  mov     r13, rdx
0x140080b2a  mov     [rbp+3Fh+var_70], r10b
0x140080b2e  mov     r8, rcx
0x140080b31  mov     [rbp+3Fh+var_60], r10
0x140080b35  mov     rcx, cs:WPP_GLOBAL_Control
0x140080b3c  lea     rax, WPP_GLOBAL_Control
0x140080b43  lea     r11d, [r10+1]
0x140080b47  cmp     rcx, rax
0x140080b4a  jz      short loc_140080B7F
0x140080b4c  mov     eax, [rcx+2Ch]
0x140080b4f  test    r11b, al
0x140080b52  jz      short loc_140080B7F
0x140080b54  cmp     byte ptr [rcx+29h], 4
0x140080b58  jb      short loc_140080B7F
0x140080b5a  mov     rcx, [rcx+18h]
0x140080b5e  lea     rax, [rbp+3Fh+arg_18]
0x140080b62  mov     qword ptr [rsp+0C0h+var_98], rax
0x140080b67  lea     edx, [r10+5Dh]
0x140080b6b  mov     r9, r8
0x140080b6e  mov     [rsp+0C0h+var_A0], r13
0x140080b73  call    WPP_SF_qis
0x140080b78  xor     r10d, r10d
0x140080b7b  lea     r11d, [r10+1]
0x140080b7f  mov     rbx, [rbp+3Fh+arg_20]
0x140080b83  mov     ecx, 2
0x140080b88  mov     r15d, [rbp+3Fh+arg_28]
0x140080b8c  mov     esi, 0C0000225h
0x140080b91  lea     r14, [rbx+0Eh]
0x140080b95  mov     [rbp+3Fh+var_68], r14
0x140080b99  lea     edi, [rcx+5]
0x140080b9c  cmp     r15d, 18h
0x140080ba0  jnb     short loc_140080BA6
0x140080ba2  mov     edi, esi
0x140080ba4  jmp     short loc_140080C10
0x140080ba6  movzx   eax, word ptr [r14]
0x140080baa  cmp     cx, ax
0x140080bad  jnb     short loc_140080C0A
0x140080baf  mov     r8d, [rbx+8]
0x140080bb3  cmp     r8d, 28h ; '('
0x140080bb7  jb      short loc_140080C0A
0x140080bb9  movzx   r9d, word ptr [rbx+20h]
0x140080bbe  cmp     r9w, 12h
0x140080bc3  jnb     short loc_140080C0A
0x140080bc5  mov     edx, [rbx+24h]
0x140080bc8  test    edx, edx
0x140080bca  jz      short loc_140080BDE
0x140080bcc  lea     rcx, ds:10h[rax*8]
0x140080bd4  cmp     rdx, rcx
0x140080bd7  jb      short loc_140080C0A
0x140080bd9  cmp     edx, r8d
0x140080bdc  ja      short loc_140080C0A
0x140080bde  movzx   eax, word ptr [rbx+22h]
0x140080be2  cmp     eax, r8d
0x140080be5  ja      short loc_140080C0A
0x140080be7  lea     ecx, [rax+rdx]
0x140080bea  cmp     ecx, r8d
0x140080bed  ja      short loc_140080C0A
0x140080bef  cmp     ecx, edx
0x140080bf1  jb      short loc_140080C0A
0x140080bf3  cmp     r9w, di
0x140080bf7  jnz     short loc_140080C0A
0x140080bf9  cmp     ax, r11w
0x140080bfd  jnz     short loc_140080C0A
0x140080bff  mov     al, [rdx+rbx]
0x140080c02  mov     edi, r10d
0x140080c05  mov     [rbp+3Fh+var_6F], al
0x140080c08  jmp     short loc_140080C0C
0x140080c0a  mov     edi, esi
0x140080c0c  mov     [rbp+3Fh+var_68], r14
0x140080c10  mov     ecx, edi
0x140080c12  call    HsmDbgBreakOnStatus
0x140080c17  xor     r10d, r10d
0x140080c1a  test    edi, edi
0x140080c1c  jns     short loc_140080C71
0x140080c1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140080c25  lea     rax, WPP_GLOBAL_Control
0x140080c2c  cmp     rcx, rax
0x140080c2f  jz      loc_1400812AE
0x140080c35  mov     eax, [rcx+2Ch]
0x140080c38  test    al, 1
0x140080c3a  jz      loc_1400812AE
0x140080c40  cmp     byte ptr [rcx+29h], 2
0x140080c44  jb      loc_1400812AE
0x140080c4a  lea     edx, [r10+5Eh]
0x140080c4e  mov     dword ptr [rsp+0C0h+var_90], edi
0x140080c52  mov     rcx, [rcx+18h]
0x140080c56  lea     rax, [rbp+3Fh+arg_18]
0x140080c5a  mov     qword ptr [rsp+0C0h+var_98], rax
0x140080c5f  mov     r9, r13
0x140080c62  mov     [rsp+0C0h+var_A0], r12
0x140080c67  call    WPP_SF_qisd
0x140080c6c  jmp     loc_1400812AE
0x140080c71  cmp     r15d, 18h
0x140080c75  jb      short loc_140080CE7
0x140080c77  movzx   eax, word ptr [r14]
0x140080c7b  mov     r11d, 1
0x140080c81  cmp     r11w, ax
0x140080c85  jnb     short loc_140080CE7
0x140080c87  mov     r8d, [rbx+8]
0x140080c8b  cmp     r8d, 20h ; ' '
0x140080c8f  jb      short loc_140080CE7
0x140080c91  movzx   r9d, word ptr [rbx+18h]
0x140080c96  cmp     r9w, 12h
0x140080c9b  jnb     short loc_140080CE7
0x140080c9d  mov     edx, [rbx+1Ch]
0x140080ca0  test    edx, edx
0x140080ca2  jz      short loc_140080CB6
0x140080ca4  lea     rcx, ds:10h[rax*8]
0x140080cac  cmp     rdx, rcx
0x140080caf  jb      short loc_140080CE7
0x140080cb1  cmp     edx, r8d
0x140080cb4  ja      short loc_140080CE7
0x140080cb6  movzx   eax, word ptr [rbx+1Ah]
0x140080cba  cmp     eax, r8d
0x140080cbd  ja      short loc_140080CE7
0x140080cbf  lea     ecx, [rax+rdx]
0x140080cc2  cmp     ecx, r8d
0x140080cc5  ja      short loc_140080CE7
0x140080cc7  cmp     ecx, edx
0x140080cc9  jb      short loc_140080CE7
0x140080ccb  mov     ecx, 7
0x140080cd0  cmp     r9w, cx
0x140080cd4  jnz     short loc_140080CE7
0x140080cd6  cmp     ax, r11w
0x140080cda  jnz     short loc_140080CE7
0x140080cdc  mov     al, [rdx+rbx]
0x140080cdf  mov     edi, r10d
0x140080ce2  mov     [rbp+3Fh+var_70], al
0x140080ce5  jmp     short loc_140080CE9
0x140080ce7  mov     edi, esi
0x140080ce9  mov     ecx, edi
0x140080ceb  call    HsmDbgBreakOnStatus
0x140080cf0  xor     r10d, r10d
0x140080cf3  test    edi, edi
0x140080cf5  jns     short loc_140080D2C
0x140080cf7  mov     rcx, cs:WPP_GLOBAL_Control
0x140080cfe  lea     rax, WPP_GLOBAL_Control
0x140080d05  cmp     rcx, rax
0x140080d08  jz      loc_1400812AE
0x140080d0e  mov     eax, [rcx+2Ch]
0x140080d11  test    al, 1
0x140080d13  jz      loc_1400812AE
0x140080d19  cmp     byte ptr [rcx+29h], 2
0x140080d1d  jb      loc_1400812AE
0x140080d23  lea     edx, [r10+5Fh]
0x140080d27  jmp     loc_140080C4E
0x140080d2c  mov     ecx, 3
0x140080d31  cmp     r15d, 18h
0x140080d35  jb      short loc_140080D9D
0x140080d37  movzx   eax, word ptr [r14]
0x140080d3b  cmp     cx, ax
0x140080d3e  jnb     short loc_140080D9D
0x140080d40  mov     r8d, [rbx+8]
0x140080d44  cmp     r8d, 30h ; '0'
0x140080d48  jb      short loc_140080D9D
0x140080d4a  movzx   r9d, word ptr [rbx+28h]
0x140080d4f  cmp     r9w, 12h
0x140080d54  jnb     short loc_140080D9D
0x140080d56  mov     edx, [rbx+2Ch]
0x140080d59  test    edx, edx
0x140080d5b  jz      short loc_140080D6F
0x140080d5d  lea     rcx, ds:10h[rax*8]
0x140080d65  cmp     rdx, rcx
0x140080d68  jb      short loc_140080D9D
0x140080d6a  cmp     edx, r8d
0x140080d6d  ja      short loc_140080D9D
0x140080d6f  movzx   eax, word ptr [rbx+2Ah]
0x140080d73  cmp     eax, r8d
0x140080d76  ja      short loc_140080D9D
0x140080d78  lea     ecx, [rax+rdx]
0x140080d7b  cmp     ecx, edx
0x140080d7d  jb      short loc_140080D9D
0x140080d7f  cmp     ecx, r8d
0x140080d82  ja      short loc_140080D9D
0x140080d84  cmp     r9w, 6
0x140080d89  jnz     short loc_140080D9D
0x140080d8b  cmp     eax, 8
0x140080d8e  jnz     short loc_140080D9D
0x140080d90  mov     rax, [rdx+rbx]
0x140080d94  mov     edi, r10d
0x140080d97  mov     [rbp+3Fh+var_60], rax
0x140080d9b  jmp     short loc_140080D9F
0x140080d9d  mov     edi, esi
0x140080d9f  mov     ecx, edi
0x140080da1  call    HsmDbgBreakOnStatus
0x140080da6  xor     r10d, r10d
0x140080da9  test    edi, edi
0x140080dab  jns     short loc_140080DE2
0x140080dad  mov     rcx, cs:WPP_GLOBAL_Control
0x140080db4  lea     rax, WPP_GLOBAL_Control
0x140080dbb  cmp     rcx, rax
0x140080dbe  jz      loc_1400812AE
0x140080dc4  mov     eax, [rcx+2Ch]
0x140080dc7  test    al, 1
0x140080dc9  jz      loc_1400812AE
0x140080dcf  cmp     byte ptr [rcx+29h], 2
0x140080dd3  jb      loc_1400812AE
0x140080dd9  lea     edx, [r10+60h]
0x140080ddd  jmp     loc_140080C4E
0x140080de2  cmp     [rbp+3Fh+arg_28], 18h
0x140080de6  mov     r15, r10
0x140080de9  mov     r14d, r10d
0x140080dec  jnb     short loc_140080DF2
0x140080dee  mov     ebx, esi
0x140080df0  jmp     short loc_140080E6B
0x140080df2  mov     rax, [rbp+3Fh+var_68]
0x140080df6  mov     ecx, 4
0x140080dfb  movzx   eax, word ptr [rax]
0x140080dfe  cmp     cx, ax
0x140080e01  jnb     short loc_140080E63
0x140080e03  mov     r8d, [rbx+8]
0x140080e07  cmp     r8d, 38h ; '8'
0x140080e0b  jb      short loc_140080E63
0x140080e0d  movzx   r9d, word ptr [rbx+30h]
0x140080e12  cmp     r9w, 12h
0x140080e17  jnb     short loc_140080E63
0x140080e19  mov     edx, [rbx+34h]
0x140080e1c  test    edx, edx
0x140080e1e  jz      short loc_140080E32
0x140080e20  lea     rcx, ds:10h[rax*8]
0x140080e28  cmp     rdx, rcx
0x140080e2b  jb      short loc_140080E63
0x140080e2d  cmp     edx, r8d
0x140080e30  ja      short loc_140080E63
0x140080e32  movzx   eax, word ptr [rbx+32h]
0x140080e36  cmp     eax, r8d
0x140080e39  ja      short loc_140080E63
0x140080e3b  lea     ecx, [rax+rdx]
0x140080e3e  cmp     ecx, r8d
0x140080e41  ja      short loc_140080E63
0x140080e43  cmp     r9w, 11h
0x140080e48  jnz     short loc_140080E63
0x140080e4a  cmp     ecx, edx
0x140080e4c  jb      short loc_140080E63
0x140080e4e  test    edx, edx
0x140080e50  jz      short loc_140080E5B
0x140080e52  test    ax, ax
0x140080e55  jz      short loc_140080E5B
0x140080e57  lea     r15, [rbx+rdx]
0x140080e5b  mov     r14d, eax
0x140080e5e  mov     ebx, r10d
0x140080e61  jmp     short loc_140080E65
0x140080e63  mov     ebx, esi
0x140080e65  test    ebx, ebx
0x140080e67  cmovs   r14d, r10d
0x140080e6b  mov     ecx, ebx
0x140080e6d  call    HsmDbgBreakOnStatus
0x140080e72  xor     ecx, ecx
0x140080e74  cmp     ebx, esi
0x140080e76  mov     edi, ecx
0x140080e78  cmovnz  edi, ebx
0x140080e7b  test    edi, edi
0x140080e7d  jns     short loc_140080EB5
0x140080e7f  mov     rcx, cs:WPP_GLOBAL_Control
0x140080e86  lea     rax, WPP_GLOBAL_Control
0x140080e8d  cmp     rcx, rax
0x140080e90  jz      loc_1400812AE
0x140080e96  mov     eax, [rcx+2Ch]
0x140080e99  test    al, 1
0x140080e9b  jz      loc_1400812AE
0x140080ea1  cmp     byte ptr [rcx+29h], 2
0x140080ea5  jb      loc_1400812AE
0x140080eab  mov     edx, 61h ; 'a'
0x140080eb0  jmp     loc_140080C4E
0x140080eb5  cmp     r14d, 1000h
0x140080ebc  jbe     short loc_140080F1F
0x140080ebe  mov     edi, 0C000CF02h
0x140080ec3  mov     ecx, edi
0x140080ec5  call    HsmDbgBreakOnStatus
0x140080eca  mov     rcx, cs:WPP_GLOBAL_Control
0x140080ed1  lea     rax, WPP_GLOBAL_Control
0x140080ed8  cmp     rcx, rax
0x140080edb  jz      loc_1400812AE
0x140080ee1  mov     eax, [rcx+2Ch]
0x140080ee4  test    al, 1
0x140080ee6  jz      loc_1400812AE
0x140080eec  cmp     byte ptr [rcx+29h], 2
0x140080ef0  jb      loc_1400812AE
0x140080ef6  mov     rcx, [rcx+18h]
0x140080efa  lea     r8, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids
0x140080f01  mov     edx, 62h ; 'b'
0x140080f06  mov     [rsp+0C0h+var_98], edi
0x140080f0a  mov     r9d, r14d
  ... truncated ...
```
