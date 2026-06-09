# MRxSmbQueryLbfoTeamCapability

- ea: `0x14002bb00`
- end: `0x14002be57`
- name: `MRxSmbQueryLbfoTeamCapability`
- size: `855`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14008ec40`

## callees

- `0x14002bb00`
- `0x140059dc0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002bbc6`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002bbe4`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002bbc6`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002bbe4`
- `ntoskrnl!RtlStringFromGUID` at `0x14002bba6`
- `ntoskrnl!RtlStringFromGUID` at `0x14002bba6`
- `ntoskrnl!ZwOpenFile` at `0x14002bc3d`
- `ntoskrnl!ZwOpenFile` at `0x14002bc3d`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x14002bcf0`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x14002bda5`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x14002bcf0`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x14002bda5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14002be2e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14002be2e`
- `ntoskrnl!ExAllocatePool2` at `0x14002bc75`
- `ntoskrnl!ExAllocatePool2` at `0x14002bd34`
- `ntoskrnl!ExAllocatePool2` at `0x14002bc75`
- `ntoskrnl!ExAllocatePool2` at `0x14002bd34`
- `ntoskrnl!ZwClose` at `0x14002bc8e`
- `ntoskrnl!ZwClose` at `0x14002bd4d`
- `ntoskrnl!ZwClose` at `0x14002bdec`
- `ntoskrnl!ZwClose` at `0x14002bc8e`
- `ntoskrnl!ZwClose` at `0x14002bd4d`
- `ntoskrnl!ZwClose` at `0x14002bdec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bd1b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002be05`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bd1b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002be05`
- `NETIO!ConvertInterfaceIndexToLuid` at `0x14002bb6c`
- `NETIO!ConvertInterfaceIndexToLuid` at `0x14002bb6c`
- `NETIO!ConvertInterfaceLuidToGuid` at `0x14002bb89`
- `NETIO!ConvertInterfaceLuidToGuid` at `0x14002bb89`

## pseudocode

```c
__int64 __fastcall MRxSmbQueryLbfoTeamCapability(NET_IFINDEX a1)
{
  unsigned __int8 v1; // di
  _DWORD *InputBuffer; // rax
  _DWORD *v3; // rbx
  unsigned int v4; // eax
  ULONG InputBufferLength; // esi
  _DWORD *OutputBuffer; // rax
  int v7; // ecx
  _DWORD *v8; // rax
  unsigned int v9; // edx
  void *FileHandle; // [rsp+50h] [rbp-B0h] BYREF
  UNICODE_STRING Destination; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING GuidString; // [rsp+68h] [rbp-98h] BYREF
  NET_LUID InterfaceLuid; // [rsp+78h] [rbp-88h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  GUID InterfaceGuid; // [rsp+C0h] [rbp-40h] BYREF
  char v18; // [rsp+D0h] [rbp-30h] BYREF

  *(_QWORD *)&Destination.Length = 6029312;
  FileHandle = 0;
  InterfaceLuid.Value = 0;
  Destination.Buffer = (wchar_t *)&v18;
  v1 = 0;
  *(_QWORD *)&GuidString.Length = 0;
  memset(&ObjectAttributes, 0, 44);
  GuidString.Buffer = 0;
  IoStatusBlock = 0;
  InterfaceGuid = 0;
  if ( ConvertInterfaceIndexToLuid(a1, &InterfaceLuid) >= 0
    && ConvertInterfaceLuidToGuid(&InterfaceLuid, &InterfaceGuid) >= 0
    && RtlStringFromGUID(&InterfaceGuid, &GuidString) >= 0
    && RtlAppendUnicodeStringToString(&Destination, &DeviceString) >= 0
    && RtlAppendUnicodeStringToString(&Destination, &GuidString) >= 0 )
  {
    ObjectAttributes.ObjectName = &Destination;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwOpenFile(&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u) >= 0 )
    {
      InputBuffer = (_DWORD *)ExAllocatePool2(256, 44, 1834184788);
      v3 = InputBuffer;
      if ( !InputBuffer )
      {
LABEL_8:
        ZwClose(FileHandle);
        goto LABEL_20;
      }
      *(_QWORD *)InputBuffer = 2884025;
      InputBuffer[2] = 0;
      InputBuffer[3] = 65793;
      *((_WORD *)InputBuffer + 20) = 44;
      if ( !ZwDeviceIoControlFile(
              FileHandle,
              0,
              0,
              0,
              &IoStatusBlock,
              0x17009Cu,
              InputBuffer,
              0x2Cu,
              InputBuffer,
              0x2Cu) )
      {
        v4 = v3[8];
        if ( v4 > 0x2C )
        {
          InputBufferLength = v4 + 44;
          ExFreePoolWithTag(v3, 0x6D537054u);
          OutputBuffer = (_DWORD *)ExAllocatePool2(256, InputBufferLength, 1834184788);
          v3 = OutputBuffer;
          if ( !OutputBuffer )
            goto LABEL_8;
          *(_QWORD *)OutputBuffer = 2884025;
          OutputBuffer[2] = 0;
          OutputBuffer[3] = 65793;
          *((_WORD *)OutputBuffer + 20) = 44;
          if ( !ZwDeviceIoControlFile(
                  FileHandle,
                  0,
                  0,
                  0,
                  &IoStatusBlock,
                  0x17009Cu,
                  OutputBuffer,
                  InputBufferLength,
                  OutputBuffer,
                  InputBufferLength) )
          {
            v7 = 0;
            v8 = (_DWORD *)((char *)v3 + *((unsigned __int16 *)v3 + 20));
            v9 = v3[6] >> 2;
            if ( v9 )
            {
              while ( *v8 != -100597503 )
              {
                ++v8;
                if ( ++v7 >= v9 )
                  goto LABEL_18;
              }
              v1 = 1;
            }
          }
        }
      }
LABEL_18:
      ZwClose(FileHandle);
      if ( v3 )
        ExFreePoolWithTag(v3, 0x6D537054u);
    }
  }
