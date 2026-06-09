# CCtfServerPort::ServerLoop(void)

- ea: `0x180040760`
- end: `0x1800415e4`
- name: `?ServerLoop@CCtfServerPort@@AEAAXXZ`
- size: `3716`
- prototype: `void __fastcall(CCtfServerPort *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180052ff8`

## callees

- `0x18000e160`
- `0x1800139c0`
- `0x180026d28`
- `0x18004004c`
- `0x180040694`
- `0x180040760`
- `0x1800415f0`
- `0x1800429e8`
- `0x180042cdc`
- `0x1800432a0`
- `0x180043548`
- `0x18006a430`
- `0x18006a71c`
- `0x18008ced0`
- `0x18009eac6`
- `0x180106a60`
- `0x180106b20`
- `0x18010a010`

## import_xrefs

- `ntdll!RtlUnhandledExceptionFilter` at `0x180107891`
- `ntdll!RtlUnhandledExceptionFilter` at `0x180107891`
- `ntdll!AlpcGetMessageAttribute` at `0x180040806`
- `ntdll!AlpcGetMessageAttribute` at `0x18004081c`
- `ntdll!AlpcGetMessageAttribute` at `0x180040a49`
- `ntdll!AlpcGetMessageAttribute` at `0x180040806`
- `ntdll!AlpcGetMessageAttribute` at `0x18004081c`
- `ntdll!AlpcGetMessageAttribute` at `0x180040a49`
- `ntdll!NtAlpcDeletePortSection` at `0x180040b4b`
- `ntdll!NtAlpcDeletePortSection` at `0x1800414c2`
- `ntdll!NtAlpcDeletePortSection` at `0x180040b4b`
- `ntdll!NtAlpcDeletePortSection` at `0x1800414c2`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180040947`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180040b11`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180040ca3`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180040da2`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18004111a`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x1800413ec`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180040947`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180040b11`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180040ca3`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180040da2`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18004111a`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x1800413ec`
- `ntdll!NtAlpcCancelMessage` at `0x18004087b`
- `ntdll!NtAlpcCancelMessage` at `0x18004087b`
- `ntdll!NtAlpcDeleteSectionView` at `0x180040b8c`
- `ntdll!NtAlpcDeleteSectionView` at `0x180040b8c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180040e23`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800414cd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180040e23`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800414cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040e2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800414d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040e2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800414d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180040834`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180040bbe`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180040834`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180040bbe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040f66`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800412f0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800413a7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040f66`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800412f0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800413a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040f1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004118f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800412b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004134f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041366`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004137e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041432`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040f1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004118f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800412b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004134f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041366`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004137e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041432`

## pseudocode

