# EnumUILIPHelper(ushort const *,ushort *,ulong)

- ea: `0x1800b7bd0`
- end: `0x1800b7e3a`
- name: `?EnumUILIPHelper@@YAHPEBGPEAGK@Z`
- size: `618`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800b7e40`

## callees

- `0x180008a60`
- `0x180008b54`
- `0x1800316ac`
- `0x1800b7bd0`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b7c56`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b7c56`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b7c1b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b7c1b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b7ce6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b7ce6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b7cff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b7cff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b7cbc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b7cbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b7cae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b7cf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b7cae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b7cf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7dea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7dea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b7ccf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b7e05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b7e2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b7ccf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b7e05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b7e2f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800b7c37`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800b7c37`

## string_xrefs

- `0x1800b7c02`: `kernel32.dll`
- `0x1800b7c29`: `kernel32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnumUILIPHelper(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  HMODULE ModuleHandleW; // rdi
  unsigned __int16 *v6; // r14
  FARPROC ProcAddress; // rax
  unsigned int (__fastcall *v8)(__int64, const unsigned __int16 *, unsigned __int16 *, unsigned __int64 *, int *); // rsi
  SIZE_T v9; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v11; // rax
  DWORD v12; // ecx
  HANDLE v13; // rax
  unsigned int v15; // r11d
  int v16; // esi
  const unsigned __int16 *v17; // rbx
  unsigned __int64 v18; // r13
  unsigned __int64 v19; // rcx
  unsigned int v20; // esi
  int v21; // [rsp+30h] [rbp-20h] BYREF
  int v22; // [rsp+34h] [rbp-1Ch]
  unsigned __int64 v23; // [rsp+38h] [rbp-18h]
  unsigned __int64 v24; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int64 v25; // [rsp+A8h] [rbp+58h] BYREF

  LODWORD(v23) = g_BufferSize;
  v3 = 0;
  v24 = 0;
  v21 = 0;
  LODWORD(v25) = 0;
  v22 = 0;
  ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
  if ( !ModuleHandleW )
  {
    v22 = 1;
    ModuleHandleW = LoadLibraryW(L"kernel32.dll");
    if ( !ModuleHandleW )
      return v3;
  }
  v6 = 0;
  ProcAddress = GetProcAddress(ModuleHandleW, "GetUILanguageInfo");
  v8 = (unsigned int (__fastcall *)(__int64, const unsigned __int16 *, unsigned __int16 *, unsigned __int64 *, int *))ProcAddress;
  if ( ProcAddress )
  {
    if ( !a1
      || !((unsigned int (__fastcall *)(__int64, const unsigned __int16 *, _QWORD, unsigned __int64 *, int *))ProcAddress)(
            8,
            a1,
            0,
            &v25,
            &v21)
      || (unsigned int)v25 <= 2
      || (v21 & 4) == 0 )
    {
      SetLastError(0x57u);
      goto LABEL_11;
    }
    v9 = 2LL * (unsigned int)v25;
    ProcessHeap = GetProcessHeap();
    v11 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, v9);
    v6 = v11;
    v12 = 8;
    if ( v11 )
    {
      if ( v8(8, a1, v11, &v25, &v21) )
      {
        v15 = g_uNumLangIdx;
        v16 = 0;
        v17 = v6;
        while ( 1 )
        {
          if ( !*v17 )
          {
            v3 = 1;
            g_uNumLangIdx = v16 + v15;
            goto LABEL_11;
          }
          v18 = (unsigned int)v25;
          if ( (int)StringCchLengthW(v17, (unsigned int)v25, &v24) < 0 || (v19 = v24 + 1, v24 = v19, v19 > v18) )
          {
            SetLastError(0x6Fu);
            v3 = 0;
            goto LABEL_11;
          }
          if ( a2 && g_LangNumber == v15 + v16 )
            break;
          v17 += v19;
          ++v16;
        }
        v20 = v23;
        if ( StringCchCopyW(a2, (unsigned int)v23, a1) >= 0
          && StringCchCatW(a2, v20, L",") >= 0
          && StringCchCatW(a2, v20, v17) >= 0 )
        {
          g_uNumLangIdx = 268435458;
          goto LABEL_10;
        }
        if ( !GetLastError() )
        {
          v12 = 111;
          goto LABEL_9;
        }
        goto LABEL_10;
      }
      v12 = 87;
    }
LABEL_9:
    SetLastError(v12);
LABEL_10:
    v3 = 0;
  }
LABEL_11:
  if ( v22 )
    FreeLibrary(ModuleHandleW);
  if ( v6 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v6);
  }
  return v3;
}

