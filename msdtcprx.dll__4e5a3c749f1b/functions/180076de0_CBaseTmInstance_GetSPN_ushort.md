# CBaseTmInstance::GetSPN(ushort * *)

- ea: `0x180076de0`
- end: `0x180076f8a`
- name: `?GetSPN@CBaseTmInstance@@UEAAJPEAPEAG@Z`
- size: `426`
- prototype: `int(CBaseTmInstance *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180006324`
- `0x1800092f4`
- `0x18000c6bc`
- `0x18000d5f4`
- `0x18001ad1c`
- `0x180076de0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076f5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076f64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076f71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076f5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076f64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076f71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180076f00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180076f00`

## string_xrefs

- `0x180076e3e`: `com\complus\dtc\shared\util\basetminstance.cpp`
- `0x180076ebe`: `NT AUTHORITY\NetworkService`
- `0x180076e0d`: `CBaseTmInstance::GetSPN (com\complus\dtc\shared\util\basetminstance.cpp@1752): CBaseTmInstance::GetSPN, ppwszSPN != NULL`
- `0x180076f13`: `CoTaskMemAlloc(cchSPN*sizeof(WCHAR)) failed`

## pseudocode

```c
__int64 __fastcall CBaseTmInstance::GetSPN(CBaseTmInstance *this, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rdi
  int PhysicalNodeNameW; // ebx
  const wchar_t *v6; // rax
  __int64 v7; // r9
  __int64 v8; // rax
  unsigned __int64 v9; // rbx
  unsigned __int16 *v10; // rax
  __int64 v12; // [rsp+28h] [rbp-18h]
  int v13; // [rsp+78h] [rbp+38h] BYREF
  LPVOID pv; // [rsp+80h] [rbp+40h] BYREF
  unsigned __int16 *v15; // [rsp+88h] [rbp+48h] BYREF

  pv = 0;
  v15 = 0;
  v13 = 0;
  if ( !a2 )
    DtcInternalErrorW(
      L"CBaseTmInstance::GetSPN (com\\complus\\dtc\\shared\\util\\basetminstance.cpp@1752): CBaseTmInstance::GetSPN, ppwszSPN != NULL");
  v4 = 0;
  PhysicalNodeNameW = GetPhysicalNodeNameW((BYTE **)&v15);
  if ( PhysicalNodeNameW < 0 )
  {
    v6 = L"GetPhysicalNodeNameW failed";
    v7 = 1758;
LABEL_5:
    LODWORD(v12) = PhysicalNodeNameW;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\basetminstance.cpp",
      v7,
      L"CBaseTmInstance::GetSPN",
      v12,
      v6);
    goto LABEL_20;
  }
  PhysicalNodeNameW = (*(__int64 (__fastcall **)(CBaseTmInstance *, LPVOID *))(*(_QWORD *)this + 40LL))(this, &pv);
  if ( PhysicalNodeNameW < 0 )
  {
    v6 = L"GetHostName failed";
    v7 = 1765;
    goto LABEL_5;
  }
  PhysicalNodeNameW = UtilMtxcluIsSameNodeW(v15, pv, &v13);
  if ( PhysicalNodeNameW < 0 )
  {
    v6 = L"Error calling UtilMtxcluIsSameNodeW";
    v7 = 1777;
    goto LABEL_5;
  }
  if ( v13 )
  {
    PhysicalNodeNameW = DuplicateString(L"NT AUTHORITY\\NetworkService", a2);
    if ( PhysicalNodeNameW < 0 )
    {
      v6 = L"DuplicateString failed";
      v7 = 1787;
      goto LABEL_5;
    }
  }
  else
  {
    v8 = -1;
    do
      ++v8;
    while ( *((_WORD *)pv + v8) );
    v9 = v8 + 6;
    v10 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v8 + 6));
    v4 = v10;
    if ( !v10 )
    {
      PhysicalNodeNameW = -2147024882;
      v6 = L"CoTaskMemAlloc(cchSPN*sizeof(WCHAR)) failed";
      v7 = 1798;
      goto LABEL_5;
    }
    PhysicalNodeNameW = StringCchPrintfW(v10, v9, L"host/%s", pv);
    if ( PhysicalNodeNameW < 0 )
    {
      v6 = L"StringCchPrintfW failed";
      v7 = 1804;
      goto LABEL_5;
    }
    *a2 = v4;
  }
LABEL_20:
  CoTaskMemFree(pv);
  CoTaskMemFree(v15);
  if ( PhysicalNodeNameW < 0 )
    CoTaskMemFree(v4);
  return (unsigned int)PhysicalNodeNameW;
}

```

## disassembly

