# _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)

- ea: `0x180006274`
- end: `0x18000639c`
- name: `?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(struct tagHELPER_ATTRIBUTE *this, const struct tagHELPER_ATTRIBUTE *)`
- caller_count: `6`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180006ac0`
- `0x1800086b0`
- `0x180009e60`
- `0x18000ad60`
- `0x18000d100`
- `0x18000d560`

## callees

- `0x180006274`
- `0x18000678c`
- `0x180007dc0`
- `0x180007e58`
- `0x180008084`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006347`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006347`

## pseudocode

```c
__int64 __fastcall _attribute_t::Copy(struct tagHELPER_ATTRIBUTE *this, const struct tagHELPER_ATTRIBUTE *a2)
{
  ATTRIBUTE_TYPE type; // esi
  __int64 v6; // rbp
  char *p_Char; // r14
  __int64 v8; // rcx
  char *v9; // rax
  int v10; // eax
  int v11; // esi
  const unsigned __int16 *pwszName; // rdi

  if ( !a2 )
    return 2147942487LL;
  if ( this == a2 )
    return 0;
  type = a2->type;
  _attribute_t::FreeAll((_attribute_t *)this);
  v6 = 128;
  p_Char = &this->Char;
  v8 = 128;
  v9 = &this->Char;
  do
  {
    *v9++ = 0;
    --v8;
  }
  while ( v8 );
  if ( type == AT_STRING )
  {
    v10 = _attribute_t::SetValue((_attribute_t *)this, a2->PWStr);
  }
  else
  {
    if ( type != AT_OCTET_STRING )
    {
      *(_OWORD *)&this->pwszName = *(_OWORD *)&a2->pwszName;
      *(_OWORD *)&this->Boolean = *(_OWORD *)&a2->Boolean;
      *((_OWORD *)&this->OctetString + 1) = *((_OWORD *)&a2->OctetString + 1);
      *((_OWORD *)&this->OctetString + 2) = *((_OWORD *)&a2->OctetString + 2);
      *((_OWORD *)&this->OctetString + 3) = *((_OWORD *)&a2->OctetString + 3);
      *((_OWORD *)&this->OctetString + 4) = *((_OWORD *)&a2->OctetString + 4);
      *((_OWORD *)&this->OctetString + 5) = *((_OWORD *)&a2->OctetString + 5);
      *((_OWORD *)&this->OctetString + 6) = *((_OWORD *)&a2->OctetString + 6);
      *((_OWORD *)&this->OctetString + 7) = *((_OWORD *)&a2->OctetString + 7);
LABEL_13:
      this->pwszName = 0;
      pwszName = a2->pwszName;
      CoTaskMemFree(0);
      this->pwszName = 0;
      if ( pwszName )
      {
        v11 = StringCchCopyWithAlloc(&this->pwszName, 0xFFFFu, pwszName);
        if ( v11 < 0 )
          goto LABEL_15;
      }
      return 0;
    }
    v10 = _attribute_t::SetValue((_attribute_t *)this, &a2->OctetString);
  }
  v11 = v10;
  if ( v10 >= 0 )
    goto LABEL_13;
LABEL_15:
  _attribute_t::FreeAll((_attribute_t *)this);
  do
  {
    *p_Char++ = 0;
    --v6;
  }
  while ( v6 );
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180006274  push    rbx
0x180006276  push    rbp
0x180006277  push    rsi
0x180006278  push    rdi
0x180006279  push    r14
0x18000627b  sub     rsp, 20h
0x18000627f  mov     rdi, rdx
0x180006282  mov     rbx, rcx
0x180006285  test    rdx, rdx
0x180006288  jnz     short loc_180006294
0x18000628a  mov     eax, 80070057h
0x18000628f  jmp     loc_180006390
0x180006294  cmp     rbx, rdi
0x180006297  jz      loc_18000638E
0x18000629d  mov     esi, [rdx+8]
0x1800062a0  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x1800062a5  mov     ebp, 80h
0x1800062aa  lea     r14, [rbx+10h]
0x1800062ae  mov     ecx, ebp
0x1800062b0  mov     rax, r14
0x1800062b3  mov     byte ptr [rax], 0
0x1800062b6  inc     rax
0x1800062b9  sub     rcx, 1
0x1800062bd  jnz     short loc_1800062B3
0x1800062bf  cmp     esi, 0Ah
0x1800062c2  jnz     short loc_1800062D2
0x1800062c4  mov     rdx, [rdi+10h]; unsigned __int16 *
0x1800062c8  mov     rcx, rbx; this
0x1800062cb  call    ?SetValue@_attribute_t@@QEAAJPEBG@Z; _attribute_t::SetValue(ushort const *)
0x1800062d0  jmp     short loc_1800062E3
0x1800062d2  cmp     esi, 0Eh
0x1800062d5  jnz     short loc_1800062EF
0x1800062d7  lea     rdx, [rdi+10h]; struct tagOCTET_STRING *
0x1800062db  mov     rcx, rbx; this
0x1800062de  call    ?SetValue@_attribute_t@@QEAAJPEBUtagOCTET_STRING@@@Z; _attribute_t::SetValue(tagOCTET_STRING const *)
0x1800062e3  mov     esi, eax
0x1800062e5  test    eax, eax
0x1800062e7  js      loc_180006375
0x1800062ed  jmp     short loc_18000633B
0x1800062ef  movups  xmm0, xmmword ptr [rdi]
0x1800062f2  movups  xmmword ptr [rbx], xmm0
0x1800062f5  movups  xmm1, xmmword ptr [rdi+10h]
0x1800062f9  movups  xmmword ptr [rbx+10h], xmm1
0x1800062fd  movups  xmm0, xmmword ptr [rdi+20h]
0x180006301  movups  xmmword ptr [rbx+20h], xmm0
0x180006305  movups  xmm1, xmmword ptr [rdi+30h]
0x180006309  movups  xmmword ptr [rbx+30h], xmm1
0x18000630d  movups  xmm0, xmmword ptr [rdi+40h]
0x180006311  movups  xmmword ptr [rbx+40h], xmm0
0x180006315  movups  xmm1, xmmword ptr [rdi+50h]
0x180006319  movups  xmmword ptr [rbx+50h], xmm1
0x18000631d  movups  xmm0, xmmword ptr [rdi+60h]
0x180006321  movups  xmmword ptr [rbx+60h], xmm0
0x180006325  movups  xmm1, xmmword ptr [rdi+70h]
0x180006329  movups  xmmword ptr [rbx+70h], xmm1
0x18000632d  movups  xmm0, xmmword ptr [rdi+80h]
0x180006334  movups  xmmword ptr [rbx+80h], xmm0
0x18000633b  mov     qword ptr [rbx], 0
0x180006342  xor     ecx, ecx; pv
0x180006344  mov     rdi, [rdi]
0x180006347  call    cs:__imp_CoTaskMemFree
0x18000634e  nop     dword ptr [rax+rax+00h]
0x180006353  mov     qword ptr [rbx], 0
0x18000635a  test    rdi, rdi
0x18000635d  jz      short loc_18000638E
0x18000635f  mov     r8, rdi; unsigned __int16 *
0x180006362  mov     edx, 0FFFFh; unsigned __int64
0x180006367  mov     rcx, rbx; unsigned __int16 **
0x18000636a  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x18000636f  mov     esi, eax
0x180006371  test    eax, eax
0x180006373  jns     short loc_18000638E
0x180006375  mov     rcx, rbx; this
0x180006378  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000637d  mov     byte ptr [r14], 0
0x180006381  inc     r14
0x180006384  sub     rbp, 1
0x180006388  jnz     short loc_18000637D
0x18000638a  mov     eax, esi
0x18000638c  jmp     short loc_180006390
0x18000638e  xor     eax, eax
0x180006390  add     rsp, 20h
0x180006394  pop     r14
0x180006396  pop     rdi
0x180006397  pop     rsi
0x180006398  pop     rbp
0x180006399  pop     rbx
0x18000639a  retn
```
