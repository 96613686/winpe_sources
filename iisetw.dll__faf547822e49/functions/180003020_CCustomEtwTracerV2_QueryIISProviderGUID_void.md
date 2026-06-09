# CCustomEtwTracerV2::QueryIISProviderGUID(void)

- ea: `0x180003020`
- end: `0x180003066`
- name: `?QueryIISProviderGUID@CCustomEtwTracerV2@@QEAAPEBU_GUID@@XZ`
- size: `70`
- prototype: `const struct _GUID *__fastcall(CCustomEtwTracerV2 *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002500`
- `0x1800025e0`
- `0x1800026bc`

## callees

- `0x180003020`

## pseudocode

```c
const struct _GUID *__fastcall CCustomEtwTracerV2::QueryIISProviderGUID(CCustomEtwTracerV2 *this)
{
  unsigned int v1; // edx
  GUID *v2; // r9

  v1 = 0;
  if ( !off_180007000[0] )
    return 0;
  while ( 1 )
  {
    v2 = off_180007000[2 * v1];
    if ( *(_QWORD *)&v2->Data1 == *(_QWORD *)((char *)this + 28)
      && *(_QWORD *)v2->Data4 == *(_QWORD *)((char *)this + 36) )
    {
      break;
    }
    if ( !off_180007000[2 * ++v1] )
      return 0;
  }
  return off_180007000[2 * v1 + 1];
}

```

## disassembly

```asm
0x180003020  xor     edx, edx
0x180003022  cmp     cs:off_180007000, rdx
0x180003029  jz      short loc_18000305D
0x18000302b  lea     r10, off_180007000
0x180003032  mov     r8d, edx
0x180003035  add     r8, r8
0x180003038  mov     r9, [r10+r8*8]
0x18000303c  mov     rax, [r9]
0x18000303f  cmp     rax, [rcx+1Ch]
0x180003043  jnz     short loc_18000304F
0x180003045  mov     rax, [r9+8]
0x180003049  cmp     rax, [rcx+24h]
0x18000304d  jz      short loc_180003060
0x18000304f  inc     edx
0x180003051  mov     eax, edx
0x180003053  add     rax, rax
0x180003056  cmp     qword ptr [r10+rax*8], 0
0x18000305b  jnz     short loc_180003032
0x18000305d  xor     eax, eax
0x18000305f  retn
0x180003060  mov     rax, [r10+r8*8+8]
0x180003065  retn
```
