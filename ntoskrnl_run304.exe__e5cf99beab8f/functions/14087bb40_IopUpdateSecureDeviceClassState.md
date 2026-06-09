# IopUpdateSecureDeviceClassState

- ea: `0x14087bb40`
- end: `0x14087be08`
- name: `IopUpdateSecureDeviceClassState`
- size: `712`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14087c300`

## callees

- `0x1403f2d50`
- `0x140414d30`
- `0x1404714f0`
- `0x1406daa70`
- `0x1406daad0`
- `0x1406dac30`
- `0x1406db490`
- `0x140863ab0`
- `0x14087b818`
- `0x14087bb40`
- `0x14092bbb0`
- `0x140973560`
- `0x140bae410`
- `0x140bae8c0`
- `0x140bae8e0`

## string_xrefs

- `0x14087bd51`: `Security`
- `0x14087bbc7`: `\Registry\Machine\System\CurrentControlSet\Control\Class`

## pseudocode

```c
__int64 __fastcall IopUpdateSecureDeviceClassState(__int64 a1, __int64 a2)
{
  void *v2; // rsi
  void *v3; // r15
  unsigned int v6; // r14d
  void *Pool2; // rdi
  int PersistedStateLocation; // eax
  NTSTATUS inited; // ebx
  __int64 v10; // r8
  int v11; // eax
  ULONG v12; // ebx
  void *v14; // [rsp+40h] [rbp-79h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-71h] BYREF
  UNICODE_STRING DestinationString; // [rsp+50h] [rbp-69h] BYREF
  void *v17; // [rsp+60h] [rbp-59h] BYREF
  PVOID P[2]; // [rsp+68h] [rbp-51h] BYREF
  OBJECT_ATTRIBUTES v19; // [rsp+78h] [rbp-41h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v21; // [rsp+130h] [rbp+77h] BYREF
  HANDLE KeyHandle; // [rsp+138h] [rbp+7Fh] BYREF

  v2 = 0;
  KeyHandle = 0;
  v3 = 0;
  v14 = 0;
  v17 = 0;
  Handle = 0;
  LODWORD(v21) = 0;
  memset(&v19, 0, 44);
  v6 = 256;
  DestinationString = 0;
  *(_OWORD *)P = 0;
  while ( 1 )
  {
    Pool2 = (void *)ExAllocatePool2(256, v6, 1665560393);
    if ( !Pool2 )
    {
      inited = -1073741670;
      goto LABEL_19;
    }
    PersistedStateLocation = RtlGetPersistedStateLocation(L"SecureDeviceClass", Pool2, v6, (__int64)&v21);
    inited = PersistedStateLocation;
    if ( PersistedStateLocation != -2147483643 )
      break;
    if ( (unsigned int)v21 <= v6 )
    {
      inited = -1073741595;
LABEL_8:
      ExFreePoolWithTag(Pool2, 0);
      Pool2 = 0;
      goto LABEL_19;
    }
    v6 = v21;
    ExFreePoolWithTag(Pool2, 0);
  }
  if ( PersistedStateLocation < 0 )
    goto LABEL_8;
  inited = RtlInitUnicodeStringEx(&DestinationString, (PCWSTR)Pool2);
  if ( inited >= 0 )
  {
    *(_QWORD *)&ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_QWORD *)&ObjectAttributes.Attributes = 576;
    KeyHandle = 0;
    ObjectAttributes.RootDirectory = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    inited = ZwOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
    if ( inited >= 0 )
    {
      LOBYTE(v10) = 1;
      inited = RtlStringFromGUIDEx(a1, P, v10);
      if ( inited >= 0 )
      {
        inited = IopCreateRegistryKeyEx(&v14, KeyHandle, P, 983103, 0, 0);
        if ( inited < 0 )
        {
          v2 = v14;
        }
        else
        {
          v11 = SeConvertStringSecurityDescriptorToSecurityDescriptor(L"D:PAI(A;OICI;GA;;;SY)", 1, &v17);
          v3 = v17;
          if ( v11 < 0 )
            v3 = 0;
          RtlInitUnicodeString(&DestinationString, L"Properties");
          v2 = v14;
          v19.ObjectName = &DestinationString;
          v19.Length = 48;
          v19.RootDirectory = v14;
          v19.Attributes = 576;
          v19.SecurityDescriptor = v3;
          v19.SecurityQualityOfService = 0;
          inited = ZwCreateKey(&Handle, 0xF003Fu, &v19, 0, 0, 0, 0);
          if ( inited >= 0 )
          {
            v12 = RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a2 + 8));
            RtlInitUnicodeString(&DestinationString, L"Security");
            inited = ZwSetValueKey(Handle, &DestinationString, 0, 3u, *(PVOID *)(a2 + 8), v12);
          }
        }
      }
    }
  }
