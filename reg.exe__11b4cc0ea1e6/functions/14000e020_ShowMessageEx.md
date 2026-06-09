# ShowMessageEx

- ea: `0x14000e020`
- end: `0x14000e21f`
- name: `ShowMessageEx`
- size: `511`
- prototype: `__int64(FILE *, int, int, const wchar_t *, ...)`
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x140002a28`
- `0x140002bc0`
- `0x1400055f8`
- `0x140005bac`
- `0x140005e84`
- `0x1400094a0`
- `0x140009574`
- `0x14000a3f8`
- `0x14000dc24`

## callees

- `0x140001cd4`
- `0x14000caa8`
- `0x14000dce0`
- `0x14000e020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e0e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e0ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e118`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e12e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e1fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e0e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e0ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e118`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e12e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e1fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e20a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e20a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000e0d4`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000e0d4`

## pseudocode

```c
__int64 ShowMessageEx(FILE *a1, int a2, int a3, const wchar_t *a4, ...)
{
  FILE *v4; // r14
  const WCHAR *v5; // rdx
  DWORD v7; // edi
  unsigned int v8; // esi
  int v9; // eax
  WCHAR *lpBuffer; // rbx
  signed int v11; // ecx
  unsigned int v12; // edi
  wchar_t *InternalTemporaryBuffer; // rax
  size_t v14; // rsi
  int v15; // eax
  va_list Args; // [rsp+40h] [rbp-18h] BYREF
  va_list va; // [rsp+B0h] [rbp+58h] BYREF

  va_start(va, a4);
  Args = 0;
  v4 = a1;
  if ( !a4 || !a1 )
  {
    if ( GetLastError() )
      return 0;
    v11 = 87;
LABEL_40:
    SetLastError(v11);
    return 0;
  }
  if ( a2 )
  {
    if ( a3 )
    {
      v12 = 0;
      while ( 1 )
      {
        va_copy(Args, va);
        if ( !va )
          goto LABEL_20;
        v12 += 2048;
        InternalTemporaryBuffer = (wchar_t *)GetInternalTemporaryBuffer(3, 0, v12, 1);
        lpBuffer = InternalTemporaryBuffer;
        if ( !InternalTemporaryBuffer )
          break;
        if ( v12 )
        {
          if ( v12 > 0x7FFFFFFF )
          {
            LOWORD(v11) = 87;
            *InternalTemporaryBuffer = 0;
            Args = 0;
LABEL_37:
            v11 = (unsigned __int16)v11;
            goto LABEL_40;
          }
          v14 = v12 - 1LL;
          v15 = vsnwprintf(InternalTemporaryBuffer, v14, a4, Args);
          if ( v15 < 0 || v15 > v14 )
          {
            v11 = -2147024774;
            lpBuffer[v14] = 0;
          }
          else
          {
            v11 = 0;
            if ( v15 == v14 )
              lpBuffer[v14] = 0;
          }
        }
        else
        {
          v11 = -2147024809;
        }
        Args = 0;
        if ( v11 != -2147024774 )
        {
          if ( v11 >= 0 )
          {
LABEL_35:
            v5 = lpBuffer;
            a1 = v4;
            return ShowMessage(a1, v5);
          }
          goto LABEL_37;
        }
      }
LABEL_18:
      if ( GetLastError() )
        return 0;
      v11 = 8;
    }
    else
    {
      v7 = -1;
      v8 = 0;
      while ( 1 )
      {
        va_copy(Args, va);
        if ( !va )
          break;
        v9 = 4096;
        if ( v7 != -1 )
          v9 = 2048;
        v8 += v9;
        lpBuffer = (WCHAR *)GetInternalTemporaryBuffer(3, 0, v8, 1);
        if ( !lpBuffer )
          goto LABEL_18;
        v7 = FormatMessageW(0x400u, a4, 0, 0, lpBuffer, v8 - 1, &Args);
        if ( !v7 )
        {
          if ( !GetLastError() )
            return 1;
          if ( GetLastError() != 122 )
            return 0;
        }
        Args = 0;
        if ( v7 )
          goto LABEL_35;
      }
LABEL_20:
      if ( GetLastError() )
        return 0;
      v11 = 1067;
    }
    goto LABEL_40;
  }
  v5 = a4;
  return ShowMessage(a1, v5);
}

```

