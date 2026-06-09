# BiCreateVhdRamdiskBootDevice

- ea: `0x180030558`
- end: `0x180030766`
- name: `BiCreateVhdRamdiskBootDevice`
- size: `526`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x18003008c`

## callees

- `0x1800032b8`
- `0x180003bb5`
- `0x180030558`

## import_xrefs

- `ntdll!ZwDeviceIoControlFile` at `0x18003064f`
- `ntdll!ZwDeviceIoControlFile` at `0x18003064f`
- `ntdll!ZwClose` at `0x180030661`
- `ntdll!ZwClose` at `0x180030661`
- `ntdll!ZwOpenFile` at `0x180030605`
- `ntdll!ZwOpenFile` at `0x180030605`
- `ntdll!RtlInitUnicodeString` at `0x1800305b6`
- `ntdll!RtlInitUnicodeString` at `0x1800305b6`
- `ntdll!RtlAllocateHeap` at `0x1800306b5`
- `ntdll!RtlAllocateHeap` at `0x1800306b5`

## pseudocode

```c
__int64 __fastcall BiCreateVhdRamdiskBootDevice(__int64 a1, _QWORD *a2)
{
  NTSTATUS v4; // ebx
  __int64 v5; // rax
  size_t v6; // rsi
  unsigned int v7; // r14d
  char *Heap; // rax
  char *v9; // rbx
  int v10; // eax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-79h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-49h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-39h] BYREF
  _BYTE OutputBuffer[20]; // [rsp+A0h] [rbp-29h] BYREF
  int v16; // [rsp+B4h] [rbp-15h]
  __int64 v17; // [rsp+C0h] [rbp-9h]
  int v18; // [rsp+C8h] [rbp-1h]
  __int64 v19; // [rsp+D0h] [rbp+7h]
  void *FileHandle; // [rsp+140h] [rbp+77h] BYREF

  IoStatusBlock = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  memset_0(OutputBuffer, 0, 0x40u);
  DestinationString = 0;
  FileHandle = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\Ramdisk{d9b257fc-684e-4dcb-ab79-03cfa2f6b750}");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  v4 = ZwOpenFile(&FileHandle, 0xC0000000, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  if ( v4 >= 0 )
  {
    v4 = ZwDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x240008u, 0, 0, OutputBuffer, 0x40u);
    ZwClose(FileHandle);
    if ( v4 >= 0 )
    {
      if ( v16 == 3 )
      {
        v5 = -1;
        do
          ++v5;
        while ( *(_WORD *)(a1 + 2 * v5 + 106) );
        v6 = 2 * v5 + 2;
        v7 = 2 * v5 + 106;
        Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
        v9 = Heap;
        if ( Heap )
        {
          memset_0(Heap, 0, v7);
          *(_DWORD *)v9 = 0;
          *((_DWORD *)v9 + 4) = 5;
          *(_QWORD *)(v9 + 28) = 5;
          *((_DWORD *)v9 + 6) = v6 + 84;
          *((_DWORD *)v9 + 2) = v7;
          *((_DWORD *)v9 + 5) = 1;
          *((_DWORD *)v9 + 10) = 72;
          *((_DWORD *)v9 + 9) = 16;
          *((_DWORD *)v9 + 12) = 3;
          *(_QWORD *)(v9 + 52) = v19 << 12;
          *(_QWORD *)(v9 + 60) = v17;
          v10 = v18;
          *((_DWORD *)v9 + 18) = 1;
          *((_DWORD *)v9 + 20) = 5;
          *((_DWORD *)v9 + 17) = v10;
          *((_DWORD *)v9 + 19) = 12;
          memcpy_0(v9 + 104, (const void *)(a1 + 106), v6);
          *a2 = v9;
          return 0;
        }
        else
        {
          return (unsigned int)-1073741670;
        }
      }
      else
      {
        return (unsigned int)-1073741808;
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180030558  push    rbp
0x18003055a  push    rbx
0x18003055b  push    rsi
0x18003055c  push    rdi
0x18003055d  push    r12
0x18003055f  push    r13
0x180030561  push    r14
0x180030563  push    r15
0x180030565  lea     rbp, [rsp-1Fh]
0x18003056a  sub     rsp, 0E8h
0x180030571  xorps   xmm0, xmm0
0x180030574  xor     eax, eax
0x180030576  mov     r12, rdx
0x180030579  mov     rdi, rcx
0x18003057c  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180030580  xor     edx, edx; Val
0x180030582  lea     rcx, [rbp+57h+var_80]; void *
0x180030586  lea     esi, [rax+40h]
0x180030589  mov     r8d, esi; Size
0x18003058c  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180030590  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180030594  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180030598  call    memset_0
0x18003059d  xorps   xmm0, xmm0
0x1800305a0  lea     rdx, aDeviceRamdiskD; "\\Device\\Ramdisk{d9b257fc-684e-4dcb-ab"...
0x1800305a7  xor     r13d, r13d
0x1800305aa  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800305ae  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800305b2  mov     [rbp+57h+FileHandle], r13
0x1800305b6  call    cs:__imp_RtlInitUnicodeString
0x1800305bd  nop     dword ptr [rax+rax+00h]
0x1800305c2  lea     rax, [rbp+57h+DestinationString]
0x1800305c6  mov     [rsp+120h+OpenOptions], 20h ; ' '; OpenOptions
0x1800305ce  xorps   xmm0, xmm0
0x1800305d1  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800305d5  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800305d9  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800305e0  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800305e4  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x1800305e8  mov     edx, 0C0000000h; DesiredAccess
0x1800305ed  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800305f4  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800305f8  mov     [rsp+120h+ShareAccess], 3; ShareAccess
0x180030600  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180030605  call    cs:__imp_ZwOpenFile
0x18003060c  nop     dword ptr [rax+rax+00h]
0x180030611  mov     ebx, eax
0x180030613  test    eax, eax
0x180030615  js      loc_18003074F
0x18003061b  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18003061f  lea     rax, [rbp+57h+var_80]
0x180030623  mov     [rsp+120h+OutputBufferLength], esi; OutputBufferLength
0x180030627  xor     r9d, r9d; ApcContext
0x18003062a  mov     [rsp+120h+OutputBuffer], rax; OutputBuffer
0x18003062f  xor     r8d, r8d; ApcRoutine
0x180030632  mov     [rsp+120h+InputBufferLength], r13d; InputBufferLength
0x180030637  lea     rax, [rbp+57h+IoStatusBlock]
0x18003063b  mov     [rsp+120h+InputBuffer], r13; InputBuffer
0x180030640  xor     edx, edx; Event
0x180030642  mov     [rsp+120h+OpenOptions], 240008h; IoControlCode
0x18003064a  mov     qword ptr [rsp+120h+ShareAccess], rax; IoStatusBlock
0x18003064f  call    cs:__imp_ZwDeviceIoControlFile
0x180030656  nop     dword ptr [rax+rax+00h]
0x18003065b  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18003065f  mov     ebx, eax
0x180030661  call    cs:__imp_ZwClose
0x180030668  nop     dword ptr [rax+rax+00h]
0x18003066d  test    ebx, ebx
0x18003066f  js      loc_18003074F
0x180030675  cmp     [rbp+57h+var_6C], 3
0x180030679  jz      short loc_180030685
0x18003067b  mov     ebx, 0C0000010h
0x180030680  jmp     loc_18003074F
0x180030685  or      rax, 0FFFFFFFFFFFFFFFFh
0x180030689  inc     rax
0x18003068c  cmp     [rdi+rax*2+6Ah], r13w
0x180030692  jnz     short loc_180030689
0x180030694  mov     rcx, gs:60h
0x18003069d  lea     rsi, ds:2[rax*2]
0x1800306a5  lea     r14d, [rsi+68h]
0x1800306a9  xor     edx, edx; Flags
0x1800306ab  mov     r8d, r14d; Size
0x1800306ae  mov     r15d, r14d
0x1800306b1  mov     rcx, [rcx+30h]; HeapHandle
0x1800306b5  call    cs:__imp_RtlAllocateHeap
0x1800306bc  nop     dword ptr [rax+rax+00h]
0x1800306c1  mov     rbx, rax
0x1800306c4  test    rax, rax
0x1800306c7  jnz     short loc_1800306D0
0x1800306c9  mov     ebx, 0C000009Ah
0x1800306ce  jmp     short loc_18003074F
0x1800306d0  mov     r8, r15; Size
0x1800306d3  xor     edx, edx; Val
0x1800306d5  mov     rcx, rbx; void *
0x1800306d8  call    memset_0
0x1800306dd  mov     edx, 5
0x1800306e2  mov     [rbx], r13d
0x1800306e5  mov     [rbx+10h], edx
0x1800306e8  lea     eax, [rsi+54h]
0x1800306eb  mov     [rbx+1Ch], rdx
0x1800306ef  mov     r8, rsi; Size
0x1800306f2  mov     [rbx+18h], eax
0x1800306f5  lea     ecx, [rdx-4]
0x1800306f8  mov     [rbx+8], r14d
0x1800306fc  mov     [rbx+14h], ecx
0x1800306ff  mov     dword ptr [rbx+28h], 48h ; 'H'
0x180030706  mov     dword ptr [rbx+24h], 10h
0x18003070d  mov     dword ptr [rbx+30h], 3
0x180030714  mov     rax, [rbp+57h+var_50]
0x180030718  shl     rax, 0Ch
0x18003071c  mov     [rbx+34h], rax
0x180030720  mov     rax, [rbp+57h+var_60]
0x180030724  mov     [rbx+3Ch], rax
0x180030728  mov     eax, [rbp+57h+var_58]
0x18003072b  mov     [rbx+48h], ecx
0x18003072e  lea     rcx, [rbx+68h]; void *
0x180030732  mov     [rbx+50h], edx
0x180030735  lea     rdx, [rdi+6Ah]; Src
0x180030739  mov     [rbx+44h], eax
0x18003073c  mov     dword ptr [rbx+4Ch], 0Ch
0x180030743  call    memcpy_0
0x180030748  mov     [r12], rbx
0x18003074c  mov     ebx, r13d
0x18003074f  mov     eax, ebx
0x180030751  add     rsp, 0E8h
0x180030758  pop     r15
0x18003075a  pop     r14
0x18003075c  pop     r13
0x18003075e  pop     r12
0x180030760  pop     rdi
0x180030761  pop     rsi
0x180030762  pop     rbx
0x180030763  pop     rbp
0x180030764  retn
```
