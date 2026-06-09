# ShellShim_GetRequestedRuntimeVersionForCLSID

- ea: `0x1800257e0`
- end: `0x18002590b`
- name: `ShellShim_GetRequestedRuntimeVersionForCLSID`
- size: `299`
- prototype: `__int64 __fastcall(struct _GUID *, wchar_t *Destination, rsize_t SizeInWords, __int64, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001c10`
- `0x1800257e0`
- `0x18002e23c`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002585e`
- `KERNEL32!GetProcAddress` at `0x1800258bf`
- `KERNEL32!GetProcAddress` at `0x18002585e`
- `KERNEL32!GetProcAddress` at `0x1800258bf`

## string_xrefs

- `0x180025857`: `GetRequestedRuntimeVersionForCLSID_RetAddr`
- `0x1800258b8`: `GetRequestedRuntimeVersionForCLSID`

## pseudocode

```c
__int64 __fastcall ShellShim_GetRequestedRuntimeVersionForCLSID(
        struct _GUID *a1,
        wchar_t *Destination,
        rsize_t SizeInWords,
        __int64 a4,
        int a5)
{
  unsigned int v7; // edi
  int ShimImpl; // eax
  HMODULE hModule[7]; // [rsp+40h] [rbp-38h] BYREF
  void *retaddr; // [rsp+78h] [rbp+0h]

  hModule[0] = 0;
  v7 = SizeInWords;
  ShimImpl = GetShimImpl(hModule);
  if ( ShimImpl == 1 )
    return 2148734721LL;
  if ( ShimImpl == 3 )
    return GetRequestedRuntimeVersionForCLSID(a1, Destination, v7, a5);
  if ( g_bShimImplDllUninitialized )
    return 2148734721LL;
  if ( g_pfGetRequestedRuntimeVersionForCLSID_RetAddr == (int (__high *)(const struct _GUID *, unsigned __int16 *, unsigned int, unsigned int *, enum __MIDL___MIDL_itf_mscoree_0000_0000_0003, void *))-1LL )
    g_pfGetRequestedRuntimeVersionForCLSID_RetAddr = (int (__high *)(const struct _GUID *, unsigned __int16 *, unsigned int, unsigned int *, enum __MIDL___MIDL_itf_mscoree_0000_0000_0003, void *))GetProcAddress(hModule[0], "GetRequestedRuntimeVersionForCLSID_RetAddr");
  if ( g_pfGetRequestedRuntimeVersionForCLSID_RetAddr )
    return ((__int64 (__fastcall *)(struct _GUID *, wchar_t *, _QWORD, __int64, int, void *))g_pfGetRequestedRuntimeVersionForCLSID_RetAddr)(
             a1,
             Destination,
             v7,
             a4,
             a5,
             retaddr);
  if ( g_pfGetRequestedRuntimeVersionForCLSID == (int (__high *)(const struct _GUID *, unsigned __int16 *, unsigned int, unsigned int *, enum __MIDL___MIDL_itf_mscoree_0000_0000_0003))-1LL )
    g_pfGetRequestedRuntimeVersionForCLSID = (int (__high *)(const struct _GUID *, unsigned __int16 *, unsigned int, unsigned int *, enum __MIDL___MIDL_itf_mscoree_0000_0000_0003))GetProcAddress(hModule[0], "GetRequestedRuntimeVersionForCLSID");
  if ( !g_pfGetRequestedRuntimeVersionForCLSID )
    return 2148734721LL;
  else
    return ((__int64 (__fastcall *)(struct _GUID *, wchar_t *, _QWORD, __int64, int))g_pfGetRequestedRuntimeVersionForCLSID)(
             a1,
             Destination,
             v7,
             a4,
             a5);
}

