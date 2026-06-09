# DriverEntry

- ea: `0x140045078`
- end: `0x1400453dd`
- name: `DriverEntry`
- size: `869`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x140045010`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x140006c08`
- `0x140006f00`
- `0x14002c6d0`
- `0x14002cbc0`
- `0x140042008`
- `0x1400421ec`
- `0x140042280`
- `0x140042bc4`
- `0x140045078`

## import_xrefs

- `ntoskrnl!RtlGetVersion` at `0x1400452d5`
- `ntoskrnl!RtlGetVersion` at `0x1400452d5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400451bb`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400451bb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400451d3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400451d3`
- `ntoskrnl!KeInitializeSpinLock` at `0x14004525a`
- `ntoskrnl!KeInitializeSpinLock` at `0x14004525a`
- `ntoskrnl!ExAllocatePool2` at `0x140045195`
- `ntoskrnl!ExAllocatePool2` at `0x140045195`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  ULONG v4; // edx
  ULONG v5; // r9d
  NTSTATUS v6; // eax
  unsigned int v7; // edi
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  int v10; // eax
  ULONG v12; // [rsp+20h] [rbp-E0h]
  BOOLEAN v13; // [rsp+28h] [rbp-D8h]
  const UNICODE_STRING *v14; // [rsp+30h] [rbp-D0h]
  const GUID *v15; // [rsp+38h] [rbp-C8h]
  PDEVICE_OBJECT *v16; // [rsp+40h] [rbp-C0h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE VersionInformation[284]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SourceString[16]; // [rsp+180h] [rbp+80h] BYREF

  wcscpy(SourceString, L"\\Deve\\IPNAT");
  DestinationString = 0;
  memset(VersionInformation, 0, sizeof(VersionInformation));
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_NatGuid;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids);
  }
  NatDbgInitalize();
  LOWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) = 0;
  WORD1(WPP_MAIN_CB.Queue.Wcb.DeviceContext) = RegistryPath->MaximumLength + 2;
  *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters = ExAllocatePool2(
                                                             256,
                                                             WORD1(WPP_MAIN_CB.Queue.Wcb.DeviceContext),
                                                             1834443086);
  if ( *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters )
  {
    RtlCopyUnicodeString((PUNICODE_STRING)&WPP_MAIN_CB.Queue.Wcb.DeviceContext, RegistryPath);
    RtlInitUnicodeString(&DestinationString, SourceString);
    v6 = WdmlibIoCreateDeviceSecure(DriverObject, v4, &DestinationString, v5, v12, v13, v14, v15, v16);
    v7 = v6;
    if ( v6 >= 0 )
    {
      KeInitializeSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink);
      DriverObject->DriverStartIo = 0;
      DriverObject->DriverUnload = (PDRIVER_UNLOAD)NatUnloadDriver;
      WPP_MAIN_CB.DeviceQueue.Lock = 0;
      DriverObject->FastIoDispatch = (PFAST_IO_DISPATCH)NatFastIoDispatch;
      *(_DWORD *)&WPP_MAIN_CB.DeviceQueue.Busy = 0;
      memset64(DriverObject->MajorFunction, (unsigned __int64)NatDispatch, 0x1Bu);
      NatCreateExternalNaming(&DestinationString);
      memset(&VersionInformation[4], 0, 0x118u);
      *(_DWORD *)VersionInformation = 284;
      if ( RtlGetVersion((PRTL_OSVERSIONINFOW)VersionInformation) >= 0 && VersionInformation[282] == 1 )
        IsIPxlatEnabled = 1;
      v10 = NatInitializeDriver();
      v7 = v10;
      if ( v10 < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return v7;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            23,
            WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids,
            (unsigned int)v10);
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        v9 = 24;
        goto LABEL_35;
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          21,
          WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids,
          (unsigned int)v6);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        v9 = 22;
LABEL_35:
        WPP_SF_d(v8->AttachedDevice, v9, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids, v7);
      }
    }
  }
  else
  {
    v7 = -1073741801;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids, 3221225495LL);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        v9 = 20;
        goto LABEL_35;
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x140045078  mov     [rsp-8+arg_10], rbx
0x14004507d  mov     [rsp-8+arg_18], rdi
0x140045082  push    rbp
0x140045083  push    r14
0x140045085  push    r15
0x140045087  lea     rbp, [rsp-0B0h]
0x14004508f  sub     rsp, 1B0h
0x140045096  mov     rax, cs:__security_cookie
0x14004509d  xor     rax, rsp
0x1400450a0  mov     [rbp+0C0h+var_20], rax
0x1400450a7  movups  xmm0, xmmword ptr cs:aDeviceIpnat; "\\Device\\IPNAT"
0x1400450ae  mov     rdi, rdx
0x1400450b1  mov     rbx, rcx
0x1400450b4  movups  xmm1, xmmword ptr cs:aDeviceIpnat+0Ch; "e\\IPNAT"
0x1400450bb  xor     edx, edx; Val
0x1400450bd  mov     r8d, 11Ch; Size
0x1400450c3  movups  xmmword ptr [rbp+0C0h+SourceString], xmm0
0x1400450ca  lea     rcx, [rsp+1C0h+VersionInformation]; void *
0x1400450cf  xorps   xmm0, xmm0
0x1400450d2  movups  xmmword ptr [rsp+1C0h+DestinationString.Length], xmm0
0x1400450d7  movups  xmmword ptr [rbp+0C0h+SourceString+0Ch], xmm1
0x1400450de  call    memset
0x1400450e3  lea     rax, WPP_ThisDir_CTLGUID_NatGuid
0x1400450ea  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x1400450f5  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x1400450fc  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x140045107  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x140045112  mov     cs:WPP_MAIN_CB.Timer, 1
0x14004511d  call    WppLoadTracingSupport
0x140045122  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14004512d  call    WppInitKm
0x140045132  mov     rcx, cs:WPP_GLOBAL_Control
0x140045139  lea     r14, WPP_GLOBAL_Control
0x140045140  lea     r15, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids
0x140045147  cmp     rcx, r14
0x14004514a  jz      short loc_14004516A
0x14004514c  mov     eax, [rcx+2Ch]
0x14004514f  test    al, 1
0x140045151  jz      short loc_14004516A
0x140045153  cmp     byte ptr [rcx+29h], 5
0x140045157  jb      short loc_14004516A
0x140045159  mov     rcx, [rcx+18h]
0x14004515d  mov     edx, 0Fh
0x140045162  mov     r8, r15
0x140045165  call    WPP_SF_
0x14004516a  call    NatDbgInitalize
0x14004516f  xor     eax, eax
0x140045171  mov     ecx, 100h
0x140045176  mov     word ptr cs:WPP_MAIN_CB.Queue+20h, ax
0x14004517d  mov     r8d, 6D57614Eh
0x140045183  movzx   eax, word ptr [rdi+2]
0x140045187  add     ax, 2
0x14004518b  movzx   edx, ax
0x14004518e  mov     word ptr cs:WPP_MAIN_CB.Queue+22h, dx
0x140045195  call    cs:__imp_ExAllocatePool2
0x14004519c  nop     dword ptr [rax+rax+00h]
0x1400451a1  mov     qword ptr cs:WPP_MAIN_CB.Queue+28h, rax
0x1400451a8  test    rax, rax
0x1400451ab  jz      loc_140045352
0x1400451b1  mov     rdx, rdi; SourceString
0x1400451b4  lea     rcx, WPP_MAIN_CB.Queue+20h; DestinationString
0x1400451bb  call    cs:__imp_RtlCopyUnicodeString
0x1400451c2  nop     dword ptr [rax+rax+00h]
0x1400451c7  lea     rdx, [rbp+0C0h+SourceString]; SourceString
0x1400451ce  lea     rcx, [rsp+1C0h+DestinationString]; DestinationString
0x1400451d3  call    cs:__imp_RtlInitUnicodeString
0x1400451da  nop     dword ptr [rax+rax+00h]
0x1400451df  lea     r8, [rsp+1C0h+DestinationString]; DeviceName
0x1400451e4  mov     rcx, rbx; DriverObject
0x1400451e7  call    WdmlibIoCreateDeviceSecure
0x1400451ec  mov     edi, eax
0x1400451ee  test    eax, eax
0x1400451f0  jns     short loc_140045253
0x1400451f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400451f9  cmp     rcx, r14
0x1400451fc  jz      loc_1400453B2
0x140045202  mov     edx, [rcx+2Ch]
0x140045205  test    dl, 1
0x140045208  jz      short loc_140045224
0x14004520a  cmp     byte ptr [rcx+29h], 2
0x14004520e  jb      short loc_140045224
0x140045210  mov     rcx, [rcx+18h]
0x140045214  mov     edx, 15h
0x140045219  mov     r9d, eax
0x14004521c  mov     r8, r15
0x14004521f  call    WPP_SF_d
0x140045224  mov     rcx, cs:WPP_GLOBAL_Control
0x14004522b  cmp     rcx, r14
0x14004522e  jz      loc_1400453B2
0x140045234  mov     eax, [rcx+2Ch]
0x140045237  test    al, 1
0x140045239  jz      loc_1400453B2
0x14004523f  cmp     byte ptr [rcx+29h], 6
0x140045243  jb      loc_1400453B2
0x140045249  mov     edx, 16h
0x14004524e  jmp     loc_1400453A3
0x140045253  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink; SpinLock
0x14004525a  call    cs:__imp_KeInitializeSpinLock
0x140045261  nop     dword ptr [rax+rax+00h]
0x140045266  lea     rax, NatUnloadDriver
0x14004526d  mov     qword ptr [rbx+60h], 0
0x140045275  mov     [rbx+68h], rax
0x140045279  lea     rdi, [rbx+70h]
0x14004527d  lea     rax, NatFastIoDispatch
0x140045284  mov     cs:WPP_MAIN_CB.DeviceQueue.Lock, 0
0x14004528f  mov     [rbx+50h], rax
0x140045293  mov     ecx, 1Bh
0x140045298  lea     rax, NatDispatch
0x14004529f  mov     dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, 0
0x1400452a9  rep stosq
0x1400452ac  lea     rcx, [rsp+1C0h+DestinationString]; DeviceName
0x1400452b1  call    NatCreateExternalNaming
0x1400452b6  xor     edx, edx; Val
0x1400452b8  lea     rcx, [rsp+1C0h+VersionInformation.dwMajorVersion]; void *
0x1400452bd  mov     r8d, 118h; Size
0x1400452c3  call    memset
0x1400452c8  lea     rcx, [rsp+1C0h+VersionInformation]; lpVersionInformation
0x1400452cd  mov     [rsp+1C0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1400452d5  call    cs:__imp_RtlGetVersion
0x1400452dc  nop     dword ptr [rax+rax+00h]
0x1400452e1  test    eax, eax
0x1400452e3  js      short loc_1400452F5
0x1400452e5  cmp     [rbp+0C0h+var_46], 1
0x1400452e9  jnz     short loc_1400452F5
0x1400452eb  mov     cs:IsIPxlatEnabled, 1
0x1400452f5  call    NatInitializeDriver
0x1400452fa  mov     edi, eax
0x1400452fc  test    eax, eax
0x1400452fe  jns     short loc_140045332
0x140045300  mov     rcx, cs:WPP_GLOBAL_Control
0x140045307  cmp     rcx, r14
0x14004530a  jz      loc_1400453B2
0x140045310  mov     edx, [rcx+2Ch]
0x140045313  test    dl, 1
0x140045316  jz      short loc_140045332
0x140045318  cmp     byte ptr [rcx+29h], 2
0x14004531c  jb      short loc_140045332
0x14004531e  mov     rcx, [rcx+18h]
0x140045322  mov     edx, 17h
0x140045327  mov     r9d, eax
0x14004532a  mov     r8, r15
0x14004532d  call    WPP_SF_d
0x140045332  mov     rcx, cs:WPP_GLOBAL_Control
0x140045339  cmp     rcx, r14
0x14004533c  jz      short loc_1400453B2
0x14004533e  mov     eax, [rcx+2Ch]
0x140045341  test    al, 1
0x140045343  jz      short loc_1400453B2
0x140045345  cmp     byte ptr [rcx+29h], 6
0x140045349  jb      short loc_1400453B2
0x14004534b  mov     edx, 18h
0x140045350  jmp     short loc_1400453A3
0x140045352  mov     rcx, cs:WPP_GLOBAL_Control
0x140045359  mov     edi, 0C0000017h
0x14004535e  cmp     rcx, r14
0x140045361  jz      short loc_1400453B2
0x140045363  mov     eax, [rcx+2Ch]
0x140045366  test    al, 1
0x140045368  jz      short loc_140045384
0x14004536a  cmp     byte ptr [rcx+29h], 2
0x14004536e  jb      short loc_140045384
0x140045370  mov     rcx, [rcx+18h]
0x140045374  mov     edx, 13h
0x140045379  mov     r9d, edi
0x14004537c  mov     r8, r15
0x14004537f  call    WPP_SF_d
0x140045384  mov     rcx, cs:WPP_GLOBAL_Control
0x14004538b  cmp     rcx, r14
0x14004538e  jz      short loc_1400453B2
0x140045390  mov     edx, [rcx+2Ch]
0x140045393  test    dl, 1
0x140045396  jz      short loc_1400453B2
0x140045398  cmp     byte ptr [rcx+29h], 6
0x14004539c  jb      short loc_1400453B2
0x14004539e  mov     edx, 14h
0x1400453a3  mov     rcx, [rcx+18h]
0x1400453a7  mov     r9d, edi
0x1400453aa  mov     r8, r15
0x1400453ad  call    WPP_SF_d
0x1400453b2  mov     eax, edi
0x1400453b4  mov     rcx, [rbp+0C0h+var_20]
0x1400453bb  xor     rcx, rsp; StackCookie
0x1400453be  call    __security_check_cookie
0x1400453c3  lea     r11, [rsp+1C0h+var_10]
0x1400453cb  mov     rbx, [r11+30h]
0x1400453cf  mov     rdi, [r11+38h]
0x1400453d3  mov     rsp, r11
0x1400453d6  pop     r15
0x1400453d8  pop     r14
0x1400453da  pop     rbp
0x1400453db  retn
```
