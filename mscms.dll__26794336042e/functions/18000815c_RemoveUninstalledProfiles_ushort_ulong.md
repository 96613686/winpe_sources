# RemoveUninstalledProfiles(ushort *,ulong *)

- ea: `0x18000815c`
- end: `0x18000836c`
- name: `?RemoveUninstalledProfiles@@YAKPEAGPEAK@Z`
- size: `528`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x1800212e0`

## callees

- `0x18000815c`
- `0x180008bf0`
- `0x180008cc0`
- `0x18000b828`
- `0x18000be44`
- `0x180029f14`
- `0x18002e5f0`
- `0x18002f2dc`
- `0x180042458`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008234`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000830e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008234`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000830e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800082b8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800082b8`

## pseudocode

```c
__int64 __fastcall RemoveUninstalledProfiles(unsigned __int16 *a1, unsigned int *a2)
{
  DWORD LastError; // ebx
  unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // rsi
  BOOL v7; // r12d
  unsigned int v8; // r15d
  unsigned __int16 *i; // rdi
  __int64 v10; // r8
  const unsigned __int16 *FilenameFromPath; // rbx
  __int64 v12; // rax
  int v13; // ecx
  __int64 v14; // rax
  unsigned int v16; // [rsp+20h] [rbp-268h] BYREF
  DWORD pcbNeeded[3]; // [rsp+24h] [rbp-264h] BYREF
  WCHAR FileName[264]; // [rsp+30h] [rbp-258h] BYREF

  v16 = 0;
  LastError = 0;
  if ( !a1 || !*a2 )
    return LastError;
  if ( *a2 > 0x7FFFFFFF )
    return 8;
  v5 = (unsigned __int16 *)MemAlloc(2LL * *a2);
  v6 = v5;
  if ( !v5 )
    return 8;
  v7 = 0;
  memcpy_0(v5, a1, 2LL * *a2);
  v8 = *a2;
  for ( i = a1; ; i += v14 + 1 )
  {
    v10 = *a2;
    if ( i - a1 >= v10 || !*i )
      break;
    pcbNeeded[0] = 520;
    FilenameFromPath = GetFilenameFromPath(i);
    if ( !FilenameFromPath )
    {
      LastError = 87;
      goto LABEL_32;
    }
    if ( InternalGetColorDirectory(0, FileName, pcbNeeded) )
    {
      v12 = -1;
      do
        ++v12;
      while ( FileName[v12] );
      if ( *((_WORD *)&pcbNeeded[2] + v12 + 1) == 92 || (v13 = StringCchCatW(FileName, 0x104u, gszBackslash), v13 >= 0) )
      {
        v13 = StringCchCatW(FileName, 0x104u, FilenameFromPath);
        if ( v13 >= 0 )
        {
          LastError = 0;
          v7 = GetFileAttributesW(FileName) != -1;
          goto LABEL_22;
        }
      }
      LastError = (unsigned __int16)v13;
      if ( (v13 & 0x1FFF0000) != 0x70000 )
        LastError = v13;
    }
    else
    {
      if ( !GetLastError() )
      {
        LastError = -2147467259;
        goto LABEL_32;
      }
      LastError = GetLastError();
    }
    if ( LastError )
      goto LABEL_32;
LABEL_22:
    if ( !v7 )
    {
      if ( !RemoveStringFromMultiSz(v6, v8, i, &v16) )
      {
        LastError = GetLastError();
        goto LABEL_32;
      }
      v8 = v16;
    }
    v14 = -1;
    do
      ++v14;
    while ( i[v14] );
  }
  memcpy_0(a1, v6, 2 * v10);
  *a2 = v8;
LABEL_32:
  MemFree(v6);
  return LastError;
}

```

## disassembly

