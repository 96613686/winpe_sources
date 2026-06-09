# Windows::Isolation::Implementation::Rtl::CopyFile(Windows::Isolation::Implementation::Rtl::CWin32FullPath const &,Windows::Isolation::Implementation::Rtl::CWin32FullPath const &,bool)

- ea: `0x18001fd88`
- end: `0x18001feb8`
- name: `?CopyFile@Rtl@Implementation@Isolation@Windows@@YA?AU_WIN32_FUNCTION_RETURN_STATUS@@AEBVCWin32FullPath@1234@0_N@Z`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180020960`

## callees

- `0x1800069e5`
- `0x18001fd88`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileA` at `0x18001fe2c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileA` at `0x18001fe2c`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18001fe96`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18001fe96`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fdc1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fdec`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fe19`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fe55`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fe83`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fdc1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fdec`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fe19`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fe55`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fe83`

## pseudocode

```c
__int64 __fastcall Windows::Isolation::Implementation::Rtl::CopyFile(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rdi
  const CHAR *v7; // rdi
  __int64 v8; // rbx
  BOOL v9; // eax
  __int64 v10; // rdi
  const WCHAR *v11; // rdi
  __int64 v12; // rbx

  *(_OWORD *)a1 = 0;
  if ( *(_DWORD *)(a2 + 56) != *(_DWORD *)(a3 + 56) )
    RaiseException(0xC00000E5, 1u, 0, 0);
  if ( *(_DWORD *)(a2 + 56) == 1 )
  {
    if ( *(_DWORD *)(a3 + 56) == 1 )
    {
      v6 = a3 + 48;
      if ( *(_QWORD *)v6 )
      {
LABEL_9:
        v7 = *(const CHAR **)(*(_QWORD *)v6 + 16LL);
        if ( *(_DWORD *)(a2 + 56) == 1 )
        {
          v8 = a2 + 48;
          if ( *(_QWORD *)v8 )
            goto LABEL_14;
        }
        else
        {
          v8 = a2 + 48;
        }
        RaiseException(0xC00000E5, 1u, 0, 0);
LABEL_14:
        v9 = CopyFileA(*(LPCSTR *)(*(_QWORD *)v8 + 16LL), v7, 0);
        goto LABEL_26;
      }
    }
    else
    {
      v6 = a3 + 48;
    }
    RaiseException(0xC00000E5, 1u, 0, 0);
    goto LABEL_9;
  }
  if ( *(_DWORD *)(a3 + 56) != 2 )
  {
    v10 = a3 + 48;
    goto LABEL_19;
  }
  v10 = a3 + 48;
  if ( !*(_QWORD *)v10 )
LABEL_19:
    RaiseException(0xC00000E5, 1u, 0, 0);
  v11 = *(const WCHAR **)(*(_QWORD *)v10 + 16LL);
  if ( *(_DWORD *)(a2 + 56) == 2 )
  {
    v12 = a2 + 48;
    if ( *(_QWORD *)v12 )
      goto LABEL_25;
  }
  else
  {
    v12 = a2 + 48;
  }
  RaiseException(0xC00000E5, 1u, 0, 0);
LABEL_25:
  v9 = CopyFileW(*(LPCWSTR *)(*(_QWORD *)v12 + 16LL), v11, 0);
LABEL_26:
  *(_DWORD *)(a1 + 8) = v9;
  if ( !v9 )
    *(_DWORD *)a1 = GetLastError_0();
  return a1;
}

```

## disassembly

