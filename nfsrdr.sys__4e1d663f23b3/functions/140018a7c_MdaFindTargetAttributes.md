# MdaFindTargetAttributes

- ea: `0x140018a7c`
- end: `0x14001903e`
- name: `MdaFindTargetAttributes`
- size: `1474`
- prototype: `__int64 __fastcall(__int64, struct _MRX_FCB_ *, __int64, char, __int64, _BYTE *, _BYTE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1400070a0`

## callees

- `0x1400022c0`
- `0x140005c90`
- `0x140008140`
- `0x140009380`
- `0x1400159cc`
- `0x1400159fc`
- `0x140018a7c`
- `0x14001a708`
- `0x140035384`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140018c77`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140018dd4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140018c77`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140018dd4`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140018ca4`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140018ca4`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140018cd3`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140018cd3`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140018de4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140018eb6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140018de4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140018eb6`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140018dff`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140018dff`
- `ntoskrnl!KeReleaseMutex` at `0x140018cb8`
- `ntoskrnl!KeReleaseMutex` at `0x140018f04`
- `ntoskrnl!KeReleaseMutex` at `0x140018cb8`
- `ntoskrnl!KeReleaseMutex` at `0x140018f04`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018d1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018d2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018d7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018f21`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018fc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018d1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018d2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018d7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018f21`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018fc3`
- `ntoskrnl!ExAllocatePool2` at `0x140018b32`
- `ntoskrnl!ExAllocatePool2` at `0x140018c44`
- `ntoskrnl!ExAllocatePool2` at `0x140018b32`
- `ntoskrnl!ExAllocatePool2` at `0x140018c44`

## pseudocode

```c
__int64 __fastcall MdaFindTargetAttributes(
        __int64 a1,
        struct _MRX_FCB_ *a2,
        __int64 a3,
        char a4,
        __int64 a5,
        _BYTE *a6,
        _BYTE *a7)
{
  PVOID *FileContextSupportPointer; // rax
  __int64 v10; // rbx
  _BYTE *v11; // r12
  bool v12; // zf
  BOOLEAN v13; // si
  WCHAR *Pool2; // rax
  WCHAR *v15; // r14
  unsigned int v16; // ebx
  __int64 v17; // rdx
  NTSTATUS appended; // ebx
  __int64 result; // rax
  unsigned int v20; // r15d
  __int64 v21; // rdx
  _BYTE *v22; // rsi
  int v23; // eax
  __int64 v24; // rsi
  unsigned int v25; // eax
  PDEVICE_OBJECT v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // [rsp+58h] [rbp-61h] BYREF
  PVOID *v29; // [rsp+60h] [rbp-59h]
  __int64 v30; // [rsp+68h] [rbp-51h]
  UNICODE_STRING String2; // [rsp+70h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-39h] BYREF
  UNICODE_STRING SourceString; // [rsp+90h] [rbp-29h] BYREF
  UNICODE_STRING Source; // [rsp+A0h] [rbp-19h] BYREF
  char v35[72]; // [rsp+B0h] [rbp-9h] BYREF
  char v36; // [rsp+108h] [rbp+4Fh]
  char v38; // [rsp+120h] [rbp+67h]

  v38 = a4;
  FileContextSupportPointer = a2->Header.FileContextSupportPointer;
  v28 = 0;
  v29 = FileContextSupportPointer;
  *(_QWORD *)&SourceString.Length = 0;
  SourceString.Buffer = 0;
  *(_QWORD *)&String2.Length = 0;
  String2.Buffer = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
    a4 = v38;
  }
  v10 = *(_QWORD *)(a1 + 40);
  v11 = a6;
  v30 = v10;
  v12 = (*(_DWORD *)(v10 + 32) & 0x100000) == 0;
  *a6 = 0;
  if ( !v12 || (v13 = 1, v36 = 1, !a4) )
  {
    v13 = 0;
    v36 = 0;
  }
  Pool2 = (WCHAR *)ExAllocatePool2(258, 520, 827483726);
  v15 = Pool2;
  if ( !Pool2 )
  {
    v16 = -1073741670;
LABEL_58:
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 )
      return v16;
    v27 = 51;
