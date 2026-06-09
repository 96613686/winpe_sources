# NatQueryStatisticsInterface

- ea: `0x18007d184`
- end: `0x18007d4f3`
- name: `NatQueryStatisticsInterface`
- size: `879`
- prototype: `__int64 __fastcall(unsigned int, PVOID OutputBuffer)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180079170`

## callees

- `0x18000d090`
- `0x180035678`
- `0x18007d184`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007d1ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007d1ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d20e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d291`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d348`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d447`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d20e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d291`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d348`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d447`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007d329`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007d329`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007d421`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007d421`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d373`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d373`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d434`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d434`
- `ntdll!NtDeviceIoControlFile` at `0x18007d406`
- `ntdll!NtDeviceIoControlFile` at `0x18007d406`
- `ntdll!RtlNtStatusToDosError` at `0x18007d4a7`
- `ntdll!RtlNtStatusToDosError` at `0x18007d4a7`

## pseudocode

```c
__int64 __fastcall NatQueryStatisticsInterface(unsigned int a1, _OWORD *OutputBuffer, ULONG *a3)
{
  struct _NAT_INTERFACE *v6; // rax
  struct _NAT_INTERFACE *v7; // rbp
  PVOID *v8; // rcx
  ULONG v9; // ebx
  __int64 v10; // rdx
  ULONG v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  HANDLE EventW; // rsi
  DWORD LastError; // eax
  int Status; // edi
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, a1);
  }
  IoStatusBlock = 0;
  EnterCriticalSection(&NatInterfaceLock);
  v6 = NatLookupInterface(a1, 0);
  v7 = v6;
  if ( !v6 )
  {
    LeaveCriticalSection(&NatInterfaceLock);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v9 = 905;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v9;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, a1);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v8 == &WPP_GLOBAL_Control || (*((_DWORD *)v8 + 7) & 0x200) == 0 || *((_BYTE *)v8 + 25) < 6u )
      return v9;
    v10 = 139;
    goto LABEL_51;
  }
  if ( (*((_DWORD *)v6 + 7) & 0x40000000) != 0 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    if ( EventW )
    {
      Status = NtDeviceIoControlFile(
                 NatFileHandle,
                 EventW,
                 0,
                 0,
                 &IoStatusBlock,
                 0x128024u,
                 (char *)v7 + 20,
                 4u,
                 OutputBuffer,
                 *a3);
      if ( Status == 259 )
      {
        WaitForSingleObject(EventW, 0xFFFFFFFF);
        Status = IoStatusBlock.Status;
      }
      CloseHandle(EventW);
      LeaveCriticalSection(&NatInterfaceLock);
      if ( Status >= 0 && IoStatusBlock.Information > *a3 )
      {
        *a3 = IoStatusBlock.Information;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
        {
          return 122;
        }
        v13 = 144;
        goto LABEL_42;
      }
      *a3 = IoStatusBlock.Information;
      if ( Status < 0 )
        v9 = RtlNtStatusToDosError(Status);
      else
        v9 = 0;
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
      {
        return v9;
      }
      v10 = 145;
    }
    else
    {
      LeaveCriticalSection(&NatInterfaceLock);
      v8 = (PVOID *)WPP_GLOBAL_Control;
      v9 = 8;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v9;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, LastError);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v8 == &WPP_GLOBAL_Control || (*((_DWORD *)v8 + 7) & 0x200) == 0 || *((_BYTE *)v8 + 25) < 6u )
        return v9;
      v10 = 143;
    }
LABEL_51:
    WPP_SF_d(v8[2], v10, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, v9);
    return v9;
  }
  LeaveCriticalSection(&NatInterfaceLock);
  v11 = *a3;
  *a3 = 56;
  if ( v11 < 0x38 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
    {
      return 122;
    }
    v13 = 140;
LABEL_42:
    WPP_SF_d(v12[2], v13, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, 122);
    return 122;
  }
  *OutputBuffer = 0;
  OutputBuffer[1] = 0;
  OutputBuffer[2] = 0;
  *((_QWORD *)OutputBuffer + 6) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18007d184  push    rbx
0x18007d186  push    rbp
0x18007d187  push    rsi
0x18007d188  push    rdi
0x18007d189  push    r12
0x18007d18b  push    r14
0x18007d18d  push    r15
0x18007d18f  sub     rsp, 60h
0x18007d193  mov     rbx, r8
0x18007d196  mov     rdi, rdx
0x18007d199  mov     esi, ecx
0x18007d19b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d1a2  lea     r15, WPP_GLOBAL_Control
0x18007d1a9  lea     r12, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18007d1b0  mov     r14d, 200h
0x18007d1b6  cmp     rcx, r15
0x18007d1b9  jz      short loc_18007D1DB
0x18007d1bb  test    [rcx+1Ch], r14d
0x18007d1bf  jz      short loc_18007D1DB
0x18007d1c1  cmp     byte ptr [rcx+19h], 6
0x18007d1c5  jb      short loc_18007D1DB
0x18007d1c7  mov     rcx, [rcx+10h]
0x18007d1cb  mov     edx, 89h
0x18007d1d0  mov     r9d, esi
0x18007d1d3  mov     r8, r12
0x18007d1d6  call    WPP_SF_d
0x18007d1db  xorps   xmm0, xmm0
0x18007d1de  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007d1e5  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x18007d1ea  call    cs:__imp_EnterCriticalSection
0x18007d1f1  nop     dword ptr [rax+rax+00h]
0x18007d1f6  xor     edx, edx; struct _LIST_ENTRY **
0x18007d1f8  mov     ecx, esi; unsigned int
0x18007d1fa  call    ?NatLookupInterface@@YAPEAU_NAT_INTERFACE@@KPEAPEAU_LIST_ENTRY@@@Z; NatLookupInterface(ulong,_LIST_ENTRY * *)
0x18007d1ff  mov     rbp, rax
0x18007d202  test    rax, rax
0x18007d205  jnz     short loc_18007D27D
0x18007d207  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007d20e  call    cs:__imp_LeaveCriticalSection
0x18007d215  nop     dword ptr [rax+rax+00h]
0x18007d21a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d221  mov     ebx, 389h
0x18007d226  cmp     rcx, r15
0x18007d229  jz      loc_18007D4E1
0x18007d22f  test    [rcx+1Ch], r14d
0x18007d233  jz      short loc_18007D256
0x18007d235  cmp     byte ptr [rcx+19h], 2
0x18007d239  jb      short loc_18007D256
0x18007d23b  mov     rcx, [rcx+10h]
0x18007d23f  mov     edx, 8Ah
0x18007d244  mov     r9d, esi
0x18007d247  mov     r8, r12
0x18007d24a  call    WPP_SF_d
0x18007d24f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d256  cmp     rcx, r15
0x18007d259  jz      loc_18007D4E1
0x18007d25f  test    [rcx+1Ch], r14d
0x18007d263  jz      loc_18007D4E1
0x18007d269  cmp     byte ptr [rcx+19h], 6
0x18007d26d  jb      loc_18007D4E1
0x18007d273  mov     edx, 8Bh
0x18007d278  jmp     loc_18007D4D2
0x18007d27d  test    dword ptr [rax+1Ch], 40000000h
0x18007d284  jnz     loc_18007D31F
0x18007d28a  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007d291  call    cs:__imp_LeaveCriticalSection
0x18007d298  nop     dword ptr [rax+rax+00h]
0x18007d29d  mov     eax, [rbx]
0x18007d29f  mov     dword ptr [rbx], 38h ; '8'
0x18007d2a5  cmp     eax, 38h ; '8'
0x18007d2a8  jnb     short loc_18007D2D8
0x18007d2aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d2b1  cmp     rcx, r15
0x18007d2b4  jz      loc_18007D494
0x18007d2ba  test    [rcx+1Ch], r14d
0x18007d2be  jz      loc_18007D494
0x18007d2c4  cmp     byte ptr [rcx+19h], 6
0x18007d2c8  jb      loc_18007D494
0x18007d2ce  mov     edx, 8Ch
0x18007d2d3  jmp     loc_18007D482
0x18007d2d8  xorps   xmm0, xmm0
0x18007d2db  xor     eax, eax
0x18007d2dd  movups  xmmword ptr [rdi], xmm0
0x18007d2e0  movups  xmmword ptr [rdi+10h], xmm0
0x18007d2e4  movups  xmmword ptr [rdi+20h], xmm0
0x18007d2e8  mov     [rdi+30h], rax
0x18007d2ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d2f3  cmp     rcx, r15
0x18007d2f6  jz      short loc_18007D318
0x18007d2f8  test    [rcx+1Ch], r14d
0x18007d2fc  jz      short loc_18007D318
0x18007d2fe  cmp     byte ptr [rcx+19h], 6
0x18007d302  jb      short loc_18007D318
0x18007d304  mov     rcx, [rcx+10h]
0x18007d308  mov     edx, 8Dh
0x18007d30d  xor     r9d, r9d
0x18007d310  mov     r8, r12
0x18007d313  call    WPP_SF_d
0x18007d318  xor     eax, eax
0x18007d31a  jmp     loc_18007D4E3
0x18007d31f  xor     r9d, r9d; lpName
0x18007d322  xor     r8d, r8d; bInitialState
0x18007d325  xor     edx, edx; bManualReset
0x18007d327  xor     ecx, ecx; lpEventAttributes
0x18007d329  call    cs:__imp_CreateEventW
0x18007d330  nop     dword ptr [rax+rax+00h]
0x18007d335  mov     rsi, rax
0x18007d338  test    rax, rax
0x18007d33b  jnz     loc_18007D3C8
0x18007d341  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007d348  call    cs:__imp_LeaveCriticalSection
0x18007d34f  nop     dword ptr [rax+rax+00h]
0x18007d354  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d35b  lea     ebx, [rsi+8]
0x18007d35e  cmp     rcx, r15
0x18007d361  jz      loc_18007D4E1
0x18007d367  test    [rcx+1Ch], r14d
0x18007d36b  jz      short loc_18007D3A1
0x18007d36d  cmp     byte ptr [rcx+19h], 2
0x18007d371  jb      short loc_18007D3A1
0x18007d373  call    cs:__imp_GetLastError
0x18007d37a  nop     dword ptr [rax+rax+00h]
0x18007d37f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d386  mov     edx, 8Eh
0x18007d38b  mov     r9d, eax
0x18007d38e  mov     r8, r12
0x18007d391  mov     rcx, [rcx+10h]
0x18007d395  call    WPP_SF_d
0x18007d39a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d3a1  cmp     rcx, r15
0x18007d3a4  jz      loc_18007D4E1
0x18007d3aa  test    [rcx+1Ch], r14d
0x18007d3ae  jz      loc_18007D4E1
0x18007d3b4  cmp     byte ptr [rcx+19h], 6
0x18007d3b8  jb      loc_18007D4E1
0x18007d3be  mov     edx, 8Fh
0x18007d3c3  jmp     loc_18007D4D2
0x18007d3c8  mov     eax, [rbx]
0x18007d3ca  lea     rcx, [rbp+14h]
0x18007d3ce  mov     [rsp+98h+OutputBufferLength], eax; OutputBufferLength
0x18007d3d2  xor     r9d, r9d; ApcContext
0x18007d3d5  mov     [rsp+98h+OutputBuffer], rdi; OutputBuffer
0x18007d3da  lea     rax, [rsp+98h+var_48]
0x18007d3df  mov     [rsp+98h+InputBufferLength], 4; InputBufferLength
0x18007d3e7  xor     r8d, r8d; ApcRoutine
0x18007d3ea  mov     [rsp+98h+InputBuffer], rcx; InputBuffer
0x18007d3ef  mov     rdx, rsi; Event
0x18007d3f2  mov     rcx, cs:NatFileHandle; FileHandle
0x18007d3f9  mov     [rsp+98h+IoControlCode], 128024h; IoControlCode
0x18007d401  mov     [rsp+98h+IoStatusBlock], rax; IoStatusBlock
0x18007d406  call    cs:__imp_NtDeviceIoControlFile
0x18007d40d  nop     dword ptr [rax+rax+00h]
0x18007d412  mov     edi, eax
0x18007d414  cmp     eax, 103h
0x18007d419  jnz     short loc_18007D431
0x18007d41b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18007d41e  mov     rcx, rsi; hHandle
0x18007d421  call    cs:__imp_WaitForSingleObject
0x18007d428  nop     dword ptr [rax+rax+00h]
0x18007d42d  mov     edi, dword ptr [rsp+98h+var_48]
0x18007d431  mov     rcx, rsi; hObject
0x18007d434  call    cs:__imp_CloseHandle
0x18007d43b  nop     dword ptr [rax+rax+00h]
0x18007d440  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007d447  call    cs:__imp_LeaveCriticalSection
0x18007d44e  nop     dword ptr [rax+rax+00h]
0x18007d453  mov     rcx, [rsp+98h+var_48.Information]
0x18007d458  test    edi, edi
0x18007d45a  js      short loc_18007D49B
0x18007d45c  mov     eax, [rbx]
0x18007d45e  cmp     rcx, rax
0x18007d461  jbe     short loc_18007D49B
0x18007d463  mov     [rbx], ecx
0x18007d465  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d46c  cmp     rcx, r15
0x18007d46f  jz      short loc_18007D494
0x18007d471  test    [rcx+1Ch], r14d
0x18007d475  jz      short loc_18007D494
0x18007d477  cmp     byte ptr [rcx+19h], 6
0x18007d47b  jb      short loc_18007D494
0x18007d47d  mov     edx, 90h
0x18007d482  mov     rcx, [rcx+10h]
0x18007d486  mov     r9d, 7Ah ; 'z'
0x18007d48c  mov     r8, r12
0x18007d48f  call    WPP_SF_d
0x18007d494  mov     eax, 7Ah ; 'z'
0x18007d499  jmp     short loc_18007D4E3
0x18007d49b  mov     [rbx], ecx
0x18007d49d  test    edi, edi
0x18007d49f  js      short loc_18007D4A5
0x18007d4a1  xor     ebx, ebx
0x18007d4a3  jmp     short loc_18007D4B5
0x18007d4a5  mov     ecx, edi; Status
0x18007d4a7  call    cs:__imp_RtlNtStatusToDosError
0x18007d4ae  nop     dword ptr [rax+rax+00h]
0x18007d4b3  mov     ebx, eax
0x18007d4b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d4bc  cmp     rcx, r15
0x18007d4bf  jz      short loc_18007D4E1
0x18007d4c1  test    [rcx+1Ch], r14d
0x18007d4c5  jz      short loc_18007D4E1
0x18007d4c7  cmp     byte ptr [rcx+19h], 6
0x18007d4cb  jb      short loc_18007D4E1
0x18007d4cd  mov     edx, 91h
0x18007d4d2  mov     rcx, [rcx+10h]
0x18007d4d6  mov     r9d, ebx
0x18007d4d9  mov     r8, r12
0x18007d4dc  call    WPP_SF_d
0x18007d4e1  mov     eax, ebx
0x18007d4e3  add     rsp, 60h
0x18007d4e7  pop     r15
0x18007d4e9  pop     r14
0x18007d4eb  pop     r12
0x18007d4ed  pop     rdi
0x18007d4ee  pop     rsi
0x18007d4ef  pop     rbp
0x18007d4f0  pop     rbx
0x18007d4f1  retn
```
