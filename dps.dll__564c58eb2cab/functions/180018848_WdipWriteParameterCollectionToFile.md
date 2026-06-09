# WdipWriteParameterCollectionToFile

- ea: `0x180018848`
- end: `0x180018aa8`
- name: `WdipWriteParameterCollectionToFile`
- size: `608`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013e68`

## callees

- `0x180009090`
- `0x180017a60`
- `0x1800180f4`
- `0x180018848`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800188cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018993`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800189cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800188cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018993`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800189cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a55`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800188bc`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180018989`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800189c1`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180018a47`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800188bc`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180018989`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800189c1`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180018a47`

## string_xrefs

- `0x180018a86`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x180018a7f`: `WdipWriteParameterCollectionToFile`

## pseudocode

```c
__int64 __fastcall WdipWriteParameterCollectionToFile(__int64 a1, void *a2)
{
  signed int v4; // ebx
  int v5; // r8d
  signed int LastError; // eax
  int v7; // eax
  int v8; // eax
  __int64 i; // rbx
  __int64 v10; // rcx
  signed int v11; // eax
  signed int v12; // eax
  signed int v13; // eax
  int Args; // [rsp+20h] [rbp-30h]
  union _LARGE_INTEGER NewFilePointer; // [rsp+38h] [rbp-18h] BYREF
  LARGE_INTEGER v17; // [rsp+40h] [rbp-10h] BYREF
  int Buffer; // [rsp+80h] [rbp+30h] BYREF
  int v19; // [rsp+90h] [rbp+40h] BYREF
  int v20; // [rsp+98h] [rbp+48h] BYREF

  v19 = 0;
  v20 = 0;
  Buffer = 0;
  NewFilePointer.QuadPart = 0;
  v17.QuadPart = 0;
  if ( !a1 )
  {
    v4 = -2147024809;
    Args = 87;
    v5 = 1115;
LABEL_37:
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (__int64)L"WdipWriteParameterCollectionToFile",
      v5,
      (const wchar_t *)L"Error = %d",
      Args);
    return (unsigned int)v4;
  }
  if ( !SetFilePointerEx(a2, 0, &NewFilePointer, 1u) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
      v5 = 1125;
LABEL_35:
      v8 = (unsigned __int16)v4;
      goto LABEL_36;
    }
  }
  v7 = WdipWriteFile(a2, (char *)&Buffer, 4u, &v19);
  v4 = v7;
  if ( v7 < 0 )
  {
    v5 = 1133;
    Args = (unsigned __int16)v7;
    goto LABEL_37;
  }
  v8 = WdipWriteFile(a2, (char *)&v20, 4u, &v19);
  v4 = v8;
  if ( v8 < 0 )
  {
    v8 = (unsigned __int16)v8;
    v5 = 1141;
LABEL_36:
    Args = v8;
    goto LABEL_37;
  }
  for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 4); Buffer += *(_DWORD *)(v10 + 32) )
  {
    if ( (int)WdipWriteParameterToFile(*(void **)(*(_QWORD *)(a1 + 8) + 8 * i), a2) < 0 )
      break;
    ++v20;
    v10 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * i);
    i = (unsigned int)(i + 1);
  }
  if ( !SetFilePointerEx(a2, 0, &v17, 1u) )
  {
    v11 = GetLastError();
    v4 = v11;
    if ( v11 > 0 )
      v4 = (unsigned __int16)v11 | 0x80070000;
    if ( v4 < 0 )
    {
      v5 = 1162;
      goto LABEL_35;
    }
  }
  if ( !SetFilePointerEx(a2, NewFilePointer, 0, 0) )
  {
    v12 = GetLastError();
    v4 = v12;
    if ( v12 > 0 )
      v4 = (unsigned __int16)v12 | 0x80070000;
    if ( v4 < 0 )
    {
      v5 = 1169;
      goto LABEL_35;
    }
  }
  v8 = WdipWriteFile(a2, (char *)&Buffer, 4u, &v19);
  v4 = v8;
  if ( v8 < 0 )
  {
    v8 = (unsigned __int16)v8;
    v5 = 1177;
    goto LABEL_36;
  }
  v8 = WdipWriteFile(a2, (char *)&v20, 4u, &v19);
  v4 = v8;
  if ( v8 < 0 )
  {
    v8 = (unsigned __int16)v8;
    v5 = 1185;
    goto LABEL_36;
  }
  if ( SetFilePointerEx(a2, v17, 0, 0) )
  {
    return 0;
  }
  else
  {
    v13 = GetLastError();
    v4 = v13;
    if ( v13 > 0 )
      v4 = (unsigned __int16)v13 | 0x80070000;
    if ( v4 < 0 )
    {
      v5 = 1195;
      goto LABEL_35;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180018848  mov     [rsp-28h+arg_8], rbx
0x18001884d  push    rbp
0x18001884e  push    rsi
0x18001884f  push    rdi
0x180018850  push    r12
0x180018852  push    r14
0x180018854  mov     rbp, rsp
0x180018857  sub     rsp, 50h
0x18001885b  mov     [rbp+arg_10], 0
0x180018862  mov     rdi, rdx
0x180018865  mov     [rbp+arg_18], 0
0x18001886c  mov     rsi, rcx
0x18001886f  mov     [rbp+Buffer], 0
0x180018876  mov     qword ptr [rbp+liDistanceToMove], 0
0x18001887e  mov     qword ptr [rbp+NewFilePointer], 0
0x180018886  mov     qword ptr [rbp+var_10], 0
0x18001888e  test    rcx, rcx
0x180018891  jnz     short loc_1800188AB
0x180018893  mov     ebx, 80070057h
0x180018898  mov     dword ptr [rsp+50h+Args], 57h ; 'W'
0x1800188a0  mov     r8d, 45Bh
0x1800188a6  jmp     loc_180018A78
0x1800188ab  mov     rdx, qword ptr [rbp+liDistanceToMove]; liDistanceToMove
0x1800188af  lea     r8, [rbp+NewFilePointer]; lpNewFilePointer
0x1800188b3  mov     r9d, 1; dwMoveMethod
0x1800188b9  mov     rcx, rdi; hFile
0x1800188bc  call    cs:__imp_SetFilePointerEx
0x1800188c2  mov     r12d, 80070000h
0x1800188c8  test    eax, eax
0x1800188ca  jnz     short loc_1800188ED
0x1800188cc  call    cs:__imp_GetLastError
0x1800188d2  mov     ebx, eax
0x1800188d4  test    eax, eax
0x1800188d6  jle     short loc_1800188DE
0x1800188d8  movzx   ebx, ax
0x1800188db  or      ebx, r12d
0x1800188de  test    ebx, ebx
0x1800188e0  jns     short loc_1800188ED
0x1800188e2  mov     r8d, 465h
0x1800188e8  jmp     loc_180018A71
0x1800188ed  lea     r9, [rbp+arg_10]
0x1800188f1  mov     r8d, 4; nNumberOfBytesToWrite
0x1800188f7  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800188fb  mov     rcx, rdi; hFile
0x1800188fe  call    WdipWriteFile
0x180018903  mov     ebx, eax
0x180018905  test    eax, eax
0x180018907  jns     short loc_18001891B
0x180018909  movzx   ecx, ax
0x18001890c  mov     r8d, 46Dh
0x180018912  mov     dword ptr [rsp+50h+Args], ecx
0x180018916  jmp     loc_180018A78
0x18001891b  lea     r9, [rbp+arg_10]
0x18001891f  mov     r8d, 4; nNumberOfBytesToWrite
0x180018925  lea     rdx, [rbp+arg_18]; lpBuffer
0x180018929  mov     rcx, rdi; hFile
0x18001892c  call    WdipWriteFile
0x180018931  mov     ebx, eax
0x180018933  test    eax, eax
0x180018935  jns     short loc_180018945
0x180018937  movzx   eax, ax
0x18001893a  mov     r8d, 475h
0x180018940  jmp     loc_180018A74
0x180018945  xor     ebx, ebx
0x180018947  cmp     [rsi+4], ebx
0x18001894a  jbe     short loc_180018978
0x18001894c  mov     rcx, [rsi+8]
0x180018950  mov     rdx, rdi; hFile
0x180018953  mov     rcx, [rcx+rbx*8]; lpBuffer
0x180018957  call    ?WdipWriteParameterToFile@@YAJPEAU__WDIP_PARAMETER@@PEAX@Z; WdipWriteParameterToFile(__WDIP_PARAMETER *,void *)
0x18001895c  test    eax, eax
0x18001895e  js      short loc_180018978
0x180018960  inc     [rbp+arg_18]
0x180018963  mov     rax, [rsi+8]
0x180018967  mov     rcx, [rax+rbx*8]
0x18001896b  inc     ebx
0x18001896d  mov     eax, [rcx+20h]
0x180018970  add     [rbp+Buffer], eax
0x180018973  cmp     ebx, [rsi+4]
0x180018976  jb      short loc_18001894C
0x180018978  mov     rdx, qword ptr [rbp+liDistanceToMove]; liDistanceToMove
0x18001897c  lea     r8, [rbp+var_10]; lpNewFilePointer
0x180018980  mov     r9d, 1; dwMoveMethod
0x180018986  mov     rcx, rdi; hFile
0x180018989  call    cs:__imp_SetFilePointerEx
0x18001898f  test    eax, eax
0x180018991  jnz     short loc_1800189B4
0x180018993  call    cs:__imp_GetLastError
0x180018999  mov     ebx, eax
0x18001899b  test    eax, eax
0x18001899d  jle     short loc_1800189A5
0x18001899f  movzx   ebx, ax
0x1800189a2  or      ebx, r12d
0x1800189a5  test    ebx, ebx
0x1800189a7  jns     short loc_1800189B4
0x1800189a9  mov     r8d, 48Ah
0x1800189af  jmp     loc_180018A71
0x1800189b4  mov     rdx, qword ptr [rbp+NewFilePointer]; liDistanceToMove
0x1800189b8  xor     r9d, r9d; dwMoveMethod
0x1800189bb  xor     r8d, r8d; lpNewFilePointer
0x1800189be  mov     rcx, rdi; hFile
0x1800189c1  call    cs:__imp_SetFilePointerEx
0x1800189c7  test    eax, eax
0x1800189c9  jnz     short loc_1800189EC
0x1800189cb  call    cs:__imp_GetLastError
0x1800189d1  mov     ebx, eax
0x1800189d3  test    eax, eax
0x1800189d5  jle     short loc_1800189DD
0x1800189d7  movzx   ebx, ax
0x1800189da  or      ebx, r12d
0x1800189dd  test    ebx, ebx
0x1800189df  jns     short loc_1800189EC
0x1800189e1  mov     r8d, 491h
0x1800189e7  jmp     loc_180018A71
0x1800189ec  lea     r9, [rbp+arg_10]
0x1800189f0  mov     r8d, 4; nNumberOfBytesToWrite
0x1800189f6  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800189fa  mov     rcx, rdi; hFile
0x1800189fd  call    WdipWriteFile
0x180018a02  mov     ebx, eax
0x180018a04  test    eax, eax
0x180018a06  jns     short loc_180018A13
0x180018a08  movzx   eax, ax
0x180018a0b  mov     r8d, 499h
0x180018a11  jmp     short loc_180018A74
0x180018a13  lea     r9, [rbp+arg_10]
0x180018a17  mov     r8d, 4; nNumberOfBytesToWrite
0x180018a1d  lea     rdx, [rbp+arg_18]; lpBuffer
0x180018a21  mov     rcx, rdi; hFile
0x180018a24  call    WdipWriteFile
0x180018a29  mov     ebx, eax
0x180018a2b  test    eax, eax
0x180018a2d  jns     short loc_180018A3A
0x180018a2f  movzx   eax, ax
0x180018a32  mov     r8d, 4A1h
0x180018a38  jmp     short loc_180018A74
0x180018a3a  mov     rdx, qword ptr [rbp+var_10]; liDistanceToMove
0x180018a3e  xor     r9d, r9d; dwMoveMethod
0x180018a41  xor     r8d, r8d; lpNewFilePointer
0x180018a44  mov     rcx, rdi; hFile
0x180018a47  call    cs:__imp_SetFilePointerEx
0x180018a4d  test    eax, eax
0x180018a4f  jz      short loc_180018A55
0x180018a51  xor     ebx, ebx
0x180018a53  jmp     short loc_180018A92
0x180018a55  call    cs:__imp_GetLastError
0x180018a5b  mov     ebx, eax
0x180018a5d  test    eax, eax
0x180018a5f  jle     short loc_180018A67
0x180018a61  movzx   ebx, ax
0x180018a64  or      ebx, r12d
0x180018a67  test    ebx, ebx
0x180018a69  jns     short loc_180018A92
0x180018a6b  mov     r8d, 4ABh; int
0x180018a71  movzx   eax, bx
0x180018a74  mov     dword ptr [rsp+50h+Args], eax; Args
0x180018a78  lea     r9, aErrorD; "Error = %d"
0x180018a7f  lea     rdx, aWdipwriteparam; "WdipWriteParameterCollectionToFile"
0x180018a86  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180018a8d  call    WdipTraceError
0x180018a92  mov     eax, ebx
0x180018a94  mov     rbx, [rsp+50h+arg_8]
0x180018a9c  add     rsp, 50h
0x180018aa0  pop     r14
0x180018aa2  pop     r12
0x180018aa4  pop     rdi
0x180018aa5  pop     rsi
0x180018aa6  pop     rbp
0x180018aa7  retn
```
