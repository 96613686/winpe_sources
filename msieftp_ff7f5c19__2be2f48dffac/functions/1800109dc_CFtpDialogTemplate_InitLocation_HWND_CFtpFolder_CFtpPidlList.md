# CFtpDialogTemplate::_InitLocation(HWND__ *,CFtpFolder *,CFtpPidlList *)

- ea: `0x1800109dc`
- end: `0x180010ace`
- name: `?_InitLocation@CFtpDialogTemplate@@AEAAJPEAUHWND__@@PEAVCFtpFolder@@PEAVCFtpPidlList@@@Z`
- size: `242`
- prototype: `int(CFtpDialogTemplate *__hidden this, HWND, struct CFtpFolder *, struct CFtpPidlList *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010390`

## callees

- `0x180002240`
- `0x1800109dc`
- `0x180010f08`
- `0x18001d6bc`
- `0x1800269f4`

## import_xrefs

- `SHELL32!__imp_ILRemoveLastID` at `0x180010a56`
- `SHELL32!__imp_ILRemoveLastID` at `0x180010a56`
- `SHELL32!__imp_ILCombine` at `0x180010a38`
- `SHELL32!__imp_ILCombine` at `0x180010a38`
- `SHELL32!__imp_ILFree` at `0x180010aa3`
- `SHELL32!__imp_ILFree` at `0x180010aa3`

## pseudocode

```c
__int64 __fastcall CFtpDialogTemplate::_InitLocation(
        CFtpDialogTemplate *this,
        HWND a2,
        struct CFtpFolder *a3,
        struct CFtpPidlList *a4)
{
  const ITEMIDLIST *Ptr; // rax
  const ITEMIDLIST *v7; // rbx
  int v8; // edi
  struct _DPA *v9; // rcx
  LPITEMIDLIST v10; // rbx
  CFtpDialogTemplate *v11; // rcx
  unsigned __int16 v13[264]; // [rsp+30h] [rbp-238h] BYREF

  Ptr = (const ITEMIDLIST *)*((_QWORD *)a4 + 2);
  v7 = (const ITEMIDLIST *)(*((_QWORD *)a3 + 6) + *((int *)a3 + 16));
  v8 = -2147467259;
  v9 = *(struct _DPA **)((char *)&Ptr[5].mkid.cb + 1);
  if ( *(_DWORD *)v9 )
  {
    if ( Ptr )
      Ptr = (const ITEMIDLIST *)DPA_GetPtr(v9, 0);
  }
  else
  {
    Ptr = &c_idlNil;
  }
  v10 = ILCombine(v7, Ptr);
  if ( v10 )
  {
    if ( **(int **)(*((_QWORD *)a4 + 2) + 16LL) > 1 )
      ILRemoveLastID(v10);
    v8 = UrlCreateFromPidl(v10, 0x4000u, v13, 0x104u, 0, 1);
    if ( v8 >= 0 )
      v8 = CFtpDialogTemplate::_ReinsertDlgText(v11, a2, v13, L"%s");
    ILFree(v10);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800109dc  mov     [rsp+arg_0], rbx
0x1800109e1  push    rbp
0x1800109e2  push    rsi
0x1800109e3  push    rdi
0x1800109e4  sub     rsp, 250h
0x1800109eb  mov     rax, cs:__security_cookie
0x1800109f2  xor     rax, rsp
0x1800109f5  mov     [rsp+268h+var_28], rax
0x1800109fd  mov     rax, [r9+10h]
0x180010a01  mov     rsi, r9
0x180010a04  movsxd  rbx, dword ptr [r8+40h]
0x180010a08  mov     rbp, rdx
0x180010a0b  add     rbx, [r8+30h]
0x180010a0f  mov     edi, 80004005h
0x180010a14  mov     rcx, [rax+10h]; hdpa
0x180010a18  cmp     dword ptr [rcx], 0
0x180010a1b  jnz     short loc_180010A26
0x180010a1d  lea     rax, ?c_idlNil@@3U_ITEMIDLIST@@B; _ITEMIDLIST const c_idlNil
0x180010a24  jmp     short loc_180010A32
0x180010a26  test    rax, rax
0x180010a29  jz      short loc_180010A32
0x180010a2b  xor     edx, edx; i
0x180010a2d  call    DPA_GetPtr
0x180010a32  mov     rdx, rax; pidl2
0x180010a35  mov     rcx, rbx; pidl1
0x180010a38  call    cs:__imp_ILCombine
0x180010a3e  mov     rbx, rax
0x180010a41  test    rax, rax
0x180010a44  jz      short loc_180010AA9
0x180010a46  mov     rax, [rsi+10h]
0x180010a4a  mov     rcx, [rax+10h]
0x180010a4e  cmp     dword ptr [rcx], 1
0x180010a51  jle     short loc_180010A5C
0x180010a53  mov     rcx, rbx; pidl
0x180010a56  call    cs:__imp_ILRemoveLastID
0x180010a5c  mov     [rsp+268h+var_240], 1; int
0x180010a64  lea     r8, [rsp+268h+var_238]; unsigned __int16 *
0x180010a69  mov     r9d, 104h; unsigned int
0x180010a6f  mov     [rsp+268h+var_248], 0; unsigned int
0x180010a77  mov     edx, 4000h; unsigned int
0x180010a7c  mov     rcx, rbx; struct _ITEMIDLIST *
0x180010a7f  call    ?UrlCreateFromPidl@@YAJPEFBU_ITEMIDLIST@@KPEAGKKH@Z; UrlCreateFromPidl(_ITEMIDLIST const *,ulong,ushort *,ulong,ulong,int)
0x180010a84  mov     edi, eax
0x180010a86  test    eax, eax
0x180010a88  js      short loc_180010AA0
0x180010a8a  lea     r9, aS; "%s"
0x180010a91  mov     rdx, rbp; HWND
0x180010a94  lea     r8, [rsp+268h+var_238]; void *
0x180010a99  call    ?_ReinsertDlgText@CFtpDialogTemplate@@AEAAJPEAUHWND__@@PEBXPEBG@Z; CFtpDialogTemplate::_ReinsertDlgText(HWND__ *,void const *,ushort const *)
0x180010a9e  mov     edi, eax
0x180010aa0  mov     rcx, rbx; pidl
0x180010aa3  call    cs:__imp_ILFree
0x180010aa9  mov     eax, edi
0x180010aab  mov     rcx, [rsp+268h+var_28]
0x180010ab3  xor     rcx, rsp; StackCookie
0x180010ab6  call    __security_check_cookie
0x180010abb  mov     rbx, [rsp+268h+arg_0]
0x180010ac3  add     rsp, 250h
0x180010aca  pop     rdi
0x180010acb  pop     rsi
0x180010acc  pop     rbp
0x180010acd  retn
```
