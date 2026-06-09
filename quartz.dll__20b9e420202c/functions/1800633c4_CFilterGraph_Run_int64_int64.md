# CFilterGraph::Run(__int64,__int64)

- ea: `0x1800633c4`
- end: `0x180063989`
- name: `?Run@CFilterGraph@@QEAAJ_J0@Z`
- size: `1477`
- prototype: `__int64 __fastcall(CFilterGraph *__hidden this, __int64, __int64)`
- caller_count: `3`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x180063990`
- `0x18007050c`
- `0x180070c30`

## callees

- `0x180001038`
- `0x180004530`
- `0x1800197c0`
- `0x18001d3b0`
- `0x18001fbcc`
- `0x1800240d0`
- `0x18002e8f4`
- `0x18002fce8`
- `0x1800301c8`
- `0x1800388a0`
- `0x180039250`
- `0x1800633c4`
- `0x1800647a0`
- `0x180064fd0`
- `0x180065048`
- `0x180069e64`
- `0x180070b88`
- `0x180141ca4`
- `0x18015e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x180063570`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x18006358d`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x1800635b5`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x180063570`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x18006358d`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x1800635b5`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180063546`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180063546`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180063514`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180063514`
- `KERNEL32!GetCurrentThread` at `0x1800637bf`
- `KERNEL32!GetCurrentThread` at `0x1800637bf`
- `KERNEL32!GetThreadPriority` at `0x1800637d1`
- `KERNEL32!GetThreadPriority` at `0x1800637d1`
- `KERNEL32!SetThreadPriority` at `0x1800637e8`
- `KERNEL32!SetThreadPriority` at `0x180063878`
- `KERNEL32!SetThreadPriority` at `0x1800637e8`
- `KERNEL32!SetThreadPriority` at `0x180063878`

## pseudocode

