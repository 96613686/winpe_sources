# CreateRegDomain

- ea: `0x18002819c`
- end: `0x18002830e`
- name: `CreateRegDomain`
- size: `370`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180011a20`
- `0x18001c190`
- `0x180021b90`
- `0x180021e50`
- `0x1800283b0`
- `0x180028490`
- `0x180028590`

## callees

- `0x18002819c`
- `0x180053010`

## import_xrefs

- `ntdll!NtClose` at `0x1800282e5`
- `ntdll!NtClose` at `0x1800282e5`
- `ntdll!NtCreateFile` at `0x1800282a4`
- `ntdll!NtCreateFile` at `0x1800282a4`
- `ntdll!RtlInitUnicodeString` at `0x1800281f0`
- `ntdll!RtlInitUnicodeString` at `0x1800281f0`
- `ntdll!RtlFreeHeap` at `0x1800282be`
- `ntdll!RtlFreeHeap` at `0x1800282be`

## string_xrefs

- `0x180028271`: `AfdRioRDOpenPacket`

## pseudocode

```c
HANDLE CreateRegDomain()
{
  char *EaBuffer; // rax
  char *v1; // rdi
  NTSTATUS v2; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+27h] BYREF
  void *FileHandle; // [rsp+C0h] [rbp+67h] BYREF

  FileHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  IoStatusBlock = 0;
  if ( MswRioRegDomain == (HANDLE)-1LL )
  {
    RtlInitUnicodeString(&DestinationString, L"\\Device\\Afd\\RioRegDomain");
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    EaBuffer = (char *)((__int64 (__fastcall *)(HANDLE, _QWORD, __int64))SockAllocateHeapRoutine)(
                         SockPrivateHeap,
                         0,
                         32);
    v1 = EaBuffer;
    if ( EaBuffer )
    {
      *(_DWORD *)EaBuffer = 0;
      *((_WORD *)EaBuffer + 2) = 4608;
      strcpy(EaBuffer + 8, "AfdRioRDOpenPacket");
      *((_WORD *)EaBuffer + 3) = 0;
      v2 = NtCreateFile(&FileHandle, 0xC0000000, &ObjectAttributes, &IoStatusBlock, 0, 0, 0, 3u, 0, EaBuffer, 0x20u);
      RtlFreeHeap(SockPrivateHeap, 0, v1);
      if ( v2 >= 0
        && _InterlockedCompareExchange64((volatile signed __int64 *)&MswRioRegDomain, (signed __int64)FileHandle, -1) != -1 )
      {
        NtClose(FileHandle);
      }
    }
  }
  return MswRioRegDomain;
}

```

## disassembly

```asm
0x18002819c  mov     [rsp-8+arg_8], rbx
0x1800281a1  mov     [rsp-8+arg_10], rdi
0x1800281a6  push    rbp
0x1800281a7  lea     rbp, [rsp-57h]
0x1800281ac  sub     rsp, 0B0h
0x1800281b3  xorps   xmm0, xmm0
0x1800281b6  mov     [rbp+57h+FileHandle], 0
0x1800281be  xor     eax, eax
0x1800281c0  xorps   xmm1, xmm1
0x1800281c3  cmp     cs:MswRioRegDomain, 0FFFFFFFFFFFFFFFFh
0x1800281cb  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800281cf  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800281d3  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800281d7  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800281db  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x1800281df  jnz     loc_1800282F1
0x1800281e5  lea     rdx, aDeviceAfdRiore; "\\Device\\Afd\\RioRegDomain"
0x1800281ec  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800281f0  call    cs:__imp_RtlInitUnicodeString
0x1800281f7  nop     dword ptr [rax+rax+00h]
0x1800281fc  mov     rcx, cs:SockPrivateHeap
0x180028203  lea     rax, [rbp+57h+DestinationString]
0x180028207  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18002820b  xorps   xmm0, xmm0
0x18002820e  mov     rax, cs:SockAllocateHeapRoutine
0x180028215  mov     ebx, 20h ; ' '
0x18002821a  mov     r8d, ebx
0x18002821d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180028224  xor     edx, edx
0x180028226  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18002822e  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180028235  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002823a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002823f  mov     rdi, rax
0x180028242  test    rax, rax
0x180028245  jz      loc_1800282F1
0x18002824b  mov     [rsp+0B0h+EaLength], ebx; EaLength
0x18002824f  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180028253  mov     [rsp+0B0h+EaBuffer], rdi; EaBuffer
0x180028258  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002825c  mov     dword ptr [rax], 0
0x180028262  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180028266  mov     word ptr [rax+4], 1200h
0x18002826c  mov     edx, 0C0000000h; DesiredAccess
0x180028271  movups  xmm0, xmmword ptr cs:aAfdriordopenpa; "AfdRioRDOpenPacket"
0x180028278  movups  xmmword ptr [rax+8], xmm0
0x18002827c  mov     eax, dword ptr cs:aAfdriordopenpa+0Fh; "ket"
0x180028282  mov     [rdi+17h], eax
0x180028285  xor     eax, eax
0x180028287  mov     [rsp+0B0h+CreateOptions], eax; CreateOptions
0x18002828b  mov     [rsp+0B0h+CreateDisposition], 3; CreateDisposition
0x180028293  mov     [rsp+0B0h+ShareAccess], eax; ShareAccess
0x180028297  mov     [rsp+0B0h+FileAttributes], eax; FileAttributes
0x18002829b  mov     [rsp+0B0h+AllocationSize], rax; AllocationSize
0x1800282a0  mov     [rdi+6], ax
0x1800282a4  call    cs:__imp_NtCreateFile
0x1800282ab  nop     dword ptr [rax+rax+00h]
0x1800282b0  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x1800282b7  mov     r8, rdi; P
0x1800282ba  xor     edx, edx; Flags
0x1800282bc  mov     ebx, eax
0x1800282be  call    cs:__imp_RtlFreeHeap
0x1800282c5  nop     dword ptr [rax+rax+00h]
0x1800282ca  test    ebx, ebx
0x1800282cc  js      short loc_1800282F1
0x1800282ce  mov     rcx, [rbp+57h+FileHandle]
0x1800282d2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800282d6  lock cmpxchg cs:MswRioRegDomain, rcx
0x1800282df  jz      short loc_1800282F1
0x1800282e1  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800282e5  call    cs:__imp_NtClose
0x1800282ec  nop     dword ptr [rax+rax+00h]
0x1800282f1  mov     rax, cs:MswRioRegDomain
0x1800282f8  lea     r11, [rsp+0B0h+var_s0]
0x180028300  mov     rbx, [r11+18h]
0x180028304  mov     rdi, [r11+20h]
0x180028308  mov     rsp, r11
0x18002830b  pop     rbp
0x18002830c  retn
```
