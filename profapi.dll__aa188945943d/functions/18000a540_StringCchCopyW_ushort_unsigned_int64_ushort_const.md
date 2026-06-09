# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000a540`
- end: `0x18000a5b5`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `117`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c0f0`
- `0x18000d620`
- `0x180010e48`
- `0x180015d60`
- `0x180016400`
- `0x1800165d0`
- `0x180016834`
- `0x180016bec`
- `0x180016d14`

## callees

- `0x18000a540`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r9
  __int64 v4; // rax
  unsigned int v5; // r11d
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
    v5 = 0;
    while ( v4 && *a3 )
    {
      *v3++ = *a3++;
      --v4;
      if ( !--a2 )
      {
        --v3;
        v5 = -2147024774;
        break;
      }
    }
    *v3 = 0;
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18000a540  mov     r9, rcx
0x18000a543  test    rdx, rdx
0x18000a546  jz      short loc_18000A5A3
0x18000a548  cmp     rdx, 7FFFFFFFh
0x18000a54f  ja      short loc_18000A59C
0x18000a551  xor     r10d, r10d
0x18000a554  mov     eax, 7FFFFFFEh
0x18000a559  mov     r11d, r10d
0x18000a55c  nop     dword ptr [rax+00h]
0x18000a560  test    rax, rax
0x18000a563  jz      short loc_18000A594
0x18000a565  movzx   ecx, word ptr [r8]
0x18000a569  test    cx, cx
0x18000a56c  jz      short loc_18000A58F
0x18000a56e  mov     [r9], cx
0x18000a572  add     r8, 2
0x18000a576  add     r9, 2
0x18000a57a  dec     rax
0x18000a57d  sub     rdx, 1
0x18000a581  jnz     short loc_18000A560
0x18000a583  sub     r9, 2
0x18000a587  mov     r11d, 8007007Ah
0x18000a58d  jmp     short loc_18000A594
0x18000a58f  test    rdx, rdx
0x18000a592  jz      short loc_18000A583
0x18000a594  mov     [r9], r10w
0x18000a598  mov     eax, r11d
0x18000a59b  retn
0x18000a59c  mov     eax, 80070057h
0x18000a5a1  jmp     short loc_18000A5AD
0x18000a5a3  mov     eax, 80070057h
0x18000a5a8  test    rdx, rdx
0x18000a5ab  jz      short locret_18000A59B
0x18000a5ad  xor     r10d, r10d
0x18000a5b0  mov     [rcx], r10w
0x18000a5b4  retn
```
