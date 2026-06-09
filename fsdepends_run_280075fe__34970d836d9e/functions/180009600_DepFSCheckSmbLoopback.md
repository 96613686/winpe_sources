# DepFSCheckSmbLoopback

- ea: `0x180009600`
- end: `0x180009832`
- name: `DepFSCheckSmbLoopback`
- size: `562`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800090f8`

## callees

- `0x180001020`
- `0x180001f70`
- `0x180002480`
- `0x180009600`

## import_xrefs

- `ntoskrnl!ZwQueryInformationFile` at `0x180009704`
- `ntoskrnl!ZwQueryInformationFile` at `0x180009704`
- `ntoskrnl!KdDebuggerNotPresent` at `0x1800097c7`
- `ntoskrnl!KdDebuggerEnabled` at `0x1800097bb`
- `ntoskrnl!ZwClose` at `0x18000980a`
- `ntoskrnl!ZwClose` at `0x18000980a`
- `ntoskrnl!ZwCreateEvent` at `0x18000968d`
- `ntoskrnl!ZwCreateEvent` at `0x18000968d`
- `ntoskrnl!ZwWaitForSingleObject` at `0x180009723`
- `ntoskrnl!ZwWaitForSingleObject` at `0x180009723`

## pseudocode

```c
__int64 __fastcall DepFSCheckSmbLoopback(HANDLE FileHandle)
{
  NTSTATUS v2; // eax
  unsigned int Status; // ebx
  PDEVICE_OBJECT v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  void *EventHandle; // [rsp+30h] [rbp-D0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+38h] [rbp-C8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD FileInformation[32]; // [rsp+80h] [rbp-80h] BYREF

  EventHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  IoStatusBlock = 0;
  memset(FileInformation, 0, 0x74u);
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwCreateEvent(&EventHandle, 0x100000u, &ObjectAttributes, SynchronizationEvent, 0);
  Status = v2;
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        37,
        WPP_89de4c9ab0183a893b206e6614efcf73_Traceguids,
        (unsigned int)v2);
    }
    return Status;
  }
  Status = ZwQueryInformationFile(FileHandle, &IoStatusBlock, FileInformation, 0x74u, FileRemoteProtocolInformation);
  if ( Status == 259 )
  {
    ZwWaitForSingleObject(EventHandle, 0, 0);
    Status = IoStatusBlock.Status;
  }
  if ( (Status & 0x80000000) == 0 )
  {
    if ( !LOWORD(FileInformation[0]) )
      goto LABEL_21;
    if ( FileInformation[1] != 0x20000 )
      goto LABEL_21;
    if ( (FileInformation[4] & 1) == 0 )
      goto LABEL_21;
    Status = -1073740761;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_21;
    }
    v5 = 39;
    v6 = 3221226535LL;
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_21;
    }
    v5 = 38;
    v6 = Status;
  }
  WPP_SF_D(v4->AttachedDevice, v5, WPP_89de4c9ab0183a893b206e6614efcf73_Traceguids, v6);
LABEL_21:
  if ( byte_18000519C )
  {
    if ( (_BYTE)KdDebuggerEnabled )
    {
      if ( !(_BYTE)KdDebuggerNotPresent )
      {
        Status = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_89de4c9ab0183a893b206e6614efcf73_Traceguids, 0);
        }
      }
    }
  }
  ZwClose(EventHandle);
  return Status;
}

