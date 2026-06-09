# ux::CLauncherMainTaskDialog::GetContentText(void)

- ea: `0x180009f4c`
- end: `0x18000a142`
- name: `?GetContentText@CLauncherMainTaskDialog@ux@@AEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ`
- size: `502`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callers

- `0x18000946c`

## callees

- `0x180002148`
- `0x18000253c`
- `0x180008b30`
- `0x180009e04`
- `0x180009f4c`
- `0x18000a280`
- `0x18000e948`
- `0x18000eb10`
- `0x18000ee48`
- `0x180011010`

## string_xrefs

- `0x18000a0b0`: `drivers\wdm\usbpw\launcher\dll\claunchermaintaskdialog.cpp`
- `0x18000a10c`: `drivers\wdm\usbpw\launcher\dll\claunchermaintaskdialog.cpp`

## pseudocode

```c
_QWORD *__fastcall ux::CLauncherMainTaskDialog::GetContentText(__int64 a1, _QWORD *a2)
{
  enum _FIRMWARE_TYPE Firmware; // eax
  unsigned int OperatingSystemArchitecture; // eax
  __int64 v5; // rdx
  __int64 v11; // rbx
  _QWORD *v12; // rdx
  __int64 pExceptionObject; // [rsp+70h] [rbp+20h] BYREF
  _QWORD *v15; // [rsp+78h] [rbp+28h]
  __int64 v16; // [rsp+80h] [rbp+30h] BYREF
  __int64 v17; // [rsp+88h] [rbp+38h] BYREF

  v15 = a2;
  pExceptionObject = a1;
  Firmware = utils::CMachine::GetFirmware();
  if ( Firmware == FirmwareTypeUefi )
  {
    OperatingSystemArchitecture = utils::CMachine::GetOperatingSystemArchitecture();
    if ( OperatingSystemArchitecture == 9 )
    {
      v5 = 224;
      goto LABEL_8;
    }
    if ( !OperatingSystemArchitecture )
    {
      v5 = 223;
      goto LABEL_8;
    }
LABEL_18:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)&WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\claunchermaintaskdialog.cpp",
        151);
    ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, -2147467259);
    throw (ATL::CAtlException *)&pExceptionObject;
  }
  if ( Firmware != FirmwareTypeBios )
    goto LABEL_18;
  _RAX = 2147483649LL;
  __asm { cpuid }
  v5 = (_RDX & 0x20000000) != 0 ? 225 : 223;
LABEL_8:
  utils::CBranding::Format(&v17, v5);
  v16 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
                        &v16,
                        226) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)&WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\claunchermaintaskdialog.cpp",
        155);
    ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, -2147467259);
    throw (ATL::CAtlException *)&pExceptionObject;
  }
  *a2 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v11 = v16;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::FormatMessageW(
    a2,
    212,
    v17,
    v16);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v11 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v11 - 24) + 8LL))(*(_QWORD *)(v11 - 24));
  v12 = (_QWORD *)(v17 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v17 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v12 + 8LL))(*v12);
  return a2;
}

```

## disassembly

