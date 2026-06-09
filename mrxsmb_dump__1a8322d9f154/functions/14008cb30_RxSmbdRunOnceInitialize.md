# RxSmbdRunOnceInitialize

- ea: `0x14008cb30`
- end: `0x14008cee7`
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
- `0x14008c838`
- `0x14008c940`
- `0x14008cb30`

## import_xrefs

- `ntoskrnl!ZwOpenFile` at `0x14008cd55`
- `ntoskrnl!ZwOpenFile` at `0x14008cd55`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x14008cdad`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x14008cdad`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008ccff`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008ccff`
- `ntoskrnl!ZwClose` at `0x14008cdc6`
- `ntoskrnl!ZwClose` at `0x14008cdc6`
- `ntoskrnl!ZwLoadDriver` at `0x14008cc13`
- `ntoskrnl!ZwLoadDriver` at `0x14008cc13`

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
  if ( (byte_1400712A3 & 8) != 0 )
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
0x14008cb30  push    rbp
0x14008cb32  push    rbx
0x14008cb33  push    rdi
0x14008cb34  push    r12
0x14008cb36  push    r14
0x14008cb38  push    r15
0x14008cb3a  lea     rbp, [rsp-1D8h]
0x14008cb42  sub     rsp, 2D8h
0x14008cb49  mov     rax, cs:__security_cookie
0x14008cb50  xor     rax, rsp
0x14008cb53  mov     [rbp+200h+var_40], rax
0x14008cb5a  lea     rax, [rbp+200h+var_140]
0x14008cb61  mov     qword ptr [rsp+300h+DriverServiceName.Length], 1000000h
0x14008cb6a  lea     rcx, [rsp+300h+DriverServiceName]; Destination
0x14008cb6f  mov     [rsp+300h+DriverServiceName.Buffer], rax
0x14008cb74  xor     r15d, r15d
0x14008cb77  call    RxSmbdGetSMBDirectServicePath
0x14008cb7c  lea     r12d, [r15+1]
0x14008cb80  mov     ebx, eax
0x14008cb82  test    eax, eax
0x14008cb84  jns     short loc_14008CBCF
0x14008cb86  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008cb8d  lea     rdi, WPP_GLOBAL_Control
0x14008cb94  cmp     rcx, rdi
0x14008cb97  jz      loc_14008CE6D
0x14008cb9d  mov     edx, [rcx+2Ch]
0x14008cba0  test    dl, 4
0x14008cba3  jz      loc_14008CE6D
0x14008cba9  cmp     [rcx+29h], r12b
0x14008cbad  jb      loc_14008CE6D
0x14008cbb3  lea     edx, [r15+22h]
0x14008cbb7  mov     r9d, eax
0x14008cbba  mov     rcx, [rcx+18h]
0x14008cbbe  lea     r8, WPP_fe1ce53ca48c31d5aa52f121b5564b01_Traceguids
0x14008cbc5  call    WPP_SF_d
0x14008cbca  jmp     loc_14008CE6D
0x14008cbcf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008cbd6  lea     rdi, WPP_GLOBAL_Control
0x14008cbdd  mov     r14d, 2
0x14008cbe3  cmp     rcx, rdi
0x14008cbe6  jz      short loc_14008CC0E
0x14008cbe8  mov     eax, [rcx+2Ch]
0x14008cbeb  test    al, 4
0x14008cbed  jz      short loc_14008CC0E
0x14008cbef  cmp     [rcx+29h], r14b
0x14008cbf3  jb      short loc_14008CC0E
0x14008cbf5  mov     rcx, [rcx+18h]
0x14008cbf9  lea     edx, [r14+21h]
0x14008cbfd  lea     r9, [rsp+300h+DriverServiceName]
0x14008cc02  lea     r8, WPP_fe1ce53ca48c31d5aa52f121b5564b01_Traceguids
0x14008cc09  call    WPP_SF_Z
0x14008cc0e  lea     rcx, [rsp+300h+DriverServiceName]; DriverServiceName
0x14008cc13  call    cs:__imp_ZwLoadDriver
0x14008cc1a  nop     dword ptr [rax+rax+00h]
0x14008cc1f  mov     ecx, 80000000h
0x14008cc24  mov     ebx, eax
0x14008cc26  add     eax, ecx
0x14008cc28  test    ecx, eax
0x14008cc2a  jnz     short loc_14008CC67
0x14008cc2c  cmp     ebx, 0C000010Eh
0x14008cc32  jz      short loc_14008CC67
0x14008cc34  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008cc3b  cmp     rcx, rdi
0x14008cc3e  jz      loc_14008CE6D
0x14008cc44  mov     eax, [rcx+2Ch]
0x14008cc47  test    r12b, al
0x14008cc4a  jz      loc_14008CE6D
0x14008cc50  cmp     [rcx+29h], r12b
0x14008cc54  jb      loc_14008CE6D
0x14008cc5a  mov     edx, 24h ; '$'
0x14008cc5f  mov     r9d, ebx
0x14008cc62  jmp     loc_14008CBBA
0x14008cc67  lea     rcx, [rbp+200h+SourceString]; pszDest
0x14008cc6b  call    RxSmbdGetSMBDirectDeviceName
0x14008cc70  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008cc77  cmp     rcx, rdi
0x14008cc7a  jz      short loc_14008CCA2
0x14008cc7c  mov     eax, [rcx+2Ch]
0x14008cc7f  test    al, 4
0x14008cc81  jz      short loc_14008CCA2
0x14008cc83  cmp     [rcx+29h], r14b
0x14008cc87  jb      short loc_14008CCA2
0x14008cc89  mov     rcx, [rcx+18h]
0x14008cc8d  lea     r9, [rbp+200h+SourceString]
0x14008cc91  mov     edx, 25h ; '%'
0x14008cc96  lea     r8, WPP_fe1ce53ca48c31d5aa52f121b5564b01_Traceguids
0x14008cc9d  call    WPP_SF_S
0x14008cca2  xorps   xmm0, xmm0
0x14008cca5  mov     [rsp+300h+var_2A0], r15
0x14008ccaa  xorps   xmm1, xmm1
0x14008ccad  xor     eax, eax
0x14008ccaf  movups  xmmword ptr [rsp+300h+ObjectAttributes.ObjectName], xmm0
0x14008ccb4  movups  xmmword ptr [rbp+200h+ObjectAttributes+1Ch], xmm0
0x14008ccb8  movups  xmmword ptr [rsp+300h+ObjectAttributes.Length], xmm0
0x14008ccbd  movups  xmmword ptr [rbp+200h+IoStatusBlock], xmm0
0x14008ccc1  movups  xmmword ptr [rbp+200h+DestinationString.Length], xmm1
0x14008ccc5  lock cmpxchg cs:SmbdInitingOrDeiniting, r12d
0x14008ccce  jz      short loc_14008CCDA
0x14008ccd0  mov     ebx, 0C0000184h
0x14008ccd5  jmp     loc_14008CDED
0x14008ccda  cmp     cs:SmbdHandle, r15
0x14008cce1  jz      short loc_14008CCEB
0x14008cce3  mov     ebx, r15d
0x14008cce6  jmp     loc_14008CDE0
0x14008cceb  mov     rax, cs:qword_1400670A8
0x14008ccf2  lea     rdx, [rbp+200h+SourceString]; SourceString
0x14008ccf6  lea     rcx, [rbp+200h+DestinationString]; DestinationString
0x14008ccfa  mov     [rsp+300h+var_2A0], rax
0x14008ccff  call    cs:__imp_RtlInitUnicodeString
0x14008cd06  nop     dword ptr [rax+rax+00h]
0x14008cd0b  lea     rax, [rbp+200h+DestinationString]
0x14008cd0f  mov     [rsp+300h+OpenOptions], 60h ; '`'; OpenOptions
0x14008cd17  xorps   xmm0, xmm0
0x14008cd1a  mov     [rsp+300h+ObjectAttributes.ObjectName], rax
0x14008cd1f  lea     r9, [rbp+200h+IoStatusBlock]; IoStatusBlock
0x14008cd23  mov     [rsp+300h+ObjectAttributes.Length], 30h ; '0'
0x14008cd2b  lea     r8, [rsp+300h+ObjectAttributes]; ObjectAttributes
0x14008cd30  mov     [rsp+300h+ObjectAttributes.RootDirectory], r15
0x14008cd35  mov     edx, 0C0100000h; DesiredAccess
0x14008cd3a  mov     [rbp+200h+ObjectAttributes.Attributes], 240h
0x14008cd41  lea     rcx, SmbdHandle; FileHandle
0x14008cd48  mov     [rsp+300h+ShareAccess], 3; ShareAccess
0x14008cd50  movdqu  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x14008cd55  call    cs:__imp_ZwOpenFile
0x14008cd5c  nop     dword ptr [rax+rax+00h]
0x14008cd61  mov     ebx, eax
0x14008cd63  test    eax, eax
0x14008cd65  js      short loc_14008CDD9
0x14008cd67  mov     rcx, cs:SmbdHandle; FileHandle
0x14008cd6e  lea     rax, SmbdFastDispatch
0x14008cd75  mov     [rsp+300h+OutputBufferLength], 8; OutputBufferLength
0x14008cd7d  xor     r9d, r9d; ApcContext
0x14008cd80  mov     [rsp+300h+OutputBuffer], rax; OutputBuffer
0x14008cd85  xor     r8d, r8d; ApcRoutine
0x14008cd88  mov     [rsp+300h+InputBufferLength], 8; InputBufferLength
0x14008cd90  lea     rax, [rsp+300h+var_2A0]
0x14008cd95  mov     [rsp+300h+InputBuffer], rax; InputBuffer
0x14008cd9a  xor     edx, edx; Event
0x14008cd9c  lea     rax, [rbp+200h+IoStatusBlock]
0x14008cda0  mov     [rsp+300h+OpenOptions], 508008h; IoControlCode
0x14008cda8  mov     qword ptr [rsp+300h+ShareAccess], rax; IoStatusBlock
0x14008cdad  call    cs:__imp_ZwDeviceIoControlFile
0x14008cdb4  nop     dword ptr [rax+rax+00h]
0x14008cdb9  mov     ebx, eax
0x14008cdbb  test    eax, eax
0x14008cdbd  jns     short loc_14008CDE0
0x14008cdbf  mov     rcx, cs:SmbdHandle; Handle
0x14008cdc6  call    cs:__imp_ZwClose
0x14008cdcd  nop     dword ptr [rax+rax+00h]
0x14008cdd2  mov     cs:SmbdFastDispatch, r15
0x14008cdd9  mov     cs:SmbdHandle, r15
0x14008cde0  mov     eax, r15d
0x14008cde3  xchg    eax, cs:SmbdInitingOrDeiniting
0x14008cde9  test    ebx, ebx
0x14008cdeb  jns     short loc_14008CE11
0x14008cded  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008cdf4  cmp     rcx, rdi
0x14008cdf7  jz      short loc_14008CE6D
0x14008cdf9  mov     eax, [rcx+2Ch]
0x14008cdfc  test    r12b, al
0x14008cdff  jz      short loc_14008CE6D
0x14008ce01  cmp     [rcx+29h], r12b
0x14008ce05  jb      short loc_14008CE6D
0x14008ce07  mov     edx, 26h ; '&'
0x14008ce0c  jmp     loc_14008CC5F
0x14008ce11  lea     rax, RxSmbdLastLoadedSmbDirectServicePath
0x14008ce18  mov     edx, 80h
0x14008ce1d  lea     rcx, [rbp+200h+var_140]
0x14008ce24  movups  xmm0, xmmword ptr [rcx]
0x14008ce27  movups  xmm1, xmmword ptr [rcx+10h]
0x14008ce2b  movups  xmmword ptr [rax], xmm0
0x14008ce2e  movups  xmm0, xmmword ptr [rcx+20h]
0x14008ce32  movups  xmmword ptr [rax+10h], xmm1
0x14008ce36  movups  xmm1, xmmword ptr [rcx+30h]
0x14008ce3a  movups  xmmword ptr [rax+20h], xmm0
0x14008ce3e  movups  xmm0, xmmword ptr [rcx+40h]
0x14008ce42  movups  xmmword ptr [rax+30h], xmm1
0x14008ce46  movups  xmm1, xmmword ptr [rcx+50h]
0x14008ce4a  movups  xmmword ptr [rax+40h], xmm0
0x14008ce4e  movups  xmm0, xmmword ptr [rcx+60h]
0x14008ce52  movups  xmmword ptr [rax+50h], xmm1
0x14008ce56  movups  xmm1, xmmword ptr [rcx+70h]
0x14008ce5a  add     rcx, rdx
0x14008ce5d  movups  xmmword ptr [rax+60h], xmm0
0x14008ce61  movups  xmmword ptr [rax+70h], xmm1
0x14008ce65  add     rax, rdx
0x14008ce68  sub     r14, r12
0x14008ce6b  jnz     short loc_14008CE24
0x14008ce6d  mov     edi, ebx
0x14008ce6f  shr     edi, 1Fh
0x14008ce72  test    cs:byte_1400712A3, 8
0x14008ce79  jz      short loc_14008CEC1
0x14008ce7b  mov     r9d, edi
0x14008ce7e  lea     rcx, [rbp+200h+SourceString]
0x14008ce82  xor     r9d, r12d
0x14008ce85  or      rax, 0FFFFFFFFFFFFFFFFh
0x14008ce89  inc     rax
0x14008ce8c  cmp     [rcx+rax*2], r15w
0x14008ce91  jnz     short loc_14008CE89
0x14008ce93  movzx   ecx, [rsp+300h+DriverServiceName.Length]
0x14008ce98  lea     rdx, [rbp+200h+SourceString]
0x14008ce9c  mov     [rsp+300h+OutputBuffer], rdx
0x14008cea1  mov     word ptr [rsp+300h+InputBufferLength], ax
0x14008cea6  mov     rax, [rsp+300h+DriverServiceName.Buffer]
0x14008ceab  mov     [rsp+300h+InputBuffer], rax
0x14008ceb0  shr     cx, 1
0x14008ceb3  mov     word ptr [rsp+300h+OpenOptions], cx
0x14008ceb8  mov     [rsp+300h+ShareAccess], ebx
0x14008cebc  call    McTemplateK0tdhzr2hzr4_EtwWriteTransfer
0x14008cec1  xor     edi, r12d
0x14008cec4  mov     eax, edi
0x14008cec6  mov     rcx, [rbp+200h+var_40]
0x14008cecd  xor     rcx, rsp; StackCookie
0x14008ced0  call    __security_check_cookie
0x14008ced5  add     rsp, 2D8h
0x14008cedc  pop     r15
0x14008cede  pop     r14
0x14008cee0  pop     r12
0x14008cee2  pop     rdi
0x14008cee3  pop     rbx
0x14008cee4  pop     rbp
0x14008cee5  retn
```
