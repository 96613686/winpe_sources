# NatQueryStatisticsInterface

- ea: `0x1800771dc`
- end: `0x180077504`
- name: `NatQueryStatisticsInterface`
- size: `808`
- prototype: `__int64 __fastcall(unsigned int, PVOID OutputBuffer)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180073600`

## callees

- `0x18000c750`
- `0x180032e10`
- `0x1800771dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077242`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077242`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077260`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800772dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077384`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077465`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077260`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800772dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077384`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077465`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007736f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007736f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007744b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007744b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800773a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800773a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180077458`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180077458`
- `ntdll!NtDeviceIoControlFile` at `0x180077436`
- `ntdll!NtDeviceIoControlFile` at `0x180077436`
- `ntdll!RtlNtStatusToDosError` at `0x1800774bf`
- `ntdll!RtlNtStatusToDosError` at `0x1800774bf`

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
0x1800771dc  push    rbx
0x1800771de  push    rbp
0x1800771df  push    rsi
0x1800771e0  push    rdi
0x1800771e1  push    r12
0x1800771e3  push    r14
0x1800771e5  push    r15
0x1800771e7  sub     rsp, 60h
0x1800771eb  mov     rbx, r8
0x1800771ee  mov     rdi, rdx
0x1800771f1  mov     esi, ecx
0x1800771f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800771fa  lea     r15, WPP_GLOBAL_Control
0x180077201  lea     r12, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x180077208  mov     r14d, 200h
0x18007720e  cmp     rcx, r15
0x180077211  jz      short loc_180077233
0x180077213  test    [rcx+1Ch], r14d
0x180077217  jz      short loc_180077233
0x180077219  cmp     byte ptr [rcx+19h], 6
0x18007721d  jb      short loc_180077233
0x18007721f  mov     rcx, [rcx+10h]
0x180077223  mov     edx, 89h
0x180077228  mov     r9d, esi
0x18007722b  mov     r8, r12
0x18007722e  call    WPP_SF_d
0x180077233  xorps   xmm0, xmm0
0x180077236  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18007723d  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x180077242  call    cs:__imp_EnterCriticalSection
0x180077248  xor     edx, edx; struct _LIST_ENTRY **
0x18007724a  mov     ecx, esi; unsigned int
0x18007724c  call    ?NatLookupInterface@@YAPEAU_NAT_INTERFACE@@KPEAPEAU_LIST_ENTRY@@@Z; NatLookupInterface(ulong,_LIST_ENTRY * *)
0x180077251  mov     rbp, rax
0x180077254  test    rax, rax
0x180077257  jnz     short loc_1800772C9
0x180077259  lea     rcx, NatInterfaceLock; lpCriticalSection
0x180077260  call    cs:__imp_LeaveCriticalSection
0x180077266  mov     rcx, cs:WPP_GLOBAL_Control
0x18007726d  mov     ebx, 389h
0x180077272  cmp     rcx, r15
0x180077275  jz      loc_1800774F3
0x18007727b  test    [rcx+1Ch], r14d
0x18007727f  jz      short loc_1800772A2
0x180077281  cmp     byte ptr [rcx+19h], 2
0x180077285  jb      short loc_1800772A2
0x180077287  mov     rcx, [rcx+10h]
0x18007728b  mov     edx, 8Ah
0x180077290  mov     r9d, esi
0x180077293  mov     r8, r12
0x180077296  call    WPP_SF_d
0x18007729b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800772a2  cmp     rcx, r15
0x1800772a5  jz      loc_1800774F3
0x1800772ab  test    [rcx+1Ch], r14d
0x1800772af  jz      loc_1800774F3
0x1800772b5  cmp     byte ptr [rcx+19h], 6
0x1800772b9  jb      loc_1800774F3
0x1800772bf  mov     edx, 8Bh
0x1800772c4  jmp     loc_1800774E4
0x1800772c9  test    dword ptr [rax+1Ch], 40000000h
0x1800772d0  jnz     loc_180077365
0x1800772d6  lea     rcx, NatInterfaceLock; lpCriticalSection
0x1800772dd  call    cs:__imp_LeaveCriticalSection
0x1800772e3  mov     eax, [rbx]
0x1800772e5  mov     dword ptr [rbx], 38h ; '8'
0x1800772eb  cmp     eax, 38h ; '8'
0x1800772ee  jnb     short loc_18007731E
0x1800772f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800772f7  cmp     rcx, r15
0x1800772fa  jz      loc_1800774AC
0x180077300  test    [rcx+1Ch], r14d
0x180077304  jz      loc_1800774AC
0x18007730a  cmp     byte ptr [rcx+19h], 6
0x18007730e  jb      loc_1800774AC
0x180077314  mov     edx, 8Ch
0x180077319  jmp     loc_18007749A
0x18007731e  xorps   xmm0, xmm0
0x180077321  xor     eax, eax
0x180077323  movups  xmmword ptr [rdi], xmm0
0x180077326  movups  xmmword ptr [rdi+10h], xmm0
0x18007732a  movups  xmmword ptr [rdi+20h], xmm0
0x18007732e  mov     [rdi+30h], rax
0x180077332  mov     rcx, cs:WPP_GLOBAL_Control
0x180077339  cmp     rcx, r15
0x18007733c  jz      short loc_18007735E
0x18007733e  test    [rcx+1Ch], r14d
0x180077342  jz      short loc_18007735E
0x180077344  cmp     byte ptr [rcx+19h], 6
0x180077348  jb      short loc_18007735E
0x18007734a  mov     rcx, [rcx+10h]
0x18007734e  mov     edx, 8Dh
0x180077353  xor     r9d, r9d
0x180077356  mov     r8, r12
0x180077359  call    WPP_SF_d
0x18007735e  xor     eax, eax
0x180077360  jmp     loc_1800774F5
0x180077365  xor     r9d, r9d; lpName
0x180077368  xor     r8d, r8d; bInitialState
0x18007736b  xor     edx, edx; bManualReset
0x18007736d  xor     ecx, ecx; lpEventAttributes
0x18007736f  call    cs:__imp_CreateEventW
0x180077375  mov     rsi, rax
0x180077378  test    rax, rax
0x18007737b  jnz     short loc_1800773F8
0x18007737d  lea     rcx, NatInterfaceLock; lpCriticalSection
0x180077384  call    cs:__imp_LeaveCriticalSection
0x18007738a  mov     rcx, cs:WPP_GLOBAL_Control
0x180077391  lea     ebx, [rsi+8]
0x180077394  cmp     rcx, r15
0x180077397  jz      loc_1800774F3
0x18007739d  test    [rcx+1Ch], r14d
0x1800773a1  jz      short loc_1800773D1
0x1800773a3  cmp     byte ptr [rcx+19h], 2
0x1800773a7  jb      short loc_1800773D1
0x1800773a9  call    cs:__imp_GetLastError
0x1800773af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800773b6  mov     edx, 8Eh
0x1800773bb  mov     r9d, eax
0x1800773be  mov     r8, r12
0x1800773c1  mov     rcx, [rcx+10h]
0x1800773c5  call    WPP_SF_d
0x1800773ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800773d1  cmp     rcx, r15
0x1800773d4  jz      loc_1800774F3
0x1800773da  test    [rcx+1Ch], r14d
0x1800773de  jz      loc_1800774F3
0x1800773e4  cmp     byte ptr [rcx+19h], 6
0x1800773e8  jb      loc_1800774F3
0x1800773ee  mov     edx, 8Fh
0x1800773f3  jmp     loc_1800774E4
0x1800773f8  mov     eax, [rbx]
0x1800773fa  lea     rcx, [rbp+14h]
0x1800773fe  mov     [rsp+98h+OutputBufferLength], eax; OutputBufferLength
0x180077402  xor     r9d, r9d; ApcContext
0x180077405  mov     [rsp+98h+OutputBuffer], rdi; OutputBuffer
0x18007740a  lea     rax, [rsp+98h+var_48]
0x18007740f  mov     [rsp+98h+InputBufferLength], 4; InputBufferLength
0x180077417  xor     r8d, r8d; ApcRoutine
0x18007741a  mov     [rsp+98h+InputBuffer], rcx; InputBuffer
0x18007741f  mov     rdx, rsi; Event
0x180077422  mov     rcx, cs:NatFileHandle; FileHandle
0x180077429  mov     [rsp+98h+IoControlCode], 128024h; IoControlCode
0x180077431  mov     [rsp+98h+IoStatusBlock], rax; IoStatusBlock
0x180077436  call    cs:__imp_NtDeviceIoControlFile
0x18007743c  mov     edi, eax
0x18007743e  cmp     eax, 103h
0x180077443  jnz     short loc_180077455
0x180077445  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180077448  mov     rcx, rsi; hHandle
0x18007744b  call    cs:__imp_WaitForSingleObject
0x180077451  mov     edi, dword ptr [rsp+98h+var_48]
0x180077455  mov     rcx, rsi; hObject
0x180077458  call    cs:__imp_CloseHandle
0x18007745e  lea     rcx, NatInterfaceLock; lpCriticalSection
0x180077465  call    cs:__imp_LeaveCriticalSection
0x18007746b  mov     rcx, [rsp+98h+var_48.Information]
0x180077470  test    edi, edi
0x180077472  js      short loc_1800774B3
0x180077474  mov     eax, [rbx]
0x180077476  cmp     rcx, rax
0x180077479  jbe     short loc_1800774B3
0x18007747b  mov     [rbx], ecx
0x18007747d  mov     rcx, cs:WPP_GLOBAL_Control
0x180077484  cmp     rcx, r15
0x180077487  jz      short loc_1800774AC
0x180077489  test    [rcx+1Ch], r14d
0x18007748d  jz      short loc_1800774AC
0x18007748f  cmp     byte ptr [rcx+19h], 6
0x180077493  jb      short loc_1800774AC
0x180077495  mov     edx, 90h
0x18007749a  mov     rcx, [rcx+10h]
0x18007749e  mov     r9d, 7Ah ; 'z'
0x1800774a4  mov     r8, r12
0x1800774a7  call    WPP_SF_d
0x1800774ac  mov     eax, 7Ah ; 'z'
0x1800774b1  jmp     short loc_1800774F5
0x1800774b3  mov     [rbx], ecx
0x1800774b5  test    edi, edi
0x1800774b7  js      short loc_1800774BD
0x1800774b9  xor     ebx, ebx
0x1800774bb  jmp     short loc_1800774C7
0x1800774bd  mov     ecx, edi; Status
0x1800774bf  call    cs:__imp_RtlNtStatusToDosError
0x1800774c5  mov     ebx, eax
0x1800774c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800774ce  cmp     rcx, r15
0x1800774d1  jz      short loc_1800774F3
0x1800774d3  test    [rcx+1Ch], r14d
0x1800774d7  jz      short loc_1800774F3
0x1800774d9  cmp     byte ptr [rcx+19h], 6
0x1800774dd  jb      short loc_1800774F3
0x1800774df  mov     edx, 91h
0x1800774e4  mov     rcx, [rcx+10h]
0x1800774e8  mov     r9d, ebx
0x1800774eb  mov     r8, r12
0x1800774ee  call    WPP_SF_d
0x1800774f3  mov     eax, ebx
0x1800774f5  add     rsp, 60h
0x1800774f9  pop     r15
0x1800774fb  pop     r14
0x1800774fd  pop     r12
0x1800774ff  pop     rdi
0x180077500  pop     rsi
0x180077501  pop     rbp
0x180077502  pop     rbx
0x180077503  retn
```
