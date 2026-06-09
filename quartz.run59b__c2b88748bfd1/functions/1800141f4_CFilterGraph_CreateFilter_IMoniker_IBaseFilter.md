# CFilterGraph::CreateFilter(IMoniker *,IBaseFilter * *)

- ea: `0x1800141f4`
- end: `0x1800143ee`
- name: `?CreateFilter@CFilterGraph@@AEAAJPEAUIMoniker@@PEAPEAUIBaseFilter@@@Z`
- size: `506`
- prototype: `__int64 __fastcall(CFilterGraph *__hidden this, struct IMoniker *, struct IBaseFilter **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180060870`

## callees

- `0x1800141f4`
- `0x18001476c`
- `0x180014880`
- `0x180014b20`
- `0x180038458`
- `0x180038498`
- `0x1800384a4`
- `0x18006a4fc`
- `0x18006a54c`
- `0x18015bb98`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180014261`
- `KERNEL32!LeaveCriticalSection` at `0x180014334`
- `KERNEL32!LeaveCriticalSection` at `0x180014362`
- `KERNEL32!LeaveCriticalSection` at `0x180014261`
- `KERNEL32!LeaveCriticalSection` at `0x180014334`
- `KERNEL32!LeaveCriticalSection` at `0x180014362`
- `KERNEL32!EnterCriticalSection` at `0x18001421c`
- `KERNEL32!EnterCriticalSection` at `0x18001421c`
- `KERNEL32!GetCurrentThreadId` at `0x180014374`
- `KERNEL32!GetCurrentThreadId` at `0x180014374`
- `KERNEL32!lstrcmpiW` at `0x18001424a`
- `KERNEL32!lstrcmpiW` at `0x18001424a`

## string_xrefs

- `0x180014239`: `Create Filter`
- `0x180014285`: `Create Filter`

## pseudocode

```c
__int64 __fastcall CFilterGraph::CreateFilter(CFilterGraph *this, struct IMoniker *a2, struct IBaseFilter **a3)
{
  int i; // ebx
  CStats *v7; // rcx
  CStat *v8; // rax
  CStat *v9; // rax
  unsigned int v10; // edx
  CStat *v11; // rbx
  signed int v12; // ecx
  void *v13; // rax
  void *v14; // rdi
  unsigned int v15; // ebx
  int v16; // ebx
  unsigned int FilterHelper; // eax
  unsigned int v18; // ebx
  int v20; // [rsp+30h] [rbp-68h] BYREF
  double Time; // [rsp+38h] [rbp-60h]
  _QWORD v22[11]; // [rsp+40h] [rbp-58h] BYREF

  v20 = -1;
  EnterCriticalSection(&CriticalSection);
  for ( i = 0; i < (int)dword_1801A1C98; ++i )
  {
    if ( !lstrcmpiW(L"Create Filter", **((LPCWSTR **)g_Stats + i)) )
    {
      LeaveCriticalSection(&CriticalSection);
      goto LABEL_14;
    }
  }
  v8 = (CStat *)operator new(0x40u);
  if ( !v8 || (v9 = CStat::CStat(v8, L"Create Filter"), (v11 = v9) == 0) )
  {
LABEL_17:
    LeaveCriticalSection(&CriticalSection);
    goto LABEL_18;
  }
  if ( !*(_QWORD *)v9 )
    goto LABEL_16;
  v12 = dword_1801A1C98;
  if ( (int)dword_1801A1C98 % 16 )
  {
    v14 = g_Stats;
    goto LABEL_13;
  }
  v13 = operator new[](saturated_mul((int)(dword_1801A1C98 + 16), 8u));
  v14 = v13;
  if ( !v13 )
  {
LABEL_16:
    CStat::`scalar deleting destructor'(v11, v10);
    goto LABEL_17;
  }
  memcpy_0(v13, g_Stats, 8LL * (int)dword_1801A1C98);
  operator delete(g_Stats);
  v12 = dword_1801A1C98;
  g_Stats = v14;
LABEL_13:
  *((_QWORD *)v14 + v12) = v11;
  v15 = ++dword_1801A1C98;
  LeaveCriticalSection(&CriticalSection);
  i = v15 - 1;
LABEL_14:
  v20 = i;
  if ( i >= 0 )
    Time = CStats::GetTime(v7);
LABEL_18:
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
    v22[1] = 0;
    v22[2] = 0;
    v22[0] = a2;
    FilterHelper = CFilterGraph::CreateFilterHelper(this, (const struct AwmCreateFilterArg *)v22, a3);
  }
  v18 = FilterHelper;
  CAutoTimer::~CAutoTimer((CAutoTimer *)&v20);
  return v18;
}

```

## disassembly

```asm
0x1800141f4  push    rbx
0x1800141f6  push    rbp
0x1800141f7  push    rsi
0x1800141f8  push    rdi
0x1800141f9  push    r12
0x1800141fb  push    r14
0x1800141fd  sub     rsp, 68h
0x180014201  mov     rsi, rcx
0x180014204  lea     r12, CriticalSection
0x18001420b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001420f  mov     rcx, r12; lpCriticalSection
0x180014212  mov     rbp, r8
0x180014215  mov     [rsp+98h+var_68], edi
0x180014219  mov     r14, rdx
0x18001421c  call    cs:__imp_EnterCriticalSection
0x180014223  nop     dword ptr [rax+rax+00h]
0x180014228  xor     ebx, ebx
0x18001422a  cmp     ebx, cs:dword_1801A1C98
0x180014230  jge     short loc_180014272
0x180014232  mov     rax, cs:?g_Stats@@3VCStats@@A; CStats g_Stats
0x180014239  lea     rcx, aCreateFilter; "Create Filter"
0x180014240  movsxd  rdx, ebx
0x180014243  mov     rdx, [rax+rdx*8]
0x180014247  mov     rdx, [rdx]; lpString2
0x18001424a  call    cs:__imp_lstrcmpiW
0x180014251  nop     dword ptr [rax+rax+00h]
0x180014256  test    eax, eax
0x180014258  jz      short loc_18001425E
0x18001425a  inc     ebx
0x18001425c  jmp     short loc_18001422A
0x18001425e  mov     rcx, r12; lpCriticalSection
0x180014261  call    cs:__imp_LeaveCriticalSection
0x180014268  nop     dword ptr [rax+rax+00h]
0x18001426d  jmp     loc_180014342
0x180014272  mov     ecx, 40h ; '@'; Size
0x180014277  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001427c  test    rax, rax
0x18001427f  jz      loc_18001435F
0x180014285  lea     rdx, aCreateFilter; "Create Filter"
0x18001428c  mov     rcx, rax; this
0x18001428f  call    ??0CStat@@QEAA@PEBG@Z; CStat::CStat(ushort const *)
0x180014294  mov     rbx, rax
0x180014297  test    rax, rax
0x18001429a  jz      loc_18001435F
0x1800142a0  cmp     qword ptr [rax], 0
0x1800142a4  jz      loc_180014357
0x1800142aa  mov     ecx, cs:dword_1801A1C98
0x1800142b0  mov     r8d, 10h
0x1800142b6  mov     eax, ecx
0x1800142b8  cdq
0x1800142b9  idiv    r8d
0x1800142bc  test    edx, edx
0x1800142be  jnz     short loc_180014315
0x1800142c0  lea     eax, [rcx+10h]
0x1800142c3  movsxd  rcx, eax
0x1800142c6  lea     eax, [rdx+8]
0x1800142c9  mul     rcx
0x1800142cc  cmovb   rax, rdi
0x1800142d0  mov     rcx, rax; unsigned __int64
0x1800142d3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800142d8  mov     rdi, rax
0x1800142db  test    rax, rax
0x1800142de  jz      short loc_180014357
0x1800142e0  movsxd  r8, cs:dword_1801A1C98
0x1800142e7  mov     rcx, rax; void *
0x1800142ea  mov     rdx, cs:?g_Stats@@3VCStats@@A; Src
0x1800142f1  shl     r8, 3; Size
0x1800142f5  call    memcpy_0
0x1800142fa  mov     rcx, cs:?g_Stats@@3VCStats@@A; Block
0x180014301  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014306  mov     ecx, cs:dword_1801A1C98
0x18001430c  mov     cs:?g_Stats@@3VCStats@@A, rdi; CStats g_Stats
0x180014313  jmp     short loc_18001431C
0x180014315  mov     rdi, cs:?g_Stats@@3VCStats@@A; CStats g_Stats
0x18001431c  movsxd  rax, ecx
0x18001431f  mov     rcx, r12; lpCriticalSection
0x180014322  mov     [rdi+rax*8], rbx
0x180014326  mov     ebx, cs:dword_1801A1C98
0x18001432c  inc     ebx
0x18001432e  mov     cs:dword_1801A1C98, ebx
0x180014334  call    cs:__imp_LeaveCriticalSection
0x18001433b  nop     dword ptr [rax+rax+00h]
0x180014340  dec     ebx
0x180014342  mov     [rsp+98h+var_68], ebx
0x180014346  test    ebx, ebx
0x180014348  js      short loc_18001436E
0x18001434a  call    ?GetTime@CStats@@QEAANXZ; CStats::GetTime(void)
0x18001434f  movsd   [rsp+98h+var_60], xmm0
0x180014355  jmp     short loc_18001436E
0x180014357  mov     rcx, rbx; this
0x18001435a  call    ??_GCStat@@QEAAPEAXI@Z; CStat::`scalar deleting destructor'(uint)
0x18001435f  mov     rcx, r12; lpCriticalSection
0x180014362  call    cs:__imp_LeaveCriticalSection
0x180014369  nop     dword ptr [rax+rax+00h]
0x18001436e  mov     ebx, [rsi+1E4h]
0x180014374  call    cs:__imp_GetCurrentThreadId
0x18001437b  nop     dword ptr [rax+rax+00h]
0x180014380  cmp     eax, ebx
0x180014382  jnz     short loc_1800143AB
0x180014384  mov     rax, [r14]
0x180014387  lea     r9, IID_IBaseFilter
0x18001438e  mov     rdx, [rsi+278h]
0x180014395  xor     r8d, r8d
0x180014398  mov     rcx, r14
0x18001439b  mov     [rsp+98h+var_78], rbp
0x1800143a0  mov     rax, [rax+40h]
0x1800143a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143a9  jmp     short loc_1800143D2
0x1800143ab  mov     r8, rbp; struct IBaseFilter **
0x1800143ae  mov     [rsp+98h+var_50], 0
0x1800143b7  lea     rdx, [rsp+98h+var_58]; struct AwmCreateFilterArg *
0x1800143bc  mov     [rsp+98h+var_48], 0
0x1800143c5  mov     rcx, rsi; this
0x1800143c8  mov     [rsp+98h+var_58], r14
0x1800143cd  call    ?CreateFilterHelper@CFilterGraph@@AEAAJPEBUAwmCreateFilterArg@@PEAPEAUIBaseFilter@@@Z; CFilterGraph::CreateFilterHelper(AwmCreateFilterArg const *,IBaseFilter * *)
0x1800143d2  lea     rcx, [rsp+98h+var_68]; this
0x1800143d7  mov     ebx, eax
0x1800143d9  call    ??1CAutoTimer@@QEAA@XZ; CAutoTimer::~CAutoTimer(void)
0x1800143de  mov     eax, ebx
0x1800143e0  add     rsp, 68h
0x1800143e4  pop     r14
0x1800143e6  pop     r12
0x1800143e8  pop     rdi
0x1800143e9  pop     rsi
0x1800143ea  pop     rbp
0x1800143eb  pop     rbx
0x1800143ec  retn
```
