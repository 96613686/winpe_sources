# CFilterGraph::CreateFilterAndNotify(IMoniker *,IBaseFilter * *)

- ea: `0x180014400`
- end: `0x1800146d5`
- name: `?CreateFilterAndNotify@CFilterGraph@@AEAAJPEAUIMoniker@@PEAPEAUIBaseFilter@@@Z`
- size: `725`
- prototype: `__int64 __fastcall(CFilterGraph *__hidden this, struct IMoniker *, struct IBaseFilter **)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180009630`
- `0x18001a404`
- `0x18002b670`

## callees

- `0x180014400`
- `0x1800146e0`
- `0x18001476c`
- `0x180014880`
- `0x180038458`
- `0x180038498`
- `0x1800384a4`
- `0x18006a4fc`
- `0x18006a54c`
- `0x18015bb98`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800144bb`
- `KERNEL32!LeaveCriticalSection` at `0x18001459b`
- `KERNEL32!LeaveCriticalSection` at `0x1800145f9`
- `KERNEL32!LeaveCriticalSection` at `0x1800144bb`
- `KERNEL32!LeaveCriticalSection` at `0x18001459b`
- `KERNEL32!LeaveCriticalSection` at `0x1800145f9`
- `KERNEL32!EnterCriticalSection` at `0x180014471`
- `KERNEL32!EnterCriticalSection` at `0x180014471`
- `KERNEL32!GetCurrentThreadId` at `0x18001460b`
- `KERNEL32!GetCurrentThreadId` at `0x18001460b`
- `KERNEL32!QueryPerformanceCounter` at `0x1800145c1`
- `KERNEL32!QueryPerformanceCounter` at `0x1800145c1`
- `KERNEL32!lstrcmpiW` at `0x1800144a0`
- `KERNEL32!lstrcmpiW` at `0x1800144a0`

## string_xrefs

- `0x18001448f`: `Create Filter`
- `0x1800144df`: `Create Filter`

## pseudocode

```c
__int64 __fastcall CFilterGraph::CreateFilterAndNotify(
        CFilterGraph *this,
        struct IMoniker *a2,
        struct IBaseFilter **a3)
{
  int v6; // ebx
  int i; // ebx
  CStat *v8; // rax
  CStat *v9; // rax
  unsigned int v10; // edx
  CStat *v11; // rbx
  signed int v12; // eax
  void *v13; // rax
  void *v14; // rdi
  unsigned int v15; // ebx
  int v16; // ebx
  int FilterHelper; // eax
  int v19; // [rsp+30h] [rbp-58h] BYREF
  double v20; // [rsp+38h] [rbp-50h]
  _QWORD v21[9]; // [rsp+40h] [rbp-48h] BYREF
  void *v22; // [rsp+90h] [rbp+8h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+A8h] [rbp+20h] BYREF

