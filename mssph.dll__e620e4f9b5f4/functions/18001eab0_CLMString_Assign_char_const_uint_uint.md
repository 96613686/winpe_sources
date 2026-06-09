# CLMString::Assign(char const *,uint,uint)

- ea: `0x18001eab0`
- end: `0x18001ebdf`
- name: `?Assign@CLMString@@UEAAHPEBDII@Z`
- size: `303`
- prototype: `__int64 __fastcall(CLMString *this, const char *, unsigned int, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a450`
- `0x18000a970`
- `0x18000b324`
- `0x18000e7fc`
- `0x18001eab0`
- `0x18001f080`
- `0x180027010`

## string_xrefs

- `0x18001eada`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
__int64 __fastcall CLMString::Assign(CLMString *this, const char *a2, unsigned int a3, int a4)
{
  unsigned int v4; // ebx
  __int64 v8; // rax
  unsigned int *v9; // rax
  _DWORD *v10; // rax
  __int64 v11; // rdx
  void (__fastcall *v12)(CLMString *, _QWORD); // rdi
  unsigned __int64 v13; // rcx
  unsigned int *v14; // rax
  _DWORD *v15; // rax
  int *v16; // rax
  int v17; // r9d
  __int64 v19; // rcx
  int v20; // [rsp+20h] [rbp-10h] BYREF
  int v21; // [rsp+24h] [rbp-Ch] BYREF
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
  v9 = (unsigned int *)SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+(
                         &v24,
                         &v21,
                         v4);
  v10 = SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(v9, &v22);
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
  v14 = (unsigned int *)SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+(
                          &v24,
                          &v22,
                          v4);
  v15 = SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(v14, &v21);
  v12(this, (unsigned int)*v15);
LABEL_14:
  v16 = SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(
          (unsigned int *)&v20,
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
0x18001eab0  mov     [rsp-18h+arg_0], rbx
0x18001eab5  mov     [rsp-18h+arg_10], rsi
0x18001eaba  push    rbp
0x18001eabb  push    rdi
0x18001eabc  push    r14
0x18001eabe  mov     rbp, rsp
0x18001eac1  sub     rsp, 30h
0x18001eac5  mov     ebx, r9d
0x18001eac8  mov     edi, r8d
0x18001eacb  mov     r14, rdx
0x18001eace  mov     rsi, rcx
0x18001ead1  test    rdx, rdx
0x18001ead4  jnz     short loc_18001EAF1
0x18001ead6  mov     rcx, [rbp+18h]; this
0x18001eada  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\search\\com"...
0x18001eae1  mov     r9d, 80070057h; char *
0x18001eae7  lea     edx, [r14+63h]; void *
0x18001eaeb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001eaf1  mov     [rbp+arg_8], edi
0x18001eaf4  mov     [rbp+var_10], ebx
0x18001eaf7  cmp     ebx, 0FFFFFFFFh
0x18001eafa  jnz     short loc_18001EB1D
0x18001eafc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001eb00  inc     rax
0x18001eb03  cmp     byte ptr [rdx+rax], 0
0x18001eb07  jnz     short loc_18001EB00
0x18001eb09  lea     rdx, [rbp+var_8]
0x18001eb0d  mov     [rbp+var_8], rax
0x18001eb11  lea     rcx, [rbp+var_10]
0x18001eb15  call    ??$?4_K@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEAAAEAV0@AEB_K@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator=<unsigned __int64>(unsigned __int64 const &)
0x18001eb1a  mov     ebx, [rbp+var_10]
0x18001eb1d  mov     r8d, ebx
0x18001eb20  lea     rdx, [rbp+var_C]
0x18001eb24  lea     rcx, [rbp+arg_8]
0x18001eb28  call    ??H?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@V0@@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+(SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>)
0x18001eb2d  lea     rdx, [rbp+var_8]
0x18001eb31  mov     rcx, rax
0x18001eb34  call    ??$?HH@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@H@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(int)
0x18001eb39  mov     edx, [rsi+10h]
0x18001eb3c  cmp     [rax], edx
0x18001eb3e  jbe     short loc_18001EB48
0x18001eb40  mov     rax, [rsi]
0x18001eb43  mov     rdi, [rax]
0x18001eb46  jmp     short loc_18001EB65
0x18001eb48  test    edi, edi
0x18001eb4a  jnz     short loc_18001EB8E
0x18001eb4c  mov     rcx, [rsi+8]
0x18001eb50  cmp     r14, rcx
0x18001eb53  jb      short loc_18001EB5E
0x18001eb55  lea     rcx, [rcx+rdx*2]
0x18001eb59  cmp     r14, rcx
0x18001eb5c  jb      short loc_18001EB8E
0x18001eb5e  mov     rax, [rsi]
0x18001eb61  mov     rdi, [rax+8]
0x18001eb65  mov     r8d, ebx
0x18001eb68  lea     rdx, [rbp+var_8]
0x18001eb6c  lea     rcx, [rbp+arg_8]
0x18001eb70  call    ??H?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@V0@@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+(SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>)
0x18001eb75  lea     rdx, [rbp+var_C]
0x18001eb79  mov     rcx, rax
0x18001eb7c  call    ??$?HH@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@H@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(int)
0x18001eb81  mov     rcx, rsi
0x18001eb84  mov     edx, [rax]
0x18001eb86  mov     rax, rdi
0x18001eb89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb8e  lea     rdx, [rbp+var_8]
0x18001eb92  lea     rcx, [rbp+var_10]
0x18001eb96  call    ??$?HH@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@H@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(int)
0x18001eb9b  mov     r9d, [rax]; int
0x18001eb9e  mov     eax, [rbp+arg_8]
0x18001eba1  lea     ecx, [r9+rax]
0x18001eba5  cmp     ecx, [rsi+10h]
0x18001eba8  jbe     short loc_18001EBAE
0x18001ebaa  xor     eax, eax
0x18001ebac  jmp     short loc_18001EBCC
0x18001ebae  mov     rcx, rax
0x18001ebb1  mov     [rsi+14h], eax
0x18001ebb4  mov     rax, [rsi+8]
0x18001ebb8  mov     edx, ebx; cbMultiByte
0x18001ebba  lea     r8, [rax+rcx*2]; wchar_t *
0x18001ebbe  mov     rcx, r14; lpMultiByteStr
0x18001ebc1  call    ?MultiByteToWideCharSZ@@YAHPEBDHPEA_WH@Z; MultiByteToWideCharSZ(char const *,int,wchar_t *,int)
0x18001ebc6  add     [rsi+14h], eax
0x18001ebc9  mov     eax, [rsi+14h]
0x18001ebcc  mov     rbx, [rsp+30h+arg_0]
0x18001ebd1  mov     rsi, [rsp+30h+arg_10]
0x18001ebd6  add     rsp, 30h
0x18001ebda  pop     r14
0x18001ebdc  pop     rdi
0x18001ebdd  pop     rbp
0x18001ebde  retn
```
