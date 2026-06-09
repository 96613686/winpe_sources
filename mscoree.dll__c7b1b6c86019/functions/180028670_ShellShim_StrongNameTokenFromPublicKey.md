# ShellShim_StrongNameTokenFromPublicKey

- ea: `0x180028670`
- end: `0x180028773`
- name: `ShellShim_StrongNameTokenFromPublicKey`
- size: `259`
- prototype: `BOOLEAN __stdcall(BYTE *pbPublicKeyBlob, ULONG cbPublicKeyBlob, BYTE **ppbStrongNameToken, ULONG *pcbStrongNameToken)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001c10`
- `0x180028670`
- `0x18002ee44`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800286e1`
- `KERNEL32!GetProcAddress` at `0x180028736`
- `KERNEL32!GetProcAddress` at `0x1800286e1`
- `KERNEL32!GetProcAddress` at `0x180028736`

## string_xrefs

- `0x1800286da`: `StrongNameTokenFromPublicKey_RetAddr`
- `0x18002872f`: `StrongNameTokenFromPublicKey`

## pseudocode

```c
BOOLEAN __stdcall ShellShim_StrongNameTokenFromPublicKey(
        BYTE *pbPublicKeyBlob,
        ULONG cbPublicKeyBlob,
        BYTE **ppbStrongNameToken,
        ULONG *pcbStrongNameToken)
{
  int ShimImpl; // eax
  HMODULE hModule[7]; // [rsp+30h] [rbp-38h] BYREF
  void *retaddr; // [rsp+68h] [rbp+0h]

  hModule[0] = 0;
  ShimImpl = GetShimImpl(hModule);
  if ( ShimImpl == 1 )
    return 0;
  if ( ShimImpl == 3 )
    return StrongNameTokenFromPublicKey(pbPublicKeyBlob, cbPublicKeyBlob, ppbStrongNameToken, pcbStrongNameToken);
  if ( g_bShimImplDllUninitialized )
    return 0;
  if ( g_pfStrongNameTokenFromPublicKey_RetAddr == (unsigned int (*)(unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *, void *))-1LL )
    g_pfStrongNameTokenFromPublicKey_RetAddr = (unsigned int (*)(unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *, void *))GetProcAddress(hModule[0], "StrongNameTokenFromPublicKey_RetAddr");
  if ( g_pfStrongNameTokenFromPublicKey_RetAddr )
    return ((__int64 (__fastcall *)(BYTE *, _QWORD, BYTE **, ULONG *, void *))g_pfStrongNameTokenFromPublicKey_RetAddr)(
             pbPublicKeyBlob,
             cbPublicKeyBlob,
             ppbStrongNameToken,
             pcbStrongNameToken,
             retaddr);
  if ( g_pfStrongNameTokenFromPublicKey == (unsigned int (*)(unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *))-1LL )
    g_pfStrongNameTokenFromPublicKey = (unsigned int (*)(unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *))GetProcAddress(hModule[0], "StrongNameTokenFromPublicKey");
  if ( !g_pfStrongNameTokenFromPublicKey )
    return 0;
  else
    return ((__int64 (__fastcall *)(BYTE *, _QWORD, BYTE **, ULONG *))g_pfStrongNameTokenFromPublicKey)(
             pbPublicKeyBlob,
             cbPublicKeyBlob,
             ppbStrongNameToken,
             pcbStrongNameToken);
}

