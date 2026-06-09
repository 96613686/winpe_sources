# CIISDsCrMap::SetMdData(ushort *,ulong,ulong,ulong,uchar *)

- ea: `0x18000d6d8`
- end: `0x18000d744`
- name: `?SetMdData@CIISDsCrMap@@QEAAJPEAGKKKPEAE@Z`
- size: `108`
- prototype: `__int64 __fastcall(CIISDsCrMap *this, unsigned __int16 *, int, int, unsigned int, unsigned __int8 *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ac50`
- `0x18000b22c`
- `0x18000cba0`
- `0x18000d4c0`
- `0x18000d5dc`
- `0x18000d81c`
- `0x18000d930`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISDsCrMap::SetMdData(
        CIISDsCrMap *this,
        unsigned __int16 *a2,
        int a3,
        int a4,
        unsigned int a5,
        unsigned __int8 *a6)
{
  int v7; // eax
  __int64 v8; // rcx
  __int64 v10; // rdx
  _DWORD v12[6]; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int8 *v13; // [rsp+48h] [rbp-20h]
  __int64 v14; // [rsp+50h] [rbp-18h]

  v12[2] = 0;
  v12[5] = 0;
  v14 = 0;
  v12[4] = a5;
  v7 = 0;
  v12[3] = a4;
  if ( a3 == 2093 )
    v7 = 4;
  v12[0] = a3;
  v8 = *((_QWORD *)this + 7);
  v12[1] = v7;
  v10 = *((unsigned int *)this + 16);
  v13 = a6;
  return (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 *, _DWORD *))(*(_QWORD *)v8 + 72LL))(
           v8,
           v10,
           a2,
           v12);
}

```

## disassembly

```asm
0x18000d6d8  mov     r11, rsp
0x18000d6db  sub     rsp, 68h
0x18000d6df  mov     eax, [rsp+68h+arg_20]
0x18000d6e6  mov     r10, rcx
0x18000d6e9  xor     ecx, ecx
0x18000d6eb  mov     [rsp+68h+var_30], ecx
0x18000d6ef  cmp     r8d, 82Dh
0x18000d6f6  mov     [rsp+68h+var_24], ecx
0x18000d6fa  mov     [r11-18h], rcx
0x18000d6fe  mov     [rsp+68h+var_28], eax
0x18000d702  mov     eax, ecx
0x18000d704  mov     [r11-2Ch], r9d
0x18000d708  mov     ecx, 4
0x18000d70d  cmovz   eax, ecx
0x18000d710  mov     [r11-38h], r8d
0x18000d714  mov     rcx, [r10+38h]
0x18000d718  lea     r9, [r11-38h]
0x18000d71c  mov     [rsp+68h+var_34], eax
0x18000d720  mov     r8, rdx
0x18000d723  mov     rax, [rsp+68h+arg_28]
0x18000d72b  mov     edx, [r10+40h]
0x18000d72f  mov     [r11-20h], rax
0x18000d733  mov     rax, [rcx]
0x18000d736  mov     rax, [rax+48h]
0x18000d73a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d73f  add     rsp, 68h
0x18000d743  retn
```
