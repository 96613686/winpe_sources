# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140009010`
- end: `0x14000905c`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `76`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140007ce0`
- `0x140011a6c`

## callees

- `0x140009010`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v4; // rax
  __int64 v5; // r9
  unsigned __int16 *v6; // rdx
  __int64 result; // rax

  v4 = 2147483646;
  v5 = 260;
  do
  {
    if ( !v4 )
      break;
    if ( !*a3 )
      break;
    *a1++ = *a3++;
    --v4;
    --v5;
  }
  while ( v5 );
  v6 = a1 - 1;
  result = 2147942522LL;
  if ( v5 )
  {
    v6 = a1;
    result = 0;
  }
  *v6 = 0;
  return result;
}

```

## disassembly

```asm
0x140009010  mov     r10, rcx
0x140009013  mov     eax, 7FFFFFFEh
0x140009018  mov     r9d, 104h
0x14000901e  xchg    ax, ax
0x140009020  test    rax, rax
0x140009023  jz      short loc_140009043
0x140009025  movzx   edx, word ptr [r8]
0x140009029  test    dx, dx
0x14000902c  jz      short loc_140009043
0x14000902e  mov     [r10], dx
0x140009032  add     r8, 2
0x140009036  add     r10, 2
0x14000903a  dec     rax
0x14000903d  sub     r9, 1
0x140009041  jnz     short loc_140009020
0x140009043  xor     ecx, ecx
0x140009045  lea     rdx, [r10-2]
0x140009049  test    r9, r9
0x14000904c  mov     eax, 8007007Ah
0x140009051  cmovnz  rdx, r10
0x140009055  cmovnz  eax, ecx
0x140009058  mov     [rdx], cx
0x14000905b  retn
```
