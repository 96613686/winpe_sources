# CKsDevice::EnumerateChildren(_IRP *)

- ea: `0x18005ce9c`
- end: `0x18005d3d6`
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
- `0x180019b80`
- `0x180019fc0`
- `0x18003abec`
- `0x18003b26c`
- `0x18005ce9c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18005cfdb`
- `ntoskrnl!RtlInitUnicodeString` at `0x18005cfdb`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x18005cf7e`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x18005cf7e`
- `ntoskrnl!ObfReferenceObject` at `0x18005d386`
- `ntoskrnl!ObfReferenceObject` at `0x18005d386`
- `ntoskrnl!ZwClose` at `0x18005d037`
- `ntoskrnl!ZwClose` at `0x18005d1b7`
- `ntoskrnl!ZwClose` at `0x18005d217`
- `ntoskrnl!ZwClose` at `0x18005d23b`
- `ntoskrnl!ZwClose` at `0x18005d24c`
- `ntoskrnl!ZwClose` at `0x18005d037`
- `ntoskrnl!ZwClose` at `0x18005d1b7`
- `ntoskrnl!ZwClose` at `0x18005d217`
- `ntoskrnl!ZwClose` at `0x18005d23b`
- `ntoskrnl!ZwClose` at `0x18005d24c`
- `ntoskrnl!ZwOpenKey` at `0x18005d020`
- `ntoskrnl!ZwOpenKey` at `0x18005d16a`
- `ntoskrnl!ZwOpenKey` at `0x18005d020`
- `ntoskrnl!ZwOpenKey` at `0x18005d16a`
- `ntoskrnl!ZwEnumerateKey` at `0x18005d084`
- `ntoskrnl!ZwEnumerateKey` at `0x18005d100`
- `ntoskrnl!ZwEnumerateKey` at `0x18005d084`
- `ntoskrnl!ZwEnumerateKey` at `0x18005d100`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005d1a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005d206`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005d22a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005d1a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005d206`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005d22a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005d0b3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005d2b5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005d0b3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005d2b5`

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
  unsigned int v15; // r8d
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
  unsigned int Length; // [rsp+20h] [rbp-E0h]
  ULONG ResultLength; // [rsp+40h] [rbp-C0h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  void *DeviceRegKey; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  struct _IRP *v37; // [rsp+A0h] [rbp-60h]
  __int128 KeyInformation; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v39; // [rsp+B8h] [rbp-48h]
  unsigned __int16 v40[128]; // [rsp+C0h] [rbp-40h] BYREF

  v37 = a2;
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
      v39 = 0;
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
      if ( (int)GetRegistryValue(Handle, v14, v15, v40, Length) < 0 )
      {
        ExFreePoolWithTag(v13, 0);
        ZwClose(Handle);
        break;
      }
      ChildPdo = CKsDevice::CreateChildPdo(this, v40, i);
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
      v2 = v37;
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
0x18005ce9c  mov     [rsp-8+arg_10], rbx
0x18005cea1  push    rbp
0x18005cea2  push    rsi
0x18005cea3  push    rdi
0x18005cea4  push    r12
0x18005cea6  push    r13
0x18005cea8  push    r14
0x18005ceaa  push    r15
0x18005ceac  lea     rbp, [rsp-0D0h]
0x18005ceb4  sub     rsp, 1D0h
0x18005cebb  mov     rax, cs:__security_cookie
0x18005cec2  xor     rax, rsp
0x18005cec5  mov     [rbp+100h+var_40], rax
0x18005cecc  xorps   xmm0, xmm0
0x18005cecf  mov     [rbp+100h+var_160], rdx
0x18005ced3  xor     r12d, r12d
0x18005ced6  mov     r13, rdx
0x18005ced9  movups  xmmword ptr [rsp+200h+ObjectAttributes.Length], xmm0
0x18005cede  mov     [rsp+200h+DeviceRegKey], r12
0x18005cee3  mov     rsi, rcx
0x18005cee6  movups  xmmword ptr [rbp+100h+ObjectAttributes.ObjectName], xmm0
0x18005ceea  mov     [rsp+200h+KeyHandle], r12
0x18005ceef  movups  xmmword ptr [rbp+100h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005cef3  mov     [rsp+200h+Handle], r12
0x18005cef8  movups  xmmword ptr [rsp+200h+DestinationString.Length], xmm0
0x18005cefd  lea     rbx, WPP_RECORDER_INITIALIZED
0x18005cf04  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x18005cf0b  jz      short loc_18005CF53
0x18005cf0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cf14  cmp     [rcx+48h], r12w
0x18005cf19  jz      short loc_18005CF53
0x18005cf1b  cmp     [rsi+45Ch], r12b
0x18005cf22  lea     r8, a1stTime; "1st Time"
0x18005cf29  mov     rax, [rsi+0E0h]
0x18005cf30  lea     rdx, aHasEnumed; "has enumed"
0x18005cf37  mov     rcx, [rcx+40h]
0x18005cf3b  lea     r9d, [r12+0Bh]
0x18005cf40  cmovz   rdx, r8
0x18005cf44  mov     [rsp+200h+var_1D0], rdx
0x18005cf49  mov     [rsp+200h+ResultLength], rax
0x18005cf4e  call    WPP_RECORDER_SF_qs
0x18005cf53  lea     r15, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005cf5a  cmp     [rsi+45Ch], r12b
0x18005cf61  jnz     loc_18005D276
0x18005cf67  mov     rcx, [rsi+0E8h]; DeviceObject
0x18005cf6e  lea     r9, [rsp+200h+DeviceRegKey]; DeviceRegKey
0x18005cf73  mov     edx, 2; DevInstKeyType
0x18005cf78  mov     r8d, 1F0000h; DesiredAccess
0x18005cf7e  call    cs:__imp_IoOpenDeviceRegistryKey
0x18005cf85  nop     dword ptr [rax+rax+00h]
0x18005cf8a  mov     byte ptr [rsi+45Ch], 1
0x18005cf91  test    eax, eax
0x18005cf93  jns     short loc_18005CFCF
0x18005cf95  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x18005cf9c  jz      loc_18005D25C
0x18005cfa2  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cfa9  lea     r15, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18005cfb0  mov     r9d, 0Ch
0x18005cfb6  mov     qword ptr [rsp+200h+Length], r15
0x18005cfbb  mov     dl, 2
0x18005cfbd  mov     rcx, [rcx+40h]
0x18005cfc1  lea     r8d, [r9-0Bh]
0x18005cfc5  call    WPP_RECORDER_SF_
0x18005cfca  jmp     loc_18005D25C
0x18005cfcf  lea     rdx, aEnum; "Enum"
0x18005cfd6  lea     rcx, [rsp+200h+DestinationString]; DestinationString
0x18005cfdb  call    cs:__imp_RtlInitUnicodeString
0x18005cfe2  nop     dword ptr [rax+rax+00h]
0x18005cfe7  mov     rax, [rsp+200h+DeviceRegKey]
0x18005cfec  lea     r8, [rsp+200h+ObjectAttributes]; ObjectAttributes
0x18005cff1  mov     [rsp+200h+ObjectAttributes.RootDirectory], rax
0x18005cff6  lea     rcx, [rsp+200h+KeyHandle]; KeyHandle
0x18005cffb  lea     rax, [rsp+200h+DestinationString]
0x18005d000  mov     [rsp+200h+ObjectAttributes.Length], 30h ; '0'
0x18005d008  xorps   xmm0, xmm0
0x18005d00b  mov     [rbp+100h+ObjectAttributes.ObjectName], rax
0x18005d00f  mov     edx, 20019h; DesiredAccess
0x18005d014  mov     [rbp+100h+ObjectAttributes.Attributes], 240h
0x18005d01b  movdqu  xmmword ptr [rbp+100h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005d020  call    cs:__imp_ZwOpenKey
0x18005d027  nop     dword ptr [rax+rax+00h]
0x18005d02c  mov     ebx, eax
0x18005d02e  test    eax, eax
0x18005d030  jns     short loc_18005D04A
0x18005d032  mov     rcx, [rsp+200h+DeviceRegKey]; Handle
0x18005d037  call    cs:__imp_ZwClose
0x18005d03e  nop     dword ptr [rax+rax+00h]
0x18005d043  mov     eax, ebx
0x18005d045  jmp     loc_18005D3AB
0x18005d04a  mov     edi, r12d
0x18005d04d  mov     rcx, [rsp+200h+KeyHandle]; KeyHandle
0x18005d052  lea     r9, [rbp+100h+KeyInformation]; KeyInformation
0x18005d056  xor     eax, eax
0x18005d058  mov     [rsp+200h+var_1C0], r12d
0x18005d05d  mov     [rbp+100h+var_148], rax
0x18005d061  xorps   xmm0, xmm0
0x18005d064  lea     rax, [rsp+200h+var_1C0]
0x18005d069  xor     r8d, r8d; KeyInformationClass
0x18005d06c  mov     [rsp+200h+ResultLength], rax; ResultLength
0x18005d071  mov     edx, edi; Index
0x18005d073  mov     [rsp+200h+Length], 18h; Length
0x18005d07b  mov     ebx, 80000000h
0x18005d080  movups  [rbp+100h+KeyInformation], xmm0
0x18005d084  call    cs:__imp_ZwEnumerateKey
0x18005d08b  nop     dword ptr [rax+rax+00h]
0x18005d090  lea     ecx, [rax+rbx]
0x18005d093  test    ebx, ecx
0x18005d095  jnz     short loc_18005D0A2
0x18005d097  cmp     eax, 80000005h
0x18005d09c  jnz     loc_18005D236
0x18005d0a2  mov     ebx, [rsp+200h+var_1C0]
0x18005d0a6  mov     r8d, 6563534Bh; Tag
0x18005d0ac  mov     edx, ebx; NumberOfBytes
0x18005d0ae  mov     ecx, 401h; PoolType
0x18005d0b3  call    cs:__imp_ExAllocatePoolWithTag
0x18005d0ba  nop     dword ptr [rax+rax+00h]
0x18005d0bf  mov     r14, rax
0x18005d0c2  test    rax, rax
0x18005d0c5  jz      loc_18005D236
0x18005d0cb  cmp     cs:ExPoolZeroingNativelySupported, r12b
0x18005d0d2  jnz     short loc_18005D0E1
0x18005d0d4  mov     r8d, ebx; Size
0x18005d0d7  xor     edx, edx; Val
0x18005d0d9  mov     rcx, rax; void *
0x18005d0dc  call    memset
0x18005d0e1  mov     rcx, [rsp+200h+KeyHandle]; KeyHandle
0x18005d0e6  lea     rax, [rsp+200h+var_1C0]
0x18005d0eb  mov     [rsp+200h+ResultLength], rax; ResultLength
0x18005d0f0  mov     r9, r14; KeyInformation
0x18005d0f3  mov     eax, [rsp+200h+var_1C0]
0x18005d0f7  xor     r8d, r8d; KeyInformationClass
0x18005d0fa  mov     edx, edi; Index
0x18005d0fc  mov     [rsp+200h+Length], eax; unsigned int
0x18005d100  call    cs:__imp_ZwEnumerateKey
0x18005d107  nop     dword ptr [rax+rax+00h]
0x18005d10c  test    eax, eax
0x18005d10e  js      loc_18005D225
0x18005d114  movzx   eax, word ptr [r14+0Ch]
0x18005d119  lea     r8, [rsp+200h+ObjectAttributes]; ObjectAttributes
0x18005d11e  mov     [rsp+200h+DestinationString.Length], ax
0x18005d123  lea     rcx, [rsp+200h+Handle]; KeyHandle
0x18005d128  movzx   eax, word ptr [r14+0Ch]
0x18005d12d  xorps   xmm0, xmm0
0x18005d130  mov     [rsp+200h+DestinationString.MaximumLength], ax
0x18005d135  mov     edx, 20019h; DesiredAccess
0x18005d13a  lea     rax, [r14+10h]
0x18005d13e  mov     [rsp+200h+ObjectAttributes.Length], 30h ; '0'
0x18005d146  mov     [rsp+200h+DestinationString.Buffer], rax
0x18005d14b  mov     rax, [rsp+200h+KeyHandle]
0x18005d150  mov     [rsp+200h+ObjectAttributes.RootDirectory], rax
0x18005d155  lea     rax, [rsp+200h+DestinationString]
0x18005d15a  mov     [rbp+100h+ObjectAttributes.ObjectName], rax
0x18005d15e  mov     [rbp+100h+ObjectAttributes.Attributes], 240h
0x18005d165  movdqu  xmmword ptr [rbp+100h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005d16a  call    cs:__imp_ZwOpenKey
0x18005d171  nop     dword ptr [rax+rax+00h]
0x18005d176  test    eax, eax
0x18005d178  js      loc_18005D225
0x18005d17e  mov     rcx, [rsp+200h+Handle]; KeyHandle
0x18005d183  lea     r9, [rbp+100h+var_140]; void *
0x18005d187  call    ?GetRegistryValue@@YAJPEAXPEAGK0K@Z; GetRegistryValue(void *,ushort *,ulong,void *,ulong)
0x18005d18c  test    eax, eax
0x18005d18e  js      short loc_18005D201
0x18005d190  mov     r8d, edi; unsigned int
0x18005d193  lea     rdx, [rbp+100h+var_140]; unsigned __int16 *
0x18005d197  mov     rcx, rsi; this
0x18005d19a  call    ?CreateChildPdo@CKsDevice@@QEAAJPEAGK@Z; CKsDevice::CreateChildPdo(ushort *,ulong)
0x18005d19f  xor     edx, edx; Tag
0x18005d1a1  mov     rcx, r14; P
0x18005d1a4  mov     ebx, eax
0x18005d1a6  call    cs:__imp_ExFreePoolWithTag
0x18005d1ad  nop     dword ptr [rax+rax+00h]
0x18005d1b2  mov     rcx, [rsp+200h+Handle]; Handle
0x18005d1b7  call    cs:__imp_ZwClose
0x18005d1be  nop     dword ptr [rax+rax+00h]
0x18005d1c3  test    ebx, ebx
0x18005d1c5  js      short loc_18005D1CE
0x18005d1c7  inc     edi
0x18005d1c9  jmp     loc_18005D04D
0x18005d1ce  lea     rax, WPP_RECORDER_INITIALIZED
0x18005d1d5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005d1dc  jz      short loc_18005D236
0x18005d1de  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d1e5  mov     r9d, 0Dh
0x18005d1eb  mov     dl, 2
0x18005d1ed  mov     qword ptr [rsp+200h+Length], r15
0x18005d1f2  mov     rcx, [rcx+40h]
0x18005d1f6  lea     r8d, [r9-0Ch]
0x18005d1fa  call    WPP_RECORDER_SF_
0x18005d1ff  jmp     short loc_18005D236
0x18005d201  xor     edx, edx; Tag
0x18005d203  mov     rcx, r14; P
0x18005d206  call    cs:__imp_ExFreePoolWithTag
0x18005d20d  nop     dword ptr [rax+rax+00h]
0x18005d212  mov     rcx, [rsp+200h+Handle]; Handle
0x18005d217  call    cs:__imp_ZwClose
0x18005d21e  nop     dword ptr [rax+rax+00h]
0x18005d223  jmp     short loc_18005D236
0x18005d225  xor     edx, edx; Tag
0x18005d227  mov     rcx, r14; P
0x18005d22a  call    cs:__imp_ExFreePoolWithTag
0x18005d231  nop     dword ptr [rax+rax+00h]
0x18005d236  mov     rcx, [rsp+200h+KeyHandle]; Handle
0x18005d23b  call    cs:__imp_ZwClose
0x18005d242  nop     dword ptr [rax+rax+00h]
0x18005d247  mov     rcx, [rsp+200h+DeviceRegKey]; Handle
0x18005d24c  call    cs:__imp_ZwClose
0x18005d253  nop     dword ptr [rax+rax+00h]
0x18005d258  test    edi, edi
0x18005d25a  jnz     short loc_18005D266
0x18005d25c  mov     eax, 0C0000002h
0x18005d261  jmp     loc_18005D3AB
0x18005d266  mov     byte ptr [rsi+312h], 1
0x18005d26d  lea     rbx, [rsi+460h]
0x18005d274  jmp     short loc_18005D29E
0x18005d276  lea     rbx, [rsi+460h]
0x18005d27d  mov     edi, r12d
0x18005d280  mov     rax, [rbx]
0x18005d283  jmp     short loc_18005D299
0x18005d285  mov     rdx, [rax+40h]
0x18005d289  lea     ecx, [rdi+1]
0x18005d28c  cmp     [rdx+2Ch], r12b
0x18005d290  mov     rax, [rdx+10h]
0x18005d294  cmovnz  ecx, edi
0x18005d297  mov     edi, ecx
0x18005d299  test    rax, rax
0x18005d29c  jnz     short loc_18005D285
0x18005d29e  lea     eax, ds:10h[rdi*8]
0x18005d2a5  mov     r8d, 7264534Bh; Tag
0x18005d2ab  mov     edx, eax; NumberOfBytes
0x18005d2ad  mov     ecx, 1; PoolType
0x18005d2b2  mov     r14d, eax
0x18005d2b5  call    cs:__imp_ExAllocatePoolWithTag
0x18005d2bc  nop     dword ptr [rax+rax+00h]
0x18005d2c1  mov     rsi, rax
0x18005d2c4  test    rax, rax
0x18005d2c7  jnz     short loc_18005D302
0x18005d2c9  lea     rax, WPP_RECORDER_INITIALIZED
0x18005d2d0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005d2d7  jz      short loc_18005D2F8
0x18005d2d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d2e0  lea     r9d, [rsi+0Eh]
0x18005d2e4  lea     r8d, [rsi+1]
0x18005d2e8  mov     qword ptr [rsp+200h+Length], r15
0x18005d2ed  mov     dl, 2
0x18005d2ef  mov     rcx, [rcx+40h]
0x18005d2f3  call    WPP_RECORDER_SF_
0x18005d2f8  mov     eax, 0C000009Ah
0x18005d2fd  jmp     loc_18005D3AB
0x18005d302  mov     r8, r14; Size
0x18005d305  xor     edx, edx; Val
0x18005d307  mov     rcx, rsi; void *
0x18005d30a  call    memset
0x18005d30f  mov     rbx, [rbx]
0x18005d312  lea     r15, [rsi+8]
0x18005d316  test    rbx, rbx
0x18005d319  jz      loc_18005D39F
0x18005d31f  lea     r13, WPP_RECORDER_INITIALIZED
0x18005d326  mov     r14, [rbx+40h]
0x18005d32a  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18005d331  jz      short loc_18005D370
0x18005d333  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d33a  cmp     [rcx+48h], r12w
0x18005d33f  jz      short loc_18005D370
0x18005d341  cmp     [r14+2Ch], r12b
0x18005d345  lea     r8, aNot; " not"
0x18005d34c  mov     rcx, [rcx+40h]
0x18005d350  lea     rdx, File
0x18005d357  cmovz   rdx, r8
0x18005d35b  mov     r9d, 0Fh
0x18005d361  mov     [rsp+200h+var_1D0], rdx
0x18005d366  mov     [rsp+200h+ResultLength], rbx
0x18005d36b  call    WPP_RECORDER_SF_qs
0x18005d370  cmp     [r14+2Ch], r12b
0x18005d374  jz      short loc_18005D37C
0x18005d376  mov     rbx, [r14+10h]
0x18005d37a  jmp     short loc_18005D396
0x18005d37c  mov     rcx, rbx; Object
0x18005d37f  mov     [r15], rbx
0x18005d382  mov     rbx, [r14+10h]
0x18005d386  call    cs:__imp_ObfReferenceObject
0x18005d38d  nop     dword ptr [rax+rax+00h]
0x18005d392  add     r15, 8
0x18005d396  test    rbx, rbx
0x18005d399  jnz     short loc_18005D326
0x18005d39b  mov     r13, [rbp+100h+var_160]
0x18005d39f  mov     [rsi], edi
0x18005d3a1  xor     eax, eax
0x18005d3a3  mov     [r13+30h], r12d
0x18005d3a7  mov     [r13+38h], rsi
0x18005d3ab  mov     rcx, [rbp+100h+var_40]
0x18005d3b2  xor     rcx, rsp; StackCookie
0x18005d3b5  call    __security_check_cookie
0x18005d3ba  mov     rbx, [rsp+200h+arg_10]
0x18005d3c2  add     rsp, 1D0h
0x18005d3c9  pop     r15
0x18005d3cb  pop     r14
0x18005d3cd  pop     r13
0x18005d3cf  pop     r12
0x18005d3d1  pop     rdi
  ... truncated ...
```