```c
__int64 __fastcall CFilterGraph::Run(CFilterGraph *this, __int64 a2, __int16 *a3)
{
  __int16 *v3; // r15
  char v6; // r13
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // ecx
  __int16 *v10; // rdi
  __int64 v11; // rcx
  unsigned int v12; // esi
  wchar_t *v13; // rax
  __int64 v14; // r9
  const wchar_t *v15; // r8
  wchar_t *v16; // rax
  bool v17; // di
  unsigned int v18; // edi
  int v19; // eax
  int v20; // ecx
  __int64 v21; // rcx
  struct IEnumFilters *v22; // rax
  __int64 v23; // rax
  __int64 v24; // rcx
  struct IEnumFilters *v25; // rax
  CFGControl *v26; // rcx
  __int64 v27; // rdx
  CDistributorManager *v28; // rcx
  HANDLE CurrentThread; // r15
  int ThreadPriority; // r12d
  CBaseList *v31; // rcx
  __int64 v32; // rsi
  struct IUnknown *v33; // r14
  struct IBaseFilter *v34; // rdi
  __int64 v35; // rdx
  int v36; // eax
  int v37; // edx
  int v38; // r8d
  int v39; // r9d
  __int64 v40; // rcx
  unsigned int v42; // [rsp+30h] [rbp-D0h] BYREF
  struct IEnumFilters *v43; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v44; // [rsp+40h] [rbp-C0h] BYREF
  __int16 *v45; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v46[16]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Str[128]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v48; // [rsp+160h] [rbp+60h]
  _BYTE v49[112]; // [rsp+170h] [rbp+70h] BYREF
  __int16 v50; // [rsp+1E0h] [rbp+E0h] BYREF
  char v51[3102]; // [rsp+1E2h] [rbp+E2h] BYREF

  v45 = a3;
  v3 = a3;
  v42 = 0;
  v50 = 0;
  v6 = 0;
  memset_0(v51, 0, 0xC18u);
  if ( (Microsoft_Windows_DirectShow_CoreEnableBits & 0x10) != 0 )
    McTemplateU0pi_EventWriteTransfer(v8, v7, this, a2);
  CAutoMsgMutex::CAutoMsgMutex((CAutoMsgMutex *)v46, (CFilterGraph *)((char *)this + 256), 0xFFFFFFFF);
  if ( *((_BYTE *)this + 776) )
  {
    v10 = &v50;
    v11 = 1549;
    v43 = 0;
    while ( v11 )
    {
      *v10++ = 0;
      --v11;
    }
    v44 = 0;
    v42 = 0;
    if ( (int)CFilterGraph::EnumFilters(this, &v43) >= 0 )
    {
      v12 = 0;
      while ( 1 )
      {
        if ( ((unsigned int (__fastcall *)(struct IEnumFilters *, __int64, __int64 *, unsigned int *))v43->lpVtbl->Next)(
               v43,
               1,
               &v44,
               &v42) )
        {
LABEL_25:
          ((void (__fastcall *)(struct IEnumFilters *))v43->lpVtbl->Release)(v43);
          v3 = v45;
          break;
        }
        memset_0(Str, 0, 0x108u);
        if ( (*(int (__fastcall **)(__int64, wchar_t *))(*(_QWORD *)v44 + 96LL))(v44, Str) < 0 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
          goto LABEL_24;
        }
        v13 = wcsrchr(Str, 0x2Eu);
        if ( v13 )
        {
          v14 = 6;
          v15 = v13;
        }
        else
        {
          v16 = wcschr(Str, 0x5Cu);
          v14 = 128;
          if ( !v16 )
          {
            v17 = (unsigned int)_o_wcsncat_s(&v50, 1549, Str, 128) != 0;
            goto LABEL_18;
          }
          v15 = L"FileSource";
        }
        v17 = (unsigned int)_o_wcsncat_s(&v50, 1549, v15, v14) != 0;
LABEL_18:
        if ( (unsigned int)_o_wcsncat_s(&v50, 1549, L"|", 1) )
          v17 = 1;
        if ( v48 )
          (*(void (**)(void))(*(_QWORD *)v48 + 16LL))();
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
        if ( v17 )
          goto LABEL_25;
        ++v12;
LABEL_24:
        if ( v12 >= 0xC )
          goto LABEL_25;
      }
    }
  }
  if ( *((_DWORD *)this + 42) == 2 )
  {
    if ( (Microsoft_Windows_DirectShow_CoreEnableBits & 0x10) != 0 )
      McTemplateU0ppzd_EventWriteTransfer(v9, (unsigned int)RunStopEvent, (_DWORD)this, 0, 0, 0);
    v18 = 0;
    goto LABEL_70;
  }
  v19 = CFilterGraph::UpstreamOrder(this);
  v18 = v19;
  if ( v19 >= 0 )
  {
    if ( *((_QWORD *)this + 22)
      || *((_DWORD *)this + 72)
      || (v19 = CFilterGraph::SetDefaultSyncSource(this), v18 = v19, v19 >= 0) )
    {
      if ( !a2 )
      {
        v21 = *((_QWORD *)this + 22);
        v22 = 0;
        v43 = 0;
        if ( v21 )
        {
          (*(void (__fastcall **)(__int64, struct IEnumFilters **))(*(_QWORD *)v21 + 24LL))(v21, &v43);
          v22 = v43;
        }
        *((_QWORD *)this + 52) += (char *)v22 - *((_QWORD *)this + 53);
        v23 = *((_QWORD *)this + 52);
        if ( !*((_DWORD *)this + 42) )
        {
          v23 += 1000000;
          *((_QWORD *)this + 52) = v23;
          v3 += 500000;
        }
        v3 += 500000;
        a2 = v23 + 1000000;
      }
      *((_QWORD *)this + 52) = a2;
      *((_QWORD *)this + 53) = 0;
      v24 = *((_QWORD *)this + 95);
      if ( !v24 )
        goto LABEL_48;
      v43 = 0;
      v19 = (*(__int64 (__fastcall **)(__int64, struct IEnumFilters **))(*(_QWORD *)v24 + 24LL))(v24, &v43);
      v18 = v19;
      if ( v19 >= 0 )
      {
        if ( *((_BYTE *)this + 738) )
          v25 = (struct IEnumFilters *)((char *)v43 + *((_QWORD *)this + 93) - *((_QWORD *)this + 94));
        else
          v25 = v43;
        *((_BYTE *)this + 737) = 1;
        *((_QWORD *)this + 93) = (char *)v25 + (_QWORD)v3;
LABEL_48:
        v26 = (CFGControl *)*((_QWORD *)this + 31);
        *((_QWORD *)this + 94) = 0;
        v27 = *((_QWORD *)this + 52);
        *((_QWORD *)this + 23) = v27;
        *((_BYTE *)this + 738) = 0;
        CFGControl::Run(v26, v27);
        v28 = (CDistributorManager *)*((_QWORD *)this + 68);
        if ( v28 )
          CDistributorManager::Run(v28, *((_QWORD *)this + 52));
        CurrentThread = GetCurrentThread();
        ThreadPriority = GetThreadPriority(CurrentThread);
        SetThreadPriority(CurrentThread, 15);
        v32 = *((_QWORD *)this + 37);
        v18 = 0;
        v33 = 0;
        v42 = 0;
        if ( v32 )
        {
          do
          {
            v34 = *(struct IBaseFilter **)CBaseList::GetI(v31, (struct __POSITION *)v32);
            if ( CFilterGraph::DoesFilterUseNormalClock(this, v34) )
              v35 = *((_QWORD *)this + 52);
            else
              v35 = *((_QWORD *)this + 93);
            v36 = ((__int64 (__fastcall *)(struct IBaseFilter *, __int64))v34->lpVtbl->Run)(v34, v35);
            CumulativeHRESULT::Accumulate((CumulativeHRESULT *)&v42, v36);
            if ( v37 < 0 )
              v33 = (struct IUnknown *)v34;
            v32 = *(_QWORD *)(v32 + 8);
          }
          while ( v32 );
          v18 = v42;
        }
        SetThreadPriority(CurrentThread, ThreadPriority);
        *((_DWORD *)this + 42) = 2;
        if ( (Microsoft_Windows_DirectShow_CoreEnableBits & 0x10) != 0 )
        {
          if ( v33 )
          {
            v6 = 1;
            v40 = *(_QWORD *)CDisp::CDisp((CDisp *)v49, v33);
          }
          else
          {
            v40 = 0;
          }
          McTemplateU0ppzd_EventWriteTransfer(v40, (unsigned int)RunStopEvent, (_DWORD)this, (_DWORD)v33, v40, v18);
        }
        if ( (v6 & 1) != 0 )
          CDispBasic::~CDispBasic((CDispBasic *)v49);
        if ( *((_BYTE *)this + 776) )
        {
          *((_BYTE *)this + 776) = 0;
          if ( (unsigned int)dword_18019A8F8 > 4
            && (qword_18019A908 & 0x400000000000LL) != 0
            && (qword_18019A910 & 0x400000000000LL) == qword_18019A910 )
          {
            v42 = v18;
            v45 = &v50;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              qword_18019A910,
              (unsigned int)byte_18018B989,
              v38,
              v39,
              (__int64)&v45,
              (__int64)&v42);
          }
        }
        goto LABEL_70;
      }
    }
  }
  if ( (Microsoft_Windows_DirectShow_CoreEnableBits & 0x10) != 0 )
    McTemplateU0ppzd_EventWriteTransfer(v20, (unsigned int)RunStopEvent, (_DWORD)this, 0, 0, v19);
LABEL_70:
  CAutoMsgMutex::~CAutoMsgMutex((CAutoMsgMutex *)v46);
  return v18;
}

```

