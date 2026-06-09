# DevAuthGetHostStrictPairingCert

- ea: `0x1800037ac`
- end: `0x1800038fe`
- name: `DevAuthGetHostStrictPairingCert`
- size: `338`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180001e04`

## callees

- `0x180002740`
- `0x180002b38`
- `0x1800037ac`
- `0x1800067e0`
- `0x180006cc0`

## pseudocode

```c
_BOOL8 __fastcall DevAuthGetHostStrictPairingCert(_OWORD *a1, int a2, __int64 a3, _OWORD *a4)
{
  _OWORD *v7; // rax
  __int128 v8; // xmm1
  __int64 *v9; // rcx
  __int64 v10; // rdx
  __int128 v11; // xmm1
  __int64 v12; // r9
  int v14; // [rsp+40h] [rbp-9h] BYREF
  _OWORD *v15; // [rsp+48h] [rbp-1h] BYREF
  UCHAR v16[16]; // [rsp+50h] [rbp+7h] BYREF
  __int128 v17; // [rsp+60h] [rbp+17h]

  memset(a4, 0, 0x240u);
  v15 = a1;
  v14 = a2;
  if ( !(unsigned int)DevAuthGetHashAllInOne(0, 0, (__int64)&v15, (__int64)&v14, 1u) )
    return 0;
  v7 = a4 + 2;
  v8 = v17;
  v9 = c_pbHostPublicKey;
  *a4 = *(_OWORD *)v16;
  v10 = 2;
  a4[1] = v8;
  *((_BYTE *)a4 + 288) = 0;
  do
  {
    *v7 = *(_OWORD *)v9;
    v7[1] = *((_OWORD *)v9 + 1);
    v7[2] = *((_OWORD *)v9 + 2);
    v7[3] = *((_OWORD *)v9 + 3);
    v7[4] = *((_OWORD *)v9 + 4);
    v7[5] = *((_OWORD *)v9 + 5);
    v7[6] = *((_OWORD *)v9 + 6);
    v11 = *((_OWORD *)v9 + 7);
    v9 += 16;
    v7[7] = v11;
    v7 += 8;
    --v10;
  }
  while ( v10 );
  v15 = a4;
  v14 = 320;
  return (unsigned int)DevAuthGetHashAllInOne(0, 0, (__int64)&v15, (__int64)&v14, 1u)
      && !*((_BYTE *)a4 + 288)
      && DevAuthSignHash(pbInput, 0x21Bu, v16, v12, (PUCHAR)a4 + 320);
}

