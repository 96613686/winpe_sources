# GetExeVersionAsString(ushort const *,ushort *,ulong)

- ea: `0x1800084d8`
- end: `0x18000861f`
- name: `?GetExeVersionAsString@@YAHPEBGPEAGK@Z`
- size: `327`
- prototype: `__int64 __fastcall(LPCWSTR lptstrFilename, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180008c38`
- `0x1800096e0`

## callees

- `0x180007b54`
- `0x1800084d8`
- `0x18000e240`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000856a`
- `KERNEL32!HeapAlloc` at `0x18000856a`
- `KERNEL32!GetProcessHeap` at `0x18000855b`
- `KERNEL32!GetProcessHeap` at `0x1800085f6`
- `KERNEL32!GetProcessHeap` at `0x18000855b`
- `KERNEL32!GetProcessHeap` at `0x1800085f6`
- `KERNEL32!HeapFree` at `0x180008604`
- `KERNEL32!HeapFree` at `0x180008604`
- `SHLWAPI!PathFileExistsW` at `0x180008530`
- `SHLWAPI!PathFileExistsW` at `0x180008530`
- `VERSION!GetFileVersionInfoW` at `0x18000858c`
- `VERSION!GetFileVersionInfoW` at `0x18000858c`
- `VERSION!VerQueryValueW` at `0x1800085ad`
- `VERSION!VerQueryValueW` at `0x1800085ad`
- `VERSION!GetFileVersionInfoSizeW` at `0x18000854b`
- `VERSION!GetFileVersionInfoSizeW` at `0x18000854b`

## string_xrefs

- `0x18000851b`: `ExecutablePath: %ws`

## pseudocode

```c
BOOL __fastcall GetExeVersionAsString(LPCWSTR lptstrFilename, unsigned __int16 *a2)
{
  BOOL result; // eax
  BOOL v5; // ebp
  DWORD FileVersionInfoSizeW; // esi
  HANDLE ProcessHeap; // rax
  void *v8; // rax
  void *v9; // rbx
  HANDLE v10; // rax
  __int64 v11; // [rsp+20h] [rbp-48h]
  int v12; // [rsp+28h] [rbp-40h]
  int v13; // [rsp+30h] [rbp-38h]
  LPVOID lpBuffer; // [rsp+40h] [rbp-28h] BYREF
  DWORD dwHandle; // [rsp+80h] [rbp+18h] BYREF
  unsigned int puLen; // [rsp+88h] [rbp+20h] BYREF

  puLen = 0;
  dwHandle = 0;
  lpBuffer = 0;
  AslLogCallPrintf(3, "GetExeVersionAsString", 705, "ExecutablePath: %ws", lptstrFilename);
  result = PathFileExistsW(lptstrFilename);
  if ( result )
  {
    v5 = 0;
    FileVersionInfoSizeW = GetFileVersionInfoSizeW(lptstrFilename, &dwHandle);
    if ( FileVersionInfoSizeW )
    {
      ProcessHeap = GetProcessHeap();
      v8 = HeapAlloc(ProcessHeap, 8u, FileVersionInfoSizeW);
      v9 = v8;
      if ( v8 )
      {
        if ( GetFileVersionInfoW(lptstrFilename, dwHandle, FileVersionInfoSizeW, v8) )
        {
          if ( VerQueryValueW(v9, L"\\", &lpBuffer, &puLen) )
          {
            v13 = *((unsigned __int16 *)lpBuffer + 6);
            v12 = *((unsigned __int16 *)lpBuffer + 7);
            LODWORD(v11) = *((unsigned __int16 *)lpBuffer + 4);
            v5 = (int)StringCchPrintfW(a2, 0x15u, L"%d.%d.%d.%d", *((unsigned __int16 *)lpBuffer + 5), v11, v12, v13) >= 0;
          }
        }
        v10 = GetProcessHeap();
        HeapFree(v10, 0, v9);
      }
    }
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800084d8  mov     rax, rsp
0x1800084db  mov     [rax+8], rbx
0x1800084df  mov     [rax+10h], rbp
0x1800084e3  mov     [rax+18h], r8d
0x1800084e7  push    rsi
0x1800084e8  push    rdi
0x1800084e9  push    r14
0x1800084eb  sub     rsp, 50h
0x1800084ef  mov     r14, rdx
0x1800084f2  mov     [rax-48h], rcx
0x1800084f6  mov     rdi, rcx
0x1800084f9  mov     dword ptr [rax+20h], 0
0x180008500  lea     rdx, aGetexeversiona; "GetExeVersionAsString"
0x180008507  mov     dword ptr [rax+18h], 0
0x18000850e  mov     ecx, 3
0x180008513  mov     qword ptr [rax-28h], 0
0x18000851b  lea     r9, aExecutablepath; "ExecutablePath: %ws"
0x180008522  mov     r8d, 2C1h
0x180008528  call    AslLogCallPrintf
0x18000852d  mov     rcx, rdi; pszPath
0x180008530  call    cs:__imp_PathFileExistsW
0x180008536  test    eax, eax
0x180008538  jz      loc_18000860C
0x18000853e  lea     rdx, [rsp+68h+dwHandle]; lpdwHandle
0x180008546  mov     rcx, rdi; lptstrFilename
0x180008549  xor     ebp, ebp
0x18000854b  call    cs:__imp_GetFileVersionInfoSizeW
0x180008551  mov     esi, eax
0x180008553  test    eax, eax
0x180008555  jz      loc_18000860A
0x18000855b  call    cs:__imp_GetProcessHeap
0x180008561  mov     r8d, esi; dwBytes
0x180008564  lea     edx, [rbp+8]; dwFlags
0x180008567  mov     rcx, rax; hHeap
0x18000856a  call    cs:__imp_HeapAlloc
0x180008570  mov     rbx, rax
0x180008573  test    rax, rax
0x180008576  jz      loc_18000860A
0x18000857c  mov     edx, [rsp+68h+dwHandle]; dwHandle
0x180008583  mov     r9, rax; lpData
0x180008586  mov     r8d, esi; dwLen
0x180008589  mov     rcx, rdi; lptstrFilename
0x18000858c  call    cs:__imp_GetFileVersionInfoW
0x180008592  test    eax, eax
0x180008594  jz      short loc_1800085F6
0x180008596  lea     r9, [rsp+68h+puLen]; puLen
0x18000859e  mov     rcx, rbx; pBlock
0x1800085a1  lea     r8, [rsp+68h+lpBuffer]; lplpBuffer
0x1800085a6  lea     rdx, asc_18001D1B4; "\\"
0x1800085ad  call    cs:__imp_VerQueryValueW
0x1800085b3  test    eax, eax
0x1800085b5  jz      short loc_1800085F6
0x1800085b7  mov     r8, [rsp+68h+lpBuffer]
0x1800085bc  movzx   ecx, word ptr [r8+0Eh]
0x1800085c1  movzx   edx, word ptr [r8+8]
0x1800085c6  movzx   eax, word ptr [r8+0Ch]
0x1800085cb  movzx   r9d, word ptr [r8+0Ah]
0x1800085d0  lea     r8, aDDDD; "%d.%d.%d.%d"
0x1800085d7  mov     [rsp+68h+var_38], eax
0x1800085db  mov     [rsp+68h+var_40], ecx
0x1800085df  mov     rcx, r14; unsigned __int16 *
0x1800085e2  mov     dword ptr [rsp+68h+var_48], edx
0x1800085e6  lea     edx, [rbp+15h]; unsigned __int64
0x1800085e9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800085ee  test    eax, eax
0x1800085f0  lea     ecx, [rbp+1]
0x1800085f3  cmovns  ebp, ecx
0x1800085f6  call    cs:__imp_GetProcessHeap
0x1800085fc  mov     r8, rbx; lpMem
0x1800085ff  xor     edx, edx; dwFlags
0x180008601  mov     rcx, rax; hHeap
0x180008604  call    cs:__imp_HeapFree
0x18000860a  mov     eax, ebp
0x18000860c  mov     rbx, [rsp+68h+arg_0]
0x180008611  mov     rbp, [rsp+68h+arg_8]
0x180008616  add     rsp, 50h
0x18000861a  pop     r14
0x18000861c  pop     rdi
0x18000861d  pop     rsi
0x18000861e  retn
```
