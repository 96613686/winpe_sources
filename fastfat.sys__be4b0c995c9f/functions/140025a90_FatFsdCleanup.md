# FatFsdCleanup

- ea: `0x140025a90`
- end: `0x140025b70`
- name: `FatFsdCleanup`
- size: `224`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140005288`
- `0x140024bd4`
- `0x140025a90`
- `0x140039550`
- `0x14003960c`
- `0x140047d24`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140025b56`
- `ntoskrnl!IofCompleteRequest` at `0x140025b56`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140025ac5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140025ac5`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140025b26`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140025b26`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025b32`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025b32`

## pseudocode

```c
__int64 __fastcall FatFsdCleanup(__int64 a1, IRP *a2)
{
  unsigned int v3; // ebx
  _DWORD *Entry; // [rsp+28h] [rbp-10h]
  char IsIrpTopLevel; // [rsp+40h] [rbp+8h]

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
    Entry = FatCreateIrpContext(a2, 1);
    v3 = FatCommonCleanup(Entry, a2);
    if ( IsIrpTopLevel )
      IoSetTopLevelIrp(0);
    KeLeaveCriticalRegion();
    return v3;
  }
}

```

## disassembly

```asm
0x140025a90  mov     [rsp+arg_10], rbx
0x140025a95  mov     [rsp+Irp], rdx
0x140025a9a  push    rdi
0x140025a9b  sub     rsp, 30h
0x140025a9f  mov     rbx, rdx
0x140025aa2  cmp     rcx, cs:qword_140017CC8
0x140025aa9  jz      loc_140025B42
0x140025aaf  cmp     rcx, cs:qword_140017CD0
0x140025ab6  jz      loc_140025B42
0x140025abc  mov     [rsp+38h+Entry], 0
0x140025ac5  call    cs:__imp_KeEnterCriticalRegion
0x140025acc  nop     dword ptr [rax+rax+00h]
0x140025ad1  mov     rcx, rbx; Irp
0x140025ad4  call    FatIsIrpTopLevel
0x140025ad9  mov     dil, al
0x140025adc  mov     [rsp+38h+arg_0], al
0x140025ae0  mov     dl, 1
0x140025ae2  mov     rcx, rbx
0x140025ae5  call    FatCreateIrpContext
0x140025aea  mov     [rsp+38h+Entry], rax
0x140025aef  mov     rdx, rbx; Irp
0x140025af2  mov     rcx, rax; Entry
0x140025af5  call    FatCommonCleanup
0x140025afa  mov     ebx, eax
0x140025afc  mov     [rsp+38h+var_18], eax
0x140025b00  jmp     short loc_140025B1F
0x140025b02  mov     r8d, eax
0x140025b05  mov     rdx, [rsp+38h+Irp]; Irp
0x140025b0a  mov     rcx, [rsp+38h+Entry]; Entry
0x140025b0f  call    FatProcessException
0x140025b14  mov     ebx, eax
0x140025b16  mov     [rsp+38h+var_18], eax
0x140025b1a  mov     dil, [rsp+38h+arg_0]
0x140025b1f  test    dil, dil
0x140025b22  jz      short loc_140025B32
0x140025b24  xor     ecx, ecx; Irp
0x140025b26  call    cs:__imp_IoSetTopLevelIrp
0x140025b2d  nop     dword ptr [rax+rax+00h]
0x140025b32  call    cs:__imp_KeLeaveCriticalRegion
0x140025b39  nop     dword ptr [rax+rax+00h]
0x140025b3e  mov     eax, ebx
0x140025b40  jmp     short loc_140025B64
0x140025b42  mov     dword ptr [rdx+30h], 0
0x140025b49  mov     qword ptr [rdx+38h], 1
0x140025b51  mov     dl, 1; PriorityBoost
0x140025b53  mov     rcx, rbx; Irp
0x140025b56  call    cs:__imp_IofCompleteRequest
0x140025b5d  nop     dword ptr [rax+rax+00h]
0x140025b62  xor     eax, eax
0x140025b64  mov     rbx, [rsp+38h+arg_10]
0x140025b69  add     rsp, 30h
0x140025b6d  pop     rdi
0x140025b6e  retn
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
