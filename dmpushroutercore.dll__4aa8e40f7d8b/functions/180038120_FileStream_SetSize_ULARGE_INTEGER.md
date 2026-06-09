# FileStream::SetSize(_ULARGE_INTEGER)

- ea: `0x180038120`
- end: `0x180038231`
- name: `?SetSize@FileStream@@UEAAJT_ULARGE_INTEGER@@@Z`
- size: `273`
- prototype: `int(FileStream *__hidden this, union _ULARGE_INTEGER)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180038120`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003818c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800381b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800381dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003820a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003818c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800381b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800381dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003820a`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800381d3`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800381d3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180038166`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800381ae`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800381fb`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180038166`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800381ae`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800381fb`

## pseudocode

```c
__int64 __fastcall FileStream::SetSize(FileStream *this, union _ULARGE_INTEGER a2)
{
  LONG LowPart; // ebx
  signed int v4; // edi
  void *v5; // rcx
  LONG v6; // ebp
  signed int LastError; // eax
  signed int v8; // eax
  signed int v9; // eax
  DWORD v10; // eax
  signed int v11; // eax
  LONG DistanceToMoveHigh; // [rsp+48h] [rbp+10h] BYREF

  LowPart = a2.LowPart;
  if ( a2.HighPart )
  {
    return (unsigned int)-2147287039;
  }
  else
  {
    v5 = (void *)*((_QWORD *)this + 1);
    DistanceToMoveHigh = 0;
    v6 = SetFilePointer(v5, 0, &DistanceToMoveHigh, 1u);
    if ( DistanceToMoveHigh )
    {
      return (unsigned int)-2147287015;
    }
    else
    {
      v4 = 0;
      if ( v6 != -1 )
        goto LABEL_12;
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 >= 0 )
      {
LABEL_12:
        if ( SetFilePointer(*((HANDLE *)this + 1), LowPart, 0, 0) != -1 )
          goto LABEL_23;
        v8 = GetLastError();
        v4 = v8;
        if ( v8 > 0 )
          v4 = (unsigned __int16)v8 | 0x80070000;
        if ( v4 >= 0 )
        {
LABEL_23:
          if ( !SetEndOfFile(*((HANDLE *)this + 1)) )
          {
            v9 = GetLastError();
            v4 = v9;
            if ( v9 > 0 )
              v4 = (unsigned __int16)v9 | 0x80070000;
          }
          v10 = SetFilePointer(*((HANDLE *)this + 1), v6, 0, 0);
          if ( v4 >= 0 && v10 == -1 )
          {
            v11 = GetLastError();
            v4 = v11;
            if ( v11 > 0 )
              return (unsigned __int16)v11 | 0x80070000;
          }
        }
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180038120  mov     [rsp+arg_0], rbx
0x180038125  mov     [rsp+arg_10], rbp
0x18003812a  push    rsi
0x18003812b  push    rdi
0x18003812c  push    r14
0x18003812e  sub     rsp, 20h
0x180038132  mov     rax, rdx
0x180038135  mov     rbx, rdx
0x180038138  shr     rax, 20h
0x18003813c  mov     rsi, rcx
0x18003813f  test    eax, eax
0x180038141  jz      short loc_18003814D
0x180038143  mov     edi, 80030001h
0x180038148  jmp     loc_18003821C
0x18003814d  mov     rcx, [rcx+8]; hFile
0x180038151  lea     r8, [rsp+38h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x180038156  mov     r9d, 1; dwMoveMethod
0x18003815c  mov     [rsp+38h+DistanceToMoveHigh], 0
0x180038164  xor     edx, edx; lDistanceToMove
0x180038166  call    cs:__imp_SetFilePointer
0x18003816c  cmp     [rsp+38h+DistanceToMoveHigh], 0
0x180038171  mov     ebp, eax
0x180038173  jz      short loc_18003817F
0x180038175  mov     edi, 80030019h
0x18003817a  jmp     loc_18003821C
0x18003817f  xor     edi, edi
0x180038181  mov     r14d, 80070000h
0x180038187  cmp     ebp, 0FFFFFFFFh
0x18003818a  jnz     short loc_1800381A2
0x18003818c  call    cs:__imp_GetLastError
0x180038192  mov     edi, eax
0x180038194  test    eax, eax
0x180038196  jle     short loc_18003819E
0x180038198  movzx   edi, ax
0x18003819b  or      edi, r14d
0x18003819e  test    edi, edi
0x1800381a0  js      short loc_18003821C
0x1800381a2  mov     rcx, [rsi+8]; hFile
0x1800381a6  xor     r9d, r9d; dwMoveMethod
0x1800381a9  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800381ac  mov     edx, ebx; lDistanceToMove
0x1800381ae  call    cs:__imp_SetFilePointer
0x1800381b4  cmp     eax, 0FFFFFFFFh
0x1800381b7  jnz     short loc_1800381CF
0x1800381b9  call    cs:__imp_GetLastError
0x1800381bf  mov     edi, eax
0x1800381c1  test    eax, eax
0x1800381c3  jle     short loc_1800381CB
0x1800381c5  movzx   edi, ax
0x1800381c8  or      edi, r14d
0x1800381cb  test    edi, edi
0x1800381cd  js      short loc_18003821C
0x1800381cf  mov     rcx, [rsi+8]; hFile
0x1800381d3  call    cs:__imp_SetEndOfFile
0x1800381d9  test    eax, eax
0x1800381db  jnz     short loc_1800381EF
0x1800381dd  call    cs:__imp_GetLastError
0x1800381e3  mov     edi, eax
0x1800381e5  test    eax, eax
0x1800381e7  jle     short loc_1800381EF
0x1800381e9  movzx   edi, ax
0x1800381ec  or      edi, r14d
0x1800381ef  mov     rcx, [rsi+8]; hFile
0x1800381f3  xor     r9d, r9d; dwMoveMethod
0x1800381f6  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800381f9  mov     edx, ebp; lDistanceToMove
0x1800381fb  call    cs:__imp_SetFilePointer
0x180038201  test    edi, edi
0x180038203  js      short loc_18003821C
0x180038205  cmp     eax, 0FFFFFFFFh
0x180038208  jnz     short loc_18003821C
0x18003820a  call    cs:__imp_GetLastError
0x180038210  mov     edi, eax
0x180038212  test    eax, eax
0x180038214  jle     short loc_18003821C
0x180038216  movzx   edi, ax
0x180038219  or      edi, r14d
0x18003821c  mov     rbx, [rsp+38h+arg_0]
0x180038221  mov     eax, edi
0x180038223  mov     rbp, [rsp+38h+arg_10]
0x180038228  add     rsp, 20h
0x18003822c  pop     r14
0x18003822e  pop     rdi
0x18003822f  pop     rsi
0x180038230  retn
```
