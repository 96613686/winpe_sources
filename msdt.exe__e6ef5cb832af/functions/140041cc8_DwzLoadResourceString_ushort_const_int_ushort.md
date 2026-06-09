# DwzLoadResourceString(ushort const *,int,ushort * *)

- ea: `0x140041cc8`
- end: `0x140041e28`
- name: `?DwzLoadResourceString@@YAJPEBGHPEAPEAG@Z`
- size: `352`
- prototype: `__int64 __fastcall(const unsigned __int16 *, UINT, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14004270c`

## callees

- `0x140020420`
- `0x140041cc8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140041da4`
- `KERNEL32!GetLastError` at `0x140041da4`
- `KERNEL32!HeapAlloc` at `0x140041d10`
- `KERNEL32!HeapAlloc` at `0x140041d10`
- `KERNEL32!HeapFree` at `0x140041e10`
- `KERNEL32!HeapFree` at `0x140041e10`
- `KERNEL32!GetProcessHeap` at `0x140041cf9`
- `KERNEL32!GetProcessHeap` at `0x140041dfc`
- `KERNEL32!GetProcessHeap` at `0x140041cf9`
- `KERNEL32!GetProcessHeap` at `0x140041dfc`
- `KERNEL32!FreeLibrary` at `0x140041deb`
- `KERNEL32!FreeLibrary` at `0x140041deb`
- `KERNEL32!LoadLibraryExW` at `0x140041cdc`
- `KERNEL32!LoadLibraryExW` at `0x140041cdc`
- `USER32!LoadStringW` at `0x140041d60`
- `USER32!LoadStringW` at `0x140041d60`
- `OLEAUT32!__imp_SysAllocString` at `0x140041d84`
- `OLEAUT32!__imp_SysAllocString` at `0x140041d84`

## pseudocode

```c
__int64 __fastcall DwzLoadResourceString(const unsigned __int16 *a1, UINT a2, unsigned __int16 **a3)
{
  HMODULE Library; // rsi
  HANDLE ProcessHeap; // rax
  WCHAR *v7; // rax
  OLECHAR *v8; // rdi
  int v9; // r9d
  unsigned int v10; // ebx
  unsigned __int16 *v11; // rax
  signed int LastError; // eax
  HANDLE v13; // rax

  Library = LoadLibraryExW(a1, 0, 2u);
  if ( (unsigned __int64)Library - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    ProcessHeap = GetProcessHeap();
    v7 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x800u);
    v8 = v7;
    if ( v7 )
    {
      if ( LoadStringW(Library, a2, v7, 1024) <= 0 )
      {
        v10 = -2143551222;
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzLoadResourceString", 293, -2143551222);
        goto LABEL_14;
      }
      v11 = SysAllocString(v8);
      *a3 = v11;
      if ( v11 )
      {
        v10 = 0;
        goto LABEL_14;
      }
      v9 = 297;
    }
    else
    {
      v9 = 289;
    }
    v10 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzLoadResourceString", v9, -2147024882);
LABEL_14:
    FreeLibrary(Library);
    if ( v8 )
    {
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v8);
    }
    return v10;
  }
  LastError = GetLastError();
  v10 = LastError;
  if ( LastError > 0 )
    v10 = (unsigned __int16)LastError | 0x80070000;
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzLoadResourceString", 287, v10);
  v8 = 0;
  if ( Library )
    goto LABEL_14;
  return v10;
}

```

## disassembly

