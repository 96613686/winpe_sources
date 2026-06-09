# IppReceivePackets

- ea: `0x1400cffc0`
- end: `0x1400d085e`
- name: `IppReceivePackets`
- size: `2206`
- prototype: ``
- caller_count: `10`
- callee_count: `11`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400ceda0`
- `0x1400cf8f4`
- `0x1400cffa0`
- `0x1400cffc0`
- `0x1400d0904`
- `0x1400d7150`
- `0x1400f3320`
- `0x140149b4c`
- `0x14018bc8c`
- `0x1401abda0`

## callees

- `0x140068bbc`
- `0x14006a6f0`
- `0x14006b590`
- `0x14006c930`
- `0x14006d580`
- `0x14006dd30`
- `0x1400cffc0`
- `0x14013f860`
- `0x1401bf700`
- `0x1401bfa80`
- `0x1401bffa0`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400d04dc`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400d04dc`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400d01fd`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400d01fd`
- `ntoskrnl!KfRaiseIrql` at `0x1400d0069`
- `ntoskrnl!KfRaiseIrql` at `0x1400d058a`
- `ntoskrnl!KfRaiseIrql` at `0x1400d0069`
- `ntoskrnl!KfRaiseIrql` at `0x1400d058a`
- `ntoskrnl!KeLowerIrql` at `0x1400d057c`
- `ntoskrnl!KeLowerIrql` at `0x1400d0703`
- `ntoskrnl!KeLowerIrql` at `0x1400d0720`
- `ntoskrnl!KeLowerIrql` at `0x1400d057c`
- `ntoskrnl!KeLowerIrql` at `0x1400d0703`
- `ntoskrnl!KeLowerIrql` at `0x1400d0720`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400d00e3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400d0538`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400d059b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400d06b6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400d00e3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400d0538`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400d059b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400d06b6`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x1400d010e`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x1400d05c6`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x1400d010e`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x1400d05c6`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1400d0836`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1400d0836`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x1400d0051`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x1400d0051`

## pseudocode

