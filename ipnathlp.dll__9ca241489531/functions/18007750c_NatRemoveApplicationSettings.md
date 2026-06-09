# NatRemoveApplicationSettings

- ea: `0x18007750c`
- end: `0x1800776fb`
- name: `NatRemoveApplicationSettings`
- size: `495`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18006dd7c`
- `0x180073920`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18007750c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800775f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077602`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800775f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077602`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007769e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800776ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007769e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800776ab`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180077573`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180077573`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180077689`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180077689`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007759c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007759c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800776b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800776b4`
- `ntdll!NtDeviceIoControlFile` at `0x180077676`
- `ntdll!NtDeviceIoControlFile` at `0x180077676`

## pseudocode

```c
int NatRemoveApplicationSettings()
{
  HANDLE EventW; // rax
  void *v1; // rdi
  PVOID *v2; // rcx
  DWORD LastError; // eax
  __int64 v4; // rdx
  LPVOID *i; // rbx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-28h] BYREF
  int InputBuffer; // [rsp+80h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids);
  }
  InputBuffer = 0;
  IoStatusBlock = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  v1 = EventW;
  if ( EventW )
  {
    EnterCriticalSection(&NatInterfaceLock);
    EnterCriticalSection(&NhLock);
    for ( i = (LPVOID *)NhApplicationSettingsList; i != &NhApplicationSettingsList; i = (LPVOID *)*i )
    {
      LOBYTE(InputBuffer) = *((_BYTE *)i + 16);
      HIWORD(InputBuffer) = *((_WORD *)i + 9);
      if ( NtDeviceIoControlFile(NatFileHandle, v1, 0, 0, &IoStatusBlock, 0x128044u, &InputBuffer, 4u, 0, 0) == 259 )
        WaitForSingleObject(v1, 0xFFFFFFFF);
    }
    LeaveCriticalSection(&NhLock);
    LeaveCriticalSection(&NatInterfaceLock);
    LODWORD(EventW) = CloseHandle(v1);
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v4 = 149;
      goto LABEL_23;
    }
  }
  else
  {
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        LODWORD(EventW) = WPP_SF_d(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            147,
                            &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids,
                            LastError);
        v2 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 7) & 0x200) != 0 && *((_BYTE *)v2 + 25) >= 6u )
      {
        v4 = 148;
LABEL_23:
        LODWORD(EventW) = WPP_SF_(v2[2], v4, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids);
      }
    }
  }
  return (int)EventW;
}