```c
void __fastcall CCtfServerPort::ServerLoop(CCtfServerPort *this)
{
  CCtfServerPort *v1; // r12
  CCtfServerPort *v2; // r14
  __int64 v3; // r13
  struct _ALPC_MESSAGE_ATTRIBUTES *MessageAttributes; // rax
  struct _ALPC_MESSAGE_ATTRIBUTES *v5; // rsi
  _QWORD *MessageAttribute; // r15
  struct _FILETIME v7; // rbx
  struct _PORT_MESSAGE *v8; // rdi
  int v9; // eax
  int v10; // esi
  HLOCAL v11; // r12
  CSHORT Type; // r9
  __int16 v13; // dx
  __int64 v14; // r12
  __int64 v15; // r15
  unsigned int TotalLength; // eax
  unsigned __int64 v17; // rcx
  void *v18; // r14
  __int64 v19; // rax
  __int64 v20; // r8
  int v21; // ecx
  struct _PORT_MESSAGE *v22; // r14
  ULONG v23; // r15d
  CCtfServerPort *v24; // r15
  int v25; // esi
  struct _ALPC_MESSAGE_ATTRIBUTES *v26; // r14
  ULONG v27; // eax
  CCtfServerPort *v28; // rax
  __int64 v29; // rdi
  struct _FILETIME v30; // rdi
  int DoNotUseThisField_low; // eax
  int Length; // r8d
  unsigned __int64 v33; // rax
  int v34; // eax
  unsigned int v35; // r11d
  int v36; // r8d
  int v37; // r9d
  int v38; // edx
  __int64 v39; // rax
  __int64 v40; // r10
  __int64 v41; // rsi
  int v42; // ecx
  __int64 v43; // rdx
  int v44; // r15d
  __int64 v45; // rdx
  __int16 v46; // cx
  int j; // edx
  _DWORD *v48; // rsi
  int v49; // edx
  unsigned int v50; // ecx
  unsigned int v51; // eax
  unsigned int v52; // eax
  _DWORD *v53; // rax
  _DWORD *v54; // rdi
  _OWORD *v55; // rcx
  int v56; // edx
  void **v57; // rax
  void *v58; // rsi
  unsigned int v59; // edi
  int v60; // r9d
  int v61; // r10d
  __int64 v62; // r14
  int v63; // r8d
  __int64 v64; // rax
  __int64 v65; // r11
  struct _ALPC_MESSAGE_ATTRIBUTES *v66; // r12
  _OWORD *v67; // rax
  HLOCAL v68; // r8
  __int64 v69; // rcx
  bool v70; // zf
  void *v71; // rcx
  __int64 *i; // rsi
  int v73; // r14d
  struct _ALPC_MESSAGE_ATTRIBUTES *v74; // r12
  CCtfServerPort *v75; // r15
  struct CCtfServerPort::ClientInfo *MessageTarget; // rax
  _OWORD *v77; // rax
  int v78; // r14d
  CCtfServerPort *v79; // rbx
  CCtfServerPort::ClientInfo *v80; // rcx
  HLOCAL hMem; // [rsp+40h] [rbp-10E8h] BYREF
  HLOCAL v82; // [rsp+48h] [rbp-10E0h]
  CCtfServerPort *v83; // [rsp+50h] [rbp-10D8h]
  _QWORD *v84; // [rsp+60h] [rbp-10C8h]
  struct _FILETIME v85; // [rsp+68h] [rbp-10C0h] BYREF
  CCtfServerPort *v86; // [rsp+70h] [rbp-10B8h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+78h] [rbp-10B0h] BYREF
  __int64 v88; // [rsp+80h] [rbp-10A8h]
  CCtfServerPort *v89; // [rsp+88h] [rbp-10A0h]
  struct _FILETIME v90; // [rsp+98h] [rbp-1090h]
  struct CCtfServerPort::ClientInfo *v91; // [rsp+A0h] [rbp-1088h] BYREF
  __int64 v92; // [rsp+A8h] [rbp-1080h]
  void *v93; // [rsp+B0h] [rbp-1078h] BYREF
  struct _FILETIME v94; // [rsp+B8h] [rbp-1070h]
  __int64 v95; // [rsp+C0h] [rbp-1068h]
  CCtfServerPort *v96; // [rsp+D0h] [rbp-1058h]
  char v97[16]; // [rsp+E0h] [rbp-1048h] BYREF
  _OWORD v98[4]; // [rsp+F0h] [rbp-1038h] BYREF
  __int64 v99; // [rsp+130h] [rbp-FF8h]

  v1 = this;
  v83 = this;
  v96 = this;
  v2 = this;
  v86 = this;
  v3 = 0;
  hMem = 0;
  MessageAttributes = CreateMessageAttributes(0x70000000u);
  v5 = MessageAttributes;
  v82 = MessageAttributes;
  if ( !MessageAttributes )
    return;
  v89 = v1;
  MessageAttribute = (_QWORD *)AlpcGetMessageAttribute(MessageAttributes, 0x20000000);
  v84 = MessageAttribute;
  v95 = AlpcGetMessageAttribute(v5, 0x40000000);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v7 = SystemTimeAsFileTime;
  v90 = SystemTimeAsFileTime;
  v94 = SystemTimeAsFileTime;
  v8 = (struct _PORT_MESSAGE *)hMem;
  while ( 1 )
  {
    if ( *((_BYTE *)v2 + 32) || !*(_QWORD *)v1 )
      goto LABEL_158;
    SystemTimeAsFileTime = (struct _FILETIME)4096LL;
    if ( v8 && v8 != (struct _PORT_MESSAGE *)v98 )
      LocalFree(v8);
    hMem = v98;
    memset(v98, 0, sizeof(v98));
    v99 = 0;
    *((_DWORD *)v5 + 1) = 0;
    v9 = NtAlpcSendWaitReceivePort(*(_QWORD *)v1, 0, 0, 0, hMem, &SystemTimeAsFileTime, v5, 0);
    v10 = v9;
    if ( v9 == -1073741816 )
      break;
    if ( v9 == -1073741789
      && *(unsigned __int64 *)&SystemTimeAsFileTime > 0x1000
      && SystemTimeAsFileTime == SystemTimeAsFileTime.dwLowDateTime )
    {
      v8 = (struct _PORT_MESSAGE *)LocalAlloc(0x40u, SystemTimeAsFileTime.dwLowDateTime);
      hMem = v8;
      v11 = v82;
      if ( !v8 )
        goto LABEL_18;
      v10 = NtAlpcSendWaitReceivePort(*(_QWORD *)v83, 0, 0, 0, v8, &SystemTimeAsFileTime, v82, 0);
    }
    else
    {
      v11 = v82;
    }
    v8 = (struct _PORT_MESSAGE *)hMem;
LABEL_18:
    if ( v10 == 258 )
      goto LABEL_7;
    if ( v10 == -1073741758 )
      goto LABEL_159;
    if ( v10 < 0 )
    {
      v70 = v10 == -1073741789;
      v5 = (struct _ALPC_MESSAGE_ATTRIBUTES *)v82;
      v1 = v83;
      if ( v70 )
        goto LABEL_4;
    }
    else
    {
      Type = v8->u2.s2.Type;
      v13 = (unsigned __int8)Type;
      if ( (unsigned __int8)Type == 10 )
      {
        CCtfServerPort::ProcessConnectionRequest(v2, v8);
        v8 = (struct _PORT_MESSAGE *)hMem;
LABEL_7:
        v5 = (struct _ALPC_MESSAGE_ATTRIBUTES *)v82;
        goto LABEL_8;
      }
      v14 = *MessageAttribute;
      v91 = (struct CCtfServerPort::ClientInfo *)v14;
      if ( v14 )
      {
        if ( (((unsigned __int8)Type - 1) & 0xFFFD) != 0
          || (v5 = (struct _ALPC_MESSAGE_ATTRIBUTES *)v82, v8[1].u2.ZeroInit == *(_DWORD *)(v14 + 20)) )
        {
          v15 = 0;
          v88 = 0;
          v92 = 0;
          v5 = (struct _ALPC_MESSAGE_ATTRIBUTES *)v82;
          if ( (unsigned __int16)((unsigned __int8)Type - 1) > 2u )
            goto LABEL_30;
          TotalLength = v8->u1.s1.TotalLength;
          v17 = TotalLength;
          if ( TotalLength < 0x48 )
            goto LABEL_169;
          if ( (*((_DWORD *)v82 + 1) & 0x40000000) != 0 )
          {
            if ( (v8[1].u1.Length & 0x80000000) != 0
              && (unsigned __int64)*((unsigned int *)&v8[1].DoNotUseThisField + 3) <= *(_QWORD *)(v95 + 24) )
            {
              v15 = *(_QWORD *)(v95 + 16);
              v88 = v15;
              if ( v15 )
              {
                v92 = v15;
                *(_QWORD *)&v8[1].MessageId = v15;
                v8 = (struct _PORT_MESSAGE *)hMem;
                goto LABEL_30;
              }
            }
LABEL_169:
            v1 = v83;
            MessageAttribute = v84;
            if ( (Type & 0x2000) != 0 )
            {
LABEL_4:
              NtAlpcCancelMessage(*(_QWORD *)v1, 0, MessageAttribute);
              goto LABEL_5;
            }
          }
          else
          {
            if ( (v8[1].u1.Length & 0x80000000) != 0 || (unsigned __int16)TotalLength > 0x48u )
            {
              v33 = *((unsigned int *)&v8[1].DoNotUseThisField + 3);
              if ( v33 < v33 + 72 && v33 + 72 <= v17 )
              {
                *(_QWORD *)&v8[1].MessageId = (char *)v8 + 72;
                v8 = (struct _PORT_MESSAGE *)hMem;
                goto LABEL_30;
              }
              goto LABEL_169;
            }
LABEL_30:
            if ( (unsigned __int8)Type != 1 )
            {
              switch ( (char)Type )
              {
                case 2:
                case 4:
                case 12:
                  v58 = (void *)v84[1];
                  if ( !v58 )
                    goto LABEL_73;
                  v91 = (struct CCtfServerPort::ClientInfo *)v84[1];
                  v59 = *((_DWORD *)v58 + 12);
                  v60 = 0;
                  v61 = *((_DWORD *)v89 + 14);
                  v62 = 0;
                  while ( 2 )
                  {
                    if ( v60 < v61 )
                    {
                      v63 = (v61 + v60) >> 1;
                      v64 = *((_QWORD *)v86 + 6);
                      v65 = *(_QWORD *)(v64 + 8LL * v63);
                      if ( *(_DWORD *)(v65 + 20) > v59 )
                      {
                        v61 = (v61 + v60) >> 1;
                        continue;
                      }
                      if ( *(_DWORD *)(v65 + 20) < v59 )
                      {
                        v60 = v63 + 1;
                        continue;
                      }
                      v62 = *(_QWORD *)(v64 + 8LL * v63);
                    }
                    break;
                  }
                  if ( v62 && v62 == *((_QWORD *)v58 + 7) )
                  {
                    v85 = 0;
                    v66 = (struct _ALPC_MESSAGE_ATTRIBUTES *)v82;
                    *((_DWORD *)v82 + 1) &= 0x40000000u;
                    *((_WORD *)v58 + 1) = *((_WORD *)hMem + 1);
                    *(_WORD *)v58 = *(_WORD *)hMem;
                    v67 = hMem;
                    *(_OWORD *)hMem = *(_OWORD *)v58;
                    v67[1] = *((_OWORD *)v58 + 1);
                    *((_QWORD *)v67 + 4) = *((_QWORD *)v58 + 4);
                    if ( (*((_DWORD *)v66 + 1) & 0x40000000) != 0 )
                    {
                      if ( (int)CreateDataView(*(void **)(v62 + 8), (struct MsgBase *)hMem, v66, (void **)&v85) < 0 )
                        *((_DWORD *)hMem + 13) = -2147467259;
                      *((_QWORD *)hMem + 8) = 0;
                    }
                    else if ( v13 != 2 )
                    {
                      *((_DWORD *)hMem + 13) = -2147467259;
                    }
                    v68 = hMem;
                    if ( *((int *)hMem + 13) < 0 )
                    {
                      *((_WORD *)hMem + 1) = 72;
                      *(_WORD *)hMem = 32;
                      *((_WORD *)hMem + 3) = 0;
                      *((_DWORD *)hMem + 10) &= ~0x80000000;
                      v68 = hMem;
                    }
                    NtAlpcSendWaitReceivePort(*(_QWORD *)(v62 + 8), 0x10000, v68, v66, 0, 0, 0, 0);
                    if ( v85 )
                      NtAlpcDeletePortSection(*(_QWORD *)(v62 + 8), 0);
                  }
                  v69 = *((_QWORD *)v58 + 7);
                  v70 = (*(_DWORD *)(v69 + 80))-- == 1;
                  if ( v70 )
                    (**(void (__fastcall ***)(__int64, __int64))v69)(v69, 1);
                  v1 = v83;
                  v71 = (void *)*((_QWORD *)v58 + 5);
                  if ( v71 )
                  {
                    SetEvent(v71);
                    CloseHandle(*((HANDLE *)v58 + 5));
                  }
                  LocalFree(v58);
                  v8 = (struct _PORT_MESSAGE *)hMem;
                  v5 = (struct _ALPC_MESSAGE_ATTRIBUTES *)v82;
                  goto LABEL_54;
                case 3:
                  DoNotUseThisField_low = LODWORD(v8[1].DoNotUseThisField);
                  if ( DoNotUseThisField_low )
                  {
                    if ( (v8[1].u1.Length & 0x100000) != 0 )
                    {
                      for ( i = *(__int64 **)(v14 + 40); i; i = (__int64 *)*i )
                      {
                        if ( *((_DWORD *)i + 4) == DoNotUseThisField_low )
                          goto LABEL_148;
                      }
                      i = 0;
LABEL_148:
                      if ( i )
                      {
                        v73 = 0;
                        if ( *((int *)i + 10) > 0 )
                        {
                          v74 = (struct _ALPC_MESSAGE_ATTRIBUTES *)v82;
                          v75 = v86;
                          do
                            CCtfServerPort::ForwardMessage(
                              v75,
                              (struct MsgBase *)v8,
                              v74,
                              *(struct CCtfServerPort::ClientInfo **)(i[4] + 8LL * v73++));
                          while ( v73 < *((_DWORD *)i + 10) );
                          v15 = v88;
                          goto LABEL_63;
                        }
                      }
                    }
                    else
                    {
                      MessageTarget = CCtfServerPort::FindMessageTarget(v2, (const struct MsgBase *)v8);
                      if ( MessageTarget )
                      {
                        CCtfServerPort::ForwardMessage(v2, (struct MsgBase *)v8, v5, MessageTarget);
                        goto LABEL_63;
                      }
                    }
                  }
                  else
                  {
                    Length = v8[1].u1.Length;
                    if ( (Length & 0x50000000) == 0 )
                      goto LABEL_62;
                    for ( j = 0; j < *(_DWORD *)(v14 + 72); ++j )
                    {
                      v48 = *(_DWORD **)(*(_QWORD *)(v14 + 64) + 8LL * j);
                      if ( ((v48[10] ^ Length) & 0xFFFFF) == 0 )
                      {
                        CVoidPtrArray::Remove((CVoidPtrArray *)(v14 + 56), j, Length);
                        LocalFree(v48);
                        v8 = (struct _PORT_MESSAGE *)hMem;
                        break;
                      }
                    }
                    v49 = v8[1].u1.Length;
                    if ( (v49 & 0x10000000) != 0 )
                    {
                      v50 = *((_DWORD *)&v8[1].DoNotUseThisField + 3);
                      v51 = (v50 + 7) & 0xFFFFFFF8;
                      if ( v51 < v50 )
                        goto LABEL_73;
                      if ( v49 >= 0 )
                        goto LABEL_73;
                      if ( !v50 )
                        goto LABEL_73;
                      v52 = v51 + 72;
                      if ( v52 < 0x48 )
                        goto LABEL_73;
                      v53 = LocalAlloc(0x40u, v52);
                      v54 = v53;
                      if ( !v53 )
                        goto LABEL_72;
                      v55 = hMem;
                      *(_OWORD *)v53 = *(_OWORD *)hMem;
                      *((_OWORD *)v53 + 1) = v55[1];
                      *((_OWORD *)v53 + 2) = v55[2];
                      *((_OWORD *)v53 + 3) = v55[3];
                      *((_QWORD *)v53 + 8) = v53 + 18;
                      memcpy_0(v53 + 18, *((const void **)hMem + 8), *((unsigned int *)hMem + 15));
                      v5 = (struct _ALPC_MESSAGE_ATTRIBUTES *)v82;
                      if ( (*((_DWORD *)v82 + 1) & 0x40000000) != 0 )
                        v54[10] |= 0x4000000u;
                      v57 = CVoidPtrArray::Append((CVoidPtrArray *)(v14 + 56), v56);
                      if ( !v57 )
                      {
                        LocalFree(v54);
                        v8 = (struct _PORT_MESSAGE *)hMem;
                        goto LABEL_53;
                      }
                      *v57 = v54;
                      v8 = (struct _PORT_MESSAGE *)hMem;
                    }
                    else
                    {
                      v5 = (struct _ALPC_MESSAGE_ATTRIBUTES *)v82;
                    }
                    if ( (v8[1].u1.Length & 0xFFFFF) == 0x29 )
                    {
LABEL_62:
                      CCtfServerPort::ProcessMessage(
                        v2,
                        (struct MsgBase **)&hMem,
                        v5,
                        (struct CCtfServerPort::ClientInfo *)v14);
LABEL_63:
                      v8 = (struct _PORT_MESSAGE *)hMem;
                    }
                  }
                  v5 = (struct _ALPC_MESSAGE_ATTRIBUTES *)v82;
                  v1 = v83;
                  if ( (v8->u2.s2.Type & 0x2000) != 0 )
                  {
                    NtAlpcSendWaitReceivePort(*(_QWORD *)v83, 0x10000, v8, v82, 0, 0, 0, 0);
                    v8 = (struct _PORT_MESSAGE *)hMem;
                  }
                  break;
                case 5:
                case 6:
                  CCtfServerPort::RemoveClient(v2, &v91);
                  v8 = (struct _PORT_MESSAGE *)hMem;
                  goto LABEL_53;
                default:
                  goto LABEL_53;
              }
              goto LABEL_54;
            }
            v18 = 0;
            v85 = 0;
            v19 = AlpcGetMessageAttribute(v5, 0x10000000);
            if ( v19 )
            {
              v21 = *((_DWORD *)v5 + 1);
              if ( (v21 & 0x10000000) != 0 && *(_DWORD *)(v19 + 16) == 16 )
              {
                v18 = *(void **)(v19 + 8);
                v85 = (struct _FILETIME)v18;
                *((_DWORD *)v5 + 1) = v21 & 0xEFFFFFFF;
              }
            }
            v8 = (struct _PORT_MESSAGE *)hMem;
            if ( !*((_DWORD *)hMem + 12) || (v34 = *((_DWORD *)hMem + 10), (v34 & 0x20000000) != 0) )
            {
              if ( *((__int16 *)hMem + 1) < SLOWORD(SystemTimeAsFileTime.dwLowDateTime) )
              {
                *((_WORD *)hMem + 1) = SystemTimeAsFileTime.dwLowDateTime;
                v8 = (struct _PORT_MESSAGE *)hMem;
              }
              v22 = v8;
              v23 = v8[1].u1.Length;
              if ( (v23 & 0x20000000) == 0 )
              {
                v24 = v86;
                v25 = CCtfServerPort::ProcessMessage(
                        v86,
                        (struct MsgBase **)&hMem,
                        v5,
                        (struct CCtfServerPort::ClientInfo *)v14);
                v8 = (struct _PORT_MESSAGE *)hMem;
                goto LABEL_38;
              }
              v35 = LODWORD(v8[1].DoNotUseThisField);
              v36 = 0;
              v37 = *((_DWORD *)v89 + 14);
              while ( v36 < v37 )
              {
                v38 = (v37 + v36) >> 1;
                v39 = *((_QWORD *)v86 + 6);
                v40 = *(_QWORD *)(v39 + 8LL * v38);
                if ( *(_DWORD *)(v40 + 20) > v35 )
                {
                  v37 = (v37 + v36) >> 1;
                }
                else
                {
                  if ( *(_DWORD *)(v40 + 20) >= v35 )
                  {
                    v3 = *(_QWORD *)(v39 + 8LL * v38);
                    break;
                  }
                  v36 = v38 + 1;
                }
              }
              if ( v3 )
              {
                v41 = 0;
                v42 = *(_DWORD *)(v3 + 72);
                if ( v42 > 0 )
                {
                  v43 = 0;
                  v44 = v23 & 0xFFFFF;
                  do
                  {
                    v41 = *(_QWORD *)(*(_QWORD *)(v3 + 64) + 8 * v43);
                    if ( (*(_DWORD *)(v41 + 40) & 0xFFFFF) == v44 )
                      break;
                    v41 = 0;
                    v43 = (unsigned int)(v43 + 1);
                  }
                  while ( (int)v43 < v42 );
                }
                if ( !v41 )
                {
                  v25 = -2147467259;
                  v3 = 0;
                  goto LABEL_88;
                }
                v45 = *(unsigned int *)(v41 + 60);
                if ( (unsigned int)v8->u1.s1.TotalLength < (unsigned __int64)(v45 + 72) )
                {
                  v8 = (struct _PORT_MESSAGE *)LocalAlloc(0, (unsigned int)(v45 + 72));
                  if ( v8 )
                  {
                    v77 = hMem;
                    *(_OWORD *)&v8->u1.s1.DataLength = *(_OWORD *)hMem;
                    *(union _PORT_MESSAGE::$C6BC508B531A81D74C33985719C23F49 *)((char *)&v8->8 + 8) = (union _PORT_MESSAGE::$C6BC508B531A81D74C33985719C23F49)v77[1];
                    *(_OWORD *)&v8->ClientViewSize = v77[2];
                    v8[1].8 = (union _PORT_MESSAGE::$C6BC508B531A81D74C33985719C23F49)v77[3];
                    *(_QWORD *)&v8[1].MessageId = *((_QWORD *)v77 + 8);
                    hMem = v8;
                    goto LABEL_94;
                  }
                  v25 = -2147024882;
                  v3 = 0;
                }
                else
                {
LABEL_94:
                  v3 = 0;
                  HIDWORD(v8[1].DoNotUseThisField) = 0;
                  v46 = *(_WORD *)(v41 + 2);
                  *((_WORD *)hMem + 1) = v46;
                  *(_WORD *)hMem = v46 - 40;
                  *((_DWORD *)hMem + 15) = *(_DWORD *)(v41 + 60);
                  *((_QWORD *)hMem + 8) = (char *)hMem + 72;
                  memcpy_0(*((void **)hMem + 8), *(const void **)(v41 + 64), *((unsigned int *)hMem + 15));
                  *((_DWORD *)hMem + 10) |= *(_DWORD *)(v41 + 40) & 0x4000000;
                  v25 = 0;
                }
                v8 = (struct _PORT_MESSAGE *)hMem;
LABEL_88:
                v24 = v86;
              }
              else
              {
                v25 = -2147467259;
                v3 = 0;
                v24 = v86;
              }
LABEL_38:
              if ( v22 != v8 && v22 != (struct _PORT_MESSAGE *)v98 && v22 )
              {
                LocalFree(v22);
                v8 = (struct _PORT_MESSAGE *)hMem;
              }
              v93 = 0;
              v26 = (struct _ALPC_MESSAGE_ATTRIBUTES *)v82;
              if ( v25 >= 0 )
              {
                v27 = v8[1].u1.Length;
                if ( (v27 & 0x4000000) != 0 )
                {
                  v8[1].u1.Length = v27 & 0xFBFFFFFF;
                  v25 = CreateDataView(*(void **)(v14 + 8), (struct MsgBase *)hMem, v26, &v93);
                  v8 = (struct _PORT_MESSAGE *)hMem;
                }
                if ( v25 >= 0 )
                {
                  v8->u1.s1.TotalLength = v8->u1.s1.DataLength + 40;
                  NtAlpcSendWaitReceivePort(*(_QWORD *)(v14 + 8), 0x10000, hMem, v26, 0, 0, 0, 0);
                  v28 = v89;
                  v29 = *((unsigned int *)v89 + 17);
                  *((_DWORD *)v89 + 17) = -1;
                  if ( (_DWORD)v29 != -1 )
                  {
                    v78 = 0;
                    if ( *((int *)v24 + 14) > 0 )
                    {
                      v79 = v28;
                      do
                      {
                        v80 = *(CCtfServerPort::ClientInfo **)(*((_QWORD *)v79 + 6) + 8LL * v78);
                        if ( v80 != (CCtfServerPort::ClientInfo *)v14 && (*((_DWORD *)v80 + 7) & 0x20000000) != 0 )
                          CCtfServerPort::ClientInfo::PostMessageW(v80, g_msgPrivate, 7u, v29);
                        ++v78;
                      }
                      while ( v78 < *((_DWORD *)v24 + 14) );
                      v7 = v90;
                    }
                  }
                  v8 = (struct _PORT_MESSAGE *)hMem;
                }
              }
              if ( v93 )
              {
                NtAlpcDeletePortSection(*(_QWORD *)(v14 + 8), 0);
                v8 = (struct _PORT_MESSAGE *)hMem;
              }
              v18 = (void *)v85;
              goto LABEL_48;
            }
            if ( v34 == 104 && (byte_180140041 & 8) != 0 )
            {
              McGenEventWrite_EventWriteTransfer(
                &Microsoft_Windows_TSF_msctf_Context,
                KeyEventForwarding_Server,
                v20,
                1,
                v97);
              v8 = (struct _PORT_MESSAGE *)hMem;
            }
            v25 = CCtfServerPort::ForwardRequest(
                    v86,
                    (struct MsgBase *)v8,
                    v5,
                    (struct CCtfServerPort::ClientInfo *)v14,
                    v18);
            if ( v25 >= 0 )
            {
LABEL_72:
              v8 = (struct _PORT_MESSAGE *)hMem;
LABEL_73:
              v5 = (struct _ALPC_MESSAGE_ATTRIBUTES *)v82;
              goto LABEL_53;
            }
            v8 = (struct _PORT_MESSAGE *)hMem;
LABEL_48:
            if ( v25 < 0 )
            {
              HIDWORD(v8[1].DoNotUseThisField) = v25;
              *((_WORD *)hMem + 1) = 72;
              *(_WORD *)hMem = 32;
              *((_WORD *)hMem + 3) = 0;
              *((_DWORD *)hMem + 10) &= ~0x80000000;
              v5 = (struct _ALPC_MESSAGE_ATTRIBUTES *)v82;
              NtAlpcSendWaitReceivePort(*(_QWORD *)(v14 + 8), 0x10000, hMem, v82, 0, 0, 0, 0);
              v8 = (struct _PORT_MESSAGE *)hMem;
            }
            else
            {
              v5 = (struct _ALPC_MESSAGE_ATTRIBUTES *)v82;
            }
            if ( v18 )
            {
              SetEvent(v18);
              CloseHandle(v18);
              v8 = (struct _PORT_MESSAGE *)hMem;
            }
            v15 = v88;
LABEL_53:
            v1 = v83;
LABEL_54:
            if ( v15 )
            {
              NtAlpcDeleteSectionView(*(_QWORD *)v1, 0, v15);
              v8 = (struct _PORT_MESSAGE *)hMem;
            }
            v2 = v89;
            MessageAttribute = v84;
            if ( *((_DWORD *)v89 + 46) )
            {
              v85 = 0;
              GetSystemTimeAsFileTime(&v85);
              v30 = v85;
              if ( (__int64)(*(_QWORD *)&v85 - *(_QWORD *)&v7) >= 72000000000LL )
              {
                CCtfServerPort::SubmitTelemetryData(v2, 1);
                v7 = v30;
                v90 = v30;
                v94 = v30;
              }
LABEL_5:
              v8 = (struct _PORT_MESSAGE *)hMem;
            }
          }
        }
        else
        {
LABEL_8:
          v1 = v83;
        }
      }
      else
      {
        v5 = (struct _ALPC_MESSAGE_ATTRIBUTES *)v82;
        v1 = v83;
        if ( (Type & 0x2000) != 0 )
          goto LABEL_4;
      }
    }
  }
  v8 = (struct _PORT_MESSAGE *)hMem;
LABEL_158:
  v11 = v82;
LABEL_159:
  if ( v8 && v8 != (struct _PORT_MESSAGE *)v98 )
    LocalFree(v8);
  LocalFree(v11);
}

```

