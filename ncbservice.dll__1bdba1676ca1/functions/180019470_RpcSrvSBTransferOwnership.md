# RpcSrvSBTransferOwnership

- ea: `0x180019470`
- end: `0x180019d11`
- name: `RpcSrvSBTransferOwnership`
- size: `2209`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, unsigned int *, const unsigned __int16 *, int, int, int, unsigned int, unsigned __int8, unsigned __int64, unsigned int, struct _SOCKET_BROKER_APP_CONTEXT *, struct _SOCKET_BROKER_SSL_CONTEXT *, struct _DNS_REGISTRATION_DATA *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180004a30`
- `0x18000a0a0`
- `0x18000a160`
- `0x180012c60`
- `0x180017804`
- `0x180019470`
- `0x18001d8e0`
- `0x18001d910`
- `0x18002666c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019c40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019c9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019c40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019c9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019c4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019caa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019c4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019caa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019cc7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019cc7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019709`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019bd2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019709`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019bd2`
- `RPCRT4!RpcRevertToSelf` at `0x180019934`
- `RPCRT4!RpcRevertToSelf` at `0x180019c59`
- `RPCRT4!RpcRevertToSelf` at `0x180019934`
- `RPCRT4!RpcRevertToSelf` at `0x180019c59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019c67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019cbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019c67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019cbd`

## string_xrefs

- `0x180019be8`: `RpcSrvSBTransferOwnership: completed`

## pseudocode

```c
__int64 __fastcall RpcSrvSBTransferOwnership(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned int *a3,
        const unsigned __int16 *a4,
        int a5,
        int a6,
        int a7,
        unsigned int a8,
        unsigned __int8 a9,
        unsigned __int64 a10,
        unsigned int a11,
        struct _SOCKET_BROKER_APP_CONTEXT *a12,
        struct _SOCKET_BROKER_SSL_CONTEXT *a13,
        struct _DNS_REGISTRATION_DATA *a14)
{
  const unsigned __int16 *v14; // rsi
  struct _SOCKET_BROKER_SSL_CONTEXT *v16; // rcx
  struct SocketBrokerContext *v17; // rbx
  unsigned __int16 *v18; // rdi
  bool v19; // r13
  HANDLE v20; // r12
  struct _GUID *v21; // rdx
  int v22; // r12d
  int v23; // ebx
  __int64 v24; // rax
  __int64 v25; // r8
  int v26; // r14d
  char v27; // al
  __int64 v28; // rax
  __int64 v29; // rax
  unsigned __int16 *v30; // rax
  unsigned int v31; // eax
  __int64 v32; // rdx
  __int64 *v33; // rcx
  __int64 v34; // rax
  unsigned int v35; // eax
  __int64 v36; // rax
  int v37; // eax
  HANDLE ProcessHeap; // rax
  void *v39; // rdi
  HANDLE v40; // rax
  void *v41; // rcx
  bool v43; // [rsp+70h] [rbp-168h] BYREF
  unsigned int v44; // [rsp+78h] [rbp-160h] BYREF
  unsigned int v45; // [rsp+80h] [rbp-158h] BYREF
  int v46; // [rsp+88h] [rbp-150h] BYREF
  int v47; // [rsp+90h] [rbp-148h] BYREF
  const wchar_t *v48; // [rsp+98h] [rbp-140h]
  HANDLE ProcessHandle; // [rsp+A0h] [rbp-138h] BYREF
  struct SocketBrokerContext *v50; // [rsp+A8h] [rbp-130h] BYREF
  BOOL v51; // [rsp+B0h] [rbp-128h] BYREF
  int v52; // [rsp+B4h] [rbp-124h] BYREF
  unsigned int v53; // [rsp+B8h] [rbp-120h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+C0h] [rbp-118h] BYREF
  unsigned __int16 *v55; // [rsp+D0h] [rbp-108h] BYREF
  struct _DNS_REGISTRATION_DATA *v56; // [rsp+D8h] [rbp-100h]
  struct _SOCKET_BROKER_SSL_CONTEXT *v57; // [rsp+E0h] [rbp-F8h]
  struct _SOCKET_BROKER_APP_CONTEXT *v58; // [rsp+E8h] [rbp-F0h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+F0h] [rbp-E8h] BYREF
  const wchar_t *v60; // [rsp+100h] [rbp-D8h]
  __int64 v61; // [rsp+108h] [rbp-D0h]
  unsigned int *v62; // [rsp+110h] [rbp-C8h]
  __int64 v63; // [rsp+118h] [rbp-C0h]
  void *v64; // [rsp+120h] [rbp-B8h]
  int v65; // [rsp+128h] [rbp-B0h]
  int v66; // [rsp+12Ch] [rbp-ACh]
  unsigned int *v67; // [rsp+130h] [rbp-A8h]
  __int64 v68; // [rsp+138h] [rbp-A0h]
  unsigned int *v69; // [rsp+140h] [rbp-98h]
  __int64 v70; // [rsp+148h] [rbp-90h]
  int *v71; // [rsp+150h] [rbp-88h]
  __int64 v72; // [rsp+158h] [rbp-80h]
  _DWORD *v73; // [rsp+160h] [rbp-78h]
  __int64 v74; // [rsp+168h] [rbp-70h]
  int *v75; // [rsp+170h] [rbp-68h]
  __int64 v76; // [rsp+178h] [rbp-60h]
  BOOL *v77; // [rsp+180h] [rbp-58h]
  __int64 v78; // [rsp+188h] [rbp-50h]

