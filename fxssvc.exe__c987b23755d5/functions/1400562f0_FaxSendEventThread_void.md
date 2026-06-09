# FaxSendEventThread(void *)

- ea: `0x1400562f0`
- end: `0x1400565c8`
- name: `?FaxSendEventThread@@YAKPEAX@Z`
- size: `728`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140001b8c`
- `0x140002c43`
- `0x140004b30`
- `0x140004b58`
- `0x14004eedc`
- `0x1400562f0`
- `0x140056dd8`
- `0x140057268`
- `0x1400579c8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140056399`
- `KERNEL32!GetLastError` at `0x140056519`
- `KERNEL32!GetLastError` at `0x140056592`
- `KERNEL32!GetLastError` at `0x140056399`
- `KERNEL32!GetLastError` at `0x140056519`
- `KERNEL32!GetLastError` at `0x140056592`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14005650f`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14005650f`
- `KERNEL32!GetQueuedCompletionStatus` at `0x140056377`
- `KERNEL32!GetQueuedCompletionStatus` at `0x140056377`

## pseudocode

```c
__int64 __fastcall FaxSendEventThread(void *a1)
{
  CClientsMap *v1; // rcx
  DWORD LastError; // eax
  LPOVERLAPPED v3; // rbx
  unsigned int v4; // eax
  CMapDeviceId *v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // eax
  DWORD v8; // eax
  LPOVERLAPPED v9; // rbx
  DWORD v10; // eax
  DWORD NumberOfBytesTransferred; // [rsp+68h] [rbp+38h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+70h] [rbp+40h] BYREF
  unsigned __int64 CompletionKey; // [rsp+78h] [rbp+48h] BYREF

  NumberOfBytesTransferred = 0;
  CompletionKey = 0;
  Overlapped = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids);
  }
  while ( 1 )
  {
    while ( 1 )
    {
      while ( !GetQueuedCompletionStatus(
                 g_hSendEventsCompPort,
                 &NumberOfBytesTransferred,
                 &CompletionKey,
                 &Overlapped,
                 0xFFFFFFFF) )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, LastError);
        }
        v3 = Overlapped;
        if ( Overlapped )
        {
LABEL_38:
          memset_0(v3, 0, 0x50u);
          operator delete(v3);
LABEL_39:
          Overlapped = 0;
        }
      }
      if ( CompletionKey != 2 )
        break;
      if ( g_bServiceIsDown )
      {
LABEL_36:
        v3 = Overlapped;
        if ( Overlapped )
          goto LABEL_37;
      }
      else if ( Overlapped )
      {
        v4 = CClientsMap::Notify(v1, (const struct CClientID *)Overlapped);
        if ( !v4 )
          goto LABEL_34;
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_34;
        }
        v6 = 79;
LABEL_33:
        WPP_SF_d(*((_QWORD *)v5 + 2), v6, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, v4);
LABEL_34:
        v3 = Overlapped;
LABEL_37:
        if ( !v3 )
          goto LABEL_39;
        goto LABEL_38;
      }
    }
    if ( CompletionKey != 3 )
      break;
    if ( g_bServiceIsDown )
      goto LABEL_36;
    if ( Overlapped )
    {
      v7 = CClientsMap::OpenClientConnection(v1, (const struct CClientID *)Overlapped);
      if ( !v7 )
        goto LABEL_34;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, v7);
      }
      v4 = CClientsMap::ReleaseClient(g_pClientsMap, (const struct CClientID *)Overlapped, 0);
      if ( !v4 )
        goto LABEL_34;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_34;
      }
      v6 = 81;
      goto LABEL_33;
    }
  }
  if ( CompletionKey != 0xFFFFFFFF )
    goto LABEL_36;
  if ( !PostQueuedCompletionStatus(g_hSendEventsCompPort, 0, 0xFFFFFFFF, 0) )
  {
    v8 = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, v8);
    }
  }
  v9 = Overlapped;
  if ( Overlapped )
  {
    memset_0(Overlapped, 0, 0x50u);
    operator delete(v9);
    Overlapped = 0;
  }
  if ( !(unsigned int)DecreaseServiceThreadsCount()
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, v10);
  }
  return 0;
}

