# ShellShim_GetCORRootDirectory

- ea: `0x180006ff0`
- end: `0x180007101`
- name: `ShellShim_GetCORRootDirectory`
- size: `273`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002a90`
- `0x180006ff0`
- `0x18002d57c`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180007060`
- `KERNEL32!GetProcAddress` at `0x180007090`
- `KERNEL32!GetProcAddress` at `0x180007060`
- `KERNEL32!GetProcAddress` at `0x180007090`

## string_xrefs

- `0x180007086`: `GetCORRootDirectory`
- `0x180007056`: `GetCORRootDirectory_RetAddr`

## pseudocode

```c
signed int __fastcall ShellShim_GetCORRootDirectory(void *a1, int (*a2)(unsigned __int16 *, void *), unsigned int *a3)
{
  HMODULE v3; // rbx
  unsigned int v5; // esi
  void *retaddr; // [rsp+58h] [rbp+0h]

  v3 = 0;
  v5 = (unsigned int)a2;
  if ( !(_DWORD)g_shimImplStatus )
    InitShimImpl((__int64)a1, a2);
  if ( (_DWORD)g_shimImplStatus == 2 )
    v3 = g_hShimImplInst;
  if ( (_DWORD)g_shimImplStatus != 1 )
  {
    if ( (_DWORD)g_shimImplStatus == 3 )
      return GetCORRootDirectory(a1, v5, a3);
    if ( !g_bShimImplDllUninitialized )
    {
      if ( g_pfGetCORRootDirectory_RetAddr == (int (*)(unsigned __int16 *, unsigned int, unsigned int *, void *))-1LL )
        g_pfGetCORRootDirectory_RetAddr = (int (*)(unsigned __int16 *, unsigned int, unsigned int *, void *))GetProcAddress(v3, "GetCORRootDirectory_RetAddr");
      if ( g_pfGetCORRootDirectory_RetAddr )
        return ((__int64 (__fastcall *)(void *, _QWORD, unsigned int *, void *))g_pfGetCORRootDirectory_RetAddr)(
                 a1,
                 v5,
                 a3,
                 retaddr);
      if ( g_pfGetCORRootDirectory == (int (*)(unsigned __int16 *, unsigned int, unsigned int *))-1LL )
        g_pfGetCORRootDirectory = (int (*)(unsigned __int16 *, unsigned int, unsigned int *))GetProcAddress(
                                                                                               v3,
                                                                                               "GetCORRootDirectory");
      if ( g_pfGetCORRootDirectory )
        return ((__int64 (__fastcall *)(void *, _QWORD, unsigned int *))g_pfGetCORRootDirectory)(a1, v5, a3);
    }
  }
  return -2146232575;
}

```

## disassembly

```asm
0x180006ff0  push    rbx
0x180006ff2  push    rbp
0x180006ff3  push    rsi
0x180006ff4  push    rdi
0x180006ff5  sub     rsp, 38h
0x180006ff9  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x180006fff  xor     ebx, ebx
0x180007001  mov     rdi, r8
0x180007004  mov     esi, edx
0x180007006  mov     rbp, rcx
0x180007009  test    eax, eax
0x18000700b  jz      loc_1800070C6
0x180007011  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x180007017  cmp     eax, 2
0x18000701a  jnz     short loc_180007023
0x18000701c  mov     rbx, cs:?g_hShimImplInst@@3REAUHINSTANCE__@@EA; HINSTANCE__ * g_hShimImplInst
0x180007023  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x180007029  cmp     eax, 1
0x18000702c  jz      loc_1800070FA
0x180007032  cmp     eax, 3
0x180007035  jz      loc_1800070D0
0x18000703b  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180007041  test    eax, eax
0x180007043  jnz     loc_1800070FA
0x180007049  mov     rax, cs:?g_pfGetCORRootDirectory_RetAddr@@3R6AJPEAGKPEAKPEAX@ZEA; long (*g_pfGetCORRootDirectory_RetAddr)(ushort *,ulong,ulong *,void *)
0x180007050  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007054  jnz     short loc_18000706D
0x180007056  lea     rdx, aGetcorrootdire_0; "GetCORRootDirectory_RetAddr"
0x18000705d  mov     rcx, rbx; hModule
0x180007060  call    cs:__imp_GetProcAddress
0x180007066  mov     cs:?g_pfGetCORRootDirectory_RetAddr@@3R6AJPEAGKPEAKPEAX@ZEA, rax; long (*g_pfGetCORRootDirectory_RetAddr)(ushort *,ulong,ulong *,void *)
0x18000706d  mov     rax, cs:?g_pfGetCORRootDirectory_RetAddr@@3R6AJPEAGKPEAKPEAX@ZEA; long (*g_pfGetCORRootDirectory_RetAddr)(ushort *,ulong,ulong *,void *)
0x180007074  test    rax, rax
0x180007077  jnz     short loc_1800070DF
0x180007079  mov     rax, cs:?g_pfGetCORRootDirectory@@3R6AJPEAGKPEAK@ZEA; long (*g_pfGetCORRootDirectory)(ushort *,ulong,ulong *)
0x180007080  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007084  jnz     short loc_18000709D
0x180007086  lea     rdx, aGetcorrootdire_1; "GetCORRootDirectory"
0x18000708d  mov     rcx, rbx; hModule
0x180007090  call    cs:__imp_GetProcAddress
0x180007096  mov     cs:?g_pfGetCORRootDirectory@@3R6AJPEAGKPEAK@ZEA, rax; long (*g_pfGetCORRootDirectory)(ushort *,ulong,ulong *)
0x18000709d  mov     rax, cs:?g_pfGetCORRootDirectory@@3R6AJPEAGKPEAK@ZEA; long (*g_pfGetCORRootDirectory)(ushort *,ulong,ulong *)
0x1800070a4  test    rax, rax
0x1800070a7  jz      short loc_1800070FA
0x1800070a9  mov     rax, cs:?g_pfGetCORRootDirectory@@3R6AJPEAGKPEAK@ZEA; long (*g_pfGetCORRootDirectory)(ushort *,ulong,ulong *)
0x1800070b0  mov     r8, rdi
0x1800070b3  mov     edx, esi
0x1800070b5  mov     rcx, rbp
0x1800070b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070bd  add     rsp, 38h
0x1800070c1  pop     rdi
0x1800070c2  pop     rsi
0x1800070c3  pop     rbp
0x1800070c4  pop     rbx
0x1800070c5  retn
0x1800070c6  call    ?InitShimImpl@@YAXXZ; InitShimImpl(void)
0x1800070cb  jmp     loc_180007011
0x1800070d0  mov     r8, rdi
0x1800070d3  mov     edx, esi
0x1800070d5  mov     rcx, rbp; void *
0x1800070d8  call    GetCORRootDirectory
0x1800070dd  jmp     short loc_1800070BD
0x1800070df  mov     rax, cs:?g_pfGetCORRootDirectory_RetAddr@@3R6AJPEAGKPEAKPEAX@ZEA; long (*g_pfGetCORRootDirectory_RetAddr)(ushort *,ulong,ulong *,void *)
0x1800070e6  mov     r8, rdi
0x1800070e9  mov     r9, [rsp+58h]
0x1800070ee  mov     edx, esi
0x1800070f0  mov     rcx, rbp
0x1800070f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070f8  jmp     short loc_1800070BD
0x1800070fa  mov     eax, 80131701h
0x1800070ff  jmp     short loc_1800070BD
```
