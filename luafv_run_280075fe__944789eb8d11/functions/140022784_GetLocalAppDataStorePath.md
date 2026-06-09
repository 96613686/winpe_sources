# GetLocalAppDataStorePath

- ea: `0x140022784`
- end: `0x140022b44`
- name: `GetLocalAppDataStorePath`
- size: `960`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140019b10`

## callees

- `0x14001b6a0`
- `0x14001dd90`
- `0x1400219fc`
- `0x140022784`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400227f4`
- `ntoskrnl!ZwOpenKey` at `0x1400227f4`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400229bc`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140022a71`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400229bc`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140022a71`
- `ntoskrnl!ZwQueryValueKey` at `0x14002294e`
- `ntoskrnl!ZwQueryValueKey` at `0x14002294e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002287e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140022adc`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002287e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140022adc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140022ac6`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140022ac6`
- `ntoskrnl!ZwClose` at `0x140022b1e`
- `ntoskrnl!ZwClose` at `0x140022b1e`
- `ntoskrnl!ExAllocatePool2` at `0x1400228d8`
- `ntoskrnl!ExAllocatePool2` at `0x1400228d8`
- `FLTMGR!FltReleasePushLockEx` at `0x14002291a`
- `FLTMGR!FltReleasePushLockEx` at `0x14002291a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400228ff`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400228ff`

## pseudocode

```c
NTSTATUS __fastcall GetLocalAppDataStorePath(const UNICODE_STRING *a1, struct _UNICODE_STRING *a2)
{
  NTSTATUS result; // eax
  unsigned int v5; // r8d
  __int64 v6; // rdx
  PCUNICODE_STRING v7; // rax
  int v8; // edi
  NTSTATUS appended; // ebx
  ULONG Length; // ebx
  __int64 Pool2; // rax
  __int64 v12; // rdi
  __int64 v13; // rdi
  NTSTATUS v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // r9d
  WCHAR *v17; // r8
  __int64 v18; // rcx
  char *Pool; // rax
  NTSTATUS v20; // eax
  UNICODE_STRING String2; // [rsp+30h] [rbp-59h] BYREF
  UNICODE_STRING v22; // [rsp+40h] [rbp-49h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+50h] [rbp-39h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+60h] [rbp-29h] BYREF
  PCUNICODE_STRING Source[3]; // [rsp+70h] [rbp-19h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-1h] BYREF
  ULONG ResultLength; // [rsp+100h] [rbp+77h] BYREF
  void *KeyHandle; // [rsp+108h] [rbp+7Fh] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  KeyHandle = 0;
  *(_QWORD *)&ValueName.Length = 0;
  ResultLength = 0;
  ValueName.Buffer = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)HiveListKey;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  String2 = 0;
  v22 = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result < 0 )
    return result;
  Source[1] = a1;
  Source[0] = (PCUNICODE_STRING)&HiveListValuePrefix;
  v5 = 0;
  Source[2] = (PCUNICODE_STRING)&HiveListValueSuffix;
  v6 = 0;
  Destination = 0;
  do
  {
    v7 = Source[v6++];
    v5 += v7->Length;
  }
  while ( v6 != 3 );
  if ( v5 > 0xFFFE )
  {
    appended = -1073741823;
    goto LABEL_41;
  }
  Destination.MaximumLength = v5;
  Destination.Buffer = (PWSTR)LuafvAllocatePool(1, (unsigned __int16)v5, 2);
  if ( Destination.Buffer )
  {
    v8 = 0;
    while ( 1 )
    {
      appended = RtlAppendUnicodeStringToString(&Destination, Source[v8]);
      if ( appended < 0 )
        break;
      if ( (unsigned int)++v8 >= 3 )
      {
        ValueName = Destination;
        goto LABEL_12;
      }
    }
    LuafvFreePool(Destination.Buffer);
  }
  else
  {
    appended = -1073741670;
  }
