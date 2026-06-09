# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180005050`
- end: `0x18000510c`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `188`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004210`
- `0x1800051cc`
- `0x180006000`

## callees

- `0x180005050`

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
0x180005050  mov     [rsp+arg_0], rbx
0x180005055  mov     [rsp+arg_8], rdi
0x18000505a  lea     rax, [rdx-1]
0x18000505e  mov     r10d, 7FFFFFFEh
0x180005064  mov     r9, rdx
0x180005067  mov     rbx, rcx
0x18000506a  cmp     rax, r10
0x18000506d  ja      loc_1800050F9
0x180005073  mov     r11, rdx
0x180005076  mov     rax, rcx
0x180005079  xor     edi, edi
0x18000507b  cmp     [rax], di
0x18000507e  jz      short loc_18000508A
0x180005080  add     rax, 2
0x180005084  sub     r11, 1
0x180005088  jnz     short loc_18000507B
0x18000508a  mov     rax, r11
0x18000508d  mov     rcx, r9
0x180005090  neg     rax
0x180005093  mov     rax, r11
0x180005096  sbb     edx, edx
0x180005098  sub     rcx, r11
0x18000509b  not     edx
0x18000509d  and     edx, 80070057h
0x1800050a3  neg     rax
0x1800050a6  sbb     rax, rax
0x1800050a9  and     rax, rcx
0x1800050ac  test    r11, r11
0x1800050af  jz      short loc_1800050FE
0x1800050b1  sub     r9, rax
0x1800050b4  lea     rax, [rbx+rax*2]
0x1800050b8  jz      short loc_1800050DC
0x1800050ba  test    r10, r10
0x1800050bd  jz      short loc_1800050DC
0x1800050bf  movzx   ecx, word ptr [r8]
0x1800050c3  test    cx, cx
0x1800050c6  jz      short loc_1800050DC
0x1800050c8  mov     [rax], cx
0x1800050cb  add     r8, 2
0x1800050cf  add     rax, 2
0x1800050d3  dec     r10
0x1800050d6  sub     r9, 1
0x1800050da  jnz     short loc_1800050BA
0x1800050dc  test    r9, r9
0x1800050df  lea     rcx, [rax-2]
0x1800050e3  cmovnz  rcx, rax
0x1800050e7  neg     r9
0x1800050ea  sbb     edx, edx
0x1800050ec  not     edx
0x1800050ee  and     edx, 8007007Ah
0x1800050f4  mov     [rcx], di
0x1800050f7  jmp     short loc_1800050FE
0x1800050f9  mov     edx, 80070057h
0x1800050fe  mov     rbx, [rsp+arg_0]
0x180005103  mov     eax, edx
0x180005105  mov     rdi, [rsp+arg_8]
0x18000510a  retn
```
