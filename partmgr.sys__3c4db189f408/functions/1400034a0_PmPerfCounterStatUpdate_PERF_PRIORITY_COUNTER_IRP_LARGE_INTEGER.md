# PmPerfCounterStatUpdate(_PERF_PRIORITY_COUNTER *,_IRP *,_LARGE_INTEGER *)

- ea: `0x1400034a0`
- end: `0x140003527`
- name: `?PmPerfCounterStatUpdate@@YAXPEAU_PERF_PRIORITY_COUNTER@@PEAU_IRP@@PEAT_LARGE_INTEGER@@@Z`
- size: `135`
- prototype: `void __fastcall(struct _PERF_PRIORITY_COUNTER *, struct _IRP *, union _LARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400021c0`

## callees

- `0x1400034a0`

## pseudocode

```c
void __fastcall PmPerfCounterStatUpdate(struct _PERF_PRIORITY_COUNTER *a1, struct _IRP *a2, union _LARGE_INTEGER *a3)
{
  UCHAR MajorFunction; // cl

  MajorFunction = a2->Tail.Overlay.CurrentStackLocation->MajorFunction;
  switch ( MajorFunction )
  {
    case 3u:
      *(_QWORD *)a1 += a2->IoStatus.Information;
      ++*((_DWORD *)a1 + 12);
      *((_QWORD *)a1 + 2) += a3->QuadPart;
      break;
    case 4u:
      *((_QWORD *)a1 + 1) += a2->IoStatus.Information;
      ++*((_DWORD *)a1 + 13);
      *((_QWORD *)a1 + 3) += a3->QuadPart;
      break;
    case 9u:
      ++*((_DWORD *)a1 + 14);
      *((_QWORD *)a1 + 4) += a3->QuadPart;
      break;
  }
  if ( (a2->Flags & 8) != 0 )
    ++*((_DWORD *)a1 + 15);
}

```

## disassembly

```asm
0x1400034a0  mov     rax, [rdx+0B8h]
0x1400034a7  mov     r10, rcx
0x1400034aa  movzx   ecx, byte ptr [rax]
0x1400034ad  cmp     cl, 3
0x1400034b0  jnz     short loc_1400034D3
0x1400034b2  mov     r9, [r10]
0x1400034b5  add     r9, [rdx+38h]
0x1400034b9  mov     [r10], r9
0x1400034bc  mov     eax, [r10+30h]
0x1400034c0  inc     eax
0x1400034c2  mov     [r10+30h], eax
0x1400034c6  mov     rcx, [r10+10h]
0x1400034ca  add     rcx, [r8]
0x1400034cd  mov     [r10+10h], rcx
0x1400034d1  jmp     short loc_140003515
0x1400034d3  cmp     cl, 4
0x1400034d6  jnz     short loc_1400034FB
0x1400034d8  mov     rcx, [r10+8]
0x1400034dc  add     rcx, [rdx+38h]
0x1400034e0  mov     [r10+8], rcx
0x1400034e4  mov     eax, [r10+34h]
0x1400034e8  inc     eax
0x1400034ea  mov     [r10+34h], eax
0x1400034ee  mov     rcx, [r10+18h]
0x1400034f2  add     rcx, [r8]
0x1400034f5  mov     [r10+18h], rcx
0x1400034f9  jmp     short loc_140003515
0x1400034fb  cmp     cl, 9
0x1400034fe  jnz     short loc_140003515
0x140003500  mov     eax, [r10+38h]
0x140003504  inc     eax
0x140003506  mov     [r10+38h], eax
0x14000350a  mov     rcx, [r10+20h]
0x14000350e  add     rcx, [r8]
0x140003511  mov     [r10+20h], rcx
0x140003515  mov     eax, [rdx+10h]
0x140003518  test    al, 8
0x14000351a  jz      short locret_140003526
0x14000351c  mov     eax, [r10+3Ch]
0x140003520  inc     eax
0x140003522  mov     [r10+3Ch], eax
0x140003526  retn
```
