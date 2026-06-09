# NetworkIncident::Diagnose(long *)

- ea: `0x18000a3e8`
- end: `0x18000ac41`
- name: `?Diagnose@NetworkIncident@@QEAAJPEAJ@Z`
- size: `2137`
- prototype: `__int64 __fastcall(NetworkIncident *__hidden this, int *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180018ae4`

## callees

- `0x180005350`
- `0x18000579c`
- `0x180006d58`
- `0x180006df8`
- `0x1800083a0`
- `0x180008c84`
- `0x1800091a4`
- `0x1800096c8`
- `0x180009b8c`
- `0x180009c5c`
- `0x18000a2f4`
- `0x18000a3e8`
- `0x18000bca0`
- `0x18000c42c`
- `0x18000cba0`
- `0x18000ec4c`
- `0x18000ede4`
- `0x18000f324`
- `0x180012b44`
- `0x18001b3a8`
- `0x18002c840`
- `0x18002f010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000a4bb`
- `KERNEL32!EnterCriticalSection` at `0x18000a4bb`
- `KERNEL32!LeaveCriticalSection` at `0x18000a52c`
- `KERNEL32!LeaveCriticalSection` at `0x18000a52c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a82d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a82d`

## string_xrefs

- `0x18000a814`: `Could not update the progress string. HRESULT: 0x%x`
- `0x18000a875`: `Warning: HelperClass '%s' not found in the HC Discovery Registry. HRESULT: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NetworkIncident::Diagnose(NetworkIncident *this, int *a2)
{
  int *v2; // r14
  NetworkIncident *v3; // rsi
  NetworkIncident *v4; // r15
  _DWORD *v5; // rbx
  _DWORD *v6; // rax
  __int64 v7; // rcx
  __int64 v9; // rcx
  int ***v10; // r13
  __int64 v11; // r8
  __int64 *v12; // rcx
  __int64 v13; // rax
  int **v14; // rax
  int *v15; // r15
  _QWORD *v16; // rbx
  __int64 v17; // rdx
  int **v18; // rcx
  __int64 v19; // r14
  _DWORD *v20; // r14
  __int64 v21; // rcx
  int v22; // ebx
  __int64 v23; // r8
  __int64 v24; // rbx
  __int64 v25; // rcx
  int *v26; // rdx
  __int64 v27; // rbx
  int v28; // edx
  int v29; // eax
  int v30; // ebx
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  int *v35; // r14
  enum tagDIAGNOSIS_STATUS v36; // eax
  enum tagDIAGNOSIS_STATUS v37; // r15d
  enum tagDIAGNOSIS_STATUS v38; // eax
  int **v39; // rax
  int v40; // ebx
  __int64 v41; // rcx
  __int64 *v42; // rbx
  unsigned int *TickCount; // rax
  __int64 v44; // r10
  unsigned __int64 v45; // rdx
  int v46; // eax
  int v47; // eax
  __int64 v48; // [rsp+20h] [rbp-108h]
  char v49; // [rsp+30h] [rbp-F8h]
  int *v50; // [rsp+38h] [rbp-F0h]
  int v51; // [rsp+40h] [rbp-E8h]
  LPVOID pv; // [rsp+48h] [rbp-E0h] BYREF
  NetworkIncident *v53; // [rsp+50h] [rbp-D8h]
  ProblemInstance *v54; // [rsp+58h] [rbp-D0h]
  __int64 v55; // [rsp+60h] [rbp-C8h] BYREF
  __int64 v56; // [rsp+68h] [rbp-C0h] BYREF
  __int64 v57; // [rsp+70h] [rbp-B8h] BYREF
  NetworkIncident *v58; // [rsp+78h] [rbp-B0h]
  _DWORD *v59; // [rsp+80h] [rbp-A8h]
  __int64 *v60; // [rsp+88h] [rbp-A0h]
  struct NetworkDiagnosticsEngine *v61; // [rsp+90h] [rbp-98h] BYREF
  int *v62; // [rsp+98h] [rbp-90h]
  int ***v63; // [rsp+A0h] [rbp-88h]
  ProblemInstance *v64; // [rsp+A8h] [rbp-80h]
  __int64 *v65; // [rsp+B0h] [rbp-78h] BYREF
  unsigned __int64 v66; // [rsp+C0h] [rbp-68h]
  char v67[16]; // [rsp+C8h] [rbp-60h] BYREF
  char v68[16]; // [rsp+D8h] [rbp-50h] BYREF
  const ATL::CAtlException *v69; // [rsp+E8h] [rbp-40h] BYREF

  v2 = a2;
  v50 = a2;
  v3 = this;
  v58 = this;
  v4 = this;
  v53 = this;
  v62 = a2;
  v51 = 2;
  v61 = NetworkDiagnosticsEngine::Instance();
  v5 = (_DWORD *)((char *)v4 + 24);
  while ( 1 )
  {
    v60 = (__int64 *)((char *)v4 + 272);
    if ( !*((_QWORD *)v4 + 34) )
    {
      v6 = v5;
      goto LABEL_108;
    }
    v59 = (_DWORD *)((char *)v3 + 352);
    if ( *((_DWORD *)v3 + 88) > 0x3E8u )
      break;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 312));
    std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>(
      (std::_Iterator_base12 *)&v65,
      *((_QWORD *)v3 + 33),
      (NetworkIncident *)((char *)v3 + 240));
    if ( v65 )
      v9 = *v65;
    else
      v9 = 0;
    v10 = (int ***)((char *)v3 + 16);
    v63 = (int ***)((char *)v3 + 16);
    *((_QWORD *)v3 + 2) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v9 + 8) + 8 * ((v66 >> 1) & (*(_QWORD *)(v9 + 16) - 1LL)))
                                    + 8 * (v66 & 1));
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 312));
    v12 = v60;
    if ( *v60 )
    {
      v13 = *v60 - 1;
      *v60 = v13;
      if ( v13 )
        ++*((_QWORD *)v4 + 33);
      else
        *((_QWORD *)v4 + 33) = 0;
    }
    v14 = *v10;
    v15 = **v10;
    v54 = (ProblemInstance *)v15;
    v64 = (ProblemInstance *)v15;
    if ( !*((_DWORD *)v14 + 8) || *((_DWORD *)v14 + 8) == 7 )
    {
      if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)v15 + 9) + 144LL))(*((_QWORD *)v15 + 9)) )
      {
        pv = 0;
        if ( (int)ATL::CComObject<CNetDiagHelperUtilFactory>::CreateInstance(&pv) >= 0 )
        {
          v16 = pv;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 8LL))(pv);
          v17 = *((_QWORD *)v3 + 27);
          v18 = *v10;
          v16[8] = *((_QWORD *)v3 + 10);
          v16[9] = v18;
          v16[10] = v17;
          v55 = 0;
          if ( (*(int (__fastcall **)(_QWORD *, GUID *, __int64 *))*v16)(
                 v16,
                 &GUID_104613fb_bc57_4178_95ba_88809698354a,
                 &v55) >= 0 )
          {
            v19 = v55;
            if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)v15 + 9) + 144LL))(*((_QWORD *)v15 + 9)) )
              (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v15 + 9) + 160LL))(*((_QWORD *)v15 + 9), v19);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
          }
          (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
        }
      }
    }
    v20 = (_DWORD *)((char *)v3 + 232);
    pv = (char *)v3 + 232;
    if ( !*((_DWORD *)v3 + 58) )
    {
      if ( (byte_180041BC1 & 4) != 0 )
        McGenEventWrite_EventWriteTransfer(v12, StartNDFReproFailure, v11, 1, v67);
      v22 = NetworkIncident::ReproduceFailure(v3, *v10);
      if ( (byte_180041BC1 & 4) != 0 )
        McGenEventWrite_EventWriteTransfer(v21, StopNDFReproFailure, v23, 1, v68);
      if ( v22 < 0 && *((_QWORD *)v3 + 27) )
      {
        if ( __eh34_try(-1, 0) )
        {
          __eh34_scope_strut(0);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v56);
          if ( v22 == -2147467263 )
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
              &v56,
              "ReproduceFailure not implemented by the entry point helper class.");
          else
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
              (__int64)&v56,
              (__int64)L"ReproduceFailure() failed with hr=0x%08X",
              (unsigned int)v22);
          v24 = v56;
          (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)v3 + 27) + 96LL))(
            *((_QWORD *)v3 + 27),
            0,
            v56);
          ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
        }
        if ( __eh34_catch(0) )
        {
          if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v69) )
          {
            (*(void (__fastcall **)(_QWORD, _QWORD, const wchar_t *))(**((_QWORD **)v58 + 27) + 96LL))(
              *((_QWORD *)v58 + 27),
              0,
              L"ReproduceFailure() failed");
            v50 = v62;
            v3 = v58;
            v10 = v63;
            v20 = pv;
            v15 = (int *)v64;
            v54 = v64;
            __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000A735);
          }
        }
      }
      *v20 = 1;
    }
    if ( *((_QWORD *)v3 + 10) )
    {
      if ( v61 )
      {
        v25 = *((_QWORD *)v61 + 3);
        if ( v25 )
        {
          v26 = **v10;
          v27 = *((_QWORD *)v26 + 2);
          if ( !*(_DWORD *)(v27 - 16) )
            v27 = *(_QWORD *)v26;
          v57 = 0;
          v28 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v25 + 24LL))(v25, v27, &v57);
          if ( v28 < 0 )
          {
            v34 = *((_QWORD *)v3 + 27);
            if ( v34 )
            {
              LODWORD(v48) = v28;
              (*(void (**)(__int64, _QWORD, const wchar_t *, ...))(*(_QWORD *)v34 + 104LL))(
                v34,
                0,
                L"Warning: HelperClass '%s' not found in the HC Discovery Registry. HRESULT: 0x%x",
                v27,
                v48);
            }
LABEL_55:
            DiagnosticsClient::SetProgress(*((DiagnosticsClient **)v3 + 10), &dword_180033E1C);
          }
          else
          {
            pv = 0;
            v29 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v57 + 64LL))(v57, &pv);
            v30 = v29;
            if ( v29 < 0 )
            {
              v33 = *((_QWORD *)v3 + 27);
              if ( v33 )
                (*(void (**)(__int64, _QWORD, const wchar_t *, ...))(*(_QWORD *)v33 + 104LL))(
                  v33,
                  0,
                  L"Could not retrieve the current HC's progress string. HRESULT: 0x%x",
                  (unsigned int)v29);
            }
            else
            {
              v31 = DiagnosticsClient::SetProgress(*((DiagnosticsClient **)v3 + 10), (const unsigned __int16 *)0xC8, pv);
              v30 = v31;
              if ( v31 < 0 )
              {
                v32 = *((_QWORD *)v3 + 27);
                if ( v32 )
                  (*(void (**)(__int64, _QWORD, const wchar_t *, ...))(*(_QWORD *)v32 + 104LL))(
                    v32,
                    0,
                    L"Could not update the progress string. HRESULT: 0x%x",
                    (unsigned int)v31);
                v30 = 0;
              }
              CoTaskMemFree(pv);
            }
            if ( v30 < 0 )
              goto LABEL_55;
          }
          ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(&v57);
        }
      }
    }
    v49 = 0;
    v5 = (_DWORD *)((char *)v3 + 24);
    v6 = (_DWORD *)((char *)v3 + 24);
    if ( ((*((_DWORD *)*v10 + 6) - 2) & 0xFFFFFFFD) != 0 )
    {
      if ( *v5 == 13 )
        goto LABEL_107;
      v51 = 8;
      v35 = v15 + 57;
      if ( v15[57] >= 0 )
        goto LABEL_62;
      if ( (*(int (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 10) + 56LL))(*((_QWORD *)v3 + 10)) >= 0 )
      {
        v49 = 1;
LABEL_62:
        v36 = (enum tagDIAGNOSIS_STATUS)ProblemInstance::Diagnose((ProblemInstance *)v15, v50, 0);
LABEL_74:
        v37 = v36;
        goto LABEL_87;
      }
      v37 = DS_INDETERMINATE;
      goto LABEL_87;
    }
    if ( *v5 == 13 )
      goto LABEL_107;
    v35 = v15 + 57;
    if ( v15[57] >= 0 )
      goto LABEL_68;
    if ( (*(int (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 10) + 56LL))(*((_QWORD *)v3 + 10)) >= 0 )
    {
      v49 = 1;
LABEL_68:
      v37 = (enum tagDIAGNOSIS_STATUS)ProblemInstance::Diagnose((ProblemInstance *)v15, v50, 1u);
      goto LABEL_69;
    }
    v37 = DS_INDETERMINATE;
LABEL_69:
    if ( v37 == DS_REJECTED )
    {
      v6 = (_DWORD *)((char *)v3 + 24);
      if ( *v5 == 13 )
        goto LABEL_107;
      v36 = (enum tagDIAGNOSIS_STATUS)ProblemInstance::Diagnose(v54, v50, 0);
      if ( v36 == DS_CONFIRMED || v36 == DS_DEFERRED )
      {
        v51 = 8;
        goto LABEL_74;
      }
    }
    else if ( ((v37 - 3) & 0xFFFFFFFD) != 0 || *v35 < 0 && !v49 )
    {
      if ( v37 == DS_CONFIRMED || v37 == DS_DEFERRED )
        v51 = 1;
    }
    else
    {
      v6 = (_DWORD *)((char *)v3 + 24);
      if ( *v5 == 13 )
      {
LABEL_107:
        v4 = v53;
        v2 = v50;
LABEL_108:
        if ( *v6 == 13 )
          return 2147500036LL;
        if ( *((_QWORD *)v4 + 36) )
        {
          v42 = *(__int64 **)(**((_QWORD **)v3 + 35) + 16LL);
          TickCount = (unsigned int *)ATL::CFileTime::GetTickCount((struct _FILETIME *)&v61);
          v44 = *v42;
          if ( *((_DWORD *)v42 + 7) == 1 )
          {
            v45 = ((*TickCount - ((unsigned int)*(_QWORD *)(v44 + 184) | *(_QWORD *)(v44 + 184) & 0xFFFFFFFF00000000uLL))
                 * (unsigned __int128)0xD6BF94D5E57A42BDuLL) >> 64;
            v46 = *(_DWORD *)(v44 + 200);
          }
          else
          {
            v45 = ((*TickCount - ((unsigned int)*(_QWORD *)(v44 + 192) | *(_QWORD *)(v44 + 192) & 0xFFFFFFFF00000000uLL))
                 * (unsigned __int128)0xD6BF94D5E57A42BDuLL) >> 64;
            v46 = *(_DWORD *)(v44 + 204);
          }
          v47 = v46 - (v45 >> 23);
          *v2 = v47;
          if ( v47 < 0 )
            *v2 = 0;
          return 2147483658LL;
        }
        else
        {
          v40 = NetworkIncident::SecondPassDiagnosis(v3);
          if ( v40 >= 0 )
          {
            v41 = *((_QWORD *)v3 + 15);
            if ( v41 )
              (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v41 + 112LL))(v41, *((unsigned int *)v3 + 88));
          }
          return (unsigned int)v40;
        }
      }
      v38 = (enum tagDIAGNOSIS_STATUS)ProblemInstance::Diagnose(v54, v50, 0);
      if ( v38 == DS_CONFIRMED )
      {
        v51 = 8;
        v37 = DS_CONFIRMED;
      }
      else
      {
        v51 = 1;
        if ( v38 == DS_DEFERRED )
          *v50 = 0;
      }
    }
LABEL_87:
    if ( *v35 < 0 && v49 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 10) + 64LL))(*((_QWORD *)v3 + 10));
    *((_DWORD *)v54 + 59) = v37;
    switch ( v37 )
    {
      case DS_CONFIRMED:
        goto LABEL_95;
      case DS_REJECTED:
        ++*v59;
        *((_DWORD *)*v10 + 8) = 8;
        goto LABEL_102;
      case DS_INDETERMINATE:
        goto LABEL_95;
    }
    if ( v37 != DS_DEFERRED )
    {
      if ( v37 == DS_PASSTHROUGH )
      {
LABEL_95:
        ++*v59;
        *((_DWORD *)*v10 + 7) = v51;
        v39 = *v10;
        if ( v37 == DS_CONFIRMED )
        {
          *((_DWORD *)v39 + 8) = 10;
          _InterlockedCompareExchange((volatile signed __int32 *)v3 + 22, 1, 0);
        }
        else
        {
          *((_DWORD *)v39 + 8) = 9;
        }
        NetworkIncident::UpdateCoveredPathAnnotation(v3, (struct ProblemNode *)*v10, 1);
        if ( *v5 != 13 )
          NetworkIncident::Handoff(v3, (struct ProblemNode *)*v10);
      }
LABEL_102:
      v2 = v50;
      goto LABEL_103;
    }
    *((_DWORD *)*v10 + 7) = v51;
    *((_DWORD *)*v10 + 8) = 2;
    v2 = v50;
    NetworkIncident::AddDeferredProblem(v3, (struct ProblemNode *)*v10, *v50);
LABEL_103:
    if ( !*v60 && *v5 != 13 )
    {
      NetworkIncident::CheckIndeterminateCauses(v3);
      NetworkIncident::CheckDeferredProblems(v3);
    }
    v4 = v53;
  }
  v7 = *((_QWORD *)v3 + 27);
  if ( v7 )
    (*(void (__fastcall **)(__int64, _QWORD, const wchar_t *))(*(_QWORD *)v7 + 96LL))(
      v7,
      0,
      L"Diagnostics session was aborted. The limit for total number of helper classes in a scenario was reached.");
  return 2147500037LL;
}

```

