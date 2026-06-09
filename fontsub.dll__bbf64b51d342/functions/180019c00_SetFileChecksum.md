# SetFileChecksum

- ea: `0x180019c00`
- end: `0x180019d21`
- name: `SetFileChecksum`
- size: `289`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180007fa4`
- `0x180009978`
- `0x18000c874`

## callees

- `0x180019c00`
- `0x180019e64`
- `0x18001a138`
- `0x18001a3bc`
- `0x18001a808`
- `0x18001ac90`

## pseudocode

```c
__int16 __fastcall SetFileChecksum(__int64 a1, unsigned int a2)
{
  unsigned int v4; // eax
  unsigned int v5; // edi
  _WORD v7[2]; // [rsp+30h] [rbp-50h] BYREF
  int v8; // [rsp+34h] [rbp-4Ch] BYREF
  _OWORD v9[3]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v10; // [rsp+68h] [rbp-18h]

  v8 = 0;
  memset(v9, 0, sizeof(v9));
  v10 = 0;
  v7[0] = 0;
  v4 = TTTableOffset(a1, "head");
  v5 = v4;
  if ( v4 )
  {
    LOWORD(v4) = ReadGeneric(a1, (__int64)v9, 0x36u, (unsigned __int8 *)HEAD_CONTROL, v4, v7);
    if ( !(_WORD)v4 )
    {
      DWORD2(v9[0]) = 0;
      LOWORD(v4) = WriteGeneric(a1, (__int64)v9, 0x36u, (unsigned __int8 *)HEAD_CONTROL, v5, v7);
      if ( !(_WORD)v4 )
      {
        LOWORD(v4) = CalcChecksum(a1, 0, a2, &v8);
        if ( !(_WORD)v4 )
        {
          DWORD2(v9[0]) = -1313820742 - v8;
          LOWORD(v4) = WriteGeneric(a1, (__int64)v9, 0x36u, (unsigned __int8 *)HEAD_CONTROL, v5, v7);
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180019c00  mov     [rsp-18h+arg_10], rbx
0x180019c05  mov     [rsp-18h+arg_18], rsi
0x180019c0a  push    rbp
0x180019c0b  push    rdi
0x180019c0c  push    r14
0x180019c0e  mov     rbp, rsp
0x180019c11  sub     rsp, 80h
0x180019c18  mov     rax, cs:__security_cookie
0x180019c1f  xor     rax, rsp
0x180019c22  mov     [rbp+var_10], rax
0x180019c26  xorps   xmm0, xmm0
0x180019c29  mov     esi, edx
0x180019c2b  xor     r14d, r14d
0x180019c2e  lea     rdx, aHead; "head"
0x180019c35  xor     eax, eax
0x180019c37  mov     [rbp+var_4C], r14d
0x180019c3b  movups  [rbp+var_48], xmm0
0x180019c3f  mov     [rbp+var_18], rax
0x180019c43  mov     rbx, rcx
0x180019c46  movups  [rbp+var_38], xmm0
0x180019c4a  mov     [rbp+var_50], r14w
0x180019c4f  movups  [rbp+var_28], xmm0
0x180019c53  call    TTTableOffset
0x180019c58  mov     edi, eax
0x180019c5a  test    eax, eax
0x180019c5c  jz      loc_180019CFD
0x180019c62  lea     rax, [rbp+var_50]
0x180019c66  mov     rcx, rbx
0x180019c69  mov     [rsp+80h+var_58], rax
0x180019c6e  lea     r8d, [r14+36h]
0x180019c72  lea     r9, HEAD_CONTROL
0x180019c79  mov     [rsp+80h+var_60], edi
0x180019c7d  lea     rdx, [rbp+var_48]
0x180019c81  call    ReadGeneric
0x180019c86  test    ax, ax
0x180019c89  jnz     short loc_180019CFD
0x180019c8b  lea     rax, [rbp+var_50]
0x180019c8f  mov     dword ptr [rbp+var_48+8], r14d
0x180019c93  mov     [rsp+80h+var_58], rax
0x180019c98  lea     r8d, [r14+36h]
0x180019c9c  lea     r9, HEAD_CONTROL
0x180019ca3  mov     [rsp+80h+var_60], edi
0x180019ca7  lea     rdx, [rbp+var_48]
0x180019cab  mov     rcx, rbx
0x180019cae  call    WriteGeneric
0x180019cb3  test    ax, ax
0x180019cb6  jnz     short loc_180019CFD
0x180019cb8  lea     r9, [rbp+var_4C]
0x180019cbc  mov     r8d, esi
0x180019cbf  xor     edx, edx
0x180019cc1  mov     rcx, rbx
0x180019cc4  call    CalcChecksum
0x180019cc9  test    ax, ax
0x180019ccc  jnz     short loc_180019CFD
0x180019cce  mov     eax, 0B1B0AFBAh
0x180019cd3  lea     r8d, [r14+36h]
0x180019cd7  sub     eax, [rbp+var_4C]
0x180019cda  lea     r9, HEAD_CONTROL
0x180019ce1  mov     dword ptr [rbp+var_48+8], eax
0x180019ce4  lea     rdx, [rbp+var_48]
0x180019ce8  lea     rax, [rbp+var_50]
0x180019cec  mov     rcx, rbx
0x180019cef  mov     [rsp+80h+var_58], rax
0x180019cf4  mov     [rsp+80h+var_60], edi
0x180019cf8  call    WriteGeneric
0x180019cfd  mov     rcx, [rbp+var_10]
0x180019d01  xor     rcx, rsp; StackCookie
0x180019d04  call    __security_check_cookie
0x180019d09  lea     r11, [rsp+80h+var_s0]
0x180019d11  mov     rbx, [r11+30h]
0x180019d15  mov     rsi, [r11+38h]
0x180019d19  mov     rsp, r11
0x180019d1c  pop     r14
0x180019d1e  pop     rdi
0x180019d1f  pop     rbp
0x180019d20  retn
```
