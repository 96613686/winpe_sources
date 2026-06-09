# WfpAuditInitialize

- ea: `0x18011763c`
- end: `0x180117809`
- name: `WfpAuditInitialize`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180085d50`

## callees

- `0x180003c7c`
- `0x1800061ec`
- `0x180010db0`
- `0x180015fb4`
- `0x1800163b0`
- `0x180016534`
- `0x18004cb9c`
- `0x180050850`
- `0x180052ae8`
- `0x18011763c`
- `0x180117ae4`
- `0x180117b7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801176bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180117789`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801176bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180117789`
- `ntdll!RtlAdjustPrivilege` at `0x180117675`
- `ntdll!RtlAdjustPrivilege` at `0x180117675`
- `AUTHZ!AuthziInitializeAuditEventType` at `0x18011777a`
- `AUTHZ!AuthziInitializeAuditEventType` at `0x18011777a`
- `AUTHZ!AuthzInitializeResourceManager` at `0x1801176b5`
- `AUTHZ!AuthzInitializeResourceManager` at `0x1801176b5`

## string_xrefs

- `0x180117682`: `RtlAdjustPrivilege`

## pseudocode

```c
__int64 WfpAuditInitialize()
{
  NTSTATUS v0; // eax
  __int64 v1; // rcx
  __int64 v2; // rax
  DWORD LastError; // eax
  __int64 v4; // rcx
  const char *v5; // rdx
  HRESULT v6; // eax
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rbx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rcx
  bool v13; // zf
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  int szResourceManagerName; // [rsp+20h] [rbp-58h]
  ULONGLONG pullResult; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int8 OldValue[8]; // [rsp+38h] [rbp-40h] BYREF

  OldValue[0] = 0;
  pullResult = 0;
  v0 = RtlAdjustPrivilege(0x15u, 1u, 0, OldValue);
  if ( v0 < 0 )
  {
    v2 = WfpReportSysErrorAsNtStatus(v1, "RtlAdjustPrivilege", (unsigned int)v0);
LABEL_15:
    v9 = v2;
    v13 = v2 == 0;
    goto LABEL_18;
  }
  if ( !AuthzInitializeResourceManager(0, 0, 0, 0, L"FWP", &gWfpAudit) )
  {
    LastError = GetLastError();
    v5 = "AuthzInitializeResourceManager";
LABEL_14:
    v2 = WfpReportSysErrorAsWinError(v4, v5, LastError, 1);
    goto LABEL_15;
  }
  v6 = ULongLongMult(0x10u, 0xCu, &pullResult);
  if ( v6 < 0 )
  {
    v2 = WfpReportSysErrorAsHResult(v7, "ULongLongMult", (unsigned int)v6, 1);
    goto LABEL_15;
  }
  v9 = WfpBufferCopy(qword_18012ACC0, pullResult, v8, (void **)&qword_180177E10);
  if ( !v9 )
  {
    v9 = WfpMemAllocArray(0x10u, 8u, v10, &qword_180177E18);
    if ( !v9 )
    {
      dword_180177E08 = 16;
      while ( (unsigned __int16)v9 < 0x10u )
      {
        szResourceManagerName = qword_180177E18 + 8 * (unsigned __int16)v9;
        if ( !(unsigned int)AuthziInitializeAuditEventType(
                              0,
                              *((unsigned __int16 *)qword_18012ACC0 + 6 * (unsigned __int16)v9),
                              *((unsigned __int16 *)qword_18012ACC0 + 6 * (unsigned __int16)v9 + 1),
                              *((unsigned __int16 *)qword_18012ACC0 + 6 * (unsigned __int16)v9 + 2)) )
        {
          LastError = GetLastError();
          v5 = "AuthziInitializeAuditEventType";
          goto LABEL_14;
        }
        LOWORD(v9) = v9 + 1;
      }
      v9 = WfpStringTableCreate(v12, v11, &qword_180177E20);
      if ( !v9 )
      {
        v9 = WfpAuditPolicyNotifyCreate(v15, v14, v16, v17, szResourceManagerName, &qword_180177E30);
        v13 = v9 == 0;
LABEL_18:
        if ( v13 )
          return v9;
      }
    }
  }
  WfpAuditShutdown();
  if ( v9 )
    WfpReportError(v9, "WfpAuditInitialize");
  return v9;
}

```

## disassembly

