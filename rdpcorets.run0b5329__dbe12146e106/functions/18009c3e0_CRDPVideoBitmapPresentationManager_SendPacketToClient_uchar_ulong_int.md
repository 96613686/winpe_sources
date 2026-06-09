# CRDPVideoBitmapPresentationManager::SendPacketToClient(uchar *,ulong,int)

- ea: `0x18009c3e0`
- end: `0x18009c6ca`
- name: `?SendPacketToClient@CRDPVideoBitmapPresentationManager@@UEAAJPEAEKH@Z`
- size: `746`
- prototype: `__int64 __fastcall(CRDPVideoBitmapPresentationManager *this, unsigned __int8 *, __int64, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009e7d0`
- `0x18009fe80`
- `0x1800a0560`

## callees

- `0x1800091a8`
- `0x18000a93c`
- `0x18000c8c0`
- `0x180012200`
- `0x18002e600`
- `0x1800598d0`
- `0x18009c3e0`
- `0x1800a1020`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009c6ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009c6ab`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18009c414`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18009c414`
- `RDPSERVERBASE!?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z` at `0x18009c49e`
- `RDPSERVERBASE!?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z` at `0x18009c521`
- `RDPSERVERBASE!?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z` at `0x18009c5b9`
- `RDPSERVERBASE!?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z` at `0x18009c641`
- `RDPSERVERBASE!?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z` at `0x18009c49e`
- `RDPSERVERBASE!?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z` at `0x18009c521`
- `RDPSERVERBASE!?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z` at `0x18009c5b9`
- `RDPSERVERBASE!?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z` at `0x18009c641`

## string_xrefs

- `0x18009c66b`: `Cannot send packet to client.  DVC is not open.`

## pseudocode

```c
__int64 __fastcall CRDPVideoBitmapPresentationManager::SendPacketToClient(
        CRDPVideoBitmapPresentationManager *this,
        unsigned __int8 *a2,
        __int64 a3,
        int a4)
{
  CRdpVideoPacketManager *v4; // rbx
  char *v6; // rcx
  int v8; // r15d
  CRdpVideoPacketManager *v10; // rsi
  unsigned int v11; // ebx
  unsigned int v12; // eax
  unsigned int v13; // eax
  signed int v14; // eax
  unsigned int v15; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v18; // [rsp+20h] [rbp-58h]
  int v19; // [rsp+20h] [rbp-58h]
  CRdpVideoPacketManager *v20; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v21[8]; // [rsp+38h] [rbp-40h] BYREF
  int v22; // [rsp+80h] [rbp+8h] BYREF

  v4 = 0;
  v6 = (char *)this + 72;
  v20 = 0;
  v22 = 0;
  v8 = a3;
  v21[0] = v6;
  if ( *((_DWORD *)v6 + 2) )
    PAL_System_CritSecEnter(*(_QWORD *)v6, a2, a3);
  v10 = 0;
  if ( *((_QWORD *)this + 24) )
  {
    TCntPtr<CWppAutoTrace>::SafeRelease(&v20);
    v20 = (CRdpVideoPacketManager *)*((_QWORD *)this + 24);
    v4 = v20;
    TCntPtr<CTermInputMgr>::SafeAddRef(&v20);
    v10 = v4;
  }
  if ( !*((_DWORD *)this + 33) || !*((_DWORD *)this + 32) || !*((_DWORD *)this + 34) )
  {
    v11 = -2147467259;
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpVideoProcessor",
      "VideoBitmapPresentationManagerError_SendPacketToClientDvcClosedFail",
      (char *)0x3E0,
      0x80004005,
      v18);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        76,
        (unsigned int)&WPP_f15dbf156c7330b9dd817250924fb52e_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"Cannot send packet to client.  DVC is not open.",
        5);
    }
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)v21);
    goto LABEL_31;
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)v21);
  if ( !a2 )
  {
    v11 = -2147467261;
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpVideoProcessor",
      "VideoBitmapPresentationManagerError_SendPacketToClientNullPointer",
      (char *)0x3E5,
      0x80004003,
      v18);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        77,
        (unsigned int)&WPP_f15dbf156c7330b9dd817250924fb52e_Traceguids,
        v12,
        (__int64)"pBuffer");
    }
