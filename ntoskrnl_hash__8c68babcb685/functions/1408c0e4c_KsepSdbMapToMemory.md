# KsepSdbMapToMemory

- ea: `0x1408c0e4c`
- end: `0x1408c121c`
- name: `KsepSdbMapToMemory`
- size: `976`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1408c0cc8`

## callees

- `0x140207670`
- `0x140216480`
- `0x140346450`
- `0x140403380`
- `0x1404a4304`
- `0x1404caeb8`
- `0x1404eef34`
- `0x14050edec`
- `0x14050f5e4`
- `0x1406dd5c0`
- `0x1406dda40`
- `0x1406ddd20`
- `0x1408c0be4`
- `0x1408c0e4c`
- `0x1408c14e4`
- `0x1408d9170`

## string_xrefs

- `0x1408c1147`: `KSE: ZwCreateSection Failed!\n`
- `0x1408c1155`: `KSE: ZwCreateSection Failed!\n`
- `0x1408c1066`: `KSE: ZwOpenFile failed opening DB file!\n`
- `0x1408c1074`: `KSE: ZwOpenFile failed opening DB file!\n`

## pseudocode

```c
__int64 __fastcall KsepSdbMapToMemory(PCWSTR SourceString, __int64 a2)
{
  int v3; // ebx
  NTSTATUS v4; // eax
  _QWORD *v5; // rdi
  PVOID v6; // rcx
  __int64 v7; // r15
  __int64 v8; // r14
  unsigned __int64 v9; // r14
  ULONG_PTR v10; // rbx
  __int64 inited; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  HANDLE FileHandle; // [rsp+40h] [rbp-29h] BYREF
  ULONG_PTR BugCheckParameter1; // [rsp+48h] [rbp-21h] BYREF
  UNICODE_STRING DestinationString; // [rsp+50h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-9h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+7h] BYREF
  PVOID Object; // [rsp+E0h] [rbp+77h] BYREF
  HANDLE SectionHandle; // [rsp+E8h] [rbp+7Fh] BYREF

  FileHandle = 0;
  SectionHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = ZwOpenFile(&FileHandle, 0x80000000, &ObjectAttributes, &IoStatusBlock, 5u, 0);
  if ( v3 < 0 )
  {
    v13 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryErrorsIndex, 1u) + 1) & 0x3F;
    KsepHistoryErrors[2 * v13 + 1] = v3;
    KsepHistoryErrors[2 * v13] = 590504;
    if ( (KsepDebugFlag & 2) != 0 )
      KsepDebugPrint(0, "KSE: ZwOpenFile failed opening DB file!\n");
    KsepLogError(0, "KSE: ZwOpenFile failed opening DB file!\n");
  }
  else
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v3 = ZwCreateSection(&SectionHandle, 4u, &ObjectAttributes, 0, 2u, 0x8000000u, FileHandle);
    if ( v3 < 0 )
    {
      v15 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryErrorsIndex, 1u) + 1) & 0x3F;
      KsepHistoryErrors[2 * v15 + 1] = v3;
      KsepHistoryErrors[2 * v15] = 590526;
      if ( (KsepDebugFlag & 2) != 0 )
        KsepDebugPrint(0, "KSE: ZwCreateSection Failed!\n");
      KsepLogError(0, "KSE: ZwCreateSection Failed!\n");
    }
    else
    {
      Object = 0;
      v4 = ObReferenceObjectByHandle(SectionHandle, 0xF001Fu, MmSectionObjectType, 0, &Object, 0);
      v5 = Object;
      v3 = v4;
      if ( v4 < 0 )
      {
        v14 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryErrorsIndex, 1u) + 1) & 0x3F;
        KsepHistoryErrors[2 * v14 + 1] = v4;
        KsepHistoryErrors[2 * v14] = 590540;
        if ( (KsepDebugFlag & 2) != 0 )
          KsepDebugPrint(0, "KSE: ObRefByHandle(section) failed!\n");
        KsepLogError(0, "KSE: ObRefByHandle(section) failed!\n");
      }
      else
      {
        v6 = Object;
        Object = 0;
        BugCheckParameter1 = 0;
        v7 = MiSectionControlArea(v6);
        MiCheckPurgeAndUpMapCount(v7);
        v8 = v5[6];
        LODWORD(Object) = (unsigned int)Object & 0xFFFF0000;
        v9 = v8 - (_QWORD)Object;
        v3 = MiInsertInSystemSpace(v9, (__int64)v5, &Object, 0, &BugCheckParameter1);
        if ( v3 < 0 )
        {
          MiDereferenceControlArea(v7);
          v17 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryErrorsIndex, 1u) + 1) & 0x3F;
          KsepHistoryErrors[2 * v17 + 1] = v3;
          KsepHistoryErrors[2 * v17] = 590553;
          if ( (KsepDebugFlag & 2) != 0 )
            KsepDebugPrint(0, "KSE: Unable to map view of section!\n");
          KsepLogError(0, "KSE: Unable to map view of section!\n");
        }
        else
        {
          v10 = BugCheckParameter1;
          inited = SdbInitDatabaseInMemory(BugCheckParameter1, v9);
          if ( inited )
          {
            *(_QWORD *)(a2 + 16) = FileHandle;
            *(_QWORD *)(a2 + 24) = SectionHandle;
            *(_QWORD *)(a2 + 32) = v5;
            *(_QWORD *)(a2 + 8) = v10;
            *(_QWORD *)a2 = inited;
            *(_DWORD *)(a2 + 48) = SdbGetDatabaseEdition(*(_QWORD *)(inited + 8));
            return 0;
          }
          v16 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryErrorsIndex, 1u) + 1) & 0x3F;
          KsepHistoryErrors[2 * v16 + 1] = -1073741823;
          KsepHistoryErrors[2 * v16] = 590562;
          if ( (KsepDebugFlag & 2) != 0 )
            KsepDebugPrint(0, "KSE: SdbInitDatabaseInMemory Failed!\n");
          KsepLogError(0, "KSE: SdbInitDatabaseInMemory Failed!\n");
          if ( v10 )
            MiRemoveFromSystemSpace(v10);
          v3 = -1073741823;
        }
      }
      if ( v5 )
        ObfDereferenceObject(v5);
    }
  }
  if ( SectionHandle )
    ZwClose(SectionHandle);
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1408c0e4c  mov     [rsp-8+arg_0], rbx
0x1408c0e51  push    rbp
0x1408c0e52  push    rsi
0x1408c0e53  push    rdi
0x1408c0e54  push    r14
0x1408c0e56  push    r15
0x1408c0e58  lea     rbp, [rsp-37h]
0x1408c0e5d  sub     rsp, 0A0h
0x1408c0e64  xorps   xmm0, xmm0
0x1408c0e67  xor     eax, eax
0x1408c0e69  mov     rsi, rdx
0x1408c0e6c  mov     [rbp+57h+FileHandle], rax
0x1408c0e70  mov     rdx, rcx; SourceString
0x1408c0e73  mov     [rbp+57h+SectionHandle], rax
0x1408c0e77  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1408c0e7b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1408c0e7f  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1408c0e83  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1408c0e87  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1408c0e8b  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1408c0e8f  call    RtlInitUnicodeString
0x1408c0e94  lea     rax, [rbp+57h+DestinationString]
0x1408c0e98  mov     [rsp+0C0h+OpenOptions], 0; OpenOptions
0x1408c0ea0  xorps   xmm0, xmm0
0x1408c0ea3  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1408c0ea7  mov     edi, 30h ; '0'
0x1408c0eac  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1408c0eb4  mov     r14d, 240h
0x1408c0eba  mov     [rbp+57h+ObjectAttributes.Length], edi
0x1408c0ebd  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1408c0ec1  mov     [rbp+57h+ObjectAttributes.Attributes], r14d
0x1408c0ec5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1408c0ec9  mov     [rsp+0C0h+ShareAccess], 5; ShareAccess
0x1408c0ed1  mov     edx, 80000000h; DesiredAccess
0x1408c0ed6  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1408c0eda  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1408c0edf  call    ZwOpenFile
0x1408c0ee4  mov     ebx, eax
0x1408c0ee6  test    eax, eax
0x1408c0ee8  js      loc_1408C1038
0x1408c0eee  mov     rax, [rbp+57h+FileHandle]
0x1408c0ef2  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1408c0ef6  mov     [rsp+0C0h+var_90], rax; FileHandle
0x1408c0efb  lea     edx, [rdi-2Ch]; DesiredAccess
0x1408c0efe  xorps   xmm0, xmm0
0x1408c0f01  mov     [rsp+0C0h+OpenOptions], 8000000h; AllocationAttributes
0x1408c0f09  xor     r9d, r9d; MaximumSize
0x1408c0f0c  mov     [rsp+0C0h+ShareAccess], 2; SectionPageProtection
0x1408c0f14  lea     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x1408c0f18  mov     [rbp+57h+ObjectAttributes.Length], edi
0x1408c0f1b  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1408c0f23  mov     [rbp+57h+ObjectAttributes.Attributes], r14d
0x1408c0f27  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x1408c0f2f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1408c0f34  call    ZwCreateSection
0x1408c0f39  mov     ebx, eax
0x1408c0f3b  test    eax, eax
0x1408c0f3d  js      loc_1408C1119
0x1408c0f43  mov     r8, cs:MmSectionObjectType; ObjectType
0x1408c0f4a  lea     rax, [rbp+57h+Object]
0x1408c0f4e  mov     rcx, [rbp+57h+SectionHandle]; Handle
0x1408c0f52  xor     r9d, r9d; AccessMode
0x1408c0f55  mov     qword ptr [rsp+0C0h+OpenOptions], 0; HandleInformation
0x1408c0f5e  mov     edx, 0F001Fh; DesiredAccess
0x1408c0f63  mov     qword ptr [rsp+0C0h+ShareAccess], rax; Object
0x1408c0f68  mov     [rbp+57h+Object], 0
0x1408c0f70  call    ObReferenceObjectByHandle
0x1408c0f75  mov     rdi, [rbp+57h+Object]
0x1408c0f79  mov     ebx, eax
0x1408c0f7b  test    eax, eax
0x1408c0f7d  js      loc_1408C1084
0x1408c0f83  mov     rcx, rdi
0x1408c0f86  mov     [rbp+57h+Object], 0
0x1408c0f8e  mov     [rbp+57h+BugCheckParameter1], 0
0x1408c0f96  call    MiSectionControlArea
0x1408c0f9b  mov     rcx, rax
0x1408c0f9e  mov     r15, rax
0x1408c0fa1  call    MiCheckPurgeAndUpMapCount
0x1408c0fa6  mov     r14, [rdi+30h]
0x1408c0faa  lea     rax, [rbp+57h+BugCheckParameter1]
0x1408c0fae  and     dword ptr [rbp+57h+Object], 0FFFF0000h
0x1408c0fb5  lea     r8, [rbp+57h+Object]
0x1408c0fb9  sub     r14, [rbp+57h+Object]
0x1408c0fbd  xor     r9d, r9d
0x1408c0fc0  mov     rcx, r14
0x1408c0fc3  mov     qword ptr [rsp+0C0h+ShareAccess], rax
0x1408c0fc8  mov     rdx, rdi
0x1408c0fcb  call    MiInsertInSystemSpace
0x1408c0fd0  mov     ebx, eax
0x1408c0fd2  test    eax, eax
0x1408c0fd4  js      loc_1408C11B7
0x1408c0fda  mov     rbx, [rbp+57h+BugCheckParameter1]
0x1408c0fde  mov     edx, r14d
0x1408c0fe1  mov     rcx, rbx
0x1408c0fe4  call    SdbInitDatabaseInMemory
0x1408c0fe9  mov     rcx, rax
0x1408c0fec  test    rax, rax
0x1408c0fef  jz      loc_1408C1161
0x1408c0ff5  mov     rax, [rbp+57h+FileHandle]
0x1408c0ff9  mov     [rsi+10h], rax
0x1408c0ffd  mov     rax, [rbp+57h+SectionHandle]
0x1408c1001  mov     [rsi+18h], rax
0x1408c1005  mov     [rsi+20h], rdi
0x1408c1009  mov     [rsi+8], rbx
0x1408c100d  mov     [rsi], rcx
0x1408c1010  mov     rcx, [rcx+8]
0x1408c1014  call    SdbGetDatabaseEdition
0x1408c1019  mov     [rsi+30h], eax
0x1408c101c  xor     ebx, ebx
0x1408c101e  mov     eax, ebx
0x1408c1020  mov     rbx, [rsp+0C0h+arg_0]
0x1408c1028  add     rsp, 0A0h
0x1408c102f  pop     r15
0x1408c1031  pop     r14
0x1408c1033  pop     rdi
0x1408c1034  pop     rsi
0x1408c1035  pop     rbp
0x1408c1036  retn
0x1408c1038  mov     ecx, 1
0x1408c103d  lock xadd cs:KsepHistoryErrorsIndex, ecx
0x1408c1045  inc     ecx
0x1408c1047  lea     rax, KsepHistoryErrors
0x1408c104e  and     ecx, 3Fh
0x1408c1051  mov     [rax+rcx*8+4], ebx
0x1408c1055  mov     dword ptr [rax+rcx*8], 902A8h
0x1408c105c  mov     eax, cs:KsepDebugFlag
0x1408c1062  test    al, 2
0x1408c1064  jz      short loc_1408C1074
0x1408c1066  lea     rdx, aKseZwopenfileF; "KSE: ZwOpenFile failed opening DB file!"...
0x1408c106d  xor     ecx, ecx
0x1408c106f  call    KsepDebugPrint
0x1408c1074  lea     rdx, aKseZwopenfileF; "KSE: ZwOpenFile failed opening DB file!"...
0x1408c107b  xor     ecx, ecx
0x1408c107d  call    KsepLogError
0x1408c1082  jmp     short loc_1408C10F5
0x1408c1084  mov     ecx, 1
0x1408c1089  lock xadd cs:KsepHistoryErrorsIndex, ecx
0x1408c1091  inc     ecx
0x1408c1093  lea     rax, KsepHistoryErrors
0x1408c109a  and     ecx, 3Fh
0x1408c109d  mov     [rax+rcx*8+4], ebx
0x1408c10a1  mov     dword ptr [rax+rcx*8], 902CCh
0x1408c10a8  mov     eax, cs:KsepDebugFlag
0x1408c10ae  test    al, 2
0x1408c10b0  jz      short loc_1408C10C0
0x1408c10b2  lea     rdx, aKseObrefbyhand; "KSE: ObRefByHandle(section) failed!\n"
0x1408c10b9  xor     ecx, ecx
0x1408c10bb  call    KsepDebugPrint
0x1408c10c0  lea     rdx, aKseObrefbyhand; "KSE: ObRefByHandle(section) failed!\n"
0x1408c10c7  xor     ecx, ecx
0x1408c10c9  call    KsepLogError
0x1408c10ce  jmp     short loc_1408C10EC
0x1408c10d0  lea     rdx, aKseSdbinitdata; "KSE: SdbInitDatabaseInMemory Failed!\n"
0x1408c10d7  xor     ecx, ecx
0x1408c10d9  call    KsepLogError
0x1408c10de  test    rbx, rbx
0x1408c10e1  jnz     loc_1408C11AA
0x1408c10e7  mov     ebx, 0C0000001h
0x1408c10ec  test    rdi, rdi
0x1408c10ef  jnz     loc_1408C1205
0x1408c10f5  mov     rcx, [rbp+57h+SectionHandle]; Handle
0x1408c10f9  test    rcx, rcx
0x1408c10fc  jnz     loc_1408C1212
0x1408c1102  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1408c1106  test    rcx, rcx
0x1408c1109  jz      loc_1408C101E
0x1408c110f  call    ZwClose
0x1408c1114  jmp     loc_1408C101E
0x1408c1119  mov     ecx, 1
0x1408c111e  lock xadd cs:KsepHistoryErrorsIndex, ecx
0x1408c1126  inc     ecx
0x1408c1128  lea     rax, KsepHistoryErrors
0x1408c112f  and     ecx, 3Fh
0x1408c1132  mov     [rax+rcx*8+4], ebx
0x1408c1136  mov     dword ptr [rax+rcx*8], 902BEh
0x1408c113d  mov     eax, cs:KsepDebugFlag
0x1408c1143  test    al, 2
0x1408c1145  jz      short loc_1408C1155
0x1408c1147  lea     rdx, aKseZwcreatesec; "KSE: ZwCreateSection Failed!\n"
0x1408c114e  xor     ecx, ecx
0x1408c1150  call    KsepDebugPrint
0x1408c1155  lea     rdx, aKseZwcreatesec; "KSE: ZwCreateSection Failed!\n"
0x1408c115c  jmp     loc_1408C107B
0x1408c1161  mov     ecx, 1
0x1408c1166  lock xadd cs:KsepHistoryErrorsIndex, ecx
0x1408c116e  inc     ecx
0x1408c1170  lea     rax, KsepHistoryErrors
0x1408c1177  and     ecx, 3Fh
0x1408c117a  mov     dword ptr [rax+rcx*8+4], 0C0000001h
0x1408c1182  mov     dword ptr [rax+rcx*8], 902E2h
0x1408c1189  mov     eax, cs:KsepDebugFlag
0x1408c118f  test    al, 2
0x1408c1191  jz      loc_1408C10D0
0x1408c1197  lea     rdx, aKseSdbinitdata; "KSE: SdbInitDatabaseInMemory Failed!\n"
0x1408c119e  xor     ecx, ecx
0x1408c11a0  call    KsepDebugPrint
0x1408c11a5  jmp     loc_1408C10D0
0x1408c11aa  mov     rcx, rbx; BugCheckParameter1
0x1408c11ad  call    MiRemoveFromSystemSpace
0x1408c11b2  jmp     loc_1408C10E7
0x1408c11b7  mov     rcx, r15
0x1408c11ba  call    MiDereferenceControlArea
0x1408c11bf  mov     ecx, 1
0x1408c11c4  lock xadd cs:KsepHistoryErrorsIndex, ecx
0x1408c11cc  inc     ecx
0x1408c11ce  lea     rax, KsepHistoryErrors
0x1408c11d5  and     ecx, 3Fh
0x1408c11d8  mov     [rax+rcx*8+4], ebx
0x1408c11dc  mov     dword ptr [rax+rcx*8], 902D9h
0x1408c11e3  mov     eax, cs:KsepDebugFlag
0x1408c11e9  test    al, 2
0x1408c11eb  jz      loc_140B548FA
0x1408c11f1  lea     rdx, aKseUnableToMap; "KSE: Unable to map view of section!\n"
0x1408c11f8  xor     ecx, ecx
0x1408c11fa  call    KsepDebugPrint
0x1408c11ff  nop
0x1408c1200  jmp     loc_140B548FA
0x1408c1205  mov     rcx, rdi; Object
0x1408c1208  call    ObfDereferenceObject
0x1408c120d  jmp     loc_1408C10F5
0x1408c1212  call    ZwClose
0x1408c1217  jmp     loc_1408C1102
0x140b548fa  lea     rdx, aKseUnableToMap; "KSE: Unable to map view of section!\n"
0x140b54901  jmp     loc_1408C10C7
```