## disassembly

```asm
0x18000a3e8  mov     [rsp+arg_10], rbx
0x18000a3ed  mov     [rsp+arg_18], rsi
0x18000a3f2  push    rdi
0x18000a3f3  push    r12
0x18000a3f5  push    r13
0x18000a3f7  push    r14
0x18000a3f9  push    r15
0x18000a3fb  sub     rsp, 100h
0x18000a402  mov     rax, cs:__security_cookie
0x18000a409  xor     rax, rsp
0x18000a40c  mov     [rsp+128h+var_38], rax
0x18000a414  mov     r14, rdx
0x18000a417  mov     [rsp+128h+var_F0], rdx
0x18000a41c  mov     rsi, rcx
0x18000a41f  mov     [rsp+128h+var_B0], rcx
0x18000a424  mov     r15, rcx
0x18000a427  mov     [rsp+128h+var_D8], rcx
0x18000a42c  mov     [rsp+128h+var_90], rdx
0x18000a434  mov     [rsp+128h+var_E8], 2
0x18000a43c  call    ?Instance@NetworkDiagnosticsEngine@@SAPEAV1@XZ; NetworkDiagnosticsEngine::Instance(void)
0x18000a441  mov     [rsp+128h+var_98], rax
0x18000a449  lea     rbx, [r15+18h]
0x18000a44d  xor     edi, edi
0x18000a44f  lea     r12d, [rdi+1]
0x18000a453  lea     rax, [r15+110h]
0x18000a45a  mov     [rsp+128h+var_A0], rax
0x18000a462  cmp     [rax], rdi
0x18000a465  jnz     short loc_18000A46F
0x18000a467  mov     rax, rbx
0x18000a46a  jmp     loc_18000AB22
0x18000a46f  lea     rax, [rsi+160h]
0x18000a476  mov     [rsp+128h+var_A8], rax
0x18000a47e  cmp     dword ptr [rax], 3E8h
0x18000a484  jbe     short loc_18000A4B1
0x18000a486  mov     rcx, [rsi+0D8h]
0x18000a48d  test    rcx, rcx
0x18000a490  jz      short loc_18000A4A7
0x18000a492  mov     rax, [rcx]
0x18000a495  lea     r8, aDiagnosticsSes; "Diagnostics session was aborted. The li"...
0x18000a49c  xor     edx, edx
0x18000a49e  mov     rax, [rax+60h]
0x18000a4a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4a7  mov     eax, 80004005h
0x18000a4ac  jmp     loc_18000AC14
0x18000a4b1  lea     rbx, [rsi+138h]
0x18000a4b8  mov     rcx, rbx; lpCriticalSection
0x18000a4bb  call    cs:__imp_EnterCriticalSection
0x18000a4c1  lea     rdx, [rsi+0F0h]
0x18000a4c8  mov     r8, rdx
0x18000a4cb  mov     rdx, [rdx+18h]
0x18000a4cf  lea     rcx, [rsp+128h+var_78]
0x18000a4d7  call    ??0?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@PEAVProblemNode@@@std@@@std@@@std@@QEAA@_KPEBU_Container_base12@1@@Z; std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>(unsigned __int64,std::_Container_base12 const *)
0x18000a4dc  nop
0x18000a4dd  mov     rcx, [rsp+128h+var_78]
0x18000a4e5  test    rcx, rcx
0x18000a4e8  jnz     short loc_18000A4EF
0x18000a4ea  mov     rcx, rdi
0x18000a4ed  jmp     short loc_18000A4F2
0x18000a4ef  mov     rcx, [rcx]
0x18000a4f2  mov     r8, [rsp+128h+var_68]
0x18000a4fa  lea     r13, [rsi+10h]
0x18000a4fe  mov     [rsp+128h+var_88], r13
0x18000a506  mov     rdx, [rcx+10h]
0x18000a50a  sub     rdx, r12
0x18000a50d  mov     rax, r8
0x18000a510  shr     rax, 1
0x18000a513  and     rdx, rax
0x18000a516  mov     rax, [rcx+8]
0x18000a51a  and     r8, r12
0x18000a51d  mov     rax, [rax+rdx*8]
0x18000a521  mov     rdx, [rax+r8*8]
0x18000a525  mov     [r13+0], rdx
0x18000a529  mov     rcx, rbx; lpCriticalSection
0x18000a52c  call    cs:__imp_LeaveCriticalSection
0x18000a532  mov     rcx, [rsp+128h+var_A0]
0x18000a53a  mov     rax, [rcx]
0x18000a53d  test    rax, rax
0x18000a540  jz      short loc_18000A55B
0x18000a542  sub     rax, 1
0x18000a546  mov     [rcx], rax
0x18000a549  jnz     short loc_18000A554
0x18000a54b  mov     [r15+108h], rdi
0x18000a552  jmp     short loc_18000A55B
0x18000a554  add     [r15+108h], r12
0x18000a55b  mov     rax, [r13+0]
0x18000a55f  mov     r15, [rax]
0x18000a562  mov     [rsp+128h+var_D0], r15
0x18000a567  mov     [rsp+128h+var_80], r15
0x18000a56f  cmp     [rax+20h], edi
0x18000a572  jz      short loc_18000A57E
0x18000a574  cmp     dword ptr [rax+20h], 7
0x18000a578  jnz     loc_18000A654
0x18000a57e  mov     rcx, [r15+48h]
0x18000a582  mov     rax, [rcx]
0x18000a585  mov     rax, [rax+90h]
0x18000a58c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a591  test    eax, eax
0x18000a593  jz      loc_18000A654
0x18000a599  mov     [rsp+128h+pv], rdi
0x18000a59e  lea     rcx, [rsp+128h+pv]
0x18000a5a3  call    ?CreateInstance@?$CComObject@VCNetDiagHelperUtilFactory@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CNetDiagHelperUtilFactory>::CreateInstance(ATL::CComObject<CNetDiagHelperUtilFactory> * *)
0x18000a5a8  test    eax, eax
0x18000a5aa  js      loc_18000A654
0x18000a5b0  mov     rbx, [rsp+128h+pv]
0x18000a5b5  mov     rax, [rbx]
0x18000a5b8  mov     rcx, rbx
0x18000a5bb  mov     rax, [rax+8]
0x18000a5bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5c4  mov     rdx, [rsi+0D8h]
0x18000a5cb  mov     rcx, [r13+0]
0x18000a5cf  mov     rax, [rsi+50h]
0x18000a5d3  mov     [rbx+40h], rax
0x18000a5d7  mov     [rbx+48h], rcx
0x18000a5db  mov     [rbx+50h], rdx
0x18000a5df  mov     [rsp+128h+var_C8], rdi
0x18000a5e4  mov     rax, [rbx]
0x18000a5e7  lea     r8, [rsp+128h+var_C8]
0x18000a5ec  lea     rdx, _GUID_104613fb_bc57_4178_95ba_88809698354a
0x18000a5f3  mov     rcx, rbx
0x18000a5f6  mov     rax, [rax]
0x18000a5f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5fe  test    eax, eax
0x18000a600  js      short loc_18000A645
0x18000a602  mov     r14, [rsp+128h+var_C8]
0x18000a607  mov     rcx, [r15+48h]
0x18000a60b  mov     rax, [rcx]
0x18000a60e  mov     rax, [rax+90h]
0x18000a615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a61a  test    eax, eax
0x18000a61c  jz      short loc_18000A634
0x18000a61e  mov     rcx, [r15+48h]
0x18000a622  mov     rax, [rcx]
0x18000a625  mov     rdx, r14
0x18000a628  mov     rax, [rax+0A0h]
0x18000a62f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a634  mov     rcx, [rsp+128h+var_C8]
0x18000a639  mov     rax, [rcx]
0x18000a63c  mov     rax, [rax+10h]
0x18000a640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a645  mov     rax, [rbx]
0x18000a648  mov     rcx, rbx
0x18000a64b  mov     rax, [rax+10h]
0x18000a64f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a654  lea     r14, [rsi+0E8h]
0x18000a65b  mov     [rsp+128h+pv], r14
0x18000a660  cmp     [r14], edi
0x18000a663  jnz     loc_18000A76A
0x18000a669  test    cs:byte_180041BC1, 4
0x18000a670  jz      short loc_18000A68E
0x18000a672  lea     rax, [rsp+128h+var_60]
0x18000a67a  mov     [rsp+128h+var_108], rax
0x18000a67f  mov     r9d, r12d
0x18000a682  lea     rdx, StartNDFReproFailure
0x18000a689  call    McGenEventWrite_EventWriteTransfer
0x18000a68e  mov     rdx, [r13+0]; struct ProblemNode *
0x18000a692  mov     rcx, rsi; this
0x18000a695  call    ?ReproduceFailure@NetworkIncident@@QEAAJPEAVProblemNode@@@Z; NetworkIncident::ReproduceFailure(ProblemNode *)
0x18000a69a  mov     ebx, eax
0x18000a69c  test    cs:byte_180041BC1, 4
0x18000a6a3  jz      short loc_18000A6C1
0x18000a6a5  lea     rax, [rsp+128h+var_50]
0x18000a6ad  mov     [rsp+128h+var_108], rax
0x18000a6b2  mov     r9d, r12d
0x18000a6b5  lea     rdx, StopNDFReproFailure
0x18000a6bc  call    McGenEventWrite_EventWriteTransfer
0x18000a6c1  test    ebx, ebx
0x18000a6c3  jns     loc_18000A767
0x18000a6c9  cmp     [rsi+0D8h], rdi
0x18000a6d0  jz      loc_18000A767
0x18000a6d6  lea     rcx, [rsp+128h+var_C0]
0x18000a6db  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000a6e0  nop
0x18000a6e1  lea     rcx, [rsp+128h+var_C0]
0x18000a6e6  cmp     ebx, 80004001h
0x18000a6ec  jz      short loc_18000A6FF
0x18000a6ee  mov     r8d, ebx
0x18000a6f1  lea     rdx, aReproducefailu_0; "ReproduceFailure() failed with hr=0x%08"...
0x18000a6f8  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000a6fd  jmp     short loc_18000A70B
0x18000a6ff  lea     rdx, aReproducefailu_2; "ReproduceFailure not implemented by the"...
0x18000a706  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x18000a70b  mov     rcx, [rsi+0D8h]
0x18000a712  mov     rax, [rcx]
0x18000a715  mov     rbx, [rsp+128h+var_C0]
0x18000a71a  mov     r8, rbx
0x18000a71d  xor     edx, edx
0x18000a71f  mov     rax, [rax+60h]
0x18000a723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a728  nop
0x18000a729  lea     rcx, [rbx-18h]; this
0x18000a72d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000a732  nop
0x18000a733  jmp     short loc_18000A767
0x18000a735  xor     edi, edi
0x18000a737  lea     r12d, [rdi+1]
0x18000a73b  mov     rax, [rsp+128h+var_90]
0x18000a743  mov     [rsp+128h+var_F0], rax
0x18000a748  mov     rsi, [rsp+128h+var_B0]
0x18000a74d  mov     r13, [rsp+128h+var_88]
0x18000a755  mov     r14, [rsp+128h+pv]
0x18000a75a  mov     r15, [rsp+128h+var_80]
0x18000a762  mov     [rsp+128h+var_D0], r15
0x18000a767  mov     [r14], r12d
0x18000a76a  cmp     [rsi+50h], rdi
0x18000a76e  jz      loc_18000A8A2
0x18000a774  mov     rax, [rsp+128h+var_98]
0x18000a77c  test    rax, rax
0x18000a77f  jz      loc_18000A8A2
0x18000a785  mov     rcx, [rax+18h]
0x18000a789  test    rcx, rcx
0x18000a78c  jz      loc_18000A8A2
0x18000a792  mov     rax, [r13+0]
0x18000a796  mov     rdx, [rax]
0x18000a799  mov     rbx, [rdx+10h]
0x18000a79d  cmp     [rbx-10h], edi
0x18000a7a0  jnz     short loc_18000A7A5
0x18000a7a2  mov     rbx, [rdx]
0x18000a7a5  mov     [rsp+128h+var_B8], rdi
0x18000a7aa  mov     rax, [rcx]
0x18000a7ad  lea     r8, [rsp+128h+var_B8]
0x18000a7b2  mov     rdx, rbx
0x18000a7b5  mov     rax, [rax+18h]
0x18000a7b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7be  mov     edx, eax
0x18000a7c0  test    eax, eax
0x18000a7c2  js      loc_18000A85F
0x18000a7c8  mov     [rsp+128h+pv], rdi
0x18000a7cd  mov     rcx, [rsp+128h+var_B8]
0x18000a7d2  mov     rax, [rcx]
0x18000a7d5  lea     rdx, [rsp+128h+pv]
0x18000a7da  mov     rax, [rax+40h]
0x18000a7de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7e3  mov     ebx, eax
0x18000a7e5  test    eax, eax
0x18000a7e7  js      short loc_18000A835
0x18000a7e9  mov     r8, [rsp+128h+pv]
0x18000a7ee  mov     edx, 0C8h; unsigned __int16 *
0x18000a7f3  mov     rcx, [rsi+50h]; this
0x18000a7f7  call    ?SetProgress@DiagnosticsClient@@QEAAJPEBGZZ; DiagnosticsClient::SetProgress(ushort const *,...)
0x18000a7fc  mov     ebx, eax
0x18000a7fe  test    eax, eax
0x18000a800  jns     short loc_18000A828
0x18000a802  mov     rcx, [rsi+0D8h]
0x18000a809  test    rcx, rcx
0x18000a80c  jz      short loc_18000A826
0x18000a80e  mov     rax, [rcx]
0x18000a811  mov     r9d, ebx
0x18000a814  lea     r8, aCouldNotUpdate; "Could not update the progress string. H"...
0x18000a81b  xor     edx, edx
0x18000a81d  mov     rax, [rax+68h]
0x18000a821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a826  mov     ebx, edi
0x18000a828  mov     rcx, [rsp+128h+pv]; pv
0x18000a82d  call    cs:__imp_CoTaskMemFree
0x18000a833  jmp     short loc_18000A859
0x18000a835  mov     rcx, [rsi+0D8h]
0x18000a83c  test    rcx, rcx
0x18000a83f  jz      short loc_18000A859
0x18000a841  mov     rax, [rcx]
0x18000a844  mov     r9d, ebx
0x18000a847  lea     r8, aCouldNotRetrie; "Could not retrieve the current HC's pro"...
0x18000a84e  xor     edx, edx
0x18000a850  mov     rax, [rax+68h]
0x18000a854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a859  test    ebx, ebx
0x18000a85b  jns     short loc_18000A898
0x18000a85d  jmp     short loc_18000A887
0x18000a85f  mov     rcx, [rsi+0D8h]
0x18000a866  test    rcx, rcx
0x18000a869  jz      short loc_18000A887
0x18000a86b  mov     rax, [rcx]
0x18000a86e  mov     dword ptr [rsp+128h+var_108], edx
0x18000a872  mov     r9, rbx
0x18000a875  lea     r8, aWarningHelperc; "Warning: HelperClass '%s' not found in "...
0x18000a87c  xor     edx, edx
0x18000a87e  mov     rax, [rax+68h]
0x18000a882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a887  lea     rdx, dword_180033E1C; unsigned __int16 *
0x18000a88e  mov     rcx, [rsi+50h]; this
0x18000a892  call    ?SetProgress@DiagnosticsClient@@QEAAJPEBGZZ; DiagnosticsClient::SetProgress(ushort const *,...)
0x18000a897  nop
0x18000a898  lea     rcx, [rsp+128h+var_B8]
0x18000a89d  call    ??1?$CComPtrBase@UINDFHelperClass@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(void)
0x18000a8a2  mov     [rsp+128h+var_F8], dil
0x18000a8a7  mov     rax, [r13+0]
0x18000a8ab  mov     ecx, [rax+18h]
0x18000a8ae  sub     ecx, 2
0x18000a8b1  lea     rbx, [rsi+18h]
0x18000a8b5  mov     rax, rbx
0x18000a8b8  test    ecx, 0FFFFFFFDh
0x18000a8be  jz      short loc_18000A916
0x18000a8c0  cmp     dword ptr [rbx], 0Dh
0x18000a8c3  jz      loc_18000AB18
0x18000a8c9  mov     [rsp+128h+var_E8], 8
0x18000a8d1  lea     r14, [r15+0E4h]
0x18000a8d8  cmp     [r14], edi
0x18000a8db  jge     short loc_18000A8F6
0x18000a8dd  mov     rcx, [rsi+50h]
0x18000a8e1  mov     rax, [rcx]
0x18000a8e4  mov     rax, [rax+38h]
  ... truncated ...
```
