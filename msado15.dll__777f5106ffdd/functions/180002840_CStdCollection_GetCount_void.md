# CStdCollection::GetCount(void)

- ea: `0x180002840`
- end: `0x180002897`
- name: `?GetCount@CStdCollection@@UEAAKXZ`
- size: `87`
- prototype: `unsigned int __fastcall(CStdCollection *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000160c`
- `0x18000174c`
- `0x180001b10`
- `0x180001c98`
- `0x180002990`
- `0x18006ef20`
- `0x1800a8670`
- `0x1800b6b10`

## callees

- `0x180002840`

## import_xrefs

- `MSDART!?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ` at `0x180002858`
- `MSDART!?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ` at `0x180002858`
- `MSDART!?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z` at `0x180002873`
- `MSDART!?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z` at `0x180002873`

## pseudocode

```c
__int64 __fastcall CStdCollection::GetCount(CStdCollection *this)
{
  unsigned int v2; // edi
  bool v3; // dl
  __int64 v4; // rax

  v2 = 0;
  v3 = CReaderWriterLock3AR::ReadOrWriteLock((CStdCollection *)((char *)this + 72));
  v4 = *((_QWORD *)this + 8);
  if ( v4 )
    v2 = *(_DWORD *)(v4 + 16);
  CReaderWriterLock3AR::ReadOrWriteUnlock((CStdCollection *)((char *)this + 72), v3);
  return v2;
}

```

## disassembly

```asm
0x180002840  mov     [rsp+arg_0], rbx
0x180002845  mov     [rsp+arg_8], rsi
0x18000284a  push    rdi
0x18000284b  sub     rsp, 20h
0x18000284f  mov     rbx, rcx
0x180002852  xor     edi, edi
0x180002854  add     rcx, 48h ; 'H'
0x180002858  call    cs:__imp_?ReadOrWriteLock@CReaderWriterLock3AR@@QEAA_NXZ; CReaderWriterLock3AR::ReadOrWriteLock(void)
0x18000285f  nop     dword ptr [rax+rax+00h]
0x180002864  mov     dl, al
0x180002866  mov     rax, [rbx+40h]
0x18000286a  test    rax, rax
0x18000286d  jnz     short loc_180002892
0x18000286f  lea     rcx, [rbx+48h]
0x180002873  call    cs:__imp_?ReadOrWriteUnlock@CReaderWriterLock3AR@@QEAAX_N@Z; CReaderWriterLock3AR::ReadOrWriteUnlock(bool)
0x18000287a  nop     dword ptr [rax+rax+00h]
0x18000287f  mov     rbx, [rsp+28h+arg_0]
0x180002884  mov     eax, edi
0x180002886  mov     rsi, [rsp+28h+arg_8]
0x18000288b  add     rsp, 20h
0x18000288f  pop     rdi
0x180002890  retn
0x180002892  mov     edi, [rax+10h]
0x180002895  jmp     short loc_18000286F
```
