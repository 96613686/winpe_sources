# DpiGdoSetupGdiParameters

- ea: `0x1402c7158`
- end: `0x1402c77c9`
- name: `DpiGdoSetupGdiParameters`
- size: `1649`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1402c6878`

## callees

- `0x14004d148`
- `0x1400a0bd0`
- `0x1402b78b8`
- `0x1402b7a64`
- `0x1402c6c84`
- `0x1402c7158`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1402c7567`
- `ntoskrnl!ExAllocatePool2` at `0x1402c7567`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c774f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c775f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c779c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c774f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c775f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c779c`
- `ntoskrnl!ZwClose` at `0x1402c773e`
- `ntoskrnl!ZwClose` at `0x1402c7775`
- `ntoskrnl!ZwClose` at `0x1402c778b`
- `ntoskrnl!ZwClose` at `0x1402c773e`
- `ntoskrnl!ZwClose` at `0x1402c7775`
- `ntoskrnl!ZwClose` at `0x1402c778b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402c732b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402c73d3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402c74d6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402c732b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402c73d3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402c74d6`
- `ntoskrnl!ZwOpenKey` at `0x1402c7414`
- `ntoskrnl!ZwOpenKey` at `0x1402c7414`
- `ntoskrnl!ZwDeleteKey` at `0x1402c7429`
- `ntoskrnl!ZwDeleteKey` at `0x1402c7429`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1402c75e7`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1402c7629`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1402c75e7`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1402c7629`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1402c7379`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1402c7703`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1402c7379`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1402c7703`
- `ntoskrnl!ZwCreateKey` at `0x1402c72ba`
- `ntoskrnl!ZwCreateKey` at `0x1402c7477`
- `ntoskrnl!ZwCreateKey` at `0x1402c76a5`
- `ntoskrnl!ZwCreateKey` at `0x1402c72ba`
- `ntoskrnl!ZwCreateKey` at `0x1402c7477`
- `ntoskrnl!ZwCreateKey` at `0x1402c76a5`
- `ntoskrnl!ZwSetValueKey` at `0x1402c750b`
- `ntoskrnl!ZwSetValueKey` at `0x1402c750b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1402c75a8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1402c75a8`
- `watchdog!WdLogSingleEntry1` at `0x1402c723e`
- `watchdog!WdLogSingleEntry1` at `0x1402c72d5`
- `watchdog!WdLogSingleEntry1` at `0x1402c7398`
- `watchdog!WdLogSingleEntry1` at `0x1402c743e`
- `watchdog!WdLogSingleEntry1` at `0x1402c749e`
- `watchdog!WdLogSingleEntry1` at `0x1402c752a`
- `watchdog!WdLogSingleEntry1` at `0x1402c7583`
- `watchdog!WdLogSingleEntry1` at `0x1402c75c3`
- `watchdog!WdLogSingleEntry1` at `0x1402c7602`
- `watchdog!WdLogSingleEntry1` at `0x1402c7644`
- `watchdog!WdLogSingleEntry1` at `0x1402c76c0`
- `watchdog!WdLogSingleEntry1` at `0x1402c771e`
- `watchdog!WdLogSingleEntry1` at `0x1402c723e`
- `watchdog!WdLogSingleEntry1` at `0x1402c72d5`
- `watchdog!WdLogSingleEntry1` at `0x1402c7398`
- `watchdog!WdLogSingleEntry1` at `0x1402c743e`
- `watchdog!WdLogSingleEntry1` at `0x1402c749e`
- `watchdog!WdLogSingleEntry1` at `0x1402c752a`
- `watchdog!WdLogSingleEntry1` at `0x1402c7583`
- `watchdog!WdLogSingleEntry1` at `0x1402c75c3`
- `watchdog!WdLogSingleEntry1` at `0x1402c7602`
- `watchdog!WdLogSingleEntry1` at `0x1402c7644`
- `watchdog!WdLogSingleEntry1` at `0x1402c76c0`
- `watchdog!WdLogSingleEntry1` at `0x1402c771e`

## string_xrefs

- `0x1402c7262`: `\Registry\Machine\System\CurrentControlSet\Control\Video\`
- `0x1402c74c7`: `SymbolicLinkValue`

## pseudocode

```c
__int64 __fastcall DpiGdoSetupGdiParameters(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // rsi
  __int64 v6; // rdi
  __int64 v7; // rbx
  int appended; // eax
  NTSTATUS v9; // eax
  NTSTATUS v10; // eax
  NTSTATUS v11; // eax
  NTSTATUS v12; // eax
  NTSTATUS v13; // eax
  NTSTATUS v14; // eax
  NTSTATUS v15; // eax
  NTSTATUS v16; // eax
  NTSTATUS v17; // eax
  NTSTATUS v18; // eax
  ULONG Disposition; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v21; // [rsp+48h] [rbp-B8h] BYREF
  void *KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING Source; // [rsp+68h] [rbp-98h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  PVOID ValueData[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-40h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+D0h] [rbp-30h] BYREF
  struct _OBJECT_ATTRIBUTES v30; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR SourceString[4]; // [rsp+110h] [rbp+10h] BYREF
  int v32; // [rsp+118h] [rbp+18h]
  __int16 v33; // [rsp+11Ch] [rbp+1Ch]

  v3 = *(_QWORD *)(a1 + 64);
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  KeyHandle = 0;
  *(_QWORD *)SourceString = 0;
  v32 = 0;
  Source = 0;
  v33 = 0;
  v21 = 0;
  DestinationString = 0;
  Disposition = 0;
  *(_OWORD *)ValueData = 0;
  Handle = 0;
  Destination = 0;
  memset(&v30, 0, sizeof(v30));
  v6 = *(_QWORD *)(*(_QWORD *)(v3 + 32) + 64LL);
  if ( *(_BYTE *)(v6 + 2847) )
  {
    LODWORD(v7) = 0;
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
      LODWORD(v7) = -1073741823;
      WdLogSingleEntry1(2, -1073741823);
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
  LODWORD(v7) = appended;
  if ( appended >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 704;
    ObjectAttributes.ObjectName = &Source;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v9 = ZwCreateKey(&KeyHandle, 0xCu, &ObjectAttributes, 0, 0, 0, 0);
    LODWORD(v7) = v9;
    if ( v9 < 0 )
    {
      WdLogSingleEntry1(2, v9);
      WdLogGlobalForLineNumber = 1814;
      goto LABEL_38;
    }
    LODWORD(v7) = DpiGdoCreateServiceEntry(*(_QWORD *)(v6 + 40) + 40LL, KeyHandle);
    if ( (int)v7 >= 0 )
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
      if ( ZwOpenKey(&v21, 0xF003Fu, &ObjectAttributes) >= 0 )
      {
        v11 = ZwDeleteKey(v21);
        if ( v11 < 0 )
        {
          WdLogSingleEntry1(3, v11);
          WdLogGlobalForLineNumber = 1880;
        }
      }
      v12 = ZwCreateKey(&v21, 0x20u, &ObjectAttributes, 0, 0, 3u, &Disposition);
      LODWORD(v7) = v12;
      if ( v12 < 0 )
      {
        if ( v12 != -1073741771 )
        {
          WdLogSingleEntry1(2, v12);
          WdLogGlobalForLineNumber = 1903;
          goto LABEL_38;
        }
LABEL_14:
        LODWORD(v7) = DpiAppendStringToString(Source.Buffer, SourceString, (PUNICODE_STRING)ValueData);
        if ( (int)v7 >= 0 )
        {
          v10 = RtlWriteRegistryValue(4u, L"VIDEO", *(PCWSTR *)(a2 + 8), 1u, ValueData[1], WORD1(ValueData[0]));
          v7 = v10;
          if ( v10 >= 0 )
          {
            Destination.Length = 0;
            Destination.MaximumLength = Source.Length + 52;
            Destination.Buffer = (wchar_t *)ExAllocatePool2(256, (unsigned __int16)(Source.Length + 52), 1953656900);
            if ( Destination.Buffer )
            {
              v14 = RtlAppendUnicodeStringToString(&Destination, &Source);
              LODWORD(v7) = v14;
              if ( v14 >= 0 )
              {
                v15 = RtlAppendUnicodeToString(&Destination, SourceString);
                LODWORD(v7) = v15;
                if ( v15 >= 0 )
                {
                  v16 = RtlAppendUnicodeToString(&Destination, L"\\VolatileSettings");
                  LODWORD(v7) = v16;
                  if ( v16 >= 0 )
                  {
                    v30.ObjectName = &Destination;
                    v30.Length = 48;
                    v30.RootDirectory = 0;
                    *(_OWORD *)&v30.SecurityDescriptor = 0;
                    v30.Attributes = 576;
                    v17 = ZwCreateKey(&Handle, 0xC0000000, &v30, 0, 0, 1u, 0);
                    LODWORD(v7) = v17;
                    if ( v17 >= 0 )
                    {
                      v18 = RtlWriteRegistryValue(
                              0,
                              Destination.Buffer,
                              L"{5b45201d-f2f2-4f3b-85bb-30ff1f953599}",
                              3u,
                              *(PVOID *)(v3 + 168),
                              *(unsigned __int16 *)(v3 + 160));
                      LODWORD(v7) = v18;
                      if ( v18 < 0 )
                      {
                        WdLogSingleEntry1(2, v18);
                        WdLogGlobalForLineNumber = 2103;
                      }
                    }
                    else
                    {
                      WdLogSingleEntry1(2, v17);
                      WdLogGlobalForLineNumber = 2082;
                    }
                  }
                  else
                  {
                    WdLogSingleEntry1(2, v16);
                    WdLogGlobalForLineNumber = 2054;
                  }
                }
                else
                {
                  WdLogSingleEntry1(2, v15);
                  WdLogGlobalForLineNumber = 2037;
                }
              }
              else
              {
                WdLogSingleEntry1(2, v14);
                WdLogGlobalForLineNumber = 2020;
              }
            }
            else
            {
              WdLogSingleEntry1(2, v7);
              WdLogGlobalForLineNumber = 2003;
            }
          }
          else
          {
            WdLogSingleEntry1(2, v10);
            WdLogGlobalForLineNumber = 1974;
          }
        }
        goto LABEL_38;
      }
      if ( Disposition != 1 )
        goto LABEL_14;
      ValueName = 0;
      RtlInitUnicodeString(&ValueName, L"SymbolicLinkValue");
      v13 = ZwSetValueKey(v21, &ValueName, 0, 6u, *(PVOID *)(v6 + 536), *(unsigned __int16 *)(v6 + 528));
      LODWORD(v7) = v13;
      if ( v13 >= 0 )
        goto LABEL_14;
      WdLogSingleEntry1(2, v13);
      WdLogGlobalForLineNumber = 1933;
    }
  }
LABEL_38:
  if ( Handle )
    ZwClose(Handle);
LABEL_40:
  RtlFreeUnicodeString(&Destination);
  RtlFreeUnicodeString((PUNICODE_STRING)ValueData);
  if ( v21 )
    ZwClose(v21);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  RtlFreeUnicodeString(&Source);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1402c7158  push    rbp
0x1402c715a  push    rbx
0x1402c715b  push    rsi
0x1402c715c  push    rdi
0x1402c715d  push    r12
0x1402c715f  push    r14
0x1402c7161  push    r15
0x1402c7163  lea     rbp, [rsp-30h]
0x1402c7168  sub     rsp, 130h
0x1402c716f  mov     rax, cs:__security_cookie
0x1402c7176  xor     rax, rsp
0x1402c7179  mov     [rbp+60h+var_40], rax
0x1402c717d  mov     rsi, [rcx+40h]
0x1402c7181  xorps   xmm0, xmm0
0x1402c7184  xor     r12d, r12d
0x1402c7187  xor     eax, eax
0x1402c7189  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x1402c718d  mov     [rsp+160h+KeyHandle], r12
0x1402c7192  mov     r14d, r8d
0x1402c7195  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x1402c7199  mov     qword ptr [rbp+60h+SourceString], rax
0x1402c719d  mov     r15, rdx
0x1402c71a0  movups  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402c71a4  mov     [rbp+60h+var_48], eax
0x1402c71a7  movups  xmmword ptr [rsp+160h+Source.Length], xmm0
0x1402c71ac  mov     [rbp+60h+var_44], ax
0x1402c71b0  mov     [rsp+160h+var_118], r12
0x1402c71b5  xorps   xmm1, xmm1
0x1402c71b8  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x1402c71bc  mov     [rsp+160h+var_120], r12d
0x1402c71c1  movups  xmmword ptr [rbp+60h+ValueData], xmm0
0x1402c71c5  mov     [rsp+160h+Handle], r12
0x1402c71ca  movups  xmmword ptr [rsp+160h+Destination.Length], xmm1
0x1402c71cf  movups  xmmword ptr [rbp+60h+var_80.Length], xmm0
0x1402c71d3  movups  xmmword ptr [rbp+60h+var_80.ObjectName], xmm0
0x1402c71d7  movups  xmmword ptr [rbp+60h+var_80.SecurityDescriptor], xmm0
0x1402c71db  mov     rax, [rsi+20h]
0x1402c71df  mov     rdi, [rax+40h]
0x1402c71e3  cmp     [rdi+0B1Fh], r12b
0x1402c71ea  jz      short loc_1402C71F4
0x1402c71ec  mov     ebx, r12d
0x1402c71ef  jmp     loc_1402C774A
0x1402c71f4  cmp     [rdi+1E0h], r12b
0x1402c71fb  jz      short loc_1402C7211
0x1402c71fd  mov     rdx, [rdi+28h]
0x1402c7201  lea     rcx, [rsp+160h+Source]; DestinationString
0x1402c7206  add     rdx, 28h ; '('; SourceString
0x1402c720a  call    DpiCopyUnicodeString
0x1402c720f  jmp     short loc_1402C726E
0x1402c7211  mov     rax, [rdi+18h]
0x1402c7215  mov     rcx, [rax+40h]
0x1402c7219  add     rcx, 1320h
0x1402c7220  mov     rax, [rcx+8]
0x1402c7224  neg     rax
0x1402c7227  sbb     rdx, rdx
0x1402c722a  and     rdx, rcx
0x1402c722d  jnz     short loc_1402C7259
0x1402c722f  mov     rbx, 0FFFFFFFFC0000001h
0x1402c7236  mov     rdx, rbx
0x1402c7239  mov     ecx, 2
0x1402c723e  call    cs:__imp_WdLogSingleEntry1
0x1402c7245  nop     dword ptr [rax+rax+00h]
0x1402c724a  mov     cs:WdLogGlobalForLineNumber, 6EEh
0x1402c7254  jmp     loc_1402C7734
0x1402c7259  mov     rdx, [rdx+8]; unsigned __int16 *
0x1402c725d  lea     r8, [rsp+160h+Source]; UnicodeString
0x1402c7262  lea     rcx, aRegistryMachin_18; "\\Registry\\Machine\\System\\CurrentCon"...
0x1402c7269  call    DpiAppendStringToString
0x1402c726e  mov     ebx, eax
0x1402c7270  test    eax, eax
0x1402c7272  js      loc_1402C7734
0x1402c7278  xor     r9d, r9d; TitleIndex
0x1402c727b  mov     [rsp+160h+Disposition], r12; Disposition
0x1402c7280  lea     rax, [rsp+160h+Source]
0x1402c7285  mov     [rsp+160h+CreateOptions], r12d; CreateOptions
0x1402c728a  xorps   xmm0, xmm0
0x1402c728d  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x1402c7294  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x1402c7298  mov     [rbp+60h+ObjectAttributes.RootDirectory], r12
0x1402c729c  lea     edx, [r9+0Ch]; DesiredAccess
0x1402c72a0  mov     [rbp+60h+ObjectAttributes.Attributes], 2C0h
0x1402c72a7  lea     rcx, [rsp+160h+KeyHandle]; KeyHandle
0x1402c72ac  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x1402c72b0  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402c72b5  mov     [rsp+160h+Class], r12; Class
0x1402c72ba  call    cs:__imp_ZwCreateKey
0x1402c72c1  nop     dword ptr [rax+rax+00h]
0x1402c72c6  movsxd  rbx, eax
0x1402c72c9  test    eax, eax
0x1402c72cb  jns     short loc_1402C72F0
0x1402c72cd  mov     rdx, rbx
0x1402c72d0  mov     ecx, 2
0x1402c72d5  call    cs:__imp_WdLogSingleEntry1
0x1402c72dc  nop     dword ptr [rax+rax+00h]
0x1402c72e1  mov     cs:WdLogGlobalForLineNumber, 716h
0x1402c72eb  jmp     loc_1402C7734
0x1402c72f0  mov     rcx, [rdi+28h]
0x1402c72f4  mov     rdx, [rsp+160h+KeyHandle]
0x1402c72f9  add     rcx, 28h ; '('
0x1402c72fd  call    DpiGdoCreateServiceEntry
0x1402c7302  mov     ebx, eax
0x1402c7304  test    eax, eax
0x1402c7306  js      loc_1402C7734
0x1402c730c  mov     ebx, 3
0x1402c7311  cmp     [rdi+1E0h], r12b
0x1402c7318  jz      loc_1402C73B3
0x1402c731e  lea     rdx, [rbp+60h+SourceString]; SourceString
0x1402c7322  mov     [rbp+60h+SourceString], r12w
0x1402c7327  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x1402c732b  call    cs:__imp_RtlInitUnicodeString
0x1402c7332  nop     dword ptr [rax+rax+00h]
0x1402c7337  mov     rcx, [rsp+160h+Source.Buffer]; Source
0x1402c733c  lea     r8, [rbp+60h+ValueData]; UnicodeString
0x1402c7340  lea     rdx, [rbp+60h+SourceString]; unsigned __int16 *
0x1402c7344  call    DpiAppendStringToString
0x1402c7349  mov     ebx, eax
0x1402c734b  test    eax, eax
0x1402c734d  js      loc_1402C7734
0x1402c7353  movzx   eax, word ptr [rbp+60h+ValueData+2]
0x1402c7357  lea     rdx, aVideo; "VIDEO"
0x1402c735e  mov     r8, [r15+8]; ValueName
0x1402c7362  mov     r9d, 1; ValueType
0x1402c7368  mov     [rsp+160h+CreateOptions], eax; ValueLength
0x1402c736c  mov     rax, [rbp+60h+ValueData+8]
0x1402c7370  mov     [rsp+160h+Class], rax; ValueData
0x1402c7375  lea     ecx, [r9+3]; RelativeTo
0x1402c7379  call    cs:__imp_RtlWriteRegistryValue
0x1402c7380  nop     dword ptr [rax+rax+00h]
0x1402c7385  movsxd  rbx, eax
0x1402c7388  test    eax, eax
0x1402c738a  jns     loc_1402C7545
0x1402c7390  mov     rdx, rbx
0x1402c7393  mov     ecx, 2
0x1402c7398  call    cs:__imp_WdLogSingleEntry1
0x1402c739f  nop     dword ptr [rax+rax+00h]
0x1402c73a4  mov     cs:WdLogGlobalForLineNumber, 7B6h
0x1402c73ae  jmp     loc_1402C7734
0x1402c73b3  mov     r9d, r14d
0x1402c73b6  lea     r8, a04d; "\\%04d"
0x1402c73bd  mov     edx, 0Eh; unsigned __int64
0x1402c73c2  lea     rcx, [rbp+60h+SourceString]; unsigned __int16 *
0x1402c73c6  call    ?RtlStringCbPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1402c73cb  lea     rdx, [rbp+60h+SourceString+2]; SourceString
0x1402c73cf  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x1402c73d3  call    cs:__imp_RtlInitUnicodeString
0x1402c73da  nop     dword ptr [rax+rax+00h]
0x1402c73df  mov     rax, [rsp+160h+KeyHandle]
0x1402c73e4  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x1402c73e8  mov     [rbp+60h+ObjectAttributes.RootDirectory], rax
0x1402c73ec  lea     rcx, [rsp+160h+var_118]; KeyHandle
0x1402c73f1  lea     rax, [rbp+60h+DestinationString]
0x1402c73f5  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x1402c73fc  xorps   xmm0, xmm0
0x1402c73ff  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x1402c7403  mov     edx, 0F003Fh; DesiredAccess
0x1402c7408  mov     [rbp+60h+ObjectAttributes.Attributes], 240h
0x1402c740f  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402c7414  call    cs:__imp_ZwOpenKey
0x1402c741b  nop     dword ptr [rax+rax+00h]
0x1402c7420  test    eax, eax
0x1402c7422  js      short loc_1402C7454
0x1402c7424  mov     rcx, [rsp+160h+var_118]; KeyHandle
0x1402c7429  call    cs:__imp_ZwDeleteKey
0x1402c7430  nop     dword ptr [rax+rax+00h]
0x1402c7435  test    eax, eax
0x1402c7437  jns     short loc_1402C7454
0x1402c7439  movsxd  rdx, eax
0x1402c743c  mov     ecx, ebx
0x1402c743e  call    cs:__imp_WdLogSingleEntry1
0x1402c7445  nop     dword ptr [rax+rax+00h]
0x1402c744a  mov     cs:WdLogGlobalForLineNumber, 758h
0x1402c7454  xor     r9d, r9d; TitleIndex
0x1402c7457  lea     rax, [rsp+160h+var_120]
0x1402c745c  mov     [rsp+160h+Disposition], rax; Disposition
0x1402c7461  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x1402c7465  mov     [rsp+160h+CreateOptions], ebx; CreateOptions
0x1402c7469  lea     rcx, [rsp+160h+var_118]; KeyHandle
0x1402c746e  mov     [rsp+160h+Class], r12; Class
0x1402c7473  lea     edx, [r9+20h]; DesiredAccess
0x1402c7477  call    cs:__imp_ZwCreateKey
0x1402c747e  nop     dword ptr [rax+rax+00h]
0x1402c7483  movsxd  rbx, eax
0x1402c7486  test    eax, eax
0x1402c7488  jns     short loc_1402C74B9
0x1402c748a  cmp     ebx, 0C0000035h
0x1402c7490  jz      loc_1402C7337
0x1402c7496  mov     rdx, rbx
0x1402c7499  mov     ecx, 2
0x1402c749e  call    cs:__imp_WdLogSingleEntry1
0x1402c74a5  nop     dword ptr [rax+rax+00h]
0x1402c74aa  mov     cs:WdLogGlobalForLineNumber, 76Fh
0x1402c74b4  jmp     loc_1402C7734
0x1402c74b9  cmp     [rsp+160h+var_120], 1
0x1402c74be  jnz     loc_1402C7337
0x1402c74c4  xorps   xmm0, xmm0
0x1402c74c7  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x1402c74ce  lea     rcx, [rbp+60h+ValueName]; DestinationString
0x1402c74d2  movups  xmmword ptr [rbp+60h+ValueName.Length], xmm0
0x1402c74d6  call    cs:__imp_RtlInitUnicodeString
0x1402c74dd  nop     dword ptr [rax+rax+00h]
0x1402c74e2  movzx   eax, word ptr [rdi+210h]
0x1402c74e9  lea     rdx, [rbp+60h+ValueName]; ValueName
0x1402c74ed  mov     rcx, [rsp+160h+var_118]; KeyHandle
0x1402c74f2  mov     r9d, 6; Type
0x1402c74f8  mov     [rsp+160h+CreateOptions], eax; DataSize
0x1402c74fc  xor     r8d, r8d; TitleIndex
0x1402c74ff  mov     rax, [rdi+218h]
0x1402c7506  mov     [rsp+160h+Class], rax; Data
0x1402c750b  call    cs:__imp_ZwSetValueKey
0x1402c7512  nop     dword ptr [rax+rax+00h]
0x1402c7517  movsxd  rbx, eax
0x1402c751a  test    eax, eax
0x1402c751c  jns     loc_1402C7337
0x1402c7522  mov     rdx, rbx
0x1402c7525  mov     ecx, 2
0x1402c752a  call    cs:__imp_WdLogSingleEntry1
0x1402c7531  nop     dword ptr [rax+rax+00h]
0x1402c7536  mov     cs:WdLogGlobalForLineNumber, 78Dh
0x1402c7540  jmp     loc_1402C7734
0x1402c7545  movzx   eax, [rsp+160h+Source.Length]
0x1402c754a  mov     ecx, 100h
0x1402c754f  add     ax, 34h ; '4'
0x1402c7553  mov     [rsp+160h+Destination.Length], r12w
0x1402c7559  movzx   edx, ax
0x1402c755c  mov     r8d, 74727044h
0x1402c7562  mov     [rsp+160h+Destination.MaximumLength], dx
0x1402c7567  call    cs:__imp_ExAllocatePool2
0x1402c756e  nop     dword ptr [rax+rax+00h]
0x1402c7573  mov     [rsp+160h+Destination.Buffer], rax
0x1402c7578  test    rax, rax
0x1402c757b  jnz     short loc_1402C759E
0x1402c757d  mov     rdx, rbx
0x1402c7580  lea     ecx, [rax+2]
0x1402c7583  call    cs:__imp_WdLogSingleEntry1
0x1402c758a  nop     dword ptr [rax+rax+00h]
0x1402c758f  mov     cs:WdLogGlobalForLineNumber, 7D3h
0x1402c7599  jmp     loc_1402C7734
0x1402c759e  lea     rdx, [rsp+160h+Source]; Source
0x1402c75a3  lea     rcx, [rsp+160h+Destination]; Destination
0x1402c75a8  call    cs:__imp_RtlAppendUnicodeStringToString
0x1402c75af  nop     dword ptr [rax+rax+00h]
0x1402c75b4  movsxd  rbx, eax
0x1402c75b7  test    eax, eax
0x1402c75b9  jns     short loc_1402C75DE
0x1402c75bb  mov     rdx, rbx
0x1402c75be  mov     ecx, 2
0x1402c75c3  call    cs:__imp_WdLogSingleEntry1
0x1402c75ca  nop     dword ptr [rax+rax+00h]
0x1402c75cf  mov     cs:WdLogGlobalForLineNumber, 7E4h
0x1402c75d9  jmp     loc_1402C7734
0x1402c75de  lea     rdx, [rbp+60h+SourceString]; Source
0x1402c75e2  lea     rcx, [rsp+160h+Destination]; Destination
0x1402c75e7  call    cs:__imp_RtlAppendUnicodeToString
0x1402c75ee  nop     dword ptr [rax+rax+00h]
0x1402c75f3  movsxd  rbx, eax
0x1402c75f6  test    eax, eax
0x1402c75f8  jns     short loc_1402C761D
0x1402c75fa  mov     rdx, rbx
0x1402c75fd  mov     ecx, 2
0x1402c7602  call    cs:__imp_WdLogSingleEntry1
0x1402c7609  nop     dword ptr [rax+rax+00h]
0x1402c760e  mov     cs:WdLogGlobalForLineNumber, 7F5h
0x1402c7618  jmp     loc_1402C7734
0x1402c761d  lea     rdx, aVolatilesettin; "\\VolatileSettings"
0x1402c7624  lea     rcx, [rsp+160h+Destination]; Destination
0x1402c7629  call    cs:__imp_RtlAppendUnicodeToString
0x1402c7630  nop     dword ptr [rax+rax+00h]
0x1402c7635  movsxd  rbx, eax
0x1402c7638  test    eax, eax
0x1402c763a  jns     short loc_1402C765F
0x1402c763c  mov     rdx, rbx
0x1402c763f  mov     ecx, 2
0x1402c7644  call    cs:__imp_WdLogSingleEntry1
0x1402c764b  nop     dword ptr [rax+rax+00h]
0x1402c7650  mov     cs:WdLogGlobalForLineNumber, 806h
0x1402c765a  jmp     loc_1402C7734
0x1402c765f  lea     rax, [rsp+160h+Destination]
0x1402c7664  mov     [rsp+160h+Disposition], r12; Disposition
0x1402c7669  xorps   xmm0, xmm0
0x1402c766c  mov     [rsp+160h+CreateOptions], 1; CreateOptions
0x1402c7674  xor     r9d, r9d; TitleIndex
0x1402c7677  mov     [rbp+60h+var_80.ObjectName], rax
0x1402c767b  lea     r8, [rbp+60h+var_80]; ObjectAttributes
0x1402c767f  mov     [rsp+160h+Class], r12; Class
0x1402c7684  mov     edx, 0C0000000h; DesiredAccess
0x1402c7689  mov     [rbp+60h+var_80.Length], 30h ; '0'
0x1402c7690  lea     rcx, [rsp+160h+Handle]; KeyHandle
0x1402c7695  mov     [rbp+60h+var_80.RootDirectory], r12
0x1402c7699  movdqu  xmmword ptr [rbp+60h+var_80.SecurityDescriptor], xmm0
0x1402c769e  mov     [rbp+60h+var_80.Attributes], 240h
0x1402c76a5  call    cs:__imp_ZwCreateKey
0x1402c76ac  nop     dword ptr [rax+rax+00h]
0x1402c76b1  movsxd  rbx, eax
0x1402c76b4  test    eax, eax
0x1402c76b6  jns     short loc_1402C76D8
0x1402c76b8  mov     rdx, rbx
0x1402c76bb  mov     ecx, 2
0x1402c76c0  call    cs:__imp_WdLogSingleEntry1
0x1402c76c7  nop     dword ptr [rax+rax+00h]
0x1402c76cc  mov     cs:WdLogGlobalForLineNumber, 822h
  ... truncated ...
```
