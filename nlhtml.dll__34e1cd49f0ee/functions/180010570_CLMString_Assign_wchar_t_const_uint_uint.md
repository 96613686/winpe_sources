# CLMString::Assign(wchar_t const *,uint,uint)

- ea: `0x180010570`
- end: `0x180010724`
- name: `?Assign@CLMString@@UEAAHPEB_WII@Z`
- size: `436`
- prototype: `__int64 __fastcall(CLMString *this, const wchar_t *, unsigned int, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180010570`
- `0x180010c60`
- `0x180010c90`
- `0x180013500`
- `0x180013968`
- `0x180023388`
- `0x180025010`

## string_xrefs

- `0x1800106b5`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
__int64 __fastcall CLMString::Assign(CLMString *this, const wchar_t *a2, unsigned int a3, int a4)
{
  unsigned int v4; // edi
  const wchar_t *v5; // rsi
  CLMString *v6; // r14
  __int64 v7; // r8
  unsigned __int64 v8; // rbx
  __int64 v9; // rax
  unsigned __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned __int64 v13; // rax
  void *v14; // rcx
  void (__fastcall *v16)(CLMString *, _QWORD); // rdi
  __int64 v17; // rax
  unsigned int *v18; // rax
  _WORD *v19; // rax
  int v20; // [rsp+20h] [rbp-18h] BYREF
  _BYTE v21[20]; // [rsp+24h] [rbp-14h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v23; // [rsp+48h] [rbp+10h] BYREF

  v4 = a3;
  v5 = a2;
  v6 = this;
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
      (const char *)0x80070057LL,
      v20);
  v23 = a3;
  v7 = 0xFFFFFFFFLL;
  if ( a4 == -1 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    if ( v8 > 0xFFFFFFFF )
      goto LABEL_22;
  }
  else
  {
    LODWORD(v8) = a4;
  }
  v9 = (unsigned int)v8 + v4;
  if ( (unsigned int)v9 < v4 )
    goto LABEL_22;
  v10 = v9 + 1;
  if ( v10 > 0xFFFFFFFF )
    goto LABEL_22;
  v11 = *((unsigned int *)this + 4);
  if ( (unsigned int)v10 > (unsigned int)v11 )
  {
    v16 = **(void (__fastcall ***)(CLMString *, _QWORD))this;
    v17 = SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+(
            &v23,
            &v20,
            (unsigned int)v8);
    v18 = (unsigned int *)SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(
                            v17,
                            v21);
    v16(v6, *v18);
    v4 = v23;
  }
  else if ( !v4 )
  {
    this = (CLMString *)*((_QWORD *)this + 1);
    if ( v5 < (const wchar_t *)this || (this = (CLMString *)((char *)this + 2 * v11), v5 >= (const wchar_t *)this) )
    {
      a2 = (const wchar_t *)((unsigned int)v8 + 1LL);
      if ( (unsigned __int64)a2 > 0xFFFFFFFF )
        goto LABEL_22;
      (*(void (__fastcall **)(CLMString *, const wchar_t *, __int64))(*(_QWORD *)v6 + 8LL))(v6, a2, 0xFFFFFFFFLL);
    }
  }
  a2 = (const wchar_t *)(2LL * (unsigned int)v8);
  if ( !is_mul_ok(2u, v8) )
    goto LABEL_22;
  v12 = 2LL * v4;
  if ( !is_mul_ok(2u, v4) )
    goto LABEL_22;
  v13 = (unsigned int)(v12 + (_DWORD)a2);
  if ( (unsigned int)v13 < (unsigned int)v12 )
    goto LABEL_22;
  this = (CLMString *)(2LL * *((unsigned int *)v6 + 4));
  if ( v13 > (unsigned __int64)this )
  {
    v19 = (_WORD *)*((_QWORD *)v6 + 1);
    *((_DWORD *)v6 + 5) = 0;
    *v19 = 0;
    return 0;
  }
  if ( v4 + (unsigned int)v8 < v4 )
LABEL_22:
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(this, a2, v7);
  v14 = (void *)(v12 + *((_QWORD *)v6 + 1));
  *((_DWORD *)v6 + 5) = v4 + v8;
  memcpy_0(v14, v5, (unsigned int)a2);
  *(_WORD *)(*((_QWORD *)v6 + 1) + 2LL * *((unsigned int *)v6 + 5)) = 0;
  return *((unsigned int *)v6 + 5);
}

