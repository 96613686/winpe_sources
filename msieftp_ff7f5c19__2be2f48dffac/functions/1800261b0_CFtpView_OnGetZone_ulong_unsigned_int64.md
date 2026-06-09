# CFtpView::_OnGetZone(ulong *,unsigned __int64)

- ea: `0x1800261b0`
- end: `0x1800262b2`
- name: `?_OnGetZone@CFtpView@@MEAAJPEAK_K@Z`
- size: `258`
- prototype: `__int64 __fastcall(CFtpView *__hidden this, unsigned int *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002240`
- `0x18001d6bc`
- `0x1800261b0`
- `0x1800271f0`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026249`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026249`

## pseudocode

```c
__int64 __fastcall CFtpView::_OnGetZone(CFtpView *this, unsigned int *a2)
{
  __int64 v2; // rax
  int v4; // ebx
  const struct _ITEMIDLIST *v5; // rcx
  unsigned int v7; // [rsp+30h] [rbp-1078h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-1070h] BYREF
  unsigned __int16 v9[2088]; // [rsp+40h] [rbp-1068h] BYREF

  v2 = *((_QWORD *)this + 8);
  v7 = 3;
  v4 = -2147024809;
  v5 = (const struct _ITEMIDLIST *)(*(_QWORD *)(v2 + 48) + *(int *)(v2 + 64));
  if ( v5 )
  {
    v4 = UrlCreateFromPidl(v5, 0x8000u, v9, 0x824u, 0xC0000000, 0);
    if ( v4 >= 0 )
    {
      ppv = 0;
      if ( CoCreateInstance(&CLSID_InternetSecurityManager, 0, 1u, &IID_IInternetSecurityManager, &ppv) >= 0 )
      {
        (*(void (__fastcall **)(LPVOID, unsigned __int16 *, unsigned int *, _QWORD))(*(_QWORD *)ppv + 40LL))(
          ppv,
          v9,
          &v7,
          0);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
  }
  if ( a2 )
  {
    v4 = 0;
    *a2 = v7;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800261b0  mov     [rsp+arg_10], rbx
0x1800261b5  push    rdi
0x1800261b6  mov     eax, 10A0h
0x1800261bb  call    _alloca_probe
0x1800261c0  sub     rsp, rax
0x1800261c3  mov     rax, cs:__security_cookie
0x1800261ca  xor     rax, rsp
0x1800261cd  mov     [rsp+10A8h+var_18], rax
0x1800261d5  mov     rax, [rcx+40h]
0x1800261d9  mov     rdi, rdx
0x1800261dc  mov     [rsp+10A8h+var_1078], 3
0x1800261e4  mov     ebx, 80070057h
0x1800261e9  movsxd  rcx, dword ptr [rax+40h]
0x1800261ed  add     rcx, [rax+30h]; struct _ITEMIDLIST *
0x1800261f1  jz      loc_180026282
0x1800261f7  mov     [rsp+10A8h+var_1080], 0; int
0x1800261ff  lea     r8, [rsp+10A8h+var_1068]; unsigned __int16 *
0x180026204  mov     r9d, 824h; unsigned int
0x18002620a  mov     dword ptr [rsp+10A8h+ppv], 0C0000000h; unsigned int
0x180026212  mov     edx, 8000h; unsigned int
0x180026217  call    ?UrlCreateFromPidl@@YAJPEFBU_ITEMIDLIST@@KPEAGKKH@Z; UrlCreateFromPidl(_ITEMIDLIST const *,ulong,ushort *,ulong,ulong,int)
0x18002621c  mov     ebx, eax
0x18002621e  test    eax, eax
0x180026220  js      short loc_180026282
0x180026222  xor     edx, edx; pUnkOuter
0x180026224  mov     [rsp+10A8h+var_1070], 0
0x18002622d  lea     rax, [rsp+10A8h+var_1070]
0x180026232  lea     r9, IID_IInternetSecurityManager; riid
0x180026239  mov     [rsp+10A8h+ppv], rax; ppv
0x18002623e  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x180026245  lea     r8d, [rdx+1]; dwClsContext
0x180026249  call    cs:__imp_CoCreateInstance
0x18002624f  test    eax, eax
0x180026251  js      short loc_180026282
0x180026253  mov     rcx, [rsp+10A8h+var_1070]
0x180026258  lea     r8, [rsp+10A8h+var_1078]
0x18002625d  xor     r9d, r9d
0x180026260  lea     rdx, [rsp+10A8h+var_1068]
0x180026265  mov     rax, [rcx]
0x180026268  mov     rax, [rax+28h]
0x18002626c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026271  mov     rcx, [rsp+10A8h+var_1070]
0x180026276  mov     rax, [rcx]
0x180026279  mov     rax, [rax+10h]
0x18002627d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026282  test    rdi, rdi
0x180026285  jz      short loc_18002628F
0x180026287  mov     eax, [rsp+10A8h+var_1078]
0x18002628b  xor     ebx, ebx
0x18002628d  mov     [rdi], eax
0x18002628f  mov     eax, ebx
0x180026291  mov     rcx, [rsp+10A8h+var_18]
0x180026299  xor     rcx, rsp; StackCookie
0x18002629c  call    __security_check_cookie
0x1800262a1  mov     rbx, [rsp+10A8h+arg_10]
0x1800262a9  add     rsp, 10A0h
0x1800262b0  pop     rdi
0x1800262b1  retn
```
