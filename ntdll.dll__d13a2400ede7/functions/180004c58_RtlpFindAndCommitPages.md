# RtlpFindAndCommitPages

- ea: `0x180004c58`
- end: `0x1800050e4`
- name: `RtlpFindAndCommitPages`
- size: `1164`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180004770`

## callees

- `0x180003980`
- `0x180004c58`
- `0x180007060`
- `0x1800070f0`
- `0x180007cb0`
- `0x18006f0d0`
- `0x180081540`
- `0x1800885e8`
- `0x180088960`
- `0x1800d7790`
- `0x1800e6cf0`
- `0x18010eedc`
- `0x18011d208`
- `0x18015ede0`
- `0x18016f020`

## pseudocode

```c
__int64 __fastcall RtlpFindAndCommitPages(unsigned __int64 a1, unsigned __int64 *a2)
{
  __int64 UCREntry; // rax
  __int64 v5; // rbp
  __int64 v6; // rdi
  __int64 v7; // rax
  unsigned __int64 v8; // rsi
  unsigned __int64 v9; // rdx
  int HeapProtection; // r15d
  int v11; // eax
  __int64 v13; // r15
  __int64 v14; // rcx
  __int64 v15; // rax
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // r9
  __int64 v19; // rdx
  unsigned __int64 v20; // rbp
  __int64 v21; // rcx
  __int64 v22; // rsi
  __int64 v23; // rcx
  __int64 v24; // [rsp+70h] [rbp+8h] BYREF

  v24 = 0;
  UCREntry = RtlpFindUCREntry(a1, *a2);
  v5 = UCREntry;
  if ( UCREntry == a1 + 240 )
    return 0;
  if ( RtlpHeapErrorHandlerThreshold >= 1 && *(_QWORD *)(UCREntry + 40) < *a2 )
  {
    if ( NtCurrentPeb()->Ldr )
      DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
    else
      DbgPrint("HEAP: ");
    DbgPrint("(UCRBlock->Size >= *Size)");
    RtlpHeapHandleError(1);
  }
  v6 = v5 - 16;
  v7 = *(unsigned __int8 *)(v5 - 16 + 14);
  if ( (_BYTE)v7 )
    v8 = (v6 & 0xFFFFFFFFFFFF0000uLL) - (v7 << 16) + 0x10000;
  else
    v8 = a1;
  v24 = *(_QWORD *)(v5 + 32);
  if ( RtlpHeapKey != *(_QWORD *)(a1 + 360) )
  {
    v11 = ((__int64 (__fastcall *)(unsigned __int64, __int64 *, unsigned __int64 *))(RtlpHeapKey ^ *(_QWORD *)(a1 + 360)))(
            a1,
            &v24,
            a2);
  }
  else
  {
    v9 = *(_QWORD *)(v5 + 40);
    if ( v9 - *a2 > 16LL * *(_QWORD *)(a1 + 176) || v9 >= 16 * (unsigned __int64)*(unsigned int *)(a1 + 148) )
      v9 = *a2;
    *a2 = (v9 + 4095) & 0xFFFFFFFFFFFFF000uLL;
    HeapProtection = RtlpGetHeapProtection(a1, 1);
    if ( (unsigned int)RtlpHpHeapCheckCommitLimit(*a2, *(_QWORD *)(a1 + 576) - *(_QWORD *)(a1 + 672), a1, a1 + 376) )
      v11 = ZwAllocateVirtualMemory(-1, &v24, 0, a2, 4096, HeapProtection);
    else
      v11 = -1073741523;
    ++*(_DWORD *)(a1 + 632);
  }
  if ( v11 < 0 )
  {
    ++*(_DWORD *)(a1 + 640);
    return 0;
  }
  v13 = 2147353472;
  if ( (unsigned int)RtlGetCurrentServiceSessionId() )
    v14 = (__int64)NtCurrentPeb()->SharedData + 550;
  else
    v14 = 2147353472;
  if ( *(_BYTE *)v14 && (NtCurrentPeb()->TracingFlags & 1) != 0 )
    RtlpLogHeapCommit(a1, v24, *a2, 2);
  if ( *(_DWORD *)(a1 + 124) )
  {
    *(_DWORD *)(v6 + 8) ^= *(_DWORD *)(a1 + 136);
    if ( *(_BYTE *)(v6 + 11) != (*(_BYTE *)(v6 + 8) ^ (unsigned __int8)(*(_BYTE *)(v6 + 9) ^ *(_BYTE *)(v6 + 10))) )
      RtlpAnalyzeHeapFailure(a1, v5 - 16);
  }
  *(_BYTE *)(v6 + 10) = 0;
  *(_BYTE *)(v6 + 15) = 0;
  RtlpRemoveUCRBlock(a1, v5);
  --*(_DWORD *)(v8 + 84);
  *(_DWORD *)(v8 + 80) -= *(_QWORD *)(v5 + 40) >> 12;
  v15 = *(_QWORD *)(v5 + 40) + *(_QWORD *)(a1 + 576);
  ++*(_DWORD *)(a1 + 616);
  --*(_DWORD *)(a1 + 612);
  *(_QWORD *)(a1 + 576) = v15;
  v16 = *(_QWORD *)(v5 + 40);
  if ( v16 >= 0xFF000 )
    *(_QWORD *)(a1 + 584) -= v16;
  v17 = *a2;
  v18 = *(_QWORD *)(v5 + 40);
  if ( v18 > *a2 || v18 + *(_QWORD *)(v5 + 32) == *(_QWORD *)(v8 + 72) )
  {
    RtlpCreateUCREntry(a1, v8, v17 - 48 + *(_QWORD *)(v5 + 32), v18 - v17, v5 - 16, (__int64)a2);
    *a2 *= 16LL;
  }
  else
  {
    *a2 = v17 + 16LL * *(unsigned __int16 *)(v6 + 8);
  }
  *(_BYTE *)(v6 + 11) = 0;
  v19 = *(_QWORD *)(v8 + 40);
  if ( v19 == v8 )
  {
    LOBYTE(v20) = 0;
  }
  else
  {
    v20 = ((v6 - v8) >> 16) + 1;
    if ( v20 >= 0xFE )
      RtlpLogHeapFailure(3, v19, v6, v8, 0, 0);
  }
  *(_BYTE *)(v6 + 14) = v20;
  if ( (unsigned int)RtlGetCurrentServiceSessionId() )
    v21 = (__int64)NtCurrentPeb()->SharedData + 550;
  else
    v21 = 2147353472;
  if ( *(_BYTE *)v21 && (NtCurrentPeb()->TracingFlags & 1) != 0 )
  {
    if ( (unsigned int)RtlGetCurrentServiceSessionId() )
      v13 = (__int64)NtCurrentPeb()->SharedData + 550;
    RtlpLogHeapExtendEvent(a1, v6, *a2, 16 * *(_QWORD *)(a1 + 192), *(unsigned __int8 *)v13);
  }
  v22 = 2147353482;
  if ( (unsigned int)RtlGetCurrentServiceSessionId() )
    v23 = (__int64)NtCurrentPeb()->SharedData + 560;
  else
    v23 = 2147353482;
  if ( *(_BYTE *)v23 )
  {
    if ( (unsigned int)RtlGetCurrentServiceSessionId() )
      v22 = (__int64)NtCurrentPeb()->SharedData + 560;
    RtlpLogHeapExtendEvent(a1, v6, *a2, 16 * *(_QWORD *)(a1 + 192), *(unsigned __int8 *)v22);
  }
  return v6;
}

