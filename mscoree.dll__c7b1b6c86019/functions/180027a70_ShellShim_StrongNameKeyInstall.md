# ShellShim_StrongNameKeyInstall

- ea: `0x180027a70`
- end: `0x180027bb2`
- name: `ShellShim_StrongNameKeyInstall`
- size: `322`
- prototype: `BOOLEAN __stdcall(LPCWSTR wszKeyContainer, BYTE *pbKeyBlob, ULONG cbKeyBlob)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x180001c10`
- `0x180027a70`
- `0x18002a2e4`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180027ae6`
- `KERNEL32!GetProcAddress` at `0x180027b2d`
- `KERNEL32!GetProcAddress` at `0x180027b7b`
- `KERNEL32!GetProcAddress` at `0x180027ae6`
- `KERNEL32!GetProcAddress` at `0x180027b2d`
- `KERNEL32!GetProcAddress` at `0x180027b7b`

## string_xrefs

- `0x180027b26`: `StrongNameKeyInstall_RetAddr`
- `0x180027adf`: `StrongNameKeyInstall`
- `0x180027b74`: `StrongNameKeyInstall`

## pseudocode

```c
BOOLEAN __stdcall ShellShim_StrongNameKeyInstall(LPCWSTR wszKeyContainer, BYTE *pbKeyBlob, ULONG cbKeyBlob)
{
  int ShimImpl; // eax
  FARPROC ProcAddress; // rax
  void *retaddr; // [rsp+38h] [rbp+0h]
  HMODULE hModule; // [rsp+58h] [rbp+20h] BYREF

  hModule = 0;
  ShimImpl = GetShimImpl(&hModule);
  if ( ShimImpl == 1 )
    return 0;
  if ( ShimImpl == 3 )
  {
    ProcAddress = (FARPROC)g_StrongNameKeyInstall;
    if ( g_StrongNameKeyInstall )
      return ((__int64 (__fastcall *)(LPCWSTR, BYTE *, _QWORD))ProcAddress)(wszKeyContainer, pbKeyBlob, cbKeyBlob);
    hModule = 0;
    if ( (int)GetRealStrongNameDll(&hModule) >= 0 )
    {
      ProcAddress = GetProcAddress(hModule, "StrongNameKeyInstall");
      g_StrongNameKeyInstall = (unsigned __int8 (*)(const unsigned __int16 *, unsigned __int8 *, unsigned int))ProcAddress;
      if ( ProcAddress )
        return ((__int64 (__fastcall *)(LPCWSTR, BYTE *, _QWORD))ProcAddress)(wszKeyContainer, pbKeyBlob, cbKeyBlob);
    }
    return 0;
  }
  if ( g_bShimImplDllUninitialized )
    return 0;
  if ( g_pfStrongNameKeyInstall_RetAddr == (unsigned int (*)(const unsigned __int16 *, unsigned __int8 *, unsigned int, void *))-1LL )
    g_pfStrongNameKeyInstall_RetAddr = (unsigned int (*)(const unsigned __int16 *, unsigned __int8 *, unsigned int, void *))GetProcAddress(hModule, "StrongNameKeyInstall_RetAddr");
  if ( g_pfStrongNameKeyInstall_RetAddr )
    return ((__int64 (__fastcall *)(LPCWSTR, BYTE *, _QWORD, void *))g_pfStrongNameKeyInstall_RetAddr)(
             wszKeyContainer,
             pbKeyBlob,
             cbKeyBlob,
             retaddr);
  if ( g_pfStrongNameKeyInstall == (unsigned int (*)(const unsigned __int16 *, unsigned __int8 *, unsigned int))-1LL )
    g_pfStrongNameKeyInstall = (unsigned int (*)(const unsigned __int16 *, unsigned __int8 *, unsigned int))GetProcAddress(hModule, "StrongNameKeyInstall");
  if ( !g_pfStrongNameKeyInstall )
    return 0;
  return ((__int64 (__fastcall *)(LPCWSTR, BYTE *, _QWORD))g_pfStrongNameKeyInstall)(
           wszKeyContainer,
           pbKeyBlob,
           cbKeyBlob);
}