```

## disassembly

```asm
0x180010570  mov     [rsp+arg_10], rsi
0x180010575  mov     [rsp+arg_18], rdi
0x18001057a  push    r14
0x18001057c  sub     rsp, 30h
0x180010580  mov     edi, r8d
0x180010583  mov     rsi, rdx
0x180010586  mov     r14, rcx
0x180010589  test    rdx, rdx
0x18001058c  jz      loc_1800106B0
0x180010592  mov     [rsp+38h+arg_8], r8d
0x180010597  mov     r8d, 0FFFFFFFFh
0x18001059d  mov     [rsp+38h+arg_0], rbx
0x1800105a2  cmp     r9d, r8d
0x1800105a5  jnz     loc_1800106CD
0x1800105ab  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800105b2  inc     rbx
0x1800105b5  cmp     word ptr [rdx+rbx*2], 0
0x1800105ba  jnz     short loc_1800105B2
0x1800105bc  cmp     rbx, r8
0x1800105bf  ja      loc_1800106AA
0x1800105c5  lea     eax, [rbx+rdi]
0x1800105c8  cmp     eax, edi
0x1800105ca  jb      loc_1800106AA
0x1800105d0  inc     rax
0x1800105d3  cmp     rax, r8
0x1800105d6  ja      loc_1800106AA
0x1800105dc  mov     edx, [rcx+10h]
0x1800105df  cmp     eax, edx
0x1800105e1  ja      loc_1800106D5
0x1800105e7  test    edi, edi
0x1800105e9  jnz     short loc_180010615
0x1800105eb  mov     rcx, [rcx+8]
0x1800105ef  cmp     rsi, rcx
0x1800105f2  jnb     loc_180010698
0x1800105f8  mov     edx, ebx
0x1800105fa  inc     rdx
0x1800105fd  cmp     rdx, r8
0x180010600  ja      loc_1800106AA
0x180010606  mov     rax, [r14]
0x180010609  mov     rcx, r14
0x18001060c  mov     rax, [rax+8]
0x180010610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010615  mov     edx, ebx
0x180010617  add     rdx, rdx
0x18001061a  mov     rax, rdx
0x18001061d  shr     rax, 20h
0x180010621  test    eax, eax
0x180010623  jnz     loc_1800106AA
0x180010629  mov     eax, edi
0x18001062b  lea     r9, [rax+rax]
0x18001062f  mov     rax, r9
0x180010632  shr     rax, 20h
0x180010636  test    eax, eax
0x180010638  jnz     short loc_1800106AA
0x18001063a  lea     eax, [r9+rdx]
0x18001063e  cmp     eax, r9d
0x180010641  jb      short loc_1800106AA
0x180010643  mov     ecx, [r14+10h]
0x180010647  add     rcx, rcx
0x18001064a  cmp     rax, rcx
0x18001064d  ja      loc_180010710
0x180010653  lea     eax, [rdi+rbx]
0x180010656  cmp     eax, edi
0x180010658  jb      short loc_1800106AA
0x18001065a  mov     rcx, [r14+8]
0x18001065e  mov     r8d, edx; Size
0x180010661  add     rcx, r9; void *
0x180010664  mov     rdx, rsi; Src
0x180010667  mov     [r14+14h], eax
0x18001066b  call    memcpy_0
0x180010670  mov     rax, [r14+8]
0x180010674  xor     edx, edx
0x180010676  mov     ecx, [r14+14h]
0x18001067a  mov     [rax+rcx*2], dx
0x18001067e  mov     eax, [r14+14h]
0x180010682  mov     rbx, [rsp+38h+arg_0]
0x180010687  mov     rsi, [rsp+38h+arg_10]
0x18001068c  mov     rdi, [rsp+38h+arg_18]
0x180010691  add     rsp, 30h
0x180010695  pop     r14
0x180010697  retn
0x180010698  lea     rcx, [rcx+rdx*2]
0x18001069c  cmp     rsi, rcx
0x18001069f  jnb     loc_1800105F8
0x1800106a5  jmp     loc_180010615
0x1800106aa  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800106b0  mov     rcx, [rsp+38h]; this
0x1800106b5  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800106bc  mov     r9d, 80070057h; char *
0x1800106c2  mov     edx, 36h ; '6'; void *
0x1800106c7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800106cd  mov     ebx, r9d
0x1800106d0  jmp     loc_1800105C5
0x1800106d5  mov     rax, [rcx]
0x1800106d8  lea     rdx, [rsp+38h+var_18]
0x1800106dd  mov     r8d, ebx
0x1800106e0  lea     rcx, [rsp+38h+arg_8]
0x1800106e5  mov     rdi, [rax]
0x1800106e8  call    ??H?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@V0@@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+(SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>)
0x1800106ed  lea     rdx, [rsp+38h+var_14]
0x1800106f2  mov     rcx, rax
0x1800106f5  call    ??$?HH@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@H@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(int)
0x1800106fa  mov     rcx, r14
0x1800106fd  mov     edx, [rax]
0x1800106ff  mov     rax, rdi
0x180010702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010707  mov     edi, [rsp+38h+arg_8]
0x18001070b  jmp     loc_180010615
0x180010710  mov     rax, [r14+8]
0x180010714  xor     edx, edx
0x180010716  mov     [r14+14h], edx
0x18001071a  mov     [rax], dx
0x18001071d  xor     eax, eax
0x18001071f  jmp     loc_180010682
```
