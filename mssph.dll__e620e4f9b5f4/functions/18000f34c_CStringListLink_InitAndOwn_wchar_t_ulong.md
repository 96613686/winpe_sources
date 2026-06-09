# CStringListLink::InitAndOwn(wchar_t *,ulong)

- ea: `0x18000f34c`
- end: `0x18000f397`
- name: `?InitAndOwn@CStringListLink@@QEAAXPEA_WK@Z`
- size: `75`
- prototype: `void __fastcall(CStringListLink *__hidden this, wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f474`
- `0x18001f95c`

## callees

- `0x18000f34c`
- `0x18000f42c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f371`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f371`

## pseudocode

```c
void __fastcall CStringListLink::InitAndOwn(CStringListLink *this, wchar_t *a2, unsigned int a3)
{
  void *v5; // rcx

  v5 = (void *)*((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = a2;
  if ( v5 )
    CoTaskMemFree(v5);
  *((_DWORD *)this + 8) = a3;
  *((_DWORD *)this + 4) = PStringHash(a2, a3);
}

```

## disassembly

```asm
0x18000f34c  mov     [rsp+arg_0], rbx
0x18000f351  mov     [rsp+arg_8], rsi
0x18000f356  push    rdi
0x18000f357  sub     rsp, 20h
0x18000f35b  mov     rbx, rcx
0x18000f35e  mov     edi, r8d
0x18000f361  mov     rcx, [rcx+18h]; pv
0x18000f365  mov     rsi, rdx
0x18000f368  mov     [rbx+18h], rdx
0x18000f36c  test    rcx, rcx
0x18000f36f  jz      short loc_18000F377
0x18000f371  call    cs:__imp_CoTaskMemFree
0x18000f377  mov     edx, edi; unsigned int
0x18000f379  mov     [rbx+20h], edi
0x18000f37c  mov     rcx, rsi; wchar_t *
0x18000f37f  call    ?PStringHash@@YAKPEB_WK@Z; PStringHash(wchar_t const *,ulong)
0x18000f384  mov     rsi, [rsp+28h+arg_8]
0x18000f389  mov     [rbx+10h], eax
0x18000f38c  mov     rbx, [rsp+28h+arg_0]
0x18000f391  add     rsp, 20h
0x18000f395  pop     rdi
0x18000f396  retn
```
