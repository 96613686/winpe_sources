# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180004680`
- end: `0x1800046ed`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `109`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005f54`

## callees

- `0x180004680`

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
0x180004680  mov     r9, rcx
0x180004683  test    rdx, rdx
0x180004686  jz      short loc_1800046DC
0x180004688  cmp     rdx, 7FFFFFFFh
0x18000468f  ja      short loc_1800046D5
0x180004691  mov     eax, 7FFFFFFEh
0x180004696  test    rax, rax
0x180004699  jz      short loc_1800046B9
0x18000469b  movzx   ecx, word ptr [r8]
0x18000469f  test    cx, cx
0x1800046a2  jz      short loc_1800046B9
0x1800046a4  mov     [r9], cx
0x1800046a8  add     r8, 2
0x1800046ac  add     r9, 2
0x1800046b0  dec     rax
0x1800046b3  sub     rdx, 1
0x1800046b7  jnz     short loc_180004696
0x1800046b9  test    rdx, rdx
0x1800046bc  lea     rax, [r9-2]
0x1800046c0  cmovnz  rax, r9
0x1800046c4  xor     ecx, ecx
0x1800046c6  test    rdx, rdx
0x1800046c9  mov     [rax], cx
0x1800046cc  mov     eax, 8007007Ah
0x1800046d1  cmovnz  eax, ecx
0x1800046d4  retn
0x1800046d5  mov     eax, 80070057h
0x1800046da  jmp     short loc_1800046E6
0x1800046dc  mov     eax, 80070057h
0x1800046e1  test    rdx, rdx
0x1800046e4  jz      short locret_1800046D4
0x1800046e6  xor     ecx, ecx
0x1800046e8  mov     [r9], cx
0x1800046ec  retn
```