```

## disassembly

```asm
0x18007750c  mov     [rsp+arg_8], rbx
0x180077511  mov     [rsp+arg_10], rbp
0x180077516  push    rsi
0x180077517  push    rdi
0x180077518  push    r13
0x18007751a  sub     rsp, 60h
0x18007751e  mov     rcx, cs:WPP_GLOBAL_Control
0x180077525  lea     rbp, WPP_GLOBAL_Control
0x18007752c  mov     esi, 200h
0x180077531  cmp     rcx, rbp
0x180077534  jz      short loc_180077556
0x180077536  test    [rcx+1Ch], esi
0x180077539  jz      short loc_180077556
0x18007753b  cmp     byte ptr [rcx+19h], 6
0x18007753f  jb      short loc_180077556
0x180077541  mov     rcx, [rcx+10h]
0x180077545  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007754c  mov     edx, 92h
0x180077551  call    WPP_SF_
0x180077556  xorps   xmm0, xmm0
0x180077559  mov     [rsp+78h+arg_0], 0
0x180077564  xor     r9d, r9d; lpName
0x180077567  xor     r8d, r8d; bInitialState
0x18007756a  xor     edx, edx; bManualReset
0x18007756c  xor     ecx, ecx; lpEventAttributes
0x18007756e  movups  xmmword ptr [rsp+78h+var_28], xmm0
0x180077573  call    cs:__imp_CreateEventW
0x180077579  mov     rdi, rax
0x18007757c  test    rax, rax
0x18007757f  jnz     short loc_1800775EE
0x180077581  mov     rcx, cs:WPP_GLOBAL_Control
0x180077588  cmp     rcx, rbp
0x18007758b  jz      loc_1800776E6
0x180077591  test    [rcx+1Ch], esi
0x180077594  jz      short loc_1800775C8
0x180077596  cmp     byte ptr [rcx+19h], 2
0x18007759a  jb      short loc_1800775C8
0x18007759c  call    cs:__imp_GetLastError
0x1800775a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800775a9  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x1800775b0  mov     edx, 93h
0x1800775b5  mov     r9d, eax
0x1800775b8  mov     rcx, [rcx+10h]
0x1800775bc  call    WPP_SF_d
0x1800775c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800775c8  cmp     rcx, rbp
0x1800775cb  jz      loc_1800776E6
0x1800775d1  test    [rcx+1Ch], esi
0x1800775d4  jz      loc_1800776E6
0x1800775da  cmp     byte ptr [rcx+19h], 6
0x1800775de  jb      loc_1800776E6
0x1800775e4  mov     edx, 94h
0x1800775e9  jmp     loc_1800776D6
0x1800775ee  lea     rcx, NatInterfaceLock; lpCriticalSection
0x1800775f5  call    cs:__imp_EnterCriticalSection
0x1800775fb  lea     rcx, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180077602  call    cs:__imp_EnterCriticalSection
0x180077608  mov     rbx, cs:?NhApplicationSettingsList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NhApplicationSettingsList
0x18007760f  lea     r13, ?NhApplicationSettingsList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NhApplicationSettingsList
0x180077616  jmp     short loc_180077692
0x180077618  mov     al, [rbx+10h]
0x18007761b  xor     r9d, r9d; ApcContext
0x18007761e  mov     rcx, cs:NatFileHandle; FileHandle
0x180077625  xor     r8d, r8d; ApcRoutine
0x180077628  mov     [rsp+78h+OutputBufferLength], 0; OutputBufferLength
0x180077630  mov     rdx, rdi; Event
0x180077633  mov     byte ptr [rsp+78h+arg_0], al
0x18007763a  movzx   eax, word ptr [rbx+12h]
0x18007763e  mov     [rsp+78h+OutputBuffer], 0; OutputBuffer
0x180077647  mov     word ptr [rsp+78h+arg_0+2], ax
0x18007764f  lea     rax, [rsp+78h+arg_0]
0x180077657  mov     [rsp+78h+InputBufferLength], 4; InputBufferLength
0x18007765f  mov     [rsp+78h+InputBuffer], rax; InputBuffer
0x180077664  lea     rax, [rsp+78h+var_28]
0x180077669  mov     [rsp+78h+IoControlCode], 128044h; IoControlCode
0x180077671  mov     [rsp+78h+IoStatusBlock], rax; IoStatusBlock
0x180077676  call    cs:__imp_NtDeviceIoControlFile
0x18007767c  cmp     eax, 103h
0x180077681  jnz     short loc_18007768F
0x180077683  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180077686  mov     rcx, rdi; hHandle
0x180077689  call    cs:__imp_WaitForSingleObject
0x18007768f  mov     rbx, [rbx]
0x180077692  cmp     rbx, r13
0x180077695  jnz     short loc_180077618
0x180077697  lea     rcx, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18007769e  call    cs:__imp_LeaveCriticalSection
0x1800776a4  lea     rcx, NatInterfaceLock; lpCriticalSection
0x1800776ab  call    cs:__imp_LeaveCriticalSection
0x1800776b1  mov     rcx, rdi; hObject
0x1800776b4  call    cs:__imp_CloseHandle
0x1800776ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800776c1  cmp     rcx, rbp
0x1800776c4  jz      short loc_1800776E6
0x1800776c6  test    [rcx+1Ch], esi
0x1800776c9  jz      short loc_1800776E6
0x1800776cb  cmp     byte ptr [rcx+19h], 6
0x1800776cf  jb      short loc_1800776E6
0x1800776d1  mov     edx, 95h
0x1800776d6  mov     rcx, [rcx+10h]
0x1800776da  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x1800776e1  call    WPP_SF_
0x1800776e6  lea     r11, [rsp+78h+var_18]
0x1800776eb  mov     rbx, [r11+28h]
0x1800776ef  mov     rbp, [r11+30h]
0x1800776f3  mov     rsp, r11
0x1800776f6  pop     r13
0x1800776f8  pop     rdi
0x1800776f9  pop     rsi
0x1800776fa  retn
```
