# RtlStringCchCopyA

- ea: `0x18001cb48`
- end: `0x18001cb91`
- name: `RtlStringCchCopyA`
- size: `73`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PSTR pszDest, size_t cchDest, NTSTRSAFE_PCSTR pszSrc)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003845c`

## callees

- `0x18001cb48`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCchCopyA(NTSTRSAFE_PSTR pszDest, size_t cchDest, NTSTRSAFE_PCSTR pszSrc)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  NTSTRSAFE_PSTR v6; // rcx
  NTSTATUS result; // eax

  v4 = 2147483646;
  v5 = 16;
  do
  {
    if ( !v4 )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --v4;
    --v5;
  }
  while ( v5 );
  v6 = pszDest - 1;
  result = v5 == 0 ? 0x80000005 : 0;
  if ( v5 )
    v6 = pszDest;
  *v6 = 0;
  return result;
}

```

## disassembly

```asm
0x18001cb48  mov     r9, rcx
0x18001cb4b  mov     eax, 7FFFFFFEh
0x18001cb50  mov     edx, 10h
0x18001cb55  test    rax, rax
0x18001cb58  jz      short loc_18001CB73
0x18001cb5a  mov     cl, [r8]
0x18001cb5d  test    cl, cl
0x18001cb5f  jz      short loc_18001CB73
0x18001cb61  mov     [r9], cl
0x18001cb64  inc     r8
0x18001cb67  inc     r9
0x18001cb6a  dec     rax
0x18001cb6d  sub     rdx, 1
0x18001cb71  jnz     short loc_18001CB55
0x18001cb73  mov     rax, rdx
0x18001cb76  lea     rcx, [r9-1]
0x18001cb7a  neg     rax
0x18001cb7d  sbb     eax, eax
0x18001cb7f  not     eax
0x18001cb81  and     eax, 80000005h
0x18001cb86  test    rdx, rdx
0x18001cb89  cmovnz  rcx, r9
0x18001cb8d  mov     byte ptr [rcx], 0
0x18001cb90  retn
```
