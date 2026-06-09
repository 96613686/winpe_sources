# CTaskHandler::Resume(void)

- ea: `0x1800065d0`
- end: `0x180006617`
- name: `?Resume@CTaskHandler@@UEAAJXZ`
- size: `71`
- prototype: `__int64 __fastcall(CTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180005ea4`
- `0x180006264`
- `0x1800065d0`

## pseudocode

```c
__int64 __fastcall CTaskHandler::Resume(CTaskHandler *this)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids);
  CTaskHandler::InterlockedEnterMaintenanceMode(this);
  return 0;
}

```

## disassembly

```asm
0x1800065d0  push    rbx
0x1800065d2  sub     rsp, 20h
0x1800065d6  mov     rbx, rcx
0x1800065d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800065e0  lea     rax, WPP_GLOBAL_Control
0x1800065e7  cmp     rcx, rax
0x1800065ea  jz      short loc_180006607
0x1800065ec  test    byte ptr [rcx+1Ch], 8
0x1800065f0  jz      short loc_180006607
0x1800065f2  mov     rcx, [rcx+10h]
0x1800065f6  lea     r8, WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids
0x1800065fd  mov     edx, 10h
0x180006602  call    WPP_SF_
0x180006607  mov     rcx, rbx; this
0x18000660a  call    ?InterlockedEnterMaintenanceMode@CTaskHandler@@AEAAXXZ; CTaskHandler::InterlockedEnterMaintenanceMode(void)
0x18000660f  xor     eax, eax
0x180006611  add     rsp, 20h
0x180006615  pop     rbx
0x180006616  retn
```
