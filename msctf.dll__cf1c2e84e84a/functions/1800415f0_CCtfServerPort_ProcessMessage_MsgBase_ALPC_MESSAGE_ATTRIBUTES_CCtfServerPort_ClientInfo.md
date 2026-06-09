# CCtfServerPort::ProcessMessage(MsgBase * &,_ALPC_MESSAGE_ATTRIBUTES *,CCtfServerPort::ClientInfo *)

- ea: `0x1800415f0`
- end: `0x1800429e0`
- name: `?ProcessMessage@CCtfServerPort@@AEAAJAEAPEAUMsgBase@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@PEAUClientInfo@1@@Z`
- size: `5104`
- prototype: `__int64 __fastcall(CCtfServerPort *__hidden this, struct MsgBase **, struct _ALPC_MESSAGE_ATTRIBUTES *, struct CCtfServerPort::ClientInfo *)`
- caller_count: `1`
- callee_count: `39`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180040760`

## callees

- `0x180011000`
- `0x1800128f8`
- `0x1800250fc`
- `0x180026d28`
- `0x18003a930`
- `0x18003dc3c`
- `0x18003eb70`
- `0x1800415f0`
- `0x180042f94`
- `0x180043100`
- `0x1800432a0`
- `0x180043448`
- `0x18004366c`
- `0x180043760`
- `0x1800438e0`
- `0x180043b68`
- `0x180043bb8`
- `0x180043e10`
- `0x18004f8e0`
- `0x18006a430`
- `0x180071628`
- `0x180076ee4`
- `0x1800771fc`
- `0x18007f390`
- `0x18007fb78`
- `0x180089830`
- `0x18008d588`
- `0x18009eaea`
- `0x18009eb02`
- `0x1800b1c40`
- `0x1800b3060`
- `0x1800b47d8`
- `0x1800b4834`
- `0x1800b4ddc`
- `0x1800b4e30`
- `0x1800b5450`
- `0x1800b5640`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180042880`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180042880`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004235c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800426ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004235c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800426ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042056`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004205f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800423dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042056`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004205f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800423dc`
- `api-ms-win-core-atoms-l1-1-0!GetAtomNameW` at `0x180041d84`
- `api-ms-win-core-atoms-l1-1-0!GetAtomNameW` at `0x180041d84`
- `USER32!GetKeyboardLayoutList` at `0x180041b70`
- `USER32!GetKeyboardLayoutList` at `0x180042371`
- `USER32!GetKeyboardLayoutList` at `0x180041b70`
- `USER32!GetKeyboardLayoutList` at `0x180042371`
- `USER32!PostThreadMessageW` at `0x180042026`
- `USER32!PostThreadMessageW` at `0x180042026`

## pseudocode

