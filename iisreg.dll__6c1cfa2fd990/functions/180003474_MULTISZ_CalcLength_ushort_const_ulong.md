# MULTISZ::CalcLength(ushort const *,ulong *)

- ea: `0x180003474`
- end: `0x1800034af`
- name: `?CalcLength@MULTISZ@@SAKPEBGPEAK@Z`
- size: `59`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000260c`
- `0x1800033ac`

## callees

- `0x180003474`

## pseudocode

```c
__int64 __fastcall MULTISZ::CalcLength(const unsigned __int16 *a1, unsigned int *a2)
{
  const unsigned __int16 *v2; // r8
  unsigned int v3; // r9d
  __int64 result; // rax
  __int64 v5; // rcx
  __int64 v6; // rcx

  v2 = a1;
  v3 = 0;
  for ( result = 1; *v2; v2 += v6 )
  {
    v5 = -1;
    do
      ++v5;
    while ( v2[v5] );
    v6 = (unsigned int)(v5 + 1);
    ++v3;
    result = (unsigned int)(v6 + result);
  }
  if ( a2 )
    *a2 = v3;
  return result;
}

```

## disassembly

```asm
0x180003474  xor     r10d, r10d
0x180003477  mov     r8, rcx
0x18000347a  mov     r9d, r10d
0x18000347d  lea     eax, [r10+1]
0x180003481  cmp     [rcx], r10w
0x180003485  jz      short loc_1800034A6
0x180003487  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000348b  inc     rcx
0x18000348e  cmp     [r8+rcx*2], r10w
0x180003493  jnz     short loc_18000348B
0x180003495  inc     ecx
0x180003497  inc     r9d
0x18000349a  add     eax, ecx
0x18000349c  lea     r8, [r8+rcx*2]
0x1800034a0  cmp     [r8], r10w
0x1800034a4  jnz     short loc_180003487
0x1800034a6  test    rdx, rdx
0x1800034a9  jz      short locret_1800034AE
0x1800034ab  mov     [rdx], r9d
0x1800034ae  retn
```
