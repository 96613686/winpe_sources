# CHashTable<CTagEntry *>::Hash(wchar_t const *,uint)

- ea: `0x180021830`
- end: `0x180021864`
- name: `?Hash@?$CHashTable@PEAVCTagEntry@@@@EEAAIPEB_WI@Z`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180021830`

## pseudocode

```c
__int64 __fastcall CHashTable<CTagEntry *>::Hash(__int64 a1, unsigned __int16 *a2, int a3)
{
  unsigned int i; // r9d
  int v4; // eax

  for ( i = 0; a3; --a3 )
  {
    v4 = *a2++;
    i = v4 + 31 * i;
  }
  return i % 0xC7;
}

```

## disassembly

```asm
0x180021830  xor     r9d, r9d
0x180021833  test    r8d, r8d
0x180021836  jz      short loc_18002184C
0x180021838  movzx   eax, word ptr [rdx]
0x18002183b  lea     rdx, [rdx+2]
0x18002183f  imul    r9d, 1Fh
0x180021843  add     r9d, eax
0x180021846  add     r8d, 0FFFFFFFFh
0x18002184a  jnz     short loc_180021838
0x18002184c  mov     eax, 5254E78Fh
0x180021851  mul     r9d
0x180021854  shr     edx, 6
0x180021857  imul    ecx, edx, 0C7h
0x18002185d  sub     r9d, ecx
0x180021860  mov     eax, r9d
0x180021863  retn
```
