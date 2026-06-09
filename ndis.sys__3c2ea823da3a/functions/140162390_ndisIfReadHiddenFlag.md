# ndisIfReadHiddenFlag

- ea: `0x140162390`
- end: `0x140162571`
- name: `ndisIfReadHiddenFlag`
- size: `481`
- prototype: `__int64 __fastcall(NetSetupPropertyBag *this, PDEVICE_OBJECT DeviceObject, bool *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140147e88`
- `0x140161840`

## callees

- `0x1400e6160`
- `0x140161ae0`
- `0x140161cd0`
- `0x140162390`

## import_xrefs

- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140162401`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140162401`
- `ntoskrnl!ZwClose` at `0x1401624f2`
- `ntoskrnl!ZwClose` at `0x140162549`
- `ntoskrnl!ZwClose` at `0x140162561`
- `ntoskrnl!ZwClose` at `0x1401624f2`
- `ntoskrnl!ZwClose` at `0x140162549`
- `ntoskrnl!ZwClose` at `0x140162561`
- `ntoskrnl!ZwQueryValueKey` at `0x1401624ac`
- `ntoskrnl!ZwQueryValueKey` at `0x1401624ac`

## pseudocode

```c
NTSTATUS __fastcall ndisIfReadHiddenFlag(NetSetupPropertyBag *this, PDEVICE_OBJECT DeviceObject, bool *a3)
{
  NTSTATUS result; // eax
  void *v7; // rbx
  const wchar_t *v8; // rax
  char v9; // r14
  __int64 v10; // rcx
  NTSTATUS v11; // ebp
  unsigned int v12; // [rsp+30h] [rbp-68h] BYREF
  ULONG ResultLength; // [rsp+34h] [rbp-64h] BYREF
  void *DeviceRegKey; // [rsp+38h] [rbp-60h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-58h] BYREF
  __int128 KeyValueInformation; // [rsp+50h] [rbp-48h] BYREF
  int v17; // [rsp+60h] [rbp-38h]

  if ( !DeviceObject )
    return NetSetupPropertyBag::ReadBoolean(this, (const struct _NETSETUPPROPKEY *)NETSETUPPKEY_Driver_HideInUi, a3);
  v12 = 0;
  if ( (int)NetSetupPropertyBag::ReadUint32(
              this,
              (const struct _NETSETUPPROPKEY *)NETSETUPPKEY_Interface_PnpDeviceInterfaceNumber,
              &v12) >= 0 )
  {
    if ( v12 )
      return NetSetupPropertyBag::ReadBoolean(this, (const struct _NETSETUPPROPKEY *)NETSETUPPKEY_Driver_HideInUi, a3);
  }
  DeviceRegKey = 0;
  result = IoOpenDeviceRegistryKey(DeviceObject, 2u, 0x80000000, &DeviceRegKey);
  if ( result < 0 )
    return result;
  v7 = DeviceRegKey;
  v8 = L"Characteristics";
  ValueName = 0;
  v9 = 0;
  v10 = 0x7FFF;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v10;
  }
  while ( v10 );
  v11 = -1073741811;
  if ( v10 )
  {
    ValueName.Buffer = L"Characteristics";
    ResultLength = 0;
    ValueName.Length = -2 - 2 * v10;
    ValueName.MaximumLength = -2 * v10;
    v17 = 0;
    KeyValueInformation = 0;
    v11 = ZwQueryValueKey(
            DeviceRegKey,
            &ValueName,
            KeyValuePartialInformation,
            &KeyValueInformation,
            0x14u,
            &ResultLength);
    if ( v11 >= 0 )
    {
      if ( DWORD1(KeyValueInformation) == 4 )
      {
        if ( DWORD2(KeyValueInformation) == 4 )
        {
          v9 = BYTE12(KeyValueInformation);
          v11 = 0;
        }
        else
        {
          v11 = -1073741789;
        }
      }
      else
      {
        v11 = -1073741788;
      }
    }
  }
  if ( v11 == -1073741772 )
  {
    if ( v7 )
      ZwClose(v7);
    return NetSetupPropertyBag::ReadBoolean(this, (const struct _NETSETUPPROPKEY *)NETSETUPPKEY_Driver_HideInUi, a3);
  }
  if ( v11 )
  {
    if ( v7 )
      ZwClose(v7);
    return v11;
  }
  else
  {
    *a3 = (v9 & 8) != 0;
    if ( v7 )
      ZwClose(v7);
    return 0;
  }
}

```

