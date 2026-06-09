# DpiGdoSetupGdiParameters

- ea: `0x1402c0708`
- end: `0x1402c0d79`
- name: `DpiGdoSetupGdiParameters`
- size: `1649`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1402bfe28`

## callees

- `0x14004cf48`
- `0x1400a0100`
- `0x1402b0f08`
- `0x1402b10b4`
- `0x1402c0234`
- `0x1402c0708`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1402c0b17`
- `ntoskrnl!ExAllocatePool2` at `0x1402c0b17`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c0cff`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c0d0f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c0d4c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c0cff`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c0d0f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c0d4c`
- `ntoskrnl!ZwClose` at `0x1402c0cee`
- `ntoskrnl!ZwClose` at `0x1402c0d25`
- `ntoskrnl!ZwClose` at `0x1402c0d3b`
- `ntoskrnl!ZwClose` at `0x1402c0cee`
- `ntoskrnl!ZwClose` at `0x1402c0d25`
- `ntoskrnl!ZwClose` at `0x1402c0d3b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402c08db`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402c0983`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402c0a86`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402c08db`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402c0983`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402c0a86`
- `ntoskrnl!ZwOpenKey` at `0x1402c09c4`
- `ntoskrnl!ZwOpenKey` at `0x1402c09c4`
- `ntoskrnl!ZwDeleteKey` at `0x1402c09d9`
- `ntoskrnl!ZwDeleteKey` at `0x1402c09d9`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1402c0b97`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1402c0bd9`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1402c0b97`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1402c0bd9`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1402c0929`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1402c0cb3`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1402c0929`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1402c0cb3`
- `ntoskrnl!ZwCreateKey` at `0x1402c086a`
- `ntoskrnl!ZwCreateKey` at `0x1402c0a27`
- `ntoskrnl!ZwCreateKey` at `0x1402c0c55`
- `ntoskrnl!ZwCreateKey` at `0x1402c086a`
- `ntoskrnl!ZwCreateKey` at `0x1402c0a27`
- `ntoskrnl!ZwCreateKey` at `0x1402c0c55`
- `ntoskrnl!ZwSetValueKey` at `0x1402c0abb`
- `ntoskrnl!ZwSetValueKey` at `0x1402c0abb`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1402c0b58`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1402c0b58`
- `watchdog!WdLogSingleEntry1` at `0x1402c07ee`
- `watchdog!WdLogSingleEntry1` at `0x1402c0885`
- `watchdog!WdLogSingleEntry1` at `0x1402c0948`
- `watchdog!WdLogSingleEntry1` at `0x1402c09ee`
- `watchdog!WdLogSingleEntry1` at `0x1402c0a4e`
- `watchdog!WdLogSingleEntry1` at `0x1402c0ada`
- `watchdog!WdLogSingleEntry1` at `0x1402c0b33`
- `watchdog!WdLogSingleEntry1` at `0x1402c0b73`
- `watchdog!WdLogSingleEntry1` at `0x1402c0bb2`
- `watchdog!WdLogSingleEntry1` at `0x1402c0bf4`
- `watchdog!WdLogSingleEntry1` at `0x1402c0c70`
- `watchdog!WdLogSingleEntry1` at `0x1402c0cce`
- `watchdog!WdLogSingleEntry1` at `0x1402c07ee`
- `watchdog!WdLogSingleEntry1` at `0x1402c0885`
- `watchdog!WdLogSingleEntry1` at `0x1402c0948`
- `watchdog!WdLogSingleEntry1` at `0x1402c09ee`
- `watchdog!WdLogSingleEntry1` at `0x1402c0a4e`
- `watchdog!WdLogSingleEntry1` at `0x1402c0ada`
- `watchdog!WdLogSingleEntry1` at `0x1402c0b33`
- `watchdog!WdLogSingleEntry1` at `0x1402c0b73`
- `watchdog!WdLogSingleEntry1` at `0x1402c0bb2`
- `watchdog!WdLogSingleEntry1` at `0x1402c0bf4`
- `watchdog!WdLogSingleEntry1` at `0x1402c0c70`
- `watchdog!WdLogSingleEntry1` at `0x1402c0cce`