## disassembly

```asm
0x180040760  mov     [rsp+arg_8], rbx
0x180040765  mov     [rsp+arg_10], rsi
0x18004076a  push    rdi
0x18004076b  push    r12
0x18004076d  push    r13
0x18004076f  push    r14
0x180040771  push    r15
0x180040773  mov     eax, 1100h
0x180040778  call    _alloca_probe
0x18004077d  sub     rsp, rax
0x180040780  mov     rax, cs:__security_cookie
0x180040787  xor     rax, rsp
0x18004078a  mov     [rsp+1128h+var_38], rax
0x180040792  mov     r12, rcx
0x180040795  mov     [rsp+1128h+var_10D8], rcx
0x18004079a  mov     [rsp+1128h+var_1058], rcx
0x1800407a2  mov     r14, rcx
0x1800407a5  mov     [rsp+1128h+var_10B8], rcx
0x1800407aa  xor     r13d, r13d
0x1800407ad  mov     [rsp+1128h+hMem], r13
0x1800407b2  mov     ecx, 70000000h; unsigned int
0x1800407b7  call    ?CreateMessageAttributes@@YAPEAU_ALPC_MESSAGE_ATTRIBUTES@@K@Z; CreateMessageAttributes(ulong)
0x1800407bc  mov     rsi, rax
0x1800407bf  mov     [rsp+1128h+var_10E0], rax
0x1800407c4  test    rax, rax
0x1800407c7  jnz     short loc_1800407F6
0x1800407c9  mov     rcx, [rsp+1128h+var_38]
0x1800407d1  xor     rcx, rsp; StackCookie
0x1800407d4  call    __security_check_cookie
0x1800407d9  lea     r11, [rsp+1128h+var_28]
0x1800407e1  mov     rbx, [r11+38h]
0x1800407e5  mov     rsi, [r11+40h]
0x1800407e9  mov     rsp, r11
0x1800407ec  pop     r15
0x1800407ee  pop     r14
0x1800407f0  pop     r13
0x1800407f2  pop     r12
0x1800407f4  pop     rdi
0x1800407f5  retn
0x1800407f6  mov     [rsp+1128h+var_10A0], r12
0x1800407fe  mov     edx, 20000000h
0x180040803  mov     rcx, rsi
0x180040806  call    cs:__imp_AlpcGetMessageAttribute
0x18004080c  mov     r15, rax
0x18004080f  mov     [rsp+1128h+var_10C8], rax
0x180040814  mov     edx, 40000000h
0x180040819  mov     rcx, rsi
0x18004081c  call    cs:__imp_AlpcGetMessageAttribute
0x180040822  mov     [rsp+1128h+var_1068], rax
0x18004082a  mov     qword ptr [rsp+1128h+SystemTimeAsFileTime.dwLowDateTime], r13
0x18004082f  lea     rcx, [rsp+1128h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180040834  call    cs:__imp_GetSystemTimeAsFileTime
0x18004083a  mov     ebx, [rsp+1128h+SystemTimeAsFileTime.dwHighDateTime]
0x18004083e  shl     rbx, 20h
0x180040842  mov     ecx, [rsp+1128h+SystemTimeAsFileTime.dwLowDateTime]
0x180040846  or      rbx, rcx
0x180040849  mov     [rsp+1128h+var_1090], rbx
0x180040851  mov     [rsp+1128h+var_1070], rbx
0x180040859  mov     rdi, [rsp+1128h+hMem]
0x18004085e  jmp     short loc_1800408AA
0x180040860  bt      r9w, 0Dh
0x180040866  mov     rsi, [rsp+1128h+var_10E0]
0x18004086b  mov     r12, [rsp+1128h+var_10D8]
0x180040870  jnb     short loc_1800408AA
0x180040872  mov     r8, r15
0x180040875  xor     edx, edx
0x180040877  mov     rcx, [r12]
0x18004087b  call    cs:__imp_NtAlpcCancelMessage
0x180040881  mov     rdi, [rsp+1128h+hMem]
0x180040886  jmp     short loc_1800408AA
0x180040888  mov     rdx, rdi; struct _PORT_MESSAGE *
0x18004088b  mov     rcx, r14; this
0x18004088e  call    ?ProcessConnectionRequest@CCtfServerPort@@AEAAJPEAU_PORT_MESSAGE@@@Z; CCtfServerPort::ProcessConnectionRequest(_PORT_MESSAGE *)
0x180040893  mov     rdi, [rsp+1128h+hMem]
0x180040898  nop     dword ptr [rax+rax+00000000h]
0x1800408a0  mov     rsi, [rsp+1128h+var_10E0]
0x1800408a5  mov     r12, [rsp+1128h+var_10D8]
0x1800408aa  cmp     byte ptr [r14+20h], 0
0x1800408af  jnz     loc_18004133E
0x1800408b5  cmp     qword ptr [r12], 0
0x1800408ba  jz      loc_18004133E
0x1800408c0  mov     qword ptr [rsp+1128h+SystemTimeAsFileTime.dwLowDateTime], 1000h
0x1800408c9  test    rdi, rdi
0x1800408cc  jz      short loc_1800408DF
0x1800408ce  lea     rax, [rsp+1128h+var_1038]
0x1800408d6  cmp     rdi, rax
0x1800408d9  jnz     loc_1800412A7
0x1800408df  lea     rax, [rsp+1128h+var_1038]
0x1800408e7  mov     [rsp+1128h+hMem], rax
0x1800408ec  xorps   xmm0, xmm0
0x1800408ef  xor     eax, eax
0x1800408f1  movups  [rsp+1128h+var_1038], xmm0
0x1800408f9  movups  [rsp+1128h+var_1028], xmm0
0x180040901  movups  [rsp+1128h+var_1018], xmm0
0x180040909  movups  [rsp+1128h+var_1008], xmm0
0x180040911  mov     [rsp+1128h+var_FF8], rax
0x180040919  mov     [rsi+4], r13d
0x18004091d  mov     [rsp+1128h+var_10F0], r13
0x180040922  mov     [rsp+1128h+var_10F8], rsi
0x180040927  lea     rax, [rsp+1128h+SystemTimeAsFileTime]
0x18004092c  mov     [rsp+1128h+var_1100], rax
0x180040931  mov     rax, [rsp+1128h+hMem]
0x180040936  mov     [rsp+1128h+var_1108], rax
0x18004093b  xor     r9d, r9d
0x18004093e  xor     r8d, r8d
0x180040941  xor     edx, edx
0x180040943  mov     rcx, [r12]
0x180040947  call    cs:__imp_NtAlpcSendWaitReceivePort
0x18004094d  mov     esi, eax
0x18004094f  cmp     eax, 0C0000008h
0x180040954  jz      loc_180041339
0x18004095a  cmp     eax, 0C0000023h
0x18004095f  jz      loc_180041386
0x180040965  mov     r12, [rsp+1128h+var_10E0]
0x18004096a  mov     rdi, [rsp+1128h+hMem]
0x18004096f  cmp     esi, 102h
0x180040975  jz      loc_1800408A0
0x18004097b  cmp     esi, 0C0000042h
0x180040981  jz      loc_180041343
0x180040987  test    esi, esi
0x180040989  js      loc_1800413F9
0x18004098f  movzx   r9d, word ptr [rdi+4]
0x180040994  movzx   edx, r9w
0x180040998  mov     eax, 0FFh
0x18004099d  and     dx, ax
0x1800409a0  cmp     dx, 0Ah
0x1800409a4  jz      loc_180040888
0x1800409aa  mov     r12, [r15]
0x1800409ad  mov     [rsp+1128h+var_1088], r12
0x1800409b5  test    r12, r12
0x1800409b8  jz      loc_180040860
0x1800409be  lea     eax, [rdx-1]
0x1800409c1  mov     ecx, 0FFFDh
0x1800409c6  test    cx, ax
0x1800409c9  jnz     short loc_1800409DE
0x1800409cb  mov     eax, [r12+14h]
0x1800409d0  cmp     [rdi+2Ch], eax
0x1800409d3  mov     rsi, [rsp+1128h+var_10E0]
0x1800409d8  jnz     loc_1800408A5
0x1800409de  mov     r15, r13
0x1800409e1  mov     [rsp+1128h+var_10A8], r13
0x1800409e9  mov     [rsp+1128h+var_1080], r13
0x1800409f1  lea     eax, [rdx-1]
0x1800409f4  mov     rsi, [rsp+1128h+var_10E0]
0x1800409f9  cmp     ax, 2
0x1800409fd  ja      short loc_180040A2F
0x1800409ff  movsx   eax, word ptr [rdi+2]
0x180040a03  mov     ecx, eax
0x180040a05  cmp     eax, 48h ; 'H'
0x180040a08  jb      loc_180041414
0x180040a0e  test    dword ptr [rsi+4], 40000000h
0x180040a15  jnz     loc_1800411C5
0x180040a1b  cmp     dword ptr [rdi+28h], 0
0x180040a1f  jl      loc_180040CB3
0x180040a25  cmp     ax, 48h ; 'H'
0x180040a29  ja      loc_180040CB3
0x180040a2f  cmp     dx, 1
0x180040a33  jnz     loc_180040C0E
0x180040a39  mov     r14, r13
0x180040a3c  mov     qword ptr [rsp+1128h+var_10C0.dwLowDateTime], r13
0x180040a41  mov     edx, 10000000h
0x180040a46  mov     rcx, rsi
0x180040a49  call    cs:__imp_AlpcGetMessageAttribute
0x180040a4f  test    rax, rax
0x180040a52  jz      short loc_180040A61
0x180040a54  mov     ecx, [rsi+4]
0x180040a57  bt      ecx, 1Ch
0x180040a5b  jb      loc_180040D25
0x180040a61  mov     rdi, [rsp+1128h+hMem]
0x180040a66  cmp     dword ptr [rdi+30h], 0
0x180040a6a  jnz     loc_180040CDE
0x180040a70  mov     rax, qword ptr [rsp+1128h+SystemTimeAsFileTime.dwLowDateTime]
0x180040a75  cmp     [rdi+2], ax
0x180040a79  jge     short loc_180040A84
0x180040a7b  mov     [rdi+2], ax
0x180040a7f  mov     rdi, [rsp+1128h+hMem]
0x180040a84  mov     r14, rdi
0x180040a87  mov     r15d, [rdi+28h]
0x180040a8b  bt      r15d, 1Dh
0x180040a90  jb      loc_180040DB2
0x180040a96  mov     r9, r12; struct CCtfServerPort::ClientInfo *
0x180040a99  mov     r8, rsi; struct _ALPC_MESSAGE_ATTRIBUTES *
0x180040a9c  lea     rdx, [rsp+1128h+hMem]; struct MsgBase **
0x180040aa1  mov     r15, [rsp+1128h+var_10B8]
0x180040aa6  mov     rcx, r15; this
0x180040aa9  call    ?ProcessMessage@CCtfServerPort@@AEAAJAEAPEAUMsgBase@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@PEAUClientInfo@1@@Z; CCtfServerPort::ProcessMessage(MsgBase * &,_ALPC_MESSAGE_ATTRIBUTES *,CCtfServerPort::ClientInfo *)
0x180040aae  mov     esi, eax
0x180040ab0  mov     rdi, [rsp+1128h+hMem]
0x180040ab5  cmp     r14, rdi
0x180040ab8  jnz     loc_180041536
0x180040abe  mov     [rsp+1128h+var_1078], r13
0x180040ac6  mov     r14, [rsp+1128h+var_10E0]
0x180040acb  test    esi, esi
0x180040acd  js      short loc_180040B37
0x180040acf  mov     eax, [rdi+28h]
0x180040ad2  bt      eax, 1Ah
0x180040ad6  jb      loc_1800412BE
0x180040adc  test    esi, esi
0x180040ade  js      short loc_180040B37
0x180040ae0  movzx   eax, word ptr [rdi]
0x180040ae3  add     ax, 28h ; '('
0x180040ae7  mov     [rdi+2], ax
0x180040aeb  mov     [rsp+1128h+var_10F0], r13
0x180040af0  mov     [rsp+1128h+var_10F8], r13
0x180040af5  mov     [rsp+1128h+var_1100], r13
0x180040afa  mov     [rsp+1128h+var_1108], r13
0x180040aff  mov     r9, r14
0x180040b02  mov     r8, [rsp+1128h+hMem]
0x180040b07  mov     edx, 10000h
0x180040b0c  mov     rcx, [r12+8]
0x180040b11  call    cs:__imp_NtAlpcSendWaitReceivePort
0x180040b17  mov     rax, [rsp+1128h+var_10A0]
0x180040b1f  mov     edi, [rax+44h]
0x180040b22  mov     dword ptr [rax+44h], 0FFFFFFFFh
0x180040b29  cmp     edi, 0FFFFFFFFh
0x180040b2c  jnz     loc_18004154C
0x180040b32  mov     rdi, [rsp+1128h+hMem]
0x180040b37  mov     r8, [rsp+1128h+var_1078]
0x180040b3f  test    r8, r8
0x180040b42  jz      short loc_180040B56
0x180040b44  xor     edx, edx
0x180040b46  mov     rcx, [r12+8]
0x180040b4b  call    cs:__imp_NtAlpcDeletePortSection
0x180040b51  mov     rdi, [rsp+1128h+hMem]
0x180040b56  mov     r14, qword ptr [rsp+1128h+var_10C0.dwLowDateTime]
0x180040b5b  test    esi, esi
0x180040b5d  js      loc_180040D44
0x180040b63  mov     rsi, [rsp+1128h+var_10E0]
0x180040b68  test    r14, r14
0x180040b6b  jnz     loc_180040E20
0x180040b71  mov     r15, [rsp+1128h+var_10A8]
0x180040b79  mov     r12, [rsp+1128h+var_10D8]; jumptable 0000000180040C31 default case, cases 7-11
0x180040b7e  test    r15, r15
0x180040b81  jz      short loc_180040B97
0x180040b83  mov     r8, r15
0x180040b86  xor     edx, edx
0x180040b88  mov     rcx, [r12]
0x180040b8c  call    cs:__imp_NtAlpcDeleteSectionView
0x180040b92  mov     rdi, [rsp+1128h+hMem]
0x180040b97  mov     rax, [rsp+1128h+var_10A0]
0x180040b9f  cmp     dword ptr [rax+0B8h], 0
0x180040ba6  mov     r14, rax
0x180040ba9  mov     r15, [rsp+1128h+var_10C8]
0x180040bae  jz      loc_1800408AA
0x180040bb4  mov     qword ptr [rsp+1128h+var_10C0.dwLowDateTime], r13
0x180040bb9  lea     rcx, [rsp+1128h+var_10C0]; lpSystemTimeAsFileTime
0x180040bbe  call    cs:__imp_GetSystemTimeAsFileTime
0x180040bc4  mov     edi, [rsp+1128h+var_10C0.dwHighDateTime]
0x180040bc8  shl     rdi, 20h
0x180040bcc  mov     eax, [rsp+1128h+var_10C0.dwLowDateTime]
0x180040bd0  or      rdi, rax
0x180040bd3  mov     rax, rdi
0x180040bd6  sub     rax, rbx
0x180040bd9  mov     rcx, 10C388D000h
0x180040be3  cmp     rax, rcx
0x180040be6  jl      loc_180040881
0x180040bec  mov     dl, 1; bool
0x180040bee  mov     rcx, r14; this
0x180040bf1  call    ?SubmitTelemetryData@CCtfServerPort@@AEAAX_N@Z; CCtfServerPort::SubmitTelemetryData(bool)
0x180040bf6  mov     rbx, rdi
0x180040bf9  mov     [rsp+1128h+var_1090], rbx
0x180040c01  mov     [rsp+1128h+var_1070], rbx
0x180040c09  jmp     loc_180040881
0x180040c0e  movzx   eax, dx
0x180040c11  add     eax, 0FFFFFFFEh; switch 11 cases
0x180040c14  cmp     eax, 0Ah
0x180040c17  ja      def_180040C31; jumptable 0000000180040C31 default case, cases 7-11
0x180040c1d  cdqe
0x180040c1f  lea     r8, __ImageBase
0x180040c26  mov     ecx, ds:(jpt_180040C31 - 180000000h)[r8+rax*4]
0x180040c2e  add     rcx, r8
0x180040c31  jmp     rcx; switch jump
0x180040c33  mov     eax, [rdi+30h]; jumptable 0000000180040C31 case 3
0x180040c36  test    eax, eax
0x180040c38  jnz     loc_1800411A4
0x180040c3e  mov     r8d, [rdi+28h]; int
0x180040c42  test    r8d, 50000000h
0x180040c49  jnz     loc_180040EE3
0x180040c4f  mov     r9, r12; struct CCtfServerPort::ClientInfo *
0x180040c52  mov     r8, rsi; struct _ALPC_MESSAGE_ATTRIBUTES *
0x180040c55  lea     rdx, [rsp+1128h+hMem]; struct MsgBase **
0x180040c5a  mov     rcx, r14; this
0x180040c5d  call    ?ProcessMessage@CCtfServerPort@@AEAAJAEAPEAUMsgBase@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@PEAUClientInfo@1@@Z; CCtfServerPort::ProcessMessage(MsgBase * &,_ALPC_MESSAGE_ATTRIBUTES *,CCtfServerPort::ClientInfo *)
0x180040c62  mov     rdi, [rsp+1128h+hMem]
0x180040c67  mov     eax, 2000h
0x180040c6c  mov     rsi, [rsp+1128h+var_10E0]
0x180040c71  mov     r12, [rsp+1128h+var_10D8]
0x180040c76  test    [rdi+4], ax
0x180040c7a  jz      loc_180040B7E
0x180040c80  mov     [rsp+1128h+var_10F0], r13
0x180040c85  mov     [rsp+1128h+var_10F8], r13
0x180040c8a  mov     [rsp+1128h+var_1100], r13
0x180040c8f  mov     [rsp+1128h+var_1108], r13
0x180040c94  mov     r9, rsi
0x180040c97  mov     r8, rdi
0x180040c9a  mov     edx, 10000h
0x180040c9f  mov     rcx, [r12]
0x180040ca3  call    cs:__imp_NtAlpcSendWaitReceivePort
0x180040ca9  mov     rdi, [rsp+1128h+hMem]
0x180040cae  jmp     loc_180040B7E
  ... truncated ...
```
