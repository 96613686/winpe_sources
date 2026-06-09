# RtlStringCchCopyA(char *,unsigned __int64,char const *)

- ea: `0x180005430`
- end: `0x180005496`
- name: `?RtlStringCchCopyA@@YAJPEAD_KPEBD@Z`
- size: `102`
- prototype: `__int64 __fastcall(char *, unsigned __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800092ac`

## callees

- `0x180005430`

## pseudocode

```c
__int64 __fastcall RtlStringCchCopyA(char *a1, unsigned __int64 a2, char *a3)
{
  char *v3; // r9
  __int64 v4; // rax
  char *v5; // rax
  __int64 result; // rax

  v3 = a1;
  if ( !a2 )
    return 3221225485LL;
  if ( a2 > 0x7FFFFFFF )
  {
    result = 3221225485LL;
    *a1 = 0;
  }
  else
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*a3 )
        break;
      *v3++ = *a3++;
      --v4;
      --a2;
    }
    while ( a2 );
    v5 = v3 - 1;
    if ( a2 )
      v5 = v3;
    *v5 = 0;
    result = 2147483653LL;
    if ( a2 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005430  mov     r9, rcx
0x180005433  test    rdx, rdx
0x180005436  jz      short loc_180005488
0x180005438  cmp     rdx, 7FFFFFFFh
0x18000543f  ja      short loc_180005481
0x180005441  mov     eax, 7FFFFFFEh
0x180005446  test    rax, rax
0x180005449  jz      short loc_180005465
0x18000544b  movzx   ecx, byte ptr [r8]
0x18000544f  test    cl, cl
0x180005451  jz      short loc_180005465
0x180005453  mov     [r9], cl
0x180005456  inc     r8
0x180005459  inc     r9
0x18000545c  dec     rax
0x18000545f  sub     rdx, 1
0x180005463  jnz     short loc_180005446
0x180005465  test    rdx, rdx
0x180005468  lea     rax, [r9-1]
0x18000546c  cmovnz  rax, r9
0x180005470  xor     ecx, ecx
0x180005472  test    rdx, rdx
0x180005475  mov     byte ptr [rax], 0
0x180005478  mov     eax, 80000005h
0x18000547d  cmovnz  eax, ecx
0x180005480  retn
0x180005481  mov     eax, 0C000000Dh
0x180005486  jmp     short loc_180005492
0x180005488  mov     eax, 0C000000Dh
0x18000548d  test    rdx, rdx
0x180005490  jz      short locret_180005480
0x180005492  mov     byte ptr [rcx], 0
0x180005495  retn
```
