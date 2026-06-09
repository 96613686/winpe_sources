# ShellShim_StrongNameTokenFromAssembly

- ea: `0x1800283e0`
- end: `0x180028522`
- name: `ShellShim_StrongNameTokenFromAssembly`
- size: `322`
- prototype: `BOOLEAN __stdcall(LPCWSTR wszFilePath, BYTE **ppbStrongNameToken, ULONG *pcbStrongNameToken)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001c10`
- `0x1800283e0`
- `0x18002a2e4`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180028456`
- `KERNEL32!GetProcAddress` at `0x18002849d`
- `KERNEL32!GetProcAddress` at `0x1800284eb`
- `KERNEL32!GetProcAddress` at `0x180028456`
- `KERNEL32!GetProcAddress` at `0x18002849d`
- `KERNEL32!GetProcAddress` at `0x1800284eb`

## string_xrefs

- `0x180028496`: `StrongNameTokenFromAssembly_RetAddr`
- `0x18002844f`: `StrongNameTokenFromAssembly`
- `0x1800284e4`: `StrongNameTokenFromAssembly`

## pseudocode

```c
BOOLEAN __stdcall ShellShim_StrongNameTokenFromAssembly(
        LPCWSTR wszFilePath,
        BYTE **ppbStrongNameToken,
        ULONG *pcbStrongNameToken)
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
    ProcAddress = (FARPROC)g_StrongNameTokenFromAssembly;
    if ( g_StrongNameTokenFromAssembly )
      return ((__int64 (__fastcall *)(LPCWSTR, BYTE **, ULONG *))ProcAddress)(
               wszFilePath,
               ppbStrongNameToken,
               pcbStrongNameToken);
    hModule = 0;
    if ( (int)GetRealStrongNameDll(&hModule) >= 0 )
    {
      ProcAddress = GetProcAddress(hModule, "StrongNameTokenFromAssembly");
      g_StrongNameTokenFromAssembly = (unsigned __int8 (*)(const unsigned __int16 *, unsigned __int8 **, unsigned int *))ProcAddress;
      if ( ProcAddress )
        return ((__int64 (__fastcall *)(LPCWSTR, BYTE **, ULONG *))ProcAddress)(
                 wszFilePath,
                 ppbStrongNameToken,
                 pcbStrongNameToken);
    }
    return 0;
  }
  if ( g_bShimImplDllUninitialized )
    return 0;
  if ( g_pfStrongNameTokenFromAssembly_RetAddr == (unsigned int (*)(const unsigned __int16 *, unsigned __int8 **, unsigned int *, void *))-1LL )
    g_pfStrongNameTokenFromAssembly_RetAddr = (unsigned int (*)(const unsigned __int16 *, unsigned __int8 **, unsigned int *, void *))GetProcAddress(hModule, "StrongNameTokenFromAssembly_RetAddr");
  if ( g_pfStrongNameTokenFromAssembly_RetAddr )
    return ((__int64 (__fastcall *)(LPCWSTR, BYTE **, ULONG *, void *))g_pfStrongNameTokenFromAssembly_RetAddr)(
             wszFilePath,
             ppbStrongNameToken,
             pcbStrongNameToken,
             retaddr);
  if ( g_pfStrongNameTokenFromAssembly == (unsigned int (*)(const unsigned __int16 *, unsigned __int8 **, unsigned int *))-1LL )
    g_pfStrongNameTokenFromAssembly = (unsigned int (*)(const unsigned __int16 *, unsigned __int8 **, unsigned int *))GetProcAddress(hModule, "StrongNameTokenFromAssembly");
  if ( !g_pfStrongNameTokenFromAssembly )
    return 0;
  return ((__int64 (__fastcall *)(LPCWSTR, BYTE **, ULONG *))g_pfStrongNameTokenFromAssembly)(
           wszFilePath,
           ppbStrongNameToken,
           pcbStrongNameToken);
}

