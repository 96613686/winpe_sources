# HrAthGetFileName

- ea: `0x18008e200`
- end: `0x18008e2dd`
- name: `HrAthGetFileName`
- size: `221`
- prototype: `__int64 __fastcall(LPOPENFILENAMEA)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x18008e160`
- `0x18008e200`
- `0x1800cb864`
- `0x1800cb93c`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!PszToANSI` at `0x18008e238`
- `MSOERT2!PszToANSI` at `0x18008e238`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18008e2af`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18008e2af`
- `SHLWAPI!PathIsDirectoryW` at `0x18008e2a2`
- `SHLWAPI!PathIsDirectoryW` at `0x18008e2a2`
- `SHLWAPI!PathFileExistsW` at `0x18008e224`
- `SHLWAPI!PathFileExistsW` at `0x18008e224`
- `KERNEL32!MultiByteToWideChar` at `0x18008e299`
- `KERNEL32!MultiByteToWideChar` at `0x18008e299`

## pseudocode

```c
__int64 __fastcall HrAthGetFileName(LPOPENFILENAMEA a1, int a2)
{
  const CHAR *v2; // rsi
  const CHAR *v5; // rax
  unsigned int v6; // edi
  BOOL OpenFileNameA; // eax
  const CHAR *lpstrFile; // r8
  __int64 v9; // r9

  a1->Flags |= 8u;
  v2 = 0;
  if ( !a1->lpstrInitialDir )
  {
    if ( !PathFileExistsW(&g_wszLastDir) )
      SetDefaultSpecialFolderPath();
    v5 = (const CHAR *)PszToANSI(0, &g_wszLastDir);
    v2 = v5;
    if ( !v5 )
    {
      v6 = -2147024882;
      goto LABEL_19;
    }
    a1->lpstrInitialDir = v5;
  }
  if ( a2 )
    OpenFileNameA = GetOpenFileNameA(a1);
  else
    OpenFileNameA = GetSaveFileNameA(a1);
  if ( OpenFileNameA )
  {
    lpstrFile = a1->lpstrFile;
    v6 = 0;
    if ( lpstrFile )
    {
      v9 = -1;
      do
        ++v9;
      while ( lpstrFile[v9] );
    }
    else
    {
      LODWORD(v9) = 0;
    }
    MultiByteToWideChar(0, 1u, lpstrFile, v9, &g_wszLastDir, 260);
    if ( !PathIsDirectoryW(&g_wszLastDir) )
      PathRemoveFileSpecW(&g_wszLastDir);
  }
  else
  {
    v6 = -2147467259;
  }
LABEL_19:
  ((void (__fastcall *)(LPMALLOC, const CHAR *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v2);
  return v6;
}

```

## disassembly

```asm
0x18008e200  push    rbx
0x18008e202  push    rbp
0x18008e203  push    rsi
0x18008e204  push    rdi
0x18008e205  sub     rsp, 38h
0x18008e209  or      dword ptr [rcx+60h], 8
0x18008e20d  lea     rbp, ?g_wszLastDir@@3PAGA; ushort near * g_wszLastDir
0x18008e214  xor     esi, esi
0x18008e216  mov     edi, edx
0x18008e218  mov     rbx, rcx
0x18008e21b  cmp     [rcx+50h], rsi
0x18008e21f  jnz     short loc_18008E251
0x18008e221  mov     rcx, rbp; pszPath
0x18008e224  call    cs:__imp_PathFileExistsW
0x18008e22a  test    eax, eax
0x18008e22c  jnz     short loc_18008E233
0x18008e22e  call    ?SetDefaultSpecialFolderPath@@YAJXZ; SetDefaultSpecialFolderPath(void)
0x18008e233  mov     rdx, rbp
0x18008e236  xor     ecx, ecx
0x18008e238  call    cs:__imp_PszToANSI
0x18008e23e  mov     rsi, rax
0x18008e241  test    rax, rax
0x18008e244  jnz     short loc_18008E24D
0x18008e246  mov     edi, 8007000Eh
0x18008e24b  jmp     short loc_18008E2BC
0x18008e24d  mov     [rbx+50h], rax
0x18008e251  mov     rcx, rbx; LPOPENFILENAMEA
0x18008e254  test    edi, edi
0x18008e256  jz      short loc_18008E25F
0x18008e258  call    GetOpenFileNameA
0x18008e25d  jmp     short loc_18008E264
0x18008e25f  call    GetSaveFileNameA
0x18008e264  test    eax, eax
0x18008e266  jz      short loc_18008E2B7
0x18008e268  mov     r8, [rbx+30h]; lpMultiByteStr
0x18008e26c  xor     edi, edi
0x18008e26e  test    r8, r8
0x18008e271  jz      short loc_18008E282
0x18008e273  or      r9, 0FFFFFFFFFFFFFFFFh
0x18008e277  inc     r9
0x18008e27a  cmp     [r8+r9], dil
0x18008e27e  jnz     short loc_18008E277
0x18008e280  jmp     short loc_18008E285
0x18008e282  xor     r9d, r9d; cbMultiByte
0x18008e285  mov     [rsp+58h+cchWideChar], 104h; cchWideChar
0x18008e28d  mov     edx, 1; dwFlags
0x18008e292  xor     ecx, ecx; CodePage
0x18008e294  mov     [rsp+58h+lpWideCharStr], rbp; lpWideCharStr
0x18008e299  call    cs:__imp_MultiByteToWideChar
0x18008e29f  mov     rcx, rbp; pszPath
0x18008e2a2  call    cs:__imp_PathIsDirectoryW
0x18008e2a8  test    eax, eax
0x18008e2aa  jnz     short loc_18008E2BC
0x18008e2ac  mov     rcx, rbp; pszPath
0x18008e2af  call    cs:__imp_PathRemoveFileSpecW
0x18008e2b5  jmp     short loc_18008E2BC
0x18008e2b7  mov     edi, 80004005h
0x18008e2bc  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18008e2c3  mov     rdx, [rcx]
0x18008e2c6  mov     rax, [rdx+28h]
0x18008e2ca  mov     rdx, rsi
0x18008e2cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e2d2  mov     eax, edi
0x18008e2d4  add     rsp, 38h
0x18008e2d8  pop     rdi
0x18008e2d9  pop     rsi
0x18008e2da  pop     rbp
0x18008e2db  pop     rbx
0x18008e2dc  retn
```
