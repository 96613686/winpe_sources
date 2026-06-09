# _hypothesis_builder::SetCount(ulong)

- ea: `0x18000b028`
- end: `0x18000b0ff`
- name: `?SetCount@_hypothesis_builder@@QEAAJK@Z`
- size: `215`
- prototype: `__int64 __fastcall(_hypothesis_builder *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006970`

## callees

- `0x180006628`
- `0x18000b028`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b0e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b0e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000b09d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000b09d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b05a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b05a`

## pseudocode

```c
__int64 __fastcall _hypothesis_builder::SetCount(_hypothesis_builder *this, unsigned int a2)
{
  __int64 v2; // rsi
  __int64 v4; // rbx
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
    _attributes_array_t::FreeElements((_hypothesis_builder *)((char *)this + 16));
    CoTaskMemFree(*((LPVOID *)this + 3));
    *((_DWORD *)this + 4) = v2;
    *((_QWORD *)this + 3) = v6;
  }
  return 0;
}

```

## disassembly

```asm
0x18000b028  push    rbx
0x18000b02a  push    rbp
0x18000b02b  push    rsi
0x18000b02c  push    rdi
0x18000b02d  push    r14
0x18000b02f  sub     rsp, 20h
0x18000b033  mov     esi, edx
0x18000b035  mov     rdi, rcx
0x18000b038  test    edx, edx
0x18000b03a  jnz     short loc_18000B0B2
0x18000b03c  cmp     [rcx+10h], edx
0x18000b03f  jnz     short loc_18000B04C
0x18000b041  cmp     qword ptr [rcx+18h], 0
0x18000b046  jz      loc_18000B0F2
0x18000b04c  cmp     qword ptr [rcx+20h], 0
0x18000b051  jnz     short loc_18000B075
0x18000b053  mov     ebx, 20h ; ' '
0x18000b058  mov     ecx, ebx; cb
0x18000b05a  call    cs:__imp_CoTaskMemAlloc
0x18000b060  mov     [rdi+20h], rax
0x18000b064  test    rax, rax
0x18000b067  jz      short loc_18000B0AB
0x18000b069  mov     byte ptr [rax], 0
0x18000b06c  inc     rax
0x18000b06f  sub     rbx, 1
0x18000b073  jnz     short loc_18000B069
0x18000b075  lea     rbx, [rdi+10h]
0x18000b079  mov     rbp, [rbx+8]
0x18000b07d  mov     qword ptr [rbx+8], 0
0x18000b085  mov     dword ptr [rbx], 0
0x18000b08b  test    esi, esi
0x18000b08d  jz      short loc_18000B0DA
0x18000b08f  lea     r14, [rsi+rsi*8]
0x18000b093  mov     rcx, rbp; pv
0x18000b096  shl     r14, 4
0x18000b09a  mov     rdx, r14; cb
0x18000b09d  call    cs:__imp_CoTaskMemRealloc
0x18000b0a3  mov     rbp, rax
0x18000b0a6  test    rax, rax
0x18000b0a9  jnz     short loc_18000B0C1
0x18000b0ab  mov     eax, 8007000Eh
0x18000b0b0  jmp     short loc_18000B0F4
0x18000b0b2  cmp     esi, 1C71C71h
0x18000b0b8  jbe     short loc_18000B04C
0x18000b0ba  mov     eax, 80070216h
0x18000b0bf  jmp     short loc_18000B0F4
0x18000b0c1  test    r14, r14
0x18000b0c4  jz      short loc_18000B0D2
0x18000b0c6  mov     byte ptr [rax], 0
0x18000b0c9  inc     rax
0x18000b0cc  sub     r14, 1
0x18000b0d0  jnz     short loc_18000B0C6
0x18000b0d2  mov     rax, [rdi+20h]
0x18000b0d6  mov     [rax+18h], rbp
0x18000b0da  mov     rcx, rbx; this
0x18000b0dd  call    ?FreeElements@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeElements(void)
0x18000b0e2  mov     rcx, [rbx+8]; pv
0x18000b0e6  call    cs:__imp_CoTaskMemFree
0x18000b0ec  mov     [rbx], esi
0x18000b0ee  mov     [rbx+8], rbp
0x18000b0f2  xor     eax, eax
0x18000b0f4  add     rsp, 20h
0x18000b0f8  pop     r14
0x18000b0fa  pop     rdi
0x18000b0fb  pop     rsi
0x18000b0fc  pop     rbp
0x18000b0fd  pop     rbx
0x18000b0fe  retn
```
