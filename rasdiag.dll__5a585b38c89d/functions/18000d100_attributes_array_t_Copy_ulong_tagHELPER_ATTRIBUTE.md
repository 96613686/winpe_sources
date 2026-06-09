# _attributes_array_t::Copy(ulong,tagHELPER_ATTRIBUTE *)

- ea: `0x18000d100`
- end: `0x18000d2ef`
- name: `?Copy@_attributes_array_t@@QEAAJKPEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `495`
- prototype: `__int64 __fastcall(LPVOID *this, unsigned int, struct tagHELPER_ATTRIBUTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000d720`

## callees

- `0x180006274`
- `0x18000678c`
- `0x180007dc0`
- `0x180007e58`
- `0x180008084`
- `0x18000d100`
- `0x18000d9e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d228`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d2b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d228`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d2b9`

## pseudocode

```c
__int64 __fastcall _attributes_array_t::Copy(LPVOID *this, unsigned int a2, struct tagHELPER_ATTRIBUTE *a3)
{
  __int64 result; // rax
  __int64 v6; // r14
  char *v7; // rbx
  char *v8; // rbx
  _BYTE *v9; // r15
  __int64 v10; // rcx
  _BYTE *v11; // rax
  int v12; // eax
  int v13; // edi
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  const unsigned __int16 *pwszName; // rdi
  __int64 v23; // rax
  __int64 i; // rbx
  struct tagHELPER_ATTRIBUTE v25; // [rsp+20h] [rbp-69h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  result = _attributes_array_t::SetCount((_attributes_array_t *)this, a2);
  if ( (int)result < 0 )
    return result;
  v6 = 0;
  if ( !*(_DWORD *)this )
    return 0;
  while ( 1 )
  {
    v7 = (char *)this[1];
    v25.pwszName = 0;
    v25.type = AT_INVALID;
    _attribute_t::Copy(&v25, &a3[v6]);
    v8 = &v7[144 * v6];
    if ( v8 == (char *)&v25 )
    {
LABEL_20:
      v13 = 0;
      goto LABEL_21;
    }
    _attribute_t::FreeAll((_attribute_t *)v8);
    v9 = v8 + 16;
    v10 = 128;
    v11 = v8 + 16;
    do
    {
      *v11++ = 0;
      --v10;
    }
    while ( v10 );
    if ( v25.type == AT_STRING )
    {
      v12 = _attribute_t::SetValue((_attribute_t *)v8, v25.PWStr);
      goto LABEL_12;
    }
    if ( v25.type == AT_OCTET_STRING )
    {
      v12 = _attribute_t::SetValue((_attribute_t *)v8, &v25.OctetString);
LABEL_12:
      v13 = v12;
      if ( v12 < 0 )
        goto LABEL_17;
      goto LABEL_15;
    }
    v14 = *(_OWORD *)&v25.Boolean;
    *(_OWORD *)v8 = *(_OWORD *)&v25.pwszName;
    v15 = *((_OWORD *)&v25.OctetString + 1);
    *((_OWORD *)v8 + 1) = v14;
    v16 = *((_OWORD *)&v25.OctetString + 2);
    *((_OWORD *)v8 + 2) = v15;
    v17 = *((_OWORD *)&v25.OctetString + 3);
    *((_OWORD *)v8 + 3) = v16;
    v18 = *((_OWORD *)&v25.OctetString + 4);
    *((_OWORD *)v8 + 4) = v17;
    v19 = *((_OWORD *)&v25.OctetString + 5);
    *((_OWORD *)v8 + 5) = v18;
    v20 = *((_OWORD *)&v25.OctetString + 6);
    *((_OWORD *)v8 + 6) = v19;
    v21 = *((_OWORD *)&v25.OctetString + 7);
    *((_OWORD *)v8 + 7) = v20;
    *((_OWORD *)v8 + 8) = v21;
LABEL_15:
    pwszName = v25.pwszName;
    *(_QWORD *)v8 = 0;
    CoTaskMemFree(0);
    *(_QWORD *)v8 = 0;
    if ( !pwszName )
      goto LABEL_20;
    v13 = StringCchCopyWithAlloc((unsigned __int16 **)v8, 0xFFFFu, pwszName);
    if ( v13 >= 0 )
      goto LABEL_20;
LABEL_17:
    _attribute_t::FreeAll((_attribute_t *)v8);
    v23 = 128;
    do
    {
      *v9++ = 0;
      --v23;
    }
    while ( v23 );
LABEL_21:
    _attribute_t::FreeAll((_attribute_t *)&v25);
    if ( v13 < 0 )
      break;
    v6 = (unsigned int)(v6 + 1);
    if ( (unsigned int)v6 >= *(_DWORD *)this )
      return 0;
  }
  if ( this[1] )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)this; i = (unsigned int)(i + 1) )
      _attribute_t::FreeAll((_attribute_t *)((char *)this[1] + 144 * i));
  }
  CoTaskMemFree(this[1]);
  result = (unsigned int)v13;
  this[1] = 0;
  *(_DWORD *)this = 0;
  return result;
}

