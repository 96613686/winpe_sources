# DuplicateString(ushort const *,ushort * *)

- ea: `0x140002ed4`
- end: `0x140002fa6`
- name: `?DuplicateString@@YAJPEBGPEAPEAG@Z`
- size: `210`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140006844`
- `0x140006a7c`

## callees

- `0x140001f9c`
- `0x1400023c4`
- `0x1400024bc`
- `0x140002ed4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140002f16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140002f16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140002f81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140002f81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002f51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002f51`

## string_xrefs

- `0x140002f99`: `DuplicateString (com\complus\dtc\shared\util\stringutil.cpp@100): DuplicateString, ppwszDest != NULL`
- `0x140002f2f`: `DuplicateString, CoTaskMemAlloc(dwSourceLength * sizeof(WCHAR)) failed`
- `0x140002f6c`: `DuplicateString, StringCchCopyW failed`

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
0x140002ed4  push    rbx
0x140002ed6  push    rbp
0x140002ed7  push    rsi
0x140002ed8  push    rdi
0x140002ed9  push    r14
0x140002edb  sub     rsp, 20h
0x140002edf  xor     r14d, r14d
0x140002ee2  mov     rdi, rdx
0x140002ee5  mov     rbp, rcx
0x140002ee8  test    rdx, rdx
0x140002eeb  jz      loc_140002F99
0x140002ef1  mov     [rdx], r14
0x140002ef4  mov     ebx, r14d
0x140002ef7  test    rcx, rcx
0x140002efa  jz      loc_140002F8C
0x140002f00  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002f04  inc     rax
0x140002f07  cmp     [rcx+rax*2], r14w
0x140002f0c  jnz     short loc_140002F04
0x140002f0e  inc     eax
0x140002f10  mov     ebx, eax
0x140002f12  lea     rcx, [rax+rax]; cb
0x140002f16  call    cs:__imp_CoTaskMemAlloc
0x140002f1c  mov     rsi, rax
0x140002f1f  test    rax, rax
0x140002f22  jnz     short loc_140002F3D
0x140002f24  mov     ebx, 8007000Eh
0x140002f29  lea     r9d, [rax+70h]; unsigned int
0x140002f2d  mov     ecx, ebx; int
0x140002f2f  lea     rdx, aDuplicatestrin; "DuplicateString, CoTaskMemAlloc(dwSourc"...
0x140002f36  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x140002f3b  jmp     short loc_140002F7E
0x140002f3d  mov     r8, rbp; unsigned __int16 *
0x140002f40  mov     rdx, rbx; unsigned __int64
0x140002f43  mov     rcx, rsi; unsigned __int16 *
0x140002f46  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140002f4b  mov     ebx, eax
0x140002f4d  test    eax, eax
0x140002f4f  jns     short loc_140002F89
0x140002f51  call    cs:__imp_GetLastError
0x140002f57  mov     ebx, eax
0x140002f59  test    eax, eax
0x140002f5b  jle     short loc_140002F66
0x140002f5d  movzx   ebx, ax
0x140002f60  or      ebx, 80070000h
0x140002f66  mov     r9d, 77h ; 'w'; unsigned int
0x140002f6c  lea     rdx, aDuplicatestrin_0; "DuplicateString, StringCchCopyW failed"
0x140002f73  mov     ecx, ebx; int
0x140002f75  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x140002f7a  test    ebx, ebx
0x140002f7c  jns     short loc_140002F8C
0x140002f7e  mov     rcx, rsi; pv
0x140002f81  call    cs:__imp_CoTaskMemFree
0x140002f87  jmp     short loc_140002F8C
0x140002f89  mov     [rdi], rsi
0x140002f8c  mov     eax, ebx
0x140002f8e  add     rsp, 20h
0x140002f92  pop     r14
0x140002f94  pop     rdi
0x140002f95  pop     rsi
0x140002f96  pop     rbp
0x140002f97  pop     rbx
0x140002f98  retn
0x140002f99  lea     rcx, aDuplicatestrin_1; "DuplicateString (com\\complus\\dtc\\sha"...
0x140002fa0  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
```