  v22 = 0;
  CFilterGraph::GetSite((CFilterGraph *)((char *)this + 24), &IID_IAMGraphBuilderCallback, &v22);
  if ( v22 )
  {
    v6 = (*(__int64 (__fastcall **)(void *, struct IMoniker *))(*(_QWORD *)v22 + 24LL))(v22, a2);
    if ( v6 < 0 )
      goto LABEL_27;
  }
  v19 = -1;
  EnterCriticalSection(&CriticalSection);
  for ( i = 0; i < (int)dword_1801A1C98; ++i )
  {
    if ( !lstrcmpiW(L"Create Filter", **((LPCWSTR **)g_Stats + i)) )
    {
      LeaveCriticalSection(&CriticalSection);
      goto LABEL_16;
    }
  }
  v8 = (CStat *)operator new(0x40u);
  if ( !v8 || (v9 = CStat::CStat(v8, L"Create Filter"), (v11 = v9) == 0) )
  {
LABEL_19:
    LeaveCriticalSection(&CriticalSection);
    goto LABEL_20;
  }
  if ( !*(_QWORD *)v9 )
    goto LABEL_18;
  v12 = dword_1801A1C98;
  if ( (int)dword_1801A1C98 % 16 )
  {
    v14 = g_Stats;
    goto LABEL_15;
  }
  v13 = operator new[](saturated_mul((int)(dword_1801A1C98 + 16), 8u));
  v14 = v13;
  if ( !v13 )
  {
LABEL_18:
    CStat::`scalar deleting destructor'(v11, v10);
    goto LABEL_19;
  }
  memcpy_0(v13, g_Stats, 8LL * (int)dword_1801A1C98);
  operator delete(g_Stats);
  v12 = dword_1801A1C98;
  g_Stats = v14;
LABEL_15:
  *((_QWORD *)v14 + v12) = v11;
  v15 = ++dword_1801A1C98;
  LeaveCriticalSection(&CriticalSection);
  i = v15 - 1;
LABEL_16:
  v19 = i;
  if ( i >= 0 )
  {
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    v20 = (double)(int)PerformanceCount.LowPart * *(double *)&qword_1801A1CC8;
  }
LABEL_20:
  v16 = *((_DWORD *)this + 121);
  if ( GetCurrentThreadId() == v16 )
  {
    FilterHelper = ((__int64 (__fastcall *)(struct IMoniker *, _QWORD, _QWORD, GUID *, struct IBaseFilter **))a2->lpVtbl->BindToObject)(
                     a2,
                     *((_QWORD *)this + 79),
                     0,
                     &IID_IBaseFilter,
                     a3);
  }
  else
  {
    v21[1] = 0;
    v21[2] = 0;
    v21[0] = a2;
    FilterHelper = CFilterGraph::CreateFilterHelper(this, (const struct AwmCreateFilterArg *)v21, a3);
  }
  v6 = FilterHelper;
  CAutoTimer::~CAutoTimer((CAutoTimer *)&v19);
  if ( v6 >= 0 )
  {
    if ( !v22 )
      return (unsigned int)v6;
    v6 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v22 + 32LL))(v22, *a3);
    if ( v6 < 0 )
    {
      ((void (__fastcall *)(_QWORD))(*a3)->lpVtbl->Release)(*a3);
      *a3 = 0;
    }
  }
LABEL_27:
  if ( v22 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v22 + 16LL))(v22);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180014400  mov     rax, rsp
0x180014403  push    rbx
0x180014404  push    rbp
0x180014405  push    rsi
0x180014406  push    r14
0x180014408  push    r15
0x18001440a  sub     rsp, 60h
0x18001440e  mov     r15, r8
0x180014411  mov     r14, rdx
0x180014414  mov     rsi, rcx
0x180014417  lea     r8, [rax+8]; void **
0x18001441b  xor     ebp, ebp
0x18001441d  lea     rdx, IID_IAMGraphBuilderCallback; struct _GUID *
0x180014424  add     rcx, 18h; this
0x180014428  mov     [rax+8], rbp
0x18001442c  call    ?GetSite@CFilterGraph@@UEAAJAEBU_GUID@@PEAPEAX@Z; CFilterGraph::GetSite(_GUID const &,void * *)
0x180014431  mov     rcx, [rsp+88h+arg_0]
0x180014439  test    rcx, rcx
0x18001443c  jz      short loc_180014457
0x18001443e  mov     rax, [rcx]
0x180014441  mov     rdx, r14
0x180014444  mov     rax, [rax+18h]
0x180014448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001444d  mov     ebx, eax
0x18001444f  test    eax, eax
0x180014451  js      loc_1800146AD
0x180014457  mov     [rsp+88h+arg_8], rdi
0x18001445f  lea     rcx, CriticalSection; lpCriticalSection
0x180014466  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18001446d  mov     [rsp+88h+var_58], edi
0x180014471  call    cs:__imp_EnterCriticalSection
0x180014478  nop     dword ptr [rax+rax+00h]
0x18001447d  mov     ebx, ebp
0x18001447f  nop
0x180014480  cmp     ebx, cs:dword_1801A1C98
0x180014486  jge     short loc_1800144CC
0x180014488  mov     rax, cs:?g_Stats@@3VCStats@@A; CStats g_Stats
0x18001448f  lea     rcx, aCreateFilter; "Create Filter"
0x180014496  movsxd  rdx, ebx
0x180014499  mov     rdx, [rax+rdx*8]
0x18001449d  mov     rdx, [rdx]; lpString2
0x1800144a0  call    cs:__imp_lstrcmpiW
0x1800144a7  nop     dword ptr [rax+rax+00h]
0x1800144ac  test    eax, eax
0x1800144ae  jz      short loc_1800144B4
0x1800144b0  inc     ebx
0x1800144b2  jmp     short loc_180014480
0x1800144b4  lea     rcx, CriticalSection; lpCriticalSection
0x1800144bb  call    cs:__imp_LeaveCriticalSection
0x1800144c2  nop     dword ptr [rax+rax+00h]
0x1800144c7  jmp     loc_1800145A9
0x1800144cc  mov     ecx, 40h ; '@'; Size
0x1800144d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800144d6  test    rax, rax
0x1800144d9  jz      loc_1800145F2
0x1800144df  lea     rdx, aCreateFilter; "Create Filter"
0x1800144e6  mov     rcx, rax; this
0x1800144e9  call    ??0CStat@@QEAA@PEBG@Z; CStat::CStat(ushort const *)
0x1800144ee  mov     rbx, rax
0x1800144f1  test    rax, rax
0x1800144f4  jz      loc_1800145F2
0x1800144fa  cmp     [rax], rbp
0x1800144fd  jz      loc_1800145EA
0x180014503  mov     eax, cs:dword_1801A1C98
0x180014509  mov     ecx, eax
0x18001450b  and     ecx, 8000000Fh
0x180014511  jge     short loc_18001451A
0x180014513  dec     ecx
0x180014515  or      ecx, 0FFFFFFF0h
0x180014518  inc     ecx
0x18001451a  test    ecx, ecx
0x18001451c  jnz     short loc_180014579
0x18001451e  add     eax, 10h
0x180014521  movsxd  rcx, eax
0x180014524  mov     eax, 8
0x180014529  mul     rcx
0x18001452c  cmovb   rax, rdi
0x180014530  mov     rcx, rax; unsigned __int64
0x180014533  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014538  mov     rdi, rax
0x18001453b  test    rax, rax
0x18001453e  jz      loc_1800145EA
0x180014544  movsxd  r8, cs:dword_1801A1C98
0x18001454b  mov     rcx, rax; void *
0x18001454e  mov     rdx, cs:?g_Stats@@3VCStats@@A; Src
0x180014555  shl     r8, 3; Size
0x180014559  call    memcpy_0
0x18001455e  mov     rcx, cs:?g_Stats@@3VCStats@@A; Block
0x180014565  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001456a  mov     eax, cs:dword_1801A1C98
0x180014570  mov     cs:?g_Stats@@3VCStats@@A, rdi; CStats g_Stats
0x180014577  jmp     short loc_180014580
0x180014579  mov     rdi, cs:?g_Stats@@3VCStats@@A; CStats g_Stats
0x180014580  cdqe
0x180014582  lea     rcx, CriticalSection; lpCriticalSection
0x180014589  mov     [rdi+rax*8], rbx
0x18001458d  mov     ebx, cs:dword_1801A1C98
0x180014593  inc     ebx
0x180014595  mov     cs:dword_1801A1C98, ebx
0x18001459b  call    cs:__imp_LeaveCriticalSection
0x1800145a2  nop     dword ptr [rax+rax+00h]
0x1800145a7  dec     ebx
0x1800145a9  mov     [rsp+88h+var_58], ebx
0x1800145ad  test    ebx, ebx
0x1800145af  js      short loc_180014605
0x1800145b1  lea     rcx, [rsp+88h+PerformanceCount]; lpPerformanceCount
0x1800145b9  mov     qword ptr [rsp+88h+PerformanceCount], rbp
0x1800145c1  call    cs:__imp_QueryPerformanceCounter
0x1800145c8  nop     dword ptr [rax+rax+00h]
0x1800145cd  xorps   xmm0, xmm0
0x1800145d0  cvtsi2sd xmm0, qword ptr [rsp+88h+PerformanceCount]
0x1800145da  mulsd   xmm0, cs:qword_1801A1CC8
0x1800145e2  movsd   [rsp+88h+var_50], xmm0
0x1800145e8  jmp     short loc_180014605
0x1800145ea  mov     rcx, rbx; this
0x1800145ed  call    ??_GCStat@@QEAAPEAXI@Z; CStat::`scalar deleting destructor'(uint)
0x1800145f2  lea     rcx, CriticalSection; lpCriticalSection
0x1800145f9  call    cs:__imp_LeaveCriticalSection
0x180014600  nop     dword ptr [rax+rax+00h]
0x180014605  mov     ebx, [rsi+1E4h]
0x18001460b  call    cs:__imp_GetCurrentThreadId
0x180014612  nop     dword ptr [rax+rax+00h]
0x180014617  mov     rdi, [rsp+88h+arg_8]
0x18001461f  cmp     eax, ebx
0x180014621  jnz     short loc_18001464A
0x180014623  mov     rax, [r14]
0x180014626  lea     r9, IID_IBaseFilter
0x18001462d  mov     rdx, [rsi+278h]
0x180014634  xor     r8d, r8d
0x180014637  mov     rcx, r14
0x18001463a  mov     [rsp+88h+var_68], r15
0x18001463f  mov     rax, [rax+40h]
0x180014643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014648  jmp     short loc_180014669
0x18001464a  mov     r8, r15; struct IBaseFilter **
0x18001464d  mov     [rsp+88h+var_40], rbp
0x180014652  lea     rdx, [rsp+88h+var_48]; struct AwmCreateFilterArg *
0x180014657  mov     [rsp+88h+var_38], rbp
0x18001465c  mov     rcx, rsi; this
0x18001465f  mov     [rsp+88h+var_48], r14
0x180014664  call    ?CreateFilterHelper@CFilterGraph@@AEAAJPEBUAwmCreateFilterArg@@PEAPEAUIBaseFilter@@@Z; CFilterGraph::CreateFilterHelper(AwmCreateFilterArg const *,IBaseFilter * *)
0x180014669  lea     rcx, [rsp+88h+var_58]; this
0x18001466e  mov     ebx, eax
0x180014670  call    ??1CAutoTimer@@QEAA@XZ; CAutoTimer::~CAutoTimer(void)
0x180014675  test    ebx, ebx
0x180014677  js      short loc_1800146AD
0x180014679  mov     rcx, [rsp+88h+arg_0]
0x180014681  test    rcx, rcx
0x180014684  jz      short loc_1800146C6
0x180014686  mov     rax, [rcx]
0x180014689  mov     rdx, [r15]
0x18001468c  mov     rax, [rax+20h]
0x180014690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014695  mov     ebx, eax
0x180014697  test    eax, eax
0x180014699  jns     short loc_1800146AD
0x18001469b  mov     rcx, [r15]
0x18001469e  mov     rax, [rcx]
0x1800146a1  mov     rax, [rax+10h]
0x1800146a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146aa  mov     [r15], rbp
0x1800146ad  mov     rcx, [rsp+88h+arg_0]
0x1800146b5  test    rcx, rcx
0x1800146b8  jz      short loc_1800146C6
0x1800146ba  mov     rax, [rcx]
0x1800146bd  mov     rax, [rax+10h]
0x1800146c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146c6  mov     eax, ebx
0x1800146c8  add     rsp, 60h
0x1800146cc  pop     r15
0x1800146ce  pop     r14
0x1800146d0  pop     rsi
0x1800146d1  pop     rbp
0x1800146d2  pop     rbx
0x1800146d3  retn
```
