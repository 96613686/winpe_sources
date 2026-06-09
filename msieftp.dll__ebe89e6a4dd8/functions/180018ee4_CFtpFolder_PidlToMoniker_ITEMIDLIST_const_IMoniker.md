# CFtpFolder::_PidlToMoniker(_ITEMIDLIST const *,IMoniker * *)

- ea: `0x180018ee4`
- end: `0x180018f9c`
- name: `?_PidlToMoniker@CFtpFolder@@QEAAJPEFBU_ITEMIDLIST@@PEAPEAUIMoniker@@@Z`
- size: `184`
- prototype: `__int64 __fastcall(CFtpFolder *__hidden this, const struct _ITEMIDLIST *, struct IMoniker **)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180016030`
- `0x180017b8c`

## callees

- `0x180002240`
- `0x180018244`
- `0x18001876c`
- `0x180018ee4`
- `0x1800271f0`
- `0x180028010`

## import_xrefs

- `urlmon!CreateURLMoniker` at `0x180018f5e`
- `urlmon!CreateURLMoniker` at `0x180018f5e`

## pseudocode

```c
__int64 __fastcall CFtpFolder::_PidlToMoniker(CFtpFolder *this, struct _ITEMIDLIST *a2, struct IMoniker **a3)
{
  int BindCtx; // ebx
  struct IBindCtx *v7; // r8
  struct IBindCtx *v9; // [rsp+30h] [rbp-1088h] BYREF
  WCHAR szURL[2088]; // [rsp+40h] [rbp-1078h] BYREF

  *a3 = 0;
  BindCtx = -2147024809;
  if ( a2 )
  {
    v9 = 0;
    BindCtx = CFtpFolder::_GetBindCtx(this, &v9);
    if ( BindCtx >= 0 )
    {
      BindCtx = CFtpFolder::_GetLegacyURL(this, a2, v7, szURL);
      if ( BindCtx >= 0 )
        BindCtx = CreateURLMoniker(0, szURL, a3);
      ((void (__fastcall *)(struct IBindCtx *))v9->lpVtbl->Release)(v9);
    }
  }
  return (unsigned int)BindCtx;
}

```

## disassembly

```asm
0x180018ee4  mov     [rsp+arg_18], rbx
0x180018ee9  push    rbp
0x180018eea  push    rsi
0x180018eeb  push    rdi
0x180018eec  mov     eax, 10A0h
0x180018ef1  call    _alloca_probe
0x180018ef6  sub     rsp, rax
0x180018ef9  mov     rax, cs:__security_cookie
0x180018f00  xor     rax, rsp
0x180018f03  mov     [rsp+10B8h+var_28], rax
0x180018f0b  mov     qword ptr [r8], 0
0x180018f12  mov     rsi, r8
0x180018f15  mov     rbp, rdx
0x180018f18  mov     rdi, rcx
0x180018f1b  mov     ebx, 80070057h
0x180018f20  test    rdx, rdx
0x180018f23  jz      short loc_180018F77
0x180018f25  lea     rdx, [rsp+10B8h+var_1088]; struct IBindCtx **
0x180018f2a  mov     [rsp+10B8h+var_1088], 0
0x180018f33  call    ?_GetBindCtx@CFtpFolder@@IEAAJPEAPEAUIBindCtx@@@Z; CFtpFolder::_GetBindCtx(IBindCtx * *)
0x180018f38  mov     ebx, eax
0x180018f3a  test    eax, eax
0x180018f3c  js      short loc_180018F77
0x180018f3e  lea     r9, [rsp+10B8h+szURL]; unsigned __int16 *
0x180018f43  mov     rdx, rbp; struct _ITEMIDLIST *
0x180018f46  mov     rcx, rdi; this
0x180018f49  call    ?_GetLegacyURL@CFtpFolder@@IEAAJPEFBU_ITEMIDLIST@@PEAUIBindCtx@@PEAGK@Z; CFtpFolder::_GetLegacyURL(_ITEMIDLIST const *,IBindCtx *,ushort *,ulong)
0x180018f4e  mov     ebx, eax
0x180018f50  test    eax, eax
0x180018f52  js      short loc_180018F66
0x180018f54  mov     r8, rsi; ppmk
0x180018f57  lea     rdx, [rsp+10B8h+szURL]; szURL
0x180018f5c  xor     ecx, ecx; pMkCtx
0x180018f5e  call    cs:__imp_CreateURLMoniker
0x180018f64  mov     ebx, eax
0x180018f66  mov     rcx, [rsp+10B8h+var_1088]
0x180018f6b  mov     rax, [rcx]
0x180018f6e  mov     rax, [rax+10h]
0x180018f72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f77  mov     eax, ebx
0x180018f79  mov     rcx, [rsp+10B8h+var_28]
0x180018f81  xor     rcx, rsp; StackCookie
0x180018f84  call    __security_check_cookie
0x180018f89  mov     rbx, [rsp+10B8h+arg_18]
0x180018f91  add     rsp, 10A0h
0x180018f98  pop     rdi
0x180018f99  pop     rsi
0x180018f9a  pop     rbp
0x180018f9b  retn
```
