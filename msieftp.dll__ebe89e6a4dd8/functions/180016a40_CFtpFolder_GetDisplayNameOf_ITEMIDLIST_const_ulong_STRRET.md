# CFtpFolder::GetDisplayNameOf(_ITEMIDLIST const *,ulong,_STRRET *)

- ea: `0x180016a40`
- end: `0x180016b2a`
- name: `?GetDisplayNameOf@CFtpFolder@@UEAAJPEFBU_ITEMIDLIST@@KPEAU_STRRET@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(CFtpFolder *__hidden this, const struct _ITEMIDLIST *, unsigned int, struct _STRRET *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002240`
- `0x180016a40`
- `0x180018d28`
- `0x18001d6bc`
- `0x1800271f0`

## import_xrefs

- `SHELL32!__imp_ILCombine` at `0x180016a9e`
- `SHELL32!__imp_ILCombine` at `0x180016a9e`
- `SHELL32!__imp_ILFree` at `0x180016af4`
- `SHELL32!__imp_ILFree` at `0x180016af4`
- `SHLWAPI!SHStrDupW` at `0x180016ae9`
- `SHLWAPI!SHStrDupW` at `0x180016ae9`

## pseudocode

```c
__int64 __fastcall CFtpFolder::GetDisplayNameOf(
        CFtpFolder *this,
        const struct _ITEMIDLIST *a2,
        unsigned int a3,
        struct _STRRET *a4)
{
  HRESULT v8; // ebx
  const struct _ITEMIDLIST *v9; // rax
  ITEMIDLIST *v10; // rdi
  WCHAR psz[2088]; // [rsp+30h] [rbp-1088h] BYREF

  if ( !a2 || !a2->mkid.cb || !CFtpFolder::_IsValidPidlParameter(this, a2) )
    return 2147942487LL;
  v8 = -2147467259;
  v9 = ILCombine((LPCITEMIDLIST)(*((_QWORD *)this + 6) + *((int *)this + 16)), a2);
  v10 = (ITEMIDLIST *)v9;
  if ( v9 )
  {
    psz[0] = 0;
    v8 = UrlCreateFromPidl(v9, a3, psz, 0x824u, 0xC0000000, 1);
    if ( v8 >= 0 )
    {
      a4->uType = 0;
      v8 = SHStrDupW(psz, &a4->pOleStr);
    }
    ILFree(v10);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180016a40  mov     [rsp+arg_10], rbx
0x180016a45  push    rbp
0x180016a46  push    rsi
0x180016a47  push    rdi
0x180016a48  push    r14
0x180016a4a  push    r15
0x180016a4c  mov     eax, 1090h
0x180016a51  call    _alloca_probe
0x180016a56  sub     rsp, rax
0x180016a59  mov     rax, cs:__security_cookie
0x180016a60  xor     rax, rsp
0x180016a63  mov     [rsp+10B8h+var_38], rax
0x180016a6b  xor     r15d, r15d
0x180016a6e  mov     r14, r9
0x180016a71  mov     ebp, r8d
0x180016a74  mov     rdi, rdx
0x180016a77  mov     rsi, rcx
0x180016a7a  test    rdx, rdx
0x180016a7d  jz      short loc_180016AFE
0x180016a7f  cmp     [rdx], r15w
0x180016a83  jz      short loc_180016AFE
0x180016a85  call    ?_IsValidPidlParameter@CFtpFolder@@QEAAHPEFBU_ITEMIDLIST@@@Z; CFtpFolder::_IsValidPidlParameter(_ITEMIDLIST const *)
0x180016a8a  test    eax, eax
0x180016a8c  jz      short loc_180016AFE
0x180016a8e  movsxd  rcx, dword ptr [rsi+40h]
0x180016a92  mov     rdx, rdi; pidl2
0x180016a95  add     rcx, [rsi+30h]; pidl1
0x180016a99  mov     ebx, 80004005h
0x180016a9e  call    cs:__imp_ILCombine
0x180016aa4  mov     rdi, rax
0x180016aa7  test    rax, rax
0x180016aaa  jz      short loc_180016AFA
0x180016aac  mov     [rsp+10B8h+var_1090], 1; int
0x180016ab4  lea     r8, [rsp+10B8h+psz]; unsigned __int16 *
0x180016ab9  mov     r9d, 824h; unsigned int
0x180016abf  mov     [rsp+10B8h+var_1098], 0C0000000h; unsigned int
0x180016ac7  mov     edx, ebp; unsigned int
0x180016ac9  mov     [rsp+10B8h+psz], r15w
0x180016acf  mov     rcx, rax; struct _ITEMIDLIST *
0x180016ad2  call    ?UrlCreateFromPidl@@YAJPEFBU_ITEMIDLIST@@KPEAGKKH@Z; UrlCreateFromPidl(_ITEMIDLIST const *,ulong,ushort *,ulong,ulong,int)
0x180016ad7  mov     ebx, eax
0x180016ad9  test    eax, eax
0x180016adb  js      short loc_180016AF1
0x180016add  lea     rdx, [r14+8]; ppwsz
0x180016ae1  mov     [r14], r15d
0x180016ae4  lea     rcx, [rsp+10B8h+psz]; psz
0x180016ae9  call    cs:__imp_SHStrDupW
0x180016aef  mov     ebx, eax
0x180016af1  mov     rcx, rdi; pidl
0x180016af4  call    cs:__imp_ILFree
0x180016afa  mov     eax, ebx
0x180016afc  jmp     short loc_180016B03
0x180016afe  mov     eax, 80070057h
0x180016b03  mov     rcx, [rsp+10B8h+var_38]
0x180016b0b  xor     rcx, rsp; StackCookie
0x180016b0e  call    __security_check_cookie
0x180016b13  mov     rbx, [rsp+10B8h+arg_10]
0x180016b1b  add     rsp, 1090h
0x180016b22  pop     r15
0x180016b24  pop     r14
0x180016b26  pop     rdi
0x180016b27  pop     rsi
0x180016b28  pop     rbp
0x180016b29  retn
```
