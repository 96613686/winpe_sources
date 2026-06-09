# AfdRegisterSwitch

- ea: `0x1800250e0`
- end: `0x180025280`
- name: `AfdRegisterSwitch`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180044380`

## callees

- `0x18001ed78`
- `0x1800222f0`
- `0x1800250e0`

## import_xrefs

- `ntdll!NtCreateFile` at `0x1800251d3`
- `ntdll!NtCreateFile` at `0x180025252`
- `ntdll!NtCreateFile` at `0x1800251d3`
- `ntdll!NtCreateFile` at `0x180025252`
- `ntdll!RtlInitUnicodeString` at `0x180025153`
- `ntdll!RtlInitUnicodeString` at `0x180025153`

## string_xrefs

- `0x180025143`: `AfdSwOpenPacket`

## pseudocode

```c
__int64 AfdRegisterSwitch()
{
  unsigned int v0; // ebx
  unsigned __int64 v1; // rax
  __int64 v2; // rcx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp+7h] BYREF
  _DWORD EaBuffer[2]; // [rsp+B0h] [rbp+17h] BYREF
  char v8[16]; // [rsp+B8h] [rbp+1Fh] BYREF
  HANDLE v9; // [rsp+C8h] [rbp+2Fh]
  HANDLE v10; // [rsp+D0h] [rbp+37h]

  EaBuffer[1] = 1052416;
  EaBuffer[0] = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  v9 = SockAsyncQueuePort;
  *(&ObjectAttributes.Length + 1) = 0;
  v10 = SockSanEvent;
  IoStatusBlock = 0;
  DestinationString = 0;
  strcpy(v8, "AfdSwOpenPacket");
  RtlInitUnicodeString(&DestinationString, L"\\Device\\Afd\\SanHelper");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  v0 = NtCreateFile(
         &SockSanHelperHandle,
         0xC0100000,
         &ObjectAttributes,
         &IoStatusBlock,
         0,
         0,
         3u,
         3u,
         0,
         EaBuffer,
         0x2Bu);
  v1 = v0 + 1073741810;
  if ( (unsigned int)v1 <= 0x2C )
  {
    v2 = 0x104000000001LL;
    if ( _bittest64(&v2, v1) )
    {
      if ( !(unsigned int)SockDemandStartAfd() )
        return (unsigned int)NtCreateFile(
                               &SockSanHelperHandle,
                               0xC0100000,
                               &ObjectAttributes,
                               &IoStatusBlock,
                               0,
                               0,
                               3u,
                               3u,
                               0,
                               EaBuffer,
                               0x2Bu);
    }
  }
  return v0;
}

```

## disassembly

```asm
0x1800250e0  mov     [rsp-8+arg_0], rbx
0x1800250e5  push    rbp
0x1800250e6  lea     rbp, [rsp-57h]
0x1800250eb  sub     rsp, 0F0h
0x1800250f2  mov     rax, cs:__security_cookie
0x1800250f9  xor     rax, rsp
0x1800250fc  mov     [rbp+57h+var_10], rax
0x180025100  xorps   xmm0, xmm0
0x180025103  mov     [rbp+57h+var_3C], 100F00h
0x18002510a  xor     eax, eax
0x18002510c  lea     rdx, aDeviceAfdSanhe; "\\Device\\Afd\\SanHelper"
0x180025113  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180025117  mov     [rbp+57h+var_40], eax
0x18002511a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18002511e  mov     rax, cs:SockAsyncQueuePort
0x180025125  xorps   xmm1, xmm1
0x180025128  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18002512c  mov     [rbp+57h+var_28], rax
0x180025130  mov     rax, cs:SockSanEvent
0x180025137  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18002513b  mov     [rbp+57h+var_20], rax
0x18002513f  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180025143  movups  xmm0, xmmword ptr cs:aAfdswopenpacke; "AfdSwOpenPacket"
0x18002514a  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x18002514e  movdqu  [rbp+57h+var_38], xmm0
0x180025153  call    cs:__imp_RtlInitUnicodeString
0x18002515a  nop     dword ptr [rax+rax+00h]
0x18002515f  mov     [rsp+0F0h+EaLength], 2Bh ; '+'; EaLength
0x180025167  lea     rax, [rbp+57h+DestinationString]
0x18002516b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18002516f  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180025173  lea     rax, [rbp+57h+var_40]
0x180025177  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18002517e  mov     [rsp+0F0h+EaBuffer], rax; EaBuffer
0x180025183  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180025187  mov     [rsp+0F0h+CreateOptions], 0; CreateOptions
0x18002518f  lea     rcx, SockSanHelperHandle; FileHandle
0x180025196  mov     [rsp+0F0h+CreateDisposition], 3; CreateDisposition
0x18002519e  xorps   xmm0, xmm0
0x1800251a1  mov     [rsp+0F0h+ShareAccess], 3; ShareAccess
0x1800251a9  mov     edx, 0C0100000h; DesiredAccess
0x1800251ae  mov     [rsp+0F0h+FileAttributes], 0; FileAttributes
0x1800251b6  mov     [rsp+0F0h+AllocationSize], 0; AllocationSize
0x1800251bf  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800251c7  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800251ce  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800251d3  call    cs:__imp_NtCreateFile
0x1800251da  nop     dword ptr [rax+rax+00h]
0x1800251df  mov     ebx, eax
0x1800251e1  add     eax, 3FFFFFF2h
0x1800251e6  cmp     eax, 2Ch ; ','
0x1800251e9  ja      short loc_180025260
0x1800251eb  mov     rcx, 104000000001h
0x1800251f5  bt      rcx, rax
0x1800251f9  jnb     short loc_180025260
0x1800251fb  call    SockDemandStartAfd
0x180025200  test    eax, eax
0x180025202  jnz     short loc_180025260
0x180025204  mov     [rsp+0F0h+EaLength], 2Bh ; '+'; EaLength
0x18002520c  lea     rax, [rbp+57h+var_40]
0x180025210  mov     [rsp+0F0h+EaBuffer], rax; EaBuffer
0x180025215  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180025219  mov     [rsp+0F0h+CreateOptions], 0; CreateOptions
0x180025221  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180025225  mov     [rsp+0F0h+CreateDisposition], 3; CreateDisposition
0x18002522d  lea     rcx, SockSanHelperHandle; FileHandle
0x180025234  mov     [rsp+0F0h+ShareAccess], 3; ShareAccess
0x18002523c  mov     edx, 0C0100000h; DesiredAccess
0x180025241  mov     [rsp+0F0h+FileAttributes], 0; FileAttributes
0x180025249  mov     [rsp+0F0h+AllocationSize], 0; AllocationSize
0x180025252  call    cs:__imp_NtCreateFile
0x180025259  nop     dword ptr [rax+rax+00h]
0x18002525e  mov     ebx, eax
0x180025260  mov     eax, ebx
0x180025262  mov     rcx, [rbp+57h+var_10]
0x180025266  xor     rcx, rsp; StackCookie
0x180025269  call    __security_check_cookie
0x18002526e  mov     rbx, [rsp+0F0h+arg_0]
0x180025276  add     rsp, 0F0h
0x18002527d  pop     rbp
0x18002527e  retn
```
