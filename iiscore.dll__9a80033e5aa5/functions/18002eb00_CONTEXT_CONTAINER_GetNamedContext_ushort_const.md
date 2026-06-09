# CONTEXT_CONTAINER::GetNamedContext(ushort const *)

- ea: `0x18002eb00`
- end: `0x18002eb84`
- name: `?GetNamedContext@CONTEXT_CONTAINER@@UEAAPEAVIHttpStoredContext@@PEBG@Z`
- size: `132`
- prototype: `struct IHttpStoredContext *(CONTEXT_CONTAINER *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002eb00`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002eb49`
- `msvcrt!_wcsicmp` at `0x18002eb49`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002eb3d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002eb3d`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18002eb70`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18002eb70`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18002eb28`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18002eb28`

## pseudocode

```c
struct IHttpStoredContext *__fastcall CONTEXT_CONTAINER::GetNamedContext(
        CONTEXT_CONTAINER *this,
        const unsigned __int16 *a2)
{
  __int64 v5; // rsi
  __int64 i; // rdi
  const wchar_t *Str; // rax

  if ( !*((_QWORD *)this + 7) )
    return 0;
  v5 = 0;
  if ( *((_BYTE *)this + 36) )
    CReaderWriterLock3::ReadLock((CONTEXT_CONTAINER *)((char *)this + 8));
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 7); i = (unsigned int)(i + 1) )
  {
    Str = STRU::QueryStr(*(STRU **)(*((_QWORD *)this + 7) + 8 * i));
    if ( !_wcsicmp(Str, a2) )
    {
      _mm_lfence();
      v5 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 7) + 8 * i) + 56LL);
      break;
    }
  }
  if ( *((_BYTE *)this + 36) )
    CReaderWriterLock3::ReadUnlock((CONTEXT_CONTAINER *)((char *)this + 8));
  return (struct IHttpStoredContext *)v5;
}

```

## disassembly

```asm
0x18002eb00  push    rbx
0x18002eb02  push    rbp
0x18002eb03  push    rsi
0x18002eb04  push    rdi
0x18002eb05  push    r14
0x18002eb07  sub     rsp, 20h
0x18002eb0b  cmp     qword ptr [rcx+38h], 0
0x18002eb10  mov     r14, rdx
0x18002eb13  mov     rbx, rcx
0x18002eb16  jnz     short loc_18002EB1C
0x18002eb18  xor     eax, eax
0x18002eb1a  jmp     short loc_18002EB79
0x18002eb1c  xor     esi, esi
0x18002eb1e  cmp     [rcx+24h], sil
0x18002eb22  jz      short loc_18002EB2E
0x18002eb24  add     rcx, 8
0x18002eb28  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18002eb2e  xor     edi, edi
0x18002eb30  cmp     edi, [rbx+1Ch]
0x18002eb33  jnb     short loc_18002EB66
0x18002eb35  mov     rcx, [rbx+38h]
0x18002eb39  mov     rcx, [rcx+rdi*8]
0x18002eb3d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002eb43  mov     rcx, rax; String1
0x18002eb46  mov     rdx, r14; String2
0x18002eb49  call    cs:__imp__wcsicmp
0x18002eb4f  test    eax, eax
0x18002eb51  jz      short loc_18002EB57
0x18002eb53  inc     edi
0x18002eb55  jmp     short loc_18002EB30
0x18002eb57  lfence
0x18002eb5a  mov     rax, [rbx+38h]
0x18002eb5e  mov     rcx, [rax+rdi*8]
0x18002eb62  mov     rsi, [rcx+38h]
0x18002eb66  cmp     byte ptr [rbx+24h], 0
0x18002eb6a  jz      short loc_18002EB76
0x18002eb6c  lea     rcx, [rbx+8]
0x18002eb70  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18002eb76  mov     rax, rsi
0x18002eb79  add     rsp, 20h
0x18002eb7d  pop     r14
0x18002eb7f  pop     rdi
0x18002eb80  pop     rsi
0x18002eb81  pop     rbp
0x18002eb82  pop     rbx
0x18002eb83  retn
```