## disassembly

```asm
0x140162390  mov     [rsp+arg_18], rbx
0x140162395  push    rbp
0x140162396  push    rsi
0x140162397  push    rdi
0x140162398  push    r14
0x14016239a  push    r15
0x14016239c  sub     rsp, 70h
0x1401623a0  mov     rax, cs:__security_cookie
0x1401623a7  xor     rax, rsp
0x1401623aa  mov     [rsp+98h+var_30], rax
0x1401623af  mov     rsi, r8
0x1401623b2  mov     rbx, rdx
0x1401623b5  mov     rdi, rcx
0x1401623b8  test    rdx, rdx
0x1401623bb  jz      loc_1401624FE
0x1401623c1  xor     r15d, r15d
0x1401623c4  lea     r8, [rsp+98h+var_68]; unsigned int *
0x1401623c9  lea     rdx, NETSETUPPKEY_Interface_PnpDeviceInterfaceNumber; struct _NETSETUPPROPKEY *
0x1401623d0  mov     [rsp+98h+var_68], r15d
0x1401623d5  call    ?ReadUint32@NetSetupPropertyBag@@QEAAJAEBU_NETSETUPPROPKEY@@AEAI@Z; NetSetupPropertyBag::ReadUint32(_NETSETUPPROPKEY const &,uint &)
0x1401623da  test    eax, eax
0x1401623dc  js      short loc_1401623E9
0x1401623de  cmp     [rsp+98h+var_68], r15d
0x1401623e3  ja      loc_1401624FE
0x1401623e9  lea     r9, [rsp+98h+DeviceRegKey]; DeviceRegKey
0x1401623ee  mov     [rsp+98h+DeviceRegKey], r15
0x1401623f3  mov     edx, 2; DevInstKeyType
0x1401623f8  mov     r8d, 80000000h; DesiredAccess
0x1401623fe  mov     rcx, rbx; DeviceObject
0x140162401  call    cs:__imp_IoOpenDeviceRegistryKey
0x140162408  nop     dword ptr [rax+rax+00h]
0x14016240d  test    eax, eax
0x14016240f  js      loc_140162510
0x140162415  mov     rbx, [rsp+98h+DeviceRegKey]
0x14016241a  lea     rdx, aCharacteristic; "Characteristics"
0x140162421  xorps   xmm0, xmm0
0x140162424  mov     rax, rdx
0x140162427  movups  xmmword ptr [rsp+98h+ValueName.Length], xmm0
0x14016242c  mov     r14d, r15d
0x14016242f  mov     ecx, 7FFFh
0x140162434  cmp     [rax], r14w
0x140162438  jz      short loc_140162444
0x14016243a  add     rax, 2
0x14016243e  sub     rcx, 1
0x140162442  jnz     short loc_140162434
0x140162444  test    rcx, rcx
0x140162447  mov     ebp, 0C000000Dh
0x14016244c  cmovnz  ebp, r15d
0x140162450  jz      loc_1401624E2
0x140162456  add     cx, cx
0x140162459  mov     [rsp+98h+ValueName.Buffer], rdx
0x14016245e  mov     eax, 0FFFEh
0x140162463  mov     [rsp+98h+var_64], r15d
0x140162468  sub     ax, cx
0x14016246b  lea     r9, [rsp+98h+KeyValueInformation]; KeyValueInformation
0x140162470  mov     [rsp+98h+ValueName.Length], ax
0x140162475  lea     rdx, [rsp+98h+ValueName]; ValueName
0x14016247a  add     ax, 2
0x14016247e  xorps   xmm0, xmm0
0x140162481  mov     [rsp+98h+ValueName.MaximumLength], ax
0x140162486  mov     r8d, 2; KeyValueInformationClass
0x14016248c  xor     eax, eax
0x14016248e  mov     rcx, rbx; KeyHandle
0x140162491  mov     [rsp+98h+var_38], eax
0x140162495  lea     rax, [rsp+98h+var_64]
0x14016249a  mov     [rsp+98h+ResultLength], rax; ResultLength
0x14016249f  mov     [rsp+98h+Length], 14h; Length
0x1401624a7  movups  [rsp+98h+KeyValueInformation], xmm0
0x1401624ac  call    cs:__imp_ZwQueryValueKey
0x1401624b3  nop     dword ptr [rax+rax+00h]
0x1401624b8  mov     ebp, eax
0x1401624ba  test    eax, eax
0x1401624bc  js      short loc_1401624E2
0x1401624be  cmp     dword ptr [rsp+98h+KeyValueInformation+4], 4
0x1401624c3  jz      short loc_1401624CC
0x1401624c5  mov     ebp, 0C0000024h
0x1401624ca  jmp     short loc_1401624E2
0x1401624cc  cmp     dword ptr [rsp+98h+KeyValueInformation+8], 4
0x1401624d1  jz      short loc_1401624DA
0x1401624d3  mov     ebp, 0C0000023h
0x1401624d8  jmp     short loc_1401624E2
0x1401624da  mov     r14d, dword ptr [rsp+98h+KeyValueInformation+0Ch]
0x1401624df  mov     ebp, r15d
0x1401624e2  cmp     ebp, 0C0000034h
0x1401624e8  jnz     short loc_140162532
0x1401624ea  test    rbx, rbx
0x1401624ed  jz      short loc_1401624FE
0x1401624ef  mov     rcx, rbx; Handle
0x1401624f2  call    cs:__imp_ZwClose
0x1401624f9  nop     dword ptr [rax+rax+00h]
0x1401624fe  mov     r8, rsi; bool *
0x140162501  lea     rdx, NETSETUPPKEY_Driver_HideInUi; struct _NETSETUPPROPKEY *
0x140162508  mov     rcx, rdi; this
0x14016250b  call    ?ReadBoolean@NetSetupPropertyBag@@QEAAJAEBU_NETSETUPPROPKEY@@AEA_N@Z; NetSetupPropertyBag::ReadBoolean(_NETSETUPPROPKEY const &,bool &)
0x140162510  mov     rcx, [rsp+98h+var_30]
0x140162515  xor     rcx, rsp; StackCookie
0x140162518  call    __security_check_cookie
0x14016251d  mov     rbx, [rsp+98h+arg_18]
0x140162525  add     rsp, 70h
0x140162529  pop     r15
0x14016252b  pop     r14
0x14016252d  pop     rdi
0x14016252e  pop     rsi
0x14016252f  pop     rbp
0x140162530  retn
0x140162532  test    ebp, ebp
0x140162534  jnz     short loc_140162559
0x140162536  shr     r14d, 3
0x14016253a  and     r14b, 1
0x14016253e  mov     [rsi], r14b
0x140162541  test    rbx, rbx
0x140162544  jz      short loc_140162555
0x140162546  mov     rcx, rbx; Handle
0x140162549  call    cs:__imp_ZwClose
0x140162550  nop     dword ptr [rax+rax+00h]
0x140162555  xor     eax, eax
0x140162557  jmp     short loc_140162510
0x140162559  test    rbx, rbx
0x14016255c  jz      short loc_14016256D
0x14016255e  mov     rcx, rbx; Handle
0x140162561  call    cs:__imp_ZwClose
0x140162568  nop     dword ptr [rax+rax+00h]
0x14016256d  mov     eax, ebp
0x14016256f  jmp     short loc_140162510
```
