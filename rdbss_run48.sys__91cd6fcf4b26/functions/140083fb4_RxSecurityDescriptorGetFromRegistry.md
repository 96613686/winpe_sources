# RxSecurityDescriptorGetFromRegistry

- ea: `0x140083fb4`
- end: `0x1400842b1`
- name: `RxSecurityDescriptorGetFromRegistry`
- size: `765`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14008321c`

## callees

- `0x140016e20`
- `0x140025d80`
- `0x140083fb4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14008414f`
- `ntoskrnl!ExAllocatePool2` at `0x140084216`
- `ntoskrnl!ExAllocatePool2` at `0x14008414f`
- `ntoskrnl!ExAllocatePool2` at `0x140084216`
- `ntoskrnl!RtlInitUnicodeString` at `0x140084009`
- `ntoskrnl!RtlInitUnicodeString` at `0x140084021`
- `ntoskrnl!RtlInitUnicodeString` at `0x140084009`
- `ntoskrnl!RtlInitUnicodeString` at `0x140084021`
- `ntoskrnl!ZwClose` at `0x14008428d`
- `ntoskrnl!ZwClose` at `0x14008449d`
- `ntoskrnl!ZwClose` at `0x14008428d`
- `ntoskrnl!ZwClose` at `0x14008449d`
- `ntoskrnl!ZwOpenKey` at `0x140084068`
- `ntoskrnl!ZwOpenKey` at `0x140084068`
- `ntoskrnl!ZwQueryValueKey` at `0x1400840e8`
- `ntoskrnl!ZwQueryValueKey` at `0x1400841ca`
- `ntoskrnl!ZwQueryValueKey` at `0x1400840e8`
- `ntoskrnl!ZwQueryValueKey` at `0x1400841ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084274`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008447d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084274`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008447d`

## string_xrefs

- `0x140084015`: `DeviceSecurity`
- `0x140083ffe`: `\Registry\Machine\SYSTEM\CurrentControlSet\services\Ndu\Parameters`

## pseudocode

```c
char __fastcall RxSecurityDescriptorGetFromRegistry(_QWORD *a1)
{
  unsigned int *Pool2; // rbx
  char v3; // r14
  NTSTATUS v4; // eax
  __int64 v5; // r9
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  unsigned int v8; // eax
  ULONG Length; // edi
  NTSTATUS v10; // eax
  void *v11; // rax
  UNICODE_STRING DestinationString; // [rsp+38h] [rbp-70h] BYREF
  UNICODE_STRING v14; // [rsp+48h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-50h] BYREF
  ULONG ResultLength; // [rsp+B0h] [rbp+8h] BYREF
  void *KeyHandle; // [rsp+B8h] [rbp+10h] BYREF

  memset(&ObjectAttributes, 0, 44);
  v14 = 0;
  DestinationString = 0;
  KeyHandle = 0;
  Pool2 = 0;
  ResultLength = 0;
  v3 = 0;
  *a1 = 0;
  RtlInitUnicodeString(&v14, L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\services\\Ndu\\Parameters");
  RtlInitUnicodeString(&DestinationString, L"DeviceSecurity");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = &v14;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = ZwOpenKey(&KeyHandle, 0x80000000, &ObjectAttributes);
  v5 = (unsigned int)v4;
  if ( v4 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v7 = 10;
LABEL_6:
      WPP_SF_d(v6->AttachedDevice, v7, &WPP_001e8d57d6fa39c4469703a163e62a81_Traceguids, v5);
      goto LABEL_30;
    }
    goto LABEL_30;
  }
  v8 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, 0, 0, &ResultLength);
  v5 = v8;
  if ( v8 != -1073741789 && v8 != -2147483643 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v7 = 11;
      goto LABEL_6;
    }
    goto LABEL_30;
  }
  Length = ResultLength;
  Pool2 = (unsigned int *)ExAllocatePool2(258, ResultLength, 1934456914);
  if ( !Pool2 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_30;
    }
    v7 = 12;
LABEL_18:
    v5 = 3221225626LL;
    goto LABEL_6;
  }
  v10 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, Pool2, Length, &ResultLength);
  v5 = (unsigned int)v10;
  if ( v10 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v7 = 13;
      goto LABEL_6;
    }
    goto LABEL_30;
  }
  v11 = (void *)ExAllocatePool2(258, Pool2[2], 1934456914);
  *a1 = v11;
  if ( v11 )
  {
    memmove(v11, Pool2 + 3, Pool2[2]);
    v3 = 1;
    goto LABEL_30;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    v7 = 14;
    goto LABEL_18;
  }
LABEL_30:
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x734D7852u);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return v3;
}

