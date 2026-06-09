# CLogIocb::GetFirstRecord(void)

- ea: `0x18001067c`
- end: `0x1800106f0`
- name: `?GetFirstRecord@CLogIocb@@QEAAPEAU_CLFS_RECORD_HEADER@@XZ`
- size: `116`
- prototype: `struct _CLFS_RECORD_HEADER *__fastcall(CLogIocb *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800113dc`
- `0x18001195c`
- `0x180011cfc`
- `0x1800124f0`
- `0x180012e18`

## callees

- `0x18001067c`

## pseudocode

```c
struct _CLFS_RECORD_HEADER *__fastcall CLogIocb::GetFirstRecord(CLogIocb *this)
{
  __int64 v1; // rax
  __int64 v2; // rcx
  unsigned int v3; // r8d
  __int64 v4; // rdx

  v1 = *((_QWORD *)this + 14);
  v2 = *(unsigned int *)(v1 + 40);
  if ( !(_DWORD)v2 )
    return 0;
  v3 = *(unsigned __int16 *)(v1 + 4) << 9;
  if ( (unsigned int)v2 > v3 )
    return 0;
  v4 = v2 + v1;
  if ( (*(_BYTE *)(v2 + v1 + 36) & 4) == 0
    || !v4
    || (*(_DWORD *)v4 & 0x1FF) == 0x1FF
    || (*(_BYTE *)(v4 + 36) & 0x3F) == 0
    || (*(_BYTE *)(v4 + 36) & 0xC0) != 0
    || *(_WORD *)(v4 + 34) < 0x28u
    || (unsigned int)*(unsigned __int16 *)(v4 + 34) > *(_DWORD *)(v4 + 24)
    || (unsigned int)v2 + (unsigned __int64)*(unsigned int *)(v4 + 24) > v3 )
  {
    return 0;
  }
  return (struct _CLFS_RECORD_HEADER *)v4;
}

```

## disassembly

```asm
0x18001067c  mov     rax, [rcx+70h]
0x180010680  mov     ecx, [rax+28h]
0x180010683  test    ecx, ecx
0x180010685  jz      short loc_1800106ED
0x180010687  movzx   r8d, word ptr [rax+4]
0x18001068c  shl     r8d, 9
0x180010690  cmp     ecx, r8d
0x180010693  ja      short loc_1800106ED
0x180010695  lea     rdx, [rcx+rax]
0x180010699  mov     r9d, ecx
0x18001069c  test    byte ptr [rdx+24h], 4
0x1800106a0  jz      short loc_1800106E6
0x1800106a2  test    rdx, rdx
0x1800106a5  jz      short loc_1800106E6
0x1800106a7  mov     eax, [rdx]
0x1800106a9  mov     ecx, 1FFh
0x1800106ae  and     eax, ecx
0x1800106b0  cmp     eax, ecx
0x1800106b2  jnb     short loc_1800106E6
0x1800106b4  test    byte ptr [rdx+24h], 3Fh
0x1800106b8  jz      short loc_1800106E6
0x1800106ba  test    byte ptr [rdx+24h], 0C0h
0x1800106be  jnz     short loc_1800106E6
0x1800106c0  cmp     word ptr [rdx+22h], 28h ; '('
0x1800106c5  jb      short loc_1800106E6
0x1800106c7  movzx   eax, word ptr [rdx+22h]
0x1800106cb  cmp     eax, [rdx+18h]
0x1800106ce  ja      short loc_1800106E6
0x1800106d0  mov     eax, [rdx+18h]
0x1800106d3  add     rax, r9
0x1800106d6  mov     rcx, rax
0x1800106d9  shr     rcx, 20h
0x1800106dd  test    ecx, ecx
0x1800106df  jnz     short loc_1800106E6
0x1800106e1  cmp     eax, r8d
0x1800106e4  jbe     short loc_1800106E8
0x1800106e6  xor     edx, edx
0x1800106e8  mov     rax, rdx
0x1800106eb  retn
0x1800106ed  xor     eax, eax
0x1800106ef  retn
```
