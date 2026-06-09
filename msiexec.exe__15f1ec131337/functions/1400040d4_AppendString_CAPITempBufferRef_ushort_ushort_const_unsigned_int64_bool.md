# AppendString(CAPITempBufferRef<ushort> &,ushort const *,unsigned __int64,bool)

- ea: `0x1400040d4`
- end: `0x1400041c6`
- name: `?AppendString@@YAKAEAV?$CAPITempBufferRef@G@@PEBG_K_N@Z`
- size: `242`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, unsigned __int64, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400011e4`

## callees

- `0x1400040d4`
- `0x1400081f0`
- `0x140008768`
- `0x140008808`

## pseudocode

```c
__int64 __fastcall AppendString(__int64 a1, const unsigned __int16 *a2, unsigned __int64 a3, unsigned __int8 a4)
{
  __int64 v5; // rbp
  const unsigned __int16 *v6; // rcx
  __int64 v9; // r8
  unsigned __int64 v10; // rbx
  unsigned __int64 v11; // r9
  int v13; // eax
  unsigned int v14; // edx
  unsigned __int64 v15; // [rsp+40h] [rbp+8h] BYREF

  v5 = a4;
  v6 = *(const unsigned __int16 **)a1;
  v15 = 0;
  if ( (int)StringCchLengthW(v6, (unsigned __int64)a2, &v15) < 0 )
    return 1627;
  v10 = v15;
  v11 = a3 + v5 + 1;
  if ( v11 > a3 && v15 + 2 * v11 > v15 && v11 + v15 > *(int *)(a1 + 8) )
  {
    LOBYTE(v9) = 1;
    if ( !(unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(a1, (unsigned int)(v15 + 2 * v11), v9) )
      return 14;
  }
  if ( StringCchCopyNW((unsigned __int16 *)(*(_QWORD *)a1 + 2 * v10), *(int *)(a1 + 8) - v10, a2, a3) < 0 )
    return 1627;
  if ( !(_BYTE)v5 )
    return 0;
  v13 = StringCchCopyNW((unsigned __int16 *)(*(_QWORD *)a1 + 2 * (v10 + a3)), *(int *)(a1 + 8) - v10 - a3, L" ", 1u);
  v14 = 1627;
  if ( v13 >= 0 )
    return 0;
  return v14;
}

```

## disassembly

```asm
0x1400040d4  mov     rax, rsp
0x1400040d7  mov     [rax+10h], rbx
0x1400040db  mov     [rax+18h], rbp
0x1400040df  push    rsi
0x1400040e0  push    rdi
0x1400040e1  push    r14
0x1400040e3  sub     rsp, 20h
0x1400040e7  mov     rdi, rcx
0x1400040ea  movzx   ebp, r9b
0x1400040ee  mov     rcx, [rcx]; unsigned __int16 *
0x1400040f1  mov     rsi, r8
0x1400040f4  lea     r8, [rax+8]; unsigned __int64 *
0x1400040f8  mov     qword ptr [rax+8], 0
0x140004100  mov     r14, rdx
0x140004103  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x140004108  test    eax, eax
0x14000410a  js      loc_1400041AE
0x140004110  mov     rbx, [rsp+38h+arg_0]
0x140004115  lea     r9, [rbp+1]
0x140004119  add     r9, rsi
0x14000411c  cmp     r9, rsi
0x14000411f  jbe     short loc_140004151
0x140004121  lea     rax, [rbx+r9*2]
0x140004125  cmp     rax, rbx
0x140004128  jbe     short loc_140004151
0x14000412a  movsxd  rax, dword ptr [rdi+8]
0x14000412e  lea     rcx, [r9+rbx]
0x140004132  cmp     rcx, rax
0x140004135  jbe     short loc_140004151
0x140004137  lea     edx, [rbx+r9*2]
0x14000413b  mov     r8b, 1
0x14000413e  mov     rcx, rdi
0x140004141  call    ?SetSize@?$CAPITempBufferRef@G@@QEAA_NH_N@Z; CAPITempBufferRef<ushort>::SetSize(int,bool)
0x140004146  test    al, al
0x140004148  jnz     short loc_140004151
0x14000414a  mov     eax, 0Eh
0x14000414f  jmp     short loc_1400041B3
0x140004151  mov     rax, [rdi]
0x140004154  mov     r9, rsi; unsigned __int64
0x140004157  movsxd  rdx, dword ptr [rdi+8]
0x14000415b  mov     r8, r14; unsigned __int16 *
0x14000415e  sub     rdx, rbx; unsigned __int64
0x140004161  lea     rcx, [rax+rbx*2]; unsigned __int16 *
0x140004165  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x14000416a  test    eax, eax
0x14000416c  js      short loc_1400041AE
0x14000416e  test    bpl, bpl
0x140004171  jz      short loc_1400041AA
0x140004173  mov     rax, [rdi]
0x140004176  lea     rcx, [rbx+rsi]
0x14000417a  movsxd  rdx, dword ptr [rdi+8]
0x14000417e  lea     r8, asc_14000B91C; " "
0x140004185  sub     rdx, rbx
0x140004188  mov     r9d, 1; unsigned __int64
0x14000418e  sub     rdx, rsi; unsigned __int64
0x140004191  lea     rcx, [rax+rcx*2]; unsigned __int16 *
0x140004195  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x14000419a  xor     ecx, ecx
0x14000419c  mov     edx, 65Bh
0x1400041a1  test    eax, eax
0x1400041a3  cmovns  edx, ecx
0x1400041a6  mov     eax, edx
0x1400041a8  jmp     short loc_1400041B3
0x1400041aa  xor     eax, eax
0x1400041ac  jmp     short loc_1400041B3
0x1400041ae  mov     eax, 65Bh
0x1400041b3  mov     rbx, [rsp+38h+arg_8]
0x1400041b8  mov     rbp, [rsp+38h+arg_10]
0x1400041bd  add     rsp, 20h
0x1400041c1  pop     r14
0x1400041c3  pop     rdi
0x1400041c4  pop     rsi
0x1400041c5  retn
```
