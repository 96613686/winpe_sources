# RtlpCommitBlock

- ea: `0x180008124`
- end: `0x180008480`
- name: `RtlpCommitBlock`
- size: `860`
- prototype: ``
- caller_count: `7`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800050f0`
- `0x1800067f0`
- `0x1800075c0`
- `0x18003c328`
- `0x1800aba3c`
- `0x180100cb0`
- `0x18011c1a0`

## callees

- `0x180003980`
- `0x180007060`
- `0x180008124`
- `0x1800526f0`
- `0x180064b60`
- `0x1800e6970`
- `0x18010db8c`
- `0x18015e5d0`

## pseudocode

```c
char __fastcall RtlpCommitBlock(__int64 a1, __int64 a2)
{
  char *v4; // rcx
  unsigned __int64 v5; // r10
  unsigned __int64 v6; // rax
  int HeapProtection; // eax
  int v8; // ebx
  __int64 v9; // rbx
  __int64 v10; // rcx
  unsigned __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rbx
  __int64 v14; // rcx
  unsigned __int64 v16; // rdx
  char *v17; // r8
  unsigned __int64 v18; // [rsp+50h] [rbp+20h] BYREF
  char *v19; // [rsp+58h] [rbp+28h] BYREF

  v18 = 0;
  v4 = (char *)((a2 + 4159) & 0xFFFFFFFFFFFFF000uLL);
  v19 = v4;
  if ( v4 == (char *)(a2 + 80) )
  {
    v4 += 4096;
    v19 = v4;
  }
  v5 = 0;
  v6 = (a2 + 16 * (*(unsigned __int16 *)(a2 + 8) - 2LL)) & 0xFFFFFFFFFFFFF000uLL;
  if ( v6 > (unsigned __int64)v4 )
  {
    v5 = v6 - (_QWORD)v4;
    v18 = v6 - (_QWORD)v4;
  }
  if ( (unsigned int)RtlpHpHeapCheckCommitLimit(v5, *(_QWORD *)(a1 + 576) - *(_QWORD *)(a1 + 672), a1, a1 + 376) )
  {
    HeapProtection = RtlpGetHeapProtection(a1, 1);
    v8 = ZwAllocateVirtualMemory(-1, &v19, 0, &v18, 4096, HeapProtection);
    if ( v8 >= 0 )
    {
      v9 = 2147353472;
      if ( (unsigned int)RtlGetCurrentServiceSessionId() )
        v10 = (__int64)NtCurrentPeb()->SharedData + 550;
      else
        v10 = 2147353472;
      if ( *(_BYTE *)v10 && (NtCurrentPeb()->TracingFlags & 1) != 0 )
        RtlpLogHeapCommit(a1, v19, v18, 8);
      v11 = *(_QWORD *)(a1 + 672) - v18;
      --*(_DWORD *)(a1 + 668);
      *(_QWORD *)(a1 + 672) = v11;
      if ( (unsigned int)RtlGetCurrentServiceSessionId() )
        v12 = (__int64)NtCurrentPeb()->SharedData + 550;
      else
        v12 = 2147353472;
      if ( *(_BYTE *)v12 && (NtCurrentPeb()->TracingFlags & 1) != 0 )
      {
        if ( (unsigned int)RtlGetCurrentServiceSessionId() )
          v9 = (__int64)NtCurrentPeb()->SharedData + 550;
        RtlpLogHeapExtendEvent(a1, (_DWORD)v19, v18, 16 * *(_QWORD *)(a1 + 192), *(unsigned __int8 *)v9);
      }
      v13 = 2147353482;
      if ( (unsigned int)RtlGetCurrentServiceSessionId() )
        v14 = (__int64)NtCurrentPeb()->SharedData + 560;
      else
        v14 = 2147353482;
      if ( *(_BYTE *)v14 )
      {
        if ( (unsigned int)RtlGetCurrentServiceSessionId() )
          v13 = (__int64)NtCurrentPeb()->SharedData + 560;
        RtlpLogHeapExtendEvent(a1, (_DWORD)v19, v18, 16 * *(_QWORD *)(a1 + 192), *(unsigned __int8 *)v13);
      }
      ++*(_DWORD *)(a1 + 632);
      if ( (*(_BYTE *)(a2 + 10) & 4) == 0 )
        goto LABEL_17;
      v16 = v18 >> 2;
      if ( !(v18 >> 2) )
        goto LABEL_17;
      v17 = v19;
      if ( ((unsigned __int8)v19 & 4) != 0 )
      {
        *(_DWORD *)v19 = -17891602;
        if ( !--v16 )
        {
LABEL_17:
          *(_BYTE *)(a2 + 10) &= 0x17u;
          return 1;
        }
        v17 += 4;
      }
      memset64(v17, 0xFEEEFEEEFEEEFEEEuLL, v16 >> 1);
      if ( (v16 & 1) != 0 )
        *(_DWORD *)&v17[4 * v16 - 4] = -17891602;
      goto LABEL_17;
    }
  }
  else
  {
    v8 = -1073741523;
  }
  ++*(_DWORD *)(a1 + 644);
  if ( NtCurrentPeb()->Ldr )
    DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
  else
    DbgPrint("HEAP: ");
  DbgPrint("ZwAllocateVirtualMemory failed %lx for heap %p (base %p, size %Ix)\n", v8, (const void *)a1, v19, v18);
  return 0;
}