```

## disassembly

```asm
0x1800037ac  push    rbp
0x1800037ae  push    rbx
0x1800037af  push    rsi
0x1800037b0  push    rdi
0x1800037b1  lea     rbp, [rsp-3Fh]
0x1800037b6  sub     rsp, 88h
0x1800037bd  mov     rax, cs:__security_cookie
0x1800037c4  xor     rax, rsp
0x1800037c7  mov     [rbp+57h+var_30], rax
0x1800037cb  mov     edi, edx
0x1800037cd  mov     rbx, rcx
0x1800037d0  xor     edx, edx; Val
0x1800037d2  mov     rcx, r9; void *
0x1800037d5  mov     r8d, 240h; Size
0x1800037db  mov     rsi, r9
0x1800037de  call    memset
0x1800037e3  lea     rax, [rbp+57h+var_50]
0x1800037e7  mov     [rbp+57h+var_58], rbx
0x1800037eb  mov     [rsp+0A0h+var_78], rax
0x1800037f0  lea     r9, [rbp+57h+var_60]
0x1800037f4  mov     ebx, 1
0x1800037f9  mov     [rbp+57h+var_60], edi
0x1800037fc  lea     r8, [rbp+57h+var_58]
0x180003800  mov     dword ptr [rsp+0A0h+pbOutput], ebx
0x180003804  xor     edx, edx
0x180003806  xor     ecx, ecx
0x180003808  call    DevAuthGetHashAllInOne
0x18000380d  test    eax, eax
0x18000380f  jz      loc_1800038E3
0x180003815  movups  xmm0, xmmword ptr [rbp+57h+var_50]
0x180003819  lea     rax, [rsi+20h]
0x18000381d  movups  xmm1, [rbp+57h+var_40]
0x180003821  lea     rcx, c_pbHostPublicKey
0x180003828  movups  xmmword ptr [rsi], xmm0
0x18000382b  lea     edx, [rbx+1]
0x18000382e  movups  xmmword ptr [rsi+10h], xmm1
0x180003832  mov     byte ptr [rsi+120h], 0
0x180003839  lea     r8d, [rbx+7Fh]
0x18000383d  movups  xmm0, xmmword ptr [rcx]
0x180003840  movups  xmmword ptr [rax], xmm0
0x180003843  movups  xmm1, xmmword ptr [rcx+10h]
0x180003847  movups  xmmword ptr [rax+10h], xmm1
0x18000384b  movups  xmm0, xmmword ptr [rcx+20h]
0x18000384f  movups  xmmword ptr [rax+20h], xmm0
0x180003853  movups  xmm1, xmmword ptr [rcx+30h]
0x180003857  movups  xmmword ptr [rax+30h], xmm1
0x18000385b  movups  xmm0, xmmword ptr [rcx+40h]
0x18000385f  movups  xmmword ptr [rax+40h], xmm0
0x180003863  movups  xmm1, xmmword ptr [rcx+50h]
0x180003867  movups  xmmword ptr [rax+50h], xmm1
0x18000386b  movups  xmm0, xmmword ptr [rcx+60h]
0x18000386f  movups  xmmword ptr [rax+60h], xmm0
0x180003873  movups  xmm1, xmmword ptr [rcx+70h]
0x180003877  add     rcx, r8
0x18000387a  movups  xmmword ptr [rax+70h], xmm1
0x18000387e  add     rax, r8
0x180003881  sub     rdx, rbx
0x180003884  jnz     short loc_18000383D
0x180003886  lea     rax, [rbp+57h+var_50]
0x18000388a  mov     [rbp+57h+var_58], rsi
0x18000388e  mov     [rsp+0A0h+var_78], rax
0x180003893  lea     r9, [rbp+57h+var_60]
0x180003897  lea     r8, [rbp+57h+var_58]
0x18000389b  mov     dword ptr [rsp+0A0h+pbOutput], ebx
0x18000389f  xor     ecx, ecx
0x1800038a1  mov     [rbp+57h+var_60], 140h
0x1800038a8  call    DevAuthGetHashAllInOne
0x1800038ad  test    eax, eax
0x1800038af  jz      short loc_1800038E3
0x1800038b1  cmp     byte ptr [rsi+120h], 0
0x1800038b8  jnz     short loc_1800038E3
0x1800038ba  lea     rcx, [rsi+140h]
0x1800038c1  mov     edx, 21Bh; cbInput
0x1800038c6  mov     [rsp+0A0h+pbOutput], rcx; pbOutput
0x1800038cb  lea     r8, [rbp+57h+var_50]; PUCHAR
0x1800038cf  lea     rcx, pbInput; "RSA2"
0x1800038d6  call    DevAuthSignHash
0x1800038db  test    eax, eax
0x1800038dd  jz      short loc_1800038E3
0x1800038df  mov     eax, ebx
0x1800038e1  jmp     short loc_1800038E5
0x1800038e3  xor     eax, eax
0x1800038e5  mov     rcx, [rbp+57h+var_30]
0x1800038e9  xor     rcx, rsp; StackCookie
0x1800038ec  call    __security_check_cookie
0x1800038f1  add     rsp, 88h
0x1800038f8  pop     rdi
0x1800038f9  pop     rsi
0x1800038fa  pop     rbx
0x1800038fb  pop     rbp
0x1800038fc  retn
```
