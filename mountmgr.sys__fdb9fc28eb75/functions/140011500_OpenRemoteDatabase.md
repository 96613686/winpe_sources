# OpenRemoteDatabase

- ea: `0x140011500`
- end: `0x140011990`
- name: `OpenRemoteDatabase`
- size: `1168`
- prototype: `__int64 __fastcall(__int64, char, _BYTE *, void **)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000a96c`
- `0x14000e340`
- `0x14000ecbc`
- `0x1400119a0`

## callees

- `0x140001ae0`
- `0x140001b30`
- `0x140002988`
- `0x140002f80`
- `0x14000afb4`
- `0x14000ba94`
- `0x140010600`
- `0x140011500`
- `0x140012df0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14001164d`
- `ntoskrnl!KeReleaseMutex` at `0x1400118c0`
- `ntoskrnl!KeReleaseMutex` at `0x14001164d`
- `ntoskrnl!KeReleaseMutex` at `0x1400118c0`
- `ntoskrnl!ExAllocatePool2` at `0x14001159b`
- `ntoskrnl!ExAllocatePool2` at `0x14001159b`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x140011614`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x140011725`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x1400117cb`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x140011614`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x140011725`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x1400117cb`
- `ntoskrnl!IoCreateFile` at `0x1400116a2`
- `ntoskrnl!IoCreateFile` at `0x1400116a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011778`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011778`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400116f2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001192e`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400116f2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001192e`

## pseudocode

```c
__int64 __fastcall OpenRemoteDatabase(__int64 a1, char a2, _BYTE *a3, void **a4)
{
  __int16 v8; // ax
  __int64 v9; // r13
  void *Pool2; // rax
  ULONG Disposition; // ebx
  NTSTATUS v12; // eax
  __int64 v13; // r8
  int v14; // edi
  int v15; // ebx
  __int64 v16; // r8
  void *v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r8
  void *v21; // rdx
  void *FileHandle; // [rsp+78h] [rbp-90h] BYREF
  __int64 v23; // [rsp+80h] [rbp-88h]
  __int64 v24; // [rsp+88h] [rbp-80h]
  PVOID P[2]; // [rsp+90h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-58h] BYREF
  BOOLEAN v29; // [rsp+140h] [rbp+38h]

  FileHandle = 0;
  *(_OWORD *)P = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( a4 && a3 )
  {
    *a3 = 0;
    v8 = word_140007020;
    *a4 = 0;
    v9 = *(_QWORD *)(a1 + 152);
    LOWORD(P[0]) = *(_WORD *)(a1 + 80) + v8;
    WORD1(P[0]) = LOWORD(P[0]) + 2;
    Pool2 = (void *)ExAllocatePool2(258, (unsigned __int16)(LOWORD(P[0]) + 2), 1098149453);
    P[1] = Pool2;
    if ( Pool2 )
    {
      memmove(Pool2, *(const void **)(a1 + 88), *(unsigned __int16 *)(a1 + 80));
      memmove((char *)P[1] + *(unsigned __int16 *)(a1 + 80), Src, (unsigned __int16)word_140007020);
      *((_WORD *)P[1] + ((unsigned __int64)LOWORD(P[0]) >> 1)) = 0;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v29 = IoSetThreadHardErrorMode(0);
      if ( !a2 || (Disposition = 3, !*(_BYTE *)(a1 + 134)) )
        Disposition = 1;
      v24 = *(_QWORD *)(v9 + 336);
      v23 = *(_QWORD *)(a1 + 176);
      KeReleaseMutex((PRKMUTEX)(v9 + 56), 0);
      v12 = IoCreateFile(
              &FileHandle,
              0x12019Fu,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              0x86u,
              0,
              Disposition,
              0x60u,
              0,
              0,
              CreateFileTypeNone,
              0,
              0x108u);
      v14 = v12;
      if ( v12 < 0 )
      {
        if ( v12 == -2147483603 )
          DetectedSymlinkOnRemoteDatabaseFile();
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 37, v13, (unsigned int)v14);
        }
      }
      KeWaitForSingleObject((PVOID)(v9 + 56), Executive, 0, 0, 0);
      v15 = VerifyEpoch(v9, v24, v23);
      if ( v15 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 38, v16, (unsigned int)v15);
        v18 = FileHandle;
        *a3 = 1;
        if ( !v18 )
          goto LABEL_21;
LABEL_20:
        CloseFileHandleOutsideExtensionMutexLock(v9);
        FileHandle = 0;
LABEL_21:
        IoSetThreadHardErrorMode(v29);
        goto LABEL_15;
      }
      if ( a2 && v14 < 0 )
      {
        KeReleaseMutex((PRKMUTEX)(v9 + 56), 0);
        v14 = CreateRemoteDatabase(a1, &FileHandle);
        if ( v14 < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 39, v19, (unsigned int)v14);
        }
        KeWaitForSingleObject((PVOID)(v9 + 56), Executive, 0, 0, 0);
        v15 = VerifyEpoch(v9, v24, v23);
        if ( v15 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 40, v20, (unsigned int)v15);
          }
          v21 = FileHandle;
          *a3 = 1;
          if ( !v21 )
            goto LABEL_21;
          goto LABEL_20;
        }
      }
      v15 = v14;
      IoSetThreadHardErrorMode(v29);
      if ( v14 >= 0 )
        *a4 = FileHandle;
    }
    else
    {
      v15 = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36);
    }
  }
  else
  {
    v15 = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_qqL(WPP_GLOBAL_Control->AttachedDevice);
  }
