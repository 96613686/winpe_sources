# GetTokenForVTableEntry_Exported(HINSTANCE__ *,uchar * *)

- ea: `0x1800018c0`
- end: `0x180001a7e`
- name: `?GetTokenForVTableEntry_Exported@@YAIPEAUHINSTANCE__@@PEAPEAE@Z`
- size: `446`
- prototype: `unsigned int __fastcall(HINSTANCE, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800018c0`
- `0x180002a90`
- `0x1800089a0`
- `0x180045020`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800019b6`
- `KERNEL32!EnterCriticalSection` at `0x1800019b6`
- `KERNEL32!LeaveCriticalSection` at `0x1800019d3`
- `KERNEL32!LeaveCriticalSection` at `0x1800019d3`
- `KERNEL32!GetProcAddress` at `0x180001a2f`
- `KERNEL32!GetProcAddress` at `0x180001a4b`
- `KERNEL32!GetProcAddress` at `0x180001a2f`
- `KERNEL32!GetProcAddress` at `0x180001a4b`

## string_xrefs

- `0x180001a25`: `GetTokenForVTableEntry_RetAddr`
- `0x180001a41`: `GetTokenForVTableEntry`

## pseudocode

```c
__int64 __fastcall GetTokenForVTableEntry_Exported(HINSTANCE a1, unsigned __int8 **a2)
{
  unsigned __int8 **v2; // rdi
  BOOL v4; // ebx
  HMODULE v5; // rbp
  struct VTableBootstrapThunkChunk *i; // rax
  bool v9; // zf
  void *retaddr; // [rsp+28h] [rbp+0h]

  v2 = a2;
  if ( !(_DWORD)g_shimImplStatus )
    InitShimImpl((__int64)a1, (int (*)(unsigned __int16 *, void *))a2);
  v4 = 0;
  if ( g_lpOnShimDllMainCalledProc )
  {
    v5 = 0;
    if ( !(_DWORD)g_shimImplStatus )
      InitShimImpl((__int64)a1, (int (*)(unsigned __int16 *, void *))a2);
    if ( (_DWORD)g_shimImplStatus == 2 )
      v5 = g_hShimImplInst;
    if ( (_DWORD)g_shimImplStatus == 1 )
      return v4;
    if ( (_DWORD)g_shimImplStatus == 3 )
      return (int)GetTokenForVTableEntry(a1, v2);
    if ( g_bShimImplDllUninitialized )
      return v4;
    if ( g_pfGetTokenForVTableEntry_RetAddr == (unsigned int (*)(HINSTANCE, unsigned __int8 **, void *))-1LL )
      g_pfGetTokenForVTableEntry_RetAddr = (unsigned int (*)(HINSTANCE, unsigned __int8 **, void *))GetProcAddress(v5, "GetTokenForVTableEntry_RetAddr");
    if ( g_pfGetTokenForVTableEntry_RetAddr )
      return (int)((__int64 (__fastcall *)(HINSTANCE, unsigned __int8 **, void *))g_pfGetTokenForVTableEntry_RetAddr)(
                    a1,
                    v2,
                    retaddr);
    if ( g_pfGetTokenForVTableEntry == (unsigned int (*)(HINSTANCE, unsigned __int8 **))-1LL )
      g_pfGetTokenForVTableEntry = (unsigned int (*)(HINSTANCE, unsigned __int8 **))GetProcAddress(
                                                                                      v5,
                                                                                      "GetTokenForVTableEntry");
    if ( !g_pfGetTokenForVTableEntry )
      return v4;
    return (int)((__int64 (__fastcall *)(HINSTANCE, unsigned __int8 **))g_pfGetTokenForVTableEntry)(a1, v2);
  }
  EnterCriticalSection(&g_chunkLock);
  for ( i = g_pVTableBootstrapThunkChunkList; i; v4 = v9 )
  {
    if ( v4 )
      break;
    v9 = *(_QWORD *)i == (_QWORD)a1;
    i = (struct VTableBootstrapThunkChunk *)*((_QWORD *)i + 2);
  }
  LeaveCriticalSection(&g_chunkLock);
  if ( v4 )
    v2 = (unsigned __int8 **)(*v2 + 24);
  return *(unsigned int *)v2;
}

