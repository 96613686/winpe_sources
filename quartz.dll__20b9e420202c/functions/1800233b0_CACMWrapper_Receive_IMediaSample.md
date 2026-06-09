# CACMWrapper::Receive(IMediaSample *)

- ea: `0x1800233b0`
- end: `0x180023884`
- name: `?Receive@CACMWrapper@@UEAAJPEAUIMediaSample@@@Z`
- size: `1236`
- prototype: `__int64 __fastcall(CACMWrapper *__hidden this, struct IMediaSample *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x1800208d8`
- `0x1800233b0`
- `0x18002e458`
- `0x18002e488`
- `0x180120184`
- `0x1801206d0`
- `0x1801207f0`
- `0x18015bb98`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800235d0`
- `KERNEL32!LeaveCriticalSection` at `0x180023864`
- `KERNEL32!LeaveCriticalSection` at `0x1800235d0`
- `KERNEL32!LeaveCriticalSection` at `0x180023864`
- `KERNEL32!EnterCriticalSection` at `0x1800233e7`
- `KERNEL32!EnterCriticalSection` at `0x1800233e7`
- `ole32!CoTaskMemFree` at `0x180023562`
- `ole32!CoTaskMemFree` at `0x1800235b4`
- `ole32!CoTaskMemFree` at `0x1800235f4`
- `ole32!CoTaskMemFree` at `0x180023786`
- `ole32!CoTaskMemFree` at `0x180023562`
- `ole32!CoTaskMemFree` at `0x1800235b4`
- `ole32!CoTaskMemFree` at `0x1800235f4`
- `ole32!CoTaskMemFree` at `0x180023786`
- `ole32!CoTaskMemAlloc` at `0x18002351e`
- `ole32!CoTaskMemAlloc` at `0x180023728`
- `ole32!CoTaskMemAlloc` at `0x18002351e`
- `ole32!CoTaskMemAlloc` at `0x180023728`

## pseudocode

```c
__int64 __fastcall CACMWrapper::Receive(CACMWrapper *this, struct IMediaSample *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  struct IMediaSampleVtbl *lpVtbl; // rax
  size_t v6; // r14
  __int64 v7; // r12
  int v8; // edi
  __int64 v9; // r8
  __int64 v10; // rax
  __int64 v11; // rax
  int v12; // eax
  void *v13; // r12
  int v14; // ecx
  void *v15; // rax
  unsigned int v16; // r13d
  void *v17; // rcx
  void *v19; // rcx
  __int64 v20; // r12
  HRESULT (__stdcall *SetSyncPoint)(IMediaSample *, BOOL); // rdi
  int v22; // eax
  HRESULT (__stdcall *SetDiscontinuity)(IMediaSample *, BOOL); // rdi
  int v24; // eax
  int v25; // eax
  char *v26; // rdx
  void *v27; // rcx
  size_t v28; // r8
  LPVOID v29; // rax
  void *v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rax
  void *Src; // [rsp+40h] [rbp-38h] BYREF
  struct _AMMediaType *pv; // [rsp+48h] [rbp-30h] BYREF
  __int64 v35; // [rsp+50h] [rbp-28h] BYREF
  __int64 v36; // [rsp+58h] [rbp-20h] BYREF
  __int64 v37; // [rsp+60h] [rbp-18h]
  int v38; // [rsp+C0h] [rbp+48h] BYREF
  int v39; // [rsp+C8h] [rbp+50h] BYREF
  struct IMediaSample *v40; // [rsp+D0h] [rbp+58h] BYREF
  __int64 v41; // [rsp+D8h] [rbp+60h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 328);
  v41 = 0;
  v35 = 0;
  v36 = 0;
  v40 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 328));
  lpVtbl = a2->lpVtbl;
  Src = 0;
  v38 = 0;
  pv = 0;
  ((void (__fastcall *)(struct IMediaSample *, struct _AMMediaType **))lpVtbl->GetMediaType)(a2, &pv);
  if ( pv && pv->pbFormat )
  {
    CACMWrapper::StopStreaming(this);
    CMediaType::Set((struct _AMMediaType *)(*((_QWORD *)this + 27) + 104LL), pv);
    DeleteMediaType(pv);
    CACMWrapper::StartStreaming(this);
  }
  v6 = ((int (__fastcall *)(struct IMediaSample *))a2->lpVtbl->GetActualDataLength)(a2);
  if ( !((unsigned int (__fastcall *)(struct IMediaSample *))a2->lpVtbl->IsDiscontinuity)(a2) )
    CACMWrapper::SendExtraStuff(this);
  v7 = *(int *)(*(_QWORD *)(*((_QWORD *)this + 27) + 184LL) + 8LL);
  v8 = ((__int64 (__fastcall *)(struct IMediaSample *, __int64 *, __int64 *))a2->lpVtbl->GetTime)(a2, &v41, &v35);
  if ( v8 >= 0 )
  {
    v11 = v35;
  }
  else
  {
    v9 = *((_QWORD *)this + 34);
    v41 = v9;
    if ( (_DWORD)v7 )
      v10 = (__int64)(10000000 * v6) / v7;
    else
      v10 = 1;
    v11 = v9 + v10;
    v35 = v11;
  }
  *((_QWORD *)this + 34) = v11;
  ((void (__fastcall *)(struct IMediaSample *, void **))a2->lpVtbl->GetPointer)(a2, &Src);
  v12 = *((_DWORD *)this + 78);
  if ( v12 <= 0 )
  {
    if ( v12 < 0 )
    {
      v19 = (void *)*((_QWORD *)this + 38);
      *((_DWORD *)this + 78) = 0;
      CoTaskMemFree(v19);
      *((_QWORD *)this + 38) = 0;
    }
  }
  else
  {
    v13 = (void *)*((_QWORD *)this + 38);
    v14 = v12 + v6;
    if ( v12 + (int)v6 < v12 )
    {
      v17 = (void *)*((_QWORD *)this + 38);
      *((_DWORD *)this + 78) = 0;
      CoTaskMemFree(v17);
      *((_QWORD *)this + 38) = 0;
      v16 = -2147418113;
      goto LABEL_18;
    }
    *((_DWORD *)this + 78) = v14;
    v15 = CoTaskMemAlloc(v14);
    *((_QWORD *)this + 38) = v15;
    if ( !v15 )
    {
      *((_DWORD *)this + 78) = 0;
      v16 = -2147024882;
LABEL_18:
      LeaveCriticalSection(v2);
      return v16;
    }
    memcpy_0(v15, v13, *((_DWORD *)this + 78) - (int)v6);
    CoTaskMemFree(v13);
    memcpy_0((void *)(*((_QWORD *)this + 38) + *((int *)this + 78) - v6), Src, v6);
    LODWORD(v6) = *((_DWORD *)this + 78);
    Src = (void *)*((_QWORD *)this + 38);
    v41 -= *((_QWORD *)this + 40);
  }
  LODWORD(v20) = 10000;
  v39 = 10000;
  while ( (int)v6 > 0 )
  {
    if ( (int)v20 <= 0 )
      break;
    v8 = (*(__int64 (__fastcall **)(_QWORD, struct IMediaSample **, _QWORD, _QWORD, _DWORD))(**((_QWORD **)this + 28)
                                                                                           + 128LL))(
           *((_QWORD *)this + 28),
           &v40,
           0,
           0,
           0);
    if ( v8 < 0 )
      break;
    SetSyncPoint = v40->lpVtbl->SetSyncPoint;
    v22 = ((__int64 (__fastcall *)(struct IMediaSample *))a2->lpVtbl->IsSyncPoint)(a2);
    ((void (__fastcall *)(struct IMediaSample *, bool))SetSyncPoint)(v40, v22 == 0);
    SetDiscontinuity = v40->lpVtbl->SetDiscontinuity;
    v24 = ((__int64 (__fastcall *)(struct IMediaSample *))a2->lpVtbl->IsDiscontinuity)(a2);
    ((void (__fastcall *)(struct IMediaSample *, bool))SetDiscontinuity)(v40, v24 == 0);
    v25 = CACMWrapper::ProcessSample(this, (unsigned __int8 *)Src, v6, v40, &v38, &v39, 1);
    v26 = (char *)Src;
    v8 = v25;
    if ( v38 > (int)v6 )
    {
      LODWORD(v6) = 0;
    }
    else
    {
      LODWORD(v6) = v6 - v38;
      v26 = (char *)Src + v38;
      Src = v26;
    }
    v20 = v39;
    if ( v39 || !(_DWORD)v6 )
      goto LABEL_37;
    v27 = (void *)*((_QWORD *)this + 38);
    if ( v27 )
    {
      v28 = (int)v6;
    }
    else
    {
      v29 = CoTaskMemAlloc((int)v6);
      *((_QWORD *)this + 38) = v29;
      if ( !v29 )
        goto LABEL_35;
      v26 = (char *)Src;
      v27 = v29;
      v28 = (int)v6;
    }
    memcpy_0(v27, v26, v28);
LABEL_35:
    if ( *((_QWORD *)this + 38) )
    {
      *((_QWORD *)this + 40) = v35 - v41;
      *((_DWORD *)this + 78) = v6;
LABEL_37:
      if ( !v8 && !(_DWORD)v6 )
      {
        v30 = (void *)*((_QWORD *)this + 38);
        *((_DWORD *)this + 78) = 0;
        CoTaskMemFree(v30);
        *((_QWORD *)this + 38) = 0;
      }
      goto LABEL_40;
    }
    *((_DWORD *)this + 78) = 0;
    v8 = -2147024882;
LABEL_40:
    v31 = *((unsigned int *)this + 70);
    if ( (_DWORD)v31 )
      v32 = 10000000 * v20 / v31;
    else
      v32 = 1;
    v36 = v32 + v41;
    v37 = v32;
    ((void (__fastcall *)(struct IMediaSample *, __int64 *, __int64 *))v40->lpVtbl->SetTime)(v40, &v41, &v36);
    v41 += v37;
    if ( v8 < 0 )
      goto LABEL_51;
    if ( v8 == 1 )
    {
      ((void (__fastcall *)(struct IMediaSample *))v40->lpVtbl->Release)(v40);
      v8 = 0;
      break;
    }
    if ( !v8 )
    {
      if ( (_DWORD)v20 )
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD, struct IMediaSample *))(**((_QWORD **)this + 28) + 136LL))(
               *((_QWORD *)this + 28),
               v40);
        if ( v8 )
        {
LABEL_51:
          ((void (__fastcall *)(struct IMediaSample *))v40->lpVtbl->Release)(v40);
          break;
        }
      }
    }
    ((void (__fastcall *)(struct IMediaSample *))v40->lpVtbl->Release)(v40);
  }
  LeaveCriticalSection(v2);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800233b0  push    rbp
