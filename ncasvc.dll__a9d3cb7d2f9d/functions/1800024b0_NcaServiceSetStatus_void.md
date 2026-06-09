# NcaServiceSetStatus(void)

- ea: `0x1800024b0`
- end: `0x1800025ab`
- name: `?NcaServiceSetStatus@@YAJXZ`
- size: `251`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800026d0`
- `0x180004400`
- `0x180004680`

## callees

- `0x1800024b0`
- `0x1800033bc`
- `0x180004c8c`
- `0x180004f04`
- `0x180004f34`
- `0x1800199b4`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002523`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002533`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002533`

## string_xrefs

- `0x180002542`: `SetServiceStatus`
- `0x180002549`: `NcaServiceSetStatus`
- `0x180002595`: `NcaServiceSetStatus`

## pseudocode

```c
__int64 __fastcall NcaServiceSetStatus(__int64 a1, __int64 a2)
{
  unsigned int v2; // ebx
  PVOID *v3; // rcx
  SERVICE_STATUS_HANDLE v4; // rax
  DWORD LastError; // eax

  v2 = 0;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  v4 = hServiceStatus;
  if ( hServiceStatus )
  {
    if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    {
      McTemplateU0q_EventWriteTransfer(v3, a2, ServiceStatus.dwCurrentState);
      v4 = hServiceStatus;
    }
    if ( !SetServiceStatus(v4, &ServiceStatus) )
    {
      LastError = GetLastError();
      v2 = NcaReportErrorAsWinError("NcaServiceSetStatus", "SetServiceStatus", LastError);
    }
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 8) != 0 )
    WPP_SF_d(v3[2], 37, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids, v2);
  if ( (v2 & 0x80000000) != 0 )
    return NcaReportReturnError("NcaServiceSetStatus", v2);
  else
    return v2;
}

```

## disassembly

```asm
0x1800024b0  mov     [rsp+arg_0], rbx
0x1800024b5  push    rdi
0x1800024b6  sub     rsp, 20h
0x1800024ba  xor     ebx, ebx
0x1800024bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024c3  lea     rdi, WPP_GLOBAL_Control
0x1800024ca  cmp     rcx, rdi
0x1800024cd  jz      short loc_1800024F1
0x1800024cf  test    byte ptr [rcx+1Ch], 8
0x1800024d3  jz      short loc_1800024F1
0x1800024d5  mov     rcx, [rcx+10h]
0x1800024d9  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x1800024e0  mov     edx, 24h ; '$'
0x1800024e5  call    WPP_SF_
0x1800024ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024f1  mov     rax, cs:hServiceStatus
0x1800024f8  test    rax, rax
0x1800024fb  jz      short loc_18000255E
0x1800024fd  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x180002504  jz      short loc_180002519
0x180002506  mov     r8d, cs:ServiceStatus.dwCurrentState
0x18000250d  call    McTemplateU0q_EventWriteTransfer
0x180002512  mov     rax, cs:hServiceStatus
0x180002519  lea     rdx, ServiceStatus; lpServiceStatus
0x180002520  mov     rcx, rax; hServiceStatus
0x180002523  call    cs:__imp_SetServiceStatus
0x18000252a  nop     dword ptr [rax+rax+00h]
0x18000252f  test    eax, eax
0x180002531  jnz     short loc_180002557
0x180002533  call    cs:__imp_GetLastError
0x18000253a  nop     dword ptr [rax+rax+00h]
0x18000253f  mov     r8d, eax
0x180002542  lea     rdx, aSetservicestat; "SetServiceStatus"
0x180002549  lea     rcx, aNcaservicesets; "NcaServiceSetStatus"
0x180002550  call    NcaReportErrorAsWinError
0x180002555  mov     ebx, eax
0x180002557  mov     rcx, cs:WPP_GLOBAL_Control
0x18000255e  cmp     rcx, rdi
0x180002561  jz      short loc_180002581
0x180002563  test    byte ptr [rcx+1Ch], 8
0x180002567  jz      short loc_180002581
0x180002569  mov     rcx, [rcx+10h]
0x18000256d  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x180002574  mov     edx, 25h ; '%'
0x180002579  mov     r9d, ebx
0x18000257c  call    WPP_SF_d
0x180002581  test    ebx, ebx
0x180002583  js      short loc_180002593
0x180002585  mov     eax, ebx
0x180002587  mov     rbx, [rsp+28h+arg_0]
0x18000258c  add     rsp, 20h
0x180002590  pop     rdi
0x180002591  retn
0x180002593  mov     edx, ebx
0x180002595  lea     rcx, aNcaservicesets; "NcaServiceSetStatus"
0x18000259c  mov     rbx, [rsp+28h+arg_0]
0x1800025a1  add     rsp, 20h
0x1800025a5  pop     rdi
0x1800025a6  jmp     NcaReportReturnError
```