  v14 = a4;
  v48 = (const wchar_t *)a3;
  v58 = a12;
  v16 = a13;
  v57 = a13;
  v56 = a14;
  v17 = 0;
  v50 = 0;
  v18 = 0;
  v55 = 0;
  v19 = 0;
  v43 = 0;
  v20 = 0;
  ProcessHandle = 0;
  v21 = (struct _GUID *)&TraceLoggingMetadataEnd;
  if ( a3 && a4 && a10 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v22 = 10;
    if ( (unsigned int)dword_18004D068 <= 5 )
    {
      v23 = a9;
    }
    else
    {
      v51 = a13 != 0;
      v23 = a9;
      v52 = a9;
      v53 = a11;
      v46 = a7;
      v47 = a6;
      v45 = a5;
      v77 = &v51;
      v78 = 4;
      v75 = &v52;
      v76 = 4;
      v73 = &v53;
      v74 = 4;
      v71 = &v46;
      v72 = 4;
      v69 = (unsigned int *)&v47;
      v70 = 4;
      v67 = &v45;
      v68 = 4;
      v24 = -1;
      do
        ++v24;
      while ( a4[v24] );
      v64 = (void *)a4;
      v65 = 2 * v24 + 2;
      v66 = 0;
      v62 = a3;
      v63 = 16;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 5;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_18004D070;
      UserData.Size = *(unsigned __int16 *)off_18004D070;
      UserData.Reserved = 2;
      v60 = (const wchar_t *)&byte_18004563F;
      v61 = 0x100000081LL;
      v44 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xAu, &UserData);
    }
    v26 = RpcHelperRetriveSbContext(a2, v21, &v43, &v55, &v50, &ProcessHandle);
    v27 = Microsoft_Windows_Network_Connection_BrokerEnableBits;
    v18 = v55;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      v46 = v23;
      v47 = a7;
      v45 = a6;
      v44 = a5;
      v60 = v48;
      v61 = 16;
      v28 = -1;
      do
        ++v28;
      while ( v14[v28] );
      v62 = (unsigned int *)v14;
      v63 = (unsigned int)(2 * v28 + 2);
      if ( v55 )
      {
        v29 = -1;
        do
          ++v29;
        while ( v55[v29] );
        v22 = 2 * v29 + 2;
        v30 = v55;
      }
      else
      {
        v30 = L"NULL";
      }
      v64 = v30;
      v65 = v22;
      v66 = 0;
      v67 = &v44;
      v68 = 4;
      v69 = &v45;
      v70 = 4;
      v71 = &v47;
      v72 = 4;
      v73 = &v46;
      v74 = 4;
      McGenEventWrite_EventWriteTransfer(v16, SbTransferOwnership, v25, 8, &UserData);
      v27 = Microsoft_Windows_Network_Connection_BrokerEnableBits;
    }
    if ( v26 )
    {
      if ( (v27 & 1) != 0 )
      {
        v44 = v26;
        v60 = L"RpcSrvSBTransferOwnership: RpcHelperRetriveSbContext failed";
        v61 = 120;
        v62 = &v44;
        v63 = 4;
        McGenEventWrite_EventWriteTransfer(v16, NcbApiStatus, v25, 3, &UserData);
      }
      v17 = v50;
      v19 = v43;
      v20 = ProcessHandle;
    }
    else
    {
      v19 = v43;
      if ( v43 )
      {
        RpcRevertToSelf();
        v19 = 0;
      }
      v20 = ProcessHandle;
      v17 = v50;
      v31 = SocketBrokerContext::TransferOwnership(
              v50,
              v14,
              a5,
              a6,
              a7,
              a8,
              a9 != 0,
              a10,
              ProcessHandle,
              a11,
              v58,
              v57,
              v56);
      v26 = v31;
      if ( v31 && (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v16, v32, L"RpcSrvSBTransferOwnership: TransferOwnership failed", v31);
    }
  }
  else
  {
    v26 = 87;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      goto LABEL_30;
    v44 = 87;
    v60 = L"RpcSrvSBTransferOwnership: invalid parameter";
    v61 = 90;
    v62 = &v44;
    v63 = 4;
    McGenEventWrite_EventWriteTransfer(a13, NcbApiStatus, a3, 3, &UserData);
  }
  a3 = (unsigned int *)v48;
