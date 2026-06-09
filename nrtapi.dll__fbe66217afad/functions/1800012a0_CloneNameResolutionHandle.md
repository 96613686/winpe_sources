# CloneNameResolutionHandle

- ea: `0x1800012a0`
- end: `0x180001419`
- name: `CloneNameResolutionHandle`
- size: `377`
- prototype: `__int64 __fastcall(PHANDLE FileHandle, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800012a0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800013fe`
- `ntdll!RtlFreeHeap` at `0x1800013fe`
- `ntdll!RtlInitUnicodeString` at `0x180001359`
- `ntdll!RtlInitUnicodeString` at `0x180001359`
- `ntdll!RtlAllocateHeap` at `0x1800012e6`
- `ntdll!RtlAllocateHeap` at `0x1800012e6`
- `ntdll!NtCreateFile` at `0x1800013ce`
- `ntdll!NtCreateFile` at `0x1800013ce`

## string_xrefs

- `0x18000133b`: `NrtCloneOpenPacket`

## pseudocode

```c
__int64 __fastcall CloneNameResolutionHandle(PHANDLE FileHandle, __int64 a2)
{
  char *Heap; // rax
  void *EaBuffer; // rbx
  NTSTATUS v6; // edi
  _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-19h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-9h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+7h] BYREF

  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  IoStatusBlock = 0;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x26u);
  EaBuffer = Heap;
  if ( Heap )
  {
    *(_QWORD *)(Heap + 6) = 0;
    *(_QWORD *)(Heap + 14) = 0;
    *(_QWORD *)(Heap + 22) = 0;
    *(_QWORD *)(Heap + 30) = 0;
    *(_DWORD *)Heap = 0;
    *((_WORD *)Heap + 2) = 4608;
    strcpy(Heap + 8, "NrtCloneOpenPacket");
    *((_WORD *)Heap + 3) = 8;
    *(_QWORD *)(Heap + 27) = a2;
    RtlInitUnicodeString(&DestinationString, L"\\Device\\NameResTrk\\Record");
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v6 = NtCreateFile(FileHandle, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 0, 0, 3u, 3u, 0, EaBuffer, 0x26u);
    if ( v6 >= 0 )
    {
LABEL_5:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, EaBuffer);
      return (unsigned int)v6;
    }
  }
  else
  {
    v6 = -1073741670;
  }
  *FileHandle = 0;
  if ( EaBuffer )
    goto LABEL_5;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800012a0  push    rbp
0x1800012a2  push    rbx
0x1800012a3  push    rsi
0x1800012a4  push    rdi
0x1800012a5  lea     rbp, [rsp-3Fh]
0x1800012aa  sub     rsp, 0B8h
0x1800012b1  xorps   xmm0, xmm0
0x1800012b4  mov     rsi, rcx
0x1800012b7  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800012bb  xor     eax, eax
0x1800012bd  mov     rdi, rdx
0x1800012c0  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800012c4  xor     edx, edx; Flags
0x1800012c6  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800012ca  lea     r8d, [rax+26h]; Size
0x1800012ce  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800012d2  xorps   xmm1, xmm1
0x1800012d5  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x1800012d9  mov     rcx, gs:60h
0x1800012e2  mov     rcx, [rcx+30h]; HeapHandle
0x1800012e6  call    cs:__imp_RtlAllocateHeap
0x1800012ed  nop     dword ptr [rax+rax+00h]
0x1800012f2  mov     rbx, rax
0x1800012f5  test    rax, rax
0x1800012f8  jnz     short loc_180001304
0x1800012fa  mov     edi, 0C000009Ah
0x1800012ff  jmp     loc_1800013E0
0x180001304  mov     qword ptr [rax+6], 0
0x18000130c  lea     rdx, SourceString; "\\Device\\NameResTrk\\Record"
0x180001313  mov     qword ptr [rax+0Eh], 0
0x18000131b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000131f  mov     qword ptr [rax+16h], 0
0x180001327  mov     qword ptr [rax+1Eh], 0
0x18000132f  mov     dword ptr [rax], 0
0x180001335  mov     word ptr [rax+4], 1200h
0x18000133b  movups  xmm0, xmmword ptr cs:aNrtcloneopenpa; "NrtCloneOpenPacket"
0x180001342  movups  xmmword ptr [rax+8], xmm0
0x180001346  mov     eax, dword ptr cs:aNrtcloneopenpa+0Fh; "ket"
0x18000134c  mov     [rbx+17h], eax
0x18000134f  mov     word ptr [rbx+6], 8
0x180001355  mov     [rbx+1Bh], rdi
0x180001359  call    cs:__imp_RtlInitUnicodeString
0x180001360  nop     dword ptr [rax+rax+00h]
0x180001365  mov     [rsp+0D0h+EaLength], 26h ; '&'; EaLength
0x18000136d  lea     rax, [rbp+57h+DestinationString]
0x180001371  mov     [rsp+0D0h+EaBuffer], rbx; EaBuffer
0x180001376  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000137a  mov     [rsp+0D0h+CreateOptions], 0; CreateOptions
0x180001382  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180001386  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000138a  xorps   xmm0, xmm0
0x18000138d  mov     eax, 3
0x180001392  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180001399  mov     [rsp+0D0h+CreateDisposition], eax; CreateDisposition
0x18000139d  mov     edx, 0C0100000h; DesiredAccess
0x1800013a2  mov     [rsp+0D0h+ShareAccess], eax; ShareAccess
0x1800013a6  mov     rcx, rsi; FileHandle
0x1800013a9  mov     [rsp+0D0h+FileAttributes], 0; FileAttributes
0x1800013b1  mov     [rsp+0D0h+AllocationSize], 0; AllocationSize
0x1800013ba  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800013c2  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800013c9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800013ce  call    cs:__imp_NtCreateFile
0x1800013d5  nop     dword ptr [rax+rax+00h]
0x1800013da  mov     edi, eax
0x1800013dc  test    eax, eax
0x1800013de  jns     short loc_1800013EC
0x1800013e0  mov     qword ptr [rsi], 0
0x1800013e7  test    rbx, rbx
0x1800013ea  jz      short loc_18000140A
0x1800013ec  mov     rcx, gs:60h
0x1800013f5  mov     r8, rbx; P
0x1800013f8  xor     edx, edx; Flags
0x1800013fa  mov     rcx, [rcx+30h]; HeapHandle
0x1800013fe  call    cs:__imp_RtlFreeHeap
0x180001405  nop     dword ptr [rax+rax+00h]
0x18000140a  mov     eax, edi
0x18000140c  add     rsp, 0B8h
0x180001413  pop     rdi
0x180001414  pop     rsi
0x180001415  pop     rbx
0x180001416  pop     rbp
0x180001417  retn
```
