# __mtdeletelocks

- ea: `0x10034ea8`
- end: `0x10034efc`
- name: `__mtdeletelocks`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1002f24b`

## callees

- `0x1002df32`
- `0x10034ea8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x10034ebf`
- `KERNEL32!DeleteCriticalSection` at `0x10034ee8`
- `KERNEL32!DeleteCriticalSection` at `0x10034ebf`
- `KERNEL32!DeleteCriticalSection` at `0x10034ee8`

## pseudocode

```c
void _mtdeletelocks()
{
  LPCRITICAL_SECTION *v0; // esi
  LPCRITICAL_SECTION *v1; // edi
  LPCRITICAL_SECTION v2; // ebx

  v0 = &lpCriticalSection;
  v1 = &lpCriticalSection;
  do
  {
    v2 = *v1;
    if ( *v1 && v1[1] != (LPCRITICAL_SECTION)1 )
    {
      DeleteCriticalSection(*v1);
      free(v2);
      *v1 = 0;
    }
    v1 += 2;
  }
  while ( (int)v1 < (int)&__lconv );
  do
  {
    if ( *v0 )
    {
      if ( v0[1] == (LPCRITICAL_SECTION)1 )
        DeleteCriticalSection(*v0);
    }
    v0 += 2;
  }
  while ( (int)v0 < (int)&__lconv );
}

```

## disassembly

```asm
0x10034ea8  push    esi
0x10034ea9  push    edi
0x10034eaa  mov     esi, offset lpCriticalSection
0x10034eaf  mov     edi, esi
0x10034eb1  push    ebx
0x10034eb2  mov     ebx, [edi]
0x10034eb4  test    ebx, ebx
0x10034eb6  jz      short loc_10034ECF
0x10034eb8  cmp     dword ptr [edi+4], 1
0x10034ebc  jz      short loc_10034ECF
0x10034ebe  push    ebx; lpCriticalSection
0x10034ebf  call    ds:__imp__DeleteCriticalSection@4
0x10034ec5  push    ebx; Block
0x10034ec6  call    _free
0x10034ecb  and     dword ptr [edi], 0
0x10034ece  pop     ecx
0x10034ecf  add     edi, 8
0x10034ed2  cmp     edi, offset ___lconv
0x10034ed8  jl      short loc_10034EB2
0x10034eda  pop     ebx
0x10034edb  cmp     dword ptr [esi], 0
0x10034ede  jz      short loc_10034EEE
0x10034ee0  cmp     dword ptr [esi+4], 1
0x10034ee4  jnz     short loc_10034EEE
0x10034ee6  push    dword ptr [esi]; lpCriticalSection
0x10034ee8  call    ds:__imp__DeleteCriticalSection@4
0x10034eee  add     esi, 8
0x10034ef1  cmp     esi, offset ___lconv
0x10034ef7  jl      short loc_10034EDB
0x10034ef9  pop     edi
0x10034efa  pop     esi
0x10034efb  retn
```
