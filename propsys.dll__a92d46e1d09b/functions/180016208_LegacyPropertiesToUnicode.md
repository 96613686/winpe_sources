# _LegacyPropertiesToUnicode

- ea: `0x180016208`
- end: `0x18001633f`
- name: `_LegacyPropertiesToUnicode`
- size: `311`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015fc0`
- `0x180086cc0`
- `0x180086fd4`

## callees

- `0x180016208`
- `0x180016688`
- `0x180086fd4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800162d2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800162d2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180016293`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180016293`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800162e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800162e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800162a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800162a4`
- `SHCORE!__imp_SHAnsiToUnicodeCP` at `0x180016317`
- `SHCORE!__imp_SHAnsiToUnicodeCP` at `0x180016317`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall LegacyPropertiesToUnicode(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  UINT v5; // r15d
  int v6; // r12d
  unsigned int v7; // ebp
  unsigned int v8; // r9d
  __int64 i; // rdi
  const CHAR *v11; // rcx
  int v12; // r13d
  WCHAR *lpWideCharStr; // rax
  WCHAR *v14; // r14
  const CHAR *v15; // r8
  unsigned int cchWideChar; // r13d
  unsigned int v17; // [rsp+80h] [rbp+18h]

  v17 = a3;
  v5 = a2;
  v6 = a1;
  v7 = 0;
  if ( (unsigned int)IsAnsiPropertySet(a1, a2, a3, (unsigned int)a3) && v5 != 1200 )
  {
    for ( i = 0; (unsigned int)i < v8; i = (unsigned int)(i + 1) )
    {
      if ( *(_WORD *)(a5 + 24 * i) == 30 )
      {
        v11 = *(const CHAR **)(a5 + 24 * i + 8);
        if ( v11 )
        {
          v12 = lstrlenA(v11);
          lpWideCharStr = (WCHAR *)CoTaskMemAlloc(2LL * v12 + 2);
          v14 = lpWideCharStr;
          if ( !lpWideCharStr )
          {
            v7 = -2147024882;
            if ( (_DWORD)i )
              LegacyPropertiesToAnsi(v6, v5, i, a4, a5);
            return v7;
          }
          v15 = *(const CHAR **)(a5 + 24 * i + 8);
          if ( *v15 )
          {
            cchWideChar = v12 + 1;
            if ( !MultiByteToWideChar(v5, 0, v15, -1, lpWideCharStr, cchWideChar) )
              SHAnsiToUnicodeCP(65001, *(_QWORD *)(a5 + 24 * i + 8), v14, cchWideChar);
          }
          else
          {
            *lpWideCharStr = 0;
          }
          CoTaskMemFree(*(LPVOID *)(a5 + 24 * i + 8));
          v8 = v17;
          *(_QWORD *)(a5 + 24 * i + 8) = v14;
        }
        *(_WORD *)(a5 + 24 * i) = 31;
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180016208  mov     [rsp+arg_0], rbx
0x18001620d  mov     [rsp+arg_18], r9
0x180016212  mov     [rsp+arg_10], r8d
0x180016217  push    rbp
0x180016218  push    rsi
0x180016219  push    rdi
0x18001621a  push    r12
0x18001621c  push    r13
0x18001621e  push    r14
0x180016220  push    r15
0x180016222  sub     rsp, 30h
0x180016226  mov     r9d, r8d
0x180016229  mov     r15d, edx
0x18001622c  mov     r12, rcx
0x18001622f  xor     ebp, ebp
0x180016231  call    _IsAnsiPropertySet
0x180016236  test    eax, eax
0x180016238  jz      short loc_180016272
0x18001623a  cmp     r15d, 4B0h
0x180016241  jz      short loc_180016272
0x180016243  mov     rbx, [rsp+68h+arg_20]
0x18001624b  xor     edi, edi
0x18001624d  cmp     edi, r9d
0x180016250  jnb     short loc_180016272
0x180016252  lea     rsi, [rdi+rdi*2]
0x180016256  mov     eax, 1Eh
0x18001625b  cmp     ax, [rbx+rsi*8]
0x18001625f  jz      short loc_180016289
0x180016261  inc     edi
0x180016263  jmp     short loc_18001624D
0x180016265  mov     ebp, 8007000Eh
0x18001626a  test    edi, edi
0x18001626c  jnz     loc_18001631F
0x180016272  mov     rbx, [rsp+68h+arg_0]
0x180016277  mov     eax, ebp
0x180016279  add     rsp, 30h
0x18001627d  pop     r15
0x18001627f  pop     r14
0x180016281  pop     r13
0x180016283  pop     r12
0x180016285  pop     rdi
0x180016286  pop     rsi
0x180016287  pop     rbp
0x180016288  retn
0x180016289  mov     rcx, [rbx+rsi*8+8]; lpString
0x18001628e  test    rcx, rcx
0x180016291  jz      short loc_1800162F4
0x180016293  call    cs:__imp_lstrlenA
0x180016299  movsxd  r13, eax
0x18001629c  lea     rcx, ds:2[r13*2]; cb
0x1800162a4  call    cs:__imp_CoTaskMemAlloc
0x1800162aa  mov     r14, rax
0x1800162ad  test    rax, rax
0x1800162b0  jz      short loc_180016265
0x1800162b2  mov     r8, [rbx+rsi*8+8]; lpMultiByteStr
0x1800162b7  cmp     [r8], bpl
0x1800162ba  jz      short loc_1800162FF
0x1800162bc  inc     r13d
0x1800162bf  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800162c3  mov     [rsp+68h+cchWideChar], r13d; cchWideChar
0x1800162c8  xor     edx, edx; dwFlags
0x1800162ca  mov     ecx, r15d; CodePage
0x1800162cd  mov     [rsp+68h+lpWideCharStr], rax; lpWideCharStr
0x1800162d2  call    cs:__imp_MultiByteToWideChar
0x1800162d8  test    eax, eax
0x1800162da  jz      short loc_180016307
0x1800162dc  mov     rcx, [rbx+rsi*8+8]; pv
0x1800162e1  call    cs:__imp_CoTaskMemFree
0x1800162e7  mov     r9d, [rsp+68h+arg_10]
0x1800162ef  mov     [rbx+rsi*8+8], r14
0x1800162f4  mov     word ptr [rbx+rsi*8], 1Fh
0x1800162fa  jmp     loc_180016261
0x1800162ff  xor     eax, eax
0x180016301  mov     [r14], ax
0x180016305  jmp     short loc_1800162DC
0x180016307  mov     rdx, [rbx+rsi*8+8]
0x18001630c  mov     r9d, r13d
0x18001630f  mov     r8, r14
0x180016312  mov     ecx, 0FDE9h
0x180016317  call    cs:__imp_SHAnsiToUnicodeCP
0x18001631d  jmp     short loc_1800162DC
0x18001631f  mov     r9, [rsp+68h+arg_18]
0x180016327  mov     r8d, edi
0x18001632a  mov     edx, r15d
0x18001632d  mov     [rsp+68h+lpWideCharStr], rbx
0x180016332  mov     rcx, r12
0x180016335  call    _LegacyPropertiesToAnsi
0x18001633a  jmp     loc_180016272
```
