# DeleteConnection

- ea: `0x18000a92c`
- end: `0x18000adeb`
- name: `DeleteConnection`
- size: `1215`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180004720`
- `0x180005850`

## callees

- `0x1800023f0`
- `0x180002418`
- `0x180008aa0`
- `0x18000a92c`
- `0x18000b9b8`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x18000ac32`
- `ntdll!NtFsControlFile` at `0x18000ac32`
- `ntdll!NtOpenFile` at `0x18000ab4a`
- `ntdll!NtOpenFile` at `0x18000ab4a`
- `ntdll!NtClose` at `0x18000aceb`
- `ntdll!NtClose` at `0x18000ad90`
- `ntdll!NtClose` at `0x18000aceb`
- `ntdll!NtClose` at `0x18000ad90`
- `ntdll!RtlInitUnicodeString` at `0x18000aad6`
- `ntdll!RtlInitUnicodeString` at `0x18000aad6`
- `KERNEL32!CreateEventW` at `0x18000aba1`
- `KERNEL32!CreateEventW` at `0x18000aba1`
- `KERNEL32!WaitForSingleObject` at `0x18000ac4d`
- `KERNEL32!WaitForSingleObject` at `0x18000ac4d`
- `KERNEL32!CloseHandle` at `0x18000ad0b`
- `KERNEL32!CloseHandle` at `0x18000ad9e`
- `KERNEL32!CloseHandle` at `0x18000ad0b`
- `KERNEL32!CloseHandle` at `0x18000ad9e`
- `KERNEL32!GetLastError` at `0x18000abb4`
- `KERNEL32!GetLastError` at `0x18000ac86`
- `KERNEL32!GetLastError` at `0x18000abb4`
- `KERNEL32!GetLastError` at `0x18000ac86`
- `ADVAPI32!LsaNtStatusToWinError` at `0x18000ab86`
- `ADVAPI32!LsaNtStatusToWinError` at `0x18000acd2`
- `ADVAPI32!LsaNtStatusToWinError` at `0x18000ab86`
- `ADVAPI32!LsaNtStatusToWinError` at `0x18000acd2`
- `RPCRT4!RpcBindingFree` at `0x18000ad02`
- `RPCRT4!RpcBindingFree` at `0x18000ada9`
- `RPCRT4!RpcBindingFree` at `0x18000ad02`
- `RPCRT4!RpcBindingFree` at `0x18000ada9`
- `RPCRT4!NdrClientCall3` at `0x18000aa5f`
- `RPCRT4!NdrClientCall3` at `0x18000aa5f`

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
0x18000a92c  mov     rax, rsp
0x18000a92f  mov     [rax+18h], r8
0x18000a933  mov     [rax+10h], edx
0x18000a936  mov     [rax+8], ecx
0x18000a939  push    rbx
0x18000a93a  push    rdi
0x18000a93b  push    r13
0x18000a93d  push    r14
0x18000a93f  push    r15
0x18000a941  sub     rsp, 0D0h
0x18000a948  mov     r13, r9
0x18000a94b  xor     edi, edi
0x18000a94d  mov     [rax+28h], edi
0x18000a950  mov     qword ptr [rax+20h], 0FFFFFFFFFFFFFFFFh
0x18000a958  mov     [rsp+0F8h+Binding], rdi
0x18000a95d  mov     r15d, edi
0x18000a960  mov     [rsp+0F8h+var_90], rdi
0x18000a965  xorps   xmm0, xmm0
0x18000a968  movups  xmmword ptr [rax-70h], xmm0
0x18000a96c  xor     ecx, ecx
0x18000a96e  movups  xmmword ptr [rax-60h], xmm0
0x18000a972  movups  xmmword ptr [rax-50h], xmm0
0x18000a976  movups  xmmword ptr [rax-44h], xmm0
0x18000a97a  movups  xmmword ptr [rsp+0F8h+DestinationString.Length], xmm0
0x18000a97f  lea     r14, WPP_GLOBAL_Control
0x18000a986  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a98d  cmp     rcx, r14
0x18000a990  jz      short loc_18000A9AE
0x18000a992  test    byte ptr [rcx+1Ch], 1
0x18000a996  jz      short loc_18000A9AE
0x18000a998  lea     edx, [rdi+0Ah]
0x18000a99b  mov     r9, r8
0x18000a99e  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000a9a5  mov     rcx, [rcx+10h]
0x18000a9a9  call    WPP_SF_S
0x18000a9ae  test    r13, r13
0x18000a9b1  jz      short loc_18000A9B8
0x18000a9b3  mov     [r13+0], di
0x18000a9b8  lea     rcx, [rsp+0F8h+Binding]
0x18000a9bd  call    RpcBindForNfsClient
0x18000a9c2  mov     ebx, eax
0x18000a9c4  test    eax, eax
0x18000a9c6  jz      short loc_18000A9FF
0x18000a9c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9cf  cmp     rcx, r14
0x18000a9d2  jz      loc_18000ADD9
0x18000a9d8  test    byte ptr [rcx+1Ch], 2
0x18000a9dc  jz      loc_18000ADB6
0x18000a9e2  mov     edx, 0Bh
0x18000a9e7  mov     r9d, eax
0x18000a9ea  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000a9f1  mov     rcx, [rcx+10h]
0x18000a9f5  call    WPP_SF_d
0x18000a9fa  jmp     loc_18000ADAF
0x18000a9ff  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000aa03  mov     rcx, [rsp+0F8h+arg_10]
0x18000aa0b  inc     rax
0x18000aa0e  cmp     [rcx+rax*2], di
0x18000aa12  jnz     short loc_18000AA0B
0x18000aa14  inc     eax
0x18000aa16  mov     [rsp+0F8h+var_78], rdi
0x18000aa1e  lea     rdx, [rsp+0F8h+arg_20]
0x18000aa26  mov     qword ptr [rsp+0F8h+OutputBufferLength], rdx
0x18000aa2b  mov     [rsp+0F8h+OutputBuffer], r13
0x18000aa30  mov     [rsp+0F8h+InputBufferLength], 104h
0x18000aa38  mov     [rsp+0F8h+InputBuffer], rcx
0x18000aa3d  mov     [rsp+0F8h+OpenOptions], eax
0x18000aa41  mov     eax, [rsp+0F8h+arg_8]
0x18000aa48  mov     [rsp+0F8h+ShareAccess], eax
0x18000aa4c  mov     r9, [rsp+0F8h+Binding]
0x18000aa51  xor     r8d, r8d; pReturnValue
0x18000aa54  lea     edx, [r8+4]; nProcNum
0x18000aa58  lea     rcx, pProxyInfo; pProxyInfo
0x18000aa5f  call    cs:__imp_NdrClientCall3
0x18000aa65  mov     rbx, rax
0x18000aa68  mov     [rsp+0F8h+var_78], rax
0x18000aa70  mov     [rsp+0F8h+var_A8], eax
0x18000aa74  test    eax, eax
0x18000aa76  jz      short loc_18000AAA7
0x18000aa78  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa7f  cmp     rcx, r14
0x18000aa82  jz      short loc_18000AAA2
0x18000aa84  test    byte ptr [rcx+1Ch], 2
0x18000aa88  jz      short loc_18000AAA2
0x18000aa8a  mov     edx, 0Ch
0x18000aa8f  mov     r9d, eax
0x18000aa92  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000aa99  mov     rcx, [rcx+10h]
0x18000aa9d  call    WPP_SF_d
0x18000aaa2  jmp     loc_18000AD82
0x18000aaa7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aaae  cmp     rcx, r14
0x18000aab1  jz      short loc_18000AACE
0x18000aab3  test    byte ptr [rcx+1Ch], 1
0x18000aab7  jz      short loc_18000AACE
0x18000aab9  mov     edx, 0Dh
0x18000aabe  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000aac5  mov     rcx, [rcx+10h]
0x18000aac9  call    WPP_SF_
0x18000aace  mov     rdx, r13; SourceString
0x18000aad1  lea     rcx, [rsp+0F8h+DestinationString]; DestinationString
0x18000aad6  call    cs:__imp_RtlInitUnicodeString
0x18000aadc  mov     eax, 0FFFEh
0x18000aae1  add     [rsp+0F8h+DestinationString.MaximumLength], ax
0x18000aae6  mov     [rsp+0F8h+ObjectAttributes.Length], 30h ; '0'
0x18000aaf1  mov     [rsp+0F8h+ObjectAttributes.RootDirectory], rdi
0x18000aaf9  mov     [rsp+0F8h+ObjectAttributes.Attributes], 40h ; '@'
0x18000ab04  lea     rax, [rsp+0F8h+DestinationString]
0x18000ab09  mov     [rsp+0F8h+ObjectAttributes.ObjectName], rax
0x18000ab11  xorps   xmm0, xmm0
0x18000ab14  movdqu  xmmword ptr [rsp+0F8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000ab1d  mov     [rsp+0F8h+OpenOptions], 80h; OpenOptions
0x18000ab25  mov     [rsp+0F8h+ShareAccess], 7; ShareAccess
0x18000ab2d  lea     r9, [rsp+0F8h+IoStatusBlock]; IoStatusBlock
0x18000ab35  lea     r8, [rsp+0F8h+ObjectAttributes]; ObjectAttributes
0x18000ab3d  mov     edx, 100000h; DesiredAccess
0x18000ab42  lea     rcx, [rsp+0F8h+FileHandle]; FileHandle
0x18000ab4a  call    cs:__imp_NtOpenFile
0x18000ab50  mov     ebx, eax
0x18000ab52  mov     [rsp+0F8h+var_A8], eax
0x18000ab56  test    eax, eax
0x18000ab58  jz      short loc_18000AB97
0x18000ab5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab61  cmp     rcx, r14
0x18000ab64  jz      short loc_18000AB84
0x18000ab66  test    byte ptr [rcx+1Ch], 2
0x18000ab6a  jz      short loc_18000AB84
0x18000ab6c  mov     edx, 0Eh
0x18000ab71  mov     r9d, eax
0x18000ab74  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000ab7b  mov     rcx, [rcx+10h]
0x18000ab7f  call    WPP_SF_d
0x18000ab84  mov     ecx, ebx; Status
0x18000ab86  call    cs:__imp_LsaNtStatusToWinError
0x18000ab8c  mov     ebx, eax
0x18000ab8e  mov     [rsp+0F8h+var_A8], eax
0x18000ab92  jmp     loc_18000AD82
0x18000ab97  xor     r9d, r9d; lpName
0x18000ab9a  xor     r8d, r8d; bInitialState
0x18000ab9d  xor     edx, edx; bManualReset
0x18000ab9f  xor     ecx, ecx; lpEventAttributes
0x18000aba1  call    cs:__imp_CreateEventW
0x18000aba7  mov     r15, rax
0x18000abaa  mov     [rsp+0F8h+var_90], rax
0x18000abaf  test    rax, rax
0x18000abb2  jnz     short loc_18000ABEE
0x18000abb4  call    cs:__imp_GetLastError
0x18000abba  mov     ebx, eax
0x18000abbc  mov     [rsp+0F8h+var_A8], eax
0x18000abc0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abc7  cmp     rcx, r14
0x18000abca  jz      short loc_18000ABE9
0x18000abcc  test    byte ptr [rcx+1Ch], 2
0x18000abd0  jz      short loc_18000ABE9
0x18000abd2  lea     edx, [r15+0Fh]
0x18000abd6  mov     r9d, eax
0x18000abd9  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000abe0  mov     rcx, [rcx+10h]
0x18000abe4  call    WPP_SF_d
0x18000abe9  jmp     loc_18000AD82
0x18000abee  mov     [rsp+0F8h+OutputBufferLength], edi; OutputBufferLength
0x18000abf2  mov     [rsp+0F8h+OutputBuffer], rdi; OutputBuffer
0x18000abf7  mov     [rsp+0F8h+InputBufferLength], 4; InputBufferLength
0x18000abff  lea     rax, [rsp+0F8h+arg_0]
0x18000ac07  mov     [rsp+0F8h+InputBuffer], rax; InputBuffer
0x18000ac0c  mov     [rsp+0F8h+OpenOptions], 140948h; FsControlCode
0x18000ac14  lea     rax, [rsp+0F8h+IoStatusBlock]
0x18000ac1c  mov     qword ptr [rsp+0F8h+ShareAccess], rax; IoStatusBlock
0x18000ac21  xor     r9d, r9d; ApcContext
0x18000ac24  xor     r8d, r8d; ApcRoutine
0x18000ac27  mov     rdx, r15; Event
0x18000ac2a  mov     rcx, [rsp+0F8h+FileHandle]; FileHandle
0x18000ac32  call    cs:__imp_NtFsControlFile
0x18000ac38  mov     ebx, eax
0x18000ac3a  mov     [rsp+0F8h+var_A8], eax
0x18000ac3e  cmp     eax, 103h
0x18000ac43  jnz     short loc_18000ACA2
0x18000ac45  or      ebx, 0FFFFFFFFh
0x18000ac48  mov     edx, ebx; dwMilliseconds
0x18000ac4a  mov     rcx, r15; hHandle
0x18000ac4d  call    cs:__imp_WaitForSingleObject
0x18000ac53  mov     [rsp+0F8h+var_A8], eax
0x18000ac57  cmp     eax, ebx
0x18000ac59  jnz     short loc_18000AC97
0x18000ac5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac62  cmp     rcx, r14
0x18000ac65  jz      short loc_18000AC86
0x18000ac67  test    byte ptr [rcx+1Ch], 2
0x18000ac6b  jz      short loc_18000AC86
0x18000ac6d  mov     edx, 10h
0x18000ac72  or      r9d, 0FFFFFFFFh
0x18000ac76  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000ac7d  mov     rcx, [rcx+10h]
0x18000ac81  call    WPP_SF_d
0x18000ac86  call    cs:__imp_GetLastError
0x18000ac8c  mov     ebx, eax
0x18000ac8e  mov     [rsp+0F8h+var_A8], eax
0x18000ac92  jmp     loc_18000AD82
0x18000ac97  mov     ebx, dword ptr [rsp+0F8h+IoStatusBlock]
0x18000ac9e  mov     [rsp+0F8h+var_A8], ebx
0x18000aca2  test    ebx, ebx
0x18000aca4  jns     short loc_18000ACE3
0x18000aca6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000acad  cmp     rcx, r14
0x18000acb0  jz      short loc_18000ACD0
0x18000acb2  test    byte ptr [rcx+1Ch], 2
0x18000acb6  jz      short loc_18000ACD0
0x18000acb8  mov     edx, 11h
0x18000acbd  mov     r9d, ebx
0x18000acc0  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000acc7  mov     rcx, [rcx+10h]
0x18000accb  call    WPP_SF_d
0x18000acd0  mov     ecx, ebx; Status
0x18000acd2  call    cs:__imp_LsaNtStatusToWinError
0x18000acd8  mov     ebx, eax
0x18000acda  mov     [rsp+0F8h+var_A8], eax
0x18000acde  jmp     loc_18000AD82
0x18000ace3  mov     rcx, [rsp+0F8h+FileHandle]; Handle
0x18000aceb  call    cs:__imp_NtClose
0x18000acf1  mov     [rsp+0F8h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x18000acfd  lea     rcx, [rsp+0F8h+Binding]; Binding
0x18000ad02  call    cs:__imp_RpcBindingFree
0x18000ad08  mov     rcx, r15; hObject
0x18000ad0b  call    cs:__imp_CloseHandle
0x18000ad11  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad18  cmp     rcx, r14
0x18000ad1b  jz      short loc_18000AD38
0x18000ad1d  test    byte ptr [rcx+1Ch], 1
0x18000ad21  jz      short loc_18000AD38
0x18000ad23  mov     edx, 13h
0x18000ad28  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000ad2f  mov     rcx, [rcx+10h]
0x18000ad33  call    WPP_SF_
0x18000ad38  xor     eax, eax
0x18000ad3a  jmp     loc_18000ADDB
0x18000ad3f  mov     ebx, eax
0x18000ad41  mov     [rsp+0F8h+var_A8], eax
0x18000ad45  lea     rdx, WPP_GLOBAL_Control
0x18000ad4c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad53  cmp     rcx, rdx
0x18000ad56  jz      short loc_18000AD76
0x18000ad58  test    byte ptr [rcx+1Ch], 2
0x18000ad5c  jz      short loc_18000AD76
0x18000ad5e  mov     edx, 12h
0x18000ad63  mov     r9d, eax
0x18000ad66  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000ad6d  mov     rcx, [rcx+10h]
0x18000ad71  call    WPP_SF_d
0x18000ad76  lea     r14, WPP_GLOBAL_Control
0x18000ad7d  mov     r15, [rsp+0F8h+var_90]
0x18000ad82  mov     rcx, [rsp+0F8h+FileHandle]; Handle
0x18000ad8a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ad8e  jz      short loc_18000AD96
0x18000ad90  call    cs:__imp_NtClose
0x18000ad96  test    r15, r15
0x18000ad99  jz      short loc_18000ADA4
0x18000ad9b  mov     rcx, r15; hObject
0x18000ad9e  call    cs:__imp_CloseHandle
0x18000ada4  lea     rcx, [rsp+0F8h+Binding]; Binding
0x18000ada9  call    cs:__imp_RpcBindingFree
0x18000adaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000adb6  cmp     rcx, r14
0x18000adb9  jz      short loc_18000ADD9
0x18000adbb  test    byte ptr [rcx+1Ch], 2
0x18000adbf  jz      short loc_18000ADD9
0x18000adc1  mov     edx, 14h
0x18000adc6  mov     r9d, ebx
0x18000adc9  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000add0  mov     rcx, [rcx+10h]
0x18000add4  call    WPP_SF_d
0x18000add9  mov     eax, ebx
0x18000addb  add     rsp, 0D0h
0x18000ade2  pop     r15
0x18000ade4  pop     r14
0x18000ade6  pop     r13
0x18000ade8  pop     rdi
0x18000ade9  pop     rbx
0x18000adea  retn
0x180012060  push    rbp
0x180012062  sub     rsp, 50h
0x180012066  mov     rbp, rdx
0x180012069  mov     rax, [rcx]
0x18001206c  mov     edx, [rax]
0x18001206e  mov     dword ptr [rbp+54h], 0
0x180012075  mov     dword ptr [rbp+54h], 0
0x18001207c  mov     eax, [rbp+54h]
0x18001207f  cmp     eax, 8
0x180012082  jge     short loc_1800120A7
0x180012084  movsxd  rcx, dword ptr [rbp+54h]
0x180012088  lea     rax, FatalExceptions
0x18001208f  cmp     edx, [rax+rcx*4]
0x180012092  jnz     short loc_18001209D
0x180012094  mov     dword ptr [rbp+58h], 0
0x18001209b  jmp     short loc_1800120AE
0x18001209d  mov     eax, [rbp+54h]
0x1800120a0  inc     eax
0x1800120a2  mov     [rbp+54h], eax
0x1800120a5  jmp     short loc_18001207C
0x1800120a7  mov     dword ptr [rbp+58h], 1
0x1800120ae  mov     eax, [rbp+58h]
  ... truncated ...
```
