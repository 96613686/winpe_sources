# ASN1BERDecSkip

- ea: `0x180001f80`
- end: `0x180002094`
- name: `ASN1BERDecSkip`
- size: `276`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x180001f80`
- `0x1800026b0`
- `0x180003270`

## callees

- `0x180001a00`
- `0x180001b30`
- `0x180001f80`
- `0x1800020a0`
- `0x180002200`
- `0x180003a60`
- `0x180004310`
- `0x180004340`

## pseudocode

```c
__int64 __fastcall ASN1BERDecSkip(__int64 a1)
{
  __int64 v2; // rcx
  int i; // eax
  int v5; // [rsp+30h] [rbp-20h] BYREF
  __int64 v6; // [rsp+38h] [rbp-18h] BYREF
  __int64 v7; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v8; // [rsp+68h] [rbp+18h] BYREF
  unsigned int v9; // [rsp+70h] [rbp+20h] BYREF
  int v10; // [rsp+78h] [rbp+28h] BYREF

  v9 = 0;
  v10 = 0;
  v8 = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  ASN1DecSetError(a1, 0x3E9u);
  if ( (unsigned int)ASN1BERDecPeekTag(a1, &v9) && (unsigned int)ASN1BERDecTag(a1, v9, &v10) )
  {
    if ( v10 )
    {
      if ( (unsigned int)ASN1BERDecLength(a1, &v8, &v5) )
      {
        v2 = a1;
        if ( !v5 )
        {
          *(_QWORD *)(a1 + 40) += v8;
LABEL_7:
          ASN1DecSetError(v2, 0);
          return 1;
        }
        for ( i = BERDecConstructed(a1, v8, v5, &v6, (unsigned __int64 *)&v7); i; i = ASN1BERDecSkip(v6) )
        {
          if ( !(unsigned int)ASN1BERDecNotEndOfContents(v6, v7) )
          {
            if ( !(unsigned int)ASN1BERDecEndOfContents(a1, v6, v7) )
              return 0;
            goto LABEL_13;
          }
        }
      }
    }
    else if ( (unsigned int)ASN1BERDecLength(a1, &v8, 0) )
    {
      *(_QWORD *)(a1 + 40) += v8;
LABEL_13:
      v2 = a1;
      goto LABEL_7;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180001f80  mov     [rsp-8+arg_0], rbx
0x180001f85  push    rbp
0x180001f86  mov     rbp, rsp
0x180001f89  sub     rsp, 50h
0x180001f8d  mov     edx, 3E9h
0x180001f92  mov     [rbp+arg_10], 0
0x180001f99  mov     rbx, rcx
0x180001f9c  mov     [rbp+arg_18], 0
0x180001fa3  mov     [rbp+arg_8], 0
0x180001faa  mov     [rbp+var_20], 0
0x180001fb1  mov     [rbp+var_18], 0
0x180001fb9  mov     [rbp+var_10], 0
0x180001fc1  call    ASN1DecSetError
0x180001fc6  lea     rdx, [rbp+arg_10]
0x180001fca  mov     rcx, rbx
0x180001fcd  call    ASN1BERDecPeekTag
0x180001fd2  test    eax, eax
0x180001fd4  jz      short loc_18000203D
0x180001fd6  mov     edx, [rbp+arg_10]
0x180001fd9  lea     r8, [rbp+arg_18]
0x180001fdd  mov     rcx, rbx
0x180001fe0  call    ASN1BERDecTag
0x180001fe5  test    eax, eax
0x180001fe7  jz      short loc_18000203D
0x180001fe9  cmp     [rbp+arg_18], 0
0x180001fed  lea     rdx, [rbp+arg_8]
0x180001ff1  mov     rcx, rbx
0x180001ff4  jz      short loc_18000204A
0x180001ff6  lea     r8, [rbp+var_20]
0x180001ffa  call    ASN1BERDecLength
0x180001fff  test    eax, eax
0x180002001  jz      short loc_18000203D
0x180002003  mov     r8d, [rbp+var_20]
0x180002007  mov     rcx, rbx
0x18000200a  test    r8d, r8d
0x18000200d  jnz     short loc_180002024
0x18000200f  mov     eax, [rbp+arg_8]
0x180002012  add     [rbx+28h], rax
0x180002016  xor     edx, edx
0x180002018  call    ASN1DecSetError
0x18000201d  mov     eax, 1
0x180002022  jmp     short loc_18000203F
0x180002024  mov     edx, [rbp+arg_8]
0x180002027  lea     rax, [rbp+var_10]
0x18000202b  lea     r9, [rbp+var_18]
0x18000202f  mov     [rsp+50h+var_30], rax
0x180002034  call    _BERDecConstructed
0x180002039  test    eax, eax
0x18000203b  jnz     short loc_180002062
0x18000203d  xor     eax, eax
0x18000203f  mov     rbx, [rsp+50h+arg_0]
0x180002044  add     rsp, 50h
0x180002048  pop     rbp
0x180002049  retn
0x18000204a  xor     r8d, r8d
0x18000204d  call    ASN1BERDecLength
0x180002052  test    eax, eax
0x180002054  jz      short loc_18000203D
0x180002056  mov     eax, [rbp+arg_8]
0x180002059  add     [rbx+28h], rax
0x18000205d  mov     rcx, rbx
0x180002060  jmp     short loc_180002016
0x180002062  mov     rdx, [rbp+var_10]
0x180002066  mov     rcx, [rbp+var_18]
0x18000206a  call    ASN1BERDecNotEndOfContents
0x18000206f  test    eax, eax
0x180002071  jz      short loc_18000207E
0x180002073  mov     rcx, [rbp+var_18]
0x180002077  call    ASN1BERDecSkip
0x18000207c  jmp     short loc_180002039
0x18000207e  mov     r8, [rbp+var_10]
0x180002082  mov     rcx, rbx
0x180002085  mov     rdx, [rbp+var_18]
0x180002089  call    ASN1BERDecEndOfContents
0x18000208e  test    eax, eax
0x180002090  jz      short loc_18000203D
0x180002092  jmp     short loc_18000205D
```
