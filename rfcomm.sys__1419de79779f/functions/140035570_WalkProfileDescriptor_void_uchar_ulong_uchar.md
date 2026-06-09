# WalkProfileDescriptor(void *,uchar,ulong,uchar *)

- ea: `0x140035570`
- end: `0x1400355c2`
- name: `?WalkProfileDescriptor@@YAJPEAXEKPEAE@Z`
- size: `82`
- prototype: `__int64 __fastcall(void *, unsigned __int8, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140035570`

## pseudocode

```c
__int64 __fastcall WalkProfileDescriptor(void *a1, __int64 a2, int a3, unsigned __int8 *a4)
{
  __int64 v4; // rcx
  int v5; // r8d
  unsigned __int8 v6; // cl
  __int64 result; // rax

  if ( !a3 )
    return 3221225485LL;
  if ( (*a4 & 0xF8) != 0x18 )
    return 3221225485LL;
  v4 = (unsigned int)g_IndexToDataSize[*a4 & 7];
  v5 = a3 - v4 - 1;
  if ( !v5 )
    return 3221225485LL;
  v6 = a4[v4 + 1];
  if ( (v6 & 0xF8) != 8 )
    return 3221225485LL;
  if ( g_IndexToDataSize[v6 & 7] != 2 )
    return 3221225485LL;
  result = (unsigned int)(v5 - 3);
  if ( v5 != 3 )
    return 3221225485LL;
  return result;
}

```

## disassembly

```asm
0x140035570  test    r8d, r8d
0x140035573  jz      short loc_1400355BC
0x140035575  movzx   ecx, byte ptr [r9]
0x140035579  mov     al, cl
0x14003557b  and     al, 0F8h
0x14003557d  cmp     al, 18h
0x14003557f  jnz     short loc_1400355BC
0x140035581  mov     eax, ecx
0x140035583  lea     rdx, g_IndexToDataSize
0x14003558a  and     eax, 7
0x14003558d  mov     ecx, [rdx+rax*4]
0x140035590  sub     r8d, ecx
0x140035593  sub     r8d, 1
0x140035597  jz      short loc_1400355BC
0x140035599  movzx   ecx, byte ptr [rcx+r9+1]
0x14003559f  mov     al, cl
0x1400355a1  and     al, 0F8h
0x1400355a3  cmp     al, 8
0x1400355a5  jnz     short loc_1400355BC
0x1400355a7  mov     eax, ecx
0x1400355a9  and     eax, 7
0x1400355ac  cmp     dword ptr [rdx+rax*4], 2
0x1400355b0  jnz     short loc_1400355BC
0x1400355b2  lea     eax, [r8-3]
0x1400355b6  test    eax, eax
0x1400355b8  jnz     short loc_1400355BC
0x1400355ba  retn
0x1400355bc  mov     eax, 0C000000Dh
0x1400355c1  retn
```
