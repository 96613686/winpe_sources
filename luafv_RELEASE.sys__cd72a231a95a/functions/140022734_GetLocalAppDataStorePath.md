# GetLocalAppDataStorePath

- ea: `0x140022734`
- end: `0x140022af4`
- name: `GetLocalAppDataStorePath`
- size: `960`
- prototype: `NTSTATUS __fastcall(const UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140019ac0`

## callees

- `0x14001b650`
- `0x14001dd40`
- `0x1400219ac`
- `0x140022734`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400227a4`
- `ntoskrnl!ZwOpenKey` at `0x1400227a4`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14002296c`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140022a21`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14002296c`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140022a21`
- `ntoskrnl!ZwQueryValueKey` at `0x1400228fe`
- `ntoskrnl!ZwQueryValueKey` at `0x1400228fe`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002282e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140022a8c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002282e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140022a8c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140022a76`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140022a76`
- `ntoskrnl!ZwClose` at `0x140022ace`
- `ntoskrnl!ZwClose` at `0x140022ace`
- `ntoskrnl!ExAllocatePool2` at `0x140022888`
- `ntoskrnl!ExAllocatePool2` at `0x140022888`
- `FLTMGR!FltReleasePushLockEx` at `0x1400228ca`
- `FLTMGR!FltReleasePushLockEx` at `0x1400228ca`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400228af`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400228af`

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
    LuafvFreePool((__int64)Destination.Buffer);
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
          dword_14000ECBC += Length,
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
      v16 = (unsigned __int16)(String2.Length - stru_14000EAE8.Length);
      v17 = (PWSTR)((char *)String2.Buffer + stru_14000EAE8.Length);
      String2.MaximumLength = String2.Length - stru_14000EAE8.Length;
      v18 = v16 >> 1;
      String2.Length -= stru_14000EAE8.Length;
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
        if ( LuafvSplitPathLeft(&String2.Length, (__int64)&v22) )
        {
          if ( LuafvSplitPathLeft(&String2.Length, (__int64)&v22)
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
    LuafvFreePool((__int64)ValueName.Buffer);
  ZwClose(KeyHandle);
  return appended;
}

```

## disassembly

