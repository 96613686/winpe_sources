# ClfsRegistryQuerySystemTempPath(_UNICODE_STRING &)

- ea: `0x14004e3d4`
- end: `0x14004e7b9`
- name: `?ClfsRegistryQuerySystemTempPath@@YAJAEAU_UNICODE_STRING@@@Z`
- size: `997`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14003ba50`

## callees

- `0x14000eef0`
- `0x140010404`
- `0x140018280`
- `0x14004e3d4`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x14004e6c5`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14004e6c5`
- `ntoskrnl!ZwClose` at `0x14004e757`
- `ntoskrnl!ZwClose` at `0x1400807b9`
- `ntoskrnl!ZwClose` at `0x14004e757`
- `ntoskrnl!ZwClose` at `0x1400807b9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004e6dd`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004e6fb`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004e6dd`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004e6fb`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004e72d`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004e72d`
- `ntoskrnl!ZwOpenKey` at `0x14004e4e4`
- `ntoskrnl!ZwOpenKey` at `0x14004e4e4`
- `ntoskrnl!ZwQueryValueKey` at `0x14004e5c1`
- `ntoskrnl!ZwQueryValueKey` at `0x14004e5c1`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14004e461`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14004e461`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004e44e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004e488`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004e6ac`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004e44e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004e488`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004e6ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e550`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e779`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e794`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400807db`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080809`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e550`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e779`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e794`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400807db`
- `ntoskrnl!ExFreePoolWithTag` at `0x140080809`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004e573`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004e66f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004e573`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004e66f`

## string_xrefs

- `0x14004e443`: `SystemTemp`
- `0x14004e478`: `\REGISTRY\MACHINE\OSDATA\Session Manager`
- `0x14004e481`: `\Registry\Machine\System\CurrentControlSet\Control\Session Manager\Environment`

## pseudocode

```c
__int64 __fastcall ClfsRegistryQuerySystemTempPath(PUNICODE_STRING Destination)
{
  unsigned int v2; // r15d
  WCHAR *PoolWithTag; // rdi
  char i; // r14
  const WCHAR *v5; // rdx
  NTSTATUS appended; // ebx
  SIZE_T Length; // r14
  NTSTATUS v8; // eax
  unsigned int v9; // ecx
  unsigned __int16 *p_MaximumLength; // r14
  wchar_t *v11; // rax
  wchar_t *Buffer; // rcx
  UNICODE_STRING String1; // [rsp+48h] [rbp-A0h] BYREF
  unsigned int v15; // [rsp+58h] [rbp-90h]
  UNICODE_STRING DestinationString; // [rsp+60h] [rbp-88h] BYREF
  UNICODE_STRING String2; // [rsp+70h] [rbp-78h] BYREF
  UNICODE_STRING ValueName; // [rsp+80h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-58h] BYREF
  SIZE_T NumberOfBytes; // [rsp+F8h] [rbp+10h] BYREF
  void *KeyHandle; // [rsp+100h] [rbp+18h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  ValueName = 0;
  String2 = 0;
  *(_QWORD *)&String1.Length = 655368;
  String1.Buffer = (wchar_t *)L"\\??\\";
  v2 = 0;
  PoolWithTag = 0;
  LODWORD(NumberOfBytes) = 0;
  RtlInitUnicodeString(&ValueName, L"SystemTemp");
  *Destination = 0;
  for ( i = RtlIsStateSeparationEnabled(); ; i = 0 )
  {
    v5 = L"\\REGISTRY\\MACHINE\\OSDATA\\Session Manager";
    if ( !i )
      v5 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Session Manager\\Environment";
    RtlInitUnicodeString(&DestinationString, v5);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    appended = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
    if ( appended >= 0 )
      break;
    if ( !i )
      goto LABEL_31;
  }
  LODWORD(Length) = 0;
  LODWORD(NumberOfBytes) = 0;
  PoolWithTag = 0;
  do
  {
    if ( (_DWORD)NumberOfBytes )
    {
      Length = (unsigned int)NumberOfBytes;
      if ( PoolWithTag )
        ExFreePoolWithTag(PoolWithTag, 0);
      PoolWithTag = (WCHAR *)ExAllocatePoolWithTag(PagedPool, Length, 0x73666C43u);
      if ( !PoolWithTag )
        goto LABEL_13;
    }
    v8 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, PoolWithTag, Length, (PULONG)&NumberOfBytes);
    appended = v8;
    v15 = ++v2;
  }
  while ( (v8 == -1073741789 || v8 == -2147483643) && v2 < 3 );
  if ( v8 >= 0 )
  {
    if ( *((_DWORD *)PoolWithTag + 1) == 1 )
    {
      v9 = *((_DWORD *)PoolWithTag + 2);
      if ( v9 < 2 || (v9 & 1) != 0 )
      {
        appended = -1073741811;
      }
      else
      {
        p_MaximumLength = &Destination->MaximumLength;
        appended = RtlULongToUShort(v9, &Destination->MaximumLength);
        if ( appended >= 0 )
        {
          appended = RtlUShortAdd(*p_MaximumLength, String1.Length + 6, &Destination->MaximumLength);
          if ( appended >= 0 )
          {
            Destination->Length = 0;
            v11 = (wchar_t *)ExAllocatePoolWithTag(PagedPool, *p_MaximumLength, 0x73666C43u);
            Destination->Buffer = v11;
            if ( !v11 )
            {
LABEL_13:
              appended = -1073741670;
              goto LABEL_31;
            }
            memset(v11, 0, *p_MaximumLength);
            PoolWithTag[((unsigned __int64)*((unsigned int *)PoolWithTag + 2) >> 1) + 5] = 0;
            RtlInitUnicodeString(&String2, PoolWithTag + 6);
            if ( RtlPrefixUnicodeString(&String1, &String2, 1u)
              || (appended = RtlAppendUnicodeStringToString(Destination, &String1), appended >= 0) )
            {
              appended = RtlAppendUnicodeStringToString(Destination, &String2);
              if ( appended >= 0 && Destination->Buffer[((unsigned __int64)Destination->Length >> 1) - 1] != 92 )
                appended = RtlAppendUnicodeToString(Destination, L"\\");
            }
          }
        }
      }
    }
    else
    {
      appended = -1073741788;
    }
  }