```asm
0x140041cc8  push    rbx
0x140041cca  push    rbp
0x140041ccb  push    rsi
0x140041ccc  push    rdi
0x140041ccd  sub     rsp, 38h
0x140041cd1  mov     ebp, edx
0x140041cd3  mov     rbx, r8
0x140041cd6  xor     edx, edx; hFile
0x140041cd8  lea     r8d, [rdx+2]; dwFlags
0x140041cdc  call    cs:__imp_LoadLibraryExW
0x140041ce3  nop     dword ptr [rax+rax+00h]
0x140041ce8  mov     rsi, rax
0x140041ceb  lea     rcx, [rax-1]
0x140041cef  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140041cf3  ja      loc_140041DA4
0x140041cf9  call    cs:__imp_GetProcessHeap
0x140041d00  nop     dword ptr [rax+rax+00h]
0x140041d05  xor     edx, edx; dwFlags
0x140041d07  mov     r8d, 800h; dwBytes
0x140041d0d  mov     rcx, rax; hHeap
0x140041d10  call    cs:__imp_HeapAlloc
0x140041d17  nop     dword ptr [rax+rax+00h]
0x140041d1c  mov     rdi, rax
0x140041d1f  test    rax, rax
0x140041d22  jnz     short loc_140041D52
0x140041d24  mov     r9d, 121h
0x140041d2a  mov     eax, 8007000Eh
0x140041d2f  mov     [rsp+58h+var_38], eax
0x140041d33  mov     ebx, eax
0x140041d35  lea     r8, aDwzloadresourc; "DwzLoadResourceString"
0x140041d3c  mov     ecx, 1; Level
0x140041d41  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140041d48  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140041d4d  jmp     loc_140041DE8
0x140041d52  mov     r9d, 400h; cchBufferMax
0x140041d58  mov     r8, rdi; lpBuffer
0x140041d5b  mov     edx, ebp; uID
0x140041d5d  mov     rcx, rsi; hInstance
0x140041d60  call    cs:__imp_LoadStringW
0x140041d67  nop     dword ptr [rax+rax+00h]
0x140041d6c  test    eax, eax
0x140041d6e  jg      short loc_140041D81
0x140041d70  mov     ebx, 803C010Ah
0x140041d75  mov     r9d, 125h
0x140041d7b  mov     [rsp+58h+var_38], ebx
0x140041d7f  jmp     short loc_140041D35
0x140041d81  mov     rcx, rdi; psz
0x140041d84  call    cs:__imp_SysAllocString
0x140041d8b  nop     dword ptr [rax+rax+00h]
0x140041d90  mov     [rbx], rax
0x140041d93  test    rax, rax
0x140041d96  jnz     short loc_140041DA0
0x140041d98  mov     r9d, 129h
0x140041d9e  jmp     short loc_140041D2A
0x140041da0  xor     ebx, ebx
0x140041da2  jmp     short loc_140041DE8
0x140041da4  call    cs:__imp_GetLastError
0x140041dab  nop     dword ptr [rax+rax+00h]
0x140041db0  mov     ebx, eax
0x140041db2  test    eax, eax
0x140041db4  jle     short loc_140041DBF
0x140041db6  movzx   ebx, ax
0x140041db9  or      ebx, 80070000h
0x140041dbf  mov     r9d, 11Fh
0x140041dc5  mov     [rsp+58h+var_38], ebx
0x140041dc9  lea     r8, aDwzloadresourc; "DwzLoadResourceString"
0x140041dd0  mov     ecx, 1; Level
0x140041dd5  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140041ddc  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140041de1  xor     edi, edi
0x140041de3  test    rsi, rsi
0x140041de6  jz      short loc_140041E1C
0x140041de8  mov     rcx, rsi; hLibModule
0x140041deb  call    cs:__imp_FreeLibrary
0x140041df2  nop     dword ptr [rax+rax+00h]
0x140041df7  test    rdi, rdi
0x140041dfa  jz      short loc_140041E1C
0x140041dfc  call    cs:__imp_GetProcessHeap
0x140041e03  nop     dword ptr [rax+rax+00h]
0x140041e08  mov     r8, rdi; lpMem
0x140041e0b  xor     edx, edx; dwFlags
0x140041e0d  mov     rcx, rax; hHeap
0x140041e10  call    cs:__imp_HeapFree
0x140041e17  nop     dword ptr [rax+rax+00h]
0x140041e1c  mov     eax, ebx
0x140041e1e  add     rsp, 38h
0x140041e22  pop     rdi
0x140041e23  pop     rsi
0x140041e24  pop     rbp
0x140041e25  pop     rbx
0x140041e26  retn
```
