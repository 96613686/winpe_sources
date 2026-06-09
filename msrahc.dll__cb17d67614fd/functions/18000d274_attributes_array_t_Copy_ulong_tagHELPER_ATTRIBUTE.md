# _attributes_array_t::Copy(ulong,tagHELPER_ATTRIBUTE *)

- ea: `0x18000d274`
- end: `0x18000d3ce`
- name: `?Copy@_attributes_array_t@@QEAAJKPEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `346`
- prototype: `__int64 __fastcall(_attributes_array_t *__hidden this, unsigned int, struct tagHELPER_ATTRIBUTE *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18000e170`
- `0x180018040`

## callees

- `0x18000d158`
- `0x18000d188`
- `0x18000d274`
- `0x18000d42c`
- `0x18000d458`
- `0x18000ef4c`
- `0x18000efc0`
- `0x18000f17c`
- `0x18000f1c8`

## pseudocode

```c
__int64 __fastcall _attributes_array_t::Copy(
        _attributes_array_t *this,
        unsigned int a2,
        struct tagHELPER_ATTRIBUTE *a3)
{
  __int64 result; // rax
  __int64 i; // rsi
  __int64 v7; // rbx
  __int64 v8; // rdi
  int v9; // eax
  int v10; // ebx
  tagOCTET_STRING v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  const unsigned __int16 *v19; // rdx
  unsigned __int16 *v20[2]; // [rsp+20h] [rbp-69h] BYREF
  tagOCTET_STRING v21; // [rsp+30h] [rbp-59h] BYREF
  __int128 v22; // [rsp+40h] [rbp-49h]
  __int128 v23; // [rsp+50h] [rbp-39h]
  __int128 v24; // [rsp+60h] [rbp-29h]
  __int128 v25; // [rsp+70h] [rbp-19h]
  __int128 v26; // [rsp+80h] [rbp-9h]
  __int128 v27; // [rsp+90h] [rbp+7h]
  __int128 v28; // [rsp+A0h] [rbp+17h]

  if ( a2 && a3 )
  {
    result = _attributes_array_t::SetCount(this, a2);
    if ( (int)result < 0 )
      return result;
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= *(_DWORD *)this )
        return 0;
      v7 = *((_QWORD *)this + 1);
      v20[0] = 0;
      LODWORD(v20[1]) = 0;
      _attribute_t::Copy((_attribute_t *)v20, &a3[i]);
      v8 = v7 + 144 * i;
      if ( (unsigned __int16 **)v8 == v20 )
        goto LABEL_16;
      _attribute_t::Clear((_attribute_t *)v8);
      if ( LODWORD(v20[1]) == 10 )
      {
        v9 = _attribute_t::SetValue((_attribute_t *)v8, *(const unsigned __int16 **)&v21.dwLength);
      }
      else
      {
        if ( LODWORD(v20[1]) != 14 )
        {
          v11 = v21;
          *(_OWORD *)v8 = *(_OWORD *)v20;
          v12 = v22;
          *(tagOCTET_STRING *)(v8 + 16) = v11;
          v13 = v23;
          *(_OWORD *)(v8 + 32) = v12;
          v14 = v24;
          *(_OWORD *)(v8 + 48) = v13;
          v15 = v25;
          *(_OWORD *)(v8 + 64) = v14;
          v16 = v26;
          *(_OWORD *)(v8 + 80) = v15;
          v17 = v27;
          *(_OWORD *)(v8 + 96) = v16;
          v18 = v28;
          *(_OWORD *)(v8 + 112) = v17;
          *(_OWORD *)(v8 + 128) = v18;
          goto LABEL_14;
        }
        v9 = _attribute_t::SetValue((_attribute_t *)v8, &v21);
      }
      v10 = v9;
      if ( v9 < 0 )
        goto LABEL_15;
LABEL_14:
      v19 = v20[0];
      *(_QWORD *)v8 = 0;
      v10 = _attribute_t::SetName((unsigned __int16 **)v8, v19);
      if ( v10 < 0 )
      {
LABEL_15:
        _attribute_t::Clear((_attribute_t *)v8);
        goto LABEL_17;
      }
LABEL_16:
      v10 = 0;
LABEL_17:
      _attribute_t::FreeAll((_attribute_t *)v20);
      if ( v10 < 0 )
      {
        _attributes_array_t::FreeAll(this);
        return (unsigned int)v10;
      }
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000d274  push    rbp
0x18000d276  push    rbx
0x18000d277  push    rsi
0x18000d278  push    rdi
0x18000d279  push    r14
0x18000d27b  push    r15
0x18000d27d  lea     rbp, [rsp-2Fh]
0x18000d282  sub     rsp, 0B8h
0x18000d289  mov     r15, r8
0x18000d28c  mov     r14, rcx
0x18000d28f  test    edx, edx
0x18000d291  jz      loc_18000D3B9
0x18000d297  test    r8, r8
0x18000d29a  jz      loc_18000D3B9
0x18000d2a0  call    ?SetCount@_attributes_array_t@@QEAAJK@Z; _attributes_array_t::SetCount(ulong)
0x18000d2a5  test    eax, eax
0x18000d2a7  js      loc_18000D3BE
0x18000d2ad  xor     esi, esi
0x18000d2af  cmp     esi, [r14]
0x18000d2b2  jnb     loc_18000D3B5
0x18000d2b8  mov     rbx, [r14+8]
0x18000d2bc  lea     rdi, [rsi+rsi*8]
0x18000d2c0  shl     rdi, 4
0x18000d2c4  lea     rcx, [rbp+57h+var_C0]; this
0x18000d2c8  mov     [rbp+57h+var_C0], 0
0x18000d2d0  mov     dword ptr [rbp+57h+var_C0+8], 0
0x18000d2d7  lea     rdx, [rdi+r15]; struct tagHELPER_ATTRIBUTE *
0x18000d2db  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x18000d2e0  lea     rax, [rbp+57h+var_C0]
0x18000d2e4  add     rdi, rbx
0x18000d2e7  cmp     rdi, rax
0x18000d2ea  jz      loc_18000D393
0x18000d2f0  mov     rcx, rdi; this
0x18000d2f3  call    ?Clear@_attribute_t@@QEAAXXZ; _attribute_t::Clear(void)
0x18000d2f8  cmp     dword ptr [rbp+57h+var_C0+8], 0Ah
0x18000d2fc  jnz     short loc_18000D30C
0x18000d2fe  mov     rdx, qword ptr [rbp+57h+var_B0.dwLength]; unsigned __int16 *
0x18000d302  mov     rcx, rdi; this
0x18000d305  call    ?SetValue@_attribute_t@@QEAAJPEBG@Z; _attribute_t::SetValue(ushort const *)
0x18000d30a  jmp     short loc_18000D31E
0x18000d30c  cmp     dword ptr [rbp+57h+var_C0+8], 0Eh
0x18000d310  jnz     short loc_18000D326
0x18000d312  lea     rdx, [rbp+57h+var_B0]; struct tagOCTET_STRING *
0x18000d316  mov     rcx, rdi; this
0x18000d319  call    ?SetValue@_attribute_t@@QEAAJPEBUtagOCTET_STRING@@@Z; _attribute_t::SetValue(tagOCTET_STRING const *)
0x18000d31e  mov     ebx, eax
0x18000d320  test    eax, eax
0x18000d322  js      short loc_18000D389
0x18000d324  jmp     short loc_18000D370
0x18000d326  movups  xmm0, xmmword ptr [rbp+57h+var_C0]
0x18000d32a  movups  xmm1, xmmword ptr [rbp+57h+var_B0.dwLength]
0x18000d32e  movups  xmmword ptr [rdi], xmm0
0x18000d331  movups  xmm0, [rbp+57h+var_A0]
0x18000d335  movups  xmmword ptr [rdi+10h], xmm1
0x18000d339  movups  xmm1, [rbp+57h+var_90]
0x18000d33d  movups  xmmword ptr [rdi+20h], xmm0
0x18000d341  movups  xmm0, [rbp+57h+var_80]
0x18000d345  movups  xmmword ptr [rdi+30h], xmm1
0x18000d349  movups  xmm1, [rbp+57h+var_70]
0x18000d34d  movups  xmmword ptr [rdi+40h], xmm0
0x18000d351  movups  xmm0, [rbp+57h+var_60]
0x18000d355  movups  xmmword ptr [rdi+50h], xmm1
0x18000d359  movups  xmm1, [rbp+57h+var_50]
0x18000d35d  movups  xmmword ptr [rdi+60h], xmm0
0x18000d361  movups  xmm0, [rbp+57h+var_40]
0x18000d365  movups  xmmword ptr [rdi+70h], xmm1
0x18000d369  movups  xmmword ptr [rdi+80h], xmm0
0x18000d370  mov     rdx, [rbp+57h+var_C0]; unsigned __int16 *
0x18000d374  mov     rcx, rdi; this
0x18000d377  mov     qword ptr [rdi], 0
0x18000d37e  call    ?SetName@_attribute_t@@QEAAJPEBG@Z; _attribute_t::SetName(ushort const *)
0x18000d383  mov     ebx, eax
0x18000d385  test    eax, eax
0x18000d387  jns     short loc_18000D393
0x18000d389  mov     rcx, rdi; this
0x18000d38c  call    ?Clear@_attribute_t@@QEAAXXZ; _attribute_t::Clear(void)
0x18000d391  jmp     short loc_18000D395
0x18000d393  xor     ebx, ebx
0x18000d395  lea     rcx, [rbp+57h+var_C0]; this
0x18000d399  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000d39e  test    ebx, ebx
0x18000d3a0  js      short loc_18000D3A9
0x18000d3a2  inc     esi
0x18000d3a4  jmp     loc_18000D2AF
0x18000d3a9  mov     rcx, r14; this
0x18000d3ac  call    ?FreeAll@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeAll(void)
0x18000d3b1  mov     eax, ebx
0x18000d3b3  jmp     short loc_18000D3BE
0x18000d3b5  xor     eax, eax
0x18000d3b7  jmp     short loc_18000D3BE
0x18000d3b9  mov     eax, 80070057h
0x18000d3be  add     rsp, 0B8h
0x18000d3c5  pop     r15
0x18000d3c7  pop     r14
0x18000d3c9  pop     rdi
0x18000d3ca  pop     rsi
0x18000d3cb  pop     rbx
0x18000d3cc  pop     rbp
0x18000d3cd  retn
```
