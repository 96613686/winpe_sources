# CFilterGraph::AddSourceFilterInternal(ushort const *,ushort const *,IBaseFilter * *,int &)

- ea: `0x180008820`
- end: `0x180008e36`
- name: `?AddSourceFilterInternal@CFilterGraph@@AEAAJPEBG0PEAPEAUIBaseFilter@@AEAH@Z`
- size: `1558`
- prototype: `__int64 __usercall@<rax>(CFilterGraph *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, struct IBaseFilter **@<r9>, int *)`
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180060730`
- `0x18006c9a0`

## callees

- `0x180002c80`
- `0x180006cc0`
- `0x180007930`
- `0x180007a2c`
- `0x180007a9c`
- `0x180008820`
- `0x180009b04`
- `0x18001476c`
- `0x180014880`
- `0x18002b218`
- `0x18002f03c`
- `0x180038458`
- `0x180038498`
- `0x1800384a4`
- `0x1800388a0`
- `0x18006a4fc`
- `0x18006a54c`
- `0x18015bb8c`
- `0x18015bb98`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180008a5e`
- `KERNEL32!LeaveCriticalSection` at `0x180008afe`
- `KERNEL32!LeaveCriticalSection` at `0x180008b6b`
- `KERNEL32!LeaveCriticalSection` at `0x180008bc9`
- `KERNEL32!LeaveCriticalSection` at `0x180008a5e`
- `KERNEL32!LeaveCriticalSection` at `0x180008afe`
- `KERNEL32!LeaveCriticalSection` at `0x180008b6b`
- `KERNEL32!LeaveCriticalSection` at `0x180008bc9`
- `KERNEL32!EnterCriticalSection` at `0x180008a15`
- `KERNEL32!EnterCriticalSection` at `0x180008a15`
- `KERNEL32!GetCurrentThreadId` at `0x180008bdb`
- `KERNEL32!GetCurrentThreadId` at `0x180008bdb`
- `KERNEL32!QueryPerformanceCounter` at `0x180008b94`
- `KERNEL32!QueryPerformanceCounter` at `0x180008b94`
- `KERNEL32!lstrcmpiW` at `0x180008a43`
- `KERNEL32!lstrcmpiW` at `0x180008a43`
- `ole32!CoTaskMemFree` at `0x180008e07`
- `ole32!CoTaskMemFree` at `0x180008e07`

## string_xrefs

- `0x180008a32`: `Create Filter`
- `0x180008a82`: `Create Filter`

## pseudocode

