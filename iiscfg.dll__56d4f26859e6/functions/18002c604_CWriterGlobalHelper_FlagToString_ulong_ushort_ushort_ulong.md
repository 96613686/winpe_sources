# CWriterGlobalHelper::FlagToString(ulong,ushort * *,ushort *,ulong)

- ea: `0x18002c604`
- end: `0x18002c9c6`
- name: `?FlagToString@CWriterGlobalHelper@@QEAAJKPEAPEAGPEAGK@Z`
- size: `962`
- prototype: `__int64 __fastcall(CWriterGlobalHelper *__hidden this, unsigned int, unsigned __int16 **, unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18002afe4`
- `0x18002b52c`
- `0x18002be2c`
- `0x18002d934`

## callees

- `0x18002c604`
- `0x18002ccc8`
- `0x18002d730`
- `0x18002d8b4`
- `0x18002deec`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18002c94f`
- `msvcrt!wcscat_s` at `0x18002c96b`
- `msvcrt!wcscat_s` at `0x18002c94f`
- `msvcrt!wcscat_s` at `0x18002c96b`
- `msvcrt!wcscpy_s` at `0x18002c916`
- `msvcrt!wcscpy_s` at `0x18002c916`
- `ole32!CoTaskMemFree` at `0x18002c91f`
- `ole32!CoTaskMemFree` at `0x18002c91f`

## pseudocode

```c
__int64 __fastcall CWriterGlobalHelper::FlagToString(
        __int64 **this,
        unsigned int a2,
        unsigned __int16 **a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  int v5; // r12d
  CWriterGlobalHelper *v6; // r15
  __int64 *v7; // rcx
  unsigned __int16 *v8; // r13
  __int64 v11; // rax
  __int64 result; // rax
  unsigned int v13; // ecx
  __int64 v14; // rcx
  __int64 v15; // rdi
  unsigned int v16; // r14d
  __int64 v17; // rdx
  __int64 v18; // rcx
  unsigned __int16 *v19; // rcx
  int v20; // edx
  int v21; // r8d
  __int64 v22; // r15
  unsigned __int16 *v23; // r13
  wchar_t *v24; // rcx
  unsigned int v25; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v26; // [rsp+44h] [rbp-BCh] BYREF
  int v27; // [rsp+48h] [rbp-B8h] BYREF
  int v28; // [rsp+4Ch] [rbp-B4h] BYREF
  int v29; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v30; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *Src; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *Destination; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v33; // [rsp+70h] [rbp-90h]
  CWriterGlobalHelper *v34; // [rsp+78h] [rbp-88h]
  _QWORD v35[2]; // [rsp+80h] [rbp-80h] BYREF
  _DWORD v36[4]; // [rsp+90h] [rbp-70h] BYREF
  int v37; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v38; // [rsp+A4h] [rbp-5Ch]
  int v39; // [rsp+ACh] [rbp-54h]
  __int128 v40; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t *Source[2]; // [rsp+C0h] [rbp-40h]
  __int128 v42; // [rsp+D0h] [rbp-30h]
  _QWORD v43[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v44; // [rsp+F0h] [rbp-10h]
  int *v45; // [rsp+100h] [rbp+0h]
  __int64 v46; // [rsp+108h] [rbp+8h]

  v5 = 0;
  v34 = (CWriterGlobalHelper *)this;
  v35[0] = a4;
  v6 = (CWriterGlobalHelper *)this;
  v43[0] = a4;
  v26 = 0;
  v35[1] = &a5;
  v37 = 4;
  v36[2] = 4;
  v7 = this[5];
  v8 = a4;
  v43[1] = &a5;
  v25 = 0;
  v45 = &v28;
  v27 = 0;
  Src = 0;
  v38 = 2;
  v39 = 1;
  v40 = 0;
  v29 = 8;
  *(_OWORD *)Source = 0;
  v30 = 0;
  v42 = 0;
  v28 = 0;
  v36[0] = 0;
  v36[1] = 1;
  v44 = 0;
  v46 = 0;
  v11 = *v7;
  v33 = a4;
  result = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD *, unsigned int *))(v11 + 24))(v7, 0, v35, &v25);
  if ( (int)result < 0 )
  {
    if ( (_DWORD)result != -2145318890 )
      return result;
    goto LABEL_41;
  }
  result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, int *, _QWORD, _DWORD **))(**((_QWORD **)v6 + 5) + 32LL))(
             *((_QWORD *)v6 + 5),
             v25,
             1,
             &v29,
             0,
             &v30);
  if ( (int)result < 0 )
    return result;
  if ( (~(a2 & *v30) & a2) != 0 )
  {
LABEL_41:
    v13 = a2;
    return UnsignedLongToNewString(v13, a3);
  }
  if ( a2 )
  {
    v16 = 1024;
    result = NewString(0x400u, a3);
    if ( (int)result < 0 )
      return result;
    result = CWriterGlobalHelper::GetStartRowIndex(v6, v8, a5, &v26);
    if ( (int)result < 0 )
      return result;
    v17 = v26;
    if ( v26 == -1 )
      return result;
    while ( 1 )
    {
      v18 = *((_QWORD *)v6 + 2);
      v25 = v17;
      result = (*(__int64 (__fastcall **)(__int64, __int64, __int64, int *, _QWORD, __int128 *))(*(_QWORD *)v18 + 32LL))(
                 v18,
                 v17,
                 4,
                 &v37,
                 0,
                 &v40);
      if ( !a2 || (_DWORD)result == -2145318890 || a5 != **((_DWORD **)&v40 + 1) )
        return 0;
      v19 = v8;
      do
      {
        v20 = *(unsigned __int16 *)((char *)v19 + v40 - (_QWORD)v8);
        v21 = *v19 - v20;
        if ( v21 )
          break;
        ++v19;
      }
      while ( v20 );
      if ( v21 )
        return 0;
      if ( (int)result < 0 )
        return result;
      if ( (a2 & *(_DWORD *)v42) != 0 )
        break;
LABEL_38:
      v17 = v25 + 1;
    }
    v22 = -1;
    do
      ++v22;
    while ( Source[0][v22] );
    if ( (int)v22 + v5 + 3 <= v16 )
    {
      if ( !a3 )
      {
LABEL_37:
        v6 = v34;
        a2 &= ~*(_DWORD *)v42;
        goto LABEL_38;
      }
    }
    else
    {
      Destination = 0;
      v16 += v22 + 1027;
      result = NewString(v16, &Destination);
      if ( (int)result < 0 )
        return result;
      v23 = Destination;
      if ( *a3 )
      {
        wcscpy_s(Destination, v16, *a3);
        CoTaskMemFree(*a3);
      }
      *a3 = v23;
      v8 = v33;
    }
    v24 = *a3;
    if ( *a3 && *v24 )
    {
      wcscat_s(v24, v16, L" | ");
      v5 += 3;
    }
    if ( *a3 )
    {
      wcscat_s(*a3, v16, Source[0]);
      v5 += v22;
    }
    goto LABEL_37;
  }
  result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _DWORD *, _QWORD, _QWORD *, unsigned int *))(**((_QWORD **)v6 + 1) + 56LL))(
             *((_QWORD *)v6 + 1),
             v26,
             3,
             v36,
             0,
             v43,
             &v25);
  if ( (_DWORD)result == -2145318890 )
  {
    v13 = 0;
    return UnsignedLongToNewString(v13, a3);
  }
  if ( (int)result >= 0 )
  {
    v14 = *((_QWORD *)v6 + 1);
    v27 = 2;
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, int *, _QWORD, unsigned __int16 **))(*(_QWORD *)v14 + 32LL))(
               v14,
               v25,
               1,
               &v27,
               0,
               &Src);
    if ( (int)result >= 0 )
    {
      v15 = -1;
      do
        ++v15;
      while ( Src[v15] );
      return StringToNewString(Src, v15, a3);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002c604  push    rbp
0x18002c606  push    rbx
0x18002c607  push    rsi
0x18002c608  push    rdi
0x18002c609  push    r12
0x18002c60b  push    r13
0x18002c60d  push    r14
0x18002c60f  push    r15
0x18002c611  lea     rbp, [rsp-28h]
0x18002c616  sub     rsp, 128h
0x18002c61d  mov     rax, cs:__security_cookie
0x18002c624  xor     rax, rsp
0x18002c627  mov     [rbp+60h+var_50], rax
0x18002c62b  xor     r12d, r12d
0x18002c62e  mov     [rsp+160h+var_E8], rcx
0x18002c633  xorps   xmm0, xmm0
0x18002c636  mov     [rbp+60h+var_E0], r9
0x18002c63a  mov     r15, rcx
0x18002c63d  mov     [rbp+60h+var_80], r9
0x18002c641  lea     rax, [rbp+60h+arg_20]
0x18002c648  mov     [rsp+160h+var_11C], r12d
0x18002c64d  mov     [rbp+60h+var_D8], rax
0x18002c651  lea     ecx, [r12+4]
0x18002c656  lea     edi, [rcx-3]
0x18002c659  mov     [rbp+60h+var_C0], ecx
0x18002c65c  mov     [rbp+60h+var_C8], ecx
0x18002c65f  lea     rax, [rbp+60h+arg_20]
0x18002c666  mov     rcx, [r15+28h]
0x18002c66a  mov     r13, r9
0x18002c66d  mov     [rbp+60h+var_78], rax
0x18002c671  mov     rbx, r8
0x18002c674  lea     rax, [rsp+160h+var_114]
0x18002c679  mov     [rsp+160h+var_120], r12d
0x18002c67e  mov     [rbp+60h+var_60], rax
0x18002c682  lea     r8, [rbp+60h+var_E0]
0x18002c686  mov     [rsp+160h+var_118], r12d
0x18002c68b  mov     esi, edx
0x18002c68d  mov     [rsp+160h+Src], r12
0x18002c692  xor     edx, edx
0x18002c694  mov     [rbp+60h+var_BC], 2
0x18002c69c  mov     [rbp+60h+var_B4], edi
0x18002c69f  movups  [rbp+60h+var_B0], xmm0
0x18002c6a3  mov     [rsp+160h+var_110], 8
0x18002c6ab  movups  xmmword ptr [rbp+60h+Source], xmm0
0x18002c6af  mov     [rsp+160h+var_108], r12
0x18002c6b4  movups  [rbp+60h+var_90], xmm0
0x18002c6b8  mov     [rsp+160h+var_114], r12d
0x18002c6bd  mov     [rbp+60h+var_D0], r12d
0x18002c6c1  mov     [rbp+60h+var_CC], edi
0x18002c6c4  movdqu  [rbp+60h+var_70], xmm0
0x18002c6c9  mov     [rbp+60h+var_58], r12
0x18002c6cd  mov     rax, [rcx]
0x18002c6d0  mov     [rsp+160h+var_F0], r9
0x18002c6d5  lea     r9, [rsp+160h+var_120]
0x18002c6da  mov     rax, [rax+18h]
0x18002c6de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c6e3  test    eax, eax
0x18002c6e5  js      loc_18002C995
0x18002c6eb  mov     rcx, [r15+28h]
0x18002c6ef  lea     rdx, [rsp+160h+var_108]
0x18002c6f4  mov     [rsp+160h+var_138], rdx
0x18002c6f9  lea     r9, [rsp+160h+var_110]
0x18002c6fe  mov     edx, [rsp+160h+var_120]
0x18002c702  mov     r8d, edi
0x18002c705  mov     [rsp+160h+var_140], r12
0x18002c70a  mov     rax, [rcx]
0x18002c70d  mov     rax, [rax+20h]
0x18002c711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c716  test    eax, eax
0x18002c718  js      loc_18002C9A6
0x18002c71e  mov     rax, [rsp+160h+var_108]
0x18002c723  mov     ecx, [rax]
0x18002c725  and     ecx, esi
0x18002c727  not     ecx
0x18002c729  test    esi, ecx
0x18002c72b  jnz     loc_18002C99C
0x18002c731  test    esi, esi
0x18002c733  jnz     loc_18002C7E1
0x18002c739  mov     rcx, [r15+8]
0x18002c73d  lea     rdx, [rsp+160h+var_120]
0x18002c742  mov     [rsp+160h+var_130], rdx
0x18002c747  lea     r9, [rbp+60h+var_D0]
0x18002c74b  lea     rdx, [rbp+60h+var_80]
0x18002c74f  mov     [rsp+160h+var_138], rdx
0x18002c754  lea     r8d, [r12+3]
0x18002c759  mov     rax, [rcx]
0x18002c75c  mov     edx, [rsp+160h+var_11C]
0x18002c760  mov     [rsp+160h+var_140], r12
0x18002c765  mov     rax, [rax+38h]
0x18002c769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c76e  cmp     eax, 80210816h
0x18002c773  jnz     short loc_18002C77C
0x18002c775  xor     ecx, ecx
0x18002c777  jmp     loc_18002C99E
0x18002c77c  test    eax, eax
0x18002c77e  js      loc_18002C9A6
0x18002c784  mov     rcx, [r15+8]
0x18002c788  lea     rdx, [rsp+160h+Src]
0x18002c78d  mov     [rsp+160h+var_138], rdx
0x18002c792  lea     r9, [rsp+160h+var_118]
0x18002c797  mov     edx, [rsp+160h+var_120]
0x18002c79b  mov     r8d, edi
0x18002c79e  mov     [rsp+160h+var_118], 2
0x18002c7a6  mov     rax, [rcx]
0x18002c7a9  mov     [rsp+160h+var_140], r12
0x18002c7ae  mov     rax, [rax+20h]
0x18002c7b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7b7  test    eax, eax
0x18002c7b9  js      loc_18002C9A6
0x18002c7bf  mov     rcx, [rsp+160h+Src]; Src
0x18002c7c4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002c7c8  inc     rdi
0x18002c7cb  cmp     [rcx+rdi*2], r12w
0x18002c7d0  jnz     short loc_18002C7C8
0x18002c7d2  mov     r8, rbx; unsigned __int16 **
0x18002c7d5  mov     edx, edi; unsigned int
0x18002c7d7  call    ?StringToNewString@@YAJPEAGKPEAPEAG@Z; StringToNewString(ushort *,ulong,ushort * *)
0x18002c7dc  jmp     loc_18002C9A6
0x18002c7e1  mov     r14d, 400h
0x18002c7e7  mov     rdx, rbx; unsigned __int16 **
0x18002c7ea  mov     ecx, r14d; unsigned int
0x18002c7ed  call    ?NewString@@YAJKPEAPEAG@Z; NewString(ulong,ushort * *)
0x18002c7f2  test    eax, eax
0x18002c7f4  js      loc_18002C9A6
0x18002c7fa  mov     r8d, [rbp+60h+arg_20]; unsigned int
0x18002c801  lea     r9, [rsp+160h+var_11C]; unsigned int *
0x18002c806  mov     rdx, r13; unsigned __int16 *
0x18002c809  mov     rcx, r15; this
0x18002c80c  call    ?GetStartRowIndex@CWriterGlobalHelper@@AEAAJPEAGKPEAK@Z; CWriterGlobalHelper::GetStartRowIndex(ushort *,ulong,ulong *)
0x18002c811  test    eax, eax
0x18002c813  js      loc_18002C9A6
0x18002c819  mov     edx, [rsp+160h+var_11C]
0x18002c81d  cmp     edx, 0FFFFFFFFh
0x18002c820  jz      loc_18002C9A6
0x18002c826  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002c82a  xor     r10d, r10d
0x18002c82d  mov     rcx, [r15+10h]
0x18002c831  lea     r8, [rbp+60h+var_B0]
0x18002c835  mov     [rsp+160h+var_138], r8
0x18002c83a  lea     r9, [rbp+60h+var_C0]
0x18002c83e  mov     [rsp+160h+var_120], edx
0x18002c842  mov     r8d, 4
0x18002c848  mov     [rsp+160h+var_140], r10
0x18002c84d  mov     rax, [rcx]
0x18002c850  mov     rax, [rax+20h]
0x18002c854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c859  xor     r10d, r10d
0x18002c85c  test    esi, esi
0x18002c85e  jz      loc_18002C991
0x18002c864  cmp     eax, 80210816h
0x18002c869  jz      loc_18002C991
0x18002c86f  mov     rcx, qword ptr [rbp+60h+var_B0+8]
0x18002c873  mov     edx, [rcx]
0x18002c875  cmp     [rbp+60h+arg_20], edx
0x18002c87b  jnz     loc_18002C991
0x18002c881  mov     r9, qword ptr [rbp+60h+var_B0]
0x18002c885  mov     rcx, r13
0x18002c888  sub     r9, r13
0x18002c88b  movzx   r8d, word ptr [rcx]
0x18002c88f  movzx   edx, word ptr [rcx+r9]
0x18002c894  sub     r8d, edx
0x18002c897  jnz     short loc_18002C8A1
0x18002c899  add     rcx, 2
0x18002c89d  test    edx, edx
0x18002c89f  jnz     short loc_18002C88B
0x18002c8a1  test    r8d, r8d
0x18002c8a4  jnz     loc_18002C991
0x18002c8aa  test    eax, eax
0x18002c8ac  js      loc_18002C9A6
0x18002c8b2  mov     rax, qword ptr [rbp+60h+var_90]
0x18002c8b6  test    [rax], esi
0x18002c8b8  jz      loc_18002C986
0x18002c8be  mov     rax, [rbp+60h+Source]
0x18002c8c2  mov     r15, rdi
0x18002c8c5  inc     r15
0x18002c8c8  cmp     [rax+r15*2], r10w
0x18002c8cd  jnz     short loc_18002C8C5
0x18002c8cf  lea     eax, [r12+3]
0x18002c8d4  add     eax, r15d
0x18002c8d7  cmp     eax, r14d
0x18002c8da  jbe     short loc_18002C932
0x18002c8dc  add     r14d, 403h
0x18002c8e3  mov     [rsp+160h+Destination], r10
0x18002c8e8  add     r14d, r15d
0x18002c8eb  lea     rdx, [rsp+160h+Destination]; unsigned __int16 **
0x18002c8f0  mov     ecx, r14d; unsigned int
0x18002c8f3  call    ?NewString@@YAJKPEAPEAG@Z; NewString(ulong,ushort * *)
0x18002c8f8  xor     r10d, r10d
0x18002c8fb  test    eax, eax
0x18002c8fd  js      loc_18002C9A6
0x18002c903  mov     r8, [rbx]; Source
0x18002c906  mov     r13, [rsp+160h+Destination]
0x18002c90b  test    r8, r8
0x18002c90e  jz      short loc_18002C928
0x18002c910  mov     edx, r14d; SizeInWords
0x18002c913  mov     rcx, r13; Destination
0x18002c916  call    cs:__imp_wcscpy_s
0x18002c91c  mov     rcx, [rbx]; pv
0x18002c91f  call    cs:__imp_CoTaskMemFree
0x18002c925  xor     r10d, r10d
0x18002c928  mov     [rbx], r13
0x18002c92b  mov     r13, [rsp+160h+var_F0]
0x18002c930  jmp     short loc_18002C937
0x18002c932  test    rbx, rbx
0x18002c935  jz      short loc_18002C977
0x18002c937  mov     rcx, [rbx]; Destination
0x18002c93a  test    rcx, rcx
0x18002c93d  jz      short loc_18002C95C
0x18002c93f  cmp     [rcx], r10w
0x18002c943  jz      short loc_18002C95C
0x18002c945  mov     edx, r14d; SizeInWords
0x18002c948  lea     r8, asc_18003CA30; " | "
0x18002c94f  call    cs:__imp_wcscat_s
0x18002c955  add     r12d, 3
0x18002c959  xor     r10d, r10d
0x18002c95c  mov     rcx, [rbx]; Destination
0x18002c95f  test    rcx, rcx
0x18002c962  jz      short loc_18002C977
0x18002c964  mov     r8, [rbp+60h+Source]; Source
0x18002c968  mov     edx, r14d; SizeInWords
0x18002c96b  call    cs:__imp_wcscat_s
0x18002c971  add     r12d, r15d
0x18002c974  xor     r10d, r10d
0x18002c977  mov     rax, qword ptr [rbp+60h+var_90]
0x18002c97b  mov     r15, [rsp+160h+var_E8]
0x18002c980  mov     ecx, [rax]
0x18002c982  not     ecx
0x18002c984  and     esi, ecx
0x18002c986  mov     edx, [rsp+160h+var_120]
0x18002c98a  inc     edx
0x18002c98c  jmp     loc_18002C82D
0x18002c991  xor     eax, eax
0x18002c993  jmp     short loc_18002C9A6
0x18002c995  cmp     eax, 80210816h
0x18002c99a  jnz     short loc_18002C9A6
0x18002c99c  mov     ecx, esi; unsigned int
0x18002c99e  mov     rdx, rbx; unsigned __int16 **
0x18002c9a1  call    ?UnsignedLongToNewString@@YAJKPEAPEAG@Z; UnsignedLongToNewString(ulong,ushort * *)
0x18002c9a6  mov     rcx, [rbp+60h+var_50]
0x18002c9aa  xor     rcx, rsp; StackCookie
0x18002c9ad  call    __security_check_cookie
0x18002c9b2  add     rsp, 128h
0x18002c9b9  pop     r15
0x18002c9bb  pop     r14
0x18002c9bd  pop     r13
0x18002c9bf  pop     r12
0x18002c9c1  pop     rdi
0x18002c9c2  pop     rsi
0x18002c9c3  pop     rbx
0x18002c9c4  pop     rbp
0x18002c9c5  retn
```
