# ChannelWrite

- ea: `0x140010810`
- end: `0x140011043`
- name: `ChannelWrite`
- size: `2099`
- prototype: `__int64 __fastcall(__int64, struct _MDL *, char, PVOID *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000aca0`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x140004e58`
- `0x1400051b4`
- `0x140010260`
- `0x140010810`
- `0x1400134f4`
- `0x140016448`
- `0x14001a12c`
- `0x14001bfa8`
- `0x14001e74c`
- `0x14001e8f4`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001089e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001089e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010e9b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010fb4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010e9b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010fb4`
- `ntoskrnl!ExAllocatePool2` at `0x140010996`
- `ntoskrnl!ExAllocatePool2` at `0x1400109c4`
- `ntoskrnl!ExAllocatePool2` at `0x1400109e7`
- `ntoskrnl!ExAllocatePool2` at `0x140010996`
- `ntoskrnl!ExAllocatePool2` at `0x1400109c4`
- `ntoskrnl!ExAllocatePool2` at `0x1400109e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010bec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010cbb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010cd1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010ce7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010f4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010f93`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010bec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010cbb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010cd1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010ce7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010f4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010f93`
- `ntoskrnl!IoFreeMdl` at `0x140010c95`
- `ntoskrnl!IoFreeMdl` at `0x140010caa`
- `ntoskrnl!IoFreeMdl` at `0x140010f32`
- `ntoskrnl!IoFreeMdl` at `0x140010c95`
- `ntoskrnl!IoFreeMdl` at `0x140010caa`
- `ntoskrnl!IoFreeMdl` at `0x140010f32`
- `ntoskrnl!IoAllocateMdl` at `0x140010a13`
- `ntoskrnl!IoAllocateMdl` at `0x140010a38`
- `ntoskrnl!IoAllocateMdl` at `0x140010a13`
- `ntoskrnl!IoAllocateMdl` at `0x140010a38`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140010a61`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140010a74`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140010a61`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140010a74`

## string_xrefs

- `0x140010b7b`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x140010d87`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x140010dab`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x140010dc6`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x140010df1`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x140010fce`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
__int64 __fastcall ChannelWrite(__int64 a1, struct _MDL *a2, char a3, PVOID *a4)
{
  __int64 v4; // r15
  int v7; // edx
  int v8; // edi
  PVOID **v9; // r13
  PVOID v10; // r14
  __int64 v11; // rax
  int v12; // r13d
  int v13; // edx
  PVOID **Pool2; // rbx
  ULONG v15; // edi
  int v16; // edx
  _BYTE *v17; // r15
  int v18; // edx
  _BYTE *v19; // r13
  PMDL Mdl; // rax
  struct _MDL *v21; // rcx
  __int64 v22; // rax
  char v23; // cl
  unsigned int v24; // edi
  char v25; // al
  char v26; // dl
  unsigned __int8 v27; // al
  __int64 v28; // rcx
  __int64 v29; // rax
  _QWORD **v30; // rdx
  PVOID *v31; // rax
  _QWORD *i; // rcx
  PVOID *v33; // rax
  PVOID *v34; // rax
  int v35; // r9d
  struct _MDL *v36; // rcx
  struct _MDL *v37; // rcx
  void *v38; // rcx
  __int64 v39; // r14
  int v40; // edi
  int v41; // r12d
  PVOID **v42; // rbx
  _QWORD *v43; // rax
  int v44; // edx
  PVOID ***v45; // rcx
  PVOID v46; // rsi
  __int64 v47; // rax
  struct _MDL *v48; // rcx
  struct _MDL *Next; // rbx
  _QWORD *v50; // rbx
  __int64 v51; // rax
  void *DeviceExtension; // rbx
  __int64 v53; // rax
  int v54; // edx
  PVOID v56; // [rsp+40h] [rbp-29h] BYREF
  PVOID *v57; // [rsp+48h] [rbp-21h]
  PVOID P[2]; // [rsp+50h] [rbp-19h] BYREF
  int v59; // [rsp+60h] [rbp-9h]
  int v60; // [rsp+64h] [rbp-5h]
  __int64 v61; // [rsp+68h] [rbp-1h]
  unsigned int v62; // [rsp+70h] [rbp+7h]
  ULONG v63; // [rsp+74h] [rbp+Bh]
  __int64 v64; // [rsp+78h] [rbp+Fh]
  PVOID **v65; // [rsp+80h] [rbp+17h]
  _QWORD **v66; // [rsp+88h] [rbp+1Fh]
  char v67; // [rsp+D0h] [rbp+67h]

  v4 = *(_QWORD *)(a1 + 56);
  P[1] = P;
  v61 = v4;
  P[0] = P;
  v57 = &v56;
  v56 = &v56;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      3,
      33,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      a3);
  *(_BYTE *)(v4 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 56));
  v64 = ChannelReferenceConnLocked(a1, 1312901187);
  if ( !v64 )
  {
    v8 = -1073741300;
    goto LABEL_69;
  }
  if ( *(_DWORD *)(v4 + 48) == 6 || *(_DWORD *)(a1 + 48) == 9 )
  {
    v8 = -1073741504;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qq(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        1,
        34,
        (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
        v4,
        a1);
    goto LABEL_69;
  }
  v67 = *(_BYTE *)(v4 + 465);
  v8 = ShortenMdlChain(a2);
  if ( v8 < 0 )
    goto LABEL_69;
  v9 = 0;
  v60 = 0;
  v59 = 0;
  v65 = 0;
  while ( 1 )
  {
    v10 = P[0];
    if ( P[0] == P )
      break;
    if ( *((PVOID **)P[0] + 1) != P )
      goto LABEL_80;
    v11 = *(_QWORD *)P[0];
    if ( *(PVOID *)(*(_QWORD *)P[0] + 8LL) != P[0] )
      goto LABEL_80;
    P[0] = *(PVOID *)P[0];
    *(_QWORD *)(v11 + 8) = P;
    v66 = (_QWORD **)*((_QWORD *)v10 + 2);
    v62 = *((_DWORD *)v10 + 6);
    v12 = 2 - (v62 < 0x80);
    Pool2 = (PVOID **)ExAllocatePool2(64, 152, 1380345426);
    if ( !Pool2 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v13,
          1,
          35,
          (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
      v8 = -1073741670;
      goto LABEL_50;
    }
    v15 = v12 + (v67 != 0) + 2;
    v63 = v15;
    v17 = (_BYTE *)ExAllocatePool2(64, v15, 1380345426);
    if ( !v17 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v16,
          1,
          36,
          (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
      v19 = 0;
      goto LABEL_41;
    }
    v19 = (_BYTE *)ExAllocatePool2(64, 1, 1380345426);
    if ( !v19 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v35 = 37;
LABEL_35:
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v18,
          1,
          v35,
          (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
      }
LABEL_41:
      v36 = (struct _MDL *)Pool2[16];
      v8 = -1073741670;
      if ( v36 )
        IoFreeMdl(v36);
      v37 = (struct _MDL *)Pool2[15];
      if ( v37 )
        IoFreeMdl(v37);
      ExFreePoolWithTag(Pool2, 0);
      if ( v17 )
        ExFreePoolWithTag(v17, 0);
      if ( v19 )
        ExFreePoolWithTag(v19, 0);
      v4 = v61;
LABEL_50:
      if ( v10 )
      {
        v38 = v10;
        goto LABEL_75;
      }
LABEL_69:
      while ( 1 )
      {
        v46 = P[0];
        if ( P[0] == P )
          break;
        if ( *((PVOID **)P[0] + 1) != P )
          goto LABEL_80;
        v47 = *(_QWORD *)P[0];
        if ( *(PVOID *)(*(_QWORD *)P[0] + 8LL) != P[0] )
          goto LABEL_80;
        P[0] = *(PVOID *)P[0];
        *(_QWORD *)(v47 + 8) = P;
        v48 = (struct _MDL *)*((_QWORD *)v46 + 2);
        if ( v48 )
        {
          do
          {
            Next = v48->Next;
            v48->Next = 0;
            IoFreeMdl(v48);
            v48 = Next;
          }
          while ( Next );
        }
        v38 = v46;
LABEL_75:
        ExFreePoolWithTag(v38, 0);
      }
      while ( 1 )
      {
        v50 = v56;
        if ( v56 == &v56 )
          break;
        if ( *((PVOID **)v56 + 1) != &v56 )
          goto LABEL_80;
        v51 = *(_QWORD *)v56;
        if ( *(PVOID *)(*(_QWORD *)v56 + 8LL) != v56 )
          goto LABEL_80;
        v56 = *(PVOID *)v56;
        *(_QWORD *)(v51 + 8) = &v56;
        RfCommFreeMdlFrame(v50[15]);
        ExFreePoolWithTag(v50, 0);
      }
      v39 = v64;
      goto LABEL_82;
    }
    Pool2[15] = (PVOID *)IoAllocateMdl(v17, v15, 0, 0, 0);
    Mdl = IoAllocateMdl(v19, 1u, 0, 0, 0);
    v21 = (struct _MDL *)Pool2[15];
    Pool2[16] = (PVOID *)&Mdl->Next;
    if ( !v21 || !Mdl )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v35 = 38;
        goto LABEL_35;
      }
      goto LABEL_41;
    }
    MmBuildMdlForNonPagedPool(v21);
    MmBuildMdlForNonPagedPool((PMDL)Pool2[16]);
    v22 = v61;
    v23 = *v17 | 1;
    *v17 = v23;
    if ( *(_BYTE *)(v22 + 272) )
    {
      v23 |= 2u;
      *v17 = v23;
    }
    v24 = v62;
    v25 = v23 | (4 * *(_BYTE *)(a1 + 184));
    v17[1] = -17;
    *v17 = v25;
    v17[2] = 2 * v24;
    if ( v24 >= 0x80 )
      v17[3] = v24 >> 7;
    else
      v17[2] = (2 * v24) | 1;
    if ( v67 )
      v17[1] = -1;
    v26 = 2;
    v27 = -1;
    do
    {
      v28 = v27;
      v29 = (unsigned __int8)*v17++;
      v27 = *((_BYTE *)crctable + (v29 ^ v28));
      --v26;
    }
    while ( v26 );
    v30 = v66;
    *v19 = ~v27;
    v31 = Pool2[15];
    *((_DWORD *)Pool2 + 34) = 3;
    *((_DWORD *)Pool2 + 4) = 1296126534;
    *v31 = v30;
    for ( i = *v30; i; i = (_QWORD *)*i )
      v30 = (_QWORD **)i;
    v4 = v61;
    *v30 = Pool2[16];
    v33 = Pool2[16];
    *((_DWORD *)Pool2 + 14) = v24;
    *v33 = 0;
    LODWORD(v33) = v63 + 1;
    Pool2[9] = (PVOID *)v4;
    *((_DWORD *)Pool2 + 13) = v24 + (_DWORD)v33;
    RefObj_InitEx(
      (_DWORD)Pool2 + 24,
      (unsigned int)FrameFree,
      541803329,
      1696,
      (__int64)"onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
    Pool2[9] = (PVOID *)a1;
    if ( P[0] == P )
    {
      v9 = Pool2;
      Pool2[11] = a4;
      v65 = Pool2;
      Pool2[12] = (PVOID *)(v64 + 456);
    }
    else
    {
      v9 = v65;
    }
    v34 = v57;
    if ( *v57 != &v56 )
LABEL_80:
      __fastfail(3u);
    v59 += v24;
    ++v60;
    *Pool2 = &v56;
    Pool2[1] = v34;
    *v34 = Pool2;
    v57 = (PVOID *)Pool2;
    ExFreePoolWithTag(v10, 0);
  }
  v39 = v64;
  v40 = v59;
  v41 = v60;
  while ( 1 )
  {
    v42 = (PVOID **)v56;
    if ( v56 == &v56 )
      break;
    if ( *((PVOID **)v56 + 1) != &v56 )
      goto LABEL_80;
    v43 = *(_QWORD **)v56;
    if ( *(PVOID *)(*(_QWORD *)v56 + 8LL) != v56 )
      goto LABEL_80;
    v56 = *(PVOID *)v56;
    v43[1] = &v56;
    RefObj_AddRefEx(v4 + 24, 1296126534, 1746, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
    RefObj_AddRefEx(a1 + 24, 1296126534, 1747, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
    RefObj_AddRefEx(v39 + 24, 1296126534, 1751, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
    v42[10] = (PVOID *)v39;
    *((_DWORD *)v42 + 15) = v40;
    *((_DWORD *)v42 + 16) = v41;
    if ( v42 != v9 )
    {
      RefObj_AddRefEx(v9 + 3, 1296126534, 1767, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
      v42[14] = (PVOID *)v9;
    }
    v45 = *(PVOID ****)(a1 + 112);
    if ( *v45 != (PVOID **)(a1 + 104) )
      goto LABEL_80;
    *v42 = (PVOID *)(a1 + 104);
    v42[1] = (PVOID *)v45;
    *v45 = v42;
    *(_QWORD *)(a1 + 112) = v42;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v44,
        9,
        39,
        (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
        *(_BYTE *)(a1 + 184));
  }
  v8 = 259;
  if ( ((*(_DWORD *)(a1 + 48) - 5) & 0xFFFFFFFD) == 0 && *(int *)(a1 + 228) > 0 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 56), *(_BYTE *)(v4 + 64));
    ChannelSendData(a1);
    goto LABEL_83;
  }
LABEL_82:
  KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 56), *(_BYTE *)(v4 + 64));
  if ( !v39 )
    goto LABEL_84;
LABEL_83:
  RefObj_ReleaseEx(v39 + 24, 1312901187, 1841, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
LABEL_84:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
    v53 = NtStatusTxt((unsigned int)v8);
    WPP_RECORDER_SF_s(
      (_DWORD)DeviceExtension,
      v54,
      3,
      40,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      v53);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140010810  mov     [rsp-8+arg_8], rbx
0x140010815  mov     [rsp-8+arg_18], r9
0x14001081a  push    rbp
0x14001081b  push    rsi
0x14001081c  push    rdi
0x14001081d  push    r12
0x14001081f  push    r13
0x140010821  push    r14
0x140010823  push    r15
0x140010825  lea     rbp, [rsp-27h]
0x14001082a  sub     rsp, 90h
0x140010831  mov     r15, [rcx+38h]
0x140010835  lea     rax, [rbp+57h+P]
0x140010839  mov     [rbp+57h+var_68], rax
0x14001083d  mov     rbx, rdx
0x140010840  lea     rax, [rbp+57h+P]
0x140010844  mov     [rbp+57h+var_58], r15
0x140010848  mov     [rbp+57h+P], rax
0x14001084c  mov     rsi, rcx
0x14001084f  lea     rax, [rbp+57h+var_80]
0x140010853  mov     [rbp+57h+var_78], rax
0x140010857  lea     rax, [rbp+57h+var_80]
0x14001085b  mov     [rbp+57h+var_80], rax
0x14001085f  lea     r14, WPP_RECORDER_INITIALIZED
0x140010866  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14001086d  lea     r12, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140010874  jz      short loc_14001089A
0x140010876  mov     rcx, cs:WPP_GLOBAL_Control
0x14001087d  mov     r9d, 21h ; '!'
0x140010883  mov     dword ptr [rsp+0C0h+var_98], r8d
0x140010888  mov     [rsp+0C0h+Irp], r12
0x14001088d  mov     rcx, [rcx+40h]
0x140010891  lea     r8d, [r9-1Eh]
0x140010895  call    WPP_RECORDER_SF_d
0x14001089a  lea     rcx, [r15+38h]; SpinLock
0x14001089e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400108a5  nop     dword ptr [rax+rax+00h]
0x1400108aa  mov     edx, 4E414843h
0x1400108af  mov     rcx, rsi
0x1400108b2  mov     [r15+40h], al
0x1400108b6  call    ChannelReferenceConnLocked
0x1400108bb  mov     [rbp+57h+var_48], rax
0x1400108bf  test    rax, rax
0x1400108c2  jnz     short loc_1400108CE
0x1400108c4  mov     edi, 0C000020Ch
0x1400108c9  jmp     loc_140010EEB
0x1400108ce  cmp     dword ptr [r15+30h], 6
0x1400108d3  jz      loc_140010EB4
0x1400108d9  cmp     dword ptr [rsi+30h], 9
0x1400108dd  jz      loc_140010EB4
0x1400108e3  mov     cl, [r15+1D1h]
0x1400108ea  lea     r8, [rbp+57h+P]
0x1400108ee  movzx   eax, word ptr [rsi+0E8h]
0x1400108f5  test    cl, cl
0x1400108f7  mov     [rbp+57h+arg_0], cl
0x1400108fa  mov     rcx, rbx; SourceMdl
0x1400108fd  lea     edx, [rax-1]
0x140010900  cmovz   edx, eax
0x140010903  call    ShortenMdlChain
0x140010908  mov     edi, eax
0x14001090a  test    eax, eax
0x14001090c  js      loc_140010EEB
0x140010912  xor     edi, edi
0x140010914  xor     r12d, r12d
0x140010917  xor     r13d, r13d
0x14001091a  mov     [rbp+57h+var_5C], r12d
0x14001091e  mov     [rbp+57h+var_60], edi
0x140010921  mov     [rbp+57h+var_40], r13
0x140010925  lea     r12d, [rdi+1]
0x140010929  mov     r14, [rbp+57h+P]
0x14001092d  lea     rax, [rbp+57h+P]
0x140010931  cmp     r14, rax
0x140010934  jz      loc_140010D44
0x14001093a  lea     rax, [rbp+57h+P]
0x14001093e  cmp     [r14+8], rax
0x140010942  jnz     loc_140010FA1
0x140010948  mov     rax, [r14]
0x14001094b  cmp     [rax+8], r14
0x14001094f  jnz     loc_140010FA1
0x140010955  mov     [rbp+57h+P], rax
0x140010959  lea     rcx, [rbp+57h+P]
0x14001095d  mov     [rax+8], rcx
0x140010961  mov     edx, 98h
0x140010966  mov     rax, [r14+10h]
0x14001096a  mov     r8d, 52466652h
0x140010970  mov     [rbp+57h+var_38], rax
0x140010974  mov     eax, [r14+18h]
0x140010978  cmp     eax, 80h
0x14001097d  mov     [rbp+57h+var_50], eax
0x140010980  lea     ecx, [rdx-58h]
0x140010983  mov     al, [rbp+57h+arg_0]
0x140010986  sbb     r13d, r13d
0x140010989  add     r13d, 2
0x14001098d  neg     al
0x14001098f  sbb     edi, edi
0x140010991  neg     edi
0x140010993  add     edi, 2
0x140010996  call    cs:__imp_ExAllocatePool2
0x14001099d  nop     dword ptr [rax+rax+00h]
0x1400109a2  mov     rbx, rax
0x1400109a5  test    rax, rax
0x1400109a8  jz      loc_140010D08
0x1400109ae  add     edi, r13d
0x1400109b1  mov     ecx, 40h ; '@'
0x1400109b6  mov     r13d, 52466652h
0x1400109bc  mov     edx, edi
0x1400109be  mov     r8d, r13d
0x1400109c1  mov     [rbp+57h+var_4C], edi
0x1400109c4  call    cs:__imp_ExAllocatePool2
0x1400109cb  nop     dword ptr [rax+rax+00h]
0x1400109d0  mov     r15, rax
0x1400109d3  test    rax, rax
0x1400109d6  jz      loc_140010C4C
0x1400109dc  mov     r8d, r13d
0x1400109df  mov     rdx, r12
0x1400109e2  mov     ecx, 40h ; '@'
0x1400109e7  call    cs:__imp_ExAllocatePool2
0x1400109ee  nop     dword ptr [rax+rax+00h]
0x1400109f3  mov     r13, rax
0x1400109f6  test    rax, rax
0x1400109f9  jz      loc_140010C34
0x1400109ff  xor     r9d, r9d; ChargeQuota
0x140010a02  mov     [rsp+0C0h+Irp], 0; Irp
0x140010a0b  xor     r8d, r8d; SecondaryBuffer
0x140010a0e  mov     edx, edi; Length
0x140010a10  mov     rcx, r15; VirtualAddress
0x140010a13  call    cs:__imp_IoAllocateMdl
0x140010a1a  nop     dword ptr [rax+rax+00h]
0x140010a1f  xor     r9d, r9d; ChargeQuota
0x140010a22  mov     [rsp+0C0h+Irp], 0; Irp
0x140010a2b  xor     r8d, r8d; SecondaryBuffer
0x140010a2e  mov     [rbx+78h], rax
0x140010a32  mov     edx, r12d; Length
0x140010a35  mov     rcx, r13; VirtualAddress
0x140010a38  call    cs:__imp_IoAllocateMdl
0x140010a3f  nop     dword ptr [rax+rax+00h]
0x140010a44  mov     rcx, [rbx+78h]; MemoryDescriptorList
0x140010a48  mov     [rbx+80h], rax
0x140010a4f  test    rcx, rcx
0x140010a52  jz      loc_140010BFD
0x140010a58  test    rax, rax
0x140010a5b  jz      loc_140010BFD
0x140010a61  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140010a68  nop     dword ptr [rax+rax+00h]
0x140010a6d  mov     rcx, [rbx+80h]; MemoryDescriptorList
0x140010a74  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140010a7b  nop     dword ptr [rax+rax+00h]
0x140010a80  mov     cl, [r15]
0x140010a83  xor     r8d, r8d
0x140010a86  mov     rax, [rbp+57h+var_58]
0x140010a8a  or      cl, r12b
0x140010a8d  mov     [r15], cl
0x140010a90  cmp     [rax+110h], r8b
0x140010a97  jz      short loc_140010A9F
0x140010a99  or      cl, 2
0x140010a9c  mov     [r15], cl
0x140010a9f  mov     al, [rsi+0B8h]
0x140010aa5  mov     edi, [rbp+57h+var_50]
0x140010aa8  shl     al, 2
0x140010aab  or      al, cl
0x140010aad  mov     byte ptr [r15+1], 0EFh
0x140010ab2  mov     [r15], al
0x140010ab5  mov     al, dil
0x140010ab8  add     al, al
0x140010aba  mov     [r15+2], al
0x140010abe  cmp     edi, 80h
0x140010ac4  jnb     short loc_140010ACF
0x140010ac6  or      al, r12b
0x140010ac9  mov     [r15+2], al
0x140010acd  jmp     short loc_140010AD8
0x140010acf  mov     eax, edi
0x140010ad1  shr     eax, 7
0x140010ad4  mov     [r15+3], al
0x140010ad8  cmp     [rbp+57h+arg_0], r8b
0x140010adc  jz      short loc_140010AE3
0x140010ade  mov     byte ptr [r15+1], 0FFh
0x140010ae3  mov     dl, 2
0x140010ae5  mov     al, 0FFh
0x140010ae7  movzx   ecx, al
0x140010aea  movzx   eax, byte ptr [r15]
0x140010aee  add     r15, r12
0x140010af1  xor     rcx, rax
0x140010af4  lea     rax, crctable
0x140010afb  mov     al, [rcx+rax]
0x140010afe  add     dl, 0FFh
0x140010b01  jnz     short loc_140010AE7
0x140010b03  mov     rdx, [rbp+57h+var_38]
0x140010b07  not     al
0x140010b09  mov     [r13+0], al
0x140010b0d  mov     rax, [rbx+78h]
0x140010b11  mov     dword ptr [rbx+88h], 3
0x140010b1b  mov     dword ptr [rbx+10h], 4D415246h
0x140010b22  mov     [rax], rdx
0x140010b25  mov     rcx, [rdx]
0x140010b28  test    rcx, rcx
0x140010b2b  jz      short loc_140010B3B
0x140010b2d  mov     rax, [rcx]
0x140010b30  mov     rdx, rcx
0x140010b33  mov     rcx, rax
0x140010b36  test    rax, rax
0x140010b39  jnz     short loc_140010B2D
0x140010b3b  mov     rax, [rbx+80h]
0x140010b42  lea     rcx, [rbx+18h]
0x140010b46  mov     r15, [rbp+57h+var_58]
0x140010b4a  mov     r9d, 6A0h
0x140010b50  mov     [rdx], rax
0x140010b53  lea     rdx, FrameFree
0x140010b5a  mov     rax, [rbx+80h]
0x140010b61  mov     [rbx+38h], edi
0x140010b64  mov     [rax], r8
0x140010b67  mov     r8d, 204B4341h
0x140010b6d  mov     eax, [rbp+57h+var_4C]
0x140010b70  inc     eax
0x140010b72  mov     [rbx+48h], r15
0x140010b76  add     eax, edi
0x140010b78  mov     [rbx+34h], eax
0x140010b7b  lea     rax, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140010b82  mov     [rsp+0C0h+Irp], rax
0x140010b87  call    RefObj_InitEx
0x140010b8c  lea     rax, [rbp+57h+P]
0x140010b90  mov     [rbx+48h], rsi
0x140010b94  cmp     [rbp+57h+P], rax
0x140010b98  jnz     short loc_140010BB9
0x140010b9a  mov     rax, [rbp+57h+arg_18]
0x140010b9e  mov     r13, rbx
0x140010ba1  mov     [rbx+58h], rax
0x140010ba5  mov     rax, [rbp+57h+var_48]
0x140010ba9  add     rax, 1C8h
0x140010baf  mov     [rbp+57h+var_40], rbx
0x140010bb3  mov     [rbx+60h], rax
0x140010bb7  jmp     short loc_140010BBD
0x140010bb9  mov     r13, [rbp+57h+var_40]
0x140010bbd  mov     rax, [rbp+57h+var_78]
0x140010bc1  lea     rcx, [rbp+57h+var_80]
0x140010bc5  cmp     [rax], rcx
0x140010bc8  jnz     loc_140010FA1
0x140010bce  add     [rbp+57h+var_60], edi
0x140010bd1  lea     rcx, [rbp+57h+var_80]
0x140010bd5  add     [rbp+57h+var_5C], r12d
0x140010bd9  xor     edx, edx; Tag
0x140010bdb  mov     [rbx], rcx
0x140010bde  mov     rcx, r14; P
0x140010be1  mov     [rbx+8], rax
0x140010be5  mov     [rax], rbx
0x140010be8  mov     [rbp+57h+var_78], rbx
0x140010bec  call    cs:__imp_ExFreePoolWithTag
0x140010bf3  nop     dword ptr [rax+rax+00h]
0x140010bf8  jmp     loc_140010929
0x140010bfd  lea     rax, WPP_RECORDER_INITIALIZED
0x140010c04  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010c0b  jz      short loc_140010C84
0x140010c0d  mov     r9d, 26h ; '&'
0x140010c13  mov     rcx, cs:WPP_GLOBAL_Control
0x140010c1a  lea     rax, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140010c21  mov     r8d, r12d
0x140010c24  mov     [rsp+0C0h+Irp], rax
0x140010c29  mov     rcx, [rcx+40h]
0x140010c2d  call    WPP_RECORDER_SF_
0x140010c32  jmp     short loc_140010C84
0x140010c34  lea     rax, WPP_RECORDER_INITIALIZED
0x140010c3b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010c42  jz      short loc_140010C84
0x140010c44  mov     r9d, 25h ; '%'
0x140010c4a  jmp     short loc_140010C13
0x140010c4c  lea     rax, WPP_RECORDER_INITIALIZED
0x140010c53  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010c5a  jz      short loc_140010C81
0x140010c5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140010c63  lea     rax, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140010c6a  mov     r9d, 24h ; '$'
0x140010c70  mov     [rsp+0C0h+Irp], rax
0x140010c75  mov     r8d, r12d
0x140010c78  mov     rcx, [rcx+40h]
0x140010c7c  call    WPP_RECORDER_SF_
0x140010c81  xor     r13d, r13d
0x140010c84  mov     rcx, [rbx+80h]; Mdl
0x140010c8b  mov     edi, 0C000009Ah
0x140010c90  test    rcx, rcx
0x140010c93  jz      short loc_140010CA1
0x140010c95  call    cs:__imp_IoFreeMdl
0x140010c9c  nop     dword ptr [rax+rax+00h]
0x140010ca1  mov     rcx, [rbx+78h]; Mdl
0x140010ca5  test    rcx, rcx
0x140010ca8  jz      short loc_140010CB6
0x140010caa  call    cs:__imp_IoFreeMdl
0x140010cb1  nop     dword ptr [rax+rax+00h]
0x140010cb6  xor     edx, edx; Tag
0x140010cb8  mov     rcx, rbx; P
0x140010cbb  call    cs:__imp_ExFreePoolWithTag
0x140010cc2  nop     dword ptr [rax+rax+00h]
0x140010cc7  test    r15, r15
0x140010cca  jz      short loc_140010CDD
0x140010ccc  xor     edx, edx; Tag
0x140010cce  mov     rcx, r15; P
0x140010cd1  call    cs:__imp_ExFreePoolWithTag
0x140010cd8  nop     dword ptr [rax+rax+00h]
0x140010cdd  test    r13, r13
0x140010ce0  jz      short loc_140010CF3
0x140010ce2  xor     edx, edx; Tag
0x140010ce4  mov     rcx, r13; P
  ... truncated ...
```