```

## disassembly

```asm
0x180004c58  push    rbx
0x180004c5a  push    rbp
0x180004c5b  push    rsi
0x180004c5c  push    rdi
0x180004c5d  push    r14
0x180004c5f  push    r15
0x180004c61  sub     rsp, 38h
0x180004c65  mov     r14, rdx
0x180004c68  mov     [rsp+68h+arg_0], 0
0x180004c71  mov     rdx, [rdx]
0x180004c74  mov     rbx, rcx
0x180004c77  call    RtlpFindUCREntry
0x180004c7c  lea     r8, [rbx+0F0h]
0x180004c83  mov     rbp, rax
0x180004c86  cmp     rax, r8
0x180004c89  jz      loc_180004D66
0x180004c8f  cmp     cs:RtlpHeapErrorHandlerThreshold, 1
0x180004c96  jge     loc_180004F3E
0x180004c9c  lea     rdi, [rbp-10h]
0x180004ca0  movzx   eax, byte ptr [rdi+0Eh]
0x180004ca4  test    al, al
0x180004ca6  jnz     loc_180004D76
0x180004cac  mov     rsi, rbx
0x180004caf  mov     rax, [rbp+20h]
0x180004cb3  mov     [rsp+68h+arg_0], rax
0x180004cb8  mov     rax, [rbx+168h]
0x180004cbf  xor     rax, cs:RtlpHeapKey
0x180004cc6  jnz     loc_180004FA5
0x180004ccc  mov     rdx, [rbp+28h]
0x180004cd0  mov     rax, [rbx+0B0h]
0x180004cd7  mov     rcx, rdx
0x180004cda  sub     rcx, [r14]
0x180004cdd  shl     rax, 4
0x180004ce1  cmp     rcx, rax
0x180004ce4  jbe     loc_180004F26
0x180004cea  mov     rdx, [r14]
0x180004ced  lea     rax, [rdx+0FFFh]
0x180004cf4  mov     rcx, rbx
0x180004cf7  and     rax, 0FFFFFFFFFFFFF000h
0x180004cfd  mov     edx, 1
0x180004d02  mov     [r14], rax
0x180004d05  call    RtlpGetHeapProtection
0x180004d0a  mov     rdx, [rbx+240h]
0x180004d11  lea     r9, [rbx+178h]
0x180004d18  sub     rdx, [rbx+2A0h]
0x180004d1f  mov     r8, rbx
0x180004d22  mov     rcx, [r14]
0x180004d25  mov     r15d, eax
0x180004d28  call    RtlpHpHeapCheckCommitLimit
0x180004d2d  test    eax, eax
0x180004d2f  jz      loc_180004FBA
0x180004d35  mov     dword ptr [rsp+68h+var_40], r15d
0x180004d3a  lea     rdx, [rsp+68h+arg_0]
0x180004d3f  mov     r9, r14
0x180004d42  mov     dword ptr [rsp+68h+var_48], 1000h
0x180004d4a  xor     r8d, r8d
0x180004d4d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180004d51  call    ZwAllocateVirtualMemory
0x180004d56  inc     dword ptr [rbx+278h]
0x180004d5c  test    eax, eax
0x180004d5e  jns     short loc_180004D93
0x180004d60  inc     dword ptr [rbx+280h]
0x180004d66  xor     eax, eax
0x180004d68  add     rsp, 38h
0x180004d6c  pop     r15
0x180004d6e  pop     r14
0x180004d70  pop     rdi
0x180004d71  pop     rsi
0x180004d72  pop     rbp
0x180004d73  pop     rbx
0x180004d74  retn
0x180004d76  shl     rax, 10h
0x180004d7a  mov     rsi, rdi
0x180004d7d  and     rsi, 0FFFFFFFFFFFF0000h
0x180004d84  sub     rsi, rax
0x180004d87  add     rsi, 10000h
0x180004d8e  jmp     loc_180004CAF
0x180004d93  call    RtlGetCurrentServiceSessionId
0x180004d98  mov     r15d, 7FFE0380h
0x180004d9e  test    eax, eax
0x180004da0  jnz     loc_180004FC4
0x180004da6  mov     ecx, r15d
0x180004da9  cmp     byte ptr [rcx], 0
0x180004dac  jnz     loc_180004FE0
0x180004db2  cmp     dword ptr [rbx+7Ch], 0
0x180004db6  jz      short loc_180004DDA
0x180004db8  mov     eax, [rbx+88h]
0x180004dbe  xor     [rdi+8], eax
0x180004dc1  mov     al, [rdi+0Ah]
0x180004dc4  xor     al, [rdi+9]
0x180004dc7  xor     al, [rdi+8]
0x180004dca  cmp     [rdi+0Bh], al
0x180004dcd  jz      short loc_180004DDA
0x180004dcf  mov     rdx, rdi
0x180004dd2  mov     rcx, rbx
0x180004dd5  call    RtlpAnalyzeHeapFailure
0x180004dda  mov     rdx, rbp
0x180004ddd  mov     byte ptr [rdi+0Ah], 0
0x180004de1  mov     rcx, rbx
0x180004de4  mov     byte ptr [rdi+0Fh], 0
0x180004de8  call    RtlpRemoveUCRBlock
0x180004ded  or      ecx, 0FFFFFFFFh
0x180004df0  add     [rsi+54h], ecx
0x180004df3  mov     rax, [rbp+28h]
0x180004df7  shr     rax, 0Ch
0x180004dfb  sub     [rsi+50h], eax
0x180004dfe  mov     rax, [rbx+240h]
0x180004e05  add     rax, [rbp+28h]
0x180004e09  inc     dword ptr [rbx+268h]
0x180004e0f  add     [rbx+264h], ecx
0x180004e15  mov     [rbx+240h], rax
0x180004e1c  mov     rax, [rbp+28h]
0x180004e20  cmp     rax, 0FF000h
0x180004e26  jnb     loc_180004ED2
0x180004e2c  mov     rdx, [r14]
0x180004e2f  mov     r9, [rbp+28h]
0x180004e33  cmp     r9, rdx
0x180004e36  jbe     loc_180004F02
0x180004e3c  mov     r8, [rbp+20h]
0x180004e40  sub     r9, rdx
0x180004e43  add     rdx, 0FFFFFFFFFFFFFFD0h
0x180004e47  mov     [rsp+68h+var_40], r14
0x180004e4c  add     r8, rdx
0x180004e4f  mov     [rsp+68h+var_48], rdi
0x180004e54  mov     rdx, rsi
0x180004e57  mov     rcx, rbx
0x180004e5a  call    RtlpCreateUCREntry
0x180004e5f  shl     qword ptr [r14], 4
0x180004e63  mov     byte ptr [rdi+0Bh], 0
0x180004e67  mov     rdx, [rsi+28h]
0x180004e6b  cmp     rdx, rsi
0x180004e6e  jz      short loc_180004ECD
0x180004e70  mov     rbp, rdi
0x180004e73  sub     rbp, rsi
0x180004e76  shr     rbp, 10h
0x180004e7a  inc     rbp
0x180004e7d  cmp     rbp, 0FEh
0x180004e84  jnb     short loc_180004EDE
0x180004e86  mov     [rdi+0Eh], bpl
0x180004e8a  call    RtlGetCurrentServiceSessionId
0x180004e8f  test    eax, eax
0x180004e91  jnz     loc_180005011
0x180004e97  mov     rcx, r15
0x180004e9a  cmp     byte ptr [rcx], 0
0x180004e9d  jnz     loc_18000502D
0x180004ea3  call    RtlGetCurrentServiceSessionId
0x180004ea8  mov     esi, 7FFE038Ah
0x180004ead  mov     ebp, 230h
0x180004eb2  test    eax, eax
0x180004eb4  jnz     loc_18000508A
0x180004eba  mov     ecx, esi
0x180004ebc  cmp     byte ptr [rcx], 0
0x180004ebf  jnz     loc_1800050A2
0x180004ec5  mov     rax, rdi
0x180004ec8  jmp     loc_180004D68
0x180004ecd  xor     bpl, bpl
0x180004ed0  jmp     short loc_180004E86
0x180004ed2  sub     [rbx+248h], rax
0x180004ed9  jmp     loc_180004E2C
0x180004ede  mov     [rsp+68h+var_40], 0
0x180004ee7  mov     r9, rsi
0x180004eea  mov     r8, rdi
0x180004eed  mov     [rsp+68h+var_48], 0
0x180004ef6  mov     ecx, 3
0x180004efb  call    RtlpLogHeapFailure
0x180004f00  jmp     short loc_180004E86
0x180004f02  mov     rcx, [rbp+20h]
0x180004f06  add     rcx, r9
0x180004f09  cmp     rcx, [rsi+48h]
0x180004f0d  jz      loc_180004E3C
0x180004f13  movzx   eax, word ptr [rdi+8]
0x180004f17  shl     rax, 4
0x180004f1b  add     rax, rdx
0x180004f1e  mov     [r14], rax
0x180004f21  jmp     loc_180004E63
0x180004f26  mov     eax, [rbx+94h]
0x180004f2c  shl     rax, 4
0x180004f30  cmp     rdx, rax
0x180004f33  jb      loc_180004CED
0x180004f39  jmp     loc_180004CEA
0x180004f3e  mov     rcx, [r14]
0x180004f41  cmp     [rax+28h], rcx
0x180004f45  jnb     loc_180004C9C
0x180004f4b  mov     rcx, gs:60h
0x180004f54  cmp     qword ptr [rcx+18h], 0
0x180004f59  jz      short loc_180004F7E
0x180004f5b  mov     rax, gs:60h
0x180004f64  mov     rcx, [rax+18h]
0x180004f68  mov     rdx, [rcx+10h]
0x180004f6c  lea     rcx, aHeapWz; "HEAP[%wZ]: "
0x180004f73  add     rdx, 58h ; 'X'
0x180004f77  call    DbgPrint
0x180004f7c  jmp     short loc_180004F8A
0x180004f7e  lea     rcx, aHeap; "HEAP: "
0x180004f85  call    DbgPrint
0x180004f8a  lea     rcx, aUcrblockSizeSi; "(UCRBlock->Size >= *Size)"
0x180004f91  call    DbgPrint
0x180004f96  mov     ecx, 1
0x180004f9b  call    RtlpHeapHandleError
0x180004fa0  jmp     loc_180004C9C
0x180004fa5  mov     r8, r14
0x180004fa8  lea     rdx, [rsp+68h+arg_0]
0x180004fad  mov     rcx, rbx
0x180004fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fb5  jmp     loc_180004D5C
0x180004fba  mov     eax, 0C000012Dh
0x180004fbf  jmp     loc_180004D56
0x180004fc4  mov     rax, gs:60h
0x180004fcd  mov     rcx, [rax+90h]
0x180004fd4  add     rcx, 226h
0x180004fdb  jmp     loc_180004DA9
0x180004fe0  mov     rax, gs:60h
0x180004fe9  test    byte ptr [rax+378h], 1
0x180004ff0  jz      loc_180004DB2
0x180004ff6  mov     r8, [r14]
0x180004ff9  mov     r9d, 2
0x180004fff  mov     rdx, [rsp+68h+arg_0]
0x180005004  mov     rcx, rbx
0x180005007  call    RtlpLogHeapCommit
0x18000500c  jmp     loc_180004DB2
0x180005011  mov     rax, gs:60h
0x18000501a  mov     rcx, [rax+90h]
0x180005021  add     rcx, 226h
0x180005028  jmp     loc_180004E9A
0x18000502d  mov     rax, gs:60h
0x180005036  test    byte ptr [rax+378h], 1
0x18000503d  jz      loc_180004EA3
0x180005043  call    RtlGetCurrentServiceSessionId
0x180005048  test    eax, eax
0x18000504a  jz      short loc_180005063
0x18000504c  mov     rax, gs:60h
0x180005055  mov     r15, [rax+90h]
0x18000505c  add     r15, 226h
0x180005063  mov     r9, [rbx+0C0h]
0x18000506a  mov     rdx, rdi
0x18000506d  movzx   eax, byte ptr [r15]
0x180005071  mov     rcx, rbx
0x180005074  mov     r8, [r14]
0x180005077  shl     r9, 4
0x18000507b  mov     [rsp+68h+var_48], rax
0x180005080  call    RtlpLogHeapExtendEvent
0x180005085  jmp     loc_180004EA3
0x18000508a  mov     rax, gs:60h
0x180005093  mov     rcx, [rax+90h]
0x18000509a  add     rcx, rbp
0x18000509d  jmp     loc_180004EBC
0x1800050a2  call    RtlGetCurrentServiceSessionId
0x1800050a7  test    eax, eax
0x1800050a9  jz      short loc_1800050BE
0x1800050ab  mov     rax, gs:60h
0x1800050b4  mov     rsi, [rax+90h]
0x1800050bb  add     rsi, rbp
0x1800050be  movzx   ecx, byte ptr [rsi]
0x1800050c1  mov     rdx, rdi
0x1800050c4  mov     r9, [rbx+0C0h]
0x1800050cb  mov     r8, [r14]
0x1800050ce  mov     [rsp+68h+var_48], rcx
0x1800050d3  mov     rcx, rbx
0x1800050d6  shl     r9, 4
0x1800050da  call    RtlpLogHeapExtendEvent
0x1800050df  jmp     loc_180004EC5
```
