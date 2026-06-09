# CMemoryTable::SetupMeta(ulong,ulong,__MIDL___MIDL_itf_catalog_0000_0000_0004 *,void * *,ulong *)

- ea: `0x180010700`
- end: `0x1800109bc`
- name: `?SetupMeta@CMemoryTable@@AEAAJKKPEAU__MIDL___MIDL_itf_catalog_0000_0000_0004@@PEAPEAXPEAK@Z`
- size: `700`
- prototype: `int(CMemoryTable *__hidden this, unsigned int, unsigned int, struct __MIDL___MIDL_itf_catalog_0000_0000_0004 *, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x1800109d0`

## callees

- `0x180010700`
- `0x18002e0b2`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180010758`
- `ole32!CoTaskMemAlloc` at `0x180010791`
- `ole32!CoTaskMemAlloc` at `0x1800107be`
- `ole32!CoTaskMemAlloc` at `0x1800107f4`
- `ole32!CoTaskMemAlloc` at `0x180010758`
- `ole32!CoTaskMemAlloc` at `0x180010791`
- `ole32!CoTaskMemAlloc` at `0x1800107be`
- `ole32!CoTaskMemAlloc` at `0x1800107f4`

## pseudocode

```c
__int64 __fastcall CMemoryTable::SetupMeta(
        CMemoryTable *this,
        int a2,
        unsigned int a3,
        struct __MIDL___MIDL_itf_catalog_0000_0000_0004 *a4,
        void **Src,
        unsigned int *a6)
{
  void *v9; // rax
  LPVOID v10; // rax
  void *v11; // rax
  void *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r10
  _DWORD *v15; // r8
  unsigned int v16; // r9d
  int v17; // r11d
  __int64 v18; // rcx
  bool v19; // zf
  int v20; // eax
  __int16 v21; // ax
  int v22; // eax
  __int64 v23; // r8
  __int16 v24; // ax
  __int16 v25; // dx

  if ( *((_DWORD *)this + 23) )
    return 2149648405LL;
  if ( a3 >= 0x8000 )
    return 2147942487LL;
  *((_DWORD *)this + 8) = a2;
  *((_DWORD *)this + 9) = a3;
  v9 = CoTaskMemAlloc(saturated_mul(a3, 0xCu));
  *((_QWORD *)this + 7) = v9;
  if ( !v9 )
    return 2147942414LL;
  memcpy_0(v9, a4, 12LL * *((unsigned int *)this + 9));
  v10 = CoTaskMemAlloc(saturated_mul(*((unsigned int *)this + 9), 8u));
  *((_QWORD *)this + 8) = v10;
  if ( !v10 )
    return 2147942414LL;
  if ( Src )
  {
    v11 = CoTaskMemAlloc(saturated_mul(*((unsigned int *)this + 9), 8u));
    *((_QWORD *)this + 9) = v11;
    if ( v11 )
    {
      memcpy_0(v11, Src, 8LL * *((unsigned int *)this + 9));
      v12 = CoTaskMemAlloc(saturated_mul(*((unsigned int *)this + 9), 4u));
      *((_QWORD *)this + 10) = v12;
      if ( v12 )
      {
        memcpy_0(v12, a6, 4LL * *((unsigned int *)this + 9));
        goto LABEL_11;
      }
    }
    return 2147942414LL;
  }
LABEL_11:
  v13 = *((_QWORD *)this + 8);
  LODWORD(v14) = 0;
  v15 = (_DWORD *)*((_QWORD *)this + 7);
  v16 = 0;
  *((_DWORD *)this + 10) = 0;
  v17 = 0;
  v18 = v13;
  while ( (unsigned int)v14 < *((_DWORD *)this + 9) )
  {
    if ( *v15 == 19 )
    {
      v19 = v15[1] == 4;
    }
    else
    {
      if ( *v15 != 72 )
      {
        if ( *v15 == 128 || *v15 == 130 )
        {
          if ( !v15[1] )
            return 2149648398LL;
          goto LABEL_23;
        }
        if ( *v15 != 135 )
          goto LABEL_23;
      }
      v19 = v15[1] == 16;
    }
    if ( !v19 )
      return 2149648398LL;
LABEL_23:
    v20 = v15[2];
    if ( v20 < 0 || (*v15 == 19 || *v15 == 72 || *v15 == 135) && (v20 & 0x100000) == 0 )
      return 2149648398LL;
    if ( (v20 & 1) != 0 )
    {
      v17 = 1;
      if ( (v20 & 0x80000) == 0 )
        return 2149648398LL;
    }
    if ( (v20 & 0x8000000) != 0 )
      ++*((_DWORD *)this + 10);
    *(_WORD *)v13 = v14;
    if ( (v15[2] & 0x8000000) != 0 )
      v21 = *((_DWORD *)this + 10) - 1;
    else
      v21 = -1;
    *(_WORD *)(v13 + 2) = v21;
    *(_DWORD *)(v13 + 4) = v16 >> 3;
    if ( (v15[2] & 0x10000000) != 0 )
      v16 += 8;
    else
      v16 += (v15[1] + 7) & 0xFFFFFFF8;
    v14 = (unsigned int)(v14 + 1);
    v15 = (_DWORD *)(*((_QWORD *)this + 7) + 12 * v14);
    v18 = *((_QWORD *)this + 8);
    v13 = v18 + 8 * v14;
  }
  if ( !v17 )
    return 2149648398LL;
  *((_DWORD *)this + 11) = (unsigned int)(v14 + 7) >> 3;
  if ( (v16 & 7) != 0 )
    return 2147549183LL;
  v22 = *((_DWORD *)this + 10);
  LODWORD(v23) = 0;
  *((_DWORD *)this + 12) = v16 >> 3;
  *((_DWORD *)this + 10) = ((unsigned int)(4 * v22 + 7) >> 2) & 0x3FFFFFFE;
  if ( *((_DWORD *)this + 9) )
  {
    do
    {
      v24 = *(_WORD *)(v18 + 2);
      if ( v24 == -1 )
        v25 = 0;
      else
        v25 = *((_WORD *)this + 22);
      v23 = (unsigned int)(v23 + 1);
      *(_WORD *)(v18 + 2) = v25 + v24;
      *(_DWORD *)(v18 + 4) += (unsigned __int16)(*((_WORD *)this + 20) + *((_WORD *)this + 22));
      v18 = *((_QWORD *)this + 8) + 8 * v23;
    }
    while ( (unsigned int)v23 < *((_DWORD *)this + 9) );
  }
  *((_DWORD *)this + 23) = 1;
  return 0;
}

