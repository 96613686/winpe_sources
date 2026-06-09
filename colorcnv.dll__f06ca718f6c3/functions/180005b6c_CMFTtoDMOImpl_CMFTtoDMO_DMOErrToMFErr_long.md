# CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)

- ea: `0x180005b6c`
- end: `0x180005b95`
- name: `?DMOErrToMFErr@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@IEAAJJ@Z`
- size: `41`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180005300`
- `0x180005400`
- `0x180005480`
- `0x1800056a0`
- `0x180009854`
- `0x18000d890`
- `0x18000d980`
- `0x18000d9b0`
- `0x18000da60`
- `0x18000db50`
- `0x18000db80`
- `0x18000dc10`

## callees

- `0x180005b6c`

## pseudocode

```c
__int64 __fastcall CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(__int64 a1, unsigned int a2)
{
  unsigned int i; // eax

  if ( a2 )
  {
    for ( i = 0; i < 6; ++i )
    {
      if ( LODWORD(`CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr'::`2'::s_DMOtoMFMap[i]) == a2 )
        return HIDWORD(`CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr'::`2'::s_DMOtoMFMap[i]);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180005b6c  test    edx, edx
0x180005b6e  jnz     short loc_180005B73
0x180005b70  mov     eax, edx
0x180005b72  retn
0x180005b73  xor     eax, eax
0x180005b75  lea     r8, ?s_DMOtoMFMap@?1??DMOErrToMFErr@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@IEAAJJ@Z@4QBU_DMOtoMFMap@?1??12@IEAAJJ@Z@B; `CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)'::`2'::_DMOtoMFMap const near * const `CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)'::`2'::s_DMOtoMFMap
0x180005b7c  cmp     eax, 6
0x180005b7f  jnb     short loc_180005B70
0x180005b81  movsxd  rcx, eax
0x180005b84  cmp     [r8+rcx*8], edx
0x180005b88  jz      short loc_180005B8E
0x180005b8a  inc     eax
0x180005b8c  jmp     short loc_180005B7C
0x180005b8e  mov     edx, [r8+rcx*8+4]
0x180005b93  jmp     short loc_180005B70
```
