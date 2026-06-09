# _SetStatusBarZone(CStatusBar *,CFtpSite *)

- ea: `0x1800258d4`
- end: `0x1800259f2`
- name: `?_SetStatusBarZone@@YAJPEAVCStatusBar@@PEAVCFtpSite@@@Z`
- size: `286`
- prototype: `__int64 __fastcall(struct CStatusBar *, struct CFtpSite *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800159c4`
- `0x180026520`

## callees

- `0x180002240`
- `0x18001d6bc`
- `0x180023710`
- `0x1800239bc`
- `0x1800258d4`
- `0x1800271f0`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILClone` at `0x180025915`
- `SHELL32!__imp_ILClone` at `0x180025915`
- `SHELL32!__imp_ILFree` at `0x1800259c6`
- `SHELL32!__imp_ILFree` at `0x1800259c6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025987`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025987`

## pseudocode

```c
__int64 __fastcall _SetStatusBarZone(LPVOID *a1, LPCITEMIDLIST *a2)
{
  const struct _ITEMIDLIST *v3; // rax
  ITEMIDLIST *v4; // rdi
  _QWORD *v5; // r14
  bool v6; // zf
  _DWORD *v7; // rsi
  unsigned __int16 v9[2088]; // [rsp+30h] [rbp-1078h] BYREF

  if ( a1 )
  {
    if ( a2 )
    {
      v3 = ILClone(a2[9]);
      v4 = (ITEMIDLIST *)v3;
      if ( v3 )
      {
        UrlCreateFromPidl(v3, 0x8000u, v9, 0x824u, 0, 1);
        CStatusBar::_InitStatusBar((CStatusBar *)a1);
        v5 = a1 + 2;
        v6 = a1[2] == 0;
        v7 = a1 + 16;
        *((_DWORD *)a1 + 32) = -1;
        if ( v6 )
          CoCreateInstance(&CLSID_InternetSecurityManager, 0, 1u, &IID_IInternetSecurityManager, a1 + 2);
        if ( *v5 )
        {
          (*(void (__fastcall **)(_QWORD, unsigned __int16 *, char *, _QWORD))(*(_QWORD *)*v5 + 40LL))(
            *v5,
            v9,
            (char *)a1 + 128,
            0);
          *v7 &= ~0x100u;
          if ( *v7 > 0xBu )
            *v7 = -1;
        }
        CStatusBar::_SetZone((CStatusBar *)a1);
        ILFree(v4);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800258d4  mov     [rsp+arg_10], rbx
0x1800258d9  push    rsi
0x1800258da  push    rdi
0x1800258db  push    r14
0x1800258dd  mov     eax, 1090h
0x1800258e2  call    _alloca_probe
0x1800258e7  sub     rsp, rax
0x1800258ea  mov     rax, cs:__security_cookie
0x1800258f1  xor     rax, rsp
0x1800258f4  mov     [rsp+10A8h+var_28], rax
0x1800258fc  mov     rbx, rcx
0x1800258ff  test    rcx, rcx
0x180025902  jz      loc_1800259CC
0x180025908  test    rdx, rdx
0x18002590b  jz      loc_1800259CC
0x180025911  mov     rcx, [rdx+48h]; pidl
0x180025915  call    cs:__imp_ILClone
0x18002591b  mov     rdi, rax
0x18002591e  test    rax, rax
0x180025921  jz      loc_1800259CC
0x180025927  mov     [rsp+10A8h+var_1080], 1; int
0x18002592f  lea     r8, [rsp+10A8h+var_1078]; unsigned __int16 *
0x180025934  mov     r9d, 824h; unsigned int
0x18002593a  mov     dword ptr [rsp+10A8h+ppv], 0; unsigned int
0x180025942  mov     edx, 8000h; unsigned int
0x180025947  mov     rcx, rax; struct _ITEMIDLIST *
0x18002594a  call    ?UrlCreateFromPidl@@YAJPEFBU_ITEMIDLIST@@KPEAGKKH@Z; UrlCreateFromPidl(_ITEMIDLIST const *,ulong,ushort *,ulong,ulong,int)
0x18002594f  mov     rcx, rbx; this
0x180025952  call    ?_InitStatusBar@CStatusBar@@IEAAJXZ; CStatusBar::_InitStatusBar(void)
0x180025957  lea     r14, [rbx+10h]
0x18002595b  cmp     qword ptr [r14], 0
0x18002595f  lea     rsi, [rbx+80h]
0x180025966  mov     dword ptr [rsi], 0FFFFFFFFh
0x18002596c  jnz     short loc_18002598D
0x18002596e  xor     edx, edx; pUnkOuter
0x180025970  mov     [rsp+10A8h+ppv], r14; ppv
0x180025975  lea     r9, IID_IInternetSecurityManager; riid
0x18002597c  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x180025983  lea     r8d, [rdx+1]; dwClsContext
0x180025987  call    cs:__imp_CoCreateInstance
0x18002598d  mov     rcx, [r14]
0x180025990  test    rcx, rcx
0x180025993  jz      short loc_1800259BB
0x180025995  mov     rax, [rcx]
0x180025998  lea     rdx, [rsp+10A8h+var_1078]
0x18002599d  xor     r9d, r9d
0x1800259a0  mov     r8, rsi
0x1800259a3  mov     rax, [rax+28h]
0x1800259a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259ac  btr     dword ptr [rsi], 8
0x1800259b0  cmp     dword ptr [rsi], 0Bh
0x1800259b3  jbe     short loc_1800259BB
0x1800259b5  mov     dword ptr [rsi], 0FFFFFFFFh
0x1800259bb  mov     rcx, rbx; this
0x1800259be  call    ?_SetZone@CStatusBar@@IEAAJXZ; CStatusBar::_SetZone(void)
0x1800259c3  mov     rcx, rdi; pidl
0x1800259c6  call    cs:__imp_ILFree
0x1800259cc  xor     eax, eax
0x1800259ce  mov     rcx, [rsp+10A8h+var_28]
0x1800259d6  xor     rcx, rsp; StackCookie
0x1800259d9  call    __security_check_cookie
0x1800259de  mov     rbx, [rsp+10A8h+arg_10]
0x1800259e6  add     rsp, 1090h
0x1800259ed  pop     r14
0x1800259ef  pop     rdi
0x1800259f0  pop     rsi
0x1800259f1  retn
```