LABEL_31:
  if ( KeyHandle )
  {
    ZwClose(KeyHandle);
    KeyHandle = 0;
  }
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0);
  if ( appended < 0 )
  {
    Buffer = Destination->Buffer;
    if ( Buffer )
      ExFreePoolWithTag(Buffer, 0);
    *Destination = 0;
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14004e3d4  mov     r11, rsp
0x14004e3d7  mov     [r11+8], rcx
0x14004e3db  push    rbx
0x14004e3dc  push    rsi
0x14004e3dd  push    rdi
0x14004e3de  push    r14
0x14004e3e0  push    r15
0x14004e3e2  sub     rsp, 0C0h
0x14004e3e9  mov     rsi, rcx
0x14004e3ec  mov     [rsp+0E8h+var_B8], 0
0x14004e3f4  mov     qword ptr [r11+18h], 0
0x14004e3fc  xorps   xmm0, xmm0
0x14004e3ff  movups  xmmword ptr [r11-58h], xmm0
0x14004e404  movups  xmmword ptr [r11-48h], xmm0
0x14004e409  movups  xmmword ptr [r11-38h], xmm0
0x14004e40e  movups  xmmword ptr [rsp+0E8h+DestinationString.Length], xmm0
0x14004e413  xorps   xmm1, xmm1
0x14004e416  movups  xmmword ptr [r11-68h], xmm1
0x14004e41b  movups  xmmword ptr [rsp+0E8h+String2.Length], xmm0
0x14004e420  mov     qword ptr [rsp+0E8h+String1.Length], 0A0008h
0x14004e429  lea     rax, asc_14001C860; "\\??\\"
0x14004e430  mov     [rsp+0E8h+String1.Buffer], rax
0x14004e435  xor     r15d, r15d
0x14004e438  xor     edi, edi
0x14004e43a  mov     [rsp+0E8h+var_B0], rdi
0x14004e43f  mov     [r11+10h], edi
0x14004e443  lea     rdx, aSystemtemp; "SystemTemp"
0x14004e44a  lea     rcx, [r11-68h]; DestinationString
0x14004e44e  call    cs:__imp_RtlInitUnicodeString
0x14004e455  nop     dword ptr [rax+rax+00h]
0x14004e45a  xorps   xmm0, xmm0
0x14004e45d  movdqu  xmmword ptr [rsi], xmm0
0x14004e461  call    cs:__imp_RtlIsStateSeparationEnabled
0x14004e468  nop     dword ptr [rax+rax+00h]
0x14004e46d  mov     r14b, al
0x14004e470  lea     rcx, [rsp+0E8h+DestinationString]; DestinationString
0x14004e475  test    r14b, r14b
0x14004e478  lea     rdx, aRegistryMachin_1; "\\REGISTRY\\MACHINE\\OSDATA\\Session Ma"...
0x14004e47f  jnz     short loc_14004E488
0x14004e481  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x14004e488  call    cs:__imp_RtlInitUnicodeString
0x14004e48f  nop     dword ptr [rax+rax+00h]
0x14004e494  mov     [rsp+0E8h+ObjectAttributes.Length], 30h ; '0'
0x14004e49f  mov     [rsp+0E8h+ObjectAttributes.RootDirectory], 0
0x14004e4ab  mov     [rsp+0E8h+ObjectAttributes.Attributes], 240h
0x14004e4b6  lea     rax, [rsp+0E8h+DestinationString]
0x14004e4bb  mov     [rsp+0E8h+ObjectAttributes.ObjectName], rax
0x14004e4c3  xorps   xmm0, xmm0
0x14004e4c6  movdqu  xmmword ptr [rsp+0E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x14004e4cf  lea     r8, [rsp+0E8h+ObjectAttributes]; ObjectAttributes
0x14004e4d7  mov     edx, 1; DesiredAccess
0x14004e4dc  lea     rcx, [rsp+0E8h+KeyHandle]; KeyHandle
0x14004e4e4  call    cs:__imp_ZwOpenKey
0x14004e4eb  nop     dword ptr [rax+rax+00h]
0x14004e4f0  mov     ebx, eax
0x14004e4f2  mov     [rsp+0E8h+var_B8], eax
0x14004e4f6  test    eax, eax
0x14004e4f8  jns     short loc_14004E51C
0x14004e4fa  test    r14b, r14b
0x14004e4fd  jz      short loc_14004E50F
0x14004e4ff  xor     r14b, r14b
0x14004e502  mov     [rsp+0E8h+var_B8], 0
0x14004e50a  jmp     loc_14004E470
0x14004e50f  test    eax, eax
0x14004e511  jns     short loc_14004E51C
0x14004e513  test    r14b, r14b
0x14004e516  jz      loc_14004E74A
0x14004e51c  xor     r14d, r14d
0x14004e51f  mov     [rsp+0E8h+var_A8], r14d
0x14004e524  mov     dword ptr [rsp+0E8h+NumberOfBytes], r14d
0x14004e52c  xor     edi, edi
0x14004e52e  mov     [rsp+0E8h+var_B0], rdi
0x14004e533  mov     eax, dword ptr [rsp+0E8h+NumberOfBytes]
0x14004e53a  test    eax, eax
0x14004e53c  jz      short loc_14004E596
0x14004e53e  mov     r14d, eax
0x14004e541  mov     [rsp+0E8h+var_A8], r14d
0x14004e546  test    rdi, rdi
0x14004e549  jz      short loc_14004E565
0x14004e54b  xor     edx, edx; Tag
0x14004e54d  mov     rcx, rdi; P
0x14004e550  call    cs:__imp_ExFreePoolWithTag
0x14004e557  nop     dword ptr [rax+rax+00h]
0x14004e55c  mov     [rsp+0E8h+var_B0], 0
0x14004e565  mov     rdx, r14; NumberOfBytes
0x14004e568  mov     ecx, 1; PoolType
0x14004e56d  mov     r8d, 73666C43h; Tag
0x14004e573  call    cs:__imp_ExAllocatePoolWithTag
0x14004e57a  nop     dword ptr [rax+rax+00h]
0x14004e57f  mov     rdi, rax
0x14004e582  mov     [rsp+0E8h+var_B0], rax
0x14004e587  test    rax, rax
0x14004e58a  jnz     short loc_14004E596
0x14004e58c  mov     ebx, 0C000009Ah
0x14004e591  jmp     loc_14004E746
0x14004e596  lea     rax, [rsp+0E8h+NumberOfBytes]
0x14004e59e  mov     [rsp+0E8h+ResultLength], rax; ResultLength
0x14004e5a3  mov     [rsp+0E8h+Length], r14d; Length
0x14004e5a8  mov     r9, rdi; KeyValueInformation
0x14004e5ab  mov     r8d, 2; KeyValueInformationClass
0x14004e5b1  lea     rdx, [rsp+0E8h+ValueName]; ValueName
0x14004e5b9  mov     rcx, [rsp+0E8h+KeyHandle]; KeyHandle
0x14004e5c1  call    cs:__imp_ZwQueryValueKey
0x14004e5c8  nop     dword ptr [rax+rax+00h]
0x14004e5cd  mov     ebx, eax
0x14004e5cf  mov     [rsp+0E8h+var_B8], eax
0x14004e5d3  inc     r15d
0x14004e5d6  mov     [rsp+0E8h+var_90], r15d
0x14004e5db  cmp     eax, 0C0000023h
0x14004e5e0  jz      short loc_14004E5E9
0x14004e5e2  cmp     eax, 80000005h
0x14004e5e7  jnz     short loc_14004E5F3
0x14004e5e9  cmp     r15d, 3
0x14004e5ed  jb      loc_14004E533
0x14004e5f3  test    eax, eax
0x14004e5f5  js      loc_14004E74A
0x14004e5fb  cmp     dword ptr [rdi+4], 1
0x14004e5ff  jz      short loc_14004E60B
0x14004e601  mov     ebx, 0C0000024h
0x14004e606  jmp     loc_14004E746
0x14004e60b  mov     ecx, [rdi+8]; unsigned int
0x14004e60e  cmp     ecx, 2
0x14004e611  jb      loc_14004E741
0x14004e617  test    cl, 1
0x14004e61a  jnz     loc_14004E741
0x14004e620  lea     r14, [rsi+2]
0x14004e624  mov     rdx, r14; unsigned __int16 *
0x14004e627  call    ?RtlULongToUShort@@YAJKPEAG@Z; RtlULongToUShort(ulong,ushort *)
0x14004e62c  mov     ebx, eax
0x14004e62e  mov     [rsp+0E8h+var_B8], eax
0x14004e632  test    eax, eax
0x14004e634  js      loc_14004E74A
0x14004e63a  movzx   edx, [rsp+0E8h+String1.Length]
0x14004e63f  add     dx, 6; unsigned __int16
0x14004e643  mov     r8, r14; unsigned __int16 *
0x14004e646  movzx   ecx, word ptr [r14]; unsigned __int16
0x14004e64a  call    ?RtlUShortAdd@@YAJGGPEAG@Z; RtlUShortAdd(ushort,ushort,ushort *)
0x14004e64f  mov     ebx, eax
0x14004e651  mov     [rsp+0E8h+var_B8], eax
0x14004e655  test    eax, eax
0x14004e657  js      loc_14004E74A
0x14004e65d  xor     eax, eax
0x14004e65f  mov     [rsi], ax
0x14004e662  movzx   edx, word ptr [r14]; NumberOfBytes
0x14004e666  lea     ecx, [rax+1]; PoolType
0x14004e669  mov     r8d, 73666C43h; Tag
0x14004e66f  call    cs:__imp_ExAllocatePoolWithTag
0x14004e676  nop     dword ptr [rax+rax+00h]
0x14004e67b  mov     [rsi+8], rax
0x14004e67f  test    rax, rax
0x14004e682  jz      loc_14004E58C
0x14004e688  movzx   r8d, word ptr [r14]; Size
0x14004e68c  xor     edx, edx; Val
0x14004e68e  mov     rcx, rax; void *
0x14004e691  call    memset
0x14004e696  lea     rdx, [rdi+0Ch]; SourceString
0x14004e69a  mov     ecx, [rdi+8]
0x14004e69d  shr     rcx, 1
0x14004e6a0  xor     eax, eax
0x14004e6a2  mov     [rdx+rcx*2-2], ax
0x14004e6a7  lea     rcx, [rsp+0E8h+String2]; DestinationString
0x14004e6ac  call    cs:__imp_RtlInitUnicodeString
0x14004e6b3  nop     dword ptr [rax+rax+00h]
0x14004e6b8  mov     r8b, 1; CaseInSensitive
0x14004e6bb  lea     rdx, [rsp+0E8h+String2]; String2
0x14004e6c0  lea     rcx, [rsp+0E8h+String1]; String1
0x14004e6c5  call    cs:__imp_RtlPrefixUnicodeString
0x14004e6cc  nop     dword ptr [rax+rax+00h]
0x14004e6d1  test    al, al
0x14004e6d3  jnz     short loc_14004E6F3
0x14004e6d5  lea     rdx, [rsp+0E8h+String1]; Source
0x14004e6da  mov     rcx, rsi; Destination
0x14004e6dd  call    cs:__imp_RtlAppendUnicodeStringToString
0x14004e6e4  nop     dword ptr [rax+rax+00h]
0x14004e6e9  mov     ebx, eax
0x14004e6eb  mov     [rsp+0E8h+var_B8], eax
0x14004e6ef  test    eax, eax
0x14004e6f1  js      short loc_14004E74A
0x14004e6f3  lea     rdx, [rsp+0E8h+String2]; Source
0x14004e6f8  mov     rcx, rsi; Destination
0x14004e6fb  call    cs:__imp_RtlAppendUnicodeStringToString
0x14004e702  nop     dword ptr [rax+rax+00h]
0x14004e707  mov     ebx, eax
0x14004e709  mov     [rsp+0E8h+var_B8], eax
0x14004e70d  test    eax, eax
0x14004e70f  js      short loc_14004E74A
0x14004e711  movzx   ecx, word ptr [rsi]
0x14004e714  shr     rcx, 1
0x14004e717  mov     rax, [rsi+8]
0x14004e71b  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14004e721  jz      short loc_14004E74A
0x14004e723  lea     rdx, Source; "\\"
0x14004e72a  mov     rcx, rsi; Destination
0x14004e72d  call    cs:__imp_RtlAppendUnicodeToString
0x14004e734  nop     dword ptr [rax+rax+00h]
0x14004e739  mov     ebx, eax
0x14004e73b  mov     [rsp+0E8h+var_B8], eax
0x14004e73f  jmp     short loc_14004E74A
0x14004e741  mov     ebx, 0C000000Dh
0x14004e746  mov     [rsp+0E8h+var_B8], ebx
0x14004e74a  mov     rcx, [rsp+0E8h+KeyHandle]; Handle
0x14004e752  test    rcx, rcx
0x14004e755  jz      short loc_14004E76F
0x14004e757  call    cs:__imp_ZwClose
0x14004e75e  nop     dword ptr [rax+rax+00h]
0x14004e763  mov     [rsp+0E8h+KeyHandle], 0
0x14004e76f  test    rdi, rdi
0x14004e772  jz      short loc_14004E785
0x14004e774  xor     edx, edx; Tag
0x14004e776  mov     rcx, rdi; P
0x14004e779  call    cs:__imp_ExFreePoolWithTag
0x14004e780  nop     dword ptr [rax+rax+00h]
0x14004e785  test    ebx, ebx
0x14004e787  jns     short loc_14004E7A7
0x14004e789  mov     rcx, [rsi+8]; P
0x14004e78d  test    rcx, rcx
0x14004e790  jz      short loc_14004E7A0
0x14004e792  xor     edx, edx; Tag
0x14004e794  call    cs:__imp_ExFreePoolWithTag
0x14004e79b  nop     dword ptr [rax+rax+00h]
0x14004e7a0  xorps   xmm0, xmm0
0x14004e7a3  movdqu  xmmword ptr [rsi], xmm0
0x14004e7a7  mov     eax, ebx
0x14004e7a9  add     rsp, 0C0h
0x14004e7b0  pop     r15
0x14004e7b2  pop     r14
0x14004e7b4  pop     rdi
0x14004e7b5  pop     rsi
0x14004e7b6  pop     rbx
0x14004e7b7  retn
0x1400807a3  push    rbx
0x1400807a5  push    rbp
0x1400807a6  sub     rsp, 38h
0x1400807aa  mov     rbp, rdx
0x1400807ad  mov     rcx, [rbp+100h]; Handle
0x1400807b4  test    rcx, rcx
0x1400807b7  jz      short loc_1400807D0
0x1400807b9  call    cs:__imp_ZwClose
0x1400807c0  nop     dword ptr [rax+rax+00h]
0x1400807c5  mov     qword ptr [rbp+100h], 0
0x1400807d0  mov     rcx, [rbp+38h]; P
0x1400807d4  test    rcx, rcx
0x1400807d7  jz      short loc_1400807EF
0x1400807d9  xor     edx, edx; Tag
0x1400807db  call    cs:__imp_ExFreePoolWithTag
0x1400807e2  nop     dword ptr [rax+rax+00h]
0x1400807e7  mov     qword ptr [rbp+38h], 0
0x1400807ef  cmp     dword ptr [rbp+30h], 0
0x1400807f3  jge     short loc_14008081D
0x1400807f5  mov     rbx, [rbp+0F0h]
0x1400807fc  cmp     qword ptr [rbx+8], 0
0x140080801  jz      short loc_140080816
0x140080803  xor     edx, edx; Tag
0x140080805  mov     rcx, [rbx+8]; P
0x140080809  call    cs:__imp_ExFreePoolWithTag
0x140080810  nop     dword ptr [rax+rax+00h]
0x140080815  nop
0x140080816  xorps   xmm0, xmm0
0x140080819  movdqu  xmmword ptr [rbx], xmm0
0x14008081d  add     rsp, 38h
0x140080821  pop     rbp
0x140080822  pop     rbx
0x140080823  retn
```
