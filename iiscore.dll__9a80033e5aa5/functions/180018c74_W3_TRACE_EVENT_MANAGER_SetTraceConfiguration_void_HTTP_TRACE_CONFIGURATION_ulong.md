# W3_TRACE_EVENT_MANAGER::SetTraceConfiguration(void *,HTTP_TRACE_CONFIGURATION *,ulong)

- ea: `0x180018c74`
- end: `0x180018cea`
- name: `?SetTraceConfiguration@W3_TRACE_EVENT_MANAGER@@QEAAJPEAXPEAUHTTP_TRACE_CONFIGURATION@@K@Z`
- size: `118`
- prototype: `__int64 __fastcall(W3_TRACE_EVENT_MANAGER *__hidden this, void *, struct HTTP_TRACE_CONFIGURATION *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001e4e0`
- `0x180022e20`

## callees

- `0x180018c74`
- `0x18002fb14`

## import_xrefs

- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180018ca1`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180018ca1`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180018cd5`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180018cd5`

## pseudocode

```c
__int64 __fastcall W3_TRACE_EVENT_MANAGER::SetTraceConfiguration(
        W3_TRACE_EVENT_MANAGER *this,
        void *a2,
        struct HTTP_TRACE_CONFIGURATION *a3,
        unsigned int a4)
{
  int v9; // esi
  __int64 i; // rdi

  if ( !a3 )
    return 2147942487LL;
  v9 = 0;
  if ( *((_BYTE *)this + 44) )
    CReaderWriterLock3::WriteLock(this);
  for ( i = 0; (unsigned int)i < a4; i = (unsigned int)(i + 1) )
  {
    v9 = W3_TRACE_EVENT_MANAGER::SetTraceConfigurationWorker(this, a2, &a3[i]);
    if ( v9 < 0 )
      break;
  }
  if ( *((_BYTE *)this + 44) )
    CReaderWriterLock3::WriteUnlock(this);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180018c74  push    rbx
0x180018c76  push    rbp
0x180018c77  push    rsi
0x180018c78  push    rdi
0x180018c79  push    r14
0x180018c7b  push    r15
0x180018c7d  sub     rsp, 28h
0x180018c81  mov     ebp, r9d
0x180018c84  mov     r14, r8
0x180018c87  mov     r15, rdx
0x180018c8a  mov     rbx, rcx
0x180018c8d  test    r8, r8
0x180018c90  jnz     short loc_180018C99
0x180018c92  mov     eax, 80070057h
0x180018c97  jmp     short loc_180018CDD
0x180018c99  xor     esi, esi
0x180018c9b  cmp     [rcx+2Ch], sil
0x180018c9f  jz      short loc_180018CA7
0x180018ca1  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180018ca7  xor     edi, edi
0x180018ca9  test    ebp, ebp
0x180018cab  jz      short loc_180018CCC
0x180018cad  lea     rcx, [rdi+rdi*2]
0x180018cb1  mov     rdx, r15; void *
0x180018cb4  lea     r8, [r14+rcx*8]; struct HTTP_TRACE_CONFIGURATION *
0x180018cb8  mov     rcx, rbx; this
0x180018cbb  call    ?SetTraceConfigurationWorker@W3_TRACE_EVENT_MANAGER@@QEAAJPEAXPEAUHTTP_TRACE_CONFIGURATION@@@Z; W3_TRACE_EVENT_MANAGER::SetTraceConfigurationWorker(void *,HTTP_TRACE_CONFIGURATION *)
0x180018cc0  mov     esi, eax
0x180018cc2  test    eax, eax
0x180018cc4  js      short loc_180018CCC
0x180018cc6  inc     edi
0x180018cc8  cmp     edi, ebp
0x180018cca  jb      short loc_180018CAD
0x180018ccc  cmp     byte ptr [rbx+2Ch], 0
0x180018cd0  jz      short loc_180018CDB
0x180018cd2  mov     rcx, rbx
0x180018cd5  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180018cdb  mov     eax, esi
0x180018cdd  add     rsp, 28h
0x180018ce1  pop     r15
0x180018ce3  pop     r14
0x180018ce5  pop     rdi
0x180018ce6  pop     rsi
0x180018ce7  pop     rbp
0x180018ce8  pop     rbx
0x180018ce9  retn
```
