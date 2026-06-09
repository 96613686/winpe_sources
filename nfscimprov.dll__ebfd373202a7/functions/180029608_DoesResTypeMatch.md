# DoesResTypeMatch

- ea: `0x180029608`
- end: `0x18002965a`
- name: `DoesResTypeMatch`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002ad9c`
- `0x18002afc0`

## callees

- `0x180029608`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180029647`
- `KERNEL32!GetLastError` at `0x180029647`
- `RESUTILS!ResUtilResourceTypesEqual` at `0x18002962d`
- `RESUTILS!ResUtilResourceTypesEqual` at `0x18002962d`
- `CLUSAPI!OpenClusterResource` at `0x180029617`
- `CLUSAPI!OpenClusterResource` at `0x180029617`
- `CLUSAPI!CloseClusterResource` at `0x18002963f`
- `CLUSAPI!CloseClusterResource` at `0x18002963f`

## pseudocode

```c
__int64 __fastcall DoesResTypeMatch(struct _HCLUSTER *a1, const WCHAR *a2, const WCHAR *a3, struct _HRESOURCE **a4)
{
  struct _HRESOURCE *v6; // rax
  struct _HRESOURCE *v7; // rbx
  unsigned int v8; // edi

  v6 = OpenClusterResource(a1, a2);
  v7 = v6;
  if ( v6 )
  {
    v8 = 0;
    if ( ResUtilResourceTypesEqual(a3, v6) )
      *a4 = v7;
    else
      CloseClusterResource(v7);
  }
  else
  {
    return GetLastError();
  }
  return v8;
}

```

## disassembly

```asm
0x180029608  push    rbx
0x18002960a  push    rbp
0x18002960b  push    rsi
0x18002960c  push    rdi
0x18002960d  sub     rsp, 28h
0x180029611  mov     rsi, r9
0x180029614  mov     rbp, r8
0x180029617  call    cs:__imp_OpenClusterResource
0x18002961d  mov     rbx, rax
0x180029620  test    rax, rax
0x180029623  jz      short loc_180029647
0x180029625  mov     rdx, rax; hResource
0x180029628  mov     rcx, rbp; lpszResourceTypeName
0x18002962b  xor     edi, edi
0x18002962d  call    cs:__imp_ResUtilResourceTypesEqual
0x180029633  test    eax, eax
0x180029635  jz      short loc_18002963C
0x180029637  mov     [rsi], rbx
0x18002963a  jmp     short loc_18002964F
0x18002963c  mov     rcx, rbx; hResource
0x18002963f  call    cs:__imp_CloseClusterResource
0x180029645  jmp     short loc_18002964F
0x180029647  call    cs:__imp_GetLastError
0x18002964d  mov     edi, eax
0x18002964f  mov     eax, edi
0x180029651  add     rsp, 28h
0x180029655  pop     rdi
0x180029656  pop     rsi
0x180029657  pop     rbp
0x180029658  pop     rbx
0x180029659  retn
```