```c
__int64 __fastcall CCtfServerPort::ProcessMessage(
        CCtfServerPort *this,
        struct MsgBase **a2,
        struct _ALPC_MESSAGE_ATTRIBUTES *a3,
        struct CCtfServerPort::ClientInfo *a4)
{
  HKL *v4; // r12
  unsigned int v9; // ebx
  unsigned int v10; // r11d
  struct MsgBase *v11; // rbx
  int v12; // r9d
  int v13; // r8d
  int v14; // edx
  _DWORD *v15; // r10
  int v16; // r8d
  int v17; // r9d
  unsigned int v18; // r10d
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rbx
  struct MsgBase *v22; // rax
  int v24; // edx
  int v25; // r8d
  _DWORD *v26; // r9
  struct MsgBase *v27; // rdx
  __int64 v28; // rbx
  CCtfServerPort::ClientInfo *v29; // rcx
  int v30; // edx
  struct MsgBase *v31; // r13
  struct MsgBase *v32; // rcx
  int v33; // ecx
  unsigned int v34; // r15d
  unsigned int v35; // r13d
  int KeyboardLayoutList; // eax
  unsigned __int64 v37; // r8
  int v38; // ebx
  int v39; // r14d
  int v40; // edx
  unsigned int *v41; // rax
  unsigned int v42; // r8d
  struct MsgBase *v43; // rcx
  int v44; // ecx
  struct MsgBase *v45; // rax
  int v46; // r14d
  GUID v47; // xmm6
  ATOM v48; // bx
  int v49; // r15d
  GUID v50; // xmm7
  int v51; // edx
  int v52; // ecx
  unsigned __int64 v53; // r9
  unsigned __int64 v54; // xmm0_8
  char *v55; // rbx
  char *v56; // rax
  unsigned __int64 v57; // rax
  unsigned __int64 v58; // rax
  __int64 v59; // rcx
  unsigned int ProfileAtomId; // ebx
  unsigned int *v61; // rax
  struct MsgBase *v62; // rdx
  unsigned int v63; // edx
  CCtfServerPort::ClientInfo *v64; // rcx
  struct MsgBase *v65; // rbx
  unsigned int v66; // eax
  void *v67; // rcx
  int v68; // edx
  int v69; // ecx
  int v70; // ecx
  struct MsgBase *v71; // rcx
  int v72; // ecx
  int v73; // ecx
  struct MsgBase *v74; // rdx
  HWND v75; // rbx
  int v76; // ecx
  unsigned int v77; // eax
  HKL *v78; // rax
  int i; // ecx
  struct MsgBase *v80; // rdx
  int v81; // ecx
  __int64 j; // r14
  char v83; // bl
  bool active; // al
  struct MsgBase *v85; // rdx
  int v86; // ebx
  int v87; // r12d
  int v88; // r13d
  _DWORD *v89; // rax
  int v90; // edx
  struct CCtfServerPort::ClientInfo *v91; // r9
  struct CCtfServerPort::ClientInfo *v92; // r9
  struct MsgBase *v93; // rcx
  __int64 v94; // rax
  unsigned __int64 m; // rcx
  unsigned int v96; // eax
  HWND v97; // rax
  __int64 v98; // r11
  unsigned int n; // ecx
  unsigned int v100; // edx
  unsigned int v101; // ebx
  int v102; // ecx
  struct MsgBase *v103; // rdx
  unsigned int v104; // r12d
  struct CCtfServerPort::ClientInfo *v105; // rbx
  __int64 k; // r14
  char v107; // bl
  bool v108; // al
  unsigned int v109; // edx
  struct CCtfServerPort::DocumentInfo *Document; // rax
  struct CCtfServerPort::DocumentInfo *v111; // rbx
  int nBuff[2]; // [rsp+38h] [rbp-D0h] BYREF
  HWND v113; // [rsp+40h] [rbp-C8h] BYREF
  HWND *Buf1; // [rsp+48h] [rbp-C0h] BYREF
  GUID Buf1_8; // [rsp+50h] [rbp-B8h] BYREF
  GUID v116; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v117[3]; // [rsp+70h] [rbp-98h] BYREF
  __int128 v118; // [rsp+88h] [rbp-80h]
  __int64 v119; // [rsp+98h] [rbp-70h]
  WCHAR Buffer[4]; // [rsp+A8h] [rbp-60h] BYREF
  GUID *p_Buf1_8; // [rsp+B0h] [rbp-58h]
  unsigned __int16 v122[4]; // [rsp+B8h] [rbp-50h] BYREF
  int v123; // [rsp+C0h] [rbp-48h]
  char v124; // [rsp+C4h] [rbp-44h]
  _BYTE v125[40]; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v126; // [rsp+F0h] [rbp-18h]
  int v127; // [rsp+F8h] [rbp-10h]
  int *p_Buf1; // [rsp+100h] [rbp-8h]
  unsigned __int16 v129[4]; // [rsp+108h] [rbp+0h] BYREF
  int v130; // [rsp+110h] [rbp+8h]
  int v131; // [rsp+118h] [rbp+10h]
  GUID *v132; // [rsp+120h] [rbp+18h]
  __int64 v133; // [rsp+128h] [rbp+20h]
  int v134; // [rsp+130h] [rbp+28h]
  int *v135; // [rsp+138h] [rbp+30h]
  int *v136; // [rsp+140h] [rbp+38h]
  int v137; // [rsp+148h] [rbp+40h]

  v4 = 0;
  *((_DWORD *)*a2 + 13) = 0;
  v9 = *((_DWORD *)*a2 + 10) & 0xFFFFF;
  if ( v9 >= 0xC8 )
  {
    if ( v9 <= 0xDC
      && !(*(unsigned __int8 (__fastcall **)(struct CCtfServerPort::ClientInfo *))(*(_QWORD *)a4 + 8LL))(a4) )
    {
      *((_DWORD *)*a2 + 13) = -2147467259;
      return *((unsigned int *)*a2 + 13);
    }
LABEL_28:
    switch ( v9 )
    {
      case 1u:
        *((_DWORD *)*a2 + 14) = 0;
        goto LABEL_36;
      case 4u:
        v43 = *a2;
        v113 = (HWND)&nBuff[1];
        nBuff[1] = 0;
        p_Buf1_8 = &Buf1_8;
        nBuff[0] = 1;
        *(_QWORD *)v125 = nBuff;
        wcscpy(Buffer, L"\x01");
        *(_QWORD *)&v125[8] = nBuff;
        *(_QWORD *)&v125[32] = &v113;
        p_Buf1 = nBuff;
        *(_QWORD *)v129 = nBuff;
        Buf1_8 = 0;
        *(_QWORD *)v122 = 0;
        v123 = 16;
        *(_DWORD *)&v125[16] = 0;
        *(_DWORD *)&v125[24] = 518;
        v126 = 0;
        v127 = 4;
        v130 = 0;
        *((_DWORD *)*a2 + 13) = MsgBase::Unmarshal(v43, 2u, (struct tagCPROXY_PARAM *)Buffer);
        if ( *((int *)*a2 + 13) >= 0 )
        {
          nBuff[1] = CGCompartList::FindProperty((CCtfServerPort *)((char *)this + 64), &Buf1_8, 0);
          v44 = 0;
          if ( nBuff[1] == -1 )
            v44 = -2147467259;
          *((_DWORD *)*a2 + 13) = v44;
          if ( *((int *)*a2 + 13) >= 0 )
          {
            v69 = MsgBase::PrepareToReply(a2, 2u, (struct tagCPROXY_PARAM *)Buffer);
            if ( v69 < 0 || (v69 = MsgBase::Marshal(*a2, 2u, (struct tagCPROXY_PARAM *)Buffer), v69 < 0) )
              *((_DWORD *)*a2 + 13) = v69;
          }
        }
        goto LABEL_206;
      case 5u:
        v32 = *a2;
        *(_QWORD *)&Buf1_8.Data1 = &nBuff[1];
        nBuff[1] = 0;
        Buf1 = &v113;
        v113 = 0;
        p_Buf1_8 = &v116;
        nBuff[0] = 1;
        *(_QWORD *)v125 = nBuff;
        *(_QWORD *)&v125[8] = nBuff;
        *(_QWORD *)&v125[32] = &Buf1;
        p_Buf1 = nBuff;
        *(_QWORD *)v129 = nBuff;
        v132 = &Buf1_8;
        v135 = nBuff;
        v136 = nBuff;
        v116 = 0;
        wcscpy(Buffer, L"\x01");
        *(_QWORD *)v122 = 0;
        v123 = 16;
        *(_DWORD *)&v125[16] = 0;
        *(_DWORD *)&v125[24] = 16390;
        v126 = 0;
        v127 = 8;
        v130 = 0;
        v131 = 518;
        v133 = 0;
        v134 = 4;
        v137 = 0;
        *((_DWORD *)*a2 + 13) = MsgBase::Unmarshal(v32, 3u, (struct tagCPROXY_PARAM *)Buffer);
        if ( *((int *)*a2 + 13) >= 0 )
        {
          nBuff[1] = CGCompartList::GetProperty(
                       (CCtfServerPort *)((char *)this + 64),
                       &v116,
                       (struct tagTFGLOBALPROPERTY *)&v113);
          v33 = 0;
          if ( nBuff[1] == -1 )
            v33 = -2147467259;
          *((_DWORD *)*a2 + 13) = v33;
          if ( *((int *)*a2 + 13) >= 0 )
          {
            v70 = MsgBase::PrepareToReply(a2, 3u, (struct tagCPROXY_PARAM *)Buffer);
            if ( v70 < 0 || (v70 = MsgBase::Marshal(*a2, 3u, (struct tagCPROXY_PARAM *)Buffer), v70 < 0) )
              *((_DWORD *)*a2 + 13) = v70;
          }
        }
        goto LABEL_144;
      case 6u:
        v71 = *a2;
        *(_QWORD *)&Buf1_8.Data1 = &nBuff[1];
        v113 = 0;
        p_Buf1_8 = &v116;
        nBuff[1] = 0;
        *(_QWORD *)v125 = nBuff;
        nBuff[0] = 1;
        *(_QWORD *)&v125[8] = nBuff;
        *(_QWORD *)&v125[32] = &v113;
        p_Buf1 = nBuff;
        *(_QWORD *)v129 = nBuff;
        v132 = &Buf1_8;
        v135 = nBuff;
        v136 = nBuff;
        v116 = 0;
        wcscpy(Buffer, L"\x01");
        *(_QWORD *)v122 = 0;
        v123 = 16;
        *(_DWORD *)&v125[16] = 0;
        *(_DWORD *)&v125[24] = 16385;
        v126 = 0;
        v127 = 8;
        v130 = 0;
        v131 = 518;
        v133 = 0;
        v134 = 4;
        v137 = 0;
        *((_DWORD *)*a2 + 13) = MsgBase::Unmarshal(v71, 3u, (struct tagCPROXY_PARAM *)Buffer);
        if ( *((int *)*a2 + 13) >= 0 )
        {
          nBuff[1] = CGCompartList::SetProperty(
                       (CCtfServerPort *)((char *)this + 64),
                       &v116,
                       (const struct tagTFGLOBALPROPERTY *)&v113);
          v72 = 0;
          if ( nBuff[1] == -1 )
            v72 = -2147467259;
          *((_DWORD *)*a2 + 13) = v72;
          if ( *((int *)*a2 + 13) >= 0 )
          {
            v73 = MsgBase::PrepareToReply(a2, 3u, (struct tagCPROXY_PARAM *)Buffer);
            if ( v73 < 0 || (v73 = MsgBase::Marshal(*a2, 3u, (struct tagCPROXY_PARAM *)Buffer), v73 < 0) )
              *((_DWORD *)*a2 + 13) = v73;
          }
        }
LABEL_144:
        CleanUpAutoParams(3u, (struct tagCPROXY_PARAM *)Buffer);
        return *((unsigned int *)*a2 + 13);
      case 0x15u:
        *((_DWORD *)*a2 + 14) = *((_DWORD *)this + 36);
        *((_DWORD *)*a2 + 15) = *((_DWORD *)this + 35);
        goto LABEL_19;
      case 0x16u:
        *((_DWORD *)this + 36) |= *((_DWORD *)*a2 + 14);
        *((_DWORD *)this + 36) &= ~*((_DWORD *)*a2 + 15);
        goto LABEL_19;
      case 0x1Au:
        *((_DWORD *)*a2 + 14) &= ~*((_DWORD *)*a2 + 15);
        *((_DWORD *)a4 + 7) |= *((_DWORD *)*a2 + 14);
        *((_DWORD *)a4 + 7) &= ~*((_DWORD *)*a2 + 15);
        goto LABEL_19;
      case 0x20u:
        v74 = *a2;
        v113 = 0;
        CCtfServerPort::FindClientByThreadId(this, *((_DWORD *)v74 + 14), (struct CCtfServerPort::ClientInfo **)&v113);
        v75 = v113;
        if ( !v113 || (*(unsigned __int8 (__fastcall **)(HWND))(*(_QWORD *)v113 + 8LL))(v113) )
          v76 = 0;
        else
          v76 = *((_DWORD *)v75 + 12);
        *((_DWORD *)*a2 + 15) = v76;
        goto LABEL_19;
      case 0x21u:
        *((_DWORD *)a4 + 12) = *((_DWORD *)*a2 + 14);
        goto LABEL_36;
      case 0x22u:
        v45 = *a2;
        v46 = *((_DWORD *)*a2 + 16);
        if ( !v46 )
          goto LABEL_94;
        v47 = GUID_NULL;
        v48 = *((_WORD *)v45 + 30);
        v49 = *((_DWORD *)v45 + 14);
        v50 = GUID_NULL;
        Buf1_8 = GUID_NULL;
        v116 = GUID_NULL;
        if ( v48 )
        {
          memset_0(Buffer, 0, 0xAEu);
          if ( GetAtomNameW(v48, Buffer, 87) == 86 )
          {
            StringToCLSID(v129, &v116);
            HIWORD(p_Buf1) = 0;
            StringToCLSID(&v122[1], &Buf1_8);
            v47 = Buf1_8;
            v50 = v116;
          }
          if ( !memcmp_0(&Buf1_8, &GUID_NULL, 0x10u) )
            return *((unsigned int *)*a2 + 13);
        }
        v51 = *((_DWORD *)this + 46);
        if ( v51 <= 0 )
          goto LABEL_89;
        v52 = 0;
        v53 = _mm_srli_si128((__m128i)v47, 8).m128i_u64[0];
        v54 = _mm_srli_si128((__m128i)v50, 8).m128i_u64[0];
        while ( 1 )
        {
          v55 = (char *)(*((_QWORD *)this + 22) + *((_DWORD *)this + 47) * v52);
          if ( *(_DWORD *)v55 == v49 )
          {
            v57 = *(_QWORD *)(v55 + 4) - *(_QWORD *)&v47.Data1;
            if ( !v57 )
              v57 = *(_QWORD *)(v55 + 12) - v53;
            if ( !v57 )
            {
              v58 = *(_QWORD *)(v55 + 20) - *(_QWORD *)&v50.Data1;
              if ( !v58 )
                v58 = *(_QWORD *)(v55 + 28) - v54;
              if ( !v58 )
                break;
            }
          }
          if ( ++v52 >= v51 )
          {
LABEL_89:
            v56 = (char *)CVoidStructArray::Append((CCtfServerPort *)((char *)this + 168), 1);
            v55 = v56;
            if ( !v56 )
              return *((unsigned int *)*a2 + 13);
            *(_DWORD *)v56 = v49;
            *(GUID *)(v56 + 4) = v47;
            *((_DWORD *)v56 + 9) = 0;
            *(GUID *)(v56 + 20) = v50;
            break;
          }
        }
        if ( *((_DWORD *)v55 + 9) > (unsigned int)(v46 + *((_DWORD *)v55 + 9)) )
          CCtfServerPort::SubmitTelemetryData(this, 0);
        *((_DWORD *)v55 + 9) += v46;
LABEL_94:
        *((_DWORD *)*a2 + 10) &= ~0x4000000u;
        *((_DWORD *)*a2 + 17) = 0;
        return *((unsigned int *)*a2 + 13);
      case 0x23u:
        v24 = 0;
        v25 = *((_DWORD *)*a2 + 14);
        *((_DWORD *)*a2 + 13) = -2147467259;
        *((_DWORD *)*a2 + 15) = 0;
        *((_DWORD *)*a2 + 16) = 0;
        while ( 2 )
        {
          if ( v24 < *((_DWORD *)this + 54) )
          {
            v26 = (_DWORD *)(*((_QWORD *)this + 26) + *((_DWORD *)this + 55) * v24);
            if ( *v26 != v25 )
            {
              ++v24;
              continue;
            }
            *((_DWORD *)*a2 + 15) = v26[1];
            *((_DWORD *)*a2 + 16) = v26[2];
            *((_DWORD *)*a2 + 13) = 0;
          }
          break;
        }
        goto LABEL_20;
      case 0x24u:
        v34 = *((_DWORD *)*a2 + 14);
        v35 = *((_DWORD *)*a2 + 15);
        nBuff[1] = *((_DWORD *)*a2 + 16);
        KeyboardLayoutList = GetKeyboardLayoutList(0, 0);
        v37 = KeyboardLayoutList;
        v38 = -1;
        nBuff[0] = KeyboardLayoutList;
        if ( KeyboardLayoutList < *((_DWORD *)this + 54) )
        {
          v77 = 8 * KeyboardLayoutList;
          if ( !is_mul_ok(v37, 8u) )
            v77 = -1;
          v78 = (HKL *)LocalAlloc(0x40u, v77);
          v4 = v78;
          if ( v78 )
          {
            LODWORD(v37) = GetKeyboardLayoutList(nBuff[0], v78);
            nBuff[0] = v37;
          }
          else
          {
            LODWORD(v37) = nBuff[0];
          }
        }
        v39 = *((_DWORD *)this + 54) - 1;
        if ( v39 < 0 )
          goto LABEL_66;
        do
        {
          v40 = *(_DWORD *)(*((_DWORD *)this + 55) * v39 + *((_QWORD *)this + 26));
          if ( v40 == v34 )
          {
            v38 = v39;
            if ( !v4 )
              break;
          }
          else if ( v4 )
          {
            for ( i = 0; i < (int)v37; ++i )
            {
              if ( LOWORD(v4[i]) == (_WORD)v40 )
                goto LABEL_97;
            }
            CVoidStructArray::Remove((CCtfServerPort *)((char *)this + 200), v39, 1);
            LODWORD(v37) = nBuff[0];
            if ( v38 > v39 )
              --v38;
          }
LABEL_97:
          --v39;
        }
        while ( v39 >= 0 );
LABEL_66:
        if ( v38 == -1 )
          v41 = (unsigned int *)CVoidStructArray::Append((CCtfServerPort *)((char *)this + 200), 1);
        else
          v41 = (unsigned int *)(*((_QWORD *)this + 26) + *((_DWORD *)this + 55) * v38);
        if ( v41 )
        {
          v42 = nBuff[1];
          v41[2] = nBuff[1];
          *v41 = v34;
          v41[1] = v35;
          CtfTraceLoggingTelemetry::ActiveKeyboardProfileSet(v34, v35, v42);
        }
        if ( v4 )
          LocalFree(v4);
        *((_DWORD *)*a2 + 17) = 0;
        goto LABEL_21;
      case 0x29u:
        if ( a4 == *((struct CCtfServerPort::ClientInfo **)this + 16) )
        {
          v80 = *a2;
          v81 = *((_DWORD *)*a2 + 10);
          if ( (v81 & 0x50000000) != 0 )
          {
            LODWORD(v118) = 0;
            BYTE4(v118) = 1;
            v117[0] = &CMsgThreadActiveProfiles::`vftable';
            *((_QWORD *)&v118 + 1) = 0;
            LODWORD(v119) = 0;
            *(_OWORD *)&v117[1] = 0;
            if ( (v81 & 0x40000000) != 0 || CMsgThreadActiveProfiles::Read((CMsgThreadActiveProfiles *)v117, v80) >= 0 )
            {
              for ( j = *((_QWORD *)this + 14); j; j = *(_QWORD *)(j + 88) )
              {
                v83 = *(_BYTE *)(j + 104);
                active = CCtfServerPort::ImeServerInfo::SetActiveProfiles(
                           (CCtfServerPort::ImeServerInfo *)j,
                           (const struct CMsgThreadActiveProfiles *)v117);
                if ( v83 || active )
                  CCtfServerPort::ForwardMessage(this, *a2, a3, (struct CCtfServerPort::ClientInfo *)j);
              }
            }
            CMsgThreadActiveProfiles::~CMsgThreadActiveProfiles((CMsgThreadActiveProfiles *)v117);
          }
        }
        *((_DWORD *)*a2 + 14) = 0;
        *((_DWORD *)*a2 + 15) = 0;
        *((_DWORD *)*a2 + 16) = 0;
        *((_DWORD *)*a2 + 17) = 0;
        return *((unsigned int *)*a2 + 13);
      case 0x38u:
        *((_DWORD *)*a2 + 14) = GetCurrentProcessId();
        goto LABEL_36;
      case 0x64u:
        v27 = *a2;
        *(_QWORD *)Buffer = &CMsgDocumentEvent::`vftable';
        p_Buf1_8 = 0;
        memset(v125, 0, 36);
        *(_QWORD *)v122 = 0;
        v123 = 0;
        v124 = 1;
        *(_DWORD *)&v125[36] = -1;
        if ( CMsgDocumentEvent::Read((CMsgDocumentEvent *)Buffer, v27) < 0 )
          goto LABEL_47;
        if ( a4 == *((struct CCtfServerPort::ClientInfo **)this + 16) && !*((_BYTE *)this + 120) )
          goto LABEL_42;
        if ( !*(_DWORD *)&v125[4] )
          goto LABEL_47;
        v113 = 0;
        nBuff[1] = 0;
        GetActiveThreadInfo((unsigned int *)&nBuff[1], &v113, 0);
        if ( !v113 || *((_DWORD *)a4 + 5) != nBuff[1] )
          goto LABEL_47;
        *((_QWORD *)this + 16) = a4;
        v30 = 0;
        while ( 2 )
        {
          if ( v30 < *((_DWORD *)a4 + 18) )
          {
            v31 = *(struct MsgBase **)(*((_QWORD *)a4 + 8) + 8LL * v30);
            if ( (*((_DWORD *)v31 + 10) & 0xFFFFF) != 0x29 )
            {
              ++v30;
              continue;
            }
            LODWORD(v118) = 0;
            BYTE4(v118) = 1;
            v117[0] = &CMsgThreadActiveProfiles::`vftable';
            *((_QWORD *)&v118 + 1) = 0;
            *(_OWORD *)&v117[1] = 0;
            LODWORD(v119) = 0;
            if ( CMsgThreadActiveProfiles::Read((CMsgThreadActiveProfiles *)v117, v31) >= 0 )
            {
              for ( k = *((_QWORD *)this + 14); k; k = *(_QWORD *)(k + 88) )
              {
                v107 = *(_BYTE *)(k + 104);
                v108 = CCtfServerPort::ImeServerInfo::SetActiveProfiles(
                         (CCtfServerPort::ImeServerInfo *)k,
                         (const struct CMsgThreadActiveProfiles *)v117);
                if ( v107 || v108 )
                  CCtfServerPort::ForwardMessage(this, v31, 0, (struct CCtfServerPort::ClientInfo *)k);
              }
              if ( !*((_QWORD *)this + 14) )
              {
                *((_BYTE *)this + 120) = 0;
                if ( *((_QWORD *)this + 12) )
                  PostThreadMessageW(*((_DWORD *)this + 26), g_msgPrivate, 0x1Du, 0);
              }
            }
            CMsgThreadActiveProfiles::~CMsgThreadActiveProfiles((CMsgThreadActiveProfiles *)v117);
          }
          break;
        }
