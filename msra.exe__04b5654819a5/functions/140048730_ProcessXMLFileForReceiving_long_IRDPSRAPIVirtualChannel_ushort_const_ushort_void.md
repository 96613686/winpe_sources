# ProcessXMLFileForReceiving(long,IRDPSRAPIVirtualChannel *,ushort const *,ushort *,void *)

- ea: `0x140048730`
- end: `0x140048d0f`
- name: `?ProcessXMLFileForReceiving@@YAJJPEAUIRDPSRAPIVirtualChannel@@PEBGPEAGPEAX@Z`
- size: `1503`
- prototype: `__int64 __fastcall(CEventLogger *, struct IRDPSRAPIVirtualChannel *, const unsigned __int16 *, unsigned __int16 *, CRATicket *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140008088`
- `0x140034ce4`
- `0x14003b330`
- `0x14003be60`
- `0x140045150`
- `0x140045f80`
- `0x140046600`
- `0x140048730`
- `0x140049190`
- `0x1400497dc`
- `0x140049880`
- `0x140049a9c`
- `0x14004a190`
- `0x14004d010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140048c85`
- `KERNEL32!HeapFree` at `0x140048caa`
- `KERNEL32!HeapFree` at `0x140048c85`
- `KERNEL32!HeapFree` at `0x140048caa`
- `KERNEL32!GetProcessHeap` at `0x140048c71`
- `KERNEL32!GetProcessHeap` at `0x140048c96`
- `KERNEL32!GetProcessHeap` at `0x140048c71`
- `KERNEL32!GetProcessHeap` at `0x140048c96`
- `msvcrt!malloc` at `0x140048a97`
- `msvcrt!malloc` at `0x140048b3a`
- `msvcrt!malloc` at `0x140048a97`
- `msvcrt!malloc` at `0x140048b3a`
- `msvcrt!free` at `0x140048b72`
- `msvcrt!free` at `0x140048b81`
- `msvcrt!free` at `0x140048b72`
- `msvcrt!free` at `0x140048b81`
- `msvcrt!calloc` at `0x140048c0d`
- `msvcrt!calloc` at `0x140048c0d`

## string_xrefs

- `0x140048796`: `ProcessXMLFileForReceiving`

## pseudocode

