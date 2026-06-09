# _xCoInternetParseUrl(ushort const *,_tagPARSEACTION,ulong,ushort * *,ulong)

- ea: `0x18000bf40`
- end: `0x18000c046`
- name: `?_xCoInternetParseUrl@@YAJPEBGW4_tagPARSEACTION@@KPEAPEAGK@Z`
- size: `262`
- prototype: `__int64 __fastcall(LPCWSTR pwzUrl, PARSEACTION ParseAction, __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000be28`

## callees

- `0x18000bf40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c01e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c01e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bfb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bfb5`
- `urlmon!CoInternetParseUrl` at `0x18000bf91`
- `urlmon!CoInternetParseUrl` at `0x18000c000`
- `urlmon!CoInternetParseUrl` at `0x18000bf91`
- `urlmon!CoInternetParseUrl` at `0x18000c000`

## pseudocode

```c
__int64 __fastcall _xCoInternetParseUrl(LPCWSTR pwzUrl, PARSEACTION ParseAction, __int64 a3, unsigned __int16 **a4)
{
  WCHAR *v4; // rbx
  HRESULT v8; // eax
  HRESULT v9; // edi
  DWORD cchResult; // eax
  unsigned __int16 *v11; // rax
  WCHAR pszResult[20]; // [rsp+40h] [rbp-28h] BYREF
  DWORD pcchResult; // [rsp+80h] [rbp+18h] BYREF

  v4 = pszResult;
  wcscpy(pszResult, L"x");
  pcchResult = 0;
  v8 = CoInternetParseUrl(pwzUrl, ParseAction, 0, pszResult, 1u, &pcchResult, 0);
  v9 = v8;
  if ( (v8 == 1 || v8 == -2147467261) && pcchResult )
  {
    v4 = (WCHAR *)CoTaskMemAlloc(2LL * pcchResult);
    if ( !v4 )
    {
      v9 = -2147024882;
      goto LABEL_11;
    }
    cchResult = pcchResult;
    pcchResult = 0;
    v9 = CoInternetParseUrl(pwzUrl, ParseAction, 0, v4, cchResult, &pcchResult, 0);
  }
  if ( v9 < 0 && v4 && v4 != pszResult )
  {
    CoTaskMemFree(v4);
    v4 = 0;
  }
LABEL_11:
  v11 = 0;
  if ( v9 >= 0 )
    v11 = v4;
  *a4 = v11;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000bf40  mov     rax, rsp
0x18000bf43  mov     [rax+8], rbx
0x18000bf47  mov     [rax+10h], rbp
0x18000bf4b  mov     [rax+18h], r8d
0x18000bf4f  push    rsi
0x18000bf50  push    rdi
0x18000bf51  push    r14
0x18000bf53  sub     rsp, 50h
0x18000bf57  mov     dword ptr [rax-38h], 0
0x18000bf5e  lea     rbx, [rax-28h]
0x18000bf62  mov     dword ptr [rax-28h], 78h ; 'x'
0x18000bf69  mov     r14, r9
0x18000bf6c  mov     dword ptr [rax+18h], 0
0x18000bf73  lea     rax, [rax+18h]
0x18000bf77  mov     [rsp+68h+pcchResult], rax; pcchResult
0x18000bf7c  lea     r9, [rsp+68h+pszResult]; pszResult
0x18000bf81  xor     r8d, r8d; dwFlags
0x18000bf84  mov     [rsp+68h+cchResult], 1; cchResult
0x18000bf8c  mov     esi, edx
0x18000bf8e  mov     rbp, rcx
0x18000bf91  call    cs:__imp_CoInternetParseUrl
0x18000bf97  mov     edi, eax
0x18000bf99  cmp     eax, 1
0x18000bf9c  jz      short loc_18000BFA5
0x18000bf9e  cmp     eax, 80004003h
0x18000bfa3  jnz     short loc_18000C008
0x18000bfa5  mov     eax, [rsp+68h+arg_10]
0x18000bfac  test    eax, eax
0x18000bfae  jz      short loc_18000C008
0x18000bfb0  mov     ecx, eax
0x18000bfb2  add     rcx, rcx; cb
0x18000bfb5  call    cs:__imp_CoTaskMemAlloc
0x18000bfbb  mov     rbx, rax
0x18000bfbe  test    rax, rax
0x18000bfc1  jnz     short loc_18000BFCA
0x18000bfc3  mov     edi, 8007000Eh
0x18000bfc8  jmp     short loc_18000C026
0x18000bfca  mov     eax, [rsp+68h+arg_10]
0x18000bfd1  lea     rcx, [rsp+68h+arg_10]
0x18000bfd9  mov     [rsp+68h+dwReserved], 0; dwReserved
0x18000bfe1  mov     r9, rbx; pszResult
0x18000bfe4  mov     [rsp+68h+pcchResult], rcx; pcchResult
0x18000bfe9  xor     r8d, r8d; dwFlags
0x18000bfec  mov     rcx, rbp; pwzUrl
0x18000bfef  mov     [rsp+68h+arg_10], 0
0x18000bffa  mov     edx, esi; ParseAction
0x18000bffc  mov     [rsp+68h+cchResult], eax; cchResult
0x18000c000  call    cs:__imp_CoInternetParseUrl
0x18000c006  mov     edi, eax
0x18000c008  test    edi, edi
0x18000c00a  jns     short loc_18000C026
0x18000c00c  test    rbx, rbx
0x18000c00f  jz      short loc_18000C026
0x18000c011  lea     rax, [rsp+68h+pszResult]
0x18000c016  cmp     rbx, rax
0x18000c019  jz      short loc_18000C026
0x18000c01b  mov     rcx, rbx; pv
0x18000c01e  call    cs:__imp_CoTaskMemFree
0x18000c024  xor     ebx, ebx
0x18000c026  xor     eax, eax
0x18000c028  test    edi, edi
0x18000c02a  cmovns  rax, rbx
0x18000c02e  mov     [r14], rax
0x18000c031  mov     eax, edi
0x18000c033  mov     rbx, [rsp+68h+arg_0]
0x18000c038  mov     rbp, [rsp+68h+arg_8]
0x18000c03d  add     rsp, 50h
0x18000c041  pop     r14
0x18000c043  pop     rdi
0x18000c044  pop     rsi
0x18000c045  retn
```
