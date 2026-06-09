# RasAuthAttributeInsert

- ea: `0x18000b610`
- end: `0x18000b809`
- name: `RasAuthAttributeInsert`
- size: `505`
- prototype: `__int64 __fastcall(int, int, int, int, size_t Size, LPCWCH lpWideCharStr)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180007370`
- `0x180009dc0`
- `0x180011414`
- `0x1800122fc`
- `0x180016e2c`
- `0x180018c8c`
- `0x180019034`
- `0x1800192e0`
- `0x180019c3c`

## callees

- `0x18000b610`
- `0x180025efc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b759`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b759`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b704`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b704`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000b742`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000b742`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b74c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b74c`

## pseudocode

```c
DWORD __fastcall RasAuthAttributeInsert(unsigned int a1, __int64 a2, int a3, int a4, size_t Size, LPCWCH lpWideCharStr)
{
  __int64 v7; // rbx
  DWORD result; // eax
  unsigned int v11; // r12d
  CHAR *lpMultiByteStr; // rax
  DWORD LastError; // edi

  v7 = 2LL * a1;
  if ( !*(_DWORD *)(a2 + 16LL * a1) )
    return 8;
  if ( a3 != 8250 )
  {
    if ( a3 > 8097 )
    {
      if ( a3 > 9000 )
      {
        if ( a3 == 9001 || a3 == 9002 || (unsigned int)(a3 - 9003) < 2 )
          goto LABEL_10;
      }
      else if ( a3 == 9000 || a3 == 8102 )
      {
        goto LABEL_10;
      }
LABEL_16:
      *(_QWORD *)(a2 + 16LL * a1 + 8) = lpWideCharStr;
      goto LABEL_24;
    }
    if ( a3 != 8097 )
    {
      switch ( a3 )
      {
        case 1:
        case 2:
        case 3:
        case 11:
        case 18:
        case 19:
        case 20:
        case 22:
        case 24:
        case 25:
        case 26:
        case 30:
        case 31:
        case 32:
        case 33:
        case 34:
        case 35:
        case 36:
        case 44:
        case 50:
        case 60:
        case 63:
        case 66:
        case 67:
        case 77:
        case 78:
        case 79:
        case 80:
        case 96:
        case 97:
          break;
        default:
          goto LABEL_16;
      }
    }
  }
LABEL_10:
  if ( lpWideCharStr )
  {
    v11 = Size + 1;
    if ( (int)Size + 1 < (unsigned int)Size )
      return 534;
    lpMultiByteStr = (CHAR *)LocalAlloc(0x40u, v11);
    *(_QWORD *)(a2 + 8 * v7 + 8) = lpMultiByteStr;
    if ( !lpMultiByteStr )
      return GetLastError();
    if ( a4 )
    {
      if ( !WideCharToMultiByte(0, 0x400u, lpWideCharStr, v11, lpMultiByteStr, Size + 1, 0, 0) )
      {
        LastError = GetLastError();
        LocalFree(*(HLOCAL *)(a2 + 8 * v7 + 8));
        return LastError;
      }
    }
    else
    {
      memcpy_0(lpMultiByteStr, lpWideCharStr, (unsigned int)Size);
    }
  }
  else
  {
    *(_QWORD *)(a2 + 16LL * a1 + 8) = 0;
  }
LABEL_24:
  *(_DWORD *)(a2 + 8 * v7 + 4) = Size;
  result = 0;
  *(_DWORD *)(a2 + 8 * v7) = a3;
  return result;
}

```

## disassembly

