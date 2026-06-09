# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180006cac`
- end: `0x180006d17`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c290`

## callees

- `0x180006cac`

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
0x180006cac  xor     r10d, r10d
0x180006caf  mov     r9, rcx
0x180006cb2  test    rdx, rdx
0x180006cb5  jz      short loc_180006D08
0x180006cb7  cmp     rdx, 7FFFFFFFh
0x180006cbe  jbe     short loc_180006CC7
0x180006cc0  mov     eax, 80070057h
0x180006cc5  jmp     short loc_180006D12
0x180006cc7  mov     eax, 7FFFFFFEh
0x180006ccc  test    rax, rax
0x180006ccf  jz      short loc_180006CEF
0x180006cd1  movzx   ecx, word ptr [r8]
0x180006cd5  test    cx, cx
0x180006cd8  jz      short loc_180006CEF
0x180006cda  mov     [r9], cx
0x180006cde  add     r8, 2
0x180006ce2  add     r9, 2
0x180006ce6  dec     rax
0x180006ce9  sub     rdx, 1
0x180006ced  jnz     short loc_180006CCC
0x180006cef  test    rdx, rdx
0x180006cf2  lea     rcx, [r9-2]
0x180006cf6  cmovnz  rcx, r9
0x180006cfa  neg     rdx
0x180006cfd  sbb     eax, eax
0x180006cff  not     eax
0x180006d01  and     eax, 8007007Ah
0x180006d06  jmp     short loc_180006D12
0x180006d08  mov     eax, 80070057h
0x180006d0d  test    rdx, rdx
0x180006d10  jz      short locret_180006D16
0x180006d12  mov     [rcx], r10w
0x180006d16  retn
```
