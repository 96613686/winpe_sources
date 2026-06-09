# HsmiCldLoadSyncRootInfoByFileObject

- ea: `0x14005f74c`
- end: `0x14005fbcf`
- name: `HsmiCldLoadSyncRootInfoByFileObject`
- size: `1155`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400516f0`
- `0x140056728`
- `0x14007f444`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000c12c`
- `0x1400111bc`
- `0x14001e140`
- `0x14005eb40`
- `0x14005f74c`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x14005f8e8`
- `ntoskrnl!RtlComputeCrc32` at `0x14005f8e8`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f99a`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f99a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fbbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005fbbe`
- `ntoskrnl!ExAllocatePool2` at `0x14005f85b`
- `ntoskrnl!ExAllocatePool2` at `0x14005f85b`
- `FLTMGR!FltReadFile` at `0x14005f89c`
- `FLTMGR!FltReadFile` at `0x14005f89c`
- `FLTMGR!FltClose` at `0x14005f9af`
- `FLTMGR!FltClose` at `0x14005f9af`
- `FLTMGR!FltQueryInformationFile` at `0x14005f816`
- `FLTMGR!FltQueryInformationFile` at `0x14005f816`

## pseudocode

```c
__int64 __fastcall HsmiCldLoadSyncRootInfoByFileObject(__int64 a1, struct _FILE_OBJECT *a2, _QWORD *a3)
{
  unsigned __int16 *v6; // rbx
  __int64 v7; // rdi
  unsigned __int16 *Pool2; // rax
  unsigned int v9; // r14d
  unsigned __int64 v10; // rdx
  __int64 v11; // r8
  unsigned __int64 v12; // r14
  __int64 v13; // r9
  int i; // esi
  unsigned int v15; // eax
  unsigned __int64 v16; // rcx
  unsigned int v17; // eax
  unsigned int v18; // eax
  FILE_INFORMATION_CLASS FileInformationClass[2]; // [rsp+20h] [rbp-59h]
  FILE_INFORMATION_CLASS FileInformationClassa[2]; // [rsp+20h] [rbp-59h]
  PULONG BytesRead; // [rsp+30h] [rbp-49h]
  PFILE_OBJECT FileObject; // [rsp+50h] [rbp-29h] BYREF
  ULONG LengthReturned; // [rsp+58h] [rbp-21h] BYREF
  HANDLE FileHandle; // [rsp+60h] [rbp-19h] BYREF
  struct _UNICODE_STRING v26; // [rsp+68h] [rbp-11h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+78h] [rbp-1h] BYREF
  __int128 FileInformation; // [rsp+80h] [rbp+7h] BYREF
  __int64 v29; // [rsp+90h] [rbp+17h]

  *(_QWORD *)&v26.Length = 7602290;
  *a3 = 0;
  v26.Buffer = L":${3D0CE612-FDEE-43f7-8ACA-957BEC0CCBA0}.SyncRootIdentity";
  FileHandle = 0;
  v29 = 0;
  FileObject = 0;
  ByteOffset.QuadPart = 0;
  v6 = 0;
  LengthReturned = 0;
  FileInformation = 0;
  LODWORD(v7) = HsmpRelativeStreamOpen(a1, a2, &v26, 0x100000u, 1u, 32, BytesRead, &FileHandle, &FileObject);
  HsmDbgBreakOnStatus((unsigned int)v7);
  if ( (int)v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      FileInformationClass[0] = v7;
      WPP_SF_qd(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids,
        a2,
        *(_QWORD *)FileInformationClass);
    }
    if ( (_DWORD)v7 == -1073741772 )
      LODWORD(v7) = 0;
  }
  else
  {
    v7 = (unsigned int)FltQueryInformationFile(
                         *(PFLT_INSTANCE *)(a1 + 32),
                         FileObject,
                         &FileInformation,
                         0x18u,
                         FileStandardInformation,
                         &LengthReturned);
    HsmDbgBreakOnStatus(v7);
    if ( (int)v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        FileInformationClassa[0] = v7;
        WPP_SF_qd(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids,
          a2,
          *(_QWORD *)FileInformationClassa);
      }
    }
    else if ( *((_QWORD *)&FileInformation + 1) && *((__int64 *)&FileInformation + 1) <= 0x10000 )
    {
      Pool2 = (unsigned __int16 *)ExAllocatePool2(256, DWORD2(FileInformation), 1767076680);
      v6 = Pool2;
      if ( Pool2 )
      {
        LODWORD(v7) = FltReadFile(
                        *(PFLT_INSTANCE *)(a1 + 32),
                        FileObject,
                        &ByteOffset,
                        DWORD2(FileInformation),
                        Pool2,
                        0,
                        0,
                        0,
                        0);
        HsmDbgBreakOnStatus((unsigned int)v7);
        if ( (int)v7 < 0 )
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
              *((_QWORD *)&FileInformation + 1));
          }
        }
        else
        {
          v9 = DWORD2(FileInformation);
          if ( DWORD2(FileInformation) >= 0x18
            && *(_DWORD *)v6 == 1850307155
            && ((v6[6] & 2) == 0
             || *((_DWORD *)v6 + 1) == RtlComputeCrc32(0, (PUCHAR)v6 + 8, DWORD2(FileInformation) - 8))
            && (v10 = *((unsigned int *)v6 + 2), v9 >= (unsigned int)v10)
            && (v11 = v6[7], (_WORD)v11)
            && (v12 = 8 * v11 + 16, v12 < v10) )
          {
            v13 = 0;
            for ( i = 0x10000; ; ++i )
            {
              v15 = 9;
              if ( (unsigned __int16)v11 < 9u )
                v15 = v6[7];
              if ( (unsigned int)v13 >= v15 )
                break;
              if ( v6[4 * v13 + 8] >= 0x12u )
                goto LABEL_55;
              v16 = *(unsigned int *)&v6[4 * v13 + 10];
              if ( (_DWORD)v16 )
              {
                if ( v16 < v12 )
                  goto LABEL_55;
              }
              if ( (unsigned int)v16 > (unsigned int)v10 )
                goto LABEL_55;
              v17 = v6[4 * v13 + 9];
              if ( v17 > (unsigned int)v10 )
                goto LABEL_55;
              v18 = v16 + v17;
              if ( v18 > (unsigned int)v10 || v18 < (unsigned int)v16 )
                goto LABEL_55;
              v13 = (unsigned int)(v13 + 1);
            }
            *a3 = v6;
            v6 = 0;
          }
          else
          {
LABEL_55:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_qqd(
                WPP_GLOBAL_Control->AttachedDevice,
                19,
                WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids,
                a2,
                *((_QWORD *)&FileInformation + 1));
            }
          }
        }
      }
      else
      {
        LODWORD(v7) = -1073741670;
        HsmDbgBreakOnStatus(3221225626LL);
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
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
  }
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
0x14005f74c  push    rbp
0x14005f74e  push    rbx
0x14005f74f  push    rsi
0x14005f750  push    rdi
0x14005f751  push    r13
0x14005f753  push    r14
0x14005f755  push    r15
0x14005f757  lea     rbp, [rsp-27h]
0x14005f75c  sub     rsp, 0A0h
0x14005f763  mov     rax, cs:__security_cookie
0x14005f76a  xor     rax, rsp
0x14005f76d  mov     [rbp+57h+var_38], rax
0x14005f771  xor     r14d, r14d
0x14005f774  mov     qword ptr [rbp+57h+var_68], 740072h
0x14005f77c  lea     rax, a3d0ce612Fdee43_2; ":${3D0CE612-FDEE-43f7-8ACA-957BEC0CCBA0"...
0x14005f783  mov     [r8], r14
0x14005f786  mov     [rbp+57h+var_60], rax
0x14005f78a  mov     r13, r8
0x14005f78d  xor     eax, eax
0x14005f78f  mov     [rbp+57h+FileHandle], r14
0x14005f793  mov     [rbp+57h+var_40], rax
0x14005f797  lea     r8, [rbp+57h+var_68]; int
0x14005f79b  lea     rax, [rbp+57h+FileObject]
0x14005f79f  mov     [rbp+57h+FileObject], r14
0x14005f7a3  mov     [rsp+0D0h+CallbackContext], rax; __int64
0x14005f7a8  xorps   xmm0, xmm0
0x14005f7ab  lea     rax, [rbp+57h+FileHandle]
0x14005f7af  mov     qword ptr [rbp+57h+ByteOffset], r14
0x14005f7b3  mov     [rsp+0D0h+CallbackRoutine], rax; __int64
0x14005f7b8  mov     r9d, 100000h; int
0x14005f7be  mov     dword ptr [rsp+0D0h+LengthReturned], 20h ; ' '; int
0x14005f7c6  mov     r15, rdx
0x14005f7c9  mov     [rsp+0D0h+FileInformationClass], 1; ULONG
0x14005f7d1  mov     rsi, rcx
0x14005f7d4  mov     ebx, r14d
0x14005f7d7  mov     [rbp+57h+var_78], r14d
0x14005f7db  movups  [rbp+57h+FileInformation], xmm0
0x14005f7df  call    HsmpRelativeStreamOpen
0x14005f7e4  mov     ecx, eax
0x14005f7e6  mov     edi, eax
0x14005f7e8  call    HsmDbgBreakOnStatus
0x14005f7ed  test    edi, edi
0x14005f7ef  js      loc_14005FA3A
0x14005f7f5  mov     rdx, [rbp+57h+FileObject]; FileObject
0x14005f7f9  lea     rax, [rbp+57h+var_78]
0x14005f7fd  mov     rcx, [rsi+20h]; Instance
0x14005f801  lea     r9d, [r14+18h]; Length
0x14005f805  mov     [rsp+0D0h+LengthReturned], rax; LengthReturned
0x14005f80a  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x14005f80e  mov     [rsp+0D0h+FileInformationClass], 5; FileInformationClass
0x14005f816  call    cs:__imp_FltQueryInformationFile
0x14005f81d  nop     dword ptr [rax+rax+00h]
0x14005f822  mov     ecx, eax
0x14005f824  mov     edi, eax
0x14005f826  call    HsmDbgBreakOnStatus
0x14005f82b  test    edi, edi
0x14005f82d  js      loc_14005FA8C
0x14005f833  mov     r8, qword ptr [rbp+57h+FileInformation+8]
0x14005f837  test    r8, r8
0x14005f83a  jz      loc_14005F9E5
0x14005f840  cmp     r8, 10000h
0x14005f847  jg      loc_14005F9E5
0x14005f84d  mov     edx, r8d
0x14005f850  mov     ecx, 100h
0x14005f855  mov     r8d, 69537348h
0x14005f85b  call    cs:__imp_ExAllocatePool2
0x14005f862  nop     dword ptr [rax+rax+00h]
0x14005f867  mov     rbx, rax
0x14005f86a  test    rax, rax
0x14005f86d  jz      loc_14005FA29
0x14005f873  mov     r9d, dword ptr [rbp+57h+FileInformation+8]; Length
0x14005f877  lea     r8, [rbp+57h+ByteOffset]; ByteOffset
0x14005f87b  mov     rdx, [rbp+57h+FileObject]; FileObject
0x14005f87f  mov     rcx, [rsi+20h]; InitiatingInstance
0x14005f883  mov     [rsp+0D0h+CallbackContext], r14; CallbackContext
0x14005f888  mov     [rsp+0D0h+CallbackRoutine], r14; CallbackRoutine
0x14005f88d  mov     [rsp+0D0h+BytesRead], r14; BytesRead
0x14005f892  mov     dword ptr [rsp+0D0h+LengthReturned], r14d; Flags
0x14005f897  mov     qword ptr [rsp+0D0h+FileInformationClass], rax; Buffer
0x14005f89c  call    cs:__imp_FltReadFile
0x14005f8a3  nop     dword ptr [rax+rax+00h]
0x14005f8a8  mov     ecx, eax
0x14005f8aa  mov     edi, eax
0x14005f8ac  call    HsmDbgBreakOnStatus
0x14005f8b1  test    edi, edi
0x14005f8b3  js      loc_14005FADB
0x14005f8b9  mov     r14d, dword ptr [rbp+57h+FileInformation+8]
0x14005f8bd  cmp     r14d, 18h
0x14005f8c1  jb      loc_14005FB58
0x14005f8c7  cmp     dword ptr [rbx], 6E497253h
0x14005f8cd  jnz     loc_14005FB4E
0x14005f8d3  test    byte ptr [rbx+0Ch], 2
0x14005f8d7  jz      short loc_14005F8F9
0x14005f8d9  lea     r8d, [r14-8]; Length
0x14005f8dd  xor     ecx, ecx; InitialCrc
0x14005f8df  lea     rdx, [rbx+8]; Buffer
0x14005f8e3  mov     esi, 2
0x14005f8e8  call    cs:__imp_RtlComputeCrc32
0x14005f8ef  nop     dword ptr [rax+rax+00h]
0x14005f8f4  cmp     [rbx+4], eax
0x14005f8f7  jnz     short loc_14005F96C
0x14005f8f9  mov     edx, [rbx+8]
0x14005f8fc  cmp     r14d, edx
0x14005f8ff  jb      loc_14005FB44
0x14005f905  movzx   r8d, word ptr [rbx+0Eh]
0x14005f90a  xor     r14d, r14d
0x14005f90d  test    r8w, r8w
0x14005f911  jz      loc_14005FB3D
0x14005f917  lea     r14, ds:10h[r8*8]
0x14005f91f  cmp     r14, rdx
0x14005f922  jnb     loc_14005FB33
0x14005f928  xor     r9d, r9d
0x14005f92b  mov     esi, 10000h
0x14005f930  lea     r11d, [r9+12h]
0x14005f934  mov     eax, 9
0x14005f939  cmp     r8w, ax
0x14005f93d  jnb     short loc_14005F942
0x14005f93f  mov     eax, r8d
0x14005f942  cmp     r9d, eax
0x14005f945  jnb     short loc_14005F986
0x14005f947  cmp     [rbx+r9*8+10h], r11w
0x14005f94d  jnb     short loc_14005F96C
0x14005f94f  mov     ecx, [rbx+r9*8+14h]
0x14005f954  test    ecx, ecx
0x14005f956  jnz     short loc_14005F974
0x14005f958  cmp     ecx, edx
0x14005f95a  ja      short loc_14005F96C
0x14005f95c  movzx   eax, word ptr [rbx+r9*8+12h]
0x14005f962  cmp     eax, edx
0x14005f964  ja      short loc_14005F96C
0x14005f966  add     eax, ecx
0x14005f968  cmp     eax, edx
0x14005f96a  jbe     short loc_14005F97B
0x14005f96c  xor     r14d, r14d
0x14005f96f  jmp     loc_14005FB5E
0x14005f974  cmp     rcx, r14
0x14005f977  jnb     short loc_14005F958
0x14005f979  jmp     short loc_14005F96C
0x14005f97b  cmp     eax, ecx
0x14005f97d  jb      short loc_14005F96C
0x14005f97f  inc     esi
0x14005f981  inc     r9d
0x14005f984  jmp     short loc_14005F934
0x14005f986  xor     r14d, r14d
0x14005f989  mov     [r13+0], rbx
0x14005f98d  mov     ebx, r14d
0x14005f990  cmp     [rbp+57h+FileObject], r14
0x14005f994  jz      short loc_14005F9A6
0x14005f996  mov     rcx, [rbp+57h+FileObject]; Object
0x14005f99a  call    cs:__imp_ObfDereferenceObject
0x14005f9a1  nop     dword ptr [rax+rax+00h]
0x14005f9a6  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14005f9aa  test    rcx, rcx
0x14005f9ad  jz      short loc_14005F9BB
0x14005f9af  call    cs:__imp_FltClose
0x14005f9b6  nop     dword ptr [rax+rax+00h]
0x14005f9bb  test    rbx, rbx
0x14005f9be  jnz     loc_14005FBB6
0x14005f9c4  mov     eax, edi
0x14005f9c6  mov     rcx, [rbp+57h+var_38]
0x14005f9ca  xor     rcx, rsp; StackCookie
0x14005f9cd  call    __security_check_cookie
0x14005f9d2  add     rsp, 0A0h
0x14005f9d9  pop     r15
0x14005f9db  pop     r14
0x14005f9dd  pop     r13
0x14005f9df  pop     rdi
0x14005f9e0  pop     rsi
0x14005f9e1  pop     rbx
0x14005f9e2  pop     rbp
0x14005f9e3  retn
0x14005f9e5  mov     r10, cs:WPP_GLOBAL_Control
0x14005f9ec  lea     rcx, WPP_GLOBAL_Control
0x14005f9f3  cmp     r10, rcx
0x14005f9f6  jz      short loc_14005F990
0x14005f9f8  mov     eax, [r10+2Ch]
0x14005f9fc  test    al, 1
0x14005f9fe  jz      short loc_14005F990
0x14005fa00  cmp     byte ptr [r10+29h], 2
0x14005fa05  jb      short loc_14005F990
0x14005fa07  mov     rcx, [r10+18h]
0x14005fa0b  mov     edx, 11h
0x14005fa10  mov     qword ptr [rsp+0D0h+FileInformationClass], r8
0x14005fa15  mov     r9, r15
0x14005fa18  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x14005fa1f  call    WPP_SF_qi
0x14005fa24  jmp     loc_14005F990
0x14005fa29  mov     edi, 0C000009Ah
0x14005fa2e  mov     ecx, edi
0x14005fa30  call    HsmDbgBreakOnStatus
0x14005fa35  jmp     loc_14005F990
0x14005fa3a  mov     r10, cs:WPP_GLOBAL_Control
0x14005fa41  lea     rcx, WPP_GLOBAL_Control
0x14005fa48  cmp     r10, rcx
0x14005fa4b  jz      short loc_14005FA78
0x14005fa4d  mov     eax, [r10+2Ch]
0x14005fa51  test    al, 1
0x14005fa53  jz      short loc_14005FA78
0x14005fa55  cmp     byte ptr [r10+29h], 2
0x14005fa5a  jb      short loc_14005FA78
0x14005fa5c  mov     rcx, [r10+18h]
0x14005fa60  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x14005fa67  mov     edx, 0Fh
0x14005fa6c  mov     [rsp+0D0h+FileInformationClass], edi
0x14005fa70  mov     r9, r15
0x14005fa73  call    WPP_SF_qd
0x14005fa78  cmp     edi, 0C0000034h
0x14005fa7e  jnz     loc_14005F990
0x14005fa84  mov     edi, r14d
0x14005fa87  jmp     loc_14005F990
0x14005fa8c  mov     r10, cs:WPP_GLOBAL_Control
0x14005fa93  lea     rcx, WPP_GLOBAL_Control
0x14005fa9a  cmp     r10, rcx
0x14005fa9d  jz      loc_14005F990
0x14005faa3  mov     eax, [r10+2Ch]
0x14005faa7  test    al, 1
0x14005faa9  jz      loc_14005F990
0x14005faaf  cmp     byte ptr [r10+29h], 2
0x14005fab4  jb      loc_14005F990
0x14005faba  mov     rcx, [r10+18h]
0x14005fabe  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x14005fac5  mov     edx, 10h
0x14005faca  mov     [rsp+0D0h+FileInformationClass], edi
0x14005face  mov     r9, r15
0x14005fad1  call    WPP_SF_qd
0x14005fad6  jmp     loc_14005F990
0x14005fadb  mov     r10, cs:WPP_GLOBAL_Control
0x14005fae2  lea     rcx, WPP_GLOBAL_Control
0x14005fae9  cmp     r10, rcx
0x14005faec  jz      loc_14005F990
0x14005faf2  mov     eax, [r10+2Ch]
0x14005faf6  test    al, 1
0x14005faf8  jz      loc_14005F990
0x14005fafe  cmp     byte ptr [r10+29h], 2
0x14005fb03  jb      loc_14005F990
0x14005fb09  mov     rax, qword ptr [rbp+57h+FileInformation+8]
0x14005fb0d  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x14005fb14  mov     rcx, [r10+18h]
0x14005fb18  mov     edx, 12h
0x14005fb1d  mov     dword ptr [rsp+0D0h+LengthReturned], edi
0x14005fb21  mov     r9, r15
0x14005fb24  mov     qword ptr [rsp+0D0h+FileInformationClass], rax
0x14005fb29  call    WPP_SF_qqd
0x14005fb2e  jmp     loc_14005F990
0x14005fb33  mov     esi, 5
0x14005fb38  jmp     loc_14005F96C
0x14005fb3d  mov     esi, 4
0x14005fb42  jmp     short loc_14005FB5E
0x14005fb44  mov     esi, 3
0x14005fb49  jmp     loc_14005F96C
0x14005fb4e  mov     esi, 1
0x14005fb53  jmp     loc_14005F96C
0x14005fb58  xor     r14d, r14d
0x14005fb5b  mov     esi, r14d
0x14005fb5e  mov     r10, cs:WPP_GLOBAL_Control
0x14005fb65  lea     rcx, WPP_GLOBAL_Control
0x14005fb6c  cmp     r10, rcx
0x14005fb6f  jz      loc_14005F990
0x14005fb75  mov     eax, [r10+2Ch]
0x14005fb79  test    al, 1
0x14005fb7b  jz      loc_14005F990
0x14005fb81  cmp     byte ptr [r10+29h], 2
0x14005fb86  jb      loc_14005F990
0x14005fb8c  mov     rax, qword ptr [rbp+57h+FileInformation+8]
0x14005fb90  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x14005fb97  mov     rcx, [r10+18h]
0x14005fb9b  mov     edx, 13h
0x14005fba0  mov     dword ptr [rsp+0D0h+LengthReturned], esi
0x14005fba4  mov     r9, r15
0x14005fba7  mov     qword ptr [rsp+0D0h+FileInformationClass], rax
0x14005fbac  call    WPP_SF_qqd
0x14005fbb1  jmp     loc_14005F990
0x14005fbb6  mov     edx, 69537348h; Tag
0x14005fbbb  mov     rcx, rbx; P
0x14005fbbe  call    cs:__imp_ExFreePoolWithTag
0x14005fbc5  nop     dword ptr [rax+rax+00h]
0x14005fbca  jmp     loc_14005F9C4
```