LABEL_12:
  if ( appended < 0 )
    goto LABEL_41;
  for ( Length = 216; ; Length = ResultLength )
  {
    if ( Length >= 0xFFFFFFF8 )
      goto LABEL_38;
    Pool2 = ExAllocatePool2(256, Length + 8, 1717663052);
    v12 = Pool2;
    if ( !Pool2
      || (*(_DWORD *)Pool2 = Length,
          *(_BYTE *)(Pool2 + 4) = -1,
          FltAcquirePushLockExclusiveEx(&PoolLock, 0),
          dword_14000F2FC += Length,
          FltReleasePushLockEx(&PoolLock, 0),
          (v13 = v12 + 8) == 0) )
    {
LABEL_38:
      appended = -1073741670;
      goto LABEL_41;
    }
    v14 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, (PVOID)v13, Length, &ResultLength);
    appended = v14;
    if ( v14 >= 0 )
      break;
    if ( v14 != -1073741789 && v14 != -2147483643 )
      goto LABEL_39;
    LuafvFreePool(v13);
  }
  if ( *(_DWORD *)(v13 + 4) == 1 )
  {
    v15 = *(_DWORD *)(v13 + 8);
    if ( (v15 & 1) == 0 && v15 >= 4 )
    {
      String2.Length = *(_DWORD *)(v13 + 8);
      String2.MaximumLength = v15;
      String2.Buffer = (PWSTR)(v13 + 12);
      if ( !RtlPrefixUnicodeString(&String1, &String2, 1u) )
      {
        appended = -1073741806;
        goto LABEL_39;
      }
      v16 = (unsigned __int16)(String2.Length - stru_14000F128.Length);
      v17 = (PWSTR)((char *)String2.Buffer + stru_14000F128.Length);
      String2.MaximumLength = String2.Length - stru_14000F128.Length;
      v18 = v16 >> 1;
      String2.Length -= stru_14000F128.Length;
      String2.Buffer = v17;
      v22.Length = 0;
      if ( v16 >> 1 )
      {
        do
        {
          if ( !(_DWORD)v18 )
            break;
          v18 = (unsigned int)(v18 - 1);
        }
        while ( v17[v18] != 92 );
        v22.Buffer = &v17[v18];
        String2.Length = 2 * v18;
        v22.Length = v16 - 2 * v18;
        v22.MaximumLength = v22.Length;
        if ( (unsigned __int8)LuafvSplitPathLeft(&String2, &v22) )
        {
          if ( (unsigned __int8)LuafvSplitPathLeft(&String2, &v22)
            && RtlPrefixUnicodeString(&MicrosoftWindows, &v22, 1u)
            && String2.Length )
          {
            ResultLength = String2.Length + LuafvStoreRoot.Length;
            Pool = LuafvAllocatePool(1, ResultLength, 2);
            if ( Pool )
            {
              a2->Buffer = (PWSTR)Pool;
              a2->MaximumLength = ResultLength;
              RtlCopyUnicodeString(a2, &String2);
              v20 = RtlAppendUnicodeStringToString(a2, &LuafvStoreRoot);
              a2->Length -= 2;
              appended = v20;
            }
            else
            {
              appended = -1073741670;
            }
            goto LABEL_39;
          }
        }
      }
    }
    appended = -1073741773;
    goto LABEL_39;
  }
  appended = -1073741788;
LABEL_39:
  LuafvFreePool(v13);
LABEL_41:
  if ( ValueName.Buffer )
    LuafvFreePool(ValueName.Buffer);
  ZwClose(KeyHandle);
  return appended;
}

