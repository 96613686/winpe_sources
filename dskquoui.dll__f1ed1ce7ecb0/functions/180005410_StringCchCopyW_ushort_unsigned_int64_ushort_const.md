# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180005410`
- end: `0x18000547b`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b090`
- `0x18000f620`
- `0x18001a1f4`
- `0x18001a5f0`
- `0x18001ac28`
- `0x18001acac`
- `0x18001b014`
- `0x18001bd20`

## callees

- `0x180005410`

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
0x180005410  xor     r10d, r10d
0x180005413  mov     r9, rcx
0x180005416  test    rdx, rdx
0x180005419  jz      short loc_18000546C
0x18000541b  cmp     rdx, 7FFFFFFFh
0x180005422  jbe     short loc_18000542B
0x180005424  mov     eax, 80070057h
0x180005429  jmp     short loc_180005476
0x18000542b  mov     eax, 7FFFFFFEh
0x180005430  test    rax, rax
0x180005433  jz      short loc_180005453
0x180005435  movzx   ecx, word ptr [r8]
0x180005439  test    cx, cx
0x18000543c  jz      short loc_180005453
0x18000543e  mov     [r9], cx
0x180005442  add     r8, 2
0x180005446  add     r9, 2
0x18000544a  dec     rax
0x18000544d  sub     rdx, 1
0x180005451  jnz     short loc_180005430
0x180005453  test    rdx, rdx
0x180005456  lea     rcx, [r9-2]
0x18000545a  cmovnz  rcx, r9
0x18000545e  neg     rdx
0x180005461  sbb     eax, eax
0x180005463  not     eax
0x180005465  and     eax, 8007007Ah
0x18000546a  jmp     short loc_180005476
0x18000546c  mov     eax, 80070057h
0x180005471  test    rdx, rdx
0x180005474  jz      short locret_18000547A
0x180005476  mov     [rcx], r10w
0x18000547a  retn
```
