# CldiSyncTransferOrAckDataByObject

- ea: `0x14006c178`
- end: `0x14006c6e9`
- name: `CldiSyncTransferOrAckDataByObject`
- size: `1393`
- prototype: `__int64 __fastcall(__int64, __int64, int, char, __int64, __int64, PVOID VirtualAddress)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1400562ec`
- `0x14006c084`

## callees

- `0x140003c50`
- `0x14000efe4`
- `0x14000f088`
- `0x14000f13c`
- `0x14000fdec`
- `0x140034268`
- `0x140036120`
- `0x14003f660`
- `0x14006c178`
- `0x14006c6f0`

## import_xrefs

- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x14006c3cb`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x14006c3cb`
- `FLTMGR!FltReleasePushLockEx` at `0x14006c5f7`
- `FLTMGR!FltReleasePushLockEx` at `0x14006c5f7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006c377`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006c377`

## pseudocode

```c
__int64 __fastcall CldiSyncTransferOrAckDataByObject(
        __int64 a1,
        __int64 a2,
        int a3,
        char a4,
        __int64 a5,
        __int64 a6,
        PVOID VirtualAddress)
{
  __int64 v7; // r15
  __int64 v10; // r8
  unsigned int v11; // edi
  __int64 v12; // r8
  __int64 v13; // r9
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  LONGLONG v16; // rdi
  LONGLONG v17; // rbx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rsi
  int i; // r15d
  __int64 v23; // rcx
  __int64 v24; // r8
  int v25; // esi
  _QWORD *v26; // r11
  int v27; // r9d
  int v28; // r10d
  __int64 v29; // rbx
  int v30; // r8d
  int v31; // eax
  __int64 v32; // r10
  int v33; // esi
  __int64 v34; // r9
  LONGLONG v35; // rcx
  LONGLONG v36; // rdx
  LONGLONG v37; // rbx
  int v38; // edx
  unsigned int v39; // eax
  ULONG Length[2]; // [rsp+20h] [rbp-A8h]
  __int64 v42; // [rsp+30h] [rbp-98h]
  __int64 v43; // [rsp+38h] [rbp-90h]
  PVOID v44; // [rsp+40h] [rbp-88h]
  __int64 v45; // [rsp+48h] [rbp-80h]
  int v46; // [rsp+50h] [rbp-78h]
  int v47; // [rsp+60h] [rbp-68h]
  LONGLONG v48; // [rsp+68h] [rbp-60h]
  __int64 v49; // [rsp+70h] [rbp-58h]
  __int64 v50; // [rsp+78h] [rbp-50h]
  _QWORD *v51; // [rsp+80h] [rbp-48h]
  __int64 v52; // [rsp+90h] [rbp-38h]
  int v53[2]; // [rsp+98h] [rbp-30h]
  unsigned int v55; // [rsp+D8h] [rbp+10h]

  v55 = a2;
  v7 = *(_QWORD *)(a1 + 8);
  *(_QWORD *)v53 = v7;
  v10 = a1;
  if ( (*(_DWORD *)(**(_QWORD **)v7 + 28LL) & 2) != 0 )
  {
    v11 = -1073688821;
    HsmDbgBreakOnStatus(3221278475LL);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v15 = 13;
      v46 = -1073688821;
      v45 = v55;
      v44 = VirtualAddress;
      v43 = a6;
      v42 = a5;
      goto LABEL_78;
    }
    return v11;
  }
  if ( (a5 & 0xFFF) != 0 )
  {
    v11 = -1073688821;
    HsmDbgBreakOnStatus(3221278475LL);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v15 = 14;
      v46 = -1073688821;
      v45 = v55;
      v44 = VirtualAddress;
      v43 = a6;
      v42 = a5;
      goto LABEL_78;
    }
    return v11;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    Length[1] = HIDWORD(*(_QWORD *)(a1 + 8));
    WPP_SF_cqdiiqi(WPP_GLOBAL_Control->AttachedDevice, a2, a1);
    v10 = a1;
  }
  v16 = a5 / 4096;
  if ( a6 == -1 )
    v17 = 0x7FFFFFFFFFFFFLL;
  else
    v17 = (__int64)((a6 + 4095) & 0xFFFFFFFFFFFFF000uLL) / 4096;
  v48 = v17;
  v52 = v10 + 24;
  FltAcquirePushLockExclusiveEx(v10 + 24, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    LOBYTE(v20) = a4;
    WPP_SF_cqii(WPP_GLOBAL_Control->AttachedDevice, v18, v19, v20, v7, a5 / 4096, v17);
  }
  v21 = a1;
  FsRtlRemoveBaseMcbEntry((PBASE_MCB)(a1 + 32), v16, v17);
  for ( i = 0; i < 2; ++i )
  {
    if ( a3 < 0 )
    {
      v23 = i != 0 ? 72LL : 56LL;
      goto LABEL_31;
    }
    if ( !i )
    {
      if ( a4 )
        continue;
      v23 = 56;
LABEL_31:
      v24 = v21 + v23;
      v50 = v21 + v23;
      if ( !(v21 + v23) )
        continue;
      v25 = *(_DWORD *)(v24 + 4);
      v26 = (_QWORD *)(v24 + 8);
      v27 = 0;
      v51 = (_QWORD *)(v24 + 8);
      v49 = v24;
      v28 = v25 - 1;
      if ( v25 - 1 < 0 )
      {
        v51 = (_QWORD *)(v24 + 8);
      }
      else
      {
        v29 = *v26;
        do
        {
          v30 = (v28 + v27) >> 1;
          if ( *(_QWORD *)(v29 + 24LL * v30) >= v16 )
            v28 = v30 - 1;
          v31 = v30 + 1;
          if ( *(_QWORD *)(v29 + 24LL * v30) >= v16 )
            v31 = v27;
          v27 = v31;
        }
        while ( v31 <= v28 );
        v24 = v50;
        v17 = v48;
      }
      v32 = v24;
      if ( v27 == v25 || *(_QWORD *)(*v26 + 24LL * v27) > v16 )
        --v27;
      v33 = 0;
      if ( v27 >= 0 )
        v33 = v27;
      while ( 1 )
      {
        if ( v33 >= *(_DWORD *)(v24 + 4) || v17 <= 0 )
        {
LABEL_68:
          v21 = a1;
          goto LABEL_69;
        }
        v34 = 3LL * v33;
        v35 = *(_QWORD *)(*v26 + 24LL * v33);
        v36 = v35 + *(_QWORD *)(*v26 + 24LL * v33 + 8);
        if ( v16 < v36 )
          break;
LABEL_66:
        v24 = v50;
        ++v33;
        v26 = v51;
        v32 = v49;
      }
      v37 = v16 + v17;
      if ( v35 >= v37 )
      {
LABEL_65:
        v17 = v48;
        goto LABEL_66;
      }
      if ( v16 > v35 )
      {
        v37 = v16;
      }
      else
      {
        if ( v36 < v37 )
          v37 = v35 + *(_QWORD *)(*v26 + 24LL * v33 + 8);
        if ( v37 <= v35 || v37 >= v36 )
        {
LABEL_59:
          if ( v37 != v16 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              Length[0] = v33;
              WPP_SF_qddii(
                WPP_GLOBAL_Control->AttachedDevice,
                *v26,
                v24,
                v24,
                *(_QWORD *)Length,
                *(_DWORD *)(v24 + 4),
                *(_QWORD *)(*v26 + 8 * v34),
                *(_QWORD *)(*v26 + 8 * v34 + 8));
            }
            v48 += v16 - v37;
            v16 = v37;
            CldiSyncRemovePendingRange(v49, v33);
          }
          goto LABEL_65;
        }
      }
      v47 = CldiSyncSplitPendingRange(v32, (unsigned int)v33, v37);
      HsmDbgBreakOnStatus((unsigned int)v47);
      if ( v47 < 0 )
      {
        v17 = v48;
        a3 = v47;
        goto LABEL_68;
      }
      v24 = v50;
      v26 = v51;
      v34 = 3LL * v33;
      goto LABEL_59;
    }
    if ( i == 1 && a4 )
    {
      v23 = 72;
      goto LABEL_31;
    }
