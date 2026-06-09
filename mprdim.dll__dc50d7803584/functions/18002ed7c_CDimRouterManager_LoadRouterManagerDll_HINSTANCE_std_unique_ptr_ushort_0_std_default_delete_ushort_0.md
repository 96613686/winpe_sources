# CDimRouterManager::LoadRouterManagerDll(HINSTANCE__ * &,std::unique_ptr<ushort [0],std::default_delete<ushort [0]>> &)

- ea: `0x18002ed7c`
- end: `0x18002ee43`
- name: `?LoadRouterManagerDll@CDimRouterManager@@AEAAKAEAPEAUHINSTANCE__@@AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@@Z`
- size: `199`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x18002f7c8`
- `0x18002fac0`

## callees

- `0x18000b654`
- `0x180023384`
- `0x18002ed7c`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ede3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ee2e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ede3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ee2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ee23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ee23`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002ee15`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002ee15`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002eda5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002ee01`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002eda5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002ee01`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDimRouterManager::LoadRouterManagerDll(void *a1, HMODULE *a2, LPCWSTR *a3)
{
  WCHAR *v5; // rbx
  DWORD v6; // eax
  DWORD v7; // ebp
  DWORD LastError; // edi
  HMODULE Library; // rax
  void *v11; // [rsp+40h] [rbp+8h] BYREF
  LPWSTR lpDst; // [rsp+48h] [rbp+10h] BYREF

  v11 = a1;
  v5 = 0;
  lpDst = 0;
  *a2 = 0;
  v6 = ExpandEnvironmentStringsW(*a3, 0, 0);
  if ( !v6 )
    goto LABEL_6;
  v7 = 2 * v6;
  v11 = operator new[](saturated_mul(2 * v6, 2u));
  std::unique_ptr<unsigned short [0]>::operator=((__int64 *)&lpDst, (__int64 *)&v11);
  operator delete[](v11);
  v5 = lpDst;
  if ( !lpDst )
  {
    LastError = 8;
    goto LABEL_7;
  }
  if ( !ExpandEnvironmentStringsW(*a3, lpDst, v7)
    || (LastError = 0, Library = LoadLibraryExW(v5, 0, 0), (*a2 = Library) == 0) )
  {
LABEL_6:
    LastError = GetLastError();
  }
LABEL_7:
  operator delete[](v5);
  return LastError;
}

```

## disassembly

```asm
0x18002ed7c  mov     [rsp+arg_10], rbx
0x18002ed81  mov     [rsp+arg_0], rcx
0x18002ed86  push    rbp
0x18002ed87  push    rsi
0x18002ed88  push    rdi
0x18002ed89  sub     rsp, 20h
0x18002ed8d  mov     rdi, r8
0x18002ed90  mov     rsi, rdx
0x18002ed93  xor     ebx, ebx
0x18002ed95  mov     [rsp+38h+lpDst], rbx
0x18002ed9a  mov     [rdx], rbx
0x18002ed9d  xor     r8d, r8d; nSize
0x18002eda0  xor     edx, edx; lpDst
0x18002eda2  mov     rcx, [rdi]; lpSrc
0x18002eda5  call    cs:__imp_ExpandEnvironmentStringsW
0x18002edab  test    eax, eax
0x18002edad  jz      short loc_18002EE23
0x18002edaf  lea     ebp, [rax+rax]
0x18002edb2  mov     ecx, ebp
0x18002edb4  lea     eax, [rbx+2]
0x18002edb7  mul     rcx
0x18002edba  lea     rcx, [rbx-1]
0x18002edbe  cmovb   rax, rcx
0x18002edc2  mov     rcx, rax; unsigned __int64
0x18002edc5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002edca  mov     [rsp+38h+arg_0], rax
0x18002edcf  lea     rdx, [rsp+38h+arg_0]
0x18002edd4  lea     rcx, [rsp+38h+lpDst]
0x18002edd9  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<ushort [0]>::operator=(std::unique_ptr<ushort [0]> &&)
0x18002edde  mov     rcx, [rsp+38h+arg_0]
0x18002ede3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002ede9  mov     rbx, [rsp+38h+lpDst]
0x18002edee  test    rbx, rbx
0x18002edf1  jnz     short loc_18002EDF8
0x18002edf3  lea     edi, [rbx+8]
0x18002edf6  jmp     short loc_18002EE2B
0x18002edf8  mov     r8d, ebp; nSize
0x18002edfb  mov     rdx, rbx; lpDst
0x18002edfe  mov     rcx, [rdi]; lpSrc
0x18002ee01  call    cs:__imp_ExpandEnvironmentStringsW
0x18002ee07  test    eax, eax
0x18002ee09  jz      short loc_18002EE23
0x18002ee0b  xor     edi, edi
0x18002ee0d  xor     r8d, r8d; dwFlags
0x18002ee10  xor     edx, edx; hFile
0x18002ee12  mov     rcx, rbx; lpLibFileName
0x18002ee15  call    cs:__imp_LoadLibraryExW
0x18002ee1b  mov     [rsi], rax
0x18002ee1e  test    rax, rax
0x18002ee21  jnz     short loc_18002EE2B
0x18002ee23  call    cs:__imp_GetLastError
0x18002ee29  mov     edi, eax
0x18002ee2b  mov     rcx, rbx
0x18002ee2e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002ee34  mov     eax, edi
0x18002ee36  mov     rbx, [rsp+38h+arg_10]
0x18002ee3b  add     rsp, 20h
0x18002ee3f  pop     rdi
0x18002ee40  pop     rsi
0x18002ee41  pop     rbp
0x18002ee42  retn
```
