# PmGrowPartition(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,_DISK_GROW_PARTITION *,__int64)

- ea: `0x14000c730`
- end: `0x14000ca14`
- name: `?PmGrowPartition@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAU_DISK_GROW_PARTITION@@_J@Z`
- size: `740`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _DRIVE_LAYOUT_INFORMATION_EX *, struct _DISK_GROW_PARTITION *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14001e2bc`

## callees

- `0x140005a84`
- `0x140007bcc`
- `0x14000a014`
- `0x14000c730`
- `0x14000cb34`
- `0x14001d090`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000c800`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c996`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c9f7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c800`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c996`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c9f7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c7b4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c9c3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c7b4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c9c3`

## pseudocode

```c
__int64 __fastcall PmGrowPartition(
        struct _DEVICE_EXTENSION *a1,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a2,
        struct _DISK_GROW_PARTITION *a3,
        LONGLONG a4)
{
  DWORD PartitionCount; // edx
  DWORD PartitionNumber; // r8d
  __int64 v9; // rsi
  __int64 v10; // r12
  int v11; // ebx
  LONGLONG v13; // rdi
  KIRQL v14; // r11
  __int64 *i; // r15
  __int64 *v16; // r13
  unsigned __int64 v17; // rax
  __int64 v18; // r8
  LARGE_INTEGER v19; // rdi
  __int64 v20; // rdx
  LARGE_INTEGER v21; // rcx
  __int64 **j; // rcx
  __int64 *v23; // rax
  __int64 v24; // rdx
  LARGE_INTEGER v25; // rax
  unsigned int v26; // r8d
  __int64 k; // rsi
  BYTE PartitionType; // cl
  __int64 v29; // rcx
  LARGE_INTEGER StartingOffset; // rax
  LARGE_INTEGER v31; // rax
  LONGLONG v32; // r10
  __int64 m; // r8
  BYTE v34; // al
  LARGE_INTEGER v35; // r9
  KIRQL v36; // al
  KIRQL v37; // bl
  int v38; // r8d
  KSPIN_LOCK *SpinLock; // [rsp+20h] [rbp-58h]
  LARGE_INTEGER BytesToGrow; // [rsp+88h] [rbp+10h]

  PartitionCount = a2->PartitionCount;
  if ( PartitionCount )
  {
    PartitionNumber = a3->PartitionNumber;
    v9 = 0;
    while ( 1 )
    {
      v10 = v9;
      if ( a2->PartitionEntry[v9].PartitionNumber == PartitionNumber )
        break;
      v9 = (unsigned int)(v9 + 1);
      if ( (unsigned int)v9 >= PartitionCount )
        return (unsigned int)-1073741810;
    }
    BytesToGrow = a3->BytesToGrow;
    if ( a2->PartitionStyle == 1 )
    {
      v13 = a2->Gpt.StartingUsableOffset.QuadPart + a2->Gpt.UsableLength.QuadPart;
      if ( a4 < v13 )
        v13 = a4;
    }
    else
    {
      v13 = a4;
    }
    SpinLock = (KSPIN_LOCK *)((char *)a1 + 112);
    v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
    for ( i = (__int64 *)*((_QWORD *)a1 + 112); ; i = (__int64 *)*i )
    {
      if ( i == (__int64 *)((char *)a1 + 896) )
      {
        v11 = -1073741810;
LABEL_18:
        KeReleaseSpinLock(SpinLock, v14);
        return (unsigned int)v11;
      }
      v16 = i - 18;
      if ( (*(_DWORD *)(i - 13) & 4) == 0 && *((_DWORD *)v16 + 48) == a3->PartitionNumber )
        break;
    }
    v17 = PartitionOffset((struct _PARTITION_EXTENSION *)(i - 18), 1u);
    if ( v17 != v18 )
    {
      v11 = -1073741637;
      goto LABEL_18;
    }
    v19.QuadPart = v13 - v18;
    v20 = v16[23];
    if ( BytesToGrow.QuadPart != 0x7FFFFFFFFFFFFFFFLL && a3->BytesToGrow.QuadPart > v19.QuadPart - v20
      || (v21 = a3->BytesToGrow, v21.QuadPart < 0) && v20 + v21.QuadPart <= 0 )
    {
LABEL_23:
      v11 = -1073741811;
      goto LABEL_18;
    }
    if ( BytesToGrow.QuadPart != 0x7FFFFFFFFFFFFFFFLL )
      v19.QuadPart = v20 + v21.QuadPart;
    for ( j = (__int64 **)*((_QWORD *)a1 + 112); j != (__int64 **)((char *)a1 + 896); j = (__int64 **)*j )
    {
      if ( (*(_DWORD *)(j - 13) & 4) == 0 )
      {
        v23 = j[4];
        v24 = i[4];
        if ( (__int64)v23 > v24 )
        {
          v25.QuadPart = (LONGLONG)v23 - v24;
          if ( BytesToGrow.QuadPart == 0x7FFFFFFFFFFFFFFFLL )
          {
            if ( v19.QuadPart >= v25.QuadPart )
              v19 = v25;
          }
          else if ( v19.QuadPart > v25.QuadPart )
          {
            goto LABEL_23;
          }
          break;
        }
      }
    }
    v26 = v9;
    if ( !a2->PartitionStyle )
    {
      for ( k = (unsigned int)v9 & 0xFFFFFFFC; (unsigned int)k < a2->PartitionCount; k = (unsigned int)(k + 1) )
      {
        PartitionType = a2->PartitionEntry[k].Mbr.PartitionType;
        if ( PartitionType == 5 || PartitionType == 15 )
        {
          v29 = v16[22];
          StartingOffset = a2->PartitionEntry[k].StartingOffset;
          if ( StartingOffset.QuadPart > v29 )
          {
            v31.QuadPart = StartingOffset.QuadPart - v29;
            if ( BytesToGrow.QuadPart == 0x7FFFFFFFFFFFFFFFLL )
            {
              if ( v19.QuadPart >= v31.QuadPart )
                v19 = v31;
            }
            else if ( v19.QuadPart > v31.QuadPart )
            {
              goto LABEL_23;
            }
          }
        }
      }
    }
    a2->PartitionEntry[v10].PartitionLength = v19;
    a2->PartitionEntry[v10].RewritePartition = 1;
    if ( !a2->PartitionStyle && v26 > 3 )
    {
      v32 = v19.QuadPart + v16[22] - 1;
      for ( m = (v26 & 0xFFFFFFFC) - 1; (int)m >= 0; m = (unsigned int)(m - 1) )
      {
        v34 = a2->PartitionEntry[m].Mbr.PartitionType;
        if ( v34 == 5 || v34 == 15 )
        {
          v35 = a2->PartitionEntry[m].StartingOffset;
          if ( v35.QuadPart + a2->PartitionEntry[m].PartitionLength.QuadPart - 1 > v32 )
            break;
          a2->PartitionEntry[m].RewritePartition = 1;
          a2->PartitionEntry[m].PartitionLength.QuadPart = v32 - v35.QuadPart + 1;
        }
      }
    }
    KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v14);
    v11 = PmWritePartitionTable(*((struct _DEVICE_OBJECT **)a1 + 1), a2);
    if ( v11 >= 0 )
    {
      PmInvalidatePartitionTableCache((KSPIN_LOCK *)a1);
      v36 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
      v16[23] = v19.QuadPart;
      v37 = v36;
      *((_DWORD *)i - 26) |= 0x10u;
      PmQueueNotificationWorkItem(a1, "PmGrowPartition", v38);
      KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v37);
      return (unsigned int)PmGetDriveLayoutEx((KSPIN_LOCK *)a1, 0);
    }
  }
  else
  {
    return (unsigned int)-1073741810;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14000c730  push    rbx
0x14000c732  push    rbp
0x14000c733  push    rsi
0x14000c734  push    rdi
0x14000c735  push    r12
0x14000c737  push    r13
0x14000c739  push    r14
0x14000c73b  push    r15
0x14000c73d  sub     rsp, 38h
0x14000c741  mov     rbx, rdx
0x14000c744  mov     r14, r8
0x14000c747  mov     edx, [rdx+4]
0x14000c74a  mov     rbp, rcx
0x14000c74d  test    edx, edx
0x14000c74f  jz      short loc_14000C76A
0x14000c751  mov     r8d, [r8]
0x14000c754  xor     esi, esi
0x14000c756  lea     r12, [rsi+rsi*8]
0x14000c75a  add     r12, r12
0x14000c75d  cmp     [rbx+r12*8+48h], r8d
0x14000c762  jz      short loc_14000C783
0x14000c764  inc     esi
0x14000c766  cmp     esi, edx
0x14000c768  jb      short loc_14000C756
0x14000c76a  mov     ebx, 0C000000Eh
0x14000c76f  mov     eax, ebx
0x14000c771  add     rsp, 38h
0x14000c775  pop     r15
0x14000c777  pop     r14
0x14000c779  pop     r13
0x14000c77b  pop     r12
0x14000c77d  pop     rdi
0x14000c77e  pop     rsi
0x14000c77f  pop     rbp
0x14000c780  pop     rbx
0x14000c781  retn
0x14000c783  cmp     dword ptr [rbx], 1
0x14000c786  mov     rax, [r14+8]
0x14000c78a  mov     [rsp+78h+arg_8], rax
0x14000c792  jnz     short loc_14000C7A5
0x14000c794  mov     rdi, [rbx+20h]
0x14000c798  add     rdi, [rbx+18h]
0x14000c79c  cmp     r9, rdi
0x14000c79f  cmovl   rdi, r9
0x14000c7a3  jmp     short loc_14000C7A8
0x14000c7a5  mov     rdi, r9
0x14000c7a8  lea     rax, [rcx+70h]
0x14000c7ac  mov     rcx, rax; SpinLock
0x14000c7af  mov     [rsp+78h+SpinLock], rax
0x14000c7b4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000c7bb  nop     dword ptr [rax+rax+00h]
0x14000c7c0  lea     rdx, [rbp+380h]
0x14000c7c7  mov     r11b, al
0x14000c7ca  mov     r15, [rdx]
0x14000c7cd  jmp     short loc_14000C7EE
0x14000c7cf  lea     r13, [r15-90h]
0x14000c7d6  mov     ecx, [r13+28h]
0x14000c7da  test    cl, 4
0x14000c7dd  jnz     short loc_14000C7EB
0x14000c7df  mov     eax, [r14]
0x14000c7e2  cmp     [r13+0C0h], eax
0x14000c7e9  jz      short loc_14000C811
0x14000c7eb  mov     r15, [r15]
0x14000c7ee  cmp     r15, rdx
0x14000c7f1  jnz     short loc_14000C7CF
0x14000c7f3  mov     ebx, 0C000000Eh
0x14000c7f8  mov     rcx, [rsp+78h+SpinLock]; SpinLock
0x14000c7fd  mov     dl, r11b; NewIrql
0x14000c800  call    cs:__imp_KeReleaseSpinLock
0x14000c807  nop     dword ptr [rax+rax+00h]
0x14000c80c  jmp     loc_14000C76F
0x14000c811  mov     r8, [r13+0B0h]
0x14000c818  mov     dl, 1; unsigned __int8
0x14000c81a  mov     rcx, r13; struct _PARTITION_EXTENSION *
0x14000c81d  call    ?PartitionOffset@@YA_KPEAU_PARTITION_EXTENSION@@E@Z; PartitionOffset(_PARTITION_EXTENSION *,uchar)
0x14000c822  cmp     rax, r8
0x14000c825  jz      short loc_14000C82E
0x14000c827  mov     ebx, 0C00000BBh
0x14000c82c  jmp     short loc_14000C7F8
0x14000c82e  mov     r9, [rsp+78h+arg_8]
0x14000c836  sub     rdi, r8
0x14000c839  mov     rdx, [r13+0B8h]
0x14000c840  mov     r10, 7FFFFFFFFFFFFFFFh
0x14000c84a  cmp     r9, r10
0x14000c84d  jz      short loc_14000C862
0x14000c84f  mov     rax, rdi
0x14000c852  sub     rax, rdx
0x14000c855  cmp     [r14+8], rax
0x14000c859  jle     short loc_14000C862
0x14000c85b  mov     ebx, 0C000000Dh
0x14000c860  jmp     short loc_14000C7F8
0x14000c862  mov     rcx, [r14+8]
0x14000c866  test    rcx, rcx
0x14000c869  jns     short loc_14000C874
0x14000c86b  lea     rax, [rdx+rcx]
0x14000c86f  test    rax, rax
0x14000c872  jle     short loc_14000C85B
0x14000c874  cmp     r9, r10
0x14000c877  jz      short loc_14000C87D
0x14000c879  lea     rdi, [rdx+rcx]
0x14000c87d  mov     rcx, [rbp+380h]
0x14000c884  lea     r8, [rbp+380h]
0x14000c88b  jmp     short loc_14000C8A4
0x14000c88d  mov     eax, [rcx-68h]
0x14000c890  test    al, 4
0x14000c892  jnz     short loc_14000C8A1
0x14000c894  mov     rax, [rcx+20h]
0x14000c898  mov     rdx, [r15+20h]
0x14000c89c  cmp     rax, rdx
0x14000c89f  jg      short loc_14000C8AB
0x14000c8a1  mov     rcx, [rcx]
0x14000c8a4  cmp     rcx, r8
0x14000c8a7  jnz     short loc_14000C88D
0x14000c8a9  jmp     short loc_14000C8C2
0x14000c8ab  sub     rax, rdx
0x14000c8ae  cmp     r9, r10
0x14000c8b1  jnz     short loc_14000C8BD
0x14000c8b3  cmp     rdi, rax
0x14000c8b6  jl      short loc_14000C8C2
0x14000c8b8  mov     rdi, rax
0x14000c8bb  jmp     short loc_14000C8C2
0x14000c8bd  cmp     rdi, rax
0x14000c8c0  jg      short loc_14000C85B
0x14000c8c2  cmp     dword ptr [rbx], 0
0x14000c8c5  mov     r8d, esi
0x14000c8c8  mov     r14d, 0FFFFFFFCh
0x14000c8ce  jnz     short loc_14000C91F
0x14000c8d0  mov     edx, [rbx+4]
0x14000c8d3  and     esi, r14d
0x14000c8d6  jmp     short loc_14000C91B
0x14000c8d8  lea     rax, [rsi+rsi*8]
0x14000c8dc  add     rax, rax
0x14000c8df  mov     cl, [rbx+rax*8+50h]
0x14000c8e3  cmp     cl, 5
0x14000c8e6  jz      short loc_14000C8ED
0x14000c8e8  cmp     cl, 0Fh
0x14000c8eb  jnz     short loc_14000C919
0x14000c8ed  mov     rcx, [r13+0B0h]
0x14000c8f4  mov     rax, [rbx+rax*8+38h]
0x14000c8f9  cmp     rax, rcx
0x14000c8fc  jle     short loc_14000C919
0x14000c8fe  sub     rax, rcx
0x14000c901  cmp     r9, r10
0x14000c904  jnz     short loc_14000C910
0x14000c906  cmp     rdi, rax
0x14000c909  jl      short loc_14000C919
0x14000c90b  mov     rdi, rax
0x14000c90e  jmp     short loc_14000C919
0x14000c910  cmp     rdi, rax
0x14000c913  jg      loc_14000C85B
0x14000c919  inc     esi
0x14000c91b  cmp     esi, edx
0x14000c91d  jb      short loc_14000C8D8
0x14000c91f  mov     [rbx+r12*8+40h], rdi
0x14000c924  mov     byte ptr [rbx+r12*8+4Ch], 1
0x14000c92a  cmp     dword ptr [rbx], 0
0x14000c92d  jnz     short loc_14000C98C
0x14000c92f  cmp     r8d, 3
0x14000c933  jbe     short loc_14000C98C
0x14000c935  mov     r10, [r13+0B0h]
0x14000c93c  and     r8d, r14d
0x14000c93f  dec     r10
0x14000c942  add     r10, rdi
0x14000c945  sub     r8d, 1
0x14000c949  js      short loc_14000C98C
0x14000c94b  lea     rdx, [r8+r8*8]
0x14000c94f  add     rdx, rdx
0x14000c952  mov     al, [rbx+rdx*8+50h]
0x14000c956  cmp     al, 5
0x14000c958  jz      short loc_14000C95E
0x14000c95a  cmp     al, 0Fh
0x14000c95c  jnz     short loc_14000C986
0x14000c95e  mov     rcx, [rbx+rdx*8+40h]
0x14000c963  mov     r9, [rbx+rdx*8+38h]
0x14000c968  dec     rcx
0x14000c96b  add     rcx, r9
0x14000c96e  cmp     rcx, r10
0x14000c971  jg      short loc_14000C98C
0x14000c973  mov     rax, r10
0x14000c976  mov     byte ptr [rbx+rdx*8+4Ch], 1
0x14000c97b  sub     rax, r9
0x14000c97e  inc     rax
0x14000c981  mov     [rbx+rdx*8+40h], rax
0x14000c986  add     r8d, 0FFFFFFFFh
0x14000c98a  jns     short loc_14000C94B
0x14000c98c  lea     rsi, [rbp+70h]
0x14000c990  mov     dl, r11b; NewIrql
0x14000c993  mov     rcx, rsi; SpinLock
0x14000c996  call    cs:__imp_KeReleaseSpinLock
0x14000c99d  nop     dword ptr [rax+rax+00h]
0x14000c9a2  mov     rcx, [rbp+8]; struct _DEVICE_OBJECT *
0x14000c9a6  mov     rdx, rbx; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14000c9a9  call    ?PmWritePartitionTable@@YAJPEAU_DEVICE_OBJECT@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmWritePartitionTable(_DEVICE_OBJECT *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x14000c9ae  mov     ebx, eax
0x14000c9b0  test    eax, eax
0x14000c9b2  js      loc_14000C76F
0x14000c9b8  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x14000c9bb  call    ?PmInvalidatePartitionTableCache@@YAXPEAU_DEVICE_EXTENSION@@@Z; PmInvalidatePartitionTableCache(_DEVICE_EXTENSION *)
0x14000c9c0  mov     rcx, rsi; SpinLock
0x14000c9c3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000c9ca  nop     dword ptr [rax+rax+00h]
0x14000c9cf  mov     [r13+0B8h], rdi
0x14000c9d6  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x14000c9d9  mov     edx, [r15-68h]
0x14000c9dd  mov     bl, al
0x14000c9df  or      edx, 10h
0x14000c9e2  mov     [r15-68h], edx
0x14000c9e6  lea     rdx, aPmgrowpartitio; "PmGrowPartition"
0x14000c9ed  call    ?PmQueueNotificationWorkItem@@YAJPEAU_DEVICE_EXTENSION@@PEBD@Z; PmQueueNotificationWorkItem(_DEVICE_EXTENSION *,char const *)
0x14000c9f2  mov     dl, bl; NewIrql
0x14000c9f4  mov     rcx, rsi; SpinLock
0x14000c9f7  call    cs:__imp_KeReleaseSpinLock
0x14000c9fe  nop     dword ptr [rax+rax+00h]
0x14000ca03  xor     edx, edx; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x14000ca05  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x14000ca08  call    ?PmGetDriveLayoutEx@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmGetDriveLayoutEx(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX * *)
0x14000ca0d  mov     ebx, eax
0x14000ca0f  jmp     loc_14000C76F
```
