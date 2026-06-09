# GetDnForDomain(ushort const *,ushort *,ulong)

- ea: `0x1800764b0`
- end: `0x1800766bf`
- name: `?GetDnForDomain@@YAJPEBGPEAGK@Z`
- size: `527`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800766c8`
- `0x180077514`

## callees

- `0x18000cf54`
- `0x18000cff0`
- `0x18000d060`
- `0x1800764b0`
- `0x1800778ec`
- `0x1800a0fb0`
- `0x1800a5010`

## import_xrefs

- `ACTIVEDS!__imp_ADsOpenObject` at `0x18007655c`
- `ACTIVEDS!__imp_ADsOpenObject` at `0x18007655c`
- `OLEAUT32!__imp_SysAllocString` at `0x180076575`
- `OLEAUT32!__imp_SysAllocString` at `0x180076575`
- `OLEAUT32!__imp_SysFreeString` at `0x1800765a7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800765a7`
- `OLEAUT32!__imp_VariantInit` at `0x180076502`
- `OLEAUT32!__imp_VariantInit` at `0x180076502`
- `OLEAUT32!__imp_VariantClear` at `0x180076593`
- `OLEAUT32!__imp_VariantClear` at `0x180076593`

## pseudocode

```c
__int64 __fastcall GetDnForDomain(const unsigned __int16 *a1, unsigned __int16 *a2, unsigned int a3)
{
  unsigned __int64 v4; // r14
  OLECHAR *v5; // rbx
  HRESULT v7; // edi
  BSTR v8; // rax
  unsigned __int64 v10; // r14
  const wchar_t *v11; // rdx
  wchar_t **v12; // r8
  wchar_t *v13; // r15
  const wchar_t *v14; // rdx
  wchar_t **v15; // r8
  void *ppObject; // [rsp+30h] [rbp-D0h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR szPathName[264]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t String[264]; // [rsp+260h] [rbp+160h] BYREF

  v4 = a3;
  v5 = 0;
  ppObject = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v7 = 0;
  VariantInit(&pvarg);
  if ( !a2 )
    return 87;
  if ( a1 )
  {
    v10 = v4 >> 1;
    StringCchPrintfW(a2, v10, &pszSrc);
    StringCchCopyW(String, 0x104u, a1);
    v13 = wcstok_0(String, v11, v12);
    if ( v13 )
    {
      while ( 1 )
      {
        StringCchCatW(a2, v10, L"DC=");
        StringCchCatW(a2, v10, v13);
        v13 = wcstok_0(0, v14, v15);
        if ( !v13 )
          break;
        StringCchCatW(a2, v10, L",");
      }
    }
  }
  else
  {
    StringCchCopyW(szPathName, 0x104u, L"LDAP://rootDSE");
    v7 = ADsOpenObject(szPathName, 0, 0, 0xC1u, &IID_IADs, &ppObject);
    if ( v7 >= 0 )
    {
      v8 = SysAllocString(L"defaultNamingContext");
      v5 = v8;
      if ( v8 )
      {
        v7 = (*(__int64 (__fastcall **)(void *, BSTR, VARIANTARG *))(*(_QWORD *)ppObject + 120LL))(ppObject, v8, &pvarg);
        if ( v7 >= 0 )
          StringCchPrintfW(a2, v4 >> 1, L"%s", pvarg.llVal);
      }
      else
      {
        v7 = -2147024882;
      }
    }
  }
  VariantClear(&pvarg);
  if ( v5 )
    SysFreeString(v5);
  if ( ppObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800764b0  mov     [rsp-8+arg_0], rbx
0x1800764b5  push    rbp
0x1800764b6  push    rsi
0x1800764b7  push    rdi
0x1800764b8  push    r14
0x1800764ba  push    r15
0x1800764bc  lea     rbp, [rsp-380h]
0x1800764c4  sub     rsp, 480h
0x1800764cb  mov     rax, cs:__security_cookie
0x1800764d2  xor     rax, rsp
0x1800764d5  mov     [rbp+3A0h+var_30], rax
0x1800764dc  mov     r15, rcx
0x1800764df  mov     r14d, r8d
0x1800764e2  xorps   xmm0, xmm0
0x1800764e5  lea     rcx, [rsp+4A0h+pvarg]; pvarg
0x1800764ea  xor     eax, eax
0x1800764ec  xor     ebx, ebx
0x1800764ee  and     [rsp+4A0h+var_470], rbx
0x1800764f3  mov     rsi, rdx
0x1800764f6  movups  xmmword ptr [rsp+4A0h+pvarg], xmm0
0x1800764fb  mov     qword ptr [rsp+4A0h+pvarg+10h], rax
0x180076500  xor     edi, edi
0x180076502  call    cs:__imp_VariantInit
0x180076509  nop     dword ptr [rax+rax+00h]
0x18007650e  test    rsi, rsi
0x180076511  jz      loc_180076693
0x180076517  test    r15, r15
0x18007651a  jnz     loc_18007660B
0x180076520  lea     r8, aLdapRootdse_0; "LDAP://rootDSE"
0x180076527  mov     edx, 104h; unsigned __int64
0x18007652c  lea     rcx, [rsp+4A0h+szPathName]; unsigned __int16 *
0x180076531  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180076536  lea     r11, [rsp+4A0h+var_470]
0x18007653b  mov     r9d, 0C1h; dwReserved
0x180076541  lea     rax, IID_IADs
0x180076548  mov     [rsp+4A0h+ppObject], r11; ppObject
0x18007654d  xor     r8d, r8d; lpszPassword
0x180076550  mov     [rsp+4A0h+riid], rax; riid
0x180076555  xor     edx, edx; lpszUserName
0x180076557  lea     rcx, [rsp+4A0h+szPathName]; lpszPathName
0x18007655c  call    cs:__imp_ADsOpenObject
0x180076563  nop     dword ptr [rax+rax+00h]
0x180076568  mov     edi, eax
0x18007656a  test    eax, eax
0x18007656c  js      short loc_18007658E
0x18007656e  lea     rcx, aDefaultnamingc; "defaultNamingContext"
0x180076575  call    cs:__imp_SysAllocString
0x18007657c  nop     dword ptr [rax+rax+00h]
0x180076581  mov     rbx, rax
0x180076584  test    rax, rax
0x180076587  jnz     short loc_1800765D0
0x180076589  mov     edi, 8007000Eh
0x18007658e  lea     rcx, [rsp+4A0h+pvarg]; pvarg
0x180076593  call    cs:__imp_VariantClear
0x18007659a  nop     dword ptr [rax+rax+00h]
0x18007659f  test    rbx, rbx
0x1800765a2  jz      short loc_1800765B3
0x1800765a4  mov     rcx, rbx; bstrString
0x1800765a7  call    cs:__imp_SysFreeString
0x1800765ae  nop     dword ptr [rax+rax+00h]
0x1800765b3  mov     rcx, [rsp+4A0h+var_470]
0x1800765b8  test    rcx, rcx
0x1800765bb  jz      short loc_1800765C9
0x1800765bd  mov     rax, [rcx]
0x1800765c0  mov     rax, [rax+10h]
0x1800765c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800765c9  mov     eax, edi
0x1800765cb  jmp     loc_180076698
0x1800765d0  mov     rcx, [rsp+4A0h+var_470]
0x1800765d5  lea     r8, [rsp+4A0h+pvarg]
0x1800765da  mov     rdx, rbx
0x1800765dd  mov     rax, [rcx]
0x1800765e0  mov     rax, [rax+78h]
0x1800765e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800765e9  mov     edi, eax
0x1800765eb  test    eax, eax
0x1800765ed  js      short loc_18007658E
0x1800765ef  mov     r9, qword ptr [rsp+4A0h+pvarg+8]
0x1800765f4  lea     r8, aS_1; "%s"
0x1800765fb  mov     rdx, r14
0x1800765fe  mov     rcx, rsi; unsigned __int16 *
0x180076601  shr     rdx, 1; unsigned __int64
0x180076604  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180076609  jmp     short loc_18007658E
0x18007660b  shr     r14, 1
0x18007660e  lea     r8, pszSrc; unsigned __int16 *
0x180076615  mov     rdx, r14; unsigned __int64
0x180076618  mov     rcx, rsi; unsigned __int16 *
0x18007661b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180076620  mov     r8, r15; unsigned __int16 *
0x180076623  lea     rcx, [rbp+3A0h+String]; unsigned __int16 *
0x18007662a  mov     edx, 104h; unsigned __int64
0x18007662f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180076634  lea     rcx, [rbp+3A0h+String]; String
0x18007663b  call    wcstok_0
0x180076640  mov     r15, rax
0x180076643  test    rax, rax
0x180076646  jz      loc_18007658E
0x18007664c  lea     r8, aDc; "DC="
0x180076653  mov     rdx, r14; unsigned __int64
0x180076656  mov     rcx, rsi; unsigned __int16 *
0x180076659  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18007665e  mov     r8, r15; unsigned __int16 *
0x180076661  mov     rdx, r14; unsigned __int64
0x180076664  mov     rcx, rsi; unsigned __int16 *
0x180076667  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18007666c  xor     ecx, ecx; String
0x18007666e  call    wcstok_0
0x180076673  mov     r15, rax
0x180076676  test    rax, rax
0x180076679  jz      loc_18007658E
0x18007667f  lea     r8, asc_1800BA394; ","
0x180076686  mov     rdx, r14; unsigned __int64
0x180076689  mov     rcx, rsi; unsigned __int16 *
0x18007668c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180076691  jmp     short loc_18007664C
0x180076693  mov     eax, 57h ; 'W'
0x180076698  mov     rcx, [rbp+3A0h+var_30]
0x18007669f  xor     rcx, rsp; StackCookie
0x1800766a2  call    __security_check_cookie
0x1800766a7  mov     rbx, [rsp+4A0h+arg_0]
0x1800766af  add     rsp, 480h
0x1800766b6  pop     r15
0x1800766b8  pop     r14
0x1800766ba  pop     rdi
0x1800766bb  pop     rsi
0x1800766bc  pop     rbp
0x1800766bd  retn
```
