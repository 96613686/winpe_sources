# _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)

- ea: `0x18000d188`
- end: `0x18000d26b`
- name: `?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z`
- size: `227`
- prototype: `__int64 __fastcall(_attribute_t *__hidden this, const struct tagHELPER_ATTRIBUTE *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000d274`
- `0x1800121d8`
- `0x180017c3c`

## callees

- `0x18000d158`
- `0x18000d188`
- `0x18000efc0`
- `0x18000f17c`
- `0x18000f1c8`

## pseudocode

```c
__int64 __fastcall _attribute_t::Copy(_attribute_t *this, const struct tagHELPER_ATTRIBUTE *a2)
{
  ATTRIBUTE_TYPE type; // esi
  int v6; // eax
  int v7; // esi

  if ( !a2 )
    return 2147942487LL;
  if ( this == (_attribute_t *)a2 )
    return 0;
  type = a2->type;
  _attribute_t::Clear(this);
  if ( type == AT_STRING )
  {
    v6 = _attribute_t::SetValue(this, a2->PWStr);
    goto LABEL_8;
  }
  if ( type == AT_OCTET_STRING )
  {
    v6 = _attribute_t::SetValue(this, &a2->OctetString);
LABEL_8:
    v7 = v6;
    if ( v6 < 0 )
    {
LABEL_12:
      _attribute_t::Clear(this);
      return (unsigned int)v7;
    }
    goto LABEL_11;
  }
  *(_OWORD *)this = *(_OWORD *)&a2->pwszName;
  *((_OWORD *)this + 1) = *(_OWORD *)&a2->Boolean;
  *((_OWORD *)this + 2) = *((_OWORD *)&a2->OctetString + 1);
  *((_OWORD *)this + 3) = *((_OWORD *)&a2->OctetString + 2);
  *((_OWORD *)this + 4) = *((_OWORD *)&a2->OctetString + 3);
  *((_OWORD *)this + 5) = *((_OWORD *)&a2->OctetString + 4);
  *((_OWORD *)this + 6) = *((_OWORD *)&a2->OctetString + 5);
  *((_OWORD *)this + 7) = *((_OWORD *)&a2->OctetString + 6);
  *((_OWORD *)this + 8) = *((_OWORD *)&a2->OctetString + 7);
LABEL_11:
  *(_QWORD *)this = 0;
  v7 = _attribute_t::SetName((unsigned __int16 **)this, a2->pwszName);
  if ( v7 < 0 )
    goto LABEL_12;
  return 0;
}

```

## disassembly

```asm
0x18000d188  mov     [rsp+arg_0], rbx
0x18000d18d  mov     [rsp+arg_8], rsi
0x18000d192  push    rdi
0x18000d193  sub     rsp, 20h
0x18000d197  mov     rdi, rdx
0x18000d19a  mov     rbx, rcx
0x18000d19d  test    rdx, rdx
0x18000d1a0  jnz     short loc_18000D1AC
0x18000d1a2  mov     eax, 80070057h
0x18000d1a7  jmp     loc_18000D25B
0x18000d1ac  cmp     rbx, rdi
0x18000d1af  jz      loc_18000D259
0x18000d1b5  mov     esi, [rdx+8]
0x18000d1b8  call    ?Clear@_attribute_t@@QEAAXXZ; _attribute_t::Clear(void)
0x18000d1bd  cmp     esi, 0Ah
0x18000d1c0  jnz     short loc_18000D1D0
0x18000d1c2  mov     rdx, [rdi+10h]; unsigned __int16 *
0x18000d1c6  mov     rcx, rbx; this
0x18000d1c9  call    ?SetValue@_attribute_t@@QEAAJPEBG@Z; _attribute_t::SetValue(ushort const *)
0x18000d1ce  jmp     short loc_18000D1E1
0x18000d1d0  cmp     esi, 0Eh
0x18000d1d3  jnz     short loc_18000D1E9
0x18000d1d5  lea     rdx, [rdi+10h]; struct tagOCTET_STRING *
0x18000d1d9  mov     rcx, rbx; this
0x18000d1dc  call    ?SetValue@_attribute_t@@QEAAJPEBUtagOCTET_STRING@@@Z; _attribute_t::SetValue(tagOCTET_STRING const *)
0x18000d1e1  mov     esi, eax
0x18000d1e3  test    eax, eax
0x18000d1e5  js      short loc_18000D24D
0x18000d1e7  jmp     short loc_18000D235
0x18000d1e9  movups  xmm0, xmmword ptr [rdi]
0x18000d1ec  movups  xmmword ptr [rbx], xmm0
0x18000d1ef  movups  xmm1, xmmword ptr [rdi+10h]
0x18000d1f3  movups  xmmword ptr [rbx+10h], xmm1
0x18000d1f7  movups  xmm0, xmmword ptr [rdi+20h]
0x18000d1fb  movups  xmmword ptr [rbx+20h], xmm0
0x18000d1ff  movups  xmm1, xmmword ptr [rdi+30h]
0x18000d203  movups  xmmword ptr [rbx+30h], xmm1
0x18000d207  movups  xmm0, xmmword ptr [rdi+40h]
0x18000d20b  movups  xmmword ptr [rbx+40h], xmm0
0x18000d20f  movups  xmm1, xmmword ptr [rdi+50h]
0x18000d213  movups  xmmword ptr [rbx+50h], xmm1
0x18000d217  movups  xmm0, xmmword ptr [rdi+60h]
0x18000d21b  movups  xmmword ptr [rbx+60h], xmm0
0x18000d21f  movups  xmm1, xmmword ptr [rdi+70h]
0x18000d223  movups  xmmword ptr [rbx+70h], xmm1
0x18000d227  movups  xmm0, xmmword ptr [rdi+80h]
0x18000d22e  movups  xmmword ptr [rbx+80h], xmm0
0x18000d235  mov     qword ptr [rbx], 0
0x18000d23c  mov     rcx, rbx; this
0x18000d23f  mov     rdx, [rdi]; unsigned __int16 *
0x18000d242  call    ?SetName@_attribute_t@@QEAAJPEBG@Z; _attribute_t::SetName(ushort const *)
0x18000d247  mov     esi, eax
0x18000d249  test    eax, eax
0x18000d24b  jns     short loc_18000D259
0x18000d24d  mov     rcx, rbx; this
0x18000d250  call    ?Clear@_attribute_t@@QEAAXXZ; _attribute_t::Clear(void)
0x18000d255  mov     eax, esi
0x18000d257  jmp     short loc_18000D25B
0x18000d259  xor     eax, eax
0x18000d25b  mov     rbx, [rsp+28h+arg_0]
0x18000d260  mov     rsi, [rsp+28h+arg_8]
0x18000d265  add     rsp, 20h
0x18000d269  pop     rdi
0x18000d26a  retn
```
