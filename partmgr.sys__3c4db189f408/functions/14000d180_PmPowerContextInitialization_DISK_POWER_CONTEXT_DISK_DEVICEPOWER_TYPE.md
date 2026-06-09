# PmPowerContextInitialization(_DISK_POWER_CONTEXT *,_DISK_DEVICEPOWER_TYPE)

- ea: `0x14000d180`
- end: `0x14000d59a`
- name: `?PmPowerContextInitialization@@YAJPEAU_DISK_POWER_CONTEXT@@W4_DISK_DEVICEPOWER_TYPE@@@Z`
- size: `1050`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000d5a0`

## callees

- `0x14000d180`
- `0x14000d634`
- `0x140010f20`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000d518`
- `ntoskrnl!ZwClose` at `0x14000d54d`
- `ntoskrnl!ZwClose` at `0x14000d563`
- `ntoskrnl!ZwClose` at `0x14000d518`
- `ntoskrnl!ZwClose` at `0x14000d54d`
- `ntoskrnl!ZwClose` at `0x14000d563`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d294`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d36c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d294`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d36c`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14000d400`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14000d400`
- `ntoskrnl!ZwOpenKey` at `0x14000d2db`
- `ntoskrnl!ZwOpenKey` at `0x14000d3b7`
- `ntoskrnl!ZwOpenKey` at `0x14000d44e`
- `ntoskrnl!ZwOpenKey` at `0x14000d2db`
- `ntoskrnl!ZwOpenKey` at `0x14000d3b7`
- `ntoskrnl!ZwOpenKey` at `0x14000d44e`

## string_xrefs

- `0x14000d1c0`: `SmallRandomReadPowerMw`
- `0x14000d1cb`: `SmallRandomWritePowerMw`
- `0x14000d1d6`: `SmallSequentialReadPowerMw`
- `0x14000d1e1`: `SmallSequentialWritePowerMw`
- `0x14000d1ec`: `LargeRandomReadPowerMw`
- `0x14000d1f7`: `LargeRandomWritePowerMw`
- `0x14000d202`: `LargeSequentialReadPowerMw`
- `0x14000d20d`: `LargeSequentialWritePowerMw`
- `0x14000d288`: `\Registry\Machine\System\CurrentControlSet\Control\Power\EnergyEstimation\Storage\SD`
- `0x14000d27f`: `\Registry\Machine\System\CurrentControlSet\Control\Power\EnergyEstimation\Storage\SSD`
- `0x14000d276`: `\Registry\Machine\System\CurrentControlSet\Control\Power\EnergyEstimation\Storage\HDD`
- `0x14000d26d`: `\Registry\Machine\System\CurrentControlSet\Control\Power\EnergyEstimation\Storage\NVME`

## pseudocode

```c
__int64 __fastcall PmPowerContextInitialization(_WORD *a1, int a2)
{
  int v3; // edx
  int v4; // edx
  NTSTATUS v5; // ebx
  const WCHAR *v6; // rdx
  __int64 v7; // rdi
  unsigned int *v8; // rsi
  __int16 v9; // ax
  _WORD *v10; // rdi
  unsigned int v11; // esi
  HANDLE v12; // rcx
  unsigned int v14; // [rsp+20h] [rbp-E0h] BYREF
  HANDLE Handle; // [rsp+28h] [rbp-D8h] BYREF
  void *KeyHandle; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-B8h] BYREF
  void *v19; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING String; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v21[10]; // [rsp+90h] [rbp-70h]
  char v22; // [rsp+E0h] [rbp-20h] BYREF

  v19 = 0;
  v14 = 0;
  v21[0] = L"SmallRandomReadPowerMw";
  v21[1] = L"SmallRandomWritePowerMw";
  v21[2] = L"SmallSequentialReadPowerMw";
  v21[3] = L"SmallSequentialWritePowerMw";
  v21[4] = L"LargeRandomReadPowerMw";
  v21[5] = L"LargeRandomWritePowerMw";
  v21[6] = L"LargeSequentialReadPowerMw";
  v21[7] = L"LargeSequentialWritePowerMw";
  v21[8] = L"FlushPowerMw";
  KeyHandle = 0;
  Handle = 0;
  DestinationString = 0;
  String = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( a2 )
  {
    v3 = a2 - 1;
    if ( v3 )
    {
      v4 = v3 - 1;
      if ( v4 )
      {
        if ( v4 != 1 )
          return 0;
        v6 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Power\\EnergyEstimation\\Storage\\NVME";
      }
      else
      {
        v6 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Power\\EnergyEstimation\\Storage\\HDD";
      }
    }
    else
    {
      v6 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Power\\EnergyEstimation\\Storage\\SSD";
    }
  }
  else
  {
    v6 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Power\\EnergyEstimation\\Storage\\SD";
  }
  RtlInitUnicodeString(&DestinationString, v6);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v5 >= 0 )
  {
    v7 = 0;
    v8 = (unsigned int *)(a1 + 84);
    while ( (unsigned int)v7 < 9 )
    {
      v5 = PmQueryDWORDValueKey(KeyHandle, v21[v7], &v14);
      if ( v5 < 0 )
        goto LABEL_29;
      v7 = (unsigned int)(v7 + 1);
      *v8++ = v14;
    }
    v5 = PmQueryDWORDValueKey(KeyHandle, L"IdleStatesNumber", &v14);
    if ( v5 >= 0 )
    {
      v9 = v14;
      *a1 = v14;
      if ( (unsigned __int16)(v9 - 1) > 4u )
      {
        v5 = -1073741811;
      }
      else
      {
        RtlInitUnicodeString(&DestinationString, L"IdleState");
        ObjectAttributes.RootDirectory = KeyHandle;
        ObjectAttributes.Attributes = 576;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Length = 48;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v5 = ZwOpenKey(&v19, 0x20019u, &ObjectAttributes);
        if ( v5 >= 0 )
        {
          v10 = 0;
          String.MaximumLength = 28;
          v11 = 0;
          String.Buffer = (PWSTR)&v22;
          while ( v11 < (unsigned __int16)*a1 )
          {
            String.Length = 26;
            v5 = RtlIntegerToUnicodeString(v11 + 1, 0xAu, &String);
            if ( v5 < 0 )
              goto LABEL_29;
            ObjectAttributes.RootDirectory = v19;
            ObjectAttributes.Length = 48;
            ObjectAttributes.ObjectName = &String;
            ObjectAttributes.Attributes = 576;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            v5 = ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes);
            if ( v5 < 0 )
              goto LABEL_29;
            v5 = PmQueryDWORDValueKey(Handle, L"IdleExitLatencyMs", &v14);
            if ( v5 < 0 )
              goto LABEL_29;
            v10 = &a1[16 * v11 + 4];
            *(_QWORD *)v10 = 10000 * v14;
            v5 = PmQueryDWORDValueKey(Handle, L"IdleExitEnergyMicroJoules", &v14);
            if ( v5 < 0 )
              goto LABEL_29;
            *((_QWORD *)v10 + 1) = 10000 * v14;
            v5 = PmQueryDWORDValueKey(Handle, L"IdleTimeLengthMs", &v14);
            if ( v5 < 0 )
              goto LABEL_29;
            *((_QWORD *)v10 + 2) = 10000 * v14;
            v5 = PmQueryDWORDValueKey(Handle, L"IdlePowerMw", &v14);
            if ( v5 < 0 )
              goto LABEL_29;
            v12 = Handle;
            *((_DWORD *)v10 + 6) = v14;
            ZwClose(v12);
            ++v11;
            Handle = 0;
          }
          *((_QWORD *)v10 + 2) = -1;
        }
      }
    }
  }
