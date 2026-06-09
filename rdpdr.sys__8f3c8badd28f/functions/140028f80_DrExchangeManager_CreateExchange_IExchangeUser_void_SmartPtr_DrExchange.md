# DrExchangeManager::CreateExchange(IExchangeUser *,void *,SmartPtr<DrExchange> &)

- ea: `0x140028f80`
- end: `0x1400290b2`
- name: `?CreateExchange@DrExchangeManager@@QEAAHPEAVIExchangeUser@@PEAXAEAV?$SmartPtr@VDrExchange@@@@@Z`
- size: `306`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14002d0c0`

## callees

- `0x140001660`
- `0x140001830`
- `0x140001890`
- `0x140028f80`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140028fb2`
- `ntoskrnl!ExAllocatePool2` at `0x140028fb2`
- `ntoskrnl!ExAcquireFastMutex` at `0x140029017`
- `ntoskrnl!ExAcquireFastMutex` at `0x140029017`
- `ntoskrnl!ExReleaseFastMutex` at `0x140029033`
- `ntoskrnl!ExReleaseFastMutex` at `0x140029093`
- `ntoskrnl!ExReleaseFastMutex` at `0x140029033`
- `ntoskrnl!ExReleaseFastMutex` at `0x140029093`
- `rdbss!RxAssociateContextWithMid` at `0x140029067`
- `rdbss!RxAssociateContextWithMid` at `0x140029067`

## pseudocode

```c
__int64 __fastcall DrExchangeManager::CreateExchange(__int64 a1, __int64 a2, __int64 a3, RefCount **a4)
{
  __int64 Pool2; // rax
  RefCount *v9; // rbx
  struct _RX_MID_ATLAS *v10; // rcx
  USHORT NewMid; // [rsp+78h] [rbp+20h] BYREF

  NewMid = 0;
  Pool2 = ExAllocatePool2(64, 56, 2017817156);
  v9 = (RefCount *)Pool2;
  if ( Pool2 )
  {
    *(_BYTE *)(Pool2 + 8) = 1;
    *(_QWORD *)(Pool2 + 12) = 0;
    *(_QWORD *)Pool2 = &DrExchange::`vftable';
    *(_QWORD *)(Pool2 + 32) = a3;
    *(_QWORD *)(Pool2 + 24) = a1;
    *(_QWORD *)(Pool2 + 40) = a2;
    *(_WORD *)(Pool2 + 48) = -1;
  }
  else
  {
    v9 = 0;
  }
  if ( *a4 )
    RefCount::Release(*a4);
  *a4 = v9;
  if ( v9 )
    RefCount::AddRef(v9);
  if ( !*a4 )
    return 0;
  ExAcquireFastMutex(&DrMutex);
  v10 = *(struct _RX_MID_ATLAS **)(a1 + 32);
  if ( !v10 || RxAssociateContextWithMid(v10, *a4, &NewMid) < 0 )
  {
    ExReleaseFastMutex(&DrMutex);
    SmartPtr<VirtualChannel>::operator=(a4, 0);
    return 0;
  }
  *((_WORD *)*a4 + 24) = NewMid;
  RefCount::AddRef(*a4);
  ExReleaseFastMutex(&DrMutex);
  return 1;
}

```

## disassembly

```asm
0x140028f80  push    rbx
0x140028f82  push    rbp
0x140028f83  push    rsi
0x140028f84  push    rdi
0x140028f85  push    r14
0x140028f87  push    r15
0x140028f89  sub     rsp, 28h
0x140028f8d  mov     rbp, r8
0x140028f90  mov     r14, rdx
0x140028f93  mov     rsi, rcx
0x140028f96  xor     r15d, r15d
0x140028f99  mov     edx, 38h ; '8'
0x140028f9e  mov     [rsp+58h+NewMid], r15w
0x140028fa4  mov     ecx, 40h ; '@'
0x140028fa9  mov     r8d, 78457244h
0x140028faf  mov     rdi, r9
0x140028fb2  call    cs:__imp_ExAllocatePool2
0x140028fb9  nop     dword ptr [rax+rax+00h]
0x140028fbe  mov     rbx, rax
0x140028fc1  test    rax, rax
0x140028fc4  jz      loc_14002905A
0x140028fca  mov     byte ptr [rax+8], 1
0x140028fce  mov     [rax+0Ch], r15
0x140028fd2  lea     rax, ??_7DrExchange@@6B@; const DrExchange::`vftable'
0x140028fd9  mov     [rbx], rax
0x140028fdc  mov     [rbx+20h], rbp
0x140028fe0  mov     [rbx+18h], rsi
0x140028fe4  mov     [rbx+28h], r14
0x140028fe8  mov     word ptr [rbx+30h], 0FFFFh
0x140028fee  mov     rcx, [rdi]; this
0x140028ff1  test    rcx, rcx
0x140028ff4  jz      short loc_140028FFB
0x140028ff6  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140028ffb  mov     [rdi], rbx
0x140028ffe  test    rbx, rbx
0x140029001  jz      short loc_14002900B
0x140029003  mov     rcx, rbx; this
0x140029006  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x14002900b  cmp     [rdi], r15
0x14002900e  jz      short loc_140029049
0x140029010  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x140029017  call    cs:__imp_ExAcquireFastMutex
0x14002901e  nop     dword ptr [rax+rax+00h]
0x140029023  mov     rcx, [rsi+20h]; MidAtlas
0x140029027  test    rcx, rcx
0x14002902a  jnz     short loc_14002905F
0x14002902c  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x140029033  call    cs:__imp_ExReleaseFastMutex
0x14002903a  nop     dword ptr [rax+rax+00h]
0x14002903f  xor     edx, edx
0x140029041  mov     rcx, rdi
0x140029044  call    ??4?$SmartPtr@VVirtualChannel@@@@QEAAAEAV0@PEAVVirtualChannel@@@Z; SmartPtr<VirtualChannel>::operator=(VirtualChannel *)
0x140029049  mov     eax, r15d
0x14002904c  add     rsp, 28h
0x140029050  pop     r15
0x140029052  pop     r14
0x140029054  pop     rdi
0x140029055  pop     rsi
0x140029056  pop     rbp
0x140029057  pop     rbx
0x140029058  retn
0x14002905a  mov     rbx, r15
0x14002905d  jmp     short loc_140028FEE
0x14002905f  mov     rdx, [rdi]; Context
0x140029062  lea     r8, [rsp+58h+NewMid]; NewMid
0x140029067  call    cs:__imp_RxAssociateContextWithMid
0x14002906e  nop     dword ptr [rax+rax+00h]
0x140029073  test    eax, eax
0x140029075  js      short loc_14002902C
0x140029077  mov     r8, [rdi]
0x14002907a  movzx   edx, [rsp+58h+NewMid]
0x14002907f  mov     [r8+30h], dx
0x140029084  mov     rcx, [rdi]; this
0x140029087  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x14002908c  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x140029093  call    cs:__imp_ExReleaseFastMutex
0x14002909a  nop     dword ptr [rax+rax+00h]
0x14002909f  mov     eax, 1
0x1400290a4  add     rsp, 28h
0x1400290a8  pop     r15
0x1400290aa  pop     r14
0x1400290ac  pop     rdi
0x1400290ad  pop     rsi
0x1400290ae  pop     rbp
0x1400290af  pop     rbx
0x1400290b0  retn
```
