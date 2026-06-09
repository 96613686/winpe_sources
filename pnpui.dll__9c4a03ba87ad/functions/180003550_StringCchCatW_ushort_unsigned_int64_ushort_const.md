# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180003550`
- end: `0x18000360b`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003110`
- `0x1800056f4`
- `0x180006700`
- `0x180009cc0`

## callees

- `0x180003550`

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
0x180003550  mov     [rsp+arg_0], rbx
0x180003555  mov     [rsp+arg_8], rdi
0x18000355a  lea     rax, [rdx-1]
0x18000355e  mov     r10d, 7FFFFFFEh
0x180003564  mov     r9, rdx
0x180003567  mov     rbx, rcx
0x18000356a  cmp     rax, r10
0x18000356d  ja      loc_1800035F9
0x180003573  mov     r11, rdx
0x180003576  mov     rax, rcx
0x180003579  xor     edi, edi
0x18000357b  cmp     [rax], di
0x18000357e  jz      short loc_18000358A
0x180003580  add     rax, 2
0x180003584  sub     r11, 1
0x180003588  jnz     short loc_18000357B
0x18000358a  mov     rax, r11
0x18000358d  mov     rcx, r9
0x180003590  neg     rax
0x180003593  mov     rax, r11
0x180003596  sbb     edx, edx
0x180003598  sub     rcx, r11
0x18000359b  not     edx
0x18000359d  and     edx, 80070057h
0x1800035a3  neg     rax
0x1800035a6  sbb     rax, rax
0x1800035a9  and     rax, rcx
0x1800035ac  test    r11, r11
0x1800035af  jz      short loc_1800035FE
0x1800035b1  sub     r9, rax
0x1800035b4  lea     rax, [rbx+rax*2]
0x1800035b8  jz      short loc_1800035DC
0x1800035ba  test    r10, r10
0x1800035bd  jz      short loc_1800035DC
0x1800035bf  movzx   ecx, word ptr [r8]
0x1800035c3  test    cx, cx
0x1800035c6  jz      short loc_1800035DC
0x1800035c8  mov     [rax], cx
0x1800035cb  add     r8, 2
0x1800035cf  add     rax, 2
0x1800035d3  dec     r10
0x1800035d6  sub     r9, 1
0x1800035da  jnz     short loc_1800035BA
0x1800035dc  test    r9, r9
0x1800035df  lea     rcx, [rax-2]
0x1800035e3  cmovnz  rcx, rax
0x1800035e7  neg     r9
0x1800035ea  sbb     edx, edx
0x1800035ec  not     edx
0x1800035ee  and     edx, 8007007Ah
0x1800035f4  mov     [rcx], di
0x1800035f7  jmp     short loc_1800035FE
0x1800035f9  mov     edx, 80070057h
0x1800035fe  mov     rbx, [rsp+arg_0]
0x180003603  mov     eax, edx
0x180003605  mov     rdi, [rsp+arg_8]
0x18000360a  retn
```
