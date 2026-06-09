# SaveConnStructToFileDSN

- ea: `0x180013270`
- end: `0x1800134cd`
- name: `SaveConnStructToFileDSN`
- size: `605`
- prototype: `__int64 __fastcall(HWND hWnd, __int64, __int64, const wchar_t *, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x18000295c`

## callees

- `0x180002e14`
- `0x180004bac`
- `0x1800129e0`
- `0x180012b14`
- `0x180013270`
- `0x1800136b0`
- `0x18001484c`
- `0x180014ae0`

## import_xrefs

- `msvcrt!_waccess` at `0x18001334b`
- `msvcrt!_waccess` at `0x18001334b`
- `USER32!MessageBoxW` at `0x18001336c`
- `USER32!MessageBoxW` at `0x18001336c`
- `USER32!LoadStringW` at `0x180013320`
- `USER32!LoadStringW` at `0x180013340`
- `USER32!LoadStringW` at `0x180013320`
- `USER32!LoadStringW` at `0x180013340`
- `KERNEL32!DeleteFileW` at `0x1800133ca`
- `KERNEL32!DeleteFileW` at `0x1800133ca`

## pseudocode

```c
__int64 __fastcall SaveConnStructToFileDSN(HWND hWnd, __int64 a2, __int64 a3, const wchar_t *a4, _QWORD *a5)
{
  unsigned __int64 v5; // rax
  unsigned __int16 FileWithUnicodeBOM; // r9
  __int64 v8; // rcx
  wchar_t *v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int16 v12; // cx
  __int64 v13; // rcx
  _QWORD *i; // rbx
  wchar_t pszDest[264]; // [rsp+30h] [rbp-C58h] BYREF
  _BYTE v17[528]; // [rsp+240h] [rbp-A48h] BYREF
  WCHAR Buffer[512]; // [rsp+450h] [rbp-838h] BYREF
  WCHAR Text[512]; // [rsp+850h] [rbp-438h] BYREF

  v5 = -1;
  do
    ++v5;
  while ( a4[v5] );
  if ( v5 <= 0x104 )
  {
    StringCchCopyW(pszDest, 0x105u, a4);
    FileWithUnicodeBOM = EnforceDSNExtension(v8, pszDest, 261);
    if ( FileWithUnicodeBOM != 0xFFFF )
    {
      v9 = pszDest;
      LoadStringW(g_hResDLL, 0x590u, Buffer, 512);
      LoadStringW(g_hResDLL, 0x592u, Text, 512);
      while ( !_waccess(v9, 0) )
      {
        if ( MessageBoxW(hWnd, Text, Buffer, 0x34u) == 6 )
        {
          DeleteFileW(v9);
          break;
        }
        if ( (unsigned __int16)SaveFileDSNUI(v17, v10, hWnd) )
        {
          PostInstError(18);
          return (unsigned __int16)(v12 - 17);
        }
        FileWithUnicodeBOM = EnforceDSNExtension(v11, v17, 261);
        if ( FileWithUnicodeBOM == 0xFFFF )
          return FileWithUnicodeBOM;
        v9 = (wchar_t *)v17;
      }
      FileWithUnicodeBOM = CreateFileWithUnicodeBOM(v9);
      if ( !FileWithUnicodeBOM )
      {
        if ( !a5[3]
          || (FileWithUnicodeBOM = WriteFileDSNW(v13, v9, L"ODBC", L"DSN", a5[3]), (FileWithUnicodeBOM & 0xFFFE) == 0) )
        {
          if ( !a5[4]
            || (FileWithUnicodeBOM = WriteFileDSNW(v13, v9, L"ODBC", L"DRIVER", a5[4]),
                (FileWithUnicodeBOM & 0xFFFE) == 0) )
          {
            if ( !a5[5]
              || (FileWithUnicodeBOM = WriteFileDSNW(v13, v9, L"ODBC", L"UID", a5[5]), (FileWithUnicodeBOM & 0xFFFE) == 0) )
            {
              for ( i = (_QWORD *)a5[10]; i; i = (_QWORD *)i[3] )
              {
                FileWithUnicodeBOM = WriteFileDSNW(v13, v9, L"ODBC", *i, i[1]);
                if ( (FileWithUnicodeBOM & 0xFFFE) != 0 )
                  break;
              }
            }
          }
        }
      }
    }
  }
  else
  {
    PostInstError(9);
  }
  return FileWithUnicodeBOM;
}

```

