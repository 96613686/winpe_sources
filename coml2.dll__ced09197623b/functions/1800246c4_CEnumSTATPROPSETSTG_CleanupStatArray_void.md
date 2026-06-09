# CEnumSTATPROPSETSTG::CleanupStatArray(void)

- ea: `0x1800246c4`
- end: `0x180024719`
- name: `?CleanupStatArray@CEnumSTATPROPSETSTG@@AEAAXXZ`
- size: `85`
- prototype: `void __fastcall(CEnumSTATPROPSETSTG *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024280`
- `0x180056a50`
- `0x180056f40`

## callees

- `0x1800246c4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024701`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024701`

## pseudocode

```c
void __fastcall CEnumSTATPROPSETSTG::CleanupStatArray(CEnumSTATPROPSETSTG *this)
{
  __int64 i; // rsi
  __int64 v3; // rbx

  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 26); *((_QWORD *)this + v3 + 3) = 0 )
  {
    v3 = 10 * i;
    CoTaskMemFree(*((LPVOID *)this + 10 * i + 3));
    i = (unsigned int)(i + 1);
  }
  *((_QWORD *)this + 13) = 0;
}

```

## disassembly

```asm
0x1800246c4  mov     [rsp+arg_0], rbx
0x1800246c9  mov     [rsp+arg_8], rsi
0x1800246ce  push    rdi
0x1800246cf  sub     rsp, 20h
0x1800246d3  xor     esi, esi
0x1800246d5  mov     rdi, rcx
0x1800246d8  cmp     [rcx+68h], esi
0x1800246db  ja      short loc_1800246F5
0x1800246dd  mov     rbx, [rsp+28h+arg_0]
0x1800246e2  mov     rsi, [rsp+28h+arg_8]
0x1800246e7  mov     qword ptr [rdi+68h], 0
0x1800246ef  add     rsp, 20h
0x1800246f3  pop     rdi
0x1800246f4  retn
0x1800246f5  lea     rbx, [rsi+rsi*4]
0x1800246f9  add     rbx, rbx
0x1800246fc  mov     rcx, [rdi+rbx*8+18h]; pv
0x180024701  call    cs:__imp_CoTaskMemFree
0x180024707  inc     esi
0x180024709  mov     qword ptr [rdi+rbx*8+18h], 0
0x180024712  cmp     esi, [rdi+68h]
0x180024715  jnb     short loc_1800246DD
0x180024717  jmp     short loc_1800246F5
```
