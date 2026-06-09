# RtlpDeCommitFreeBlock

- ea: `0x180008488`
- end: `0x18000905a`
- name: `RtlpDeCommitFreeBlock`
- size: `3026`
- prototype: ``
- caller_count: `8`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800050f0`
- `0x1800067f0`
- `0x1800075c0`
- `0x18003806c`
- `0x18003c328`
- `0x1800aba3c`
- `0x180100cb0`
- `0x18011c1a0`

## callees

- `0x180005f70`
- `0x1800067f0`
- `0x180007060`
- `0x180007cb0`
- `0x180007d00`
- `0x180008488`
- `0x1800526f0`
- `0x18006bb38`
- `0x18006bd20`
- `0x18007a840`
- `0x1800a0e50`
- `0x1800d34e0`
- `0x1800d8ab0`
- `0x1800e7298`
- `0x1801104ec`
- `0x18011c718`

## pseudocode

```c
struct _PEB *__fastcall RtlpDeCommitFreeBlock(unsigned __int64 a1, __int64 a2, unsigned __int64 a3, char a4)
{
  _PEB_LDR_DATA *v4; // r11
  bool v5; // zf
  unsigned __int64 v7; // rdi
  __int64 v8; // rsi
  unsigned __int64 v9; // rbx
  struct _PEB *result; // rax
  unsigned __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // r14
  unsigned __int64 v14; // rdi
  __int64 v15; // rax
  unsigned __int64 v16; // rsi
  __int64 v17; // r8
  char v18; // r13
  unsigned __int64 v19; // rdx
  __int64 v20; // rcx
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rcx
  __int64 v23; // r12
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  int CurrentServiceSessionId; // eax
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 v41; // rdi
  __int64 v42; // rcx
  _QWORD *v43; // rcx
  __int64 v44; // r10
  _PEB_LDR_DATA *v45; // r15
  int v46; // edx
  __int64 v47; // rcx
  unsigned __int64 v48; // rcx
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // r8
  __int64 v52; // r9
  __int64 v53; // r12
  __int64 v54; // rcx
  _BYTE *v55; // r15
  __int64 v56; // rdi
  unsigned __int64 Blink; // rax
  __int64 v58; // rdx
  unsigned __int64 v59; // rcx
  __int64 v60; // r8
  __int64 v61; // r9
  unsigned __int64 v62; // rax
  _BYTE *v63; // r15
  __int64 v64; // rdi
  __int64 v65; // rdx
  __int64 v66; // r8
  __int64 v67; // r9
  __int64 v68; // rcx
  __int64 v69; // r15
  __int64 v70; // rdx
  __int64 v71; // r8
  __int64 v72; // r9
  __int64 v73; // rdi
  __int64 v74; // rcx
  unsigned __int64 v75; // rdi
  bool v76; // cc
  __int64 v77; // rdx
  unsigned __int64 v78; // rdi
  __int64 v79; // r8
  __int64 v80; // r15
  __int64 v81; // rcx
  __int64 v82; // rax
  unsigned __int64 v83; // rax
  unsigned __int64 v84; // rdi
  __int64 v85; // rdx
  unsigned __int64 v86; // rdi
  __int64 v87; // r8
  int v88; // ecx
  unsigned __int64 v89; // [rsp+40h] [rbp-30h] BYREF
  __int64 v90; // [rsp+48h] [rbp-28h] BYREF
  _PEB_LDR_DATA *v91; // [rsp+50h] [rbp-20h] BYREF
  __int64 v92; // [rsp+58h] [rbp-18h] BYREF
  __int64 v93; // [rsp+60h] [rbp-10h]
  unsigned __int64 v94; // [rsp+B0h] [rbp+40h] BYREF
  unsigned __int64 v95; // [rsp+C0h] [rbp+50h] BYREF
  char v96; // [rsp+C8h] [rbp+58h]

