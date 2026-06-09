# _attributes_array_t::Copy(ulong,tagHELPER_ATTRIBUTE *)

- ea: `0x18000c0a0`
- end: `0x18000c43a`
- name: `?Copy@_attributes_array_t@@QEAAJKPEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `922`
- prototype: `__int64 __fastcall(_attributes_array_t *__hidden this, unsigned int, struct tagHELPER_ATTRIBUTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x18000a9e0`

## callees

- `0x1800026a6`
- `0x1800089b4`
- `0x18000be50`
- `0x18000c0a0`
- `0x18000f800`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000c0fa`
- `ole32!CoTaskMemAlloc` at `0x18000c2b0`
- `ole32!CoTaskMemAlloc` at `0x18000c0fa`
- `ole32!CoTaskMemAlloc` at `0x18000c2b0`
- `ole32!CoTaskMemFree` at `0x18000c1a5`
- `ole32!CoTaskMemFree` at `0x18000c1bf`
- `ole32!CoTaskMemFree` at `0x18000c1d7`
- `ole32!CoTaskMemFree` at `0x18000c20b`
- `ole32!CoTaskMemFree` at `0x18000c224`
- `ole32!CoTaskMemFree` at `0x18000c271`
- `ole32!CoTaskMemFree` at `0x18000c28a`
- `ole32!CoTaskMemFree` at `0x18000c34a`
- `ole32!CoTaskMemFree` at `0x18000c37a`
- `ole32!CoTaskMemFree` at `0x18000c393`
- `ole32!CoTaskMemFree` at `0x18000c3aa`
- `ole32!CoTaskMemFree` at `0x18000c3e6`
- `ole32!CoTaskMemFree` at `0x18000c3f0`
- `ole32!CoTaskMemFree` at `0x18000c1a5`
- `ole32!CoTaskMemFree` at `0x18000c1bf`
- `ole32!CoTaskMemFree` at `0x18000c1d7`
- `ole32!CoTaskMemFree` at `0x18000c20b`
- `ole32!CoTaskMemFree` at `0x18000c224`
- `ole32!CoTaskMemFree` at `0x18000c271`
- `ole32!CoTaskMemFree` at `0x18000c28a`
- `ole32!CoTaskMemFree` at `0x18000c34a`
- `ole32!CoTaskMemFree` at `0x18000c37a`
- `ole32!CoTaskMemFree` at `0x18000c393`
- `ole32!CoTaskMemFree` at `0x18000c3aa`
- `ole32!CoTaskMemFree` at `0x18000c3e6`
- `ole32!CoTaskMemFree` at `0x18000c3f0`

## pseudocode

```c
__int64 __fastcall _attributes_array_t::Copy(
        _attributes_array_t *this,
        unsigned int a2,
        struct tagHELPER_ATTRIBUTE *a3)
{
  __int64 v3; // rdi
  struct tagHELPER_ATTRIBUTE *v4; // rsi
  __int64 v7; // rbx
  _BYTE *v8; // rax
  __int64 v10; // r13
  __int64 v11; // rbx
  BYTE *lpValue; // rcx
  const unsigned __int16 *PWStr; // rsi
  __int64 v14; // rbx
  ATTRIBUTE_TYPE type; // r14d
  LPVOID *v16; // rdi
  _BYTE *v17; // rax
  __int64 v18; // rcx
  int v19; // esi
  void *v20; // rax
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int64 v29; // rax
  unsigned __int16 *pv; // [rsp+20h] [rbp-79h]
  LONGLONG Int64; // [rsp+28h] [rbp-71h]
  struct tagHELPER_ATTRIBUTE v32; // [rsp+30h] [rbp-69h] BYREF
  ATTRIBUTE_TYPE v33; // [rsp+108h] [rbp+6Fh]
  BYTE *Src; // [rsp+118h] [rbp+7Fh]

  v3 = a2;
  v4 = a3;
  if ( a2 && a3 )
  {
    if ( a2 > 0x1C71C71 )
      return (unsigned int)-2147024362;
    _attributes_array_t::FreeAll(this);
    v7 = 144 * v3;
    v8 = CoTaskMemAlloc(144 * v3);
    *((_QWORD *)this + 1) = v8;
    if ( !v8 )
      return (unsigned int)-2147024882;
    for ( ; v7; --v7 )
      *v8++ = 0;
    v10 = 0;
    *(_DWORD *)this = v3;
    if ( !(_DWORD)v3 )
      return 0;
    while ( 1 )
    {
      v11 = *((_QWORD *)this + 1);
      v32.pwszName = 0;
      v32.type = AT_INVALID;
      _attribute_t::Copy(&v32, &v4[v10]);
      lpValue = v32.OctetString.lpValue;
      PWStr = v32.PWStr;
      v14 = 144 * v10 + v11;
      type = v32.type;
      Src = v32.OctetString.lpValue;
      Int64 = v32.Int64;
      v33 = v32.type;
      pv = v32.pwszName;
      if ( (struct tagHELPER_ATTRIBUTE *)v14 == &v32 )
        goto LABEL_49;
      if ( *(_DWORD *)(v14 + 8) == 10 )
      {
        CoTaskMemFree(*(LPVOID *)(v14 + 16));
        *(_QWORD *)(v14 + 16) = 0;
      }
      else if ( *(_DWORD *)(v14 + 8) == 14 )
      {
        CoTaskMemFree(*(LPVOID *)(v14 + 24));
        *(_QWORD *)(v14 + 24) = 0;
        *(_DWORD *)(v14 + 16) = 0;
      }
      CoTaskMemFree(*(LPVOID *)v14);
      v16 = (LPVOID *)(v14 + 16);
      *(_QWORD *)v14 = 0;
      v17 = (_BYTE *)(v14 + 16);
      v18 = 128;
      do
      {
        *v17++ = 0;
        --v18;
      }
      while ( v18 );
      if ( type == AT_STRING )
      {
        if ( *(_DWORD *)(v14 + 8) == 10 )
        {
          CoTaskMemFree(*v16);
          *v16 = 0;
        }
        else if ( *(_DWORD *)(v14 + 8) == 14 )
        {
          CoTaskMemFree(*(LPVOID *)(v14 + 24));
          *(_QWORD *)(v14 + 24) = 0;
          *(_DWORD *)v16 = 0;
        }
        if ( PWStr )
        {
          v19 = StringCopyWithAlloc((unsigned __int16 **)(v14 + 16), PWStr);
          if ( v19 < 0 )
            goto LABEL_35;
          *(_DWORD *)(v14 + 8) = 10;
        }
      }
      else if ( type == AT_OCTET_STRING )
      {
        if ( *(_DWORD *)(v14 + 8) == 10 )
        {
          CoTaskMemFree(*v16);
          *v16 = 0;
        }
        else if ( *(_DWORD *)(v14 + 8) == 14 )
        {
          CoTaskMemFree(*(LPVOID *)(v14 + 24));
          *(_QWORD *)(v14 + 24) = 0;
          *(_DWORD *)v16 = 0;
        }
        if ( v14 == -16 || (unsigned int)PWStr >= 0xFFFF )
        {
          v19 = -2147024809;
          goto LABEL_35;
        }
        v20 = CoTaskMemAlloc((unsigned int)PWStr);
        *(_QWORD *)(v14 + 24) = v20;
        if ( !v20 )
        {
          type = v33;
          v19 = -2147024882;
LABEL_35:
          *(_DWORD *)(v14 + 8) = 0;
          goto LABEL_41;
        }
        memcpy_0(v20, Src, (unsigned int)PWStr);
        type = v33;
        *(_DWORD *)v16 = (_DWORD)PWStr;
        *(_DWORD *)(v14 + 8) = 14;
      }
      else
      {
        v21 = *(_OWORD *)&v32.Boolean;
        *(_OWORD *)v14 = *(_OWORD *)&v32.pwszName;
        v22 = *((_OWORD *)&v32.OctetString + 1);
        *(_OWORD *)(v14 + 16) = v21;
        v23 = *((_OWORD *)&v32.OctetString + 2);
        *(_OWORD *)(v14 + 32) = v22;
        v24 = *((_OWORD *)&v32.OctetString + 3);
        *(_OWORD *)(v14 + 48) = v23;
        v25 = *((_OWORD *)&v32.OctetString + 4);
        *(_OWORD *)(v14 + 64) = v24;
        v26 = *((_OWORD *)&v32.OctetString + 5);
        *(_OWORD *)(v14 + 80) = v25;
        v27 = *((_OWORD *)&v32.OctetString + 6);
        *(_OWORD *)(v14 + 96) = v26;
        v28 = *((_OWORD *)&v32.OctetString + 7);
        *(_OWORD *)(v14 + 112) = v27;
        *(_OWORD *)(v14 + 128) = v28;
      }
      *(_QWORD *)v14 = 0;
      CoTaskMemFree(0);
      *(_QWORD *)v14 = 0;
      if ( !pv || (v19 = StringCopyWithAlloc((unsigned __int16 **)v14, pv), v19 >= 0) )
      {
        lpValue = Src;
LABEL_49:
        v19 = 0;
        goto LABEL_50;
      }
LABEL_41:
      if ( *(_DWORD *)(v14 + 8) == 10 )
      {
        CoTaskMemFree(*v16);
        *v16 = 0;
      }
      else if ( *(_DWORD *)(v14 + 8) == 14 )
      {
        CoTaskMemFree(*(LPVOID *)(v14 + 24));
        *(_QWORD *)(v14 + 24) = 0;
        *(_DWORD *)v16 = 0;
      }
      CoTaskMemFree(*(LPVOID *)v14);
      v29 = 128;
      *(_QWORD *)v14 = 0;
      do
      {
        *(_BYTE *)v16 = 0;
        v16 = (LPVOID *)((char *)v16 + 1);
        --v29;
      }
      while ( v29 );
      lpValue = Src;
LABEL_50:
      if ( type == AT_STRING )
      {
        lpValue = (BYTE *)Int64;
      }
      else if ( type != AT_OCTET_STRING )
      {
        goto LABEL_54;
      }
      CoTaskMemFree(lpValue);
LABEL_54:
      CoTaskMemFree(pv);
      if ( v19 < 0 )
      {
        _attributes_array_t::FreeAll(this);
        return (unsigned int)v19;
      }
      v4 = a3;
      v10 = (unsigned int)(v10 + 1);
      if ( (unsigned int)v10 >= *(_DWORD *)this )
        return 0;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000c0a0  mov     [rsp-8+arg_0], rbx
0x18000c0a5  mov     [rsp-8+arg_10], r8
0x18000c0aa  push    rbp
0x18000c0ab  push    rsi
0x18000c0ac  push    rdi
0x18000c0ad  push    r12
0x18000c0af  push    r13
0x18000c0b1  push    r14
0x18000c0b3  push    r15
0x18000c0b5  lea     rbp, [rsp-27h]
0x18000c0ba  sub     rsp, 0C0h
0x18000c0c1  mov     edi, edx
0x18000c0c3  mov     rsi, r8
0x18000c0c6  mov     r15, rcx
0x18000c0c9  test    edx, edx
0x18000c0cb  jz      loc_18000C41A
0x18000c0d1  test    r8, r8
0x18000c0d4  jz      loc_18000C41A
0x18000c0da  cmp     edi, 1C71C71h
0x18000c0e0  jbe     short loc_18000C0EA
0x18000c0e2  mov     r12d, 80070216h
0x18000c0e8  jmp     short loc_18000C10F
0x18000c0ea  call    ?FreeAll@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeAll(void)
0x18000c0ef  lea     rbx, [rdi+rdi*8]
0x18000c0f3  shl     rbx, 4
0x18000c0f7  mov     rcx, rbx; cb
0x18000c0fa  call    cs:__imp_CoTaskMemAlloc
0x18000c100  mov     [r15+8], rax
0x18000c104  test    rax, rax
0x18000c107  jnz     short loc_18000C117
0x18000c109  mov     r12d, 8007000Eh
0x18000c10f  mov     eax, r12d
0x18000c112  jmp     loc_18000C41F
0x18000c117  test    rbx, rbx
0x18000c11a  jz      short loc_18000C128
0x18000c11c  mov     byte ptr [rax], 0
0x18000c11f  inc     rax
0x18000c122  sub     rbx, 1
0x18000c126  jnz     short loc_18000C11C
0x18000c128  xor     r13d, r13d
0x18000c12b  mov     [r15], edi
0x18000c12e  test    edi, edi
0x18000c130  jz      loc_18000C40A
0x18000c136  mov     r12d, 8007000Eh
0x18000c13c  mov     rbx, [r15+8]
0x18000c140  lea     rdi, ds:0[r13*8]
0x18000c148  add     rdi, r13
0x18000c14b  mov     [rbp+57h+var_C0], 0
0x18000c153  shl     rdi, 4
0x18000c157  lea     rcx, [rbp+57h+var_C0]; this
0x18000c15b  mov     dword ptr [rbp+57h+var_C0+8], 0
0x18000c162  lea     rdx, [rdi+rsi]; struct tagHELPER_ATTRIBUTE *
0x18000c166  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x18000c16b  mov     rcx, [rbp+57h+cb+8]
0x18000c16f  lea     rdx, [rbp+57h+var_C0]
0x18000c173  mov     rsi, [rbp+57h+cb]
0x18000c177  add     rbx, rdi
0x18000c17a  mov     rax, [rbp+57h+var_C0]
0x18000c17e  mov     r14d, dword ptr [rbp+57h+var_C0+8]
0x18000c182  mov     [rbp+57h+Src], rcx
0x18000c186  mov     [rbp+57h+var_C8], rsi
0x18000c18a  mov     [rbp+57h+arg_8], r14d
0x18000c18e  mov     [rbp+57h+pv], rax
0x18000c192  cmp     rbx, rdx
0x18000c195  jz      loc_18000C3D2
0x18000c19b  cmp     dword ptr [rbx+8], 0Ah
0x18000c19f  jnz     short loc_18000C1B5
0x18000c1a1  mov     rcx, [rbx+10h]; pv
0x18000c1a5  call    cs:__imp_CoTaskMemFree
0x18000c1ab  mov     qword ptr [rbx+10h], 0
0x18000c1b3  jmp     short loc_18000C1D4
0x18000c1b5  cmp     dword ptr [rbx+8], 0Eh
0x18000c1b9  jnz     short loc_18000C1D4
0x18000c1bb  mov     rcx, [rbx+18h]; pv
0x18000c1bf  call    cs:__imp_CoTaskMemFree
0x18000c1c5  mov     qword ptr [rbx+18h], 0
0x18000c1cd  mov     dword ptr [rbx+10h], 0
0x18000c1d4  mov     rcx, [rbx]; pv
0x18000c1d7  call    cs:__imp_CoTaskMemFree
0x18000c1dd  lea     rdi, [rbx+10h]
0x18000c1e1  mov     qword ptr [rbx], 0
0x18000c1e8  mov     rax, rdi
0x18000c1eb  mov     ecx, 80h
0x18000c1f0  mov     byte ptr [rax], 0
0x18000c1f3  inc     rax
0x18000c1f6  sub     rcx, 1
0x18000c1fa  jnz     short loc_18000C1F0
0x18000c1fc  cmp     r14d, 0Ah
0x18000c200  jnz     short loc_18000C25E
0x18000c202  cmp     [rbx+8], r14d
0x18000c206  jnz     short loc_18000C21A
0x18000c208  mov     rcx, [rdi]; pv
0x18000c20b  call    cs:__imp_CoTaskMemFree
0x18000c211  mov     qword ptr [rdi], 0
0x18000c218  jmp     short loc_18000C238
0x18000c21a  cmp     dword ptr [rbx+8], 0Eh
0x18000c21e  jnz     short loc_18000C238
0x18000c220  mov     rcx, [rbx+18h]; pv
0x18000c224  call    cs:__imp_CoTaskMemFree
0x18000c22a  mov     qword ptr [rbx+18h], 0
0x18000c232  mov     dword ptr [rdi], 0
0x18000c238  test    rsi, rsi
0x18000c23b  jz      loc_18000C341
0x18000c241  mov     rdx, rsi; unsigned __int16 *
0x18000c244  mov     rcx, rdi; unsigned __int16 **
0x18000c247  call    ?StringCopyWithAlloc@@YAJPEAPEAGPEBG@Z; StringCopyWithAlloc(ushort * *,ushort const *)
0x18000c24c  mov     esi, eax
0x18000c24e  test    eax, eax
0x18000c250  js      short loc_18000C2C6
0x18000c252  mov     dword ptr [rbx+8], 0Ah
0x18000c259  jmp     loc_18000C341
0x18000c25e  cmp     r14d, 0Eh
0x18000c262  jnz     loc_18000C2F7
0x18000c268  cmp     dword ptr [rbx+8], 0Ah
0x18000c26c  jnz     short loc_18000C280
0x18000c26e  mov     rcx, [rdi]; pv
0x18000c271  call    cs:__imp_CoTaskMemFree
0x18000c277  mov     qword ptr [rdi], 0
0x18000c27e  jmp     short loc_18000C29E
0x18000c280  cmp     dword ptr [rbx+8], 0Eh
0x18000c284  jnz     short loc_18000C29E
0x18000c286  mov     rcx, [rbx+18h]; pv
0x18000c28a  call    cs:__imp_CoTaskMemFree
0x18000c290  mov     qword ptr [rbx+18h], 0
0x18000c298  mov     dword ptr [rdi], 0
0x18000c29e  test    rdi, rdi
0x18000c2a1  jz      short loc_18000C2F0
0x18000c2a3  cmp     esi, 0FFFFh
0x18000c2a9  jnb     short loc_18000C2F0
0x18000c2ab  mov     ecx, esi; cb
0x18000c2ad  mov     r14d, esi
0x18000c2b0  call    cs:__imp_CoTaskMemAlloc
0x18000c2b6  mov     [rdi+8], rax
0x18000c2ba  test    rax, rax
0x18000c2bd  jnz     short loc_18000C2D2
0x18000c2bf  mov     r14d, [rbp+57h+arg_8]
0x18000c2c3  mov     esi, r12d
0x18000c2c6  mov     dword ptr [rbx+8], 0
0x18000c2cd  jmp     loc_18000C371
0x18000c2d2  mov     rdx, [rbp+57h+Src]; Src
0x18000c2d6  mov     r8, r14; Size
0x18000c2d9  mov     rcx, rax; void *
0x18000c2dc  call    memcpy_0
0x18000c2e1  mov     r14d, [rbp+57h+arg_8]
0x18000c2e5  mov     [rdi], esi
0x18000c2e7  mov     dword ptr [rbx+8], 0Eh
0x18000c2ee  jmp     short loc_18000C341
0x18000c2f0  mov     esi, 80070057h
0x18000c2f5  jmp     short loc_18000C2C6
0x18000c2f7  movups  xmm0, xmmword ptr [rbp+57h+var_C0]
0x18000c2fb  movups  xmm1, xmmword ptr [rbp+57h+cb]
0x18000c2ff  movups  xmmword ptr [rbx], xmm0
0x18000c302  movups  xmm0, [rbp+57h+var_A0]
0x18000c306  movups  xmmword ptr [rbx+10h], xmm1
0x18000c30a  movups  xmm1, [rbp+57h+var_90]
0x18000c30e  movups  xmmword ptr [rbx+20h], xmm0
0x18000c312  movups  xmm0, [rbp+57h+var_80]
0x18000c316  movups  xmmword ptr [rbx+30h], xmm1
0x18000c31a  movups  xmm1, [rbp+57h+var_70]
0x18000c31e  movups  xmmword ptr [rbx+40h], xmm0
0x18000c322  movups  xmm0, [rbp+57h+var_60]
0x18000c326  movups  xmmword ptr [rbx+50h], xmm1
0x18000c32a  movups  xmm1, [rbp+57h+var_50]
0x18000c32e  movups  xmmword ptr [rbx+60h], xmm0
0x18000c332  movups  xmm0, [rbp+57h+var_40]
0x18000c336  movups  xmmword ptr [rbx+70h], xmm1
0x18000c33a  movups  xmmword ptr [rbx+80h], xmm0
0x18000c341  xor     ecx, ecx; pv
0x18000c343  mov     qword ptr [rbx], 0
0x18000c34a  call    cs:__imp_CoTaskMemFree
0x18000c350  mov     rax, [rbp+57h+pv]
0x18000c354  mov     qword ptr [rbx], 0
0x18000c35b  test    rax, rax
0x18000c35e  jz      short loc_18000C3CE
0x18000c360  mov     rdx, rax; unsigned __int16 *
0x18000c363  mov     rcx, rbx; unsigned __int16 **
0x18000c366  call    ?StringCopyWithAlloc@@YAJPEAPEAGPEBG@Z; StringCopyWithAlloc(ushort * *,ushort const *)
0x18000c36b  mov     esi, eax
0x18000c36d  test    eax, eax
0x18000c36f  jns     short loc_18000C3CE
0x18000c371  cmp     dword ptr [rbx+8], 0Ah
0x18000c375  jnz     short loc_18000C389
0x18000c377  mov     rcx, [rdi]; pv
0x18000c37a  call    cs:__imp_CoTaskMemFree
0x18000c380  mov     qword ptr [rdi], 0
0x18000c387  jmp     short loc_18000C3A7
0x18000c389  cmp     dword ptr [rbx+8], 0Eh
0x18000c38d  jnz     short loc_18000C3A7
0x18000c38f  mov     rcx, [rbx+18h]; pv
0x18000c393  call    cs:__imp_CoTaskMemFree
0x18000c399  mov     qword ptr [rbx+18h], 0
0x18000c3a1  mov     dword ptr [rdi], 0
0x18000c3a7  mov     rcx, [rbx]; pv
0x18000c3aa  call    cs:__imp_CoTaskMemFree
0x18000c3b0  mov     eax, 80h
0x18000c3b5  mov     qword ptr [rbx], 0
0x18000c3bc  mov     byte ptr [rdi], 0
0x18000c3bf  inc     rdi
0x18000c3c2  sub     rax, 1
0x18000c3c6  jnz     short loc_18000C3BC
0x18000c3c8  mov     rcx, [rbp+57h+Src]
0x18000c3cc  jmp     short loc_18000C3D4
0x18000c3ce  mov     rcx, [rbp+57h+Src]; pv
0x18000c3d2  xor     esi, esi
0x18000c3d4  cmp     r14d, 0Ah
0x18000c3d8  jnz     short loc_18000C3E0
0x18000c3da  mov     rcx, [rbp+57h+var_C8]
0x18000c3de  jmp     short loc_18000C3E6
0x18000c3e0  cmp     r14d, 0Eh
0x18000c3e4  jnz     short loc_18000C3EC
0x18000c3e6  call    cs:__imp_CoTaskMemFree
0x18000c3ec  mov     rcx, [rbp+57h+pv]; pv
0x18000c3f0  call    cs:__imp_CoTaskMemFree
0x18000c3f6  test    esi, esi
0x18000c3f8  js      short loc_18000C40E
0x18000c3fa  mov     rsi, [rbp+57h+arg_10]
0x18000c3fe  inc     r13d
0x18000c401  cmp     r13d, [r15]
0x18000c404  jb      loc_18000C13C
0x18000c40a  xor     eax, eax
0x18000c40c  jmp     short loc_18000C41F
0x18000c40e  mov     rcx, r15; this
0x18000c411  call    ?FreeAll@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeAll(void)
0x18000c416  mov     eax, esi
0x18000c418  jmp     short loc_18000C41F
0x18000c41a  mov     eax, 80070057h
0x18000c41f  mov     rbx, [rsp+0F0h+arg_0]
0x18000c427  add     rsp, 0C0h
0x18000c42e  pop     r15
0x18000c430  pop     r14
0x18000c432  pop     r13
0x18000c434  pop     r12
0x18000c436  pop     rdi
0x18000c437  pop     rsi
0x18000c438  pop     rbp
0x18000c439  retn
```
