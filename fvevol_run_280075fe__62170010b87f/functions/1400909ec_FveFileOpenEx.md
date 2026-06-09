# FveFileOpenEx

- ea: `0x1400909ec`
- end: `0x140090e7e`
- name: `FveFileOpenEx`
- size: `1170`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING SourceString@<rcx>, GUID *Guid@<rdx>, char, ULONG, ULONG, ULONG, char, __int64, __int64, __int64)`
- caller_count: `12`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140058c28`
- `0x140058d84`
- `0x14005bc18`
- `0x140065b08`
- `0x140068234`
- `0x14006a670`
- `0x14006b690`
- `0x14006d3ac`
- `0x14008f314`
- `0x14008fff8`
- `0x140090824`
- `0x140090e84`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x14000aef4`
- `0x1400909ec`
- `0x140095570`
- `0x140098290`
- `0x140099f70`
- `0x1400de1d4`
- `0x1400e3a5c`

## import_xrefs

- `ntoskrnl!ZwFsControlFile` at `0x140090d2c`
- `ntoskrnl!ZwFsControlFile` at `0x140090d2c`
- `ntoskrnl!KeDelayExecutionThread` at `0x140090bf2`
- `ntoskrnl!KeDelayExecutionThread` at `0x140090bf2`
- `ntoskrnl!ZwCreateFile` at `0x140090bb8`
- `ntoskrnl!ZwCreateFile` at `0x140090bb8`
- `ntoskrnl!ZwClose` at `0x140090e21`
- `ntoskrnl!ZwClose` at `0x140090e21`

## pseudocode

```c
__int64 __fastcall FveFileOpenEx(
        PCUNICODE_STRING SourceString,
        GUID *Guid,
        __int64 a3,
        __int64 a4,
        char a5,
        ULONG ShareAccess,
        ULONG CreateDisposition,
        ULONG CreateOptions,
        char a9,
        __int64 a10,
        _DWORD *a11,
        _QWORD *a12)
{
  int v14; // eax
  NTSTATUS Path; // ebx
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  unsigned int v19; // r14d
  int v20; // eax
  void *v21; // rcx
  void *FileHandle; // [rsp+60h] [rbp-81h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-79h] BYREF
  union _LARGE_INTEGER AllocationSize; // [rsp+78h] [rbp-69h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+80h] [rbp-61h] BYREF
  __int64 InputBuffer; // [rsp+88h] [rbp-59h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-51h] BYREF
  struct _IO_STATUS_BLOCK v29; // [rsp+A0h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-31h] BYREF

  FileHandle = 0;
  AllocationSize.QuadPart = 0;
  DestinationString = 0;
  Interval.QuadPart = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids);
  }
  FileHandle = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  v14 = FveAllocateUnicodePath(&DestinationString);
  Path = v14;
  if ( v14 >= 0 )
  {
    Path = FveFileGetPath(SourceString, Guid, &DestinationString);
    if ( Path >= 0 )
    {
      v19 = 0;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      AllocationSize.QuadPart = a10;
      ObjectAttributes.Length = 48;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      while ( 1 )
      {
        ++v19;
        Path = ZwCreateFile(
                 &FileHandle,
                 a9 != 0 ? 0x80000000 : -1073741824,
                 &ObjectAttributes,
                 &IoStatusBlock,
                 &AllocationSize,
                 6u,
                 ShareAccess,
                 CreateDisposition,
                 CreateOptions,
                 0,
                 0);
        if ( Path != -1073741790 )
          break;
        if ( CreateDisposition > 5 )
          break;
        v20 = 53;
        if ( !_bittest(&v20, CreateDisposition) || v19 > 3 )
          break;
        Interval.QuadPart = -5000000;
        KeDelayExecutionThread(0, 0, &Interval);
      }
      if ( Path < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids, v19, Path);
        }
        goto LABEL_60;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          38,
          WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids,
          CreateDisposition,
          IoStatusBlock.Information);
      }
      if ( IoStatusBlock.Information != 2 || LODWORD(SourceString[7].Buffer) != 5 )
        goto LABEL_69;
      InputBuffer = 0;
      v29 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids);
      }
      v29 = 0;
      InputBuffer = 0;
      Path = ZwFsControlFile(FileHandle, 0, 0, 0, &v29, 0x9C280u, &InputBuffer, 8u, 0, 0);
      if ( Path < 0 || (Path = v29.Status, v29.Status < 0) )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_60;
        }
        v17 = 40;
      }
      else
      {
LABEL_69:
        if ( !a5 || IoStatusBlock.Information == 1 || (Path = FveFileFillZeros(FileHandle), Path >= 0) )
        {
          if ( !a10 || (Path = FveFileSetSize(FileHandle), Path >= 0) )
          {
            if ( a11 )
              *a11 = IoStatusBlock.Information;
            v21 = FileHandle;
            FileHandle = 0;
            *a12 = v21;
            goto LABEL_60;
          }
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_60;
          }
          v17 = 42;
        }
        else
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_60;
          }
          v17 = 41;
        }
      }
    }
    else
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_60;
      }
      v17 = 36;
    }
    v18 = (unsigned int)Path;
    goto LABEL_10;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v17 = 35;
    v18 = (unsigned int)v14;
