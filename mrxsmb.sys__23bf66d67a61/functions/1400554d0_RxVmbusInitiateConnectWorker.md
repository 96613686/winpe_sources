# RxVmbusInitiateConnectWorker

- ea: `0x1400554d0`
- end: `0x14005591e`
- name: `RxVmbusInitiateConnectWorker`
- size: `1102`
- prototype: `void __stdcall(PVOID Context)`
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x14003838c`
- `0x140039fa8`
- `0x14003e14c`
- `0x1400400c4`
- `0x1400554d0`
- `0x1400559e4`
- `0x140055c64`
- `0x140056060`
- `0x140056c38`
- `0x140059ea0`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x14005553a`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14005553a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400555c6`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400555f1`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400555c6`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400555f1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400555da`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400555da`
- `ntoskrnl!ZwOpenFile` at `0x140055660`
- `ntoskrnl!ZwOpenFile` at `0x140055660`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400556df`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400556df`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400556c3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400557b7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400556c3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400557b7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005560d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005560d`
- `ntoskrnl!ExAllocatePool2` at `0x14005559c`
- `ntoskrnl!ExAllocatePool2` at `0x14005559c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140055717`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140055717`
- `ntoskrnl!IoFileObjectType` at `0x1400556f2`
- `ntoskrnl!ZwClose` at `0x140055770`
- `ntoskrnl!ZwClose` at `0x140055770`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055858`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055858`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140055782`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140055782`

## pseudocode

```c
void __fastcall RxVmbusInitiateConnectWorker(_QWORD *Context)
{
  __int64 v1; // r15
  _QWORD *v2; // rdi
  _WORD *v4; // rbx
  __int64 v5; // r13
  unsigned __int16 v6; // ax
  int v7; // ebx
  unsigned int v8; // esi
  int v9; // edx
  int v10; // r8d
  void *v11; // rcx
  unsigned int v12; // eax
  UNICODE_STRING Destination; // [rsp+40h] [rbp-39h] BYREF
  UNICODE_STRING Source; // [rsp+50h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-9h] BYREF
  void *FileHandle; // [rsp+E0h] [rbp+67h] BYREF
  PVOID Object; // [rsp+E8h] [rbp+6Fh] BYREF
  LARGE_INTEGER Interval; // [rsp+F0h] [rbp+77h] BYREF

  v1 = Context[1];
  v2 = (_QWORD *)Context[27];
  Object = 0;
  Destination = 0;
  FileHandle = (void *)-1LL;
  v4 = (_WORD *)(v1 + 48);
  Source = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  v5 = *(_QWORD *)(v1 + 32);
  if ( RtlPrefixUnicodeString(&VsmbServerPrefix, (PCUNICODE_STRING)(v1 + 48), 1u)
    && (unsigned __int16)*v4 == VsmbServerPrefix.Length + 76LL )
  {
    Source.Buffer = (wchar_t *)(*(_QWORD *)(v1 + 56) + 2 * ((unsigned __int64)VsmbServerPrefix.Length >> 1));
    v6 = *v4 - VsmbServerPrefix.Length;
    *(_DWORD *)&Destination.Length = 12582912;
    Source.Length = v6;
    Source.MaximumLength = v6;
    Destination.Buffer = (wchar_t *)ExAllocatePool2(66, 192, 1665366098);
    if ( Destination.Buffer )
    {
      RtlAppendUnicodeToString(&Destination, L"\\Device\\VMBus\\{4d12e519-17a0-4ae4-8eaa-5270fc6abdb7}-");
      RtlAppendUnicodeStringToString(&Destination, &Source);
      RtlAppendUnicodeToString(&Destination, L"-0000");
      v8 = 0;
      v7 = -1073741802;
      while ( v8 < 5 )
      {
        KeEnterCriticalRegion();
        ObjectAttributes.ObjectName = &Destination;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v7 = ZwOpenFile(&FileHandle, 0xC0000000, &ObjectAttributes, &IoStatusBlock, 0, 0x40u);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_LdqqZ(
            WPP_GLOBAL_Control->AttachedDevice,
            v9,
            v10,
            v7,
            v8,
            (char)v2,
            (char)FileHandle,
            (__int64)&Destination);
        }
        if ( v7 >= 0 )
        {
          v7 = ObReferenceObjectByHandle(FileHandle, 0, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
          if ( v7 >= 0 )
          {
            v2[13] = IoGetRelatedDeviceObject((PFILE_OBJECT)Object);
            v2[14] = Object;
            v11 = FileHandle;
            v2[15] = FileHandle;
            v7 = RxVmbusSendTransportNegotiateMessage(v11);
            if ( v7 >= 0 )
              v7 = RxVmbusRecvTransportNegotiateMessage((__int64)v2);
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_dq(
                WPP_GLOBAL_Control->AttachedDevice,
                30,
                WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids,
                (unsigned int)v7,
                FileHandle);
            }
            ZwClose(FileHandle);
          }
          KeLeaveCriticalRegion();
          goto LABEL_28;
        }
        Interval.QuadPart = 0;
        KeLeaveCriticalRegion();
        Interval.QuadPart = -10000000;
        KeDelayExecutionThread(0, 0, &Interval);
        ++v8;
      }
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_32;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids);
    }
    else
    {
      v7 = -1073741670;
    }
  }
  else
  {
    v7 = -1073741634;
  }