## string_xrefs

- `0x1402c0812`: `\Registry\Machine\System\CurrentControlSet\Control\Video\`
- `0x1402c0a77`: `SymbolicLinkValue`

## pseudocode

```c
__int64 __fastcall DpiGdoSetupGdiParameters(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // rsi
  __int64 v6; // rdi
  NTSTATUS ServiceEntry; // ebx
  int appended; // eax
  ULONG Disposition; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v11; // [rsp+48h] [rbp-B8h] BYREF
  void *KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING Source; // [rsp+68h] [rbp-98h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  PVOID ValueData[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-40h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+D0h] [rbp-30h] BYREF
  struct _OBJECT_ATTRIBUTES v20; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR SourceString[4]; // [rsp+110h] [rbp+10h] BYREF
  int v22; // [rsp+118h] [rbp+18h]
  __int16 v23; // [rsp+11Ch] [rbp+1Ch]

  v3 = *(_QWORD *)(a1 + 64);
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  KeyHandle = 0;
  *(_QWORD *)SourceString = 0;
  v22 = 0;
  Source = 0;
  v23 = 0;
  v11 = 0;
  DestinationString = 0;
  Disposition = 0;
  *(_OWORD *)ValueData = 0;
  Handle = 0;
  Destination = 0;
  memset(&v20, 0, sizeof(v20));
  v6 = *(_QWORD *)(*(_QWORD *)(v3 + 32) + 64LL);
  if ( *(_BYTE *)(v6 + 2847) )
  {
    ServiceEntry = 0;
    goto LABEL_40;
  }
  if ( *(_BYTE *)(v6 + 480) )
  {
    appended = DpiCopyUnicodeString(&Source, (PCUNICODE_STRING)(*(_QWORD *)(v6 + 40) + 40LL));
  }
  else
  {
    if ( ((*(_QWORD *)(*(_QWORD *)(v6 + 24) + 64LL) + 4896LL)
        & ((unsigned __int128)-(__int128)*(unsigned __int64 *)(*(_QWORD *)(*(_QWORD *)(v6 + 24) + 64LL) + 4904LL) >> 64)) == 0 )
    {
      ServiceEntry = -1073741823;
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 1774;
      goto LABEL_38;
    }
    appended = DpiAppendStringToString(
                 L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Video\\",
                 *(unsigned __int16 **)(((*(_QWORD *)(*(_QWORD *)(v6 + 24) + 64LL) + 4896LL)
                                       & ((unsigned __int128)-(__int128)*(unsigned __int64 *)(*(_QWORD *)(*(_QWORD *)(v6 + 24) + 64LL)
                                                                                            + 4904LL) >> 64))
                                      + 8),
                 &Source);
  }
  ServiceEntry = appended;
  if ( appended >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 704;
    ObjectAttributes.ObjectName = &Source;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ServiceEntry = ZwCreateKey(&KeyHandle, 0xCu, &ObjectAttributes, 0, 0, 0, 0);
    if ( ServiceEntry < 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 1814;
      goto LABEL_38;
    }
    ServiceEntry = DpiGdoCreateServiceEntry(*(_QWORD *)(v6 + 40) + 40LL, KeyHandle);
    if ( ServiceEntry >= 0 )
    {
      if ( *(_BYTE *)(v6 + 480) )
      {
        SourceString[0] = 0;
        RtlInitUnicodeString(&DestinationString, SourceString);
        goto LABEL_14;
      }
      RtlStringCbPrintfW(SourceString, 0xEu, L"\\%04d", a3);
      RtlInitUnicodeString(&DestinationString, &SourceString[1]);
      ObjectAttributes.RootDirectory = KeyHandle;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( ZwOpenKey(&v11, 0xF003Fu, &ObjectAttributes) >= 0 && ZwDeleteKey(v11) < 0 )
      {
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 1880;
      }
      ServiceEntry = ZwCreateKey(&v11, 0x20u, &ObjectAttributes, 0, 0, 3u, &Disposition);
      if ( ServiceEntry < 0 )
      {
        if ( ServiceEntry != -1073741771 )
        {
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 1903;
          goto LABEL_38;
        }
LABEL_14:
        ServiceEntry = DpiAppendStringToString(Source.Buffer, SourceString, (PUNICODE_STRING)ValueData);
        if ( ServiceEntry >= 0 )
        {
          ServiceEntry = RtlWriteRegistryValue(4u, L"VIDEO", *(PCWSTR *)(a2 + 8), 1u, ValueData[1], WORD1(ValueData[0]));
          if ( ServiceEntry >= 0 )
          {
            Destination.Length = 0;
            Destination.MaximumLength = Source.Length + 52;
            Destination.Buffer = (wchar_t *)ExAllocatePool2(256, (unsigned __int16)(Source.Length + 52), 1953656900);
            if ( Destination.Buffer )
            {
              ServiceEntry = RtlAppendUnicodeStringToString(&Destination, &Source);
              if ( ServiceEntry >= 0 )
              {
                ServiceEntry = RtlAppendUnicodeToString(&Destination, SourceString);
                if ( ServiceEntry >= 0 )
                {
                  ServiceEntry = RtlAppendUnicodeToString(&Destination, L"\\VolatileSettings");
                  if ( ServiceEntry >= 0 )
                  {
                    v20.ObjectName = &Destination;
                    v20.Length = 48;
                    v20.RootDirectory = 0;
                    *(_OWORD *)&v20.SecurityDescriptor = 0;
                    v20.Attributes = 576;
                    ServiceEntry = ZwCreateKey(&Handle, 0xC0000000, &v20, 0, 0, 1u, 0);
                    if ( ServiceEntry >= 0 )
                    {
                      ServiceEntry = RtlWriteRegistryValue(
                                       0,
                                       Destination.Buffer,
                                       L"{5b45201d-f2f2-4f3b-85bb-30ff1f953599}",
                                       3u,
                                       *(PVOID *)(v3 + 168),
                                       *(unsigned __int16 *)(v3 + 160));
                      if ( ServiceEntry < 0 )
                      {
                        WdLogSingleEntry1(2);
                        WdLogGlobalForLineNumber = 2103;
                      }
                    }
                    else
                    {
                      WdLogSingleEntry1(2);
                      WdLogGlobalForLineNumber = 2082;
                    }
                  }
                  else
                  {
                    WdLogSingleEntry1(2);
                    WdLogGlobalForLineNumber = 2054;
                  }
                }
                else
                {
                  WdLogSingleEntry1(2);
                  WdLogGlobalForLineNumber = 2037;
                }
              }
              else
              {
                WdLogSingleEntry1(2);
                WdLogGlobalForLineNumber = 2020;
              }
            }
            else
            {
              WdLogSingleEntry1(2);
              WdLogGlobalForLineNumber = 2003;
            }
          }
          else
          {
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 1974;
          }
        }
        goto LABEL_38;
      }
      if ( Disposition != 1 )
        goto LABEL_14;
      ValueName = 0;
      RtlInitUnicodeString(&ValueName, L"SymbolicLinkValue");
      ServiceEntry = ZwSetValueKey(v11, &ValueName, 0, 6u, *(PVOID *)(v6 + 536), *(unsigned __int16 *)(v6 + 528));
      if ( ServiceEntry >= 0 )
        goto LABEL_14;
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 1933;
    }
  }
LABEL_38:
  if ( Handle )
    ZwClose(Handle);
LABEL_40:
  RtlFreeUnicodeString(&Destination);
  RtlFreeUnicodeString((PUNICODE_STRING)ValueData);
  if ( v11 )
    ZwClose(v11);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  RtlFreeUnicodeString(&Source);
  return (unsigned int)ServiceEntry;
}

