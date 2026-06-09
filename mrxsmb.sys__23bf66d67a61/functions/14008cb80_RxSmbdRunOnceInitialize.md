# RxSmbdRunOnceInitialize

- ea: `0x14008cb80`
- end: `0x14008cf37`
- name: `RxSmbdRunOnceInitialize`
- size: `951`
- prototype: `RTL_RUN_ONCE_INIT_FN`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x140010f94`
- `0x14003838c`
- `0x14004f8f4`
- `0x140053340`
- `0x140059dc0`
- `0x14008c888`
- `0x14008c990`
- `0x14008cb80`

## import_xrefs

- `ntoskrnl!ZwOpenFile` at `0x14008cda5`
- `ntoskrnl!ZwOpenFile` at `0x14008cda5`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x14008cdfd`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x14008cdfd`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008cd4f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008cd4f`
- `ntoskrnl!ZwClose` at `0x14008ce16`
- `ntoskrnl!ZwClose` at `0x14008ce16`
- `ntoskrnl!ZwLoadDriver` at `0x14008cc63`
- `ntoskrnl!ZwLoadDriver` at `0x14008cc63`

## pseudocode

```c
_BOOL8 __fastcall RxSmbdRunOnceInitialize(PRTL_RUN_ONCE a1, PVOID a2, PVOID *a3)
{
  int SMBDirectServicePath; // eax
  int v4; // r8d
  NTSTATUS v5; // ebx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  __int64 v9; // r14
  __int64 *v10; // rax
  _OWORD *v11; // rcx
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int64 v19; // rax
  UNICODE_STRING DriverServiceName; // [rsp+50h] [rbp-B0h] BYREF
  __int64 InputBuffer; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR SourceString[128]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v27[256]; // [rsp+1C0h] [rbp+C0h] BYREF

  *(_QWORD *)&DriverServiceName.Length = 0x1000000;
  DriverServiceName.Buffer = (wchar_t *)v27;
  SMBDirectServicePath = RxSmbdGetSMBDirectServicePath(&DriverServiceName);
  v5 = SMBDirectServicePath;
  if ( SMBDirectServicePath >= 0 )
  {
    v9 = 2;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_Z(
        WPP_GLOBAL_Control->AttachedDevice,
        35,
        WPP_fe1ce53ca48c31d5aa52f121b5564b01_Traceguids,
        &DriverServiceName);
    }
    v5 = ZwLoadDriver(&DriverServiceName);
    if ( (int)(v5 + 0x80000000) >= 0 && v5 != -1073741554 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_37;
      }
      v7 = 36;
      goto LABEL_17;
    }
    RxSmbdGetSMBDirectDeviceName(SourceString);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_S(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_fe1ce53ca48c31d5aa52f121b5564b01_Traceguids, SourceString);
    }
    InputBuffer = 0;
    memset(&ObjectAttributes, 0, 44);
    IoStatusBlock = 0;
    DestinationString = 0;
    if ( _InterlockedCompareExchange(&SmbdInitingOrDeiniting, 1, 0) )
    {
      v5 = -1073741436;
LABEL_31:
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_37;
      }
      v7 = 38;
LABEL_17:
      v8 = (unsigned int)v5;
      goto LABEL_6;
    }
    if ( SmbdHandle )
    {
      v5 = 0;
      goto LABEL_30;
    }
    InputBuffer = 0xA00000001LL;
    RtlInitUnicodeString(&DestinationString, SourceString);
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v5 = ZwOpenFile(&SmbdHandle, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 3u, 0x60u);
    if ( v5 >= 0 )
    {
      v5 = ZwDeviceIoControlFile(
             SmbdHandle,
             0,
             0,
             0,
             &IoStatusBlock,
             0x508008u,
             &InputBuffer,
             8u,
             &SmbdFastDispatch,
             8u);
      if ( v5 >= 0 )
        goto LABEL_30;
      ZwClose(SmbdHandle);
      SmbdFastDispatch = 0;
    }
    SmbdHandle = 0;
LABEL_30:
    _InterlockedExchange(&SmbdInitingOrDeiniting, 0);
    if ( v5 >= 0 )
    {
      v10 = RxSmbdLastLoadedSmbDirectServicePath;
      v11 = v27;
      do
      {
        v12 = v11[1];
        *(_OWORD *)v10 = *v11;
        v13 = v11[2];
        *((_OWORD *)v10 + 1) = v12;
        v14 = v11[3];
        *((_OWORD *)v10 + 2) = v13;
        v15 = v11[4];
        *((_OWORD *)v10 + 3) = v14;
        v16 = v11[5];
        *((_OWORD *)v10 + 4) = v15;
        v17 = v11[6];
        *((_OWORD *)v10 + 5) = v16;
        v18 = v11[7];
        v11 += 8;
        *((_OWORD *)v10 + 6) = v17;
        *((_OWORD *)v10 + 7) = v18;
        v10 += 16;
        --v9;
      }
      while ( v9 );
      goto LABEL_37;
    }
    goto LABEL_31;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    v7 = 34;
    v8 = (unsigned int)SMBDirectServicePath;
LABEL_6:
    WPP_SF_d(v6->AttachedDevice, v7, WPP_fe1ce53ca48c31d5aa52f121b5564b01_Traceguids, v8);
  }
LABEL_37:
  if ( (byte_1400712C3 & 8) != 0 )
  {
    v19 = -1;
    do
      ++v19;
    while ( SourceString[v19] );
    McTemplateK0tdhzr2hzr4_EtwWriteTransfer(
      DriverServiceName.Length >> 1,
      (unsigned int)SourceString,
      v4,
      v5 >= 0,
      v5,
      DriverServiceName.Length >> 1,
      (__int64)DriverServiceName.Buffer,
      v19,
      (__int64)SourceString);
  }
  return v5 >= 0;
}

```

