# LzmsDecompress

- ea: `0x1800095e0`
- end: `0x180009644`
- name: `LzmsDecompress`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800095e0`
- `0x180009650`

## pseudocode

```c
__int64 __fastcall LzmsDecompress(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        __int64 a4,
        unsigned __int64 a5,
        unsigned __int64 *a6)
{
  unsigned int v6; // edx

  if ( a5 > 0x40000000 )
  {
    v6 = 111;
    *a6 = 0x40000000;
  }
  else if ( a3 )
  {
    if ( a3 > a5 )
    {
      return 605;
    }
    else
    {
      v6 = LzmsDecoderDecode(a1);
      if ( !v6 )
        *a6 = a5;
    }
  }
  else
  {
    v6 = 122;
    *a6 = a5;
  }
  return v6;
}

```

## disassembly

```asm
0x1800095e0  push    rbx
0x1800095e2  sub     rsp, 30h
0x1800095e6  mov     rbx, [rsp+38h+arg_20]
0x1800095eb  mov     r10d, 40000000h
0x1800095f1  cmp     rbx, r10
0x1800095f4  ja      short loc_18000961F
0x1800095f6  test    r8, r8
0x1800095f9  jz      short loc_18000962E
0x1800095fb  cmp     r8, rbx
0x1800095fe  ja      short loc_18000963D
0x180009600  mov     [rsp+38h+var_18], ebx
0x180009604  call    LzmsDecoderDecode
0x180009609  mov     edx, eax
0x18000960b  test    eax, eax
0x18000960d  jnz     short loc_180009617
0x18000960f  mov     rcx, [rsp+38h+arg_28]
0x180009614  mov     [rcx], rbx
0x180009617  mov     eax, edx
0x180009619  add     rsp, 30h
0x18000961d  pop     rbx
0x18000961e  retn
0x18000961f  mov     rax, [rsp+38h+arg_28]
0x180009624  mov     edx, 6Fh ; 'o'
0x180009629  mov     [rax], r10
0x18000962c  jmp     short loc_180009617
0x18000962e  mov     rax, [rsp+38h+arg_28]
0x180009633  mov     edx, 7Ah ; 'z'
0x180009638  mov     [rax], rbx
0x18000963b  jmp     short loc_180009617
0x18000963d  mov     edx, 25Dh
0x180009642  jmp     short loc_180009617
```
