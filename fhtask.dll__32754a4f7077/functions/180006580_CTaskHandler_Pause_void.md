# CTaskHandler::Pause(void)

- ea: `0x180006580`
- end: `0x1800065c9`
- name: `?Pause@CTaskHandler@@UEAAJXZ`
- size: `73`
- prototype: `__int64 __fastcall(CTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180005ea4`
- `0x1800064d4`
- `0x180006580`

## pseudocode

```c
__int64 __fastcall CTaskHandler::Pause(CTaskHandler *this)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids);
  CTaskHandler::InterlockedExitMaintenanceMode(this, 0);
  return 0;
}

```

## disassembly

```asm
0x180006580  push    rbx
0x180006582  sub     rsp, 20h
0x180006586  mov     rbx, rcx
0x180006589  mov     rcx, cs:WPP_GLOBAL_Control
0x180006590  lea     rax, WPP_GLOBAL_Control
0x180006597  cmp     rcx, rax
0x18000659a  jz      short loc_1800065B7
0x18000659c  test    byte ptr [rcx+1Ch], 8
0x1800065a0  jz      short loc_1800065B7
0x1800065a2  mov     rcx, [rcx+10h]
0x1800065a6  lea     r8, WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids
0x1800065ad  mov     edx, 0Fh
0x1800065b2  call    WPP_SF_
0x1800065b7  xor     edx, edx; int
0x1800065b9  mov     rcx, rbx; this
0x1800065bc  call    ?InterlockedExitMaintenanceMode@CTaskHandler@@AEAAXH@Z; CTaskHandler::InterlockedExitMaintenanceMode(int)
0x1800065c1  xor     eax, eax
0x1800065c3  add     rsp, 20h
0x1800065c7  pop     rbx
0x1800065c8  retn
```