```

## disassembly

```asm
0x1800283e0  mov     rax, rsp
0x1800283e3  mov     [rax+8], rbx
0x1800283e7  mov     [rax+10h], rsi
0x1800283eb  push    rdi
0x1800283ec  sub     rsp, 30h
0x1800283f0  mov     rsi, rcx
0x1800283f3  mov     qword ptr [rax+20h], 0
0x1800283fb  lea     rcx, [rax+20h]
0x1800283ff  mov     rbx, r8
0x180028402  mov     rdi, rdx
0x180028405  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x18002840a  cmp     eax, 1
0x18002840d  jz      short loc_180028468
0x18002840f  cmp     eax, 3
0x180028412  jnz     short loc_18002847A
0x180028414  mov     rax, cs:?g_StrongNameTokenFromAssembly@@3P6AEPEBGPEAPEAEPEAK@ZEA; uchar (*g_StrongNameTokenFromAssembly)(ushort const *,uchar * *,ulong *)
0x18002841b  test    rax, rax
0x18002841e  jz      short loc_180028433
0x180028420  mov     r8, rbx
0x180028423  mov     rdx, rdi
0x180028426  mov     rcx, rsi
0x180028429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002842e  movzx   eax, al
0x180028431  jmp     short loc_18002846A
0x180028433  lea     rcx, [rsp+38h+hModule]; HINSTANCE *
0x180028438  mov     [rsp+38h+hModule], 0
0x180028441  call    ?GetRealStrongNameDll@@YAJPEAPEAUHINSTANCE__@@@Z; GetRealStrongNameDll(HINSTANCE__ * *)
0x180028446  test    eax, eax
0x180028448  js      short loc_180028468
0x18002844a  mov     rcx, [rsp+38h+hModule]; hModule
0x18002844f  lea     rdx, aStrongnametoke_7; "StrongNameTokenFromAssembly"
0x180028456  call    cs:__imp_GetProcAddress
0x18002845c  mov     cs:?g_StrongNameTokenFromAssembly@@3P6AEPEBGPEAPEAEPEAK@ZEA, rax; uchar (*g_StrongNameTokenFromAssembly)(ushort const *,uchar * *,ulong *)
0x180028463  test    rax, rax
0x180028466  jnz     short loc_180028420
0x180028468  xor     eax, eax
0x18002846a  mov     rbx, [rsp+38h+arg_0]
0x18002846f  mov     rsi, [rsp+38h+arg_8]
0x180028474  add     rsp, 30h
0x180028478  pop     rdi
0x180028479  retn
0x18002847a  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180028480  test    eax, eax
0x180028482  jnz     short loc_180028468
0x180028484  mov     rax, cs:?g_pfStrongNameTokenFromAssembly_RetAddr@@3R6AKPEBGPEAPEAEPEAKPEAX@ZEA; ulong (*g_pfStrongNameTokenFromAssembly_RetAddr)(ushort const *,uchar * *,ulong *,void *)
0x18002848b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002848f  jnz     short loc_1800284AA
0x180028491  mov     rcx, [rsp+38h+hModule]; hModule
0x180028496  lea     rdx, aStrongnametoke_2; "StrongNameTokenFromAssembly_RetAddr"
0x18002849d  call    cs:__imp_GetProcAddress
0x1800284a3  mov     cs:?g_pfStrongNameTokenFromAssembly_RetAddr@@3R6AKPEBGPEAPEAEPEAKPEAX@ZEA, rax; ulong (*g_pfStrongNameTokenFromAssembly_RetAddr)(ushort const *,uchar * *,ulong *,void *)
0x1800284aa  mov     rax, cs:?g_pfStrongNameTokenFromAssembly_RetAddr@@3R6AKPEBGPEAPEAEPEAKPEAX@ZEA; ulong (*g_pfStrongNameTokenFromAssembly_RetAddr)(ushort const *,uchar * *,ulong *,void *)
0x1800284b1  test    rax, rax
0x1800284b4  jz      short loc_1800284D2
0x1800284b6  mov     rax, cs:?g_pfStrongNameTokenFromAssembly_RetAddr@@3R6AKPEBGPEAPEAEPEAKPEAX@ZEA; ulong (*g_pfStrongNameTokenFromAssembly_RetAddr)(ushort const *,uchar * *,ulong *,void *)
0x1800284bd  mov     r8, rbx
0x1800284c0  mov     r9, [rsp+38h]
0x1800284c5  mov     rdx, rdi
0x1800284c8  mov     rcx, rsi
0x1800284cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284d0  jmp     short loc_18002846A
0x1800284d2  mov     rax, cs:?g_pfStrongNameTokenFromAssembly@@3R6AKPEBGPEAPEAEPEAK@ZEA; ulong (*g_pfStrongNameTokenFromAssembly)(ushort const *,uchar * *,ulong *)
0x1800284d9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800284dd  jnz     short loc_1800284F8
0x1800284df  mov     rcx, [rsp+38h+hModule]; hModule
0x1800284e4  lea     rdx, aStrongnametoke_7; "StrongNameTokenFromAssembly"
0x1800284eb  call    cs:__imp_GetProcAddress
0x1800284f1  mov     cs:?g_pfStrongNameTokenFromAssembly@@3R6AKPEBGPEAPEAEPEAK@ZEA, rax; ulong (*g_pfStrongNameTokenFromAssembly)(ushort const *,uchar * *,ulong *)
0x1800284f8  mov     rax, cs:?g_pfStrongNameTokenFromAssembly@@3R6AKPEBGPEAPEAEPEAK@ZEA; ulong (*g_pfStrongNameTokenFromAssembly)(ushort const *,uchar * *,ulong *)
0x1800284ff  test    rax, rax
0x180028502  jz      loc_180028468
0x180028508  mov     rax, cs:?g_pfStrongNameTokenFromAssembly@@3R6AKPEBGPEAPEAEPEAK@ZEA; ulong (*g_pfStrongNameTokenFromAssembly)(ushort const *,uchar * *,ulong *)
0x18002850f  mov     r8, rbx
0x180028512  mov     rdx, rdi
0x180028515  mov     rcx, rsi
0x180028518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002851d  jmp     loc_18002846A
```
