# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140008ec8`
- end: `0x140008f71`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140004734`
- `0x140009124`
- `0x14000b8c0`

## callees

- `0x140008ec8`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // r10
  unsigned __int16 *v4; // rax
  unsigned int v5; // edx
  __int64 v6; // r11
  unsigned __int16 *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r9
  unsigned __int16 *v10; // rcx

  v3 = 260;
  v4 = a1;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v3;
  }
  while ( v3 );
  v5 = v3 == 0 ? 0x80070057 : 0;
  v6 = (260 - v3) & -(__int64)(v3 != 0);
  if ( v3 )
  {
    v7 = &a1[v6];
    v8 = 2147483646;
    v9 = 260 - v6;
    if ( 260 != v6 )
    {
      do
      {
        if ( !v8 )
          break;
        if ( !*a3 )
          break;
        *v7++ = *a3++;
        --v8;
        --v9;
      }
      while ( v9 );
    }
    v10 = v7 - 1;
    if ( v9 )
      v10 = v7;
    v5 = v9 == 0 ? 0x8007007A : 0;
    *v10 = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x140008ec8  mov     [rsp+arg_0], rbx
0x140008ecd  mov     [rsp+arg_8], rdi
0x140008ed2  mov     r9d, 104h
0x140008ed8  mov     rbx, rcx
0x140008edb  mov     r10d, r9d
0x140008ede  mov     rax, rcx
0x140008ee1  xor     edi, edi
0x140008ee3  cmp     [rax], di
0x140008ee6  jz      short loc_140008EF2
0x140008ee8  add     rax, 2
0x140008eec  sub     r10, 1
0x140008ef0  jnz     short loc_140008EE3
0x140008ef2  mov     rax, r10
0x140008ef5  mov     rcx, r9
0x140008ef8  neg     rax
0x140008efb  mov     rax, r10
0x140008efe  sbb     edx, edx
0x140008f00  sub     rcx, r10
0x140008f03  not     edx
0x140008f05  and     edx, 80070057h
0x140008f0b  neg     rax
0x140008f0e  sbb     r11, r11
0x140008f11  and     r11, rcx
0x140008f14  test    r10, r10
0x140008f17  jz      short loc_140008F64
0x140008f19  lea     rax, [rbx+r11*2]
0x140008f1d  mov     ecx, 7FFFFFFEh
0x140008f22  sub     r9, r11
0x140008f25  jz      short loc_140008F49
0x140008f27  test    rcx, rcx
0x140008f2a  jz      short loc_140008F49
0x140008f2c  movzx   edx, word ptr [r8]
0x140008f30  test    dx, dx
0x140008f33  jz      short loc_140008F49
0x140008f35  mov     [rax], dx
0x140008f38  add     r8, 2
0x140008f3c  add     rax, 2
0x140008f40  dec     rcx
0x140008f43  sub     r9, 1
0x140008f47  jnz     short loc_140008F27
0x140008f49  test    r9, r9
0x140008f4c  lea     rcx, [rax-2]
0x140008f50  cmovnz  rcx, rax
0x140008f54  neg     r9
0x140008f57  sbb     edx, edx
0x140008f59  not     edx
0x140008f5b  and     edx, 8007007Ah
0x140008f61  mov     [rcx], di
0x140008f64  mov     rbx, [rsp+arg_0]
0x140008f69  mov     eax, edx
0x140008f6b  mov     rdi, [rsp+arg_8]
0x140008f70  retn
```