```

## disassembly

```asm
0x1800b7bd0  mov     [rsp-38h+arg_0], rbx
0x1800b7bd5  mov     [rsp-38h+arg_10], r8d
0x1800b7bda  push    rbp
0x1800b7bdb  push    rsi
0x1800b7bdc  push    rdi
0x1800b7bdd  push    r12
0x1800b7bdf  push    r13
0x1800b7be1  push    r14
0x1800b7be3  push    r15
0x1800b7be5  mov     rbp, rsp
0x1800b7be8  sub     rsp, 50h
0x1800b7bec  mov     eax, cs:?g_BufferSize@@3IA; uint g_BufferSize
0x1800b7bf2  xor     r13d, r13d
0x1800b7bf5  mov     r12, rcx
0x1800b7bf8  mov     dword ptr [rbp+var_18], eax
0x1800b7bfb  mov     ebx, r13d
0x1800b7bfe  mov     [rbp+var_10], r13
0x1800b7c02  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1800b7c09  mov     [rbp+arg_10], ebx
0x1800b7c0c  mov     r15, rdx
0x1800b7c0f  mov     [rbp+var_20], r13d
0x1800b7c13  mov     dword ptr [rbp+arg_18], r13d
0x1800b7c17  mov     [rbp+var_1C], r13d
0x1800b7c1b  call    cs:__imp_GetModuleHandleW
0x1800b7c21  mov     rdi, rax
0x1800b7c24  test    rax, rax
0x1800b7c27  jnz     short loc_1800B7C49
0x1800b7c29  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1800b7c30  mov     [rbp+var_1C], 1
0x1800b7c37  call    cs:__imp_LoadLibraryW
0x1800b7c3d  mov     rdi, rax
0x1800b7c40  test    rax, rax
0x1800b7c43  jz      loc_1800B7D05
0x1800b7c49  lea     rdx, aGetuilanguagei; "GetUILanguageInfo"
0x1800b7c50  mov     rcx, rdi; hModule
0x1800b7c53  mov     r14, r13
0x1800b7c56  call    cs:__imp_GetProcAddress
0x1800b7c5c  mov     rsi, rax
0x1800b7c5f  test    rax, rax
0x1800b7c62  jz      short loc_1800B7CDD
0x1800b7c64  test    r12, r12
0x1800b7c67  jz      loc_1800B7E2A
0x1800b7c6d  xor     r8d, r8d
0x1800b7c70  lea     rax, [rbp+var_20]
0x1800b7c74  mov     [rsp+50h+var_30], rax
0x1800b7c79  lea     r9, [rbp+arg_18]
0x1800b7c7d  mov     rdx, r12
0x1800b7c80  mov     rax, rsi
0x1800b7c83  lea     ecx, [r8+8]
0x1800b7c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7c8c  test    eax, eax
0x1800b7c8e  jz      loc_1800B7E2A
0x1800b7c94  cmp     dword ptr [rbp+arg_18], 2
0x1800b7c98  jbe     loc_1800B7E2A
0x1800b7c9e  test    byte ptr [rbp+var_20], 4
0x1800b7ca2  jz      loc_1800B7E2A
0x1800b7ca8  mov     ebx, dword ptr [rbp+arg_18]
0x1800b7cab  add     rbx, rbx
0x1800b7cae  call    cs:__imp_GetProcessHeap
0x1800b7cb4  mov     r8, rbx; dwBytes
0x1800b7cb7  xor     edx, edx; dwFlags
0x1800b7cb9  mov     rcx, rax; hHeap
0x1800b7cbc  call    cs:__imp_HeapAlloc
0x1800b7cc2  mov     r14, rax
0x1800b7cc5  mov     ecx, 8; dwErrCode
0x1800b7cca  test    rax, rax
0x1800b7ccd  jnz     short loc_1800B7D1F
0x1800b7ccf  call    cs:__imp_SetLastError
0x1800b7cd5  mov     ebx, r13d
0x1800b7cd8  test    rdi, rdi
0x1800b7cdb  jz      short loc_1800B7CEC
0x1800b7cdd  cmp     [rbp+var_1C], r13d
0x1800b7ce1  jz      short loc_1800B7CEC
0x1800b7ce3  mov     rcx, rdi; hLibModule
0x1800b7ce6  call    cs:__imp_FreeLibrary
0x1800b7cec  test    r14, r14
0x1800b7cef  jz      short loc_1800B7D05
0x1800b7cf1  call    cs:__imp_GetProcessHeap
0x1800b7cf7  mov     r8, r14; lpMem
0x1800b7cfa  xor     edx, edx; dwFlags
0x1800b7cfc  mov     rcx, rax; hHeap
0x1800b7cff  call    cs:__imp_HeapFree
0x1800b7d05  mov     eax, ebx
0x1800b7d07  mov     rbx, [rsp+50h+arg_0]
0x1800b7d0f  add     rsp, 50h
0x1800b7d13  pop     r15
0x1800b7d15  pop     r14
0x1800b7d17  pop     r13
0x1800b7d19  pop     r12
0x1800b7d1b  pop     rdi
0x1800b7d1c  pop     rsi
0x1800b7d1d  pop     rbp
0x1800b7d1e  retn
0x1800b7d1f  lea     rax, [rbp+var_20]
0x1800b7d23  mov     r8, r14
0x1800b7d26  mov     [rsp+50h+var_30], rax
0x1800b7d2b  lea     r9, [rbp+arg_18]
0x1800b7d2f  mov     rax, rsi
0x1800b7d32  mov     rdx, r12
0x1800b7d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7d3a  test    eax, eax
0x1800b7d3c  jnz     short loc_1800B7D43
0x1800b7d3e  lea     ecx, [rax+57h]
0x1800b7d41  jmp     short loc_1800B7CCF
0x1800b7d43  mov     r11d, cs:?g_uNumLangIdx@@3IA; uint g_uNumLangIdx
0x1800b7d4a  mov     esi, r13d
0x1800b7d4d  mov     rbx, r14
0x1800b7d50  cmp     [rbx], r13w
0x1800b7d54  jz      loc_1800B7E16
0x1800b7d5a  mov     r13d, dword ptr [rbp+arg_18]
0x1800b7d5e  lea     r8, [rbp+var_10]; unsigned __int64 *
0x1800b7d62  mov     edx, r13d; unsigned __int64
0x1800b7d65  mov     rcx, rbx; unsigned __int16 *
0x1800b7d68  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800b7d6d  test    eax, eax
0x1800b7d6f  js      loc_1800B7E00
0x1800b7d75  mov     rcx, [rbp+var_10]
0x1800b7d79  inc     rcx
0x1800b7d7c  mov     [rbp+var_10], rcx
0x1800b7d80  cmp     rcx, r13
0x1800b7d83  ja      short loc_1800B7E00
0x1800b7d85  xor     r13d, r13d
0x1800b7d88  test    r15, r15
0x1800b7d8b  jz      short loc_1800B7D99
0x1800b7d8d  lea     eax, [r11+rsi]
0x1800b7d91  cmp     cs:?g_LangNumber@@3IA, eax; uint g_LangNumber
0x1800b7d97  jz      short loc_1800B7DA1
0x1800b7d99  lea     rbx, [rbx+rcx*2]
0x1800b7d9d  inc     esi
0x1800b7d9f  jmp     short loc_1800B7D50
0x1800b7da1  mov     esi, dword ptr [rbp+var_18]
0x1800b7da4  mov     r8, r12; unsigned __int16 *
0x1800b7da7  mov     edx, esi; unsigned __int64
0x1800b7da9  mov     rcx, r15; unsigned __int16 *
0x1800b7dac  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b7db1  test    eax, eax
0x1800b7db3  js      short loc_1800B7DEA
0x1800b7db5  lea     r8, asc_1800E7590; ","
0x1800b7dbc  mov     edx, esi; unsigned __int64
0x1800b7dbe  mov     rcx, r15; unsigned __int16 *
0x1800b7dc1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b7dc6  test    eax, eax
0x1800b7dc8  js      short loc_1800B7DEA
0x1800b7dca  mov     r8, rbx; unsigned __int16 *
0x1800b7dcd  mov     edx, esi; unsigned __int64
0x1800b7dcf  mov     rcx, r15; unsigned __int16 *
0x1800b7dd2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b7dd7  test    eax, eax
0x1800b7dd9  js      short loc_1800B7DEA
0x1800b7ddb  mov     cs:?g_uNumLangIdx@@3IA, 10000002h; uint g_uNumLangIdx
0x1800b7de5  jmp     loc_1800B7CD5
0x1800b7dea  call    cs:__imp_GetLastError
0x1800b7df0  test    eax, eax
0x1800b7df2  jnz     loc_1800B7CD5
0x1800b7df8  lea     ecx, [rax+6Fh]
0x1800b7dfb  jmp     loc_1800B7CCF
0x1800b7e00  mov     ecx, 6Fh ; 'o'; dwErrCode
0x1800b7e05  call    cs:__imp_SetLastError
0x1800b7e0b  mov     ebx, [rbp+arg_10]
0x1800b7e0e  xor     r13d, r13d
0x1800b7e11  jmp     loc_1800B7CD8
0x1800b7e16  add     r11d, esi
0x1800b7e19  mov     ebx, 1
0x1800b7e1e  mov     cs:?g_uNumLangIdx@@3IA, r11d; uint g_uNumLangIdx
0x1800b7e25  jmp     loc_1800B7CD8
0x1800b7e2a  mov     ecx, 57h ; 'W'; dwErrCode
0x1800b7e2f  call    cs:__imp_SetLastError
0x1800b7e35  jmp     loc_1800B7CD8
```
