# CImpIColumnsRowset::GetAvailableColumns(unsigned __int64 *,tagDBID * *)

- ea: `0x1800121c0`
- end: `0x1800122f5`
- name: `?GetAvailableColumns@CImpIColumnsRowset@@UEAAJPEA_KPEAPEAUtagDBID@@@Z`
- size: `309`
- prototype: `__int64 __fastcall(CImpIColumnsRowset *__hidden this, unsigned __int64 *, struct tagDBID **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x1800121c0`
- `0x180016584`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800121f1`
- `KERNEL32!GetCurrentThreadId` at `0x1800121f1`
- `KERNEL32!LeaveCriticalSection` at `0x1800122a7`
- `KERNEL32!LeaveCriticalSection` at `0x1800122dc`
- `KERNEL32!LeaveCriticalSection` at `0x1800122a7`
- `KERNEL32!LeaveCriticalSection` at `0x1800122dc`
- `ole32!CoTaskMemAlloc` at `0x180012238`
- `ole32!CoTaskMemAlloc` at `0x180012238`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001220e`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001220e`
- `MSDART!UMSEnterCSWraper` at `0x1800121db`
- `MSDART!UMSEnterCSWraper` at `0x1800121db`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIColumnsRowset::GetAvailableColumns(
        CImpIColumnsRowset *this,
        unsigned __int64 *a2,
        struct tagDBID **a3)
{
  __int64 v5; // rbx
  DWORD *v6; // rdi
  struct tagDBID *v7; // rax
  int v8; // ecx
  __int64 i; // r8
  __int64 v10; // rcx
  __int64 v11; // rax
  bool v12; // zf
  __int64 v13; // rcx
  unsigned int v15; // esi
  __int64 v16; // rcx

  v5 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v5);
  v6 = (DWORD *)(v5 + 8);
  if ( !*(_DWORD *)(v5 + 12) )
    *v6 = GetCurrentThreadId();
  ++*(_DWORD *)(v5 + 12);
  ++*(_DWORD *)(v5 + 16);
  SetErrorInfo(0, 0);
  if ( !a2 || !a3 )
  {
    v8 = -2147024809;
    goto LABEL_13;
  }
  *a2 = 31;
  v7 = (struct tagDBID *)CoTaskMemAlloc(0x3E0u);
  *a3 = v7;
  if ( !v7 )
  {
    v8 = -2147024882;
LABEL_13:
    v15 = Exit(v8, 0);
    --*(_DWORD *)(v5 + 16);
    v12 = (*(_DWORD *)(v5 + 12))-- == 1;
    if ( v12 )
      *v6 = -1;
    v16 = *(_QWORD *)v5;
    --*(_DWORD *)(v16 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v16 + 8));
    return v15;
  }
  for ( i = 11; i != 31; ++i )
  {
    v10 = 32 * i;
    v11 = (__int64)*a3;
    *(_OWORD *)(v10 + v11) = *((_OWORD *)&g_rgDesiredColumn + 5 * i);
    *(_OWORD *)(v10 + v11 + 16) = *((_OWORD *)&g_rgDesiredColumn + 5 * i + 1);
  }
  --*(_DWORD *)(v5 + 16);
  v12 = (*(_DWORD *)(v5 + 12))-- == 1;
  if ( v12 )
    *v6 = -1;
  v13 = *(_QWORD *)v5;
  --*(_DWORD *)(v13 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
  return 0;
}

```

## disassembly