```

## disassembly

```asm
0x18000d100  push    rbp
0x18000d102  push    rbx
0x18000d103  push    rsi
0x18000d104  push    rdi
0x18000d105  push    r12
0x18000d107  push    r14
0x18000d109  push    r15
0x18000d10b  lea     rbp, [rsp-27h]
0x18000d110  sub     rsp, 0B0h
0x18000d117  mov     r12, r8
0x18000d11a  mov     rsi, rcx
0x18000d11d  test    edx, edx
0x18000d11f  jz      loc_18000D2D7
0x18000d125  test    r8, r8
0x18000d128  jz      loc_18000D2D7
0x18000d12e  call    ?SetCount@_attributes_array_t@@QEAAJK@Z; _attributes_array_t::SetCount(ulong)
0x18000d133  test    eax, eax
0x18000d135  js      loc_18000D2DC
0x18000d13b  xor     r14d, r14d
0x18000d13e  cmp     [rsi], r14d
0x18000d141  jbe     loc_18000D28D
0x18000d147  mov     rbx, [rsi+8]
0x18000d14b  lea     rdi, [r14+r14*8]
0x18000d14f  shl     rdi, 4
0x18000d153  lea     rcx, [rbp+57h+var_C0]; this
0x18000d157  mov     [rbp+57h+var_C0], 0
0x18000d15f  mov     dword ptr [rbp+57h+var_C0+8], 0
0x18000d166  lea     rdx, [rdi+r12]; struct tagHELPER_ATTRIBUTE *
0x18000d16a  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x18000d16f  lea     rax, [rbp+57h+var_C0]
0x18000d173  add     rbx, rdi
0x18000d176  cmp     rbx, rax
0x18000d179  jz      loc_18000D272
0x18000d17f  mov     rcx, rbx; this
0x18000d182  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000d187  lea     r15, [rbx+10h]
0x18000d18b  mov     ecx, 80h
0x18000d190  mov     rax, r15
0x18000d193  mov     byte ptr [rax], 0
0x18000d196  inc     rax
0x18000d199  sub     rcx, 1
0x18000d19d  jnz     short loc_18000D193
0x18000d19f  cmp     dword ptr [rbp+57h+var_C0+8], 0Ah
0x18000d1a3  jnz     short loc_18000D1B3
0x18000d1a5  mov     rdx, qword ptr [rbp+57h+var_B0.dwLength]; unsigned __int16 *
0x18000d1a9  mov     rcx, rbx; this
0x18000d1ac  call    ?SetValue@_attribute_t@@QEAAJPEBG@Z; _attribute_t::SetValue(ushort const *)
0x18000d1b1  jmp     short loc_18000D1C5
0x18000d1b3  cmp     dword ptr [rbp+57h+var_C0+8], 0Eh
0x18000d1b7  jnz     short loc_18000D1D1
0x18000d1b9  lea     rdx, [rbp+57h+var_B0]; struct tagOCTET_STRING *
0x18000d1bd  mov     rcx, rbx; this
0x18000d1c0  call    ?SetValue@_attribute_t@@QEAAJPEBUtagOCTET_STRING@@@Z; _attribute_t::SetValue(tagOCTET_STRING const *)
0x18000d1c5  mov     edi, eax
0x18000d1c7  test    eax, eax
0x18000d1c9  js      loc_18000D256
0x18000d1cf  jmp     short loc_18000D21B
0x18000d1d1  movups  xmm0, xmmword ptr [rbp+57h+var_C0]
0x18000d1d5  movups  xmm1, xmmword ptr [rbp+57h+var_B0.dwLength]
0x18000d1d9  movups  xmmword ptr [rbx], xmm0
0x18000d1dc  movups  xmm0, [rbp+57h+var_A0]
0x18000d1e0  movups  xmmword ptr [rbx+10h], xmm1
0x18000d1e4  movups  xmm1, [rbp+57h+var_90]
0x18000d1e8  movups  xmmword ptr [rbx+20h], xmm0
0x18000d1ec  movups  xmm0, [rbp+57h+var_80]
0x18000d1f0  movups  xmmword ptr [rbx+30h], xmm1
0x18000d1f4  movups  xmm1, [rbp+57h+var_70]
0x18000d1f8  movups  xmmword ptr [rbx+40h], xmm0
0x18000d1fc  movups  xmm0, [rbp+57h+var_60]
0x18000d200  movups  xmmword ptr [rbx+50h], xmm1
0x18000d204  movups  xmm1, [rbp+57h+var_50]
0x18000d208  movups  xmmword ptr [rbx+60h], xmm0
0x18000d20c  movups  xmm0, [rbp+57h+var_40]
0x18000d210  movups  xmmword ptr [rbx+70h], xmm1
0x18000d214  movups  xmmword ptr [rbx+80h], xmm0
0x18000d21b  mov     rdi, [rbp+57h+var_C0]
0x18000d21f  xor     ecx, ecx; pv
0x18000d221  mov     qword ptr [rbx], 0
0x18000d228  call    cs:__imp_CoTaskMemFree
0x18000d22f  nop     dword ptr [rax+rax+00h]
0x18000d234  mov     qword ptr [rbx], 0
0x18000d23b  test    rdi, rdi
0x18000d23e  jz      short loc_18000D272
0x18000d240  mov     r8, rdi; unsigned __int16 *
0x18000d243  mov     edx, 0FFFFh; unsigned __int64
0x18000d248  mov     rcx, rbx; unsigned __int16 **
0x18000d24b  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x18000d250  mov     edi, eax
0x18000d252  test    eax, eax
0x18000d254  jns     short loc_18000D272
0x18000d256  mov     rcx, rbx; this
0x18000d259  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000d25e  mov     eax, 80h
0x18000d263  mov     byte ptr [r15], 0
0x18000d267  inc     r15
0x18000d26a  sub     rax, 1
0x18000d26e  jnz     short loc_18000D263
0x18000d270  jmp     short loc_18000D274
0x18000d272  xor     edi, edi
0x18000d274  lea     rcx, [rbp+57h+var_C0]; this
0x18000d278  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000d27d  test    edi, edi
0x18000d27f  js      short loc_18000D291
0x18000d281  inc     r14d
0x18000d284  cmp     r14d, [rsi]
0x18000d287  jb      loc_18000D147
0x18000d28d  xor     eax, eax
0x18000d28f  jmp     short loc_18000D2DC
0x18000d291  cmp     qword ptr [rsi+8], 0
0x18000d296  jz      short loc_18000D2B5
0x18000d298  xor     ebx, ebx
0x18000d29a  cmp     [rsi], ebx
0x18000d29c  jbe     short loc_18000D2B5
0x18000d29e  lea     rcx, [rbx+rbx*8]
0x18000d2a2  shl     rcx, 4
0x18000d2a6  add     rcx, [rsi+8]; this
0x18000d2aa  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000d2af  inc     ebx
0x18000d2b1  cmp     ebx, [rsi]
0x18000d2b3  jb      short loc_18000D29E
0x18000d2b5  mov     rcx, [rsi+8]; pv
0x18000d2b9  call    cs:__imp_CoTaskMemFree
0x18000d2c0  nop     dword ptr [rax+rax+00h]
0x18000d2c5  mov     eax, edi
0x18000d2c7  mov     qword ptr [rsi+8], 0
0x18000d2cf  mov     dword ptr [rsi], 0
0x18000d2d5  jmp     short loc_18000D2DC
0x18000d2d7  mov     eax, 80070057h
0x18000d2dc  add     rsp, 0B0h
0x18000d2e3  pop     r15
0x18000d2e5  pop     r14
0x18000d2e7  pop     r12
0x18000d2e9  pop     rdi
0x18000d2ea  pop     rsi
0x18000d2eb  pop     rbx
0x18000d2ec  pop     rbp
0x18000d2ed  retn
```
