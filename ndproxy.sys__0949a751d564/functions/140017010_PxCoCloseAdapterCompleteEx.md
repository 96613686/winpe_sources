# PxCoCloseAdapterCompleteEx

- ea: `0x140017010`
- end: `0x14001709f`
- name: `PxCoCloseAdapterCompleteEx`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001bc8`
- `0x140017010`

## import_xrefs

- `NDIS!NdisSetEvent` at `0x140017087`
- `NDIS!NdisSetEvent` at `0x140017087`

## pseudocode

```c
void __fastcall PxCoCloseAdapterCompleteEx(_DWORD *a1)
{
  int v1; // edi
  _DWORD *v2; // rbx
  struct _NDIS_EVENT *v3; // rcx

  v1 = *a1;
  v2 = a1 - 4;
  if ( *a1 != 538996035 )
    v2 = a1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids, v2);
  if ( v1 == 538996035 )
  {
    v2[128] = 0;
    v3 = (struct _NDIS_EVENT *)(v2 + 122);
  }
  else
  {
    v2[120] = 0;
    v3 = (struct _NDIS_EVENT *)(v2 + 114);
  }
  NdisSetEvent(v3);
}

```

## disassembly

```asm
0x140017010  mov     [rsp+arg_0], rbx
0x140017015  push    rdi
0x140017016  sub     rsp, 20h
0x14001701a  mov     edi, [rcx]
0x14001701c  cmp     edi, 20206D43h
0x140017022  lea     rbx, [rcx-10h]
0x140017026  lea     rax, WPP_GLOBAL_Control
0x14001702d  cmovnz  rbx, rcx
0x140017031  mov     rcx, cs:WPP_GLOBAL_Control
0x140017038  cmp     rcx, rax
0x14001703b  jz      short loc_14001705B
0x14001703d  cmp     byte ptr [rcx+29h], 5
0x140017041  jb      short loc_14001705B
0x140017043  mov     rcx, [rcx+18h]
0x140017047  lea     r8, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids
0x14001704e  mov     edx, 1Bh
0x140017053  mov     r9, rbx
0x140017056  call    WPP_SF_q
0x14001705b  cmp     edi, 20206D43h
0x140017061  jz      short loc_140017076
0x140017063  mov     dword ptr [rbx+1E0h], 0
0x14001706d  lea     rcx, [rbx+1C8h]
0x140017074  jmp     short loc_140017087
0x140017076  mov     dword ptr [rbx+200h], 0
0x140017080  lea     rcx, [rbx+1E8h]; Event
0x140017087  call    cs:__imp_NdisSetEvent
0x14001708e  nop     dword ptr [rax+rax+00h]
0x140017093  mov     rbx, [rsp+28h+arg_0]
0x140017098  add     rsp, 20h
0x14001709c  pop     rdi
0x14001709d  retn
```
