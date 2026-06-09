# CLMString::Assign(char const *,uint,uint)

- ea: `0x180022350`
- end: `0x18002247f`
- name: `?Assign@CLMString@@UEAAHPEBDII@Z`
- size: `303`
- prototype: `int(CLMString *__hidden this, const char *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180010c60`
- `0x180010c90`
- `0x180010dd4`
- `0x180013500`
- `0x180022350`
- `0x180022600`
- `0x180025010`

## string_xrefs

- `0x18002237a`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
__int64 __fastcall CLMString::Assign(CLMString *this, const char *a2, unsigned int a3, int a4)
{
  unsigned int v4; // ebx
  __int64 v8; // rax
  __int64 v9; // rax
  _DWORD *v10; // rax
  __int64 v11; // rdx
  void (__fastcall *v12)(CLMString *, _QWORD); // rdi
  unsigned __int64 v13; // rcx
  __int64 v14; // rax
  unsigned int *v15; // rax
  int *v16; // rax
  int v17; // r9d
  __int64 v19; // rcx
  int v20; // [rsp+20h] [rbp-10h] BYREF
  _BYTE v21[4]; // [rsp+24h] [rbp-Ch] BYREF
  __int64 v22; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  unsigned int v24; // [rsp+58h] [rbp+28h] BYREF

  v4 = a4;
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
      (const char *)0x80070057LL,
      v20);
  v24 = a3;
  v20 = a4;
  if ( a4 == -1 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    v22 = v8;
    SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator=<unsigned __int64>(
      &v20,
      &v22);
    v4 = v20;
  }
  v9 = SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+(&v24, v21, v4);
  v10 = (_DWORD *)SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(
                    v9,
                    &v22);
  v11 = *((unsigned int *)this + 4);
  if ( *v10 <= (unsigned int)v11 )
  {
    if ( a3 )
      goto LABEL_14;
    v13 = *((_QWORD *)this + 1);
    if ( (unsigned __int64)a2 >= v13 && (unsigned __int64)a2 < v13 + 2 * v11 )
      goto LABEL_14;
    v12 = *(void (__fastcall **)(CLMString *, _QWORD))(*(_QWORD *)this + 8LL);
  }
  else
  {
    v12 = **(void (__fastcall ***)(CLMString *, _QWORD))this;
  }
  v14 = SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+(&v24, &v22, v4);
  v15 = (unsigned int *)SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(
                          v14,
                          v21);
  v12(this, *v15);
LABEL_14:
  v16 = (int *)SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(
                 &v20,
                 &v22);
  v17 = *v16;
  if ( *v16 + v24 > *((_DWORD *)this + 4) )
    return 0;
  v19 = v24;
  *((_DWORD *)this + 5) = v24;
  *((_DWORD *)this + 5) += MultiByteToWideCharSZ(a2, v4, (wchar_t *)(*((_QWORD *)this + 1) + 2 * v19), v17);
  return *((unsigned int *)this + 5);
}

