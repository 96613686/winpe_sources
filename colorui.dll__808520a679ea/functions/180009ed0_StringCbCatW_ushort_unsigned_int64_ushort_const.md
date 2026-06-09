# StringCbCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180009ed0`
- end: `0x180009f79`
- name: `?StringCbCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004bb4`
- `0x18000a47c`
- `0x180014284`
- `0x180015428`

## callees

- `0x180009ed0`

## pseudocode

```c
__int64 __fastcall StringCbCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
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
0x180009ed0  mov     [rsp+arg_0], rbx
0x180009ed5  mov     [rsp+arg_8], rdi
0x180009eda  mov     r9d, 104h
0x180009ee0  mov     rbx, rcx
0x180009ee3  mov     r10d, r9d
0x180009ee6  mov     rax, rcx
0x180009ee9  xor     edi, edi
0x180009eeb  cmp     [rax], di
0x180009eee  jz      short loc_180009EFA
0x180009ef0  add     rax, 2
0x180009ef4  sub     r10, 1
0x180009ef8  jnz     short loc_180009EEB
0x180009efa  mov     rax, r10
0x180009efd  mov     rcx, r9
0x180009f00  neg     rax
0x180009f03  mov     rax, r10
0x180009f06  sbb     edx, edx
0x180009f08  sub     rcx, r10
0x180009f0b  not     edx
0x180009f0d  and     edx, 80070057h
0x180009f13  neg     rax
0x180009f16  sbb     r11, r11
0x180009f19  and     r11, rcx
0x180009f1c  test    r10, r10
0x180009f1f  jz      short loc_180009F6C
0x180009f21  lea     rax, [rbx+r11*2]
0x180009f25  mov     ecx, 7FFFFFFEh
0x180009f2a  sub     r9, r11
0x180009f2d  jz      short loc_180009F51
0x180009f2f  test    rcx, rcx
0x180009f32  jz      short loc_180009F51
0x180009f34  movzx   edx, word ptr [r8]
0x180009f38  test    dx, dx
0x180009f3b  jz      short loc_180009F51
0x180009f3d  mov     [rax], dx
0x180009f40  add     r8, 2
0x180009f44  add     rax, 2
0x180009f48  dec     rcx
0x180009f4b  sub     r9, 1
0x180009f4f  jnz     short loc_180009F2F
0x180009f51  test    r9, r9
0x180009f54  lea     rcx, [rax-2]
0x180009f58  cmovnz  rcx, rax
0x180009f5c  neg     r9
0x180009f5f  sbb     edx, edx
0x180009f61  not     edx
0x180009f63  and     edx, 8007007Ah
0x180009f69  mov     [rcx], di
0x180009f6c  mov     rbx, [rsp+arg_0]
0x180009f71  mov     eax, edx
0x180009f73  mov     rdi, [rsp+arg_8]
0x180009f78  retn
```