LABEL_19:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( v2 )
    ZwClose(v2);
  if ( Handle )
    ZwClose(Handle);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0);
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  if ( P[1] )
    ExFreePool(P[1]);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x14087bb40  mov     [rsp-8+arg_0], rbx
0x14087bb45  push    rbp
0x14087bb46  push    rsi
0x14087bb47  push    rdi
0x14087bb48  push    r12
0x14087bb4a  push    r13
0x14087bb4c  push    r14
0x14087bb4e  push    r15
0x14087bb50  lea     rbp, [rsp-27h]
0x14087bb55  sub     rsp, 0E0h
0x14087bb5c  xor     eax, eax
0x14087bb5e  xorps   xmm0, xmm0
0x14087bb61  xor     esi, esi
0x14087bb63  mov     [rbp+57h+KeyHandle], rax
0x14087bb67  xor     r15d, r15d
0x14087bb6a  mov     [rbp+57h+var_D0], rsi
0x14087bb6e  xorps   xmm1, xmm1
0x14087bb71  mov     [rbp+57h+var_B0], r15
0x14087bb75  movups  xmmword ptr [rbp+57h+var_98.ObjectName], xmm0
0x14087bb79  mov     r13, rdx
0x14087bb7c  mov     [rbp+57h+Handle], rax
0x14087bb80  mov     r12, rcx
0x14087bb83  mov     dword ptr [rbp+57h+arg_10], eax
0x14087bb86  movups  xmmword ptr [rbp+57h+var_98.Length], xmm0
0x14087bb8a  mov     r14d, 100h
0x14087bb90  movups  xmmword ptr [rbp+57h+var_98+1Ch], xmm0
0x14087bb94  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14087bb98  movups  xmmword ptr [rbp+57h+P], xmm1
0x14087bb9c  mov     edx, r14d
0x14087bb9f  mov     ecx, 100h
0x14087bba4  mov     r8d, 63466F49h
0x14087bbaa  call    ExAllocatePool2
0x14087bbaf  mov     rdi, rax
0x14087bbb2  test    rax, rax
0x14087bbb5  jz      loc_14087BD90
0x14087bbbb  lea     rax, [rbp+57h+arg_10]
0x14087bbbf  xor     r9d, r9d
0x14087bbc2  mov     [rsp+110h+Disposition], rax; __int64
0x14087bbc7  lea     r8, aRegistryMachin_11; "\\Registry\\Machine\\System\\CurrentCon"...
0x14087bbce  mov     [rsp+110h+CreateOptions], r14d; int
0x14087bbd3  lea     rcx, aSecuredevicecl; "SecureDeviceClass"
0x14087bbda  xor     edx, edx
0x14087bbdc  mov     [rsp+110h+Class], rdi; void *
0x14087bbe1  call    RtlGetPersistedStateLocation
0x14087bbe6  mov     ebx, eax
0x14087bbe8  cmp     eax, 80000005h
0x14087bbed  jnz     short loc_14087BC0F
0x14087bbef  cmp     dword ptr [rbp+57h+arg_10], r14d
0x14087bbf3  jbe     short loc_14087BC05
0x14087bbf5  mov     r14d, dword ptr [rbp+57h+arg_10]
0x14087bbf9  xor     edx, edx; Tag
0x14087bbfb  mov     rcx, rdi; P
0x14087bbfe  call    ExFreePoolWithTag
0x14087bc03  jmp     short loc_14087BB9C
0x14087bc05  mov     ebx, 0C00000E5h
0x14087bc0a  xor     r14d, r14d
0x14087bc0d  jmp     short loc_14087BC16
0x14087bc0f  xor     r14d, r14d
0x14087bc12  test    eax, eax
0x14087bc14  jns     short loc_14087BC28
0x14087bc16  xor     edx, edx; Tag
0x14087bc18  mov     rcx, rdi; P
0x14087bc1b  call    ExFreePoolWithTag
0x14087bc20  mov     rdi, r14
0x14087bc23  jmp     loc_14087BD95
0x14087bc28  mov     rdx, rdi; SourceString
0x14087bc2b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14087bc2f  call    RtlInitUnicodeStringEx
0x14087bc34  mov     ebx, eax
0x14087bc36  test    eax, eax
0x14087bc38  js      loc_14087BD95
0x14087bc3e  lea     rax, [rbp+57h+DestinationString]
0x14087bc42  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14087bc4a  xorps   xmm0, xmm0
0x14087bc4d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14087bc51  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14087bc55  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x14087bc5d  mov     edx, 0F003Fh; DesiredAccess
0x14087bc62  mov     [rbp+57h+KeyHandle], r14
0x14087bc66  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14087bc6a  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x14087bc6e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14087bc73  call    ZwOpenKey
0x14087bc78  mov     ebx, eax
0x14087bc7a  test    eax, eax
0x14087bc7c  js      loc_14087BD95
0x14087bc82  mov     r8b, 1
0x14087bc85  lea     rdx, [rbp+57h+P]
0x14087bc89  mov     rcx, r12
0x14087bc8c  call    RtlStringFromGUIDEx
0x14087bc91  mov     ebx, eax
0x14087bc93  test    eax, eax
0x14087bc95  js      loc_14087BD95
0x14087bc9b  mov     rdx, [rbp+57h+KeyHandle]
0x14087bc9f  lea     r8, [rbp+57h+P]
0x14087bca3  mov     r12d, 0F003Fh
0x14087bca9  mov     qword ptr [rsp+110h+CreateOptions], r14
0x14087bcae  mov     r9d, r12d
0x14087bcb1  mov     dword ptr [rsp+110h+Class], r14d
0x14087bcb6  lea     rcx, [rbp+57h+var_D0]
0x14087bcba  call    IopCreateRegistryKeyEx
0x14087bcbf  mov     ebx, eax
0x14087bcc1  test    eax, eax
0x14087bcc3  js      loc_14087BD8A
0x14087bcc9  xor     r9d, r9d
0x14087bccc  lea     r8, [rbp+57h+var_B0]
0x14087bcd0  lea     rcx, aDPaiAOiciGaSy; "D:PAI(A;OICI;GA;;;SY)"
0x14087bcd7  lea     edx, [r9+1]
0x14087bcdb  call    SeConvertStringSecurityDescriptorToSecurityDescriptor
0x14087bce0  mov     r15, [rbp+57h+var_B0]
0x14087bce4  lea     rdx, aProperties_1; "Properties"
0x14087bceb  test    eax, eax
0x14087bced  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14087bcf1  cmovs   r15, r14
0x14087bcf5  call    RtlInitUnicodeString
0x14087bcfa  mov     rsi, [rbp+57h+var_D0]
0x14087bcfe  lea     rax, [rbp+57h+DestinationString]
0x14087bd02  mov     [rsp+110h+Disposition], r14; Disposition
0x14087bd07  lea     r8, [rbp+57h+var_98]; ObjectAttributes
0x14087bd0b  mov     [rsp+110h+CreateOptions], r14d; CreateOptions
0x14087bd10  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x14087bd14  xor     r9d, r9d; TitleIndex
0x14087bd17  mov     [rbp+57h+var_98.ObjectName], rax
0x14087bd1b  mov     edx, r12d; DesiredAccess
0x14087bd1e  mov     [rbp+57h+var_98.Length], 30h ; '0'
0x14087bd25  mov     [rbp+57h+var_98.RootDirectory], rsi
0x14087bd29  mov     [rbp+57h+var_98.Attributes], 240h
0x14087bd30  mov     [rbp+57h+var_98.SecurityDescriptor], r15
0x14087bd34  mov     [rbp+57h+var_98.SecurityQualityOfService], r14
0x14087bd38  mov     [rsp+110h+Class], r14; Class
0x14087bd3d  call    ZwCreateKey
0x14087bd42  mov     ebx, eax
0x14087bd44  test    eax, eax
0x14087bd46  js      short loc_14087BD95
0x14087bd48  mov     rcx, [r13+8]; SecurityDescriptor
0x14087bd4c  call    RtlLengthSecurityDescriptor
0x14087bd51  lea     rdx, aSecurity_0; "Security"
0x14087bd58  mov     ebx, eax
0x14087bd5a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14087bd5e  call    RtlInitUnicodeString
0x14087bd63  mov     rax, [r13+8]
0x14087bd67  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14087bd6b  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14087bd6f  mov     r9d, 3; Type
0x14087bd75  mov     [rsp+110h+CreateOptions], ebx; DataSize
0x14087bd79  xor     r8d, r8d; TitleIndex
0x14087bd7c  mov     [rsp+110h+Class], rax; Data
0x14087bd81  call    ZwSetValueKey
0x14087bd86  mov     ebx, eax
0x14087bd88  jmp     short loc_14087BD95
0x14087bd8a  mov     rsi, [rbp+57h+var_D0]
0x14087bd8e  jmp     short loc_14087BD95
0x14087bd90  mov     ebx, 0C000009Ah
0x14087bd95  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14087bd99  test    rcx, rcx
0x14087bd9c  jz      short loc_14087BDA3
0x14087bd9e  call    ZwClose
0x14087bda3  test    rsi, rsi
0x14087bda6  jz      short loc_14087BDB0
0x14087bda8  mov     rcx, rsi; Handle
0x14087bdab  call    ZwClose
0x14087bdb0  mov     rcx, [rbp+57h+Handle]; Handle
0x14087bdb4  test    rcx, rcx
0x14087bdb7  jz      short loc_14087BDBE
0x14087bdb9  call    ZwClose
0x14087bdbe  test    rdi, rdi
0x14087bdc1  jz      short loc_14087BDCD
0x14087bdc3  xor     edx, edx; Tag
0x14087bdc5  mov     rcx, rdi; P
0x14087bdc8  call    ExFreePoolWithTag
0x14087bdcd  test    r15, r15
0x14087bdd0  jz      short loc_14087BDDC
0x14087bdd2  xor     edx, edx; Tag
0x14087bdd4  mov     rcx, r15; P
0x14087bdd7  call    ExFreePoolWithTag
0x14087bddc  mov     rcx, [rbp+57h+P+8]; P
0x14087bde0  test    rcx, rcx
0x14087bde3  jz      short loc_14087BDEA
0x14087bde5  call    ExFreePool
0x14087bdea  mov     eax, ebx
0x14087bdec  mov     rbx, [rsp+110h+arg_0]
0x14087bdf4  add     rsp, 0E0h
0x14087bdfb  pop     r15
0x14087bdfd  pop     r14
0x14087bdff  pop     r13
0x14087be01  pop     r12
0x14087be03  pop     rdi
0x14087be04  pop     rsi
0x14087be05  pop     rbp
0x14087be06  retn
```