LABEL_31:
    CoTaskMemFree(a2);
    goto LABEL_32;
  }
  if ( !v10 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpVideoProcessor",
      "VideoBitmapPresentationManagerError_SendPacketToClientNullPointer",
      (char *)0x3EA,
      0x80004003,
      v18);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        78,
        (unsigned int)&WPP_f15dbf156c7330b9dd817250924fb52e_Traceguids,
        v13,
        (__int64)"spPacketManager");
    }
    v11 = -2147418113;
    goto LABEL_31;
  }
  v14 = CRdpVideoPacketManager::EnqueuePacket(v4, a4, v8, a2, &v22);
  v11 = v14;
  if ( v14 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpVideoProcessor",
      "VideoBitmapPresentationManagerError_SendPacketToClientEnqueuePacketFail",
      (char *)0x3F1,
      v14,
      v19);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        79,
        (unsigned int)&WPP_f15dbf156c7330b9dd817250924fb52e_Traceguids,
        v15,
        (__int64)"spPacketManager->EnqueuePacket() failed",
        v11);
    }
  }
  if ( !v22 )
    goto LABEL_31;
LABEL_32:
  TCntPtr<CWppAutoTrace>::SafeRelease(&v20);
  return v11;
}

```

## disassembly

```asm
0x18009c3e0  mov     rax, rsp
0x18009c3e3  push    rbx
0x18009c3e4  push    rbp
0x18009c3e5  push    rsi
0x18009c3e6  push    rdi
0x18009c3e7  push    r14
0x18009c3e9  push    r15
0x18009c3eb  sub     rsp, 48h
0x18009c3ef  xor     ebx, ebx
0x18009c3f1  mov     rdi, rcx
0x18009c3f4  add     rcx, 48h ; 'H'
0x18009c3f8  mov     [rax-48h], rbx
0x18009c3fc  mov     r14d, r9d
0x18009c3ff  mov     [rax+8], ebx
0x18009c402  mov     r15d, r8d
0x18009c405  mov     [rax-40h], rcx
0x18009c409  mov     rbp, rdx
0x18009c40c  cmp     [rcx+8], ebx
0x18009c40f  jz      short loc_18009C41A
0x18009c411  mov     rcx, [rcx]
0x18009c414  call    cs:__imp_PAL_System_CritSecEnter
0x18009c41a  xor     esi, esi
0x18009c41c  cmp     [rdi+0C0h], rbx
0x18009c423  jz      short loc_18009C448
0x18009c425  lea     rcx, [rsp+78h+var_48]
0x18009c42a  call    ?SafeRelease@?$TCntPtr@VCWppAutoTrace@@@@AEAAXXZ; TCntPtr<CWppAutoTrace>::SafeRelease(void)
0x18009c42f  mov     rbx, [rdi+0C0h]
0x18009c436  lea     rcx, [rsp+78h+var_48]
0x18009c43b  mov     [rsp+78h+var_48], rbx
0x18009c440  call    ?SafeAddRef@?$TCntPtr@VCTermInputMgr@@@@AEAAXXZ; TCntPtr<CTermInputMgr>::SafeAddRef(void)
0x18009c445  mov     rsi, rbx
0x18009c448  cmp     dword ptr [rdi+84h], 0
0x18009c44f  jz      loc_18009C625
0x18009c455  cmp     dword ptr [rdi+80h], 0
0x18009c45c  jz      loc_18009C625
0x18009c462  cmp     dword ptr [rdi+88h], 0
0x18009c469  jz      loc_18009C625
0x18009c46f  lea     rcx, [rsp+78h+var_40]; this
0x18009c474  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18009c479  test    rbp, rbp
0x18009c47c  jnz     loc_18009C502
0x18009c482  mov     ebx, 80004003h
0x18009c487  lea     rdx, aVideobitmappre_1; "VideoBitmapPresentationManagerError_Sen"...
0x18009c48e  mov     r9d, ebx
0x18009c491  lea     rcx, aIidIrdpvideopr; "IID_IRdpVideoProcessor"
0x18009c498  mov     r8d, 3E5h
0x18009c49e  call    cs:__imp_?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18009c4a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c4ab  lea     rax, WPP_GLOBAL_Control
0x18009c4b2  cmp     rcx, rax
0x18009c4b5  jz      loc_18009C6A8
0x18009c4bb  test    byte ptr [rcx+1Ch], 8
0x18009c4bf  jz      loc_18009C6A8
0x18009c4c5  cmp     byte ptr [rcx+19h], 2
0x18009c4c9  jb      loc_18009C6A8
0x18009c4cf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009c4d4  lea     rcx, aPbuffer; "pBuffer"
0x18009c4db  mov     r9d, eax
0x18009c4de  mov     [rsp+78h+var_58], rcx
0x18009c4e3  lea     edx, [rbp+4Dh]
0x18009c4e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c4ed  lea     r8, WPP_f15dbf156c7330b9dd817250924fb52e_Traceguids
0x18009c4f4  mov     rcx, [rcx+10h]
0x18009c4f8  call    WPP_SF_Ds
0x18009c4fd  jmp     loc_18009C6A8
0x18009c502  test    rsi, rsi
0x18009c505  jnz     short loc_18009C57E
0x18009c507  mov     r9d, 80004003h
0x18009c50d  lea     rdx, aVideobitmappre_1; "VideoBitmapPresentationManagerError_Sen"...
0x18009c514  mov     r8d, 3EAh
0x18009c51a  lea     rcx, aIidIrdpvideopr; "IID_IRdpVideoProcessor"
0x18009c521  call    cs:__imp_?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18009c527  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c52e  lea     rax, WPP_GLOBAL_Control
0x18009c535  cmp     rcx, rax
0x18009c538  jz      short loc_18009C574
0x18009c53a  test    byte ptr [rcx+1Ch], 8
0x18009c53e  jz      short loc_18009C574
0x18009c540  cmp     byte ptr [rcx+19h], 1
0x18009c544  jb      short loc_18009C574
0x18009c546  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009c54b  lea     rcx, aSppacketmanage; "spPacketManager"
0x18009c552  mov     r9d, eax
0x18009c555  mov     [rsp+78h+var_58], rcx
0x18009c55a  lea     edx, [rsi+4Eh]
0x18009c55d  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c564  lea     r8, WPP_f15dbf156c7330b9dd817250924fb52e_Traceguids
0x18009c56b  mov     rcx, [rcx+10h]
0x18009c56f  call    WPP_SF_Ds
0x18009c574  mov     ebx, 8000FFFFh
0x18009c579  jmp     loc_18009C6A8
0x18009c57e  lea     rax, [rsp+78h+arg_0]
0x18009c586  mov     r9, rbp; unsigned __int8 *
0x18009c589  mov     r8d, r15d; unsigned int
0x18009c58c  mov     [rsp+78h+var_58], rax; int *
0x18009c591  mov     edx, r14d; int
0x18009c594  mov     rcx, rbx; this
0x18009c597  call    ?EnqueuePacket@CRdpVideoPacketManager@@UEAAJHKPEAEPEAH@Z; CRdpVideoPacketManager::EnqueuePacket(int,ulong,uchar *,int *)
0x18009c59c  mov     ebx, eax
0x18009c59e  test    eax, eax
0x18009c5a0  jns     short loc_18009C612
0x18009c5a2  mov     r9d, eax
0x18009c5a5  lea     rdx, aVideobitmappre_13; "VideoBitmapPresentationManagerError_Sen"...
0x18009c5ac  mov     r8d, 3F1h
0x18009c5b2  lea     rcx, aIidIrdpvideopr; "IID_IRdpVideoProcessor"
0x18009c5b9  call    cs:__imp_?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18009c5bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c5c6  lea     rax, WPP_GLOBAL_Control
0x18009c5cd  cmp     rcx, rax
0x18009c5d0  jz      short loc_18009C612
0x18009c5d2  test    byte ptr [rcx+1Ch], 8
0x18009c5d6  jz      short loc_18009C612
0x18009c5d8  cmp     byte ptr [rcx+19h], 2
0x18009c5dc  jb      short loc_18009C612
0x18009c5de  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009c5e3  lea     rcx, aSppacketmanage_1; "spPacketManager->EnqueuePacket() failed"
0x18009c5ea  mov     [rsp+78h+var_50], ebx
0x18009c5ee  mov     [rsp+78h+var_58], rcx
0x18009c5f3  lea     r8, WPP_f15dbf156c7330b9dd817250924fb52e_Traceguids
0x18009c5fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c601  mov     edx, 4Fh ; 'O'
0x18009c606  mov     r9d, eax
0x18009c609  mov     rcx, [rcx+10h]
0x18009c60d  call    WPP_SF_DsD
0x18009c612  cmp     [rsp+78h+arg_0], 0
0x18009c61a  jnz     loc_18009C6B1
0x18009c620  jmp     loc_18009C6A8
0x18009c625  mov     ebx, 80004005h
0x18009c62a  lea     rdx, aVideobitmappre_5; "VideoBitmapPresentationManagerError_Sen"...
0x18009c631  mov     r9d, ebx
0x18009c634  lea     rcx, aIidIrdpvideopr; "IID_IRdpVideoProcessor"
0x18009c63b  mov     r8d, 3E0h
0x18009c641  call    cs:__imp_?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18009c647  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c64e  lea     rax, WPP_GLOBAL_Control
0x18009c655  cmp     rcx, rax
0x18009c658  jz      short loc_18009C69E
0x18009c65a  test    byte ptr [rcx+1Ch], 8
0x18009c65e  jz      short loc_18009C69E
0x18009c660  cmp     byte ptr [rcx+19h], 2
0x18009c664  jb      short loc_18009C69E
0x18009c666  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009c66b  lea     rcx, aCannotSendPack; "Cannot send packet to client.  DVC is n"...
0x18009c672  mov     [rsp+78h+var_50], 80004005h
0x18009c67a  mov     [rsp+78h+var_58], rcx
0x18009c67f  lea     r8, WPP_f15dbf156c7330b9dd817250924fb52e_Traceguids
0x18009c686  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c68d  mov     edx, 4Ch ; 'L'
0x18009c692  mov     r9d, eax
0x18009c695  mov     rcx, [rcx+10h]
0x18009c699  call    WPP_SF_DsD
0x18009c69e  lea     rcx, [rsp+78h+var_40]; this
0x18009c6a3  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18009c6a8  mov     rcx, rbp; pv
0x18009c6ab  call    cs:__imp_CoTaskMemFree
0x18009c6b1  lea     rcx, [rsp+78h+var_48]
0x18009c6b6  call    ?SafeRelease@?$TCntPtr@VCWppAutoTrace@@@@AEAAXXZ; TCntPtr<CWppAutoTrace>::SafeRelease(void)
0x18009c6bb  mov     eax, ebx
0x18009c6bd  add     rsp, 48h
0x18009c6c1  pop     r15
0x18009c6c3  pop     r14
0x18009c6c5  pop     rdi
0x18009c6c6  pop     rsi
0x18009c6c7  pop     rbp
0x18009c6c8  pop     rbx
0x18009c6c9  retn
```
