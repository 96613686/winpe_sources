# IsThirdPartyFwRunning(void)

- ea: `0x180003570`
- end: `0x1800036f1`
- name: `?IsThirdPartyFwRunning@@YAHXZ`
- size: `385`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800025c8`
- `0x180002b64`

## callees

- `0x180003570`
- `0x180005010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800035b8`
- `OLEAUT32!__imp_SysAllocString` at `0x18000361d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800035b8`
- `OLEAUT32!__imp_SysAllocString` at `0x18000361d`
- `OLEAUT32!__imp_SysFreeString` at `0x180003604`
- `OLEAUT32!__imp_SysFreeString` at `0x1800036b6`
- `OLEAUT32!__imp_SysFreeString` at `0x180003604`
- `OLEAUT32!__imp_SysFreeString` at `0x1800036b6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800035a3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800035a3`

## string_xrefs

- `0x1800035b1`: `ROOT\SecurityCenter`

## pseudocode

```c
__int64 IsThirdPartyFwRunning(void)
{
  unsigned int v0; // esi
  OLECHAR *v1; // rdi
  int v2; // ebx
  OLECHAR *v3; // rbx
  LPVOID ppv; // [rsp+50h] [rbp-18h] BYREF
  int v6; // [rsp+90h] [rbp+28h] BYREF
  __int64 v7; // [rsp+98h] [rbp+30h] BYREF
  __int64 v8; // [rsp+A0h] [rbp+38h] BYREF
  __int64 v9; // [rsp+A8h] [rbp+40h] BYREF

  v0 = 0;
  ppv = 0;
  v9 = 0;
  if ( CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, &ppv) >= 0 )
  {
    v1 = SysAllocString(L"ROOT\\SecurityCenter");
    if ( v1 )
    {
      v2 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)ppv + 24LL))(
             ppv,
             v1,
             0,
             0,
             0,
             0,
             0,
             0,
             &v9);
      SysFreeString(v1);
      if ( v2 >= 0 )
      {
        v8 = 0;
        v3 = SysAllocString(L"FirewallProduct");
        if ( v3 )
        {
          if ( (*(int (__fastcall **)(__int64, OLECHAR *, __int64, _QWORD, __int64 *))(*(_QWORD *)v9 + 144LL))(
                 v9,
                 v3,
                 32,
                 0,
                 &v8) >= 0 )
          {
            v7 = 0;
            v6 = 0;
            if ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64, __int64 *, int *))(*(_QWORD *)v8 + 32LL))(
                    v8,
                    1000,
                    1,
                    &v7,
                    &v6) )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
              v7 = 0;
              v0 = 1;
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
          }
          SysFreeString(v3);
        }
      }
    }
  }
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v0;
}

