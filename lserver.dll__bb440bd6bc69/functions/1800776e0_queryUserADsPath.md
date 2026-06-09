# queryUserADsPath

- ea: `0x1800776e0`
- end: `0x1800778e6`
- name: `queryUserADsPath`
- size: `518`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180057958`

## callees

- `0x18000d060`
- `0x1800772f0`
- `0x1800776e0`
- `0x1800a0fb0`
- `0x1800a5010`

## import_xrefs

- `ACTIVEDS!__imp_ADsOpenObject` at `0x180077798`
- `ACTIVEDS!__imp_ADsOpenObject` at `0x180077848`
- `ACTIVEDS!__imp_ADsOpenObject` at `0x180077798`
- `ACTIVEDS!__imp_ADsOpenObject` at `0x180077848`
- `OLEAUT32!__imp_SysAllocString` at `0x1800777b5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800777b5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800778b1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800778b1`
- `OLEAUT32!__imp_VariantInit` at `0x180077736`
- `OLEAUT32!__imp_VariantInit` at `0x180077736`
- `OLEAUT32!__imp_VariantClear` at `0x180077887`
- `OLEAUT32!__imp_VariantClear` at `0x180077887`

## pseudocode

```c
__int64 __fastcall queryUserADsPath(__int64 a1, __int64 a2, __int64 a3)
{
  OLECHAR *v4; // rsi
  HRESULT UserADsPath; // ebx
  void *v9; // [rsp+30h] [rbp-D0h] BYREF
  void *ppObject; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR v12[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR szPathName[1024]; // [rsp+270h] [rbp+170h] BYREF

  v9 = 0;
  v4 = 0;
  ppObject = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( a2 )
    StringCchPrintfW(szPathName, 0x400u, L"LDAP://%s/rootDSE", a2);
  else
    StringCchPrintfW(szPathName, 0x400u, L"LDAP://rootDSE");
  UserADsPath = ADsOpenObject(szPathName, 0, 0, 0xC5u, &IID_IADs, &ppObject);
  if ( UserADsPath >= 0 )
  {
    v4 = SysAllocString(L"defaultNamingContext");
    UserADsPath = (*(__int64 (__fastcall **)(void *, OLECHAR *, VARIANTARG *))(*(_QWORD *)ppObject + 120LL))(
                    ppObject,
                    v4,
                    &pvarg);
    if ( UserADsPath >= 0 )
    {
      if ( a2 )
        StringCchPrintfW(v12, 0x104u, L"LDAP://%s/%s", a2, pvarg.llVal);
      else
        StringCchPrintfW(v12, 0x104u, L"LDAP://%s", pvarg.llVal);
      UserADsPath = ADsOpenObject(v12, 0, 0, 0xC5u, &IID_IDirectorySearch, &v9);
      if ( UserADsPath >= 0 )
        UserADsPath = FindUserADsPath(v9, a1, a3);
    }
  }
  if ( v9 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
  VariantClear(&pvarg);
  if ( ppObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
  if ( v4 )
    SysFreeString(v4);
  return (unsigned int)UserADsPath;
}

```

## disassembly

```asm
0x1800776e0  mov     [rsp-8+arg_18], rbx
0x1800776e5  push    rbp
0x1800776e6  push    rsi
0x1800776e7  push    rdi
0x1800776e8  push    r14
0x1800776ea  push    r15
0x1800776ec  lea     rbp, [rsp-980h]
0x1800776f4  sub     rsp, 0A80h
0x1800776fb  mov     rax, cs:__security_cookie
0x180077702  xor     rax, rsp
0x180077705  mov     [rbp+9A0h+var_30], rax
0x18007770c  and     [rsp+0AA0h+var_A70], 0
0x180077712  mov     r14, rcx
0x180077715  xorps   xmm0, xmm0
0x180077718  lea     rcx, [rsp+0AA0h+pvarg]; pvarg
0x18007771d  xor     eax, eax
0x18007771f  xor     esi, esi
0x180077721  and     [rsp+0AA0h+var_A68], rsi
0x180077726  mov     r15, r8
0x180077729  movups  xmmword ptr [rsp+0AA0h+pvarg], xmm0
0x18007772e  mov     qword ptr [rsp+0AA0h+pvarg+10h], rax
0x180077733  mov     rdi, rdx
0x180077736  call    cs:__imp_VariantInit
0x18007773d  nop     dword ptr [rax+rax+00h]
0x180077742  lea     rcx, [rbp+9A0h+szPathName]; unsigned __int16 *
0x180077749  mov     edx, 400h; unsigned __int64
0x18007774e  test    rdi, rdi
0x180077751  jnz     short loc_180077761
0x180077753  lea     r8, aLdapRootdse_0; "LDAP://rootDSE"
0x18007775a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007775f  jmp     short loc_180077770
0x180077761  mov     r9, rdi
0x180077764  lea     r8, aLdapSRootdse; "LDAP://%s/rootDSE"
0x18007776b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180077770  lea     rax, [rsp+0AA0h+var_A68]
0x180077775  mov     r9d, 0C5h; dwReserved
0x18007777b  mov     [rsp+0AA0h+ppObject], rax; ppObject
0x180077780  lea     rcx, [rbp+9A0h+szPathName]; lpszPathName
0x180077787  lea     rax, IID_IADs
0x18007778e  xor     r8d, r8d; lpszPassword
0x180077791  xor     edx, edx; lpszUserName
0x180077793  mov     [rsp+0AA0h+riid], rax; riid
0x180077798  call    cs:__imp_ADsOpenObject
0x18007779f  nop     dword ptr [rax+rax+00h]
0x1800777a4  mov     ebx, eax
0x1800777a6  test    eax, eax
0x1800777a8  js      loc_18007786C
0x1800777ae  lea     rcx, aDefaultnamingc; "defaultNamingContext"
0x1800777b5  call    cs:__imp_SysAllocString
0x1800777bc  nop     dword ptr [rax+rax+00h]
0x1800777c1  mov     rcx, [rsp+0AA0h+var_A68]
0x1800777c6  lea     r8, [rsp+0AA0h+pvarg]
0x1800777cb  mov     rsi, rax
0x1800777ce  mov     rdx, [rcx]
0x1800777d1  mov     rax, [rdx+78h]
0x1800777d5  mov     rdx, rsi
0x1800777d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800777dd  mov     ebx, eax
0x1800777df  test    eax, eax
0x1800777e1  js      loc_18007786C
0x1800777e7  lea     rcx, [rsp+0AA0h+var_A40]; unsigned __int16 *
0x1800777ec  mov     edx, 104h; unsigned __int64
0x1800777f1  test    rdi, rdi
0x1800777f4  jnz     short loc_180077809
0x1800777f6  mov     r9, qword ptr [rsp+0AA0h+pvarg+8]
0x1800777fb  lea     r8, aLdapS; "LDAP://%s"
0x180077802  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180077807  jmp     short loc_180077822
0x180077809  mov     rax, qword ptr [rsp+0AA0h+pvarg+8]
0x18007780e  lea     r8, aLdapSS; "LDAP://%s/%s"
0x180077815  mov     r9, rdi
0x180077818  mov     [rsp+0AA0h+riid], rax
0x18007781d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180077822  lea     rax, [rsp+0AA0h+var_A70]
0x180077827  mov     r9d, 0C5h; dwReserved
0x18007782d  mov     [rsp+0AA0h+ppObject], rax; ppObject
0x180077832  lea     rcx, [rsp+0AA0h+var_A40]; lpszPathName
0x180077837  lea     rax, IID_IDirectorySearch
0x18007783e  xor     r8d, r8d; lpszPassword
0x180077841  xor     edx, edx; lpszUserName
0x180077843  mov     [rsp+0AA0h+riid], rax; riid
0x180077848  call    cs:__imp_ADsOpenObject
0x18007784f  nop     dword ptr [rax+rax+00h]
0x180077854  mov     ebx, eax
0x180077856  test    eax, eax
0x180077858  js      short loc_18007786C
0x18007785a  mov     rcx, [rsp+0AA0h+var_A70]
0x18007785f  mov     r8, r15
0x180077862  mov     rdx, r14
0x180077865  call    FindUserADsPath
0x18007786a  mov     ebx, eax
0x18007786c  mov     rcx, [rsp+0AA0h+var_A70]
0x180077871  test    rcx, rcx
0x180077874  jz      short loc_180077882
0x180077876  mov     rax, [rcx]
0x180077879  mov     rax, [rax+10h]
0x18007787d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077882  lea     rcx, [rsp+0AA0h+pvarg]; pvarg
0x180077887  call    cs:__imp_VariantClear
0x18007788e  nop     dword ptr [rax+rax+00h]
0x180077893  mov     rcx, [rsp+0AA0h+var_A68]
0x180077898  test    rcx, rcx
0x18007789b  jz      short loc_1800778A9
0x18007789d  mov     rax, [rcx]
0x1800778a0  mov     rax, [rax+10h]
0x1800778a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800778a9  test    rsi, rsi
0x1800778ac  jz      short loc_1800778BD
0x1800778ae  mov     rcx, rsi; bstrString
0x1800778b1  call    cs:__imp_SysFreeString
0x1800778b8  nop     dword ptr [rax+rax+00h]
0x1800778bd  mov     eax, ebx
0x1800778bf  mov     rcx, [rbp+9A0h+var_30]
0x1800778c6  xor     rcx, rsp; StackCookie
0x1800778c9  call    __security_check_cookie
0x1800778ce  mov     rbx, [rsp+0AA0h+arg_18]
0x1800778d6  add     rsp, 0A80h
0x1800778dd  pop     r15
0x1800778df  pop     r14
0x1800778e1  pop     rdi
0x1800778e2  pop     rsi
0x1800778e3  pop     rbp
0x1800778e4  retn
```
