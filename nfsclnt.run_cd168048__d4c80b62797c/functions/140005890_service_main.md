# service_main

- ea: `0x140005890`
- end: `0x14000595a`
- name: `service_main`
- size: `202`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x140002bd8`
- `0x1400053e0`
- `0x140005890`
- `0x14000664c`

## import_xrefs

- `ADVAPI32!RegisterServiceCtrlHandlerW` at `0x1400058d5`
- `ADVAPI32!RegisterServiceCtrlHandlerW` at `0x1400058d5`

## pseudocode

```c
void service_main()
{
  ssStatus.dwServiceType = 16;
  ssStatus.dwCurrentState = 2;
  ssStatus.dwWaitHint = 10000;
  *(_OWORD *)&ssStatus.dwControlsAccepted = 0;
  sshStatusHandle = RegisterServiceCtrlHandlerW(L"NfsClnt", service_ctrl);
  if ( sshStatusHandle && (unsigned int)ReportStatusToSCMgr(2u, 0, 0x2710u) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_befea35b910b3d8fcaee8503f00af8a3_Traceguids);
    ServiceStart();
  }
  if ( sshStatusHandle )
    ReportStatusToSCMgr(1u, dwErr, 0);
}

```

## disassembly

```asm
0x140005890  mov     [rsp+arg_0], rbx
0x140005895  push    rdi
0x140005896  sub     rsp, 20h
0x14000589a  mov     rbx, rdx
0x14000589d  mov     cs:ssStatus.dwServiceType, 10h
0x1400058a7  mov     edi, ecx
0x1400058a9  mov     cs:ssStatus.dwCurrentState, 2
0x1400058b3  xorps   xmm0, xmm0
0x1400058b6  mov     cs:ssStatus.dwWaitHint, 2710h
0x1400058c0  lea     rdx, service_ctrl; lpHandlerProc
0x1400058c7  lea     rcx, ServiceName; "NfsClnt"
0x1400058ce  movups  xmmword ptr cs:ssStatus.dwControlsAccepted, xmm0
0x1400058d5  call    cs:__imp_RegisterServiceCtrlHandlerW
0x1400058db  mov     cs:sshStatusHandle, rax
0x1400058e2  test    rax, rax
0x1400058e5  jz      short loc_140005933
0x1400058e7  xor     edx, edx
0x1400058e9  mov     r8d, 2710h
0x1400058ef  lea     ecx, [rdx+2]
0x1400058f2  call    ReportStatusToSCMgr
0x1400058f7  test    eax, eax
0x1400058f9  jz      short loc_140005933
0x1400058fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140005902  lea     rax, WPP_GLOBAL_Control
0x140005909  cmp     rcx, rax
0x14000590c  jz      short loc_140005929
0x14000590e  test    byte ptr [rcx+1Ch], 8
0x140005912  jz      short loc_140005929
0x140005914  mov     rcx, [rcx+10h]
0x140005918  lea     r8, WPP_befea35b910b3d8fcaee8503f00af8a3_Traceguids
0x14000591f  mov     edx, 13h
0x140005924  call    WPP_SF_
0x140005929  mov     rdx, rbx
0x14000592c  mov     ecx, edi
0x14000592e  call    ServiceStart
0x140005933  cmp     cs:sshStatusHandle, 0
0x14000593b  jz      short loc_14000594F
0x14000593d  mov     edx, cs:dwErr
0x140005943  xor     r8d, r8d
0x140005946  lea     ecx, [r8+1]
0x14000594a  call    ReportStatusToSCMgr
0x14000594f  mov     rbx, [rsp+28h+arg_0]
0x140005954  add     rsp, 20h
0x140005958  pop     rdi
0x140005959  retn
```
