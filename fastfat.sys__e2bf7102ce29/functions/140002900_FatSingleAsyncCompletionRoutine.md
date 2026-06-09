# FatSingleAsyncCompletionRoutine

- ea: `0x140002900`
- end: `0x140002a86`
- name: `FatSingleAsyncCompletionRoutine`
- size: `390`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140002900`
- `0x140005288`
- `0x140007320`
- `0x140007440`
- `0x14000c680`
- `0x140047d24`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14000293f`
- `ntoskrnl!IoFreeMdl` at `0x14000293f`
- `ntoskrnl!KeSetEvent` at `0x1400029dd`
- `ntoskrnl!KeSetEvent` at `0x1400029dd`
- `ntoskrnl!ExInterlockedAddUlong` at `0x1400029c0`
- `ntoskrnl!ExInterlockedAddUlong` at `0x1400029c0`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400029f6`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140002a0f`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400029f6`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140002a0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002a2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002a2b`

## pseudocode

```c
__int64 __fastcall FatSingleAsyncCompletionRoutine(__int64 a1, __int64 a2, unsigned int *a3)
{
  unsigned int v5; // r14d
  bool v6; // r15
  __int64 v7; // rcx
  int v8; // ecx
  int v9; // edx
  __int64 v10; // rcx
  struct _ERESOURCE *v11; // rcx
  struct _ERESOURCE *v12; // rcx
  __int64 v13; // rdx
  _DWORD *IrpContext; // rbx

  v5 = 0;
  v6 = 0;
  v7 = *((_QWORD *)a3 + 2);
  if ( v7 )
  {
    if ( *(int *)(a2 + 48) >= 0 )
      memset(*(void **)(v7 + 24), 0, *(unsigned int *)(v7 + 40));
    IoFreeMdl(*((PMDL *)a3 + 2));
    *((_QWORD *)a3 + 2) = 0;
  }
  v8 = *(_DWORD *)(a2 + 48);
  if ( v8 < 0 )
  {
    if ( (*a3 & 0x10) == 0 )
      v6 = v8 == -2147483626;
  }
  else
  {
    *(_QWORD *)(a2 + 56) = a3[12];
    if ( (*(_DWORD *)(a2 + 16) & 2) == 0 )
    {
      v9 = 0x80000;
      if ( **(_BYTE **)(a2 + 184) != 3 )
        v9 = 4096;
      *(_DWORD *)(*((_QWORD *)a3 + 7) + 80LL) |= v9;
    }
  }
  v10 = *((_QWORD *)a3 + 8);
  if ( v10 && ExInterlockedAddUlong((PULONG)(v10 + 24), 0xFFFFFFFF, &SpinLock) == 1 )
    KeSetEvent(*(PRKEVENT *)(*((_QWORD *)a3 + 8) + 32LL), 0, 0);
  v11 = (struct _ERESOURCE *)*((_QWORD *)a3 + 3);
  if ( v11 )
    ExReleaseResourceForThreadLite(v11, *((_QWORD *)a3 + 5));
  v12 = (struct _ERESOURCE *)*((_QWORD *)a3 + 4);
  if ( v12 )
    ExReleaseResourceForThreadLite(v12, *((_QWORD *)a3 + 5));
  *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  ExFreePoolWithTag(a3, 0);
  if ( v6 )
  {
    LOBYTE(v13) = 1;
    IrpContext = (_DWORD *)FatCreateIrpContext(a2, v13);
    IrpContext[17] &= ~0x10u;
    FatPrePostIrp(IrpContext, (PIRP)a2);
    FatAddToWorkque(IrpContext, (PVOID)a2);
    return (unsigned int)-1073741802;
  }
  return v5;
}

```

## disassembly

