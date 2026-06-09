# DeleteConnection

- ea: `0x18000b0d8`
- end: `0x18000b5f8`
- name: `DeleteConnection`
- size: `1312`
- prototype: `__int64 __fastcall(int, int, __int64, const WCHAR *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180004a40`
- `0x180005c40`

## callees

- `0x180002508`
- `0x180002538`
- `0x1800090dc`
- `0x18000b0d8`
- `0x18000c220`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x18000b402`
- `ntdll!NtFsControlFile` at `0x18000b402`
- `ntdll!NtOpenFile` at `0x18000b302`
- `ntdll!NtOpenFile` at `0x18000b302`
- `ntdll!NtClose` at `0x18000b4d3`
- `ntdll!NtClose` at `0x18000b58a`
- `ntdll!NtClose` at `0x18000b4d3`
- `ntdll!NtClose` at `0x18000b58a`
- `ntdll!RtlInitUnicodeString` at `0x18000b288`
- `ntdll!RtlInitUnicodeString` at `0x18000b288`
- `KERNEL32!CreateEventW` at `0x18000b365`
- `KERNEL32!CreateEventW` at `0x18000b365`
- `KERNEL32!WaitForSingleObject` at `0x18000b423`
- `KERNEL32!WaitForSingleObject` at `0x18000b423`
- `KERNEL32!CloseHandle` at `0x18000b4ff`
- `KERNEL32!CloseHandle` at `0x18000b59e`
- `KERNEL32!CloseHandle` at `0x18000b4ff`
- `KERNEL32!CloseHandle` at `0x18000b59e`
- `KERNEL32!GetLastError` at `0x18000b37e`
- `KERNEL32!GetLastError` at `0x18000b462`
- `KERNEL32!GetLastError` at `0x18000b37e`
- `KERNEL32!GetLastError` at `0x18000b462`
- `ADVAPI32!LsaNtStatusToWinError` at `0x18000b344`
- `ADVAPI32!LsaNtStatusToWinError` at `0x18000b4b4`
- `ADVAPI32!LsaNtStatusToWinError` at `0x18000b344`
- `ADVAPI32!LsaNtStatusToWinError` at `0x18000b4b4`
- `RPCRT4!RpcBindingFree` at `0x18000b4f0`
- `RPCRT4!RpcBindingFree` at `0x18000b5af`
- `RPCRT4!RpcBindingFree` at `0x18000b4f0`
- `RPCRT4!RpcBindingFree` at `0x18000b5af`
- `RPCRT4!NdrClientCall3` at `0x18000b20b`
- `RPCRT4!NdrClientCall3` at `0x18000b20b`

## pseudocode

```c
__int64 __fastcall DeleteConnection(int a1, int a2, __int64 a3, const WCHAR *a4, int a5)
{
  HANDLE EventW; // r15
  ULONG v7; // eax
  ULONG Pointer; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rax
  CLIENT_CALL_RETURN v11; // rax
  unsigned int v12; // eax
  int Status; // ebx
  DWORD LastError; // eax
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp-98h] BYREF
  HANDLE v17; // [rsp+68h] [rbp-90h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-88h] BYREF
  CLIENT_CALL_RETURN v19; // [rsp+80h] [rbp-78h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-70h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-60h] BYREF
  int InputBuffer; // [rsp+100h] [rbp+8h] BYREF
  int v23; // [rsp+108h] [rbp+10h]
  __int64 v24; // [rsp+110h] [rbp+18h]
  void *FileHandle; // [rsp+118h] [rbp+20h] BYREF

  v24 = a3;
  v23 = a2;
  InputBuffer = a1;
  a5 = 0;
  FileHandle = (void *)-1LL;
  Binding = 0;
  EventW = 0;
  v17 = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_7b522c97afb2341f13613538df880a66_Traceguids, a3);
  if ( a4 )
    *a4 = 0;
  v7 = RpcBindForNfsClient(&Binding);
  Pointer = v7;
  if ( v7 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return Pointer;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
LABEL_52:
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 )
        WPP_SF_d(v9[2], 20, &WPP_7b522c97afb2341f13613538df880a66_Traceguids, Pointer);
      return Pointer;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_7b522c97afb2341f13613538df880a66_Traceguids, v7);
