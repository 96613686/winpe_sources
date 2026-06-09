# CDownloadBuffer::Release(void)

- ea: `0x18000d840`
- end: `0x18000d895`
- name: `?Release@CDownloadBuffer@@UEAAKXZ`
- size: `85`
- prototype: `__int64 __fastcall(CDownloadBuffer *this, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000d8a0`
- `0x18000f6a4`
- `0x1800105f8`
- `0x180011660`

## callees

- `0x1800012c4`
- `0x18000d840`

## pseudocode

```c
__int64 __fastcall CDownloadBuffer::Release(CDownloadBuffer *this, unsigned __int64 a2)
{
  unsigned __int32 v3; // edi

  v3 = _InterlockedDecrement((volatile signed __int32 *)this + 15);
  if ( !v3 && this )
  {
    *(_QWORD *)this = &CDownloadBuffer::`vftable'{for `IDirectMusicDownload'};
    *((_QWORD *)this + 1) = &CDownloadBuffer::`vftable'{for `IDirectMusicDownloadPrivate'};
    operator delete(*((void **)this + 5), a2);
    operator delete(this, 0x40u);
  }
  return v3;
}

```

## disassembly

```asm
0x18000d840  mov     [rsp+arg_0], rbx
0x18000d845  push    rdi
0x18000d846  sub     rsp, 20h
0x18000d84a  mov     rbx, rcx
0x18000d84d  or      edi, 0FFFFFFFFh
0x18000d850  lock xadd [rcx+3Ch], edi
0x18000d855  sub     edi, 1
0x18000d858  jnz     short loc_18000D888
0x18000d85a  test    rcx, rcx
0x18000d85d  jz      short loc_18000D888
0x18000d85f  lea     rax, ??_7CDownloadBuffer@@6BIDirectMusicDownload@@@; const CDownloadBuffer::`vftable'{for `IDirectMusicDownload'}
0x18000d866  mov     [rcx], rax
0x18000d869  lea     rax, ??_7CDownloadBuffer@@6BIDirectMusicDownloadPrivate@@@; const CDownloadBuffer::`vftable'{for `IDirectMusicDownloadPrivate'}
0x18000d870  mov     [rcx+8], rax
0x18000d874  mov     rcx, [rcx+28h]; void *
0x18000d878  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d87d  lea     edx, [rdi+40h]; unsigned __int64
0x18000d880  mov     rcx, rbx; void *
0x18000d883  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d888  mov     rbx, [rsp+28h+arg_0]
0x18000d88d  mov     eax, edi
0x18000d88f  add     rsp, 20h
0x18000d893  pop     rdi
0x18000d894  retn
```
