# CClipServer::Initialize(void)

- ea: `0x14003bdd0`
- end: `0x14003c1a1`
- name: `?Initialize@CClipServer@@MEAAJXZ`
- size: `977`
- prototype: `__int64 __fastcall(CClipServer *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, installer_update`

## callers

- `0x14003a8c0`

## callees

- `0x140004b1c`
- `0x140005750`
- `0x1400081ac`
- `0x1400081d0`
- `0x140023e58`
- `0x140039df4`
- `0x140039f28`
- `0x14003a2b4`
- `0x14003b0d0`
- `0x14003bdd0`
- `0x14003f518`
- `0x14004038c`
- `0x140046190`
- `0x14004d1c8`
- `0x14004d71c`
- `0x14004dcb8`
- `0x140051830`

## string_xrefs

- `0x14003becb`: `TSCreatePlatform failed!`
- `0x14003bf1a`: `CreateClipUpdateHandler failed!`
- `0x14003bf77`: `CServerRdrFileTransfer::CreateInstance failed!`
- `0x14003bfd0`: `CServerFormatDataPacker::CreateInstance`
- `0x14003c029`: `CClientRcvThreadDispatcher::CreateInstance failed!`
- `0x14003c097`: `CServerRdrVirtualChannel::CreateInstance (static) failed!`
- `0x14003c121`: `UpdateContext failed.`

## pseudocode

```c
__int64 __fastcall CClipServer::Initialize(CClipServer *this)
{
  CClipServer *v1; // rsi
  int ClipUpdateHandler; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v5; // edx
  const char *v6; // rcx
  __int64 *v7; // r14
  bool v8; // zf
  __int64 v9; // rbx
  CLIPBOARD_DATA_CHANNEL_CONTEXT *v10; // rax
  __int64 *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  int v15; // [rsp+28h] [rbp-38h]
  __int64 v16; // [rsp+30h] [rbp-30h] BYREF
  __int64 v17; // [rsp+38h] [rbp-28h]
  __int64 v18; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v19[24]; // [rsp+48h] [rbp-18h] BYREF
  char v20; // [rsp+90h] [rbp+30h] BYREF

  v1 = (CClipServer *)((char *)this - 8);
  v18 = 0;
  if ( *((_DWORD *)this + 85) )
  {
    ClipUpdateHandler = -2092629014;
    goto LABEL_49;
  }
  ClipUpdateHandler = CClipBase::Initialize(this);
  if ( ClipUpdateHandler >= 0 )
  {
    ClipUpdateHandler = TSCreateCoreEvents(*((struct ITSPlatform **)this + 83));
    if ( ClipUpdateHandler >= 0 )
    {
      ClipUpdateHandler = CClipServer::CreateClipUpdateHandler(v1);
      if ( ClipUpdateHandler >= 0 )
      {
        ClipUpdateHandler = CServerRdrFileTransfer::CreateInstance(
                              (const unsigned __int16 *)this + 176,
                              (struct CRdrFileTransfer **)this + 76);
        if ( ClipUpdateHandler >= 0 )
        {
          ClipUpdateHandler = CServerFormatDataPacker::CreateInstance(
                                *((struct CRdrFileTransfer **)this + 76),
                                (struct CFormatDataPacker **)this + 77,
                                v1);
          if ( ClipUpdateHandler >= 0 )
          {
            ClipUpdateHandler = CServerClipRdrPduDispatcher::CreateInstance(
                                  *((struct ITSCoreEvents **)this + 84),
                                  (struct IRdrPduDispatcher **)this + 79);
            if ( ClipUpdateHandler >= 0 )
            {
              v7 = (__int64 *)((char *)this + 624);
              ClipUpdateHandler = CServerRdrVirtualChannel::CreateInstance(
                                    *((struct IRdrPduDispatcher **)this + 79),
                                    *((struct IRDPVirtualChannel **)this + 113),
                                    (struct IRdrVCConnectedCallback *)(((unsigned __int64)this + 56)
                                                                     & -(__int64)(v1 != 0)),
                                    (struct IRdrVirtualChannel **)this + 78);
              if ( ClipUpdateHandler >= 0 )
              {
                LOWORD(v16) = 0;
                v8 = *v7 == 0;
                HIDWORD(v16) = -1;
                LODWORD(v17) = -1;
                if ( !v8 )
                {
                  TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v18);
                  v18 = *v7;
                  TCntPtr<IRdrVirtualChannel>::SafeAddRef(&v18);
                }
                v9 = *((_QWORD *)this + 105);
                v10 = CLIPBOARD_DATA_CHANNEL_CONTEXT::CLIPBOARD_DATA_CHANNEL_CONTEXT(
                        (CLIPBOARD_DATA_CHANNEL_CONTEXT *)v19,
                        (const struct CLIPBOARD_DATA_CHANNEL_CONTEXT *)&v16);
                ClipUpdateHandler = CDataChannelManager::UpdateContext(v9, 0, (__int64)v10);
                if ( ClipUpdateHandler >= 0 )
                {
                  *((_DWORD *)this + 82) = -1;
                  *((_DWORD *)this + 84) = 0x7FFFFFFF;
                  v11 = (__int64 *)IFileFilterClipboardPlugin::CreateInstance(&v20);
                  v12 = *v11;
                  *v11 = 0;
                  v13 = *((_QWORD *)this + 130);
                  *((_QWORD *)this + 130) = v12;
                  if ( v13 )
                    utl::default_delete<IFileFilterClipboardPlugin>::operator()();
                  utl::unique_ptr<IFileFilterClipboardPlugin,utl::default_delete<IFileFilterClipboardPlugin>>::~unique_ptr<IFileFilterClipboardPlugin,utl::default_delete<IFileFilterClipboardPlugin>>(&v20);
                  ClipUpdateHandler = 0;
                  *((_DWORD *)this + 85) = 1;
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                  v5 = 26;
                  v6 = "UpdateContext failed.";
                  goto LABEL_8;
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v5 = 25;
                v6 = "CServerRdrVirtualChannel::CreateInstance (static) failed!";
                goto LABEL_8;
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              v5 = 24;
              v6 = "CClientRcvThreadDispatcher::CreateInstance failed!";
              goto LABEL_8;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v5 = 23;
            v6 = "CServerFormatDataPacker::CreateInstance";
            goto LABEL_8;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v5 = 22;
          v6 = "CServerRdrFileTransfer::CreateInstance failed!";
          goto LABEL_8;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v5 = 21;
        v6 = "CreateClipUpdateHandler failed!";
        goto LABEL_8;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v5 = 20;
      v6 = "TSCreatePlatform failed!";
      goto LABEL_8;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 19;
    v6 = "CClipBase::Initialize failed!";
LABEL_8:
    v15 = ClipUpdateHandler;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      (unsigned int)WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v6,
      v15,
      v16,
      v17,
      v18);
  }
LABEL_49:
  TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v18);
  return (unsigned int)ClipUpdateHandler;
}

```

