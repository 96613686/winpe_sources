# OpenCtrs(ushort *)

- ea: `0x18002b5b8`
- end: `0x18002b7ae`
- name: `?OpenCtrs@@YAKPEAG@Z`
- size: `502`
- prototype: `unsigned int __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x1800077c0`

## callees

- `0x180003740`
- `0x180003840`
- `0x180008710`
- `0x18000c1a8`
- `0x18000d614`
- `0x1800297ac`
- `0x18002b5b8`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002b6fa`
- `KERNEL32!GetProcAddress` at `0x18002b715`
- `KERNEL32!GetProcAddress` at `0x18002b730`
- `KERNEL32!GetProcAddress` at `0x18002b6fa`
- `KERNEL32!GetProcAddress` at `0x18002b715`
- `KERNEL32!GetProcAddress` at `0x18002b730`
- `KERNEL32!FreeLibrary` at `0x18002b777`
- `KERNEL32!FreeLibrary` at `0x18002b777`
- `KERNEL32!LoadLibraryExW` at `0x18002b6ce`
- `KERNEL32!LoadLibraryExW` at `0x18002b6ce`

## string_xrefs

- `0x18002b6f3`: `OpenCtrs`
- `0x18002b6b3`: `CorperfmonExt.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OpenCtrs(unsigned __int16 *a1)
{
  __int64 v2; // rcx
  rsize_t v3; // rbx
  unsigned __int128 v4; // rax
  wchar_t *v5; // rax
  wchar_t *v6; // rdi
  unsigned int v7; // ebx
  unsigned int (*ProcAddress)(void); // rax
  unsigned __int16 *v10[2]; // [rsp+20h] [rbp-59h] BYREF
  __int128 v11; // [rsp+30h] [rbp-49h]
  __int128 v12; // [rsp+40h] [rbp-39h]
  __int128 v13; // [rsp+50h] [rbp-29h]
  __int64 v14; // [rsp+60h] [rbp-19h]
  int v15; // [rsp+68h] [rbp-11h]
  __int64 v16; // [rsp+70h] [rbp-9h]
  int v17; // [rsp+78h] [rbp-1h]
  __int64 v18; // [rsp+80h] [rbp+7h]
  __int64 v19; // [rsp+88h] [rbp+Fh]
  __int64 v20; // [rsp+90h] [rbp+17h]
  int v21; // [rsp+98h] [rbp+1Fh]
  __int64 v22; // [rsp+A0h] [rbp+27h]

  if ( !g_dwNumPerfCounterDllOpened )
  {
    *(_OWORD *)v10 = 0;
    v11 = 0;
    v12 = 0;
    v13 = 0;
    v14 = 1;
    v15 = 0;
    v16 = 0;
    v17 = 1;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = -1;
    DWORD2(v13) = 1;
    if ( (int)RuntimeRequest::FindVersionedRuntime(v10, 0, 0) >= 0 )
    {
      v2 = -1;
      do
        ++v2;
      while ( Src[v2] );
      if ( (unsigned __int64)~v2 < 0x11 || v2 == -18 )
      {
        v7 = -2146233066;
        goto LABEL_19;
      }
      v3 = v2 + 18;
      v4 = (unsigned __int64)(v2 + 18) * (unsigned __int128)2uLL;
      if ( !is_mul_ok(v2 + 18, 2u) )
        *(_QWORD *)&v4 = -1;
      v5 = (wchar_t *)operator new(v4, *((const struct NoThrow **)&v4 + 1));
      v6 = v5;
      if ( !v5 )
      {
        v7 = 8;
LABEL_19:
        RuntimeRequest::~RuntimeRequest((RuntimeRequest *)v10);
        return v7;
      }
      wcscpy_s(v5, v3, Src);
      wcscat_s(v6, v3, L"CorperfmonExt.dll");
      g_hPerfCounterDllMod = LoadLibraryExW(v6, 0, 8u);
      operator delete(v6);
      if ( g_hPerfCounterDllMod )
      {
        g_pfnOpenPerfCounters = (unsigned int (*)(unsigned __int16 *))GetProcAddress(g_hPerfCounterDllMod, "OpenCtrs");
        g_pfnCollectPerfCounters = (unsigned int (*)(unsigned __int16 *, void **, unsigned int *, unsigned int *))GetProcAddress(g_hPerfCounterDllMod, "CollectCtrs");
        ProcAddress = (unsigned int (*)(void))GetProcAddress(g_hPerfCounterDllMod, "CloseCtrs");
        g_pfnClosePerfCounters = ProcAddress;
        if ( g_pfnOpenPerfCounters && g_pfnCollectPerfCounters && ProcAddress )
        {
          v7 = ((__int64 (__fastcall *)(unsigned __int16 *))g_pfnOpenPerfCounters)(a1);
          if ( !v7 )
            ++g_dwNumPerfCounterDllOpened;
          goto LABEL_19;
        }
        FreeLibrary(g_hPerfCounterDllMod);
      }
    }
    v7 = 2;
    goto LABEL_19;
  }
  ++g_dwNumPerfCounterDllOpened;
  return 0;
}