LABEL_10:
    WPP_SF_d(v16->AttachedDevice, v17, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids, v18);
  }
LABEL_60:
  if ( FileHandle )
    ZwClose(FileHandle);
  FveFreeUnicodePath(&DestinationString);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids,
      (unsigned int)Path);
  }
  return (unsigned int)Path;
}

```

## disassembly

```asm
0x1400909ec  mov     [rsp-8+arg_0], rcx
0x1400909f1  push    rbp
0x1400909f2  push    rbx
0x1400909f3  push    rsi
0x1400909f4  push    rdi
0x1400909f5  push    r12
0x1400909f7  push    r13
0x1400909f9  push    r14
0x1400909fb  push    r15
0x1400909fd  lea     rbp, [rsp-7]
0x140090a02  sub     rsp, 0E8h
0x140090a09  xorps   xmm0, xmm0
0x140090a0c  xor     r12d, r12d
0x140090a0f  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm0
0x140090a13  mov     rdi, r9
0x140090a16  mov     esi, r8d
0x140090a19  movups  xmmword ptr [rbp+3Fh+ObjectAttributes+1Ch], xmm0
0x140090a1d  mov     r14, rdx
0x140090a20  mov     [rsp+120h+FileHandle], r12
0x140090a25  mov     r15, rcx
0x140090a28  mov     qword ptr [rbp+3Fh+var_A8], r12
0x140090a2c  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x140090a30  xor     eax, eax
0x140090a32  mov     qword ptr [rbp+3Fh+Interval], r12
0x140090a36  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm0
0x140090a3a  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm0
0x140090a3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140090a45  lea     r13, WPP_GLOBAL_Control
0x140090a4c  cmp     rcx, r13
0x140090a4f  jz      short loc_140090A73
0x140090a51  mov     eax, [rcx+2Ch]
0x140090a54  test    al, 20h
0x140090a56  jz      short loc_140090A73
0x140090a58  cmp     byte ptr [rcx+29h], 5
0x140090a5c  jb      short loc_140090A73
0x140090a5e  mov     rcx, [rcx+18h]
0x140090a62  lea     edx, [r12+22h]
0x140090a67  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x140090a6e  call    WPP_SF_
0x140090a73  xorps   xmm0, xmm0
0x140090a76  mov     [rsp+120h+FileHandle], r12
0x140090a7b  xorps   xmm1, xmm1
0x140090a7e  lea     rcx, [rbp+3Fh+DestinationString]
0x140090a82  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x140090a86  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm1
0x140090a8a  call    FveAllocateUnicodePath
0x140090a8f  mov     ebx, eax
0x140090a91  test    eax, eax
0x140090a93  jns     short loc_140090AD8
0x140090a95  mov     rcx, cs:WPP_GLOBAL_Control
0x140090a9c  cmp     rcx, r13
0x140090a9f  jz      loc_140090E17
0x140090aa5  mov     edx, [rcx+2Ch]
0x140090aa8  test    dl, 20h
0x140090aab  jz      loc_140090E17
0x140090ab1  cmp     byte ptr [rcx+29h], 2
0x140090ab5  jb      loc_140090E17
0x140090abb  mov     edx, 23h ; '#'
0x140090ac0  mov     r9d, eax
0x140090ac3  mov     rcx, [rcx+18h]
0x140090ac7  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x140090ace  call    WPP_SF_d
0x140090ad3  jmp     loc_140090E17
0x140090ad8  lea     rax, [rbp+3Fh+DestinationString]
0x140090adc  mov     r9, rdi
0x140090adf  mov     r8d, esi
0x140090ae2  mov     [rsp+120h+AllocationSize], rax; DestinationString
0x140090ae7  mov     rdx, r14; Guid
0x140090aea  mov     rcx, r15; SourceString
0x140090aed  call    FveFileGetPath
0x140090af2  mov     ebx, eax
0x140090af4  test    eax, eax
0x140090af6  jns     short loc_140090B27
0x140090af8  mov     rcx, cs:WPP_GLOBAL_Control
0x140090aff  cmp     rcx, r13
0x140090b02  jz      loc_140090E17
0x140090b08  mov     eax, [rcx+2Ch]
0x140090b0b  test    al, 20h
0x140090b0d  jz      loc_140090E17
0x140090b13  cmp     byte ptr [rcx+29h], 2
0x140090b17  jb      loc_140090E17
0x140090b1d  mov     edx, 24h ; '$'
0x140090b22  mov     r9d, ebx
0x140090b25  jmp     short loc_140090AC3
0x140090b27  neg     [rbp+3Fh+arg_40]
0x140090b2d  lea     rax, [rbp+3Fh+DestinationString]
0x140090b31  mov     r15, [rbp+3Fh+arg_48]
0x140090b38  xorps   xmm0, xmm0
0x140090b3b  mov     edi, [rbp+3Fh+arg_30]
0x140090b3e  sbb     esi, esi
0x140090b40  mov     r13d, [rbp+3Fh+arg_28]
0x140090b44  mov     r14d, r12d
0x140090b47  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x140090b4b  mov     eax, 0C0000000h
0x140090b50  and     esi, eax
0x140090b52  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], r12
0x140090b56  mov     r12d, [rbp+3Fh+arg_38]
0x140090b5d  add     esi, eax
0x140090b5f  mov     qword ptr [rbp+3Fh+var_A8], r15
0x140090b63  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x140090b6a  mov     [rbp+3Fh+ObjectAttributes.Attributes], 240h
0x140090b71  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x140090b76  mov     [rsp+120h+EaLength], 0; EaLength
0x140090b7e  lea     rax, [rbp+3Fh+var_A8]
0x140090b82  mov     [rsp+120h+EaBuffer], 0; EaBuffer
0x140090b8b  lea     r9, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x140090b8f  mov     [rsp+120h+CreateOptions], r12d; CreateOptions
0x140090b94  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x140090b98  mov     [rsp+120h+CreateDisposition], edi; CreateDisposition
0x140090b9c  lea     rcx, [rsp+120h+FileHandle]; FileHandle
0x140090ba1  mov     [rsp+120h+ShareAccess], r13d; ShareAccess
0x140090ba6  mov     edx, esi; DesiredAccess
0x140090ba8  mov     [rsp+120h+FileAttributes], 6; FileAttributes
0x140090bb0  inc     r14d
0x140090bb3  mov     [rsp+120h+AllocationSize], rax; AllocationSize
0x140090bb8  call    cs:__imp_ZwCreateFile
0x140090bbf  nop     dword ptr [rax+rax+00h]
0x140090bc4  mov     ebx, eax
0x140090bc6  cmp     eax, 0C0000022h
0x140090bcb  jnz     short loc_140090C03
0x140090bcd  cmp     edi, 5
0x140090bd0  ja      short loc_140090C03
0x140090bd2  mov     eax, 35h ; '5'
0x140090bd7  bt      eax, edi
0x140090bda  jnb     short loc_140090C03
0x140090bdc  cmp     r14d, 3
0x140090be0  ja      short loc_140090C03
0x140090be2  lea     r8, [rbp+3Fh+Interval]; Interval
0x140090be6  mov     qword ptr [rbp+3Fh+Interval], 0FFFFFFFFFFB3B4C0h
0x140090bee  xor     edx, edx; Alertable
0x140090bf0  xor     ecx, ecx; WaitMode
0x140090bf2  call    cs:__imp_KeDelayExecutionThread
0x140090bf9  nop     dword ptr [rax+rax+00h]
0x140090bfe  jmp     loc_140090B76
0x140090c03  xor     r12d, r12d
0x140090c06  test    ebx, ebx
0x140090c08  jns     short loc_140090C57
0x140090c0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140090c11  lea     r13, WPP_GLOBAL_Control
0x140090c18  cmp     rcx, r13
0x140090c1b  jz      loc_140090E17
0x140090c21  mov     eax, [rcx+2Ch]
0x140090c24  test    al, 20h
0x140090c26  jz      loc_140090E17
0x140090c2c  cmp     byte ptr [rcx+29h], 2
0x140090c30  jb      loc_140090E17
0x140090c36  mov     rcx, [rcx+18h]
0x140090c3a  lea     edx, [r12+25h]
0x140090c3f  mov     r9d, r14d
0x140090c42  mov     dword ptr [rsp+120h+AllocationSize], ebx
0x140090c46  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x140090c4d  call    WPP_SF_Dd
0x140090c52  jmp     loc_140090E17
0x140090c57  mov     rcx, cs:WPP_GLOBAL_Control
0x140090c5e  lea     r13, WPP_GLOBAL_Control
0x140090c65  cmp     rcx, r13
0x140090c68  jz      short loc_140090C96
0x140090c6a  mov     eax, [rcx+2Ch]
0x140090c6d  test    al, 20h
0x140090c6f  jz      short loc_140090C96
0x140090c71  cmp     byte ptr [rcx+29h], 5
0x140090c75  jb      short loc_140090C96
0x140090c77  mov     eax, dword ptr [rbp+3Fh+IoStatusBlock.Information]
0x140090c7a  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x140090c81  mov     rcx, [rcx+18h]
0x140090c85  mov     edx, 26h ; '&'
0x140090c8a  mov     r9d, edi
0x140090c8d  mov     dword ptr [rsp+120h+AllocationSize], eax
0x140090c91  call    WPP_SF_Dd
0x140090c96  cmp     [rbp+3Fh+IoStatusBlock.Information], 2
0x140090c9b  jnz     loc_140090D74
0x140090ca1  mov     rax, [rbp+3Fh+arg_0]
0x140090ca5  cmp     dword ptr [rax+78h], 5
0x140090ca9  jnz     loc_140090D74
0x140090caf  xorps   xmm0, xmm0
0x140090cb2  mov     [rbp+3Fh+InputBuffer], r12
0x140090cb6  movups  xmmword ptr [rbp+3Fh+var_80], xmm0
0x140090cba  mov     rcx, cs:WPP_GLOBAL_Control
0x140090cc1  cmp     rcx, r13
0x140090cc4  jz      short loc_140090CE8
0x140090cc6  mov     eax, [rcx+2Ch]
0x140090cc9  test    al, 20h
0x140090ccb  jz      short loc_140090CE8
0x140090ccd  cmp     byte ptr [rcx+29h], 5
0x140090cd1  jb      short loc_140090CE8
0x140090cd3  mov     rcx, [rcx+18h]
0x140090cd7  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x140090cde  mov     edx, 27h ; '''
0x140090ce3  call    WPP_SF_
0x140090ce8  mov     rcx, [rsp+120h+FileHandle]; FileHandle
0x140090ced  lea     rax, [rbp+3Fh+InputBuffer]
0x140090cf1  mov     dword ptr [rsp+120h+EaBuffer], r12d; OutputBufferLength
0x140090cf6  xorps   xmm0, xmm0
0x140090cf9  mov     qword ptr [rsp+120h+CreateOptions], r12; OutputBuffer
0x140090cfe  xor     r9d, r9d; ApcContext
0x140090d01  mov     [rsp+120h+CreateDisposition], 8; InputBufferLength
0x140090d09  xor     r8d, r8d; ApcRoutine
0x140090d0c  mov     qword ptr [rsp+120h+ShareAccess], rax; InputBuffer
0x140090d11  xor     edx, edx; Event
0x140090d13  lea     rax, [rbp+3Fh+var_80]
0x140090d17  mov     [rsp+120h+FileAttributes], 9C280h; FsControlCode
0x140090d1f  mov     [rsp+120h+AllocationSize], rax; IoStatusBlock
0x140090d24  movups  xmmword ptr [rbp+3Fh+var_80], xmm0
0x140090d28  mov     [rbp+3Fh+InputBuffer], r12
0x140090d2c  call    cs:__imp_ZwFsControlFile
0x140090d33  nop     dword ptr [rax+rax+00h]
0x140090d38  mov     ebx, eax
0x140090d3a  test    eax, eax
0x140090d3c  js      short loc_140090D45
0x140090d3e  mov     ebx, dword ptr [rbp+3Fh+var_80]
0x140090d41  test    ebx, ebx
0x140090d43  jns     short loc_140090D74
0x140090d45  mov     rcx, cs:WPP_GLOBAL_Control
0x140090d4c  cmp     rcx, r13
0x140090d4f  jz      loc_140090E17
0x140090d55  mov     eax, [rcx+2Ch]
0x140090d58  test    al, 20h
0x140090d5a  jz      loc_140090E17
0x140090d60  cmp     byte ptr [rcx+29h], 2
0x140090d64  jb      loc_140090E17
0x140090d6a  mov     edx, 28h ; '('
0x140090d6f  jmp     loc_140090B22
0x140090d74  cmp     [rbp+3Fh+arg_20], r12b
0x140090d78  jz      short loc_140090DB7
0x140090d7a  cmp     [rbp+3Fh+IoStatusBlock.Information], 1
0x140090d7f  jz      short loc_140090DB7
0x140090d81  mov     rcx, [rsp+120h+FileHandle]; FileHandle
0x140090d86  mov     r8, r15
0x140090d89  call    FveFileFillZeros
0x140090d8e  mov     ebx, eax
0x140090d90  test    eax, eax
0x140090d92  jns     short loc_140090DB7
0x140090d94  mov     rcx, cs:WPP_GLOBAL_Control
0x140090d9b  cmp     rcx, r13
0x140090d9e  jz      short loc_140090E17
0x140090da0  mov     eax, [rcx+2Ch]
0x140090da3  test    al, 20h
0x140090da5  jz      short loc_140090E17
0x140090da7  cmp     byte ptr [rcx+29h], 2
0x140090dab  jb      short loc_140090E17
0x140090dad  mov     edx, 29h ; ')'
0x140090db2  jmp     loc_140090B22
0x140090db7  test    r15, r15
0x140090dba  jz      short loc_140090DF2
0x140090dbc  mov     rcx, [rsp+120h+FileHandle]; FileHandle
0x140090dc1  mov     rdx, r15
0x140090dc4  call    FveFileSetSize
0x140090dc9  mov     ebx, eax
0x140090dcb  test    eax, eax
0x140090dcd  jns     short loc_140090DF2
0x140090dcf  mov     rcx, cs:WPP_GLOBAL_Control
0x140090dd6  cmp     rcx, r13
0x140090dd9  jz      short loc_140090E17
0x140090ddb  mov     eax, [rcx+2Ch]
0x140090dde  test    al, 20h
0x140090de0  jz      short loc_140090E17
0x140090de2  cmp     byte ptr [rcx+29h], 2
0x140090de6  jb      short loc_140090E17
0x140090de8  mov     edx, 2Ah ; '*'
0x140090ded  jmp     loc_140090B22
0x140090df2  mov     rcx, [rbp+3Fh+arg_50]
0x140090df9  test    rcx, rcx
0x140090dfc  jz      short loc_140090E03
0x140090dfe  mov     eax, dword ptr [rbp+3Fh+IoStatusBlock.Information]
0x140090e01  mov     [rcx], eax
0x140090e03  mov     rcx, [rsp+120h+FileHandle]
0x140090e08  mov     rax, [rbp+3Fh+arg_58]
0x140090e0f  mov     [rsp+120h+FileHandle], r12
0x140090e14  mov     [rax], rcx
0x140090e17  mov     rcx, [rsp+120h+FileHandle]; Handle
0x140090e1c  test    rcx, rcx
0x140090e1f  jz      short loc_140090E2D
0x140090e21  call    cs:__imp_ZwClose
0x140090e28  nop     dword ptr [rax+rax+00h]
0x140090e2d  lea     rcx, [rbp+3Fh+DestinationString]
0x140090e31  call    FveFreeUnicodePath
0x140090e36  mov     rcx, cs:WPP_GLOBAL_Control
0x140090e3d  cmp     rcx, r13
0x140090e40  jz      short loc_140090E67
0x140090e42  mov     eax, [rcx+2Ch]
0x140090e45  test    al, 20h
0x140090e47  jz      short loc_140090E67
0x140090e49  cmp     byte ptr [rcx+29h], 5
0x140090e4d  jb      short loc_140090E67
0x140090e4f  mov     rcx, [rcx+18h]
0x140090e53  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x140090e5a  mov     edx, 2Bh ; '+'
0x140090e5f  mov     r9d, ebx
0x140090e62  call    WPP_SF_d
0x140090e67  mov     eax, ebx
0x140090e69  add     rsp, 0E8h
0x140090e70  pop     r15
0x140090e72  pop     r14
0x140090e74  pop     r13
0x140090e76  pop     r12
0x140090e78  pop     rdi
0x140090e79  pop     rsi
0x140090e7a  pop     rbx
0x140090e7b  pop     rbp
0x140090e7c  retn
  ... truncated ...
```