```asm
0x180076de0  mov     [rsp-28h+arg_0], rbx
0x180076de5  push    rbp
0x180076de6  push    rsi
0x180076de7  push    rdi
0x180076de8  push    r14
0x180076dea  push    r15
0x180076dec  mov     rbp, rsp
0x180076def  sub     rsp, 40h
0x180076df3  xor     r15d, r15d
0x180076df6  mov     rsi, rdx
0x180076df9  mov     [rbp+pv], r15
0x180076dfd  mov     r14, rcx
0x180076e00  mov     [rbp+arg_18], r15
0x180076e04  mov     [rbp+arg_8], r15d
0x180076e08  test    rdx, rdx
0x180076e0b  jnz     short loc_180076E1A
0x180076e0d  lea     rcx, aCbasetminstanc_16; "CBaseTmInstance::GetSPN (com\\complus\\"...
0x180076e14  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180076e1a  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x180076e1e  mov     rdi, r15
0x180076e21  call    ?GetPhysicalNodeNameW@@YAJPEAPEAG@Z; GetPhysicalNodeNameW(ushort * *)
0x180076e26  mov     ebx, eax
0x180076e28  test    eax, eax
0x180076e2a  jns     short loc_180076E67
0x180076e2c  lea     rax, aGetphysicalnod; "GetPhysicalNodeNameW failed"
0x180076e33  mov     r9d, 6DEh
0x180076e39  mov     [rsp+40h+var_10], rax
0x180076e3e  lea     r8, aComComplusDtcS_3; "com\\complus\\dtc\\shared\\util\\basetm"...
0x180076e45  mov     edx, 1
0x180076e4a  mov     dword ptr [rsp+40h+var_18], ebx
0x180076e4e  lea     rax, aCbasetminstanc_19; "CBaseTmInstance::GetSPN"
0x180076e55  mov     [rsp+40h+var_20], rax
0x180076e5a  lea     ecx, [rdx+6]
0x180076e5d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180076e62  jmp     loc_180076F56
0x180076e67  mov     rax, [r14]
0x180076e6a  lea     rdx, [rbp+pv]
0x180076e6e  mov     rcx, r14
0x180076e71  mov     rax, [rax+28h]
0x180076e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076e7a  mov     ebx, eax
0x180076e7c  test    eax, eax
0x180076e7e  jns     short loc_180076E8F
0x180076e80  lea     rax, aGethostnameFai; "GetHostName failed"
0x180076e87  mov     r9d, 6E5h
0x180076e8d  jmp     short loc_180076E39
0x180076e8f  mov     rdx, [rbp+pv]
0x180076e93  lea     r8, [rbp+arg_8]
0x180076e97  mov     rcx, [rbp+arg_18]
0x180076e9b  call    UtilMtxcluIsSameNodeW
0x180076ea0  mov     ebx, eax
0x180076ea2  test    eax, eax
0x180076ea4  jns     short loc_180076EB5
0x180076ea6  lea     rax, aErrorCallingUt; "Error calling UtilMtxcluIsSameNodeW"
0x180076ead  mov     r9d, 6F1h
0x180076eb3  jmp     short loc_180076E39
0x180076eb5  cmp     [rbp+arg_8], r15d
0x180076eb9  jz      short loc_180076EE6
0x180076ebb  mov     rdx, rsi; unsigned __int16 **
0x180076ebe  lea     rcx, aNtAuthorityNet; "NT AUTHORITY\\NetworkService"
0x180076ec5  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x180076eca  mov     ebx, eax
0x180076ecc  test    eax, eax
0x180076ece  jns     loc_180076F56
0x180076ed4  lea     rax, aDuplicatestrin_5; "DuplicateString failed"
0x180076edb  mov     r9d, 6FBh
0x180076ee1  jmp     loc_180076E39
0x180076ee6  mov     rcx, [rbp+pv]
0x180076eea  or      rax, 0FFFFFFFFFFFFFFFFh
0x180076eee  inc     rax
0x180076ef1  cmp     [rcx+rax*2], r15w
0x180076ef6  jnz     short loc_180076EEE
0x180076ef8  lea     rbx, [rax+6]
0x180076efc  lea     rcx, [rbx+rbx]; cb
0x180076f00  call    cs:__imp_CoTaskMemAlloc
0x180076f06  mov     rdi, rax
0x180076f09  test    rax, rax
0x180076f0c  jnz     short loc_180076F25
0x180076f0e  mov     ebx, 8007000Eh
0x180076f13  lea     rax, aCotaskmemalloc_0; "CoTaskMemAlloc(cchSPN*sizeof(WCHAR)) fa"...
0x180076f1a  mov     r9d, 706h
0x180076f20  jmp     loc_180076E39
0x180076f25  mov     r9, [rbp+pv]
0x180076f29  lea     r8, aHostS; "host/%s"
0x180076f30  mov     rdx, rbx; unsigned __int64
0x180076f33  mov     rcx, rdi; unsigned __int16 *
0x180076f36  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180076f3b  mov     ebx, eax
0x180076f3d  test    eax, eax
0x180076f3f  jns     short loc_180076F53
0x180076f41  lea     rax, aStringcchprint_0; "StringCchPrintfW failed"
0x180076f48  mov     r9d, 70Ch
0x180076f4e  jmp     loc_180076E39
0x180076f53  mov     [rsi], rdi
0x180076f56  mov     rcx, [rbp+pv]; pv
0x180076f5a  call    cs:__imp_CoTaskMemFree
0x180076f60  mov     rcx, [rbp+arg_18]; pv
0x180076f64  call    cs:__imp_CoTaskMemFree
0x180076f6a  test    ebx, ebx
0x180076f6c  jns     short loc_180076F77
0x180076f6e  mov     rcx, rdi; pv
0x180076f71  call    cs:__imp_CoTaskMemFree
0x180076f77  mov     eax, ebx
0x180076f79  mov     rbx, [rsp+40h+arg_0]
0x180076f7e  add     rsp, 40h
0x180076f82  pop     r15
0x180076f84  pop     r14
0x180076f86  pop     rdi
0x180076f87  pop     rsi
0x180076f88  pop     rbp
0x180076f89  retn
```
