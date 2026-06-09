# StringCchCopyA(char *,unsigned __int64,char const *)

- ea: `0x180005a84`
- end: `0x180005ae6`
- name: `?StringCchCopyA@@YAJPEAD_KPEBD@Z`
- size: `98`
- prototype: `__int64 __fastcall(char *, unsigned __int64, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800052dc`

## callees

- `0x180005a84`

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
0x180005a84  test    rdx, rdx
0x180005a87  jz      short loc_180005AD8
0x180005a89  cmp     rdx, 7FFFFFFFh
0x180005a90  jbe     short loc_180005A99
0x180005a92  mov     eax, 80070057h
0x180005a97  jmp     short loc_180005AE2
0x180005a99  mov     eax, 7FFFFFFEh
0x180005a9e  test    rax, rax
0x180005aa1  jz      short loc_180005ABD
0x180005aa3  mov     r9b, [r8]
0x180005aa6  test    r9b, r9b
0x180005aa9  jz      short loc_180005ABD
0x180005aab  mov     [rcx], r9b
0x180005aae  inc     r8
0x180005ab1  inc     rcx
0x180005ab4  dec     rax
0x180005ab7  sub     rdx, 1
0x180005abb  jnz     short loc_180005A9E
0x180005abd  test    rdx, rdx
0x180005ac0  lea     rax, [rcx-1]
0x180005ac4  cmovnz  rax, rcx
0x180005ac8  neg     rdx
0x180005acb  mov     byte ptr [rax], 0
0x180005ace  sbb     eax, eax
0x180005ad0  not     eax
0x180005ad2  and     eax, 8007007Ah
0x180005ad7  retn
0x180005ad8  mov     eax, 80070057h
0x180005add  test    rdx, rdx
0x180005ae0  jz      short locret_180005AE5
0x180005ae2  mov     byte ptr [rcx], 0
0x180005ae5  retn
```
