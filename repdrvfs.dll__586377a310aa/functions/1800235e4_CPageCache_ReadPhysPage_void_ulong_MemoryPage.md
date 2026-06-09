# CPageCache::ReadPhysPage(void *,ulong,MemoryPage * *)

- ea: `0x1800235e4`
- end: `0x1800237a8`
- name: `?ReadPhysPage@CPageCache@@SAKPEAXKPEAPEAVMemoryPage@@@Z`
- size: `452`
- prototype: `unsigned int __fastcall(HANDLE hFile, unsigned int, struct MemoryPage **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002496c`
- `0x180030374`

## callees

- `0x1800012b8`
- `0x18000f8f0`
- `0x1800235e4`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002360d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002360d`
- `wbemcomn!GetMemLogObject` at `0x1800236b1`
- `wbemcomn!GetMemLogObject` at `0x180023712`
- `wbemcomn!GetMemLogObject` at `0x18002374c`
- `wbemcomn!GetMemLogObject` at `0x1800236b1`
- `wbemcomn!GetMemLogObject` at `0x180023712`
- `wbemcomn!GetMemLogObject` at `0x18002374c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800236c1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180023722`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002375c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800236c1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180023722`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002375c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002368f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002368f`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002365c`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002365c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800236fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023704`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800236fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023704`

## pseudocode

```c
DWORD __fastcall CPageCache::ReadPhysPage(HANDLE hFile, unsigned int a2, LPVOID **a3)
{
  LPVOID *v6; // rax
  LPVOID *v7; // rbx
  CMemoryLog *MemLogObject; // rax
  unsigned int v10; // ebx
  CVarObjHeap *v11; // rcx
  __int64 v12; // rdx
  CMemoryLog *v13; // rax
  CMemoryLog *v14; // rax
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp+18h] BYREF
  LPVOID *v16; // [rsp+68h] [rbp+20h]

  if ( !a3 )
  {
    MemLogObject = GetMemLogObject();
    v10 = 87;
    CMemoryLog::Write(MemLogObject, 87);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v10;
    }
    v12 = 38;
    goto LABEL_21;
  }
  *a3 = 0;
  v6 = (LPVOID *)CWin32DefaultArena::WbemMemAlloc(0x2020u);
  v16 = v6;
  v7 = v6;
  if ( !v6 )
  {
    v14 = GetMemLogObject();
    v10 = 14;
    CMemoryLog::Write(v14, 14);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v10;
    }
    v12 = 39;
LABEL_21:
    WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, v10);
    return v10;
  }
  *(_DWORD *)v6 = 1313820496;
  *((_DWORD *)v6 + 1) = 1347374926;
  *((_DWORD *)v6 + 2) = 1;
  *((_BYTE *)v6 + 24) = 0;
  v6[2] = v6 + 4;
  if ( SetFilePointerEx(hFile, (LARGE_INTEGER)((unsigned __int64)a2 << 13), 0, 0) )
  {
    NumberOfBytesRead = 0;
    if ( ReadFile(hFile, v7[2], 0x2000u, &NumberOfBytesRead, 0) && NumberOfBytesRead == 0x2000 )
    {
      *a3 = v7;
      return 0;
    }
    GetLastError();
    MemoryPage::Release((MemoryPage *)v7);
    v13 = GetMemLogObject();
    v10 = 87;
    CMemoryLog::Write(v13, 87);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v10;
    }
    v12 = 40;
    goto LABEL_21;
  }
  MemoryPage::Release((MemoryPage *)v7);
  return GetLastError();
}

```

## disassembly

