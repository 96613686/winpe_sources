# LKRhash::CTypedHashTable<SnapinCLSIDTable,SnapinRecord,CStr const *,LKRhash::CLKRLinearHashTable>::_CalcKeyHash(unsigned __int64)

- ea: `0x18000e490`
- end: `0x18000e4c5`
- name: `?_CalcKeyHash@?$CTypedHashTable@VSnapinCLSIDTable@@VSnapinRecord@@PEBVCStr@@VCLKRLinearHashTable@LKRhash@@@LKRhash@@CAK_K@Z`
- size: `53`
- prototype: `unsigned int(unsigned __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000e490`

## pseudocode

```c
__int64 __fastcall LKRhash::CTypedHashTable<SnapinCLSIDTable,SnapinRecord,CStr const *,LKRhash::CLKRLinearHashTable>::_CalcKeyHash(
        __int64 a1)
{
  unsigned int v1; // edx
  unsigned __int64 v2; // r10
  unsigned __int64 v3; // r9
  __int16 *i; // r8
  __int16 v5; // cx

  v1 = 0;
  if ( a1 )
  {
    v2 = *(unsigned int *)(a1 + 16);
    v3 = 0;
    for ( i = *(__int16 **)(a1 + 8); v3 < v2; v1 = (v5 & 0xFFDF) + 101 * v1 )
    {
      v5 = *i;
      ++v3;
      ++i;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18000e490  xor     edx, edx
0x18000e492  test    rcx, rcx
0x18000e495  jz      short loc_18000E4C2
0x18000e497  mov     r10d, [rcx+10h]
0x18000e49b  xor     r9d, r9d
0x18000e49e  mov     r8, [rcx+8]
0x18000e4a2  test    r10, r10
0x18000e4a5  jz      short loc_18000E4C2
0x18000e4a7  movzx   ecx, word ptr [r8]
0x18000e4ab  inc     r9
0x18000e4ae  imul    edx, 65h ; 'e'
0x18000e4b1  lea     r8, [r8+2]
0x18000e4b5  and     ecx, 0FFDFh
0x18000e4bb  add     edx, ecx
0x18000e4bd  cmp     r9, r10
0x18000e4c0  jb      short loc_18000E4A7
0x18000e4c2  mov     eax, edx
0x18000e4c4  retn
```
