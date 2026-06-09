# BfsReadDeleteThresholdFromRegistry

- ea: `0x14000d2d4`
- end: `0x14000d584`
- name: `BfsReadDeleteThresholdFromRegistry`
- size: `688`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001f078`

## callees

- `0x140001008`
- `0x14000d2d4`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14000d372`
- `ntoskrnl!ZwOpenKey` at `0x14000d372`
- `ntoskrnl!ZwQueryValueKey` at `0x14000d3dd`
- `ntoskrnl!ZwQueryValueKey` at `0x14000d44f`
- `ntoskrnl!ZwQueryValueKey` at `0x14000d4b0`
- `ntoskrnl!ZwQueryValueKey` at `0x14000d513`
- `ntoskrnl!ZwQueryValueKey` at `0x14000d3dd`
- `ntoskrnl!ZwQueryValueKey` at `0x14000d44f`
- `ntoskrnl!ZwQueryValueKey` at `0x14000d4b0`
- `ntoskrnl!ZwQueryValueKey` at `0x14000d513`
- `ntoskrnl!ZwClose` at `0x14000d545`
- `ntoskrnl!ZwClose` at `0x14000d545`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d487`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d55b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d487`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d55b`
- `ntoskrnl!ExAllocatePool2` at `0x14000d402`
- `ntoskrnl!ExAllocatePool2` at `0x14000d4dd`
- `ntoskrnl!ExAllocatePool2` at `0x14000d402`
- `ntoskrnl!ExAllocatePool2` at `0x14000d4dd`

## string_xrefs

- `0x14000d300`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\FileSystem`

## pseudocode

```c
__int64 BfsReadDeleteThresholdFromRegistry()
{
  unsigned int v0; // edi
  _DWORD *Pool2; // rbx
  NTSTATUS v2; // ecx
  int v3; // r8d
  int v4; // r9d
  ULONG v5; // esi
  NTSTATUS v6; // eax
  ULONG v7; // esi
  unsigned int v8; // eax
  ULONG Length; // [rsp+20h] [rbp-89h]
  int v11; // [rsp+30h] [rbp-79h] BYREF
  ULONG ResultLength; // [rsp+34h] [rbp-75h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-71h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-69h] BYREF
  struct _UNICODE_STRING v15; // [rsp+50h] [rbp-59h] BYREF
  _QWORD v16[2]; // [rsp+60h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+A0h] [rbp-9h] BYREF
  int *v19; // [rsp+C0h] [rbp+17h]
  __int64 v20; // [rsp+C8h] [rbp+1Fh]

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v16[1] = L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\FileSystem";
  KeyHandle = 0;
  ValueName.Buffer = L"MaximumTunnelEntries";
  ResultLength = 0;
  v15.Buffer = L"MaximumTunnelEntryAgeInSeconds";
  v16[0] = 8126586;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v16;
  v0 = 150000000;
  *(_QWORD *)&ValueName.Length = 2752552;
  Pool2 = 0;
  *(_QWORD *)&v15.Length = 4063292;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v2 < 0 )
    goto LABEL_2;
  v2 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, 0, 0, &ResultLength);
  if ( v2 != -1073741789 )
    goto LABEL_2;
  v5 = ResultLength;
  Pool2 = (_DWORD *)ExAllocatePool2(256, ResultLength, 1985111618);
  if ( !Pool2 )
    goto LABEL_7;
  v6 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, Pool2, v5, &ResultLength);
  if ( v6 < 0 )
  {
    if ( v6 != -1073741772 )
      goto LABEL_22;
  }
  else
  {
    if ( Pool2[1] != 4 )
      goto LABEL_22;
    if ( !Pool2[3] )
    {
      v0 = 0;
      goto LABEL_22;
    }
  }
  ExFreePoolWithTag(Pool2, 0);
  v2 = ZwQueryValueKey(KeyHandle, &v15, KeyValuePartialInformation, 0, 0, &ResultLength);
  if ( v2 != -1073741789 )
  {
    Pool2 = 0;
LABEL_2:
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_22;
    v11 = v2;
    goto LABEL_4;
  }
  v7 = ResultLength;
  Pool2 = (_DWORD *)ExAllocatePool2(256, ResultLength, 1985111618);
  if ( Pool2 )
  {
    if ( ZwQueryValueKey(KeyHandle, &v15, KeyValuePartialInformation, Pool2, v7, &ResultLength) >= 0 && Pool2[1] == 4 )
    {
      v8 = Pool2[3];
      if ( v8 > 0x47 )
        v8 = 71;
      v0 = 10000000 * v8;
    }
    goto LABEL_22;
  }
LABEL_7:
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v11 = -1073741801;
LABEL_4:
    v20 = 4;
    v19 = &v11;
    tlgWriteTransfer_EtwWriteTransfer(v2, (int)&byte_140016D91, v3, v4, Length, &v18);
  }
LABEL_22:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0);
  return v0;
}

```

