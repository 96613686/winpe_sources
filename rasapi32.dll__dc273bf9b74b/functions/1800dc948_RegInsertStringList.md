# RegInsertStringList

- ea: `0x1800dc948`
- end: `0x1800dcb1d`
- name: `RegInsertStringList`
- size: `469`
- prototype: `__int64 __fastcall(HKEY hKey, LPCSTR lpValueName)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180040a68`
- `0x1800da4fc`

## callees

- `0x180015f3c`
- `0x18004e580`
- `0x18004e77c`
- `0x1800dc948`
- `0x1800ded06`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800dca89`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800dca89`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800dc998`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800dc998`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dca1c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dca65`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dca94`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dca1c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dca65`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dca94`

## pseudocode

```c
__int64 __fastcall RegInsertStringList(HKEY hKey, LPCSTR lpValueName, __int64 *a3)
{
  __int64 v3; // rax
  int v4; // r10d
  __int64 v8; // r9
  DWORD v9; // r14d
  SIZE_T v10; // rbp
  HGLOBAL v11; // rax
  void *v12; // rdi
  _QWORD *v13; // rcx
  unsigned int v14; // ebx
  __int64 v15; // rdx
  __int64 i; // rbx
  const char *v18; // rax
  STRSAFE_LPSTR *v19; // r9
  char *v20; // rsi
  BYTE *lpData; // [rsp+20h] [rbp-58h]
  DWORD cbData; // [rsp+28h] [rbp-50h]

  v3 = *a3;
  v4 = 0;
  while ( v3 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(*(_QWORD *)(v3 + 16) + 2 * v8) );
    v3 = *(_QWORD *)(v3 + 8);
    v4 += v8;
  }
  v9 = v4 + 1;
  v10 = (unsigned int)(v4 + 1);
  v11 = GlobalAlloc(0x40u, v10);
  v12 = v11;
  if ( !v11 )
  {
    v13 = WPP_GLOBAL_Control;
    v14 = 8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v15 = 18;
LABEL_11:
      WPP_SF_d(v13[2], v15, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v14);
    }
    return v14;
  }
  memset_0(v11, 0, v10);
  for ( i = *a3; i; i = *(_QWORD *)(i + 8) )
  {
    v18 = (const char *)StrdupWtoA(*(LPCWCH *)(i + 16));
    v20 = (char *)v18;
    if ( !v18 )
    {
      v14 = 8;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, 8);
      }
      GlobalFree(v12);
      return v14;
    }
    StringCchCatExA((STRSAFE_LPSTR)v12, v10, v18, v19, (size_t *)lpData, cbData);
    GlobalFree(v20);
  }
  v14 = RegSetValueExA(hKey, lpValueName, 0, 7u, (const BYTE *)v12, v9);
  GlobalFree(v12);
  if ( v14 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v15 = 20;
      goto LABEL_11;
    }
    return v14;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800dc948  push    rbx
0x1800dc94a  push    rbp
0x1800dc94b  push    rsi
0x1800dc94c  push    rdi
0x1800dc94d  push    r12
0x1800dc94f  push    r13
0x1800dc951  push    r14
0x1800dc953  push    r15
0x1800dc955  sub     rsp, 38h
0x1800dc959  mov     rax, [r8]
0x1800dc95c  xor     r13d, r13d
0x1800dc95f  mov     r10d, r13d
0x1800dc962  mov     rbx, r8
0x1800dc965  mov     r15, rdx
0x1800dc968  mov     r12, rcx
0x1800dc96b  jmp     short loc_1800DC986
0x1800dc96d  mov     r11, [rax+10h]
0x1800dc971  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800dc975  inc     r9
0x1800dc978  cmp     [r11+r9*2], r13w
0x1800dc97d  jnz     short loc_1800DC975
0x1800dc97f  mov     rax, [rax+8]
0x1800dc983  add     r10d, r9d
0x1800dc986  test    rax, rax
0x1800dc989  jnz     short loc_1800DC96D
0x1800dc98b  lea     r14d, [r10+1]
0x1800dc98f  mov     edx, r14d; dwBytes
0x1800dc992  lea     ecx, [rax+40h]; uFlags
0x1800dc995  mov     ebp, r14d
0x1800dc998  call    cs:__imp_GlobalAlloc
0x1800dc99e  mov     rdi, rax
0x1800dc9a1  test    rax, rax
0x1800dc9a4  jnz     short loc_1800DC9E5
0x1800dc9a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc9ad  lea     rax, WPP_GLOBAL_Control
0x1800dc9b4  lea     ebx, [rdi+8]
0x1800dc9b7  cmp     rcx, rax
0x1800dc9ba  jz      short loc_1800DC9DE
0x1800dc9bc  test    byte ptr [rcx+1Ch], 80h
0x1800dc9c0  jz      short loc_1800DC9DE
0x1800dc9c2  cmp     byte ptr [rcx+19h], 6
0x1800dc9c6  jb      short loc_1800DC9DE
0x1800dc9c8  lea     edx, [rdi+12h]
0x1800dc9cb  mov     rcx, [rcx+10h]
0x1800dc9cf  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800dc9d6  mov     r9d, ebx
0x1800dc9d9  call    WPP_SF_d
0x1800dc9de  mov     eax, ebx
0x1800dc9e0  jmp     loc_1800DCB0C
0x1800dc9e5  mov     r8, rbp; Size
0x1800dc9e8  xor     edx, edx; Val
0x1800dc9ea  mov     rcx, rdi; void *
0x1800dc9ed  call    memset_0
0x1800dc9f2  mov     rbx, [rbx]
0x1800dc9f5  test    rbx, rbx
0x1800dc9f8  jz      short loc_1800DCA70
0x1800dc9fa  mov     rcx, [rbx+10h]; lpWideCharStr
0x1800dc9fe  call    _StrdupWtoA
0x1800dca03  mov     rsi, rax
0x1800dca06  test    rax, rax
0x1800dca09  jz      short loc_1800DCA28
0x1800dca0b  mov     r8, rax; pszSrc
0x1800dca0e  mov     rdx, rbp; cchDest
0x1800dca11  mov     rcx, rdi; pszDest
0x1800dca14  call    StringCchCatExA
0x1800dca19  mov     rcx, rsi; hMem
0x1800dca1c  call    cs:__imp_GlobalFree
0x1800dca22  mov     rbx, [rbx+8]
0x1800dca26  jmp     short loc_1800DC9F5
0x1800dca28  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dca2f  lea     rax, WPP_GLOBAL_Control
0x1800dca36  mov     ebx, 8
0x1800dca3b  cmp     rcx, rax
0x1800dca3e  jz      short loc_1800DCA62
0x1800dca40  test    byte ptr [rcx+1Ch], 80h
0x1800dca44  jz      short loc_1800DCA62
0x1800dca46  cmp     byte ptr [rcx+19h], 6
0x1800dca4a  jb      short loc_1800DCA62
0x1800dca4c  mov     rcx, [rcx+10h]
0x1800dca50  lea     edx, [rbx+0Bh]
0x1800dca53  mov     r9d, ebx
0x1800dca56  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800dca5d  call    WPP_SF_d
0x1800dca62  mov     rcx, rdi; hMem
0x1800dca65  call    cs:__imp_GlobalFree
0x1800dca6b  jmp     loc_1800DC9DE
0x1800dca70  mov     [rsp+78h+cbData], r14d; cbData
0x1800dca75  mov     r9d, 7; dwType
0x1800dca7b  xor     r8d, r8d; Reserved
0x1800dca7e  mov     [rsp+78h+lpData], rdi; lpData
0x1800dca83  mov     rdx, r15; lpValueName
0x1800dca86  mov     rcx, r12; hKey
0x1800dca89  call    cs:__imp_RegSetValueExA
0x1800dca8f  mov     rcx, rdi; hMem
0x1800dca92  mov     ebx, eax
0x1800dca94  call    cs:__imp_GlobalFree
0x1800dca9a  test    ebx, ebx
0x1800dca9c  jz      short loc_1800DCAD3
0x1800dca9e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dcaa5  lea     rax, WPP_GLOBAL_Control
0x1800dcaac  cmp     rcx, rax
0x1800dcaaf  jz      loc_1800DC9DE
0x1800dcab5  test    byte ptr [rcx+1Ch], 80h
0x1800dcab9  jz      loc_1800DC9DE
0x1800dcabf  cmp     byte ptr [rcx+19h], 6
0x1800dcac3  jb      loc_1800DC9DE
0x1800dcac9  mov     edx, 14h
0x1800dcace  jmp     loc_1800DC9CB
0x1800dcad3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dcada  lea     rax, WPP_GLOBAL_Control
0x1800dcae1  cmp     rcx, rax
0x1800dcae4  jz      short loc_1800DCB0A
0x1800dcae6  test    byte ptr [rcx+1Ch], 80h
0x1800dcaea  jz      short loc_1800DCB0A
0x1800dcaec  cmp     byte ptr [rcx+19h], 6
0x1800dcaf0  jb      short loc_1800DCB0A
0x1800dcaf2  mov     rcx, [rcx+10h]
0x1800dcaf6  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800dcafd  mov     edx, 15h
0x1800dcb02  xor     r9d, r9d
0x1800dcb05  call    WPP_SF_d
0x1800dcb0a  xor     eax, eax
0x1800dcb0c  add     rsp, 38h
0x1800dcb10  pop     r15
0x1800dcb12  pop     r14
0x1800dcb14  pop     r13
0x1800dcb16  pop     r12
0x1800dcb18  pop     rdi
0x1800dcb19  pop     rsi
0x1800dcb1a  pop     rbp
0x1800dcb1b  pop     rbx
0x1800dcb1c  retn
```
