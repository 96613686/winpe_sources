# DhcpBNDCleanup

- ea: `0x1800bf348`
- end: `0x1800bf71d`
- name: `DhcpBNDCleanup`
- size: `981`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800a3b60`
- `0x1800c09e8`

## callees

- `0x18000282c`
- `0x18001c45c`
- `0x1800bf348`
- `0x1800cc9e4`

## import_xrefs

- `WS2_32!WSACloseEvent` at `0x1800bf3f0`
- `WS2_32!WSACloseEvent` at `0x1800bf436`
- `WS2_32!WSACloseEvent` at `0x1800bf47c`
- `WS2_32!WSACloseEvent` at `0x1800bf4c2`
- `WS2_32!WSACloseEvent` at `0x1800bf508`
- `WS2_32!WSACloseEvent` at `0x1800bf54e`
- `WS2_32!WSACloseEvent` at `0x1800bf594`
- `WS2_32!WSACloseEvent` at `0x1800bf5da`
- `WS2_32!WSACloseEvent` at `0x1800bf620`
- `WS2_32!WSACloseEvent` at `0x1800bf666`
- `WS2_32!WSACloseEvent` at `0x1800bf3f0`
- `WS2_32!WSACloseEvent` at `0x1800bf436`
- `WS2_32!WSACloseEvent` at `0x1800bf47c`
- `WS2_32!WSACloseEvent` at `0x1800bf4c2`
- `WS2_32!WSACloseEvent` at `0x1800bf508`
- `WS2_32!WSACloseEvent` at `0x1800bf54e`
- `WS2_32!WSACloseEvent` at `0x1800bf594`
- `WS2_32!WSACloseEvent` at `0x1800bf5da`
- `WS2_32!WSACloseEvent` at `0x1800bf620`
- `WS2_32!WSACloseEvent` at `0x1800bf666`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bf400`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bf446`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bf48c`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bf4d2`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bf518`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bf55e`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bf5a4`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bf5ea`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bf630`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bf676`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bf400`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bf446`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bf48c`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bf4d2`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bf518`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bf55e`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bf5a4`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bf5ea`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bf630`
- `WS2_32!__imp_WSAGetLastError` at `0x1800bf676`
- `KERNEL32!DeleteCriticalSection` at `0x1800bf6a7`
- `KERNEL32!DeleteCriticalSection` at `0x1800bf6a7`
- `KERNEL32!CloseHandle` at `0x1800bf6c4`
- `KERNEL32!CloseHandle` at `0x1800bf6e1`
- `KERNEL32!CloseHandle` at `0x1800bf6fe`
- `KERNEL32!CloseHandle` at `0x1800bf6c4`
- `KERNEL32!CloseHandle` at `0x1800bf6e1`
- `KERNEL32!CloseHandle` at `0x1800bf6fe`
- `KERNEL32!HeapFree` at `0x1800bf3b9`
- `KERNEL32!HeapFree` at `0x1800bf3b9`

## string_xrefs

- `0x1800bf3dd`: `WSACloseEvent`

## pseudocode

