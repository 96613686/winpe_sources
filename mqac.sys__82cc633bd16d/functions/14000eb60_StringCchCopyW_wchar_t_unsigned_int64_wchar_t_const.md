# StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)

- ea: `0x14000eb60`
- end: `0x14000ebcb`
- name: `?StringCchCopyW@@YAJPEA_W_KPEB_W@Z`
- size: `107`
- prototype: `__int64 __fastcall(wchar_t *, unsigned __int64, const wchar_t *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e834`
- `0x14001916c`
- `0x14001919c`
- `0x140019254`
- `0x14001d1e8`
- `0x14001e768`

## callees

- `0x14000eb60`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(wchar_t *a1, unsigned __int64 a2, wchar_t *a3)
{
  wchar_t *v3; // r9
  __int64 result; // rax
  __int64 v5; // rax

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
    a1 = v3 - 1;
    if ( a2 )
      a1 = v3;
    result = a2 == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = 2147942487LL;
  }
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x14000eb60  xor     r10d, r10d
0x14000eb63  mov     r9, rcx
0x14000eb66  test    rdx, rdx
0x14000eb69  jz      short loc_14000EBBC
0x14000eb6b  cmp     rdx, 7FFFFFFFh
0x14000eb72  jbe     short loc_14000EB7B
0x14000eb74  mov     eax, 80070057h
0x14000eb79  jmp     short loc_14000EBC6
0x14000eb7b  mov     eax, 7FFFFFFEh
0x14000eb80  test    rax, rax
0x14000eb83  jz      short loc_14000EBA3
0x14000eb85  movzx   ecx, word ptr [r8]
0x14000eb89  test    cx, cx
0x14000eb8c  jz      short loc_14000EBA3
0x14000eb8e  mov     [r9], cx
0x14000eb92  add     r8, 2
0x14000eb96  add     r9, 2
0x14000eb9a  dec     rax
0x14000eb9d  sub     rdx, 1
0x14000eba1  jnz     short loc_14000EB80
0x14000eba3  test    rdx, rdx
0x14000eba6  lea     rcx, [r9-2]
0x14000ebaa  cmovnz  rcx, r9
0x14000ebae  neg     rdx
0x14000ebb1  sbb     eax, eax
0x14000ebb3  not     eax
0x14000ebb5  and     eax, 8007007Ah
0x14000ebba  jmp     short loc_14000EBC6
0x14000ebbc  mov     eax, 80070057h
0x14000ebc1  test    rdx, rdx
0x14000ebc4  jz      short locret_14000EBCA
0x14000ebc6  mov     [rcx], r10w
0x14000ebca  retn
```
