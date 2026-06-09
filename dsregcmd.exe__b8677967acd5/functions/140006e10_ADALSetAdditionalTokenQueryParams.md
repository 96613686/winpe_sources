# ADALSetAdditionalTokenQueryParams

- ea: `0x140006e10`
- end: `0x140006e84`
- name: `ADALSetAdditionalTokenQueryParams`
- size: `116`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140003bc0`

## callees

- `0x140006484`
- `0x140006e10`
- `0x140009034`
- `0x14000e020`
- `0x14002c3e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006e27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006e27`

## pseudocode

```c
__int64 __fastcall ADALSetAdditionalTokenQueryParams(__int64 a1, __int64 a2)
{
  char v4; // al
  __int64 v5; // rdx
  __int64 result; // rax
  const Exception *v7; // [rsp+20h] [rbp-28h] BYREF
  const std::exception *v8; // [rsp+28h] [rbp-20h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-18h] BYREF

  SetLastError(0);
  if ( !a1 || (v4 = APIHandle<AuthenticationContext,HADALCONTEXT__ *,-1441095254>::Validate(a1)) == 0 )
  {
    InvalidHandleException::InvalidHandleException((InvalidHandleException *)pExceptionObject, 0xCAA1000E);
    throw (InvalidHandleException *)pExceptionObject;
  }
  try
  {
    AuthenticationContext::SetAdditionalQueryStrings(*(_QWORD *)(a1 + 8), v5, 0, a2);
    result = 1;
  }
  catch ( const Exception *v7 )
  {
    HandleException((struct HADALCONTEXT__ *)a1, v7);
    return 0;
  }
  catch ( const std::exception *v8 )
  {
    HandleException((struct HADALCONTEXT__ *)a1, v8);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140006e10  mov     [rsp+arg_8], rbx
0x140006e15  mov     [rsp+arg_0], rcx
0x140006e1a  push    rdi
0x140006e1b  sub     rsp, 40h
0x140006e1f  mov     rdi, rdx
0x140006e22  mov     rbx, rcx
0x140006e25  xor     ecx, ecx; dwErrCode
0x140006e27  call    cs:__imp_SetLastError
0x140006e2d  nop
0x140006e2e  test    rbx, rbx
0x140006e31  jz      short loc_140006E62
0x140006e33  mov     rcx, rbx
0x140006e36  call    ?Validate@?$APIHandle@VAuthenticationContext@@PEAUHADALCONTEXT__@@$0?FFOFFOFG@@@CA_NPEBV1@@Z; APIHandle<AuthenticationContext,HADALCONTEXT__ *,-1441095254>::Validate(APIHandle<AuthenticationContext,HADALCONTEXT__ *,-1441095254> const *)
0x140006e3b  test    al, al
0x140006e3d  jz      short loc_140006E62
0x140006e3f  mov     r9, rdi
0x140006e42  xor     r8d, r8d
0x140006e45  mov     rcx, [rbx+8]
0x140006e49  call    ?SetAdditionalQueryStrings@AuthenticationContext@@QEAAXW4EndpointType@@_NPEBG@Z; AuthenticationContext::SetAdditionalQueryStrings(EndpointType,bool,ushort const *)
0x140006e4e  mov     eax, 1
0x140006e53  jmp     short loc_140006E57
0x140006e55  xor     eax, eax
0x140006e57  mov     rbx, [rsp+48h+arg_8]
0x140006e5c  add     rsp, 40h
0x140006e60  pop     rdi
0x140006e61  retn
0x140006e62  mov     edx, 0CAA1000Eh; unsigned int
0x140006e67  lea     rcx, [rsp+48h+pExceptionObject]; this
0x140006e6c  call    ??0InvalidHandleException@@QEAA@K@Z; InvalidHandleException::InvalidHandleException(ulong)
0x140006e71  lea     rdx, _TI4?AVInvalidHandleException@@; pThrowInfo
0x140006e78  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x140006e7d  call    _CxxThrowException_0
```
