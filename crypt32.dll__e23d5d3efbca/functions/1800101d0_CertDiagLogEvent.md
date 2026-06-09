# CertDiagLogEvent

- ea: `0x1800101d0`
- end: `0x1800105fb`
- name: `CertDiagLogEvent`
- size: `1067`
- prototype: `__int64 __fastcall(struct _CERT_DIAG_EVENT_STACK_ENTRY *, DWORD dwMessageId)`
- caller_count: `14`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180011cf0`
- `0x180012020`
- `0x18001313c`
- `0x1800140c0`
- `0x180014f38`
- `0x180015d90`
- `0x180055e08`
- `0x18006f778`
- `0x1800952c4`
- `0x18009b118`
- `0x18009b25c`
- `0x1800ad02c`
- `0x1800c1360`
- `0x1800c14b0`

## callees

- `0x18000bae0`
- `0x18000f970`
- `0x1800101d0`
- `0x18001071c`
- `0x180010784`
- `0x18001082c`
- `0x180010af4`
- `0x180015500`
- `0x18008ce18`
- `0x1800bec20`
- `0x1800c165c`
- `0x1800c1908`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800105f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800105f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010562`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010562`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010571`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010571`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800103e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800103e8`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001039b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001039b`
- `ntdll!EtwEventWriteFull` at `0x18001049b`
- `ntdll!EtwEventWriteFull` at `0x18001049b`

## string_xrefs

- `0x1800102d2`: `TaskId`

## pseudocode

```c
void __fastcall CertDiagLogEvent(struct _CERT_DIAG_EVENT_STACK_ENTRY *a1, DWORD dwMessageId, DWORD a3)
{
  __int64 v3; // rbx
  int v6; // edx
  __int64 v7; // r15
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rdi
  unsigned int i; // r15d
  __int64 j; // rcx
  __int64 v13; // rax
  void *v14; // rcx
  void *v15; // rsi
  __int64 v16; // r14
  void *v17; // rdi
  _DWORD *v18; // rdi
  unsigned int v19; // edx
  __int64 v20; // rcx
  __int64 v21; // rax
  char v22; // r9
  __int64 v23; // r10
  __int64 v24; // r8
  __int64 v25; // rsi
  __int128 v26; // xmm0
  _QWORD *v27; // r14
  __int64 v28; // rdx
  __int64 v29; // rax
  __int64 v30; // rdx
  void (__fastcall *v31)(_QWORD, __int64, _QWORD); // rax
  _DWORD *v32; // rcx
  const unsigned __int16 *Committed; // rax
  __int64 v34; // [rsp+40h] [rbp-69h] BYREF
  WCHAR Buffer[4]; // [rsp+48h] [rbp-61h] BYREF
  DWORD v36; // [rsp+50h] [rbp-59h] BYREF
  const wchar_t *v37; // [rsp+60h] [rbp-49h]
  int v38; // [rsp+68h] [rbp-41h]
  __int64 v39; // [rsp+6Ch] [rbp-3Dh]
  int v40; // [rsp+74h] [rbp-35h]
  __int64 v41; // [rsp+78h] [rbp-31h]
  const wchar_t *v42; // [rsp+80h] [rbp-29h]
  int v43; // [rsp+88h] [rbp-21h]
  __int64 v44; // [rsp+8Ch] [rbp-1Dh]
  int v45; // [rsp+94h] [rbp-15h]
  __int64 v46; // [rsp+98h] [rbp-11h]
  __int128 v47; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v48; // [rsp+B0h] [rbp+7h] BYREF
  int v49; // [rsp+B8h] [rbp+Fh]
  int v50; // [rsp+BCh] [rbp+13h]

  v3 = *(_QWORD *)a1;
  v36 = a3;
  v6 = *(_DWORD *)(v3 + 1056);
  if ( (unsigned int)(v6 - 1) <= 9 && a1 == (struct _CERT_DIAG_EVENT_STACK_ENTRY *)(v3 + 104LL * (unsigned int)(v6 - 1)) )
  {
    if ( v3 )
    {
      v7 = v3 + 1064;
      v8 = *(_QWORD *)(v3 + 1064);
      v48 = v3 + 1064;
      v9 = CertDiagStrMemTruncateXmlElements(v8);
      if ( v9 )
      {
        v32 = *(_DWORD **)v7;
        *(_DWORD *)Buffer = v9;
        LODWORD(v34) = 0;
        *(_QWORD *)&v47 = &v34;
        *((_QWORD *)&v47 + 1) = Buffer;
        CertDiagXmlFormatElement(v32);
      }
      if ( *(_DWORD *)(v3 + 1056) == 1 )
      {
        CertDiagPrvFormatAndWinEvtReportX509ObjectsEvent((struct _CERT_DIAG_TLS_INFO *)v3);
        v10 = *(_QWORD *)(v3 + 1088);
        if ( (*(_BYTE *)v10 & 1) == 0 )
          EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 40));
        for ( i = 0; i < *(_DWORD *)(v10 + 32); ++i )
        {
          for ( j = *(_QWORD *)(v10 + 88); *(_QWORD *)(j + 16LL * i + 8); j = *(_QWORD *)(v10 + 88) )
          {
            v27 = *(_QWORD **)(j + 16LL * i + 8);
            v28 = v27[5];
            v29 = v27[6];
            if ( v28 )
              *(_QWORD *)(v28 + 48) = v29;
            else
              *(_QWORD *)(j + 16LL * i + 8) = v29;
            v30 = v27[6];
            if ( v30 )
              *(_QWORD *)(v30 + 40) = v27[5];
            v27[5] = 0;
            v27[6] = 0;
            --*(_DWORD *)(v10 + 80);
            if ( *(_DWORD *)(v10 + 36) )
              *(_DWORD *)(j + 16LL * i) = 0;
            v31 = *(void (__fastcall **)(_QWORD, __int64, _QWORD))(v10 + 24);
            if ( v31 )
              v31(v27[4], v3, 0);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v27, 0xFFFFFFFF) == 1 )
              CLruEntry::`scalar deleting destructor'(v27, v30);
          }
        }
        if ( (*(_BYTE *)v10 & 1) == 0 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 40));
        v13 = *(_QWORD *)(v3 + 1096);
        if ( v13 )
        {
          *(_DWORD *)(v13 + 12) = 0;
          *(_DWORD *)(v13 + 20) = 0;
        }
        v7 = v48;
        *(_DWORD *)(v3 + 1136) = 0;
      }
      CertDiagPrvFormatEventAuxInfo(a1);
      v14 = *(void **)(v3 + 1064);
      v37 = L"TaskId";
      *(_QWORD *)Buffer = v3;
      v42 = L"SeqNumber";
      v38 = 0;
      v39 = 19;
      v40 = 1112;
      v41 = 0;
      v43 = 3;
      v44 = 4;
      v45 = 1128;
      v46 = 0;
      CertDiagXmlFormatElement(v14);
      ++*(_DWORD *)(*(_QWORD *)Buffer + 1128LL);
      v15 = *(void **)(*(_QWORD *)a1 + 1064LL);
      v16 = qword_180120970[4 * *((unsigned int *)a1 + 2) + 3];
      if ( v36 )
      {
        v36 = dwMessageId;
        v17 = 0;
        v34 = 0;
        if ( dwMessageId )
        {
          *(_QWORD *)Buffer = 0;
          FormatMessageW(0x1100u, 0, dwMessageId, 0x400u, Buffer, 0, 0);
          v17 = *(void **)Buffer;
          v34 = *(_QWORD *)Buffer;
          if ( *(_QWORD *)Buffer )
            CertDiagPrvRemoveControlCharacters(*(unsigned __int16 **)Buffer);
        }
        *(_QWORD *)&v47 = &v36;
        *((_QWORD *)&v47 + 1) = &v34;
        CertDiagXmlFormatElement(v15);
        if ( v17 )
          LocalFree(v17);
      }
      CertDiagXmlAppendEndElementName(v15, v16);
      v18 = *(_DWORD **)v7;
      if ( !*(_DWORD *)(*(_QWORD *)v7 + 28LL) )
      {
        v19 = v18[3] - v18[5];
        if ( v19 )
        {
          v20 = (unsigned int)v18[5];
          v21 = *(_QWORD *)v18;
          v22 = *(_BYTE *)(v3 + 1060);
          v23 = *((unsigned int *)a1 + 2);
          LODWORD(v34) = v19 + 1;
          v24 = v21 + 2 * v20;
          *(_WORD *)(v24 + 2LL * v19) = 0;
          if ( v24 )
          {
            v25 = *(_QWORD *)(v3 + 1048);
            if ( qword_180157D50 )
            {
              v26 = *(_OWORD *)qword_180120970[4 * v23 + 2];
              v48 = v21 + 2 * v20;
              v49 = 2 * (v19 + 1);
              v50 = 0;
              v47 = v26;
              BYTE4(v47) = v22;
              EtwEventWriteFull(qword_180157D50, &v47, 1, 0, 0, 1, &v48);
            }
            if ( *(_QWORD *)(v25 + 16) )
            {
              CertDiagPrvXmlFormatExecutionElement(v18, (struct _CERT_DIAG_PROCESS_INFO *)v25);
              Committed = (const unsigned __int16 *)CertDiagStrMemGetCommitted(v18, &v34);
              if ( Committed )
                CertDiagPrvEvtReportTextToXmlFile(*(LPCWSTR *)(v25 + 16), v34 - 1, Committed);
            }
          }
        }
      }
      --*(_DWORD *)(v3 + 1132);
    }
  }
  else
  {
    SetLastError(6u);
  }
}

```

## disassembly

```asm
0x1800101d0  mov     [rsp-8+arg_10], rbx
0x1800101d5  push    rbp
0x1800101d6  push    rsi
0x1800101d7  push    rdi
0x1800101d8  push    r12
0x1800101da  push    r13
0x1800101dc  push    r14
0x1800101de  push    r15
0x1800101e0  lea     rbp, [rsp-27h]
0x1800101e5  sub     rsp, 0D0h
0x1800101ec  mov     rax, cs:__security_cookie
0x1800101f3  xor     rax, rsp
0x1800101f6  mov     [rbp+57h+var_40], rax
0x1800101fa  mov     rbx, [rcx]
0x1800101fd  mov     r13d, edx
0x180010200  mov     [rbp+57h+var_B0], r8d
0x180010204  mov     r12, rcx
0x180010207  mov     edx, [rbx+420h]
0x18001020d  lea     eax, [rdx-1]
0x180010210  cmp     eax, 9
0x180010213  ja      loc_1800105EB
0x180010219  lea     ecx, [rdx-1]
0x18001021c  imul    rax, rcx, 68h ; 'h'
0x180010220  add     rax, rbx
0x180010223  cmp     r12, rax
0x180010226  jnz     loc_1800105EB
0x18001022c  xor     r14d, r14d
0x18001022f  test    rbx, rbx
0x180010232  jz      loc_1800104B1
0x180010238  lea     r15, [rbx+428h]
0x18001023f  mov     rcx, [r15]
0x180010242  mov     [rbp+57h+var_50], r15
0x180010246  call    CertDiagStrMemTruncateXmlElements
0x18001024b  test    eax, eax
0x18001024d  jnz     loc_18001057C
0x180010253  cmp     dword ptr [rbx+420h], 1
0x18001025a  jnz     short loc_1800102C3
0x18001025c  mov     rcx, rbx; struct _CERT_DIAG_TLS_INFO *
0x18001025f  call    ?CertDiagPrvFormatAndWinEvtReportX509ObjectsEvent@@YAXPEAU_CERT_DIAG_TLS_INFO@@@Z; CertDiagPrvFormatAndWinEvtReportX509ObjectsEvent(_CERT_DIAG_TLS_INFO *)
0x180010264  mov     rdi, [rbx+440h]
0x18001026b  test    byte ptr [rdi], 1
0x18001026e  jz      loc_18001056D
0x180010274  mov     r15d, r14d
0x180010277  cmp     [rdi+20h], r14d
0x18001027b  jbe     short loc_18001029B
0x18001027d  mov     rcx, [rdi+58h]
0x180010281  mov     esi, r15d
0x180010284  add     rsi, rsi
0x180010287  cmp     [rcx+rsi*8+8], r14
0x18001028c  jnz     loc_1800104D8
0x180010292  inc     r15d
0x180010295  cmp     r15d, [rdi+20h]
0x180010299  jb      short loc_18001027D
0x18001029b  test    byte ptr [rdi], 1
0x18001029e  jz      loc_18001055E
0x1800102a4  mov     rax, [rbx+448h]
0x1800102ab  test    rax, rax
0x1800102ae  jz      short loc_1800102B8
0x1800102b0  mov     [rax+0Ch], r14d
0x1800102b4  mov     [rax+14h], r14d
0x1800102b8  mov     r15, [rbp+57h+var_50]
0x1800102bc  mov     [rbx+470h], r14d
0x1800102c3  mov     rcx, r12; struct _CERT_DIAG_EVENT_STACK_ENTRY *
0x1800102c6  call    ?CertDiagPrvFormatEventAuxInfo@@YAXPEAU_CERT_DIAG_EVENT_STACK_ENTRY@@@Z; CertDiagPrvFormatEventAuxInfo(_CERT_DIAG_EVENT_STACK_ENTRY *)
0x1800102cb  mov     rcx, [rbx+428h]; void *
0x1800102d2  lea     rax, aTaskid; "TaskId"
0x1800102d9  mov     [rbp+57h+var_A0], rax
0x1800102dd  lea     r9, [rbp+57h+Buffer]
0x1800102e1  lea     rax, aSeqnumber; "SeqNumber"
0x1800102e8  mov     qword ptr [rbp+57h+Buffer], rbx
0x1800102ec  lea     r8, [rbp+57h+var_A0]
0x1800102f0  mov     [rbp+57h+var_80], rax
0x1800102f4  lea     rdx, aCorrelationaux; "CorrelationAuxInfo"
0x1800102fb  mov     [rbp+57h+var_98], r14d
0x1800102ff  mov     [rbp+57h+var_94], 13h
0x180010307  mov     [rbp+57h+var_8C], 458h
0x18001030e  mov     [rbp+57h+var_88], r14
0x180010312  mov     [rbp+57h+var_78], 3
0x180010319  mov     [rbp+57h+var_74], 4
0x180010321  mov     [rbp+57h+var_6C], 468h
0x180010328  mov     [rbp+57h+var_68], r14
0x18001032c  call    CertDiagXmlFormatElement
0x180010331  mov     rax, qword ptr [rbp+57h+Buffer]
0x180010335  lea     rcx, qword_180120970
0x18001033c  inc     dword ptr [rax+468h]
0x180010342  mov     rax, [r12]
0x180010346  mov     rsi, [rax+428h]
0x18001034d  mov     eax, [r12+8]
0x180010352  shl     rax, 5
0x180010356  mov     r14, [rax+rcx+18h]
0x18001035b  xor     eax, eax
0x18001035d  cmp     [rbp+57h+var_B0], eax
0x180010360  jz      loc_1800103EE
0x180010366  mov     [rbp+57h+var_B0], r13d
0x18001036a  mov     edi, eax
0x18001036c  mov     [rbp+57h+var_C0], rax
0x180010370  test    r13d, r13d
0x180010373  jz      short loc_1800103B6
0x180010375  mov     [rsp+100h+Arguments], rax; Arguments
0x18001037a  mov     r9d, 400h; dwLanguageId
0x180010380  mov     [rsp+100h+nSize], eax; nSize
0x180010384  mov     r8d, r13d; dwMessageId
0x180010387  mov     qword ptr [rbp+57h+Buffer], rax
0x18001038b  xor     edx, edx; lpSource
0x18001038d  lea     rax, [rbp+57h+Buffer]
0x180010391  mov     ecx, 1100h; dwFlags
0x180010396  mov     [rsp+100h+lpBuffer], rax; lpBuffer
0x18001039b  call    cs:__imp_FormatMessageW
0x1800103a1  mov     rdi, qword ptr [rbp+57h+Buffer]
0x1800103a5  mov     [rbp+57h+var_C0], rdi
0x1800103a9  test    rdi, rdi
0x1800103ac  jz      short loc_1800103B6
0x1800103ae  mov     rcx, rdi; unsigned __int16 *
0x1800103b1  call    ?CertDiagPrvRemoveControlCharacters@@YAXPEAG@Z; CertDiagPrvRemoveControlCharacters(ushort *)
0x1800103b6  lea     rax, [rbp+57h+var_B0]
0x1800103ba  mov     rcx, rsi; void *
0x1800103bd  mov     qword ptr [rbp+57h+var_60], rax
0x1800103c1  lea     r9, [rbp+57h+var_60]
0x1800103c5  lea     rax, [rbp+57h+var_C0]
0x1800103c9  lea     r8, off_180120E40; "value"
0x1800103d0  mov     qword ptr [rbp+57h+var_60+8], rax
0x1800103d4  lea     rdx, aResult; "Result"
0x1800103db  call    CertDiagXmlFormatElement
0x1800103e0  test    rdi, rdi
0x1800103e3  jz      short loc_1800103EE
0x1800103e5  mov     rcx, rdi; hMem
0x1800103e8  call    cs:__imp_LocalFree
0x1800103ee  mov     rdx, r14
0x1800103f1  mov     rcx, rsi
0x1800103f4  call    CertDiagXmlAppendEndElementName
0x1800103f9  mov     rdi, [r15]
0x1800103fc  xor     r15d, r15d
0x1800103ff  cmp     [rdi+1Ch], r15d
0x180010403  jnz     loc_1800104AB
0x180010409  mov     edx, [rdi+0Ch]
0x18001040c  sub     edx, [rdi+14h]
0x18001040f  jz      loc_1800104AB
0x180010415  mov     ecx, [rdi+14h]
0x180010418  lea     r14d, [rdx+1]
0x18001041c  mov     rax, [rdi]
0x18001041f  mov     r9b, [rbx+424h]
0x180010426  mov     r10d, [r12+8]
0x18001042b  mov     dword ptr [rbp+57h+var_C0], r14d
0x18001042f  lea     r8, [rax+rcx*2]
0x180010433  mov     [r8+rdx*2], r15w
0x180010438  test    r8, r8
0x18001043b  jz      short loc_1800104AB
0x18001043d  mov     rcx, cs:qword_180157D50
0x180010444  mov     rsi, [rbx+418h]
0x18001044b  test    rcx, rcx
0x18001044e  jz      short loc_1800104A1
0x180010450  lea     rdx, qword_180120970
0x180010457  shl     r10, 5
0x18001045b  mov     rax, [r10+rdx+10h]
0x180010460  lea     edx, [r15+1]
0x180010464  movups  xmm0, xmmword ptr [rax]
0x180010467  lea     eax, [r14+r14]
0x18001046b  mov     [rbp+57h+var_50], r8
0x18001046f  mov     [rbp+57h+var_48], eax
0x180010472  mov     r8d, edx
0x180010475  lea     rax, [rbp+57h+var_50]
0x180010479  mov     [rbp+57h+var_44], r15d
0x18001047d  mov     [rsp+100h+Arguments], rax
0x180010482  mov     [rsp+100h+nSize], edx
0x180010486  lea     rdx, [rbp+57h+var_60]
0x18001048a  movdqu  [rbp+57h+var_60], xmm0
0x18001048f  mov     byte ptr [rbp+57h+var_60+4], r9b
0x180010493  xor     r9d, r9d
0x180010496  mov     [rsp+100h+lpBuffer], r15
0x18001049b  call    cs:__imp_EtwEventWriteFull
0x1800104a1  cmp     [rsi+10h], r15
0x1800104a5  jnz     loc_1800105B2
0x1800104ab  dec     dword ptr [rbx+46Ch]
0x1800104b1  mov     rcx, [rbp+57h+var_40]
0x1800104b5  xor     rcx, rsp; StackCookie
0x1800104b8  call    __security_check_cookie
0x1800104bd  mov     rbx, [rsp+100h+arg_10]
0x1800104c5  add     rsp, 0D0h
0x1800104cc  pop     r15
0x1800104ce  pop     r14
0x1800104d0  pop     r13
0x1800104d2  pop     r12
0x1800104d4  pop     rdi
0x1800104d5  pop     rsi
0x1800104d6  pop     rbp
0x1800104d7  retn
0x1800104d8  mov     r14, [rcx+rsi*8+8]
0x1800104dd  xor     r8d, r8d
0x1800104e0  mov     rdx, [r14+28h]
0x1800104e4  mov     rax, [r14+30h]
0x1800104e8  test    rdx, rdx
0x1800104eb  jnz     short loc_180010552
0x1800104ed  mov     [rcx+rsi*8+8], rax
0x1800104f2  mov     rdx, [r14+30h]
0x1800104f6  test    rdx, rdx
0x1800104f9  jz      short loc_180010503
0x1800104fb  mov     rax, [r14+28h]
0x1800104ff  mov     [rdx+28h], rax
0x180010503  mov     [r14+28h], r8
0x180010507  mov     [r14+30h], r8
0x18001050b  dec     dword ptr [rdi+50h]
0x18001050e  cmp     [rdi+24h], r8d
0x180010512  jnz     short loc_180010558
0x180010514  mov     rax, [rdi+18h]
0x180010518  test    rax, rax
0x18001051b  jz      short loc_180010529
0x18001051d  mov     rcx, [r14+20h]
0x180010521  mov     rdx, rbx
0x180010524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010529  or      eax, 0FFFFFFFFh
0x18001052c  lock xadd [r14], eax
0x180010531  cmp     eax, 1
0x180010534  jnz     short loc_18001053E
0x180010536  mov     rcx, r14; hMem
0x180010539  call    ??_GCLruEntry@@QEAAPEAXI@Z; CLruEntry::`scalar deleting destructor'(uint)
0x18001053e  mov     rcx, [rdi+58h]
0x180010542  xor     r14d, r14d
0x180010545  cmp     [rcx+rsi*8+8], r14
0x18001054a  jz      loc_180010292
0x180010550  jmp     short loc_1800104D8
0x180010552  mov     [rdx+30h], rax
0x180010556  jmp     short loc_1800104F2
0x180010558  mov     [rcx+rsi*8], r8d
0x18001055c  jmp     short loc_180010514
0x18001055e  lea     rcx, [rdi+28h]; lpCriticalSection
0x180010562  call    cs:__imp_LeaveCriticalSection
0x180010568  jmp     loc_1800102A4
0x18001056d  lea     rcx, [rdi+28h]; lpCriticalSection
0x180010571  call    cs:__imp_EnterCriticalSection
0x180010577  jmp     loc_180010274
0x18001057c  mov     rcx, [r15]; void *
0x18001057f  lea     r9, [rbp+57h+var_60]
0x180010583  mov     dword ptr [rbp+57h+Buffer], eax
0x180010586  lea     r8, off_180122CC0; "objectCount"
0x18001058d  lea     rax, [rbp+57h+var_C0]
0x180010591  mov     dword ptr [rbp+57h+var_C0], r14d
0x180010595  mov     qword ptr [rbp+57h+var_60], rax
0x180010599  lea     rdx, aEventoverflow; "EventOverflow"
0x1800105a0  lea     rax, [rbp+57h+Buffer]
0x1800105a4  mov     qword ptr [rbp+57h+var_60+8], rax
0x1800105a8  call    CertDiagXmlFormatElement
0x1800105ad  jmp     loc_180010253
0x1800105b2  mov     r8d, r14d; unsigned int
0x1800105b5  mov     rdx, rsi; struct _CERT_DIAG_PROCESS_INFO *
0x1800105b8  mov     rcx, rdi; void *
0x1800105bb  call    ?CertDiagPrvXmlFormatExecutionElement@@YAXPEAXPEAU_CERT_DIAG_PROCESS_INFO@@K@Z; CertDiagPrvXmlFormatExecutionElement(void *,_CERT_DIAG_PROCESS_INFO *,ulong)
0x1800105c0  lea     rdx, [rbp+57h+var_C0]
0x1800105c4  mov     rcx, rdi
0x1800105c7  call    CertDiagStrMemGetCommitted
0x1800105cc  test    rax, rax
0x1800105cf  jz      loc_1800104AB
0x1800105d5  mov     edx, dword ptr [rbp+57h+var_C0]
0x1800105d8  mov     r8, rax; unsigned __int16 *
0x1800105db  mov     rcx, [rsi+10h]; lpFileName
0x1800105df  dec     edx; unsigned int
0x1800105e1  call    ?CertDiagPrvEvtReportTextToXmlFile@@YAHPEBGK0@Z; CertDiagPrvEvtReportTextToXmlFile(ushort const *,ulong,ushort const *)
0x1800105e6  jmp     loc_1800104AB
0x1800105eb  mov     ecx, 6; dwErrCode
0x1800105f0  call    cs:__imp_SetLastError
0x1800105f6  jmp     loc_1800104B1
```
