# ShellShim_DllGetClassObject

- ea: `0x180001010`
- end: `0x18000112c`
- name: `ShellShim_DllGetClassObject`
- size: `284`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001010`
- `0x180002a90`
- `0x18002d134`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800010de`
- `KERNEL32!GetProcAddress` at `0x180001113`
- `KERNEL32!GetProcAddress` at `0x1800010de`
- `KERNEL32!GetProcAddress` at `0x180001113`

## string_xrefs

- `0x1800010d4`: `DllGetClassObject_RetAddr`
- `0x180001109`: `DllGetClassObject`

## pseudocode

```c
HRESULT __stdcall ShellShim_DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HMODULE v3; // rbp
  void *retaddr; // [rsp+58h] [rbp+0h]

  v3 = 0;
  if ( !(_DWORD)g_shimImplStatus )
    InitShimImpl();
  if ( (_DWORD)g_shimImplStatus == 2 )
    v3 = g_hShimImplInst;
  if ( (_DWORD)g_shimImplStatus != 1 )
  {
    if ( (_DWORD)g_shimImplStatus == 3 )
      return DllGetClassObject(rclsid, riid, ppv);
    if ( !g_bShimImplDllUninitialized )
    {
      if ( g_pfDllGetClassObject_RetAddr == (int (*)(const struct _GUID *, const struct _GUID *, void **, void *))-1LL )
        g_pfDllGetClassObject_RetAddr = (int (*)(const struct _GUID *, const struct _GUID *, void **, void *))GetProcAddress(v3, "DllGetClassObject_RetAddr");
      if ( g_pfDllGetClassObject_RetAddr )
        return ((__int64 (__fastcall *)(const IID *const, const IID *const, LPVOID *, void *))g_pfDllGetClassObject_RetAddr)(
                 rclsid,
                 riid,
                 ppv,
                 retaddr);
      if ( g_pfDllGetClassObject == (int (*)(const struct _GUID *, const struct _GUID *, void **))-1LL )
        g_pfDllGetClassObject = (int (*)(const struct _GUID *, const struct _GUID *, void **))GetProcAddress(
                                                                                                v3,
                                                                                                "DllGetClassObject");
      if ( g_pfDllGetClassObject )
        return ((__int64 (__fastcall *)(const IID *const, const IID *const, LPVOID *))g_pfDllGetClassObject)(
                 rclsid,
                 riid,
                 ppv);
    }
  }
  return -2146232575;
}

```

## disassembly

```asm
0x180001010  push    rbx
0x180001012  push    rbp
0x180001013  push    rsi
0x180001014  push    rdi
0x180001015  sub     rsp, 38h
0x180001019  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x18000101f  xor     ebp, ebp
0x180001021  mov     rbx, r8
0x180001024  mov     rdi, rdx
0x180001027  mov     rsi, rcx
0x18000102a  test    eax, eax
0x18000102c  jz      loc_1800010BA
0x180001032  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x180001038  cmp     eax, 2
0x18000103b  jnz     short loc_180001044
0x18000103d  mov     rbp, cs:?g_hShimImplInst@@3REAUHINSTANCE__@@EA; HINSTANCE__ * g_hShimImplInst
0x180001044  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x18000104a  cmp     eax, 1
0x18000104d  jz      loc_180001125
0x180001053  cmp     eax, 3
0x180001056  jz      short loc_1800010C4
0x180001058  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x18000105e  test    eax, eax
0x180001060  jnz     loc_180001125
0x180001066  mov     rax, cs:?g_pfDllGetClassObject_RetAddr@@3R6AJAEBU_GUID@@0PEAPEAXPEAX@ZEA; long (*g_pfDllGetClassObject_RetAddr)(_GUID const &,_GUID const &,void * *,void *)
0x18000106d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001071  jz      short loc_1800010D4
0x180001073  mov     rax, cs:?g_pfDllGetClassObject_RetAddr@@3R6AJAEBU_GUID@@0PEAPEAXPEAX@ZEA; long (*g_pfDllGetClassObject_RetAddr)(_GUID const &,_GUID const &,void * *,void *)
0x18000107a  test    rax, rax
0x18000107d  jnz     short loc_1800010ED
0x18000107f  mov     rax, cs:?g_pfDllGetClassObject@@3R6AJAEBU_GUID@@0PEAPEAX@ZEA; long (*g_pfDllGetClassObject)(_GUID const &,_GUID const &,void * *)
0x180001086  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000108a  jz      short loc_180001109
0x18000108c  mov     rax, cs:?g_pfDllGetClassObject@@3R6AJAEBU_GUID@@0PEAPEAX@ZEA; long (*g_pfDllGetClassObject)(_GUID const &,_GUID const &,void * *)
0x180001093  test    rax, rax
0x180001096  jz      loc_180001125
0x18000109c  mov     rax, cs:?g_pfDllGetClassObject@@3R6AJAEBU_GUID@@0PEAPEAX@ZEA; long (*g_pfDllGetClassObject)(_GUID const &,_GUID const &,void * *)
0x1800010a3  mov     r8, rbx
0x1800010a6  mov     rdx, rdi
0x1800010a9  mov     rcx, rsi
0x1800010ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010b1  add     rsp, 38h
0x1800010b5  pop     rdi
0x1800010b6  pop     rsi
0x1800010b7  pop     rbp
0x1800010b8  pop     rbx
0x1800010b9  retn
0x1800010ba  call    ?InitShimImpl@@YAXXZ; InitShimImpl(void)
0x1800010bf  jmp     loc_180001032
0x1800010c4  mov     r8, rbx; ppv
0x1800010c7  mov     rdx, rdi; riid
0x1800010ca  mov     rcx, rsi; rclsid
0x1800010cd  call    DllGetClassObject
0x1800010d2  jmp     short loc_1800010B1
0x1800010d4  lea     rdx, ProcName; "DllGetClassObject_RetAddr"
0x1800010db  mov     rcx, rbp; hModule
0x1800010de  call    cs:__imp_GetProcAddress
0x1800010e4  mov     cs:?g_pfDllGetClassObject_RetAddr@@3R6AJAEBU_GUID@@0PEAPEAXPEAX@ZEA, rax; long (*g_pfDllGetClassObject_RetAddr)(_GUID const &,_GUID const &,void * *,void *)
0x1800010eb  jmp     short loc_180001073
0x1800010ed  mov     rax, cs:?g_pfDllGetClassObject_RetAddr@@3R6AJAEBU_GUID@@0PEAPEAXPEAX@ZEA; long (*g_pfDllGetClassObject_RetAddr)(_GUID const &,_GUID const &,void * *,void *)
0x1800010f4  mov     r8, rbx
0x1800010f7  mov     r9, [rsp+58h]
0x1800010fc  mov     rdx, rdi
0x1800010ff  mov     rcx, rsi
0x180001102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001107  jmp     short loc_1800010B1
0x180001109  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x180001110  mov     rcx, rbp; hModule
0x180001113  call    cs:__imp_GetProcAddress
0x180001119  mov     cs:?g_pfDllGetClassObject@@3R6AJAEBU_GUID@@0PEAPEAX@ZEA, rax; long (*g_pfDllGetClassObject)(_GUID const &,_GUID const &,void * *)
0x180001120  jmp     loc_18000108C
0x180001125  mov     eax, 80131701h
0x18000112a  jmp     short loc_1800010B1
```