```

## disassembly

```asm
0x1800257e0  push    rbx
0x1800257e2  push    rbp
0x1800257e3  push    rsi
0x1800257e4  push    rdi
0x1800257e5  sub     rsp, 58h
0x1800257e9  mov     rbp, rcx
0x1800257ec  mov     [rsp+78h+hModule], 0
0x1800257f5  lea     rcx, [rsp+78h+hModule]
0x1800257fa  mov     rbx, r9
0x1800257fd  mov     edi, r8d
0x180025800  mov     rsi, rdx
0x180025803  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180025808  cmp     eax, 1
0x18002580b  jz      loc_1800258FD
0x180025811  cmp     eax, 3
0x180025814  jnz     short loc_180025837
0x180025816  mov     eax, [rsp+78h+arg_20]
0x18002581d  mov     r9, rbx
0x180025820  mov     r8d, edi; SizeInWords
0x180025823  mov     [rsp+78h+var_58], eax; int
0x180025827  mov     rdx, rsi; Destination
0x18002582a  mov     rcx, rbp; struct _GUID *
0x18002582d  call    GetRequestedRuntimeVersionForCLSID
0x180025832  jmp     loc_180025902
0x180025837  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x18002583d  test    eax, eax
0x18002583f  jnz     loc_1800258FD
0x180025845  mov     rax, cs:?g_pfGetRequestedRuntimeVersionForCLSID_RetAddr@@3R6AJAEBU_GUID@@PEAGKPEAKW4__MIDL___MIDL_itf_mscoree_0000_0000_0003@@PEAX@ZEA; long (*g_pfGetRequestedRuntimeVersionForCLSID_RetAddr)(_GUID const &,ushort *,ulong,ulong *,__MIDL___MIDL_itf_mscoree_0000_0000_0003,void *)
0x18002584c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025850  jnz     short loc_18002586B
0x180025852  mov     rcx, [rsp+78h+hModule]; hModule
0x180025857  lea     rdx, aGetrequestedru_6; "GetRequestedRuntimeVersionForCLSID_RetA"...
0x18002585e  call    cs:__imp_GetProcAddress
0x180025864  mov     cs:?g_pfGetRequestedRuntimeVersionForCLSID_RetAddr@@3R6AJAEBU_GUID@@PEAGKPEAKW4__MIDL___MIDL_itf_mscoree_0000_0000_0003@@PEAX@ZEA, rax; long (*g_pfGetRequestedRuntimeVersionForCLSID_RetAddr)(_GUID const &,ushort *,ulong,ulong *,__MIDL___MIDL_itf_mscoree_0000_0000_0003,void *)
0x18002586b  mov     rax, cs:?g_pfGetRequestedRuntimeVersionForCLSID_RetAddr@@3R6AJAEBU_GUID@@PEAGKPEAKW4__MIDL___MIDL_itf_mscoree_0000_0000_0003@@PEAX@ZEA; long (*g_pfGetRequestedRuntimeVersionForCLSID_RetAddr)(_GUID const &,ushort *,ulong,ulong *,__MIDL___MIDL_itf_mscoree_0000_0000_0003,void *)
0x180025872  test    rax, rax
0x180025875  jz      short loc_1800258A6
0x180025877  mov     rax, cs:?g_pfGetRequestedRuntimeVersionForCLSID_RetAddr@@3R6AJAEBU_GUID@@PEAGKPEAKW4__MIDL___MIDL_itf_mscoree_0000_0000_0003@@PEAX@ZEA; long (*g_pfGetRequestedRuntimeVersionForCLSID_RetAddr)(_GUID const &,ushort *,ulong,ulong *,__MIDL___MIDL_itf_mscoree_0000_0000_0003,void *)
0x18002587e  mov     r9, rbx
0x180025881  mov     rcx, [rsp+78h]
0x180025886  mov     r8d, edi
0x180025889  mov     [rsp+78h+var_50], rcx
0x18002588e  mov     rdx, rsi
0x180025891  mov     ecx, [rsp+78h+arg_20]
0x180025898  mov     [rsp+78h+var_58], ecx
0x18002589c  mov     rcx, rbp
0x18002589f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258a4  jmp     short loc_180025902
0x1800258a6  mov     rax, cs:?g_pfGetRequestedRuntimeVersionForCLSID@@3R6AJAEBU_GUID@@PEAGKPEAKW4__MIDL___MIDL_itf_mscoree_0000_0000_0003@@@ZEA; long (*g_pfGetRequestedRuntimeVersionForCLSID)(_GUID const &,ushort *,ulong,ulong *,__MIDL___MIDL_itf_mscoree_0000_0000_0003)
0x1800258ad  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800258b1  jnz     short loc_1800258CC
0x1800258b3  mov     rcx, [rsp+78h+hModule]; hModule
0x1800258b8  lea     rdx, aGetrequestedru_4; "GetRequestedRuntimeVersionForCLSID"
0x1800258bf  call    cs:__imp_GetProcAddress
0x1800258c5  mov     cs:?g_pfGetRequestedRuntimeVersionForCLSID@@3R6AJAEBU_GUID@@PEAGKPEAKW4__MIDL___MIDL_itf_mscoree_0000_0000_0003@@@ZEA, rax; long (*g_pfGetRequestedRuntimeVersionForCLSID)(_GUID const &,ushort *,ulong,ulong *,__MIDL___MIDL_itf_mscoree_0000_0000_0003)
0x1800258cc  mov     rax, cs:?g_pfGetRequestedRuntimeVersionForCLSID@@3R6AJAEBU_GUID@@PEAGKPEAKW4__MIDL___MIDL_itf_mscoree_0000_0000_0003@@@ZEA; long (*g_pfGetRequestedRuntimeVersionForCLSID)(_GUID const &,ushort *,ulong,ulong *,__MIDL___MIDL_itf_mscoree_0000_0000_0003)
0x1800258d3  test    rax, rax
0x1800258d6  jz      short loc_1800258FD
0x1800258d8  mov     ecx, [rsp+78h+arg_20]
0x1800258df  mov     r9, rbx
0x1800258e2  mov     rax, cs:?g_pfGetRequestedRuntimeVersionForCLSID@@3R6AJAEBU_GUID@@PEAGKPEAKW4__MIDL___MIDL_itf_mscoree_0000_0000_0003@@@ZEA; long (*g_pfGetRequestedRuntimeVersionForCLSID)(_GUID const &,ushort *,ulong,ulong *,__MIDL___MIDL_itf_mscoree_0000_0000_0003)
0x1800258e9  mov     r8d, edi
0x1800258ec  mov     [rsp+78h+var_58], ecx
0x1800258f0  mov     rdx, rsi
0x1800258f3  mov     rcx, rbp
0x1800258f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258fb  jmp     short loc_180025902
0x1800258fd  mov     eax, 80131701h
0x180025902  add     rsp, 58h
0x180025906  pop     rdi
0x180025907  pop     rsi
0x180025908  pop     rbp
0x180025909  pop     rbx
0x18002590a  retn
```
