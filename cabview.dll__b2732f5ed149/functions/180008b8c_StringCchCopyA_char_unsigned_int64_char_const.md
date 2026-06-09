# StringCchCopyA(char *,unsigned __int64,char const *)

- ea: `0x180008b8c`
- end: `0x180008bee`
- name: `?StringCchCopyA@@YAJPEAD_KPEBD@Z`
- size: `98`
- prototype: `__int64 __fastcall(char *, unsigned __int64, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004a70`
- `0x180006090`
- `0x180008898`

## callees

- `0x180008b8c`

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
0x180008b8c  test    rdx, rdx
0x180008b8f  jz      short loc_180008BE0
0x180008b91  cmp     rdx, 7FFFFFFFh
0x180008b98  jbe     short loc_180008BA1
0x180008b9a  mov     eax, 80070057h
0x180008b9f  jmp     short loc_180008BEA
0x180008ba1  mov     eax, 7FFFFFFEh
0x180008ba6  test    rax, rax
0x180008ba9  jz      short loc_180008BC5
0x180008bab  mov     r9b, [r8]
0x180008bae  test    r9b, r9b
0x180008bb1  jz      short loc_180008BC5
0x180008bb3  mov     [rcx], r9b
0x180008bb6  inc     r8
0x180008bb9  inc     rcx
0x180008bbc  dec     rax
0x180008bbf  sub     rdx, 1
0x180008bc3  jnz     short loc_180008BA6
0x180008bc5  test    rdx, rdx
0x180008bc8  lea     rax, [rcx-1]
0x180008bcc  cmovnz  rax, rcx
0x180008bd0  neg     rdx
0x180008bd3  mov     byte ptr [rax], 0
0x180008bd6  sbb     eax, eax
0x180008bd8  not     eax
0x180008bda  and     eax, 8007007Ah
0x180008bdf  retn
0x180008be0  mov     eax, 80070057h
0x180008be5  test    rdx, rdx
0x180008be8  jz      short locret_180008BED
0x180008bea  mov     byte ptr [rcx], 0
0x180008bed  retn
```
