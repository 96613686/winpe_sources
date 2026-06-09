# RfcommSetPageScanForAddress

- ea: `0x140003330`
- end: `0x1400035c6`
- name: `RfcommSetPageScanForAddress`
- size: `662`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006470`
- `0x1400085a0`

## callees

- `0x140003330`
- `0x140003bf4`
- `0x140003cb4`
- `0x1400049c0`
- `0x14001a2f8`
- `0x14001a3a8`
- `0x14001e74c`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003453`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003453`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400033fc`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400033fc`
- `ntoskrnl!IofCallDriver` at `0x140003566`
- `ntoskrnl!IofCallDriver` at `0x140003566`

## string_xrefs

- `0x1400033d9`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\io.c`
- `0x1400034ef`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\io.c`
- `0x14000350b`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\io.c`

## pseudocode

```c
__int64 __fastcall RfcommSetPageScanForAddress(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  NTSTATUS v8; // ebx
  int v9; // r8d
  __int64 v10; // rcx
  __int64 v11; // rdx
  IRP *v12; // r12
  _OWORD *v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  signed __int32 v18[8]; // [rsp+0h] [rbp-78h] BYREF
  ULONG RemlockSize[2]; // [rsp+20h] [rbp-58h]
  _OWORD *v20; // [rsp+28h] [rbp-50h]
  int v21; // [rsp+30h] [rbp-48h]
  int v22; // [rsp+38h] [rbp-40h]
  void *v23; // [rsp+40h] [rbp-38h]
  _OWORD *v24; // [rsp+48h] [rbp-30h]
  _OWORD *v25; // [rsp+88h] [rbp+10h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_l(WPP_GLOBAL_Control->DeviceExtension, a2, a3, a4, RemlockSize[0], a4);
  v25 = 0;
  _InterlockedOr(v18, 0);
  if ( *(_DWORD *)(a2 + 220) && a4 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        3,
        108,
        (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids);
    goto LABEL_7;
  }
  if ( *(_DWORD *)(a2 + 220) || a4 )
  {
LABEL_7:
    v8 = IoAcquireRemoveLockEx(
           (PIO_REMOVE_LOCK)(*(_QWORD *)(a2 + 80) + 40LL),
           RfcommSetPageScanForAddress,
           "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\io.c",
           0xA5Fu,
           0x20u);
    if ( v8 >= 0 )
    {
      v10 = *(_QWORD *)(a2 + 80);
      RemlockSize[0] = 32;
      v11 = *(_QWORD *)(v10 + 88);
      LOBYTE(v11) = *(_BYTE *)(v11 + 76);
      v12 = (IRP *)IrpAllocateWithContextEx(*(_QWORD *)(v10 + 80), v11, v9, (unsigned int)&v25, 32);
      if ( v12 )
      {
        v13 = v25;
        *v25 = 0;
        v13[1] = 0;
        *(_BYTE *)v13 = 2;
        *((_BYTE *)v13 + 1) = a4;
        *((_QWORD *)v13 + 2) = a2;
        *((_QWORD *)v13 + 1) = a1;
        if ( a3 )
        {
          *((_QWORD *)v13 + 3) = a3;
          *(_BYTE *)(*(_QWORD *)(a3 + 184) + 3LL) |= 1u;
        }
        RefObj_AddRefEx(a1 + 24, 542134857, 2681, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\io.c");
        RefObj_AddRefEx(a2 + 24, 542134857, 2682, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\io.c");
        v14 = *(_QWORD *)(a2 + 80);
        v24 = v13;
        v23 = &RfcommSendPageScanCompletionRoutine;
        v22 = 0;
        v15 = *(_QWORD *)(v14 + 80);
        v16 = *(_QWORD *)(v14 + 88);
        v21 = 4;
        v20 = v13;
        RemlockSize[0] = 4263968;
        IrpBuildIoctlEx(v16, v15, v12);
        IofCallDriver(*(PDEVICE_OBJECT *)(*(_QWORD *)(a2 + 80) + 88LL), v12);
        v8 = 259;
      }
      else
      {
        v8 = -1073741670;
        IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(*(_QWORD *)(a2 + 80) + 40LL), RfcommSetPageScanForAddress, 0x20u);
      }
    }
    goto LABEL_18;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      109,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids);
  v8 = 0;
LABEL_18:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      110,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
      v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140003330  mov     [rsp+arg_0], rbx
0x140003335  mov     [rsp+arg_10], rbp
0x14000333a  push    rsi
0x14000333b  push    rdi
0x14000333c  push    r12
0x14000333e  push    r14
0x140003340  push    r15
0x140003342  sub     rsp, 50h
0x140003346  movzx   esi, r9b
0x14000334a  mov     r14, r8
0x14000334d  mov     rdi, rdx
0x140003350  mov     r15, rcx
0x140003353  lea     rcx, WPP_RECORDER_INITIALIZED
0x14000335a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140003361  jz      short loc_14000337E
0x140003363  mov     rcx, cs:WPP_GLOBAL_Control
0x14000336a  mov     dword ptr [rsp+78h+var_50], esi
0x14000336e  mov     rcx, [rcx+40h]
0x140003372  call    WPP_RECORDER_SF_l
0x140003377  lea     rcx, WPP_RECORDER_INITIALIZED
0x14000337e  mov     [rsp+78h+arg_8], 0
0x14000338a  lock or [rsp+78h+var_78], 0
0x14000338f  mov     eax, [rdi+0DCh]
0x140003395  lea     rbp, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x14000339c  test    eax, eax
0x14000339e  jz      loc_140003464
0x1400033a4  test    sil, sil
0x1400033a7  jz      loc_140003464
0x1400033ad  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400033b4  jz      short loc_1400033D5
0x1400033b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400033bd  mov     r9d, 6Ch ; 'l'
0x1400033c3  mov     qword ptr [rsp+78h+RemlockSize], rbp
0x1400033c8  mov     rcx, [rcx+40h]
0x1400033cc  lea     r8d, [r9-69h]
0x1400033d0  call    WPP_RECORDER_SF_
0x1400033d5  mov     rcx, [rdi+50h]
0x1400033d9  lea     r8, File; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400033e0  mov     r12d, 20h ; ' '
0x1400033e6  lea     rdx, RfcommSetPageScanForAddress; Tag
0x1400033ed  add     rcx, 28h ; '('; RemoveLock
0x1400033f1  mov     [rsp+78h+RemlockSize], r12d; RemlockSize
0x1400033f6  mov     r9d, 0A5Fh; Line
0x1400033fc  call    cs:__imp_IoAcquireRemoveLockEx
0x140003403  nop     dword ptr [rax+rax+00h]
0x140003408  mov     ebx, eax
0x14000340a  test    eax, eax
0x14000340c  js      loc_140003577
0x140003412  mov     rcx, [rdi+50h]
0x140003416  lea     r9, [rsp+78h+arg_8]
0x14000341e  mov     [rsp+78h+RemlockSize], r12d
0x140003423  mov     rdx, [rcx+58h]
0x140003427  mov     rcx, [rcx+50h]
0x14000342b  mov     dl, [rdx+4Ch]
0x14000342e  call    IrpAllocateWithContextEx
0x140003433  mov     r12, rax
0x140003436  test    rax, rax
0x140003439  jnz     short loc_1400034AF
0x14000343b  mov     rcx, [rdi+50h]
0x14000343f  lea     r8d, [rax+20h]; RemlockSize
0x140003443  add     rcx, 28h ; '('; RemoveLock
0x140003447  lea     rdx, RfcommSetPageScanForAddress; Tag
0x14000344e  mov     ebx, 0C000009Ah
0x140003453  call    cs:__imp_IoReleaseRemoveLockEx
0x14000345a  nop     dword ptr [rax+rax+00h]
0x14000345f  jmp     loc_140003577
0x140003464  mov     eax, [rdi+0DCh]
0x14000346a  test    eax, eax
0x14000346c  jnz     loc_1400033D5
0x140003472  test    sil, sil
0x140003475  jnz     loc_1400033D5
0x14000347b  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140003482  lea     rbp, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140003489  jz      short loc_1400034A8
0x14000348b  mov     rcx, cs:WPP_GLOBAL_Control
0x140003492  lea     r9d, [rax+6Dh]
0x140003496  lea     r8d, [rax+3]
0x14000349a  mov     qword ptr [rsp+78h+RemlockSize], rbp
0x14000349f  mov     rcx, [rcx+40h]
0x1400034a3  call    WPP_RECORDER_SF_
0x1400034a8  xor     ebx, ebx
0x1400034aa  jmp     loc_140003577
0x1400034af  mov     rbx, [rsp+78h+arg_8]
0x1400034b7  xorps   xmm0, xmm0
0x1400034ba  movups  xmmword ptr [rbx], xmm0
0x1400034bd  movups  xmmword ptr [rbx+10h], xmm0
0x1400034c1  mov     byte ptr [rbx], 2
0x1400034c4  mov     [rbx+1], sil
0x1400034c8  mov     [rbx+10h], rdi
0x1400034cc  mov     [rbx+8], r15
0x1400034d0  test    r14, r14
0x1400034d3  jz      short loc_1400034E4
0x1400034d5  mov     [rbx+18h], r14
0x1400034d9  mov     rax, [r14+0B8h]
0x1400034e0  or      byte ptr [rax+3], 1
0x1400034e4  mov     esi, 20505249h
0x1400034e9  lea     rcx, [r15+18h]
0x1400034ed  mov     edx, esi
0x1400034ef  lea     r9, File; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400034f6  mov     r8d, 0A79h
0x1400034fc  call    RefObj_AddRefEx
0x140003501  lea     rcx, [rdi+18h]
0x140003505  mov     r8d, 0A7Ah
0x14000350b  lea     r9, File; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140003512  mov     edx, esi
0x140003514  call    RefObj_AddRefEx
0x140003519  mov     rcx, [rdi+50h]
0x14000351d  lea     rax, RfcommSendPageScanCompletionRoutine
0x140003524  mov     [rsp+78h+var_30], rbx
0x140003529  mov     r8, r12
0x14000352c  mov     [rsp+78h+var_38], rax
0x140003531  mov     [rsp+78h+var_40], 0
0x140003539  mov     rdx, [rcx+50h]
0x14000353d  mov     rcx, [rcx+58h]
0x140003541  mov     [rsp+78h+var_48], 4
0x140003549  mov     [rsp+78h+var_50], rbx
0x14000354e  mov     [rsp+78h+RemlockSize], 411020h
0x140003556  call    IrpBuildIoctlEx
0x14000355b  mov     rcx, [rdi+50h]
0x14000355f  mov     rdx, r12; Irp
0x140003562  mov     rcx, [rcx+58h]; DeviceObject
0x140003566  call    cs:__imp_IofCallDriver
0x14000356d  nop     dword ptr [rax+rax+00h]
0x140003572  mov     ebx, 103h
0x140003577  lea     rax, WPP_RECORDER_INITIALIZED
0x14000357e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003585  jz      short loc_1400035AA
0x140003587  mov     rcx, cs:WPP_GLOBAL_Control
0x14000358e  mov     r9d, 6Eh ; 'n'
0x140003594  mov     dword ptr [rsp+78h+var_50], ebx
0x140003598  mov     qword ptr [rsp+78h+RemlockSize], rbp
0x14000359d  mov     rcx, [rcx+40h]
0x1400035a1  lea     r8d, [r9-6Bh]
0x1400035a5  call    WPP_RECORDER_SF_d
0x1400035aa  lea     r11, [rsp+78h+var_28]
0x1400035af  mov     eax, ebx
0x1400035b1  mov     rbx, [r11+30h]
0x1400035b5  mov     rbp, [r11+40h]
0x1400035b9  mov     rsp, r11
0x1400035bc  pop     r15
0x1400035be  pop     r14
0x1400035c0  pop     r12
0x1400035c2  pop     rdi
0x1400035c3  pop     rsi
0x1400035c4  retn
```
