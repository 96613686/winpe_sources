# GetCorrelationVectorForDmSession(ushort const *,char *)

- ea: `0x180020c74`
- end: `0x180020dee`
- name: `?GetCorrelationVectorForDmSession@@YAJPEBGPEAD@Z`
- size: `378`
- prototype: `int(const unsigned __int16 *, char *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180020ef8`
- `0x180021688`
- `0x180021ec4`

## callees

- `0x1800031b0`
- `0x1800031d4`
- `0x180004a8c`
- `0x180020950`
- `0x180020aac`
- `0x180020c74`
- `0x180021598`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020d16`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020d16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020da1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020ddb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020da1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020ddb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020cd8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020cd8`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180020c9f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180020c9f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetCorrelationVectorForDmSession(const unsigned __int16 *a1, char *a2)
{
  char IsStateSeparationEnabled; // al
  int ComponentCVForEnrollmentId; // eax
  bool v5; // cc
  const unsigned __int16 *v6; // rcx
  void *v7; // rax
  volatile signed __int64 *v8; // rax
  volatile signed __int64 *v9; // rbx
  HKEY hKey; // [rsp+30h] [rbp-78h] BYREF
  DWORD cbData[2]; // [rsp+38h] [rbp-70h] BYREF
  unsigned __int16 Data[40]; // [rsp+40h] [rbp-68h] BYREF

  hKey = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1);
  ComponentCVForEnrollmentId = RegOpenKeyExW(
                                 HKEY_LOCAL_MACHINE,
                                 *(wchar_t **)((char *)`DMGetKnownRegPath'::`2'::Paths
                                             + (IsStateSeparationEnabled != 0 ? 8 : 0)),
                                 0,
                                 0x20019u,
                                 &hKey);
  v5 = ComponentCVForEnrollmentId <= 0;
  if ( ComponentCVForEnrollmentId
    || (cbData[0] = 78,
        ComponentCVForEnrollmentId = RegQueryValueExW(hKey, L"CurrentEnrollmentId", 0, 0, (LPBYTE)Data, cbData),
        v5 = ComponentCVForEnrollmentId <= 0,
        ComponentCVForEnrollmentId) )
  {
    if ( !v5 )
      ComponentCVForEnrollmentId = (unsigned __int16)ComponentCVForEnrollmentId | 0x80070000;
  }
  else
  {
    ComponentCVForEnrollmentId = GetComponentCVForEnrollmentId(v6, Data, a2, hKey);
  }
  if ( ComponentCVForEnrollmentId >= 0 )
    goto LABEL_10;
  v7 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)cbData = v7;
  if ( v7 )
  {
    v8 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v7);
    v9 = v8;
    if ( v8 )
    {
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v8,
        _InterlockedExchangeAdd64(v8 + 17, 0),
        a2);
      operator delete((void *)v9, 0x90u);
LABEL_10:
      if ( hKey )
        RegCloseKey(hKey);
      return 0;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180020c74  mov     [rsp+arg_0], rbx