LABEL_51:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_52;
  }
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(v24 + 2 * v10) );
  v19.Simple = 0;
  v11.Pointer = NdrClientCall3(
                  (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                  4u,
                  0,
                  Binding,
                  v23,
                  (int)v10 + 1,
                  v24,
                  260,
                  a4,
                  &a5).Pointer;
  Pointer = (ULONG)v11.Pointer;
  v19.Pointer = v11.Pointer;
  if ( LODWORD(v11.Pointer) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        &WPP_7b522c97afb2341f13613538df880a66_Traceguids,
        LODWORD(v11.Pointer));
    goto LABEL_46;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_7b522c97afb2341f13613538df880a66_Traceguids);
  RtlInitUnicodeString(&DestinationString, a4);
  DestinationString.MaximumLength -= 2;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v12 = NtOpenFile(&FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x80u);
  Status = v12;
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_7b522c97afb2341f13613538df880a66_Traceguids, v12);
LABEL_24:
    Pointer = LsaNtStatusToWinError(Status);
LABEL_46:
    if ( FileHandle != (void *)-1LL )
      NtClose(FileHandle);
    if ( EventW )
      CloseHandle(EventW);
    RpcBindingFree(&Binding);
    goto LABEL_51;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v17 = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    Pointer = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_7b522c97afb2341f13613538df880a66_Traceguids, LastError);
    goto LABEL_46;
  }
  Status = NtFsControlFile(FileHandle, EventW, 0, 0, &IoStatusBlock, 0x140948u, &InputBuffer, 4u, 0, 0);
  if ( Status == 259 )
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) == -1 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          &WPP_7b522c97afb2341f13613538df880a66_Traceguids,
          0xFFFFFFFFLL);
      Pointer = GetLastError();
      goto LABEL_46;
    }
    Status = IoStatusBlock.Status;
  }
  if ( Status < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        &WPP_7b522c97afb2341f13613538df880a66_Traceguids,
        (unsigned int)Status);
    goto LABEL_24;
  }
  NtClose(FileHandle);
  FileHandle = (void *)-1LL;
  RpcBindingFree(&Binding);
  CloseHandle(EventW);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_7b522c97afb2341f13613538df880a66_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x18000b0d8  mov     rax, rsp
