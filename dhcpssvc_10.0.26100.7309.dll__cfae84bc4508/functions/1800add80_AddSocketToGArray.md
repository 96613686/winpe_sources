# AddSocketToGArray

- ea: `0x1800add80`
- end: `0x1800ae114`
- name: `AddSocketToGArray`
- size: `916`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800ae358`
- `0x1800afd9c`

## callees

- `0x18000323c`
- `0x18001ceb4`
- `0x1800add80`

## import_xrefs

- `WS2_32!WSAEventSelect` at `0x1800adf4c`
- `WS2_32!WSAEventSelect` at `0x1800adf4c`
- `WS2_32!WSACloseEvent` at `0x1800adff5`
- `WS2_32!WSACloseEvent` at `0x1800ae032`
- `WS2_32!WSACloseEvent` at `0x1800ae06e`
- `WS2_32!WSACloseEvent` at `0x1800adff5`
- `WS2_32!WSACloseEvent` at `0x1800ae032`
- `WS2_32!WSACloseEvent` at `0x1800ae06e`
- `WS2_32!WSACreateEvent` at `0x1800adeb3`
- `WS2_32!WSACreateEvent` at `0x1800adef2`
- `WS2_32!WSACreateEvent` at `0x1800adf1b`
- `WS2_32!WSACreateEvent` at `0x1800adeb3`
- `WS2_32!WSACreateEvent` at `0x1800adef2`
- `WS2_32!WSACreateEvent` at `0x1800adf1b`
- `WS2_32!__imp_WSAGetLastError` at `0x1800adec8`
- `WS2_32!__imp_WSAGetLastError` at `0x1800adf07`
- `WS2_32!__imp_WSAGetLastError` at `0x1800adf2f`
- `WS2_32!__imp_WSAGetLastError` at `0x1800adf5f`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae005`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae042`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae07e`
- `WS2_32!__imp_WSAGetLastError` at `0x1800adec8`
- `WS2_32!__imp_WSAGetLastError` at `0x1800adf07`
- `WS2_32!__imp_WSAGetLastError` at `0x1800adf2f`
- `WS2_32!__imp_WSAGetLastError` at `0x1800adf5f`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae005`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae042`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae07e`
- `WS2_32!__imp_WSASetLastError` at `0x1800addb1`
- `WS2_32!__imp_WSASetLastError` at `0x1800ae0eb`
- `WS2_32!__imp_WSASetLastError` at `0x1800addb1`
- `WS2_32!__imp_WSASetLastError` at `0x1800ae0eb`
- `KERNEL32!HeapAlloc` at `0x1800addd4`
- `KERNEL32!HeapAlloc` at `0x1800addd4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800adfd1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800adfd1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800adfab`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800adfab`
- `KERNEL32!EnterCriticalSection` at `0x1800ade13`
- `KERNEL32!EnterCriticalSection` at `0x1800ae0a4`
- `KERNEL32!EnterCriticalSection` at `0x1800ade13`
- `KERNEL32!EnterCriticalSection` at `0x1800ae0a4`
- `KERNEL32!LeaveCriticalSection` at `0x1800ade59`
- `KERNEL32!LeaveCriticalSection` at `0x1800ae0c3`
- `KERNEL32!LeaveCriticalSection` at `0x1800ade59`
- `KERNEL32!LeaveCriticalSection` at `0x1800ae0c3`
- `KERNEL32!HeapFree` at `0x1800ae0db`
- `KERNEL32!HeapFree` at `0x1800ae0db`

## string_xrefs

- `0x1800adeda`: `WSACreateEvent`
- `0x1800adfe9`: `WSACloseEvent`

## pseudocode

