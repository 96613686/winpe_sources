# W3_TRACE_EVENT_MANAGER::SetTraceConfiguration(void *,HTTP_TRACE_CONFIGURATION *,ulong)

- ea: `0x18001a1ac`
- end: `0x18001a22f`
- name: `?SetTraceConfiguration@W3_TRACE_EVENT_MANAGER@@QEAAJPEAXPEAUHTTP_TRACE_CONFIGURATION@@K@Z`
- size: `131`
- prototype: `__int64 __fastcall(W3_TRACE_EVENT_MANAGER *__hidden this, void *, struct HTTP_TRACE_CONFIGURATION *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001ff70`
- `0x180024b30`

## callees

- `0x18001a1ac`
- `0x180032774`

## import_xrefs

- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001a1d9`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001a1d9`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001a213`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001a213`

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
0x18001a1ac  push    rbx
0x18001a1ae  push    rbp
0x18001a1af  push    rsi
0x18001a1b0  push    rdi
0x18001a1b1  push    r14
0x18001a1b3  push    r15
0x18001a1b5  sub     rsp, 28h
0x18001a1b9  mov     ebp, r9d
0x18001a1bc  mov     r14, r8
0x18001a1bf  mov     r15, rdx
0x18001a1c2  mov     rbx, rcx
0x18001a1c5  test    r8, r8
0x18001a1c8  jnz     short loc_18001A1D1
0x18001a1ca  mov     eax, 80070057h
0x18001a1cf  jmp     short loc_18001A221
0x18001a1d1  xor     esi, esi
0x18001a1d3  cmp     [rcx+2Ch], sil
0x18001a1d7  jz      short loc_18001A1E5
0x18001a1d9  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18001a1e0  nop     dword ptr [rax+rax+00h]
0x18001a1e5  xor     edi, edi
0x18001a1e7  test    ebp, ebp
0x18001a1e9  jz      short loc_18001A20A
0x18001a1eb  lea     rcx, [rdi+rdi*2]
0x18001a1ef  mov     rdx, r15; void *
0x18001a1f2  lea     r8, [r14+rcx*8]; struct HTTP_TRACE_CONFIGURATION *
0x18001a1f6  mov     rcx, rbx; this
0x18001a1f9  call    ?SetTraceConfigurationWorker@W3_TRACE_EVENT_MANAGER@@QEAAJPEAXPEAUHTTP_TRACE_CONFIGURATION@@@Z; W3_TRACE_EVENT_MANAGER::SetTraceConfigurationWorker(void *,HTTP_TRACE_CONFIGURATION *)
0x18001a1fe  mov     esi, eax
0x18001a200  test    eax, eax
0x18001a202  js      short loc_18001A20A
0x18001a204  inc     edi
0x18001a206  cmp     edi, ebp
0x18001a208  jb      short loc_18001A1EB
0x18001a20a  cmp     byte ptr [rbx+2Ch], 0
0x18001a20e  jz      short loc_18001A21F
0x18001a210  mov     rcx, rbx
0x18001a213  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18001a21a  nop     dword ptr [rax+rax+00h]
0x18001a21f  mov     eax, esi
0x18001a221  add     rsp, 28h
0x18001a225  pop     r15
0x18001a227  pop     r14
0x18001a229  pop     rdi
0x18001a22a  pop     rsi
0x18001a22b  pop     rbp
0x18001a22c  pop     rbx
0x18001a22d  retn
```
