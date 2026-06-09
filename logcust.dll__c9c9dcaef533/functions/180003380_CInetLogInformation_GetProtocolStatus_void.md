# CInetLogInformation::GetProtocolStatus(void)

- ea: `0x180003380`
- end: `0x1800033af`
- name: `?GetProtocolStatus@CInetLogInformation@@UEAAKXZ`
- size: `47`
- prototype: `unsigned int __fastcall(CInetLogInformation *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004010`

## pseudocode

```c
__int64 __fastcall CInetLogInformation::GetProtocolStatus(CInetLogInformation *this)
{
  __int64 v1; // rax

  v1 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 32LL))(*((_QWORD *)this + 8));
  return *(unsigned __int16 *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 8LL))(v1) + 8);
}

```

## disassembly

```asm
0x180003380  sub     rsp, 28h
0x180003384  mov     rcx, [rcx+40h]
0x180003388  mov     rax, [rcx]
0x18000338b  mov     rax, [rax+20h]
0x18000338f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003394  mov     rdx, rax
0x180003397  mov     rcx, [rax]
0x18000339a  mov     rax, [rcx+8]
0x18000339e  mov     rcx, rdx
0x1800033a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033a6  movzx   eax, word ptr [rax+8]
0x1800033aa  add     rsp, 28h
0x1800033ae  retn
```
