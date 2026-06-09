# _handle_error

- ea: `0x180077b00`
- end: `0x180077c80`
- name: `_handle_error`
- size: `384`
- prototype: ``
- caller_count: `22`
- callee_count: `7`
- tags: ``

## callers

- `0x18006cf00`
- `0x18006d2c0`
- `0x18006d700`
- `0x18006eb70`
- `0x18006edb0`
- `0x18006f310`
- `0x18006f840`
- `0x18006fab0`
- `0x180070970`
- `0x180070b70`
- `0x180070f10`
- `0x180071ef0`
- `0x1800726e0`
- `0x180072e50`
- `0x180073040`
- `0x180073ca0`
- `0x180073fb0`
- `0x180075d00`
- `0x180076550`
- `0x180076750`
- `0x1800772a0`
- `0x180079280`

## callees

- `0x1800779b0`
- `0x180077a30`
- `0x180077b00`
- `0x180078510`
- `0x180078870`
- `0x180078a30`
- `0x180079760`

## pseudocode

```c
double __fastcall handle_error(
        int a1,
        int a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        __int64 a7,
        __int64 a8,
        int a9)
{
  int v13; // eax
  int v14; // r9d
  __int64 v15; // xmm6_8
  double result; // xmm0_8
  double v17; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+48h] [rbp-C0h] BYREF
  _OWORD v19[3]; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v20; // [rsp+80h] [rbp-88h]
  __int128 v21; // [rsp+90h] [rbp-78h]
  __int128 v22; // [rsp+A0h] [rbp-68h]
  __int128 v23; // [rsp+B0h] [rbp-58h]

  v18 = ctrlfp(8064, 65472);
  v17 = *(double *)&a3;
  v13 = exception_enabled(a5, v18);
  v15 = a8;
  if ( !v13 )
  {
    memset(v19, 0, sizeof(v19));
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    if ( a9 == 2 )
    {
      *(_QWORD *)&v20 = a8;
      LODWORD(v21) = 3;
    }
    raise_exc((unsigned int)v19, (unsigned int)&v18, a5, a2, (__int64)&a7, (__int64)&v17);
  }
  if ( matherr_flag || !a4 )
  {
    set_errno_from_matherr(a4);
    ctrlfp(v18, 65472);
    return v17;
  }
  else
  {
    result = v17;
    call_matherr(a4, a6, a1, v14, v15, *(__int64 *)&v17, v18);
  }
  return result;
}

```

## disassembly

```asm
0x180077b00  push    rbx
0x180077b02  push    rbp
0x180077b03  push    rsi
0x180077b04  push    rdi
0x180077b05  sub     rsp, 0E8h
0x180077b0c  movaps  [rsp+108h+var_38], xmm6
0x180077b14  mov     rax, cs:__security_cookie
0x180077b1b  xor     rax, rsp
0x180077b1e  mov     [rsp+108h+var_48], rax
0x180077b26  mov     esi, edx
0x180077b28  mov     rbp, rcx
0x180077b2b  xorps   xmm0, xmm0
0x180077b2e  mov     edx, 0FFC0h
0x180077b33  mov     ecx, 1F80h
0x180077b38  movsd   qword ptr [rsp+108h+var_C8], xmm0
0x180077b3e  mov     edi, r9d
0x180077b41  mov     rbx, r8
0x180077b44  call    _ctrlfp
0x180077b49  mov     qword ptr [rsp+108h+var_C8+8], rax
0x180077b4e  mov     qword ptr [rsp+108h+var_C8], rbx
0x180077b53  movsd   xmm0, qword ptr [rsp+108h+var_C8]
0x180077b59  mov     ebx, [rsp+108h+arg_20]
0x180077b60  mov     ecx, ebx
0x180077b62  mov     rdx, qword ptr [rsp+108h+var_C8+8]
0x180077b67  movsd   qword ptr [rsp+108h+var_C8], xmm0
0x180077b6d  call    _exception_enabled
0x180077b72  movsd   xmm6, [rsp+108h+arg_38]
0x180077b7b  test    eax, eax
0x180077b7d  jnz     short loc_180077BFB
0x180077b7f  cmp     [rsp+108h+arg_40], 2
0x180077b87  xorps   xmm0, xmm0
0x180077b8a  movups  [rsp+108h+var_B8], xmm0
0x180077b8f  movups  [rsp+108h+var_A8], xmm0
0x180077b94  movups  [rsp+108h+var_98], xmm0
0x180077b99  movups  [rsp+108h+var_88], xmm0
0x180077ba1  movups  [rsp+108h+var_78], xmm0
0x180077ba9  movups  [rsp+108h+var_68], xmm0
0x180077bb1  movups  [rsp+108h+var_58], xmm0
0x180077bb9  jnz     short loc_180077BCF
0x180077bbb  movsd   qword ptr [rsp+108h+var_88], xmm6
0x180077bc4  mov     dword ptr [rsp+108h+var_78], 3
0x180077bcf  lea     rax, [rsp+108h+var_C8]
0x180077bd4  mov     r9d, esi
0x180077bd7  mov     qword ptr [rsp+108h+var_E0], rax
0x180077bdc  lea     rdx, [rsp+108h+var_C8+8]
0x180077be1  lea     rax, [rsp+108h+arg_30]
0x180077be9  mov     r8d, ebx
0x180077bec  lea     rcx, [rsp+108h+var_B8]
0x180077bf1  mov     [rsp+108h+var_E8], rax
0x180077bf6  call    _raise_exc
0x180077bfb  cmp     cs:_matherr_flag, 0
0x180077c02  jnz     short loc_180077C40
0x180077c04  test    edi, edi
0x180077c06  jz      short loc_180077C40
0x180077c08  mov     rax, qword ptr [rsp+108h+var_C8+8]
0x180077c0d  mov     r8, rbp
0x180077c10  movsd   xmm0, qword ptr [rsp+108h+var_C8]
0x180077c16  mov     ecx, edi
0x180077c18  movsd   xmm3, [rsp+108h+arg_30]
0x180077c21  mov     edx, [rsp+108h+arg_28]
0x180077c28  mov     qword ptr [rsp+108h+var_E0+8], rax
0x180077c2d  movsd   qword ptr [rsp+108h+var_E0], xmm0
0x180077c33  movsd   [rsp+108h+var_E8], xmm6
0x180077c39  call    _call_matherr
0x180077c3e  jmp     short loc_180077C5C
0x180077c40  mov     ecx, edi
0x180077c42  call    _set_errno_from_matherr
0x180077c47  mov     rcx, qword ptr [rsp+108h+var_C8+8]
0x180077c4c  mov     edx, 0FFC0h
0x180077c51  call    _ctrlfp
0x180077c56  movsd   xmm0, qword ptr [rsp+108h+var_C8]
0x180077c5c  mov     rcx, [rsp+108h+var_48]
0x180077c64  xor     rcx, rsp; StackCookie
0x180077c67  call    __security_check_cookie
0x180077c6c  movaps  xmm6, [rsp+108h+var_38]
0x180077c74  add     rsp, 0E8h
0x180077c7b  pop     rdi
0x180077c7c  pop     rsi
0x180077c7d  pop     rbp
0x180077c7e  pop     rbx
0x180077c7f  retn
```