```

## disassembly

```asm
0x180003570  push    rbp
0x180003572  push    rbx
0x180003573  push    rsi
0x180003574  push    rdi
0x180003575  mov     rbp, rsp
0x180003578  sub     rsp, 68h
0x18000357c  xor     esi, esi
0x18000357e  lea     rax, [rbp+var_18]
0x180003582  lea     r9, IID_IWbemLocator; riid
0x180003589  mov     [rbp+var_18], rsi
0x18000358d  xor     edx, edx; pUnkOuter
0x18000358f  mov     [rbp+arg_18], rsi
0x180003593  lea     rcx, CLSID_WbemLocator; rclsid
0x18000359a  mov     [rsp+68h+ppv], rax; ppv
0x18000359f  lea     r8d, [rsi+1]; dwClsContext
0x1800035a3  call    cs:__imp_CoCreateInstance
0x1800035a9  test    eax, eax
0x1800035ab  js      loc_1800036BC
0x1800035b1  lea     rcx, psz; "ROOT\\SecurityCenter"
0x1800035b8  call    cs:__imp_SysAllocString
0x1800035be  mov     rdi, rax
0x1800035c1  test    rax, rax
0x1800035c4  jz      loc_1800036BC
0x1800035ca  mov     rcx, [rbp+var_18]
0x1800035ce  xor     r9d, r9d
0x1800035d1  xor     r8d, r8d
0x1800035d4  mov     rdx, [rcx]
0x1800035d7  mov     rax, [rdx+18h]
0x1800035db  lea     rdx, [rbp+arg_18]
0x1800035df  mov     [rsp+68h+var_28], rdx
0x1800035e4  mov     rdx, rdi
0x1800035e7  mov     [rsp+68h+var_30], rsi
0x1800035ec  mov     [rsp+68h+var_38], rsi
0x1800035f1  mov     [rsp+68h+var_40], esi
0x1800035f5  mov     [rsp+68h+ppv], rsi
0x1800035fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035ff  mov     rcx, rdi; bstrString
0x180003602  mov     ebx, eax
0x180003604  call    cs:__imp_SysFreeString
0x18000360a  test    ebx, ebx
0x18000360c  js      loc_1800036BC
0x180003612  lea     rcx, aFirewallproduc; "FirewallProduct"
0x180003619  mov     [rbp+arg_10], rsi
0x18000361d  call    cs:__imp_SysAllocString
0x180003623  mov     rbx, rax
0x180003626  test    rax, rax
0x180003629  jz      loc_1800036BC
0x18000362f  mov     rcx, [rbp+arg_18]
0x180003633  lea     r8d, [rsi+20h]
0x180003637  xor     r9d, r9d
0x18000363a  mov     rdx, [rcx]
0x18000363d  mov     rax, [rdx+90h]
0x180003644  lea     rdx, [rbp+arg_10]
0x180003648  mov     [rsp+68h+ppv], rdx
0x18000364d  mov     rdx, rbx
0x180003650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003655  test    eax, eax
0x180003657  js      short loc_1800036B3
0x180003659  mov     rcx, [rbp+arg_10]
0x18000365d  lea     rdx, [rbp+arg_0]
0x180003661  mov     [rbp+arg_8], rsi
0x180003665  lea     r9, [rbp+arg_8]
0x180003669  mov     [rbp+arg_0], esi
0x18000366c  lea     r8d, [rsi+1]
0x180003670  mov     [rsp+68h+ppv], rdx
0x180003675  mov     edx, 3E8h
0x18000367a  mov     rax, [rcx]
0x18000367d  mov     rax, [rax+20h]
0x180003681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003686  test    eax, eax
0x180003688  jnz     short loc_1800036A3
0x18000368a  mov     rcx, [rbp+arg_8]
0x18000368e  mov     rax, [rcx]
0x180003691  mov     rax, [rax+10h]
0x180003695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000369a  mov     [rbp+arg_8], rsi
0x18000369e  mov     esi, 1
0x1800036a3  mov     rcx, [rbp+arg_10]
0x1800036a7  mov     rax, [rcx]
0x1800036aa  mov     rax, [rax+10h]
0x1800036ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036b3  mov     rcx, rbx; bstrString
0x1800036b6  call    cs:__imp_SysFreeString
0x1800036bc  mov     rcx, [rbp+arg_18]
0x1800036c0  test    rcx, rcx
0x1800036c3  jz      short loc_1800036D1
0x1800036c5  mov     rax, [rcx]
0x1800036c8  mov     rax, [rax+10h]
0x1800036cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036d1  mov     rcx, [rbp+var_18]
0x1800036d5  test    rcx, rcx
0x1800036d8  jz      short loc_1800036E6
0x1800036da  mov     rdx, [rcx]
0x1800036dd  mov     rax, [rdx+10h]
0x1800036e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036e6  mov     eax, esi
0x1800036e8  add     rsp, 68h
0x1800036ec  pop     rdi
0x1800036ed  pop     rsi
0x1800036ee  pop     rbx
0x1800036ef  pop     rbp
0x1800036f0  retn
```
