# SQLInstallDriver

- ea: `0x18000f2b0`
- end: `0x18000f3d8`
- name: `SQLInstallDriver`
- size: `296`
- prototype: `BOOL __stdcall(LPCSTR lpszInfFile, LPCSTR lpszDriver, LPSTR lpszPath, WORD cchPathMax, WORD *pcchPathOut)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180002940`
- `0x180009280`
- `0x18000f2b0`
- `0x18000fea8`
- `0x1800138e4`
- `0x180013c2c`
- `0x180014ae0`

## pseudocode

```c
BOOL __stdcall SQLInstallDriver(
        LPCSTR lpszInfFile,
        LPCSTR lpszDriver,
        LPSTR lpszPath,
        WORD cchPathMax,
        WORD *pcchPathOut)
{
  WORD *v6; // rdi
  BOOL v7; // esi
  WORD v8; // r14
  const CHAR *v10; // rcx
  unsigned int v11; // r8d
  __int64 v12; // rcx
  __int16 v14; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpszDrivera; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpszInfFilea; // [rsp+50h] [rbp-B0h] BYREF
  LPSTR v17; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR szPath[264]; // [rsp+60h] [rbp-A0h] BYREF

  v17 = lpszPath;
  lpszInfFilea = 0;
  v6 = (WORD *)&v14;
  v7 = 0;
  lpszDrivera = 0;
  v14 = 0;
  v8 = 261;
  if ( pcchPathOut )
    v6 = pcchPathOut;
  if ( cchPathMax <= 0x105u )
    v8 = cchPathMax;
  if ( (unsigned int)GWConvertToUnicode(lpszInfFile, (WCHAR **)&lpszInfFilea, 0xFFFFFFFD) )
  {
    if ( !lpszDriver
      || ((v10 = lpszDriver, lpszInfFile) ? (const CHAR *)(v11 = -3) : (v11 = dnlen(lpszDriver), v10 = lpszDriver),
          (unsigned int)GWConvertToUnicode(v10, (WCHAR **)&lpszDrivera, v11)) )
    {
      v7 = SQLInstallDriverW(lpszInfFilea, lpszDrivera, szPath, v8, v6);
      if ( v7 )
        LConvertToAnsiWordLengths(v12, szPath, *v6, &v17, v8, v6);
    }
  }
  OFree((void *)lpszInfFilea);
  OFree((void *)lpszDrivera);
  return v7;
}

```

## disassembly

```asm
0x18000f2b0  push    rbp
0x18000f2b2  push    rbx
0x18000f2b3  push    rsi
0x18000f2b4  push    rdi
0x18000f2b5  push    r14
0x18000f2b7  push    r15
0x18000f2b9  lea     rbp, [rsp-188h]
0x18000f2c1  sub     rsp, 288h
0x18000f2c8  mov     rax, cs:__security_cookie
0x18000f2cf  xor     rax, rsp
0x18000f2d2  mov     [rbp+1B0h+var_40], rax
0x18000f2d9  xor     eax, eax
0x18000f2db  mov     [rsp+2B0h+var_258], r8
0x18000f2e0  mov     rbx, rdx
0x18000f2e3  mov     [rsp+2B0h+lpszInfFile], 0
0x18000f2ec  mov     rdx, [rbp+1B0h+pcchPathOut]
0x18000f2f3  lea     rdi, [rsp+2B0h+var_270]
0x18000f2f8  xor     esi, esi
0x18000f2fa  mov     [rsp+2B0h+lpszDriver], 0
0x18000f303  test    rdx, rdx
0x18000f306  mov     [rsp+2B0h+var_270], ax
0x18000f30b  mov     r14d, 105h
0x18000f311  mov     r15, rcx
0x18000f314  cmovnz  rdi, rdx
0x18000f318  cmp     r9w, r14w
0x18000f31c  lea     r8d, [rsi-3]
0x18000f320  lea     rdx, [rsp+2B0h+lpszInfFile]
0x18000f325  cmovbe  r14w, r9w
0x18000f32a  call    GWConvertToUnicode
0x18000f32f  test    eax, eax
0x18000f331  jz      short loc_18000F3A3
0x18000f333  test    rbx, rbx
0x18000f336  jz      short loc_18000F362
0x18000f338  mov     rcx, rbx; lpMultiByteStr
0x18000f33b  test    r15, r15
0x18000f33e  jnz     short loc_18000F34E
0x18000f340  call    dnlen
0x18000f345  movsx   r8d, ax
0x18000f349  mov     rcx, rbx
0x18000f34c  jmp     short loc_18000F354
0x18000f34e  mov     r8d, 0FFFFFFFDh
0x18000f354  lea     rdx, [rsp+2B0h+lpszDriver]
0x18000f359  call    GWConvertToUnicode
0x18000f35e  test    eax, eax
0x18000f360  jz      short loc_18000F3A3
0x18000f362  mov     rdx, [rsp+2B0h+lpszDriver]; lpszDriver
0x18000f367  lea     r8, [rsp+2B0h+szPath]; lpszPath
0x18000f36c  mov     rcx, [rsp+2B0h+lpszInfFile]; lpszInfFile
0x18000f371  movzx   r9d, r14w; cchPathMax
0x18000f375  mov     [rsp+2B0h+var_290], rdi; pcchPathOut
0x18000f37a  call    SQLInstallDriverW
0x18000f37f  mov     esi, eax
0x18000f381  test    eax, eax
0x18000f383  jz      short loc_18000F3A3
0x18000f385  movzx   r8d, word ptr [rdi]
0x18000f389  lea     r9, [rsp+2B0h+var_258]
0x18000f38e  mov     [rsp+2B0h+var_288], rdi
0x18000f393  lea     rdx, [rsp+2B0h+szPath]
0x18000f398  mov     word ptr [rsp+2B0h+var_290], r14w
0x18000f39e  call    LConvertToAnsiWordLengths
0x18000f3a3  mov     rcx, [rsp+2B0h+lpszInfFile]
0x18000f3a8  call    OFree
0x18000f3ad  mov     rcx, [rsp+2B0h+lpszDriver]
0x18000f3b2  call    OFree
0x18000f3b7  mov     eax, esi
0x18000f3b9  mov     rcx, [rbp+1B0h+var_40]
0x18000f3c0  xor     rcx, rsp; StackCookie
0x18000f3c3  call    __security_check_cookie
0x18000f3c8  add     rsp, 288h
0x18000f3cf  pop     r15
0x18000f3d1  pop     r14
0x18000f3d3  pop     rdi
0x18000f3d4  pop     rsi
0x18000f3d5  pop     rbx
0x18000f3d6  pop     rbp
0x18000f3d7  retn
```
