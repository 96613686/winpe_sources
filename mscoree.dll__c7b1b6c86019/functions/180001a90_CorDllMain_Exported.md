# _CorDllMain_Exported

- ea: `0x180001a90`
- end: `0x180001bfe`
- name: `_CorDllMain_Exported`
- size: `366`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001a90`
- `0x180002a90`
- `0x18002efb4`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180001b9e`
- `KERNEL32!GetProcAddress` at `0x180001bda`
- `KERNEL32!GetProcAddress` at `0x180001b9e`
- `KERNEL32!GetProcAddress` at `0x180001bda`

## string_xrefs

- `0x180001b94`: `_CorDllMain`
- `0x180001bd0`: `_CorDllMain_RetAddr`

## pseudocode

```c
__int64 __fastcall CorDllMain_Exported(HINSTANCE a1, int (*a2)(unsigned __int16 *, void *), void *a3)
{
  unsigned int v4; // esi
  HMODULE v6; // rbx
  void *retaddr; // [rsp+38h] [rbp+0h]

  v4 = (unsigned int)a2;
  if ( !(_DWORD)g_shimImplStatus )
    InitShimImpl((__int64)a1, a2);
  if ( !g_lpOnShimDllMainCalledProc )
    return CorDllMain(a1, v4, a3);
  v6 = 0;
  if ( !(_DWORD)g_shimImplStatus )
    InitShimImpl((__int64)a1, a2);
  if ( (_DWORD)g_shimImplStatus == 2 )
    v6 = g_hShimImplInst;
  if ( (_DWORD)g_shimImplStatus == 1 )
    return 0;
  if ( (_DWORD)g_shimImplStatus == 3 )
    return CorDllMain(a1, v4, a3);
  if ( g_bShimImplDllUninitialized )
    return 0;
  if ( g_pf_CorDllMain_RetAddr == (int (*)(HINSTANCE, unsigned int, void *, void *))-1LL )
    g_pf_CorDllMain_RetAddr = (int (*)(HINSTANCE, unsigned int, void *, void *))GetProcAddress(
                                                                                  v6,
                                                                                  "_CorDllMain_RetAddr");
  if ( !g_pf_CorDllMain_RetAddr )
  {
    if ( g_pf_CorDllMain == (int (*)(HINSTANCE, unsigned int, void *))-1LL )
      g_pf_CorDllMain = (int (*)(HINSTANCE, unsigned int, void *))GetProcAddress(v6, "_CorDllMain");
    if ( g_pf_CorDllMain )
      return ((__int64 (__fastcall *)(HINSTANCE, _QWORD, void *))g_pf_CorDllMain)(a1, v4, a3);
    return 0;
  }
  return ((__int64 (__fastcall *)(HINSTANCE, _QWORD, void *, void *))g_pf_CorDllMain_RetAddr)(a1, v4, a3, retaddr);
}

```

## disassembly

