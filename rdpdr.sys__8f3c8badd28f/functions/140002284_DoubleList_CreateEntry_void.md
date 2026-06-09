# DoubleList::CreateEntry(void *)

- ea: `0x140002284`
- end: `0x140002316`
- name: `?CreateEntry@DoubleList@@QEAAHPEAX@Z`
- size: `146`
- prototype: `__int64 __fastcall(DoubleList *__hidden this, void *)`
- caller_count: `7`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14001d3f0`
- `0x14001d938`
- `0x1400254c0`
- `0x140027190`
- `0x140027fe0`
- `0x140029c90`
- `0x14002be3c`

## callees

- `0x140002284`
- `0x140006560`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400022a4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400022a4`

## pseudocode

```c
__int64 __fastcall DoubleList::CreateEntry(DoubleList *this, void *a2)
{
  __int64 result; // rax
  DoubleList *v5; // rbx
  DoubleList **v6; // rcx

  result = (__int64)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)((char *)WPP_MAIN_CB.Dpc.SystemArgument1
                                                                             + 64));
  v5 = (DoubleList *)result;
  if ( result )
  {
    *(_QWORD *)(result + 16) = a2;
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 4) + 24LL))((char *)this + 32);
    v6 = (DoubleList **)*((_QWORD *)this + 3);
    if ( *v6 != (DoubleList *)((char *)this + 16) )
      __fastfail(3u);
    *(_QWORD *)v5 = (char *)this + 16;
    *((_QWORD *)v5 + 1) = v6;
    *v6 = v5;
    *((_QWORD *)this + 3) = v5;
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 4) + 32LL))((char *)this + 32);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x140002284  mov     [rsp+arg_0], rbx
0x140002289  mov     [rsp+arg_8], rsi
0x14000228e  push    rdi
0x14000228f  sub     rsp, 20h
0x140002293  mov     rsi, rcx
0x140002296  mov     rdi, rdx
0x140002299  mov     rcx, cs:WPP_MAIN_CB.Dpc.SystemArgument1
0x1400022a0  add     rcx, 40h ; '@'; Lookaside
0x1400022a4  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400022ab  nop     dword ptr [rax+rax+00h]
0x1400022b0  mov     rbx, rax
0x1400022b3  test    rax, rax
0x1400022b6  jz      short loc_140002305
0x1400022b8  mov     [rax+10h], rdi
0x1400022bc  lea     rdi, [rsi+20h]
0x1400022c0  mov     rdx, [rdi]
0x1400022c3  mov     rcx, rdi
0x1400022c6  mov     rax, [rdx+18h]
0x1400022ca  call    _guard_dispatch_icall
0x1400022cf  lea     rax, [rsi+10h]
0x1400022d3  mov     rcx, [rax+8]
0x1400022d7  cmp     [rcx], rax
0x1400022da  jz      short loc_1400022E3
0x1400022dc  mov     ecx, 3
0x1400022e1  int     29h; Win8: RtlFailFast(ecx)
0x1400022e3  mov     [rbx], rax
0x1400022e6  mov     [rbx+8], rcx
0x1400022ea  mov     [rcx], rbx
0x1400022ed  mov     rcx, rdi
0x1400022f0  mov     [rax+8], rbx
0x1400022f4  mov     rax, [rdi]
0x1400022f7  mov     rax, [rax+20h]
0x1400022fb  call    _guard_dispatch_icall
0x140002300  mov     eax, 1
0x140002305  mov     rbx, [rsp+28h+arg_0]
0x14000230a  mov     rsi, [rsp+28h+arg_8]
0x14000230f  add     rsp, 20h
0x140002313  pop     rdi
0x140002314  retn
```
