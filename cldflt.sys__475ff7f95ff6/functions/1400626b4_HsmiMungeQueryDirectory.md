# HsmiMungeQueryDirectory

- ea: `0x1400626b4`
- end: `0x140062db2`
- name: `HsmiMungeQueryDirectory`
- size: `1790`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140062060`

## callees

- `0x140003c50`
- `0x140009364`
- `0x14000ac28`
- `0x14001d48c`
- `0x14004552c`
- `0x140045780`
- `0x1400459b4`
- `0x140045bfc`
- `0x140045e30`
- `0x140046370`
- `0x14004c6d0`
- `0x1400626b4`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140062aad`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140062aad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062d7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062d7d`
- `ntoskrnl!ExAllocatePool2` at `0x140062801`
- `ntoskrnl!ExAllocatePool2` at `0x140062801`
- `FLTMGR!FltAllocateCallbackDataEx` at `0x14006289d`
- `FLTMGR!FltAllocateCallbackDataEx` at `0x14006289d`
- `FLTMGR!FltPropagateIrpExtension` at `0x1400628f9`
- `FLTMGR!FltPropagateIrpExtension` at `0x1400628f9`
- `FLTMGR!FltLockUserBuffer` at `0x140062a2f`
- `FLTMGR!FltLockUserBuffer` at `0x140062a2f`
- `FLTMGR!FltPerformSynchronousIo` at `0x1400629d3`
- `FLTMGR!FltPerformSynchronousIo` at `0x1400629d3`
- `FLTMGR!FltFreeCallbackData` at `0x1400629f7`
- `FLTMGR!FltFreeCallbackData` at `0x140062d64`
- `FLTMGR!FltFreeCallbackData` at `0x1400629f7`
- `FLTMGR!FltFreeCallbackData` at `0x140062d64`
- `FLTMGR!FltReleaseContext` at `0x140062d92`
- `FLTMGR!FltReleaseContext` at `0x140062d92`

## pseudocode

```c
__int64 __fastcall HsmiMungeQueryDirectory(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  struct _FILE_OBJECT *v2; // rax
  void *Pool2; // r12
  struct _FLT_INSTANCE *v4; // rdx
  int v6; // edi
  int v7; // esi
  DWORD v8; // ebx
  __int64 StreamHandleContext; // rax
  __int64 v10; // rdx
  __int64 v11; // r13
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  int LowPart; // r15d
  unsigned int Length; // eax
  int v15; // esi
  unsigned int v16; // ecx
  NTSTATUS Status; // edi
  PDEVICE_OBJECT v18; // r10
  __int64 v19; // rdx
  PFLT_IO_PARAMETER_BLOCK v20; // rsi
  bool v21; // zf
  LARGE_INTEGER AllocationSize; // rcx
  PVOID EaBuffer; // rsi
  KPROCESSOR_MODE RequestorMode; // r13
  char PlaceholderCompatMode; // al
  DWORD v26; // ebx
  DWORD v27; // ebx
  DWORD v28; // ebx
  DWORD v29; // ebx
  DWORD v30; // ebx
  int v31; // ecx
  int DirectoryBufferForFileIdAllExtdBothDirectoryInformation; // eax
  int v33; // ecx
  int v34; // ecx
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx
  ULONG_PTR v38; // rax
  __int64 v39; // r8
  __int64 v41; // [rsp+50h] [rbp-28h]
  struct _FILE_OBJECT *v42; // [rsp+58h] [rbp-20h]
  __int64 v43; // [rsp+60h] [rbp-18h]
  PFLT_CONTEXT Context; // [rsp+68h] [rbp-10h]
  unsigned int v45; // [rsp+C0h] [rbp+48h] BYREF
  __int64 v46; // [rsp+C8h] [rbp+50h]
  ULONG Information; // [rsp+D0h] [rbp+58h]
  PFLT_CALLBACK_DATA RetNewCallbackData; // [rsp+D8h] [rbp+60h] BYREF

  v46 = a2;
  v2 = *(struct _FILE_OBJECT **)(a2 + 32);
  Pool2 = 0;
  v4 = *(struct _FLT_INSTANCE **)(a2 + 24);
  v42 = v2;
  RetNewCallbackData = 0;
  v6 = 0;
  v45 = 0;
  v7 = 0;
  v8 = 0;
  StreamHandleContext = HsmpGetStreamHandleContext(CallbackData, v4, v2);
  Context = (PFLT_CONTEXT)StreamHandleContext;
  if ( StreamHandleContext )
  {
    v10 = *(_QWORD *)(*(_QWORD *)(StreamHandleContext + 16) + 16LL);
    v11 = *(_QWORD *)(v10 + 16);
    v41 = *(_QWORD *)(v10 + 32);
  }
  else
  {
    v11 = 0;
    v41 = 0;
  }
  Iopb = CallbackData->Iopb;
  v43 = v11;
  LowPart = Iopb->Parameters.Read.ByteOffset.LowPart;
  if ( LowPart > 60 )
  {
    switch ( LowPart )
    {
      case '?':
        v6 = 114;
        v8 = 63;
        break;
      case 'N':
LABEL_11:
        v6 = 80;
        v7 = 80;
LABEL_19:
        v8 = 78;
        goto LABEL_31;
      case 'O':
        v7 = 106;
        v6 = 106;
        goto LABEL_15;
      case 'P':
        v6 = 96;
        v8 = 80;
        break;
      case 'Q':
        v6 = 122;
        v8 = 81;
        break;
      default:
        goto LABEL_31;
    }
  }
  else
  {
    if ( LowPart != 60 )
    {
      if ( LowPart == 1 )
      {
        v6 = 64;
      }
      else
      {
        if ( LowPart != 2 )
        {
          switch ( LowPart )
          {
            case 3:
              v6 = 94;
              break;
            case 37:
              v6 = 104;
              break;
            case 38:
              goto LABEL_11;
            default:
              goto LABEL_31;
          }
          v7 = 106;
LABEL_15:
          v8 = 79;
          goto LABEL_31;
        }
        v6 = 68;
      }
      v7 = 80;
      goto LABEL_19;
    }
    v6 = 88;
    v8 = 60;
  }
  v7 = v6;
LABEL_31:
  Length = Iopb->Parameters.Read.Length;
  v15 = v7 - v6;
  v16 = Length + v15;
  if ( Length + v15 < Length )
  {
    Status = -1073741811;
    HsmDbgBreakOnStatus(-1073741811);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqqiDDd(
        WPP_GLOBAL_Control->AttachedDevice,
        WPP_GLOBAL_Control,
        v39,
        CallbackData,
        v11,
        v42,
        v41,
        CallbackData->Iopb->Parameters.Read.Length,
        v15);
    }
    goto LABEL_94;
  }
  if ( v16 > 0x100000 )
    v16 = 0x100000;
  Information = v16;
  Pool2 = (void *)ExAllocatePool2(256, v16, 1683059528);
  if ( Pool2 )
  {
    Status = FltAllocateCallbackDataEx(
               *(PFLT_INSTANCE *)(v46 + 24),
               *(PFILE_OBJECT *)(v46 + 32),
               1u,
               &RetNewCallbackData);
    HsmDbgBreakOnStatus(Status);
    if ( Status < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_94;
      }
      v19 = 12;
      goto LABEL_39;
    }
    Status = FltPropagateIrpExtension(CallbackData, RetNewCallbackData, 0);
    HsmDbgBreakOnStatus(Status);
    if ( Status < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_94;
      }
      v19 = 13;
      goto LABEL_39;
    }
    RetNewCallbackData->Iopb->MajorFunction = 12;
    RetNewCallbackData->Iopb->MinorFunction = 1;
    RetNewCallbackData->Iopb->Parameters.Read.Length = Information;
    RetNewCallbackData->Iopb->Parameters.QueryEa.EaList = CallbackData->Iopb->Parameters.QueryEa.EaList;
    RetNewCallbackData->Iopb->Parameters.Read.ByteOffset.LowPart = v8;
    RetNewCallbackData->Iopb->Parameters.Create.EaLength = CallbackData->Iopb->Parameters.Create.EaLength;
    RetNewCallbackData->Iopb->Parameters.Create.EaBuffer = Pool2;
    RetNewCallbackData->Iopb->Parameters.Create.AllocationSize.QuadPart = 0;
    RetNewCallbackData->Iopb->OperationFlags = CallbackData->Iopb->OperationFlags;
    FltPerformSynchronousIo(RetNewCallbackData);
    Status = RetNewCallbackData->IoStatus.Status;
    HsmDbgBreakOnStatus(Status);
    Information = RetNewCallbackData->IoStatus.Information;
    FltFreeCallbackData(RetNewCallbackData);
    RetNewCallbackData = 0;
    CallbackData->IoStatus.Status = Status;
    if ( Status < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        goto LABEL_94;
      }
      v19 = 17;
      goto LABEL_39;
    }
    v20 = CallbackData->Iopb;
    v21 = v20->Parameters.Create.AllocationSize.QuadPart == 0;
    LODWORD(v46) = v20->Parameters.Read.Length;
    if ( v21 )
    {
      RequestorMode = CallbackData->RequestorMode;
      EaBuffer = v20->Parameters.Create.EaBuffer;
    }
    else
    {
      Status = FltLockUserBuffer(CallbackData);
      HsmDbgBreakOnStatus(Status);
      if ( Status < 0 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_94;
        }
        v19 = 14;
        goto LABEL_39;
      }
      AllocationSize = CallbackData->Iopb->Parameters.Create.AllocationSize;
      if ( (*(_BYTE *)(AllocationSize.QuadPart + 10) & 5) != 0 )
        EaBuffer = *(PVOID *)(AllocationSize.QuadPart + 24);
      else
        EaBuffer = MmMapLockedPagesSpecifyCache((PMDL)AllocationSize.QuadPart, 0, MmCached, 0, 0, 0x40000010u);
      if ( !EaBuffer )
      {
        Status = -1073741801;
        HsmDbgBreakOnStatus(-1073741801);
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_94;
        }
        v19 = 15;
        goto LABEL_39;
      }
      RequestorMode = 0;
    }
    PlaceholderCompatMode = HsmOsGetPlaceholderCompatMode(CallbackData);
    v26 = v8 - 60;
    if ( v26 )
    {
      v27 = v26 - 3;
      if ( v27 )
      {
        v28 = v27 - 15;
        if ( v28 )
        {
          v29 = v28 - 1;
          if ( v29 )
          {
            v30 = v29 - 1;
            if ( v30 )
            {
              if ( v30 != 1 )
                goto LABEL_85;
              v31 = v46;
              LOBYTE(v31) = PlaceholderCompatMode;
              DirectoryBufferForFileIdAllExtdBothDirectoryInformation = HsmiMungeQueryDirectoryBufferForFileIdAllExtdBothDirectoryInformation(
                                                                          v31,
                                                                          LowPart,
                                                                          (_DWORD)Pool2,
                                                                          Information,
                                                                          RequestorMode,
                                                                          v46,
                                                                          (__int64)EaBuffer,
                                                                          (__int64)&v45);
            }
            else
            {
              v33 = v46;
              LOBYTE(v33) = PlaceholderCompatMode;
              DirectoryBufferForFileIdAllExtdBothDirectoryInformation = HsmiMungeQueryDirectoryBufferForFileIdAllExtdDirectoryInformation(
                                                                          v33,
                                                                          LowPart,
                                                                          (_DWORD)Pool2,
                                                                          Information,
                                                                          RequestorMode,
                                                                          v46,
                                                                          (__int64)EaBuffer,
                                                                          (__int64)&v45);
            }
          }
          else
          {
            v34 = v46;
            LOBYTE(v34) = PlaceholderCompatMode;
            DirectoryBufferForFileIdAllExtdBothDirectoryInformation = HsmiMungeQueryDirectoryBufferWithShortnameFileId64(
                                                                        v34,
                                                                        LowPart,
                                                                        (_DWORD)Pool2,
                                                                        Information,
                                                                        RequestorMode,
                                                                        v46,
                                                                        (__int64)EaBuffer,
                                                                        (__int64)&v45);
          }
        }
        else
        {
          v35 = v46;
          LOBYTE(v35) = PlaceholderCompatMode;
          DirectoryBufferForFileIdAllExtdBothDirectoryInformation = HsmiMungeQueryDirectoryBufferWithoutShortnameFileId64(
                                                                      v35,
                                                                      LowPart,
                                                                      (_DWORD)Pool2,
                                                                      Information,
                                                                      RequestorMode,
                                                                      v46,
                                                                      (__int64)EaBuffer,
                                                                      (__int64)&v45);
        }
      }
      else
      {
        v36 = v46;
        LOBYTE(v36) = PlaceholderCompatMode;
        DirectoryBufferForFileIdAllExtdBothDirectoryInformation = HsmiMungeQueryDirectoryBufferForFileIdExtdBothDirectoryInformation(
                                                                    v36,
                                                                    LowPart,
                                                                    (_DWORD)Pool2,
                                                                    Information,
                                                                    RequestorMode,
                                                                    v46,
                                                                    (__int64)EaBuffer,
                                                                    (__int64)&v45);
      }
    }
    else
    {
      v37 = v46;
      LOBYTE(v37) = PlaceholderCompatMode;
      DirectoryBufferForFileIdAllExtdBothDirectoryInformation = HsmiMungeQueryDirectoryBufferForFileIdExtdDirectoryInformation(
                                                                  v37,
                                                                  LowPart,
                                                                  (_DWORD)Pool2,
                                                                  Information,
                                                                  RequestorMode,
                                                                  v46,
                                                                  (__int64)EaBuffer,
                                                                  (__int64)&v45);
    }
    Status = DirectoryBufferForFileIdAllExtdBothDirectoryInformation;
    HsmDbgBreakOnStatus(DirectoryBufferForFileIdAllExtdBothDirectoryInformation);
    if ( Status < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqiqd(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          WPP_3a0b160e0a683f3dea1866dfb9c0f226_Traceguids,
          CallbackData,
          v43,
          v42,
          v41,
          Status);
      }
      goto LABEL_94;
    }
