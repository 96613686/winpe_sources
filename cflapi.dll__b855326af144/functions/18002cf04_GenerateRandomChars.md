# GenerateRandomChars

- ea: `0x18002cf04`
- end: `0x18002d150`
- name: `GenerateRandomChars`
- size: `588`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x18001d29c`

## callees

- `0x180002490`
- `0x18002cf04`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18002cf72`
- `ntdll!RtlInitUnicodeString` at `0x18002cf72`
- `ntdll!NtOpenFile` at `0x18002cfbf`
- `ntdll!NtOpenFile` at `0x18002cfbf`
- `ntdll!NtClose` at `0x18002d018`
- `ntdll!NtClose` at `0x18002d018`
- `ntdll!NtDeviceIoControlFile` at `0x18002d00c`
- `ntdll!NtDeviceIoControlFile` at `0x18002d00c`

## pseudocode

```c
__int64 __fastcall GenerateRandomChars(__int64 a1, unsigned int a2)
{
  NTSTATUS v4; // ebx
  unsigned int v5; // r11d
  __int64 i; // rbx
  int v7; // r10d
  void *FileHandle; // [rsp+50h] [rbp-39h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-31h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-1h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp+Fh] BYREF
  _BYTE OutputBuffer[24]; // [rsp+A8h] [rbp+1Fh] BYREF

  if ( !a1 || a2 >= 0x10 )
    return 2147942487LL;
  FileHandle = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  DestinationString = 0;
  IoStatusBlock = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\KsecDD");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  if ( NtOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x10u) < 0 )
    return (unsigned int)-2147467259;
  v4 = NtDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x390008u, 0, 0, OutputBuffer, 0x18u);
  NtClose(FileHandle);
  if ( v4 < 0 )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    v5 = 0;
    for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
    {
      v7 = 5 * i;
      *(_WORD *)(a1 + 2 * i) = a0123456789abcd[(((unsigned __int8)(1 << ((-3 * i) & 7))
                                               & OutputBuffer[(unsigned __int64)(unsigned int)(5 * i) >> 3]) != 0)
                                             | ((OutputBuffer[(unsigned __int64)(unsigned int)(v7 + 1) >> 3]
                                               & (unsigned __int8)(1 << ((1 - 3 * i) & 7))) != 0
                                              ? 2
                                              : 0)
                                             | ((OutputBuffer[(unsigned __int64)(unsigned int)(v7 + 2) >> 3]
                                               & (unsigned __int8)(1 << ((2 - 3 * i) & 7))) != 0
                                              ? 4
                                              : 0)
                                             | ((OutputBuffer[(unsigned __int64)(unsigned int)(v7 + 3) >> 3]
                                               & (unsigned __int8)(1 << ((3 - 3 * i) & 7))) != 0
                                              ? 8
                                              : 0)
                                             | (unsigned __int64)((OutputBuffer[(unsigned __int64)(unsigned int)(v7 + 4) >> 3]
                                                                 & (unsigned __int8)(1 << ((-4 - 3 * i) & 7))) != 0
                                                                ? 0x10
                                                                : 0)];
    }
    *(_WORD *)(a1 + 2LL * (a2 - 1)) = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x18002cf04  mov     [rsp-8+arg_10], rbx
0x18002cf09  mov     [rsp-8+arg_18], rsi
0x18002cf0e  push    rbp
0x18002cf0f  push    rdi
0x18002cf10  push    r12
0x18002cf12  lea     rbp, [rsp-47h]
0x18002cf17  sub     rsp, 0D0h
0x18002cf1e  mov     rax, cs:__security_cookie
0x18002cf25  xor     rax, rsp
0x18002cf28  mov     [rbp+57h+var_20], rax
0x18002cf2c  mov     edi, edx
0x18002cf2e  mov     rsi, rcx
0x18002cf31  test    rcx, rcx
0x18002cf34  jz      loc_18002D127
0x18002cf3a  cmp     edx, 10h
0x18002cf3d  jnb     loc_18002D127
0x18002cf43  xorps   xmm0, xmm0
0x18002cf46  mov     [rbp+57h+FileHandle], 0
0x18002cf4e  xorps   xmm1, xmm1
0x18002cf51  lea     rdx, SourceString; "\\Device\\KsecDD"
0x18002cf58  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18002cf5c  xor     eax, eax
0x18002cf5e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18002cf62  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18002cf66  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18002cf6a  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x18002cf6e  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18002cf72  call    cs:__imp_RtlInitUnicodeString
0x18002cf78  lea     rax, [rbp+57h+DestinationString]
0x18002cf7c  mov     [rsp+0E0h+OpenOptions], 10h; OpenOptions
0x18002cf84  xorps   xmm0, xmm0
0x18002cf87  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18002cf8b  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18002cf8f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18002cf96  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002cf9a  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18002cfa2  mov     edx, 100001h; DesiredAccess
0x18002cfa7  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18002cfae  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18002cfb2  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x18002cfba  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002cfbf  call    cs:__imp_NtOpenFile
0x18002cfc5  test    eax, eax
0x18002cfc7  js      loc_18002D11C
0x18002cfcd  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18002cfd1  lea     rax, [rbp+57h+var_38]
0x18002cfd5  mov     [rsp+0E0h+OutputBufferLength], 18h; OutputBufferLength
0x18002cfdd  xor     r9d, r9d; ApcContext
0x18002cfe0  mov     [rsp+0E0h+OutputBuffer], rax; OutputBuffer
0x18002cfe5  xor     r8d, r8d; ApcRoutine
0x18002cfe8  mov     [rsp+0E0h+InputBufferLength], 0; InputBufferLength
0x18002cff0  lea     rax, [rbp+57h+IoStatusBlock]
0x18002cff4  mov     [rsp+0E0h+InputBuffer], 0; InputBuffer
0x18002cffd  xor     edx, edx; Event
0x18002cfff  mov     [rsp+0E0h+OpenOptions], 390008h; IoControlCode
0x18002d007  mov     qword ptr [rsp+0E0h+ShareAccess], rax; IoStatusBlock
0x18002d00c  call    cs:__imp_NtDeviceIoControlFile
0x18002d012  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18002d016  mov     ebx, eax
0x18002d018  call    cs:__imp_NtClose
0x18002d01e  test    ebx, ebx
0x18002d020  js      loc_18002D11C
0x18002d026  xor     r11d, r11d
0x18002d029  xor     ebx, ebx
0x18002d02b  test    edi, edi
0x18002d02d  jz      loc_18002D111
0x18002d033  lea     r12d, [r11+1]
0x18002d037  lea     r10d, [rbx+rbx*4]
0x18002d03b  mov     ecx, 0FFFFFFFCh
0x18002d040  lea     r8d, [rbx+rbx*2]
0x18002d044  mov     edx, r12d
0x18002d047  sub     ecx, r8d
0x18002d04a  and     ecx, 7
0x18002d04d  shl     edx, cl
0x18002d04f  lea     ecx, [r10+4]
0x18002d053  shr     rcx, 3
0x18002d057  and     dl, [rbp+rcx+57h+var_38]
0x18002d05b  mov     ecx, 3
0x18002d060  neg     dl
0x18002d062  mov     edx, r12d
0x18002d065  sbb     r9, r9
0x18002d068  sub     ecx, r8d
0x18002d06b  and     ecx, 7
0x18002d06e  and     r9d, 10h
0x18002d072  shl     edx, cl
0x18002d074  lea     ecx, [r10+3]
0x18002d078  shr     rcx, 3
0x18002d07c  and     dl, [rbp+rcx+57h+var_38]
0x18002d080  mov     ecx, 2
0x18002d085  neg     dl
0x18002d087  mov     edx, r12d
0x18002d08a  sbb     rax, rax
0x18002d08d  sub     ecx, r8d
0x18002d090  and     eax, 8
0x18002d093  and     ecx, 7
0x18002d096  shl     edx, cl
0x18002d098  or      r9, rax
0x18002d09b  lea     ecx, [r10+2]
0x18002d09f  shr     rcx, 3
0x18002d0a3  and     dl, [rbp+rcx+57h+var_38]
0x18002d0a7  mov     ecx, r12d
0x18002d0aa  neg     dl
0x18002d0ac  mov     edx, r12d
0x18002d0af  sbb     rax, rax
0x18002d0b2  sub     ecx, r8d
0x18002d0b5  and     eax, 4
0x18002d0b8  and     ecx, 7
0x18002d0bb  or      r9, rax
0x18002d0be  shl     edx, cl
0x18002d0c0  lea     ecx, [r10+1]
0x18002d0c4  shr     rcx, 3
0x18002d0c8  and     dl, [rbp+rcx+57h+var_38]
0x18002d0cc  neg     dl
0x18002d0ce  mov     edx, r12d
0x18002d0d1  sbb     rax, rax
0x18002d0d4  imul    ecx, ebx, -3
0x18002d0d7  and     eax, 2
0x18002d0da  or      r9, rax
0x18002d0dd  mov     eax, r10d
0x18002d0e0  shr     rax, 3
0x18002d0e4  and     ecx, 7
0x18002d0e7  shl     edx, cl
0x18002d0e9  test    [rbp+rax+57h+var_38], dl
0x18002d0ed  mov     rax, r11
0x18002d0f0  setnz   al
0x18002d0f3  or      r9, rax
0x18002d0f6  lea     rax, a0123456789abcd; "0123456789ABCDEFGHIJKLMNOPQRSTUV"
0x18002d0fd  movzx   eax, word ptr [rax+r9*2]
0x18002d102  mov     [rsi+rbx*2], ax
0x18002d106  add     ebx, r12d
0x18002d109  cmp     ebx, edi
0x18002d10b  jb      loc_18002D037
0x18002d111  lea     ecx, [rdi-1]
0x18002d114  xor     eax, eax
0x18002d116  mov     [rsi+rcx*2], ax
0x18002d11a  jmp     short loc_18002D122
0x18002d11c  mov     r11d, 80004005h
0x18002d122  mov     eax, r11d
0x18002d125  jmp     short loc_18002D12C
0x18002d127  mov     eax, 80070057h
0x18002d12c  mov     rcx, [rbp+57h+var_20]
0x18002d130  xor     rcx, rsp; StackCookie
0x18002d133  call    __security_check_cookie
0x18002d138  lea     r11, [rsp+0E0h+var_10]
0x18002d140  mov     rbx, [r11+30h]
0x18002d144  mov     rsi, [r11+38h]
0x18002d148  mov     rsp, r11
0x18002d14b  pop     r12
0x18002d14d  pop     rdi
0x18002d14e  pop     rbp
0x18002d14f  retn
```