```

## disassembly

```asm
0x140022784  mov     [rsp-8+arg_0], rbx
0x140022789  push    rbp
0x14002278a  push    rsi
0x14002278b  push    rdi
0x14002278c  push    r13
0x14002278e  push    r14
0x140022790  lea     rbp, [rsp-37h]
0x140022795  sub     rsp, 0C0h
0x14002279c  xor     r14d, r14d
0x14002279f  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400227a7  xorps   xmm0, xmm0
0x1400227aa  mov     [rbp+57h+KeyHandle], r14
0x1400227ae  mov     rsi, rdx
0x1400227b1  mov     qword ptr [rbp+57h+ValueName.Length], r14
0x1400227b5  mov     rbx, rcx
0x1400227b8  mov     [rbp+57h+arg_10], r14d
0x1400227bc  xorps   xmm1, xmm1
0x1400227bf  mov     [rbp+57h+ValueName.Buffer], r14
0x1400227c3  lea     rax, HiveListKey; "vx"
0x1400227ca  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x1400227ce  mov     edx, 20019h; DesiredAccess
0x1400227d3  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400227d7  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400227db  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400227e3  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400227e7  movups  xmmword ptr [rbp+57h+String2.Length], xmm0
0x1400227eb  movups  xmmword ptr [rbp+57h+var_A0.Length], xmm1
0x1400227ef  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400227f4  call    cs:__imp_ZwOpenKey
0x1400227fb  nop     dword ptr [rax+rax+00h]
0x140022800  test    eax, eax
0x140022802  js      loc_140022B2C
0x140022808  lea     rax, HiveListValuePrefix
0x14002280f  mov     [rbp+57h+var_68], rbx
0x140022813  mov     [rbp+57h+Source], rax
0x140022817  xorps   xmm0, xmm0
0x14002281a  lea     rax, HiveListValueSuffix
0x140022821  mov     r8d, r14d
0x140022824  mov     [rbp+57h+var_60], rax
0x140022828  mov     edx, r14d
0x14002282b  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x14002282f  mov     rax, [rbp+rdx*8+57h+Source]
0x140022834  inc     rdx
0x140022837  movzx   ecx, word ptr [rax]
0x14002283a  add     r8d, ecx
0x14002283d  cmp     rdx, 3
0x140022841  jnz     short loc_14002282F
0x140022843  mov     r13d, 0FFFEh
0x140022849  cmp     r8d, r13d
0x14002284c  ja      loc_140022B07
0x140022852  movzx   edx, r8w
0x140022856  mov     ecx, 1
0x14002285b  mov     r8b, 2
0x14002285e  mov     [rbp+57h+Destination.MaximumLength], dx
0x140022862  call    LuafvAllocatePool
0x140022867  mov     [rbp+57h+Destination.Buffer], rax
0x14002286b  test    rax, rax
0x14002286e  jz      short loc_1400228AD
0x140022870  mov     edi, r14d
0x140022873  mov     edx, edi
0x140022875  lea     rcx, [rbp+57h+Destination]; Destination
0x140022879  mov     rdx, [rbp+rdx*8+57h+Source]; Source
0x14002287e  call    cs:__imp_RtlAppendUnicodeStringToString
0x140022885  nop     dword ptr [rax+rax+00h]
0x14002288a  mov     ebx, eax
0x14002288c  test    eax, eax
0x14002288e  js      short loc_1400228A2
0x140022890  inc     edi
0x140022892  cmp     edi, 3
0x140022895  jb      short loc_140022873
0x140022897  movaps  xmm0, xmmword ptr [rbp+57h+Destination.Length]
0x14002289b  movdqa  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x1400228a0  jmp     short loc_1400228B2
0x1400228a2  mov     rcx, [rbp+57h+Destination.Buffer]
0x1400228a6  call    LuafvFreePool
0x1400228ab  jmp     short loc_1400228B2
0x1400228ad  mov     ebx, 0C000009Ah
0x1400228b2  test    ebx, ebx
0x1400228b4  js      loc_140022B0C
0x1400228ba  mov     ebx, 0D8h
0x1400228bf  lea     eax, [rbx+8]
0x1400228c2  cmp     eax, 8
0x1400228c5  jb      loc_140022AF0
0x1400228cb  mov     edx, eax
0x1400228cd  mov     ecx, 100h
0x1400228d2  mov     r8d, 6661754Ch
0x1400228d8  call    cs:__imp_ExAllocatePool2
0x1400228df  nop     dword ptr [rax+rax+00h]
0x1400228e4  mov     rdi, rax
0x1400228e7  test    rax, rax
0x1400228ea  jz      loc_140022AF0
0x1400228f0  xor     edx, edx
0x1400228f2  mov     [rax], ebx
0x1400228f4  lea     rcx, PoolLock
0x1400228fb  mov     byte ptr [rax+4], 0FFh
0x1400228ff  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140022906  nop     dword ptr [rax+rax+00h]
0x14002290b  add     cs:dword_14000F2FC, ebx
0x140022911  lea     rcx, PoolLock
0x140022918  xor     edx, edx
0x14002291a  call    cs:__imp_FltReleasePushLockEx
0x140022921  nop     dword ptr [rax+rax+00h]
0x140022926  add     rdi, 8
0x14002292a  jz      loc_140022AF3
0x140022930  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140022934  lea     rax, [rbp+57h+arg_10]
0x140022938  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x14002293d  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140022941  mov     r9, rdi; KeyValueInformation
0x140022944  mov     [rsp+0E0h+Length], ebx; Length
0x140022948  mov     r8d, 2; KeyValueInformationClass
0x14002294e  call    cs:__imp_ZwQueryValueKey
0x140022955  nop     dword ptr [rax+rax+00h]
0x14002295a  mov     ebx, eax
0x14002295c  test    eax, eax
0x14002295e  jns     short loc_140022982
0x140022960  cmp     eax, 0C0000023h
0x140022965  jz      short loc_140022972
0x140022967  cmp     eax, 80000005h
0x14002296c  jnz     loc_140022AFD
0x140022972  mov     rcx, rdi
0x140022975  call    LuafvFreePool
0x14002297a  mov     ebx, [rbp+57h+arg_10]
0x14002297d  jmp     loc_1400228BF
0x140022982  cmp     dword ptr [rdi+4], 1
0x140022986  jz      short loc_140022992
0x140022988  mov     ebx, 0C0000024h
0x14002298d  jmp     loc_140022AFD
0x140022992  mov     eax, [rdi+8]
0x140022995  test    al, 1
0x140022997  jnz     short loc_140022A09
0x140022999  cmp     eax, 4
0x14002299c  jb      short loc_140022A09
0x14002299e  mov     [rbp+57h+String2.Length], ax
0x1400229a2  lea     rdx, [rbp+57h+String2]; String2
0x1400229a6  mov     [rbp+57h+String2.MaximumLength], ax
0x1400229aa  lea     rcx, String1; String1
0x1400229b1  lea     rax, [rdi+0Ch]
0x1400229b5  mov     r8b, 1; CaseInSensitive
0x1400229b8  mov     [rbp+57h+String2.Buffer], rax
0x1400229bc  call    cs:__imp_RtlPrefixUnicodeString
0x1400229c3  nop     dword ptr [rax+rax+00h]
0x1400229c8  test    al, al
0x1400229ca  jnz     short loc_1400229D6
0x1400229cc  mov     ebx, 0C0000012h
0x1400229d1  jmp     loc_140022AFD
0x1400229d6  movzx   ecx, cs:stru_14000F128.Length
0x1400229dd  movzx   eax, [rbp+57h+String2.Length]
0x1400229e1  mov     r8, [rbp+57h+String2.Buffer]
0x1400229e5  sub     ax, cx
0x1400229e8  movzx   r9d, ax
0x1400229ec  add     r8, rcx
0x1400229ef  mov     ecx, r9d
0x1400229f2  mov     [rbp+57h+String2.MaximumLength], r9w
0x1400229f7  shr     ecx, 1
0x1400229f9  mov     [rbp+57h+String2.Length], r9w
0x1400229fe  mov     [rbp+57h+String2.Buffer], r8
0x140022a02  mov     [rbp+57h+var_A0.Length], r14w
0x140022a07  jnz     short loc_140022A13
0x140022a09  mov     ebx, 0C0000033h
0x140022a0e  jmp     loc_140022AFD
0x140022a13  test    ecx, ecx
0x140022a15  jz      short loc_140022A21
0x140022a17  dec     ecx
0x140022a19  cmp     word ptr [r8+rcx*2], 5Ch ; '\'
0x140022a1f  jnz     short loc_140022A13
0x140022a21  movzx   edx, cx
0x140022a24  lea     rcx, [r8+rcx*2]
0x140022a28  add     dx, dx
0x140022a2b  mov     [rbp+57h+var_A0.Buffer], rcx
0x140022a2f  sub     r9w, dx
0x140022a33  mov     [rbp+57h+String2.Length], dx
0x140022a37  lea     rdx, [rbp+57h+var_A0]
0x140022a3b  mov     [rbp+57h+var_A0.Length], r9w
0x140022a40  lea     rcx, [rbp+57h+String2]
0x140022a44  mov     [rbp+57h+var_A0.MaximumLength], r9w
0x140022a49  call    LuafvSplitPathLeft
0x140022a4e  test    al, al
0x140022a50  jz      short loc_140022A09
0x140022a52  lea     rdx, [rbp+57h+var_A0]
0x140022a56  lea     rcx, [rbp+57h+String2]
0x140022a5a  call    LuafvSplitPathLeft
0x140022a5f  test    al, al
0x140022a61  jz      short loc_140022A09
0x140022a63  mov     r8b, 1; CaseInSensitive
0x140022a66  lea     rdx, [rbp+57h+var_A0]; String2
0x140022a6a  lea     rcx, MicrosoftWindows; String1
0x140022a71  call    cs:__imp_RtlPrefixUnicodeString
0x140022a78  nop     dword ptr [rax+rax+00h]
0x140022a7d  test    al, al
0x140022a7f  jz      short loc_140022A09
0x140022a81  movzx   eax, [rbp+57h+String2.Length]
0x140022a85  test    ax, ax
0x140022a88  jz      loc_140022A09
0x140022a8e  movzx   edx, cs:LuafvStoreRoot.Length
0x140022a95  mov     r8b, 2
0x140022a98  add     edx, eax
0x140022a9a  mov     ecx, 1
0x140022a9f  mov     [rbp+57h+arg_10], edx
0x140022aa2  call    LuafvAllocatePool
0x140022aa7  test    rax, rax
0x140022aaa  jnz     short loc_140022AB3
0x140022aac  mov     ebx, 0C000009Ah
0x140022ab1  jmp     short loc_140022AFD
0x140022ab3  mov     [rsi+8], rax
0x140022ab7  lea     rdx, [rbp+57h+String2]; SourceString
0x140022abb  movzx   eax, word ptr [rbp+57h+arg_10]
0x140022abf  mov     rcx, rsi; DestinationString
0x140022ac2  mov     [rsi+2], ax
0x140022ac6  call    cs:__imp_RtlCopyUnicodeString
0x140022acd  nop     dword ptr [rax+rax+00h]
0x140022ad2  lea     rdx, LuafvStoreRoot; Source
0x140022ad9  mov     rcx, rsi; Destination
0x140022adc  call    cs:__imp_RtlAppendUnicodeStringToString
0x140022ae3  nop     dword ptr [rax+rax+00h]
0x140022ae8  add     [rsi], r13w
0x140022aec  mov     ebx, eax
0x140022aee  jmp     short loc_140022AFD
0x140022af0  mov     rdi, r14
0x140022af3  mov     ebx, 0C000009Ah
0x140022af8  test    rdi, rdi
0x140022afb  jz      short loc_140022B0C
0x140022afd  mov     rcx, rdi
0x140022b00  call    LuafvFreePool
0x140022b05  jmp     short loc_140022B0C
0x140022b07  mov     ebx, 0C0000001h
0x140022b0c  mov     rcx, [rbp+57h+ValueName.Buffer]
0x140022b10  test    rcx, rcx
0x140022b13  jz      short loc_140022B1A
0x140022b15  call    LuafvFreePool
0x140022b1a  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140022b1e  call    cs:__imp_ZwClose
0x140022b25  nop     dword ptr [rax+rax+00h]
0x140022b2a  mov     eax, ebx
0x140022b2c  mov     rbx, [rsp+0E0h+arg_0]
0x140022b34  add     rsp, 0C0h
0x140022b3b  pop     r14
0x140022b3d  pop     r13
0x140022b3f  pop     rdi
0x140022b40  pop     rsi
0x140022b41  pop     rbp
0x140022b42  retn
```
