# DhcpBNDCleanup

- ea: `0x1800be358`
- end: `0x1800be70c`
- name: `DhcpBNDCleanup`
- size: `948`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800a2e30`
- `0x1800bf9cc`

## callees

- `0x180002854`
- `0x18001ceb4`
- `0x1800be358`
- `0x1800cb938`

## import_xrefs

- `WS2_32!WSACloseEvent` at `0x1800be3fd`
- `WS2_32!WSACloseEvent` at `0x1800be440`
- `WS2_32!WSACloseEvent` at `0x1800be483`
- `WS2_32!WSACloseEvent` at `0x1800be4c6`
- `WS2_32!WSACloseEvent` at `0x1800be509`
- `WS2_32!WSACloseEvent` at `0x1800be54c`
- `WS2_32!WSACloseEvent` at `0x1800be58f`
- `WS2_32!WSACloseEvent` at `0x1800be5d2`
- `WS2_32!WSACloseEvent` at `0x1800be615`
- `WS2_32!WSACloseEvent` at `0x1800be658`
- `WS2_32!WSACloseEvent` at `0x1800be3fd`
- `WS2_32!WSACloseEvent` at `0x1800be440`
- `WS2_32!WSACloseEvent` at `0x1800be483`
- `WS2_32!WSACloseEvent` at `0x1800be4c6`
- `WS2_32!WSACloseEvent` at `0x1800be509`
- `WS2_32!WSACloseEvent` at `0x1800be54c`
- `WS2_32!WSACloseEvent` at `0x1800be58f`
- `WS2_32!WSACloseEvent` at `0x1800be5d2`
- `WS2_32!WSACloseEvent` at `0x1800be615`
- `WS2_32!WSACloseEvent` at `0x1800be658`
- `WS2_32!__imp_WSAGetLastError` at `0x1800be40d`
- `WS2_32!__imp_WSAGetLastError` at `0x1800be450`
- `WS2_32!__imp_WSAGetLastError` at `0x1800be493`
- `WS2_32!__imp_WSAGetLastError` at `0x1800be4d6`
- `WS2_32!__imp_WSAGetLastError` at `0x1800be519`
- `WS2_32!__imp_WSAGetLastError` at `0x1800be55c`
- `WS2_32!__imp_WSAGetLastError` at `0x1800be59f`
- `WS2_32!__imp_WSAGetLastError` at `0x1800be5e2`
- `WS2_32!__imp_WSAGetLastError` at `0x1800be625`
- `WS2_32!__imp_WSAGetLastError` at `0x1800be668`
- `WS2_32!__imp_WSAGetLastError` at `0x1800be40d`
- `WS2_32!__imp_WSAGetLastError` at `0x1800be450`
- `WS2_32!__imp_WSAGetLastError` at `0x1800be493`
- `WS2_32!__imp_WSAGetLastError` at `0x1800be4d6`
- `WS2_32!__imp_WSAGetLastError` at `0x1800be519`
- `WS2_32!__imp_WSAGetLastError` at `0x1800be55c`
- `WS2_32!__imp_WSAGetLastError` at `0x1800be59f`
- `WS2_32!__imp_WSAGetLastError` at `0x1800be5e2`
- `WS2_32!__imp_WSAGetLastError` at `0x1800be625`
- `WS2_32!__imp_WSAGetLastError` at `0x1800be668`
- `KERNEL32!DeleteCriticalSection` at `0x1800be696`
- `KERNEL32!DeleteCriticalSection` at `0x1800be696`
- `KERNEL32!CloseHandle` at `0x1800be6b3`
- `KERNEL32!CloseHandle` at `0x1800be6d0`
- `KERNEL32!CloseHandle` at `0x1800be6ed`
- `KERNEL32!CloseHandle` at `0x1800be6b3`
- `KERNEL32!CloseHandle` at `0x1800be6d0`
- `KERNEL32!CloseHandle` at `0x1800be6ed`
- `KERNEL32!HeapFree` at `0x1800be3c9`
- `KERNEL32!HeapFree` at `0x1800be3c9`

## string_xrefs

- `0x1800be3ea`: `WSACloseEvent`

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
0x1800be358  mov     [rsp+arg_0], rbx
0x1800be35d  mov     [rsp+arg_8], rsi
0x1800be362  push    rdi
0x1800be363  sub     rsp, 20h
0x1800be367  xor     esi, esi
0x1800be369  lea     rbx, gBndFailoverEndpointsQueue
0x1800be370  lea     edi, [rsi+20h]
0x1800be373  mov     rcx, [rbx]
0x1800be376  test    rcx, rcx
0x1800be379  jz      short loc_1800BE3D9
0x1800be37b  mov     rcx, [rcx]; lpMem
0x1800be37e  call    MessageQCleanup
0x1800be383  mov     esi, eax
0x1800be385  test    eax, eax
0x1800be387  jz      short loc_1800BE3BD
0x1800be389  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be390  lea     rax, WPP_GLOBAL_Control
0x1800be397  cmp     rcx, rax
0x1800be39a  jz      short loc_1800BE3BD
0x1800be39c  test    dword ptr [rcx+1Ch], 800000h
0x1800be3a3  jz      short loc_1800BE3BD
0x1800be3a5  mov     rcx, [rcx+10h]
0x1800be3a9  lea     r8, WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids
0x1800be3b0  mov     edx, 5Dh ; ']'
0x1800be3b5  mov     r9d, esi
0x1800be3b8  call    WPP_SF_D
0x1800be3bd  mov     r8, [rbx]; lpMem
0x1800be3c0  xor     edx, edx; dwFlags
0x1800be3c2  mov     rcx, cs:gDhcpHeap; hHeap
0x1800be3c9  call    cs:__imp_HeapFree
0x1800be3d0  nop     dword ptr [rax+rax+00h]
0x1800be3d5  and     qword ptr [rbx], 0
0x1800be3d9  add     rbx, 8
0x1800be3dd  sub     rdi, 1
0x1800be3e1  jnz     short loc_1800BE373
0x1800be3e3  mov     rcx, cs:gLeaseDBupdateQFullEvent; hEvent
0x1800be3ea  lea     rbx, aWsacloseevent; "WSACloseEvent"
0x1800be3f1  lea     rdi, aDhcpbndcleanup_0; "DhcpBNDCleanup"
0x1800be3f8  test    rcx, rcx
0x1800be3fb  jz      short loc_1800BE434
0x1800be3fd  call    cs:__imp_WSACloseEvent
0x1800be404  nop     dword ptr [rax+rax+00h]
0x1800be409  test    eax, eax
0x1800be40b  jnz     short loc_1800BE42C
0x1800be40d  call    cs:__imp_WSAGetLastError
0x1800be414  nop     dword ptr [rax+rax+00h]
0x1800be419  mov     r9d, 100Eh
0x1800be41f  mov     r8, rbx
0x1800be422  mov     ecx, eax
0x1800be424  mov     rdx, rdi
0x1800be427  call    DhcpPrintFOErrorEx
0x1800be42c  and     cs:gLeaseDBupdateQFullEvent, 0
0x1800be434  mov     rcx, cs:gStartBndSendProcessingReqEvent; hEvent
0x1800be43b  test    rcx, rcx
0x1800be43e  jz      short loc_1800BE477
0x1800be440  call    cs:__imp_WSACloseEvent
0x1800be447  nop     dword ptr [rax+rax+00h]
0x1800be44c  test    eax, eax
0x1800be44e  jnz     short loc_1800BE46F
0x1800be450  call    cs:__imp_WSAGetLastError
0x1800be457  nop     dword ptr [rax+rax+00h]
0x1800be45c  mov     r9d, 100Fh
0x1800be462  mov     r8, rbx
0x1800be465  mov     ecx, eax
0x1800be467  mov     rdx, rdi
0x1800be46a  call    DhcpPrintFOErrorEx
0x1800be46f  and     cs:gStartBndSendProcessingReqEvent, 0
0x1800be477  mov     rcx, cs:gStartBndRecvProcessingReqEvent; hEvent
0x1800be47e  test    rcx, rcx
0x1800be481  jz      short loc_1800BE4BA
0x1800be483  call    cs:__imp_WSACloseEvent
0x1800be48a  nop     dword ptr [rax+rax+00h]
0x1800be48f  test    eax, eax
0x1800be491  jnz     short loc_1800BE4B2
0x1800be493  call    cs:__imp_WSAGetLastError
0x1800be49a  nop     dword ptr [rax+rax+00h]
0x1800be49f  mov     r9d, 1010h
0x1800be4a5  mov     r8, rbx
0x1800be4a8  mov     ecx, eax
0x1800be4aa  mov     rdx, rdi
0x1800be4ad  call    DhcpPrintFOErrorEx
0x1800be4b2  and     cs:gStartBndRecvProcessingReqEvent, 0
0x1800be4ba  mov     rcx, cs:gTerminateBndSendThreadEvent; hEvent
0x1800be4c1  test    rcx, rcx
0x1800be4c4  jz      short loc_1800BE4FD
0x1800be4c6  call    cs:__imp_WSACloseEvent
0x1800be4cd  nop     dword ptr [rax+rax+00h]
0x1800be4d2  test    eax, eax
0x1800be4d4  jnz     short loc_1800BE4F5
0x1800be4d6  call    cs:__imp_WSAGetLastError
0x1800be4dd  nop     dword ptr [rax+rax+00h]
0x1800be4e2  mov     r9d, 1011h
0x1800be4e8  mov     r8, rbx
0x1800be4eb  mov     ecx, eax
0x1800be4ed  mov     rdx, rdi
0x1800be4f0  call    DhcpPrintFOErrorEx
0x1800be4f5  and     cs:gTerminateBndSendThreadEvent, 0
0x1800be4fd  mov     rcx, cs:gTerminateBndRecvThreadEvent; hEvent
0x1800be504  test    rcx, rcx
0x1800be507  jz      short loc_1800BE540
0x1800be509  call    cs:__imp_WSACloseEvent
0x1800be510  nop     dword ptr [rax+rax+00h]
0x1800be515  test    eax, eax
0x1800be517  jnz     short loc_1800BE538
0x1800be519  call    cs:__imp_WSAGetLastError
0x1800be520  nop     dword ptr [rax+rax+00h]
0x1800be525  mov     r9d, 1012h
0x1800be52b  mov     r8, rbx
0x1800be52e  mov     ecx, eax
0x1800be530  mov     rdx, rdi
0x1800be533  call    DhcpPrintFOErrorEx
0x1800be538  and     cs:gTerminateBndRecvThreadEvent, 0
0x1800be540  mov     rcx, cs:gTerminateBndSendThreadCompleteEvent; hEvent
0x1800be547  test    rcx, rcx
0x1800be54a  jz      short loc_1800BE583
0x1800be54c  call    cs:__imp_WSACloseEvent
0x1800be553  nop     dword ptr [rax+rax+00h]
0x1800be558  test    eax, eax
0x1800be55a  jnz     short loc_1800BE57B
0x1800be55c  call    cs:__imp_WSAGetLastError
0x1800be563  nop     dword ptr [rax+rax+00h]
0x1800be568  mov     r9d, 1013h
0x1800be56e  mov     r8, rbx
0x1800be571  mov     ecx, eax
0x1800be573  mov     rdx, rdi
0x1800be576  call    DhcpPrintFOErrorEx
0x1800be57b  and     cs:gTerminateBndSendThreadCompleteEvent, 0
0x1800be583  mov     rcx, cs:gTerminateBndRecvThreadCompleteEvent; hEvent
0x1800be58a  test    rcx, rcx
0x1800be58d  jz      short loc_1800BE5C6
0x1800be58f  call    cs:__imp_WSACloseEvent
0x1800be596  nop     dword ptr [rax+rax+00h]
0x1800be59b  test    eax, eax
0x1800be59d  jnz     short loc_1800BE5BE
0x1800be59f  call    cs:__imp_WSAGetLastError
0x1800be5a6  nop     dword ptr [rax+rax+00h]
0x1800be5ab  mov     r9d, 1014h
0x1800be5b1  mov     r8, rbx
0x1800be5b4  mov     ecx, eax
0x1800be5b6  mov     rdx, rdi
0x1800be5b9  call    DhcpPrintFOErrorEx
0x1800be5be  and     cs:gTerminateBndRecvThreadCompleteEvent, 0
0x1800be5c6  mov     rcx, cs:gStartBndCoreProcessingReqEvent; hEvent
0x1800be5cd  test    rcx, rcx
0x1800be5d0  jz      short loc_1800BE609
0x1800be5d2  call    cs:__imp_WSACloseEvent
0x1800be5d9  nop     dword ptr [rax+rax+00h]
0x1800be5de  test    eax, eax
0x1800be5e0  jnz     short loc_1800BE601
0x1800be5e2  call    cs:__imp_WSAGetLastError
0x1800be5e9  nop     dword ptr [rax+rax+00h]
0x1800be5ee  mov     r9d, 1015h
0x1800be5f4  mov     r8, rbx
0x1800be5f7  mov     ecx, eax
0x1800be5f9  mov     rdx, rdi
0x1800be5fc  call    DhcpPrintFOErrorEx
0x1800be601  and     cs:gStartBndCoreProcessingReqEvent, 0
0x1800be609  mov     rcx, cs:gTerminateBndCoreThreadEvent; hEvent
0x1800be610  test    rcx, rcx
0x1800be613  jz      short loc_1800BE64C
0x1800be615  call    cs:__imp_WSACloseEvent
0x1800be61c  nop     dword ptr [rax+rax+00h]
0x1800be621  test    eax, eax
0x1800be623  jnz     short loc_1800BE644
0x1800be625  call    cs:__imp_WSAGetLastError
0x1800be62c  nop     dword ptr [rax+rax+00h]
0x1800be631  mov     r9d, 1016h
0x1800be637  mov     r8, rbx
0x1800be63a  mov     ecx, eax
0x1800be63c  mov     rdx, rdi
0x1800be63f  call    DhcpPrintFOErrorEx
0x1800be644  and     cs:gTerminateBndCoreThreadEvent, 0
0x1800be64c  mov     rcx, cs:gTerminateBndCoreThreadCompleteEvent; hEvent
0x1800be653  test    rcx, rcx
0x1800be656  jz      short loc_1800BE68F
0x1800be658  call    cs:__imp_WSACloseEvent
0x1800be65f  nop     dword ptr [rax+rax+00h]
0x1800be664  test    eax, eax
0x1800be666  jnz     short loc_1800BE687
0x1800be668  call    cs:__imp_WSAGetLastError
0x1800be66f  nop     dword ptr [rax+rax+00h]
0x1800be674  mov     r9d, 1017h
0x1800be67a  mov     r8, rbx
0x1800be67d  mov     ecx, eax
0x1800be67f  mov     rdx, rdi
0x1800be682  call    DhcpPrintFOErrorEx
0x1800be687  and     cs:gTerminateBndCoreThreadCompleteEvent, 0
0x1800be68f  lea     rcx, gBndFailoverEndpointCS; lpCriticalSection
0x1800be696  call    cs:__imp_DeleteCriticalSection
0x1800be69d  nop     dword ptr [rax+rax+00h]
0x1800be6a2  mov     rcx, cs:gBndSendThreadHandle; hObject
0x1800be6a9  lea     rax, [rcx-1]
0x1800be6ad  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800be6b1  ja      short loc_1800BE6BF
0x1800be6b3  call    cs:__imp_CloseHandle
0x1800be6ba  nop     dword ptr [rax+rax+00h]
0x1800be6bf  mov     rcx, cs:gBndRecvThreadHandle; hObject
0x1800be6c6  lea     rax, [rcx-1]
0x1800be6ca  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800be6ce  ja      short loc_1800BE6DC
0x1800be6d0  call    cs:__imp_CloseHandle
0x1800be6d7  nop     dword ptr [rax+rax+00h]
0x1800be6dc  mov     rcx, cs:gBndCoreThreadHandle; hObject
0x1800be6e3  lea     rax, [rcx-1]
0x1800be6e7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800be6eb  ja      short loc_1800BE6F9
0x1800be6ed  call    cs:__imp_CloseHandle
0x1800be6f4  nop     dword ptr [rax+rax+00h]
0x1800be6f9  mov     rbx, [rsp+28h+arg_0]
0x1800be6fe  mov     eax, esi
0x1800be700  mov     rsi, [rsp+28h+arg_8]
0x1800be705  add     rsp, 20h
0x1800be709  pop     rdi
0x1800be70a  retn
```
