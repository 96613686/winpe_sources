# PmSetLegacyRemovableFlag(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *)

- ea: `0x14000ce84`
- end: `0x14000d041`
- name: `?PmSetLegacyRemovableFlag@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `445`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _DRIVE_LAYOUT_INFORMATION_EX *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140005b2c`

## callees

- `0x140004ef8`
- `0x140005ab0`
- `0x14000ce84`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000cee0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cf89`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d025`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cee0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cf89`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d025`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ceb0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cf69`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cfb7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cff0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ceb0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cf69`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cfb7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cff0`

## pseudocode

```c
__int64 __fastcall PmSetLegacyRemovableFlag(struct _DEVICE_EXTENSION *a1, struct _DRIVE_LAYOUT_INFORMATION_EX *a2)
{
  KSPIN_LOCK *v4; // rdi
  KIRQL v5; // al
  int v6; // ebp
  DWORD PartitionCount; // r10d
  char v8; // r14
  __int64 v9; // r11
  SC_PART_ENTRY *v10; // rcx
  int v11; // r9d
  unsigned int v12; // r10d
  int v13; // r11d
  KIRQL v14; // al
  char *v15; // rbx
  KIRQL v16; // al
  __int64 v17; // r8
  __int64 **v18; // rbx
  __int64 *i; // rdx

  if ( (*(_DWORD *)(*((_QWORD *)a1 + 1) + 52LL) & 1) == 0 )
    return 0;
  v4 = (KSPIN_LOCK *)((char *)a1 + 112);
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
  v6 = *((_DWORD *)a1 + 129) & 0x1000;
  *((_DWORD *)a1 + 129) &= ~0x1000u;
  KeReleaseSpinLock(v4, v5);
  if ( !a2->PartitionStyle )
  {
    PartitionCount = a2->PartitionCount;
    v8 = 0;
    if ( PartitionCount != 1
      || a2->PartitionEntry[0].StartingOffset.QuadPart
      || a2->PartitionEntry[0].PartitionLength.QuadPart )
    {
      v9 = 0;
      if ( !PartitionCount )
      {
LABEL_16:
        v14 = KeAcquireSpinLockRaiseToDpc(v4);
        *((_DWORD *)a1 + 129) |= 0x1000u;
        KeReleaseSpinLock(v4, v14);
        goto LABEL_17;
      }
    }
    else
    {
      v8 = 1;
      v9 = 0;
    }
    do
    {
      if ( !SC_PART_ENTRY::IsUnused((SC_PART_ENTRY *)&a2->PartitionEntry[v9]) && !SC_PART_ENTRY::IsContainer(v10) )
        ++v11;
      v9 = (unsigned int)(v13 + 1);
    }
    while ( (unsigned int)v9 < v12 );
    if ( v11 )
    {
      if ( v11 != 1 )
        goto LABEL_17;
      if ( !v8 && !v6 )
        goto LABEL_22;
    }
    goto LABEL_16;
  }
LABEL_17:
  if ( v6 )
  {
    if ( (*((_DWORD *)a1 + 129) & 0x1000) == 0 )
    {
      v15 = (char *)a1 + 896;
      if ( *(char **)v15 != v15 )
      {
        v16 = KeAcquireSpinLockRaiseToDpc(v4);
        v17 = *(_QWORD *)v15;
        if ( !*(_QWORD *)(*(_QWORD *)v15 + 40LL) )
        {
          *(_DWORD *)(v17 - 104) |= 4u;
          *(_DWORD *)(v17 + 16) = -1;
        }
        goto LABEL_26;
      }
    }
    return 0;
  }
LABEL_22:
  if ( (*((_DWORD *)a1 + 129) & 0x1000) != 0 )
  {
    v16 = KeAcquireSpinLockRaiseToDpc(v4);
    v18 = (__int64 **)((char *)a1 + 896);
    for ( i = *v18; i != (__int64 *)v18; i = (__int64 *)*i )
    {
      *((_DWORD *)i - 26) |= 4u;
      *((_DWORD *)i + 4) = -1;
    }
LABEL_26:
    KeReleaseSpinLock(v4, v16);
  }
  return 0;
}