```

## disassembly

```asm
0x18002b5b8  push    rbp
0x18002b5ba  push    rbx
0x18002b5bb  push    rsi
0x18002b5bc  push    rdi
0x18002b5bd  push    r14
0x18002b5bf  lea     rbp, [rsp-37h]
0x18002b5c4  sub     rsp, 0B0h
0x18002b5cb  mov     rsi, rcx
0x18002b5ce  mov     eax, cs:?g_dwNumPerfCounterDllOpened@@3KA; ulong g_dwNumPerfCounterDllOpened
0x18002b5d4  xor     r14d, r14d
0x18002b5d7  test    eax, eax
0x18002b5d9  jnz     loc_18002B796
0x18002b5df  xorps   xmm0, xmm0
0x18002b5e2  movdqa  xmmword ptr [rbp+57h+var_B0], xmm0
0x18002b5e7  xorps   xmm1, xmm1
0x18002b5ea  movdqa  [rbp+57h+var_A0], xmm1
0x18002b5ef  movdqa  [rbp+57h+var_90], xmm0
0x18002b5f4  movups  [rbp+57h+var_80], xmm1
0x18002b5f8  mov     [rbp+57h+var_70], 1
0x18002b600  mov     [rbp+57h+var_68], r14d
0x18002b604  mov     [rbp+57h+var_60], r14
0x18002b608  mov     [rbp+57h+var_58], 1
0x18002b60f  mov     [rbp+57h+var_50], r14
0x18002b613  mov     [rbp+57h+var_48], r14
0x18002b617  mov     [rbp+57h+var_40], r14
0x18002b61b  mov     [rbp+57h+var_38], r14d
0x18002b61f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002b623  mov     [rbp+57h+var_30], rdi
0x18002b627  mov     dword ptr [rbp+57h+var_80+8], 1
0x18002b62e  xor     r8d, r8d; int *
0x18002b631  xor     edx, edx; int
0x18002b633  lea     rcx, [rbp+57h+var_B0]; this
0x18002b637  call    ?FindVersionedRuntime@RuntimeRequest@@QEAAJHPEAH@Z; RuntimeRequest::FindVersionedRuntime(int,int *)
0x18002b63c  test    eax, eax
0x18002b63e  js      loc_18002B77D
0x18002b644  mov     rax, cs:Src
0x18002b64b  mov     rcx, rdi
0x18002b64e  inc     rcx
0x18002b651  cmp     [rax+rcx*2], r14w
0x18002b656  jnz     short loc_18002B64E
0x18002b658  mov     rax, rcx
0x18002b65b  not     rax
0x18002b65e  cmp     rax, 11h
0x18002b662  jb      loc_18002B78F
0x18002b668  lea     rax, [rcx+11h]
0x18002b66c  not     rax
0x18002b66f  cmp     rax, 1
0x18002b673  jb      loc_18002B78F
0x18002b679  lea     rbx, [rcx+12h]
0x18002b67d  mov     eax, 2
0x18002b682  mul     rbx
0x18002b685  cmovb   rax, rdi
0x18002b689  mov     rcx, rax; unsigned __int64
0x18002b68c  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x18002b691  mov     rdi, rax
0x18002b694  test    rax, rax
0x18002b697  jnz     short loc_18002B6A1
0x18002b699  lea     ebx, [rax+8]
0x18002b69c  jmp     loc_18002B782
0x18002b6a1  mov     r8, cs:Src; Source
0x18002b6a8  mov     rdx, rbx; SizeInWords
0x18002b6ab  mov     rcx, rdi; Destination
0x18002b6ae  call    wcscpy_s
0x18002b6b3  lea     r8, aCorperfmonextD; "CorperfmonExt.dll"
0x18002b6ba  mov     rdx, rbx; SizeInWords
0x18002b6bd  mov     rcx, rdi; Destination
0x18002b6c0  call    wcscat_s
0x18002b6c5  xor     edx, edx; hFile
0x18002b6c7  lea     r8d, [rdx+8]; dwFlags
0x18002b6cb  mov     rcx, rdi; lpLibFileName
0x18002b6ce  call    cs:__imp_LoadLibraryExW
0x18002b6d4  mov     cs:?g_hPerfCounterDllMod@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hPerfCounterDllMod
0x18002b6db  mov     rcx, rdi; void *
0x18002b6de  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002b6e3  mov     rcx, cs:?g_hPerfCounterDllMod@@3PEAUHINSTANCE__@@EA; hModule
0x18002b6ea  test    rcx, rcx
0x18002b6ed  jz      loc_18002B77D
0x18002b6f3  lea     rdx, aOpenctrs_0; "OpenCtrs"
0x18002b6fa  call    cs:__imp_GetProcAddress
0x18002b700  mov     cs:?g_pfnOpenPerfCounters@@3P6AKPEAG@ZEA, rax; ulong (*g_pfnOpenPerfCounters)(ushort *)
0x18002b707  lea     rdx, aCollectctrs_0; "CollectCtrs"
0x18002b70e  mov     rcx, cs:?g_hPerfCounterDllMod@@3PEAUHINSTANCE__@@EA; hModule
0x18002b715  call    cs:__imp_GetProcAddress
0x18002b71b  mov     cs:?g_pfnCollectPerfCounters@@3P6AKPEAGPEAPEAXPEAK2@ZEA, rax; ulong (*g_pfnCollectPerfCounters)(ushort *,void * *,ulong *,ulong *)
0x18002b722  lea     rdx, aClosectrs_0; "CloseCtrs"
0x18002b729  mov     rcx, cs:?g_hPerfCounterDllMod@@3PEAUHINSTANCE__@@EA; hModule
0x18002b730  call    cs:__imp_GetProcAddress
0x18002b736  mov     cs:?g_pfnClosePerfCounters@@3P6AKXZEA, rax; ulong (*g_pfnClosePerfCounters)(void)
0x18002b73d  mov     rdx, cs:?g_pfnOpenPerfCounters@@3P6AKPEAG@ZEA; ulong (*g_pfnOpenPerfCounters)(ushort *)
0x18002b744  test    rdx, rdx
0x18002b747  jz      short loc_18002B770
0x18002b749  cmp     cs:?g_pfnCollectPerfCounters@@3P6AKPEAGPEAPEAXPEAK2@ZEA, r14; ulong (*g_pfnCollectPerfCounters)(ushort *,void * *,ulong *,ulong *)
0x18002b750  jz      short loc_18002B770
0x18002b752  test    rax, rax
0x18002b755  jz      short loc_18002B770
0x18002b757  mov     rcx, rsi
0x18002b75a  mov     rax, rdx
0x18002b75d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b762  mov     ebx, eax
0x18002b764  test    eax, eax
0x18002b766  jnz     short loc_18002B782
0x18002b768  inc     cs:?g_dwNumPerfCounterDllOpened@@3KA; ulong g_dwNumPerfCounterDllOpened
0x18002b76e  jmp     short loc_18002B782
0x18002b770  mov     rcx, cs:?g_hPerfCounterDllMod@@3PEAUHINSTANCE__@@EA; hLibModule
0x18002b777  call    cs:__imp_FreeLibrary
0x18002b77d  mov     ebx, 2
0x18002b782  lea     rcx, [rbp+57h+var_B0]; this
0x18002b786  call    ??1RuntimeRequest@@QEAA@XZ; RuntimeRequest::~RuntimeRequest(void)
0x18002b78b  mov     eax, ebx
0x18002b78d  jmp     short loc_18002B7A0
0x18002b78f  mov     ebx, 80131516h
0x18002b794  jmp     short loc_18002B782
0x18002b796  inc     eax
0x18002b798  mov     cs:?g_dwNumPerfCounterDllOpened@@3KA, eax; ulong g_dwNumPerfCounterDllOpened
0x18002b79e  xor     eax, eax
0x18002b7a0  add     rsp, 0B0h
0x18002b7a7  pop     r14
0x18002b7a9  pop     rdi
0x18002b7aa  pop     rsi
0x18002b7ab  pop     rbx
0x18002b7ac  pop     rbp
0x18002b7ad  retn
```