```asm
0x180009f4c  mov     [rsp-18h+arg_8], rdx
0x180009f51  mov     [rsp-18h+pExceptionObject], rcx
0x180009f56  push    rbp
0x180009f57  push    rbx
0x180009f58  push    rdi
0x180009f59  mov     rbp, rsp
0x180009f5c  sub     rsp, 50h
0x180009f60  mov     rdi, rdx
0x180009f63  mov     [rbp+var_20], 0
0x180009f6a  call    ?GetFirmware@CMachine@utils@@SA?AW4_FIRMWARE_TYPE@@XZ; utils::CMachine::GetFirmware(void)
0x180009f6f  cmp     eax, 2
0x180009f72  jnz     short loc_180009F94
0x180009f74  call    ?GetOperatingSystemArchitecture@CMachine@utils@@SAKXZ; utils::CMachine::GetOperatingSystemArchitecture(void)
0x180009f79  cmp     eax, 9
0x180009f7c  jnz     short loc_180009F85
0x180009f7e  mov     edx, 0E0h
0x180009f83  jmp     short loc_180009FBA
0x180009f85  test    eax, eax
0x180009f87  jnz     loc_18000A0E6
0x180009f8d  mov     edx, 0DFh
0x180009f92  jmp     short loc_180009FBA
0x180009f94  cmp     eax, 1
0x180009f97  jnz     loc_18000A0E6
0x180009f9d  mov     eax, 80000001h
0x180009fa2  xor     ecx, ecx
0x180009fa4  cpuid
0x180009fa6  and     edx, 20000000h
0x180009fac  neg     edx
0x180009fae  sbb     eax, eax
0x180009fb0  and     eax, 2
0x180009fb3  mov     edx, 0DFh
0x180009fb8  add     edx, eax
0x180009fba  lea     rcx, [rbp+arg_18]
0x180009fbe  call    ?Format@CBranding@utils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@I@Z; utils::CBranding::Format(uint)
0x180009fc3  nop
0x180009fc4  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180009fcb  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180009fd2  mov     rax, [rax+18h]
0x180009fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fdb  add     rax, 18h
0x180009fdf  mov     [rbp+arg_10], rax
0x180009fe3  mov     edx, 0E2h
0x180009fe8  lea     rcx, [rbp+arg_10]
0x180009fec  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)
0x180009ff1  test    eax, eax
0x180009ff3  jz      loc_18000A08A
0x180009ff9  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000a000  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000a007  mov     rax, [rax+18h]
0x18000a00b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a010  add     rax, 18h
0x18000a014  mov     [rdi], rax
0x18000a017  mov     [rbp+var_20], 1
0x18000a01e  mov     rbx, [rbp+arg_10]
0x18000a022  mov     r9, rbx
0x18000a025  mov     r8, [rbp+arg_18]
0x18000a029  mov     edx, 0D4h
0x18000a02e  mov     rcx, rdi
0x18000a031  call    ?FormatMessageW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXIZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::FormatMessageW(uint,...)
0x18000a036  nop
0x18000a037  lea     rdx, [rbx-18h]
0x18000a03b  or      ebx, 0FFFFFFFFh
0x18000a03e  mov     eax, ebx
0x18000a040  lock xadd [rdx+10h], eax
0x18000a045  add     eax, ebx
0x18000a047  test    eax, eax
0x18000a049  jg      short loc_18000A05B
0x18000a04b  mov     rcx, [rdx]
0x18000a04e  mov     rax, [rcx]
0x18000a051  mov     rax, [rax+8]
0x18000a055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a05a  nop
0x18000a05b  mov     rdx, [rbp+arg_18]
0x18000a05f  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000a063  mov     eax, ebx
0x18000a065  lock xadd [rdx+10h], eax
0x18000a06a  add     eax, ebx
0x18000a06c  test    eax, eax
0x18000a06e  jg      short loc_18000A07F
0x18000a070  mov     rcx, [rdx]
0x18000a073  mov     rax, [rcx]
0x18000a076  mov     rax, [rax+8]
0x18000a07a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a07f  mov     rax, rdi
0x18000a082  add     rsp, 50h
0x18000a086  pop     rdi
0x18000a087  pop     rbx
0x18000a088  pop     rbp
0x18000a089  retn
0x18000a08a  lea     rax, WPP_GLOBAL_Control
0x18000a091  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a098  cmp     rcx, rax
0x18000a09b  jz      short loc_18000A0C7
0x18000a09d  test    byte ptr [rcx+1Ch], 1
0x18000a0a1  jz      short loc_18000A0C7
0x18000a0a3  mov     edx, 0Eh
0x18000a0a8  mov     [rsp+50h+var_30], 9Bh
0x18000a0b0  lea     r9, aDriversWdmUsbp_2; "drivers\\wdm\\usbpw\\launcher\\dll\\cla"...
0x18000a0b7  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x18000a0be  mov     rcx, [rcx+10h]
0x18000a0c2  call    WPP_SF_sd
0x18000a0c7  mov     edx, 80004005h; int
0x18000a0cc  lea     rcx, [rbp+pExceptionObject]; this
0x18000a0d0  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000a0d5  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000a0dc  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000a0e0  call    _CxxThrowException_0
0x18000a0e6  lea     rax, WPP_GLOBAL_Control
0x18000a0ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a0f4  cmp     rcx, rax
0x18000a0f7  jz      short loc_18000A123
0x18000a0f9  test    byte ptr [rcx+1Ch], 1
0x18000a0fd  jz      short loc_18000A123
0x18000a0ff  mov     edx, 0Dh
0x18000a104  mov     [rsp+50h+var_30], 97h
0x18000a10c  lea     r9, aDriversWdmUsbp_2; "drivers\\wdm\\usbpw\\launcher\\dll\\cla"...
0x18000a113  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x18000a11a  mov     rcx, [rcx+10h]
0x18000a11e  call    WPP_SF_sd
0x18000a123  mov     edx, 80004005h; int
0x18000a128  lea     rcx, [rbp+pExceptionObject]; this
0x18000a12c  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000a131  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000a138  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000a13c  call    _CxxThrowException_0
```
