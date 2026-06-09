# Compress(ushort const *,unsigned __int64,ushort * *)

- ea: `0x1401c3444`
- end: `0x1401c36be`
- name: `?Compress@@YAJPEBG_KPEAPEAG@Z`
- size: `634`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1401c5934`

## callees

- `0x14000fbdc`
- `0x140027ba0`
- `0x14009ac68`
- `0x14010e160`
- `0x14010ed90`
- `0x1401c3444`
- `0x1401c36c4`
- `0x1401c47c0`
- `0x1401c5cf4`
- `0x1401c5d38`
- `0x1401d1de0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1401c360d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1401c3626`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1401c3663`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1401c360d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1401c3626`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1401c3663`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1401c3491`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1401c357a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1401c3491`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1401c357a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Compress(const unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 **a3)
{
  unsigned int *v6; // rax
  unsigned int *v7; // rdi
  unsigned __int64 i; // rdx
  unsigned int v9; // edx
  __int64 v10; // r12
  unsigned __int64 v11; // r15
  int v12; // r14d
  _WORD *v13; // rbx
  int v14; // edx
  unsigned __int64 v15; // r9
  unsigned __int64 j; // r8
  __int64 v17; // r10
  unsigned __int16 *v18; // rax
  __int64 v19; // rdx
  __int64 v21; // rdx
  unsigned int v22[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v23; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+40h] [rbp-C0h]
  unsigned int v25; // [rsp+48h] [rbp-B8h]
  int v26; // [rsp+4Ch] [rbp-B4h]
  unsigned __int64 v27; // [rsp+50h] [rbp-B0h]
  _BYTE v28[10248]; // [rsp+58h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+28A8h] [rbp+27A8h]

  *a3 = 0;
  v6 = (unsigned int *)CoTaskMemAlloc(4 * a2);
  v7 = v6;
  if ( !v6 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x140,
      (unsigned int)"onecore\\shell\\lib\\userchoicehelpers\\userchoicecore.cpp",
      (const char *)0x8007000ELL,
      v22[0]);
    return 2147942414LL;
  }
  for ( i = 0; i < a2; ++i )
    v6[i] = a1[i];
  v23 = 0;
  v24 = 0;
  inverted::vector_nothrow<unsigned __int64>::clear(&v23, i);
  inverted::vector_nothrow<unsigned __int64>::push_back(&v23, qword_14020CE00);
  v26 = 0;
  v27 = 0xFBFFFFFFFFFFFFFFuLL;
  memset_0(v28, 0, sizeof(v28));
  v25 = 0;
  v22[0] = 0;
  inverted::CSimple256Compressor::Compress((inverted::CSimple256Compressor *)&v23, v7, a2, v22);
  inverted::CSimple256Compressor::CompressRemainder((inverted::CSimple256Compressor *)&v23, &v7[v22[0]], a2 - v22[0]);
  v9 = v24;
  v10 = v23;
  *(_QWORD *)v23 = v25 | (unsigned __int64)(v24 << 32);
  v11 = v9;
  v12 = 4 * v9;
  v13 = CoTaskMemAlloc(2LL * (int)(4 * v9) + 2);
  if ( !v13 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x150,
      (unsigned int)"onecore\\shell\\lib\\userchoicehelpers\\userchoicecore.cpp",
      (const char *)0x8007000ELL,
      v22[0]);
    inverted::vector_nothrow<unsigned __int64>::clear(&v23, v21);
    CoTaskMemFree(v7);
    return 2147942414LL;
  }
  v14 = 0;
  v15 = 0;
  if ( (_DWORD)v11 )
  {
    do
    {
      if ( v14 >= v12 )
        break;
      for ( j = 0; j < 8; j += 2LL )
      {
        if ( v14 >= v12 )
          break;
        v17 = *(_QWORD *)(v10 + 8 * v15) >> (8 * (unsigned __int8)j);
        if ( (_WORD)v17 )
          v13[v14++] = v17;
      }
      ++v15;
    }
    while ( v15 < v11 );
  }
  v13[v14] = 0;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    v22,
    v13,
    -1);
  v18 = *(unsigned __int16 **)v22;
  *(_QWORD *)v22 = 0;
  *a3 = v18;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v22);
  CoTaskMemFree(v13);
  inverted::vector_nothrow<unsigned __int64>::clear(&v23, v19);
  CoTaskMemFree(v7);
  return 0;
}

