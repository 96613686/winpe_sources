# ShellShim_CreateConfigStream

- ea: `0x180001280`
- end: `0x1800013a5`
- name: `ShellShim_CreateConfigStream`
- size: `293`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPSTREAM *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180001280`
- `0x180002a90`
- `0x1800303ec`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800012f4`
- `KERNEL32!GetProcAddress` at `0x18000137f`
- `KERNEL32!GetProcAddress` at `0x1800012f4`
- `KERNEL32!GetProcAddress` at `0x18000137f`

## string_xrefs

- `0x1800012ea`: `CreateConfigStream_RetAddr`
- `0x180001375`: `CreateConfigStream`

## pseudocode

```c
__int64 __fastcall ShellShim_CreateConfigStream(LPCWSTR lpFileName, LPSTREAM *a2)
{
  HMODULE v2; // rbx
  void *retaddr; // [rsp+28h] [rbp+0h]

  v2 = 0;
  if ( !(_DWORD)g_shimImplStatus )
    InitShimImpl((__int64)lpFileName, (int (*)(unsigned __int16 *, void *))a2);
  if ( (_DWORD)g_shimImplStatus == 2 )
    v2 = g_hShimImplInst;
  if ( (_DWORD)g_shimImplStatus == 1 )
    return 2148734721LL;
  if ( (_DWORD)g_shimImplStatus != 3 )
  {
    if ( !g_bShimImplDllUninitialized )
    {
      if ( g_pfCreateConfigStream_RetAddr == (int (*)(const unsigned __int16 *, struct IStream **, void *))-1LL )
        g_pfCreateConfigStream_RetAddr = (int (*)(const unsigned __int16 *, struct IStream **, void *))GetProcAddress(v2, "CreateConfigStream_RetAddr");
      if ( g_pfCreateConfigStream_RetAddr )
        return ((__int64 (__fastcall *)(LPCWSTR, LPSTREAM *, void *))g_pfCreateConfigStream_RetAddr)(
                 lpFileName,
                 a2,
                 retaddr);
      if ( g_pfCreateConfigStream == (int (*)(const unsigned __int16 *, struct IStream **))-1LL )
        g_pfCreateConfigStream = (int (*)(const unsigned __int16 *, struct IStream **))GetProcAddress(
                                                                                         v2,
                                                                                         "CreateConfigStream");
      if ( g_pfCreateConfigStream )
        return ((__int64 (__fastcall *)(LPCWSTR, LPSTREAM *))g_pfCreateConfigStream)(lpFileName, a2);
    }
    return 2148734721LL;
  }
  return CreateConfigStream(lpFileName, a2);
}

```

## disassembly

```asm
0x180001280  mov     [rsp+arg_0], rbx
0x180001285  mov     [rsp+arg_8], rsi
0x18000128a  push    rdi
0x18000128b  sub     rsp, 20h
0x18000128f  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x180001295  xor     ebx, ebx
0x180001297  mov     rdi, rdx
0x18000129a  mov     rsi, rcx
0x18000129d  test    eax, eax
0x18000129f  jz      loc_18000138E
0x1800012a5  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x1800012ab  cmp     eax, 2
0x1800012ae  jnz     short loc_1800012B7
0x1800012b0  mov     rbx, cs:?g_hShimImplInst@@3REAUHINSTANCE__@@EA; HINSTANCE__ * g_hShimImplInst
0x1800012b7  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x1800012bd  cmp     eax, 1
0x1800012c0  jz      loc_18000136E
0x1800012c6  cmp     eax, 3
0x1800012c9  jz      loc_180001398
0x1800012cf  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x1800012d5  test    eax, eax
0x1800012d7  jnz     loc_18000136E
0x1800012dd  mov     rax, cs:?g_pfCreateConfigStream_RetAddr@@3R6AJPEBGPEAPEAUIStream@@PEAX@ZEA; long (*g_pfCreateConfigStream_RetAddr)(ushort const *,IStream * *,void *)
0x1800012e4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800012e8  jnz     short loc_180001301
0x1800012ea  lea     rdx, aCreateconfigst_0; "CreateConfigStream_RetAddr"
0x1800012f1  mov     rcx, rbx; hModule
0x1800012f4  call    cs:__imp_GetProcAddress
0x1800012fa  mov     cs:?g_pfCreateConfigStream_RetAddr@@3R6AJPEBGPEAPEAUIStream@@PEAX@ZEA, rax; long (*g_pfCreateConfigStream_RetAddr)(ushort const *,IStream * *,void *)
0x180001301  mov     rax, cs:?g_pfCreateConfigStream_RetAddr@@3R6AJPEBGPEAPEAUIStream@@PEAX@ZEA; long (*g_pfCreateConfigStream_RetAddr)(ushort const *,IStream * *,void *)
0x180001308  test    rax, rax
0x18000130b  jnz     short loc_180001348
0x18000130d  mov     rax, cs:?g_pfCreateConfigStream@@3R6AJPEBGPEAPEAUIStream@@@ZEA; long (*g_pfCreateConfigStream)(ushort const *,IStream * *)
0x180001314  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001318  jz      short loc_180001375
0x18000131a  mov     rax, cs:?g_pfCreateConfigStream@@3R6AJPEBGPEAPEAUIStream@@@ZEA; long (*g_pfCreateConfigStream)(ushort const *,IStream * *)
0x180001321  test    rax, rax
0x180001324  jz      short loc_18000136E
0x180001326  mov     rax, cs:?g_pfCreateConfigStream@@3R6AJPEBGPEAPEAUIStream@@@ZEA; long (*g_pfCreateConfigStream)(ushort const *,IStream * *)
0x18000132d  mov     rdx, rdi
0x180001330  mov     rcx, rsi
0x180001333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001338  mov     rbx, [rsp+28h+arg_0]
0x18000133d  mov     rsi, [rsp+28h+arg_8]
0x180001342  add     rsp, 20h
0x180001346  pop     rdi
0x180001347  retn
0x180001348  mov     rax, cs:?g_pfCreateConfigStream_RetAddr@@3R6AJPEBGPEAPEAUIStream@@PEAX@ZEA; long (*g_pfCreateConfigStream_RetAddr)(ushort const *,IStream * *,void *)
0x18000134f  mov     rdx, rdi
0x180001352  mov     r8, [rsp+28h]
0x180001357  mov     rcx, rsi
0x18000135a  mov     rbx, [rsp+28h+arg_0]
0x18000135f  mov     rsi, [rsp+28h+arg_8]
0x180001364  add     rsp, 20h
0x180001368  pop     rdi
0x180001369  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000136e  mov     eax, 80131701h
0x180001373  jmp     short loc_180001338
0x180001375  lea     rdx, aCreateconfigst_1; "CreateConfigStream"
0x18000137c  mov     rcx, rbx; hModule
0x18000137f  call    cs:__imp_GetProcAddress
0x180001385  mov     cs:?g_pfCreateConfigStream@@3R6AJPEBGPEAPEAUIStream@@@ZEA, rax; long (*g_pfCreateConfigStream)(ushort const *,IStream * *)
0x18000138c  jmp     short loc_18000131A
0x18000138e  call    ?InitShimImpl@@YAXXZ; InitShimImpl(void)
0x180001393  jmp     loc_1800012A5
0x180001398  mov     rdx, rdi; LPSTREAM *
0x18000139b  mov     rcx, rsi; lpFileName
0x18000139e  call    CreateConfigStream
0x1800013a3  jmp     short loc_180001338
```
