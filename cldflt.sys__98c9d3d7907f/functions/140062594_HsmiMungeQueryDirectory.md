# HsmiMungeQueryDirectory

- ea: `0x140062594`
- end: `0x140062c92`
- name: `HsmiMungeQueryDirectory`
- size: `1790`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140061f40`

## callees

- `0x140003c50`
- `0x140009364`
- `0x14000ac28`
- `0x14001d40c`
- `0x14004543c`
- `0x140045690`
- `0x1400458c4`
- `0x140045b0c`
- `0x140045d40`
- `0x140046280`
- `0x14004c5e0`
- `0x140062594`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006298d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006298d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062c5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062c5d`
- `ntoskrnl!ExAllocatePool2` at `0x1400626e1`
- `ntoskrnl!ExAllocatePool2` at `0x1400626e1`
- `FLTMGR!FltAllocateCallbackDataEx` at `0x14006277d`
- `FLTMGR!FltAllocateCallbackDataEx` at `0x14006277d`
- `FLTMGR!FltPropagateIrpExtension` at `0x1400627d9`
- `FLTMGR!FltPropagateIrpExtension` at `0x1400627d9`
- `FLTMGR!FltLockUserBuffer` at `0x14006290f`
- `FLTMGR!FltLockUserBuffer` at `0x14006290f`
- `FLTMGR!FltPerformSynchronousIo` at `0x1400628b3`
- `FLTMGR!FltPerformSynchronousIo` at `0x1400628b3`
- `FLTMGR!FltFreeCallbackData` at `0x1400628d7`
- `FLTMGR!FltFreeCallbackData` at `0x140062c44`
- `FLTMGR!FltFreeCallbackData` at `0x1400628d7`
- `FLTMGR!FltFreeCallbackData` at `0x140062c44`
- `FLTMGR!FltReleaseContext` at `0x140062c72`
- `FLTMGR!FltReleaseContext` at `0x140062c72`

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
  __int64 v17; // rdi
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
  unsigned int DirectoryBufferForFileIdAllExtdBothDirectoryInformation; // eax
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
    LODWORD(v17) = -1073741811;
    HsmDbgBreakOnStatus(3221225485LL);
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
    v17 = (unsigned int)FltAllocateCallbackDataEx(
                          *(PFLT_INSTANCE *)(v46 + 24),
                          *(PFILE_OBJECT *)(v46 + 32),
                          1u,
                          &RetNewCallbackData);
    HsmDbgBreakOnStatus(v17);
    if ( (int)v17 < 0 )
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
    LODWORD(v17) = FltPropagateIrpExtension(CallbackData, RetNewCallbackData, 0);
    HsmDbgBreakOnStatus((unsigned int)v17);
    if ( (int)v17 < 0 )
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
    LODWORD(v17) = RetNewCallbackData->IoStatus.Status;
    HsmDbgBreakOnStatus((unsigned int)v17);
    Information = RetNewCallbackData->IoStatus.Information;
    FltFreeCallbackData(RetNewCallbackData);
    RetNewCallbackData = 0;
    CallbackData->IoStatus.Status = v17;
    if ( (int)v17 < 0 )
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
      LODWORD(v17) = FltLockUserBuffer(CallbackData);
      HsmDbgBreakOnStatus((unsigned int)v17);
      if ( (int)v17 < 0 )
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
        LODWORD(v17) = -1073741801;
        HsmDbgBreakOnStatus(3221225495LL);
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
    PlaceholderCompatMode = HsmOsGetPlaceholderCompatMode((__int64)CallbackData);
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
    LODWORD(v17) = DirectoryBufferForFileIdAllExtdBothDirectoryInformation;
    HsmDbgBreakOnStatus(DirectoryBufferForFileIdAllExtdBothDirectoryInformation);
    if ( (int)v17 < 0 )
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
          v17);
      }
      goto LABEL_94;
    }
LABEL_85:
    v38 = v45;
    goto LABEL_95;
  }
  LODWORD(v17) = -1073741670;
  HsmDbgBreakOnStatus(3221225626LL);
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
    v17);
LABEL_94:
  CallbackData->IoStatus.Status = v17;
  v38 = 0;
