# GetUserDesktopPath

- ea: `0x140005370`
- end: `0x140005615`
- name: `GetUserDesktopPath`
- size: `677`
- prototype: `__int64 __fastcall(void *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140001f7c`

## callees

- `0x140005370`
- `0x140005d00`
- `0x14001b650`
- `0x14001dd40`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400053d9`
- `ntoskrnl!ZwOpenKey` at `0x1400053d9`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400054cf`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000551f`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400054cf`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000551f`
- `ntoskrnl!ZwQueryValueKey` at `0x140005431`
- `ntoskrnl!ZwQueryValueKey` at `0x140005431`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005594`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005594`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140005580`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140005580`
- `ntoskrnl!ZwClose` at `0x1400055ef`
- `ntoskrnl!ZwClose` at `0x1400055ef`

## pseudocode

```c
__int64 __fastcall GetUserDesktopPath(void *a1, __int64 a2)
{
  __int64 Pool; // rdi
  NTSTATUS appended; // ebx
  __int64 v5; // r8
  ULONG Length; // ebx
  NTSTATUS v7; // eax
  __int64 v8; // r8
  WCHAR *v9; // rax
  __int64 v10; // r8
  __int64 v11; // rdx
  unsigned __int16 v12; // dx
  UNICODE_STRING Source; // [rsp+30h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-19h] BYREF
  UNICODE_STRING String2; // [rsp+50h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF
  ULONG ResultLength; // [rsp+C0h] [rbp+67h] BYREF
  void *KeyHandle; // [rsp+D0h] [rbp+77h] BYREF

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
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  appended = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( appended < 0 )
    goto LABEL_20;
  for ( Length = 532; ; Length = ResultLength )
  {
    LOBYTE(v5) = 1;
    Pool = LuafvAllocatePool(1, Length, v5);
    if ( !Pool )
      goto LABEL_19;
    v7 = ZwQueryValueKey(KeyHandle, &DesktopFolderValue, KeyValuePartialInformation, (PVOID)Pool, Length, &ResultLength);
    appended = v7;
    if ( v7 >= 0 )
      break;
    if ( v7 != -1073741789 && v7 != -2147483643 )
      goto LABEL_20;
    LuafvFreePool(Pool);
  }
  if ( (unsigned int)(*(_DWORD *)(Pool + 4) - 1) > 1 )
  {
    appended = -1073741788;
    goto LABEL_20;
  }
  LOBYTE(v8) = 2;
  String2.Length = *(_WORD *)(Pool + 8) - 2;
  String2.MaximumLength = *(_WORD *)(Pool + 8);
  v9 = (WCHAR *)LuafvAllocatePool(1, String2.Length, v8);
  String2.Buffer = v9;
  if ( !v9 )
    goto LABEL_19;
  memmove(v9, (const void *)(Pool + 12), String2.Length);
  Source = String2;
  if ( RtlPrefixUnicodeString(&UserProfileEnvironmentString, &String2, 1u) )
  {
    Source.Length -= UserProfileEnvironmentString.Length;
    Source.MaximumLength -= UserProfileEnvironmentString.Length;
    v11 = (unsigned __int16)(*(_WORD *)(a2 + 120) + Source.MaximumLength);
    Source.Buffer += (unsigned __int64)UserProfileEnvironmentString.Length >> 1;
  }
  else
  {
    if ( !RtlPrefixUnicodeString((PCUNICODE_STRING)(a2 + 104), &String2, 1u) )
      goto LABEL_17;
    v12 = *(_WORD *)(a2 + 104);
    Source.Length -= v12;
    Source.Buffer += (unsigned __int64)v12 >> 1;
    Source.MaximumLength -= v12;
    v11 = (unsigned __int16)(*(_WORD *)(a2 + 120) + Source.MaximumLength);
  }
  DestinationString.MaximumLength = v11;
  LOBYTE(v10) = 2;
  DestinationString.Length = 0;
  DestinationString.Buffer = (PWSTR)LuafvAllocatePool(1, v11, v10);
  if ( !DestinationString.Buffer )
  {
LABEL_19:
    appended = -1073741670;
    goto LABEL_20;
  }
  RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(a2 + 120));
  appended = RtlAppendUnicodeStringToString(&DestinationString, &Source);
  if ( appended < 0 )
    goto LABEL_20;
LABEL_17:
  *(struct _UNICODE_STRING *)(a2 + 152) = DestinationString;
  if ( appended >= 0 )
    goto LABEL_23;
