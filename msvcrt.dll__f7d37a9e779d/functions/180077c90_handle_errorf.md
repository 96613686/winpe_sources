# _handle_errorf

- ea: `0x180077c90`
- end: `0x180077e1b`
- name: `_handle_errorf`
- size: `395`
- prototype: ``
- caller_count: `22`
- callee_count: `7`
- tags: ``

## callers

- `0x18006d100`
- `0x18006d4f0`
- `0x18006d980`
- `0x18006ecb0`
- `0x18006f080`
- `0x18006f5d0`
- `0x180070240`
- `0x180070710`
- `0x180070a90`
- `0x1800715b0`
- `0x180071a30`
- `0x180072340`
- `0x180072a60`
- `0x180072f60`
- `0x180073600`
- `0x180074320`
- `0x180074550`
- `0x1800761a0`
- `0x180076660`
- `0x180076ef0`
- `0x180077630`
- `0x1800793c0`

## callees

- `0x1800779b0`
- `0x180077a30`
- `0x180077c90`
- `0x180078840`
- `0x180078870`
- `0x180078a30`
- `0x180079760`

## pseudocode

```c
float __fastcall handle_errorf(
        int a1,
        int a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        int a7,
        float a8,
        int a9)
{
  int v13; // eax
  int v14; // r9d
  float v15; // xmm6_4
  float v17; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+48h] [rbp-C0h] BYREF
  _OWORD v19[3]; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v20; // [rsp+80h] [rbp-88h]
  __int128 v21; // [rsp+90h] [rbp-78h]
  __int128 v22; // [rsp+A0h] [rbp-68h]
  __int128 v23; // [rsp+B0h] [rbp-58h]

  v18 = ctrlfp(8064, 65472);
  v17 = *(float *)&a3;
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
      *(float *)&v20 = a8;
      LODWORD(v21) = 1;
    }
    raise_excf((unsigned int)v19, (unsigned int)&v18, a5, a2, (__int64)&a7, (__int64)&v17);
  }
  if ( !matherr_flag && a4 )
    return call_matherr(a4, a6, a1, v14, COERCE__INT64(v15), COERCE__INT64(v17), v18);
  set_errno_from_matherr(a4);
  ctrlfp(v18, 65472);
  return v17;
}

```

## disassembly

```asm
0x180077c90  push    rbx
0x180077c92  push    rbp
0x180077c93  push    rsi
0x180077c94  push    rdi
0x180077c95  sub     rsp, 0E8h
0x180077c9c  movaps  [rsp+108h+var_38], xmm6
0x180077ca4  mov     rax, cs:__security_cookie
0x180077cab  xor     rax, rsp
0x180077cae  mov     [rsp+108h+var_48], rax
0x180077cb6  mov     esi, edx
0x180077cb8  mov     [rsp+108h+var_C8], 0
0x180077cc0  mov     rbp, rcx
0x180077cc3  mov     edx, 0FFC0h
0x180077cc8  mov     ecx, 1F80h
0x180077ccd  mov     edi, r9d
0x180077cd0  mov     rbx, r8
0x180077cd3  call    _ctrlfp
0x180077cd8  mov     [rsp+108h+var_C0], rax
0x180077cdd  mov     [rsp+108h+var_C8], ebx
0x180077ce1  movss   xmm0, [rsp+108h+var_C8]
0x180077ce7  mov     ebx, [rsp+108h+arg_20]
0x180077cee  mov     ecx, ebx
0x180077cf0  mov     rdx, [rsp+108h+var_C0]
0x180077cf5  movss   [rsp+108h+var_C8], xmm0
0x180077cfb  call    _exception_enabled
0x180077d00  movss   xmm6, [rsp+108h+arg_38]
0x180077d09  test    eax, eax
0x180077d0b  jnz     short loc_180077D89
0x180077d0d  cmp     [rsp+108h+arg_40], 2
0x180077d15  xorps   xmm0, xmm0
0x180077d18  movups  [rsp+108h+var_B8], xmm0
0x180077d1d  movups  [rsp+108h+var_A8], xmm0
0x180077d22  movups  [rsp+108h+var_98], xmm0
0x180077d27  movups  [rsp+108h+var_88], xmm0
0x180077d2f  movups  [rsp+108h+var_78], xmm0
0x180077d37  movups  [rsp+108h+var_68], xmm0
0x180077d3f  movups  [rsp+108h+var_58], xmm0
0x180077d47  jnz     short loc_180077D5D
0x180077d49  movss   dword ptr [rsp+108h+var_88], xmm6
0x180077d52  mov     dword ptr [rsp+108h+var_78], 1
0x180077d5d  lea     rax, [rsp+108h+var_C8]
0x180077d62  mov     r9d, esi
0x180077d65  mov     [rsp+108h+var_E0], rax
0x180077d6a  lea     rdx, [rsp+108h+var_C0]
0x180077d6f  lea     rax, [rsp+108h+arg_30]
0x180077d77  mov     r8d, ebx
0x180077d7a  lea     rcx, [rsp+108h+var_B8]
0x180077d7f  mov     [rsp+108h+var_E8], rax
0x180077d84  call    _raise_excf
0x180077d89  cmp     cs:_matherr_flag, 0
0x180077d90  jnz     short loc_180077DDB
0x180077d92  test    edi, edi
0x180077d94  jz      short loc_180077DDB
0x180077d96  movss   xmm0, [rsp+108h+var_C8]
0x180077d9c  mov     r8, rbp
0x180077d9f  movss   xmm3, [rsp+108h+arg_30]
0x180077da8  mov     ecx, edi
0x180077daa  mov     rax, [rsp+108h+var_C0]
0x180077daf  mov     edx, [rsp+108h+arg_28]
0x180077db6  mov     [rsp+108h+var_D8], rax
0x180077dbb  cvtps2pd xmm0, xmm0
0x180077dbe  cvtps2pd xmm1, xmm6
0x180077dc1  movsd   [rsp+108h+var_E0], xmm0
0x180077dc7  cvtps2pd xmm3, xmm3
0x180077dca  movsd   [rsp+108h+var_E8], xmm1
0x180077dd0  call    _call_matherr
0x180077dd5  cvtsd2ss xmm0, xmm0
0x180077dd9  jmp     short loc_180077DF7
0x180077ddb  mov     ecx, edi
0x180077ddd  call    _set_errno_from_matherr
0x180077de2  mov     rcx, [rsp+108h+var_C0]
0x180077de7  mov     edx, 0FFC0h
0x180077dec  call    _ctrlfp
0x180077df1  movss   xmm0, [rsp+108h+var_C8]
0x180077df7  mov     rcx, [rsp+108h+var_48]
0x180077dff  xor     rcx, rsp; StackCookie
0x180077e02  call    __security_check_cookie
0x180077e07  movaps  xmm6, [rsp+108h+var_38]
0x180077e0f  add     rsp, 0E8h
0x180077e16  pop     rdi
0x180077e17  pop     rsi
0x180077e18  pop     rbp
0x180077e19  pop     rbx
0x180077e1a  retn
```