```asm
0x18011763c  push    rbx
0x18011763e  push    rsi
0x18011763f  push    rdi
0x180117640  push    r14
0x180117642  sub     rsp, 58h
0x180117646  mov     rax, cs:__security_cookie
0x18011764d  xor     rax, rsp
0x180117650  mov     [rsp+78h+var_38], rax
0x180117655  xor     r8d, r8d; ForThread
0x180117658  mov     [rsp+78h+OldValue], 0
0x18011765d  lea     r9, [rsp+78h+OldValue]; OldValue
0x180117662  mov     [rsp+78h+pullResult], 0
0x18011766b  lea     edi, [r8+1]
0x18011766f  mov     dl, dil; NewValue
0x180117672  lea     ecx, [rdi+14h]; Privilege
0x180117675  call    cs:__imp_RtlAdjustPrivilege
0x18011767b  test    eax, eax
0x18011767d  jns     short loc_180117693
0x18011767f  mov     r8d, eax
0x180117682  lea     rdx, aRtladjustprivi; "RtlAdjustPrivilege"
0x180117689  call    WfpReportSysErrorAsNtStatus
0x18011768e  jmp     loc_1801177A1
0x180117693  lea     rax, gWfpAudit
0x18011769a  xor     r9d, r9d; pfnFreeDynamicGroups
0x18011769d  mov     [rsp+78h+phAuthzResourceManager], rax; phAuthzResourceManager
0x1801176a2  xor     r8d, r8d; pfnComputeDynamicGroups
0x1801176a5  lea     rax, IKE_AUDIT_SUBSYTEM_NAME; "FWP"
0x1801176ac  xor     edx, edx; pfnDynamicAccessCheck
0x1801176ae  xor     ecx, ecx; Flags
0x1801176b0  mov     [rsp+78h+szResourceManagerName], rax; szResourceManagerName
0x1801176b5  call    cs:__imp_AuthzInitializeResourceManager
0x1801176bb  test    eax, eax
0x1801176bd  jnz     short loc_1801176D1
0x1801176bf  call    cs:__imp_GetLastError
0x1801176c5  lea     rdx, aAuthzinitializ; "AuthzInitializeResourceManager"
0x1801176cc  jmp     loc_180117796
0x1801176d1  mov     edx, 0Ch; ullMultiplier
0x1801176d6  lea     r8, [rsp+78h+pullResult]; pullResult
0x1801176db  lea     esi, [rdx+4]
0x1801176de  mov     ecx, esi; ullMultiplicand
0x1801176e0  call    ULongLongMult
0x1801176e5  test    eax, eax
0x1801176e7  jns     short loc_180117700
0x1801176e9  mov     r9d, edi
0x1801176ec  lea     rdx, aUlonglongmult; "ULongLongMult"
0x1801176f3  mov     r8d, eax
0x1801176f6  call    WfpReportSysErrorAsHResult
0x1801176fb  jmp     loc_1801177A1
0x180117700  mov     rdx, [rsp+78h+pullResult]; Size
0x180117705  lea     r14, qword_18012ACC0
0x18011770c  mov     rcx, r14; Src
0x18011770f  lea     r9, qword_180177E10
0x180117716  call    WfpBufferCopy
0x18011771b  mov     rbx, rax
0x18011771e  test    rax, rax
0x180117721  jnz     loc_1801177D6
0x180117727  lea     r9, qword_180177E18
0x18011772e  mov     rcx, rsi
0x180117731  lea     edx, [rax+8]
0x180117734  call    WfpMemAllocArray
0x180117739  mov     rbx, rax
0x18011773c  test    rax, rax
0x18011773f  jnz     loc_1801177D6
0x180117745  mov     cs:dword_180177E08, esi
0x18011774b  cmp     bx, si
0x18011774e  jnb     short loc_1801177A9
0x180117750  mov     rax, cs:qword_180177E18
0x180117757  movzx   ecx, bx
0x18011775a  lea     r10, [rcx+rcx*2]
0x18011775e  movzx   r9d, word ptr [r14+r10*4+4]
0x180117764  lea     rdx, [rax+rcx*8]
0x180117768  movzx   r8d, word ptr [r14+r10*4+2]
0x18011776e  xor     ecx, ecx
0x180117770  mov     [rsp+78h+szResourceManagerName], rdx
0x180117775  movzx   edx, word ptr [r14+r10*4]
0x18011777a  call    cs:__imp_AuthziInitializeAuditEventType
0x180117780  test    eax, eax
0x180117782  jz      short loc_180117789
0x180117784  add     bx, di
0x180117787  jmp     short loc_18011774B
0x180117789  call    cs:__imp_GetLastError
0x18011778f  lea     rdx, aAuthziinitiali_1; "AuthziInitializeAuditEventType"
0x180117796  mov     r9d, edi
0x180117799  mov     r8d, eax
0x18011779c  call    WfpReportSysErrorAsWinError
0x1801177a1  mov     rbx, rax
0x1801177a4  test    rax, rax
0x1801177a7  jmp     short loc_1801177D4
0x1801177a9  lea     r8, qword_180177E20
0x1801177b0  call    WfpStringTableCreate
0x1801177b5  mov     rbx, rax
0x1801177b8  test    rax, rax
0x1801177bb  jnz     short loc_1801177D6
0x1801177bd  lea     rax, qword_180177E30
0x1801177c4  mov     [rsp+78h+phAuthzResourceManager], rax
0x1801177c9  call    WfpAuditPolicyNotifyCreate
0x1801177ce  mov     rbx, rax
0x1801177d1  test    rax, rax
0x1801177d4  jz      short loc_1801177EF
0x1801177d6  call    WfpAuditShutdown
0x1801177db  test    rbx, rbx
0x1801177de  jz      short loc_1801177EF
0x1801177e0  lea     rdx, aWfpauditinitia; "WfpAuditInitialize"
0x1801177e7  mov     rcx, rbx
0x1801177ea  call    WfpReportError
0x1801177ef  mov     rax, rbx
0x1801177f2  mov     rcx, [rsp+78h+var_38]
0x1801177f7  xor     rcx, rsp; StackCookie
0x1801177fa  call    __security_check_cookie
0x1801177ff  add     rsp, 58h
0x180117803  pop     r14
0x180117805  pop     rdi
0x180117806  pop     rsi
0x180117807  pop     rbx
0x180117808  retn
```