LABEL_30:
  if ( (unsigned int)dword_18004D068 > 5 )
  {
    v44 = v26;
    v69 = &v44;
    v70 = 4;
    if ( v18 )
    {
      v33 = (__int64 *)v18;
      v34 = -1;
      do
        ++v34;
      while ( v18[v34] );
      v35 = 2 * v34 + 2;
    }
    else
    {
      v33 = qword_18003ED50;
      v35 = 2;
    }
    v67 = (unsigned int *)v33;
    v68 = v35;
    if ( v14 )
    {
      v36 = -1;
      do
        ++v36;
      while ( v14[v36] );
      v37 = 2 * v36 + 2;
    }
    else
    {
      v14 = (const unsigned __int16 *)qword_18003ED50;
      v37 = 2;
    }
    v64 = (void *)v14;
    v65 = v37;
    v66 = 0;
    v62 = a3;
    v63 = 16;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 5;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_18004D070;
    UserData.Size = *(unsigned __int16 *)off_18004D070;
    UserData.Reserved = 2;
    v60 = (const wchar_t *)&unk_180045750;
    v61 = 0x100000048LL;
    v45 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
  }
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    v44 = v26;
    v60 = L"RpcSrvSBTransferOwnership: completed";
    v61 = 74;
    v62 = &v44;
    v63 = 4;
    McGenEventWrite_EventWriteTransfer(v16, NcbApiStatus, a3, 3, &UserData);
  }
  if ( v18 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v18);
  }
  if ( v19 )
    RpcRevertToSelf();
  if ( v20 )
    CloseHandle(v20);
  if ( v17 && _InterlockedExchangeAdd((volatile signed __int32 *)v17 + 6, 0xFFFFFFFF) == 1 )
  {
    SocketBrokerContext::CleanupSockets(v17);
    SocketBrokerContext::DeletePushEnableContext(v17);
    v39 = (void *)*((_QWORD *)v17 + 6);
    if ( v39 )
    {
      v40 = GetProcessHeap();
      HeapFree(v40, 0, v39);
    }
    *((_QWORD *)v17 + 6) = 0;
    v41 = (void *)*((_QWORD *)v17 + 7);
    if ( v41 )
      CloseHandle(v41);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v17 + 64));
    operator delete(v17);
  }
  if ( v26 > 0 )
    return (unsigned __int16)v26 | 0x80070000;
  else
    return (unsigned int)v26;
}

