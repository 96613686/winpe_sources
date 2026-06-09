# StringCbCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1400137f8`
- end: `0x1400138a3`
- name: `?StringCbCatW@@YAJPEAG_KPEBG@Z`
- size: `171`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140014828`
- `0x140017000`
- `0x140017d90`
- `0x140019940`

## callees

- `0x1400137f8`

## pseudocode

```c
__int64 __fastcall StringCbCatW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int64 v3; // rdx
  __int64 v4; // r10
  unsigned __int64 v6; // r9
  unsigned __int16 *v7; // rax
  __int64 result; // rax
  unsigned __int64 v9; // rcx
  unsigned __int16 *v10; // rax
  unsigned __int64 i; // rdx
  unsigned __int16 *v12; // rcx

  v3 = a2 >> 1;
  v4 = 2147483646;
  if ( v3 - 1 > 0x7FFFFFFE )
    return 2147942487LL;
  v6 = v3;
  v7 = a1;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v6;
  }
  while ( v6 );
  result = v6 == 0 ? 0x80070057 : 0;
  if ( v6 )
    v9 = v3 - v6;
  else
    v9 = 0;
  if ( v6 )
  {
    v10 = &a1[v9];
    for ( i = v3 - v9; i; --i )
    {
      if ( !v4 )
        break;
      if ( !*a3 )
        break;
      *v10++ = *a3++;
      --v4;
    }
    v12 = v10 - 1;
    if ( i )
      v12 = v10;
    result = i == 0 ? 0x8007007A : 0;
    *v12 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400137f8  mov     [rsp+arg_0], rbx
0x1400137fd  shr     rdx, 1
0x140013800  mov     r10d, 7FFFFFFEh
0x140013806  mov     r11, rcx
0x140013809  lea     rax, [rdx-1]
0x14001380d  cmp     rax, r10
0x140013810  ja      loc_140013898
0x140013816  mov     r9, rdx
0x140013819  mov     rax, rcx
0x14001381c  xor     ebx, ebx
0x14001381e  cmp     [rax], bx
0x140013821  jz      short loc_14001382D
0x140013823  add     rax, 2
0x140013827  sub     r9, 1
0x14001382b  jnz     short loc_14001381E
0x14001382d  mov     rax, r9
0x140013830  neg     rax
0x140013833  sbb     eax, eax
0x140013835  not     eax
0x140013837  and     eax, 80070057h
0x14001383c  test    r9, r9
0x14001383f  jz      short loc_140013849
0x140013841  mov     rcx, rdx
0x140013844  sub     rcx, r9
0x140013847  jmp     short loc_14001384C
0x140013849  mov     rcx, rbx
0x14001384c  test    r9, r9
0x14001384f  jz      short loc_14001389D
0x140013851  lea     rax, [r11+rcx*2]
0x140013855  sub     rdx, rcx
0x140013858  jz      short loc_14001387C
0x14001385a  test    r10, r10
0x14001385d  jz      short loc_14001387C
0x14001385f  movzx   ecx, word ptr [r8]
0x140013863  test    cx, cx
0x140013866  jz      short loc_14001387C
0x140013868  mov     [rax], cx
0x14001386b  add     r8, 2
0x14001386f  add     rax, 2
0x140013873  dec     r10
0x140013876  sub     rdx, 1
0x14001387a  jnz     short loc_14001385A
0x14001387c  lea     rcx, [rax-2]
0x140013880  test    rdx, rdx
0x140013883  cmovnz  rcx, rax
0x140013887  neg     rdx
0x14001388a  sbb     eax, eax
0x14001388c  not     eax
0x14001388e  and     eax, 8007007Ah
0x140013893  mov     [rcx], bx
0x140013896  jmp     short loc_14001389D
0x140013898  mov     eax, 80070057h
0x14001389d  mov     rbx, [rsp+arg_0]
0x1400138a2  retn
```
