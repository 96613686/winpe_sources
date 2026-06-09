# HsmiCldLoadSyncRootInfoByFileObject

- ea: `0x14005f86c`
- end: `0x14005fcef`
- name: `HsmiCldLoadSyncRootInfoByFileObject`
- size: `1155`
- prototype: `__int64 __fastcall(__int64, __int64, UCHAR **)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140051810`
- `0x140056848`
- `0x14007f5dc`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000c12c`
- `0x14001123c`
- `0x14001e1c0`
- `0x14005ec60`
- `0x14005f86c`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x14005fa08`
- `ntoskrnl!RtlComputeCrc32` at `0x14005fa08`
- `ntoskrnl!ObfDereferenceObject` at `0x14005faba`
- `ntoskrnl!ObfDereferenceObject` at `0x14005faba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fcde`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fcde`
- `ntoskrnl!ExAllocatePool2` at `0x14005f97b`
- `ntoskrnl!ExAllocatePool2` at `0x14005f97b`
- `FLTMGR!FltReadFile` at `0x14005f9bc`
- `FLTMGR!FltReadFile` at `0x14005f9bc`
- `FLTMGR!FltClose` at `0x14005facf`
- `FLTMGR!FltClose` at `0x14005facf`
- `FLTMGR!FltQueryInformationFile` at `0x14005f936`
- `FLTMGR!FltQueryInformationFile` at `0x14005f936`

## pseudocode

```c
__int64 __fastcall HsmiCldLoadSyncRootInfoByFileObject(__int64 a1, __int64 a2, UCHAR **a3)
{
  UCHAR *v6; // rbx
  NTSTATUS v7; // edi
  UCHAR *Pool2; // rax
  unsigned int v9; // r14d
  int i; // esi
  unsigned __int64 v11; // rdx
  __int64 v12; // r8
  unsigned __int64 v13; // r14
  __int64 v14; // r9
  unsigned int v15; // eax
  unsigned __int64 v16; // rcx
  unsigned int v17; // eax
  unsigned int v18; // eax
  PULONG BytesRead; // [rsp+30h] [rbp-49h]
  PFILE_OBJECT FileObject; // [rsp+50h] [rbp-29h] BYREF
  ULONG LengthReturned; // [rsp+58h] [rbp-21h] BYREF
  HANDLE FileHandle; // [rsp+60h] [rbp-19h] BYREF
  int v24[2]; // [rsp+68h] [rbp-11h] BYREF
  const wchar_t *v25; // [rsp+70h] [rbp-9h]
  union _LARGE_INTEGER ByteOffset; // [rsp+78h] [rbp-1h] BYREF
  __int128 FileInformation; // [rsp+80h] [rbp+7h] BYREF
  __int64 v28; // [rsp+90h] [rbp+17h]

  *(_QWORD *)v24 = 7602290;
  *a3 = 0;
  v25 = L":${3D0CE612-FDEE-43f7-8ACA-957BEC0CCBA0}.SyncRootIdentity";
  FileHandle = 0;
  v28 = 0;
  FileObject = 0;
  ByteOffset.QuadPart = 0;
  v6 = 0;
  LengthReturned = 0;
  FileInformation = 0;
  v7 = HsmpRelativeStreamOpen(a1, a2, (int)v24, 0x100000, 1u, 32, BytesRead, (__int64)&FileHandle, (__int64)&FileObject);
  HsmDbgBreakOnStatus(v7);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids, a2, v7);
    }
    if ( v7 == -1073741772 )
      v7 = 0;
    goto LABEL_29;
  }
  v7 = FltQueryInformationFile(
         *(PFLT_INSTANCE *)(a1 + 32),
         FileObject,
         &FileInformation,
         0x18u,
         FileStandardInformation,
         &LengthReturned);
  HsmDbgBreakOnStatus(v7);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids, a2, v7);
    }
    goto LABEL_29;
  }
  if ( !*((_QWORD *)&FileInformation + 1) || *((__int64 *)&FileInformation + 1) > 0x10000 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qi(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids,
        a2,
        *((_QWORD *)&FileInformation + 1));
    }
    goto LABEL_29;
  }
  Pool2 = (UCHAR *)ExAllocatePool2(256, DWORD2(FileInformation), 1767076680);
  v6 = Pool2;
  if ( !Pool2 )
  {
    v7 = -1073741670;
    HsmDbgBreakOnStatus(-1073741670);
    goto LABEL_29;
  }
  v7 = FltReadFile(*(PFLT_INSTANCE *)(a1 + 32), FileObject, &ByteOffset, DWORD2(FileInformation), Pool2, 0, 0, 0, 0);
  HsmDbgBreakOnStatus(v7);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqd(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids,
        a2,
        *((_QWORD *)&FileInformation + 1),
        v7);
    }
    goto LABEL_29;
  }
  v9 = DWORD2(FileInformation);
  if ( DWORD2(FileInformation) < 0x18 )
  {
    i = 0;
    goto LABEL_60;
  }
  if ( *(_DWORD *)v6 != 1850307155 )
  {
    i = 1;
    goto LABEL_60;
  }
  if ( (v6[12] & 2) != 0 )
  {
    i = 2;
    if ( *((_DWORD *)v6 + 1) != RtlComputeCrc32(0, v6 + 8, DWORD2(FileInformation) - 8) )
    {
LABEL_60:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqd(
          WPP_GLOBAL_Control->AttachedDevice,
          19,
          WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids,
          a2,
          *((_QWORD *)&FileInformation + 1),
          i);
      }
      goto LABEL_29;
    }
  }
  v11 = *((unsigned int *)v6 + 2);
  if ( v9 < (unsigned int)v11 )
  {
    i = 3;
    goto LABEL_60;
  }
  v12 = *((unsigned __int16 *)v6 + 7);
  if ( !(_WORD)v12 )
  {
    i = 4;
    goto LABEL_60;
  }
  v13 = 8 * v12 + 16;
  if ( v13 >= v11 )
  {
    i = 5;
    goto LABEL_60;
  }
  v14 = 0;
  for ( i = 0x10000; ; ++i )
  {
    v15 = 9;
    if ( (unsigned __int16)v12 < 9u )
      v15 = *((unsigned __int16 *)v6 + 7);
    if ( (unsigned int)v14 >= v15 )
      break;
    if ( *(_WORD *)&v6[8 * v14 + 16] >= 0x12u )
      goto LABEL_60;
    v16 = *(unsigned int *)&v6[8 * v14 + 20];
    if ( (_DWORD)v16 )
    {
      if ( v16 < v13 )
        goto LABEL_60;
    }
    if ( (unsigned int)v16 > (unsigned int)v11 )
      goto LABEL_60;
    v17 = *(unsigned __int16 *)&v6[8 * v14 + 18];
    if ( v17 > (unsigned int)v11 )
      goto LABEL_60;
    v18 = v16 + v17;
    if ( v18 > (unsigned int)v11 || v18 < (unsigned int)v16 )
      goto LABEL_60;
    v14 = (unsigned int)(v14 + 1);
  }
  *a3 = v6;
  v6 = 0;