```c
__int64 __fastcall CFilterGraph::AddSourceFilterInternal(
        CFilterGraph *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IBaseFilter **a4,
        int *a5)
{
  unsigned __int16 *i; // r14
  signed int MediaTypeFile; // eax
  unsigned int v10; // edi
  unsigned int v11; // ebx
  int j; // ebx
  CStat *v14; // rax
  CStat *v15; // rax
  unsigned int v16; // edx
  CStat *v17; // rbx
  signed int v18; // eax
  void *v19; // rax
  unsigned int v20; // edx
  void *v21; // rdi
  unsigned int v22; // ebx
  int v23; // ebx
  int v24; // eax
  int v25; // ebx
  int v26; // eax
  int v27; // ebx
  void (*Release)(void); // rax
  int v29; // eax
  struct _AMMediaType *v30; // r8
  bool v31; // zf
  struct IBaseFilter *v32; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v33; // [rsp+28h] [rbp-D8h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+30h] [rbp-D0h] BYREF
  int v35; // [rsp+38h] [rbp-C8h] BYREF
  double v36; // [rsp+40h] [rbp-C0h]
  _QWORD v37[3]; // [rsp+48h] [rbp-B8h] BYREF
  GUID Buf1; // [rsp+60h] [rbp-A0h] BYREF
  struct _GUID v39; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID v40; // [rsp+80h] [rbp-80h] BYREF
  struct _AMMediaType v41; // [rsp+90h] [rbp-70h] BYREF

  v32 = 0;
  i = a2;
  *a5 = 0;
  if ( ((*a2 - 70) & 0xFFDF) == 0
    && ((a2[1] - 73) & 0xFFDF) == 0
    && ((a2[2] - 76) & 0xFFDF) == 0
    && ((a2[3] - 69) & 0xFFDF) == 0
    && a2[4] == 58 )
  {
    for ( i = a2 + 5; *i == 47; ++i )
      ;
  }
  memset(&v41.bFixedSizeSamples, 0, 56);
  v41.lSampleSize = 1;
  v41.bFixedSizeSamples = 1;
  Buf1 = 0;
  v39 = 0;
  v40 = 0;
  memset(&v41, 0, 32);
  MediaTypeFile = GetMediaTypeFile(i, &Buf1, &v39, &v40);
  v10 = -2147220928;
  v11 = MediaTypeFile;
  if ( MediaTypeFile == -2147220928 )
  {
    CFilterGraph::Log(this, 2500);
    *a5 = 1;
    v40 = CLSID_AVIDoc;
  }
  else
  {
    if ( MediaTypeFile < 0 )
    {
      if ( (unsigned int)(MediaTypeFile + 2147024894) <= 1 || MediaTypeFile == -2147024773 )
        v11 = -2147220970;
      CFilterGraph::Log(this, 2501, v11);
      FreeMediaType(&v41);
      return v11;
    }
    if ( !memcmp_0(&Buf1, &MEDIATYPE_Stream, 0x10u) && !memcmp_0(&v39, &GUID_NULL, 0x10u) )
      *a5 = 1;
    v41.majortype = Buf1;
    v41.subtype = v39;
    CFilterGraph::Log(this, 2502);
  }
  CFilterGraph::Log(this, 2503, v40.Data1);
  v35 = -1;
  EnterCriticalSection(&CriticalSection);
  for ( j = 0; ; ++j )
  {
    if ( j >= (int)dword_1801A1C98 )
    {
      v14 = (CStat *)operator new(0x40u);
      if ( v14 )
      {
        v15 = CStat::CStat(v14, L"Create Filter");
        v17 = v15;
        if ( v15 )
        {
          if ( *(_QWORD *)v15 )
          {
            v18 = dword_1801A1C98;
            if ( (int)dword_1801A1C98 % 16 )
            {
              v21 = g_Stats;
            }
            else
            {
              v19 = operator new[](saturated_mul((int)(dword_1801A1C98 + 16), 8u));
              v21 = v19;
              if ( !v19 )
              {
                CStat::`scalar deleting destructor'(v17, v20);
                LeaveCriticalSection(&CriticalSection);
                v10 = -2147220928;
                goto LABEL_37;
              }
              memcpy_0(v19, g_Stats, 8LL * (int)dword_1801A1C98);
              operator delete(g_Stats);
              v18 = dword_1801A1C98;
              g_Stats = v21;
            }
            *((_QWORD *)v21 + v18) = v17;
            v22 = ++dword_1801A1C98;
            LeaveCriticalSection(&CriticalSection);
            j = v22 - 1;
            v10 = -2147220928;
            goto LABEL_33;
          }
          CStat::`scalar deleting destructor'(v15, v16);
        }
      }
      LeaveCriticalSection(&CriticalSection);
      goto LABEL_37;
    }
    if ( !lstrcmpiW(L"Create Filter", **((LPCWSTR **)g_Stats + j)) )
      break;
  }
  LeaveCriticalSection(&CriticalSection);
LABEL_33:
  v35 = j;
  if ( j >= 0 )
  {
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    v36 = (double)(int)PerformanceCount.LowPart * *(double *)&qword_1801A1CC8;
  }
LABEL_37:
  v23 = *((_DWORD *)this + 121);
  if ( GetCurrentThreadId() == v23 )
  {
    v24 = CoCreateFilter(&v40, &v32);
  }
  else
  {
    v37[2] = 1;
    v37[1] = 0;
    v37[0] = &v40;
    v24 = CFilterGraph::CreateFilterHelper(this, (const struct AwmCreateFilterArg *)v37, &v32);
  }
  v25 = v24;
  CAutoTimer::~CAutoTimer((CAutoTimer *)&v35);
  if ( v25 < 0 )
  {
    CFilterGraph::Log(this, 2504, (unsigned int)v25);
    if ( !*a5 )
    {
      v10 = v25;
      if ( v25 != -2147221008 )
        v10 = -2147220927;
    }
    FreeMediaType(&v41);
    return v10;
  }
  v33 = 0;
  v26 = ((__int64 (__fastcall *)(struct IBaseFilter *, GUID *, __int64 *))v32->lpVtbl->QueryInterface)(
          v32,
          &IID_IFileSourceFilter,
          &v33);
  v27 = v26;
  if ( v26 < 0 )
  {
    CFilterGraph::Log(this, 2505, (unsigned int)v26);
    Release = (void (*)(void))v32->lpVtbl->Release;
LABEL_47:
    Release();
LABEL_48:
    FreeMediaType(&v41);
    return (unsigned int)v27;
  }
  if ( !a3 )
    a3 = i;
  v29 = CFilterGraph::AddFilterInternal(this, v32, a3, 0);
  v27 = v29;
  if ( v29 < 0 )
  {
    CFilterGraph::Log(this, 2510, (unsigned int)v29);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    Release = (void (*)(void))v32->lpVtbl->Release;
    goto LABEL_47;
  }
  if ( !memcmp_0(&v41, &GUID_NULL, 0x10u) )
    v30 = 0;
  else
    v30 = &v41;
  v27 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, struct _AMMediaType *))(*(_QWORD *)v33 + 24LL))(
          v33,
          i,
          v30);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  if ( v27 < 0 )
  {
    CFilterGraph::RemoveFilterInternal(this, v32, 0);
    ((void (__fastcall *)(struct IBaseFilter *))v32->lpVtbl->Release)(v32);
    CFilterGraph::Log(this, 2507, (unsigned int)v27);
    if ( *a5 && (v27 & 0x1FFF0000) == 0x40000 )
      v27 = -2147220928;
    goto LABEL_48;
  }
  CFilterGraph::Log(this, 2508);
  ++*((_DWORD *)this + 101);
  ++*((_DWORD *)this + 96);
  CFilterGraph::AttemptDeferredConnections(this);
  CReconnectList::Passive((CFilterGraph *)((char *)this + 384));
  *a4 = v32;
  CFilterGraph::Log(this, 2509);
  v31 = v41.cbFormat == 0;
  *((_DWORD *)this + 102) = 1;
  if ( !v31 )
    CoTaskMemFree(v41.pbFormat);
  return 0;
}

```

