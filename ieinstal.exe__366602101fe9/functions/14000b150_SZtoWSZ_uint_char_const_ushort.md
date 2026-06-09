# SZtoWSZ(uint,char const *,ushort * *)

- ea: `0x14000b150`
- end: `0x14000b241`
- name: `?SZtoWSZ@@YAJIPEBDPEAPEAG@Z`
- size: `241`
- prototype: `int(unsigned int, const char *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140004738`
- `0x1400049bc`
- `0x140008b44`
- `0x14000b334`

## callees

- `0x14000b150`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x14000b193`
- `KERNEL32!MultiByteToWideChar` at `0x14000b1df`
- `KERNEL32!MultiByteToWideChar` at `0x14000b193`
- `KERNEL32!MultiByteToWideChar` at `0x14000b1df`
- `KERNEL32!GetLastError` at `0x14000b204`
- `KERNEL32!GetLastError` at `0x14000b204`
- `ole32!CoTaskMemAlloc` at `0x14000b1b0`
- `ole32!CoTaskMemAlloc` at `0x14000b1b0`
- `ole32!CoTaskMemFree` at `0x14000b227`
- `ole32!CoTaskMemFree` at `0x14000b227`

## pseudocode

```c
__int64 __fastcall SZtoWSZ(__int64 a1, const char *a2, unsigned __int16 **a3)
{
  unsigned int v5; // ebx
  unsigned __int16 *v6; // rdi
  unsigned int cchWideChar; // ebx
  WCHAR *lpWideCharStr; // rax
  unsigned int v9; // eax
  signed int LastError; // eax

  v5 = -2147024809;
  if ( a2 && a3 )
  {
    v6 = 0;
    cchWideChar = MultiByteToWideChar(0, 0, a2, -1, 0, 0);
    if ( cchWideChar - 1 <= 0x3FF )
    {
      lpWideCharStr = (WCHAR *)CoTaskMemAlloc(2LL * cchWideChar);
      v6 = lpWideCharStr;
      if ( !lpWideCharStr )
        return (unsigned int)-2147024882;
      v9 = MultiByteToWideChar(0, 0, a2, -1, lpWideCharStr, cchWideChar);
      if ( v9 && v9 <= cchWideChar && !v6[v9 - 1] )
      {
        v5 = 0;
        *a3 = v6;
        return v5;
      }
    }
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 )
      CoTaskMemFree(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x14000b150  push    rbx
0x14000b152  push    rbp
0x14000b153  push    rsi
0x14000b154  push    rdi
0x14000b155  push    r14
0x14000b157  sub     rsp, 30h
0x14000b15b  xor     r14d, r14d
0x14000b15e  mov     rsi, r8
0x14000b161  mov     rbp, rdx
0x14000b164  mov     ebx, 80070057h
0x14000b169  test    rdx, rdx
0x14000b16c  jz      loc_14000B233
0x14000b172  test    r8, r8
0x14000b175  jz      loc_14000B233
0x14000b17b  mov     r8, rdx; lpMultiByteStr
0x14000b17e  mov     [rsp+58h+cchWideChar], r14d; cchWideChar
0x14000b183  xor     edx, edx; dwFlags
0x14000b185  mov     [rsp+58h+lpWideCharStr], r14; lpWideCharStr
0x14000b18a  or      r9d, 0FFFFFFFFh; cbMultiByte
0x14000b18e  xor     ecx, ecx; CodePage
0x14000b190  mov     edi, r14d
0x14000b193  call    cs:__imp_MultiByteToWideChar
0x14000b19a  nop     dword ptr [rax+rax+00h]
0x14000b19f  mov     ebx, eax
0x14000b1a1  lea     eax, [rbx-1]
0x14000b1a4  cmp     eax, 3FFh
0x14000b1a9  ja      short loc_14000B204
0x14000b1ab  mov     ecx, ebx
0x14000b1ad  add     rcx, rcx; cb
0x14000b1b0  call    cs:__imp_CoTaskMemAlloc
0x14000b1b7  nop     dword ptr [rax+rax+00h]
0x14000b1bc  mov     rdi, rax
0x14000b1bf  test    rax, rax
0x14000b1c2  jnz     short loc_14000B1CB
0x14000b1c4  mov     ebx, 8007000Eh
0x14000b1c9  jmp     short loc_14000B233
0x14000b1cb  mov     [rsp+58h+cchWideChar], ebx; cchWideChar
0x14000b1cf  or      r9d, 0FFFFFFFFh; cbMultiByte
0x14000b1d3  mov     r8, rbp; lpMultiByteStr
0x14000b1d6  mov     [rsp+58h+lpWideCharStr], rdi; lpWideCharStr
0x14000b1db  xor     edx, edx; dwFlags
0x14000b1dd  xor     ecx, ecx; CodePage
0x14000b1df  call    cs:__imp_MultiByteToWideChar
0x14000b1e6  nop     dword ptr [rax+rax+00h]
0x14000b1eb  test    eax, eax
0x14000b1ed  jz      short loc_14000B204
0x14000b1ef  cmp     eax, ebx
0x14000b1f1  ja      short loc_14000B204
0x14000b1f3  dec     eax
0x14000b1f5  cmp     [rdi+rax*2], r14w
0x14000b1fa  jnz     short loc_14000B204
0x14000b1fc  mov     ebx, r14d
0x14000b1ff  mov     [rsi], rdi
0x14000b202  jmp     short loc_14000B233
0x14000b204  call    cs:__imp_GetLastError
0x14000b20b  nop     dword ptr [rax+rax+00h]
0x14000b210  mov     ebx, eax
0x14000b212  test    eax, eax
0x14000b214  jle     short loc_14000B21F
0x14000b216  movzx   ebx, ax
0x14000b219  or      ebx, 80070000h
0x14000b21f  test    rdi, rdi
0x14000b222  jz      short loc_14000B233
0x14000b224  mov     rcx, rdi; pv
0x14000b227  call    cs:__imp_CoTaskMemFree
0x14000b22e  nop     dword ptr [rax+rax+00h]
0x14000b233  mov     eax, ebx
0x14000b235  add     rsp, 30h
0x14000b239  pop     r14
0x14000b23b  pop     rdi
0x14000b23c  pop     rsi
0x14000b23d  pop     rbp
0x14000b23e  pop     rbx
0x14000b23f  retn
```