```asm
0x18000b610  mov     [rsp+arg_18], rbx
0x18000b615  push    rbp
0x18000b616  push    rsi
0x18000b617  push    r14
0x18000b619  sub     rsp, 40h
0x18000b61d  mov     ebx, ecx
0x18000b61f  mov     r14d, r9d
0x18000b622  add     rbx, rbx
0x18000b625  mov     ebp, r8d
0x18000b628  mov     rsi, rdx
0x18000b62b  cmp     dword ptr [rdx+rbx*8], 0
0x18000b62f  jnz     short loc_18000B644
0x18000b631  mov     eax, 8
0x18000b636  mov     rbx, [rsp+58h+arg_18]
0x18000b63b  add     rsp, 40h
0x18000b63f  pop     r14
0x18000b641  pop     rsi
0x18000b642  pop     rbp
0x18000b643  retn
0x18000b644  mov     [rsp+58h+arg_0], rdi
0x18000b649  mov     edi, dword ptr [rsp+58h+Size]
0x18000b650  mov     [rsp+58h+arg_8], r12
0x18000b655  mov     [rsp+58h+arg_10], r15
0x18000b65a  cmp     ebp, 203Ah
0x18000b660  jz      short loc_18000B6B0; jumptable 000000018000B690 cases 1-3,11,18-20,22,24-26,30-36,44,50,60,63,66,67,77-80,96,97
0x18000b662  cmp     ebp, 1FA1h
0x18000b668  jg      short loc_18000B692
0x18000b66a  jz      short loc_18000B6B0; jumptable 000000018000B690 cases 1-3,11,18-20,22,24-26,30-36,44,50,60,63,66,67,77-80,96,97
0x18000b66c  lea     eax, [r8-1]; switch 97 cases
0x18000b670  cmp     eax, 60h
0x18000b673  ja      short def_18000B690; jumptable 000000018000B690 default case, cases 4-10,12-17,21,23,27-29,37-43,45-49,51-59,61,62,64,65,68-76,81-95
0x18000b675  lea     rdx, __ImageBase
0x18000b67c  cdqe
0x18000b67e  movzx   eax, ds:(byte_18000B7A8 - 180000000h)[rdx+rax]
0x18000b686  mov     ecx, ds:(jpt_18000B690 - 180000000h)[rdx+rax*4]
0x18000b68d  add     rcx, rdx
0x18000b690  jmp     rcx; switch jump
0x18000b692  cmp     ebp, 2328h
0x18000b698  jg      short loc_18000B6D4
0x18000b69a  jz      short loc_18000B6B0; jumptable 000000018000B690 cases 1-3,11,18-20,22,24-26,30-36,44,50,60,63,66,67,77-80,96,97
0x18000b69c  mov     ecx, ebp
0x18000b69e  sub     ecx, 1FA3h
0x18000b6a4  jz      short def_18000B690; jumptable 000000018000B690 default case, cases 4-10,12-17,21,23,27-29,37-43,45-49,51-59,61,62,64,65,68-76,81-95
0x18000b6a6  sub     ecx, 1
0x18000b6a9  jz      short def_18000B690; jumptable 000000018000B690 default case, cases 4-10,12-17,21,23,27-29,37-43,45-49,51-59,61,62,64,65,68-76,81-95
0x18000b6ab  cmp     ecx, 2
0x18000b6ae  jnz     short def_18000B690; jumptable 000000018000B690 default case, cases 4-10,12-17,21,23,27-29,37-43,45-49,51-59,61,62,64,65,68-76,81-95
0x18000b6b0  mov     r15, [rsp+58h+lpWideCharStr]; jumptable 000000018000B690 cases 1-3,11,18-20,22,24-26,30-36,44,50,60,63,66,67,77-80,96,97
0x18000b6b8  test    r15, r15
0x18000b6bb  jz      loc_18000B773
0x18000b6c1  lea     r12d, [rdi+1]
0x18000b6c5  cmp     r12d, edi
0x18000b6c8  jnb     short loc_18000B6FC
0x18000b6ca  mov     eax, 216h
0x18000b6cf  jmp     loc_18000B783
0x18000b6d4  mov     ecx, ebp
0x18000b6d6  sub     ecx, 2329h
0x18000b6dc  jz      short loc_18000B6B0; jumptable 000000018000B690 cases 1-3,11,18-20,22,24-26,30-36,44,50,60,63,66,67,77-80,96,97
0x18000b6de  sub     ecx, 1
0x18000b6e1  jz      short loc_18000B6B0; jumptable 000000018000B690 cases 1-3,11,18-20,22,24-26,30-36,44,50,60,63,66,67,77-80,96,97
0x18000b6e3  sub     ecx, 1
0x18000b6e6  jz      short loc_18000B6B0; jumptable 000000018000B690 cases 1-3,11,18-20,22,24-26,30-36,44,50,60,63,66,67,77-80,96,97
0x18000b6e8  cmp     ecx, 1
0x18000b6eb  jz      short loc_18000B6B0; jumptable 000000018000B690 cases 1-3,11,18-20,22,24-26,30-36,44,50,60,63,66,67,77-80,96,97
0x18000b6ed  mov     rax, [rsp+58h+lpWideCharStr]; jumptable 000000018000B690 default case, cases 4-10,12-17,21,23,27-29,37-43,45-49,51-59,61,62,64,65,68-76,81-95
0x18000b6f5  mov     [rsi+rbx*8+8], rax
0x18000b6fa  jmp     short loc_18000B77A
0x18000b6fc  mov     edx, r12d; uBytes
0x18000b6ff  mov     ecx, 40h ; '@'; uFlags
0x18000b704  call    cs:__imp_LocalAlloc
0x18000b70a  mov     [rsi+rbx*8+8], rax
0x18000b70f  test    rax, rax
0x18000b712  jnz     short loc_18000B71C
0x18000b714  call    cs:__imp_GetLastError
0x18000b71a  jmp     short loc_18000B783
0x18000b71c  test    r14d, r14d
0x18000b71f  jz      short loc_18000B763
0x18000b721  xor     ecx, ecx; CodePage
0x18000b723  mov     r9d, r12d; cchWideChar
0x18000b726  mov     [rsp+58h+lpUsedDefaultChar], rcx; lpUsedDefaultChar
0x18000b72b  mov     r8, r15; lpWideCharStr
0x18000b72e  mov     [rsp+58h+lpDefaultChar], rcx; lpDefaultChar
0x18000b733  mov     edx, 400h; dwFlags
0x18000b738  mov     [rsp+58h+cbMultiByte], r12d; cbMultiByte
0x18000b73d  mov     [rsp+58h+lpMultiByteStr], rax; lpMultiByteStr
0x18000b742  call    cs:__imp_WideCharToMultiByte
0x18000b748  test    eax, eax
0x18000b74a  jnz     short loc_18000B77A
0x18000b74c  call    cs:__imp_GetLastError
0x18000b752  mov     rcx, [rsi+rbx*8+8]; hMem
0x18000b757  mov     edi, eax
0x18000b759  call    cs:__imp_LocalFree
0x18000b75f  mov     eax, edi
0x18000b761  jmp     short loc_18000B783
0x18000b763  mov     r8, rdi; Size
0x18000b766  mov     rdx, r15; Src
0x18000b769  mov     rcx, rax; void *
0x18000b76c  call    memcpy_0
0x18000b771  jmp     short loc_18000B77A
0x18000b773  xor     ecx, ecx
0x18000b775  mov     [rsi+rbx*8+8], rcx
0x18000b77a  mov     [rsi+rbx*8+4], edi
0x18000b77e  xor     eax, eax
0x18000b780  mov     [rsi+rbx*8], ebp
0x18000b783  mov     r12, [rsp+58h+arg_8]
0x18000b788  mov     rdi, [rsp+58h+arg_0]
0x18000b78d  mov     r15, [rsp+58h+arg_10]
0x18000b792  mov     rbx, [rsp+58h+arg_18]
0x18000b797  add     rsp, 40h
0x18000b79b  pop     r14
0x18000b79d  pop     rsi
0x18000b79e  pop     rbp
0x18000b79f  retn
```
