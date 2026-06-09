# ndisWdfOpenConfigurationKey

- ea: `0x140160460`
- end: `0x14016082c`
- name: `ndisWdfOpenConfigurationKey`
- size: `972`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x14008c350`
- `0x140136a20`

## callees

- `0x14001cf50`
- `0x14001d030`
- `0x14006a270`
- `0x14006f040`
- `0x14008c714`
- `0x1400e6160`
- `0x140160460`
- `0x140161cd0`
- `0x140162120`
- `0x1401621d0`

## import_xrefs

- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1401605a8`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1401605a8`
- `ntoskrnl!ZwClose` at `0x14016050b`
- `ntoskrnl!ZwClose` at `0x14016060b`
- `ntoskrnl!ZwClose` at `0x1401607c3`
- `ntoskrnl!ZwClose` at `0x1401607e9`
- `ntoskrnl!ZwClose` at `0x1401607ff`
- `ntoskrnl!ZwClose` at `0x14016050b`
- `ntoskrnl!ZwClose` at `0x14016060b`
- `ntoskrnl!ZwClose` at `0x1401607c3`
- `ntoskrnl!ZwClose` at `0x1401607e9`
- `ntoskrnl!ZwClose` at `0x1401607ff`

## pseudocode

```c
__int64 __fastcall ndisWdfOpenConfigurationKey(__int64 a1, void **a2)
{
  unsigned int *v2; // r12
  unsigned int v5; // eax
  int v6; // edx
  unsigned int v7; // ebx
  unsigned int Uint32; // eax
  int v10; // edx
  struct _DEVICE_OBJECT *v11; // rcx
  int v12; // edx
  int v13; // r9d
  unsigned int v14; // eax
  int v15; // edx
  int v16; // r8d
  int v17; // r9d
  struct _GUID *v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  char v20[8]; // [rsp+28h] [rbp-D8h]
  char v21[8]; // [rsp+30h] [rbp-D0h]
  void *DeviceRegKey; // [rsp+70h] [rbp-90h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp-88h] BYREF
  char v24[4]; // [rsp+80h] [rbp-80h] BYREF
  HANDLE p_Handle; // [rsp+88h] [rbp-78h] BYREF
  HANDLE *v26; // [rsp+90h] [rbp-70h]
  wchar_t v27[56]; // [rsp+A0h] [rbp-60h] BYREF

  v2 = (unsigned int *)(a1 + 4008);
  v26 = a2;
  Handle = 0;
  v5 = ndisIfOpenInterfaceRegistryKey(a1 + 4008, (KRegKey *)&Handle, 1u, 1);
  v7 = v5;
  if ( v5 )
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_q_guid_d(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v6,
        8,
        10,
        (struct _GUID *)&WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids,
        a1,
        (__int64)v2,
        v5);
    }
LABEL_4:
    if ( Handle )
      ZwClose(Handle);
    return v7;
  }
  *(_DWORD *)v24 = 0;
  p_Handle = &Handle;
  Uint32 = NetSetupPropertyBag::ReadUint32(
             (NetSetupPropertyBag *)&p_Handle,
             (const struct _NETSETUPPROPKEY *)NETSETUPPKEY_Interface_PnpDeviceInterfaceNumber,
             (unsigned int *)v24);
  v7 = Uint32;
  if ( Uint32 )
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v10,
        8,
        11,
        (struct _GUID *)&WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids,
        a1,
        Uint32);
    }
    goto LABEL_4;
  }
  v11 = *(struct _DEVICE_OBJECT **)(a1 + 3832);
  DeviceRegKey = 0;
  v7 = IoOpenDeviceRegistryKey(v11, 2u, 0xC2000000, &DeviceRegKey);
  if ( v7 )
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_14;
    v13 = 12;
    goto LABEL_13;
  }
  if ( *(_DWORD *)v24 )
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 4;
      WPP_RECORDER_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v12,
        8,
        14,
        (struct _GUID *)&WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids,
        a1,
        v24[0]);
    }
    *(_DWORD *)v21 = *((unsigned __int8 *)v2 + 8);
    *(_DWORD *)v20 = *((unsigned __int16 *)v2 + 3);
    LODWORD(v18) = *((unsigned __int16 *)v2 + 2);
    v7 = RtlStringCbPrintfW(
           v27,
           0x70u,
           L"NetworkInterface\\{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
           *v2,
           v18,
           *(_QWORD *)v20,
           *(_QWORD *)v21,
           *((unsigned __int8 *)v2 + 9),
           *((unsigned __int8 *)v2 + 10),
           *((unsigned __int8 *)v2 + 11),
           *((unsigned __int8 *)v2 + 12),
           *((unsigned __int8 *)v2 + 13),
           *((unsigned __int8 *)v2 + 14),
           *((unsigned __int8 *)v2 + 15));
    if ( v7 )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      {
LABEL_14:
        if ( DeviceRegKey )
          ZwClose(DeviceRegKey);
        goto LABEL_4;
      }
      v13 = 15;
