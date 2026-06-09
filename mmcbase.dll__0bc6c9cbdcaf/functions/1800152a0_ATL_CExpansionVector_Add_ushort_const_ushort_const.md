# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x1800152a0`
- end: `0x180015422`
- name: `?Add@CExpansionVector@ATL@@QEAAJPEBG0@Z`
- size: `386`
- prototype: `int(ATL::CExpansionVector *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001549c`

## callees

- `0x18000a506`
- `0x1800152a0`

## import_xrefs

- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x1800152d1`
- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x1800152d1`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x1800153c1`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x180015407`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x1800153c1`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x180015407`
- `msvcrt!realloc` at `0x1800153a0`
- `msvcrt!realloc` at `0x1800153a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800153ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800153b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800153f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800153fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800153ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800153b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800153f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800153fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001533a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015350`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001533a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015350`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::Add(
        ATL::CExpansionVector *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  ATL::CExpansionVector *v3; // rdi
  const unsigned __int16 *v4; // r12
  const unsigned __int16 *v5; // r15
  void **v6; // rsi
  __int64 v7; // r14
  __int64 v8; // rax
  unsigned int v9; // r13d
  SIZE_T v10; // r14
  LPVOID v11; // rax
  int v12; // eax
  int v13; // eax
  void *v14; // rax
  unsigned int v15; // ebx
  void **v20; // [rsp+78h] [rbp+20h]

  try
  {
    v4 = a3;
    v5 = a2;
    v3 = this;
    v15 = 0;
    v6 = (void **)operator new(0x10u);
    v20 = v6;
  }
  catch ( ... )
  {
    v15 = 0;
    v3 = this;
    v4 = a3;
    v5 = a2;
    v6 = v20;
  }
  if ( v6 )
  {
    v7 = -1;
    if ( v5 )
    {
      v8 = -1;
      do
        ++v8;
      while ( v5[v8] );
    }
    else
    {
      LODWORD(v8) = 0;
    }
    if ( v4 )
    {
      do
        ++v7;
      while ( v4[v7] );
    }
    else
    {
      LODWORD(v7) = 0;
    }
    v9 = 2 * v8 + 2;
    *v6 = CoTaskMemAlloc(v9);
    v10 = (unsigned int)(2 * v7 + 2);
    v11 = CoTaskMemAlloc(v10);
    v6[1] = v11;
    if ( *v6 && v11 )
    {
      memcpy_0(*v6, v5, v9);
      memcpy_0(v6[1], v4, (unsigned int)v10);
      v12 = *((_DWORD *)v3 + 3);
      if ( *((_DWORD *)v3 + 2) == v12 )
      {
        v13 = 2 * v12;
        *((_DWORD *)v3 + 3) = v13;
        v14 = realloc(*(void **)v3, 8LL * v13);
        if ( !v14 )
        {
          CoTaskMemFree(*v6);
          CoTaskMemFree(v6[1]);
          operator delete(v6);
          *((int *)v3 + 3) /= 2;
          return (unsigned int)-2147024882;
        }
        *(_QWORD *)v3 = v14;
      }
      *(_QWORD *)(*(_QWORD *)v3 + 8LL * (int)(*((_DWORD *)v3 + 2))++) = v6;
      return v15;
    }
    CoTaskMemFree(*v6);
    CoTaskMemFree(v6[1]);
    operator delete(v6);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800152a0  mov     [rsp+arg_10], r8
0x1800152a5  mov     [rsp+arg_8], rdx
0x1800152aa  mov     [rsp+arg_0], rcx
0x1800152af  push    rbx
0x1800152b0  push    rsi
0x1800152b1  push    rdi
0x1800152b2  push    r12
0x1800152b4  push    r13
0x1800152b6  push    r14
0x1800152b8  push    r15
0x1800152ba  sub     rsp, 20h
0x1800152be  mov     r12, r8
0x1800152c1  mov     r15, rdx
0x1800152c4  mov     rdi, rcx
0x1800152c7  xor     ebx, ebx
0x1800152c9  mov     [rsp+58h+arg_18], rbx
0x1800152ce  lea     ecx, [rbx+10h]
0x1800152d1  call    cs:__imp_??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800152d7  mov     rsi, rax
0x1800152da  mov     [rsp+58h+arg_18], rax
0x1800152df  jmp     short loc_1800152F7
0x1800152e1  xor     ebx, ebx
0x1800152e3  mov     rdi, [rsp+58h+arg_0]
0x1800152e8  mov     r12, [rsp+58h+arg_10]
0x1800152ed  mov     r15, [rsp+58h+arg_8]
0x1800152f2  mov     rsi, [rsp+58h+arg_18]
0x1800152f7  test    rsi, rsi
0x1800152fa  jz      loc_18001540D
0x180015300  or      r14, 0FFFFFFFFFFFFFFFFh
0x180015304  test    r15, r15
0x180015307  jnz     short loc_18001530D
0x180015309  mov     eax, ebx
0x18001530b  jmp     short loc_18001531A
0x18001530d  mov     rax, r14
0x180015310  inc     rax
0x180015313  cmp     [r15+rax*2], bx
0x180015318  jnz     short loc_180015310
0x18001531a  test    r12, r12
0x18001531d  jnz     short loc_180015324
0x18001531f  mov     r14d, ebx
0x180015322  jmp     short loc_18001532E
0x180015324  inc     r14
0x180015327  cmp     [r12+r14*2], bx
0x18001532c  jnz     short loc_180015324
0x18001532e  lea     eax, ds:2[rax*2]
0x180015335  mov     r13d, eax
0x180015338  mov     ecx, eax; cb
0x18001533a  call    cs:__imp_CoTaskMemAlloc
0x180015340  mov     [rsi], rax
0x180015343  lea     eax, ds:2[r14*2]
0x18001534b  mov     r14d, eax
0x18001534e  mov     ecx, eax; cb
0x180015350  call    cs:__imp_CoTaskMemAlloc
0x180015356  mov     [rsi+8], rax
0x18001535a  cmp     [rsi], rbx
0x18001535d  jz      loc_1800153F1
0x180015363  test    rax, rax
0x180015366  jz      loc_1800153F1
0x18001536c  mov     r8d, r13d; Size
0x18001536f  mov     rdx, r15; Src
0x180015372  mov     rcx, [rsi]; void *
0x180015375  call    memcpy_0
0x18001537a  mov     r8d, r14d; Size
0x18001537d  mov     rdx, r12; Src
0x180015380  mov     rcx, [rsi+8]; void *
0x180015384  call    memcpy_0
0x180015389  mov     eax, [rdi+0Ch]
0x18001538c  cmp     [rdi+8], eax
0x18001538f  jnz     short loc_1800153DF
0x180015391  add     eax, eax
0x180015393  mov     [rdi+0Ch], eax
0x180015396  movsxd  rdx, eax
0x180015399  shl     rdx, 3; Size
0x18001539d  mov     rcx, [rdi]; Block
0x1800153a0  call    cs:__imp_realloc
0x1800153a6  test    rax, rax
0x1800153a9  jnz     short loc_1800153DC
0x1800153ab  mov     rcx, [rsi]; pv
0x1800153ae  call    cs:__imp_CoTaskMemFree
0x1800153b4  mov     rcx, [rsi+8]; pv
0x1800153b8  call    cs:__imp_CoTaskMemFree
0x1800153be  mov     rcx, rsi
0x1800153c1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800153c7  mov     eax, [rdi+0Ch]
0x1800153ca  cdq
0x1800153cb  mov     ecx, 2
0x1800153d0  idiv    ecx
0x1800153d2  mov     [rdi+0Ch], eax
0x1800153d5  mov     ebx, 8007000Eh
0x1800153da  jmp     short loc_1800153ED
0x1800153dc  mov     [rdi], rax
0x1800153df  movsxd  rdx, dword ptr [rdi+8]
0x1800153e3  mov     rcx, [rdi]
0x1800153e6  mov     [rcx+rdx*8], rsi
0x1800153ea  inc     dword ptr [rdi+8]
0x1800153ed  mov     eax, ebx
0x1800153ef  jmp     short loc_180015412
0x1800153f1  mov     rcx, [rsi]; pv
0x1800153f4  call    cs:__imp_CoTaskMemFree
0x1800153fa  mov     rcx, [rsi+8]; pv
0x1800153fe  call    cs:__imp_CoTaskMemFree
0x180015404  mov     rcx, rsi
0x180015407  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001540d  mov     eax, 8007000Eh
0x180015412  add     rsp, 20h
0x180015416  pop     r15
0x180015418  pop     r14
0x18001541a  pop     r13
0x18001541c  pop     r12
0x18001541e  pop     rdi
0x18001541f  pop     rsi
0x180015420  pop     rbx
0x180015421  retn
```