0x1800233b2  push    rbx
0x1800233b3  push    rsi
0x1800233b4  push    rdi
0x1800233b5  push    r12
0x1800233b7  push    r13
0x1800233b9  push    r14
0x1800233bb  push    r15
0x1800233bd  mov     rbp, rsp
0x1800233c0  sub     rsp, 78h
0x1800233c4  xor     r13d, r13d
0x1800233c7  lea     rbx, [rcx+148h]
0x1800233ce  mov     rsi, rcx
0x1800233d1  mov     [rbp+arg_18], r13
0x1800233d5  mov     rcx, rbx; lpCriticalSection
0x1800233d8  mov     [rbp+var_28], r13
0x1800233dc  mov     r15, rdx
0x1800233df  mov     [rbp+var_20], r13
0x1800233e3  mov     [rbp+arg_10], r13
0x1800233e7  call    cs:__imp_EnterCriticalSection
0x1800233ee  nop     dword ptr [rax+rax+00h]
0x1800233f3  mov     rax, [r15]
0x1800233f6  lea     rdx, [rbp+pv]
0x1800233fa  mov     rcx, r15
0x1800233fd  mov     [rbp+Src], r13
0x180023401  mov     [rbp+arg_0], r13d
0x180023405  mov     [rbp+pv], r13
0x180023409  mov     rax, [rax+68h]
0x18002340d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023412  mov     rax, [rbp+pv]
0x180023416  test    rax, rax
0x180023419  jz      short loc_18002344E
0x18002341b  cmp     [rax+50h], r13
0x18002341f  jz      short loc_18002344E
0x180023421  mov     rcx, rsi; this
0x180023424  call    ?StopStreaming@CACMWrapper@@UEAAJXZ; CACMWrapper::StopStreaming(void)
0x180023429  mov     rcx, [rsi+0D8h]
0x180023430  mov     rdx, [rbp+pv]; struct _AMMediaType *
0x180023434  add     rcx, 68h ; 'h'; this
0x180023438  call    ?Set@CMediaType@@QEAAJAEBU_AMMediaType@@@Z; CMediaType::Set(_AMMediaType const &)
0x18002343d  mov     rcx, [rbp+pv]; pv
0x180023441  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x180023446  mov     rcx, rsi; this
0x180023449  call    ?StartStreaming@CACMWrapper@@UEAAJXZ; CACMWrapper::StartStreaming(void)
0x18002344e  mov     rax, [r15]
0x180023451  mov     rcx, r15
0x180023454  mov     rax, [rax+58h]
0x180023458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002345d  mov     rcx, [r15]
0x180023460  movsxd  r14, eax
0x180023463  mov     rax, [rcx+78h]
0x180023467  mov     rcx, r15
0x18002346a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002346f  test    eax, eax
0x180023471  jnz     short loc_18002347B
0x180023473  mov     rcx, rsi; this
0x180023476  call    ?SendExtraStuff@CACMWrapper@@QEAAJXZ; CACMWrapper::SendExtraStuff(void)
0x18002347b  mov     rax, [rsi+0D8h]
0x180023482  lea     r8, [rbp+var_28]
0x180023486  lea     rdx, [rbp+arg_18]
0x18002348a  mov     rcx, [rax+0B8h]
0x180023491  mov     rax, [r15]
0x180023494  movsxd  r12, dword ptr [rcx+8]
0x180023498  mov     rcx, r15
0x18002349b  mov     rax, [rax+28h]
0x18002349f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234a4  mov     edi, eax
0x1800234a6  test    eax, eax
0x1800234a8  jns     short loc_1800234D6
0x1800234aa  mov     r8, [rsi+110h]
0x1800234b1  mov     [rbp+arg_18], r8
0x1800234b5  test    r12d, r12d
0x1800234b8  jnz     short loc_1800234C1
0x1800234ba  lea     eax, [r12+1]
0x1800234bf  jmp     short loc_1800234CD
0x1800234c1  imul    rax, r14, 989680h
0x1800234c8  cqo
0x1800234ca  idiv    r12
0x1800234cd  add     rax, r8
0x1800234d0  mov     [rbp+var_28], rax
0x1800234d4  jmp     short loc_1800234DA
0x1800234d6  mov     rax, [rbp+var_28]
0x1800234da  mov     [rsi+110h], rax
0x1800234e1  lea     rdx, [rbp+Src]
0x1800234e5  mov     rax, [r15]
0x1800234e8  mov     rcx, r15
0x1800234eb  mov     rax, [rax+18h]
0x1800234ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234f4  mov     eax, [rsi+138h]
0x1800234fa  test    eax, eax
0x1800234fc  jle     loc_1800235E4
0x180023502  mov     r12, [rsi+130h]
0x180023509  lea     ecx, [rax+r14]
0x18002350d  cmp     ecx, eax
0x18002350f  jl      loc_1800235AA
0x180023515  mov     [rsi+138h], ecx
0x18002351b  movsxd  rcx, ecx; cb
0x18002351e  call    cs:__imp_CoTaskMemAlloc
0x180023525  nop     dword ptr [rax+rax+00h]
0x18002352a  mov     [rsi+130h], rax
0x180023531  mov     rcx, rax; void *
0x180023534  test    rax, rax
0x180023537  jnz     short loc_18002354B
0x180023539  mov     [rsi+138h], r13d
0x180023540  mov     r13d, 8007000Eh
0x180023546  jmp     loc_1800235CD
0x18002354b  mov     eax, [rsi+138h]
0x180023551  mov     rdx, r12; Src
0x180023554  sub     eax, r14d
0x180023557  movsxd  r8, eax; Size
0x18002355a  call    memcpy_0
0x18002355f  mov     rcx, r12; pv
0x180023562  call    cs:__imp_CoTaskMemFree
0x180023569  nop     dword ptr [rax+rax+00h]
0x18002356e  movsxd  rcx, dword ptr [rsi+138h]
0x180023575  mov     r8, r14; Size
0x180023578  mov     rdx, [rbp+Src]; Src
0x18002357c  sub     rcx, r14
0x18002357f  add     rcx, [rsi+130h]; void *
0x180023586  call    memcpy_0
0x18002358b  mov     rax, [rsi+130h]
0x180023592  mov     r14d, [rsi+138h]
0x180023599  mov     [rbp+Src], rax
0x18002359d  mov     rax, [rsi+140h]
0x1800235a4  sub     [rbp+arg_18], rax
0x1800235a8  jmp     short loc_180023607
0x1800235aa  mov     rcx, r12; pv
0x1800235ad  mov     [rsi+138h], r13d
0x1800235b4  call    cs:__imp_CoTaskMemFree
0x1800235bb  nop     dword ptr [rax+rax+00h]
0x1800235c0  mov     [rsi+130h], r13
0x1800235c7  mov     r13d, 8000FFFFh
0x1800235cd  mov     rcx, rbx; lpCriticalSection
0x1800235d0  call    cs:__imp_LeaveCriticalSection
0x1800235d7  nop     dword ptr [rax+rax+00h]
0x1800235dc  mov     eax, r13d
0x1800235df  jmp     loc_180023872
0x1800235e4  jns     short loc_180023607
0x1800235e6  mov     rcx, [rsi+130h]; pv
0x1800235ed  mov     [rsi+138h], r13d
0x1800235f4  call    cs:__imp_CoTaskMemFree
0x1800235fb  nop     dword ptr [rax+rax+00h]
0x180023600  mov     [rsi+130h], r13
0x180023607  mov     r12d, 2710h
0x18002360d  mov     r13d, 8007000Eh
0x180023613  mov     [rbp+arg_8], r12d
0x180023617  test    r14d, r14d
0x18002361a  jle     loc_180023861
0x180023620  test    r12d, r12d
0x180023623  jle     loc_180023861
0x180023629  mov     rcx, [rsi+0E0h]
0x180023630  lea     rdx, [rbp+arg_10]
0x180023634  xor     r9d, r9d
0x180023637  mov     dword ptr [rsp+78h+var_58], 0
0x18002363f  xor     r8d, r8d
0x180023642  mov     rax, [rcx]
0x180023645  mov     rax, [rax+80h]
0x18002364c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023651  mov     edi, eax
0x180023653  test    eax, eax
0x180023655  js      loc_180023861
0x18002365b  mov     rax, [rbp+arg_10]
0x18002365f  mov     rcx, [rax]
0x180023662  mov     rdi, [rcx+40h]
0x180023666  mov     rcx, [r15]
0x180023669  mov     rax, [rcx+38h]
0x18002366d  mov     rcx, r15
0x180023670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023675  mov     rcx, [rbp+arg_10]
0x180023679  xor     edx, edx
0x18002367b  test    eax, eax
0x18002367d  mov     rax, rdi
0x180023680  setz    dl
0x180023683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023688  mov     rax, [rbp+arg_10]
0x18002368c  mov     rcx, [rax]
0x18002368f  mov     rdi, [rcx+80h]
0x180023696  mov     rcx, [r15]
0x180023699  mov     rax, [rcx+78h]
0x18002369d  mov     rcx, r15
0x1800236a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800236a5  mov     rcx, [rbp+arg_10]
0x1800236a9  xor     edx, edx
0x1800236ab  test    eax, eax
0x1800236ad  mov     rax, rdi
0x1800236b0  setz    dl
0x1800236b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800236b8  mov     r9, [rbp+arg_10]; struct IMediaSample *
0x1800236bc  lea     rax, [rbp+arg_8]
0x1800236c0  mov     rdx, [rbp+Src]; unsigned __int8 *
0x1800236c4  mov     r8d, r14d; int
0x1800236c7  mov     [rsp+78h+var_48], 1; int
0x1800236cf  mov     rcx, rsi; this
0x1800236d2  mov     [rsp+78h+var_50], rax; int *
0x1800236d7  lea     rax, [rbp+arg_0]
0x1800236db  mov     [rsp+78h+var_58], rax; int *
0x1800236e0  call    ?ProcessSample@CACMWrapper@@QEAAJPEAEJPEAUIMediaSample@@PEAJ2H@Z; CACMWrapper::ProcessSample(uchar *,long,IMediaSample *,long *,long *,int)
0x1800236e5  mov     rdx, [rbp+Src]
0x1800236e9  mov     edi, eax
0x1800236eb  movsxd  rax, [rbp+arg_0]
0x1800236ef  cmp     eax, r14d
0x1800236f2  jg      short loc_180023700
0x1800236f4  sub     r14d, eax
0x1800236f7  add     rdx, rax
0x1800236fa  mov     [rbp+Src], rdx
0x1800236fe  jmp     short loc_180023703
0x180023700  xor     r14d, r14d
0x180023703  movsxd  r12, [rbp+arg_8]
0x180023707  test    r12d, r12d
0x18002370a  jnz     short loc_18002376F
0x18002370c  test    r14d, r14d
0x18002370f  jz      short loc_18002376F
0x180023711  mov     rcx, [rsi+130h]
0x180023718  movsxd  rax, r14d
0x18002371b  test    rcx, rcx
0x18002371e  jz      short loc_180023725
0x180023720  mov     r8, rax
0x180023723  jmp     short loc_18002374A
0x180023725  mov     rcx, rax; cb
0x180023728  call    cs:__imp_CoTaskMemAlloc
0x18002372f  nop     dword ptr [rax+rax+00h]
0x180023734  mov     [rsi+130h], rax
0x18002373b  test    rax, rax
0x18002373e  jz      short loc_18002374F
0x180023740  mov     rdx, [rbp+Src]; Src
0x180023744  mov     rcx, rax; void *
0x180023747  movsxd  r8, r14d; Size
0x18002374a  call    memcpy_0
0x18002374f  cmp     qword ptr [rsi+130h], 0
0x180023757  jz      short loc_1800237AC
0x180023759  mov     rax, [rbp+var_28]
0x18002375d  sub     rax, [rbp+arg_18]
0x180023761  mov     [rsi+140h], rax
0x180023768  mov     [rsi+138h], r14d
0x18002376f  test    edi, edi
0x180023771  jnz     short loc_18002379D
0x180023773  test    r14d, r14d
0x180023776  jnz     short loc_18002379D
0x180023778  mov     rcx, [rsi+130h]; pv
0x18002377f  mov     [rsi+138h], r14d
0x180023786  call    cs:__imp_CoTaskMemFree
0x18002378d  nop     dword ptr [rax+rax+00h]
0x180023792  mov     qword ptr [rsi+130h], 0
0x18002379d  mov     ecx, [rsi+118h]
0x1800237a3  test    ecx, ecx
0x1800237a5  jnz     short loc_1800237BB
0x1800237a7  lea     eax, [rcx+1]
0x1800237aa  jmp     short loc_1800237C7
0x1800237ac  mov     dword ptr [rsi+138h], 0
0x1800237b6  mov     edi, r13d
0x1800237b9  jmp     short loc_18002379D
0x1800237bb  imul    rax, r12, 989680h
0x1800237c2  cqo
0x1800237c4  idiv    rcx
0x1800237c7  mov     rdx, [rbp+arg_18]
0x1800237cb  lea     r8, [rbp+var_20]
0x1800237cf  mov     rcx, [rbp+arg_10]
0x1800237d3  add     rdx, rax
0x1800237d6  mov     [rbp+var_20], rdx
0x1800237da  mov     [rbp+var_18], rax
0x1800237de  mov     rdx, [rcx]
0x1800237e1  mov     rax, [rdx+30h]
0x1800237e5  lea     rdx, [rbp+arg_18]
0x1800237e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237ee  mov     rax, [rbp+var_18]
0x1800237f2  add     [rbp+arg_18], rax
0x1800237f6  test    edi, edi
0x1800237f8  js      short loc_180023851
0x1800237fa  cmp     edi, 1
0x1800237fd  jz      short loc_18002383D
0x1800237ff  test    edi, edi
0x180023801  jnz     short loc_180023828
0x180023803  test    r12d, r12d
0x180023806  jz      short loc_180023828
0x180023808  mov     rcx, [rsi+0E0h]
0x18002380f  mov     rdx, [rbp+arg_10]
0x180023813  mov     rax, [rcx]
0x180023816  mov     rax, [rax+88h]
0x18002381d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023822  mov     edi, eax
0x180023824  test    eax, eax
0x180023826  jnz     short loc_180023851
0x180023828  mov     rcx, [rbp+arg_10]
0x18002382c  mov     rax, [rcx]
0x18002382f  mov     rax, [rax+10h]
0x180023833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023838  jmp     loc_180023617
0x18002383d  mov     rcx, [rbp+arg_10]
0x180023841  mov     rax, [rcx]
0x180023844  mov     rax, [rax+10h]
0x180023848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002384d  xor     edi, edi
0x18002384f  jmp     short loc_180023861
0x180023851  mov     rcx, [rbp+arg_10]
0x180023855  mov     rax, [rcx]
0x180023858  mov     rax, [rax+10h]
0x18002385c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023861  mov     rcx, rbx; lpCriticalSection
0x180023864  call    cs:__imp_LeaveCriticalSection
0x18002386b  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
