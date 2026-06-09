# DfscDeleteLinkedConnectionWorker

- ea: `0x140014810`
- end: `0x140014906`
- name: `DfscDeleteLinkedConnectionWorker`
- size: `246`
- prototype: `void __fastcall(char *StartContext)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x140005520`
- `0x140006380`
- `0x140014810`
- `0x1400170a8`
- `0x140017294`
- `0x14002545c`

## import_xrefs

- `ntoskrnl!PsTerminateSystemThread` at `0x1400148e9`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400148e9`
- `ntoskrnl!KeSetEvent` at `0x1400148db`
- `ntoskrnl!KeSetEvent` at `0x1400148db`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400148b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400148b1`
- `ntoskrnl!ExAllocatePool2` at `0x14001484a`
- `ntoskrnl!ExAllocatePool2` at `0x14001484a`

## pseudocode

```c
void __fastcall DfscDeleteLinkedConnectionWorker(char *StartContext)
{
  int v2; // ebx
  _DWORD *Pool2; // rax
  _DWORD *v4; // rdi
  int v5; // [rsp+50h] [rbp+8h] BYREF

  v2 = DfscImpersonateLinkedToken(*(void ***)StartContext);
  if ( v2 < 0 )
  {
    if ( v2 == -1073741788 )
      v2 = 0;
  }
  else
  {
    v5 = 528;
    Pool2 = (_DWORD *)ExAllocatePool2(258, 528, 1279485508);
    v4 = Pool2;
    if ( Pool2 )
    {
      memset(Pool2, 0, 0x210u);
      v2 = DfscDeleteNetUseConnection(
             *((_QWORD *)StartContext + 8),
             *((_QWORD *)StartContext + 6),
             *((_QWORD *)StartContext + 5),
             *((_DWORD *)StartContext + 14),
             v4,
             &v5,
             1);
      if ( v2 >= 0 )
        DfscCredDelete(v4 + 1, (unsigned int)*v4);
      ExFreePoolWithTag(v4, 0);
    }
    else
    {
      v2 = -1073741670;
    }
    DfscRevert();
  }
  *((_DWORD *)StartContext + 8) = v2;
  KeSetEvent((PRKEVENT)(StartContext + 8), 0, 0);
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x140014810  mov     [rsp+arg_8], rbx
0x140014815  mov     [rsp+arg_10], rsi
0x14001481a  push    rdi
0x14001481b  sub     rsp, 40h
0x14001481f  mov     rsi, rcx
0x140014822  mov     rcx, [rcx]
0x140014825  call    DfscImpersonateLinkedToken
0x14001482a  mov     ebx, eax
0x14001482c  test    eax, eax
0x14001482e  js      loc_1400148C4
0x140014834  mov     ebx, 210h
0x140014839  mov     r8d, 4C436644h
0x14001483f  mov     edx, ebx
0x140014841  mov     [rsp+48h+arg_0], ebx
0x140014845  mov     ecx, 102h
0x14001484a  call    cs:__imp_ExAllocatePool2
0x140014851  nop     dword ptr [rax+rax+00h]
0x140014856  mov     rdi, rax
0x140014859  test    rax, rax
0x14001485c  jnz     short loc_140014865
0x14001485e  mov     ebx, 0C000009Ah
0x140014863  jmp     short loc_1400148BD
0x140014865  mov     r8, rbx; Size
0x140014868  xor     edx, edx; Val
0x14001486a  mov     rcx, rdi; void *
0x14001486d  call    memset
0x140014872  mov     r9d, [rsi+38h]
0x140014876  lea     rax, [rsp+48h+arg_0]
0x14001487b  mov     r8, [rsi+28h]
0x14001487f  mov     rdx, [rsi+30h]
0x140014883  mov     rcx, [rsi+40h]
0x140014887  mov     [rsp+48h+var_18], 1
0x14001488c  mov     [rsp+48h+var_20], rax
0x140014891  mov     [rsp+48h+var_28], rdi
0x140014896  call    DfscDeleteNetUseConnection
0x14001489b  mov     ebx, eax
0x14001489d  test    eax, eax
0x14001489f  js      short loc_1400148AC
0x1400148a1  mov     edx, [rdi]
0x1400148a3  lea     rcx, [rdi+4]
0x1400148a7  call    DfscCredDelete
0x1400148ac  xor     edx, edx; Tag
0x1400148ae  mov     rcx, rdi; P
0x1400148b1  call    cs:__imp_ExFreePoolWithTag
0x1400148b8  nop     dword ptr [rax+rax+00h]
0x1400148bd  call    DfscRevert
0x1400148c2  jmp     short loc_1400148CF
0x1400148c4  xor     eax, eax
0x1400148c6  cmp     ebx, 0C0000024h
0x1400148cc  cmovz   ebx, eax
0x1400148cf  lea     rcx, [rsi+8]; Event
0x1400148d3  mov     [rsi+20h], ebx
0x1400148d6  xor     r8d, r8d; Wait
0x1400148d9  xor     edx, edx; Increment
0x1400148db  call    cs:__imp_KeSetEvent
0x1400148e2  nop     dword ptr [rax+rax+00h]
0x1400148e7  xor     ecx, ecx; ExitStatus
0x1400148e9  call    cs:__imp_PsTerminateSystemThread
0x1400148f0  nop     dword ptr [rax+rax+00h]
0x1400148f5  mov     rbx, [rsp+48h+arg_8]
0x1400148fa  mov     rsi, [rsp+48h+arg_10]
0x1400148ff  add     rsp, 40h
0x140014903  pop     rdi
0x140014904  retn
```
