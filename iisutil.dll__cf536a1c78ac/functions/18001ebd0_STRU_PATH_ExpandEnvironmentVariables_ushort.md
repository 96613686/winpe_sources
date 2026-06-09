# STRU_PATH::ExpandEnvironmentVariables(ushort *)

- ea: `0x18001ebd0`
- end: `0x18001ed51`
- name: `?ExpandEnvironmentVariables@STRU_PATH@@QEAAJPEAG@Z`
- size: `385`
- prototype: `__int64 __fastcall(STRU_PATH *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001ed60`

## callees

- `0x1800026d0`
- `0x180002da0`
- `0x1800034f0`
- `0x18001ebd0`
- `0x18002e52e`
- `0x18002e560`

## import_xrefs

- `msvcrt!wcschr` at `0x18001ec30`
- `msvcrt!wcschr` at `0x18001ec30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ecd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ece2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ecd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ece2`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001ec75`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001ecc2`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001ec75`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001ecc2`

## pseudocode

```c
__int64 __fastcall STRU_PATH::ExpandEnvironmentVariables(STRU_PATH *this, unsigned __int16 *a2)
{
  const unsigned __int16 *v4; // rdi
  unsigned int v5; // edi
  DWORD v7; // edx
  signed int v8; // ebx
  DWORD v9; // eax
  signed int LastError; // eax
  _BYTE v11[32]; // [rsp+20h] [rbp-E0h] BYREF
  LPWSTR lpDst; // [rsp+40h] [rbp-C0h]
  unsigned int v13; // [rsp+48h] [rbp-B8h]
  __int16 v14; // [rsp+4Ch] [rbp-B4h]
  WCHAR Dst[136]; // [rsp+50h] [rbp-B0h] BYREF

  memset_0((char *)Dst + 1, 0, 0x107u);
  v4 = Dst;
  LOBYTE(Dst[0]) = 0;
  lpDst = Dst;
  v13 = 264;
  v14 = 256;
  if ( wcschr(a2, 0x25u) )
  {
    v7 = ExpandEnvironmentStringsW(a2, Dst, 0x84u);
    if ( v7 )
    {
      if ( 2 * (unsigned __int64)v7 > 0x108 )
      {
        if ( !BUFFER::Resize((BUFFER *)v11, 2 * v7) )
        {
LABEL_8:
          v8 = -2147024882;
LABEL_18:
          BUFFER::~BUFFER((BUFFER *)v11);
          return (unsigned int)v8;
        }
        v4 = lpDst;
        v9 = ExpandEnvironmentStringsW(a2, lpDst, v13 >> 1);
        if ( !v9 )
          goto LABEL_10;
        if ( v13 < 2 * (unsigned __int64)v9 )
          goto LABEL_8;
      }
LABEL_17:
      v8 = STRU::Copy(this, v4);
      goto LABEL_18;
    }
LABEL_10:
    if ( GetLastError() )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v8 = -2147467259;
    }
    if ( v8 < 0 )
      goto LABEL_18;
    goto LABEL_17;
  }
  v5 = 0;
  if ( a2 != *((unsigned __int16 **)this + 4) )
    v5 = STRU::Copy(this, a2);
  BUFFER::~BUFFER((BUFFER *)v11);
  return v5;
}

```

## disassembly

