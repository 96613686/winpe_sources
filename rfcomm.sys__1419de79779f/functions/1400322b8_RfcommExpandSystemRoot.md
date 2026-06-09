# RfcommExpandSystemRoot

- ea: `0x1400322b8`
- end: `0x1400326ef`
- name: `RfcommExpandSystemRoot`
- size: `1079`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400328e8`

## callees

- `0x140003cb4`
- `0x140004788`
- `0x1400322b8`

## import_xrefs

- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x140032331`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x14003250e`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x140032331`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x14003250e`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140032396`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140032469`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140032553`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x1400325ff`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140032396`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140032469`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140032553`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x1400325ff`
- `ntoskrnl!ExAllocatePool2` at `0x140032436`
- `ntoskrnl!ExAllocatePool2` at `0x1400325cb`
- `ntoskrnl!ExAllocatePool2` at `0x140032436`
- `ntoskrnl!ExAllocatePool2` at `0x1400325cb`
- `ntoskrnl!ZwClose` at `0x14003249e`
- `ntoskrnl!ZwClose` at `0x140032611`
- `ntoskrnl!ZwClose` at `0x140032689`
- `ntoskrnl!ZwClose` at `0x14003249e`
- `ntoskrnl!ZwClose` at `0x140032611`
- `ntoskrnl!ZwClose` at `0x140032689`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400326a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400326c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400326a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400326c2`

## pseudocode