  v96 = a4;
  v95 = a3;
  v4 = 0;
  v5 = RtlpHeapKey == *(_QWORD *)(a1 + 360);
  v7 = a3;
  v89 = 0;
  v8 = a2;
  v94 = 0;
  v9 = a1;
  v92 = 0;
  if ( !v5 )
    return (struct _PEB *)RtlpInsertFreeBlock(a1, a2, a3);
  if ( a4 )
  {
    v5 = (*(_BYTE *)(a2 + 10) & 8) == 0;
    v91 = 0;
    v90 = 0;
    if ( !v5 )
    {
      --*(_DWORD *)(a1 + 668);
      if ( (unsigned __int8)RtlpGetFreeBlockInsidePageBoundaries(a1, a2, &v90, &v91) )
        *(_QWORD *)(v9 + 672) -= v91;
    }
    v13 = v8;
  }
  else
  {
    if ( a3 < *(_QWORD *)(a1 + 176) )
      return (struct _PEB *)RtlpInsertFreeBlock(a1, a2, a3);
    v11 = a3 + *(_QWORD *)(a1 + 192);
    if ( v11 < *(_QWORD *)(a1 + 184) || v11 < *(_QWORD *)(a1 + 576) >> (*(_BYTE *)(a1 + 696) + 4) )
    {
      a2 = v8;
LABEL_9:
      a1 = v9;
      return (struct _PEB *)RtlpInsertFreeBlock(a1, a2, a3);
    }
    v12 = RtlpCoalesceFreeBlocks(a1, v8, &v95, 0);
    v7 = v95;
    v13 = v12;
    if ( v95 - 257 <= 0xFDFF )
    {
      RtlpInsertFreeBlock(v9, v12, v95);
      v14 = *(_QWORD *)(v9 + 576) - 16LL * *(_QWORD *)(v9 + 192);
      result = (struct _PEB *)(*(_QWORD *)(v9 + 680) >> 4);
      if ( v14 < *(_QWORD *)(v9 + 680) - (_QWORD)result )
      {
        result = (struct _PEB *)(*(_QWORD *)(v9 + 688) >> 2);
        if ( v14 > *(_QWORD *)(v9 + 688) - (_QWORD)result )
        {
          result = (struct _PEB *)RtlpCollectFreeBlocks(v9);
          *(_QWORD *)(v9 + 688) = v14;
          *(_QWORD *)(v9 + 680) = v14;
        }
      }
      return result;
    }
    v4 = 0;
  }
  v15 = *(unsigned __int8 *)(v8 + 14);
  if ( (_BYTE)v15 )
    v16 = (v8 & 0xFFFFFFFFFFFF0000uLL) - (v15 << 16) + 0x10000;
  else
    v16 = v9;
  v17 = 16 * v7;
  v93 = 16 * v7;
  if ( *(_BYTE *)(16 * v7 + v13 + 15) == 3 )
  {
    v80 = v17 + v13;
    RtlpRemoveUCRBlock(v9, v17 + v13 + 16);
    v91 = *(_PEB_LDR_DATA **)(v80 + 48);
    v81 = *(_QWORD *)(v80 + 56);
    --*(_DWORD *)(v16 + 84);
    *(_DWORD *)(v16 + 80) -= *(_QWORD *)(v80 + 56) >> 12;
    v82 = *(_QWORD *)(v9 + 576) + *(_QWORD *)(v80 + 56);
    --*(_DWORD *)(v9 + 612);
    *(_QWORD *)(v9 + 576) = v82;
    v83 = *(_QWORD *)(v80 + 56);
    v90 = v81;
    if ( v83 >= 0xFF000 )
      *(_QWORD *)(v9 + 584) -= v83;
    v17 = v93;
    v18 = 1;
    v7 += (*(_QWORD *)(v80 + 56) >> 4) + 64LL;
    v95 = v7;
    v4 = 0;
  }
  else
  {
    v91 = v4;
    v18 = (char)v4;
    v90 = (__int64)v4;
  }
  if ( *(_WORD *)(v9 + 140) != *(_WORD *)(v13 + 12) )
    goto LABEL_21;
  v89 = v13;
  v43 = *(_QWORD **)(v16 + 96);
  v44 = v13;
  while ( (_QWORD *)(v16 + 96) != v43 )
  {
    v45 = (_PEB_LDR_DATA *)(v43 - 2);
    if ( v43[2] + v43[3] == v13 )
      goto LABEL_46;
    v43 = (_QWORD *)*v43;
  }
  v45 = v4;
LABEL_46:
  if ( a4 && !v45 )
  {
LABEL_21:
    v19 = (v13 + 4159) & 0xFFFFFFFFFFFFF000uLL;
    v89 = v19;
    if ( v19 == v13 + 80 )
    {
      v19 += 4096LL;
      v89 = v19;
    }
    v20 = 16 * v7;
    if ( !v18 )
      v20 -= 32;
    v21 = (v13 + v20) & 0xFFFFFFFFFFFFF000uLL;
    if ( v21 < v19 )
    {
      if ( RtlpHeapErrorHandlerThreshold < 1 || !v18 )
        goto LABEL_101;
      if ( NtCurrentPeb()->Ldr == v4 )
        goto LABEL_147;
      goto LABEL_146;
    }
    v22 = v21 - v19;
    v23 = 2147353472;
    v94 = v22;
    if ( v96 != (_BYTE)v4 || *(_BYTE *)(v17 + v13 + 15) == 3 )
    {
      if ( !v22 )
        goto LABEL_32;
    }
    else if ( !v22 || v22 < *(_QWORD *)(v9 + 176) )
    {
      goto LABEL_101;
    }
    ++*(_DWORD *)(v9 + 620);
    if ( (int)RtlpSecMemFreeVirtualMemory(v22, &v89, &v94, 0x4000) < 0 )
      goto LABEL_119;
    CurrentServiceSessionId = RtlGetCurrentServiceSessionId(v25, v24, v26, v27);
    v4 = 0;
    if ( CurrentServiceSessionId )
      v29 = (__int64)NtCurrentPeb()->SharedData + 550;
    else
      v29 = 2147353472;
    if ( *(_BYTE *)v29 && (NtCurrentPeb()->TracingFlags & 1) != 0 )
    {
      RtlpLogHeapDecommit(v9, v89, v94, 6);
      v4 = 0;
    }
LABEL_32:
    if ( !v18 )
    {
      v55 = (_BYTE *)(v89 + v94);
      v56 = 16 * v7;
      *(_WORD *)(v89 + v94 + 12) = *(_WORD *)(v9 + 140);
      if ( v56 + v13 == v94 + v89 )
      {
        if ( *(_DWORD *)(v9 + 124) != (_DWORD)v4 )
        {
          v55[11] = v55[8] ^ v55[9] ^ v55[10];
          *((_DWORD *)v55 + 2) ^= *(_DWORD *)(v9 + 136);
        }
      }
      else
      {
        v55[15] = (_BYTE)v4;
        v55[10] = (_BYTE)v4;
        v84 = (v13 + v56 - v94 - v89) >> 4;
        v76 = RtlpHeapErrorHandlerThreshold < 1;
        *((_WORD *)v55 + 4) = v84;
        if ( !v76 && (unsigned __int16)v84 <= 1u )
        {
          if ( NtCurrentPeb()->Ldr == v4 )
            DbgPrint("HEAP: ");
          else
            DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
          DbgPrint("(LONG)FreeEntry->Size > 1");
          RtlpHeapHandleError(1);
          v4 = 0;
        }
        v55[11] = (_BYTE)v4;
        v85 = *(_QWORD *)(v16 + 40);
        if ( v85 == v16 )
        {
          LOBYTE(v86) = (_BYTE)v4;
        }
        else
        {
          v86 = ((unsigned __int64)&v55[-v16] >> 16) + 1;
          if ( v86 >= 0xFE )
            RtlpLogHeapFailure(3, v85, (_DWORD)v55, v16, (__int64)v4, (__int64)v4);
        }
        v87 = *((unsigned __int16 *)v55 + 4);
        v55[14] = v86;
        RtlpInsertFreeBlock(v9, v55, v87);
      }
    }
    RtlpCreateUCREntry(v9, v16, v89 - 48, v94, v13, (__int64)&v92);
    RtlpInsertFreeBlock(v9, v13, v92);
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v31, v30, v32, v33) )
      v37 = (__int64)NtCurrentPeb()->SharedData + 550;
    else
      v37 = 2147353472;
    if ( *(_BYTE *)v37 && (NtCurrentPeb()->TracingFlags & 1) != 0 )
    {
      if ( (unsigned int)RtlGetCurrentServiceSessionId(v37, v34, v35, v36) )
        v23 = (__int64)NtCurrentPeb()->SharedData + 550;
      RtlpLogHeapContractEvent(v9, v89, v94, 16 * *(_QWORD *)(v9 + 192), 0, 0, *(unsigned __int8 *)v23);
    }
    result = (struct _PEB *)RtlGetCurrentServiceSessionId(v37, v34, v35, v36);
    v41 = 2147353482;
    if ( (_DWORD)result )
    {
      result = NtCurrentPeb();
      v42 = (__int64)result->SharedData + 560;
    }
    else
    {
      v42 = 2147353482;
    }
    if ( *(_BYTE *)v42 )
    {
      if ( (unsigned int)RtlGetCurrentServiceSessionId(v42, v38, v39, v40) )
        v41 = (__int64)NtCurrentPeb()->SharedData + 560;
      return (struct _PEB *)RtlpLogHeapContractEvent(
                              v9,
                              v89,
                              v94,
                              16 * (unsigned int)*(_QWORD *)(v9 + 192),
                              0,
                              0,
                              *(unsigned __int8 *)v41);
    }
    return result;
  }
  v46 = RtlpHeapErrorHandlerThreshold;
  if ( RtlpHeapErrorHandlerThreshold >= 1 && !v45 )
  {
    if ( NtCurrentPeb()->Ldr == v4 )
      DbgPrint("HEAP: ");
    else
      DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
    DbgPrint("(UCRBlock != NULL)");
    RtlpHeapHandleError(1);
    v44 = v89;
    v4 = 0;
    v46 = RtlpHeapErrorHandlerThreshold;
  }
  v47 = 16 * v7;
  if ( !v18 )
    v47 -= 32;
  v48 = ((v13 + v47) & 0xFFFFFFFFFFFFF000uLL) - v44;
  v94 = v48;
  if ( !v48 )
  {
    if ( v46 < 1 || !v18 )
      goto LABEL_101;
    if ( NtCurrentPeb()->Ldr == v4 )
    {
LABEL_147:
      DbgPrint("HEAP: ");
      goto LABEL_148;
    }
LABEL_146:
    DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
LABEL_148:
    DbgPrint("(!TrailingUCR)");
    RtlpHeapHandleError(1);
LABEL_101:
    a3 = v7;
    a2 = v13;
    goto LABEL_9;
  }
  if ( (int)RtlpSecMemFreeVirtualMemory(v48, &v89, &v94, 0x4000) < 0 )
  {
LABEL_119:
    RtlpUpdateHeapRates(v9, 3);
    if ( v18 )
    {
      RtlpCreateUCREntry(v88, v16, (_DWORD)v91 - 48, v90, v13, (__int64)&v95);
      v7 = v95;
    }
    goto LABEL_101;
  }
  v53 = 2147353472;
  if ( (unsigned int)RtlGetCurrentServiceSessionId(v50, v49, v51, v52) )
    v54 = (__int64)NtCurrentPeb()->SharedData + 550;
  else
    v54 = 2147353472;
  if ( *(_BYTE *)v54 && (NtCurrentPeb()->TracingFlags & 1) != 0 )
    RtlpLogHeapDecommit(v9, v89, v94, 5);
  ++*(_DWORD *)(v9 + 620);
  Blink = (unsigned __int64)v45->InMemoryOrderModuleList.Blink;
  if ( Blink >= 0xFF000 )
    *(_QWORD *)(v9 + 584) -= Blink;
  RtlpRemoveUCRBlock(v9, v45);
  v45->InMemoryOrderModuleList.Blink = (_LIST_ENTRY *)((char *)v45->InMemoryOrderModuleList.Blink + v94);
  RtlpInsertUCRBlock(v9, v45);
  *(_DWORD *)(v16 + 80) += v94 >> 12;
  *(_QWORD *)(v9 + 576) -= v94;
  v62 = (unsigned __int64)v45->InMemoryOrderModuleList.Blink;
  if ( v62 >= 0xFF000 )
    *(_QWORD *)(v9 + 584) += v62;
  if ( !v18 )
  {
    v63 = (_BYTE *)(v89 + v94);
    v64 = 16 * v7;
    *(_WORD *)(v89 + v94 + 12) = *(_WORD *)(v9 + 140);
    v59 = v94 + v89;
    v58 = v64 + v13;
    if ( v64 + v13 == v94 + v89 )
    {
      if ( *(_DWORD *)(v9 + 124) )
      {
        v63[11] = v63[8] ^ v63[9] ^ v63[10];
        *((_DWORD *)v63 + 2) ^= *(_DWORD *)(v9 + 136);
      }
    }
    else
    {
      v63[15] = 0;
      v63[10] = 0;
      v75 = (v64 - v94) >> 4;
      v76 = RtlpHeapErrorHandlerThreshold < 1;
      *((_WORD *)v63 + 4) = v75;
      if ( !v76 && (unsigned __int16)v75 <= 1u )
      {
        if ( NtCurrentPeb()->Ldr )
          DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
        else
          DbgPrint("HEAP: ");
        DbgPrint("((LONG)FreeEntry->Size > 1)");
        RtlpHeapHandleError(1);
      }
      v63[11] = 0;
      v77 = *(_QWORD *)(v16 + 40);
      if ( v77 == v16 )
      {
        LOBYTE(v78) = 0;
      }
      else
      {
        v78 = ((unsigned __int64)&v63[-v16] >> 16) + 1;
        if ( v78 >= 0xFE )
          RtlpLogHeapFailure(3, v77, (_DWORD)v63, v16, 0, 0);
      }
      v79 = *((unsigned __int16 *)v63 + 4);
      v63[14] = v78;
      RtlpInsertFreeBlock(v9, v63, v79);
    }
  }
  if ( (unsigned int)RtlGetCurrentServiceSessionId(v59, v58, v60, v61) )
    v68 = (__int64)NtCurrentPeb()->SharedData + 550;
  else
    v68 = 2147353472;
  if ( *(_BYTE *)v68 && (NtCurrentPeb()->TracingFlags & 1) != 0 )
  {
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v68, v65, v66, v67) )
      v53 = (__int64)NtCurrentPeb()->SharedData + 550;
    v69 = v90;
    RtlpLogHeapContractEvent(v9, v89, v94, 16 * *(_QWORD *)(v9 + 192), v18, v90, *(unsigned __int8 *)v53);
  }
  else
  {
    v69 = v90;
  }
  result = (struct _PEB *)RtlGetCurrentServiceSessionId(v68, v65, v66, v67);
  v73 = 2147353482;
  if ( (_DWORD)result )
  {
    result = NtCurrentPeb();
    v74 = (__int64)result->SharedData + 560;
  }
  else
  {
    v74 = 2147353482;
  }
  if ( *(_BYTE *)v74 )
  {
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v74, v70, v71, v72) )
      v73 = (__int64)NtCurrentPeb()->SharedData + 560;
    return (struct _PEB *)RtlpLogHeapContractEvent(
                            v9,
                            v89,
                            v94,
                            16 * (unsigned int)*(_QWORD *)(v9 + 192),
                            v18,
                            v69,
                            *(unsigned __int8 *)v73);
  }
  return result;
}

