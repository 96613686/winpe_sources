# CImportExportContext::~CImportExportContext(void)

- ea: `0x180059608`
- end: `0x18005981a`
- name: `??1CImportExportContext@@IEAA@XZ`
- size: `530`
- prototype: `void __fastcall(CImportExportContext *this, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18005a4c0`

## callees

- `0x1800095bc`
- `0x180033470`
- `0x180059608`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059671`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059671`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059697`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059697`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800597b9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800597b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005979e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005979e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800597ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800597ac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800597dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800597dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800597cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800597cb`
- `RPCRT4!NdrClientCall3` at `0x1800596d7`
- `RPCRT4!NdrClientCall3` at `0x1800596d7`

## pseudocode

```c
void __fastcall CImportExportContext::~CImportExportContext(CImportExportContext *this, int a2, int a3)
{
  char *v4; // rdi
  __int64 v5; // rdx
  char **v6; // rax
  __int64 v7; // rcx
  int Pointer; // eax
  int v9; // edx
  int v10; // r8d
  void *v11; // rdi
  HANDLE ProcessHeap; // rax
  int v13; // edx
  int v14; // r8d
  void *v15; // rcx
  struct _TP_WAIT *v16; // rcx
  int v17; // [rsp+28h] [rbp-30h]

  *(_QWORD *)this = &CImportExportContext::`vftable';
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sq(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      a2,
      a3,
      12,
      &WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids,
      v17,
      (char)this);
  v4 = (char *)this + 208;
  if ( *((_QWORD *)this + 26) )
  {
    EnterCriticalSection(&g_ImportExportList);
    v5 = *(_QWORD *)v4;
    if ( *(char **)(*(_QWORD *)v4 + 8LL) != v4 || (v6 = (char **)*((_QWORD *)this + 27), *v6 != v4) )
      __fastfail(3u);
    *v6 = (char *)v5;
    *(_QWORD *)(v5 + 8) = v6;
    LeaveCriticalSection(&g_ImportExportList);
  }
  v7 = *((_QWORD *)this + 11);
  if ( *((_DWORD *)this + 11) )
  {
    if ( v7 )
    {
      Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180083280, 0x20u, 0).Pointer;
      if ( Pointer < 0 && *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_SqD(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v9,
          v10,
          13,
          &WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids,
          *((_QWORD *)this + 6),
          (char)this,
          Pointer);
    }
  }
  else if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  v11 = (void *)*((_QWORD *)this + 6);
  if ( v11 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v11);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  v15 = (void *)*((_QWORD *)this + 34);
  if ( v15 )
    CloseHandle(v15);
  v16 = (struct _TP_WAIT *)*((_QWORD *)this + 35);
  if ( v16 )
    CloseThreadpoolWait(v16);
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sq(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v13,
      v14,
      15,
      &WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids,
      v17,
      (char)this);
}

```

## disassembly

```asm
0x180059608  mov     r11, rsp
0x18005960b  mov     [r11+18h], rbx
0x18005960f  mov     [r11+8], rcx
0x180059613  push    rsi
0x180059614  push    rdi
0x180059615  push    r14
0x180059617  sub     rsp, 40h
0x18005961b  mov     rbx, rcx
0x18005961e  lea     rax, ??_7CImportExportContext@@6B@; const CImportExportContext::`vftable'
0x180059625  mov     [rcx], rax
0x180059628  lea     r14, WPP_RECORDER_INITIALIZED
0x18005962f  lea     rsi, WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids
0x180059636  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005963d  jz      short loc_18005965D
0x18005963f  mov     r9d, 0Ch; int
0x180059645  mov     [r11-28h], rcx
0x180059649  mov     [r11-38h], rsi
0x18005964d  mov     rcx, cs:WPP_GLOBAL_Control
0x180059654  mov     rcx, [rcx+28h]; int
0x180059658  call    WPP_RECORDER_SF_sq
0x18005965d  lea     rdi, [rbx+0D0h]
0x180059664  cmp     qword ptr [rdi], 0
0x180059668  jz      short loc_1800596A6
0x18005966a  lea     rcx, ?g_ImportExportList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x180059671  call    cs:__imp_EnterCriticalSection
0x180059677  mov     rdx, [rdi]
0x18005967a  cmp     [rdx+8], rdi
0x18005967e  jnz     short loc_18005969F
0x180059680  mov     rax, [rdi+8]
0x180059684  cmp     [rax], rdi
0x180059687  jnz     short loc_18005969F
0x180059689  mov     [rax], rdx
0x18005968c  mov     [rdx+8], rax
0x180059690  lea     rcx, ?g_ImportExportList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x180059697  call    cs:__imp_LeaveCriticalSection
0x18005969d  jmp     short loc_1800596A6
0x18005969f  mov     ecx, 3
0x1800596a4  int     29h; Win8: RtlFailFast(ecx)
0x1800596a6  lea     r9, [rbx+58h]
0x1800596aa  mov     rcx, [r9]
0x1800596ad  cmp     dword ptr [rbx+2Ch], 0
0x1800596b1  jz      loc_180059784
0x1800596b7  test    rcx, rcx
0x1800596ba  jz      loc_180059795
0x1800596c0  mov     [rsp+58h+arg_8], 0
0x1800596c9  xor     r8d, r8d; pReturnValue
0x1800596cc  lea     edx, [r8+20h]; nProcNum
0x1800596d0  lea     rcx, stru_180083280; pProxyInfo
0x1800596d7  call    cs:__imp_NdrClientCall3
0x1800596dd  mov     [rsp+58h+arg_8], rax
0x1800596e2  test    eax, eax
0x1800596e4  jns     short loc_18005971C
0x1800596e6  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1800596ed  jz      short loc_18005971C
0x1800596ef  mov     r9d, 0Dh; int
0x1800596f5  mov     dword ptr [rsp+58h+var_20], eax; char
0x1800596f9  mov     qword ptr [rsp+58h+var_28], rbx; char
0x1800596fe  mov     rax, [rbx+30h]
0x180059702  mov     [rsp+58h+var_30], rax; __int64
0x180059707  mov     [rsp+58h+MessageGuid], rsi; MessageGuid
0x18005970c  mov     rcx, cs:WPP_GLOBAL_Control
0x180059713  mov     rcx, [rcx+28h]; int
0x180059717  call    WPP_RECORDER_SF_SqD
0x18005971c  jmp     short loc_180059795
0x18005971e  cmp     eax, 1
0x180059721  jl      short loc_18005972B
0x180059723  movzx   eax, ax
0x180059726  or      eax, 80010000h
0x18005972b  lea     rcx, WPP_RECORDER_INITIALIZED
0x180059732  mov     rbx, qword ptr [rsp+58h+arg_0]
0x180059737  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18005973e  jz      short loc_180059774
0x180059740  mov     r9d, 0Eh; int
0x180059746  mov     dword ptr [rsp+58h+var_20], eax; char
0x18005974a  mov     qword ptr [rsp+58h+var_28], rbx; char
0x18005974f  mov     rax, [rbx+30h]
0x180059753  mov     [rsp+58h+var_30], rax; __int64
0x180059758  lea     rax, WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids
0x18005975f  mov     [rsp+58h+MessageGuid], rax; MessageGuid
0x180059764  mov     rcx, cs:WPP_GLOBAL_Control
0x18005976b  mov     rcx, [rcx+28h]; int
0x18005976f  call    WPP_RECORDER_SF_SqD
0x180059774  lea     r14, WPP_RECORDER_INITIALIZED
0x18005977b  lea     rsi, WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids
0x180059782  jmp     short loc_180059795
0x180059784  test    rcx, rcx
0x180059787  jz      short loc_180059795
0x180059789  mov     rax, [rcx]
0x18005978c  mov     rax, [rax+10h]
0x180059790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059795  mov     rdi, [rbx+30h]
0x180059799  test    rdi, rdi
0x18005979c  jz      short loc_1800597B2
0x18005979e  call    cs:__imp_GetProcessHeap
0x1800597a4  mov     r8, rdi; lpMem
0x1800597a7  xor     edx, edx; dwFlags
0x1800597a9  mov     rcx, rax; hHeap
0x1800597ac  call    cs:__imp_HeapFree
0x1800597b2  lea     rcx, [rbx+0E8h]; lpCriticalSection
0x1800597b9  call    cs:__imp_DeleteCriticalSection
0x1800597bf  mov     rcx, [rbx+110h]; hObject
0x1800597c6  test    rcx, rcx
0x1800597c9  jz      short loc_1800597D1
0x1800597cb  call    cs:__imp_CloseHandle
0x1800597d1  mov     rcx, [rbx+118h]; pwa
0x1800597d8  test    rcx, rcx
0x1800597db  jz      short loc_1800597E3
0x1800597dd  call    cs:__imp_CloseThreadpoolWait
0x1800597e3  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1800597ea  jz      short loc_18005980C
0x1800597ec  mov     r9d, 0Fh; int
0x1800597f2  mov     qword ptr [rsp+58h+var_28], rbx; char
0x1800597f7  mov     [rsp+58h+MessageGuid], rsi; MessageGuid
0x1800597fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180059803  mov     rcx, [rcx+28h]; int
0x180059807  call    WPP_RECORDER_SF_sq
0x18005980c  mov     rbx, [rsp+58h+arg_10]
0x180059811  add     rsp, 40h
0x180059815  pop     r14
0x180059817  pop     rdi
0x180059818  pop     rsi
0x180059819  retn
```
