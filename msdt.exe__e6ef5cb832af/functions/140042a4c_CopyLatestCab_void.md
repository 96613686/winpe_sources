# CopyLatestCab(void)

- ea: `0x140042a4c`
- end: `0x140042bef`
- name: `?CopyLatestCab@@YAJXZ`
- size: `419`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x140043a14`

## callees

- `0x140006fe0`
- `0x1400070b0`
- `0x140020420`
- `0x14003504c`
- `0x1400404f4`
- `0x140042a4c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140042b4c`
- `KERNEL32!GetLastError` at `0x140042b4c`
- `KERNEL32!HeapAlloc` at `0x140042a76`
- `KERNEL32!HeapAlloc` at `0x140042a76`
- `KERNEL32!HeapFree` at `0x140042bb5`
- `KERNEL32!HeapFree` at `0x140042bd5`
- `KERNEL32!HeapFree` at `0x140042bb5`
- `KERNEL32!HeapFree` at `0x140042bd5`
- `KERNEL32!GetProcessHeap` at `0x140042a5f`
- `KERNEL32!GetProcessHeap` at `0x140042b9f`
- `KERNEL32!GetProcessHeap` at `0x140042bc1`
- `KERNEL32!GetProcessHeap` at `0x140042a5f`
- `KERNEL32!GetProcessHeap` at `0x140042b9f`
- `KERNEL32!GetProcessHeap` at `0x140042bc1`
- `KERNEL32!DeleteFileW` at `0x140042b3c`
- `KERNEL32!DeleteFileW` at `0x140042b3c`

## string_xrefs

- `0x140042a8f`: `CopyLatestCab`
- `0x140042adf`: `CopyLatestCab`
- `0x140042b7b`: `CopyLatestCab`

## pseudocode

```c
__int64 CopyLatestCab(void)
{
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v1; // rax
  unsigned __int16 *v2; // rdi
  unsigned int v3; // ebx
  int v4; // eax
  int CabFromPath; // eax
  int v6; // r9d
  unsigned __int16 *v7; // r8
  HANDLE v8; // rax
  HANDLE v9; // rax
  LPVOID lpMem; // [rsp+40h] [rbp+8h] BYREF

  lpMem = 0;
  ProcessHeap = GetProcessHeap();
  v1 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x800u);
  v2 = v1;
  if ( v1 )
  {
    v4 = StringCchPrintfW(v1, 0x104u, L"%s\\..\\", g_HistoryDirectory);
    v3 = v4;
    if ( v4 < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CopyLatestCab", 306, v4);
LABEL_16:
      v9 = GetProcessHeap();
      HeapFree(v9, 0, v2);
      return v3;
    }
    CabFromPath = Configuration::CanonicalizeFilePath(v2, (unsigned __int16 **)&lpMem);
    v3 = CabFromPath;
    if ( CabFromPath >= 0 )
    {
      CabFromPath = StringCchCatW(v2, 0x104u, L"latest.cab");
      v3 = CabFromPath;
      if ( CabFromPath >= 0 )
      {
        if ( !DeleteFileW(v2) )
          GetLastError();
        CabFromPath = CreateCabFromPath((const unsigned __int16 *)lpMem, L"latest.cab", v7, 1);
        v3 = CabFromPath;
        if ( CabFromPath >= 0 )
          goto LABEL_14;
        v6 = 321;
      }
      else
      {
        v6 = 312;
      }
    }
    else
    {
      v6 = 309;
    }
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CopyLatestCab", v6, CabFromPath);
LABEL_14:
    if ( lpMem )
    {
      v8 = GetProcessHeap();
      HeapFree(v8, 0, lpMem);
    }
    goto LABEL_16;
  }
  v3 = -2147024882;
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CopyLatestCab", 299, -2147024882);
  return v3;
}