0x18000b0db  mov     [rax+18h], r8
0x18000b0df  mov     [rax+10h], edx
0x18000b0e2  mov     [rax+8], ecx
0x18000b0e5  push    rbx
0x18000b0e6  push    rdi
0x18000b0e7  push    r13
0x18000b0e9  push    r14
0x18000b0eb  push    r15
0x18000b0ed  sub     rsp, 0D0h
0x18000b0f4  mov     r13, r9
0x18000b0f7  xor     edi, edi
0x18000b0f9  mov     [rax+28h], edi
0x18000b0fc  mov     qword ptr [rax+20h], 0FFFFFFFFFFFFFFFFh
0x18000b104  mov     [rsp+0F8h+Binding], rdi
0x18000b109  mov     r15d, edi
0x18000b10c  mov     [rsp+0F8h+var_90], rdi
0x18000b111  xorps   xmm0, xmm0
0x18000b114  movups  xmmword ptr [rax-70h], xmm0
0x18000b118  xor     ecx, ecx
0x18000b11a  movups  xmmword ptr [rax-60h], xmm0
0x18000b11e  movups  xmmword ptr [rax-50h], xmm0
0x18000b122  movups  xmmword ptr [rax-44h], xmm0
0x18000b126  movups  xmmword ptr [rsp+0F8h+DestinationString.Length], xmm0
0x18000b12b  lea     r14, WPP_GLOBAL_Control
0x18000b132  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b139  cmp     rcx, r14
0x18000b13c  jz      short loc_18000B15A
0x18000b13e  test    byte ptr [rcx+1Ch], 1
0x18000b142  jz      short loc_18000B15A
0x18000b144  lea     edx, [rdi+0Ah]
0x18000b147  mov     r9, r8
0x18000b14a  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000b151  mov     rcx, [rcx+10h]
0x18000b155  call    WPP_SF_S
0x18000b15a  test    r13, r13
0x18000b15d  jz      short loc_18000B164
0x18000b15f  mov     [r13+0], di
0x18000b164  lea     rcx, [rsp+0F8h+Binding]
0x18000b169  call    RpcBindForNfsClient
0x18000b16e  mov     ebx, eax
0x18000b170  test    eax, eax
0x18000b172  jz      short loc_18000B1AB
0x18000b174  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b17b  cmp     rcx, r14
0x18000b17e  jz      loc_18000B5E5
0x18000b184  test    byte ptr [rcx+1Ch], 2
0x18000b188  jz      loc_18000B5C2
0x18000b18e  mov     edx, 0Bh
0x18000b193  mov     r9d, eax
0x18000b196  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000b19d  mov     rcx, [rcx+10h]
0x18000b1a1  call    WPP_SF_d
0x18000b1a6  jmp     loc_18000B5BB
0x18000b1ab  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b1af  mov     rcx, [rsp+0F8h+arg_10]
0x18000b1b7  inc     rax
0x18000b1ba  cmp     [rcx+rax*2], di
0x18000b1be  jnz     short loc_18000B1B7
0x18000b1c0  inc     eax
0x18000b1c2  mov     [rsp+0F8h+var_78], rdi
0x18000b1ca  lea     rdx, [rsp+0F8h+arg_20]
0x18000b1d2  mov     qword ptr [rsp+0F8h+OutputBufferLength], rdx
0x18000b1d7  mov     [rsp+0F8h+OutputBuffer], r13
0x18000b1dc  mov     [rsp+0F8h+InputBufferLength], 104h
0x18000b1e4  mov     [rsp+0F8h+InputBuffer], rcx
0x18000b1e9  mov     [rsp+0F8h+OpenOptions], eax
0x18000b1ed  mov     eax, [rsp+0F8h+arg_8]
0x18000b1f4  mov     [rsp+0F8h+ShareAccess], eax
0x18000b1f8  mov     r9, [rsp+0F8h+Binding]
0x18000b1fd  xor     r8d, r8d; pReturnValue
0x18000b200  lea     edx, [r8+4]; nProcNum
0x18000b204  lea     rcx, pProxyInfo; pProxyInfo
0x18000b20b  call    cs:__imp_NdrClientCall3
0x18000b212  nop     dword ptr [rax+rax+00h]
0x18000b217  mov     rbx, rax
0x18000b21a  mov     [rsp+0F8h+var_78], rax
0x18000b222  mov     [rsp+0F8h+var_A8], eax
0x18000b226  test    eax, eax
0x18000b228  jz      short loc_18000B259
0x18000b22a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b231  cmp     rcx, r14
0x18000b234  jz      short loc_18000B254
0x18000b236  test    byte ptr [rcx+1Ch], 2
0x18000b23a  jz      short loc_18000B254
0x18000b23c  mov     edx, 0Ch
0x18000b241  mov     r9d, eax
0x18000b244  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000b24b  mov     rcx, [rcx+10h]
0x18000b24f  call    WPP_SF_d
0x18000b254  jmp     loc_18000B57C
0x18000b259  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b260  cmp     rcx, r14
0x18000b263  jz      short loc_18000B280
0x18000b265  test    byte ptr [rcx+1Ch], 1
0x18000b269  jz      short loc_18000B280
0x18000b26b  mov     edx, 0Dh
0x18000b270  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000b277  mov     rcx, [rcx+10h]
0x18000b27b  call    WPP_SF_
0x18000b280  mov     rdx, r13; SourceString
0x18000b283  lea     rcx, [rsp+0F8h+DestinationString]; DestinationString
0x18000b288  call    cs:__imp_RtlInitUnicodeString
0x18000b28f  nop     dword ptr [rax+rax+00h]
0x18000b294  mov     eax, 0FFFEh
0x18000b299  add     [rsp+0F8h+DestinationString.MaximumLength], ax
0x18000b29e  mov     [rsp+0F8h+ObjectAttributes.Length], 30h ; '0'
0x18000b2a9  mov     [rsp+0F8h+ObjectAttributes.RootDirectory], rdi
0x18000b2b1  mov     [rsp+0F8h+ObjectAttributes.Attributes], 40h ; '@'
0x18000b2bc  lea     rax, [rsp+0F8h+DestinationString]
0x18000b2c1  mov     [rsp+0F8h+ObjectAttributes.ObjectName], rax
0x18000b2c9  xorps   xmm0, xmm0
0x18000b2cc  movdqu  xmmword ptr [rsp+0F8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000b2d5  mov     [rsp+0F8h+OpenOptions], 80h; OpenOptions
0x18000b2dd  mov     [rsp+0F8h+ShareAccess], 7; ShareAccess
0x18000b2e5  lea     r9, [rsp+0F8h+IoStatusBlock]; IoStatusBlock
0x18000b2ed  lea     r8, [rsp+0F8h+ObjectAttributes]; ObjectAttributes
0x18000b2f5  mov     edx, 100000h; DesiredAccess
0x18000b2fa  lea     rcx, [rsp+0F8h+FileHandle]; FileHandle
0x18000b302  call    cs:__imp_NtOpenFile
0x18000b309  nop     dword ptr [rax+rax+00h]
0x18000b30e  mov     ebx, eax
0x18000b310  mov     [rsp+0F8h+var_A8], eax
0x18000b314  test    eax, eax
0x18000b316  jz      short loc_18000B35B
0x18000b318  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b31f  cmp     rcx, r14
0x18000b322  jz      short loc_18000B342
0x18000b324  test    byte ptr [rcx+1Ch], 2
0x18000b328  jz      short loc_18000B342
0x18000b32a  mov     edx, 0Eh
0x18000b32f  mov     r9d, eax
0x18000b332  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000b339  mov     rcx, [rcx+10h]
0x18000b33d  call    WPP_SF_d
0x18000b342  mov     ecx, ebx; Status
0x18000b344  call    cs:__imp_LsaNtStatusToWinError
0x18000b34b  nop     dword ptr [rax+rax+00h]
0x18000b350  mov     ebx, eax
0x18000b352  mov     [rsp+0F8h+var_A8], eax
0x18000b356  jmp     loc_18000B57C
0x18000b35b  xor     r9d, r9d; lpName
0x18000b35e  xor     r8d, r8d; bInitialState
0x18000b361  xor     edx, edx; bManualReset
0x18000b363  xor     ecx, ecx; lpEventAttributes
0x18000b365  call    cs:__imp_CreateEventW
0x18000b36c  nop     dword ptr [rax+rax+00h]
0x18000b371  mov     r15, rax
0x18000b374  mov     [rsp+0F8h+var_90], rax
0x18000b379  test    rax, rax
0x18000b37c  jnz     short loc_18000B3BE
0x18000b37e  call    cs:__imp_GetLastError
0x18000b385  nop     dword ptr [rax+rax+00h]
0x18000b38a  mov     ebx, eax
0x18000b38c  mov     [rsp+0F8h+var_A8], eax
0x18000b390  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b397  cmp     rcx, r14
0x18000b39a  jz      short loc_18000B3B9
0x18000b39c  test    byte ptr [rcx+1Ch], 2
0x18000b3a0  jz      short loc_18000B3B9
0x18000b3a2  lea     edx, [r15+0Fh]
0x18000b3a6  mov     r9d, eax
0x18000b3a9  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000b3b0  mov     rcx, [rcx+10h]
0x18000b3b4  call    WPP_SF_d
0x18000b3b9  jmp     loc_18000B57C
0x18000b3be  mov     [rsp+0F8h+OutputBufferLength], edi; OutputBufferLength
0x18000b3c2  mov     [rsp+0F8h+OutputBuffer], rdi; OutputBuffer
0x18000b3c7  mov     [rsp+0F8h+InputBufferLength], 4; InputBufferLength
0x18000b3cf  lea     rax, [rsp+0F8h+arg_0]
0x18000b3d7  mov     [rsp+0F8h+InputBuffer], rax; InputBuffer
0x18000b3dc  mov     [rsp+0F8h+OpenOptions], 140948h; FsControlCode
0x18000b3e4  lea     rax, [rsp+0F8h+IoStatusBlock]
0x18000b3ec  mov     qword ptr [rsp+0F8h+ShareAccess], rax; IoStatusBlock
0x18000b3f1  xor     r9d, r9d; ApcContext
0x18000b3f4  xor     r8d, r8d; ApcRoutine
0x18000b3f7  mov     rdx, r15; Event
0x18000b3fa  mov     rcx, [rsp+0F8h+FileHandle]; FileHandle
0x18000b402  call    cs:__imp_NtFsControlFile
0x18000b409  nop     dword ptr [rax+rax+00h]
0x18000b40e  mov     ebx, eax
0x18000b410  mov     [rsp+0F8h+var_A8], eax
0x18000b414  cmp     eax, 103h
0x18000b419  jnz     short loc_18000B484
0x18000b41b  or      ebx, 0FFFFFFFFh
0x18000b41e  mov     edx, ebx; dwMilliseconds
0x18000b420  mov     rcx, r15; hHandle
0x18000b423  call    cs:__imp_WaitForSingleObject
0x18000b42a  nop     dword ptr [rax+rax+00h]
0x18000b42f  mov     [rsp+0F8h+var_A8], eax
0x18000b433  cmp     eax, ebx
0x18000b435  jnz     short loc_18000B479
0x18000b437  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b43e  cmp     rcx, r14
0x18000b441  jz      short loc_18000B462
0x18000b443  test    byte ptr [rcx+1Ch], 2
0x18000b447  jz      short loc_18000B462
0x18000b449  mov     edx, 10h
0x18000b44e  or      r9d, 0FFFFFFFFh
0x18000b452  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000b459  mov     rcx, [rcx+10h]
0x18000b45d  call    WPP_SF_d
0x18000b462  call    cs:__imp_GetLastError
0x18000b469  nop     dword ptr [rax+rax+00h]
0x18000b46e  mov     ebx, eax
0x18000b470  mov     [rsp+0F8h+var_A8], eax
0x18000b474  jmp     loc_18000B57C
0x18000b479  mov     ebx, dword ptr [rsp+0F8h+IoStatusBlock]
0x18000b480  mov     [rsp+0F8h+var_A8], ebx
0x18000b484  test    ebx, ebx
0x18000b486  jns     short loc_18000B4CB
0x18000b488  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b48f  cmp     rcx, r14
0x18000b492  jz      short loc_18000B4B2
0x18000b494  test    byte ptr [rcx+1Ch], 2
0x18000b498  jz      short loc_18000B4B2
0x18000b49a  mov     edx, 11h
0x18000b49f  mov     r9d, ebx
0x18000b4a2  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000b4a9  mov     rcx, [rcx+10h]
0x18000b4ad  call    WPP_SF_d
0x18000b4b2  mov     ecx, ebx; Status
0x18000b4b4  call    cs:__imp_LsaNtStatusToWinError
0x18000b4bb  nop     dword ptr [rax+rax+00h]
0x18000b4c0  mov     ebx, eax
0x18000b4c2  mov     [rsp+0F8h+var_A8], eax
0x18000b4c6  jmp     loc_18000B57C
0x18000b4cb  mov     rcx, [rsp+0F8h+FileHandle]; Handle
0x18000b4d3  call    cs:__imp_NtClose
0x18000b4da  nop     dword ptr [rax+rax+00h]
0x18000b4df  mov     [rsp+0F8h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x18000b4eb  lea     rcx, [rsp+0F8h+Binding]; Binding
0x18000b4f0  call    cs:__imp_RpcBindingFree
0x18000b4f7  nop     dword ptr [rax+rax+00h]
0x18000b4fc  mov     rcx, r15; hObject
0x18000b4ff  call    cs:__imp_CloseHandle
0x18000b506  nop     dword ptr [rax+rax+00h]
0x18000b50b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b512  cmp     rcx, r14
0x18000b515  jz      short loc_18000B532
0x18000b517  test    byte ptr [rcx+1Ch], 1
0x18000b51b  jz      short loc_18000B532
0x18000b51d  mov     edx, 13h
0x18000b522  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000b529  mov     rcx, [rcx+10h]
0x18000b52d  call    WPP_SF_
0x18000b532  xor     eax, eax
0x18000b534  jmp     loc_18000B5E7
0x18000b539  mov     ebx, eax
0x18000b53b  mov     [rsp+0F8h+var_A8], eax
0x18000b53f  lea     rdx, WPP_GLOBAL_Control
0x18000b546  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b54d  cmp     rcx, rdx
0x18000b550  jz      short loc_18000B570
0x18000b552  test    byte ptr [rcx+1Ch], 2
0x18000b556  jz      short loc_18000B570
0x18000b558  mov     edx, 12h
0x18000b55d  mov     r9d, eax
0x18000b560  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000b567  mov     rcx, [rcx+10h]
0x18000b56b  call    WPP_SF_d
0x18000b570  lea     r14, WPP_GLOBAL_Control
0x18000b577  mov     r15, [rsp+0F8h+var_90]
0x18000b57c  mov     rcx, [rsp+0F8h+FileHandle]; Handle
0x18000b584  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b588  jz      short loc_18000B596
0x18000b58a  call    cs:__imp_NtClose
0x18000b591  nop     dword ptr [rax+rax+00h]
0x18000b596  test    r15, r15
0x18000b599  jz      short loc_18000B5AA
0x18000b59b  mov     rcx, r15; hObject
0x18000b59e  call    cs:__imp_CloseHandle
0x18000b5a5  nop     dword ptr [rax+rax+00h]
0x18000b5aa  lea     rcx, [rsp+0F8h+Binding]; Binding
0x18000b5af  call    cs:__imp_RpcBindingFree
0x18000b5b6  nop     dword ptr [rax+rax+00h]
0x18000b5bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5c2  cmp     rcx, r14
0x18000b5c5  jz      short loc_18000B5E5
0x18000b5c7  test    byte ptr [rcx+1Ch], 2
0x18000b5cb  jz      short loc_18000B5E5
0x18000b5cd  mov     edx, 14h
0x18000b5d2  mov     r9d, ebx
0x18000b5d5  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000b5dc  mov     rcx, [rcx+10h]
0x18000b5e0  call    WPP_SF_d
0x18000b5e5  mov     eax, ebx
0x18000b5e7  add     rsp, 0D0h
0x18000b5ee  pop     r15
0x18000b5f0  pop     r14
0x18000b5f2  pop     r13
0x18000b5f4  pop     rdi
0x18000b5f5  pop     rbx
0x18000b5f6  retn
0x180013330  push    rbp
0x180013332  sub     rsp, 50h
0x180013336  mov     rbp, rdx
0x180013339  mov     rax, [rcx]
0x18001333c  mov     edx, [rax]
0x18001333e  mov     dword ptr [rbp+54h], 0
  ... truncated ...
```
