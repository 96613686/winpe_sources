# GetGenericSize

- ea: `0x18001a2cc`
- end: `0x18001a340`
- name: `GetGenericSize`
- size: `116`
- prototype: ``
- caller_count: `28`
- callee_count: `1`
- tags: ``

## callers

- `0x180008714`
- `0x1800087e8`
- `0x1800089c8`
- `0x180009544`
- `0x180009978`
- `0x18000b888`
- `0x18000bdd4`
- `0x18000c350`
- `0x18000d45c`
- `0x18000d808`
- `0x18000d8e4`
- `0x18000de24`
- `0x18000f364`
- `0x18000fad8`
- `0x18000fd08`
- `0x180010088`
- `0x180010284`
- `0x1800109fc`
- `0x180010fd4`
- `0x1800115ac`
- `0x1800118bc`
- `0x180012154`
- `0x180013364`
- `0x1800154a4`
- `0x180016e9c`
- `0x180017a48`
- `0x180017b6c`
- `0x180019b18`

## callees

- `0x18001a2cc`

## pseudocode

```c
__int64 __fastcall GetGenericSize(unsigned __int8 *a1)
{
  unsigned __int16 v1; // dx
  unsigned __int16 i; // r9
  unsigned __int8 v3; // r8
  unsigned __int16 v4; // ax

  v1 = 0;
  for ( i = 1; i <= *a1; ++i )
  {
    v3 = a1[i];
    if ( (v3 & 7) == 1 )
    {
      if ( (v3 & 0x10) == 0 )
        ++v1;
    }
    else
    {
      if ( (a1[i] & 7) == 2 )
      {
        v4 = v1 + 2;
      }
      else
      {
        if ( (a1[i] & 7) != 4 )
          return 0;
        v4 = v1 + 4;
      }
      if ( (v3 & 0x10) != 0 )
        v4 = v1;
      v1 = v4;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18001a2cc  mov     [rsp+arg_0], rbx
0x18001a2d1  mov     [rsp+arg_8], rsi
0x18001a2d6  movzx   r11d, byte ptr [rcx]
0x18001a2da  xor     edx, edx
0x18001a2dc  mov     r10, rcx
0x18001a2df  lea     ebx, [rdx+1]
0x18001a2e2  movzx   r9d, bx
0x18001a2e6  lea     esi, [rdx+2]
0x18001a2e9  cmp     r9w, r11w
0x18001a2ed  ja      short loc_18001A332
0x18001a2ef  movzx   eax, r9w
0x18001a2f3  movzx   r8d, byte ptr [rax+r10]
0x18001a2f8  mov     ecx, r8d
0x18001a2fb  and     ecx, 7
0x18001a2fe  sub     ecx, ebx
0x18001a300  jz      short loc_18001A31F
0x18001a302  sub     ecx, ebx
0x18001a304  jz      short loc_18001A30F
0x18001a306  cmp     ecx, esi
0x18001a308  jnz     short loc_18001A32E
0x18001a30a  lea     eax, [rdx+4]
0x18001a30d  jmp     short loc_18001A312
0x18001a30f  lea     eax, [rsi+rdx]
0x18001a312  test    r8b, 10h
0x18001a316  cmovnz  ax, dx
0x18001a31a  movzx   edx, ax
0x18001a31d  jmp     short loc_18001A328
0x18001a31f  test    r8b, 10h
0x18001a323  jnz     short loc_18001A328
0x18001a325  add     dx, bx
0x18001a328  add     r9w, bx
0x18001a32c  jmp     short loc_18001A2E9
0x18001a32e  xor     eax, eax
0x18001a330  jmp     short loc_18001A335
0x18001a332  movzx   eax, dx
0x18001a335  mov     rbx, [rsp+arg_0]
0x18001a33a  mov     rsi, [rsp+arg_8]
0x18001a33f  retn
```