```asm
0x18001ebd0  mov     [rsp-8+arg_10], rbx
0x18001ebd5  push    rbp
0x18001ebd6  push    rsi
0x18001ebd7  push    rdi
0x18001ebd8  lea     rbp, [rsp-70h]
0x18001ebdd  sub     rsp, 170h
0x18001ebe4  mov     rax, cs:__security_cookie
0x18001ebeb  xor     rax, rsp
0x18001ebee  mov     [rbp+80h+var_20], rax
0x18001ebf2  mov     rbx, rdx
0x18001ebf5  mov     rsi, rcx
0x18001ebf8  xor     edx, edx; Val
0x18001ebfa  lea     rcx, [rsp+180h+Dst+1]; void *
0x18001ebff  mov     r8d, 107h; Size
0x18001ec05  call    memset_0
0x18001ec0a  lea     rdi, [rsp+180h+Dst]
0x18001ec0f  mov     byte ptr [rsp+180h+Dst], 0
0x18001ec14  mov     edx, 25h ; '%'; Ch
0x18001ec19  mov     [rsp+180h+lpDst], rdi
0x18001ec1e  mov     rcx, rbx; Str
0x18001ec21  mov     [rsp+180h+var_138], 108h
0x18001ec29  mov     [rsp+180h+var_134], 100h
0x18001ec30  call    cs:__imp_wcschr
0x18001ec37  nop     dword ptr [rax+rax+00h]
0x18001ec3c  test    rax, rax
0x18001ec3f  jnz     short loc_18001EC67
0x18001ec41  xor     edi, edi
0x18001ec43  cmp     rbx, [rsi+20h]
0x18001ec47  jz      short loc_18001EC56
0x18001ec49  mov     rdx, rbx; unsigned __int16 *
0x18001ec4c  mov     rcx, rsi; this
0x18001ec4f  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001ec54  mov     edi, eax
0x18001ec56  lea     rcx, [rsp+180h+var_160]; this
0x18001ec5b  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001ec60  mov     eax, edi
0x18001ec62  jmp     loc_18001ED31
0x18001ec67  mov     r8d, 84h; nSize
0x18001ec6d  lea     rdx, [rsp+180h+Dst]; lpDst
0x18001ec72  mov     rcx, rbx; lpSrc
0x18001ec75  call    cs:__imp_ExpandEnvironmentStringsW
0x18001ec7c  nop     dword ptr [rax+rax+00h]
0x18001ec81  mov     edx, eax
0x18001ec83  test    eax, eax
0x18001ec85  jz      short loc_18001ECD2
0x18001ec87  mov     eax, edx
0x18001ec89  add     rax, rax
0x18001ec8c  cmp     rax, 108h
0x18001ec92  jbe     loc_18001ED18
0x18001ec98  add     edx, edx; unsigned int
0x18001ec9a  lea     rcx, [rsp+180h+var_160]; this
0x18001ec9f  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18001eca4  test    al, al
0x18001eca6  jnz     short loc_18001ECAF
0x18001eca8  mov     ebx, 8007000Eh
0x18001ecad  jmp     short loc_18001ED25
0x18001ecaf  mov     r8d, [rsp+180h+var_138]
0x18001ecb4  mov     rcx, rbx; lpSrc
0x18001ecb7  mov     rdi, [rsp+180h+lpDst]
0x18001ecbc  shr     r8d, 1; nSize
0x18001ecbf  mov     rdx, rdi; lpDst
0x18001ecc2  call    cs:__imp_ExpandEnvironmentStringsW
0x18001ecc9  nop     dword ptr [rax+rax+00h]
0x18001ecce  test    eax, eax
0x18001ecd0  jnz     short loc_18001ED0A
0x18001ecd2  call    cs:__imp_GetLastError
0x18001ecd9  nop     dword ptr [rax+rax+00h]
0x18001ecde  test    eax, eax
0x18001ece0  jz      short loc_18001ECFF
0x18001ece2  call    cs:__imp_GetLastError
0x18001ece9  nop     dword ptr [rax+rax+00h]
0x18001ecee  mov     ebx, eax
0x18001ecf0  test    eax, eax
0x18001ecf2  jle     short loc_18001ED04
0x18001ecf4  movzx   ebx, ax
0x18001ecf7  or      ebx, 80070000h
0x18001ecfd  jmp     short loc_18001ED04
0x18001ecff  mov     ebx, 80004005h
0x18001ed04  test    ebx, ebx
0x18001ed06  js      short loc_18001ED25
0x18001ed08  jmp     short loc_18001ED18
0x18001ed0a  mov     ecx, eax
0x18001ed0c  mov     eax, [rsp+180h+var_138]
0x18001ed10  add     rcx, rcx
0x18001ed13  cmp     rax, rcx
0x18001ed16  jb      short loc_18001ECA8
0x18001ed18  mov     rdx, rdi; unsigned __int16 *
0x18001ed1b  mov     rcx, rsi; this
0x18001ed1e  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001ed23  mov     ebx, eax
0x18001ed25  lea     rcx, [rsp+180h+var_160]; this
0x18001ed2a  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001ed2f  mov     eax, ebx
0x18001ed31  mov     rcx, [rbp+80h+var_20]
0x18001ed35  xor     rcx, rsp; StackCookie
0x18001ed38  call    __security_check_cookie
0x18001ed3d  mov     rbx, [rsp+180h+arg_10]
0x18001ed45  add     rsp, 170h
0x18001ed4c  pop     rdi
0x18001ed4d  pop     rsi
0x18001ed4e  pop     rbp
0x18001ed4f  retn
```
