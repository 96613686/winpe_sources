# fcicb_Open

- ea: `0x18002ab00`
- end: `0x18002acbe`
- name: `fcicb_Open`
- size: `446`
- prototype: `INT_PTR __cdecl(LPSTR pszFile, int oflag, int pmode, int *err, void *pv)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002a900`
- `0x18002b130`
- `0x18002b1f0`

## callees

- `0x18002ab00`
- `0x180055550`
- `0x180055610`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002abf5`
- `msvcrt!_wcsicmp` at `0x18002abf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac8a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002ab84`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002abd7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002ab84`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002abd7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002ac75`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002ac75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ac9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ac9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ab2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ac2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ab2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ac2c`

## pseudocode

```c
INT_PTR __fastcall fcicb_Open(const CHAR *pszFile, int oflag, int pmode, DWORD *err)
{
  _DWORD *v7; // rax
  _QWORD *v8; // rbx
  int v9; // eax
  __int64 cchWideChar; // rdx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rax
  void *v13; // rsp
  void *v14; // rsp
  HANDLE FileW; // rax
  LPVOID v16; // rax
  wchar_t WideCharStr[32]; // [rsp+40h] [rbp+0h] BYREF

  v7 = CoTaskMemAlloc(0x30u);
  v8 = v7;
  if ( !v7 )
    goto LABEL_16;
  *v7 = 0;
  if ( (oflag & 0x10000) != 0 )
  {
    LOWORD(oflag) = 0x8000;
    *v7 = 4;
    v7[6] = 0;
    v7[10] = 1;
  }
  v9 = MultiByteToWideChar(CodePage, 0, pszFile, -1, 0, 0);
  cchWideChar = v9;
  if ( !v9 )
    goto LABEL_16;
  v11 = 2LL * v9 + 15;
  if ( v11 <= 2 * cchWideChar )
    v11 = 0xFFFFFFFFFFFFFF0LL;
  v12 = v11 & 0xFFFFFFFFFFFFFFF0uLL;
  v13 = alloca(v12);
  v14 = alloca(v12);
  if ( !MultiByteToWideChar(CodePage, 0, pszFile, -1, WideCharStr, cchWideChar) )
    goto LABEL_16;
  if ( (oflag & 0x100) == 0 )
  {
    FileW = CreateFileW(WideCharStr, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
LABEL_14:
    v8[4] = FileW;
    if ( FileW != (HANDLE)-1LL )
      return (INT_PTR)v8;
    goto LABEL_16;
  }
  if ( _wcsicmp(WideCharStr, ::WideCharStr) )
  {
    FileW = CreateFileW(WideCharStr, 0xC0000000, 0, 0, 2u, 0x80u, 0);
    goto LABEL_14;
  }
  v16 = CoTaskMemAlloc(0x30D40u);
  v8[1] = v16;
  if ( v16 )
  {
    *(_DWORD *)v8 = 3;
    v8[2] = 0;
    *((_DWORD *)v8 + 6) = 200000;
    return (INT_PTR)v8;
  }
LABEL_16:
  *err = GetLastError();
  if ( v8 )
    CoTaskMemFree(v8);
  return -1;
}

```

## disassembly