LABEL_15:
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140011500  mov     rax, rsp
0x140011503  mov     [rax+10h], dl
0x140011506  push    rbp
0x140011507  push    rbx
0x140011508  lea     rbp, [rax-18h]
0x14001150c  sub     rsp, 108h
0x140011513  mov     [rax+8], rsi
0x140011517  xorps   xmm0, xmm0
0x14001151a  mov     [rax-18h], rdi
0x14001151e  movzx   ebx, dl
0x140011521  mov     [rax-20h], r12
0x140011525  xor     edi, edi
0x140011527  mov     [rax-28h], r13
0x14001152b  mov     rsi, rcx
0x14001152e  mov     [rax-30h], r14
0x140011532  mov     r14, r8
0x140011535  mov     [rax-38h], r15
0x140011539  mov     r15, r9
0x14001153c  xor     eax, eax
0x14001153e  mov     [rsp+110h+FileHandle], rdi
0x140011543  movups  xmmword ptr [rbp+10h+ObjectAttributes.ObjectName], xmm0
0x140011547  movups  xmmword ptr [rbp+10h+P], xmm0
0x14001154b  movups  xmmword ptr [rbp+10h+ObjectAttributes.Length], xmm0
0x14001154f  movups  xmmword ptr [rbp+10h+ObjectAttributes+1Ch], xmm0
0x140011553  movups  xmmword ptr [rbp+10h+IoStatusBlock], xmm0
0x140011557  test    r9, r9
0x14001155a  jz      loc_1400117DC
0x140011560  test    r8, r8
0x140011563  jz      loc_1400117DC
0x140011569  mov     [r8], al
0x14001156c  mov     r8d, 41746E4Dh
0x140011572  movzx   eax, cs:word_140007020
0x140011579  mov     [r9], rdi
0x14001157c  add     ax, [rcx+50h]
0x140011580  mov     r13, [rcx+98h]
0x140011587  mov     ecx, 102h
0x14001158c  mov     word ptr [rbp+10h+P], ax
0x140011590  add     ax, 2
0x140011594  movzx   edx, ax
0x140011597  mov     word ptr [rbp+10h+P+2], dx
0x14001159b  call    cs:__imp_ExAllocatePool2
0x1400115a2  nop     dword ptr [rax+rax+00h]
0x1400115a7  mov     [rbp+10h+P+8], rax
0x1400115ab  test    rax, rax
0x1400115ae  jz      loc_140011816
0x1400115b4  movzx   r8d, word ptr [rsi+50h]; Size
0x1400115b9  mov     rcx, rax; void *
0x1400115bc  mov     rdx, [rsi+58h]; Src
0x1400115c0  call    memmove
0x1400115c5  movzx   ecx, word ptr [rsi+50h]
0x1400115c9  add     rcx, [rbp+10h+P+8]; void *
0x1400115cd  movzx   r8d, cs:word_140007020; Size
0x1400115d5  mov     rdx, cs:Src; Src
0x1400115dc  call    memmove
0x1400115e1  movzx   edx, word ptr [rbp+10h+P]
0x1400115e5  xorps   xmm0, xmm0
0x1400115e8  mov     rax, [rbp+10h+P+8]
0x1400115ec  xor     ecx, ecx; EnableHardErrors
0x1400115ee  shr     rdx, 1
0x1400115f1  mov     [rax+rdx*2], di
0x1400115f5  lea     rax, [rbp+10h+P]
0x1400115f9  mov     [rbp+10h+ObjectAttributes.ObjectName], rax
0x1400115fd  mov     [rbp+10h+ObjectAttributes.Length], 30h ; '0'
0x140011604  mov     [rbp+10h+ObjectAttributes.RootDirectory], rdi
0x140011608  mov     [rbp+10h+ObjectAttributes.Attributes], 240h
0x14001160f  movdqu  xmmword ptr [rbp+10h+ObjectAttributes.SecurityDescriptor], xmm0
0x140011614  call    cs:__imp_IoSetThreadHardErrorMode
0x14001161b  nop     dword ptr [rax+rax+00h]
0x140011620  mov     [rbp+10h+arg_18], al
0x140011623  test    bl, bl
0x140011625  jnz     loc_140011850
0x14001162b  mov     ebx, 1
0x140011630  mov     rax, [r13+150h]
0x140011637  lea     rcx, [r13+38h]; Mutex
0x14001163b  mov     [rbp+10h+var_90], rax
0x14001163f  xor     edx, edx; Wait
0x140011641  mov     rax, [rsi+0B0h]
0x140011648  mov     [rsp+110h+var_98], rax
0x14001164d  call    cs:__imp_KeReleaseMutex
0x140011654  nop     dword ptr [rax+rax+00h]
0x140011659  mov     [rsp+110h+Options], 108h; Options
0x140011661  lea     r9, [rbp+10h+IoStatusBlock]; IoStatusBlock
0x140011665  mov     [rsp+110h+InternalParameters], rdi; InternalParameters
0x14001166a  lea     r8, [rbp+10h+ObjectAttributes]; ObjectAttributes
0x14001166e  mov     [rsp+110h+CreateFileType], edi; CreateFileType
0x140011672  lea     rcx, [rsp+110h+FileHandle]; FileHandle
0x140011677  mov     [rsp+110h+EaLength], edi; EaLength
0x14001167b  mov     edx, 12019Fh; DesiredAccess
0x140011680  mov     [rsp+110h+EaBuffer], rdi; EaBuffer
0x140011685  mov     [rsp+110h+CreateOptions], 60h ; '`'; CreateOptions
0x14001168d  mov     [rsp+110h+Disposition], ebx; Disposition
0x140011691  mov     [rsp+110h+ShareAccess], edi; ShareAccess
0x140011695  mov     [rsp+110h+FileAttributes], 86h; FileAttributes
0x14001169d  mov     [rsp+110h+AllocationSize], rdi; AllocationSize
0x1400116a2  call    cs:__imp_IoCreateFile
0x1400116a9  nop     dword ptr [rax+rax+00h]
0x1400116ae  lea     rbx, WPP_GLOBAL_Control
0x1400116b5  mov     edi, eax
0x1400116b7  test    eax, eax
0x1400116b9  jns     short loc_1400116DD
0x1400116bb  cmp     eax, 8000002Dh
0x1400116c0  jz      loc_140011867
0x1400116c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400116cd  cmp     rcx, rbx
0x1400116d0  jz      short loc_1400116DD
0x1400116d2  mov     eax, [rcx+2Ch]
0x1400116d5  test    al, 1
0x1400116d7  jnz     loc_140011871
0x1400116dd  xor     r9d, r9d; Alertable
0x1400116e0  mov     [rsp+110h+AllocationSize], 0; Timeout
0x1400116e9  xor     r8d, r8d; WaitMode
0x1400116ec  lea     rcx, [r13+38h]; Object
0x1400116f0  xor     edx, edx; WaitReason
0x1400116f2  call    cs:__imp_KeWaitForSingleObject
0x1400116f9  nop     dword ptr [rax+rax+00h]
0x1400116fe  mov     r8, [rsp+110h+var_98]
0x140011703  mov     rcx, r13
0x140011706  mov     rdx, [rbp+10h+var_90]
0x14001170a  call    VerifyEpoch
0x14001170f  mov     ebx, eax
0x140011711  test    eax, eax
0x140011713  js      short loc_140011791
0x140011715  cmp     [rbp+10h+arg_8], 0
0x140011719  jnz     loc_1400118B2
0x14001171f  movzx   ecx, [rbp+10h+arg_18]; EnableHardErrors
0x140011723  mov     ebx, edi
0x140011725  call    cs:__imp_IoSetThreadHardErrorMode
0x14001172c  nop     dword ptr [rax+rax+00h]
0x140011731  test    edi, edi
0x140011733  js      short loc_14001173D
0x140011735  mov     rax, [rsp+110h+FileHandle]
0x14001173a  mov     [r15], rax
0x14001173d  mov     rcx, [rbp+10h+P+8]; P
0x140011741  mov     r15, [rsp+110h+var_30]
0x140011749  mov     r14, [rsp+110h+var_28]
0x140011751  mov     r13, [rsp+110h+var_20]
0x140011759  mov     r12, [rsp+110h+var_18]
0x140011761  mov     rdi, [rsp+100h]
0x140011769  mov     rsi, [rsp+110h+arg_0]
0x140011771  test    rcx, rcx
0x140011774  jz      short loc_140011784
0x140011776  xor     edx, edx; Tag
0x140011778  call    cs:__imp_ExFreePoolWithTag
0x14001177f  nop     dword ptr [rax+rax+00h]
0x140011784  mov     eax, ebx
0x140011786  add     rsp, 108h
0x14001178d  pop     rbx
0x14001178e  pop     rbp
0x14001178f  retn
0x140011791  mov     rcx, cs:WPP_GLOBAL_Control
0x140011798  lea     rsi, WPP_GLOBAL_Control
0x14001179f  cmp     rcx, rsi
0x1400117a2  jnz     loc_140011891
0x1400117a8  mov     rdx, [rsp+110h+FileHandle]
0x1400117ad  mov     byte ptr [r14], 1
0x1400117b1  test    rdx, rdx
0x1400117b4  jz      short loc_1400117C7
0x1400117b6  mov     rcx, r13
0x1400117b9  call    CloseFileHandleOutsideExtensionMutexLock
0x1400117be  mov     [rsp+110h+FileHandle], 0
0x1400117c7  movzx   ecx, [rbp+10h+arg_18]; EnableHardErrors
0x1400117cb  call    cs:__imp_IoSetThreadHardErrorMode
0x1400117d2  nop     dword ptr [rax+rax+00h]
0x1400117d7  jmp     loc_14001173D
0x1400117dc  mov     ebx, 0C000000Dh
0x1400117e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400117e8  lea     rsi, WPP_GLOBAL_Control
0x1400117ef  cmp     rcx, rsi
0x1400117f2  jz      loc_14001173D
0x1400117f8  mov     eax, [rcx+2Ch]
0x1400117fb  test    al, 1
0x1400117fd  jz      loc_14001173D
0x140011803  mov     rcx, [rcx+18h]
0x140011807  mov     [rsp+110h+AllocationSize], r14
0x14001180c  call    WPP_SF_qqL
0x140011811  jmp     loc_14001173D
0x140011816  mov     ebx, 0C000009Ah
0x14001181b  mov     rcx, cs:WPP_GLOBAL_Control
0x140011822  lea     rsi, WPP_GLOBAL_Control
0x140011829  cmp     rcx, rsi
0x14001182c  jz      loc_14001173D
0x140011832  mov     eax, [rcx+2Ch]
0x140011835  test    al, 4
0x140011837  jz      loc_14001173D
0x14001183d  mov     rcx, [rcx+18h]
0x140011841  mov     edx, 24h ; '$'
0x140011846  call    WPP_SF_
0x14001184b  jmp     loc_14001173D
0x140011850  mov     ebx, 3
0x140011855  cmp     [rsi+86h], dil
0x14001185c  jnz     loc_140011630
0x140011862  jmp     loc_14001162B
0x140011867  call    DetectedSymlinkOnRemoteDatabaseFile
0x14001186c  jmp     loc_1400116C6
0x140011871  cmp     byte ptr [rcx+29h], 1
0x140011875  jb      loc_1400116DD
0x14001187b  mov     rcx, [rcx+18h]
0x14001187f  mov     edx, 25h ; '%'
0x140011884  mov     r9d, edi
0x140011887  call    WPP_SF_L
0x14001188c  jmp     loc_1400116DD
0x140011891  mov     eax, [rcx+2Ch]
0x140011894  test    al, 1
0x140011896  jz      loc_1400117A8
0x14001189c  mov     rcx, [rcx+18h]
0x1400118a0  mov     edx, 26h ; '&'
0x1400118a5  mov     r9d, ebx
0x1400118a8  call    WPP_SF_L
0x1400118ad  jmp     loc_1400117A8
0x1400118b2  test    edi, edi
0x1400118b4  jns     loc_14001171F
0x1400118ba  xor     edx, edx; Wait
0x1400118bc  lea     rcx, [r13+38h]; Mutex
0x1400118c0  call    cs:__imp_KeReleaseMutex
0x1400118c7  nop     dword ptr [rax+rax+00h]
0x1400118cc  lea     rdx, [rsp+110h+FileHandle]
0x1400118d1  mov     rcx, rsi
0x1400118d4  call    CreateRemoteDatabase
0x1400118d9  mov     edi, eax
0x1400118db  test    eax, eax
0x1400118dd  jns     short loc_140011912
0x1400118df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400118e6  lea     rsi, WPP_GLOBAL_Control
0x1400118ed  cmp     rcx, rsi
0x1400118f0  jz      short loc_140011919
0x1400118f2  mov     eax, [rcx+2Ch]
0x1400118f5  test    al, 1
0x1400118f7  jz      short loc_140011919
0x1400118f9  cmp     byte ptr [rcx+29h], 1
0x1400118fd  jb      short loc_140011919
0x1400118ff  mov     rcx, [rcx+18h]
0x140011903  mov     edx, 27h ; '''
0x140011908  mov     r9d, edi
0x14001190b  call    WPP_SF_L
0x140011910  jmp     short loc_140011919
0x140011912  lea     rsi, WPP_GLOBAL_Control
0x140011919  xor     r9d, r9d; Alertable
0x14001191c  mov     [rsp+110h+AllocationSize], 0; Timeout
0x140011925  xor     r8d, r8d; WaitMode
0x140011928  lea     rcx, [r13+38h]; Object
0x14001192c  xor     edx, edx; WaitReason
0x14001192e  call    cs:__imp_KeWaitForSingleObject
0x140011935  nop     dword ptr [rax+rax+00h]
0x14001193a  mov     r8, [rsp+110h+var_98]
0x14001193f  mov     rcx, r13
0x140011942  mov     rdx, [rbp+10h+var_90]
0x140011946  call    VerifyEpoch
0x14001194b  mov     ebx, eax
0x14001194d  test    eax, eax
0x14001194f  jns     loc_14001171F
0x140011955  mov     rcx, cs:WPP_GLOBAL_Control
0x14001195c  cmp     rcx, rsi
0x14001195f  jz      short loc_140011979
0x140011961  mov     eax, [rcx+2Ch]
0x140011964  test    al, 1
0x140011966  jz      short loc_140011979
0x140011968  mov     rcx, [rcx+18h]
0x14001196c  mov     edx, 28h ; '('
0x140011971  mov     r9d, ebx
0x140011974  call    WPP_SF_L
0x140011979  mov     rdx, [rsp+110h+FileHandle]
0x14001197e  mov     byte ptr [r14], 1
0x140011982  test    rdx, rdx
0x140011985  jz      loc_1400117C7
0x14001198b  jmp     loc_1400117B6
```
