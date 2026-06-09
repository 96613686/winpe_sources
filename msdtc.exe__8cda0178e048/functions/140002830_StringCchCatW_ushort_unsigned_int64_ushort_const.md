# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140002830`
- end: `0x1400028eb`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003c50`
- `0x140004640`

## callees

- `0x140002830`

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
0x140002830  mov     [rsp+arg_0], rbx
0x140002835  mov     [rsp+arg_8], rdi
0x14000283a  lea     rax, [rdx-1]
0x14000283e  mov     r10d, 7FFFFFFEh
0x140002844  mov     r9, rdx
0x140002847  mov     rbx, rcx
0x14000284a  cmp     rax, r10
0x14000284d  ja      loc_1400028D9
0x140002853  mov     r11, rdx
0x140002856  mov     rax, rcx
0x140002859  xor     edi, edi
0x14000285b  cmp     [rax], di
0x14000285e  jz      short loc_14000286A
0x140002860  add     rax, 2
0x140002864  sub     r11, 1
0x140002868  jnz     short loc_14000285B
0x14000286a  mov     rax, r11
0x14000286d  mov     rcx, r9
0x140002870  neg     rax
0x140002873  mov     rax, r11
0x140002876  sbb     edx, edx
0x140002878  sub     rcx, r11
0x14000287b  not     edx
0x14000287d  and     edx, 80070057h
0x140002883  neg     rax
0x140002886  sbb     rax, rax
0x140002889  and     rax, rcx
0x14000288c  test    r11, r11
0x14000288f  jz      short loc_1400028DE
0x140002891  sub     r9, rax
0x140002894  lea     rax, [rbx+rax*2]
0x140002898  jz      short loc_1400028BC
0x14000289a  test    r10, r10
0x14000289d  jz      short loc_1400028BC
0x14000289f  movzx   ecx, word ptr [r8]
0x1400028a3  test    cx, cx
0x1400028a6  jz      short loc_1400028BC
0x1400028a8  mov     [rax], cx
0x1400028ab  add     r8, 2
0x1400028af  add     rax, 2
0x1400028b3  dec     r10
0x1400028b6  sub     r9, 1
0x1400028ba  jnz     short loc_14000289A
0x1400028bc  test    r9, r9
0x1400028bf  lea     rcx, [rax-2]
0x1400028c3  cmovnz  rcx, rax
0x1400028c7  neg     r9
0x1400028ca  sbb     edx, edx
0x1400028cc  not     edx
0x1400028ce  and     edx, 8007007Ah
0x1400028d4  mov     [rcx], di
0x1400028d7  jmp     short loc_1400028DE
0x1400028d9  mov     edx, 80070057h
0x1400028de  mov     rbx, [rsp+arg_0]
0x1400028e3  mov     eax, edx
0x1400028e5  mov     rdi, [rsp+arg_8]
0x1400028ea  retn
```
