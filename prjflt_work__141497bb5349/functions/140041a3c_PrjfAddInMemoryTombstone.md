# PrjfAddInMemoryTombstone

- ea: `0x140041a3c`
- end: `0x140041e20`
- name: `PrjfAddInMemoryTombstone`
- size: `996`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PCUNICODE_STRING SourceString, __int64, __int64, PFILE_OBJECT FileObject, _QWORD *)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140007cec`
- `0x140040670`
- `0x140042658`
- `0x140042eac`

## callees

- `0x140002f3c`
- `0x14000b1a0`
- `0x14000d754`
- `0x14003775c`
- `0x14003c4b8`
- `0x140041a3c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140041dc4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041ded`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041dc4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041ded`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140041ca9`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140041ca9`
- `ntoskrnl!RtlHashUnicodeString` at `0x140041c74`
- `ntoskrnl!RtlHashUnicodeString` at `0x140041c74`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x140041c51`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x140041c51`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140041dfd`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140041dfd`
- `ntoskrnl!ObfDereferenceObject` at `0x140041d7c`
- `ntoskrnl!ObfDereferenceObject` at `0x140041d7c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140041c3b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140041c3b`
- `ntoskrnl!ExAllocatePool2` at `0x140041bd5`
- `ntoskrnl!ExAllocatePool2` at `0x140041bd5`
- `FLTMGR!FltClose` at `0x140041d62`
- `FLTMGR!FltClose` at `0x140041d62`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140041c8c`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140041c8c`
- `FLTMGR!FltReleaseResource` at `0x140041cb8`
- `FLTMGR!FltReleaseResource` at `0x140041cb8`
- `FLTMGR!FltReleaseContext` at `0x140041d90`
- `FLTMGR!FltReleaseContext` at `0x140041da5`
- `FLTMGR!FltReleaseContext` at `0x140041dd9`
- `FLTMGR!FltReleaseContext` at `0x140041d90`
- `FLTMGR!FltReleaseContext` at `0x140041da5`
- `FLTMGR!FltReleaseContext` at `0x140041dd9`

## string_xrefs

- `0x140041cd0`: `Parent file doesn't have a context; expanded directory?`

## pseudocode

