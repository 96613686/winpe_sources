# CClfsLogFcbPhysical::PostAsyncRequest(IClfsRequestAsync *)

- ea: `0x14006e1e0`
- end: `0x14006e290`
- name: `?PostAsyncRequest@CClfsLogFcbPhysical@@UEAAJPEAUIClfsRequestAsync@@@Z`
- size: `176`
- prototype: `int(CClfsLogFcbPhysical *__hidden this, struct IClfsRequestAsync *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140015ed0`

## callees

- `0x140005840`
- `0x140017f20`
- `0x14006e1e0`

## import_xrefs

- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14006e26d`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14006e26d`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14006e20a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14006e20a`
- `ntoskrnl!IoCsqInsertIrpEx` at `0x14006e24e`
- `ntoskrnl!IoCsqInsertIrpEx` at `0x14006e24e`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::PostAsyncRequest(CClfsLogFcbPhysical *this, struct IClfsRequestAsync *a2)
{
  struct _ERESOURCE *v4; // r14
  struct _IO_CSQ_IRP_CONTEXT *v5; // rbx
  IRP *v6; // rax
  unsigned int inserted; // ebx
  BOOLEAN v9; // [rsp+50h] [rbp+18h]

  v4 = (struct _ERESOURCE *)((char *)this - 408);
  v9 = ExAcquireResourceSharedLite((PERESOURCE)((char *)this - 408), 1u);
  v5 = (struct _IO_CSQ_IRP_CONTEXT *)(*(__int64 (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)a2 + 40LL))(a2);
  v6 = (IRP *)(*(__int64 (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)a2 + 32LL))(a2);
  inserted = IoCsqInsertIrpEx((PIO_CSQ)((char *)this + 392), v6, v5, a2);
  if ( v9 )
    ExReleaseResourceForThreadLite(v4, (ERESOURCE_THREAD)KeGetCurrentThread());
  return inserted;
}

```

## disassembly

```asm
0x14006e1e0  mov     [rsp+arg_8], rbx
0x14006e1e5  mov     [rsp+arg_18], rsi
0x14006e1ea  mov     [rsp+arg_0], rcx
0x14006e1ef  push    rdi
0x14006e1f0  push    r14
0x14006e1f2  push    r15
0x14006e1f4  sub     rsp, 20h
0x14006e1f8  mov     r15, rdx
0x14006e1fb  mov     rdi, rcx
0x14006e1fe  lea     r14, [rcx-198h]
0x14006e205  mov     dl, 1; Wait
0x14006e207  mov     rcx, r14; Resource
0x14006e20a  call    cs:__imp_ExAcquireResourceSharedLite
0x14006e211  nop     dword ptr [rax+rax+00h]
0x14006e216  mov     sil, al
0x14006e219  mov     [rsp+38h+arg_10], al
0x14006e21d  mov     r8, [r15]
0x14006e220  mov     rax, [r8+28h]
0x14006e224  mov     rcx, r15
0x14006e227  call    _guard_dispatch_icall
0x14006e22c  mov     rbx, rax
0x14006e22f  mov     rcx, [r15]
0x14006e232  mov     rax, [rcx+20h]
0x14006e236  mov     rcx, r15
0x14006e239  call    _guard_dispatch_icall
0x14006e23e  lea     rcx, [rdi+188h]; Csq
0x14006e245  mov     r9, r15; InsertContext
0x14006e248  mov     r8, rbx; Context
0x14006e24b  mov     rdx, rax; Irp
0x14006e24e  call    cs:__imp_IoCsqInsertIrpEx
0x14006e255  nop     dword ptr [rax+rax+00h]
0x14006e25a  mov     ebx, eax
0x14006e25c  test    sil, sil
0x14006e25f  jz      short loc_14006E279
0x14006e261  mov     rdx, gs:188h; ResourceThreadId
0x14006e26a  mov     rcx, r14; Resource
0x14006e26d  call    cs:__imp_ExReleaseResourceForThreadLite
0x14006e274  nop     dword ptr [rax+rax+00h]
0x14006e279  mov     eax, ebx
0x14006e27b  mov     rbx, [rsp+38h+arg_8]
0x14006e280  mov     rsi, [rsp+38h+arg_18]
0x14006e285  add     rsp, 20h
0x14006e289  pop     r15
0x14006e28b  pop     r14
0x14006e28d  pop     rdi
0x14006e28e  retn
0x14007ba12  push    rbp
0x14007ba14  sub     rsp, 20h
0x14007ba18  mov     rbp, rdx
0x14007ba1b  cmp     byte ptr [rbp+50h], 0
0x14007ba1f  jz      short loc_14007BA32
0x14007ba21  mov     rcx, [rbp+40h]
0x14007ba25  add     rcx, 0FFFFFFFFFFFFFE68h
0x14007ba2c  call    ClfsReleaseResourceLite
0x14007ba31  nop
0x14007ba32  add     rsp, 20h
0x14007ba36  pop     rbp
0x14007ba37  retn
```