## disassembly

```asm
0x14000e020  mov     [rsp-30h+lpSource], r9
0x14000e025  push    rbp
0x14000e026  push    rbx
0x14000e027  push    rsi
0x14000e028  push    rdi
0x14000e029  push    r14
0x14000e02b  push    r15
0x14000e02d  mov     rbp, rsp
0x14000e030  sub     rsp, 58h
0x14000e034  mov     [rbp+Args], 0
0x14000e03c  mov     r14, rcx
0x14000e03f  test    r9, r9
0x14000e042  jz      loc_14000E1FD
0x14000e048  test    rcx, rcx
0x14000e04b  jz      loc_14000E1FD
0x14000e051  test    edx, edx
0x14000e053  jnz     short loc_14000E062
0x14000e055  mov     rdx, r9; lpString
0x14000e058  call    ShowMessage
0x14000e05d  jmp     loc_14000E212
0x14000e062  mov     r15d, 800h
0x14000e068  test    r8d, r8d
0x14000e06b  jnz     loc_14000E146
0x14000e071  or      edi, 0FFFFFFFFh
0x14000e074  xor     esi, esi
0x14000e076  lea     rax, [rbp+arg_20]
0x14000e07a  mov     [rbp+Args], rax
0x14000e07e  test    rax, rax
0x14000e081  jz      loc_14000E12E
0x14000e087  mov     eax, 1000h
0x14000e08c  cmp     edi, 0FFFFFFFFh
0x14000e08f  mov     r9d, 1
0x14000e095  cmovnz  eax, r15d
0x14000e099  xor     edx, edx
0x14000e09b  add     esi, eax
0x14000e09d  mov     r8d, esi
0x14000e0a0  lea     ecx, [rdx+3]
0x14000e0a3  call    GetInternalTemporaryBuffer
0x14000e0a8  mov     rbx, rax
0x14000e0ab  test    rax, rax
0x14000e0ae  jz      short loc_14000E118
0x14000e0b0  mov     rdx, [rbp+lpSource]; lpSource
0x14000e0b4  lea     ecx, [rsi-1]
0x14000e0b7  lea     rax, [rbp+Args]
0x14000e0bb  xor     r9d, r9d; dwLanguageId
0x14000e0be  mov     [rsp+58h+Arguments], rax; Arguments
0x14000e0c3  xor     r8d, r8d; dwMessageId
0x14000e0c6  mov     [rsp+58h+nSize], ecx; nSize
0x14000e0ca  mov     ecx, 400h; dwFlags
0x14000e0cf  mov     [rsp+58h+lpBuffer], rbx; lpBuffer
0x14000e0d4  call    cs:__imp_FormatMessageW
0x14000e0da  mov     edi, eax
0x14000e0dc  test    eax, eax
0x14000e0de  jnz     short loc_14000E0F9
0x14000e0e0  call    cs:__imp_GetLastError
0x14000e0e6  test    eax, eax
0x14000e0e8  jz      short loc_14000E10E
0x14000e0ea  call    cs:__imp_GetLastError
0x14000e0f0  cmp     eax, 7Ah ; 'z'
0x14000e0f3  jnz     loc_14000E210
0x14000e0f9  mov     [rbp+Args], 0
0x14000e101  test    edi, edi
0x14000e103  jz      loc_14000E076
0x14000e109  jmp     loc_14000E1DF
0x14000e10e  mov     eax, 1
0x14000e113  jmp     loc_14000E212
0x14000e118  call    cs:__imp_GetLastError
0x14000e11e  test    eax, eax
0x14000e120  jnz     loc_14000E210
0x14000e126  lea     ecx, [rax+8]
0x14000e129  jmp     loc_14000E20A
0x14000e12e  call    cs:__imp_GetLastError
0x14000e134  test    eax, eax
0x14000e136  jnz     loc_14000E210
0x14000e13c  mov     ecx, 42Bh
0x14000e141  jmp     loc_14000E20A
0x14000e146  xor     edi, edi
0x14000e148  lea     rax, [rbp+arg_20]
0x14000e14c  mov     [rbp+Args], rax
0x14000e150  test    rax, rax
0x14000e153  jz      short loc_14000E12E
0x14000e155  xor     edx, edx
0x14000e157  add     edi, r15d
0x14000e15a  mov     r9d, 1
0x14000e160  mov     r8d, edi
0x14000e163  lea     ecx, [rdx+3]
0x14000e166  call    GetInternalTemporaryBuffer
0x14000e16b  mov     rbx, rax
0x14000e16e  test    rax, rax
0x14000e171  jz      short loc_14000E118
0x14000e173  test    edi, edi
0x14000e175  jz      short loc_14000E1BE
0x14000e177  cmp     edi, 7FFFFFFFh
0x14000e17d  ja      short loc_14000E1EA
0x14000e17f  mov     r9, [rbp+Args]; Args
0x14000e183  mov     rcx, rax; Buffer
0x14000e186  mov     r8, [rbp+lpSource]; Format
0x14000e18a  mov     esi, edi
0x14000e18c  dec     rsi
0x14000e18f  mov     rdx, rsi; BufferCount
0x14000e192  call    _vsnwprintf
0x14000e197  test    eax, eax
0x14000e199  js      short loc_14000E1B1
0x14000e19b  cdqe
0x14000e19d  cmp     rax, rsi
0x14000e1a0  ja      short loc_14000E1B1
0x14000e1a2  xor     ecx, ecx
0x14000e1a4  cmp     rax, rsi
0x14000e1a7  jnz     short loc_14000E1C7
0x14000e1a9  xor     eax, eax
0x14000e1ab  mov     [rbx+rsi*2], ax
0x14000e1af  jmp     short loc_14000E1C7
0x14000e1b1  xor     eax, eax
0x14000e1b3  mov     ecx, 8007007Ah
0x14000e1b8  mov     [rbx+rsi*2], ax
0x14000e1bc  jmp     short loc_14000E1C7
0x14000e1be  mov     ecx, 80070057h
0x14000e1c3  test    edi, edi
0x14000e1c5  jnz     short loc_14000E1EF
0x14000e1c7  mov     [rbp+Args], 0
0x14000e1cf  cmp     ecx, 8007007Ah
0x14000e1d5  jz      loc_14000E148
0x14000e1db  test    ecx, ecx
0x14000e1dd  js      short loc_14000E1F8
0x14000e1df  mov     rdx, rbx
0x14000e1e2  mov     rcx, r14
0x14000e1e5  jmp     loc_14000E058
0x14000e1ea  mov     ecx, 80070057h
0x14000e1ef  xor     eax, eax
0x14000e1f1  mov     [rbx], ax
0x14000e1f4  mov     [rbp+Args], rax
0x14000e1f8  movzx   ecx, cx
0x14000e1fb  jmp     short loc_14000E20A
0x14000e1fd  call    cs:__imp_GetLastError
0x14000e203  test    eax, eax
0x14000e205  jnz     short loc_14000E210
0x14000e207  lea     ecx, [rax+57h]; dwErrCode
0x14000e20a  call    cs:__imp_SetLastError
0x14000e210  xor     eax, eax
0x14000e212  add     rsp, 58h
0x14000e216  pop     r15
0x14000e218  pop     r14
0x14000e21a  pop     rdi
0x14000e21b  pop     rsi
0x14000e21c  pop     rbx
0x14000e21d  pop     rbp
0x14000e21e  retn
```
