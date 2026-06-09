# FILE_CACHE::DereferenceRecord(void *)

- ea: `0x180002650`
- end: `0x1800026f8`
- name: `?DereferenceRecord@FILE_CACHE@@UEAAXPEAX@Z`
- size: `168`
- prototype: `void __fastcall(FILE_CACHE *__hidden this, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004010`

## pseudocode

```c
void __fastcall FILE_CACHE::DereferenceRecord(FILE_CACHE *this, void *a2)
{
  __int64 v4; // rdi

  v4 = (*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 96LL))(g_pGlobalInfo);
  (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v4 + 8LL))(v4, 26, 1);
  _InterlockedDecrement((volatile signed __int32 *)this + 15);
  (*(void (__fastcall **)(void *))(*(_QWORD *)a2 + 40LL))(a2);
  (**(void (__fastcall ***)(__int64, __int64, __int64))v4)(v4, 3, 1);
  (**(void (__fastcall ***)(__int64, __int64, __int64))v4)(v4, 4, 1);
  (*(void (__fastcall **)(void *))(*(_QWORD *)a2 + 16LL))(a2);
}

```

## disassembly

```asm
0x180002650  mov     [rsp+arg_0], rbx
0x180002655  mov     [rsp+arg_8], rsi
0x18000265a  push    rdi
0x18000265b  sub     rsp, 20h
0x18000265f  mov     rbx, rcx
0x180002662  mov     rsi, rdx
0x180002665  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000266c  mov     rax, [rcx]
0x18000266f  mov     rax, [rax+60h]
0x180002673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002678  mov     rdi, rax
0x18000267b  mov     edx, 1Ah
0x180002680  mov     rcx, rdi
0x180002683  mov     r8, [rax]
0x180002686  mov     rax, [r8+8]
0x18000268a  mov     r8d, 1
0x180002690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002695  lock dec dword ptr [rbx+3Ch]
0x180002699  mov     rcx, [rsi]
0x18000269c  mov     rax, [rcx+28h]
0x1800026a0  mov     rcx, rsi
0x1800026a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026a8  mov     rax, [rdi]
0x1800026ab  mov     edx, 3
0x1800026b0  mov     r8d, 1
0x1800026b6  mov     rcx, rdi
0x1800026b9  mov     rax, [rax]
0x1800026bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026c1  mov     rax, [rdi]
0x1800026c4  mov     edx, 4
0x1800026c9  mov     r8d, 1
0x1800026cf  mov     rcx, rdi
0x1800026d2  mov     rax, [rax]
0x1800026d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026da  mov     rax, [rsi]
0x1800026dd  mov     rcx, rsi
0x1800026e0  mov     rax, [rax+10h]
0x1800026e4  mov     rbx, [rsp+28h+arg_0]
0x1800026e9  mov     rsi, [rsp+28h+arg_8]
0x1800026ee  add     rsp, 20h
0x1800026f2  pop     rdi
0x1800026f3  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
