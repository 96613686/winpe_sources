# GetMsftVerifyData

- ea: `0x180005020`
- end: `0x1800051eb`
- name: `GetMsftVerifyData`
- size: `459`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180002444`
- `0x180004368`

## callees

- `0x1800051f4`
- `0x180005250`
- `0x180005f7c`
- `0x1800067e0`
- `0x180006cc0`

## pseudocode

```c
__int64 __fastcall GetMsftVerifyData(unsigned __int128 *a1, unsigned __int64 a2, unsigned __int128 *a3, __int64 a4)
{
  int v8; // r8d
  unsigned __int128 v9; // xmm1
  unsigned int v10; // r11d
  unsigned __int128 v11; // xmm1
  unsigned __int128 v12; // xmm0
  unsigned int v13; // r11d
  int v14; // eax
  __int128 v15; // xmm0
  __int64 v16; // rax
  _BYTE v18[368]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v19; // [rsp+190h] [rbp+90h] BYREF
  int v20; // [rsp+198h] [rbp+98h]
  unsigned __int128 v21; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int128 v22; // [rsp+1B0h] [rbp+B0h]
  __int128 v23; // [rsp+1C0h] [rbp+C0h]
  __int128 v24; // [rsp+1D0h] [rbp+D0h]
  __int128 v25; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v26; // [rsp+1F0h] [rbp+F0h]

  v19 = 0;
  v20 = 0;
  v25 = 0;
  v26 = 0;
  memset(v18, 0, 0x163u);
  v21 = __PAIR128__(a2, (unsigned __int64)a1);
  *((_QWORD *)&v22 + 1) = qword_18000B410;
  *(_QWORD *)&v23 = &v19;
  *(_QWORD *)&v22 = a3;
  *((_QWORD *)&v23 + 1) = &v25;
  GetMSIPresults((__int64)&v21, (__int64)v18, v8);
  DWORD2(v23) = v20;
  *(_OWORD *)a4 = 0;
  *(_OWORD *)(a4 + 16) = 0;
  v9 = a1[1];
  v21 = *a1;
  *(_QWORD *)&v23 = v19;
  v22 = v9;
  Swap4Byte(&v21, 44);
  *(_DWORD *)a4 = HashBytes(&v21, v10);
  v11 = *a3;
  *(_QWORD *)&v21 = 0;
  v12 = a3[1];
  v21 = v11;
  v22 = v12;
  v23 = v25;
  v24 = v26;
  Swap4Byte(&v21, 64);
  v14 = HashBytes(&v21, v13);
  v15 = v25;
  *(_DWORD *)(a4 + 4) = v14;
  v16 = v19;
  *(_OWORD *)(a4 + 16) = v15;
  *(_QWORD *)(a4 + 8) = v16;
  return Swap4Byte(a4, 8);
}