```c
__int64 DhcpBNDCleanup()
{
  unsigned int v0; // esi
  LPVOID **v1; // rbx
  __int64 v2; // rdi
  unsigned int Error; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax

  v0 = 0;
  v1 = (LPVOID **)&gBndFailoverEndpointsQueue;
  v2 = 32;
  do
  {
    if ( *v1 )
    {
      v0 = MessageQCleanup(**v1);
      if ( v0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids, v0);
      }
      HeapFree(gDhcpHeap, 0, *v1);
      *v1 = 0;
    }
    ++v1;
    --v2;
  }
  while ( v2 );
  if ( gLeaseDBupdateQFullEvent )
  {
    if ( !WSACloseEvent(gLeaseDBupdateQFullEvent) )
    {
      Error = WSAGetLastError();
      DhcpPrintFOErrorEx(Error, "DhcpBNDCleanup", "WSACloseEvent", 4110);
    }
    gLeaseDBupdateQFullEvent = 0;
  }
  if ( gStartBndSendProcessingReqEvent )
  {
    if ( !WSACloseEvent(gStartBndSendProcessingReqEvent) )
    {
      v4 = WSAGetLastError();
      DhcpPrintFOErrorEx(v4, "DhcpBNDCleanup", "WSACloseEvent", 4111);
    }
    gStartBndSendProcessingReqEvent = 0;
  }
  if ( gStartBndRecvProcessingReqEvent )
  {
    if ( !WSACloseEvent(gStartBndRecvProcessingReqEvent) )
    {
      v5 = WSAGetLastError();
      DhcpPrintFOErrorEx(v5, "DhcpBNDCleanup", "WSACloseEvent", 4112);
    }
    gStartBndRecvProcessingReqEvent = 0;
  }
  if ( gTerminateBndSendThreadEvent )
  {
    if ( !WSACloseEvent(gTerminateBndSendThreadEvent) )
    {
      v6 = WSAGetLastError();
      DhcpPrintFOErrorEx(v6, "DhcpBNDCleanup", "WSACloseEvent", 4113);
    }
    gTerminateBndSendThreadEvent = 0;
  }
  if ( gTerminateBndRecvThreadEvent )
  {
    if ( !WSACloseEvent(gTerminateBndRecvThreadEvent) )
    {
      v7 = WSAGetLastError();
      DhcpPrintFOErrorEx(v7, "DhcpBNDCleanup", "WSACloseEvent", 4114);
    }
    gTerminateBndRecvThreadEvent = 0;
  }
  if ( gTerminateBndSendThreadCompleteEvent )
  {
    if ( !WSACloseEvent(gTerminateBndSendThreadCompleteEvent) )
    {
      v8 = WSAGetLastError();
      DhcpPrintFOErrorEx(v8, "DhcpBNDCleanup", "WSACloseEvent", 4115);
    }
    gTerminateBndSendThreadCompleteEvent = 0;
  }
  if ( gTerminateBndRecvThreadCompleteEvent )
  {
    if ( !WSACloseEvent(gTerminateBndRecvThreadCompleteEvent) )
    {
      v9 = WSAGetLastError();
      DhcpPrintFOErrorEx(v9, "DhcpBNDCleanup", "WSACloseEvent", 4116);
    }
    gTerminateBndRecvThreadCompleteEvent = 0;
  }
  if ( gStartBndCoreProcessingReqEvent )
  {
    if ( !WSACloseEvent(gStartBndCoreProcessingReqEvent) )
    {
      v10 = WSAGetLastError();
      DhcpPrintFOErrorEx(v10, "DhcpBNDCleanup", "WSACloseEvent", 4117);
    }
    gStartBndCoreProcessingReqEvent = 0;
  }
  if ( gTerminateBndCoreThreadEvent )
  {
    if ( !WSACloseEvent(gTerminateBndCoreThreadEvent) )
    {
      v11 = WSAGetLastError();
      DhcpPrintFOErrorEx(v11, "DhcpBNDCleanup", "WSACloseEvent", 4118);
    }
    gTerminateBndCoreThreadEvent = 0;
  }
  if ( gTerminateBndCoreThreadCompleteEvent )
  {
    if ( !WSACloseEvent(gTerminateBndCoreThreadCompleteEvent) )
    {
      v12 = WSAGetLastError();
      DhcpPrintFOErrorEx(v12, "DhcpBNDCleanup", "WSACloseEvent", 4119);
    }
    gTerminateBndCoreThreadCompleteEvent = 0;
  }
  DeleteCriticalSection(&gBndFailoverEndpointCS);
  if ( (char *)gBndSendThreadHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(gBndSendThreadHandle);
  if ( (char *)gBndRecvThreadHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(gBndRecvThreadHandle);
  if ( (char *)gBndCoreThreadHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(gBndCoreThreadHandle);
  return v0;
}

```

## disassembly