```

## disassembly

```asm
0x180008488  mov     [rsp-38h+arg_8], rbx
0x18000848d  mov     [rsp-38h+arg_18], r9b
0x180008492  mov     [rsp-38h+arg_10], r8
0x180008497  push    rbp
0x180008498  push    rsi
0x180008499  push    rdi
0x18000849a  push    r12
0x18000849c  push    r13
0x18000849e  push    r14
0x1800084a0  push    r15
0x1800084a2  mov     rbp, rsp
0x1800084a5  sub     rsp, 70h
0x1800084a9  mov     rax, [rcx+168h]
0x1800084b0  xor     r11d, r11d
0x1800084b3  xor     rax, cs:RtlpHeapKey
0x1800084ba  mov     r12b, r9b
0x1800084bd  mov     rdi, r8
0x1800084c0  mov     [rbp+var_30], r11
0x1800084c4  mov     rsi, rdx
0x1800084c7  mov     [rbp+arg_0], r11
0x1800084cb  mov     rbx, rcx
0x1800084ce  mov     [rbp+var_18], r11
0x1800084d2  jz      short loc_1800084F2
0x1800084d4  call    RtlpInsertFreeBlock
0x1800084d9  mov     rbx, [rsp+70h+arg_8]
0x1800084e1  add     rsp, 70h
0x1800084e5  pop     r15
0x1800084e7  pop     r14
0x1800084e9  pop     r13
0x1800084eb  pop     r12
0x1800084ed  pop     rdi
0x1800084ee  pop     rsi
0x1800084ef  pop     rbp
0x1800084f0  retn
0x1800084f2  or      r13d, 0FFFFFFFFh
0x1800084f6  test    r12b, r12b
0x1800084f9  jnz     loc_1800085DA
0x1800084ff  cmp     r8, [rcx+0B0h]
0x180008506  jb      short loc_1800084D4
0x180008508  mov     rdx, [rcx+0C0h]
0x18000850f  add     rdx, r8
0x180008512  cmp     rdx, [rcx+0B8h]
0x180008519  jb      short loc_180008533
0x18000851b  mov     ecx, [rcx+2B8h]
0x180008521  mov     rax, [rbx+240h]
0x180008528  add     ecx, 4
0x18000852b  shr     rax, cl
0x18000852e  cmp     rdx, rax
0x180008531  jnb     short loc_18000853B
0x180008533  mov     rdx, rsi
0x180008536  mov     rcx, rbx
0x180008539  jmp     short loc_1800084D4
0x18000853b  xor     r9d, r9d
0x18000853e  lea     r8, [rbp+arg_10]
0x180008542  mov     rdx, rsi
0x180008545  mov     rcx, rbx
0x180008548  call    RtlpCoalesceFreeBlocks
0x18000854d  mov     rdi, [rbp+arg_10]
0x180008551  mov     r14, rax
0x180008554  lea     rcx, [rdi-101h]
0x18000855b  cmp     rcx, 0FDFFh
0x180008562  ja      loc_180008865
0x180008568  mov     r8, rdi
0x18000856b  mov     rdx, rax
0x18000856e  mov     rcx, rbx
0x180008571  call    RtlpInsertFreeBlock
0x180008576  mov     rcx, [rbx+2A8h]
0x18000857d  mov     rax, [rbx+0C0h]
0x180008584  mov     rdi, [rbx+240h]
0x18000858b  shl     rax, 4
0x18000858f  sub     rdi, rax
0x180008592  mov     rax, rcx
0x180008595  shr     rax, 4
0x180008599  sub     rcx, rax
0x18000859c  cmp     rdi, rcx
0x18000859f  jnb     loc_1800084D9
0x1800085a5  mov     rcx, [rbx+2B0h]
0x1800085ac  mov     rax, rcx
0x1800085af  shr     rax, 2
0x1800085b3  sub     rcx, rax
0x1800085b6  cmp     rdi, rcx
0x1800085b9  jbe     loc_1800084D9
0x1800085bf  mov     rcx, rbx
0x1800085c2  call    RtlpCollectFreeBlocks
0x1800085c7  mov     [rbx+2B0h], rdi
0x1800085ce  mov     [rbx+2A8h], rdi
0x1800085d5  jmp     loc_1800084D9
0x1800085da  test    byte ptr [rdx+0Ah], 8
0x1800085de  mov     [rbp+var_20], r11
0x1800085e2  mov     [rbp+var_28], r11
0x1800085e6  jnz     loc_180008C50
0x1800085ec  mov     r14, rsi
0x1800085ef  movzx   eax, byte ptr [rsi+0Eh]
0x1800085f3  test    al, al
0x1800085f5  jnz     loc_1800087B6
0x1800085fb  mov     rsi, rbx
0x1800085fe  mov     r8, rdi
0x180008601  shl     r8, 4
0x180008605  mov     [rbp+var_10], r8
0x180008609  cmp     byte ptr [r8+r14+0Fh], 3
0x18000860f  jz      loc_180008AD0
0x180008615  mov     [rbp+var_20], r11
0x180008619  mov     r13b, r11b
0x18000861c  mov     [rbp+var_28], r11
0x180008620  movzx   eax, word ptr [r14+0Ch]
0x180008625  cmp     [rbx+8Ch], ax
0x18000862c  jz      loc_1800087D0
0x180008632  lea     rdx, [r14+103Fh]
0x180008639  mov     r9, 0FFFFFFFFFFFFF000h
0x180008640  and     rdx, r9
0x180008643  lea     rax, [r14+50h]
0x180008647  mov     [rbp+var_30], rdx
0x18000864b  cmp     rdx, rax
0x18000864e  jz      loc_180008ED1
0x180008654  mov     rcx, rdi
0x180008657  shl     rcx, 4
0x18000865b  test    r13b, r13b
0x18000865e  jnz     short loc_180008664
0x180008660  add     rcx, 0FFFFFFFFFFFFFFE0h
0x180008664  add     rcx, r14
0x180008667  and     rcx, r9
0x18000866a  cmp     rcx, rdx
0x18000866d  jb      loc_180008BD9
0x180008673  sub     rcx, rdx
0x180008676  mov     r12d, 7FFE0380h
0x18000867c  mov     [rbp+arg_0], rcx
0x180008680  cmp     [rbp+arg_18], r11b
0x180008684  jz      loc_180008C30
0x18000868a  test    rcx, rcx
0x18000868d  jz      short loc_1800086E7
0x18000868f  mov     r15d, 1
0x180008695  lea     r8, [rbp+arg_0]
0x180008699  add     [rbx+26Ch], r15d
0x1800086a0  lea     rdx, [rbp+var_30]
0x1800086a4  mov     r9d, 4000h
0x1800086aa  call    RtlpSecMemFreeVirtualMemory
0x1800086af  test    eax, eax
0x1800086b1  js      loc_180008D77
0x1800086b7  call    RtlGetCurrentServiceSessionId
0x1800086bc  xor     r11d, r11d
0x1800086bf  test    eax, eax
0x1800086c1  jz      loc_18000886D
0x1800086c7  mov     rax, gs:60h
0x1800086d0  mov     rcx, [rax+90h]
0x1800086d7  add     rcx, 226h
0x1800086de  cmp     [rcx], r11b
0x1800086e1  jnz     loc_180008EE1
0x1800086e7  test    r13b, r13b
0x1800086ea  mov     r13d, 1
0x1800086f0  jz      loc_180008875
0x1800086f6  mov     r8, [rbp+var_30]
0x1800086fa  lea     rax, [rbp+var_18]
0x1800086fe  mov     r9, [rbp+arg_0]
0x180008702  add     r8, 0FFFFFFFFFFFFFFD0h
0x180008706  mov     [rsp+70h+var_48], rax
0x18000870b  mov     rdx, rsi
0x18000870e  mov     rcx, rbx
0x180008711  mov     [rsp+70h+var_50], r14
0x180008716  call    RtlpCreateUCREntry
0x18000871b  mov     r8, [rbp+var_18]
0x18000871f  mov     rdx, r14
0x180008722  mov     rcx, rbx
0x180008725  call    RtlpInsertFreeBlock
0x18000872a  call    RtlGetCurrentServiceSessionId
0x18000872f  xor     r14d, r14d
0x180008732  test    eax, eax
0x180008734  jnz     loc_1800088CB
0x18000873a  mov     rcx, r12
0x18000873d  cmp     [rcx], r14b
0x180008740  jnz     loc_180008F79
0x180008746  call    RtlGetCurrentServiceSessionId
0x18000874b  mov     edi, 7FFE038Ah
0x180008750  mov     esi, 230h
0x180008755  test    eax, eax
0x180008757  jnz     loc_180008FE3
0x18000875d  mov     ecx, edi
0x18000875f  cmp     [rcx], r14b
0x180008762  jz      loc_1800084D9
0x180008768  call    RtlGetCurrentServiceSessionId
0x18000876d  test    eax, eax
0x18000876f  jz      short loc_180008784
0x180008771  mov     rax, gs:60h
0x18000877a  mov     rdi, [rax+90h]
0x180008781  add     rdi, rsi
0x180008784  movzx   eax, byte ptr [rdi]
0x180008787  mov     [rsp+70h+var_40], rax
0x18000878c  mov     [rsp+70h+var_48], r14
0x180008791  mov     byte ptr [rsp+70h+var_50], r14b
0x180008796  mov     r9, [rbx+0C0h]
0x18000879d  mov     rcx, rbx
0x1800087a0  mov     r8, [rbp+arg_0]
0x1800087a4  mov     rdx, [rbp+var_30]
0x1800087a8  shl     r9, 4
0x1800087ac  call    RtlpLogHeapContractEvent
0x1800087b1  jmp     loc_1800084D9
0x1800087b6  shl     rax, 10h
0x1800087ba  and     rsi, 0FFFFFFFFFFFF0000h
0x1800087c1  sub     rsi, rax
0x1800087c4  add     rsi, 10000h
0x1800087cb  jmp     loc_1800085FE
0x1800087d0  lea     rdx, [rsi+60h]
0x1800087d4  mov     [rbp+var_30], r14
0x1800087d8  mov     rcx, [rdx]
0x1800087db  mov     r10, r14
0x1800087de  cmp     rdx, rcx
0x1800087e1  jnz     loc_180008B4A
0x1800087e7  mov     r15, r11
0x1800087ea  test    r12b, r12b
0x1800087ed  jnz     loc_180008C8F
0x1800087f3  mov     edx, cs:RtlpHeapErrorHandlerThreshold
0x1800087f9  mov     r12d, 1
0x1800087ff  cmp     edx, r12d
0x180008802  jge     loc_180008C9D
0x180008808  mov     rcx, rdi
0x18000880b  shl     rcx, 4
0x18000880f  test    r13b, r13b
0x180008812  jz      loc_180008D0A
0x180008818  add     rcx, r14
0x18000881b  and     rcx, 0FFFFFFFFFFFFF000h
0x180008822  sub     rcx, r10
0x180008825  mov     [rbp+arg_0], rcx
0x180008829  jz      loc_180008D13
0x18000882f  mov     r9d, 4000h
0x180008835  lea     r8, [rbp+arg_0]
0x180008839  lea     rdx, [rbp+var_30]
0x18000883d  call    RtlpSecMemFreeVirtualMemory
0x180008842  test    eax, eax
0x180008844  js      loc_180008D77
0x18000884a  call    RtlGetCurrentServiceSessionId
0x18000884f  mov     r12d, 7FFE0380h
0x180008855  test    eax, eax
0x180008857  jnz     loc_1800088E7
0x18000885d  mov     ecx, r12d
0x180008860  jmp     loc_1800088FE
0x180008865  xor     r11d, r11d
0x180008868  jmp     loc_1800085EF
0x18000886d  mov     rcx, r12
0x180008870  jmp     loc_1800086DE
0x180008875  mov     r15, [rbp+arg_0]
0x180008879  add     r15, [rbp+var_30]
0x18000887d  movzx   eax, word ptr [rbx+8Ch]
0x180008884  shl     rdi, 4
0x180008888  mov     [r15+0Ch], ax
0x18000888d  mov     rcx, [rbp+var_30]
0x180008891  add     rcx, [rbp+arg_0]
0x180008895  lea     rdx, [rdi+r14]
0x180008899  cmp     rdx, rcx
0x18000889c  jnz     loc_180008B67
0x1800088a2  cmp     [rbx+7Ch], r11d
0x1800088a6  jz      loc_1800086F6
0x1800088ac  mov     al, [r15+0Ah]
0x1800088b0  xor     al, [r15+9]
0x1800088b4  xor     al, [r15+8]
0x1800088b8  mov     [r15+0Bh], al
0x1800088bc  mov     eax, [rbx+88h]
0x1800088c2  xor     [r15+8], eax
0x1800088c6  jmp     loc_1800086F6
0x1800088cb  mov     rax, gs:60h
0x1800088d4  mov     rcx, [rax+90h]
0x1800088db  add     rcx, 226h
0x1800088e2  jmp     loc_18000873D
0x1800088e7  mov     rax, gs:60h
0x1800088f0  mov     rcx, [rax+90h]
0x1800088f7  add     rcx, 226h
0x1800088fe  cmp     byte ptr [rcx], 0
0x180008901  jnz     loc_180008DB8
0x180008907  inc     dword ptr [rbx+26Ch]
0x18000890d  mov     rax, [r15+28h]
0x180008911  cmp     rax, 0FF000h
0x180008917  jnb     loc_180008DE9
0x18000891d  mov     rdx, r15
0x180008920  mov     rcx, rbx
0x180008923  call    RtlpRemoveUCRBlock
0x180008928  mov     rax, [rbp+arg_0]
0x18000892c  mov     rdx, r15
0x18000892f  add     [r15+28h], rax
0x180008933  mov     rcx, rbx
0x180008936  call    RtlpInsertUCRBlock
0x18000893b  mov     rax, [rbp+arg_0]
0x18000893f  shr     rax, 0Ch
0x180008943  add     [rsi+50h], eax
0x180008946  mov     rax, [rbx+240h]
0x18000894d  sub     rax, [rbp+arg_0]
0x180008951  mov     [rbx+240h], rax
0x180008958  mov     rax, [r15+28h]
0x18000895c  cmp     rax, 0FF000h
0x180008962  jnb     loc_180008DF5
0x180008968  test    r13b, r13b
0x18000896b  jnz     loc_180008AC8
0x180008971  mov     r15, [rbp+arg_0]
0x180008975  add     r15, [rbp+var_30]
0x180008979  movzx   eax, word ptr [rbx+8Ch]
0x180008980  shl     rdi, 4
0x180008984  mov     [r15+0Ch], ax
0x180008989  mov     rcx, [rbp+var_30]
0x18000898d  add     rcx, [rbp+arg_0]
0x180008991  lea     rdx, [rdi+r14]
0x180008995  xor     r14d, r14d
0x180008998  cmp     rdx, rcx
0x18000899b  jnz     loc_180008A5E
  ... truncated ...
```
