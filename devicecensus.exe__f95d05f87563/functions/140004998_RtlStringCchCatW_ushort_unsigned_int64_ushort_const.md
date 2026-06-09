# RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140004998`
- end: `0x140004a53`
- name: `?RtlStringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400050a0`
- `0x140008f48`
- `0x14000b6bc`
- `0x14000fb14`

## callees

- `0x140004998`

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
0x140004998  mov     [rsp+arg_0], rbx
0x14000499d  mov     [rsp+arg_8], rdi
0x1400049a2  lea     rax, [rdx-1]
0x1400049a6  mov     r10d, 7FFFFFFEh
0x1400049ac  mov     r9, rdx
0x1400049af  mov     rbx, rcx
0x1400049b2  cmp     rax, r10
0x1400049b5  ja      loc_140004A41
0x1400049bb  mov     r11, rdx
0x1400049be  mov     rax, rcx
0x1400049c1  xor     edi, edi
0x1400049c3  cmp     [rax], di
0x1400049c6  jz      short loc_1400049D2
0x1400049c8  add     rax, 2
0x1400049cc  sub     r11, 1
0x1400049d0  jnz     short loc_1400049C3
0x1400049d2  mov     rax, r11
0x1400049d5  mov     rcx, r9
0x1400049d8  neg     rax
0x1400049db  mov     rax, r11
0x1400049de  sbb     edx, edx
0x1400049e0  sub     rcx, r11
0x1400049e3  not     edx
0x1400049e5  and     edx, 0C000000Dh
0x1400049eb  neg     rax
0x1400049ee  sbb     rax, rax
0x1400049f1  and     rax, rcx
0x1400049f4  test    r11, r11
0x1400049f7  jz      short loc_140004A46
0x1400049f9  sub     r9, rax
0x1400049fc  lea     rax, [rbx+rax*2]
0x140004a00  jz      short loc_140004A24
0x140004a02  test    r10, r10
0x140004a05  jz      short loc_140004A24
0x140004a07  movzx   ecx, word ptr [r8]
0x140004a0b  test    cx, cx
0x140004a0e  jz      short loc_140004A24
0x140004a10  mov     [rax], cx
0x140004a13  add     r8, 2
0x140004a17  add     rax, 2
0x140004a1b  dec     r10
0x140004a1e  sub     r9, 1
0x140004a22  jnz     short loc_140004A02
0x140004a24  test    r9, r9
0x140004a27  lea     rcx, [rax-2]
0x140004a2b  cmovnz  rcx, rax
0x140004a2f  neg     r9
0x140004a32  sbb     edx, edx
0x140004a34  not     edx
0x140004a36  and     edx, 80000005h
0x140004a3c  mov     [rcx], di
0x140004a3f  jmp     short loc_140004A46
0x140004a41  mov     edx, 0C000000Dh
0x140004a46  mov     rbx, [rsp+arg_0]
0x140004a4b  mov     eax, edx
0x140004a4d  mov     rdi, [rsp+arg_8]
0x140004a52  retn
```
