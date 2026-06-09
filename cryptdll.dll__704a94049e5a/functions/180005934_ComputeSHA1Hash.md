# ComputeSHA1Hash

- ea: `0x180005934`
- end: `0x180005a2b`
- name: `ComputeSHA1Hash`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800060a0`

## callees

- `0x1800030d0`
- `0x180004c40`
- `0x180005934`
- `0x180009010`

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
  v11 = 0;
  v13 = 0;
  v14 = 0;
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
0x180005934  mov     [rsp-28h+arg_18], rbx
0x180005939  push    rbp
0x18000593a  push    rsi
0x18000593b  push    rdi
0x18000593c  push    r14
0x18000593e  push    r15
0x180005940  mov     rbp, rsp
0x180005943  sub     rsp, 60h
0x180005947  mov     rax, cs:__security_cookie
0x18000594e  xor     rax, rsp
0x180005951  mov     [rbp+var_8], rax
0x180005955  mov     r15d, edx
0x180005958  mov     [rbp+var_28], 0
0x180005960  mov     r14, rcx
0x180005963  mov     [rbp+var_30], 0
0x18000596b  xorps   xmm0, xmm0
0x18000596e  lea     rdx, [rbp+var_28]
0x180005972  xor     eax, eax
0x180005974  mov     ecx, 0FFFFFF7Dh
0x180005979  movups  [rbp+var_20], xmm0
0x18000597d  mov     [rbp+var_10], eax
0x180005980  mov     rsi, r8
0x180005983  call    CDLocateCheckSum
0x180005988  mov     ebx, eax
0x18000598a  test    eax, eax
0x18000598c  js      short loc_180005A09
0x18000598e  mov     rdi, [rbp+var_28]
0x180005992  mov     rax, [rdi+30h]
0x180005996  test    rax, rax
0x180005999  jz      short loc_1800059F0
0x18000599b  lea     r9, [rbp+var_30]
0x18000599f  xor     r8d, r8d
0x1800059a2  xor     edx, edx
0x1800059a4  xor     ecx, ecx
0x1800059a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059ab  mov     ebx, eax
0x1800059ad  test    eax, eax
0x1800059af  js      short loc_1800059F5
0x1800059b1  mov     rcx, [rbp+var_30]
0x1800059b5  mov     r8, r14
0x1800059b8  mov     rax, [rdi+18h]
0x1800059bc  mov     edx, r15d
0x1800059bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059c4  mov     ebx, eax
0x1800059c6  test    eax, eax
0x1800059c8  js      short loc_1800059F5
0x1800059ca  mov     rcx, [rbp+var_30]
0x1800059ce  lea     rdx, [rbp+var_20]
0x1800059d2  mov     rax, [rdi+20h]
0x1800059d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059db  mov     ebx, eax
0x1800059dd  test    eax, eax
0x1800059df  js      short loc_1800059F5
0x1800059e1  movups  xmm0, [rbp+var_20]
0x1800059e5  mov     eax, [rbp+var_10]
0x1800059e8  movups  xmmword ptr [rsi], xmm0
0x1800059eb  mov     [rsi+10h], eax
0x1800059ee  jmp     short loc_1800059F5
0x1800059f0  mov     ebx, 0C00000BBh
0x1800059f5  cmp     [rbp+var_30], 0
0x1800059fa  jz      short loc_180005A09
0x1800059fc  mov     rax, [rdi+28h]
0x180005a00  lea     rcx, [rbp+var_30]
0x180005a04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a09  mov     eax, ebx
0x180005a0b  mov     rcx, [rbp+var_8]
0x180005a0f  xor     rcx, rsp; StackCookie
0x180005a12  call    __security_check_cookie
0x180005a17  mov     rbx, [rsp+60h+arg_18]
0x180005a1f  add     rsp, 60h
0x180005a23  pop     r15
0x180005a25  pop     r14
0x180005a27  pop     rdi
0x180005a28  pop     rsi
0x180005a29  pop     rbp
0x180005a2a  retn
```
