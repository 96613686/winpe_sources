# ForceDelete

- ea: `0x180013610`
- end: `0x180013685`
- name: `ForceDelete`
- size: `117`
- prototype: `signed int __fastcall(unsigned int, const WCHAR *, _DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18001351c`
- `0x180013610`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001364f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001364f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180013645`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180013645`

## pseudocode

```c
signed int __fastcall ForceDelete(unsigned int a1, const WCHAR *a2, _DWORD *a3)
{
  signed int result; // eax
  bool v7; // sf

  if ( !a2 || !a3 )
    return -2147024809;
  if ( a1 > 1 || (*a3 & 1) == 0 || SetFileAttributesW(a2, *a3 & 0xFFFFFFFE) )
    return Delete(a1, a2, (__int64)a3);
  result = GetLastError();
  v7 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v7 = result < 0;
  }
  if ( !v7 )
    return Delete(a1, a2, (__int64)a3);
  return result;
}

```

## disassembly

```asm
0x180013610  push    rbx
0x180013612  push    rbp
0x180013613  push    rsi
0x180013614  push    rdi
0x180013615  sub     rsp, 28h
0x180013619  mov     rbp, r9
0x18001361c  mov     rbx, r8
0x18001361f  mov     rsi, rdx
0x180013622  mov     edi, ecx
0x180013624  test    rdx, rdx
0x180013627  jz      short loc_180013677
0x180013629  test    rbx, rbx
0x18001362c  jz      short loc_180013677
0x18001362e  test    ecx, ecx
0x180013630  jz      short loc_180013637
0x180013632  cmp     ecx, 1
0x180013635  jnz     short loc_180013665
0x180013637  mov     edx, [r8]
0x18001363a  test    dl, 1
0x18001363d  jz      short loc_180013665
0x18001363f  and     edx, 0FFFFFFFEh; dwFileAttributes
0x180013642  mov     rcx, rsi; lpFileName
0x180013645  call    cs:__imp_SetFileAttributesW
0x18001364b  test    eax, eax
0x18001364d  jnz     short loc_180013665
0x18001364f  call    cs:__imp_GetLastError
0x180013655  test    eax, eax
0x180013657  jle     short loc_180013663
0x180013659  movzx   eax, ax
0x18001365c  or      eax, 80070000h
0x180013661  test    eax, eax
0x180013663  js      short loc_18001367C
0x180013665  mov     r9, rbp
0x180013668  mov     r8, rbx
0x18001366b  mov     rdx, rsi
0x18001366e  mov     ecx, edi
0x180013670  call    Delete
0x180013675  jmp     short loc_18001367C
0x180013677  mov     eax, 80070057h
0x18001367c  add     rsp, 28h
0x180013680  pop     rdi
0x180013681  pop     rsi
0x180013682  pop     rbp
0x180013683  pop     rbx
0x180013684  retn
```