```c
_QWORD *__fastcall AddSocketToGArray(RTL_SRWLOCK *a1, SOCKET a2, int a3)
{
  void *v3; // r14
  int v7; // ecx
  _QWORD *v9; // rdi
  DWORD v10; // eax
  __int64 v11; // rax
  _DWORD *v12; // rcx
  _DWORD *v13; // rax
  int v14; // esi
  HANDLE v15; // rax
  unsigned int Error; // eax
  __int64 v17; // r9
  const char *v18; // r8
  HANDLE v19; // rax
  HANDLE v20; // rax
  __int64 v21; // rcx
  void *v22; // rcx
  unsigned int v23; // eax
  void *v24; // rcx
  unsigned int v25; // eax
  unsigned int v26; // eax

  v3 = 0;
  if ( gSocketEventTotal >= 0x40 )
  {
    v7 = 87;
LABEL_3:
    WSASetLastError(v7);
    return 0;
  }
  v9 = HeapAlloc(gDhcpHeap, 8u, 0x40u);
  if ( !v9 )
  {
    v7 = 8;
    goto LABEL_3;
  }
  v10 = gSocketEventTotal;
  v9[3] = 0;
  *((_DWORD *)v9 + 8) = 0;
  v9[2] = 0;
  *(_DWORD *)v9 = v10;
  *((_DWORD *)v9 + 1) = v10;
  v9[1] = a2;
  v9[7] = a1;
  EnterCriticalSection(&gSocketLock);
  v11 = 0;
  v12 = &gCMCritSecSendSocket;
  while ( *v12 )
  {
    v11 = (unsigned int)(v11 + 1);
    v12 += 12;
    if ( (unsigned int)v11 >= 0x40 )
      goto LABEL_11;
  }
  v13 = (_DWORD *)((char *)&gCMCritSecSendSocket + 48 * v11);
  v9[2] = v13;
  *v13 = 1;
LABEL_11:
  LeaveCriticalSection(&gSocketLock);
  if ( !v9[2] )
  {
    v14 = 8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids);
    goto LABEL_28;
  }
  v15 = WSACreateEvent();
  v9[5] = v15;
  if ( !v15 )
  {
    Error = WSAGetLastError();
    v17 = 224;
LABEL_17:
    v18 = "WSACreateEvent";
LABEL_18:
    v14 = Error;
    DhcpPrintFOErrorEx(Error, "AddSocketToGArray", v18, v17);
    goto LABEL_27;
  }
  v19 = WSACreateEvent();
  v9[6] = v19;
  if ( !v19 )
  {
    Error = WSAGetLastError();
    v17 = 225;
    goto LABEL_17;
  }
  v20 = WSACreateEvent();
  v3 = v20;
  if ( !v20 )
  {
    Error = WSAGetLastError();
    v17 = 229;
    goto LABEL_17;
  }
  v14 = WSAEventSelect(a2, v20, a3);
  if ( v14 == -1 )
  {
    Error = WSAGetLastError();
    v17 = 232;
    v18 = "WSAEventSelect";
    goto LABEL_18;
  }
  v21 = gSocketEventTotal;
  gSocketArray[gSocketEventTotal] = (__int64)v9;
  gSocketEventArray[v21] = v3;
  gSocketEventTotal = v21 + 1;
  if ( a1 )
  {
    AcquireSRWLockExclusive(a1 + 9);
    a1[60].Ptr = v9;
    a1[61].Ptr = (PVOID)(v9[2] + 8LL);
    ReleaseSRWLockExclusive(a1 + 9);
  }
LABEL_27:
  if ( v14 )
  {
LABEL_28:
    v22 = (void *)v9[5];
    if ( v22 )
    {
      if ( !WSACloseEvent(v22) )
      {
        v23 = WSAGetLastError();
        DhcpPrintFOErrorEx(v23, "AddSocketToGArray", "WSACloseEvent", 251);
      }
      v9[5] = 0;
    }
    v24 = (void *)v9[6];
    if ( v24 )
    {
      if ( !WSACloseEvent(v24) )
      {
        v25 = WSAGetLastError();
        DhcpPrintFOErrorEx(v25, "AddSocketToGArray", "WSACloseEvent", 252);
      }
      v9[6] = 0;
    }
    if ( v3 )
    {
      if ( !WSACloseEvent(v3) )
      {
        v26 = WSAGetLastError();
        DhcpPrintFOErrorEx(v26, "AddSocketToGArray", "WSACloseEvent", 253);
      }
    }
    EnterCriticalSection(&gSocketLock);
    *(_DWORD *)v9[2] = 0;
    v9[2] = 0;
    LeaveCriticalSection(&gSocketLock);
    HeapFree(gDhcpHeap, 0, v9);
    v9 = 0;
    WSASetLastError(v14);
  }
  return v9;
}

```