```asm
0x180001a90  mov     [rsp+arg_8], rbp
0x180001a95  mov     [rsp+arg_10], rsi
0x180001a9a  push    rdi
0x180001a9b  sub     rsp, 30h
0x180001a9f  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x180001aa5  mov     rdi, r8
0x180001aa8  mov     esi, edx
0x180001aaa  mov     rbp, rcx
0x180001aad  test    eax, eax
0x180001aaf  jz      loc_180001BAD
0x180001ab5  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x180001abb  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x180001ac1  mov     rax, cs:?g_lpOnShimDllMainCalledProc@@3R6AHPEAXK0@ZEA; int (*g_lpOnShimDllMainCalledProc)(void *,ulong,void *)
0x180001ac8  test    rax, rax
0x180001acb  jz      loc_180001BEC
0x180001ad1  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x180001ad7  mov     [rsp+38h+arg_0], rbx
0x180001adc  xor     ebx, ebx
0x180001ade  test    eax, eax
0x180001ae0  jz      loc_180001BB7
0x180001ae6  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x180001aec  cmp     eax, 2
0x180001aef  jnz     short loc_180001AF8
0x180001af1  mov     rbx, cs:?g_hShimImplInst@@3REAUHINSTANCE__@@EA; HINSTANCE__ * g_hShimImplInst
0x180001af8  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x180001afe  cmp     eax, 1
0x180001b01  jz      short loc_180001B75
0x180001b03  cmp     eax, 3
0x180001b06  jz      loc_180001BC1
0x180001b0c  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180001b12  test    eax, eax
0x180001b14  jnz     short loc_180001B75
0x180001b16  mov     rax, cs:?g_pf_CorDllMain_RetAddr@@3R6AHPEAUHINSTANCE__@@KPEAX1@ZEA; int (*g_pf_CorDllMain_RetAddr)(HINSTANCE__ *,ulong,void *,void *)
0x180001b1d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001b21  jz      loc_180001BD0
0x180001b27  mov     rax, cs:?g_pf_CorDllMain_RetAddr@@3R6AHPEAUHINSTANCE__@@KPEAX1@ZEA; int (*g_pf_CorDllMain_RetAddr)(HINSTANCE__ *,ulong,void *,void *)
0x180001b2e  test    rax, rax
0x180001b31  jnz     short loc_180001B79
0x180001b33  mov     rax, cs:?g_pf_CorDllMain@@3R6AHPEAUHINSTANCE__@@KPEAX@ZEA; int (*g_pf_CorDllMain)(HINSTANCE__ *,ulong,void *)
0x180001b3a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001b3e  jz      short loc_180001B94
0x180001b40  mov     rax, cs:?g_pf_CorDllMain@@3R6AHPEAUHINSTANCE__@@KPEAX@ZEA; int (*g_pf_CorDllMain)(HINSTANCE__ *,ulong,void *)
0x180001b47  test    rax, rax
0x180001b4a  jz      short loc_180001B75
0x180001b4c  mov     rax, cs:?g_pf_CorDllMain@@3R6AHPEAUHINSTANCE__@@KPEAX@ZEA; int (*g_pf_CorDllMain)(HINSTANCE__ *,ulong,void *)
0x180001b53  mov     r8, rdi
0x180001b56  mov     edx, esi
0x180001b58  mov     rcx, rbp
0x180001b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b60  mov     rbx, [rsp+38h+arg_0]
0x180001b65  mov     rbp, [rsp+38h+arg_8]
0x180001b6a  mov     rsi, [rsp+38h+arg_10]
0x180001b6f  add     rsp, 30h
0x180001b73  pop     rdi
0x180001b74  retn
0x180001b75  xor     eax, eax
0x180001b77  jmp     short loc_180001B60
0x180001b79  mov     rax, cs:?g_pf_CorDllMain_RetAddr@@3R6AHPEAUHINSTANCE__@@KPEAX1@ZEA; int (*g_pf_CorDllMain_RetAddr)(HINSTANCE__ *,ulong,void *,void *)
0x180001b80  mov     r8, rdi
0x180001b83  mov     r9, [rsp+38h]
0x180001b88  mov     edx, esi
0x180001b8a  mov     rcx, rbp
0x180001b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b92  jmp     short loc_180001B60
0x180001b94  lea     rdx, aCordllmain_0; "_CorDllMain"
0x180001b9b  mov     rcx, rbx; hModule
0x180001b9e  call    cs:__imp_GetProcAddress
0x180001ba4  mov     cs:?g_pf_CorDllMain@@3R6AHPEAUHINSTANCE__@@KPEAX@ZEA, rax; int (*g_pf_CorDllMain)(HINSTANCE__ *,ulong,void *)
0x180001bab  jmp     short loc_180001B40
0x180001bad  call    ?InitShimImpl@@YAXXZ; InitShimImpl(void)
0x180001bb2  jmp     loc_180001AB5
0x180001bb7  call    ?InitShimImpl@@YAXXZ; InitShimImpl(void)
0x180001bbc  jmp     loc_180001AE6
0x180001bc1  mov     r8, rdi; void *
0x180001bc4  mov     edx, esi; unsigned int
0x180001bc6  mov     rcx, rbp; HINSTANCE
0x180001bc9  call    _CorDllMain
0x180001bce  jmp     short loc_180001B60
0x180001bd0  lea     rdx, aCordllmainReta; "_CorDllMain_RetAddr"
0x180001bd7  mov     rcx, rbx; hModule
0x180001bda  call    cs:__imp_GetProcAddress
0x180001be0  mov     cs:?g_pf_CorDllMain_RetAddr@@3R6AHPEAUHINSTANCE__@@KPEAX1@ZEA, rax; int (*g_pf_CorDllMain_RetAddr)(HINSTANCE__ *,ulong,void *,void *)
0x180001be7  jmp     loc_180001B27
0x180001bec  mov     r8, rdi; void *
0x180001bef  mov     edx, esi; unsigned int
0x180001bf1  mov     rcx, rbp; HINSTANCE
0x180001bf4  call    _CorDllMain
0x180001bf9  jmp     loc_180001B65
```
