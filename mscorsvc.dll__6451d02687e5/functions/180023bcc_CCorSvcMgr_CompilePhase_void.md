# CCorSvcMgr::CompilePhase(void)

- ea: `0x180023bcc`
- end: `0x180024514`
- name: `?CompilePhase@CCorSvcMgr@@AEAAXXZ`
- size: `2376`
- prototype: `void __fastcall(CCorSvcMgr *__hidden this)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180023834`

## callees

- `0x180002468`
- `0x180002504`
- `0x1800098f8`
- `0x180009ff4`
- `0x18000a214`
- `0x18000ba88`
- `0x18000c8a8`
- `0x180013954`
- `0x180013b9c`
- `0x180023b40`
- `0x180023bcc`
- `0x180024bf4`
- `0x180026b78`
- `0x1800270b0`
- `0x18002c124`
- `0x18002c5a0`
- `0x18002d3c0`
- `0x18002d624`
- `0x18002db88`
- `0x18002ff64`
- `0x18002ffa4`
- `0x18003000c`
- `0x1800304ec`
- `0x180030568`
- `0x180030ab8`
- `0x180030d84`
- `0x180031a8c`
- `0x18003303c`
- `0x1800330c4`
- `0x180034fd4`
- `0x18003dc30`
- `0x18003dc50`
- `0x18003f280`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800244cb`
- `KERNEL32!HeapFree` at `0x1800244cb`
- `KERNEL32!GetProcessHeap` at `0x1800244b6`
- `KERNEL32!GetProcessHeap` at `0x1800244b6`
- `VCRUNTIME140_CLR0400!wcsrchr` at `0x180024100`
- `VCRUNTIME140_CLR0400!wcsrchr` at `0x180024100`
- `ucrtbase_clr0400!_wcsnicmp` at `0x1800240ef`
- `ucrtbase_clr0400!_wcsnicmp` at `0x18002411d`
- `ucrtbase_clr0400!_wcsnicmp` at `0x1800240ef`
- `ucrtbase_clr0400!_wcsnicmp` at `0x18002411d`
- `ucrtbase_clr0400!_wcsicmp` at `0x180024144`
- `ucrtbase_clr0400!_wcsicmp` at `0x180024144`

## string_xrefs

- `0x18002419d`: `Unable to compile %s.  Please install .NET Framework 2.0 SP2 or above, or .NET Framework 3.5 SP1 or above.\n`

## pseudocode

```c
void __fastcall CCorSvcMgr::CompilePhase(CCorSvcMgr *this)
{
  unsigned int v2; // ebx
  __int64 v3; // rdi
  unsigned int v4; // r13d
  int v5; // eax
  __int64 v6; // r8
  int v7; // eax
  WorkQueue *v8; // r12
  struct Root *i; // rax
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 j; // rbx
  unsigned int *v13; // rdx
  struct Root *v14; // rdi
  unsigned int v15; // r14d
  const unsigned __int8 near *const *v16; // r8
  _QWORD *v17; // rax
  Configuration *v18; // rdi
  Configuration *Configuration; // rbx
  char v20; // di
  int v21; // ebx
  wchar_t *v22; // rbx
  unsigned int v23; // ebx
  unsigned __int64 v24; // rdx
  __int64 v25; // rbx
  __int64 v26; // r15
  __int64 v27; // r14
  __int64 v28; // rax
  __int64 v29; // rbx
  wchar_t *v30; // rax
  wchar_t *v31; // r15
  bool IsV2PreSP2Helper; // al
  __int64 v33; // rax
  __int64 v34; // rdi
  _DWORD *v35; // rax
  void *v36; // rbx
  void *v37; // rbx
  __int64 v38; // rbx
  int v39; // eax
  __int64 v40; // rdi
  __int64 v41; // r14
  int v42; // edx
  __int64 v43; // rdx
  struct Configuration **ReadyCompilationJob; // rdi
  struct ICorSvcWorker **SvcWorkerForConfiguration; // r14
  void *v46; // rbx
  HANDLE ProcessHeap; // rax
  int v48; // [rsp+38h] [rbp-D0h] BYREF
  int v49; // [rsp+3Ch] [rbp-CCh]
  __int64 v50; // [rsp+40h] [rbp-C8h]
  wchar_t *String1; // [rsp+48h] [rbp-C0h]
  __int64 v52; // [rsp+50h] [rbp-B8h] BYREF
  unsigned int v53; // [rsp+58h] [rbp-B0h]
  int v54; // [rsp+60h] [rbp-A8h] BYREF
  int v55; // [rsp+64h] [rbp-A4h]
  __int64 v56; // [rsp+68h] [rbp-A0h]
  void *v57; // [rsp+70h] [rbp-98h]
  void *v58; // [rsp+78h] [rbp-90h]
  BOOL v59; // [rsp+80h] [rbp-88h]
  __int128 v60; // [rsp+88h] [rbp-80h]
  __int64 v61; // [rsp+98h] [rbp-70h]
  __int128 v62; // [rsp+A8h] [rbp-60h] BYREF
  _OWORD v63[2]; // [rsp+B8h] [rbp-50h] BYREF
  _DWORD *v64; // [rsp+D8h] [rbp-30h]
  _DWORD *v65; // [rsp+E0h] [rbp-28h]
  void *v66; // [rsp+E8h] [rbp-20h]
  void *v67; // [rsp+F0h] [rbp-18h]
  unsigned int v68; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v69; // [rsp+FCh] [rbp-Ch]
  LPVOID lpMem; // [rsp+108h] [rbp+0h]
  char v71; // [rsp+110h] [rbp+8h] BYREF
  _DWORD v72[4]; // [rsp+218h] [rbp+110h] BYREF
  char *v73; // [rsp+228h] [rbp+120h]
  char v74; // [rsp+230h] [rbp+128h] BYREF

  v2 = **((_DWORD **)this + 16) >> 3;
  *((_DWORD *)this + 54) = v2;
  v3 = *((_QWORD *)this + 24);
  v4 = 0;
  if ( v3 )
  {
    v5 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v3)(
           *((_QWORD *)this + 24),
           &IID_ICompileProgressNotification2,
           &v52);
    v6 = 3 * v2;
    v7 = v5
       ? (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v3 + 24LL))(v3, v2, v6)
       : (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v52 + 24LL))(v52, v2, v6, 0);
    if ( v7 < 0 )
      ThrowHR(v7);
  }
  v68 = 0;
  v69 = 256;
  lpMem = &v71;
  v8 = (CCorSvcMgr *)((char *)this + 104);
  for ( i = (struct Root *)WorkQueue::GetJob(this, *((_QWORD *)this + 16));
        ;
        i = (struct Root *)WorkQueue::GetJob(v11, *((_QWORD *)this + 16)) )
  {
    v14 = i;
    if ( !i )
      break;
    WorkQueue::AppendJobToSecondaryList((CCorSvcMgr *)((char *)this + 104), i);
    for ( j = (unsigned int)((*((_DWORD *)v14 + 12) >> 3) - 1); (_DWORD)j != -1; j = (unsigned int)(j - 1) )
    {
      v13 = *(unsigned int **)(*((_QWORD *)v14 + 8) + 8 * j);
      v11 = v13[4];
      if ( (unsigned int)(v11 - 2) <= 1 )
      {
        SArray<Root *,1>::Append((SBuffer *)&v68);
      }
      else if ( !(_DWORD)v11 && (*((_DWORD *)v14 + 12) & 0xFFFFFFF8) >= 0x80 )
      {
        CCorSvcMgr::DeleteConfigurationNoThrowOnPerAssemblyFailure(this, (struct Configuration *)v13);
      }
    }
  }
  v72[0] = 0;
  *(_QWORD *)&v72[1] = 240;
  v73 = &v74;
  v15 = 0;
  v16 = &SString::s_EmptyBuffer;
  if ( (v68 & 0xFFFFFFF8) != 0 )
  {
    do
    {
      v17 = lpMem;
      v18 = (Configuration *)*((_QWORD *)lpMem + v15);
      if ( *((_DWORD *)v18 + 4) == 2 && (*((_DWORD *)v18 + 8) & 0xFFFFFFF8) != 0 )
      {
        Configuration = Root::CreateConfiguration(*((Root **)v18 + 1));
        Configuration::DuplicateProperties(Configuration, v18);
        Node::SetStatus(Configuration, 2);
        Node::SetStatus(v18, 0);
        v18 = Configuration;
        v17 = lpMem;
      }
      v17[v15] = v18;
      *(_QWORD *)&v60 = CCorSvcMgr::GetRuntimeForConfiguration;
      DWORD2(v60) = 0;
      v62 = v60;
      CCorSvcMgr::TryProcessEmptyConfiguration(this, v18, &v62);
      if ( (unsigned int)(*((_DWORD *)v18 + 4) - 2) > 1 || *((_DWORD *)v18 + 162) )
      {
        *((_QWORD *)lpMem + v15) = 0;
      }
      else
      {
        v48 = 2;
        v49 = 2;
        LODWORD(v50) = 16;
        String1 = (wchar_t *)&SString::s_EmptyBuffer;
        SBuffer::Set((SBuffer *)&v48, (Configuration *)((char *)v18 + 616));
        LODWORD(v50) = v50 & 0xFFFFFEF8 | *((_DWORD *)v18 + 156) & 7;
        v20 = 0;
        v21 = 0;
        if ( v72[0] / 0x18u )
        {
          while ( !(unsigned int)SString::EqualsCaseInsensitive((SString *)&v48, (const struct SString *)&v73[24 * v21]) )
          {
            if ( ++v21 >= v72[0] / 0x18u )
              goto LABEL_28;
          }
          v20 = 1;
        }
LABEL_28:
        if ( v20 )
        {
          v22 = String1;
        }
        else
        {
          v61 = (__int64)&v54;
          SString::ConvertToUnicode((SString *)&v48);
          v54 = 2;
          v55 = 2;
          LODWORD(v56) = 16;
          v57 = (void *)&SString::s_EmptyBuffer;
          v22 = String1;
          SString::Set((SString *)&v54, String1);
          SArray<SString,0>::Append((SBuffer *)v72, (struct SBuffer *)&v54);
        }
        if ( (v50 & 8) != 0 )
          operator delete(v22);
      }
      ++v15;
    }
    while ( v15 < v68 >> 3 );
    v8 = (CCorSvcMgr *)((char *)this + 104);
    v16 = &SString::s_EmptyBuffer;
  }
  v23 = 0;
  v53 = 0;
  v24 = v72[0] / 0x18uLL;
  if ( (_DWORD)v24 )
  {
    while ( 1 )
    {
      v54 = 2;
      v55 = 2;
      LODWORD(v56) = 16;
      v57 = (void *)&SString::s_EmptyBuffer;
      SString::Set((SString *)&v54, L"v2.");
      v61 = 3LL * v23;
      v25 = (int)SString::BeginsWithCaseInsensitive((SString *)&v73[24 * v23], (const struct SString *)&v54);
      if ( (v56 & 8) != 0 )
        operator delete(v57);
      if ( (_DWORD)v25 && *((_DWORD *)this + 319) )
        CCorSvcMgr::MultiprocCompile(this, 1);
      if ( (v68 & 0xFFFFFFF8) != 0 )
        break;
LABEL_98:
      v23 = v53 + 1;
      v53 = v23;
      v24 = v72[0] / 0x18uLL;
      v4 = 0;
      if ( v23 >= (unsigned int)v24 )
        goto LABEL_99;
    }
    v26 = v25;
    v52 = v25;
    while ( 1 )
    {
      v27 = *((_QWORD *)lpMem + v4);
      if ( v27 )
      {
        v48 = 2;
        v49 = 2;
        LODWORD(v50) = 16;
        String1 = (wchar_t *)&SString::s_EmptyBuffer;
        SBuffer::Set((SBuffer *)&v48, (const struct SBuffer *)(v27 + 616));
        LODWORD(v50) = *(_DWORD *)(v27 + 624) & 7 | v50 & 0xFFFFFFF8;
        LODWORD(v50) = v50 & 0xFFFFFEFF;
        if ( (unsigned int)SString::EqualsCaseInsensitive((SString *)&v48, (const struct SString *)&v73[8 * v61]) )
        {
          if ( !v26 )
            goto LABEL_72;
          v28 = *(_QWORD *)(v27 + 8);
          v29 = *(_QWORD *)(v28 + 24);
          if ( v29 )
          {
            SString::ConvertToUnicode(*(SString **)(v28 + 24));
            v29 = *(_QWORD *)(v29 + 16);
          }
          if ( _wcsnicmp((const wchar_t *)v29, L"msvcm", 5u)
            && ((v30 = wcsrchr((const wchar_t *)v29, 0x5Cu)) == 0 || _wcsnicmp(v30 + 1, L"msvcm", 5u)) )
          {
LABEL_72:
            v31 = String1;
          }
          else
          {
            SString::ConvertToUnicode((SString *)&v48);
            v31 = String1;
            if ( !_wcsicmp(String1, L"v2.0.50727") )
            {
              if ( Helpers::isV2PreSP2 == -1 )
              {
                IsV2PreSP2Helper = Helpers::IsV2PreSP2Helper();
                Helpers::isV2PreSP2 = IsV2PreSP2Helper;
              }
              else
              {
                IsV2PreSP2Helper = Helpers::isV2PreSP2 != 0;
              }
              if ( IsV2PreSP2Helper )
              {
                v33 = *(_QWORD *)(v27 + 8);
                v34 = *(_QWORD *)(v33 + 24);
                if ( v34 )
                {
                  SString::ConvertToUnicode(*(SString **)(v33 + 24));
                  v34 = *(_QWORD *)(v34 + 16);
                }
                Logger::Printf(
                  (CCorSvcMgr *)((char *)this + 208),
                  L"Unable to compile %s.  Please install .NET Framework 2.0 SP2 or above, or .NET Framework 3.5 SP1 or above.\n",
                  v34);
                v35 = operator new(0x18u);
                v36 = v35;
                v64 = v35;
                if ( v35 )
                {
                  v65 = v35;
                  *v35 = 2;
                  v35[1] = 2;
                  v35[2] = 16;
                  *((_QWORD *)v35 + 2) = &SString::s_EmptyBuffer;
                  if ( !v34 )
                    ThrowHR(-2147024736);
                  SString::Set((SString *)v35, (const unsigned __int16 *)v34);
                }
                else
                {
                  v36 = 0;
                }
                v58 = v36;
                v59 = v36 != 0;
                Configuration::CreateLogicalImage((Configuration *)v27);
                Node::SetStatus(v27, 5);
                if ( v59 )
                {
                  v37 = v58;
                  v66 = v58;
                  if ( v58 )
                  {
                    v67 = v58;
                    if ( (*((_BYTE *)v58 + 8) & 8) != 0 )
                      operator delete(*((void **)v58 + 2));
                    operator delete(v37);
                  }
                  v59 = 0;
                }
LABEL_94:
                if ( (v50 & 8) != 0 )
                  operator delete(v31);
                v26 = v52;
                goto LABEL_97;
              }
            }
          }
          v38 = *((_QWORD *)lpMem + v4);
          v39 = *(_DWORD *)(v38 + 16);
          if ( v39 == 2 )
          {
            *(_QWORD *)&v62 = CCorSvcMgr::ExpandEmptyConfiguration;
            DWORD2(v62) = 0;
            v63[0] = v62;
            CCorSvcMgr::TryProcessEmptyConfiguration(this, v38, v63);
            if ( !*(_DWORD *)(v38 + 16) )
            {
              WorkQueue::AppendJobToSecondaryList(v8, *(struct Root **)(v38 + 8));
LABEL_86:
              if ( !*((_DWORD *)this + 319) || v52 )
              {
                ReadyCompilationJob = (struct Configuration **)WorkQueue::GetReadyCompilationJob(v8, 0, 1);
                if ( ReadyCompilationJob )
                {
                  do
                  {
                    SvcWorkerForConfiguration = (struct ICorSvcWorker **)CCorSvcMgr::GetSvcWorkerForConfiguration(
                                                                           this,
                                                                           ReadyCompilationJob[1],
                                                                           0,
                                                                           (struct LogicalImage *)ReadyCompilationJob,
                                                                           0);
                    *(_QWORD *)&v60 = SvcWorkerForConfiguration;
                    DWORD2(v60) = SvcWorkerForConfiguration != 0;
                    CCorSvcMgr::CompileWorker(
                      this,
                      (struct LogicalImage *)ReadyCompilationJob,
                      SvcWorkerForConfiguration[3],
                      0,
                      0);
                    if ( SvcWorkerForConfiguration )
                    {
                      CCorSvcMgr::WorkerPoolItem::~WorkerPoolItem((CCorSvcMgr::WorkerPoolItem *)SvcWorkerForConfiguration);
                      operator delete(SvcWorkerForConfiguration);
                      DWORD2(v60) = 0;
                    }
                    ReadyCompilationJob = (struct Configuration **)WorkQueue::GetReadyCompilationJob(v8, 0, 1);
                  }
                  while ( ReadyCompilationJob );
                  v31 = String1;
                }
              }
              else
              {
                CCorSvcMgr::MultiprocCompile(this, 0);
              }
              goto LABEL_94;
            }
            Node::SetStatus(v38, 3);
            v39 = *(_DWORD *)(v38 + 16);
          }
          if ( v39 == 3 )
          {
            v40 = 0;
            if ( (*(_DWORD *)(v38 + 32) & 0xFFFFFFF8) != 0 )
            {
              do
              {
                v41 = *(_QWORD *)(*(_QWORD *)(v38 + 48) + 8 * v40);
                if ( *(_DWORD *)(v41 + 16) == 3 )
                {
                  v42 = *(_DWORD *)v8 >> 3;
                  if ( *((_DWORD *)v8 + 1) >> 3 == v42 )
                  {
                    v43 = (unsigned int)(16 * v42);
                    if ( (unsigned int)v43 > *((_DWORD *)v8 + 1) )
                      SBuffer::ReallocateBuffer(v8, v43, 1);
                  }
                  SArray<LogicalImage *,1>::End(v8, v63);
                  SBuffer::Replace(v8, (const struct SBuffer::Iterator *)((char *)v63 + 8), 0, 8u);
                  **((_QWORD **)&v63[0] + 1) = v41;
                }
                v40 = (unsigned int)(v40 + 1);
              }
              while ( (unsigned int)v40 < *(_DWORD *)(v38 + 32) >> 3 );
              v31 = String1;
            }
          }
          goto LABEL_86;
        }
        if ( (v50 & 8) != 0 )
          operator delete(String1);
      }
LABEL_97:
      if ( ++v4 >= v68 >> 3 )
        goto LABEL_98;
    }
  }