LABEL_42:
        v28 = *((_QWORD *)this + 14);
        for ( *((_DWORD *)this + 34) = *(_DWORD *)&v125[4]; v28; v28 = *(_QWORD *)(v28 + 88) )
        {
          if ( *(_BYTE *)(v28 + 104) )
          {
            CCtfServerPort::ForwardMessage(this, *a2, a3, (struct CCtfServerPort::ClientInfo *)v28);
            v29 = (CCtfServerPort::ClientInfo *)*((_QWORD *)this + 16);
            if ( v29 )
              CCtfServerPort::ClientInfo::AddDocumentReference(
                v29,
                *((_DWORD *)this + 34),
                (struct CCtfServerPort::ImeServerInfo *)v28);
          }
        }
LABEL_47:
        CMsgDocumentEvent::~CMsgDocumentEvent((CMsgDocumentEvent *)Buffer);
        return *((unsigned int *)*a2 + 13);
      case 0x66u:
        v109 = *((_DWORD *)*a2 + 15);
        if ( *((struct CCtfServerPort::ClientInfo **)this + 16) == a4 && *((_DWORD *)this + 34) == v109 )
        {
          *((_QWORD *)this + 16) = 0;
          *((_DWORD *)this + 34) = 0;
        }
        Document = CCtfServerPort::ClientInfo::GetDocument(a4, v109, 1);
        v111 = Document;
        if ( Document )
        {
          CCtfServerPort::ForwardMessageToDocumentImes(this, *a2, a3, Document);
          v67 = (void *)*((_QWORD *)v111 + 4);
          *((_QWORD *)v111 + 3) = &CStructArray<char>::`vftable';
          if ( v67 )
            LocalFree(v67);
          LocalFree(v111);
        }
        goto LABEL_21;
      case 0x77u:
        v93 = *a2;
        v117[0] = nBuff;
        nBuff[0] = 0;
        p_Buf1_8 = (GUID *)v117;
        v113 = 0;
        *(_QWORD *)v125 = &nBuff[1];
        nBuff[1] = 1;
        *(_QWORD *)&v125[8] = &nBuff[1];
        LODWORD(Buf1) = 0;
        *(_QWORD *)&v125[32] = &v113;
        p_Buf1 = (int *)&Buf1;
        *(_QWORD *)v129 = nBuff;
        *(_OWORD *)&v117[1] = 0;
        v119 = 0;
        v118 = 0;
        wcscpy(Buffer, L"Ȇ");
        *(_QWORD *)v122 = 0;
        v123 = 4;
        *(_DWORD *)&v125[16] = 0;
        *(_DWORD *)&v125[24] = 38;
        v126 = 0;
        v127 = 16;
        v130 = 0;
        *((_DWORD *)*a2 + 13) = MsgBase::Unmarshal(v93, 2u, (struct tagCPROXY_PARAM *)Buffer);
        if ( *((int *)*a2 + 13) >= 0 )
        {
          v94 = *((_QWORD *)this + 14);
          for ( m = (unsigned int)nBuff[0]; v94; v94 = *(_QWORD *)(v94 + 88) )
          {
            if ( *(_BYTE *)(v94 + 104) )
            {
              m = (unsigned int)(*(_DWORD *)(v94 + 160) + m);
              nBuff[0] = m;
            }
          }
          if ( (_DWORD)m )
          {
            v96 = 16 * m;
            if ( !is_mul_ok(m, 0x10u) )
              v96 = -1;
            v97 = (HWND)LocalAlloc(0x40u, v96);
            v113 = v97;
            if ( v97 )
            {
              v98 = *((_QWORD *)this + 14);
              for ( n = 0; v98; v98 = *(_QWORD *)(v98 + 88) )
              {
                if ( *(_BYTE *)(v98 + 104) )
                {
                  v100 = *(_DWORD *)(v98 + 160);
                  v101 = n + v100;
                  if ( n + v100 > n && v101 <= nBuff[0] )
                  {
                    CCtfServerPort::ImeServerInfo::GetHotkeys(
                      (CCtfServerPort::ImeServerInfo *)v98,
                      v100,
                      (struct TIP_HOTKEY *)(v97 + 4 * n));
                    v97 = v113;
                    n = v101;
                  }
                }
              }
            }
          }
          if ( *((int *)*a2 + 13) >= 0 )
          {
            v102 = MsgBase::PrepareToReply(a2, 2u, (struct tagCPROXY_PARAM *)Buffer);
            if ( v102 < 0 || (v102 = MsgBase::Marshal(*a2, 2u, (struct tagCPROXY_PARAM *)Buffer), v102 < 0) )
              *((_DWORD *)*a2 + 13) = v102;
          }
        }
LABEL_206:
        CleanUpAutoParams(2u, (struct tagCPROXY_PARAM *)Buffer);
        return *((unsigned int *)*a2 + 13);
      case 0xC8u:
        v85 = *a2;
        p_Buf1_8 = 0;
        memset(v125, 0, 34);
        *(_QWORD *)v122 = 0;
        v123 = 200;
        v124 = 1;
        *(_QWORD *)Buffer = &CMsgRegisterInputProviderContext::`vftable';
        *(_DWORD *)&v125[36] = 0;
        if ( CMsgRegisterInputProviderContext::Read((CMsgRegisterInputProviderContext *)Buffer, v85) < 0 )
          goto LABEL_119;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InputSupportForBcp47>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InputSupportForBcp47>::GetImpl'::`2'::impl) )
        {
          v59 = *((_QWORD *)this + 12);
          if ( !v59 )
            goto LABEL_118;
          ProfileAtomId = (*(__int64 (__fastcall **)(__int64, _BYTE *, _BYTE *, _QWORD))(*(_QWORD *)v59 + 40LL))(
                            v59,
                            v125,
                            &v125[16],
                            *(unsigned __int16 *)&v125[32]);
        }
        else
        {
          ProfileAtomId = CInputProfileAtoms::GetProfileAtomId(
                            (const struct _GUID *)v125,
                            (const struct _GUID *)&v125[16],
                            *(unsigned __int16 *)&v125[32],
                            0);
        }
        if ( ProfileAtomId )
        {
          if ( !CCtfServerPort::FindImeContextOwner(this, ProfileAtomId) )
          {
            v61 = (unsigned int *)CVoidStructArray::Append((struct CCtfServerPort::ClientInfo *)((char *)a4 + 112), 1);
            if ( v61 )
            {
              *v61 = ProfileAtomId;
              v62 = *a2;
              *(_DWORD *)&v125[36] = ProfileAtomId;
              CMsgRegisterInputProviderContext::WriteReply((CMsgRegisterInputProviderContext *)Buffer, v62);
              v64 = (CCtfServerPort::ClientInfo *)*((_QWORD *)this + 16);
              v113 = 0;
              if ( v64 && CCtfServerPort::ClientInfo::FindCachedMessage(v64, v63, (struct MsgBase **)&v113) )
              {
                v65 = (struct MsgBase *)v113;
                LODWORD(v118) = 0;
                BYTE4(v118) = 1;
                v117[0] = &CMsgThreadActiveProfiles::`vftable';
                *(_OWORD *)&v117[1] = 0;
                *((_QWORD *)&v118 + 1) = 0;
                LODWORD(v119) = 0;
                if ( CMsgThreadActiveProfiles::Read((CMsgThreadActiveProfiles *)v117, (struct MsgBase *)v113) >= 0
                  && CCtfServerPort::ImeServerInfo::SetActiveProfiles(a4, (const struct CMsgThreadActiveProfiles *)v117) )
                {
                  CCtfServerPort::ForwardMessage(this, v65, 0, a4);
                  v66 = *((_DWORD *)this + 34);
                  if ( v66 )
                    CCtfServerPort::ClientInfo::PostMessageW(
                      *((CCtfServerPort::ClientInfo **)this + 16),
                      g_msgPrivate,
                      0xEu,
                      v66);
                }
                CMsgThreadActiveProfiles::~CMsgThreadActiveProfiles((CMsgThreadActiveProfiles *)v117);
              }
LABEL_119:
              CMsgRegisterInputProviderContext::~CMsgRegisterInputProviderContext((CMsgRegisterInputProviderContext *)Buffer);
              return *((unsigned int *)*a2 + 13);
            }
          }
        }
LABEL_118:
        *((_DWORD *)*a2 + 13) = -2147467259;
        goto LABEL_119;
      case 0xC9u:
        v68 = 0;
        while ( 2 )
        {
          if ( v68 < *((_DWORD *)a4 + 32) )
          {
            if ( *(_DWORD *)(*((_DWORD *)a4 + 33) * v68 + *((_QWORD *)a4 + 15)) != *((_DWORD *)*a2 + 14) )
            {
              ++v68;
              continue;
            }
            CVoidStructArray::Remove((struct CCtfServerPort::ClientInfo *)((char *)a4 + 112), v68, 1);
          }
          break;
        }
        goto LABEL_36;
      case 0xCAu:
        v103 = *a2;
        v113 = 0;
        v104 = *((_DWORD *)v103 + 15);
        CCtfServerPort::FindClientByThreadId(this, *((_DWORD *)v103 + 14), (struct CCtfServerPort::ClientInfo **)&v113);
        v105 = (struct CCtfServerPort::ClientInfo *)v113;
        if ( v113 && CCtfServerPort::ClientInfo::ReleaseDocumentReference((CCtfServerPort::ClientInfo *)v113, v104, a4) )
          CCtfServerPort::ForwardMessage(this, *a2, a3, v105);
        *((_DWORD *)*a2 + 14) = 0;
        *((_DWORD *)*a2 + 15) = 0;
        *((_DWORD *)*a2 + 16) = 0;
        *((_DWORD *)*a2 + 17) = 0;
        goto LABEL_21;
      case 0xDBu:
        if ( (*(unsigned __int8 (__fastcall **)(struct CCtfServerPort::ClientInfo *))(*(_QWORD *)a4 + 8LL))(a4) )
        {
          v86 = *((_DWORD *)*a2 + 14);
          v87 = *((_DWORD *)*a2 + 15);
          v88 = *((_DWORD *)*a2 + 16);
          nBuff[1] = *((_DWORD *)*a2 + 17);
          v89 = CVoidStructArray::Append((struct CCtfServerPort::ClientInfo *)((char *)a4 + 144), 1);
          if ( v89 )
          {
            v90 = 0;
            v89[3] = nBuff[1];
            *v89 = v86;
            v89[1] = v87;
            v89[2] = v88;
          }
          else
          {
            v90 = -2147467259;
          }
          *((_DWORD *)*a2 + 13) = v90;
          if ( *((int *)*a2 + 13) >= 0 )
          {
            v91 = (struct CCtfServerPort::ClientInfo *)*((_QWORD *)this + 16);
            if ( v91 )
              CCtfServerPort::ForwardMessage(this, *a2, a3, v91);
          }
        }
        goto LABEL_21;
      case 0xDCu:
        if ( (*(unsigned __int8 (__fastcall **)(struct CCtfServerPort::ClientInfo *))(*(_QWORD *)a4 + 8LL))(a4) )
        {
          CCtfServerPort::ImeServerInfo::RemoveHotkey(a4, 0, *((_DWORD *)*a2 + 14));
          v92 = (struct CCtfServerPort::ClientInfo *)*((_QWORD *)this + 16);
          if ( v92 )
            CCtfServerPort::ForwardMessage(this, *a2, a3, v92);
        }
        goto LABEL_36;
      default:
        *((_DWORD *)*a2 + 13) = -2147467259;
        *((_DWORD *)*a2 + 14) = 0;
        goto LABEL_36;
    }
  }
  if ( v9 == 27 )
  {
    v16 = 0;
    v17 = *((_DWORD *)this + 14);
    v18 = *((_DWORD *)*a2 + 14);
    while ( v16 < v17 )
    {
      v19 = *((_QWORD *)this + 6);
      v20 = (v17 + v16) >> 1;
      v21 = *(_QWORD *)(v19 + 8LL * v20);
      if ( *(_DWORD *)(v21 + 20) > v18 )
      {
        v17 = (v17 + v16) >> 1;
      }
      else
      {
        if ( *(_DWORD *)(v21 + 20) >= v18 )
        {
          if ( (*(_BYTE *)(v21 + 28) & 8) != 0
            && !(*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v21 + 8LL))(*(_QWORD *)(v19 + 8LL * v20)) )
          {
            *((_DWORD *)*a2 + 14) = *(_DWORD *)(v21 + 32);
            *((_DWORD *)*a2 + 15) = *(_DWORD *)(v21 + 36);
            goto LABEL_19;
          }
          break;
        }
        v16 = v20 + 1;
      }
    }
    *((_DWORD *)*a2 + 14) = 16;
LABEL_36:
    *((_DWORD *)*a2 + 15) = 0;
LABEL_19:
    *((_DWORD *)*a2 + 16) = 0;
LABEL_20:
    *((_DWORD *)*a2 + 17) = 0;
LABEL_21:
    v22 = *a2;
    goto LABEL_22;
  }
  if ( v9 != 25 )
  {
    if ( v9 == 28 )
    {
      *((_DWORD *)a4 + 8) = *((_DWORD *)*a2 + 14);
      *((_DWORD *)a4 + 9) = *((_DWORD *)*a2 + 15);
      *((_DWORD *)*a2 + 16) = 0;
      *((_DWORD *)*a2 + 17) = 0;
      v22 = *a2;
LABEL_22:
      *((_DWORD *)v22 + 10) &= ~0x4000000u;
      return *((unsigned int *)*a2 + 13);
    }
    goto LABEL_28;
  }
  v10 = *((_DWORD *)*a2 + 14);
  v11 = *a2;
  v12 = *((_DWORD *)this + 14);
  v13 = 0;
  while ( v13 < v12 )
  {
    v14 = (v12 + v13) >> 1;
    v15 = *(_DWORD **)(*((_QWORD *)this + 6) + 8LL * v14);
    if ( v15[5] > v10 )
    {
      v12 = (v12 + v13) >> 1;
    }
    else
    {
      if ( v15[5] >= v10 )
      {
        *((_DWORD *)v11 + 14) = v15[7];
        *((_DWORD *)*a2 + 15) = v15[4];
        *((_DWORD *)*a2 + 16) = v15[6];
        goto LABEL_20;
      }
      v13 = v14 + 1;
    }
  }
  *((_DWORD *)v11 + 13) = -2147467259;
  return *((unsigned int *)*a2 + 13);
}

```

## disassembly

```asm
0x1800415f0  mov     rax, rsp
0x1800415f3  push    rbp
0x1800415f4  push    rbx
0x1800415f5  push    rsi
0x1800415f6  push    rdi
0x1800415f7  push    r12
0x1800415f9  push    r13
0x1800415fb  push    r14
0x1800415fd  push    r15
0x1800415ff  lea     rbp, [rax-0C8h]
0x180041606  sub     rsp, 188h
0x18004160d  movaps  xmmword ptr [rax-58h], xmm6
0x180041611  movaps  xmmword ptr [rax-68h], xmm7
0x180041615  mov     rax, cs:__security_cookie
0x18004161c  xor     rax, rsp
0x18004161f  mov     [rbp+0C0h+var_70], rax
0x180041623  mov     rax, [rdx]
0x180041626  xor     r12d, r12d
0x180041629  mov     r14, r9
0x18004162c  mov     r15, r8
0x18004162f  mov     rdi, rdx
0x180041632  mov     rsi, rcx
0x180041635  mov     [rax+34h], r12d
0x180041639  mov     rax, [rdx]
0x18004163c  mov     ebx, [rax+28h]
0x18004163f  and     ebx, 0FFFFFh
0x180041645  cmp     ebx, 0C8h
0x18004164b  jnb     loc_18004178A
0x180041651  cmp     ebx, 1Bh
0x180041654  jz      short loc_1800416A1
0x180041656  cmp     ebx, 19h
0x180041659  jnz     loc_18004175E
0x18004165f  mov     r11d, [rax+38h]
0x180041663  mov     rbx, rax
0x180041666  mov     r9d, [rcx+38h]
0x18004166a  mov     r8d, r12d
0x18004166d  nop     dword ptr [rax]
0x180041670  cmp     r8d, r9d
0x180041673  jge     loc_180041859
0x180041679  mov     rax, [rsi+30h]
0x18004167d  lea     edx, [r9+r8]
0x180041681  sar     edx, 1
0x180041683  movsxd  rcx, edx
0x180041686  mov     r10, [rax+rcx*8]
0x18004168a  cmp     [r10+14h], r11d
0x18004168e  ja      short loc_18004169C
0x180041690  jnb     loc_180041839
0x180041696  lea     r8d, [rdx+1]
0x18004169a  jmp     short loc_180041670
0x18004169c  mov     r9d, edx
0x18004169f  jmp     short loc_180041670
0x1800416a1  mov     rax, [rdx]
0x1800416a4  mov     r8d, r12d
0x1800416a7  mov     r9d, [rcx+38h]
0x1800416ab  mov     r10d, [rax+38h]
0x1800416af  nop
0x1800416b0  cmp     r8d, r9d
0x1800416b3  jge     loc_180041865
0x1800416b9  mov     rcx, [rsi+30h]
0x1800416bd  lea     eax, [r9+r8]
0x1800416c1  sar     eax, 1
0x1800416c3  movsxd  rdx, eax
0x1800416c6  mov     rbx, [rcx+rdx*8]
0x1800416ca  cmp     [rbx+14h], r10d
0x1800416ce  ja      short loc_1800416D8
0x1800416d0  jnb     short loc_1800416DD
0x1800416d2  lea     r8d, [rax+1]
0x1800416d6  jmp     short loc_1800416B0
0x1800416d8  mov     r9d, eax
0x1800416db  jmp     short loc_1800416B0
0x1800416dd  test    byte ptr [rbx+1Ch], 8
0x1800416e1  jz      loc_180041865
0x1800416e7  mov     rax, [rbx]
0x1800416ea  mov     rcx, rbx
0x1800416ed  mov     rax, [rax+8]
0x1800416f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416f6  test    al, al
0x1800416f8  jnz     loc_180041865
0x1800416fe  mov     rcx, [rdi]
0x180041701  mov     eax, [rbx+20h]
0x180041704  mov     [rcx+38h], eax
0x180041707  mov     rcx, [rdi]
0x18004170a  mov     eax, [rbx+24h]
0x18004170d  mov     [rcx+3Ch], eax
0x180041710  mov     rax, [rdi]
0x180041713  mov     [rax+40h], r12d
0x180041717  mov     rax, [rdi]
0x18004171a  mov     [rax+44h], r12d
0x18004171e  mov     rax, [rdi]
0x180041721  and     dword ptr [rax+28h], 0FBFFFFFFh
0x180041728  mov     rax, [rdi]
0x18004172b  mov     eax, [rax+34h]
0x18004172e  mov     rcx, [rbp+0C0h+var_70]
0x180041732  xor     rcx, rsp; StackCookie
0x180041735  call    __security_check_cookie
0x18004173a  movaps  xmm6, [rsp+1C0h+var_58+8]
0x180041742  movaps  xmm7, [rsp+1C0h+var_68+8]
0x18004174a  add     rsp, 188h
0x180041751  pop     r15
0x180041753  pop     r14
0x180041755  pop     r13
0x180041757  pop     r12
0x180041759  pop     rdi
0x18004175a  pop     rsi
0x18004175b  pop     rbx
0x18004175c  pop     rbp
0x18004175d  retn
0x18004175e  cmp     ebx, 1Ch
0x180041761  jnz     short loc_1800417A9
0x180041763  mov     rax, [rdx]
0x180041766  mov     ecx, [rax+38h]
0x180041769  mov     [r9+20h], ecx
0x18004176d  mov     rax, [rdx]
0x180041770  mov     ecx, [rax+3Ch]
0x180041773  mov     [r9+24h], ecx
0x180041777  mov     rax, [rdx]
0x18004177a  mov     [rax+40h], r12d
0x18004177e  mov     rax, [rdx]
0x180041781  mov     [rax+44h], r12d
0x180041785  mov     rax, [rdx]
0x180041788  jmp     short loc_180041721
0x18004178a  cmp     ebx, 0DCh
0x180041790  ja      short loc_1800417A9
0x180041792  mov     rax, [r9]
0x180041795  mov     rcx, r14
0x180041798  mov     rax, [rax+8]
0x18004179c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800417a1  test    al, al
0x1800417a3  jz      loc_18004187B
0x1800417a9  dec     ebx; switch 220 cases
0x1800417ab  cmp     ebx, 0DBh
0x1800417b1  ja      def_1800417D0; jumptable 00000001800417D0 default case, cases 2,3,7-20,23-25,27-31,37-40,42-55,57-99,101,103-118,120-199,203-218
0x1800417b7  lea     rdx, __ImageBase
0x1800417be  movzx   eax, ds:(byte_180042904 - 180000000h)[rdx+rbx]
0x1800417c6  mov     ecx, ds:(jpt_1800417D0 - 180000000h)[rdx+rax*4]
0x1800417cd  add     rcx, rdx
0x1800417d0  jmp     rcx; switch jump
0x1800417d2  mov     rax, [rdi]; jumptable 00000001800417D0 case 35
0x1800417d5  mov     edx, r12d
0x1800417d8  mov     r8d, [rax+38h]
0x1800417dc  mov     dword ptr [rax+34h], 80004005h
0x1800417e3  mov     rax, [rdi]
0x1800417e6  mov     [rax+3Ch], r12d
0x1800417ea  mov     rax, [rdi]
0x1800417ed  mov     [rax+40h], r12d
0x1800417f1  cmp     edx, [rsi+0D8h]
0x1800417f7  jge     loc_180041717
0x1800417fd  mov     eax, edx
0x1800417ff  imul    eax, [rsi+0DCh]
0x180041806  movsxd  r9, eax
0x180041809  add     r9, [rsi+0D0h]
0x180041810  cmp     [r9], r8d
0x180041813  jnz     loc_180041E68
0x180041819  mov     eax, [r9+4]
0x18004181d  mov     rcx, [rdi]
0x180041820  mov     [rcx+3Ch], eax
0x180041823  mov     eax, [r9+8]
0x180041827  mov     rcx, [rdi]
0x18004182a  mov     [rcx+40h], eax
0x18004182d  mov     rax, [rdi]
0x180041830  mov     [rax+34h], r12d
0x180041834  jmp     loc_180041717
0x180041839  mov     eax, [r10+1Ch]
0x18004183d  mov     [rbx+38h], eax
0x180041840  mov     rcx, [rdi]
0x180041843  mov     eax, [r10+10h]
0x180041847  mov     [rcx+3Ch], eax
0x18004184a  mov     rcx, [rdi]
0x18004184d  mov     eax, [r10+18h]
0x180041851  mov     [rcx+40h], eax
0x180041854  jmp     loc_180041717
0x180041859  mov     dword ptr [rbx+34h], 80004005h
0x180041860  jmp     loc_180041728
0x180041865  mov     rax, [rdi]
0x180041868  mov     dword ptr [rax+38h], 10h
0x18004186f  mov     rax, [rdi]
0x180041872  mov     [rax+3Ch], r12d
0x180041876  jmp     loc_180041710
0x18004187b  mov     rax, [rdi]
0x18004187e  mov     dword ptr [rax+34h], 80004005h
0x180041885  jmp     loc_180041728
0x18004188a  mov     rcx, [rdi]; jumptable 00000001800417D0 case 26
0x18004188d  mov     eax, [rcx+3Ch]
0x180041890  not     eax
0x180041892  and     [rcx+38h], eax
0x180041895  mov     rax, [rdi]
0x180041898  mov     ecx, [rax+38h]
0x18004189b  or      [r14+1Ch], ecx
0x18004189f  mov     rax, [rdi]
0x1800418a2  mov     ecx, [rax+3Ch]
0x1800418a5  not     ecx
0x1800418a7  and     [r14+1Ch], ecx
0x1800418ab  jmp     loc_180041710
0x1800418b0  mov     rdx, [rdi]; jumptable 00000001800417D0 case 100
0x1800418b3  lea     rax, ??_7CMsgDocumentEvent@@6B@; const CMsgDocumentEvent::`vftable'
0x1800418ba  mov     qword ptr [rbp+0C0h+Buffer], rax
0x1800418be  lea     rcx, [rbp+0C0h+Buffer]; this
0x1800418c2  xor     eax, eax
0x1800418c4  mov     [rbp+0C0h+var_118], r12
0x1800418c8  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800418cf  mov     qword ptr [rbp+0C0h+var_100.Data1], rax
0x1800418d3  mov     qword ptr [rbp+0C0h+var_100.Data4+4], rax
0x1800418d7  mov     qword ptr [rbp+0C0h+var_F0.Data2], rax
0x1800418db  mov     qword ptr [rbp+0C0h+var_F0.Data4+4], rax
0x1800418df  mov     qword ptr [rbp+0C0h+var_110], r12
0x1800418e3  mov     [rbp+0C0h+var_108], r12d
0x1800418e7  mov     [rbp+0C0h+var_104], 1
0x1800418eb  mov     dword ptr [rbp+0C0h+var_100.Data4], r12d
0x1800418ef  mov     dword ptr [rbp+0C0h+var_E0+4], ebx
0x1800418f2  call    ?Read@CMsgDocumentEvent@@UEAAJPEAUMsgBase@@@Z; CMsgDocumentEvent::Read(MsgBase *)
0x1800418f7  test    eax, eax
0x1800418f9  js      short loc_180041956
0x1800418fb  cmp     r14, [rsi+80h]
0x180041902  jnz     short loc_180041981
0x180041904  cmp     [rsi+78h], r12b
0x180041908  jnz     short loc_180041981
0x18004190a  mov     rbx, [rsi+70h]
0x18004190e  mov     eax, dword ptr [rbp+0C0h+var_100.Data2]
0x180041911  mov     [rsi+88h], eax
0x180041917  test    rbx, rbx
0x18004191a  jz      short loc_180041956
0x18004191c  cmp     [rbx+68h], r12b
0x180041920  jz      short loc_18004194D
0x180041922  mov     rdx, [rdi]; struct MsgBase *
0x180041925  mov     r9, rbx; struct CCtfServerPort::ClientInfo *
0x180041928  mov     r8, r15; struct _ALPC_MESSAGE_ATTRIBUTES *
0x18004192b  mov     rcx, rsi; this
0x18004192e  call    ?ForwardMessage@CCtfServerPort@@AEAAXPEAUMsgBase@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@PEAUClientInfo@1@@Z; CCtfServerPort::ForwardMessage(MsgBase *,_ALPC_MESSAGE_ATTRIBUTES *,CCtfServerPort::ClientInfo *)
0x180041933  mov     rcx, [rsi+80h]; this
0x18004193a  test    rcx, rcx
0x18004193d  jz      short loc_18004194D
0x18004193f  mov     edx, [rsi+88h]; unsigned int
0x180041945  mov     r8, rbx; struct CCtfServerPort::ImeServerInfo *
0x180041948  call    ?AddDocumentReference@ClientInfo@CCtfServerPort@@QEAA_NKPEAUImeServerInfo@2@@Z; CCtfServerPort::ClientInfo::AddDocumentReference(ulong,CCtfServerPort::ImeServerInfo *)
0x18004194d  mov     rbx, [rbx+58h]
0x180041951  test    rbx, rbx
0x180041954  jnz     short loc_18004191C
0x180041956  lea     rcx, [rbp+0C0h+Buffer]; this
0x18004195a  call    ??1CMsgDocumentEvent@@UEAA@XZ; CMsgDocumentEvent::~CMsgDocumentEvent(void)
0x18004195f  jmp     loc_180041728
0x180041964  mov     rcx, [rdi]; jumptable 00000001800417D0 case 21
0x180041967  mov     eax, [rsi+90h]
0x18004196d  mov     [rcx+38h], eax
0x180041970  mov     rcx, [rdi]
0x180041973  mov     eax, [rsi+8Ch]
0x180041979  mov     [rcx+3Ch], eax
0x18004197c  jmp     loc_180041710
0x180041981  cmp     dword ptr [rbp+0C0h+var_100.Data2], r12d
0x180041985  jz      short loc_180041956
0x180041987  xor     r8d, r8d; unsigned int *
0x18004198a  mov     [rsp+1C0h+var_188], r12
0x18004198f  lea     rdx, [rsp+1C0h+var_188]; HWND *
0x180041994  mov     [rsp+1C0h+nBuff+4], r12d
0x180041999  lea     rcx, [rsp+1C0h+nBuff+4]; unsigned int *
0x18004199e  call    ?GetActiveThreadInfo@@YAXPEAKPEAPEAUHWND__@@0@Z; GetActiveThreadInfo(ulong *,HWND__ * *,ulong *)
0x1800419a3  cmp     [rsp+1C0h+var_188], r12
0x1800419a8  jz      short loc_180041956
0x1800419aa  mov     eax, [rsp+1C0h+nBuff+4]
0x1800419ae  cmp     [r14+14h], eax
0x1800419b2  jnz     short loc_180041956
0x1800419b4  mov     [rsi+80h], r14
0x1800419bb  mov     edx, r12d
0x1800419be  cmp     edx, [r14+48h]
0x1800419c2  jge     loc_18004190A
0x1800419c8  mov     rax, [r14+40h]
0x1800419cc  movsxd  rcx, edx
0x1800419cf  mov     r13, [rax+rcx*8]
0x1800419d3  mov     eax, [r13+28h]
0x1800419d7  and     eax, 0FFFFFh
0x1800419dc  cmp     eax, 29h ; ')'
0x1800419df  jnz     loc_1800427EC
0x1800419e5  xorps   xmm0, xmm0
0x1800419e8  mov     dword ptr [rbp+0C0h+var_140], r12d
0x1800419ec  lea     rax, ??_7CMsgThreadActiveProfiles@@6B@; const CMsgThreadActiveProfiles::`vftable'
0x1800419f3  mov     byte ptr [rbp+0C0h+var_140+4], 1
0x1800419f7  mov     rdx, r13; struct MsgBase *
0x1800419fa  mov     qword ptr [rsp+1C0h+var_158], rax
0x1800419ff  lea     rcx, [rsp+1C0h+var_158]; this
0x180041a04  mov     qword ptr [rbp+0C0h+var_140+8], r12
0x180041a08  movdqu  xmmword ptr [rsp+1C0h+var_158+8], xmm0
0x180041a0e  mov     dword ptr [rbp+0C0h+var_130], r12d
0x180041a12  call    ?Read@CMsgThreadActiveProfiles@@UEAAJPEAUMsgBase@@@Z; CMsgThreadActiveProfiles::Read(MsgBase *)
0x180041a17  test    eax, eax
0x180041a19  jns     loc_1800427F3
0x180041a1f  lea     rcx, [rsp+1C0h+var_158]; this
0x180041a24  call    ??1CMsgThreadActiveProfiles@@UEAA@XZ; CMsgThreadActiveProfiles::~CMsgThreadActiveProfiles(void)
0x180041a29  jmp     loc_18004190A
0x180041a2e  mov     rcx, [rdi]; jumptable 00000001800417D0 case 5
0x180041a31  lea     rax, [rsp+1C0h+nBuff+4]
0x180041a36  mov     qword ptr [rsp+1C0h+Buf1+8], rax
0x180041a3b  lea     r8, [rbp+0C0h+Buffer]; struct tagCPROXY_PARAM *
0x180041a3f  lea     rax, [rsp+1C0h+var_188]
0x180041a44  mov     [rsp+1C0h+nBuff+4], r12d
0x180041a49  mov     qword ptr [rsp+1C0h+Buf1], rax
0x180041a4e  xorps   xmm0, xmm0
0x180041a51  lea     rax, [rsp+1C0h+var_170.Data4]
0x180041a56  mov     [rsp+1C0h+var_188], r12
0x180041a5b  mov     [rbp+0C0h+var_118], rax
0x180041a5f  mov     edx, 3; unsigned int
0x180041a64  lea     rax, [rsp+1C0h+nBuff]
  ... truncated ...
```
