# IISCORE_PROTOCOL_MANAGER::RequestCounters(void)

- ea: `0x180033ff0`
- end: `0x18003405f`
- name: `?RequestCounters@IISCORE_PROTOCOL_MANAGER@@UEAAJXZ`
- size: `111`
- prototype: `__int64 __fastcall(IISCORE_PROTOCOL_MANAGER *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18001fc38`
- `0x180033ff0`
- `0x180038010`

## import_xrefs

- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180034045`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180034045`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180034004`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180034004`

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
      dword_18003C5E4,
      0);
    v4 = -2147467259;
  }
  CReaderWriterLock3::ReadUnlock(v1);
  return v4;
}

```

## disassembly

```asm
0x180033ff0  mov     [rsp+arg_0], rbx
0x180033ff5  push    rdi
0x180033ff6  sub     rsp, 20h
0x180033ffa  lea     rbx, [rcx+38h]
0x180033ffe  mov     rdi, rcx
0x180034001  mov     rcx, rbx
0x180034004  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18003400b  nop     dword ptr [rax+rax+00h]
0x180034010  cmp     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x180034018  jz      short loc_180034023
0x18003401a  call    ?ReportCounters@W3_SERVER@@QEAAJXZ; W3_SERVER::ReportCounters(void)
0x18003401f  mov     edi, eax
0x180034021  jmp     short loc_180034042
0x180034023  mov     rcx, [rdi+20h]
0x180034027  lea     rdx, dword_18003C5E4
0x18003402e  xor     r8d, r8d
0x180034031  mov     rax, [rcx]
0x180034034  mov     rax, [rax+10h]
0x180034038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003403d  mov     edi, 80004005h
0x180034042  mov     rcx, rbx
0x180034045  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18003404c  nop     dword ptr [rax+rax+00h]
0x180034051  mov     rbx, [rsp+28h+arg_0]
0x180034056  mov     eax, edi
0x180034058  add     rsp, 20h
0x18003405c  pop     rdi
0x18003405d  retn
```
