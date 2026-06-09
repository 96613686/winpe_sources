# _ValidateBootMeasurement

- ea: `0x1800046ec`
- end: `0x1800047c8`
- name: `_ValidateBootMeasurement`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800044a8`

## callees

- `0x1800046ec`
- `0x18000489c`
- `0x1800067e0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x18000478f`
- `ntoskrnl!RtlCompareMemory` at `0x18000478f`

## pseudocode

```c
__int64 __fastcall ValidateBootMeasurement(int a1, unsigned __int8 a2, __int64 a3, const void *a4)
{
  __int64 v5; // rdi
  __m128i si128; // xmm0
  unsigned int v7; // esi
  int v8; // ebx
  _OWORD v10[2]; // [rsp+20h] [rbp-68h] BYREF
  _OWORD Source2[2]; // [rsp+40h] [rbp-48h] BYREF

  v5 = a3;
  if ( (unsigned __int8)(a2 - 1) <= 2u )
  {
    si128 = 0;
    memset(v10, 0, sizeof(v10));
    if ( a3 )
    {
      v7 = a2;
      if ( a2 <= 3u )
      {
        if ( (a1 & 0x20) != 0 )
          si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
        LODWORD(v10[0]) = a1;
        Source2[1] = si128;
        Source2[0] = si128;
        if ( (unsigned int)DevAuth2_DrAppend(Source2, v10) )
        {
          v8 = 0;
          if ( v7 )
          {
            while ( (unsigned int)DevAuth2_DrAppend(Source2, v5) )
            {
              v5 += 32;
              if ( ++v8 >= v7 )
                goto LABEL_10;
            }
          }
          else
          {
LABEL_10:
            if ( RtlCompareMemory(a4, Source2, 0x20u) == 32 )
              return 1;
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800046ec  mov     [rsp+arg_0], rbx
0x1800046f1  push    rbp
0x1800046f2  push    rsi
0x1800046f3  push    rdi
0x1800046f4  sub     rsp, 70h
0x1800046f8  mov     rax, cs:__security_cookie
0x1800046ff  xor     rax, rsp
0x180004702  mov     [rsp+88h+var_28], rax
0x180004707  lea     eax, [rdx-1]
0x18000470a  mov     rbp, r9
0x18000470d  mov     rdi, r8
0x180004710  cmp     al, 2
0x180004712  ja      loc_1800047A8
0x180004718  xorps   xmm0, xmm0
0x18000471b  movups  [rsp+88h+var_68], xmm0
0x180004720  movups  [rsp+88h+var_58], xmm0
0x180004725  test    r8, r8
0x180004728  jz      short loc_1800047A8
0x18000472a  movzx   esi, dl
0x18000472d  cmp     esi, 3
0x180004730  ja      short loc_1800047A8
0x180004732  test    cl, 20h
0x180004735  jz      short loc_18000473F
0x180004737  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000473f  mov     dword ptr [rsp+88h+var_68], ecx
0x180004743  lea     rdx, [rsp+88h+var_68]
0x180004748  lea     rcx, [rsp+88h+Source2]
0x18000474d  movups  [rsp+88h+var_38], xmm0
0x180004752  movups  [rsp+88h+Source2], xmm0
0x180004757  call    DevAuth2_DrAppend
0x18000475c  test    eax, eax
0x18000475e  jz      short loc_1800047A8
0x180004760  xor     ebx, ebx
0x180004762  test    esi, esi
0x180004764  jz      short loc_180004781
0x180004766  mov     rdx, rdi
0x180004769  lea     rcx, [rsp+88h+Source2]
0x18000476e  call    DevAuth2_DrAppend
0x180004773  test    eax, eax
0x180004775  jz      short loc_1800047A8
0x180004777  add     rdi, 20h ; ' '
0x18000477b  inc     ebx
0x18000477d  cmp     ebx, esi
0x18000477f  jb      short loc_180004766
0x180004781  mov     r8d, 20h ; ' '; Length
0x180004787  lea     rdx, [rsp+88h+Source2]; Source2
0x18000478c  mov     rcx, rbp; Source1
0x18000478f  call    cs:__imp_RtlCompareMemory
0x180004796  nop     dword ptr [rax+rax+00h]
0x18000479b  cmp     rax, 20h ; ' '
0x18000479f  jnz     short loc_1800047A8
0x1800047a1  mov     eax, 1
0x1800047a6  jmp     short loc_1800047AA
0x1800047a8  xor     eax, eax
0x1800047aa  mov     rcx, [rsp+88h+var_28]
0x1800047af  xor     rcx, rsp; StackCookie
0x1800047b2  call    __security_check_cookie
0x1800047b7  mov     rbx, [rsp+88h+arg_0]
0x1800047bf  add     rsp, 70h
0x1800047c3  pop     rdi
0x1800047c4  pop     rsi
0x1800047c5  pop     rbp
0x1800047c6  retn
```
