# OUTPUT_ENTRY::SetResponseEntry(RESPONSE_ENTRY *,char const *)

- ea: `0x180007218`
- end: `0x180007293`
- name: `?SetResponseEntry@OUTPUT_ENTRY@@QEAAJPEAVRESPONSE_ENTRY@@PEBD@Z`
- size: `123`
- prototype: `__int64 __fastcall(OUTPUT_ENTRY *__hidden this, struct RESPONSE_ENTRY *, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004220`

## callees

- `0x180007218`

## import_xrefs

- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180007234`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180007234`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180007265`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180007265`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180007282`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180007282`

## pseudocode

```c
__int64 __fastcall OUTPUT_ENTRY::SetResponseEntry(OUTPUT_ENTRY *this, struct RESPONSE_ENTRY *a2, const char *a3)
{
  CReaderWriterLock3 *v3; // rbp

  v3 = (OUTPUT_ENTRY *)((char *)this + 816);
  CReaderWriterLock3::WriteLock((OUTPUT_ENTRY *)((char *)this + 816));
  if ( !a3 )
  {
    if ( !*((_QWORD *)this + 103) )
    {
      *((_QWORD *)this + 103) = a2;
      goto LABEL_8;
    }
LABEL_7:
    LODWORD(a3) = -2147024713;
    goto LABEL_8;
  }
  if ( *((_QWORD *)this + 104) )
    goto LABEL_7;
  LODWORD(a3) = STRA::Copy((OUTPUT_ENTRY *)((char *)this + 840), a3);
  if ( (int)a3 >= 0 )
    *((_QWORD *)this + 104) = a2;
LABEL_8:
  CReaderWriterLock3::WriteUnlock(v3);
  return (unsigned int)a3;
}

```

## disassembly

```asm
0x180007218  push    rbx
0x18000721a  push    rbp
0x18000721b  push    rsi
0x18000721c  push    rdi
0x18000721d  sub     rsp, 28h
0x180007221  lea     rbp, [rcx+330h]
0x180007228  mov     rdi, rcx
0x18000722b  mov     rcx, rbp
0x18000722e  mov     rbx, r8
0x180007231  mov     rsi, rdx
0x180007234  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000723a  test    rbx, rbx
0x18000723d  jnz     short loc_180007251
0x18000723f  cmp     [rdi+338h], rbx
0x180007246  jnz     short loc_18000727A
0x180007248  mov     [rdi+338h], rsi
0x18000724f  jmp     short loc_18000727F
0x180007251  cmp     qword ptr [rdi+340h], 0
0x180007259  jnz     short loc_18000727A
0x18000725b  lea     rcx, [rdi+348h]
0x180007262  mov     rdx, rbx
0x180007265  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x18000726b  mov     ebx, eax
0x18000726d  test    eax, eax
0x18000726f  js      short loc_18000727F
0x180007271  mov     [rdi+340h], rsi
0x180007278  jmp     short loc_18000727F
0x18000727a  mov     ebx, 800700B7h
0x18000727f  mov     rcx, rbp
0x180007282  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180007288  mov     eax, ebx
0x18000728a  add     rsp, 28h
0x18000728e  pop     rdi
0x18000728f  pop     rsi
0x180007290  pop     rbp
0x180007291  pop     rbx
0x180007292  retn
```
