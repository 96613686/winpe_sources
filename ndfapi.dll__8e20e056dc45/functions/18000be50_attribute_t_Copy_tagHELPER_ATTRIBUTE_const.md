# _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)

- ea: `0x18000be50`
- end: `0x18000c099`
- name: `?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z`
- size: `585`
- prototype: `__int64 __fastcall(struct tagHELPER_ATTRIBUTE *this, const struct tagHELPER_ATTRIBUTE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x18000c0a0`

## callees

- `0x1800026a6`
- `0x18000be50`
- `0x18000f800`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000bf85`
- `ole32!CoTaskMemAlloc` at `0x18000bf85`
- `ole32!CoTaskMemFree` at `0x18000be8d`
- `ole32!CoTaskMemFree` at `0x18000bea3`
- `ole32!CoTaskMemFree` at `0x18000beb4`
- `ole32!CoTaskMemFree` at `0x18000beeb`
- `ole32!CoTaskMemFree` at `0x18000bf00`
- `ole32!CoTaskMemFree` at `0x18000bf49`
- `ole32!CoTaskMemFree` at `0x18000bf5e`
- `ole32!CoTaskMemFree` at `0x18000c022`
- `ole32!CoTaskMemFree` at `0x18000c04a`
- `ole32!CoTaskMemFree` at `0x18000c05f`
- `ole32!CoTaskMemFree` at `0x18000c06f`
- `ole32!CoTaskMemFree` at `0x18000be8d`
- `ole32!CoTaskMemFree` at `0x18000bea3`
- `ole32!CoTaskMemFree` at `0x18000beb4`
- `ole32!CoTaskMemFree` at `0x18000beeb`
- `ole32!CoTaskMemFree` at `0x18000bf00`
- `ole32!CoTaskMemFree` at `0x18000bf49`
- `ole32!CoTaskMemFree` at `0x18000bf5e`
- `ole32!CoTaskMemFree` at `0x18000c022`
- `ole32!CoTaskMemFree` at `0x18000c04a`
- `ole32!CoTaskMemFree` at `0x18000c05f`
- `ole32!CoTaskMemFree` at `0x18000c06f`

## pseudocode

```c
__int64 __fastcall _attribute_t::Copy(struct tagHELPER_ATTRIBUTE *this, const struct tagHELPER_ATTRIBUTE *a2)
{
  ATTRIBUTE_TYPE type; // esi
  __int64 v6; // r15
  LPVOID *p_PWStr; // rdi
  __int64 v8; // rcx
  unsigned __int16 **v9; // rax
  const unsigned __int16 *PWStr; // rsi
  int v11; // esi
  LONGLONG *p_Int64; // rsi
  SIZE_T v13; // rbp
  unsigned __int16 *v14; // rax
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
  if ( type != AT_STRING )
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
      goto LABEL_32;
    }
    p_Int64 = &a2->Int64;
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
    if ( a2 != (const struct tagHELPER_ATTRIBUTE *)-16LL )
    {
      if ( this == (struct tagHELPER_ATTRIBUTE *)-16LL || *(_DWORD *)p_Int64 >= 0xFFFFu )
      {
        v11 = -2147024809;
      }
      else
      {
        v13 = *(unsigned int *)p_Int64;
        v14 = (unsigned __int16 *)CoTaskMemAlloc(v13);
        this->OctetString.lpValue = (BYTE *)v14;
        if ( v14 )
        {
          memcpy_0(v14, a2->OctetString.lpValue, v13);
          *(_DWORD *)p_PWStr = *(_DWORD *)p_Int64;
          this->type = AT_OCTET_STRING;
          goto LABEL_32;
        }
        v11 = -2147024882;
      }
      goto LABEL_28;
    }
LABEL_32:
    this->pwszName = 0;
    pwszName = a2->pwszName;
    CoTaskMemFree(0);
    this->pwszName = 0;
    if ( pwszName )
    {
      v11 = StringCopyWithAlloc(&this->pwszName, pwszName);
      if ( v11 < 0 )
        goto LABEL_34;
    }
    return 0;
  }
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
    goto LABEL_32;
  v11 = StringCopyWithAlloc(&this->PWStr, PWStr);
  if ( v11 >= 0 )
  {
    this->type = AT_STRING;
    goto LABEL_32;
  }
LABEL_28:
  this->type = AT_INVALID;
