# GetCorrelationVectorForDmSession(ushort const *,char *)

- ea: `0x18000ed9c`
- end: `0x18000eef7`
- name: `?GetCorrelationVectorForDmSession@@YAJPEBGPEAD@Z`
- size: `347`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000e83c`

## callees

- `0x180001cf0`
- `0x180001d14`
- `0x180002a5c`
- `0x18000ead8`
- `0x18000ec04`
- `0x18000ed9c`
- `0x18000ef24`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18000edc7`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000edc7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000eeb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000eeea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000eeb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000eeea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000edfa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000edfa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ee32`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ee32`

## pseudocode

```c
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
  v7 = operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
  *(_QWORD *)cbData = v7;
  if ( v7 )
  {
    v8 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((__int64)v7);
    v9 = v8;
    if ( v8 )
    {
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v8,
        _InterlockedExchangeAdd64(v8 + 17, 0),
        a2);
      operator delete((void *)v9);
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
0x18000ed9c  mov     [rsp+arg_0], rbx
0x18000eda1  push    rdi
0x18000eda2  sub     rsp, 0A0h
0x18000eda9  mov     rax, cs:__security_cookie
0x18000edb0  xor     rax, rsp
0x18000edb3  mov     [rsp+0A8h+var_18], rax
0x18000edbb  mov     rdi, rdx
0x18000edbe  mov     [rsp+0A8h+hKey], 0
0x18000edc7  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000edcd  neg     al
0x18000edcf  sbb     rdx, rdx
0x18000edd2  and     edx, 8
0x18000edd5  lea     rcx, ?Paths@?1??DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z@4QAY01QEBGA; ushort const * (near * `DMGetKnownRegPath(REFKNOWNREGID)'::`2'::Paths)[2]
0x18000eddc  lea     rax, [rsp+0A8h+hKey]
0x18000ede1  mov     [rsp+0A8h+phkResult], rax; phkResult
0x18000ede6  mov     r9d, 20019h; samDesired
0x18000edec  xor     r8d, r8d; ulOptions
0x18000edef  mov     rdx, [rdx+rcx]; lpSubKey
0x18000edf3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000edfa  call    cs:__imp_RegOpenKeyExW
0x18000ee00  test    eax, eax
0x18000ee02  jnz     short loc_18000EE50
0x18000ee04  mov     [rsp+0A8h+cbData], 4Eh ; 'N'
0x18000ee0c  lea     rax, [rsp+0A8h+cbData]
0x18000ee11  mov     [rsp+0A8h+lpcbData], rax; lpcbData
0x18000ee16  lea     rax, [rsp+0A8h+Data]
0x18000ee1b  mov     [rsp+0A8h+phkResult], rax; lpData
0x18000ee20  xor     r9d, r9d; lpType
0x18000ee23  xor     r8d, r8d; lpReserved
0x18000ee26  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x18000ee2d  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18000ee32  call    cs:__imp_RegQueryValueExW
0x18000ee38  test    eax, eax
0x18000ee3a  jnz     short loc_18000EE50
0x18000ee3c  mov     r9, [rsp+0A8h+hKey]; HKEY
0x18000ee41  mov     r8, rdi; char *
0x18000ee44  lea     rdx, [rsp+0A8h+Data]; unsigned __int16 *
0x18000ee49  call    ?GetComponentCVForEnrollmentId@@YAJPEBG0PEADPEAUHKEY__@@@Z; GetComponentCVForEnrollmentId(ushort const *,ushort const *,char *,HKEY__ *)
0x18000ee4e  jmp     short loc_18000EE5A
0x18000ee50  jle     short loc_18000EE5A
0x18000ee52  movzx   eax, ax
0x18000ee55  or      eax, 80070000h
0x18000ee5a  test    eax, eax
0x18000ee5c  jns     short loc_18000EEAD
0x18000ee5e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ee65  mov     ecx, 90h; unsigned __int64
0x18000ee6a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ee6f  mov     qword ptr [rsp+0A8h+cbData], rax
0x18000ee74  test    rax, rax
0x18000ee77  jz      short loc_18000EEE0
0x18000ee79  mov     rcx, rax
0x18000ee7c  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18000ee81  mov     rbx, rax
0x18000ee84  test    rax, rax
0x18000ee87  jz      short loc_18000EEE0
0x18000ee89  xor     edx, edx
0x18000ee8b  lock xadd [rax+88h], rdx; unsigned __int64
0x18000ee94  mov     r8, rdi; char *
0x18000ee97  mov     rcx, rax; this
0x18000ee9a  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18000ee9f  mov     edx, 90h
0x18000eea4  mov     rcx, rbx; Block
0x18000eea7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000eeac  nop
0x18000eead  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18000eeb2  test    rcx, rcx
0x18000eeb5  jz      short loc_18000EEBD
0x18000eeb7  call    cs:__imp_RegCloseKey
0x18000eebd  xor     eax, eax
0x18000eebf  mov     rcx, [rsp+0A8h+var_18]
0x18000eec7  xor     rcx, rsp; StackCookie
0x18000eeca  call    __security_check_cookie
0x18000eecf  mov     rbx, [rsp+0A8h+arg_0]
0x18000eed7  add     rsp, 0A0h
0x18000eede  pop     rdi
0x18000eedf  retn
0x18000eee0  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18000eee5  test    rcx, rcx
0x18000eee8  jz      short loc_18000EEF0
0x18000eeea  call    cs:__imp_RegCloseKey
0x18000eef0  mov     eax, 8007000Eh
0x18000eef5  jmp     short loc_18000EEBF
```