LABEL_61:
    WPP_SF_d(v26->AttachedDevice, v27, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
    return v16;
  }
  *(_DWORD *)&String2.Length = 34078720;
  String2.Buffer = Pool2;
  v12 = (*(_DWORD *)(v10 + 32) & 0x200) == 0;
  LOBYTE(a6) = 0;
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
LABEL_51:
    v16 = -1073741823;
    goto LABEL_52;
  }
  v16 = MdaResolveSymbolicLink(a1, a2, a3, v13, &String2, (unsigned __int16 *)&a6, 0, a5, a7);
  if ( (v16 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
LABEL_52:
    if ( (*((_BYTE *)v29 + 2316) & 4) != 0 || (*(_DWORD *)(v30 + 32) & 0x800) != 0 )
    {
      v16 = 0;
      *(_QWORD *)a5 = 0;
      *(_QWORD *)(a5 + 8) = 0;
      *(_QWORD *)(a5 + 16) = 0;
      *(_QWORD *)(a5 + 24) = 0;
      *(_QWORD *)(a5 + 48) = 0;
      *(_QWORD *)(a5 + 40) = 0;
      *(_DWORD *)(a5 + 32) = 32;
    }
    ExFreePoolWithTag(v15, 0);
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return v16;
    v27 = 52;
    goto LABEL_61;
  }
  if ( !(_BYTE)a6 )
  {
LABEL_47:
    ExFreePoolWithTag(v15, 0);
    goto LABEL_58;
  }
  DestinationString = 0;
  DestinationString.Buffer = (PWSTR)ExAllocatePool2(258, 520, 827483726);
  if ( !DestinationString.Buffer )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
LABEL_32:
    v20 = 0;
    while ( 1 )
    {
      if ( v20 )
      {
        String2.Buffer = v15;
        RtlCopyUnicodeString(&String2, &SourceString);
        RtlFreeUnicodeString(&SourceString);
      }
      if ( RtlPrefixUnicodeString(*(PCUNICODE_STRING *)(*(_QWORD *)(a1 + 32) + 88LL), &String2, v13) )
      {
        v21 = *(_QWORD *)(a1 + 32);
        String2.Buffer = (PWSTR)((char *)String2.Buffer + **(unsigned __int16 **)(v21 + 88));
        String2.Length -= **(_WORD **)(v21 + 88);
        String2.MaximumLength -= **(_WORD **)(v21 + 88);
      }
      v22 = a7;
      v23 = MdaParsePathFast(a1, a2, &String2, v38, &v28, &SourceString, a7, 0);
      v16 = v23;
      if ( *v22 )
      {
        if ( v23 == 260 )
          goto LABEL_52;
      }
      if ( v23 < 0 || (v24 = v28) == 0 && v23 != 260 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
        goto LABEL_51;
      }
      if ( v23 != 260 || (v25 = v20, ++v20, v25 >= 0x1A) )
      {
        RtlFreeUnicodeString(&SourceString);
        if ( v20 > 0x1A )
          goto LABEL_24;
        HacAcquireLock(v24);
        MdaMapBasicInformation(a1, v24, a5);
        *(_QWORD *)(a5 + 40) = *(_QWORD *)(v24 + 152) + 0x10000LL;
        *(_QWORD *)(a5 + 48) = *(_QWORD *)(v24 + 152);
        KeReleaseMutex(*(PRKMUTEX *)(v24 + 40), 0);
        HacDereference(v29, v24);
        goto LABEL_47;
      }
      v13 = v36;
    }
  }
  v17 = *(_QWORD *)(a1 + 32);
  *(_DWORD *)&DestinationString.Length = 34078720;
  Source = 0;
  RtlCopyUnicodeString(&DestinationString, *(PCUNICODE_STRING *)(v17 + 88));
  HacAcquireLock(a3);
  MdaDissectNameTail(a3 + 64, &Source, v35);
  appended = RtlAppendUnicodeStringToString(&DestinationString, &Source);
  KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
  if ( appended < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
    goto LABEL_28;
  }
  if ( RtlCompareUnicodeString(&DestinationString, &String2, v13) )
  {
LABEL_28:
    ExFreePoolWithTag(DestinationString.Buffer, 0);
    goto LABEL_32;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
  ExFreePoolWithTag(DestinationString.Buffer, 0);
LABEL_24:
  ExFreePoolWithTag(v15, 0);
  result = 0;
  *v11 = 1;
  return result;
}

