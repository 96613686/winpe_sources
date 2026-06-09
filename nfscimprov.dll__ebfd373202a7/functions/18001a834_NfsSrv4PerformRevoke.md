# NfsSrv4PerformRevoke

- ea: `0x18001a834`
- end: `0x18001a9ab`
- name: `NfsSrv4PerformRevoke`
- size: `375`
- prototype: `__int64 __fastcall(PCWSTR SourceString, LPCWSTR lpszResourceName)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18001b49c`
- `0x18001b544`

## callees

- `0x18001a834`
- `0x180029c30`
- `0x18002a4dc`
- `0x180035b40`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001a88d`
- `ntdll!RtlInitUnicodeString` at `0x18001a88d`
- `ntdll!RtlGUIDFromString` at `0x18001a8df`
- `ntdll!RtlGUIDFromString` at `0x18001a8df`
- `KERNEL32!GetLastError` at `0x18001a977`
- `KERNEL32!GetLastError` at `0x18001a98a`
- `KERNEL32!GetLastError` at `0x18001a977`
- `KERNEL32!GetLastError` at `0x18001a98a`
- `KERNEL32!CloseHandle` at `0x18001a982`
- `KERNEL32!CloseHandle` at `0x18001a982`
- `KERNEL32!CreateFileW` at `0x18001a92f`
- `KERNEL32!CreateFileW` at `0x18001a92f`
- `KERNEL32!DeviceIoControl` at `0x18001a96d`
- `KERNEL32!DeviceIoControl` at `0x18001a96d`

## pseudocode

```c
__int64 __fastcall NfsSrv4PerformRevoke(PCWSTR SourceString, LPCWSTR lpszResourceName, char a3)
{
  __int64 v5; // rcx
  DWORD IsClusterNode; // ebx
  DWORD ResourceIdForNetworkName; // eax
  HANDLE FileW; // rdi
  int v10; // [rsp+40h] [rbp-29h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-25h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-21h] BYREF
  _BYTE InBuffer[40]; // [rsp+58h] [rbp-11h] BYREF
  __int128 v14; // [rsp+80h] [rbp+17h] BYREF
  GUID Guid; // [rsp+90h] [rbp+27h] BYREF

  v10 = 0;
  BytesReturned = 0;
  memset(InBuffer, 0, sizeof(InBuffer));
  v14 = 0;
  Guid = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  InBuffer[36] = a3;
  IsClusterNode = NfsClusterIsClusterNode(v5, &v10);
  if ( !IsClusterNode && v10 )
  {
    ResourceIdForNetworkName = NfsClusGetResourceIdForNetworkName(lpszResourceName, (__int64)&v14);
    IsClusterNode = ResourceIdForNetworkName;
    if ( ResourceIdForNetworkName )
    {
      if ( ResourceIdForNetworkName == 1168 )
      {
        IsClusterNode = 0;
        InBuffer[16] = 1;
      }
    }
    else
    {
      InBuffer[16] = 0;
      *(_OWORD *)&InBuffer[20] = v14;
    }
  }
  if ( RtlGUIDFromString(&DestinationString, &Guid) >= 0 )
  {
    if ( !IsClusterNode )
    {
      *(GUID *)InBuffer = Guid;
      FileW = CreateFileW(L"\\\\.\\NfsSvr", 0x40000000u, 0, 0, 3u, 0x1000080u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        return GetLastError();
      }
      else
      {
        if ( !DeviceIoControl(FileW, 0x10008594u, InBuffer, 0x28u, 0, 0, &BytesReturned, 0) )
          IsClusterNode = GetLastError();
        CloseHandle(FileW);
      }
    }
  }
  else
  {
    return 13;
  }
  return IsClusterNode;
}

