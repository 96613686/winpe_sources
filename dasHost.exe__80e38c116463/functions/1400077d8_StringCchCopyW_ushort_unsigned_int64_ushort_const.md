# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1400077d8`
- end: `0x140007843`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000deb0`
- `0x14000ee44`
- `0x14000f1b8`
- `0x14000f48c`
- `0x14000f9d4`
- `0x14000faa8`

## callees

- `0x1400077d8`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r9
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
0x1400077d8  xor     r10d, r10d
0x1400077db  mov     r9, rcx
0x1400077de  test    rdx, rdx
0x1400077e1  jz      short loc_140007834
0x1400077e3  cmp     rdx, 7FFFFFFFh
0x1400077ea  jbe     short loc_1400077F3
0x1400077ec  mov     eax, 80070057h
0x1400077f1  jmp     short loc_14000783E
0x1400077f3  mov     eax, 7FFFFFFEh
0x1400077f8  test    rax, rax
0x1400077fb  jz      short loc_14000781B
0x1400077fd  movzx   ecx, word ptr [r8]
0x140007801  test    cx, cx
0x140007804  jz      short loc_14000781B
0x140007806  mov     [r9], cx
0x14000780a  add     r8, 2
0x14000780e  add     r9, 2
0x140007812  dec     rax
0x140007815  sub     rdx, 1
0x140007819  jnz     short loc_1400077F8
0x14000781b  test    rdx, rdx
0x14000781e  lea     rcx, [r9-2]
0x140007822  cmovnz  rcx, r9
0x140007826  neg     rdx
0x140007829  sbb     eax, eax
0x14000782b  not     eax
0x14000782d  and     eax, 8007007Ah
0x140007832  jmp     short loc_14000783E
0x140007834  mov     eax, 80070057h
0x140007839  test    rdx, rdx
0x14000783c  jz      short locret_140007842
0x14000783e  mov     [rcx], r10w
0x140007842  retn
```
