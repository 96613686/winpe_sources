# CONTEXT_CONTAINER::GetNamedContext(ushort const *)

- ea: `0x1800316f0`
- end: `0x18003178d`
- name: `?GetNamedContext@CONTEXT_CONTAINER@@UEAAPEAVIHttpStoredContext@@PEBG@Z`
- size: `157`
- prototype: `struct IHttpStoredContext *(CONTEXT_CONTAINER *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800316f0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180031745`
- `msvcrt!_wcsicmp` at `0x180031745`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180031733`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180031733`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180031772`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180031772`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180031718`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180031718`

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
0x1800316f0  push    rbx
0x1800316f2  push    rbp
0x1800316f3  push    rsi
0x1800316f4  push    rdi
0x1800316f5  push    r14
0x1800316f7  sub     rsp, 20h
0x1800316fb  cmp     qword ptr [rcx+38h], 0
0x180031700  mov     r14, rdx
0x180031703  mov     rbx, rcx
0x180031706  jnz     short loc_18003170C
0x180031708  xor     eax, eax
0x18003170a  jmp     short loc_180031781
0x18003170c  xor     esi, esi
0x18003170e  cmp     [rcx+24h], sil
0x180031712  jz      short loc_180031724
0x180031714  add     rcx, 8
0x180031718  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18003171f  nop     dword ptr [rax+rax+00h]
0x180031724  xor     edi, edi
0x180031726  cmp     edi, [rbx+1Ch]
0x180031729  jnb     short loc_180031768
0x18003172b  mov     rcx, [rbx+38h]
0x18003172f  mov     rcx, [rcx+rdi*8]
0x180031733  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18003173a  nop     dword ptr [rax+rax+00h]
0x18003173f  mov     rcx, rax; String1
0x180031742  mov     rdx, r14; String2
0x180031745  call    cs:__imp__wcsicmp
0x18003174c  nop     dword ptr [rax+rax+00h]
0x180031751  test    eax, eax
0x180031753  jz      short loc_180031759
0x180031755  inc     edi
0x180031757  jmp     short loc_180031726
0x180031759  lfence
0x18003175c  mov     rax, [rbx+38h]
0x180031760  mov     rcx, [rax+rdi*8]
0x180031764  mov     rsi, [rcx+38h]
0x180031768  cmp     byte ptr [rbx+24h], 0
0x18003176c  jz      short loc_18003177E
0x18003176e  lea     rcx, [rbx+8]
0x180031772  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180031779  nop     dword ptr [rax+rax+00h]
0x18003177e  mov     rax, rsi
0x180031781  add     rsp, 20h
0x180031785  pop     r14
0x180031787  pop     rdi
0x180031788  pop     rsi
0x180031789  pop     rbp
0x18003178a  pop     rbx
0x18003178b  retn
```
