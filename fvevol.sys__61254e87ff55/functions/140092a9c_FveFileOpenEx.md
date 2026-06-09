# FveFileOpenEx

- ea: `0x140092a9c`
- end: `0x140092f2e`
- name: `FveFileOpenEx`
- size: `1170`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING SourceString@<rcx>, GUID *Guid@<rdx>, char, ULONG, ULONG, ULONG, char, __int64, __int64, __int64)`
- caller_count: `12`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14005ac80`
- `0x14005addc`
- `0x14005dc88`
- `0x140067b98`
- `0x14006a2c4`
- `0x14006c700`
- `0x14006d720`
- `0x14006f43c`
- `0x1400913c4`
- `0x1400920a8`
- `0x1400928d4`
- `0x140092f34`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x14000afb4`
- `0x140092a9c`
- `0x140097620`
- `0x14009a340`
- `0x14009c020`
- `0x1400e08f4`
- `0x1400e6538`

## import_xrefs

- `ntoskrnl!ZwFsControlFile` at `0x140092ddc`
- `ntoskrnl!ZwFsControlFile` at `0x140092ddc`
- `ntoskrnl!KeDelayExecutionThread` at `0x140092ca2`
- `ntoskrnl!KeDelayExecutionThread` at `0x140092ca2`
- `ntoskrnl!ZwCreateFile` at `0x140092c68`
- `ntoskrnl!ZwCreateFile` at `0x140092c68`
- `ntoskrnl!ZwClose` at `0x140092ed1`
- `ntoskrnl!ZwClose` at `0x140092ed1`

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
0x140092a9c  mov     [rsp-8+arg_0], rcx
0x140092aa1  push    rbp
0x140092aa2  push    rbx
0x140092aa3  push    rsi
0x140092aa4  push    rdi
0x140092aa5  push    r12
0x140092aa7  push    r13
0x140092aa9  push    r14
0x140092aab  push    r15
0x140092aad  lea     rbp, [rsp-7]
0x140092ab2  sub     rsp, 0E8h
0x140092ab9  xorps   xmm0, xmm0
0x140092abc  xor     r12d, r12d
0x140092abf  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm0
0x140092ac3  mov     rdi, r9
0x140092ac6  mov     esi, r8d
0x140092ac9  movups  xmmword ptr [rbp+3Fh+ObjectAttributes+1Ch], xmm0
0x140092acd  mov     r14, rdx
0x140092ad0  mov     [rsp+120h+FileHandle], r12
0x140092ad5  mov     r15, rcx
0x140092ad8  mov     qword ptr [rbp+3Fh+var_A8], r12
0x140092adc  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x140092ae0  xor     eax, eax
0x140092ae2  mov     qword ptr [rbp+3Fh+Interval], r12
0x140092ae6  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm0
0x140092aea  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm0
0x140092aee  mov     rcx, cs:WPP_GLOBAL_Control
0x140092af5  lea     r13, WPP_GLOBAL_Control
0x140092afc  cmp     rcx, r13
0x140092aff  jz      short loc_140092B23
0x140092b01  mov     eax, [rcx+2Ch]
0x140092b04  test    al, 20h
0x140092b06  jz      short loc_140092B23
0x140092b08  cmp     byte ptr [rcx+29h], 5
0x140092b0c  jb      short loc_140092B23
0x140092b0e  mov     rcx, [rcx+18h]
0x140092b12  lea     edx, [r12+22h]
0x140092b17  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x140092b1e  call    WPP_SF_
0x140092b23  xorps   xmm0, xmm0
0x140092b26  mov     [rsp+120h+FileHandle], r12
0x140092b2b  xorps   xmm1, xmm1
0x140092b2e  lea     rcx, [rbp+3Fh+DestinationString]
0x140092b32  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x140092b36  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm1
0x140092b3a  call    FveAllocateUnicodePath
0x140092b3f  mov     ebx, eax
0x140092b41  test    eax, eax
0x140092b43  jns     short loc_140092B88
0x140092b45  mov     rcx, cs:WPP_GLOBAL_Control
0x140092b4c  cmp     rcx, r13
0x140092b4f  jz      loc_140092EC7
0x140092b55  mov     edx, [rcx+2Ch]
0x140092b58  test    dl, 20h
0x140092b5b  jz      loc_140092EC7
0x140092b61  cmp     byte ptr [rcx+29h], 2
0x140092b65  jb      loc_140092EC7
0x140092b6b  mov     edx, 23h ; '#'
0x140092b70  mov     r9d, eax
0x140092b73  mov     rcx, [rcx+18h]
0x140092b77  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x140092b7e  call    WPP_SF_d
0x140092b83  jmp     loc_140092EC7
0x140092b88  lea     rax, [rbp+3Fh+DestinationString]
0x140092b8c  mov     r9, rdi
0x140092b8f  mov     r8d, esi
0x140092b92  mov     [rsp+120h+AllocationSize], rax; DestinationString
0x140092b97  mov     rdx, r14; Guid
0x140092b9a  mov     rcx, r15; SourceString
0x140092b9d  call    FveFileGetPath
0x140092ba2  mov     ebx, eax
0x140092ba4  test    eax, eax
0x140092ba6  jns     short loc_140092BD7
0x140092ba8  mov     rcx, cs:WPP_GLOBAL_Control
0x140092baf  cmp     rcx, r13
0x140092bb2  jz      loc_140092EC7
0x140092bb8  mov     eax, [rcx+2Ch]
0x140092bbb  test    al, 20h
0x140092bbd  jz      loc_140092EC7
0x140092bc3  cmp     byte ptr [rcx+29h], 2
0x140092bc7  jb      loc_140092EC7
0x140092bcd  mov     edx, 24h ; '$'
0x140092bd2  mov     r9d, ebx
0x140092bd5  jmp     short loc_140092B73
0x140092bd7  neg     [rbp+3Fh+arg_40]
0x140092bdd  lea     rax, [rbp+3Fh+DestinationString]
0x140092be1  mov     r15, [rbp+3Fh+arg_48]
0x140092be8  xorps   xmm0, xmm0
0x140092beb  mov     edi, [rbp+3Fh+arg_30]
0x140092bee  sbb     esi, esi
0x140092bf0  mov     r13d, [rbp+3Fh+arg_28]
0x140092bf4  mov     r14d, r12d
0x140092bf7  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x140092bfb  mov     eax, 0C0000000h
0x140092c00  and     esi, eax
0x140092c02  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], r12
0x140092c06  mov     r12d, [rbp+3Fh+arg_38]
0x140092c0d  add     esi, eax
0x140092c0f  mov     qword ptr [rbp+3Fh+var_A8], r15
0x140092c13  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x140092c1a  mov     [rbp+3Fh+ObjectAttributes.Attributes], 240h
0x140092c21  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x140092c26  mov     [rsp+120h+EaLength], 0; EaLength
0x140092c2e  lea     rax, [rbp+3Fh+var_A8]
0x140092c32  mov     [rsp+120h+EaBuffer], 0; EaBuffer
0x140092c3b  lea     r9, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x140092c3f  mov     [rsp+120h+CreateOptions], r12d; CreateOptions
0x140092c44  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x140092c48  mov     [rsp+120h+CreateDisposition], edi; CreateDisposition
0x140092c4c  lea     rcx, [rsp+120h+FileHandle]; FileHandle
0x140092c51  mov     [rsp+120h+ShareAccess], r13d; ShareAccess
0x140092c56  mov     edx, esi; DesiredAccess
0x140092c58  mov     [rsp+120h+FileAttributes], 6; FileAttributes
0x140092c60  inc     r14d
0x140092c63  mov     [rsp+120h+AllocationSize], rax; AllocationSize
0x140092c68  call    cs:__imp_ZwCreateFile
0x140092c6f  nop     dword ptr [rax+rax+00h]
0x140092c74  mov     ebx, eax
0x140092c76  cmp     eax, 0C0000022h
0x140092c7b  jnz     short loc_140092CB3
0x140092c7d  cmp     edi, 5
0x140092c80  ja      short loc_140092CB3
0x140092c82  mov     eax, 35h ; '5'
0x140092c87  bt      eax, edi
0x140092c8a  jnb     short loc_140092CB3
0x140092c8c  cmp     r14d, 3
0x140092c90  ja      short loc_140092CB3
0x140092c92  lea     r8, [rbp+3Fh+Interval]; Interval
0x140092c96  mov     qword ptr [rbp+3Fh+Interval], 0FFFFFFFFFFB3B4C0h
0x140092c9e  xor     edx, edx; Alertable
0x140092ca0  xor     ecx, ecx; WaitMode
0x140092ca2  call    cs:__imp_KeDelayExecutionThread
0x140092ca9  nop     dword ptr [rax+rax+00h]
0x140092cae  jmp     loc_140092C26
0x140092cb3  xor     r12d, r12d
0x140092cb6  test    ebx, ebx
0x140092cb8  jns     short loc_140092D07
0x140092cba  mov     rcx, cs:WPP_GLOBAL_Control
0x140092cc1  lea     r13, WPP_GLOBAL_Control
0x140092cc8  cmp     rcx, r13
0x140092ccb  jz      loc_140092EC7
0x140092cd1  mov     eax, [rcx+2Ch]
0x140092cd4  test    al, 20h
0x140092cd6  jz      loc_140092EC7
0x140092cdc  cmp     byte ptr [rcx+29h], 2
0x140092ce0  jb      loc_140092EC7
0x140092ce6  mov     rcx, [rcx+18h]
0x140092cea  lea     edx, [r12+25h]
0x140092cef  mov     r9d, r14d
0x140092cf2  mov     dword ptr [rsp+120h+AllocationSize], ebx
0x140092cf6  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x140092cfd  call    WPP_SF_Dd
0x140092d02  jmp     loc_140092EC7
0x140092d07  mov     rcx, cs:WPP_GLOBAL_Control
0x140092d0e  lea     r13, WPP_GLOBAL_Control
0x140092d15  cmp     rcx, r13
0x140092d18  jz      short loc_140092D46
0x140092d1a  mov     eax, [rcx+2Ch]
0x140092d1d  test    al, 20h
0x140092d1f  jz      short loc_140092D46
0x140092d21  cmp     byte ptr [rcx+29h], 5
0x140092d25  jb      short loc_140092D46
0x140092d27  mov     eax, dword ptr [rbp+3Fh+IoStatusBlock.Information]
0x140092d2a  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x140092d31  mov     rcx, [rcx+18h]
0x140092d35  mov     edx, 26h ; '&'
0x140092d3a  mov     r9d, edi
0x140092d3d  mov     dword ptr [rsp+120h+AllocationSize], eax
0x140092d41  call    WPP_SF_Dd
0x140092d46  cmp     [rbp+3Fh+IoStatusBlock.Information], 2
0x140092d4b  jnz     loc_140092E24
0x140092d51  mov     rax, [rbp+3Fh+arg_0]
0x140092d55  cmp     dword ptr [rax+78h], 5
0x140092d59  jnz     loc_140092E24
0x140092d5f  xorps   xmm0, xmm0
0x140092d62  mov     [rbp+3Fh+InputBuffer], r12
0x140092d66  movups  xmmword ptr [rbp+3Fh+var_80], xmm0
0x140092d6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140092d71  cmp     rcx, r13
0x140092d74  jz      short loc_140092D98
0x140092d76  mov     eax, [rcx+2Ch]
0x140092d79  test    al, 20h
0x140092d7b  jz      short loc_140092D98
0x140092d7d  cmp     byte ptr [rcx+29h], 5
0x140092d81  jb      short loc_140092D98
0x140092d83  mov     rcx, [rcx+18h]
0x140092d87  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x140092d8e  mov     edx, 27h ; '''
0x140092d93  call    WPP_SF_
0x140092d98  mov     rcx, [rsp+120h+FileHandle]; FileHandle
0x140092d9d  lea     rax, [rbp+3Fh+InputBuffer]
0x140092da1  mov     dword ptr [rsp+120h+EaBuffer], r12d; OutputBufferLength
0x140092da6  xorps   xmm0, xmm0
0x140092da9  mov     qword ptr [rsp+120h+CreateOptions], r12; OutputBuffer
0x140092dae  xor     r9d, r9d; ApcContext
0x140092db1  mov     [rsp+120h+CreateDisposition], 8; InputBufferLength
0x140092db9  xor     r8d, r8d; ApcRoutine
0x140092dbc  mov     qword ptr [rsp+120h+ShareAccess], rax; InputBuffer
0x140092dc1  xor     edx, edx; Event
0x140092dc3  lea     rax, [rbp+3Fh+var_80]
0x140092dc7  mov     [rsp+120h+FileAttributes], 9C280h; FsControlCode
0x140092dcf  mov     [rsp+120h+AllocationSize], rax; IoStatusBlock
0x140092dd4  movups  xmmword ptr [rbp+3Fh+var_80], xmm0
0x140092dd8  mov     [rbp+3Fh+InputBuffer], r12
0x140092ddc  call    cs:__imp_ZwFsControlFile
0x140092de3  nop     dword ptr [rax+rax+00h]
0x140092de8  mov     ebx, eax
0x140092dea  test    eax, eax
0x140092dec  js      short loc_140092DF5
0x140092dee  mov     ebx, dword ptr [rbp+3Fh+var_80]
0x140092df1  test    ebx, ebx
0x140092df3  jns     short loc_140092E24
0x140092df5  mov     rcx, cs:WPP_GLOBAL_Control
0x140092dfc  cmp     rcx, r13
0x140092dff  jz      loc_140092EC7
0x140092e05  mov     eax, [rcx+2Ch]
0x140092e08  test    al, 20h
0x140092e0a  jz      loc_140092EC7
0x140092e10  cmp     byte ptr [rcx+29h], 2
0x140092e14  jb      loc_140092EC7
0x140092e1a  mov     edx, 28h ; '('
0x140092e1f  jmp     loc_140092BD2
0x140092e24  cmp     [rbp+3Fh+arg_20], r12b
0x140092e28  jz      short loc_140092E67
0x140092e2a  cmp     [rbp+3Fh+IoStatusBlock.Information], 1
0x140092e2f  jz      short loc_140092E67
0x140092e31  mov     rcx, [rsp+120h+FileHandle]; FileHandle
0x140092e36  mov     r8, r15
0x140092e39  call    FveFileFillZeros
0x140092e3e  mov     ebx, eax
0x140092e40  test    eax, eax
0x140092e42  jns     short loc_140092E67
0x140092e44  mov     rcx, cs:WPP_GLOBAL_Control
0x140092e4b  cmp     rcx, r13
0x140092e4e  jz      short loc_140092EC7
0x140092e50  mov     eax, [rcx+2Ch]
0x140092e53  test    al, 20h
0x140092e55  jz      short loc_140092EC7
0x140092e57  cmp     byte ptr [rcx+29h], 2
0x140092e5b  jb      short loc_140092EC7
0x140092e5d  mov     edx, 29h ; ')'
0x140092e62  jmp     loc_140092BD2
0x140092e67  test    r15, r15
0x140092e6a  jz      short loc_140092EA2
0x140092e6c  mov     rcx, [rsp+120h+FileHandle]; FileHandle
0x140092e71  mov     rdx, r15
0x140092e74  call    FveFileSetSize
0x140092e79  mov     ebx, eax
0x140092e7b  test    eax, eax
0x140092e7d  jns     short loc_140092EA2
0x140092e7f  mov     rcx, cs:WPP_GLOBAL_Control
0x140092e86  cmp     rcx, r13
0x140092e89  jz      short loc_140092EC7
0x140092e8b  mov     eax, [rcx+2Ch]
0x140092e8e  test    al, 20h
0x140092e90  jz      short loc_140092EC7
0x140092e92  cmp     byte ptr [rcx+29h], 2
0x140092e96  jb      short loc_140092EC7
0x140092e98  mov     edx, 2Ah ; '*'
0x140092e9d  jmp     loc_140092BD2
0x140092ea2  mov     rcx, [rbp+3Fh+arg_50]
0x140092ea9  test    rcx, rcx
0x140092eac  jz      short loc_140092EB3
0x140092eae  mov     eax, dword ptr [rbp+3Fh+IoStatusBlock.Information]
0x140092eb1  mov     [rcx], eax
0x140092eb3  mov     rcx, [rsp+120h+FileHandle]
0x140092eb8  mov     rax, [rbp+3Fh+arg_58]
0x140092ebf  mov     [rsp+120h+FileHandle], r12
0x140092ec4  mov     [rax], rcx
0x140092ec7  mov     rcx, [rsp+120h+FileHandle]; Handle
0x140092ecc  test    rcx, rcx
0x140092ecf  jz      short loc_140092EDD
0x140092ed1  call    cs:__imp_ZwClose
0x140092ed8  nop     dword ptr [rax+rax+00h]
0x140092edd  lea     rcx, [rbp+3Fh+DestinationString]
0x140092ee1  call    FveFreeUnicodePath
0x140092ee6  mov     rcx, cs:WPP_GLOBAL_Control
0x140092eed  cmp     rcx, r13
0x140092ef0  jz      short loc_140092F17
0x140092ef2  mov     eax, [rcx+2Ch]
0x140092ef5  test    al, 20h
0x140092ef7  jz      short loc_140092F17
0x140092ef9  cmp     byte ptr [rcx+29h], 5
0x140092efd  jb      short loc_140092F17
0x140092eff  mov     rcx, [rcx+18h]
0x140092f03  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x140092f0a  mov     edx, 2Bh ; '+'
0x140092f0f  mov     r9d, ebx
0x140092f12  call    WPP_SF_d
0x140092f17  mov     eax, ebx
0x140092f19  add     rsp, 0E8h
0x140092f20  pop     r15
0x140092f22  pop     r14
0x140092f24  pop     r13
0x140092f26  pop     r12
0x140092f28  pop     rdi
0x140092f29  pop     rsi
0x140092f2a  pop     rbx
0x140092f2b  pop     rbp
0x140092f2c  retn
  ... truncated ...
```