```

## disassembly

```asm
0x14000ce84  push    rbx
0x14000ce86  push    rbp
0x14000ce87  push    rsi
0x14000ce88  push    rdi
0x14000ce89  push    r12
0x14000ce8b  push    r14
0x14000ce8d  sub     rsp, 28h
0x14000ce91  mov     rax, [rcx+8]
0x14000ce95  mov     rsi, rdx
0x14000ce98  mov     rbx, rcx
0x14000ce9b  mov     r8d, [rax+34h]
0x14000ce9f  test    r8b, 1
0x14000cea3  jz      loc_14000D031
0x14000cea9  lea     rdi, [rcx+70h]
0x14000cead  mov     rcx, rdi; SpinLock
0x14000ceb0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000ceb7  nop     dword ptr [rax+rax+00h]
0x14000cebc  mov     ebp, [rbx+204h]
0x14000cec2  mov     r12d, 1000h
0x14000cec8  mov     ecx, [rbx+204h]
0x14000cece  mov     dl, al; NewIrql
0x14000ced0  btr     ecx, 0Ch
0x14000ced4  and     ebp, r12d
0x14000ced7  mov     [rbx+204h], ecx
0x14000cedd  mov     rcx, rdi; SpinLock
0x14000cee0  call    cs:__imp_KeReleaseSpinLock
0x14000cee7  nop     dword ptr [rax+rax+00h]
0x14000ceec  cmp     dword ptr [rsi], 0
0x14000ceef  jnz     loc_14000CF95
0x14000cef5  mov     r10d, [rsi+4]
0x14000cef9  xor     r14b, r14b
0x14000cefc  cmp     r10d, 1
0x14000cf00  jnz     short loc_14000CF1B
0x14000cf02  cmp     qword ptr [rsi+38h], 0
0x14000cf07  jnz     short loc_14000CF1B
0x14000cf09  cmp     qword ptr [rsi+40h], 0
0x14000cf0e  jnz     short loc_14000CF1B
0x14000cf10  xor     r9d, r9d
0x14000cf13  mov     r14b, r10b
0x14000cf16  xor     r11d, r11d
0x14000cf19  jmp     short loc_14000CF26
0x14000cf1b  xor     r9d, r9d
0x14000cf1e  xor     r11d, r11d
0x14000cf21  test    r10d, r10d
0x14000cf24  jz      short loc_14000CF66
0x14000cf26  lea     rcx, [r11+r11*8]
0x14000cf2a  shl     rcx, 4
0x14000cf2e  add     rcx, 30h ; '0'
0x14000cf32  add     rcx, rsi; this
0x14000cf35  call    ?IsUnused@SC_PART_ENTRY@@QEAAEXZ; SC_PART_ENTRY::IsUnused(void)
0x14000cf3a  test    al, al
0x14000cf3c  jnz     short loc_14000CF4A
0x14000cf3e  call    ?IsContainer@SC_PART_ENTRY@@QEAAEXZ; SC_PART_ENTRY::IsContainer(void)
0x14000cf43  test    al, al
0x14000cf45  jnz     short loc_14000CF4A
0x14000cf47  inc     r9d
0x14000cf4a  inc     r11d
0x14000cf4d  cmp     r11d, r10d
0x14000cf50  jb      short loc_14000CF26
0x14000cf52  test    r9d, r9d
0x14000cf55  jz      short loc_14000CF66
0x14000cf57  cmp     r9d, 1
0x14000cf5b  jnz     short loc_14000CF95
0x14000cf5d  test    r14b, r14b
0x14000cf60  jnz     short loc_14000CF66
0x14000cf62  test    ebp, ebp
0x14000cf64  jz      short loc_14000CFE2
0x14000cf66  mov     rcx, rdi; SpinLock
0x14000cf69  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000cf70  nop     dword ptr [rax+rax+00h]
0x14000cf75  mov     ecx, [rbx+204h]
0x14000cf7b  mov     dl, al; NewIrql
0x14000cf7d  or      ecx, r12d
0x14000cf80  mov     [rbx+204h], ecx
0x14000cf86  mov     rcx, rdi; SpinLock
0x14000cf89  call    cs:__imp_KeReleaseSpinLock
0x14000cf90  nop     dword ptr [rax+rax+00h]
0x14000cf95  test    ebp, ebp
0x14000cf97  jz      short loc_14000CFE2
0x14000cf99  mov     eax, [rbx+204h]
0x14000cf9f  test    r12d, eax
0x14000cfa2  jnz     loc_14000D031
0x14000cfa8  add     rbx, 380h
0x14000cfaf  cmp     [rbx], rbx
0x14000cfb2  jz      short loc_14000D031
0x14000cfb4  mov     rcx, rdi; SpinLock
0x14000cfb7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000cfbe  nop     dword ptr [rax+rax+00h]
0x14000cfc3  mov     r8, [rbx]
0x14000cfc6  cmp     qword ptr [r8+28h], 0
0x14000cfcb  jnz     short loc_14000D020
0x14000cfcd  mov     edx, [r8-68h]
0x14000cfd1  or      edx, 4
0x14000cfd4  mov     [r8-68h], edx
0x14000cfd8  mov     dword ptr [r8+10h], 0FFFFFFFFh
0x14000cfe0  jmp     short loc_14000D020
0x14000cfe2  mov     eax, [rbx+204h]
0x14000cfe8  test    r12d, eax
0x14000cfeb  jz      short loc_14000D031
0x14000cfed  mov     rcx, rdi; SpinLock
0x14000cff0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000cff7  nop     dword ptr [rax+rax+00h]
0x14000cffc  add     rbx, 380h
0x14000d003  mov     rdx, [rbx]
0x14000d006  jmp     short loc_14000D01B
0x14000d008  mov     ecx, [rdx-68h]
0x14000d00b  or      ecx, 4
0x14000d00e  mov     [rdx-68h], ecx
0x14000d011  mov     dword ptr [rdx+10h], 0FFFFFFFFh
0x14000d018  mov     rdx, [rdx]
0x14000d01b  cmp     rdx, rbx
0x14000d01e  jnz     short loc_14000D008
0x14000d020  mov     dl, al; NewIrql
0x14000d022  mov     rcx, rdi; SpinLock
0x14000d025  call    cs:__imp_KeReleaseSpinLock
0x14000d02c  nop     dword ptr [rax+rax+00h]
0x14000d031  xor     eax, eax
0x14000d033  add     rsp, 28h
0x14000d037  pop     r14
0x14000d039  pop     r12
0x14000d03b  pop     rdi
0x14000d03c  pop     rsi
0x14000d03d  pop     rbp
0x14000d03e  pop     rbx
0x14000d03f  retn
```
