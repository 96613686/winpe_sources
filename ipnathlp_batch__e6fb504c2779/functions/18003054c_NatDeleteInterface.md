# NatDeleteInterface

- ea: `0x18003054c`
- end: `0x1800309b7`
- name: `NatDeleteInterface`
- size: `1131`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `5`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18004ba34`
- `0x18004f3e8`
- `0x180078a60`
- `0x18007ec14`
- `0x18007f288`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x1800202e0`
- `0x18003054c`
- `0x1800309c0`
- `0x180030c14`
- `0x180059a04`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800307df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800307ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800307df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800307ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800307f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030813`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800307f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030813`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003064f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003064f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800308a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030927`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800308a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030927`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800305bc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800305bc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003074b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003074b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800305e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800305e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800307a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030936`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800307a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030936`
- `ntdll!NtDeviceIoControlFile` at `0x180030730`
- `ntdll!NtDeviceIoControlFile` at `0x180030730`
- `ntdll!RtlNtStatusToDosError` at `0x180030761`
- `ntdll!RtlNtStatusToDosError` at `0x180030761`

## pseudocode

```c
__int64 __fastcall NatDeleteInterface(unsigned int a1, int a2)
{
  HANDLE EventW; // r14
  PVOID *v5; // rcx
  DWORD LastError; // eax
  PVOID *v8; // rcx
  LPVOID *i; // rbx
  ULONG v10; // edi
  int Status; // esi
  ULONG v12; // eax
  _QWORD *v13; // rcx
  LPVOID *v14; // rax
  void *v15; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v17; // rax
  PVOID *v18; // rcx
  PVOID *v19; // rcx
  int IoStatusBlock; // [rsp+20h] [rbp-78h]
  struct _IO_STATUS_BLOCK v21; // [rsp+50h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_Dc(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, a1, a2 != 0);
  }
  v21 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    if ( !a2 )
      EnterCriticalSection(&NatInterfaceLock);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, a1);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    for ( i = (LPVOID *)NatInterfaceList; ; i = (LPVOID *)*i )
    {
      if ( i == &NatInterfaceList )
        goto LABEL_59;
      if ( a1 <= *((_DWORD *)i + 4) )
        break;
    }
    if ( a1 < *((_DWORD *)i + 4) )
    {
LABEL_59:
      if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x200) != 0 && *((_BYTE *)v8 + 25) >= 6u )
        WPP_SF_d(v8[2], 113, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, a1);
      goto LABEL_63;
    }
    if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x200) != 0 && *((_BYTE *)v8 + 25) >= 6u )
      WPP_SF_d(v8[2], 112, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, a1);
    if ( i )
    {
      v10 = 0;
      if ( (*((_DWORD *)i + 7) & 0x40000000) != 0 )
      {
        Status = NtDeviceIoControlFile(NatFileHandle, EventW, 0, 0, &v21, 0x12800Cu, (char *)i + 20, 4u, 0, 0);
        if ( Status == 259 )
        {
          WaitForSingleObject(EventW, 0xFFFFFFFF);
          Status = v21.Status;
        }
        if ( Status < 0 )
        {
          v12 = RtlNtStatusToDosError(Status);
          v10 = v12;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              90,
              &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids,
              (unsigned int)Status,
              v12);
          }
        }
      }
      CloseHandle(EventW);
      v13 = *i;
      if ( *((LPVOID **)*i + 1) != i || (v14 = (LPVOID *)i[1], *v14 != i) )
        __fastfail(3u);
      *v14 = v13;
      v13[1] = v14;
      v15 = i[4];
      if ( v15 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v15);
      }
      v17 = GetProcessHeap();
      HeapFree(v17, 0, i);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        LOBYTE(IoStatusBlock) = 0;
        WPP_SF_Dc(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          116,
          &WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids,
          a1,
          IoStatusBlock);
      }
      DhcpSignalNatInterface(a1, 0);
      DnsSignalNatInterface(a1, 0);
      v18 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, &WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids);
        v18 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( !a2 )
      {
        LeaveCriticalSection(&NatInterfaceLock);
        v18 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v18 != &WPP_GLOBAL_Control && (*((_DWORD *)v18 + 7) & 0x200) != 0 && *((_BYTE *)v18 + 25) >= 6u )
        WPP_SF_d(v18[2], 91, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, v10);
      return v10;
    }
LABEL_63:
    if ( !a2 )
      LeaveCriticalSection(&NatInterfaceLock);
    CloseHandle(EventW);
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, a1);
        v19 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v19 != &WPP_GLOBAL_Control && (*((_DWORD *)v19 + 7) & 0x200) != 0 && *((_BYTE *)v19 + 25) >= 6u )
        WPP_SF_d(v19[2], 89, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, 905);
    }
    return 905;
  }
  else
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, LastError);
        v5 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x200) != 0 && *((_BYTE *)v5 + 25) >= 6u )
        WPP_SF_d(v5[2], 87, &WPP_1a1a310d9f3938633825d91885f62d23_Traceguids, 8);
    }
    return 8;
  }
}

```

