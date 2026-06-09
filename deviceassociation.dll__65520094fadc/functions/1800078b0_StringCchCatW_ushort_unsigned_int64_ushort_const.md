# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800078b0`
- end: `0x180007959`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004880`
- `0x180007c68`

## callees

- `0x1800078b0`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // r10
  unsigned __int16 *v4; // rax
  unsigned int v5; // edx
  __int64 v6; // r11
  unsigned __int16 *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r9
  unsigned __int16 *v10; // rcx

  v3 = 260;
  v4 = a1;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v3;
  }
  while ( v3 );
  v5 = v3 == 0 ? 0x80070057 : 0;
  v6 = (260 - v3) & -(__int64)(v3 != 0);
  if ( v3 )
  {
    v7 = &a1[v6];
    v8 = 2147483646;
    v9 = 260 - v6;
    if ( 260 != v6 )
    {
      do
      {
        if ( !v8 )
          break;
        if ( !*a3 )
          break;
        *v7++ = *a3++;
        --v8;
        --v9;
      }
      while ( v9 );
    }
    v10 = v7 - 1;
    if ( v9 )
      v10 = v7;
    v5 = v9 == 0 ? 0x8007007A : 0;
    *v10 = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x1800078b0  mov     [rsp+arg_0], rbx
0x1800078b5  mov     [rsp+arg_8], rdi
0x1800078ba  mov     r9d, 104h
0x1800078c0  mov     rbx, rcx
0x1800078c3  mov     r10d, r9d
0x1800078c6  mov     rax, rcx
0x1800078c9  xor     edi, edi
0x1800078cb  cmp     [rax], di
0x1800078ce  jz      short loc_1800078DA
0x1800078d0  add     rax, 2
0x1800078d4  sub     r10, 1
0x1800078d8  jnz     short loc_1800078CB
0x1800078da  mov     rax, r10
0x1800078dd  mov     rcx, r9
0x1800078e0  neg     rax
0x1800078e3  mov     rax, r10
0x1800078e6  sbb     edx, edx
0x1800078e8  sub     rcx, r10
0x1800078eb  not     edx
0x1800078ed  and     edx, 80070057h
0x1800078f3  neg     rax
0x1800078f6  sbb     r11, r11
0x1800078f9  and     r11, rcx
0x1800078fc  test    r10, r10
0x1800078ff  jz      short loc_18000794C
0x180007901  lea     rax, [rbx+r11*2]
0x180007905  mov     ecx, 7FFFFFFEh
0x18000790a  sub     r9, r11
0x18000790d  jz      short loc_180007931
0x18000790f  test    rcx, rcx
0x180007912  jz      short loc_180007931
0x180007914  movzx   edx, word ptr [r8]
0x180007918  test    dx, dx
0x18000791b  jz      short loc_180007931
0x18000791d  mov     [rax], dx
0x180007920  add     r8, 2
0x180007924  add     rax, 2
0x180007928  dec     rcx
0x18000792b  sub     r9, 1
0x18000792f  jnz     short loc_18000790F
0x180007931  test    r9, r9
0x180007934  lea     rcx, [rax-2]
0x180007938  cmovnz  rcx, rax
0x18000793c  neg     r9
0x18000793f  sbb     edx, edx
0x180007941  not     edx
0x180007943  and     edx, 8007007Ah
0x180007949  mov     [rcx], di
0x18000794c  mov     rbx, [rsp+arg_0]
0x180007951  mov     eax, edx
0x180007953  mov     rdi, [rsp+arg_8]
0x180007958  retn
```
