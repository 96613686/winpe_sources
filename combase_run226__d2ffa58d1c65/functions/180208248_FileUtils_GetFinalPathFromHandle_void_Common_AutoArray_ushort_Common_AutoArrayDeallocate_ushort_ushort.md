# FileUtils::GetFinalPathFromHandle(void *,Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> &)

- ea: `0x180208248`
- end: `0x180208352`
- name: `?GetFinalPathFromHandle@FileUtils@@YAJPEAXAEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@@Z`
- size: `266`
- prototype: `HRESULT __fastcall(void *pathHandle, Common::AutoArray<unsigned short,&Common::AutoArrayDeallocate<unsigned short> > *finalPath)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1801a3934`
- `0x180208394`

## callees

- `0x18003a8bc`
- `0x18003cf8c`
- `0x180208248`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180208262`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1802082e1`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180208262`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1802082e1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1802082a6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1802082a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18020830f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18020832a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180208341`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18020830f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18020832a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180208341`

## string_xrefs

- `0x180208273`: `onecore\base\appmodel\common\fileutils.cpp`
- `0x1802082b9`: `onecore\base\appmodel\common\fileutils.cpp`
- `0x1802082f0`: `onecore\base\appmodel\common\fileutils.cpp`

## pseudocode

```c
HRESULT __fastcall FileUtils::GetFinalPathFromHandle(
        void *pathHandle,
        Common::AutoArray<unsigned short,&Common::AutoArrayDeallocate<unsigned short> > *finalPath)
{
  DWORD FinalPathNameByHandleW; // eax
  unsigned __int64 v5; // rdi
  SIZE_T v7; // rax
  wchar_t *v8; // rax
  wchar_t *v9; // rbx
  int v10; // ebx
  HRESULT LastError; // edi
  void *retaddr; // [rsp+48h] [rbp+0h]

  FinalPathNameByHandleW = GetFinalPathNameByHandleW(pathHandle, 0, 0, 1u);
  v5 = FinalPathNameByHandleW;
  if ( !FinalPathNameByHandleW )
    return wil::details::in1diag3::Return_GetLastError(retaddr, 0x20u, "onecore\\base\\appmodel\\common\\fileutils.cpp");
  v7 = 2LL * FinalPathNameByHandleW;
  if ( !is_mul_ok(v5, 2u) )
    v7 = -1;
  v8 = (wchar_t *)HeapAlloc(g_hHeap, 0, v7);
  v9 = v8;
  if ( v8 )
  {
    if ( GetFinalPathNameByHandleW(pathHandle, v8, v5, 1u) > (unsigned int)v5 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    0x26u,
                    "onecore\\base\\appmodel\\common\\fileutils.cpp");
      HeapFree(g_hHeap, 0, v9);
      return LastError;
    }
    if ( finalPath->p != v9 )
    {
      HeapFree(g_hHeap, 0, finalPath->p);
      finalPath->p = v9;
    }
    v10 = 0;
  }
  else
  {
    v10 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, 0x23u, "onecore\\base\\appmodel\\common\\fileutils.cpp", -2147024882);
  }
  HeapFree(g_hHeap, 0, 0);
  return v10;
}

```

## disassembly

```asm
0x180208248  push    rbx
0x18020824a  push    rbp
0x18020824b  push    rsi
0x18020824c  push    rdi
0x18020824d  sub     rsp, 28h
0x180208251  mov     rsi, finalPath
0x180208254  mov     r9d, 1; dwFlags
0x18020825a  xor     edx, edx; lpszFilePath
0x18020825c  xor     r8d, r8d; cchFilePath
0x18020825f  mov     rbp, pathHandle
0x180208262  call    cs:__imp_GetFinalPathNameByHandleW
0x180208268  mov     edi, eax
0x18020826a  test    eax, eax
0x18020826c  jnz     short loc_180208287
0x18020826e  mov     pathHandle, [rsp+48h]; callerReturnAddress
0x180208273  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\fileut"...
0x18020827a  lea     edx, [rax+20h]; lineNumber
0x18020827d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180208282  jmp     loc_180208349
0x180208287  mov     pathHandle, 0FFFFFFFFFFFFFFFFh
0x18020828e  mov     eax, 2
0x180208293  mul     rdi
0x180208296  cmovb   rax, pathHandle
0x18020829a  mov     pathHandle, cs:?g_hHeap@@3QEAXEA; hHeap
0x1802082a1  mov     r8, rax; dwBytes
0x1802082a4  xor     edx, edx; dwFlags
0x1802082a6  call    cs:__imp_HeapAlloc
0x1802082ac  mov     rbx, rax
0x1802082af  test    rax, rax
0x1802082b2  jnz     short loc_1802082D2
0x1802082b4  mov     pathHandle, [rsp+48h]; callerReturnAddress
0x1802082b9  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\fileut"...
0x1802082c0  mov     ebx, 8007000Eh
0x1802082c5  lea     edx, [rax+23h]; lineNumber
0x1802082c8  mov     r9d, ebx; hr
0x1802082cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802082d0  jmp     short loc_180208335
0x1802082d2  mov     r9d, 1; dwFlags
0x1802082d8  mov     r8d, edi; cchFilePath
0x1802082db  mov     finalPath, rbx; lpszFilePath
0x1802082de  mov     pathHandle, rbp; hFile
0x1802082e1  call    cs:__imp_GetFinalPathNameByHandleW
0x1802082e7  cmp     eax, edi
0x1802082e9  jbe     short loc_180208319
0x1802082eb  mov     pathHandle, [rsp+48h]; callerReturnAddress
0x1802082f0  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\fileut"...
0x1802082f7  mov     edx, 26h ; '&'; lineNumber
0x1802082fc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180208301  mov     pathHandle, cs:?g_hHeap@@3QEAXEA; hHeap
0x180208308  mov     r8, rbx; lpMem
0x18020830b  xor     edx, edx; dwFlags
0x18020830d  mov     edi, eax
0x18020830f  call    cs:__imp_HeapFree
0x180208315  mov     eax, edi
0x180208317  jmp     short loc_180208349
0x180208319  cmp     [rsi], rbx
0x18020831c  jz      short loc_180208333
0x18020831e  mov     r8, [rsi]; lpMem
0x180208321  xor     edx, edx; dwFlags
0x180208323  mov     pathHandle, cs:?g_hHeap@@3QEAXEA; hHeap
0x18020832a  call    cs:__imp_HeapFree
0x180208330  mov     [rsi], rbx
0x180208333  xor     ebx, ebx
0x180208335  mov     pathHandle, cs:?g_hHeap@@3QEAXEA; hHeap
0x18020833c  xor     r8d, r8d; lpMem
0x18020833f  xor     edx, edx; dwFlags
0x180208341  call    cs:__imp_HeapFree
0x180208347  mov     eax, ebx
0x180208349  add     rsp, 28h
0x18020834d  pop     rdi
0x18020834e  pop     rsi
0x18020834f  pop     rbp
0x180208350  pop     rbx
0x180208351  retn
```
