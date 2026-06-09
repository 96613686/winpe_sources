# TLSDATA::init(void)

- ea: `0x100578d2`
- end: `0x10057917`
- name: `?init@TLSDATA@@QAEHXZ`
- size: `69`
- prototype: `int __thiscall(TLSDATA *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x10057b75`
- `0x1005b4c9`

## callees

- `0x100578d2`
- `0x10065f14`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x100578f9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x100578f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x100578d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x100578d8`

## pseudocode

```c
BOOL __thiscall TLSDATA::init(TLSDATA *this)
{
  DWORD CurrentThreadId; // eax
  _SYS_EXCEPTION_RECORD *v3; // edi
  HANDLE v5; // [esp-Ch] [ebp-14h]

  CurrentThreadId = GetCurrentThreadId();
  v5 = g_hMsxmlHeap;
  this->_dwTID = CurrentThreadId;
  this->_pDelayedFinalizeNodes = 0;
  this->_dwDelayedFinalizeDepth = 0;
  this->_fLatestExceptionOfStackOverflowHandling = 0;
  v3 = (_SYS_EXCEPTION_RECORD *)HeapAlloc(v5, 8u, 0x71Cu);
  if ( !v3 )
    failure_tracing::record();
  this->_pLatestExceptionOfStackOverflow = v3;
  return v3 != 0;
}

```

## disassembly

```asm
0x100578d2  mov     edi, edi
0x100578d4  push    esi
0x100578d5  push    edi
0x100578d6  mov     esi, this
0x100578d8  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x100578de  push    71Ch; dwBytes
0x100578e3  push    8; dwFlags
0x100578e5  push    ?g_hMsxmlHeap@@3PAXA; hHeap
0x100578eb  mov     [esi+18h], eax
0x100578ee  xor     eax, eax
0x100578f0  mov     [esi+24h], eax
0x100578f3  mov     [esi+28h], eax
0x100578f6  mov     [esi+14h], al
0x100578f9  call    ds:__imp__HeapAlloc@12; HeapAlloc(x,x,x)
0x100578ff  mov     edi, eax
0x10057901  test    edi, edi
0x10057903  jnz     short loc_1005790A
0x10057905  call    ?record@failure_tracing@@SGXXZ; failure_tracing::record(void)
0x1005790a  xor     eax, eax
0x1005790c  mov     [esi+10h], edi
0x1005790f  test    edi, edi
0x10057911  pop     edi
0x10057912  setnz   al
0x10057915  pop     esi
0x10057916  retn
```
