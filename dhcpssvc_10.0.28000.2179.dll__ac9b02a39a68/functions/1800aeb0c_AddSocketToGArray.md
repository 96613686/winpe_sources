# AddSocketToGArray

- ea: `0x1800aeb0c`
- end: `0x1800aeeac`
- name: `AddSocketToGArray`
- size: `928`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800af10c`
- `0x1800b0bb4`

## callees

- `0x180003228`
- `0x18001c45c`
- `0x1800aeb0c`

## import_xrefs

- `WS2_32!WSAEventSelect` at `0x1800aecd8`
- `WS2_32!WSAEventSelect` at `0x1800aecd8`
- `WS2_32!WSACloseEvent` at `0x1800aed81`
- `WS2_32!WSACloseEvent` at `0x1800aedc1`
- `WS2_32!WSACloseEvent` at `0x1800aee00`
- `WS2_32!WSACloseEvent` at `0x1800aed81`
- `WS2_32!WSACloseEvent` at `0x1800aedc1`
- `WS2_32!WSACloseEvent` at `0x1800aee00`
- `WS2_32!WSACreateEvent` at `0x1800aec3f`
- `WS2_32!WSACreateEvent` at `0x1800aec7e`
- `WS2_32!WSACreateEvent` at `0x1800aeca7`
- `WS2_32!WSACreateEvent` at `0x1800aec3f`
- `WS2_32!WSACreateEvent` at `0x1800aec7e`
- `WS2_32!WSACreateEvent` at `0x1800aeca7`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aec54`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aec93`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aecbb`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aeceb`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aed91`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aedd1`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aee10`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aec54`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aec93`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aecbb`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aeceb`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aed91`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aedd1`
- `WS2_32!__imp_WSAGetLastError` at `0x1800aee10`
- `WS2_32!__imp_WSASetLastError` at `0x1800aeb3d`
- `WS2_32!__imp_WSASetLastError` at `0x1800aee83`
- `WS2_32!__imp_WSASetLastError` at `0x1800aeb3d`
- `WS2_32!__imp_WSASetLastError` at `0x1800aee83`
- `KERNEL32!HeapAlloc` at `0x1800aeb60`
- `KERNEL32!HeapAlloc` at `0x1800aeb60`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800aed5d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800aed5d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800aed37`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800aed37`
- `KERNEL32!EnterCriticalSection` at `0x1800aeb9f`
- `KERNEL32!EnterCriticalSection` at `0x1800aee36`
- `KERNEL32!EnterCriticalSection` at `0x1800aeb9f`
- `KERNEL32!EnterCriticalSection` at `0x1800aee36`
- `KERNEL32!LeaveCriticalSection` at `0x1800aebe5`
- `KERNEL32!LeaveCriticalSection` at `0x1800aee5b`
- `KERNEL32!LeaveCriticalSection` at `0x1800aebe5`
- `KERNEL32!LeaveCriticalSection` at `0x1800aee5b`
- `KERNEL32!HeapFree` at `0x1800aee73`
- `KERNEL32!HeapFree` at `0x1800aee73`

## string_xrefs

- `0x1800aec66`: `WSACreateEvent`
- `0x1800aed75`: `WSACloseEvent`

## pseudocode

