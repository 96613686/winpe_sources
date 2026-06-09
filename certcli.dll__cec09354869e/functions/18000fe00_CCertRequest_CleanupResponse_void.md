# CCertRequest::_CleanupResponse(void)

- ea: `0x18000fe00`
- end: `0x18000fef2`
- name: `?_CleanupResponse@CCertRequest@@AEAAXXZ`
- size: `242`
- prototype: `void __fastcall(CCertRequest *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000fddc`
- `0x18001092c`

## callees

- `0x18000fe00`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fe7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fe7f`
- `crypttpmeksvc!FreeCMCResponse` at `0x18000fe9e`
- `crypttpmeksvc!FreeCMCResponse` at `0x18000fe9e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fecd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fecd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe66`
- `CRYPT32!CertCloseStore` at `0x18000febc`
- `CRYPT32!CertCloseStore` at `0x18000febc`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CCertRequest::_CleanupResponse(CCertRequest *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  __int64 v7; // rcx
  void *v8; // rcx

  v2 = (void *)*((_QWORD *)this + 17);
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *((_QWORD *)this + 17) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 20);
  if ( v3 )
  {
    CoTaskMemFree(v3);
    *((_QWORD *)this + 20) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 22);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 22) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 24);
  if ( v5 )
  {
    CoTaskMemFree(v5);
    *((_QWORD *)this + 24) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 18);
  if ( v6 )
  {
    LocalFree(v6);
    *((_QWORD *)this + 18) = 0;
  }
  v7 = *((_QWORD *)this + 27);
  if ( v7 )
  {
    FreeCMCResponse(v7, *((unsigned int *)this + 56));
    *((_QWORD *)this + 27) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 26);
  if ( v8 )
  {
    CertCloseStore(v8, 2u);
    *((_QWORD *)this + 26) = 0;
  }
  SysFreeString(*((BSTR *)this + 15));
  *((_QWORD *)this + 15) = 0;
  *((_DWORD *)this + 56) = 0;
  *(_QWORD *)((char *)this + 108) = 0;
  *((_DWORD *)this + 32) = 0;
}

```

## disassembly

```asm
0x18000fe00  mov     [rsp+arg_0], rbx
0x18000fe05  push    rdi
0x18000fe06  sub     rsp, 20h
0x18000fe0a  mov     rbx, rcx
0x18000fe0d  xor     edi, edi
0x18000fe0f  mov     rcx, [rcx+88h]; pv
0x18000fe16  test    rcx, rcx
0x18000fe19  jz      short loc_18000FE28
0x18000fe1b  call    cs:__imp_CoTaskMemFree
0x18000fe21  mov     [rbx+88h], rdi
0x18000fe28  mov     rcx, [rbx+0A0h]; pv
0x18000fe2f  test    rcx, rcx
0x18000fe32  jz      short loc_18000FE41
0x18000fe34  call    cs:__imp_CoTaskMemFree
0x18000fe3a  mov     [rbx+0A0h], rdi
0x18000fe41  mov     rcx, [rbx+0B0h]; pv
0x18000fe48  test    rcx, rcx
0x18000fe4b  jz      short loc_18000FE5A
0x18000fe4d  call    cs:__imp_CoTaskMemFree
0x18000fe53  mov     [rbx+0B0h], rdi
0x18000fe5a  mov     rcx, [rbx+0C0h]; pv
0x18000fe61  test    rcx, rcx
0x18000fe64  jz      short loc_18000FE73
0x18000fe66  call    cs:__imp_CoTaskMemFree
0x18000fe6c  mov     [rbx+0C0h], rdi
0x18000fe73  mov     rcx, [rbx+90h]; hMem
0x18000fe7a  test    rcx, rcx
0x18000fe7d  jz      short loc_18000FE8C
0x18000fe7f  call    cs:__imp_LocalFree
0x18000fe85  mov     [rbx+90h], rdi
0x18000fe8c  mov     rcx, [rbx+0D8h]
0x18000fe93  test    rcx, rcx
0x18000fe96  jz      short loc_18000FEAB
0x18000fe98  mov     edx, [rbx+0E0h]
0x18000fe9e  call    cs:__imp_FreeCMCResponse
0x18000fea4  mov     [rbx+0D8h], rdi
0x18000feab  mov     rcx, [rbx+0D0h]; hCertStore
0x18000feb2  test    rcx, rcx
0x18000feb5  jz      short loc_18000FEC9
0x18000feb7  mov     edx, 2; dwFlags
0x18000febc  call    cs:__imp_CertCloseStore
0x18000fec2  mov     [rbx+0D0h], rdi
0x18000fec9  mov     rcx, [rbx+78h]; bstrString
0x18000fecd  call    cs:__imp_SysFreeString
0x18000fed3  mov     [rbx+78h], rdi
0x18000fed7  mov     [rbx+0E0h], edi
0x18000fedd  mov     [rbx+6Ch], rdi
0x18000fee1  mov     [rbx+80h], edi
0x18000fee7  mov     rbx, [rsp+28h+arg_0]
0x18000feec  add     rsp, 20h
0x18000fef0  pop     rdi
0x18000fef1  retn
```
