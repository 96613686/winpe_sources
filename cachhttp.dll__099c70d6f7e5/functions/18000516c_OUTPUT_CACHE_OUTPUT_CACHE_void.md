# OUTPUT_CACHE::OUTPUT_CACHE(void)

- ea: `0x18000516c`
- end: `0x1800051f8`
- name: `??0OUTPUT_CACHE@@QEAA@XZ`
- size: `140`
- prototype: `OUTPUT_CACHE *__fastcall(OUTPUT_CACHE *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800039d0`

## import_xrefs

- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x1800051c3`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x1800051c3`

## string_xrefs

- `0x180005195`: `OUTPUT_CACHE`

## pseudocode

```c
OUTPUT_CACHE *__fastcall OUTPUT_CACHE::OUTPUT_CACHE(OUTPUT_CACHE *this)
{
  OUTPUT_CACHE *result; // rax

  CLKRHashTable::CLKRHashTable(
    this,
    "OUTPUT_CACHE",
    (unsigned __int64 (*)(const void *))CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_ExtractKey,
    (unsigned int (*)(unsigned __int64))CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_CalcKeyHash,
    (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_EqualKeys,
    (void (*)(const void *, int))CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_AddRefRecord,
    4.0,
    1u,
    0,
    0);
  result = this;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 5000;
  *((_DWORD *)this + 30) = 0;
  return result;
}

```

## disassembly

```asm
0x18000516c  mov     rax, rsp
0x18000516f  push    rbx
0x180005170  sub     rsp, 50h
0x180005174  movsd   xmm0, cs:__real@4010000000000000
0x18000517c  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VOUTPUT_CACHE@@VOUTPUT_ENTRY@@PEAVOUTPUT_KEY@@VCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x180005183  mov     byte ptr [rax-10h], 0
0x180005187  lea     r8, ?_ExtractKey@?$CTypedHashTable@VOUTPUT_CACHE@@VOUTPUT_ENTRY@@PEAVOUTPUT_KEY@@VCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_ExtractKey(void const *)
0x18000518e  mov     dword ptr [rax-18h], 0
0x180005195  lea     rdx, aOutputCache; "OUTPUT_CACHE"
0x18000519c  mov     dword ptr [rax-20h], 1
0x1800051a3  mov     rbx, rcx
0x1800051a6  movsd   qword ptr [rax-28h], xmm0
0x1800051ab  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VOUTPUT_CACHE@@VOUTPUT_ENTRY@@PEAVOUTPUT_KEY@@VCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_AddRefRecord(void const *,int)
0x1800051b2  mov     [rsp+58h+var_30], rax
0x1800051b7  lea     rax, ?_EqualKeys@?$CTypedHashTable@VOUTPUT_CACHE@@VOUTPUT_ENTRY@@PEAVOUTPUT_KEY@@VCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x1800051be  mov     [rsp+58h+var_38], rax
0x1800051c3  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x1800051c9  mov     rax, rbx
0x1800051cc  mov     qword ptr [rbx+48h], 0
0x1800051d4  mov     dword ptr [rbx+50h], 0
0x1800051db  mov     qword ptr [rbx+68h], 0
0x1800051e3  mov     qword ptr [rbx+70h], 1388h
0x1800051eb  mov     dword ptr [rbx+78h], 0
0x1800051f2  add     rsp, 50h
0x1800051f6  pop     rbx
0x1800051f7  retn
```
