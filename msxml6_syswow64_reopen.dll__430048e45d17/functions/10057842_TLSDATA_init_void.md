# TLSDATA::init(void)

- ea: `0x10057842`
- end: `0x10057887`
- name: `?init@TLSDATA@@QAEHXZ`
- size: `69`
- prototype: `int __thiscall(TLSDATA *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x10057ae5`
- `0x1005b439`

## callees

- `0x10057842`
- `0x10065e74`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10057869`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10057869`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10057848`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10057848`

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
0x10057842  mov     edi, edi
0x10057844  push    esi
0x10057845  push    edi
0x10057846  mov     esi, this
0x10057848  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1005784e  push    71Ch; dwBytes
0x10057853  push    8; dwFlags
0x10057855  push    ?g_hMsxmlHeap@@3PAXA; hHeap
0x1005785b  mov     [esi+18h], eax
0x1005785e  xor     eax, eax
0x10057860  mov     [esi+24h], eax
0x10057863  mov     [esi+28h], eax
0x10057866  mov     [esi+14h], al
0x10057869  call    ds:__imp__HeapAlloc@12; HeapAlloc(x,x,x)
0x1005786f  mov     edi, eax
0x10057871  test    edi, edi
0x10057873  jnz     short loc_1005787A
0x10057875  call    ?record@failure_tracing@@SGXXZ; failure_tracing::record(void)
0x1005787a  xor     eax, eax
0x1005787c  mov     [esi+10h], edi
0x1005787f  test    edi, edi
0x10057881  pop     edi
0x10057882  setnz   al
0x10057885  pop     esi
0x10057886  retn
```