```

## disassembly

```asm
0x180009600  push    rbp
0x180009602  push    rbx
0x180009603  push    rdi
0x180009604  push    r14
0x180009606  lea     rbp, [rsp-18h]
0x18000960b  sub     rsp, 118h
0x180009612  mov     rax, cs:__security_cookie
0x180009619  xor     rax, rsp
0x18000961c  mov     [rbp+30h+var_30], rax
0x180009620  xor     edx, edx; Val
0x180009622  mov     [rsp+130h+EventHandle], 0
0x18000962b  mov     rdi, rcx
0x18000962e  mov     qword ptr [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x180009637  xorps   xmm0, xmm0
0x18000963a  mov     qword ptr [rsp+130h+ObjectAttributes.Attributes], 200h
0x180009643  lea     rcx, [rbp+30h+FileInformation]; void *
0x180009647  lea     r8d, [rdx+74h]; Size
0x18000964b  movups  xmmword ptr [rsp+130h+IoStatusBlock], xmm0
0x180009650  call    memset
0x180009655  xorps   xmm0, xmm0
0x180009658  mov     [rsp+130h+ObjectAttributes.RootDirectory], 0
0x180009661  mov     r14d, 1
0x180009667  mov     [rsp+130h+ObjectAttributes.ObjectName], 0
0x180009670  mov     r9d, r14d; EventType
0x180009673  mov     [rsp+130h+InitialState], 0; InitialState
0x180009678  lea     r8, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x18000967d  mov     edx, 100000h; DesiredAccess
0x180009682  lea     rcx, [rsp+130h+EventHandle]; EventHandle
0x180009687  movdqu  xmmword ptr [rsp+130h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000968d  call    cs:__imp_ZwCreateEvent
0x180009694  nop     dword ptr [rax+rax+00h]
0x180009699  mov     ebx, eax
0x18000969b  test    eax, eax
0x18000969d  jns     short loc_1800096EA
0x18000969f  mov     r10, cs:WPP_GLOBAL_Control
0x1800096a6  lea     rdi, WPP_GLOBAL_Control
0x1800096ad  cmp     r10, rdi
0x1800096b0  jz      loc_180009816
0x1800096b6  mov     ecx, [r10+2Ch]
0x1800096ba  test    r14b, cl
0x1800096bd  jz      loc_180009816
0x1800096c3  cmp     byte ptr [r10+29h], 2
0x1800096c8  jb      loc_180009816
0x1800096ce  mov     rcx, [r10+18h]
0x1800096d2  lea     edx, [r14+24h]
0x1800096d6  mov     r9d, eax
0x1800096d9  lea     r8, WPP_89de4c9ab0183a893b206e6614efcf73_Traceguids
0x1800096e0  call    WPP_SF_D
0x1800096e5  jmp     loc_180009816
0x1800096ea  mov     r9d, 74h ; 't'; Length
0x1800096f0  mov     dword ptr [rsp+130h+InitialState], 37h ; '7'; FileInformationClass
0x1800096f8  lea     r8, [rbp+30h+FileInformation]; FileInformation
0x1800096fc  mov     rcx, rdi; FileHandle
0x1800096ff  lea     rdx, [rsp+130h+IoStatusBlock]; IoStatusBlock
0x180009704  call    cs:__imp_ZwQueryInformationFile
0x18000970b  nop     dword ptr [rax+rax+00h]
0x180009710  mov     ebx, eax
0x180009712  cmp     eax, 103h
0x180009717  jnz     short loc_180009733
0x180009719  mov     rcx, [rsp+130h+EventHandle]; Handle
0x18000971e  xor     r8d, r8d; Timeout
0x180009721  xor     edx, edx; Alertable
0x180009723  call    cs:__imp_ZwWaitForSingleObject
0x18000972a  nop     dword ptr [rax+rax+00h]
0x18000972f  mov     ebx, dword ptr [rsp+130h+IoStatusBlock]
0x180009733  lea     rdi, WPP_GLOBAL_Control
0x18000973a  test    ebx, ebx
0x18000973c  jns     short loc_180009762
0x18000973e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009745  cmp     rcx, rdi
0x180009748  jz      short loc_1800097B2
0x18000974a  mov     eax, [rcx+2Ch]
0x18000974d  test    r14b, al
0x180009750  jz      short loc_1800097B2
0x180009752  cmp     byte ptr [rcx+29h], 2
0x180009756  jb      short loc_1800097B2
0x180009758  mov     edx, 26h ; '&'
0x18000975d  mov     r9d, ebx
0x180009760  jmp     short loc_1800097A2
0x180009762  cmp     [rbp+30h+FileInformation], r14w
0x180009767  jb      short loc_1800097B2
0x180009769  cmp     [rbp+30h+var_AC], 20000h
0x180009770  jnz     short loc_1800097B2
0x180009772  test    [rbp+30h+var_A0], r14b
0x180009776  jz      short loc_1800097B2
0x180009778  mov     ebx, 0C0000427h
0x18000977d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009784  cmp     rcx, rdi
0x180009787  jz      short loc_1800097B2
0x180009789  mov     eax, [rcx+2Ch]
0x18000978c  test    r14b, al
0x18000978f  jz      short loc_1800097B2
0x180009791  cmp     byte ptr [rcx+29h], 2
0x180009795  jb      short loc_1800097B2
0x180009797  mov     edx, 27h ; '''
0x18000979c  mov     r9d, 0C0000427h
0x1800097a2  mov     rcx, [rcx+18h]
0x1800097a6  lea     r8, WPP_89de4c9ab0183a893b206e6614efcf73_Traceguids
0x1800097ad  call    WPP_SF_D
0x1800097b2  cmp     cs:byte_18000519C, 0
0x1800097b9  jz      short loc_180009805
0x1800097bb  mov     rax, cs:KdDebuggerEnabled
0x1800097c2  cmp     byte ptr [rax], 0
0x1800097c5  jz      short loc_180009805
0x1800097c7  mov     rax, cs:KdDebuggerNotPresent
0x1800097ce  cmp     byte ptr [rax], 0
0x1800097d1  jnz     short loc_180009805
0x1800097d3  xor     ebx, ebx
0x1800097d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097dc  cmp     rcx, rdi
0x1800097df  jz      short loc_180009805
0x1800097e1  mov     eax, [rcx+2Ch]
0x1800097e4  test    r14b, al
0x1800097e7  jz      short loc_180009805
0x1800097e9  cmp     byte ptr [rcx+29h], 2
0x1800097ed  jb      short loc_180009805
0x1800097ef  mov     rcx, [rcx+18h]
0x1800097f3  lea     edx, [rbx+28h]
0x1800097f6  xor     r9d, r9d
0x1800097f9  lea     r8, WPP_89de4c9ab0183a893b206e6614efcf73_Traceguids
0x180009800  call    WPP_SF_D
0x180009805  mov     rcx, [rsp+130h+EventHandle]; Handle
0x18000980a  call    cs:__imp_ZwClose
0x180009811  nop     dword ptr [rax+rax+00h]
0x180009816  mov     eax, ebx
0x180009818  mov     rcx, [rbp+30h+var_30]
0x18000981c  xor     rcx, rsp; StackCookie
0x18000981f  call    __security_check_cookie
0x180009824  add     rsp, 118h
0x18000982b  pop     r14
0x18000982d  pop     rdi
0x18000982e  pop     rbx
0x18000982f  pop     rbp
0x180009830  retn
```
