# CreateFtpPidlFromUrlPathAndPidl(_ITEMIDLIST const *,char const *,_ITEMIDLIST * *)

- ea: `0x18001bc60`
- end: `0x18001bd0b`
- name: `?CreateFtpPidlFromUrlPathAndPidl@@YAJPEFBU_ITEMIDLIST@@PEBDPEAPEFAU1@@Z`
- size: `171`
- prototype: `int(const struct _ITEMIDLIST *, const char *, struct _ITEMIDLIST **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e358`

## callees

- `0x18001b614`
- `0x18001bc60`
- `0x18001bda4`

## import_xrefs

- `SHELL32!__imp_ILFindLastID` at `0x18001bc95`
- `SHELL32!__imp_ILFindLastID` at `0x18001bc95`
- `SHELL32!__imp_ILClone` at `0x18001bc7d`
- `SHELL32!__imp_ILClone` at `0x18001bc7d`
- `SHELL32!__imp_ILCombine` at `0x18001bcd1`
- `SHELL32!__imp_ILCombine` at `0x18001bcd1`
- `SHELL32!__imp_ILFree` at `0x18001bce2`
- `SHELL32!__imp_ILFree` at `0x18001bcf0`
- `SHELL32!__imp_ILFree` at `0x18001bce2`
- `SHELL32!__imp_ILFree` at `0x18001bcf0`

## pseudocode

```c
__int64 __fastcall CreateFtpPidlFromUrlPathAndPidl(
        const struct _ITEMIDLIST *a1,
        const char *a2,
        struct _ITEMIDLIST **a3)
{
  unsigned int v5; // esi
  const ITEMIDLIST *v6; // rbp
  LPITEMIDLIST ID; // rbx
  const ITEMIDLIST *v8; // rdx
  int FtpPidlFromFtpWirePath; // eax
  ITEMIDLIST *v10; // rdi
  LPCITEMIDLIST pidl2; // [rsp+68h] [rbp+20h] BYREF

  v5 = -2147467259;
  v6 = ILClone(a1);
  if ( v6 )
  {
    while ( 1 )
    {
      ID = ILFindLastID(v6);
      if ( (unsigned int)FtpID_IsServerItemID(ID) )
        break;
      ID->mkid.cb = 0;
    }
    pidl2 = 0;
    FtpPidlFromFtpWirePath = CreateFtpPidlFromFtpWirePath(a2, v8, (struct _ITEMIDLIST **)&pidl2);
    v10 = (ITEMIDLIST *)pidl2;
    v5 = FtpPidlFromFtpWirePath;
    if ( FtpPidlFromFtpWirePath >= 0 )
      *a3 = ILCombine(v6, pidl2);
    if ( ID )
      ILFree(ID);
    if ( v10 )
      ILFree(v10);
  }
  return v5;
}

```

## disassembly

```asm
0x18001bc60  mov     [rsp+arg_0], rbx
0x18001bc65  mov     [rsp+arg_8], rbp
0x18001bc6a  push    rsi
0x18001bc6b  push    rdi
0x18001bc6c  push    r14
0x18001bc6e  sub     rsp, 30h
0x18001bc72  mov     r14, r8
0x18001bc75  mov     rdi, rdx
0x18001bc78  mov     esi, 80004005h
0x18001bc7d  call    cs:__imp_ILClone
0x18001bc83  mov     rbp, rax
0x18001bc86  test    rax, rax
0x18001bc89  jz      short loc_18001BCF6
0x18001bc8b  jmp     short loc_18001BC92
0x18001bc8d  xor     eax, eax
0x18001bc8f  mov     [rbx], ax
0x18001bc92  mov     rcx, rbp; pidl
0x18001bc95  call    cs:__imp_ILFindLastID
0x18001bc9b  mov     rcx, rax; struct _ITEMIDLIST *
0x18001bc9e  mov     rbx, rax
0x18001bca1  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x18001bca6  test    eax, eax
0x18001bca8  jz      short loc_18001BC8D
0x18001bcaa  lea     r8, [rsp+48h+pidl2]; struct _ITEMIDLIST **
0x18001bcaf  mov     [rsp+48h+pidl2], 0
0x18001bcb8  mov     rcx, rdi; char *
0x18001bcbb  call    ?CreateFtpPidlFromFtpWirePath@@YAJPEBDPEAKPEAPEFAU_ITEMIDLIST@@HH@Z; CreateFtpPidlFromFtpWirePath(char const *,ulong *,_ITEMIDLIST * *,int,int)
0x18001bcc0  mov     rdi, [rsp+48h+pidl2]
0x18001bcc5  mov     esi, eax
0x18001bcc7  test    eax, eax
0x18001bcc9  js      short loc_18001BCDA
0x18001bccb  mov     rdx, rdi; pidl2
0x18001bcce  mov     rcx, rbp; pidl1
0x18001bcd1  call    cs:__imp_ILCombine
0x18001bcd7  mov     [r14], rax
0x18001bcda  test    rbx, rbx
0x18001bcdd  jz      short loc_18001BCE8
0x18001bcdf  mov     rcx, rbx; pidl
0x18001bce2  call    cs:__imp_ILFree
0x18001bce8  test    rdi, rdi
0x18001bceb  jz      short loc_18001BCF6
0x18001bced  mov     rcx, rdi; pidl
0x18001bcf0  call    cs:__imp_ILFree
0x18001bcf6  mov     rbx, [rsp+48h+arg_0]
0x18001bcfb  mov     eax, esi
0x18001bcfd  mov     rbp, [rsp+48h+arg_8]
0x18001bd02  add     rsp, 30h
0x18001bd06  pop     r14
0x18001bd08  pop     rdi
0x18001bd09  pop     rsi
0x18001bd0a  retn
```