```

## disassembly

```asm
0x180010700  mov     [rsp+arg_0], rbx
0x180010705  mov     [rsp+arg_8], rbp
0x18001070a  push    rdi
0x18001070b  sub     rsp, 20h
0x18001070f  cmp     dword ptr [rcx+5Ch], 0
0x180010713  mov     rdi, r9
0x180010716  mov     rbx, rcx
0x180010719  jz      short loc_180010725
0x18001071b  mov     eax, 80210815h
0x180010720  jmp     loc_1800109AC
0x180010725  cmp     r8d, 8000h
0x18001072c  jb      short loc_180010738
0x18001072e  mov     eax, 80070057h
0x180010733  jmp     loc_1800109AC
0x180010738  mov     [rcx+20h], edx
0x18001073b  mov     eax, 0Ch
0x180010740  mov     [rcx+24h], r8d
0x180010744  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x18001074b  mov     ecx, r8d
0x18001074e  mul     rcx
0x180010751  cmovb   rax, rbp
0x180010755  mov     rcx, rax; cb
0x180010758  call    cs:__imp_CoTaskMemAlloc
0x18001075e  mov     [rbx+38h], rax
0x180010762  test    rax, rax
0x180010765  jz      loc_1800109A7
0x18001076b  mov     ecx, [rbx+24h]
0x18001076e  mov     rdx, rdi; Src
0x180010771  lea     r8, [rcx+rcx*2]
0x180010775  mov     rcx, rax; void *
0x180010778  shl     r8, 2; Size
0x18001077c  call    memcpy_0
0x180010781  mov     ecx, [rbx+24h]
0x180010784  lea     eax, [rbp+9]
0x180010787  mul     rcx
0x18001078a  cmovb   rax, rbp
0x18001078e  mov     rcx, rax; cb
0x180010791  call    cs:__imp_CoTaskMemAlloc
0x180010797  mov     [rbx+40h], rax
0x18001079b  test    rax, rax
0x18001079e  jz      loc_1800109A7
0x1800107a4  mov     rdi, [rsp+28h+Src]
0x1800107a9  test    rdi, rdi
0x1800107ac  jz      short loc_18001081C
0x1800107ae  mov     ecx, [rbx+24h]
0x1800107b1  lea     eax, [rbp+9]
0x1800107b4  mul     rcx
0x1800107b7  cmovb   rax, rbp
0x1800107bb  mov     rcx, rax; cb
0x1800107be  call    cs:__imp_CoTaskMemAlloc
0x1800107c4  mov     [rbx+48h], rax
0x1800107c8  test    rax, rax
0x1800107cb  jz      loc_1800109A7
0x1800107d1  mov     r8d, [rbx+24h]
0x1800107d5  mov     rdx, rdi; Src
0x1800107d8  shl     r8, 3; Size
0x1800107dc  mov     rcx, rax; void *
0x1800107df  call    memcpy_0
0x1800107e4  mov     ecx, [rbx+24h]
0x1800107e7  lea     eax, [rbp+5]
0x1800107ea  mul     rcx
0x1800107ed  cmovb   rax, rbp
0x1800107f1  mov     rcx, rax; cb
0x1800107f4  call    cs:__imp_CoTaskMemAlloc
0x1800107fa  mov     [rbx+50h], rax
0x1800107fe  test    rax, rax
0x180010801  jz      loc_1800109A7
0x180010807  mov     r8d, [rbx+24h]
0x18001080b  mov     rcx, rax; void *
0x18001080e  mov     rdx, [rsp+28h+arg_28]; Src
0x180010813  shl     r8, 2; Size
0x180010817  call    memcpy_0
0x18001081c  mov     rdx, [rbx+40h]
0x180010820  xor     r10d, r10d
0x180010823  mov     r8, [rbx+38h]
0x180010827  xor     r9d, r9d
0x18001082a  mov     [rbx+28h], r10d
0x18001082e  xor     r11d, r11d
0x180010831  mov     rcx, rdx
0x180010834  mov     ebp, 8000000h
0x180010839  lea     edi, [r10+1]
0x18001083d  cmp     r10d, [rbx+24h]
0x180010841  jnb     loc_180010918
0x180010847  mov     eax, [r8]
0x18001084a  sub     eax, 13h
0x18001084d  jz      short loc_180010877
0x18001084f  sub     eax, 35h ; '5'
0x180010852  jz      short loc_180010863
0x180010854  sub     eax, 38h ; '8'
0x180010857  jz      short loc_18001086A
0x180010859  sub     eax, 2
0x18001085c  jz      short loc_18001086A
0x18001085e  cmp     eax, 5
0x180010861  jnz     short loc_180010882
0x180010863  cmp     dword ptr [r8+4], 10h
0x180010868  jmp     short loc_18001087C
0x18001086a  cmp     dword ptr [r8+4], 0
0x18001086f  jz      loc_18001091D
0x180010875  jmp     short loc_180010882
0x180010877  cmp     dword ptr [r8+4], 4
0x18001087c  jnz     loc_18001091D
0x180010882  mov     eax, [r8+8]
0x180010886  test    eax, eax
0x180010888  js      loc_18001091D
0x18001088e  cmp     dword ptr [r8], 13h
0x180010892  jz      short loc_1800108A3
0x180010894  cmp     dword ptr [r8], 48h ; 'H'
0x180010898  jz      short loc_1800108A3
0x18001089a  cmp     dword ptr [r8], 87h
0x1800108a1  jnz     short loc_1800108A9
0x1800108a3  bt      eax, 14h
0x1800108a7  jnb     short loc_18001091D
0x1800108a9  test    dil, al
0x1800108ac  jz      short loc_1800108B7
0x1800108ae  mov     r11d, edi
0x1800108b1  bt      eax, 13h
0x1800108b5  jnb     short loc_18001091D
0x1800108b7  test    ebp, eax
0x1800108b9  jz      short loc_1800108BE
0x1800108bb  add     [rbx+28h], edi
0x1800108be  mov     [rdx], r10w
0x1800108c2  test    [r8+8], ebp
0x1800108c6  jz      short loc_1800108CF
0x1800108c8  mov     eax, [rbx+28h]
0x1800108cb  sub     eax, edi
0x1800108cd  jmp     short loc_1800108D2
0x1800108cf  or      eax, 0FFFFFFFFh
0x1800108d2  mov     [rdx+2], ax
0x1800108d6  mov     eax, r9d
0x1800108d9  shr     eax, 3
0x1800108dc  mov     [rdx+4], eax
0x1800108df  test    dword ptr [r8+8], 10000000h
0x1800108e7  jz      short loc_1800108EF
0x1800108e9  add     r9d, 8
0x1800108ed  jmp     short loc_1800108FC
0x1800108ef  mov     eax, [r8+4]
0x1800108f3  add     eax, 7
0x1800108f6  and     eax, 0FFFFFFF8h
0x1800108f9  add     r9d, eax
0x1800108fc  mov     rax, [rbx+38h]
0x180010900  add     r10d, edi
0x180010903  lea     rcx, [r10+r10*2]
0x180010907  lea     r8, [rax+rcx*4]
0x18001090b  mov     rcx, [rbx+40h]
0x18001090f  lea     rdx, [rcx+r10*8]
0x180010913  jmp     loc_18001083D
0x180010918  test    r11d, r11d
0x18001091b  jnz     short loc_180010927
0x18001091d  mov     eax, 8021080Eh
0x180010922  jmp     loc_1800109AC
0x180010927  lea     eax, [r10+7]
0x18001092b  shr     eax, 3
0x18001092e  mov     [rbx+2Ch], eax
0x180010931  test    r9b, 7
0x180010935  jz      short loc_18001093E
0x180010937  mov     eax, 8000FFFFh
0x18001093c  jmp     short loc_1800109AC
0x18001093e  mov     eax, [rbx+28h]
0x180010941  xor     r8d, r8d
0x180010944  shr     r9d, 3
0x180010948  mov     [rbx+30h], r9d
0x18001094c  lea     eax, ds:7[rax*4]
0x180010953  shr     eax, 2
0x180010956  and     eax, 3FFFFFFEh
0x18001095b  mov     [rbx+28h], eax
0x18001095e  cmp     [rbx+24h], r8d
0x180010962  jbe     short loc_1800109A0
0x180010964  movzx   eax, word ptr [rcx+2]
0x180010968  mov     edx, 0FFFFh
0x18001096d  cmp     dx, ax
0x180010970  jnz     short loc_180010976
0x180010972  xor     edx, edx
0x180010974  jmp     short loc_18001097A
0x180010976  movzx   edx, word ptr [rbx+2Ch]
0x18001097a  add     ax, dx
0x18001097d  add     r8d, edi
0x180010980  mov     [rcx+2], ax
0x180010984  movzx   eax, word ptr [rbx+2Ch]
0x180010988  add     ax, [rbx+28h]
0x18001098c  movzx   eax, ax
0x18001098f  add     [rcx+4], eax
0x180010992  mov     rax, [rbx+40h]
0x180010996  lea     rcx, [rax+r8*8]
0x18001099a  cmp     r8d, [rbx+24h]
0x18001099e  jb      short loc_180010964
0x1800109a0  mov     [rbx+5Ch], edi
0x1800109a3  xor     eax, eax
0x1800109a5  jmp     short loc_1800109AC
0x1800109a7  mov     eax, 8007000Eh
0x1800109ac  mov     rbx, [rsp+28h+arg_0]
0x1800109b1  mov     rbp, [rsp+28h+arg_8]
0x1800109b6  add     rsp, 20h
0x1800109ba  pop     rdi
0x1800109bb  retn
```
