# UxDuoRunStreamReceivePump

- ea: `0x1c00c0050`
- end: `0x1c00c0356`
- name: `UxDuoRunStreamReceivePump`
- size: `774`
- prototype: ``
- caller_count: `9`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1c00b94d0`
- `0x1c00c3bc0`
- `0x1c00c5de0`
- `0x1c010fed8`
- `0x1c0112f18`
- `0x1c01130c0`
- `0x1c01136a0`
- `0x1c011446c`
- `0x1c0114690`

## callees

- `0x1c000b798`
- `0x1c000b838`
- `0x1c0011c4c`
- `0x1c001b610`
- `0x1c002b0f8`
- `0x1c008f3a8`
- `0x1c0094924`
- `0x1c0094f24`
- `0x1c0094fe0`
- `0x1c0095714`
- `0x1c0095778`
- `0x1c0095848`
- `0x1c00c0050`
- `0x1c00d1c68`
- `0x1c010ecf0`
- `0x1c0111818`
- `0x1c0111ac4`
- `0x1c0111bf8`
- `0x1c0112a30`
- `0x1c0113ad4`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x1c00c0330`
- `ntoskrnl!IoFreeMdl` at `0x1c00c0330`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00c0345`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00edd5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00eddff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00ede65`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00edf1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00c0345`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00edd5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00eddff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00ede65`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00edf1f`
- `NETIO!RtlCopyMdlToMdl` at `0x1c00edc2f`
- `NETIO!RtlCopyMdlToMdl` at `0x1c00edc2f`

## pseudocode

```c
__int64 __fastcall UxDuoRunStreamReceivePump(__int64 a1, __int64 a2)
{
  _QWORD *v2; // r14
  _QWORD *v4; // rbx
  void **v5; // rsi
  unsigned int *v6; // rbx
  char v7; // al
  _QWORD *v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // rsi
  int updated; // ebx
  unsigned int v12; // r14d
  LONG v13; // r15d
  __int64 v14; // rbp
  __int64 v15; // rdx
  __int64 v16; // r10
  __int64 v17; // r9
  LONG v18; // ecx
  __int64 v20; // rcx
  int v21; // eax
  _QWORD *v22; // rax
  void **v23; // rcx
  void *v24; // rcx
  struct _MDL *v25; // rcx
  __int64 *v26; // rsi
  unsigned int v27; // ebp
  int v28; // eax
  __int64 *v29; // rax
  __int64 **v30; // rcx
  __int64 v31; // rax
  _QWORD *v32; // rcx
  __int64 v33; // rax
  _QWORD *v34; // rcx
  __int64 v35; // rax
  NTSTATUS v36; // eax
  __int64 v37; // rcx
  __int64 v38; // rdx
  int v39; // ecx
  __int64 v40; // rbx
  __int64 v41; // [rsp+28h] [rbp-90h]
  __int128 v42; // [rsp+60h] [rbp-58h] BYREF
  __int128 v43; // [rsp+70h] [rbp-48h]
  LONG plResult; // [rsp+C0h] [rbp+8h] BYREF
  LONG v45; // [rsp+C8h] [rbp+10h] BYREF
  __int64 v46; // [rsp+D0h] [rbp+18h] BYREF
  __int64 v47; // [rsp+D8h] [rbp+20h] BYREF

  v46 = 0;
  v2 = (_QWORD *)(a1 + 352);
  v42 = 0;
  v43 = 0;
  while ( 1 )
  {
    v4 = (_QWORD *)*v2;
    if ( (_QWORD *)*v2 == v2 )
      break;
    v26 = *(__int64 **)(a1 + 336);
    if ( v26 == (__int64 *)(a1 + 336) )
    {
      if ( v4 != v2 && v4[3] )
      {
        v33 = *v4;
        if ( *(_QWORD **)(*v4 + 8LL) != v4 || (v34 = (_QWORD *)v4[1], (_QWORD *)*v34 != v4) )
LABEL_44:
          __fastfail(3u);
        *v34 = v33;
        *(_QWORD *)(v33 + 8) = v34;
        *v4 = 0;
        v4[1] = 0;
        if ( (HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x4000000) != 0 )
        {
          LODWORD(v41) = *((_DWORD *)v4 + 4);
          WPP_SF_DDqdP(
            24,
            *(_QWORD *)(a1 + 32),
            *(unsigned int *)(*(_QWORD *)(a1 + 32) + 824LL),
            *(unsigned int *)(a1 + 72),
            v4[11],
            v41,
            v4[3]);
        }
        UlInvokeCompletionRoutine(*((unsigned int *)v4 + 4), v4[3], v4[10], v4[11]);
        ExFreePoolWithTag(v4, 0);
      }
      break;
    }
    RtlCopyMdlToMdl(v26[2], *((unsigned int *)v26 + 6), v4[7], v4[4], *((unsigned int *)v26 + 7), &v46);
    v27 = v46;
    if ( (HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x4000000) != 0 )
      WPP_SF_DDd(22, a2, *(unsigned int *)(*(_QWORD *)(a1 + 32) + 824LL), *(unsigned int *)(a1 + 72), v46);
    v4[3] += v27;
    v4[4] += v27;
    v4[5] -= v27;
    *((_DWORD *)v26 + 7) -= v27;
    *((_DWORD *)v26 + 6) += v27;
    v28 = *((_DWORD *)v26 + 7);
    if ( *((_BYTE *)v26 + 76) )
    {
      UxDuoReleaseReceiveWindow(*(_QWORD *)(a1 + 32), a1, v27);
      v28 = *((_DWORD *)v26 + 7);
    }
    if ( !v28 )
    {
      v29 = (__int64 *)*v26;
      if ( *(__int64 **)(*v26 + 8) != v26 )
        goto LABEL_44;
      v30 = (__int64 **)v26[1];
      if ( *v30 != v26 )
        goto LABEL_44;
      *v30 = v29;
      v29[1] = (__int64)v30;
      *v26 = 0;
      v26[1] = 0;
      UxDuoFreeDelivery(a1, v26);
    }
    if ( !v4[5] )
    {
      v31 = *v4;
      if ( *(_QWORD **)(*v4 + 8LL) != v4 )
        goto LABEL_44;
      v32 = (_QWORD *)v4[1];
      if ( (_QWORD *)*v32 != v4 )
        goto LABEL_44;
      *v32 = v31;
      *(_QWORD *)(v31 + 8) = v32;
      *v4 = 0;
      v4[1] = 0;
      if ( (HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x4000000) != 0 )
      {
        LODWORD(v41) = *((_DWORD *)v4 + 4);
        WPP_SF_DDqdP(
          23,
          *(_QWORD *)(a1 + 32),
          *(unsigned int *)(*(_QWORD *)(a1 + 32) + 824LL),
          *(unsigned int *)(a1 + 72),
          v4[11],
          v41,
          v4[3]);
      }
      UlInvokeCompletionRoutine(*((unsigned int *)v4 + 4), v4[3], v4[10], v4[11]);
      ExFreePoolWithTag(v4, 0);
    }
  }
  v5 = (void **)(a1 + 336);
  while ( 1 )
  {
    v6 = (unsigned int *)*v5;
    if ( *v5 == v5 || *(_BYTE *)(a1 + 445) && !*(_BYTE *)(a1 + 446) )
      break;
    if ( !*(_BYTE *)(a1 + 446) )
    {
      if ( (HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x4000000) != 0 )
        WPP_SF_DDLq(
          *(_QWORD *)(a1 + 32),
          a2,
          *(unsigned int *)(*(_QWORD *)(a1 + 32) + 824LL),
          *(unsigned int *)(a1 + 72),
          v6[7],
          *(_QWORD *)(a1 + 8));
      v20 = *(_QWORD *)(a1 + 8);
      *(_QWORD *)&v42 = 0;
      DWORD1(v43) = 0;
      *((_QWORD *)&v42 + 1) = *((_QWORD *)v6 + 2);
      LODWORD(v43) = v6[6];
      *((_QWORD *)&v43 + 1) = v6[7];
      v21 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, _QWORD))(*(_QWORD *)(a1 + 16) + 40LL))(
              v20,
              0,
              &v42,
              v6[7]);
      if ( v21 < 0 )
      {
        if ( (HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x4000000) != 0 )
          WPP_SF_DDd(
            26,
            (unsigned int)v21,
            *(unsigned int *)(*(_QWORD *)(a1 + 32) + 824LL),
            *(unsigned int *)(a1 + 72),
            v21);
        *(_BYTE *)(a1 + 445) = 1;
        break;
      }
    }
    v22 = *(_QWORD **)v6;
    if ( *(unsigned int **)(*(_QWORD *)v6 + 8LL) != v6 )
      goto LABEL_44;
    v23 = (void **)*((_QWORD *)v6 + 1);
    if ( *v23 != v6 )
      goto LABEL_44;
    *v23 = v22;
    v22[1] = v23;
    *(_QWORD *)v6 = 0;
    *((_QWORD *)v6 + 1) = 0;
    if ( *((_BYTE *)v6 + 76) )
      UxDuoReleaseReceiveWindow(*(_QWORD *)(a1 + 32), a1, v6[7]);
    UxTerminateExbuffer(v6 + 8);
    v24 = (void *)*((_QWORD *)v6 + 8);
    if ( v24 )
    {
      ExFreePoolWithTag(v24, 0);
      *((_QWORD *)v6 + 8) = 0;
    }
    v25 = (struct _MDL *)*((_QWORD *)v6 + 2);
    if ( v25 )
    {
      IoFreeMdl(v25);
      *((_QWORD *)v6 + 2) = 0;
    }
    ExFreePoolWithTag(v6, 0);
  }
  v7 = *(_BYTE *)(a1 + 447);
  if ( v7 )
  {
    while ( 1 )
    {
      v8 = (_QWORD *)*v2;
      if ( (_QWORD *)*v2 == v2 )
        break;
      if ( (_QWORD *)v8[1] != v2 )
        goto LABEL_44;
      v35 = *v8;
      if ( *(_QWORD **)(*v8 + 8LL) != v8 )
        goto LABEL_44;
      *v2 = v35;
      *(_QWORD *)(v35 + 8) = v2;
      *v8 = 0;
      v8[1] = 0;
      if ( (HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x4000000) != 0 )
        WPP_SF_DDq(
          27,
          WPP_e4d82b0664f433ba4e49d0d4a417570b_Traceguids,
          *(unsigned int *)(*(_QWORD *)(a1 + 32) + 824LL),
          *(unsigned int *)(a1 + 72),
          v8[11]);
      UlInvokeCompletionRoutine(0, 0, v8[10], v8[11]);
      ExFreePoolWithTag(v8, 0);
    }
    v7 = *(_BYTE *)(a1 + 447);
  }
  if ( *v5 == v5 && v7 && !*(_BYTE *)(a1 + 451) && !*(_BYTE *)(a1 + 446) )
  {
    if ( (HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x4000000) != 0 )
      WPP_SF_DDq(
        28,
        WPP_e4d82b0664f433ba4e49d0d4a417570b_Traceguids,
        *(unsigned int *)(*(_QWORD *)(a1 + 32) + 824LL),
        *(unsigned int *)(a1 + 72),
        *(_QWORD *)(a1 + 8));
    v9 = *(unsigned int *)(*(_QWORD *)(a1 + 32) + 324LL);
    if ( !*(_BYTE *)(a1 + 453) || *(_BYTE *)(a1 + 454) )
      LODWORD(v9) = v9 | 0x400;
    *(_BYTE *)(a1 + 451) = 1;
    (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)(a1 + 16) + 32LL))(*(_QWORD *)(a1 + 8), v9);
  }
  if ( *(_BYTE *)(a1 + 447) && *(_BYTE *)(a1 + 449) )
  {
    if ( (HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x4000000) != 0 )
      WPP_SF_DD(
        29,
        WPP_e4d82b0664f433ba4e49d0d4a417570b_Traceguids,
        *(unsigned int *)(*(_QWORD *)(a1 + 32) + 824LL),
        *(unsigned int *)(a1 + 72));
    UxDuoCleanupStream(a1);
  }
  v10 = *(_QWORD *)(a1 + 32);
  updated = 0;
  v12 = 0;
  plResult = 0;
  v13 = 0;
  v45 = 0;
  v47 = 0;
  if ( !*(_BYTE *)(v10 + 309) && *(_DWORD *)(v10 + 360) == 3 )
  {
    v14 = 0;
    v15 = *(int *)(v10 + 628);
    if ( !*(_BYTE *)(a1 + 76) )
      v14 = a1;
    if ( (int)v15 < 0x100000 )
    {
      updated = UxDuoWindowUpdateHelper(v10, v14, &plResult, &v45);
      if ( updated < 0 )
        goto LABEL_101;
      v12 = plResult;
      v13 = v45;
LABEL_34:
      if ( !v12 && !v13 )
        goto LABEL_36;
      updated = UxDuoAllocateParcel(8, v14, v10, 4, 0, (__int64)&v47);
      if ( updated >= 0 )
      {
        v40 = v47;
        *(_DWORD *)(v47 + 100) = v12;
        *(_DWORD *)(v40 + 96) = v13;
        if ( v14 )
        {
          if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x4000000) != 0 )
            WPP_SF_DDdddddddd(
              v39,
              v38,
              *(_DWORD *)(v10 + 824),
              *(_DWORD *)(v14 + 72),
              v12,
              *(_DWORD *)(v10 + 620),
              *(_DWORD *)(v10 + 624),
              *(_DWORD *)(v10 + 628),
              v13,
              *(_DWORD *)(v14 + 288),
              *(_DWORD *)(v14 + 292),
              *(_DWORD *)(v14 + 296));
        }
        else if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x4000000) != 0 )
        {
          WPP_SF_Ddddd(
            17,
            v38,
            *(unsigned int *)(v10 + 824),
            v12,
            *(_DWORD *)(v10 + 620),
            *(_DWORD *)(v10 + 624),
            *(_DWORD *)(v10 + 628));
        }
        UxDuoSubmitParcel(v40);
        updated = UxDuoDispatchConnectionSends(v10);