```

## disassembly

```asm
0x1402c0708  push    rbp
0x1402c070a  push    rbx
0x1402c070b  push    rsi
0x1402c070c  push    rdi
0x1402c070d  push    r12
0x1402c070f  push    r14
0x1402c0711  push    r15
0x1402c0713  lea     rbp, [rsp-30h]
0x1402c0718  sub     rsp, 130h
0x1402c071f  mov     rax, cs:__security_cookie
0x1402c0726  xor     rax, rsp
0x1402c0729  mov     [rbp+60h+var_40], rax
0x1402c072d  mov     rsi, [rcx+40h]
0x1402c0731  xorps   xmm0, xmm0
0x1402c0734  xor     r12d, r12d
0x1402c0737  xor     eax, eax
0x1402c0739  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x1402c073d  mov     [rsp+160h+KeyHandle], r12
0x1402c0742  mov     r14d, r8d
0x1402c0745  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x1402c0749  mov     qword ptr [rbp+60h+SourceString], rax
0x1402c074d  mov     r15, rdx
0x1402c0750  movups  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402c0754  mov     [rbp+60h+var_48], eax
0x1402c0757  movups  xmmword ptr [rsp+160h+Source.Length], xmm0
0x1402c075c  mov     [rbp+60h+var_44], ax
0x1402c0760  mov     [rsp+160h+var_118], r12
0x1402c0765  xorps   xmm1, xmm1
0x1402c0768  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x1402c076c  mov     [rsp+160h+var_120], r12d
0x1402c0771  movups  xmmword ptr [rbp+60h+ValueData], xmm0
0x1402c0775  mov     [rsp+160h+Handle], r12
0x1402c077a  movups  xmmword ptr [rsp+160h+Destination.Length], xmm1
0x1402c077f  movups  xmmword ptr [rbp+60h+var_80.Length], xmm0
0x1402c0783  movups  xmmword ptr [rbp+60h+var_80.ObjectName], xmm0
0x1402c0787  movups  xmmword ptr [rbp+60h+var_80.SecurityDescriptor], xmm0
0x1402c078b  mov     rax, [rsi+20h]
0x1402c078f  mov     rdi, [rax+40h]
0x1402c0793  cmp     [rdi+0B1Fh], r12b
0x1402c079a  jz      short loc_1402C07A4
0x1402c079c  mov     ebx, r12d
0x1402c079f  jmp     loc_1402C0CFA
0x1402c07a4  cmp     [rdi+1E0h], r12b
0x1402c07ab  jz      short loc_1402C07C1
0x1402c07ad  mov     rdx, [rdi+28h]
0x1402c07b1  lea     rcx, [rsp+160h+Source]; DestinationString
0x1402c07b6  add     rdx, 28h ; '('; SourceString
0x1402c07ba  call    DpiCopyUnicodeString
0x1402c07bf  jmp     short loc_1402C081E
0x1402c07c1  mov     rax, [rdi+18h]
0x1402c07c5  mov     rcx, [rax+40h]
0x1402c07c9  add     rcx, 1320h
0x1402c07d0  mov     rax, [rcx+8]
0x1402c07d4  neg     rax
0x1402c07d7  sbb     rdx, rdx
0x1402c07da  and     rdx, rcx
0x1402c07dd  jnz     short loc_1402C0809
0x1402c07df  mov     rbx, 0FFFFFFFFC0000001h
0x1402c07e6  mov     rdx, rbx
0x1402c07e9  mov     ecx, 2
0x1402c07ee  call    cs:__imp_WdLogSingleEntry1
0x1402c07f5  nop     dword ptr [rax+rax+00h]
0x1402c07fa  mov     cs:WdLogGlobalForLineNumber, 6EEh
0x1402c0804  jmp     loc_1402C0CE4
0x1402c0809  mov     rdx, [rdx+8]; unsigned __int16 *
0x1402c080d  lea     r8, [rsp+160h+Source]; UnicodeString
0x1402c0812  lea     rcx, aRegistryMachin_18; "\\Registry\\Machine\\System\\CurrentCon"...
0x1402c0819  call    DpiAppendStringToString
0x1402c081e  mov     ebx, eax
0x1402c0820  test    eax, eax
0x1402c0822  js      loc_1402C0CE4
0x1402c0828  xor     r9d, r9d; TitleIndex
0x1402c082b  mov     [rsp+160h+Disposition], r12; Disposition
0x1402c0830  lea     rax, [rsp+160h+Source]
0x1402c0835  mov     [rsp+160h+CreateOptions], r12d; CreateOptions
0x1402c083a  xorps   xmm0, xmm0
0x1402c083d  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x1402c0844  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x1402c0848  mov     [rbp+60h+ObjectAttributes.RootDirectory], r12
0x1402c084c  lea     edx, [r9+0Ch]; DesiredAccess
0x1402c0850  mov     [rbp+60h+ObjectAttributes.Attributes], 2C0h
0x1402c0857  lea     rcx, [rsp+160h+KeyHandle]; KeyHandle
0x1402c085c  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x1402c0860  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402c0865  mov     [rsp+160h+Class], r12; Class
0x1402c086a  call    cs:__imp_ZwCreateKey
0x1402c0871  nop     dword ptr [rax+rax+00h]
0x1402c0876  movsxd  rbx, eax
0x1402c0879  test    eax, eax
0x1402c087b  jns     short loc_1402C08A0
0x1402c087d  mov     rdx, rbx
0x1402c0880  mov     ecx, 2
0x1402c0885  call    cs:__imp_WdLogSingleEntry1
0x1402c088c  nop     dword ptr [rax+rax+00h]
0x1402c0891  mov     cs:WdLogGlobalForLineNumber, 716h
0x1402c089b  jmp     loc_1402C0CE4
0x1402c08a0  mov     rcx, [rdi+28h]
0x1402c08a4  mov     rdx, [rsp+160h+KeyHandle]
0x1402c08a9  add     rcx, 28h ; '('
0x1402c08ad  call    DpiGdoCreateServiceEntry
0x1402c08b2  mov     ebx, eax
0x1402c08b4  test    eax, eax
0x1402c08b6  js      loc_1402C0CE4
0x1402c08bc  mov     ebx, 3
0x1402c08c1  cmp     [rdi+1E0h], r12b
0x1402c08c8  jz      loc_1402C0963
0x1402c08ce  lea     rdx, [rbp+60h+SourceString]; SourceString
0x1402c08d2  mov     [rbp+60h+SourceString], r12w
0x1402c08d7  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x1402c08db  call    cs:__imp_RtlInitUnicodeString
0x1402c08e2  nop     dword ptr [rax+rax+00h]
0x1402c08e7  mov     rcx, [rsp+160h+Source.Buffer]; Source
0x1402c08ec  lea     r8, [rbp+60h+ValueData]; UnicodeString
0x1402c08f0  lea     rdx, [rbp+60h+SourceString]; unsigned __int16 *
0x1402c08f4  call    DpiAppendStringToString
0x1402c08f9  mov     ebx, eax
0x1402c08fb  test    eax, eax
0x1402c08fd  js      loc_1402C0CE4
0x1402c0903  movzx   eax, word ptr [rbp+60h+ValueData+2]
0x1402c0907  lea     rdx, aVideo; "VIDEO"
0x1402c090e  mov     r8, [r15+8]; ValueName
0x1402c0912  mov     r9d, 1; ValueType
0x1402c0918  mov     [rsp+160h+CreateOptions], eax; ValueLength
0x1402c091c  mov     rax, [rbp+60h+ValueData+8]
0x1402c0920  mov     [rsp+160h+Class], rax; ValueData
0x1402c0925  lea     ecx, [r9+3]; RelativeTo
0x1402c0929  call    cs:__imp_RtlWriteRegistryValue
0x1402c0930  nop     dword ptr [rax+rax+00h]
0x1402c0935  movsxd  rbx, eax
0x1402c0938  test    eax, eax
0x1402c093a  jns     loc_1402C0AF5
0x1402c0940  mov     rdx, rbx
0x1402c0943  mov     ecx, 2
0x1402c0948  call    cs:__imp_WdLogSingleEntry1
0x1402c094f  nop     dword ptr [rax+rax+00h]
0x1402c0954  mov     cs:WdLogGlobalForLineNumber, 7B6h
0x1402c095e  jmp     loc_1402C0CE4
0x1402c0963  mov     r9d, r14d
0x1402c0966  lea     r8, a04d; "\\%04d"
0x1402c096d  mov     edx, 0Eh; unsigned __int64
0x1402c0972  lea     rcx, [rbp+60h+SourceString]; unsigned __int16 *
0x1402c0976  call    ?RtlStringCbPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1402c097b  lea     rdx, [rbp+60h+SourceString+2]; SourceString
0x1402c097f  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x1402c0983  call    cs:__imp_RtlInitUnicodeString
0x1402c098a  nop     dword ptr [rax+rax+00h]
0x1402c098f  mov     rax, [rsp+160h+KeyHandle]
0x1402c0994  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x1402c0998  mov     [rbp+60h+ObjectAttributes.RootDirectory], rax
0x1402c099c  lea     rcx, [rsp+160h+var_118]; KeyHandle
0x1402c09a1  lea     rax, [rbp+60h+DestinationString]
0x1402c09a5  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x1402c09ac  xorps   xmm0, xmm0
0x1402c09af  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x1402c09b3  mov     edx, 0F003Fh; DesiredAccess
0x1402c09b8  mov     [rbp+60h+ObjectAttributes.Attributes], 240h
0x1402c09bf  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402c09c4  call    cs:__imp_ZwOpenKey
0x1402c09cb  nop     dword ptr [rax+rax+00h]
0x1402c09d0  test    eax, eax
0x1402c09d2  js      short loc_1402C0A04
0x1402c09d4  mov     rcx, [rsp+160h+var_118]; KeyHandle
0x1402c09d9  call    cs:__imp_ZwDeleteKey
0x1402c09e0  nop     dword ptr [rax+rax+00h]
0x1402c09e5  test    eax, eax
0x1402c09e7  jns     short loc_1402C0A04
0x1402c09e9  movsxd  rdx, eax
0x1402c09ec  mov     ecx, ebx
0x1402c09ee  call    cs:__imp_WdLogSingleEntry1
0x1402c09f5  nop     dword ptr [rax+rax+00h]
0x1402c09fa  mov     cs:WdLogGlobalForLineNumber, 758h
0x1402c0a04  xor     r9d, r9d; TitleIndex
0x1402c0a07  lea     rax, [rsp+160h+var_120]
0x1402c0a0c  mov     [rsp+160h+Disposition], rax; Disposition
0x1402c0a11  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x1402c0a15  mov     [rsp+160h+CreateOptions], ebx; CreateOptions
0x1402c0a19  lea     rcx, [rsp+160h+var_118]; KeyHandle
0x1402c0a1e  mov     [rsp+160h+Class], r12; Class
0x1402c0a23  lea     edx, [r9+20h]; DesiredAccess
0x1402c0a27  call    cs:__imp_ZwCreateKey
0x1402c0a2e  nop     dword ptr [rax+rax+00h]
0x1402c0a33  movsxd  rbx, eax
0x1402c0a36  test    eax, eax
0x1402c0a38  jns     short loc_1402C0A69
0x1402c0a3a  cmp     ebx, 0C0000035h
0x1402c0a40  jz      loc_1402C08E7
0x1402c0a46  mov     rdx, rbx
0x1402c0a49  mov     ecx, 2
0x1402c0a4e  call    cs:__imp_WdLogSingleEntry1
0x1402c0a55  nop     dword ptr [rax+rax+00h]
0x1402c0a5a  mov     cs:WdLogGlobalForLineNumber, 76Fh
0x1402c0a64  jmp     loc_1402C0CE4
0x1402c0a69  cmp     [rsp+160h+var_120], 1
0x1402c0a6e  jnz     loc_1402C08E7
0x1402c0a74  xorps   xmm0, xmm0
0x1402c0a77  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x1402c0a7e  lea     rcx, [rbp+60h+ValueName]; DestinationString
0x1402c0a82  movups  xmmword ptr [rbp+60h+ValueName.Length], xmm0
0x1402c0a86  call    cs:__imp_RtlInitUnicodeString
0x1402c0a8d  nop     dword ptr [rax+rax+00h]
0x1402c0a92  movzx   eax, word ptr [rdi+210h]
0x1402c0a99  lea     rdx, [rbp+60h+ValueName]; ValueName
0x1402c0a9d  mov     rcx, [rsp+160h+var_118]; KeyHandle
0x1402c0aa2  mov     r9d, 6; Type
0x1402c0aa8  mov     [rsp+160h+CreateOptions], eax; DataSize
0x1402c0aac  xor     r8d, r8d; TitleIndex
0x1402c0aaf  mov     rax, [rdi+218h]
0x1402c0ab6  mov     [rsp+160h+Class], rax; Data
0x1402c0abb  call    cs:__imp_ZwSetValueKey
0x1402c0ac2  nop     dword ptr [rax+rax+00h]
0x1402c0ac7  movsxd  rbx, eax
0x1402c0aca  test    eax, eax
0x1402c0acc  jns     loc_1402C08E7
0x1402c0ad2  mov     rdx, rbx
0x1402c0ad5  mov     ecx, 2
0x1402c0ada  call    cs:__imp_WdLogSingleEntry1
0x1402c0ae1  nop     dword ptr [rax+rax+00h]
0x1402c0ae6  mov     cs:WdLogGlobalForLineNumber, 78Dh
0x1402c0af0  jmp     loc_1402C0CE4
0x1402c0af5  movzx   eax, [rsp+160h+Source.Length]
0x1402c0afa  mov     ecx, 100h
0x1402c0aff  add     ax, 34h ; '4'
0x1402c0b03  mov     [rsp+160h+Destination.Length], r12w
0x1402c0b09  movzx   edx, ax
0x1402c0b0c  mov     r8d, 74727044h
0x1402c0b12  mov     [rsp+160h+Destination.MaximumLength], dx
0x1402c0b17  call    cs:__imp_ExAllocatePool2
0x1402c0b1e  nop     dword ptr [rax+rax+00h]
0x1402c0b23  mov     [rsp+160h+Destination.Buffer], rax
0x1402c0b28  test    rax, rax
0x1402c0b2b  jnz     short loc_1402C0B4E
0x1402c0b2d  mov     rdx, rbx
0x1402c0b30  lea     ecx, [rax+2]
0x1402c0b33  call    cs:__imp_WdLogSingleEntry1
0x1402c0b3a  nop     dword ptr [rax+rax+00h]
0x1402c0b3f  mov     cs:WdLogGlobalForLineNumber, 7D3h
0x1402c0b49  jmp     loc_1402C0CE4
0x1402c0b4e  lea     rdx, [rsp+160h+Source]; Source
0x1402c0b53  lea     rcx, [rsp+160h+Destination]; Destination
0x1402c0b58  call    cs:__imp_RtlAppendUnicodeStringToString
0x1402c0b5f  nop     dword ptr [rax+rax+00h]
0x1402c0b64  movsxd  rbx, eax
0x1402c0b67  test    eax, eax
0x1402c0b69  jns     short loc_1402C0B8E
0x1402c0b6b  mov     rdx, rbx
0x1402c0b6e  mov     ecx, 2
0x1402c0b73  call    cs:__imp_WdLogSingleEntry1
0x1402c0b7a  nop     dword ptr [rax+rax+00h]
0x1402c0b7f  mov     cs:WdLogGlobalForLineNumber, 7E4h
0x1402c0b89  jmp     loc_1402C0CE4
0x1402c0b8e  lea     rdx, [rbp+60h+SourceString]; Source
0x1402c0b92  lea     rcx, [rsp+160h+Destination]; Destination
0x1402c0b97  call    cs:__imp_RtlAppendUnicodeToString
0x1402c0b9e  nop     dword ptr [rax+rax+00h]
0x1402c0ba3  movsxd  rbx, eax
0x1402c0ba6  test    eax, eax
0x1402c0ba8  jns     short loc_1402C0BCD
0x1402c0baa  mov     rdx, rbx
0x1402c0bad  mov     ecx, 2
0x1402c0bb2  call    cs:__imp_WdLogSingleEntry1
0x1402c0bb9  nop     dword ptr [rax+rax+00h]
0x1402c0bbe  mov     cs:WdLogGlobalForLineNumber, 7F5h
0x1402c0bc8  jmp     loc_1402C0CE4
0x1402c0bcd  lea     rdx, aVolatilesettin; "\\VolatileSettings"
0x1402c0bd4  lea     rcx, [rsp+160h+Destination]; Destination
0x1402c0bd9  call    cs:__imp_RtlAppendUnicodeToString
0x1402c0be0  nop     dword ptr [rax+rax+00h]
0x1402c0be5  movsxd  rbx, eax
0x1402c0be8  test    eax, eax
0x1402c0bea  jns     short loc_1402C0C0F
0x1402c0bec  mov     rdx, rbx
0x1402c0bef  mov     ecx, 2
0x1402c0bf4  call    cs:__imp_WdLogSingleEntry1
0x1402c0bfb  nop     dword ptr [rax+rax+00h]
0x1402c0c00  mov     cs:WdLogGlobalForLineNumber, 806h
0x1402c0c0a  jmp     loc_1402C0CE4
0x1402c0c0f  lea     rax, [rsp+160h+Destination]
0x1402c0c14  mov     [rsp+160h+Disposition], r12; Disposition
0x1402c0c19  xorps   xmm0, xmm0
0x1402c0c1c  mov     [rsp+160h+CreateOptions], 1; CreateOptions
0x1402c0c24  xor     r9d, r9d; TitleIndex
0x1402c0c27  mov     [rbp+60h+var_80.ObjectName], rax
0x1402c0c2b  lea     r8, [rbp+60h+var_80]; ObjectAttributes
0x1402c0c2f  mov     [rsp+160h+Class], r12; Class
0x1402c0c34  mov     edx, 0C0000000h; DesiredAccess
0x1402c0c39  mov     [rbp+60h+var_80.Length], 30h ; '0'
0x1402c0c40  lea     rcx, [rsp+160h+Handle]; KeyHandle
0x1402c0c45  mov     [rbp+60h+var_80.RootDirectory], r12
0x1402c0c49  movdqu  xmmword ptr [rbp+60h+var_80.SecurityDescriptor], xmm0
0x1402c0c4e  mov     [rbp+60h+var_80.Attributes], 240h
0x1402c0c55  call    cs:__imp_ZwCreateKey
0x1402c0c5c  nop     dword ptr [rax+rax+00h]
0x1402c0c61  movsxd  rbx, eax
0x1402c0c64  test    eax, eax
0x1402c0c66  jns     short loc_1402C0C88
0x1402c0c68  mov     rdx, rbx
0x1402c0c6b  mov     ecx, 2
0x1402c0c70  call    cs:__imp_WdLogSingleEntry1
0x1402c0c77  nop     dword ptr [rax+rax+00h]
0x1402c0c7c  mov     cs:WdLogGlobalForLineNumber, 822h
  ... truncated ...
```