```c
_DWORD *__fastcall AddSocketToGArray(RTL_SRWLOCK *a1, SOCKET a2, int a3)
{
  void *v3; // r14
  int v7; // ecx
  _DWORD *v9; // rdi
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
  *v9 = gSocketEventTotal;
  v9[1] = v10;
  *((_QWORD *)v9 + 1) = a2;
  *((_QWORD *)v9 + 7) = a1;
  *((_QWORD *)v9 + 3) = 0;
  v9[8] = 0;
  *((_QWORD *)v9 + 2) = 0;
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
  *((_QWORD *)v9 + 2) = v13;
  *v13 = 1;
LABEL_11:
  LeaveCriticalSection(&gSocketLock);
  if ( !*((_QWORD *)v9 + 2) )
  {
    v14 = 8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids);
    goto LABEL_28;
  }
  v15 = WSACreateEvent();
  *((_QWORD *)v9 + 5) = v15;
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
  *((_QWORD *)v9 + 6) = v19;
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
    a1[61].Ptr = (PVOID)(*((_QWORD *)v9 + 2) + 8LL);
    ReleaseSRWLockExclusive(a1 + 9);
  }
LABEL_27:
  if ( v14 )
  {
LABEL_28:
    v22 = (void *)*((_QWORD *)v9 + 5);
    if ( v22 )
    {
      if ( !WSACloseEvent(v22) )
      {
        v23 = WSAGetLastError();
        DhcpPrintFOErrorEx(v23, "AddSocketToGArray", "WSACloseEvent", 251);
      }
      *((_QWORD *)v9 + 5) = 0;
    }
    v24 = (void *)*((_QWORD *)v9 + 6);
    if ( v24 )
    {
      if ( !WSACloseEvent(v24) )
      {
        v25 = WSAGetLastError();
        DhcpPrintFOErrorEx(v25, "AddSocketToGArray", "WSACloseEvent", 252);
      }
      *((_QWORD *)v9 + 6) = 0;
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
    **((_DWORD **)v9 + 2) = 0;
    *((_QWORD *)v9 + 2) = 0;
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
0x1800aeb0c  mov     [rsp+arg_0], rbx
0x1800aeb11  mov     [rsp+arg_8], rbp
0x1800aeb16  mov     [rsp+arg_10], rsi
0x1800aeb1b  push    rdi
0x1800aeb1c  push    r12
0x1800aeb1e  push    r14
0x1800aeb20  sub     rsp, 20h
0x1800aeb24  xor     r14d, r14d
0x1800aeb27  mov     esi, r8d
0x1800aeb2a  cmp     cs:gSocketEventTotal, 40h ; '@'
0x1800aeb31  mov     rbx, rdx
0x1800aeb34  mov     rbp, rcx
0x1800aeb37  jb      short loc_1800AEB50
0x1800aeb39  lea     ecx, [r14+57h]; iError
0x1800aeb3d  call    cs:__imp_WSASetLastError
0x1800aeb44  nop     dword ptr [rax+rax+00h]
0x1800aeb49  xor     eax, eax
0x1800aeb4b  jmp     loc_1800AEE92
0x1800aeb50  mov     rcx, cs:gDhcpHeap; hHeap
0x1800aeb57  mov     edx, 8; dwFlags
0x1800aeb5c  lea     r8d, [rdx+38h]; dwBytes
0x1800aeb60  call    cs:__imp_HeapAlloc
0x1800aeb67  nop     dword ptr [rax+rax+00h]
0x1800aeb6c  mov     rdi, rax
0x1800aeb6f  test    rax, rax
0x1800aeb72  jnz     short loc_1800AEB79
0x1800aeb74  lea     ecx, [rax+8]
0x1800aeb77  jmp     short loc_1800AEB3D
0x1800aeb79  mov     eax, cs:gSocketEventTotal
0x1800aeb7f  lea     rcx, gSocketLock; lpCriticalSection
0x1800aeb86  mov     [rdi], eax
0x1800aeb88  mov     [rdi+4], eax
0x1800aeb8b  mov     [rdi+8], rbx
0x1800aeb8f  mov     [rdi+38h], rbp
0x1800aeb93  mov     [rdi+18h], r14
0x1800aeb97  mov     [rdi+20h], r14d
0x1800aeb9b  mov     [rdi+10h], r14
0x1800aeb9f  call    cs:__imp_EnterCriticalSection
0x1800aeba6  nop     dword ptr [rax+rax+00h]
0x1800aebab  lea     rdx, gCMCritSecSendSocket
0x1800aebb2  xor     eax, eax
0x1800aebb4  mov     rcx, rdx
0x1800aebb7  cmp     [rcx], r14d
0x1800aebba  jz      short loc_1800AEBC9
0x1800aebbc  inc     eax
0x1800aebbe  add     rcx, 30h ; '0'
0x1800aebc2  cmp     eax, 40h ; '@'
0x1800aebc5  jb      short loc_1800AEBB7
0x1800aebc7  jmp     short loc_1800AEBDE
0x1800aebc9  lea     rax, [rax+rax*2]
0x1800aebcd  shl     rax, 4
0x1800aebd1  add     rax, rdx
0x1800aebd4  mov     [rdi+10h], rax
0x1800aebd8  mov     dword ptr [rax], 1
0x1800aebde  lea     rcx, gSocketLock; lpCriticalSection
0x1800aebe5  call    cs:__imp_LeaveCriticalSection
0x1800aebec  nop     dword ptr [rax+rax+00h]
0x1800aebf1  lea     r12, aAddsockettogar; "AddSocketToGArray"
0x1800aebf8  cmp     [rdi+10h], r14
0x1800aebfc  jnz     short loc_1800AEC3F
0x1800aebfe  mov     esi, 8
0x1800aec03  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aec0a  lea     rax, WPP_GLOBAL_Control
0x1800aec11  cmp     rcx, rax
0x1800aec14  jz      loc_1800AED71
0x1800aec1a  test    dword ptr [rcx+1Ch], 800000h
0x1800aec21  jz      loc_1800AED71
0x1800aec27  mov     rcx, [rcx+10h]
0x1800aec2b  lea     edx, [rsi+2]
0x1800aec2e  lea     r8, WPP_5bd49953df5f3f59743b495ddca40749_Traceguids
0x1800aec35  call    WPP_SF_
0x1800aec3a  jmp     loc_1800AED71
0x1800aec3f  call    cs:__imp_WSACreateEvent
0x1800aec46  nop     dword ptr [rax+rax+00h]
0x1800aec4b  mov     [rdi+28h], rax
0x1800aec4f  test    rax, rax
0x1800aec52  jnz     short loc_1800AEC7E
0x1800aec54  call    cs:__imp_WSAGetLastError
0x1800aec5b  nop     dword ptr [rax+rax+00h]
0x1800aec60  mov     r9d, 0E0h
0x1800aec66  lea     r8, aWsacreateevent; "WSACreateEvent"
0x1800aec6d  mov     rdx, r12
0x1800aec70  mov     ecx, eax
0x1800aec72  mov     esi, eax
0x1800aec74  call    DhcpPrintFOErrorEx
0x1800aec79  jmp     loc_1800AED69
0x1800aec7e  call    cs:__imp_WSACreateEvent
0x1800aec85  nop     dword ptr [rax+rax+00h]
0x1800aec8a  mov     [rdi+30h], rax
0x1800aec8e  test    rax, rax
0x1800aec91  jnz     short loc_1800AECA7
0x1800aec93  call    cs:__imp_WSAGetLastError
0x1800aec9a  nop     dword ptr [rax+rax+00h]
0x1800aec9f  mov     r9d, 0E1h
0x1800aeca5  jmp     short loc_1800AEC66
0x1800aeca7  call    cs:__imp_WSACreateEvent
0x1800aecae  nop     dword ptr [rax+rax+00h]
0x1800aecb3  mov     r14, rax
0x1800aecb6  test    rax, rax
0x1800aecb9  jnz     short loc_1800AECCF
0x1800aecbb  call    cs:__imp_WSAGetLastError
0x1800aecc2  nop     dword ptr [rax+rax+00h]
0x1800aecc7  mov     r9d, 0E5h
0x1800aeccd  jmp     short loc_1800AEC66
0x1800aeccf  mov     r8d, esi; lNetworkEvents
0x1800aecd2  mov     rdx, r14; hEventObject
0x1800aecd5  mov     rcx, rbx; s
0x1800aecd8  call    cs:__imp_WSAEventSelect
0x1800aecdf  nop     dword ptr [rax+rax+00h]
0x1800aece4  mov     esi, eax
0x1800aece6  cmp     eax, 0FFFFFFFFh
0x1800aece9  jnz     short loc_1800AED09
0x1800aeceb  call    cs:__imp_WSAGetLastError
0x1800aecf2  nop     dword ptr [rax+rax+00h]
0x1800aecf7  mov     r9d, 0E8h
0x1800aecfd  lea     r8, aWsaeventselect; "WSAEventSelect"
0x1800aed04  jmp     loc_1800AEC6D
0x1800aed09  mov     ecx, cs:gSocketEventTotal
0x1800aed0f  lea     rdx, __ImageBase
0x1800aed16  mov     rva gSocketArray[rdx+rcx*8], rdi
0x1800aed1e  mov     rva gSocketEventArray[rdx+rcx*8], r14
0x1800aed26  inc     ecx
0x1800aed28  mov     cs:gSocketEventTotal, ecx
0x1800aed2e  test    rbp, rbp
0x1800aed31  jz      short loc_1800AED69
0x1800aed33  lea     rcx, [rbp+48h]; SRWLock
0x1800aed37  call    cs:__imp_AcquireSRWLockExclusive
0x1800aed3e  nop     dword ptr [rax+rax+00h]
0x1800aed43  mov     [rbp+1E0h], rdi
0x1800aed4a  lea     rcx, [rbp+48h]; SRWLock
0x1800aed4e  mov     rax, [rdi+10h]
0x1800aed52  add     rax, 8
0x1800aed56  mov     [rbp+1E8h], rax
0x1800aed5d  call    cs:__imp_ReleaseSRWLockExclusive
0x1800aed64  nop     dword ptr [rax+rax+00h]
0x1800aed69  test    esi, esi
0x1800aed6b  jz      loc_1800AEE8F
0x1800aed71  mov     rcx, [rdi+28h]; hEvent
0x1800aed75  lea     rbx, aWsacloseevent; "WSACloseEvent"
0x1800aed7c  test    rcx, rcx
0x1800aed7f  jz      short loc_1800AEDB8
0x1800aed81  call    cs:__imp_WSACloseEvent
0x1800aed88  nop     dword ptr [rax+rax+00h]
0x1800aed8d  test    eax, eax
0x1800aed8f  jnz     short loc_1800AEDB0
0x1800aed91  call    cs:__imp_WSAGetLastError
0x1800aed98  nop     dword ptr [rax+rax+00h]
0x1800aed9d  mov     r9d, 0FBh
0x1800aeda3  mov     r8, rbx
0x1800aeda6  mov     ecx, eax
0x1800aeda8  mov     rdx, r12
0x1800aedab  call    DhcpPrintFOErrorEx
0x1800aedb0  mov     qword ptr [rdi+28h], 0
0x1800aedb8  mov     rcx, [rdi+30h]; hEvent
0x1800aedbc  test    rcx, rcx
0x1800aedbf  jz      short loc_1800AEDF8
0x1800aedc1  call    cs:__imp_WSACloseEvent
0x1800aedc8  nop     dword ptr [rax+rax+00h]
0x1800aedcd  test    eax, eax
0x1800aedcf  jnz     short loc_1800AEDF0
0x1800aedd1  call    cs:__imp_WSAGetLastError
0x1800aedd8  nop     dword ptr [rax+rax+00h]
0x1800aeddd  mov     r9d, 0FCh
0x1800aede3  mov     r8, rbx
0x1800aede6  mov     ecx, eax
0x1800aede8  mov     rdx, r12
0x1800aedeb  call    DhcpPrintFOErrorEx
0x1800aedf0  mov     qword ptr [rdi+30h], 0
0x1800aedf8  test    r14, r14
0x1800aedfb  jz      short loc_1800AEE2F
0x1800aedfd  mov     rcx, r14; hEvent
0x1800aee00  call    cs:__imp_WSACloseEvent
0x1800aee07  nop     dword ptr [rax+rax+00h]
0x1800aee0c  test    eax, eax
0x1800aee0e  jnz     short loc_1800AEE2F
0x1800aee10  call    cs:__imp_WSAGetLastError
0x1800aee17  nop     dword ptr [rax+rax+00h]
0x1800aee1c  mov     r9d, 0FDh
0x1800aee22  mov     r8, rbx
0x1800aee25  mov     ecx, eax
0x1800aee27  mov     rdx, r12
0x1800aee2a  call    DhcpPrintFOErrorEx
0x1800aee2f  lea     rcx, gSocketLock; lpCriticalSection
0x1800aee36  call    cs:__imp_EnterCriticalSection
0x1800aee3d  nop     dword ptr [rax+rax+00h]
0x1800aee42  mov     rax, [rdi+10h]
0x1800aee46  lea     rcx, gSocketLock; lpCriticalSection
0x1800aee4d  mov     dword ptr [rax], 0
0x1800aee53  mov     qword ptr [rdi+10h], 0
0x1800aee5b  call    cs:__imp_LeaveCriticalSection
0x1800aee62  nop     dword ptr [rax+rax+00h]
0x1800aee67  mov     rcx, cs:gDhcpHeap; hHeap
0x1800aee6e  mov     r8, rdi; lpMem
0x1800aee71  xor     edx, edx; dwFlags
0x1800aee73  call    cs:__imp_HeapFree
0x1800aee7a  nop     dword ptr [rax+rax+00h]
0x1800aee7f  mov     ecx, esi; iError
0x1800aee81  xor     edi, edi
0x1800aee83  call    cs:__imp_WSASetLastError
0x1800aee8a  nop     dword ptr [rax+rax+00h]
0x1800aee8f  mov     rax, rdi
0x1800aee92  mov     rbx, [rsp+38h+arg_0]
0x1800aee97  mov     rbp, [rsp+38h+arg_8]
0x1800aee9c  mov     rsi, [rsp+38h+arg_10]
0x1800aeea1  add     rsp, 20h
0x1800aeea5  pop     r14
0x1800aeea7  pop     r12
0x1800aeea9  pop     rdi
0x1800aeeaa  retn
```