```

## disassembly

```asm
0x180027a70  mov     rax, rsp
0x180027a73  mov     [rax+8], rbx
0x180027a77  mov     [rax+10h], rsi
0x180027a7b  push    rdi
0x180027a7c  sub     rsp, 30h
0x180027a80  mov     rsi, rcx
0x180027a83  mov     qword ptr [rax+20h], 0
0x180027a8b  lea     rcx, [rax+20h]
0x180027a8f  mov     ebx, r8d
0x180027a92  mov     rdi, rdx
0x180027a95  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180027a9a  cmp     eax, 1
0x180027a9d  jz      short loc_180027AF8
0x180027a9f  cmp     eax, 3
0x180027aa2  jnz     short loc_180027B0A
0x180027aa4  mov     rax, cs:?g_StrongNameKeyInstall@@3P6AEPEBGPEAEK@ZEA; uchar (*g_StrongNameKeyInstall)(ushort const *,uchar *,ulong)
0x180027aab  test    rax, rax
0x180027aae  jz      short loc_180027AC3
0x180027ab0  mov     r8d, ebx
0x180027ab3  mov     rdx, rdi
0x180027ab6  mov     rcx, rsi
0x180027ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027abe  movzx   eax, al
0x180027ac1  jmp     short loc_180027AFA
0x180027ac3  lea     rcx, [rsp+38h+hModule]; HINSTANCE *
0x180027ac8  mov     [rsp+38h+hModule], 0
0x180027ad1  call    ?GetRealStrongNameDll@@YAJPEAPEAUHINSTANCE__@@@Z; GetRealStrongNameDll(HINSTANCE__ * *)
0x180027ad6  test    eax, eax
0x180027ad8  js      short loc_180027AF8
0x180027ada  mov     rcx, [rsp+38h+hModule]; hModule
0x180027adf  lea     rdx, aStrongnamekeyi_0; "StrongNameKeyInstall"
0x180027ae6  call    cs:__imp_GetProcAddress
0x180027aec  mov     cs:?g_StrongNameKeyInstall@@3P6AEPEBGPEAEK@ZEA, rax; uchar (*g_StrongNameKeyInstall)(ushort const *,uchar *,ulong)
0x180027af3  test    rax, rax
0x180027af6  jnz     short loc_180027AB0
0x180027af8  xor     eax, eax
0x180027afa  mov     rbx, [rsp+38h+arg_0]
0x180027aff  mov     rsi, [rsp+38h+arg_8]
0x180027b04  add     rsp, 30h
0x180027b08  pop     rdi
0x180027b09  retn
0x180027b0a  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180027b10  test    eax, eax
0x180027b12  jnz     short loc_180027AF8
0x180027b14  mov     rax, cs:?g_pfStrongNameKeyInstall_RetAddr@@3R6AKPEBGPEAEKPEAX@ZEA; ulong (*g_pfStrongNameKeyInstall_RetAddr)(ushort const *,uchar *,ulong,void *)
0x180027b1b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180027b1f  jnz     short loc_180027B3A
0x180027b21  mov     rcx, [rsp+38h+hModule]; hModule
0x180027b26  lea     rdx, aStrongnamekeyi_1; "StrongNameKeyInstall_RetAddr"
0x180027b2d  call    cs:__imp_GetProcAddress
0x180027b33  mov     cs:?g_pfStrongNameKeyInstall_RetAddr@@3R6AKPEBGPEAEKPEAX@ZEA, rax; ulong (*g_pfStrongNameKeyInstall_RetAddr)(ushort const *,uchar *,ulong,void *)
0x180027b3a  mov     rax, cs:?g_pfStrongNameKeyInstall_RetAddr@@3R6AKPEBGPEAEKPEAX@ZEA; ulong (*g_pfStrongNameKeyInstall_RetAddr)(ushort const *,uchar *,ulong,void *)
0x180027b41  test    rax, rax
0x180027b44  jz      short loc_180027B62
0x180027b46  mov     rax, cs:?g_pfStrongNameKeyInstall_RetAddr@@3R6AKPEBGPEAEKPEAX@ZEA; ulong (*g_pfStrongNameKeyInstall_RetAddr)(ushort const *,uchar *,ulong,void *)
0x180027b4d  mov     r8d, ebx
0x180027b50  mov     r9, [rsp+38h]
0x180027b55  mov     rdx, rdi
0x180027b58  mov     rcx, rsi
0x180027b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b60  jmp     short loc_180027AFA
0x180027b62  mov     rax, cs:?g_pfStrongNameKeyInstall@@3R6AKPEBGPEAEK@ZEA; ulong (*g_pfStrongNameKeyInstall)(ushort const *,uchar *,ulong)
0x180027b69  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180027b6d  jnz     short loc_180027B88
0x180027b6f  mov     rcx, [rsp+38h+hModule]; hModule
0x180027b74  lea     rdx, aStrongnamekeyi_0; "StrongNameKeyInstall"
0x180027b7b  call    cs:__imp_GetProcAddress
0x180027b81  mov     cs:?g_pfStrongNameKeyInstall@@3R6AKPEBGPEAEK@ZEA, rax; ulong (*g_pfStrongNameKeyInstall)(ushort const *,uchar *,ulong)
0x180027b88  mov     rax, cs:?g_pfStrongNameKeyInstall@@3R6AKPEBGPEAEK@ZEA; ulong (*g_pfStrongNameKeyInstall)(ushort const *,uchar *,ulong)
0x180027b8f  test    rax, rax
0x180027b92  jz      loc_180027AF8
0x180027b98  mov     rax, cs:?g_pfStrongNameKeyInstall@@3R6AKPEBGPEAEK@ZEA; ulong (*g_pfStrongNameKeyInstall)(ushort const *,uchar *,ulong)
0x180027b9f  mov     r8d, ebx
0x180027ba2  mov     rdx, rdi
0x180027ba5  mov     rcx, rsi
0x180027ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bad  jmp     loc_180027AFA
```
