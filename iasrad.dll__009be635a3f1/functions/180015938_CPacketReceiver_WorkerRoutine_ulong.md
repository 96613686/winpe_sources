# CPacketReceiver::WorkerRoutine(ulong)

- ea: `0x180015938`
- end: `0x1800160ab`
- name: `?WorkerRoutine@CPacketReceiver@@QEAA_NK@Z`
- size: `1907`
- prototype: `bool __fastcall(CPacketReceiver *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800147b0`

## callees

- `0x180002106`
- `0x1800094e4`
- `0x18000dc54`
- `0x18000e4e0`
- `0x1800126b8`
- `0x180014494`
- `0x180014580`
- `0x180014f88`
- `0x1800151cc`
- `0x1800157dc`
- `0x180015938`
- `0x180016244`
- `0x18001d31c`
- `0x18002819c`
- `0x18002e202`
- `0x18002e230`

## import_xrefs

- `msvcrt!free` at `0x180016042`
- `msvcrt!free` at `0x180016042`
- `KERNEL32!Sleep` at `0x180015b53`
- `KERNEL32!Sleep` at `0x180015c53`
- `KERNEL32!Sleep` at `0x180015b53`
- `KERNEL32!Sleep` at `0x180015c53`
- `WS2_32!__imp_recvfrom` at `0x180015d5f`
- `WS2_32!__imp_recvfrom` at `0x180015d5f`
- `WS2_32!__imp_select` at `0x180015b7c`
- `WS2_32!__imp_select` at `0x180015b7c`
- `WS2_32!__imp_WSAGetLastError` at `0x180015b8e`
- `WS2_32!__imp_WSAGetLastError` at `0x180015d70`
- `WS2_32!__imp_WSAGetLastError` at `0x180015b8e`
- `WS2_32!__imp_WSAGetLastError` at `0x180015d70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015f6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015f6d`

## string_xrefs

- `0x180015aab`: `Worker Thread exiting as packet processing is not enabled`
- `0x180015c91`: `Worker Thread exiting as packet processing is not enabled`
- `0x180015bba`: `Worker Thread failed on select call with error:%d`
- `0x180015da5`: `WARNING Worker Thread failed on recvfrom with error:%d`
- `0x180015e93`: `WARNING StartThreadIfNeeded failed in CPacketReceiver::WorkerRoutine`

## pseudocode