```c
__int64 __fastcall ProcessXMLFileForReceiving(
        CEventLogger *a1,
        struct IRDPSRAPIVirtualChannel *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        CRATicket *a5)
{
  unsigned int v6; // esi
  unsigned int v7; // r14d
  struct RECV_ENTRY *v8; // rdi
  unsigned int v9; // r9d
  unsigned __int16 *v10; // r13
  unsigned __int16 *v11; // r15
  signed int XMLControlBlock; // eax
  CEventLogger *v13; // rcx
  _QWORD *v14; // r14
  int v15; // ebx
  RAXferWorker *FileXferInstByFileVCName; // rax
  volatile __int32 *v17; // r12
  struct IRDPSRAPIVirtualChannel *VCByName; // r15
  int v19; // edi
  __int64 v20; // rax
  ReceivingFileContext *v21; // rcx
  struct IRDPSRAPIVirtualChannel *v22; // r8
  int RecvFileEntry; // eax
  __int64 v24; // r8
  struct RECV_ENTRY *v25; // r14
  struct IRDPSRAPIVirtualChannel *v26; // rbx
  char v27; // si
  struct IRDPSRAPIVirtualChannel *v28; // rax
  CRATicket *v29; // rdi
  _QWORD *i; // rax
  __int64 v31; // rcx
  bool v32; // sf
  int v33; // eax
  _QWORD *v34; // rbx
  void *v35; // r11
  __int64 v36; // rcx
  unsigned __int16 *v37; // rax
  __int64 v38; // rdx
  unsigned __int64 v39; // rdi
  unsigned __int16 *v40; // rax
  int v41; // eax
  struct IRDPSRAPIVirtualChannel *v42; // rbx
  __int64 v43; // r8
  _QWORD *v44; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v46; // rax
  unsigned int v48; // [rsp+38h] [rbp-81h]
  unsigned __int16 *v49; // [rsp+40h] [rbp-79h]
  int v50; // [rsp+48h] [rbp-71h]
  int v51; // [rsp+4Ch] [rbp-6Dh]
  struct IRDPSRAPIVirtualChannel *v52; // [rsp+50h] [rbp-69h] BYREF
  struct RECV_ENTRY *v53; // [rsp+58h] [rbp-61h] BYREF
  unsigned __int16 *v54[2]; // [rsp+60h] [rbp-59h] BYREF
  LPVOID lpMem[2]; // [rsp+70h] [rbp-49h]
  _OWORD v56[2]; // [rsp+80h] [rbp-39h] BYREF
  __int128 v57; // [rsp+A0h] [rbp-19h]
  __int128 v58; // [rsp+B0h] [rbp-9h]
  int v59; // [rsp+118h] [rbp+5Fh]

  v59 = (int)a1;
  v6 = (unsigned int)a1;
  DWORD1(v56[0]) = 0;
  DWORD1(v58) = 0;
  v7 = 1;
  *(_OWORD *)v54 = 0;
  *(_OWORD *)lpMem = 0;
  v8 = 0;
  v53 = 0;
  v52 = 0;
  if ( !a5 )
  {
    v9 = 1145;
LABEL_3:
    CEventLogger::LogError(
      a1,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\rarecv.cpp",
      v9,
      L"ProcessXMLFileForReceiving",
      0x80004003);
LABEL_4:
    v10 = (unsigned __int16 *)lpMem[0];
    v11 = v54[0];
    goto LABEL_87;
  }
  if ( !a2 )
  {
    v9 = 1146;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v9 = 1147;
    goto LABEL_3;
  }
  XMLControlBlock = ReadXMLControlBlock(v54, a4);
  v7 = XMLControlBlock;
  v48 = XMLControlBlock;
  if ( XMLControlBlock < 0 )
  {
    CEventLogger::LogError(
      v13,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\rarecv.cpp",
      0x489u,
      L"ProcessXMLFileForReceiving",
      XMLControlBlock);
    goto LABEL_4;
  }
  v14 = 0;
  v50 = 0;
  v51 = 0;
  LODWORD(v56[0]) = v6;
  *((_QWORD *)&v56[0] + 1) = a2;
  v56[1] = 0;
  LODWORD(v57) = 12;
  DWORD1(v57) = v54[1];
  v11 = v54[0];
  v49 = v54[0];
  *((unsigned __int16 **)&v57 + 1) = v54[0];
  v15 = (int)lpMem[1];
  LODWORD(v58) = lpMem[1];
  v10 = (unsigned __int16 *)lpMem[0];
  FileXferInstByFileVCName = CRATicket::GetFileXferInstByFileVCName(a5, (const unsigned __int16 *)lpMem[0]);
  v17 = (volatile __int32 *)FileXferInstByFileVCName;
  if ( FileXferInstByFileVCName )
  {
    VCByName = RAXferWorker::GetVCByName(FileXferInstByFileVCName, v10);
    if ( !VCByName )
    {
LABEL_77:
      v42 = RAXferWorker::GetVCByName((RAXferWorker *)v17, v10);
      if ( v42 )
      {
        if ( v14 )
        {
          v44 = calloc(1u, 0x58u);
          if ( v44 )
          {
            *(_DWORD *)v44 = 1;
            v44[1] = v42;
            *((_DWORD *)v44 + 4) = v6;
            *((_DWORD *)v44 + 5) = 0;
            RAXferWorker::InsertToCommandToSendList((RAXferWorker *)v17, (struct COMMAND_TO_SEND *)v44);
          }
        }
      }
      goto LABEL_81;
    }
    v19 = 0;
    goto LABEL_19;
  }
  if ( (int)CRATicket::CreateVCByName(a5, v10, &v52) >= 0 && v52 )
  {
    VCByName = 0;
    v19 = 1;
    v50 = 1;
    v20 = *((_QWORD *)a5 + 58);
    if ( v20 && *(_QWORD *)(v20 + 536) )
      ChannelInfoList::Append(*(ChannelInfoList **)(v20 + 536), v10, v52);
LABEL_19:
    v21 = (ReceivingFileContext *)*((_QWORD *)a5 + 64);
    if ( !v21 )
    {
      v7 = -2147418113;
      v11 = v49;
      goto LABEL_87;
    }
    v22 = v52;
    if ( !v19 )
      v22 = VCByName;
    RecvFileEntry = ReceivingFileContext::GetRecvFileEntry(v21, v6, v22, 1, &v53);
    v25 = v53;
    if ( RecvFileEntry >= 0 || v53 )
    {
      ResetReceiverEntry(v53);
      *(_DWORD *)v25 = v6;
      *((_DWORD *)v25 + 12) = v15;
      if ( v19 )
      {
        v26 = v52;
        if ( v52 )
          ((void (__fastcall *)(struct IRDPSRAPIVirtualChannel *))v52->lpVtbl->AddRef)(v52);
        v27 = 1;
        v28 = v26;
        v29 = a5;
      }
      else
      {
        v29 = (CRATicket *)VCByName;
        if ( VCByName )
          ((void (__fastcall *)(struct IRDPSRAPIVirtualChannel *))VCByName->lpVtbl->AddRef)(VCByName);
        v27 = 2;
        v28 = VCByName;
        v26 = (struct IRDPSRAPIVirtualChannel *)a5;
      }
      *((_QWORD *)v25 + 1) = v28;
      if ( (v27 & 2) != 0 )
      {
        v27 &= ~2u;
        if ( v29 )
          (*(void (__fastcall **)(CRATicket *))(*(_QWORD *)v29 + 16LL))(v29);
      }
      if ( (v27 & 1) != 0 && v26 )
        ((void (__fastcall *)(struct IRDPSRAPIVirtualChannel *))v26->lpVtbl->Release)(v26);
      v19 = v50;
      v6 = v59;
    }
    v14 = (_QWORD *)*((_QWORD *)a5 + 60);
    if ( !v14 )
      goto LABEL_72;
    for ( i = (_QWORD *)*v14; i != v14; i = (_QWORD *)*i )
    {
      v31 = i[2];
      if ( v31 && (*(_DWORD *)(v31 + 16) == -100 || v6 == *(_DWORD *)(v31 + 16)) )
        *(_DWORD *)(v31 + 32) = 1;
    }
    if ( (unsigned int)FileReceiveAgent::ReturnFileToReceivers(v14, v6, v24, v56, 12) )
      goto LABEL_72;
    v51 = 1;
    if ( v19 )
    {
      v32 = SendStringOverVC(v52, L"FILEXFERACK", v6, 0) < 0;
      goto LABEL_50;
    }
    if ( _InterlockedCompareExchange(v17 + 136, 0, 1) == 1 )
    {
      v33 = SendStringOverVC(VCByName, L"FILEXFERACK", v6, 0);
      _InterlockedExchange(v17 + 136, 1);
      v32 = v33 < 0;
LABEL_50:
      v11 = v49;
      if ( !v32 )
        goto LABEL_86;
LABEL_70:
      v8 = v53;
      if ( v17 )
        goto LABEL_74;
      goto LABEL_73;
    }
    if ( !VCByName )
    {
LABEL_72:
      v11 = v49;
      goto LABEL_70;
    }
    v34 = malloc(0x58u);
    if ( !v34 )
    {
      v11 = v49;
      goto LABEL_70;
    }
    *(_DWORD *)v34 = 0;
    v34[1] = VCByName;
    *((_DWORD *)v34 + 4) = v6;
    *((_DWORD *)v34 + 5) = 0;
    v34[3] = v14;
    *((_OWORD *)v34 + 2) = v56[0];
    *((_OWORD *)v34 + 3) = 0;
    *((_OWORD *)v34 + 4) = v57;
    v34[10] = v58;
    v11 = v49;
    if ( !v49 )
    {
      v35 = 0;
LABEL_64:
      v34[9] = v35;
      v41 = RAXferWorker::InsertToCommandToSendList((RAXferWorker *)v17, (struct COMMAND_TO_SEND *)v34);
      if ( v41 >= 0 )
        goto LABEL_86;
      goto LABEL_70;
    }
    v36 = 260;
    v37 = v49;
    do
    {
      if ( !*v37 )
        break;
      ++v37;
      --v36;
    }
    while ( v36 );
    v38 = (260 - v36) & ((unsigned __int128)-(__int128)(unsigned __int64)v36 >> 64);
    if ( v36 )
    {
      v39 = v38 + 1;
      v40 = (unsigned __int16 *)malloc(2 * (v38 + 1));
      if ( v40 )
      {
        if ( (int)StringCchCopyW(v40, v39, v49) >= 0 )
          goto LABEL_64;
        free(v35);
      }
    }
    free(v34);
    goto LABEL_70;
  }
LABEL_73:
  v17 = (volatile __int32 *)CRATicket::GetFileXferInstByFileVCName(a5, v10);
LABEL_74:
  if ( v50 )
  {
    v6 = v59;
    SendStringOverVC(v52, L"FILEXFERREJECT", v59, 0);
LABEL_81:
    if ( v8 )
    {
      *((_DWORD *)v8 + 8) = 8;
      if ( v14 )
      {
        if ( v51 )
          FileReceiveAgent::ReturnFileToReceivers(v14, v6, v43, v8, 8);
      }
    }
    v11 = v49;
    goto LABEL_86;
  }
  if ( v17 )
  {
    v6 = v59;
    goto LABEL_77;
  }
LABEL_86:
  v7 = v48;
LABEL_87:
  if ( v10 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v10);
  }
  if ( v11 )
  {
    v46 = GetProcessHeap();
    HeapFree(v46, 0, v11);
  }
  if ( v52 )
    ((void (__fastcall *)(struct IRDPSRAPIVirtualChannel *))v52->lpVtbl->Release)(v52);
  return v7;
}

```

