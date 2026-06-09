# SQLInstallDriverEx

- ea: `0x18000f3e0`
- end: `0x18000f521`
- name: `SQLInstallDriverEx`
- size: `321`
- prototype: `BOOL __stdcall(LPCSTR lpszDriver, LPCSTR lpszPathIn, LPSTR lpszPathOut, WORD cchPathOutMax, WORD *pcchPathOut, WORD fRequest, LPDWORD lpdwUsageCount)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180002940`
- `0x180009160`
- `0x18000f3e0`
- `0x18000fea8`
- `0x1800138e4`
- `0x180013c2c`

## import_xrefs

- `msvcrt!calloc` at `0x18000f48c`
- `msvcrt!calloc` at `0x18000f48c`

## pseudocode

```c
BOOL __stdcall SQLInstallDriverEx(
        LPCSTR lpszDriver,
        LPCSTR lpszPathIn,
        LPSTR lpszPathOut,
        WORD cchPathOutMax,
        WORD *pcchPathOut,
        WORD fRequest,
        LPDWORD lpdwUsageCount)
{
  WORD *v7; // r15
  __int64 v8; // rbx
  WCHAR *v11; // rsi
  WCHAR *v12; // rdi
  WCHAR *v13; // r14
  __int16 v14; // ax
  LPCCH v15; // r9
  int v16; // eax
  int v17; // eax
  __int64 v18; // rcx
  WCHAR *v20; // [rsp+40h] [rbp-20h] BYREF
  WCHAR *v21; // [rsp+48h] [rbp-18h] BYREF
  LPSTR v22; // [rsp+50h] [rbp-10h] BYREF
  __int16 v23; // [rsp+A0h] [rbp+40h] BYREF
  BOOL v24; // [rsp+B0h] [rbp+50h]

  v7 = (WORD *)&v23;
  v8 = cchPathOutMax;
  v22 = lpszPathOut;
  v20 = 0;
  v11 = 0;
  v21 = 0;
  if ( pcchPathOut )
    v7 = pcchPathOut;
  v24 = 0;
  v23 = 0;
  v12 = 0;
  v13 = 0;
  if ( !lpszDriver || (v14 = dnlen(lpszDriver), v16 = GWConvertToUnicode(v15, &v20, v14), v11 = v20, v16) )
  {
    if ( !lpszPathIn || (v17 = GWConvertToUnicode(lpszPathIn, &v21, 0xFFFFFFFD), v12 = v21, v17) )
    {
      if ( !(_WORD)v8 || !lpszPathOut || (v13 = (WCHAR *)calloc(2 * v8, 1u)) != 0 )
      {
        v24 = SQLInstallDriverExW(v11, v12, v13, v8, v7, fRequest, lpdwUsageCount);
        if ( v24 && lpszPathOut && (_WORD)v8 )
          LConvertToAnsiWordLengths(v18, v13, *v7, &v22, v8, v7);
      }
    }
  }
  OFree(v11);
  OFree(v12);
  OFree(v13);
  return v24;
}

```

## disassembly

