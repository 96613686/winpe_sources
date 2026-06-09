# LauncherGetFirmwareType(_FIRMWARE_TYPE *)

- ea: `0x1800075fc`
- end: `0x1800077f0`
- name: `?LauncherGetFirmwareType@@YAHPEAW4_FIRMWARE_TYPE@@@Z`
- size: `500`
- prototype: `__int64 __fastcall(enum _FIRMWARE_TYPE *)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180005a68`
- `0x180005c98`
- `0x1800070ec`

## callees

- `0x180005528`
- `0x1800075fc`
- `0x180008ac8`
- `0x180008b30`
- `0x180008c40`
- `0x18000fe10`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180007697`
- `KERNEL32!SetLastError` at `0x18000771a`
- `KERNEL32!SetLastError` at `0x180007752`
- `KERNEL32!SetLastError` at `0x180007697`
- `KERNEL32!SetLastError` at `0x18000771a`
- `KERNEL32!SetLastError` at `0x180007752`
- `ntdll!NtQuerySystemInformation` at `0x1800076ce`
- `ntdll!NtQuerySystemInformation` at `0x1800076ce`
- `ntdll!RtlNtStatusToDosError` at `0x180007712`
- `ntdll!RtlNtStatusToDosError` at `0x180007712`

## string_xrefs

- `0x18000767b`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x1800076f0`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x180007791`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`

## pseudocode

```c
__int64 __fastcall LauncherGetFirmwareType(enum _FIRMWARE_TYPE *a1)
{
  _QWORD *v2; // rcx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  NTSTATUS v5; // eax
  NTSTATUS v6; // edi
  DWORD v7; // eax
  _QWORD *v9; // rcx
  const char *v10; // rax
  _OWORD SystemInformation[2]; // [rsp+30h] [rbp-58h] BYREF

  memset(SystemInformation, 0, sizeof(SystemInformation));
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 )
      WPP_SF_sd(
        v2[2],
        11,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        159);
    SetLastError(0x57u);
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      return 0;
    v4 = 12;
LABEL_18:
    WPP_SF_(v3[2], v4, &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids);
    return 0;
  }
  v5 = NtQuerySystemInformation(SystemBootEnvironmentInformation, SystemInformation, 0x20u, 0);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        172,
        v5,
        SystemInformation[0]);
    v7 = RtlNtStatusToDosError(v6);
    SetLastError(v7);
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      return 0;
    v4 = 14;
    goto LABEL_18;
  }
  *a1 = SystemInformation[1];
  SetLastError(0);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      if ( *a1 == FirmwareTypeBios )
      {
        v10 = "PCAT";
      }
      else
      {
        v10 = "UEFI";
        if ( *a1 != FirmwareTypeUefi )
          v10 = "UNKNOWN";
      }
      WPP_SF_sds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        181,
        (__int64)v10);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 )
      WPP_SF_(v9[2], 16, &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids);
  }
  return 1;
}

```

## disassembly

