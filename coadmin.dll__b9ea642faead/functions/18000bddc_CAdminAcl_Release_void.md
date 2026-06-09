# CAdminAcl::Release(void)

- ea: `0x18000bddc`
- end: `0x18000be18`
- name: `?Release@CAdminAcl@@QEAAKXZ`
- size: `60`
- prototype: `unsigned int __fastcall(CAdminAcl *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18000aefc`
- `0x18000b08c`
- `0x18000b2d4`
- `0x18000b988`

## callees

- `0x1800010a4`
- `0x18000abbc`
- `0x18000bddc`

## pseudocode

```c
__int64 __fastcall CAdminAcl::Release(CAdminAcl *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 142);
  if ( !v2 && this )
  {
    CAdminAcl::~CAdminAcl(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x18000bddc  mov     [rsp+arg_0], rbx
0x18000bde1  push    rdi
0x18000bde2  sub     rsp, 20h
0x18000bde6  mov     rbx, rcx
0x18000bde9  or      edi, 0FFFFFFFFh
0x18000bdec  lock xadd [rcx+238h], edi
0x18000bdf4  sub     edi, 1
0x18000bdf7  jnz     short loc_18000BE0B
0x18000bdf9  test    rcx, rcx
0x18000bdfc  jz      short loc_18000BE0B
0x18000bdfe  call    ??1CAdminAcl@@QEAA@XZ; CAdminAcl::~CAdminAcl(void)
0x18000be03  mov     rcx, rbx; Block
0x18000be06  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000be0b  mov     rbx, [rsp+28h+arg_0]
0x18000be10  mov     eax, edi
0x18000be12  add     rsp, 20h
0x18000be16  pop     rdi
0x18000be17  retn
```
