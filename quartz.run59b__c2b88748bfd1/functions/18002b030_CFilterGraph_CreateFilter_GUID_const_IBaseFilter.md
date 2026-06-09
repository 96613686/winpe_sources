# CFilterGraph::CreateFilter(_GUID const *,IBaseFilter * *)

- ea: `0x18002b030`
- end: `0x18002b211`
- name: `?CreateFilter@CFilterGraph@@AEAAJPEBU_GUID@@PEAPEAUIBaseFilter@@@Z`
- size: `481`
- prototype: `__int64 __fastcall(CFilterGraph *__hidden this, const struct _GUID *, struct IBaseFilter **)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180060870`
- `0x180061f04`

## callees

- `0x18001476c`
- `0x180014880`
- `0x180014b20`
- `0x18002b030`
- `0x18002b218`
- `0x180038458`
- `0x180038498`
- `0x1800384a4`
- `0x18006a4fc`
- `0x18006a54c`
- `0x18015bb98`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18002b09d`
- `KERNEL32!LeaveCriticalSection` at `0x18002b170`
- `KERNEL32!LeaveCriticalSection` at `0x18002b19e`
- `KERNEL32!LeaveCriticalSection` at `0x18002b09d`
- `KERNEL32!LeaveCriticalSection` at `0x18002b170`
- `KERNEL32!LeaveCriticalSection` at `0x18002b19e`
- `KERNEL32!EnterCriticalSection` at `0x18002b058`
- `KERNEL32!EnterCriticalSection` at `0x18002b058`
- `KERNEL32!GetCurrentThreadId` at `0x18002b1b1`
- `KERNEL32!GetCurrentThreadId` at `0x18002b1b1`
- `KERNEL32!lstrcmpiW` at `0x18002b086`
- `KERNEL32!lstrcmpiW` at `0x18002b086`

## string_xrefs

- `0x18002b075`: `Create Filter`
- `0x18002b0c1`: `Create Filter`

## pseudocode

```c
__int64 __fastcall CFilterGraph::CreateFilter(CFilterGraph *this, const struct _GUID *a2, struct IBaseFilter **a3)
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
  unsigned int Filter; // eax
  unsigned int v18; // ebx
  int v20; // [rsp+20h] [rbp-68h] BYREF
  double Time; // [rsp+28h] [rbp-60h]
  _QWORD v22[11]; // [rsp+30h] [rbp-58h] BYREF

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
    Filter = CoCreateFilter(a2, a3);
  }
  else
  {
    v22[1] = 0;
    v22[2] = 1;
    v22[0] = a2;
    Filter = CFilterGraph::CreateFilterHelper(this, (const struct AwmCreateFilterArg *)v22, a3);
  }
  v18 = Filter;
  CAutoTimer::~CAutoTimer((CAutoTimer *)&v20);
  return v18;
}

