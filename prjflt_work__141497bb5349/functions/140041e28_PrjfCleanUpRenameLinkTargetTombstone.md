# PrjfCleanUpRenameLinkTargetTombstone

- ea: `0x140041e28`
- end: `0x1400422e6`
- name: `PrjfCleanUpRenameLinkTargetTombstone`
- size: `1214`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, char)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14002c3f8`
- `0x14002c98c`

## callees

- `0x140002b50`
- `0x140006570`
- `0x14000b1d0`
- `0x14000d128`
- `0x14003775c`
- `0x140041e28`
- `0x1400422ec`
- `0x140042b6c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140042226`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004224f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004227d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042226`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004224f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004227d`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400421f1`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400421f1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004207b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400420a6`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004207b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400420a6`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140042092`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140042092`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400420f8`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400420f8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140041e88`
- `ntoskrnl!RtlInitUnicodeString` at `0x140041e88`
- `FLTMGR!FltParseFileName` at `0x140041eb9`
- `FLTMGR!FltParseFileName` at `0x140041eb9`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140041fbd`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140041fbd`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140042292`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140042292`
- `FLTMGR!FltReleaseResource` at `0x1400420d4`
- `FLTMGR!FltReleaseResource` at `0x140042207`
- `FLTMGR!FltReleaseResource` at `0x1400420d4`
- `FLTMGR!FltReleaseResource` at `0x140042207`
- `FLTMGR!FltReferenceContext` at `0x1400420c1`
- `FLTMGR!FltReferenceContext` at `0x1400420c1`
- `FLTMGR!FltReleaseContext` at `0x14004223b`
- `FLTMGR!FltReleaseContext` at `0x140042263`
- `FLTMGR!FltReleaseContext` at `0x1400422a6`
- `FLTMGR!FltReleaseContext` at `0x1400422bb`
- `FLTMGR!FltReleaseContext` at `0x14004223b`
- `FLTMGR!FltReleaseContext` at `0x140042263`
- `FLTMGR!FltReleaseContext` at `0x1400422a6`
- `FLTMGR!FltReleaseContext` at `0x1400422bb`

## pseudocode