```

## disassembly

```asm
0x140018a7c  mov     rax, rsp
0x140018a7f  mov     [rax+18h], rbx
0x140018a83  mov     [rax+20h], r9b
0x140018a87  mov     [rax+10h], rdx
0x140018a8b  push    rbp
0x140018a8c  push    rsi
0x140018a8d  push    rdi
0x140018a8e  push    r12
0x140018a90  push    r13
0x140018a92  push    r14
0x140018a94  push    r15
0x140018a96  lea     rbp, [rax-47h]
0x140018a9a  sub     rsp, 0C0h
0x140018aa1  mov     rax, [rdx+50h]
0x140018aa5  xor     edi, edi
0x140018aa7  mov     [rbp+3Fh+var_A0], rdi
0x140018aab  mov     r15, r8
0x140018aae  mov     [rbp+3Fh+var_98], rax
0x140018ab2  mov     r13, rcx
0x140018ab5  mov     qword ptr [rbp+3Fh+SourceString.Length], rdi
0x140018ab9  mov     [rbp+3Fh+SourceString.Buffer], rdi
0x140018abd  mov     qword ptr [rbp+3Fh+String2.Length], rdi
0x140018ac1  mov     [rbp+3Fh+String2.Buffer], rdi
0x140018ac5  mov     rcx, cs:WPP_GLOBAL_Control
0x140018acc  lea     rax, WPP_GLOBAL_Control
0x140018ad3  cmp     rcx, rax
0x140018ad6  jz      short loc_140018AF6
0x140018ad8  mov     eax, [rcx+2Ch]
0x140018adb  test    al, 8
0x140018add  jz      short loc_140018AF6
0x140018adf  mov     rcx, [rcx+18h]
0x140018ae3  lea     edx, [rdi+2Ch]
0x140018ae6  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x140018aed  call    WPP_SF_
0x140018af2  mov     r9b, byte ptr [rbp+3Fh+arg_18]
0x140018af6  mov     rbx, [r13+28h]
0x140018afa  mov     r12, [rbp+3Fh+arg_28]
0x140018afe  mov     [rbp+3Fh+var_90], rbx
0x140018b02  test    dword ptr [rbx+20h], 100000h
0x140018b09  mov     [r12], dil
0x140018b0d  jnz     short loc_140018B1B
0x140018b0f  mov     sil, 1
0x140018b12  mov     [rbp+3Fh+arg_0], sil
0x140018b16  test    r9b, r9b
0x140018b19  jnz     short loc_140018B22
0x140018b1b  mov     sil, dil
0x140018b1e  mov     [rbp+3Fh+arg_0], dil
0x140018b22  mov     edx, 208h
0x140018b27  mov     ecx, 102h
0x140018b2c  mov     r8d, 3152664Eh
0x140018b32  call    cs:__imp_ExAllocatePool2
0x140018b39  nop     dword ptr [rax+rax+00h]
0x140018b3e  mov     r14, rax
0x140018b41  test    rax, rax
0x140018b44  jz      loc_140018FE9
0x140018b4a  mov     dword ptr [rbp+3Fh+String2.Length], 2080000h
0x140018b51  mov     [rbp+3Fh+String2.Buffer], rax
0x140018b55  test    dword ptr [rbx+20h], 200h
0x140018b5c  mov     byte ptr [rbp+3Fh+arg_28], dil
0x140018b60  mov     rdi, [rbp+3Fh+arg_20]
0x140018b64  jnz     short loc_140018BA2
0x140018b66  mov     rcx, cs:WPP_GLOBAL_Control
0x140018b6d  lea     rsi, WPP_GLOBAL_Control
0x140018b74  cmp     rcx, rsi
0x140018b77  jz      loc_140018F64
0x140018b7d  mov     eax, [rcx+2Ch]
0x140018b80  test    al, 4
0x140018b82  jz      loc_140018F64
0x140018b88  mov     rcx, [rcx+18h]
0x140018b8c  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x140018b93  mov     edx, 2Dh ; '-'
0x140018b98  call    WPP_SF_
0x140018b9d  jmp     loc_140018F64
0x140018ba2  mov     rax, [rbp+3Fh+arg_30]
0x140018ba6  mov     r9b, sil; int
0x140018ba9  mov     rdx, qword ptr [rbp+3Fh+arg_8]; int
0x140018bad  mov     r8, r15; int
0x140018bb0  mov     [rsp+40h], rax; __int64
0x140018bb5  mov     rcx, r13; int
0x140018bb8  mov     [rsp+0F0h+var_B8], rdi; __int64
0x140018bbd  lea     rax, [rbp+3Fh+arg_28]
0x140018bc1  mov     [rsp+0F0h+var_C0], 0; __int64
0x140018bca  mov     [rsp+0F0h+Destination], rax; __int64
0x140018bcf  lea     rax, [rbp+3Fh+String2]
0x140018bd3  mov     [rsp+0F0h+var_D0], rax; String2
0x140018bd8  call    MdaResolveSymbolicLink
0x140018bdd  mov     ebx, eax
0x140018bdf  test    eax, eax
0x140018be1  jns     short loc_140018C23
0x140018be3  mov     rcx, cs:WPP_GLOBAL_Control
0x140018bea  lea     rsi, WPP_GLOBAL_Control
0x140018bf1  cmp     rcx, rsi
0x140018bf4  jz      loc_140018F72
0x140018bfa  mov     edx, [rcx+2Ch]
0x140018bfd  test    dl, 1
0x140018c00  jz      loc_140018F72
0x140018c06  mov     rcx, [rcx+18h]
0x140018c0a  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x140018c11  mov     edx, 2Eh ; '.'
0x140018c16  mov     r9d, eax
0x140018c19  call    WPP_SF_d
0x140018c1e  jmp     loc_140018F72
0x140018c23  cmp     byte ptr [rbp+3Fh+arg_28], 0
0x140018c27  jz      loc_140018F1C
0x140018c2d  xorps   xmm0, xmm0
0x140018c30  mov     edx, 208h
0x140018c35  mov     ecx, 102h
0x140018c3a  mov     r8d, 3152664Eh
0x140018c40  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x140018c44  call    cs:__imp_ExAllocatePool2
0x140018c4b  nop     dword ptr [rax+rax+00h]
0x140018c50  mov     [rbp+3Fh+DestinationString.Buffer], rax
0x140018c54  test    rax, rax
0x140018c57  jz      loc_140018D8B
0x140018c5d  mov     rdx, [r13+20h]
0x140018c61  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x140018c65  xorps   xmm0, xmm0
0x140018c68  mov     dword ptr [rbp+3Fh+DestinationString.Length], 2080000h
0x140018c6f  movups  xmmword ptr [rbp+3Fh+Source.Length], xmm0
0x140018c73  mov     rdx, [rdx+58h]; SourceString
0x140018c77  call    cs:__imp_RtlCopyUnicodeString
0x140018c7e  nop     dword ptr [rax+rax+00h]
0x140018c83  mov     rcx, r15
0x140018c86  call    HacAcquireLock
0x140018c8b  lea     rcx, [r15+40h]
0x140018c8f  lea     r8, [rbp+3Fh+var_48]
0x140018c93  lea     rdx, [rbp+3Fh+Source]
0x140018c97  call    MdaDissectNameTail
0x140018c9c  lea     rdx, [rbp+3Fh+Source]; Source
0x140018ca0  lea     rcx, [rbp+3Fh+DestinationString]; Destination
0x140018ca4  call    cs:__imp_RtlAppendUnicodeStringToString
0x140018cab  nop     dword ptr [rax+rax+00h]
0x140018cb0  mov     rcx, [r15+28h]; Mutex
0x140018cb4  xor     edx, edx; Wait
0x140018cb6  mov     ebx, eax
0x140018cb8  call    cs:__imp_KeReleaseMutex
0x140018cbf  nop     dword ptr [rax+rax+00h]
0x140018cc4  test    ebx, ebx
0x140018cc6  js      short loc_140018D45
0x140018cc8  mov     r8b, sil; CaseInSensitive
0x140018ccb  lea     rdx, [rbp+3Fh+String2]; String2
0x140018ccf  lea     rcx, [rbp+3Fh+DestinationString]; String1
0x140018cd3  call    cs:__imp_RtlCompareUnicodeString
0x140018cda  nop     dword ptr [rax+rax+00h]
0x140018cdf  test    eax, eax
0x140018ce1  jnz     loc_140018D77
0x140018ce7  mov     rcx, cs:WPP_GLOBAL_Control
0x140018cee  lea     rax, WPP_GLOBAL_Control
0x140018cf5  cmp     rcx, rax
0x140018cf8  jz      short loc_140018D16
0x140018cfa  mov     eax, [rcx+2Ch]
0x140018cfd  test    al, 2
0x140018cff  jz      short loc_140018D16
0x140018d01  mov     rcx, [rcx+18h]
0x140018d05  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x140018d0c  mov     edx, 2Fh ; '/'
0x140018d11  call    WPP_SF_
0x140018d16  mov     rcx, [rbp+3Fh+DestinationString.Buffer]; P
0x140018d1a  xor     edx, edx; Tag
0x140018d1c  call    cs:__imp_ExFreePoolWithTag
0x140018d23  nop     dword ptr [rax+rax+00h]
0x140018d28  xor     edx, edx; Tag
0x140018d2a  mov     rcx, r14; P
0x140018d2d  call    cs:__imp_ExFreePoolWithTag
0x140018d34  nop     dword ptr [rax+rax+00h]
0x140018d39  xor     eax, eax
0x140018d3b  mov     byte ptr [r12], 1
0x140018d40  jmp     loc_140019022
0x140018d45  mov     rcx, cs:WPP_GLOBAL_Control
0x140018d4c  lea     rax, WPP_GLOBAL_Control
0x140018d53  cmp     rcx, rax
0x140018d56  jz      short loc_140018D77
0x140018d58  mov     eax, [rcx+2Ch]
0x140018d5b  test    al, 1
0x140018d5d  jz      short loc_140018D77
0x140018d5f  mov     rcx, [rcx+18h]
0x140018d63  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x140018d6a  mov     edx, 30h ; '0'
0x140018d6f  mov     r9d, ebx
0x140018d72  call    WPP_SF_d
0x140018d77  mov     rcx, [rbp+3Fh+DestinationString.Buffer]; P
0x140018d7b  xor     edx, edx; Tag
0x140018d7d  call    cs:__imp_ExFreePoolWithTag
0x140018d84  nop     dword ptr [rax+rax+00h]
0x140018d89  jmp     short loc_140018DBA
0x140018d8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140018d92  lea     rax, WPP_GLOBAL_Control
0x140018d99  cmp     rcx, rax
0x140018d9c  jz      short loc_140018DBA
0x140018d9e  mov     eax, [rcx+2Ch]
0x140018da1  test    al, 1
0x140018da3  jz      short loc_140018DBA
0x140018da5  mov     rcx, [rcx+18h]
0x140018da9  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x140018db0  mov     edx, 31h ; '1'
0x140018db5  call    WPP_SF_
0x140018dba  xor     r15d, r15d
0x140018dbd  jmp     short loc_140018DC3
0x140018dbf  mov     sil, [rbp+3Fh+arg_0]
0x140018dc3  test    r15d, r15d
0x140018dc6  jz      short loc_140018DF0
0x140018dc8  lea     rdx, [rbp+3Fh+SourceString]; SourceString
0x140018dcc  mov     [rbp+3Fh+String2.Buffer], r14
0x140018dd0  lea     rcx, [rbp+3Fh+String2]; DestinationString
0x140018dd4  call    cs:__imp_RtlCopyUnicodeString
0x140018ddb  nop     dword ptr [rax+rax+00h]
0x140018de0  lea     rcx, [rbp+3Fh+SourceString]; UnicodeString
0x140018de4  call    cs:__imp_RtlFreeUnicodeString
0x140018deb  nop     dword ptr [rax+rax+00h]
0x140018df0  mov     rcx, [r13+20h]
0x140018df4  lea     rdx, [rbp+3Fh+String2]; String2
0x140018df8  mov     r8b, sil; CaseInSensitive
0x140018dfb  mov     rcx, [rcx+58h]; String1
0x140018dff  call    cs:__imp_RtlPrefixUnicodeString
0x140018e06  nop     dword ptr [rax+rax+00h]
0x140018e0b  test    al, al
0x140018e0d  jz      short loc_140018E34
0x140018e0f  mov     rdx, [r13+20h]
0x140018e13  mov     rax, [rdx+58h]
0x140018e17  movzx   ecx, word ptr [rax]
0x140018e1a  add     [rbp+3Fh+String2.Buffer], rcx
0x140018e1e  mov     rax, [rdx+58h]
0x140018e22  movzx   ecx, word ptr [rax]
0x140018e25  sub     [rbp+3Fh+String2.Length], cx
0x140018e29  mov     rax, [rdx+58h]
0x140018e2d  movzx   ecx, word ptr [rax]
0x140018e30  sub     [rbp+3Fh+String2.MaximumLength], cx
0x140018e34  mov     rsi, [rbp+3Fh+arg_30]
0x140018e38  lea     rax, [rbp+3Fh+SourceString]
0x140018e3c  mov     r9b, byte ptr [rbp+3Fh+arg_18]; int
0x140018e40  lea     r8, [rbp+3Fh+String2]; int
0x140018e44  mov     rdx, qword ptr [rbp+3Fh+arg_8]; int
0x140018e48  mov     rcx, r13; int
0x140018e4b  mov     [rsp+0F0h+var_B8], 0; __int64
0x140018e54  mov     [rsp+0F0h+var_C0], rsi; __int64
0x140018e59  mov     [rsp+0F0h+Destination], rax; Destination
0x140018e5e  lea     rax, [rbp+3Fh+var_A0]
0x140018e62  mov     [rsp+0F0h+var_D0], rax; __int64
0x140018e67  call    MdaParsePathFast
0x140018e6c  cmp     byte ptr [rsi], 0
0x140018e6f  mov     ebx, eax
0x140018e71  jz      short loc_140018E7E
0x140018e73  cmp     eax, 104h
0x140018e78  jz      loc_140018F6B
0x140018e7e  test    ebx, ebx
0x140018e80  js      loc_140018F32
0x140018e86  mov     rsi, [rbp+3Fh+var_A0]
0x140018e8a  test    rsi, rsi
0x140018e8d  jnz     short loc_140018E9B
0x140018e8f  cmp     ebx, 104h
0x140018e95  jnz     loc_140018F32
0x140018e9b  cmp     ebx, 104h
0x140018ea1  jnz     short loc_140018EB2
0x140018ea3  mov     eax, r15d
0x140018ea6  inc     r15d
0x140018ea9  cmp     eax, 1Ah
0x140018eac  jb      loc_140018DBF
0x140018eb2  lea     rcx, [rbp+3Fh+SourceString]; UnicodeString
0x140018eb6  call    cs:__imp_RtlFreeUnicodeString
0x140018ebd  nop     dword ptr [rax+rax+00h]
0x140018ec2  cmp     r15d, 1Ah
0x140018ec6  ja      loc_140018D28
0x140018ecc  mov     rcx, rsi
0x140018ecf  call    HacAcquireLock
0x140018ed4  mov     r8, rdi
0x140018ed7  mov     rdx, rsi
0x140018eda  mov     rcx, r13
0x140018edd  call    MdaMapBasicInformation
0x140018ee2  mov     rax, [rsi+98h]
0x140018ee9  xor     edx, edx; Wait
0x140018eeb  add     rax, 10000h
0x140018ef1  mov     [rdi+28h], rax
0x140018ef5  mov     rax, [rsi+98h]
0x140018efc  mov     [rdi+30h], rax
0x140018f00  mov     rcx, [rsi+28h]; Mutex
0x140018f04  call    cs:__imp_KeReleaseMutex
0x140018f0b  nop     dword ptr [rax+rax+00h]
0x140018f10  mov     rcx, [rbp+3Fh+var_98]
0x140018f14  mov     rdx, rsi
0x140018f17  call    HacDereference
0x140018f1c  xor     edx, edx; Tag
0x140018f1e  mov     rcx, r14; P
0x140018f21  call    cs:__imp_ExFreePoolWithTag
0x140018f28  nop     dword ptr [rax+rax+00h]
0x140018f2d  jmp     loc_140018FEE
0x140018f32  mov     rcx, cs:WPP_GLOBAL_Control
0x140018f39  lea     rsi, WPP_GLOBAL_Control
0x140018f40  cmp     rcx, rsi
0x140018f43  jz      short loc_140018F64
0x140018f45  mov     eax, [rcx+2Ch]
0x140018f48  test    al, 1
0x140018f4a  jz      short loc_140018F64
0x140018f4c  mov     rcx, [rcx+18h]
0x140018f50  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x140018f57  mov     edx, 32h ; '2'
0x140018f5c  mov     r9d, ebx
0x140018f5f  call    WPP_SF_d
0x140018f64  mov     ebx, 0C0000001h
0x140018f69  jmp     short loc_140018F72
0x140018f6b  lea     rsi, WPP_GLOBAL_Control
  ... truncated ...
```