LABEL_85:
    v38 = v45;
    goto LABEL_95;
  }
  Status = -1073741670;
  HsmDbgBreakOnStatus(-1073741670);
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
  {
    goto LABEL_94;
  }
  v19 = 11;
LABEL_39:
  WPP_SF_qqiqd(
    v18->AttachedDevice,
    v19,
    WPP_3a0b160e0a683f3dea1866dfb9c0f226_Traceguids,
    CallbackData,
    v11,
    v42,
    v41,
    Status);
LABEL_94:
  CallbackData->IoStatus.Status = Status;
  v38 = 0;
LABEL_95:
  CallbackData->IoStatus.Information = v38;
  if ( RetNewCallbackData )
    FltFreeCallbackData(RetNewCallbackData);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x64517348u);
  if ( Context )
    FltReleaseContext(Context);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400626b4  mov     [rsp-40h+arg_8], rdx
0x1400626b9  push    rbp
0x1400626ba  push    rbx
0x1400626bb  push    rsi
0x1400626bc  push    rdi
0x1400626bd  push    r12
0x1400626bf  push    r13
0x1400626c1  push    r14
0x1400626c3  push    r15
0x1400626c5  mov     rbp, rsp
0x1400626c8  sub     rsp, 78h
0x1400626cc  mov     rax, [rdx+20h]
0x1400626d0  xor     r12d, r12d
0x1400626d3  mov     rdx, [rdx+18h]; Instance
0x1400626d7  mov     r8, rax; FileObject
0x1400626da  mov     r14, rcx
0x1400626dd  mov     [rbp+var_20], rax
0x1400626e1  mov     [rbp+RetNewCallbackData], r12
0x1400626e5  mov     edi, r12d
0x1400626e8  mov     [rbp+arg_0], r12d
0x1400626ec  mov     esi, r12d
0x1400626ef  mov     ebx, r12d
0x1400626f2  call    HsmpGetStreamHandleContext
0x1400626f7  mov     [rbp+Context], rax
0x1400626fb  test    rax, rax
0x1400626fe  jz      short loc_140062716
0x140062700  mov     rcx, [rax+10h]
0x140062704  mov     rdx, [rcx+10h]
0x140062708  mov     rax, [rdx+20h]
0x14006270c  mov     r13, [rdx+10h]
0x140062710  mov     [rbp+var_28], rax
0x140062714  jmp     short loc_14006271D
0x140062716  mov     r13, r12
0x140062719  mov     [rbp+var_28], r12
0x14006271d  mov     rdx, [r14+10h]
0x140062721  mov     [rbp+var_18], r13
0x140062725  mov     r15d, [rdx+28h]
0x140062729  cmp     r15d, 3Ch ; '<'
0x14006272d  jg      short loc_140062796
0x14006272f  jz      short loc_14006278C
0x140062731  mov     ecx, r15d
0x140062734  sub     ecx, 1
0x140062737  jz      short loc_14006277B
0x140062739  sub     ecx, 1
0x14006273c  jz      short loc_140062774
0x14006273e  sub     ecx, 1
0x140062741  jz      short loc_140062763
0x140062743  sub     ecx, 22h ; '"'
0x140062746  jz      short loc_14006275C
0x140062748  cmp     ecx, 1
0x14006274b  jnz     loc_1400627D7
0x140062751  mov     ebx, 50h ; 'P'
0x140062756  mov     edi, ebx
0x140062758  mov     esi, ebx
0x14006275a  jmp     short loc_140062785
0x14006275c  mov     edi, 68h ; 'h'
0x140062761  jmp     short loc_140062768
0x140062763  mov     edi, 5Eh ; '^'
0x140062768  mov     esi, 6Ah ; 'j'
0x14006276d  mov     ebx, 4Fh ; 'O'
0x140062772  jmp     short loc_1400627D7
0x140062774  mov     edi, 44h ; 'D'
0x140062779  jmp     short loc_140062780
0x14006277b  mov     edi, 40h ; '@'
0x140062780  mov     esi, 50h ; 'P'
0x140062785  mov     ebx, 4Eh ; 'N'
0x14006278a  jmp     short loc_1400627D7
0x14006278c  mov     edi, 58h ; 'X'
0x140062791  lea     ebx, [rdi-1Ch]
0x140062794  jmp     short loc_1400627D5
0x140062796  mov     ecx, r15d
0x140062799  sub     ecx, 3Fh ; '?'
0x14006279c  jz      short loc_1400627CD
0x14006279e  sub     ecx, 0Fh
0x1400627a1  jz      short loc_140062751
0x1400627a3  sub     ecx, 1
0x1400627a6  jz      short loc_1400627C4
0x1400627a8  sub     ecx, 1
0x1400627ab  jz      short loc_1400627BA
0x1400627ad  cmp     ecx, 1
0x1400627b0  jnz     short loc_1400627D7
0x1400627b2  lea     edi, [rcx+79h]
0x1400627b5  lea     ebx, [rcx+50h]
0x1400627b8  jmp     short loc_1400627D5
0x1400627ba  mov     edi, 60h ; '`'
0x1400627bf  lea     ebx, [rdi-10h]
0x1400627c2  jmp     short loc_1400627D5
0x1400627c4  mov     esi, 6Ah ; 'j'
0x1400627c9  mov     edi, esi
0x1400627cb  jmp     short loc_14006276D
0x1400627cd  mov     edi, 72h ; 'r'
0x1400627d2  lea     ebx, [rdi-33h]
0x1400627d5  mov     esi, edi
0x1400627d7  mov     eax, [rdx+18h]
0x1400627da  sub     esi, edi
0x1400627dc  lea     ecx, [rax+rsi]
0x1400627df  cmp     ecx, eax
0x1400627e1  jb      loc_140062CF3
0x1400627e7  mov     eax, 100000h
0x1400627ec  mov     r8d, 64517348h
0x1400627f2  cmp     ecx, eax
0x1400627f4  cmova   ecx, eax
0x1400627f7  mov     [rbp+arg_10], ecx
0x1400627fa  mov     edx, ecx
0x1400627fc  mov     ecx, 100h
0x140062801  call    cs:__imp_ExAllocatePool2
0x140062808  nop     dword ptr [rax+rax+00h]
0x14006280d  mov     r12, rax
0x140062810  test    rax, rax
0x140062813  jnz     short loc_140062887
0x140062815  mov     edi, 0C000009Ah
0x14006281a  mov     ecx, edi
0x14006281c  call    HsmDbgBreakOnStatus
0x140062821  mov     r10, cs:WPP_GLOBAL_Control
0x140062828  lea     rcx, WPP_GLOBAL_Control
0x14006282f  cmp     r10, rcx
0x140062832  jz      loc_140062D51
0x140062838  mov     eax, [r10+2Ch]
0x14006283c  test    al, 1
0x14006283e  jz      loc_140062D51
0x140062844  cmp     byte ptr [r10+29h], 2
0x140062849  jb      loc_140062D51
0x14006284f  lea     edx, [r12+0Bh]
0x140062854  mov     rax, [rbp+var_28]
0x140062858  mov     dword ptr [rsp+78h+var_40], edi
0x14006285c  mov     [rsp+78h+var_48], rax
0x140062861  mov     rax, [rbp+var_20]
0x140062865  mov     qword ptr [rsp+78h+Priority], rax
0x14006286a  mov     qword ptr [rsp+78h+BugCheckOnFailure], r13
0x14006286f  mov     rcx, [r10+18h]
0x140062873  lea     r8, WPP_3a0b160e0a683f3dea1866dfb9c0f226_Traceguids
0x14006287a  mov     r9, r14
0x14006287d  call    WPP_SF_qqiqd
0x140062882  jmp     loc_140062D51
0x140062887  mov     rcx, [rbp+arg_8]
0x14006288b  lea     r9, [rbp+RetNewCallbackData]; RetNewCallbackData
0x14006288f  mov     r8d, 1; Flags
0x140062895  mov     rdx, [rcx+20h]; FileObject
0x140062899  mov     rcx, [rcx+18h]; Instance
0x14006289d  call    cs:__imp_FltAllocateCallbackDataEx
0x1400628a4  nop     dword ptr [rax+rax+00h]
0x1400628a9  mov     ecx, eax
0x1400628ab  mov     edi, eax
0x1400628ad  call    HsmDbgBreakOnStatus
0x1400628b2  test    edi, edi
0x1400628b4  jns     short loc_1400628EF
0x1400628b6  mov     r10, cs:WPP_GLOBAL_Control
0x1400628bd  lea     rcx, WPP_GLOBAL_Control
0x1400628c4  cmp     r10, rcx
0x1400628c7  jz      loc_140062D51
0x1400628cd  mov     ecx, [r10+2Ch]
0x1400628d1  test    cl, 1
0x1400628d4  jz      loc_140062D51
0x1400628da  cmp     byte ptr [r10+29h], 2
0x1400628df  jb      loc_140062D51
0x1400628e5  mov     edx, 0Ch
0x1400628ea  jmp     loc_140062854
0x1400628ef  mov     rdx, [rbp+RetNewCallbackData]
0x1400628f3  xor     r8d, r8d
0x1400628f6  mov     rcx, r14
0x1400628f9  call    cs:__imp_FltPropagateIrpExtension
0x140062900  nop     dword ptr [rax+rax+00h]
0x140062905  mov     ecx, eax
0x140062907  mov     edi, eax
0x140062909  call    HsmDbgBreakOnStatus
0x14006290e  test    edi, edi
0x140062910  jns     short loc_14006294A
0x140062912  mov     r10, cs:WPP_GLOBAL_Control
0x140062919  lea     rcx, WPP_GLOBAL_Control
0x140062920  cmp     r10, rcx
0x140062923  jz      loc_140062D51
0x140062929  mov     eax, [r10+2Ch]
0x14006292d  test    al, 1
0x14006292f  jz      loc_140062D51
0x140062935  cmp     byte ptr [r10+29h], 2
0x14006293a  jb      loc_140062D51
0x140062940  mov     edx, 0Dh
0x140062945  jmp     loc_140062854
0x14006294a  mov     rax, [rbp+RetNewCallbackData]
0x14006294e  mov     rcx, [rax+10h]
0x140062952  mov     byte ptr [rcx+4], 0Ch
0x140062956  mov     rax, [rbp+RetNewCallbackData]
0x14006295a  mov     rcx, [rax+10h]
0x14006295e  mov     byte ptr [rcx+5], 1
0x140062962  mov     rax, [rbp+RetNewCallbackData]
0x140062966  mov     rcx, [rax+10h]
0x14006296a  mov     eax, [rbp+arg_10]
0x14006296d  mov     [rcx+18h], eax
0x140062970  mov     rax, [rbp+RetNewCallbackData]
0x140062974  mov     rdx, [r14+10h]
0x140062978  mov     rcx, [rax+10h]
0x14006297c  mov     rax, [rdx+20h]
0x140062980  mov     [rcx+20h], rax
0x140062984  mov     rax, [rbp+RetNewCallbackData]
0x140062988  mov     rcx, [rax+10h]
0x14006298c  mov     [rcx+28h], ebx
0x14006298f  mov     rax, [rbp+RetNewCallbackData]
0x140062993  mov     rdx, [r14+10h]
0x140062997  mov     rcx, [rax+10h]
0x14006299b  mov     eax, [rdx+30h]
0x14006299e  mov     [rcx+30h], eax
0x1400629a1  mov     rax, [rbp+RetNewCallbackData]
0x1400629a5  mov     rcx, [rax+10h]
0x1400629a9  mov     [rcx+38h], r12
0x1400629ad  mov     rax, [rbp+RetNewCallbackData]
0x1400629b1  mov     rcx, [rax+10h]
0x1400629b5  mov     qword ptr [rcx+40h], 0
0x1400629bd  mov     rax, [rbp+RetNewCallbackData]
0x1400629c1  mov     rdx, [r14+10h]
0x1400629c5  mov     rcx, [rax+10h]
0x1400629c9  mov     al, [rdx+6]
0x1400629cc  mov     [rcx+6], al
0x1400629cf  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x1400629d3  call    cs:__imp_FltPerformSynchronousIo
0x1400629da  nop     dword ptr [rax+rax+00h]
0x1400629df  mov     rax, [rbp+RetNewCallbackData]
0x1400629e3  mov     edi, [rax+18h]
0x1400629e6  mov     ecx, edi
0x1400629e8  call    HsmDbgBreakOnStatus
0x1400629ed  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x1400629f1  mov     eax, [rcx+20h]
0x1400629f4  mov     [rbp+arg_10], eax
0x1400629f7  call    cs:__imp_FltFreeCallbackData
0x1400629fe  nop     dword ptr [rax+rax+00h]
0x140062a03  mov     [rbp+RetNewCallbackData], 0
0x140062a0b  mov     [r14+18h], edi
0x140062a0f  test    edi, edi
0x140062a11  js      loc_140062CC7
0x140062a17  mov     rsi, [r14+10h]
0x140062a1b  cmp     qword ptr [rsi+40h], 0
0x140062a20  mov     eax, [rsi+18h]
0x140062a23  mov     dword ptr [rbp+arg_8], eax
0x140062a26  jz      loc_140062B08
0x140062a2c  mov     rcx, r14; CallbackData
0x140062a2f  call    cs:__imp_FltLockUserBuffer
0x140062a36  nop     dword ptr [rax+rax+00h]
0x140062a3b  mov     ecx, eax
0x140062a3d  mov     edi, eax
0x140062a3f  call    HsmDbgBreakOnStatus
0x140062a44  test    edi, edi
0x140062a46  jns     short loc_140062A80
0x140062a48  mov     r10, cs:WPP_GLOBAL_Control
0x140062a4f  lea     rcx, WPP_GLOBAL_Control
0x140062a56  cmp     r10, rcx
0x140062a59  jz      loc_140062D51
0x140062a5f  mov     eax, [r10+2Ch]
0x140062a63  test    al, 1
0x140062a65  jz      loc_140062D51
0x140062a6b  cmp     byte ptr [r10+29h], 2
0x140062a70  jb      loc_140062D51
0x140062a76  mov     edx, 0Eh
0x140062a7b  jmp     loc_140062854
0x140062a80  mov     rax, [r14+10h]
0x140062a84  mov     rcx, [rax+40h]; MemoryDescriptorList
0x140062a88  test    byte ptr [rcx+0Ah], 5
0x140062a8c  jz      short loc_140062A94
0x140062a8e  mov     rsi, [rcx+18h]
0x140062a92  jmp     short loc_140062ABC
0x140062a94  xor     r9d, r9d; RequestedAddress
0x140062a97  mov     [rsp+78h+Priority], 40000010h; Priority
0x140062a9f  xor     edx, edx; AccessMode
0x140062aa1  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140062aa9  lea     r8d, [r9+1]; CacheType
0x140062aad  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140062ab4  nop     dword ptr [rax+rax+00h]
0x140062ab9  mov     rsi, rax
0x140062abc  test    rsi, rsi
0x140062abf  jnz     short loc_140062B03
0x140062ac1  mov     edi, 0C0000017h
0x140062ac6  mov     ecx, edi
0x140062ac8  call    HsmDbgBreakOnStatus
0x140062acd  mov     r10, cs:WPP_GLOBAL_Control
0x140062ad4  lea     rcx, WPP_GLOBAL_Control
0x140062adb  cmp     r10, rcx
0x140062ade  jz      loc_140062D51
0x140062ae4  mov     eax, [r10+2Ch]
0x140062ae8  test    al, 1
0x140062aea  jz      loc_140062D51
0x140062af0  cmp     byte ptr [r10+29h], 2
0x140062af5  jb      loc_140062D51
0x140062afb  lea     edx, [rsi+0Fh]
0x140062afe  jmp     loc_140062854
0x140062b03  xor     r13b, r13b
0x140062b06  jmp     short loc_140062B10
0x140062b08  mov     r13b, [r14+50h]
0x140062b0c  mov     rsi, [rsi+38h]
0x140062b10  mov     rcx, r14
0x140062b13  call    HsmOsGetPlaceholderCompatMode
0x140062b18  sub     ebx, 3Ch ; '<'
0x140062b1b  jz      loc_140062C30
0x140062b21  sub     ebx, 3
0x140062b24  jz      loc_140062C03
0x140062b2a  sub     ebx, 0Fh
0x140062b2d  jz      loc_140062BD6
0x140062b33  sub     ebx, 1
0x140062b36  jz      short loc_140062BA6
0x140062b38  sub     ebx, 1
0x140062b3b  jz      short loc_140062B76
0x140062b3d  cmp     ebx, 1
0x140062b40  jnz     loc_140062CBF
  ... truncated ...
```
