# PxCoOidRequestComplete

- ea: `0x140003730`
- end: `0x1400037a1`
- name: `PxCoOidRequestComplete`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001bc8`
- `0x140003730`

## import_xrefs

- `NDIS!NdisSetEvent` at `0x140003789`
- `NDIS!NdisSetEvent` at `0x140003789`

## pseudocode

```c
void __fastcall PxCoOidRequestComplete(_DWORD *a1, __int64 a2, int a3)
{
  _DWORD *v5; // r9

  v5 = a1 - 4;
  if ( *a1 != 538996035 )
    v5 = a1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids, v5);
  *(_DWORD *)(a2 + 272) = a3;
  NdisSetEvent((PNDIS_EVENT)(a2 + 248));
}

```

## disassembly

```asm
0x140003730  mov     [rsp+arg_0], rbx
0x140003735  push    rdi
0x140003736  sub     rsp, 20h
0x14000373a  mov     edi, r8d
0x14000373d  mov     rbx, rdx
0x140003740  cmp     dword ptr [rcx], 20206D43h
0x140003746  lea     r9, [rcx-10h]
0x14000374a  lea     rax, WPP_GLOBAL_Control
0x140003751  cmovnz  r9, rcx
0x140003755  mov     rcx, cs:WPP_GLOBAL_Control
0x14000375c  cmp     rcx, rax
0x14000375f  jz      short loc_14000377C
0x140003761  cmp     byte ptr [rcx+29h], 4
0x140003765  jb      short loc_14000377C
0x140003767  mov     rcx, [rcx+18h]
0x14000376b  lea     r8, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids
0x140003772  mov     edx, 1Ch
0x140003777  call    WPP_SF_q
0x14000377c  lea     rcx, [rbx+0F8h]; Event
0x140003783  mov     [rbx+110h], edi
0x140003789  call    cs:__imp_NdisSetEvent
0x140003790  nop     dword ptr [rax+rax+00h]
0x140003795  mov     rbx, [rsp+28h+arg_0]
0x14000379a  add     rsp, 20h
0x14000379e  pop     rdi
0x14000379f  retn
```