```asm
0x1800075fc  push    rbx
0x1800075fe  push    rbp
0x1800075ff  push    rsi
0x180007600  push    rdi
0x180007601  sub     rsp, 68h
0x180007605  mov     rax, cs:__security_cookie
0x18000760c  xor     rax, rsp
0x18000760f  mov     [rsp+88h+var_38], rax
0x180007614  xorps   xmm0, xmm0
0x180007617  mov     [rsp+88h+SystemInformation], 0
0x18000761f  movups  [rsp+88h+var_54], xmm0
0x180007624  mov     rbx, rcx
0x180007627  movups  [rsp+88h+var_54+0Ch], xmm0
0x18000762c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007633  lea     rsi, WPP_GLOBAL_Control
0x18000763a  lea     rbp, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x180007641  cmp     rcx, rsi
0x180007644  jz      short loc_180007664
0x180007646  test    byte ptr [rcx+1Ch], 8
0x18000764a  jz      short loc_180007664
0x18000764c  mov     rcx, [rcx+10h]
0x180007650  mov     edx, 0Ah
0x180007655  mov     r8, rbp
0x180007658  call    WPP_SF_
0x18000765d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007664  test    rbx, rbx
0x180007667  jnz     short loc_1800076BE
0x180007669  cmp     rcx, rsi
0x18000766c  jz      short loc_180007692
0x18000766e  test    byte ptr [rcx+1Ch], 1
0x180007672  jz      short loc_180007692
0x180007674  mov     rcx, [rcx+10h]
0x180007678  lea     edx, [rbx+0Bh]
0x18000767b  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180007682  mov     [rsp+88h+var_68], 9Fh
0x18000768a  mov     r8, rbp
0x18000768d  call    WPP_SF_sd
0x180007692  mov     ecx, 57h ; 'W'; dwErrCode
0x180007697  call    cs:__imp_SetLastError
0x18000769d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076a4  cmp     rcx, rsi
0x1800076a7  jz      loc_180007743
0x1800076ad  test    byte ptr [rcx+1Ch], 8
0x1800076b1  jz      loc_180007743
0x1800076b7  mov     edx, 0Ch
0x1800076bc  jmp     short loc_180007737
0x1800076be  xor     r9d, r9d; ReturnLength
0x1800076c1  lea     rdx, [rsp+88h+SystemInformation]; SystemInformation
0x1800076c6  lea     r8d, [r9+20h]; SystemInformationLength
0x1800076ca  lea     ecx, [r9+5Ah]; SystemInformationClass
0x1800076ce  call    cs:__imp_NtQuerySystemInformation
0x1800076d4  mov     edi, eax
0x1800076d6  test    eax, eax
0x1800076d8  jns     short loc_18000774A
0x1800076da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076e1  cmp     rcx, rsi
0x1800076e4  jz      short loc_180007710
0x1800076e6  test    byte ptr [rcx+1Ch], 1
0x1800076ea  jz      short loc_180007710
0x1800076ec  mov     rcx, [rcx+10h]
0x1800076f0  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x1800076f7  mov     dword ptr [rsp+88h+var_60], eax
0x1800076fb  mov     edx, 0Dh
0x180007700  mov     r8, rbp
0x180007703  mov     [rsp+88h+var_68], 0ACh
0x18000770b  call    WPP_SF_sdD
0x180007710  mov     ecx, edi; Status
0x180007712  call    cs:__imp_RtlNtStatusToDosError
0x180007718  mov     ecx, eax; dwErrCode
0x18000771a  call    cs:__imp_SetLastError
0x180007720  mov     rcx, cs:WPP_GLOBAL_Control
0x180007727  cmp     rcx, rsi
0x18000772a  jz      short loc_180007743
0x18000772c  test    byte ptr [rcx+1Ch], 8
0x180007730  jz      short loc_180007743
0x180007732  mov     edx, 0Eh
0x180007737  mov     rcx, [rcx+10h]
0x18000773b  mov     r8, rbp
0x18000773e  call    WPP_SF_
0x180007743  xor     eax, eax
0x180007745  jmp     loc_1800077DA
0x18000774a  mov     eax, dword ptr [rsp+88h+var_54+0Ch]
0x18000774e  xor     ecx, ecx; dwErrCode
0x180007750  mov     [rbx], eax
0x180007752  call    cs:__imp_SetLastError
0x180007758  mov     rcx, cs:WPP_GLOBAL_Control
0x18000775f  cmp     rcx, rsi
0x180007762  jz      short loc_1800077D5
0x180007764  test    byte ptr [rcx+1Ch], 4
0x180007768  jz      short loc_1800077B9
0x18000776a  cmp     dword ptr [rbx], 1
0x18000776d  jnz     short loc_180007778
0x18000776f  lea     rax, aPcat; "PCAT"
0x180007776  jmp     short loc_18000778D
0x180007778  cmp     dword ptr [rbx], 2
0x18000777b  lea     rax, aUefi; "UEFI"
0x180007782  lea     rdx, aUnknown; "UNKNOWN"
0x180007789  cmovnz  rax, rdx
0x18000778d  mov     rcx, [rcx+10h]
0x180007791  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180007798  mov     [rsp+88h+var_60], rax
0x18000779d  mov     edx, 0Fh
0x1800077a2  mov     r8, rbp
0x1800077a5  mov     [rsp+88h+var_68], 0B5h
0x1800077ad  call    WPP_SF_sds
0x1800077b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077b9  cmp     rcx, rsi
0x1800077bc  jz      short loc_1800077D5
0x1800077be  test    byte ptr [rcx+1Ch], 8
0x1800077c2  jz      short loc_1800077D5
0x1800077c4  mov     rcx, [rcx+10h]
0x1800077c8  mov     edx, 10h
0x1800077cd  mov     r8, rbp
0x1800077d0  call    WPP_SF_
0x1800077d5  mov     eax, 1
0x1800077da  mov     rcx, [rsp+88h+var_38]
0x1800077df  xor     rcx, rsp; StackCookie
0x1800077e2  call    __security_check_cookie
0x1800077e7  add     rsp, 68h
0x1800077eb  pop     rdi
0x1800077ec  pop     rsi
0x1800077ed  pop     rbp
0x1800077ee  pop     rbx
0x1800077ef  retn
```
