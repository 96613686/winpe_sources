# StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)

- ea: `0x14000676c`
- end: `0x140006815`
- name: `?StringCchCatW@@YAJPEA_W_KPEB_W@Z`
- size: `169`
- prototype: `__int64 __fastcall(wchar_t *, __int64, wchar_t *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000410c`
- `0x14000691c`

## callees

- `0x14000676c`

## pseudocode

```c
__int64 __fastcall StringCchCatW(wchar_t *a1, __int64 a2, wchar_t *a3)
{
  __int64 v3; // r10
  wchar_t *v4; // rax
  unsigned int v5; // edx
  __int64 v6; // r11
  wchar_t *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r9
  wchar_t *v10; // rcx

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
0x14000676c  mov     [rsp+arg_0], rbx
0x140006771  mov     [rsp+arg_8], rdi
0x140006776  mov     r9d, 104h
0x14000677c  mov     rbx, rcx
0x14000677f  mov     r10d, r9d
0x140006782  mov     rax, rcx
0x140006785  xor     edi, edi
0x140006787  cmp     [rax], di
0x14000678a  jz      short loc_140006796
0x14000678c  add     rax, 2
0x140006790  sub     r10, 1
0x140006794  jnz     short loc_140006787
0x140006796  mov     rax, r10
0x140006799  mov     rcx, r9
0x14000679c  neg     rax
0x14000679f  mov     rax, r10
0x1400067a2  sbb     edx, edx
0x1400067a4  sub     rcx, r10
0x1400067a7  not     edx
0x1400067a9  and     edx, 80070057h
0x1400067af  neg     rax
0x1400067b2  sbb     r11, r11
0x1400067b5  and     r11, rcx
0x1400067b8  test    r10, r10
0x1400067bb  jz      short loc_140006808
0x1400067bd  lea     rax, [rbx+r11*2]
0x1400067c1  mov     ecx, 7FFFFFFEh
0x1400067c6  sub     r9, r11
0x1400067c9  jz      short loc_1400067ED
0x1400067cb  test    rcx, rcx
0x1400067ce  jz      short loc_1400067ED
0x1400067d0  movzx   edx, word ptr [r8]
0x1400067d4  test    dx, dx
0x1400067d7  jz      short loc_1400067ED
0x1400067d9  mov     [rax], dx
0x1400067dc  add     r8, 2
0x1400067e0  add     rax, 2
0x1400067e4  dec     rcx
0x1400067e7  sub     r9, 1
0x1400067eb  jnz     short loc_1400067CB
0x1400067ed  test    r9, r9
0x1400067f0  lea     rcx, [rax-2]
0x1400067f4  cmovnz  rcx, rax
0x1400067f8  neg     r9
0x1400067fb  sbb     edx, edx
0x1400067fd  not     edx
0x1400067ff  and     edx, 8007007Ah
0x140006805  mov     [rcx], di
0x140006808  mov     rbx, [rsp+arg_0]
0x14000680d  mov     eax, edx
0x14000680f  mov     rdi, [rsp+arg_8]
0x140006814  retn
```
