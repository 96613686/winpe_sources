# BiIsBootRamdisk

- ea: `0x18003181c`
- end: `0x180031963`
- name: `BiIsBootRamdisk`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x18002e970`

## callees

- `0x1800032b8`
- `0x18003181c`

## import_xrefs

- `ntdll!ZwDeviceIoControlFile` at `0x180031911`
- `ntdll!ZwDeviceIoControlFile` at `0x180031911`
- `ntdll!ZwClose` at `0x180031923`
- `ntdll!ZwClose` at `0x180031923`
- `ntdll!ZwOpenFile` at `0x1800318c6`
- `ntdll!ZwOpenFile` at `0x1800318c6`
- `ntdll!RtlInitUnicodeString` at `0x180031873`
- `ntdll!RtlInitUnicodeString` at `0x180031873`

## pseudocode

```c
char __fastcall BiIsBootRamdisk(_QWORD *a1)
{
  char v2; // di
  NTSTATUS v3; // ebx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-59h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-19h] BYREF
  _BYTE OutputBuffer[20]; // [rsp+A0h] [rbp-9h] BYREF
  int v9; // [rsp+B4h] [rbp+Bh]
  __int64 v10; // [rsp+C0h] [rbp+17h]
  __int64 v11; // [rsp+D0h] [rbp+27h]
  void *FileHandle; // [rsp+118h] [rbp+6Fh] BYREF

  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  IoStatusBlock = 0;
  memset_0(OutputBuffer, 0, 0x40u);
  FileHandle = 0;
  v2 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\Ramdisk{d9b257fc-684e-4dcb-ab79-03cfa2f6b750}");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  if ( ZwOpenFile(&FileHandle, 0xC0000000, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u) >= 0 )
  {
    v3 = ZwDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x240008u, 0, 0, OutputBuffer, 0x40u);
    ZwClose(FileHandle);
    if ( v3 >= 0 && (v9 == 3 || *a1 == v11 << 12 && a1[1] == v10) )
      return 1;
  }
  return v2;
}

```

## disassembly

```asm
0x18003181c  push    rbp
0x18003181e  push    rbx
0x18003181f  push    rsi
0x180031820  push    rdi
0x180031821  lea     rbp, [rsp-3Fh]
0x180031826  sub     rsp, 0E8h
0x18003182d  xorps   xmm0, xmm0
0x180031830  xor     eax, eax
0x180031832  mov     rsi, rcx
0x180031835  xor     edx, edx; Val
0x180031837  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18003183b  lea     rcx, [rbp+57h+var_60]; void *
0x18003183f  lea     ebx, [rax+40h]
0x180031842  mov     r8d, ebx; Size
0x180031845  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180031849  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18003184d  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180031851  call    memset_0
0x180031856  xorps   xmm0, xmm0
0x180031859  mov     [rbp+57h+FileHandle], 0
0x180031861  lea     rdx, aDeviceRamdiskD; "\\Device\\Ramdisk{d9b257fc-684e-4dcb-ab"...
0x180031868  xor     dil, dil
0x18003186b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003186f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180031873  call    cs:__imp_RtlInitUnicodeString
0x18003187a  nop     dword ptr [rax+rax+00h]
0x18003187f  lea     rax, [rbp+57h+DestinationString]
0x180031883  mov     [rsp+100h+OpenOptions], 20h ; ' '; OpenOptions
0x18003188b  xorps   xmm0, xmm0
0x18003188e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180031892  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180031896  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18003189d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800318a1  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800318a9  mov     edx, 0C0000000h; DesiredAccess
0x1800318ae  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800318b5  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800318b9  mov     [rsp+100h+ShareAccess], 3; ShareAccess
0x1800318c1  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800318c6  call    cs:__imp_ZwOpenFile
0x1800318cd  nop     dword ptr [rax+rax+00h]
0x1800318d2  test    eax, eax
0x1800318d4  js      short loc_180031953
0x1800318d6  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800318da  lea     rax, [rbp+57h+var_60]
0x1800318de  mov     [rsp+100h+OutputBufferLength], ebx; OutputBufferLength
0x1800318e2  xor     r9d, r9d; ApcContext
0x1800318e5  mov     [rsp+100h+OutputBuffer], rax; OutputBuffer
0x1800318ea  xor     r8d, r8d; ApcRoutine
0x1800318ed  mov     [rsp+100h+InputBufferLength], 0; InputBufferLength
0x1800318f5  lea     rax, [rbp+57h+IoStatusBlock]
0x1800318f9  mov     [rsp+100h+InputBuffer], 0; InputBuffer
0x180031902  xor     edx, edx; Event
0x180031904  mov     [rsp+100h+OpenOptions], 240008h; IoControlCode
0x18003190c  mov     qword ptr [rsp+100h+ShareAccess], rax; IoStatusBlock
0x180031911  call    cs:__imp_ZwDeviceIoControlFile
0x180031918  nop     dword ptr [rax+rax+00h]
0x18003191d  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180031921  mov     ebx, eax
0x180031923  call    cs:__imp_ZwClose
0x18003192a  nop     dword ptr [rax+rax+00h]
0x18003192f  test    ebx, ebx
0x180031931  js      short loc_180031953
0x180031933  cmp     [rbp+57h+var_4C], 3
0x180031937  jz      short loc_180031950
0x180031939  mov     rax, [rbp+57h+var_30]
0x18003193d  shl     rax, 0Ch
0x180031941  cmp     [rsi], rax
0x180031944  jnz     short loc_180031953
0x180031946  mov     rax, [rbp+57h+var_40]
0x18003194a  cmp     [rsi+8], rax
0x18003194e  jnz     short loc_180031953
0x180031950  mov     dil, 1
0x180031953  mov     al, dil
0x180031956  add     rsp, 0E8h
0x18003195d  pop     rdi
0x18003195e  pop     rsi
0x18003195f  pop     rbx
0x180031960  pop     rbp
0x180031961  retn
```
