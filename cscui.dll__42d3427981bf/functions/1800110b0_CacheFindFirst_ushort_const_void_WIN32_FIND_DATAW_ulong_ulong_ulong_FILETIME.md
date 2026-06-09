# CacheFindFirst(ushort const *,void *,_WIN32_FIND_DATAW *,ulong *,ulong *,ulong *,_FILETIME *)

- ea: `0x1800110b0`
- end: `0x18001114f`
- name: `?CacheFindFirst@@YAPEAXPEBGPEAXPEAU_WIN32_FIND_DATAW@@PEAK33PEAU_FILETIME@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void *, struct _WIN32_FIND_DATAW *, unsigned int *, unsigned int *, unsigned int *, struct _FILETIME *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000db90`
- `0x18000dfc4`

## callees

- `0x1800110b0`
- `0x180011890`

## import_xrefs

- `CSCDLL!__imp_CSCFindClose` at `0x180011133`
- `CSCDLL!__imp_CSCFindClose` at `0x180011133`
- `CSCDLL!__imp_CSCFindNextFileW` at `0x18001111e`
- `CSCDLL!__imp_CSCFindNextFileW` at `0x18001111e`
- `CSCDLL!__imp_CSCFindFirstFileForSidW` at `0x1800110ec`
- `CSCDLL!__imp_CSCFindFirstFileForSidW` at `0x1800110ec`

## pseudocode

```c
__int64 __fastcall CacheFindFirst(
        const unsigned __int16 *a1,
        void *a2,
        struct _WIN32_FIND_DATAW *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int *a6,
        struct _FILETIME *a7)
{
  __int64 FileForSidW; // rbx

  FileForSidW = CSCFindFirstFileForSidW(a1, a2);
  if ( FileForSidW != -1 )
  {
    while ( (unsigned int)PathIsDotOrDotDotW(a3->cFileName) )
    {
      if ( !(unsigned int)CSCFindNextFileW(FileForSidW, a3, a4, a5, a6, a7) )
      {
        CSCFindClose(FileForSidW);
        return -1;
      }
    }
  }
  return FileForSidW;
}

```

## disassembly

```asm
0x1800110b0  push    rbx
0x1800110b2  push    rbp
0x1800110b3  push    rsi
0x1800110b4  push    rdi
0x1800110b5  push    r12
0x1800110b7  push    r14
0x1800110b9  push    r15
0x1800110bb  sub     rsp, 40h
0x1800110bf  mov     r14, [rsp+78h+arg_30]
0x1800110c7  mov     rbp, r9
0x1800110ca  mov     r15, [rsp+78h+arg_28]
0x1800110d2  mov     rdi, r8
0x1800110d5  mov     r12, [rsp+78h+arg_20]
0x1800110dd  mov     [rsp+78h+var_48], r14
0x1800110e2  mov     [rsp+78h+var_50], r15
0x1800110e7  mov     [rsp+78h+var_58], r12
0x1800110ec  call    cs:__imp_CSCFindFirstFileForSidW
0x1800110f2  mov     rbx, rax
0x1800110f5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800110f9  jz      short loc_18001113D
0x1800110fb  lea     rcx, [rdi+2Ch]; unsigned __int16 *
0x1800110ff  call    ?PathIsDotOrDotDotW@@YAHPEBG@Z; PathIsDotOrDotDotW(ushort const *)
0x180011104  test    eax, eax
0x180011106  jz      short loc_18001113D
0x180011108  mov     [rsp+78h+var_50], r14
0x18001110d  mov     r9, r12
0x180011110  mov     r8, rbp
0x180011113  mov     [rsp+78h+var_58], r15
0x180011118  mov     rdx, rdi
0x18001111b  mov     rcx, rbx
0x18001111e  call    cs:__imp_CSCFindNextFileW
0x180011124  test    eax, eax
0x180011126  jz      short loc_180011130
0x180011128  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001112c  jnz     short loc_1800110FB
0x18001112e  jmp     short loc_18001113D
0x180011130  mov     rcx, rbx
0x180011133  call    cs:__imp_CSCFindClose
0x180011139  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001113d  mov     rax, rbx
0x180011140  add     rsp, 40h
0x180011144  pop     r15
0x180011146  pop     r14
0x180011148  pop     r12
0x18001114a  pop     rdi
0x18001114b  pop     rsi
0x18001114c  pop     rbp
0x18001114d  pop     rbx
0x18001114e  retn
```