LABEL_36:
        if ( updated >= 0 )
          return (unsigned int)updated;
      }
LABEL_101:
      if ( !*(_DWORD *)(v10 + 632) && (!v14 || !*(_DWORD *)(v14 + 208)) )
        UxDuoSetFault(v10, 0, 1045, (unsigned int)updated);
      v37 = *(_QWORD *)(a1 + 32);
      if ( !*(_DWORD *)(v37 + 632) && !*(_DWORD *)(a1 + 208) )
        UxDuoSetFault(v37, 0, 1045, (unsigned int)updated);
      return (unsigned int)updated;
    }
    v16 = *(int *)(v10 + 620);
    v17 = v15 - *(int *)(v10 + 624) - v16;
    v18 = 0;
    plResult = 0;
    if ( (unsigned __int64)(v17 + 0x80000000LL) > 0xFFFFFFFF )
    {
      updated = -1073741675;
      UxDuoSetFault(v10, 0, 1062, 3221225621LL);
      goto LABEL_97;
    }
    if ( v14 && !*(_BYTE *)(v14 + 447) )
    {
      v36 = RtlLongLongToLong(*(int *)(v14 + 296) - (__int64)*(int *)(v14 + 292) - *(int *)(v14 + 288), &plResult);
      updated = v36;
      if ( v36 < 0 )
      {
        UxDuoSetFault(v10, 0, 1062, (unsigned int)v36);
        goto LABEL_33;
      }
      v18 = plResult;
    }
    if ( (int)v17 < 0x10000 )
      LODWORD(v17) = 0;
    if ( v18 < 0x10000 )
      v18 = 0;
    if ( (_DWORD)v17 || v18 )
    {
      *(_DWORD *)(v10 + 620) = v17 + v16;
      if ( v14 )
        *(_DWORD *)(v14 + 288) += v18;
      v12 = v17;
      v13 = v18;
    }
