# FatFsdCreate

- ea: `0x14002a4b0`
- end: `0x14002a60b`
- name: `FatFsdCreate`
- size: `347`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140005288`
- `0x140028a14`
- `0x14002a4b0`
- `0x14002c598`
- `0x140038eb4`
- `0x140039550`
- `0x14003960c`
- `0x140047d24`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002a5ea`
- `ntoskrnl!IofCompleteRequest` at `0x14002a5ea`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002a4f6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002a4f6`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14002a568`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14002a568`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002a574`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002a574`

## pseudocode

```c
__int64 __fastcall FatFsdCreate(__int64 a1, IRP *a2)
{
  _DWORD *IrpContext; // r14
  unsigned int v5; // ebx
  __int64 v6; // r9
  int v7; // eax
  char IsIrpTopLevel; // [rsp+70h] [rbp+18h]

  if ( a1 == qword_140017CC8 || a1 == qword_140017CD0 )
  {
    a2->IoStatus.Status = 0;
    a2->IoStatus.Information = 1;
    IofCompleteRequest(a2, 1);
    return 0;
  }
  else
  {
    KeEnterCriticalRegion();
    IsIrpTopLevel = FatIsIrpTopLevel(a2);
    IrpContext = FatCreateIrpContext(a2, 1);
    v5 = FatCommonCreateOnNewStack(IrpContext, a2);
    if ( IsIrpTopLevel )
      IoSetTopLevelIrp(0);
    KeLeaveCriticalRegion();
    if ( v5 != 259 && (IrpContext[17] & 0x8000) != 0 )
    {
      v7 = FatPostProcessEfsCreate((__int64)IrpContext, a2, a1, v5);
      IrpContext[17] |= 0x10000u;
      if ( v7 < 0 && (v5 & 0x80000000) == 0 )
        v5 = v7;
    }
    if ( v5 != 259 )
      FatCompleteRequest_Real(IrpContext, a2, v5, v6);
    return v5;
  }
}

```

## disassembly

```asm
0x14002a4b0  mov     rax, rsp
0x14002a4b3  mov     [rax+20h], rbx
0x14002a4b7  mov     [rax+10h], rdx
0x14002a4bb  mov     [rax+8], rcx
0x14002a4bf  push    rsi
0x14002a4c0  push    rdi
0x14002a4c1  push    r12
0x14002a4c3  push    r14
0x14002a4c5  push    r15
0x14002a4c7  sub     rsp, 30h
0x14002a4cb  mov     rdi, rdx
0x14002a4ce  mov     rsi, rcx
0x14002a4d1  cmp     rcx, cs:qword_140017CC8
0x14002a4d8  jz      loc_14002A5D6
0x14002a4de  cmp     rcx, cs:qword_140017CD0
0x14002a4e5  jz      loc_14002A5D6
0x14002a4eb  mov     qword ptr [rax-30h], 0
0x14002a4f3  xor     r12b, r12b
0x14002a4f6  call    cs:__imp_KeEnterCriticalRegion
0x14002a4fd  nop     dword ptr [rax+rax+00h]
0x14002a502  mov     rcx, rdi; Irp
0x14002a505  call    FatIsIrpTopLevel
0x14002a50a  mov     r15b, al
0x14002a50d  mov     [rsp+58h+arg_10], al
0x14002a511  mov     dl, 1
0x14002a513  mov     rcx, rdi
0x14002a516  call    FatCreateIrpContext
0x14002a51b  mov     r14, rax
0x14002a51e  mov     [rsp+58h+Entry], rax
0x14002a523  mov     rdx, rdi
0x14002a526  mov     rcx, rax
0x14002a529  call    FatCommonCreateOnNewStack
0x14002a52e  mov     ebx, eax
0x14002a530  mov     [rsp+58h+var_38], eax
0x14002a534  jmp     short loc_14002A561
0x14002a536  mov     r8d, eax
0x14002a539  mov     rdi, [rsp+58h+Irp]
0x14002a53e  mov     rdx, rdi; Irp
0x14002a541  mov     r14, [rsp+58h+Entry]
0x14002a546  mov     rcx, r14; Entry
0x14002a549  call    FatProcessException
0x14002a54e  mov     ebx, eax
0x14002a550  mov     [rsp+58h+var_38], eax
0x14002a554  mov     r12b, 1
0x14002a557  mov     rsi, [rsp+58h+arg_0]
0x14002a55c  mov     r15b, [rsp+58h+arg_10]
0x14002a561  test    r15b, r15b
0x14002a564  jz      short loc_14002A574
0x14002a566  xor     ecx, ecx; Irp
0x14002a568  call    cs:__imp_IoSetTopLevelIrp
0x14002a56f  nop     dword ptr [rax+rax+00h]
0x14002a574  call    cs:__imp_KeLeaveCriticalRegion
0x14002a57b  nop     dword ptr [rax+rax+00h]
0x14002a580  test    r12b, r12b
0x14002a583  jnz     short loc_14002A5D2
0x14002a585  cmp     ebx, 103h
0x14002a58b  jz      short loc_14002A5B7
0x14002a58d  test    dword ptr [r14+44h], 8000h
0x14002a595  jz      short loc_14002A5B7
0x14002a597  mov     r9d, ebx
0x14002a59a  mov     r8, rsi
0x14002a59d  mov     rdx, rdi
0x14002a5a0  mov     rcx, r14
0x14002a5a3  call    FatPostProcessEfsCreate
0x14002a5a8  bts     dword ptr [r14+44h], 10h
0x14002a5ae  test    eax, eax
0x14002a5b0  jns     short loc_14002A5B7
0x14002a5b2  test    ebx, ebx
0x14002a5b4  cmovns  ebx, eax
0x14002a5b7  test    r12b, r12b
0x14002a5ba  jnz     short loc_14002A5D2
0x14002a5bc  cmp     ebx, 103h
0x14002a5c2  jz      short loc_14002A5D2
0x14002a5c4  mov     r8d, ebx
0x14002a5c7  mov     rdx, rdi; Irp
0x14002a5ca  mov     rcx, r14; Entry
0x14002a5cd  call    FatCompleteRequest_Real
0x14002a5d2  mov     eax, ebx
0x14002a5d4  jmp     short loc_14002A5F8
0x14002a5d6  mov     dword ptr [rdx+30h], 0
0x14002a5dd  mov     qword ptr [rdx+38h], 1
0x14002a5e5  mov     dl, 1; PriorityBoost
0x14002a5e7  mov     rcx, rdi; Irp
0x14002a5ea  call    cs:__imp_IofCompleteRequest
0x14002a5f1  nop     dword ptr [rax+rax+00h]
0x14002a5f6  xor     eax, eax
0x14002a5f8  mov     rbx, [rsp+58h+arg_18]
0x14002a5fd  add     rsp, 30h
0x14002a601  pop     r15
0x14002a603  pop     r14
0x14002a605  pop     r12
0x14002a607  pop     rdi
0x14002a608  pop     rsi
0x14002a609  retn
0x14005b9b6  push    rbp
0x14005b9b8  sub     rsp, 20h
0x14005b9bc  mov     rbp, rdx
0x14005b9bf  mov     rdx, rcx
0x14005b9c2  mov     rcx, [rbp+28h]
0x14005b9c6  call    FatExceptionFilter
0x14005b9cb  nop
0x14005b9cc  add     rsp, 20h
0x14005b9d0  pop     rbp
0x14005b9d1  retn
```
