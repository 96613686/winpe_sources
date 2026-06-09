# TLSDATA::init(void)

- ea: `0x1800a22e0`
- end: `0x1800a2346`
- name: `?init@TLSDATA@@QEAAHXZ`
- size: `102`
- prototype: `int __fastcall(TLSDATA *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180090ab0`
- `0x1800d52a4`

## callees

- `0x1800a22e0`
- `0x1800c3c0c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a231c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a231c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a22ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a22ed`

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
0x1800a22e0  mov     [rsp+arg_0], rbx
0x1800a22e5  push    rdi
0x1800a22e6  sub     rsp, 20h
0x1800a22ea  mov     rbx, this
0x1800a22ed  call    cs:__imp_GetCurrentThreadId
0x1800a22f3  mov     this, cs:?g_hMsxmlHeap@@3PEAXEA; hHeap
0x1800a22fa  mov     edx, 8; dwFlags
0x1800a22ff  mov     r8d, 0D70h; dwBytes
0x1800a2305  mov     [rbx+24h], eax
0x1800a2308  mov     qword ptr [rbx+38h], 0
0x1800a2310  mov     qword ptr [rbx+40h], 0
0x1800a2318  mov     byte ptr [rbx+20h], 0
0x1800a231c  call    cs:__imp_HeapAlloc
0x1800a2322  mov     rdi, rax
0x1800a2325  test    rax, rax
0x1800a2328  jnz     short loc_1800A232F
0x1800a232a  call    ?record@failure_tracing@@SAXXZ; failure_tracing::record(void)
0x1800a232f  xor     eax, eax
0x1800a2331  mov     [rbx+18h], rdi
0x1800a2335  mov     rbx, [rsp+28h+arg_0]
0x1800a233a  test    rdi, rdi
0x1800a233d  setnz   al
0x1800a2340  add     rsp, 20h
0x1800a2344  pop     rdi
0x1800a2345  retn
```