LABEL_33:
    if ( updated >= 0 )
      goto LABEL_34;
LABEL_97:
    if ( !*(_DWORD *)(v10 + 632) && (!v14 || !*(_DWORD *)(v14 + 208)) )
      UxDuoSetFault(v10, 0, 1045, (unsigned int)updated);
    goto LABEL_101;
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1c00c0050  mov     rax, rsp
0x1c00c0053  push    rbx
0x1c00c0054  push    rdi
0x1c00c0055  push    r12
0x1c00c0057  push    r14
0x1c00c0059  sub     rsp, 98h
0x1c00c0060  xorps   xmm0, xmm0
0x1c00c0063  mov     [rax-28h], rbp
0x1c00c0067  xor     r12d, r12d
0x1c00c006a  mov     [rax-30h], rsi
0x1c00c006e  mov     [rax+18h], r12
0x1c00c0072  lea     r14, [rcx+160h]
0x1c00c0079  movups  xmmword ptr [rax-58h], xmm0
0x1c00c007d  mov     rdi, rcx
0x1c00c0080  movups  xmmword ptr [rax-48h], xmm0
0x1c00c0084  mov     rbx, [r14]
0x1c00c0087  cmp     rbx, r14
0x1c00c008a  jnz     loc_1C00EDBF8
0x1c00c0090  lea     rsi, [rdi+150h]
0x1c00c0097  mov     rbx, [rsi]
0x1c00c009a  cmp     rbx, rsi
0x1c00c009d  jnz     loc_1C00C0254
0x1c00c00a3  movzx   eax, byte ptr [rdi+1BFh]
0x1c00c00aa  test    al, al
0x1c00c00ac  jz      short loc_1C00C00C1
0x1c00c00ae  mov     rbx, [r14]
0x1c00c00b1  cmp     rbx, r14
0x1c00c00b4  jnz     loc_1C00EDEAF
0x1c00c00ba  movzx   eax, byte ptr [rdi+1BFh]
0x1c00c00c1  mov     [rsp+0B8h+var_38], r15
0x1c00c00c9  cmp     [rsi], rsi
0x1c00c00cc  jnz     short loc_1C00C0128
0x1c00c00ce  test    al, al
0x1c00c00d0  jz      short loc_1C00C0128
0x1c00c00d2  cmp     [rdi+1C3h], r12b
0x1c00c00d9  jnz     short loc_1C00C0128
0x1c00c00db  cmp     [rdi+1BEh], r12b
0x1c00c00e2  jnz     short loc_1C00C0128
0x1c00c00e4  test    dword ptr cs:WPP_MAIN_CB.Queue+4, 4000000h
0x1c00c00ee  jnz     loc_1C00EDF31
0x1c00c00f4  mov     rax, [rdi+20h]
0x1c00c00f8  mov     edx, [rax+144h]
0x1c00c00fe  cmp     [rdi+1C5h], r12b
0x1c00c0105  jnz     loc_1C00EDF60
0x1c00c010b  bts     edx, 0Ah
0x1c00c010f  mov     byte ptr [rdi+1C3h], 1
0x1c00c0116  mov     rax, [rdi+10h]
0x1c00c011a  mov     rcx, [rdi+8]
0x1c00c011e  mov     rax, [rax+20h]
0x1c00c0122  call    cs:__guard_dispatch_icall_fptr
0x1c00c0128  cmp     [rdi+1BFh], r12b
0x1c00c012f  jz      short loc_1C00C013E
0x1c00c0131  cmp     [rdi+1C1h], r12b
0x1c00c0138  jnz     loc_1C00C02D3
0x1c00c013e  mov     rsi, [rdi+20h]
0x1c00c0142  mov     ebx, r12d
0x1c00c0145  mov     r14d, r12d
0x1c00c0148  mov     [rsp+0B8h+plResult], r12d
0x1c00c0150  mov     r15d, r12d
0x1c00c0153  mov     [rsp+0B8h+arg_8], r12d
0x1c00c015b  mov     [rsp+0B8h+arg_18], r12
0x1c00c0163  cmp     [rsi+135h], bl
0x1c00c0169  jnz     loc_1C00C022B
0x1c00c016f  cmp     dword ptr [rsi+168h], 3
0x1c00c0176  jnz     loc_1C00C022B
0x1c00c017c  cmp     [rdi+4Ch], bl
0x1c00c017f  mov     rbp, r12
0x1c00c0182  movsxd  rdx, dword ptr [rsi+274h]
0x1c00c0189  cmovz   rbp, rdi
0x1c00c018d  cmp     edx, 100000h
0x1c00c0193  jl      loc_1C00EE0BB
0x1c00c0199  movsxd  rax, dword ptr [rsi+270h]
0x1c00c01a0  mov     r9, rdx
0x1c00c01a3  movsxd  r10, dword ptr [rsi+26Ch]
0x1c00c01aa  sub     r9, rax
0x1c00c01ad  sub     r9, r10
0x1c00c01b0  mov     eax, 80000000h
0x1c00c01b5  add     rax, r9
0x1c00c01b8  mov     edx, 0FFFFFFFFh
0x1c00c01bd  mov     ecx, r12d
0x1c00c01c0  mov     [rsp+0B8h+plResult], ecx
0x1c00c01c7  cmp     rax, rdx
0x1c00c01ca  ja      loc_1C00EE00B
0x1c00c01d0  test    rbp, rbp
0x1c00c01d3  jz      short loc_1C00C01E1
0x1c00c01d5  cmp     [rbp+1BFh], cl
0x1c00c01db  jz      loc_1C00EDF98
0x1c00c01e1  cmp     r9d, 10000h
0x1c00c01e8  jge     short loc_1C00C01ED
0x1c00c01ea  mov     r9d, r12d
0x1c00c01ed  cmp     ecx, 10000h
0x1c00c01f3  jge     short loc_1C00C01F8
0x1c00c01f5  mov     ecx, r12d
0x1c00c01f8  test    r9d, r9d
0x1c00c01fb  jnz     loc_1C00EDFEB
0x1c00c0201  test    ecx, ecx
0x1c00c0203  jnz     loc_1C00EDFEB
0x1c00c0209  test    ebx, ebx
0x1c00c020b  js      loc_1C00EE023
0x1c00c0211  test    r14d, r14d
0x1c00c0214  jnz     loc_1C00EE0F5
0x1c00c021a  test    r15d, r15d
0x1c00c021d  jnz     loc_1C00EE0F5
0x1c00c0223  test    ebx, ebx
0x1c00c0225  js      loc_1C00EE055
0x1c00c022b  mov     r15, [rsp+0B8h+var_38]
0x1c00c0233  mov     eax, ebx
0x1c00c0235  mov     rsi, [rsp+0B8h+var_30]
0x1c00c023d  mov     rbp, [rsp+0B8h+var_28]
0x1c00c0245  add     rsp, 98h
0x1c00c024c  pop     r14
0x1c00c024e  pop     r12
0x1c00c0250  pop     rdi
0x1c00c0251  pop     rbx
0x1c00c0252  retn
0x1c00c0254  cmp     [rdi+1BDh], r12b
0x1c00c025b  jnz     loc_1C00EDE11
0x1c00c0261  cmp     [rdi+1BEh], r12b
0x1c00c0268  jnz     short loc_1C00C02C3
0x1c00c026a  test    dword ptr cs:WPP_MAIN_CB.Queue+4, 4000000h
0x1c00c0274  jnz     loc_1C00EDE23
0x1c00c027a  mov     rcx, [rdi+8]
0x1c00c027e  lea     r8, [rsp+0B8h+var_58]
0x1c00c0283  mov     [rsp+0B8h+var_58], r12
0x1c00c0288  xor     edx, edx
0x1c00c028a  mov     [rsp+0B8h+var_44], r12d
0x1c00c028f  mov     rax, [rbx+10h]
0x1c00c0293  mov     [rsp+0B8h+var_50], rax
0x1c00c0298  mov     eax, [rbx+18h]
0x1c00c029b  mov     [rsp+0B8h+var_48], eax
0x1c00c029f  mov     eax, [rbx+1Ch]
0x1c00c02a2  mov     [rsp+0B8h+var_40], rax
0x1c00c02a7  mov     rax, [rdi+10h]
0x1c00c02ab  mov     r9d, [rbx+1Ch]
0x1c00c02af  mov     rax, [rax+28h]
0x1c00c02b3  call    cs:__guard_dispatch_icall_fptr
0x1c00c02b9  mov     edx, eax
0x1c00c02bb  test    eax, eax
0x1c00c02bd  js      loc_1C00EDE7A
0x1c00c02c3  mov     rax, [rbx]
0x1c00c02c6  cmp     [rax+8], rbx
0x1c00c02ca  jz      short loc_1C00C02F0
0x1c00c02cc  mov     ecx, 3
0x1c00c02d1  int     29h; Win8: RtlFailFast(ecx)
0x1c00c02d3  test    dword ptr cs:WPP_MAIN_CB.Queue+4, 4000000h
0x1c00c02dd  jnz     loc_1C00EDF72
0x1c00c02e3  mov     rcx, rdi
0x1c00c02e6  call    UxDuoCleanupStream
0x1c00c02eb  jmp     loc_1C00C013E
0x1c00c02f0  mov     rcx, [rbx+8]
0x1c00c02f4  cmp     [rcx], rbx
0x1c00c02f7  jnz     short loc_1C00C02CC
0x1c00c02f9  mov     [rcx], rax
0x1c00c02fc  mov     [rax+8], rcx
0x1c00c0300  mov     [rbx], r12
0x1c00c0303  mov     [rbx+8], r12
0x1c00c0307  cmp     [rbx+4Ch], r12b
0x1c00c030b  jnz     loc_1C00EDE4D
0x1c00c0311  lea     rcx, [rbx+20h]
0x1c00c0315  call    UxTerminateExbuffer
0x1c00c031a  mov     rcx, [rbx+40h]; P
0x1c00c031e  test    rcx, rcx
0x1c00c0321  jnz     loc_1C00EDE63
0x1c00c0327  mov     rcx, [rbx+10h]; Mdl
0x1c00c032b  test    rcx, rcx
0x1c00c032e  jz      short loc_1C00C0340
0x1c00c0330  call    cs:__imp_IoFreeMdl
0x1c00c0337  nop     dword ptr [rax+rax+00h]
0x1c00c033c  mov     [rbx+10h], r12
0x1c00c0340  xor     edx, edx; Tag
0x1c00c0342  mov     rcx, rbx; P
0x1c00c0345  call    cs:__imp_ExFreePoolWithTag
0x1c00c034c  nop     dword ptr [rax+rax+00h]
0x1c00c0351  jmp     loc_1C00C0097
0x1c00edbf8  lea     rax, [rdi+150h]
0x1c00edbff  mov     rsi, [rax]
0x1c00edc02  cmp     rsi, rax
0x1c00edc05  jz      loc_1C00EDD6D
0x1c00edc0b  mov     eax, [rsi+1Ch]
0x1c00edc0e  lea     rcx, [rsp+0B8h+arg_10]
0x1c00edc16  mov     edx, [rsi+18h]
0x1c00edc19  mov     r9, [rbx+20h]
0x1c00edc1d  mov     r8, [rbx+38h]
0x1c00edc21  mov     [rsp+0B8h+var_90], rcx
0x1c00edc26  mov     rcx, [rsi+10h]
0x1c00edc2a  mov     [rsp+0B8h+var_98], rax
0x1c00edc2f  call    cs:__imp_RtlCopyMdlToMdl
0x1c00edc36  nop     dword ptr [rax+rax+00h]
0x1c00edc3b  mov     rbp, [rsp+0B8h+arg_10]
0x1c00edc43  test    dword ptr cs:WPP_MAIN_CB.Queue+4, 4000000h
0x1c00edc4d  jz      short loc_1C00EDC6C
0x1c00edc4f  mov     rax, [rdi+20h]
0x1c00edc53  mov     ecx, 16h
0x1c00edc58  mov     r9d, [rdi+48h]
0x1c00edc5c  mov     dword ptr [rsp+0B8h+var_98], ebp
0x1c00edc60  mov     r8d, [rax+338h]
0x1c00edc67  call    WPP_SF_DDd
0x1c00edc6c  mov     eax, ebp
0x1c00edc6e  add     [rbx+18h], rax
0x1c00edc72  add     [rbx+20h], rax
0x1c00edc76  sub     [rbx+28h], rax
0x1c00edc7a  sub     [rsi+1Ch], ebp
0x1c00edc7d  add     [rsi+18h], ebp
0x1c00edc80  mov     eax, [rsi+1Ch]
0x1c00edc83  cmp     [rsi+4Ch], r12b
0x1c00edc87  jz      short loc_1C00EDC9B
0x1c00edc89  mov     rcx, [rdi+20h]
0x1c00edc8d  mov     r8d, ebp
0x1c00edc90  mov     rdx, rdi
0x1c00edc93  call    UxDuoReleaseReceiveWindow
0x1c00edc98  mov     eax, [rsi+1Ch]
0x1c00edc9b  test    eax, eax
0x1c00edc9d  jnz     short loc_1C00EDCD2
0x1c00edc9f  mov     rax, [rsi]
0x1c00edca2  cmp     [rax+8], rsi
0x1c00edca6  jnz     loc_1C00C02CC
0x1c00edcac  mov     rcx, [rsi+8]
0x1c00edcb0  cmp     [rcx], rsi
0x1c00edcb3  jnz     loc_1C00C02CC
0x1c00edcb9  mov     [rcx], rax
0x1c00edcbc  mov     rdx, rsi
0x1c00edcbf  mov     [rax+8], rcx
0x1c00edcc3  mov     rcx, rdi
0x1c00edcc6  mov     [rsi], r12
0x1c00edcc9  mov     [rsi+8], r12
0x1c00edccd  call    UxDuoFreeDelivery
0x1c00edcd2  cmp     [rbx+28h], r12
0x1c00edcd6  jnz     loc_1C00C0084
0x1c00edcdc  mov     rax, [rbx]
0x1c00edcdf  cmp     [rax+8], rbx
0x1c00edce3  jnz     loc_1C00C02CC
0x1c00edce9  mov     rcx, [rbx+8]
0x1c00edced  cmp     [rcx], rbx
0x1c00edcf0  jnz     loc_1C00C02CC
0x1c00edcf6  mov     [rcx], rax
0x1c00edcf9  mov     [rax+8], rcx
0x1c00edcfd  mov     [rbx], r12
0x1c00edd00  mov     [rbx+8], r12
0x1c00edd04  test    dword ptr cs:WPP_MAIN_CB.Queue+4, 4000000h
0x1c00edd0e  jz      short loc_1C00EDD42
0x1c00edd10  mov     rax, [rbx+18h]
0x1c00edd14  mov     ecx, 17h
0x1c00edd19  mov     rdx, [rdi+20h]
0x1c00edd1d  mov     r9d, [rdi+48h]
0x1c00edd21  mov     [rsp+0B8h+var_88], rax
0x1c00edd26  mov     eax, [rbx+10h]
0x1c00edd29  mov     r8d, [rdx+338h]
0x1c00edd30  mov     dword ptr [rsp+0B8h+var_90], eax
0x1c00edd34  mov     rax, [rbx+58h]
0x1c00edd38  mov     [rsp+0B8h+var_98], rax
0x1c00edd3d  call    WPP_SF_DDqdP
0x1c00edd42  mov     r9, [rbx+58h]
0x1c00edd46  mov     r8, [rbx+50h]
0x1c00edd4a  mov     rdx, [rbx+18h]
0x1c00edd4e  mov     ecx, [rbx+10h]
0x1c00edd51  call    UlInvokeCompletionRoutine
0x1c00edd56  xor     edx, edx; Tag
0x1c00edd58  mov     rcx, rbx; P
0x1c00edd5b  call    cs:__imp_ExFreePoolWithTag
0x1c00edd62  nop     dword ptr [rax+rax+00h]
0x1c00edd67  nop
0x1c00edd68  jmp     loc_1C00C0084
0x1c00edd6d  cmp     rbx, r14
0x1c00edd70  jz      loc_1C00C0090
0x1c00edd76  cmp     [rbx+18h], r12
0x1c00edd7a  jz      loc_1C00C0090
0x1c00edd80  mov     rax, [rbx]
0x1c00edd83  cmp     [rax+8], rbx
0x1c00edd87  jnz     loc_1C00C02CC
0x1c00edd8d  mov     rcx, [rbx+8]
0x1c00edd91  cmp     [rcx], rbx
0x1c00edd94  jnz     loc_1C00C02CC
0x1c00edd9a  mov     [rcx], rax
0x1c00edd9d  mov     [rax+8], rcx
0x1c00edda1  mov     [rbx], r12
0x1c00edda4  mov     [rbx+8], r12
0x1c00edda8  test    dword ptr cs:WPP_MAIN_CB.Queue+4, 4000000h
0x1c00eddb2  jz      short loc_1C00EDDE6
0x1c00eddb4  mov     rax, [rbx+18h]
0x1c00eddb8  mov     ecx, 18h
0x1c00eddbd  mov     rdx, [rdi+20h]
0x1c00eddc1  mov     r9d, [rdi+48h]
0x1c00eddc5  mov     [rsp+0B8h+var_88], rax
0x1c00eddca  mov     eax, [rbx+10h]
0x1c00eddcd  mov     r8d, [rdx+338h]
0x1c00eddd4  mov     dword ptr [rsp+0B8h+var_90], eax
0x1c00eddd8  mov     rax, [rbx+58h]
0x1c00edddc  mov     [rsp+0B8h+var_98], rax
0x1c00edde1  call    WPP_SF_DDqdP
0x1c00edde6  mov     r9, [rbx+58h]
0x1c00eddea  mov     r8, [rbx+50h]
0x1c00eddee  mov     rdx, [rbx+18h]
0x1c00eddf2  mov     ecx, [rbx+10h]
0x1c00eddf5  call    UlInvokeCompletionRoutine
0x1c00eddfa  xor     edx, edx; Tag
0x1c00eddfc  mov     rcx, rbx; P
0x1c00eddff  call    cs:__imp_ExFreePoolWithTag
0x1c00ede06  nop     dword ptr [rax+rax+00h]
0x1c00ede0b  nop
0x1c00ede0c  jmp     loc_1C00C0090
  ... truncated ...
```
