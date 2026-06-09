# ShowMessageEx

- ea: `0x14000ec2c`
- end: `0x14000ee56`
- name: `ShowMessageEx`
- size: `554`
- prototype: `__int64(_QWORD, _QWORD, _QWORD, _QWORD, ...)`
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x140002b6c`
- `0x140002d40`
- `0x140005910`
- `0x140005ef0`
- `0x1400061e4`
- `0x140009a50`
- `0x140009b2c`
- `0x14000aa4c`
- `0x14000e798`

## callees

- `0x140001cd4`
- `0x14000d3e8`
- `0x14000e864`
- `0x14000ec2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ecf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ed02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ed36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ed52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ee27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ecf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ed02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ed36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ed52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ee27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ee3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ee3a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000ece0`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000ece0`

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
        InternalTemporaryBuffer = (wchar_t *)GetInternalTemporaryBuffer(3u, 0, v12, 1);
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
        lpBuffer = (WCHAR *)GetInternalTemporaryBuffer(3u, 0, v8, 1);
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
0x14000ec2c  mov     [rsp-30h+lpSource], r9
0x14000ec31  push    rbp
0x14000ec32  push    rbx
0x14000ec33  push    rsi
0x14000ec34  push    rdi
0x14000ec35  push    r14
0x14000ec37  push    r15
0x14000ec39  mov     rbp, rsp
0x14000ec3c  sub     rsp, 58h
0x14000ec40  mov     [rbp+Args], 0
0x14000ec48  mov     r14, rcx
0x14000ec4b  test    r9, r9
0x14000ec4e  jz      loc_14000EE27
0x14000ec54  test    rcx, rcx
0x14000ec57  jz      loc_14000EE27
0x14000ec5d  test    edx, edx
0x14000ec5f  jnz     short loc_14000EC6E
0x14000ec61  mov     rdx, r9; lpString
0x14000ec64  call    ShowMessage
0x14000ec69  jmp     loc_14000EE48
0x14000ec6e  mov     r15d, 800h
0x14000ec74  test    r8d, r8d
0x14000ec77  jnz     loc_14000ED70
0x14000ec7d  or      edi, 0FFFFFFFFh
0x14000ec80  xor     esi, esi
0x14000ec82  lea     rax, [rbp+arg_20]
0x14000ec86  mov     [rbp+Args], rax
0x14000ec8a  test    rax, rax
0x14000ec8d  jz      loc_14000ED52
0x14000ec93  mov     eax, 1000h
0x14000ec98  cmp     edi, 0FFFFFFFFh
0x14000ec9b  mov     r9d, 1
0x14000eca1  cmovnz  eax, r15d
0x14000eca5  xor     edx, edx
0x14000eca7  add     esi, eax
0x14000eca9  mov     r8d, esi
0x14000ecac  lea     ecx, [rdx+3]
0x14000ecaf  call    GetInternalTemporaryBuffer
0x14000ecb4  mov     rbx, rax
0x14000ecb7  test    rax, rax
0x14000ecba  jz      short loc_14000ED36
0x14000ecbc  mov     rdx, [rbp+lpSource]; lpSource
0x14000ecc0  lea     ecx, [rsi-1]
0x14000ecc3  lea     rax, [rbp+Args]
0x14000ecc7  xor     r9d, r9d; dwLanguageId
0x14000ecca  mov     [rsp+58h+Arguments], rax; Arguments
0x14000eccf  xor     r8d, r8d; dwMessageId
0x14000ecd2  mov     [rsp+58h+nSize], ecx; nSize
0x14000ecd6  mov     ecx, 400h; dwFlags
0x14000ecdb  mov     [rsp+58h+lpBuffer], rbx; lpBuffer
0x14000ece0  call    cs:__imp_FormatMessageW
0x14000ece7  nop     dword ptr [rax+rax+00h]
0x14000ecec  mov     edi, eax
0x14000ecee  test    eax, eax
0x14000ecf0  jnz     short loc_14000ED17
0x14000ecf2  call    cs:__imp_GetLastError
0x14000ecf9  nop     dword ptr [rax+rax+00h]
0x14000ecfe  test    eax, eax
0x14000ed00  jz      short loc_14000ED2C
0x14000ed02  call    cs:__imp_GetLastError
0x14000ed09  nop     dword ptr [rax+rax+00h]
0x14000ed0e  cmp     eax, 7Ah ; 'z'
0x14000ed11  jnz     loc_14000EE46
0x14000ed17  mov     [rbp+Args], 0
0x14000ed1f  test    edi, edi
0x14000ed21  jz      loc_14000EC82
0x14000ed27  jmp     loc_14000EE09
0x14000ed2c  mov     eax, 1
0x14000ed31  jmp     loc_14000EE48
0x14000ed36  call    cs:__imp_GetLastError
0x14000ed3d  nop     dword ptr [rax+rax+00h]
0x14000ed42  test    eax, eax
0x14000ed44  jnz     loc_14000EE46
0x14000ed4a  lea     ecx, [rax+8]
0x14000ed4d  jmp     loc_14000EE3A
0x14000ed52  call    cs:__imp_GetLastError
0x14000ed59  nop     dword ptr [rax+rax+00h]
0x14000ed5e  test    eax, eax
0x14000ed60  jnz     loc_14000EE46
0x14000ed66  mov     ecx, 42Bh
0x14000ed6b  jmp     loc_14000EE3A
0x14000ed70  xor     edi, edi
0x14000ed72  lea     rax, [rbp+arg_20]
0x14000ed76  mov     [rbp+Args], rax
0x14000ed7a  test    rax, rax
0x14000ed7d  jz      short loc_14000ED52
0x14000ed7f  xor     edx, edx
0x14000ed81  add     edi, r15d
0x14000ed84  mov     r9d, 1
0x14000ed8a  mov     r8d, edi
0x14000ed8d  lea     ecx, [rdx+3]
0x14000ed90  call    GetInternalTemporaryBuffer
0x14000ed95  mov     rbx, rax
0x14000ed98  test    rax, rax
0x14000ed9b  jz      short loc_14000ED36
0x14000ed9d  test    edi, edi
0x14000ed9f  jz      short loc_14000EDE8
0x14000eda1  cmp     edi, 7FFFFFFFh
0x14000eda7  ja      short loc_14000EE14
0x14000eda9  mov     r9, [rbp+Args]; Args
0x14000edad  mov     rcx, rax; Buffer
0x14000edb0  mov     r8, [rbp+lpSource]; Format
0x14000edb4  mov     esi, edi
0x14000edb6  dec     rsi
0x14000edb9  mov     rdx, rsi; BufferCount
0x14000edbc  call    _vsnwprintf
0x14000edc1  test    eax, eax
0x14000edc3  js      short loc_14000EDDB
0x14000edc5  cdqe
0x14000edc7  cmp     rax, rsi
0x14000edca  ja      short loc_14000EDDB
0x14000edcc  xor     ecx, ecx
0x14000edce  cmp     rax, rsi
0x14000edd1  jnz     short loc_14000EDF1
0x14000edd3  xor     eax, eax
0x14000edd5  mov     [rbx+rsi*2], ax
0x14000edd9  jmp     short loc_14000EDF1
0x14000eddb  xor     eax, eax
0x14000eddd  mov     ecx, 8007007Ah
0x14000ede2  mov     [rbx+rsi*2], ax
0x14000ede6  jmp     short loc_14000EDF1
0x14000ede8  mov     ecx, 80070057h
0x14000eded  test    edi, edi
0x14000edef  jnz     short loc_14000EE19
0x14000edf1  mov     [rbp+Args], 0
0x14000edf9  cmp     ecx, 8007007Ah
0x14000edff  jz      loc_14000ED72
0x14000ee05  test    ecx, ecx
0x14000ee07  js      short loc_14000EE22
0x14000ee09  mov     rdx, rbx
0x14000ee0c  mov     rcx, r14
0x14000ee0f  jmp     loc_14000EC64
0x14000ee14  mov     ecx, 80070057h
0x14000ee19  xor     eax, eax
0x14000ee1b  mov     [rbx], ax
0x14000ee1e  mov     [rbp+Args], rax
0x14000ee22  movzx   ecx, cx
0x14000ee25  jmp     short loc_14000EE3A
0x14000ee27  call    cs:__imp_GetLastError
0x14000ee2e  nop     dword ptr [rax+rax+00h]
0x14000ee33  test    eax, eax
0x14000ee35  jnz     short loc_14000EE46
0x14000ee37  lea     ecx, [rax+57h]; dwErrCode
0x14000ee3a  call    cs:__imp_SetLastError
0x14000ee41  nop     dword ptr [rax+rax+00h]
0x14000ee46  xor     eax, eax
0x14000ee48  add     rsp, 58h
0x14000ee4c  pop     r15
0x14000ee4e  pop     r14
0x14000ee50  pop     rdi
0x14000ee51  pop     rsi
0x14000ee52  pop     rbx
0x14000ee53  pop     rbp
0x14000ee54  retn
```
