# CFtpStm::Stat(tagSTATSTG *,ulong)

- ea: `0x180021440`
- end: `0x180021500`
- name: `?Stat@CFtpStm@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `192`
- prototype: `int(CFtpStm *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002b60`
- `0x18001c7a8`
- `0x18001c908`
- `0x180021440`

## import_xrefs

- `SHELL32!__imp_ILFindLastID` at `0x180021471`
- `SHELL32!__imp_ILFindLastID` at `0x180021487`
- `SHELL32!__imp_ILFindLastID` at `0x180021471`
- `SHELL32!__imp_ILFindLastID` at `0x180021487`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800214cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800214cf`

## pseudocode

```c
int __fastcall CFtpStm::Stat(LPCITEMIDLIST *this, struct _FILETIME *a2, char a3)
{
  const struct _ITEMIDLIST *ID; // rax
  LPITEMIDLIST v7; // rax
  struct _FILETIME v8; // rcx
  DWORD dwLowDateTime; // ecx
  unsigned __int16 *v11; // rax
  unsigned int v12; // r8d

  memset_0(a2, 0, 0x50u);
  a2[1].dwLowDateTime = 2;
  ID = ILFindLastID(this[6]);
  a2[3] = FtpPidl_GetFileTime(ID);
  v7 = ILFindLastID(this[6]);
  v8 = 0;
  if ( v7->mkid.cb >= 0x27u && (*(_DWORD *)&v7[2].mkid.cb & 0xFFFCFFC2) == 0 )
    v8 = *(struct _FILETIME *)v7[4].mkid.abID;
  a2[2] = v8;
  dwLowDateTime = a2[6].dwLowDateTime;
  a2[6].dwLowDateTime = dwLowDateTime | 0x10;
  if ( ((_DWORD)this[3] & 0x40000000) != 0 )
    a2[6].dwLowDateTime = dwLowDateTime | 0x11;
  if ( (a3 & 1) != 0 )
    return 0;
  v11 = (unsigned __int16 *)CoTaskMemAlloc(0x208u);
  *a2 = (struct _FILETIME)v11;
  if ( v11 )
    return FtpPidl_GetLastFileDisplayName(this[6], v11, v12);
  else
    return -2147287032;
}

```

## disassembly

```asm
0x180021440  mov     [rsp+arg_0], rbx
0x180021445  mov     [rsp+arg_8], rsi
0x18002144a  push    rdi
0x18002144b  sub     rsp, 20h
0x18002144f  mov     rbx, rdx
0x180021452  mov     esi, r8d
0x180021455  xor     edx, edx; Val
0x180021457  mov     rdi, rcx
0x18002145a  mov     rcx, rbx; void *
0x18002145d  lea     r8d, [rdx+50h]; Size
0x180021461  call    memset_0
0x180021466  mov     dword ptr [rbx+8], 2
0x18002146d  mov     rcx, [rdi+30h]; pidl
0x180021471  call    cs:__imp_ILFindLastID
0x180021477  mov     rcx, rax; struct _ITEMIDLIST *
0x18002147a  call    ?FtpPidl_GetFileTime@@YA?AU_FILETIME@@PEFBU_ITEMIDLIST@@@Z; FtpPidl_GetFileTime(_ITEMIDLIST const *)
0x18002147f  mov     [rbx+18h], rax
0x180021483  mov     rcx, [rdi+30h]; pidl
0x180021487  call    cs:__imp_ILFindLastID
0x18002148d  xor     ecx, ecx
0x18002148f  cmp     word ptr [rax], 27h ; '''
0x180021493  jb      short loc_1800214A2
0x180021495  test    dword ptr [rax+6], 0FFFCFFC2h
0x18002149c  jnz     short loc_1800214A2
0x18002149e  mov     rcx, [rax+0Eh]
0x1800214a2  mov     [rbx+10h], rcx
0x1800214a6  mov     ecx, [rbx+30h]
0x1800214a9  mov     eax, ecx
0x1800214ab  or      eax, 10h
0x1800214ae  mov     [rbx+30h], eax
0x1800214b1  test    dword ptr [rdi+18h], 40000000h
0x1800214b8  jz      short loc_1800214C0
0x1800214ba  or      ecx, 11h
0x1800214bd  mov     [rbx+30h], ecx
0x1800214c0  test    sil, 1
0x1800214c4  jz      short loc_1800214CA
0x1800214c6  xor     eax, eax
0x1800214c8  jmp     short loc_1800214F0
0x1800214ca  mov     ecx, 208h; cb
0x1800214cf  call    cs:__imp_CoTaskMemAlloc
0x1800214d5  mov     [rbx], rax
0x1800214d8  test    rax, rax
0x1800214db  jz      short loc_1800214EB
0x1800214dd  mov     rcx, [rdi+30h]; struct _ITEMIDLIST *
0x1800214e1  mov     rdx, rax; unsigned __int16 *
0x1800214e4  call    ?FtpPidl_GetLastFileDisplayName@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; FtpPidl_GetLastFileDisplayName(_ITEMIDLIST const *,ushort *,ulong)
0x1800214e9  jmp     short loc_1800214F0
0x1800214eb  mov     eax, 80030008h
0x1800214f0  mov     rbx, [rsp+28h+arg_0]
0x1800214f5  mov     rsi, [rsp+28h+arg_8]
0x1800214fa  add     rsp, 20h
0x1800214fe  pop     rdi
0x1800214ff  retn
```