LABEL_69:
    ;
  }
  FltReleasePushLockEx(v52, 0);
  v7 = *(_QWORD *)v53;
  if ( a4 )
    v39 = CldStreamAckData(v53[0], v38, a3, a5, a6);
  else
    v39 = CldStreamTransferData(v53[0], v55, a3, a5, a6, VirtualAddress);
  v11 = v39;
  HsmDbgBreakOnStatus(v39);
  if ( (v11 & 0x80000000) != 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v15 = 18;
      v46 = v11;
      v45 = v55;
      v44 = VirtualAddress;
      v43 = a6;
      v42 = a5;
LABEL_78:
      LOBYTE(v13) = a4;
      WPP_SF_cqdiiqid(v14->AttachedDevice, v15, v12, v13, v7, a3, v42, v43, v44, v45, v46);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x14006c178  mov     rax, rsp
0x14006c17b  mov     [rax+18h], rbx
0x14006c17f  mov     [rax+20h], rsi
0x14006c183  mov     [rax+10h], edx
0x14006c186  mov     [rax+8], rcx
0x14006c18a  push    rdi
0x14006c18b  push    r12
0x14006c18d  push    r13
0x14006c18f  push    r14
0x14006c191  push    r15
0x14006c193  sub     rsp, 0A0h
0x14006c19a  mov     r15, [rcx+8]
0x14006c19e  mov     r12d, r8d
0x14006c1a1  mov     r13b, r9b
0x14006c1a4  mov     qword ptr [rsp+0C8h+var_30], r15
0x14006c1ac  mov     r8, rcx
0x14006c1af  mov     rax, [r15]
0x14006c1b2  mov     r10, [rax]
0x14006c1b5  mov     eax, [r10+1Ch]
0x14006c1b9  test    al, 2
0x14006c1bb  jz      short loc_14006C23A
0x14006c1bd  mov     ebx, 0C000CF0Bh
0x14006c1c2  mov     ecx, ebx
0x14006c1c4  mov     edi, ebx
0x14006c1c6  call    HsmDbgBreakOnStatus
0x14006c1cb  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c1d2  lea     r14, WPP_GLOBAL_Control
0x14006c1d9  cmp     rcx, r14
0x14006c1dc  jz      loc_14006C6C9
0x14006c1e2  test    dword ptr [rcx+2Ch], 100h
0x14006c1e9  jz      loc_14006C6C9
0x14006c1ef  cmp     byte ptr [rcx+29h], 4
0x14006c1f3  jb      loc_14006C6C9
0x14006c1f9  mov     eax, [rsp+0C8h+arg_8]
0x14006c200  mov     edx, 0Dh
0x14006c205  mov     [rsp+0C8h+var_78], ebx
0x14006c209  mov     [rsp+0C8h+var_80], rax
0x14006c20e  mov     rax, [rsp+0C8h+arg_30]
0x14006c216  mov     [rsp+0C8h+var_88], rax
0x14006c21b  mov     rax, [rsp+0C8h+arg_28]
0x14006c223  mov     [rsp+0C8h+var_90], rax
0x14006c228  mov     rax, [rsp+0C8h+arg_20]
0x14006c230  mov     [rsp+0C8h+var_98], rax
0x14006c235  jmp     loc_14006C6B3
0x14006c23a  mov     rsi, [rsp+0C8h+arg_20]
0x14006c242  test    rsi, 0FFFh
0x14006c249  jz      short loc_14006C2C0
0x14006c24b  mov     ebx, 0C000CF0Bh
0x14006c250  mov     ecx, ebx
0x14006c252  mov     edi, ebx
0x14006c254  call    HsmDbgBreakOnStatus
0x14006c259  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c260  lea     r14, WPP_GLOBAL_Control
0x14006c267  cmp     rcx, r14
0x14006c26a  jz      loc_14006C6C9
0x14006c270  test    dword ptr [rcx+2Ch], 100h
0x14006c277  jz      loc_14006C6C9
0x14006c27d  cmp     byte ptr [rcx+29h], 4
0x14006c281  jb      loc_14006C6C9
0x14006c287  mov     eax, [rsp+0C8h+arg_8]
0x14006c28e  mov     edx, 0Eh
0x14006c293  mov     [rsp+0C8h+var_78], ebx
0x14006c297  mov     [rsp+0C8h+var_80], rax
0x14006c29c  mov     rax, [rsp+0C8h+arg_30]
0x14006c2a4  mov     [rsp+0C8h+var_88], rax
0x14006c2a9  mov     rax, [rsp+0C8h+arg_28]
0x14006c2b1  mov     [rsp+0C8h+var_90], rax
0x14006c2b6  mov     [rsp+0C8h+var_98], rsi
0x14006c2bb  jmp     loc_14006C6B3
0x14006c2c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c2c7  lea     r14, WPP_GLOBAL_Control
0x14006c2ce  cmp     rcx, r14
0x14006c2d1  jz      short loc_14006C323
0x14006c2d3  test    dword ptr [rcx+2Ch], 100h
0x14006c2da  jz      short loc_14006C323
0x14006c2dc  cmp     byte ptr [rcx+29h], 4
0x14006c2e0  jb      short loc_14006C323
0x14006c2e2  mov     rcx, [rcx+18h]
0x14006c2e6  mov     eax, edx
0x14006c2e8  mov     [rsp+0C8h+var_80], rax
0x14006c2ed  mov     rax, [rsp+0C8h+arg_30]
0x14006c2f5  mov     [rsp+0C8h+var_88], rax
0x14006c2fa  mov     rax, [rsp+0C8h+arg_28]
0x14006c302  mov     [rsp+0C8h+var_90], rax
0x14006c307  mov     [rsp+0C8h+var_98], rsi
0x14006c30c  mov     dword ptr [rsp+0C8h+VirtualAddress], r12d
0x14006c311  mov     qword ptr [rsp+0C8h+Length], r15
0x14006c316  call    WPP_SF_cqdiiqi
0x14006c31b  mov     r8, [rsp+0C8h+arg_0]
0x14006c323  mov     rax, rsi
0x14006c326  mov     ecx, 1000h
0x14006c32b  cqo
0x14006c32d  idiv    rcx
0x14006c330  mov     rdi, rax
0x14006c333  mov     rax, [rsp+0C8h+arg_28]
0x14006c33b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14006c33f  jnz     short loc_14006C34D
0x14006c341  mov     rbx, 7FFFFFFFFFFFFh
0x14006c34b  jmp     short loc_14006C361
0x14006c34d  add     rax, 0FFFh
0x14006c353  and     rax, 0FFFFFFFFFFFFF000h
0x14006c359  cqo
0x14006c35b  idiv    rcx
0x14006c35e  mov     rbx, rax
0x14006c361  lea     rax, [r8+18h]
0x14006c365  mov     [rsp+0C8h+var_60], rbx
0x14006c36a  mov     rcx, rax
0x14006c36d  mov     [rsp+0C8h+var_38], rax
0x14006c375  xor     edx, edx
0x14006c377  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14006c37e  nop     dword ptr [rax+rax+00h]
0x14006c383  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c38a  cmp     rcx, r14
0x14006c38d  jz      short loc_14006C3B9
0x14006c38f  test    dword ptr [rcx+2Ch], 100h
0x14006c396  jz      short loc_14006C3B9
0x14006c398  cmp     byte ptr [rcx+29h], 4
0x14006c39c  jb      short loc_14006C3B9
0x14006c39e  mov     rcx, [rcx+18h]
0x14006c3a2  mov     r9b, r13b
0x14006c3a5  mov     [rsp+0C8h+var_98], rbx
0x14006c3aa  mov     [rsp+0C8h+VirtualAddress], rdi
0x14006c3af  mov     qword ptr [rsp+0C8h+Length], r15
0x14006c3b4  call    WPP_SF_cqii
0x14006c3b9  mov     rsi, [rsp+0C8h+arg_0]
0x14006c3c1  mov     r8, rbx; SectorCount
0x14006c3c4  mov     rdx, rdi; Vbn
0x14006c3c7  lea     rcx, [rsi+20h]; Mcb
0x14006c3cb  call    cs:__imp_FsRtlRemoveBaseMcbEntry
0x14006c3d2  nop     dword ptr [rax+rax+00h]
0x14006c3d7  xor     r15d, r15d
0x14006c3da  test    r12d, r12d
0x14006c3dd  jns     short loc_14006C3F0
0x14006c3df  mov     eax, r15d
0x14006c3e2  neg     eax
0x14006c3e4  sbb     rcx, rcx
0x14006c3e7  and     ecx, 10h
0x14006c3ea  add     rcx, 38h ; '8'
0x14006c3ee  jmp     short loc_14006C41B
0x14006c3f0  test    r15d, r15d
0x14006c3f3  jnz     short loc_14006C404
0x14006c3f5  test    r13b, r13b
0x14006c3f8  jnz     loc_14006C5E0
0x14006c3fe  lea     ecx, [r15+38h]
0x14006c402  jmp     short loc_14006C41B
0x14006c404  cmp     r15d, 1
0x14006c408  jnz     loc_14006C5E0
0x14006c40e  test    r13b, r13b
0x14006c411  jz      loc_14006C5E0
0x14006c417  lea     ecx, [r15+47h]
0x14006c41b  lea     r8, [rsi+rcx]
0x14006c41f  mov     [rsp+0C8h+var_50], r8
0x14006c424  test    r8, r8
0x14006c427  jz      loc_14006C5E0
0x14006c42d  mov     esi, [r8+4]
0x14006c431  lea     r11, [r8+8]
0x14006c435  xor     r9d, r9d
0x14006c438  mov     [rsp+0C8h+var_48], r11
0x14006c440  mov     [rsp+0C8h+var_58], r8
0x14006c445  lea     r10d, [rsi-1]
0x14006c449  test    r10d, r10d
0x14006c44c  js      short loc_14006C487
0x14006c44e  mov     rbx, [r11]
0x14006c451  lea     r8d, [r10+r9]
0x14006c455  sar     r8d, 1
0x14006c458  movsxd  rax, r8d
0x14006c45b  lea     rcx, [rax+rax*2]
0x14006c45f  cmp     [rbx+rcx*8], rdi
0x14006c463  lea     eax, [r8-1]
0x14006c467  cmovge  r10d, eax
0x14006c46b  lea     eax, [r8+1]
0x14006c46f  cmovge  eax, r9d
0x14006c473  mov     r9d, eax
0x14006c476  cmp     eax, r10d
0x14006c479  jle     short loc_14006C451
0x14006c47b  mov     r8, [rsp+0C8h+var_50]
0x14006c480  mov     rbx, [rsp+0C8h+var_60]
0x14006c485  jmp     short loc_14006C48F
0x14006c487  mov     [rsp+0C8h+var_48], r11
0x14006c48f  mov     r10, r8
0x14006c492  cmp     r9d, esi
0x14006c495  jz      short loc_14006C4A7
0x14006c497  movsxd  rax, r9d
0x14006c49a  lea     rcx, [rax+rax*2]
0x14006c49e  mov     rax, [r11]
0x14006c4a1  cmp     [rax+rcx*8], rdi
0x14006c4a5  jle     short loc_14006C4AA
0x14006c4a7  dec     r9d
0x14006c4aa  xor     esi, esi
0x14006c4ac  test    r9d, r9d
0x14006c4af  cmovns  esi, r9d
0x14006c4b3  cmp     esi, [r8+4]
0x14006c4b7  jge     loc_14006C5D8
0x14006c4bd  test    rbx, rbx
0x14006c4c0  jle     loc_14006C5D8
0x14006c4c6  movsxd  rax, esi
0x14006c4c9  lea     r9, [rax+rax*2]
0x14006c4cd  mov     rax, [r11]
0x14006c4d0  mov     [rsp+0C8h+var_40], r9
0x14006c4d8  mov     rcx, [rax+r9*8]
0x14006c4dc  mov     rdx, [rax+r9*8+8]
0x14006c4e1  add     rdx, rcx
0x14006c4e4  cmp     rdi, rdx
0x14006c4e7  jge     loc_14006C5B7
0x14006c4ed  add     rbx, rdi
0x14006c4f0  cmp     rcx, rbx
0x14006c4f3  jge     loc_14006C5B2
0x14006c4f9  cmp     rdi, rcx
0x14006c4fc  jg      short loc_14006C511
0x14006c4fe  cmp     rdx, rbx
0x14006c501  cmovl   rbx, rdx
0x14006c505  cmp     rbx, rcx
0x14006c508  jle     short loc_14006C54D
0x14006c50a  cmp     rbx, rdx
0x14006c50d  jl      short loc_14006C514
0x14006c50f  jmp     short loc_14006C54D
0x14006c511  mov     rbx, rdi
0x14006c514  mov     r8, rbx
0x14006c517  mov     edx, esi
0x14006c519  mov     rcx, r10
0x14006c51c  call    CldiSyncSplitPendingRange
0x14006c521  mov     ecx, eax
0x14006c523  mov     [rsp+0C8h+var_68], eax
0x14006c527  call    HsmDbgBreakOnStatus
0x14006c52c  mov     eax, [rsp+0C8h+var_68]
0x14006c530  test    eax, eax
0x14006c532  js      loc_14006C5D0
0x14006c538  mov     r8, [rsp+0C8h+var_50]
0x14006c53d  mov     r11, [rsp+0C8h+var_48]
0x14006c545  mov     r9, [rsp+0C8h+var_40]
0x14006c54d  cmp     rbx, rdi
0x14006c550  jz      short loc_14006C5B2
0x14006c552  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c559  cmp     rcx, r14
0x14006c55c  jz      short loc_14006C59B
0x14006c55e  test    dword ptr [rcx+2Ch], 100h
0x14006c565  jz      short loc_14006C59B
0x14006c567  cmp     byte ptr [rcx+29h], 4
0x14006c56b  jb      short loc_14006C59B
0x14006c56d  mov     rdx, [r11]
0x14006c570  mov     rcx, [rcx+18h]
0x14006c574  mov     rax, [rdx+r9*8+8]
0x14006c579  mov     [rsp+0C8h+var_90], rax
0x14006c57e  mov     rax, [rdx+r9*8]
0x14006c582  mov     r9, r8
0x14006c585  mov     [rsp+0C8h+var_98], rax
0x14006c58a  mov     eax, [r8+4]
0x14006c58e  mov     dword ptr [rsp+0C8h+VirtualAddress], eax
0x14006c592  mov     [rsp+0C8h+Length], esi
0x14006c596  call    WPP_SF_qddii
0x14006c59b  mov     rcx, [rsp+0C8h+var_58]
0x14006c5a0  sub     rdi, rbx
0x14006c5a3  add     [rsp+0C8h+var_60], rdi
0x14006c5a8  mov     edx, esi
0x14006c5aa  mov     rdi, rbx
0x14006c5ad  call    CldiSyncRemovePendingRange
0x14006c5b2  mov     rbx, [rsp+0C8h+var_60]
0x14006c5b7  mov     r8, [rsp+0C8h+var_50]
0x14006c5bc  inc     esi
0x14006c5be  mov     r11, [rsp+0C8h+var_48]
0x14006c5c6  mov     r10, [rsp+0C8h+var_58]
0x14006c5cb  jmp     loc_14006C4B3
0x14006c5d0  mov     rbx, [rsp+0C8h+var_60]
0x14006c5d5  mov     r12d, eax
0x14006c5d8  mov     rsi, [rsp+0C8h+arg_0]
0x14006c5e0  inc     r15d
0x14006c5e3  cmp     r15d, 2
0x14006c5e7  jl      loc_14006C3DA
0x14006c5ed  mov     rcx, [rsp+0C8h+var_38]
0x14006c5f5  xor     edx, edx
0x14006c5f7  call    cs:__imp_FltReleasePushLockEx
0x14006c5fe  nop     dword ptr [rax+rax+00h]
0x14006c603  mov     r15, qword ptr [rsp+0C8h+var_30]
0x14006c60b  mov     r8d, r12d; int
0x14006c60e  mov     rbx, [rsp+0C8h+arg_20]
0x14006c616  mov     rcx, r15; int
0x14006c619  mov     esi, [rsp+0C8h+arg_8]
0x14006c620  mov     r9, rbx; int
0x14006c623  test    r13b, r13b
0x14006c626  jz      short loc_14006C63C
0x14006c628  mov     rax, [rsp+0C8h+arg_28]
0x14006c630  mov     qword ptr [rsp+0C8h+Length], rax
0x14006c635  call    CldStreamAckData
0x14006c63a  jmp     short loc_14006C65E
0x14006c63c  mov     rax, [rsp+0C8h+arg_30]
0x14006c644  mov     rdx, rsi; int
0x14006c647  mov     [rsp+0C8h+VirtualAddress], rax; VirtualAddress
0x14006c64c  mov     rax, [rsp+0C8h+arg_28]
0x14006c654  mov     qword ptr [rsp+0C8h+Length], rax; Length
0x14006c659  call    CldStreamTransferData
0x14006c65e  mov     ecx, eax
0x14006c660  mov     edi, eax
0x14006c662  call    HsmDbgBreakOnStatus
0x14006c667  test    edi, edi
0x14006c669  jns     short loc_14006C6C9
0x14006c66b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c672  cmp     rcx, r14
0x14006c675  jz      short loc_14006C6C9
0x14006c677  test    dword ptr [rcx+2Ch], 100h
0x14006c67e  jz      short loc_14006C6C9
  ... truncated ...
```
