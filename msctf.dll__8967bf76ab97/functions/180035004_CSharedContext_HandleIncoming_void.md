# CSharedContext::HandleIncoming(void)

- ea: `0x180035004`
- end: `0x180036149`
- name: `?HandleIncoming@CSharedContext@@AEAAXXZ`
- size: `4421`
- prototype: `void __fastcall(CSharedContext *__hidden this)`
- caller_count: `1`
- callee_count: `56`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800343e4`

## callees

- `0x180031540`
- `0x180032220`
- `0x180033040`
- `0x1800339a4`
- `0x180033b70`
- `0x1800342b4`
- `0x180035004`
- `0x180036150`
- `0x180036b58`
- `0x180036d1c`
- `0x1800375d0`
- `0x180037a38`
- `0x180042f94`
- `0x180043100`
- `0x18004366c`
- `0x180043760`
- `0x1800540ec`
- `0x180054168`
- `0x180054294`
- `0x18005439c`
- `0x1800544b4`
- `0x18005ba10`
- `0x18005f5f8`
- `0x180060314`
- `0x180066458`
- `0x1800672b8`
- `0x180068fe0`
- `0x18006b830`
- `0x18006c330`
- `0x18006d658`
- `0x180071028`
- `0x1800729e0`
- `0x180072e64`
- `0x180073da0`
- `0x180074920`
- `0x180078d78`
- `0x18007cd60`
- `0x18007d524`
- `0x18007dff8`
- `0x18007e180`
- `0x18007efe8`
- `0x18008cdfc`
- `0x18008ced0`
- `0x18009212c`
- `0x18009eaea`
- `0x1800a69f8`
- `0x1800bff88`
- `0x1800c03bc`
- `0x1800c3390`
- `0x1800c37d0`

## import_xrefs

- `ntdll!NtAlpcSendWaitReceivePort` at `0x18003509f`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18003509f`
- `ntdll!NtAlpcDeleteSectionView` at `0x180035473`
- `ntdll!NtAlpcDeleteSectionView` at `0x180035473`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800352e9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800352e9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180035445`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800357a2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180035a37`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180035c5d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003607e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180035445`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800357a2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180035a37`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180035c5d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003607e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003504a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003504a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003561a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180035b22`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003561a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180035b22`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
void __fastcall CSharedContext::HandleIncoming(CSharedContext *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rdx
  bool v6; // r12
  unsigned int v7; // ebx
  int v8; // r13d
  unsigned int v9; // edi
  unsigned int v10; // esi
  __int64 v11; // rbx
  int v12; // ecx
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  struct CSharedDocument *v15; // rax
  __int64 ii; // rbx
  __int64 jj; // rbx
  _DWORD *v18; // rsi
  int v19; // ecx
  __int64 kk; // rdi
  __int64 mm; // rsi
  __int64 v22; // rdi
  int v23; // eax
  int v24; // eax
  __int128 v25; // xmm0
  unsigned int v26; // ebx
  unsigned int v27; // ebx
  __int64 m; // rdi
  CONTEXT_MESSAGE *v29; // rax
  CONTEXT_MESSAGE *v30; // rax
  __int64 v31; // r8
  CONTEXT_MESSAGE *v32; // rbx
  __int64 v33; // rbx
  char v34; // di
  unsigned int k; // edx
  char v36; // al
  __int64 v37; // rcx
  CSharedDocument *i; // rcx
  __int64 v39; // rcx
  CSharedDocument *v40; // rbx
  bool v41; // zf
  unsigned int v42; // ebx
  unsigned int v43; // ebx
  unsigned int v44; // ebx
  int v45; // eax
  __int64 n; // rbx
  __int64 v47; // rax
  struct CSharedDocument *v48; // rax
  __int64 *v49; // rdx
  struct CSharedDocument *v50; // rax
  CONTEXT_MESSAGE *v51; // rax
  CONTEXT_MESSAGE *v52; // rax
  __int64 v53; // rdx
  _QWORD *Tail; // rax
  __int64 v55; // r8
  unsigned int v56; // esi
  unsigned int v57; // edi
  CSharedDocument *v58; // rax
  void *v59; // rcx
  CSharedDocument *v60; // rax
  unsigned int v61; // r9d
  unsigned int v62; // r10d
  __int64 j; // rcx
  int v64; // eax
  CSharedDocument *v65; // rax
  CSharedDocument *v66; // rax
  int v67; // esi
  struct CContextConnection *ImeContext; // rdi
  CSharedDocument *v69; // rax
  struct MsgBase *v70; // rdx
  CSharedDocument *v71; // rax
  struct MsgBase *v72; // rdx
  CSharedDocument *v73; // rax
  CSharedDocument *Document; // rax
  unsigned int v75; // ebx
  CSharedDocument *v76; // rax
  struct MsgBase *v77; // rdx
  void *v78; // rcx
  int v79; // eax
  struct DOCUMENT_RANGE *v80; // [rsp+30h] [rbp-D0h]
  void **v81; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v82; // [rsp+48h] [rbp-B8h]
  int v83; // [rsp+58h] [rbp-A8h]
  char v84; // [rsp+5Ch] [rbp-A4h]
  _BYTE v85[12]; // [rsp+60h] [rbp-A0h] BYREF
  int v86; // [rsp+6Ch] [rbp-94h]
  __int64 v87; // [rsp+70h] [rbp-90h] BYREF
  void **v88; // [rsp+80h] [rbp-80h] BYREF
  __int128 v89; // [rsp+88h] [rbp-78h]
  int v90; // [rsp+98h] [rbp-68h]
  char v91; // [rsp+9Ch] [rbp-64h]
  __int64 v92; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v93[56]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v94; // [rsp+E0h] [rbp-20h]
  _OWORD v95[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v96; // [rsp+110h] [rbp+10h]
  _BYTE v97[24]; // [rsp+120h] [rbp+20h]
  char v98; // [rsp+138h] [rbp+38h] BYREF
  char v99[16]; // [rsp+2F0h] [rbp+1F0h] BYREF

  memset_0(v95, 0, 0x48u);
  LODWORD(v95[0]) = 4718624;
  HIDWORD(v96) = GetCurrentThreadId();
  while ( *((_QWORD *)this + 2) )
  {
    *(_DWORD *)(*((_QWORD *)this + 3) + 4LL) = 0;
    v2 = *((_QWORD *)this + 2);
    v80 = (struct DOCUMENT_RANGE *)*((_QWORD *)this + 3);
    v87 = 512;
    if ( (unsigned int)NtAlpcSendWaitReceivePort(v2, 0, 0, 0, v95, &v87, v80, 0) )
      break;
    if ( (unsigned __int16)(BYTE4(v95[0]) - 1) > 2u )
    {
      if ( BYTE4(v95[0]) == 12 )
      {
        *(_DWORD *)&v97[4] = -2147467259;
      }
      else if ( BYTE4(v95[0]) == 5 )
      {
        CAlpcPort::Close((CSharedContext *)((char *)this + 8));
        return;
      }
    }
    else
    {
      v3 = *((_QWORD *)this + 3);
      if ( (*(_DWORD *)(v3 + 4) & 0x40000000) != 0 && (v53 = *(_QWORD *)(*((_QWORD *)this + 5) + 16LL)) != 0 )
      {
        DWORD2(v96) |= 0x4000000u;
        *(_QWORD *)&v97[16] = v53;
        *(_DWORD *)(v3 + 4) &= ~0x40000000u;
        *(_QWORD *)(*((_QWORD *)this + 5) + 16LL) = 0;
      }
      else if ( SDWORD2(v96) < 0 )
      {
        *(_QWORD *)&v97[16] = &v98;
      }
    }
    v4 = *((_QWORD *)this + 3);
    LODWORD(v5) = 0;
    if ( (*(_DWORD *)(v4 + 4) & 0x20000000) != 0 )
      v5 = *(_QWORD *)(*((_QWORD *)this + 4) + 8LL);
    *(_DWORD *)(v4 + 4) = 0;
    v6 = 0;
    v7 = DWORD2(v96) & 0xFFFFF;
    v8 = BYTE4(v95[0]);
    if ( (DWORD2(v96) & 0xFFFFFu) <= 0x79 )
    {
      if ( v7 == 121 )
        goto LABEL_134;
      if ( v7 > 0x6E )
      {
        switch ( v7 )
        {
          case 'o':
            v89 = 0u;
            v88 = &CMsgTextChange::`vftable';
            v92 = 0;
            v90 = 0;
            v91 = 1;
            memset(v93, 0, 29);
            if ( CMsgTextChange::Read((CMsgTextChange *)&v88, (struct MsgBase *)v95) >= 0 )
            {
              Document = CSharedContext::FindDocument(this, (const struct DOCUMENT_ID *)&v92);
              if ( Document )
                CSharedDocument::OnTextChange(Document, (const struct CMsgTextChange *)&v88);
            }
            CMsgTextChange::~CMsgTextChange((CMsgTextChange *)&v88);
            break;
          case 'p':
            v89 = 0u;
            v88 = &CMsgTextPropertyChange::`vftable';
            v92 = 0;
            v90 = 0;
            v91 = 1;
            memset(v93, 0, 28);
            memset(&v93[32], 0, 24);
            if ( CMsgTextPropertyChange::Read((CMsgTextPropertyChange *)&v88, (struct MsgBase *)v95) >= 0 )
            {
              for ( i = (CSharedDocument *)*((_QWORD *)this + 8); i; i = (CSharedDocument *)*((_QWORD *)i + 2) )
              {
                if ( v92 == *((_QWORD *)i + 4) )
                {
                  CSharedDocument::OnTextPropertyChange(i, (struct CMsgTextPropertyChange *)&v88);
                  break;
                }
              }
            }
            CMsgTextPropertyChange::~CMsgTextPropertyChange((CMsgTextPropertyChange *)&v88);
            break;
          case 'q':
          case 'r':
            goto LABEL_134;
          case 's':
            v90 = 0;
            v88 = &CMsgCompositionChange::`vftable';
            v91 = 1;
            v92 = 0;
            *(_QWORD *)&v93[4] = 0;
            v89 = 0;
            *(_DWORD *)v93 = 0;
            if ( CMsgCompositionChange::Read((CMsgCompositionChange *)&v88, (struct MsgBase *)v95) >= 0 )
            {
              v73 = CSharedContext::FindDocument(this, (const struct DOCUMENT_ID *)&v92);
              if ( v73 )
                CSharedDocument::OnCompositionChange(v73, (const struct CMsgCompositionChange *)&v88);
            }
            CMsgCompositionChange::~CMsgCompositionChange((CMsgCompositionChange *)&v88);
            break;
          case 't':
          case 'u':
LABEL_217:
            v89 = 0u;
            v92 = 0;
            memset(v93, 0, 36);
            v88 = &CMsgCandidateListRequest::`vftable';
            v90 = 0;
            v91 = 1;
            *(_OWORD *)&v93[40] = 0;
            v94 = 0;
            if ( (int)CMsgCandidateListRequest::Read((CMsgCandidateListRequest *)&v88, (struct MsgBase *)v95) >= 0 )
            {
              v71 = CSharedContext::FindDocument(this, (const struct DOCUMENT_ID *)&v92);
              if ( v71 )
              {
                v72 = (struct MsgBase *)v95;
                if ( v8 != 1 )
                  v72 = 0;
                v6 = CSharedDocument::OnCandidateListMessage(
                       v71,
                       v72,
                       v90 & 0xFFFFF,
                       *(unsigned int *)&v93[12],
                       *(unsigned int *)&v93[16],
                       *(unsigned int *)&v93[32],
                       (const struct DOCUMENT_RANGE *)v93);
              }
            }
            CMsgCandidateListRequest::~CMsgCandidateListRequest((CMsgCandidateListRequest *)&v88);
            break;
          case 'v':
            goto LABEL_211;
          case 'x':
            v67 = *(_DWORD *)&v97[20];
            ImeContext = CSharedContext::FindImeContext(this, *(unsigned int *)&v97[16]);
            if ( ImeContext )
            {
              if ( *(_QWORD *)&v97[8] == *((_QWORD *)this + 14) )
              {
                v51 = (CONTEXT_MESSAGE *)LocalAlloc(0x40u, 0xC8u);
                if ( v51 )
                {
                  v52 = CONTEXT_MESSAGE::CONTEXT_MESSAGE(v51);
                  if ( v52 )
                  {
                    *((_DWORD *)v52 + 4) = v7;
                    *((_DWORD *)v52 + 5) = 64;
                    *((_DWORD *)v52 + 31) = v67;
                    *((_DWORD *)v52 + 6) = -2147467259;
                    LinkBase<CONTEXT_MESSAGE *>::Link(v52, (char *)ImeContext + 136);
                  }
                }
              }
            }
            break;
        }
      }
      else
      {
        if ( v7 == 110 )
          goto LABEL_217;
        if ( v7 > 0x69 )
        {
          switch ( v7 )
          {
            case 'j':
              v90 = 0;
              v88 = &CMsgSelectionChange::`vftable';
              v91 = 1;
              v92 = 0;
              *(_QWORD *)&v93[4] = 0;
              v89 = 0;
              *(_DWORD *)v93 = 0;
              if ( CMsgSelectionChange::Read((CMsgSelectionChange *)&v88, (struct MsgBase *)v95) >= 0 )
              {
                v66 = CSharedContext::FindDocument(this, (const struct DOCUMENT_ID *)&v92);
                if ( v66 )
                  CSharedDocument::OnSelectionChange(v66, (const struct CMsgSelectionChange *)&v88);
              }
              CMsgSelectionChange::~CMsgSelectionChange((CMsgSelectionChange *)&v88);
              break;
            case 'k':
              v89 = 0u;
              v88 = &CMsgContentChange::`vftable';
              *(_QWORD *)&v93[8] = 0;
              v90 = -2113929216;
              v91 = 1;
              v92 = 0;
              *(_DWORD *)v93 = 0;
              *(_DWORD *)&v93[16] = 0;
              if ( CMsgGroup::Read((CMsgGroup *)&v88, (struct MsgBase *)v95) >= 0 )
              {
                for ( j = v92; j; j = *(_QWORD *)(j + 8) )
                {
                  v64 = *(_DWORD *)(j + 24) & 0xFFFFF;
                  if ( v64 == 106
                    || v64 == 208
                    || v64 == 115
                    || v64 == 211
                    || v64 == 112
                    || v64 == 210
                    || v64 == 111
                    || v64 == 209 )
                  {
                    *(_QWORD *)&v93[8] = *(_QWORD *)(j + 32);
                    *(_DWORD *)&v93[16] = *(_DWORD *)(j + 40);
                    break;
                  }
                }
                v65 = CSharedContext::FindDocument(this, (const struct DOCUMENT_ID *)&v93[8]);
                if ( v65 )
                  CSharedDocument::OnContentChange(v65, (struct CMsgContentChange *)&v88);
              }
              CMsgGroup::~CMsgGroup((CMsgGroup *)&v88);
              break;
            case 'l':
LABEL_211:
              v90 = 0;
              v88 = &CMsgReconversion::`vftable';
              v91 = 1;
              v92 = 0;
              *(_QWORD *)v93 = 0;
              v89 = 0;
              *(_DWORD *)&v93[8] = 0;
              if ( (int)CMsgReconversion::Read((CMsgReconversion *)&v88, (struct MsgBase *)v95) >= 0 )
              {
                v69 = CSharedContext::FindDocument(this, (const struct DOCUMENT_ID *)&v92);
                if ( v69 )
                {
                  v70 = (struct MsgBase *)v95;
                  if ( v8 != 1 )
                    v70 = 0;
                  v6 = CSharedDocument::OnReconversionRequest(
                         v69,
                         v70,
                         v90 & 0xFFFFF,
                         *(unsigned int *)&v93[8],
                         (const struct DOCUMENT_RANGE *)v93);
                }
              }
              CMsgReconversion::~CMsgReconversion((CMsgReconversion *)&v88);
              break;
            default:
              v81 = &CMsgReleaseCandidateList::`vftable';
              v84 = 1;
              *(_QWORD *)v85 = *(_QWORD *)&v97[8];
              v82 = 0;
              v83 = DWORD2(v96) & 0xFFFFF;
              *(_DWORD *)&v85[8] = *(_DWORD *)&v97[16];
              v86 = *(_DWORD *)&v97[20];
              v60 = CSharedContext::FindDocument(this, (const struct DOCUMENT_ID *)v85);
              if ( v60 )
                CSharedDocument::OnCandidateListMessage(v60, 0, v7, v61, v62, 0, 0);
              break;
          }
        }
        else if ( v7 == 105 )
        {
          if ( *(_QWORD *)&v97[8] == *((_QWORD *)this + 14) )
          {
            v50 = CSharedContext::FindDocument(this, (CSharedContext *)((char *)this + 112));
            if ( v50 )
              CSharedDocument::OnConversionModeChange(v50, *(unsigned int *)&v97[16]);
          }
        }
        else
        {
          v13 = v7 - 41;
          if ( !v13 )
          {
            v81 = &CMsgThreadActiveProfiles::`vftable';
            v82 = 0;
            v83 = 0;
            v84 = 1;
            memset(v85, 0, sizeof(v85));
            if ( (DWORD2(v96) & 0x40000000) == 0
              && CMsgThreadActiveProfiles::Read((CMsgThreadActiveProfiles *)&v81, (struct MsgBase *)v95) < 0
              || (v33 = *((_QWORD *)this + 7)) == 0 )
            {
LABEL_107:
              CMsgThreadActiveProfiles::~CMsgThreadActiveProfiles((CMsgThreadActiveProfiles *)&v81);
              goto LABEL_68;
            }
            while ( 2 )
            {
              v34 = 0;
              for ( k = 0; k < *(_DWORD *)&v85[8]; ++k )
              {
                v4 = *(unsigned int *)(*(_QWORD *)v85 + 4LL * k);
                if ( *(_DWORD *)(v33 + 76) == (_DWORD)v4 )
                {
                  v34 = 1;
                  break;
                }
              }
              v36 = *(_BYTE *)(v33 + 172);
              if ( v36 == v34 )
              {
LABEL_106:
                v33 = *(_QWORD *)(v33 + 24);
                if ( !v33 )
                  goto LABEL_107;
                continue;
              }
              break;
            }
            if ( v36 && *((_DWORD *)this + 29) )
              CSharedDocument::OnKillFocusNotify((struct CContextConnection *)v33);
            if ( v34 )
            {
              if ( (byte_180140041 & 4) != 0 )
              {
                v49 = InputProfileActivation_Profile;
                goto LABEL_184;
              }
            }
            else if ( (byte_180140041 & 4) != 0 )
            {
              v49 = InputProfileDeactivation_Profile;
LABEL_184:
              McTemplateU0t_EventWriteTransfer(v4, v49, *(unsigned int *)(v33 + 76));
            }
            *(_BYTE *)(v33 + 172) = v34;
            goto LABEL_106;
          }
          v14 = v13 - 59;
          if ( v14 )
          {
            v26 = v14 - 1;
            if ( v26 )
            {
              v27 = v26 - 1;
              if ( v27 )
              {
                if ( v27 == 2 )
                {
                  v89 = 0u;
                  v88 = &CMsgKeyPressedEvent::`vftable';
                  v92 = 0;
                  *(_QWORD *)v93 = 0;
                  v90 = 0;
                  v91 = 1;
                  *(_DWORD *)&v93[8] = 0;
                  *(_WORD *)&v93[12] = 0;
                  *(_DWORD *)&v93[16] = 0;
                  v93[20] = 0;
                  if ( (int)CMsgKeyPressedEvent::Read((CMsgKeyPressedEvent *)&v88, (struct MsgBase *)v95) >= 0 )
                  {
                    for ( m = *((_QWORD *)this + 7); m; m = *(_QWORD *)(m + 24) )
                    {
                      if ( *(_DWORD *)(m + 76) == *(_DWORD *)v93 )
                      {
                        if ( v92 == *((_QWORD *)this + 14) )
                        {
                          v29 = (CONTEXT_MESSAGE *)LocalAlloc(0x40u, 0xC8u);
                          if ( v29 )
                          {
                            v30 = CONTEXT_MESSAGE::CONTEXT_MESSAGE(v29);
                            v32 = v30;
                            if ( v30 )
                            {
                              *((_DWORD *)v30 + 4) = 104;
                              *((_QWORD *)v30 + 14) = v92;
                              *((_DWORD *)v30 + 5) = 268435458;
                              *((_OWORD *)v30 + 2) = v95[0];
                              *((_OWORD *)v30 + 3) = v95[1];
                              *((_OWORD *)v30 + 4) = v96;
                              *((_OWORD *)v30 + 5) = *(_OWORD *)v97;
                              *((_QWORD *)v30 + 12) = *(_QWORD *)&v97[16];
                              *((_QWORD *)v30 + 15) = *(unsigned int *)&v93[4];
                              *((_QWORD *)v30 + 16) = *(unsigned int *)&v93[8];
                              *((_WORD *)v30 + 68) = *(_WORD *)&v93[12];
                              *((_DWORD *)v30 + 35) = *(_DWORD *)&v93[16];
                              *((_DWORD *)v30 + 36) = 0;
                              if ( (byte_180140041 & 8) != 0 )
                                McGenEventWrite_EventWriteTransfer(
                                  &Microsoft_Windows_TSF_msctf_Context,
                                  KeyEventRecieved_SharedContext,
                                  v31,
                                  1,
                                  v99);
                              *((_DWORD *)v32 + 6) = -2147467259;
                              if ( *(_QWORD *)(m + 136) )
                              {
                                Tail = (_QWORD *)LinkBase<CONTEXT_MESSAGE *>::GetTail(v32);
                                *Tail = v55;
                                *(_QWORD *)(*(_QWORD *)(m + 136) + 8LL) = Tail;
                              }
                              *(_QWORD *)(m + 136) = v32;
                              v6 = 1;
                            }
                          }
                        }
                        break;
                      }
                    }
                  }
                  CMsgKeyPressedEvent::~CMsgKeyPressedEvent((CMsgKeyPressedEvent *)&v88);
                }
              }
              else
              {
                v56 = *(_DWORD *)&v97[8];
                v57 = *(_DWORD *)&v97[12];
                v84 = 1;
                v81 = &CMsgDocumentSimple::`vftable';
                v86 = *(_DWORD *)&v97[20];
                v82 = 0;
                v83 = 102;
                *(_DWORD *)v85 = *(_DWORD *)&v97[8];
                *(_QWORD *)&v85[4] = *(_QWORD *)&v97[12];
                v58 = CSharedContext::FindDocument(this, (const struct DOCUMENT_ID *)v85);
                if ( v58 )
                  CSharedDocument::SetDisconnected(v58);
                for ( n = *((_QWORD *)this + 7); n; n = *(_QWORD *)(n + 24) )
                {
                  if ( !CContextConnection::IsOutgoingProcessed((CContextConnection *)n) )
                  {
                    v47 = *(_QWORD *)(n + 128);
                    if ( *(_DWORD *)(v47 + 112) == v56 && *(_DWORD *)(v47 + 116) == v57 )
                      SetEvent(*(HANDLE *)(n + 88));
                  }
                  if ( !CContextConnection::IsEditSessionRequestCompleted((CContextConnection *)n)
                    && *(_QWORD *)(n + 160) == __PAIR64__(v57, v56) )
                  {
                    v59 = *(void **)(n + 112);
                    *(_DWORD *)(n + 168) = 3;
                    SetEvent(v59);
                  }
                }
              }
            }
            else if ( *(_QWORD *)&v97[8] == *((_QWORD *)this + 14) )
            {
              v48 = CSharedContext::FindDocument(this, (CSharedContext *)((char *)this + 112));
              if ( v48 )
                CSharedDocument::OnSettingsChange(v48, *(unsigned int *)&v97[16]);
            }
          }
          else
          {
            v89 = 0u;
            v88 = &CMsgDocumentEvent::`vftable';
            v90 = 0;
            v91 = 1;
            v92 = 0;
            memset(v93, 0, 28);
            *(_DWORD *)&v93[28] = -1;
            if ( (byte_180140041 & 4) != 0 )
              McTemplateU0qq_EventWriteTransfer(v4, DocumentFocusChangeRecd_Profile, (unsigned int)v92, HIDWORD(v92));
            if ( CMsgDocumentEvent::Read((CMsgDocumentEvent *)&v88, (struct MsgBase *)v95) >= 0 )
            {
              if ( HIDWORD(v92) )
              {
                v40 = CSharedContext::FindOrCreateDocument(this, (const struct DOCUMENT_ID *)&v92);
                if ( v40 )
                {
                  if ( (byte_180140041 & 4) != 0 )
                    McTemplateU0qq_EventWriteTransfer(
                      v39,
                      DocumentFocusChangeSent_Profile,
                      (unsigned int)v92,
                      HIDWORD(v92));
                  CSharedDocument::OnSetFocus(
                    v40,
                    (const struct CMsgDocumentEvent *)&v88,
                    *((struct CContextConnection **)this + 7));
                }
              }
              else if ( *((_DWORD *)this + 29) )
              {
                v15 = CSharedContext::FindDocument(this, (CSharedContext *)((char *)this + 112));
                if ( v15 )
                {
                  for ( ii = *((_QWORD *)v15 + 6); ii; ii = *(_QWORD *)(ii + 40) )
                    CSharedDocument::OnKillFocusNotify(*(struct CContextConnection **)(ii + 56));
                }
              }
              *((_QWORD *)this + 14) = v92;
            }
            CMsgDocumentEvent::~CMsgDocumentEvent((CMsgDocumentEvent *)&v88);
          }
        }
      }
    }
    else
    {
      if ( v7 <= 0xCB )
      {
        if ( v7 != 203 )
        {
          if ( v7 > 0x80 )
          {
            v42 = v7 - 129;
            v41 = v42 == 0;
            goto LABEL_130;
          }
          if ( v7 != 128 )
          {
            v75 = v7 - 122;
            if ( v75 )
            {
              v42 = v75 - 1;
              v41 = v42 == 0;
LABEL_130:
              if ( !v41 )
              {
                v43 = v42 - 1;
                if ( v43 )
                {
                  v44 = v43 - 1;
                  if ( v44 )
                  {
                    if ( v44 - 1 > 1 )
                      goto LABEL_68;
                  }
                }
              }
            }
          }
LABEL_134:
          v90 = 0;
          v88 = &CMsgCandidateListEvent::`vftable';
          v91 = 1;
          v92 = 0;
          *(_QWORD *)v93 = 0;
          v89 = 0;
          *(_DWORD *)&v93[8] = 0;
          if ( CMsgCandidateListEvent::Read((CMsgCandidateListEvent *)&v88, (struct MsgBase *)v95) >= 0 )
          {
            v76 = CSharedContext::FindDocument(this, (const struct DOCUMENT_ID *)&v92);
            if ( v76 )
            {
              v77 = (struct MsgBase *)v95;
              if ( v8 != 1 )
                v77 = 0;
              v6 = CSharedDocument::OnCandidateListMessage(
                     v76,
                     v77,
                     v90 & 0xFFFFF,
                     *(unsigned int *)v93,
                     *(unsigned int *)&v93[4],
                     *(unsigned int *)&v93[8],
                     0);
            }
          }
          CMsgCandidateListEvent::~CMsgCandidateListEvent((CMsgCandidateListEvent *)&v88);
          goto LABEL_68;
        }
      }
      else if ( v7 != 204 )
      {
        if ( v7 == 208 || v7 == 209 || v7 == 210 || v7 == 211 || v7 == 212 )
        {
          for ( jj = *((_QWORD *)this + 7); jj; jj = *(_QWORD *)(jj + 24) )
          {
            if ( *(_DWORD *)(jj + 76) == (_DWORD)v5 )
            {
              v18 = *(_DWORD **)(jj + 128);
              if ( v18 )
              {
                if ( WaitForSingleObject(*(HANDLE *)(jj + 88), 0) )
                {
                  if ( CContextConnection::IsEditSessionRequestCompleted((CContextConnection *)jj) )
                  {
                    v19 = v18[28];
                    if ( *(_DWORD *)(jj + 160) == v19 && *(_DWORD *)(jj + 164) == v18[29] )
                    {
                      v18[6] = *(_DWORD *)&v97[4];
                      for ( kk = *((_QWORD *)this + 8); kk; kk = *(_QWORD *)(kk + 16) )
                      {
                        if ( v19 == *(_DWORD *)(kk + 32) && v18[29] == *(_DWORD *)(kk + 36) )
                        {
                          v37 = *(_QWORD *)(kk + 128);
                          if ( v37 )
                          {
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                            *(_QWORD *)(kk + 128) = 0;
                          }
                          break;
                        }
                      }
                      SetEvent(*(HANDLE *)(jj + 88));
                    }
                  }
                }
              }
              goto LABEL_68;
            }
          }
        }
        else if ( v7 == 213 )
        {
          v9 = *(_DWORD *)&v97[8];
          v10 = *(_DWORD *)&v97[12];
          v11 = *((_QWORD *)this + 7);
          v92 = *(_QWORD *)&v97[8];
          while ( 1 )
          {
            if ( !v11 )
            {
              v11 = 0;
              goto LABEL_26;
            }
            if ( *(_DWORD *)(v11 + 76) == (_DWORD)v5 )
              break;
            v11 = *(_QWORD *)(v11 + 24);
          }
          if ( !CContextConnection::IsEditSessionRequestCompleted((CContextConnection *)v11)
            && __PAIR64__(v10, v9) == *(_QWORD *)(v11 + 160) )
          {
            v78 = *(void **)(v11 + 112);
            *(_DWORD *)(v11 + 168) = 2;
            SetEvent(v78);
            goto LABEL_68;
          }
LABEL_26:
          if ( v11 )
            v12 = *(_DWORD *)(v11 + 76);
          else
            v12 = 0;
          *(_DWORD *)&v85[8] = v12;
          v81 = &CMsgDocumentLock::`vftable';
          *(_QWORD *)v85 = v92;
          v83 = 16777430;
          v82 = 0;
          v84 = 1;
          LOBYTE(v86) = 0;
          CAlpcPort::AlpcPost((CSharedContext *)((char *)this + 8), (struct CMsgStruct *)&v81, 0);
        }
        goto LABEL_68;
      }
      for ( mm = *((_QWORD *)this + 7); mm; mm = *(_QWORD *)(mm + 24) )
      {
        if ( *(_DWORD *)(mm + 76) == (_DWORD)v5 )
        {
          if ( CContextConnection::IsOutgoingProcessed((CContextConnection *)mm) )
            break;
          v22 = *(_QWORD *)(mm + 128);
          if ( v22 )
          {
            if ( *(_DWORD *)(v22 + 16) != v7 )
              break;
            *(_DWORD *)(v22 + 24) = *(_DWORD *)&v97[4];
            if ( *(int *)&v97[4] >= 0 )
            {
              if ( v7 == 203 )
              {
                v90 = 0;
                v88 = &CMsgGetText::`vftable';
                *(_QWORD *)&v93[8] = 0;
                v92 = 0;
                *(_QWORD *)v93 = 0;
                v89 = 0;
                v91 = 1;
                v45 = CMsgGetText::Read((CMsgGetText *)&v88, (struct MsgBase *)v95);
                *(_DWORD *)(v22 + 24) = v45;
                if ( v45 >= 0 )
                {
                  v79 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v22 + 120) + 24LL))(*(_QWORD *)(v22 + 120));
                  if ( *(_DWORD *)v93 == v79 )
                  {
                    *(_DWORD *)(v22 + 144) = *(_DWORD *)&v93[4];
                    *(_QWORD *)(v22 + 136) = *(_QWORD *)&v93[8];
                    *(_QWORD *)&v93[8] = 0;
                  }
                }
                CMsgGetText::~CMsgGetText((CMsgGetText *)&v88);
              }
              else
              {
                v89 = 0u;
                v88 = &CMsgGetTextProperty::`vftable';
                v90 = 0;
                v92 = 0;
                memset(v93, 0, 48);
                v91 = 1;
                v23 = CMsgGetTextProperty::Read((CMsgGetTextProperty *)&v88, (struct MsgBase *)v95);
                *(_DWORD *)(v22 + 24) = v23;
                if ( v23 >= 0 )
                {
                  v24 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v22 + 120) + 24LL))(*(_QWORD *)(v22 + 120));
                  if ( *(_DWORD *)v93 == v24 )
                  {
                    v25 = *(_OWORD *)&v93[32];
                    *(_QWORD *)(v22 + 152) = *(_QWORD *)&v93[24];
                    *(_WORD *)&v93[24] = 0;
                    *(_OWORD *)(v22 + 160) = v25;
                  }
                }
                CMsgGetTextProperty::~CMsgGetTextProperty((CMsgGetTextProperty *)&v88);
              }
            }
          }
          SetEvent(*(HANDLE *)(mm + 88));
          break;
        }
      }
    }
