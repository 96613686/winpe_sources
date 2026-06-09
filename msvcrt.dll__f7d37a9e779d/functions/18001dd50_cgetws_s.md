# _cgetws_s

- ea: `0x18001dd50`
- end: `0x18001df3f`
- name: `_cgetws_s`
- size: `495`
- prototype: `errno_t __cdecl(wchar_t *Buffer, size_t BufferCount, size_t *SizeRead)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18001dba0`
- `0x18001dcd0`

## callees

- `0x180007e80`
- `0x180007ea8`
- `0x180007f00`
- `0x18001dd50`
- `0x180023ac0`
- `0x18002f050`
- `0x18003e6c0`
- `0x18003e8e0`

## import_xrefs

- `api-ms-win-core-console-l1-1-0!GetConsoleMode` at `0x18001de59`
- `api-ms-win-core-console-l1-1-0!GetConsoleMode` at `0x18001de59`
- `api-ms-win-core-console-l1-1-0!SetConsoleMode` at `0x18001de73`
- `api-ms-win-core-console-l1-1-0!SetConsoleMode` at `0x18001df03`
- `api-ms-win-core-console-l1-1-0!SetConsoleMode` at `0x18001de73`
- `api-ms-win-core-console-l1-1-0!SetConsoleMode` at `0x18001df03`
- `api-ms-win-core-console-l1-1-0!ReadConsoleW` at `0x18001de93`
- `api-ms-win-core-console-l1-1-0!ReadConsoleW` at `0x18001de93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001df0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001df0b`

## pseudocode

```c
errno_t __cdecl cgetws_s(wchar_t *Buffer, size_t BufferCount, size_t *SizeRead)
{
  wchar_t *v5; // rbx
  int v6; // r14d
  size_t v7; // rsi
  size_t v8; // rax
  HANDLE v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rdx
  DWORD LastError; // eax
  DWORD Mode[14]; // [rsp+30h] [rbp-38h] BYREF
  DWORD NumberOfCharsRead; // [rsp+88h] [rbp+20h] BYREF

  v5 = Buffer;
  Mode[0] = 0;
  NumberOfCharsRead = 0;
  if ( !Buffer || !BufferCount || (*Buffer = 0, !SizeRead) )
  {
    *_doserrno() = 0;
    *errno() = 22;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  v6 = 0;
  lock(3);
  v7 = BufferCount - 1;
  *SizeRead = 0;
  if ( _console_wchar_buffer_used && v7 )
  {
    *v5++ = _console_wchar_buffer;
    _console_wchar_buffer = 0;
    v8 = --v7;
    ++*SizeRead;
    if ( !_console_wchar_buffer )
    {
      v7 = 0;
      v8 = 0;
    }
  }
  else
  {
    v8 = v7;
  }
  if ( v8 )
  {
    v9 = coninpfh;
    if ( coninpfh == (HANDLE)-2LL )
    {
      _initconin();
      v9 = coninpfh;
    }
    if ( v9 != (HANDLE)-1LL && GetConsoleMode(v9, Mode) )
    {
      SetConsoleMode(coninpfh, 7u);
      if ( !ReadConsoleW(coninpfh, v5, v7, &NumberOfCharsRead, 0) )
      {
LABEL_26:
        SetConsoleMode(coninpfh, Mode[0]);
        goto LABEL_28;
      }
      v10 = NumberOfCharsRead;
      if ( NumberOfCharsRead >= 2 )
      {
        v11 = NumberOfCharsRead - 2;
        if ( v5[v11] == 13 )
        {
LABEL_21:
          *SizeRead += v11;
          v5[v11] = 0;
          goto LABEL_26;
        }
      }
      if ( NumberOfCharsRead == v7 )
      {
        if ( !NumberOfCharsRead )
          goto LABEL_25;
        v11 = NumberOfCharsRead - 1;
        if ( v5[v11] == 13 )
          goto LABEL_21;
      }
      if ( NumberOfCharsRead == 1 && *v5 == 10 )
      {
        *v5 = 0;
        *SizeRead = *SizeRead;
        goto LABEL_26;
      }
LABEL_25:
      *SizeRead += NumberOfCharsRead;
      v5[v10] = 0;
      goto LABEL_26;
    }
    LastError = GetLastError();
    dosmaperr(LastError);
    v6 = *errno();
  }
LABEL_28:
  unlock(3);
  if ( v6 )
    *errno() = v6;
  return v6;
}

```

