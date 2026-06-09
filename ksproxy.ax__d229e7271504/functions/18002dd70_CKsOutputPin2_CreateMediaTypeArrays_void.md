# CKsOutputPin2::CreateMediaTypeArrays(void)

- ea: `0x18002dd70`
- end: `0x18002dff1`
- name: `?CreateMediaTypeArrays@CKsOutputPin2@@QEAAJXZ`
- size: `641`
- prototype: `__int64 __fastcall(CKsOutputPin2 *__hidden this)`
- caller_count: `6`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18002da70`
- `0x18002f8d0`
- `0x18002f9d0`
- `0x18002fa50`
- `0x180031360`
- `0x1800315e0`

## callees

- `0x1800043d0`
- `0x180004f70`
- `0x18001f1c4`
- `0x18001f1d0`
- `0x18001f210`
- `0x18001ffb0`
- `0x18002dd70`
- `0x18002f2b8`
- `0x1800389a0`
- `0x18003e22c`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall CKsOutputPin2::CreateMediaTypeArrays(CKsOutputPin2 *this)
{
  _DWORD *v1; // rsi
  int v3; // r13d
  int MediaTypeCount; // ebx
  unsigned int v5; // ebx
  char *v6; // rax
  _DWORD *v7; // r15
  void *v8; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // r14
  int v11; // ebp
  __int64 i; // r12
  int v13; // ebx
  char *v14; // rax
  unsigned __int64 v15; // rdx
  void *v16; // rax
  GUID *v17; // r9
  void *v18; // rcx
  __int64 j; // r12
  void *v20; // rcx
  struct _AMMediaType *pv; // [rsp+80h] [rbp+8h] BYREF

  v1 = (_DWORD *)((char *)this + 1200);
  v3 = 1;
  if ( !*((_QWORD *)this + 141) || *v1 )
  {
    MediaTypeCount = 0;
    goto LABEL_27;
  }
  CKsOutputPin2::DestroyMediaTypeArrays(this);
  v5 = *((_DWORD *)this + 146);
  v6 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 10) + 168LL) + 24LL))(*((_QWORD *)this + 10) + 168LL);
  v7 = (_DWORD *)((char *)this + 1176);
  MediaTypeCount = KsGetMediaTypeCount(v6, v5, (_DWORD *)this + 294);
  if ( MediaTypeCount < 0 )
  {
LABEL_29:
    CKsOutputPin2::DestroyMediaTypeArrays(this);
    v3 = 0;
    goto LABEL_30;
  }
  v8 = operator new[](saturated_mul((unsigned int)*v7, 8u));
  *((_QWORD *)this + 146) = v8;
  if ( !v8
    || (memset_0(v8, 0, 8LL * (unsigned int)*v7),
        v9 = operator new[](saturated_mul((unsigned int)*v7, 8u)),
        (v10 = v9) == 0) )
  {
    MediaTypeCount = -2147024882;
    goto LABEL_29;
  }
  v11 = 0;
  memset_0(v9, 0, 8LL * (unsigned int)*v7);
  for ( i = 0; (unsigned int)i < *v7; i = (unsigned int)(i + 1) )
  {
    v13 = *((_DWORD *)this + 146);
    v14 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 10) + 168LL) + 24LL))(*((_QWORD *)this + 10) + 168LL);
    MediaTypeCount = KsGetDriverMediaType(i, (union KSDATAFORMAT **)(*((_QWORD *)this + 146) + 8 * i), v14, v13);
    if ( MediaTypeCount < 0 )
      goto LABEL_21;
    v16 = operator new(0x80u);
    v10[i] = v16;
    if ( !v16 )
    {
      MediaTypeCount = -2147024882;
      goto LABEL_21;
    }
    memset_0(v16, 0, 0x80u);
    v17 = (GUID *)v10[i];
    pv = 0;
    MediaTypeCount = CKsOutputPin::GetStreamCaps((CKsOutputPin *)((char *)this + 440), i, &pv, v17);
    if ( MediaTypeCount < 0 )
    {
      v18 = (void *)v10[i];
      if ( v18 )
      {
        operator delete(v18, 0x80u);
        v10[i] = 0;
      }
    }
    DeleteMediaType(pv);
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *, _QWORD))(**((_QWORD **)this + 141) + 24LL))(
          *((_QWORD *)this + 141),
          *((_QWORD *)this + 146),
          v10,
          (unsigned int)*v7);
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, char *, char *, _DWORD *))(**((_QWORD **)this + 141) + 40LL))(
            *((_QWORD *)this + 141),
            (char *)this + 1184,
            (char *)this + 1192,
            v1);
    if ( v11 >= 0 && !*v1 )
      v11 = -2147467259;
  }
LABEL_21:
  for ( j = 0; (unsigned int)j < *v7; j = (unsigned int)(j + 1) )
  {
    v20 = (void *)v10[j];
    if ( v20 )
    {
      operator delete(v20, 0x80u);
      v10[j] = 0;
    }
  }
  operator delete(v10, v15);
  if ( MediaTypeCount < 0 || v11 < 0 )
    goto LABEL_29;
LABEL_27:
  if ( !*v1 || !*((_QWORD *)this + 141) )
    goto LABEL_29;
LABEL_30:
  *((_DWORD *)this + 286) = v3;
  return (unsigned int)MediaTypeCount;
}

```

