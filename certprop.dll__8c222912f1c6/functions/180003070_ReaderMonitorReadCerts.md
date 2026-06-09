# ReaderMonitorReadCerts

- ea: `0x180003070`
- end: `0x18000321d`
- name: `ReaderMonitorReadCerts`
- size: `429`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180002df0`

## callees

- `0x180003070`
- `0x180004600`
- `0x180018b58`
- `0x180018bb4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800031c8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800031c8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180003155`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180003155`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800030da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800030da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800031bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800031bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003164`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003164`

## pseudocode

```c
__int64 __fastcall ReaderMonitorReadCerts(__int64 a1)
{
  int v1; // ebp
  DWORD LastError; // ebx
  _DWORD *v4; // rax
  __int64 v5; // rcx
  _DWORD *v6; // rdi
  STRSAFE_LPSTR v7; // rcx
  struct _TP_WORK *ThreadpoolWork; // rax
  __int64 v9; // rcx

  v1 = g_fEnableRootCertProp;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 186, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  LastError = 8;
  v4 = HeapAlloc(hHeap, 8u, 0x18u);
  v6 = v4;
  if ( v4 )
  {
    *(_QWORD *)v4 = a1;
    v4[2] = 1;
    v4[3] = v1;
    ThreadpoolWork = CreateThreadpoolWork(I_ReaderListReadCertificates, v4, (PTP_CALLBACK_ENVIRON)(a1 + 136));
    *((_QWORD *)v6 + 2) = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      LastError = 0;
      SubmitThreadpoolWork(ThreadpoolWork);
    }
    else
    {
      LastError = GetLastError();
      WppTraceIndent(v9, 2);
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          188,
          (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
          WPP_pszIndent,
          LastError);
      }
      HeapFree(hHeap, 0, *((LPVOID *)v6 + 2));
    }
  }
  else
  {
    WppTraceIndent(v5, 2);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        187,
        &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
        WPP_pszIndent);
    }
  }
  WppTraceIndent(v7, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      189,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180003070  push    rbx
0x180003072  push    rbp
0x180003073  push    rsi
0x180003074  push    rdi
0x180003075  push    r14
0x180003077  sub     rsp, 30h
0x18000307b  mov     ebp, cs:g_fEnableRootCertProp
0x180003081  xor     edx, edx
0x180003083  mov     rsi, rcx
0x180003086  call    WppTraceIndent
0x18000308b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003092  lea     r14, WPP_GLOBAL_Control
0x180003099  cmp     rcx, r14
0x18000309c  jz      short loc_1800030C6
0x18000309e  test    byte ptr [rcx+1Ch], 2
0x1800030a2  jz      short loc_1800030C6
0x1800030a4  cmp     byte ptr [rcx+19h], 5
0x1800030a8  jb      short loc_1800030C6
0x1800030aa  mov     r9, cs:WPP_pszIndent
0x1800030b1  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800030b8  mov     rcx, [rcx+10h]
0x1800030bc  mov     edx, 0BAh
0x1800030c1  call    WPP_SF_s
0x1800030c6  mov     rcx, cs:hHeap; hHeap
0x1800030cd  mov     ebx, 8
0x1800030d2  mov     edx, ebx; dwFlags
0x1800030d4  mov     r8d, 18h; dwBytes
0x1800030da  call    cs:__imp_HeapAlloc
0x1800030e0  mov     rdi, rax
0x1800030e3  test    rax, rax
0x1800030e6  jnz     short loc_180003137
0x1800030e8  mov     edx, 2
0x1800030ed  call    WppTraceIndent
0x1800030f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030f9  cmp     rcx, r14
0x1800030fc  jz      loc_1800031CE
0x180003102  test    byte ptr [rcx+1Ch], 1
0x180003106  jz      loc_1800031CE
0x18000310c  cmp     byte ptr [rcx+19h], 2
0x180003110  jb      loc_1800031CE
0x180003116  mov     r9, cs:WPP_pszIndent
0x18000311d  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180003124  mov     rcx, [rcx+10h]
0x180003128  mov     edx, 0BBh
0x18000312d  call    WPP_SF_s
0x180003132  jmp     loc_1800031CE
0x180003137  lea     r8, [rsi+88h]; pcbe
0x18000313e  mov     [rax], rsi
0x180003141  mov     rdx, rdi; pv
0x180003144  mov     dword ptr [rax+8], 1
0x18000314b  lea     rcx, I_ReaderListReadCertificates; pfnwk
0x180003152  mov     [rax+0Ch], ebp
0x180003155  call    cs:__imp_CreateThreadpoolWork
0x18000315b  mov     [rdi+10h], rax
0x18000315f  test    rax, rax
0x180003162  jnz     short loc_1800031C3
0x180003164  call    cs:__imp_GetLastError
0x18000316a  mov     edx, 2
0x18000316f  mov     ebx, eax
0x180003171  call    WppTraceIndent
0x180003176  mov     rcx, cs:WPP_GLOBAL_Control
0x18000317d  cmp     rcx, r14
0x180003180  jz      short loc_1800031AE
0x180003182  test    byte ptr [rcx+1Ch], 1
0x180003186  jz      short loc_1800031AE
0x180003188  cmp     byte ptr [rcx+19h], 3
0x18000318c  jb      short loc_1800031AE
0x18000318e  mov     r9, cs:WPP_pszIndent
0x180003195  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000319c  mov     rcx, [rcx+10h]
0x1800031a0  mov     edx, 0BCh
0x1800031a5  mov     [rsp+58h+var_38], ebx
0x1800031a9  call    WPP_SF_sD
0x1800031ae  mov     r8, [rdi+10h]; lpMem
0x1800031b2  xor     edx, edx; dwFlags
0x1800031b4  mov     rcx, cs:hHeap; hHeap
0x1800031bb  call    cs:__imp_HeapFree
0x1800031c1  jmp     short loc_1800031CE
0x1800031c3  xor     ebx, ebx
0x1800031c5  mov     rcx, rax; pwk
0x1800031c8  call    cs:__imp_SubmitThreadpoolWork
0x1800031ce  mov     edx, 1
0x1800031d3  call    WppTraceIndent
0x1800031d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031df  cmp     rcx, r14
0x1800031e2  jz      short loc_180003210
0x1800031e4  test    byte ptr [rcx+1Ch], 2
0x1800031e8  jz      short loc_180003210
0x1800031ea  cmp     byte ptr [rcx+19h], 5
0x1800031ee  jb      short loc_180003210
0x1800031f0  mov     r9, cs:WPP_pszIndent
0x1800031f7  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800031fe  mov     rcx, [rcx+10h]
0x180003202  mov     edx, 0BDh
0x180003207  mov     [rsp+58h+var_38], ebx
0x18000320b  call    WPP_SF_sD
0x180003210  mov     eax, ebx
0x180003212  add     rsp, 30h
0x180003216  pop     r14
0x180003218  pop     rdi
0x180003219  pop     rsi
0x18000321a  pop     rbp
0x18000321b  pop     rbx
0x18000321c  retn
```
