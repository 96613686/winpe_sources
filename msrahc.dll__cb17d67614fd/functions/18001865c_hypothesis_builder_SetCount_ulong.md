# _hypothesis_builder::SetCount(ulong)

- ea: `0x18001865c`
- end: `0x180018729`
- name: `?SetCount@_hypothesis_builder@@QEAAJK@Z`
- size: `205`
- prototype: `__int64 __fastcall(_hypothesis_builder *__hidden this, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f5bc`
- `0x18000f7c8`
- `0x18000fc14`
- `0x180010184`
- `0x1800104f0`

## callees

- `0x18000d458`
- `0x18001865c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800186d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800186d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001868e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001868e`

## pseudocode

```c
__int64 __fastcall _hypothesis_builder::SetCount(_hypothesis_builder *this, unsigned int a2)
{
  __int64 v2; // rsi
  __int64 v4; // rdi
  _BYTE *v5; // rax
  void *v6; // rbp
  __int64 v7; // r14
  _BYTE *v8; // rax

  v2 = a2;
  if ( a2 )
  {
    if ( a2 > 0x1C71C71 )
      return 2147942934LL;
    goto LABEL_4;
  }
  if ( *((_DWORD *)this + 4) || *((_QWORD *)this + 3) )
  {
LABEL_4:
    if ( !*((_QWORD *)this + 4) )
    {
      v4 = 32;
      v5 = CoTaskMemAlloc(0x20u);
      *((_QWORD *)this + 4) = v5;
      if ( !v5 )
        return 2147942414LL;
      do
      {
        *v5++ = 0;
        --v4;
      }
      while ( v4 );
    }
    v6 = (void *)*((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = 0;
    *((_DWORD *)this + 4) = 0;
    if ( (_DWORD)v2 )
    {
      v7 = 144 * v2;
      v8 = CoTaskMemRealloc(v6, 144 * v2);
      v6 = v8;
      if ( !v8 )
        return 2147942414LL;
      for ( ; v7; --v7 )
        *v8++ = 0;
      *(_QWORD *)(*((_QWORD *)this + 4) + 24LL) = v6;
    }
    _attributes_array_t::FreeAll((LPVOID *)this + 2);
    *((_DWORD *)this + 4) = v2;
    *((_QWORD *)this + 3) = v6;
  }
  return 0;
}

```

## disassembly

```asm
0x18001865c  push    rbx
0x18001865e  push    rbp
0x18001865f  push    rsi
0x180018660  push    rdi
0x180018661  push    r14
0x180018663  sub     rsp, 20h
0x180018667  mov     esi, edx
0x180018669  mov     rbx, rcx
0x18001866c  test    edx, edx
0x18001866e  jnz     short loc_1800186E6
0x180018670  cmp     [rcx+10h], edx
0x180018673  jnz     short loc_180018680
0x180018675  cmp     qword ptr [rcx+18h], 0
0x18001867a  jz      loc_18001871C
0x180018680  cmp     qword ptr [rcx+20h], 0
0x180018685  jnz     short loc_1800186A9
0x180018687  mov     edi, 20h ; ' '
0x18001868c  mov     ecx, edi; cb
0x18001868e  call    cs:__imp_CoTaskMemAlloc
0x180018694  mov     [rbx+20h], rax
0x180018698  test    rax, rax
0x18001869b  jz      short loc_1800186DF
0x18001869d  mov     byte ptr [rax], 0
0x1800186a0  inc     rax
0x1800186a3  sub     rdi, 1
0x1800186a7  jnz     short loc_18001869D
0x1800186a9  lea     rdi, [rbx+10h]
0x1800186ad  mov     rbp, [rdi+8]
0x1800186b1  mov     qword ptr [rdi+8], 0
0x1800186b9  mov     dword ptr [rdi], 0
0x1800186bf  test    esi, esi
0x1800186c1  jz      short loc_18001870E
0x1800186c3  lea     r14, [rsi+rsi*8]
0x1800186c7  mov     rcx, rbp; pv
0x1800186ca  shl     r14, 4
0x1800186ce  mov     rdx, r14; cb
0x1800186d1  call    cs:__imp_CoTaskMemRealloc
0x1800186d7  mov     rbp, rax
0x1800186da  test    rax, rax
0x1800186dd  jnz     short loc_1800186F5
0x1800186df  mov     eax, 8007000Eh
0x1800186e4  jmp     short loc_18001871E
0x1800186e6  cmp     esi, 1C71C71h
0x1800186ec  jbe     short loc_180018680
0x1800186ee  mov     eax, 80070216h
0x1800186f3  jmp     short loc_18001871E
0x1800186f5  test    r14, r14
0x1800186f8  jz      short loc_180018706
0x1800186fa  mov     byte ptr [rax], 0
0x1800186fd  inc     rax
0x180018700  sub     r14, 1
0x180018704  jnz     short loc_1800186FA
0x180018706  mov     rax, [rbx+20h]
0x18001870a  mov     [rax+18h], rbp
0x18001870e  mov     rcx, rdi; this
0x180018711  call    ?FreeAll@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeAll(void)
0x180018716  mov     [rdi], esi
0x180018718  mov     [rdi+8], rbp
0x18001871c  xor     eax, eax
0x18001871e  add     rsp, 20h
0x180018722  pop     r14
0x180018724  pop     rdi
0x180018725  pop     rsi
0x180018726  pop     rbp
0x180018727  pop     rbx
0x180018728  retn
```
