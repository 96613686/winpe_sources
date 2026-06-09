# NatUnbindInterface

- ea: `0x1800438bc`
- end: `0x180043be6`
- name: `NatUnbindInterface`
- size: `810`
- prototype: `__int64 __fastcall(unsigned int, struct _NAT_INTERFACE *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180050474`
- `0x1800799c4`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x1800202e0`
- `0x180035678`
- `0x1800438bc`
- `0x180084928`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800439a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800439a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800439d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043a4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043b45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800439d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043a4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043b45`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004391e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004391e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180043b2e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180043b2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043949`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043949`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043b54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043b54`
- `ntdll!NtDeviceIoControlFile` at `0x180043b13`
- `ntdll!NtDeviceIoControlFile` at `0x180043b13`
- `ntdll!RtlNtStatusToDosError` at `0x180043b6a`
- `ntdll!RtlNtStatusToDosError` at `0x180043b6a`

## pseudocode

```c
__int64 __fastcall NatUnbindInterface(unsigned int a1, struct _NAT_INTERFACE *a2)
{
  HANDLE EventW; // rsi
  PVOID *v5; // rcx
  DWORD LastError; // eax
  PVOID *v8; // rcx
  int v9; // eax
  PVOID *v10; // rcx
  bool v11; // zf
  int Status; // edi
  ULONG v13; // ebx
  ULONG v14; // eax
  PVOID *v15; // rcx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, a1);
  }
  IoStatusBlock = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, LastError);
        v5 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x200) != 0 && *((_BYTE *)v5 + 25) >= 6u )
        WPP_SF_(v5[2], 152, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids);
    }
    return 8;
  }
  EnterCriticalSection(&NatInterfaceLock);
  if ( !a2 )
  {
    a2 = NatLookupInterface(a1, 0);
    if ( !a2 )
    {
      LeaveCriticalSection(&NatInterfaceLock);
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, a1);
          v8 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x200) != 0 && *((_BYTE *)v8 + 25) >= 6u )
          WPP_SF_(v8[2], 154, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids);
      }
      return 905;
    }
  }
  v9 = *((_DWORD *)a2 + 7);
  if ( (v9 & 0x40000000) != 0 )
  {
    v11 = *((_DWORD *)a2 + 6) == 3;
    *((_DWORD *)a2 + 7) = v9 & 0xBFFFFFFF;
    if ( v11 )
      NatUpdateProxyArp(a2, 0);
    Status = NtDeviceIoControlFile(NatFileHandle, EventW, 0, 0, &IoStatusBlock, 0x12800Cu, (char *)a2 + 20, 4u, 0, 0);
    if ( Status == 259 )
    {
      WaitForSingleObject(EventW, 0xFFFFFFFF);
      Status = IoStatusBlock.Status;
    }
    LeaveCriticalSection(&NatInterfaceLock);
    CloseHandle(EventW);
    if ( Status < 0 )
    {
      v14 = RtlNtStatusToDosError(Status);
      v13 = v14;
      if ( v14 )
      {
        v15 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v13;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_48:
          if ( v15 != &WPP_GLOBAL_Control && (*((_DWORD *)v15 + 7) & 0x200) != 0 && *((_BYTE *)v15 + 25) >= 6u )
            WPP_SF_d(v15[2], 158, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, v13);
          return v13;
        }
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          157,
          &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids,
          (unsigned int)Status,
          v14);
      }
    }
    else
    {
      v13 = 0;
    }
    v15 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_48;
  }
  LeaveCriticalSection(&NatInterfaceLock);
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, a1);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x200) != 0 && *((_BYTE *)v10 + 25) >= 6u )
      WPP_SF_(v10[2], 156, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids);
  }
  return 1228;
}