## disassembly

```asm
0x18001dd50  mov     rax, rsp
0x18001dd53  push    rbx
0x18001dd54  push    rsi
0x18001dd55  push    rdi
0x18001dd56  push    r14
0x18001dd58  push    r15
0x18001dd5a  sub     rsp, 40h
0x18001dd5e  mov     rdi, r8
0x18001dd61  mov     rsi, rdx
0x18001dd64  mov     rbx, rcx
0x18001dd67  xor     r15d, r15d
0x18001dd6a  mov     [rax-38h], r15d
0x18001dd6e  mov     [rax+20h], r15d
0x18001dd72  test    rcx, rcx
0x18001dd75  jnz     short loc_18001DDAD
0x18001dd77  call    __doserrno
0x18001dd7c  mov     [rax], r15d
0x18001dd7f  call    _errno
0x18001dd84  mov     ebx, 16h
0x18001dd89  mov     [rax], ebx
0x18001dd8b  mov     [rsp+68h+Reserved], r15; Reserved
0x18001dd90  xor     r9d, r9d; LineNo
0x18001dd93  xor     r8d, r8d; FileName
0x18001dd96  xor     edx, edx; FunctionName
0x18001dd98  xor     ecx, ecx; Expression
0x18001dd9a  call    _invalid_parameter
0x18001dd9f  mov     eax, ebx
0x18001dda1  add     rsp, 40h
0x18001dda5  pop     r15
0x18001dda7  pop     r14
0x18001dda9  pop     rdi
0x18001ddaa  pop     rsi
0x18001ddab  pop     rbx
0x18001ddac  retn
0x18001ddad  test    rsi, rsi
0x18001ddb0  jz      short loc_18001DD77
0x18001ddb2  mov     eax, r15d
0x18001ddb5  mov     [rcx], ax
0x18001ddb8  test    rdi, rdi
0x18001ddbb  jz      short loc_18001DD77
0x18001ddbd  mov     r14d, r15d
0x18001ddc0  mov     ecx, 3
0x18001ddc5  call    _lock
0x18001ddca  nop
0x18001ddcb  dec     rsi
0x18001ddce  mov     [rsp+68h+arg_8], rsi
0x18001ddd3  mov     [rdi], r15
0x18001ddd6  cmp     cs:__console_wchar_buffer_used, r15d
0x18001dddd  jz      short loc_18001DE25
0x18001dddf  test    rsi, rsi
0x18001dde2  jz      short loc_18001DE25
0x18001dde4  movzx   eax, cs:__console_wchar_buffer
0x18001ddeb  mov     [rbx], ax
0x18001ddee  add     rbx, 2
0x18001ddf2  mov     [rsp+68h+arg_0], rbx
0x18001ddf7  mov     cs:__console_wchar_buffer, r15w
0x18001ddff  lea     rax, [rsi-1]
0x18001de03  mov     rsi, rax
0x18001de06  mov     [rsp+68h+arg_8], rax
0x18001de0b  inc     qword ptr [rdi]
0x18001de0e  cmp     cs:__console_wchar_buffer, r15w
0x18001de16  jnz     short loc_18001DE28
0x18001de18  mov     rsi, r15
0x18001de1b  mov     [rsp+68h+arg_8], r15
0x18001de20  mov     rax, r15
0x18001de23  jmp     short loc_18001DE28
0x18001de25  mov     rax, rsi
0x18001de28  test    rax, rax
0x18001de2b  jz      loc_18001DF20
0x18001de31  mov     rcx, cs:_coninpfh
0x18001de38  cmp     rcx, 0FFFFFFFFFFFFFFFEh
0x18001de3c  jnz     short loc_18001DE4A
0x18001de3e  call    __initconin
0x18001de43  mov     rcx, cs:_coninpfh; hConsoleHandle
0x18001de4a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001de4e  jz      loc_18001DF0B
0x18001de54  lea     rdx, [rsp+68h+Mode]; lpMode
0x18001de59  call    cs:__imp_GetConsoleMode
0x18001de5f  test    eax, eax
0x18001de61  jz      loc_18001DF0B
0x18001de67  mov     edx, 7; dwMode
0x18001de6c  mov     rcx, cs:_coninpfh; hConsoleHandle
0x18001de73  call    cs:__imp_SetConsoleMode
0x18001de79  mov     [rsp+68h+Reserved], r15; pInputControl
0x18001de7e  lea     r9, [rsp+68h+NumberOfCharsRead]; lpNumberOfCharsRead
0x18001de86  mov     r8d, esi; nNumberOfCharsToRead
0x18001de89  mov     rdx, rbx; lpBuffer
0x18001de8c  mov     rcx, cs:_coninpfh; hConsoleInput
0x18001de93  call    cs:__imp_ReadConsoleW
0x18001de99  test    eax, eax
0x18001de9b  jz      short loc_18001DEF8
0x18001de9d  mov     ecx, [rsp+68h+NumberOfCharsRead]
0x18001dea4  cmp     ecx, 2
0x18001dea7  jb      short loc_18001DEB5
0x18001dea9  lea     eax, [rcx-2]
0x18001deac  mov     edx, eax
0x18001deae  cmp     word ptr [rbx+rax*2], 0Dh
0x18001deb3  jz      short loc_18001DECB
0x18001deb5  cmp     rcx, rsi
0x18001deb8  jnz     short loc_18001DED7
0x18001deba  cmp     ecx, 1
0x18001debd  jb      short loc_18001DEEE
0x18001debf  lea     eax, [rcx-1]
0x18001dec2  mov     edx, eax
0x18001dec4  cmp     word ptr [rbx+rax*2], 0Dh
0x18001dec9  jnz     short loc_18001DED7
0x18001decb  add     [rdi], rdx
0x18001dece  mov     eax, r15d
0x18001ded1  mov     [rbx+rdx*2], ax
0x18001ded5  jmp     short loc_18001DEF8
0x18001ded7  cmp     ecx, 1
0x18001deda  jnz     short loc_18001DEEE
0x18001dedc  cmp     word ptr [rbx], 0Ah
0x18001dee0  jnz     short loc_18001DEEE
0x18001dee2  mov     [rbx], r15w
0x18001dee6  mov     rax, [rdi]
0x18001dee9  mov     [rdi], rax
0x18001deec  jmp     short loc_18001DEF8
0x18001deee  add     [rdi], rcx
0x18001def1  mov     eax, r15d
0x18001def4  mov     [rbx+rcx*2], ax
0x18001def8  mov     edx, [rsp+68h+Mode]; dwMode
0x18001defc  mov     rcx, cs:_coninpfh; hConsoleHandle
0x18001df03  call    cs:__imp_SetConsoleMode
0x18001df09  jmp     short loc_18001DF20
0x18001df0b  call    cs:__imp_GetLastError
0x18001df11  mov     ecx, eax
0x18001df13  call    _dosmaperr
0x18001df18  call    _errno
0x18001df1d  mov     r14d, [rax]
0x18001df20  mov     ecx, 3
0x18001df25  call    _unlock
0x18001df2a  test    r14d, r14d
0x18001df2d  jz      short loc_18001DF37
0x18001df2f  call    _errno
0x18001df34  mov     [rax], r14d
0x18001df37  mov     eax, r14d
0x18001df3a  jmp     loc_18001DDA1
0x18007b82b  push    rbp
0x18007b82d  sub     rsp, 30h
0x18007b831  mov     rbp, rdx
0x18007b834  mov     ecx, 3
0x18007b839  call    _unlock
0x18007b83e  nop
0x18007b83f  add     rsp, 30h
0x18007b843  pop     rbp
0x18007b844  retn
```