```c
__int64 __fastcall PrjfCleanUpRenameLinkTargetTombstone(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  __int64 v4; // rax
  __int64 v6; // rbx
  NTSTATUS v9; // ebx
  __int64 v10; // rdi
  int v11; // edx
  int v12; // r8d
  struct _LIST_ENTRY *v13; // r14
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v14; // rsi
  int v15; // edx
  int v16; // r8d
  BOOLEAN v17; // r15
  struct _LIST_ENTRY *Flink; // rcx
  int v19; // edx
  int Tombstone; // ebx
  int v21; // r8d
  int v22; // eax
  void *Signature; // rcx
  struct _LIST_ENTRY *v24; // rcx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY Entry; // [rsp+60h] [rbp-19h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+68h] [rbp-11h] BYREF
  __int64 v28; // [rsp+70h] [rbp-9h]
  PFLT_CONTEXT Context; // [rsp+78h] [rbp-1h]
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp+7h] BYREF
  UNICODE_STRING FileName; // [rsp+90h] [rbp+17h] BYREF
  struct _UNICODE_STRING FinalComponent; // [rsp+A0h] [rbp+27h] BYREF
  int v33; // [rsp+E0h] [rbp+67h] BYREF

  v4 = *(_QWORD *)(a1 + 16);
  Context = 0;
  v28 = 0;
  v33 = 0;
  v6 = *(_QWORD *)(v4 + 56);
  FileNameInformation = 0;
  FinalComponent = 0;
  FileName = 0;
  Entry = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  FileName.MaximumLength = *(_WORD *)(v6 + 16);
  FileName.Length = *(_WORD *)(v6 + 16);
  FileName.Buffer = (PWSTR)(v6 + 20);
  v9 = FltParseFileName(&FileName, 0, 0, &FinalComponent);
  if ( v9 < 0 )
    goto LABEL_35;
  v10 = v28;
  if ( !(unsigned __int8)PrjfGetContextFileObject(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a3 + 80)) )
    goto LABEL_35;
  v9 = PrjfLookupInMemoryTombstoneEntry(v28, &FinalComponent, 1, &v33, &Entry);
  if ( v9 == -1073741275 )
  {
    v9 = 0;
    goto LABEL_35;
  }
  if ( v9 < 0 )
  {
    if ( (BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = BYTE2(xmmword_14001A3D0) & 8;
      LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        531,
        v11,
        v12,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        19,
        33,
        (__int64)WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\tombstone.c",
        142,
        v9);
    }
    goto LABEL_35;
  }
  v13 = 0;
  if ( !a4 )
    goto LABEL_26;
  v14 = Entry;
  FltGetFileNameInformationUnsafe(*(PFILE_OBJECT *)(a3 + 80), *(PFLT_INSTANCE *)(a2 + 24), 0x301u, &FileNameInformation);
  DestinationString.MaximumLength = FileNameInformation->Name.MaximumLength + 2 + WORD1(v14[1].Linkage.Blink);
  v9 = PrjfAllocateUnicodeString(1852197456, &DestinationString);
  if ( v9 < 0 )
  {
    v17 = 0;
    if ( (BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v15) = BYTE2(xmmword_14001A3D0) & 8;
      LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        531,
        v15,
        v16,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        19,
        34,
        (__int64)WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\tombstone.c",
        172,
        v9);
    }
    goto LABEL_27;
  }
  RtlAppendUnicodeStringToString(&DestinationString, &FileNameInformation->Name);
  RtlAppendUnicodeToString(&DestinationString, L"\\");
  RtlAppendUnicodeStringToString(&DestinationString, (PCUNICODE_STRING)&v14[1].Linkage.Blink);
  Flink = v14[2].Linkage.Flink;
  if ( Flink )
  {
    v13 = v14[2].Linkage.Flink;
    FltReferenceContext(Flink);
  }
  FltReleaseResource((PERESOURCE)(v10 + 136));
  KeWaitForSingleObject(&v13[18], Executive, 0, 0, 0);
  if ( !BYTE2(v13[17].Blink) )
  {
    Tombstone = PrjfCreateTombstone(*(PFLT_INSTANCE *)(a2 + 24));
    if ( Tombstone < 0 )
    {
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v19) = xmmword_14001A3D0 & 0x20;
        LOBYTE(v21) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          517,
          v19,
          v21,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          35,
          (__int64)WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\tombstone.c",
          218,
          Tombstone);
      }
      PrjfTelemetryTombstoneFailureOperation(1, 7, (unsigned int)Tombstone);
    }
  }
  v22 = PrjfLookupInMemoryTombstoneEntry(v10, &FinalComponent, 1, &v33, &Entry);
  v9 = v22;
  if ( v22 != -1073741275 )
  {
    if ( v22 < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
LABEL_26:
    v14 = Entry;
    v17 = RtlRemoveEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(v10 + 240), Entry, 0);
LABEL_27:
    FltReleaseResource((PERESOURCE)(v10 + 136));
    if ( v17 )
    {
      Signature = (void *)v14[1].Signature;
      if ( Signature )
        ExFreePoolWithTag(Signature, 0x6E664A50u);
      v24 = v14[2].Linkage.Flink;
      if ( v24 )
        FltReleaseContext(v24);
      ExFreePoolWithTag(v14, 0x74684A50u);
    }
    goto LABEL_33;
  }
  v9 = 0;
LABEL_33:
  if ( v13 )
    FltReleaseContext(v13);
LABEL_35:
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x6E664A50u);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( Context )
    FltReleaseContext(Context);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140041e28  mov     [rsp-8+arg_8], rbx
0x140041e2d  mov     [rsp-8+arg_10], rsi
0x140041e32  push    rbp
0x140041e33  push    rdi
0x140041e34  push    r13
0x140041e36  push    r14
0x140041e38  push    r15
0x140041e3a  lea     rbp, [rsp-37h]
0x140041e3f  sub     rsp, 0B0h
0x140041e46  mov     rax, [rcx+10h]
0x140041e4a  xor     edi, edi
0x140041e4c  xorps   xmm0, xmm0
0x140041e4f  mov     [rbp+57h+Context], 0
0x140041e57  mov     r15, rdx
0x140041e5a  mov     [rbp+57h+var_60], rdi
0x140041e5e  xorps   xmm1, xmm1
0x140041e61  mov     [rbp+57h+arg_0], edi
0x140041e64  mov     rbx, [rax+38h]
0x140041e68  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140041e6c  xor     edx, edx; SourceString
0x140041e6e  mov     [rbp+57h+FileNameInformation], rdi
0x140041e72  movups  xmmword ptr [rbp+57h+FinalComponent.Length], xmm0
0x140041e76  mov     sil, r9b
0x140041e79  mov     r13, r8
0x140041e7c  movups  xmmword ptr [rbp+57h+FileName.Length], xmm1
0x140041e80  mov     [rbp+57h+Entry], rdi
0x140041e84  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140041e88  call    cs:__imp_RtlInitUnicodeString
0x140041e8f  nop     dword ptr [rax+rax+00h]
0x140041e94  movzx   eax, word ptr [rbx+10h]
0x140041e98  lea     r9, [rbp+57h+FinalComponent]; FinalComponent
0x140041e9c  mov     [rbp+57h+FileName.MaximumLength], ax
0x140041ea0  lea     rcx, [rbp+57h+FileName]; FileName
0x140041ea4  movzx   eax, word ptr [rbx+10h]
0x140041ea8  xor     r8d, r8d; Stream
0x140041eab  mov     [rbp+57h+FileName.Length], ax
0x140041eaf  xor     edx, edx; Extension
0x140041eb1  lea     rax, [rbx+14h]
0x140041eb5  mov     [rbp+57h+FileName.Buffer], rax
0x140041eb9  call    cs:__imp_FltParseFileName
0x140041ec0  nop     dword ptr [rax+rax+00h]
0x140041ec5  mov     ebx, eax
0x140041ec7  test    eax, eax
0x140041ec9  js      loc_14004226F
0x140041ecf  mov     rdx, [r13+50h]; FileObject
0x140041ed3  lea     r9, [rbp+57h+Context]
0x140041ed7  mov     rcx, [r15+18h]; Instance
0x140041edb  lea     r8, [rbp+57h+var_60]
0x140041edf  call    PrjfGetContextFileObject
0x140041ee4  mov     rdi, [rbp+57h+var_60]
0x140041ee8  test    al, al
0x140041eea  jz      loc_14004226F
0x140041ef0  lea     rax, [rbp+57h+Entry]
0x140041ef4  mov     r8d, 1
0x140041efa  lea     r9, [rbp+57h+arg_0]
0x140041efe  mov     [rsp+0D0h+Timeout], rax
0x140041f03  lea     rdx, [rbp+57h+FinalComponent]
0x140041f07  mov     rcx, rdi
0x140041f0a  call    PrjfLookupInMemoryTombstoneEntry
0x140041f0f  mov     ebx, eax
0x140041f11  cmp     eax, 0C0000225h
0x140041f16  jnz     short loc_140041F1F
0x140041f18  xor     ebx, ebx
0x140041f1a  jmp     loc_14004226F
0x140041f1f  test    ebx, ebx
0x140041f21  jns     short loc_140041F9B
0x140041f23  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140041f29  lea     rax, WPP_RECORDER_INITIALIZED
0x140041f30  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140041f37  setnz   r8b
0x140041f3b  and     dl, 8
0x140041f3e  jnz     short loc_140041F49
0x140041f40  test    r8b, r8b
0x140041f43  jz      loc_14004226F
0x140041f49  mov     r9, cs:WPP_GLOBAL_Control
0x140041f50  lea     rax, aOnecoreBaseFsG_6; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140041f57  mov     [rsp+0D0h+var_80], ebx
0x140041f5b  mov     ecx, 213h
0x140041f60  mov     [rsp+0D0h+var_88], 68Eh
0x140041f68  mov     [rsp+0D0h+var_90], rax
0x140041f6d  lea     rax, WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids
0x140041f74  mov     r9, [r9+40h]
0x140041f78  mov     [rsp+0D0h+var_98], rax
0x140041f7d  mov     [rsp+0D0h+var_A0], 21h ; '!'
0x140041f84  mov     [rsp+0D0h+var_A8], 13h
0x140041f8c  mov     byte ptr [rsp+0D0h+Timeout], 2
0x140041f91  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140041f96  jmp     loc_14004226F
0x140041f9b  xor     r14d, r14d
0x140041f9e  test    sil, sil
0x140041fa1  jz      loc_1400421E0
0x140041fa7  mov     rdx, [r15+18h]; Instance
0x140041fab  lea     r9, [rbp+57h+FileNameInformation]; FileNameInformation
0x140041faf  mov     rcx, [r13+50h]; FileObject
0x140041fb3  mov     r8d, 301h; NameOptions
0x140041fb9  mov     rsi, [rbp+57h+Entry]
0x140041fbd  call    cs:__imp_FltGetFileNameInformationUnsafe
0x140041fc4  nop     dword ptr [rax+rax+00h]
0x140041fc9  mov     rax, [rbp+57h+FileNameInformation]
0x140041fcd  lea     rdx, [rbp+57h+DestinationString]
0x140041fd1  movzx   ecx, word ptr [rax+0Ah]
0x140041fd5  movzx   eax, word ptr [rsi+22h]
0x140041fd9  add     cx, 2
0x140041fdd  add     ax, cx
0x140041fe0  mov     ecx, 6E664A50h
0x140041fe5  mov     [rbp+57h+DestinationString.MaximumLength], ax
0x140041fe9  call    PrjfAllocateUnicodeString
0x140041fee  mov     ebx, eax
0x140041ff0  test    eax, eax
0x140041ff2  jns     short loc_14004206F
0x140041ff4  xor     r15b, r15b
0x140041ff7  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140041ffd  lea     rax, WPP_RECORDER_INITIALIZED
0x140042004  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004200b  setnz   r8b
0x14004200f  and     dl, 8
0x140042012  jnz     short loc_14004201D
0x140042014  test    r8b, r8b
0x140042017  jz      loc_140042200
0x14004201d  mov     r9, cs:WPP_GLOBAL_Control
0x140042024  lea     rax, aOnecoreBaseFsG_6; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14004202b  mov     [rsp+0D0h+var_80], ebx
0x14004202f  mov     ecx, 213h
0x140042034  mov     [rsp+0D0h+var_88], 6ACh
0x14004203c  mov     [rsp+0D0h+var_90], rax
0x140042041  lea     rax, WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids
0x140042048  mov     r9, [r9+40h]
0x14004204c  mov     [rsp+0D0h+var_98], rax
0x140042051  mov     [rsp+0D0h+var_A0], 22h ; '"'
0x140042058  mov     [rsp+0D0h+var_A8], 13h
0x140042060  mov     byte ptr [rsp+0D0h+Timeout], 2
0x140042065  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14004206a  jmp     loc_140042200
0x14004206f  mov     rdx, [rbp+57h+FileNameInformation]
0x140042073  lea     rcx, [rbp+57h+DestinationString]; Destination
0x140042077  add     rdx, 8; Source
0x14004207b  call    cs:__imp_RtlAppendUnicodeStringToString
0x140042082  nop     dword ptr [rax+rax+00h]
0x140042087  lea     rdx, asc_14001595C; "\\"
0x14004208e  lea     rcx, [rbp+57h+DestinationString]; Destination
0x140042092  call    cs:__imp_RtlAppendUnicodeToString
0x140042099  nop     dword ptr [rax+rax+00h]
0x14004209e  lea     rdx, [rsi+20h]; Source
0x1400420a2  lea     rcx, [rbp+57h+DestinationString]; Destination
0x1400420a6  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400420ad  nop     dword ptr [rax+rax+00h]
0x1400420b2  mov     rcx, [rsi+30h]; Context
0x1400420b6  mov     bl, [rsi+18h]
0x1400420b9  test    rcx, rcx
0x1400420bc  jz      short loc_1400420CD
0x1400420be  mov     r14, rcx
0x1400420c1  call    cs:__imp_FltReferenceContext
0x1400420c8  nop     dword ptr [rax+rax+00h]
0x1400420cd  lea     rcx, [rdi+88h]; Resource
0x1400420d4  call    cs:__imp_FltReleaseResource
0x1400420db  nop     dword ptr [rax+rax+00h]
0x1400420e0  lea     rcx, [r14+120h]; Object
0x1400420e7  mov     [rsp+0D0h+Timeout], 0; Timeout
0x1400420f0  xor     r9d, r9d; Alertable
0x1400420f3  xor     r8d, r8d; WaitMode
0x1400420f6  xor     edx, edx; WaitReason
0x1400420f8  call    cs:__imp_KeWaitForSingleObject
0x1400420ff  nop     dword ptr [rax+rax+00h]
0x140042104  mov     al, [r14+11Ah]
0x14004210b  test    al, al
0x14004210d  jnz     loc_1400421A8
0x140042113  mov     rcx, [r15+18h]; Instance
0x140042117  lea     rdx, [rbp+57h+DestinationString]
0x14004211b  mov     r8b, bl
0x14004211e  call    PrjfCreateTombstone
0x140042123  mov     ebx, eax
0x140042125  test    eax, eax
0x140042127  jns     short loc_1400421A8
0x140042129  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14004212f  lea     rax, WPP_RECORDER_INITIALIZED
0x140042136  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004213d  setnz   r8b
0x140042141  and     dl, 20h
0x140042144  jnz     short loc_14004214B
0x140042146  test    r8b, r8b
0x140042149  jz      short loc_140042198
0x14004214b  mov     r9, cs:WPP_GLOBAL_Control
0x140042152  lea     rax, aOnecoreBaseFsG_6; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140042159  mov     [rsp+0D0h+var_80], ebx
0x14004215d  mov     ecx, 205h
0x140042162  mov     [rsp+0D0h+var_88], 6DAh
0x14004216a  mov     [rsp+0D0h+var_90], rax
0x14004216f  lea     rax, WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids
0x140042176  mov     r9, [r9+40h]
0x14004217a  mov     [rsp+0D0h+var_98], rax
0x14004217f  mov     [rsp+0D0h+var_A0], 23h ; '#'
0x140042186  mov     [rsp+0D0h+var_A8], 5
0x14004218e  mov     byte ptr [rsp+0D0h+Timeout], 2
0x140042193  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140042198  mov     edx, 7
0x14004219d  mov     r8d, ebx
0x1400421a0  lea     ecx, [rdx-6]
0x1400421a3  call    PrjfTelemetryTombstoneFailureOperation
0x1400421a8  lea     rax, [rbp+57h+Entry]
0x1400421ac  mov     r8d, 1
0x1400421b2  lea     r9, [rbp+57h+arg_0]
0x1400421b6  mov     [rsp+0D0h+Timeout], rax
0x1400421bb  lea     rdx, [rbp+57h+FinalComponent]
0x1400421bf  mov     rcx, rdi
0x1400421c2  call    PrjfLookupInMemoryTombstoneEntry
0x1400421c7  mov     ebx, eax
0x1400421c9  cmp     eax, 0C0000225h
0x1400421ce  jnz     short loc_1400421D7
0x1400421d0  xor     ebx, ebx
0x1400421d2  jmp     loc_14004225B
0x1400421d7  test    eax, eax
0x1400421d9  jns     short loc_1400421E0
0x1400421db  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400421e0  mov     rsi, [rbp+57h+Entry]
0x1400421e4  lea     rcx, [rdi+0F0h]; HashTable
0x1400421eb  mov     rdx, rsi; Entry
0x1400421ee  xor     r8d, r8d; Context
0x1400421f1  call    cs:__imp_RtlRemoveEntryHashTable
0x1400421f8  nop     dword ptr [rax+rax+00h]
0x1400421fd  mov     r15b, al
0x140042200  lea     rcx, [rdi+88h]; Resource
0x140042207  call    cs:__imp_FltReleaseResource
0x14004220e  nop     dword ptr [rax+rax+00h]
0x140042213  test    r15b, r15b
0x140042216  jz      short loc_14004225B
0x140042218  mov     rcx, [rsi+28h]; P
0x14004221c  test    rcx, rcx
0x14004221f  jz      short loc_140042232
0x140042221  mov     edx, 6E664A50h; Tag
0x140042226  call    cs:__imp_ExFreePoolWithTag
0x14004222d  nop     dword ptr [rax+rax+00h]
0x140042232  mov     rcx, [rsi+30h]; Context
0x140042236  test    rcx, rcx
0x140042239  jz      short loc_140042247
0x14004223b  call    cs:__imp_FltReleaseContext
0x140042242  nop     dword ptr [rax+rax+00h]
0x140042247  mov     edx, 74684A50h; Tag
0x14004224c  mov     rcx, rsi; P
0x14004224f  call    cs:__imp_ExFreePoolWithTag
0x140042256  nop     dword ptr [rax+rax+00h]
0x14004225b  test    r14, r14
0x14004225e  jz      short loc_14004226F
0x140042260  mov     rcx, r14; Context
0x140042263  call    cs:__imp_FltReleaseContext
0x14004226a  nop     dword ptr [rax+rax+00h]
0x14004226f  mov     rcx, [rbp+57h+DestinationString.Buffer]; P
0x140042273  test    rcx, rcx
0x140042276  jz      short loc_140042289
0x140042278  mov     edx, 6E664A50h; Tag
0x14004227d  call    cs:__imp_ExFreePoolWithTag
0x140042284  nop     dword ptr [rax+rax+00h]
0x140042289  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x14004228d  test    rcx, rcx
0x140042290  jz      short loc_14004229E
0x140042292  call    cs:__imp_FltReleaseFileNameInformation
0x140042299  nop     dword ptr [rax+rax+00h]
0x14004229e  test    rdi, rdi
0x1400422a1  jz      short loc_1400422B2
0x1400422a3  mov     rcx, rdi; Context
0x1400422a6  call    cs:__imp_FltReleaseContext
0x1400422ad  nop     dword ptr [rax+rax+00h]
0x1400422b2  mov     rcx, [rbp+57h+Context]; Context
0x1400422b6  test    rcx, rcx
0x1400422b9  jz      short loc_1400422C7
0x1400422bb  call    cs:__imp_FltReleaseContext
0x1400422c2  nop     dword ptr [rax+rax+00h]
0x1400422c7  lea     r11, [rsp+0D0h+var_20]
0x1400422cf  mov     eax, ebx
0x1400422d1  mov     rbx, [r11+38h]
0x1400422d5  mov     rsi, [r11+40h]
0x1400422d9  mov     rsp, r11
0x1400422dc  pop     r15
0x1400422de  pop     r14
0x1400422e0  pop     r13
0x1400422e2  pop     rdi
0x1400422e3  pop     rbp
0x1400422e4  retn
```
