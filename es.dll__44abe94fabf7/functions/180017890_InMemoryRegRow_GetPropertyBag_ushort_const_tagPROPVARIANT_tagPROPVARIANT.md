# InMemoryRegRow::GetPropertyBag(ushort const *,tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x180017890`
- end: `0x180017a2b`
- name: `?GetPropertyBag@InMemoryRegRow@@UEAAJPEBGPEAUtagPROPVARIANT@@1@Z`
- size: `411`
- prototype: `int(InMemoryRegRow *__hidden this, const unsigned __int16 *, struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180017890`
- `0x180017a40`
- `0x180017aa0`
- `0x180017b2c`
- `0x1800434c6`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800179fd`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800179fd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180017944`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001794d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180017944`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001794d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017959`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017985`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017959`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017985`

## pseudocode

```c
__int64 __fastcall InMemoryRegRow::GetPropertyBag(
        InMemoryRegRow *this,
        const unsigned __int16 *a2,
        PROPVARIANT *a3,
        PROPVARIANT *a4)
{
  unsigned int v8; // eax
  __int64 v9; // r8
  unsigned int v10; // ebx
  __int64 *i; // rbx
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rbp
  __int64 v16; // rdi
  BYTE *v17; // rax
  BYTE *v18; // rax
  __int64 v19; // rdx
  BYTE *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rsi

  *(_OWORD *)a3 = 0;
  a3[2] = 0;
  *(_OWORD *)a4 = 0;
  a4[2] = 0;
  v8 = InMemoryRegRow::HashCaseInsentitiveWSTR::Hash(a2);
  v9 = *((_QWORD *)this + 10);
  if ( !v9 )
    return 1;
  for ( i = (__int64 *)(v9 + 8LL * (v8 % *((_DWORD *)this + 22))); ; i = (__int64 *)(v14 + 16) )
  {
    if ( !*i )
      return 1;
    v13 = InMemoryRegRow::HashCaseInsentitiveWSTR::Equals(*(const unsigned __int16 **)(*i + 32), a2);
    v14 = *i;
    if ( v13 )
      break;
  }
  v15 = *(_QWORD *)(v14 + 40);
  v10 = 0;
  v16 = *(unsigned int *)(v15 + 16);
  if ( !(_DWORD)v16 )
    return v10;
  if ( (unsigned __int64)(8 * v16) > 0xFFFFFFFF || (unsigned __int64)(24 * v16) > 0xFFFFFFFF )
  {
    v10 = -2147024362;
LABEL_12:
    PropVariantClear(a3);
    PropVariantClear(a4);
    return v10;
  }
  v17 = (BYTE *)CoTaskMemAlloc((unsigned int)(8 * v16));
  a3[2] = v17;
  if ( !v17
    || (memset_0(v17, 0, (unsigned int)(8 * v16)),
        *(_WORD *)a3 = 4127,
        *((_DWORD *)a3 + 2) = v16,
        v18 = (BYTE *)CoTaskMemAlloc((unsigned int)(24 * v16)),
        (a4[2] = v18) == 0) )
  {
    v10 = -2147024882;
    goto LABEL_12;
  }
  v19 = 0;
  v10 = 0;
  do
  {
    v20 = (BYTE *)a4[2];
    v21 = 3 * v19;
    v19 = (unsigned int)(v19 + 1);
    *(_OWORD *)&v20[8 * v21] = 0;
    *(_QWORD *)&v20[8 * v21 + 16] = 0;
  }
  while ( (unsigned int)v19 < (unsigned int)v16 );
  *(_WORD *)a4 = 4108;
  v22 = 0;
  *((_DWORD *)a4 + 2) = v16;
  while ( (unsigned int)v22 < (unsigned int)v16 )
  {
    *((_QWORD *)a3[2] + v22) = WStringCopy(*(const unsigned __int16 **)(*(_QWORD *)v15 + 8 * v22));
    if ( !*((_QWORD *)a3[2] + v22) )
    {
      v10 = -2147024882;
      break;
    }
    v10 = PropVariantCopy((PROPVARIANT *)a4[2] + 3 * v22, (const PROPVARIANT *)(*(_QWORD *)(v15 + 8) + 24 * v22));
    if ( v10 )
      break;
    v22 = (unsigned int)(v22 + 1);
  }
  if ( (v10 & 0x80000000) != 0 )
    goto LABEL_12;
  return v10;
}

