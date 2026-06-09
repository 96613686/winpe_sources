# DWRITE_FracSqrt(int)

- ea: `0x14001e838`
- end: `0x14001e899`
- name: `?DWRITE_FracSqrt@@YAHH@Z`
- size: `97`
- prototype: `__int64 __fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14001c950`
- `0x14001d214`
- `0x1400324b0`

## callees

- `0x14001e838`

## pseudocode

```c
__int64 __fastcall DWRITE_FracSqrt(int a1)
{
  unsigned int v2; // eax
  int v3; // edx
  unsigned int v4; // ecx
  unsigned int v5; // edx
  unsigned int v6; // ecx
  unsigned int v8; // ecx

  if ( a1 < 0 )
    return 0x80000000LL;
  v2 = 0x10000000;
  v3 = -((unsigned int)a1 < 0x40000000);
  v4 = a1 - 0x40000000;
  v5 = ~v3 & 0x40000000;
  if ( (unsigned int)a1 < 0x40000000 )
    v4 = a1;
  do
  {
    if ( v4 >= v2 + v5 )
    {
      v4 -= v2 + v5;
      v5 += 2 * v2;
    }
    v4 *= 2;
    v2 >>= 1;
  }
  while ( v2 );
  if ( v4 > v5 )
  {
    v8 = v4 - v5++;
    v6 = 2 * v8 - 1;
  }
  else
  {
    v6 = 2 * v4;
  }
  return v5 + (v6 > v5);
}

```

## disassembly

```asm
0x14001e838  mov     r8d, ecx
0x14001e83b  test    ecx, ecx
0x14001e83d  js      short loc_14001E893
0x14001e83f  mov     r9d, 40000000h
0x14001e845  mov     eax, 10000000h
0x14001e84a  cmp     ecx, r9d
0x14001e84d  sbb     edx, edx
0x14001e84f  add     ecx, 0C0000000h
0x14001e855  not     edx
0x14001e857  and     edx, r9d
0x14001e85a  cmp     r8d, r9d
0x14001e85d  cmovb   ecx, r8d
0x14001e861  lea     r8d, [rax+rdx]
0x14001e865  cmp     ecx, r8d
0x14001e868  jb      short loc_14001E870
0x14001e86a  sub     ecx, r8d
0x14001e86d  lea     edx, [rdx+rax*2]
0x14001e870  add     ecx, ecx
0x14001e872  shr     eax, 1
0x14001e874  jnz     short loc_14001E861
0x14001e876  cmp     ecx, edx
0x14001e878  ja      short loc_14001E886
0x14001e87a  add     ecx, ecx
0x14001e87c  xor     eax, eax
0x14001e87e  cmp     ecx, edx
0x14001e880  setnbe  al
0x14001e883  add     eax, edx
0x14001e885  retn
0x14001e886  sub     ecx, edx
0x14001e888  inc     edx
0x14001e88a  lea     ecx, ds:0FFFFFFFFFFFFFFFFh[rcx*2]
0x14001e891  jmp     short loc_14001E87C
0x14001e893  mov     eax, 80000000h
0x14001e898  retn
```
