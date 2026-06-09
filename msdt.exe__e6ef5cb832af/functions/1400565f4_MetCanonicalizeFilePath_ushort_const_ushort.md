# MetCanonicalizeFilePath(ushort const *,ushort * *)

- ea: `0x1400565f4`
- end: `0x14005670b`
- name: `?MetCanonicalizeFilePath@@YAJPEBGPEAPEAG@Z`
- size: `279`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140052d60`
- `0x140052f10`
- `0x1400531d0`
- `0x14005421c`
- `0x1400556c0`

## callees

- `0x140020420`
- `0x1400565f4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14005667a`
- `KERNEL32!GetLastError` at `0x14005667a`
- `KERNEL32!HeapAlloc` at `0x140056620`
- `KERNEL32!HeapAlloc` at `0x140056620`
- `KERNEL32!HeapFree` at `0x1400566e7`
- `KERNEL32!HeapFree` at `0x1400566e7`
- `KERNEL32!GetProcessHeap` at `0x140056609`
- `KERNEL32!GetProcessHeap` at `0x1400566d3`
- `KERNEL32!GetProcessHeap` at `0x140056609`
- `KERNEL32!GetProcessHeap` at `0x1400566d3`
- `KERNEL32!GetFullPathNameW` at `0x14005666a`
- `KERNEL32!GetFullPathNameW` at `0x14005666a`

## string_xrefs

- `0x14005663d`: `MetCanonicalizeFilePath`
- `0x1400566bb`: `MetCanonicalizeFilePath`

## pseudocode

```c
__int64 __fastcall MetCanonicalizeFilePath(LPCWSTR lpFileName, unsigned __int16 **a2)
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
        v10 = 112;
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
        v10 = 109;
LABEL_10:
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetCanonicalizeFilePath", v10, v7);
        v11 = GetProcessHeap();
        HeapFree(v11, 0, v6);
        return v7;
      }
    }
    *a2 = v6;
    return v7;
  }
  v7 = -2147024882;
  SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetCanonicalizeFilePath", 104, -2147024882);
  return v7;
}

```

## disassembly

```asm
0x1400565f4  mov     [rsp+arg_0], rbx
0x1400565f9  mov     [rsp+arg_8], rsi
0x1400565fe  push    rdi
0x1400565ff  sub     rsp, 30h
0x140056603  mov     rsi, rdx
0x140056606  mov     rbx, rcx
0x140056609  call    cs:__imp_GetProcessHeap
0x140056610  nop     dword ptr [rax+rax+00h]
0x140056615  xor     edx, edx; dwFlags
0x140056617  mov     r8d, 208h; dwBytes
0x14005661d  mov     rcx, rax; hHeap
0x140056620  call    cs:__imp_HeapAlloc
0x140056627  nop     dword ptr [rax+rax+00h]
0x14005662c  mov     rdi, rax
0x14005662f  test    rax, rax
0x140056632  jnz     short loc_14005665C
0x140056634  mov     ebx, 8007000Eh
0x140056639  lea     r9d, [rax+68h]
0x14005663d  lea     r8, aMetcanonicaliz; "MetCanonicalizeFilePath"
0x140056644  mov     [rsp+38h+var_18], ebx
0x140056648  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x14005664f  lea     ecx, [rax+1]; Level
0x140056652  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140056657  jmp     loc_1400566F8
0x14005665c  xor     r9d, r9d; lpFilePart
0x14005665f  mov     r8, rdi; lpBuffer
0x140056662  mov     edx, 103h; nBufferLength
0x140056667  mov     rcx, rbx; lpFileName
0x14005666a  call    cs:__imp_GetFullPathNameW
0x140056671  nop     dword ptr [rax+rax+00h]
0x140056676  test    eax, eax
0x140056678  jnz     short loc_1400566A1
0x14005667a  call    cs:__imp_GetLastError
0x140056681  nop     dword ptr [rax+rax+00h]
0x140056686  mov     ebx, eax
0x140056688  test    eax, eax
0x14005668a  jle     short loc_140056695
0x14005668c  movzx   ebx, ax
0x14005668f  or      ebx, 80070000h
0x140056695  test    ebx, ebx
0x140056697  jns     short loc_1400566F5
0x140056699  mov     r9d, 6Dh ; 'm'
0x14005669f  jmp     short loc_1400566B5
0x1400566a1  xor     ebx, ebx
0x1400566a3  cmp     eax, 103h
0x1400566a8  jbe     short loc_1400566F5
0x1400566aa  mov     ebx, 80028016h
0x1400566af  mov     r9d, 70h ; 'p'
0x1400566b5  mov     eax, ebx
0x1400566b7  mov     [rsp+38h+var_18], ebx
0x1400566bb  lea     r8, aMetcanonicaliz; "MetCanonicalizeFilePath"
0x1400566c2  mov     ecx, 1; Level
0x1400566c7  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x1400566ce  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400566d3  call    cs:__imp_GetProcessHeap
0x1400566da  nop     dword ptr [rax+rax+00h]
0x1400566df  mov     r8, rdi; lpMem
0x1400566e2  xor     edx, edx; dwFlags
0x1400566e4  mov     rcx, rax; hHeap
0x1400566e7  call    cs:__imp_HeapFree
0x1400566ee  nop     dword ptr [rax+rax+00h]
0x1400566f3  jmp     short loc_1400566F8
0x1400566f5  mov     [rsi], rdi
0x1400566f8  mov     rsi, [rsp+38h+arg_8]
0x1400566fd  mov     eax, ebx
0x1400566ff  mov     rbx, [rsp+38h+arg_0]
0x140056704  add     rsp, 30h
0x140056708  pop     rdi
0x140056709  retn
```
