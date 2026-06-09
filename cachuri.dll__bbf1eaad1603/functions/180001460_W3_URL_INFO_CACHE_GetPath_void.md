# W3_URL_INFO_CACHE::GetPath(void *)

- ea: `0x180001460`
- end: `0x180001488`
- name: `?GetPath@W3_URL_INFO_CACHE@@UEAAPEBGPEAX@Z`
- size: `40`
- prototype: `const unsigned __int16 *__fastcall(W3_URL_INFO_CACHE *this, __int64 (__fastcall ***)(_QWORD))`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003010`

## pseudocode

```c
const unsigned __int16 *__fastcall W3_URL_INFO_CACHE::GetPath(
        W3_URL_INFO_CACHE *this,
        __int64 (__fastcall ***a2)(_QWORD))
{
  __int64 v2; // rax

  v2 = (**a2)(a2);
  return (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 72LL))(v2);
}

```

## disassembly

```asm
0x180001460  sub     rsp, 28h
0x180001464  mov     rax, [rdx]
0x180001467  mov     rcx, rdx
0x18000146a  mov     rax, [rax]
0x18000146d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001472  mov     rdx, rax
0x180001475  mov     rcx, [rax]
0x180001478  mov     rax, [rcx+48h]
0x18000147c  mov     rcx, rdx
0x18000147f  add     rsp, 28h
0x180001483  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