## disassembly

```asm
0x1800add80  mov     [rsp+arg_0], rbx
0x1800add85  mov     [rsp+arg_8], rbp
0x1800add8a  mov     [rsp+arg_10], rsi
0x1800add8f  push    rdi
0x1800add90  push    r12
0x1800add92  push    r14
0x1800add94  sub     rsp, 20h
0x1800add98  xor     r14d, r14d
0x1800add9b  mov     esi, r8d
0x1800add9e  cmp     cs:gSocketEventTotal, 40h ; '@'
0x1800adda5  mov     rbx, rdx
0x1800adda8  mov     rbp, rcx
0x1800addab  jb      short loc_1800ADDC4
0x1800addad  lea     ecx, [r14+57h]; iError
0x1800addb1  call    cs:__imp_WSASetLastError
0x1800addb8  nop     dword ptr [rax+rax+00h]
0x1800addbd  xor     eax, eax
0x1800addbf  jmp     loc_1800AE0FA
0x1800addc4  mov     rcx, cs:gDhcpHeap; hHeap
0x1800addcb  mov     edx, 8; dwFlags
0x1800addd0  lea     r8d, [rdx+38h]; dwBytes
0x1800addd4  call    cs:__imp_HeapAlloc
0x1800adddb  nop     dword ptr [rax+rax+00h]
0x1800adde0  mov     rdi, rax
0x1800adde3  test    rax, rax
0x1800adde6  jnz     short loc_1800ADDED
0x1800adde8  lea     ecx, [rax+8]
0x1800addeb  jmp     short loc_1800ADDB1
0x1800added  mov     eax, cs:gSocketEventTotal
0x1800addf3  lea     rcx, gSocketLock; lpCriticalSection
0x1800addfa  and     [rdi+18h], r14
0x1800addfe  and     [rdi+20h], r14d
0x1800ade02  and     [rdi+10h], r14
0x1800ade06  mov     [rdi], eax
0x1800ade08  mov     [rdi+4], eax
0x1800ade0b  mov     [rdi+8], rbx
0x1800ade0f  mov     [rdi+38h], rbp
0x1800ade13  call    cs:__imp_EnterCriticalSection
0x1800ade1a  nop     dword ptr [rax+rax+00h]
0x1800ade1f  lea     rdx, gCMCritSecSendSocket
0x1800ade26  xor     eax, eax
0x1800ade28  mov     rcx, rdx
0x1800ade2b  cmp     [rcx], r14d
0x1800ade2e  jz      short loc_1800ADE3D
0x1800ade30  inc     eax
0x1800ade32  add     rcx, 30h ; '0'
0x1800ade36  cmp     eax, 40h ; '@'
0x1800ade39  jb      short loc_1800ADE2B
0x1800ade3b  jmp     short loc_1800ADE52
0x1800ade3d  lea     rax, [rax+rax*2]
0x1800ade41  shl     rax, 4
0x1800ade45  add     rax, rdx
0x1800ade48  mov     [rdi+10h], rax
0x1800ade4c  mov     dword ptr [rax], 1
0x1800ade52  lea     rcx, gSocketLock; lpCriticalSection
0x1800ade59  call    cs:__imp_LeaveCriticalSection
0x1800ade60  nop     dword ptr [rax+rax+00h]
0x1800ade65  lea     r12, aAddsockettogar; "AddSocketToGArray"
0x1800ade6c  cmp     [rdi+10h], r14
0x1800ade70  jnz     short loc_1800ADEB3
0x1800ade72  mov     esi, 8
0x1800ade77  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ade7e  lea     rax, WPP_GLOBAL_Control
0x1800ade85  cmp     rcx, rax
0x1800ade88  jz      loc_1800ADFE5
0x1800ade8e  test    dword ptr [rcx+1Ch], 800000h
0x1800ade95  jz      loc_1800ADFE5
0x1800ade9b  mov     rcx, [rcx+10h]
0x1800ade9f  lea     edx, [rsi+2]
0x1800adea2  lea     r8, WPP_5bd49953df5f3f59743b495ddca40749_Traceguids
0x1800adea9  call    WPP_SF_
0x1800adeae  jmp     loc_1800ADFE5
0x1800adeb3  call    cs:__imp_WSACreateEvent
0x1800adeba  nop     dword ptr [rax+rax+00h]
0x1800adebf  mov     [rdi+28h], rax
0x1800adec3  test    rax, rax
0x1800adec6  jnz     short loc_1800ADEF2
0x1800adec8  call    cs:__imp_WSAGetLastError
0x1800adecf  nop     dword ptr [rax+rax+00h]
0x1800aded4  mov     r9d, 0E0h
0x1800adeda  lea     r8, aWsacreateevent; "WSACreateEvent"
0x1800adee1  mov     rdx, r12
0x1800adee4  mov     ecx, eax
0x1800adee6  mov     esi, eax
0x1800adee8  call    DhcpPrintFOErrorEx
0x1800adeed  jmp     loc_1800ADFDD
0x1800adef2  call    cs:__imp_WSACreateEvent
0x1800adef9  nop     dword ptr [rax+rax+00h]
0x1800adefe  mov     [rdi+30h], rax
0x1800adf02  test    rax, rax
0x1800adf05  jnz     short loc_1800ADF1B
0x1800adf07  call    cs:__imp_WSAGetLastError
0x1800adf0e  nop     dword ptr [rax+rax+00h]
0x1800adf13  mov     r9d, 0E1h
0x1800adf19  jmp     short loc_1800ADEDA
0x1800adf1b  call    cs:__imp_WSACreateEvent
0x1800adf22  nop     dword ptr [rax+rax+00h]
0x1800adf27  mov     r14, rax
0x1800adf2a  test    rax, rax
0x1800adf2d  jnz     short loc_1800ADF43
0x1800adf2f  call    cs:__imp_WSAGetLastError
0x1800adf36  nop     dword ptr [rax+rax+00h]
0x1800adf3b  mov     r9d, 0E5h
0x1800adf41  jmp     short loc_1800ADEDA
0x1800adf43  mov     r8d, esi; lNetworkEvents
0x1800adf46  mov     rdx, r14; hEventObject
0x1800adf49  mov     rcx, rbx; s
0x1800adf4c  call    cs:__imp_WSAEventSelect
0x1800adf53  nop     dword ptr [rax+rax+00h]
0x1800adf58  mov     esi, eax
0x1800adf5a  cmp     eax, 0FFFFFFFFh
0x1800adf5d  jnz     short loc_1800ADF7D
0x1800adf5f  call    cs:__imp_WSAGetLastError
0x1800adf66  nop     dword ptr [rax+rax+00h]
0x1800adf6b  mov     r9d, 0E8h
0x1800adf71  lea     r8, aWsaeventselect; "WSAEventSelect"
0x1800adf78  jmp     loc_1800ADEE1
0x1800adf7d  mov     ecx, cs:gSocketEventTotal
0x1800adf83  lea     rdx, __ImageBase
0x1800adf8a  mov     rva gSocketArray[rdx+rcx*8], rdi
0x1800adf92  mov     rva gSocketEventArray[rdx+rcx*8], r14
0x1800adf9a  inc     ecx
0x1800adf9c  mov     cs:gSocketEventTotal, ecx
0x1800adfa2  test    rbp, rbp
0x1800adfa5  jz      short loc_1800ADFDD
0x1800adfa7  lea     rcx, [rbp+48h]; SRWLock
0x1800adfab  call    cs:__imp_AcquireSRWLockExclusive
0x1800adfb2  nop     dword ptr [rax+rax+00h]
0x1800adfb7  mov     [rbp+1E0h], rdi
0x1800adfbe  lea     rcx, [rbp+48h]; SRWLock
0x1800adfc2  mov     rax, [rdi+10h]
0x1800adfc6  add     rax, 8
0x1800adfca  mov     [rbp+1E8h], rax
0x1800adfd1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800adfd8  nop     dword ptr [rax+rax+00h]
0x1800adfdd  test    esi, esi
0x1800adfdf  jz      loc_1800AE0F7
0x1800adfe5  mov     rcx, [rdi+28h]; hEvent
0x1800adfe9  lea     rbx, aWsacloseevent; "WSACloseEvent"
0x1800adff0  test    rcx, rcx
0x1800adff3  jz      short loc_1800AE029
0x1800adff5  call    cs:__imp_WSACloseEvent
0x1800adffc  nop     dword ptr [rax+rax+00h]
0x1800ae001  test    eax, eax
0x1800ae003  jnz     short loc_1800AE024
0x1800ae005  call    cs:__imp_WSAGetLastError
0x1800ae00c  nop     dword ptr [rax+rax+00h]
0x1800ae011  mov     r9d, 0FBh
0x1800ae017  mov     r8, rbx
0x1800ae01a  mov     ecx, eax
0x1800ae01c  mov     rdx, r12
0x1800ae01f  call    DhcpPrintFOErrorEx
0x1800ae024  and     qword ptr [rdi+28h], 0
0x1800ae029  mov     rcx, [rdi+30h]; hEvent
0x1800ae02d  test    rcx, rcx
0x1800ae030  jz      short loc_1800AE066
0x1800ae032  call    cs:__imp_WSACloseEvent
0x1800ae039  nop     dword ptr [rax+rax+00h]
0x1800ae03e  test    eax, eax
0x1800ae040  jnz     short loc_1800AE061
0x1800ae042  call    cs:__imp_WSAGetLastError
0x1800ae049  nop     dword ptr [rax+rax+00h]
0x1800ae04e  mov     r9d, 0FCh
0x1800ae054  mov     r8, rbx
0x1800ae057  mov     ecx, eax
0x1800ae059  mov     rdx, r12
0x1800ae05c  call    DhcpPrintFOErrorEx
0x1800ae061  and     qword ptr [rdi+30h], 0
0x1800ae066  test    r14, r14
0x1800ae069  jz      short loc_1800AE09D
0x1800ae06b  mov     rcx, r14; hEvent
0x1800ae06e  call    cs:__imp_WSACloseEvent
0x1800ae075  nop     dword ptr [rax+rax+00h]
0x1800ae07a  test    eax, eax
0x1800ae07c  jnz     short loc_1800AE09D
0x1800ae07e  call    cs:__imp_WSAGetLastError
0x1800ae085  nop     dword ptr [rax+rax+00h]
0x1800ae08a  mov     r9d, 0FDh
0x1800ae090  mov     r8, rbx
0x1800ae093  mov     ecx, eax
0x1800ae095  mov     rdx, r12
0x1800ae098  call    DhcpPrintFOErrorEx
0x1800ae09d  lea     rcx, gSocketLock; lpCriticalSection
0x1800ae0a4  call    cs:__imp_EnterCriticalSection
0x1800ae0ab  nop     dword ptr [rax+rax+00h]
0x1800ae0b0  mov     rax, [rdi+10h]
0x1800ae0b4  lea     rcx, gSocketLock; lpCriticalSection
0x1800ae0bb  and     dword ptr [rax], 0
0x1800ae0be  and     qword ptr [rdi+10h], 0
0x1800ae0c3  call    cs:__imp_LeaveCriticalSection
0x1800ae0ca  nop     dword ptr [rax+rax+00h]
0x1800ae0cf  mov     rcx, cs:gDhcpHeap; hHeap
0x1800ae0d6  mov     r8, rdi; lpMem
0x1800ae0d9  xor     edx, edx; dwFlags
0x1800ae0db  call    cs:__imp_HeapFree
0x1800ae0e2  nop     dword ptr [rax+rax+00h]
0x1800ae0e7  mov     ecx, esi; iError
0x1800ae0e9  xor     edi, edi
0x1800ae0eb  call    cs:__imp_WSASetLastError
0x1800ae0f2  nop     dword ptr [rax+rax+00h]
0x1800ae0f7  mov     rax, rdi
0x1800ae0fa  mov     rbx, [rsp+38h+arg_0]
0x1800ae0ff  mov     rbp, [rsp+38h+arg_8]
0x1800ae104  mov     rsi, [rsp+38h+arg_10]
0x1800ae109  add     rsp, 20h
0x1800ae10d  pop     r14
0x1800ae10f  pop     r12
0x1800ae111  pop     rdi
0x1800ae112  retn
```
