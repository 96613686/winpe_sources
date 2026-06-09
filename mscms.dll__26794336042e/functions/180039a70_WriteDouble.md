# WriteDouble

- ea: `0x180039a70`
- end: `0x180039b94`
- name: `WriteDouble`
- size: `292`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x180030d48`
- `0x1800325cc`
- `0x1800346a4`
- `0x180034c80`
- `0x180034f88`
- `0x180035f30`
- `0x1800367f0`
- `0x180038458`
- `0x1800387e4`
- `0x1800388e8`
- `0x180038cf8`
- `0x1800390c8`

## callees

- `0x18002f228`
- `0x180039224`
- `0x180039a70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039b4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039b60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039b4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039b60`

## pseudocode

```c
__int64 __fastcall WriteDouble(STRSAFE_LPSTR *a1, _DWORD *a2, double a3)
{
  size_t v4; // rdi
  double v6; // xmm6_8
  double v7; // xmm0_8
  int v8; // r8d
  HRESULT v9; // eax
  DWORD v10; // ecx
  unsigned int v11; // ebx
  int v12; // ecx
  size_t pcchRemaining; // [rsp+A8h] [rbp+10h] BYREF

  v4 = (unsigned int)*a2;
  v6 = (double)(int)floor(a3 * 10000.0 + 0.5) / 10000.0;
  v7 = floor(COERCE_DOUBLE(*(_QWORD *)&v6 & _xmm));
  pcchRemaining = v4;
  v8 = 32;
  if ( v6 < 0.0 )
    v8 = 45;
  v9 = StringCchPrintfExA(
         *a1,
         (unsigned int)v4,
         0,
         &pcchRemaining,
         0x1000u,
         "%c%d.%0.4lu ",
         v8,
         (unsigned __int16)(int)v7,
         (int)((COERCE_DOUBLE(*(_QWORD *)&v6 & _xmm) - v7) * 10000.0));
  if ( v9 == -2147024809 )
  {
    v10 = 87;
LABEL_7:
    SetLastError(v10);
    return 0;
  }
  if ( v9 == -2147024774 )
  {
    v10 = 122;
    goto LABEL_7;
  }
  v11 = 0;
  if ( v9 >= 0 )
  {
    v12 = pcchRemaining;
    v11 = 1;
    *a1 += v4 - pcchRemaining;
    *a2 = v12;
  }
  else
  {
    SetLastError(v9);
  }
  return v11;
}

```

## disassembly

```asm
0x180039a70  push    rbx
0x180039a72  push    rsi
0x180039a73  push    rdi
0x180039a74  push    r14
0x180039a76  sub     rsp, 78h
0x180039a7a  mulsd   xmm2, cs:__real@40c3880000000000
0x180039a82  mov     r14, rdx
0x180039a85  mov     edi, [rdx]
0x180039a87  mov     rsi, rcx
0x180039a8a  movaps  [rsp+98h+var_38], xmm6
0x180039a8f  movaps  [rsp+98h+var_48], xmm7
0x180039a94  addsd   xmm2, cs:__real@3fe0000000000000
0x180039a9c  movaps  xmm0, xmm2; X
0x180039a9f  call    floor
0x180039aa4  cvttsd2si eax, xmm0
0x180039aa8  movd    xmm6, eax
0x180039aac  cvtdq2pd xmm6, xmm6
0x180039ab0  divsd   xmm6, cs:__real@40c3880000000000
0x180039ab8  movaps  xmm7, xmm6
0x180039abb  andps   xmm7, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x180039ac2  movaps  xmm0, xmm7; X
0x180039ac5  call    floor
0x180039aca  mov     eax, 2Dh ; '-'
0x180039acf  mov     [rsp+98h+pcchRemaining], rdi
0x180039ad7  xorps   xmm1, xmm1
0x180039ada  subsd   xmm7, xmm0
0x180039ade  comisd  xmm1, xmm6
0x180039ae2  lea     r9, [rsp+98h+pcchRemaining]; pcchRemaining
0x180039aea  lea     r8d, [rax-0Dh]
0x180039aee  mulsd   xmm7, cs:__real@40c3880000000000
0x180039af6  cmova   r8d, eax
0x180039afa  cvttsd2si eax, xmm0
0x180039afe  cvttsd2si rdx, xmm7
0x180039b03  movzx   ecx, ax
0x180039b06  lea     rax, pszFormat; "%c%d.%0.4lu "
0x180039b0d  mov     [rsp+98h+var_58], edx
0x180039b11  mov     edx, edi; cchDest
0x180039b13  mov     [rsp+98h+var_60], ecx
0x180039b17  mov     rcx, [rsi]; pszDest
0x180039b1a  mov     [rsp+98h+var_68], r8d
0x180039b1f  xor     r8d, r8d; ppszDestEnd
0x180039b22  mov     [rsp+98h+pszFormat], rax; pszFormat
0x180039b27  mov     [rsp+98h+dwFlags], 1000h; dwFlags
0x180039b2f  call    StringCchPrintfExA
0x180039b34  cmp     eax, 80070057h
0x180039b39  jnz     short loc_180039B42
0x180039b3b  mov     ecx, 57h ; 'W'
0x180039b40  jmp     short loc_180039B4E
0x180039b42  cmp     eax, 8007007Ah
0x180039b47  jnz     short loc_180039B58
0x180039b49  mov     ecx, 7Ah ; 'z'; dwErrCode
0x180039b4e  call    cs:__imp_SetLastError
0x180039b54  xor     ebx, ebx
0x180039b56  jmp     short loc_180039B7E
0x180039b58  xor     ebx, ebx
0x180039b5a  test    eax, eax
0x180039b5c  jns     short loc_180039B68
0x180039b5e  mov     ecx, eax; dwErrCode
0x180039b60  call    cs:__imp_SetLastError
0x180039b66  jmp     short loc_180039B7E
0x180039b68  mov     rcx, [rsp+98h+pcchRemaining]
0x180039b70  mov     ebx, 1
0x180039b75  sub     rdi, rcx
0x180039b78  add     [rsi], rdi
0x180039b7b  mov     [r14], ecx
0x180039b7e  movaps  xmm6, [rsp+98h+var_38]
0x180039b83  mov     eax, ebx
0x180039b85  movaps  xmm7, [rsp+98h+var_48]
0x180039b8a  add     rsp, 78h
0x180039b8e  pop     r14
0x180039b90  pop     rdi
0x180039b91  pop     rsi
0x180039b92  pop     rbx
0x180039b93  retn
```
