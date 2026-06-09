# StrongNameTokenFromAssemblyEx

- ea: `0x18002eda8`
- end: `0x18002ee3b`
- name: `StrongNameTokenFromAssemblyEx`
- size: `147`
- prototype: `BOOLEAN __stdcall(LPCWSTR wszFilePath, BYTE **ppbStrongNameToken, ULONG *pcbStrongNameToken, BYTE **ppbPublicKeyBlob, ULONG *pcbPublicKeyBlob)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180028530`

## callees

- `0x18002a2e4`
- `0x18002eda8`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002ee03`
- `KERNEL32!GetProcAddress` at `0x18002ee03`

## string_xrefs

- `0x18002edfc`: `StrongNameTokenFromAssemblyEx`

## pseudocode

```c
BOOLEAN __stdcall StrongNameTokenFromAssemblyEx(
        LPCWSTR wszFilePath,
        BYTE **ppbStrongNameToken,
        ULONG *pcbStrongNameToken,
        BYTE **ppbPublicKeyBlob,
        ULONG *pcbPublicKeyBlob)
{
  FARPROC ProcAddress; // rax
  const WCHAR *v6; // rbp
  HMODULE hModule; // [rsp+30h] [rbp-38h] BYREF

  ProcAddress = (FARPROC)g_StrongNameTokenFromAssemblyEx;
  v6 = wszFilePath;
  if ( g_StrongNameTokenFromAssemblyEx )
    return ((__int64 (__fastcall *)(LPCWSTR))ProcAddress)(wszFilePath);
  hModule = 0;
  if ( (int)GetRealStrongNameDll(&hModule) >= 0 )
  {
    ProcAddress = GetProcAddress(hModule, "StrongNameTokenFromAssemblyEx");
    g_StrongNameTokenFromAssemblyEx = (unsigned __int8 (*)(const unsigned __int16 *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *))ProcAddress;
    if ( ProcAddress )
    {
      wszFilePath = v6;
      return ((__int64 (__fastcall *)(LPCWSTR))ProcAddress)(wszFilePath);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002eda8  push    rbx
0x18002edaa  push    rbp
0x18002edab  push    rsi
0x18002edac  push    rdi
0x18002edad  sub     rsp, 48h
0x18002edb1  mov     rax, cs:?g_StrongNameTokenFromAssemblyEx@@3P6AEPEBGPEAPEAEPEAK12@ZEA; uchar (*g_StrongNameTokenFromAssemblyEx)(ushort const *,uchar * *,ulong *,uchar * *,ulong *)
0x18002edb8  mov     rbx, r9
0x18002edbb  mov     rdi, r8
0x18002edbe  mov     rsi, rdx
0x18002edc1  mov     rbp, rcx
0x18002edc4  test    rax, rax
0x18002edc7  jz      short loc_18002EDE0
0x18002edc9  mov     r10, [rsp+68h+pcbPublicKeyBlob]
0x18002edd1  mov     [rsp+68h+var_48], r10
0x18002edd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eddb  movzx   eax, al
0x18002edde  jmp     short loc_18002EE32
0x18002ede0  lea     rcx, [rsp+68h+hModule]; HINSTANCE *
0x18002ede5  mov     [rsp+68h+hModule], 0
0x18002edee  call    ?GetRealStrongNameDll@@YAJPEAPEAUHINSTANCE__@@@Z; GetRealStrongNameDll(HINSTANCE__ * *)
0x18002edf3  test    eax, eax
0x18002edf5  js      short loc_18002EE30
0x18002edf7  mov     rcx, [rsp+68h+hModule]; hModule
0x18002edfc  lea     rdx, aStrongnametoke_4; "StrongNameTokenFromAssemblyEx"
0x18002ee03  call    cs:__imp_GetProcAddress
0x18002ee09  mov     cs:?g_StrongNameTokenFromAssemblyEx@@3P6AEPEBGPEAPEAEPEAK12@ZEA, rax; uchar (*g_StrongNameTokenFromAssemblyEx)(ushort const *,uchar * *,ulong *,uchar * *,ulong *)
0x18002ee10  test    rax, rax
0x18002ee13  jz      short loc_18002EE30
0x18002ee15  mov     rcx, [rsp+68h+pcbPublicKeyBlob]
0x18002ee1d  mov     r9, rbx
0x18002ee20  mov     [rsp+68h+var_48], rcx
0x18002ee25  mov     r8, rdi
0x18002ee28  mov     rcx, rbp
0x18002ee2b  mov     rdx, rsi
0x18002ee2e  jmp     short loc_18002EDD6
0x18002ee30  xor     eax, eax
0x18002ee32  add     rsp, 48h
0x18002ee36  pop     rdi
0x18002ee37  pop     rsi
0x18002ee38  pop     rbp
0x18002ee39  pop     rbx
0x18002ee3a  retn
```
