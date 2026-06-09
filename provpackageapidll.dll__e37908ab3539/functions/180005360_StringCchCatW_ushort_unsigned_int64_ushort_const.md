# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180005360`
- end: `0x18000541b`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003438`
- `0x18000555c`
- `0x18000a5b0`
- `0x18000da5c`
- `0x180016c50`

## callees

- `0x180005360`

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
0x180005360  mov     [rsp+arg_0], rbx
0x180005365  mov     [rsp+arg_8], rdi
0x18000536a  lea     rax, [rdx-1]
0x18000536e  mov     r10d, 7FFFFFFEh
0x180005374  mov     r9, rdx
0x180005377  mov     rbx, rcx
0x18000537a  cmp     rax, r10
0x18000537d  ja      loc_180005409
0x180005383  mov     r11, rdx
0x180005386  mov     rax, rcx
0x180005389  xor     edi, edi
0x18000538b  cmp     [rax], di
0x18000538e  jz      short loc_18000539A
0x180005390  add     rax, 2
0x180005394  sub     r11, 1
0x180005398  jnz     short loc_18000538B
0x18000539a  mov     rax, r11
0x18000539d  mov     rcx, r9
0x1800053a0  neg     rax
0x1800053a3  mov     rax, r11
0x1800053a6  sbb     edx, edx
0x1800053a8  sub     rcx, r11
0x1800053ab  not     edx
0x1800053ad  and     edx, 80070057h
0x1800053b3  neg     rax
0x1800053b6  sbb     rax, rax
0x1800053b9  and     rax, rcx
0x1800053bc  test    r11, r11
0x1800053bf  jz      short loc_18000540E
0x1800053c1  sub     r9, rax
0x1800053c4  lea     rax, [rbx+rax*2]
0x1800053c8  jz      short loc_1800053EC
0x1800053ca  test    r10, r10
0x1800053cd  jz      short loc_1800053EC
0x1800053cf  movzx   ecx, word ptr [r8]
0x1800053d3  test    cx, cx
0x1800053d6  jz      short loc_1800053EC
0x1800053d8  mov     [rax], cx
0x1800053db  add     r8, 2
0x1800053df  add     rax, 2
0x1800053e3  dec     r10
0x1800053e6  sub     r9, 1
0x1800053ea  jnz     short loc_1800053CA
0x1800053ec  test    r9, r9
0x1800053ef  lea     rcx, [rax-2]
0x1800053f3  cmovnz  rcx, rax
0x1800053f7  neg     r9
0x1800053fa  sbb     edx, edx
0x1800053fc  not     edx
0x1800053fe  and     edx, 8007007Ah
0x180005404  mov     [rcx], di
0x180005407  jmp     short loc_18000540E
0x180005409  mov     edx, 80070057h
0x18000540e  mov     rbx, [rsp+arg_0]
0x180005413  mov     eax, edx
0x180005415  mov     rdi, [rsp+arg_8]
0x18000541a  retn
```
