# CMediaTypeAttributes::Release(void)

- ea: `0x18003a420`
- end: `0x18003a46a`
- name: `?Release@CMediaTypeAttributes@@UEAAKXZ`
- size: `74`
- prototype: `__int64 __fastcall(CMediaTypeAttributes *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task`

## callees

- `0x18001f1c4`
- `0x18003a420`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18003a443`
- `ole32!CoTaskMemFree` at `0x18003a443`

## pseudocode

```c
__int64 __fastcall CMediaTypeAttributes::Release(CMediaTypeAttributes *this)
{
  unsigned __int32 v2; // ebx
  void *v3; // rcx

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 4);
  if ( !v2 )
  {
    v3 = (void *)*((_QWORD *)this + 1);
    if ( v3 )
      CoTaskMemFree(v3);
    operator delete(this, 0x18u);
  }
  return v2;
}

```

## disassembly

```asm
0x18003a420  mov     [rsp+arg_0], rbx
0x18003a425  push    rdi
0x18003a426  sub     rsp, 20h
0x18003a42a  mov     rdi, rcx
0x18003a42d  or      ebx, 0FFFFFFFFh
0x18003a430  lock xadd [rcx+10h], ebx
0x18003a435  sub     ebx, 1
0x18003a438  jnz     short loc_18003A45C
0x18003a43a  mov     rcx, [rcx+8]; pv
0x18003a43e  test    rcx, rcx
0x18003a441  jz      short loc_18003A44F
0x18003a443  call    cs:__imp_CoTaskMemFree
0x18003a44a  nop     dword ptr [rax+rax+00h]
0x18003a44f  mov     edx, 18h; unsigned __int64
0x18003a454  mov     rcx, rdi; void *
0x18003a457  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003a45c  mov     eax, ebx
0x18003a45e  mov     rbx, [rsp+28h+arg_0]
0x18003a463  add     rsp, 20h
0x18003a467  pop     rdi
0x18003a468  retn
```
