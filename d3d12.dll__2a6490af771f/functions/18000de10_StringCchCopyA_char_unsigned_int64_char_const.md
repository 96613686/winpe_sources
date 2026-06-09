# StringCchCopyA(char *,unsigned __int64,char const *)

- ea: `0x18000de10`
- end: `0x18000de72`
- name: `?StringCchCopyA@@YAJPEAD_KPEBD@Z`
- size: `98`
- prototype: `__int64 __fastcall(char *, unsigned __int64, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d1f4`
- `0x180010ae0`
- `0x180010d8c`
- `0x1800111b8`
- `0x18001153c`
- `0x180013750`

## callees

- `0x18000de10`

## pseudocode

```c
__int64 __fastcall StringCchCopyA(char *a1, unsigned __int64 a2, char *a3)
{
  __int64 result; // rax
  __int64 v4; // rax
  char *v5; // rax

  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*a3 )
        break;
      *a1++ = *a3++;
      --v4;
      --a2;
    }
    while ( a2 );
    v5 = a1 - 1;
    if ( a2 )
      v5 = a1;
    *v5 = 0;
    return a2 == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000de10  test    rdx, rdx
0x18000de13  jz      short loc_18000DE64
0x18000de15  cmp     rdx, 7FFFFFFFh
0x18000de1c  jbe     short loc_18000DE25
0x18000de1e  mov     eax, 80070057h
0x18000de23  jmp     short loc_18000DE6E
0x18000de25  mov     eax, 7FFFFFFEh
0x18000de2a  test    rax, rax
0x18000de2d  jz      short loc_18000DE49
0x18000de2f  mov     r9b, [r8]
0x18000de32  test    r9b, r9b
0x18000de35  jz      short loc_18000DE49
0x18000de37  mov     [rcx], r9b
0x18000de3a  inc     r8
0x18000de3d  inc     rcx
0x18000de40  dec     rax
0x18000de43  sub     rdx, 1
0x18000de47  jnz     short loc_18000DE2A
0x18000de49  test    rdx, rdx
0x18000de4c  lea     rax, [rcx-1]
0x18000de50  cmovnz  rax, rcx
0x18000de54  neg     rdx
0x18000de57  mov     byte ptr [rax], 0
0x18000de5a  sbb     eax, eax
0x18000de5c  not     eax
0x18000de5e  and     eax, 8007007Ah
0x18000de63  retn
0x18000de64  mov     eax, 80070057h
0x18000de69  test    rdx, rdx
0x18000de6c  jz      short locret_18000DE71
0x18000de6e  mov     byte ptr [rcx], 0
0x18000de71  retn
```
