# DevAuth2_DrAppend

- ea: `0x18000489c`
- end: `0x180004903`
- name: `DevAuth2_DrAppend`
- size: `103`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004594`
- `0x1800046ec`

## callees

- `0x180002740`
- `0x18000489c`

## pseudocode

```c
__int64 __fastcall DevAuth2_DrAppend(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  _QWORD v4[3]; // [rsp+40h] [rbp-18h] BYREF
  int v5; // [rsp+60h] [rbp+8h] BYREF
  int v6; // [rsp+64h] [rbp+Ch]

  if ( a1 && a2 )
  {
    v4[0] = a1;
    v5 = 32;
    v6 = 32;
    v2 = 0;
    v4[1] = a2;
    while ( v4[v2] && *(&v5 + v2) )
    {
      v2 = (unsigned int)(v2 + 1);
      if ( (unsigned int)v2 >= 2 )
        return DevAuthGetHashAllInOne(0, 0, (__int64)v4, (__int64)&v5, 2u);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000489c  sub     rsp, 58h
0x1800048a0  test    rcx, rcx
0x1800048a3  jz      short loc_1800048FB
0x1800048a5  test    rdx, rdx
0x1800048a8  jz      short loc_1800048FB
0x1800048aa  mov     eax, 20h ; ' '
0x1800048af  mov     [rsp+58h+var_18], rcx
0x1800048b4  mov     [rsp+58h+arg_0], eax
0x1800048b8  mov     [rsp+58h+arg_4], eax
0x1800048bc  xor     eax, eax
0x1800048be  mov     [rsp+58h+var_10], rdx
0x1800048c3  cmp     [rsp+rax*8+58h+var_18], 0
0x1800048c9  jz      short loc_1800048FB
0x1800048cb  cmp     [rsp+rax*4+58h+arg_0], 0
0x1800048d0  jz      short loc_1800048FB
0x1800048d2  inc     eax
0x1800048d4  cmp     eax, 2
0x1800048d7  jb      short loc_1800048C3
0x1800048d9  mov     [rsp+58h+var_30], rcx
0x1800048de  lea     r9, [rsp+58h+arg_0]
0x1800048e3  xor     ecx, ecx
0x1800048e5  mov     [rsp+58h+var_38], 2
0x1800048ed  lea     r8, [rsp+58h+var_18]
0x1800048f2  xor     edx, edx
0x1800048f4  call    DevAuthGetHashAllInOne
0x1800048f9  jmp     short loc_1800048FD
0x1800048fb  xor     eax, eax
0x1800048fd  add     rsp, 58h
0x180004901  retn
```