## disassembly

```asm
0x14008cb80  push    rbp
0x14008cb82  push    rbx
0x14008cb83  push    rdi
0x14008cb84  push    r12
0x14008cb86  push    r14
0x14008cb88  push    r15
0x14008cb8a  lea     rbp, [rsp-1D8h]
0x14008cb92  sub     rsp, 2D8h
0x14008cb99  mov     rax, cs:__security_cookie
0x14008cba0  xor     rax, rsp
0x14008cba3  mov     [rbp+200h+var_40], rax
0x14008cbaa  lea     rax, [rbp+200h+var_140]
0x14008cbb1  mov     qword ptr [rsp+300h+DriverServiceName.Length], 1000000h
0x14008cbba  lea     rcx, [rsp+300h+DriverServiceName]; Destination
0x14008cbbf  mov     [rsp+300h+DriverServiceName.Buffer], rax
0x14008cbc4  xor     r15d, r15d
0x14008cbc7  call    RxSmbdGetSMBDirectServicePath
0x14008cbcc  lea     r12d, [r15+1]
0x14008cbd0  mov     ebx, eax
0x14008cbd2  test    eax, eax
0x14008cbd4  jns     short loc_14008CC1F
0x14008cbd6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008cbdd  lea     rdi, WPP_GLOBAL_Control
0x14008cbe4  cmp     rcx, rdi
0x14008cbe7  jz      loc_14008CEBD
0x14008cbed  mov     edx, [rcx+2Ch]
0x14008cbf0  test    dl, 4
0x14008cbf3  jz      loc_14008CEBD
0x14008cbf9  cmp     [rcx+29h], r12b
0x14008cbfd  jb      loc_14008CEBD
0x14008cc03  lea     edx, [r15+22h]
0x14008cc07  mov     r9d, eax
0x14008cc0a  mov     rcx, [rcx+18h]
0x14008cc0e  lea     r8, WPP_fe1ce53ca48c31d5aa52f121b5564b01_Traceguids
0x14008cc15  call    WPP_SF_d
0x14008cc1a  jmp     loc_14008CEBD
0x14008cc1f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008cc26  lea     rdi, WPP_GLOBAL_Control
0x14008cc2d  mov     r14d, 2
0x14008cc33  cmp     rcx, rdi
0x14008cc36  jz      short loc_14008CC5E
0x14008cc38  mov     eax, [rcx+2Ch]
0x14008cc3b  test    al, 4
0x14008cc3d  jz      short loc_14008CC5E
0x14008cc3f  cmp     [rcx+29h], r14b
0x14008cc43  jb      short loc_14008CC5E
0x14008cc45  mov     rcx, [rcx+18h]
0x14008cc49  lea     edx, [r14+21h]
0x14008cc4d  lea     r9, [rsp+300h+DriverServiceName]
0x14008cc52  lea     r8, WPP_fe1ce53ca48c31d5aa52f121b5564b01_Traceguids
0x14008cc59  call    WPP_SF_Z
0x14008cc5e  lea     rcx, [rsp+300h+DriverServiceName]; DriverServiceName
0x14008cc63  call    cs:__imp_ZwLoadDriver
0x14008cc6a  nop     dword ptr [rax+rax+00h]
0x14008cc6f  mov     ecx, 80000000h
0x14008cc74  mov     ebx, eax
0x14008cc76  add     eax, ecx
0x14008cc78  test    ecx, eax
0x14008cc7a  jnz     short loc_14008CCB7
0x14008cc7c  cmp     ebx, 0C000010Eh
0x14008cc82  jz      short loc_14008CCB7
0x14008cc84  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008cc8b  cmp     rcx, rdi
0x14008cc8e  jz      loc_14008CEBD
0x14008cc94  mov     eax, [rcx+2Ch]
0x14008cc97  test    r12b, al
0x14008cc9a  jz      loc_14008CEBD
0x14008cca0  cmp     [rcx+29h], r12b
0x14008cca4  jb      loc_14008CEBD
0x14008ccaa  mov     edx, 24h ; '$'
0x14008ccaf  mov     r9d, ebx
0x14008ccb2  jmp     loc_14008CC0A
0x14008ccb7  lea     rcx, [rbp+200h+SourceString]; pszDest
0x14008ccbb  call    RxSmbdGetSMBDirectDeviceName
0x14008ccc0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008ccc7  cmp     rcx, rdi
0x14008ccca  jz      short loc_14008CCF2
0x14008cccc  mov     eax, [rcx+2Ch]
0x14008cccf  test    al, 4
0x14008ccd1  jz      short loc_14008CCF2
0x14008ccd3  cmp     [rcx+29h], r14b
0x14008ccd7  jb      short loc_14008CCF2
0x14008ccd9  mov     rcx, [rcx+18h]
0x14008ccdd  lea     r9, [rbp+200h+SourceString]
0x14008cce1  mov     edx, 25h ; '%'
0x14008cce6  lea     r8, WPP_fe1ce53ca48c31d5aa52f121b5564b01_Traceguids
0x14008cced  call    WPP_SF_S
0x14008ccf2  xorps   xmm0, xmm0
0x14008ccf5  mov     [rsp+300h+var_2A0], r15
0x14008ccfa  xorps   xmm1, xmm1
0x14008ccfd  xor     eax, eax
0x14008ccff  movups  xmmword ptr [rsp+300h+ObjectAttributes.ObjectName], xmm0
0x14008cd04  movups  xmmword ptr [rbp+200h+ObjectAttributes+1Ch], xmm0
0x14008cd08  movups  xmmword ptr [rsp+300h+ObjectAttributes.Length], xmm0
0x14008cd0d  movups  xmmword ptr [rbp+200h+IoStatusBlock], xmm0
0x14008cd11  movups  xmmword ptr [rbp+200h+DestinationString.Length], xmm1
0x14008cd15  lock cmpxchg cs:SmbdInitingOrDeiniting, r12d
0x14008cd1e  jz      short loc_14008CD2A
0x14008cd20  mov     ebx, 0C0000184h
0x14008cd25  jmp     loc_14008CE3D
0x14008cd2a  cmp     cs:SmbdHandle, r15
0x14008cd31  jz      short loc_14008CD3B
0x14008cd33  mov     ebx, r15d
0x14008cd36  jmp     loc_14008CE30
0x14008cd3b  mov     rax, cs:qword_1400670C0
0x14008cd42  lea     rdx, [rbp+200h+SourceString]; SourceString
0x14008cd46  lea     rcx, [rbp+200h+DestinationString]; DestinationString
0x14008cd4a  mov     [rsp+300h+var_2A0], rax
0x14008cd4f  call    cs:__imp_RtlInitUnicodeString
0x14008cd56  nop     dword ptr [rax+rax+00h]
0x14008cd5b  lea     rax, [rbp+200h+DestinationString]
0x14008cd5f  mov     [rsp+300h+OpenOptions], 60h ; '`'; OpenOptions
0x14008cd67  xorps   xmm0, xmm0
0x14008cd6a  mov     [rsp+300h+ObjectAttributes.ObjectName], rax
0x14008cd6f  lea     r9, [rbp+200h+IoStatusBlock]; IoStatusBlock
0x14008cd73  mov     [rsp+300h+ObjectAttributes.Length], 30h ; '0'
0x14008cd7b  lea     r8, [rsp+300h+ObjectAttributes]; ObjectAttributes
0x14008cd80  mov     [rsp+300h+ObjectAttributes.RootDirectory], r15
0x14008cd85  mov     edx, 0C0100000h; DesiredAccess
0x14008cd8a  mov     [rbp+200h+ObjectAttributes.Attributes], 240h
0x14008cd91  lea     rcx, SmbdHandle; FileHandle
0x14008cd98  mov     [rsp+300h+ShareAccess], 3; ShareAccess
0x14008cda0  movdqu  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x14008cda5  call    cs:__imp_ZwOpenFile
0x14008cdac  nop     dword ptr [rax+rax+00h]
0x14008cdb1  mov     ebx, eax
0x14008cdb3  test    eax, eax
0x14008cdb5  js      short loc_14008CE29
0x14008cdb7  mov     rcx, cs:SmbdHandle; FileHandle
0x14008cdbe  lea     rax, SmbdFastDispatch
0x14008cdc5  mov     [rsp+300h+OutputBufferLength], 8; OutputBufferLength
0x14008cdcd  xor     r9d, r9d; ApcContext
0x14008cdd0  mov     [rsp+300h+OutputBuffer], rax; OutputBuffer
0x14008cdd5  xor     r8d, r8d; ApcRoutine
0x14008cdd8  mov     [rsp+300h+InputBufferLength], 8; InputBufferLength
0x14008cde0  lea     rax, [rsp+300h+var_2A0]
0x14008cde5  mov     [rsp+300h+InputBuffer], rax; InputBuffer
0x14008cdea  xor     edx, edx; Event
0x14008cdec  lea     rax, [rbp+200h+IoStatusBlock]
0x14008cdf0  mov     [rsp+300h+OpenOptions], 508008h; IoControlCode
0x14008cdf8  mov     qword ptr [rsp+300h+ShareAccess], rax; IoStatusBlock
0x14008cdfd  call    cs:__imp_ZwDeviceIoControlFile
0x14008ce04  nop     dword ptr [rax+rax+00h]
0x14008ce09  mov     ebx, eax
0x14008ce0b  test    eax, eax
0x14008ce0d  jns     short loc_14008CE30
0x14008ce0f  mov     rcx, cs:SmbdHandle; Handle
0x14008ce16  call    cs:__imp_ZwClose
0x14008ce1d  nop     dword ptr [rax+rax+00h]
0x14008ce22  mov     cs:SmbdFastDispatch, r15
0x14008ce29  mov     cs:SmbdHandle, r15
0x14008ce30  mov     eax, r15d
0x14008ce33  xchg    eax, cs:SmbdInitingOrDeiniting
0x14008ce39  test    ebx, ebx
0x14008ce3b  jns     short loc_14008CE61
0x14008ce3d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008ce44  cmp     rcx, rdi
0x14008ce47  jz      short loc_14008CEBD
0x14008ce49  mov     eax, [rcx+2Ch]
0x14008ce4c  test    r12b, al
0x14008ce4f  jz      short loc_14008CEBD
0x14008ce51  cmp     [rcx+29h], r12b
0x14008ce55  jb      short loc_14008CEBD
0x14008ce57  mov     edx, 26h ; '&'
0x14008ce5c  jmp     loc_14008CCAF
0x14008ce61  lea     rax, RxSmbdLastLoadedSmbDirectServicePath
0x14008ce68  mov     edx, 80h
0x14008ce6d  lea     rcx, [rbp+200h+var_140]
0x14008ce74  movups  xmm0, xmmword ptr [rcx]
0x14008ce77  movups  xmm1, xmmword ptr [rcx+10h]
0x14008ce7b  movups  xmmword ptr [rax], xmm0
0x14008ce7e  movups  xmm0, xmmword ptr [rcx+20h]
0x14008ce82  movups  xmmword ptr [rax+10h], xmm1
0x14008ce86  movups  xmm1, xmmword ptr [rcx+30h]
0x14008ce8a  movups  xmmword ptr [rax+20h], xmm0
0x14008ce8e  movups  xmm0, xmmword ptr [rcx+40h]
0x14008ce92  movups  xmmword ptr [rax+30h], xmm1
0x14008ce96  movups  xmm1, xmmword ptr [rcx+50h]
0x14008ce9a  movups  xmmword ptr [rax+40h], xmm0
0x14008ce9e  movups  xmm0, xmmword ptr [rcx+60h]
0x14008cea2  movups  xmmword ptr [rax+50h], xmm1
0x14008cea6  movups  xmm1, xmmword ptr [rcx+70h]
0x14008ceaa  add     rcx, rdx
0x14008cead  movups  xmmword ptr [rax+60h], xmm0
0x14008ceb1  movups  xmmword ptr [rax+70h], xmm1
0x14008ceb5  add     rax, rdx
0x14008ceb8  sub     r14, r12
0x14008cebb  jnz     short loc_14008CE74
0x14008cebd  mov     edi, ebx
0x14008cebf  shr     edi, 1Fh
0x14008cec2  test    cs:byte_1400712C3, 8
0x14008cec9  jz      short loc_14008CF11
0x14008cecb  mov     r9d, edi
0x14008cece  lea     rcx, [rbp+200h+SourceString]
0x14008ced2  xor     r9d, r12d
0x14008ced5  or      rax, 0FFFFFFFFFFFFFFFFh
0x14008ced9  inc     rax
0x14008cedc  cmp     [rcx+rax*2], r15w
0x14008cee1  jnz     short loc_14008CED9
0x14008cee3  movzx   ecx, [rsp+300h+DriverServiceName.Length]
0x14008cee8  lea     rdx, [rbp+200h+SourceString]
0x14008ceec  mov     [rsp+300h+OutputBuffer], rdx
0x14008cef1  mov     word ptr [rsp+300h+InputBufferLength], ax
0x14008cef6  mov     rax, [rsp+300h+DriverServiceName.Buffer]
0x14008cefb  mov     [rsp+300h+InputBuffer], rax
0x14008cf00  shr     cx, 1
0x14008cf03  mov     word ptr [rsp+300h+OpenOptions], cx
0x14008cf08  mov     [rsp+300h+ShareAccess], ebx
0x14008cf0c  call    McTemplateK0tdhzr2hzr4_EtwWriteTransfer
0x14008cf11  xor     edi, r12d
0x14008cf14  mov     eax, edi
0x14008cf16  mov     rcx, [rbp+200h+var_40]
0x14008cf1d  xor     rcx, rsp; StackCookie
0x14008cf20  call    __security_check_cookie
0x14008cf25  add     rsp, 2D8h
0x14008cf2c  pop     r15
0x14008cf2e  pop     r14
0x14008cf30  pop     r12
0x14008cf32  pop     rdi
0x14008cf33  pop     rbx
0x14008cf34  pop     rbp
0x14008cf35  retn
```