```

## disassembly

```asm
0x180022350  mov     [rsp-18h+arg_0], rbx
0x180022355  mov     [rsp-18h+arg_10], rsi
0x18002235a  push    rbp
0x18002235b  push    rdi
0x18002235c  push    r14
0x18002235e  mov     rbp, rsp
0x180022361  sub     rsp, 30h
0x180022365  mov     ebx, r9d
0x180022368  mov     edi, r8d
0x18002236b  mov     r14, rdx
0x18002236e  mov     rsi, rcx
0x180022371  test    rdx, rdx
0x180022374  jnz     short loc_180022391
0x180022376  mov     rcx, [rbp+18h]; this
0x18002237a  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x180022381  mov     r9d, 80070057h; char *
0x180022387  lea     edx, [r14+63h]; void *
0x18002238b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180022391  mov     [rbp+arg_8], edi
0x180022394  mov     [rbp+var_10], ebx
0x180022397  cmp     ebx, 0FFFFFFFFh
0x18002239a  jnz     short loc_1800223BD
0x18002239c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800223a0  inc     rax
0x1800223a3  cmp     byte ptr [rdx+rax], 0
0x1800223a7  jnz     short loc_1800223A0
0x1800223a9  lea     rdx, [rbp+var_8]
0x1800223ad  mov     [rbp+var_8], rax
0x1800223b1  lea     rcx, [rbp+var_10]
0x1800223b5  call    ??$?4_K@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEAAAEAV0@AEB_K@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator=<unsigned __int64>(unsigned __int64 const &)
0x1800223ba  mov     ebx, [rbp+var_10]
0x1800223bd  mov     r8d, ebx
0x1800223c0  lea     rdx, [rbp+var_C]
0x1800223c4  lea     rcx, [rbp+arg_8]
0x1800223c8  call    ??H?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@V0@@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+(SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>)
0x1800223cd  lea     rdx, [rbp+var_8]
0x1800223d1  mov     rcx, rax
0x1800223d4  call    ??$?HH@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@H@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(int)
0x1800223d9  mov     edx, [rsi+10h]
0x1800223dc  cmp     [rax], edx
0x1800223de  jbe     short loc_1800223E8
0x1800223e0  mov     rax, [rsi]
0x1800223e3  mov     rdi, [rax]
0x1800223e6  jmp     short loc_180022405
0x1800223e8  test    edi, edi
0x1800223ea  jnz     short loc_18002242E
0x1800223ec  mov     rcx, [rsi+8]
0x1800223f0  cmp     r14, rcx
0x1800223f3  jb      short loc_1800223FE
0x1800223f5  lea     rcx, [rcx+rdx*2]
0x1800223f9  cmp     r14, rcx
0x1800223fc  jb      short loc_18002242E
0x1800223fe  mov     rax, [rsi]
0x180022401  mov     rdi, [rax+8]
0x180022405  mov     r8d, ebx
0x180022408  lea     rdx, [rbp+var_8]
0x18002240c  lea     rcx, [rbp+arg_8]
0x180022410  call    ??H?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@V0@@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+(SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>)
0x180022415  lea     rdx, [rbp+var_C]
0x180022419  mov     rcx, rax
0x18002241c  call    ??$?HH@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@H@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(int)
0x180022421  mov     rcx, rsi
0x180022424  mov     edx, [rax]
0x180022426  mov     rax, rdi
0x180022429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002242e  lea     rdx, [rbp+var_8]
0x180022432  lea     rcx, [rbp+var_10]
0x180022436  call    ??$?HH@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@H@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(int)
0x18002243b  mov     r9d, [rax]; int
0x18002243e  mov     eax, [rbp+arg_8]
0x180022441  lea     ecx, [r9+rax]
0x180022445  cmp     ecx, [rsi+10h]
0x180022448  jbe     short loc_18002244E
0x18002244a  xor     eax, eax
0x18002244c  jmp     short loc_18002246C
0x18002244e  mov     rcx, rax
0x180022451  mov     [rsi+14h], eax
0x180022454  mov     rax, [rsi+8]
0x180022458  mov     edx, ebx; cbMultiByte
0x18002245a  lea     r8, [rax+rcx*2]; wchar_t *
0x18002245e  mov     rcx, r14; lpMultiByteStr
0x180022461  call    ?MultiByteToWideCharSZ@@YAHPEBDHPEA_WH@Z; MultiByteToWideCharSZ(char const *,int,wchar_t *,int)
0x180022466  add     [rsi+14h], eax
0x180022469  mov     eax, [rsi+14h]
0x18002246c  mov     rbx, [rsp+30h+arg_0]
0x180022471  mov     rsi, [rsp+30h+arg_10]
0x180022476  add     rsp, 30h
0x18002247a  pop     r14
0x18002247c  pop     rdi
0x18002247d  pop     rbp
0x18002247e  retn
```
