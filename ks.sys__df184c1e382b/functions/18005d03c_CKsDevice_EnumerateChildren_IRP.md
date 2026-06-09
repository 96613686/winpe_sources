# CKsDevice::EnumerateChildren(_IRP *)

- ea: `0x18005d03c`
- end: `0x18005d576`
- name: `?EnumerateChildren@CKsDevice@@QEAAJPEAU_IRP@@@Z`
- size: `1338`
- prototype: `__int64 __fastcall(CKsDevice *__hidden this, struct _IRP *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180048c60`

## callees

- `0x18000b7bc`
- `0x180013d70`
- `0x180019bd0`
- `0x18001a000`
- `0x18003abdc`
- `0x18003b25c`
- `0x18005d03c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18005d17b`
- `ntoskrnl!RtlInitUnicodeString` at `0x18005d17b`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x18005d11e`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x18005d11e`
- `ntoskrnl!ObfReferenceObject` at `0x18005d526`
- `ntoskrnl!ObfReferenceObject` at `0x18005d526`
- `ntoskrnl!ZwClose` at `0x18005d1d7`
- `ntoskrnl!ZwClose` at `0x18005d357`
- `ntoskrnl!ZwClose` at `0x18005d3b7`
- `ntoskrnl!ZwClose` at `0x18005d3db`
- `ntoskrnl!ZwClose` at `0x18005d3ec`
- `ntoskrnl!ZwClose` at `0x18005d1d7`
- `ntoskrnl!ZwClose` at `0x18005d357`
- `ntoskrnl!ZwClose` at `0x18005d3b7`
- `ntoskrnl!ZwClose` at `0x18005d3db`
- `ntoskrnl!ZwClose` at `0x18005d3ec`
- `ntoskrnl!ZwOpenKey` at `0x18005d1c0`
- `ntoskrnl!ZwOpenKey` at `0x18005d30a`
- `ntoskrnl!ZwOpenKey` at `0x18005d1c0`
- `ntoskrnl!ZwOpenKey` at `0x18005d30a`
- `ntoskrnl!ZwEnumerateKey` at `0x18005d224`
- `ntoskrnl!ZwEnumerateKey` at `0x18005d2a0`
- `ntoskrnl!ZwEnumerateKey` at `0x18005d224`
- `ntoskrnl!ZwEnumerateKey` at `0x18005d2a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005d346`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005d3a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005d3ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005d346`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005d3a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005d3ca`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005d253`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005d455`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005d253`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005d455`

## pseudocode