0x180020c79  push    rdi
0x180020c7a  sub     rsp, 0A0h
0x180020c81  mov     rax, cs:__security_cookie
0x180020c88  xor     rax, rsp
0x180020c8b  mov     [rsp+0A8h+var_18], rax
0x180020c93  mov     rdi, rdx
0x180020c96  mov     [rsp+0A8h+hKey], 0
0x180020c9f  call    cs:__imp_RtlIsStateSeparationEnabled
0x180020ca6  nop     dword ptr [rax+rax+00h]
0x180020cab  neg     al
0x180020cad  sbb     rdx, rdx
0x180020cb0  and     edx, 8
0x180020cb3  lea     rcx, ?Paths@?1??DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z@4QAY01QEBGA; ushort const * (near * `DMGetKnownRegPath(REFKNOWNREGID)'::`2'::Paths)[2]
0x180020cba  lea     rax, [rsp+0A8h+hKey]
0x180020cbf  mov     [rsp+0A8h+phkResult], rax; phkResult
0x180020cc4  mov     r9d, 20019h; samDesired
0x180020cca  xor     r8d, r8d; ulOptions
0x180020ccd  mov     rdx, [rdx+rcx]; lpSubKey
0x180020cd1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180020cd8  call    cs:__imp_RegOpenKeyExW
0x180020cdf  nop     dword ptr [rax+rax+00h]
0x180020ce4  test    eax, eax
0x180020ce6  jnz     short loc_180020D3A
0x180020ce8  mov     [rsp+0A8h+cbData], 4Eh ; 'N'
0x180020cf0  lea     rax, [rsp+0A8h+cbData]
0x180020cf5  mov     [rsp+0A8h+lpcbData], rax; lpcbData
0x180020cfa  lea     rax, [rsp+0A8h+Data]
0x180020cff  mov     [rsp+0A8h+phkResult], rax; lpData
0x180020d04  xor     r9d, r9d; lpType
0x180020d07  xor     r8d, r8d; lpReserved
0x180020d0a  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x180020d11  mov     rcx, [rsp+0A8h+hKey]; hKey
0x180020d16  call    cs:__imp_RegQueryValueExW
0x180020d1d  nop     dword ptr [rax+rax+00h]
0x180020d22  test    eax, eax
0x180020d24  jnz     short loc_180020D3A
0x180020d26  mov     r9, [rsp+0A8h+hKey]; HKEY
0x180020d2b  mov     r8, rdi; char *
0x180020d2e  lea     rdx, [rsp+0A8h+Data]; unsigned __int16 *
0x180020d33  call    ?GetComponentCVForEnrollmentId@@YAJPEBG0PEADPEAUHKEY__@@@Z; GetComponentCVForEnrollmentId(ushort const *,ushort const *,char *,HKEY__ *)
0x180020d38  jmp     short loc_180020D44
0x180020d3a  jle     short loc_180020D44
0x180020d3c  movzx   eax, ax
0x180020d3f  or      eax, 80070000h
0x180020d44  test    eax, eax
0x180020d46  jns     short loc_180020D97
0x180020d48  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020d4f  mov     ecx, 90h; unsigned __int64
0x180020d54  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180020d59  mov     qword ptr [rsp+0A8h+cbData], rax
0x180020d5e  test    rax, rax
0x180020d61  jz      short loc_180020DD1
0x180020d63  mov     rcx, rax
0x180020d66  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x180020d6b  mov     rbx, rax
0x180020d6e  test    rax, rax
0x180020d71  jz      short loc_180020DD1
0x180020d73  xor     edx, edx
0x180020d75  lock xadd [rax+88h], rdx; unsigned __int64
0x180020d7e  mov     r8, rdi; char *
0x180020d81  mov     rcx, rax; this
0x180020d84  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180020d89  mov     edx, 90h; unsigned __int64
0x180020d8e  mov     rcx, rbx; void *
0x180020d91  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020d96  nop
0x180020d97  mov     rcx, [rsp+0A8h+hKey]; hKey
0x180020d9c  test    rcx, rcx
0x180020d9f  jz      short loc_180020DAD
0x180020da1  call    cs:__imp_RegCloseKey
0x180020da8  nop     dword ptr [rax+rax+00h]
0x180020dad  xor     eax, eax
0x180020daf  mov     rcx, [rsp+0A8h+var_18]
0x180020db7  xor     rcx, rsp; StackCookie
0x180020dba  call    __security_check_cookie
0x180020dbf  mov     rbx, [rsp+0A8h+arg_0]
0x180020dc7  add     rsp, 0A0h
0x180020dce  pop     rdi
0x180020dcf  retn
0x180020dd1  mov     rcx, [rsp+0A8h+hKey]; hKey
0x180020dd6  test    rcx, rcx
0x180020dd9  jz      short loc_180020DE7
0x180020ddb  call    cs:__imp_RegCloseKey
0x180020de2  nop     dword ptr [rax+rax+00h]
0x180020de7  mov     eax, 8007000Eh
0x180020dec  jmp     short loc_180020DAF
```
