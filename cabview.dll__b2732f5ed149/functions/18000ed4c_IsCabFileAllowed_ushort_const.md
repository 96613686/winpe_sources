# IsCabFileAllowed(ushort const *)

- ea: `0x18000ed4c`
- end: `0x18000ede1`
- name: `?IsCabFileAllowed@@YA_NPEBG@Z`
- size: `149`
- prototype: `bool __fastcall(LPCWSTR pszPath)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x18000e190`

## callees

- `0x180002620`
- `0x180002f40`
- `0x18000ed4c`
- `0x18001226c`

## import_xrefs

- `SHLWAPI!PathCanonicalizeW` at `0x18000ed9a`
- `SHLWAPI!PathCanonicalizeW` at `0x18000ed9a`
- `SHLWAPI!PathIsRelativeW` at `0x18000ed76`
- `SHLWAPI!PathIsRelativeW` at `0x18000ed76`

## pseudocode

```c
bool __fastcall IsCabFileAllowed(unsigned __int16 *pszPath)
{
  WCHAR *v2; // rax
  signed __int64 v3; // rbx
  int v4; // edx
  int v5; // ecx
  WCHAR pszBuf[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( (unsigned int)PathIsInvalidW(pszPath) )
    return 0;
  if ( !PathIsRelativeW(pszPath) )
    return 0;
  memset_0(pszBuf, 0, 0x208u);
  if ( !PathCanonicalizeW(pszBuf, pszPath) )
    return 0;
  v2 = pszBuf;
  v3 = (char *)pszPath - (char *)pszBuf;
  do
  {
    v4 = *(WCHAR *)((char *)v2 + v3);
    v5 = *v2 - v4;
    if ( v5 )
      break;
    ++v2;
  }
  while ( v4 );
  return v5 == 0;
}

```

## disassembly

```asm
0x18000ed4c  push    rbx
0x18000ed4e  sub     rsp, 240h
0x18000ed55  mov     rax, cs:__security_cookie
0x18000ed5c  xor     rax, rsp
0x18000ed5f  mov     [rsp+248h+var_18], rax
0x18000ed67  mov     rbx, rcx
0x18000ed6a  call    PathIsInvalidW
0x18000ed6f  test    eax, eax
0x18000ed71  jnz     short loc_18000EDC6
0x18000ed73  mov     rcx, rbx; pszPath
0x18000ed76  call    cs:__imp_PathIsRelativeW
0x18000ed7c  test    eax, eax
0x18000ed7e  jz      short loc_18000EDC6
0x18000ed80  xor     edx, edx; Val
0x18000ed82  lea     rcx, [rsp+248h+pszBuf]; void *
0x18000ed87  mov     r8d, 208h; Size
0x18000ed8d  call    memset_0
0x18000ed92  mov     rdx, rbx; pszPath
0x18000ed95  lea     rcx, [rsp+248h+pszBuf]; pszBuf
0x18000ed9a  call    cs:__imp_PathCanonicalizeW
0x18000eda0  test    eax, eax
0x18000eda2  jz      short loc_18000EDC6
0x18000eda4  lea     rax, [rsp+248h+pszBuf]
0x18000eda9  sub     rbx, rax
0x18000edac  movzx   ecx, word ptr [rax]
0x18000edaf  movzx   edx, word ptr [rax+rbx]
0x18000edb3  sub     ecx, edx
0x18000edb5  jnz     short loc_18000EDBF
0x18000edb7  add     rax, 2
0x18000edbb  test    edx, edx
0x18000edbd  jnz     short loc_18000EDAC
0x18000edbf  test    ecx, ecx
0x18000edc1  setz    al
0x18000edc4  jmp     short loc_18000EDC8
0x18000edc6  xor     al, al
0x18000edc8  mov     rcx, [rsp+248h+var_18]
0x18000edd0  xor     rcx, rsp; StackCookie
0x18000edd3  call    __security_check_cookie
0x18000edd8  add     rsp, 240h
0x18000eddf  pop     rbx
0x18000ede0  retn
```