```

## disassembly

```asm
0x18001a834  push    rbp
0x18001a836  push    rbx
0x18001a837  push    rdi
0x18001a838  lea     rbp, [rsp-47h]
0x18001a83d  sub     rsp, 0B0h
0x18001a844  mov     rax, cs:__security_cookie
0x18001a84b  xor     rax, rsp
0x18001a84e  mov     [rbp+57h+var_20], rax
0x18001a852  xorps   xmm0, xmm0
0x18001a855  mov     [rbp+57h+var_80], 0
0x18001a85c  mov     rdi, rdx
0x18001a85f  mov     [rbp+57h+BytesReturned], 0
0x18001a866  mov     rdx, rcx; SourceString
0x18001a869  xor     eax, eax
0x18001a86b  xorps   xmm1, xmm1
0x18001a86e  mov     [rbp+57h+var_48], rax
0x18001a872  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18001a876  mov     bl, r8b
0x18001a879  movups  [rbp+57h+InBuffer], xmm0
0x18001a87d  movups  [rbp+57h+var_58], xmm0
0x18001a881  movups  [rbp+57h+var_40], xmm0
0x18001a885  movups  xmmword ptr [rbp+57h+Guid.Data1], xmm1
0x18001a889  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18001a88d  call    cs:__imp_RtlInitUnicodeString
0x18001a893  lea     rdx, [rbp+57h+var_80]
0x18001a897  mov     byte ptr [rbp+57h+var_48+4], bl
0x18001a89a  call    NfsClusterIsClusterNode
0x18001a89f  mov     ebx, eax
0x18001a8a1  test    eax, eax
0x18001a8a3  jnz     short loc_18001A8D7
0x18001a8a5  cmp     [rbp+57h+var_80], eax
0x18001a8a8  jz      short loc_18001A8D7
0x18001a8aa  lea     rdx, [rbp+57h+var_40]
0x18001a8ae  mov     rcx, rdi; lpszResourceName
0x18001a8b1  call    NfsClusGetResourceIdForNetworkName
0x18001a8b6  mov     ebx, eax
0x18001a8b8  test    eax, eax
0x18001a8ba  jnz     short loc_18001A8CA
0x18001a8bc  movups  xmm0, [rbp+57h+var_40]
0x18001a8c0  mov     byte ptr [rbp+57h+var_58], al
0x18001a8c3  movdqu  [rbp+57h+var_58+4], xmm0
0x18001a8c8  jmp     short loc_18001A8D7
0x18001a8ca  cmp     eax, 490h
0x18001a8cf  jnz     short loc_18001A8D7
0x18001a8d1  xor     ebx, ebx
0x18001a8d3  mov     byte ptr [rbp+57h+var_58], 1
0x18001a8d7  lea     rdx, [rbp+57h+Guid]; Guid
0x18001a8db  lea     rcx, [rbp+57h+DestinationString]; GuidString
0x18001a8df  call    cs:__imp_RtlGUIDFromString
0x18001a8e5  test    eax, eax
0x18001a8e7  jns     short loc_18001A8F3
0x18001a8e9  mov     ebx, 0Dh
0x18001a8ee  jmp     loc_18001A992
0x18001a8f3  test    ebx, ebx
0x18001a8f5  jnz     loc_18001A992
0x18001a8fb  movups  xmm0, xmmword ptr [rbp+57h+Guid.Data1]
0x18001a8ff  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18001a908  lea     rcx, aNfssvr; "\\\\.\\NfsSvr"
0x18001a90f  mov     [rsp+0C0h+dwFlagsAndAttributes], 1000080h; dwFlagsAndAttributes
0x18001a917  xor     r9d, r9d; lpSecurityAttributes
0x18001a91a  xor     r8d, r8d; dwShareMode
0x18001a91d  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18001a925  mov     edx, 40000000h; dwDesiredAccess
0x18001a92a  movdqu  [rbp+57h+InBuffer], xmm0
0x18001a92f  call    cs:__imp_CreateFileW
0x18001a935  mov     rdi, rax
0x18001a938  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a93c  jz      short loc_18001A98A
0x18001a93e  mov     [rsp+0C0h+lpOverlapped], 0; lpOverlapped
0x18001a947  lea     rax, [rbp+57h+BytesReturned]
0x18001a94b  mov     [rsp+0C0h+hTemplateFile], rax; lpBytesReturned
0x18001a950  lea     r9d, [rbx+28h]; nInBufferSize
0x18001a954  mov     [rsp+0C0h+dwFlagsAndAttributes], ebx; nOutBufferSize
0x18001a958  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x18001a95c  mov     edx, 10008594h; dwIoControlCode
0x18001a961  mov     qword ptr [rsp+0C0h+dwCreationDisposition], 0; lpOutBuffer
0x18001a96a  mov     rcx, rdi; hDevice
0x18001a96d  call    cs:__imp_DeviceIoControl
0x18001a973  test    eax, eax
0x18001a975  jnz     short loc_18001A97F
0x18001a977  call    cs:__imp_GetLastError
0x18001a97d  mov     ebx, eax
0x18001a97f  mov     rcx, rdi; hObject
0x18001a982  call    cs:__imp_CloseHandle
0x18001a988  jmp     short loc_18001A992
0x18001a98a  call    cs:__imp_GetLastError
0x18001a990  mov     ebx, eax
0x18001a992  mov     eax, ebx
0x18001a994  mov     rcx, [rbp+57h+var_20]
0x18001a998  xor     rcx, rsp; StackCookie
0x18001a99b  call    __security_check_cookie
0x18001a9a0  add     rsp, 0B0h
0x18001a9a7  pop     rdi
0x18001a9a8  pop     rbx
0x18001a9a9  pop     rbp
0x18001a9aa  retn
```
