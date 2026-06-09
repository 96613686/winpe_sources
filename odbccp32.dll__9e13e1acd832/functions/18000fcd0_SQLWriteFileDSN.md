# SQLWriteFileDSN

- ea: `0x18000fcd0`
- end: `0x18000fdc8`
- name: `SQLWriteFileDSN`
- size: `248`
- prototype: `BOOL __stdcall(LPCSTR lpszFileName, LPCSTR lpszAppName, LPCSTR lpszKeyName, LPCSTR lpszString)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180002940`
- `0x18000a150`
- `0x18000fcd0`
- `0x1800138e4`

## pseudocode

```c
BOOL __stdcall SQLWriteFileDSN(LPCSTR lpszFileName, LPCSTR lpszAppName, LPCSTR lpszKeyName, LPCSTR lpszString)
{
  WCHAR *v4; // rbx
  WCHAR *v5; // r14
  WCHAR *v6; // rsi
  WCHAR *v7; // rdi
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  WCHAR *v16; // [rsp+20h] [rbp-28h] BYREF
  WCHAR *v17; // [rsp+28h] [rbp-20h] BYREF
  WCHAR *v18; // [rsp+30h] [rbp-18h] BYREF
  WCHAR *v19; // [rsp+38h] [rbp-10h] BYREF
  BOOL v20; // [rsp+90h] [rbp+48h]

  v4 = 0;
  v5 = 0;
  v6 = 0;
  v16 = 0;
  v7 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  if ( !lpszFileName || (v11 = GWConvertToUnicode(lpszFileName, &v16, 0xFFFFFFFD), v5 = v16, v11) )
  {
    if ( !lpszAppName || (v12 = GWConvertToUnicode(lpszAppName, &v17, 0xFFFFFFFD), v6 = v17, v12) )
    {
      if ( !lpszKeyName || (v13 = GWConvertToUnicode(lpszKeyName, &v18, 0xFFFFFFFD), v7 = v18, v13) )
      {
        if ( !lpszString || (v14 = GWConvertToUnicode(lpszString, &v19, 0xFFFFFFFD), v4 = v19, v14) )
          v20 = SQLWriteFileDSNW(v5, v6, v7, v4);
      }
    }
  }
  OFree(v5);
  OFree(v6);
  OFree(v7);
  OFree(v4);
  return v20;
}

```

## disassembly

```asm
0x18000fcd0  push    rbp
0x18000fcd2  push    rbx
0x18000fcd3  push    rsi
0x18000fcd4  push    rdi
0x18000fcd5  push    r12
0x18000fcd7  push    r13
0x18000fcd9  push    r14
0x18000fcdb  push    r15
0x18000fcdd  mov     rbp, rsp
0x18000fce0  sub     rsp, 48h
0x18000fce4  xor     ebx, ebx
0x18000fce6  xor     r14d, r14d
0x18000fce9  xor     esi, esi
0x18000fceb  mov     [rbp+var_28], r14
0x18000fcef  xor     edi, edi
0x18000fcf1  mov     [rbp+var_20], rsi
0x18000fcf5  mov     [rbp+var_18], rdi
0x18000fcf9  mov     r13, r9
0x18000fcfc  mov     [rbp+var_10], rbx
0x18000fd00  mov     r12, r8
0x18000fd03  mov     [rbp+arg_0], ebx
0x18000fd06  mov     r15, rdx
0x18000fd09  test    rcx, rcx
0x18000fd0c  jz      short loc_18000FD23
0x18000fd0e  lea     r8d, [r14-3]
0x18000fd12  lea     rdx, [rbp+var_28]
0x18000fd16  call    GWConvertToUnicode
0x18000fd1b  mov     r14, [rbp+var_28]
0x18000fd1f  test    eax, eax
0x18000fd21  jz      short loc_18000FD94
0x18000fd23  test    r15, r15
0x18000fd26  jz      short loc_18000FD42
0x18000fd28  mov     r8d, 0FFFFFFFDh
0x18000fd2e  lea     rdx, [rbp+var_20]
0x18000fd32  mov     rcx, r15; lpMultiByteStr
0x18000fd35  call    GWConvertToUnicode
0x18000fd3a  mov     rsi, [rbp+var_20]
0x18000fd3e  test    eax, eax
0x18000fd40  jz      short loc_18000FD94
0x18000fd42  test    r12, r12
0x18000fd45  jz      short loc_18000FD61
0x18000fd47  mov     r8d, 0FFFFFFFDh
0x18000fd4d  lea     rdx, [rbp+var_18]
0x18000fd51  mov     rcx, r12; lpMultiByteStr
0x18000fd54  call    GWConvertToUnicode
0x18000fd59  mov     rdi, [rbp+var_18]
0x18000fd5d  test    eax, eax
0x18000fd5f  jz      short loc_18000FD94
0x18000fd61  test    r13, r13
0x18000fd64  jz      short loc_18000FD80
0x18000fd66  mov     r8d, 0FFFFFFFDh
0x18000fd6c  lea     rdx, [rbp+var_10]
0x18000fd70  mov     rcx, r13; lpMultiByteStr
0x18000fd73  call    GWConvertToUnicode
0x18000fd78  mov     rbx, [rbp+var_10]
0x18000fd7c  test    eax, eax
0x18000fd7e  jz      short loc_18000FD94
0x18000fd80  mov     r9, rbx; lpszString
0x18000fd83  mov     r8, rdi; lpszKeyName
0x18000fd86  mov     rdx, rsi; lpszAppName
0x18000fd89  mov     rcx, r14; lpszFileName
0x18000fd8c  call    SQLWriteFileDSNW
0x18000fd91  mov     [rbp+arg_0], eax
0x18000fd94  mov     rcx, r14
0x18000fd97  call    OFree
0x18000fd9c  mov     rcx, rsi
0x18000fd9f  call    OFree
0x18000fda4  mov     rcx, rdi
0x18000fda7  call    OFree
0x18000fdac  mov     rcx, rbx
0x18000fdaf  call    OFree
0x18000fdb4  mov     eax, [rbp+arg_0]
0x18000fdb7  add     rsp, 48h
0x18000fdbb  pop     r15
0x18000fdbd  pop     r14
0x18000fdbf  pop     r13
0x18000fdc1  pop     r12
0x18000fdc3  pop     rdi
0x18000fdc4  pop     rsi
0x18000fdc5  pop     rbx
0x18000fdc6  pop     rbp
0x18000fdc7  retn
```
