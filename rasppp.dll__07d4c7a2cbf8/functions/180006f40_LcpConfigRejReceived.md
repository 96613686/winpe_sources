# LcpConfigRejReceived

- ea: `0x180006f40`
- end: `0x18000704e`
- name: `LcpConfigRejReceived`
- size: `270`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180001460`
- `0x180006f40`
- `0x1800081cc`
- `0x180032454`

## pseudocode

```c
__int64 __fastcall LcpConfigRejReceived(__int64 a1, unsigned __int8 *a2)
{
  unsigned __int8 *v2; // rbx
  unsigned int v4; // ecx
  int v5; // ebp
  int v6; // eax
  __int64 v7; // rdx
  int v8; // eax
  __int64 result; // rax
  _BYTE Buf1[1504]; // [rsp+20h] [rbp-608h] BYREF

  v2 = a2 + 4;
  v4 = 0;
  v5 = (a2[2] << 8) + a2[3] - 4;
  while ( (unsigned int)v5 >= 2 )
  {
    v6 = v2[1];
    if ( !(_BYTE)v6 )
      return 722;
    v5 -= v6;
    if ( v5 < 0 )
      return 722;
    v7 = *v2;
    if ( (unsigned __int8)v7 <= 0x17u )
    {
      if ( (unsigned int)v7 < v4 )
        return 722;
      v8 = *(_DWORD *)(a1 + 1208);
      if ( !_bittest(&v8, v7) )
        return 722;
    }
    if ( (*(_BYTE *)(a1 + 1120) & 8) != 0 && (_BYTE)v7 == 3 && (*(_DWORD *)(a1 + 24) & 0x4000) == 0 )
      return 919;
    result = MakeOption(a1 + 1208, v7, Buf1, 1500);
    if ( (_DWORD)result )
      return result;
    if ( memcmp_0(Buf1, v2, v2[1]) )
      return 722;
    v4 = *v2;
    if ( (unsigned __int8)v4 <= 0x17u )
      *(_DWORD *)(a1 + 1208) &= ~(1 << v4);
    v2 += v2[1];
  }
  return 0;
}

```

## disassembly

```asm
0x180006f40  mov     [rsp+arg_10], rbx
0x180006f45  push    rbp
0x180006f46  push    rsi
0x180006f47  push    rdi
0x180006f48  sub     rsp, 610h
0x180006f4f  mov     rax, cs:__security_cookie
0x180006f56  xor     rax, rsp
0x180006f59  mov     [rsp+628h+var_28], rax
0x180006f61  movzx   r8d, byte ptr [rdx+2]
0x180006f66  lea     rbx, [rdx+4]
0x180006f6a  movzx   ebp, byte ptr [rdx+3]
0x180006f6e  mov     rsi, rcx
0x180006f71  xor     ecx, ecx
0x180006f73  shl     r8d, 8
0x180006f77  add     ebp, 0FFFFFFFCh
0x180006f7a  add     ebp, r8d
0x180006f7d  lea     rdi, [rsi+4B8h]
0x180006f84  cmp     ebp, 2
0x180006f87  jb      loc_180007029
0x180006f8d  movzx   eax, byte ptr [rbx+1]
0x180006f91  test    al, al
0x180006f93  jz      loc_180007022
0x180006f99  sub     ebp, eax
0x180006f9b  js      loc_180007022
0x180006fa1  movzx   edx, byte ptr [rbx]
0x180006fa4  cmp     dl, 17h
0x180006fa7  ja      short loc_180006FB8
0x180006fa9  cmp     edx, ecx
0x180006fab  jb      short loc_180007022
0x180006fad  mov     eax, [rsi+4B8h]
0x180006fb3  bt      eax, edx
0x180006fb6  jnb     short loc_180007022
0x180006fb8  test    byte ptr [rsi+460h], 8
0x180006fbf  jz      short loc_180006FCF
0x180006fc1  cmp     dl, 3
0x180006fc4  jnz     short loc_180006FCF
0x180006fc6  test    dword ptr [rsi+18h], 4000h
0x180006fcd  jz      short loc_18000701B
0x180006fcf  mov     r9d, 5DCh
0x180006fd5  lea     r8, [rsp+628h+Buf1]
0x180006fda  mov     rcx, rdi
0x180006fdd  call    MakeOption
0x180006fe2  test    eax, eax
0x180006fe4  jnz     short loc_18000702B
0x180006fe6  movzx   r8d, byte ptr [rbx+1]; Size
0x180006feb  lea     rcx, [rsp+628h+Buf1]; Buf1
0x180006ff0  mov     rdx, rbx; Buf2
0x180006ff3  call    memcmp_0
0x180006ff8  test    eax, eax
0x180006ffa  jnz     short loc_180007022
0x180006ffc  movzx   ecx, byte ptr [rbx]
0x180006fff  cmp     cl, 17h
0x180007002  ja      short loc_18000700F
0x180007004  mov     eax, 1
0x180007009  shl     eax, cl
0x18000700b  not     eax
0x18000700d  and     [rdi], eax
0x18000700f  movzx   eax, byte ptr [rbx+1]
0x180007013  add     rbx, rax
0x180007016  jmp     loc_180006F84
0x18000701b  mov     eax, 397h
0x180007020  jmp     short loc_18000702B
0x180007022  mov     eax, 2D2h
0x180007027  jmp     short loc_18000702B
0x180007029  xor     eax, eax
0x18000702b  mov     rcx, [rsp+628h+var_28]
0x180007033  xor     rcx, rsp; StackCookie
0x180007036  call    __security_check_cookie
0x18000703b  mov     rbx, [rsp+628h+arg_10]
0x180007043  add     rsp, 610h
0x18000704a  pop     rdi
0x18000704b  pop     rsi
0x18000704c  pop     rbp
0x18000704d  retn
```
