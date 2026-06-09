# _ProcessDeviceKeyExchange

- ea: `0x180004594`
- end: `0x1800046e5`
- name: `_ProcessDeviceKeyExchange`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000409c`

## callees

- `0x180002740`
- `0x180004594`
- `0x18000489c`
- `0x18000490c`
- `0x180004ccc`
- `0x1800067e0`

## pseudocode

```c
__int64 __fastcall ProcessDeviceKeyExchange(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // rbx
  _OWORD *v5; // rdi
  __int64 v6; // rax
  UCHAR *v7; // r14
  __int128 v8; // xmm1
  __int64 v9; // rcx
  __int64 v10; // r9
  __int64 result; // rax
  _DWORD v12[2]; // [rsp+40h] [rbp-19h] BYREF
  _OWORD v13[2]; // [rsp+48h] [rbp-11h] BYREF
  _OWORD v14[2]; // [rsp+68h] [rbp+Fh] BYREF

  v3 = a1;
  LOBYTE(a1) = 36;
  if ( (unsigned int)DevAuth2_ValidateMessageHeader(a1, a2, a2, a3) )
  {
    v12[0] = 64;
    *((_QWORD *)&v13[0] + 1) = v3 + 16;
    v5 = (_OWORD *)(a2 + 4);
    v12[1] = 32;
    v6 = 0;
    *(_QWORD *)&v13[0] = a2 + 4;
    memset(v14, 0, sizeof(v14));
    while ( *((_QWORD *)v13 + v6) && v12[v6] )
    {
      v6 = (unsigned int)(v6 + 1);
      if ( (unsigned int)v6 >= 2 )
      {
        if ( (unsigned int)DevAuthGetHashAllInOne(0, 0, (__int64)v13, (__int64)v12, 2u) )
        {
          if ( v3 != -292 && v3 != -184 )
          {
            v7 = (UCHAR *)(a2 + 68);
            if ( v7 )
            {
              v8 = *(_OWORD *)(v3 + 200);
              v13[0] = *(_OWORD *)(v3 + 184);
              v13[1] = v8;
              if ( (unsigned int)DevAuth2_DrAppend(v13, v14) )
              {
                if ( DevAuth2_EcdsaVerifySignature(v9, (_OWORD *)(v3 + 292), (UCHAR *)v13, v10, v7) )
                {
                  result = 1;
                  *(_OWORD *)(v3 + 216) = *v5;
                  *(_OWORD *)(v3 + 232) = v5[1];
                  *(_OWORD *)(v3 + 248) = v5[2];
                  *(_OWORD *)(v3 + 264) = v5[3];
                  return result;
                }
              }
            }
          }
        }
        return 0;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180004594  push    rbp
0x180004596  push    rbx
0x180004597  push    rsi
0x180004598  push    rdi
0x180004599  push    r14
0x18000459b  lea     rbp, [rsp-37h]
0x1800045a0  sub     rsp, 90h
0x1800045a7  mov     rax, cs:__security_cookie
0x1800045ae  xor     rax, rsp
0x1800045b1  mov     [rbp+57h+var_28], rax
0x1800045b5  mov     rbx, rcx
0x1800045b8  mov     r9d, r8d
0x1800045bb  mov     r8, rdx
0x1800045be  mov     cl, 24h ; '$'
0x1800045c0  mov     r14, rdx
0x1800045c3  call    DevAuth2_ValidateMessageHeader
0x1800045c8  test    eax, eax
0x1800045ca  jz      loc_1800046C8
0x1800045d0  lea     rax, [rbx+10h]
0x1800045d4  mov     [rbp+57h+var_70], 40h ; '@'
0x1800045db  xorps   xmm0, xmm0
0x1800045de  mov     qword ptr [rbp+57h+var_68+8], rax
0x1800045e2  lea     rdi, [r14+4]
0x1800045e6  mov     [rbp+57h+var_6C], 20h ; ' '
0x1800045ed  xor     eax, eax
0x1800045ef  mov     qword ptr [rbp+57h+var_68], rdi
0x1800045f3  movups  [rbp+57h+var_48], xmm0
0x1800045f7  movups  [rbp+57h+var_38], xmm0
0x1800045fb  cmp     qword ptr [rbp+rax*8+57h+var_68], 0
0x180004601  jz      loc_1800046C8
0x180004607  cmp     [rbp+rax*4+57h+var_70], 0
0x18000460c  jz      loc_1800046C8
0x180004612  inc     eax
0x180004614  cmp     eax, 2
0x180004617  jb      short loc_1800045FB
0x180004619  lea     rax, [rbp+57h+var_48]
0x18000461d  xor     edx, edx
0x18000461f  mov     [rsp+0B0h+var_88], rax
0x180004624  lea     r9, [rbp+57h+var_70]
0x180004628  lea     r8, [rbp+57h+var_68]
0x18000462c  mov     dword ptr [rsp+0B0h+var_90], 2
0x180004634  xor     ecx, ecx
0x180004636  call    DevAuthGetHashAllInOne
0x18000463b  test    eax, eax
0x18000463d  jz      loc_1800046C8
0x180004643  lea     rsi, [rbx+124h]
0x18000464a  test    rsi, rsi
0x18000464d  jz      short loc_1800046C8
0x18000464f  lea     rax, [rbx+0B8h]
0x180004656  test    rax, rax
0x180004659  jz      short loc_1800046C8
0x18000465b  add     r14, 44h ; 'D'
0x18000465f  jz      short loc_1800046C8
0x180004661  movups  xmm0, xmmword ptr [rax]
0x180004664  lea     rdx, [rbp+57h+var_48]
0x180004668  movups  xmm1, xmmword ptr [rax+10h]
0x18000466c  lea     rcx, [rbp+57h+var_68]
0x180004670  movups  [rbp+57h+var_68], xmm0
0x180004674  movups  [rbp+57h+var_58], xmm1
0x180004678  call    DevAuth2_DrAppend
0x18000467d  test    eax, eax
0x18000467f  jz      short loc_1800046C8
0x180004681  lea     r8, [rbp+57h+var_68]
0x180004685  mov     [rsp+0B0h+var_90], r14
0x18000468a  mov     rdx, rsi
0x18000468d  call    DevAuth2_EcdsaVerifySignature
0x180004692  test    eax, eax
0x180004694  jz      short loc_1800046C8
0x180004696  movups  xmm0, xmmword ptr [rdi]
0x180004699  mov     eax, 1
0x18000469e  movups  xmmword ptr [rbx+0D8h], xmm0
0x1800046a5  movups  xmm1, xmmword ptr [rdi+10h]
0x1800046a9  movups  xmmword ptr [rbx+0E8h], xmm1
0x1800046b0  movups  xmm0, xmmword ptr [rdi+20h]
0x1800046b4  movups  xmmword ptr [rbx+0F8h], xmm0
0x1800046bb  movups  xmm1, xmmword ptr [rdi+30h]
0x1800046bf  movups  xmmword ptr [rbx+108h], xmm1
0x1800046c6  jmp     short loc_1800046CA
0x1800046c8  xor     eax, eax
0x1800046ca  mov     rcx, [rbp+57h+var_28]
0x1800046ce  xor     rcx, rsp; StackCookie
0x1800046d1  call    __security_check_cookie
0x1800046d6  add     rsp, 90h
0x1800046dd  pop     r14
0x1800046df  pop     rdi
0x1800046e0  pop     rsi
0x1800046e1  pop     rbx
0x1800046e2  pop     rbp
0x1800046e3  retn
```
