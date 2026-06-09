# TLSDATA::init(void)

- ea: `0x1800a25a8`
- end: `0x1800a261b`
- name: `?init@TLSDATA@@QEAAHXZ`
- size: `115`
- prototype: `int __fastcall(TLSDATA *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800909f8`
- `0x1800d6f64`

## callees

- `0x1800a25a8`
- `0x1800c55c8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a25ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a25ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a25b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a25b5`

## pseudocode

```c
_BOOL8 __fastcall TLSDATA::init(TLSDATA *this)
{
  DWORD CurrentThreadId; // eax
  HANDLE v3; // rcx
  _SYS_EXCEPTION_RECORD *v4; // rdi

  CurrentThreadId = GetCurrentThreadId();
  v3 = g_hMsxmlHeap;
  this->_dwTID = CurrentThreadId;
  this->_pDelayedFinalizeNodes = 0;
  this->_dwDelayedFinalizeDepth = 0;
  this->_fLatestExceptionOfStackOverflowHandling = 0;
  v4 = (_SYS_EXCEPTION_RECORD *)HeapAlloc(v3, 8u, 0xD70u);
  if ( !v4 )
    failure_tracing::record();
  this->_pLatestExceptionOfStackOverflow = v4;
  return v4 != 0;
}

```

## disassembly

```asm
0x1800a25a8  mov     [rsp+arg_0], rbx
0x1800a25ad  push    rdi
0x1800a25ae  sub     rsp, 20h
0x1800a25b2  mov     rbx, this
0x1800a25b5  call    cs:__imp_GetCurrentThreadId
0x1800a25bc  nop     dword ptr [rax+rax+00h]
0x1800a25c1  mov     this, cs:?g_hMsxmlHeap@@3PEAXEA; hHeap
0x1800a25c8  mov     edx, 8; dwFlags
0x1800a25cd  mov     r8d, 0D70h; dwBytes
0x1800a25d3  mov     [rbx+24h], eax
0x1800a25d6  mov     qword ptr [rbx+38h], 0
0x1800a25de  mov     qword ptr [rbx+40h], 0
0x1800a25e6  mov     byte ptr [rbx+20h], 0
0x1800a25ea  call    cs:__imp_HeapAlloc
0x1800a25f1  nop     dword ptr [rax+rax+00h]
0x1800a25f6  mov     rdi, rax
0x1800a25f9  test    rax, rax
0x1800a25fc  jnz     short loc_1800A2603
0x1800a25fe  call    ?record@failure_tracing@@SAXXZ; failure_tracing::record(void)
0x1800a2603  xor     eax, eax
0x1800a2605  mov     [rbx+18h], rdi
0x1800a2609  mov     rbx, [rsp+28h+arg_0]
0x1800a260e  test    rdi, rdi
0x1800a2611  setnz   al
0x1800a2614  add     rsp, 20h
0x1800a2618  pop     rdi
0x1800a2619  retn
```
