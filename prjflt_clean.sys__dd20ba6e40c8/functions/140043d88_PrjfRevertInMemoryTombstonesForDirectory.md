# PrjfRevertInMemoryTombstonesForDirectory

- ea: `0x140043d88`
- end: `0x1400442e6`
- name: `PrjfRevertInMemoryTombstonesForDirectory`
- size: `1374`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `5`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140009d20`
- `0x14002bc38`
- `0x14002bf00`
- `0x14003d620`
- `0x140040670`

## callees

- `0x140002b50`
- `0x140006570`
- `0x14000ba20`
- `0x14000d128`
- `0x14003775c`
- `0x1400422ec`
- `0x140043d88`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140044143`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400441a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400441ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044143`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400441a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400441ca`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140043f95`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140043fad`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140043f95`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140043fad`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140044187`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140044187`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x140043f73`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x140043f73`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140043f57`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140043f57`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400441dd`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400441dd`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140044169`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140044169`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140043ff9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140044024`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140043ff9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140044024`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140044010`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140044010`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004407a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004407a`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140043edf`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140043edf`
- `FLTMGR!FltParseFileNameInformation` at `0x140043ef9`
- `FLTMGR!FltParseFileNameInformation` at `0x140043ef9`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140043f19`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140044152`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140043f19`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140044152`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140044287`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140044287`
- `FLTMGR!FltReleaseResource` at `0x140044052`
- `FLTMGR!FltReleaseResource` at `0x140044272`
- `FLTMGR!FltReleaseResource` at `0x140044052`
- `FLTMGR!FltReleaseResource` at `0x140044272`
- `FLTMGR!FltQueryInformationFile` at `0x140043e08`
- `FLTMGR!FltQueryInformationFile` at `0x140043e08`
- `FLTMGR!FltReferenceContext` at `0x140044043`
- `FLTMGR!FltReferenceContext` at `0x140044043`
- `FLTMGR!FltReleaseContext` at `0x140044129`
- `FLTMGR!FltReleaseContext` at `0x1400441b6`
- `FLTMGR!FltReleaseContext` at `0x14004429b`
- `FLTMGR!FltReleaseContext` at `0x1400442b0`
- `FLTMGR!FltReleaseContext` at `0x140044129`
- `FLTMGR!FltReleaseContext` at `0x1400441b6`
- `FLTMGR!FltReleaseContext` at `0x14004429b`
- `FLTMGR!FltReleaseContext` at `0x1400442b0`

## pseudocode

```c
__int64 __fastcall PrjfRevertInMemoryTombstonesForDirectory(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)
{
  NTSTATUS v4; // eax
  int v5; // edx
  int v6; // r8d
  NTSTATUS FileNameInformationUnsafe; // ebx
  char v8; // si
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v9; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v10; // rsi
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // eax
  int v14; // edx
  int v15; // r8d
  struct _LIST_ENTRY *Flink; // rax
  char v17; // si
  int v18; // eax
  int v19; // edx
  int v20; // r8d
  PRTL_DYNAMIC_HASH_TABLE_ENTRY i; // rax
  void *v22; // rcx
  void *v23; // rcx
  _QWORD *p_Flink; // rsi
  char v26; // [rsp+60h] [rbp-79h]
  struct _LIST_ENTRY *Context; // [rsp+68h] [rbp-71h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+70h] [rbp-69h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+78h] [rbp-61h] BYREF
  PFLT_CONTEXT v30; // [rsp+88h] [rbp-51h]
  ULONG_PTR Signature; // [rsp+90h] [rbp-49h]
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT v32; // [rsp+98h] [rbp-41h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+B0h] [rbp-29h] BYREF
  __int128 FileInformation; // [rsp+D8h] [rbp-1h] BYREF
  __int64 v35; // [rsp+E8h] [rbp+Fh]

  v30 = 0;
  FileNameInformation = 0;
  v35 = 0;
  memset(&Enumerator, 0, sizeof(Enumerator));
  FileInformation = 0;
  Destination = 0;
  memset(&v32, 0, sizeof(v32));
  v4 = FltQueryInformationFile(Instance, FileObject, &FileInformation, 0x18u, FileStandardInformation, 0);
  FileNameInformationUnsafe = v4;
  if ( v4 >= 0 )
  {
    if ( !BYTE6(v35) )
    {
      if ( BYTE5(v35) )
      {
        if ( (unsigned __int8)PrjfGetContextFileObject(Instance, FileObject) )
        {
          if ( MEMORY[0x104] )
          {
            FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(
                                          FileObject,
                                          Instance,
                                          0x301u,
                                          &FileNameInformation);
            if ( FileNameInformationUnsafe >= 0 )
            {
              FileNameInformationUnsafe = FltParseFileNameInformation(FileNameInformation);
              if ( FileNameInformationUnsafe >= 0 )
              {
                FltAcquireResourceExclusive((PERESOURCE)0x88);
                v8 = 1;
                v26 = 1;
                if ( MEMORY[0x104] )
                {
                  while ( 2 )
                  {
                    if ( v8 )
                    {
                      RtlInitEnumerationHashTable((PRTL_DYNAMIC_HASH_TABLE)0xF0, &Enumerator);
                      do
                      {
                        v9 = RtlEnumerateEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)0xF0, &Enumerator);
                        v10 = v9;
                        if ( !v9 )
                        {
                          v8 = 0;
                          v26 = 0;
                          RtlEndEnumerationHashTable((PRTL_DYNAMIC_HASH_TABLE)0xF0, &Enumerator);
                          goto LABEL_36;
                        }
                      }
                      while ( !v9[2].Linkage.Flink );
                      RtlEndEnumerationHashTable((PRTL_DYNAMIC_HASH_TABLE)0xF0, &Enumerator);
                      Signature = v10->Signature;
                      Destination.MaximumLength = WORD1(v10[1].Linkage.Blink)
                                                + FileNameInformation->Name.MaximumLength
                                                + 2;
                      v13 = PrjfAllocateUnicodeString(1852197456, &Destination, v11, v12);
                      FileNameInformationUnsafe = v13;
                      if ( v13 < 0 )
                      {
                        if ( (BYTE2(xmmword_14001A3D0) & 8) != 0
                          || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                        {
                          LOBYTE(v14) = BYTE2(xmmword_14001A3D0) & 8;
                          LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                          WPP_RECORDER_AND_TRACE_SF_sDL(
                            531,
                            v14,
                            v15,
                            *((_QWORD *)WPP_GLOBAL_Control + 8),
                            2,
                            19,
                            37,
                            (__int64)&WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids,
                            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\tombstone.c",
                            242,
                            v13);
                        }
                        break;
                      }
                      RtlAppendUnicodeStringToString(&Destination, &FileNameInformation->Name);
                      RtlAppendUnicodeToString(&Destination, L"\\");
                      RtlAppendUnicodeStringToString(&Destination, (PCUNICODE_STRING)&v10[1].Linkage.Blink);
                      Flink = v10[2].Linkage.Flink;
                      BYTE1(v10[1].Linkage.Flink) = 1;
                      v17 = (char)v10[1].Linkage.Flink;
                      Context = Flink;
                      FltReferenceContext(Flink);
                      FltReleaseResource((PERESOURCE)0x88);
                      KeWaitForSingleObject(&Context[18], Executive, 0, 0, 0);
                      if ( !BYTE2(Context[17].Blink) )
                      {
                        v18 = PrjfCreateTombstone(Instance, &Destination, v17);
                        FileNameInformationUnsafe = v18;
                        if ( v18 < 0 )
                        {
                          if ( (xmmword_14001A3D0 & 0x20) != 0
                            || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                          {
                            LOBYTE(v19) = xmmword_14001A3D0 & 0x20;
                            LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                            WPP_RECORDER_AND_TRACE_SF_sDL(
                              517,
                              v19,
                              v20,
                              *((_QWORD *)WPP_GLOBAL_Control + 8),
                              2,
                              5,
                              38,
                              (__int64)&WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids,
                              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\tombstone.c",
                              38,
                              v18);
                          }
                          PrjfTelemetryTombstoneFailureOperation(1, 6, (unsigned int)FileNameInformationUnsafe);
                        }
                      }
                      FltReleaseContext(Context);
                      if ( Destination.Buffer )
                        ExFreePoolWithTag(Destination.Buffer, 0x6E664A50u);
                      FltAcquireResourceExclusive((PERESOURCE)0x88);
                      for ( i = RtlLookupEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)0xF0, Signature, &v32);
                            ;
                            i = RtlGetNextEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)0xF0, &v32) )
                      {
                        p_Flink = &i->Linkage.Flink;
                        if ( !i )
                          break;
                        if ( BYTE1(i[1].Linkage.Flink) )
                        {
                          RtlRemoveEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)0xF0, i, &v32);
                          v22 = (void *)p_Flink[5];
                          if ( v22 )
                            ExFreePoolWithTag(v22, 0x6E664A50u);
                          v23 = (void *)p_Flink[6];
                          if ( v23 )
                            FltReleaseContext(v23);
                          ExFreePoolWithTag(p_Flink, 0x74684A50u);
                        }
                      }
                      v8 = v26;
LABEL_36:
                      if ( MEMORY[0x104] )
                        continue;
                    }
                    break;
                  }
                }
                FltReleaseResource((PERESOURCE)0x88);
              }
            }
          }
        }
      }
    }
  }
  else if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = xmmword_14001A3D0 & 0x20;
    LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      517,
      v5,
      v6,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      5,
      36,
      (__int64)&WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\tombstone.c",
      125,
      v4);
  }
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( v30 )
    FltReleaseContext(v30);
  return (unsigned int)FileNameInformationUnsafe;
}

