# GetMemoryTableInterceptor(_GUID const &,void * *)

- ea: `0x1800024b0`
- end: `0x1800025a2`
- name: `?GetMemoryTableInterceptor@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `242`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180002970`

## callees

- `0x180001fe8`
- `0x1800024b0`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800024c4`
- `ole32!CoTaskMemAlloc` at `0x1800024c4`

## pseudocode

```c
__int64 __fastcall GetMemoryTableInterceptor(const struct _GUID *a1, void **a2)
{
  CMemoryTable *v4; // rax
  CMemoryTable *v5; // rbx
  unsigned int v6; // edx
  int v7; // edi

  v4 = (CMemoryTable *)CoTaskMemAlloc(0xC8u);
  v5 = v4;
  if ( !v4 )
    return 2147942414LL;
  *((_QWORD *)v4 + 4) = 0;
  *(_QWORD *)v4 = &CMemoryTable::`vftable'{for `ISimpleTableInterceptor'};
  *((_QWORD *)v4 + 5) = 0;
  *((_QWORD *)v4 + 1) = &CMemoryTable::`vftable'{for `ISimpleTableWrite2'};
  *((_DWORD *)v4 + 12) = 0;
  *((_QWORD *)v4 + 2) = &CMemoryTable::`vftable'{for `ISimpleTableController'};
  *((_QWORD *)v4 + 7) = 0;
  *((_QWORD *)v4 + 3) = &CMemoryTable::`vftable'{for `ISimpleTableMarshall'};
  *((_QWORD *)v4 + 8) = 0;
  *((_QWORD *)v4 + 9) = 0;
  *((_QWORD *)v4 + 10) = 0;
  *((_QWORD *)v4 + 11) = 1024;
  *((_QWORD *)v4 + 12) = 1;
  *((_DWORD *)v4 + 26) = 0;
  *((_QWORD *)v4 + 14) = 0;
  *((_QWORD *)v4 + 15) = 0;
  *((_QWORD *)v4 + 16) = 0;
  *((_QWORD *)v4 + 17) = 0;
  *((_QWORD *)v4 + 18) = 0;
  *((_QWORD *)v4 + 19) = 0;
  *((_QWORD *)v4 + 20) = 0;
  *((_QWORD *)v4 + 21) = 0;
  *((_QWORD *)v4 + 22) = 0;
  *((_QWORD *)v4 + 23) = 0;
  v7 = ((__int64 (__fastcall *)(CMemoryTable *, const struct _GUID *, void **))CMemoryTable::`vftable'{for `ISimpleTableInterceptor'})(
         v4,
         a1,
         a2);
  if ( v7 < 0 )
    CMemoryTable::`scalar deleting destructor'(v5, v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800024b0  push    rbx
0x1800024b2  push    rbp
0x1800024b3  push    rsi
0x1800024b4  push    rdi
0x1800024b5  sub     rsp, 28h
0x1800024b9  mov     rsi, rcx
0x1800024bc  mov     rdi, rdx
0x1800024bf  mov     ecx, 0C8h; cb
0x1800024c4  call    cs:__imp_CoTaskMemAlloc
0x1800024ca  xor     ebp, ebp
0x1800024cc  mov     rbx, rax
0x1800024cf  test    rax, rax
0x1800024d2  jz      loc_180002594
0x1800024d8  lea     r9, ??_7CMemoryTable@@6BISimpleTableInterceptor@@@; const CMemoryTable::`vftable'{for `ISimpleTableInterceptor'}
0x1800024df  mov     [rbx+20h], rbp
0x1800024e3  mov     [rax], r9
0x1800024e6  mov     r8, rdi
0x1800024e9  lea     rax, ??_7CMemoryTable@@6BISimpleTableWrite2@@@; const CMemoryTable::`vftable'{for `ISimpleTableWrite2'}
0x1800024f0  mov     [rbx+28h], rbp
0x1800024f4  mov     [rbx+8], rax
0x1800024f8  mov     rdx, rsi
0x1800024fb  lea     rax, ??_7CMemoryTable@@6BISimpleTableController@@@; const CMemoryTable::`vftable'{for `ISimpleTableController'}
0x180002502  mov     [rbx+30h], ebp
0x180002505  mov     [rbx+10h], rax
0x180002509  mov     rcx, rbx
0x18000250c  lea     rax, ??_7CMemoryTable@@6BISimpleTableMarshall@@@; const CMemoryTable::`vftable'{for `ISimpleTableMarshall'}
0x180002513  mov     [rbx+38h], rbp
0x180002517  mov     [rbx+18h], rax
0x18000251b  mov     rax, [r9]
0x18000251e  mov     [rbx+40h], rbp
0x180002522  mov     [rbx+48h], rbp
0x180002526  mov     [rbx+50h], rbp
0x18000252a  mov     qword ptr [rbx+58h], 400h
0x180002532  mov     qword ptr [rbx+60h], 1
0x18000253a  mov     [rbx+68h], ebp
0x18000253d  mov     [rbx+70h], rbp
0x180002541  mov     [rbx+78h], rbp
0x180002545  mov     [rbx+80h], rbp
0x18000254c  mov     [rbx+88h], rbp
0x180002553  mov     [rbx+90h], rbp
0x18000255a  mov     [rbx+98h], rbp
0x180002561  mov     [rbx+0A0h], rbp
0x180002568  mov     [rbx+0A8h], rbp
0x18000256f  mov     [rbx+0B0h], rbp
0x180002576  mov     [rbx+0B8h], rbp
0x18000257d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002582  mov     edi, eax
0x180002584  test    eax, eax
0x180002586  jns     short loc_180002590
0x180002588  mov     rcx, rbx; this
0x18000258b  call    ??_GCMemoryTable@@QEAAPEAXI@Z; CMemoryTable::`scalar deleting destructor'(uint)
0x180002590  mov     eax, edi
0x180002592  jmp     short loc_180002599
0x180002594  mov     eax, 8007000Eh
0x180002599  add     rsp, 28h
0x18000259d  pop     rdi
0x18000259e  pop     rsi
0x18000259f  pop     rbp
0x1800025a0  pop     rbx
0x1800025a1  retn
```
