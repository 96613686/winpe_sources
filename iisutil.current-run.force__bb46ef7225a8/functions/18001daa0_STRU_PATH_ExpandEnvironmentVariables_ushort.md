# STRU_PATH::ExpandEnvironmentVariables(ushort *)

- ea: `0x18001daa0`
- end: `0x18001dbfe`
- name: `?ExpandEnvironmentVariables@STRU_PATH@@QEAAJPEAG@Z`
- size: `350`
- prototype: `__int64 __fastcall(STRU_PATH *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001dc10`

## callees

- `0x180001b60`
- `0x180002470`
- `0x180002b60`
- `0x18001daa0`
- `0x18002c48e`
- `0x18002c4c0`

## import_xrefs

- `msvcrt!wcschr` at `0x18001db00`
- `msvcrt!wcschr` at `0x18001db00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db96`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001db3f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001db82`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001db3f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001db82`

## pseudocode

```c
__int64 __fastcall STRU_PATH::ExpandEnvironmentVariables(STRU_PATH *this, unsigned __int16 *a2)
{
  const unsigned __int16 *v4; // rdi
  unsigned int v5; // edi
  DWORD v7; // edx
  int v8; // ebx
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
0x18001daa0  mov     [rsp-8+arg_10], rbx
0x18001daa5  push    rbp
0x18001daa6  push    rsi
0x18001daa7  push    rdi
0x18001daa8  lea     rbp, [rsp-70h]
0x18001daad  sub     rsp, 170h
0x18001dab4  mov     rax, cs:__security_cookie
0x18001dabb  xor     rax, rsp
0x18001dabe  mov     [rbp+80h+var_20], rax
0x18001dac2  mov     rbx, rdx
0x18001dac5  mov     rsi, rcx
0x18001dac8  xor     edx, edx; Val
0x18001daca  lea     rcx, [rsp+180h+Dst+1]; void *
0x18001dacf  mov     r8d, 107h; Size
0x18001dad5  call    memset_0
0x18001dada  lea     rdi, [rsp+180h+Dst]
0x18001dadf  mov     byte ptr [rsp+180h+Dst], 0
0x18001dae4  mov     edx, 25h ; '%'; Ch
0x18001dae9  mov     [rsp+180h+lpDst], rdi
0x18001daee  mov     rcx, rbx; Str
0x18001daf1  mov     [rsp+180h+var_138], 108h
0x18001daf9  mov     [rsp+180h+var_134], 100h
0x18001db00  call    cs:__imp_wcschr
0x18001db06  test    rax, rax
0x18001db09  jnz     short loc_18001DB31
0x18001db0b  xor     edi, edi
0x18001db0d  cmp     rbx, [rsi+20h]
0x18001db11  jz      short loc_18001DB20
0x18001db13  mov     rdx, rbx; unsigned __int16 *
0x18001db16  mov     rcx, rsi; this
0x18001db19  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001db1e  mov     edi, eax
0x18001db20  lea     rcx, [rsp+180h+var_160]; this
0x18001db25  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001db2a  mov     eax, edi
0x18001db2c  jmp     loc_18001DBDF
0x18001db31  mov     r8d, 84h; nSize
0x18001db37  lea     rdx, [rsp+180h+Dst]; lpDst
0x18001db3c  mov     rcx, rbx; lpSrc
0x18001db3f  call    cs:__imp_ExpandEnvironmentStringsW
0x18001db45  mov     edx, eax
0x18001db47  test    eax, eax
0x18001db49  jz      short loc_18001DB8C
0x18001db4b  mov     eax, edx
0x18001db4d  add     rax, rax
0x18001db50  cmp     rax, 108h
0x18001db56  jbe     short loc_18001DBC6
0x18001db58  add     edx, edx; unsigned int
0x18001db5a  lea     rcx, [rsp+180h+var_160]; this
0x18001db5f  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18001db64  test    al, al
0x18001db66  jnz     short loc_18001DB6F
0x18001db68  mov     ebx, 8007000Eh
0x18001db6d  jmp     short loc_18001DBD3
0x18001db6f  mov     r8d, [rsp+180h+var_138]
0x18001db74  mov     rcx, rbx; lpSrc
0x18001db77  mov     rdi, [rsp+180h+lpDst]
0x18001db7c  shr     r8d, 1; nSize
0x18001db7f  mov     rdx, rdi; lpDst
0x18001db82  call    cs:__imp_ExpandEnvironmentStringsW
0x18001db88  test    eax, eax
0x18001db8a  jnz     short loc_18001DBB8
0x18001db8c  call    cs:__imp_GetLastError
0x18001db92  test    eax, eax
0x18001db94  jz      short loc_18001DBAD
0x18001db96  call    cs:__imp_GetLastError
0x18001db9c  mov     ebx, eax
0x18001db9e  test    eax, eax
0x18001dba0  jle     short loc_18001DBB2
0x18001dba2  movzx   ebx, ax
0x18001dba5  or      ebx, 80070000h
0x18001dbab  jmp     short loc_18001DBB2
0x18001dbad  mov     ebx, 80004005h
0x18001dbb2  test    ebx, ebx
0x18001dbb4  js      short loc_18001DBD3
0x18001dbb6  jmp     short loc_18001DBC6
0x18001dbb8  mov     ecx, eax
0x18001dbba  mov     eax, [rsp+180h+var_138]
0x18001dbbe  add     rcx, rcx
0x18001dbc1  cmp     rax, rcx
0x18001dbc4  jb      short loc_18001DB68
0x18001dbc6  mov     rdx, rdi; unsigned __int16 *
0x18001dbc9  mov     rcx, rsi; this
0x18001dbcc  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001dbd1  mov     ebx, eax
0x18001dbd3  lea     rcx, [rsp+180h+var_160]; this
0x18001dbd8  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001dbdd  mov     eax, ebx
0x18001dbdf  mov     rcx, [rbp+80h+var_20]
0x18001dbe3  xor     rcx, rsp; StackCookie
0x18001dbe6  call    __security_check_cookie
0x18001dbeb  mov     rbx, [rsp+180h+arg_10]
0x18001dbf3  add     rsp, 170h
0x18001dbfa  pop     rdi
0x18001dbfb  pop     rsi
0x18001dbfc  pop     rbp
0x18001dbfd  retn
```