```asm
0x140022734  mov     [rsp-8+arg_0], rbx
0x140022739  push    rbp
0x14002273a  push    rsi
0x14002273b  push    rdi
0x14002273c  push    r13
0x14002273e  push    r14
0x140022740  lea     rbp, [rsp-37h]
0x140022745  sub     rsp, 0C0h
0x14002274c  xor     r14d, r14d
0x14002274f  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140022757  xorps   xmm0, xmm0
0x14002275a  mov     [rbp+57h+KeyHandle], r14
0x14002275e  mov     rsi, rdx
0x140022761  mov     qword ptr [rbp+57h+ValueName.Length], r14
0x140022765  mov     rbx, rcx
0x140022768  mov     [rbp+57h+arg_10], r14d
0x14002276c  xorps   xmm1, xmm1
0x14002276f  mov     [rbp+57h+ValueName.Buffer], r14
0x140022773  lea     rax, HiveListKey; "vx"
0x14002277a  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x14002277e  mov     edx, 20019h; DesiredAccess
0x140022783  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140022787  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14002278b  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140022793  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140022797  movups  xmmword ptr [rbp+57h+String2.Length], xmm0
0x14002279b  movups  xmmword ptr [rbp+57h+var_A0.Length], xmm1
0x14002279f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400227a4  call    cs:__imp_ZwOpenKey
0x1400227ab  nop     dword ptr [rax+rax+00h]
0x1400227b0  test    eax, eax
0x1400227b2  js      loc_140022ADC
0x1400227b8  lea     rax, HiveListValuePrefix
0x1400227bf  mov     [rbp+57h+var_68], rbx
0x1400227c3  mov     [rbp+57h+Source], rax
0x1400227c7  xorps   xmm0, xmm0
0x1400227ca  lea     rax, HiveListValueSuffix
0x1400227d1  mov     r8d, r14d
0x1400227d4  mov     [rbp+57h+var_60], rax
0x1400227d8  mov     edx, r14d
0x1400227db  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x1400227df  mov     rax, [rbp+rdx*8+57h+Source]
0x1400227e4  inc     rdx
0x1400227e7  movzx   ecx, word ptr [rax]
0x1400227ea  add     r8d, ecx
0x1400227ed  cmp     rdx, 3
0x1400227f1  jnz     short loc_1400227DF
0x1400227f3  mov     r13d, 0FFFEh
0x1400227f9  cmp     r8d, r13d
0x1400227fc  ja      loc_140022AB7
0x140022802  movzx   edx, r8w
0x140022806  mov     ecx, 1
0x14002280b  mov     r8b, 2
0x14002280e  mov     [rbp+57h+Destination.MaximumLength], dx
0x140022812  call    LuafvAllocatePool
0x140022817  mov     [rbp+57h+Destination.Buffer], rax
0x14002281b  test    rax, rax
0x14002281e  jz      short loc_14002285D
0x140022820  mov     edi, r14d
0x140022823  mov     edx, edi
0x140022825  lea     rcx, [rbp+57h+Destination]; Destination
0x140022829  mov     rdx, [rbp+rdx*8+57h+Source]; Source
0x14002282e  call    cs:__imp_RtlAppendUnicodeStringToString
0x140022835  nop     dword ptr [rax+rax+00h]
0x14002283a  mov     ebx, eax
0x14002283c  test    eax, eax
0x14002283e  js      short loc_140022852
0x140022840  inc     edi
0x140022842  cmp     edi, 3
0x140022845  jb      short loc_140022823
0x140022847  movaps  xmm0, xmmword ptr [rbp+57h+Destination.Length]
0x14002284b  movdqa  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x140022850  jmp     short loc_140022862
0x140022852  mov     rcx, [rbp+57h+Destination.Buffer]
0x140022856  call    LuafvFreePool
0x14002285b  jmp     short loc_140022862
0x14002285d  mov     ebx, 0C000009Ah
0x140022862  test    ebx, ebx
0x140022864  js      loc_140022ABC
0x14002286a  mov     ebx, 0D8h
0x14002286f  lea     eax, [rbx+8]
0x140022872  cmp     eax, 8
0x140022875  jb      loc_140022AA0
0x14002287b  mov     edx, eax
0x14002287d  mov     ecx, 100h
0x140022882  mov     r8d, 6661754Ch
0x140022888  call    cs:__imp_ExAllocatePool2
0x14002288f  nop     dword ptr [rax+rax+00h]
0x140022894  mov     rdi, rax
0x140022897  test    rax, rax
0x14002289a  jz      loc_140022AA0
0x1400228a0  xor     edx, edx
0x1400228a2  mov     [rax], ebx
0x1400228a4  lea     rcx, PoolLock
0x1400228ab  mov     byte ptr [rax+4], 0FFh
0x1400228af  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400228b6  nop     dword ptr [rax+rax+00h]
0x1400228bb  add     cs:dword_14000ECBC, ebx
0x1400228c1  lea     rcx, PoolLock
0x1400228c8  xor     edx, edx
0x1400228ca  call    cs:__imp_FltReleasePushLockEx
0x1400228d1  nop     dword ptr [rax+rax+00h]
0x1400228d6  add     rdi, 8
0x1400228da  jz      loc_140022AA3
0x1400228e0  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400228e4  lea     rax, [rbp+57h+arg_10]
0x1400228e8  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1400228ed  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1400228f1  mov     r9, rdi; KeyValueInformation
0x1400228f4  mov     [rsp+0E0h+Length], ebx; Length
0x1400228f8  mov     r8d, 2; KeyValueInformationClass
0x1400228fe  call    cs:__imp_ZwQueryValueKey
0x140022905  nop     dword ptr [rax+rax+00h]
0x14002290a  mov     ebx, eax
0x14002290c  test    eax, eax
0x14002290e  jns     short loc_140022932
0x140022910  cmp     eax, 0C0000023h
0x140022915  jz      short loc_140022922
0x140022917  cmp     eax, 80000005h
0x14002291c  jnz     loc_140022AAD
0x140022922  mov     rcx, rdi
0x140022925  call    LuafvFreePool
0x14002292a  mov     ebx, [rbp+57h+arg_10]
0x14002292d  jmp     loc_14002286F
0x140022932  cmp     dword ptr [rdi+4], 1
0x140022936  jz      short loc_140022942
0x140022938  mov     ebx, 0C0000024h
0x14002293d  jmp     loc_140022AAD
0x140022942  mov     eax, [rdi+8]
0x140022945  test    al, 1
0x140022947  jnz     short loc_1400229B9
0x140022949  cmp     eax, 4
0x14002294c  jb      short loc_1400229B9
0x14002294e  mov     [rbp+57h+String2.Length], ax
0x140022952  lea     rdx, [rbp+57h+String2]; String2
0x140022956  mov     [rbp+57h+String2.MaximumLength], ax
0x14002295a  lea     rcx, String1; String1
0x140022961  lea     rax, [rdi+0Ch]
0x140022965  mov     r8b, 1; CaseInSensitive
0x140022968  mov     [rbp+57h+String2.Buffer], rax
0x14002296c  call    cs:__imp_RtlPrefixUnicodeString
0x140022973  nop     dword ptr [rax+rax+00h]
0x140022978  test    al, al
0x14002297a  jnz     short loc_140022986
0x14002297c  mov     ebx, 0C0000012h
0x140022981  jmp     loc_140022AAD
0x140022986  movzx   ecx, cs:stru_14000EAE8.Length
0x14002298d  movzx   eax, [rbp+57h+String2.Length]
0x140022991  mov     r8, [rbp+57h+String2.Buffer]
0x140022995  sub     ax, cx
0x140022998  movzx   r9d, ax
0x14002299c  add     r8, rcx
0x14002299f  mov     ecx, r9d
0x1400229a2  mov     [rbp+57h+String2.MaximumLength], r9w
0x1400229a7  shr     ecx, 1
0x1400229a9  mov     [rbp+57h+String2.Length], r9w
0x1400229ae  mov     [rbp+57h+String2.Buffer], r8
0x1400229b2  mov     [rbp+57h+var_A0.Length], r14w
0x1400229b7  jnz     short loc_1400229C3
0x1400229b9  mov     ebx, 0C0000033h
0x1400229be  jmp     loc_140022AAD
0x1400229c3  test    ecx, ecx
0x1400229c5  jz      short loc_1400229D1
0x1400229c7  dec     ecx
0x1400229c9  cmp     word ptr [r8+rcx*2], 5Ch ; '\'
0x1400229cf  jnz     short loc_1400229C3
0x1400229d1  movzx   edx, cx
0x1400229d4  lea     rcx, [r8+rcx*2]
0x1400229d8  add     dx, dx
0x1400229db  mov     [rbp+57h+var_A0.Buffer], rcx
0x1400229df  sub     r9w, dx
0x1400229e3  mov     [rbp+57h+String2.Length], dx
0x1400229e7  lea     rdx, [rbp+57h+var_A0]
0x1400229eb  mov     [rbp+57h+var_A0.Length], r9w
0x1400229f0  lea     rcx, [rbp+57h+String2]
0x1400229f4  mov     [rbp+57h+var_A0.MaximumLength], r9w
0x1400229f9  call    LuafvSplitPathLeft
0x1400229fe  test    al, al
0x140022a00  jz      short loc_1400229B9
0x140022a02  lea     rdx, [rbp+57h+var_A0]
0x140022a06  lea     rcx, [rbp+57h+String2]
0x140022a0a  call    LuafvSplitPathLeft
0x140022a0f  test    al, al
0x140022a11  jz      short loc_1400229B9
0x140022a13  mov     r8b, 1; CaseInSensitive
0x140022a16  lea     rdx, [rbp+57h+var_A0]; String2
0x140022a1a  lea     rcx, MicrosoftWindows; String1
0x140022a21  call    cs:__imp_RtlPrefixUnicodeString
0x140022a28  nop     dword ptr [rax+rax+00h]
0x140022a2d  test    al, al
0x140022a2f  jz      short loc_1400229B9
0x140022a31  movzx   eax, [rbp+57h+String2.Length]
0x140022a35  test    ax, ax
0x140022a38  jz      loc_1400229B9
0x140022a3e  movzx   edx, cs:LuafvStoreRoot.Length
0x140022a45  mov     r8b, 2
0x140022a48  add     edx, eax
0x140022a4a  mov     ecx, 1
0x140022a4f  mov     [rbp+57h+arg_10], edx
0x140022a52  call    LuafvAllocatePool
0x140022a57  test    rax, rax
0x140022a5a  jnz     short loc_140022A63
0x140022a5c  mov     ebx, 0C000009Ah
0x140022a61  jmp     short loc_140022AAD
0x140022a63  mov     [rsi+8], rax
0x140022a67  lea     rdx, [rbp+57h+String2]; SourceString
0x140022a6b  movzx   eax, word ptr [rbp+57h+arg_10]
0x140022a6f  mov     rcx, rsi; DestinationString
0x140022a72  mov     [rsi+2], ax
0x140022a76  call    cs:__imp_RtlCopyUnicodeString
0x140022a7d  nop     dword ptr [rax+rax+00h]
0x140022a82  lea     rdx, LuafvStoreRoot; Source
0x140022a89  mov     rcx, rsi; Destination
0x140022a8c  call    cs:__imp_RtlAppendUnicodeStringToString
0x140022a93  nop     dword ptr [rax+rax+00h]
0x140022a98  add     [rsi], r13w
0x140022a9c  mov     ebx, eax
0x140022a9e  jmp     short loc_140022AAD
0x140022aa0  mov     rdi, r14
0x140022aa3  mov     ebx, 0C000009Ah
0x140022aa8  test    rdi, rdi
0x140022aab  jz      short loc_140022ABC
0x140022aad  mov     rcx, rdi
0x140022ab0  call    LuafvFreePool
0x140022ab5  jmp     short loc_140022ABC
0x140022ab7  mov     ebx, 0C0000001h
0x140022abc  mov     rcx, [rbp+57h+ValueName.Buffer]
0x140022ac0  test    rcx, rcx
0x140022ac3  jz      short loc_140022ACA
0x140022ac5  call    LuafvFreePool
0x140022aca  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140022ace  call    cs:__imp_ZwClose
0x140022ad5  nop     dword ptr [rax+rax+00h]
0x140022ada  mov     eax, ebx
0x140022adc  mov     rbx, [rsp+0E0h+arg_0]
0x140022ae4  add     rsp, 0C0h
0x140022aeb  pop     r14
0x140022aed  pop     r13
0x140022aef  pop     rdi
0x140022af0  pop     rsi
0x140022af1  pop     rbp
0x140022af2  retn
```
