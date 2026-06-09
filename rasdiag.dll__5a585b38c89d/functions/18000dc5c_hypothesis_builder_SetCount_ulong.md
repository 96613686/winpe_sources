# _hypothesis_builder::SetCount(ulong)

- ea: `0x18000dc5c`
- end: `0x18000dd5e`
- name: `?SetCount@_hypothesis_builder@@QEAAJK@Z`
- size: `258`
- prototype: `__int64 __fastcall(_hypothesis_builder *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006ac0`
- `0x1800086b0`
- `0x180009e60`
- `0x18000ad60`

## callees

- `0x18000678c`
- `0x18000dc5c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000dcd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000dcd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dc8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dc8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd3f`

## pseudocode

```c
__int64 __fastcall _hypothesis_builder::SetCount(_hypothesis_builder *this, unsigned int a2)
{
  __int64 v2; // rdi
  __int64 v4; // rsi
  _BYTE *v5; // rax
  void *v6; // rbp
  __int64 v7; // rsi
  _BYTE *v8; // rax
  __int64 i; // rsi

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
    if ( *((_QWORD *)this + 3) )
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)this + 4); i = (unsigned int)(i + 1) )
        _attribute_t::FreeAll((LPVOID *)(*((_QWORD *)this + 3) + 144 * i));
    }
    CoTaskMemFree(*((LPVOID *)this + 3));
    *((_DWORD *)this + 4) = v2;
    *((_QWORD *)this + 3) = v6;
  }
  return 0;
}

```

## disassembly

```asm
0x18000dc5c  push    rbx
0x18000dc5e  push    rbp
0x18000dc5f  push    rsi
0x18000dc60  push    rdi
0x18000dc61  sub     rsp, 28h
0x18000dc65  mov     edi, edx
0x18000dc67  mov     rbx, rcx
0x18000dc6a  test    edx, edx
0x18000dc6c  jnz     short loc_18000DCED
0x18000dc6e  cmp     [rcx+10h], edx
0x18000dc71  jnz     short loc_18000DC7E
0x18000dc73  cmp     qword ptr [rcx+18h], 0
0x18000dc78  jz      loc_18000DD52
0x18000dc7e  cmp     qword ptr [rcx+20h], 0
0x18000dc83  jnz     short loc_18000DCAD
0x18000dc85  mov     esi, 20h ; ' '
0x18000dc8a  mov     ecx, esi; cb
0x18000dc8c  call    cs:__imp_CoTaskMemAlloc
0x18000dc93  nop     dword ptr [rax+rax+00h]
0x18000dc98  mov     [rbx+20h], rax
0x18000dc9c  test    rax, rax
0x18000dc9f  jz      short loc_18000DCE6
0x18000dca1  mov     byte ptr [rax], 0
0x18000dca4  inc     rax
0x18000dca7  sub     rsi, 1
0x18000dcab  jnz     short loc_18000DCA1
0x18000dcad  mov     rbp, [rbx+18h]
0x18000dcb1  mov     qword ptr [rbx+18h], 0
0x18000dcb9  mov     dword ptr [rbx+10h], 0
0x18000dcc0  test    edi, edi
0x18000dcc2  jz      short loc_18000DD15
0x18000dcc4  lea     rsi, [rdi+rdi*8]
0x18000dcc8  mov     rcx, rbp; pv
0x18000dccb  shl     rsi, 4
0x18000dccf  mov     rdx, rsi; cb
0x18000dcd2  call    cs:__imp_CoTaskMemRealloc
0x18000dcd9  nop     dword ptr [rax+rax+00h]
0x18000dcde  mov     rbp, rax
0x18000dce1  test    rax, rax
0x18000dce4  jnz     short loc_18000DCFC
0x18000dce6  mov     eax, 8007000Eh
0x18000dceb  jmp     short loc_18000DD54
0x18000dced  cmp     edi, 1C71C71h
0x18000dcf3  jbe     short loc_18000DC7E
0x18000dcf5  mov     eax, 80070216h
0x18000dcfa  jmp     short loc_18000DD54
0x18000dcfc  test    rsi, rsi
0x18000dcff  jz      short loc_18000DD0D
0x18000dd01  mov     byte ptr [rax], 0
0x18000dd04  inc     rax
0x18000dd07  sub     rsi, 1
0x18000dd0b  jnz     short loc_18000DD01
0x18000dd0d  mov     rax, [rbx+20h]
0x18000dd11  mov     [rax+18h], rbp
0x18000dd15  cmp     qword ptr [rbx+18h], 0
0x18000dd1a  jz      short loc_18000DD3B
0x18000dd1c  xor     esi, esi
0x18000dd1e  cmp     [rbx+10h], esi
0x18000dd21  jbe     short loc_18000DD3B
0x18000dd23  lea     rcx, [rsi+rsi*8]
0x18000dd27  shl     rcx, 4
0x18000dd2b  add     rcx, [rbx+18h]; this
0x18000dd2f  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000dd34  inc     esi
0x18000dd36  cmp     esi, [rbx+10h]
0x18000dd39  jb      short loc_18000DD23
0x18000dd3b  mov     rcx, [rbx+18h]; pv
0x18000dd3f  call    cs:__imp_CoTaskMemFree
0x18000dd46  nop     dword ptr [rax+rax+00h]
0x18000dd4b  mov     [rbx+10h], edi
0x18000dd4e  mov     [rbx+18h], rbp
0x18000dd52  xor     eax, eax
0x18000dd54  add     rsp, 28h
0x18000dd58  pop     rdi
0x18000dd59  pop     rsi
0x18000dd5a  pop     rbp
0x18000dd5b  pop     rbx
0x18000dd5c  retn
```
