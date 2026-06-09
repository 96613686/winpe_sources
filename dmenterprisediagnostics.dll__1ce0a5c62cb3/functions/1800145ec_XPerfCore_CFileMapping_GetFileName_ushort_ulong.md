# XPerfCore::CFileMapping::GetFileName(ushort *,ulong &)

- ea: `0x1800145ec`
- end: `0x18001463c`
- name: `?GetFileName@CFileMapping@XPerfCore@@QEAAKPEAGAEAK@Z`
- size: `80`
- prototype: `unsigned int __fastcall(XPerfCore::CFileMapping *__hidden this, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x1800121e8`

## callees

- `0x1800145ec`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180014613`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180014629`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180014613`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180014629`

## pseudocode

```c
__int64 __fastcall XPerfCore::CFileMapping::GetFileName(void **this, unsigned __int16 *a2, unsigned int *a3)
{
  void *v3; // rcx
  DWORD v6; // r8d
  DWORD FinalPathNameByHandleW; // eax

  v3 = *this;
  if ( v3 == (void *)-1LL )
    return 87;
  if ( a2 && (v6 = *a3) != 0 )
  {
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(v3, a2, v6, 0);
    if ( FinalPathNameByHandleW < *a3 )
      return 0;
  }
  else
  {
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(v3, 0, 0, 0);
  }
  *a3 = FinalPathNameByHandleW;
  return 122;
}

```

## disassembly

```asm
0x1800145ec  push    rbx
0x1800145ee  sub     rsp, 20h
0x1800145f2  mov     rcx, [rcx]; hFile
0x1800145f5  mov     rbx, r8
0x1800145f8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800145fc  jnz     short loc_180014603
0x1800145fe  lea     eax, [rcx+58h]
0x180014601  jmp     short loc_180014636
0x180014603  test    rdx, rdx
0x180014606  jz      short loc_180014621
0x180014608  mov     r8d, [r8]; cchFilePath
0x18001460b  test    r8d, r8d
0x18001460e  jz      short loc_180014621
0x180014610  xor     r9d, r9d; dwFlags
0x180014613  call    cs:__imp_GetFinalPathNameByHandleW
0x180014619  cmp     eax, [rbx]
0x18001461b  jnb     short loc_18001462F
0x18001461d  xor     eax, eax
0x18001461f  jmp     short loc_180014636
0x180014621  xor     r9d, r9d; dwFlags
0x180014624  xor     r8d, r8d; cchFilePath
0x180014627  xor     edx, edx; lpszFilePath
0x180014629  call    cs:__imp_GetFinalPathNameByHandleW
0x18001462f  mov     [rbx], eax
0x180014631  mov     eax, 7Ah ; 'z'
0x180014636  add     rsp, 20h
0x18001463a  pop     rbx
0x18001463b  retn
```
