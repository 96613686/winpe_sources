# CPolicyCriticalSectionCollection::InitializeLockSecurityDescriptor(void)

- ea: `0x1800113f0`
- end: `0x18001166e`
- name: `?InitializeLockSecurityDescriptor@CPolicyCriticalSectionCollection@@AEAAKXZ`
- size: `638`
- prototype: `unsigned int __fastcall(CPolicyCriticalSectionCollection *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800112dc`

## callees

- `0x1800113f0`
- `0x18001d0c0`
- `0x18001d220`
- `0x18001d380`
- `0x180049bf0`
- `0x18004e164`
- `0x180072a08`
- `0x18007d320`
- `0x1800b5e10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800114a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800114a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011637`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011628`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011628`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001149e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180011587`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001149e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180011587`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180011524`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001160d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180011524`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001160d`

## string_xrefs

- `0x18001159a`: `AddNetworkService: Failed to initialize sid.  Error = %d`
- `0x1800115ef`: `AddNetworkService: Not initialised or failure.`
- `0x1800114b1`: `AddLocalSystem: Failed to initialize sid.  Error = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPolicyCriticalSectionCollection::InitializeLockSecurityDescriptor(
        CPolicyCriticalSectionCollection *this)
{
  DWORD v2; // edi
  DWORD LastError; // eax
  PSID v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rax
  DWORD v7; // eax
  PSID v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rax
  struct _SECURITY_DESCRIPTOR *SD; // rbx
  void *v12; // rcx
  PSID pSid; // [rsp+60h] [rbp+7h] BYREF
  __int64 v15; // [rsp+68h] [rbp+Fh] BYREF
  unsigned int v16; // [rsp+70h] [rbp+17h]
  int v17; // [rsp+74h] [rbp+1Bh]
  int v18; // [rsp+78h] [rbp+1Fh]
  int v19; // [rsp+7Ch] [rbp+23h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp+37h] BYREF

  v2 = 0;
  CSecDesc::CSecDesc((CSecDesc *)&v15);
  CSecDesc::AddAdministratorsAsOwner((CSecDesc *)&v15);
  CSecDesc::AddAdministratorsAsGroup((CSecDesc *)&v15);
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid = 0;
  if ( !v18 || v19 )
  {
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddLocalSystem: Not initialised or failure.");
  }
  else
  {
    v19 = 1;
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
    {
      if ( v16 != v17 || (unsigned int)CSecDesc::ReAllocSidList((CSecDesc *)&v15) )
      {
        v4 = pSid;
        pSid = 0;
        v5 = 3LL * v16;
        v6 = v15;
        *(_QWORD *)(v15 + 8 * v5) = v4;
        *(_DWORD *)(v6 + 8 * v5 + 8) = 2;
        *(_DWORD *)(v6 + 8 * v5 + 16) = 0;
        ++v16;
        v19 = 0;
      }
    }
    else
    {
      LastError = GetLastError();
      CDebugWrapper::Msg(
        (CDebugWrapper *)dbgCommon,
        2u,
        L"AddLocalSystem: Failed to initialize sid.  Error = %d",
        LastError);
    }
  }
  if ( pSid )
    FreeSid(pSid);
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid = 0;
  if ( !v18 || v19 )
  {
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddNetworkService: Not initialised or failure.");
  }
  else
  {
    v19 = 1;
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
    {
      if ( v16 != v17 || (unsigned int)CSecDesc::ReAllocSidList((CSecDesc *)&v15) )
      {
        v8 = pSid;
        pSid = 0;
        v9 = 3LL * v16;
        v10 = v15;
        *(_QWORD *)(v15 + 8 * v9) = v8;
        *(_DWORD *)(v10 + 8 * v9 + 8) = 2;
        *(_DWORD *)(v10 + 8 * v9 + 16) = 0;
        ++v16;
        v19 = 0;
      }
    }
    else
    {
      v7 = GetLastError();
      CDebugWrapper::Msg(
        (CDebugWrapper *)dbgCommon,
        2u,
        L"AddNetworkService: Failed to initialize sid.  Error = %d",
        v7);
    }
  }
  if ( pSid )
    FreeSid(pSid);
  SD = CSecDesc::MakeSD((CSecDesc *)&v15);
  v12 = (void *)*((_QWORD *)this + 8);
  if ( v12 )
    LocalFree(v12);
  *((_QWORD *)this + 8) = SD;
  if ( !SD )
    v2 = GetLastError();
  CSecDesc::~CSecDesc((CSecDesc *)&v15);
  return v2;
}

