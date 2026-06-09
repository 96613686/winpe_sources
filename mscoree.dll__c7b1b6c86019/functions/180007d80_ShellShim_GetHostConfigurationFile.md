# ShellShim_GetHostConfigurationFile

- ea: `0x180007d80`
- end: `0x180007e8c`
- name: `ShellShim_GetHostConfigurationFile`
- size: `268`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180002a90`
- `0x180007d80`
- `0x18002dccc`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180007e01`
- `KERNEL32!GetProcAddress` at `0x180007e4a`
- `KERNEL32!GetProcAddress` at `0x180007e01`
- `KERNEL32!GetProcAddress` at `0x180007e4a`

## string_xrefs

- `0x180007df7`: `GetHostConfigurationFile_RetAddr`
- `0x180007e40`: `GetHostConfigurationFile`

## pseudocode

```c
__int64 __fastcall ShellShim_GetHostConfigurationFile(__int64 a1, int (*a2)(unsigned __int16 *, void *))
{
  HMODULE v2; // rbx
  void *retaddr; // [rsp+28h] [rbp+0h]

  v2 = 0;
  if ( !(_DWORD)g_shimImplStatus )
    InitShimImpl(a1, a2);
  if ( (_DWORD)g_shimImplStatus == 2 )
    v2 = g_hShimImplInst;
  if ( (_DWORD)g_shimImplStatus == 1 )
    return 2148734721LL;
  if ( (_DWORD)g_shimImplStatus == 3 )
    return GetHostConfigurationFile(a1, a2);
  if ( g_bShimImplDllUninitialized )
    return 2148734721LL;
  if ( g_pfGetHostConfigurationFile_RetAddr == (int (*)(unsigned __int16 *, unsigned __int64 *, void *))-1LL )
    g_pfGetHostConfigurationFile_RetAddr = (int (*)(unsigned __int16 *, unsigned __int64 *, void *))GetProcAddress(v2, "GetHostConfigurationFile_RetAddr");
  if ( g_pfGetHostConfigurationFile_RetAddr )
    return ((__int64 (__fastcall *)(__int64, int (*)(unsigned __int16 *, void *), void *))g_pfGetHostConfigurationFile_RetAddr)(
             a1,
             a2,
             retaddr);
  if ( g_pfGetHostConfigurationFile == (int (*)(unsigned __int16 *, unsigned __int64 *))-1LL )
    g_pfGetHostConfigurationFile = (int (*)(unsigned __int16 *, unsigned __int64 *))GetProcAddress(
                                                                                      v2,
                                                                                      "GetHostConfigurationFile");
  if ( !g_pfGetHostConfigurationFile )
    return 2148734721LL;
  else
    return ((__int64 (__fastcall *)(__int64, int (*)(unsigned __int16 *, void *)))g_pfGetHostConfigurationFile)(a1, a2);
}

```

## disassembly

```asm
0x180007d80  mov     [rsp+arg_0], rbx
0x180007d85  mov     [rsp+arg_8], rsi
0x180007d8a  push    rdi
0x180007d8b  sub     rsp, 20h
0x180007d8f  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x180007d95  xor     ebx, ebx
0x180007d97  mov     rdi, rdx
0x180007d9a  mov     rsi, rcx
0x180007d9d  test    eax, eax
0x180007d9f  jnz     short loc_180007DA6
0x180007da1  call    ?InitShimImpl@@YAXXZ; InitShimImpl(void)
0x180007da6  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x180007dac  cmp     eax, 2
0x180007daf  jnz     short loc_180007DB8
0x180007db1  mov     rbx, cs:?g_hShimImplInst@@3REAUHINSTANCE__@@EA; HINSTANCE__ * g_hShimImplInst
0x180007db8  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x180007dbe  cmp     eax, 1
0x180007dc1  jz      loc_180007E77
0x180007dc7  cmp     eax, 3
0x180007dca  jnz     short loc_180007DDC
0x180007dcc  mov     rdx, rdi
0x180007dcf  mov     rcx, rsi
0x180007dd2  call    GetHostConfigurationFile
0x180007dd7  jmp     loc_180007E7C
0x180007ddc  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180007de2  test    eax, eax
0x180007de4  jnz     loc_180007E77
0x180007dea  mov     rax, cs:?g_pfGetHostConfigurationFile_RetAddr@@3R6AJPEAGPEA_KPEAX@ZEA; long (*g_pfGetHostConfigurationFile_RetAddr)(ushort *,unsigned __int64 *,void *)
0x180007df1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007df5  jnz     short loc_180007E0E
0x180007df7  lea     rdx, aGethostconfigu_0; "GetHostConfigurationFile_RetAddr"
0x180007dfe  mov     rcx, rbx; hModule
0x180007e01  call    cs:__imp_GetProcAddress
0x180007e07  mov     cs:?g_pfGetHostConfigurationFile_RetAddr@@3R6AJPEAGPEA_KPEAX@ZEA, rax; long (*g_pfGetHostConfigurationFile_RetAddr)(ushort *,unsigned __int64 *,void *)
0x180007e0e  mov     rax, cs:?g_pfGetHostConfigurationFile_RetAddr@@3R6AJPEAGPEA_KPEAX@ZEA; long (*g_pfGetHostConfigurationFile_RetAddr)(ushort *,unsigned __int64 *,void *)
0x180007e15  test    rax, rax
0x180007e18  jz      short loc_180007E33
0x180007e1a  mov     rax, cs:?g_pfGetHostConfigurationFile_RetAddr@@3R6AJPEAGPEA_KPEAX@ZEA; long (*g_pfGetHostConfigurationFile_RetAddr)(ushort *,unsigned __int64 *,void *)
0x180007e21  mov     rdx, rdi
0x180007e24  mov     r8, [rsp+28h]
0x180007e29  mov     rcx, rsi
0x180007e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e31  jmp     short loc_180007E7C
0x180007e33  mov     rax, cs:?g_pfGetHostConfigurationFile@@3R6AJPEAGPEA_K@ZEA; long (*g_pfGetHostConfigurationFile)(ushort *,unsigned __int64 *)
0x180007e3a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007e3e  jnz     short loc_180007E57
0x180007e40  lea     rdx, aGethostconfigu_1; "GetHostConfigurationFile"
0x180007e47  mov     rcx, rbx; hModule
0x180007e4a  call    cs:__imp_GetProcAddress
0x180007e50  mov     cs:?g_pfGetHostConfigurationFile@@3R6AJPEAGPEA_K@ZEA, rax; long (*g_pfGetHostConfigurationFile)(ushort *,unsigned __int64 *)
0x180007e57  mov     rax, cs:?g_pfGetHostConfigurationFile@@3R6AJPEAGPEA_K@ZEA; long (*g_pfGetHostConfigurationFile)(ushort *,unsigned __int64 *)
0x180007e5e  test    rax, rax
0x180007e61  jz      short loc_180007E77
0x180007e63  mov     rax, cs:?g_pfGetHostConfigurationFile@@3R6AJPEAGPEA_K@ZEA; long (*g_pfGetHostConfigurationFile)(ushort *,unsigned __int64 *)
0x180007e6a  mov     rdx, rdi
0x180007e6d  mov     rcx, rsi
0x180007e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e75  jmp     short loc_180007E7C
0x180007e77  mov     eax, 80131701h
0x180007e7c  mov     rbx, [rsp+28h+arg_0]
0x180007e81  mov     rsi, [rsp+28h+arg_8]
0x180007e86  add     rsp, 20h
0x180007e8a  pop     rdi
0x180007e8b  retn
```