```c
void __fastcall IppReceivePackets(__int64 a1, _QWORD *a2, bool a3, unsigned int a4)
{
  __int64 *v4; // rbx
  char v5; // di
  _QWORD *v6; // r13
  __int64 v7; // rsi
  __int64 v8; // r15
  unsigned int v9; // eax
  KIRQL v10; // dl
  unsigned int LockArray_high; // eax
  _QWORD *v12; // r14
  bool v13; // zf
  __int64 v14; // r12
  __int64 v15; // rsi
  int *v16; // rbx
  int v17; // eax
  __int64 *v18; // rbx
  int v19; // r12d
  __int64 v20; // rcx
  int v21; // ecx
  __int64 v22; // rdx
  __int64 v23; // rbx
  _QWORD *v24; // r14
  __int64 v25; // rdx
  char v26; // al
  __int64 v27; // r9
  _QWORD *v28; // r8
  __int64 v29; // rdx
  _QWORD *v30; // rdi
  char v31; // dl
  char v32; // al
  __int64 v33; // rdx
  _DWORD *v34; // rcx
  int *v35; // rbx
  int v36; // eax
  unsigned int v37; // eax
  __int64 v38; // rcx
  __int64 v39; // rax
  _DWORD *v40; // rcx
  _QWORD *v41; // rdi
  _QWORD *v42; // r8
  _QWORD *v43; // rbx
  __int64 v44; // rdx
  unsigned int v45; // eax
  __int64 v46; // r9
  __int64 v47; // rcx
  KIRQL v48; // [rsp+60h] [rbp-69h]
  char v49; // [rsp+61h] [rbp-68h]
  unsigned int v50; // [rsp+64h] [rbp-65h]
  int v51; // [rsp+68h] [rbp-61h]
  __int128 v52; // [rsp+70h] [rbp-59h] BYREF
  __int64 *v53; // [rsp+80h] [rbp-49h]
  unsigned int v54; // [rsp+88h] [rbp-41h]
  int v55; // [rsp+8Ch] [rbp-3Dh]
  __int64 v56; // [rsp+90h] [rbp-39h]
  __int128 v57; // [rsp+98h] [rbp-31h] BYREF
  __int128 v58; // [rsp+A8h] [rbp-21h] BYREF
  __int128 v59; // [rsp+B8h] [rbp-11h] BYREF
  __int64 v60; // [rsp+C8h] [rbp-1h] BYREF
  _QWORD *v61; // [rsp+D0h] [rbp+7h] BYREF
  __int64 v62; // [rsp+D8h] [rbp+Fh]
  __int64 v63; // [rsp+E0h] [rbp+17h]
  bool v65; // [rsp+140h] [rbp+77h]
  char v66; // [rsp+148h] [rbp+7Fh]

  v65 = a3;
  v4 = *(__int64 **)(a1 + 8);
  v60 = 0;
  v52 = 0;
  v5 = a4;
  v6 = a2;
  v57 = 0;
  v7 = a1;
  v53 = v4;
  v58 = 0;
  v59 = 0;
  v56 = *v4;
  v8 = *(_QWORD *)(v56 + 40);
  v9 = a4 >> 1;
  LOBYTE(v9) = (a4 & 2) != 0;
  v54 = v9;
  if ( LOBYTE(WPP_MAIN_CB.DeviceExtension) )
  {
    NdisNblTrackerTransferOwnership(a2, 0, *(_QWORD *)(v8 + 23032), 157, a3);
    a3 = v65;
  }
  if ( a3 )
  {
    v10 = 2;
  }
  else
  {
    v10 = KfRaiseIrql(2u);
    a3 = v10 == 2;
    v65 = v10 == 2;
  }
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v50 = LockArray_high;
  v48 = v10;
  v12 = (_QWORD *)(*(_QWORD *)(v8 + 20264) + 192LL * LockArray_high);
  v13 = (v4[49] & 1) == 0;
  v14 = *(_QWORD *)(*(_QWORD *)(v7 + 104) + 8LL * LockArray_high);
  v62 = v14;
  v63 = (__int64)v12;
  if ( !v13 )
    goto LABEL_79;
  v15 = *((_QWORD *)qword_140224820 + LockArray_high);
  if ( *(_DWORD *)(v15 + 21508) == 3 )
  {
    v7 = a1;
LABEL_79:
    if ( !a3 )
      KeLowerIrql(v10);
    v41 = v6;
    if ( v6 )
    {
      v42 = v6;
      v43 = v6;
      do
      {
        v44 = v43[1];
        ++*(_QWORD *)(v14 + 48);
        ++*v12;
        *(_QWORD *)(v14 + 56) += *(unsigned int *)(v44 + 24);
        v12[1] += *(unsigned int *)(v44 + 24);
        v45 = HIDWORD(KeGetPcr()[1].LockArray);
        v46 = *(_QWORD *)(*(_QWORD *)(v7 + 104) + 8LL * v45);
        v47 = *(_QWORD *)(v8 + 20264) + 192LL * v45;
        ++*(_DWORD *)(v47 + 144);
        if ( v46 )
          ++*(_DWORD *)(v46 + 72);
        if ( SBYTE6(WPP_MAIN_CB.Reserved) < 0 || byte_140225C30 )
          IppLogPacketDiscard(
            *(unsigned __int16 *)(v8 + 28),
            256,
            0,
            0,
            10,
            1,
            1,
            v42,
            *(_QWORD *)(v7 + 8),
            3,
            -536854215);
        *((_DWORD *)v43 + 35) = -1073741285;
        v42 = (_QWORD *)*v41;
        v41 = v42;
        v43 = v42;
      }
      while ( v42 );
    }
    NetioDereferenceNetBufferListChain(v6, v65);
    return;
  }
  v66 = v5 & 1;
  v16 = *(int **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
  v17 = *v16;
  if ( *v16 )
  {
    if ( v17 == 1 )
    {
      ++v16[32];
    }
    else if ( v17 == 2 )
    {
      ++v16[28];
    }
  }
  else
  {
    if ( KeQueryDpcWatchdogInformation((PKDPC_WATCHDOG_INFORMATION)(v16 + 2)) )
    {
      *((_QWORD *)v16 + 1) = MEMORY[0xFFFFF78000000008];
      *v16 = 2;
      *((_OWORD *)v16 + 1) = 0;
      *((_OWORD *)v16 + 2) = 0;
      *((_OWORD *)v16 + 3) = 0;
      *((_OWORD *)v16 + 4) = 0;
      *((_OWORD *)v16 + 5) = 0;
      *((_OWORD *)v16 + 6) = 0;
    }
    else
    {
      *v16 = 1;
      *((_OWORD *)v16 + 2) = 0;
      *((_OWORD *)v16 + 3) = 0;
      *((_OWORD *)v16 + 4) = 0;
      *((_OWORD *)v16 + 5) = 0;
      *((_OWORD *)v16 + 6) = 0;
      *((_OWORD *)v16 + 7) = 0;
      v16[32] = 1;
    }
    v16[28] = 1;
  }
  ++*(_DWORD *)(v15 + 21508);
  while ( 2 )
  {
    v18 = v53;
    while ( 2 )
    {
      v19 = 0;
      *((_QWORD *)&v52 + 1) = &v52;
      *((_QWORD *)&v57 + 1) = &v57;
      *((_QWORD *)&v58 + 1) = &v58;
      *((_QWORD *)&v59 + 1) = &v59;
      *(_QWORD *)&v52 = 0;
      *(_QWORD *)&v57 = 0;
      *(_QWORD *)&v58 = 0;
      *(_QWORD *)&v59 = 0;
      v20 = v18[12];
      if ( !v20
        || *(_BYTE *)(v20 + 40)
        || (v49 = 1, !ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v20 + 16), 1u)) )
      {
        v49 = 0;
      }
      v51 = *(_DWORD *)(v15 + 21504);
      v21 = 64 - 32 / (1 << (*(_DWORD *)(v15 + 21508) - 1));
      v55 = v21;
      do
      {
        v22 = *(unsigned int *)(v15 + 21504);
        if ( (_DWORD)v22 == v21 )
          break;
        v23 = v15 + 336 * v22;
        *(_DWORD *)(v15 + 21504) = v22 + 1;
        memset((void *)v23, 0, 0x150u);
        v24 = v6;
        v61 = v6;
        v6 = (_QWORD *)*v6;
        *v24 = 0;
        v25 = v24[1];
        *(_QWORD *)(v23 + 224) = a1;
        v26 = *(_BYTE *)(v23 + 186) & 0x7F;
        *(_QWORD *)(v23 + 8) = v24;
        *(_QWORD *)(v23 + 200) = v56;
        *(_BYTE *)(v23 + 186) = v26 | (v66 << 7);
        v60 = v24[18];
        if ( !v66 )
        {
          v27 = v62;
          v28 = (_QWORD *)v63;
          ++*(_QWORD *)(v62 + 48);
          ++*v28;
          *(_QWORD *)(v27 + 56) += *(unsigned int *)(v25 + 24);
          v28[1] += *(unsigned int *)(v25 + 24);
        }
        if ( (*(int (__fastcall **)(__int64, __int64 *))(v8 + 88))(v23, &v60) >= 0 )
        {
          if ( !v49 || v66 )
          {
LABEL_36:
            if ( (_QWORD)v52
              && memcmp(
                   *(const void **)(v52 + 248),
                   *(const void **)(v23 + 248),
                   *(unsigned __int16 *)(*(_QWORD *)(v8 + 16) + 6LL)) )
            {
              IppDispatchReceivePacketHelper(v8, v56, v53, &v52, v19, &v57, &v58);
              v19 = 0;
              *(_QWORD *)&v52 = 0;
              *((_QWORD *)&v52 + 1) = &v52;
            }
            v31 = v54;
            v32 = *(_BYTE *)(v23 + 184);
            *(_BYTE *)(v23 + 16) ^= (*(_BYTE *)(v23 + 16) ^ v54) & 1;
            *(_BYTE *)(v23 + 184) = v32 ^ (v32 ^ (16 * v31)) & 0x10;
            ++v19;
            **((_QWORD **)&v52 + 1) = v23;
            *((_QWORD *)&v52 + 1) = v23;
            goto LABEL_40;
          }
          IppIndicatePacketsToIpsServiceChain(a1, (unsigned int)&v61, (_DWORD)v24, 0, 0, 0);
          v30 = v61;
          if ( v61 )
          {
            if ( v61 == *(_QWORD **)(v23 + 8) && !*v61 )
              goto LABEL_36;
            LOBYTE(v29) = 1;
            *(_QWORD *)(v23 + 8) = 0;
            IppCompleteAndFreePacketList(v23, v29);
            --*(_DWORD *)(v15 + 21504);
            IppReceivePackets(a1, v30, v65, 1);
          }
          else
          {
            LOBYTE(v29) = 1;
            *(_QWORD *)(v23 + 8) = 0;
            IppCompleteAndFreePacketList(v23, v29);
            --*(_DWORD *)(v15 + 21504);
          }
        }
        else
        {
          **((_QWORD **)&v59 + 1) = v23;
          *((_QWORD *)&v59 + 1) = v23;
        }
LABEL_40:
        v21 = v55;
      }
      while ( v6 );
      v18 = v53;
      if ( (_QWORD)v52 )
      {
        IppDispatchReceivePacketHelper(v8, v56, v53, &v52, v19, &v57, &v58);
        *(_QWORD *)&v52 = 0;
        *((_QWORD *)&v52 + 1) = &v52;
      }
      if ( (_QWORD)v57 )
        IppReceiveHeaderBatch(v8, &v57);
      if ( v49 )
        ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v18[12] + 16), 1u);
      v33 = v58;
      if ( (_QWORD)v58 )
        IppFragmentPackets(v8);
      if ( (_QWORD)v59 )
      {
        LOBYTE(v33) = 1;
        IppCompleteAndFreePacketList(v59, v33);
      }
      *(_DWORD *)(v15 + 21504) = v51;
      if ( v65 )
      {
        if ( !v6 )
          goto LABEL_70;
        continue;
      }
      break;
    }
    if ( v6 )
    {
      IppDequeueForwardInjectedPacketsAtDpc(v50);
      --*(_DWORD *)(v15 + 21508);
      v34 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      if ( *v34 == 1 )
      {
        v13 = v34[32]-- == 1;
        if ( !v13 )
          goto LABEL_59;
      }
      else
      {
        if ( *v34 != 2 )
          goto LABEL_59;
        v13 = v34[28]-- == 1;
        if ( !v13 )
          goto LABEL_59;
      }
      *v34 = 0;
LABEL_59:
      KeLowerIrql(v48);
      v48 = KfRaiseIrql(2u);
      v35 = *(int **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      v36 = *v35;
      if ( *v35 )
      {
        if ( v36 == 1 )
        {
          ++v35[32];
        }
        else if ( v36 == 2 )
        {
          ++v35[28];
        }
      }
      else
      {
        if ( KeQueryDpcWatchdogInformation((PKDPC_WATCHDOG_INFORMATION)(v35 + 2)) )
        {
          *((_QWORD *)v35 + 1) = MEMORY[0xFFFFF78000000008];
          *v35 = 2;
          *((_OWORD *)v35 + 1) = 0;
          *((_OWORD *)v35 + 2) = 0;
          *((_OWORD *)v35 + 3) = 0;
          *((_OWORD *)v35 + 4) = 0;
          *((_OWORD *)v35 + 5) = 0;
          *((_OWORD *)v35 + 6) = 0;
        }
        else
        {
          *v35 = 1;
          *((_OWORD *)v35 + 2) = 0;
          *((_OWORD *)v35 + 3) = 0;
          *((_OWORD *)v35 + 4) = 0;
          *((_OWORD *)v35 + 5) = 0;
          *((_OWORD *)v35 + 6) = 0;
          *((_OWORD *)v35 + 7) = 0;
          v35[32] = 1;
        }
        v35[28] = 1;
      }
      v37 = HIDWORD(KeGetPcr()[1].LockArray);
      v38 = v37;
      v50 = v37;
      v15 = *((_QWORD *)qword_140224820 + v37);
      ++*(_DWORD *)(v15 + 21508);
      v39 = *(_QWORD *)(a1 + 104);
      v63 = *(_QWORD *)(v8 + 20264) + 192 * v38;
      v62 = *(_QWORD *)(v39 + 8 * v38);
      continue;
    }
    break;
  }
LABEL_70:
  IppDequeueForwardInjectedPacketsAtDpc(v50);
  --*(_DWORD *)(v15 + 21508);
  v40 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
  if ( *v40 == 1 )
  {
    v13 = v40[32]-- == 1;
    if ( !v13 )
      goto LABEL_76;
  }
  else
  {
    if ( *v40 != 2 )
      goto LABEL_76;
    v13 = v40[28]-- == 1;
    if ( !v13 )
      goto LABEL_76;
  }
  *v40 = 0;
LABEL_76:
  if ( !v65 )
    KeLowerIrql(v48);
}

```

