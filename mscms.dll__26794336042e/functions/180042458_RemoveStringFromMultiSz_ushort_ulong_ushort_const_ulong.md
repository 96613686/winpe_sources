# RemoveStringFromMultiSz(ushort *,ulong,ushort const *,ulong *)

- ea: `0x180042458`
- end: `0x180042615`
- name: `?RemoveStringFromMultiSz@@YAHPEAGKPEBGPEAK@Z`
- size: `445`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000815c`
- `0x180042334`
- `0x18004364c`

## callees

- `0x1800098b0`
- `0x18002f2dc`
- `0x180042458`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800425c8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800425c8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800424e3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800424e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800425e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800425f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800425e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800425f8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180042547`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180042547`

## pseudocode

```c
_BOOL8 __fastcall RemoveStringFromMultiSz(
        unsigned __int16 *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int *a4)
{
  int v4; // edi
  __int64 cchCount2; // r15
  unsigned __int16 *v9; // r14
  unsigned int v10; // r13d
  int v11; // esi
  unsigned __int16 *v12; // r12
  __int64 v13; // r9
  int v14; // eax
  DWORD v15; // ecx
  int v16; // [rsp+70h] [rbp+8h]

  v4 = 0;
  if ( !a1 || !a3 || !a4 || a2 - 2 > 0x7FFFFFFD || a2 == 2 && (*a1 || a1[1]) )
  {
    SetLastError(0x57u);
    return 0;
  }
  else
  {
    cchCount2 = -1;
    do
      ++cchCount2;
    while ( a3[cchCount2] );
    if ( (_DWORD)cchCount2 )
    {
      v9 = (unsigned __int16 *)malloc(2LL * a2);
      if ( v9 )
      {
        v10 = 0;
        v11 = 0;
        v12 = a1;
        if ( a2 )
        {
          do
          {
            if ( !*v12 )
              break;
            v13 = -1;
            do
              ++v13;
            while ( v12[v13] );
            v16 = v13 + 1;
            if ( CompareStringW(0x7Fu, 1u, v12, v13, a3, cchCount2) == 2 )
            {
              v14 = v16;
            }
            else
            {
              v4 = StringCchCopyW(&v9[v11], a2 - v11, v12);
              if ( v4 < 0 )
                goto LABEL_27;
              v14 = v16;
              v11 += v16;
            }
            v10 += v14;
            v12 += v14;
          }
          while ( v10 < a2 );
          if ( v10 > a2 )
            goto LABEL_25;
        }
        if ( v11 + 1 > a2 )
        {
LABEL_25:
          v4 = -2147024809;
        }
        else
        {
          v9[v11] = 0;
          memcpy_0(a1, v9, 2LL * (unsigned int)(v11 + 1));
          *a4 = v11 + 1;
        }
      }
      else
      {
        v4 = -2147024882;
      }
LABEL_27:
      free(v9);
      if ( v4 < 0 )
      {
        v15 = (unsigned __int16)v4;
        if ( (v4 & 0x1FFF0000) != 0x70000 )
          v15 = v4;
        SetLastError(v15);
      }
      return v4 >= 0;
    }
    else
    {
      return 1;
    }
  }
}

