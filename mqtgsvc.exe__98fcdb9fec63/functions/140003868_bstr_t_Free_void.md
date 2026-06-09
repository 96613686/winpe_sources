# _bstr_t::_Free(void)

- ea: `0x140003868`
- end: `0x1400038d3`
- name: `?_Free@_bstr_t@@AEAAXXZ`
- size: `107`
- prototype: `void __fastcall(_bstr_t *__hidden this)`
- caller_count: `33`
- callee_count: `1`
- tags: ``

## callers

- `0x140003194`
- `0x140005e40`
- `0x140005f1c`
- `0x140006af4`
- `0x140007034`
- `0x1400076a8`
- `0x14000799c`
- `0x140007a18`
- `0x140007a64`
- `0x14000858c`
- `0x140009180`
- `0x140009994`
- `0x140009e04`
- `0x14000a3a8`
- `0x14000a6dc`
- `0x14000ac9c`
- `0x14000b2f0`
- `0x14000b6f0`
- `0x14000baa8`
- `0x14000c720`
- `0x14000d4a8`
- `0x14000e768`
- `0x14000eb04`
- `0x14000fbcc`
- `0x14000fda4`
- `0x14000fe40`
- `0x140010ec0`
- `0x140011d38`
- `0x14001201c`
- `0x1400120e8`
- `0x140015d64`
- `0x140015e8c`
- `0x140016024`

## callees

- `0x140003868`

## import_xrefs

- `msvcrt!free` at `0x1400038a8`
- `msvcrt!free` at `0x1400038ba`
- `msvcrt!free` at `0x1400038a8`
- `msvcrt!free` at `0x1400038ba`
- `OLEAUT32!__imp_SysFreeString` at `0x140003892`
- `OLEAUT32!__imp_SysFreeString` at `0x140003892`

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
0x140003868  mov     [rsp+arg_8], rbx
0x14000386d  push    rdi
0x14000386e  sub     rsp, 20h
0x140003872  mov     rdi, rcx
0x140003875  mov     rbx, [rcx]
0x140003878  test    rbx, rbx
0x14000387b  jz      short loc_1400038C8
0x14000387d  or      eax, 0FFFFFFFFh
0x140003880  lock xadd [rbx+10h], eax
0x140003885  cmp     eax, 1
0x140003888  jnz     short loc_1400038C1
0x14000388a  mov     rcx, [rbx]; bstrString
0x14000388d  test    rcx, rcx
0x140003890  jz      short loc_14000389F
0x140003892  call    cs:__imp_SysFreeString
0x140003898  mov     qword ptr [rbx], 0
0x14000389f  mov     rcx, [rbx+8]; Block
0x1400038a3  test    rcx, rcx
0x1400038a6  jz      short loc_1400038B7
0x1400038a8  call    cs:__imp_free
0x1400038ae  nop
0x1400038af  mov     qword ptr [rbx+8], 0
0x1400038b7  mov     rcx, rbx; Block
0x1400038ba  call    cs:__imp_free
0x1400038c0  nop
0x1400038c1  mov     qword ptr [rdi], 0
0x1400038c8  mov     rbx, [rsp+28h+arg_8]
0x1400038cd  add     rsp, 20h
0x1400038d1  pop     rdi
0x1400038d2  retn
```