```

## disassembly

```asm
0x1800438bc  push    rbx
0x1800438be  push    rbp
0x1800438bf  push    rsi
0x1800438c0  push    rdi
0x1800438c1  push    r14
0x1800438c3  push    r15
0x1800438c5  sub     rsp, 68h
0x1800438c9  mov     rbx, rdx
0x1800438cc  mov     edi, ecx
0x1800438ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800438d5  lea     r14, WPP_GLOBAL_Control
0x1800438dc  lea     r15, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x1800438e3  mov     ebp, 200h
0x1800438e8  cmp     rcx, r14
0x1800438eb  jz      short loc_18004390C
0x1800438ed  test    [rcx+1Ch], ebp
0x1800438f0  jz      short loc_18004390C
0x1800438f2  cmp     byte ptr [rcx+19h], 6
0x1800438f6  jb      short loc_18004390C
0x1800438f8  mov     rcx, [rcx+10h]
0x1800438fc  mov     edx, 96h
0x180043901  mov     r9d, edi
0x180043904  mov     r8, r15
0x180043907  call    WPP_SF_d
0x18004390c  xorps   xmm0, xmm0
0x18004390f  xor     r9d, r9d; lpName
0x180043912  xor     r8d, r8d; bInitialState
0x180043915  xor     edx, edx; bManualReset
0x180043917  xor     ecx, ecx; lpEventAttributes
0x180043919  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x18004391e  call    cs:__imp_CreateEventW
0x180043925  nop     dword ptr [rax+rax+00h]
0x18004392a  mov     rsi, rax
0x18004392d  test    rax, rax
0x180043930  jnz     short loc_1800439A2
0x180043932  mov     rcx, cs:WPP_GLOBAL_Control
0x180043939  cmp     rcx, r14
0x18004393c  jz      short loc_180043998
0x18004393e  test    [rcx+1Ch], ebp
0x180043941  jz      short loc_180043977
0x180043943  cmp     byte ptr [rcx+19h], 2
0x180043947  jb      short loc_180043977
0x180043949  call    cs:__imp_GetLastError
0x180043950  nop     dword ptr [rax+rax+00h]
0x180043955  mov     rcx, cs:WPP_GLOBAL_Control
0x18004395c  mov     edx, 97h
0x180043961  mov     r9d, eax
0x180043964  mov     r8, r15
0x180043967  mov     rcx, [rcx+10h]
0x18004396b  call    WPP_SF_d
0x180043970  mov     rcx, cs:WPP_GLOBAL_Control
0x180043977  cmp     rcx, r14
0x18004397a  jz      short loc_180043998
0x18004397c  test    [rcx+1Ch], ebp
0x18004397f  jz      short loc_180043998
0x180043981  cmp     byte ptr [rcx+19h], 6
0x180043985  jb      short loc_180043998
0x180043987  mov     rcx, [rcx+10h]
0x18004398b  mov     edx, 98h
0x180043990  mov     r8, r15
0x180043993  call    WPP_SF_
0x180043998  mov     eax, 8
0x18004399d  jmp     loc_180043BD8
0x1800439a2  lea     rcx, NatInterfaceLock; lpCriticalSection
0x1800439a9  call    cs:__imp_EnterCriticalSection
0x1800439b0  nop     dword ptr [rax+rax+00h]
0x1800439b5  test    rbx, rbx
0x1800439b8  jnz     loc_180043A3F
0x1800439be  xor     edx, edx; struct _LIST_ENTRY **
0x1800439c0  mov     ecx, edi; unsigned int
0x1800439c2  call    ?NatLookupInterface@@YAPEAU_NAT_INTERFACE@@KPEAPEAU_LIST_ENTRY@@@Z; NatLookupInterface(ulong,_LIST_ENTRY * *)
0x1800439c7  mov     rbx, rax
0x1800439ca  test    rax, rax
0x1800439cd  jnz     short loc_180043A3F
0x1800439cf  lea     rcx, NatInterfaceLock; lpCriticalSection
0x1800439d6  call    cs:__imp_LeaveCriticalSection
0x1800439dd  nop     dword ptr [rax+rax+00h]
0x1800439e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800439e9  cmp     rcx, r14
0x1800439ec  jz      short loc_180043A35
0x1800439ee  test    [rcx+1Ch], ebp
0x1800439f1  jz      short loc_180043A14
0x1800439f3  cmp     byte ptr [rcx+19h], 2
0x1800439f7  jb      short loc_180043A14
0x1800439f9  mov     rcx, [rcx+10h]
0x1800439fd  mov     edx, 99h
0x180043a02  mov     r9d, edi
0x180043a05  mov     r8, r15
0x180043a08  call    WPP_SF_d
0x180043a0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180043a14  cmp     rcx, r14
0x180043a17  jz      short loc_180043A35
0x180043a19  test    [rcx+1Ch], ebp
0x180043a1c  jz      short loc_180043A35
0x180043a1e  cmp     byte ptr [rcx+19h], 6
0x180043a22  jb      short loc_180043A35
0x180043a24  mov     rcx, [rcx+10h]
0x180043a28  mov     edx, 9Ah
0x180043a2d  mov     r8, r15
0x180043a30  call    WPP_SF_
0x180043a35  mov     eax, 389h
0x180043a3a  jmp     loc_180043BD8
0x180043a3f  mov     eax, [rbx+1Ch]
0x180043a42  bt      eax, 1Eh
0x180043a46  jb      short loc_180043AB8
0x180043a48  lea     rcx, NatInterfaceLock; lpCriticalSection
0x180043a4f  call    cs:__imp_LeaveCriticalSection
0x180043a56  nop     dword ptr [rax+rax+00h]
0x180043a5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180043a62  cmp     rcx, r14
0x180043a65  jz      short loc_180043AAE
0x180043a67  test    [rcx+1Ch], ebp
0x180043a6a  jz      short loc_180043A8D
0x180043a6c  cmp     byte ptr [rcx+19h], 2
0x180043a70  jb      short loc_180043A8D
0x180043a72  mov     rcx, [rcx+10h]
0x180043a76  mov     edx, 9Bh
0x180043a7b  mov     r9d, edi
0x180043a7e  mov     r8, r15
0x180043a81  call    WPP_SF_d
0x180043a86  mov     rcx, cs:WPP_GLOBAL_Control
0x180043a8d  cmp     rcx, r14
0x180043a90  jz      short loc_180043AAE
0x180043a92  test    [rcx+1Ch], ebp
0x180043a95  jz      short loc_180043AAE
0x180043a97  cmp     byte ptr [rcx+19h], 6
0x180043a9b  jb      short loc_180043AAE
0x180043a9d  mov     rcx, [rcx+10h]
0x180043aa1  mov     edx, 9Ch
0x180043aa6  mov     r8, r15
0x180043aa9  call    WPP_SF_
0x180043aae  mov     eax, 4CCh
0x180043ab3  jmp     loc_180043BD8
0x180043ab8  btr     eax, 1Eh
0x180043abc  cmp     dword ptr [rbx+18h], 3
0x180043ac0  mov     [rbx+1Ch], eax
0x180043ac3  jnz     short loc_180043ACF
0x180043ac5  xor     edx, edx; unsigned __int8
0x180043ac7  mov     rcx, rbx; struct _NAT_INTERFACE *
0x180043aca  call    ?NatUpdateProxyArp@@YAXPEAU_NAT_INTERFACE@@E@Z; NatUpdateProxyArp(_NAT_INTERFACE *,uchar)
0x180043acf  mov     rcx, cs:NatFileHandle; FileHandle
0x180043ad6  lea     rax, [rbx+14h]
0x180043ada  mov     [rsp+98h+OutputBufferLength], 0; OutputBufferLength
0x180043ae2  xor     r9d, r9d; ApcContext
0x180043ae5  mov     [rsp+98h+OutputBuffer], 0; OutputBuffer
0x180043aee  xor     r8d, r8d; ApcRoutine
0x180043af1  mov     [rsp+98h+InputBufferLength], 4; InputBufferLength
0x180043af9  mov     rdx, rsi; Event
0x180043afc  mov     [rsp+98h+InputBuffer], rax; InputBuffer
0x180043b01  lea     rax, [rsp+98h+var_48]
0x180043b06  mov     [rsp+98h+IoControlCode], 12800Ch; IoControlCode
0x180043b0e  mov     [rsp+98h+IoStatusBlock], rax; IoStatusBlock
0x180043b13  call    cs:__imp_NtDeviceIoControlFile
0x180043b1a  nop     dword ptr [rax+rax+00h]
0x180043b1f  mov     edi, eax
0x180043b21  cmp     eax, 103h
0x180043b26  jnz     short loc_180043B3E
0x180043b28  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180043b2b  mov     rcx, rsi; hHandle
0x180043b2e  call    cs:__imp_WaitForSingleObject
0x180043b35  nop     dword ptr [rax+rax+00h]
0x180043b3a  mov     edi, dword ptr [rsp+98h+var_48]
0x180043b3e  lea     rcx, NatInterfaceLock; lpCriticalSection
0x180043b45  call    cs:__imp_LeaveCriticalSection
0x180043b4c  nop     dword ptr [rax+rax+00h]
0x180043b51  mov     rcx, rsi; hObject
0x180043b54  call    cs:__imp_CloseHandle
0x180043b5b  nop     dword ptr [rax+rax+00h]
0x180043b60  test    edi, edi
0x180043b62  js      short loc_180043B68
0x180043b64  xor     ebx, ebx
0x180043b66  jmp     short loc_180043BAB
0x180043b68  mov     ecx, edi; Status
0x180043b6a  call    cs:__imp_RtlNtStatusToDosError
0x180043b71  nop     dword ptr [rax+rax+00h]
0x180043b76  mov     ebx, eax
0x180043b78  test    eax, eax
0x180043b7a  jz      short loc_180043BAB
0x180043b7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180043b83  cmp     rcx, r14
0x180043b86  jz      short loc_180043BD6
0x180043b88  test    [rcx+1Ch], ebp
0x180043b8b  jz      short loc_180043BB2
0x180043b8d  cmp     byte ptr [rcx+19h], 2
0x180043b91  jb      short loc_180043BB2
0x180043b93  mov     rcx, [rcx+10h]
0x180043b97  mov     edx, 9Dh
0x180043b9c  mov     r9d, edi
0x180043b9f  mov     dword ptr [rsp+98h+IoStatusBlock], eax
0x180043ba3  mov     r8, r15
0x180043ba6  call    WPP_SF_Dd
0x180043bab  mov     rcx, cs:WPP_GLOBAL_Control
0x180043bb2  cmp     rcx, r14
0x180043bb5  jz      short loc_180043BD6
0x180043bb7  test    [rcx+1Ch], ebp
0x180043bba  jz      short loc_180043BD6
0x180043bbc  cmp     byte ptr [rcx+19h], 6
0x180043bc0  jb      short loc_180043BD6
0x180043bc2  mov     rcx, [rcx+10h]
0x180043bc6  mov     edx, 9Eh
0x180043bcb  mov     r9d, ebx
0x180043bce  mov     r8, r15
0x180043bd1  call    WPP_SF_d
0x180043bd6  mov     eax, ebx
0x180043bd8  add     rsp, 68h
0x180043bdc  pop     r15
0x180043bde  pop     r14
0x180043be0  pop     rdi
0x180043be1  pop     rsi
0x180043be2  pop     rbp
0x180043be3  pop     rbx
0x180043be4  retn
```