```

## disassembly

```asm
0x180008124  mov     [rsp-18h+arg_10], rbx
0x180008129  mov     [rsp-18h+arg_18], rsi
0x18000812e  push    rbp
0x18000812f  push    rdi
0x180008130  push    r12
0x180008132  mov     rbp, rsp
0x180008135  sub     rsp, 30h
0x180008139  mov     rsi, rdx
0x18000813c  mov     [rbp+arg_0], 0
0x180008144  mov     rdi, rcx
0x180008147  lea     rcx, [rdx+103Fh]
0x18000814e  mov     rdx, 0FFFFFFFFFFFFF000h
0x180008155  and     rcx, rdx
0x180008158  lea     rax, [rsi+50h]
0x18000815c  mov     [rbp+arg_8], rcx
0x180008160  cmp     rcx, rax
0x180008163  jnz     short loc_180008170
0x180008165  add     rcx, 1000h
0x18000816c  mov     [rbp+arg_8], rcx
0x180008170  movzx   eax, word ptr [rsi+8]
0x180008174  xor     r10d, r10d
0x180008177  sub     rax, 2
0x18000817b  shl     rax, 4
0x18000817f  add     rax, rsi
0x180008182  and     rax, rdx
0x180008185  cmp     rax, rcx
0x180008188  jbe     short loc_180008194
0x18000818a  mov     r10, rax
0x18000818d  sub     r10, rcx
0x180008190  mov     [rbp+arg_0], r10
0x180008194  mov     rdx, [rdi+240h]
0x18000819b  lea     r9, [rdi+178h]
0x1800081a2  sub     rdx, [rdi+2A0h]
0x1800081a9  mov     r8, rdi
0x1800081ac  mov     rcx, r10
0x1800081af  call    RtlpHpHeapCheckCommitLimit
0x1800081b4  test    eax, eax
0x1800081b6  jz      loc_180008349
0x1800081bc  mov     edx, 1
0x1800081c1  mov     rcx, rdi
0x1800081c4  call    RtlpGetHeapProtection
0x1800081c9  mov     [rsp+30h+var_8], eax
0x1800081cd  lea     r9, [rbp+arg_0]
0x1800081d1  xor     r8d, r8d
0x1800081d4  mov     dword ptr [rsp+30h+var_10], 1000h
0x1800081dc  lea     rdx, [rbp+arg_8]
0x1800081e0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800081e4  call    ZwAllocateVirtualMemory
0x1800081e9  mov     ebx, eax
0x1800081eb  test    eax, eax
0x1800081ed  js      loc_180008294
0x1800081f3  call    RtlGetCurrentServiceSessionId
0x1800081f8  mov     ebx, 7FFE0380h
0x1800081fd  mov     r12d, 226h
0x180008203  test    eax, eax
0x180008205  jnz     loc_180008353
0x18000820b  mov     ecx, ebx
0x18000820d  cmp     byte ptr [rcx], 0
0x180008210  jnz     loc_18000836B
0x180008216  mov     rax, [rdi+2A0h]
0x18000821d  sub     rax, [rbp+arg_0]
0x180008221  dec     dword ptr [rdi+29Ch]
0x180008227  mov     [rdi+2A0h], rax
0x18000822e  call    RtlGetCurrentServiceSessionId
0x180008233  test    eax, eax
0x180008235  jnz     loc_18000839C
0x18000823b  mov     rcx, rbx
0x18000823e  cmp     byte ptr [rcx], 0
0x180008241  jnz     loc_1800083B4
0x180008247  call    RtlGetCurrentServiceSessionId
0x18000824c  mov     ebx, 7FFE038Ah
0x180008251  mov     r12d, 230h
0x180008257  test    eax, eax
0x180008259  jnz     loc_18000840E
0x18000825f  mov     ecx, ebx
0x180008261  cmp     byte ptr [rcx], 0
0x180008264  jnz     loc_180008426
0x18000826a  inc     dword ptr [rdi+278h]
0x180008270  test    byte ptr [rsi+0Ah], 4
0x180008274  jnz     loc_1800082FB
0x18000827a  and     byte ptr [rsi+0Ah], 17h
0x18000827e  mov     al, 1
0x180008280  mov     rbx, [rsp+30h+arg_10]
0x180008285  mov     rsi, [rsp+30h+arg_18]
0x18000828a  add     rsp, 30h
0x18000828e  pop     r12
0x180008290  pop     rdi
0x180008291  pop     rbp
0x180008292  retn
0x180008294  inc     dword ptr [rdi+284h]
0x18000829a  mov     rax, gs:60h
0x1800082a3  cmp     qword ptr [rax+18h], 0
0x1800082a8  jz      short loc_1800082ED
0x1800082aa  mov     rax, gs:60h
0x1800082b3  mov     rcx, [rax+18h]
0x1800082b7  mov     rdx, [rcx+10h]
0x1800082bb  lea     rcx, aHeapWz; "HEAP[%wZ]: "
0x1800082c2  add     rdx, 58h ; 'X'
0x1800082c6  call    DbgPrint
0x1800082cb  mov     rax, [rbp+arg_0]
0x1800082cf  lea     rcx, aZwallocatevirt_1; "ZwAllocateVirtualMemory failed %lx for "...
0x1800082d6  mov     r9, [rbp+arg_8]
0x1800082da  mov     r8, rdi
0x1800082dd  mov     edx, ebx
0x1800082df  mov     [rsp+30h+var_10], rax
0x1800082e4  call    DbgPrint
0x1800082e9  xor     al, al
0x1800082eb  jmp     short loc_180008280
0x1800082ed  lea     rcx, aHeap; "HEAP: "
0x1800082f4  call    DbgPrint
0x1800082f9  jmp     short loc_1800082CB
0x1800082fb  mov     rdx, [rbp+arg_0]
0x1800082ff  shr     rdx, 2
0x180008303  test    rdx, rdx
0x180008306  jz      loc_18000827A
0x18000830c  mov     r8, [rbp+arg_8]
0x180008310  mov     r9d, 0FEEEFEEEh
0x180008316  test    r8b, 4
0x18000831a  jnz     loc_18000846A
0x180008320  mov     rcx, rdx
0x180008323  mov     rax, 0FEEEFEEEFEEEFEEEh
0x18000832d  shr     rcx, 1
0x180008330  mov     rdi, r8
0x180008333  rep stosq
0x180008336  test    dl, 1
0x180008339  jz      loc_18000827A
0x18000833f  mov     [r8+rdx*4-4], r9d
0x180008344  jmp     loc_18000827A
0x180008349  mov     ebx, 0C000012Dh
0x18000834e  jmp     loc_180008294
0x180008353  mov     rax, gs:60h
0x18000835c  mov     rcx, [rax+90h]
0x180008363  add     rcx, r12
0x180008366  jmp     loc_18000820D
0x18000836b  mov     rax, gs:60h
0x180008374  test    byte ptr [rax+378h], 1
0x18000837b  jz      loc_180008216
0x180008381  mov     r8, [rbp+arg_0]
0x180008385  mov     r9d, 8
0x18000838b  mov     rdx, [rbp+arg_8]
0x18000838f  mov     rcx, rdi
0x180008392  call    RtlpLogHeapCommit
0x180008397  jmp     loc_180008216
0x18000839c  mov     rax, gs:60h
0x1800083a5  mov     rcx, [rax+90h]
0x1800083ac  add     rcx, r12
0x1800083af  jmp     loc_18000823E
0x1800083b4  mov     rax, gs:60h
0x1800083bd  test    byte ptr [rax+378h], 1
0x1800083c4  jz      loc_180008247
0x1800083ca  call    RtlGetCurrentServiceSessionId
0x1800083cf  test    eax, eax
0x1800083d1  jz      short loc_1800083E6
0x1800083d3  mov     rax, gs:60h
0x1800083dc  mov     rbx, [rax+90h]
0x1800083e3  add     rbx, r12
0x1800083e6  mov     r9, [rdi+0C0h]
0x1800083ed  mov     rcx, rdi
0x1800083f0  movzx   eax, byte ptr [rbx]
0x1800083f3  mov     r8, [rbp+arg_0]
0x1800083f7  mov     rdx, [rbp+arg_8]
0x1800083fb  shl     r9, 4
0x1800083ff  mov     [rsp+30h+var_10], rax
0x180008404  call    RtlpLogHeapExtendEvent
0x180008409  jmp     loc_180008247
0x18000840e  mov     rax, gs:60h
0x180008417  mov     rcx, [rax+90h]
0x18000841e  add     rcx, r12
0x180008421  jmp     loc_180008261
0x180008426  call    RtlGetCurrentServiceSessionId
0x18000842b  test    eax, eax
0x18000842d  jz      short loc_180008442
0x18000842f  mov     rax, gs:60h
0x180008438  mov     rbx, [rax+90h]
0x18000843f  add     rbx, r12
0x180008442  mov     r9, [rdi+0C0h]
0x180008449  mov     rcx, rdi
0x18000844c  movzx   eax, byte ptr [rbx]
0x18000844f  mov     r8, [rbp+arg_0]
0x180008453  mov     rdx, [rbp+arg_8]
0x180008457  shl     r9, 4
0x18000845b  mov     [rsp+30h+var_10], rax
0x180008460  call    RtlpLogHeapExtendEvent
0x180008465  jmp     loc_18000826A
0x18000846a  mov     [r8], r9d
0x18000846d  sub     rdx, 1
0x180008471  jz      loc_18000827A
0x180008477  add     r8, 4
0x18000847b  jmp     loc_180008320
```
