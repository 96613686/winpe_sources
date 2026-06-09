# CFileStream::Release(void)

- ea: `0x18000db40`
- end: `0x18000db7e`
- name: `?Release@CFileStream@@UEAAKXZ`
- size: `62`
- prototype: `unsigned int __fastcall(CFileStream *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180009844`
- `0x18000b45c`
- `0x18000bbc4`
- `0x18000d060`
- `0x18000db90`

## callees

- `0x1800019a0`
- `0x18000cdc0`
- `0x18000db40`

## pseudocode

```c
__int64 __fastcall CFileStream::Release(CFileStream *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 4);
  if ( !v2 && this )
  {
    CFileStream::~CFileStream(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x18000db40  mov     [rsp+arg_0], rbx
0x18000db45  push    rdi
0x18000db46  sub     rsp, 20h
0x18000db4a  mov     rbx, rcx
0x18000db4d  or      edi, 0FFFFFFFFh
0x18000db50  lock xadd [rcx+10h], edi
0x18000db55  sub     edi, 1
0x18000db58  jnz     short loc_18000DB71
0x18000db5a  test    rcx, rcx
0x18000db5d  jz      short loc_18000DB71
0x18000db5f  call    ??1CFileStream@@QEAA@XZ; CFileStream::~CFileStream(void)
0x18000db64  mov     edx, 230h; unsigned __int64
0x18000db69  mov     rcx, rbx; void *
0x18000db6c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000db71  mov     rbx, [rsp+28h+arg_0]
0x18000db76  mov     eax, edi
0x18000db78  add     rsp, 20h
0x18000db7c  pop     rdi
0x18000db7d  retn
```