```

## disassembly

```asm
0x180017890  push    rbx
0x180017892  push    rbp
0x180017893  push    rsi
0x180017894  push    rdi
0x180017895  push    r14
0x180017897  push    r15
0x180017899  sub     rsp, 28h
0x18001789d  xor     eax, eax
0x18001789f  xorps   xmm0, xmm0
0x1800178a2  movups  xmmword ptr [r8], xmm0
0x1800178a6  mov     [r8+10h], rax
0x1800178aa  mov     rbx, rcx
0x1800178ad  xorps   xmm1, xmm1
0x1800178b0  mov     rcx, rdx; unsigned __int16 *
0x1800178b3  movups  xmmword ptr [r9], xmm1
0x1800178b7  mov     [r9+10h], rax
0x1800178bb  mov     r14, r9
0x1800178be  mov     r15, r8
0x1800178c1  mov     rdi, rdx
0x1800178c4  call    ?Hash@HashCaseInsentitiveWSTR@InMemoryRegRow@@SAKPEBG@Z; InMemoryRegRow::HashCaseInsentitiveWSTR::Hash(ushort const *)
0x1800178c9  mov     r8, [rbx+50h]
0x1800178cd  test    r8, r8
0x1800178d0  jnz     short loc_1800178E6
0x1800178d2  mov     ebx, 1
0x1800178d7  mov     eax, ebx
0x1800178d9  add     rsp, 28h
0x1800178dd  pop     r15
0x1800178df  pop     r14
0x1800178e1  pop     rdi
0x1800178e2  pop     rsi
0x1800178e3  pop     rbp
0x1800178e4  pop     rbx
0x1800178e5  retn
0x1800178e6  xor     edx, edx
0x1800178e8  div     dword ptr [rbx+58h]
0x1800178eb  lea     rbx, [r8+rdx*8]
0x1800178ef  mov     rcx, [rbx]
0x1800178f2  test    rcx, rcx
0x1800178f5  jz      short loc_1800178D2
0x1800178f7  mov     rcx, [rcx+20h]; unsigned __int16 *
0x1800178fb  mov     rdx, rdi; unsigned __int16 *
0x1800178fe  call    ?Equals@HashCaseInsentitiveWSTR@InMemoryRegRow@@SAHPEBG0@Z; InMemoryRegRow::HashCaseInsentitiveWSTR::Equals(ushort const *,ushort const *)
0x180017903  mov     rcx, [rbx]
0x180017906  test    eax, eax
0x180017908  jnz     short loc_180017910
0x18001790a  lea     rbx, [rcx+10h]
0x18001790e  jmp     short loc_1800178EF
0x180017910  mov     rbp, [rcx+28h]
0x180017914  xor     ebx, ebx
0x180017916  mov     edi, [rbp+10h]
0x180017919  test    edi, edi
0x18001791b  jz      short loc_1800178D7
0x18001791d  lea     rcx, ds:0[rdi*8]
0x180017925  mov     edx, 0FFFFFFFFh
0x18001792a  cmp     rcx, rdx
0x18001792d  ja      short loc_18001793C
0x18001792f  lea     rbx, [rdi+rdi*2]
0x180017933  shl     rbx, 3
0x180017937  cmp     rbx, rdx
0x18001793a  jbe     short loc_180017955
0x18001793c  mov     ebx, 80070216h
0x180017941  mov     rcx, r15; pvar
0x180017944  call    cs:__imp_PropVariantClear
0x18001794a  mov     rcx, r14; pvar
0x18001794d  call    cs:__imp_PropVariantClear
0x180017953  jmp     short loc_1800178D7
0x180017955  mov     esi, ecx
0x180017957  mov     ecx, ecx; cb
0x180017959  call    cs:__imp_CoTaskMemAlloc
0x18001795f  mov     [r15+10h], rax
0x180017963  test    rax, rax
0x180017966  jz      loc_180017A1A
0x18001796c  mov     r8d, esi; Size
0x18001796f  xor     edx, edx; Val
0x180017971  mov     rcx, rax; void *
0x180017974  call    memset_0
0x180017979  mov     ecx, ebx; cb
0x18001797b  mov     word ptr [r15], 101Fh
0x180017981  mov     [r15+8], edi
0x180017985  call    cs:__imp_CoTaskMemAlloc
0x18001798b  mov     [r14+10h], rax
0x18001798f  test    rax, rax
0x180017992  jz      loc_180017A1A
0x180017998  xor     edx, edx
0x18001799a  xor     ebx, ebx
0x18001799c  mov     rax, [r14+10h]
0x1800179a0  lea     rcx, [rdx+rdx*2]
0x1800179a4  xor     r8d, r8d
0x1800179a7  xorps   xmm0, xmm0
0x1800179aa  inc     edx
0x1800179ac  movups  xmmword ptr [rax+rcx*8], xmm0
0x1800179b0  mov     [rax+rcx*8+10h], r8
0x1800179b5  cmp     edx, edi
0x1800179b7  jb      short loc_18001799C
0x1800179b9  mov     word ptr [r14], 100Ch
0x1800179bf  xor     esi, esi
0x1800179c1  mov     [r14+8], edi
0x1800179c5  cmp     esi, edi
0x1800179c7  jnb     short loc_180017A0D
0x1800179c9  mov     rcx, [rbp+0]
0x1800179cd  mov     rcx, [rcx+rsi*8]; Src
0x1800179d1  call    ?WStringCopy@@YAPEAGPEBG@Z; WStringCopy(ushort const *)
0x1800179d6  mov     rcx, [r15+10h]
0x1800179da  mov     [rcx+rsi*8], rax
0x1800179de  mov     rax, [r15+10h]
0x1800179e2  cmp     qword ptr [rax+rsi*8], 0
0x1800179e7  jz      short loc_180017A24
0x1800179e9  mov     rax, [rbp+8]
0x1800179ed  lea     rcx, [rsi+rsi*2]
0x1800179f1  lea     rdx, [rax+rcx*8]; pvarSrc
0x1800179f5  mov     rax, [r14+10h]
0x1800179f9  lea     rcx, [rax+rcx*8]; pvarDest
0x1800179fd  call    cs:__imp_PropVariantCopy
0x180017a03  mov     ebx, eax
0x180017a05  test    eax, eax
0x180017a07  jnz     short loc_180017A0D
0x180017a09  inc     esi
0x180017a0b  jmp     short loc_1800179C5
0x180017a0d  test    ebx, ebx
0x180017a0f  jns     loc_1800178D7
0x180017a15  jmp     loc_180017941
0x180017a1a  mov     ebx, 8007000Eh
0x180017a1f  jmp     loc_180017941
0x180017a24  mov     ebx, 8007000Eh
0x180017a29  jmp     short loc_180017A0D
```
