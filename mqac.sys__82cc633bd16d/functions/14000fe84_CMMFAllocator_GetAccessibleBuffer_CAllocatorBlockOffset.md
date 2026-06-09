# CMMFAllocator::GetAccessibleBuffer(CAllocatorBlockOffset)

- ea: `0x14000fe84`
- end: `0x14000fefe`
- name: `?GetAccessibleBuffer@CMMFAllocator@@QEAAPEAVCAccessibleBlock@@VCAllocatorBlockOffset@@@Z`
- size: `122`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x140001cb0`
- `0x140010d20`
- `0x140010e2c`
- `0x1400152d0`
- `0x14001adac`

## callees

- `0x14000fe68`
- `0x14000fe84`
- `0x14000ff9c`
- `0x140010200`
- `0x140010b74`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x14000fea5`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000fea5`

## pseudocode

```c
__int64 __fastcall CMMFAllocator::GetAccessibleBuffer(CMMFAllocator *a1, unsigned int a2)
{
  __int64 v4; // rbp
  struct _KPROCESS *v5; // rdi
  CMMFAllocator *v7; // rcx

  if ( !*((_QWORD *)a1 + 11) )
    return 0;
  v4 = *(_QWORD *)(*((_QWORD *)a1 + 15) + 64LL);
  v5 = *(struct _KPROCESS **)(v4 + 80);
  if ( IoGetCurrentProcess() == v5 )
    return CMMFAllocator::GetQmAccessibleBuffer(a1, a2);
  if ( *((_QWORD *)a1 + 13) )
    return CMMFAllocator::GetAcAccessibleBufferNoMapping(a1, a2);
  v7 = *(CMMFAllocator **)(v4 + 1024);
  if ( v7 )
    CMMFAllocator::UnmapACView(v7);
  if ( (int)CMMFAllocator::MapACView(a1) >= 0 )
    return CMMFAllocator::GetAcAccessibleBufferNoMapping(a1, a2);
  else
    return 0;
}

```

## disassembly

```asm
0x14000fe84  push    rbx
0x14000fe86  push    rbp
0x14000fe87  push    rsi
0x14000fe88  push    rdi
0x14000fe89  sub     rsp, 28h
0x14000fe8d  cmp     qword ptr [rcx+58h], 0
0x14000fe92  mov     ebx, edx
0x14000fe94  mov     rsi, rcx
0x14000fe97  jz      short loc_14000FEF2
0x14000fe99  mov     rax, [rcx+78h]
0x14000fe9d  mov     rbp, [rax+40h]
0x14000fea1  mov     rdi, [rbp+50h]
0x14000fea5  call    cs:__imp_IoGetCurrentProcess
0x14000feac  nop     dword ptr [rax+rax+00h]
0x14000feb1  cmp     rax, rdi
0x14000feb4  jnz     short loc_14000FEC2
0x14000feb6  mov     edx, ebx
0x14000feb8  mov     rcx, rsi
0x14000febb  call    ?GetQmAccessibleBuffer@CMMFAllocator@@QEAAPEAVCAccessibleBlock@@VCAllocatorBlockOffset@@@Z; CMMFAllocator::GetQmAccessibleBuffer(CAllocatorBlockOffset)
0x14000fec0  jmp     short loc_14000FEF4
0x14000fec2  cmp     qword ptr [rsi+68h], 0
0x14000fec7  jnz     short loc_14000FEE6
0x14000fec9  mov     rcx, [rbp+400h]; this
0x14000fed0  test    rcx, rcx
0x14000fed3  jz      short loc_14000FEDA
0x14000fed5  call    ?UnmapACView@CMMFAllocator@@AEAAXXZ; CMMFAllocator::UnmapACView(void)
0x14000feda  mov     rcx, rsi; this
0x14000fedd  call    ?MapACView@CMMFAllocator@@AEAAJXZ; CMMFAllocator::MapACView(void)
0x14000fee2  test    eax, eax
0x14000fee4  js      short loc_14000FEF2
0x14000fee6  mov     edx, ebx
0x14000fee8  mov     rcx, rsi
0x14000feeb  call    ?GetAcAccessibleBufferNoMapping@CMMFAllocator@@AEBAPEAVCAccessibleBlock@@VCAllocatorBlockOffset@@@Z; CMMFAllocator::GetAcAccessibleBufferNoMapping(CAllocatorBlockOffset)
0x14000fef0  jmp     short loc_14000FEF4
0x14000fef2  xor     eax, eax
0x14000fef4  add     rsp, 28h
0x14000fef8  pop     rdi
0x14000fef9  pop     rsi
0x14000fefa  pop     rbp
0x14000fefb  pop     rbx
0x14000fefc  retn
```