LABEL_99:
  if ( *((_DWORD *)this + 319) )
    CCorSvcMgr::MultiprocCompile(this, 1);
  SArray<SString,0>::~SArray<SString,0>(v72, v24, v16, v10);
  if ( (v69 & 0x800000000LL) != 0 )
  {
    v46 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v46);
    }
  }
}

```

## disassembly

```asm
0x180023bcc  mov     rax, rsp
0x180023bcf  mov     [rax+10h], rbx
0x180023bd3  mov     [rax+18h], rsi
0x180023bd7  mov     [rax+20h], rdi
0x180023bdb  push    rbp
0x180023bdc  push    r12
0x180023bde  push    r13
0x180023be0  push    r14
0x180023be2  push    r15
0x180023be4  lea     rbp, [rax-258h]
0x180023beb  sub     rsp, 330h
0x180023bf2  mov     rax, cs:__security_cookie
0x180023bf9  xor     rax, rsp
0x180023bfc  mov     [rbp+250h+var_30], rax
0x180023c03  mov     rsi, rcx
0x180023c06  mov     rax, [rcx+80h]
0x180023c0d  mov     ebx, [rax]
0x180023c0f  shr     ebx, 3
0x180023c12  mov     [rcx+0D8h], ebx
0x180023c18  mov     rdi, [rcx+0C0h]
0x180023c1f  xor     r13d, r13d
0x180023c22  test    rdi, rdi
0x180023c25  jz      short loc_180023C7E
0x180023c27  lea     r14d, [rbx+rbx*2]
0x180023c2b  mov     rax, [rdi]
0x180023c2e  lea     r8, [rsp+350h+var_308]
0x180023c33  lea     rdx, IID_ICompileProgressNotification2
0x180023c3a  mov     rcx, rdi
0x180023c3d  mov     rax, [rax]
0x180023c40  call    cs:__guard_dispatch_icall_fptr
0x180023c46  mov     r8d, r14d
0x180023c49  mov     edx, ebx
0x180023c4b  test    eax, eax
0x180023c4d  jnz     short loc_180023C66
0x180023c4f  mov     rcx, [rsp+350h+var_308]
0x180023c54  mov     rax, [rcx]
0x180023c57  xor     r9d, r9d
0x180023c5a  mov     rax, [rax+18h]
0x180023c5e  call    cs:__guard_dispatch_icall_fptr
0x180023c64  jmp     short loc_180023C76
0x180023c66  mov     rax, [rdi]
0x180023c69  mov     rcx, rdi
0x180023c6c  mov     rax, [rax+18h]
0x180023c70  call    cs:__guard_dispatch_icall_fptr
0x180023c76  test    eax, eax
0x180023c78  js      loc_18002450C
0x180023c7e  mov     [rbp+250h+var_260], r13
0x180023c82  mov     [rbp+250h+var_260+4], 100h
0x180023c8a  mov     [rbp+250h+lpMem], r13
0x180023c8e  lea     rax, [rbp+250h+var_248]
0x180023c92  mov     [rbp+250h+lpMem], rax
0x180023c96  lea     r12, [rsi+68h]
0x180023c9a  mov     rdx, [r12+18h]
0x180023c9f  call    ?GetJob@WorkQueue@@AEAAPEAVRoot@@PEAV?$SArray@PEAVRoot@@$00@@@Z; WorkQueue::GetJob(SArray<Root *,1> *)
0x180023ca4  mov     r15d, 1
0x180023caa  or      r14d, 0FFFFFFFFh
0x180023cae  jmp     short loc_180023D11
0x180023cb0  mov     rdx, rdi; struct Root *
0x180023cb3  mov     rcx, r12; this
0x180023cb6  call    ?AppendJobToSecondaryList@WorkQueue@@QEAAXPEAVRoot@@@Z; WorkQueue::AppendJobToSecondaryList(Root *)
0x180023cbb  mov     ebx, [rdi+30h]
0x180023cbe  shr     ebx, 3
0x180023cc1  sub     ebx, r15d
0x180023cc4  jmp     short loc_180023D00
0x180023cc6  mov     rax, [rdi+40h]
0x180023cca  mov     rdx, [rax+rbx*8]; struct Configuration *
0x180023cce  mov     ecx, [rdx+10h]
0x180023cd1  lea     eax, [rcx-2]
0x180023cd4  cmp     eax, r15d
0x180023cd7  jbe     short loc_180023CF4
0x180023cd9  test    ecx, ecx
0x180023cdb  jnz     short loc_180023CFD
0x180023cdd  mov     eax, [rdi+30h]
0x180023ce0  and     eax, 0FFFFFFF8h
0x180023ce3  cmp     eax, 80h
0x180023ce8  jb      short loc_180023CFD
0x180023cea  mov     rcx, rsi; this
0x180023ced  call    ?DeleteConfigurationNoThrowOnPerAssemblyFailure@CCorSvcMgr@@AEAAJPEAVConfiguration@@@Z; CCorSvcMgr::DeleteConfigurationNoThrowOnPerAssemblyFailure(Configuration *)
0x180023cf2  jmp     short loc_180023CFD
0x180023cf4  lea     rcx, [rbp+250h+var_260]; this
0x180023cf8  call    ?Append@?$SArray@PEAVRoot@@$00@@QEAAXPEAVRoot@@@Z; SArray<Root *,1>::Append(Root *)
0x180023cfd  add     ebx, r14d
0x180023d00  cmp     ebx, r14d
0x180023d03  jnz     short loc_180023CC6
0x180023d05  mov     rdx, [rsi+80h]
0x180023d0c  call    ?GetJob@WorkQueue@@AEAAPEAVRoot@@PEAV?$SArray@PEAVRoot@@$00@@@Z; WorkQueue::GetJob(SArray<Root *,1> *)
0x180023d11  test    rax, rax
0x180023d14  mov     rdi, rax
0x180023d17  jnz     short loc_180023CB0
0x180023d19  mov     qword ptr [rbp+250h+var_140], r13
0x180023d20  mov     qword ptr [rbp+250h+var_140+4], 0F0h
0x180023d2b  mov     [rbp+250h+var_130], r13
0x180023d32  lea     rax, [rbp+250h+var_128]
0x180023d39  mov     [rbp+250h+var_130], rax
0x180023d40  mov     r14d, r13d
0x180023d43  lea     r8, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x180023d4a  mov     rax, 0AAAAAAAAAAAAAAABh
0x180023d54  test    dword ptr [rbp+250h+var_260], 0FFFFFFF8h
0x180023d5b  jbe     loc_180023F70
0x180023d61  mov     r12, rax
0x180023d64  mov     r15d, r14d
0x180023d67  mov     rax, [rbp+250h+lpMem]
0x180023d6b  mov     rdi, [rax+r15*8]
0x180023d6f  cmp     dword ptr [rdi+10h], 2
0x180023d73  jnz     short loc_180023DB3
0x180023d75  test    dword ptr [rdi+20h], 0FFFFFFF8h
0x180023d7c  jbe     short loc_180023DB3
0x180023d7e  mov     rcx, [rdi+8]; this
0x180023d82  call    ?CreateConfiguration@Root@@QEAAPEAVConfiguration@@XZ; Root::CreateConfiguration(void)
0x180023d87  mov     rbx, rax
0x180023d8a  mov     rdx, rdi; struct Configuration *
0x180023d8d  mov     rcx, rax; this
0x180023d90  call    ?DuplicateProperties@Configuration@@QEAAXPEAV1@@Z; Configuration::DuplicateProperties(Configuration *)
0x180023d95  mov     edx, 2
0x180023d9a  mov     rcx, rbx
0x180023d9d  call    ?SetStatus@Node@@QEAAXW4EntryStatus@@@Z; Node::SetStatus(EntryStatus)
0x180023da2  xor     edx, edx
0x180023da4  mov     rcx, rdi
0x180023da7  call    ?SetStatus@Node@@QEAAXW4EntryStatus@@@Z; Node::SetStatus(EntryStatus)
0x180023dac  mov     rdi, rbx
0x180023daf  mov     rax, [rbp+250h+lpMem]
0x180023db3  mov     [rax+r15*8], rdi
0x180023db7  lea     rax, ?GetRuntimeForConfiguration@CCorSvcMgr@@AEAAXPEAVConfiguration@@@Z; CCorSvcMgr::GetRuntimeForConfiguration(Configuration *)
0x180023dbe  mov     qword ptr [rbp+250h+var_2D0], rax
0x180023dc2  mov     dword ptr [rbp+250h+var_2D0+8], r13d
0x180023dc6  movaps  xmm0, [rbp+250h+var_2D0]
0x180023dca  movdqa  [rbp+250h+var_2B0], xmm0
0x180023dcf  lea     r8, [rbp+250h+var_2B0]
0x180023dd3  mov     rdx, rdi
0x180023dd6  mov     rcx, rsi
0x180023dd9  call    ?TryProcessEmptyConfiguration@CCorSvcMgr@@AEAAXPEAVConfiguration@@P81@EAAX0@Z@Z; CCorSvcMgr::TryProcessEmptyConfiguration(Configuration *,void (CCorSvcMgr::*)(Configuration *))
0x180023dde  mov     eax, [rdi+10h]
0x180023de1  sub     eax, 2
0x180023de4  mov     r8d, 1
0x180023dea  cmp     eax, r8d
0x180023ded  ja      loc_180023F3B
0x180023df3  cmp     [rdi+288h], r13d
0x180023dfa  jnz     loc_180023F3B
0x180023e00  mov     [rsp+350h+var_320], 2
0x180023e08  mov     [rsp+350h+var_31C], 2
0x180023e10  mov     dword ptr [rsp+350h+var_318], 10h
0x180023e18  lea     r15, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x180023e1f  mov     [rsp+350h+String1], r15
0x180023e24  lea     rbx, [rdi+268h]
0x180023e2b  mov     rdx, rbx; struct SBuffer *
0x180023e2e  lea     rcx, [rsp+350h+var_320]; this
0x180023e33  call    ?Set@SBuffer@@QEAAXAEBV1@@Z; SBuffer::Set(SBuffer const &)
0x180023e38  mov     ecx, [rbx+8]
0x180023e3b  and     ecx, 7
0x180023e3e  mov     eax, dword ptr [rsp+350h+var_318]
0x180023e42  and     eax, 0FFFFFFF8h
0x180023e45  mov     dword ptr [rsp+350h+var_318], eax
0x180023e49  or      ecx, eax
0x180023e4b  mov     dword ptr [rsp+350h+var_318], ecx
0x180023e4f  btr     ecx, 8
0x180023e53  mov     dword ptr [rsp+350h+var_318], ecx
0x180023e57  mov     dil, r13b
0x180023e5a  mov     ebx, r13d
0x180023e5d  mov     ecx, [rbp+250h+var_140]
0x180023e63  mov     rax, r12
0x180023e66  mul     rcx
0x180023e69  shr     rdx, 4
0x180023e6d  test    edx, edx
0x180023e6f  jz      short loc_180023ECA
0x180023e71  mov     r15d, 1
0x180023e77  mov     eax, ebx
0x180023e79  lea     rcx, [rax+rax*2]
0x180023e7d  mov     rax, [rbp+250h+var_130]
0x180023e84  lea     rdx, [rax+rcx*8]; struct SString *
0x180023e88  lea     rcx, [rsp+350h+var_320]; this
0x180023e8d  call    ?EqualsCaseInsensitive@SString@@QEBAHAEBV1@@Z; SString::EqualsCaseInsensitive(SString const &)
0x180023e92  test    eax, eax
0x180023e94  jnz     short loc_180023EB6
0x180023e96  add     ebx, r15d
0x180023e99  mov     ecx, [rbp+250h+var_140]
0x180023e9f  mov     rax, 0AAAAAAAAAAAAAAABh
0x180023ea9  mul     rcx
0x180023eac  shr     rdx, 4
0x180023eb0  cmp     ebx, edx
0x180023eb2  jb      short loc_180023E77
0x180023eb4  jmp     short loc_180023EB9
0x180023eb6  mov     dil, r15b
0x180023eb9  lea     r15, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x180023ec0  mov     r12, 0AAAAAAAAAAAAAAABh
0x180023eca  test    dil, dil
0x180023ecd  jnz     short loc_180023F25
0x180023ecf  lea     rax, [rsp+350h+var_2F8]
0x180023ed4  mov     [rbp+250h+var_2C0], rax
0x180023ed8  lea     rcx, [rsp+350h+var_320]; this
0x180023edd  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180023ee2  mov     [rsp+350h+var_2F8], 2
0x180023eea  mov     [rsp+350h+var_2F4], 2
0x180023ef2  mov     dword ptr [rsp+350h+var_2F0], 10h
0x180023efa  mov     [rsp+350h+var_2E8], r15
0x180023eff  mov     rbx, [rsp+350h+String1]
0x180023f04  mov     rdx, rbx; unsigned __int16 *
0x180023f07  lea     rcx, [rsp+350h+var_2F8]; this
0x180023f0c  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x180023f11  nop
0x180023f12  lea     rdx, [rsp+350h+var_2F8]; struct SBuffer *
0x180023f17  lea     rcx, [rbp+250h+var_140]; this
0x180023f1e  call    ?Append@?$SArray@VSString@@$0A@@@QEAAXVSString@@@Z; SArray<SString,0>::Append(SString)
0x180023f23  jmp     short loc_180023F2A
0x180023f25  mov     rbx, [rsp+350h+String1]
0x180023f2a  test    byte ptr [rsp+350h+var_318], 8
0x180023f2f  jz      short loc_180023F43
0x180023f31  mov     rcx, rbx; lpMem
0x180023f34  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023f39  jmp     short loc_180023F43
0x180023f3b  mov     rax, [rbp+250h+lpMem]
0x180023f3f  mov     [rax+r15*8], r13
0x180023f43  mov     r15d, 1
0x180023f49  add     r14d, r15d
0x180023f4c  mov     eax, dword ptr [rbp+250h+var_260]
0x180023f4f  shr     eax, 3
0x180023f52  cmp     r14d, eax
0x180023f55  jb      loc_180023D64
0x180023f5b  lea     r12, [rsi+68h]
0x180023f5f  mov     rax, 0AAAAAAAAAAAAAAABh
0x180023f69  lea     r8, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x180023f70  mov     ebx, r13d
0x180023f73  mov     [rsp+350h+var_300], ebx
0x180023f77  mov     ecx, [rbp+250h+var_140]
0x180023f7d  mul     rcx
0x180023f80  shr     rdx, 4
0x180023f84  test    edx, edx
0x180023f86  jz      loc_180024479
0x180023f8c  mov     [rsp+350h+var_2F8], 2
0x180023f94  mov     [rsp+350h+var_2F4], 2
0x180023f9c  mov     dword ptr [rsp+350h+var_2F0], 10h
0x180023fa4  mov     [rsp+350h+var_2E8], r8
0x180023fa9  lea     rdx, aV2; "v2."
0x180023fb0  lea     rcx, [rsp+350h+var_2F8]; this
0x180023fb5  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x180023fba  nop
0x180023fbb  mov     eax, ebx
0x180023fbd  lea     rcx, [rax+rax*2]
0x180023fc1  mov     [rbp+250h+var_2C0], rcx
0x180023fc5  mov     rax, [rbp+250h+var_130]
0x180023fcc  lea     rcx, [rax+rcx*8]; this
0x180023fd0  lea     rdx, [rsp+350h+var_2F8]; struct SString *
0x180023fd5  call    ?BeginsWithCaseInsensitive@SString@@QEBAHAEBV1@@Z; SString::BeginsWithCaseInsensitive(SString const &)
0x180023fda  movsxd  rbx, eax
0x180023fdd  test    byte ptr [rsp+350h+var_2F0], 8
0x180023fe2  jz      short loc_180023FEE
0x180023fe4  mov     rcx, [rsp+350h+var_2E8]; lpMem
0x180023fe9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023fee  test    ebx, ebx
0x180023ff0  jz      short loc_180024006
0x180023ff2  cmp     [rsi+4FCh], r13d
0x180023ff9  jz      short loc_180024006
0x180023ffb  mov     dl, r15b; bool
0x180023ffe  mov     rcx, rsi; this
0x180024001  call    ?MultiprocCompile@CCorSvcMgr@@AEAAX_N@Z; CCorSvcMgr::MultiprocCompile(bool)
0x180024006  test    dword ptr [rbp+250h+var_260], 0FFFFFFF8h
0x18002400d  jbe     loc_180024444
0x180024013  mov     r15, rbx
0x180024016  mov     [rsp+350h+var_308], rbx
0x18002401b  mov     edi, r13d
0x18002401e  mov     rax, [rbp+250h+lpMem]
0x180024022  mov     r14, [rax+rdi*8]
0x180024026  test    r14, r14
0x180024029  jz      loc_18002442C
0x18002402f  mov     eax, 2
0x180024034  mov     [rsp+350h+var_320], eax
0x180024038  mov     [rsp+350h+var_31C], eax
0x18002403c  mov     dword ptr [rsp+350h+var_318], 10h
0x180024044  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x18002404b  mov     [rsp+350h+String1], rax
0x180024050  lea     rbx, [r14+268h]
0x180024057  mov     rdx, rbx; struct SBuffer *
0x18002405a  lea     rcx, [rsp+350h+var_320]; this
0x18002405f  call    ?Set@SBuffer@@QEAAXAEBV1@@Z; SBuffer::Set(SBuffer const &)
0x180024064  mov     eax, [rbx+8]
0x180024067  and     eax, 7
0x18002406a  mov     ecx, dword ptr [rsp+350h+var_318]
0x18002406e  and     ecx, 0FFFFFFF8h
0x180024071  mov     dword ptr [rsp+350h+var_318], ecx
0x180024075  or      ecx, eax
0x180024077  mov     dword ptr [rsp+350h+var_318], ecx
0x18002407b  btr     ecx, 8
0x18002407f  mov     dword ptr [rsp+350h+var_318], ecx
0x180024083  mov     rax, [rbp+250h+var_130]
0x18002408a  mov     rcx, [rbp+250h+var_2C0]
0x18002408e  lea     rdx, [rax+rcx*8]; struct SString *
0x180024092  lea     rcx, [rsp+350h+var_320]; this
0x180024097  call    ?EqualsCaseInsensitive@SString@@QEBAHAEBV1@@Z; SString::EqualsCaseInsensitive(SString const &)
0x18002409c  test    eax, eax
0x18002409e  jnz     short loc_1800240BA
0x1800240a0  test    byte ptr [rsp+350h+var_318], 8
0x1800240a5  jz      loc_18002442C
0x1800240ab  mov     rcx, [rsp+350h+String1]; lpMem
0x1800240b0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800240b5  jmp     loc_18002442C
0x1800240ba  test    r15, r15
0x1800240bd  jz      loc_18002426D
0x1800240c3  mov     rax, [r14+8]
0x1800240c7  mov     rbx, [rax+18h]
0x1800240cb  test    rbx, rbx
0x1800240ce  jz      short loc_1800240DC
  ... truncated ...
```
