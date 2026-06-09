# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800053bc`
- end: `0x180005477`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000550c`
- `0x180005f70`
- `0x180006518`

## callees

- `0x1800053bc`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // r10
  __int64 v5; // r11
  unsigned __int16 *v6; // rax
  unsigned int v7; // edx
  __int64 v8; // rax
  __int64 v9; // r9
  unsigned __int16 *i; // rax
  unsigned __int16 *v11; // rcx

  v3 = 2147483646;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v5 = a2;
    v6 = a1;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v5;
    }
    while ( v5 );
    v7 = v5 == 0 ? 0x80070057 : 0;
    v8 = (a2 - v5) & -(__int64)(v5 != 0);
    if ( v5 )
    {
      v9 = a2 - v8;
      for ( i = &a1[v8]; v9; --v9 )
      {
        if ( !v3 )
          break;
        if ( !*a3 )
          break;
        *i++ = *a3++;
        --v3;
      }
      v11 = i - 1;
      if ( v9 )
        v11 = i;
      v7 = v9 == 0 ? 0x8007007A : 0;
      *v11 = 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800053bc  mov     [rsp+arg_0], rbx
0x1800053c1  mov     [rsp+arg_8], rdi
0x1800053c6  lea     rax, [rdx-1]
0x1800053ca  mov     r10d, 7FFFFFFEh
0x1800053d0  mov     r9, rdx
0x1800053d3  mov     rbx, rcx
0x1800053d6  cmp     rax, r10
0x1800053d9  ja      loc_180005465
0x1800053df  mov     r11, rdx
0x1800053e2  mov     rax, rcx
0x1800053e5  xor     edi, edi
0x1800053e7  cmp     [rax], di
0x1800053ea  jz      short loc_1800053F6
0x1800053ec  add     rax, 2
0x1800053f0  sub     r11, 1
0x1800053f4  jnz     short loc_1800053E7
0x1800053f6  mov     rax, r11
0x1800053f9  mov     rcx, r9
0x1800053fc  neg     rax
0x1800053ff  mov     rax, r11
0x180005402  sbb     edx, edx
0x180005404  sub     rcx, r11
0x180005407  not     edx
0x180005409  and     edx, 80070057h
0x18000540f  neg     rax
0x180005412  sbb     rax, rax
0x180005415  and     rax, rcx
0x180005418  test    r11, r11
0x18000541b  jz      short loc_18000546A
0x18000541d  sub     r9, rax
0x180005420  lea     rax, [rbx+rax*2]
0x180005424  jz      short loc_180005448
0x180005426  test    r10, r10
0x180005429  jz      short loc_180005448
0x18000542b  movzx   ecx, word ptr [r8]
0x18000542f  test    cx, cx
0x180005432  jz      short loc_180005448
0x180005434  mov     [rax], cx
0x180005437  add     r8, 2
0x18000543b  add     rax, 2
0x18000543f  dec     r10
0x180005442  sub     r9, 1
0x180005446  jnz     short loc_180005426
0x180005448  test    r9, r9
0x18000544b  lea     rcx, [rax-2]
0x18000544f  cmovnz  rcx, rax
0x180005453  neg     r9
0x180005456  sbb     edx, edx
0x180005458  not     edx
0x18000545a  and     edx, 8007007Ah
0x180005460  mov     [rcx], di
0x180005463  jmp     short loc_18000546A
0x180005465  mov     edx, 80070057h
0x18000546a  mov     rbx, [rsp+arg_0]
0x18000546f  mov     eax, edx
0x180005471  mov     rdi, [rsp+arg_8]
0x180005476  retn
```