```asm
0x1800bf348  mov     [rsp+arg_0], rbx
0x1800bf34d  mov     [rsp+arg_8], rsi
0x1800bf352  push    rdi
0x1800bf353  sub     rsp, 20h
0x1800bf357  xor     esi, esi
0x1800bf359  lea     rbx, gBndFailoverEndpointsQueue
0x1800bf360  lea     edi, [rsi+20h]
0x1800bf363  mov     rcx, [rbx]
0x1800bf366  test    rcx, rcx
0x1800bf369  jz      short loc_1800BF3CC
0x1800bf36b  mov     rcx, [rcx]; lpMem
0x1800bf36e  call    MessageQCleanup
0x1800bf373  mov     esi, eax
0x1800bf375  test    eax, eax
0x1800bf377  jz      short loc_1800BF3AD
0x1800bf379  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf380  lea     rax, WPP_GLOBAL_Control
0x1800bf387  cmp     rcx, rax
0x1800bf38a  jz      short loc_1800BF3AD
0x1800bf38c  test    dword ptr [rcx+1Ch], 800000h
0x1800bf393  jz      short loc_1800BF3AD
0x1800bf395  mov     rcx, [rcx+10h]
0x1800bf399  lea     r8, WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids
0x1800bf3a0  mov     edx, 5Dh ; ']'
0x1800bf3a5  mov     r9d, esi
0x1800bf3a8  call    WPP_SF_D
0x1800bf3ad  mov     r8, [rbx]; lpMem
0x1800bf3b0  xor     edx, edx; dwFlags
0x1800bf3b2  mov     rcx, cs:gDhcpHeap; hHeap
0x1800bf3b9  call    cs:__imp_HeapFree
0x1800bf3c0  nop     dword ptr [rax+rax+00h]
0x1800bf3c5  mov     qword ptr [rbx], 0
0x1800bf3cc  add     rbx, 8
0x1800bf3d0  sub     rdi, 1
0x1800bf3d4  jnz     short loc_1800BF363
0x1800bf3d6  mov     rcx, cs:gLeaseDBupdateQFullEvent; hEvent
0x1800bf3dd  lea     rbx, aWsacloseevent; "WSACloseEvent"
0x1800bf3e4  lea     rdi, aDhcpbndcleanup_0; "DhcpBNDCleanup"
0x1800bf3eb  test    rcx, rcx
0x1800bf3ee  jz      short loc_1800BF42A
0x1800bf3f0  call    cs:__imp_WSACloseEvent
0x1800bf3f7  nop     dword ptr [rax+rax+00h]
0x1800bf3fc  test    eax, eax
0x1800bf3fe  jnz     short loc_1800BF41F
0x1800bf400  call    cs:__imp_WSAGetLastError
0x1800bf407  nop     dword ptr [rax+rax+00h]
0x1800bf40c  mov     r9d, 100Eh
0x1800bf412  mov     r8, rbx
0x1800bf415  mov     ecx, eax
0x1800bf417  mov     rdx, rdi
0x1800bf41a  call    DhcpPrintFOErrorEx
0x1800bf41f  mov     cs:gLeaseDBupdateQFullEvent, 0
0x1800bf42a  mov     rcx, cs:gStartBndSendProcessingReqEvent; hEvent
0x1800bf431  test    rcx, rcx
0x1800bf434  jz      short loc_1800BF470
0x1800bf436  call    cs:__imp_WSACloseEvent
0x1800bf43d  nop     dword ptr [rax+rax+00h]
0x1800bf442  test    eax, eax
0x1800bf444  jnz     short loc_1800BF465
0x1800bf446  call    cs:__imp_WSAGetLastError
0x1800bf44d  nop     dword ptr [rax+rax+00h]
0x1800bf452  mov     r9d, 100Fh
0x1800bf458  mov     r8, rbx
0x1800bf45b  mov     ecx, eax
0x1800bf45d  mov     rdx, rdi
0x1800bf460  call    DhcpPrintFOErrorEx
0x1800bf465  mov     cs:gStartBndSendProcessingReqEvent, 0
0x1800bf470  mov     rcx, cs:gStartBndRecvProcessingReqEvent; hEvent
0x1800bf477  test    rcx, rcx
0x1800bf47a  jz      short loc_1800BF4B6
0x1800bf47c  call    cs:__imp_WSACloseEvent
0x1800bf483  nop     dword ptr [rax+rax+00h]
0x1800bf488  test    eax, eax
0x1800bf48a  jnz     short loc_1800BF4AB
0x1800bf48c  call    cs:__imp_WSAGetLastError
0x1800bf493  nop     dword ptr [rax+rax+00h]
0x1800bf498  mov     r9d, 1010h
0x1800bf49e  mov     r8, rbx
0x1800bf4a1  mov     ecx, eax
0x1800bf4a3  mov     rdx, rdi
0x1800bf4a6  call    DhcpPrintFOErrorEx
0x1800bf4ab  mov     cs:gStartBndRecvProcessingReqEvent, 0
0x1800bf4b6  mov     rcx, cs:gTerminateBndSendThreadEvent; hEvent
0x1800bf4bd  test    rcx, rcx
0x1800bf4c0  jz      short loc_1800BF4FC
0x1800bf4c2  call    cs:__imp_WSACloseEvent
0x1800bf4c9  nop     dword ptr [rax+rax+00h]
0x1800bf4ce  test    eax, eax
0x1800bf4d0  jnz     short loc_1800BF4F1
0x1800bf4d2  call    cs:__imp_WSAGetLastError
0x1800bf4d9  nop     dword ptr [rax+rax+00h]
0x1800bf4de  mov     r9d, 1011h
0x1800bf4e4  mov     r8, rbx
0x1800bf4e7  mov     ecx, eax
0x1800bf4e9  mov     rdx, rdi
0x1800bf4ec  call    DhcpPrintFOErrorEx
0x1800bf4f1  mov     cs:gTerminateBndSendThreadEvent, 0
0x1800bf4fc  mov     rcx, cs:gTerminateBndRecvThreadEvent; hEvent
0x1800bf503  test    rcx, rcx
0x1800bf506  jz      short loc_1800BF542
0x1800bf508  call    cs:__imp_WSACloseEvent
0x1800bf50f  nop     dword ptr [rax+rax+00h]
0x1800bf514  test    eax, eax
0x1800bf516  jnz     short loc_1800BF537
0x1800bf518  call    cs:__imp_WSAGetLastError
0x1800bf51f  nop     dword ptr [rax+rax+00h]
0x1800bf524  mov     r9d, 1012h
0x1800bf52a  mov     r8, rbx
0x1800bf52d  mov     ecx, eax
0x1800bf52f  mov     rdx, rdi
0x1800bf532  call    DhcpPrintFOErrorEx
0x1800bf537  mov     cs:gTerminateBndRecvThreadEvent, 0
0x1800bf542  mov     rcx, cs:gTerminateBndSendThreadCompleteEvent; hEvent
0x1800bf549  test    rcx, rcx
0x1800bf54c  jz      short loc_1800BF588
0x1800bf54e  call    cs:__imp_WSACloseEvent
0x1800bf555  nop     dword ptr [rax+rax+00h]
0x1800bf55a  test    eax, eax
0x1800bf55c  jnz     short loc_1800BF57D
0x1800bf55e  call    cs:__imp_WSAGetLastError
0x1800bf565  nop     dword ptr [rax+rax+00h]
0x1800bf56a  mov     r9d, 1013h
0x1800bf570  mov     r8, rbx
0x1800bf573  mov     ecx, eax
0x1800bf575  mov     rdx, rdi
0x1800bf578  call    DhcpPrintFOErrorEx
0x1800bf57d  mov     cs:gTerminateBndSendThreadCompleteEvent, 0
0x1800bf588  mov     rcx, cs:gTerminateBndRecvThreadCompleteEvent; hEvent
0x1800bf58f  test    rcx, rcx
0x1800bf592  jz      short loc_1800BF5CE
0x1800bf594  call    cs:__imp_WSACloseEvent
0x1800bf59b  nop     dword ptr [rax+rax+00h]
0x1800bf5a0  test    eax, eax
0x1800bf5a2  jnz     short loc_1800BF5C3
0x1800bf5a4  call    cs:__imp_WSAGetLastError
0x1800bf5ab  nop     dword ptr [rax+rax+00h]
0x1800bf5b0  mov     r9d, 1014h
0x1800bf5b6  mov     r8, rbx
0x1800bf5b9  mov     ecx, eax
0x1800bf5bb  mov     rdx, rdi
0x1800bf5be  call    DhcpPrintFOErrorEx
0x1800bf5c3  mov     cs:gTerminateBndRecvThreadCompleteEvent, 0
0x1800bf5ce  mov     rcx, cs:gStartBndCoreProcessingReqEvent; hEvent
0x1800bf5d5  test    rcx, rcx
0x1800bf5d8  jz      short loc_1800BF614
0x1800bf5da  call    cs:__imp_WSACloseEvent
0x1800bf5e1  nop     dword ptr [rax+rax+00h]
0x1800bf5e6  test    eax, eax
0x1800bf5e8  jnz     short loc_1800BF609
0x1800bf5ea  call    cs:__imp_WSAGetLastError
0x1800bf5f1  nop     dword ptr [rax+rax+00h]
0x1800bf5f6  mov     r9d, 1015h
0x1800bf5fc  mov     r8, rbx
0x1800bf5ff  mov     ecx, eax
0x1800bf601  mov     rdx, rdi
0x1800bf604  call    DhcpPrintFOErrorEx
0x1800bf609  mov     cs:gStartBndCoreProcessingReqEvent, 0
0x1800bf614  mov     rcx, cs:gTerminateBndCoreThreadEvent; hEvent
0x1800bf61b  test    rcx, rcx
0x1800bf61e  jz      short loc_1800BF65A
0x1800bf620  call    cs:__imp_WSACloseEvent
0x1800bf627  nop     dword ptr [rax+rax+00h]
0x1800bf62c  test    eax, eax
0x1800bf62e  jnz     short loc_1800BF64F
0x1800bf630  call    cs:__imp_WSAGetLastError
0x1800bf637  nop     dword ptr [rax+rax+00h]
0x1800bf63c  mov     r9d, 1016h
0x1800bf642  mov     r8, rbx
0x1800bf645  mov     ecx, eax
0x1800bf647  mov     rdx, rdi
0x1800bf64a  call    DhcpPrintFOErrorEx
0x1800bf64f  mov     cs:gTerminateBndCoreThreadEvent, 0
0x1800bf65a  mov     rcx, cs:gTerminateBndCoreThreadCompleteEvent; hEvent
0x1800bf661  test    rcx, rcx
0x1800bf664  jz      short loc_1800BF6A0
0x1800bf666  call    cs:__imp_WSACloseEvent
0x1800bf66d  nop     dword ptr [rax+rax+00h]
0x1800bf672  test    eax, eax
0x1800bf674  jnz     short loc_1800BF695
0x1800bf676  call    cs:__imp_WSAGetLastError
0x1800bf67d  nop     dword ptr [rax+rax+00h]
0x1800bf682  mov     r9d, 1017h
0x1800bf688  mov     r8, rbx
0x1800bf68b  mov     ecx, eax
0x1800bf68d  mov     rdx, rdi
0x1800bf690  call    DhcpPrintFOErrorEx
0x1800bf695  mov     cs:gTerminateBndCoreThreadCompleteEvent, 0
0x1800bf6a0  lea     rcx, gBndFailoverEndpointCS; lpCriticalSection
0x1800bf6a7  call    cs:__imp_DeleteCriticalSection
0x1800bf6ae  nop     dword ptr [rax+rax+00h]
0x1800bf6b3  mov     rcx, cs:gBndSendThreadHandle; hObject
0x1800bf6ba  lea     rax, [rcx-1]
0x1800bf6be  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800bf6c2  ja      short loc_1800BF6D0
0x1800bf6c4  call    cs:__imp_CloseHandle
0x1800bf6cb  nop     dword ptr [rax+rax+00h]
0x1800bf6d0  mov     rcx, cs:gBndRecvThreadHandle; hObject
0x1800bf6d7  lea     rax, [rcx-1]
0x1800bf6db  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800bf6df  ja      short loc_1800BF6ED
0x1800bf6e1  call    cs:__imp_CloseHandle
0x1800bf6e8  nop     dword ptr [rax+rax+00h]
0x1800bf6ed  mov     rcx, cs:gBndCoreThreadHandle; hObject
0x1800bf6f4  lea     rax, [rcx-1]
0x1800bf6f8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800bf6fc  ja      short loc_1800BF70A
0x1800bf6fe  call    cs:__imp_CloseHandle
0x1800bf705  nop     dword ptr [rax+rax+00h]
0x1800bf70a  mov     rbx, [rsp+28h+arg_0]
0x1800bf70f  mov     eax, esi
0x1800bf711  mov     rsi, [rsp+28h+arg_8]
0x1800bf716  add     rsp, 20h
0x1800bf71a  pop     rdi
0x1800bf71b  retn
```
