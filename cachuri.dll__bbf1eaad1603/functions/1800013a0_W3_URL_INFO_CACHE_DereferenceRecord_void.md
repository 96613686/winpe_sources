# W3_URL_INFO_CACHE::DereferenceRecord(void *)

- ea: `0x1800013a0`
- end: `0x18000141e`
- name: `?DereferenceRecord@W3_URL_INFO_CACHE@@UEAAXPEAX@Z`
- size: `126`
- prototype: `void __fastcall(W3_URL_INFO_CACHE *__hidden this, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003010`

## pseudocode

```c
void __fastcall W3_URL_INFO_CACHE::DereferenceRecord(W3_URL_INFO_CACHE *this, void *a2)
{
  __int64 v3; // rbx

  v3 = (*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 96LL))(g_pGlobalInfo);
  (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v3 + 8LL))(v3, 5, 1);
  (**(void (__fastcall ***)(__int64, __int64, __int64))v3)(v3, 7, 1);
  (*(void (__fastcall **)(void *))(*(_QWORD *)a2 + 40LL))(a2);
  (*(void (__fastcall **)(void *))(*(_QWORD *)a2 + 16LL))(a2);
}

```

## disassembly

```asm
0x1800013a0  mov     [rsp+arg_0], rbx
0x1800013a5  push    rdi
0x1800013a6  sub     rsp, 20h
0x1800013aa  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800013b1  mov     rdi, rdx
0x1800013b4  mov     rax, [rcx]
0x1800013b7  mov     rax, [rax+60h]
0x1800013bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013c0  mov     rbx, rax
0x1800013c3  mov     edx, 5
0x1800013c8  mov     r8d, 1
0x1800013ce  mov     rcx, [rax]
0x1800013d1  mov     rax, [rcx+8]
0x1800013d5  mov     rcx, rbx
0x1800013d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013dd  mov     rcx, [rbx]
0x1800013e0  mov     edx, 7
0x1800013e5  mov     r8d, 1
0x1800013eb  mov     rax, [rcx]
0x1800013ee  mov     rcx, rbx
0x1800013f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013f6  mov     rax, [rdi]
0x1800013f9  mov     rcx, rdi
0x1800013fc  mov     rax, [rax+28h]
0x180001400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001405  mov     rax, [rdi]
0x180001408  mov     rcx, rdi
0x18000140b  mov     rax, [rax+10h]
0x18000140f  mov     rbx, [rsp+28h+arg_0]
0x180001414  add     rsp, 20h
0x180001418  pop     rdi
0x180001419  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