LABEL_29:
  if ( Handle )
    ZwClose(Handle);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000d180  mov     [rsp-8+arg_8], rbx
0x14000d185  mov     [rsp-8+arg_10], rsi
0x14000d18a  push    rbp
0x14000d18b  push    rdi
0x14000d18c  push    r13
0x14000d18e  push    r14
0x14000d190  push    r15
0x14000d192  lea     rbp, [rsp-10h]
0x14000d197  sub     rsp, 110h
0x14000d19e  mov     rax, cs:__security_cookie
0x14000d1a5  xor     rax, rsp
0x14000d1a8  mov     [rbp+30h+var_30], rax
0x14000d1ac  mov     [rsp+130h+var_B8], 0
0x14000d1b5  xorps   xmm0, xmm0
0x14000d1b8  mov     [rsp+130h+var_110], 0
0x14000d1c0  lea     rax, aSmallrandomrea; "SmallRandomReadPowerMw"
0x14000d1c7  mov     [rbp+30h+var_A0], rax
0x14000d1cb  lea     rax, aSmallrandomwri; "SmallRandomWritePowerMw"
0x14000d1d2  mov     [rbp+30h+var_98], rax
0x14000d1d6  lea     rax, aSmallsequentia; "SmallSequentialReadPowerMw"
0x14000d1dd  mov     [rbp+30h+var_90], rax
0x14000d1e1  lea     rax, aSmallsequentia_0; "SmallSequentialWritePowerMw"
0x14000d1e8  mov     [rbp+30h+var_88], rax
0x14000d1ec  lea     rax, aLargerandomrea; "LargeRandomReadPowerMw"
0x14000d1f3  mov     [rbp+30h+var_80], rax
0x14000d1f7  lea     rax, aLargerandomwri; "LargeRandomWritePowerMw"
0x14000d1fe  mov     [rbp+30h+var_78], rax
0x14000d202  lea     rax, aLargesequentia_0; "LargeSequentialReadPowerMw"
0x14000d209  mov     [rbp+30h+var_70], rax
0x14000d20d  lea     rax, aLargesequentia; "LargeSequentialWritePowerMw"
0x14000d214  mov     [rbp+30h+var_68], rax
0x14000d218  lea     rax, aFlushpowermw; "FlushPowerMw"
0x14000d21f  mov     [rbp+30h+var_60], rax
0x14000d223  xorps   xmm1, xmm1
0x14000d226  mov     [rsp+130h+KeyHandle], 0
0x14000d22f  mov     r14, rcx
0x14000d232  mov     [rsp+130h+Handle], 0
0x14000d23b  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm0
0x14000d240  movups  xmmword ptr [rbp+30h+String.Length], xmm1
0x14000d244  movups  xmmword ptr [rsp+130h+ObjectAttributes.Length], xmm0
0x14000d249  movups  xmmword ptr [rsp+130h+ObjectAttributes.ObjectName], xmm0
0x14000d24e  movups  xmmword ptr [rsp+130h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000d253  test    edx, edx
0x14000d255  jz      short loc_14000D288
0x14000d257  sub     edx, 1
0x14000d25a  jz      short loc_14000D27F
0x14000d25c  sub     edx, 1
0x14000d25f  jz      short loc_14000D276
0x14000d261  cmp     edx, 1
0x14000d264  jz      short loc_14000D26D
0x14000d266  xor     ebx, ebx
0x14000d268  jmp     loc_14000D56F
0x14000d26d  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x14000d274  jmp     short loc_14000D28F
0x14000d276  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x14000d27d  jmp     short loc_14000D28F
0x14000d27f  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x14000d286  jmp     short loc_14000D28F
0x14000d288  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x14000d28f  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x14000d294  call    cs:__imp_RtlInitUnicodeString
0x14000d29b  nop     dword ptr [rax+rax+00h]
0x14000d2a0  lea     rax, [rsp+130h+DestinationString]
0x14000d2a5  mov     [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x14000d2ad  xorps   xmm0, xmm0
0x14000d2b0  mov     [rsp+130h+ObjectAttributes.ObjectName], rax
0x14000d2b5  lea     r8, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x14000d2ba  mov     [rsp+130h+ObjectAttributes.RootDirectory], 0
0x14000d2c3  mov     edx, 20019h; DesiredAccess
0x14000d2c8  mov     [rsp+130h+ObjectAttributes.Attributes], 240h
0x14000d2d0  lea     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x14000d2d5  movdqu  xmmword ptr [rsp+130h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000d2db  call    cs:__imp_ZwOpenKey
0x14000d2e2  nop     dword ptr [rax+rax+00h]
0x14000d2e7  mov     ebx, eax
0x14000d2e9  test    eax, eax
0x14000d2eb  js      loc_14000D543
0x14000d2f1  xor     edi, edi
0x14000d2f3  lea     rsi, [r14+0A8h]
0x14000d2fa  lea     r15d, [rdi+1]
0x14000d2fe  lea     r13d, [rdi+4]
0x14000d302  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x14000d307  lea     r8, [rsp+130h+var_110]; unsigned int *
0x14000d30c  cmp     edi, 9
0x14000d30f  jnb     short loc_14000D333
0x14000d311  mov     rdx, [rbp+rdi*8+30h+var_A0]; unsigned __int16 *
0x14000d316  call    ?PmQueryDWORDValueKey@@YAJPEAXPEBGPEAK@Z; PmQueryDWORDValueKey(void *,ushort const *,ulong *)
0x14000d31b  mov     ebx, eax
0x14000d31d  test    eax, eax
0x14000d31f  js      loc_14000D543
0x14000d325  mov     eax, [rsp+130h+var_110]
0x14000d329  add     edi, r15d
0x14000d32c  mov     [rsi], eax
0x14000d32e  add     rsi, r13
0x14000d331  jmp     short loc_14000D302
0x14000d333  lea     rdx, aIdlestatesnumb; "IdleStatesNumber"
0x14000d33a  call    ?PmQueryDWORDValueKey@@YAJPEAXPEBGPEAK@Z; PmQueryDWORDValueKey(void *,ushort const *,ulong *)
0x14000d33f  mov     ebx, eax
0x14000d341  test    eax, eax
0x14000d343  js      loc_14000D543
0x14000d349  movzx   eax, word ptr [rsp+130h+var_110]
0x14000d34e  mov     [r14], ax
0x14000d352  sub     ax, r15w
0x14000d356  cmp     ax, r13w
0x14000d35a  ja      loc_14000D53E
0x14000d360  lea     rdx, aIdlestate; "IdleState"
0x14000d367  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x14000d36c  call    cs:__imp_RtlInitUnicodeString
0x14000d373  nop     dword ptr [rax+rax+00h]
0x14000d378  mov     rax, [rsp+130h+KeyHandle]
0x14000d37d  lea     r8, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x14000d382  mov     [rsp+130h+ObjectAttributes.RootDirectory], rax
0x14000d387  lea     rcx, [rsp+130h+var_B8]; KeyHandle
0x14000d38c  lea     rax, [rsp+130h+DestinationString]
0x14000d391  mov     [rsp+130h+ObjectAttributes.Attributes], 240h
0x14000d399  xorps   xmm0, xmm0
0x14000d39c  mov     [rsp+130h+ObjectAttributes.ObjectName], rax
0x14000d3a1  mov     r13d, 30h ; '0'
0x14000d3a7  mov     edx, 20019h; DesiredAccess
0x14000d3ac  mov     [rsp+130h+ObjectAttributes.Length], r13d
0x14000d3b1  movdqu  xmmword ptr [rsp+130h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000d3b7  call    cs:__imp_ZwOpenKey
0x14000d3be  nop     dword ptr [rax+rax+00h]
0x14000d3c3  mov     ebx, eax
0x14000d3c5  test    eax, eax
0x14000d3c7  js      loc_14000D543
0x14000d3cd  lea     eax, [r13-14h]
0x14000d3d1  xor     edi, edi
0x14000d3d3  mov     [rbp+30h+String.MaximumLength], ax
0x14000d3d7  xor     esi, esi
0x14000d3d9  lea     rax, [rbp+30h+var_50]
0x14000d3dd  mov     [rbp+30h+String.Buffer], rax
0x14000d3e1  movzx   eax, word ptr [r14]
0x14000d3e5  cmp     esi, eax
0x14000d3e7  jnb     loc_14000D534
0x14000d3ed  mov     eax, 1Ah
0x14000d3f2  lea     r8, [rbp+30h+String]; String
0x14000d3f6  lea     ecx, [rsi+1]; Value
0x14000d3f9  mov     [rbp+30h+String.Length], ax
0x14000d3fd  lea     edx, [rax-10h]; Base
0x14000d400  call    cs:__imp_RtlIntegerToUnicodeString
0x14000d407  nop     dword ptr [rax+rax+00h]
0x14000d40c  mov     ebx, eax
0x14000d40e  test    eax, eax
0x14000d410  js      loc_14000D543
0x14000d416  mov     rax, [rsp+130h+var_B8]
0x14000d41b  lea     r8, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x14000d420  mov     [rsp+130h+ObjectAttributes.RootDirectory], rax
0x14000d425  lea     rcx, [rsp+130h+Handle]; KeyHandle
0x14000d42a  lea     rax, [rbp+30h+String]
0x14000d42e  mov     [rsp+130h+ObjectAttributes.Length], r13d
0x14000d433  xorps   xmm0, xmm0
0x14000d436  mov     [rsp+130h+ObjectAttributes.ObjectName], rax
0x14000d43b  mov     edx, 20019h; DesiredAccess
0x14000d440  mov     [rsp+130h+ObjectAttributes.Attributes], 240h
0x14000d448  movdqu  xmmword ptr [rsp+130h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000d44e  call    cs:__imp_ZwOpenKey
0x14000d455  nop     dword ptr [rax+rax+00h]
0x14000d45a  mov     ebx, eax
0x14000d45c  test    eax, eax
0x14000d45e  js      loc_14000D543
0x14000d464  mov     rcx, [rsp+130h+Handle]; KeyHandle
0x14000d469  lea     r8, [rsp+130h+var_110]; unsigned int *
0x14000d46e  lea     rdx, aIdleexitlatenc; "IdleExitLatencyMs"
0x14000d475  call    ?PmQueryDWORDValueKey@@YAJPEAXPEBGPEAK@Z; PmQueryDWORDValueKey(void *,ushort const *,ulong *)
0x14000d47a  mov     ebx, eax
0x14000d47c  test    eax, eax
0x14000d47e  js      loc_14000D543
0x14000d484  imul    ecx, [rsp+130h+var_110], 2710h
0x14000d48c  lea     r8, [rsp+130h+var_110]; unsigned int *
0x14000d491  mov     edi, esi
0x14000d493  lea     rdx, aIdleexitenergy; "IdleExitEnergyMicroJoules"
0x14000d49a  shl     rdi, 5
0x14000d49e  add     rdi, 8
0x14000d4a2  add     rdi, r14
0x14000d4a5  mov     [rdi], rcx
0x14000d4a8  mov     rcx, [rsp+130h+Handle]; KeyHandle
0x14000d4ad  call    ?PmQueryDWORDValueKey@@YAJPEAXPEBGPEAK@Z; PmQueryDWORDValueKey(void *,ushort const *,ulong *)
0x14000d4b2  mov     ebx, eax
0x14000d4b4  test    eax, eax
0x14000d4b6  js      loc_14000D543
0x14000d4bc  imul    ecx, [rsp+130h+var_110], 2710h
0x14000d4c4  lea     r8, [rsp+130h+var_110]; unsigned int *
0x14000d4c9  lea     rdx, aIdletimelength; "IdleTimeLengthMs"
0x14000d4d0  mov     [rdi+8], rcx
0x14000d4d4  mov     rcx, [rsp+130h+Handle]; KeyHandle
0x14000d4d9  call    ?PmQueryDWORDValueKey@@YAJPEAXPEBGPEAK@Z; PmQueryDWORDValueKey(void *,ushort const *,ulong *)
0x14000d4de  mov     ebx, eax
0x14000d4e0  test    eax, eax
0x14000d4e2  js      short loc_14000D543
0x14000d4e4  imul    ecx, [rsp+130h+var_110], 2710h
0x14000d4ec  lea     r8, [rsp+130h+var_110]; unsigned int *
0x14000d4f1  lea     rdx, aIdlepowermw; "IdlePowerMw"
0x14000d4f8  mov     [rdi+10h], rcx
0x14000d4fc  mov     rcx, [rsp+130h+Handle]; KeyHandle
0x14000d501  call    ?PmQueryDWORDValueKey@@YAJPEAXPEBGPEAK@Z; PmQueryDWORDValueKey(void *,ushort const *,ulong *)
0x14000d506  mov     ebx, eax
0x14000d508  test    eax, eax
0x14000d50a  js      short loc_14000D543
0x14000d50c  mov     eax, [rsp+130h+var_110]
0x14000d510  mov     rcx, [rsp+130h+Handle]; Handle
0x14000d515  mov     [rdi+18h], eax
0x14000d518  call    cs:__imp_ZwClose
0x14000d51f  nop     dword ptr [rax+rax+00h]
0x14000d524  inc     esi
0x14000d526  mov     [rsp+130h+Handle], 0
0x14000d52f  jmp     loc_14000D3E1
0x14000d534  mov     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x14000d53c  jmp     short loc_14000D543
0x14000d53e  mov     ebx, 0C000000Dh
0x14000d543  mov     rcx, [rsp+130h+Handle]; Handle
0x14000d548  test    rcx, rcx
0x14000d54b  jz      short loc_14000D559
0x14000d54d  call    cs:__imp_ZwClose
0x14000d554  nop     dword ptr [rax+rax+00h]
0x14000d559  mov     rcx, [rsp+130h+KeyHandle]; Handle
0x14000d55e  test    rcx, rcx
0x14000d561  jz      short loc_14000D56F
0x14000d563  call    cs:__imp_ZwClose
0x14000d56a  nop     dword ptr [rax+rax+00h]
0x14000d56f  mov     eax, ebx
0x14000d571  mov     rcx, [rbp+30h+var_30]
0x14000d575  xor     rcx, rsp; StackCookie
0x14000d578  call    __security_check_cookie
0x14000d57d  lea     r11, [rsp+130h+var_20]
0x14000d585  mov     rbx, [r11+38h]
0x14000d589  mov     rsi, [r11+40h]
0x14000d58d  mov     rsp, r11
0x14000d590  pop     r15
0x14000d592  pop     r14
0x14000d594  pop     r13
0x14000d596  pop     rdi
0x14000d597  pop     rbp
0x14000d598  retn
```