```asm
0x1800235e4  mov     [rsp+arg_0], rbx
0x1800235e9  push    rbp
0x1800235ea  push    rsi
0x1800235eb  push    rdi
0x1800235ec  sub     rsp, 30h
0x1800235f0  mov     ebp, edx
0x1800235f2  mov     rdi, r8
0x1800235f5  mov     rsi, rcx
0x1800235f8  test    r8, r8
0x1800235fb  jz      loc_1800236B1
0x180023601  mov     ecx, 2020h
0x180023606  mov     qword ptr [r8], 0
0x18002360d  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180023613  mov     [rsp+48h+arg_18], rax
0x180023618  mov     rbx, rax
0x18002361b  test    rax, rax
0x18002361e  jz      loc_18002374C
0x180023624  mov     dword ptr [rax], 4E4F4F50h
0x18002362a  mov     dword ptr [rax+4], 504F4F4Eh
0x180023631  mov     dword ptr [rax+8], 1
0x180023638  mov     byte ptr [rax+18h], 0
0x18002363c  add     rax, 20h ; ' '
0x180023640  mov     [rbx+10h], rax
0x180023644  test    rbx, rbx
0x180023647  jz      loc_18002374C
0x18002364d  mov     edx, ebp
0x18002364f  xor     r9d, r9d; dwMoveMethod
0x180023652  shl     rdx, 0Dh; liDistanceToMove
0x180023656  xor     r8d, r8d; lpNewFilePointer
0x180023659  mov     rcx, rsi; hFile
0x18002365c  call    cs:__imp_SetFilePointerEx
0x180023662  test    eax, eax
0x180023664  jz      loc_1800236F4
0x18002366a  mov     [rsp+48h+NumberOfBytesRead], 0
0x180023672  lea     r9, [rsp+48h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180023677  mov     rdx, [rbx+10h]; lpBuffer
0x18002367b  mov     ebp, 2000h
0x180023680  mov     r8d, ebp; nNumberOfBytesToRead
0x180023683  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x18002368c  mov     rcx, rsi; hFile
0x18002368f  call    cs:__imp_ReadFile
0x180023695  test    eax, eax
0x180023697  jz      short loc_180023704
0x180023699  cmp     [rsp+48h+NumberOfBytesRead], ebp
0x18002369d  jnz     short loc_180023704
0x18002369f  mov     [rdi], rbx
0x1800236a2  xor     eax, eax
0x1800236a4  mov     rbx, [rsp+48h+arg_0]
0x1800236a9  add     rsp, 30h
0x1800236ad  pop     rdi
0x1800236ae  pop     rsi
0x1800236af  pop     rbp
0x1800236b0  retn
0x1800236b1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800236b7  mov     ebx, 57h ; 'W'
0x1800236bc  mov     rcx, rax
0x1800236bf  mov     edx, ebx
0x1800236c1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800236c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800236ce  lea     rax, WPP_GLOBAL_Control
0x1800236d5  cmp     rcx, rax
0x1800236d8  jnz     short loc_1800236DE
0x1800236da  mov     eax, ebx
0x1800236dc  jmp     short loc_1800236A4
0x1800236de  test    byte ptr [rcx+1Ch], 1
0x1800236e2  jz      short loc_1800236DA
0x1800236e4  cmp     byte ptr [rcx+19h], 2
0x1800236e8  jb      short loc_1800236DA
0x1800236ea  mov     edx, 26h ; '&'
0x1800236ef  jmp     loc_180023790
0x1800236f4  mov     rcx, rbx; this
0x1800236f7  call    ?Release@MemoryPage@@QEAAJXZ; MemoryPage::Release(void)
0x1800236fc  call    cs:__imp_GetLastError
0x180023702  jmp     short loc_1800236A4
0x180023704  call    cs:__imp_GetLastError
0x18002370a  mov     rcx, rbx; this
0x18002370d  call    ?Release@MemoryPage@@QEAAJXZ; MemoryPage::Release(void)
0x180023712  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180023718  mov     ebx, 57h ; 'W'
0x18002371d  mov     rcx, rax
0x180023720  mov     edx, ebx
0x180023722  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180023728  mov     rcx, cs:WPP_GLOBAL_Control
0x18002372f  lea     rax, WPP_GLOBAL_Control
0x180023736  cmp     rcx, rax
0x180023739  jz      short loc_1800236DA
0x18002373b  test    byte ptr [rcx+1Ch], 1
0x18002373f  jz      short loc_1800236DA
0x180023741  cmp     byte ptr [rcx+19h], 2
0x180023745  jb      short loc_1800236DA
0x180023747  lea     edx, [rbx-2Fh]
0x18002374a  jmp     short loc_180023790
0x18002374c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180023752  mov     ebx, 0Eh
0x180023757  mov     rcx, rax
0x18002375a  mov     edx, ebx
0x18002375c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180023762  mov     rcx, cs:WPP_GLOBAL_Control
0x180023769  lea     rax, WPP_GLOBAL_Control
0x180023770  cmp     rcx, rax
0x180023773  jz      loc_1800236DA
0x180023779  test    byte ptr [rcx+1Ch], 1
0x18002377d  jz      loc_1800236DA
0x180023783  cmp     byte ptr [rcx+19h], 2
0x180023787  jb      loc_1800236DA
0x18002378d  lea     edx, [rbx+19h]
0x180023790  mov     rcx, [rcx+10h]
0x180023794  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18002379b  mov     r9d, ebx
0x18002379e  call    WPP_SF_d
0x1800237a3  jmp     loc_1800236DA
```
