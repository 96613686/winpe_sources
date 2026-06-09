# WaitNamedPipeW

- ea: `0x1800b1980`
- end: `0x1800b1e07`
- name: `WaitNamedPipeW`
- size: `1159`
- prototype: `BOOL __stdcall(LPCWSTR lpNamedPipeName, DWORD nTimeOut)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800b1520`

## callees

- `0x18004b9d0`
- `0x1800b1980`
- `0x180194eb9`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800b1ba6`
- `ntdll!RtlFreeUnicodeString` at `0x1800b1c54`
- `ntdll!RtlFreeUnicodeString` at `0x1800b1cb7`
- `ntdll!RtlFreeUnicodeString` at `0x1800b1cdb`
- `ntdll!RtlFreeUnicodeString` at `0x1800b1d87`
- `ntdll!RtlFreeUnicodeString` at `0x1800b1ba6`
- `ntdll!RtlFreeUnicodeString` at `0x1800b1c54`
- `ntdll!RtlFreeUnicodeString` at `0x1800b1cb7`
- `ntdll!RtlFreeUnicodeString` at `0x1800b1cdb`
- `ntdll!RtlFreeUnicodeString` at `0x1800b1d87`
- `ntdll!RtlInitUnicodeString` at `0x1800b1a68`
- `ntdll!RtlInitUnicodeString` at `0x1800b1aaf`
- `ntdll!RtlInitUnicodeString` at `0x1800b1a68`
- `ntdll!RtlInitUnicodeString` at `0x1800b1aaf`
- `ntdll!NtOpenFile` at `0x1800b1afb`
- `ntdll!NtOpenFile` at `0x1800b1afb`
- `ntdll!NtFsControlFile` at `0x1800b1be2`
- `ntdll!NtFsControlFile` at `0x1800b1be2`
- `ntdll!_wcsnicmp` at `0x1800b1cfd`
- `ntdll!_wcsnicmp` at `0x1800b1cfd`
- `ntdll!RtlSetLastWin32Error` at `0x1800b1c75`
- `ntdll!RtlSetLastWin32Error` at `0x1800b1d68`
- `ntdll!RtlSetLastWin32Error` at `0x1800b1df4`
- `ntdll!RtlSetLastWin32Error` at `0x1800b1c75`
- `ntdll!RtlSetLastWin32Error` at `0x1800b1d68`
- `ntdll!RtlSetLastWin32Error` at `0x1800b1df4`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x1800b1a39`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x1800b1a39`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800b1dba`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800b1dba`
- `ntdll!NtClose` at `0x1800b1c12`
- `ntdll!NtClose` at `0x1800b1c64`
- `ntdll!NtClose` at `0x1800b1c12`
- `ntdll!NtClose` at `0x1800b1c64`
- `ntdll!RtlCreateUnicodeString` at `0x1800b19d4`
- `ntdll!RtlCreateUnicodeString` at `0x1800b19d4`
- `ntdll!RtlFreeHeap` at `0x1800b1b20`
- `ntdll!RtlFreeHeap` at `0x1800b1c02`
- `ntdll!RtlFreeHeap` at `0x1800b1b20`
- `ntdll!RtlFreeHeap` at `0x1800b1c02`
- `ntdll!RtlPrefixString` at `0x1800b1a7f`
- `ntdll!RtlPrefixString` at `0x1800b1a7f`
- `ntdll!RtlAllocateHeap` at `0x1800b1b51`
- `ntdll!RtlAllocateHeap` at `0x1800b1d4b`
- `ntdll!RtlAllocateHeap` at `0x1800b1b51`
- `ntdll!RtlAllocateHeap` at `0x1800b1d4b`

## pseudocode

```c
BOOL __stdcall WaitNamedPipeW(LPCWSTR lpNamedPipeName, DWORD nTimeOut)
{
  __int64 v2; // rsi
  USHORT Length; // r8
  unsigned int v5; // eax
  __int32 v6; // eax
  const WCHAR *v7; // rdx
  struct _UNICODE_STRING *p_String2; // rcx
  WCHAR *v9; // rbx
  NTSTATUS v10; // edi
  ULONG InputBufferLength; // edi
  _DWORD *v12; // rax
  _DWORD *InputBuffer; // rbx
  char v14; // al
  __int64 v15; // rcx
  PCHAR v17; // rbx
  __int16 i; // ax
  PCHAR v19; // rdi
  USHORT v20; // cx
  WCHAR *Heap; // rax
  STRING String2; // [rsp+50h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-39h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+70h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-19h] BYREF
  struct _UNICODE_STRING v26; // [rsp+B0h] [rbp+17h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp+27h] BYREF
  struct _IO_STATUS_BLOCK v28; // [rsp+D0h] [rbp+37h] BYREF
  HANDLE FileHandle; // [rsp+110h] [rbp+77h] BYREF

  v2 = nTimeOut;
  FileHandle = 0;
  v28 = 0;
  memset(&ObjectAttributes, 0, 44);
  Destination = 0;
  String2 = 0;
  DestinationString = 0;
  v26 = 0;
  IoStatusBlock = 0;
  if ( !RtlCreateUnicodeString(&DestinationString, lpNamedPipeName) )
  {
    RtlSetLastWin32Error(8u);
    return 0;
  }
  Length = DestinationString.Length;
  v5 = 0;
  if ( (DestinationString.Length & 0xFFFE) != 0 )
  {
    do
    {
      if ( DestinationString.Buffer[v5] == 47 )
      {
        DestinationString.Buffer[v5] = 92;
        Length = DestinationString.Length;
      }
      ++v5;
    }
    while ( v5 < Length >> 1 );
  }
  String2 = (STRING)DestinationString;
  v6 = RtlDetermineDosPathNameType_U(lpNamedPipeName) - 1;
  if ( !v6 )
  {
    v17 = String2.Buffer + 4;
    for ( i = *((_WORD *)String2.Buffer + 2); i; v17 += 2 )
    {
      if ( i == 92 )
        break;
      i = *((_WORD *)v17 + 1);
    }
    if ( !*(_WORD *)v17 || _wcsnicmp((const wchar_t *)v17 + 1, L"pipe\\", 5u) )
      goto LABEL_27;
    v19 = v17 + 10;
    v20 = (_WORD)v17 + 10 - (LOWORD(String2.Buffer) + 4);
    String2.Buffer += 4;
    String2.Length = v20;
    String2.MaximumLength = v20;
    Destination.MaximumLength = v20 + 34;
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, (unsigned __int16)(v20 + 34));
    Destination.Buffer = Heap;
    v9 = Heap;
    if ( Heap )
    {
      *(_OWORD *)Heap = *(_OWORD *)L"\\DosDevices\\UNC\\";
      *((_OWORD *)Heap + 1) = *(_OWORD *)L"ces\\UNC\\";
      Destination.Length = 32;
      RtlAppendUnicodeStringToString(&Destination, (PCUNICODE_STRING)&String2);
      v7 = (const WCHAR *)(v19 + 2);
      p_String2 = (struct _UNICODE_STRING *)&String2;
      goto LABEL_10;
    }
    RtlSetLastWin32Error(8u);
LABEL_29:
    RtlFreeUnicodeString(&DestinationString);
    return 0;
  }
  if ( v6 != 5 )
  {
    BaseSetLastNTError(3221225531LL);
    goto LABEL_29;
  }
  RtlInitUnicodeString(&v26, L"\\\\.\\pipe\\");
  if ( !RtlPrefixString((const STRING *)&v26, &String2, 1u) )
  {
LABEL_27:
    RtlFreeUnicodeString(&DestinationString);
    v15 = 3221225531LL;
    goto LABEL_20;
  }
  String2.Buffer += 18;
  v7 = L"\\DosDevices\\pipe\\";
  p_String2 = &Destination;
  String2.Length -= 18;
  v9 = 0;