## disassembly

```asm
0x14003bdd0  mov     [rsp-28h+arg_8], rbx
0x14003bdd5  mov     [rsp-28h+arg_10], rsi
0x14003bdda  push    rbp
0x14003bddb  push    rdi
0x14003bddc  push    r12
0x14003bdde  push    r14
0x14003bde0  push    r15
0x14003bde2  mov     rbp, rsp
0x14003bde5  sub     rsp, 60h
0x14003bde9  lea     rsi, [rcx-8]
0x14003bded  mov     [rbp+var_20], 0
0x14003bdf5  cmp     dword ptr [rsi+15Ch], 0
0x14003bdfc  mov     rdi, rcx
0x14003bdff  jz      short loc_14003BE0B
0x14003be01  mov     ebx, 834503EAh
0x14003be06  jmp     loc_14003C17D
0x14003be0b  call    ?Initialize@CClipBase@@MEAAJXZ; CClipBase::Initialize(void)
0x14003be10  mov     ebx, eax
0x14003be12  test    eax, eax
0x14003be14  jns     short loc_14003BE7A
0x14003be16  mov     rcx, cs:WPP_GLOBAL_Control
0x14003be1d  lea     rax, WPP_GLOBAL_Control
0x14003be24  cmp     rcx, rax
0x14003be27  jz      loc_14003C17D
0x14003be2d  test    byte ptr [rcx+1Ch], 8
0x14003be31  jz      loc_14003C17D
0x14003be37  cmp     byte ptr [rcx+19h], 2
0x14003be3b  jb      loc_14003C17D
0x14003be41  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003be46  mov     edx, 13h
0x14003be4b  lea     rcx, aCclipbaseIniti; "CClipBase::Initialize failed!"
0x14003be52  mov     [rsp+60h+var_38], ebx
0x14003be56  lea     r8, WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids
0x14003be5d  mov     [rsp+60h+var_40], rcx
0x14003be62  mov     r9d, eax
0x14003be65  mov     rcx, cs:WPP_GLOBAL_Control
0x14003be6c  mov     rcx, [rcx+10h]
0x14003be70  call    WPP_SF_DsD
0x14003be75  jmp     loc_14003C17D
0x14003be7a  mov     rcx, [rdi+298h]; struct ITSPlatform *
0x14003be81  lea     r15, [rdi+2A0h]
0x14003be88  mov     rdx, r15
0x14003be8b  call    TSCreateCoreEvents
0x14003be90  mov     ebx, eax
0x14003be92  test    eax, eax
0x14003be94  jns     short loc_14003BED7
0x14003be96  mov     rcx, cs:WPP_GLOBAL_Control
0x14003be9d  lea     rax, WPP_GLOBAL_Control
0x14003bea4  cmp     rcx, rax
0x14003bea7  jz      loc_14003C17D
0x14003bead  test    byte ptr [rcx+1Ch], 8
0x14003beb1  jz      loc_14003C17D
0x14003beb7  cmp     byte ptr [rcx+19h], 2
0x14003bebb  jb      loc_14003C17D
0x14003bec1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003bec6  mov     edx, 14h
0x14003becb  lea     rcx, aTscreateplatfo_1; "TSCreatePlatform failed!"
0x14003bed2  jmp     loc_14003BE52
0x14003bed7  mov     rcx, rsi; this
0x14003beda  call    ?CreateClipUpdateHandler@CClipServer@@AEAAJXZ; CClipServer::CreateClipUpdateHandler(void)
0x14003bedf  mov     ebx, eax
0x14003bee1  test    eax, eax
0x14003bee3  jns     short loc_14003BF26
0x14003bee5  mov     rcx, cs:WPP_GLOBAL_Control
0x14003beec  lea     rax, WPP_GLOBAL_Control
0x14003bef3  cmp     rcx, rax
0x14003bef6  jz      loc_14003C17D
0x14003befc  test    byte ptr [rcx+1Ch], 8
0x14003bf00  jz      loc_14003C17D
0x14003bf06  cmp     byte ptr [rcx+19h], 2
0x14003bf0a  jb      loc_14003C17D
0x14003bf10  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003bf15  mov     edx, 15h
0x14003bf1a  lea     rcx, aCreateclipupda; "CreateClipUpdateHandler failed!"
0x14003bf21  jmp     loc_14003BE52
0x14003bf26  lea     r14, [rdi+260h]
0x14003bf2d  mov     rdx, r14; struct CRdrFileTransfer **
0x14003bf30  lea     rcx, [rdi+160h]; unsigned __int16 *
0x14003bf37  call    ?CreateInstance@CServerRdrFileTransfer@@SAJPEBGPEAPEAVCRdrFileTransfer@@@Z; CServerRdrFileTransfer::CreateInstance(ushort const *,CRdrFileTransfer * *)
0x14003bf3c  mov     ebx, eax
0x14003bf3e  test    eax, eax
0x14003bf40  jns     short loc_14003BF83
0x14003bf42  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bf49  lea     rax, WPP_GLOBAL_Control
0x14003bf50  cmp     rcx, rax
0x14003bf53  jz      loc_14003C17D
0x14003bf59  test    byte ptr [rcx+1Ch], 8
0x14003bf5d  jz      loc_14003C17D
0x14003bf63  cmp     byte ptr [rcx+19h], 2
0x14003bf67  jb      loc_14003C17D
0x14003bf6d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003bf72  mov     edx, 16h
0x14003bf77  lea     rcx, aCserverrdrfile_0; "CServerRdrFileTransfer::CreateInstance "...
0x14003bf7e  jmp     loc_14003BE52
0x14003bf83  mov     rcx, [r14]; struct CRdrFileTransfer *
0x14003bf86  lea     rdx, [rdi+268h]; struct CFormatDataPacker **
0x14003bf8d  mov     r8, rsi; struct CClipBase *
0x14003bf90  call    ?CreateInstance@CServerFormatDataPacker@@SAJPEAVCRdrFileTransfer@@PEAPEAVCFormatDataPacker@@PEAVCClipBase@@@Z; CServerFormatDataPacker::CreateInstance(CRdrFileTransfer *,CFormatDataPacker * *,CClipBase *)
0x14003bf95  mov     ebx, eax
0x14003bf97  test    eax, eax
0x14003bf99  jns     short loc_14003BFDC
0x14003bf9b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bfa2  lea     rax, WPP_GLOBAL_Control
0x14003bfa9  cmp     rcx, rax
0x14003bfac  jz      loc_14003C17D
0x14003bfb2  test    byte ptr [rcx+1Ch], 8
0x14003bfb6  jz      loc_14003C17D
0x14003bfbc  cmp     byte ptr [rcx+19h], 2
0x14003bfc0  jb      loc_14003C17D
0x14003bfc6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003bfcb  mov     edx, 17h
0x14003bfd0  lea     rcx, aCserverformatd_0; "CServerFormatDataPacker::CreateInstance"
0x14003bfd7  jmp     loc_14003BE52
0x14003bfdc  mov     rcx, [r15]; struct ITSCoreEvents *
0x14003bfdf  lea     r12, [rdi+278h]
0x14003bfe6  mov     rdx, r12; struct IRdrPduDispatcher **
0x14003bfe9  call    ?CreateInstance@CServerClipRdrPduDispatcher@@SAJPEAVITSCoreEvents@@PEAPEAVIRdrPduDispatcher@@@Z; CServerClipRdrPduDispatcher::CreateInstance(ITSCoreEvents *,IRdrPduDispatcher * *)
0x14003bfee  mov     ebx, eax
0x14003bff0  test    eax, eax
0x14003bff2  jns     short loc_14003C035
0x14003bff4  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bffb  lea     rax, WPP_GLOBAL_Control
0x14003c002  cmp     rcx, rax
0x14003c005  jz      loc_14003C17D
0x14003c00b  test    byte ptr [rcx+1Ch], 8
0x14003c00f  jz      loc_14003C17D
0x14003c015  cmp     byte ptr [rcx+19h], 2
0x14003c019  jb      loc_14003C17D
0x14003c01f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003c024  mov     edx, 18h
0x14003c029  lea     rcx, aCclientrcvthre; "CClientRcvThreadDispatcher::CreateInsta"...
0x14003c030  jmp     loc_14003BE52
0x14003c035  mov     rdx, [rdi+388h]; struct IRDPVirtualChannel *
0x14003c03c  lea     rax, [rdi+38h]
0x14003c040  mov     rcx, [r12]; struct IRdrPduDispatcher *
0x14003c044  lea     r14, [rdi+270h]
0x14003c04b  neg     rsi
0x14003c04e  mov     r9, r14; struct IRdrVirtualChannel **
0x14003c051  sbb     r8, r8
0x14003c054  and     r8, rax; struct IRdrVCConnectedCallback *
0x14003c057  call    ?CreateInstance@CServerRdrVirtualChannel@@SAJPEAVIRdrPduDispatcher@@PEAUIRDPVirtualChannel@@PEAVIRdrVCConnectedCallback@@PEAPEAVIRdrVirtualChannel@@@Z; CServerRdrVirtualChannel::CreateInstance(IRdrPduDispatcher *,IRDPVirtualChannel *,IRdrVCConnectedCallback *,IRdrVirtualChannel * *)
0x14003c05c  mov     ebx, eax
0x14003c05e  test    eax, eax
0x14003c060  jns     short loc_14003C0A3
0x14003c062  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c069  lea     rax, WPP_GLOBAL_Control
0x14003c070  cmp     rcx, rax
0x14003c073  jz      loc_14003C17D
0x14003c079  test    byte ptr [rcx+1Ch], 8
0x14003c07d  jz      loc_14003C17D
0x14003c083  cmp     byte ptr [rcx+19h], 2
0x14003c087  jb      loc_14003C17D
0x14003c08d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003c092  mov     edx, 19h
0x14003c097  lea     rcx, aCserverrdrvirt_0; "CServerRdrVirtualChannel::CreateInstanc"...
0x14003c09e  jmp     loc_14003BE52
0x14003c0a3  or      esi, 0FFFFFFFFh
0x14003c0a6  mov     [rbp+var_30], 0
0x14003c0ac  cmp     qword ptr [r14], 0
0x14003c0b0  mov     [rbp+var_2C], esi
0x14003c0b3  mov     dword ptr [rbp+var_28], esi
0x14003c0b6  jz      short loc_14003C0D1
0x14003c0b8  lea     rcx, [rbp+var_20]
0x14003c0bc  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14003c0c1  mov     rax, [r14]
0x14003c0c4  lea     rcx, [rbp+var_20]
0x14003c0c8  mov     [rbp+var_20], rax
0x14003c0cc  call    ?SafeAddRef@?$TCntPtr@VIRdrVirtualChannel@@@@AEAAXXZ; TCntPtr<IRdrVirtualChannel>::SafeAddRef(void)
0x14003c0d1  mov     rbx, [rdi+348h]
0x14003c0d8  lea     rdx, [rbp+var_30]; struct CLIPBOARD_DATA_CHANNEL_CONTEXT *
0x14003c0dc  lea     rcx, [rbp+var_18]; this
0x14003c0e0  call    ??0CLIPBOARD_DATA_CHANNEL_CONTEXT@@QEAA@AEBU0@@Z; CLIPBOARD_DATA_CHANNEL_CONTEXT::CLIPBOARD_DATA_CHANNEL_CONTEXT(CLIPBOARD_DATA_CHANNEL_CONTEXT const &)
0x14003c0e5  mov     r8, rax
0x14003c0e8  xor     edx, edx
0x14003c0ea  mov     rcx, rbx
0x14003c0ed  call    ?UpdateContext@CDataChannelManager@@QEAAJJUCLIPBOARD_DATA_CHANNEL_CONTEXT@@@Z; CDataChannelManager::UpdateContext(long,CLIPBOARD_DATA_CHANNEL_CONTEXT)
0x14003c0f2  mov     ebx, eax
0x14003c0f4  test    eax, eax
0x14003c0f6  jns     short loc_14003C12D
0x14003c0f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c0ff  lea     rax, WPP_GLOBAL_Control
0x14003c106  cmp     rcx, rax
0x14003c109  jz      short loc_14003C17D
0x14003c10b  test    byte ptr [rcx+1Ch], 8
0x14003c10f  jz      short loc_14003C17D
0x14003c111  cmp     byte ptr [rcx+19h], 2
0x14003c115  jb      short loc_14003C17D
0x14003c117  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003c11c  mov     edx, 1Ah
0x14003c121  lea     rcx, aUpdatecontextF; "UpdateContext failed."
0x14003c128  jmp     loc_14003BE52
0x14003c12d  lea     rcx, [rbp+arg_0]
0x14003c131  mov     [rdi+148h], esi
0x14003c137  mov     dword ptr [rdi+150h], 7FFFFFFFh
0x14003c141  call    ?CreateInstance@IFileFilterClipboardPlugin@@SA?AV?$unique_ptr@VIFileFilterClipboardPlugin@@U?$default_delete@VIFileFilterClipboardPlugin@@@utl@@@utl@@XZ; IFileFilterClipboardPlugin::CreateInstance(void)
0x14003c146  mov     rcx, [rax]
0x14003c149  mov     qword ptr [rax], 0
0x14003c150  mov     rdx, [rdi+410h]
0x14003c157  mov     [rdi+410h], rcx
0x14003c15e  test    rdx, rdx
0x14003c161  jz      short loc_14003C168
0x14003c163  call    ??R?$default_delete@VIFileFilterClipboardPlugin@@@utl@@QEBAXPEAVIFileFilterClipboardPlugin@@@Z; utl::default_delete<IFileFilterClipboardPlugin>::operator()(IFileFilterClipboardPlugin *)
0x14003c168  lea     rcx, [rbp+arg_0]
0x14003c16c  call    ??1?$unique_ptr@VIFileFilterClipboardPlugin@@U?$default_delete@VIFileFilterClipboardPlugin@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<IFileFilterClipboardPlugin,utl::default_delete<IFileFilterClipboardPlugin>>::~unique_ptr<IFileFilterClipboardPlugin,utl::default_delete<IFileFilterClipboardPlugin>>(void)
0x14003c171  xor     ebx, ebx
0x14003c173  mov     dword ptr [rdi+154h], 1
0x14003c17d  lea     rcx, [rbp+var_20]
0x14003c181  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14003c186  lea     r11, [rsp+60h+var_s0]
0x14003c18b  mov     eax, ebx
0x14003c18d  mov     rbx, [r11+38h]
0x14003c191  mov     rsi, [r11+40h]
0x14003c195  mov     rsp, r11
0x14003c198  pop     r15
0x14003c19a  pop     r14
0x14003c19c  pop     r12
0x14003c19e  pop     rdi
0x14003c19f  pop     rbp
0x14003c1a0  retn
```
