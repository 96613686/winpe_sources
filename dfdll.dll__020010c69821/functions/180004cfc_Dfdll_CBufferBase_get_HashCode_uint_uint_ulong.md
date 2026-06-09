# Dfdll::CBufferBase::get_HashCode(uint,uint,ulong &)

- ea: `0x180004cfc`
- end: `0x180004e0c`
- name: `?get_HashCode@CBufferBase@Dfdll@@QEAAJIIAEAK@Z`
- size: `272`
- prototype: `__int64 __fastcall(Dfdll::CBufferBase *__hidden this, unsigned int, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180004e10`

## callees

- `0x180004cfc`
- `0x180012bd0`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall Dfdll::CBufferBase::get_HashCode(
        Dfdll::CBufferBase *this,
        unsigned int a2,
        unsigned int a3,
        unsigned int *a4)
{
  __int64 result; // rax
  unsigned int v8; // r8d
  unsigned int v9; // ebp
  unsigned int v10; // ebx
  __int64 v11; // rax
  unsigned __int8 *v12; // r9
  unsigned int v13; // r8d
  __int64 v14; // r10
  __int64 v15; // r11
  int v16; // eax
  int *v17; // rcx
  __int64 v18; // rdx
  int v19; // eax
  unsigned __int8 *v20; // [rsp+20h] [rbp-48h] BYREF
  __int128 v21; // [rsp+28h] [rbp-40h] BYREF

  if ( a2 > a3 || a3 >= *((_DWORD *)this + 4) )
    return 2147942487LL;
  v8 = a3 - a2;
  if ( v8 == -1 )
    return 2147942934LL;
  v9 = v8 + 1;
  v10 = (*(__int64 (__fastcall **)(Dfdll::CBufferBase *))(*(_QWORD *)this + 72LL))(this);
  if ( v10 )
  {
    if ( v9 > 0xFFFFFFFF / v10 )
      return 2147942934LL;
    v10 *= v9;
  }
  v11 = *(_QWORD *)this;
  v20 = 0;
  result = (*(__int64 (__fastcall **)(Dfdll::CBufferBase *, _QWORD, unsigned __int8 **))(v11 + 64))(this, a2, &v20);
  if ( (int)result >= 0 )
  {
    v12 = v20;
    v13 = 0;
    if ( v20 )
    {
      v14 = 0;
      v21 = 0;
      if ( v10 )
      {
        v15 = v10;
        do
        {
          v16 = *v12++;
          *((_DWORD *)&v21 + v14) = v16 + 65599 * *((_DWORD *)&v21 + v14);
          v14 = ((_BYTE)v14 + 1) & 3;
          --v15;
        }
        while ( v15 );
      }
      v17 = (int *)&v21;
      v18 = 4;
      do
      {
        v19 = *v17++;
        v13 = v19 + 65599 * v13;
        --v18;
      }
      while ( v18 );
    }
    *a4 = v13;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004cfc  push    rbx
0x180004cfe  push    rbp
0x180004cff  push    rsi
0x180004d00  push    rdi
0x180004d01  push    r14
0x180004d03  sub     rsp, 40h
0x180004d07  mov     rax, cs:__security_cookie
0x180004d0e  xor     rax, rsp
0x180004d11  mov     [rsp+68h+var_30], rax
0x180004d16  mov     r14, r9
0x180004d19  mov     esi, edx
0x180004d1b  mov     rdi, rcx
0x180004d1e  cmp     edx, r8d
0x180004d21  jbe     short loc_180004D2D
0x180004d23  mov     eax, 80070057h
0x180004d28  jmp     loc_180004DF4
0x180004d2d  cmp     r8d, [rcx+10h]
0x180004d31  jnb     short loc_180004D23
0x180004d33  sub     r8d, esi
0x180004d36  cmp     r8d, 0FFFFFFFEh
0x180004d3a  jbe     short loc_180004D46
0x180004d3c  mov     eax, 80070216h
0x180004d41  jmp     loc_180004DF4
0x180004d46  lea     ebp, [r8+1]
0x180004d4a  mov     rax, [rcx]
0x180004d4d  mov     rax, [rax+48h]
0x180004d51  call    cs:__guard_dispatch_icall_fptr
0x180004d57  mov     ebx, eax
0x180004d59  test    eax, eax
0x180004d5b  jz      short loc_180004D6B
0x180004d5d  xor     edx, edx
0x180004d5f  or      eax, 0FFFFFFFFh
0x180004d62  div     ebx
0x180004d64  cmp     ebp, eax
0x180004d66  ja      short loc_180004D3C
0x180004d68  imul    ebx, ebp
0x180004d6b  mov     rax, [rdi]
0x180004d6e  lea     r8, [rsp+68h+var_48]
0x180004d73  and     [rsp+68h+var_48], 0
0x180004d79  mov     edx, esi
0x180004d7b  mov     rcx, rdi
0x180004d7e  mov     rax, [rax+40h]
0x180004d82  call    cs:__guard_dispatch_icall_fptr
0x180004d88  test    eax, eax
0x180004d8a  js      short loc_180004DF4
0x180004d8c  mov     r9, [rsp+68h+var_48]
0x180004d91  xor     r8d, r8d
0x180004d94  test    r9, r9
0x180004d97  jz      short loc_180004DEF
0x180004d99  xor     r10d, r10d
0x180004d9c  xorps   xmm0, xmm0
0x180004d9f  movups  [rsp+68h+var_40], xmm0
0x180004da4  test    ebx, ebx
0x180004da6  jz      short loc_180004DCF
0x180004da8  mov     r11d, ebx
0x180004dab  imul    ecx, dword ptr [rsp+r10*4+68h+var_40], 1003Fh
0x180004db4  movzx   eax, byte ptr [r9]
0x180004db8  inc     r9
0x180004dbb  add     ecx, eax
0x180004dbd  mov     dword ptr [rsp+r10*4+68h+var_40], ecx
0x180004dc2  inc     r10d
0x180004dc5  and     r10d, 3
0x180004dc9  sub     r11, 1
0x180004dcd  jnz     short loc_180004DAB
0x180004dcf  lea     rcx, [rsp+68h+var_40]
0x180004dd4  mov     edx, 4
0x180004dd9  mov     eax, [rcx]
0x180004ddb  lea     rcx, [rcx+4]
0x180004ddf  imul    r8, 1003Fh
0x180004de6  add     r8, rax
0x180004de9  sub     rdx, 1
0x180004ded  jnz     short loc_180004DD9
0x180004def  mov     [r14], r8d
0x180004df2  xor     eax, eax
0x180004df4  mov     rcx, [rsp+68h+var_30]
0x180004df9  xor     rcx, rsp; StackCookie
0x180004dfc  call    __security_check_cookie
0x180004e01  add     rsp, 40h
0x180004e05  pop     r14
0x180004e07  pop     rdi
0x180004e08  pop     rsi
0x180004e09  pop     rbp
0x180004e0a  pop     rbx
0x180004e0b  retn
```
