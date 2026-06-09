# ndisWdfOpenConfigurationKey

- ea: `0x1401673f0`
- end: `0x1401677bc`
- name: `ndisWdfOpenConfigurationKey`
- size: `972`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x140090d90`
- `0x14013da20`

## callees

- `0x1400110b0`
- `0x140011190`
- `0x14006fcd0`
- `0x140074ea0`
- `0x140091154`
- `0x1400eb380`
- `0x1401673f0`
- `0x140168c60`
- `0x1401690b0`
- `0x140169160`

## import_xrefs

- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140167538`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140167538`
- `ntoskrnl!ZwClose` at `0x14016749b`
- `ntoskrnl!ZwClose` at `0x14016759b`
- `ntoskrnl!ZwClose` at `0x140167753`
- `ntoskrnl!ZwClose` at `0x140167779`
- `ntoskrnl!ZwClose` at `0x14016778f`
- `ntoskrnl!ZwClose` at `0x14016749b`
- `ntoskrnl!ZwClose` at `0x14016759b`
- `ntoskrnl!ZwClose` at `0x140167753`
- `ntoskrnl!ZwClose` at `0x140167779`
- `ntoskrnl!ZwClose` at `0x14016778f`

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
0x1401673f0  push    rbp
0x1401673f2  push    rbx
0x1401673f3  push    rsi
0x1401673f4  push    rdi
0x1401673f5  push    r12
0x1401673f7  push    r13
0x1401673f9  push    r15
0x1401673fb  lea     rbp, [rsp-20h]
0x140167400  sub     rsp, 120h
0x140167407  mov     rax, cs:__security_cookie
0x14016740e  xor     rax, rsp
0x140167411  mov     [rbp+50h+var_40], rax
0x140167415  lea     r12, [rcx+0FA8h]
0x14016741c  mov     [rbp+50h+var_C0], rdx
0x140167420  mov     r9d, 1; char
0x140167426  mov     rdi, rdx
0x140167429  mov     r13, rcx
0x14016742c  lea     rdx, [rsp+150h+Handle]; this
0x140167431  xor     esi, esi
0x140167433  mov     r8d, r9d; unsigned int
0x140167436  mov     rcx, r12; __int64
0x140167439  mov     [rsp+150h+Handle], rsi
0x14016743e  call    ndisIfOpenInterfaceRegistryKey
0x140167443  mov     ebx, eax
0x140167445  test    eax, eax
0x140167447  jz      short loc_1401674AE
0x140167449  lea     r15, WPP_RECORDER_INITIALIZED
0x140167450  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140167457  jz      short loc_140167491
0x140167459  mov     rcx, cs:WPP_GLOBAL_Control
0x140167460  mov     r9d, 0Ah; int
0x140167466  mov     dword ptr [rsp+150h+var_118], eax; char
0x14016746a  mov     r8d, 8; int
0x140167470  mov     qword ptr [rsp+150h+var_120], r12; __int64
0x140167475  lea     rax, WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids
0x14016747c  mov     qword ptr [rsp+150h+var_128], r13; char
0x140167481  mov     dl, 2; int
0x140167483  mov     rcx, [rcx+40h]; int
0x140167487  mov     [rsp+150h+var_130], rax; struct _GUID *
0x14016748c  call    WPP_RECORDER_SF_q_guid_d
0x140167491  mov     rcx, [rsp+150h+Handle]; Handle
0x140167496  test    rcx, rcx
0x140167499  jz      short loc_1401674A7
0x14016749b  call    cs:__imp_ZwClose
0x1401674a2  nop     dword ptr [rax+rax+00h]
0x1401674a7  mov     eax, ebx
0x1401674a9  jmp     loc_14016779D
0x1401674ae  lea     rax, [rsp+150h+Handle]
0x1401674b3  mov     dword ptr [rbp+50h+var_D0], esi
0x1401674b6  lea     r8, [rbp+50h+var_D0]; unsigned int *
0x1401674ba  mov     [rbp+50h+var_C8], rax
0x1401674be  lea     rdx, NETSETUPPKEY_Interface_PnpDeviceInterfaceNumber; struct _NETSETUPPROPKEY *
0x1401674c5  lea     rcx, [rbp+50h+var_C8]; this
0x1401674c9  call    ?ReadUint32@NetSetupPropertyBag@@QEAAJAEBU_NETSETUPPROPKEY@@AEAI@Z; NetSetupPropertyBag::ReadUint32(_NETSETUPPROPKEY const &,uint &)
0x1401674ce  mov     ebx, eax
0x1401674d0  test    eax, eax
0x1401674d2  jz      short loc_14016751C
0x1401674d4  lea     r15, WPP_RECORDER_INITIALIZED
0x1401674db  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1401674e2  jz      short loc_140167491
0x1401674e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1401674eb  mov     r9d, 0Bh; int
0x1401674f1  mov     dword ptr [rsp+150h+var_120], eax; char
0x1401674f5  mov     r8d, 8; int
0x1401674fb  lea     rax, WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids
0x140167502  mov     qword ptr [rsp+150h+var_128], r13; char
0x140167507  mov     dl, 2; int
0x140167509  mov     [rsp+150h+var_130], rax; struct _GUID *
0x14016750e  mov     rcx, [rcx+40h]; int
0x140167512  call    WPP_RECORDER_SF_qD
0x140167517  jmp     loc_140167491
0x14016751c  mov     rcx, [r13+0EF8h]; DeviceObject
0x140167523  lea     r9, [rsp+150h+DeviceRegKey]; DeviceRegKey
0x140167528  mov     edx, 2; DevInstKeyType
0x14016752d  mov     [rsp+150h+DeviceRegKey], rsi
0x140167532  mov     r8d, 0C2000000h; DesiredAccess
0x140167538  call    cs:__imp_IoOpenDeviceRegistryKey
0x14016753f  nop     dword ptr [rax+rax+00h]
0x140167544  mov     ebx, eax
0x140167546  test    eax, eax
0x140167548  jz      short loc_1401675AC
0x14016754a  lea     r15, WPP_RECORDER_INITIALIZED
0x140167551  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140167558  jz      short loc_14016758D
0x14016755a  mov     r9d, 0Ch; int
0x140167560  mov     rcx, cs:WPP_GLOBAL_Control
0x140167567  lea     rax, WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids
0x14016756e  mov     dword ptr [rsp+150h+var_120], ebx; char
0x140167572  mov     r8d, 8; int
0x140167578  mov     qword ptr [rsp+150h+var_128], r13; char
0x14016757d  mov     dl, 2; int
0x14016757f  mov     [rsp+150h+var_130], rax; struct _GUID *
0x140167584  mov     rcx, [rcx+40h]; int
0x140167588  call    WPP_RECORDER_SF_qD
0x14016758d  mov     rcx, [rsp+150h+DeviceRegKey]; Handle
0x140167592  test    rcx, rcx
0x140167595  jz      loc_140167491
0x14016759b  call    cs:__imp_ZwClose
0x1401675a2  nop     dword ptr [rax+rax+00h]
0x1401675a7  jmp     loc_140167491
0x1401675ac  mov     ecx, dword ptr [rbp+50h+var_D0]
0x1401675af  test    ecx, ecx
0x1401675b1  jnz     short loc_140167604
0x1401675b3  lea     r15, WPP_RECORDER_INITIALIZED
0x1401675ba  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1401675c1  jz      short loc_1401675F2
0x1401675c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1401675ca  lea     rax, WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids
0x1401675d1  mov     r9d, 0Dh; int
0x1401675d7  mov     qword ptr [rsp+150h+var_128], r13; char
0x1401675dc  mov     r8d, 8; int
0x1401675e2  mov     [rsp+150h+var_130], rax; struct _GUID *
0x1401675e7  mov     dl, 4; int
0x1401675e9  mov     rcx, [rcx+40h]; int
0x1401675ed  call    WPP_RECORDER_SF_q
0x1401675f2  mov     rax, [rsp+150h+DeviceRegKey]
0x1401675f7  mov     [rdi], rax
0x1401675fa  mov     [rsp+150h+DeviceRegKey], rsi
0x1401675ff  jmp     loc_140167785
0x140167604  lea     r15, WPP_RECORDER_INITIALIZED
0x14016760b  mov     [rsp+150h+arg_10], r14
0x140167613  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14016761a  lea     rax, WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids
0x140167621  jz      short loc_14016764F
0x140167623  mov     dword ptr [rsp+150h+var_120], ecx; char
0x140167627  mov     r9d, 0Eh; int
0x14016762d  mov     rcx, cs:WPP_GLOBAL_Control
0x140167634  mov     r8d, 8; int
0x14016763a  mov     qword ptr [rsp+150h+var_128], r13; char
0x14016763f  mov     dl, 4; int
0x140167641  mov     [rsp+150h+var_130], rax; struct _GUID *
0x140167646  mov     rcx, [rcx+40h]; int
0x14016764a  call    WPP_RECORDER_SF_qD
0x14016764f  movzx   ecx, byte ptr [r12+0Eh]
0x140167655  movzx   edx, byte ptr [r12+0Dh]
0x14016765b  movzx   r8d, byte ptr [r12+0Ch]
0x140167661  movzx   eax, byte ptr [r12+0Fh]
0x140167667  movzx   r10d, byte ptr [r12+0Bh]
0x14016766d  movzx   r11d, byte ptr [r12+0Ah]
0x140167673  movzx   ebx, byte ptr [r12+9]
0x140167679  movzx   edi, byte ptr [r12+8]
0x14016767f  movzx   esi, word ptr [r12+6]
0x140167685  movzx   r14d, word ptr [r12+4]
0x14016768b  mov     r9d, [r12]
0x14016768f  mov     [rsp+150h+var_E8], eax
0x140167693  mov     [rsp+150h+var_F0], ecx
0x140167697  lea     rcx, [rbp+50h+var_B0]; wchar_t *
0x14016769b  mov     [rsp+150h+var_F8], edx
0x14016769f  mov     edx, 70h ; 'p'; unsigned __int64
0x1401676a4  mov     [rsp+150h+var_100], r8d
0x1401676a9  lea     r8, aNetworkinterfa_1; "NetworkInterface\\{%08x-%04x-%04x-%02x%"...
0x1401676b0  mov     [rsp+150h+var_108], r10d
0x1401676b5  mov     [rsp+150h+var_110], r11d
0x1401676ba  mov     dword ptr [rsp+150h+var_118], ebx
0x1401676be  mov     dword ptr [rsp+150h+var_120], edi
0x1401676c2  mov     dword ptr [rsp+150h+var_128], esi
0x1401676c6  mov     dword ptr [rsp+150h+var_130], r14d
0x1401676cb  call    ?RtlStringCbPrintfW@@YAJPEA_W_KPEB_WZZ; RtlStringCbPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1401676d0  mov     r14, [rsp+150h+arg_10]
0x1401676d8  mov     ebx, eax
0x1401676da  test    eax, eax
0x1401676dc  jz      short loc_1401676F6
0x1401676de  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1401676e5  jz      loc_14016758D
0x1401676eb  mov     r9d, 0Fh
0x1401676f1  jmp     loc_140167560
0x1401676f6  mov     r9, [rsp+150h+DeviceRegKey]; void *
0x1401676fb  lea     r8, [rbp+50h+var_B0]; wchar_t *
0x1401676ff  mov     edx, 0C2000000h; unsigned int
0x140167704  mov     [rbp+50h+var_C8], 0
0x14016770c  lea     rcx, [rbp+50h+var_C8]; this
0x140167710  call    ?Open@KRegKey@@QEAAJKPEB_WPEAX@Z; KRegKey::Open(ulong,wchar_t const *,void *)
0x140167715  mov     ebx, eax
0x140167717  test    eax, eax
0x140167719  jz      short loc_140167764
0x14016771b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140167722  jz      short loc_140167746
0x140167724  mov     rcx, cs:WPP_GLOBAL_Control
0x14016772b  mov     dword ptr [rsp+150h+var_118], eax
0x14016772f  lea     rax, [rbp+50h+var_B0]
0x140167733  mov     qword ptr [rsp+150h+var_120], rax
0x140167738  mov     qword ptr [rsp+150h+var_128], r13
0x14016773d  mov     rcx, [rcx+40h]
0x140167741  call    WPP_RECORDER_SF_qSd
0x140167746  mov     rcx, [rbp+50h+var_C8]; Handle
0x14016774a  test    rcx, rcx
0x14016774d  jz      loc_14016758D
0x140167753  call    cs:__imp_ZwClose
0x14016775a  nop     dword ptr [rax+rax+00h]
0x14016775f  jmp     loc_14016758D
0x140167764  mov     rcx, [rbp+50h+var_C0]
0x140167768  mov     rax, [rbp+50h+var_C8]
0x14016776c  mov     [rcx], rax
0x14016776f  mov     rcx, [rsp+150h+DeviceRegKey]; Handle
0x140167774  test    rcx, rcx
0x140167777  jz      short loc_140167785
0x140167779  call    cs:__imp_ZwClose
0x140167780  nop     dword ptr [rax+rax+00h]
0x140167785  mov     rcx, [rsp+150h+Handle]; Handle
0x14016778a  test    rcx, rcx
0x14016778d  jz      short loc_14016779B
0x14016778f  call    cs:__imp_ZwClose
0x140167796  nop     dword ptr [rax+rax+00h]
0x14016779b  xor     eax, eax
0x14016779d  mov     rcx, [rbp+50h+var_40]
0x1401677a1  xor     rcx, rsp; StackCookie
0x1401677a4  call    __security_check_cookie
0x1401677a9  add     rsp, 120h
0x1401677b0  pop     r15
0x1401677b2  pop     r13
0x1401677b4  pop     r12
0x1401677b6  pop     rdi
0x1401677b7  pop     rsi
0x1401677b8  pop     rbx
0x1401677b9  pop     rbp
0x1401677ba  retn
```
