# MRxSmbStart

- ea: `0x1400328a0`
- end: `0x1400329a9`
- name: `MRxSmbStart`
- size: `265`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000dfd8`
- `0x14000f7e8`
- `0x140011bc0`
- `0x1400328a0`

## import_xrefs

- `ntoskrnl!MmResetDriverPaging` at `0x1400328ad`
- `ntoskrnl!MmResetDriverPaging` at `0x1400328ad`
- `ntoskrnl!KeInitializeEvent` at `0x1400328c5`
- `ntoskrnl!KeInitializeEvent` at `0x1400328c5`
- `ksecdd!InitSecurityInterfaceW` at `0x140032905`
- `ksecdd!InitSecurityInterfaceW` at `0x140032905`

## pseudocode

```c
__int64 MRxSmbStart()
{
  unsigned int v0; // ebx
  PDEVICE_OBJECT v1; // rcx
  __int64 v2; // rdx
  __int64 v3; // r9

  MmResetDriverPaging(MRxSmbStart);
  KeInitializeEvent(&Object, NotificationEvent, 0);
  qword_140020650 = (__int64)&qword_140020648;
  qword_140020648 = (__int64)&qword_140020648;
  SmbCeStartStopContext = 1;
  Event = 0;
  if ( !MRxSmbSecurityInitialized )
  {
    if ( !InitSecurityInterfaceW() )
    {
      v0 = -1073741811;
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
        goto LABEL_12;
      }
      v2 = 17;
      v3 = 3221225485LL;
      goto LABEL_11;
    }
    MRxSmbSecurityInitialized = 1;
  }
  v0 = MRxSmbInitializeRecurrentServices();
  if ( (v0 & 0x80000000) == 0 )
  {
    *((_QWORD *)WPP_MAIN_CB.Queue.Wcb.DeviceObject + 13) = 0;
    return v0;
  }
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
  {
    v2 = 18;
    v3 = v0;
LABEL_11:
    WPP_SF_d(v1->AttachedDevice, v2, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids, v3);
  }
LABEL_12:
  SmbCeDbStop();
  return v0;
}

```

## disassembly

```asm
0x1400328a0  push    rbx
0x1400328a2  sub     rsp, 20h
0x1400328a6  lea     rcx, MRxSmbStart; AddressWithinSection
0x1400328ad  call    cs:__imp_MmResetDriverPaging
0x1400328b4  nop     dword ptr [rax+rax+00h]
0x1400328b9  xor     r8d, r8d; State
0x1400328bc  lea     rcx, Object; Event
0x1400328c3  xor     edx, edx; Type
0x1400328c5  call    cs:__imp_KeInitializeEvent
0x1400328cc  nop     dword ptr [rax+rax+00h]
0x1400328d1  cmp     cs:MRxSmbSecurityInitialized, 0
0x1400328d8  lea     rax, qword_140020648
0x1400328df  mov     cs:qword_140020650, rax
0x1400328e6  mov     cs:qword_140020648, rax
0x1400328ed  mov     cs:SmbCeStartStopContext, 1
0x1400328f8  mov     cs:Event, 0
0x140032903  jnz     short loc_14003291D
0x140032905  call    cs:__imp_InitSecurityInterfaceW
0x14003290c  nop     dword ptr [rax+rax+00h]
0x140032911  test    rax, rax
0x140032914  jz      short loc_14003294E
0x140032916  mov     cs:MRxSmbSecurityInitialized, 1
0x14003291d  call    MRxSmbInitializeRecurrentServices
0x140032922  mov     ebx, eax
0x140032924  test    eax, eax
0x140032926  jns     short loc_140032991
0x140032928  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003292f  lea     rax, WPP_GLOBAL_Control
0x140032936  cmp     rcx, rax
0x140032939  jz      short loc_14003298A
0x14003293b  test    dword ptr [rcx+2Ch], 100h
0x140032942  jz      short loc_14003298A
0x140032944  mov     edx, 12h
0x140032949  mov     r9d, ebx
0x14003294c  jmp     short loc_14003297A
0x14003294e  mov     ebx, 0C000000Dh
0x140032953  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003295a  lea     rax, WPP_GLOBAL_Control
0x140032961  cmp     rcx, rax
0x140032964  jz      short loc_14003298A
0x140032966  test    dword ptr [rcx+2Ch], 100h
0x14003296d  jz      short loc_14003298A
0x14003296f  mov     edx, 11h
0x140032974  mov     r9d, 0C000000Dh
0x14003297a  mov     rcx, [rcx+18h]
0x14003297e  lea     r8, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids
0x140032985  call    WPP_SF_d
0x14003298a  call    SmbCeDbStop
0x14003298f  jmp     short loc_1400329A0
0x140032991  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x140032998  mov     qword ptr [rax+68h], 0
0x1400329a0  mov     eax, ebx
0x1400329a2  add     rsp, 20h
0x1400329a6  pop     rbx
0x1400329a7  retn
```
