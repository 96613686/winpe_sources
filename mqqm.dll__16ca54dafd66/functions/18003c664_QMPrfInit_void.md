# QMPrfInit(void)

- ea: `0x18003c664`
- end: `0x18003c7f0`
- name: `?QMPrfInit@@YAJXZ`
- size: `396`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002cd84`

## callees

- `0x18000d1f0`
- `0x18002c61c`
- `0x180033138`
- `0x1800341fc`
- `0x18003c644`
- `0x18003c664`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x18003c780`
- `msvcrt!free` at `0x18003c798`
- `msvcrt!free` at `0x18003c780`
- `msvcrt!free` at `0x18003c798`
- `msvcrt!_wcsicmp` at `0x18003c744`
- `msvcrt!_wcsicmp` at `0x18003c744`
- `ADVAPI32!RegQueryValueExW` at `0x18003c6d5`
- `ADVAPI32!RegQueryValueExW` at `0x18003c730`
- `ADVAPI32!RegQueryValueExW` at `0x18003c6d5`
- `ADVAPI32!RegQueryValueExW` at `0x18003c730`
- `ADVAPI32!RegOpenKeyExW` at `0x18003c694`
- `ADVAPI32!RegOpenKeyExW` at `0x18003c694`

## string_xrefs

- `0x18003c7d4`: `MSMQ Service`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 QMPrfInit(void)
{
  void *v0; // rbx
  int inited; // eax
  CPerf *v3; // rcx
  unsigned int v4; // ebx
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  DWORD Type; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF
  void *v8; // [rsp+58h] [rbp+20h]

  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\MSMQ\\Parameters", 0, 0x20019u, &hKey) )
    goto LABEL_10;
  cbData = 0;
  Type = 1;
  if ( RegQueryValueExW(hKey, L"NetNameForPerfCounters", 0, &Type, 0, &cbData) )
    goto LABEL_10;
  v0 = MmAllocate(saturated_mul((unsigned __int64)cbData >> 1, 2u));
  v8 = v0;
  if ( RegQueryValueExW(hKey, L"NetNameForPerfCounters", 0, &Type, (LPBYTE)v0, &cbData)
    || !_wcsicmp((const wchar_t *)v0, g_szMachineName) )
  {
    free(v0);
LABEL_10:
    CRegHandle::~CRegHandle((CRegHandle *)&hKey);
    inited = CPerf::InitPerf((CPerf *)&PerfApp);
    v4 = inited;
    if ( inited >= 0 )
    {
      CPerf::ValidateObject(v3, (wchar_t *)L"MSMQ Service");
      return 0;
    }
    else
    {
      LogMsgHR(inited, (wchar_t *)L"qmperf", 0xAu);
      return v4;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_54f5e3677e783fbec6da9e49b48fce1b_Traceguids);
  free(v0);
  CRegHandle::~CRegHandle((CRegHandle *)&hKey);
  return 0;
}

```

## disassembly

```asm
0x18003c664  push    rbx
0x18003c666  sub     rsp, 30h
0x18003c66a  mov     [rsp+38h+hKey], 0
0x18003c673  lea     rax, [rsp+38h+hKey]
0x18003c678  mov     [rsp+38h+phkResult], rax; phkResult
0x18003c67d  mov     r9d, 20019h; samDesired
0x18003c683  xor     r8d, r8d; ulOptions
0x18003c686  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\MSMQ\\Parameters"
0x18003c68d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003c694  call    cs:__imp_RegOpenKeyExW
0x18003c69a  test    eax, eax
0x18003c69c  jnz     loc_18003C79F
0x18003c6a2  mov     [rsp+38h+cbData], eax
0x18003c6a6  mov     [rsp+38h+Type], 1
0x18003c6ae  lea     rax, [rsp+38h+cbData]
0x18003c6b3  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18003c6b8  mov     [rsp+38h+phkResult], 0; lpData
0x18003c6c1  lea     r9, [rsp+38h+Type]; lpType
0x18003c6c6  xor     r8d, r8d; lpReserved
0x18003c6c9  lea     rdx, ValueName; "NetNameForPerfCounters"
0x18003c6d0  mov     rcx, [rsp+38h+hKey]; hKey
0x18003c6d5  call    cs:__imp_RegQueryValueExW
0x18003c6db  test    eax, eax
0x18003c6dd  jnz     loc_18003C79F
0x18003c6e3  mov     ecx, [rsp+38h+cbData]
0x18003c6e7  shr     rcx, 1
0x18003c6ea  mov     eax, 2
0x18003c6ef  mul     rcx
0x18003c6f2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003c6f9  cmovb   rax, rcx
0x18003c6fd  mov     rcx, rax; unsigned __int64
0x18003c700  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18003c705  mov     rbx, rax
0x18003c708  mov     [rsp+38h+arg_18], rax
0x18003c70d  lea     rax, [rsp+38h+cbData]
0x18003c712  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18003c717  mov     [rsp+38h+phkResult], rbx; lpData
0x18003c71c  lea     r9, [rsp+38h+Type]; lpType
0x18003c721  xor     r8d, r8d; lpReserved
0x18003c724  lea     rdx, ValueName; "NetNameForPerfCounters"
0x18003c72b  mov     rcx, [rsp+38h+hKey]; hKey
0x18003c730  call    cs:__imp_RegQueryValueExW
0x18003c736  test    eax, eax
0x18003c738  jnz     short loc_18003C795
0x18003c73a  mov     rdx, cs:?g_szMachineName@@3PEA_WEA; String2
0x18003c741  mov     rcx, rbx; String1
0x18003c744  call    cs:__imp__wcsicmp
0x18003c74a  test    eax, eax
0x18003c74c  jz      short loc_18003C795
0x18003c74e  lea     rax, WPP_GLOBAL_Control
0x18003c755  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c75c  cmp     rcx, rax
0x18003c75f  jz      short loc_18003C77D
0x18003c761  test    byte ptr [rcx+1Ch], 4
0x18003c765  jz      short loc_18003C77D
0x18003c767  mov     edx, 0Ah
0x18003c76c  lea     r8, WPP_54f5e3677e783fbec6da9e49b48fce1b_Traceguids
0x18003c773  mov     rcx, [rcx+10h]
0x18003c777  call    WPP_SF_
0x18003c77c  nop
0x18003c77d  mov     rcx, rbx; Block
0x18003c780  call    cs:__imp_free
0x18003c786  nop
0x18003c787  lea     rcx, [rsp+38h+hKey]; this
0x18003c78c  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x18003c791  xor     eax, eax
0x18003c793  jmp     short loc_18003C7E9
0x18003c795  mov     rcx, rbx; Block
0x18003c798  call    cs:__imp_free
0x18003c79e  nop
0x18003c79f  lea     rcx, [rsp+38h+hKey]; this
0x18003c7a4  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x18003c7a9  nop
0x18003c7aa  lea     rcx, ?PerfApp@@3VCPerf@@A; this
0x18003c7b1  call    ?InitPerf@CPerf@@QEAAJXZ; CPerf::InitPerf(void)
0x18003c7b6  mov     ebx, eax
0x18003c7b8  test    eax, eax
0x18003c7ba  jns     short loc_18003C7D4
0x18003c7bc  mov     r8d, 0Ah; unsigned __int16
0x18003c7c2  lea     rdx, aQmperf; "qmperf"
0x18003c7c9  mov     ecx, eax; int
0x18003c7cb  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18003c7d0  mov     eax, ebx
0x18003c7d2  jmp     short loc_18003C7E9
0x18003c7d4  lea     rdx, aMsmqService; "MSMQ Service"
0x18003c7db  call    ?ValidateObject@CPerf@@QEAAHPEA_W@Z; CPerf::ValidateObject(wchar_t *)
0x18003c7e0  xor     eax, eax
0x18003c7e2  jmp     short loc_18003C7E9
0x18003c7e4  mov     eax, 0C00E0027h
0x18003c7e9  add     rsp, 30h
0x18003c7ed  pop     rbx
0x18003c7ee  retn
```
