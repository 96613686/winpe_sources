# GatherAutoLogEventsFromMobile(void)

- ea: `0x1800043e0`
- end: `0x18000442f`
- name: `?GatherAutoLogEventsFromMobile@@YAJXZ`
- size: `79`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800043e0`
- `0x180005a14`
- `0x1800080f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000441a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000441a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800043ea`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800043ea`

## string_xrefs

- `0x1800043fe`: `onecoreuap\admin\enterprisemgmt\enterprisediagnosticsetw\dll\dmautologging.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800043e0  push    rbx; int
0x1800043e2  sub     rsp, 20h
0x1800043e6  xor     edx, edx; dwCoInit
0x1800043e8  xor     ecx, ecx; pvReserved
0x1800043ea  call    cs:__imp_CoInitializeEx
0x1800043f0  mov     ebx, eax
0x1800043f2  test    eax, eax
0x1800043f4  jns     short loc_180004413
0x1800043f6  mov     rcx, [rsp+28h]; this
0x1800043fb  mov     r9d, eax; char *
0x1800043fe  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180004405  mov     edx, 18Ch; void *
0x18000440a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000440f  mov     eax, ebx
0x180004411  jmp     short loc_180004428
0x180004413  call    ?GatherEnterpriseDiagnosticsEventsFromMobileAutoLoggers@DmDiagnosticsCollector@@SAJPEBG@Z; DmDiagnosticsCollector::GatherEnterpriseDiagnosticsEventsFromMobileAutoLoggers(ushort const *)
0x180004418  mov     ebx, eax
0x18000441a  call    cs:__imp_CoUninitialize
0x180004420  mov     eax, ebx
0x180004422  jmp     short loc_180004428
0x180004424  mov     eax, [rsp+28h+arg_0]
0x180004428  add     rsp, 20h
0x18000442c  pop     rbx
0x18000442d  retn
```