```

## disassembly

```asm
0x180042458  mov     [rsp+arg_8], rbx
0x18004245d  mov     [rsp+arg_18], r9
0x180042462  mov     [rsp+arg_10], r8
0x180042467  push    rbp
0x180042468  push    rsi
0x180042469  push    rdi
0x18004246a  push    r12
0x18004246c  push    r13
0x18004246e  push    r14
0x180042470  push    r15
0x180042472  sub     rsp, 30h
0x180042476  xor     edi, edi
0x180042478  mov     ebx, edx
0x18004247a  mov     rax, r9
0x18004247d  mov     rbp, rcx
0x180042480  test    rcx, rcx
0x180042483  jz      loc_1800425F3
0x180042489  test    r8, r8
0x18004248c  jz      loc_1800425F3
0x180042492  test    rax, rax
0x180042495  jz      loc_1800425F3
0x18004249b  lea     eax, [rbx-2]
0x18004249e  cmp     eax, 7FFFFFFDh
0x1800424a3  ja      loc_1800425F3
0x1800424a9  cmp     ebx, 2
0x1800424ac  jnz     short loc_1800424C1
0x1800424ae  cmp     [rcx], di
0x1800424b1  jnz     loc_1800425F3
0x1800424b7  cmp     [rcx+2], di
0x1800424bb  jnz     loc_1800425F3
0x1800424c1  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800424c5  inc     r15
0x1800424c8  cmp     [r8+r15*2], di
0x1800424cd  jnz     short loc_1800424C5
0x1800424cf  test    r15d, r15d
0x1800424d2  jnz     short loc_1800424DD
0x1800424d4  lea     eax, [r15+1]
0x1800424d8  jmp     loc_180042600
0x1800424dd  mov     rcx, rbx
0x1800424e0  add     rcx, rcx; Size
0x1800424e3  call    cs:__imp_malloc
0x1800424e9  mov     r14, rax
0x1800424ec  test    rax, rax
0x1800424ef  jnz     short loc_1800424FB
0x1800424f1  mov     edi, 8007000Eh
0x1800424f6  jmp     loc_1800425C5
0x1800424fb  xor     edx, edx
0x1800424fd  mov     r13d, edi
0x180042500  mov     esi, edi
0x180042502  mov     r12, rbp
0x180042505  test    ebx, ebx
0x180042507  jz      loc_18004258E
0x18004250d  cmp     [r12], dx
0x180042512  jz      short loc_180042589
0x180042514  or      r9, 0FFFFFFFFFFFFFFFFh
0x180042518  inc     r9; cchCount1
0x18004251b  cmp     [r12+r9*2], dx
0x180042520  jnz     short loc_180042518
0x180042522  lea     eax, [r9+1]
0x180042526  mov     [rsp+68h+cchCount2], r15d; cchCount2
0x18004252b  mov     edx, 1; dwCmpFlags
0x180042530  mov     [rsp+68h+arg_0], eax
0x180042534  mov     rax, [rsp+68h+arg_10]
0x18004253c  mov     r8, r12; lpString1
0x18004253f  mov     [rsp+68h+lpString2], rax; lpString2
0x180042544  lea     ecx, [rdx+7Eh]; Locale
0x180042547  call    cs:__imp_CompareStringW
0x18004254d  cmp     eax, 2
0x180042550  jz      short loc_180042574
0x180042552  mov     eax, esi
0x180042554  mov     edx, ebx
0x180042556  sub     edx, esi; unsigned __int64
0x180042558  mov     r8, r12; unsigned __int16 *
0x18004255b  lea     rcx, [r14+rax*2]; unsigned __int16 *
0x18004255f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180042564  xor     edx, edx
0x180042566  mov     edi, eax
0x180042568  test    eax, eax
0x18004256a  js      short loc_1800425C5
0x18004256c  mov     eax, [rsp+68h+arg_0]
0x180042570  add     esi, eax
0x180042572  jmp     short loc_18004257A
0x180042574  mov     eax, [rsp+68h+arg_0]
0x180042578  xor     edx, edx
0x18004257a  movsxd  rcx, eax
0x18004257d  add     r13d, eax
0x180042580  lea     r12, [r12+rcx*2]
0x180042584  cmp     r13d, ebx
0x180042587  jb      short loc_18004250D
0x180042589  cmp     r13d, ebx
0x18004258c  ja      short loc_180042595
0x18004258e  lea     eax, [rsi+1]
0x180042591  cmp     eax, ebx
0x180042593  jbe     short loc_18004259C
0x180042595  mov     edi, 80070057h
0x18004259a  jmp     short loc_1800425C5
0x18004259c  test    edi, edi
0x18004259e  js      short loc_1800425C5
0x1800425a0  mov     ecx, esi
0x1800425a2  lea     ebx, [rsi+1]
0x1800425a5  mov     r8d, ebx
0x1800425a8  add     r8, r8; Size
0x1800425ab  mov     [r14+rcx*2], dx
0x1800425b0  mov     rdx, r14; Src
0x1800425b3  mov     rcx, rbp; void *
0x1800425b6  call    memcpy_0
0x1800425bb  mov     rax, [rsp+68h+arg_18]
0x1800425c3  mov     [rax], ebx
0x1800425c5  mov     rcx, r14; Block
0x1800425c8  call    cs:__imp_free
0x1800425ce  test    edi, edi
0x1800425d0  jns     short loc_1800425EA
0x1800425d2  mov     eax, edi
0x1800425d4  movzx   ecx, di
0x1800425d7  and     eax, 1FFF0000h
0x1800425dc  cmp     eax, 70000h
0x1800425e1  cmovnz  ecx, edi; dwErrCode
0x1800425e4  call    cs:__imp_SetLastError
0x1800425ea  not     edi
0x1800425ec  shr     edi, 1Fh
0x1800425ef  mov     eax, edi
0x1800425f1  jmp     short loc_180042600
0x1800425f3  mov     ecx, 57h ; 'W'; dwErrCode
0x1800425f8  call    cs:__imp_SetLastError
0x1800425fe  xor     eax, eax
0x180042600  mov     rbx, [rsp+68h+arg_8]
0x180042605  add     rsp, 30h
0x180042609  pop     r15
0x18004260b  pop     r14
0x18004260d  pop     r13
0x18004260f  pop     r12
0x180042611  pop     rdi
0x180042612  pop     rsi
0x180042613  pop     rbp
0x180042614  retn
```
