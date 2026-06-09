# CTaskHandler::ExitMaintenanceMode(int)

- ea: `0x180006070`
- end: `0x180006124`
- name: `?ExitMaintenanceMode@CTaskHandler@@AEAAXH@Z`
- size: `180`
- prototype: `void __fastcall(CTaskHandler *__hidden this, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180006264`
- `0x1800064d4`

## callees

- `0x180006070`
- `0x1800067a0`

## import_xrefs

- `KERNEL32!CloseThreadpoolWait` at `0x1800060bc`
- `KERNEL32!CloseThreadpoolWait` at `0x1800060bc`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x1800060af`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x1800060af`
- `KERNEL32!CloseHandle` at `0x18000608b`
- `KERNEL32!CloseHandle` at `0x18000608b`
- `fhsvcctl!FhServiceExitMaintenanceMode` at `0x1800060de`
- `fhsvcctl!FhServiceExitMaintenanceMode` at `0x1800060de`

## pseudocode

```c
void __fastcall CTaskHandler::ExitMaintenanceMode(CTaskHandler *this, int a2)
{
  void *v4; // rcx
  struct _TP_WAIT *v5; // rcx
  __int64 v6; // rcx
  int v7; // eax

  v4 = (void *)*((_QWORD *)this + 16);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 16) = 0;
  }
  v5 = (struct _TP_WAIT *)*((_QWORD *)this + 17);
  if ( v5 )
  {
    if ( !a2 )
      WaitForThreadpoolWaitCallbacks(v5, 1);
    CloseThreadpoolWait(*((PTP_WAIT *)this + 17));
    *((_QWORD *)this + 17) = 0;
  }
  if ( *((_DWORD *)this + 30) )
  {
    v6 = *((_QWORD *)this + 9);
    *((_DWORD *)this + 30) = 0;
    v7 = FhServiceExitMaintenanceMode(v6);
    if ( v7 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids,
        (unsigned int)v7);
    }
  }
}

```

## disassembly

```asm
0x180006070  mov     [rsp+arg_0], rbx
0x180006075  push    rdi
0x180006076  sub     rsp, 20h
0x18000607a  mov     rbx, rcx
0x18000607d  mov     edi, edx
0x18000607f  mov     rcx, [rcx+80h]; hObject
0x180006086  test    rcx, rcx
0x180006089  jz      short loc_18000609C
0x18000608b  call    cs:__imp_CloseHandle
0x180006091  mov     qword ptr [rbx+80h], 0
0x18000609c  mov     rcx, [rbx+88h]; pwa
0x1800060a3  test    rcx, rcx
0x1800060a6  jz      short loc_1800060CD
0x1800060a8  test    edi, edi
0x1800060aa  jnz     short loc_1800060B5
0x1800060ac  lea     edx, [rdi+1]; fCancelPendingCallbacks
0x1800060af  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800060b5  mov     rcx, [rbx+88h]; pwa
0x1800060bc  call    cs:__imp_CloseThreadpoolWait
0x1800060c2  mov     qword ptr [rbx+88h], 0
0x1800060cd  cmp     dword ptr [rbx+78h], 0
0x1800060d1  jz      short loc_180006119
0x1800060d3  mov     rcx, [rbx+48h]
0x1800060d7  mov     dword ptr [rbx+78h], 0
0x1800060de  call    cs:__imp_FhServiceExitMaintenanceMode
0x1800060e4  test    eax, eax
0x1800060e6  jns     short loc_180006119
0x1800060e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800060ef  lea     rdx, WPP_GLOBAL_Control
0x1800060f6  cmp     rcx, rdx
0x1800060f9  jz      short loc_180006119
0x1800060fb  test    byte ptr [rcx+1Ch], 1
0x1800060ff  jz      short loc_180006119
0x180006101  mov     rcx, [rcx+10h]
0x180006105  lea     r8, WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids
0x18000610c  mov     edx, 16h
0x180006111  mov     r9d, eax
0x180006114  call    WPP_SF_d
0x180006119  mov     rbx, [rsp+28h+arg_0]
0x18000611e  add     rsp, 20h
0x180006122  pop     rdi
0x180006123  retn
```
