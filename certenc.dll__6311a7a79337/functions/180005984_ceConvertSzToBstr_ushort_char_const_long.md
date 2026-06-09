# ceConvertSzToBstr(ushort * *,char const *,long)

- ea: `0x180005984`
- end: `0x180005a45`
- name: `?ceConvertSzToBstr@@YAHPEAPEAGPEBDJ@Z`
- size: `193`
- prototype: `int(unsigned __int16 **, const char *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002f20`
- `0x180007eb0`

## callees

- `0x180005984`
- `0x1800064e0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800059cc`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800059cc`
- `OLEAUT32!__imp_SysFreeString` at `0x180005a09`
- `OLEAUT32!__imp_SysFreeString` at `0x180005a09`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800059f3`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800059f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a15`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x1800059b7`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x1800059da`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x1800059b7`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x1800059da`

## pseudocode

```c
_BOOL8 __fastcall ceConvertSzToBstr(unsigned __int16 **a1, const char *a2)
{
  WCHAR *lpWideCharStr; // rdi
  unsigned __int64 v4; // rbx
  DWORD v6; // ebx
  UINT ACP; // eax
  signed int i; // eax
  UINT v9; // eax
  int cchWideChar; // esi

  lpWideCharStr = 0;
  *a1 = 0;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  if ( v4 <= 0x61A8000 )
  {
    ACP = GetACP();
    for ( i = MultiByteToWideChar(ACP, 0, a2, v4, 0, 0);
          ;
          i = MultiByteToWideChar(v9, 0, a2, v4, lpWideCharStr, cchWideChar) )
    {
      cchWideChar = i;
      if ( i <= 0 )
      {
        v6 = ceHLastError();
        goto LABEL_11;
      }
      if ( lpWideCharStr )
        break;
      lpWideCharStr = SysAllocStringLen(0, i);
      if ( !lpWideCharStr )
      {
        v6 = -2147024882;
        goto LABEL_11;
      }
      v9 = GetACP();
    }
    lpWideCharStr[i] = 0;
    *a1 = lpWideCharStr;
    lpWideCharStr = 0;
    v6 = 0;
  }
  else
  {
    v6 = -2147024362;
  }
LABEL_11:
  SysFreeString(lpWideCharStr);
  if ( v6 )
    SetLastError(v6);
  return v6 == 0;
}

```

## disassembly

```asm
0x180005984  push    rbx
0x180005986  push    rbp
0x180005987  push    rsi
0x180005988  push    rdi
0x180005989  push    r14
0x18000598b  sub     rsp, 30h
0x18000598f  xor     edi, edi
0x180005991  mov     rbp, rdx
0x180005994  mov     [rcx], rdi
0x180005997  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000599b  mov     r14, rcx
0x18000599e  inc     rbx
0x1800059a1  cmp     [rbx+rdx], dil
0x1800059a5  jnz     short loc_18000599E
0x1800059a7  cmp     rbx, 61A8000h
0x1800059ae  jbe     short loc_1800059B7
0x1800059b0  mov     ebx, 80070216h
0x1800059b5  jmp     short loc_180005A06
0x1800059b7  call    cs:__imp_GetACP
0x1800059bd  mov     [rsp+58h+cchWideChar], edi
0x1800059c1  jmp     short loc_1800059E4
0x1800059c3  test    rdi, rdi
0x1800059c6  jnz     short loc_180005A34
0x1800059c8  mov     edx, esi; ui
0x1800059ca  xor     ecx, ecx; strIn
0x1800059cc  call    cs:__imp_SysAllocStringLen
0x1800059d2  mov     rdi, rax
0x1800059d5  test    rax, rax
0x1800059d8  jz      short loc_180005A2D
0x1800059da  call    cs:__imp_GetACP
0x1800059e0  mov     [rsp+58h+cchWideChar], esi; cchWideChar
0x1800059e4  mov     r9d, ebx; cbMultiByte
0x1800059e7  mov     [rsp+58h+lpWideCharStr], rdi; lpWideCharStr
0x1800059ec  mov     r8, rbp; lpMultiByteStr
0x1800059ef  xor     edx, edx; dwFlags
0x1800059f1  mov     ecx, eax; CodePage
0x1800059f3  call    cs:__imp_MultiByteToWideChar
0x1800059f9  mov     esi, eax
0x1800059fb  test    eax, eax
0x1800059fd  jg      short loc_1800059C3
0x1800059ff  call    ?ceHLastError@@YAJXZ; ceHLastError(void)
0x180005a04  mov     ebx, eax
0x180005a06  mov     rcx, rdi; bstrString
0x180005a09  call    cs:__imp_SysFreeString
0x180005a0f  test    ebx, ebx
0x180005a11  jz      short loc_180005A1B
0x180005a13  mov     ecx, ebx; dwErrCode
0x180005a15  call    cs:__imp_SetLastError
0x180005a1b  xor     eax, eax
0x180005a1d  test    ebx, ebx
0x180005a1f  setz    al
0x180005a22  add     rsp, 30h
0x180005a26  pop     r14
0x180005a28  pop     rdi
0x180005a29  pop     rsi
0x180005a2a  pop     rbp
0x180005a2b  pop     rbx
0x180005a2c  retn
0x180005a2d  mov     ebx, 8007000Eh
0x180005a32  jmp     short loc_180005A06
0x180005a34  xor     eax, eax
0x180005a36  mov     ecx, esi
0x180005a38  mov     [rdi+rcx*2], ax
0x180005a3c  mov     [r14], rdi
0x180005a3f  xor     edi, edi
0x180005a41  xor     ebx, ebx
0x180005a43  jmp     short loc_180005A06
```