LABEL_68:
    if ( v8 == 1 && !v6 )
      CAlpcPort::AlpcReply((CSharedContext *)((char *)this + 8), (const struct MsgBase *)v95, 0, -2147467259);
    if ( (DWORD2(v96) & 0x4000000) != 0 )
    {
      NtAlpcDeleteSectionView(*((_QWORD *)this + 2), 0, *(_QWORD *)&v97[16]);
      DWORD2(v96) &= ~0x4000000u;
      *(_QWORD *)&v97[16] = 0;
    }
  }
}

```

## disassembly

```asm
0x180035004  push    rbp
0x180035006  push    rbx
0x180035007  push    rsi
0x180035008  push    rdi
0x180035009  push    r12
0x18003500b  push    r13
0x18003500d  push    r14
0x18003500f  push    r15
0x180035011  lea     rbp, [rsp-218h]
0x180035019  sub     rsp, 318h
0x180035020  mov     rax, cs:__security_cookie
0x180035027  xor     rax, rsp
0x18003502a  mov     [rbp+250h+var_50], rax
0x180035031  xor     edx, edx; Val
0x180035033  mov     r14, rcx
0x180035036  lea     rcx, [rbp+250h+var_260]; void *
0x18003503a  lea     r8d, [rdx+48h]; Size
0x18003503e  call    memset_0
0x180035043  mov     dword ptr [rbp+250h+var_260], 480020h
0x18003504a  call    cs:__imp_GetCurrentThreadId
0x180035050  xor     esi, esi
0x180035052  mov     [rbp+250h+var_234], eax
0x180035055  lea     r15, [r14+8]
0x180035059  lea     edi, [rsi+2]
0x18003505c  cmp     [r15+8], rsi
0x180035060  jz      short loc_1800350A9
0x180035062  mov     rax, [r15+10h]
0x180035066  xor     r9d, r9d
0x180035069  mov     [rsp+350h+var_318], rsi
0x18003506e  xor     r8d, r8d
0x180035071  xor     edx, edx
0x180035073  mov     [rax+4], esi
0x180035076  mov     rax, [r15+10h]
0x18003507a  mov     rcx, [r15+8]
0x18003507e  mov     [rsp+350h+var_320], rax
0x180035083  lea     rax, [rsp+350h+var_2E0]
0x180035088  mov     qword ptr [rsp+350h+var_328], rax
0x18003508d  lea     rax, [rbp+250h+var_260]
0x180035091  mov     [rsp+350h+var_330], rax
0x180035096  mov     [rsp+350h+var_2E0], 200h
0x18003509f  call    cs:__imp_NtAlpcSendWaitReceivePort
0x1800350a5  test    eax, eax
0x1800350a7  jz      short loc_1800350CC
0x1800350a9  mov     rcx, [rbp+250h+var_50]
0x1800350b0  xor     rcx, rsp; StackCookie
0x1800350b3  call    __security_check_cookie
0x1800350b8  add     rsp, 318h
0x1800350bf  pop     r15
0x1800350c1  pop     r14
0x1800350c3  pop     r13
0x1800350c5  pop     r12
0x1800350c7  pop     rdi
0x1800350c8  pop     rsi
0x1800350c9  pop     rbx
0x1800350ca  pop     rbp
0x1800350cb  retn
0x1800350cc  movzx   ecx, word ptr [rbp+250h+var_260+4]
0x1800350d0  mov     eax, 0FFh
0x1800350d5  and     cx, ax
0x1800350d8  mov     r9d, 1
0x1800350de  movzx   eax, cx
0x1800350e1  sub     ax, r9w
0x1800350e5  cmp     ax, di
0x1800350e8  ja      loc_180035925
0x1800350ee  mov     rcx, [r15+10h]
0x1800350f2  test    dword ptr [rcx+4], 40000000h
0x1800350f9  jnz     loc_180035B76
0x1800350ff  test    [rbp+250h+var_238], 80000000h
0x180035106  jz      short loc_180035110
0x180035108  lea     rax, [rbp+250h+var_218]
0x18003510c  mov     qword ptr [rbp+250h+var_220], rax
0x180035110  mov     rcx, [r15+10h]
0x180035114  mov     rdx, rsi
0x180035117  test    dword ptr [rcx+4], 20000000h
0x18003511e  jz      short loc_180035128
0x180035120  mov     rax, [r15+18h]
0x180035124  mov     rdx, [rax+8]
0x180035128  mov     [rcx+4], esi
0x18003512b  mov     r12b, sil
0x18003512e  mov     ebx, [rbp+250h+var_238]
0x180035131  movzx   r13d, word ptr [rbp+250h+var_260+4]
0x180035136  and     ebx, 0FFFFFh
0x18003513c  and     r13d, 0FFFF00FFh
0x180035143  cmp     ebx, 79h ; 'y'
0x180035146  jbe     loc_1800351FE
0x18003514c  mov     eax, 0CBh
0x180035151  cmp     ebx, eax
0x180035153  jbe     loc_18003588F
0x180035159  mov     eax, ebx
0x18003515b  sub     eax, 0CCh
0x180035160  jz      loc_18003534F
0x180035166  sub     eax, 4
0x180035169  jz      loc_1800352BD
0x18003516f  sub     eax, r9d
0x180035172  jz      loc_1800352BD
0x180035178  sub     eax, r9d
0x18003517b  jz      loc_1800352BD
0x180035181  sub     eax, r9d
0x180035184  jz      loc_1800352BD
0x18003518a  sub     eax, r9d
0x18003518d  jz      loc_1800352BD
0x180035193  cmp     eax, r9d
0x180035196  jnz     loc_180035452
0x18003519c  mov     edi, dword ptr [rbp+250h+var_228]
0x18003519f  xor     eax, eax
0x1800351a1  mov     esi, dword ptr [rbp+250h+var_228+4]
0x1800351a4  mov     rbx, [r14+38h]
0x1800351a8  mov     [rbp+250h+var_2B0], rax
0x1800351ac  mov     dword ptr [rbp+250h+var_2B0], edi
0x1800351af  mov     dword ptr [rbp+250h+var_2B0+4], esi
0x1800351b2  test    rbx, rbx
0x1800351b5  jz      loc_18003590C
0x1800351bb  cmp     [rbx+4Ch], edx
0x1800351be  jnz     loc_180035487
0x1800351c4  mov     rcx, rbx; this
0x1800351c7  call    ?IsEditSessionRequestCompleted@CContextConnection@@QEBA_NXZ; CContextConnection::IsEditSessionRequestCompleted(void)
0x1800351cc  test    al, al
0x1800351ce  jnz     short loc_1800351E7
0x1800351d0  mov     rax, [rbx+0A0h]
0x1800351d7  cmp     edi, eax
0x1800351d9  jnz     short loc_1800351E7
0x1800351db  shr     rax, 20h
0x1800351df  cmp     esi, eax
0x1800351e1  jz      loc_18003606F
0x1800351e7  xor     esi, esi
0x1800351e9  lea     r9d, [rsi+1]
0x1800351ed  test    rbx, rbx
0x1800351f0  jz      loc_180036089
0x1800351f6  mov     ecx, [rbx+4Ch]
0x1800351f9  jmp     loc_18003608B
0x1800351fe  jz      loc_1800358C2
0x180035204  cmp     ebx, 6Eh ; 'n'
0x180035207  ja      loc_1800354A2
0x18003520d  jz      loc_180035EBE
0x180035213  cmp     ebx, 69h ; 'i'
0x180035216  ja      loc_180035517
0x18003521c  jz      loc_180035AC2
0x180035222  sub     ebx, 29h ; ')'
0x180035225  jz      loc_1800356E9
0x18003522b  sub     ebx, 3Bh ; ';'
0x18003522e  jnz     loc_18003557C
0x180035234  lea     rax, ??_7CMsgDocumentEvent@@6B@; const CMsgDocumentEvent::`vftable'
0x18003523b  mov     qword ptr [rbp+250h+var_2C8], rsi
0x18003523f  mov     [rbp+250h+var_2D0], rax
0x180035243  xor     eax, eax
0x180035245  test    cs:byte_180140041, 4
0x18003524c  mov     qword ptr [rbp+250h+var_2C8+8], rsi
0x180035250  mov     [rbp+250h+var_2B8], esi
0x180035253  mov     [rbp+250h+var_2B4], r9b
0x180035257  mov     [rbp+250h+var_2B0], rax
0x18003525b  mov     [rbp+250h+var_2A8], esi
0x18003525e  mov     qword ptr [rbp+250h+var_2A8+4], rax
0x180035262  mov     qword ptr [rbp+250h+var_2A0+4], rax
0x180035266  mov     qword ptr [rbp+250h+var_298+4], rax
0x18003526a  mov     dword ptr [rbp+250h+var_290+4], 0FFFFFFFFh
0x180035271  jnz     loc_180035C68
0x180035277  lea     rdx, [rbp+250h+var_260]; struct MsgBase *
0x18003527b  lea     rcx, [rbp+250h+var_2D0]; this
0x18003527f  call    ?Read@CMsgDocumentEvent@@UEAAJPEAUMsgBase@@@Z; CMsgDocumentEvent::Read(MsgBase *)
0x180035284  test    eax, eax
0x180035286  js      loc_18003580E
0x18003528c  cmp     dword ptr [rbp+250h+var_2B0+4], esi
0x18003528f  jnz     loc_1800357D5
0x180035295  cmp     [r14+74h], esi
0x180035299  jz      loc_180035806
0x18003529f  lea     rdx, [r14+70h]; struct DOCUMENT_ID *
0x1800352a3  mov     rcx, r14; this
0x1800352a6  call    ?FindDocument@CSharedContext@@AEBAPEAVCSharedDocument@@PEBUDOCUMENT_ID@@@Z; CSharedContext::FindDocument(DOCUMENT_ID const *)
0x1800352ab  test    rax, rax
0x1800352ae  jz      loc_180035806
0x1800352b4  mov     rbx, [rax+30h]
0x1800352b8  jmp     loc_1800359A9
0x1800352bd  mov     rbx, [r14+38h]
0x1800352c1  test    rbx, rbx
0x1800352c4  jz      loc_180035452
0x1800352ca  cmp     [rbx+4Ch], edx
0x1800352cd  jnz     loc_180035490
0x1800352d3  mov     rsi, [rbx+80h]
0x1800352da  test    rsi, rsi
0x1800352dd  jz      loc_180035450
0x1800352e3  mov     rcx, [rbx+58h]; hHandle
0x1800352e7  xor     edx, edx; dwMilliseconds
0x1800352e9  call    cs:__imp_WaitForSingleObject
0x1800352ef  test    eax, eax
0x1800352f1  jz      loc_180035450
0x1800352f7  mov     rcx, rbx; this
0x1800352fa  call    ?IsEditSessionRequestCompleted@CContextConnection@@QEBA_NXZ; CContextConnection::IsEditSessionRequestCompleted(void)
0x1800352ff  test    al, al
0x180035301  jz      loc_180035450
0x180035307  mov     ecx, [rsi+70h]
0x18003530a  cmp     [rbx+0A0h], ecx
0x180035310  jnz     loc_180035450
0x180035316  mov     eax, [rsi+74h]
0x180035319  cmp     [rbx+0A4h], eax
0x18003531f  jnz     loc_180035450
0x180035325  mov     eax, [rbp+250h+var_22C]
0x180035328  mov     [rsi+18h], eax
0x18003532b  mov     rdi, [r14+40h]
0x18003532f  test    rdi, rdi
0x180035332  jz      loc_18003591E
0x180035338  cmp     ecx, [rdi+20h]
0x18003533b  jnz     short loc_180035349
0x18003533d  mov     eax, [rdi+24h]
0x180035340  cmp     [rsi+74h], eax
0x180035343  jz      loc_18003578C
0x180035349  mov     rdi, [rdi+10h]
0x18003534d  jmp     short loc_18003532F
0x18003534f  mov     rsi, [r14+38h]
0x180035353  test    rsi, rsi
0x180035356  jz      loc_180035450
0x18003535c  cmp     [rsi+4Ch], edx
0x18003535f  jnz     loc_180035499
0x180035365  mov     rcx, rsi; this
0x180035368  call    ?IsOutgoingProcessed@CContextConnection@@QEBA_NXZ; CContextConnection::IsOutgoingProcessed(void)
0x18003536d  xor     ecx, ecx
0x18003536f  test    al, al
0x180035371  jnz     loc_180035450
0x180035377  mov     rdi, [rsi+80h]
0x18003537e  test    rdi, rdi
0x180035381  jz      loc_180035441
0x180035387  cmp     [rdi+10h], ebx
0x18003538a  jnz     loc_18003544B
0x180035390  mov     eax, [rbp+250h+var_22C]
0x180035393  mov     [rdi+18h], eax
0x180035396  cmp     [rbp+250h+var_22C], ecx
0x180035399  jl      loc_180035441
0x18003539f  cmp     ebx, 0CBh
0x1800353a5  jz      loc_18003594E
0x1800353ab  cmp     ebx, 0CCh
0x1800353b1  jnz     loc_180035441
0x1800353b7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800353be  lea     rax, ??_7CMsgGetTextProperty@@6B@; const CMsgGetTextProperty::`vftable'
0x1800353c5  mov     qword ptr [rbp+250h+var_2C8], rcx
0x1800353c9  mov     [rbp+250h+var_2D0], rax
0x1800353cd  lea     rdx, [rbp+250h+var_260]; struct MsgBase *
0x1800353d1  xor     eax, eax
0x1800353d3  mov     qword ptr [rbp+250h+var_2C8+8], rcx
0x1800353d7  mov     [rbp+250h+var_2B8], ecx
0x1800353da  xorps   xmm1, xmm1
0x1800353dd  lea     rcx, [rbp+250h+var_2D0]; this
0x1800353e1  mov     [rbp+250h+var_2B0], rax
0x1800353e5  mov     qword ptr [rbp+250h+var_2A8], rax
0x1800353e9  mov     qword ptr [rbp+250h+var_280], rax
0x1800353ed  mov     [rbp+250h+var_2B4], 1
0x1800353f1  movdqu  xmmword ptr [rbp-50h], xmm0
0x1800353f6  movups  xmmword ptr [rbp+250h+var_290], xmm1
0x1800353fa  call    ?Read@CMsgGetTextProperty@@UEAAJPEAUMsgBase@@@Z; CMsgGetTextProperty::Read(MsgBase *)
0x1800353ff  mov     [rdi+18h], eax
0x180035402  test    eax, eax
0x180035404  js      short loc_180035438
0x180035406  mov     rcx, [rdi+78h]
0x18003540a  mov     rax, [rcx]
0x18003540d  mov     rax, [rax+18h]
0x180035411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035416  cmp     [rbp+250h+var_2A8], eax
0x180035419  jnz     short loc_180035438
0x18003541b  mov     rax, [rbp+250h+var_290]
0x18003541f  movups  xmm0, xmmword ptr [rbp+250h+var_288]
0x180035423  mov     [rdi+98h], rax
0x18003542a  xor     eax, eax
0x18003542c  mov     word ptr [rbp+250h+var_290], ax
0x180035430  movdqu  xmmword ptr [rdi+0A0h], xmm0
0x180035438  lea     rcx, [rbp+250h+var_2D0]; this
0x18003543c  call    ??1CMsgGetTextProperty@@UEAA@XZ; CMsgGetTextProperty::~CMsgGetTextProperty(void)
0x180035441  mov     rcx, [rsi+58h]; hEvent
0x180035445  call    cs:__imp_SetEvent
0x18003544b  mov     edi, 2
0x180035450  xor     esi, esi
0x180035452  cmp     r13d, 1
0x180035456  jz      loc_180036126
0x18003545c  test    [rbp+250h+var_238], 4000000h
0x180035463  jz      loc_18003505C
0x180035469  mov     r8, qword ptr [rbp+250h+var_220]
0x18003546d  xor     edx, edx
0x18003546f  mov     rcx, [r14+10h]
0x180035473  call    cs:__imp_NtAlpcDeleteSectionView
0x180035479  btr     [rbp+250h+var_238], 1Ah
0x18003547e  mov     qword ptr [rbp+250h+var_220], rsi
0x180035482  jmp     loc_18003505C
0x180035487  mov     rbx, [rbx+18h]
0x18003548b  jmp     loc_1800351B2
0x180035490  mov     rbx, [rbx+18h]
0x180035494  jmp     loc_1800352C1
0x180035499  mov     rsi, [rsi+18h]
0x18003549d  jmp     loc_180035353
0x1800354a2  mov     eax, ebx
0x1800354a4  sub     eax, 6Fh ; 'o'
0x1800354a7  jz      loc_180035F94
0x1800354ad  sub     eax, r9d
0x1800354b0  jnz     loc_18003582A
0x1800354b6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800354bd  lea     rax, ??_7CMsgTextPropertyChange@@6B@; const CMsgTextPropertyChange::`vftable'
0x1800354c4  mov     qword ptr [rbp+250h+var_2C8], rsi
0x1800354c8  mov     [rbp+250h+var_2D0], rax
0x1800354cc  lea     rdx, [rbp+250h+var_260]; struct MsgBase *
0x1800354d0  xor     eax, eax
0x1800354d2  mov     qword ptr [rbp+250h+var_2C8+8], rsi
0x1800354d6  xorps   xmm1, xmm1
0x1800354d9  mov     [rbp+250h+var_2B0], rax
0x1800354dd  lea     rcx, [rbp+250h+var_2D0]; this
  ... truncated ...
```
