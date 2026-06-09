# FatMultiAsyncCompletionRoutine

- ea: `0x140001f80`
- end: `0x140002156`
- name: `FatMultiAsyncCompletionRoutine`
- size: `470`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140001f80`
- `0x140005288`
- `0x140007320`
- `0x140007440`
- `0x14000c680`
- `0x140047d24`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x140001fe8`
- `ntoskrnl!IoFreeMdl` at `0x1400020e8`
- `ntoskrnl!IoFreeMdl` at `0x140001fe8`
- `ntoskrnl!IoFreeMdl` at `0x1400020e8`
- `ntoskrnl!KeSetEvent` at `0x140002085`
- `ntoskrnl!KeSetEvent` at `0x140002085`
- `ntoskrnl!IoFreeIrp` at `0x1400020f7`
- `ntoskrnl!IoFreeIrp` at `0x1400020f7`
- `ntoskrnl!ExInterlockedAddUlong` at `0x140002068`
- `ntoskrnl!ExInterlockedAddUlong` at `0x140002068`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14000209e`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400020b7`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14000209e`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400020b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400020d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400020d3`

## pseudocode

```c
__int64 __fastcall FatMultiAsyncCompletionRoutine(__int64 a1, __int64 a2, volatile signed __int32 *a3)
{
  unsigned int v5; // r14d
  __int64 v6; // rsi
  int *v7; // rdi
  bool v8; // r15
  __int64 v9; // rcx
  int v10; // edx
  __int64 v11; // rcx
  struct _ERESOURCE *v12; // rcx
  struct _ERESOURCE *v13; // rcx
  __int64 v14; // rdx
  _DWORD *IrpContext; // rbx

  v5 = 0;
  v6 = *((_QWORD *)a3 + 1);
  v7 = (int *)(v6 + 48);
  if ( *(int *)(a2 + 48) < 0 )
    *(_OWORD *)v7 = *(_OWORD *)(a2 + 48);
  if ( _InterlockedExchangeAdd(a3 + 1, 0xFFFFFFFF) == 1 )
  {
    v8 = 0;
    v9 = *((_QWORD *)a3 + 2);
    if ( v9 )
    {
      if ( *v7 >= 0 )
        memset(*(void **)(v9 + 24), 0, *(unsigned int *)(v9 + 40));
      IoFreeMdl(*((PMDL *)a3 + 2));
      *((_QWORD *)a3 + 2) = 0;
    }
    if ( *v7 < 0 )
    {
      if ( (*a3 & 0x10) == 0 )
        v8 = *v7 == -2147483626;
    }
    else
    {
      *(_QWORD *)(v6 + 56) = *((unsigned int *)a3 + 12);
      if ( (*(_DWORD *)(v6 + 16) & 2) == 0 )
      {
        v10 = 0x80000;
        if ( **(_BYTE **)(v6 + 184) != 3 )
          v10 = 4096;
        *(_DWORD *)(*((_QWORD *)a3 + 7) + 80LL) |= v10;
      }
    }
    v11 = *((_QWORD *)a3 + 8);
    if ( v11 && ExInterlockedAddUlong((PULONG)(v11 + 24), 0xFFFFFFFF, &SpinLock) == 1 )
      KeSetEvent(*(PRKEVENT *)(*((_QWORD *)a3 + 8) + 32LL), 0, 0);
    v12 = (struct _ERESOURCE *)*((_QWORD *)a3 + 3);
    if ( v12 )
      ExReleaseResourceForThreadLite(v12, *((_QWORD *)a3 + 5));
    v13 = (struct _ERESOURCE *)*((_QWORD *)a3 + 4);
    if ( v13 )
      ExReleaseResourceForThreadLite(v13, *((_QWORD *)a3 + 5));
    *(_BYTE *)(*(_QWORD *)(v6 + 184) + 3LL) |= 1u;
    ExFreePoolWithTag((PVOID)a3, 0);
    if ( v8 )
    {
      IoFreeMdl(*(PMDL *)(a2 + 8));
      IoFreeIrp((PIRP)a2);
      *(_DWORD *)(v6 + 24) = 0;
      LOBYTE(v14) = 1;
      IrpContext = (_DWORD *)FatCreateIrpContext(v6, v14);
      IrpContext[17] &= ~0x10u;
      FatPrePostIrp(IrpContext, (PIRP)v6);
      FatAddToWorkque(IrpContext, (PVOID)v6);
      return (unsigned int)-1073741802;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x140001f80  push    rbx
0x140001f82  push    rsi
0x140001f83  push    rdi
0x140001f84  push    r13
0x140001f86  push    r14
0x140001f88  push    r15
0x140001f8a  sub     rsp, 38h
0x140001f8e  mov     rbx, r8
0x140001f91  mov     r13, rdx
0x140001f94  xor     r14d, r14d
0x140001f97  mov     [rsp+68h+var_48], r14d
0x140001f9c  mov     rsi, [r8+8]
0x140001fa0  lea     rdi, [rsi+30h]
0x140001fa4  cmp     [rdx+30h], r14d
0x140001fa8  jge     short loc_140001FB2
0x140001faa  movups  xmm0, xmmword ptr [rdx+30h]
0x140001fae  movdqu  xmmword ptr [rdi], xmm0
0x140001fb2  or      eax, 0FFFFFFFFh
0x140001fb5  lock xadd [r8+4], eax
0x140001fbb  cmp     eax, 1
0x140001fbe  jnz     loc_140002144
0x140001fc4  xor     r15b, r15b
0x140001fc7  mov     rcx, [r8+10h]
0x140001fcb  test    rcx, rcx
0x140001fce  jz      short loc_140001FF8
0x140001fd0  cmp     [rdi], r14d
0x140001fd3  jl      short loc_140001FE4
0x140001fd5  mov     r8d, [rcx+28h]; Size
0x140001fd9  xor     edx, edx; Val
0x140001fdb  mov     rcx, [rcx+18h]; void *
0x140001fdf  call    memset
0x140001fe4  mov     rcx, [rbx+10h]; Mdl
0x140001fe8  call    cs:__imp_IoFreeMdl
0x140001fef  nop     dword ptr [rax+rax+00h]
0x140001ff4  mov     [rbx+10h], r14
0x140001ff8  mov     ecx, [rdi]
0x140001ffa  test    ecx, ecx
0x140001ffc  js      short loc_140002031
0x140001ffe  mov     eax, [rbx+30h]
0x140002001  mov     [rsi+38h], rax
0x140002005  mov     eax, [rsi+10h]
0x140002008  test    al, 2
0x14000200a  jnz     short loc_14000204C
0x14000200c  mov     rax, [rsi+0B8h]
0x140002013  mov     edx, 80000h
0x140002018  mov     ecx, 1000h
0x14000201d  cmp     byte ptr [rax], 3
0x140002020  cmovnz  edx, ecx
0x140002023  mov     rcx, [rbx+38h]
0x140002027  mov     eax, [rcx+50h]
0x14000202a  or      edx, eax
0x14000202c  mov     [rcx+50h], edx
0x14000202f  jmp     short loc_14000204C
0x140002031  mov     eax, [rbx]
0x140002033  test    al, 10h
0x140002035  jnz     short loc_14000204C
0x140002037  movzx   r15d, r15b
0x14000203b  mov     edi, 1
0x140002040  cmp     ecx, 80000016h
0x140002046  cmovz   r15d, edi
0x14000204a  jmp     short loc_140002051
0x14000204c  mov     edi, 1
0x140002051  mov     rcx, [rbx+40h]
0x140002055  test    rcx, rcx
0x140002058  jz      short loc_140002091
0x14000205a  add     rcx, 18h; Addend
0x14000205e  lea     r8, SpinLock; Lock
0x140002065  or      edx, 0FFFFFFFFh; Increment
0x140002068  call    cs:__imp_ExInterlockedAddUlong
0x14000206f  nop     dword ptr [rax+rax+00h]
0x140002074  cmp     eax, edi
0x140002076  jnz     short loc_140002091
0x140002078  mov     rcx, [rbx+40h]
0x14000207c  xor     r8d, r8d; Wait
0x14000207f  xor     edx, edx; Increment
0x140002081  mov     rcx, [rcx+20h]; Event
0x140002085  call    cs:__imp_KeSetEvent
0x14000208c  nop     dword ptr [rax+rax+00h]
0x140002091  mov     rcx, [rbx+18h]; Resource
0x140002095  test    rcx, rcx
0x140002098  jz      short loc_1400020AA
0x14000209a  mov     rdx, [rbx+28h]; ResourceThreadId
0x14000209e  call    cs:__imp_ExReleaseResourceForThreadLite
0x1400020a5  nop     dword ptr [rax+rax+00h]
0x1400020aa  mov     rcx, [rbx+20h]; Resource
0x1400020ae  test    rcx, rcx
0x1400020b1  jz      short loc_1400020C3
0x1400020b3  mov     rdx, [rbx+28h]; ResourceThreadId
0x1400020b7  call    cs:__imp_ExReleaseResourceForThreadLite
0x1400020be  nop     dword ptr [rax+rax+00h]
0x1400020c3  mov     rax, [rsi+0B8h]
0x1400020ca  or      [rax+3], dil
0x1400020ce  xor     edx, edx; Tag
0x1400020d0  mov     rcx, rbx; P
0x1400020d3  call    cs:__imp_ExFreePoolWithTag
0x1400020da  nop     dword ptr [rax+rax+00h]
0x1400020df  test    r15b, r15b
0x1400020e2  jz      short loc_140002144
0x1400020e4  mov     rcx, [r13+8]; Mdl
0x1400020e8  call    cs:__imp_IoFreeMdl
0x1400020ef  nop     dword ptr [rax+rax+00h]
0x1400020f4  mov     rcx, r13; Irp
0x1400020f7  call    cs:__imp_IoFreeIrp
0x1400020fe  nop     dword ptr [rax+rax+00h]
0x140002103  mov     dword ptr [rsi+18h], 0
0x14000210a  mov     dl, dil
0x14000210d  mov     rcx, rsi
0x140002110  call    FatCreateIrpContext
0x140002115  mov     rbx, rax
0x140002118  and     dword ptr [rax+44h], 0FFFFFFEFh
0x14000211c  mov     rdx, rsi; Irp
0x14000211f  mov     rcx, rax; Context
0x140002122  call    FatPrePostIrp
0x140002127  mov     rdx, rsi; Context2
0x14000212a  mov     rcx, rbx; Context1
0x14000212d  call    FatAddToWorkque
0x140002132  mov     r14d, 0C0000016h
0x140002138  mov     [rsp+68h+var_48], r14d
0x14000213d  jmp     short loc_140002144
0x14000213f  mov     r14d, [rsp+68h+var_48]
0x140002144  mov     eax, r14d
0x140002147  add     rsp, 38h
0x14000214b  pop     r15
0x14000214d  pop     r14
0x14000214f  pop     r13
0x140002151  pop     rdi
0x140002152  pop     rsi
0x140002153  pop     rbx
0x140002154  retn
0x14000ccd8  push    rbp
0x14000ccda  sub     rsp, 20h
0x14000ccde  mov     rbp, rdx
0x14000cce1  mov     rdx, rcx
0x14000cce4  xor     ecx, ecx
0x14000cce6  call    FatExceptionFilter
0x14000cceb  nop
0x14000ccec  add     rsp, 20h
0x14000ccf0  pop     rbp
0x14000ccf1  retn
```
