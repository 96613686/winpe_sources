# BiGetPhysicalDiskNumber

- ea: `0x18003151c`
- end: `0x180031641`
- name: `BiGetPhysicalDiskNumber`
- size: `293`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180031648`
- `0x180034598`

## callees

- `0x18003151c`
- `0x180031700`

## import_xrefs

- `ntdll!ZwClose` at `0x18003161d`
- `ntdll!ZwClose` at `0x18003161d`
- `ntdll!ZwOpenFile` at `0x1800315b6`
- `ntdll!ZwOpenFile` at `0x1800315b6`
- `ntdll!RtlFreeHeap` at `0x180031608`
- `ntdll!RtlFreeHeap` at `0x180031608`
- `ntdll!RtlInitUnicodeString` at `0x18003155f`
- `ntdll!RtlInitUnicodeString` at `0x18003155f`

## pseudocode

```c
__int64 __fastcall BiGetPhysicalDiskNumber(PCWSTR SourceString, _DWORD *a2)
{
  NTSTATUS v3; // ebx
  int VolumeDiskExtentsInformation; // eax
  PVOID v5; // r8
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+A0h] [rbp+20h] BYREF
  PVOID P; // [rsp+A8h] [rbp+28h]

  FileHandle = 0;
  P = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  v3 = ZwOpenFile(&FileHandle, 0x80100000, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  if ( v3 >= 0 )
  {
    VolumeDiskExtentsInformation = BiGetVolumeDiskExtentsInformation(FileHandle);
    v5 = P;
    v3 = VolumeDiskExtentsInformation;
    if ( VolumeDiskExtentsInformation >= 0 )
    {
      if ( *(_DWORD *)P == 1 )
      {
        v3 = 0;
        *a2 = *((_DWORD *)P + 2);
      }
      else
      {
        v3 = -1073741637;
      }
    }
    if ( v5 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003151c  mov     [rsp-8+arg_0], rbx
0x180031521  mov     [rsp-8+arg_8], rdi
0x180031526  push    rbp
0x180031527  mov     rbp, rsp
0x18003152a  sub     rsp, 80h
0x180031531  xorps   xmm0, xmm0
0x180031534  xor     eax, eax
0x180031536  mov     rdi, rdx
0x180031539  mov     [rbp+FileHandle], rax
0x18003153d  mov     rdx, rcx; SourceString
0x180031540  mov     [rbp+P], rax
0x180031544  xorps   xmm1, xmm1
0x180031547  lea     rcx, [rbp+DestinationString]; DestinationString
0x18003154b  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18003154f  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180031553  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180031557  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x18003155b  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x18003155f  call    cs:__imp_RtlInitUnicodeString
0x180031566  nop     dword ptr [rax+rax+00h]
0x18003156b  xorps   xmm0, xmm0
0x18003156e  mov     [rsp+80h+OpenOptions], 20h ; ' '; OpenOptions
0x180031576  lea     rax, [rbp+DestinationString]
0x18003157a  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180031581  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x180031585  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180031589  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18003158d  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180031595  mov     edx, 80100000h; DesiredAccess
0x18003159a  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800315a1  lea     rcx, [rbp+FileHandle]; FileHandle
0x1800315a5  mov     [rsp+80h+ShareAccess], 3; ShareAccess
0x1800315ad  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800315b2  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x1800315b6  call    cs:__imp_ZwOpenFile
0x1800315bd  nop     dword ptr [rax+rax+00h]
0x1800315c2  mov     ebx, eax
0x1800315c4  test    eax, eax
0x1800315c6  js      short loc_180031614
0x1800315c8  mov     rcx, [rbp+FileHandle]; FileHandle
0x1800315cc  lea     rdx, [rbp+P]
0x1800315d0  call    BiGetVolumeDiskExtentsInformation
0x1800315d5  mov     r8, [rbp+P]; P
0x1800315d9  mov     ebx, eax
0x1800315db  test    eax, eax
0x1800315dd  js      short loc_1800315F4
0x1800315df  cmp     dword ptr [r8], 1
0x1800315e3  jz      short loc_1800315EC
0x1800315e5  mov     ebx, 0C00000BBh
0x1800315ea  jmp     short loc_1800315F4
0x1800315ec  mov     eax, [r8+8]
0x1800315f0  xor     ebx, ebx
0x1800315f2  mov     [rdi], eax
0x1800315f4  test    r8, r8
0x1800315f7  jz      short loc_180031614
0x1800315f9  mov     rcx, gs:60h
0x180031602  xor     edx, edx; Flags
0x180031604  mov     rcx, [rcx+30h]; HeapHandle
0x180031608  call    cs:__imp_RtlFreeHeap
0x18003160f  nop     dword ptr [rax+rax+00h]
0x180031614  mov     rcx, [rbp+FileHandle]; Handle
0x180031618  test    rcx, rcx
0x18003161b  jz      short loc_180031629
0x18003161d  call    cs:__imp_ZwClose
0x180031624  nop     dword ptr [rax+rax+00h]
0x180031629  lea     r11, [rsp+80h+var_s0]
0x180031631  mov     eax, ebx
0x180031633  mov     rbx, [r11+10h]
0x180031637  mov     rdi, [r11+18h]
0x18003163b  mov     rsp, r11
0x18003163e  pop     rbp
0x18003163f  retn
```
