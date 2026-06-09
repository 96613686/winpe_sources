# _ProvOperations::AddPackage_::_1_::catch$58

- ea: `0x180034b86`
- end: `0x180034c50`
- name: `_ProvOperations::AddPackage_::_1_::catch$58`
- size: `202`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003ae0`
- `0x18000a7d0`
- `0x1800178a8`
- `0x18001f8ac`
- `0x1800225e8`
- `0x180034b86`

## import_xrefs

- `ext-ms-win-provisioning-platform-l1-1-0!ReportInstallationError` at `0x180034c35`
- `ext-ms-win-provisioning-platform-l1-1-0!ReportInstallationError` at `0x180034c35`

## pseudocode

```c
__int64 __fastcall ProvOperations::AddPackage_::_1_::catch_58(wil *a1, __int64 a2, unsigned int a3)
{
  unsigned int v4; // eax
  unsigned int v5; // r8d
  unsigned int v6; // ebx
  __int64 v8; // rcx
  __int64 v9; // r8
  int v11; // [rsp+20h] [rbp-48h]

  v4 = wil::ResultFromCaughtException(a1, (void *)a2, a3);
  v6 = v4;
  *(_DWORD *)(a2 + 80) = v4;
  if ( v4 != -2147024885 && v4 != -2147467260 )
    wil::details::in1diag3::_Log_Hr(*(wil::details::in1diag3 **)(a2 + 1688), (void *)0x19E, v5, (const char *)v6, v11);
  Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg::ProvOpsAddPkgFailed<long &>(
    a2 + 480,
    a2 + 80,
    *(_QWORD *)(a2 + 224));
  if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 2) != 0 )
  {
    *(_DWORD *)(a2 + 80) = v6;
    *(_QWORD *)(a2 + 928) = a2 + 80;
    *(_QWORD *)(a2 + 936) = 4;
    McGenEventWrite_EventWriteTransfer(v8, (const EVENT_DESCRIPTOR *)">", v9, 2u, (PEVENT_DATA_DESCRIPTOR)(a2 + 912));
  }
  if ( (unsigned __int8)IsCheckUserConsentPresent(v8) && !*(_DWORD *)(a2 + 1752) )
    ReportInstallationError(v6);
  *(_DWORD *)(a2 + 80) = v6;
  return 0;
}

```

## disassembly

```asm
0x180034b86  mov     [rsp+arg_8], rdx
0x180034b8b  push    rbx
0x180034b8c  push    rbp
0x180034b8d  sub     rsp, 58h
0x180034b91  mov     rbp, rdx
0x180034b94  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180034b99  mov     ebx, eax
0x180034b9b  mov     [rbp+50h], eax
0x180034b9e  cmp     eax, 8007000Bh
0x180034ba3  jz      short loc_180034BB0
0x180034ba5  cmp     eax, 80004004h
0x180034baa  jz      short loc_180034BB0
0x180034bac  mov     al, 1
0x180034bae  jmp     short loc_180034BB2
0x180034bb0  xor     al, al
0x180034bb2  mov     rcx, [rbp+698h]; this
0x180034bb9  test    al, al
0x180034bbb  jz      short loc_180034BCA
0x180034bbd  mov     r9d, ebx; char *
0x180034bc0  mov     edx, 19Eh; void *
0x180034bc5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180034bca  mov     r8, [rbp+0E0h]
0x180034bd1  lea     rdx, [rbp+50h]
0x180034bd5  lea     rcx, [rbp+1E0h]
0x180034bdc  call    ??$ProvOpsAddPkgFailed@AEAJ@ProvOpsAddPkg@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAXAEAJPEBD@Z; Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg::ProvOpsAddPkgFailed<long &>(long &,char const *)
0x180034be1  test    cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, 2
0x180034be8  jz      short loc_180034C21
0x180034bea  mov     [rbp+50h], ebx
0x180034bed  lea     rax, [rbp+50h]
0x180034bf1  mov     [rbp+3A0h], rax
0x180034bf8  mov     qword ptr [rbp+3A8h], 4
0x180034c03  lea     rax, [rbp+390h]
0x180034c0a  mov     qword ptr [rsp+68h+var_48], rax
0x180034c0f  mov     r9d, 2
0x180034c15  lea     rdx, ProvOpsAddPackageFailed; ">"
0x180034c1c  call    McGenEventWrite_EventWriteTransfer
0x180034c21  call    IsCheckUserConsentPresent
0x180034c26  test    al, al
0x180034c28  jz      short loc_180034C3B
0x180034c2a  cmp     dword ptr [rbp+6D8h], 0
0x180034c31  jnz     short loc_180034C3B
0x180034c33  mov     ecx, ebx
0x180034c35  call    cs:__imp_ReportInstallationError
0x180034c3b  mov     [rbp+50h], ebx
0x180034c3e  mov     rax, 0
0x180034c48  add     rsp, 58h
0x180034c4c  pop     rbp
0x180034c4d  pop     rbx
0x180034c4e  retn
```
