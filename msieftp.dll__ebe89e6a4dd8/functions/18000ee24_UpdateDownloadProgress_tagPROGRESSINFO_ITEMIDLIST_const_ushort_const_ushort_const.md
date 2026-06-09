# UpdateDownloadProgress(tagPROGRESSINFO *,_ITEMIDLIST const *,ushort const *,ushort const *)

- ea: `0x18000ee24`
- end: `0x18000ef6c`
- name: `?UpdateDownloadProgress@@YAJPEAUtagPROGRESSINFO@@PEFBU_ITEMIDLIST@@PEBG2@Z`
- size: `328`
- prototype: `int(struct tagPROGRESSINFO *, const struct _ITEMIDLIST *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000dc58`

## callees

- `0x180002240`
- `0x1800096c4`
- `0x18000ee24`
- `0x18001c53c`
- `0x180023f04`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILRemoveLastID` at `0x18000ee5f`
- `SHELL32!__imp_ILRemoveLastID` at `0x18000ee5f`
- `SHELL32!__imp_ILClone` at `0x18000ee4e`
- `SHELL32!__imp_ILClone` at `0x18000ee4e`
- `SHELL32!__imp_ILFree` at `0x18000ee7e`
- `SHELL32!__imp_ILFree` at `0x18000ee7e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000eeb2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000eeb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ef48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ef48`

## pseudocode

```c
__int64 __fastcall UpdateDownloadProgress(
        struct tagPROGRESSINFO *a1,
        const struct _ITEMIDLIST *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  ITEMIDLIST *v7; // rax
  ITEMIDLIST *v8; // rbx
  int v9; // ebx
  HLOCAL hMem; // [rsp+30h] [rbp-678h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-668h] BYREF
  unsigned __int16 v13[264]; // [rsp+250h] [rbp-458h] BYREF
  unsigned __int16 v14[264]; // [rsp+460h] [rbp-248h] BYREF

  v7 = ILClone(a2);
  v8 = v7;
  if ( v7 )
  {
    ILRemoveLastID(v7);
    FtpPidl_GetDisplayName(v8, v14, 0x104u);
    ILFree(v8);
  }
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)a1 + 72LL))(
    *(_QWORD *)a1,
    *((_QWORD *)a1 + 1),
    *((_QWORD *)a1 + 2));
  LoadStringW(g_hinst, 0x48u, Buffer, 260);
  StringCchPrintfW(v13, 0x104u, Buffer, a4);
  (*(void (__fastcall **)(_QWORD, __int64, unsigned __int16 *))(**(_QWORD **)a1 + 80LL))(*(_QWORD *)a1, 1, v13);
  hMem = 0;
  v9 = CreateFromToStr((unsigned __int16 **)&hMem, v14, a3);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, HLOCAL))(**(_QWORD **)a1 + 80LL))(*(_QWORD *)a1, 2, hMem);
    LocalFree(hMem);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000ee24  push    rbx
0x18000ee26  push    rbp
0x18000ee27  push    rsi
0x18000ee28  push    rdi
0x18000ee29  sub     rsp, 688h
0x18000ee30  mov     rax, cs:__security_cookie
0x18000ee37  xor     rax, rsp
0x18000ee3a  mov     [rsp+6A8h+var_38], rax
0x18000ee42  mov     rdi, rcx
0x18000ee45  mov     rbp, r9
0x18000ee48  mov     rcx, rdx; pidl
0x18000ee4b  mov     rsi, r8
0x18000ee4e  call    cs:__imp_ILClone
0x18000ee54  mov     rbx, rax
0x18000ee57  test    rax, rax
0x18000ee5a  jz      short loc_18000EE84
0x18000ee5c  mov     rcx, rax; pidl
0x18000ee5f  call    cs:__imp_ILRemoveLastID
0x18000ee65  mov     r8d, 104h; unsigned int
0x18000ee6b  lea     rdx, [rsp+6A8h+var_248]; unsigned __int16 *
0x18000ee73  mov     rcx, rbx; struct _ITEMIDLIST *
0x18000ee76  call    ?FtpPidl_GetDisplayName@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; FtpPidl_GetDisplayName(_ITEMIDLIST const *,ushort *,ulong)
0x18000ee7b  mov     rcx, rbx; pidl
0x18000ee7e  call    cs:__imp_ILFree
0x18000ee84  mov     rcx, [rdi]
0x18000ee87  mov     r8, [rdi+10h]
0x18000ee8b  mov     rdx, [rdi+8]
0x18000ee8f  mov     rax, [rcx]
0x18000ee92  mov     rax, [rax+48h]
0x18000ee96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee9b  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18000eea2  lea     r8, [rsp+6A8h+Buffer]; lpBuffer
0x18000eea7  mov     r9d, 104h; cchBufferMax
0x18000eead  mov     edx, 48h ; 'H'; uID
0x18000eeb2  call    cs:__imp_LoadStringW
0x18000eeb8  mov     r9, rbp
0x18000eebb  lea     r8, [rsp+6A8h+Buffer]; unsigned __int16 *
0x18000eec0  mov     edx, 104h; unsigned __int64
0x18000eec5  lea     rcx, [rsp+6A8h+var_458]; unsigned __int16 *
0x18000eecd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000eed2  mov     rcx, [rdi]
0x18000eed5  lea     r8, [rsp+6A8h+var_458]
0x18000eedd  xor     r9d, r9d
0x18000eee0  mov     [rsp+6A8h+var_688], 0
0x18000eee9  mov     rax, [rcx]
0x18000eeec  lea     edx, [r9+1]
0x18000eef0  mov     rax, [rax+50h]
0x18000eef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eef9  mov     r8, rsi
0x18000eefc  mov     [rsp+6A8h+hMem], 0
0x18000ef05  lea     rdx, [rsp+6A8h+var_248]
0x18000ef0d  lea     rcx, [rsp+6A8h+hMem]; unsigned __int16 **
0x18000ef12  call    ?CreateFromToStr@@YAJPEAPEAGZZ; CreateFromToStr(ushort * *,...)
0x18000ef17  mov     ebx, eax
0x18000ef19  test    eax, eax
0x18000ef1b  js      short loc_18000EF4E
0x18000ef1d  mov     rcx, [rdi]
0x18000ef20  xor     r9d, r9d
0x18000ef23  mov     r8, [rsp+6A8h+hMem]
0x18000ef28  mov     [rsp+6A8h+var_688], 0
0x18000ef31  mov     rax, [rcx]
0x18000ef34  lea     edx, [r9+2]
0x18000ef38  mov     rax, [rax+50h]
0x18000ef3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef41  mov     rcx, [rsp+6A8h+hMem]; hMem
0x18000ef46  mov     ebx, eax
0x18000ef48  call    cs:__imp_LocalFree
0x18000ef4e  mov     eax, ebx
0x18000ef50  mov     rcx, [rsp+6A8h+var_38]
0x18000ef58  xor     rcx, rsp; StackCookie
0x18000ef5b  call    __security_check_cookie
0x18000ef60  add     rsp, 688h
0x18000ef67  pop     rdi
0x18000ef68  pop     rsi
0x18000ef69  pop     rbp
0x18000ef6a  pop     rbx
0x18000ef6b  retn
```