```c
__int64 __fastcall RfcommExpandSystemRoot(wchar_t **a1)
{
  wchar_t *v2; // rdi
  int v3; // edx
  NTSTATUS v4; // ebx
  int v5; // r9d
  char v6; // cl
  int v7; // r9d
  __int64 v8; // rcx
  wchar_t *Pool2; // rax
  char v11; // [rsp+38h] [rbp-21h]
  struct _UNICODE_STRING LinkTarget; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING v13; // [rsp+50h] [rbp-9h] BYREF
  _QWORD v14[2]; // [rsp+60h] [rbp+7h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+17h] BYREF
  ULONG ReturnedLength; // [rsp+C0h] [rbp+67h] BYREF
  void *LinkHandle; // [rsp+C8h] [rbp+6Fh] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v14[0] = 1572886;
  v14[1] = L"\\SystemRoot";
  LinkHandle = 0;
  ReturnedLength = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v14;
  v2 = 0;
  LinkTarget = 0;
  v13 = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = ZwOpenSymbolicLinkObject(&LinkHandle, 1u, &ObjectAttributes);
  if ( v4 < 0 )
  {
    LinkHandle = 0;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_43;
    v5 = 27;
LABEL_4:
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v3,
      19,
      v5,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
      v4);
    goto LABEL_41;
  }
  v4 = ZwQuerySymbolicLinkObject(LinkHandle, &LinkTarget, &ReturnedLength);
  if ( v4 != -1073741789 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_41;
    v5 = 28;
    goto LABEL_4;
  }
  v6 = ReturnedLength;
  if ( ReturnedLength > 0xFFFF )
  {
    v4 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_41;
    v7 = 29;
    v11 = 13;
LABEL_12:
    WPP_RECORDER_SF_ddd(
      WPP_GLOBAL_Control->DeviceExtension,
      v3,
      19,
      v7,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
      v6,
      255,
      v11);
    goto LABEL_41;
  }
  LinkTarget.Buffer = (wchar_t *)ExAllocatePool2(64, ReturnedLength, 1835230802);
  if ( !LinkTarget.Buffer )
    goto LABEL_15;
  LinkTarget.MaximumLength = ReturnedLength;
  v4 = ZwQuerySymbolicLinkObject(LinkHandle, &LinkTarget, &ReturnedLength);
  if ( v4 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_41;
    v5 = 30;
    goto LABEL_4;
  }
  ZwClose(LinkHandle);
  LODWORD(v8) = LinkTarget.Length >> 1;
  LinkHandle = 0;
  if ( !(_DWORD)v8 )
  {
    v4 = -1073741823;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_43;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      -1073741823,
      19,
      31,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
      1);
    goto LABEL_41;
  }
  do
    v8 = (unsigned int)(v8 - 1);
  while ( LinkTarget.Buffer[v8] != 92 && (_DWORD)v8 );
  LinkTarget.Length = 2 * v8;
  ObjectAttributes.ObjectName = &LinkTarget;
  v4 = ZwOpenSymbolicLinkObject(&LinkHandle, 1u, &ObjectAttributes);
  if ( v4 < 0 )
  {
    LinkHandle = 0;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_43;
    v5 = 32;
    goto LABEL_4;
  }
  ReturnedLength = 0;
  v4 = ZwQuerySymbolicLinkObject(LinkHandle, &v13, &ReturnedLength);
  if ( v4 != -1073741789 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_41;
    v5 = 33;
    goto LABEL_4;
  }
  v6 = ReturnedLength;
  if ( ReturnedLength > 0xFFFF )
  {
    v3 = -1073741823;
    v4 = -1073741823;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_41;
    v7 = 34;
    v11 = 1;
    goto LABEL_12;
  }
  Pool2 = (wchar_t *)ExAllocatePool2(64, ReturnedLength + 2LL, 1835230802);
  v2 = Pool2;
  if ( !Pool2 )
  {
LABEL_15:
    v4 = -1073741670;
    goto LABEL_41;
  }
  v13.Buffer = Pool2;
  v13.MaximumLength = ReturnedLength;
  v13.Length = 0;
  v4 = ZwQuerySymbolicLinkObject(LinkHandle, &v13, 0);
  ZwClose(LinkHandle);
  LinkHandle = 0;
  if ( v4 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_43;
    v5 = 35;
    goto LABEL_4;
  }
  if ( v13.Length <= v13.MaximumLength )
  {
    v2[(unsigned __int64)v13.Length >> 1] = 0;
  }
  else
  {
    v4 = -1073741823;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_43;
    WPP_RECORDER_SF_ddd(
      WPP_GLOBAL_Control->DeviceExtension,
      -1073741823,
      19,
      36,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
      v13.Length,
      v13.MaximumLength,
      1);
  }
LABEL_41:
  if ( LinkHandle )
  {
    ZwClose(LinkHandle);
    LinkHandle = 0;
  }
LABEL_43:
  if ( LinkTarget.Buffer )
  {
    ExFreePoolWithTag(LinkTarget.Buffer, 0);
    LinkTarget.Buffer = 0;
  }
  if ( v4 < 0 && v2 )
  {
    ExFreePoolWithTag(v2, 0);
    v2 = 0;
  }
  *a1 = v2;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400322b8  mov     [rsp-8+arg_10], rbx
0x1400322bd  mov     [rsp-8+arg_18], rsi
0x1400322c2  push    rbp
0x1400322c3  push    rdi
0x1400322c4  push    r14
0x1400322c6  lea     rbp, [rsp-47h]
0x1400322cb  sub     rsp, 0A0h
0x1400322d2  xor     r14d, r14d
0x1400322d5  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400322dd  xorps   xmm0, xmm0
0x1400322e0  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400322e8  lea     rax, aSystemroot; "\\SystemRoot"
0x1400322ef  mov     [rbp+57h+var_50], 180016h
0x1400322f7  mov     [rbp+57h+var_48], rax
0x1400322fb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400322ff  mov     rsi, rcx
0x140032302  mov     [rbp+57h+LinkHandle], r14
0x140032306  xorps   xmm1, xmm1
0x140032309  mov     [rbp+57h+ReturnedLength], r14d
0x14003230d  lea     rax, [rbp+57h+var_50]
0x140032311  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x140032315  lea     edx, [r14+1]; DesiredAccess
0x140032319  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14003231d  lea     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x140032321  mov     edi, r14d
0x140032324  movups  xmmword ptr [rbp+57h+LinkTarget.Length], xmm0
0x140032328  movups  xmmword ptr [rbp+57h+var_60.Length], xmm1
0x14003232c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140032331  call    cs:__imp_ZwOpenSymbolicLinkObject
0x140032338  nop     dword ptr [rax+rax+00h]
0x14003233d  mov     ebx, eax
0x14003233f  test    eax, eax
0x140032341  jns     short loc_14003238A
0x140032343  mov     [rbp+57h+LinkHandle], r14
0x140032347  lea     rax, WPP_RECORDER_INITIALIZED
0x14003234e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140032355  jz      loc_140032699
0x14003235b  lea     r9d, [r14+1Bh]
0x14003235f  mov     [rsp+0B0h+var_88], ebx
0x140032363  mov     rcx, cs:WPP_GLOBAL_Control
0x14003236a  lea     rax, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140032371  mov     r8d, 13h
0x140032377  mov     [rsp+0B0h+var_90], rax
0x14003237c  mov     rcx, [rcx+40h]
0x140032380  call    WPP_RECORDER_SF_d
0x140032385  jmp     loc_140032680
0x14003238a  mov     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x14003238e  lea     r8, [rbp+57h+ReturnedLength]; ReturnedLength
0x140032392  lea     rdx, [rbp+57h+LinkTarget]; LinkTarget
0x140032396  call    cs:__imp_ZwQuerySymbolicLinkObject
0x14003239d  nop     dword ptr [rax+rax+00h]
0x1400323a2  mov     ebx, eax
0x1400323a4  cmp     eax, 0C0000023h
0x1400323a9  jz      short loc_1400323C7
0x1400323ab  lea     rax, WPP_RECORDER_INITIALIZED
0x1400323b2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400323b9  jz      loc_140032680
0x1400323bf  mov     r9d, 1Ch
0x1400323c5  jmp     short loc_14003235F
0x1400323c7  mov     ecx, [rbp+57h+ReturnedLength]
0x1400323ca  cmp     ecx, 0FFFFh
0x1400323d0  jbe     short loc_140032428
0x1400323d2  mov     ebx, 0C000000Dh
0x1400323d7  lea     rax, WPP_RECORDER_INITIALIZED
0x1400323de  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400323e5  jz      loc_140032680
0x1400323eb  mov     r9d, 1Dh
0x1400323f1  mov     dword ptr [rsp+0B0h+var_78], ebx
0x1400323f5  mov     [rsp+0B0h+var_80], 0FFFFh
0x1400323fd  mov     [rsp+0B0h+var_88], ecx
0x140032401  lea     rax, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140032408  mov     rcx, cs:WPP_GLOBAL_Control
0x14003240f  mov     r8d, 13h
0x140032415  mov     [rsp+0B0h+var_90], rax
0x14003241a  mov     rcx, [rcx+40h]
0x14003241e  call    WPP_RECORDER_SF_ddd
0x140032423  jmp     loc_140032680
0x140032428  mov     rdx, rcx
0x14003242b  mov     r8d, 6D636652h
0x140032431  mov     ecx, 40h ; '@'
0x140032436  call    cs:__imp_ExAllocatePool2
0x14003243d  nop     dword ptr [rax+rax+00h]
0x140032442  mov     [rbp+57h+LinkTarget.Buffer], rax
0x140032446  test    rax, rax
0x140032449  jnz     short loc_140032455
0x14003244b  mov     ebx, 0C000009Ah
0x140032450  jmp     loc_140032680
0x140032455  movzx   eax, word ptr [rbp+57h+ReturnedLength]
0x140032459  lea     r8, [rbp+57h+ReturnedLength]; ReturnedLength
0x14003245d  mov     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x140032461  lea     rdx, [rbp+57h+LinkTarget]; LinkTarget
0x140032465  mov     [rbp+57h+LinkTarget.MaximumLength], ax
0x140032469  call    cs:__imp_ZwQuerySymbolicLinkObject
0x140032470  nop     dword ptr [rax+rax+00h]
0x140032475  mov     ebx, eax
0x140032477  test    eax, eax
0x140032479  jns     short loc_14003249A
0x14003247b  lea     rax, WPP_RECORDER_INITIALIZED
0x140032482  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140032489  jz      loc_140032680
0x14003248f  mov     r9d, 1Eh
0x140032495  jmp     loc_14003235F
0x14003249a  mov     rcx, [rbp+57h+LinkHandle]; Handle
0x14003249e  call    cs:__imp_ZwClose
0x1400324a5  nop     dword ptr [rax+rax+00h]
0x1400324aa  movzx   ecx, [rbp+57h+LinkTarget.Length]
0x1400324ae  shr     ecx, 1
0x1400324b0  mov     [rbp+57h+LinkHandle], r14
0x1400324b4  jnz     short loc_1400324E0
0x1400324b6  mov     edx, 0C0000001h
0x1400324bb  mov     ebx, edx
0x1400324bd  lea     rax, WPP_RECORDER_INITIALIZED
0x1400324c4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400324cb  jz      loc_140032699
0x1400324d1  mov     r9d, 1Fh
0x1400324d7  mov     [rsp+0B0h+var_88], edx
0x1400324db  jmp     loc_140032363
0x1400324e0  mov     r8, [rbp+57h+LinkTarget.Buffer]
0x1400324e4  dec     ecx
0x1400324e6  cmp     word ptr [r8+rcx*2], 5Ch ; '\'
0x1400324ec  jz      short loc_1400324F2
0x1400324ee  test    ecx, ecx
0x1400324f0  jnz     short loc_1400324E4
0x1400324f2  add     cx, cx
0x1400324f5  lea     rax, [rbp+57h+LinkTarget]
0x1400324f9  mov     [rbp+57h+LinkTarget.Length], cx
0x1400324fd  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140032501  lea     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x140032505  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140032509  mov     edx, 1; DesiredAccess
0x14003250e  call    cs:__imp_ZwOpenSymbolicLinkObject
0x140032515  nop     dword ptr [rax+rax+00h]
0x14003251a  mov     ebx, eax
0x14003251c  test    eax, eax
0x14003251e  jns     short loc_140032543
0x140032520  mov     [rbp+57h+LinkHandle], r14
0x140032524  lea     rax, WPP_RECORDER_INITIALIZED
0x14003252b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140032532  jz      loc_140032699
0x140032538  mov     r9d, 20h ; ' '
0x14003253e  jmp     loc_14003235F
0x140032543  mov     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x140032547  lea     r8, [rbp+57h+ReturnedLength]; ReturnedLength
0x14003254b  lea     rdx, [rbp+57h+var_60]; LinkTarget
0x14003254f  mov     [rbp+57h+ReturnedLength], r14d
0x140032553  call    cs:__imp_ZwQuerySymbolicLinkObject
0x14003255a  nop     dword ptr [rax+rax+00h]
0x14003255f  mov     ebx, eax
0x140032561  cmp     eax, 0C0000023h
0x140032566  jz      short loc_140032587
0x140032568  lea     rax, WPP_RECORDER_INITIALIZED
0x14003256f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140032576  jz      loc_140032680
0x14003257c  mov     r9d, 21h ; '!'
0x140032582  jmp     loc_14003235F
0x140032587  mov     ecx, [rbp+57h+ReturnedLength]
0x14003258a  cmp     ecx, 0FFFFh
0x140032590  jbe     short loc_1400325BC
0x140032592  mov     edx, 0C0000001h
0x140032597  mov     ebx, edx
0x140032599  lea     rax, WPP_RECORDER_INITIALIZED
0x1400325a0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400325a7  jz      loc_140032680
0x1400325ad  mov     r9d, 22h ; '"'
0x1400325b3  mov     dword ptr [rsp+0B0h+var_78], edx
0x1400325b7  jmp     loc_1400323F5
0x1400325bc  lea     rdx, [rcx+2]
0x1400325c0  mov     r8d, 6D636652h
0x1400325c6  mov     ecx, 40h ; '@'
0x1400325cb  call    cs:__imp_ExAllocatePool2
0x1400325d2  nop     dword ptr [rax+rax+00h]
0x1400325d7  mov     rdi, rax
0x1400325da  test    rax, rax
0x1400325dd  jz      loc_14003244B
0x1400325e3  mov     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x1400325e7  lea     rdx, [rbp+57h+var_60]; LinkTarget
0x1400325eb  mov     [rbp+57h+var_60.Buffer], rax
0x1400325ef  xor     r8d, r8d; ReturnedLength
0x1400325f2  movzx   eax, word ptr [rbp+57h+ReturnedLength]
0x1400325f6  mov     [rbp+57h+var_60.MaximumLength], ax
0x1400325fa  mov     [rbp+57h+var_60.Length], r14w
0x1400325ff  call    cs:__imp_ZwQuerySymbolicLinkObject
0x140032606  nop     dword ptr [rax+rax+00h]
0x14003260b  mov     rcx, [rbp+57h+LinkHandle]; Handle
0x14003260f  mov     ebx, eax
0x140032611  call    cs:__imp_ZwClose
0x140032618  nop     dword ptr [rax+rax+00h]
0x14003261d  mov     [rbp+57h+LinkHandle], r14
0x140032621  test    ebx, ebx
0x140032623  jns     short loc_140032640
0x140032625  lea     rax, WPP_RECORDER_INITIALIZED
0x14003262c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140032633  jz      short loc_140032699
0x140032635  mov     r9d, 23h ; '#'
0x14003263b  jmp     loc_14003235F
0x140032640  movzx   ecx, [rbp+57h+var_60.Length]
0x140032644  cmp     cx, [rbp+57h+var_60.MaximumLength]
0x140032648  jbe     short loc_140032678
0x14003264a  mov     edx, 0C0000001h
0x14003264f  mov     ebx, edx
0x140032651  lea     rax, WPP_RECORDER_INITIALIZED
0x140032658  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003265f  jz      short loc_140032699
0x140032661  movzx   eax, [rbp+57h+var_60.MaximumLength]
0x140032665  mov     r9d, 24h ; '$'
0x14003266b  mov     dword ptr [rsp+0B0h+var_78], edx
0x14003266f  mov     [rsp+0B0h+var_80], eax
0x140032673  jmp     loc_1400323FD
0x140032678  shr     rcx, 1
0x14003267b  mov     [rdi+rcx*2], r14w
0x140032680  mov     rcx, [rbp+57h+LinkHandle]; Handle
0x140032684  test    rcx, rcx
0x140032687  jz      short loc_140032699
0x140032689  call    cs:__imp_ZwClose
0x140032690  nop     dword ptr [rax+rax+00h]
0x140032695  mov     [rbp+57h+LinkHandle], r14
0x140032699  mov     rcx, [rbp+57h+LinkTarget.Buffer]; P
0x14003269d  test    rcx, rcx
0x1400326a0  jz      short loc_1400326B4
0x1400326a2  xor     edx, edx; Tag
0x1400326a4  call    cs:__imp_ExFreePoolWithTag
0x1400326ab  nop     dword ptr [rax+rax+00h]
0x1400326b0  mov     [rbp+57h+LinkTarget.Buffer], r14
0x1400326b4  test    ebx, ebx
0x1400326b6  jns     short loc_1400326D1
0x1400326b8  test    rdi, rdi
0x1400326bb  jz      short loc_1400326D1
0x1400326bd  xor     edx, edx; Tag
0x1400326bf  mov     rcx, rdi; P
0x1400326c2  call    cs:__imp_ExFreePoolWithTag
0x1400326c9  nop     dword ptr [rax+rax+00h]
0x1400326ce  mov     rdi, r14
0x1400326d1  lea     r11, [rsp+0B0h+var_10]
0x1400326d9  mov     [rsi], rdi
0x1400326dc  mov     rsi, [r11+38h]
0x1400326e0  mov     eax, ebx
0x1400326e2  mov     rbx, [r11+30h]
0x1400326e6  mov     rsp, r11
0x1400326e9  pop     r14
0x1400326eb  pop     rdi
0x1400326ec  pop     rbp
0x1400326ed  retn
```