## disassembly

```asm
0x14000d2d4  push    rbp
0x14000d2d6  push    rbx
0x14000d2d7  push    rsi
0x14000d2d8  push    rdi
0x14000d2d9  push    r14
0x14000d2db  lea     rbp, [rsp-37h]
0x14000d2e0  sub     rsp, 0E0h
0x14000d2e7  mov     rax, cs:__security_cookie
0x14000d2ee  xor     rax, rsp
0x14000d2f1  mov     [rbp+57h+var_30], rax
0x14000d2f5  xor     r14d, r14d
0x14000d2f8  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000d300  lea     rax, aRegistryMachin; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x14000d307  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x14000d30f  mov     [rbp+57h+var_98], rax
0x14000d313  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000d317  lea     rax, aMaximumtunnele_0; "MaximumTunnelEntries"
0x14000d31e  mov     [rbp+57h+KeyHandle], r14
0x14000d322  mov     [rbp+57h+ValueName.Buffer], rax
0x14000d326  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d32a  lea     rax, aMaximumtunnele; "MaximumTunnelEntryAgeInSeconds"
0x14000d331  mov     [rbp+57h+var_CC], r14d
0x14000d335  mov     [rbp+57h+var_B0.Buffer], rax
0x14000d339  xorps   xmm0, xmm0
0x14000d33c  lea     rax, [rbp+57h+var_A0]
0x14000d340  mov     [rbp+57h+var_A0], 7C007Ah
0x14000d348  mov     edx, 20019h; DesiredAccess
0x14000d34d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000d351  mov     edi, 8F0D180h
0x14000d356  mov     qword ptr [rbp+57h+ValueName.Length], 2A0028h
0x14000d35e  mov     ebx, r14d
0x14000d361  mov     qword ptr [rbp+57h+var_B0.Length], 3E003Ch
0x14000d369  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x14000d36d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000d372  call    cs:__imp_ZwOpenKey
0x14000d379  nop     dword ptr [rax+rax+00h]
0x14000d37e  mov     ecx, eax; int
0x14000d380  test    eax, eax
0x14000d382  jns     short loc_14000D3C0
0x14000d384  mov     eax, cs:dword_140019000
0x14000d38a  cmp     eax, 3
0x14000d38d  jbe     loc_14000D53C
0x14000d393  mov     [rbp+57h+var_D0], ecx
0x14000d396  lea     rax, [rbp+57h+var_D0]
0x14000d39a  mov     [rbp+57h+var_38], 4
0x14000d3a2  mov     [rbp+57h+var_40], rax
0x14000d3a6  lea     rdx, byte_140016D91; int
0x14000d3ad  lea     rax, [rbp+57h+var_60]
0x14000d3b1  mov     [rsp+100h+ResultLength], rax; PEVENT_DATA_DESCRIPTOR
0x14000d3b6  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000d3bb  jmp     loc_14000D53C
0x14000d3c0  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d3c4  lea     rax, [rbp+57h+var_CC]
0x14000d3c8  xor     r9d, r9d; KeyValueInformation
0x14000d3cb  mov     [rsp+100h+ResultLength], rax; ResultLength
0x14000d3d0  lea     rdx, [rbp+57h+ValueName]; ValueName
0x14000d3d4  mov     [rsp+100h+Length], r14d; Length
0x14000d3d9  lea     r8d, [r9+2]; KeyValueInformationClass
0x14000d3dd  call    cs:__imp_ZwQueryValueKey
0x14000d3e4  nop     dword ptr [rax+rax+00h]
0x14000d3e9  mov     ecx, eax
0x14000d3eb  cmp     eax, 0C0000023h
0x14000d3f0  jnz     short loc_14000D384
0x14000d3f2  mov     esi, [rbp+57h+var_CC]
0x14000d3f5  mov     ecx, 100h
0x14000d3fa  mov     edx, esi
0x14000d3fc  mov     r8d, 76526642h
0x14000d402  call    cs:__imp_ExAllocatePool2
0x14000d409  nop     dword ptr [rax+rax+00h]
0x14000d40e  mov     rbx, rax
0x14000d411  test    rax, rax
0x14000d414  jnz     short loc_14000D431
0x14000d416  mov     eax, cs:dword_140019000
0x14000d41c  cmp     eax, 3
0x14000d41f  jbe     loc_14000D53C
0x14000d425  mov     [rbp+57h+var_D0], 0C0000017h
0x14000d42c  jmp     loc_14000D396
0x14000d431  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d435  lea     rax, [rbp+57h+var_CC]
0x14000d439  mov     [rsp+100h+ResultLength], rax; ResultLength
0x14000d43e  lea     rdx, [rbp+57h+ValueName]; ValueName
0x14000d442  mov     r9, rbx; KeyValueInformation
0x14000d445  mov     [rsp+100h+Length], esi; Length
0x14000d449  mov     r8d, 2; KeyValueInformationClass
0x14000d44f  call    cs:__imp_ZwQueryValueKey
0x14000d456  nop     dword ptr [rax+rax+00h]
0x14000d45b  test    eax, eax
0x14000d45d  js      short loc_14000D477
0x14000d45f  cmp     dword ptr [rbx+4], 4
0x14000d463  jnz     loc_14000D53C
0x14000d469  cmp     [rbx+0Ch], r14d
0x14000d46d  jnz     short loc_14000D482
0x14000d46f  mov     edi, r14d
0x14000d472  jmp     loc_14000D53C
0x14000d477  cmp     eax, 0C0000034h
0x14000d47c  jnz     loc_14000D53C
0x14000d482  xor     edx, edx; Tag
0x14000d484  mov     rcx, rbx; P
0x14000d487  call    cs:__imp_ExFreePoolWithTag
0x14000d48e  nop     dword ptr [rax+rax+00h]
0x14000d493  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d497  lea     rax, [rbp+57h+var_CC]
0x14000d49b  xor     r9d, r9d; KeyValueInformation
0x14000d49e  mov     [rsp+100h+ResultLength], rax; ResultLength
0x14000d4a3  lea     rdx, [rbp+57h+var_B0]; ValueName
0x14000d4a7  mov     [rsp+100h+Length], r14d; Length
0x14000d4ac  lea     r8d, [r9+2]; KeyValueInformationClass
0x14000d4b0  call    cs:__imp_ZwQueryValueKey
0x14000d4b7  nop     dword ptr [rax+rax+00h]
0x14000d4bc  mov     ecx, eax
0x14000d4be  cmp     eax, 0C0000023h
0x14000d4c3  jz      short loc_14000D4CD
0x14000d4c5  mov     rbx, r14
0x14000d4c8  jmp     loc_14000D384
0x14000d4cd  mov     esi, [rbp+57h+var_CC]
0x14000d4d0  mov     ecx, 100h
0x14000d4d5  mov     edx, esi
0x14000d4d7  mov     r8d, 76526642h
0x14000d4dd  call    cs:__imp_ExAllocatePool2
0x14000d4e4  nop     dword ptr [rax+rax+00h]
0x14000d4e9  mov     rbx, rax
0x14000d4ec  test    rax, rax
0x14000d4ef  jz      loc_14000D416
0x14000d4f5  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d4f9  lea     rax, [rbp+57h+var_CC]
0x14000d4fd  mov     [rsp+100h+ResultLength], rax; ResultLength
0x14000d502  lea     rdx, [rbp+57h+var_B0]; ValueName
0x14000d506  mov     r9, rbx; KeyValueInformation
0x14000d509  mov     [rsp+100h+Length], esi; Length
0x14000d50d  mov     r8d, 2; KeyValueInformationClass
0x14000d513  call    cs:__imp_ZwQueryValueKey
0x14000d51a  nop     dword ptr [rax+rax+00h]
0x14000d51f  test    eax, eax
0x14000d521  js      short loc_14000D53C
0x14000d523  cmp     dword ptr [rbx+4], 4
0x14000d527  jnz     short loc_14000D53C
0x14000d529  mov     eax, [rbx+0Ch]
0x14000d52c  mov     ecx, 47h ; 'G'
0x14000d531  cmp     eax, ecx
0x14000d533  cmova   eax, ecx
0x14000d536  imul    edi, eax, 989680h
0x14000d53c  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14000d540  test    rcx, rcx
0x14000d543  jz      short loc_14000D551
0x14000d545  call    cs:__imp_ZwClose
0x14000d54c  nop     dword ptr [rax+rax+00h]
0x14000d551  test    rbx, rbx
0x14000d554  jz      short loc_14000D567
0x14000d556  xor     edx, edx; Tag
0x14000d558  mov     rcx, rbx; P
0x14000d55b  call    cs:__imp_ExFreePoolWithTag
0x14000d562  nop     dword ptr [rax+rax+00h]
0x14000d567  mov     eax, edi
0x14000d569  mov     rcx, [rbp+57h+var_30]
0x14000d56d  xor     rcx, rsp; StackCookie
0x14000d570  call    __security_check_cookie
0x14000d575  add     rsp, 0E0h
0x14000d57c  pop     r14
0x14000d57e  pop     rdi
0x14000d57f  pop     rsi
0x14000d580  pop     rbx
0x14000d581  pop     rbp
0x14000d582  retn
```