```

## disassembly

```asm
0x140083fb4  mov     r11, rsp
0x140083fb7  mov     [r11+18h], rbx
0x140083fbb  push    rsi
0x140083fbc  push    rdi
0x140083fbd  push    r14
0x140083fbf  sub     rsp, 90h
0x140083fc6  mov     rsi, rcx
0x140083fc9  xor     eax, eax
0x140083fcb  xorps   xmm0, xmm0
0x140083fce  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.Length], xmm0
0x140083fd3  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.ObjectName], xmm0
0x140083fd8  movups  xmmword ptr [rsp+0A8h+ObjectAttributes+1Ch], xmm0
0x140083fdd  movups  [rsp+0A8h+var_60], xmm0
0x140083fe2  xorps   xmm1, xmm1
0x140083fe5  movups  xmmword ptr [rsp+0A8h+DestinationString.Length], xmm1
0x140083fea  mov     [r11+10h], rax
0x140083fee  xor     ebx, ebx
0x140083ff0  mov     [r11-78h], rbx
0x140083ff4  mov     [r11+8], eax
0x140083ff8  xor     r14b, r14b
0x140083ffb  mov     [rcx], rax
0x140083ffe  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x140084005  lea     rcx, [r11-60h]; DestinationString
0x140084009  call    cs:__imp_RtlInitUnicodeString
0x140084010  nop     dword ptr [rax+rax+00h]
0x140084015  lea     rdx, aDevicesecurity; "DeviceSecurity"
0x14008401c  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x140084021  call    cs:__imp_RtlInitUnicodeString
0x140084028  nop     dword ptr [rax+rax+00h]
0x14008402d  nop
0x14008402e  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x140084036  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], rbx
0x14008403b  mov     [rsp+0A8h+ObjectAttributes.Attributes], 240h
0x140084043  lea     rax, [rsp+0A8h+var_60]
0x140084048  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rax
0x14008404d  xorps   xmm0, xmm0
0x140084050  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x140084056  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x14008405b  mov     edx, 80000000h; DesiredAccess
0x140084060  lea     rcx, [rsp+0A8h+KeyHandle]; KeyHandle
0x140084068  call    cs:__imp_ZwOpenKey
0x14008406f  nop     dword ptr [rax+rax+00h]
0x140084074  mov     r9d, eax
0x140084077  test    eax, eax
0x140084079  jns     short loc_1400840BF
0x14008407b  lea     rax, WPP_GLOBAL_Control
0x140084082  mov     rcx, cs:WPP_GLOBAL_Control
0x140084089  cmp     rcx, rax
0x14008408c  jz      loc_140084267
0x140084092  mov     eax, [rcx+2Ch]
0x140084095  test    al, 1
0x140084097  jz      loc_140084267
0x14008409d  cmp     byte ptr [rcx+29h], 1
0x1400840a1  jb      loc_140084267
0x1400840a7  lea     edx, [rbx+0Ah]
0x1400840aa  lea     r8, WPP_001e8d57d6fa39c4469703a163e62a81_Traceguids
0x1400840b1  mov     rcx, [rcx+18h]
0x1400840b5  call    WPP_SF_d
0x1400840ba  jmp     loc_140084267
0x1400840bf  lea     rax, [rsp+0A8h+arg_0]
0x1400840c7  mov     [rsp+0A8h+ResultLength], rax; ResultLength
0x1400840cc  mov     [rsp+0A8h+Length], 0; Length
0x1400840d4  xor     r9d, r9d; KeyValueInformation
0x1400840d7  lea     r8d, [r9+2]; KeyValueInformationClass
0x1400840db  lea     rdx, [rsp+0A8h+DestinationString]; ValueName
0x1400840e0  mov     rcx, [rsp+0A8h+KeyHandle]; KeyHandle
0x1400840e8  call    cs:__imp_ZwQueryValueKey
0x1400840ef  nop     dword ptr [rax+rax+00h]
0x1400840f4  mov     r9d, eax
0x1400840f7  cmp     eax, 0C0000023h
0x1400840fc  jz      short loc_14008413B
0x1400840fe  cmp     eax, 80000005h
0x140084103  jz      short loc_14008413B
0x140084105  lea     rax, WPP_GLOBAL_Control
0x14008410c  mov     rcx, cs:WPP_GLOBAL_Control
0x140084113  cmp     rcx, rax
0x140084116  jz      loc_140084267
0x14008411c  mov     eax, [rcx+2Ch]
0x14008411f  test    al, 1
0x140084121  jz      loc_140084267
0x140084127  cmp     byte ptr [rcx+29h], 1
0x14008412b  jb      loc_140084267
0x140084131  mov     edx, 0Bh
0x140084136  jmp     loc_1400840AA
0x14008413b  mov     edi, [rsp+0A8h+arg_0]
0x140084142  mov     edx, edi
0x140084144  mov     ecx, 102h
0x140084149  mov     r8d, 734D7852h
0x14008414f  call    cs:__imp_ExAllocatePool2
0x140084156  nop     dword ptr [rax+rax+00h]
0x14008415b  mov     rbx, rax
0x14008415e  mov     [rsp+0A8h+var_78], rax
0x140084163  test    rax, rax
0x140084166  jnz     short loc_1400841A3
0x140084168  lea     rax, WPP_GLOBAL_Control
0x14008416f  mov     rcx, cs:WPP_GLOBAL_Control
0x140084176  cmp     rcx, rax
0x140084179  jz      loc_140084267
0x14008417f  mov     edx, [rcx+2Ch]
0x140084182  test    dl, 1
0x140084185  jz      loc_140084267
0x14008418b  cmp     byte ptr [rcx+29h], 1
0x14008418f  jb      loc_140084267
0x140084195  lea     edx, [rbx+0Ch]
0x140084198  mov     r9d, 0C000009Ah
0x14008419e  jmp     loc_1400840AA
0x1400841a3  lea     rax, [rsp+0A8h+arg_0]
0x1400841ab  mov     [rsp+0A8h+ResultLength], rax; ResultLength
0x1400841b0  mov     [rsp+0A8h+Length], edi; Length
0x1400841b4  mov     r9, rbx; KeyValueInformation
0x1400841b7  mov     r8d, 2; KeyValueInformationClass
0x1400841bd  lea     rdx, [rsp+0A8h+DestinationString]; ValueName
0x1400841c2  mov     rcx, [rsp+0A8h+KeyHandle]; KeyHandle
0x1400841ca  call    cs:__imp_ZwQueryValueKey
0x1400841d1  nop     dword ptr [rax+rax+00h]
0x1400841d6  mov     r9d, eax
0x1400841d9  test    eax, eax
0x1400841db  jns     short loc_140084208
0x1400841dd  lea     rax, WPP_GLOBAL_Control
0x1400841e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400841eb  cmp     rcx, rax
0x1400841ee  jz      short loc_140084267
0x1400841f0  mov     edx, [rcx+2Ch]
0x1400841f3  test    dl, 1
0x1400841f6  jz      short loc_140084267
0x1400841f8  cmp     byte ptr [rcx+29h], 1
0x1400841fc  jb      short loc_140084267
0x1400841fe  mov     edx, 0Dh
0x140084203  jmp     loc_1400840AA
0x140084208  mov     edx, [rbx+8]
0x14008420b  mov     ecx, 102h
0x140084210  mov     r8d, 734D7852h
0x140084216  call    cs:__imp_ExAllocatePool2
0x14008421d  nop     dword ptr [rax+rax+00h]
0x140084222  mov     [rsi], rax
0x140084225  test    rax, rax
0x140084228  jnz     short loc_140084254
0x14008422a  lea     rax, WPP_GLOBAL_Control
0x140084231  mov     rcx, cs:WPP_GLOBAL_Control
0x140084238  cmp     rcx, rax
0x14008423b  jz      short loc_140084267
0x14008423d  mov     eax, [rcx+2Ch]
0x140084240  test    al, 1
0x140084242  jz      short loc_140084267
0x140084244  cmp     byte ptr [rcx+29h], 1
0x140084248  jb      short loc_140084267
0x14008424a  mov     edx, 0Eh
0x14008424f  jmp     loc_140084198
0x140084254  mov     r8d, [rbx+8]; Size
0x140084258  lea     rdx, [rbx+0Ch]; Src
0x14008425c  mov     rcx, rax; void *
0x14008425f  call    memmove
0x140084264  mov     r14b, 1
0x140084267  test    rbx, rbx
0x14008426a  jz      short loc_140084280
0x14008426c  mov     edx, 734D7852h; Tag
0x140084271  mov     rcx, rbx; P
0x140084274  call    cs:__imp_ExFreePoolWithTag
0x14008427b  nop     dword ptr [rax+rax+00h]
0x140084280  mov     rcx, [rsp+0A8h+KeyHandle]; Handle
0x140084288  test    rcx, rcx
0x14008428b  jz      short loc_140084299
0x14008428d  call    cs:__imp_ZwClose
0x140084294  nop     dword ptr [rax+rax+00h]
0x140084299  mov     al, r14b
0x14008429c  mov     rbx, [rsp+0A8h+arg_10]
0x1400842a4  add     rsp, 90h
0x1400842ab  pop     r14
0x1400842ad  pop     rdi
0x1400842ae  pop     rsi
0x1400842af  retn
0x140084466  push    rbp
0x140084468  sub     rsp, 30h
0x14008446c  mov     rbp, rdx
0x14008446f  mov     rcx, [rbp+30h]; P
0x140084473  test    rcx, rcx
0x140084476  jz      short loc_140084491
0x140084478  mov     edx, 734D7852h; Tag
0x14008447d  call    cs:__imp_ExFreePoolWithTag
0x140084484  nop     dword ptr [rax+rax+00h]
0x140084489  mov     qword ptr [rbp+30h], 0
0x140084491  mov     rcx, [rbp+0B8h]; Handle
0x140084498  test    rcx, rcx
0x14008449b  jz      short loc_1400844AA
0x14008449d  call    cs:__imp_ZwClose
0x1400844a4  nop     dword ptr [rax+rax+00h]
0x1400844a9  nop
0x1400844aa  add     rsp, 30h
0x1400844ae  pop     rbp
0x1400844af  retn
```
