# CMFSystemThreadRoutine

- ea: `0x1407eea40`
- end: `0x1407ef098`
- name: `CMFSystemThreadRoutine`
- size: `1624`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x1402268e0`
- `0x140258260`
- `0x1403f2d50`
- `0x1404729c0`
- `0x1406d9d70`
- `0x1406da910`
- `0x1406da950`
- `0x1406daa70`
- `0x1406dad90`
- `0x1406dadd0`
- `0x1406daef0`
- `0x1406db190`
- `0x1406db1d0`
- `0x1407edae0`
- `0x1407ee430`
- `0x1407ee4a8`
- `0x1407ee554`
- `0x1407eea40`
- `0x1408a4070`
- `0x140bae410`
- `0x140bae8e0`

## string_xrefs

- `0x1407eeaea`: `%s\rc%04u\rescache.dir`
- `0x1407eeae3`: `\SystemRoot\Rescache`
- `0x1407eeb41`: `\SystemRoot\Rescache`
- `0x1407eeb90`: `\SystemRoot\Rescache`
- `0x1407eeb97`: `%s\rc%04u\rescache.hit`

## pseudocode

```c
void __fastcall CMFSystemThreadRoutine(__int64 a1)
{
  PVOID v2; // rsi
  int v3; // eax
  ULONG *Pool2; // r13
  NTSTATUS v5; // ebx
  const char *v6; // r12
  ULONG Length; // r14d
  ULONG *v8; // r15
  NTSTATUS v9; // eax
  HANDLE v10; // r15
  bool v11; // sf
  int v12; // eax
  ULONG_PTR LowPart; // r14
  LARGE_INTEGER *p_SectionOffset; // r15
  PVOID v15; // r12
  ULONG v16; // eax
  _QWORD *v17; // rax
  struct _KEVENT *v18; // rcx
  ULONG OpenOptions; // [rsp+28h] [rbp-D8h]
  char v20; // [rsp+50h] [rbp-B0h]
  LARGE_INTEGER SectionOffset; // [rsp+58h] [rbp-A8h] BYREF
  PVOID P; // [rsp+60h] [rbp-A0h] BYREF
  void *v23; // [rsp+68h] [rbp-98h]
  PVOID BaseAddress; // [rsp+70h] [rbp-90h] BYREF
  HANDLE FileHandle; // [rsp+78h] [rbp-88h] BYREF
  HANDLE EventHandle; // [rsp+80h] [rbp-80h] BYREF
  HANDLE SectionHandle; // [rsp+88h] [rbp-78h] BYREF
  HANDLE Object; // [rsp+90h] [rbp-70h] BYREF
  ULONG_PTR ViewSize; // [rsp+98h] [rbp-68h] BYREF
  LARGE_INTEGER MaximumSize; // [rsp+A0h] [rbp-60h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D8h] [rbp-28h] BYREF
  UNICODE_STRING DestinationString; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v34; // [rsp+F8h] [rbp-8h] BYREF
  wchar_t pszDest[264]; // [rsp+100h] [rbp+0h] BYREF

  MaximumSize.QuadPart = 0;
  SectionOffset.QuadPart = 0;
  ViewSize = 0;
  v2 = 0;
  v34 = 0;
  EventHandle = 0;
  FileHandle = 0;
  P = 0;
  SectionHandle = 0;
  BaseAddress = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  if ( !a1 )
    return;
  v3 = *(_DWORD *)(a1 + 48);
  Pool2 = 0;
  v23 = 0;
  switch ( v3 )
  {
    case 16:
      v5 = RtlStringCchPrintfW(
             pszDest,
             0x104u,
             L"%s\\rc%04u\\rescache.dir",
             L"\\SystemRoot\\Rescache",
             *(_DWORD *)(a1 + 4));
      if ( (v5 & 0xC0000000) == 0xC0000000 )
        goto LABEL_26;
      v6 = "RESCDIR";
      break;
    case 32:
      Length = 4192;
      Pool2 = (ULONG *)ExAllocatePool2(256, 4192, 1668114000);
      if ( !Pool2 )
      {
        v5 = -1073741801;
LABEL_64:
        v10 = 0;
        goto LABEL_65;
      }
      v5 = RtlStringCchPrintfW(
             pszDest,
             0x104u,
             L"%s\\rc%04u\\segment%u.cmf",
             L"\\SystemRoot\\Rescache",
             *(_DWORD *)(a1 + 4),
             *(_DWORD *)(a1 + 28));
      if ( (v5 & 0xC0000000) == 0xC0000000 )
        goto LABEL_26;
      v6 = "RESCSEG";
      v8 = Pool2;
      goto LABEL_14;
    case 256:
      v5 = RtlStringCchPrintfW(
             pszDest,
             0x104u,
             L"%s\\rc%04u\\rescache.hit",
             L"\\SystemRoot\\Rescache",
             *(_DWORD *)(a1 + 4));
      if ( (v5 & 0xC0000000) == 0xC0000000 )
        goto LABEL_26;
      v6 = "RESCHIT";
      break;
    default:
      v5 = -1073741811;
      goto LABEL_64;
  }
  v8 = (ULONG *)&v34;
  Length = 8;
LABEL_14:
  RtlInitUnicodeString(&DestinationString, pszDest);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwOpenFile(&FileHandle, 0xC0000000, &ObjectAttributes, &IoStatusBlock, 7u, 0);
  if ( (v5 & 0xC0000000) == 0xC0000000 )
  {
    FileHandle = 0;
LABEL_16:
    v2 = P;
    goto LABEL_64;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, SynchronizationEvent, 0);
  if ( (v5 & 0xC0000000) == 0xC0000000 )
    goto LABEL_26;
  SectionOffset.QuadPart = 0;
  v5 = ZwReadFile(FileHandle, EventHandle, 0, 0, &IoStatusBlock, v8, Length, &SectionOffset, 0);
  if ( v5 < 0 )
    goto LABEL_26;
  v9 = ZwWaitForSingleObject(EventHandle, 0, 0);
  v5 = v9;
  if ( v9 )
  {
    v10 = 0;
    v11 = v9 < 0;
    goto LABEL_21;
  }
  if ( *(_QWORD *)v8 == *(_QWORD *)v6 )
  {
    v12 = *(_DWORD *)(a1 + 48);
    v20 = 0;
    if ( v12 == 32 && Pool2[19] )
    {
      *(_DWORD *)(a1 + 24) |= 4u;
      v20 = 1;
      *(_BYTE *)(a1 + 12) = 1;
    }
    if ( *(_BYTE *)(a1 + 12) )
    {
      SectionOffset.QuadPart = 0;
      if ( v12 == 16 || v12 == 256 )
      {
        v5 = CMFGetFileSizeEx(FileHandle, &SectionOffset);
        if ( (v5 & 0xC0000000) == 0xC0000000 )
          goto LABEL_26;
        LowPart = SectionOffset.LowPart;
      }
      else
      {
        LowPart = Pool2[8];
        SectionOffset.LowPart = Pool2[8];
      }
      Object = 0;
      if ( (int)CMFGetLargePageSectionSize(&SectionOffset, &MaximumSize) < 0 || *(int *)a1 >= 0 )
      {
        *(_DWORD *)a1 &= ~0x80000000;
        p_SectionOffset = &SectionOffset;
        ViewSize = LowPart;
      }
      else
      {
        p_SectionOffset = &MaximumSize;
        ViewSize = MaximumSize.LowPart;
      }
    }
    else
    {
      LowPart = 0;
      Object = FileHandle;
      p_SectionOffset = 0;
    }
    if ( *(_DWORD *)(a1 + 48) != 256 )
    {
      v5 = CMFCreateSecurityDescriptor(&P, 0);
      if ( (v5 & 0xC0000000) == 0xC0000000 )
        goto LABEL_16;
    }
    v15 = P;
    while ( 1 )
    {
      OpenOptions = *(_DWORD *)a1;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = 0;
      ObjectAttributes.SecurityDescriptor = v15;
      ObjectAttributes.SecurityQualityOfService = 0;
      v5 = ZwCreateSection(&SectionHandle, 6u, &ObjectAttributes, p_SectionOffset, 4u, OpenOptions, Object);
      if ( v5 >= 0 )
        break;
      if ( !*(_BYTE *)(a1 + 12) || (v16 = *(_DWORD *)a1, *(int *)a1 >= 0) )
      {
        SectionHandle = 0;
        goto LABEL_16;
      }
      ViewSize = LowPart;
      *(_DWORD *)a1 = v16 & 0x7FFFFFFF;
      p_SectionOffset = &SectionOffset;
    }
    Object = 0;
    v5 = ObReferenceObjectByHandle(SectionHandle, 0xF001Fu, MmSectionObjectType, 0, &Object, 0);
    if ( (v5 & 0xC0000000) == 0xC0000000 )
      goto LABEL_16;
    v10 = Object;
    if ( *(_BYTE *)(a1 + 12) )
    {
      BaseAddress = 0;
      SectionOffset.QuadPart = 0;
      v5 = ZwMapViewOfSection(
             SectionHandle,
             (HANDLE)0xFFFFFFFFFFFFFFFFLL,
             &BaseAddress,
             0,
             0,
             &SectionOffset,
             &ViewSize,
             ViewUnmap,
             0x400000u,
             4u);
      if ( (v5 & 0xC0000000) == 0xC0000000 )
      {
        BaseAddress = 0;
        goto LABEL_23;
      }
      if ( v20 )
      {
        Pool2[19] = 0;
        v5 = CMFReadCompressedSegment(FileHandle, BaseAddress);
        if ( v5 < 0 )
          goto LABEL_23;
      }
      else
      {
        SectionOffset.QuadPart = 0;
        v5 = ZwReadFile(FileHandle, EventHandle, 0, 0, &IoStatusBlock, BaseAddress, LowPart, &SectionOffset, 0);
        if ( v5 < 0 )
          goto LABEL_23;
        v5 = ZwWaitForSingleObject(EventHandle, 0, 0);
        v11 = v5 < 0;
        if ( v5 )
        {
LABEL_21:
          if ( !v11 )
            v5 = -1073741823;
          goto LABEL_23;
        }
      }
      ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, BaseAddress);
      BaseAddress = 0;
    }
    v17 = *(_QWORD **)(a1 + 40);
    if ( v17 )
    {
      *v17 = v10;
      v10 = 0;
      if ( *(_DWORD *)(a1 + 48) == 16 && CMFCacheIndex == 10000 )
      {
        CMFFlagsCache |= *(_DWORD *)(a1 + 24) & 0xF;
        CMFCacheIndex = *(_DWORD *)(a1 + 4);
      }
    }
    goto LABEL_23;
  }
  v5 = -1073700864;