```

## disassembly

```asm
0x1800113f0  mov     [rsp-8+arg_8], rbx
0x1800113f5  mov     [rsp-8+arg_10], rsi
0x1800113fa  push    rbp
0x1800113fb  push    rdi
0x1800113fc  push    r14
0x1800113fe  lea     rbp, [rsp-47h]
0x180011403  sub     rsp, 0A0h
0x18001140a  mov     rax, cs:__security_cookie
0x180011411  xor     rax, rsp
0x180011414  mov     [rbp+57h+var_18], rax
0x180011418  mov     rsi, rcx
0x18001141b  xor     r14d, r14d
0x18001141e  mov     edi, r14d
0x180011421  lea     rcx, [rbp+57h+var_48]; this
0x180011425  call    ??0CSecDesc@@QEAA@XZ; CSecDesc::CSecDesc(void)
0x18001142a  nop
0x18001142b  lea     rcx, [rbp+57h+var_48]; this
0x18001142f  call    ?AddAdministratorsAsOwner@CSecDesc@@QEAAHXZ; CSecDesc::AddAdministratorsAsOwner(void)
0x180011434  lea     rcx, [rbp+57h+var_48]; this
0x180011438  call    ?AddAdministratorsAsGroup@CSecDesc@@QEAAHXZ; CSecDesc::AddAdministratorsAsGroup(void)
0x18001143d  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x180011441  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180011447  mov     [rbp+57h+var_50], r14
0x18001144b  lea     ebx, [r14+2]
0x18001144f  cmp     [rbp+57h+var_38], r14d
0x180011453  jz      loc_180011506
0x180011459  cmp     [rbp+57h+var_34], r14d
0x18001145d  jnz     loc_180011506
0x180011463  mov     [rbp+57h+var_34], 1
0x18001146a  lea     rax, [rbp+57h+var_50]
0x18001146e  mov     [rsp+0B0h+pSid], rax; pSid
0x180011473  mov     [rsp+0B0h+nSubAuthority7], r14d; nSubAuthority7
0x180011478  mov     [rsp+0B0h+nSubAuthority6], r14d; nSubAuthority6
0x18001147d  mov     [rsp+0B0h+nSubAuthority5], r14d; nSubAuthority5
0x180011482  mov     [rsp+0B0h+nSubAuthority4], r14d; nSubAuthority4
0x180011487  mov     [rsp+0B0h+nSubAuthority3], r14d; nSubAuthority3
0x18001148c  mov     [rsp+0B0h+nSubAuthority2], r14d; nSubAuthority2
0x180011491  xor     r9d, r9d; nSubAuthority1
0x180011494  lea     r8d, [r14+12h]; nSubAuthority0
0x180011498  mov     dl, 1; nSubAuthorityCount
0x18001149a  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18001149e  call    cs:__imp_AllocateAndInitializeSid
0x1800114a4  test    eax, eax
0x1800114a6  jnz     short loc_1800114C8
0x1800114a8  call    cs:__imp_GetLastError
0x1800114ae  mov     r9d, eax
0x1800114b1  lea     r8, aAddlocalsystem_0; "AddLocalSystem: Failed to initialize si"...
0x1800114b8  mov     edx, ebx; unsigned int
0x1800114ba  lea     rcx, ?dbgCommon@@3VCDebugWrapper@@A; this
0x1800114c1  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800114c6  jmp     short loc_18001151B
0x1800114c8  mov     eax, [rbp+57h+var_3C]
0x1800114cb  cmp     [rbp+57h+var_40], eax
0x1800114ce  jnz     short loc_1800114DD
0x1800114d0  lea     rcx, [rbp+57h+var_48]; this
0x1800114d4  call    ?ReAllocSidList@CSecDesc@@AEAAHXZ; CSecDesc::ReAllocSidList(void)
0x1800114d9  test    eax, eax
0x1800114db  jz      short loc_18001151B
0x1800114dd  mov     rdx, [rbp+57h+var_50]
0x1800114e1  mov     [rbp+57h+var_50], r14
0x1800114e5  mov     eax, [rbp+57h+var_40]
0x1800114e8  lea     rcx, [rax+rax*2]
0x1800114ec  mov     rax, [rbp+57h+var_48]
0x1800114f0  mov     [rax+rcx*8], rdx
0x1800114f4  mov     [rax+rcx*8+8], ebx
0x1800114f8  mov     [rax+rcx*8+10h], r14d
0x1800114fd  inc     [rbp+57h+var_40]
0x180011500  mov     [rbp+57h+var_34], r14d
0x180011504  jmp     short loc_18001151B
0x180011506  lea     r8, aAddlocalsystem; "AddLocalSystem: Not initialised or fail"...
0x18001150d  mov     edx, ebx; unsigned int
0x18001150f  lea     rcx, ?dbgCommon@@3VCDebugWrapper@@A; this
0x180011516  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x18001151b  mov     rcx, [rbp+57h+var_50]; pSid
0x18001151f  test    rcx, rcx
0x180011522  jz      short loc_18001152A
0x180011524  call    cs:__imp_FreeSid
0x18001152a  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x18001152e  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180011534  mov     [rbp+57h+var_50], r14
0x180011538  cmp     [rbp+57h+var_38], r14d
0x18001153c  jz      loc_1800115EF
0x180011542  cmp     [rbp+57h+var_34], r14d
0x180011546  jnz     loc_1800115EF
0x18001154c  mov     [rbp+57h+var_34], 1
0x180011553  lea     rax, [rbp+57h+var_50]
0x180011557  mov     [rsp+0B0h+pSid], rax; pSid
0x18001155c  mov     [rsp+0B0h+nSubAuthority7], r14d; nSubAuthority7
0x180011561  mov     [rsp+0B0h+nSubAuthority6], r14d; nSubAuthority6
0x180011566  mov     [rsp+0B0h+nSubAuthority5], r14d; nSubAuthority5
0x18001156b  mov     [rsp+0B0h+nSubAuthority4], r14d; nSubAuthority4
0x180011570  mov     [rsp+0B0h+nSubAuthority3], r14d; nSubAuthority3
0x180011575  mov     [rsp+0B0h+nSubAuthority2], r14d; nSubAuthority2
0x18001157a  xor     r9d, r9d; nSubAuthority1
0x18001157d  lea     r8d, [r9+14h]; nSubAuthority0
0x180011581  mov     dl, 1; nSubAuthorityCount
0x180011583  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180011587  call    cs:__imp_AllocateAndInitializeSid
0x18001158d  test    eax, eax
0x18001158f  jnz     short loc_1800115B1
0x180011591  call    cs:__imp_GetLastError
0x180011597  mov     r9d, eax
0x18001159a  lea     r8, aAddnetworkserv; "AddNetworkService: Failed to initialize"...
0x1800115a1  mov     edx, ebx; unsigned int
0x1800115a3  lea     rcx, ?dbgCommon@@3VCDebugWrapper@@A; this
0x1800115aa  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800115af  jmp     short loc_180011604
0x1800115b1  mov     eax, [rbp+57h+var_3C]
0x1800115b4  cmp     [rbp+57h+var_40], eax
0x1800115b7  jnz     short loc_1800115C6
0x1800115b9  lea     rcx, [rbp+57h+var_48]; this
0x1800115bd  call    ?ReAllocSidList@CSecDesc@@AEAAHXZ; CSecDesc::ReAllocSidList(void)
0x1800115c2  test    eax, eax
0x1800115c4  jz      short loc_180011604
0x1800115c6  mov     rdx, [rbp+57h+var_50]
0x1800115ca  mov     [rbp+57h+var_50], r14
0x1800115ce  mov     eax, [rbp+57h+var_40]
0x1800115d1  lea     rcx, [rax+rax*2]
0x1800115d5  mov     rax, [rbp+57h+var_48]
0x1800115d9  mov     [rax+rcx*8], rdx
0x1800115dd  mov     [rax+rcx*8+8], ebx
0x1800115e1  mov     [rax+rcx*8+10h], r14d
0x1800115e6  inc     [rbp+57h+var_40]
0x1800115e9  mov     [rbp+57h+var_34], r14d
0x1800115ed  jmp     short loc_180011604
0x1800115ef  lea     r8, aAddnetworkserv_0; "AddNetworkService: Not initialised or f"...
0x1800115f6  mov     edx, ebx; unsigned int
0x1800115f8  lea     rcx, ?dbgCommon@@3VCDebugWrapper@@A; this
0x1800115ff  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x180011604  mov     rcx, [rbp+57h+var_50]; pSid
0x180011608  test    rcx, rcx
0x18001160b  jz      short loc_180011613
0x18001160d  call    cs:__imp_FreeSid
0x180011613  lea     rcx, [rbp+57h+var_48]; this
0x180011617  call    ?MakeSD@CSecDesc@@QEAAPEAU_SECURITY_DESCRIPTOR@@XZ; CSecDesc::MakeSD(void)
0x18001161c  mov     rbx, rax
0x18001161f  mov     rcx, [rsi+40h]; hMem
0x180011623  test    rcx, rcx
0x180011626  jz      short loc_18001162E
0x180011628  call    cs:__imp_LocalFree
0x18001162e  mov     [rsi+40h], rbx
0x180011632  test    rbx, rbx
0x180011635  jnz     short loc_18001163F
0x180011637  call    cs:__imp_GetLastError
0x18001163d  mov     edi, eax
0x18001163f  lea     rcx, [rbp+57h+var_48]; this
0x180011643  call    ??1CSecDesc@@QEAA@XZ; CSecDesc::~CSecDesc(void)
0x180011648  mov     eax, edi
0x18001164a  mov     rcx, [rbp+57h+var_18]
0x18001164e  xor     rcx, rsp; StackCookie
0x180011651  call    __security_check_cookie
0x180011656  lea     r11, [rsp+0B0h+var_10]
0x18001165e  mov     rbx, [r11+28h]
0x180011662  mov     rsi, [r11+30h]
0x180011666  mov     rsp, r11
0x180011669  pop     r14
0x18001166b  pop     rdi
0x18001166c  pop     rbp
0x18001166d  retn
```