LABEL_20:
  RtlFreeUnicodeString(&GuidString);
  return v1;
}

```

## disassembly

```asm
0x14002bb00  push    rbp
0x14002bb02  push    rdi
0x14002bb03  push    r14
0x14002bb05  lea     rbp, [rsp-40h]
0x14002bb0a  sub     rsp, 140h
0x14002bb11  mov     rax, cs:__security_cookie
0x14002bb18  xor     rax, rsp
0x14002bb1b  mov     [rbp+50h+var_20], rax
0x14002bb1f  xorps   xmm0, xmm0
0x14002bb22  mov     qword ptr [rsp+150h+Destination.Length], 5C0000h
0x14002bb2b  xor     r14d, r14d
0x14002bb2e  lea     rdx, [rsp+150h+InterfaceLuid]; InterfaceLuid
0x14002bb33  xor     eax, eax
0x14002bb35  mov     [rsp+150h+FileHandle], r14
0x14002bb3a  lea     rax, [rbp+50h+var_80]
0x14002bb3e  mov     qword ptr [rsp+150h+InterfaceLuid], r14
0x14002bb43  xorps   xmm1, xmm1
0x14002bb46  mov     [rsp+150h+Destination.Buffer], rax
0x14002bb4b  movups  xmmword ptr [rbp+50h+ObjectAttributes.ObjectName], xmm0
0x14002bb4f  xor     dil, dil
0x14002bb52  mov     qword ptr [rsp+150h+GuidString.Length], r14
0x14002bb57  movups  xmmword ptr [rbp+50h+ObjectAttributes.Length], xmm0
0x14002bb5b  mov     [rsp+150h+GuidString.Buffer], r14
0x14002bb60  movups  xmmword ptr [rbp+50h+ObjectAttributes+1Ch], xmm0
0x14002bb64  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x14002bb68  movups  xmmword ptr [rbp+50h+InterfaceGuid.Data1], xmm1
0x14002bb6c  call    cs:__imp_ConvertInterfaceIndexToLuid
0x14002bb73  nop     dword ptr [rax+rax+00h]
0x14002bb78  test    eax, eax
0x14002bb7a  js      loc_14002BE29
0x14002bb80  lea     rdx, [rbp+50h+InterfaceGuid]; InterfaceGuid
0x14002bb84  lea     rcx, [rsp+150h+InterfaceLuid]; InterfaceLuid
0x14002bb89  call    cs:__imp_ConvertInterfaceLuidToGuid
0x14002bb90  nop     dword ptr [rax+rax+00h]
0x14002bb95  test    eax, eax
0x14002bb97  js      loc_14002BE29
0x14002bb9d  lea     rdx, [rsp+150h+GuidString]; GuidString
0x14002bba2  lea     rcx, [rbp+50h+InterfaceGuid]; Guid
0x14002bba6  call    cs:__imp_RtlStringFromGUID
0x14002bbad  nop     dword ptr [rax+rax+00h]
0x14002bbb2  test    eax, eax
0x14002bbb4  js      loc_14002BE29
0x14002bbba  lea     rdx, DeviceString; Source
0x14002bbc1  lea     rcx, [rsp+150h+Destination]; Destination
0x14002bbc6  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002bbcd  nop     dword ptr [rax+rax+00h]
0x14002bbd2  test    eax, eax
0x14002bbd4  js      loc_14002BE29
0x14002bbda  lea     rdx, [rsp+150h+GuidString]; Source
0x14002bbdf  lea     rcx, [rsp+150h+Destination]; Destination
0x14002bbe4  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002bbeb  nop     dword ptr [rax+rax+00h]
0x14002bbf0  test    eax, eax
0x14002bbf2  js      loc_14002BE29
0x14002bbf8  lea     rax, [rsp+150h+Destination]
0x14002bbfd  mov     [rsp+150h+OpenOptions], 20h ; ' '; OpenOptions
0x14002bc05  xorps   xmm0, xmm0
0x14002bc08  mov     [rbp+50h+ObjectAttributes.ObjectName], rax
0x14002bc0c  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x14002bc10  mov     [rbp+50h+ObjectAttributes.Length], 30h ; '0'
0x14002bc17  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x14002bc1b  mov     [rbp+50h+ObjectAttributes.RootDirectory], r14
0x14002bc1f  mov     edx, 12019Fh; DesiredAccess
0x14002bc24  mov     [rbp+50h+ObjectAttributes.Attributes], 240h
0x14002bc2b  lea     rcx, [rsp+150h+FileHandle]; FileHandle
0x14002bc30  mov     [rsp+150h+ShareAccess], 7; ShareAccess
0x14002bc38  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002bc3d  call    cs:__imp_ZwOpenFile
0x14002bc44  nop     dword ptr [rax+rax+00h]
0x14002bc49  test    eax, eax
0x14002bc4b  js      loc_14002BE29
0x14002bc51  mov     [rsp+150h+arg_8], rbx
0x14002bc59  mov     r8d, 6D537054h
0x14002bc5f  mov     [rsp+150h+arg_18], r15
0x14002bc67  mov     ecx, 100h
0x14002bc6c  mov     r15d, 2Ch ; ','
0x14002bc72  mov     edx, r15d
0x14002bc75  call    cs:__imp_ExAllocatePool2
0x14002bc7c  nop     dword ptr [rax+rax+00h]
0x14002bc81  mov     rbx, rax
0x14002bc84  test    rax, rax
0x14002bc87  jnz     short loc_14002BC9F
0x14002bc89  mov     rcx, [rsp+150h+FileHandle]; Handle
0x14002bc8e  call    cs:__imp_ZwClose
0x14002bc95  nop     dword ptr [rax+rax+00h]
0x14002bc9a  jmp     loc_14002BE19
0x14002bc9f  mov     [rsp+150h+OutputBufferLength], r15d; OutputBufferLength
0x14002bca4  xor     r9d, r9d; ApcContext
0x14002bca7  mov     [rsp+150h+OutputBuffer], rbx; OutputBuffer
0x14002bcac  xor     r8d, r8d; ApcRoutine
0x14002bcaf  mov     [rsp+150h+InputBufferLength], r15d; InputBufferLength
0x14002bcb4  xor     edx, edx; Event
0x14002bcb6  mov     qword ptr [rax], 2C01B9h
0x14002bcbd  mov     [rax+8], r14d
0x14002bcc1  mov     dword ptr [rax+0Ch], 10101h
0x14002bcc8  mov     [rax+28h], r15w
0x14002bccd  lea     rax, [rbp+50h+IoStatusBlock]
0x14002bcd1  mov     rcx, [rsp+150h+FileHandle]; FileHandle
0x14002bcd6  mov     [rsp+150h+InputBuffer], rbx; InputBuffer
0x14002bcdb  mov     [rsp+150h+OpenOptions], 17009Ch; IoControlCode
0x14002bce3  mov     qword ptr [rsp+150h+ShareAccess], rax; IoStatusBlock
0x14002bce8  mov     [rsp+150h+arg_10], rsi
0x14002bcf0  call    cs:__imp_ZwDeviceIoControlFile
0x14002bcf7  nop     dword ptr [rax+rax+00h]
0x14002bcfc  test    eax, eax
0x14002bcfe  jnz     loc_14002BDE7
0x14002bd04  mov     eax, [rbx+20h]
0x14002bd07  cmp     eax, r15d
0x14002bd0a  jbe     loc_14002BDE7
0x14002bd10  mov     edx, 6D537054h; Tag
0x14002bd15  lea     esi, [rax+2Ch]
0x14002bd18  mov     rcx, rbx; P
0x14002bd1b  call    cs:__imp_ExFreePoolWithTag
0x14002bd22  nop     dword ptr [rax+rax+00h]
0x14002bd27  mov     edx, esi
0x14002bd29  mov     ecx, 100h
0x14002bd2e  mov     r8d, 6D537054h
0x14002bd34  call    cs:__imp_ExAllocatePool2
0x14002bd3b  nop     dword ptr [rax+rax+00h]
0x14002bd40  mov     rbx, rax
0x14002bd43  test    rax, rax
0x14002bd46  jnz     short loc_14002BD5E
0x14002bd48  mov     rcx, [rsp+150h+FileHandle]; Handle
0x14002bd4d  call    cs:__imp_ZwClose
0x14002bd54  nop     dword ptr [rax+rax+00h]
0x14002bd59  jmp     loc_14002BE11
0x14002bd5e  mov     [rsp+150h+OutputBufferLength], esi; OutputBufferLength
0x14002bd62  xor     r9d, r9d; ApcContext
0x14002bd65  mov     [rsp+150h+OutputBuffer], rbx; OutputBuffer
0x14002bd6a  xor     r8d, r8d; ApcRoutine
0x14002bd6d  mov     [rsp+150h+InputBufferLength], esi; InputBufferLength
0x14002bd71  xor     edx, edx; Event
0x14002bd73  mov     qword ptr [rax], 2C01B9h
0x14002bd7a  mov     [rax+8], r14d
0x14002bd7e  mov     dword ptr [rax+0Ch], 10101h
0x14002bd85  mov     [rax+28h], r15w
0x14002bd8a  lea     rax, [rbp+50h+IoStatusBlock]
0x14002bd8e  mov     rcx, [rsp+150h+FileHandle]; FileHandle
0x14002bd93  mov     [rsp+150h+InputBuffer], rbx; InputBuffer
0x14002bd98  mov     [rsp+150h+OpenOptions], 17009Ch; IoControlCode
0x14002bda0  mov     qword ptr [rsp+150h+ShareAccess], rax; IoStatusBlock
0x14002bda5  call    cs:__imp_ZwDeviceIoControlFile
0x14002bdac  nop     dword ptr [rax+rax+00h]
0x14002bdb1  test    eax, eax
0x14002bdb3  jnz     short loc_14002BDE7
0x14002bdb5  movzx   eax, word ptr [rbx+28h]
0x14002bdb9  mov     ecx, r14d
0x14002bdbc  mov     edx, [rbx+18h]
0x14002bdbf  add     rax, rbx
0x14002bdc2  shr     edx, 2
0x14002bdc5  test    edx, edx
0x14002bdc7  jz      short loc_14002BDE7
0x14002bdc9  nop     dword ptr [rax+00000000h]
0x14002bdd0  cmp     dword ptr [rax], 0FA010101h
0x14002bdd6  jz      short loc_14002BDE4
0x14002bdd8  add     rax, 4
0x14002bddc  inc     ecx
0x14002bdde  cmp     ecx, edx
0x14002bde0  jb      short loc_14002BDD0
0x14002bde2  jmp     short loc_14002BDE7
0x14002bde4  mov     dil, 1
0x14002bde7  mov     rcx, [rsp+150h+FileHandle]; Handle
0x14002bdec  call    cs:__imp_ZwClose
0x14002bdf3  nop     dword ptr [rax+rax+00h]
0x14002bdf8  test    rbx, rbx
0x14002bdfb  jz      short loc_14002BE11
0x14002bdfd  mov     edx, 6D537054h; Tag
0x14002be02  mov     rcx, rbx; P
0x14002be05  call    cs:__imp_ExFreePoolWithTag
0x14002be0c  nop     dword ptr [rax+rax+00h]
0x14002be11  mov     rsi, [rsp+150h+arg_10]
0x14002be19  mov     rbx, [rsp+150h+arg_8]
0x14002be21  mov     r15, [rsp+150h+arg_18]
0x14002be29  lea     rcx, [rsp+150h+GuidString]; UnicodeString
0x14002be2e  call    cs:__imp_RtlFreeUnicodeString
0x14002be35  nop     dword ptr [rax+rax+00h]
0x14002be3a  movzx   eax, dil
0x14002be3e  mov     rcx, [rbp+50h+var_20]
0x14002be42  xor     rcx, rsp; StackCookie
0x14002be45  call    __security_check_cookie
0x14002be4a  add     rsp, 140h
0x14002be51  pop     r14
0x14002be53  pop     rdi
0x14002be54  pop     rbp
0x14002be55  retn
```
