# PerflibciLoadString

- ea: `0x180003810`
- end: `0x180003b2d`
- name: `PerflibciLoadString`
- size: `797`
- prototype: `__int64 __fastcall(HMODULE *, __int64, unsigned int, WORD, _WORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x1800044a0`

## callees

- `0x180003810`
- `0x180005da0`
- `0x180008042`
- `0x180008050`
- `0x18000df90`
- `0x18001e431`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800038b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003afc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800038b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003afc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800038e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180003948`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800038e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180003948`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800038a3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800039e2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800038a3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800039e2`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180003a51`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180003a51`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180003a60`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180003a60`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180003a72`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180003a72`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180003a39`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180003a39`

## pseudocode

```c
__int64 __fastcall PerflibciLoadString(HMODULE *a1, __int64 a2, unsigned int a3, WORD a4, _WORD *a5, _DWORD *a6)
{
  _DWORD *v10; // r12
  _WORD *v11; // rax
  DWORD v12; // ebx
  unsigned int v13; // r13d
  _WORD *v14; // r15
  HMODULE Library; // rax
  DWORD LastError; // eax
  __int16 *v17; // rcx
  __int16 v18; // ax
  UINT SystemWindowsDirectoryW; // eax
  unsigned int v20; // ecx
  __int64 v21; // rax
  __int64 v23; // r12
  WCHAR *v24; // rax
  unsigned __int16 *v25; // r15
  __int64 v26; // r8
  __int64 v27; // rax
  unsigned __int16 *v28; // rdx
  __int64 v29; // rcx
  const wchar_t *v30; // rdx
  unsigned __int16 *v31; // r9
  __int64 v32; // rax
  unsigned __int16 *v33; // rcx
  HMODULE v34; // rax
  HRSRC Resource; // rax
  HRSRC v36; // rbp
  unsigned __int64 v37; // r14
  HGLOBAL v38; // rax
  char *v39; // r8
  __int64 v40; // rdx
  int i; // edi
  size_t v42; // rdi
  unsigned int v44; // [rsp+78h] [rbp+10h]

  if ( !a2 )
    return 87;
  v10 = a6;
  if ( !a6 )
    return 87;
  v11 = *(_WORD **)(a2 + 16);
  if ( !v11 || !*v11 )
    return 13;
  v13 = *a6;
  v14 = a5;
  v44 = *a6;
  if ( !*a6 )
    goto LABEL_9;
  if ( !a5 )
    return 87;
  memset_0(a5, 0, v13);
LABEL_9:
  v12 = 0;
  if ( *a1 )
    goto LABEL_42;
  Library = LoadLibraryExW(*(LPCWSTR *)(a2 + 16), 0, 0x2Au);
  *a1 = Library;
  if ( Library )
    goto LABEL_42;
  LastError = GetLastError();
  v17 = *(__int16 **)(a2 + 16);
  v12 = LastError;
  while ( 1 )
  {
    v18 = *v17;
    if ( !*v17 )
      break;
    if ( v18 == 92 || v18 == 58 )
      goto LABEL_41;
    ++v17;
  }
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(0, 0);
  v20 = SystemWindowsDirectoryW + 16;
  if ( SystemWindowsDirectoryW < SystemWindowsDirectoryW + 16 )
  {
    v21 = -1;
    while ( *(_WORD *)(*(_QWORD *)(a2 + 16) + 2 * v21++ + 2) != 0 )
      ;
    v23 = v20 + (unsigned int)v21;
    if ( v20 < (unsigned int)v23 )
    {
      v24 = (WCHAR *)operator new(saturated_mul((unsigned int)v23, 2u));
      v25 = v24;
      if ( v24 )
      {
        GetSystemWindowsDirectoryW(v24, v23);
        v26 = 2147483646;
        if ( (unsigned __int64)(v23 - 1) <= 0x7FFFFFFE )
        {
          v27 = (unsigned int)v23;
          v28 = v25;
          while ( *v28 )
          {
            ++v28;
            if ( !--v27 )
            {
              v29 = 0;
              goto LABEL_27;
            }
          }
          v29 = (unsigned int)v23 - v27;
LABEL_27:
          if ( v27 )
          {
            v30 = L"\\syswow64\\";
            v31 = &v25[v29];
            v32 = (unsigned int)v23 - v29;
            if ( (unsigned int)v23 != v29 )
            {
              do
              {
                if ( !v26 )
                  break;
                if ( !*v30 )
                  break;
                *v31++ = *v30++;
                --v26;
                --v32;
              }
              while ( v32 );
            }
            v33 = v31 - 1;
            if ( v32 )
              v33 = v31;
            *v33 = 0;
          }
        }
        StringCchCatW(v25, (unsigned int)v23, *(const unsigned __int16 **)(a2 + 16));
        v34 = LoadLibraryExW(v25, 0, 0x2Au);
        *a1 = v34;
        if ( v34 )
          v12 = 0;
        else
          v12 = GetLastError();
        operator delete(v25);
      }
      v13 = v44;
      v14 = a5;
    }
    v10 = a6;
  }
LABEL_41:
  if ( !v12 )
  {
LABEL_42:
    Resource = FindResourceExW(*a1, (LPCWSTR)6, (LPCWSTR)(unsigned __int16)((a3 >> 4) + 1), a4);
    v36 = Resource;
    if ( !Resource
      || (v37 = SizeofResource(*a1, Resource), (v38 = LoadResource(*a1, v36)) == 0)
      || (v39 = (char *)LockResource(v38)) == 0 )
    {
      v12 = GetLastError();
LABEL_57:
      if ( !v12 && !*v14 )
        return 15100;
      return v12;
    }
    v40 = 0;
    for ( i = a3 & 0xF; i; --i )
    {
      v40 = (unsigned int)v40 + 2 * *(unsigned __int16 *)&v39[v40] + 2;
      if ( (unsigned int)v40 >= (unsigned int)v37 )
        return 13;
    }
    if ( v40 + 2 < v37 )
    {
      v42 = 2 * (unsigned int)*(unsigned __int16 *)&v39[v40];
      if ( (unsigned int)v40 + v42 + 2 <= v37 )
      {
        if ( v14 && v42 + 2 <= v13 )
          memcpy_0(v14, &v39[v40 + 2], v42);
        else
          v12 = 8;
        *v10 = v42 + 2;
        goto LABEL_57;
      }
    }
    return 13;
  }
  return v12;
}

