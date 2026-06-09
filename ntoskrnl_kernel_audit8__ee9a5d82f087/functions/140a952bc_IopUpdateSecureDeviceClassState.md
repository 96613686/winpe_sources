# IopUpdateSecureDeviceClassState

- ea: `0x140a952bc`
- end: `0x140a95584`
- name: `IopUpdateSecureDeviceClassState`
- size: `712`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140a94db0`

## callees

- `0x140403380`
- `0x14042bfd0`
- `0x1404809e0`
- `0x1406dd5c0`
- `0x1406dd620`
- `0x1406dd780`
- `0x1406ddfe0`
- `0x140852b30`
- `0x140879b80`
- `0x140923cd0`
- `0x140a952bc`
- `0x140a95b68`
- `0x140bb1410`
- `0x140bb19d0`
- `0x140bb19f0`

## string_xrefs

- `0x140a954cd`: `Security`
- `0x140a95343`: `\Registry\Machine\System\CurrentControlSet\Control\Class`

## pseudocode

```c
__int64 __fastcall IopUpdateSecureDeviceClassState(__int64 a1, __int64 a2)
{
  void *v2; // rsi
  void *v3; // r15
  unsigned int v6; // r14d
  void *Pool2; // rdi
  int PersistedStateLocation; // eax
  int inited; // ebx
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
0x140a952bc  mov     [rsp-8+arg_0], rbx
0x140a952c1  push    rbp
0x140a952c2  push    rsi
0x140a952c3  push    rdi
0x140a952c4  push    r12
0x140a952c6  push    r13
0x140a952c8  push    r14
0x140a952ca  push    r15
0x140a952cc  lea     rbp, [rsp-27h]
0x140a952d1  sub     rsp, 0E0h
0x140a952d8  xor     eax, eax
0x140a952da  xorps   xmm0, xmm0
0x140a952dd  xor     esi, esi
0x140a952df  mov     [rbp+57h+KeyHandle], rax
0x140a952e3  xor     r15d, r15d
0x140a952e6  mov     [rbp+57h+var_D0], rsi
0x140a952ea  xorps   xmm1, xmm1
0x140a952ed  mov     [rbp+57h+var_B0], r15
0x140a952f1  movups  xmmword ptr [rbp+57h+var_98.ObjectName], xmm0
0x140a952f5  mov     r13, rdx
0x140a952f8  mov     [rbp+57h+Handle], rax
0x140a952fc  mov     r12, rcx
0x140a952ff  mov     dword ptr [rbp+57h+arg_10], eax
0x140a95302  movups  xmmword ptr [rbp+57h+var_98.Length], xmm0
0x140a95306  mov     r14d, 100h
0x140a9530c  movups  xmmword ptr [rbp+57h+var_98+1Ch], xmm0
0x140a95310  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140a95314  movups  xmmword ptr [rbp+57h+P], xmm1
0x140a95318  mov     edx, r14d
0x140a9531b  mov     ecx, 100h
0x140a95320  mov     r8d, 63466F49h
0x140a95326  call    ExAllocatePool2
0x140a9532b  mov     rdi, rax
0x140a9532e  test    rax, rax
0x140a95331  jz      loc_140A9550C
0x140a95337  lea     rax, [rbp+57h+arg_10]
0x140a9533b  xor     r9d, r9d
0x140a9533e  mov     [rsp+110h+Disposition], rax; __int64
0x140a95343  lea     r8, aRegistryMachin_11; "\\Registry\\Machine\\System\\CurrentCon"...
0x140a9534a  mov     [rsp+110h+CreateOptions], r14d; int
0x140a9534f  lea     rcx, aSecuredevicecl; "SecureDeviceClass"
0x140a95356  xor     edx, edx
0x140a95358  mov     [rsp+110h+Class], rdi; void *
0x140a9535d  call    RtlGetPersistedStateLocation
0x140a95362  mov     ebx, eax
0x140a95364  cmp     eax, 80000005h
0x140a95369  jnz     short loc_140A9538B
0x140a9536b  cmp     dword ptr [rbp+57h+arg_10], r14d
0x140a9536f  jbe     short loc_140A95381
0x140a95371  mov     r14d, dword ptr [rbp+57h+arg_10]
0x140a95375  xor     edx, edx; Tag
0x140a95377  mov     rcx, rdi; P
0x140a9537a  call    ExFreePoolWithTag
0x140a9537f  jmp     short loc_140A95318
0x140a95381  mov     ebx, 0C00000E5h
0x140a95386  xor     r14d, r14d
0x140a95389  jmp     short loc_140A95392
0x140a9538b  xor     r14d, r14d
0x140a9538e  test    eax, eax
0x140a95390  jns     short loc_140A953A4
0x140a95392  xor     edx, edx; Tag
0x140a95394  mov     rcx, rdi; P
0x140a95397  call    ExFreePoolWithTag
0x140a9539c  mov     rdi, r14
0x140a9539f  jmp     loc_140A95511
0x140a953a4  mov     rdx, rdi; SourceString
0x140a953a7  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140a953ab  call    RtlInitUnicodeStringEx
0x140a953b0  mov     ebx, eax
0x140a953b2  test    eax, eax
0x140a953b4  js      loc_140A95511
0x140a953ba  lea     rax, [rbp+57h+DestinationString]
0x140a953be  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140a953c6  xorps   xmm0, xmm0
0x140a953c9  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140a953cd  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140a953d1  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140a953d9  mov     edx, 0F003Fh; DesiredAccess
0x140a953de  mov     [rbp+57h+KeyHandle], r14
0x140a953e2  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140a953e6  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x140a953ea  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140a953ef  call    ZwOpenKey
0x140a953f4  mov     ebx, eax
0x140a953f6  test    eax, eax
0x140a953f8  js      loc_140A95511
0x140a953fe  mov     r8b, 1
0x140a95401  lea     rdx, [rbp+57h+P]
0x140a95405  mov     rcx, r12
0x140a95408  call    RtlStringFromGUIDEx
0x140a9540d  mov     ebx, eax
0x140a9540f  test    eax, eax
0x140a95411  js      loc_140A95511
0x140a95417  mov     rdx, [rbp+57h+KeyHandle]
0x140a9541b  lea     r8, [rbp+57h+P]
0x140a9541f  mov     r12d, 0F003Fh
0x140a95425  mov     qword ptr [rsp+110h+CreateOptions], r14
0x140a9542a  mov     r9d, r12d
0x140a9542d  mov     dword ptr [rsp+110h+Class], r14d
0x140a95432  lea     rcx, [rbp+57h+var_D0]
0x140a95436  call    IopCreateRegistryKeyEx
0x140a9543b  mov     ebx, eax
0x140a9543d  test    eax, eax
0x140a9543f  js      loc_140A95506
0x140a95445  xor     r9d, r9d
0x140a95448  lea     r8, [rbp+57h+var_B0]
0x140a9544c  lea     rcx, aDPaiAOiciGaSy; "D:PAI(A;OICI;GA;;;SY)"
0x140a95453  lea     edx, [r9+1]
0x140a95457  call    SeConvertStringSecurityDescriptorToSecurityDescriptor
0x140a9545c  mov     r15, [rbp+57h+var_B0]
0x140a95460  lea     rdx, aProperties_1; "Properties"
0x140a95467  test    eax, eax
0x140a95469  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140a9546d  cmovs   r15, r14
0x140a95471  call    RtlInitUnicodeString
0x140a95476  mov     rsi, [rbp+57h+var_D0]
0x140a9547a  lea     rax, [rbp+57h+DestinationString]
0x140a9547e  mov     [rsp+110h+Disposition], r14; Disposition
0x140a95483  lea     r8, [rbp+57h+var_98]; ObjectAttributes
0x140a95487  mov     [rsp+110h+CreateOptions], r14d; CreateOptions
0x140a9548c  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x140a95490  xor     r9d, r9d; TitleIndex
0x140a95493  mov     [rbp+57h+var_98.ObjectName], rax
0x140a95497  mov     edx, r12d; DesiredAccess
0x140a9549a  mov     [rbp+57h+var_98.Length], 30h ; '0'
0x140a954a1  mov     [rbp+57h+var_98.RootDirectory], rsi
0x140a954a5  mov     [rbp+57h+var_98.Attributes], 240h
0x140a954ac  mov     [rbp+57h+var_98.SecurityDescriptor], r15
0x140a954b0  mov     [rbp+57h+var_98.SecurityQualityOfService], r14
0x140a954b4  mov     [rsp+110h+Class], r14; Class
0x140a954b9  call    ZwCreateKey
0x140a954be  mov     ebx, eax
0x140a954c0  test    eax, eax
0x140a954c2  js      short loc_140A95511
0x140a954c4  mov     rcx, [r13+8]; SecurityDescriptor
0x140a954c8  call    RtlLengthSecurityDescriptor
0x140a954cd  lea     rdx, aSecurity_0; "Security"
0x140a954d4  mov     ebx, eax
0x140a954d6  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140a954da  call    RtlInitUnicodeString
0x140a954df  mov     rax, [r13+8]
0x140a954e3  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140a954e7  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x140a954eb  mov     r9d, 3; Type
0x140a954f1  mov     [rsp+110h+CreateOptions], ebx; DataSize
0x140a954f5  xor     r8d, r8d; TitleIndex
0x140a954f8  mov     [rsp+110h+Class], rax; Data
0x140a954fd  call    ZwSetValueKey
0x140a95502  mov     ebx, eax
0x140a95504  jmp     short loc_140A95511
0x140a95506  mov     rsi, [rbp+57h+var_D0]
0x140a9550a  jmp     short loc_140A95511
0x140a9550c  mov     ebx, 0C000009Ah
0x140a95511  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140a95515  test    rcx, rcx
0x140a95518  jz      short loc_140A9551F
0x140a9551a  call    ZwClose
0x140a9551f  test    rsi, rsi
0x140a95522  jz      short loc_140A9552C
0x140a95524  mov     rcx, rsi; Handle
0x140a95527  call    ZwClose
0x140a9552c  mov     rcx, [rbp+57h+Handle]; Handle
0x140a95530  test    rcx, rcx
0x140a95533  jz      short loc_140A9553A
0x140a95535  call    ZwClose
0x140a9553a  test    rdi, rdi
0x140a9553d  jz      short loc_140A95549
0x140a9553f  xor     edx, edx; Tag
0x140a95541  mov     rcx, rdi; P
0x140a95544  call    ExFreePoolWithTag
0x140a95549  test    r15, r15
0x140a9554c  jz      short loc_140A95558
0x140a9554e  xor     edx, edx; Tag
0x140a95550  mov     rcx, r15; P
0x140a95553  call    ExFreePoolWithTag
0x140a95558  mov     rcx, [rbp+57h+P+8]; P
0x140a9555c  test    rcx, rcx
0x140a9555f  jz      short loc_140A95566
0x140a95561  call    ExFreePool
0x140a95566  mov     eax, ebx
0x140a95568  mov     rbx, [rsp+110h+arg_0]
0x140a95570  add     rsp, 0E0h
0x140a95577  pop     r15
0x140a95579  pop     r14
0x140a9557b  pop     r13
0x140a9557d  pop     r12
0x140a9557f  pop     rdi
0x140a95580  pop     rsi
0x140a95581  pop     rbp
0x140a95582  retn
```
