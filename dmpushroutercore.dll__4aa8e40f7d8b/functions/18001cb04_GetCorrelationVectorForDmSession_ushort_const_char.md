# GetCorrelationVectorForDmSession(ushort const *,char *)

- ea: `0x18001cb04`
- end: `0x18001cc5f`
- name: `?GetCorrelationVectorForDmSession@@YAJPEBGPEAD@Z`
- size: `347`
- prototype: `int(const unsigned __int16 *, char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001bc10`

## callees

- `0x1800039f0`
- `0x180003a14`
- `0x180006090`
- `0x18001c244`
- `0x18001c7a0`
- `0x18001c96c`
- `0x18001cb04`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cc1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cc52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cc1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cc52`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001cb9a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001cb9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cb62`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cb62`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001cb2f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001cb2f`

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
                                 *(LPCWSTR *)((char *)&`DMGetKnownRegPath'::`2'::Paths
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
      operator delete((void *)v9, (const struct std::nothrow_t *)0x90);
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
0x18001cb04  mov     [rsp+arg_0], rbx
0x18001cb09  push    rdi
0x18001cb0a  sub     rsp, 0A0h
0x18001cb11  mov     rax, cs:__security_cookie
0x18001cb18  xor     rax, rsp
0x18001cb1b  mov     [rsp+0A8h+var_18], rax
0x18001cb23  mov     rdi, rdx
0x18001cb26  mov     [rsp+0A8h+hKey], 0
0x18001cb2f  call    cs:__imp_RtlIsStateSeparationEnabled
0x18001cb35  neg     al
0x18001cb37  sbb     rdx, rdx
0x18001cb3a  and     edx, 8
0x18001cb3d  lea     rcx, ?Paths@?1??DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z@4QAY01QEBGA; ushort const * (near * `DMGetKnownRegPath(REFKNOWNREGID)'::`2'::Paths)[2]
0x18001cb44  lea     rax, [rsp+0A8h+hKey]
0x18001cb49  mov     [rsp+0A8h+phkResult], rax; phkResult
0x18001cb4e  mov     r9d, 20019h; samDesired
0x18001cb54  xor     r8d, r8d; ulOptions
0x18001cb57  mov     rdx, [rdx+rcx]; lpSubKey
0x18001cb5b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001cb62  call    cs:__imp_RegOpenKeyExW
0x18001cb68  test    eax, eax
0x18001cb6a  jnz     short loc_18001CBB8
0x18001cb6c  mov     [rsp+0A8h+cbData], 4Eh ; 'N'
0x18001cb74  lea     rax, [rsp+0A8h+cbData]
0x18001cb79  mov     [rsp+0A8h+lpcbData], rax; lpcbData
0x18001cb7e  lea     rax, [rsp+0A8h+Data]
0x18001cb83  mov     [rsp+0A8h+phkResult], rax; lpData
0x18001cb88  xor     r9d, r9d; lpType
0x18001cb8b  xor     r8d, r8d; lpReserved
0x18001cb8e  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x18001cb95  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18001cb9a  call    cs:__imp_RegQueryValueExW
0x18001cba0  test    eax, eax
0x18001cba2  jnz     short loc_18001CBB8
0x18001cba4  mov     r9, [rsp+0A8h+hKey]; HKEY
0x18001cba9  mov     r8, rdi; char *
0x18001cbac  lea     rdx, [rsp+0A8h+Data]; unsigned __int16 *
0x18001cbb1  call    ?GetComponentCVForEnrollmentId@@YAJPEBG0PEADPEAUHKEY__@@@Z; GetComponentCVForEnrollmentId(ushort const *,ushort const *,char *,HKEY__ *)
0x18001cbb6  jmp     short loc_18001CBC2
0x18001cbb8  jle     short loc_18001CBC2
0x18001cbba  movzx   eax, ax
0x18001cbbd  or      eax, 80070000h
0x18001cbc2  test    eax, eax
0x18001cbc4  jns     short loc_18001CC15
0x18001cbc6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001cbcd  mov     ecx, 90h; unsigned __int64
0x18001cbd2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001cbd7  mov     qword ptr [rsp+0A8h+cbData], rax
0x18001cbdc  test    rax, rax
0x18001cbdf  jz      short loc_18001CC48
0x18001cbe1  mov     rcx, rax
0x18001cbe4  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18001cbe9  mov     rbx, rax
0x18001cbec  test    rax, rax
0x18001cbef  jz      short loc_18001CC48
0x18001cbf1  xor     edx, edx
0x18001cbf3  lock xadd [rax+88h], rdx; unsigned __int64
0x18001cbfc  mov     r8, rdi; char *
0x18001cbff  mov     rcx, rax; this
0x18001cc02  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18001cc07  mov     edx, 90h; struct std::nothrow_t *
0x18001cc0c  mov     rcx, rbx; void *
0x18001cc0f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001cc14  nop
0x18001cc15  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18001cc1a  test    rcx, rcx
0x18001cc1d  jz      short loc_18001CC25
0x18001cc1f  call    cs:__imp_RegCloseKey
0x18001cc25  xor     eax, eax
0x18001cc27  mov     rcx, [rsp+0A8h+var_18]
0x18001cc2f  xor     rcx, rsp; StackCookie
0x18001cc32  call    __security_check_cookie
0x18001cc37  mov     rbx, [rsp+0A8h+arg_0]
0x18001cc3f  add     rsp, 0A0h
0x18001cc46  pop     rdi
0x18001cc47  retn
0x18001cc48  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18001cc4d  test    rcx, rcx
0x18001cc50  jz      short loc_18001CC58
0x18001cc52  call    cs:__imp_RegCloseKey
0x18001cc58  mov     eax, 8007000Eh
0x18001cc5d  jmp     short loc_18001CC27
```