```c
__int64 __fastcall CKsDevice::EnumerateChildren(CKsDevice *this, struct _IRP *a2)
{
  struct _IRP *v2; // r13
  const char *v4; // rdx
  NTSTATUS v5; // eax
  int v6; // edx
  NTSTATUS v7; // ebx
  __int64 result; // rax
  ULONG i; // edi
  NTSTATUS v10; // eax
  ULONG v11; // ebx
  unsigned __int16 *PoolWithTag; // rax
  unsigned __int16 *v13; // r14
  unsigned __int16 *v14; // rdx
  __int64 v15; // r8
  int ChildPdo; // ebx
  int v17; // edx
  _DEVICE_OBJECT **p_m_pNextChildPdo; // rbx
  _DEVICE_OBJECT *m_pNextChildPdo; // rax
  PVOID DeviceExtension; // rdx
  ULONG v21; // ecx
  ULONG *v22; // rax
  int v23; // edx
  ULONG *v24; // rsi
  _DEVICE_OBJECT *v25; // rbx
  _DEVICE_OBJECT **v26; // r15
  PVOID v27; // r14
  const char *v28; // rdx
  _DEVICE_OBJECT *v29; // rcx
  ULONG ResultLength; // [rsp+40h] [rbp-C0h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  void *DeviceRegKey; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  struct _IRP *v36; // [rsp+A0h] [rbp-60h]
  __int128 KeyInformation; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v38; // [rsp+B8h] [rbp-48h]
  unsigned __int16 v39[128]; // [rsp+C0h] [rbp-40h] BYREF

  v36 = a2;
  v2 = a2;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DeviceRegKey = 0;
  KeyHandle = 0;
  Handle = 0;
  DestinationString = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    v4 = "has enumed";
    if ( !this->m_ChildEnumedFromRegistry )
      v4 = "1st Time";
    WPP_RECORDER_SF_qs(WPP_GLOBAL_Control->DeviceExtension, (_DWORD)v4, (unsigned int)"1st Time", 11);
  }
  if ( this->m_ChildEnumedFromRegistry )
  {
    p_m_pNextChildPdo = &this->m_pNextChildPdo;
    i = 0;
    m_pNextChildPdo = this->m_pNextChildPdo;
    while ( m_pNextChildPdo )
    {
      DeviceExtension = m_pNextChildPdo->DeviceExtension;
      v21 = i + 1;
      m_pNextChildPdo = (_DEVICE_OBJECT *)*((_QWORD *)DeviceExtension + 2);
      if ( *((_BYTE *)DeviceExtension + 44) )
        v21 = i;
      i = v21;
    }
  }
  else
  {
    v5 = IoOpenDeviceRegistryKey(this->m_Ext.Public.PhysicalDeviceObject, 2u, 0x1F0000u, &DeviceRegKey);
    this->m_ChildEnumedFromRegistry = 1;
    if ( v5 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          1,
          12,
          (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
      }
      return 3221225474LL;
    }
    RtlInitUnicodeString(&DestinationString, L"Enum");
    ObjectAttributes.RootDirectory = DeviceRegKey;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v7 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( v7 < 0 )
    {
      ZwClose(DeviceRegKey);
      return (unsigned int)v7;
    }
    for ( i = 0; ; ++i )
    {
      ResultLength = 0;
      v38 = 0;
      KeyInformation = 0;
      v10 = ZwEnumerateKey(KeyHandle, i, KeyBasicInformation, &KeyInformation, 0x18u, &ResultLength);
      if ( ((v10 + 0x80000000) & 0x80000000) == 0 && v10 != -2147483643 )
        break;
      v11 = ResultLength;
      PoolWithTag = (unsigned __int16 *)ExAllocatePoolWithTag((POOL_TYPE)1025, ResultLength, 0x6563534Bu);
      v13 = PoolWithTag;
      if ( !PoolWithTag )
        break;
      if ( !ExPoolZeroingNativelySupported )
        memset(PoolWithTag, 0, v11);
      if ( ZwEnumerateKey(KeyHandle, i, KeyBasicInformation, v13, ResultLength, &ResultLength) < 0 )
        goto LABEL_26;
      DestinationString.Length = v13[6];
      DestinationString.MaximumLength = v13[6];
      ObjectAttributes.Length = 48;
      DestinationString.Buffer = v13 + 8;
      ObjectAttributes.RootDirectory = KeyHandle;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes) < 0 )
      {
LABEL_26:
        ExFreePoolWithTag(v13, 0);
        break;
      }
      if ( (int)GetRegistryValue(Handle, v14, v15, v39) < 0 )
      {
        ExFreePoolWithTag(v13, 0);
        ZwClose(Handle);
        break;
      }
      ChildPdo = CKsDevice::CreateChildPdo(this, v39, i);
      ExFreePoolWithTag(v13, 0);
      ZwClose(Handle);
      if ( ChildPdo < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v17) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v17,
            1,
            13,
            (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
        }
        break;
      }
    }
    ZwClose(KeyHandle);
    ZwClose(DeviceRegKey);
    if ( !i )
      return 3221225474LL;
    this->m_IsParentFdo = 1;
    p_m_pNextChildPdo = &this->m_pNextChildPdo;
  }
  v22 = (ULONG *)ExAllocatePoolWithTag(PagedPool, 8 * i + 16, 0x7264534Bu);
  v24 = v22;
  if ( v22 )
  {
    memset(v22, 0, 8 * i + 16);
    v25 = *p_m_pNextChildPdo;
    v26 = (_DEVICE_OBJECT **)(v24 + 2);
    if ( v25 )
    {
      do
      {
        v27 = v25->DeviceExtension;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          v28 = File;
          if ( !*((_BYTE *)v27 + 44) )
            v28 = " not";
          WPP_RECORDER_SF_qs(WPP_GLOBAL_Control->DeviceExtension, (_DWORD)v28, (unsigned int)" not", 15);
        }
        if ( *((_BYTE *)v27 + 44) )
        {
          v25 = (_DEVICE_OBJECT *)*((_QWORD *)v27 + 2);
        }
        else
        {
          v29 = v25;
          *v26 = v25;
          v25 = (_DEVICE_OBJECT *)*((_QWORD *)v27 + 2);
          ObfReferenceObject(v29);
          ++v26;
        }
      }
      while ( v25 );
      v2 = v36;
    }
    *v24 = i;
    result = 0;
    v2->IoStatus.Status = 0;
    v2->IoStatus.Information = (ULONG_PTR)v24;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v23) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v23,
        1,
        14,
        (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    }
    return 3221225626LL;
  }
  return result;
}

```