```asm
0x18000f3e0  mov     [rsp-38h+arg_8], rbx
0x18000f3e5  push    rbp
0x18000f3e6  push    rsi
0x18000f3e7  push    rdi
0x18000f3e8  push    r12
0x18000f3ea  push    r13
0x18000f3ec  push    r14
0x18000f3ee  push    r15
0x18000f3f0  mov     rbp, rsp
0x18000f3f3  sub     rsp, 60h
0x18000f3f7  mov     rax, [rbp+pcchPathOut]
0x18000f3fb  lea     r15, [rbp+arg_0]
0x18000f3ff  movzx   ebx, r9w
0x18000f403  mov     r12, r8
0x18000f406  mov     r9, rcx
0x18000f409  mov     [rbp+var_10], r8
0x18000f40d  xor     ecx, ecx
0x18000f40f  mov     r13, rdx
0x18000f412  test    rax, rax
0x18000f415  mov     [rbp+var_20], rcx
0x18000f419  mov     esi, ecx
0x18000f41b  mov     [rbp+var_18], rcx
0x18000f41f  cmovnz  r15, rax
0x18000f423  mov     [rbp+arg_10], ecx
0x18000f426  mov     [rbp+arg_0], cx
0x18000f42a  mov     edi, ecx
0x18000f42c  mov     r14d, ecx
0x18000f42f  test    r9, r9
0x18000f432  jz      short loc_18000F458
0x18000f434  mov     rcx, r9
0x18000f437  call    dnlen
0x18000f43c  movsx   r8d, ax
0x18000f440  lea     rdx, [rbp+var_20]
0x18000f444  mov     rcx, r9; lpMultiByteStr
0x18000f447  call    GWConvertToUnicode
0x18000f44c  mov     rsi, [rbp+var_20]
0x18000f450  test    eax, eax
0x18000f452  jz      loc_18000F4EE
0x18000f458  test    r13, r13
0x18000f45b  jz      short loc_18000F477
0x18000f45d  mov     r8d, 0FFFFFFFDh
0x18000f463  lea     rdx, [rbp+var_18]
0x18000f467  mov     rcx, r13; lpMultiByteStr
0x18000f46a  call    GWConvertToUnicode
0x18000f46f  mov     rdi, [rbp+var_18]
0x18000f473  test    eax, eax
0x18000f475  jz      short loc_18000F4EE
0x18000f477  test    bx, bx
0x18000f47a  jz      short loc_18000F49A
0x18000f47c  test    r12, r12
0x18000f47f  jz      short loc_18000F49A
0x18000f481  mov     rcx, rbx
0x18000f484  mov     edx, 1; Size
0x18000f489  add     rcx, rcx; Count
0x18000f48c  call    cs:__imp_calloc
0x18000f492  mov     r14, rax
0x18000f495  test    rax, rax
0x18000f498  jz      short loc_18000F4EE
0x18000f49a  mov     rcx, [rbp+lpdwUsageCount]
0x18000f49e  movzx   r9d, bx; cchPathOutMax
0x18000f4a2  mov     [rsp+60h+var_30], rcx; lpdwUsageCount
0x18000f4a7  mov     r8, r14; lpszPathOut
0x18000f4aa  movzx   ecx, [rbp+fRequest]
0x18000f4ae  mov     rdx, rdi; lpszPathIn
0x18000f4b1  mov     [rsp+60h+var_38], cx; fRequest
0x18000f4b6  mov     rcx, rsi; lpszDriver
0x18000f4b9  mov     [rsp+60h+var_40], r15; pcchPathOut
0x18000f4be  call    SQLInstallDriverExW
0x18000f4c3  mov     [rbp+arg_10], eax
0x18000f4c6  test    eax, eax
0x18000f4c8  jz      short loc_18000F4EE
0x18000f4ca  test    r12, r12
0x18000f4cd  jz      short loc_18000F4EE
0x18000f4cf  test    bx, bx
0x18000f4d2  jz      short loc_18000F4EE
0x18000f4d4  movzx   r8d, word ptr [r15]
0x18000f4d8  lea     r9, [rbp+var_10]
0x18000f4dc  mov     qword ptr [rsp+60h+var_38], r15
0x18000f4e1  mov     rdx, r14
0x18000f4e4  mov     word ptr [rsp+60h+var_40], bx
0x18000f4e9  call    LConvertToAnsiWordLengths
0x18000f4ee  mov     rcx, rsi
0x18000f4f1  call    OFree
0x18000f4f6  mov     rcx, rdi
0x18000f4f9  call    OFree
0x18000f4fe  mov     rcx, r14
0x18000f501  call    OFree
0x18000f506  mov     eax, [rbp+arg_10]
0x18000f509  mov     rbx, [rsp+60h+arg_8]
0x18000f511  add     rsp, 60h
0x18000f515  pop     r15
0x18000f517  pop     r14
0x18000f519  pop     r13
0x18000f51b  pop     r12
0x18000f51d  pop     rdi
0x18000f51e  pop     rsi
0x18000f51f  pop     rbp
0x18000f520  retn
```