LABEL_10:
  RtlInitUnicodeString(p_String2, v7);
  ObjectAttributes.ObjectName = &Destination;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v10 = NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  if ( v9 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  if ( v10 < 0 )
  {
    RtlFreeUnicodeString(&DestinationString);
LABEL_19:
    v15 = (unsigned int)v10;
LABEL_20:
    BaseSetLastNTError(v15);
    return 0;
  }
  InputBufferLength = String2.Length + 14;
  v12 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, InputBufferLength);
  InputBuffer = v12;
  if ( !v12 )
  {
    RtlFreeUnicodeString(&DestinationString);
    NtClose(FileHandle);
    RtlSetLastWin32Error(8u);
    return 0;
  }
  if ( (_DWORD)v2 )
  {
    if ( (_DWORD)v2 == -1 )
    {
      *v12 = 0;
      v12[1] = 0x80000000;
    }
    else
    {
      *(_QWORD *)v12 = -10000 * v2;
    }
    v14 = 1;
  }
  else
  {
    *(_QWORD *)v12 = 0;
    v14 = 0;
  }
  *((_BYTE *)InputBuffer + 12) = v14;
  InputBuffer[2] = String2.Length;
  memcpy_0((char *)InputBuffer + 14, String2.Buffer, String2.Length);
  RtlFreeUnicodeString(&DestinationString);
  v10 = NtFsControlFile(FileHandle, 0, 0, 0, &v28, 0x110018u, InputBuffer, InputBufferLength, 0, 0);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, InputBuffer);
  NtClose(FileHandle);
  if ( v10 < 0 )
    goto LABEL_19;
  return 1;
}