## disassembly

```asm
0x1800633c4  mov     [rsp-8+arg_10], rbx
0x1800633c9  push    rbp
0x1800633ca  push    rsi
0x1800633cb  push    rdi
0x1800633cc  push    r12
0x1800633ce  push    r13
0x1800633d0  push    r14
0x1800633d2  push    r15
0x1800633d4  lea     rbp, [rsp-0D10h]
0x1800633dc  sub     rsp, 0E10h
0x1800633e3  mov     rax, cs:__security_cookie
0x1800633ea  xor     rax, rsp
0x1800633ed  mov     [rbp+0D40h+var_40], rax
0x1800633f4  xor     r12d, r12d
0x1800633f7  mov     [rsp+0E40h+var_DF8], r8
0x1800633fc  mov     r15, r8
0x1800633ff  mov     [rsp+0E40h+var_E10], r12d
0x180063404  mov     r14, rdx
0x180063407  mov     [rbp+0D40h+var_C60], r12w
0x18006340f  mov     rbx, rcx
0x180063412  xor     edx, edx; Val
0x180063414  mov     r8d, 0C18h; Size
0x18006341a  lea     rcx, [rbp+0D40h+var_C5E]; void *
0x180063421  mov     r13d, r12d
0x180063424  call    memset_0
0x180063429  mov     sil, 10h
0x18006342c  test    cs:Microsoft_Windows_DirectShow_CoreEnableBits, sil
0x180063433  jz      short loc_180063440
0x180063435  mov     r9, r14
0x180063438  mov     r8, rbx
0x18006343b  call    McTemplateU0pi_EventWriteTransfer
0x180063440  lea     rdx, [rbx+100h]; struct CMsgMutex *
0x180063447  or      r8d, 0FFFFFFFFh; unsigned int
0x18006344b  lea     rcx, [rsp+0E40h+var_DF0]; this
0x180063450  call    ??0CAutoMsgMutex@@QEAA@PEAVCMsgMutex@@K@Z; CAutoMsgMutex::CAutoMsgMutex(CMsgMutex *,ulong)
0x180063455  cmp     [rbx+308h], r12b
0x18006345c  jz      loc_180063617
0x180063462  movzx   eax, r12w
0x180063466  lea     rdi, [rbp+0D40h+var_C60]
0x18006346d  mov     ecx, 60Dh
0x180063472  mov     [rsp+0E40h+var_E08], r12
0x180063477  rep stosw
0x18006347a  mov     rcx, rbx; this
0x18006347d  mov     [rsp+0E40h+var_E00], r12
0x180063482  lea     rdx, [rsp+0E40h+var_E08]; struct IEnumFilters **
0x180063487  mov     [rsp+0E40h+var_E10], r12d
0x18006348c  call    ?EnumFilters@CFilterGraph@@UEAAJPEAPEAUIEnumFilters@@@Z; CFilterGraph::EnumFilters(IEnumFilters * *)
0x180063491  test    eax, eax
0x180063493  js      loc_180063617
0x180063499  mov     esi, r12d
0x18006349c  mov     r15d, 1
0x1800634a2  mov     rcx, [rsp+0E40h+var_E08]
0x1800634a7  lea     r9, [rsp+0E40h+var_E10]
0x1800634ac  lea     r8, [rsp+0E40h+var_E00]
0x1800634b1  mov     edx, r15d
0x1800634b4  mov     rax, [rcx]
0x1800634b7  mov     rax, [rax+18h]
0x1800634bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800634c0  test    eax, eax
0x1800634c2  jnz     loc_1800635FE
0x1800634c8  xor     edx, edx; Val
0x1800634ca  lea     rcx, [rsp+0E40h+Str]; void *
0x1800634cf  mov     r8d, 108h; Size
0x1800634d5  call    memset_0
0x1800634da  mov     rcx, [rsp+0E40h+var_E00]
0x1800634df  lea     rdx, [rsp+0E40h+Str]
0x1800634e4  mov     rax, [rcx]
0x1800634e7  mov     rax, [rax+60h]
0x1800634eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800634f0  test    eax, eax
0x1800634f2  jns     short loc_18006350A
0x1800634f4  mov     rcx, [rsp+0E40h+var_E00]
0x1800634f9  mov     rax, [rcx]
0x1800634fc  mov     rax, [rax+10h]
0x180063500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063505  jmp     loc_1800635F5
0x18006350a  mov     edx, 2Eh ; '.'; Ch
0x18006350f  lea     rcx, [rsp+0E40h+Str]; Str
0x180063514  call    cs:__imp_wcsrchr
0x18006351b  nop     dword ptr [rax+rax+00h]
0x180063520  test    rax, rax
0x180063523  jz      short loc_18006353C
0x180063525  mov     r9d, 6
0x18006352b  lea     rcx, [rbp+0D40h+var_C60]
0x180063532  mov     r8, rax
0x180063535  mov     edx, 60Dh
0x18006353a  jmp     short loc_180063570
0x18006353c  mov     edx, 5Ch ; '\'; Ch
0x180063541  lea     rcx, [rsp+0E40h+Str]; Str
0x180063546  call    cs:__imp_wcschr
0x18006354d  nop     dword ptr [rax+rax+00h]
0x180063552  mov     r9d, 80h
0x180063558  lea     rcx, [rbp+0D40h+var_C60]
0x18006355f  mov     edx, 60Dh
0x180063564  test    rax, rax
0x180063567  jz      short loc_180063584
0x180063569  lea     r8, aFilesource; "FileSource"
0x180063570  call    cs:__imp__o_wcsncat_s
0x180063577  nop     dword ptr [rax+rax+00h]
0x18006357c  test    eax, eax
0x18006357e  setnz   dil
0x180063582  jmp     short loc_18006359F
0x180063584  lea     r8, [rsp+0E40h+Str]
0x180063589  movzx   edi, r12b
0x18006358d  call    cs:__imp__o_wcsncat_s
0x180063594  nop     dword ptr [rax+rax+00h]
0x180063599  test    eax, eax
0x18006359b  cmovnz  edi, r15d
0x18006359f  mov     r9, r15
0x1800635a2  lea     r8, asc_1801765E8; "|"
0x1800635a9  mov     edx, 60Dh
0x1800635ae  lea     rcx, [rbp+0D40h+var_C60]
0x1800635b5  call    cs:__imp__o_wcsncat_s
0x1800635bc  nop     dword ptr [rax+rax+00h]
0x1800635c1  mov     rcx, [rbp+0D40h+var_CE0]
0x1800635c5  test    eax, eax
0x1800635c7  cmovnz  edi, r15d
0x1800635cb  test    rcx, rcx
0x1800635ce  jz      short loc_1800635DC
0x1800635d0  mov     rax, [rcx]
0x1800635d3  mov     rax, [rax+10h]
0x1800635d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800635dc  mov     rcx, [rsp+0E40h+var_E00]
0x1800635e1  mov     rax, [rcx]
0x1800635e4  mov     rax, [rax+10h]
0x1800635e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800635ed  test    dil, dil
0x1800635f0  jnz     short loc_1800635FE
0x1800635f2  add     esi, r15d
0x1800635f5  cmp     esi, 0Ch
0x1800635f8  jb      loc_1800634A2
0x1800635fe  mov     rcx, [rsp+0E40h+var_E08]
0x180063603  mov     rax, [rcx]
0x180063606  mov     rax, [rax+10h]
0x18006360a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006360f  mov     r15, [rsp+0E40h+var_DF8]
0x180063614  mov     sil, 10h
0x180063617  cmp     dword ptr [rbx+0A8h], 2
0x18006361e  jnz     short loc_18006364D
0x180063620  test    cs:Microsoft_Windows_DirectShow_CoreEnableBits, sil
0x180063627  jz      short loc_180063645
0x180063629  mov     dword ptr [rsp+0E40h+var_E18], r12d
0x18006362e  lea     rdx, RunStopEvent
0x180063635  xor     r9d, r9d
0x180063638  mov     [rsp+0E40h+var_E20], r12
0x18006363d  mov     r8, rbx
0x180063640  call    McTemplateU0ppzd_EventWriteTransfer
0x180063645  mov     edi, r12d
0x180063648  jmp     loc_180063952
0x18006364d  mov     rcx, rbx; this
0x180063650  call    ?UpstreamOrder@CFilterGraph@@AEAAJXZ; CFilterGraph::UpstreamOrder(void)
0x180063655  mov     edi, eax
0x180063657  test    eax, eax
0x180063659  jns     short loc_180063688
0x18006365b  test    cs:Microsoft_Windows_DirectShow_CoreEnableBits, sil
0x180063662  jz      loc_180063952
0x180063668  mov     dword ptr [rsp+0E40h+var_E18], eax
0x18006366c  lea     rdx, RunStopEvent
0x180063673  xor     r9d, r9d
0x180063676  mov     [rsp+0E40h+var_E20], r12
0x18006367b  mov     r8, rbx
0x18006367e  call    McTemplateU0ppzd_EventWriteTransfer
0x180063683  jmp     loc_180063952
0x180063688  cmp     [rbx+0B0h], r12
0x18006368f  jnz     short loc_1800636A8
0x180063691  cmp     [rbx+120h], r12d
0x180063698  jnz     short loc_1800636A8
0x18006369a  mov     rcx, rbx; this
0x18006369d  call    ?SetDefaultSyncSource@CFilterGraph@@UEAAJXZ; CFilterGraph::SetDefaultSyncSource(void)
0x1800636a2  mov     edi, eax
0x1800636a4  test    eax, eax
0x1800636a6  js      short loc_18006365B
0x1800636a8  test    r14, r14
0x1800636ab  jnz     short loc_180063711
0x1800636ad  mov     rcx, [rbx+0B0h]
0x1800636b4  mov     rax, r12
0x1800636b7  mov     [rsp+0E40h+var_E08], rax
0x1800636bc  test    rcx, rcx
0x1800636bf  jz      short loc_1800636D7
0x1800636c1  mov     rax, [rcx]
0x1800636c4  lea     rdx, [rsp+0E40h+var_E08]
0x1800636c9  mov     rax, [rax+18h]
0x1800636cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800636d2  mov     rax, [rsp+0E40h+var_E08]
0x1800636d7  sub     rax, [rbx+1A8h]
0x1800636de  mov     ecx, 0F4240h
0x1800636e3  add     [rbx+1A0h], rax
0x1800636ea  mov     rax, [rbx+1A0h]
0x1800636f1  cmp     [rbx+0A8h], r12d
0x1800636f8  jnz     short loc_180063707
0x1800636fa  add     rax, rcx
0x1800636fd  mov     [rbx+1A0h], rax
0x180063704  add     r15, rcx
0x180063707  add     r15, rcx
0x18006370a  lea     r14, [rax+0F4240h]
0x180063711  mov     [rbx+1A0h], r14
0x180063718  mov     [rbx+1A8h], r12
0x18006371f  mov     rcx, [rbx+2F8h]
0x180063726  test    rcx, rcx
0x180063729  jz      short loc_18006377F
0x18006372b  mov     [rsp+0E40h+var_E08], r12
0x180063730  lea     rdx, [rsp+0E40h+var_E08]
0x180063735  mov     rax, [rcx]
0x180063738  mov     rax, [rax+18h]
0x18006373c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063741  mov     edi, eax
0x180063743  test    eax, eax
0x180063745  js      loc_18006365B
0x18006374b  cmp     [rbx+2E2h], r12b
0x180063752  jnz     short loc_18006375B
0x180063754  mov     rax, [rsp+0E40h+var_E08]
0x180063759  jmp     short loc_18006376E
0x18006375b  mov     rax, [rbx+2E8h]
0x180063762  sub     rax, [rbx+2F0h]
0x180063769  add     rax, [rsp+0E40h+var_E08]
0x18006376e  add     rax, r15
0x180063771  mov     byte ptr [rbx+2E1h], 1
0x180063778  mov     [rbx+2E8h], rax
0x18006377f  mov     rcx, [rbx+0F8h]; this
0x180063786  mov     [rbx+2F0h], r12
0x18006378d  mov     rdx, [rbx+1A0h]; __int64
0x180063794  mov     [rbx+0B8h], rdx
0x18006379b  mov     [rbx+2E2h], r12b
0x1800637a2  call    ?Run@CFGControl@@QEAAJ_J@Z; CFGControl::Run(__int64)
0x1800637a7  mov     rcx, [rbx+220h]; this
0x1800637ae  test    rcx, rcx
0x1800637b1  jz      short loc_1800637BF
0x1800637b3  mov     rdx, [rbx+1A0h]; __int64
0x1800637ba  call    ?Run@CDistributorManager@@QEAAJ_J@Z; CDistributorManager::Run(__int64)
0x1800637bf  call    cs:__imp_GetCurrentThread
0x1800637c6  nop     dword ptr [rax+rax+00h]
0x1800637cb  mov     rcx, rax; hThread
0x1800637ce  mov     r15, rax
0x1800637d1  call    cs:__imp_GetThreadPriority
0x1800637d8  nop     dword ptr [rax+rax+00h]
0x1800637dd  mov     edx, 0Fh; nPriority
0x1800637e2  mov     rcx, r15; hThread
0x1800637e5  mov     r12d, eax
0x1800637e8  call    cs:__imp_SetThreadPriority
0x1800637ef  nop     dword ptr [rax+rax+00h]
0x1800637f4  mov     rsi, [rbx+128h]
0x1800637fb  xor     edi, edi
0x1800637fd  xor     r14d, r14d
0x180063800  mov     [rsp+0E40h+var_E10], edi
0x180063804  test    rsi, rsi
0x180063807  jz      short loc_180063872
0x180063809  mov     rdx, rsi; struct __POSITION *
0x18006380c  call    ?GetI@CBaseList@@IEBAPEAXPEAU__POSITION@@@Z; CBaseList::GetI(__POSITION *)
0x180063811  mov     rcx, rbx; this
0x180063814  mov     rdi, [rax]
0x180063817  mov     rdx, rdi; struct IBaseFilter *
0x18006381a  call    ?DoesFilterUseNormalClock@CFilterGraph@@AEAA_NPEAUIBaseFilter@@@Z; CFilterGraph::DoesFilterUseNormalClock(IBaseFilter *)
0x18006381f  mov     rcx, [rdi]
0x180063822  test    al, al
0x180063824  mov     r8, [rcx+30h]
0x180063828  mov     rcx, rdi
0x18006382b  mov     rax, r8
0x18006382e  jz      short loc_180063839
0x180063830  mov     rdx, [rbx+1A0h]
0x180063837  jmp     short loc_180063840
0x180063839  mov     rdx, [rbx+2E8h]
0x180063840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063845  mov     edx, eax; int
0x180063847  lea     rcx, [rsp+0E40h+var_E10]; this
0x18006384c  call    ?Accumulate@CumulativeHRESULT@@QEAAXJ@Z; CumulativeHRESULT::Accumulate(long)
0x180063851  test    edx, edx
0x180063853  cmovs   r14, rdi
0x180063857  test    rsi, rsi
0x18006385a  jnz     short loc_180063865
0x18006385c  mov     rsi, [rbx+128h]
0x180063863  jmp     short loc_180063869
0x180063865  mov     rsi, [rsi+8]
0x180063869  test    rsi, rsi
0x18006386c  jnz     short loc_180063809
0x18006386e  mov     edi, [rsp+0E40h+var_E10]
0x180063872  mov     edx, r12d; nPriority
0x180063875  mov     rcx, r15; hThread
0x180063878  call    cs:__imp_SetThreadPriority
0x18006387f  nop     dword ptr [rax+rax+00h]
0x180063884  mov     dword ptr [rbx+0A8h], 2
0x18006388e  test    cs:Microsoft_Windows_DirectShow_CoreEnableBits, 10h
0x180063895  jz      short loc_1800638D0
0x180063897  test    r14, r14
0x18006389a  jz      short loc_1800638B3
0x18006389c  mov     rdx, r14; struct IUnknown *
0x18006389f  lea     rcx, [rbp+0D40h+var_CD0]; this
0x1800638a3  call    ??0CDisp@@QEAA@PEAUIUnknown@@@Z; CDisp::CDisp(IUnknown *)
0x1800638a8  mov     r13d, 1
0x1800638ae  mov     rcx, [rax]
0x1800638b1  jmp     short loc_1800638B5
0x1800638b3  xor     ecx, ecx
0x1800638b5  mov     dword ptr [rsp+0E40h+var_E18], edi
0x1800638b9  lea     rdx, RunStopEvent
0x1800638c0  mov     r9, r14
0x1800638c3  mov     [rsp+0E40h+var_E20], rcx
0x1800638c8  mov     r8, rbx
0x1800638cb  call    McTemplateU0ppzd_EventWriteTransfer
0x1800638d0  test    r13b, 1
0x1800638d4  jz      short loc_1800638DF
0x1800638d6  lea     rcx, [rbp+0D40h+var_CD0]; this
  ... truncated ...
```