```

## disassembly

```asm
0x140042a4c  mov     [rsp+arg_8], rbx
0x140042a51  push    rdi
0x140042a52  sub     rsp, 30h
0x140042a56  mov     [rsp+38h+lpMem], 0
0x140042a5f  call    cs:__imp_GetProcessHeap
0x140042a66  nop     dword ptr [rax+rax+00h]
0x140042a6b  xor     edx, edx; dwFlags
0x140042a6d  mov     r8d, 800h; dwBytes
0x140042a73  mov     rcx, rax; hHeap
0x140042a76  call    cs:__imp_HeapAlloc
0x140042a7d  nop     dword ptr [rax+rax+00h]
0x140042a82  mov     rdi, rax
0x140042a85  test    rax, rax
0x140042a88  jnz     short loc_140042AB4
0x140042a8a  mov     ebx, 8007000Eh
0x140042a8f  lea     r8, aCopylatestcab; "CopyLatestCab"
0x140042a96  mov     r9d, 12Bh
0x140042a9c  mov     [rsp+38h+var_18], ebx
0x140042aa0  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140042aa7  lea     ecx, [rax+1]; Level
0x140042aaa  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140042aaf  jmp     loc_140042BE1
0x140042ab4  mov     r9, cs:?g_HistoryDirectory@@3PEAGEA; ushort * g_HistoryDirectory
0x140042abb  lea     r8, aS_4; "%s\\..\\"
0x140042ac2  mov     edx, 104h; unsigned __int64
0x140042ac7  mov     rcx, rdi; unsigned __int16 *
0x140042aca  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140042acf  mov     ebx, eax
0x140042ad1  test    eax, eax
0x140042ad3  jns     short loc_140042AFC
0x140042ad5  mov     r9d, 132h
0x140042adb  mov     [rsp+38h+var_18], eax
0x140042adf  lea     r8, aCopylatestcab; "CopyLatestCab"
0x140042ae6  mov     ecx, 1; Level
0x140042aeb  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140042af2  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140042af7  jmp     loc_140042BC1
0x140042afc  lea     rdx, [rsp+38h+lpMem]; unsigned __int16 **
0x140042b01  mov     rcx, rdi; lpFileName
0x140042b04  call    ?CanonicalizeFilePath@Configuration@@SAJPEBGPEAPEAG@Z; Configuration::CanonicalizeFilePath(ushort const *,ushort * *)
0x140042b09  mov     ebx, eax
0x140042b0b  test    eax, eax
0x140042b0d  jns     short loc_140042B17
0x140042b0f  mov     r9d, 135h
0x140042b15  jmp     short loc_140042B7B
0x140042b17  lea     r8, aLatestCab; "latest.cab"
0x140042b1e  mov     edx, 104h; unsigned __int64
0x140042b23  mov     rcx, rdi; unsigned __int16 *
0x140042b26  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140042b2b  mov     ebx, eax
0x140042b2d  test    eax, eax
0x140042b2f  jns     short loc_140042B39
0x140042b31  mov     r9d, 138h
0x140042b37  jmp     short loc_140042B7B
0x140042b39  mov     rcx, rdi; lpFileName
0x140042b3c  call    cs:__imp_DeleteFileW
0x140042b43  nop     dword ptr [rax+rax+00h]
0x140042b48  test    eax, eax
0x140042b4a  jnz     short loc_140042B58
0x140042b4c  call    cs:__imp_GetLastError
0x140042b53  nop     dword ptr [rax+rax+00h]
0x140042b58  mov     rcx, [rsp+38h+lpMem]; unsigned __int16 *
0x140042b5d  lea     rdx, aLatestCab; "latest.cab"
0x140042b64  mov     r9d, 1; int
0x140042b6a  call    ?CreateCabFromPath@@YAJPEBG0PEAGH@Z; CreateCabFromPath(ushort const *,ushort const *,ushort *,int)
0x140042b6f  mov     ebx, eax
0x140042b71  test    eax, eax
0x140042b73  jns     short loc_140042B97
0x140042b75  mov     r9d, 141h
0x140042b7b  lea     r8, aCopylatestcab; "CopyLatestCab"
0x140042b82  mov     [rsp+38h+var_18], eax
0x140042b86  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140042b8d  mov     ecx, 1; Level
0x140042b92  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140042b97  cmp     [rsp+38h+lpMem], 0
0x140042b9d  jz      short loc_140042BC1
0x140042b9f  call    cs:__imp_GetProcessHeap
0x140042ba6  nop     dword ptr [rax+rax+00h]
0x140042bab  mov     r8, [rsp+38h+lpMem]; lpMem
0x140042bb0  xor     edx, edx; dwFlags
0x140042bb2  mov     rcx, rax; hHeap
0x140042bb5  call    cs:__imp_HeapFree
0x140042bbc  nop     dword ptr [rax+rax+00h]
0x140042bc1  call    cs:__imp_GetProcessHeap
0x140042bc8  nop     dword ptr [rax+rax+00h]
0x140042bcd  mov     r8, rdi; lpMem
0x140042bd0  xor     edx, edx; dwFlags
0x140042bd2  mov     rcx, rax; hHeap
0x140042bd5  call    cs:__imp_HeapFree
0x140042bdc  nop     dword ptr [rax+rax+00h]
0x140042be1  mov     eax, ebx
0x140042be3  mov     rbx, [rsp+38h+arg_8]
0x140042be8  add     rsp, 30h
0x140042bec  pop     rdi
0x140042bed  retn
```
