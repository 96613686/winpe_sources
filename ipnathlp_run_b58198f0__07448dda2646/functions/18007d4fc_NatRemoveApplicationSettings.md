# NatRemoveApplicationSettings

- ea: `0x18007d4fc`
- end: `0x18007d729`
- name: `NatRemoveApplicationSettings`
- size: `557`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18007351c`
- `0x180079490`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18007d4fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007d5f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007d604`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007d5f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007d604`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d6b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d6cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d6b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d6cc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007d563`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007d563`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007d69a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007d69a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d592`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d6db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d6db`
- `ntdll!NtDeviceIoControlFile` at `0x18007d681`
- `ntdll!NtDeviceIoControlFile` at `0x18007d681`

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
0x18007d4fc  mov     [rsp+arg_8], rbx
0x18007d501  mov     [rsp+arg_10], rbp
0x18007d506  push    rsi
0x18007d507  push    rdi
0x18007d508  push    r13
0x18007d50a  sub     rsp, 60h
0x18007d50e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d515  lea     rbp, WPP_GLOBAL_Control
0x18007d51c  mov     esi, 200h
0x18007d521  cmp     rcx, rbp
0x18007d524  jz      short loc_18007D546
0x18007d526  test    [rcx+1Ch], esi
0x18007d529  jz      short loc_18007D546
0x18007d52b  cmp     byte ptr [rcx+19h], 6
0x18007d52f  jb      short loc_18007D546
0x18007d531  mov     rcx, [rcx+10h]
0x18007d535  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007d53c  mov     edx, 92h
0x18007d541  call    WPP_SF_
0x18007d546  xorps   xmm0, xmm0
0x18007d549  mov     [rsp+78h+arg_0], 0
0x18007d554  xor     r9d, r9d; lpName
0x18007d557  xor     r8d, r8d; bInitialState
0x18007d55a  xor     edx, edx; bManualReset
0x18007d55c  xor     ecx, ecx; lpEventAttributes
0x18007d55e  movups  xmmword ptr [rsp+78h+var_28], xmm0
0x18007d563  call    cs:__imp_CreateEventW
0x18007d56a  nop     dword ptr [rax+rax+00h]
0x18007d56f  mov     rdi, rax
0x18007d572  test    rax, rax
0x18007d575  jnz     short loc_18007D5EA
0x18007d577  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d57e  cmp     rcx, rbp
0x18007d581  jz      loc_18007D713
0x18007d587  test    [rcx+1Ch], esi
0x18007d58a  jz      short loc_18007D5C4
0x18007d58c  cmp     byte ptr [rcx+19h], 2
0x18007d590  jb      short loc_18007D5C4
0x18007d592  call    cs:__imp_GetLastError
0x18007d599  nop     dword ptr [rax+rax+00h]
0x18007d59e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d5a5  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007d5ac  mov     edx, 93h
0x18007d5b1  mov     r9d, eax
0x18007d5b4  mov     rcx, [rcx+10h]
0x18007d5b8  call    WPP_SF_d
0x18007d5bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d5c4  cmp     rcx, rbp
0x18007d5c7  jz      loc_18007D713
0x18007d5cd  test    [rcx+1Ch], esi
0x18007d5d0  jz      loc_18007D713
0x18007d5d6  cmp     byte ptr [rcx+19h], 6
0x18007d5da  jb      loc_18007D713
0x18007d5e0  mov     edx, 94h
0x18007d5e5  jmp     loc_18007D703
0x18007d5ea  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007d5f1  call    cs:__imp_EnterCriticalSection
0x18007d5f8  nop     dword ptr [rax+rax+00h]
0x18007d5fd  lea     rcx, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18007d604  call    cs:__imp_EnterCriticalSection
0x18007d60b  nop     dword ptr [rax+rax+00h]
0x18007d610  mov     rbx, cs:?NhApplicationSettingsList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NhApplicationSettingsList
0x18007d617  lea     r13, ?NhApplicationSettingsList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NhApplicationSettingsList
0x18007d61e  jmp     loc_18007D6A9
0x18007d623  mov     al, [rbx+10h]
0x18007d626  xor     r9d, r9d; ApcContext
0x18007d629  mov     rcx, cs:NatFileHandle; FileHandle
0x18007d630  xor     r8d, r8d; ApcRoutine
0x18007d633  mov     [rsp+78h+OutputBufferLength], 0; OutputBufferLength
0x18007d63b  mov     rdx, rdi; Event
0x18007d63e  mov     byte ptr [rsp+78h+arg_0], al
0x18007d645  movzx   eax, word ptr [rbx+12h]
0x18007d649  mov     [rsp+78h+OutputBuffer], 0; OutputBuffer
0x18007d652  mov     word ptr [rsp+78h+arg_0+2], ax
0x18007d65a  lea     rax, [rsp+78h+arg_0]
0x18007d662  mov     [rsp+78h+InputBufferLength], 4; InputBufferLength
0x18007d66a  mov     [rsp+78h+InputBuffer], rax; InputBuffer
0x18007d66f  lea     rax, [rsp+78h+var_28]
0x18007d674  mov     [rsp+78h+IoControlCode], 128044h; IoControlCode
0x18007d67c  mov     [rsp+78h+IoStatusBlock], rax; IoStatusBlock
0x18007d681  call    cs:__imp_NtDeviceIoControlFile
0x18007d688  nop     dword ptr [rax+rax+00h]
0x18007d68d  cmp     eax, 103h
0x18007d692  jnz     short loc_18007D6A6
0x18007d694  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18007d697  mov     rcx, rdi; hHandle
0x18007d69a  call    cs:__imp_WaitForSingleObject
0x18007d6a1  nop     dword ptr [rax+rax+00h]
0x18007d6a6  mov     rbx, [rbx]
0x18007d6a9  cmp     rbx, r13
0x18007d6ac  jnz     loc_18007D623
0x18007d6b2  lea     rcx, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18007d6b9  call    cs:__imp_LeaveCriticalSection
0x18007d6c0  nop     dword ptr [rax+rax+00h]
0x18007d6c5  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007d6cc  call    cs:__imp_LeaveCriticalSection
0x18007d6d3  nop     dword ptr [rax+rax+00h]
0x18007d6d8  mov     rcx, rdi; hObject
0x18007d6db  call    cs:__imp_CloseHandle
0x18007d6e2  nop     dword ptr [rax+rax+00h]
0x18007d6e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d6ee  cmp     rcx, rbp
0x18007d6f1  jz      short loc_18007D713
0x18007d6f3  test    [rcx+1Ch], esi
0x18007d6f6  jz      short loc_18007D713
0x18007d6f8  cmp     byte ptr [rcx+19h], 6
0x18007d6fc  jb      short loc_18007D713
0x18007d6fe  mov     edx, 95h
0x18007d703  mov     rcx, [rcx+10h]
0x18007d707  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007d70e  call    WPP_SF_
0x18007d713  lea     r11, [rsp+78h+var_18]
0x18007d718  mov     rbx, [r11+28h]
0x18007d71c  mov     rbp, [r11+30h]
0x18007d720  mov     rsp, r11
0x18007d723  pop     r13
0x18007d725  pop     rdi
0x18007d726  pop     rsi
0x18007d727  retn
```
