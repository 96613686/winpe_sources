# CIncomingConnectionsTask::CanUnregisterPage(_GUID * const)

- ea: `0x18001fb60`
- end: `0x18001fba7`
- name: `?CanUnregisterPage@CIncomingConnectionsTask@@UEAAJQEAU_GUID@@@Z`
- size: `71`
- prototype: `__int64 __fastcall(CIncomingConnectionsTask *__hidden this, struct _GUID *const)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18001fb60`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18001fb97`
- `rtutils!TracePrintfExA` at `0x18001fb97`

## string_xrefs

- `0x18001fb8b`: `CIncomingConnectionsTask::CanUnregisterPage: Rejected CanUnregisterPage request.`

## pseudocode

```c
__int64 __fastcall CIncomingConnectionsTask::CanUnregisterPage(CIncomingConnectionsTask *this, struct _GUID *const a2)
{
  __int64 result; // rax

  result = *(_QWORD *)&a2->Data1 - *(_QWORD *)&CLSID_IncomingConnectionCheckDevsPage.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&CLSID_IncomingConnectionCheckDevsPage.Data1 )
    result = *(_QWORD *)a2->Data4 - *(_QWORD *)CLSID_IncomingConnectionCheckDevsPage.Data4;
  if ( result )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(
        g_dwTraceId,
        0xCu,
        "CIncomingConnectionsTask::CanUnregisterPage: Rejected CanUnregisterPage request.");
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18001fb60  sub     rsp, 28h
0x18001fb64  mov     rax, [rdx]
0x18001fb67  sub     rax, qword ptr cs:CLSID_IncomingConnectionCheckDevsPage.Data1
0x18001fb6e  jnz     short loc_18001FB7B
0x18001fb70  mov     rax, [rdx+8]
0x18001fb74  sub     rax, qword ptr cs:CLSID_IncomingConnectionCheckDevsPage.Data4
0x18001fb7b  test    rax, rax
0x18001fb7e  jz      short loc_18001FBA2
0x18001fb80  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001fb86  cmp     ecx, 0FFFFFFFFh
0x18001fb89  jz      short loc_18001FB9D
0x18001fb8b  lea     r8, aCincomingconne_4; "CIncomingConnectionsTask::CanUnregister"...
0x18001fb92  mov     edx, 0Ch; dwFlags
0x18001fb97  call    cs:__imp_TracePrintfExA
0x18001fb9d  mov     eax, 1
0x18001fba2  add     rsp, 28h
0x18001fba6  retn
```