```c
__int64 __fastcall PrjfAddInMemoryTombstone(
        PFLT_INSTANCE Instance,
        PCUNICODE_STRING SourceString,
        __int64 a3,
        __int64 a4,
        PFILE_OBJECT FileObject,
        _QWORD *a6)
{
  struct _FILE_OBJECT *v6; // r15
  __int64 v7; // r14
  __int64 v8; // rdi
  char v9; // r12
  __int16 v12; // cx
  __int16 v13; // ax
  int v14; // edx
  int UnicodeString; // esi
  int v16; // r8d
  int SetContextFileObject; // eax
  int v18; // edx
  int v19; // r8d
  __int64 Pool2; // rax
  USHORT MaximumLength; // ax
  void *v22; // rcx
  void *v23; // rcx
  _BYTE v25[4]; // [rsp+60h] [rbp-49h] BYREF
  ULONG HashValue; // [rsp+64h] [rbp-45h] BYREF
  PVOID Object; // [rsp+68h] [rbp-41h] BYREF
  __int64 v28; // [rsp+70h] [rbp-39h] BYREF
  HANDLE FileHandle; // [rsp+78h] [rbp-31h] BYREF
  PFLT_CONTEXT Context; // [rsp+80h] [rbp-29h] BYREF
  __m128i v31; // [rsp+88h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-11h] BYREF
  char FileObjecta; // [rsp+120h] [rbp+77h]

  v6 = FileObject;
  v7 = 0;
  v8 = 0;
  FileHandle = 0;
  Object = 0;
  v28 = 0;
  Context = 0;
  v9 = a3;
  HashValue = 0;
  v25[0] = 0;
  v31 = 0;
  DestinationString = 0;
  if ( FileObject )
  {
    FileObjecta = 0;
    goto LABEL_11;
  }
  FileObjecta = 1;
  v31 = *(__m128i *)(a4 + 8);
  v12 = _mm_cvtsi128_si32(v31) - *(_WORD *)(a4 + 88);
  v13 = v12 - 2;
  if ( v12 - 2 == *(_WORD *)(a4 + 24) )
    v13 = v12;
  v31.m128i_i16[0] = v13;
  UnicodeString = PrjfOpenPlaceHolder(Instance, (__int64)&v31, a3, &FileHandle, &Object, v25);
  if ( UnicodeString >= 0 )
  {
    v6 = (struct _FILE_OBJECT *)Object;
LABEL_11:
    SetContextFileObject = PrjfGetSetContextFileObject(Instance, v6, 0x80000000, 0, 0, 0, 0, &v28, &Context);
    v7 = v28;
    UnicodeString = SetContextFileObject;
    if ( SetContextFileObject < 0 )
    {
      if ( v28 )
      {
LABEL_22:
        if ( (BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v18) = BYTE2(xmmword_14001A3D0) & 8;
          LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDdZ(
            531,
            v18,
            v19,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            19,
            11,
            (__int64)WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\tombstone.c",
            144,
            UnicodeString,
            (__int64)&v6->FileName);
        }
        goto LABEL_25;
      }
    }
    else if ( v28 )
    {
      Pool2 = ExAllocatePool2(256, 56, 1952991824);
      v8 = Pool2;
      if ( Pool2 )
      {
        *(_BYTE *)(Pool2 + 24) = v9;
        MaximumLength = SourceString->MaximumLength;
        *(_WORD *)(v8 + 34) = MaximumLength;
        *(_WORD *)(v8 + 32) = MaximumLength;
        UnicodeString = PrjfAllocateUnicodeString(1852197456, v8 + 32);
        if ( UnicodeString >= 0 )
        {
          if ( a6 )
          {
            *(_QWORD *)(v8 + 48) = *a6;
            *a6 = 0;
          }
          RtlCopyUnicodeString((PUNICODE_STRING)(v8 + 32), SourceString);
          UnicodeString = RtlDowncaseUnicodeString(&DestinationString, SourceString, 1u);
          if ( UnicodeString >= 0 )
          {
            UnicodeString = RtlHashUnicodeString(&DestinationString, 1u, 0, &HashValue);
            FltAcquireResourceExclusive((PERESOURCE)(v7 + 136));
            RtlInsertEntryHashTable(
              (PRTL_DYNAMIC_HASH_TABLE)(v7 + 240),
              (PRTL_DYNAMIC_HASH_TABLE_ENTRY)v8,
              HashValue,
              0);
            FltReleaseResource((PERESOURCE)(v7 + 136));
            v8 = 0;
          }
        }
      }
      else
      {
        UnicodeString = -1073741670;
      }
      goto LABEL_25;
    }
    MicrosoftTelemetryAssertTriggeredMsgKM("Parent file doesn't have a context; expanded directory?");
    UnicodeString = -1073741595;
    goto LABEL_22;
  }
  if ( (BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v14) = BYTE2(xmmword_14001A3D0) & 8;
    LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDdZ(
      531,
      v14,
      v16,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      19,
      10,
      (__int64)WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\tombstone.c",
      104,
      UnicodeString,
      (__int64)&v31);
  }
  v6 = (struct _FILE_OBJECT *)Object;
LABEL_25:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObjecta && v6 )
    ObfDereferenceObject(v6);
  if ( v7 )
    FltReleaseContext((PFLT_CONTEXT)v7);
  if ( Context )
    FltReleaseContext(Context);
  if ( v8 )
  {
    v22 = *(void **)(v8 + 40);
    if ( v22 )
      ExFreePoolWithTag(v22, 0x6E664A50u);
    v23 = *(void **)(v8 + 48);
    if ( v23 )
      FltReleaseContext(v23);
    ExFreePoolWithTag((PVOID)v8, 0x74684A50u);
  }
  RtlFreeUnicodeString(&DestinationString);
  return (unsigned int)UnicodeString;
}

```

## disassembly

