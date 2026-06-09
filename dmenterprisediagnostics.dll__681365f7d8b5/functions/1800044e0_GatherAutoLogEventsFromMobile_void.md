# GatherAutoLogEventsFromMobile(void)

- ea: `0x1800044e0`
- end: `0x18000453b`
- name: `?GatherAutoLogEventsFromMobile@@YAJXZ`
- size: `91`
- prototype: `int(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800044e0`
- `0x180005c14`
- `0x1800084a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180004520`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180004520`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800044ea`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800044ea`

## string_xrefs

- `0x180004504`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`

## pseudocode

```c
__int64 GatherAutoLogEventsFromMobile(void)
{
  HRESULT v0; // eax
  const unsigned __int16 *v1; // rcx
  unsigned int v2; // ebx
  __int64 result; // rax
  unsigned int v4; // ebx
  unsigned int v5; // r8d
  const char *v6; // r9
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v0 = CoInitializeEx(0, 0);
  v2 = v0;
  if ( v0 >= 0 )
  {
    try
    {
      v4 = DmDiagnosticsCollector::GatherEnterpriseDiagnosticsEventsFromMobileAutoLoggers(v1);
      CoUninitialize();
      result = v4;
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x193, v5, v6);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\dll\\dmautologging.cpp",
      (const char *)(unsigned int)v0,
      v7);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x1800044e0  push    rbx; int
0x1800044e2  sub     rsp, 20h
0x1800044e6  xor     edx, edx; dwCoInit
0x1800044e8  xor     ecx, ecx; pvReserved
0x1800044ea  call    cs:__imp_CoInitializeEx
0x1800044f1  nop     dword ptr [rax+rax+00h]
0x1800044f6  mov     ebx, eax
0x1800044f8  test    eax, eax
0x1800044fa  jns     short loc_180004519
0x1800044fc  mov     rcx, [rsp+28h]; this
0x180004501  mov     r9d, eax; char *
0x180004504  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18000450b  mov     edx, 18Ch; void *
0x180004510  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004515  mov     eax, ebx
0x180004517  jmp     short loc_180004534
0x180004519  call    ?GatherEnterpriseDiagnosticsEventsFromMobileAutoLoggers@DmDiagnosticsCollector@@SAJPEBG@Z; DmDiagnosticsCollector::GatherEnterpriseDiagnosticsEventsFromMobileAutoLoggers(ushort const *)
0x18000451e  mov     ebx, eax
0x180004520  call    cs:__imp_CoUninitialize
0x180004527  nop     dword ptr [rax+rax+00h]
0x18000452c  mov     eax, ebx
0x18000452e  jmp     short loc_180004534
0x180004530  mov     eax, [rsp+28h+arg_0]
0x180004534  add     rsp, 20h
0x180004538  pop     rbx
0x180004539  retn
```