```

## disassembly

```asm
0x1401c3444  mov     [rsp-8+arg_0], rbx
0x1401c3449  push    rbp
0x1401c344a  push    rsi
0x1401c344b  push    rdi
0x1401c344c  push    r12
0x1401c344e  push    r13
0x1401c3450  push    r14
0x1401c3452  push    r15
0x1401c3454  lea     rbp, [rsp-2770h]
0x1401c345c  mov     eax, 2870h
0x1401c3461  call    _alloca_probe
0x1401c3466  sub     rsp, rax
0x1401c3469  mov     rax, cs:__security_cookie
0x1401c3470  xor     rax, rsp
0x1401c3473  mov     [rbp+27A0h+var_40], rax
0x1401c347a  mov     rsi, r8
0x1401c347d  mov     rbx, rdx
0x1401c3480  mov     r14, rcx
0x1401c3483  xor     r13d, r13d
0x1401c3486  mov     [r8], r13
0x1401c3489  lea     rcx, ds:0[rdx*4]; cb
0x1401c3491  call    cs:__imp_CoTaskMemAlloc
0x1401c3498  nop     dword ptr [rax+rax+00h]
0x1401c349d  mov     rdi, rax
0x1401c34a0  test    rax, rax
0x1401c34a3  jz      loc_1401C3671
0x1401c34a9  mov     edx, r13d
0x1401c34ac  test    rbx, rbx
0x1401c34af  jz      short loc_1401C34C1
0x1401c34b1  movzx   ecx, word ptr [r14+rdx*2]
0x1401c34b6  mov     [rax+rdx*4], ecx
0x1401c34b9  inc     rdx
0x1401c34bc  cmp     rdx, rbx
0x1401c34bf  jb      short loc_1401C34B1
0x1401c34c1  xorps   xmm0, xmm0
0x1401c34c4  movdqa  [rsp+28A0h+var_2870], xmm0
0x1401c34ca  mov     [rsp+28A0h+var_2860], r13
0x1401c34cf  lea     rcx, [rsp+28A0h+var_2870]
0x1401c34d4  call    ?clear@?$vector_nothrow@_K@inverted@@QEAAXXZ; inverted::vector_nothrow<unsigned __int64>::clear(void)
0x1401c34d9  lea     rdx, qword_14020CE00
0x1401c34e0  lea     rcx, [rsp+28A0h+var_2870]
0x1401c34e5  call    ?push_back@?$vector_nothrow@_K@inverted@@QEAAXAEB_K@Z; inverted::vector_nothrow<unsigned __int64>::push_back(unsigned __int64 const &)
0x1401c34ea  mov     [rsp+28A0h+var_2854], r13d
0x1401c34ef  mov     rax, 0FBFFFFFFFFFFFFFFh
0x1401c34f9  mov     [rsp+28A0h+var_2850], rax
0x1401c34fe  xor     edx, edx; Val
0x1401c3500  mov     r8d, 2808h; Size
0x1401c3506  lea     rcx, [rsp+28A0h+var_2848]; void *
0x1401c350b  call    memset_0
0x1401c3510  mov     [rsp+28A0h+var_2858], r13d
0x1401c3515  mov     [rsp+28A0h+var_2880], r13d; int
0x1401c351a  lea     r9, [rsp+28A0h+var_2880]; unsigned int *
0x1401c351f  mov     r8d, ebx; unsigned int
0x1401c3522  mov     rdx, rdi; unsigned int *
0x1401c3525  lea     rcx, [rsp+28A0h+var_2870]; this
0x1401c352a  call    ?Compress@CSimple256Compressor@inverted@@AEAAXPEBIIPEAI@Z; inverted::CSimple256Compressor::Compress(uint const *,uint,uint *)
0x1401c352f  sub     ebx, [rsp+28A0h+var_2880]
0x1401c3533  mov     eax, [rsp+28A0h+var_2880]
0x1401c3537  lea     rdx, [rdi+rax*4]; unsigned int *
0x1401c353b  mov     r8d, ebx; unsigned int
0x1401c353e  lea     rcx, [rsp+28A0h+var_2870]; this
0x1401c3543  call    ?CompressRemainder@CSimple256Compressor@inverted@@AEAAXPEBII@Z; inverted::CSimple256Compressor::CompressRemainder(uint const *,uint)
0x1401c3548  mov     rdx, [rsp+28A0h+var_2860]
0x1401c354d  mov     rcx, rdx
0x1401c3550  shl     rcx, 20h
0x1401c3554  mov     eax, [rsp+28A0h+var_2858]
0x1401c3558  or      rcx, rax
0x1401c355b  mov     r12, qword ptr [rsp+28A0h+var_2870]
0x1401c3560  mov     [r12], rcx
0x1401c3564  mov     r15d, edx
0x1401c3567  lea     r14d, ds:0[r15*4]
0x1401c356f  movsxd  rcx, r14d
0x1401c3572  lea     rcx, ds:2[rcx*2]; cb
0x1401c357a  call    cs:__imp_CoTaskMemAlloc
0x1401c3581  nop     dword ptr [rax+rax+00h]
0x1401c3586  mov     rbx, rax
0x1401c3589  test    rax, rax
0x1401c358c  jz      loc_1401C3636
0x1401c3592  mov     edx, r13d
0x1401c3595  mov     r9, r13
0x1401c3598  test    r15d, r15d
0x1401c359b  jz      short loc_1401C35D9
0x1401c359d  cmp     edx, r14d
0x1401c35a0  jge     short loc_1401C35D9
0x1401c35a2  mov     r8, r13
0x1401c35a5  cmp     edx, r14d
0x1401c35a8  jge     short loc_1401C35D1
0x1401c35aa  mov     cl, r8b
0x1401c35ad  shl     cl, 3
0x1401c35b0  mov     r10, [r12+r9*8]
0x1401c35b4  shr     r10, cl
0x1401c35b7  test    r10w, r10w
0x1401c35bb  jz      short loc_1401C35C7
0x1401c35bd  movsxd  rax, edx
0x1401c35c0  mov     [rbx+rax*2], r10w
0x1401c35c5  inc     edx
0x1401c35c7  add     r8, 2
0x1401c35cb  cmp     r8, 8
0x1401c35cf  jb      short loc_1401C35A5
0x1401c35d1  inc     r9
0x1401c35d4  cmp     r9, r15
0x1401c35d7  jb      short loc_1401C359D
0x1401c35d9  movsxd  rcx, edx
0x1401c35dc  mov     [rbx+rcx*2], r13w
0x1401c35e1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1401c35e5  mov     rdx, rbx
0x1401c35e8  lea     rcx, [rsp+28A0h+var_2880]
0x1401c35ed  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1401c35f2  mov     rax, qword ptr [rsp+28A0h+var_2880]
0x1401c35f7  mov     qword ptr [rsp+28A0h+var_2880], r13
0x1401c35fc  mov     [rsi], rax
0x1401c35ff  lea     rcx, [rsp+28A0h+var_2880]
0x1401c3604  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1401c3609  nop
0x1401c360a  mov     rcx, rbx; pv
0x1401c360d  call    cs:__imp_CoTaskMemFree
0x1401c3614  nop     dword ptr [rax+rax+00h]
0x1401c3619  lea     rcx, [rsp+28A0h+var_2870]
0x1401c361e  call    ?clear@?$vector_nothrow@_K@inverted@@QEAAXXZ; inverted::vector_nothrow<unsigned __int64>::clear(void)
0x1401c3623  mov     rcx, rdi; pv
0x1401c3626  call    cs:__imp_CoTaskMemFree
0x1401c362d  nop     dword ptr [rax+rax+00h]
0x1401c3632  xor     eax, eax
0x1401c3634  jmp     short loc_1401C3693
0x1401c3636  mov     rcx, [rbp+27A8h]; this
0x1401c363d  mov     ebx, 8007000Eh
0x1401c3642  mov     r9d, ebx; char *
0x1401c3645  lea     r8, aOnecoreShellLi_1; "onecore\\shell\\lib\\userchoicehelpers"...
0x1401c364c  mov     edx, 150h; void *
0x1401c3651  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401c3656  lea     rcx, [rsp+28A0h+var_2870]
0x1401c365b  call    ?clear@?$vector_nothrow@_K@inverted@@QEAAXXZ; inverted::vector_nothrow<unsigned __int64>::clear(void)
0x1401c3660  mov     rcx, rdi; pv
0x1401c3663  call    cs:__imp_CoTaskMemFree
0x1401c366a  nop     dword ptr [rax+rax+00h]
0x1401c366f  jmp     short loc_1401C3691
0x1401c3671  mov     rcx, [rbp+27A8h]; this
0x1401c3678  mov     ebx, 8007000Eh
0x1401c367d  mov     r9d, ebx; char *
0x1401c3680  lea     r8, aOnecoreShellLi_1; "onecore\\shell\\lib\\userchoicehelpers"...
0x1401c3687  mov     edx, 140h; void *
0x1401c368c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401c3691  mov     eax, ebx
0x1401c3693  mov     rcx, [rbp+27A0h+var_40]
0x1401c369a  xor     rcx, rsp; StackCookie
0x1401c369d  call    __security_check_cookie
0x1401c36a2  mov     rbx, [rsp+28A0h+arg_0]
0x1401c36aa  add     rsp, 2870h
0x1401c36b1  pop     r15
0x1401c36b3  pop     r14
0x1401c36b5  pop     r13
0x1401c36b7  pop     r12
0x1401c36b9  pop     rdi
0x1401c36ba  pop     rsi
0x1401c36bb  pop     rbp
0x1401c36bc  retn
```
