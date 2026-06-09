# GetUserDesktopPath

- ea: `0x1400054e8`
- end: `0x14000578f`
- name: `GetUserDesktopPath`
- size: `679`
- prototype: `__int64 __fastcall(void *, const UNICODE_STRING *, const UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400058cc`

## callees

- `0x1400054e8`
- `0x140006080`
- `0x14001b6a0`
- `0x14001dd90`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140005558`
- `ntoskrnl!ZwOpenKey` at `0x140005558`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140005651`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000569e`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140005651`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000569e`
- `ntoskrnl!ZwQueryValueKey` at `0x1400055af`
- `ntoskrnl!ZwQueryValueKey` at `0x1400055af`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005711`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005711`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400056fd`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400056fd`
- `ntoskrnl!ZwClose` at `0x140005770`
- `ntoskrnl!ZwClose` at `0x140005770`

## pseudocode

```c
__int64 __fastcall GetUserDesktopPath(
        void *a1,
        const UNICODE_STRING *a2,
        const UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4)
{
  __int64 Pool; // rdi
  NTSTATUS appended; // ebx
  __int64 v9; // r8
  ULONG Length; // ebx
  NTSTATUS v11; // eax
  __int64 v12; // r8
  WCHAR *v13; // rax
  __int64 v14; // r8
  __int64 v15; // rdx
  USHORT v16; // dx
  unsigned __int64 v17; // rcx
  void *KeyHandle; // [rsp+30h] [rbp-49h] BYREF
  UNICODE_STRING Source; // [rsp+40h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-29h] BYREF
  UNICODE_STRING String2; // [rsp+60h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-9h] BYREF
  ULONG ResultLength; // [rsp+E0h] [rbp+67h] BYREF

  ObjectAttributes.RootDirectory = a1;
  ResultLength = 0;
  KeyHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&UserShellFoldersPath;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  DestinationString = 0;
  Pool = 0;
  String2 = 0;
  Source = 0;
  *a4 = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  appended = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( appended < 0 )
    goto LABEL_20;
  for ( Length = 532; ; Length = ResultLength )
  {
    LOBYTE(v9) = 1;
    Pool = LuafvAllocatePool(1, Length, v9);
    if ( !Pool )
      goto LABEL_19;
    v11 = ZwQueryValueKey(
            KeyHandle,
            &DesktopFolderValue,
            KeyValuePartialInformation,
            (PVOID)Pool,
            Length,
            &ResultLength);
    appended = v11;
    if ( v11 >= 0 )
      break;
    if ( v11 != -1073741789 && v11 != -2147483643 )
      goto LABEL_20;
    LuafvFreePool(Pool);
  }
  if ( (unsigned int)(*(_DWORD *)(Pool + 4) - 1) > 1 )
  {
    appended = -1073741788;
    goto LABEL_20;
  }
  LOBYTE(v12) = 2;
  String2.Length = *(_WORD *)(Pool + 8) - 2;
  String2.MaximumLength = *(_WORD *)(Pool + 8);
  v13 = (WCHAR *)LuafvAllocatePool(1, String2.Length, v12);
  String2.Buffer = v13;
  if ( !v13 )
    goto LABEL_19;
  memmove(v13, (const void *)(Pool + 12), String2.Length);
  Source = String2;
  if ( RtlPrefixUnicodeString(&UserProfileEnvironmentString, &String2, 1u) )
  {
    Source.Length -= UserProfileEnvironmentString.Length;
    Source.Buffer += (unsigned __int64)UserProfileEnvironmentString.Length >> 1;
    Source.MaximumLength -= UserProfileEnvironmentString.Length;
    v15 = (unsigned __int16)(a2->Length + Source.MaximumLength);
  }
  else
  {
    if ( !RtlPrefixUnicodeString(a3, &String2, 1u) )
      goto LABEL_17;
    v16 = a3->Length;
    v17 = a3->Length;
    Source.Length -= a3->Length;
    Source.Buffer += v17 >> 1;
    Source.MaximumLength -= v16;
    v15 = (unsigned __int16)(a2->Length + Source.MaximumLength);
  }
  DestinationString.MaximumLength = v15;
  LOBYTE(v14) = 2;
  DestinationString.Length = 0;
  DestinationString.Buffer = (PWSTR)LuafvAllocatePool(1, v15, v14);
  if ( !DestinationString.Buffer )
  {
LABEL_19:
    appended = -1073741670;
    goto LABEL_20;
  }
  RtlCopyUnicodeString(&DestinationString, a2);
  appended = RtlAppendUnicodeStringToString(&DestinationString, &Source);
  if ( appended < 0 )
    goto LABEL_20;
LABEL_17:
  *a4 = DestinationString;
  if ( appended >= 0 )
    goto LABEL_23;
LABEL_20:
  if ( DestinationString.Buffer )
    LuafvFreePool(DestinationString.Buffer);
  *a4 = 0;
  if ( Pool )
LABEL_23:
    LuafvFreePool(Pool);
  if ( String2.Buffer )
    LuafvFreePool(String2.Buffer);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1400054e8  push    rbp
0x1400054ea  push    rbx
0x1400054eb  push    rsi
0x1400054ec  push    rdi
0x1400054ed  push    r14
0x1400054ef  push    r15
0x1400054f1  lea     rbp, [rsp-2Fh]
0x1400054f6  sub     rsp, 0A8h
0x1400054fd  xor     eax, eax
0x1400054ff  mov     [rbp+57h+ObjectAttributes.RootDirectory], rcx
0x140005503  xorps   xmm0, xmm0
0x140005506  mov     [rbp+57h+arg_0], eax
0x140005509  xorps   xmm1, xmm1
0x14000550c  mov     [rbp+57h+KeyHandle], rax
0x140005510  lea     rax, UserShellFoldersPath
0x140005517  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000551f  mov     r15, r8
0x140005522  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140005526  mov     rsi, rdx
0x140005529  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140005531  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140005535  mov     edx, 20019h; DesiredAccess
0x14000553a  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000553e  mov     r14, r9
0x140005541  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140005545  xor     edi, edi
0x140005547  movups  xmmword ptr [rbp+57h+String2.Length], xmm1
0x14000554b  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x14000554f  movups  xmmword ptr [r9], xmm1
0x140005553  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140005558  call    cs:__imp_ZwOpenKey
0x14000555f  nop     dword ptr [rax+rax+00h]
0x140005564  mov     ebx, eax
0x140005566  test    eax, eax
0x140005568  js      loc_140005737
0x14000556e  mov     ebx, 214h
0x140005573  mov     r8b, 1
0x140005576  mov     edx, ebx
0x140005578  mov     ecx, 1
0x14000557d  call    LuafvAllocatePool
0x140005582  mov     rdi, rax
0x140005585  test    rax, rax
0x140005588  jz      loc_140005732
0x14000558e  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140005592  lea     rax, [rbp+57h+arg_0]
0x140005596  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x14000559b  lea     rdx, DesktopFolderValue; ValueName
0x1400055a2  mov     r9, rdi; KeyValueInformation
0x1400055a5  mov     [rsp+0D0h+Length], ebx; Length
0x1400055a9  mov     r8d, 2; KeyValueInformationClass
0x1400055af  call    cs:__imp_ZwQueryValueKey
0x1400055b6  nop     dword ptr [rax+rax+00h]
0x1400055bb  mov     ebx, eax
0x1400055bd  test    eax, eax
0x1400055bf  jns     short loc_1400055E0
0x1400055c1  cmp     eax, 0C0000023h
0x1400055c6  jz      short loc_1400055D3
0x1400055c8  cmp     eax, 80000005h
0x1400055cd  jnz     loc_140005737
0x1400055d3  mov     rcx, rdi
0x1400055d6  call    LuafvFreePool
0x1400055db  mov     ebx, [rbp+57h+arg_0]
0x1400055de  jmp     short loc_140005573
0x1400055e0  mov     eax, [rdi+4]
0x1400055e3  dec     eax
0x1400055e5  cmp     eax, 1
0x1400055e8  jbe     short loc_1400055F4
0x1400055ea  mov     ebx, 0C0000024h
0x1400055ef  jmp     loc_140005737
0x1400055f4  movzx   eax, word ptr [rdi+8]
0x1400055f8  mov     ecx, 2
0x1400055fd  sub     ax, cx
0x140005600  mov     r8b, cl
0x140005603  movzx   edx, ax
0x140005606  mov     ecx, 1
0x14000560b  mov     [rbp+57h+String2.Length], dx
0x14000560f  movzx   eax, word ptr [rdi+8]
0x140005613  mov     [rbp+57h+String2.MaximumLength], ax
0x140005617  call    LuafvAllocatePool
0x14000561c  mov     [rbp+57h+String2.Buffer], rax
0x140005620  test    rax, rax
0x140005623  jz      loc_140005732
0x140005629  movzx   r8d, [rbp+57h+String2.Length]; Size
0x14000562e  lea     rdx, [rdi+0Ch]; Src
0x140005632  mov     rcx, rax; void *
0x140005635  call    memmove
0x14000563a  movaps  xmm0, xmmword ptr [rbp+57h+String2.Length]
0x14000563e  lea     rdx, [rbp+57h+String2]; String2
0x140005642  mov     r8b, 1; CaseInSensitive
0x140005645  movdqa  xmmword ptr [rbp+57h+Source.Length], xmm0
0x14000564a  lea     rcx, UserProfileEnvironmentString; String1
0x140005651  call    cs:__imp_RtlPrefixUnicodeString
0x140005658  nop     dword ptr [rax+rax+00h]
0x14000565d  test    al, al
0x14000565f  jz      short loc_140005694
0x140005661  movzx   r9d, cs:UserProfileEnvironmentString.Length
0x140005669  mov     rax, [rbp+57h+Source.Buffer]
0x14000566d  mov     ecx, r9d
0x140005670  sub     [rbp+57h+Source.Length], r9w
0x140005675  shr     rcx, 1
0x140005678  lea     rdx, [rax+rcx*2]
0x14000567c  mov     [rbp+57h+Source.Buffer], rdx
0x140005680  movzx   edx, [rbp+57h+Source.MaximumLength]
0x140005684  sub     dx, r9w
0x140005688  mov     [rbp+57h+Source.MaximumLength], dx
0x14000568c  add     dx, [rsi]
0x14000568f  movzx   edx, dx
0x140005692  jmp     short loc_1400056D8
0x140005694  mov     r8b, 1; CaseInSensitive
0x140005697  lea     rdx, [rbp+57h+String2]; String2
0x14000569b  mov     rcx, r15; String1
0x14000569e  call    cs:__imp_RtlPrefixUnicodeString
0x1400056a5  nop     dword ptr [rax+rax+00h]
0x1400056aa  test    al, al
0x1400056ac  jz      short loc_140005723
0x1400056ae  movzx   edx, word ptr [r15]
0x1400056b2  mov     rax, [rbp+57h+Source.Buffer]
0x1400056b6  mov     ecx, edx
0x1400056b8  sub     [rbp+57h+Source.Length], dx
0x1400056bc  shr     rcx, 1
0x1400056bf  lea     rcx, [rax+rcx*2]
0x1400056c3  mov     [rbp+57h+Source.Buffer], rcx
0x1400056c7  movzx   ecx, [rbp+57h+Source.MaximumLength]
0x1400056cb  sub     cx, dx
0x1400056ce  mov     [rbp+57h+Source.MaximumLength], cx
0x1400056d2  add     cx, [rsi]
0x1400056d5  movzx   edx, cx
0x1400056d8  xor     eax, eax
0x1400056da  mov     [rbp+57h+DestinationString.MaximumLength], dx
0x1400056de  mov     r8b, 2
0x1400056e1  mov     [rbp+57h+DestinationString.Length], ax
0x1400056e5  lea     ecx, [rax+1]
0x1400056e8  call    LuafvAllocatePool
0x1400056ed  mov     [rbp+57h+DestinationString.Buffer], rax
0x1400056f1  test    rax, rax
0x1400056f4  jz      short loc_140005732
0x1400056f6  mov     rdx, rsi; SourceString
0x1400056f9  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400056fd  call    cs:__imp_RtlCopyUnicodeString
0x140005704  nop     dword ptr [rax+rax+00h]
0x140005709  lea     rdx, [rbp+57h+Source]; Source
0x14000570d  lea     rcx, [rbp+57h+DestinationString]; Destination
0x140005711  call    cs:__imp_RtlAppendUnicodeStringToString
0x140005718  nop     dword ptr [rax+rax+00h]
0x14000571d  mov     ebx, eax
0x14000571f  test    eax, eax
0x140005721  js      short loc_140005737
0x140005723  movups  xmm0, xmmword ptr [rbp+57h+DestinationString.Length]
0x140005727  movdqu  xmmword ptr [r14], xmm0
0x14000572c  test    ebx, ebx
0x14000572e  jns     short loc_140005751
0x140005730  jmp     short loc_140005737
0x140005732  mov     ebx, 0C000009Ah
0x140005737  mov     rcx, [rbp+57h+DestinationString.Buffer]
0x14000573b  test    rcx, rcx
0x14000573e  jz      short loc_140005745
0x140005740  call    LuafvFreePool
0x140005745  xorps   xmm0, xmm0
0x140005748  movups  xmmword ptr [r14], xmm0
0x14000574c  test    rdi, rdi
0x14000574f  jz      short loc_140005759
0x140005751  mov     rcx, rdi
0x140005754  call    LuafvFreePool
0x140005759  mov     rcx, [rbp+57h+String2.Buffer]
0x14000575d  test    rcx, rcx
0x140005760  jz      short loc_140005767
0x140005762  call    LuafvFreePool
0x140005767  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14000576b  test    rcx, rcx
0x14000576e  jz      short loc_14000577C
0x140005770  call    cs:__imp_ZwClose
0x140005777  nop     dword ptr [rax+rax+00h]
0x14000577c  mov     eax, ebx
0x14000577e  add     rsp, 0A8h
0x140005785  pop     r15
0x140005787  pop     r14
0x140005789  pop     rdi
0x14000578a  pop     rsi
0x14000578b  pop     rbx
0x14000578c  pop     rbp
0x14000578d  retn
```