```asm
0x18000815c  mov     [rsp+arg_10], rbx
0x180008161  push    rbp
0x180008162  push    rsi
0x180008163  push    rdi
0x180008164  push    r12
0x180008166  push    r13
0x180008168  push    r14
0x18000816a  push    r15
0x18000816c  sub     rsp, 250h
0x180008173  mov     rax, cs:__security_cookie
0x18000817a  xor     rax, rsp
0x18000817d  mov     [rsp+288h+var_48], rax
0x180008185  xor     r13d, r13d
0x180008188  mov     r14, rdx
0x18000818b  mov     [rsp+288h+var_268], r13d
0x180008190  mov     rbp, rcx
0x180008193  mov     ebx, r13d
0x180008196  test    rcx, rcx
0x180008199  jz      loc_18000833F
0x18000819f  cmp     [rdx], r13d
0x1800081a2  jz      loc_18000833F
0x1800081a8  cmp     dword ptr [rdx], 7FFFFFFFh
0x1800081ae  ja      loc_18000833A
0x1800081b4  mov     ecx, [rdx]
0x1800081b6  add     rcx, rcx
0x1800081b9  call    MemAlloc
0x1800081be  mov     rsi, rax
0x1800081c1  test    rax, rax
0x1800081c4  jz      loc_18000833A
0x1800081ca  mov     r8d, [r14]
0x1800081cd  mov     rdx, rbp; Src
0x1800081d0  add     r8, r8; Size
0x1800081d3  mov     rcx, rax; void *
0x1800081d6  mov     r12d, r13d
0x1800081d9  call    memcpy_0
0x1800081de  mov     r15d, [r14]
0x1800081e1  mov     rdi, rbp
0x1800081e4  mov     r8d, [r14]
0x1800081e7  mov     rax, rdi
0x1800081ea  sub     rax, rbp
0x1800081ed  sar     rax, 1
0x1800081f0  cmp     rax, r8
0x1800081f3  jge     loc_18000831F
0x1800081f9  cmp     [rdi], r13w
0x1800081fd  jz      loc_18000831F
0x180008203  mov     rcx, rdi; lpStringSource
0x180008206  mov     [rsp+288h+pcbNeeded], 208h
0x18000820e  call    GetFilenameFromPath
0x180008213  mov     rbx, rax
0x180008216  test    rax, rax
0x180008219  jz      loc_180008318
0x18000821f  lea     r8, [rsp+288h+pcbNeeded]; pcbNeeded
0x180008224  xor     ecx, ecx; pName
0x180008226  lea     rdx, [rsp+288h+FileName]; unsigned __int16 *
0x18000822b  call    ?InternalGetColorDirectory@@YAHPEBGPEAGPEAK@Z; InternalGetColorDirectory(ushort const *,ushort *,ulong *)
0x180008230  test    eax, eax
0x180008232  jnz     short loc_18000824C
0x180008234  call    cs:__imp_GetLastError
0x18000823a  test    eax, eax
0x18000823c  jz      loc_180008307
0x180008242  call    cs:__imp_GetLastError
0x180008248  mov     ebx, eax
0x18000824a  jmp     short loc_1800082AD
0x18000824c  lea     rcx, [rsp+288h+FileName]
0x180008251  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008255  inc     rax
0x180008258  cmp     [rcx+rax*2], r13w
0x18000825d  jnz     short loc_180008255
0x18000825f  cmp     [rsp+rax*2+288h+var_25A], 5Ch ; '\'
0x180008265  jz      short loc_180008283
0x180008267  lea     r8, gszBackslash; "\\"
0x18000826e  mov     edx, 104h; unsigned __int64
0x180008273  lea     rcx, [rsp+288h+FileName]; unsigned __int16 *
0x180008278  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000827d  mov     ecx, eax
0x18000827f  test    eax, eax
0x180008281  js      short loc_18000829B
0x180008283  mov     r8, rbx; unsigned __int16 *
0x180008286  lea     rcx, [rsp+288h+FileName]; unsigned __int16 *
0x18000828b  mov     edx, 104h; unsigned __int64
0x180008290  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008295  mov     ecx, eax
0x180008297  test    eax, eax
0x180008299  jns     short loc_1800082B3
0x18000829b  mov     eax, ecx
0x18000829d  movzx   ebx, cx
0x1800082a0  and     eax, 1FFF0000h
0x1800082a5  cmp     eax, 70000h
0x1800082aa  cmovnz  ebx, ecx
0x1800082ad  test    ebx, ebx
0x1800082af  jnz     short loc_180008330
0x1800082b1  jmp     short loc_1800082CB
0x1800082b3  lea     rcx, [rsp+288h+FileName]; lpFileName
0x1800082b8  call    cs:__imp_GetFileAttributesW
0x1800082be  mov     r12d, r13d
0x1800082c1  mov     ebx, r13d
0x1800082c4  cmp     eax, 0FFFFFFFFh
0x1800082c7  setnz   r12b
0x1800082cb  test    r12d, r12d
0x1800082ce  jnz     short loc_1800082EC
0x1800082d0  lea     r9, [rsp+288h+var_268]; unsigned int *
0x1800082d5  mov     r8, rdi; unsigned __int16 *
0x1800082d8  mov     edx, r15d; unsigned int
0x1800082db  mov     rcx, rsi; unsigned __int16 *
0x1800082de  call    ?RemoveStringFromMultiSz@@YAHPEAGKPEBGPEAK@Z; RemoveStringFromMultiSz(ushort *,ulong,ushort const *,ulong *)
0x1800082e3  test    eax, eax
0x1800082e5  jz      short loc_18000830E
0x1800082e7  mov     r15d, [rsp+288h+var_268]
0x1800082ec  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800082f0  inc     rax
0x1800082f3  cmp     [rdi+rax*2], r13w
0x1800082f8  jnz     short loc_1800082F0
0x1800082fa  lea     rdi, [rdi+rax*2]
0x1800082fe  add     rdi, 2
0x180008302  jmp     loc_1800081E4
0x180008307  mov     ebx, 80004005h
0x18000830c  jmp     short loc_180008330
0x18000830e  call    cs:__imp_GetLastError
0x180008314  mov     ebx, eax
0x180008316  jmp     short loc_180008330
0x180008318  mov     ebx, 57h ; 'W'
0x18000831d  jmp     short loc_180008330
0x18000831f  add     r8, r8; Size
0x180008322  mov     rdx, rsi; Src
0x180008325  mov     rcx, rbp; void *
0x180008328  call    memcpy_0
0x18000832d  mov     [r14], r15d
0x180008330  mov     rcx, rsi; lpMem
0x180008333  call    MemFree
0x180008338  jmp     short loc_18000833F
0x18000833a  mov     ebx, 8
0x18000833f  mov     eax, ebx
0x180008341  mov     rcx, [rsp+288h+var_48]
0x180008349  xor     rcx, rsp; StackCookie
0x18000834c  call    __security_check_cookie
0x180008351  mov     rbx, [rsp+288h+arg_10]
0x180008359  add     rsp, 250h
0x180008360  pop     r15
0x180008362  pop     r14
0x180008364  pop     r13
0x180008366  pop     r12
0x180008368  pop     rdi
0x180008369  pop     rsi
0x18000836a  pop     rbp
0x18000836b  retn
```
