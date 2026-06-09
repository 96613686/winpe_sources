# CMFSystemThreadRoutine

- ea: `0x1407f18a0`
- end: `0x1407f1ef8`
- name: `CMFSystemThreadRoutine`
- size: `1624`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x140216480`
- `0x14033a550`
- `0x140403380`
- `0x140481fa0`
- `0x1406dc8c0`
- `0x1406dd460`
- `0x1406dd4a0`
- `0x1406dd5c0`
- `0x1406dd8e0`
- `0x1406dd920`
- `0x1406dda40`
- `0x1406ddce0`
- `0x1406ddd20`
- `0x1407f0940`
- `0x1407f1290`
- `0x1407f1308`
- `0x1407f13b4`
- `0x1407f18a0`
- `0x1408d9170`
- `0x140bb1410`
- `0x140bb19f0`

## string_xrefs

- `0x1407f194a`: `%s\rc%04u\rescache.dir`
- `0x1407f19f7`: `%s\rc%04u\rescache.hit`
- `0x1407f1943`: `\SystemRoot\Rescache`
- `0x1407f19a1`: `\SystemRoot\Rescache`
- `0x1407f19f0`: `\SystemRoot\Rescache`

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
      Pool2 = (ULONG *)ExAllocatePool2(256, 4192, 0x636D6650u);
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
0x1407f18a0  push    rbp
0x1407f18a2  push    rbx
0x1407f18a3  push    rsi
0x1407f18a4  push    rdi
0x1407f18a5  push    r12
0x1407f18a7  push    r13
0x1407f18a9  push    r14
0x1407f18ab  push    r15
0x1407f18ad  lea     rbp, [rsp-228h]
0x1407f18b5  sub     rsp, 328h
0x1407f18bc  mov     rax, cs:__security_cookie
0x1407f18c3  xor     rax, rsp
0x1407f18c6  mov     [rbp+260h+var_50], rax
0x1407f18cd  xor     r12d, r12d
0x1407f18d0  xorps   xmm0, xmm0
0x1407f18d3  xor     eax, eax
0x1407f18d5  mov     qword ptr [rbp+260h+MaximumSize], r12
0x1407f18d9  mov     qword ptr [rsp+360h+SectionOffset], r12
0x1407f18de  mov     rdi, rcx
0x1407f18e1  mov     [rbp+260h+ViewSize], r12
0x1407f18e5  mov     esi, r12d
0x1407f18e8  mov     [rbp+260h+var_268], r12
0x1407f18ec  mov     [rbp+260h+EventHandle], r12
0x1407f18f0  mov     [rsp+360h+FileHandle], r12
0x1407f18f5  mov     [rsp+360h+P], r12
0x1407f18fa  mov     [rbp+260h+SectionHandle], r12
0x1407f18fe  mov     [rsp+360h+BaseAddress], r12
0x1407f1903  movups  xmmword ptr [rbp+260h+ObjectAttributes.ObjectName], xmm0
0x1407f1907  movups  xmmword ptr [rbp+260h+ObjectAttributes+1Ch], xmm0
0x1407f190b  movups  xmmword ptr [rbp+260h+IoStatusBlock], xmm0
0x1407f190f  movups  xmmword ptr [rbp+260h+ObjectAttributes.Length], xmm0
0x1407f1913  movups  xmmword ptr [rbp+260h+DestinationString.Length], xmm0
0x1407f1917  test    rcx, rcx
0x1407f191a  jz      loc_1407F1ED4
0x1407f1920  mov     eax, [rcx+30h]
0x1407f1923  mov     r13d, r12d
0x1407f1926  mov     [rsp+360h+var_2F8], r12
0x1407f192b  mov     ecx, 100h
0x1407f1930  cmp     eax, 10h
0x1407f1933  jnz     short loc_1407F1973
0x1407f1935  mov     eax, [rdi+4]
0x1407f1938  lea     edx, [rcx+4]; cchDest
0x1407f193b  lea     rcx, [rbp+260h+pszDest]; pszDest
0x1407f193f  mov     [rsp+360h+ShareAccess], eax
0x1407f1943  lea     r9, aSystemrootResc; "\\SystemRoot\\Rescache"
0x1407f194a  lea     r8, aSRc04uRescache_0; "%s\\rc%04u\\rescache.dir"
0x1407f1951  call    RtlStringCchPrintfW
0x1407f1956  mov     esi, 0C0000000h
0x1407f195b  mov     ebx, eax
0x1407f195d  and     eax, esi
0x1407f195f  cmp     eax, esi
0x1407f1961  jz      loc_1407F1B63
0x1407f1967  lea     r12, aRescdir; "RESCDIR"
0x1407f196e  jmp     loc_1407F1A28
0x1407f1973  cmp     eax, 20h ; ' '
0x1407f1976  jnz     short loc_1407F19E5
0x1407f1978  mov     r14d, 1060h
0x1407f197e  mov     r8d, 636D6650h
0x1407f1984  mov     edx, r14d
0x1407f1987  call    ExAllocatePool2
0x1407f198c  mov     r13, rax
0x1407f198f  test    rax, rax
0x1407f1992  jnz     short loc_1407F199E
0x1407f1994  mov     ebx, 0C0000017h
0x1407f1999  jmp     loc_1407F1E50
0x1407f199e  mov     eax, [rdi+1Ch]
0x1407f19a1  lea     r9, aSystemrootResc; "\\SystemRoot\\Rescache"
0x1407f19a8  mov     [rsp+360h+OpenOptions], eax
0x1407f19ac  lea     r8, aSRc04uSegmentU; "%s\\rc%04u\\segment%u.cmf"
0x1407f19b3  mov     eax, [rdi+4]
0x1407f19b6  lea     rcx, [rbp+260h+pszDest]; pszDest
0x1407f19ba  mov     edx, 104h; cchDest
0x1407f19bf  mov     [rsp+360h+ShareAccess], eax
0x1407f19c3  call    RtlStringCchPrintfW
0x1407f19c8  mov     esi, 0C0000000h
0x1407f19cd  mov     ebx, eax
0x1407f19cf  and     eax, esi
0x1407f19d1  cmp     eax, esi
0x1407f19d3  jz      loc_1407F1B63
0x1407f19d9  lea     r12, aRescseg; "RESCSEG"
0x1407f19e0  mov     r15, r13
0x1407f19e3  jmp     short loc_1407F1A32
0x1407f19e5  cmp     eax, ecx
0x1407f19e7  jnz     loc_1407F1E4B
0x1407f19ed  mov     eax, [rdi+4]
0x1407f19f0  lea     r9, aSystemrootResc; "\\SystemRoot\\Rescache"
0x1407f19f7  lea     r8, aSRc04uRescache; "%s\\rc%04u\\rescache.hit"
0x1407f19fe  mov     [rsp+360h+ShareAccess], eax
0x1407f1a02  mov     edx, 104h; cchDest
0x1407f1a07  lea     rcx, [rbp+260h+pszDest]; pszDest
0x1407f1a0b  call    RtlStringCchPrintfW
0x1407f1a10  mov     esi, 0C0000000h
0x1407f1a15  mov     ebx, eax
0x1407f1a17  and     eax, esi
0x1407f1a19  cmp     eax, esi
0x1407f1a1b  jz      loc_1407F1B63
0x1407f1a21  lea     r12, aReschit; "RESCHIT"
0x1407f1a28  lea     r15, [rbp+260h+var_268]
0x1407f1a2c  mov     r14d, 8
0x1407f1a32  lea     rdx, [rbp+260h+pszDest]; SourceString
0x1407f1a36  lea     rcx, [rbp+260h+DestinationString]; DestinationString
0x1407f1a3a  call    RtlInitUnicodeString
0x1407f1a3f  lea     rax, [rbp+260h+DestinationString]
0x1407f1a43  mov     [rsp+360h+OpenOptions], 0; OpenOptions
0x1407f1a4b  xorps   xmm0, xmm0
0x1407f1a4e  mov     [rbp+260h+ObjectAttributes.ObjectName], rax
0x1407f1a52  lea     r9, [rbp+260h+IoStatusBlock]; IoStatusBlock
0x1407f1a56  mov     [rbp+260h+ObjectAttributes.Length], 30h ; '0'
0x1407f1a5d  lea     r8, [rbp+260h+ObjectAttributes]; ObjectAttributes
0x1407f1a61  mov     [rbp+260h+ObjectAttributes.RootDirectory], 0
0x1407f1a69  mov     edx, esi; DesiredAccess
0x1407f1a6b  mov     [rbp+260h+ObjectAttributes.Attributes], 240h
0x1407f1a72  lea     rcx, [rsp+360h+FileHandle]; FileHandle
0x1407f1a77  mov     [rsp+360h+ShareAccess], 7; ShareAccess
0x1407f1a7f  movdqu  xmmword ptr [rbp+260h+ObjectAttributes.SecurityDescriptor], xmm0
0x1407f1a84  call    ZwOpenFile
0x1407f1a89  mov     ebx, eax
0x1407f1a8b  and     eax, esi
0x1407f1a8d  cmp     eax, esi
0x1407f1a8f  jnz     short loc_1407F1AA3
0x1407f1a91  xor     r12d, r12d
0x1407f1a94  mov     [rsp+360h+FileHandle], r12
0x1407f1a99  mov     rsi, [rsp+360h+P]
0x1407f1a9e  jmp     loc_1407F1E50
0x1407f1aa3  xor     eax, eax
0x1407f1aa5  mov     [rbp+260h+ObjectAttributes.Length], 30h ; '0'
0x1407f1aac  xorps   xmm0, xmm0
0x1407f1aaf  mov     [rbp+260h+ObjectAttributes.RootDirectory], rax
0x1407f1ab3  lea     r8, [rbp+260h+ObjectAttributes]; ObjectAttributes
0x1407f1ab7  mov     [rbp+260h+ObjectAttributes.Attributes], 200h
0x1407f1abe  mov     edx, 1F0003h; DesiredAccess
0x1407f1ac3  mov     [rbp+260h+ObjectAttributes.ObjectName], rax
0x1407f1ac7  lea     r9d, [rax+1]; EventType
0x1407f1acb  mov     byte ptr [rsp+360h+ShareAccess], al; InitialState
0x1407f1acf  lea     rcx, [rbp+260h+EventHandle]; EventHandle
0x1407f1ad3  movdqu  xmmword ptr [rbp+260h+ObjectAttributes.SecurityDescriptor], xmm0
0x1407f1ad8  call    ZwCreateEvent
0x1407f1add  mov     ebx, eax
0x1407f1adf  and     eax, esi
0x1407f1ae1  cmp     eax, esi
0x1407f1ae3  jz      short loc_1407F1B63
0x1407f1ae5  mov     rdx, [rbp+260h+EventHandle]; Event
0x1407f1ae9  xor     eax, eax
0x1407f1aeb  mov     rcx, [rsp+360h+FileHandle]; FileHandle
0x1407f1af0  xor     r9d, r9d; ApcContext
0x1407f1af3  mov     [rsp+360h+Key], rax; Key
0x1407f1af8  xor     r8d, r8d; ApcRoutine
0x1407f1afb  mov     qword ptr [rsp+360h+SectionOffset], rax
0x1407f1b00  lea     rax, [rsp+360h+SectionOffset]
0x1407f1b05  mov     [rsp+360h+ByteOffset], rax; ByteOffset
0x1407f1b0a  lea     rax, [rbp+260h+IoStatusBlock]
0x1407f1b0e  mov     [rsp+360h+Length], r14d; Length
0x1407f1b13  mov     qword ptr [rsp+360h+OpenOptions], r15; Buffer
0x1407f1b18  mov     qword ptr [rsp+360h+ShareAccess], rax; IoStatusBlock
0x1407f1b1d  call    ZwReadFile
0x1407f1b22  mov     ebx, eax
0x1407f1b24  test    eax, eax
0x1407f1b26  js      short loc_1407F1B63
0x1407f1b28  mov     rcx, [rbp+260h+EventHandle]; Handle
0x1407f1b2c  xor     r8d, r8d; Timeout
0x1407f1b2f  xor     edx, edx; Alertable
0x1407f1b31  call    ZwWaitForSingleObject
0x1407f1b36  mov     ebx, eax
0x1407f1b38  test    eax, eax
0x1407f1b3a  jz      short loc_1407F1B55
0x1407f1b3c  xor     r12d, r12d
0x1407f1b3f  mov     r15d, r12d
0x1407f1b42  test    eax, eax
0x1407f1b44  js      short loc_1407F1B4B
0x1407f1b46  mov     ebx, 0C0000001h
0x1407f1b4b  mov     rsi, [rsp+360h+P]
0x1407f1b50  jmp     loc_1407F1E53
0x1407f1b55  mov     rax, [r12]
0x1407f1b59  cmp     [r15], rax
0x1407f1b5c  jz      short loc_1407F1B6A
0x1407f1b5e  mov     ebx, 0C000A000h
0x1407f1b63  mov     r15, [rsp+360h+var_2F8]
0x1407f1b68  jmp     short loc_1407F1B4B
0x1407f1b6a  mov     eax, [rdi+30h]
0x1407f1b6d  xor     r12d, r12d
0x1407f1b70  mov     [rsp+360h+var_310], r12b
0x1407f1b75  cmp     eax, 20h ; ' '
0x1407f1b78  jnz     short loc_1407F1B8D
0x1407f1b7a  cmp     [r13+4Ch], r12d
0x1407f1b7e  jz      short loc_1407F1B8D
0x1407f1b80  or      dword ptr [rdi+18h], 4
0x1407f1b84  mov     [rsp+360h+var_310], 1
0x1407f1b89  mov     byte ptr [rdi+0Ch], 1
0x1407f1b8d  cmp     [rdi+0Ch], r12b
0x1407f1b91  jz      short loc_1407F1C02
0x1407f1b93  mov     qword ptr [rsp+360h+SectionOffset], r12
0x1407f1b98  cmp     eax, 10h
0x1407f1b9b  jz      short loc_1407F1BAF
0x1407f1b9d  cmp     eax, 100h
0x1407f1ba2  jz      short loc_1407F1BAF
0x1407f1ba4  mov     r14d, [r13+20h]
0x1407f1ba8  mov     dword ptr [rsp+360h+SectionOffset], r14d
0x1407f1bad  jmp     short loc_1407F1BCB
0x1407f1baf  mov     rcx, [rsp+360h+FileHandle]
0x1407f1bb4  lea     rdx, [rsp+360h+SectionOffset]
0x1407f1bb9  call    CMFGetFileSizeEx
0x1407f1bbe  mov     ebx, eax
0x1407f1bc0  and     eax, esi
0x1407f1bc2  cmp     eax, esi
0x1407f1bc4  jz      short loc_1407F1B63
0x1407f1bc6  mov     r14d, dword ptr [rsp+360h+SectionOffset]
0x1407f1bcb  lea     rdx, [rbp+260h+MaximumSize]
0x1407f1bcf  mov     [rbp+260h+Object], r12
0x1407f1bd3  lea     rcx, [rsp+360h+SectionOffset]
0x1407f1bd8  call    CMFGetLargePageSectionSize
0x1407f1bdd  test    eax, eax
0x1407f1bdf  js      short loc_1407F1BF3
0x1407f1be1  cmp     [rdi], r12d
0x1407f1be4  jge     short loc_1407F1BF3
0x1407f1be6  mov     eax, dword ptr [rbp+260h+MaximumSize]
0x1407f1be9  lea     r15, [rbp+260h+MaximumSize]
0x1407f1bed  mov     [rbp+260h+ViewSize], rax
0x1407f1bf1  jmp     short loc_1407F1C11
0x1407f1bf3  btr     dword ptr [rdi], 1Fh
0x1407f1bf7  lea     r15, [rsp+360h+SectionOffset]
0x1407f1bfc  mov     [rbp+260h+ViewSize], r14
0x1407f1c00  jmp     short loc_1407F1C11
0x1407f1c02  mov     rax, [rsp+360h+FileHandle]
0x1407f1c07  mov     r14, r12
0x1407f1c0a  mov     [rbp+260h+Object], rax
0x1407f1c0e  mov     r15, r12
0x1407f1c11  cmp     dword ptr [rdi+30h], 100h
0x1407f1c18  jz      short loc_1407F1C32
0x1407f1c1a  xor     edx, edx
0x1407f1c1c  lea     rcx, [rsp+360h+P]
0x1407f1c21  call    CMFCreateSecurityDescriptor
0x1407f1c26  mov     ebx, eax
0x1407f1c28  and     eax, esi
0x1407f1c2a  cmp     eax, esi
0x1407f1c2c  jz      loc_1407F1A99
0x1407f1c32  mov     r12, [rsp+360h+P]
0x1407f1c37  mov     rax, [rbp+260h+Object]
0x1407f1c3b  lea     r8, [rbp+260h+ObjectAttributes]; ObjectAttributes
0x1407f1c3f  mov     qword ptr [rsp+360h+Length], rax; FileHandle
0x1407f1c44  lea     rcx, [rbp+260h+SectionHandle]; SectionHandle
0x1407f1c48  mov     eax, [rdi]
0x1407f1c4a  mov     r9, r15; MaximumSize
0x1407f1c4d  mov     [rsp+360h+OpenOptions], eax; AllocationAttributes
0x1407f1c51  mov     edx, 6; DesiredAccess
0x1407f1c56  mov     [rsp+360h+ShareAccess], 4; SectionPageProtection
0x1407f1c5e  mov     [rbp+260h+ObjectAttributes.Length], 30h ; '0'
0x1407f1c65  mov     [rbp+260h+ObjectAttributes.RootDirectory], 0
0x1407f1c6d  mov     [rbp+260h+ObjectAttributes.Attributes], 240h
0x1407f1c74  mov     [rbp+260h+ObjectAttributes.ObjectName], 0
0x1407f1c7c  mov     [rbp+260h+ObjectAttributes.SecurityDescriptor], r12
0x1407f1c80  mov     [rbp+260h+ObjectAttributes.SecurityQualityOfService], 0
0x1407f1c88  call    ZwCreateSection
0x1407f1c8d  mov     ebx, eax
0x1407f1c8f  test    eax, eax
0x1407f1c91  jns     short loc_1407F1CBC
0x1407f1c93  cmp     byte ptr [rdi+0Ch], 0
0x1407f1c97  jz      short loc_1407F1CB0
0x1407f1c99  mov     eax, [rdi]
0x1407f1c9b  test    eax, eax
0x1407f1c9d  jns     short loc_1407F1CB0
0x1407f1c9f  btr     eax, 1Fh
0x1407f1ca3  mov     [rbp+260h+ViewSize], r14
0x1407f1ca7  mov     [rdi], eax
0x1407f1ca9  lea     r15, [rsp+360h+SectionOffset]
0x1407f1cae  jmp     short loc_1407F1C37
0x1407f1cb0  xor     r12d, r12d
0x1407f1cb3  mov     [rbp+260h+SectionHandle], r12
0x1407f1cb7  jmp     loc_1407F1A99
0x1407f1cbc  mov     r8, cs:MmSectionObjectType; ObjectType
0x1407f1cc3  lea     rax, [rbp+260h+Object]
0x1407f1cc7  mov     rcx, [rbp+260h+SectionHandle]; Handle
0x1407f1ccb  xor     r12d, r12d
0x1407f1cce  mov     qword ptr [rsp+360h+OpenOptions], r12; HandleInformation
0x1407f1cd3  xor     r9d, r9d; AccessMode
0x1407f1cd6  mov     edx, 0F001Fh; DesiredAccess
0x1407f1cdb  mov     qword ptr [rsp+360h+ShareAccess], rax; Object
0x1407f1ce0  mov     [rbp+260h+Object], r12
0x1407f1ce4  call    ObReferenceObjectByHandle
0x1407f1ce9  mov     ebx, eax
0x1407f1ceb  and     eax, esi
0x1407f1ced  cmp     eax, esi
0x1407f1cef  jz      loc_1407F1A99
0x1407f1cf5  mov     r15, [rbp+260h+Object]
0x1407f1cf9  cmp     [rdi+0Ch], r12b
0x1407f1cfd  jz      loc_1407F1E04
0x1407f1d03  mov     rcx, [rbp+260h+SectionHandle]; SectionHandle
0x1407f1d07  lea     rax, [rbp+260h+ViewSize]
0x1407f1d0b  mov     [rsp+360h+Win32Protect], 4; Win32Protect
0x1407f1d13  lea     r8, [rsp+360h+BaseAddress]; BaseAddress
0x1407f1d18  mov     dword ptr [rsp+360h+Key], 400000h; AllocationType
0x1407f1d20  xor     r9d, r9d; ZeroBits
0x1407f1d23  mov     dword ptr [rsp+360h+ByteOffset], 2; InheritDisposition
0x1407f1d2b  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1407f1d2f  mov     qword ptr [rsp+360h+Length], rax; ViewSize
0x1407f1d34  lea     rax, [rsp+360h+SectionOffset]
0x1407f1d39  mov     qword ptr [rsp+360h+OpenOptions], rax; SectionOffset
0x1407f1d3e  mov     qword ptr [rsp+360h+ShareAccess], r12; CommitSize
0x1407f1d43  mov     [rsp+360h+BaseAddress], r12
0x1407f1d48  mov     qword ptr [rsp+360h+SectionOffset], r12
0x1407f1d4d  call    ZwMapViewOfSection
  ... truncated ...
```
