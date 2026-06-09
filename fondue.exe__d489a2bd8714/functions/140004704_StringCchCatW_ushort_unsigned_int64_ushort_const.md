# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140004704`
- end: `0x1400047ad`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002e5c`
- `0x140004840`

## callees

- `0x140004704`

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
0x140004704  mov     [rsp+arg_0], rbx
0x140004709  mov     [rsp+arg_8], rdi
0x14000470e  mov     r9d, 104h
0x140004714  mov     rbx, rcx
0x140004717  mov     r10d, r9d
0x14000471a  mov     rax, rcx
0x14000471d  xor     edi, edi
0x14000471f  cmp     [rax], di
0x140004722  jz      short loc_14000472E
0x140004724  add     rax, 2
0x140004728  sub     r10, 1
0x14000472c  jnz     short loc_14000471F
0x14000472e  mov     rax, r10
0x140004731  mov     rcx, r9
0x140004734  neg     rax
0x140004737  mov     rax, r10
0x14000473a  sbb     edx, edx
0x14000473c  sub     rcx, r10
0x14000473f  not     edx
0x140004741  and     edx, 80070057h
0x140004747  neg     rax
0x14000474a  sbb     r11, r11
0x14000474d  and     r11, rcx
0x140004750  test    r10, r10
0x140004753  jz      short loc_1400047A0
0x140004755  lea     rax, [rbx+r11*2]
0x140004759  mov     ecx, 7FFFFFFEh
0x14000475e  sub     r9, r11
0x140004761  jz      short loc_140004785
0x140004763  test    rcx, rcx
0x140004766  jz      short loc_140004785
0x140004768  movzx   edx, word ptr [r8]
0x14000476c  test    dx, dx
0x14000476f  jz      short loc_140004785
0x140004771  mov     [rax], dx
0x140004774  add     r8, 2
0x140004778  add     rax, 2
0x14000477c  dec     rcx
0x14000477f  sub     r9, 1
0x140004783  jnz     short loc_140004763
0x140004785  test    r9, r9
0x140004788  lea     rcx, [rax-2]
0x14000478c  cmovnz  rcx, rax
0x140004790  neg     r9
0x140004793  sbb     edx, edx
0x140004795  not     edx
0x140004797  and     edx, 8007007Ah
0x14000479d  mov     [rcx], di
0x1400047a0  mov     rbx, [rsp+arg_0]
0x1400047a5  mov     eax, edx
0x1400047a7  mov     rdi, [rsp+arg_8]
0x1400047ac  retn
```
