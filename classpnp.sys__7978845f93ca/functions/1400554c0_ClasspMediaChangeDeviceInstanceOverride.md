# ClasspMediaChangeDeviceInstanceOverride

- ea: `0x1400554c0`
- end: `0x14005583d`
- name: `ClasspMediaChangeDeviceInstanceOverride`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400543e0`

## callees

- `0x14001fbf4`
- `0x140022748`
- `0x14003e430`
- `0x14003e470`
- `0x14003e940`
- `0x1400554c0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140055599`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400556aa`
- `ntoskrnl!RtlInitUnicodeString` at `0x140055599`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400556aa`
- `ntoskrnl!ZwCreateKey` at `0x1400555f2`
- `ntoskrnl!ZwCreateKey` at `0x1400555f2`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140055533`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140055533`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400556da`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400556ba`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400556ba`
- `ntoskrnl!ZwClose` at `0x140055706`
- `ntoskrnl!ZwClose` at `0x14005571c`
- `ntoskrnl!ZwClose` at `0x140055706`
- `ntoskrnl!ZwClose` at `0x14005571c`

## string_xrefs

- `0x140055694`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
__int64 __fastcall ClasspMediaChangeDeviceInstanceOverride(__int64 a1, _BYTE *a2)
{
  struct _DEVICE_OBJECT *v2; // rcx
  NTSTATUS v4; // eax
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx
  unsigned int i; // edi
  int *v8; // rax
  void *v9; // rbx
  PVOID SystemRoutineAddress; // rax
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  const char *v13; // r9
  __int64 result; // rax
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+44h] [rbp-BCh] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  void *DeviceRegKey; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING SystemRoutineName; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v22[22]; // [rsp+B0h] [rbp-50h] BYREF

  v2 = *(struct _DEVICE_OBJECT **)(a1 + 512);
  DeviceRegKey = 0;
  KeyHandle = 0;
  v16 = 0;
  v15 = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  v4 = IoOpenDeviceRegistryKey(v2, 1u, 0xF003Fu, &DeviceRegKey);
  if ( v4 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"MediaChangeNotification");
    ObjectAttributes.RootDirectory = DeviceRegKey;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v4 = ZwCreateKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0, 0, 0, 0);
    if ( v4 >= 0 )
    {
      for ( i = 0; i < 2; ++i )
      {
        memset(v22, 0, 0xA8u);
        LODWORD(v22[1]) = 288;
        LODWORD(v22[4]) = 0x4000000;
        LODWORD(v22[6]) = 0;
        if ( i )
        {
          v22[2] = L"AlwaysEnableMCN";
          v22[3] = &v16;
          v8 = &v16;
        }
        else
        {
          v22[2] = L"AlwaysDisableMCN";
          v22[3] = &v15;
          v8 = &v15;
        }
        v9 = KeyHandle;
        v22[5] = v8;
        SystemRoutineName = 0;
        RtlInitUnicodeString(&SystemRoutineName, L"RtlQueryRegistryValuesEx");
        SystemRoutineAddress = MmGetSystemRoutineAddress(&SystemRoutineName);
        if ( !SystemRoutineAddress )
          SystemRoutineAddress = RtlQueryRegistryValues;
        ((void (__fastcall *)(__int64, void *, _QWORD *, _QWORD, _QWORD))SystemRoutineAddress)(
          0x40000000,
          v9,
          v22,
          0,
          0);
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v6 = 76;
        goto LABEL_6;
      }
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v6 = 75;
LABEL_6:
      WPP_SF_d(v5->AttachedDevice, v6, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids, (unsigned int)v4);
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( DeviceRegKey )
    ZwClose(DeviceRegKey);
  if ( v16 )
  {
    if ( v15 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu)
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        goto LABEL_40;
      }
      v12 = 77;
      v13 = "Both Enable and Disable set -- DISABLE";
LABEL_39:
      WPP_SF_s(v11->AttachedDevice, v12, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids, v13);
LABEL_40:
      result = 0;
      *a2 = 0;
      return result;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids, "ENABLE");
    }
    result = 0;
    *a2 = 1;
  }
  else
  {
    if ( v15 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu)
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        goto LABEL_40;
      }
      v12 = 78;
      v13 = "DISABLE";
      goto LABEL_39;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids, "DEFAULT");
    }
    return 3221225473LL;
  }
  return result;
}

