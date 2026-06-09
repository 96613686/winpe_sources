# _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)

- ea: `0x180006160`
- end: `0x180006333`
- name: `?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z`
- size: `467`
- prototype: `__int64 __fastcall(unsigned __int16 **this, const struct tagHELPER_ATTRIBUTE *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180006970`
- `0x18000a38c`
- `0x18000a8f0`

## callees

- `0x180006160`
- `0x180008998`
- `0x180008ac0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000619b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800061b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800061c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800061f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000620e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800062b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800062e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800062fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000630b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000619b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800061b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800061c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800061f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000620e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800062b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800062e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800062fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000630b`

## pseudocode

```c
__int64 __fastcall _attribute_t::Copy(struct tagHELPER_ATTRIBUTE *this, const struct tagHELPER_ATTRIBUTE *a2)
{
  ATTRIBUTE_TYPE type; // ebp
  __int64 v6; // r14
  LPVOID *p_PWStr; // rdi
  __int64 v8; // rcx
  unsigned __int16 **v9; // rax
  const unsigned __int16 *PWStr; // rbp
  int v11; // ebp
  const unsigned __int16 *pwszName; // rsi

  if ( !a2 )
    return 2147942487LL;
  if ( this == a2 )
    return 0;
  type = a2->type;
  if ( this->type == AT_STRING )
  {
    CoTaskMemFree(this->PWStr);
    this->Int64 = 0;
  }
  else if ( this->type == AT_OCTET_STRING )
  {
    CoTaskMemFree(this->OctetString.lpValue);
    this->OctetString.lpValue = 0;
    this->Boolean = 0;
  }
  CoTaskMemFree(this->pwszName);
  v6 = 128;
  this->pwszName = 0;
  p_PWStr = (LPVOID *)&this->PWStr;
  v8 = 128;
  v9 = &this->PWStr;
  do
  {
    *(_BYTE *)v9 = 0;
    v9 = (unsigned __int16 **)((char *)v9 + 1);
    --v8;
  }
  while ( v8 );
  if ( type == AT_STRING )
  {
    PWStr = a2->PWStr;
    if ( this->type == AT_STRING )
    {
      CoTaskMemFree(*p_PWStr);
      *p_PWStr = 0;
    }
    else if ( this->type == AT_OCTET_STRING )
    {
      CoTaskMemFree(this->OctetString.lpValue);
      this->OctetString.lpValue = 0;
      *(_DWORD *)p_PWStr = 0;
    }
    if ( !PWStr )
    {
LABEL_23:
      this->pwszName = 0;
      pwszName = a2->pwszName;
      CoTaskMemFree(0);
      this->pwszName = 0;
      if ( pwszName )
      {
        v11 = StringCchCopyWithAlloc(&this->pwszName, 0xFFFFu, pwszName);
        if ( v11 < 0 )
          goto LABEL_25;
      }
      return 0;
    }
    v11 = StringCchCopyWithAlloc(&this->PWStr, 0xFFFFu, PWStr);
    if ( v11 >= 0 )
    {
      this->type = AT_STRING;
      goto LABEL_23;
    }
    this->type = AT_INVALID;
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
      goto LABEL_23;
    }
    v11 = _attribute_t::SetValue((_attribute_t *)this, &a2->OctetString);
    if ( v11 >= 0 )
      goto LABEL_23;
  }
LABEL_25:
  if ( this->type == AT_STRING )
  {
    CoTaskMemFree(*p_PWStr);
    *p_PWStr = 0;
  }
  else if ( this->type == AT_OCTET_STRING )
  {
    CoTaskMemFree(this->OctetString.lpValue);
    this->OctetString.lpValue = 0;
    *(_DWORD *)p_PWStr = 0;
  }
  CoTaskMemFree(this->pwszName);
  this->pwszName = 0;
  do
  {
    *(_BYTE *)p_PWStr = 0;
    p_PWStr = (LPVOID *)((char *)p_PWStr + 1);
    --v6;
  }
  while ( v6 );
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180006160  push    rbx
0x180006162  push    rbp
0x180006163  push    rsi
0x180006164  push    rdi
0x180006165  push    r14
0x180006167  push    r15
0x180006169  sub     rsp, 28h
0x18000616d  xor     r15d, r15d
0x180006170  mov     rsi, rdx
0x180006173  mov     rbx, rcx
0x180006176  test    rdx, rdx
0x180006179  jnz     short loc_180006185
0x18000617b  mov     eax, 80070057h
0x180006180  jmp     loc_180006326
0x180006185  cmp     rbx, rsi
0x180006188  jz      loc_180006324
0x18000618e  cmp     dword ptr [rcx+8], 0Ah
0x180006192  mov     ebp, [rdx+8]
0x180006195  jnz     short loc_1800061A7
0x180006197  mov     rcx, [rcx+10h]; pv
0x18000619b  call    cs:__imp_CoTaskMemFree
0x1800061a1  mov     [rbx+10h], r15
0x1800061a5  jmp     short loc_1800061BF
0x1800061a7  cmp     dword ptr [rcx+8], 0Eh
0x1800061ab  jnz     short loc_1800061BF
0x1800061ad  mov     rcx, [rcx+18h]; pv
0x1800061b1  call    cs:__imp_CoTaskMemFree
0x1800061b7  mov     [rbx+18h], r15
0x1800061bb  mov     [rbx+10h], r15d
0x1800061bf  mov     rcx, [rbx]; pv
0x1800061c2  call    cs:__imp_CoTaskMemFree
0x1800061c8  mov     r14d, 80h
0x1800061ce  mov     [rbx], r15
0x1800061d1  lea     rdi, [rbx+10h]
0x1800061d5  mov     ecx, r14d
0x1800061d8  mov     rax, rdi
0x1800061db  mov     [rax], r15b
0x1800061de  inc     rax
0x1800061e1  sub     rcx, 1
0x1800061e5  jnz     short loc_1800061DB
0x1800061e7  cmp     ebp, 0Ah
0x1800061ea  jnz     short loc_18000624C
0x1800061ec  cmp     dword ptr [rbx+8], 0Ah
0x1800061f0  mov     rbp, [rsi+10h]
0x1800061f4  jnz     short loc_180006204
0x1800061f6  mov     rcx, [rdi]; pv
0x1800061f9  call    cs:__imp_CoTaskMemFree
0x1800061ff  mov     [rdi], r15
0x180006202  jmp     short loc_18000621B
0x180006204  cmp     dword ptr [rbx+8], 0Eh
0x180006208  jnz     short loc_18000621B
0x18000620a  mov     rcx, [rbx+18h]; pv
0x18000620e  call    cs:__imp_CoTaskMemFree
0x180006214  mov     [rbx+18h], r15
0x180006218  mov     [rdi], r15d
0x18000621b  test    rbp, rbp
0x18000621e  jz      loc_1800062B1
0x180006224  mov     r8, rbp; unsigned __int16 *
0x180006227  mov     edx, 0FFFFh; unsigned __int64
0x18000622c  mov     rcx, rdi; unsigned __int16 **
0x18000622f  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x180006234  mov     ebp, eax
0x180006236  test    eax, eax
0x180006238  js      short loc_180006243
0x18000623a  mov     dword ptr [rbx+8], 0Ah
0x180006241  jmp     short loc_1800062B1
0x180006243  mov     [rbx+8], r15d
0x180006247  jmp     loc_1800062DD
0x18000624c  cmp     ebp, 0Eh
0x18000624f  jnz     short loc_180006265
0x180006251  lea     rdx, [rsi+10h]; struct tagOCTET_STRING *
0x180006255  mov     rcx, rbx; this
0x180006258  call    ?SetValue@_attribute_t@@QEAAJPEBUtagOCTET_STRING@@@Z; _attribute_t::SetValue(tagOCTET_STRING const *)
0x18000625d  mov     ebp, eax
0x18000625f  test    eax, eax
0x180006261  js      short loc_1800062DD
0x180006263  jmp     short loc_1800062B1
0x180006265  movups  xmm0, xmmword ptr [rsi]
0x180006268  movups  xmmword ptr [rbx], xmm0
0x18000626b  movups  xmm1, xmmword ptr [rsi+10h]
0x18000626f  movups  xmmword ptr [rbx+10h], xmm1
0x180006273  movups  xmm0, xmmword ptr [rsi+20h]
0x180006277  movups  xmmword ptr [rbx+20h], xmm0
0x18000627b  movups  xmm1, xmmword ptr [rsi+30h]
0x18000627f  movups  xmmword ptr [rbx+30h], xmm1
0x180006283  movups  xmm0, xmmword ptr [rsi+40h]
0x180006287  movups  xmmword ptr [rbx+40h], xmm0
0x18000628b  movups  xmm1, xmmword ptr [rsi+50h]
0x18000628f  movups  xmmword ptr [rbx+50h], xmm1
0x180006293  movups  xmm0, xmmword ptr [rsi+60h]
0x180006297  movups  xmmword ptr [rbx+60h], xmm0
0x18000629b  movups  xmm1, xmmword ptr [rsi+70h]
0x18000629f  movups  xmmword ptr [rbx+70h], xmm1
0x1800062a3  movups  xmm0, xmmword ptr [rsi+80h]
0x1800062aa  movups  xmmword ptr [rbx+80h], xmm0
0x1800062b1  mov     [rbx], r15
0x1800062b4  xor     ecx, ecx; pv
0x1800062b6  mov     rsi, [rsi]
0x1800062b9  call    cs:__imp_CoTaskMemFree
0x1800062bf  mov     [rbx], r15
0x1800062c2  test    rsi, rsi
0x1800062c5  jz      short loc_180006324
0x1800062c7  mov     r8, rsi; unsigned __int16 *
0x1800062ca  mov     edx, 0FFFFh; unsigned __int64
0x1800062cf  mov     rcx, rbx; unsigned __int16 **
0x1800062d2  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x1800062d7  mov     ebp, eax
0x1800062d9  test    eax, eax
0x1800062db  jns     short loc_180006324
0x1800062dd  cmp     dword ptr [rbx+8], 0Ah
0x1800062e1  jnz     short loc_1800062F1
0x1800062e3  mov     rcx, [rdi]; pv
0x1800062e6  call    cs:__imp_CoTaskMemFree
0x1800062ec  mov     [rdi], r15
0x1800062ef  jmp     short loc_180006308
0x1800062f1  cmp     dword ptr [rbx+8], 0Eh
0x1800062f5  jnz     short loc_180006308
0x1800062f7  mov     rcx, [rbx+18h]; pv
0x1800062fb  call    cs:__imp_CoTaskMemFree
0x180006301  mov     [rbx+18h], r15
0x180006305  mov     [rdi], r15d
0x180006308  mov     rcx, [rbx]; pv
0x18000630b  call    cs:__imp_CoTaskMemFree
0x180006311  mov     [rbx], r15
0x180006314  mov     [rdi], r15b
0x180006317  inc     rdi
0x18000631a  sub     r14, 1
0x18000631e  jnz     short loc_180006314
0x180006320  mov     eax, ebp
0x180006322  jmp     short loc_180006326
0x180006324  xor     eax, eax
0x180006326  add     rsp, 28h
0x18000632a  pop     r15
0x18000632c  pop     r14
0x18000632e  pop     rdi
0x18000632f  pop     rsi
0x180006330  pop     rbp
0x180006331  pop     rbx
0x180006332  retn
```