## disassembly

```asm
0x18002dd70  push    rbx
0x18002dd72  push    rbp
0x18002dd73  push    rsi
0x18002dd74  push    rdi
0x18002dd75  push    r12
0x18002dd77  push    r13
0x18002dd79  push    r14
0x18002dd7b  push    r15
0x18002dd7d  sub     rsp, 38h
0x18002dd81  cmp     qword ptr [rcx+468h], 0
0x18002dd89  lea     rsi, [rcx+4B0h]
0x18002dd90  mov     rdi, rcx
0x18002dd93  mov     r13d, 1
0x18002dd99  jnz     short loc_18002DDA2
0x18002dd9b  xor     ebx, ebx
0x18002dd9d  jmp     loc_18002DFBC
0x18002dda2  cmp     dword ptr [rsi], 0
0x18002dda5  ja      short loc_18002DD9B
0x18002dda7  call    ?DestroyMediaTypeArrays@CKsOutputPin2@@QEAAXXZ; CKsOutputPin2::DestroyMediaTypeArrays(void)
0x18002ddac  mov     rcx, [rdi+50h]
0x18002ddb0  mov     ebx, [rdi+248h]
0x18002ddb6  add     rcx, 0A8h
0x18002ddbd  mov     rax, [rcx]
0x18002ddc0  mov     rax, [rax+18h]
0x18002ddc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddc9  lea     r15, [rdi+498h]
0x18002ddd0  mov     edx, ebx
0x18002ddd2  mov     r8, r15
0x18002ddd5  mov     rcx, rax; hFile
0x18002ddd8  call    KsGetMediaTypeCount
0x18002dddd  mov     ebx, eax
0x18002dddf  test    eax, eax
0x18002dde1  js      loc_18002DFCB
0x18002dde7  mov     ecx, [r15]
0x18002ddea  mov     ebp, 8
0x18002ddef  mov     eax, ebp
0x18002ddf1  mul     rcx
0x18002ddf4  lea     r14, [rbp-9]
0x18002ddf8  cmovb   rax, r14
0x18002ddfc  mov     rcx, rax; unsigned __int64
0x18002ddff  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002de04  mov     [rdi+490h], rax
0x18002de0b  test    rax, rax
0x18002de0e  jnz     short loc_18002DE1A
0x18002de10  mov     ebx, 8007000Eh
0x18002de15  jmp     loc_18002DFCB
0x18002de1a  mov     r8d, [r15]
0x18002de1d  xor     edx, edx; Val
0x18002de1f  shl     r8, 3; Size
0x18002de23  mov     rcx, rax; void *
0x18002de26  call    memset_0
0x18002de2b  mov     ecx, [r15]
0x18002de2e  mov     rax, rbp
0x18002de31  mul     rcx
0x18002de34  cmovb   rax, r14
0x18002de38  mov     rcx, rax; unsigned __int64
0x18002de3b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002de40  mov     r14, rax
0x18002de43  test    rax, rax
0x18002de46  jz      short loc_18002DE10
0x18002de48  mov     r8d, [r15]
0x18002de4b  xor     edx, edx; Val
0x18002de4d  shl     r8, 3; Size
0x18002de51  mov     rcx, rax; void *
0x18002de54  xor     ebp, ebp
0x18002de56  call    memset_0
0x18002de5b  xor     r12d, r12d
0x18002de5e  cmp     r12d, [r15]
0x18002de61  jnb     loc_18002DF26
0x18002de67  mov     rcx, [rdi+50h]
0x18002de6b  mov     ebx, [rdi+248h]
0x18002de71  add     rcx, 0A8h
0x18002de78  mov     rax, [rcx]
0x18002de7b  mov     rax, [rax+18h]
0x18002de7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de84  mov     rcx, [rdi+490h]
0x18002de8b  mov     r9d, ebx; unsigned int
0x18002de8e  mov     r8, rax; void *
0x18002de91  lea     rdx, [rcx+r12*8]; union KSDATAFORMAT **
0x18002de95  mov     ecx, r12d; int
0x18002de98  call    ?KsGetDriverMediaType@@YAJHPEAPEATKSDATAFORMAT@@PEAXK@Z; KsGetDriverMediaType(int,KSDATAFORMAT * *,void *,ulong)
0x18002de9d  mov     ebx, eax
0x18002de9f  test    eax, eax
0x18002dea1  js      loc_18002DF81
0x18002dea7  mov     ecx, 80h; Size
0x18002deac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002deb1  mov     [r14+r12*8], rax
0x18002deb5  test    rax, rax
0x18002deb8  jz      short loc_18002DF1F
0x18002deba  xor     edx, edx; Val
0x18002debc  mov     r8d, 80h; Size
0x18002dec2  mov     rcx, rax; void *
0x18002dec5  call    memset_0
0x18002deca  mov     r9, [r14+r12*8]; unsigned __int8 *
0x18002dece  lea     rcx, [rdi+1B8h]; this
0x18002ded5  lea     r8, [rsp+78h+pv]; struct _AMMediaType **
0x18002dedd  mov     [rsp+78h+pv], rbp
0x18002dee5  mov     edx, r12d; int
0x18002dee8  call    ?GetStreamCaps@CKsOutputPin@@UEAAJHPEAPEAU_AMMediaType@@PEAE@Z; CKsOutputPin::GetStreamCaps(int,_AMMediaType * *,uchar *)
0x18002deed  mov     ebx, eax
0x18002deef  test    eax, eax
0x18002def1  jns     short loc_18002DF0A
0x18002def3  mov     rcx, [r14+r12*8]; void *
0x18002def7  test    rcx, rcx
0x18002defa  jz      short loc_18002DF0A
0x18002defc  mov     edx, 80h; unsigned __int64
0x18002df01  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002df06  mov     [r14+r12*8], rbp
0x18002df0a  mov     rcx, [rsp+78h+pv]; pv
0x18002df12  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x18002df17  add     r12d, r13d
0x18002df1a  jmp     loc_18002DE5E
0x18002df1f  mov     ebx, 8007000Eh
0x18002df24  jmp     short loc_18002DF81
0x18002df26  mov     rcx, [rdi+468h]
0x18002df2d  mov     r8, r14
0x18002df30  mov     r9d, [r15]
0x18002df33  mov     rdx, [rdi+490h]
0x18002df3a  mov     rax, [rcx]
0x18002df3d  mov     rax, [rax+18h]
0x18002df41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df46  mov     ebp, eax
0x18002df48  test    eax, eax
0x18002df4a  js      short loc_18002DF81
0x18002df4c  mov     rcx, [rdi+468h]
0x18002df53  lea     r8, [rdi+4A8h]
0x18002df5a  lea     rdx, [rdi+4A0h]
0x18002df61  mov     r9, rsi
0x18002df64  mov     rax, [rcx]
0x18002df67  mov     rax, [rax+28h]
0x18002df6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df70  mov     ebp, eax
0x18002df72  test    eax, eax
0x18002df74  js      short loc_18002DF81
0x18002df76  cmp     dword ptr [rsi], 0
0x18002df79  mov     eax, 80004005h
0x18002df7e  cmovz   ebp, eax
0x18002df81  xor     r12d, r12d
0x18002df84  cmp     [r15], r12d
0x18002df87  jbe     short loc_18002DFAC
0x18002df89  mov     rcx, [r14+r12*8]; void *
0x18002df8d  test    rcx, rcx
0x18002df90  jz      short loc_18002DFA4
0x18002df92  mov     edx, 80h; unsigned __int64
0x18002df97  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002df9c  mov     qword ptr [r14+r12*8], 0
0x18002dfa4  add     r12d, r13d
0x18002dfa7  cmp     r12d, [r15]
0x18002dfaa  jb      short loc_18002DF89
0x18002dfac  mov     rcx, r14; void *
0x18002dfaf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002dfb4  test    ebx, ebx
0x18002dfb6  js      short loc_18002DFCB
0x18002dfb8  test    ebp, ebp
0x18002dfba  js      short loc_18002DFCB
0x18002dfbc  cmp     dword ptr [rsi], 0
0x18002dfbf  jbe     short loc_18002DFCB
0x18002dfc1  cmp     qword ptr [rdi+468h], 0
0x18002dfc9  jnz     short loc_18002DFD6
0x18002dfcb  mov     rcx, rdi; this
0x18002dfce  call    ?DestroyMediaTypeArrays@CKsOutputPin2@@QEAAXXZ; CKsOutputPin2::DestroyMediaTypeArrays(void)
0x18002dfd3  xor     r13d, r13d
0x18002dfd6  mov     [rdi+478h], r13d
0x18002dfdd  mov     eax, ebx
0x18002dfdf  add     rsp, 38h
0x18002dfe3  pop     r15
0x18002dfe5  pop     r14
0x18002dfe7  pop     r13
0x18002dfe9  pop     r12
0x18002dfeb  pop     rdi
0x18002dfec  pop     rsi
0x18002dfed  pop     rbp
0x18002dfee  pop     rbx
0x18002dfef  retn
```