LABEL_34:
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
0x18000be50  push    rbx
0x18000be52  push    rbp
0x18000be53  push    rsi
0x18000be54  push    rdi
0x18000be55  push    r12
0x18000be57  push    r14
0x18000be59  push    r15
0x18000be5b  sub     rsp, 20h
0x18000be5f  xor     r12d, r12d
0x18000be62  mov     r14, rdx
0x18000be65  mov     rbx, rcx
0x18000be68  test    rdx, rdx
0x18000be6b  jnz     short loc_18000BE77
0x18000be6d  mov     eax, 80070057h
0x18000be72  jmp     loc_18000C08A
0x18000be77  cmp     rbx, r14
0x18000be7a  jz      loc_18000C088
0x18000be80  cmp     dword ptr [rcx+8], 0Ah
0x18000be84  mov     esi, [rdx+8]
0x18000be87  jnz     short loc_18000BE99
0x18000be89  mov     rcx, [rcx+10h]; pv
0x18000be8d  call    cs:__imp_CoTaskMemFree
0x18000be93  mov     [rbx+10h], r12
0x18000be97  jmp     short loc_18000BEB1
0x18000be99  cmp     dword ptr [rcx+8], 0Eh
0x18000be9d  jnz     short loc_18000BEB1
0x18000be9f  mov     rcx, [rcx+18h]; pv
0x18000bea3  call    cs:__imp_CoTaskMemFree
0x18000bea9  mov     [rbx+18h], r12
0x18000bead  mov     [rbx+10h], r12d
0x18000beb1  mov     rcx, [rbx]; pv
0x18000beb4  call    cs:__imp_CoTaskMemFree
0x18000beba  mov     r15d, 80h
0x18000bec0  mov     [rbx], r12
0x18000bec3  lea     rdi, [rbx+10h]
0x18000bec7  mov     ecx, r15d
0x18000beca  mov     rax, rdi
0x18000becd  mov     [rax], r12b
0x18000bed0  inc     rax
0x18000bed3  sub     rcx, 1
0x18000bed7  jnz     short loc_18000BECD
0x18000bed9  cmp     esi, 0Ah
0x18000bedc  jnz     short loc_18000BF33
0x18000bede  cmp     dword ptr [rbx+8], 0Ah
0x18000bee2  mov     rsi, [r14+10h]
0x18000bee6  jnz     short loc_18000BEF6
0x18000bee8  mov     rcx, [rdi]; pv
0x18000beeb  call    cs:__imp_CoTaskMemFree
0x18000bef1  mov     [rdi], r12
0x18000bef4  jmp     short loc_18000BF0D
0x18000bef6  cmp     dword ptr [rbx+8], 0Eh
0x18000befa  jnz     short loc_18000BF0D
0x18000befc  mov     rcx, [rbx+18h]; pv
0x18000bf00  call    cs:__imp_CoTaskMemFree
0x18000bf06  mov     [rbx+18h], r12
0x18000bf0a  mov     [rdi], r12d
0x18000bf0d  test    rsi, rsi
0x18000bf10  jz      loc_18000C01A
0x18000bf16  mov     rdx, rsi; unsigned __int16 *
0x18000bf19  mov     rcx, rdi; unsigned __int16 **
0x18000bf1c  call    ?StringCopyWithAlloc@@YAJPEAPEAGPEBG@Z; StringCopyWithAlloc(ushort * *,ushort const *)
0x18000bf21  mov     esi, eax
0x18000bf23  test    eax, eax
0x18000bf25  js      short loc_18000BF99
0x18000bf27  mov     dword ptr [rbx+8], 0Ah
0x18000bf2e  jmp     loc_18000C01A
0x18000bf33  cmp     esi, 0Eh
0x18000bf36  jnz     loc_18000BFC5
0x18000bf3c  cmp     dword ptr [rbx+8], 0Ah
0x18000bf40  lea     rsi, [r14+10h]
0x18000bf44  jnz     short loc_18000BF54
0x18000bf46  mov     rcx, [rdi]; pv
0x18000bf49  call    cs:__imp_CoTaskMemFree
0x18000bf4f  mov     [rdi], r12
0x18000bf52  jmp     short loc_18000BF6B
0x18000bf54  cmp     dword ptr [rbx+8], 0Eh
0x18000bf58  jnz     short loc_18000BF6B
0x18000bf5a  mov     rcx, [rbx+18h]; pv
0x18000bf5e  call    cs:__imp_CoTaskMemFree
0x18000bf64  mov     [rbx+18h], r12
0x18000bf68  mov     [rdi], r12d
0x18000bf6b  test    rsi, rsi
0x18000bf6e  jz      loc_18000C01A
0x18000bf74  test    rdi, rdi
0x18000bf77  jz      short loc_18000BFBE
0x18000bf79  cmp     dword ptr [rsi], 0FFFFh
0x18000bf7f  jnb     short loc_18000BFBE
0x18000bf81  mov     ebp, [rsi]
0x18000bf83  mov     ecx, ebp; cb
0x18000bf85  call    cs:__imp_CoTaskMemAlloc
0x18000bf8b  mov     [rdi+8], rax
0x18000bf8f  test    rax, rax
0x18000bf92  jnz     short loc_18000BFA2
0x18000bf94  mov     esi, 8007000Eh
0x18000bf99  mov     [rbx+8], r12d
0x18000bf9d  jmp     loc_18000C041
0x18000bfa2  mov     rdx, [rsi+8]; Src
0x18000bfa6  mov     r8, rbp; Size
0x18000bfa9  mov     rcx, rax; void *
0x18000bfac  call    memcpy_0
0x18000bfb1  mov     eax, [rsi]
0x18000bfb3  mov     [rdi], eax
0x18000bfb5  mov     dword ptr [rbx+8], 0Eh
0x18000bfbc  jmp     short loc_18000C01A
0x18000bfbe  mov     esi, 80070057h
0x18000bfc3  jmp     short loc_18000BF99
0x18000bfc5  movups  xmm0, xmmword ptr [r14]
0x18000bfc9  movups  xmmword ptr [rbx], xmm0
0x18000bfcc  movups  xmm1, xmmword ptr [r14+10h]
0x18000bfd1  movups  xmmword ptr [rbx+10h], xmm1
0x18000bfd5  movups  xmm0, xmmword ptr [r14+20h]
0x18000bfda  movups  xmmword ptr [rbx+20h], xmm0
0x18000bfde  movups  xmm1, xmmword ptr [r14+30h]
0x18000bfe3  movups  xmmword ptr [rbx+30h], xmm1
0x18000bfe7  movups  xmm0, xmmword ptr [r14+40h]
0x18000bfec  movups  xmmword ptr [rbx+40h], xmm0
0x18000bff0  movups  xmm1, xmmword ptr [r14+50h]
0x18000bff5  movups  xmmword ptr [rbx+50h], xmm1
0x18000bff9  movups  xmm0, xmmword ptr [r14+60h]
0x18000bffe  movups  xmmword ptr [rbx+60h], xmm0
0x18000c002  movups  xmm1, xmmword ptr [r14+70h]
0x18000c007  movups  xmmword ptr [rbx+70h], xmm1
0x18000c00b  movups  xmm0, xmmword ptr [r14+80h]
0x18000c013  movups  xmmword ptr [rbx+80h], xmm0
0x18000c01a  mov     [rbx], r12
0x18000c01d  xor     ecx, ecx; pv
0x18000c01f  mov     rsi, [r14]
0x18000c022  call    cs:__imp_CoTaskMemFree
0x18000c028  mov     [rbx], r12
0x18000c02b  test    rsi, rsi
0x18000c02e  jz      short loc_18000C088
0x18000c030  mov     rdx, rsi; unsigned __int16 *
0x18000c033  mov     rcx, rbx; unsigned __int16 **
0x18000c036  call    ?StringCopyWithAlloc@@YAJPEAPEAGPEBG@Z; StringCopyWithAlloc(ushort * *,ushort const *)
0x18000c03b  mov     esi, eax
0x18000c03d  test    eax, eax
0x18000c03f  jns     short loc_18000C088
0x18000c041  cmp     dword ptr [rbx+8], 0Ah
0x18000c045  jnz     short loc_18000C055
0x18000c047  mov     rcx, [rdi]; pv
0x18000c04a  call    cs:__imp_CoTaskMemFree
0x18000c050  mov     [rdi], r12
0x18000c053  jmp     short loc_18000C06C
0x18000c055  cmp     dword ptr [rbx+8], 0Eh
0x18000c059  jnz     short loc_18000C06C
0x18000c05b  mov     rcx, [rbx+18h]; pv
0x18000c05f  call    cs:__imp_CoTaskMemFree
0x18000c065  mov     [rbx+18h], r12
0x18000c069  mov     [rdi], r12d
0x18000c06c  mov     rcx, [rbx]; pv
0x18000c06f  call    cs:__imp_CoTaskMemFree
0x18000c075  mov     [rbx], r12
0x18000c078  mov     [rdi], r12b
0x18000c07b  inc     rdi
0x18000c07e  sub     r15, 1
0x18000c082  jnz     short loc_18000C078
0x18000c084  mov     eax, esi
0x18000c086  jmp     short loc_18000C08A
0x18000c088  xor     eax, eax
0x18000c08a  add     rsp, 20h
0x18000c08e  pop     r15
0x18000c090  pop     r14
0x18000c092  pop     r12
0x18000c094  pop     rdi
0x18000c095  pop     rsi
0x18000c096  pop     rbp
0x18000c097  pop     rbx
0x18000c098  retn
```
