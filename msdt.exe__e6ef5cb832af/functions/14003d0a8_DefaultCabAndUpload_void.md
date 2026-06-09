# DefaultCabAndUpload(void)

- ea: `0x14003d0a8`
- end: `0x14003d287`
- name: `?DefaultCabAndUpload@@YAJXZ`
- size: `479`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14003eb60`

## callees

- `0x140020420`
- `0x14003d0a8`
- `0x14003e700`
- `0x1400404f4`
- `0x140041578`
- `0x140043a14`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14003d0e3`
- `KERNEL32!HeapAlloc` at `0x14003d137`
- `KERNEL32!HeapAlloc` at `0x14003d0e3`
- `KERNEL32!HeapAlloc` at `0x14003d137`
- `KERNEL32!HeapFree` at `0x14003d243`
- `KERNEL32!HeapFree` at `0x14003d268`
- `KERNEL32!HeapFree` at `0x14003d243`
- `KERNEL32!HeapFree` at `0x14003d268`
- `KERNEL32!GetProcessHeap` at `0x14003d0ca`
- `KERNEL32!GetProcessHeap` at `0x14003d123`
- `KERNEL32!GetProcessHeap` at `0x14003d22f`
- `KERNEL32!GetProcessHeap` at `0x14003d254`
- `KERNEL32!GetProcessHeap` at `0x14003d0ca`
- `KERNEL32!GetProcessHeap` at `0x14003d123`
- `KERNEL32!GetProcessHeap` at `0x14003d22f`
- `KERNEL32!GetProcessHeap` at `0x14003d254`
- `KERNEL32!GetFullPathNameW` at `0x14003d18e`
- `KERNEL32!GetFullPathNameW` at `0x14003d18e`

## pseudocode

```c
__int64 DefaultCabAndUpload(void)
{
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v1; // rsi
  unsigned int v2; // ebx
  HANDLE v3; // rax
  WCHAR *v4; // rax
  __int64 v5; // rdx
  unsigned __int64 v6; // r8
  unsigned __int16 *v7; // rdi
  int TemporaryFileName; // eax
  int HistoryDirectory; // eax
  unsigned __int16 *v10; // r8
  int CabFromPath; // eax
  int v12; // eax
  HANDLE v13; // rax
  HANDLE v14; // rax
  LPWSTR FilePart; // [rsp+40h] [rbp+8h] BYREF

  FilePart = 0;
  g_ErrorContext = 405;
  ProcessHeap = GetProcessHeap();
  v1 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x208u);
  if ( v1 )
  {
    v3 = GetProcessHeap();
    v4 = (WCHAR *)HeapAlloc(v3, 0, 0x208u);
    v7 = v4;
    if ( v4 )
    {
      TemporaryFileName = GetTemporaryFileName(v4, v5, v6);
      v2 = TemporaryFileName;
      if ( TemporaryFileName >= 0 )
      {
        if ( GetFullPathNameW(v7, 0x104u, v1, &FilePart) - 1 > 0x103 || FilePart <= v1 )
        {
          v2 = -2147319786;
          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DefaultCabAndUpload", 946, -2147319786);
        }
        else
        {
          *(FilePart - 1) = 0;
          HistoryDirectory = MakeHistoryDirectory(0);
          v2 = HistoryDirectory;
          if ( HistoryDirectory >= 0 )
          {
            CabFromPath = CreateCabFromPath(v1, FilePart, v10, 0);
            v2 = CabFromPath;
            if ( CabFromPath >= 0 )
            {
              v12 = UploadFile(v7);
              v2 = v12;
              if ( v12 < 0 )
                SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DefaultCabAndUpload", 962, v12);
            }
            else
            {
              SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DefaultCabAndUpload", 959, CabFromPath);
            }
          }
          else
          {
            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DefaultCabAndUpload", 956, HistoryDirectory);
          }
        }
      }
      else
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DefaultCabAndUpload", 937, TemporaryFileName);
      }
    }
    else
    {
      v2 = -2147024882;
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DefaultCabAndUpload", 931, -2147024882);
    }
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v1);
    if ( v7 )
    {
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v7);
    }
  }
  else
  {
    v2 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DefaultCabAndUpload", 930, -2147024882);
  }
  return v2;
}

```

## disassembly

