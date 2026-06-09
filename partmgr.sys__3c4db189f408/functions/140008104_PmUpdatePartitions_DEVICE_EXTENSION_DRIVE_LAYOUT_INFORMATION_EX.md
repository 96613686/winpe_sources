# PmUpdatePartitions(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *)

- ea: `0x140008104`
- end: `0x14000848f`
- name: `?PmUpdatePartitions@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `907`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _DRIVE_LAYOUT_INFORMATION_EX *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x140005b2c`

## callees

- `0x140004ef8`
- `0x140005ab0`
- `0x140007f70`
- `0x140008104`
- `0x1400254c8`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140008211`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008374`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400083c7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000845d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008211`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008374`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400083c7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000845d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400081ec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000833f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400083ad`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400083dd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008443`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400081ec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000833f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400083ad`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400083dd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008443`

## pseudocode

```c
__int64 __fastcall PmUpdatePartitions(struct _DEVICE_EXTENSION *a1, struct _DRIVE_LAYOUT_INFORMATION_EX *a2)
{
  LARGE_INTEGER **v2; // rsi
  LARGE_INTEGER **v3; // r14
  LARGE_INTEGER **v6; // rdi
  __int64 v7; // r10
  SC_PART_ENTRY *v8; // rcx
  unsigned int v9; // r10d
  unsigned int v10; // r11d
  struct _DRIVE_LAYOUT_INFORMATION_EX *v11; // r8
  __int64 v12; // r9
  KIRQL v13; // al
  __int64 v14; // rbp
  PARTITION_INFORMATION_EX *PartitionEntry; // r14
  PARTITION_INFORMATION_EX *v16; // rdi
  SC_PART_ENTRY *v17; // rcx
  bool v18; // zf
  __int64 v19; // rax
  unsigned __int64 v20; // rax
  LARGE_INTEGER **i; // rcx
  DWORD PartitionNumber; // eax
  LARGE_INTEGER *j; // rbx
  LARGE_INTEGER v24; // rax
  KIRQL v25; // al
  LARGE_INTEGER **QuadPart; // r8
  LARGE_INTEGER *v27; // rdx
  LARGE_INTEGER **k; // rbx
  KIRQL v29; // al
  LARGE_INTEGER **m; // rdx
  LARGE_INTEGER *v31; // rcx
  LARGE_INTEGER *v32; // r8
  KIRQL v33; // al
  unsigned __int64 v35; // [rsp+60h] [rbp+8h] BYREF
  struct _PARTITION_EXTENSION *v36; // [rsp+68h] [rbp+10h] BYREF

  v2 = (LARGE_INTEGER **)((char *)a1 + 896);
  v36 = 0;
  v3 = (LARGE_INTEGER **)*((_QWORD *)a1 + 112);
  v35 = -2;
  while ( v3 != v2 )
  {
    v6 = v3 - 18;
    if ( (*(_DWORD *)(v3 - 13) & 4) == 0 )
    {
      v7 = 0;
      if ( a2->PartitionCount )
      {
        while ( SC_PART_ENTRY::IsUnused((SC_PART_ENTRY *)&a2->PartitionEntry[v7])
             || SC_PART_ENTRY::IsContainer(v8)
             || *(_DWORD *)(v12 + 24)
             || *(LARGE_INTEGER **)(v12 + 8) != v6[22]
             || *(LARGE_INTEGER **)(v12 + 16) != v6[23]
             || *(_DWORD *)v12 == 1
             && *((_DWORD *)v6 + 42) == 1
             && (*(LARGE_INTEGER **)(v12 + 48) != v6[27] || *(LARGE_INTEGER **)(v12 + 56) != v6[28]) )
        {
          v7 = v9 + 1;
          if ( (unsigned int)v7 >= v10 )
            goto LABEL_14;
        }
        v20 = *((unsigned int *)v6 + 48);
        *(_DWORD *)(v12 + 24) = v20;
        if ( (unsigned int)v20 < 0x40 )
          _bittestandreset64((signed __int64 *)&v35, v20);
        PmUpdatePartition(
          a1,
          (struct _PARTITION_EXTENSION *)(v3 - 18),
          v11,
          v9,
          (struct _PARTITION_INFORMATION_EX *)v12);
      }
      else
      {
LABEL_14:
        v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
        *((_DWORD *)v6 + 10) |= 4u;
        *((_DWORD *)v6 + 40) = -1;
        KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v13);
      }
    }
    v3 = (LARGE_INTEGER **)*v3;
  }
  v14 = 0;
  if ( a2->PartitionCount )
  {
    PartitionEntry = a2->PartitionEntry;
    do
    {
      v16 = &PartitionEntry[v14];
      if ( !SC_PART_ENTRY::IsUnused((SC_PART_ENTRY *)v16) && !SC_PART_ENTRY::IsContainer(v17) && !v16->PartitionNumber )
      {
        v18 = !_BitScanForward64((unsigned __int64 *)&v19, v35);
        v16->PartitionNumber = v19;
        if ( v18 )
        {
          v16->PartitionNumber = 64;
LABEL_30:
          for ( i = (LARGE_INTEGER **)*((_QWORD *)a1 + 112); i != v2; i = (LARGE_INTEGER **)*i )
          {
            if ( (*(_DWORD *)(i - 13) & 4) == 0 )
            {
              PartitionNumber = v16->PartitionNumber;
              if ( *((_DWORD *)i + 12) == PartitionNumber )
              {
                v16->PartitionNumber = PartitionNumber + 1;
                goto LABEL_30;
              }
            }
          }
        }
        else
        {
          _bittestandreset64((signed __int64 *)&v35, (unsigned int)v19);
        }
        if ( (int)PmCreatePartition(a1, a2, v14, &PartitionEntry[v14], &v36) >= 0 )
        {
          for ( j = *v2; j != (LARGE_INTEGER *)v2; j = (LARGE_INTEGER *)j->QuadPart )
          {
            if ( (j[-13].LowPart & 4) == 0 )
            {
              v24 = j[4];
              if ( v16->StartingOffset.QuadPart < v24.QuadPart
                || v16->StartingOffset.QuadPart == v24.QuadPart && (unsigned int)v14 < j[2].LowPart )
              {
                break;
              }
            }
          }
          v25 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
          QuadPart = (LARGE_INTEGER **)j[1].QuadPart;
          if ( *QuadPart != j )
            __fastfail(3u);
          v27 = (LARGE_INTEGER *)((char *)v36 + 144);
          *((_QWORD *)v36 + 18) = j;
          v27[1].QuadPart = (LONGLONG)QuadPart;
          *QuadPart = v27;
          j[1].QuadPart = (LONGLONG)v27;
          KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v25);
        }
        else
        {
          v16->PartitionNumber = 0;
        }
      }
      v14 = (unsigned int)(v14 + 1);
    }
    while ( (unsigned int)v14 < a2->PartitionCount );
  }
  for ( k = (LARGE_INTEGER **)*v2; k != v2; k = (LARGE_INTEGER **)*k )
  {
    if ( (*(_DWORD *)(k - 13) & 4) == 0 )
    {
      v29 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
      *((_DWORD *)k - 26) &= ~0x40u;
      KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v29);
      if ( k[5] )
      {
        for ( m = (LARGE_INTEGER **)*v2; m != v2; m = (LARGE_INTEGER **)*m )
        {
          if ( m != k && (*(_DWORD *)(m - 13) & 4) == 0 && *((_DWORD *)m + 4) <= *((_DWORD *)k + 4) )
          {
            v31 = (LARGE_INTEGER *)(m + 3);
            if ( k[4] > m[4] )
            {
              v32 = (LARGE_INTEGER *)(m + 3);
              v31 = (LARGE_INTEGER *)(k + 3);
            }
            else
            {
              v32 = (LARGE_INTEGER *)(k + 3);
            }
            if ( v32[2].QuadPart > (unsigned __int64)(v31[1].QuadPart - v32[1].QuadPart) )
              goto LABEL_62;
          }
        }
      }
      else
      {
LABEL_62:
        v33 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
        *((_DWORD *)k - 26) |= 0x40u;
        KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v33);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140008104  mov     rax, rsp
0x140008107  mov     [rax+18h], rbx
0x14000810b  mov     [rax+20h], rbp
0x14000810f  push    rsi
0x140008110  push    rdi
0x140008111  push    r13
0x140008113  push    r14
0x140008115  push    r15
0x140008117  sub     rsp, 30h
0x14000811b  lea     rsi, [rcx+380h]
0x140008122  mov     qword ptr [rax+10h], 0
0x14000812a  mov     r14, [rsi]
0x14000812d  mov     r15, rdx
0x140008130  mov     r13, rcx
0x140008133  mov     qword ptr [rax+8], 0FFFFFFFFFFFFFFFEh
0x14000813b  jmp     loc_140008220
0x140008140  lea     rdi, [r14-90h]
0x140008147  mov     eax, [rdi+28h]
0x14000814a  test    al, 4
0x14000814c  jnz     loc_14000821D
0x140008152  mov     r11d, [r15+4]
0x140008156  xor     r10d, r10d
0x140008159  test    r11d, r11d
0x14000815c  jz      loc_1400081E8
0x140008162  lea     r9, [r10+r10*8]
0x140008166  shl     r9, 4
0x14000816a  add     r9, 30h ; '0'
0x14000816e  add     r9, r15
0x140008171  mov     rcx, r9; this
0x140008174  call    ?IsUnused@SC_PART_ENTRY@@QEAAEXZ; SC_PART_ENTRY::IsUnused(void)
0x140008179  test    al, al
0x14000817b  jnz     short loc_1400081DC
0x14000817d  call    ?IsContainer@SC_PART_ENTRY@@QEAAEXZ; SC_PART_ENTRY::IsContainer(void)
0x140008182  test    al, al
0x140008184  jnz     short loc_1400081DC
0x140008186  cmp     dword ptr [r9+18h], 0
0x14000818b  jnz     short loc_1400081DC
0x14000818d  mov     rax, [rdi+0B0h]
0x140008194  cmp     [r9+8], rax
0x140008198  jnz     short loc_1400081DC
0x14000819a  mov     rax, [rdi+0B8h]
0x1400081a1  cmp     [r9+10h], rax
0x1400081a5  jnz     short loc_1400081DC
0x1400081a7  cmp     dword ptr [r9], 1
0x1400081ab  jnz     loc_1400082B3
0x1400081b1  cmp     dword ptr [rdi+0A8h], 1
0x1400081b8  jnz     loc_1400082B3
0x1400081be  mov     rax, [r9+30h]
0x1400081c2  cmp     rax, [rdi+0D8h]
0x1400081c9  jnz     short loc_1400081DC
0x1400081cb  mov     rax, [r9+38h]
0x1400081cf  cmp     rax, [rdi+0E0h]
0x1400081d6  jz      loc_1400082B3
0x1400081dc  inc     r10d
0x1400081df  cmp     r10d, r11d
0x1400081e2  jb      loc_140008162
0x1400081e8  lea     rcx, [r13+70h]; SpinLock
0x1400081ec  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400081f3  nop     dword ptr [rax+rax+00h]
0x1400081f8  mov     edx, [rdi+28h]
0x1400081fb  lea     rcx, [r13+70h]; SpinLock
0x1400081ff  or      edx, 4
0x140008202  mov     [rdi+28h], edx
0x140008205  mov     dl, al; NewIrql
0x140008207  mov     dword ptr [rdi+0A0h], 0FFFFFFFFh
0x140008211  call    cs:__imp_KeReleaseSpinLock
0x140008218  nop     dword ptr [rax+rax+00h]
0x14000821d  mov     r14, [r14]
0x140008220  cmp     r14, rsi
0x140008223  jnz     loc_140008140
0x140008229  xor     ebp, ebp
0x14000822b  cmp     [r15+4], ebp
0x14000822f  jbe     loc_14000838C
0x140008235  lea     r14, [r15+30h]
0x140008239  lea     rdi, ds:0[rbp*8]
0x140008241  add     rdi, rbp
0x140008244  shl     rdi, 4
0x140008248  add     rdi, r14
0x14000824b  mov     rcx, rdi; this
0x14000824e  call    ?IsUnused@SC_PART_ENTRY@@QEAAEXZ; SC_PART_ENTRY::IsUnused(void)
0x140008253  test    al, al
0x140008255  jnz     loc_140008380
0x14000825b  call    ?IsContainer@SC_PART_ENTRY@@QEAAEXZ; SC_PART_ENTRY::IsContainer(void)
0x140008260  test    al, al
0x140008262  jnz     loc_140008380
0x140008268  cmp     dword ptr [rdi+18h], 0
0x14000826c  jnz     loc_140008380
0x140008272  bsf     rax, [rsp+58h+arg_0]
0x140008278  mov     [rdi+18h], eax
0x14000827b  jz      short loc_1400082E3
0x14000827d  mov     eax, eax
0x14000827f  lea     rcx, [rsp+58h+arg_0]
0x140008284  btr     [rcx], rax
0x140008288  lea     rax, [rsp+58h+arg_8]
0x14000828d  mov     r9, rdi; struct _PARTITION_INFORMATION_EX *
0x140008290  mov     r8d, ebp; unsigned int
0x140008293  mov     [rsp+58h+var_38], rax; struct _PARTITION_EXTENSION **
0x140008298  mov     rdx, r15; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14000829b  mov     rcx, r13; struct _DEVICE_EXTENSION *
0x14000829e  call    ?PmCreatePartition@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@KPEAU_PARTITION_INFORMATION_EX@@PEAPEAU_PARTITION_EXTENSION@@@Z; PmCreatePartition(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,ulong,_PARTITION_INFORMATION_EX *,_PARTITION_EXTENSION * *)
0x1400082a3  test    eax, eax
0x1400082a5  jns     short loc_140008316
0x1400082a7  mov     dword ptr [rdi+18h], 0
0x1400082ae  jmp     loc_140008380
0x1400082b3  mov     eax, [rdi+0C0h]
0x1400082b9  mov     [r9+18h], eax
0x1400082bd  cmp     eax, 40h ; '@'
0x1400082c0  jnb     short loc_1400082CB
0x1400082c2  lea     rcx, [rsp+58h+arg_0]
0x1400082c7  btr     [rcx], rax
0x1400082cb  mov     [rsp+58h+var_38], r9; struct _PARTITION_INFORMATION_EX *
0x1400082d0  mov     rdx, rdi; struct _PARTITION_EXTENSION *
0x1400082d3  mov     r9d, r10d; unsigned int
0x1400082d6  mov     rcx, r13; struct _DEVICE_EXTENSION *
0x1400082d9  call    ?PmUpdatePartition@@YAJPEAU_DEVICE_EXTENSION@@PEAU_PARTITION_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@KPEAU_PARTITION_INFORMATION_EX@@@Z; PmUpdatePartition(_DEVICE_EXTENSION *,_PARTITION_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,ulong,_PARTITION_INFORMATION_EX *)
0x1400082de  jmp     loc_14000821D
0x1400082e3  mov     dword ptr [rdi+18h], 40h ; '@'
0x1400082ea  mov     rcx, [r13+380h]
0x1400082f1  jmp     short loc_140008305
0x1400082f3  mov     eax, [rcx-68h]
0x1400082f6  test    al, 4
0x1400082f8  jnz     short loc_140008302
0x1400082fa  mov     eax, [rdi+18h]
0x1400082fd  cmp     [rcx+30h], eax
0x140008300  jz      short loc_14000830F
0x140008302  mov     rcx, [rcx]
0x140008305  cmp     rcx, rsi
0x140008308  jnz     short loc_1400082F3
0x14000830a  jmp     loc_140008288
0x14000830f  inc     eax
0x140008311  mov     [rdi+18h], eax
0x140008314  jmp     short loc_1400082EA
0x140008316  mov     rbx, [rsi]
0x140008319  jmp     short loc_140008336
0x14000831b  mov     eax, [rbx-68h]
0x14000831e  test    al, 4
0x140008320  jnz     short loc_140008333
0x140008322  mov     rax, [rbx+20h]
0x140008326  cmp     [rdi+8], rax
0x14000832a  jl      short loc_14000833B
0x14000832c  jnz     short loc_140008333
0x14000832e  cmp     ebp, [rbx+10h]
0x140008331  jb      short loc_14000833B
0x140008333  mov     rbx, [rbx]
0x140008336  cmp     rbx, rsi
0x140008339  jnz     short loc_14000831B
0x14000833b  lea     rcx, [r13+70h]; SpinLock
0x14000833f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008346  nop     dword ptr [rax+rax+00h]
0x14000834b  mov     r8, [rbx+8]
0x14000834f  cmp     [r8], rbx
0x140008352  jnz     short loc_140008394
0x140008354  mov     rdx, [rsp+58h+arg_8]
0x140008359  lea     rcx, [r13+70h]; SpinLock
0x14000835d  add     rdx, 90h
0x140008364  mov     [rdx], rbx
0x140008367  mov     [rdx+8], r8
0x14000836b  mov     [r8], rdx
0x14000836e  mov     [rbx+8], rdx
0x140008372  mov     dl, al; NewIrql
0x140008374  call    cs:__imp_KeReleaseSpinLock
0x14000837b  nop     dword ptr [rax+rax+00h]
0x140008380  inc     ebp
0x140008382  cmp     ebp, [r15+4]
0x140008386  jb      loc_140008239
0x14000838c  mov     rbx, [rsi]
0x14000838f  jmp     loc_14000846C
0x140008394  mov     ecx, 3
0x140008399  int     29h; Win8: RtlFailFast(ecx)
0x14000839b  mov     eax, [rbx-68h]
0x14000839e  test    al, 4
0x1400083a0  jnz     loc_140008469
0x1400083a6  lea     rdi, [r13+70h]
0x1400083aa  mov     rcx, rdi; SpinLock
0x1400083ad  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400083b4  nop     dword ptr [rax+rax+00h]
0x1400083b9  mov     ecx, [rbx-68h]
0x1400083bc  mov     dl, al; NewIrql
0x1400083be  and     ecx, 0FFFFFFBFh
0x1400083c1  mov     [rbx-68h], ecx
0x1400083c4  mov     rcx, rdi; SpinLock
0x1400083c7  call    cs:__imp_KeReleaseSpinLock
0x1400083ce  nop     dword ptr [rax+rax+00h]
0x1400083d3  cmp     qword ptr [rbx+28h], 0
0x1400083d8  jnz     short loc_1400083F4
0x1400083da  mov     rcx, rdi; SpinLock
0x1400083dd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400083e4  nop     dword ptr [rax+rax+00h]
0x1400083e9  mov     edx, [rbx-68h]
0x1400083ec  or      edx, 40h
0x1400083ef  mov     [rbx-68h], edx
0x1400083f2  jmp     short loc_140008458
0x1400083f4  mov     rdx, [rsi]
0x1400083f7  jmp     short loc_140008439
0x1400083f9  cmp     rdx, rbx
0x1400083fc  jz      short loc_140008436
0x1400083fe  mov     eax, [rdx-68h]
0x140008401  test    al, 4
0x140008403  jnz     short loc_140008436
0x140008405  mov     eax, [rbx+10h]
0x140008408  cmp     [rdx+10h], eax
0x14000840b  ja      short loc_140008436
0x14000840d  lea     rcx, [rdx+18h]
0x140008411  mov     rax, [rcx+8]
0x140008415  cmp     [rbx+20h], rax
0x140008419  ja      short loc_140008421
0x14000841b  lea     r8, [rbx+18h]
0x14000841f  jmp     short loc_140008428
0x140008421  mov     r8, rcx
0x140008424  lea     rcx, [rbx+18h]
0x140008428  mov     rcx, [rcx+8]
0x14000842c  sub     rcx, [r8+8]
0x140008430  cmp     [r8+10h], rcx
0x140008434  ja      short loc_140008440
0x140008436  mov     rdx, [rdx]
0x140008439  cmp     rdx, rsi
0x14000843c  jnz     short loc_1400083F9
0x14000843e  jmp     short loc_140008469
0x140008440  mov     rcx, rdi; SpinLock
0x140008443  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000844a  nop     dword ptr [rax+rax+00h]
0x14000844f  mov     ecx, [rbx-68h]
0x140008452  or      ecx, 40h
0x140008455  mov     [rbx-68h], ecx
0x140008458  mov     dl, al; NewIrql
0x14000845a  mov     rcx, rdi; SpinLock
0x14000845d  call    cs:__imp_KeReleaseSpinLock
0x140008464  nop     dword ptr [rax+rax+00h]
0x140008469  mov     rbx, [rbx]
0x14000846c  cmp     rbx, rsi
0x14000846f  jnz     loc_14000839B
0x140008475  mov     rbx, [rsp+58h+arg_10]
0x14000847a  xor     eax, eax
0x14000847c  mov     rbp, [rsp+58h+arg_18]
0x140008481  add     rsp, 30h
0x140008485  pop     r15
0x140008487  pop     r14
0x140008489  pop     r13
0x14000848b  pop     rdi
0x14000848c  pop     rsi
0x14000848d  retn
```
