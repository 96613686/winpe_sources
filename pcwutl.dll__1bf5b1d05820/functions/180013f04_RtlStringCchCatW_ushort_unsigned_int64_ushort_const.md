# RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180013f04`
- end: `0x180013fbf`
- name: `?RtlStringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f39c`
- `0x180012fa0`
- `0x180016880`
- `0x1800180f8`

## callees

- `0x180013f04`

## pseudocode

```c
__int64 __fastcall RtlStringCchCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
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
    return (unsigned int)-1073741811;
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
    v7 = v5 == 0 ? 0xC000000D : 0;
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
      v7 = v9 == 0 ? 0x80000005 : 0;
      *v11 = 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180013f04  mov     [rsp+arg_0], rbx
0x180013f09  mov     [rsp+arg_8], rdi
0x180013f0e  lea     rax, [rdx-1]
0x180013f12  mov     r10d, 7FFFFFFEh
0x180013f18  mov     r9, rdx
0x180013f1b  mov     rbx, rcx
0x180013f1e  cmp     rax, r10
0x180013f21  ja      loc_180013FAD
0x180013f27  mov     r11, rdx
0x180013f2a  mov     rax, rcx
0x180013f2d  xor     edi, edi
0x180013f2f  cmp     [rax], di
0x180013f32  jz      short loc_180013F3E
0x180013f34  add     rax, 2
0x180013f38  sub     r11, 1
0x180013f3c  jnz     short loc_180013F2F
0x180013f3e  mov     rax, r11
0x180013f41  mov     rcx, r9
0x180013f44  neg     rax
0x180013f47  mov     rax, r11
0x180013f4a  sbb     edx, edx
0x180013f4c  sub     rcx, r11
0x180013f4f  not     edx
0x180013f51  and     edx, 0C000000Dh
0x180013f57  neg     rax
0x180013f5a  sbb     rax, rax
0x180013f5d  and     rax, rcx
0x180013f60  test    r11, r11
0x180013f63  jz      short loc_180013FB2
0x180013f65  sub     r9, rax
0x180013f68  lea     rax, [rbx+rax*2]
0x180013f6c  jz      short loc_180013F90
0x180013f6e  test    r10, r10
0x180013f71  jz      short loc_180013F90
0x180013f73  movzx   ecx, word ptr [r8]
0x180013f77  test    cx, cx
0x180013f7a  jz      short loc_180013F90
0x180013f7c  mov     [rax], cx
0x180013f7f  add     r8, 2
0x180013f83  add     rax, 2
0x180013f87  dec     r10
0x180013f8a  sub     r9, 1
0x180013f8e  jnz     short loc_180013F6E
0x180013f90  test    r9, r9
0x180013f93  lea     rcx, [rax-2]
0x180013f97  cmovnz  rcx, rax
0x180013f9b  neg     r9
0x180013f9e  sbb     edx, edx
0x180013fa0  not     edx
0x180013fa2  and     edx, 80000005h
0x180013fa8  mov     [rcx], di
0x180013fab  jmp     short loc_180013FB2
0x180013fad  mov     edx, 0C000000Dh
0x180013fb2  mov     rbx, [rsp+arg_0]
0x180013fb7  mov     eax, edx
0x180013fb9  mov     rdi, [rsp+arg_8]
0x180013fbe  retn
```