## disassembly

```asm
0x180008820  push    rbp
0x180008822  push    rbx
0x180008823  push    rsi
0x180008824  push    rdi
0x180008825  push    r12
0x180008827  push    r13
0x180008829  push    r14
0x18000882b  push    r15
0x18000882d  lea     rbp, [rsp-8]
0x180008832  sub     rsp, 108h
0x180008839  mov     rax, cs:__security_cookie
0x180008840  xor     rax, rsp
0x180008843  mov     [rbp+40h+var_50], rax
0x180008847  mov     r12, [rbp+40h+arg_20]
0x18000884b  xor     eax, eax
0x18000884d  mov     [rsp+140h+var_120], rax
0x180008852  mov     rsi, rcx
0x180008855  mov     ecx, 0FFDFh
0x18000885a  mov     r13, r9
0x18000885d  mov     r15, r8
0x180008860  mov     r14, rdx
0x180008863  mov     [r12], eax
0x180008867  movzx   eax, word ptr [rdx]
0x18000886a  sub     ax, 46h ; 'F'
0x18000886e  test    cx, ax
0x180008871  jnz     short loc_1800088B7
0x180008873  movzx   eax, word ptr [rdx+2]
0x180008877  sub     ax, 49h ; 'I'
0x18000887b  test    cx, ax
0x18000887e  jnz     short loc_1800088B7
0x180008880  movzx   eax, word ptr [rdx+4]
0x180008884  sub     ax, 4Ch ; 'L'
0x180008888  test    cx, ax
0x18000888b  jnz     short loc_1800088B7
0x18000888d  movzx   eax, word ptr [rdx+6]
0x180008891  sub     ax, 45h ; 'E'
0x180008895  test    cx, ax
0x180008898  jnz     short loc_1800088B7
0x18000889a  cmp     word ptr [rdx+8], 3Ah ; ':'
0x18000889f  jnz     short loc_1800088B7
0x1800088a1  add     r14, 0Ah
0x1800088a5  cmp     word ptr [r14], 2Fh ; '/'
0x1800088aa  jnz     short loc_1800088B7
0x1800088ac  add     r14, 2
0x1800088b0  cmp     word ptr [r14], 2Fh ; '/'
0x1800088b5  jz      short loc_1800088AC
0x1800088b7  xorps   xmm1, xmm1
0x1800088ba  lea     r9, [rbp+40h+var_C0]; struct _GUID *
0x1800088be  xorps   xmm0, xmm0
0x1800088c1  lea     r8, [rsp+140h+var_D0]; struct _GUID *
0x1800088c6  movups  xmmword ptr [rbp+40h+var_B0.bFixedSizeSamples], xmm1
0x1800088ca  xor     eax, eax
0x1800088cc  mov     [rbp+40h+var_B0.lSampleSize], 1
0x1800088d3  lea     rdx, [rsp+140h+Buf1]; struct _GUID *
0x1800088d8  mov     [rbp+40h+var_B0.bFixedSizeSamples], 1
0x1800088df  mov     rcx, r14; unsigned __int16 *
0x1800088e2  mov     [rbp+40h+var_B0.pbFormat], rax
0x1800088e6  movups  [rsp+140h+Buf1], xmm0
0x1800088eb  movups  xmmword ptr [rsp+140h+var_D0.Data1], xmm1
0x1800088f0  movups  xmmword ptr [rbp+40h+var_C0.Data1], xmm0
0x1800088f4  movups  xmmword ptr [rbp+40h+var_B0.majortype.Data1], xmm1
0x1800088f8  movups  xmmword ptr [rbp+40h+var_B0.subtype.Data1], xmm1
0x1800088fc  movups  xmmword ptr [rbp+40h+var_B0.formattype.Data2], xmm1
0x180008900  movups  xmmword ptr [rbp+40h+var_B0.pUnk], xmm1
0x180008904  call    GetMediaTypeFile
0x180008909  mov     edi, 80040240h
0x18000890e  mov     ebx, eax
0x180008910  cmp     eax, edi
0x180008912  jnz     short loc_180008939
0x180008914  mov     edx, 9C4h; int
0x180008919  mov     rcx, rsi; this
0x18000891c  call    ?Log@CFilterGraph@@AEAAXHZZ; CFilterGraph::Log(int,...)
0x180008921  movups  xmm0, xmmword ptr cs:CLSID_AVIDoc.Data1
0x180008928  mov     dword ptr [r12], 1
0x180008930  movups  xmmword ptr [rbp+40h+var_C0.Data1], xmm0
0x180008934  jmp     loc_1800089F5
0x180008939  test    ebx, ebx
0x18000893b  jns     short loc_180008974
0x18000893d  add     eax, 7FF8FFFEh
0x180008942  cmp     eax, 1
0x180008945  jbe     short loc_18000894F
0x180008947  cmp     ebx, 8007007Bh
0x18000894d  jnz     short loc_180008954
0x18000894f  mov     ebx, 80040216h
0x180008954  mov     r8d, ebx
0x180008957  mov     edx, 9C5h; int
0x18000895c  mov     rcx, rsi; this
0x18000895f  call    ?Log@CFilterGraph@@AEAAXHZZ; CFilterGraph::Log(int,...)
0x180008964  lea     rcx, [rbp+40h+var_B0]; struct _AMMediaType *
0x180008968  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x18000896d  mov     eax, ebx
0x18000896f  jmp     loc_180008E15
0x180008974  mov     r8d, 10h; Size
0x18000897a  lea     rdx, MEDIATYPE_Stream; Buf2
0x180008981  lea     rcx, [rsp+140h+Buf1]; Buf1
0x180008986  call    memcmp_0
0x18000898b  test    eax, eax
0x18000898d  jnz     short loc_1800089B2
0x18000898f  mov     r8d, 10h; Size
0x180008995  lea     rdx, GUID_NULL; Buf2
0x18000899c  lea     rcx, [rsp+140h+var_D0]; Buf1
0x1800089a1  call    memcmp_0
0x1800089a6  test    eax, eax
0x1800089a8  jnz     short loc_1800089B2
0x1800089aa  mov     dword ptr [r12], 1
0x1800089b2  movsd   xmm0, qword ptr [rsp+140h+Buf1+4]
0x1800089b8  mov     edx, 9C6h; int
0x1800089bd  mov     eax, dword ptr [rsp+140h+Buf1+0Ch]
0x1800089c1  mov     rcx, rsi; this
0x1800089c4  mov     r8d, dword ptr [rsp+140h+Buf1]
0x1800089c9  mov     r9d, [rsp+140h+var_D0.Data1]
0x1800089ce  movsd   qword ptr [rbp+40h+var_B0.majortype.Data2], xmm0
0x1800089d3  movsd   xmm0, qword ptr [rsp+140h+var_D0.Data2]
0x1800089d9  mov     dword ptr [rbp+40h+var_B0.majortype.Data4+4], eax
0x1800089dc  mov     eax, dword ptr [rsp+140h+var_D0.Data4+4]
0x1800089e0  movsd   qword ptr [rbp+40h+var_B0.subtype.Data2], xmm0
0x1800089e5  mov     [rbp+40h+var_B0.majortype.Data1], r8d
0x1800089e9  mov     [rbp+40h+var_B0.subtype.Data1], r9d
0x1800089ed  mov     dword ptr [rbp+40h+var_B0.subtype.Data4+4], eax
0x1800089f0  call    ?Log@CFilterGraph@@AEAAXHZZ; CFilterGraph::Log(int,...)
0x1800089f5  mov     r8d, [rbp+40h+var_C0.Data1]
0x1800089f9  mov     edx, 9C7h; int
0x1800089fe  mov     rcx, rsi; this
0x180008a01  call    ?Log@CFilterGraph@@AEAAXHZZ; CFilterGraph::Log(int,...)
0x180008a06  lea     rcx, CriticalSection; lpCriticalSection
0x180008a0d  mov     [rsp+140h+var_108], 0FFFFFFFFh
0x180008a15  call    cs:__imp_EnterCriticalSection
0x180008a1c  nop     dword ptr [rax+rax+00h]
0x180008a21  xor     ebx, ebx
0x180008a23  cmp     ebx, cs:dword_1801A1C98
0x180008a29  jge     short loc_180008A6F
0x180008a2b  mov     rax, cs:?g_Stats@@3VCStats@@A; CStats g_Stats
0x180008a32  lea     rcx, aCreateFilter; "Create Filter"
0x180008a39  movsxd  rdx, ebx
0x180008a3c  mov     rdx, [rax+rdx*8]
0x180008a40  mov     rdx, [rdx]; lpString2
0x180008a43  call    cs:__imp_lstrcmpiW
0x180008a4a  nop     dword ptr [rax+rax+00h]
0x180008a4f  test    eax, eax
0x180008a51  jz      short loc_180008A57
0x180008a53  inc     ebx
0x180008a55  jmp     short loc_180008A23
0x180008a57  lea     rcx, CriticalSection; lpCriticalSection
0x180008a5e  call    cs:__imp_LeaveCriticalSection
0x180008a65  nop     dword ptr [rax+rax+00h]
0x180008a6a  jmp     loc_180008B7E
0x180008a6f  mov     ecx, 40h ; '@'; Size
0x180008a74  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008a79  test    rax, rax
0x180008a7c  jz      loc_180008BC2
0x180008a82  lea     rdx, aCreateFilter; "Create Filter"
0x180008a89  mov     rcx, rax; this
0x180008a8c  call    ??0CStat@@QEAA@PEBG@Z; CStat::CStat(ushort const *)
0x180008a91  mov     rbx, rax
0x180008a94  test    rax, rax
0x180008a97  jz      loc_180008BC2
0x180008a9d  cmp     qword ptr [rax], 0
0x180008aa1  jz      loc_180008BBA
0x180008aa7  mov     eax, cs:dword_1801A1C98
0x180008aad  mov     ecx, eax
0x180008aaf  and     ecx, 8000000Fh
0x180008ab5  jge     short loc_180008ABE
0x180008ab7  dec     ecx
0x180008ab9  or      ecx, 0FFFFFFF0h
0x180008abc  inc     ecx
0x180008abe  test    ecx, ecx
0x180008ac0  jnz     loc_180008B49
0x180008ac6  add     eax, 10h
0x180008ac9  movsxd  rcx, eax
0x180008acc  mov     eax, 8
0x180008ad1  mul     rcx
0x180008ad4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180008adb  cmovb   rax, rcx
0x180008adf  mov     rcx, rax; unsigned __int64
0x180008ae2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180008ae7  mov     rdi, rax
0x180008aea  test    rax, rax
0x180008aed  jnz     short loc_180008B14
0x180008aef  mov     rcx, rbx; this
0x180008af2  call    ??_GCStat@@QEAAPEAXI@Z; CStat::`scalar deleting destructor'(uint)
0x180008af7  lea     rcx, CriticalSection; lpCriticalSection
0x180008afe  call    cs:__imp_LeaveCriticalSection
0x180008b05  nop     dword ptr [rax+rax+00h]
0x180008b0a  mov     edi, 80040240h
0x180008b0f  jmp     loc_180008BD5
0x180008b14  movsxd  r8, cs:dword_1801A1C98
0x180008b1b  mov     rcx, rdi; void *
0x180008b1e  mov     rdx, cs:?g_Stats@@3VCStats@@A; Src
0x180008b25  shl     r8, 3; Size
0x180008b29  call    memcpy_0
0x180008b2e  mov     rcx, cs:?g_Stats@@3VCStats@@A; Block
0x180008b35  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008b3a  mov     eax, cs:dword_1801A1C98
0x180008b40  mov     cs:?g_Stats@@3VCStats@@A, rdi; CStats g_Stats
0x180008b47  jmp     short loc_180008B50
0x180008b49  mov     rdi, cs:?g_Stats@@3VCStats@@A; CStats g_Stats
0x180008b50  cdqe
0x180008b52  lea     rcx, CriticalSection; lpCriticalSection
0x180008b59  mov     [rdi+rax*8], rbx
0x180008b5d  mov     ebx, cs:dword_1801A1C98
0x180008b63  inc     ebx
0x180008b65  mov     cs:dword_1801A1C98, ebx
0x180008b6b  call    cs:__imp_LeaveCriticalSection
0x180008b72  nop     dword ptr [rax+rax+00h]
0x180008b77  dec     ebx
0x180008b79  mov     edi, 80040240h
0x180008b7e  mov     [rsp+140h+var_108], ebx
0x180008b82  test    ebx, ebx
0x180008b84  js      short loc_180008BD5
0x180008b86  lea     rcx, [rsp+140h+PerformanceCount]; lpPerformanceCount
0x180008b8b  mov     qword ptr [rsp+140h+PerformanceCount], 0
0x180008b94  call    cs:__imp_QueryPerformanceCounter
0x180008b9b  nop     dword ptr [rax+rax+00h]
0x180008ba0  xorps   xmm0, xmm0
0x180008ba3  cvtsi2sd xmm0, qword ptr [rsp+140h+PerformanceCount]
0x180008baa  mulsd   xmm0, cs:qword_1801A1CC8
0x180008bb2  movsd   [rsp+140h+var_100], xmm0
0x180008bb8  jmp     short loc_180008BD5
0x180008bba  mov     rcx, rbx; this
0x180008bbd  call    ??_GCStat@@QEAAPEAXI@Z; CStat::`scalar deleting destructor'(uint)
0x180008bc2  lea     rcx, CriticalSection; lpCriticalSection
0x180008bc9  call    cs:__imp_LeaveCriticalSection
0x180008bd0  nop     dword ptr [rax+rax+00h]
0x180008bd5  mov     ebx, [rsi+1E4h]
0x180008bdb  call    cs:__imp_GetCurrentThreadId
0x180008be2  nop     dword ptr [rax+rax+00h]
0x180008be7  cmp     eax, ebx
0x180008be9  jnz     short loc_180008BFB
0x180008beb  lea     rdx, [rsp+140h+var_120]
0x180008bf0  lea     rcx, [rbp+40h+var_C0]
0x180008bf4  call    CoCreateFilter
0x180008bf9  jmp     short loc_180008C26
0x180008bfb  xor     eax, eax
0x180008bfd  mov     [rsp+140h+var_E8], 1
0x180008c06  mov     [rsp+140h+var_F0], rax
0x180008c0b  lea     r8, [rsp+140h+var_120]; struct IBaseFilter **
0x180008c10  lea     rax, [rbp+40h+var_C0]
0x180008c14  mov     rcx, rsi; this
0x180008c17  lea     rdx, [rsp+140h+var_F8]; struct AwmCreateFilterArg *
0x180008c1c  mov     [rsp+140h+var_F8], rax
0x180008c21  call    ?CreateFilterHelper@CFilterGraph@@AEAAJPEBUAwmCreateFilterArg@@PEAPEAUIBaseFilter@@@Z; CFilterGraph::CreateFilterHelper(AwmCreateFilterArg const *,IBaseFilter * *)
0x180008c26  lea     rcx, [rsp+140h+var_108]; this
0x180008c2b  mov     ebx, eax
0x180008c2d  call    ??1CAutoTimer@@QEAA@XZ; CAutoTimer::~CAutoTimer(void)
0x180008c32  test    ebx, ebx
0x180008c34  jns     short loc_180008C6D
0x180008c36  mov     r8d, ebx
0x180008c39  mov     edx, 9C8h; int
0x180008c3e  mov     rcx, rsi; this
0x180008c41  call    ?Log@CFilterGraph@@AEAAXHZZ; CFilterGraph::Log(int,...)
0x180008c46  cmp     dword ptr [r12], 0
0x180008c4b  jnz     short loc_180008C5D
0x180008c4d  cmp     ebx, 800401F0h
0x180008c53  mov     edi, ebx
0x180008c55  mov     eax, 80040241h
0x180008c5a  cmovnz  edi, eax
0x180008c5d  lea     rcx, [rbp+40h+var_B0]; struct _AMMediaType *
0x180008c61  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x180008c66  mov     eax, edi
0x180008c68  jmp     loc_180008E15
0x180008c6d  mov     rcx, [rsp+140h+var_120]
0x180008c72  lea     r8, [rsp+140h+var_118]
0x180008c77  mov     [rsp+140h+var_118], 0
0x180008c80  lea     rdx, IID_IFileSourceFilter
0x180008c87  mov     rax, [rcx]
0x180008c8a  mov     rax, [rax]
0x180008c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c92  mov     ebx, eax
0x180008c94  mov     rcx, rsi; this
0x180008c97  test    eax, eax
0x180008c99  jns     short loc_180008CC9
0x180008c9b  mov     r8d, eax
0x180008c9e  mov     edx, 9C9h; int
0x180008ca3  call    ?Log@CFilterGraph@@AEAAXHZZ; CFilterGraph::Log(int,...)
0x180008ca8  mov     rcx, [rsp+140h+var_120]
0x180008cad  mov     rdx, [rcx]
0x180008cb0  mov     rax, [rdx+10h]
0x180008cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cb9  lea     rcx, [rbp+40h+var_B0]; struct _AMMediaType *
0x180008cbd  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x180008cc2  mov     eax, ebx
0x180008cc4  jmp     loc_180008E15
0x180008cc9  mov     rdx, [rsp+140h+var_120]; struct IBaseFilter *
0x180008cce  test    r15, r15
0x180008cd1  cmovz   r15, r14
0x180008cd5  xor     r9d, r9d; bool
0x180008cd8  mov     r8, r15; unsigned __int16 *
0x180008cdb  call    ?AddFilterInternal@CFilterGraph@@QEAAJPEAUIBaseFilter@@PEBG_N@Z; CFilterGraph::AddFilterInternal(IBaseFilter *,ushort const *,bool)
0x180008ce0  mov     ebx, eax
0x180008ce2  test    eax, eax
0x180008ce4  jns     short loc_180008D15
0x180008ce6  mov     r8d, eax
0x180008ce9  mov     edx, 9CEh; int
0x180008cee  mov     rcx, rsi; this
0x180008cf1  call    ?Log@CFilterGraph@@AEAAXHZZ; CFilterGraph::Log(int,...)
0x180008cf6  mov     rcx, [rsp+140h+var_118]
0x180008cfb  mov     rdx, [rcx]
0x180008cfe  mov     rax, [rdx+10h]
0x180008d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d07  mov     rcx, [rsp+140h+var_120]
  ... truncated ...
```
