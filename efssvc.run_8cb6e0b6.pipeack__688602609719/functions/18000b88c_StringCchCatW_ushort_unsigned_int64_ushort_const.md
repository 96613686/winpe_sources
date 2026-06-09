# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000b88c`
- end: `0x18000b936`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `170`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ac68`
- `0x18000b9d0`

## callees

- `0x18000b88c`

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
0x18000b88c  mov     [rsp+arg_0], rbx
0x18000b891  mov     [rsp+arg_8], rdi
0x18000b896  mov     r9d, 104h
0x18000b89c  mov     rbx, rcx
0x18000b89f  mov     r10d, r9d
0x18000b8a2  mov     rax, rcx
0x18000b8a5  xor     edi, edi
0x18000b8a7  cmp     [rax], di
0x18000b8aa  jz      short loc_18000B8B6
0x18000b8ac  add     rax, 2
0x18000b8b0  sub     r10, 1
0x18000b8b4  jnz     short loc_18000B8A7
0x18000b8b6  mov     rax, r10
0x18000b8b9  mov     rcx, r9
0x18000b8bc  neg     rax
0x18000b8bf  mov     rax, r10
0x18000b8c2  sbb     edx, edx
0x18000b8c4  sub     rcx, r10
0x18000b8c7  not     edx
0x18000b8c9  and     edx, 80070057h
0x18000b8cf  neg     rax
0x18000b8d2  sbb     r11, r11
0x18000b8d5  and     r11, rcx
0x18000b8d8  test    r10, r10
0x18000b8db  jz      short loc_18000B928
0x18000b8dd  lea     rax, [rbx+r11*2]
0x18000b8e1  mov     ecx, 7FFFFFFEh
0x18000b8e6  sub     r9, r11
0x18000b8e9  jz      short loc_18000B90D
0x18000b8eb  test    rcx, rcx
0x18000b8ee  jz      short loc_18000B90D
0x18000b8f0  movzx   edx, word ptr [r8]
0x18000b8f4  test    dx, dx
0x18000b8f7  jz      short loc_18000B90D
0x18000b8f9  mov     [rax], dx
0x18000b8fc  add     r8, 2
0x18000b900  add     rax, 2
0x18000b904  dec     rcx
0x18000b907  sub     r9, 1
0x18000b90b  jnz     short loc_18000B8EB
0x18000b90d  test    r9, r9
0x18000b910  lea     rcx, [rax-2]
0x18000b914  cmovnz  rcx, rax
0x18000b918  neg     r9
0x18000b91b  sbb     edx, edx
0x18000b91d  not     edx
0x18000b91f  and     edx, 8007007Ah
0x18000b925  mov     [rcx], di
0x18000b928  mov     rbx, [rsp+arg_0]
0x18000b92d  mov     eax, edx
0x18000b92f  mov     rdi, [rsp+arg_8]
0x18000b934  retn
```