LABEL_95:
  CallbackData->IoStatus.Information = v38;
  if ( RetNewCallbackData )
    FltFreeCallbackData(RetNewCallbackData);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x64517348u);
  if ( Context )
    FltReleaseContext(Context);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x140062594  mov     [rsp-40h+arg_8], rdx
0x140062599  push    rbp
0x14006259a  push    rbx
0x14006259b  push    rsi
0x14006259c  push    rdi
0x14006259d  push    r12
0x14006259f  push    r13
0x1400625a1  push    r14
0x1400625a3  push    r15
0x1400625a5  mov     rbp, rsp
0x1400625a8  sub     rsp, 78h
0x1400625ac  mov     rax, [rdx+20h]
0x1400625b0  xor     r12d, r12d
0x1400625b3  mov     rdx, [rdx+18h]; Instance
0x1400625b7  mov     r8, rax; FileObject
0x1400625ba  mov     r14, rcx
0x1400625bd  mov     [rbp+var_20], rax
0x1400625c1  mov     [rbp+RetNewCallbackData], r12
0x1400625c5  mov     edi, r12d
0x1400625c8  mov     [rbp+arg_0], r12d
0x1400625cc  mov     esi, r12d
0x1400625cf  mov     ebx, r12d
0x1400625d2  call    HsmpGetStreamHandleContext
0x1400625d7  mov     [rbp+Context], rax
0x1400625db  test    rax, rax
0x1400625de  jz      short loc_1400625F6
0x1400625e0  mov     rcx, [rax+10h]
0x1400625e4  mov     rdx, [rcx+10h]
0x1400625e8  mov     rax, [rdx+20h]
0x1400625ec  mov     r13, [rdx+10h]
0x1400625f0  mov     [rbp+var_28], rax
0x1400625f4  jmp     short loc_1400625FD
0x1400625f6  mov     r13, r12
0x1400625f9  mov     [rbp+var_28], r12
0x1400625fd  mov     rdx, [r14+10h]
0x140062601  mov     [rbp+var_18], r13
0x140062605  mov     r15d, [rdx+28h]
0x140062609  cmp     r15d, 3Ch ; '<'
0x14006260d  jg      short loc_140062676
0x14006260f  jz      short loc_14006266C
0x140062611  mov     ecx, r15d
0x140062614  sub     ecx, 1
0x140062617  jz      short loc_14006265B
0x140062619  sub     ecx, 1
0x14006261c  jz      short loc_140062654
0x14006261e  sub     ecx, 1
0x140062621  jz      short loc_140062643
0x140062623  sub     ecx, 22h ; '"'
0x140062626  jz      short loc_14006263C
0x140062628  cmp     ecx, 1
0x14006262b  jnz     loc_1400626B7
0x140062631  mov     ebx, 50h ; 'P'
0x140062636  mov     edi, ebx
0x140062638  mov     esi, ebx
0x14006263a  jmp     short loc_140062665
0x14006263c  mov     edi, 68h ; 'h'
0x140062641  jmp     short loc_140062648
0x140062643  mov     edi, 5Eh ; '^'
0x140062648  mov     esi, 6Ah ; 'j'
0x14006264d  mov     ebx, 4Fh ; 'O'
0x140062652  jmp     short loc_1400626B7
0x140062654  mov     edi, 44h ; 'D'
0x140062659  jmp     short loc_140062660
0x14006265b  mov     edi, 40h ; '@'
0x140062660  mov     esi, 50h ; 'P'
0x140062665  mov     ebx, 4Eh ; 'N'
0x14006266a  jmp     short loc_1400626B7
0x14006266c  mov     edi, 58h ; 'X'
0x140062671  lea     ebx, [rdi-1Ch]
0x140062674  jmp     short loc_1400626B5
0x140062676  mov     ecx, r15d
0x140062679  sub     ecx, 3Fh ; '?'
0x14006267c  jz      short loc_1400626AD
0x14006267e  sub     ecx, 0Fh
0x140062681  jz      short loc_140062631
0x140062683  sub     ecx, 1
0x140062686  jz      short loc_1400626A4
0x140062688  sub     ecx, 1
0x14006268b  jz      short loc_14006269A
0x14006268d  cmp     ecx, 1
0x140062690  jnz     short loc_1400626B7
0x140062692  lea     edi, [rcx+79h]
0x140062695  lea     ebx, [rcx+50h]
0x140062698  jmp     short loc_1400626B5
0x14006269a  mov     edi, 60h ; '`'
0x14006269f  lea     ebx, [rdi-10h]
0x1400626a2  jmp     short loc_1400626B5
0x1400626a4  mov     esi, 6Ah ; 'j'
0x1400626a9  mov     edi, esi
0x1400626ab  jmp     short loc_14006264D
0x1400626ad  mov     edi, 72h ; 'r'
0x1400626b2  lea     ebx, [rdi-33h]
0x1400626b5  mov     esi, edi
0x1400626b7  mov     eax, [rdx+18h]
0x1400626ba  sub     esi, edi
0x1400626bc  lea     ecx, [rax+rsi]
0x1400626bf  cmp     ecx, eax
0x1400626c1  jb      loc_140062BD3
0x1400626c7  mov     eax, 100000h
0x1400626cc  mov     r8d, 64517348h
0x1400626d2  cmp     ecx, eax
0x1400626d4  cmova   ecx, eax
0x1400626d7  mov     [rbp+arg_10], ecx
0x1400626da  mov     edx, ecx
0x1400626dc  mov     ecx, 100h
0x1400626e1  call    cs:__imp_ExAllocatePool2
0x1400626e8  nop     dword ptr [rax+rax+00h]
0x1400626ed  mov     r12, rax
0x1400626f0  test    rax, rax
0x1400626f3  jnz     short loc_140062767
0x1400626f5  mov     edi, 0C000009Ah
0x1400626fa  mov     ecx, edi
0x1400626fc  call    HsmDbgBreakOnStatus
0x140062701  mov     r10, cs:WPP_GLOBAL_Control
0x140062708  lea     rcx, WPP_GLOBAL_Control
0x14006270f  cmp     r10, rcx
0x140062712  jz      loc_140062C31
0x140062718  mov     eax, [r10+2Ch]
0x14006271c  test    al, 1
0x14006271e  jz      loc_140062C31
0x140062724  cmp     byte ptr [r10+29h], 2
0x140062729  jb      loc_140062C31
0x14006272f  lea     edx, [r12+0Bh]
0x140062734  mov     rax, [rbp+var_28]
0x140062738  mov     dword ptr [rsp+78h+var_40], edi
0x14006273c  mov     [rsp+78h+var_48], rax
0x140062741  mov     rax, [rbp+var_20]
0x140062745  mov     qword ptr [rsp+78h+Priority], rax
0x14006274a  mov     qword ptr [rsp+78h+BugCheckOnFailure], r13
0x14006274f  mov     rcx, [r10+18h]
0x140062753  lea     r8, WPP_3a0b160e0a683f3dea1866dfb9c0f226_Traceguids
0x14006275a  mov     r9, r14
0x14006275d  call    WPP_SF_qqiqd
0x140062762  jmp     loc_140062C31
0x140062767  mov     rcx, [rbp+arg_8]
0x14006276b  lea     r9, [rbp+RetNewCallbackData]; RetNewCallbackData
0x14006276f  mov     r8d, 1; Flags
0x140062775  mov     rdx, [rcx+20h]; FileObject
0x140062779  mov     rcx, [rcx+18h]; Instance
0x14006277d  call    cs:__imp_FltAllocateCallbackDataEx
0x140062784  nop     dword ptr [rax+rax+00h]
0x140062789  mov     ecx, eax
0x14006278b  mov     edi, eax
0x14006278d  call    HsmDbgBreakOnStatus
0x140062792  test    edi, edi
0x140062794  jns     short loc_1400627CF
0x140062796  mov     r10, cs:WPP_GLOBAL_Control
0x14006279d  lea     rcx, WPP_GLOBAL_Control
0x1400627a4  cmp     r10, rcx
0x1400627a7  jz      loc_140062C31
0x1400627ad  mov     ecx, [r10+2Ch]
0x1400627b1  test    cl, 1
0x1400627b4  jz      loc_140062C31
0x1400627ba  cmp     byte ptr [r10+29h], 2
0x1400627bf  jb      loc_140062C31
0x1400627c5  mov     edx, 0Ch
0x1400627ca  jmp     loc_140062734
0x1400627cf  mov     rdx, [rbp+RetNewCallbackData]
0x1400627d3  xor     r8d, r8d
0x1400627d6  mov     rcx, r14
0x1400627d9  call    cs:__imp_FltPropagateIrpExtension
0x1400627e0  nop     dword ptr [rax+rax+00h]
0x1400627e5  mov     ecx, eax
0x1400627e7  mov     edi, eax
0x1400627e9  call    HsmDbgBreakOnStatus
0x1400627ee  test    edi, edi
0x1400627f0  jns     short loc_14006282A
0x1400627f2  mov     r10, cs:WPP_GLOBAL_Control
0x1400627f9  lea     rcx, WPP_GLOBAL_Control
0x140062800  cmp     r10, rcx
0x140062803  jz      loc_140062C31
0x140062809  mov     eax, [r10+2Ch]
0x14006280d  test    al, 1
0x14006280f  jz      loc_140062C31
0x140062815  cmp     byte ptr [r10+29h], 2
0x14006281a  jb      loc_140062C31
0x140062820  mov     edx, 0Dh
0x140062825  jmp     loc_140062734
0x14006282a  mov     rax, [rbp+RetNewCallbackData]
0x14006282e  mov     rcx, [rax+10h]
0x140062832  mov     byte ptr [rcx+4], 0Ch
0x140062836  mov     rax, [rbp+RetNewCallbackData]
0x14006283a  mov     rcx, [rax+10h]
0x14006283e  mov     byte ptr [rcx+5], 1
0x140062842  mov     rax, [rbp+RetNewCallbackData]
0x140062846  mov     rcx, [rax+10h]
0x14006284a  mov     eax, [rbp+arg_10]
0x14006284d  mov     [rcx+18h], eax
0x140062850  mov     rax, [rbp+RetNewCallbackData]
0x140062854  mov     rdx, [r14+10h]
0x140062858  mov     rcx, [rax+10h]
0x14006285c  mov     rax, [rdx+20h]
0x140062860  mov     [rcx+20h], rax
0x140062864  mov     rax, [rbp+RetNewCallbackData]
0x140062868  mov     rcx, [rax+10h]
0x14006286c  mov     [rcx+28h], ebx
0x14006286f  mov     rax, [rbp+RetNewCallbackData]
0x140062873  mov     rdx, [r14+10h]
0x140062877  mov     rcx, [rax+10h]
0x14006287b  mov     eax, [rdx+30h]
0x14006287e  mov     [rcx+30h], eax
0x140062881  mov     rax, [rbp+RetNewCallbackData]
0x140062885  mov     rcx, [rax+10h]
0x140062889  mov     [rcx+38h], r12
0x14006288d  mov     rax, [rbp+RetNewCallbackData]
0x140062891  mov     rcx, [rax+10h]
0x140062895  mov     qword ptr [rcx+40h], 0
0x14006289d  mov     rax, [rbp+RetNewCallbackData]
0x1400628a1  mov     rdx, [r14+10h]
0x1400628a5  mov     rcx, [rax+10h]
0x1400628a9  mov     al, [rdx+6]
0x1400628ac  mov     [rcx+6], al
0x1400628af  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x1400628b3  call    cs:__imp_FltPerformSynchronousIo
0x1400628ba  nop     dword ptr [rax+rax+00h]
0x1400628bf  mov     rax, [rbp+RetNewCallbackData]
0x1400628c3  mov     edi, [rax+18h]
0x1400628c6  mov     ecx, edi
0x1400628c8  call    HsmDbgBreakOnStatus
0x1400628cd  mov     rcx, [rbp+RetNewCallbackData]; CallbackData
0x1400628d1  mov     eax, [rcx+20h]
0x1400628d4  mov     [rbp+arg_10], eax
0x1400628d7  call    cs:__imp_FltFreeCallbackData
0x1400628de  nop     dword ptr [rax+rax+00h]
0x1400628e3  mov     [rbp+RetNewCallbackData], 0
0x1400628eb  mov     [r14+18h], edi
0x1400628ef  test    edi, edi
0x1400628f1  js      loc_140062BA7
0x1400628f7  mov     rsi, [r14+10h]
0x1400628fb  cmp     qword ptr [rsi+40h], 0
0x140062900  mov     eax, [rsi+18h]
0x140062903  mov     dword ptr [rbp+arg_8], eax
0x140062906  jz      loc_1400629E8
0x14006290c  mov     rcx, r14; CallbackData
0x14006290f  call    cs:__imp_FltLockUserBuffer
0x140062916  nop     dword ptr [rax+rax+00h]
0x14006291b  mov     ecx, eax
0x14006291d  mov     edi, eax
0x14006291f  call    HsmDbgBreakOnStatus
0x140062924  test    edi, edi
0x140062926  jns     short loc_140062960
0x140062928  mov     r10, cs:WPP_GLOBAL_Control
0x14006292f  lea     rcx, WPP_GLOBAL_Control
0x140062936  cmp     r10, rcx
0x140062939  jz      loc_140062C31
0x14006293f  mov     eax, [r10+2Ch]
0x140062943  test    al, 1
0x140062945  jz      loc_140062C31
0x14006294b  cmp     byte ptr [r10+29h], 2
0x140062950  jb      loc_140062C31
0x140062956  mov     edx, 0Eh
0x14006295b  jmp     loc_140062734
0x140062960  mov     rax, [r14+10h]
0x140062964  mov     rcx, [rax+40h]; MemoryDescriptorList
0x140062968  test    byte ptr [rcx+0Ah], 5
0x14006296c  jz      short loc_140062974
0x14006296e  mov     rsi, [rcx+18h]
0x140062972  jmp     short loc_14006299C
0x140062974  xor     r9d, r9d; RequestedAddress
0x140062977  mov     [rsp+78h+Priority], 40000010h; Priority
0x14006297f  xor     edx, edx; AccessMode
0x140062981  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140062989  lea     r8d, [r9+1]; CacheType
0x14006298d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140062994  nop     dword ptr [rax+rax+00h]
0x140062999  mov     rsi, rax
0x14006299c  test    rsi, rsi
0x14006299f  jnz     short loc_1400629E3
0x1400629a1  mov     edi, 0C0000017h
0x1400629a6  mov     ecx, edi
0x1400629a8  call    HsmDbgBreakOnStatus
0x1400629ad  mov     r10, cs:WPP_GLOBAL_Control
0x1400629b4  lea     rcx, WPP_GLOBAL_Control
0x1400629bb  cmp     r10, rcx
0x1400629be  jz      loc_140062C31
0x1400629c4  mov     eax, [r10+2Ch]
0x1400629c8  test    al, 1
0x1400629ca  jz      loc_140062C31
0x1400629d0  cmp     byte ptr [r10+29h], 2
0x1400629d5  jb      loc_140062C31
0x1400629db  lea     edx, [rsi+0Fh]
0x1400629de  jmp     loc_140062734
0x1400629e3  xor     r13b, r13b
0x1400629e6  jmp     short loc_1400629F0
0x1400629e8  mov     r13b, [r14+50h]
0x1400629ec  mov     rsi, [rsi+38h]
0x1400629f0  mov     rcx, r14
0x1400629f3  call    HsmOsGetPlaceholderCompatMode
0x1400629f8  sub     ebx, 3Ch ; '<'
0x1400629fb  jz      loc_140062B10
0x140062a01  sub     ebx, 3
0x140062a04  jz      loc_140062AE3
0x140062a0a  sub     ebx, 0Fh
0x140062a0d  jz      loc_140062AB6
0x140062a13  sub     ebx, 1
0x140062a16  jz      short loc_140062A86
0x140062a18  sub     ebx, 1
0x140062a1b  jz      short loc_140062A56
0x140062a1d  cmp     ebx, 1
0x140062a20  jnz     loc_140062B9F
  ... truncated ...
```
