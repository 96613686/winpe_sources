# WMIConnect

- ea: `0x18003f5e0`
- end: `0x18003f802`
- name: `WMIConnect`
- size: `546`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, int, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009958`

## callees

- `0x180037c8c`
- `0x180037d94`
- `0x18003f5e0`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003f65d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003f65d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003f6a2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003f6a2`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003f79d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003f79d`

## pseudocode

```c
__int64 __fastcall WMIConnect(unsigned __int16 *a1, IUnknown **a2, __int64 a3, __int64 a4, int a5, _QWORD *a6)
{
  unsigned int v8; // eax
  HRESULT v9; // ebx
  int v10; // eax
  __int64 (__fastcall *v11)(LPVOID, __int64, __int64, __int64, _QWORD, int, _QWORD, _QWORD, IUnknown **); // r15
  _bstr_t *v12; // rax
  __int64 v13; // rsi
  _bstr_t *v14; // rax
  __int64 v15; // rbx
  _bstr_t *v16; // rax
  __int64 v17; // rdx
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v20[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v21[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v22[8]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v23[1040]; // [rsp+70h] [rbp-90h] BYREF

  ppv = 0;
  memset_0(v23, 0, 0x404u);
  if ( !a1 || !a2 || !a6 )
    return 2147749889LL;
  *a6 = 0;
  v8 = CoInitializeEx(0, 2u);
  v9 = v8;
  if ( v8 <= 1 )
  {
    v10 = 1;
    goto LABEL_8;
  }
  if ( v8 == -2147417850 )
  {
    v10 = 0;
LABEL_8:
    dwDoUninitialize = v10;
    v9 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, &ppv);
    if ( v9 >= 0 )
    {
      v11 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64, __int64, _QWORD, int, _QWORD, _QWORD, IUnknown **))(*(_QWORD *)ppv + 24LL);
      v12 = _bstr_t::_bstr_t((_bstr_t *)v22, 0);
      v13 = *(_QWORD *)v12 ? **(_QWORD **)v12 : 0LL;
      v14 = _bstr_t::_bstr_t((_bstr_t *)v21, 0);
      v15 = *(_QWORD *)v14 ? **(_QWORD **)v14 : 0LL;
      v16 = _bstr_t::_bstr_t((_bstr_t *)v20, a1);
      v17 = *(_QWORD *)v16 ? **(_QWORD **)v16 : 0LL;
      v9 = v11(ppv, v17, v15, v13, 0, 128, 0, 0, a2);
      _bstr_t::~_bstr_t((_bstr_t *)v20);
      _bstr_t::~_bstr_t((_bstr_t *)v21);
      _bstr_t::~_bstr_t((_bstr_t *)v22);
      if ( v9 >= 0 )
        v9 = CoSetProxyBlanket(*a2, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 6u, 3u, 0, 0);
    }
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v9 < 0 )
  {
    if ( *a2 )
      ((void (__fastcall *)(IUnknown *))(*a2)->lpVtbl->Release)(*a2);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003f5e0  mov     [rsp-8+arg_10], rbx
0x18003f5e5  push    rbp
0x18003f5e6  push    rsi
0x18003f5e7  push    rdi
0x18003f5e8  push    r14
0x18003f5ea  push    r15
0x18003f5ec  lea     rbp, [rsp-390h]
0x18003f5f4  sub     rsp, 490h
0x18003f5fb  mov     rax, cs:__security_cookie
0x18003f602  xor     rax, rsp
0x18003f605  mov     [rbp+3B0h+var_30], rax
0x18003f60c  mov     rbx, [rbp+3B0h+arg_28]
0x18003f613  mov     rdi, rdx
0x18003f616  mov     r14, rcx
0x18003f619  mov     [rsp+4B0h+var_460], 0
0x18003f622  xor     edx, edx; Val
0x18003f624  lea     rcx, [rsp+4B0h+var_440]; void *
0x18003f629  mov     r8d, 404h; Size
0x18003f62f  call    memset_0
0x18003f634  test    r14, r14
0x18003f637  jz      loc_18003F7D7
0x18003f63d  test    rdi, rdi
0x18003f640  jz      loc_18003F7D7
0x18003f646  test    rbx, rbx
0x18003f649  jz      loc_18003F7D7
0x18003f64f  mov     edx, 2; dwCoInit
0x18003f654  mov     qword ptr [rbx], 0
0x18003f65b  xor     ecx, ecx; pvReserved
0x18003f65d  call    cs:__imp_CoInitializeEx
0x18003f663  mov     r8d, 1; dwClsContext
0x18003f669  mov     ebx, eax
0x18003f66b  cmp     eax, r8d
0x18003f66e  jbe     short loc_18003F67F
0x18003f670  cmp     eax, 80010106h
0x18003f675  jnz     loc_18003F7A5
0x18003f67b  xor     eax, eax
0x18003f67d  jmp     short loc_18003F682
0x18003f67f  mov     eax, r8d
0x18003f682  mov     cs:?dwDoUninitialize@@3HA, eax; int dwDoUninitialize
0x18003f688  lea     r9, IID_IWbemLocator; riid
0x18003f68f  lea     rax, [rsp+4B0h+var_460]
0x18003f694  xor     edx, edx; pUnkOuter
0x18003f696  lea     rcx, CLSID_WbemLocator; rclsid
0x18003f69d  mov     [rsp+4B0h+ppv], rax; ppv
0x18003f6a2  call    cs:__imp_CoCreateInstance
0x18003f6a8  mov     ebx, eax
0x18003f6aa  test    eax, eax
0x18003f6ac  js      loc_18003F7A5
0x18003f6b2  mov     rax, [rsp+4B0h+var_460]
0x18003f6b7  xor     edx, edx; unsigned __int16 *
0x18003f6b9  mov     rcx, [rax]
0x18003f6bc  mov     r15, [rcx+18h]
0x18003f6c0  lea     rcx, [rsp+4B0h+var_448]; this
0x18003f6c5  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003f6ca  mov     rcx, [rax]
0x18003f6cd  test    rcx, rcx
0x18003f6d0  jz      short loc_18003F6D7
0x18003f6d2  mov     rsi, [rcx]
0x18003f6d5  jmp     short loc_18003F6D9
0x18003f6d7  xor     esi, esi
0x18003f6d9  xor     edx, edx; unsigned __int16 *
0x18003f6db  lea     rcx, [rsp+4B0h+var_450]; this
0x18003f6e0  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003f6e5  mov     rcx, [rax]
0x18003f6e8  test    rcx, rcx
0x18003f6eb  jz      short loc_18003F6F2
0x18003f6ed  mov     rbx, [rcx]
0x18003f6f0  jmp     short loc_18003F6F4
0x18003f6f2  xor     ebx, ebx
0x18003f6f4  mov     rdx, r14; unsigned __int16 *
0x18003f6f7  lea     rcx, [rsp+4B0h+var_458]; this
0x18003f6fc  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003f701  mov     rcx, [rax]
0x18003f704  test    rcx, rcx
0x18003f707  jz      short loc_18003F70E
0x18003f709  mov     rdx, [rcx]
0x18003f70c  jmp     short loc_18003F710
0x18003f70e  xor     edx, edx
0x18003f710  mov     rcx, [rsp+4B0h+var_460]
0x18003f715  mov     r9, rsi
0x18003f718  mov     [rsp+4B0h+var_470], rdi
0x18003f71d  mov     r8, rbx
0x18003f720  mov     qword ptr [rsp+4B0h+dwCapabilities], 0
0x18003f729  mov     rax, r15
0x18003f72c  mov     [rsp+4B0h+pAuthInfo], 0
0x18003f735  mov     [rsp+4B0h+dwImpLevel], 80h
0x18003f73d  mov     [rsp+4B0h+ppv], 0
0x18003f746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f74b  lea     rcx, [rsp+4B0h+var_458]; this
0x18003f750  mov     ebx, eax
0x18003f752  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18003f757  lea     rcx, [rsp+4B0h+var_450]; this
0x18003f75c  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18003f761  lea     rcx, [rsp+4B0h+var_448]; this
0x18003f766  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18003f76b  test    ebx, ebx
0x18003f76d  js      short loc_18003F7A5
0x18003f76f  mov     rcx, [rdi]; pProxy
0x18003f772  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18003f775  mov     [rsp+4B0h+dwCapabilities], 0; dwCapabilities
0x18003f77d  mov     r8d, edx; dwAuthzSvc
0x18003f780  mov     [rsp+4B0h+pAuthInfo], 0; pAuthInfo
0x18003f789  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18003f78d  mov     [rsp+4B0h+dwImpLevel], 3; dwImpLevel
0x18003f795  mov     dword ptr [rsp+4B0h+ppv], 6; dwAuthnLevel
0x18003f79d  call    cs:__imp_CoSetProxyBlanket
0x18003f7a3  mov     ebx, eax
0x18003f7a5  mov     rcx, [rsp+4B0h+var_460]
0x18003f7aa  test    rcx, rcx
0x18003f7ad  jz      short loc_18003F7BB
0x18003f7af  mov     rax, [rcx]
0x18003f7b2  mov     rax, [rax+10h]
0x18003f7b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7bb  test    ebx, ebx
0x18003f7bd  jns     short loc_18003F7D3
0x18003f7bf  mov     rcx, [rdi]
0x18003f7c2  test    rcx, rcx
0x18003f7c5  jz      short loc_18003F7D3
0x18003f7c7  mov     rax, [rcx]
0x18003f7ca  mov     rax, [rax+10h]
0x18003f7ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7d3  mov     eax, ebx
0x18003f7d5  jmp     short loc_18003F7DC
0x18003f7d7  mov     eax, 80041001h
0x18003f7dc  mov     rcx, [rbp+3B0h+var_30]
0x18003f7e3  xor     rcx, rsp; StackCookie
0x18003f7e6  call    __security_check_cookie
0x18003f7eb  mov     rbx, [rsp+4B0h+arg_10]
0x18003f7f3  add     rsp, 490h
0x18003f7fa  pop     r15
0x18003f7fc  pop     r14
0x18003f7fe  pop     rdi
0x18003f7ff  pop     rsi
0x18003f800  pop     rbp
0x18003f801  retn
```