## disassembly

```asm
0x180013270  mov     [rsp+arg_8], rbx
0x180013275  push    rsi
0x180013276  push    rdi
0x180013277  push    r12
0x180013279  push    r14
0x18001327b  push    r15
0x18001327d  sub     rsp, 0C60h
0x180013284  mov     rax, cs:__security_cookie
0x18001328b  xor     rax, rsp
0x18001328e  mov     [rsp+0C88h+var_38], rax
0x180013296  mov     rbx, [rsp+0C88h+arg_20]
0x18001329e  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800132a2  mov     rax, r15
0x1800132a5  xor     r14d, r14d
0x1800132a8  mov     rsi, rcx
0x1800132ab  inc     rax
0x1800132ae  cmp     [r9+rax*2], r14w
0x1800132b3  jnz     short loc_1800132AB
0x1800132b5  cmp     rax, 104h
0x1800132bb  jbe     short loc_1800132D0
0x1800132bd  mov     ecx, 9
0x1800132c2  movzx   r9d, r15w
0x1800132c6  call    PostInstError
0x1800132cb  jmp     loc_1800134A1
0x1800132d0  mov     r12d, 105h
0x1800132d6  lea     rcx, [rsp+0C88h+pszDest]; pszDest
0x1800132db  mov     edx, r12d; cchDest
0x1800132de  mov     r8, r9; pszSrc
0x1800132e1  call    StringCchCopyW
0x1800132e6  mov     r8d, r12d
0x1800132e9  lea     rdx, [rsp+0C88h+pszDest]
0x1800132ee  call    EnforceDSNExtension
0x1800132f3  movzx   r9d, ax
0x1800132f7  cmp     ax, r15w
0x1800132fb  jz      loc_1800134A1
0x180013301  mov     rcx, cs:g_hResDLL; hInstance
0x180013308  lea     r8, [rsp+0C88h+Buffer]; lpBuffer
0x180013310  mov     r9d, 200h; cchBufferMax
0x180013316  lea     rdi, [rsp+0C88h+pszDest]
0x18001331b  mov     edx, 590h; uID
0x180013320  call    cs:__imp_LoadStringW
0x180013326  mov     rcx, cs:g_hResDLL; hInstance
0x18001332d  lea     r8, [rsp+0C88h+Text]; lpBuffer
0x180013335  mov     r9d, 200h; cchBufferMax
0x18001333b  mov     edx, 592h; uID
0x180013340  call    cs:__imp_LoadStringW
0x180013346  xor     edx, edx; AccessMode
0x180013348  mov     rcx, rdi; FileName
0x18001334b  call    cs:__imp__waccess
0x180013351  test    eax, eax
0x180013353  jnz     short loc_1800133D0
0x180013355  lea     r9d, [rax+34h]; uType
0x180013359  mov     rcx, rsi; hWnd
0x18001335c  lea     r8, [rsp+0C88h+Buffer]; lpCaption
0x180013364  lea     rdx, [rsp+0C88h+Text]; lpText
0x18001336c  call    cs:__imp_MessageBoxW
0x180013372  cmp     eax, 6
0x180013375  jz      short loc_1800133C7
0x180013377  mov     r8, rsi
0x18001337a  lea     rcx, [rsp+0C88h+var_A48]
0x180013382  call    SaveFileDSNUI
0x180013387  test    ax, ax
0x18001338a  jnz     short loc_1800133B4
0x18001338c  mov     r8, r12
0x18001338f  lea     rdx, [rsp+0C88h+var_A48]
0x180013397  call    EnforceDSNExtension
0x18001339c  movzx   r9d, ax
0x1800133a0  cmp     ax, r15w
0x1800133a4  jz      loc_1800134A1
0x1800133aa  lea     rdi, [rsp+0C88h+var_A48]
0x1800133b2  jmp     short loc_180013346
0x1800133b4  mov     ecx, 12h
0x1800133b9  call    PostInstError
0x1800133be  lea     r9d, [rcx-11h]
0x1800133c2  jmp     loc_1800134A1
0x1800133c7  mov     rcx, rdi; lpFileName
0x1800133ca  call    cs:__imp_DeleteFileW
0x1800133d0  mov     rcx, rdi
0x1800133d3  call    CreateFileWithUnicodeBOM
0x1800133d8  movzx   r9d, ax
0x1800133dc  test    ax, ax
0x1800133df  jnz     loc_1800134A1
0x1800133e5  mov     rax, [rbx+18h]
0x1800133e9  lea     rsi, aOdbc; "ODBC"
0x1800133f0  test    rax, rax
0x1800133f3  jz      short loc_18001341A
0x1800133f5  lea     r9, aDsn; "DSN"
0x1800133fc  mov     [rsp+0C88h+var_C68], rax
0x180013401  mov     r8, rsi
0x180013404  mov     rdx, rdi
0x180013407  call    WriteFileDSNW
0x18001340c  movzx   r9d, ax
0x180013410  test    ax, 0FFFEh
0x180013414  jnz     loc_1800134A1
0x18001341a  mov     rax, [rbx+20h]
0x18001341e  test    rax, rax
0x180013421  jz      short loc_180013444
0x180013423  lea     r9, aDriver; "DRIVER"
0x18001342a  mov     [rsp+0C88h+var_C68], rax
0x18001342f  mov     r8, rsi
0x180013432  mov     rdx, rdi
0x180013435  call    WriteFileDSNW
0x18001343a  movzx   r9d, ax
0x18001343e  test    ax, 0FFFEh
0x180013442  jnz     short loc_1800134A1
0x180013444  mov     rax, [rbx+28h]
0x180013448  test    rax, rax
0x18001344b  jz      short loc_18001346E
0x18001344d  lea     r9, aUid; "UID"
0x180013454  mov     [rsp+0C88h+var_C68], rax
0x180013459  mov     r8, rsi
0x18001345c  mov     rdx, rdi
0x18001345f  call    WriteFileDSNW
0x180013464  movzx   r9d, ax
0x180013468  test    ax, 0FFFEh
0x18001346c  jnz     short loc_1800134A1
0x18001346e  mov     rbx, [rbx+50h]
0x180013472  test    rbx, rbx
0x180013475  jz      short loc_1800134A1
0x180013477  mov     rax, [rbx+8]
0x18001347b  mov     r8, rsi
0x18001347e  mov     r9, [rbx]
0x180013481  mov     rdx, rdi
0x180013484  mov     [rsp+0C88h+var_C68], rax
0x180013489  call    WriteFileDSNW
0x18001348e  movzx   r9d, ax
0x180013492  test    ax, 0FFFEh
0x180013496  jnz     short loc_1800134A1
0x180013498  mov     rbx, [rbx+18h]
0x18001349c  test    rbx, rbx
0x18001349f  jnz     short loc_180013477
0x1800134a1  movzx   eax, r9w
0x1800134a5  mov     rcx, [rsp+0C88h+var_38]
0x1800134ad  xor     rcx, rsp; StackCookie
0x1800134b0  call    __security_check_cookie
0x1800134b5  mov     rbx, [rsp+0C88h+arg_8]
0x1800134bd  add     rsp, 0C60h
0x1800134c4  pop     r15
0x1800134c6  pop     r14
0x1800134c8  pop     r12
0x1800134ca  pop     rdi
0x1800134cb  pop     rsi
0x1800134cc  retn
```