```

## disassembly

```asm
0x1400554c0  mov     [rsp-8+arg_10], rbx
0x1400554c5  mov     [rsp-8+arg_18], rsi
0x1400554ca  push    rbp
0x1400554cb  push    rdi
0x1400554cc  push    r12
0x1400554ce  push    r13
0x1400554d0  push    r14
0x1400554d2  lea     rbp, [rsp-70h]
0x1400554d7  sub     rsp, 170h
0x1400554de  mov     rax, cs:__security_cookie
0x1400554e5  xor     rax, rsp
0x1400554e8  mov     [rbp+90h+var_30], rax
0x1400554ec  mov     rcx, [rcx+200h]; DeviceObject
0x1400554f3  lea     r9, [rsp+190h+DeviceRegKey]; DeviceRegKey
0x1400554f8  xorps   xmm0, xmm0
0x1400554fb  xor     r14d, r14d
0x1400554fe  xor     eax, eax
0x140055500  mov     [rsp+190h+DeviceRegKey], r14
0x140055505  mov     rsi, rdx
0x140055508  mov     [rsp+190h+KeyHandle], r14
0x14005550d  movups  xmmword ptr [rsp+190h+ObjectAttributes.ObjectName], xmm0
0x140055512  mov     r8d, 0F003Fh; DesiredAccess
0x140055518  mov     [rsp+190h+var_14C], r14d
0x14005551d  lea     edx, [rax+1]; DevInstKeyType
0x140055520  mov     [rsp+190h+var_150], r14d
0x140055525  movups  xmmword ptr [rsp+190h+ObjectAttributes.Length], xmm0
0x14005552a  movups  xmmword ptr [rsp+190h+ObjectAttributes+1Ch], xmm0
0x14005552f  movups  xmmword ptr [rbp+90h+DestinationString.Length], xmm0
0x140055533  call    cs:__imp_IoOpenDeviceRegistryKey
0x14005553a  nop     dword ptr [rax+rax+00h]
0x14005553f  lea     r13, WPP_GLOBAL_Control
0x140055546  lea     rbx, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x14005554d  test    eax, eax
0x14005554f  jns     short loc_14005558E
0x140055551  mov     rcx, cs:WPP_GLOBAL_Control
0x140055558  cmp     rcx, r13
0x14005555b  jz      loc_1400556FC
0x140055561  bt      dword ptr [rcx+2Ch], 0Ch
0x140055566  jnb     loc_1400556FC
0x14005556c  cmp     byte ptr [rcx+29h], 4
0x140055570  jb      loc_1400556FC
0x140055576  lea     edx, [r14+4Bh]
0x14005557a  mov     rcx, [rcx+18h]
0x14005557e  mov     r9d, eax
0x140055581  mov     r8, rbx
0x140055584  call    WPP_SF_d
0x140055589  jmp     loc_1400556FC
0x14005558e  lea     rdx, aMediachangenot; "MediaChangeNotification"
0x140055595  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x140055599  call    cs:__imp_RtlInitUnicodeString
0x1400555a0  nop     dword ptr [rax+rax+00h]
0x1400555a5  mov     rax, [rsp+190h+DeviceRegKey]
0x1400555aa  lea     r8, [rsp+190h+ObjectAttributes]; ObjectAttributes
0x1400555af  mov     [rsp+190h+ObjectAttributes.RootDirectory], rax
0x1400555b4  lea     rcx, [rsp+190h+KeyHandle]; KeyHandle
0x1400555b9  lea     rax, [rbp+90h+DestinationString]
0x1400555bd  mov     [rsp+190h+Disposition], r14; Disposition
0x1400555c2  xorps   xmm0, xmm0
0x1400555c5  mov     [rsp+190h+CreateOptions], r14d; CreateOptions
0x1400555ca  xor     r9d, r9d; TitleIndex
0x1400555cd  mov     [rsp+190h+ObjectAttributes.ObjectName], rax
0x1400555d2  mov     edx, 20019h; DesiredAccess
0x1400555d7  mov     [rsp+190h+ObjectAttributes.Length], 30h ; '0'
0x1400555df  mov     [rsp+190h+ObjectAttributes.Attributes], 240h
0x1400555e7  movdqu  xmmword ptr [rsp+190h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400555ed  mov     [rsp+190h+Class], r14; Class
0x1400555f2  call    cs:__imp_ZwCreateKey
0x1400555f9  nop     dword ptr [rax+rax+00h]
0x1400555fe  test    eax, eax
0x140055600  jns     short loc_140055631
0x140055602  mov     rcx, cs:WPP_GLOBAL_Control
0x140055609  cmp     rcx, r13
0x14005560c  jz      loc_1400556FC
0x140055612  bt      dword ptr [rcx+2Ch], 0Ch
0x140055617  jnb     loc_1400556FC
0x14005561d  cmp     byte ptr [rcx+29h], 4
0x140055621  jb      loc_1400556FC
0x140055627  mov     edx, 4Ch ; 'L'
0x14005562c  jmp     loc_14005557A
0x140055631  mov     edi, r14d
0x140055634  xor     edx, edx; Val
0x140055636  lea     rcx, [rbp+90h+var_E0]; void *
0x14005563a  mov     r8d, 0A8h; Size
0x140055640  call    memset
0x140055645  mov     [rbp+90h+var_D8], 120h
0x14005564c  mov     [rbp+90h+var_C0], 4000000h
0x140055653  mov     [rbp+90h+var_B0], r14d
0x140055657  test    edi, edi
0x140055659  jnz     short loc_140055676
0x14005565b  lea     rax, aAlwaysdisablem; "AlwaysDisableMCN"
0x140055662  mov     [rbp+90h+var_D0], rax
0x140055666  lea     rax, [rsp+190h+var_150]
0x14005566b  mov     [rbp+90h+var_C8], rax
0x14005566f  lea     rax, [rsp+190h+var_150]
0x140055674  jmp     short loc_14005568F
0x140055676  lea     rax, aAlwaysenablemc; "AlwaysEnableMCN"
0x14005567d  mov     [rbp+90h+var_D0], rax
0x140055681  lea     rax, [rsp+190h+var_14C]
0x140055686  mov     [rbp+90h+var_C8], rax
0x14005568a  lea     rax, [rsp+190h+var_14C]
0x14005568f  mov     rbx, [rsp+190h+KeyHandle]
0x140055694  lea     rdx, SourceString; "RtlQueryRegistryValuesEx"
0x14005569b  xorps   xmm0, xmm0
0x14005569e  mov     [rbp+90h+var_B8], rax
0x1400556a2  lea     rcx, [rbp+90h+SystemRoutineName]; DestinationString
0x1400556a6  movups  xmmword ptr [rbp+90h+SystemRoutineName.Length], xmm0
0x1400556aa  call    cs:__imp_RtlInitUnicodeString
0x1400556b1  nop     dword ptr [rax+rax+00h]
0x1400556b6  lea     rcx, [rbp+90h+SystemRoutineName]; SystemRoutineName
0x1400556ba  call    cs:__imp_MmGetSystemRoutineAddress
0x1400556c1  nop     dword ptr [rax+rax+00h]
0x1400556c6  lea     r8, [rbp+90h+var_E0]
0x1400556ca  mov     [rsp+190h+Class], r14
0x1400556cf  test    rax, rax
0x1400556d2  mov     rdx, rbx
0x1400556d5  mov     ecx, 40000000h
0x1400556da  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x1400556e2  xor     r9d, r9d
0x1400556e5  call    _guard_dispatch_icall
0x1400556ea  inc     edi
0x1400556ec  cmp     edi, 2
0x1400556ef  jb      loc_140055634
0x1400556f5  lea     rbx, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x1400556fc  mov     rcx, [rsp+190h+KeyHandle]; Handle
0x140055701  test    rcx, rcx
0x140055704  jz      short loc_140055712
0x140055706  call    cs:__imp_ZwClose
0x14005570d  nop     dword ptr [rax+rax+00h]
0x140055712  mov     rcx, [rsp+190h+DeviceRegKey]; Handle
0x140055717  test    rcx, rcx
0x14005571a  jz      short loc_140055728
0x14005571c  call    cs:__imp_ZwClose
0x140055723  nop     dword ptr [rax+rax+00h]
0x140055728  cmp     [rsp+190h+var_14C], r14d
0x14005572d  jz      short loc_14005579E
0x14005572f  cmp     [rsp+190h+var_150], r14d
0x140055734  jz      short loc_140055765
0x140055736  mov     rcx, cs:WPP_GLOBAL_Control
0x14005573d  cmp     rcx, r13
0x140055740  jz      loc_1400557D6
0x140055746  bt      dword ptr [rcx+2Ch], 0Ch
0x14005574b  jnb     loc_1400557D6
0x140055751  cmp     byte ptr [rcx+29h], 4
0x140055755  jb      short loc_1400557D6
0x140055757  mov     edx, 4Dh ; 'M'
0x14005575c  lea     r9, aBothEnableAndD; "Both Enable and Disable set -- DISABLE"
0x140055763  jmp     short loc_1400557CA
0x140055765  mov     rcx, cs:WPP_GLOBAL_Control
0x14005576c  cmp     rcx, r13
0x14005576f  jz      short loc_140055796
0x140055771  bt      dword ptr [rcx+2Ch], 0Ch
0x140055776  jnb     short loc_140055796
0x140055778  cmp     byte ptr [rcx+29h], 4
0x14005577c  jb      short loc_140055796
0x14005577e  mov     rcx, [rcx+18h]
0x140055782  lea     r9, aEnable; "ENABLE"
0x140055789  mov     edx, 4Fh ; 'O'
0x14005578e  mov     r8, rbx
0x140055791  call    WPP_SF_s
0x140055796  mov     eax, r14d
0x140055799  mov     byte ptr [rsi], 1
0x14005579c  jmp     short loc_140055814
0x14005579e  cmp     [rsp+190h+var_150], r14d
0x1400557a3  jz      short loc_1400557DE
0x1400557a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400557ac  cmp     rcx, r13
0x1400557af  jz      short loc_1400557D6
0x1400557b1  bt      dword ptr [rcx+2Ch], 0Ch
0x1400557b6  jnb     short loc_1400557D6
0x1400557b8  cmp     byte ptr [rcx+29h], 4
0x1400557bc  jb      short loc_1400557D6
0x1400557be  mov     edx, 4Eh ; 'N'
0x1400557c3  lea     r9, aDisable; "DISABLE"
0x1400557ca  mov     rcx, [rcx+18h]
0x1400557ce  mov     r8, rbx
0x1400557d1  call    WPP_SF_s
0x1400557d6  mov     eax, r14d
0x1400557d9  mov     [rsi], r14b
0x1400557dc  jmp     short loc_140055814
0x1400557de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400557e5  cmp     rcx, r13
0x1400557e8  jz      short loc_14005580F
0x1400557ea  bt      dword ptr [rcx+2Ch], 0Ch
0x1400557ef  jnb     short loc_14005580F
0x1400557f1  cmp     byte ptr [rcx+29h], 4
0x1400557f5  jb      short loc_14005580F
0x1400557f7  mov     rcx, [rcx+18h]
0x1400557fb  lea     r9, aDefault; "DEFAULT"
0x140055802  mov     edx, 50h ; 'P'
0x140055807  mov     r8, rbx
0x14005580a  call    WPP_SF_s
0x14005580f  mov     eax, 0C0000001h
0x140055814  mov     rcx, [rbp+90h+var_30]
0x140055818  xor     rcx, rsp; StackCookie
0x14005581b  call    __security_check_cookie
0x140055820  lea     r11, [rsp+190h+var_20]
0x140055828  mov     rbx, [r11+40h]
0x14005582c  mov     rsi, [r11+48h]
0x140055830  mov     rsp, r11
0x140055833  pop     r14
0x140055835  pop     r13
0x140055837  pop     r12
0x140055839  pop     rdi
0x14005583a  pop     rbp
0x14005583b  retn
```
