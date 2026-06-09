# StringCchCopyA(char *,unsigned __int64,char const *)

- ea: `0x1800058a0`
- end: `0x180005909`
- name: `?StringCchCopyA@@YAJPEAD_KPEBD@Z`
- size: `105`
- prototype: `__int64 __fastcall(char *, unsigned __int64, char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007a60`
- `0x180008430`

## callees

- `0x1800058a0`

## pseudocode

```c
__int64 __fastcall StringCchCopyA(char *a1, unsigned __int64 a2, char *a3)
{
  char *v3; // r9
  __int64 result; // rax
  __int64 v5; // rax
  char *v6; // rax

  v3 = a1;
  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*a3 )
        break;
      *v3++ = *a3++;
      --v5;
      --a2;
    }
    while ( a2 );
    v6 = v3 - 1;
    if ( a2 )
      v6 = v3;
    *v6 = 0;
    result = 2147942522LL;
    if ( a2 )
      return 0;
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
0x1800058a0  mov     r9, rcx
0x1800058a3  test    rdx, rdx
0x1800058a6  jz      short loc_1800058FB
0x1800058a8  cmp     rdx, 7FFFFFFFh
0x1800058af  jbe     short loc_1800058B8
0x1800058b1  mov     eax, 80070057h
0x1800058b6  jmp     short loc_180005905
0x1800058b8  mov     eax, 7FFFFFFEh
0x1800058bd  nop     dword ptr [rax]
0x1800058c0  test    rax, rax
0x1800058c3  jz      short loc_1800058DF
0x1800058c5  movzx   ecx, byte ptr [r8]
0x1800058c9  test    cl, cl
0x1800058cb  jz      short loc_1800058DF
0x1800058cd  mov     [r9], cl
0x1800058d0  inc     r8
0x1800058d3  inc     r9
0x1800058d6  dec     rax
0x1800058d9  sub     rdx, 1
0x1800058dd  jnz     short loc_1800058C0
0x1800058df  test    rdx, rdx
0x1800058e2  lea     rax, [r9-1]
0x1800058e6  cmovnz  rax, r9
0x1800058ea  xor     ecx, ecx
0x1800058ec  test    rdx, rdx
0x1800058ef  mov     byte ptr [rax], 0
0x1800058f2  mov     eax, 8007007Ah
0x1800058f7  cmovnz  eax, ecx
0x1800058fa  retn
0x1800058fb  mov     eax, 80070057h
0x180005900  test    rdx, rdx
0x180005903  jz      short locret_180005908
0x180005905  mov     byte ptr [rcx], 0
0x180005908  retn
```