LABEL_26:
  v10 = v23;
LABEL_23:
  v2 = P;
LABEL_65:
  if ( EventHandle )
    ZwClose(EventHandle);
  if ( BaseAddress )
    ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, BaseAddress);
  if ( SectionHandle )
    ZwClose(SectionHandle);
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  if ( v10 )
    ObfDereferenceObject(v10);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0);
  v18 = *(struct _KEVENT **)(a1 + 16);
  *(_DWORD *)(a1 + 36) = v5;
  if ( v18 )
    KeSetEvent(v18, 1, 0);
}

```

## disassembly

```asm
0x1407eea40  push    rbp
0x1407eea42  push    rbx
0x1407eea43  push    rsi
0x1407eea44  push    rdi
0x1407eea45  push    r12
0x1407eea47  push    r13
0x1407eea49  push    r14
0x1407eea4b  push    r15
0x1407eea4d  lea     rbp, [rsp-228h]
0x1407eea55  sub     rsp, 328h
0x1407eea5c  mov     rax, cs:__security_cookie
0x1407eea63  xor     rax, rsp
0x1407eea66  mov     [rbp+260h+var_50], rax
0x1407eea6d  xor     r12d, r12d
0x1407eea70  xorps   xmm0, xmm0
0x1407eea73  xor     eax, eax
0x1407eea75  mov     qword ptr [rbp+260h+MaximumSize], r12
0x1407eea79  mov     qword ptr [rsp+360h+SectionOffset], r12
0x1407eea7e  mov     rdi, rcx
0x1407eea81  mov     [rbp+260h+ViewSize], r12
0x1407eea85  mov     esi, r12d
0x1407eea88  mov     [rbp+260h+var_268], r12
0x1407eea8c  mov     [rbp+260h+EventHandle], r12
0x1407eea90  mov     [rsp+360h+FileHandle], r12
0x1407eea95  mov     [rsp+360h+P], r12
0x1407eea9a  mov     [rbp+260h+SectionHandle], r12
0x1407eea9e  mov     [rsp+360h+BaseAddress], r12
0x1407eeaa3  movups  xmmword ptr [rbp+260h+ObjectAttributes.ObjectName], xmm0
0x1407eeaa7  movups  xmmword ptr [rbp+260h+ObjectAttributes+1Ch], xmm0
0x1407eeaab  movups  xmmword ptr [rbp+260h+IoStatusBlock], xmm0
0x1407eeaaf  movups  xmmword ptr [rbp+260h+ObjectAttributes.Length], xmm0
0x1407eeab3  movups  xmmword ptr [rbp+260h+DestinationString.Length], xmm0
0x1407eeab7  test    rcx, rcx
0x1407eeaba  jz      loc_1407EF074
0x1407eeac0  mov     eax, [rcx+30h]
0x1407eeac3  mov     r13d, r12d
0x1407eeac6  mov     [rsp+360h+var_2F8], r12
0x1407eeacb  mov     ecx, 100h
0x1407eead0  cmp     eax, 10h
0x1407eead3  jnz     short loc_1407EEB13
0x1407eead5  mov     eax, [rdi+4]
0x1407eead8  lea     edx, [rcx+4]; cchDest
0x1407eeadb  lea     rcx, [rbp+260h+pszDest]; pszDest
0x1407eeadf  mov     [rsp+360h+ShareAccess], eax
0x1407eeae3  lea     r9, aSystemrootResc; "\\SystemRoot\\Rescache"
0x1407eeaea  lea     r8, aSRc04uRescache_0; "%s\\rc%04u\\rescache.dir"
0x1407eeaf1  call    RtlStringCchPrintfW
0x1407eeaf6  mov     esi, 0C0000000h
0x1407eeafb  mov     ebx, eax
0x1407eeafd  and     eax, esi
0x1407eeaff  cmp     eax, esi
0x1407eeb01  jz      loc_1407EED03
0x1407eeb07  lea     r12, aRescdir; "RESCDIR"
0x1407eeb0e  jmp     loc_1407EEBC8
0x1407eeb13  cmp     eax, 20h ; ' '
0x1407eeb16  jnz     short loc_1407EEB85
0x1407eeb18  mov     r14d, 1060h
0x1407eeb1e  mov     r8d, 636D6650h
0x1407eeb24  mov     edx, r14d
0x1407eeb27  call    ExAllocatePool2
0x1407eeb2c  mov     r13, rax
0x1407eeb2f  test    rax, rax
0x1407eeb32  jnz     short loc_1407EEB3E
0x1407eeb34  mov     ebx, 0C0000017h
0x1407eeb39  jmp     loc_1407EEFF0
0x1407eeb3e  mov     eax, [rdi+1Ch]
0x1407eeb41  lea     r9, aSystemrootResc; "\\SystemRoot\\Rescache"
0x1407eeb48  mov     [rsp+360h+OpenOptions], eax
0x1407eeb4c  lea     r8, aSRc04uSegmentU; "%s\\rc%04u\\segment%u.cmf"
0x1407eeb53  mov     eax, [rdi+4]
0x1407eeb56  lea     rcx, [rbp+260h+pszDest]; pszDest
0x1407eeb5a  mov     edx, 104h; cchDest
0x1407eeb5f  mov     [rsp+360h+ShareAccess], eax
0x1407eeb63  call    RtlStringCchPrintfW
0x1407eeb68  mov     esi, 0C0000000h
0x1407eeb6d  mov     ebx, eax
0x1407eeb6f  and     eax, esi
0x1407eeb71  cmp     eax, esi
0x1407eeb73  jz      loc_1407EED03
0x1407eeb79  lea     r12, aRescseg; "RESCSEG"
0x1407eeb80  mov     r15, r13
0x1407eeb83  jmp     short loc_1407EEBD2
0x1407eeb85  cmp     eax, ecx
0x1407eeb87  jnz     loc_1407EEFEB
0x1407eeb8d  mov     eax, [rdi+4]
0x1407eeb90  lea     r9, aSystemrootResc; "\\SystemRoot\\Rescache"
0x1407eeb97  lea     r8, aSRc04uRescache; "%s\\rc%04u\\rescache.hit"
0x1407eeb9e  mov     [rsp+360h+ShareAccess], eax
0x1407eeba2  mov     edx, 104h; cchDest
0x1407eeba7  lea     rcx, [rbp+260h+pszDest]; pszDest
0x1407eebab  call    RtlStringCchPrintfW
0x1407eebb0  mov     esi, 0C0000000h
0x1407eebb5  mov     ebx, eax
0x1407eebb7  and     eax, esi
0x1407eebb9  cmp     eax, esi
0x1407eebbb  jz      loc_1407EED03
0x1407eebc1  lea     r12, aReschit; "RESCHIT"
0x1407eebc8  lea     r15, [rbp+260h+var_268]
0x1407eebcc  mov     r14d, 8
0x1407eebd2  lea     rdx, [rbp+260h+pszDest]; SourceString
0x1407eebd6  lea     rcx, [rbp+260h+DestinationString]; DestinationString
0x1407eebda  call    RtlInitUnicodeString
0x1407eebdf  lea     rax, [rbp+260h+DestinationString]
0x1407eebe3  mov     [rsp+360h+OpenOptions], 0; OpenOptions
0x1407eebeb  xorps   xmm0, xmm0
0x1407eebee  mov     [rbp+260h+ObjectAttributes.ObjectName], rax
0x1407eebf2  lea     r9, [rbp+260h+IoStatusBlock]; IoStatusBlock
0x1407eebf6  mov     [rbp+260h+ObjectAttributes.Length], 30h ; '0'
0x1407eebfd  lea     r8, [rbp+260h+ObjectAttributes]; ObjectAttributes
0x1407eec01  mov     [rbp+260h+ObjectAttributes.RootDirectory], 0
0x1407eec09  mov     edx, esi; DesiredAccess
0x1407eec0b  mov     [rbp+260h+ObjectAttributes.Attributes], 240h
0x1407eec12  lea     rcx, [rsp+360h+FileHandle]; FileHandle
0x1407eec17  mov     [rsp+360h+ShareAccess], 7; ShareAccess
0x1407eec1f  movdqu  xmmword ptr [rbp+260h+ObjectAttributes.SecurityDescriptor], xmm0
0x1407eec24  call    ZwOpenFile
0x1407eec29  mov     ebx, eax
0x1407eec2b  and     eax, esi
0x1407eec2d  cmp     eax, esi
0x1407eec2f  jnz     short loc_1407EEC43
0x1407eec31  xor     r12d, r12d
0x1407eec34  mov     [rsp+360h+FileHandle], r12
0x1407eec39  mov     rsi, [rsp+360h+P]
0x1407eec3e  jmp     loc_1407EEFF0
0x1407eec43  xor     eax, eax
0x1407eec45  mov     [rbp+260h+ObjectAttributes.Length], 30h ; '0'
0x1407eec4c  xorps   xmm0, xmm0
0x1407eec4f  mov     [rbp+260h+ObjectAttributes.RootDirectory], rax
0x1407eec53  lea     r8, [rbp+260h+ObjectAttributes]; ObjectAttributes
0x1407eec57  mov     [rbp+260h+ObjectAttributes.Attributes], 200h
0x1407eec5e  mov     edx, 1F0003h; DesiredAccess
0x1407eec63  mov     [rbp+260h+ObjectAttributes.ObjectName], rax
0x1407eec67  lea     r9d, [rax+1]; EventType
0x1407eec6b  mov     byte ptr [rsp+360h+ShareAccess], al; InitialState
0x1407eec6f  lea     rcx, [rbp+260h+EventHandle]; EventHandle
0x1407eec73  movdqu  xmmword ptr [rbp+260h+ObjectAttributes.SecurityDescriptor], xmm0
0x1407eec78  call    ZwCreateEvent
0x1407eec7d  mov     ebx, eax
0x1407eec7f  and     eax, esi
0x1407eec81  cmp     eax, esi
0x1407eec83  jz      short loc_1407EED03
0x1407eec85  mov     rdx, [rbp+260h+EventHandle]; Event
0x1407eec89  xor     eax, eax
0x1407eec8b  mov     rcx, [rsp+360h+FileHandle]; FileHandle
0x1407eec90  xor     r9d, r9d; ApcContext
0x1407eec93  mov     [rsp+360h+Key], rax; Key
0x1407eec98  xor     r8d, r8d; ApcRoutine
0x1407eec9b  mov     qword ptr [rsp+360h+SectionOffset], rax
0x1407eeca0  lea     rax, [rsp+360h+SectionOffset]
0x1407eeca5  mov     [rsp+360h+ByteOffset], rax; ByteOffset
0x1407eecaa  lea     rax, [rbp+260h+IoStatusBlock]
0x1407eecae  mov     [rsp+360h+Length], r14d; Length
0x1407eecb3  mov     qword ptr [rsp+360h+OpenOptions], r15; Buffer
0x1407eecb8  mov     qword ptr [rsp+360h+ShareAccess], rax; IoStatusBlock
0x1407eecbd  call    ZwReadFile
0x1407eecc2  mov     ebx, eax
0x1407eecc4  test    eax, eax
0x1407eecc6  js      short loc_1407EED03
0x1407eecc8  mov     rcx, [rbp+260h+EventHandle]; Handle
0x1407eeccc  xor     r8d, r8d; Timeout
0x1407eeccf  xor     edx, edx; Alertable
0x1407eecd1  call    ZwWaitForSingleObject
0x1407eecd6  mov     ebx, eax
0x1407eecd8  test    eax, eax
0x1407eecda  jz      short loc_1407EECF5
0x1407eecdc  xor     r12d, r12d
0x1407eecdf  mov     r15d, r12d
0x1407eece2  test    eax, eax
0x1407eece4  js      short loc_1407EECEB
0x1407eece6  mov     ebx, 0C0000001h
0x1407eeceb  mov     rsi, [rsp+360h+P]
0x1407eecf0  jmp     loc_1407EEFF3
0x1407eecf5  mov     rax, [r12]
0x1407eecf9  cmp     [r15], rax
0x1407eecfc  jz      short loc_1407EED0A
0x1407eecfe  mov     ebx, 0C000A000h
0x1407eed03  mov     r15, [rsp+360h+var_2F8]
0x1407eed08  jmp     short loc_1407EECEB
0x1407eed0a  mov     eax, [rdi+30h]
0x1407eed0d  xor     r12d, r12d
0x1407eed10  mov     [rsp+360h+var_310], r12b
0x1407eed15  cmp     eax, 20h ; ' '
0x1407eed18  jnz     short loc_1407EED2D
0x1407eed1a  cmp     [r13+4Ch], r12d
0x1407eed1e  jz      short loc_1407EED2D
0x1407eed20  or      dword ptr [rdi+18h], 4
0x1407eed24  mov     [rsp+360h+var_310], 1
0x1407eed29  mov     byte ptr [rdi+0Ch], 1
0x1407eed2d  cmp     [rdi+0Ch], r12b
0x1407eed31  jz      short loc_1407EEDA2
0x1407eed33  mov     qword ptr [rsp+360h+SectionOffset], r12
0x1407eed38  cmp     eax, 10h
0x1407eed3b  jz      short loc_1407EED4F
0x1407eed3d  cmp     eax, 100h
0x1407eed42  jz      short loc_1407EED4F
0x1407eed44  mov     r14d, [r13+20h]
0x1407eed48  mov     dword ptr [rsp+360h+SectionOffset], r14d
0x1407eed4d  jmp     short loc_1407EED6B
0x1407eed4f  mov     rcx, [rsp+360h+FileHandle]
0x1407eed54  lea     rdx, [rsp+360h+SectionOffset]
0x1407eed59  call    CMFGetFileSizeEx
0x1407eed5e  mov     ebx, eax
0x1407eed60  and     eax, esi
0x1407eed62  cmp     eax, esi
0x1407eed64  jz      short loc_1407EED03
0x1407eed66  mov     r14d, dword ptr [rsp+360h+SectionOffset]
0x1407eed6b  lea     rdx, [rbp+260h+MaximumSize]
0x1407eed6f  mov     [rbp+260h+Object], r12
0x1407eed73  lea     rcx, [rsp+360h+SectionOffset]
0x1407eed78  call    CMFGetLargePageSectionSize
0x1407eed7d  test    eax, eax
0x1407eed7f  js      short loc_1407EED93
0x1407eed81  cmp     [rdi], r12d
0x1407eed84  jge     short loc_1407EED93
0x1407eed86  mov     eax, dword ptr [rbp+260h+MaximumSize]
0x1407eed89  lea     r15, [rbp+260h+MaximumSize]
0x1407eed8d  mov     [rbp+260h+ViewSize], rax
0x1407eed91  jmp     short loc_1407EEDB1
0x1407eed93  btr     dword ptr [rdi], 1Fh
0x1407eed97  lea     r15, [rsp+360h+SectionOffset]
0x1407eed9c  mov     [rbp+260h+ViewSize], r14
0x1407eeda0  jmp     short loc_1407EEDB1
0x1407eeda2  mov     rax, [rsp+360h+FileHandle]
0x1407eeda7  mov     r14, r12
0x1407eedaa  mov     [rbp+260h+Object], rax
0x1407eedae  mov     r15, r12
0x1407eedb1  cmp     dword ptr [rdi+30h], 100h
0x1407eedb8  jz      short loc_1407EEDD2
0x1407eedba  xor     edx, edx
0x1407eedbc  lea     rcx, [rsp+360h+P]
0x1407eedc1  call    CMFCreateSecurityDescriptor
0x1407eedc6  mov     ebx, eax
0x1407eedc8  and     eax, esi
0x1407eedca  cmp     eax, esi
0x1407eedcc  jz      loc_1407EEC39
0x1407eedd2  mov     r12, [rsp+360h+P]
0x1407eedd7  mov     rax, [rbp+260h+Object]
0x1407eeddb  lea     r8, [rbp+260h+ObjectAttributes]; ObjectAttributes
0x1407eeddf  mov     qword ptr [rsp+360h+Length], rax; FileHandle
0x1407eede4  lea     rcx, [rbp+260h+SectionHandle]; SectionHandle
0x1407eede8  mov     eax, [rdi]
0x1407eedea  mov     r9, r15; MaximumSize
0x1407eeded  mov     [rsp+360h+OpenOptions], eax; AllocationAttributes
0x1407eedf1  mov     edx, 6; DesiredAccess
0x1407eedf6  mov     [rsp+360h+ShareAccess], 4; SectionPageProtection
0x1407eedfe  mov     [rbp+260h+ObjectAttributes.Length], 30h ; '0'
0x1407eee05  mov     [rbp+260h+ObjectAttributes.RootDirectory], 0
0x1407eee0d  mov     [rbp+260h+ObjectAttributes.Attributes], 240h
0x1407eee14  mov     [rbp+260h+ObjectAttributes.ObjectName], 0
0x1407eee1c  mov     [rbp+260h+ObjectAttributes.SecurityDescriptor], r12
0x1407eee20  mov     [rbp+260h+ObjectAttributes.SecurityQualityOfService], 0
0x1407eee28  call    ZwCreateSection
0x1407eee2d  mov     ebx, eax
0x1407eee2f  test    eax, eax
0x1407eee31  jns     short loc_1407EEE5C
0x1407eee33  cmp     byte ptr [rdi+0Ch], 0
0x1407eee37  jz      short loc_1407EEE50
0x1407eee39  mov     eax, [rdi]
0x1407eee3b  test    eax, eax
0x1407eee3d  jns     short loc_1407EEE50
0x1407eee3f  btr     eax, 1Fh
0x1407eee43  mov     [rbp+260h+ViewSize], r14
0x1407eee47  mov     [rdi], eax
0x1407eee49  lea     r15, [rsp+360h+SectionOffset]
0x1407eee4e  jmp     short loc_1407EEDD7
0x1407eee50  xor     r12d, r12d
0x1407eee53  mov     [rbp+260h+SectionHandle], r12
0x1407eee57  jmp     loc_1407EEC39
0x1407eee5c  mov     r8, cs:MmSectionObjectType; ObjectType
0x1407eee63  lea     rax, [rbp+260h+Object]
0x1407eee67  mov     rcx, [rbp+260h+SectionHandle]; Handle
0x1407eee6b  xor     r12d, r12d
0x1407eee6e  mov     qword ptr [rsp+360h+OpenOptions], r12; HandleInformation
0x1407eee73  xor     r9d, r9d; AccessMode
0x1407eee76  mov     edx, 0F001Fh; DesiredAccess
0x1407eee7b  mov     qword ptr [rsp+360h+ShareAccess], rax; Object
0x1407eee80  mov     [rbp+260h+Object], r12
0x1407eee84  call    ObReferenceObjectByHandle
0x1407eee89  mov     ebx, eax
0x1407eee8b  and     eax, esi
0x1407eee8d  cmp     eax, esi
0x1407eee8f  jz      loc_1407EEC39
0x1407eee95  mov     r15, [rbp+260h+Object]
0x1407eee99  cmp     [rdi+0Ch], r12b
0x1407eee9d  jz      loc_1407EEFA4
0x1407eeea3  mov     rcx, [rbp+260h+SectionHandle]; SectionHandle
0x1407eeea7  lea     rax, [rbp+260h+ViewSize]
0x1407eeeab  mov     [rsp+360h+Win32Protect], 4; Win32Protect
0x1407eeeb3  lea     r8, [rsp+360h+BaseAddress]; BaseAddress
0x1407eeeb8  mov     dword ptr [rsp+360h+Key], 400000h; AllocationType
0x1407eeec0  xor     r9d, r9d; ZeroBits
0x1407eeec3  mov     dword ptr [rsp+360h+ByteOffset], 2; InheritDisposition
0x1407eeecb  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1407eeecf  mov     qword ptr [rsp+360h+Length], rax; ViewSize
0x1407eeed4  lea     rax, [rsp+360h+SectionOffset]
0x1407eeed9  mov     qword ptr [rsp+360h+OpenOptions], rax; SectionOffset
0x1407eeede  mov     qword ptr [rsp+360h+ShareAccess], r12; CommitSize
0x1407eeee3  mov     [rsp+360h+BaseAddress], r12
0x1407eeee8  mov     qword ptr [rsp+360h+SectionOffset], r12
0x1407eeeed  call    ZwMapViewOfSection
  ... truncated ...
```
