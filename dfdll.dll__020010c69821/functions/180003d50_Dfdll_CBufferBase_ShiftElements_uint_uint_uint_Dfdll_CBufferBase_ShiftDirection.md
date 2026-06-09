# Dfdll::CBufferBase::ShiftElements(uint,uint,uint,Dfdll::CBufferBase::ShiftDirection)

- ea: `0x180003d50`
- end: `0x180003e5f`
- name: `?ShiftElements@CBufferBase@Dfdll@@UEAAJIIIW4ShiftDirection@12@@Z`
- size: `271`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180003d50`
- `0x1800140a0`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall Dfdll::CBufferBase::ShiftElements(_DWORD *a1, __int64 a2, unsigned int a3, unsigned int a4, int a5)
{
  __int64 result; // rax
  unsigned int v7; // ebx
  unsigned int v8; // edi
  __int64 v9; // rax
  __int64 v10; // rax
  unsigned int v11; // ecx
  void *Src; // [rsp+20h] [rbp-18h] BYREF
  void *v13; // [rsp+28h] [rbp-10h] BYREF

  if ( (unsigned int)a2 > a3 || a3 >= a1[4] )
    return 2147942487LL;
  if ( a3 - (_DWORD)a2 == -1 )
    return 2147942934LL;
  v7 = a3 - a2 + 1;
  if ( a5 != 1 )
  {
    if ( a5 == 2 )
    {
      if ( a3 > ~a4 )
        return 2147942934LL;
      if ( a3 + a4 < a1[4] )
      {
        if ( (unsigned int)a2 > ~a4 )
          return 2147942934LL;
        v8 = a2 + a4;
        goto LABEL_13;
      }
    }
    return 2147942487LL;
  }
  if ( (unsigned int)a2 < a4 )
    return 2147942487LL;
  v8 = a2 - a4;
LABEL_13:
  v9 = *(_QWORD *)a1;
  Src = 0;
  result = (*(__int64 (__fastcall **)(_DWORD *, __int64, void **))(v9 + 64))(a1, a2, &Src);
  if ( (int)result >= 0 )
  {
    v10 = *(_QWORD *)a1;
    v13 = 0;
    result = (*(__int64 (__fastcall **)(_DWORD *, _QWORD, void **))(v10 + 64))(a1, v8, &v13);
    if ( (int)result >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)a1 + 72LL))(a1);
      if ( v11 )
      {
        if ( v7 > 0xFFFFFFFF / v11 )
          return 2147942934LL;
        v11 *= v7;
      }
      memmove(v13, Src, v11);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003d50  mov     [rsp+arg_0], rbx
0x180003d55  mov     [rsp+arg_8], rsi
0x180003d5a  push    rdi
0x180003d5b  sub     rsp, 30h
0x180003d5f  mov     rsi, rcx
0x180003d62  cmp     edx, r8d
0x180003d65  ja      loc_180003E4A
0x180003d6b  cmp     r8d, [rcx+10h]
0x180003d6f  jnb     loc_180003E4A
0x180003d75  mov     ebx, r8d
0x180003d78  sub     ebx, edx
0x180003d7a  cmp     ebx, 0FFFFFFFEh
0x180003d7d  jbe     short loc_180003D89
0x180003d7f  mov     eax, 80070216h
0x180003d84  jmp     loc_180003E4F
0x180003d89  inc     ebx
0x180003d8b  cmp     [rsp+38h+arg_20], 1
0x180003d90  jnz     short loc_180003DA2
0x180003d92  cmp     edx, r9d
0x180003d95  jb      loc_180003E4A
0x180003d9b  mov     edi, edx
0x180003d9d  sub     edi, r9d
0x180003da0  jmp     short loc_180003DCC
0x180003da2  cmp     [rsp+38h+arg_20], 2
0x180003da7  jnz     loc_180003E4A
0x180003dad  mov     ecx, r9d
0x180003db0  not     ecx
0x180003db2  cmp     r8d, ecx
0x180003db5  ja      short loc_180003D7F
0x180003db7  lea     eax, [r8+r9]
0x180003dbb  cmp     eax, [rsi+10h]
0x180003dbe  jnb     loc_180003E4A
0x180003dc4  cmp     edx, ecx
0x180003dc6  ja      short loc_180003D7F
0x180003dc8  lea     edi, [rdx+r9]
0x180003dcc  mov     rax, [rsi]
0x180003dcf  lea     r8, [rsp+38h+Src]
0x180003dd4  and     [rsp+38h+Src], 0
0x180003dda  mov     rcx, rsi
0x180003ddd  mov     rax, [rax+40h]
0x180003de1  call    cs:__guard_dispatch_icall_fptr
0x180003de7  test    eax, eax
0x180003de9  js      short loc_180003E4F
0x180003deb  mov     rax, [rsi]
0x180003dee  lea     r8, [rsp+38h+var_10]
0x180003df3  and     [rsp+38h+var_10], 0
0x180003df9  mov     edx, edi
0x180003dfb  mov     rcx, rsi
0x180003dfe  mov     rax, [rax+40h]
0x180003e02  call    cs:__guard_dispatch_icall_fptr
0x180003e08  test    eax, eax
0x180003e0a  js      short loc_180003E4F
0x180003e0c  mov     rax, [rsi]
0x180003e0f  mov     rcx, rsi
0x180003e12  mov     rax, [rax+48h]
0x180003e16  call    cs:__guard_dispatch_icall_fptr
0x180003e1c  mov     ecx, eax
0x180003e1e  test    eax, eax
0x180003e20  jz      short loc_180003E34
0x180003e22  xor     edx, edx
0x180003e24  or      eax, 0FFFFFFFFh
0x180003e27  div     ecx
0x180003e29  cmp     ebx, eax
0x180003e2b  ja      loc_180003D7F
0x180003e31  imul    ecx, ebx
0x180003e34  mov     rdx, [rsp+38h+Src]; Src
0x180003e39  mov     r8d, ecx; Size
0x180003e3c  mov     rcx, [rsp+38h+var_10]; void *
0x180003e41  call    memmove
0x180003e46  xor     eax, eax
0x180003e48  jmp     short loc_180003E4F
0x180003e4a  mov     eax, 80070057h
0x180003e4f  mov     rbx, [rsp+38h+arg_0]
0x180003e54  mov     rsi, [rsp+38h+arg_8]
0x180003e59  add     rsp, 30h
0x180003e5d  pop     rdi
0x180003e5e  retn
```
