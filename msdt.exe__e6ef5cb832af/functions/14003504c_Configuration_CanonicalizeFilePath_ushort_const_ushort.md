# Configuration::CanonicalizeFilePath(ushort const *,ushort * *)

- ea: `0x14003504c`
- end: `0x140035165`
- name: `?CanonicalizeFilePath@Configuration@@SAJPEBGPEAPEAG@Z`
- size: `281`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400362b8`
- `0x140036410`
- `0x140036690`
- `0x140037e2c`
- `0x140042a4c`

## callees

- `0x140020420`
- `0x14003504c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400350d4`
- `KERNEL32!GetLastError` at `0x1400350d4`
- `KERNEL32!HeapAlloc` at `0x140035078`
- `KERNEL32!HeapAlloc` at `0x140035078`
- `KERNEL32!HeapFree` at `0x140035141`
- `KERNEL32!HeapFree` at `0x140035141`
- `KERNEL32!GetProcessHeap` at `0x140035061`
- `KERNEL32!GetProcessHeap` at `0x14003512d`
- `KERNEL32!GetProcessHeap` at `0x140035061`
- `KERNEL32!GetProcessHeap` at `0x14003512d`
- `KERNEL32!GetFullPathNameW` at `0x1400350c4`
- `KERNEL32!GetFullPathNameW` at `0x1400350c4`

## string_xrefs

- `0x140035091`: `Configuration::CanonicalizeFilePath`
- `0x140035115`: `Configuration::CanonicalizeFilePath`

## pseudocode

```c
__int64 __fastcall Configuration::CanonicalizeFilePath(LPCWSTR lpFileName, unsigned __int16 **a2)
{
  HANDLE ProcessHeap; // rax
  WCHAR *v5; // rax
  WCHAR *v6; // rdi
  unsigned int v7; // ebx
  DWORD FullPathNameW; // eax
  signed int LastError; // eax
  int v10; // r9d
  HANDLE v11; // rax

  ProcessHeap = GetProcessHeap();
  v5 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x208u);
  v6 = v5;
  if ( v5 )
  {
    FullPathNameW = GetFullPathNameW(lpFileName, 0x103u, v5, 0);
    if ( FullPathNameW )
    {
      v7 = 0;
      if ( FullPathNameW > 0x103 )
      {
        v7 = -2147319786;
        v10 = 1416;
        goto LABEL_10;
      }
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( (v7 & 0x80000000) != 0 )
      {
        v10 = 1413;
LABEL_10:
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Configuration::CanonicalizeFilePath", v10, v7);
        v11 = GetProcessHeap();
        HeapFree(v11, 0, v6);
        return v7;
      }
    }
    *a2 = v6;
    return v7;
  }
  v7 = -2147024882;
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Configuration::CanonicalizeFilePath", 1408, -2147024882);
  return v7;
}

```

## disassembly

```asm
0x14003504c  mov     [rsp+arg_0], rbx
0x140035051  mov     [rsp+arg_8], rsi
0x140035056  push    rdi
0x140035057  sub     rsp, 30h
0x14003505b  mov     rsi, rdx
0x14003505e  mov     rbx, rcx
0x140035061  call    cs:__imp_GetProcessHeap
0x140035068  nop     dword ptr [rax+rax+00h]
0x14003506d  xor     edx, edx; dwFlags
0x14003506f  mov     r8d, 208h; dwBytes
0x140035075  mov     rcx, rax; hHeap
0x140035078  call    cs:__imp_HeapAlloc
0x14003507f  nop     dword ptr [rax+rax+00h]
0x140035084  mov     rdi, rax
0x140035087  test    rax, rax
0x14003508a  jnz     short loc_1400350B6
0x14003508c  mov     ebx, 8007000Eh
0x140035091  lea     r8, aConfigurationC_0; "Configuration::CanonicalizeFilePath"
0x140035098  mov     r9d, 580h
0x14003509e  mov     [rsp+38h+var_18], ebx
0x1400350a2  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400350a9  lea     ecx, [rax+1]; Level
0x1400350ac  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400350b1  jmp     loc_140035152
0x1400350b6  xor     r9d, r9d; lpFilePart
0x1400350b9  mov     r8, rdi; lpBuffer
0x1400350bc  mov     edx, 103h; nBufferLength
0x1400350c1  mov     rcx, rbx; lpFileName
0x1400350c4  call    cs:__imp_GetFullPathNameW
0x1400350cb  nop     dword ptr [rax+rax+00h]
0x1400350d0  test    eax, eax
0x1400350d2  jnz     short loc_1400350FB
0x1400350d4  call    cs:__imp_GetLastError
0x1400350db  nop     dword ptr [rax+rax+00h]
0x1400350e0  mov     ebx, eax
0x1400350e2  test    eax, eax
0x1400350e4  jle     short loc_1400350EF
0x1400350e6  movzx   ebx, ax
0x1400350e9  or      ebx, 80070000h
0x1400350ef  test    ebx, ebx
0x1400350f1  jns     short loc_14003514F
0x1400350f3  mov     r9d, 585h
0x1400350f9  jmp     short loc_14003510F
0x1400350fb  xor     ebx, ebx
0x1400350fd  cmp     eax, 103h
0x140035102  jbe     short loc_14003514F
0x140035104  mov     ebx, 80028016h
0x140035109  mov     r9d, 588h
0x14003510f  mov     eax, ebx
0x140035111  mov     [rsp+38h+var_18], ebx
0x140035115  lea     r8, aConfigurationC_0; "Configuration::CanonicalizeFilePath"
0x14003511c  mov     ecx, 1; Level
0x140035121  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140035128  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003512d  call    cs:__imp_GetProcessHeap
0x140035134  nop     dword ptr [rax+rax+00h]
0x140035139  mov     r8, rdi; lpMem
0x14003513c  xor     edx, edx; dwFlags
0x14003513e  mov     rcx, rax; hHeap
0x140035141  call    cs:__imp_HeapFree
0x140035148  nop     dword ptr [rax+rax+00h]
0x14003514d  jmp     short loc_140035152
0x14003514f  mov     [rsi], rdi
0x140035152  mov     rsi, [rsp+38h+arg_8]
0x140035157  mov     eax, ebx
0x140035159  mov     rbx, [rsp+38h+arg_0]
0x14003515e  add     rsp, 30h
0x140035162  pop     rdi
0x140035163  retn
```
