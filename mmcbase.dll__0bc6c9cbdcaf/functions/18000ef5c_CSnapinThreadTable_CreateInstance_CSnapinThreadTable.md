# CSnapinThreadTable::CreateInstance(CSnapinThreadTable * *)

- ea: `0x18000ef5c`
- end: `0x18000f024`
- name: `?CreateInstance@CSnapinThreadTable@@SAJPEAPEAV1@@Z`
- size: `200`
- prototype: `__int64 __fastcall(struct CSnapinThreadTable **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180001f90`

## callees

- `0x1800023e0`
- `0x18000bd34`
- `0x18000ef5c`
- `0x180019ba0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSnapinThreadTable::CreateInstance(struct CSnapinThreadTable **a1, __int64 a2, unsigned int a3)
{
  LKRhash::CLKRLinearHashTable *v3; // rbx
  unsigned int v4; // edi
  unsigned int v6; // [rsp+40h] [rbp-28h]
  bool v7; // [rsp+48h] [rbp-20h]
  bool v8; // [rsp+50h] [rbp-18h]
  struct CLKRhashAllocator *v9; // [rsp+58h] [rbp-10h]

  v3 = (LKRhash::CLKRLinearHashTable *)CHeapFactory::Alloc((CHeapFactory *)a1, 0xB8u, a3);
  v4 = 0;
  if ( v3 )
  {
    LKRhash::CLKRLinearHashTable::CLKRLinearHashTable(
      v3,
      "number",
      LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,unsigned long,LKRhash::CLKRLinearHashTable>::_ExtractKey,
      LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,unsigned long,LKRhash::CLKRLinearHashTable>::_CalcKeyHash,
      LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,unsigned long,LKRhash::CLKRLinearHashTable>::_EqualKeys,
      (void (*)(const void *, int))CObject::AssertValid,
      4.0,
      3u,
      v6,
      v7,
      v8,
      v9);
    *((_DWORD *)v3 + 44) = 0;
  }
  else
  {
    v3 = 0;
  }
  if ( !v3 )
  {
    v4 = -2147024882;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 23, WPP_8949107765ef31f55290197bfd8c288d_Traceguids);
  }
  BookKeeping::s_pSnapinThreadTable = v3;
  return v4;
}

```

## disassembly

```asm
0x18000ef5c  mov     [rsp+arg_8], rbx
0x18000ef61  mov     [rsp+arg_0], rcx
0x18000ef66  push    rdi
0x18000ef67  sub     rsp, 60h
0x18000ef6b  mov     edx, 0B8h; unsigned __int64
0x18000ef70  call    ?Alloc@CHeapFactory@@QEAAPEAX_KK@Z; CHeapFactory::Alloc(unsigned __int64,ulong)
0x18000ef75  mov     rbx, rax
0x18000ef78  mov     [rsp+68h+arg_0], rax
0x18000ef7d  xor     edi, edi
0x18000ef7f  test    rax, rax
0x18000ef82  jz      short loc_18000EFD7
0x18000ef84  mov     [rsp+68h+var_30], 3; unsigned int
0x18000ef8c  movsd   xmm0, cs:__real@4010000000000000
0x18000ef94  movsd   [rsp+68h+var_38], xmm0; double
0x18000ef9a  lea     rax, ?AssertValid@CObject@@UEBAXXZ; CObject::AssertValid(void)
0x18000efa1  mov     [rsp+68h+var_40], rax; void (*)(const void *, int)
0x18000efa6  lea     rax, ?_EqualKeys@?$CTypedHashTable@VCSnapinThreadTable@@VCSnapinThread@@KVCLKRLinearHashTable@LKRhash@@@LKRhash@@CA_N_K0@Z; LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,ulong,LKRhash::CLKRLinearHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x18000efad  mov     [rsp+68h+var_48], rax; bool (*)(unsigned __int64, unsigned __int64)
0x18000efb2  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VCSnapinThreadTable@@VCSnapinThread@@KVCLKRLinearHashTable@LKRhash@@@LKRhash@@CAK_K@Z; unsigned int (*)(unsigned __int64)
0x18000efb9  lea     r8, ?_ExtractKey@?$CTypedHashTable@VCSnapinThreadTable@@VCSnapinThread@@KVCLKRLinearHashTable@LKRhash@@@LKRhash@@CA?B_KPEBX@Z; unsigned __int64 (*)(const void *)
0x18000efc0  lea     rdx, aNumber; "number"
0x18000efc7  mov     rcx, rbx; this
0x18000efca  call    ??0CLKRLinearHashTable@LKRhash@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N7PEAVCLKRhashAllocator@@@Z; LKRhash::CLKRLinearHashTable::CLKRLinearHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool,bool,CLKRhashAllocator *)
0x18000efcf  mov     [rbx+0B0h], edi
0x18000efd5  jmp     short loc_18000EFDA
0x18000efd7  mov     rbx, rdi
0x18000efda  test    rbx, rbx
0x18000efdd  jnz     short loc_18000F010
0x18000efdf  mov     edi, 8007000Eh
0x18000efe4  lea     rax, WPP_GLOBAL_Control
0x18000efeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eff2  cmp     rcx, rax
0x18000eff5  jz      short loc_18000F010
0x18000eff7  cmp     byte ptr [rcx+19h], 2
0x18000effb  jb      short loc_18000F010
0x18000effd  lea     edx, [rbx+17h]
0x18000f000  lea     r8, WPP_8949107765ef31f55290197bfd8c288d_Traceguids
0x18000f007  mov     rcx, [rcx+10h]
0x18000f00b  call    WPP_SF_
0x18000f010  mov     cs:?s_pSnapinThreadTable@BookKeeping@@0PEAVCSnapinThreadTable@@EA, rbx; CSnapinThreadTable * BookKeeping::s_pSnapinThreadTable
0x18000f017  mov     eax, edi
0x18000f019  mov     rbx, [rsp+68h+arg_8]
0x18000f01e  add     rsp, 60h
0x18000f022  pop     rdi
0x18000f023  retn
```