```asm
0x140002900  push    rbx
0x140002902  push    rsi
0x140002903  push    rdi
0x140002904  push    r14
0x140002906  push    r15
0x140002908  sub     rsp, 30h
0x14000290c  mov     rbx, r8
0x14000290f  mov     rdi, rdx
0x140002912  xor     r14d, r14d
0x140002915  mov     [rsp+58h+var_38], r14d
0x14000291a  xor     r15b, r15b
0x14000291d  mov     rcx, [r8+10h]
0x140002921  test    rcx, rcx
0x140002924  jz      short loc_14000294F
0x140002926  cmp     [rdx+30h], r14d
0x14000292a  jl      short loc_14000293B
0x14000292c  mov     r8d, [rcx+28h]; Size
0x140002930  xor     edx, edx; Val
0x140002932  mov     rcx, [rcx+18h]; void *
0x140002936  call    memset
0x14000293b  mov     rcx, [rbx+10h]; Mdl
0x14000293f  call    cs:__imp_IoFreeMdl
0x140002946  nop     dword ptr [rax+rax+00h]
0x14000294b  mov     [rbx+10h], r14
0x14000294f  mov     ecx, [rdi+30h]
0x140002952  test    ecx, ecx
0x140002954  js      short loc_140002989
0x140002956  mov     eax, [rbx+30h]
0x140002959  mov     [rdi+38h], rax
0x14000295d  mov     eax, [rdi+10h]
0x140002960  test    al, 2
0x140002962  jnz     short loc_1400029A4
0x140002964  mov     rax, [rdi+0B8h]
0x14000296b  mov     edx, 80000h
0x140002970  mov     ecx, 1000h
0x140002975  cmp     byte ptr [rax], 3
0x140002978  cmovnz  edx, ecx
0x14000297b  mov     rcx, [rbx+38h]
0x14000297f  mov     eax, [rcx+50h]
0x140002982  or      edx, eax
0x140002984  mov     [rcx+50h], edx
0x140002987  jmp     short loc_1400029A4
0x140002989  mov     eax, [rbx]
0x14000298b  test    al, 10h
0x14000298d  jnz     short loc_1400029A4
0x14000298f  movzx   r15d, r15b
0x140002993  mov     esi, 1
0x140002998  cmp     ecx, 80000016h
0x14000299e  cmovz   r15d, esi
0x1400029a2  jmp     short loc_1400029A9
0x1400029a4  mov     esi, 1
0x1400029a9  mov     rcx, [rbx+40h]
0x1400029ad  test    rcx, rcx
0x1400029b0  jz      short loc_1400029E9
0x1400029b2  add     rcx, 18h; Addend
0x1400029b6  lea     r8, SpinLock; Lock
0x1400029bd  or      edx, 0FFFFFFFFh; Increment
0x1400029c0  call    cs:__imp_ExInterlockedAddUlong
0x1400029c7  nop     dword ptr [rax+rax+00h]
0x1400029cc  cmp     eax, esi
0x1400029ce  jnz     short loc_1400029E9
0x1400029d0  mov     rcx, [rbx+40h]
0x1400029d4  xor     r8d, r8d; Wait
0x1400029d7  xor     edx, edx; Increment
0x1400029d9  mov     rcx, [rcx+20h]; Event
0x1400029dd  call    cs:__imp_KeSetEvent
0x1400029e4  nop     dword ptr [rax+rax+00h]
0x1400029e9  mov     rcx, [rbx+18h]; Resource
0x1400029ed  test    rcx, rcx
0x1400029f0  jz      short loc_140002A02
0x1400029f2  mov     rdx, [rbx+28h]; ResourceThreadId
0x1400029f6  call    cs:__imp_ExReleaseResourceForThreadLite
0x1400029fd  nop     dword ptr [rax+rax+00h]
0x140002a02  mov     rcx, [rbx+20h]; Resource
0x140002a06  test    rcx, rcx
0x140002a09  jz      short loc_140002A1B
0x140002a0b  mov     rdx, [rbx+28h]; ResourceThreadId
0x140002a0f  call    cs:__imp_ExReleaseResourceForThreadLite
0x140002a16  nop     dword ptr [rax+rax+00h]
0x140002a1b  mov     rax, [rdi+0B8h]
0x140002a22  or      [rax+3], sil
0x140002a26  xor     edx, edx; Tag
0x140002a28  mov     rcx, rbx; P
0x140002a2b  call    cs:__imp_ExFreePoolWithTag
0x140002a32  nop     dword ptr [rax+rax+00h]
0x140002a37  test    r15b, r15b
0x140002a3a  jz      short loc_140002A76
0x140002a3c  mov     dl, sil
0x140002a3f  mov     rcx, rdi
0x140002a42  call    FatCreateIrpContext
0x140002a47  mov     rbx, rax
0x140002a4a  and     dword ptr [rax+44h], 0FFFFFFEFh
0x140002a4e  mov     rdx, rdi; Irp
0x140002a51  mov     rcx, rax; Context
0x140002a54  call    FatPrePostIrp
0x140002a59  mov     rdx, rdi; Context2
0x140002a5c  mov     rcx, rbx; Context1
0x140002a5f  call    FatAddToWorkque
0x140002a64  mov     r14d, 0C0000016h
0x140002a6a  mov     [rsp+58h+var_38], r14d
0x140002a6f  jmp     short loc_140002A76
0x140002a71  mov     r14d, [rsp+58h+var_38]
0x140002a76  mov     eax, r14d
0x140002a79  add     rsp, 30h
0x140002a7d  pop     r15
0x140002a7f  pop     r14
0x140002a81  pop     rdi
0x140002a82  pop     rsi
0x140002a83  pop     rbx
0x140002a84  retn
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
