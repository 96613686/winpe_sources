# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180001840`
- end: `0x1800018ad`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `109`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `40`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x180001610`
- `0x180001770`
- `0x180004060`
- `0x180004590`
- `0x180005270`
- `0x180005cd0`
- `0x180007860`
- `0x18000807c`
- `0x180008688`
- `0x180009490`
- `0x18000b740`
- `0x18000b920`
- `0x18000bb50`
- `0x18000beb8`
- `0x18000c93c`
- `0x18000cae0`
- `0x18000cdcc`
- `0x18000cff4`
- `0x18000d650`
- `0x18000da50`
- `0x18000dc70`
- `0x18000dd40`
- `0x18000df10`
- `0x18000e578`
- `0x18000e7f8`
- `0x18000f850`
- `0x18000fc80`
- `0x18000ff30`
- `0x180010710`
- `0x180010b5c`
- `0x180010c90`
- `0x180011568`
- `0x180011fc0`
- `0x180012a04`
- `0x1800135a4`
- `0x180017f60`
- `0x180018300`
- `0x180019d4c`
- `0x18001a43c`

## callees

- `0x180001840`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r9
  __int64 v4; // rax
  unsigned __int16 *v5; // rax
  __int64 result; // rax

  v3 = a1;
  if ( !a2 )
    return 2147942487LL;
  if ( a2 > 0x7FFFFFFF )
  {
    result = 2147942487LL;
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
    result = 2147942522LL;
    if ( a2 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180001840  mov     r9, rcx
0x180001843  test    rdx, rdx
0x180001846  jz      short loc_18000189C
0x180001848  cmp     rdx, 7FFFFFFFh
0x18000184f  ja      short loc_180001895
0x180001851  mov     eax, 7FFFFFFEh
0x180001856  test    rax, rax
0x180001859  jz      short loc_180001879
0x18000185b  movzx   ecx, word ptr [r8]
0x18000185f  test    cx, cx
0x180001862  jz      short loc_180001879
0x180001864  mov     [r9], cx
0x180001868  add     r8, 2
0x18000186c  add     r9, 2
0x180001870  dec     rax
0x180001873  sub     rdx, 1
0x180001877  jnz     short loc_180001856
0x180001879  test    rdx, rdx
0x18000187c  lea     rax, [r9-2]
0x180001880  cmovnz  rax, r9
0x180001884  xor     ecx, ecx
0x180001886  test    rdx, rdx
0x180001889  mov     [rax], cx
0x18000188c  mov     eax, 8007007Ah
0x180001891  cmovnz  eax, ecx
0x180001894  retn
0x180001895  mov     eax, 80070057h
0x18000189a  jmp     short loc_1800018A6
0x18000189c  mov     eax, 80070057h
0x1800018a1  test    rdx, rdx
0x1800018a4  jz      short locret_180001894
0x1800018a6  xor     ecx, ecx
0x1800018a8  mov     [r9], cx
0x1800018ac  retn
```
