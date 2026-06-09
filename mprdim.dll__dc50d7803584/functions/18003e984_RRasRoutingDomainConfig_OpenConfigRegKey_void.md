# RRasRoutingDomainConfig::OpenConfigRegKey(void)

- ea: `0x18003e984`
- end: `0x18003ec40`
- name: `?OpenConfigRegKey@RRasRoutingDomainConfig@@QEAAKXZ`
- size: `700`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003bd5c`
- `0x18003de9c`
- `0x180041210`

## callees

- `0x180033e90`
- `0x180038eb8`
- `0x18003e984`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18003ea7c`
- `ADVAPI32!RegOpenKeyExW` at `0x18003ea7c`
- `ADVAPI32!RegCloseKey` at `0x18003ebf9`
- `ADVAPI32!RegCloseKey` at `0x18003ebf9`
- `ADVAPI32!RegCreateKeyExW` at `0x18003eb4d`
- `ADVAPI32!RegCreateKeyExW` at `0x18003eb4d`

## string_xrefs

- `0x18003ea6e`: `System\CurrentControlSet\Services\RemoteAccess\RoutingDomains`
- `0x18003eab7`: `System\CurrentControlSet\Services\RemoteAccess\RoutingDomains`
- `0x18003eac5`: `%s: RegOpenKeyEx (%s) failed: %d.`
- `0x18003ea34`: `RRasRoutingDomainConfig::OpenConfigRegKey`
- `0x18003eabe`: `RRasRoutingDomainConfig::OpenConfigRegKey`
- `0x18003eb8d`: `RRasRoutingDomainConfig::OpenConfigRegKey`
- `0x18003eb94`: `%s: RegCreateKeyEx failed for routing domain (%ws): %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RRasRoutingDomainConfig::OpenConfigRegKey(RRasRoutingDomainConfig *this)
{
  unsigned int v2; // ebx
  void (*v3)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  LSTATUS v4; // eax
  unsigned int v5; // ecx
  GUID *v6; // r9
  LSTATUS Key; // eax
  GUID *v8; // r9
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *samDesired; // [rsp+28h] [rbp-D8h]
  unsigned int lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  unsigned int v14; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v16; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v17; // [rsp+68h] [rbp-98h]
  __int128 v18; // [rsp+78h] [rbp-88h]
  __int64 v19; // [rsp+88h] [rbp-78h]
  int v20; // [rsp+90h] [rbp-70h]
  int v21; // [rsp+94h] [rbp-6Ch]
  GUID v22; // [rsp+98h] [rbp-68h] BYREF
  int v23; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v24; // [rsp+ACh] [rbp-54h]
  __int128 v25; // [rsp+BCh] [rbp-44h]
  int v26; // [rsp+CCh] [rbp-34h]
  WCHAR SubKey[40]; // [rsp+D0h] [rbp-30h] BYREF
  int v28; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v29[2044]; // [rsp+124h] [rbp+24h] BYREF

  v2 = 0;
  v14 = 0;
  hKey = 0;
  memset_0(SubKey, 0, sizeof(SubKey));
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v17 = 0;
  v16 = 0;
  v18 = 0;
  v19 = 0;
  v20 = -1;
  v21 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v16,
      L"RRasRoutingDomainConfig::OpenConfigRegKey",
      &v14,
      v3,
      (struct _GUID *)((char *)this + 516),
      samDesired,
      lpSecurityAttributes);
    v2 = v14;
  }
  if ( !*((_QWORD *)this + 103) )
  {
    v4 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains",
           0,
           0xF003Fu,
           &hKey);
    v5 = v4;
    v14 = v4;
    if ( v4 )
    {
      if ( (_QWORD)xmmword_1800710A0 )
      {
        LOWORD(v28) = 0;
        v22 = GUID_NULL;
        LOWORD(v23) = 0;
        LODWORD(phkResult) = v4;
        FormatRRASErrorString(
          &v28,
          L"%s: RegOpenKeyEx (%s) failed: %d.",
          L"RRasRoutingDomainConfig::OpenConfigRegKey",
          L"System\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains",
          phkResult);
        v6 = &v22;
        if ( this != (RRasRoutingDomainConfig *)-516LL )
          v6 = (GUID *)((char *)this + 516);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_1800710A0,
          &v28,
          v6,
          0,
          &v23);
        v5 = v14;
      }
    }
    else
    {
      MprConvertGuidToString((char *)this + 516, 40, SubKey);
      Key = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0xF003Fu, 0, (PHKEY)this + 103, 0);
      v5 = Key;
      v14 = Key;
      if ( Key || !*((_QWORD *)this + 103) )
      {
        if ( (_QWORD)xmmword_1800710A0 )
        {
          LOWORD(v28) = 0;
          v22 = GUID_NULL;
          LOWORD(v23) = 0;
          LODWORD(phkResulta) = Key;
          FormatRRASErrorString(
            &v28,
            L"%s: RegCreateKeyEx failed for routing domain (%ws): %d.",
            L"RRasRoutingDomainConfig::OpenConfigRegKey",
            SubKey,
            phkResulta);
          v8 = &v22;
          if ( this != (RRasRoutingDomainConfig *)-516LL )
            v8 = (GUID *)((char *)this + 516);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
            gCfgStoreEtwContext,
            xmmword_1800710A0,
            &v28,
            v8,
            0,
            &v23);
          v5 = v14;
        }
        if ( !v5 )
        {
          v5 = 6;
          v14 = 6;
        }
      }
    }
    if ( hKey )
    {
      RegCloseKey(hKey);
      v5 = v14;
    }
    if ( v5 )
    {
      RRasRoutingDomainConfig::CloseConfigRegKey(this);
      v5 = v14;
    }
    v2 = v5;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v16);
  return v2;
}

```