LABEL_20:
  if ( DestinationString.Buffer )
    LuafvFreePool(DestinationString.Buffer);
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
0x140005370  mov     [rsp-8+arg_8], rbx
0x140005375  push    rbp
0x140005376  push    rsi
0x140005377  push    rdi
0x140005378  push    r13
0x14000537a  push    r14
0x14000537c  lea     rbp, [rsp-37h]
0x140005381  sub     rsp, 90h
0x140005388  xor     eax, eax
0x14000538a  mov     [rbp+57h+ObjectAttributes.RootDirectory], rcx
0x14000538e  xorps   xmm0, xmm0
0x140005391  mov     [rbp+57h+arg_0], eax
0x140005394  mov     [rbp+57h+KeyHandle], rax
0x140005398  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000539c  lea     rax, UserShellFoldersPath
0x1400053a3  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400053ab  mov     rsi, rdx
0x1400053ae  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400053b2  xorps   xmm1, xmm1
0x1400053b5  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400053bd  mov     edx, 20019h; DesiredAccess
0x1400053c2  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400053c6  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400053ca  xor     edi, edi
0x1400053cc  movups  xmmword ptr [rbp+57h+String2.Length], xmm1
0x1400053d0  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x1400053d4  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400053d9  call    cs:__imp_ZwOpenKey
0x1400053e0  nop     dword ptr [rax+rax+00h]
0x1400053e5  mov     ebx, eax
0x1400053e7  test    eax, eax
0x1400053e9  js      loc_1400055BD
0x1400053ef  mov     ebx, 214h
0x1400053f4  lea     r13d, [rdi+2]
0x1400053f8  mov     r8b, 1
0x1400053fb  mov     edx, ebx
0x1400053fd  mov     ecx, 1
0x140005402  call    LuafvAllocatePool
0x140005407  mov     rdi, rax
0x14000540a  test    rax, rax
0x14000540d  jz      loc_1400055B8
0x140005413  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140005417  lea     rax, [rbp+57h+arg_0]
0x14000541b  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x140005420  lea     rdx, DesktopFolderValue; ValueName
0x140005427  mov     r9, rdi; KeyValueInformation
0x14000542a  mov     [rsp+0B0h+Length], ebx; Length
0x14000542e  mov     r8d, r13d; KeyValueInformationClass
0x140005431  call    cs:__imp_ZwQueryValueKey
0x140005438  nop     dword ptr [rax+rax+00h]
0x14000543d  mov     ebx, eax
0x14000543f  test    eax, eax
0x140005441  jns     short loc_140005462
0x140005443  cmp     eax, 0C0000023h
0x140005448  jz      short loc_140005455
0x14000544a  cmp     eax, 80000005h
0x14000544f  jnz     loc_1400055BD
0x140005455  mov     rcx, rdi
0x140005458  call    LuafvFreePool
0x14000545d  mov     ebx, [rbp+57h+arg_0]
0x140005460  jmp     short loc_1400053F8
0x140005462  mov     eax, [rdi+4]
0x140005465  dec     eax
0x140005467  cmp     eax, 1
0x14000546a  jbe     short loc_140005476
0x14000546c  mov     ebx, 0C0000024h
0x140005471  jmp     loc_1400055BD
0x140005476  movzx   eax, word ptr [rdi+8]
0x14000547a  mov     r8b, r13b
0x14000547d  sub     ax, r13w
0x140005481  mov     ecx, 1
0x140005486  movzx   edx, ax
0x140005489  mov     [rbp+57h+String2.Length], dx
0x14000548d  movzx   eax, word ptr [rdi+8]
0x140005491  mov     [rbp+57h+String2.MaximumLength], ax
0x140005495  call    LuafvAllocatePool
0x14000549a  mov     [rbp+57h+String2.Buffer], rax
0x14000549e  test    rax, rax
0x1400054a1  jz      loc_1400055B8
0x1400054a7  movzx   r8d, [rbp+57h+String2.Length]; Size
0x1400054ac  lea     rdx, [rdi+0Ch]; Src
0x1400054b0  mov     rcx, rax; void *
0x1400054b3  call    memmove
0x1400054b8  movaps  xmm0, xmmword ptr [rbp+57h+String2.Length]
0x1400054bc  lea     rdx, [rbp+57h+String2]; String2
0x1400054c0  mov     r8b, 1; CaseInSensitive
0x1400054c3  movdqa  xmmword ptr [rbp+57h+Source.Length], xmm0
0x1400054c8  lea     rcx, UserProfileEnvironmentString; String1
0x1400054cf  call    cs:__imp_RtlPrefixUnicodeString
0x1400054d6  nop     dword ptr [rax+rax+00h]
0x1400054db  test    al, al
0x1400054dd  jz      short loc_140005514
0x1400054df  movzx   edx, cs:UserProfileEnvironmentString.Length
0x1400054e6  mov     rax, [rbp+57h+Source.Buffer]
0x1400054ea  mov     ecx, edx
0x1400054ec  movzx   r9d, [rbp+57h+Source.MaximumLength]
0x1400054f1  sub     [rbp+57h+Source.Length], dx
0x1400054f5  sub     r9w, dx
0x1400054f9  shr     rcx, 1
0x1400054fc  mov     [rbp+57h+Source.MaximumLength], r9w
0x140005501  add     r9w, [rsi+78h]
0x140005506  movzx   edx, r9w
0x14000550a  lea     rcx, [rax+rcx*2]
0x14000550e  mov     [rbp+57h+Source.Buffer], rcx
0x140005512  jmp     short loc_14000555A
0x140005514  mov     r8b, 1; CaseInSensitive
0x140005517  lea     rdx, [rbp+57h+String2]; String2
0x14000551b  lea     rcx, [rsi+68h]; String1
0x14000551f  call    cs:__imp_RtlPrefixUnicodeString
0x140005526  nop     dword ptr [rax+rax+00h]
0x14000552b  test    al, al
0x14000552d  jz      short loc_1400055A6
0x14000552f  movzx   edx, word ptr [rsi+68h]
0x140005533  mov     rax, [rbp+57h+Source.Buffer]
0x140005537  mov     ecx, edx
0x140005539  sub     [rbp+57h+Source.Length], dx
0x14000553d  shr     rcx, 1
0x140005540  lea     rcx, [rax+rcx*2]
0x140005544  mov     [rbp+57h+Source.Buffer], rcx
0x140005548  movzx   ecx, [rbp+57h+Source.MaximumLength]
0x14000554c  sub     cx, dx
0x14000554f  mov     [rbp+57h+Source.MaximumLength], cx
0x140005553  add     cx, [rsi+78h]
0x140005557  movzx   edx, cx
0x14000555a  xor     eax, eax
0x14000555c  mov     [rbp+57h+DestinationString.MaximumLength], dx
0x140005560  mov     r8b, r13b
0x140005563  mov     [rbp+57h+DestinationString.Length], ax
0x140005567  lea     ecx, [rax+1]
0x14000556a  call    LuafvAllocatePool
0x14000556f  mov     [rbp+57h+DestinationString.Buffer], rax
0x140005573  test    rax, rax
0x140005576  jz      short loc_1400055B8
0x140005578  lea     rdx, [rsi+78h]; SourceString
0x14000557c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140005580  call    cs:__imp_RtlCopyUnicodeString
0x140005587  nop     dword ptr [rax+rax+00h]
0x14000558c  lea     rdx, [rbp+57h+Source]; Source
0x140005590  lea     rcx, [rbp+57h+DestinationString]; Destination
0x140005594  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000559b  nop     dword ptr [rax+rax+00h]
0x1400055a0  mov     ebx, eax
0x1400055a2  test    eax, eax
0x1400055a4  js      short loc_1400055BD
0x1400055a6  movups  xmm0, xmmword ptr [rbp+57h+DestinationString.Length]
0x1400055aa  movdqu  xmmword ptr [rsi+98h], xmm0
0x1400055b2  test    ebx, ebx
0x1400055b4  jns     short loc_1400055D0
0x1400055b6  jmp     short loc_1400055BD
0x1400055b8  mov     ebx, 0C000009Ah
0x1400055bd  mov     rcx, [rbp+57h+DestinationString.Buffer]
0x1400055c1  test    rcx, rcx
0x1400055c4  jz      short loc_1400055CB
0x1400055c6  call    LuafvFreePool
0x1400055cb  test    rdi, rdi
0x1400055ce  jz      short loc_1400055D8
0x1400055d0  mov     rcx, rdi
0x1400055d3  call    LuafvFreePool
0x1400055d8  mov     rcx, [rbp+57h+String2.Buffer]
0x1400055dc  test    rcx, rcx
0x1400055df  jz      short loc_1400055E6
0x1400055e1  call    LuafvFreePool
0x1400055e6  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400055ea  test    rcx, rcx
0x1400055ed  jz      short loc_1400055FB
0x1400055ef  call    cs:__imp_ZwClose
0x1400055f6  nop     dword ptr [rax+rax+00h]
0x1400055fb  mov     eax, ebx
0x1400055fd  mov     rbx, [rsp+0B0h+arg_8]
0x140005605  add     rsp, 90h
0x14000560c  pop     r14
0x14000560e  pop     r13
0x140005610  pop     rdi
0x140005611  pop     rsi
0x140005612  pop     rbp
0x140005613  retn
```