## disassembly

```asm
0x18005d03c  mov     [rsp-8+arg_10], rbx
0x18005d041  push    rbp
0x18005d042  push    rsi
0x18005d043  push    rdi
0x18005d044  push    r12
0x18005d046  push    r13
0x18005d048  push    r14
0x18005d04a  push    r15
0x18005d04c  lea     rbp, [rsp-0D0h]
0x18005d054  sub     rsp, 1D0h
0x18005d05b  mov     rax, cs:__security_cookie
0x18005d062  xor     rax, rsp
0x18005d065  mov     [rbp+100h+var_40], rax
0x18005d06c  xorps   xmm0, xmm0
0x18005d06f  mov     [rbp+100h+var_160], rdx
0x18005d073  xor     r12d, r12d
0x18005d076  mov     r13, rdx
0x18005d079  movups  xmmword ptr [rsp+200h+ObjectAttributes.Length], xmm0
0x18005d07e  mov     [rsp+200h+DeviceRegKey], r12
0x18005d083  mov     rsi, rcx
0x18005d086  movups  xmmword ptr [rbp+100h+ObjectAttributes.ObjectName], xmm0
0x18005d08a  mov     [rsp+200h+KeyHandle], r12
0x18005d08f  movups  xmmword ptr [rbp+100h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005d093  mov     [rsp+200h+Handle], r12
0x18005d098  movups  xmmword ptr [rsp+200h+DestinationString.Length], xmm0
0x18005d09d  lea     rbx, WPP_RECORDER_INITIALIZED
0x18005d0a4  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x18005d0ab  jz      short loc_18005D0F3
0x18005d0ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d0b4  cmp     [rcx+48h], r12w
0x18005d0b9  jz      short loc_18005D0F3
0x18005d0bb  cmp     [rsi+45Ch], r12b
0x18005d0c2  lea     r8, a1stTime; "1st Time"
0x18005d0c9  mov     rax, [rsi+0E0h]
0x18005d0d0  lea     rdx, aHasEnumed; "has enumed"
0x18005d0d7  mov     rcx, [rcx+40h]
0x18005d0db  lea     r9d, [r12+0Bh]
0x18005d0e0  cmovz   rdx, r8
0x18005d0e4  mov     [rsp+200h+var_1D0], rdx
0x18005d0e9  mov     [rsp+200h+ResultLength], rax
0x18005d0ee  call    WPP_RECORDER_SF_qs
0x18005d0f3  lea     r15, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005d0fa  cmp     [rsi+45Ch], r12b
0x18005d101  jnz     loc_18005D416
0x18005d107  mov     rcx, [rsi+0E8h]; DeviceObject
0x18005d10e  lea     r9, [rsp+200h+DeviceRegKey]; DeviceRegKey
0x18005d113  mov     edx, 2; DevInstKeyType
0x18005d118  mov     r8d, 1F0000h; DesiredAccess
0x18005d11e  call    cs:__imp_IoOpenDeviceRegistryKey
0x18005d125  nop     dword ptr [rax+rax+00h]
0x18005d12a  mov     byte ptr [rsi+45Ch], 1
0x18005d131  test    eax, eax
0x18005d133  jns     short loc_18005D16F
0x18005d135  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x18005d13c  jz      loc_18005D3FC
0x18005d142  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d149  lea     r15, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005d150  mov     r9d, 0Ch
0x18005d156  mov     qword ptr [rsp+200h+Length], r15
0x18005d15b  mov     dl, 2
0x18005d15d  mov     rcx, [rcx+40h]
0x18005d161  lea     r8d, [r9-0Bh]
0x18005d165  call    WPP_RECORDER_SF_
0x18005d16a  jmp     loc_18005D3FC
0x18005d16f  lea     rdx, aEnum; "Enum"
0x18005d176  lea     rcx, [rsp+200h+DestinationString]; DestinationString
0x18005d17b  call    cs:__imp_RtlInitUnicodeString
0x18005d182  nop     dword ptr [rax+rax+00h]
0x18005d187  mov     rax, [rsp+200h+DeviceRegKey]
0x18005d18c  lea     r8, [rsp+200h+ObjectAttributes]; ObjectAttributes
0x18005d191  mov     [rsp+200h+ObjectAttributes.RootDirectory], rax
0x18005d196  lea     rcx, [rsp+200h+KeyHandle]; KeyHandle
0x18005d19b  lea     rax, [rsp+200h+DestinationString]
0x18005d1a0  mov     [rsp+200h+ObjectAttributes.Length], 30h ; '0'
0x18005d1a8  xorps   xmm0, xmm0
0x18005d1ab  mov     [rbp+100h+ObjectAttributes.ObjectName], rax
0x18005d1af  mov     edx, 20019h; DesiredAccess
0x18005d1b4  mov     [rbp+100h+ObjectAttributes.Attributes], 240h
0x18005d1bb  movdqu  xmmword ptr [rbp+100h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005d1c0  call    cs:__imp_ZwOpenKey
0x18005d1c7  nop     dword ptr [rax+rax+00h]
0x18005d1cc  mov     ebx, eax
0x18005d1ce  test    eax, eax
0x18005d1d0  jns     short loc_18005D1EA
0x18005d1d2  mov     rcx, [rsp+200h+DeviceRegKey]; Handle
0x18005d1d7  call    cs:__imp_ZwClose
0x18005d1de  nop     dword ptr [rax+rax+00h]
0x18005d1e3  mov     eax, ebx
0x18005d1e5  jmp     loc_18005D54B
0x18005d1ea  mov     edi, r12d
0x18005d1ed  mov     rcx, [rsp+200h+KeyHandle]; KeyHandle
0x18005d1f2  lea     r9, [rbp+100h+KeyInformation]; KeyInformation
0x18005d1f6  xor     eax, eax
0x18005d1f8  mov     [rsp+200h+var_1C0], r12d
0x18005d1fd  mov     [rbp+100h+var_148], rax
0x18005d201  xorps   xmm0, xmm0
0x18005d204  lea     rax, [rsp+200h+var_1C0]
0x18005d209  xor     r8d, r8d; KeyInformationClass
0x18005d20c  mov     [rsp+200h+ResultLength], rax; ResultLength
0x18005d211  mov     edx, edi; Index
0x18005d213  mov     [rsp+200h+Length], 18h; Length
0x18005d21b  mov     ebx, 80000000h
0x18005d220  movups  [rbp+100h+KeyInformation], xmm0
0x18005d224  call    cs:__imp_ZwEnumerateKey
0x18005d22b  nop     dword ptr [rax+rax+00h]
0x18005d230  lea     ecx, [rax+rbx]
0x18005d233  test    ebx, ecx
0x18005d235  jnz     short loc_18005D242
0x18005d237  cmp     eax, 80000005h
0x18005d23c  jnz     loc_18005D3D6
0x18005d242  mov     ebx, [rsp+200h+var_1C0]
0x18005d246  mov     r8d, 6563534Bh; Tag
0x18005d24c  mov     edx, ebx; NumberOfBytes
0x18005d24e  mov     ecx, 401h; PoolType
0x18005d253  call    cs:__imp_ExAllocatePoolWithTag
0x18005d25a  nop     dword ptr [rax+rax+00h]
0x18005d25f  mov     r14, rax
0x18005d262  test    rax, rax
0x18005d265  jz      loc_18005D3D6
0x18005d26b  cmp     cs:ExPoolZeroingNativelySupported, r12b
0x18005d272  jnz     short loc_18005D281
0x18005d274  mov     r8d, ebx; Size
0x18005d277  xor     edx, edx; Val
0x18005d279  mov     rcx, rax; void *
0x18005d27c  call    memset
0x18005d281  mov     rcx, [rsp+200h+KeyHandle]; KeyHandle
0x18005d286  lea     rax, [rsp+200h+var_1C0]
0x18005d28b  mov     [rsp+200h+ResultLength], rax; ResultLength
0x18005d290  mov     r9, r14; KeyInformation
0x18005d293  mov     eax, [rsp+200h+var_1C0]
0x18005d297  xor     r8d, r8d; KeyInformationClass
0x18005d29a  mov     edx, edi; Index
0x18005d29c  mov     [rsp+200h+Length], eax; unsigned int
0x18005d2a0  call    cs:__imp_ZwEnumerateKey
0x18005d2a7  nop     dword ptr [rax+rax+00h]
0x18005d2ac  test    eax, eax
0x18005d2ae  js      loc_18005D3C5
0x18005d2b4  movzx   eax, word ptr [r14+0Ch]
0x18005d2b9  lea     r8, [rsp+200h+ObjectAttributes]; ObjectAttributes
0x18005d2be  mov     [rsp+200h+DestinationString.Length], ax
0x18005d2c3  lea     rcx, [rsp+200h+Handle]; KeyHandle
0x18005d2c8  movzx   eax, word ptr [r14+0Ch]
0x18005d2cd  xorps   xmm0, xmm0
0x18005d2d0  mov     [rsp+200h+DestinationString.MaximumLength], ax
0x18005d2d5  mov     edx, 20019h; DesiredAccess
0x18005d2da  lea     rax, [r14+10h]
0x18005d2de  mov     [rsp+200h+ObjectAttributes.Length], 30h ; '0'
0x18005d2e6  mov     [rsp+200h+DestinationString.Buffer], rax
0x18005d2eb  mov     rax, [rsp+200h+KeyHandle]
0x18005d2f0  mov     [rsp+200h+ObjectAttributes.RootDirectory], rax
0x18005d2f5  lea     rax, [rsp+200h+DestinationString]
0x18005d2fa  mov     [rbp+100h+ObjectAttributes.ObjectName], rax
0x18005d2fe  mov     [rbp+100h+ObjectAttributes.Attributes], 240h
0x18005d305  movdqu  xmmword ptr [rbp+100h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005d30a  call    cs:__imp_ZwOpenKey
0x18005d311  nop     dword ptr [rax+rax+00h]
0x18005d316  test    eax, eax
0x18005d318  js      loc_18005D3C5
0x18005d31e  mov     rcx, [rsp+200h+Handle]; KeyHandle
0x18005d323  lea     r9, [rbp+100h+var_140]; void *
0x18005d327  call    ?GetRegistryValue@@YAJPEAXPEAGK0K@Z; GetRegistryValue(void *,ushort *,ulong,void *,ulong)
0x18005d32c  test    eax, eax
0x18005d32e  js      short loc_18005D3A1
0x18005d330  mov     r8d, edi; unsigned int
0x18005d333  lea     rdx, [rbp+100h+var_140]; unsigned __int16 *
0x18005d337  mov     rcx, rsi; this
0x18005d33a  call    ?CreateChildPdo@CKsDevice@@QEAAJPEAGK@Z; CKsDevice::CreateChildPdo(ushort *,ulong)
0x18005d33f  xor     edx, edx; Tag
0x18005d341  mov     rcx, r14; P
0x18005d344  mov     ebx, eax
0x18005d346  call    cs:__imp_ExFreePoolWithTag
0x18005d34d  nop     dword ptr [rax+rax+00h]
0x18005d352  mov     rcx, [rsp+200h+Handle]; Handle
0x18005d357  call    cs:__imp_ZwClose
0x18005d35e  nop     dword ptr [rax+rax+00h]
0x18005d363  test    ebx, ebx
0x18005d365  js      short loc_18005D36E
0x18005d367  inc     edi
0x18005d369  jmp     loc_18005D1ED
0x18005d36e  lea     rax, WPP_RECORDER_INITIALIZED
0x18005d375  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005d37c  jz      short loc_18005D3D6
0x18005d37e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d385  mov     r9d, 0Dh
0x18005d38b  mov     dl, 2
0x18005d38d  mov     qword ptr [rsp+200h+Length], r15
0x18005d392  mov     rcx, [rcx+40h]
0x18005d396  lea     r8d, [r9-0Ch]
0x18005d39a  call    WPP_RECORDER_SF_
0x18005d39f  jmp     short loc_18005D3D6
0x18005d3a1  xor     edx, edx; Tag
0x18005d3a3  mov     rcx, r14; P
0x18005d3a6  call    cs:__imp_ExFreePoolWithTag
0x18005d3ad  nop     dword ptr [rax+rax+00h]
0x18005d3b2  mov     rcx, [rsp+200h+Handle]; Handle
0x18005d3b7  call    cs:__imp_ZwClose
0x18005d3be  nop     dword ptr [rax+rax+00h]
0x18005d3c3  jmp     short loc_18005D3D6
0x18005d3c5  xor     edx, edx; Tag
0x18005d3c7  mov     rcx, r14; P
0x18005d3ca  call    cs:__imp_ExFreePoolWithTag
0x18005d3d1  nop     dword ptr [rax+rax+00h]
0x18005d3d6  mov     rcx, [rsp+200h+KeyHandle]; Handle
0x18005d3db  call    cs:__imp_ZwClose
0x18005d3e2  nop     dword ptr [rax+rax+00h]
0x18005d3e7  mov     rcx, [rsp+200h+DeviceRegKey]; Handle
0x18005d3ec  call    cs:__imp_ZwClose
0x18005d3f3  nop     dword ptr [rax+rax+00h]
0x18005d3f8  test    edi, edi
0x18005d3fa  jnz     short loc_18005D406
0x18005d3fc  mov     eax, 0C0000002h
0x18005d401  jmp     loc_18005D54B
0x18005d406  mov     byte ptr [rsi+312h], 1
0x18005d40d  lea     rbx, [rsi+460h]
0x18005d414  jmp     short loc_18005D43E
0x18005d416  lea     rbx, [rsi+460h]
0x18005d41d  mov     edi, r12d
0x18005d420  mov     rax, [rbx]
0x18005d423  jmp     short loc_18005D439
0x18005d425  mov     rdx, [rax+40h]
0x18005d429  lea     ecx, [rdi+1]
0x18005d42c  cmp     [rdx+2Ch], r12b
0x18005d430  mov     rax, [rdx+10h]
0x18005d434  cmovnz  ecx, edi
0x18005d437  mov     edi, ecx
0x18005d439  test    rax, rax
0x18005d43c  jnz     short loc_18005D425
0x18005d43e  lea     eax, ds:10h[rdi*8]
0x18005d445  mov     r8d, 7264534Bh; Tag
0x18005d44b  mov     edx, eax; NumberOfBytes
0x18005d44d  mov     ecx, 1; PoolType
0x18005d452  mov     r14d, eax
0x18005d455  call    cs:__imp_ExAllocatePoolWithTag
0x18005d45c  nop     dword ptr [rax+rax+00h]
0x18005d461  mov     rsi, rax
0x18005d464  test    rax, rax
0x18005d467  jnz     short loc_18005D4A2
0x18005d469  lea     rax, WPP_RECORDER_INITIALIZED
0x18005d470  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005d477  jz      short loc_18005D498
0x18005d479  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d480  lea     r9d, [rsi+0Eh]
0x18005d484  lea     r8d, [rsi+1]
0x18005d488  mov     qword ptr [rsp+200h+Length], r15
0x18005d48d  mov     dl, 2
0x18005d48f  mov     rcx, [rcx+40h]
0x18005d493  call    WPP_RECORDER_SF_
0x18005d498  mov     eax, 0C000009Ah
0x18005d49d  jmp     loc_18005D54B
0x18005d4a2  mov     r8, r14; Size
0x18005d4a5  xor     edx, edx; Val
0x18005d4a7  mov     rcx, rsi; void *
0x18005d4aa  call    memset
0x18005d4af  mov     rbx, [rbx]
0x18005d4b2  lea     r15, [rsi+8]
0x18005d4b6  test    rbx, rbx
0x18005d4b9  jz      loc_18005D53F
0x18005d4bf  lea     r13, WPP_RECORDER_INITIALIZED
0x18005d4c6  mov     r14, [rbx+40h]
0x18005d4ca  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18005d4d1  jz      short loc_18005D510
0x18005d4d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d4da  cmp     [rcx+48h], r12w
0x18005d4df  jz      short loc_18005D510
0x18005d4e1  cmp     [r14+2Ch], r12b
0x18005d4e5  lea     r8, aNot; " not"
0x18005d4ec  mov     rcx, [rcx+40h]
0x18005d4f0  lea     rdx, File
0x18005d4f7  cmovz   rdx, r8
0x18005d4fb  mov     r9d, 0Fh
0x18005d501  mov     [rsp+200h+var_1D0], rdx
0x18005d506  mov     [rsp+200h+ResultLength], rbx
0x18005d50b  call    WPP_RECORDER_SF_qs
0x18005d510  cmp     [r14+2Ch], r12b
0x18005d514  jz      short loc_18005D51C
0x18005d516  mov     rbx, [r14+10h]
0x18005d51a  jmp     short loc_18005D536
0x18005d51c  mov     rcx, rbx; Object
0x18005d51f  mov     [r15], rbx
0x18005d522  mov     rbx, [r14+10h]
0x18005d526  call    cs:__imp_ObfReferenceObject
0x18005d52d  nop     dword ptr [rax+rax+00h]
0x18005d532  add     r15, 8
0x18005d536  test    rbx, rbx
0x18005d539  jnz     short loc_18005D4C6
0x18005d53b  mov     r13, [rbp+100h+var_160]
0x18005d53f  mov     [rsi], edi
0x18005d541  xor     eax, eax
0x18005d543  mov     [r13+30h], r12d
0x18005d547  mov     [r13+38h], rsi
0x18005d54b  mov     rcx, [rbp+100h+var_40]
0x18005d552  xor     rcx, rsp; StackCookie
0x18005d555  call    __security_check_cookie
0x18005d55a  mov     rbx, [rsp+200h+arg_10]
0x18005d562  add     rsp, 1D0h
0x18005d569  pop     r15
0x18005d56b  pop     r14
0x18005d56d  pop     r13
0x18005d56f  pop     r12
0x18005d571  pop     rdi
  ... truncated ...
```
