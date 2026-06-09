# CldiSyncTransferOrAckDataByObject

- ea: `0x14006c058`
- end: `0x14006c5c9`
- name: `CldiSyncTransferOrAckDataByObject`
- size: `1393`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1400561cc`
- `0x14006bf64`

## callees

- `0x140003c50`
- `0x14000ef7c`
- `0x14000f020`
- `0x14000f0d4`
- `0x14000fd84`
- `0x140034268`
- `0x140036120`
- `0x14003f640`
- `0x14006c058`
- `0x14006c5d0`

## import_xrefs

- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x14006c2ab`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x14006c2ab`
- `FLTMGR!FltReleasePushLockEx` at `0x14006c4d7`
- `FLTMGR!FltReleasePushLockEx` at `0x14006c4d7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006c257`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006c257`

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
  volatile signed __int32 *v7; // r15
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
  volatile signed __int32 *v53; // [rsp+98h] [rbp-30h]
  unsigned int v55; // [rsp+D8h] [rbp+10h]

  v55 = a2;
  v7 = *(volatile signed __int32 **)(a1 + 8);
  v53 = v7;
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
            CldiSyncRemovePendingRange(v49, (unsigned int)v33);
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
  v7 = v53;
  if ( a4 )
    v39 = CldStreamAckData((_DWORD)v53, v38, a3, a5, a6);
  else
    v39 = CldStreamTransferData(v53, v55, a3, a5, a6, VirtualAddress);
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
0x14006c058  mov     rax, rsp
0x14006c05b  mov     [rax+18h], rbx
0x14006c05f  mov     [rax+20h], rsi
0x14006c063  mov     [rax+10h], edx
0x14006c066  mov     [rax+8], rcx
0x14006c06a  push    rdi
0x14006c06b  push    r12
0x14006c06d  push    r13
0x14006c06f  push    r14
0x14006c071  push    r15
0x14006c073  sub     rsp, 0A0h
0x14006c07a  mov     r15, [rcx+8]
0x14006c07e  mov     r12d, r8d
0x14006c081  mov     r13b, r9b
0x14006c084  mov     qword ptr [rsp+0C8h+var_30], r15
0x14006c08c  mov     r8, rcx
0x14006c08f  mov     rax, [r15]
0x14006c092  mov     r10, [rax]
0x14006c095  mov     eax, [r10+1Ch]
0x14006c099  test    al, 2
0x14006c09b  jz      short loc_14006C11A
0x14006c09d  mov     ebx, 0C000CF0Bh
0x14006c0a2  mov     ecx, ebx
0x14006c0a4  mov     edi, ebx
0x14006c0a6  call    HsmDbgBreakOnStatus
0x14006c0ab  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c0b2  lea     r14, WPP_GLOBAL_Control
0x14006c0b9  cmp     rcx, r14
0x14006c0bc  jz      loc_14006C5A9
0x14006c0c2  test    dword ptr [rcx+2Ch], 100h
0x14006c0c9  jz      loc_14006C5A9
0x14006c0cf  cmp     byte ptr [rcx+29h], 4
0x14006c0d3  jb      loc_14006C5A9
0x14006c0d9  mov     eax, [rsp+0C8h+arg_8]
0x14006c0e0  mov     edx, 0Dh
0x14006c0e5  mov     [rsp+0C8h+var_78], ebx
0x14006c0e9  mov     [rsp+0C8h+var_80], rax
0x14006c0ee  mov     rax, [rsp+0C8h+arg_30]
0x14006c0f6  mov     [rsp+0C8h+var_88], rax
0x14006c0fb  mov     rax, [rsp+0C8h+arg_28]
0x14006c103  mov     [rsp+0C8h+var_90], rax
0x14006c108  mov     rax, [rsp+0C8h+arg_20]
0x14006c110  mov     [rsp+0C8h+var_98], rax
0x14006c115  jmp     loc_14006C593
0x14006c11a  mov     rsi, [rsp+0C8h+arg_20]
0x14006c122  test    rsi, 0FFFh
0x14006c129  jz      short loc_14006C1A0
0x14006c12b  mov     ebx, 0C000CF0Bh
0x14006c130  mov     ecx, ebx
0x14006c132  mov     edi, ebx
0x14006c134  call    HsmDbgBreakOnStatus
0x14006c139  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c140  lea     r14, WPP_GLOBAL_Control
0x14006c147  cmp     rcx, r14
0x14006c14a  jz      loc_14006C5A9
0x14006c150  test    dword ptr [rcx+2Ch], 100h
0x14006c157  jz      loc_14006C5A9
0x14006c15d  cmp     byte ptr [rcx+29h], 4
0x14006c161  jb      loc_14006C5A9
0x14006c167  mov     eax, [rsp+0C8h+arg_8]
0x14006c16e  mov     edx, 0Eh
0x14006c173  mov     [rsp+0C8h+var_78], ebx
0x14006c177  mov     [rsp+0C8h+var_80], rax
0x14006c17c  mov     rax, [rsp+0C8h+arg_30]
0x14006c184  mov     [rsp+0C8h+var_88], rax
0x14006c189  mov     rax, [rsp+0C8h+arg_28]
0x14006c191  mov     [rsp+0C8h+var_90], rax
0x14006c196  mov     [rsp+0C8h+var_98], rsi
0x14006c19b  jmp     loc_14006C593
0x14006c1a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c1a7  lea     r14, WPP_GLOBAL_Control
0x14006c1ae  cmp     rcx, r14
0x14006c1b1  jz      short loc_14006C203
0x14006c1b3  test    dword ptr [rcx+2Ch], 100h
0x14006c1ba  jz      short loc_14006C203
0x14006c1bc  cmp     byte ptr [rcx+29h], 4
0x14006c1c0  jb      short loc_14006C203
0x14006c1c2  mov     rcx, [rcx+18h]
0x14006c1c6  mov     eax, edx
0x14006c1c8  mov     [rsp+0C8h+var_80], rax
0x14006c1cd  mov     rax, [rsp+0C8h+arg_30]
0x14006c1d5  mov     [rsp+0C8h+var_88], rax
0x14006c1da  mov     rax, [rsp+0C8h+arg_28]
0x14006c1e2  mov     [rsp+0C8h+var_90], rax
0x14006c1e7  mov     [rsp+0C8h+var_98], rsi
0x14006c1ec  mov     dword ptr [rsp+0C8h+VirtualAddress], r12d
0x14006c1f1  mov     qword ptr [rsp+0C8h+Length], r15
0x14006c1f6  call    WPP_SF_cqdiiqi
0x14006c1fb  mov     r8, [rsp+0C8h+arg_0]
0x14006c203  mov     rax, rsi
0x14006c206  mov     ecx, 1000h
0x14006c20b  cqo
0x14006c20d  idiv    rcx
0x14006c210  mov     rdi, rax
0x14006c213  mov     rax, [rsp+0C8h+arg_28]
0x14006c21b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14006c21f  jnz     short loc_14006C22D
0x14006c221  mov     rbx, 7FFFFFFFFFFFFh
0x14006c22b  jmp     short loc_14006C241
0x14006c22d  add     rax, 0FFFh
0x14006c233  and     rax, 0FFFFFFFFFFFFF000h
0x14006c239  cqo
0x14006c23b  idiv    rcx
0x14006c23e  mov     rbx, rax
0x14006c241  lea     rax, [r8+18h]
0x14006c245  mov     [rsp+0C8h+var_60], rbx
0x14006c24a  mov     rcx, rax
0x14006c24d  mov     [rsp+0C8h+var_38], rax
0x14006c255  xor     edx, edx
0x14006c257  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14006c25e  nop     dword ptr [rax+rax+00h]
0x14006c263  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c26a  cmp     rcx, r14
0x14006c26d  jz      short loc_14006C299
0x14006c26f  test    dword ptr [rcx+2Ch], 100h
0x14006c276  jz      short loc_14006C299
0x14006c278  cmp     byte ptr [rcx+29h], 4
0x14006c27c  jb      short loc_14006C299
0x14006c27e  mov     rcx, [rcx+18h]
0x14006c282  mov     r9b, r13b
0x14006c285  mov     [rsp+0C8h+var_98], rbx
0x14006c28a  mov     [rsp+0C8h+VirtualAddress], rdi
0x14006c28f  mov     qword ptr [rsp+0C8h+Length], r15
0x14006c294  call    WPP_SF_cqii
0x14006c299  mov     rsi, [rsp+0C8h+arg_0]
0x14006c2a1  mov     r8, rbx; SectorCount
0x14006c2a4  mov     rdx, rdi; Vbn
0x14006c2a7  lea     rcx, [rsi+20h]; Mcb
0x14006c2ab  call    cs:__imp_FsRtlRemoveBaseMcbEntry
0x14006c2b2  nop     dword ptr [rax+rax+00h]
0x14006c2b7  xor     r15d, r15d
0x14006c2ba  test    r12d, r12d
0x14006c2bd  jns     short loc_14006C2D0
0x14006c2bf  mov     eax, r15d
0x14006c2c2  neg     eax
0x14006c2c4  sbb     rcx, rcx
0x14006c2c7  and     ecx, 10h
0x14006c2ca  add     rcx, 38h ; '8'
0x14006c2ce  jmp     short loc_14006C2FB
0x14006c2d0  test    r15d, r15d
0x14006c2d3  jnz     short loc_14006C2E4
0x14006c2d5  test    r13b, r13b
0x14006c2d8  jnz     loc_14006C4C0
0x14006c2de  lea     ecx, [r15+38h]
0x14006c2e2  jmp     short loc_14006C2FB
0x14006c2e4  cmp     r15d, 1
0x14006c2e8  jnz     loc_14006C4C0
0x14006c2ee  test    r13b, r13b
0x14006c2f1  jz      loc_14006C4C0
0x14006c2f7  lea     ecx, [r15+47h]
0x14006c2fb  lea     r8, [rsi+rcx]
0x14006c2ff  mov     [rsp+0C8h+var_50], r8
0x14006c304  test    r8, r8
0x14006c307  jz      loc_14006C4C0
0x14006c30d  mov     esi, [r8+4]
0x14006c311  lea     r11, [r8+8]
0x14006c315  xor     r9d, r9d
0x14006c318  mov     [rsp+0C8h+var_48], r11
0x14006c320  mov     [rsp+0C8h+var_58], r8
0x14006c325  lea     r10d, [rsi-1]
0x14006c329  test    r10d, r10d
0x14006c32c  js      short loc_14006C367
0x14006c32e  mov     rbx, [r11]
0x14006c331  lea     r8d, [r10+r9]
0x14006c335  sar     r8d, 1
0x14006c338  movsxd  rax, r8d
0x14006c33b  lea     rcx, [rax+rax*2]
0x14006c33f  cmp     [rbx+rcx*8], rdi
0x14006c343  lea     eax, [r8-1]
0x14006c347  cmovge  r10d, eax
0x14006c34b  lea     eax, [r8+1]
0x14006c34f  cmovge  eax, r9d
0x14006c353  mov     r9d, eax
0x14006c356  cmp     eax, r10d
0x14006c359  jle     short loc_14006C331
0x14006c35b  mov     r8, [rsp+0C8h+var_50]
0x14006c360  mov     rbx, [rsp+0C8h+var_60]
0x14006c365  jmp     short loc_14006C36F
0x14006c367  mov     [rsp+0C8h+var_48], r11
0x14006c36f  mov     r10, r8
0x14006c372  cmp     r9d, esi
0x14006c375  jz      short loc_14006C387
0x14006c377  movsxd  rax, r9d
0x14006c37a  lea     rcx, [rax+rax*2]
0x14006c37e  mov     rax, [r11]
0x14006c381  cmp     [rax+rcx*8], rdi
0x14006c385  jle     short loc_14006C38A
0x14006c387  dec     r9d
0x14006c38a  xor     esi, esi
0x14006c38c  test    r9d, r9d
0x14006c38f  cmovns  esi, r9d
0x14006c393  cmp     esi, [r8+4]
0x14006c397  jge     loc_14006C4B8
0x14006c39d  test    rbx, rbx
0x14006c3a0  jle     loc_14006C4B8
0x14006c3a6  movsxd  rax, esi
0x14006c3a9  lea     r9, [rax+rax*2]
0x14006c3ad  mov     rax, [r11]
0x14006c3b0  mov     [rsp+0C8h+var_40], r9
0x14006c3b8  mov     rcx, [rax+r9*8]
0x14006c3bc  mov     rdx, [rax+r9*8+8]
0x14006c3c1  add     rdx, rcx
0x14006c3c4  cmp     rdi, rdx
0x14006c3c7  jge     loc_14006C497
0x14006c3cd  add     rbx, rdi
0x14006c3d0  cmp     rcx, rbx
0x14006c3d3  jge     loc_14006C492
0x14006c3d9  cmp     rdi, rcx
0x14006c3dc  jg      short loc_14006C3F1
0x14006c3de  cmp     rdx, rbx
0x14006c3e1  cmovl   rbx, rdx
0x14006c3e5  cmp     rbx, rcx
0x14006c3e8  jle     short loc_14006C42D
0x14006c3ea  cmp     rbx, rdx
0x14006c3ed  jl      short loc_14006C3F4
0x14006c3ef  jmp     short loc_14006C42D
0x14006c3f1  mov     rbx, rdi
0x14006c3f4  mov     r8, rbx
0x14006c3f7  mov     edx, esi
0x14006c3f9  mov     rcx, r10
0x14006c3fc  call    CldiSyncSplitPendingRange
0x14006c401  mov     ecx, eax
0x14006c403  mov     [rsp+0C8h+var_68], eax
0x14006c407  call    HsmDbgBreakOnStatus
0x14006c40c  mov     eax, [rsp+0C8h+var_68]
0x14006c410  test    eax, eax
0x14006c412  js      loc_14006C4B0
0x14006c418  mov     r8, [rsp+0C8h+var_50]
0x14006c41d  mov     r11, [rsp+0C8h+var_48]
0x14006c425  mov     r9, [rsp+0C8h+var_40]
0x14006c42d  cmp     rbx, rdi
0x14006c430  jz      short loc_14006C492
0x14006c432  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c439  cmp     rcx, r14
0x14006c43c  jz      short loc_14006C47B
0x14006c43e  test    dword ptr [rcx+2Ch], 100h
0x14006c445  jz      short loc_14006C47B
0x14006c447  cmp     byte ptr [rcx+29h], 4
0x14006c44b  jb      short loc_14006C47B
0x14006c44d  mov     rdx, [r11]
0x14006c450  mov     rcx, [rcx+18h]
0x14006c454  mov     rax, [rdx+r9*8+8]
0x14006c459  mov     [rsp+0C8h+var_90], rax
0x14006c45e  mov     rax, [rdx+r9*8]
0x14006c462  mov     r9, r8
0x14006c465  mov     [rsp+0C8h+var_98], rax
0x14006c46a  mov     eax, [r8+4]
0x14006c46e  mov     dword ptr [rsp+0C8h+VirtualAddress], eax
0x14006c472  mov     [rsp+0C8h+Length], esi
0x14006c476  call    WPP_SF_qddii
0x14006c47b  mov     rcx, [rsp+0C8h+var_58]
0x14006c480  sub     rdi, rbx
0x14006c483  add     [rsp+0C8h+var_60], rdi
0x14006c488  mov     edx, esi
0x14006c48a  mov     rdi, rbx
0x14006c48d  call    CldiSyncRemovePendingRange
0x14006c492  mov     rbx, [rsp+0C8h+var_60]
0x14006c497  mov     r8, [rsp+0C8h+var_50]
0x14006c49c  inc     esi
0x14006c49e  mov     r11, [rsp+0C8h+var_48]
0x14006c4a6  mov     r10, [rsp+0C8h+var_58]
0x14006c4ab  jmp     loc_14006C393
0x14006c4b0  mov     rbx, [rsp+0C8h+var_60]
0x14006c4b5  mov     r12d, eax
0x14006c4b8  mov     rsi, [rsp+0C8h+arg_0]
0x14006c4c0  inc     r15d
0x14006c4c3  cmp     r15d, 2
0x14006c4c7  jl      loc_14006C2BA
0x14006c4cd  mov     rcx, [rsp+0C8h+var_38]
0x14006c4d5  xor     edx, edx
0x14006c4d7  call    cs:__imp_FltReleasePushLockEx
0x14006c4de  nop     dword ptr [rax+rax+00h]
0x14006c4e3  mov     r15, qword ptr [rsp+0C8h+var_30]
0x14006c4eb  mov     r8d, r12d; int
0x14006c4ee  mov     rbx, [rsp+0C8h+arg_20]
0x14006c4f6  mov     rcx, r15; int
0x14006c4f9  mov     esi, [rsp+0C8h+arg_8]
0x14006c500  mov     r9, rbx; int
0x14006c503  test    r13b, r13b
0x14006c506  jz      short loc_14006C51C
0x14006c508  mov     rax, [rsp+0C8h+arg_28]
0x14006c510  mov     qword ptr [rsp+0C8h+Length], rax
0x14006c515  call    CldStreamAckData
0x14006c51a  jmp     short loc_14006C53E
0x14006c51c  mov     rax, [rsp+0C8h+arg_30]
0x14006c524  mov     rdx, rsi; int
0x14006c527  mov     [rsp+0C8h+VirtualAddress], rax; VirtualAddress
0x14006c52c  mov     rax, [rsp+0C8h+arg_28]
0x14006c534  mov     qword ptr [rsp+0C8h+Length], rax; Length
0x14006c539  call    CldStreamTransferData
0x14006c53e  mov     ecx, eax
0x14006c540  mov     edi, eax
0x14006c542  call    HsmDbgBreakOnStatus
0x14006c547  test    edi, edi
0x14006c549  jns     short loc_14006C5A9
0x14006c54b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c552  cmp     rcx, r14
0x14006c555  jz      short loc_14006C5A9
0x14006c557  test    dword ptr [rcx+2Ch], 100h
0x14006c55e  jz      short loc_14006C5A9
  ... truncated ...
```