## disassembly

```asm
0x18003e984  push    rbp
0x18003e986  push    rbx
0x18003e987  push    rsi
0x18003e988  push    rdi
0x18003e989  push    r14
0x18003e98b  push    r15
0x18003e98d  lea     rbp, [rsp-838h]
0x18003e995  sub     rsp, 938h
0x18003e99c  mov     rax, cs:__security_cookie
0x18003e9a3  xor     rax, rsp
0x18003e9a6  mov     [rbp+860h+var_40], rax
0x18003e9ad  mov     r14, rcx
0x18003e9b0  xor     r15d, r15d
0x18003e9b3  mov     ebx, r15d
0x18003e9b6  mov     [rsp+960h+var_910], ebx
0x18003e9ba  mov     [rsp+960h+hKey], r15
0x18003e9bf  xor     edx, edx; Val
0x18003e9c1  lea     r8d, [r15+50h]; Size
0x18003e9c5  lea     rcx, [rbp+860h+SubKey]; void *
0x18003e9c9  call    memset_0
0x18003e9ce  mov     [rbp+860h+var_840], r15d
0x18003e9d2  xor     edx, edx; Val
0x18003e9d4  mov     r8d, 7FCh; Size
0x18003e9da  lea     rcx, [rbp+860h+var_83C]; void *
0x18003e9de  call    memset_0
0x18003e9e3  mov     [rbp+860h+var_8B8], r15d
0x18003e9e7  xorps   xmm0, xmm0
0x18003e9ea  xor     eax, eax
0x18003e9ec  movups  [rbp+860h+var_8B4], xmm0
0x18003e9f0  movups  [rbp+860h+var_8A4], xmm0
0x18003e9f4  mov     [rbp+860h+var_894], eax
0x18003e9f7  movdqu  [rsp+960h+var_8F8], xmm0
0x18003e9fd  mov     [rsp+960h+var_900], r15
0x18003ea02  xorps   xmm1, xmm1
0x18003ea05  movdqu  [rsp+960h+var_8E8], xmm1
0x18003ea0b  mov     [rbp+860h+var_8D8], r15
0x18003ea0f  mov     [rbp+860h+var_8D0], 0FFFFFFFFh
0x18003ea16  mov     [rbp+860h+var_8CC], r15d
0x18003ea1a  lea     rsi, [r14+204h]
0x18003ea21  cmp     qword ptr cs:xmmword_1800710A0+8, r15
0x18003ea28  jz      short loc_18003EA49
0x18003ea2a  mov     [rsp+960h+phkResult], rsi; struct _GUID *
0x18003ea2f  lea     r8, [rsp+960h+var_910]; unsigned int *
0x18003ea34  lea     rdx, aRrasroutingdom_40; "RRasRoutingDomainConfig::OpenConfigRegK"...
0x18003ea3b  lea     rcx, [rsp+960h+var_900]; this
0x18003ea40  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18003ea45  mov     ebx, [rsp+960h+var_910]
0x18003ea49  lea     rdi, [r14+338h]
0x18003ea50  cmp     [rdi], r15
0x18003ea53  jnz     loc_18003EC15
0x18003ea59  lea     rax, [rsp+960h+hKey]
0x18003ea5e  mov     [rsp+960h+phkResult], rax; phkResult
0x18003ea63  mov     ebx, 0F003Fh
0x18003ea68  mov     r9d, ebx; samDesired
0x18003ea6b  xor     r8d, r8d; ulOptions
0x18003ea6e  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Re"...
0x18003ea75  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003ea7c  call    cs:__imp_RegOpenKeyExW
0x18003ea82  mov     ecx, eax
0x18003ea84  mov     [rsp+960h+var_910], eax
0x18003ea88  test    eax, eax
0x18003ea8a  jz      loc_18003EB15
0x18003ea90  cmp     qword ptr cs:xmmword_1800710A0, r15
0x18003ea97  jz      loc_18003EBEC
0x18003ea9d  mov     word ptr [rbp+860h+var_840], r15w
0x18003eaa2  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003eaa9  movdqu  [rbp+860h+var_8C8], xmm0
0x18003eaae  mov     word ptr [rbp+860h+var_8B8], r15w
0x18003eab3  mov     dword ptr [rsp+960h+phkResult], eax
0x18003eab7  lea     r9, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Re"...
0x18003eabe  lea     r8, aRrasroutingdom_40; "RRasRoutingDomainConfig::OpenConfigRegK"...
0x18003eac5  lea     rdx, aSRegopenkeyexS_0; "%s: RegOpenKeyEx (%s) failed: %d."
0x18003eacc  lea     rcx, [rbp+860h+var_840]
0x18003ead0  call    FormatRRASErrorString
0x18003ead5  lea     r9, [rbp+860h+var_8C8]
0x18003ead9  test    rsi, rsi
0x18003eadc  cmovnz  r9, rsi
0x18003eae0  lea     rax, [rbp+860h+var_8B8]
0x18003eae4  mov     qword ptr [rsp+960h+samDesired], rax
0x18003eae9  mov     [rsp+960h+phkResult], r15
0x18003eaee  lea     r8, [rbp+860h+var_840]
0x18003eaf2  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003eaf9  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003eb00  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003eb07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb0c  mov     ecx, [rsp+960h+var_910]
0x18003eb10  jmp     loc_18003EBEC
0x18003eb15  lea     r8, [rbp+860h+SubKey]
0x18003eb19  mov     edx, 28h ; '('
0x18003eb1e  mov     rcx, rsi
0x18003eb21  call    MprConvertGuidToString
0x18003eb26  mov     [rsp+960h+lpdwDisposition], r15; lpdwDisposition
0x18003eb2b  mov     [rsp+960h+var_928], rdi; phkResult
0x18003eb30  mov     [rsp+960h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18003eb35  mov     [rsp+960h+samDesired], ebx; samDesired
0x18003eb39  mov     dword ptr [rsp+960h+phkResult], r15d; dwOptions
0x18003eb3e  xor     r9d, r9d; lpClass
0x18003eb41  xor     r8d, r8d; Reserved
0x18003eb44  lea     rdx, [rbp+860h+SubKey]; lpSubKey
0x18003eb48  mov     rcx, [rsp+960h+hKey]; hKey
0x18003eb4d  call    cs:__imp_RegCreateKeyExW
0x18003eb53  mov     ecx, eax
0x18003eb55  mov     [rsp+960h+var_910], eax
0x18003eb59  test    eax, eax
0x18003eb5b  jnz     short loc_18003EB66
0x18003eb5d  cmp     [rdi], r15
0x18003eb60  jnz     loc_18003EBEC
0x18003eb66  cmp     qword ptr cs:xmmword_1800710A0, r15
0x18003eb6d  jz      short loc_18003EBDF
0x18003eb6f  mov     word ptr [rbp+860h+var_840], r15w
0x18003eb74  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003eb7b  movdqu  [rbp+860h+var_8C8], xmm0
0x18003eb80  mov     word ptr [rbp+860h+var_8B8], r15w
0x18003eb85  mov     dword ptr [rsp+960h+phkResult], eax
0x18003eb89  lea     r9, [rbp+860h+SubKey]
0x18003eb8d  lea     r8, aRrasroutingdom_40; "RRasRoutingDomainConfig::OpenConfigRegK"...
0x18003eb94  lea     rdx, aSRegcreatekeye_3; "%s: RegCreateKeyEx failed for routing d"...
0x18003eb9b  lea     rcx, [rbp+860h+var_840]
0x18003eb9f  call    FormatRRASErrorString
0x18003eba4  lea     r9, [rbp+860h+var_8C8]
0x18003eba8  test    rsi, rsi
0x18003ebab  cmovnz  r9, rsi
0x18003ebaf  lea     rax, [rbp+860h+var_8B8]
0x18003ebb3  mov     qword ptr [rsp+960h+samDesired], rax
0x18003ebb8  mov     [rsp+960h+phkResult], r15
0x18003ebbd  lea     r8, [rbp+860h+var_840]
0x18003ebc1  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003ebc8  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003ebcf  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003ebd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ebdb  mov     ecx, [rsp+960h+var_910]
0x18003ebdf  test    ecx, ecx
0x18003ebe1  jnz     short loc_18003EBEC
0x18003ebe3  mov     ecx, 6
0x18003ebe8  mov     [rsp+960h+var_910], ecx
0x18003ebec  mov     rax, [rsp+960h+hKey]
0x18003ebf1  test    rax, rax
0x18003ebf4  jz      short loc_18003EC03
0x18003ebf6  mov     rcx, rax; hKey
0x18003ebf9  call    cs:__imp_RegCloseKey
0x18003ebff  mov     ecx, [rsp+960h+var_910]
0x18003ec03  test    ecx, ecx
0x18003ec05  jz      short loc_18003EC13
0x18003ec07  mov     rcx, r14; this
0x18003ec0a  call    ?CloseConfigRegKey@RRasRoutingDomainConfig@@AEAAXXZ; RRasRoutingDomainConfig::CloseConfigRegKey(void)
0x18003ec0f  mov     ecx, [rsp+960h+var_910]
0x18003ec13  mov     ebx, ecx
0x18003ec15  lea     rcx, [rsp+960h+var_900]; this
0x18003ec1a  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003ec1f  mov     eax, ebx
0x18003ec21  mov     rcx, [rbp+860h+var_40]
0x18003ec28  xor     rcx, rsp; StackCookie
0x18003ec2b  call    __security_check_cookie
0x18003ec30  add     rsp, 938h
0x18003ec37  pop     r15
0x18003ec39  pop     r14
0x18003ec3b  pop     rdi
0x18003ec3c  pop     rsi
0x18003ec3d  pop     rbx
0x18003ec3e  pop     rbp
0x18003ec3f  retn
```