```c
char __fastcall CPacketReceiver::WorkerRoutine(CPacketReceiver *this, int a2)
{
  int v2; // r12d
  struct sockaddr *v4; // r15
  char *v5; // rdi
  SIZE_T v6; // rsi
  int v7; // r13d
  fd_set *p_readfds; // rcx
  __int64 v9; // rdx
  _OWORD *v10; // rax
  char v11; // bl
  int v12; // eax
  unsigned __int64 v13; // rsi
  int Error; // ebx
  PVOID *v15; // rax
  __int64 v16; // rdx
  unsigned __int64 v17; // rdx
  SOCKET v18; // rsi
  unsigned int v19; // eax
  int v20; // r9d
  PVOID *v21; // rax
  void *v22; // rcx
  int v23; // eax
  char v25; // [rsp+30h] [rbp-338h]
  void *v27; // [rsp+40h] [rbp-328h]
  int fromlen[4]; // [rsp+50h] [rbp-318h] BYREF
  char *v29; // [rsp+60h] [rbp-308h]
  SOCKET v30; // [rsp+68h] [rbp-300h]
  struct sockaddr *v31; // [rsp+70h] [rbp-2F8h]
  CPacketReceiver *v32; // [rsp+78h] [rbp-2F0h]
  int v33; // [rsp+80h] [rbp-2E8h]
  __int64 v34; // [rsp+88h] [rbp-2E0h]
  fd_set readfds; // [rsp+90h] [rbp-2D8h] BYREF
  _BYTE v36[144]; // [rsp+2A0h] [rbp-C8h] BYREF

  v2 = a2;
  v32 = this;
  fromlen[2] = a2;
  v25 = 0;
  v4 = 0;
  v31 = 0;
  v5 = 0;
  v29 = 0;
  v27 = 0;
  LODWORD(v6) = 4096;
  memset_0(&readfds, 0, sizeof(readfds));
  v30 = -1;
  v7 = 0;
  p_readfds = &readfds;
  v9 = 4;
  if ( v2 == 1 )
  {
    v10 = (_OWORD *)((char *)this + 224);
    do
    {
      *(_OWORD *)&p_readfds->fd_count = *v10;
      *(_OWORD *)&p_readfds->fd_array[1] = v10[1];
      *(_OWORD *)&p_readfds->fd_array[3] = v10[2];
      *(_OWORD *)&p_readfds->fd_array[5] = v10[3];
      *(_OWORD *)&p_readfds->fd_array[7] = v10[4];
      *(_OWORD *)&p_readfds->fd_array[9] = v10[5];
      *(_OWORD *)&p_readfds->fd_array[11] = v10[6];
      *(_OWORD *)&p_readfds->fd_array[13] = v10[7];
      p_readfds = (fd_set *)((char *)p_readfds + 128);
      v10 += 8;
      --v9;
    }
    while ( v9 );
  }
  else
  {
    v10 = (_OWORD *)((char *)this + 744);
    do
    {
      *(_OWORD *)&p_readfds->fd_count = *v10;
      *(_OWORD *)&p_readfds->fd_array[1] = v10[1];
      *(_OWORD *)&p_readfds->fd_array[3] = v10[2];
      *(_OWORD *)&p_readfds->fd_array[5] = v10[3];
      *(_OWORD *)&p_readfds->fd_array[7] = v10[4];
      *(_OWORD *)&p_readfds->fd_array[9] = v10[5];
      *(_OWORD *)&p_readfds->fd_array[11] = v10[6];
      *(_OWORD *)&p_readfds->fd_array[13] = v10[7];
      p_readfds = (fd_set *)((char *)p_readfds + 128);
      v10 += 8;
      --v9;
    }
    while ( v9 );
  }
  *(_QWORD *)&p_readfds->fd_count = *(_QWORD *)v10;
  while ( (unsigned int)CPacketIo::IsProcessingEnabled(this) )
  {
    v5 = (char *)memory_pool<4096,task_allocator>::allocate((LPCRITICAL_SECTION)((char *)this + 176));
    v29 = v5;
    if ( v5 )
    {
      v12 = select(0, &readfds, 0, 0, 0);
      v13 = v12;
      if ( v12 == -1 )
      {
        Error = WSAGetLastError();
        v15 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WppDbgPrint("Worker Thread failed on select call with error:%d");
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v13 + 19,
            (unsigned int)WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids,
            (unsigned int)"NPSRAD",
            Error);
          v15 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( Error == 10055 )
        {
          if ( v15 != &WPP_GLOBAL_Control && *((_BYTE *)v15 + 25) >= 2u && (*((_DWORD *)v15 + 7) & 0x100) != 0 )
          {
            WppDbgPrint("WARNING: out of memory condition on select in CPacketReceiver::WorkerRoutine");
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids, "NPSRAD");
          }
          v11 = 1;
          Sleep(5u);
          LODWORD(v6) = 4096;
          goto LABEL_76;
        }
LABEL_37:
        LODWORD(v6) = 4096;
LABEL_38:
        v11 = v25;
LABEL_76:
        v2 = a2;
        goto LABEL_77;
      }
      if ( (unsigned int)CPacketIo::IsProcessingEnabled(this) )
      {
        v17 = ++qword_180042A60 % v13;
        v18 = readfds.fd_array[qword_180042A60 % v13];
        v30 = v18;
        v4 = (struct sockaddr *)operator new[](0x80u, (const struct std::nothrow_t *)v17);
        v31 = v4;
        if ( v4 )
        {
          fromlen[0] = 128;
          v19 = recvfrom(v18, v5, 4096, 0, v4, fromlen);
          v6 = v19;
          if ( v19 == -1 )
          {
            v7 = WSAGetLastError();
            v33 = v7;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
            {
              WppDbgPrint("WARNING Worker Thread failed on recvfrom with error:%d");
              WPP_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                22,
                (unsigned int)WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids,
                (unsigned int)"NPSRAD",
                v7);
            }
          }
          v34 = 65;
          if ( (int)ias_inet_htow(v4, v36) >= 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WppDbgPrint("Receive RADIUS packet with size %d from %S");
            WPP_SF_sdS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              23,
              (unsigned int)WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids,
              v20,
              v6,
              (__int64)v36);
          }
          if ( (unsigned int)CPacketReceiver::StartThreadIfNeeded(this, a2) )
          {
            v21 = (PVOID *)WPP_GLOBAL_Control;
            v11 = 0;
          }
          else
          {
            v21 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
            {
              WppDbgPrint("WARNING StartThreadIfNeeded failed in CPacketReceiver::WorkerRoutine");
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                24,
                WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids,
                "NPSRAD");
              v21 = (PVOID *)WPP_GLOBAL_Control;
            }
            v11 = 1;
            v25 = 1;
          }
          if ( !(_DWORD)v6 )
          {
            if ( v21 != &WPP_GLOBAL_Control && *((_BYTE *)v21 + 25) >= 2u && (*((_DWORD *)v21 + 7) & 0x100) != 0 )
            {
              WppDbgPrint("WARNING failed to receive data, quit processing in CPacketReceiver::WorkerRoutine");
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                25,
                WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids,
                "NPSRAD");
            }
            goto LABEL_76;
          }
          if ( (_DWORD)v6 == -1 )
          {
            if ( v7 == 10040 )
            {
              v2 = a2;
              CPacketReceiver::ProcessInvalidPacketSize(this, a2, v5, v4);
              goto LABEL_77;
            }
            goto LABEL_76;
          }
          v22 = CoTaskMemAlloc(v6);
          v27 = v22;
          if ( v22 )
          {
            memcpy_0(v22, v5, v6);
            memory_pool<4096,task_allocator>::deallocate((LPCRITICAL_SECTION)((char *)this + 176));
            v5 = 0;
            v29 = 0;
            v23 = 1;
            v11 = v25;
            v2 = a2;
            goto LABEL_78;
          }
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
          {
            v11 = v25;
            v2 = a2;
            v23 = 0;
            goto LABEL_79;
          }
          WppDbgPrint("Unable to allocate memory for received Radius packet from Process Heap");
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids, "NPSRAD");
          goto LABEL_38;
        }
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
        {
          goto LABEL_37;
        }
        WppDbgPrint("Not enough memory to allocate SOCKADDR_STORAGE");
        v16 = 21;
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
        {
          goto LABEL_37;
        }
        WppDbgPrint("Worker Thread exiting as packet processing is not enabled");
        v16 = 20;
      }
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids, "NPSRAD");
      goto LABEL_37;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("unable to allocate memory from buffer pool for in-bound packet");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids, "NPSRAD");
    }
    Sleep(0x3E8u);
    v2 = a2;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Worker Thread exiting as packet processing is not enabled");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids, "NPSRAD");
  }
  v11 = 0;
LABEL_77:
  v23 = 0;
LABEL_78:
  v22 = v27;
LABEL_79:
  if ( v23 )
  {
    _InterlockedIncrement(&g_lPacketCount);
    if ( (int)CPacketReceiver::ReceivePacket((__int64)this, v22, v6, v4, v30, v2) < 0 )
      _InterlockedDecrement(&g_lPacketCount);
  }
  else
  {
    if ( v5 )
      memory_pool<4096,task_allocator>::deallocate((LPCRITICAL_SECTION)((char *)this + 176));
    if ( v4 )
      free(v4);
  }
  return v11;
}

```

