# DpSearch::DpSearch(void)

- ea: `0x180007a40`
- end: `0x180007b06`
- name: `??0DpSearch@@QEAA@XZ`
- size: `198`
- prototype: `LPVOID *__fastcall(LPVOID *ppv)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004020`
- `0x180004a00`

## callees

- `0x180001d04`
- `0x1800020d8`
- `0x180007a40`
- `0x1800091fc`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007a94`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007a94`

## pseudocode

```c
LPVOID *__fastcall DpSearch::DpSearch(LPVOID *ppv)
{
  HRESULT Instance; // eax
  int v3; // eax
  char pExceptionObject; // [rsp+48h] [rbp+10h] BYREF

  *ppv = 0;
  ppv[1] = 0;
  ppv[2] = 0;
  ppv[3] = 0;
  GetUserSIDString(ppv + 4);
  Instance = CoCreateInstance(
               &GUID_7d096c5f_ac08_4f1f_beb7_5c22c517ce39,
               0,
               0x15u,
               &GUID_ab310581_ac80_11d1_8df3_00c04fb6ef69,
               ppv);
  if ( Instance < 0 )
  {
    ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, Instance);
    throw (ATL::CAtlException *)&pExceptionObject;
  }
  v3 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, LPVOID *))(*(_QWORD *)*ppv + 80LL))(
         *ppv,
         L"SystemIndex",
         ppv + 1);
  if ( v3 < 0 )
  {
    ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, v3);
    throw (ATL::CAtlException *)&pExceptionObject;
  }
  return ppv;
}

```

## disassembly

```asm
0x180007a40  mov     [rsp+arg_10], rbx
0x180007a45  mov     [rsp+arg_0], rcx
0x180007a4a  push    rdi
0x180007a4b  sub     rsp, 30h
0x180007a4f  mov     rbx, rcx
0x180007a52  mov     qword ptr [rcx], 0
0x180007a59  mov     qword ptr [rcx+8], 0
0x180007a61  mov     qword ptr [rcx+10h], 0
0x180007a69  mov     qword ptr [rcx+18h], 0
0x180007a71  add     rcx, 20h ; ' '; Src
0x180007a75  call    ?GetUserSIDString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GetUserSIDString(void)
0x180007a7a  nop
0x180007a7b  mov     [rsp+38h+ppv], rbx; ppv
0x180007a80  lea     r9, _GUID_ab310581_ac80_11d1_8df3_00c04fb6ef69; riid
0x180007a87  xor     edx, edx; pUnkOuter
0x180007a89  lea     r8d, [rdx+15h]; dwClsContext
0x180007a8d  lea     rcx, _GUID_7d096c5f_ac08_4f1f_beb7_5c22c517ce39; rclsid
0x180007a94  call    cs:__imp_CoCreateInstance
0x180007a9a  test    eax, eax
0x180007a9c  js      short loc_180007AE8
0x180007a9e  mov     rcx, [rbx]
0x180007aa1  mov     rax, [rcx]
0x180007aa4  lea     r8, [rbx+8]
0x180007aa8  lea     rdx, aSystemindex; "SystemIndex"
0x180007aaf  mov     rax, [rax+50h]
0x180007ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ab8  test    eax, eax
0x180007aba  js      short loc_180007ACA
0x180007abc  mov     rax, rbx
0x180007abf  mov     rbx, [rsp+38h+arg_10]
0x180007ac4  add     rsp, 30h
0x180007ac8  pop     rdi
0x180007ac9  retn
0x180007aca  mov     edx, eax; int
0x180007acc  lea     rcx, [rsp+38h+pExceptionObject]; this
0x180007ad1  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x180007ad6  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x180007add  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180007ae2  call    _CxxThrowException_0
0x180007ae8  mov     edx, eax; int
0x180007aea  lea     rcx, [rsp+38h+pExceptionObject]; this
0x180007aef  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x180007af4  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x180007afb  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180007b00  call    _CxxThrowException_0
```