LABEL_13:
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v12,
        8,
        v13,
        (struct _GUID *)&WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids,
        a1,
        v7);
      goto LABEL_14;
    }
    p_Handle = 0;
    v14 = KRegKey::Open((KRegKey *)&p_Handle, 0xC2000000, v27, DeviceRegKey);
    v7 = v14;
    if ( v14 )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qSd(*((_QWORD *)WPP_GLOBAL_Control + 8), v15, v16, v17, v19, a1, (__int64)v27, v14);
      if ( p_Handle )
        ZwClose(p_Handle);
      goto LABEL_14;
    }
    *v26 = p_Handle;
    if ( DeviceRegKey )
      ZwClose(DeviceRegKey);
  }
  else
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 4;
      WPP_RECORDER_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v12,
        8,
        13,
        (struct _GUID *)&WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids,
        a1);
    }
    *a2 = DeviceRegKey;
    DeviceRegKey = 0;
  }
  if ( Handle )
    ZwClose(Handle);
  return 0;
}

```

## disassembly

```asm
0x140160460  push    rbp
0x140160462  push    rbx
0x140160463  push    rsi
0x140160464  push    rdi
0x140160465  push    r12
0x140160467  push    r13
0x140160469  push    r15
0x14016046b  lea     rbp, [rsp-20h]
0x140160470  sub     rsp, 120h
0x140160477  mov     rax, cs:__security_cookie
0x14016047e  xor     rax, rsp
0x140160481  mov     [rbp+50h+var_40], rax
0x140160485  lea     r12, [rcx+0FA8h]
0x14016048c  mov     [rbp+50h+var_C0], rdx
0x140160490  mov     r9d, 1; char
0x140160496  mov     rdi, rdx
0x140160499  mov     r13, rcx
0x14016049c  lea     rdx, [rsp+150h+Handle]; this
0x1401604a1  xor     esi, esi
0x1401604a3  mov     r8d, r9d; unsigned int
0x1401604a6  mov     rcx, r12; __int64
0x1401604a9  mov     [rsp+150h+Handle], rsi
0x1401604ae  call    ndisIfOpenInterfaceRegistryKey
0x1401604b3  mov     ebx, eax
0x1401604b5  test    eax, eax
0x1401604b7  jz      short loc_14016051E
0x1401604b9  lea     r15, WPP_RECORDER_INITIALIZED
0x1401604c0  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1401604c7  jz      short loc_140160501
0x1401604c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1401604d0  mov     r9d, 0Ah; int
0x1401604d6  mov     dword ptr [rsp+150h+var_118], eax; char
0x1401604da  mov     r8d, 8; int
0x1401604e0  mov     qword ptr [rsp+150h+var_120], r12; __int64
0x1401604e5  lea     rax, WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids
0x1401604ec  mov     qword ptr [rsp+150h+var_128], r13; char
0x1401604f1  mov     dl, 2; int
0x1401604f3  mov     rcx, [rcx+40h]; int
0x1401604f7  mov     [rsp+150h+var_130], rax; struct _GUID *
0x1401604fc  call    WPP_RECORDER_SF_q_guid_d
0x140160501  mov     rcx, [rsp+150h+Handle]; Handle
0x140160506  test    rcx, rcx
0x140160509  jz      short loc_140160517
0x14016050b  call    cs:__imp_ZwClose
0x140160512  nop     dword ptr [rax+rax+00h]
0x140160517  mov     eax, ebx
0x140160519  jmp     loc_14016080D
0x14016051e  lea     rax, [rsp+150h+Handle]
0x140160523  mov     dword ptr [rbp+50h+var_D0], esi
0x140160526  lea     r8, [rbp+50h+var_D0]; unsigned int *
0x14016052a  mov     [rbp+50h+var_C8], rax
0x14016052e  lea     rdx, NETSETUPPKEY_Interface_PnpDeviceInterfaceNumber; struct _NETSETUPPROPKEY *
0x140160535  lea     rcx, [rbp+50h+var_C8]; this
0x140160539  call    ?ReadUint32@NetSetupPropertyBag@@QEAAJAEBU_NETSETUPPROPKEY@@AEAI@Z; NetSetupPropertyBag::ReadUint32(_NETSETUPPROPKEY const &,uint &)
0x14016053e  mov     ebx, eax
0x140160540  test    eax, eax
0x140160542  jz      short loc_14016058C
0x140160544  lea     r15, WPP_RECORDER_INITIALIZED
0x14016054b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140160552  jz      short loc_140160501
0x140160554  mov     rcx, cs:WPP_GLOBAL_Control
0x14016055b  mov     r9d, 0Bh; int
0x140160561  mov     dword ptr [rsp+150h+var_120], eax; char
0x140160565  mov     r8d, 8; int
0x14016056b  lea     rax, WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids
0x140160572  mov     qword ptr [rsp+150h+var_128], r13; char
0x140160577  mov     dl, 2; int
0x140160579  mov     [rsp+150h+var_130], rax; struct _GUID *
0x14016057e  mov     rcx, [rcx+40h]; int
0x140160582  call    WPP_RECORDER_SF_qD
0x140160587  jmp     loc_140160501
0x14016058c  mov     rcx, [r13+0EF8h]; DeviceObject
0x140160593  lea     r9, [rsp+150h+DeviceRegKey]; DeviceRegKey
0x140160598  mov     edx, 2; DevInstKeyType
0x14016059d  mov     [rsp+150h+DeviceRegKey], rsi
0x1401605a2  mov     r8d, 0C2000000h; DesiredAccess
0x1401605a8  call    cs:__imp_IoOpenDeviceRegistryKey
0x1401605af  nop     dword ptr [rax+rax+00h]
0x1401605b4  mov     ebx, eax
0x1401605b6  test    eax, eax
0x1401605b8  jz      short loc_14016061C
0x1401605ba  lea     r15, WPP_RECORDER_INITIALIZED
0x1401605c1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1401605c8  jz      short loc_1401605FD
0x1401605ca  mov     r9d, 0Ch; int
0x1401605d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1401605d7  lea     rax, WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids
0x1401605de  mov     dword ptr [rsp+150h+var_120], ebx; char
0x1401605e2  mov     r8d, 8; int
0x1401605e8  mov     qword ptr [rsp+150h+var_128], r13; char
0x1401605ed  mov     dl, 2; int
0x1401605ef  mov     [rsp+150h+var_130], rax; struct _GUID *
0x1401605f4  mov     rcx, [rcx+40h]; int
0x1401605f8  call    WPP_RECORDER_SF_qD
0x1401605fd  mov     rcx, [rsp+150h+DeviceRegKey]; Handle
0x140160602  test    rcx, rcx
0x140160605  jz      loc_140160501
0x14016060b  call    cs:__imp_ZwClose
0x140160612  nop     dword ptr [rax+rax+00h]
0x140160617  jmp     loc_140160501
0x14016061c  mov     ecx, dword ptr [rbp+50h+var_D0]
0x14016061f  test    ecx, ecx
0x140160621  jnz     short loc_140160674
0x140160623  lea     r15, WPP_RECORDER_INITIALIZED
0x14016062a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140160631  jz      short loc_140160662
0x140160633  mov     rcx, cs:WPP_GLOBAL_Control
0x14016063a  lea     rax, WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids
0x140160641  mov     r9d, 0Dh; int
0x140160647  mov     qword ptr [rsp+150h+var_128], r13; char
0x14016064c  mov     r8d, 8; int
0x140160652  mov     [rsp+150h+var_130], rax; struct _GUID *
0x140160657  mov     dl, 4; int
0x140160659  mov     rcx, [rcx+40h]; int
0x14016065d  call    WPP_RECORDER_SF_q
0x140160662  mov     rax, [rsp+150h+DeviceRegKey]
0x140160667  mov     [rdi], rax
0x14016066a  mov     [rsp+150h+DeviceRegKey], rsi
0x14016066f  jmp     loc_1401607F5
0x140160674  lea     r15, WPP_RECORDER_INITIALIZED
0x14016067b  mov     [rsp+150h+arg_10], r14
0x140160683  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14016068a  lea     rax, WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids
0x140160691  jz      short loc_1401606BF
0x140160693  mov     dword ptr [rsp+150h+var_120], ecx; char
0x140160697  mov     r9d, 0Eh; int
0x14016069d  mov     rcx, cs:WPP_GLOBAL_Control
0x1401606a4  mov     r8d, 8; int
0x1401606aa  mov     qword ptr [rsp+150h+var_128], r13; char
0x1401606af  mov     dl, 4; int
0x1401606b1  mov     [rsp+150h+var_130], rax; struct _GUID *
0x1401606b6  mov     rcx, [rcx+40h]; int
0x1401606ba  call    WPP_RECORDER_SF_qD
0x1401606bf  movzx   ecx, byte ptr [r12+0Eh]
0x1401606c5  movzx   edx, byte ptr [r12+0Dh]
0x1401606cb  movzx   r8d, byte ptr [r12+0Ch]
0x1401606d1  movzx   eax, byte ptr [r12+0Fh]
0x1401606d7  movzx   r10d, byte ptr [r12+0Bh]
0x1401606dd  movzx   r11d, byte ptr [r12+0Ah]
0x1401606e3  movzx   ebx, byte ptr [r12+9]
0x1401606e9  movzx   edi, byte ptr [r12+8]
0x1401606ef  movzx   esi, word ptr [r12+6]
0x1401606f5  movzx   r14d, word ptr [r12+4]
0x1401606fb  mov     r9d, [r12]
0x1401606ff  mov     [rsp+150h+var_E8], eax
0x140160703  mov     [rsp+150h+var_F0], ecx
0x140160707  lea     rcx, [rbp+50h+var_B0]; wchar_t *
0x14016070b  mov     [rsp+150h+var_F8], edx
0x14016070f  mov     edx, 70h ; 'p'; unsigned __int64
0x140160714  mov     [rsp+150h+var_100], r8d
0x140160719  lea     r8, aNetworkinterfa_1; "NetworkInterface\\{%08x-%04x-%04x-%02x%"...
0x140160720  mov     [rsp+150h+var_108], r10d
0x140160725  mov     [rsp+150h+var_110], r11d
0x14016072a  mov     dword ptr [rsp+150h+var_118], ebx
0x14016072e  mov     dword ptr [rsp+150h+var_120], edi
0x140160732  mov     dword ptr [rsp+150h+var_128], esi
0x140160736  mov     dword ptr [rsp+150h+var_130], r14d
0x14016073b  call    ?RtlStringCbPrintfW@@YAJPEA_W_KPEB_WZZ; RtlStringCbPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140160740  mov     r14, [rsp+150h+arg_10]
0x140160748  mov     ebx, eax
0x14016074a  test    eax, eax
0x14016074c  jz      short loc_140160766
0x14016074e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140160755  jz      loc_1401605FD
0x14016075b  mov     r9d, 0Fh
0x140160761  jmp     loc_1401605D0
0x140160766  mov     r9, [rsp+150h+DeviceRegKey]; void *
0x14016076b  lea     r8, [rbp+50h+var_B0]; wchar_t *
0x14016076f  mov     edx, 0C2000000h; unsigned int
0x140160774  mov     [rbp+50h+var_C8], 0
0x14016077c  lea     rcx, [rbp+50h+var_C8]; this
0x140160780  call    ?Open@KRegKey@@QEAAJKPEB_WPEAX@Z; KRegKey::Open(ulong,wchar_t const *,void *)
0x140160785  mov     ebx, eax
0x140160787  test    eax, eax
0x140160789  jz      short loc_1401607D4
0x14016078b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140160792  jz      short loc_1401607B6
0x140160794  mov     rcx, cs:WPP_GLOBAL_Control
0x14016079b  mov     dword ptr [rsp+150h+var_118], eax
0x14016079f  lea     rax, [rbp+50h+var_B0]
0x1401607a3  mov     qword ptr [rsp+150h+var_120], rax
0x1401607a8  mov     qword ptr [rsp+150h+var_128], r13
0x1401607ad  mov     rcx, [rcx+40h]
0x1401607b1  call    WPP_RECORDER_SF_qSd
0x1401607b6  mov     rcx, [rbp+50h+var_C8]; Handle
0x1401607ba  test    rcx, rcx
0x1401607bd  jz      loc_1401605FD
0x1401607c3  call    cs:__imp_ZwClose
0x1401607ca  nop     dword ptr [rax+rax+00h]
0x1401607cf  jmp     loc_1401605FD
0x1401607d4  mov     rcx, [rbp+50h+var_C0]
0x1401607d8  mov     rax, [rbp+50h+var_C8]
0x1401607dc  mov     [rcx], rax
0x1401607df  mov     rcx, [rsp+150h+DeviceRegKey]; Handle
0x1401607e4  test    rcx, rcx
0x1401607e7  jz      short loc_1401607F5
0x1401607e9  call    cs:__imp_ZwClose
0x1401607f0  nop     dword ptr [rax+rax+00h]
0x1401607f5  mov     rcx, [rsp+150h+Handle]; Handle
0x1401607fa  test    rcx, rcx
0x1401607fd  jz      short loc_14016080B
0x1401607ff  call    cs:__imp_ZwClose
0x140160806  nop     dword ptr [rax+rax+00h]
0x14016080b  xor     eax, eax
0x14016080d  mov     rcx, [rbp+50h+var_40]
0x140160811  xor     rcx, rsp; StackCookie
0x140160814  call    __security_check_cookie
0x140160819  add     rsp, 120h
0x140160820  pop     r15
0x140160822  pop     r13
0x140160824  pop     r12
0x140160826  pop     rdi
0x140160827  pop     rsi
0x140160828  pop     rbx
0x140160829  pop     rbp
0x14016082a  retn
```