```asm
0x140041a3c  push    rbp
0x140041a3e  push    rbx
0x140041a3f  push    rsi
0x140041a40  push    rdi
0x140041a41  push    r12
0x140041a43  push    r13
0x140041a45  push    r14
0x140041a47  push    r15
0x140041a49  lea     rbp, [rsp-0Fh]
0x140041a4e  sub     rsp, 0B8h
0x140041a55  mov     r15, [rbp+47h+FileObject]
0x140041a59  xor     r14d, r14d
0x140041a5c  xor     edi, edi
0x140041a5e  mov     [rbp+47h+FileHandle], 0
0x140041a66  mov     [rbp+47h+Object], 0
0x140041a6e  xorps   xmm0, xmm0
0x140041a71  mov     [rbp+47h+var_80], r14
0x140041a75  xorps   xmm1, xmm1
0x140041a78  mov     [rbp+47h+Context], r14
0x140041a7c  mov     r12b, r8b
0x140041a7f  mov     [rbp+47h+HashValue], edi
0x140041a82  mov     r13, rdx
0x140041a85  mov     [rbp+47h+var_90], dil
0x140041a89  mov     rbx, rcx
0x140041a8c  movups  [rbp+47h+var_68], xmm0
0x140041a90  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm1
0x140041a94  test    r15, r15
0x140041a97  jz      short loc_140041AA2
0x140041a99  mov     byte ptr [rbp+47h+FileObject], dil
0x140041a9d  jmp     loc_140041B79
0x140041aa2  movups  xmm0, xmmword ptr [r9+8]
0x140041aa7  lea     rdx, [rbp+47h+var_68]
0x140041aab  mov     byte ptr [rbp+47h+FileObject], 1
0x140041aaf  movd    ecx, xmm0
0x140041ab3  movups  [rbp+47h+var_68], xmm0
0x140041ab7  sub     cx, [r9+58h]
0x140041abc  lea     eax, [rcx-2]
0x140041abf  cmp     ax, [r9+18h]
0x140041ac4  lea     r9, [rbp+47h+FileHandle]
0x140041ac8  cmovz   ax, cx
0x140041acc  mov     rcx, rbx
0x140041acf  mov     word ptr [rbp+47h+var_68], ax
0x140041ad3  lea     rax, [rbp+47h+var_90]
0x140041ad7  mov     [rsp+0F0h+var_C8], rax
0x140041adc  lea     rax, [rbp+47h+Object]
0x140041ae0  mov     qword ptr [rsp+0F0h+var_D0], rax
0x140041ae5  call    PrjfOpenPlaceHolder
0x140041aea  mov     esi, eax
0x140041aec  test    eax, eax
0x140041aee  jns     loc_140041B75
0x140041af4  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140041afa  lea     rax, WPP_RECORDER_INITIALIZED
0x140041b01  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140041b08  setnz   r8b
0x140041b0c  and     dl, 8
0x140041b0f  jnz     short loc_140041B16
0x140041b11  test    r8b, r8b
0x140041b14  jz      short loc_140041B6C
0x140041b16  mov     r9, cs:WPP_GLOBAL_Control
0x140041b1d  lea     rax, [rbp+47h+var_68]
0x140041b21  mov     [rsp+0F0h+var_98], rax
0x140041b26  mov     ecx, 213h
0x140041b2b  mov     [rsp+0F0h+var_A0], esi
0x140041b2f  lea     rax, aOnecoreBaseFsG_6; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140041b36  mov     [rsp+0F0h+var_A8], 68h ; 'h'
0x140041b3e  mov     r9, [r9+40h]
0x140041b42  mov     [rsp+0F0h+var_B0], rax
0x140041b47  lea     rax, WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids
0x140041b4e  mov     [rsp+0F0h+var_B8], rax
0x140041b53  mov     word ptr [rsp+0F0h+var_C0], 0Ah
0x140041b5a  mov     dword ptr [rsp+0F0h+var_C8], 13h
0x140041b62  mov     [rsp+0F0h+var_D0], 2
0x140041b67  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140041b6c  mov     r15, [rbp+47h+Object]
0x140041b70  jmp     loc_140041D59
0x140041b75  mov     r15, [rbp+47h+Object]
0x140041b79  lea     rax, [rbp+47h+Context]
0x140041b7d  xor     r9d, r9d
0x140041b80  mov     [rsp+0F0h+var_B0], rax; __int64
0x140041b85  mov     r8d, 80000000h
0x140041b8b  lea     rax, [rbp+47h+var_80]
0x140041b8f  mov     rdx, r15; FileObject
0x140041b92  mov     [rsp+0F0h+var_B8], rax; __int64
0x140041b97  mov     rcx, rbx; Instance
0x140041b9a  mov     [rsp+0F0h+var_C0], rdi; __int64
0x140041b9f  mov     [rsp+0F0h+var_C8], rdi; __int64
0x140041ba4  mov     [rsp+0F0h+var_D0], dil; char
0x140041ba9  call    PrjfGetSetContextFileObject
0x140041bae  mov     r14, [rbp+47h+var_80]
0x140041bb2  mov     esi, eax
0x140041bb4  test    eax, eax
0x140041bb6  js      loc_140041CCB
0x140041bbc  test    r14, r14
0x140041bbf  jz      loc_140041CD0
0x140041bc5  mov     edx, 38h ; '8'
0x140041bca  mov     ecx, 100h
0x140041bcf  mov     r8d, 74684A50h
0x140041bd5  call    cs:__imp_ExAllocatePool2
0x140041bdc  nop     dword ptr [rax+rax+00h]
0x140041be1  mov     rdi, rax
0x140041be4  test    rax, rax
0x140041be7  jnz     short loc_140041BF3
0x140041be9  mov     esi, 0C000009Ah
0x140041bee  jmp     loc_140041D59
0x140041bf3  mov     [rax+18h], r12b
0x140041bf7  lea     rbx, [rdi+20h]
0x140041bfb  movzx   eax, word ptr [r13+2]
0x140041c00  mov     rdx, rbx
0x140041c03  mov     ecx, 6E664A50h
0x140041c08  mov     [rdi+22h], ax
0x140041c0c  mov     [rbx], ax
0x140041c0f  call    PrjfAllocateUnicodeString
0x140041c14  mov     esi, eax
0x140041c16  test    eax, eax
0x140041c18  js      loc_140041D59
0x140041c1e  mov     rdx, [rbp+47h+arg_28]
0x140041c22  test    rdx, rdx
0x140041c25  jz      short loc_140041C35
0x140041c27  mov     rax, [rdx]
0x140041c2a  mov     [rdi+30h], rax
0x140041c2e  mov     qword ptr [rdx], 0
0x140041c35  mov     rdx, r13; SourceString
0x140041c38  mov     rcx, rbx; DestinationString
0x140041c3b  call    cs:__imp_RtlCopyUnicodeString
0x140041c42  nop     dword ptr [rax+rax+00h]
0x140041c47  mov     r8b, 1; AllocateDestinationString
0x140041c4a  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x140041c4e  mov     rdx, r13; SourceString
0x140041c51  call    cs:__imp_RtlDowncaseUnicodeString
0x140041c58  nop     dword ptr [rax+rax+00h]
0x140041c5d  mov     esi, eax
0x140041c5f  test    eax, eax
0x140041c61  js      loc_140041D59
0x140041c67  lea     r9, [rbp+47h+HashValue]; HashValue
0x140041c6b  xor     r8d, r8d; HashAlgorithm
0x140041c6e  mov     dl, 1; CaseInSensitive
0x140041c70  lea     rcx, [rbp+47h+DestinationString]; String
0x140041c74  call    cs:__imp_RtlHashUnicodeString
0x140041c7b  nop     dword ptr [rax+rax+00h]
0x140041c80  lea     rbx, [r14+88h]
0x140041c87  mov     esi, eax
0x140041c89  mov     rcx, rbx; Resource
0x140041c8c  call    cs:__imp_FltAcquireResourceExclusive
0x140041c93  nop     dword ptr [rax+rax+00h]
0x140041c98  mov     r8d, [rbp+47h+HashValue]; Signature
0x140041c9c  lea     rcx, [r14+0F0h]; HashTable
0x140041ca3  xor     r9d, r9d; Context
0x140041ca6  mov     rdx, rdi; Entry
0x140041ca9  call    cs:__imp_RtlInsertEntryHashTable
0x140041cb0  nop     dword ptr [rax+rax+00h]
0x140041cb5  mov     rcx, rbx; Resource
0x140041cb8  call    cs:__imp_FltReleaseResource
0x140041cbf  nop     dword ptr [rax+rax+00h]
0x140041cc4  xor     edi, edi
0x140041cc6  jmp     loc_140041D59
0x140041ccb  test    r14, r14
0x140041cce  jnz     short loc_140041CE1
0x140041cd0  lea     rcx, aParentFileDoes; "Parent file doesn't have a context; exp"...
0x140041cd7  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140041cdc  mov     esi, 0C00000E5h
0x140041ce1  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140041ce7  lea     rax, WPP_RECORDER_INITIALIZED
0x140041cee  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140041cf5  setnz   r8b
0x140041cf9  and     dl, 8
0x140041cfc  jnz     short loc_140041D03
0x140041cfe  test    r8b, r8b
0x140041d01  jz      short loc_140041D59
0x140041d03  mov     r9, cs:WPP_GLOBAL_Control
0x140041d0a  lea     rax, [r15+58h]
0x140041d0e  mov     [rsp+0F0h+var_98], rax
0x140041d13  mov     ecx, 213h
0x140041d18  mov     [rsp+0F0h+var_A0], esi
0x140041d1c  lea     rax, aOnecoreBaseFsG_6; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140041d23  mov     [rsp+0F0h+var_A8], 90h
0x140041d2b  mov     r9, [r9+40h]
0x140041d2f  mov     [rsp+0F0h+var_B0], rax
0x140041d34  lea     rax, WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids
0x140041d3b  mov     [rsp+0F0h+var_B8], rax
0x140041d40  mov     word ptr [rsp+0F0h+var_C0], 0Bh
0x140041d47  mov     dword ptr [rsp+0F0h+var_C8], 13h
0x140041d4f  mov     [rsp+0F0h+var_D0], 2
0x140041d54  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140041d59  mov     rcx, [rbp+47h+FileHandle]; FileHandle
0x140041d5d  test    rcx, rcx
0x140041d60  jz      short loc_140041D6E
0x140041d62  call    cs:__imp_FltClose
0x140041d69  nop     dword ptr [rax+rax+00h]
0x140041d6e  cmp     byte ptr [rbp+47h+FileObject], 0
0x140041d72  jz      short loc_140041D88
0x140041d74  test    r15, r15
0x140041d77  jz      short loc_140041D88
0x140041d79  mov     rcx, r15; Object
0x140041d7c  call    cs:__imp_ObfDereferenceObject
0x140041d83  nop     dword ptr [rax+rax+00h]
0x140041d88  test    r14, r14
0x140041d8b  jz      short loc_140041D9C
0x140041d8d  mov     rcx, r14; Context
0x140041d90  call    cs:__imp_FltReleaseContext
0x140041d97  nop     dword ptr [rax+rax+00h]
0x140041d9c  mov     rcx, [rbp+47h+Context]; Context
0x140041da0  test    rcx, rcx
0x140041da3  jz      short loc_140041DB1
0x140041da5  call    cs:__imp_FltReleaseContext
0x140041dac  nop     dword ptr [rax+rax+00h]
0x140041db1  test    rdi, rdi
0x140041db4  jz      short loc_140041DF9
0x140041db6  mov     rcx, [rdi+28h]; P
0x140041dba  test    rcx, rcx
0x140041dbd  jz      short loc_140041DD0
0x140041dbf  mov     edx, 6E664A50h; Tag
0x140041dc4  call    cs:__imp_ExFreePoolWithTag
0x140041dcb  nop     dword ptr [rax+rax+00h]
0x140041dd0  mov     rcx, [rdi+30h]; Context
0x140041dd4  test    rcx, rcx
0x140041dd7  jz      short loc_140041DE5
0x140041dd9  call    cs:__imp_FltReleaseContext
0x140041de0  nop     dword ptr [rax+rax+00h]
0x140041de5  mov     edx, 74684A50h; Tag
0x140041dea  mov     rcx, rdi; P
0x140041ded  call    cs:__imp_ExFreePoolWithTag
0x140041df4  nop     dword ptr [rax+rax+00h]
0x140041df9  lea     rcx, [rbp+47h+DestinationString]; UnicodeString
0x140041dfd  call    cs:__imp_RtlFreeUnicodeString
0x140041e04  nop     dword ptr [rax+rax+00h]
0x140041e09  mov     eax, esi
0x140041e0b  add     rsp, 0B8h
0x140041e12  pop     r15
0x140041e14  pop     r14
0x140041e16  pop     r13
0x140041e18  pop     r12
0x140041e1a  pop     rdi
0x140041e1b  pop     rsi
0x140041e1c  pop     rbx
0x140041e1d  pop     rbp
0x140041e1e  retn
```
