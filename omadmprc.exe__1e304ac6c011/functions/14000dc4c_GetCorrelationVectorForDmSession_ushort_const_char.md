# GetCorrelationVectorForDmSession(ushort const *,char *)

- ea: `0x14000dc4c`
- end: `0x14000ddce`
- name: `?GetCorrelationVectorForDmSession@@YAJPEBGPEAD@Z`
- size: `386`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, char *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000b708`
- `0x14000e4f0`

## callees

- `0x140002aa0`
- `0x14000d908`
- `0x14000da8c`
- `0x14000dc4c`
- `0x14000ebb8`
- `0x140015690`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000dd6a`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000dd6a`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14000dc7a`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14000dc7a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000dcf1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000dcf1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000dcb3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000dcb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000dd81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ddbb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000dd81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ddbb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetCorrelationVectorForDmSession(LPCWSTR lpValueName, char *a2)
{
  char IsStateSeparationEnabled; // al
  int ComponentCVForEnrollmentId; // eax
  bool v6; // cc
  void *v7; // rax
  volatile signed __int64 *v8; // rax
  volatile signed __int64 *v9; // rbx
  HKEY hKey; // [rsp+30h] [rbp-78h] BYREF
  DWORD cbData[2]; // [rsp+38h] [rbp-70h] BYREF
  unsigned __int16 Data[40]; // [rsp+40h] [rbp-68h] BYREF

  hKey = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(lpValueName);
  ComponentCVForEnrollmentId = RegOpenKeyExW(
                                 HKEY_LOCAL_MACHINE,
                                 *(wchar_t **)((char *)`DMGetKnownRegPath'::`2'::Paths
                                             + (IsStateSeparationEnabled != 0 ? 8 : 0)),
                                 0,
                                 0x20019u,
                                 &hKey);
  v6 = ComponentCVForEnrollmentId <= 0;
  if ( ComponentCVForEnrollmentId
    || (cbData[0] = 78,
        ComponentCVForEnrollmentId = RegQueryValueExW(hKey, L"CurrentEnrollmentId", 0, 0, (LPBYTE)Data, cbData),
        v6 = ComponentCVForEnrollmentId <= 0,
        ComponentCVForEnrollmentId) )
  {
    if ( !v6 )
      ComponentCVForEnrollmentId = (unsigned __int16)ComponentCVForEnrollmentId | 0x80070000;
  }
  else
  {
    ComponentCVForEnrollmentId = GetComponentCVForEnrollmentId(lpValueName, Data, a2, hKey);
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
0x14000dc4c  mov     [rsp+arg_10], rbx
0x14000dc51  push    rdi
0x14000dc52  sub     rsp, 0A0h
0x14000dc59  mov     rax, cs:__security_cookie
0x14000dc60  xor     rax, rsp
0x14000dc63  mov     [rsp+0A8h+var_18], rax
0x14000dc6b  mov     rdi, rdx
0x14000dc6e  mov     rbx, rcx
0x14000dc71  mov     [rsp+0A8h+hKey], 0
0x14000dc7a  call    cs:__imp_RtlIsStateSeparationEnabled
0x14000dc81  nop     dword ptr [rax+rax+00h]
0x14000dc86  neg     al
0x14000dc88  sbb     rdx, rdx
0x14000dc8b  and     edx, 8
0x14000dc8e  lea     rcx, ?Paths@?1??DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z@4QAY01QEBGA; ushort const * (near * `DMGetKnownRegPath(REFKNOWNREGID)'::`2'::Paths)[2]
0x14000dc95  lea     rax, [rsp+0A8h+hKey]
0x14000dc9a  mov     [rsp+0A8h+phkResult], rax; phkResult
0x14000dc9f  mov     r9d, 20019h; samDesired
0x14000dca5  xor     r8d, r8d; ulOptions
0x14000dca8  mov     rdx, [rdx+rcx]; lpSubKey
0x14000dcac  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000dcb3  call    cs:__imp_RegOpenKeyExW
0x14000dcba  nop     dword ptr [rax+rax+00h]
0x14000dcbf  test    eax, eax
0x14000dcc1  jnz     short loc_14000DD18
0x14000dcc3  mov     [rsp+0A8h+cbData], 4Eh ; 'N'
0x14000dccb  lea     rax, [rsp+0A8h+cbData]
0x14000dcd0  mov     [rsp+0A8h+lpcbData], rax; lpcbData
0x14000dcd5  lea     rax, [rsp+0A8h+Data]
0x14000dcda  mov     [rsp+0A8h+phkResult], rax; lpData
0x14000dcdf  xor     r9d, r9d; lpType
0x14000dce2  xor     r8d, r8d; lpReserved
0x14000dce5  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x14000dcec  mov     rcx, [rsp+0A8h+hKey]; hKey
0x14000dcf1  call    cs:__imp_RegQueryValueExW
0x14000dcf8  nop     dword ptr [rax+rax+00h]
0x14000dcfd  test    eax, eax
0x14000dcff  jnz     short loc_14000DD18
0x14000dd01  mov     r9, [rsp+0A8h+hKey]; HKEY
0x14000dd06  mov     r8, rdi; char *
0x14000dd09  lea     rdx, [rsp+0A8h+Data]; unsigned __int16 *
0x14000dd0e  mov     rcx, rbx; lpValueName
0x14000dd11  call    ?GetComponentCVForEnrollmentId@@YAJPEBG0PEADPEAUHKEY__@@@Z; GetComponentCVForEnrollmentId(ushort const *,ushort const *,char *,HKEY__ *)
0x14000dd16  jmp     short loc_14000DD22
0x14000dd18  jle     short loc_14000DD22
0x14000dd1a  movzx   eax, ax
0x14000dd1d  or      eax, 80070000h
0x14000dd22  test    eax, eax
0x14000dd24  jns     short loc_14000DD77
0x14000dd26  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000dd2d  mov     ecx, 90h; unsigned __int64
0x14000dd32  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000dd37  mov     qword ptr [rsp+0A8h+cbData], rax
0x14000dd3c  test    rax, rax
0x14000dd3f  jz      short loc_14000DDB1
0x14000dd41  mov     rcx, rax
0x14000dd44  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x14000dd49  mov     rbx, rax
0x14000dd4c  test    rax, rax
0x14000dd4f  jz      short loc_14000DDB1
0x14000dd51  xor     edx, edx
0x14000dd53  lock xadd [rax+88h], rdx; unsigned __int64
0x14000dd5c  mov     r8, rdi; char *
0x14000dd5f  mov     rcx, rax; this
0x14000dd62  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x14000dd67  mov     rcx, rbx
0x14000dd6a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000dd71  nop     dword ptr [rax+rax+00h]
0x14000dd76  nop
0x14000dd77  mov     rcx, [rsp+0A8h+hKey]; hKey
0x14000dd7c  test    rcx, rcx
0x14000dd7f  jz      short loc_14000DD8D
0x14000dd81  call    cs:__imp_RegCloseKey
0x14000dd88  nop     dword ptr [rax+rax+00h]
0x14000dd8d  xor     eax, eax
0x14000dd8f  mov     rcx, [rsp+0A8h+var_18]
0x14000dd97  xor     rcx, rsp; StackCookie
0x14000dd9a  call    __security_check_cookie
0x14000dd9f  mov     rbx, [rsp+0A8h+arg_10]
0x14000dda7  add     rsp, 0A0h
0x14000ddae  pop     rdi
0x14000ddaf  retn
0x14000ddb1  mov     rcx, [rsp+0A8h+hKey]; hKey
0x14000ddb6  test    rcx, rcx
0x14000ddb9  jz      short loc_14000DDC7
0x14000ddbb  call    cs:__imp_RegCloseKey
0x14000ddc2  nop     dword ptr [rax+rax+00h]
0x14000ddc7  mov     eax, 8007000Eh
0x14000ddcc  jmp     short loc_14000DD8F
```
