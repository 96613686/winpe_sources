# ConvertDosPathToNtPath

- ea: `0x140005034`
- end: `0x140005368`
- name: `ConvertDosPathToNtPath`
- size: `820`
- prototype: `__int64 __fastcall(UNICODE_STRING *, struct _UNICODE_STRING *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400045f4`
- `0x140005800`

## callees

- `0x140005034`
- `0x14001b650`
- `0x14001dd40`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400050bf`
- `ntoskrnl!RtlCompareMemory` at `0x1400050bf`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x1400051cf`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140005231`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x1400051cf`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140005231`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000516a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005322`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000516a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005322`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x1400051ad`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x1400051ad`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140005156`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000530e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140005156`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000530e`
- `ntoskrnl!ZwClose` at `0x1400052b1`
- `ntoskrnl!ZwClose` at `0x1400052b1`

## pseudocode

```c
__int64 __fastcall ConvertDosPathToNtPath(UNICODE_STRING *a1, struct _UNICODE_STRING *a2, __int64 a3)
{
  USHORT Length; // cx
  PWSTR Buffer; // rax
  int v7; // r14d
  WCHAR *Pool; // rsi
  NTSTATUS appended; // ebx
  __int64 v11; // r8
  USHORT v12; // bx
  __int16 v13; // ax
  __int16 v14; // cx
  UNICODE_STRING v15; // [rsp+20h] [rbp-49h] BYREF
  struct _UNICODE_STRING LinkTarget; // [rsp+30h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-29h] BYREF
  UNICODE_STRING Source; // [rsp+50h] [rbp-19h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+60h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+7h] BYREF
  ULONG ReturnedLength; // [rsp+D0h] [rbp+67h] BYREF
  void *LinkHandle; // [rsp+E0h] [rbp+77h] BYREF

  ReturnedLength = 0;
  LinkHandle = 0;
  LinkTarget = 0;
  DestinationString = 0;
  Source = 0;
  memset(&ObjectAttributes, 0, 44);
  v15 = 0;
  Destination = 0;
  if ( !a1 || a1->Length < 4u )
    return 3221225485LL;
  if ( a1->Length > 6u && RtlCompareMemory(a1->Buffer, L"\\??\\", 6u) == 6 )
  {
    Length = a1->Length;
    if ( a1->Length >= 0xCu )
    {
      Buffer = a1->Buffer;
      if ( Buffer[5] == 58 )
      {
        v7 = 1;
        Source.Buffer = Buffer + 4;
        Source.MaximumLength = Length - 8;
        goto LABEL_10;
      }
    }
    return 3221225485LL;
  }
  v7 = 0;
  if ( a1->Buffer[1] != 58 )
    return 3221225485LL;
  Source = *a1;
LABEL_10:
  Source.Length = 4;
  LOBYTE(a3) = 1;
  *(_DWORD *)&DestinationString.Length = 1835036;
  DestinationString.Buffer = (PWSTR)LuafvAllocatePool(1, 28, a3);
  if ( !DestinationString.Buffer )
    return 3221225626LL;
  Pool = 0;
  RtlCopyUnicodeString(&DestinationString, &DosDevicesPrefix);
  appended = RtlAppendUnicodeStringToString(&DestinationString, &Source);
  if ( appended < 0 )
    goto LABEL_24;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  appended = ZwOpenSymbolicLinkObject(&LinkHandle, 1u, &ObjectAttributes);
  if ( appended < 0 )
    goto LABEL_24;
  appended = ZwQuerySymbolicLinkObject(LinkHandle, &LinkTarget, &ReturnedLength);
  if ( (int)(appended + 0x80000000) >= 0 && appended != -1073741789 )
    goto LABEL_24;
  if ( appended == -1073741789 )
  {
    LOBYTE(v11) = 1;
    LinkTarget.Buffer = (PWSTR)LuafvAllocatePool(1, ReturnedLength, v11);
    if ( !LinkTarget.Buffer )
    {
LABEL_18:
      appended = -1073741670;
      goto LABEL_24;
    }
    LinkTarget.Length = 0;
    LinkTarget.MaximumLength = ReturnedLength;
    appended = ZwQuerySymbolicLinkObject(LinkHandle, &LinkTarget, &ReturnedLength);
    if ( appended < 0 )
      goto LABEL_24;
  }
  LOBYTE(v11) = 2;
  v12 = LinkTarget.Length + a1->Length - Source.Length + 2;
  Pool = (WCHAR *)LuafvAllocatePool(1, v12, v11);
  if ( !Pool )
    goto LABEL_18;
  v13 = _mm_cvtsi128_si32(*(__m128i *)a1);
  v15 = *a1;
  if ( v13 == 4 )
  {
    appended = -1073741811;
  }
  else
  {
    if ( v7 )
    {
      v15.Buffer += 6;
      v14 = -12;
    }
    else
    {
      v15.Buffer += 2;
      v14 = -4;
    }
    v15.Length = v14 + v13;
    *(_QWORD *)&Destination.Length = 0;
    Destination.MaximumLength = v12;
    Destination.Buffer = Pool;
    v15.MaximumLength = v14 + v13;
    RtlCopyUnicodeString(&Destination, &LinkTarget);
    appended = RtlAppendUnicodeStringToString(&Destination, &v15);
    if ( appended >= 0 )
    {
      *a2 = Destination;
      goto LABEL_24;
    }
  }
  LuafvFreePool(Pool);
LABEL_24:
  if ( DestinationString.Buffer )
    LuafvFreePool(DestinationString.Buffer);
  if ( LinkTarget.Buffer )
    LuafvFreePool(LinkTarget.Buffer);
  if ( LinkHandle )
    ZwClose(LinkHandle);
  if ( appended < 0 )
  {
    if ( Pool )
      LuafvFreePool(Pool);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140005034  mov     [rsp-8+arg_8], rbx
0x140005039  mov     [rsp-8+arg_18], rsi
0x14000503e  push    rbp
0x14000503f  push    rdi
0x140005040  push    r13
0x140005042  push    r14
0x140005044  push    r15
0x140005046  lea     rbp, [rsp-37h]
0x14000504b  sub     rsp, 0A0h
0x140005052  xorps   xmm0, xmm0
0x140005055  xor     eax, eax
0x140005057  mov     [rbp+57h+ReturnedLength], eax
0x14000505a  xorps   xmm1, xmm1
0x14000505d  mov     [rbp+57h+LinkHandle], rax
0x140005061  mov     r15, rdx
0x140005064  mov     rdi, rcx
0x140005067  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14000506b  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14000506f  movups  xmmword ptr [rbp+57h+LinkTarget.Length], xmm0
0x140005073  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x140005077  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x14000507b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14000507f  movups  xmmword ptr [rbp+57h+var_A0.Length], xmm0
0x140005083  movups  xmmword ptr [rbp+57h+Destination.Length], xmm1
0x140005087  test    rcx, rcx
0x14000508a  jz      loc_140005346
0x140005090  movzx   eax, word ptr [rcx]
0x140005093  mov     esi, 4
0x140005098  cmp     ax, si
0x14000509b  jb      loc_140005346
0x1400050a1  lea     ebx, [rsi+2]
0x1400050a4  lea     r14d, [rsi+8]
0x1400050a8  lea     r13d, [rsi-3]
0x1400050ac  cmp     ax, bx
0x1400050af  jbe     short loc_140005101
0x1400050b1  mov     rcx, [rcx+8]; Source1
0x1400050b5  lea     rdx, asc_14000ABC8; "\\??\\"
0x1400050bc  mov     r8d, ebx; Length
0x1400050bf  call    cs:__imp_RtlCompareMemory
0x1400050c6  nop     dword ptr [rax+rax+00h]
0x1400050cb  cmp     rax, rbx
0x1400050ce  jnz     short loc_140005101
0x1400050d0  movzx   ecx, word ptr [rdi]
0x1400050d3  cmp     cx, r14w
0x1400050d7  jb      loc_140005346
0x1400050dd  mov     rax, [rdi+8]
0x1400050e1  cmp     word ptr [rax+0Ah], 3Ah ; ':'
0x1400050e6  jnz     loc_140005346
0x1400050ec  add     rax, 8
0x1400050f0  mov     r14d, r13d
0x1400050f3  sub     cx, 8
0x1400050f7  mov     [rbp+57h+Source.Buffer], rax
0x1400050fb  mov     [rbp+57h+Source.MaximumLength], cx
0x1400050ff  jmp     short loc_14000511B
0x140005101  mov     rax, [rdi+8]
0x140005105  xor     r14d, r14d
0x140005108  cmp     word ptr [rax+2], 3Ah ; ':'
0x14000510d  jnz     loc_140005346
0x140005113  movups  xmm0, xmmword ptr [rdi]
0x140005116  movdqu  xmmword ptr [rbp+57h+Source.Length], xmm0
0x14000511b  mov     edx, 1Ch
0x140005120  mov     [rbp+57h+Source.Length], si
0x140005124  mov     r8b, r13b
0x140005127  mov     dword ptr [rbp+57h+DestinationString.Length], 1C001Ch
0x14000512e  mov     ecx, r13d
0x140005131  call    LuafvAllocatePool
0x140005136  mov     [rbp+57h+DestinationString.Buffer], rax
0x14000513a  test    rax, rax
0x14000513d  jnz     short loc_140005149
0x14000513f  mov     eax, 0C000009Ah
0x140005144  jmp     loc_14000534B
0x140005149  lea     rdx, DosDevicesPrefix; SourceString
0x140005150  xor     esi, esi
0x140005152  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140005156  call    cs:__imp_RtlCopyUnicodeString
0x14000515d  nop     dword ptr [rax+rax+00h]
0x140005162  lea     rdx, [rbp+57h+Source]; Source
0x140005166  lea     rcx, [rbp+57h+DestinationString]; Destination
0x14000516a  call    cs:__imp_RtlAppendUnicodeStringToString
0x140005171  nop     dword ptr [rax+rax+00h]
0x140005176  mov     ebx, eax
0x140005178  test    eax, eax
0x14000517a  js      loc_14000528C
0x140005180  lea     rax, [rbp+57h+DestinationString]
0x140005184  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000518b  xorps   xmm0, xmm0
0x14000518e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140005192  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140005196  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x14000519a  mov     edx, r13d; DesiredAccess
0x14000519d  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400051a4  lea     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x1400051a8  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400051ad  call    cs:__imp_ZwOpenSymbolicLinkObject
0x1400051b4  nop     dword ptr [rax+rax+00h]
0x1400051b9  mov     ebx, eax
0x1400051bb  test    eax, eax
0x1400051bd  js      loc_14000528C
0x1400051c3  mov     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x1400051c7  lea     r8, [rbp+57h+ReturnedLength]; ReturnedLength
0x1400051cb  lea     rdx, [rbp+57h+LinkTarget]; LinkTarget
0x1400051cf  call    cs:__imp_ZwQuerySymbolicLinkObject
0x1400051d6  nop     dword ptr [rax+rax+00h]
0x1400051db  mov     ecx, 80000000h
0x1400051e0  mov     edx, 0C0000023h
0x1400051e5  mov     ebx, eax
0x1400051e7  add     eax, ecx
0x1400051e9  test    ecx, eax
0x1400051eb  jnz     short loc_1400051F5
0x1400051ed  cmp     ebx, edx
0x1400051ef  jnz     loc_14000528C
0x1400051f5  cmp     ebx, edx
0x1400051f7  jnz     short loc_140005243
0x1400051f9  mov     edx, [rbp+57h+ReturnedLength]
0x1400051fc  mov     r8b, r13b
0x1400051ff  mov     ecx, r13d
0x140005202  call    LuafvAllocatePool
0x140005207  mov     [rbp+57h+LinkTarget.Buffer], rax
0x14000520b  test    rax, rax
0x14000520e  jnz     short loc_140005217
0x140005210  mov     ebx, 0C000009Ah
0x140005215  jmp     short loc_14000528C
0x140005217  mov     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x14000521b  lea     r8, [rbp+57h+ReturnedLength]; ReturnedLength
0x14000521f  xor     eax, eax
0x140005221  lea     rdx, [rbp+57h+LinkTarget]; LinkTarget
0x140005225  mov     [rbp+57h+LinkTarget.Length], ax
0x140005229  movzx   eax, word ptr [rbp+57h+ReturnedLength]
0x14000522d  mov     [rbp+57h+LinkTarget.MaximumLength], ax
0x140005231  call    cs:__imp_ZwQuerySymbolicLinkObject
0x140005238  nop     dword ptr [rax+rax+00h]
0x14000523d  mov     ebx, eax
0x14000523f  test    eax, eax
0x140005241  js      short loc_14000528C
0x140005243  movzx   eax, word ptr [rdi]
0x140005246  mov     r8b, 2
0x140005249  sub     ax, [rbp+57h+Source.Length]
0x14000524d  mov     ecx, r13d
0x140005250  add     ax, 2
0x140005254  add     ax, [rbp+57h+LinkTarget.Length]
0x140005258  movzx   ebx, ax
0x14000525b  mov     edx, ebx
0x14000525d  call    LuafvAllocatePool
0x140005262  mov     rsi, rax
0x140005265  test    rax, rax
0x140005268  jz      short loc_140005210
0x14000526a  movups  xmm0, xmmword ptr [rdi]
0x14000526d  mov     ecx, 4
0x140005272  movd    eax, xmm0
0x140005276  movups  xmmword ptr [rbp+57h+var_A0.Length], xmm0
0x14000527a  cmp     ax, cx
0x14000527d  jnz     short loc_1400052D2
0x14000527f  mov     ebx, 0C000000Dh
0x140005284  mov     rcx, rsi
0x140005287  call    LuafvFreePool
0x14000528c  mov     rcx, [rbp+57h+DestinationString.Buffer]
0x140005290  test    rcx, rcx
0x140005293  jz      short loc_14000529A
0x140005295  call    LuafvFreePool
0x14000529a  mov     rcx, [rbp+57h+LinkTarget.Buffer]
0x14000529e  test    rcx, rcx
0x1400052a1  jz      short loc_1400052A8
0x1400052a3  call    LuafvFreePool
0x1400052a8  mov     rcx, [rbp+57h+LinkHandle]; Handle
0x1400052ac  test    rcx, rcx
0x1400052af  jz      short loc_1400052BD
0x1400052b1  call    cs:__imp_ZwClose
0x1400052b8  nop     dword ptr [rax+rax+00h]
0x1400052bd  test    ebx, ebx
0x1400052bf  jns     short loc_1400052CE
0x1400052c1  test    rsi, rsi
0x1400052c4  jz      short loc_1400052CE
0x1400052c6  mov     rcx, rsi
0x1400052c9  call    LuafvFreePool
0x1400052ce  mov     eax, ebx
0x1400052d0  jmp     short loc_14000534B
0x1400052d2  test    r14d, r14d
0x1400052d5  jz      short loc_1400052E3
0x1400052d7  add     [rbp+57h+var_A0.Buffer], 0Ch
0x1400052dc  mov     ecx, 0FFF4h
0x1400052e1  jmp     short loc_1400052EC
0x1400052e3  add     [rbp+57h+var_A0.Buffer], rcx
0x1400052e7  mov     ecx, 0FFFCh
0x1400052ec  add     ax, cx
0x1400052ef  lea     rdx, [rbp+57h+LinkTarget]; SourceString
0x1400052f3  xorps   xmm0, xmm0
0x1400052f6  mov     [rbp+57h+var_A0.Length], ax
0x1400052fa  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x1400052fe  lea     rcx, [rbp+57h+Destination]; DestinationString
0x140005302  mov     [rbp+57h+Destination.MaximumLength], bx
0x140005306  mov     [rbp+57h+Destination.Buffer], rsi
0x14000530a  mov     [rbp+57h+var_A0.MaximumLength], ax
0x14000530e  call    cs:__imp_RtlCopyUnicodeString
0x140005315  nop     dword ptr [rax+rax+00h]
0x14000531a  lea     rdx, [rbp+57h+var_A0]; Source
0x14000531e  lea     rcx, [rbp+57h+Destination]; Destination
0x140005322  call    cs:__imp_RtlAppendUnicodeStringToString
0x140005329  nop     dword ptr [rax+rax+00h]
0x14000532e  mov     ebx, eax
0x140005330  test    eax, eax
0x140005332  js      loc_140005284
0x140005338  movups  xmm0, xmmword ptr [rbp+57h+Destination.Length]
0x14000533c  movdqu  xmmword ptr [r15], xmm0
0x140005341  jmp     loc_14000528C
0x140005346  mov     eax, 0C000000Dh
0x14000534b  lea     r11, [rsp+0C0h+var_20]
0x140005353  mov     rbx, [r11+38h]
0x140005357  mov     rsi, [r11+48h]
0x14000535b  mov     rsp, r11
0x14000535e  pop     r15
0x140005360  pop     r14
0x140005362  pop     r13
0x140005364  pop     rdi
0x140005365  pop     rbp
0x140005366  retn
```
