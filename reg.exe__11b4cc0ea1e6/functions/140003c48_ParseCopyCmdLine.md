# ParseCopyCmdLine

- ea: `0x140003c48`
- end: `0x140003ebc`
- name: `ParseCopyCmdLine`
- size: `628`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000375c`

## callees

- `0x140001e90`
- `0x140002b70`
- `0x140003c48`
- `0x14000cd48`
- `0x14000d010`
- `0x14000daa4`
- `0x14000e228`
- `0x14000e284`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003cd5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003cd5`

## pseudocode

```c
__int64 __fastcall ParseCopyCmdLine(unsigned int a1, __int64 a2, _DWORD *a3, __int64 a4, _DWORD *a5)
{
  __int64 v10; // rcx
  __int64 ResString2FromModule; // rax
  __int64 v12; // r8
  unsigned int v13; // r14d

  if ( !a1 || !a2 || !a3 || !a4 || !a5 || *a3 > 0xBu )
    goto LABEL_36;
  if ( a1 >= 3 && (unsigned int)InString(*(LPCWSTR *)(a2 + 16), L"-?|/?|-h|/h") == 1 )
  {
    if ( a1 == 3 )
    {
      *a5 = 1;
      return 1;
    }
    goto LABEL_12;
  }
  if ( a1 - 4 > 3 )
  {
LABEL_12:
    SetLastError(0x800401E4);
    ResString2FromModule = GetResString2FromModule(v10, 103, 0);
    SetReason2(1, ResString2FromModule, L"COPY");
    return 0;
  }
  if ( (unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8), L"COPY", (__int64)a3, 0) )
  {
LABEL_36:
    SaveErrorMessage(87);
    return 0;
  }
  if ( (unsigned int)BreakDownKeyString(*(_QWORD *)(a2 + 16), a3)
    && (unsigned int)BreakDownKeyString(*(_QWORD *)(a2 + 24), a4) )
  {
    v13 = 4;
    if ( a1 > 4 )
    {
      while ( 1 )
      {
        if ( (unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * v13), L"/f", v12, 0)
          && (unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * v13), L"-f", v12, 0) )
        {
          if ( (unsigned int)StringCompareW(*(PCNZWCH *)(a2 + 8LL * v13), L"/s", 1, 0)
            && (unsigned int)StringCompareW(*(PCNZWCH *)(a2 + 8LL * v13), L"-s", 1, 0) )
          {
            if ( (unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * v13), L"/reg:32", v12, 0)
              && (unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * v13), L"-reg:32", v12, 0) )
            {
              if ( (unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * v13), L"/reg:64", v12, 0)
                && (unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * v13), L"-reg:64", v12, 0)
                || a3[35] )
              {
                goto LABEL_12;
              }
              a3[35] = 256;
              *(_DWORD *)(a4 + 140) = 256;
            }
            else
            {
              if ( a3[35] )
                goto LABEL_12;
              a3[35] = 512;
              *(_DWORD *)(a4 + 140) = 512;
            }
          }
          else
          {
            if ( a3[8] == 1 )
              goto LABEL_12;
            a3[8] = 1;
          }
        }
        else
        {
          if ( a3[6] == 1 )
            goto LABEL_12;
          a3[6] = 1;
        }
        if ( ++v13 >= a1 )
          return 1;
      }
    }
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x140003c48  push    rbx
0x140003c4a  push    rbp
0x140003c4b  push    rsi
0x140003c4c  push    rdi
0x140003c4d  push    r12
0x140003c4f  push    r14
0x140003c51  push    r15
0x140003c53  sub     rsp, 20h
0x140003c57  mov     r15, r9
0x140003c5a  mov     rbx, r8
0x140003c5d  mov     rdi, rdx
0x140003c60  mov     esi, ecx
0x140003c62  test    ecx, ecx
0x140003c64  jz      loc_140003EA1
0x140003c6a  test    rdx, rdx
0x140003c6d  jz      loc_140003EA1
0x140003c73  test    rbx, rbx
0x140003c76  jz      loc_140003EA1
0x140003c7c  test    r9, r9
0x140003c7f  jz      loc_140003EA1
0x140003c85  mov     r14, [rsp+58h+arg_20]
0x140003c8d  test    r14, r14
0x140003c90  jz      loc_140003EA1
0x140003c96  cmp     dword ptr [r8], 0Bh
0x140003c9a  ja      loc_140003EA1
0x140003ca0  mov     r12d, 1
0x140003ca6  cmp     ecx, 3
0x140003ca9  jb      short loc_140003CFE
0x140003cab  mov     rcx, [rdi+10h]; lpString
0x140003caf  lea     rdx, aHH; "-?|/?|-h|/h"
0x140003cb6  call    InString
0x140003cbb  cmp     eax, r12d
0x140003cbe  jnz     short loc_140003CFE
0x140003cc0  cmp     esi, 3
0x140003cc3  jnz     short loc_140003CD0
0x140003cc5  mov     [r14], r12d
0x140003cc8  mov     eax, r12d
0x140003ccb  jmp     loc_140003EAD
0x140003cd0  mov     ecx, 800401E4h; dwErrCode
0x140003cd5  call    cs:__imp_SetLastError
0x140003cdb  xor     r8d, r8d
0x140003cde  lea     edx, [r8+67h]
0x140003ce2  call    GetResString2FromModule
0x140003ce7  lea     r8, aCopy_0; "COPY"
0x140003cee  mov     rdx, rax
0x140003cf1  mov     ecx, r12d
0x140003cf4  call    SetReason2
0x140003cf9  jmp     loc_140003EAB
0x140003cfe  lea     eax, [rsi-4]
0x140003d01  cmp     eax, 3
0x140003d04  ja      short loc_140003CD0
0x140003d06  mov     rcx, [rdi+8]; lpString1
0x140003d0a  lea     rdx, aCopy; "COPY"
0x140003d11  xor     r9d, r9d
0x140003d14  call    StringCompareExW
0x140003d19  test    eax, eax
0x140003d1b  jnz     loc_140003EA1
0x140003d21  mov     rcx, [rdi+10h]
0x140003d25  mov     rdx, rbx
0x140003d28  call    BreakDownKeyString
0x140003d2d  test    eax, eax
0x140003d2f  jz      loc_140003EAB
0x140003d35  mov     rcx, [rdi+18h]
0x140003d39  mov     rdx, r15
0x140003d3c  call    BreakDownKeyString
0x140003d41  test    eax, eax
0x140003d43  jz      loc_140003EAB
0x140003d49  mov     r14d, 4
0x140003d4f  cmp     esi, r14d
0x140003d52  jbe     loc_140003CC8
0x140003d58  mov     ebp, r14d
0x140003d5b  lea     rdx, asc_140010CFC; "/f"
0x140003d62  xor     r9d, r9d
0x140003d65  mov     rcx, [rdi+rbp*8]; lpString1
0x140003d69  call    StringCompareExW
0x140003d6e  test    eax, eax
0x140003d70  jz      loc_140003E82
0x140003d76  mov     rcx, [rdi+rbp*8]; lpString1
0x140003d7a  lea     rdx, asc_140010D04; "-f"
0x140003d81  xor     r9d, r9d
0x140003d84  call    StringCompareExW
0x140003d89  test    eax, eax
0x140003d8b  jz      loc_140003E82
0x140003d91  mov     rcx, [rdi+rbp*8]; lpString1
0x140003d95  lea     rdx, aS_4; "/s"
0x140003d9c  xor     r9d, r9d
0x140003d9f  mov     r8d, r12d
0x140003da2  call    StringCompareW
0x140003da7  test    eax, eax
0x140003da9  jz      loc_140003E72
0x140003daf  mov     rcx, [rdi+rbp*8]; lpString1
0x140003db3  lea     rdx, aS_3; "-s"
0x140003dba  xor     r9d, r9d
0x140003dbd  mov     r8d, r12d
0x140003dc0  call    StringCompareW
0x140003dc5  test    eax, eax
0x140003dc7  jz      loc_140003E72
0x140003dcd  mov     rcx, [rdi+rbp*8]; lpString1
0x140003dd1  lea     rdx, aReg32; "/reg:32"
0x140003dd8  xor     r9d, r9d
0x140003ddb  call    StringCompareExW
0x140003de0  test    eax, eax
0x140003de2  jz      short loc_140003E51
0x140003de4  mov     rcx, [rdi+rbp*8]; lpString1
0x140003de8  lea     rdx, aReg32_0; "-reg:32"
0x140003def  xor     r9d, r9d
0x140003df2  call    StringCompareExW
0x140003df7  test    eax, eax
0x140003df9  jz      short loc_140003E51
0x140003dfb  mov     rcx, [rdi+rbp*8]; lpString1
0x140003dff  lea     rdx, aReg64_0; "/reg:64"
0x140003e06  xor     r9d, r9d
0x140003e09  call    StringCompareExW
0x140003e0e  test    eax, eax
0x140003e10  jz      short loc_140003E2D
0x140003e12  mov     rcx, [rdi+rbp*8]; lpString1
0x140003e16  lea     rdx, aReg64; "-reg:64"
0x140003e1d  xor     r9d, r9d
0x140003e20  call    StringCompareExW
0x140003e25  test    eax, eax
0x140003e27  jnz     loc_140003CD0
0x140003e2d  cmp     dword ptr [rbx+8Ch], 0
0x140003e34  jnz     loc_140003CD0
0x140003e3a  mov     dword ptr [rbx+8Ch], 100h
0x140003e44  mov     dword ptr [r15+8Ch], 100h
0x140003e4f  jmp     short loc_140003E90
0x140003e51  cmp     dword ptr [rbx+8Ch], 0
0x140003e58  jnz     loc_140003CD0
0x140003e5e  mov     eax, 200h
0x140003e63  mov     [rbx+8Ch], eax
0x140003e69  mov     [r15+8Ch], eax
0x140003e70  jmp     short loc_140003E90
0x140003e72  cmp     [rbx+20h], r12d
0x140003e76  jz      loc_140003CD0
0x140003e7c  mov     [rbx+20h], r12d
0x140003e80  jmp     short loc_140003E90
0x140003e82  cmp     [rbx+18h], r12d
0x140003e86  jz      loc_140003CD0
0x140003e8c  mov     [rbx+18h], r12d
0x140003e90  add     r14d, r12d
0x140003e93  cmp     r14d, esi
0x140003e96  jb      loc_140003D58
0x140003e9c  jmp     loc_140003CC8
0x140003ea1  mov     ecx, 57h ; 'W'
0x140003ea6  call    SaveErrorMessage
0x140003eab  xor     eax, eax
0x140003ead  add     rsp, 20h
0x140003eb1  pop     r15
0x140003eb3  pop     r14
0x140003eb5  pop     r12
0x140003eb7  pop     rdi
0x140003eb8  pop     rsi
0x140003eb9  pop     rbp
0x140003eba  pop     rbx
0x140003ebb  retn
```
