# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000909c`
- end: `0x180009145`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800083b4`
- `0x18000914c`

## callees

- `0x18000909c`

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
0x18000909c  mov     [rsp+arg_0], rbx
0x1800090a1  mov     [rsp+arg_8], rdi
0x1800090a6  mov     r9d, 104h
0x1800090ac  mov     rbx, rcx
0x1800090af  mov     r10d, r9d
0x1800090b2  mov     rax, rcx
0x1800090b5  xor     edi, edi
0x1800090b7  cmp     [rax], di
0x1800090ba  jz      short loc_1800090C6
0x1800090bc  add     rax, 2
0x1800090c0  sub     r10, 1
0x1800090c4  jnz     short loc_1800090B7
0x1800090c6  mov     rax, r10
0x1800090c9  mov     rcx, r9
0x1800090cc  neg     rax
0x1800090cf  mov     rax, r10
0x1800090d2  sbb     edx, edx
0x1800090d4  sub     rcx, r10
0x1800090d7  not     edx
0x1800090d9  and     edx, 80070057h
0x1800090df  neg     rax
0x1800090e2  sbb     r11, r11
0x1800090e5  and     r11, rcx
0x1800090e8  test    r10, r10
0x1800090eb  jz      short loc_180009138
0x1800090ed  lea     rax, [rbx+r11*2]
0x1800090f1  mov     ecx, 7FFFFFFEh
0x1800090f6  sub     r9, r11
0x1800090f9  jz      short loc_18000911D
0x1800090fb  test    rcx, rcx
0x1800090fe  jz      short loc_18000911D
0x180009100  movzx   edx, word ptr [r8]
0x180009104  test    dx, dx
0x180009107  jz      short loc_18000911D
0x180009109  mov     [rax], dx
0x18000910c  add     r8, 2
0x180009110  add     rax, 2
0x180009114  dec     rcx
0x180009117  sub     r9, 1
0x18000911b  jnz     short loc_1800090FB
0x18000911d  test    r9, r9
0x180009120  lea     rcx, [rax-2]
0x180009124  cmovnz  rcx, rax
0x180009128  neg     r9
0x18000912b  sbb     edx, edx
0x18000912d  not     edx
0x18000912f  and     edx, 8007007Ah
0x180009135  mov     [rcx], di
0x180009138  mov     rbx, [rsp+arg_0]
0x18000913d  mov     eax, edx
0x18000913f  mov     rdi, [rsp+arg_8]
0x180009144  retn
```