## disassembly

```asm
0x140048730  mov     rax, rsp
0x140048733  mov     [rax+8], ecx
0x140048736  push    rbp
0x140048737  push    rbx
0x140048738  push    rsi
0x140048739  push    rdi
0x14004873a  push    r12
0x14004873c  push    r13
0x14004873e  push    r14
0x140048740  push    r15
0x140048742  lea     rbp, [rax-57h]
0x140048746  sub     rsp, 0C8h
0x14004874d  movaps  xmmword ptr [rax-58h], xmm6
0x140048751  mov     rbx, rdx
0x140048754  mov     esi, ecx
0x140048756  xor     r15d, r15d
0x140048759  mov     [rbp+4Fh+var_BC], r15d
0x14004875d  mov     dword ptr [rbp+4Fh+var_88+4], r15d
0x140048761  mov     dword ptr [rbp+4Fh+var_58+4], r15d
0x140048765  lea     r14d, [r15+1]
0x140048769  xorps   xmm0, xmm0
0x14004876c  movups  xmmword ptr [rbp+4Fh+var_A8], xmm0
0x140048770  movups  xmmword ptr [rbp+4Fh+lpMem], xmm0
0x140048774  mov     edi, r15d
0x140048777  mov     [rbp+4Fh+var_B0], r15
0x14004877b  mov     [rbp+4Fh+var_B8], r15
0x14004877f  mov     r12, [rbp+4Fh+arg_20]
0x140048783  test    r12, r12
0x140048786  jnz     short loc_1400487C2
0x140048788  mov     r9d, 479h; unsigned int
0x14004878e  mov     [rsp+100h+var_D8], 80004003h; unsigned int
0x140048796  lea     rax, aProcessxmlfile; "ProcessXMLFileForReceiving"
0x14004879d  mov     [rsp+100h+var_E0], rax; unsigned __int16 *
0x1400487a2  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\core\\lib\\rarecv."...
0x1400487a9  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400487b0  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400487b5  mov     r13, [rbp+4Fh+lpMem]
0x1400487b9  mov     r15, [rbp+4Fh+var_A8]
0x1400487bd  jmp     loc_140048C6C
0x1400487c2  test    rbx, rbx
0x1400487c5  jnz     short loc_1400487CF
0x1400487c7  mov     r9d, 47Ah
0x1400487cd  jmp     short loc_14004878E
0x1400487cf  test    r9, r9
0x1400487d2  jnz     short loc_1400487DC
0x1400487d4  mov     r9d, 47Bh
0x1400487da  jmp     short loc_14004878E
0x1400487dc  mov     rdx, r9; unsigned __int16 *
0x1400487df  lea     rcx, [rbp+4Fh+var_A8]; unsigned __int16 **
0x1400487e3  call    ?ReadXMLControlBlock@@YAJPEAUFILE_ATTRIBUTES@@PEAG@Z; ReadXMLControlBlock(FILE_ATTRIBUTES *,ushort *)
0x1400487e8  mov     r14d, eax
0x1400487eb  mov     [rsp+30h], eax
0x1400487ef  test    eax, eax
0x1400487f1  jns     short loc_1400487FF
0x1400487f3  mov     [rsp+100h+var_D8], eax
0x1400487f7  mov     r9d, 489h
0x1400487fd  jmp     short loc_140048796
0x1400487ff  mov     r14, r15
0x140048802  mov     [rbp+4Fh+var_C0], r15d
0x140048806  mov     [rbp+4Fh+var_BC], r15d
0x14004880a  mov     dword ptr [rbp+4Fh+var_88], esi
0x14004880d  mov     qword ptr [rbp+4Fh+var_88+8], rbx
0x140048811  xorps   xmm6, xmm6
0x140048814  movdqu  [rbp+4Fh+var_78], xmm6
0x140048819  mov     dword ptr [rbp+4Fh+var_68], 0Ch
0x140048820  mov     eax, dword ptr [rbp+4Fh+var_A8+8]
0x140048823  mov     dword ptr [rbp+4Fh+var_68+4], eax
0x140048826  mov     r15, [rbp+4Fh+var_A8]
0x14004882a  mov     [rbp+4Fh+var_C8], r15
0x14004882e  mov     qword ptr [rbp+4Fh+var_68+8], r15
0x140048832  mov     ebx, dword ptr [rbp+4Fh+lpMem+8]
0x140048835  mov     dword ptr [rbp+4Fh+var_58], ebx
0x140048838  mov     r13, [rbp+4Fh+lpMem]
0x14004883c  mov     rdx, r13; unsigned __int16 *
0x14004883f  mov     rcx, r12; this
0x140048842  call    ?GetFileXferInstByFileVCName@CRATicket@@AEAAPEAVRAXferWorker@@PEBG@Z; CRATicket::GetFileXferInstByFileVCName(ushort const *)
0x140048847  mov     r12, rax
0x14004884a  mov     rdx, r13; unsigned __int16 *
0x14004884d  test    rax, rax
0x140048850  jnz     short loc_1400488B3
0x140048852  lea     r8, [rbp+4Fh+var_B8]; struct IRDPSRAPIVirtualChannel **
0x140048856  mov     rcx, [rbp+4Fh+arg_20]; this
0x14004885a  call    ?CreateVCByName@CRATicket@@AEAAJPEBGPEAPEAUIRDPSRAPIVirtualChannel@@@Z; CRATicket::CreateVCByName(ushort const *,IRDPSRAPIVirtualChannel * *)
0x14004885f  test    eax, eax
0x140048861  js      loc_140048BC9
0x140048867  mov     rcx, [rbp+4Fh+var_B8]
0x14004886b  test    rcx, rcx
0x14004886e  setz    al
0x140048871  test    al, al
0x140048873  jnz     loc_140048BC9
0x140048879  xor     r14d, r14d
0x14004887c  mov     r15d, r14d
0x14004887f  lea     edi, [r12+1]
0x140048884  mov     [rbp+4Fh+var_C0], edi
0x140048887  mov     rax, [rbp+4Fh+arg_20]
0x14004888b  mov     rax, [rax+1D0h]
0x140048892  test    rax, rax
0x140048895  jz      short loc_1400488CA
0x140048897  mov     r9, [rax+218h]
0x14004889e  test    r9, r9
0x1400488a1  jz      short loc_1400488CA
0x1400488a3  mov     r8, rcx; struct IRDPSRAPIVirtualChannel *
0x1400488a6  mov     rdx, r13; unsigned __int16 *
0x1400488a9  mov     rcx, r9; this
0x1400488ac  call    ?Append@ChannelInfoList@@QEAAJPEBGPEAUIRDPSRAPIVirtualChannel@@@Z; ChannelInfoList::Append(ushort const *,IRDPSRAPIVirtualChannel *)
0x1400488b1  jmp     short loc_1400488CA
0x1400488b3  mov     rcx, r12; this
0x1400488b6  call    ?GetVCByName@RAXferWorker@@QEAAPEAUIRDPSRAPIVirtualChannel@@PEBG@Z; RAXferWorker::GetVCByName(ushort const *)
0x1400488bb  mov     r15, rax
0x1400488be  test    rax, rax
0x1400488c1  jz      loc_140048BEB
0x1400488c7  mov     edi, r14d
0x1400488ca  mov     rax, [rbp+4Fh+arg_20]
0x1400488ce  mov     rcx, [rax+200h]; this
0x1400488d5  test    rcx, rcx
0x1400488d8  jnz     short loc_1400488E9
0x1400488da  mov     r14d, 8000FFFFh
0x1400488e0  mov     r15, [rbp+4Fh+var_C8]
0x1400488e4  jmp     loc_140048C6C
0x1400488e9  lea     rax, [rbp+4Fh+var_B0]
0x1400488ed  mov     r9d, 1; int
0x1400488f3  mov     edx, esi; int
0x1400488f5  mov     [rsp+100h+var_E0], rax; struct RECV_ENTRY **
0x1400488fa  test    edi, edi
0x1400488fc  mov     r8, [rbp+4Fh+var_B8]
0x140048900  jnz     short loc_140048905
0x140048902  mov     r8, r15; struct IRDPSRAPIVirtualChannel *
0x140048905  call    ?GetRecvFileEntry@ReceivingFileContext@@QEAAJJPEAUIRDPSRAPIVirtualChannel@@HPEAPEAURECV_ENTRY@@@Z; ReceivingFileContext::GetRecvFileEntry(long,IRDPSRAPIVirtualChannel *,int,RECV_ENTRY * *)
0x14004890a  mov     r14, [rbp+4Fh+var_B0]
0x14004890e  mov     [rbp+4Fh+var_B0], r14
0x140048912  test    eax, eax
0x140048914  jns     short loc_14004891F
0x140048916  test    r14, r14
0x140048919  jz      loc_1400489C0
0x14004891f  mov     rcx, r14; struct RECV_ENTRY *
0x140048922  call    ?ResetReceiverEntry@@YAJPEAURECV_ENTRY@@@Z; ResetReceiverEntry(RECV_ENTRY *)
0x140048927  mov     [r14], esi
0x14004892a  mov     [r14+30h], ebx
0x14004892e  test    edi, edi
0x140048930  jz      short loc_140048959
0x140048932  mov     rbx, [rbp+4Fh+var_B8]
0x140048936  test    rbx, rbx
0x140048939  jz      short loc_14004894B
0x14004893b  mov     rax, [rbx]
0x14004893e  mov     rcx, rbx
0x140048941  mov     rax, [rax+8]
0x140048945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004894a  nop
0x14004894b  mov     esi, 1
0x140048950  mov     rax, rbx
0x140048953  mov     rdi, [rbp+4Fh+arg_20]
0x140048957  jmp     short loc_14004897D
0x140048959  mov     rdi, r15
0x14004895c  test    r15, r15
0x14004895f  jz      short loc_140048971
0x140048961  mov     rax, [r15]
0x140048964  mov     rcx, r15
0x140048967  mov     rax, [rax+8]
0x14004896b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048970  nop
0x140048971  mov     esi, 2
0x140048976  mov     rax, r15
0x140048979  mov     rbx, [rbp+4Fh+arg_20]
0x14004897d  mov     [r14+8], rax
0x140048981  test    sil, 2
0x140048985  jz      short loc_14004899F
0x140048987  and     esi, 0FFFFFFFDh
0x14004898a  test    rdi, rdi
0x14004898d  jz      short loc_14004899F
0x14004898f  mov     rax, [rdi]
0x140048992  mov     rcx, rdi
0x140048995  mov     rax, [rax+10h]
0x140048999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004899e  nop
0x14004899f  test    sil, 1
0x1400489a3  jz      short loc_1400489BA
0x1400489a5  test    rbx, rbx
0x1400489a8  jz      short loc_1400489BA
0x1400489aa  mov     rax, [rbx]
0x1400489ad  mov     rcx, rbx
0x1400489b0  mov     rax, [rax+10h]
0x1400489b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400489b9  nop
0x1400489ba  mov     edi, [rbp+4Fh+var_C0]
0x1400489bd  mov     esi, [rbp+4Fh+arg_0]
0x1400489c0  mov     rax, [rbp+4Fh+arg_20]
0x1400489c4  mov     r14, [rax+1E0h]
0x1400489cb  xor     ebx, ebx
0x1400489cd  test    r14, r14
0x1400489d0  jz      loc_140048BC3
0x1400489d6  mov     rax, [r14]
0x1400489d9  jmp     short loc_1400489F9
0x1400489db  mov     rcx, [rax+10h]
0x1400489df  test    rcx, rcx
0x1400489e2  jz      short loc_1400489F6
0x1400489e4  cmp     dword ptr [rcx+10h], 0FFFFFF9Ch
0x1400489e8  jz      short loc_1400489EF
0x1400489ea  cmp     esi, [rcx+10h]
0x1400489ed  jnz     short loc_1400489F6
0x1400489ef  mov     dword ptr [rcx+20h], 1
0x1400489f6  mov     rax, [rax]
0x1400489f9  cmp     rax, r14
0x1400489fc  jnz     short loc_1400489DB
0x1400489fe  mov     dword ptr [rsp+100h+var_E0], 0Ch
0x140048a06  lea     r9, [rbp+4Fh+var_88]
0x140048a0a  mov     edx, esi
0x140048a0c  mov     rcx, r14
0x140048a0f  call    ?ReturnFileToReceivers@FileReceiveAgent@@QEAAJJPEAUIRDPSRAPIVirtualChannel@@PEAURECV_ENTRY@@W4RAFX_STATUS@@@Z; FileReceiveAgent::ReturnFileToReceivers(long,IRDPSRAPIVirtualChannel *,RECV_ENTRY *,RAFX_STATUS)
0x140048a14  test    eax, eax
0x140048a16  jnz     loc_140048BC3
0x140048a1c  mov     [rbp+4Fh+var_BC], 1
0x140048a23  test    edi, edi
0x140048a25  jz      short loc_140048A4E
0x140048a27  xor     r9d, r9d; unsigned int
0x140048a2a  mov     r8d, esi; int
0x140048a2d  lea     rdx, aFilexferack; "FILEXFERACK"
0x140048a34  mov     rcx, [rbp+4Fh+var_B8]; struct IRDPSRAPIVirtualChannel *
0x140048a38  call    ?SendStringOverVC@@YAJPEAUIRDPSRAPIVirtualChannel@@PEBGJK@Z; SendStringOverVC(IRDPSRAPIVirtualChannel *,ushort const *,long,ulong)
0x140048a3d  test    eax, eax
0x140048a3f  mov     r15, [rbp+4Fh+var_C8]
0x140048a43  js      loc_140048BB8
0x140048a49  jmp     loc_140048C67
0x140048a4e  mov     ecx, ebx
0x140048a50  mov     eax, 1
0x140048a55  lock cmpxchg [r12+220h], ecx
0x140048a5f  jnz     short loc_140048A89
0x140048a61  xor     r9d, r9d; unsigned int
0x140048a64  mov     r8d, esi; int
0x140048a67  lea     rdx, aFilexferack; "FILEXFERACK"
0x140048a6e  mov     rcx, r15; struct IRDPSRAPIVirtualChannel *
0x140048a71  call    ?SendStringOverVC@@YAJPEAUIRDPSRAPIVirtualChannel@@PEBGJK@Z; SendStringOverVC(IRDPSRAPIVirtualChannel *,ushort const *,long,ulong)
0x140048a76  mov     ecx, eax
0x140048a78  mov     eax, 1
0x140048a7d  xchg    eax, [r12+220h]
0x140048a85  test    ecx, ecx
0x140048a87  jmp     short loc_140048A3F
0x140048a89  test    r15, r15
0x140048a8c  jz      loc_140048BC3
0x140048a92  mov     ecx, 58h ; 'X'; Size
0x140048a97  call    cs:__imp_malloc
0x140048a9e  nop     dword ptr [rax+rax+00h]
0x140048aa3  mov     rbx, rax
0x140048aa6  xor     eax, eax
0x140048aa8  test    rbx, rbx
0x140048aab  jz      loc_140048BB2
0x140048ab1  mov     [rbx], eax
0x140048ab3  mov     [rbx+8], r15
0x140048ab7  mov     [rbx+10h], esi
0x140048aba  xor     esi, esi
0x140048abc  mov     [rbx+14h], esi
0x140048abf  mov     [rbx+18h], r14
0x140048ac3  movups  xmm0, [rbp+4Fh+var_88]
0x140048ac7  movups  xmmword ptr [rbx+20h], xmm0
0x140048acb  movups  xmmword ptr [rbx+30h], xmm6
0x140048acf  movups  xmm0, [rbp+4Fh+var_68]
0x140048ad3  movups  xmmword ptr [rbx+40h], xmm0
0x140048ad7  movsd   xmm1, qword ptr [rbp+4Fh+var_58]
0x140048adc  movsd   qword ptr [rbx+50h], xmm1
0x140048ae1  mov     r15, [rbp+4Fh+var_C8]
0x140048ae5  test    r15, r15
0x140048ae8  jnz     short loc_140048AEF
0x140048aea  mov     r11d, esi
0x140048aed  jmp     short loc_140048B69
0x140048aef  mov     r8d, 104h
0x140048af5  mov     ecx, r8d
0x140048af8  mov     rax, r15
0x140048afb  xor     r9d, r9d
0x140048afe  cmp     [rax], r9w
0x140048b02  jz      short loc_140048B0E
0x140048b04  add     rax, 2
0x140048b08  sub     rcx, 1
0x140048b0c  jnz     short loc_140048AFE
0x140048b0e  mov     rax, rcx
0x140048b11  neg     rax
0x140048b14  sbb     edi, edi
0x140048b16  not     edi
0x140048b18  and     edi, 80070057h
0x140048b1e  mov     rax, rcx
0x140048b21  sub     r8, rcx
0x140048b24  neg     rax
0x140048b27  sbb     rdx, rdx
0x140048b2a  and     rdx, r8
0x140048b2d  test    rcx, rcx
0x140048b30  jz      short loc_140048B7E
0x140048b32  lea     rdi, [rdx+1]
0x140048b36  lea     rcx, [rdi+rdi]; Size
0x140048b3a  call    cs:__imp_malloc
0x140048b41  nop     dword ptr [rax+rax+00h]
0x140048b46  mov     r11, rax
0x140048b49  test    rax, rax
0x140048b4c  jnz     short loc_140048B55
0x140048b4e  mov     edi, 8007000Eh
0x140048b53  jmp     short loc_140048B7E
0x140048b55  mov     r8, r15; unsigned __int16 *
0x140048b58  mov     rdx, rdi; unsigned __int64
0x140048b5b  mov     rcx, r11; unsigned __int16 *
0x140048b5e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140048b63  mov     edi, eax
0x140048b65  test    eax, eax
0x140048b67  js      short loc_140048B6F
  ... truncated ...
```
