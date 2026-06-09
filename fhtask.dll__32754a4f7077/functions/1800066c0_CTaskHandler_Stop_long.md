# CTaskHandler::Stop(long *)

- ea: `0x1800066c0`
- end: `0x180006720`
- name: `?Stop@CTaskHandler@@UEAAJPEAJ@Z`
- size: `96`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180005ea4`
- `0x1800064d4`
- `0x1800066c0`

## pseudocode

```c
__int64 __fastcall CTaskHandler::Stop(struct _RTL_CRITICAL_SECTION *this, int *a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids);
  CTaskHandler::InterlockedExitMaintenanceMode(this, 0);
  if ( a2 )
    *a2 = 0;
  return 0;
}

```

## disassembly

```asm
0x1800066c0  mov     [rsp+arg_0], rbx
0x1800066c5  push    rdi
0x1800066c6  sub     rsp, 20h
0x1800066ca  mov     rbx, rdx
0x1800066cd  mov     rdi, rcx
0x1800066d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066d7  lea     rax, WPP_GLOBAL_Control
0x1800066de  cmp     rcx, rax
0x1800066e1  jz      short loc_1800066FE
0x1800066e3  test    byte ptr [rcx+1Ch], 8
0x1800066e7  jz      short loc_1800066FE
0x1800066e9  mov     rcx, [rcx+10h]
0x1800066ed  lea     r8, WPP_c432cab80fa834a8c758b8af3c384ba0_Traceguids
0x1800066f4  mov     edx, 0Eh
0x1800066f9  call    WPP_SF_
0x1800066fe  xor     edx, edx; int
0x180006700  mov     rcx, rdi; this
0x180006703  call    ?InterlockedExitMaintenanceMode@CTaskHandler@@AEAAXH@Z; CTaskHandler::InterlockedExitMaintenanceMode(int)
0x180006708  test    rbx, rbx
0x18000670b  jz      short loc_180006713
0x18000670d  mov     dword ptr [rbx], 0
0x180006713  mov     rbx, [rsp+28h+arg_0]
0x180006718  xor     eax, eax
0x18000671a  add     rsp, 20h
0x18000671e  pop     rdi
0x18000671f  retn
```