```

## disassembly

```asm
0x140043d88  mov     [rsp-8+arg_10], rbx
0x140043d8d  push    rbp
0x140043d8e  push    rsi
0x140043d8f  push    rdi
0x140043d90  push    r12
0x140043d92  push    r13
0x140043d94  push    r14
0x140043d96  push    r15
0x140043d98  lea     rbp, [rsp-27h]
0x140043d9d  sub     rsp, 100h
0x140043da4  mov     rax, cs:__security_cookie
0x140043dab  xor     rax, rsp
0x140043dae  mov     [rbp+57h+var_40], rax
0x140043db2  xor     r14d, r14d
0x140043db5  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140043db9  xorps   xmm0, xmm0
0x140043dbc  mov     [rsp+130h+LengthReturned], r14; LengthReturned
0x140043dc1  xor     eax, eax
0x140043dc3  mov     [rbp+57h+var_A8], r14
0x140043dc7  xorps   xmm1, xmm1
0x140043dca  mov     [rbp+57h+Context], r14
0x140043dce  lea     r12d, [r14+5]
0x140043dd2  mov     qword ptr [rbp+57h+Enumerator.BucketIndex], rax
0x140043dd6  lea     r9d, [r14+18h]; Length
0x140043dda  mov     [rsp+130h+FileInformationClass], r12d; FileInformationClass
0x140043ddf  mov     rsi, rdx
0x140043de2  mov     [rbp+57h+FileNameInformation], r14
0x140043de6  mov     r13, rcx
0x140043de9  mov     [rbp+57h+var_48], rax
0x140043ded  mov     edi, r14d
0x140043df0  mov     [rbp+57h+var_98.Signature], rax
0x140043df4  movups  xmmword ptr [rbp+57h+Enumerator], xmm0
0x140043df8  movups  xmmword ptr [rbp+57h+Enumerator+10h], xmm0
0x140043dfc  movups  [rbp+57h+FileInformation], xmm0
0x140043e00  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x140043e04  movups  xmmword ptr [rbp+57h+var_98.ChainHead], xmm1
0x140043e08  call    cs:__imp_FltQueryInformationFile
0x140043e0f  nop     dword ptr [rax+rax+00h]
0x140043e14  mov     ebx, eax
0x140043e16  test    eax, eax
0x140043e18  jns     short loc_140043E8F
0x140043e1a  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140043e20  lea     r15, WPP_RECORDER_INITIALIZED
0x140043e27  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140043e2e  setnz   r8b
0x140043e32  and     dl, 20h
0x140043e35  jnz     short loc_140043E40
0x140043e37  test    r8b, r8b
0x140043e3a  jz      loc_14004427E
0x140043e40  mov     r9, cs:WPP_GLOBAL_Control
0x140043e47  mov     ecx, 205h
0x140043e4c  mov     [rsp+130h+var_E0], eax
0x140043e50  lea     rax, aOnecoreBaseFsG_6; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140043e57  mov     [rsp+130h+var_E8], 77Dh
0x140043e5f  mov     [rsp+130h+var_F0], rax
0x140043e64  lea     rax, WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids
0x140043e6b  mov     r9, [r9+40h]
0x140043e6f  mov     [rsp+130h+var_F8], rax
0x140043e74  mov     [rsp+130h+var_100], 24h ; '$'
0x140043e7b  mov     dword ptr [rsp+130h+LengthReturned], r12d
0x140043e80  mov     byte ptr [rsp+130h+FileInformationClass], 2
0x140043e85  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140043e8a  jmp     loc_14004427E
0x140043e8f  cmp     byte ptr [rbp+57h+var_48+6], r14b
0x140043e93  jnz     loc_14004427E
0x140043e99  cmp     byte ptr [rbp+57h+var_48+5], r14b
0x140043e9d  jz      loc_14004427E
0x140043ea3  lea     r9, [rbp+57h+var_A8]
0x140043ea7  mov     rdx, rsi; FileObject
0x140043eaa  lea     r8, [rbp+57h+Context]
0x140043eae  mov     rcx, r13; Instance
0x140043eb1  call    PrjfGetContextFileObject
0x140043eb6  mov     rdi, [rbp+57h+Context]
0x140043eba  test    al, al
0x140043ebc  jz      loc_14004427E
0x140043ec2  cmp     [rdi+104h], r14d
0x140043ec9  jz      loc_14004427E
0x140043ecf  lea     r9, [rbp+57h+FileNameInformation]; FileNameInformation
0x140043ed3  mov     r8d, 301h; NameOptions
0x140043ed9  mov     rdx, r13; Instance
0x140043edc  mov     rcx, rsi; FileObject
0x140043edf  call    cs:__imp_FltGetFileNameInformationUnsafe
0x140043ee6  nop     dword ptr [rax+rax+00h]
0x140043eeb  mov     ebx, eax
0x140043eed  test    eax, eax
0x140043eef  js      loc_14004427E
0x140043ef5  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140043ef9  call    cs:__imp_FltParseFileNameInformation
0x140043f00  nop     dword ptr [rax+rax+00h]
0x140043f05  mov     ebx, eax
0x140043f07  test    eax, eax
0x140043f09  js      loc_14004427E
0x140043f0f  lea     r12, [rdi+88h]
0x140043f16  mov     rcx, r12; Resource
0x140043f19  call    cs:__imp_FltAcquireResourceExclusive
0x140043f20  nop     dword ptr [rax+rax+00h]
0x140043f25  mov     sil, 1
0x140043f28  mov     [rbp+57h+var_D0], sil
0x140043f2c  cmp     [rdi+104h], r14d
0x140043f33  jz      loc_14004426F
0x140043f39  lea     r15, WPP_RECORDER_INITIALIZED
0x140043f40  test    sil, sil
0x140043f43  jz      loc_14004426F
0x140043f49  lea     r14, [rdi+0F0h]
0x140043f50  mov     rcx, r14; HashTable
0x140043f53  lea     rdx, [rbp+57h+Enumerator]; Enumerator
0x140043f57  call    cs:__imp_RtlInitEnumerationHashTable
0x140043f5e  nop     dword ptr [rax+rax+00h]
0x140043f63  jmp     short loc_140043F6C
0x140043f65  cmp     qword ptr [rsi+30h], 0
0x140043f6a  jnz     short loc_140043FA6
0x140043f6c  lea     rdx, [rbp+57h+Enumerator]; Enumerator
0x140043f70  mov     rcx, r14; HashTable
0x140043f73  call    cs:__imp_RtlEnumerateEntryHashTable
0x140043f7a  nop     dword ptr [rax+rax+00h]
0x140043f7f  mov     rsi, rax
0x140043f82  test    rax, rax
0x140043f85  jnz     short loc_140043F65
0x140043f87  xor     sil, sil
0x140043f8a  lea     rdx, [rbp+57h+Enumerator]; Enumerator
0x140043f8e  mov     rcx, r14; HashTable
0x140043f91  mov     [rbp+57h+var_D0], sil
0x140043f95  call    cs:__imp_RtlEndEnumerationHashTable
0x140043f9c  nop     dword ptr [rax+rax+00h]
0x140043fa1  jmp     loc_1400441F5
0x140043fa6  lea     rdx, [rbp+57h+Enumerator]; Enumerator
0x140043faa  mov     rcx, r14; HashTable
0x140043fad  call    cs:__imp_RtlEndEnumerationHashTable
0x140043fb4  nop     dword ptr [rax+rax+00h]
0x140043fb9  mov     rax, [rsi+10h]
0x140043fbd  mov     ecx, 6E664A50h
0x140043fc2  mov     [rbp+57h+Signature], rax
0x140043fc6  mov     rax, [rbp+57h+FileNameInformation]
0x140043fca  movzx   edx, word ptr [rax+0Ah]
0x140043fce  add     dx, 2
0x140043fd2  add     dx, [rsi+22h]
0x140043fd6  mov     [rbp+57h+Destination.MaximumLength], dx
0x140043fda  lea     rdx, [rbp+57h+Destination]
0x140043fde  call    PrjfAllocateUnicodeString
0x140043fe3  mov     ebx, eax
0x140043fe5  test    eax, eax
0x140043fe7  js      loc_140044207
0x140043fed  mov     rdx, [rbp+57h+FileNameInformation]
0x140043ff1  lea     rcx, [rbp+57h+Destination]; Destination
0x140043ff5  add     rdx, 8; Source
0x140043ff9  call    cs:__imp_RtlAppendUnicodeStringToString
0x140044000  nop     dword ptr [rax+rax+00h]
0x140044005  lea     rdx, asc_14001595C; "\\"
0x14004400c  lea     rcx, [rbp+57h+Destination]; Destination
0x140044010  call    cs:__imp_RtlAppendUnicodeToString
0x140044017  nop     dword ptr [rax+rax+00h]
0x14004401c  lea     rdx, [rsi+20h]; Source
0x140044020  lea     rcx, [rbp+57h+Destination]; Destination
0x140044024  call    cs:__imp_RtlAppendUnicodeStringToString
0x14004402b  nop     dword ptr [rax+rax+00h]
0x140044030  mov     rax, [rsi+30h]
0x140044034  mov     byte ptr [rsi+19h], 1
0x140044038  mov     rcx, rax; Context
0x14004403b  mov     sil, [rsi+18h]
0x14004403f  mov     [rbp+57h+Context], rax
0x140044043  call    cs:__imp_FltReferenceContext
0x14004404a  nop     dword ptr [rax+rax+00h]
0x14004404f  mov     rcx, r12; Resource
0x140044052  call    cs:__imp_FltReleaseResource
0x140044059  nop     dword ptr [rax+rax+00h]
0x14004405e  mov     rcx, [rbp+57h+Context]
0x140044062  xor     r9d, r9d; Alertable
0x140044065  add     rcx, 120h; Object
0x14004406c  mov     qword ptr [rsp+130h+FileInformationClass], 0; Timeout
0x140044075  xor     r8d, r8d; WaitMode
0x140044078  xor     edx, edx; WaitReason
0x14004407a  call    cs:__imp_KeWaitForSingleObject
0x140044081  nop     dword ptr [rax+rax+00h]
0x140044086  mov     rcx, [rbp+57h+Context]
0x14004408a  mov     al, [rcx+11Ah]
0x140044090  test    al, al
0x140044092  jnz     loc_140044125
0x140044098  mov     r8b, sil
0x14004409b  lea     rdx, [rbp+57h+Destination]
0x14004409f  mov     rcx, r13; Instance
0x1400440a2  call    PrjfCreateTombstone
0x1400440a7  mov     ebx, eax
0x1400440a9  test    eax, eax
0x1400440ab  jns     short loc_140044125
0x1400440ad  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400440b4  mov     dl, byte ptr cs:xmmword_14001A3D0
0x1400440ba  setnz   r8b
0x1400440be  and     dl, 20h
0x1400440c1  jnz     short loc_1400440C8
0x1400440c3  test    r8b, r8b
0x1400440c6  jz      short loc_140044115
0x1400440c8  mov     r9, cs:WPP_GLOBAL_Control
0x1400440cf  lea     rax, aOnecoreBaseFsG_6; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400440d6  mov     [rsp+130h+var_E0], ebx
0x1400440da  mov     ecx, 205h
0x1400440df  mov     [rsp+130h+var_E8], 826h
0x1400440e7  mov     [rsp+130h+var_F0], rax
0x1400440ec  lea     rax, WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids
0x1400440f3  mov     r9, [r9+40h]
0x1400440f7  mov     [rsp+130h+var_F8], rax
0x1400440fc  mov     [rsp+130h+var_100], 26h ; '&'
0x140044103  mov     dword ptr [rsp+130h+LengthReturned], 5
0x14004410b  mov     byte ptr [rsp+130h+FileInformationClass], 2
0x140044110  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140044115  mov     edx, 6
0x14004411a  mov     r8d, ebx
0x14004411d  lea     ecx, [rdx-5]
0x140044120  call    PrjfTelemetryTombstoneFailureOperation
0x140044125  mov     rcx, [rbp+57h+Context]; Context
0x140044129  call    cs:__imp_FltReleaseContext
0x140044130  nop     dword ptr [rax+rax+00h]
0x140044135  mov     rcx, [rbp+57h+Destination.Buffer]; P
0x140044139  test    rcx, rcx
0x14004413c  jz      short loc_14004414F
0x14004413e  mov     edx, 6E664A50h; Tag
0x140044143  call    cs:__imp_ExFreePoolWithTag
0x14004414a  nop     dword ptr [rax+rax+00h]
0x14004414f  mov     rcx, r12; Resource
0x140044152  call    cs:__imp_FltAcquireResourceExclusive
0x140044159  nop     dword ptr [rax+rax+00h]
0x14004415e  mov     rdx, [rbp+57h+Signature]; Signature
0x140044162  lea     r8, [rbp+57h+var_98]; Context
0x140044166  mov     rcx, r14; HashTable
0x140044169  call    cs:__imp_RtlLookupEntryHashTable
0x140044170  nop     dword ptr [rax+rax+00h]
0x140044175  jmp     short loc_1400441E9
0x140044177  cmp     byte ptr [rsi+19h], 0
0x14004417b  jz      short loc_1400441D6
0x14004417d  lea     r8, [rbp+57h+var_98]; Context
0x140044181  mov     rdx, rsi; Entry
0x140044184  mov     rcx, r14; HashTable
0x140044187  call    cs:__imp_RtlRemoveEntryHashTable
0x14004418e  nop     dword ptr [rax+rax+00h]
0x140044193  mov     rcx, [rsi+28h]; P
0x140044197  test    rcx, rcx
0x14004419a  jz      short loc_1400441AD
0x14004419c  mov     edx, 6E664A50h; Tag
0x1400441a1  call    cs:__imp_ExFreePoolWithTag
0x1400441a8  nop     dword ptr [rax+rax+00h]
0x1400441ad  mov     rcx, [rsi+30h]; Context
0x1400441b1  test    rcx, rcx
0x1400441b4  jz      short loc_1400441C2
0x1400441b6  call    cs:__imp_FltReleaseContext
0x1400441bd  nop     dword ptr [rax+rax+00h]
0x1400441c2  mov     edx, 74684A50h; Tag
0x1400441c7  mov     rcx, rsi; P
0x1400441ca  call    cs:__imp_ExFreePoolWithTag
0x1400441d1  nop     dword ptr [rax+rax+00h]
0x1400441d6  lea     rdx, [rbp+57h+var_98]; Context
0x1400441da  mov     rcx, r14; HashTable
0x1400441dd  call    cs:__imp_RtlGetNextEntryHashTable
0x1400441e4  nop     dword ptr [rax+rax+00h]
0x1400441e9  mov     rsi, rax
0x1400441ec  test    rax, rax
0x1400441ef  jnz     short loc_140044177
0x1400441f1  mov     sil, [rbp+57h+var_D0]
0x1400441f5  xor     r14d, r14d
0x1400441f8  cmp     [rdi+104h], r14d
0x1400441ff  jnz     loc_140043F40
0x140044205  jmp     short loc_14004426F
0x140044207  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004420e  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140044214  setnz   r8b
0x140044218  and     dl, 8
0x14004421b  jnz     short loc_140044222
0x14004421d  test    r8b, r8b
0x140044220  jz      short loc_14004426F
0x140044222  mov     r9, cs:WPP_GLOBAL_Control
0x140044229  mov     ecx, 213h
0x14004422e  mov     [rsp+130h+var_E0], eax
0x140044232  lea     rax, aOnecoreBaseFsG_6; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140044239  mov     [rsp+130h+var_E8], 7F2h
0x140044241  mov     [rsp+130h+var_F0], rax
0x140044246  lea     rax, WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids
0x14004424d  mov     r9, [r9+40h]
0x140044251  mov     [rsp+130h+var_F8], rax
0x140044256  mov     [rsp+130h+var_100], 25h ; '%'
0x14004425d  mov     dword ptr [rsp+130h+LengthReturned], 13h
0x140044265  mov     byte ptr [rsp+130h+FileInformationClass], 2
0x14004426a  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14004426f  mov     rcx, r12; Resource
0x140044272  call    cs:__imp_FltReleaseResource
0x140044279  nop     dword ptr [rax+rax+00h]
0x14004427e  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140044282  test    rcx, rcx
0x140044285  jz      short loc_140044293
0x140044287  call    cs:__imp_FltReleaseFileNameInformation
0x14004428e  nop     dword ptr [rax+rax+00h]
0x140044293  test    rdi, rdi
0x140044296  jz      short loc_1400442A7
0x140044298  mov     rcx, rdi; Context
0x14004429b  call    cs:__imp_FltReleaseContext
0x1400442a2  nop     dword ptr [rax+rax+00h]
0x1400442a7  mov     rcx, [rbp+57h+var_A8]; Context
0x1400442ab  test    rcx, rcx
0x1400442ae  jz      short loc_1400442BC
0x1400442b0  call    cs:__imp_FltReleaseContext
0x1400442b7  nop     dword ptr [rax+rax+00h]
0x1400442bc  mov     eax, ebx
0x1400442be  mov     rcx, [rbp+57h+var_40]
  ... truncated ...
```