```

## disassembly

```asm
0x1400562f0  mov     [rsp-28h+arg_0], rbx
0x1400562f5  push    rbp
0x1400562f6  push    r12
0x1400562f8  push    r13
0x1400562fa  push    r14
0x1400562fc  push    r15
0x1400562fe  mov     rbp, rsp
0x140056301  sub     rsp, 30h
0x140056305  mov     [rbp+NumberOfBytesTransferred], 0
0x14005630c  mov     [rbp+CompletionKey], 0
0x140056314  mov     [rbp+Overlapped], 0
0x14005631c  mov     rcx, cs:WPP_GLOBAL_Control
0x140056323  lea     r14, WPP_GLOBAL_Control
0x14005632a  lea     r15, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x140056331  cmp     rcx, r14
0x140056334  jz      short loc_140056353
0x140056336  test    byte ptr [rcx+1Ch], 4
0x14005633a  jz      short loc_140056353
0x14005633c  cmp     byte ptr [rcx+19h], 5
0x140056340  jb      short loc_140056353
0x140056342  mov     rcx, [rcx+10h]
0x140056346  mov     edx, 4Dh ; 'M'
0x14005634b  mov     r8, r15
0x14005634e  call    WPP_SF_
0x140056353  mov     r13d, 0FFFFFFFFh
0x140056359  mov     r12d, 50h ; 'P'
0x14005635f  mov     rcx, cs:?g_hSendEventsCompPort@@3PEAXEA; CompletionPort
0x140056366  lea     r9, [rbp+Overlapped]; lpOverlapped
0x14005636a  lea     r8, [rbp+CompletionKey]; lpCompletionKey
0x14005636e  mov     [rsp+30h+dwMilliseconds], r13d; dwMilliseconds
0x140056373  lea     rdx, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x140056377  call    cs:__imp_GetQueuedCompletionStatus
0x14005637d  test    eax, eax
0x14005637f  jnz     short loc_1400563C8
0x140056381  mov     rax, cs:WPP_GLOBAL_Control
0x140056388  cmp     rax, r14
0x14005638b  jz      short loc_1400563BA
0x14005638d  test    byte ptr [rax+1Ch], 4
0x140056391  jz      short loc_1400563BA
0x140056393  cmp     byte ptr [rax+19h], 2
0x140056397  jb      short loc_1400563BA
0x140056399  call    cs:__imp_GetLastError
0x14005639f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400563a6  mov     edx, 4Eh ; 'N'
0x1400563ab  mov     r9d, eax
0x1400563ae  mov     r8, r15
0x1400563b1  mov     rcx, [rcx+10h]
0x1400563b5  call    WPP_SF_d
0x1400563ba  mov     rbx, [rbp+Overlapped]
0x1400563be  test    rbx, rbx
0x1400563c1  jz      short loc_14005635F
0x1400563c3  jmp     loc_1400564DE
0x1400563c8  mov     rax, [rbp+CompletionKey]
0x1400563cc  cmp     rax, 2
0x1400563d0  jnz     short loc_140056427
0x1400563d2  cmp     cs:?g_bServiceIsDown@@3HA, 0; int g_bServiceIsDown
0x1400563d9  jnz     loc_1400564CC
0x1400563df  mov     rdx, [rbp+Overlapped]; struct CClientID *
0x1400563e3  test    rdx, rdx
0x1400563e6  jz      loc_14005635F
0x1400563ec  call    ?Notify@CClientsMap@@QEAAKAEBVCClientID@@@Z; CClientsMap::Notify(CClientID const &)
0x1400563f1  test    eax, eax
0x1400563f3  jz      loc_1400564C1
0x1400563f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140056400  cmp     rcx, r14
0x140056403  jz      loc_1400564C1
0x140056409  test    byte ptr [rcx+1Ch], 4
0x14005640d  jz      loc_1400564C1
0x140056413  cmp     byte ptr [rcx+19h], 2
0x140056417  jb      loc_1400564C1
0x14005641d  mov     edx, 4Fh ; 'O'
0x140056422  jmp     loc_1400564B2
0x140056427  cmp     rax, 3
0x14005642b  jnz     loc_1400564C7
0x140056431  cmp     cs:?g_bServiceIsDown@@3HA, 0; int g_bServiceIsDown
0x140056438  jnz     loc_1400564CC
0x14005643e  mov     rdx, [rbp+Overlapped]; struct CClientID *
0x140056442  test    rdx, rdx
0x140056445  jz      loc_14005635F
0x14005644b  call    ?OpenClientConnection@CClientsMap@@QEAAKAEBVCClientID@@@Z; CClientsMap::OpenClientConnection(CClientID const &)
0x140056450  test    eax, eax
0x140056452  jz      short loc_1400564C1
0x140056454  mov     rcx, cs:WPP_GLOBAL_Control
0x14005645b  cmp     rcx, r14
0x14005645e  jz      short loc_14005647E
0x140056460  test    byte ptr [rcx+1Ch], 4
0x140056464  jz      short loc_14005647E
0x140056466  cmp     byte ptr [rcx+19h], 2
0x14005646a  jb      short loc_14005647E
0x14005646c  mov     rcx, [rcx+10h]
0x140056470  mov     edx, r12d
0x140056473  mov     r9d, eax
0x140056476  mov     r8, r15
0x140056479  call    WPP_SF_d
0x14005647e  mov     rdx, [rbp+Overlapped]; struct CClientID *
0x140056482  xor     r8d, r8d; int
0x140056485  mov     rcx, cs:?g_pClientsMap@@3PEAVCClientsMap@@EA; this
0x14005648c  call    ?ReleaseClient@CClientsMap@@QEAAKAEBVCClientID@@H@Z; CClientsMap::ReleaseClient(CClientID const &,int)
0x140056491  test    eax, eax
0x140056493  jz      short loc_1400564C1
0x140056495  mov     rcx, cs:WPP_GLOBAL_Control
0x14005649c  cmp     rcx, r14
0x14005649f  jz      short loc_1400564C1
0x1400564a1  test    byte ptr [rcx+1Ch], 4
0x1400564a5  jz      short loc_1400564C1
0x1400564a7  cmp     byte ptr [rcx+19h], 2
0x1400564ab  jb      short loc_1400564C1
0x1400564ad  mov     edx, 51h ; 'Q'
0x1400564b2  mov     rcx, [rcx+10h]
0x1400564b6  mov     r9d, eax
0x1400564b9  mov     r8, r15
0x1400564bc  call    WPP_SF_d
0x1400564c1  mov     rbx, [rbp+Overlapped]
0x1400564c5  jmp     short loc_1400564D9
0x1400564c7  cmp     rax, r13
0x1400564ca  jz      short loc_140056500
0x1400564cc  mov     rbx, [rbp+Overlapped]
0x1400564d0  test    rbx, rbx
0x1400564d3  jz      loc_14005635F
0x1400564d9  test    rbx, rbx
0x1400564dc  jz      short loc_1400564F3
0x1400564de  mov     r8, r12; Size
0x1400564e1  xor     edx, edx; Val
0x1400564e3  mov     rcx, rbx; void *
0x1400564e6  call    memset_0
0x1400564eb  mov     rcx, rbx; Block
0x1400564ee  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400564f3  mov     [rbp+Overlapped], 0
0x1400564fb  jmp     loc_14005635F
0x140056500  mov     rcx, cs:?g_hSendEventsCompPort@@3PEAXEA; CompletionPort
0x140056507  xor     r9d, r9d; lpOverlapped
0x14005650a  mov     r8, r13; dwCompletionKey
0x14005650d  xor     edx, edx; dwNumberOfBytesTransferred
0x14005650f  call    cs:__imp_PostQueuedCompletionStatus
0x140056515  test    eax, eax
0x140056517  jnz     short loc_14005654B
0x140056519  call    cs:__imp_GetLastError
0x14005651f  mov     rcx, cs:WPP_GLOBAL_Control
0x140056526  cmp     rcx, r14
0x140056529  jz      short loc_14005654B
0x14005652b  test    byte ptr [rcx+1Ch], 4
0x14005652f  jz      short loc_14005654B
0x140056531  cmp     byte ptr [rcx+19h], 2
0x140056535  jb      short loc_14005654B
0x140056537  mov     rcx, [rcx+10h]
0x14005653b  mov     edx, 52h ; 'R'
0x140056540  mov     r9d, eax
0x140056543  mov     r8, r15
0x140056546  call    WPP_SF_d
0x14005654b  mov     rbx, [rbp+Overlapped]
0x14005654f  test    rbx, rbx
0x140056552  jz      short loc_140056571
0x140056554  mov     r8, r12; Size
0x140056557  xor     edx, edx; Val
0x140056559  mov     rcx, rbx; void *
0x14005655c  call    memset_0
0x140056561  mov     rcx, rbx; Block
0x140056564  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140056569  mov     [rbp+Overlapped], 0
0x140056571  call    ?DecreaseServiceThreadsCount@@YAHXZ; DecreaseServiceThreadsCount(void)
0x140056576  test    eax, eax
0x140056578  jnz     short loc_1400565B3
0x14005657a  mov     rax, cs:WPP_GLOBAL_Control
0x140056581  cmp     rax, r14
0x140056584  jz      short loc_1400565B3
0x140056586  test    byte ptr [rax+1Ch], 4
0x14005658a  jz      short loc_1400565B3
0x14005658c  cmp     byte ptr [rax+19h], 2
0x140056590  jb      short loc_1400565B3
0x140056592  call    cs:__imp_GetLastError
0x140056598  mov     rcx, cs:WPP_GLOBAL_Control
0x14005659f  mov     edx, 53h ; 'S'
0x1400565a4  mov     r9d, eax
0x1400565a7  mov     r8, r15
0x1400565aa  mov     rcx, [rcx+10h]
0x1400565ae  call    WPP_SF_d
0x1400565b3  mov     rbx, [rsp+30h+arg_0]
0x1400565b8  xor     eax, eax
0x1400565ba  add     rsp, 30h
0x1400565be  pop     r15
0x1400565c0  pop     r14
0x1400565c2  pop     r13
0x1400565c4  pop     r12
0x1400565c6  pop     rbp
0x1400565c7  retn
```