## disassembly

```asm
0x180015938  mov     [rsp+arg_10], rbx
0x18001593d  mov     [rsp+arg_18], rsi
0x180015942  push    rdi
0x180015943  push    r12
0x180015945  push    r13
0x180015947  push    r14
0x180015949  push    r15
0x18001594b  sub     rsp, 340h
0x180015952  mov     rax, cs:__security_cookie
0x180015959  xor     rax, rsp
0x18001595c  mov     [rsp+368h+var_38], rax
0x180015964  mov     r12d, edx
0x180015967  mov     [rsp+368h+var_330], edx
0x18001596b  mov     r14, rcx
0x18001596e  mov     [rsp+368h+var_2F0], rcx
0x180015973  mov     [rsp+368h+var_310], edx
0x180015977  xor     ebx, ebx
0x180015979  mov     [rsp+368h+var_338], bl
0x18001597d  mov     [rsp+368h+var_334], ebx
0x180015981  mov     r15d, ebx
0x180015984  mov     [rsp+368h+var_2F8], rbx
0x180015989  mov     edi, ebx
0x18001598b  mov     [rsp+368h+var_308], rbx
0x180015990  mov     [rsp+368h+var_328], rbx
0x180015995  mov     esi, 1000h
0x18001599a  mov     [rsp+368h+var_31C], esi
0x18001599e  xor     edx, edx; Val
0x1800159a0  mov     r8d, 208h; Size
0x1800159a6  lea     rcx, [rsp+368h+readfds]; void *
0x1800159ae  call    memset_0
0x1800159b3  mov     [rsp+368h+var_300], 0FFFFFFFFFFFFFFFFh
0x1800159bc  mov     r13d, ebx
0x1800159bf  lea     rcx, [rsp+368h+readfds]
0x1800159c7  lea     edx, [rbx+4]
0x1800159ca  lea     ebx, [rdx+7Ch]
0x1800159cd  cmp     r12d, 1
0x1800159d1  jnz     short loc_180015A26
0x1800159d3  lea     rax, [r14+0E0h]
0x1800159da  movups  xmm0, xmmword ptr [rax]
0x1800159dd  movups  xmmword ptr [rcx], xmm0
0x1800159e0  movups  xmm1, xmmword ptr [rax+10h]
0x1800159e4  movups  xmmword ptr [rcx+10h], xmm1
0x1800159e8  movups  xmm0, xmmword ptr [rax+20h]
0x1800159ec  movups  xmmword ptr [rcx+20h], xmm0
0x1800159f0  movups  xmm1, xmmword ptr [rax+30h]
0x1800159f4  movups  xmmword ptr [rcx+30h], xmm1
0x1800159f8  movups  xmm0, xmmword ptr [rax+40h]
0x1800159fc  movups  xmmword ptr [rcx+40h], xmm0
0x180015a00  movups  xmm1, xmmword ptr [rax+50h]
0x180015a04  movups  xmmword ptr [rcx+50h], xmm1
0x180015a08  movups  xmm0, xmmword ptr [rax+60h]
0x180015a0c  movups  xmmword ptr [rcx+60h], xmm0
0x180015a10  movups  xmm1, xmmword ptr [rax+70h]
0x180015a14  movups  xmmword ptr [rcx+70h], xmm1
0x180015a18  add     rcx, rbx
0x180015a1b  add     rax, rbx
0x180015a1e  sub     rdx, 1
0x180015a22  jnz     short loc_1800159DA
0x180015a24  jmp     short loc_180015A77
0x180015a26  lea     rax, [r14+2E8h]
0x180015a2d  movups  xmm0, xmmword ptr [rax]
0x180015a30  movups  xmmword ptr [rcx], xmm0
0x180015a33  movups  xmm1, xmmword ptr [rax+10h]
0x180015a37  movups  xmmword ptr [rcx+10h], xmm1
0x180015a3b  movups  xmm0, xmmword ptr [rax+20h]
0x180015a3f  movups  xmmword ptr [rcx+20h], xmm0
0x180015a43  movups  xmm1, xmmword ptr [rax+30h]
0x180015a47  movups  xmmword ptr [rcx+30h], xmm1
0x180015a4b  movups  xmm0, xmmword ptr [rax+40h]
0x180015a4f  movups  xmmword ptr [rcx+40h], xmm0
0x180015a53  movups  xmm1, xmmword ptr [rax+50h]
0x180015a57  movups  xmmword ptr [rcx+50h], xmm1
0x180015a5b  movups  xmm0, xmmword ptr [rax+60h]
0x180015a5f  movups  xmmword ptr [rcx+60h], xmm0
0x180015a63  movups  xmm1, xmmword ptr [rax+70h]
0x180015a67  movups  xmmword ptr [rcx+70h], xmm1
0x180015a6b  add     rcx, rbx
0x180015a6e  add     rax, rbx
0x180015a71  sub     rdx, 1
0x180015a75  jnz     short loc_180015A2D
0x180015a77  mov     rax, [rax]
0x180015a7a  mov     [rcx], rax
0x180015a7d  mov     rcx, r14; this
0x180015a80  call    ?IsProcessingEnabled@CPacketIo@@IEAAHXZ; CPacketIo::IsProcessingEnabled(void)
0x180015a85  test    eax, eax
0x180015a87  jnz     short loc_180015AE3
0x180015a89  mov     rax, cs:WPP_GLOBAL_Control
0x180015a90  lea     rdx, WPP_GLOBAL_Control
0x180015a97  cmp     rax, rdx
0x180015a9a  jz      short loc_180015ADA
0x180015a9c  cmp     byte ptr [rax+19h], 2
0x180015aa0  jb      short loc_180015ADA
0x180015aa2  test    dword ptr [rax+1Ch], 100h
0x180015aa9  jz      short loc_180015ADA
0x180015aab  lea     rcx, aWorkerThreadEx; "Worker Thread exiting as packet process"...
0x180015ab2  call    WppDbgPrint
0x180015ab7  mov     edx, 10h
0x180015abc  lea     r9, aNpsrad; "NPSRAD"
0x180015ac3  lea     r8, WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids
0x180015aca  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ad1  mov     rcx, [rcx+10h]
0x180015ad5  call    WPP_SF_s
0x180015ada  mov     bl, [rsp+368h+var_338]
0x180015ade  jmp     loc_180016019
0x180015ae3  lea     r12, [r14+0B0h]
0x180015aea  mov     rcx, r12; lpCriticalSection
0x180015aed  call    ?allocate@?$memory_pool@$0BAAA@Vtask_allocator@@@@QEAAPEAXXZ; memory_pool<4096,task_allocator>::allocate(void)
0x180015af2  mov     rdi, rax
0x180015af5  mov     [rsp+368h+var_308], rax
0x180015afa  test    rax, rax
0x180015afd  jnz     short loc_180015B63
0x180015aff  mov     rax, cs:WPP_GLOBAL_Control
0x180015b06  lea     rcx, WPP_GLOBAL_Control
0x180015b0d  cmp     rax, rcx
0x180015b10  jz      short loc_180015B4E
0x180015b12  cmp     byte ptr [rax+19h], 2
0x180015b16  jb      short loc_180015B4E
0x180015b18  test    dword ptr [rax+1Ch], 100h
0x180015b1f  jz      short loc_180015B4E
0x180015b21  lea     rcx, aUnableToAlloca_16; "unable to allocate memory from buffer p"...
0x180015b28  call    WppDbgPrint
0x180015b2d  lea     edx, [rdi+11h]
0x180015b30  lea     r9, aNpsrad; "NPSRAD"
0x180015b37  lea     r8, WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids
0x180015b3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b45  mov     rcx, [rcx+10h]
0x180015b49  call    WPP_SF_s
0x180015b4e  mov     ecx, 3E8h; dwMilliseconds
0x180015b53  call    cs:__imp_Sleep
0x180015b59  mov     r12d, [rsp+368h+var_330]
0x180015b5e  jmp     loc_180015A7D
0x180015b63  mov     [rsp+368h+timeout], 0; timeout
0x180015b6c  xor     r9d, r9d; exceptfds
0x180015b6f  xor     r8d, r8d; writefds
0x180015b72  lea     rdx, [rsp+368h+readfds]; readfds
0x180015b7a  xor     ecx, ecx; nfds
0x180015b7c  call    cs:__imp_select
0x180015b82  movsxd  rsi, eax
0x180015b85  cmp     esi, 0FFFFFFFFh
0x180015b88  jnz     loc_180015C63
0x180015b8e  call    cs:__imp_WSAGetLastError
0x180015b94  mov     ebx, eax
0x180015b96  mov     rax, cs:WPP_GLOBAL_Control
0x180015b9d  lea     rcx, WPP_GLOBAL_Control
0x180015ba4  cmp     rax, rcx
0x180015ba7  jz      short loc_180015BF9
0x180015ba9  cmp     byte ptr [rax+19h], 2
0x180015bad  jb      short loc_180015BF9
0x180015baf  test    dword ptr [rax+1Ch], 100h
0x180015bb6  jz      short loc_180015BF9
0x180015bb8  mov     edx, ebx
0x180015bba  lea     rcx, aWorkerThreadFa; "Worker Thread failed on select call wit"...
0x180015bc1  call    WppDbgPrint
0x180015bc6  lea     edx, [rsi+13h]
0x180015bc9  mov     dword ptr [rsp+368h+timeout], ebx
0x180015bcd  lea     r9, aNpsrad; "NPSRAD"
0x180015bd4  lea     r8, WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids
0x180015bdb  mov     rcx, cs:WPP_GLOBAL_Control
0x180015be2  mov     rcx, [rcx+10h]
0x180015be6  call    WPP_SF_sd
0x180015beb  mov     rax, cs:WPP_GLOBAL_Control
0x180015bf2  lea     rcx, WPP_GLOBAL_Control
0x180015bf9  cmp     ebx, 2747h
0x180015bff  jnz     loc_180015CC0
0x180015c05  cmp     rax, rcx
0x180015c08  jz      short loc_180015C48
0x180015c0a  cmp     byte ptr [rax+19h], 2
0x180015c0e  jb      short loc_180015C48
0x180015c10  test    dword ptr [rax+1Ch], 100h
0x180015c17  jz      short loc_180015C48
0x180015c19  lea     rcx, aWarningOutOfMe; "WARNING: out of memory condition on sel"...
0x180015c20  call    WppDbgPrint
0x180015c25  mov     edx, 13h
0x180015c2a  lea     r9, aNpsrad; "NPSRAD"
0x180015c31  lea     r8, WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids
0x180015c38  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c3f  mov     rcx, [rcx+10h]
0x180015c43  call    WPP_SF_s
0x180015c48  mov     bl, 1
0x180015c4a  mov     [rsp+368h+var_320], bl
0x180015c4e  mov     ecx, 5; dwMilliseconds
0x180015c53  call    cs:__imp_Sleep
0x180015c59  mov     esi, 1000h
0x180015c5e  jmp     loc_180016014
0x180015c63  mov     rcx, r14; this
0x180015c66  call    ?IsProcessingEnabled@CPacketIo@@IEAAHXZ; CPacketIo::IsProcessingEnabled(void)
0x180015c6b  test    eax, eax
0x180015c6d  jnz     short loc_180015CCE
0x180015c6f  mov     rax, cs:WPP_GLOBAL_Control
0x180015c76  lea     rcx, WPP_GLOBAL_Control
0x180015c7d  cmp     rax, rcx
0x180015c80  jz      short loc_180015CC0
0x180015c82  cmp     byte ptr [rax+19h], 2
0x180015c86  jb      short loc_180015CC0
0x180015c88  test    dword ptr [rax+1Ch], 100h
0x180015c8f  jz      short loc_180015CC0
0x180015c91  lea     rcx, aWorkerThreadEx; "Worker Thread exiting as packet process"...
0x180015c98  call    WppDbgPrint
0x180015c9d  mov     edx, 14h
0x180015ca2  lea     r9, aNpsrad; "NPSRAD"
0x180015ca9  lea     r8, WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids
0x180015cb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180015cb7  mov     rcx, [rcx+10h]
0x180015cbb  call    WPP_SF_s
0x180015cc0  mov     esi, 1000h
0x180015cc5  mov     bl, [rsp+368h+var_338]
0x180015cc9  jmp     loc_180016014
0x180015cce  mov     rax, cs:qword_180042A60
0x180015cd5  inc     rax
0x180015cd8  mov     cs:qword_180042A60, rax
0x180015cdf  xor     edx, edx; struct std::nothrow_t *
0x180015ce1  div     rsi
0x180015ce4  mov     rsi, [rsp+rdx*8+368h+readfds.fd_array]
0x180015cec  mov     [rsp+368h+var_300], rsi
0x180015cf1  mov     rcx, rbx; Size
0x180015cf4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180015cf9  mov     r15, rax
0x180015cfc  mov     [rsp+368h+var_2F8], rax
0x180015d01  test    rax, rax
0x180015d04  jnz     short loc_180015D3D
0x180015d06  mov     rax, cs:WPP_GLOBAL_Control
0x180015d0d  lea     rcx, WPP_GLOBAL_Control
0x180015d14  cmp     rax, rcx
0x180015d17  jz      short loc_180015CC0
0x180015d19  cmp     byte ptr [rax+19h], 2
0x180015d1d  jb      short loc_180015CC0
0x180015d1f  test    dword ptr [rax+1Ch], 100h
0x180015d26  jz      short loc_180015CC0
0x180015d28  lea     rcx, aNotEnoughMemor; "Not enough memory to allocate SOCKADDR_"...
0x180015d2f  call    WppDbgPrint
0x180015d34  lea     edx, [r15+15h]
0x180015d38  jmp     loc_180015CA2
0x180015d3d  mov     [rsp+368h+var_318], ebx
0x180015d41  lea     rax, [rsp+368h+var_318]
0x180015d46  mov     [rsp+368h+fromlen], rax; fromlen
0x180015d4b  mov     [rsp+368h+timeout], r15; from
0x180015d50  xor     r9d, r9d; flags
0x180015d53  mov     r8d, 1000h; len
0x180015d59  mov     rdx, rdi; buf
0x180015d5c  mov     rcx, rsi; s
0x180015d5f  call    cs:__imp_recvfrom
0x180015d65  mov     esi, eax
0x180015d67  mov     [rsp+368h+var_31C], esi
0x180015d6b  cmp     eax, 0FFFFFFFFh
0x180015d6e  jnz     short loc_180015DDB
0x180015d70  call    cs:__imp_WSAGetLastError
0x180015d76  mov     r13d, eax
0x180015d79  mov     [rsp+368h+var_2E8], eax
0x180015d80  mov     rax, cs:WPP_GLOBAL_Control
0x180015d87  lea     rbx, WPP_GLOBAL_Control
0x180015d8e  cmp     rax, rbx
0x180015d91  jz      short loc_180015DE2
0x180015d93  cmp     byte ptr [rax+19h], 2
0x180015d97  jb      short loc_180015DE2
0x180015d99  test    dword ptr [rax+1Ch], 100h
0x180015da0  jz      short loc_180015DE2
0x180015da2  mov     edx, r13d
0x180015da5  lea     rcx, aWarningWorkerT; "WARNING Worker Thread failed on recvfro"...
0x180015dac  call    WppDbgPrint
0x180015db1  mov     edx, 16h
0x180015db6  mov     dword ptr [rsp+368h+timeout], r13d
0x180015dbb  lea     r9, aNpsrad; "NPSRAD"
0x180015dc2  lea     r8, WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids
0x180015dc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180015dd0  mov     rcx, [rcx+10h]
0x180015dd4  call    WPP_SF_sd
0x180015dd9  jmp     short loc_180015DE2
0x180015ddb  lea     rbx, WPP_GLOBAL_Control
0x180015de2  mov     [rsp+368h+var_2E0], 41h ; 'A'
0x180015dee  lea     r8, [rsp+368h+var_2E0]
0x180015df6  lea     rdx, [rsp+368h+var_C8]; void *
0x180015dfe  mov     rcx, r15; pSockaddr
0x180015e01  call    ias_inet_htow
0x180015e06  test    eax, eax
0x180015e08  js      short loc_180015E68
0x180015e0a  mov     rax, cs:WPP_GLOBAL_Control
0x180015e11  cmp     rax, rbx
0x180015e14  jz      short loc_180015E68
0x180015e16  cmp     byte ptr [rax+19h], 4
0x180015e1a  jb      short loc_180015E68
0x180015e1c  test    dword ptr [rax+1Ch], 100h
0x180015e23  jz      short loc_180015E68
0x180015e25  lea     r8, [rsp+368h+var_C8]
0x180015e2d  mov     edx, esi
0x180015e2f  lea     rcx, aReceiveRadiusP; "Receive RADIUS packet with size %d from"...
0x180015e36  call    WppDbgPrint
0x180015e3b  mov     edx, 17h
0x180015e40  lea     rax, [rsp+368h+var_C8]
0x180015e48  mov     [rsp+368h+fromlen], rax
0x180015e4d  mov     dword ptr [rsp+368h+timeout], esi
0x180015e51  lea     r8, WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids
0x180015e58  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e5f  mov     rcx, [rcx+10h]
0x180015e63  call    WPP_SF_sdS
0x180015e68  mov     edx, [rsp+368h+var_330]; unsigned int
0x180015e6c  mov     rcx, r14; this
0x180015e6f  call    ?StartThreadIfNeeded@CPacketReceiver@@AEAAHK@Z; CPacketReceiver::StartThreadIfNeeded(ulong)
0x180015e74  test    eax, eax
0x180015e76  jnz     short loc_180015ED5
0x180015e78  mov     rax, cs:WPP_GLOBAL_Control
  ... truncated ...
```
