# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180006018`
- end: `0x1800060c1`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180006724`
- `0x180009044`
- `0x18000c70c`

## callees

- `0x180006018`

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
0x180006018  mov     [rsp+arg_0], rbx
0x18000601d  mov     [rsp+arg_8], rdi
0x180006022  mov     r9d, 104h
0x180006028  mov     rbx, rcx
0x18000602b  mov     r10d, r9d
0x18000602e  mov     rax, rcx
0x180006031  xor     edi, edi
0x180006033  cmp     [rax], di
0x180006036  jz      short loc_180006042
0x180006038  add     rax, 2
0x18000603c  sub     r10, 1
0x180006040  jnz     short loc_180006033
0x180006042  mov     rax, r10
0x180006045  mov     rcx, r9
0x180006048  neg     rax
0x18000604b  mov     rax, r10
0x18000604e  sbb     edx, edx
0x180006050  sub     rcx, r10
0x180006053  not     edx
0x180006055  and     edx, 80070057h
0x18000605b  neg     rax
0x18000605e  sbb     r11, r11
0x180006061  and     r11, rcx
0x180006064  test    r10, r10
0x180006067  jz      short loc_1800060B4
0x180006069  lea     rax, [rbx+r11*2]
0x18000606d  mov     ecx, 7FFFFFFEh
0x180006072  sub     r9, r11
0x180006075  jz      short loc_180006099
0x180006077  test    rcx, rcx
0x18000607a  jz      short loc_180006099
0x18000607c  movzx   edx, word ptr [r8]
0x180006080  test    dx, dx
0x180006083  jz      short loc_180006099
0x180006085  mov     [rax], dx
0x180006088  add     r8, 2
0x18000608c  add     rax, 2
0x180006090  dec     rcx
0x180006093  sub     r9, 1
0x180006097  jnz     short loc_180006077
0x180006099  test    r9, r9
0x18000609c  lea     rcx, [rax-2]
0x1800060a0  cmovnz  rcx, rax
0x1800060a4  neg     r9
0x1800060a7  sbb     edx, edx
0x1800060a9  not     edx
0x1800060ab  and     edx, 8007007Ah
0x1800060b1  mov     [rcx], di
0x1800060b4  mov     rbx, [rsp+arg_0]
0x1800060b9  mov     eax, edx
0x1800060bb  mov     rdi, [rsp+arg_8]
0x1800060c0  retn
```