```asm
0x18002ab00  push    rbp
0x18002ab02  push    rbx
0x18002ab03  push    rsi
0x18002ab04  push    rdi
0x18002ab05  push    r14
0x18002ab07  push    r15
0x18002ab09  sub     rsp, 58h
0x18002ab0d  lea     rbp, [rsp+40h]
0x18002ab12  mov     rax, cs:__security_cookie
0x18002ab19  xor     rax, rbp
0x18002ab1c  mov     qword ptr [rbp+40h+WideCharStr], rax
0x18002ab20  mov     r14, rcx
0x18002ab23  mov     r15, r9
0x18002ab26  mov     ecx, 30h ; '0'; cb
0x18002ab2b  mov     edi, edx
0x18002ab2d  call    cs:__imp_CoTaskMemAlloc
0x18002ab33  mov     rbx, rax
0x18002ab36  test    rax, rax
0x18002ab39  jz      loc_18002AC8A
0x18002ab3f  mov     dword ptr [rax], 0
0x18002ab45  bt      edi, 10h
0x18002ab49  jnb     short loc_18002AB64
0x18002ab4b  mov     edi, 8000h
0x18002ab50  mov     dword ptr [rax], 4
0x18002ab56  mov     dword ptr [rax+18h], 0
0x18002ab5d  mov     dword ptr [rax+28h], 1
0x18002ab64  mov     ecx, cs:CodePage; CodePage
0x18002ab6a  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18002ab6e  mov     [rsp+80h+cchWideChar], 0; cchWideChar
0x18002ab76  mov     r8, r14; lpMultiByteStr
0x18002ab79  xor     edx, edx; dwFlags
0x18002ab7b  mov     [rsp+80h+lpWideCharStr], 0; lpWideCharStr
0x18002ab84  call    cs:__imp_MultiByteToWideChar
0x18002ab8a  movsxd  rdx, eax
0x18002ab8d  test    eax, eax
0x18002ab8f  jz      loc_18002AC8A
0x18002ab95  mov     rcx, rdx
0x18002ab98  add     rcx, rcx
0x18002ab9b  lea     rax, [rcx+0Fh]
0x18002ab9f  cmp     rax, rcx
0x18002aba2  ja      short loc_18002ABAE
0x18002aba4  mov     rax, 0FFFFFFFFFFFFFF0h
0x18002abae  and     rax, 0FFFFFFFFFFFFFFF0h
0x18002abb2  call    _alloca_probe
0x18002abb7  mov     ecx, cs:CodePage; CodePage
0x18002abbd  sub     rsp, rax
0x18002abc0  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18002abc4  mov     r8, r14; lpMultiByteStr
0x18002abc7  mov     [rsp+80h+cchWideChar], edx; cchWideChar
0x18002abcb  lea     rsi, [rsp+80h+WideCharStr]
0x18002abd0  xor     edx, edx; dwFlags
0x18002abd2  mov     [rsp+80h+lpWideCharStr], rsi; lpWideCharStr
0x18002abd7  call    cs:__imp_MultiByteToWideChar
0x18002abdd  test    eax, eax
0x18002abdf  jz      loc_18002AC8A
0x18002abe5  mov     rcx, rsi; lpFileName
0x18002abe8  bt      edi, 8
0x18002abec  jnb     short loc_18002AC4E
0x18002abee  lea     rdx, WideCharStr; String2
0x18002abf5  call    cs:__imp__wcsicmp
0x18002abfb  test    eax, eax
0x18002abfd  jz      short loc_18002AC25
0x18002abff  mov     [rsp+80h+hTemplateFile], 0
0x18002ac08  xor     r8d, r8d
0x18002ac0b  mov     [rsp+80h+cchWideChar], 80h
0x18002ac13  mov     edx, 0C0000000h
0x18002ac18  mov     dword ptr [rsp+80h+lpWideCharStr], 2
0x18002ac20  mov     rcx, rsi
0x18002ac23  jmp     short loc_18002AC72
0x18002ac25  mov     edi, 30D40h
0x18002ac2a  mov     ecx, edi; cb
0x18002ac2c  call    cs:__imp_CoTaskMemAlloc
0x18002ac32  mov     [rbx+8], rax
0x18002ac36  test    rax, rax
0x18002ac39  jz      short loc_18002AC8A
0x18002ac3b  mov     dword ptr [rbx], 3
0x18002ac41  mov     qword ptr [rbx+10h], 0
0x18002ac49  mov     [rbx+18h], edi
0x18002ac4c  jmp     short loc_18002AC85
0x18002ac4e  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x18002ac57  mov     edx, 80000000h; dwDesiredAccess
0x18002ac5c  mov     [rsp+80h+cchWideChar], 8000000h; dwFlagsAndAttributes
0x18002ac64  mov     r8d, 1; dwShareMode
0x18002ac6a  mov     dword ptr [rsp+80h+lpWideCharStr], 3; dwCreationDisposition
0x18002ac72  xor     r9d, r9d; lpSecurityAttributes
0x18002ac75  call    cs:__imp_CreateFileW
0x18002ac7b  mov     [rbx+20h], rax
0x18002ac7f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002ac83  jz      short loc_18002AC8A
0x18002ac85  mov     rax, rbx
0x18002ac88  jmp     short loc_18002ACA5
0x18002ac8a  call    cs:__imp_GetLastError
0x18002ac90  mov     [r15], eax
0x18002ac93  test    rbx, rbx
0x18002ac96  jz      short loc_18002ACA1
0x18002ac98  mov     rcx, rbx; pv
0x18002ac9b  call    cs:__imp_CoTaskMemFree
0x18002aca1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002aca5  mov     rcx, qword ptr [rbp+40h+WideCharStr]
0x18002aca9  xor     rcx, rbp; StackCookie
0x18002acac  call    __security_check_cookie
0x18002acb1  lea     rsp, [rbp+18h]
0x18002acb5  pop     r15
0x18002acb7  pop     r14
0x18002acb9  pop     rdi
0x18002acba  pop     rsi
0x18002acbb  pop     rbx
0x18002acbc  pop     rbp
0x18002acbd  retn
```