## disassembly

```asm
0x18003054c  push    rbx
0x18003054e  push    rbp
0x18003054f  push    rsi
0x180030550  push    rdi
0x180030551  push    r13
0x180030553  push    r14
0x180030555  push    r15
0x180030557  sub     rsp, 60h
0x18003055b  mov     r15d, edx
0x18003055e  mov     ebp, ecx
0x180030560  mov     rcx, cs:WPP_GLOBAL_Control
0x180030567  lea     r13, WPP_GLOBAL_Control
0x18003056e  lea     rbx, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x180030575  mov     sil, 6
0x180030578  mov     edi, 200h
0x18003057d  cmp     rcx, r13
0x180030580  jz      short loc_1800305AA
0x180030582  test    [rcx+1Ch], edi
0x180030585  jz      short loc_1800305AA
0x180030587  cmp     [rcx+19h], sil
0x18003058b  jb      short loc_1800305AA
0x18003058d  mov     rcx, [rcx+10h]
0x180030591  test    edx, edx
0x180030593  mov     edx, 55h ; 'U'
0x180030598  mov     r9d, ebp
0x18003059b  setnz   al
0x18003059e  mov     r8, rbx
0x1800305a1  mov     byte ptr [rsp+98h+IoStatusBlock], al
0x1800305a5  call    WPP_SF_Dc
0x1800305aa  xorps   xmm0, xmm0
0x1800305ad  xor     r9d, r9d; lpName
0x1800305b0  xor     r8d, r8d; bInitialState
0x1800305b3  xor     edx, edx; bManualReset
0x1800305b5  xor     ecx, ecx; lpEventAttributes
0x1800305b7  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x1800305bc  call    cs:__imp_CreateEventW
0x1800305c3  nop     dword ptr [rax+rax+00h]
0x1800305c8  mov     r14, rax
0x1800305cb  test    rax, rax
0x1800305ce  jnz     short loc_180030643
0x1800305d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800305d7  cmp     rcx, r13
0x1800305da  jz      short loc_180030639
0x1800305dc  test    [rcx+1Ch], edi
0x1800305df  jz      short loc_180030614
0x1800305e1  cmp     byte ptr [rcx+19h], 2
0x1800305e5  jb      short loc_180030614
0x1800305e7  call    cs:__imp_GetLastError
0x1800305ee  nop     dword ptr [rax+rax+00h]
0x1800305f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800305fa  lea     edx, [r14+56h]
0x1800305fe  mov     r9d, eax
0x180030601  mov     r8, rbx
0x180030604  mov     rcx, [rcx+10h]
0x180030608  call    WPP_SF_d
0x18003060d  mov     rcx, cs:WPP_GLOBAL_Control
0x180030614  cmp     rcx, r13
0x180030617  jz      short loc_180030639
0x180030619  test    [rcx+1Ch], edi
0x18003061c  jz      short loc_180030639
0x18003061e  cmp     [rcx+19h], sil
0x180030622  jb      short loc_180030639
0x180030624  mov     rcx, [rcx+10h]
0x180030628  mov     edx, 57h ; 'W'
0x18003062d  mov     r8, rbx
0x180030630  lea     r9d, [rdx-4Fh]
0x180030634  call    WPP_SF_d
0x180030639  mov     eax, 8
0x18003063e  jmp     loc_1800309A7
0x180030643  test    r15d, r15d
0x180030646  jnz     short loc_18003065B
0x180030648  lea     rcx, NatInterfaceLock; lpCriticalSection
0x18003064f  call    cs:__imp_EnterCriticalSection
0x180030656  nop     dword ptr [rax+rax+00h]
0x18003065b  mov     rcx, cs:WPP_GLOBAL_Control
0x180030662  cmp     rcx, r13
0x180030665  jz      short loc_18003068D
0x180030667  test    [rcx+1Ch], edi
0x18003066a  jz      short loc_18003068D
0x18003066c  cmp     [rcx+19h], sil
0x180030670  jb      short loc_18003068D
0x180030672  mov     rcx, [rcx+10h]
0x180030676  mov     edx, 6Fh ; 'o'
0x18003067b  mov     r9d, ebp
0x18003067e  mov     r8, rbx
0x180030681  call    WPP_SF_d
0x180030686  mov     rcx, cs:WPP_GLOBAL_Control
0x18003068d  mov     rbx, cs:NatInterfaceList
0x180030694  lea     rax, NatInterfaceList
0x18003069b  cmp     rbx, rax
0x18003069e  jz      loc_1800308F3
0x1800306a4  cmp     ebp, [rbx+10h]
0x1800306a7  jbe     short loc_1800306AE
0x1800306a9  mov     rbx, [rbx]
0x1800306ac  jmp     short loc_180030694
0x1800306ae  jb      loc_1800308F3
0x1800306b4  cmp     rcx, r13
0x1800306b7  jz      short loc_1800306DC
0x1800306b9  test    [rcx+1Ch], edi
0x1800306bc  jz      short loc_1800306DC
0x1800306be  cmp     [rcx+19h], sil
0x1800306c2  jb      short loc_1800306DC
0x1800306c4  mov     rcx, [rcx+10h]
0x1800306c8  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x1800306cf  mov     edx, 70h ; 'p'
0x1800306d4  mov     r9d, ebp
0x1800306d7  call    WPP_SF_d
0x1800306dc  test    rbx, rbx
0x1800306df  jz      loc_18003091B
0x1800306e5  xor     edi, edi
0x1800306e7  test    dword ptr [rbx+1Ch], 40000000h
0x1800306ee  jz      loc_1800307A6
0x1800306f4  mov     rcx, cs:NatFileHandle; FileHandle
0x1800306fb  lea     rax, [rbx+14h]
0x1800306ff  mov     [rsp+98h+OutputBufferLength], edi; OutputBufferLength
0x180030703  xor     r9d, r9d; ApcContext
0x180030706  mov     [rsp+98h+OutputBuffer], rdi; OutputBuffer
0x18003070b  xor     r8d, r8d; ApcRoutine
0x18003070e  mov     [rsp+98h+InputBufferLength], 4; InputBufferLength
0x180030716  mov     rdx, r14; Event
0x180030719  mov     [rsp+98h+InputBuffer], rax; InputBuffer
0x18003071e  lea     rax, [rsp+98h+var_48]
0x180030723  mov     [rsp+98h+IoControlCode], 12800Ch; IoControlCode
0x18003072b  mov     [rsp+98h+IoStatusBlock], rax; IoStatusBlock
0x180030730  call    cs:__imp_NtDeviceIoControlFile
0x180030737  nop     dword ptr [rax+rax+00h]
0x18003073c  mov     esi, eax
0x18003073e  cmp     eax, 103h
0x180030743  jnz     short loc_18003075B
0x180030745  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180030748  mov     rcx, r14; hHandle
0x18003074b  call    cs:__imp_WaitForSingleObject
0x180030752  nop     dword ptr [rax+rax+00h]
0x180030757  mov     esi, dword ptr [rsp+98h+var_48]
0x18003075b  test    esi, esi
0x18003075d  jns     short loc_1800307A6
0x18003075f  mov     ecx, esi; Status
0x180030761  call    cs:__imp_RtlNtStatusToDosError
0x180030768  nop     dword ptr [rax+rax+00h]
0x18003076d  mov     edi, eax
0x18003076f  mov     rcx, cs:WPP_GLOBAL_Control
0x180030776  cmp     rcx, r13
0x180030779  jz      short loc_1800307A6
0x18003077b  test    dword ptr [rcx+1Ch], 200h
0x180030782  jz      short loc_1800307A6
0x180030784  cmp     byte ptr [rcx+19h], 2
0x180030788  jb      short loc_1800307A6
0x18003078a  mov     rcx, [rcx+10h]
0x18003078e  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x180030795  mov     edx, 5Ah ; 'Z'
0x18003079a  mov     dword ptr [rsp+98h+IoStatusBlock], eax
0x18003079e  mov     r9d, esi
0x1800307a1  call    WPP_SF_Dd
0x1800307a6  mov     rcx, r14; hObject
0x1800307a9  call    cs:__imp_CloseHandle
0x1800307b0  nop     dword ptr [rax+rax+00h]
0x1800307b5  mov     rcx, [rbx]
0x1800307b8  cmp     [rcx+8], rbx
0x1800307bc  jnz     loc_1800308EC
0x1800307c2  mov     rax, [rbx+8]
0x1800307c6  cmp     [rax], rbx
0x1800307c9  jnz     loc_1800308EC
0x1800307cf  mov     [rax], rcx
0x1800307d2  mov     [rcx+8], rax
0x1800307d6  mov     rsi, [rbx+20h]
0x1800307da  test    rsi, rsi
0x1800307dd  jz      short loc_1800307FF
0x1800307df  call    cs:__imp_GetProcessHeap
0x1800307e6  nop     dword ptr [rax+rax+00h]
0x1800307eb  mov     r8, rsi; lpMem
0x1800307ee  xor     edx, edx; dwFlags
0x1800307f0  mov     rcx, rax; hHeap
0x1800307f3  call    cs:__imp_HeapFree
0x1800307fa  nop     dword ptr [rax+rax+00h]
0x1800307ff  call    cs:__imp_GetProcessHeap
0x180030806  nop     dword ptr [rax+rax+00h]
0x18003080b  mov     r8, rbx; lpMem
0x18003080e  xor     edx, edx; dwFlags
0x180030810  mov     rcx, rax; hHeap
0x180030813  call    cs:__imp_HeapFree
0x18003081a  nop     dword ptr [rax+rax+00h]
0x18003081f  mov     rcx, cs:WPP_GLOBAL_Control
0x180030826  cmp     rcx, r13
0x180030829  jz      short loc_180030854
0x18003082b  test    byte ptr [rcx+1Ch], 8
0x18003082f  jz      short loc_180030854
0x180030831  cmp     byte ptr [rcx+19h], 6
0x180030835  jb      short loc_180030854
0x180030837  mov     rcx, [rcx+10h]
0x18003083b  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180030842  mov     edx, 74h ; 't'
0x180030847  mov     byte ptr [rsp+98h+IoStatusBlock], 0
0x18003084c  mov     r9d, ebp
0x18003084f  call    WPP_SF_Dc
0x180030854  xor     edx, edx; unsigned __int8
0x180030856  mov     ecx, ebp; unsigned int
0x180030858  call    ?DhcpSignalNatInterface@@YAXKE@Z; DhcpSignalNatInterface(ulong,uchar)
0x18003085d  xor     edx, edx; unsigned __int8
0x18003085f  mov     ecx, ebp; unsigned int
0x180030861  call    ?DnsSignalNatInterface@@YAXKE@Z; DnsSignalNatInterface(ulong,uchar)
0x180030866  mov     rcx, cs:WPP_GLOBAL_Control
0x18003086d  cmp     rcx, r13
0x180030870  jz      short loc_18003089A
0x180030872  test    byte ptr [rcx+1Ch], 8
0x180030876  jz      short loc_18003089A
0x180030878  cmp     byte ptr [rcx+19h], 6
0x18003087c  jb      short loc_18003089A
0x18003087e  mov     rcx, [rcx+10h]
0x180030882  lea     r8, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180030889  mov     edx, 75h ; 'u'
0x18003088e  call    WPP_SF_
0x180030893  mov     rcx, cs:WPP_GLOBAL_Control
0x18003089a  test    r15d, r15d
0x18003089d  jnz     short loc_1800308B9
0x18003089f  lea     rcx, NatInterfaceLock; lpCriticalSection
0x1800308a6  call    cs:__imp_LeaveCriticalSection
0x1800308ad  nop     dword ptr [rax+rax+00h]
0x1800308b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800308b9  cmp     rcx, r13
0x1800308bc  jz      short loc_1800308E5
0x1800308be  test    dword ptr [rcx+1Ch], 200h
0x1800308c5  jz      short loc_1800308E5
0x1800308c7  cmp     byte ptr [rcx+19h], 6
0x1800308cb  jb      short loc_1800308E5
0x1800308cd  mov     rcx, [rcx+10h]
0x1800308d1  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x1800308d8  mov     edx, 5Bh ; '['
0x1800308dd  mov     r9d, edi
0x1800308e0  call    WPP_SF_d
0x1800308e5  mov     eax, edi
0x1800308e7  jmp     loc_1800309A7
0x1800308ec  mov     ecx, 3
0x1800308f1  int     29h; Win8: RtlFailFast(ecx)
0x1800308f3  cmp     rcx, r13
0x1800308f6  jz      short loc_18003091B
0x1800308f8  test    [rcx+1Ch], edi
0x1800308fb  jz      short loc_18003091B
0x1800308fd  cmp     [rcx+19h], sil
0x180030901  jb      short loc_18003091B
0x180030903  mov     rcx, [rcx+10h]
0x180030907  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x18003090e  mov     edx, 71h ; 'q'
0x180030913  mov     r9d, ebp
0x180030916  call    WPP_SF_d
0x18003091b  test    r15d, r15d
0x18003091e  jnz     short loc_180030933
0x180030920  lea     rcx, NatInterfaceLock; lpCriticalSection
0x180030927  call    cs:__imp_LeaveCriticalSection
0x18003092e  nop     dword ptr [rax+rax+00h]
0x180030933  mov     rcx, r14; hObject
0x180030936  call    cs:__imp_CloseHandle
0x18003093d  nop     dword ptr [rax+rax+00h]
0x180030942  mov     rcx, cs:WPP_GLOBAL_Control
0x180030949  mov     ebx, 389h
0x18003094e  cmp     rcx, r13
0x180030951  jz      short loc_1800309A5
0x180030953  test    [rcx+1Ch], edi
0x180030956  jz      short loc_18003097D
0x180030958  cmp     byte ptr [rcx+19h], 2
0x18003095c  jb      short loc_18003097D
0x18003095e  mov     rcx, [rcx+10h]
0x180030962  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x180030969  mov     edx, 58h ; 'X'
0x18003096e  mov     r9d, ebp
0x180030971  call    WPP_SF_d
0x180030976  mov     rcx, cs:WPP_GLOBAL_Control
0x18003097d  cmp     rcx, r13
0x180030980  jz      short loc_1800309A5
0x180030982  test    [rcx+1Ch], edi
0x180030985  jz      short loc_1800309A5
0x180030987  cmp     [rcx+19h], sil
0x18003098b  jb      short loc_1800309A5
0x18003098d  mov     rcx, [rcx+10h]
0x180030991  lea     r8, WPP_1a1a310d9f3938633825d91885f62d23_Traceguids
0x180030998  mov     edx, 59h ; 'Y'
0x18003099d  mov     r9d, ebx
0x1800309a0  call    WPP_SF_d
0x1800309a5  mov     eax, ebx
0x1800309a7  add     rsp, 60h
0x1800309ab  pop     r15
0x1800309ad  pop     r14
0x1800309af  pop     r13
0x1800309b1  pop     rdi
0x1800309b2  pop     rsi
0x1800309b3  pop     rbp
0x1800309b4  pop     rbx
0x1800309b5  retn
```
