# WmiClass::Initialize(ushort const *,ushort const *,ushort const *)

- ea: `0x18000a484`
- end: `0x18000a620`
- name: `?Initialize@WmiClass@@AEAAJPEBG00@Z`
- size: `412`
- prototype: `__int64 __fastcall(WmiClass *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a030`

## callees

- `0x180003a20`
- `0x18000a484`
- `0x18000a800`
- `0x18000b010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000a4c2`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a539`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a4c2`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a539`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a5fb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a5fb`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000a5bf`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000a5bf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a4f8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a4f8`

## string_xrefs

- `0x18000a4b0`: `root\cimv2\security\microsofttpm`

## pseudocode

```c
__int64 __fastcall WmiClass::Initialize(
        WmiClass *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  BSTR v5; // rax
  HRESULT Instance; // ebx
  BSTR v7; // rax
  OLECHAR *v8; // rsi
  IUnknown **v9; // r14
  OLECHAR psz[264]; // [rsp+50h] [rbp-248h] BYREF

  *(_QWORD *)this = L".";
  *((_QWORD *)this + 1) = L"root\\cimv2\\security\\microsofttpm";
  v5 = SysAllocString(L"Win32_Tpm");
  *((_QWORD *)this + 5) = v5;
  if ( !v5 )
    return (unsigned int)-2147024882;
  Instance = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, (LPVOID *)this + 2);
  if ( Instance >= 0 )
  {
    Instance = StringCchPrintfW(psz, 0x105u, L"\\\\%s\\%s", *(_QWORD *)this, *((_QWORD *)this + 1));
    if ( Instance >= 0 )
    {
      v7 = SysAllocString(psz);
      v8 = v7;
      if ( !v7 )
        return (unsigned int)-2147024882;
      v9 = (IUnknown **)((char *)this + 24);
      Instance = (*(__int64 (__fastcall **)(_QWORD, BSTR, _QWORD, _QWORD, _QWORD, int, _QWORD, _QWORD, char *))(**((_QWORD **)this + 2) + 24LL))(
                   *((_QWORD *)this + 2),
                   v7,
                   0,
                   0,
                   0,
                   128,
                   0,
                   0,
                   (char *)this + 24);
      if ( Instance >= 0 )
      {
        Instance = CoSetProxyBlanket(*v9, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 6u, 3u, 0, 0);
        if ( Instance >= 0 )
          Instance = ((__int64 (__fastcall *)(IUnknown *, _QWORD, _QWORD, _QWORD, char *, _QWORD))(*v9)->lpVtbl[2].QueryInterface)(
                       *v9,
                       *((_QWORD *)this + 5),
                       0,
                       0,
                       (char *)this + 32,
                       0);
      }
      SysFreeString(v8);
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000a484  push    rbx
0x18000a486  push    rsi
0x18000a487  push    rdi
0x18000a488  push    r14
0x18000a48a  sub     rsp, 278h
0x18000a491  mov     rax, cs:__security_cookie
0x18000a498  xor     rax, rsp
0x18000a49b  mov     [rsp+298h+var_38], rax
0x18000a4a3  lea     rax, asc_18000F23C; "."
0x18000a4aa  mov     rdi, rcx
0x18000a4ad  mov     [rcx], rax
0x18000a4b0  lea     rax, aRootCimv2Secur; "root\\cimv2\\security\\microsofttpm"
0x18000a4b7  mov     [rcx+8], rax
0x18000a4bb  lea     rcx, aWin32Tpm; "Win32_Tpm"
0x18000a4c2  call    cs:__imp_SysAllocString
0x18000a4c8  mov     [rdi+28h], rax
0x18000a4cc  test    rax, rax
0x18000a4cf  jnz     short loc_18000A4DB
0x18000a4d1  mov     ebx, 8007000Eh
0x18000a4d6  jmp     loc_18000A601
0x18000a4db  xor     edx, edx; pUnkOuter
0x18000a4dd  lea     r14, [rdi+10h]
0x18000a4e1  lea     r9, IID_IWbemLocator; riid
0x18000a4e8  mov     [rsp+298h+ppv], r14; ppv
0x18000a4ed  lea     rcx, CLSID_WbemLocator; rclsid
0x18000a4f4  lea     r8d, [rdx+1]; dwClsContext
0x18000a4f8  call    cs:__imp_CoCreateInstance
0x18000a4fe  mov     ebx, eax
0x18000a500  test    eax, eax
0x18000a502  js      loc_18000A601
0x18000a508  mov     rax, [rdi+8]
0x18000a50c  lea     r8, aSS_0; "\\\\%s\\%s"
0x18000a513  mov     r9, [rdi]
0x18000a516  lea     rcx, [rsp+298h+psz]; unsigned __int16 *
0x18000a51b  mov     edx, 105h; unsigned __int64
0x18000a520  mov     [rsp+298h+ppv], rax
0x18000a525  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a52a  mov     ebx, eax
0x18000a52c  test    eax, eax
0x18000a52e  js      loc_18000A601
0x18000a534  lea     rcx, [rsp+298h+psz]; psz
0x18000a539  call    cs:__imp_SysAllocString
0x18000a53f  mov     rsi, rax
0x18000a542  test    rax, rax
0x18000a545  jz      short loc_18000A4D1
0x18000a547  mov     rcx, [r14]
0x18000a54a  xor     r9d, r9d
0x18000a54d  lea     r14, [rdi+18h]
0x18000a551  xor     r8d, r8d
0x18000a554  mov     [rsp+298h+var_258], r14
0x18000a559  mov     rdx, rsi
0x18000a55c  mov     qword ptr [rsp+298h+dwCapabilities], 0
0x18000a565  mov     rax, [rcx]
0x18000a568  mov     [rsp+298h+pAuthInfo], 0
0x18000a571  mov     [rsp+298h+dwImpLevel], 80h
0x18000a579  mov     [rsp+298h+ppv], 0
0x18000a582  mov     rax, [rax+18h]
0x18000a586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a58b  mov     ebx, eax
0x18000a58d  test    eax, eax
0x18000a58f  js      short loc_18000A5F8
0x18000a591  mov     rcx, [r14]; pProxy
0x18000a594  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18000a598  mov     [rsp+298h+dwCapabilities], 0; dwCapabilities
0x18000a5a0  xor     r8d, r8d; dwAuthzSvc
0x18000a5a3  mov     [rsp+298h+pAuthInfo], 0; pAuthInfo
0x18000a5ac  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18000a5af  mov     [rsp+298h+dwImpLevel], 3; dwImpLevel
0x18000a5b7  mov     dword ptr [rsp+298h+ppv], 6; dwAuthnLevel
0x18000a5bf  call    cs:__imp_CoSetProxyBlanket
0x18000a5c5  mov     ebx, eax
0x18000a5c7  test    eax, eax
0x18000a5c9  js      short loc_18000A5F8
0x18000a5cb  mov     rcx, [r14]
0x18000a5ce  lea     rdx, [rdi+20h]
0x18000a5d2  mov     qword ptr [rsp+298h+dwImpLevel], 0
0x18000a5db  xor     r9d, r9d
0x18000a5de  mov     [rsp+298h+ppv], rdx
0x18000a5e3  xor     r8d, r8d
0x18000a5e6  mov     rdx, [rdi+28h]
0x18000a5ea  mov     rax, [rcx]
0x18000a5ed  mov     rax, [rax+30h]
0x18000a5f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5f6  mov     ebx, eax
0x18000a5f8  mov     rcx, rsi; bstrString
0x18000a5fb  call    cs:__imp_SysFreeString
0x18000a601  mov     eax, ebx
0x18000a603  mov     rcx, [rsp+298h+var_38]
0x18000a60b  xor     rcx, rsp; StackCookie
0x18000a60e  call    __security_check_cookie
0x18000a613  add     rsp, 278h
0x18000a61a  pop     r14
0x18000a61c  pop     rdi
0x18000a61d  pop     rsi
0x18000a61e  pop     rbx
0x18000a61f  retn
```
