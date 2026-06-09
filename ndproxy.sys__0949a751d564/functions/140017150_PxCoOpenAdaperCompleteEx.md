# PxCoOpenAdaperCompleteEx

- ea: `0x140017150`
- end: `0x1400171c7`
- name: `PxCoOpenAdaperCompleteEx`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001c0c`
- `0x140017150`

## import_xrefs

- `NDIS!NdisSetEvent` at `0x1400171af`
- `NDIS!NdisSetEvent` at `0x1400171af`

## pseudocode

```c
void __fastcall PxCoOpenAdaperCompleteEx(_DWORD *a1, int a2)
{
  _DWORD *v4; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids, a1, a2);
  v4 = a1 - 4;
  if ( *a1 != 538996035 )
    v4 = a1;
  v4[136] = a2;
  NdisSetEvent((PNDIS_EVENT)(v4 + 130));
}

```

## disassembly

```asm
0x140017150  mov     [rsp+arg_0], rbx
0x140017155  push    rdi
0x140017156  sub     rsp, 30h
0x14001715a  mov     edi, edx
0x14001715c  mov     rbx, rcx
0x14001715f  mov     rcx, cs:WPP_GLOBAL_Control
0x140017166  lea     rax, WPP_GLOBAL_Control
0x14001716d  cmp     rcx, rax
0x140017170  jz      short loc_140017194
0x140017172  cmp     byte ptr [rcx+29h], 5
0x140017176  jb      short loc_140017194
0x140017178  mov     rcx, [rcx+18h]
0x14001717c  lea     r8, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids
0x140017183  mov     edx, 17h
0x140017188  mov     [rsp+38h+var_18], edi
0x14001718c  mov     r9, rbx
0x14001718f  call    WPP_SF_qD
0x140017194  cmp     dword ptr [rbx], 20206D43h
0x14001719a  lea     rcx, [rbx-10h]
0x14001719e  cmovnz  rcx, rbx
0x1400171a2  mov     [rcx+220h], edi
0x1400171a8  add     rcx, 208h; Event
0x1400171af  call    cs:__imp_NdisSetEvent
0x1400171b6  nop     dword ptr [rax+rax+00h]
0x1400171bb  mov     rbx, [rsp+38h+arg_0]
0x1400171c0  add     rsp, 30h
0x1400171c4  pop     rdi
0x1400171c5  retn
```