```asm
0x18001fd88  push    rbx
0x18001fd8a  push    rbp
0x18001fd8b  push    rsi
0x18001fd8c  push    rdi
0x18001fd8d  push    r14
0x18001fd8f  sub     rsp, 20h
0x18001fd93  xorps   xmm0, xmm0
0x18001fd96  mov     rdi, r8
0x18001fd99  movups  xmmword ptr [rcx], xmm0
0x18001fd9c  mov     eax, [r8+38h]
0x18001fda0  mov     rbx, rdx
0x18001fda3  mov     rsi, rcx
0x18001fda6  mov     ebp, 1
0x18001fdab  mov     r14d, 0C00000E5h
0x18001fdb1  cmp     [rdx+38h], eax
0x18001fdb4  jz      short loc_18001FDC7
0x18001fdb6  xor     r9d, r9d; lpArguments
0x18001fdb9  xor     r8d, r8d; nNumberOfArguments
0x18001fdbc  mov     edx, ebp; dwExceptionFlags
0x18001fdbe  mov     ecx, r14d; dwExceptionCode
0x18001fdc1  call    cs:__imp_RaiseException
0x18001fdc7  cmp     [rbx+38h], ebp
0x18001fdca  jnz     short loc_18001FE34
0x18001fdcc  cmp     [rdi+38h], ebp
0x18001fdcf  jnz     short loc_18001FDDD
0x18001fdd1  add     rdi, 30h ; '0'
0x18001fdd5  cmp     qword ptr [rdi], 0
0x18001fdd9  jz      short loc_18001FDE1
0x18001fddb  jmp     short loc_18001FDF2
0x18001fddd  add     rdi, 30h ; '0'
0x18001fde1  xor     r9d, r9d; lpArguments
0x18001fde4  xor     r8d, r8d; nNumberOfArguments
0x18001fde7  mov     edx, ebp; dwExceptionFlags
0x18001fde9  mov     ecx, r14d; dwExceptionCode
0x18001fdec  call    cs:__imp_RaiseException
0x18001fdf2  mov     rax, [rdi]
0x18001fdf5  mov     rdi, [rax+10h]
0x18001fdf9  cmp     [rbx+38h], ebp
0x18001fdfc  jnz     short loc_18001FE0A
0x18001fdfe  add     rbx, 30h ; '0'
0x18001fe02  cmp     qword ptr [rbx], 0
0x18001fe06  jz      short loc_18001FE0E
0x18001fe08  jmp     short loc_18001FE1F
0x18001fe0a  add     rbx, 30h ; '0'
0x18001fe0e  xor     r9d, r9d; lpArguments
0x18001fe11  xor     r8d, r8d; nNumberOfArguments
0x18001fe14  mov     edx, ebp; dwExceptionFlags
0x18001fe16  mov     ecx, r14d; dwExceptionCode
0x18001fe19  call    cs:__imp_RaiseException
0x18001fe1f  mov     rcx, [rbx]
0x18001fe22  xor     r8d, r8d; bFailIfExists
0x18001fe25  mov     rdx, rdi; lpNewFileName
0x18001fe28  mov     rcx, [rcx+10h]; lpExistingFileName
0x18001fe2c  call    cs:__imp_CopyFileA
0x18001fe32  jmp     short loc_18001FE9C
0x18001fe34  cmp     dword ptr [rdi+38h], 2
0x18001fe38  jnz     short loc_18001FE46
0x18001fe3a  add     rdi, 30h ; '0'
0x18001fe3e  cmp     qword ptr [rdi], 0
0x18001fe42  jz      short loc_18001FE4A
0x18001fe44  jmp     short loc_18001FE5B
0x18001fe46  add     rdi, 30h ; '0'
0x18001fe4a  xor     r9d, r9d; lpArguments
0x18001fe4d  xor     r8d, r8d; nNumberOfArguments
0x18001fe50  mov     edx, ebp; dwExceptionFlags
0x18001fe52  mov     ecx, r14d; dwExceptionCode
0x18001fe55  call    cs:__imp_RaiseException
0x18001fe5b  cmp     dword ptr [rbx+38h], 2
0x18001fe5f  mov     rax, [rdi]
0x18001fe62  mov     rdi, [rax+10h]
0x18001fe66  jnz     short loc_18001FE74
0x18001fe68  add     rbx, 30h ; '0'
0x18001fe6c  cmp     qword ptr [rbx], 0
0x18001fe70  jz      short loc_18001FE78
0x18001fe72  jmp     short loc_18001FE89
0x18001fe74  add     rbx, 30h ; '0'
0x18001fe78  xor     r9d, r9d; lpArguments
0x18001fe7b  xor     r8d, r8d; nNumberOfArguments
0x18001fe7e  mov     edx, ebp; dwExceptionFlags
0x18001fe80  mov     ecx, r14d; dwExceptionCode
0x18001fe83  call    cs:__imp_RaiseException
0x18001fe89  mov     rcx, [rbx]
0x18001fe8c  xor     r8d, r8d; bFailIfExists
0x18001fe8f  mov     rdx, rdi; lpNewFileName
0x18001fe92  mov     rcx, [rcx+10h]; lpExistingFileName
0x18001fe96  call    cs:__imp_CopyFileW
0x18001fe9c  mov     [rsi+8], eax
0x18001fe9f  test    eax, eax
0x18001fea1  jnz     short loc_18001FEAA
0x18001fea3  call    GetLastError_0
0x18001fea8  mov     [rsi], eax
0x18001feaa  mov     rax, rsi
0x18001fead  add     rsp, 20h
0x18001feb1  pop     r14
0x18001feb3  pop     rdi
0x18001feb4  pop     rsi
0x18001feb5  pop     rbp
0x18001feb6  pop     rbx
0x18001feb7  retn
```
