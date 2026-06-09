# ServiceMain

- ea: `0x1800033d0`
- end: `0x18000347b`
- name: `ServiceMain`
- size: `171`
- prototype: `DWORD __fastcall(unsigned int, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180003360`
- `0x1800033d0`
- `0x180013b24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000344e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000344e`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800033f0`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800033f0`

## string_xrefs

- `0x1800033e9`: `MSiSCSI`

## pseudocode

```c
DWORD __fastcall ServiceMain(unsigned int a1, __int64 a2)
{
  DWORD result; // eax

  DiscpStatusHandle = (__int64)RegisterServiceCtrlHandlerExW(L"MSiSCSI", DiscpServiceControlHandler, 0);
  if ( !DiscpStatusHandle )
    goto LABEL_5;
  DiscpServiceStatus = 16;
  dword_180027550 = 0;
  if ( !(unsigned int)ReportStatusToSCMgr(2, 0, 10000) )
    goto LABEL_5;
  for ( result = DiscpServiceStart(DiscpStatusHandle, a1, a2); !result; result = GetLastError() )
  {
    result = ReportStatusToSCMgr(4, 0, 0);
    if ( result )
      return result;
LABEL_5:
    ;
  }
  if ( DiscpStatusHandle )
    return ReportStatusToSCMgr(1, result, 0);
  return result;
}

```

## disassembly

```asm
0x1800033d0  mov     [rsp+arg_0], rbx
0x1800033d5  push    rdi
0x1800033d6  sub     rsp, 20h
0x1800033da  mov     rbx, rdx
0x1800033dd  mov     edi, ecx
0x1800033df  lea     rdx, DiscpServiceControlHandler; lpHandlerProc
0x1800033e6  xor     r8d, r8d; lpContext
0x1800033e9  lea     rcx, ServiceName; "MSiSCSI"
0x1800033f0  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800033f6  mov     cs:DiscpStatusHandle, rax
0x1800033fd  test    rax, rax
0x180003400  jz      short loc_18000344E
0x180003402  xor     edx, edx
0x180003404  mov     cs:DiscpServiceStatus, 10h
0x18000340e  mov     r8d, 2710h
0x180003414  mov     cs:dword_180027550, 0
0x18000341e  lea     ecx, [rdx+2]
0x180003421  call    ReportStatusToSCMgr
0x180003426  test    eax, eax
0x180003428  jz      short loc_18000344E
0x18000342a  mov     rcx, cs:DiscpStatusHandle
0x180003431  mov     r8, rbx
0x180003434  mov     edx, edi
0x180003436  call    DiscpServiceStart
0x18000343b  jmp     short loc_180003454
0x18000343d  xor     edx, edx
0x18000343f  xor     r8d, r8d
0x180003442  lea     ecx, [rdx+4]
0x180003445  call    ReportStatusToSCMgr
0x18000344a  test    eax, eax
0x18000344c  jnz     short loc_180003470
0x18000344e  call    cs:__imp_GetLastError
0x180003454  test    eax, eax
0x180003456  jz      short loc_18000343D
0x180003458  cmp     cs:DiscpStatusHandle, 0
0x180003460  jz      short loc_180003470
0x180003462  xor     r8d, r8d
0x180003465  mov     edx, eax
0x180003467  lea     ecx, [r8+1]
0x18000346b  call    ReportStatusToSCMgr
0x180003470  mov     rbx, [rsp+28h+arg_0]
0x180003475  add     rsp, 20h
0x180003479  pop     rdi
0x18000347a  retn
```