```asm
0x1800121c0  push    rbx
0x1800121c2  push    rsi
0x1800121c3  push    rdi
0x1800121c4  push    r14
0x1800121c6  sub     rsp, 28h
0x1800121ca  mov     rsi, r8
0x1800121cd  mov     r14, rdx
0x1800121d0  mov     rbx, [rcx+18h]
0x1800121d4  sub     rbx, 0FFFFFFFFFFFFFF80h
0x1800121d8  mov     rcx, rbx
0x1800121db  call    cs:__imp_UMSEnterCSWraper
0x1800121e2  nop     dword ptr [rax+rax+00h]
0x1800121e7  lea     rdi, [rbx+8]
0x1800121eb  cmp     dword ptr [rbx+0Ch], 0
0x1800121ef  jnz     short loc_1800121FF
0x1800121f1  call    cs:__imp_GetCurrentThreadId
0x1800121f8  nop     dword ptr [rax+rax+00h]
0x1800121fd  mov     [rdi], eax
0x1800121ff  inc     dword ptr [rbx+0Ch]
0x180012202  inc     dword ptr [rbx+10h]
0x180012205  mov     [rsp+48h+arg_0], rbx
0x18001220a  xor     edx, edx; perrinfo
0x18001220c  xor     ecx, ecx; dwReserved
0x18001220e  call    cs:__imp_SetErrorInfo
0x180012215  nop     dword ptr [rax+rax+00h]
0x18001221a  test    r14, r14
0x18001221d  jz      loc_1800122B7
0x180012223  test    rsi, rsi
0x180012226  jz      loc_1800122B7
0x18001222c  mov     qword ptr [r14], 1Fh
0x180012233  mov     ecx, 3E0h; cb
0x180012238  call    cs:__imp_CoTaskMemAlloc
0x18001223f  nop     dword ptr [rax+rax+00h]
0x180012244  mov     [rsi], rax
0x180012247  test    rax, rax
0x18001224a  jnz     short loc_180012253
0x18001224c  mov     ecx, 8007000Eh
0x180012251  jmp     short loc_1800122BC
0x180012253  mov     r8d, 0Bh
0x180012259  lea     rdx, [r8+r8*4]
0x18001225d  add     rdx, rdx
0x180012260  lea     r9, ?g_rgDesiredColumn@@3QBUtagDESIREDCOLUMNS@@B; tagDESIREDCOLUMNS const near * const g_rgDesiredColumn
0x180012267  mov     rcx, r8
0x18001226a  shl     rcx, 5
0x18001226e  mov     rax, [rsi]
0x180012271  movups  xmm0, xmmword ptr [r9+rdx*8]
0x180012276  movups  xmmword ptr [rcx+rax], xmm0
0x18001227a  movups  xmm1, xmmword ptr [r9+rdx*8+10h]
0x180012280  movups  xmmword ptr [rcx+rax+10h], xmm1
0x180012285  inc     r8
0x180012288  cmp     r8, 1Fh
0x18001228c  jnz     short loc_180012259
0x18001228e  dec     dword ptr [rbx+10h]
0x180012291  sub     dword ptr [rbx+0Ch], 1
0x180012295  jnz     short loc_18001229D
0x180012297  mov     dword ptr [rdi], 0FFFFFFFFh
0x18001229d  mov     rcx, [rbx]
0x1800122a0  dec     dword ptr [rcx+30h]
0x1800122a3  add     rcx, 8; lpCriticalSection
0x1800122a7  call    cs:__imp_LeaveCriticalSection
0x1800122ae  nop     dword ptr [rax+rax+00h]
0x1800122b3  xor     eax, eax
0x1800122b5  jmp     short loc_1800122EA
0x1800122b7  mov     ecx, 80070057h; int
0x1800122bc  xor     edx, edx; unsigned int
0x1800122be  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x1800122c3  mov     esi, eax
0x1800122c5  or      edx, 0FFFFFFFFh
0x1800122c8  add     [rbx+10h], edx
0x1800122cb  add     [rbx+0Ch], edx
0x1800122ce  jnz     short loc_1800122D2
0x1800122d0  mov     [rdi], edx
0x1800122d2  mov     rcx, [rbx]
0x1800122d5  dec     dword ptr [rcx+30h]
0x1800122d8  add     rcx, 8; lpCriticalSection
0x1800122dc  call    cs:__imp_LeaveCriticalSection
0x1800122e3  nop     dword ptr [rax+rax+00h]
0x1800122e8  mov     eax, esi
0x1800122ea  add     rsp, 28h
0x1800122ee  pop     r14
0x1800122f0  pop     rdi
0x1800122f1  pop     rsi
0x1800122f2  pop     rbx
0x1800122f3  retn
```
