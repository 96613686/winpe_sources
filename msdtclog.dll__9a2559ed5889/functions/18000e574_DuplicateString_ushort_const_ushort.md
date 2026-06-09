# DuplicateString(ushort const *,ushort * *)

- ea: `0x18000e574`
- end: `0x18000e646`
- name: `?DuplicateString@@YAJPEBGPEAPEAG@Z`
- size: `210`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012154`
- `0x18001238c`

## callees

- `0x18000ad1c`
- `0x18000da60`
- `0x18000dc8c`
- `0x18000e574`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e5b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e5b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e621`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e621`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5f1`

## string_xrefs

- `0x18000e639`: `DuplicateString (com\complus\dtc\shared\util\stringutil.cpp@100): DuplicateString, ppwszDest != NULL`
- `0x18000e5cf`: `DuplicateString, CoTaskMemAlloc(dwSourceLength * sizeof(WCHAR)) failed`
- `0x18000e60c`: `DuplicateString, StringCchCopyW failed`

## pseudocode

```c
__int64 __fastcall DuplicateString(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  signed int v4; // ebx
  __int64 v5; // rax
  unsigned __int64 v6; // rbx
  unsigned __int16 *v7; // rax
  const unsigned __int16 *v8; // r8
  unsigned __int16 *v9; // rsi
  signed int LastError; // eax
  const unsigned __int16 *v11; // r8

  if ( !a2 )
    DtcInternalErrorW(L"DuplicateString (com\\complus\\dtc\\shared\\util\\stringutil.cpp@100): DuplicateString, ppwszDest != NULL");
  *a2 = 0;
  v4 = 0;
  if ( a1 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a1[v5] );
    v6 = (unsigned int)(v5 + 1);
    v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * v6);
    v9 = v7;
    if ( !v7 )
    {
      v4 = -2147024882;
      TraceFileW(-2147024882, L"DuplicateString, CoTaskMemAlloc(dwSourceLength * sizeof(WCHAR)) failed", v8, 0x70u);
LABEL_11:
      CoTaskMemFree(v9);
      return (unsigned int)v4;
    }
    v4 = StringCchCopyW(v7, v6, a1);
    if ( v4 >= 0 )
    {
      *a2 = v9;
      return (unsigned int)v4;
    }
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    TraceFileW(v4, L"DuplicateString, StringCchCopyW failed", v11, 0x77u);
    if ( v4 < 0 )
      goto LABEL_11;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000e574  push    rbx
0x18000e576  push    rbp
0x18000e577  push    rsi
0x18000e578  push    rdi
0x18000e579  push    r14
0x18000e57b  sub     rsp, 20h
0x18000e57f  xor     r14d, r14d
0x18000e582  mov     rdi, rdx
0x18000e585  mov     rbp, rcx
0x18000e588  test    rdx, rdx
0x18000e58b  jz      loc_18000E639
0x18000e591  mov     [rdx], r14
0x18000e594  mov     ebx, r14d
0x18000e597  test    rcx, rcx
0x18000e59a  jz      loc_18000E62C
0x18000e5a0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e5a4  inc     rax
0x18000e5a7  cmp     [rcx+rax*2], r14w
0x18000e5ac  jnz     short loc_18000E5A4
0x18000e5ae  inc     eax
0x18000e5b0  mov     ebx, eax
0x18000e5b2  lea     rcx, [rax+rax]; cb
0x18000e5b6  call    cs:__imp_CoTaskMemAlloc
0x18000e5bc  mov     rsi, rax
0x18000e5bf  test    rax, rax
0x18000e5c2  jnz     short loc_18000E5DD
0x18000e5c4  mov     ebx, 8007000Eh
0x18000e5c9  lea     r9d, [rax+70h]; unsigned int
0x18000e5cd  mov     ecx, ebx; int
0x18000e5cf  lea     rdx, aDuplicatestrin; "DuplicateString, CoTaskMemAlloc(dwSourc"...
0x18000e5d6  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x18000e5db  jmp     short loc_18000E61E
0x18000e5dd  mov     r8, rbp; unsigned __int16 *
0x18000e5e0  mov     rdx, rbx; unsigned __int64
0x18000e5e3  mov     rcx, rsi; unsigned __int16 *
0x18000e5e6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e5eb  mov     ebx, eax
0x18000e5ed  test    eax, eax
0x18000e5ef  jns     short loc_18000E629
0x18000e5f1  call    cs:__imp_GetLastError
0x18000e5f7  mov     ebx, eax
0x18000e5f9  test    eax, eax
0x18000e5fb  jle     short loc_18000E606
0x18000e5fd  movzx   ebx, ax
0x18000e600  or      ebx, 80070000h
0x18000e606  mov     r9d, 77h ; 'w'; unsigned int
0x18000e60c  lea     rdx, aDuplicatestrin_0; "DuplicateString, StringCchCopyW failed"
0x18000e613  mov     ecx, ebx; int
0x18000e615  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x18000e61a  test    ebx, ebx
0x18000e61c  jns     short loc_18000E62C
0x18000e61e  mov     rcx, rsi; pv
0x18000e621  call    cs:__imp_CoTaskMemFree
0x18000e627  jmp     short loc_18000E62C
0x18000e629  mov     [rdi], rsi
0x18000e62c  mov     eax, ebx
0x18000e62e  add     rsp, 20h
0x18000e632  pop     r14
0x18000e634  pop     rdi
0x18000e635  pop     rsi
0x18000e636  pop     rbp
0x18000e637  pop     rbx
0x18000e638  retn
0x18000e639  lea     rcx, aDuplicatestrin_1; "DuplicateString (com\\complus\\dtc\\sha"...
0x18000e640  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
```
