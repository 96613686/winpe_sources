# CACHED_FILE_KEY::GetIsPrefix(IHttpCacheKey *)

- ea: `0x180003b40`
- end: `0x180003b8f`
- name: `?GetIsPrefix@CACHED_FILE_KEY@@UEBA_NPEAVIHttpCacheKey@@@Z`
- size: `79`
- prototype: `bool __fastcall(CACHED_FILE_KEY *__hidden this, struct IHttpCacheKey *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003c3e`
- `0x180004010`

## pseudocode

```c
bool __fastcall CACHED_FILE_KEY::GetIsPrefix(CACHED_FILE_KEY *this, struct IHttpCacheKey *a2)
{
  unsigned int v3; // ebp
  __int64 (__fastcall *v4)(CACHED_FILE_KEY *); // rdi
  const wchar_t *v5; // rbx
  const wchar_t *v6; // rax

  v3 = *((_DWORD *)this + 14);
  v4 = *(__int64 (__fastcall **)(CACHED_FILE_KEY *))(*(_QWORD *)this + 40LL);
  v5 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IHttpCacheKey *))(*(_QWORD *)a2 + 40LL))(a2);
  v6 = (const wchar_t *)v4(this);
  return wcsncmp_0(v6, v5, v3) == 0;
}

```

## disassembly

```asm
0x180003b40  push    rbx
0x180003b42  push    rbp
0x180003b43  push    rsi
0x180003b44  push    rdi
0x180003b45  sub     rsp, 28h
0x180003b49  mov     r9, [rcx]
0x180003b4c  mov     rsi, rcx
0x180003b4f  mov     rax, [rdx]
0x180003b52  mov     ebp, [rcx+38h]
0x180003b55  mov     rcx, rdx
0x180003b58  mov     rdi, [r9+28h]
0x180003b5c  mov     rax, [rax+28h]
0x180003b60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b65  mov     rbx, rax
0x180003b68  mov     rcx, rsi
0x180003b6b  mov     rax, rdi
0x180003b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b73  mov     rcx, rax; String1
0x180003b76  mov     r8d, ebp; MaxCount
0x180003b79  mov     rdx, rbx; String2
0x180003b7c  call    wcsncmp_0
0x180003b81  test    eax, eax
0x180003b83  setz    al
0x180003b86  add     rsp, 28h
0x180003b8a  pop     rdi
0x180003b8b  pop     rsi
0x180003b8c  pop     rbp
0x180003b8d  pop     rbx
0x180003b8e  retn
```
