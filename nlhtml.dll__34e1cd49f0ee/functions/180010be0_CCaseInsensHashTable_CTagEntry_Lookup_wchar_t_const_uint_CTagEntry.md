# CCaseInsensHashTable<CTagEntry *>::Lookup(wchar_t const *,uint,CTagEntry * &)

- ea: `0x180010be0`
- end: `0x180010c4d`
- name: `?Lookup@?$CCaseInsensHashTable@PEAVCTagEntry@@@@UEAAHPEB_WIAEAPEAVCTagEntry@@@Z`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180010be0`
- `0x180025010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180010c18`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180010c18`

## pseudocode

```c
__int64 __fastcall CCaseInsensHashTable<CTagEntry *>::Lookup(__int64 a1, __int64 a2, unsigned int a3, _QWORD *a4)
{
  __int64 v5; // rsi
  _QWORD *i; // rbx
  __int64 v8; // r9

  v5 = a3;
  for ( i = *(_QWORD **)(a1 + 8LL * (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1) + 8);
        i;
        i = (_QWORD *)i[2] )
  {
    if ( !(unsigned int)_o__wcsnicmp(a2, *i, v5, v8) && !*(_WORD *)(*i + 2 * v5) )
    {
      *a4 = i[1];
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180010be0  push    rbx
0x180010be2  push    rbp
0x180010be3  push    rsi
0x180010be4  push    rdi
0x180010be5  push    r14
0x180010be7  sub     rsp, 20h
0x180010beb  mov     rax, [rcx]
0x180010bee  mov     r14, r9
0x180010bf1  mov     esi, r8d
0x180010bf4  mov     rbp, rdx
0x180010bf7  mov     rdi, rcx
0x180010bfa  mov     rax, [rax+10h]
0x180010bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c03  mov     ebx, eax
0x180010c05  mov     rbx, [rdi+rbx*8+8]
0x180010c0a  test    rbx, rbx
0x180010c0d  jz      short loc_180010C49
0x180010c0f  mov     rdx, [rbx]
0x180010c12  mov     r8, rsi
0x180010c15  mov     rcx, rbp
0x180010c18  call    cs:__imp__o__wcsnicmp
0x180010c1e  test    eax, eax
0x180010c20  jnz     short loc_180010C43
0x180010c22  mov     rax, [rbx]
0x180010c25  cmp     word ptr [rax+rsi*2], 0
0x180010c2a  jnz     short loc_180010C43
0x180010c2c  mov     rax, [rbx+8]
0x180010c30  mov     [r14], rax
0x180010c33  mov     eax, 1
0x180010c38  add     rsp, 20h
0x180010c3c  pop     r14
0x180010c3e  pop     rdi
0x180010c3f  pop     rsi
0x180010c40  pop     rbp
0x180010c41  pop     rbx
0x180010c42  retn
0x180010c43  mov     rbx, [rbx+10h]
0x180010c47  jmp     short loc_180010C0A
0x180010c49  xor     eax, eax
0x180010c4b  jmp     short loc_180010C38
```
