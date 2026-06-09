# std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>::_Growmap(unsigned __int64)

- ea: `0x180010594`
- end: `0x1800106dd`
- name: `?_Growmap@?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@AEAAX_K@Z`
- size: `329`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009b98`

## callees

- `0x1800028e8`
- `0x180003a00`
- `0x180003c34`
- `0x180003e4c`
- `0x180010594`
- `0x180010d24`
- `0x1800139ec`

## pseudocode

```c
void __fastcall std::deque<ATL::CComPtr<IBackgroundCopyFile>>::_Growmap(_QWORD *a1)
{
  unsigned __int64 v2; // rsi
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rdi
  size_t size_of; // rax
  _QWORD *v6; // r14
  __int64 v7; // r15
  char *v8; // r12
  unsigned __int64 v9; // rax
  __int64 v10; // rax
  unsigned __int64 v11; // rsi
  size_t v12; // rbx
  const void *v13; // rdx
  char *v14; // rbx
  size_t v15; // r8
  char *v16; // rcx
  void *v17; // rcx

  v2 = 1;
  v3 = a1[2];
  if ( v3 )
    v2 = v3;
  while ( v2 == v3 || v2 < 8 )
  {
    if ( 0xFFFFFFFFFFFFFFFLL - v2 < v2 )
      std::deque<MapsBackgroundTransferJob::RequestContext>::_Xlen();
    v2 *= 2LL;
  }
  v4 = a1[3] >> 1;
  size_of = std::_Get_size_of_n<8>(v2);
  v6 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v7 = 8 * v4;
  v8 = (char *)&v6[v4];
  v9 = v2 >> 1;
  while ( v2 <= v9 )
    v2 *= 2LL;
  v10 = a1[2];
  v11 = v2 - v10;
  v12 = 8 * v10 - v7;
  memmove_0(v8, (const void *)(a1[1] + v7), v12);
  v13 = (const void *)a1[1];
  v14 = &v8[v12];
  if ( v4 > v11 )
  {
    memmove_0(v14, v13, 8 * v11);
    memmove_0(v6, (const void *)(8 * v11 + a1[1]), v7 - 8 * v11);
    v16 = (char *)v6 + v7 - 8 * v11;
    v15 = 8 * v11;
  }
  else
  {
    memmove_0(v14, v13, 8 * v4);
    memset_0(&v14[v7], 0, 8 * (v11 - v4));
    v15 = 8 * v4;
    v16 = (char *)v6;
  }
  memset_0(v16, 0, v15);
  v17 = (void *)a1[1];
  if ( v17 )
    std::_Deallocate<16>(v17, 8LL * a1[2]);
  a1[2] += v11;
  a1[1] = v6;
}

```

## disassembly

```asm
0x180010594  push    rbx
0x180010596  push    rbp
0x180010597  push    rsi
0x180010598  push    rdi
0x180010599  push    r12
0x18001059b  push    r14
0x18001059d  push    r15
0x18001059f  sub     rsp, 20h
0x1800105a3  mov     rbp, rcx
0x1800105a6  mov     esi, 1
0x1800105ab  mov     rcx, [rcx+10h]
0x1800105af  test    rcx, rcx
0x1800105b2  cmovnz  rsi, rcx
0x1800105b6  mov     rax, rsi
0x1800105b9  sub     rax, rcx
0x1800105bc  cmp     rax, 1
0x1800105c0  jb      short loc_1800105C8
0x1800105c2  cmp     rsi, 8
0x1800105c6  jnb     short loc_1800105E3
0x1800105c8  mov     rax, 0FFFFFFFFFFFFFFFh
0x1800105d2  sub     rax, rsi
0x1800105d5  cmp     rax, rsi
0x1800105d8  jb      loc_1800106D7
0x1800105de  add     rsi, rsi
0x1800105e1  jmp     short loc_1800105B6
0x1800105e3  mov     rdi, [rbp+18h]
0x1800105e7  mov     rcx, rsi
0x1800105ea  shr     rdi, 1
0x1800105ed  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x1800105f2  mov     rcx, rax
0x1800105f5  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800105fa  mov     r14, rax
0x1800105fd  lea     r15, ds:0[rdi*8]
0x180010605  lea     r12, [r15+rax]
0x180010609  mov     rax, rsi
0x18001060c  shr     rax, 1
0x18001060f  jmp     short loc_180010614
0x180010611  add     rsi, rsi
0x180010614  cmp     rsi, rax
0x180010617  jbe     short loc_180010611
0x180010619  mov     rcx, [rbp+8]
0x18001061d  mov     rax, [rbp+10h]
0x180010621  sub     rsi, rax
0x180010624  shl     rax, 3
0x180010628  lea     rdx, [rcx+r15]; Src
0x18001062c  sub     rax, rdx
0x18001062f  lea     rbx, [rax+rcx]
0x180010633  mov     rcx, r12; void *
0x180010636  mov     r8, rbx; Size
0x180010639  call    memmove_0
0x18001063e  mov     rdx, [rbp+8]; Src
0x180010642  add     rbx, r12
0x180010645  mov     rcx, rbx; void *
0x180010648  cmp     rdi, rsi
0x18001064b  ja      short loc_180010672
0x18001064d  mov     r8, r15; Size
0x180010650  call    memmove_0
0x180010655  mov     r8, rsi
0x180010658  lea     rcx, [rbx+r15]; void *
0x18001065c  sub     r8, rdi
0x18001065f  xor     edx, edx; Val
0x180010661  shl     r8, 3; Size
0x180010665  call    memset_0
0x18001066a  mov     r8, r15
0x18001066d  mov     rcx, r14
0x180010670  jmp     short loc_1800106A3
0x180010672  lea     rdi, ds:0[rsi*8]
0x18001067a  mov     r8, rdi; Size
0x18001067d  call    memmove_0
0x180010682  mov     rax, [rbp+8]
0x180010686  mov     rcx, r14; void *
0x180010689  lea     rdx, [rdi+rax]; Src
0x18001068d  sub     rax, rdx
0x180010690  lea     rbx, [rax+r15]
0x180010694  mov     r8, rbx; Size
0x180010697  call    memmove_0
0x18001069c  lea     rcx, [rbx+r14]; void *
0x1800106a0  mov     r8, rdi; Size
0x1800106a3  xor     edx, edx; Val
0x1800106a5  call    memset_0
0x1800106aa  mov     rcx, [rbp+8]
0x1800106ae  test    rcx, rcx
0x1800106b1  jz      short loc_1800106C0
0x1800106b3  mov     rdx, [rbp+10h]
0x1800106b7  shl     rdx, 3
0x1800106bb  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800106c0  add     [rbp+10h], rsi
0x1800106c4  mov     [rbp+8], r14
0x1800106c8  add     rsp, 20h
0x1800106cc  pop     r15
0x1800106ce  pop     r14
0x1800106d0  pop     r12
0x1800106d2  pop     rdi
0x1800106d3  pop     rsi
0x1800106d4  pop     rbp
0x1800106d5  pop     rbx
0x1800106d6  retn
0x1800106d7  call    ?_Xlen@?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@CAXXZ; std::deque<MapsBackgroundTransferJob::RequestContext>::_Xlen(void)
```
