# CSecConLib::ListWebServiceExtensions(ushort const *,ushort * *,ulong *)

- ea: `0x18000f674`
- end: `0x18000f900`
- name: `?ListWebServiceExtensions@CSecConLib@@QEAAJPEBGPEAPEAGPEAK@Z`
- size: `652`
- prototype: `__int64 __fastcall(CSecConLib *__hidden this, const unsigned __int16 *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x1800097b0`

## callees

- `0x180001048`
- `0x180001054`
- `0x18000f02c`
- `0x18000f1c0`
- `0x18000f674`
- `0x1800111a2`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18000f83c`
- `msvcrt!wcscpy_s` at `0x18000f83c`
- `msvcrt!_wcsicmp` at `0x18000f7a5`
- `msvcrt!_wcsicmp` at `0x18000f7a5`
- `msvcrt!wcschr` at `0x18000f728`
- `msvcrt!wcschr` at `0x18000f77c`
- `msvcrt!wcschr` at `0x18000f728`
- `msvcrt!wcschr` at `0x18000f77c`

## pseudocode

```c
__int64 __fastcall CSecConLib::ListWebServiceExtensions(
        CSecConLib *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned int *a4)
{
  int inited; // ebx
  wchar_t *v7; // rdi
  wchar_t *v8; // r12
  wchar_t *v9; // r14
  unsigned int v10; // r13d
  wchar_t *v11; // rbp
  int v12; // r15d
  wchar_t *v13; // rax
  wchar_t *v14; // rsi
  char v15; // al
  wchar_t *v16; // rax
  const wchar_t *i; // r15
  __int64 v18; // rax
  __int64 v19; // rax
  int v20; // ebp
  wchar_t *v21; // rax
  wchar_t *v22; // r15
  __int64 v23; // rax
  wchar_t *Str; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v26[16]; // [rsp+38h] [rbp-40h] BYREF

  Str = 0;
  v26[0] = 0;
  inited = CSecConLib::InternalInitIfNecessary(this);
  if ( inited >= 0 )
  {
    inited = CSecConLib::GetMultiSZPropVal(this, a2, 0x878u, &Str, v26);
    if ( inited >= 0 )
    {
      v7 = Str;
      if ( !Str )
        return (unsigned int)-2147024882;
      v8 = Str;
      if ( !*Str )
        goto LABEL_35;
      v9 = 0;
      v10 = 1;
      LODWORD(Str) = 1;
      v11 = v7;
      *(_QWORD *)v26 = &v7[v26[0] - 1];
      while ( 1 )
      {
        v12 = 0;
        while ( 1 )
        {
          v13 = wcschr(v7, 0x2Cu);
          if ( !v13 )
            break;
          v14 = v13 + 1;
          ++v12;
          *v13 = 0;
          v7 = v13 + 1;
          v11 = v13 + 1;
          if ( v12 >= 3 )
          {
            v15 = 0;
            goto LABEL_12;
          }
        }
        v14 = v11;
        v15 = 1;
LABEL_12:
        if ( *v14 != 44 && !v15 )
        {
          v16 = wcschr(v7, 0x2Cu);
          v14 = v16;
          if ( v16 )
          {
            *v16 = 0;
            v14 = v16 + 1;
          }
          for ( i = v9; i; i += (unsigned int)(v18 + 1) )
          {
            if ( !*i )
              break;
            if ( !_wcsicmp(i, v7) )
              goto LABEL_28;
            v18 = -1;
            do
              ++v18;
            while ( i[v18] );
          }
          v19 = -1;
          do
            ++v19;
          while ( v7[v19] );
          v20 = v19 + v10;
          v10 += v19 + 1;
          v21 = (wchar_t *)operator new[](saturated_mul((unsigned int)(v20 + 1), 2u));
          v22 = v21;
          if ( !v21 )
          {
            inited = -2147024882;
            goto LABEL_39;
          }
          if ( v9 )
          {
            memcpy_0(v21, v9, 2LL * (unsigned int)Str);
            operator delete(v9);
          }
          wcscpy_s(&v22[(_DWORD)Str - 1], v10 - (unsigned int)Str + 1, v7);
          LODWORD(Str) = v20 + 1;
          v9 = v22;
          v22[v20 - 1] = 0;
          v22[v20] = 0;
        }
LABEL_28:
        v23 = -1;
        do
          ++v23;
        while ( v14[v23] );
        v7 = &v14[(unsigned int)v23 + 1];
        if ( (unsigned __int64)v7 > *(_QWORD *)v26 || !*v7 )
          break;
        v11 = &v14[(unsigned int)v23 + 1];
      }
      if ( !v9 )
      {
LABEL_35:
        v9 = (wchar_t *)operator new[](4u);
        if ( !v9 )
        {
          inited = -2147024882;
LABEL_39:
          operator delete(v8);
          return (unsigned int)inited;
        }
        v10 = 2;
        *v9 = 0;
        v9[1] = 0;
      }
      *a3 = v9;
      *a4 = v10;
      goto LABEL_39;
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000f674  mov     rax, rsp
0x18000f677  mov     [rax+8], rbx
0x18000f67b  mov     [rax+20h], r9
0x18000f67f  mov     [rax+18h], r8
0x18000f683  push    rbp
0x18000f684  push    rsi
0x18000f685  push    rdi
0x18000f686  push    r12
0x18000f688  push    r13
0x18000f68a  push    r14
0x18000f68c  push    r15
0x18000f68e  sub     rsp, 40h
0x18000f692  xor     ebp, ebp
0x18000f694  mov     rsi, rdx
0x18000f697  mov     [rax-48h], rbp
0x18000f69b  mov     rdi, rcx
0x18000f69e  mov     [rax-40h], ebp
0x18000f6a1  call    ?InternalInitIfNecessary@CSecConLib@@AEAAJXZ; CSecConLib::InternalInitIfNecessary(void)
0x18000f6a6  mov     ebx, eax
0x18000f6a8  test    eax, eax
0x18000f6aa  js      loc_18000F8E6
0x18000f6b0  lea     rax, [rsp+78h+var_40]
0x18000f6b5  mov     r8d, 878h; unsigned int
0x18000f6bb  lea     r9, [rsp+78h+Str]; unsigned __int16 **
0x18000f6c0  mov     [rsp+78h+var_58], rax; unsigned int *
0x18000f6c5  mov     rdx, rsi; unsigned __int16 *
0x18000f6c8  mov     rcx, rdi; this
0x18000f6cb  call    ?GetMultiSZPropVal@CSecConLib@@AEAAJPEBGKPEAPEAGPEAK@Z; CSecConLib::GetMultiSZPropVal(ushort const *,ulong,ushort * *,ulong *)
0x18000f6d0  mov     ebx, eax
0x18000f6d2  test    eax, eax
0x18000f6d4  js      loc_18000F8E6
0x18000f6da  mov     rdi, [rsp+78h+Str]
0x18000f6df  test    rdi, rdi
0x18000f6e2  jnz     short loc_18000F6EE
0x18000f6e4  mov     ebx, 8007000Eh
0x18000f6e9  jmp     loc_18000F8E6
0x18000f6ee  mov     r12, rdi
0x18000f6f1  cmp     [rdi], bp
0x18000f6f4  jz      loc_18000F899
0x18000f6fa  mov     eax, 1
0x18000f6ff  mov     r14, rbp
0x18000f702  mov     r13d, eax
0x18000f705  mov     dword ptr [rsp+78h+Str], eax
0x18000f709  mov     eax, [rsp+78h+var_40]
0x18000f70d  mov     rbp, rdi
0x18000f710  dec     rax
0x18000f713  lea     ecx, [r13+2Bh]
0x18000f717  lea     rax, [rdi+rax*2]
0x18000f71b  mov     qword ptr [rsp+78h+var_40], rax
0x18000f720  xor     r15d, r15d
0x18000f723  mov     edx, ecx; Ch
0x18000f725  mov     rcx, rdi; Str
0x18000f728  call    cs:__imp_wcschr
0x18000f72e  mov     rsi, rax
0x18000f731  test    rax, rax
0x18000f734  jz      short loc_18000F75A
0x18000f736  xor     ecx, ecx
0x18000f738  add     rsi, 2
0x18000f73c  inc     r15d
0x18000f73f  mov     [rax], cx
0x18000f742  mov     ecx, 2Ch ; ','
0x18000f747  mov     rdi, rsi
0x18000f74a  mov     rbp, rsi
0x18000f74d  cmp     r15d, 3
0x18000f751  jl      short loc_18000F723
0x18000f753  xor     ebp, ebp
0x18000f755  mov     al, bpl
0x18000f758  jmp     short loc_18000F761
0x18000f75a  mov     rsi, rbp
0x18000f75d  mov     al, 1
0x18000f75f  xor     ebp, ebp
0x18000f761  mov     ecx, 2Ch ; ','
0x18000f766  cmp     cx, [rsi]
0x18000f769  jz      loc_18000F861
0x18000f76f  test    al, al
0x18000f771  jnz     loc_18000F861
0x18000f777  mov     edx, ecx; Ch
0x18000f779  mov     rcx, rdi; Str
0x18000f77c  call    cs:__imp_wcschr
0x18000f782  mov     rsi, rax
0x18000f785  test    rax, rax
0x18000f788  jz      short loc_18000F791
0x18000f78a  mov     [rax], bp
0x18000f78d  add     rsi, 2
0x18000f791  mov     r15, r14
0x18000f794  test    r14, r14
0x18000f797  jz      short loc_18000F7CC
0x18000f799  cmp     [r15], bp
0x18000f79d  jz      short loc_18000F7CC
0x18000f79f  mov     rdx, rdi; String2
0x18000f7a2  mov     rcx, r15; String1
0x18000f7a5  call    cs:__imp__wcsicmp
0x18000f7ab  test    eax, eax
0x18000f7ad  jz      loc_18000F85C
0x18000f7b3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f7b7  inc     rax
0x18000f7ba  cmp     [r15+rax*2], bp
0x18000f7bf  jnz     short loc_18000F7B7
0x18000f7c1  inc     eax
0x18000f7c3  lea     r15, [r15+rax*2]
0x18000f7c7  test    r15, r15
0x18000f7ca  jnz     short loc_18000F799
0x18000f7cc  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000f7d0  mov     rax, r8
0x18000f7d3  inc     rax
0x18000f7d6  cmp     [rdi+rax*2], bp
0x18000f7da  jnz     short loc_18000F7D3
0x18000f7dc  lea     ebp, [rax+r13]
0x18000f7e0  mov     eax, 2
0x18000f7e5  lea     r13d, [rbp+1]
0x18000f7e9  mov     ecx, r13d
0x18000f7ec  mul     rcx
0x18000f7ef  cmovb   rax, r8
0x18000f7f3  mov     rcx, rax; unsigned __int64
0x18000f7f6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000f7fb  mov     r15, rax
0x18000f7fe  test    rax, rax
0x18000f801  jz      loc_18000F88B
0x18000f807  test    r14, r14
0x18000f80a  jz      short loc_18000F827
0x18000f80c  mov     r8d, dword ptr [rsp+78h+Str]
0x18000f811  mov     rdx, r14; Src
0x18000f814  add     r8, r8; Size
0x18000f817  mov     rcx, rax; void *
0x18000f81a  call    memcpy_0
0x18000f81f  mov     rcx, r14; Block
0x18000f822  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f827  mov     ecx, dword ptr [rsp+78h+Str]
0x18000f82b  mov     edx, r13d
0x18000f82e  sub     edx, ecx
0x18000f830  mov     r8, rdi; Source
0x18000f833  inc     edx; SizeInWords
0x18000f835  lea     eax, [rcx-1]
0x18000f838  lea     rcx, [r15+rax*2]; Destination
0x18000f83c  call    cs:__imp_wcscpy_s
0x18000f842  mov     ecx, ebp
0x18000f844  lea     eax, [r13-2]
0x18000f848  xor     ebp, ebp
0x18000f84a  mov     dword ptr [rsp+78h+Str], r13d
0x18000f84f  mov     r14, r15
0x18000f852  mov     [r15+rax*2], bp
0x18000f857  mov     [r15+rcx*2], bp
0x18000f85c  mov     ecx, 2Ch ; ','
0x18000f861  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f865  inc     rax
0x18000f868  cmp     [rsi+rax*2], bp
0x18000f86c  jnz     short loc_18000F865
0x18000f86e  mov     edi, eax
0x18000f870  inc     rdi
0x18000f873  lea     rdi, [rsi+rdi*2]
0x18000f877  cmp     rdi, qword ptr [rsp+78h+var_40]
0x18000f87c  ja      short loc_18000F894
0x18000f87e  cmp     [rdi], bp
0x18000f881  jz      short loc_18000F894
0x18000f883  mov     rbp, rdi
0x18000f886  jmp     loc_18000F720
0x18000f88b  mov     ebx, 8007000Eh
0x18000f890  xor     ebp, ebp
0x18000f892  jmp     short loc_18000F8D9
0x18000f894  test    r14, r14
0x18000f897  jnz     short loc_18000F8C3
0x18000f899  mov     ecx, 4; unsigned __int64
0x18000f89e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000f8a3  mov     r14, rax
0x18000f8a6  test    rax, rax
0x18000f8a9  jnz     short loc_18000F8B2
0x18000f8ab  mov     ebx, 8007000Eh
0x18000f8b0  jmp     short loc_18000F8D9
0x18000f8b2  mov     eax, ebp
0x18000f8b4  mov     r13d, 2
0x18000f8ba  mov     [r14], ax
0x18000f8be  mov     [r14+2], ax
0x18000f8c3  mov     rax, [rsp+78h+arg_10]
0x18000f8cb  mov     [rax], r14
0x18000f8ce  mov     rax, [rsp+78h+arg_18]
0x18000f8d6  mov     [rax], r13d
0x18000f8d9  test    r12, r12
0x18000f8dc  jz      short loc_18000F8E6
0x18000f8de  mov     rcx, r12; Block
0x18000f8e1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f8e6  mov     eax, ebx
0x18000f8e8  mov     rbx, [rsp+78h+arg_0]
0x18000f8f0  add     rsp, 40h
0x18000f8f4  pop     r15
0x18000f8f6  pop     r14
0x18000f8f8  pop     r13
0x18000f8fa  pop     r12
0x18000f8fc  pop     rdi
0x18000f8fd  pop     rsi
0x18000f8fe  pop     rbp
0x18000f8ff  retn
```
