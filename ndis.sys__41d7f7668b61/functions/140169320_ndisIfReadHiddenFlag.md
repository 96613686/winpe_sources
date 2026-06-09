# ndisIfReadHiddenFlag

- ea: `0x140169320`
- end: `0x140169501`
- name: `ndisIfReadHiddenFlag`
- size: `481`
- prototype: `__int64 __fastcall(NetSetupPropertyBag *this, PDEVICE_OBJECT DeviceObject, bool *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x14014ee28`
- `0x1401687d0`

## callees

- `0x1400eb380`
- `0x140168a70`
- `0x140168c60`
- `0x140169320`

## import_xrefs

- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140169391`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140169391`
- `ntoskrnl!ZwClose` at `0x140169482`
- `ntoskrnl!ZwClose` at `0x1401694d9`
- `ntoskrnl!ZwClose` at `0x1401694f1`
- `ntoskrnl!ZwClose` at `0x140169482`
- `ntoskrnl!ZwClose` at `0x1401694d9`
- `ntoskrnl!ZwClose` at `0x1401694f1`
- `ntoskrnl!ZwQueryValueKey` at `0x14016943c`
- `ntoskrnl!ZwQueryValueKey` at `0x14016943c`

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
0x140169320  mov     [rsp+arg_18], rbx
0x140169325  push    rbp
0x140169326  push    rsi
0x140169327  push    rdi
0x140169328  push    r14
0x14016932a  push    r15
0x14016932c  sub     rsp, 70h
0x140169330  mov     rax, cs:__security_cookie
0x140169337  xor     rax, rsp
0x14016933a  mov     [rsp+98h+var_30], rax
0x14016933f  mov     rsi, r8
0x140169342  mov     rbx, rdx
0x140169345  mov     rdi, rcx
0x140169348  test    rdx, rdx
0x14016934b  jz      loc_14016948E
0x140169351  xor     r15d, r15d
0x140169354  lea     r8, [rsp+98h+var_68]; unsigned int *
0x140169359  lea     rdx, NETSETUPPKEY_Interface_PnpDeviceInterfaceNumber; struct _NETSETUPPROPKEY *
0x140169360  mov     [rsp+98h+var_68], r15d
0x140169365  call    ?ReadUint32@NetSetupPropertyBag@@QEAAJAEBU_NETSETUPPROPKEY@@AEAI@Z; NetSetupPropertyBag::ReadUint32(_NETSETUPPROPKEY const &,uint &)
0x14016936a  test    eax, eax
0x14016936c  js      short loc_140169379
0x14016936e  cmp     [rsp+98h+var_68], r15d
0x140169373  ja      loc_14016948E
0x140169379  lea     r9, [rsp+98h+DeviceRegKey]; DeviceRegKey
0x14016937e  mov     [rsp+98h+DeviceRegKey], r15
0x140169383  mov     edx, 2; DevInstKeyType
0x140169388  mov     r8d, 80000000h; DesiredAccess
0x14016938e  mov     rcx, rbx; DeviceObject
0x140169391  call    cs:__imp_IoOpenDeviceRegistryKey
0x140169398  nop     dword ptr [rax+rax+00h]
0x14016939d  test    eax, eax
0x14016939f  js      loc_1401694A0
0x1401693a5  mov     rbx, [rsp+98h+DeviceRegKey]
0x1401693aa  lea     rdx, aCharacteristic; "Characteristics"
0x1401693b1  xorps   xmm0, xmm0
0x1401693b4  mov     rax, rdx
0x1401693b7  movups  xmmword ptr [rsp+98h+ValueName.Length], xmm0
0x1401693bc  mov     r14d, r15d
0x1401693bf  mov     ecx, 7FFFh
0x1401693c4  cmp     [rax], r14w
0x1401693c8  jz      short loc_1401693D4
0x1401693ca  add     rax, 2
0x1401693ce  sub     rcx, 1
0x1401693d2  jnz     short loc_1401693C4
0x1401693d4  test    rcx, rcx
0x1401693d7  mov     ebp, 0C000000Dh
0x1401693dc  cmovnz  ebp, r15d
0x1401693e0  jz      loc_140169472
0x1401693e6  add     cx, cx
0x1401693e9  mov     [rsp+98h+ValueName.Buffer], rdx
0x1401693ee  mov     eax, 0FFFEh
0x1401693f3  mov     [rsp+98h+var_64], r15d
0x1401693f8  sub     ax, cx
0x1401693fb  lea     r9, [rsp+98h+KeyValueInformation]; KeyValueInformation
0x140169400  mov     [rsp+98h+ValueName.Length], ax
0x140169405  lea     rdx, [rsp+98h+ValueName]; ValueName
0x14016940a  add     ax, 2
0x14016940e  xorps   xmm0, xmm0
0x140169411  mov     [rsp+98h+ValueName.MaximumLength], ax
0x140169416  mov     r8d, 2; KeyValueInformationClass
0x14016941c  xor     eax, eax
0x14016941e  mov     rcx, rbx; KeyHandle
0x140169421  mov     [rsp+98h+var_38], eax
0x140169425  lea     rax, [rsp+98h+var_64]
0x14016942a  mov     [rsp+98h+ResultLength], rax; ResultLength
0x14016942f  mov     [rsp+98h+Length], 14h; Length
0x140169437  movups  [rsp+98h+KeyValueInformation], xmm0
0x14016943c  call    cs:__imp_ZwQueryValueKey
0x140169443  nop     dword ptr [rax+rax+00h]
0x140169448  mov     ebp, eax
0x14016944a  test    eax, eax
0x14016944c  js      short loc_140169472
0x14016944e  cmp     dword ptr [rsp+98h+KeyValueInformation+4], 4
0x140169453  jz      short loc_14016945C
0x140169455  mov     ebp, 0C0000024h
0x14016945a  jmp     short loc_140169472
0x14016945c  cmp     dword ptr [rsp+98h+KeyValueInformation+8], 4
0x140169461  jz      short loc_14016946A
0x140169463  mov     ebp, 0C0000023h
0x140169468  jmp     short loc_140169472
0x14016946a  mov     r14d, dword ptr [rsp+98h+KeyValueInformation+0Ch]
0x14016946f  mov     ebp, r15d
0x140169472  cmp     ebp, 0C0000034h
0x140169478  jnz     short loc_1401694C2
0x14016947a  test    rbx, rbx
0x14016947d  jz      short loc_14016948E
0x14016947f  mov     rcx, rbx; Handle
0x140169482  call    cs:__imp_ZwClose
0x140169489  nop     dword ptr [rax+rax+00h]
0x14016948e  mov     r8, rsi; bool *
0x140169491  lea     rdx, NETSETUPPKEY_Driver_HideInUi; struct _NETSETUPPROPKEY *
0x140169498  mov     rcx, rdi; this
0x14016949b  call    ?ReadBoolean@NetSetupPropertyBag@@QEAAJAEBU_NETSETUPPROPKEY@@AEA_N@Z; NetSetupPropertyBag::ReadBoolean(_NETSETUPPROPKEY const &,bool &)
0x1401694a0  mov     rcx, [rsp+98h+var_30]
0x1401694a5  xor     rcx, rsp; StackCookie
0x1401694a8  call    __security_check_cookie
0x1401694ad  mov     rbx, [rsp+98h+arg_18]
0x1401694b5  add     rsp, 70h
0x1401694b9  pop     r15
0x1401694bb  pop     r14
0x1401694bd  pop     rdi
0x1401694be  pop     rsi
0x1401694bf  pop     rbp
0x1401694c0  retn
0x1401694c2  test    ebp, ebp
0x1401694c4  jnz     short loc_1401694E9
0x1401694c6  shr     r14d, 3
0x1401694ca  and     r14b, 1
0x1401694ce  mov     [rsi], r14b
0x1401694d1  test    rbx, rbx
0x1401694d4  jz      short loc_1401694E5
0x1401694d6  mov     rcx, rbx; Handle
0x1401694d9  call    cs:__imp_ZwClose
0x1401694e0  nop     dword ptr [rax+rax+00h]
0x1401694e5  xor     eax, eax
0x1401694e7  jmp     short loc_1401694A0
0x1401694e9  test    rbx, rbx
0x1401694ec  jz      short loc_1401694FD
0x1401694ee  mov     rcx, rbx; Handle
0x1401694f1  call    cs:__imp_ZwClose
0x1401694f8  nop     dword ptr [rax+rax+00h]
0x1401694fd  mov     eax, ebp
0x1401694ff  jmp     short loc_1401694A0
```
