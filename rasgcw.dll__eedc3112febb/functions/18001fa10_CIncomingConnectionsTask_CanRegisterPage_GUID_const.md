# CIncomingConnectionsTask::CanRegisterPage(_GUID * const)

- ea: `0x18001fa10`
- end: `0x18001fa57`
- name: `?CanRegisterPage@CIncomingConnectionsTask@@UEAAJQEAU_GUID@@@Z`
- size: `71`
- prototype: `__int64 __fastcall(CIncomingConnectionsTask *__hidden this, struct _GUID *const)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18001fa10`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18001fa47`
- `rtutils!TracePrintfExA` at `0x18001fa47`

## string_xrefs

- `0x18001fa3b`: `CIncomingConnectionsTask::CanRegisterPage: Rejected CanRegisterPage request.`

## pseudocode

```c
__int64 __fastcall CIncomingConnectionsTask::CanRegisterPage(CIncomingConnectionsTask *this, struct _GUID *const a2)
{
  __int64 result; // rax

  result = *(_QWORD *)&a2->Data1 - *(_QWORD *)&CLSID_IncomingConnectionCheckDevsPage.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&CLSID_IncomingConnectionCheckDevsPage.Data1 )
    result = *(_QWORD *)a2->Data4 - *(_QWORD *)CLSID_IncomingConnectionCheckDevsPage.Data4;
  if ( result )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "CIncomingConnectionsTask::CanRegisterPage: Rejected CanRegisterPage request.");
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18001fa10  sub     rsp, 28h
0x18001fa14  mov     rax, [rdx]
0x18001fa17  sub     rax, qword ptr cs:CLSID_IncomingConnectionCheckDevsPage.Data1
0x18001fa1e  jnz     short loc_18001FA2B
0x18001fa20  mov     rax, [rdx+8]
0x18001fa24  sub     rax, qword ptr cs:CLSID_IncomingConnectionCheckDevsPage.Data4
0x18001fa2b  test    rax, rax
0x18001fa2e  jz      short loc_18001FA52
0x18001fa30  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001fa36  cmp     ecx, 0FFFFFFFFh
0x18001fa39  jz      short loc_18001FA4D
0x18001fa3b  lea     r8, aCincomingconne_6; "CIncomingConnectionsTask::CanRegisterPa"...
0x18001fa42  mov     edx, 0Ch; dwFlags
0x18001fa47  call    cs:__imp_TracePrintfExA
0x18001fa4d  mov     eax, 1
0x18001fa52  add     rsp, 28h
0x18001fa56  retn
```