```

## disassembly

```asm
0x1800b1980  mov     [rsp-8+arg_18], rbx
0x1800b1985  push    rbp
0x1800b1986  push    rsi
0x1800b1987  push    r15
0x1800b1989  lea     rbp, [rsp-47h]
0x1800b198e  sub     rsp, 0E0h
0x1800b1995  xorps   xmm0, xmm0
0x1800b1998  mov     esi, edx
0x1800b199a  xorps   xmm1, xmm1
0x1800b199d  mov     rdx, rcx; SourceString
0x1800b19a0  mov     rbx, rcx
0x1800b19a3  xor     r15d, r15d
0x1800b19a6  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800b19aa  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800b19ae  mov     [rbp+57h+FileHandle], r15
0x1800b19b2  xor     eax, eax
0x1800b19b4  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800b19b8  movups  xmmword ptr [rbp+57h+var_20], xmm0
0x1800b19bc  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800b19c0  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x1800b19c4  movups  xmmword ptr [rbp+57h+String2.Length], xmm1
0x1800b19c8  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800b19cc  movups  xmmword ptr [rbp+57h+var_40.Length], xmm1
0x1800b19d0  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800b19d4  call    cs:__imp_RtlCreateUnicodeString
0x1800b19db  nop     dword ptr [rax+rax+00h]
0x1800b19e0  test    al, al
0x1800b19e2  jz      loc_1800B1DEF
0x1800b19e8  movzx   r8d, [rbp+57h+DestinationString.Length]
0x1800b19ed  mov     eax, r15d
0x1800b19f0  mov     [rsp+0F0h+arg_8], r14
0x1800b19f8  test    r8d, 0FFFFFFFEh
0x1800b19ff  jbe     short loc_1800B1A25
0x1800b1a01  mov     rcx, [rbp+57h+DestinationString.Buffer]
0x1800b1a05  mov     edx, eax
0x1800b1a07  cmp     word ptr [rcx+rdx*2], 2Fh ; '/'
0x1800b1a0c  jnz     short loc_1800B1A19
0x1800b1a0e  mov     word ptr [rcx+rdx*2], 5Ch ; '\'
0x1800b1a14  movzx   r8d, [rbp+57h+DestinationString.Length]
0x1800b1a19  movzx   ecx, r8w
0x1800b1a1d  inc     eax
0x1800b1a1f  shr     ecx, 1
0x1800b1a21  cmp     eax, ecx
0x1800b1a23  jb      short loc_1800B1A01
0x1800b1a25  movaps  xmm0, xmmword ptr [rbp+57h+DestinationString.Length]
0x1800b1a29  mov     rcx, rbx; Path
0x1800b1a2c  movdqa  xmmword ptr [rbp+57h+String2.Length], xmm0
0x1800b1a31  mov     [rsp+0F0h+arg_0], rdi
0x1800b1a39  call    cs:__imp_RtlDetermineDosPathNameType_U
0x1800b1a40  nop     dword ptr [rax+rax+00h]
0x1800b1a45  mov     r14d, 20h ; ' '
0x1800b1a4b  sub     eax, 1
0x1800b1a4e  jz      loc_1800B1C99
0x1800b1a54  cmp     eax, 5
0x1800b1a57  jnz     loc_1800B1CCD
0x1800b1a5d  lea     rdx, aPipe; "\\\\.\\pipe\\"
0x1800b1a64  lea     rcx, [rbp+57h+var_40]; DestinationString
0x1800b1a68  call    cs:__imp_RtlInitUnicodeString
0x1800b1a6f  nop     dword ptr [rax+rax+00h]
0x1800b1a74  mov     r8b, 1; CaseInsensitive
0x1800b1a77  lea     rdx, [rbp+57h+String2]; String2
0x1800b1a7b  lea     rcx, [rbp+57h+var_40]; String1
0x1800b1a7f  call    cs:__imp_RtlPrefixString
0x1800b1a86  nop     dword ptr [rax+rax+00h]
0x1800b1a8b  test    al, al
0x1800b1a8d  jz      loc_1800B1CB3
0x1800b1a93  add     [rbp+57h+String2.Buffer], 12h
0x1800b1a98  lea     rdx, aDosdevicesPipe; "\\DosDevices\\pipe\\"
0x1800b1a9f  mov     eax, 0FFEEh
0x1800b1aa4  lea     rcx, [rbp+57h+Destination]; DestinationString
0x1800b1aa8  add     [rbp+57h+String2.Length], ax
0x1800b1aac  mov     rbx, r15
0x1800b1aaf  call    cs:__imp_RtlInitUnicodeString
0x1800b1ab6  nop     dword ptr [rax+rax+00h]
0x1800b1abb  lea     rax, [rbp+57h+Destination]
0x1800b1abf  mov     [rsp+0F0h+OpenOptions], r14d; OpenOptions
0x1800b1ac4  xorps   xmm0, xmm0
0x1800b1ac7  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800b1acb  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800b1acf  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800b1ad6  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800b1ada  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x1800b1ade  mov     edx, 100080h; DesiredAccess
0x1800b1ae3  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800b1aea  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800b1aee  mov     [rsp+0F0h+ShareAccess], 3; ShareAccess
0x1800b1af6  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800b1afb  call    cs:__imp_NtOpenFile
0x1800b1b02  nop     dword ptr [rax+rax+00h]
0x1800b1b07  mov     edi, eax
0x1800b1b09  test    rbx, rbx
0x1800b1b0c  jz      short loc_1800B1B2C
0x1800b1b0e  mov     rcx, gs:60h
0x1800b1b17  mov     r8, rbx; P
0x1800b1b1a  xor     edx, edx; Flags
0x1800b1b1c  mov     rcx, [rcx+30h]; HeapHandle
0x1800b1b20  call    cs:__imp_RtlFreeHeap
0x1800b1b27  nop     dword ptr [rax+rax+00h]
0x1800b1b2c  test    edi, edi
0x1800b1b2e  js      loc_1800B1D83
0x1800b1b34  mov     rcx, gs:60h
0x1800b1b3d  movzx   edi, [rbp+57h+String2.Length]
0x1800b1b41  mov     edx, cs:KernelBaseGlobalData; Flags
0x1800b1b47  add     edi, 0Eh
0x1800b1b4a  mov     r8d, edi; Size
0x1800b1b4d  mov     rcx, [rcx+30h]; HeapHandle
0x1800b1b51  call    cs:__imp_RtlAllocateHeap
0x1800b1b58  nop     dword ptr [rax+rax+00h]
0x1800b1b5d  mov     rbx, rax
0x1800b1b60  test    rax, rax
0x1800b1b63  jz      loc_1800B1C50
0x1800b1b69  test    esi, esi
0x1800b1b6b  jz      loc_1800B1D79
0x1800b1b71  cmp     esi, 0FFFFFFFFh
0x1800b1b74  jz      loc_1800B1C8A
0x1800b1b7a  imul    rcx, rsi, 0FFFFFFFFFFFFD8F0h
0x1800b1b81  mov     [rax], rcx
0x1800b1b84  mov     al, 1
0x1800b1b86  mov     [rbx+0Ch], al
0x1800b1b89  lea     rcx, [rbx+0Eh]; void *
0x1800b1b8d  movzx   eax, [rbp+57h+String2.Length]
0x1800b1b91  mov     [rbx+8], eax
0x1800b1b94  movzx   r8d, [rbp+57h+String2.Length]; Size
0x1800b1b99  mov     rdx, [rbp+57h+String2.Buffer]; Src
0x1800b1b9d  call    memcpy_0
0x1800b1ba2  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x1800b1ba6  call    cs:__imp_RtlFreeUnicodeString
0x1800b1bad  nop     dword ptr [rax+rax+00h]
0x1800b1bb2  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800b1bb6  lea     rax, [rbp+57h+var_20]
0x1800b1bba  mov     [rsp+0F0h+OutputBufferLength], r15d; OutputBufferLength
0x1800b1bbf  xor     r9d, r9d; ApcContext
0x1800b1bc2  mov     [rsp+0F0h+OutputBuffer], r15; OutputBuffer
0x1800b1bc7  xor     r8d, r8d; ApcRoutine
0x1800b1bca  mov     [rsp+0F0h+InputBufferLength], edi; InputBufferLength
0x1800b1bce  xor     edx, edx; Event
0x1800b1bd0  mov     [rsp+0F0h+InputBuffer], rbx; InputBuffer
0x1800b1bd5  mov     [rsp+0F0h+OpenOptions], 110018h; FsControlCode
0x1800b1bdd  mov     qword ptr [rsp+0F0h+ShareAccess], rax; IoStatusBlock
0x1800b1be2  call    cs:__imp_NtFsControlFile
0x1800b1be9  nop     dword ptr [rax+rax+00h]
0x1800b1bee  mov     rcx, gs:60h
0x1800b1bf7  mov     r8, rbx; P
0x1800b1bfa  xor     edx, edx; Flags
0x1800b1bfc  mov     edi, eax
0x1800b1bfe  mov     rcx, [rcx+30h]; HeapHandle
0x1800b1c02  call    cs:__imp_RtlFreeHeap
0x1800b1c09  nop     dword ptr [rax+rax+00h]
0x1800b1c0e  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800b1c12  call    cs:__imp_NtClose
0x1800b1c19  nop     dword ptr [rax+rax+00h]
0x1800b1c1e  test    edi, edi
0x1800b1c20  jns     short loc_1800B1C83
0x1800b1c22  mov     ecx, edi
0x1800b1c24  call    BaseSetLastNTError
0x1800b1c29  xor     eax, eax
0x1800b1c2b  mov     rdi, [rsp+0F0h+arg_0]
0x1800b1c33  mov     r14, [rsp+0F0h+arg_8]
0x1800b1c3b  mov     rbx, [rsp+0F0h+arg_18]
0x1800b1c43  add     rsp, 0E0h
0x1800b1c4a  pop     r15
0x1800b1c4c  pop     rsi
0x1800b1c4d  pop     rbp
0x1800b1c4e  retn
0x1800b1c50  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x1800b1c54  call    cs:__imp_RtlFreeUnicodeString
0x1800b1c5b  nop     dword ptr [rax+rax+00h]
0x1800b1c60  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800b1c64  call    cs:__imp_NtClose
0x1800b1c6b  nop     dword ptr [rax+rax+00h]
0x1800b1c70  mov     ecx, 8; LastError
0x1800b1c75  call    cs:__imp_RtlSetLastWin32Error
0x1800b1c7c  nop     dword ptr [rax+rax+00h]
0x1800b1c81  jmp     short loc_1800B1C29
0x1800b1c83  mov     eax, 1
0x1800b1c88  jmp     short loc_1800B1C2B
0x1800b1c8a  mov     [rax], r15d
0x1800b1c8d  mov     dword ptr [rax+4], 80000000h
0x1800b1c94  jmp     loc_1800B1B84
0x1800b1c99  mov     rbx, [rbp+57h+String2.Buffer]
0x1800b1c9d  add     rbx, 4
0x1800b1ca1  movzx   eax, word ptr [rbx]
0x1800b1ca4  test    ax, ax
0x1800b1ca7  jnz     loc_1800B1DD3
0x1800b1cad  cmp     [rbx], r15w
0x1800b1cb1  jnz     short loc_1800B1CEC
0x1800b1cb3  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x1800b1cb7  call    cs:__imp_RtlFreeUnicodeString
0x1800b1cbe  nop     dword ptr [rax+rax+00h]
0x1800b1cc3  mov     ecx, 0C000003Bh
0x1800b1cc8  jmp     loc_1800B1C24
0x1800b1ccd  mov     ecx, 0C000003Bh
0x1800b1cd2  call    BaseSetLastNTError
0x1800b1cd7  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x1800b1cdb  call    cs:__imp_RtlFreeUnicodeString
0x1800b1ce2  nop     dword ptr [rax+rax+00h]
0x1800b1ce7  jmp     loc_1800B1C29
0x1800b1cec  lea     rcx, [rbx+2]; String1
0x1800b1cf0  mov     r8d, 5; MaxCount
0x1800b1cf6  lea     rdx, aPipe_0; "pipe\\"
0x1800b1cfd  call    cs:__imp__wcsnicmp
0x1800b1d04  nop     dword ptr [rax+rax+00h]
0x1800b1d09  test    eax, eax
0x1800b1d0b  jnz     short loc_1800B1CB3
0x1800b1d0d  mov     rax, [rbp+57h+String2.Buffer]
0x1800b1d11  lea     rdi, [rbx+0Ah]
0x1800b1d15  add     rax, 4
0x1800b1d19  movzx   ecx, di
0x1800b1d1c  sub     cx, ax
0x1800b1d1f  mov     [rbp+57h+String2.Buffer], rax
0x1800b1d23  mov     [rbp+57h+String2.Length], cx
0x1800b1d27  mov     [rbp+57h+String2.MaximumLength], cx
0x1800b1d2b  add     cx, 22h ; '"'
0x1800b1d2f  movzx   r8d, cx; Size
0x1800b1d33  mov     [rbp+57h+Destination.MaximumLength], r8w
0x1800b1d38  mov     rcx, gs:60h
0x1800b1d41  mov     edx, cs:KernelBaseGlobalData; Flags
0x1800b1d47  mov     rcx, [rcx+30h]; HeapHandle
0x1800b1d4b  call    cs:__imp_RtlAllocateHeap
0x1800b1d52  nop     dword ptr [rax+rax+00h]
0x1800b1d57  mov     [rbp+57h+Destination.Buffer], rax
0x1800b1d5b  mov     rbx, rax
0x1800b1d5e  test    rax, rax
0x1800b1d61  jnz     short loc_1800B1D98
0x1800b1d63  mov     ecx, 8; LastError
0x1800b1d68  call    cs:__imp_RtlSetLastWin32Error
0x1800b1d6f  nop     dword ptr [rax+rax+00h]
0x1800b1d74  jmp     loc_1800B1CD7
0x1800b1d79  mov     [rax], r15
0x1800b1d7c  xor     al, al
0x1800b1d7e  jmp     loc_1800B1B86
0x1800b1d83  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x1800b1d87  call    cs:__imp_RtlFreeUnicodeString
0x1800b1d8e  nop     dword ptr [rax+rax+00h]
0x1800b1d93  jmp     loc_1800B1C22
0x1800b1d98  movups  xmm0, xmmword ptr cs:aDosdevicesUnc; "\\DosDevices\\UNC\\"
0x1800b1d9f  lea     rdx, [rbp+57h+String2]; Source
0x1800b1da3  lea     rcx, [rbp+57h+Destination]; Destination
0x1800b1da7  movups  xmmword ptr [rax], xmm0
0x1800b1daa  movups  xmm1, xmmword ptr cs:aDosdevicesUnc+10h; "ces\\UNC\\"
0x1800b1db1  movups  xmmword ptr [rax+10h], xmm1
0x1800b1db5  mov     [rbp+57h+Destination.Length], r14w
0x1800b1dba  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800b1dc1  nop     dword ptr [rax+rax+00h]
0x1800b1dc6  lea     rdx, [rdi+2]
0x1800b1dca  lea     rcx, [rbp+57h+String2]
0x1800b1dce  jmp     loc_1800B1AAF
0x1800b1dd3  cmp     ax, 5Ch ; '\'
0x1800b1dd7  jz      loc_1800B1CAD
0x1800b1ddd  movzx   eax, word ptr [rbx+2]
0x1800b1de1  add     rbx, 2
0x1800b1de5  test    ax, ax
0x1800b1de8  jnz     short loc_1800B1DD3
0x1800b1dea  jmp     loc_1800B1CAD
0x1800b1def  mov     ecx, 8; LastError
0x1800b1df4  call    cs:__imp_RtlSetLastWin32Error
0x1800b1dfb  nop     dword ptr [rax+rax+00h]
0x1800b1e00  xor     eax, eax
0x1800b1e02  jmp     loc_1800B1C3B
```
