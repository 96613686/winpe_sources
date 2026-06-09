# HashFNV::HashData(uchar *,ulong)

- ea: `0x180004ce8`
- end: `0x180004d19`
- name: `?HashData@HashFNV@@QEAA_KPEAEK@Z`
- size: `49`
- prototype: `unsigned __int64 __fastcall(HashFNV *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800027d4`
- `0x180004d20`

## callees

- `0x180004ce8`

## pseudocode

```c
unsigned __int64 __fastcall HashFNV::HashData(HashFNV *this, unsigned __int8 *a2, int a3)
{
  unsigned __int8 *v3; // r9
  __int64 v4; // r8
  __int64 v5; // rax

  v3 = &a2[a3];
  if ( a2 < v3 )
  {
    v4 = *(_QWORD *)this;
    do
    {
      v5 = *a2++;
      v4 = 0x100000001B3LL * (v5 ^ v4);
      *(_QWORD *)this = v4;
    }
    while ( a2 < v3 );
  }
  return *(_QWORD *)this;
}

```

## disassembly

```asm
0x180004ce8  mov     r9d, r8d
0x180004ceb  add     r9, rdx
0x180004cee  cmp     rdx, r9
0x180004cf1  jnb     short loc_180004D15
0x180004cf3  mov     r8, [rcx]
0x180004cf6  movzx   eax, byte ptr [rdx]
0x180004cf9  mov     r10, 100000001B3h
0x180004d03  xor     r8, rax
0x180004d06  inc     rdx
0x180004d09  imul    r8, r10
0x180004d0d  mov     [rcx], r8
0x180004d10  cmp     rdx, r9
0x180004d13  jb      short loc_180004CF6
0x180004d15  mov     rax, [rcx]
0x180004d18  retn
```