```asm
0x14003d0a8  mov     [rsp+arg_8], rbx
0x14003d0ad  mov     [rsp+arg_10], rsi
0x14003d0b2  push    rdi
0x14003d0b3  sub     rsp, 30h
0x14003d0b7  mov     [rsp+38h+FilePart], 0
0x14003d0c0  mov     cs:?g_ErrorContext@@3IC, 195h; uint volatile g_ErrorContext
0x14003d0ca  call    cs:__imp_GetProcessHeap
0x14003d0d1  nop     dword ptr [rax+rax+00h]
0x14003d0d6  mov     ebx, 208h
0x14003d0db  xor     edx, edx; dwFlags
0x14003d0dd  mov     rcx, rax; hHeap
0x14003d0e0  mov     r8d, ebx; dwBytes
0x14003d0e3  call    cs:__imp_HeapAlloc
0x14003d0ea  nop     dword ptr [rax+rax+00h]
0x14003d0ef  mov     rsi, rax
0x14003d0f2  test    rax, rax
0x14003d0f5  jnz     short loc_14003D123
0x14003d0f7  mov     eax, 8007000Eh
0x14003d0fc  lea     r8, aDefaultcabandu; "DefaultCabAndUpload"
0x14003d103  mov     r9d, 3A2h
0x14003d109  mov     [rsp+38h+var_18], eax
0x14003d10d  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003d114  mov     ebx, eax
0x14003d116  lea     ecx, [rsi+1]; Level
0x14003d119  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003d11e  jmp     loc_14003D274
0x14003d123  call    cs:__imp_GetProcessHeap
0x14003d12a  nop     dword ptr [rax+rax+00h]
0x14003d12f  mov     r8, rbx; dwBytes
0x14003d132  xor     edx, edx; dwFlags
0x14003d134  mov     rcx, rax; hHeap
0x14003d137  call    cs:__imp_HeapAlloc
0x14003d13e  nop     dword ptr [rax+rax+00h]
0x14003d143  mov     rdi, rax
0x14003d146  test    rax, rax
0x14003d149  jnz     short loc_14003D161
0x14003d14b  mov     eax, 8007000Eh
0x14003d150  mov     r9d, 3A3h
0x14003d156  mov     ebx, eax
0x14003d158  mov     [rsp+38h+var_18], eax
0x14003d15c  jmp     loc_14003D217
0x14003d161  mov     rcx, rdi; lpTempFileName
0x14003d164  call    ?GetTemporaryFileName@@YAJPEAG@Z; GetTemporaryFileName(ushort *)
0x14003d169  mov     ebx, eax
0x14003d16b  test    eax, eax
0x14003d16d  jns     short loc_14003D17E
0x14003d16f  mov     [rsp+38h+var_18], eax
0x14003d173  mov     r9d, 3A9h
0x14003d179  jmp     loc_14003D217
0x14003d17e  lea     r9, [rsp+38h+FilePart]; lpFilePart
0x14003d183  mov     r8, rsi; lpBuffer
0x14003d186  mov     edx, 104h; nBufferLength
0x14003d18b  mov     rcx, rdi; lpFileName
0x14003d18e  call    cs:__imp_GetFullPathNameW
0x14003d195  nop     dword ptr [rax+rax+00h]
0x14003d19a  dec     eax
0x14003d19c  cmp     eax, 103h
0x14003d1a1  ja      short loc_14003D208
0x14003d1a3  mov     rcx, [rsp+38h+FilePart]
0x14003d1a8  cmp     rcx, rsi
0x14003d1ab  jbe     short loc_14003D208
0x14003d1ad  xor     eax, eax
0x14003d1af  mov     [rcx-2], ax
0x14003d1b3  xor     ecx, ecx; int
0x14003d1b5  call    ?MakeHistoryDirectory@@YAJH@Z; MakeHistoryDirectory(int)
0x14003d1ba  mov     ebx, eax
0x14003d1bc  test    eax, eax
0x14003d1be  jns     short loc_14003D1CC
0x14003d1c0  mov     [rsp+38h+var_18], eax
0x14003d1c4  mov     r9d, 3BCh
0x14003d1ca  jmp     short loc_14003D217
0x14003d1cc  mov     rdx, [rsp+38h+FilePart]; unsigned __int16 *
0x14003d1d1  xor     r9d, r9d; int
0x14003d1d4  mov     rcx, rsi; unsigned __int16 *
0x14003d1d7  call    ?CreateCabFromPath@@YAJPEBG0PEAGH@Z; CreateCabFromPath(ushort const *,ushort const *,ushort *,int)
0x14003d1dc  mov     ebx, eax
0x14003d1de  test    eax, eax
0x14003d1e0  jns     short loc_14003D1EE
0x14003d1e2  mov     [rsp+38h+var_18], eax
0x14003d1e6  mov     r9d, 3BFh
0x14003d1ec  jmp     short loc_14003D217
0x14003d1ee  mov     rcx, rdi; unsigned __int16 *
0x14003d1f1  call    ?UploadFile@@YAJPEAG@Z; UploadFile(ushort *)
0x14003d1f6  mov     ebx, eax
0x14003d1f8  test    eax, eax
0x14003d1fa  jns     short loc_14003D22F
0x14003d1fc  mov     [rsp+38h+var_18], eax
0x14003d200  mov     r9d, 3C2h
0x14003d206  jmp     short loc_14003D217
0x14003d208  mov     ebx, 80028016h
0x14003d20d  mov     r9d, 3B2h
0x14003d213  mov     [rsp+38h+var_18], ebx
0x14003d217  lea     r8, aDefaultcabandu; "DefaultCabAndUpload"
0x14003d21e  mov     ecx, 1; Level
0x14003d223  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003d22a  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003d22f  call    cs:__imp_GetProcessHeap
0x14003d236  nop     dword ptr [rax+rax+00h]
0x14003d23b  mov     r8, rsi; lpMem
0x14003d23e  xor     edx, edx; dwFlags
0x14003d240  mov     rcx, rax; hHeap
0x14003d243  call    cs:__imp_HeapFree
0x14003d24a  nop     dword ptr [rax+rax+00h]
0x14003d24f  test    rdi, rdi
0x14003d252  jz      short loc_14003D274
0x14003d254  call    cs:__imp_GetProcessHeap
0x14003d25b  nop     dword ptr [rax+rax+00h]
0x14003d260  mov     r8, rdi; lpMem
0x14003d263  xor     edx, edx; dwFlags
0x14003d265  mov     rcx, rax; hHeap
0x14003d268  call    cs:__imp_HeapFree
0x14003d26f  nop     dword ptr [rax+rax+00h]
0x14003d274  mov     rsi, [rsp+38h+arg_10]
0x14003d279  mov     eax, ebx
0x14003d27b  mov     rbx, [rsp+38h+arg_8]
0x14003d280  add     rsp, 30h
0x14003d284  pop     rdi
0x14003d285  retn
```
