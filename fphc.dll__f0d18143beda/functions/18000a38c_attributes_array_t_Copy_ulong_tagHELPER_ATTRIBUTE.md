# _attributes_array_t::Copy(ulong,tagHELPER_ATTRIBUTE *)

- ea: `0x18000a38c`
- end: `0x18000a6c4`
- name: `?Copy@_attributes_array_t@@QEAAJKPEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `824`
- prototype: `__int64 __fastcall(LPVOID *this, unsigned int, struct tagHELPER_ATTRIBUTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000aac0`

## callees

- `0x180006160`
- `0x180006628`
- `0x180008998`
- `0x180008ac0`
- `0x18000a38c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a3e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a481`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a49b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a4b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a4e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a500`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a5ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a5ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a608`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a620`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a660`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a66a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a693`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a3e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a481`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a49b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a4b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a4e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a500`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a5ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a5ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a608`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a620`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a660`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a66a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a693`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a3fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a3fc`

## pseudocode

```c
__int64 __fastcall _attributes_array_t::Copy(LPVOID *this, unsigned int a2, struct tagHELPER_ATTRIBUTE *a3)
{
  __int64 v3; // rdi
  struct tagHELPER_ATTRIBUTE *v4; // r14
  __int64 result; // rax
  __int64 v7; // rbx
  _BYTE *v8; // rax
  unsigned int v9; // r15d
  char *v10; // rbx
  __int64 v11; // rdi
  const unsigned __int16 *v12; // r13
  LPVOID *v13; // rbx
  int v14; // r12d
  LPVOID *v15; // r14
  _BYTE *v16; // rax
  __int64 v17; // rcx
  int v18; // edi
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int64 v27; // rax
  unsigned __int16 *v28; // rcx
  unsigned __int16 *v29[2]; // [rsp+20h] [rbp-69h] BYREF
  LPVOID pv[2]; // [rsp+30h] [rbp-59h] BYREF
  __int128 v31; // [rsp+40h] [rbp-49h]
  __int128 v32; // [rsp+50h] [rbp-39h]
  __int128 v33; // [rsp+60h] [rbp-29h]
  __int128 v34; // [rsp+70h] [rbp-19h]
  __int128 v35; // [rsp+80h] [rbp-9h]
  __int128 v36; // [rsp+90h] [rbp+7h]
  __int128 v37; // [rsp+A0h] [rbp+17h]
  unsigned __int16 *v39; // [rsp+108h] [rbp+7Fh]

  v3 = a2;
  v4 = a3;
  if ( a2 && a3 )
  {
    if ( a2 > 0x1C71C71 )
      return 2147942934LL;
    _attributes_array_t::FreeElements((_attributes_array_t *)this);
    CoTaskMemFree(this[1]);
    this[1] = 0;
    v7 = 144 * v3;
    *(_DWORD *)this = 0;
    v8 = CoTaskMemAlloc(144 * v3);
    this[1] = v8;
    if ( !v8 )
      return 2147942414LL;
    for ( ; v7; --v7 )
      *v8++ = 0;
    *(_DWORD *)this = v3;
    v9 = 0;
    if ( !(_DWORD)v3 )
      return 0;
    while ( 1 )
    {
      v10 = (char *)this[1];
      v29[0] = 0;
      LODWORD(v29[1]) = 0;
      v11 = v9;
      _attribute_t::Copy(v29, &v4[v11]);
      v12 = (const unsigned __int16 *)pv[0];
      v13 = (LPVOID *)&v10[v11 * 144];
      v14 = (int)v29[1];
      v39 = v29[0];
      if ( v13 == (LPVOID *)v29 )
        goto LABEL_40;
      if ( *((_DWORD *)v13 + 2) == 10 )
      {
        CoTaskMemFree(v13[2]);
        v13[2] = 0;
      }
      else if ( *((_DWORD *)v13 + 2) == 14 )
      {
        CoTaskMemFree(v13[3]);
        v13[3] = 0;
        *((_DWORD *)v13 + 4) = 0;
      }
      CoTaskMemFree(*v13);
      v15 = v13 + 2;
      *v13 = 0;
      v16 = v13 + 2;
      v17 = 128;
      do
      {
        *v16++ = 0;
        --v17;
      }
      while ( v17 );
      if ( v14 == 10 )
      {
        if ( *((_DWORD *)v13 + 2) == 10 )
        {
          CoTaskMemFree(*v15);
          *v15 = 0;
        }
        else if ( *((_DWORD *)v13 + 2) == 14 )
        {
          CoTaskMemFree(v13[3]);
          v13[3] = 0;
          *(_DWORD *)v15 = 0;
        }
        if ( v12 )
        {
          v18 = StringCchCopyWithAlloc((unsigned __int16 **)v13 + 2, 0xFFFFu, v12);
          if ( v18 < 0 )
          {
            *((_DWORD *)v13 + 2) = 0;
            goto LABEL_32;
          }
          *((_DWORD *)v13 + 2) = 10;
        }
      }
      else if ( v14 == 14 )
      {
        v18 = _attribute_t::SetValue((_attribute_t *)v13, (const struct tagOCTET_STRING *)pv);
        if ( v18 < 0 )
          goto LABEL_32;
      }
      else
      {
        v19 = *(_OWORD *)pv;
        *(_OWORD *)v13 = *(_OWORD *)v29;
        v20 = v31;
        *((_OWORD *)v13 + 1) = v19;
        v21 = v32;
        *((_OWORD *)v13 + 2) = v20;
        v22 = v33;
        *((_OWORD *)v13 + 3) = v21;
        v23 = v34;
        *((_OWORD *)v13 + 4) = v22;
        v24 = v35;
        *((_OWORD *)v13 + 5) = v23;
        v25 = v36;
        *((_OWORD *)v13 + 6) = v24;
        v26 = v37;
        *((_OWORD *)v13 + 7) = v25;
        *((_OWORD *)v13 + 8) = v26;
      }
      *v13 = 0;
      CoTaskMemFree(0);
      *v13 = 0;
      if ( !v39 || (v18 = StringCchCopyWithAlloc((unsigned __int16 **)v13, 0xFFFFu, v39), v18 >= 0) )
      {
        v4 = a3;
LABEL_40:
        v18 = 0;
        goto LABEL_41;
      }
LABEL_32:
      if ( *((_DWORD *)v13 + 2) == 10 )
      {
        CoTaskMemFree(*v15);
        *v15 = 0;
      }
      else if ( *((_DWORD *)v13 + 2) == 14 )
      {
        CoTaskMemFree(v13[3]);
        v13[3] = 0;
        *(_DWORD *)v15 = 0;
      }
      CoTaskMemFree(*v13);
      v27 = 128;
      *v13 = 0;
      do
      {
        *(_BYTE *)v15 = 0;
        v15 = (LPVOID *)((char *)v15 + 1);
        --v27;
      }
      while ( v27 );
      v4 = a3;
LABEL_41:
      if ( v14 == 10 )
      {
        v28 = (unsigned __int16 *)v12;
      }
      else
      {
        if ( v14 != 14 )
          goto LABEL_46;
        v28 = (unsigned __int16 *)pv[1];
      }
      CoTaskMemFree(v28);
LABEL_46:
      CoTaskMemFree(v39);
      if ( v18 < 0 )
      {
        _attributes_array_t::FreeElements((_attributes_array_t *)this);
        CoTaskMemFree(this[1]);
        result = (unsigned int)v18;
        this[1] = 0;
        *(_DWORD *)this = 0;
        return result;
      }
      if ( ++v9 >= *(_DWORD *)this )
        return 0;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000a38c  mov     [rsp-8+arg_0], rbx
0x18000a391  mov     [rsp-8+arg_10], r8
0x18000a396  push    rbp
0x18000a397  push    rsi
0x18000a398  push    rdi
0x18000a399  push    r12
0x18000a39b  push    r13
0x18000a39d  push    r14
0x18000a39f  push    r15
0x18000a3a1  lea     rbp, [rsp-27h]
0x18000a3a6  sub     rsp, 0B0h
0x18000a3ad  xor     r12d, r12d
0x18000a3b0  mov     edi, edx
0x18000a3b2  mov     r14, r8
0x18000a3b5  mov     rsi, rcx
0x18000a3b8  test    edx, edx
0x18000a3ba  jz      loc_18000A6A4
0x18000a3c0  test    r8, r8
0x18000a3c3  jz      loc_18000A6A4
0x18000a3c9  cmp     edi, 1C71C71h
0x18000a3cf  jbe     short loc_18000A3DB
0x18000a3d1  mov     eax, 80070216h
0x18000a3d6  jmp     loc_18000A6A9
0x18000a3db  call    ?FreeElements@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeElements(void)
0x18000a3e0  mov     rcx, [rsi+8]; pv
0x18000a3e4  call    cs:__imp_CoTaskMemFree
0x18000a3ea  lea     rbx, [rdi+rdi*8]
0x18000a3ee  mov     [rsi+8], r12
0x18000a3f2  shl     rbx, 4
0x18000a3f6  mov     rcx, rbx; cb
0x18000a3f9  mov     [rsi], r12d
0x18000a3fc  call    cs:__imp_CoTaskMemAlloc
0x18000a402  mov     [rsi+8], rax
0x18000a406  test    rax, rax
0x18000a409  jnz     short loc_18000A415
0x18000a40b  mov     eax, 8007000Eh
0x18000a410  jmp     loc_18000A6A9
0x18000a415  test    rbx, rbx
0x18000a418  jz      short loc_18000A426
0x18000a41a  mov     [rax], r12b
0x18000a41d  inc     rax
0x18000a420  sub     rbx, 1
0x18000a424  jnz     short loc_18000A41A
0x18000a426  mov     [rsi], edi
0x18000a428  mov     r15d, r12d
0x18000a42b  test    edi, edi
0x18000a42d  jz      loc_18000A683
0x18000a433  mov     rbx, [rsi+8]
0x18000a437  lea     rcx, [rbp+57h+var_C0]; this
0x18000a43b  mov     eax, r15d
0x18000a43e  mov     [rbp+57h+var_C0], r12
0x18000a442  mov     dword ptr [rbp+57h+var_C0+8], r12d
0x18000a446  lea     rdi, [rax+rax*8]
0x18000a44a  shl     rdi, 4
0x18000a44e  lea     rdx, [rdi+r14]; struct tagHELPER_ATTRIBUTE *
0x18000a452  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x18000a457  mov     rax, [rbp+57h+var_C0]
0x18000a45b  lea     rcx, [rbp+57h+var_C0]
0x18000a45f  mov     r13, [rbp+57h+pv]
0x18000a463  add     rbx, rdi
0x18000a466  mov     r12d, dword ptr [rbp+57h+var_C0+8]
0x18000a46a  mov     [rbp+57h+arg_18], rax
0x18000a46e  cmp     rbx, rcx
0x18000a471  jz      loc_18000A649
0x18000a477  cmp     dword ptr [rbx+8], 0Ah
0x18000a47b  jnz     short loc_18000A491
0x18000a47d  mov     rcx, [rbx+10h]; pv
0x18000a481  call    cs:__imp_CoTaskMemFree
0x18000a487  mov     qword ptr [rbx+10h], 0
0x18000a48f  jmp     short loc_18000A4B0
0x18000a491  cmp     dword ptr [rbx+8], 0Eh
0x18000a495  jnz     short loc_18000A4B0
0x18000a497  mov     rcx, [rbx+18h]; pv
0x18000a49b  call    cs:__imp_CoTaskMemFree
0x18000a4a1  mov     qword ptr [rbx+18h], 0
0x18000a4a9  mov     dword ptr [rbx+10h], 0
0x18000a4b0  mov     rcx, [rbx]; pv
0x18000a4b3  call    cs:__imp_CoTaskMemFree
0x18000a4b9  lea     r14, [rbx+10h]
0x18000a4bd  mov     qword ptr [rbx], 0
0x18000a4c4  mov     rax, r14
0x18000a4c7  mov     ecx, 80h
0x18000a4cc  mov     byte ptr [rax], 0
0x18000a4cf  inc     rax
0x18000a4d2  sub     rcx, 1
0x18000a4d6  jnz     short loc_18000A4CC
0x18000a4d8  cmp     r12d, 0Ah
0x18000a4dc  jnz     short loc_18000A549
0x18000a4de  cmp     [rbx+8], r12d
0x18000a4e2  jnz     short loc_18000A4F6
0x18000a4e4  mov     rcx, [r14]; pv
0x18000a4e7  call    cs:__imp_CoTaskMemFree
0x18000a4ed  mov     qword ptr [r14], 0
0x18000a4f4  jmp     short loc_18000A515
0x18000a4f6  cmp     dword ptr [rbx+8], 0Eh
0x18000a4fa  jnz     short loc_18000A515
0x18000a4fc  mov     rcx, [rbx+18h]; pv
0x18000a500  call    cs:__imp_CoTaskMemFree
0x18000a506  mov     qword ptr [rbx+18h], 0
0x18000a50e  mov     dword ptr [r14], 0
0x18000a515  test    r13, r13
0x18000a518  jz      loc_18000A5B1
0x18000a51e  mov     r8, r13; unsigned __int16 *
0x18000a521  mov     edx, 0FFFFh; unsigned __int64
0x18000a526  mov     rcx, r14; unsigned __int16 **
0x18000a529  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x18000a52e  mov     edi, eax
0x18000a530  test    eax, eax
0x18000a532  js      short loc_18000A53D
0x18000a534  mov     dword ptr [rbx+8], 0Ah
0x18000a53b  jmp     short loc_18000A5B1
0x18000a53d  mov     dword ptr [rbx+8], 0
0x18000a544  jmp     loc_18000A5E6
0x18000a549  cmp     r12d, 0Eh
0x18000a54d  jnz     short loc_18000A567
0x18000a54f  lea     rdx, [rbp+57h+pv]; struct tagOCTET_STRING *
0x18000a553  mov     rcx, rbx; this
0x18000a556  call    ?SetValue@_attribute_t@@QEAAJPEBUtagOCTET_STRING@@@Z; _attribute_t::SetValue(tagOCTET_STRING const *)
0x18000a55b  mov     edi, eax
0x18000a55d  test    eax, eax
0x18000a55f  js      loc_18000A5E6
0x18000a565  jmp     short loc_18000A5B1
0x18000a567  movups  xmm0, xmmword ptr [rbp+57h+var_C0]
0x18000a56b  movups  xmm1, xmmword ptr [rbp+57h+pv]
0x18000a56f  movups  xmmword ptr [rbx], xmm0
0x18000a572  movups  xmm0, [rbp+57h+var_A0]
0x18000a576  movups  xmmword ptr [rbx+10h], xmm1
0x18000a57a  movups  xmm1, [rbp+57h+var_90]
0x18000a57e  movups  xmmword ptr [rbx+20h], xmm0
0x18000a582  movups  xmm0, [rbp+57h+var_80]
0x18000a586  movups  xmmword ptr [rbx+30h], xmm1
0x18000a58a  movups  xmm1, [rbp+57h+var_70]
0x18000a58e  movups  xmmword ptr [rbx+40h], xmm0
0x18000a592  movups  xmm0, [rbp+57h+var_60]
0x18000a596  movups  xmmword ptr [rbx+50h], xmm1
0x18000a59a  movups  xmm1, [rbp+57h+var_50]
0x18000a59e  movups  xmmword ptr [rbx+60h], xmm0
0x18000a5a2  movups  xmm0, [rbp+57h+var_40]
0x18000a5a6  movups  xmmword ptr [rbx+70h], xmm1
0x18000a5aa  movups  xmmword ptr [rbx+80h], xmm0
0x18000a5b1  xor     ecx, ecx; pv
0x18000a5b3  mov     qword ptr [rbx], 0
0x18000a5ba  call    cs:__imp_CoTaskMemFree
0x18000a5c0  mov     rax, [rbp+57h+arg_18]
0x18000a5c4  mov     qword ptr [rbx], 0
0x18000a5cb  test    rax, rax
0x18000a5ce  jz      short loc_18000A645
0x18000a5d0  mov     r8, rax; unsigned __int16 *
0x18000a5d3  mov     edx, 0FFFFh; unsigned __int64
0x18000a5d8  mov     rcx, rbx; unsigned __int16 **
0x18000a5db  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x18000a5e0  mov     edi, eax
0x18000a5e2  test    eax, eax
0x18000a5e4  jns     short loc_18000A645
0x18000a5e6  cmp     dword ptr [rbx+8], 0Ah
0x18000a5ea  jnz     short loc_18000A5FE
0x18000a5ec  mov     rcx, [r14]; pv
0x18000a5ef  call    cs:__imp_CoTaskMemFree
0x18000a5f5  mov     qword ptr [r14], 0
0x18000a5fc  jmp     short loc_18000A61D
0x18000a5fe  cmp     dword ptr [rbx+8], 0Eh
0x18000a602  jnz     short loc_18000A61D
0x18000a604  mov     rcx, [rbx+18h]; pv
0x18000a608  call    cs:__imp_CoTaskMemFree
0x18000a60e  mov     qword ptr [rbx+18h], 0
0x18000a616  mov     dword ptr [r14], 0
0x18000a61d  mov     rcx, [rbx]; pv
0x18000a620  call    cs:__imp_CoTaskMemFree
0x18000a626  mov     eax, 80h
0x18000a62b  mov     qword ptr [rbx], 0
0x18000a632  mov     byte ptr [r14], 0
0x18000a636  inc     r14
0x18000a639  sub     rax, 1
0x18000a63d  jnz     short loc_18000A632
0x18000a63f  mov     r14, [rbp+57h+arg_10]
0x18000a643  jmp     short loc_18000A64B
0x18000a645  mov     r14, [rbp+57h+arg_10]
0x18000a649  xor     edi, edi
0x18000a64b  cmp     r12d, 0Ah
0x18000a64f  jnz     short loc_18000A656
0x18000a651  mov     rcx, r13
0x18000a654  jmp     short loc_18000A660
0x18000a656  cmp     r12d, 0Eh
0x18000a65a  jnz     short loc_18000A666
0x18000a65c  mov     rcx, [rbp+57h+pv+8]; pv
0x18000a660  call    cs:__imp_CoTaskMemFree
0x18000a666  mov     rcx, [rbp+57h+arg_18]; pv
0x18000a66a  call    cs:__imp_CoTaskMemFree
0x18000a670  xor     r12d, r12d
0x18000a673  test    edi, edi
0x18000a675  js      short loc_18000A687
0x18000a677  inc     r15d
0x18000a67a  cmp     r15d, [rsi]
0x18000a67d  jb      loc_18000A433
0x18000a683  xor     eax, eax
0x18000a685  jmp     short loc_18000A6A9
0x18000a687  mov     rcx, rsi; this
0x18000a68a  call    ?FreeElements@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeElements(void)
0x18000a68f  mov     rcx, [rsi+8]; pv
0x18000a693  call    cs:__imp_CoTaskMemFree
0x18000a699  mov     eax, edi
0x18000a69b  mov     [rsi+8], r12
0x18000a69f  mov     [rsi], r12d
0x18000a6a2  jmp     short loc_18000A6A9
0x18000a6a4  mov     eax, 80070057h
0x18000a6a9  mov     rbx, [rsp+0E0h+arg_0]
0x18000a6b1  add     rsp, 0B0h
0x18000a6b8  pop     r15
0x18000a6ba  pop     r14
0x18000a6bc  pop     r13
0x18000a6be  pop     r12
0x18000a6c0  pop     rdi
0x18000a6c1  pop     rsi
0x18000a6c2  pop     rbp
0x18000a6c3  retn
```
