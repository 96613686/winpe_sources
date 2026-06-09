# DevAuth2_HostGetRequest

- ea: `0x180003e20`
- end: `0x180004093`
- name: `DevAuth2_HostGetRequest`
- size: `627`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800015f0`

## callees

- `0x1800026e8`
- `0x1800027dc`
- `0x180002888`
- `0x180003e20`
- `0x180004280`
- `0x1800067e0`
- `0x180006cc0`

## import_xrefs

- `cng!BCryptHashData` at `0x180004046`
- `cng!BCryptHashData` at `0x180004046`

## pseudocode

```c
__int64 __fastcall DevAuth2_HostGetRequest(__int64 a1, _BYTE *a2, __int64 a3, _DWORD *a4)
{
  ULONG v4; // esi
  unsigned int v8; // ebp
  __int64 v9; // r8
  _DWORD *v10; // r14
  __int64 v11; // rcx
  __int64 v12; // rcx
  size_t Size; // [rsp+30h] [rbp-68h]
  ULONG v15; // [rsp+40h] [rbp-58h] BYREF
  int v16[8]; // [rsp+48h] [rbp-50h] BYREF

  v4 = 0;
  v15 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      if ( a4 )
      {
        v8 = 1;
        if ( *(_BYTE *)a1 == 1 && !*(_DWORD *)(a1 + 8) )
        {
          memset(a2, 0, 0x5DCu);
          v10 = a2 + 5;
          switch ( *(_BYTE *)(a1 + 1) )
          {
            case '!':
              *a2 = 65;
              *(_WORD *)(a2 + 1) = 8448;
              if ( a1 == -16 || !(unsigned int)DevAuthGenerateRandomNumber((void *)(a1 + 16), 0x20u) )
                goto LABEL_35;
              *v10 = 603980321;
              *(_OWORD *)(a2 + 9) = *(_OWORD *)(a1 + 16);
              v4 = 40;
              *(_OWORD *)(a2 + 25) = *(_OWORD *)(a1 + 32);
              *(_DWORD *)(a2 + 41) = _byteswap_ulong(*(_DWORD *)(a1 + 12));
              break;
            case '"':
              *a2 = 66;
              *(_DWORD *)(a2 + 1) = -1342168576;
              goto LABEL_34;
            case '#':
              *a2 = 66;
              *(_DWORD *)(a2 + 1) = 67314432;
              goto LABEL_34;
            case '$':
              *a2 = 66;
              *(_DWORD *)(a2 + 1) = -2080365568;
              goto LABEL_34;
            case '%':
              *a2 = 65;
              *(_WORD *)(a2 + 1) = 9472;
              if ( !(unsigned int)GenerateHostKeyExchange_0(a1, a2 + 5, v9, &v15) )
                goto LABEL_35;
              v4 = v15;
              break;
            case '&':
              *a2 = 65;
              *(_WORD *)(a2 + 1) = 9728;
              v11 = *(_QWORD *)(a1 + 1096);
              if ( !v11 )
                goto LABEL_35;
              if ( !(unsigned int)DevAuthGetRunningHash(v11, v16) )
                goto LABEL_35;
              if ( a1 == -1048 )
                goto LABEL_35;
              if ( a2 == (_BYTE *)-9LL )
                goto LABEL_35;
              LODWORD(Size) = 32;
              if ( !(unsigned int)DevAuthPesudoRandomFunction(
                                    (__int64)"Host Finished",
                                    (int)a1 + 1048,
                                    48,
                                    (__int64)v16,
                                    32,
                                    a2 + 9,
                                    Size) )
                goto LABEL_35;
              *v10 = 536871462;
              v4 = 36;
              break;
            case '\'':
              *a2 = 66;
              *(_DWORD *)(a2 + 1) = 1140860672;
LABEL_34:
              *(_DWORD *)(a1 + 8) = 1;
              *a4 = v4 + 5;
              return v8;
            default:
LABEL_35:
              v8 = 0;
              *(_BYTE *)a1 = 3;
              return v8;
          }
          if ( *a2 == 65 )
            *(_WORD *)(a2 + 3) = ((_WORD)v4 << 8) | BYTE1(v4);
          if ( !v4 )
            goto LABEL_34;
          v12 = *(_QWORD *)(a1 + 1096);
          if ( v12 )
          {
            if ( a2 != (_BYTE *)-5LL && BCryptHashData(*(BCRYPT_HASH_HANDLE *)(v12 + 8), a2 + 5, v4, 0) >= 0 )
              goto LABEL_34;
          }
          goto LABEL_35;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003e20  mov     [rsp+arg_10], rbx
0x180003e25  push    rbp
0x180003e26  push    rsi
0x180003e27  push    rdi
0x180003e28  push    r14
0x180003e2a  push    r15
0x180003e2c  sub     rsp, 70h
0x180003e30  mov     rax, cs:__security_cookie
0x180003e37  xor     rax, rsp
0x180003e3a  mov     [rsp+98h+var_30], rax
0x180003e3f  xor     esi, esi
0x180003e41  mov     r15, r9
0x180003e44  mov     [rsp+98h+var_58], esi
0x180003e48  mov     rbx, rdx
0x180003e4b  mov     rdi, rcx
0x180003e4e  test    rcx, rcx
0x180003e51  jz      loc_18000406F
0x180003e57  test    rdx, rdx
0x180003e5a  jz      loc_18000406F
0x180003e60  test    r9, r9
0x180003e63  jz      loc_18000406F
0x180003e69  lea     ebp, [rsi+1]
0x180003e6c  cmp     [rcx], bpl
0x180003e6f  jnz     loc_18000406F
0x180003e75  cmp     [rcx+8], esi
0x180003e78  jnz     loc_18000406F
0x180003e7e  xor     edx, edx; Val
0x180003e80  mov     r8d, 5DCh; Size
0x180003e86  mov     rcx, rbx; void *
0x180003e89  call    memset
0x180003e8e  movzx   ecx, byte ptr [rdi+1]
0x180003e92  lea     r14, [rbx+5]
0x180003e96  sub     ecx, 21h ; '!'
0x180003e99  jz      loc_180003FB9
0x180003e9f  sub     ecx, ebp
0x180003ea1  jz      loc_180003FAA
0x180003ea7  sub     ecx, ebp
0x180003ea9  jz      loc_180003F9B
0x180003eaf  sub     ecx, ebp
0x180003eb1  jz      loc_180003F8C
0x180003eb7  sub     ecx, ebp
0x180003eb9  jz      loc_180003F65
0x180003ebf  sub     ecx, ebp
0x180003ec1  jz      short loc_180003EDA
0x180003ec3  cmp     ecx, ebp
0x180003ec5  jnz     loc_180004066
0x180003ecb  mov     byte ptr [rbx], 42h ; 'B'
0x180003ece  mov     dword ptr [rbx+1], 44002700h
0x180003ed5  jmp     loc_18000405B
0x180003eda  mov     byte ptr [rbx], 41h ; 'A'
0x180003edd  mov     word ptr [rbx+1], 2600h
0x180003ee3  mov     rcx, [rdi+448h]
0x180003eea  test    rcx, rcx
0x180003eed  jz      loc_180004066
0x180003ef3  lea     rdx, [rsp+98h+var_50]
0x180003ef8  call    DevAuthGetRunningHash
0x180003efd  test    eax, eax
0x180003eff  jz      loc_180004066
0x180003f05  lea     rax, [rdi+418h]
0x180003f0c  test    rax, rax
0x180003f0f  jz      loc_180004066
0x180003f15  lea     rcx, [r14+4]
0x180003f19  test    rcx, rcx
0x180003f1c  jz      loc_180004066
0x180003f22  mov     edx, 20h ; ' '
0x180003f27  lea     r9, [rsp+98h+var_50]; int
0x180003f2c  mov     dword ptr [rsp+98h+Size], edx; Size
0x180003f30  mov     [rsp+98h+var_70], rcx; void *
0x180003f35  lea     rcx, aHostFinished; "Host Finished"
0x180003f3c  mov     [rsp+98h+var_78], edx; int
0x180003f40  lea     r8d, [rdx+10h]; int
0x180003f44  mov     rdx, rax; int
0x180003f47  call    DevAuthPesudoRandomFunction
0x180003f4c  test    eax, eax
0x180003f4e  jz      loc_180004066
0x180003f54  mov     dword ptr [r14], 20000226h
0x180003f5b  mov     esi, 24h ; '$'
0x180003f60  jmp     loc_18000400A
0x180003f65  lea     r9, [rsp+98h+var_58]
0x180003f6a  mov     byte ptr [rbx], 41h ; 'A'
0x180003f6d  mov     rdx, r14
0x180003f70  mov     word ptr [rbx+1], 2500h
0x180003f76  mov     rcx, rdi
0x180003f79  call    _GenerateHostKeyExchange_0
0x180003f7e  test    eax, eax
0x180003f80  jz      loc_180004066
0x180003f86  mov     esi, [rsp+98h+var_58]
0x180003f8a  jmp     short loc_18000400A
0x180003f8c  mov     byte ptr [rbx], 42h ; 'B'
0x180003f8f  mov     dword ptr [rbx+1], 84002400h
0x180003f96  jmp     loc_18000405B
0x180003f9b  mov     byte ptr [rbx], 42h ; 'B'
0x180003f9e  mov     dword ptr [rbx+1], 4032300h
0x180003fa5  jmp     loc_18000405B
0x180003faa  mov     byte ptr [rbx], 42h ; 'B'
0x180003fad  mov     dword ptr [rbx+1], 0B0002200h
0x180003fb4  jmp     loc_18000405B
0x180003fb9  lea     rsi, [rdi+10h]
0x180003fbd  mov     byte ptr [rbx], 41h ; 'A'
0x180003fc0  mov     word ptr [rbx+1], 2100h
0x180003fc6  test    rsi, rsi
0x180003fc9  jz      loc_180004066
0x180003fcf  mov     edx, 20h ; ' '; Size
0x180003fd4  mov     rcx, rsi; void *
0x180003fd7  call    DevAuthGenerateRandomNumber
0x180003fdc  test    eax, eax
0x180003fde  jz      loc_180004066
0x180003fe4  mov     dword ptr [r14], 24000221h
0x180003feb  movups  xmm0, xmmword ptr [rsi]
0x180003fee  movups  xmmword ptr [r14+4], xmm0
0x180003ff3  movups  xmm1, xmmword ptr [rsi+10h]
0x180003ff7  mov     esi, 28h ; '('
0x180003ffc  movups  xmmword ptr [r14+14h], xmm1
0x180004001  mov     eax, [rdi+0Ch]
0x180004004  bswap   eax
0x180004006  mov     [r14+24h], eax
0x18000400a  cmp     byte ptr [rbx], 41h ; 'A'
0x18000400d  jnz     short loc_180004024
0x18000400f  movzx   ecx, si
0x180004012  movzx   eax, si
0x180004015  shr     cx, 8
0x180004019  shl     ax, 8
0x18000401d  or      cx, ax
0x180004020  mov     [rbx+3], cx
0x180004024  test    esi, esi
0x180004026  jz      short loc_18000405B
0x180004028  mov     rcx, [rdi+448h]
0x18000402f  test    rcx, rcx
0x180004032  jz      short loc_180004066
0x180004034  test    r14, r14
0x180004037  jz      short loc_180004066
0x180004039  mov     rcx, [rcx+8]; hHash
0x18000403d  xor     r9d, r9d; dwFlags
0x180004040  mov     r8d, esi; cbInput
0x180004043  mov     rdx, r14; pbInput
0x180004046  call    cs:__imp_BCryptHashData
0x18000404d  nop     dword ptr [rax+rax+00h]
0x180004052  not     eax
0x180004054  shr     eax, 1Fh
0x180004057  test    eax, eax
0x180004059  jz      short loc_180004066
0x18000405b  lea     eax, [rsi+5]
0x18000405e  mov     [rdi+8], ebp
0x180004061  mov     [r15], eax
0x180004064  jmp     short loc_18000406B
0x180004066  xor     ebp, ebp
0x180004068  mov     byte ptr [rdi], 3
0x18000406b  mov     eax, ebp
0x18000406d  jmp     short loc_180004071
0x18000406f  xor     eax, eax
0x180004071  mov     rcx, [rsp+98h+var_30]
0x180004076  xor     rcx, rsp; StackCookie
0x180004079  call    __security_check_cookie
0x18000407e  mov     rbx, [rsp+98h+arg_10]
0x180004086  add     rsp, 70h
0x18000408a  pop     r15
0x18000408c  pop     r14
0x18000408e  pop     rdi
0x18000408f  pop     rsi
0x180004090  pop     rbp
0x180004091  retn
```
