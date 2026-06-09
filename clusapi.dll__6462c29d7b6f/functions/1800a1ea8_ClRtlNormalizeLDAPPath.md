# ClRtlNormalizeLDAPPath

- ea: `0x1800a1ea8`
- end: `0x1800a201e`
- name: `ClRtlNormalizeLDAPPath`
- size: `374`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800a0c6c`
- `0x1800a1250`
- `0x1800a15c0`
- `0x1800a16fc`
- `0x1800a1d98`
- `0x1800a26f8`
- `0x1800a2904`
- `0x1800a2a74`

## callees

- `0x18009ef90`
- `0x1800a1ea8`
- `0x1800b5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1fd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1fd0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a1ef3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a1ef3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a2003`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a2003`

## pseudocode

```c
__int64 __fastcall ClRtlNormalizeLDAPPath(__int64 a1, _WORD *a2, __int64 *a3)
{
  int v6; // ebx
  __int64 v7; // rax
  signed int LastError; // eax
  BSTR bstrString[2]; // [rsp+30h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp+38h] BYREF

  ppv = 0;
  bstrString[0] = 0;
  v6 = CoCreateInstance(&CLSID_Pathname, 0, 1u, &IID_IADsPathname, &ppv);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64))(*(_QWORD *)ppv + 56LL))(ppv, L"LDAP", 2);
    if ( v6 >= 0 )
    {
      if ( !a2 )
        goto LABEL_8;
      if ( *a2 == 92 && a2[1] == 92 )
        a2 += 2;
      v6 = (*(__int64 (__fastcall **)(LPVOID, _WORD *, __int64))(*(_QWORD *)ppv + 56LL))(ppv, a2, 3);
      if ( v6 >= 0 )
      {
LABEL_8:
        v6 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 56LL))(ppv, a1, 4);
        if ( v6 >= 0 )
        {
          v6 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 136LL))(ppv, 2);
          if ( v6 >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(LPVOID, __int64, BSTR *))(*(_QWORD *)ppv + 72LL))(ppv, 1, bstrString);
            if ( v6 >= 0 )
            {
              v7 = ClRtlDupString(bstrString[0]);
              *a3 = v7;
              if ( !v7 )
              {
                LastError = GetLastError();
                v6 = LastError;
                if ( LastError > 0 )
                  v6 = (unsigned __int16)LastError | 0x80070000;
              }
            }
          }
        }
      }
    }
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( bstrString[0] )
    SysFreeString(bstrString[0]);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800a1ea8  mov     [rsp-18h+arg_0], rbx
0x1800a1ead  mov     [rsp-18h+arg_8], rsi
0x1800a1eb2  push    rbp
0x1800a1eb3  push    rdi
0x1800a1eb4  push    r14
0x1800a1eb6  mov     rbp, rsp
0x1800a1eb9  sub     rsp, 40h
0x1800a1ebd  mov     rdi, rdx
0x1800a1ec0  mov     [rbp+arg_18], 0
0x1800a1ec8  xor     edx, edx; pUnkOuter
0x1800a1eca  mov     [rbp+bstrString], 0
0x1800a1ed2  mov     rsi, r8
0x1800a1ed5  lea     rax, [rbp+arg_18]
0x1800a1ed9  mov     r14, rcx
0x1800a1edc  mov     [rsp+40h+ppv], rax; ppv
0x1800a1ee1  lea     r9, IID_IADsPathname; riid
0x1800a1ee8  lea     r8d, [rdx+1]; dwClsContext
0x1800a1eec  lea     rcx, CLSID_Pathname; rclsid
0x1800a1ef3  call    cs:__imp_CoCreateInstance
0x1800a1ef9  mov     ebx, eax
0x1800a1efb  test    eax, eax
0x1800a1efd  js      loc_1800A1FE5
0x1800a1f03  mov     rcx, [rbp+arg_18]
0x1800a1f07  lea     rdx, aLdap; "LDAP"
0x1800a1f0e  mov     r8d, 2
0x1800a1f14  mov     rax, [rcx]
0x1800a1f17  mov     rax, [rax+38h]
0x1800a1f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1f20  mov     ebx, eax
0x1800a1f22  test    eax, eax
0x1800a1f24  js      loc_1800A1FE5
0x1800a1f2a  test    rdi, rdi
0x1800a1f2d  jz      short loc_1800A1F63
0x1800a1f2f  cmp     word ptr [rdi], 5Ch ; '\'
0x1800a1f33  jnz     short loc_1800A1F40
0x1800a1f35  cmp     word ptr [rdi+2], 5Ch ; '\'
0x1800a1f3a  jnz     short loc_1800A1F40
0x1800a1f3c  add     rdi, 4
0x1800a1f40  mov     rcx, [rbp+arg_18]
0x1800a1f44  mov     r8d, 3
0x1800a1f4a  mov     rdx, rdi
0x1800a1f4d  mov     rax, [rcx]
0x1800a1f50  mov     rax, [rax+38h]
0x1800a1f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1f59  mov     ebx, eax
0x1800a1f5b  test    eax, eax
0x1800a1f5d  js      loc_1800A1FE5
0x1800a1f63  mov     rcx, [rbp+arg_18]
0x1800a1f67  mov     r8d, 4
0x1800a1f6d  mov     rdx, r14
0x1800a1f70  mov     rax, [rcx]
0x1800a1f73  mov     rax, [rax+38h]
0x1800a1f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1f7c  mov     ebx, eax
0x1800a1f7e  test    eax, eax
0x1800a1f80  js      short loc_1800A1FE5
0x1800a1f82  mov     rcx, [rbp+arg_18]
0x1800a1f86  mov     edx, 2
0x1800a1f8b  mov     rax, [rcx]
0x1800a1f8e  mov     rax, [rax+88h]
0x1800a1f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1f9a  mov     ebx, eax
0x1800a1f9c  test    eax, eax
0x1800a1f9e  js      short loc_1800A1FE5
0x1800a1fa0  mov     rcx, [rbp+arg_18]
0x1800a1fa4  lea     r8, [rbp+bstrString]
0x1800a1fa8  mov     edx, 1
0x1800a1fad  mov     rax, [rcx]
0x1800a1fb0  mov     rax, [rax+48h]
0x1800a1fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1fb9  mov     ebx, eax
0x1800a1fbb  test    eax, eax
0x1800a1fbd  js      short loc_1800A1FE5
0x1800a1fbf  mov     rcx, [rbp+bstrString]; wchar_t *
0x1800a1fc3  call    ClRtlDupString
0x1800a1fc8  mov     [rsi], rax
0x1800a1fcb  test    rax, rax
0x1800a1fce  jnz     short loc_1800A1FE5
0x1800a1fd0  call    cs:__imp_GetLastError
0x1800a1fd6  mov     ebx, eax
0x1800a1fd8  test    eax, eax
0x1800a1fda  jle     short loc_1800A1FE5
0x1800a1fdc  movzx   ebx, ax
0x1800a1fdf  or      ebx, 80070000h
0x1800a1fe5  mov     rcx, [rbp+arg_18]
0x1800a1fe9  test    rcx, rcx
0x1800a1fec  jz      short loc_1800A1FFA
0x1800a1fee  mov     rax, [rcx]
0x1800a1ff1  mov     rax, [rax+10h]
0x1800a1ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1ffa  mov     rcx, [rbp+bstrString]; bstrString
0x1800a1ffe  test    rcx, rcx
0x1800a2001  jz      short loc_1800A2009
0x1800a2003  call    cs:__imp_SysFreeString
0x1800a2009  mov     rsi, [rsp+40h+arg_8]
0x1800a200e  mov     eax, ebx
0x1800a2010  mov     rbx, [rsp+40h+arg_0]
0x1800a2015  add     rsp, 40h
0x1800a2019  pop     r14
0x1800a201b  pop     rdi
0x1800a201c  pop     rbp
0x1800a201d  retn
```
