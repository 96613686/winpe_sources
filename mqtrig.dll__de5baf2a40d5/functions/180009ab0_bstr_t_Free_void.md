# _bstr_t::_Free(void)

- ea: `0x180009ab0`
- end: `0x180009b1b`
- name: `?_Free@_bstr_t@@AEAAXXZ`
- size: `107`
- prototype: `void __fastcall(_bstr_t *__hidden this)`
- caller_count: `47`
- callee_count: `1`
- tags: ``

## callers

- `0x18000561c`
- `0x1800056bc`
- `0x180005704`
- `0x180005740`
- `0x180005888`
- `0x180005df4`
- `0x180006bec`
- `0x180006ef0`
- `0x1800082b8`
- `0x180008380`
- `0x1800084d0`
- `0x18000897c`
- `0x180008d68`
- `0x180009420`
- `0x1800097c8`
- `0x18000a300`
- `0x18000c9c0`
- `0x18000cddc`
- `0x18000ce94`
- `0x18000d0e0`
- `0x18000d1a0`
- `0x18000d250`
- `0x18000d310`
- `0x18000d3d0`
- `0x18000d480`
- `0x18000d520`
- `0x180010590`
- `0x180012770`
- `0x180012f40`
- `0x1800164c8`
- `0x1800168e0`
- `0x180016e54`
- `0x180016f70`
- `0x180016fb8`
- `0x180016ff0`
- `0x180017028`
- `0x180017070`
- `0x1800176ec`
- `0x180017890`
- `0x18001792c`
- `0x1800189c4`
- `0x1800190c8`
- `0x180019ce0`
- `0x180019dc0`
- `0x18001a324`
- `0x18001a358`
- `0x18001f159`

## callees

- `0x180009ab0`

## import_xrefs

- `msvcrt!free` at `0x180009af0`
- `msvcrt!free` at `0x180009b02`
- `msvcrt!free` at `0x180009af0`
- `msvcrt!free` at `0x180009b02`
- `OLEAUT32!__imp_SysFreeString` at `0x180009ada`
- `OLEAUT32!__imp_SysFreeString` at `0x180009ada`

## pseudocode

```c
void __fastcall _bstr_t::_Free(_bstr_t *this)
{
  __int64 v2; // rbx
  void *v3; // rcx

  v2 = *(_QWORD *)this;
  if ( *(_QWORD *)this )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 16), 0xFFFFFFFF) == 1 )
    {
      if ( *(_QWORD *)v2 )
      {
        SysFreeString(*(BSTR *)v2);
        *(_QWORD *)v2 = 0;
      }
      v3 = *(void **)(v2 + 8);
      if ( v3 )
      {
        free(v3);
        *(_QWORD *)(v2 + 8) = 0;
      }
      free((void *)v2);
    }
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180009ab0  mov     [rsp+arg_8], rbx
0x180009ab5  push    rdi
0x180009ab6  sub     rsp, 20h
0x180009aba  mov     rdi, rcx
0x180009abd  mov     rbx, [rcx]
0x180009ac0  test    rbx, rbx
0x180009ac3  jz      short loc_180009B10
0x180009ac5  or      eax, 0FFFFFFFFh
0x180009ac8  lock xadd [rbx+10h], eax
0x180009acd  cmp     eax, 1
0x180009ad0  jnz     short loc_180009B09
0x180009ad2  mov     rcx, [rbx]; bstrString
0x180009ad5  test    rcx, rcx
0x180009ad8  jz      short loc_180009AE7
0x180009ada  call    cs:__imp_SysFreeString
0x180009ae0  mov     qword ptr [rbx], 0
0x180009ae7  mov     rcx, [rbx+8]; Block
0x180009aeb  test    rcx, rcx
0x180009aee  jz      short loc_180009AFF
0x180009af0  call    cs:__imp_free
0x180009af6  nop
0x180009af7  mov     qword ptr [rbx+8], 0
0x180009aff  mov     rcx, rbx; Block
0x180009b02  call    cs:__imp_free
0x180009b08  nop
0x180009b09  mov     qword ptr [rdi], 0
0x180009b10  mov     rbx, [rsp+28h+arg_8]
0x180009b15  add     rsp, 20h
0x180009b19  pop     rdi
0x180009b1a  retn
```