```

## disassembly

```asm
0x1800018c0  mov     [rsp+arg_10], rsi
0x1800018c5  push    rdi
0x1800018c6  sub     rsp, 20h
0x1800018ca  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x1800018d0  mov     rdi, rdx
0x1800018d3  mov     rsi, rcx
0x1800018d6  test    eax, eax
0x1800018d8  jz      loc_180001A01
0x1800018de  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x1800018e4  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x1800018ea  mov     rax, cs:?g_lpOnShimDllMainCalledProc@@3R6AHPEAXK0@ZEA; int (*g_lpOnShimDllMainCalledProc)(void *,ulong,void *)
0x1800018f1  mov     [rsp+28h+arg_0], rbx
0x1800018f6  xor     ebx, ebx
0x1800018f8  test    rax, rax
0x1800018fb  jz      loc_1800019AF
0x180001901  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x180001907  mov     [rsp+28h+arg_8], rbp
0x18000190c  mov     ebp, ebx
0x18000190e  test    eax, eax
0x180001910  jz      loc_180001A0B
0x180001916  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x18000191c  cmp     eax, 2
0x18000191f  jnz     short loc_180001928
0x180001921  mov     rbp, cs:?g_hShimImplInst@@3REAUHINSTANCE__@@EA; HINSTANCE__ * g_hShimImplInst
0x180001928  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x18000192e  cmp     eax, 1
0x180001931  jz      short loc_180001998
0x180001933  cmp     eax, 3
0x180001936  jz      loc_180001A15
0x18000193c  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180001942  test    eax, eax
0x180001944  jnz     short loc_180001998
0x180001946  mov     rax, cs:?g_pfGetTokenForVTableEntry_RetAddr@@3R6AIPEAUHINSTANCE__@@PEAPEAEPEAX@ZEA; uint (*g_pfGetTokenForVTableEntry_RetAddr)(HINSTANCE__ *,uchar * *,void *)
0x18000194d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001951  jz      loc_180001A25
0x180001957  mov     rax, cs:?g_pfGetTokenForVTableEntry_RetAddr@@3R6AIPEAUHINSTANCE__@@PEAPEAEPEAX@ZEA; uint (*g_pfGetTokenForVTableEntry_RetAddr)(HINSTANCE__ *,uchar * *,void *)
0x18000195e  test    rax, rax
0x180001961  jnz     loc_1800019E8
0x180001967  mov     rax, cs:?g_pfGetTokenForVTableEntry@@3R6AIPEAUHINSTANCE__@@PEAPEAE@ZEA; uint (*g_pfGetTokenForVTableEntry)(HINSTANCE__ *,uchar * *)
0x18000196e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001972  jz      loc_180001A41
0x180001978  mov     rax, cs:?g_pfGetTokenForVTableEntry@@3R6AIPEAUHINSTANCE__@@PEAPEAE@ZEA; uint (*g_pfGetTokenForVTableEntry)(HINSTANCE__ *,uchar * *)
0x18000197f  test    rax, rax
0x180001982  jz      short loc_180001998
0x180001984  mov     rax, cs:?g_pfGetTokenForVTableEntry@@3R6AIPEAUHINSTANCE__@@PEAPEAE@ZEA; uint (*g_pfGetTokenForVTableEntry)(HINSTANCE__ *,uchar * *)
0x18000198b  mov     rdx, rdi
0x18000198e  mov     rcx, rsi
0x180001991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001996  mov     ebx, eax
0x180001998  mov     rbp, [rsp+28h+arg_8]
0x18000199d  mov     eax, ebx
0x18000199f  mov     rbx, [rsp+28h+arg_0]
0x1800019a4  mov     rsi, [rsp+28h+arg_10]
0x1800019a9  add     rsp, 20h
0x1800019ad  pop     rdi
0x1800019ae  retn
0x1800019af  lea     rcx, ?g_chunkLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800019b6  call    cs:__imp_EnterCriticalSection
0x1800019bc  mov     rax, cs:?g_pVTableBootstrapThunkChunkList@@3PEAVVTableBootstrapThunkChunk@@EA; VTableBootstrapThunkChunk * g_pVTableBootstrapThunkChunkList
0x1800019c3  test    rax, rax
0x1800019c6  jnz     loc_180001A5D
0x1800019cc  lea     rcx, ?g_chunkLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800019d3  call    cs:__imp_LeaveCriticalSection
0x1800019d9  test    ebx, ebx
0x1800019db  jz      short loc_1800019E4
0x1800019dd  mov     rdi, [rdi]
0x1800019e0  add     rdi, 18h
0x1800019e4  mov     eax, [rdi]
0x1800019e6  jmp     short loc_18000199F
0x1800019e8  mov     rax, cs:?g_pfGetTokenForVTableEntry_RetAddr@@3R6AIPEAUHINSTANCE__@@PEAPEAEPEAX@ZEA; uint (*g_pfGetTokenForVTableEntry_RetAddr)(HINSTANCE__ *,uchar * *,void *)
0x1800019ef  mov     rdx, rdi
0x1800019f2  mov     r8, [rsp+28h]
0x1800019f7  mov     rcx, rsi
0x1800019fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019ff  jmp     short loc_180001996
0x180001a01  call    ?InitShimImpl@@YAXXZ; InitShimImpl(void)
0x180001a06  jmp     loc_1800018DE
0x180001a0b  call    ?InitShimImpl@@YAXXZ; InitShimImpl(void)
0x180001a10  jmp     loc_180001916
0x180001a15  mov     rdx, rdi; unsigned __int8 **
0x180001a18  mov     rcx, rsi; HINSTANCE
0x180001a1b  call    ?GetTokenForVTableEntry@@YAIPEAUHINSTANCE__@@PEAPEAE@Z; GetTokenForVTableEntry(HINSTANCE__ *,uchar * *)
0x180001a20  jmp     loc_180001996
0x180001a25  lea     rdx, aGettokenforvta_1; "GetTokenForVTableEntry_RetAddr"
0x180001a2c  mov     rcx, rbp; hModule
0x180001a2f  call    cs:__imp_GetProcAddress
0x180001a35  mov     cs:?g_pfGetTokenForVTableEntry_RetAddr@@3R6AIPEAUHINSTANCE__@@PEAPEAEPEAX@ZEA, rax; uint (*g_pfGetTokenForVTableEntry_RetAddr)(HINSTANCE__ *,uchar * *,void *)
0x180001a3c  jmp     loc_180001957
0x180001a41  lea     rdx, aGettokenforvta_0; "GetTokenForVTableEntry"
0x180001a48  mov     rcx, rbp; hModule
0x180001a4b  call    cs:__imp_GetProcAddress
0x180001a51  mov     cs:?g_pfGetTokenForVTableEntry@@3R6AIPEAUHINSTANCE__@@PEAPEAE@ZEA, rax; uint (*g_pfGetTokenForVTableEntry)(HINSTANCE__ *,uchar * *)
0x180001a58  jmp     loc_180001978
0x180001a5d  mov     ecx, 1
0x180001a62  test    ebx, ebx
0x180001a64  jnz     loc_1800019CC
0x180001a6a  cmp     [rax], rsi
0x180001a6d  mov     rax, [rax+10h]
0x180001a71  cmovz   ebx, ecx
0x180001a74  test    rax, rax
0x180001a77  jnz     short loc_180001A62
0x180001a79  jmp     loc_1800019CC
```
