# PmUuidCreate(_GUID *)

- ea: `0x1400217e8`
- end: `0x140021843`
- name: `?PmUuidCreate@@YAXPEAU_GUID@@@Z`
- size: `91`
- prototype: `void __fastcall(struct _GUID *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400210a8`
- `0x1400215d0`
- `0x140021738`

## callees

- `0x1400217e8`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x14002180f`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x14002182c`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x14002180f`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x14002182c`
- `ntoskrnl!ExUuidCreate` at `0x1400217f1`
- `ntoskrnl!ExUuidCreate` at `0x1400217f1`

## pseudocode

```c
void __fastcall PmUuidCreate(struct _GUID *a1)
{
  ULONG64 v2; // rax
  unsigned __int64 QpcTimeStamp; // [rsp+38h] [rbp+10h] BYREF

  if ( ExUuidCreate(a1) < 0 )
  {
    QpcTimeStamp = 0;
    v2 = KeQueryUnbiasedInterruptTimePrecise(&QpcTimeStamp);
    QpcTimeStamp = 0;
    *(_QWORD *)&a1->Data1 = v2;
    *(_QWORD *)a1->Data4 = KeQueryUnbiasedInterruptTimePrecise(&QpcTimeStamp);
  }
}

```

## disassembly

```asm
0x1400217e8  push    rbx
0x1400217ea  sub     rsp, 20h
0x1400217ee  mov     rbx, rcx
0x1400217f1  call    cs:__imp_ExUuidCreate
0x1400217f8  nop     dword ptr [rax+rax+00h]
0x1400217fd  test    eax, eax
0x1400217ff  jns     short loc_14002183C
0x140021801  lea     rcx, [rsp+28h+QpcTimeStamp]; QpcTimeStamp
0x140021806  mov     [rsp+28h+QpcTimeStamp], 0
0x14002180f  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x140021816  nop     dword ptr [rax+rax+00h]
0x14002181b  lea     rcx, [rsp+28h+QpcTimeStamp]; QpcTimeStamp
0x140021820  mov     [rsp+28h+QpcTimeStamp], 0
0x140021829  mov     [rbx], rax
0x14002182c  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x140021833  nop     dword ptr [rax+rax+00h]
0x140021838  mov     [rbx+8], rax
0x14002183c  add     rsp, 20h
0x140021840  pop     rbx
0x140021841  retn
```
