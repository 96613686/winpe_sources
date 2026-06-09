# CPackage::CreateTempFile(bool)

- ea: `0x180007934`
- end: `0x1800079a4`
- name: `?CreateTempFile@CPackage@@IEAAJ_N@Z`
- size: `112`
- prototype: `__int64 __fastcall(CPackage *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800050b0`
- `0x180006af0`

## callees

- `0x180007934`
- `0x1800079ac`
- `0x1800095e0`

## import_xrefs

- `SHLWAPI!PathFileExistsW` at `0x180007956`
- `SHLWAPI!PathFileExistsW` at `0x180007956`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18000797b`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18000797b`

## pseudocode

```c
__int64 __fastcall CPackage::CreateTempFile(CPackage *this)
{
  __int64 result; // rax
  const WCHAR *v3; // rcx

  result = CPackage::CreateTempFileName(this);
  if ( (int)result >= 0 )
  {
    v3 = *(const WCHAR **)(*((_QWORD *)this + 14) + 592LL);
    if ( !v3 || !PathFileExistsW(v3) )
    {
      if ( !*((_DWORD *)this + 32)
        && !CopyFileW((LPCWSTR)(*((_QWORD *)this + 14) + 72LL), *(LPCWSTR *)(*((_QWORD *)this + 14) + 592LL), 0) )
      {
        return 2147500037LL;
      }
      MarkFileUnsafe(*(const unsigned __int16 **)(*((_QWORD *)this + 14) + 592LL));
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180007934  push    rbx
0x180007936  sub     rsp, 20h
0x18000793a  mov     rbx, rcx
0x18000793d  call    ?CreateTempFileName@CPackage@@IEAAJXZ; CPackage::CreateTempFileName(void)
0x180007942  test    eax, eax
0x180007944  js      short loc_18000799E
0x180007946  mov     rax, [rbx+70h]
0x18000794a  mov     rcx, [rax+250h]; pszPath
0x180007951  test    rcx, rcx
0x180007954  jz      short loc_180007960
0x180007956  call    cs:__imp_PathFileExistsW
0x18000795c  test    eax, eax
0x18000795e  jnz     short loc_18000799C
0x180007960  cmp     dword ptr [rbx+80h], 0
0x180007967  jnz     short loc_18000798C
0x180007969  mov     rdx, [rbx+70h]
0x18000796d  xor     r8d, r8d; bFailIfExists
0x180007970  lea     rcx, [rdx+48h]; lpExistingFileName
0x180007974  mov     rdx, [rdx+250h]; lpNewFileName
0x18000797b  call    cs:__imp_CopyFileW
0x180007981  test    eax, eax
0x180007983  jnz     short loc_18000798C
0x180007985  mov     eax, 80004005h
0x18000798a  jmp     short loc_18000799E
0x18000798c  mov     rcx, [rbx+70h]
0x180007990  mov     rcx, [rcx+250h]; unsigned __int16 *
0x180007997  call    ?MarkFileUnsafe@@YAJPEBG@Z; MarkFileUnsafe(ushort const *)
0x18000799c  xor     eax, eax
0x18000799e  add     rsp, 20h
0x1800079a2  pop     rbx
0x1800079a3  retn
```