LABEL_29:
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( v6 )
    ExFreePoolWithTag(v6, 0x69537348u);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14005f86c  push    rbp
0x14005f86e  push    rbx
0x14005f86f  push    rsi
0x14005f870  push    rdi
0x14005f871  push    r13
0x14005f873  push    r14
0x14005f875  push    r15
0x14005f877  lea     rbp, [rsp-27h]
0x14005f87c  sub     rsp, 0A0h
0x14005f883  mov     rax, cs:__security_cookie
0x14005f88a  xor     rax, rsp
0x14005f88d  mov     [rbp+57h+var_38], rax
0x14005f891  xor     r14d, r14d
0x14005f894  mov     qword ptr [rbp+57h+var_68], 740072h
0x14005f89c  lea     rax, a3d0ce612Fdee43_2; ":${3D0CE612-FDEE-43f7-8ACA-957BEC0CCBA0"...
0x14005f8a3  mov     [r8], r14
0x14005f8a6  mov     [rbp+57h+var_60], rax
0x14005f8aa  mov     r13, r8
0x14005f8ad  xor     eax, eax
0x14005f8af  mov     [rbp+57h+FileHandle], r14
0x14005f8b3  mov     [rbp+57h+var_40], rax
0x14005f8b7  lea     r8, [rbp+57h+var_68]; int
0x14005f8bb  lea     rax, [rbp+57h+FileObject]
0x14005f8bf  mov     [rbp+57h+FileObject], r14
0x14005f8c3  mov     [rsp+0D0h+CallbackContext], rax; __int64
0x14005f8c8  xorps   xmm0, xmm0
0x14005f8cb  lea     rax, [rbp+57h+FileHandle]
0x14005f8cf  mov     qword ptr [rbp+57h+ByteOffset], r14
0x14005f8d3  mov     [rsp+0D0h+CallbackRoutine], rax; __int64
0x14005f8d8  mov     r9d, 100000h; int
0x14005f8de  mov     dword ptr [rsp+0D0h+LengthReturned], 20h ; ' '; int
0x14005f8e6  mov     r15, rdx
0x14005f8e9  mov     [rsp+0D0h+FileInformationClass], 1; ULONG
0x14005f8f1  mov     rsi, rcx
0x14005f8f4  mov     ebx, r14d
0x14005f8f7  mov     [rbp+57h+var_78], r14d
0x14005f8fb  movups  [rbp+57h+FileInformation], xmm0
0x14005f8ff  call    HsmpRelativeStreamOpen
0x14005f904  mov     ecx, eax
0x14005f906  mov     edi, eax
0x14005f908  call    HsmDbgBreakOnStatus
0x14005f90d  test    edi, edi
0x14005f90f  js      loc_14005FB5A
0x14005f915  mov     rdx, [rbp+57h+FileObject]; FileObject
0x14005f919  lea     rax, [rbp+57h+var_78]
0x14005f91d  mov     rcx, [rsi+20h]; Instance
0x14005f921  lea     r9d, [r14+18h]; Length
0x14005f925  mov     [rsp+0D0h+LengthReturned], rax; LengthReturned
0x14005f92a  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x14005f92e  mov     [rsp+0D0h+FileInformationClass], 5; FileInformationClass
0x14005f936  call    cs:__imp_FltQueryInformationFile
0x14005f93d  nop     dword ptr [rax+rax+00h]
0x14005f942  mov     ecx, eax
0x14005f944  mov     edi, eax
0x14005f946  call    HsmDbgBreakOnStatus
0x14005f94b  test    edi, edi
0x14005f94d  js      loc_14005FBAC
0x14005f953  mov     r8, qword ptr [rbp+57h+FileInformation+8]
0x14005f957  test    r8, r8
0x14005f95a  jz      loc_14005FB05
0x14005f960  cmp     r8, 10000h
0x14005f967  jg      loc_14005FB05
0x14005f96d  mov     edx, r8d
0x14005f970  mov     ecx, 100h
0x14005f975  mov     r8d, 69537348h
0x14005f97b  call    cs:__imp_ExAllocatePool2
0x14005f982  nop     dword ptr [rax+rax+00h]
0x14005f987  mov     rbx, rax
0x14005f98a  test    rax, rax
0x14005f98d  jz      loc_14005FB49
0x14005f993  mov     r9d, dword ptr [rbp+57h+FileInformation+8]; Length
0x14005f997  lea     r8, [rbp+57h+ByteOffset]; ByteOffset
0x14005f99b  mov     rdx, [rbp+57h+FileObject]; FileObject
0x14005f99f  mov     rcx, [rsi+20h]; InitiatingInstance
0x14005f9a3  mov     [rsp+0D0h+CallbackContext], r14; CallbackContext
0x14005f9a8  mov     [rsp+0D0h+CallbackRoutine], r14; CallbackRoutine
0x14005f9ad  mov     [rsp+0D0h+BytesRead], r14; BytesRead
0x14005f9b2  mov     dword ptr [rsp+0D0h+LengthReturned], r14d; Flags
0x14005f9b7  mov     qword ptr [rsp+0D0h+FileInformationClass], rax; Buffer
0x14005f9bc  call    cs:__imp_FltReadFile
0x14005f9c3  nop     dword ptr [rax+rax+00h]
0x14005f9c8  mov     ecx, eax
0x14005f9ca  mov     edi, eax
0x14005f9cc  call    HsmDbgBreakOnStatus
0x14005f9d1  test    edi, edi
0x14005f9d3  js      loc_14005FBFB
0x14005f9d9  mov     r14d, dword ptr [rbp+57h+FileInformation+8]
0x14005f9dd  cmp     r14d, 18h
0x14005f9e1  jb      loc_14005FC78
0x14005f9e7  cmp     dword ptr [rbx], 6E497253h
0x14005f9ed  jnz     loc_14005FC6E
0x14005f9f3  test    byte ptr [rbx+0Ch], 2
0x14005f9f7  jz      short loc_14005FA19
0x14005f9f9  lea     r8d, [r14-8]; Length
0x14005f9fd  xor     ecx, ecx; InitialCrc
0x14005f9ff  lea     rdx, [rbx+8]; Buffer
0x14005fa03  mov     esi, 2
0x14005fa08  call    cs:__imp_RtlComputeCrc32
0x14005fa0f  nop     dword ptr [rax+rax+00h]
0x14005fa14  cmp     [rbx+4], eax
0x14005fa17  jnz     short loc_14005FA8C
0x14005fa19  mov     edx, [rbx+8]
0x14005fa1c  cmp     r14d, edx
0x14005fa1f  jb      loc_14005FC64
0x14005fa25  movzx   r8d, word ptr [rbx+0Eh]
0x14005fa2a  xor     r14d, r14d
0x14005fa2d  test    r8w, r8w
0x14005fa31  jz      loc_14005FC5D
0x14005fa37  lea     r14, ds:10h[r8*8]
0x14005fa3f  cmp     r14, rdx
0x14005fa42  jnb     loc_14005FC53
0x14005fa48  xor     r9d, r9d
0x14005fa4b  mov     esi, 10000h
0x14005fa50  lea     r11d, [r9+12h]
0x14005fa54  mov     eax, 9
0x14005fa59  cmp     r8w, ax
0x14005fa5d  jnb     short loc_14005FA62
0x14005fa5f  mov     eax, r8d
0x14005fa62  cmp     r9d, eax
0x14005fa65  jnb     short loc_14005FAA6
0x14005fa67  cmp     [rbx+r9*8+10h], r11w
0x14005fa6d  jnb     short loc_14005FA8C
0x14005fa6f  mov     ecx, [rbx+r9*8+14h]
0x14005fa74  test    ecx, ecx
0x14005fa76  jnz     short loc_14005FA94
0x14005fa78  cmp     ecx, edx
0x14005fa7a  ja      short loc_14005FA8C
0x14005fa7c  movzx   eax, word ptr [rbx+r9*8+12h]
0x14005fa82  cmp     eax, edx
0x14005fa84  ja      short loc_14005FA8C
0x14005fa86  add     eax, ecx
0x14005fa88  cmp     eax, edx
0x14005fa8a  jbe     short loc_14005FA9B
0x14005fa8c  xor     r14d, r14d
0x14005fa8f  jmp     loc_14005FC7E
0x14005fa94  cmp     rcx, r14
0x14005fa97  jnb     short loc_14005FA78
0x14005fa99  jmp     short loc_14005FA8C
0x14005fa9b  cmp     eax, ecx
0x14005fa9d  jb      short loc_14005FA8C
0x14005fa9f  inc     esi
0x14005faa1  inc     r9d
0x14005faa4  jmp     short loc_14005FA54
0x14005faa6  xor     r14d, r14d
0x14005faa9  mov     [r13+0], rbx
0x14005faad  mov     ebx, r14d
0x14005fab0  cmp     [rbp+57h+FileObject], r14
0x14005fab4  jz      short loc_14005FAC6
0x14005fab6  mov     rcx, [rbp+57h+FileObject]; Object
0x14005faba  call    cs:__imp_ObfDereferenceObject
0x14005fac1  nop     dword ptr [rax+rax+00h]
0x14005fac6  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14005faca  test    rcx, rcx
0x14005facd  jz      short loc_14005FADB
0x14005facf  call    cs:__imp_FltClose
0x14005fad6  nop     dword ptr [rax+rax+00h]
0x14005fadb  test    rbx, rbx
0x14005fade  jnz     loc_14005FCD6
0x14005fae4  mov     eax, edi
0x14005fae6  mov     rcx, [rbp+57h+var_38]
0x14005faea  xor     rcx, rsp; StackCookie
0x14005faed  call    __security_check_cookie
0x14005faf2  add     rsp, 0A0h
0x14005faf9  pop     r15
0x14005fafb  pop     r14
0x14005fafd  pop     r13
0x14005faff  pop     rdi
0x14005fb00  pop     rsi
0x14005fb01  pop     rbx
0x14005fb02  pop     rbp
0x14005fb03  retn
0x14005fb05  mov     r10, cs:WPP_GLOBAL_Control
0x14005fb0c  lea     rcx, WPP_GLOBAL_Control
0x14005fb13  cmp     r10, rcx
0x14005fb16  jz      short loc_14005FAB0
0x14005fb18  mov     eax, [r10+2Ch]
0x14005fb1c  test    al, 1
0x14005fb1e  jz      short loc_14005FAB0
0x14005fb20  cmp     byte ptr [r10+29h], 2
0x14005fb25  jb      short loc_14005FAB0
0x14005fb27  mov     rcx, [r10+18h]
0x14005fb2b  mov     edx, 11h
0x14005fb30  mov     qword ptr [rsp+0D0h+FileInformationClass], r8
0x14005fb35  mov     r9, r15
0x14005fb38  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x14005fb3f  call    WPP_SF_qi
0x14005fb44  jmp     loc_14005FAB0
0x14005fb49  mov     edi, 0C000009Ah
0x14005fb4e  mov     ecx, edi
0x14005fb50  call    HsmDbgBreakOnStatus
0x14005fb55  jmp     loc_14005FAB0
0x14005fb5a  mov     r10, cs:WPP_GLOBAL_Control
0x14005fb61  lea     rcx, WPP_GLOBAL_Control
0x14005fb68  cmp     r10, rcx
0x14005fb6b  jz      short loc_14005FB98
0x14005fb6d  mov     eax, [r10+2Ch]
0x14005fb71  test    al, 1
0x14005fb73  jz      short loc_14005FB98
0x14005fb75  cmp     byte ptr [r10+29h], 2
0x14005fb7a  jb      short loc_14005FB98
0x14005fb7c  mov     rcx, [r10+18h]
0x14005fb80  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x14005fb87  mov     edx, 0Fh
0x14005fb8c  mov     [rsp+0D0h+FileInformationClass], edi
0x14005fb90  mov     r9, r15
0x14005fb93  call    WPP_SF_qd
0x14005fb98  cmp     edi, 0C0000034h
0x14005fb9e  jnz     loc_14005FAB0
0x14005fba4  mov     edi, r14d
0x14005fba7  jmp     loc_14005FAB0
0x14005fbac  mov     r10, cs:WPP_GLOBAL_Control
0x14005fbb3  lea     rcx, WPP_GLOBAL_Control
0x14005fbba  cmp     r10, rcx
0x14005fbbd  jz      loc_14005FAB0
0x14005fbc3  mov     eax, [r10+2Ch]
0x14005fbc7  test    al, 1
0x14005fbc9  jz      loc_14005FAB0
0x14005fbcf  cmp     byte ptr [r10+29h], 2
0x14005fbd4  jb      loc_14005FAB0
0x14005fbda  mov     rcx, [r10+18h]
0x14005fbde  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x14005fbe5  mov     edx, 10h
0x14005fbea  mov     [rsp+0D0h+FileInformationClass], edi
0x14005fbee  mov     r9, r15
0x14005fbf1  call    WPP_SF_qd
0x14005fbf6  jmp     loc_14005FAB0
0x14005fbfb  mov     r10, cs:WPP_GLOBAL_Control
0x14005fc02  lea     rcx, WPP_GLOBAL_Control
0x14005fc09  cmp     r10, rcx
0x14005fc0c  jz      loc_14005FAB0
0x14005fc12  mov     eax, [r10+2Ch]
0x14005fc16  test    al, 1
0x14005fc18  jz      loc_14005FAB0
0x14005fc1e  cmp     byte ptr [r10+29h], 2
0x14005fc23  jb      loc_14005FAB0
0x14005fc29  mov     rax, qword ptr [rbp+57h+FileInformation+8]
0x14005fc2d  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x14005fc34  mov     rcx, [r10+18h]
0x14005fc38  mov     edx, 12h
0x14005fc3d  mov     dword ptr [rsp+0D0h+LengthReturned], edi
0x14005fc41  mov     r9, r15
0x14005fc44  mov     qword ptr [rsp+0D0h+FileInformationClass], rax
0x14005fc49  call    WPP_SF_qqd
0x14005fc4e  jmp     loc_14005FAB0
0x14005fc53  mov     esi, 5
0x14005fc58  jmp     loc_14005FA8C
0x14005fc5d  mov     esi, 4
0x14005fc62  jmp     short loc_14005FC7E
0x14005fc64  mov     esi, 3
0x14005fc69  jmp     loc_14005FA8C
0x14005fc6e  mov     esi, 1
0x14005fc73  jmp     loc_14005FA8C
0x14005fc78  xor     r14d, r14d
0x14005fc7b  mov     esi, r14d
0x14005fc7e  mov     r10, cs:WPP_GLOBAL_Control
0x14005fc85  lea     rcx, WPP_GLOBAL_Control
0x14005fc8c  cmp     r10, rcx
0x14005fc8f  jz      loc_14005FAB0
0x14005fc95  mov     eax, [r10+2Ch]
0x14005fc99  test    al, 1
0x14005fc9b  jz      loc_14005FAB0
0x14005fca1  cmp     byte ptr [r10+29h], 2
0x14005fca6  jb      loc_14005FAB0
0x14005fcac  mov     rax, qword ptr [rbp+57h+FileInformation+8]
0x14005fcb0  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x14005fcb7  mov     rcx, [r10+18h]
0x14005fcbb  mov     edx, 13h
0x14005fcc0  mov     dword ptr [rsp+0D0h+LengthReturned], esi
0x14005fcc4  mov     r9, r15
0x14005fcc7  mov     qword ptr [rsp+0D0h+FileInformationClass], rax
0x14005fccc  call    WPP_SF_qqd
0x14005fcd1  jmp     loc_14005FAB0
0x14005fcd6  mov     edx, 69537348h; Tag
0x14005fcdb  mov     rcx, rbx; P
0x14005fcde  call    cs:__imp_ExFreePoolWithTag
0x14005fce5  nop     dword ptr [rax+rax+00h]
0x14005fcea  jmp     loc_14005FAE4
```