## disassembly

```asm
0x1400cffc0  mov     [rsp-8+arg_8], rbx
0x1400cffc5  mov     [rsp-8+arg_10], r8b
0x1400cffca  mov     [rsp-8+arg_0], rcx
0x1400cffcf  push    rbp
0x1400cffd0  push    rsi
0x1400cffd1  push    rdi
0x1400cffd2  push    r12
0x1400cffd4  push    r13
0x1400cffd6  push    r14
0x1400cffd8  push    r15
0x1400cffda  lea     rbp, [rsp-27h]
0x1400cffdf  sub     rsp, 0F0h
0x1400cffe6  mov     rbx, [rcx+8]
0x1400cffea  xorps   xmm0, xmm0
0x1400cffed  xorps   xmm1, xmm1
0x1400cfff0  mov     [rbp+57h+var_58], 0
0x1400cfff8  movups  [rbp+57h+var_B0], xmm0
0x1400cfffc  mov     edi, r9d
0x1400cffff  mov     r13, rdx
0x1400d0002  movups  [rbp+57h+var_88], xmm1
0x1400d0006  mov     rsi, rcx
0x1400d0009  mov     [rbp+57h+var_A0], rbx
0x1400d000d  movups  [rbp+57h+var_78], xmm0
0x1400d0011  movups  [rbp+57h+var_68], xmm1
0x1400d0015  mov     rax, [rbx]
0x1400d0018  mov     [rbp+57h+var_90], rax
0x1400d001c  mov     r15, [rax+28h]
0x1400d0020  mov     eax, r9d
0x1400d0023  shr     eax, 1
0x1400d0025  and     al, 1
0x1400d0027  cmp     byte ptr cs:WPP_MAIN_CB.DeviceExtension, 0
0x1400d002e  mov     [rbp+57h+var_98], eax
0x1400d0031  jz      short loc_1400D0062
0x1400d0033  xor     eax, eax
0x1400d0035  mov     r9d, 9Dh
0x1400d003b  test    r8b, r8b
0x1400d003e  mov     rcx, r13
0x1400d0041  mov     r8, [r15+59F8h]
0x1400d0048  setnz   al
0x1400d004b  xor     edx, edx
0x1400d004d  mov     [rsp+120h+var_100], eax
0x1400d0051  call    cs:__imp_NdisNblTrackerTransferOwnership
0x1400d0058  nop     dword ptr [rax+rax+00h]
0x1400d005d  movzx   r8d, [rbp+57h+arg_10]
0x1400d0062  test    r8b, r8b
0x1400d0065  jnz     short loc_1400D0084
0x1400d0067  mov     cl, 2; NewIrql
0x1400d0069  call    cs:__imp_KfRaiseIrql
0x1400d0070  nop     dword ptr [rax+rax+00h]
0x1400d0075  cmp     al, 2
0x1400d0077  movzx   edx, al
0x1400d007a  setz    r8b
0x1400d007e  mov     [rbp+57h+arg_10], r8b
0x1400d0082  jmp     short loc_1400D0086
0x1400d0084  mov     dl, 2
0x1400d0086  mov     eax, gs:1A4h
0x1400d008e  mov     ecx, eax
0x1400d0090  mov     [rbp+57h+var_BC], eax
0x1400d0093  mov     rax, [rsi+68h]
0x1400d0097  mov     [rbp+57h+var_C0], dl
0x1400d009a  lea     r14, [rcx+rcx*2]
0x1400d009e  shl     r14, 6
0x1400d00a2  add     r14, [r15+4F28h]
0x1400d00a9  test    byte ptr [rbx+188h], 1
0x1400d00b0  mov     r12, [rax+rcx*8]
0x1400d00b4  mov     [rbp+57h+var_48], r12
0x1400d00b8  mov     [rbp+57h+var_40], r14
0x1400d00bc  jnz     loc_1400D0718
0x1400d00c2  mov     rax, cs:qword_140224820
0x1400d00c9  mov     rsi, [rax+rcx*8]
0x1400d00cd  cmp     dword ptr [rsi+5404h], 3
0x1400d00d4  jz      loc_1400D0714
0x1400d00da  and     dil, 1
0x1400d00de  xor     ecx, ecx; ProcNumber
0x1400d00e0  mov     [rbp+57h+arg_18], edi
0x1400d00e3  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400d00ea  nop     dword ptr [rax+rax+00h]
0x1400d00ef  lea     ecx, [rax+rax*8]
0x1400d00f2  mov     rax, cs:gWfpPerProContext
0x1400d00f9  shl     ecx, 3
0x1400d00fc  mov     rbx, [rcx+rax]
0x1400d0100  mov     eax, [rbx]
0x1400d0102  test    eax, eax
0x1400d0104  jnz     loc_1400D018A
0x1400d010a  lea     rcx, [rbx+8]; WatchdogInformation
0x1400d010e  call    cs:__imp_KeQueryDpcWatchdogInformation
0x1400d0115  nop     dword ptr [rax+rax+00h]
0x1400d011a  xorps   xmm0, xmm0
0x1400d011d  xorps   xmm1, xmm1
0x1400d0120  test    eax, eax
0x1400d0122  jnz     short loc_1400D0155
0x1400d0124  mov     dword ptr [rbx], 1
0x1400d012a  movups  xmmword ptr [rbx+20h], xmm0
0x1400d012e  movups  xmmword ptr [rbx+30h], xmm0
0x1400d0132  movups  xmmword ptr [rbx+40h], xmm0
0x1400d0136  movups  xmmword ptr [rbx+50h], xmm1
0x1400d013a  movups  xmmword ptr [rbx+60h], xmm1
0x1400d013e  movups  xmmword ptr [rbx+70h], xmm1
0x1400d0142  mov     dword ptr [rbx+80h], 1
0x1400d014c  mov     dword ptr [rbx+70h], 1
0x1400d0153  jmp     short loc_1400D019F
0x1400d0155  mov     rax, ds:0FFFFF78000000008h
0x1400d015f  mov     [rbx+8], rax
0x1400d0163  mov     dword ptr [rbx], 2
0x1400d0169  movups  xmmword ptr [rbx+10h], xmm0
0x1400d016d  movups  xmmword ptr [rbx+20h], xmm0
0x1400d0171  movups  xmmword ptr [rbx+30h], xmm0
0x1400d0175  movups  xmmword ptr [rbx+40h], xmm1
0x1400d0179  movups  xmmword ptr [rbx+50h], xmm1
0x1400d017d  movups  xmmword ptr [rbx+60h], xmm1
0x1400d0181  mov     dword ptr [rbx+70h], 1
0x1400d0188  jmp     short loc_1400D019F
0x1400d018a  cmp     eax, 1
0x1400d018d  jnz     short loc_1400D0197
0x1400d018f  inc     dword ptr [rbx+80h]
0x1400d0195  jmp     short loc_1400D019F
0x1400d0197  cmp     eax, 2
0x1400d019a  jnz     short loc_1400D019F
0x1400d019c  inc     dword ptr [rbx+70h]
0x1400d019f  inc     dword ptr [rsi+5404h]
0x1400d01a5  mov     rbx, [rbp+57h+var_A0]
0x1400d01a9  nop     dword ptr [rax+00000000h]
0x1400d01b0  xor     r12d, r12d
0x1400d01b3  lea     rax, [rbp+57h+var_B0]
0x1400d01b7  mov     qword ptr [rbp+57h+var_B0+8], rax
0x1400d01bb  lea     rax, [rbp+57h+var_88]
0x1400d01bf  mov     qword ptr [rbp+57h+var_88+8], rax
0x1400d01c3  lea     rax, [rbp+57h+var_78]
0x1400d01c7  mov     qword ptr [rbp+57h+var_78+8], rax
0x1400d01cb  lea     rax, [rbp+57h+var_68]
0x1400d01cf  mov     qword ptr [rbp+57h+var_68+8], rax
0x1400d01d3  mov     qword ptr [rbp+57h+var_B0], r12
0x1400d01d7  mov     qword ptr [rbp+57h+var_88], r12
0x1400d01db  mov     qword ptr [rbp+57h+var_78], r12
0x1400d01df  mov     qword ptr [rbp+57h+var_68], r12
0x1400d01e3  mov     rcx, [rbx+60h]
0x1400d01e7  test    rcx, rcx
0x1400d01ea  jz      short loc_1400D0211
0x1400d01ec  movzx   eax, byte ptr [rcx+28h]
0x1400d01f0  test    al, al
0x1400d01f2  jnz     short loc_1400D0211
0x1400d01f4  mov     rcx, [rcx+10h]; RunRefCacheAware
0x1400d01f8  mov     edx, 1; Count
0x1400d01fd  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1400d0204  nop     dword ptr [rax+rax+00h]
0x1400d0209  mov     [rbp+57h+var_BF], 1
0x1400d020d  test    al, al
0x1400d020f  jnz     short loc_1400D0215
0x1400d0211  mov     [rbp+57h+var_BF], r12b
0x1400d0215  mov     ecx, [rsi+5404h]
0x1400d021b  mov     r8d, 1
0x1400d0221  mov     edi, [rsi+5400h]
0x1400d0227  dec     ecx
0x1400d0229  shl     r8d, cl
0x1400d022c  mov     eax, 20h ; ' '
0x1400d0231  cdq
0x1400d0232  mov     [rbp+57h+var_B8], edi
0x1400d0235  idiv    r8d
0x1400d0238  mov     ecx, 40h ; '@'
0x1400d023d  sub     ecx, eax
0x1400d023f  mov     [rbp+57h+var_94], ecx
0x1400d0242  mov     edx, [rsi+5400h]
0x1400d0248  cmp     edx, ecx
0x1400d024a  jz      loc_1400D0471
0x1400d0250  imul    rbx, rdx, 150h
0x1400d0257  lea     eax, [rdx+1]
0x1400d025a  mov     r8d, 150h; Size
0x1400d0260  add     rbx, rsi
0x1400d0263  mov     [rsi+5400h], eax
0x1400d0269  mov     rcx, rbx; void *
0x1400d026c  xor     edx, edx; Val
0x1400d026e  mov     rdi, r13
0x1400d0271  call    memset
0x1400d0276  mov     rax, [rbp+57h+arg_0]
0x1400d027a  mov     r14, r13
0x1400d027d  mov     r8d, [rbp+57h+arg_18]
0x1400d0281  movzx   ecx, r8b
0x1400d0285  shl     cl, 7
0x1400d0288  mov     [rbp+57h+var_50], r13
0x1400d028c  mov     r13, [r13+0]
0x1400d0290  mov     qword ptr [r14], 0
0x1400d0297  mov     rdx, [r14+8]
0x1400d029b  mov     [rbx+0E0h], rax
0x1400d02a2  movzx   eax, byte ptr [rbx+0BAh]
0x1400d02a9  and     al, 7Fh
0x1400d02ab  mov     [rbx+8], r14
0x1400d02af  or      cl, al
0x1400d02b1  mov     rax, [rbp+57h+var_90]
0x1400d02b5  mov     [rbx+0C8h], rax
0x1400d02bc  mov     [rbx+0BAh], cl
0x1400d02c2  mov     rax, [r14+90h]
0x1400d02c9  mov     [rbp+57h+var_58], rax
0x1400d02cd  test    r8b, r8b
0x1400d02d0  jnz     short loc_1400D030A
0x1400d02d2  mov     r9, [rbp+57h+var_48]
0x1400d02d6  mov     r8, [rbp+57h+var_40]
0x1400d02da  mov     rax, [r9+30h]
0x1400d02de  inc     rax
0x1400d02e1  mov     [r9+30h], rax
0x1400d02e5  mov     rax, [r8]
0x1400d02e8  inc     rax
0x1400d02eb  mov     [r8], rax
0x1400d02ee  mov     rax, [r9+38h]
0x1400d02f2  mov     ecx, [rdx+18h]
0x1400d02f5  add     rcx, rax
0x1400d02f8  mov     [r9+38h], rcx
0x1400d02fc  mov     ecx, [rdx+18h]
0x1400d02ff  mov     rax, [r8+8]
0x1400d0303  add     rcx, rax
0x1400d0306  mov     [r8+8], rcx
0x1400d030a  mov     rax, [r15+58h]
0x1400d030e  lea     rdx, [rbp+57h+var_58]
0x1400d0312  mov     rcx, rbx
0x1400d0315  call    _guard_dispatch_icall
0x1400d031a  test    eax, eax
0x1400d031c  jns     short loc_1400D032E
0x1400d031e  mov     rax, qword ptr [rbp+57h+var_68+8]
0x1400d0322  mov     [rax], rbx
0x1400d0325  mov     qword ptr [rbp+57h+var_68+8], rbx
0x1400d0329  jmp     loc_1400D0465
0x1400d032e  cmp     [rbp+57h+var_BF], 0
0x1400d0332  jz      loc_1400D03C6
0x1400d0338  cmp     byte ptr [rbp+57h+arg_18], 0
0x1400d033c  jnz     loc_1400D03C6
0x1400d0342  mov     r8, r14
0x1400d0345  mov     dword ptr [rsp+120h+var_F8], 0
0x1400d034d  mov     r14, [rbp+57h+arg_0]
0x1400d0351  lea     rdx, [rbp+57h+var_50]
0x1400d0355  mov     rcx, r14
0x1400d0358  mov     byte ptr [rsp+120h+var_100], 0
0x1400d035d  xor     r9d, r9d
0x1400d0360  call    IppIndicatePacketsToIpsServiceChain
0x1400d0365  mov     rdi, [rbp+57h+var_50]
0x1400d0369  test    rdi, rdi
0x1400d036c  jnz     short loc_1400D0387
0x1400d036e  mov     dl, 1
0x1400d0370  mov     [rbx+8], rdi
0x1400d0374  mov     rcx, rbx
0x1400d0377  call    IppCompleteAndFreePacketList
0x1400d037c  dec     dword ptr [rsi+5400h]
0x1400d0382  jmp     loc_1400D0465
0x1400d0387  cmp     rdi, [rbx+8]
0x1400d038b  jnz     short loc_1400D0393
0x1400d038d  cmp     qword ptr [rdi], 0
0x1400d0391  jz      short loc_1400D03C6
0x1400d0393  mov     dl, 1
0x1400d0395  mov     qword ptr [rbx+8], 0
0x1400d039d  mov     rcx, rbx
0x1400d03a0  call    IppCompleteAndFreePacketList
0x1400d03a5  movzx   r8d, [rbp+57h+arg_10]
0x1400d03aa  mov     r9d, 1
0x1400d03b0  dec     dword ptr [rsi+5400h]
0x1400d03b6  mov     rdx, rdi
0x1400d03b9  mov     rcx, r14
0x1400d03bc  call    IppReceivePackets
0x1400d03c1  jmp     loc_1400D0465
0x1400d03c6  mov     rcx, qword ptr [rbp+57h+var_B0]
0x1400d03ca  test    rcx, rcx
0x1400d03cd  jz      short loc_1400D0429
0x1400d03cf  mov     rax, [r15+10h]
0x1400d03d3  mov     rdx, [rbx+0F8h]; Buf2
0x1400d03da  mov     rcx, [rcx+0F8h]; Buf1
0x1400d03e1  movzx   r8d, word ptr [rax+6]; Size
0x1400d03e6  call    memcmp
0x1400d03eb  test    eax, eax
0x1400d03ed  jz      short loc_1400D0429
0x1400d03ef  mov     r8, [rbp+57h+var_A0]
0x1400d03f3  lea     rax, [rbp+57h+var_78]
0x1400d03f7  mov     rdx, [rbp+57h+var_90]
0x1400d03fb  lea     r9, [rbp+57h+var_B0]
0x1400d03ff  mov     [rsp+120h+var_F0], rax
0x1400d0404  mov     rcx, r15
0x1400d0407  lea     rax, [rbp+57h+var_88]
0x1400d040b  mov     [rsp+120h+var_F8], rax
0x1400d0410  mov     [rsp+120h+var_100], r12d
0x1400d0415  call    IppDispatchReceivePacketHelper
0x1400d041a  xor     r12d, r12d
0x1400d041d  lea     rax, [rbp+57h+var_B0]
0x1400d0421  mov     qword ptr [rbp+57h+var_B0], r12
0x1400d0425  mov     qword ptr [rbp+57h+var_B0+8], rax
0x1400d0429  movzx   eax, byte ptr [rbx+10h]
0x1400d042d  mov     edx, [rbp+57h+var_98]
0x1400d0430  movzx   ecx, dl
0x1400d0433  xor     cl, al
0x1400d0435  and     cl, 1
0x1400d0438  xor     cl, al
0x1400d043a  movzx   eax, byte ptr [rbx+0B8h]
0x1400d0441  mov     [rbx+10h], cl
0x1400d0444  movzx   ecx, dl
0x1400d0447  shl     cl, 4
0x1400d044a  xor     cl, al
0x1400d044c  and     cl, 10h
0x1400d044f  xor     cl, al
0x1400d0451  mov     [rbx+0B8h], cl
0x1400d0457  inc     r12d
0x1400d045a  mov     rax, qword ptr [rbp+57h+var_B0+8]
0x1400d045e  mov     [rax], rbx
0x1400d0461  mov     qword ptr [rbp+57h+var_B0+8], rbx
0x1400d0465  mov     ecx, [rbp+57h+var_94]
0x1400d0468  test    r13, r13
  ... truncated ...
```
