# IISCORE_PROTOCOL_MANAGER::RequestCounters(void)

- ea: `0x180031230`
- end: `0x180031292`
- name: `?RequestCounters@IISCORE_PROTOCOL_MANAGER@@UEAAJXZ`
- size: `98`
- prototype: `__int64 __fastcall(IISCORE_PROTOCOL_MANAGER *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18001e1c0`
- `0x180031230`
- `0x180035010`

## import_xrefs

- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003127f`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003127f`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180031244`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180031244`

## pseudocode

```c
__int64 __fastcall IISCORE_PROTOCOL_MANAGER::RequestCounters(IISCORE_PROTOCOL_MANAGER *this)
{
  CReaderWriterLock3 *v1; // rbx
  W3_SERVER *v3; // rcx
  unsigned int v4; // edi

  v1 = (IISCORE_PROTOCOL_MANAGER *)((char *)this + 56);
  CReaderWriterLock3::ReadLock((IISCORE_PROTOCOL_MANAGER *)((char *)this + 56));
  if ( g_pW3Server )
  {
    v4 = W3_SERVER::ReportCounters(v3);
  }
  else
  {
    (*(void (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 4) + 16LL))(
      *((_QWORD *)this + 4),
      dword_1800395E4,
      0);
    v4 = -2147467259;
  }
  CReaderWriterLock3::ReadUnlock(v1);
  return v4;
}

```

## disassembly

```asm
0x180031230  mov     [rsp+arg_0], rbx
0x180031235  push    rdi
0x180031236  sub     rsp, 20h
0x18003123a  lea     rbx, [rcx+38h]
0x18003123e  mov     rdi, rcx
0x180031241  mov     rcx, rbx
0x180031244  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18003124a  cmp     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x180031252  jz      short loc_18003125D
0x180031254  call    ?ReportCounters@W3_SERVER@@QEAAJXZ; W3_SERVER::ReportCounters(void)
0x180031259  mov     edi, eax
0x18003125b  jmp     short loc_18003127C
0x18003125d  mov     rcx, [rdi+20h]
0x180031261  lea     rdx, dword_1800395E4
0x180031268  xor     r8d, r8d
0x18003126b  mov     rax, [rcx]
0x18003126e  mov     rax, [rax+10h]
0x180031272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031277  mov     edi, 80004005h
0x18003127c  mov     rcx, rbx
0x18003127f  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180031285  mov     rbx, [rsp+28h+arg_0]
0x18003128a  mov     eax, edi
0x18003128c  add     rsp, 20h
0x180031290  pop     rdi
0x180031291  retn
```
