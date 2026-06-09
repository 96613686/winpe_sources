# ComputeSHA1Hash

- ea: `0x14000e55c`
- end: `0x14000e654`
- name: `ComputeSHA1Hash`
- size: `248`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002d740`

## callees

- `0x14000e55c`
- `0x140010160`
- `0x140010240`
- `0x1400261e0`

## pseudocode

```c
__int64 __fastcall ComputeSHA1Hash(__int64 a1, unsigned int a2, __int64 a3)
{
  int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(_QWORD, _QWORD, _QWORD, __int64 *); // rax
  int v9; // eax
  __int64 v11; // [rsp+30h] [rbp-30h] BYREF
  __int64 v12; // [rsp+38h] [rbp-28h] BYREF
  __int128 v13; // [rsp+40h] [rbp-20h] BYREF
  int v14; // [rsp+50h] [rbp-10h]

  v12 = 0;
  v14 = 0;
  v11 = 0;
  v13 = 0;
  v6 = CDLocateCheckSum(4294967165LL, &v12);
  if ( v6 >= 0 )
  {
    v7 = v12;
    v8 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))(v12 + 48);
    if ( v8 )
    {
      v6 = v8(0, 0, 0, &v11);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(v7 + 24))(v11, a2, a1);
        if ( v6 >= 0 )
        {
          v6 = (*(__int64 (__fastcall **)(__int64, __int128 *))(v7 + 32))(v11, &v13);
          if ( v6 >= 0 )
          {
            v9 = v14;
            *(_OWORD *)a3 = v13;
            *(_DWORD *)(a3 + 16) = v9;
          }
        }
      }
    }
    else
    {
      v6 = -1073741637;
    }
    if ( v11 )
      (*(void (__fastcall **)(__int64 *))(v7 + 40))(&v11);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000e55c  mov     [rsp-28h+arg_18], rbx
0x14000e561  push    rbp
0x14000e562  push    rsi
0x14000e563  push    rdi
0x14000e564  push    r14
0x14000e566  push    r15
0x14000e568  mov     rbp, rsp
0x14000e56b  sub     rsp, 60h
0x14000e56f  mov     rax, cs:__security_cookie
0x14000e576  xor     rax, rsp
0x14000e579  mov     [rbp+var_8], rax
0x14000e57d  xor     eax, eax
0x14000e57f  mov     [rbp+var_28], 0
0x14000e587  mov     r15d, edx
0x14000e58a  mov     [rbp+var_10], eax
0x14000e58d  mov     r14, rcx
0x14000e590  mov     [rbp+var_30], 0
0x14000e598  xorps   xmm0, xmm0
0x14000e59b  lea     rdx, [rbp+var_28]
0x14000e59f  mov     ecx, 0FFFFFF7Dh
0x14000e5a4  mov     rsi, r8
0x14000e5a7  movups  [rbp+var_20], xmm0
0x14000e5ab  call    CDLocateCheckSum
0x14000e5b0  mov     ebx, eax
0x14000e5b2  test    eax, eax
0x14000e5b4  js      short loc_14000E631
0x14000e5b6  mov     rdi, [rbp+var_28]
0x14000e5ba  mov     rax, [rdi+30h]
0x14000e5be  test    rax, rax
0x14000e5c1  jz      short loc_14000E618
0x14000e5c3  lea     r9, [rbp+var_30]
0x14000e5c7  xor     r8d, r8d
0x14000e5ca  xor     edx, edx
0x14000e5cc  xor     ecx, ecx
0x14000e5ce  call    _guard_dispatch_icall
0x14000e5d3  mov     ebx, eax
0x14000e5d5  test    eax, eax
0x14000e5d7  js      short loc_14000E61D
0x14000e5d9  mov     rax, [rdi+18h]
0x14000e5dd  mov     r8, r14
0x14000e5e0  mov     rcx, [rbp+var_30]
0x14000e5e4  mov     edx, r15d
0x14000e5e7  call    _guard_dispatch_icall
0x14000e5ec  mov     ebx, eax
0x14000e5ee  test    eax, eax
0x14000e5f0  js      short loc_14000E61D
0x14000e5f2  mov     rax, [rdi+20h]
0x14000e5f6  lea     rdx, [rbp+var_20]
0x14000e5fa  mov     rcx, [rbp+var_30]
0x14000e5fe  call    _guard_dispatch_icall
0x14000e603  mov     ebx, eax
0x14000e605  test    eax, eax
0x14000e607  js      short loc_14000E61D
0x14000e609  movups  xmm0, [rbp+var_20]
0x14000e60d  mov     eax, [rbp+var_10]
0x14000e610  movups  xmmword ptr [rsi], xmm0
0x14000e613  mov     [rsi+10h], eax
0x14000e616  jmp     short loc_14000E61D
0x14000e618  mov     ebx, 0C00000BBh
0x14000e61d  cmp     [rbp+var_30], 0
0x14000e622  jz      short loc_14000E631
0x14000e624  mov     rax, [rdi+28h]
0x14000e628  lea     rcx, [rbp+var_30]
0x14000e62c  call    _guard_dispatch_icall
0x14000e631  mov     eax, ebx
0x14000e633  mov     rcx, [rbp+var_8]
0x14000e637  xor     rcx, rsp; StackCookie
0x14000e63a  call    __security_check_cookie
0x14000e63f  mov     rbx, [rsp+60h+arg_18]
0x14000e647  add     rsp, 60h
0x14000e64b  pop     r15
0x14000e64d  pop     r14
0x14000e64f  pop     rdi
0x14000e650  pop     rsi
0x14000e651  pop     rbp
0x14000e652  retn
```