```

## disassembly

```asm
0x18002b030  push    rbx
0x18002b032  push    rbp
0x18002b033  push    rsi
0x18002b034  push    rdi
0x18002b035  push    r12
0x18002b037  push    r14
0x18002b039  sub     rsp, 58h
0x18002b03d  mov     r14, rcx
0x18002b040  lea     r12, CriticalSection
0x18002b047  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002b04b  mov     rcx, r12; lpCriticalSection
0x18002b04e  mov     rsi, r8
0x18002b051  mov     [rsp+88h+var_68], edi
0x18002b055  mov     rbp, rdx
0x18002b058  call    cs:__imp_EnterCriticalSection
0x18002b05f  nop     dword ptr [rax+rax+00h]
0x18002b064  xor     ebx, ebx
0x18002b066  cmp     ebx, cs:dword_1801A1C98
0x18002b06c  jge     short loc_18002B0AE
0x18002b06e  mov     rax, cs:?g_Stats@@3VCStats@@A; CStats g_Stats
0x18002b075  lea     rcx, aCreateFilter; "Create Filter"
0x18002b07c  movsxd  rdx, ebx
0x18002b07f  mov     rdx, [rax+rdx*8]
0x18002b083  mov     rdx, [rdx]; lpString2
0x18002b086  call    cs:__imp_lstrcmpiW
0x18002b08d  nop     dword ptr [rax+rax+00h]
0x18002b092  test    eax, eax
0x18002b094  jz      short loc_18002B09A
0x18002b096  inc     ebx
0x18002b098  jmp     short loc_18002B066
0x18002b09a  mov     rcx, r12; lpCriticalSection
0x18002b09d  call    cs:__imp_LeaveCriticalSection
0x18002b0a4  nop     dword ptr [rax+rax+00h]
0x18002b0a9  jmp     loc_18002B17E
0x18002b0ae  mov     ecx, 40h ; '@'; Size
0x18002b0b3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b0b8  test    rax, rax
0x18002b0bb  jz      loc_18002B19B
0x18002b0c1  lea     rdx, aCreateFilter; "Create Filter"
0x18002b0c8  mov     rcx, rax; this
0x18002b0cb  call    ??0CStat@@QEAA@PEBG@Z; CStat::CStat(ushort const *)
0x18002b0d0  mov     rbx, rax
0x18002b0d3  test    rax, rax
0x18002b0d6  jz      loc_18002B19B
0x18002b0dc  cmp     qword ptr [rax], 0
0x18002b0e0  jz      loc_18002B193
0x18002b0e6  mov     ecx, cs:dword_1801A1C98
0x18002b0ec  mov     r8d, 10h
0x18002b0f2  mov     eax, ecx
0x18002b0f4  cdq
0x18002b0f5  idiv    r8d
0x18002b0f8  test    edx, edx
0x18002b0fa  jnz     short loc_18002B151
0x18002b0fc  lea     eax, [rcx+10h]
0x18002b0ff  movsxd  rcx, eax
0x18002b102  lea     eax, [rdx+8]
0x18002b105  mul     rcx
0x18002b108  cmovb   rax, rdi
0x18002b10c  mov     rcx, rax; unsigned __int64
0x18002b10f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002b114  mov     rdi, rax
0x18002b117  test    rax, rax
0x18002b11a  jz      short loc_18002B193
0x18002b11c  movsxd  r8, cs:dword_1801A1C98
0x18002b123  mov     rcx, rax; void *
0x18002b126  mov     rdx, cs:?g_Stats@@3VCStats@@A; Src
0x18002b12d  shl     r8, 3; Size
0x18002b131  call    memcpy_0
0x18002b136  mov     rcx, cs:?g_Stats@@3VCStats@@A; Block
0x18002b13d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002b142  mov     ecx, cs:dword_1801A1C98
0x18002b148  mov     cs:?g_Stats@@3VCStats@@A, rdi; CStats g_Stats
0x18002b14f  jmp     short loc_18002B158
0x18002b151  mov     rdi, cs:?g_Stats@@3VCStats@@A; CStats g_Stats
0x18002b158  movsxd  rax, ecx
0x18002b15b  mov     rcx, r12; lpCriticalSection
0x18002b15e  mov     [rdi+rax*8], rbx
0x18002b162  mov     ebx, cs:dword_1801A1C98
0x18002b168  inc     ebx
0x18002b16a  mov     cs:dword_1801A1C98, ebx
0x18002b170  call    cs:__imp_LeaveCriticalSection
0x18002b177  nop     dword ptr [rax+rax+00h]
0x18002b17c  dec     ebx
0x18002b17e  mov     [rsp+88h+var_68], ebx
0x18002b182  test    ebx, ebx
0x18002b184  js      short loc_18002B1AA
0x18002b186  call    ?GetTime@CStats@@QEAANXZ; CStats::GetTime(void)
0x18002b18b  movsd   [rsp+88h+var_60], xmm0
0x18002b191  jmp     short loc_18002B1AA
0x18002b193  mov     rcx, rbx; this
0x18002b196  call    ??_GCStat@@QEAAPEAXI@Z; CStat::`scalar deleting destructor'(uint)
0x18002b19b  mov     rcx, r12; lpCriticalSection
0x18002b19e  call    cs:__imp_LeaveCriticalSection
0x18002b1a5  nop     dword ptr [rax+rax+00h]
0x18002b1aa  mov     ebx, [r14+1E4h]
0x18002b1b1  call    cs:__imp_GetCurrentThreadId
0x18002b1b8  nop     dword ptr [rax+rax+00h]
0x18002b1bd  cmp     eax, ebx
0x18002b1bf  jnz     short loc_18002B1CE
0x18002b1c1  mov     rdx, rsi
0x18002b1c4  mov     rcx, rbp
0x18002b1c7  call    CoCreateFilter
0x18002b1cc  jmp     short loc_18002B1F5
0x18002b1ce  mov     r8, rsi; struct IBaseFilter **
0x18002b1d1  mov     [rsp+88h+var_50], 0
0x18002b1da  lea     rdx, [rsp+88h+var_58]; struct AwmCreateFilterArg *
0x18002b1df  mov     [rsp+88h+var_48], 1
0x18002b1e8  mov     rcx, r14; this
0x18002b1eb  mov     [rsp+88h+var_58], rbp
0x18002b1f0  call    ?CreateFilterHelper@CFilterGraph@@AEAAJPEBUAwmCreateFilterArg@@PEAPEAUIBaseFilter@@@Z; CFilterGraph::CreateFilterHelper(AwmCreateFilterArg const *,IBaseFilter * *)
0x18002b1f5  lea     rcx, [rsp+88h+var_68]; this
0x18002b1fa  mov     ebx, eax
0x18002b1fc  call    ??1CAutoTimer@@QEAA@XZ; CAutoTimer::~CAutoTimer(void)
0x18002b201  mov     eax, ebx
0x18002b203  add     rsp, 58h
0x18002b207  pop     r14
0x18002b209  pop     r12
0x18002b20b  pop     rdi
0x18002b20c  pop     rsi
0x18002b20d  pop     rbp
0x18002b20e  pop     rbx
0x18002b20f  retn
```