```

## disassembly

```asm
0x180003810  push    rbx
0x180003812  push    rbp
0x180003813  push    rsi
0x180003814  push    rdi
0x180003815  push    r12
0x180003817  push    r13
0x180003819  push    r14
0x18000381b  push    r15
0x18000381d  sub     rsp, 28h
0x180003821  mov     r14d, r9d
0x180003824  mov     edi, r8d
0x180003827  mov     rbp, rdx
0x18000382a  mov     rsi, rcx
0x18000382d  test    rdx, rdx
0x180003830  jz      loc_180003B15
0x180003836  mov     r12, [rsp+68h+arg_28]
0x18000383e  test    r12, r12
0x180003841  jz      loc_180003B15
0x180003847  mov     rax, [rdx+10h]
0x18000384b  test    rax, rax
0x18000384e  jnz     short loc_18000385A
0x180003850  mov     ebx, 0Dh
0x180003855  jmp     loc_180003B1A
0x18000385a  cmp     word ptr [rax], 0
0x18000385e  jz      short loc_180003850
0x180003860  mov     r13d, [r12]
0x180003864  mov     r15, [rsp+68h+arg_20]
0x18000386c  mov     [rsp+68h+arg_8], r13d
0x180003871  test    r13d, r13d
0x180003874  jz      short loc_18000388C
0x180003876  test    r15, r15
0x180003879  jz      loc_180003B15
0x18000387f  mov     r8d, r13d; Size
0x180003882  xor     edx, edx; Val
0x180003884  mov     rcx, r15; void *
0x180003887  call    memset_0
0x18000388c  xor     ebx, ebx
0x18000388e  cmp     [rsi], rbx
0x180003891  jnz     loc_180003A21
0x180003897  mov     rcx, [rbp+10h]; lpLibFileName
0x18000389b  xor     edx, edx; hFile
0x18000389d  mov     r8d, 2Ah ; '*'; dwFlags
0x1800038a3  call    cs:__imp_LoadLibraryExW
0x1800038a9  mov     [rsi], rax
0x1800038ac  test    rax, rax
0x1800038af  jnz     loc_180003A21
0x1800038b5  call    cs:__imp_GetLastError
0x1800038bb  mov     rcx, [rbp+10h]
0x1800038bf  mov     ebx, eax
0x1800038c1  movzx   eax, word ptr [rcx]
0x1800038c4  test    ax, ax
0x1800038c7  jz      short loc_1800038E3
0x1800038c9  cmp     ax, 5Ch ; '\'
0x1800038cd  jz      loc_180003A19
0x1800038d3  cmp     ax, 3Ah ; ':'
0x1800038d7  jz      loc_180003A19
0x1800038dd  add     rcx, 2
0x1800038e1  jmp     short loc_1800038C1
0x1800038e3  xor     edx, edx; uSize
0x1800038e5  xor     ecx, ecx; lpBuffer
0x1800038e7  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800038ed  lea     ecx, [rax+10h]
0x1800038f0  cmp     eax, ecx
0x1800038f2  jnb     loc_180003A19
0x1800038f8  mov     rdx, [rbp+10h]
0x1800038fc  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180003903  mov     rax, r8
0x180003906  cmp     word ptr [rdx+rax*2+2], 0
0x18000390c  lea     rax, [rax+1]
0x180003910  jnz     short loc_180003906
0x180003912  lea     r12d, [rcx+rax]
0x180003916  cmp     ecx, r12d
0x180003919  jnb     loc_180003A11
0x18000391f  mov     r13d, r12d
0x180003922  mov     eax, 2
0x180003927  mul     r13
0x18000392a  cmovb   rax, r8
0x18000392e  mov     rcx, rax
0x180003931  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180003936  mov     r15, rax
0x180003939  test    rax, rax
0x18000393c  jz      loc_180003A04
0x180003942  mov     edx, r12d; uSize
0x180003945  mov     rcx, rax; lpBuffer
0x180003948  call    cs:__imp_GetSystemWindowsDirectoryW
0x18000394e  lea     rax, [r12-1]
0x180003953  mov     r8d, 7FFFFFFEh
0x180003959  cmp     rax, r8
0x18000395c  ja      short loc_1800039C8
0x18000395e  mov     eax, r13d
0x180003961  mov     rdx, r15
0x180003964  mov     ecx, r13d
0x180003967  cmp     word ptr [rdx], 0
0x18000396b  jz      short loc_18000397B
0x18000396d  add     rdx, 2
0x180003971  sub     rax, 1
0x180003975  jnz     short loc_180003967
0x180003977  xor     ecx, ecx
0x180003979  jmp     short loc_18000397E
0x18000397b  sub     rcx, rax
0x18000397e  test    rax, rax
0x180003981  jz      short loc_1800039C8
0x180003983  mov     rax, r13
0x180003986  lea     rdx, aSyswow64; "\\syswow64\\"
0x18000398d  lea     r9, [r15+rcx*2]
0x180003991  sub     rax, rcx
0x180003994  jz      short loc_1800039B8
0x180003996  test    r8, r8
0x180003999  jz      short loc_1800039B8
0x18000399b  movzx   ecx, word ptr [rdx]
0x18000399e  test    cx, cx
0x1800039a1  jz      short loc_1800039B8
0x1800039a3  mov     [r9], cx
0x1800039a7  add     rdx, 2
0x1800039ab  add     r9, 2
0x1800039af  dec     r8
0x1800039b2  sub     rax, 1
0x1800039b6  jnz     short loc_180003996
0x1800039b8  test    rax, rax
0x1800039bb  lea     rcx, [r9-2]
0x1800039bf  cmovnz  rcx, r9
0x1800039c3  xor     eax, eax
0x1800039c5  mov     [rcx], ax
0x1800039c8  mov     r8, [rbp+10h]; unsigned __int16 *
0x1800039cc  mov     rdx, r13; unsigned __int64
0x1800039cf  mov     rcx, r15; unsigned __int16 *
0x1800039d2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800039d7  xor     edx, edx; hFile
0x1800039d9  mov     r8d, 2Ah ; '*'; dwFlags
0x1800039df  mov     rcx, r15; lpLibFileName
0x1800039e2  call    cs:__imp_LoadLibraryExW
0x1800039e8  mov     [rsi], rax
0x1800039eb  test    rax, rax
0x1800039ee  jz      short loc_1800039F4
0x1800039f0  xor     ebx, ebx
0x1800039f2  jmp     short loc_1800039FC
0x1800039f4  call    cs:__imp_GetLastError
0x1800039fa  mov     ebx, eax
0x1800039fc  mov     rcx, r15; Block
0x1800039ff  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003a04  mov     r13d, [rsp+68h+arg_8]
0x180003a09  mov     r15, [rsp+68h+arg_20]
0x180003a11  mov     r12, [rsp+68h+arg_28]
0x180003a19  test    ebx, ebx
0x180003a1b  jnz     loc_180003B1A
0x180003a21  mov     rcx, [rsi]; hModule
0x180003a24  mov     eax, edi
0x180003a26  shr     eax, 4
0x180003a29  movzx   r9d, r14w; wLanguage
0x180003a2d  inc     ax
0x180003a30  mov     edx, 6; lpType
0x180003a35  movzx   r8d, ax; lpName
0x180003a39  call    cs:__imp_FindResourceExW
0x180003a3f  mov     rbp, rax
0x180003a42  test    rax, rax
0x180003a45  jz      loc_180003AFC
0x180003a4b  mov     rcx, [rsi]; hModule
0x180003a4e  mov     rdx, rax; hResInfo
0x180003a51  call    cs:__imp_SizeofResource
0x180003a57  mov     rcx, [rsi]; hModule
0x180003a5a  mov     rdx, rbp; hResInfo
0x180003a5d  mov     r14d, eax
0x180003a60  call    cs:__imp_LoadResource
0x180003a66  test    rax, rax
0x180003a69  jz      loc_180003AFC
0x180003a6f  mov     rcx, rax; hResData
0x180003a72  call    cs:__imp_LockResource
0x180003a78  mov     r8, rax
0x180003a7b  test    rax, rax
0x180003a7e  jz      short loc_180003AFC
0x180003a80  xor     edx, edx
0x180003a82  and     edi, 0Fh
0x180003a85  mov     ecx, edx
0x180003a87  test    edi, edi
0x180003a89  jz      short loc_180003AA3
0x180003a8b  movzx   eax, word ptr [rdx+r8]
0x180003a90  lea     edx, [rdx+rax*2]
0x180003a93  add     edx, 2
0x180003a96  cmp     edx, r14d
0x180003a99  jnb     loc_180003850
0x180003a9f  dec     edi
0x180003aa1  jmp     short loc_180003A85
0x180003aa3  lea     rax, [rdx+2]
0x180003aa7  cmp     rax, r14
0x180003aaa  jnb     loc_180003850
0x180003ab0  movzx   eax, word ptr [rdx+r8]
0x180003ab5  lea     r9, [rdx+r8]
0x180003ab9  lea     edi, [rax+rax]
0x180003abc  lea     rax, [rdi+2]
0x180003ac0  mov     r8d, edi; Size
0x180003ac3  add     rax, rcx
0x180003ac6  cmp     rax, r14
0x180003ac9  ja      loc_180003850
0x180003acf  test    r15, r15
0x180003ad2  jz      short loc_180003AEE
0x180003ad4  lea     rcx, [rdi+2]
0x180003ad8  mov     eax, r13d
0x180003adb  cmp     rcx, rax
0x180003ade  ja      short loc_180003AEE
0x180003ae0  lea     rdx, [r9+2]; Src
0x180003ae4  mov     rcx, r15; void *
0x180003ae7  call    memcpy_0
0x180003aec  jmp     short loc_180003AF3
0x180003aee  mov     ebx, 8
0x180003af3  lea     eax, [rdi+2]
0x180003af6  mov     [r12], eax
0x180003afa  jmp     short loc_180003B04
0x180003afc  call    cs:__imp_GetLastError
0x180003b02  mov     ebx, eax
0x180003b04  test    ebx, ebx
0x180003b06  jnz     short loc_180003B1A
0x180003b08  cmp     [r15], bx
0x180003b0c  jnz     short loc_180003B1A
0x180003b0e  mov     ebx, 3AFCh
0x180003b13  jmp     short loc_180003B1A
0x180003b15  mov     ebx, 57h ; 'W'
0x180003b1a  mov     eax, ebx
0x180003b1c  add     rsp, 28h
0x180003b20  pop     r15
0x180003b22  pop     r14
0x180003b24  pop     r13
0x180003b26  pop     r12
0x180003b28  pop     rdi
0x180003b29  pop     rsi
0x180003b2a  pop     rbp
0x180003b2b  pop     rbx
0x180003b2c  retn
```