```

## disassembly

```asm
0x180028670  push    rbx
0x180028672  push    rbp
0x180028673  push    rsi
0x180028674  push    rdi
0x180028675  sub     rsp, 48h
0x180028679  mov     rbp, rcx
0x18002867c  mov     [rsp+68h+hModule], 0
0x180028685  lea     rcx, [rsp+68h+hModule]
0x18002868a  mov     rbx, r9
0x18002868d  mov     rdi, r8
0x180028690  mov     esi, edx
0x180028692  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180028697  cmp     eax, 1
0x18002869a  jz      loc_180028768
0x1800286a0  cmp     eax, 3
0x1800286a3  jnz     short loc_1800286BA
0x1800286a5  mov     r9, rbx; pcbStrongNameToken
0x1800286a8  mov     r8, rdi; ppbStrongNameToken
0x1800286ab  mov     edx, esi; cbPublicKeyBlob
0x1800286ad  mov     rcx, rbp; pbPublicKeyBlob
0x1800286b0  call    StrongNameTokenFromPublicKey
0x1800286b5  jmp     loc_18002876A
0x1800286ba  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x1800286c0  test    eax, eax
0x1800286c2  jnz     loc_180028768
0x1800286c8  mov     rax, cs:?g_pfStrongNameTokenFromPublicKey_RetAddr@@3R6AKPEAEKPEAPEAEPEAKPEAX@ZEA; ulong (*g_pfStrongNameTokenFromPublicKey_RetAddr)(uchar *,ulong,uchar * *,ulong *,void *)
0x1800286cf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800286d3  jnz     short loc_1800286EE
0x1800286d5  mov     rcx, [rsp+68h+hModule]; hModule
0x1800286da  lea     rdx, aStrongnametoke_6; "StrongNameTokenFromPublicKey_RetAddr"
0x1800286e1  call    cs:__imp_GetProcAddress
0x1800286e7  mov     cs:?g_pfStrongNameTokenFromPublicKey_RetAddr@@3R6AKPEAEKPEAPEAEPEAKPEAX@ZEA, rax; ulong (*g_pfStrongNameTokenFromPublicKey_RetAddr)(uchar *,ulong,uchar * *,ulong *,void *)
0x1800286ee  mov     rax, cs:?g_pfStrongNameTokenFromPublicKey_RetAddr@@3R6AKPEAEKPEAPEAEPEAKPEAX@ZEA; ulong (*g_pfStrongNameTokenFromPublicKey_RetAddr)(uchar *,ulong,uchar * *,ulong *,void *)
0x1800286f5  test    rax, rax
0x1800286f8  jz      short loc_18002871D
0x1800286fa  mov     rax, cs:?g_pfStrongNameTokenFromPublicKey_RetAddr@@3R6AKPEAEKPEAPEAEPEAKPEAX@ZEA; ulong (*g_pfStrongNameTokenFromPublicKey_RetAddr)(uchar *,ulong,uchar * *,ulong *,void *)
0x180028701  mov     r9, rbx
0x180028704  mov     rcx, [rsp+68h]
0x180028709  mov     r8, rdi
0x18002870c  mov     [rsp+68h+var_48], rcx
0x180028711  mov     edx, esi
0x180028713  mov     rcx, rbp
0x180028716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002871b  jmp     short loc_18002876A
0x18002871d  mov     rax, cs:?g_pfStrongNameTokenFromPublicKey@@3R6AKPEAEKPEAPEAEPEAK@ZEA; ulong (*g_pfStrongNameTokenFromPublicKey)(uchar *,ulong,uchar * *,ulong *)
0x180028724  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180028728  jnz     short loc_180028743
0x18002872a  mov     rcx, [rsp+68h+hModule]; hModule
0x18002872f  lea     rdx, aStrongnametoke_3; "StrongNameTokenFromPublicKey"
0x180028736  call    cs:__imp_GetProcAddress
0x18002873c  mov     cs:?g_pfStrongNameTokenFromPublicKey@@3R6AKPEAEKPEAPEAEPEAK@ZEA, rax; ulong (*g_pfStrongNameTokenFromPublicKey)(uchar *,ulong,uchar * *,ulong *)
0x180028743  mov     rax, cs:?g_pfStrongNameTokenFromPublicKey@@3R6AKPEAEKPEAPEAEPEAK@ZEA; ulong (*g_pfStrongNameTokenFromPublicKey)(uchar *,ulong,uchar * *,ulong *)
0x18002874a  test    rax, rax
0x18002874d  jz      short loc_180028768
0x18002874f  mov     rax, cs:?g_pfStrongNameTokenFromPublicKey@@3R6AKPEAEKPEAPEAEPEAK@ZEA; ulong (*g_pfStrongNameTokenFromPublicKey)(uchar *,ulong,uchar * *,ulong *)
0x180028756  mov     r9, rbx
0x180028759  mov     r8, rdi
0x18002875c  mov     edx, esi
0x18002875e  mov     rcx, rbp
0x180028761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028766  jmp     short loc_18002876A
0x180028768  xor     eax, eax
0x18002876a  add     rsp, 48h
0x18002876e  pop     rdi
0x18002876f  pop     rsi
0x180028770  pop     rbp
0x180028771  pop     rbx
0x180028772  retn
```
