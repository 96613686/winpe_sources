# ConvertDosPathToNtPath

- ea: `0x140004e6c`
- end: `0x1400051a0`
- name: `ConvertDosPathToNtPath`
- size: `820`
- prototype: `__int64 __fastcall(UNICODE_STRING *, struct _UNICODE_STRING *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400043c4`
- `0x140005b84`

## callees

- `0x140004e6c`
- `0x14001b6a0`
- `0x14001dd90`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140004ef7`
- `ntoskrnl!RtlCompareMemory` at `0x140004ef7`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140005007`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140005069`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140005007`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140005069`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140004fa2`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000515a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140004fa2`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000515a`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x140004fe5`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x140004fe5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140004f8e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140005146`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140004f8e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140005146`
- `ntoskrnl!ZwClose` at `0x1400050e9`
- `ntoskrnl!ZwClose` at `0x1400050e9`

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
0x140004e6c  mov     [rsp-8+arg_8], rbx
0x140004e71  mov     [rsp-8+arg_18], rsi
0x140004e76  push    rbp
0x140004e77  push    rdi
0x140004e78  push    r13
0x140004e7a  push    r14
0x140004e7c  push    r15
0x140004e7e  lea     rbp, [rsp-37h]
0x140004e83  sub     rsp, 0A0h
0x140004e8a  xorps   xmm0, xmm0
0x140004e8d  xor     eax, eax
0x140004e8f  mov     [rbp+57h+ReturnedLength], eax
0x140004e92  xorps   xmm1, xmm1
0x140004e95  mov     [rbp+57h+LinkHandle], rax
0x140004e99  mov     r15, rdx
0x140004e9c  mov     rdi, rcx
0x140004e9f  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140004ea3  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140004ea7  movups  xmmword ptr [rbp+57h+LinkTarget.Length], xmm0
0x140004eab  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x140004eaf  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x140004eb3  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140004eb7  movups  xmmword ptr [rbp+57h+var_A0.Length], xmm0
0x140004ebb  movups  xmmword ptr [rbp+57h+Destination.Length], xmm1
0x140004ebf  test    rcx, rcx
0x140004ec2  jz      loc_14000517E
0x140004ec8  movzx   eax, word ptr [rcx]
0x140004ecb  mov     esi, 4
0x140004ed0  cmp     ax, si
0x140004ed3  jb      loc_14000517E
0x140004ed9  lea     ebx, [rsi+2]
0x140004edc  lea     r14d, [rsi+8]
0x140004ee0  lea     r13d, [rsi-3]
0x140004ee4  cmp     ax, bx
0x140004ee7  jbe     short loc_140004F39
0x140004ee9  mov     rcx, [rcx+8]; Source1
0x140004eed  lea     rdx, asc_14000ABC8; "\\??\\"
0x140004ef4  mov     r8d, ebx; Length
0x140004ef7  call    cs:__imp_RtlCompareMemory
0x140004efe  nop     dword ptr [rax+rax+00h]
0x140004f03  cmp     rax, rbx
0x140004f06  jnz     short loc_140004F39
0x140004f08  movzx   ecx, word ptr [rdi]
0x140004f0b  cmp     cx, r14w
0x140004f0f  jb      loc_14000517E
0x140004f15  mov     rax, [rdi+8]
0x140004f19  cmp     word ptr [rax+0Ah], 3Ah ; ':'
0x140004f1e  jnz     loc_14000517E
0x140004f24  add     rax, 8
0x140004f28  mov     r14d, r13d
0x140004f2b  sub     cx, 8
0x140004f2f  mov     [rbp+57h+Source.Buffer], rax
0x140004f33  mov     [rbp+57h+Source.MaximumLength], cx
0x140004f37  jmp     short loc_140004F53
0x140004f39  mov     rax, [rdi+8]
0x140004f3d  xor     r14d, r14d
0x140004f40  cmp     word ptr [rax+2], 3Ah ; ':'
0x140004f45  jnz     loc_14000517E
0x140004f4b  movups  xmm0, xmmword ptr [rdi]
0x140004f4e  movdqu  xmmword ptr [rbp+57h+Source.Length], xmm0
0x140004f53  mov     edx, 1Ch
0x140004f58  mov     [rbp+57h+Source.Length], si
0x140004f5c  mov     r8b, r13b
0x140004f5f  mov     dword ptr [rbp+57h+DestinationString.Length], 1C001Ch
0x140004f66  mov     ecx, r13d
0x140004f69  call    LuafvAllocatePool
0x140004f6e  mov     [rbp+57h+DestinationString.Buffer], rax
0x140004f72  test    rax, rax
0x140004f75  jnz     short loc_140004F81
0x140004f77  mov     eax, 0C000009Ah
0x140004f7c  jmp     loc_140005183
0x140004f81  lea     rdx, DosDevicesPrefix; SourceString
0x140004f88  xor     esi, esi
0x140004f8a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140004f8e  call    cs:__imp_RtlCopyUnicodeString
0x140004f95  nop     dword ptr [rax+rax+00h]
0x140004f9a  lea     rdx, [rbp+57h+Source]; Source
0x140004f9e  lea     rcx, [rbp+57h+DestinationString]; Destination
0x140004fa2  call    cs:__imp_RtlAppendUnicodeStringToString
0x140004fa9  nop     dword ptr [rax+rax+00h]
0x140004fae  mov     ebx, eax
0x140004fb0  test    eax, eax
0x140004fb2  js      loc_1400050C4
0x140004fb8  lea     rax, [rbp+57h+DestinationString]
0x140004fbc  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140004fc3  xorps   xmm0, xmm0
0x140004fc6  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140004fca  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140004fce  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x140004fd2  mov     edx, r13d; DesiredAccess
0x140004fd5  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140004fdc  lea     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x140004fe0  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140004fe5  call    cs:__imp_ZwOpenSymbolicLinkObject
0x140004fec  nop     dword ptr [rax+rax+00h]
0x140004ff1  mov     ebx, eax
0x140004ff3  test    eax, eax
0x140004ff5  js      loc_1400050C4
0x140004ffb  mov     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x140004fff  lea     r8, [rbp+57h+ReturnedLength]; ReturnedLength
0x140005003  lea     rdx, [rbp+57h+LinkTarget]; LinkTarget
0x140005007  call    cs:__imp_ZwQuerySymbolicLinkObject
0x14000500e  nop     dword ptr [rax+rax+00h]
0x140005013  mov     ecx, 80000000h
0x140005018  mov     edx, 0C0000023h
0x14000501d  mov     ebx, eax
0x14000501f  add     eax, ecx
0x140005021  test    ecx, eax
0x140005023  jnz     short loc_14000502D
0x140005025  cmp     ebx, edx
0x140005027  jnz     loc_1400050C4
0x14000502d  cmp     ebx, edx
0x14000502f  jnz     short loc_14000507B
0x140005031  mov     edx, [rbp+57h+ReturnedLength]
0x140005034  mov     r8b, r13b
0x140005037  mov     ecx, r13d
0x14000503a  call    LuafvAllocatePool
0x14000503f  mov     [rbp+57h+LinkTarget.Buffer], rax
0x140005043  test    rax, rax
0x140005046  jnz     short loc_14000504F
0x140005048  mov     ebx, 0C000009Ah
0x14000504d  jmp     short loc_1400050C4
0x14000504f  mov     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x140005053  lea     r8, [rbp+57h+ReturnedLength]; ReturnedLength
0x140005057  xor     eax, eax
0x140005059  lea     rdx, [rbp+57h+LinkTarget]; LinkTarget
0x14000505d  mov     [rbp+57h+LinkTarget.Length], ax
0x140005061  movzx   eax, word ptr [rbp+57h+ReturnedLength]
0x140005065  mov     [rbp+57h+LinkTarget.MaximumLength], ax
0x140005069  call    cs:__imp_ZwQuerySymbolicLinkObject
0x140005070  nop     dword ptr [rax+rax+00h]
0x140005075  mov     ebx, eax
0x140005077  test    eax, eax
0x140005079  js      short loc_1400050C4
0x14000507b  movzx   eax, word ptr [rdi]
0x14000507e  mov     r8b, 2
0x140005081  sub     ax, [rbp+57h+Source.Length]
0x140005085  mov     ecx, r13d
0x140005088  add     ax, 2
0x14000508c  add     ax, [rbp+57h+LinkTarget.Length]
0x140005090  movzx   ebx, ax
0x140005093  mov     edx, ebx
0x140005095  call    LuafvAllocatePool
0x14000509a  mov     rsi, rax
0x14000509d  test    rax, rax
0x1400050a0  jz      short loc_140005048
0x1400050a2  movups  xmm0, xmmword ptr [rdi]
0x1400050a5  mov     ecx, 4
0x1400050aa  movd    eax, xmm0
0x1400050ae  movups  xmmword ptr [rbp+57h+var_A0.Length], xmm0
0x1400050b2  cmp     ax, cx
0x1400050b5  jnz     short loc_14000510A
0x1400050b7  mov     ebx, 0C000000Dh
0x1400050bc  mov     rcx, rsi
0x1400050bf  call    LuafvFreePool
0x1400050c4  mov     rcx, [rbp+57h+DestinationString.Buffer]
0x1400050c8  test    rcx, rcx
0x1400050cb  jz      short loc_1400050D2
0x1400050cd  call    LuafvFreePool
0x1400050d2  mov     rcx, [rbp+57h+LinkTarget.Buffer]
0x1400050d6  test    rcx, rcx
0x1400050d9  jz      short loc_1400050E0
0x1400050db  call    LuafvFreePool
0x1400050e0  mov     rcx, [rbp+57h+LinkHandle]; Handle
0x1400050e4  test    rcx, rcx
0x1400050e7  jz      short loc_1400050F5
0x1400050e9  call    cs:__imp_ZwClose
0x1400050f0  nop     dword ptr [rax+rax+00h]
0x1400050f5  test    ebx, ebx
0x1400050f7  jns     short loc_140005106
0x1400050f9  test    rsi, rsi
0x1400050fc  jz      short loc_140005106
0x1400050fe  mov     rcx, rsi
0x140005101  call    LuafvFreePool
0x140005106  mov     eax, ebx
0x140005108  jmp     short loc_140005183
0x14000510a  test    r14d, r14d
0x14000510d  jz      short loc_14000511B
0x14000510f  add     [rbp+57h+var_A0.Buffer], 0Ch
0x140005114  mov     ecx, 0FFF4h
0x140005119  jmp     short loc_140005124
0x14000511b  add     [rbp+57h+var_A0.Buffer], rcx
0x14000511f  mov     ecx, 0FFFCh
0x140005124  add     ax, cx
0x140005127  lea     rdx, [rbp+57h+LinkTarget]; SourceString
0x14000512b  xorps   xmm0, xmm0
0x14000512e  mov     [rbp+57h+var_A0.Length], ax
0x140005132  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x140005136  lea     rcx, [rbp+57h+Destination]; DestinationString
0x14000513a  mov     [rbp+57h+Destination.MaximumLength], bx
0x14000513e  mov     [rbp+57h+Destination.Buffer], rsi
0x140005142  mov     [rbp+57h+var_A0.MaximumLength], ax
0x140005146  call    cs:__imp_RtlCopyUnicodeString
0x14000514d  nop     dword ptr [rax+rax+00h]
0x140005152  lea     rdx, [rbp+57h+var_A0]; Source
0x140005156  lea     rcx, [rbp+57h+Destination]; Destination
0x14000515a  call    cs:__imp_RtlAppendUnicodeStringToString
0x140005161  nop     dword ptr [rax+rax+00h]
0x140005166  mov     ebx, eax
0x140005168  test    eax, eax
0x14000516a  js      loc_1400050BC
0x140005170  movups  xmm0, xmmword ptr [rbp+57h+Destination.Length]
0x140005174  movdqu  xmmword ptr [r15], xmm0
0x140005179  jmp     loc_1400050C4
0x14000517e  mov     eax, 0C000000Dh
0x140005183  lea     r11, [rsp+0C0h+var_20]
0x14000518b  mov     rbx, [r11+38h]
0x14000518f  mov     rsi, [r11+48h]
0x140005193  mov     rsp, r11
0x140005196  pop     r15
0x140005198  pop     r14
0x14000519a  pop     r13
0x14000519c  pop     rdi
0x14000519d  pop     rbp
0x14000519e  retn
```