```

## disassembly

```asm
0x180019470  mov     r11, rsp
0x180019473  push    rbx
0x180019474  push    rsi
0x180019475  push    rdi
0x180019476  push    r12
0x180019478  push    r13
0x18001947a  push    r14
0x18001947c  push    r15
0x18001947e  sub     rsp, 1A0h
0x180019485  mov     rax, cs:__security_cookie
0x18001948c  xor     rax, rsp
0x18001948f  mov     [rsp+1D8h+var_48], rax
0x180019497  mov     rsi, r9
0x18001949a  mov     [rsp+1D8h+var_140], r8
0x1800194a2  mov     r14, rdx
0x1800194a5  mov     rax, [rsp+1D8h+arg_58]
0x1800194ad  mov     [rsp+1D8h+var_F0], rax
0x1800194b5  mov     rcx, [rsp+1D8h+arg_60]
0x1800194bd  mov     [rsp+1D8h+var_F8], rcx
0x1800194c5  mov     rax, [rsp+1D8h+arg_68]
0x1800194cd  mov     [rsp+1D8h+var_100], rax
0x1800194d5  xor     r9d, r9d; RelatedActivityId
0x1800194d8  mov     ebx, r9d
0x1800194db  mov     [r11-130h], rbx
0x1800194e2  mov     edi, r9d
0x1800194e5  mov     [r11-108h], r9
0x1800194ec  xor     r13b, r13b
0x1800194ef  mov     [rsp+1D8h+var_168], r13b
0x1800194f4  mov     r12d, r9d
0x1800194f7  mov     [r11-138h], r9
0x1800194fe  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180019505  lea     rdx, _TraceLoggingMetadataEnd; struct _GUID *
0x18001950c  lea     r10, _TraceLoggingMetadata
0x180019513  test    r8, r8
0x180019516  jz      loc_1800199EB
0x18001951c  test    rsi, rsi
0x18001951f  jz      loc_1800199EB
0x180019525  mov     rax, [rsp+1D8h+arg_48]
0x18001952d  dec     rax
0x180019530  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019534  ja      loc_1800199EB
0x18001953a  movzx   r13d, [rsp+1D8h+arg_40]
0x180019543  mov     eax, cs:dword_18004D068
0x180019549  mov     r12d, 0Ah
0x18001954f  cmp     eax, 5
0x180019552  jbe     loc_180019711
0x180019558  mov     eax, r9d
0x18001955b  test    rcx, rcx
0x18001955e  setnz   al
0x180019561  mov     [rsp+1D8h+var_128], eax
0x180019568  mov     ebx, r13d
0x18001956b  mov     [rsp+1D8h+var_124], ebx
0x180019572  mov     eax, [rsp+1D8h+arg_50]
0x180019579  mov     [rsp+1D8h+var_120], eax
0x180019580  mov     eax, [rsp+1D8h+arg_30]
0x180019587  mov     [rsp+1D8h+var_150], eax
0x18001958e  mov     eax, [rsp+1D8h+arg_28]
0x180019595  mov     [rsp+1D8h+var_148], eax
0x18001959c  mov     eax, [rsp+1D8h+arg_20]
0x1800195a3  mov     [rsp+1D8h+var_158], eax
0x1800195aa  lea     rax, [r11-128h]
0x1800195b1  mov     [r11-58h], rax
0x1800195b5  mov     qword ptr [r11-50h], 4
0x1800195bd  lea     rax, [r11-124h]
0x1800195c4  mov     [r11-68h], rax
0x1800195c8  mov     qword ptr [r11-60h], 4
0x1800195d0  lea     rax, [r11-120h]
0x1800195d7  mov     [r11-78h], rax
0x1800195db  mov     qword ptr [r11-70h], 4
0x1800195e3  lea     rax, [r11-150h]
0x1800195ea  mov     [r11-88h], rax
0x1800195f1  mov     qword ptr [r11-80h], 4
0x1800195f9  lea     rax, [r11-148h]
0x180019600  mov     [r11-98h], rax
0x180019607  mov     qword ptr [r11-90h], 4
0x180019612  lea     rax, [r11-158h]
0x180019619  mov     [r11-0A8h], rax
0x180019620  mov     qword ptr [r11-0A0h], 4
0x18001962b  mov     rax, r15
0x18001962e  xchg    ax, ax
0x180019630  lea     rax, [rax+1]
0x180019634  cmp     [rsi+rax*2], r9w
0x180019639  jnz     short loc_180019630
0x18001963b  mov     [rsp+1D8h+var_B8], rsi
0x180019643  lea     eax, ds:2[rax*2]
0x18001964a  mov     [rsp+1D8h+var_B0], eax
0x180019651  mov     [rsp+1D8h+var_AC], r9d
0x180019659  mov     [rsp+1D8h+var_C8], r8
0x180019661  mov     [rsp+1D8h+var_C0], 10h
0x18001966d  mov     dword ptr [rsp+1D8h+EventDescriptor.Id], 0B000000h
0x180019678  movzx   eax, cs:word_180045635
0x18001967f  mov     dword ptr [rsp+1D8h+EventDescriptor.Level], eax
0x180019686  mov     [rsp+1D8h+EventDescriptor.Keyword], r9
0x18001968e  mov     rax, cs:off_18004D070
0x180019695  mov     [rsp+1D8h+var_E8.Ptr], rax
0x18001969d  movzx   eax, word ptr [rax]
0x1800196a0  mov     [rsp+1D8h+var_E8.Size], eax
0x1800196a7  mov     dword ptr [rsp+1D8h+var_E8.0Ch], 2
0x1800196b2  lea     rax, byte_18004563F
0x1800196b9  mov     [rsp+1D8h+var_D8], rax
0x1800196c1  mov     dword ptr [rsp+1D8h+var_D0], 81h
0x1800196cc  mov     dword ptr [rsp+1D8h+var_D0+4], 1
0x1800196d7  mov     rax, rdx
0x1800196da  sub     eax, r10d
0x1800196dd  mov     [rsp+1D8h+var_160], eax
0x1800196e1  mov     eax, [rsp+1D8h+var_160]
0x1800196e5  lea     rax, [rsp+1D8h+var_E8]
0x1800196ed  mov     [rsp+1D8h+UserData], rax; UserData
0x1800196f2  mov     [rsp+1D8h+UserDataCount], r12d; UserDataCount
0x1800196f7  xor     r8d, r8d; ActivityId
0x1800196fa  lea     rdx, [rsp+1D8h+EventDescriptor]; EventDescriptor
0x180019702  mov     rcx, cs:RegHandle; RegHandle
0x180019709  call    cs:__imp_EventWriteTransfer
0x18001970f  jmp     short loc_180019714
0x180019711  mov     ebx, r13d
0x180019714  lea     rax, [rsp+1D8h+var_138]
0x18001971c  mov     [rsp+1D8h+UserData], rax; void **
0x180019721  lea     rax, [rsp+1D8h+var_130]
0x180019729  mov     qword ptr [rsp+1D8h+UserDataCount], rax; struct SocketBrokerContext **
0x18001972e  lea     r9, [rsp+1D8h+var_108]; unsigned __int16 **
0x180019736  lea     r8, [rsp+1D8h+var_168]; bool *
0x18001973b  mov     rcx, r14; unsigned __int16 *
0x18001973e  call    ?RpcHelperRetriveSbContext@@YAKPEBGPEAU_GUID@@PEA_NPEAPEAGPEAPEAVSocketBrokerContext@@PEAPEAX@Z; RpcHelperRetriveSbContext(ushort const *,_GUID *,bool *,ushort * *,SocketBrokerContext * *,void * *)
0x180019743  mov     r14d, eax
0x180019746  mov     eax, cs:Microsoft_Windows_Network_Connection_BrokerEnableBits
0x18001974c  mov     rdi, [rsp+1D8h+var_108]
0x180019754  test    al, 1
0x180019756  jz      loc_1800198A7
0x18001975c  mov     [rsp+1D8h+var_150], ebx
0x180019763  mov     eax, [rsp+1D8h+arg_30]
0x18001976a  mov     [rsp+1D8h+var_148], eax
0x180019771  mov     eax, [rsp+1D8h+arg_28]
0x180019778  mov     [rsp+1D8h+var_158], eax
0x18001977f  mov     eax, [rsp+1D8h+arg_20]
0x180019786  mov     [rsp+1D8h+var_160], eax
0x18001978a  mov     rax, [rsp+1D8h+var_140]
0x180019792  mov     [rsp+1D8h+var_D8], rax
0x18001979a  mov     [rsp+1D8h+var_D0], 10h
0x1800197a6  xor     ebx, ebx
0x1800197a8  mov     rax, r15
0x1800197ab  nop     dword ptr [rax+rax+00h]
0x1800197b0  lea     rax, [rax+1]
0x1800197b4  cmp     [rsi+rax*2], bx
0x1800197b8  jnz     short loc_1800197B0
0x1800197ba  lea     eax, ds:2[rax*2]
0x1800197c1  mov     [rsp+1D8h+var_C8], rsi
0x1800197c9  mov     dword ptr [rsp+1D8h+var_C0], eax
0x1800197d0  mov     dword ptr [rsp+1D8h+var_C0+4], ebx
0x1800197d7  test    rdi, rdi
0x1800197da  jz      short loc_1800197F7
0x1800197dc  mov     rax, r15
0x1800197df  nop
0x1800197e0  lea     rax, [rax+1]
0x1800197e4  cmp     [rdi+rax*2], bx
0x1800197e8  jnz     short loc_1800197E0
0x1800197ea  lea     r12d, ds:2[rax*2]
0x1800197f2  mov     rax, rdi
0x1800197f5  jmp     short loc_1800197FE
0x1800197f7  lea     rax, aNull_1; "NULL"
0x1800197fe  mov     [rsp+1D8h+var_B8], rax
0x180019806  mov     [rsp+1D8h+var_B0], r12d
0x18001980e  mov     [rsp+1D8h+var_AC], ebx
0x180019815  lea     rax, [rsp+1D8h+var_160]
0x18001981a  mov     [rsp+1D8h+var_A8], rax
0x180019822  mov     [rsp+1D8h+var_A0], 4
0x18001982e  lea     rax, [rsp+1D8h+var_158]
0x180019836  mov     [rsp+1D8h+var_98], rax
0x18001983e  mov     [rsp+1D8h+var_90], 4
0x18001984a  lea     rax, [rsp+1D8h+var_148]
0x180019852  mov     [rsp+1D8h+var_88], rax
0x18001985a  mov     [rsp+1D8h+var_80], 4
0x180019866  lea     rax, [rsp+1D8h+var_150]
0x18001986e  mov     [rsp+1D8h+var_78], rax
0x180019876  mov     [rsp+1D8h+var_70], 4
0x180019882  lea     rax, [rsp+1D8h+var_E8]
0x18001988a  mov     qword ptr [rsp+1D8h+UserDataCount], rax
0x18001988f  mov     r9d, 8
0x180019895  lea     rdx, SbTransferOwnership
0x18001989c  call    McGenEventWrite_EventWriteTransfer
0x1800198a1  mov     eax, cs:Microsoft_Windows_Network_Connection_BrokerEnableBits
0x1800198a7  test    r14d, r14d
0x1800198aa  jz      short loc_180019923
0x1800198ac  test    al, 1
0x1800198ae  jz      short loc_180019908
0x1800198b0  mov     [rsp+1D8h+var_160], r14d
0x1800198b5  lea     rax, aRpcsrvsbtransf_2; "RpcSrvSBTransferOwnership: RpcHelperRet"...
0x1800198bc  mov     [rsp+1D8h+var_D8], rax
0x1800198c4  mov     [rsp+1D8h+var_D0], 78h ; 'x'
0x1800198d0  lea     rax, [rsp+1D8h+var_160]
0x1800198d5  mov     [rsp+1D8h+var_C8], rax
0x1800198dd  mov     [rsp+1D8h+var_C0], 4
0x1800198e9  lea     rax, [rsp+1D8h+var_E8]
0x1800198f1  mov     qword ptr [rsp+1D8h+UserDataCount], rax
0x1800198f6  mov     r9d, 3
0x1800198fc  lea     rdx, NcbApiStatus
0x180019903  call    McGenEventWrite_EventWriteTransfer
0x180019908  mov     rbx, [rsp+1D8h+var_130]
0x180019910  movzx   r13d, [rsp+1D8h+var_168]
0x180019916  mov     r12, [rsp+1D8h+var_138]
0x18001991e  jmp     loc_180019A52
0x180019923  test    r13b, r13b
0x180019926  setnz   bl
0x180019929  movzx   r13d, [rsp+1D8h+var_168]
0x18001992f  test    r13b, r13b
0x180019932  jz      short loc_18001993D
0x180019934  call    cs:__imp_RpcRevertToSelf
0x18001993a  xor     r13b, r13b
0x18001993d  mov     rax, [rsp+1D8h+var_100]
0x180019945  mov     [rsp+1D8h+var_178], rax; struct _DNS_REGISTRATION_DATA *
0x18001994a  mov     rax, [rsp+1D8h+var_F8]
0x180019952  mov     [rsp+1D8h+var_180], rax; struct _SOCKET_BROKER_SSL_CONTEXT *
0x180019957  mov     rax, [rsp+1D8h+var_F0]
0x18001995f  mov     [rsp+1D8h+var_188], rax; struct _SOCKET_BROKER_APP_CONTEXT *
0x180019964  mov     eax, [rsp+1D8h+arg_50]
0x18001996b  mov     [rsp+1D8h+var_190], eax; unsigned int
0x18001996f  mov     r12, [rsp+1D8h+var_138]
0x180019977  mov     [rsp+1D8h+ProcessHandle], r12; ProcessHandle
0x18001997c  mov     rax, [rsp+1D8h+arg_48]
0x180019984  mov     [rsp+1D8h+var_1A0], rax; unsigned __int64
0x180019989  mov     [rsp+1D8h+var_1A8], bl; bool
0x18001998d  mov     eax, [rsp+1D8h+arg_38]
0x180019994  mov     dword ptr [rsp+1D8h+UserData], eax; unsigned int
0x180019998  mov     eax, [rsp+1D8h+arg_30]
0x18001999f  mov     [rsp+1D8h+UserDataCount], eax; int
0x1800199a3  mov     r9d, [rsp+1D8h+arg_28]; int
0x1800199ab  mov     r8d, [rsp+1D8h+arg_20]; int
0x1800199b3  mov     rdx, rsi; unsigned __int16 *
0x1800199b6  mov     rbx, [rsp+1D8h+var_130]
0x1800199be  mov     rcx, rbx; this
0x1800199c1  call    ?TransferOwnership@SocketBrokerContext@@QEAAKPEBGHHHK_N_KPEAXKPEAU_SOCKET_BROKER_APP_CONTEXT@@PEAU_SOCKET_BROKER_SSL_CONTEXT@@PEAU_DNS_REGISTRATION_DATA@@@Z; SocketBrokerContext::TransferOwnership(ushort const *,int,int,int,ulong,bool,unsigned __int64,void *,ulong,_SOCKET_BROKER_APP_CONTEXT *,_SOCKET_BROKER_SSL_CONTEXT *,_DNS_REGISTRATION_DATA *)
0x1800199c6  mov     r14d, eax
0x1800199c9  test    eax, eax
0x1800199cb  jz      loc_180019A52
0x1800199d1  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800199d8  jz      short loc_180019A52
0x1800199da  mov     r9d, eax
0x1800199dd  lea     r8, aRpcsrvsbtransf_1; "RpcSrvSBTransferOwnership: TransferOwne"...
0x1800199e4  call    McTemplateU0zq_EventWriteTransfer
0x1800199e9  jmp     short loc_180019A52
0x1800199eb  mov     r14d, 57h ; 'W'
0x1800199f1  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800199f8  jz      short loc_180019A6B
0x1800199fa  mov     [rsp+1D8h+var_160], r14d
0x1800199ff  lea     rax, aRpcsrvsbtransf_3; "RpcSrvSBTransferOwnership: invalid para"...
0x180019a06  mov     [rsp+1D8h+var_D8], rax
0x180019a0e  mov     [rsp+1D8h+var_D0], 5Ah ; 'Z'
0x180019a1a  lea     rax, [rsp+1D8h+var_160]
0x180019a1f  mov     [rsp+1D8h+var_C8], rax
0x180019a27  mov     [rsp+1D8h+var_C0], 4
0x180019a33  lea     rax, [rsp+1D8h+var_E8]
0x180019a3b  mov     qword ptr [rsp+1D8h+UserDataCount], rax
0x180019a40  mov     r9d, 3
0x180019a46  lea     rdx, NcbApiStatus
0x180019a4d  call    McGenEventWrite_EventWriteTransfer
0x180019a52  lea     r10, _TraceLoggingMetadata
0x180019a59  xor     r9d, r9d
0x180019a5c  lea     rdx, _TraceLoggingMetadataEnd
0x180019a63  mov     r8, [rsp+1D8h+var_140]
0x180019a6b  mov     eax, cs:dword_18004D068
0x180019a71  cmp     eax, 5
0x180019a74  jbe     loc_180019BD8
0x180019a7a  mov     [rsp+1D8h+var_160], r14d
0x180019a7f  lea     rax, [rsp+1D8h+var_160]
0x180019a84  mov     [rsp+1D8h+var_98], rax
0x180019a8c  mov     [rsp+1D8h+var_90], 4
0x180019a98  test    rdi, rdi
0x180019a9b  jz      short loc_180019AB7
0x180019a9d  mov     rcx, rdi
0x180019aa0  mov     rax, r15
0x180019aa3  lea     rax, [rax+1]
0x180019aa7  cmp     word ptr [rdi+rax*2], 0
0x180019aac  jnz     short loc_180019AA3
0x180019aae  lea     eax, ds:2[rax*2]
0x180019ab5  jmp     short loc_180019AC3
0x180019ab7  lea     rcx, qword_18003ED50
0x180019abe  mov     eax, 2
0x180019ac3  mov     [rsp+1D8h+var_A8], rcx
0x180019acb  mov     dword ptr [rsp+1D8h+var_A0], eax
0x180019ad2  mov     dword ptr [rsp+1D8h+var_A0+4], r9d
0x180019ada  test    rsi, rsi
0x180019add  jz      short loc_180019AF6
0x180019adf  mov     rax, r15
0x180019ae2  lea     rax, [rax+1]
0x180019ae6  cmp     word ptr [rsi+rax*2], 0
0x180019aeb  jnz     short loc_180019AE2
0x180019aed  lea     eax, ds:2[rax*2]
0x180019af4  jmp     short loc_180019B02
0x180019af6  lea     rsi, qword_18003ED50
0x180019afd  mov     eax, 2
0x180019b02  mov     [rsp+1D8h+var_B8], rsi
0x180019b0a  mov     [rsp+1D8h+var_B0], eax
0x180019b11  mov     [rsp+1D8h+var_AC], r9d
0x180019b19  mov     [rsp+1D8h+var_C8], r8
0x180019b21  mov     [rsp+1D8h+var_C0], 10h
0x180019b2d  mov     dword ptr [rsp+1D8h+EventDescriptor.Id], 0B000000h
0x180019b38  movzx   eax, cs:word_180045746
0x180019b3f  mov     dword ptr [rsp+1D8h+EventDescriptor.Level], eax
0x180019b46  mov     [rsp+1D8h+EventDescriptor.Keyword], r9
0x180019b4e  mov     rax, cs:off_18004D070
0x180019b55  mov     [rsp+1D8h+var_E8.Ptr], rax
  ... truncated ...
```
