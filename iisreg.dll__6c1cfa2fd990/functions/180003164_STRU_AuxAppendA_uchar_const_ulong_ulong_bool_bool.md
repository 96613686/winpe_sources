# STRU::AuxAppendA(uchar const *,ulong,ulong,bool,bool)

- ea: `0x180003164`
- end: `0x180003271`
- name: `?AuxAppendA@STRU@@AEAAJPEBEKK_N1@Z`
- size: `269`
- prototype: `__int64 __usercall@<rax>(STRU *__hidden this@<rcx>, LPCCH lpMultiByteStr@<rdx>, unsigned int cbMultiByte@<r8d>, unsigned int@<r9d>, bool, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002330`

## callees

- `0x180003024`
- `0x180003164`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800031c5`
- `KERNEL32!GetLastError` at `0x18000321d`
- `KERNEL32!GetLastError` at `0x1800031c5`
- `KERNEL32!GetLastError` at `0x18000321d`
- `KERNEL32!MultiByteToWideChar` at `0x180003213`
- `KERNEL32!MultiByteToWideChar` at `0x180003243`
- `KERNEL32!MultiByteToWideChar` at `0x180003213`
- `KERNEL32!MultiByteToWideChar` at `0x180003243`

## pseudocode

```c
signed int __fastcall STRU::AuxAppendA(
        STRU *this,
        LPCCH lpMultiByteStr,
        int cbMultiByte,
        unsigned int a4,
        bool a5,
        bool a6)
{
  __int64 v6; // rsi
  unsigned __int64 v8; // rcx
  __int64 v11; // r8
  unsigned __int64 v12; // rdx
  signed int result; // eax
  int v14; // eax
  int v15; // r9d
  WCHAR *v16; // rbp
  const CHAR *v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rdx
  WCHAR *lpWideCharStr; // [rsp+20h] [rbp-48h]
  int cchWideChar; // [rsp+28h] [rbp-40h]

  v6 = a4;
  v8 = *((unsigned int *)this + 10);
  v11 = a4 + 2LL * (unsigned int)cbMultiByte;
  if ( v8 < v11 + 2 )
  {
    v12 = v11 + (a5 ? 128LL : 2LL);
    if ( v12 > 0xFFFFFFFF )
      return -2147024362;
    if ( (unsigned int)v12 > (unsigned int)v8 && !BUFFER::ReallocStorage(this, v12) )
      goto LABEL_6;
  }
  v14 = 0;
  if ( !cbMultiByte )
    goto LABEL_14;
  v15 = cbMultiByte;
  v16 = (WCHAR *)(v6 + *((_QWORD *)this + 4));
  v17 = lpMultiByteStr;
  cchWideChar = *((_DWORD *)this + 10);
  lpWideCharStr = v16;
  if ( a6 )
    goto LABEL_13;
  v14 = MultiByteToWideChar(0xFDE9u, 8u, lpMultiByteStr, cbMultiByte, v16, cchWideChar);
  if ( v14 )
  {
LABEL_14:
    v18 = *((_QWORD *)this + 4);
    v19 = ((unsigned int)v6 >> 1) + v14;
    *((_DWORD *)this + 12) = v19;
    result = 0;
    *(_WORD *)(v18 + 2 * v19) = 0;
    return result;
  }
  if ( GetLastError() != 1113 )
    goto LABEL_6;
  v15 = cbMultiByte;
  cchWideChar = *((_DWORD *)this + 10);
  v17 = lpMultiByteStr;
  lpWideCharStr = v16;
LABEL_13:
  v14 = MultiByteToWideChar(0, 9u, v17, v15, lpWideCharStr, cchWideChar);
  if ( v14 )
    goto LABEL_14;
LABEL_6:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180003164  push    rbx
0x180003166  push    rbp
0x180003167  push    rsi
0x180003168  push    rdi
0x180003169  push    r14
0x18000316b  push    r15
0x18000316d  sub     rsp, 38h
0x180003171  mov     esi, r9d
0x180003174  mov     rbx, rcx
0x180003177  mov     ecx, [rcx+28h]
0x18000317a  mov     r14, rdx
0x18000317d  mov     edi, r8d
0x180003180  lea     r8, [rsi+rdi*2]
0x180003184  lea     rax, [r8+2]
0x180003188  cmp     rcx, rax
0x18000318b  jnb     short loc_1800031E0
0x18000318d  neg     [rsp+68h+arg_20]
0x180003194  sbb     rax, rax
0x180003197  and     eax, 7Eh
0x18000319a  lea     rdx, [rax+2]
0x18000319e  mov     eax, 0FFFFFFFFh
0x1800031a3  add     rdx, r8; unsigned int
0x1800031a6  cmp     rdx, rax
0x1800031a9  jbe     short loc_1800031B5
0x1800031ab  mov     eax, 80070216h
0x1800031b0  jmp     loc_180003264
0x1800031b5  cmp     edx, ecx
0x1800031b7  jbe     short loc_1800031E0
0x1800031b9  mov     rcx, rbx; this
0x1800031bc  call    ?ReallocStorage@BUFFER@@AEAA_NK@Z; BUFFER::ReallocStorage(ulong)
0x1800031c1  test    al, al
0x1800031c3  jnz     short loc_1800031E0
0x1800031c5  call    cs:__imp_GetLastError
0x1800031cb  test    eax, eax
0x1800031cd  jle     loc_180003264
0x1800031d3  movzx   eax, ax
0x1800031d6  or      eax, 80070000h
0x1800031db  jmp     loc_180003264
0x1800031e0  xor     eax, eax
0x1800031e2  test    edi, edi
0x1800031e4  jz      short loc_180003251
0x1800031e6  mov     rbp, [rbx+20h]
0x1800031ea  mov     r9d, edi; cbMultiByte
0x1800031ed  mov     eax, [rbx+28h]
0x1800031f0  add     rbp, rsi
0x1800031f3  cmp     [rsp+68h+arg_28], 0
0x1800031fb  mov     r8, r14; lpMultiByteStr
0x1800031fe  mov     [rsp+68h+cchWideChar], eax; cchWideChar
0x180003202  mov     [rsp+68h+lpWideCharStr], rbp; lpWideCharStr
0x180003207  jnz     short loc_18000323C
0x180003209  mov     edx, 8; dwFlags
0x18000320e  mov     ecx, 0FDE9h; CodePage
0x180003213  call    cs:__imp_MultiByteToWideChar
0x180003219  test    eax, eax
0x18000321b  jnz     short loc_180003251
0x18000321d  call    cs:__imp_GetLastError
0x180003223  cmp     eax, 459h
0x180003228  jnz     short loc_1800031C5
0x18000322a  mov     eax, [rbx+28h]
0x18000322d  mov     r9d, edi; cbMultiByte
0x180003230  mov     [rsp+68h+cchWideChar], eax; cchWideChar
0x180003234  mov     r8, r14; lpMultiByteStr
0x180003237  mov     [rsp+68h+lpWideCharStr], rbp; lpWideCharStr
0x18000323c  mov     edx, 9; dwFlags
0x180003241  xor     ecx, ecx; CodePage
0x180003243  call    cs:__imp_MultiByteToWideChar
0x180003249  test    eax, eax
0x18000324b  jz      loc_1800031C5
0x180003251  mov     rcx, [rbx+20h]
0x180003255  shr     esi, 1
0x180003257  add     eax, esi
0x180003259  mov     edx, eax
0x18000325b  mov     [rbx+30h], eax
0x18000325e  xor     eax, eax
0x180003260  mov     [rcx+rdx*2], ax
0x180003264  add     rsp, 38h
0x180003268  pop     r15
0x18000326a  pop     r14
0x18000326c  pop     rdi
0x18000326d  pop     rsi
0x18000326e  pop     rbp
0x18000326f  pop     rbx
0x180003270  retn
```
