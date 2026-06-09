# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140005000`
- end: `0x1400050a9`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002f74`
- `0x140005298`

## callees

- `0x140005000`

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
0x140005000  mov     [rsp+arg_0], rbx
0x140005005  mov     [rsp+arg_8], rdi
0x14000500a  mov     r9d, 104h
0x140005010  mov     rbx, rcx
0x140005013  mov     r10d, r9d
0x140005016  mov     rax, rcx
0x140005019  xor     edi, edi
0x14000501b  cmp     [rax], di
0x14000501e  jz      short loc_14000502A
0x140005020  add     rax, 2
0x140005024  sub     r10, 1
0x140005028  jnz     short loc_14000501B
0x14000502a  mov     rax, r10
0x14000502d  mov     rcx, r9
0x140005030  neg     rax
0x140005033  mov     rax, r10
0x140005036  sbb     edx, edx
0x140005038  sub     rcx, r10
0x14000503b  not     edx
0x14000503d  and     edx, 80070057h
0x140005043  neg     rax
0x140005046  sbb     r11, r11
0x140005049  and     r11, rcx
0x14000504c  test    r10, r10
0x14000504f  jz      short loc_14000509C
0x140005051  lea     rax, [rbx+r11*2]
0x140005055  mov     ecx, 7FFFFFFEh
0x14000505a  sub     r9, r11
0x14000505d  jz      short loc_140005081
0x14000505f  test    rcx, rcx
0x140005062  jz      short loc_140005081
0x140005064  movzx   edx, word ptr [r8]
0x140005068  test    dx, dx
0x14000506b  jz      short loc_140005081
0x14000506d  mov     [rax], dx
0x140005070  add     r8, 2
0x140005074  add     rax, 2
0x140005078  dec     rcx
0x14000507b  sub     r9, 1
0x14000507f  jnz     short loc_14000505F
0x140005081  test    r9, r9
0x140005084  lea     rcx, [rax-2]
0x140005088  cmovnz  rcx, rax
0x14000508c  neg     r9
0x14000508f  sbb     edx, edx
0x140005091  not     edx
0x140005093  and     edx, 8007007Ah
0x140005099  mov     [rcx], di
0x14000509c  mov     rbx, [rsp+arg_0]
0x1400050a1  mov     eax, edx
0x1400050a3  mov     rdi, [rsp+arg_8]
0x1400050a8  retn
```
