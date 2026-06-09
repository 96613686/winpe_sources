# GetCorrelationVectorForDmSession(ushort const *,char *)

- ea: `0x1400123b0`
- end: `0x14001252a`
- name: `?GetCorrelationVectorForDmSession@@YAJPEBGPEAD@Z`
- size: `378`
- prototype: `int(const unsigned __int16 *, char *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000e610`
- `0x140012c58`
- `0x14006572c`

## callees

- `0x140003450`
- `0x1400036e4`
- `0x1400057fc`
- `0x140012068`
- `0x1400121e8`
- `0x1400123b0`
- `0x140013314`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012414`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012414`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140012452`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140012452`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400124dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012517`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400124dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012517`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1400123db`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1400123db`

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
  v7 = operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
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
0x1400123b0  mov     [rsp+arg_0], rbx
0x1400123b5  push    rdi
0x1400123b6  sub     rsp, 0A0h
0x1400123bd  mov     rax, cs:__security_cookie
0x1400123c4  xor     rax, rsp
0x1400123c7  mov     [rsp+0A8h+var_18], rax
0x1400123cf  mov     rdi, rdx
0x1400123d2  mov     [rsp+0A8h+hKey], 0
0x1400123db  call    cs:__imp_RtlIsStateSeparationEnabled
0x1400123e2  nop     dword ptr [rax+rax+00h]
0x1400123e7  neg     al
0x1400123e9  sbb     rdx, rdx
0x1400123ec  and     edx, 8
0x1400123ef  lea     rcx, ?Paths@?1??DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z@4QAY01QEBGA; ushort const * (near * `DMGetKnownRegPath(REFKNOWNREGID)'::`2'::Paths)[2]
0x1400123f6  lea     rax, [rsp+0A8h+hKey]
0x1400123fb  mov     [rsp+0A8h+phkResult], rax; phkResult
0x140012400  mov     r9d, 20019h; samDesired
0x140012406  xor     r8d, r8d; ulOptions
0x140012409  mov     rdx, [rdx+rcx]; lpSubKey
0x14001240d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140012414  call    cs:__imp_RegOpenKeyExW
0x14001241b  nop     dword ptr [rax+rax+00h]
0x140012420  test    eax, eax
0x140012422  jnz     short loc_140012476
0x140012424  mov     [rsp+0A8h+cbData], 4Eh ; 'N'
0x14001242c  lea     rax, [rsp+0A8h+cbData]
0x140012431  mov     [rsp+0A8h+lpcbData], rax; lpcbData
0x140012436  lea     rax, [rsp+0A8h+Data]
0x14001243b  mov     [rsp+0A8h+phkResult], rax; lpData
0x140012440  xor     r9d, r9d; lpType
0x140012443  xor     r8d, r8d; lpReserved
0x140012446  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x14001244d  mov     rcx, [rsp+0A8h+hKey]; hKey
0x140012452  call    cs:__imp_RegQueryValueExW
0x140012459  nop     dword ptr [rax+rax+00h]
0x14001245e  test    eax, eax
0x140012460  jnz     short loc_140012476
0x140012462  mov     r9, [rsp+0A8h+hKey]; HKEY
0x140012467  mov     r8, rdi; char *
0x14001246a  lea     rdx, [rsp+0A8h+Data]; unsigned __int16 *
0x14001246f  call    ?GetComponentCVForEnrollmentId@@YAJPEBG0PEADPEAUHKEY__@@@Z; GetComponentCVForEnrollmentId(ushort const *,ushort const *,char *,HKEY__ *)
0x140012474  jmp     short loc_140012480
0x140012476  jle     short loc_140012480
0x140012478  movzx   eax, ax
0x14001247b  or      eax, 80070000h
0x140012480  test    eax, eax
0x140012482  jns     short loc_1400124D3
0x140012484  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001248b  mov     ecx, 90h; unsigned __int64
0x140012490  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140012495  mov     qword ptr [rsp+0A8h+cbData], rax
0x14001249a  test    rax, rax
0x14001249d  jz      short loc_14001250D
0x14001249f  mov     rcx, rax
0x1400124a2  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x1400124a7  mov     rbx, rax
0x1400124aa  test    rax, rax
0x1400124ad  jz      short loc_14001250D
0x1400124af  xor     edx, edx
0x1400124b1  lock xadd [rax+88h], rdx; unsigned __int64
0x1400124ba  mov     r8, rdi; char *
0x1400124bd  mov     rcx, rax; this
0x1400124c0  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1400124c5  mov     edx, 90h
0x1400124ca  mov     rcx, rbx; Block
0x1400124cd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400124d2  nop
0x1400124d3  mov     rcx, [rsp+0A8h+hKey]; hKey
0x1400124d8  test    rcx, rcx
0x1400124db  jz      short loc_1400124E9
0x1400124dd  call    cs:__imp_RegCloseKey
0x1400124e4  nop     dword ptr [rax+rax+00h]
0x1400124e9  xor     eax, eax
0x1400124eb  mov     rcx, [rsp+0A8h+var_18]
0x1400124f3  xor     rcx, rsp; StackCookie
0x1400124f6  call    __security_check_cookie
0x1400124fb  mov     rbx, [rsp+0A8h+arg_0]
0x140012503  add     rsp, 0A0h
0x14001250a  pop     rdi
0x14001250b  retn
0x14001250d  mov     rcx, [rsp+0A8h+hKey]; hKey
0x140012512  test    rcx, rcx
0x140012515  jz      short loc_140012523
0x140012517  call    cs:__imp_RegCloseKey
0x14001251e  nop     dword ptr [rax+rax+00h]
0x140012523  mov     eax, 8007000Eh
0x140012528  jmp     short loc_1400124EB
```
