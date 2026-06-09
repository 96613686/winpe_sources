# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180006180`
- end: `0x1800061eb`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000485c`
- `0x1800049dc`
- `0x180008f30`
- `0x18000a300`
- `0x18000cca0`

## callees

- `0x180006180`

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
0x180006180  xor     r10d, r10d
0x180006183  mov     r9, rcx
0x180006186  test    rdx, rdx
0x180006189  jz      short loc_1800061DC
0x18000618b  cmp     rdx, 7FFFFFFFh
0x180006192  jbe     short loc_18000619B
0x180006194  mov     eax, 80070057h
0x180006199  jmp     short loc_1800061E6
0x18000619b  mov     eax, 7FFFFFFEh
0x1800061a0  test    rax, rax
0x1800061a3  jz      short loc_1800061C3
0x1800061a5  movzx   ecx, word ptr [r8]
0x1800061a9  test    cx, cx
0x1800061ac  jz      short loc_1800061C3
0x1800061ae  mov     [r9], cx
0x1800061b2  add     r8, 2
0x1800061b6  add     r9, 2
0x1800061ba  dec     rax
0x1800061bd  sub     rdx, 1
0x1800061c1  jnz     short loc_1800061A0
0x1800061c3  test    rdx, rdx
0x1800061c6  lea     rcx, [r9-2]
0x1800061ca  cmovnz  rcx, r9
0x1800061ce  neg     rdx
0x1800061d1  sbb     eax, eax
0x1800061d3  not     eax
0x1800061d5  and     eax, 8007007Ah
0x1800061da  jmp     short loc_1800061E6
0x1800061dc  mov     eax, 80070057h
0x1800061e1  test    rdx, rdx
0x1800061e4  jz      short locret_1800061EA
0x1800061e6  mov     [rcx], r10w
0x1800061ea  retn
```
