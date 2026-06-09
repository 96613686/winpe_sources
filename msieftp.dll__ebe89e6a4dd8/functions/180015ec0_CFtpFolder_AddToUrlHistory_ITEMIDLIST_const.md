# CFtpFolder::AddToUrlHistory(_ITEMIDLIST const *)

- ea: `0x180015ec0`
- end: `0x180015f7a`
- name: `?AddToUrlHistory@CFtpFolder@@QEAAJPEFBU_ITEMIDLIST@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(CFtpFolder *__hidden this, const struct _ITEMIDLIST *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800159c4`

## callees

- `0x180002240`
- `0x180015ec0`
- `0x18001d6bc`
- `0x1800271f0`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015f3a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015f3a`

## pseudocode

```c
HRESULT __fastcall CFtpFolder::AddToUrlHistory(CFtpFolder *this, const struct _ITEMIDLIST *a2)
{
  HRESULT result; // eax
  LPVOID *ppv; // rbx
  unsigned __int16 v5[2088]; // [rsp+30h] [rbp-1068h] BYREF

  result = UrlCreateFromPidl(a2, 0x8000u, v5, 0x824u, 0xC0000000, 1);
  if ( result >= 0 )
  {
    ppv = (LPVOID *)((char *)this + 136);
    result = 0;
    if ( !*ppv )
      result = CoCreateInstance(&CLSID_CUrlHistory, 0, 1u, &IID_IUrlHistoryStg, ppv);
    if ( *ppv )
      return (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, unsigned __int16 *, _QWORD))(*(_QWORD *)*ppv + 24LL))(
               *ppv,
               v5,
               v5,
               0);
  }
  return result;
}

```

## disassembly

```asm
0x180015ec0  push    rbx
0x180015ec2  mov     eax, 1090h
0x180015ec7  call    _alloca_probe
0x180015ecc  sub     rsp, rax
0x180015ecf  mov     rax, cs:__security_cookie
0x180015ed6  xor     rax, rsp
0x180015ed9  mov     [rsp+1098h+var_18], rax
0x180015ee1  mov     rax, rdx
0x180015ee4  mov     [rsp+1098h+var_1070], 1; int
0x180015eec  mov     rbx, rcx
0x180015eef  mov     dword ptr [rsp+1098h+ppv], 0C0000000h; unsigned int
0x180015ef7  mov     rcx, rax; struct _ITEMIDLIST *
0x180015efa  lea     r8, [rsp+1098h+var_1068]; unsigned __int16 *
0x180015eff  mov     r9d, 824h; unsigned int
0x180015f05  mov     edx, 8000h; unsigned int
0x180015f0a  call    ?UrlCreateFromPidl@@YAJPEFBU_ITEMIDLIST@@KPEAGKKH@Z; UrlCreateFromPidl(_ITEMIDLIST const *,ulong,ushort *,ulong,ulong,int)
0x180015f0f  test    eax, eax
0x180015f11  js      short loc_180015F61
0x180015f13  add     rbx, 88h
0x180015f1a  xor     eax, eax
0x180015f1c  cmp     [rbx], rax
0x180015f1f  jnz     short loc_180015F40
0x180015f21  lea     r9, IID_IUrlHistoryStg; riid
0x180015f28  mov     [rsp+1098h+ppv], rbx; ppv
0x180015f2d  xor     edx, edx; pUnkOuter
0x180015f2f  lea     r8d, [rax+1]; dwClsContext
0x180015f33  lea     rcx, CLSID_CUrlHistory; rclsid
0x180015f3a  call    cs:__imp_CoCreateInstance
0x180015f40  mov     rcx, [rbx]
0x180015f43  test    rcx, rcx
0x180015f46  jz      short loc_180015F61
0x180015f48  mov     rax, [rcx]
0x180015f4b  lea     r8, [rsp+1098h+var_1068]
0x180015f50  xor     r9d, r9d
0x180015f53  lea     rdx, [rsp+1098h+var_1068]
0x180015f58  mov     rax, [rax+18h]
0x180015f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f61  mov     rcx, [rsp+1098h+var_18]
0x180015f69  xor     rcx, rsp; StackCookie
0x180015f6c  call    __security_check_cookie
0x180015f71  add     rsp, 1090h
0x180015f78  pop     rbx
0x180015f79  retn
```