```

## disassembly

```asm
0x180005020  push    rbp
0x180005022  push    rbx
0x180005023  push    rsi
0x180005024  push    rdi
0x180005025  push    r14
0x180005027  lea     rbp, [rsp-110h]
0x18000502f  sub     rsp, 210h
0x180005036  mov     rax, cs:__security_cookie
0x18000503d  xor     rax, rsp
0x180005040  mov     [rbp+130h+var_30], rax
0x180005047  xor     eax, eax
0x180005049  xorps   xmm0, xmm0
0x18000504c  mov     rsi, r8
0x18000504f  mov     [rbp+130h+var_A0], rax
0x180005056  mov     rbx, rdx
0x180005059  mov     [rbp+130h+var_98], eax
0x18000505f  mov     rdi, rcx
0x180005062  xor     edx, edx; Val
0x180005064  mov     r8d, 163h; Size
0x18000506a  lea     rcx, [rsp+230h+var_210]; void *
0x18000506f  movups  [rbp+130h+var_50], xmm0
0x180005076  mov     r14, r9
0x180005079  movups  [rbp+130h+var_40], xmm0
0x180005080  call    memset
0x180005085  lea     rax, qword_18000B410
0x18000508c  mov     qword ptr [rbp+130h+var_90], rdi
0x180005093  mov     qword ptr [rbp+130h+var_80+8], rax
0x18000509a  lea     rdx, [rsp+230h+var_210]
0x18000509f  lea     rax, [rbp+130h+var_A0]
0x1800050a6  mov     qword ptr [rbp+130h+var_90+8], rbx
0x1800050ad  mov     qword ptr [rbp+130h+var_70], rax
0x1800050b4  lea     rcx, [rbp+130h+var_90]
0x1800050bb  lea     rax, [rbp+130h+var_50]
0x1800050c2  mov     qword ptr [rbp+130h+var_80], rsi
0x1800050c9  mov     qword ptr [rbp+130h+var_70+8], rax
0x1800050d0  call    GetMSIPresults
0x1800050d5  mov     eax, [rbp+130h+var_98]
0x1800050db  lea     rcx, [rbp+130h+var_90]
0x1800050e2  xorps   xmm2, xmm2
0x1800050e5  mov     dword ptr [rbp+130h+var_70+8], eax
0x1800050eb  movups  xmmword ptr [r14], xmm2
0x1800050ef  mov     r11d, 2Ch ; ','
0x1800050f5  movups  xmmword ptr [r14+10h], xmm2
0x1800050fa  mov     edx, r11d
0x1800050fd  movups  xmm0, xmmword ptr [rdi]
0x180005100  movups  xmm1, xmmword ptr [rdi+10h]
0x180005104  movaps  [rbp+130h+var_90], xmm0
0x18000510b  movsd   xmm0, [rbp+130h+var_A0]
0x180005113  movsd   qword ptr [rbp+130h+var_70], xmm0
0x18000511b  movaps  [rbp+130h+var_80], xmm1
0x180005122  call    Swap4Byte
0x180005127  mov     edx, r11d
0x18000512a  lea     rcx, [rbp+130h+var_90]
0x180005131  call    HashBytes
0x180005136  mov     [r14], eax
0x180005139  lea     rcx, [rbp+130h+var_90]
0x180005140  movups  xmm1, xmmword ptr [rsi]
0x180005143  mov     qword ptr [rbp+130h+var_90], 0
0x18000514e  mov     r11d, 40h ; '@'
0x180005154  movups  xmm0, xmmword ptr [rsi+10h]
0x180005158  mov     qword ptr [rbp+130h+var_90+8], 0
0x180005163  mov     edx, r11d
0x180005166  movaps  [rbp+130h+var_90], xmm1
0x18000516d  movups  xmm1, [rbp+130h+var_50]
0x180005174  movaps  [rbp+130h+var_80], xmm0
0x18000517b  movups  xmm0, [rbp+130h+var_40]
0x180005182  movaps  [rbp+130h+var_70], xmm1
0x180005189  movaps  [rbp+130h+var_60], xmm0
0x180005190  call    Swap4Byte
0x180005195  mov     edx, r11d
0x180005198  lea     rcx, [rbp+130h+var_90]
0x18000519f  call    HashBytes
0x1800051a4  movups  xmm0, [rbp+130h+var_50]
0x1800051ab  mov     [r14+4], eax
0x1800051af  mov     edx, 8
0x1800051b4  mov     rax, [rbp+130h+var_A0]
0x1800051bb  mov     rcx, r14
0x1800051be  movdqu  xmmword ptr [r14+10h], xmm0
0x1800051c4  mov     [r14+8], rax
0x1800051c8  call    Swap4Byte
0x1800051cd  mov     rcx, [rbp+130h+var_30]
0x1800051d4  xor     rcx, rsp; StackCookie
0x1800051d7  call    __security_check_cookie
0x1800051dc  add     rsp, 210h
0x1800051e3  pop     r14
0x1800051e5  pop     rdi
0x1800051e6  pop     rsi
0x1800051e7  pop     rbx
0x1800051e8  pop     rbp
0x1800051e9  retn
```