LABEL_28:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids, v2, v7);
  }
LABEL_32:
  if ( Destination.Buffer )
  {
    ExFreePoolWithTag(Destination.Buffer, 0x63437852u);
    Destination.Buffer = 0;
    *(_DWORD *)&Destination.Length = 0;
  }
  if ( v7 < 0 && _bittest16((const signed __int16 *)(v5 + 1314), 8u) )
  {
    __debugbreak();
    v7 = -1073741628;
  }
  *((_DWORD *)Context + 4) = v7;
  *((_DWORD *)Context + 5) = 0;
  (*(void (__fastcall **)(_QWORD *))(v1 + 136))(Context);
  if ( v7 >= 0 )
  {
    *(_DWORD *)(v2[16] + 20LL) = 4;
    *(_DWORD *)(v2[16] + 24LL) = 0;
    *(_DWORD *)(v2[16] + 8LL) = 0;
    v12 = VmbusRecvAsync(v2);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids, v12);
    }
  }
}

```

## disassembly

```asm
0x1400554d0  push    rbp
0x1400554d2  push    rbx
0x1400554d3  push    rsi
0x1400554d4  push    rdi
0x1400554d5  push    r13
0x1400554d7  push    r14
0x1400554d9  push    r15
0x1400554db  lea     rbp, [rsp-27h]
0x1400554e0  sub     rsp, 0A0h
0x1400554e7  mov     r15, [rcx+8]
0x1400554eb  xorps   xmm0, xmm0
0x1400554ee  mov     rdi, [rcx+0D8h]
0x1400554f5  xorps   xmm1, xmm1
0x1400554f8  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400554fc  mov     r14, rcx
0x1400554ff  mov     [rbp+57h+Object], 0
0x140055507  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x14005550b  mov     [rbp+57h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x140055513  lea     rbx, [r15+30h]
0x140055517  movups  xmmword ptr [rbp+57h+Source.Length], xmm1
0x14005551b  mov     rdx, rbx; String2
0x14005551e  xor     eax, eax
0x140055520  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140055524  mov     r8b, 1; CaseInSensitive
0x140055527  lea     rcx, VsmbServerPrefix; String1
0x14005552e  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140055532  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140055536  mov     r13, [r15+20h]
0x14005553a  call    cs:__imp_RtlPrefixUnicodeString
0x140055541  nop     dword ptr [rax+rax+00h]
0x140055546  test    al, al
0x140055548  jz      loc_140055807
0x14005554e  movzx   r8d, cs:VsmbServerPrefix.Length
0x140055556  movzx   eax, word ptr [rbx]
0x140055559  mov     edx, r8d
0x14005555c  lea     rcx, [r8+4Ch]
0x140055560  cmp     rax, rcx
0x140055563  jnz     loc_140055807
0x140055569  mov     rax, [r15+38h]
0x14005556d  shr     rdx, 1
0x140055570  lea     rcx, [rax+rdx*2]
0x140055574  mov     edx, 0C0h
0x140055579  mov     [rbp+57h+Source.Buffer], rcx
0x14005557d  movzx   eax, word ptr [rbx]
0x140055580  sub     ax, r8w
0x140055584  mov     dword ptr [rbp+57h+Destination.Length], 0C00000h
0x14005558b  lea     ecx, [rdx-7Eh]
0x14005558e  mov     [rbp+57h+Source.Length], ax
0x140055592  mov     r8d, 63437852h
0x140055598  mov     [rbp+57h+Source.MaximumLength], ax
0x14005559c  call    cs:__imp_ExAllocatePool2
0x1400555a3  nop     dword ptr [rax+rax+00h]
0x1400555a8  mov     [rbp+57h+Destination.Buffer], rax
0x1400555ac  test    rax, rax
0x1400555af  jnz     short loc_1400555BB
0x1400555b1  mov     ebx, 0C000009Ah
0x1400555b6  jmp     loc_14005580C
0x1400555bb  lea     rdx, aDeviceVmbus4d1; "\\Device\\VMBus\\{4d12e519-17a0-4ae4-8e"...
0x1400555c2  lea     rcx, [rbp+57h+Destination]; Destination
0x1400555c6  call    cs:__imp_RtlAppendUnicodeToString
0x1400555cd  nop     dword ptr [rax+rax+00h]
0x1400555d2  lea     rdx, [rbp+57h+Source]; Source
0x1400555d6  lea     rcx, [rbp+57h+Destination]; Destination
0x1400555da  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400555e1  nop     dword ptr [rax+rax+00h]
0x1400555e6  lea     rdx, a0000; "-0000"
0x1400555ed  lea     rcx, [rbp+57h+Destination]; Destination
0x1400555f1  call    cs:__imp_RtlAppendUnicodeToString
0x1400555f8  nop     dword ptr [rax+rax+00h]
0x1400555fd  xor     esi, esi
0x1400555ff  mov     ebx, 0C0000016h
0x140055604  cmp     esi, 5
0x140055607  jnb     loc_1400557C5
0x14005560d  call    cs:__imp_KeEnterCriticalRegion
0x140055614  nop     dword ptr [rax+rax+00h]
0x140055619  lea     rax, [rbp+57h+Destination]
0x14005561d  mov     [rsp+0D0h+OpenOptions], 40h ; '@'; OpenOptions
0x140055625  xorps   xmm0, xmm0
0x140055628  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14005562c  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140055630  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140055637  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14005563b  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140055643  mov     edx, 0C0000000h; DesiredAccess
0x140055648  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14005564f  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140055653  mov     [rsp+0D0h+ShareAccess], 0; ShareAccess
0x14005565b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140055660  call    cs:__imp_ZwOpenFile
0x140055667  nop     dword ptr [rax+rax+00h]
0x14005566c  mov     ebx, eax
0x14005566e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140055675  lea     rax, WPP_GLOBAL_Control
0x14005567c  cmp     rcx, rax
0x14005567f  jz      short loc_1400556B7
0x140055681  test    dword ptr [rcx+2Ch], 200h
0x140055688  jz      short loc_1400556B7
0x14005568a  cmp     byte ptr [rcx+29h], 4
0x14005568e  jb      short loc_1400556B7
0x140055690  mov     rcx, [rcx+18h]
0x140055694  lea     rax, [rbp+57h+Destination]
0x140055698  mov     [rsp+0D0h+var_98], rax
0x14005569d  mov     r9d, ebx
0x1400556a0  mov     rax, [rbp+57h+FileHandle]
0x1400556a4  mov     [rsp+0D0h+var_A0], rax
0x1400556a9  mov     qword ptr [rsp+0D0h+OpenOptions], rdi
0x1400556ae  mov     [rsp+0D0h+ShareAccess], esi
0x1400556b2  call    WPP_SF_LdqqZ
0x1400556b7  test    ebx, ebx
0x1400556b9  jns     short loc_1400556F2
0x1400556bb  mov     qword ptr [rbp+57h+Interval], 0
0x1400556c3  call    cs:__imp_KeLeaveCriticalRegion
0x1400556ca  nop     dword ptr [rax+rax+00h]
0x1400556cf  lea     r8, [rbp+57h+Interval]; Interval
0x1400556d3  mov     qword ptr [rbp+57h+Interval], 0FFFFFFFFFF676980h
0x1400556db  xor     edx, edx; Alertable
0x1400556dd  xor     ecx, ecx; WaitMode
0x1400556df  call    cs:__imp_KeDelayExecutionThread
0x1400556e6  nop     dword ptr [rax+rax+00h]
0x1400556eb  inc     esi
0x1400556ed  jmp     loc_140055604
0x1400556f2  mov     r8, cs:__imp_IoFileObjectType
0x1400556f9  lea     rax, [rbp+57h+Object]
0x1400556fd  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140055701  xor     r9d, r9d; AccessMode
0x140055704  mov     qword ptr [rsp+0D0h+OpenOptions], 0; HandleInformation
0x14005570d  xor     edx, edx; DesiredAccess
0x14005570f  mov     qword ptr [rsp+0D0h+ShareAccess], rax; Object
0x140055714  mov     r8, [r8]; ObjectType
0x140055717  call    cs:__imp_ObReferenceObjectByHandle
0x14005571e  nop     dword ptr [rax+rax+00h]
0x140055723  mov     ebx, eax
0x140055725  test    eax, eax
0x140055727  jns     short loc_14005577E
0x140055729  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140055730  lea     rax, WPP_GLOBAL_Control
0x140055737  cmp     rcx, rax
0x14005573a  jz      short loc_14005576C
0x14005573c  test    dword ptr [rcx+2Ch], 200h
0x140055743  jz      short loc_14005576C
0x140055745  cmp     byte ptr [rcx+29h], 1
0x140055749  jb      short loc_14005576C
0x14005574b  mov     rax, [rbp+57h+FileHandle]
0x14005574f  lea     r8, WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids
0x140055756  mov     rcx, [rcx+18h]
0x14005575a  mov     edx, 1Eh
0x14005575f  mov     r9d, ebx
0x140055762  mov     qword ptr [rsp+0D0h+ShareAccess], rax
0x140055767  call    WPP_SF_dq
0x14005576c  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140055770  call    cs:__imp_ZwClose
0x140055777  nop     dword ptr [rax+rax+00h]
0x14005577c  jmp     short loc_1400557B7
0x14005577e  mov     rcx, [rbp+57h+Object]; FileObject
0x140055782  call    cs:__imp_IoGetRelatedDeviceObject
0x140055789  nop     dword ptr [rax+rax+00h]
0x14005578e  mov     [rdi+68h], rax
0x140055792  mov     rax, [rbp+57h+Object]
0x140055796  mov     [rdi+70h], rax
0x14005579a  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14005579e  mov     [rdi+78h], rcx
0x1400557a2  call    RxVmbusSendTransportNegotiateMessage
0x1400557a7  mov     ebx, eax
0x1400557a9  test    eax, eax
0x1400557ab  js      short loc_1400557B7
0x1400557ad  mov     rcx, rdi
0x1400557b0  call    RxVmbusRecvTransportNegotiateMessage
0x1400557b5  mov     ebx, eax
0x1400557b7  call    cs:__imp_KeLeaveCriticalRegion
0x1400557be  nop     dword ptr [rax+rax+00h]
0x1400557c3  jmp     short loc_14005580C
0x1400557c5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400557cc  lea     rax, WPP_GLOBAL_Control
0x1400557d3  cmp     rcx, rax
0x1400557d6  jz      short loc_1400557FE
0x1400557d8  test    dword ptr [rcx+2Ch], 200h
0x1400557df  jz      short loc_14005580C
0x1400557e1  cmp     byte ptr [rcx+29h], 4
0x1400557e5  jb      short loc_14005580C
0x1400557e7  mov     rcx, [rcx+18h]
0x1400557eb  lea     r8, WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids
0x1400557f2  mov     edx, 1Dh
0x1400557f7  call    WPP_SF_
0x1400557fc  jmp     short loc_14005580C
0x1400557fe  lea     rsi, WPP_GLOBAL_Control
0x140055805  jmp     short loc_14005584A
0x140055807  mov     ebx, 0C00000BEh
0x14005580c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140055813  lea     rsi, WPP_GLOBAL_Control
0x14005581a  cmp     rcx, rsi
0x14005581d  jz      short loc_14005584A
0x14005581f  test    dword ptr [rcx+2Ch], 200h
0x140055826  jz      short loc_14005584A
0x140055828  cmp     byte ptr [rcx+29h], 4
0x14005582c  jb      short loc_14005584A
0x14005582e  mov     rcx, [rcx+18h]
0x140055832  lea     r8, WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids
0x140055839  mov     edx, 1Fh
0x14005583e  mov     [rsp+0D0h+ShareAccess], ebx
0x140055842  mov     r9, rdi
0x140055845  call    WPP_SF_qD
0x14005584a  mov     rcx, [rbp+57h+Destination.Buffer]; P
0x14005584e  test    rcx, rcx
0x140055851  jz      short loc_140055871
0x140055853  mov     edx, 63437852h; Tag
0x140055858  call    cs:__imp_ExFreePoolWithTag
0x14005585f  nop     dword ptr [rax+rax+00h]
0x140055864  xor     eax, eax
0x140055866  mov     [rbp+57h+Destination.Buffer], 0
0x14005586e  mov     dword ptr [rbp+57h+Destination.Length], eax
0x140055871  test    ebx, ebx
0x140055873  jns     short loc_140055887
0x140055875  bt      word ptr [r13+522h], 8
0x14005587f  jnb     short loc_140055887
0x140055881  int     3; Trap to Debugger
0x140055882  mov     ebx, 0C00000C4h
0x140055887  mov     [r14+10h], ebx
0x14005588b  mov     rcx, r14
0x14005588e  mov     dword ptr [r14+14h], 0
0x140055896  mov     rax, [r15+88h]
0x14005589d  call    _guard_dispatch_icall
0x1400558a2  test    ebx, ebx
0x1400558a4  js      short loc_14005590B
0x1400558a6  mov     rax, [rdi+80h]
0x1400558ad  mov     rcx, rdi; pContext
0x1400558b0  mov     dword ptr [rax+14h], 4
0x1400558b7  mov     rax, [rdi+80h]
0x1400558be  mov     dword ptr [rax+18h], 0
0x1400558c5  mov     rax, [rdi+80h]
0x1400558cc  mov     dword ptr [rax+8], 0
0x1400558d3  call    VmbusRecvAsync
0x1400558d8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400558df  cmp     rcx, rsi
0x1400558e2  jz      short loc_14005590B
0x1400558e4  test    dword ptr [rcx+2Ch], 200h
0x1400558eb  jz      short loc_14005590B
0x1400558ed  cmp     byte ptr [rcx+29h], 4
0x1400558f1  jb      short loc_14005590B
0x1400558f3  mov     rcx, [rcx+18h]
0x1400558f7  lea     r8, WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids
0x1400558fe  mov     edx, 20h ; ' '
0x140055903  mov     r9d, eax
0x140055906  call    WPP_SF_d
0x14005590b  add     rsp, 0A0h
0x140055912  pop     r15
0x140055914  pop     r14
0x140055916  pop     r13
0x140055918  pop     rdi
0x140055919  pop     rsi
0x14005591a  pop     rbx
0x14005591b  pop     rbp
0x14005591c  retn
```
