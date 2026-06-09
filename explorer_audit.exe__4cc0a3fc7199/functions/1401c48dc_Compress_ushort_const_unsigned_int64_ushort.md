# Compress(ushort const *,unsigned __int64,ushort * *)

- ea: `0x1401c48dc`
- end: `0x1401c4b37`
- name: `?Compress@@YAJPEBG_KPEAPEAG@Z`
- size: `603`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1401c6d80`

## callees

- `0x140034af0`
- `0x1400353c0`
- `0x1400954e0`
- `0x1401040e0`
- `0x140104ce0`
- `0x1401c48dc`
- `0x1401c4b40`
- `0x1401c5c3c`
- `0x1401c7124`
- `0x1401c7160`
- `0x1401d3480`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1401c4a99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1401c4aac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1401c4ae3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1401c4a99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1401c4aac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1401c4ae3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1401c4929`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1401c4a0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1401c4929`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1401c4a0c`

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
  inverted::vector_nothrow<unsigned __int64>::push_back(&v23, &unk_14020FAA0);
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
0x1401c48dc  mov     [rsp-8+arg_0], rbx
0x1401c48e1  push    rbp
0x1401c48e2  push    rsi
0x1401c48e3  push    rdi
0x1401c48e4  push    r12
0x1401c48e6  push    r13
0x1401c48e8  push    r14
0x1401c48ea  push    r15
0x1401c48ec  lea     rbp, [rsp-2770h]
0x1401c48f4  mov     eax, 2870h
0x1401c48f9  call    _alloca_probe
0x1401c48fe  sub     rsp, rax
0x1401c4901  mov     rax, cs:__security_cookie
0x1401c4908  xor     rax, rsp
0x1401c490b  mov     [rbp+27A0h+var_40], rax
0x1401c4912  mov     rsi, r8
0x1401c4915  mov     rbx, rdx
0x1401c4918  mov     r14, rcx
0x1401c491b  xor     r13d, r13d
0x1401c491e  mov     [r8], r13
0x1401c4921  lea     rcx, ds:0[rdx*4]; cb
0x1401c4929  call    cs:__imp_CoTaskMemAlloc
0x1401c492f  mov     rdi, rax
0x1401c4932  test    rax, rax
0x1401c4935  jz      loc_1401C4AEB
0x1401c493b  mov     edx, r13d
0x1401c493e  test    rbx, rbx
0x1401c4941  jz      short loc_1401C4953
0x1401c4943  movzx   ecx, word ptr [r14+rdx*2]
0x1401c4948  mov     [rax+rdx*4], ecx
0x1401c494b  inc     rdx
0x1401c494e  cmp     rdx, rbx
0x1401c4951  jb      short loc_1401C4943
0x1401c4953  xorps   xmm0, xmm0
0x1401c4956  movdqa  [rsp+28A0h+var_2870], xmm0
0x1401c495c  mov     [rsp+28A0h+var_2860], r13
0x1401c4961  lea     rcx, [rsp+28A0h+var_2870]
0x1401c4966  call    ?clear@?$vector_nothrow@_K@inverted@@QEAAXXZ; inverted::vector_nothrow<unsigned __int64>::clear(void)
0x1401c496b  lea     rdx, unk_14020FAA0
0x1401c4972  lea     rcx, [rsp+28A0h+var_2870]
0x1401c4977  call    ?push_back@?$vector_nothrow@_K@inverted@@QEAAXAEB_K@Z; inverted::vector_nothrow<unsigned __int64>::push_back(unsigned __int64 const &)
0x1401c497c  mov     [rsp+28A0h+var_2854], r13d
0x1401c4981  mov     rax, 0FBFFFFFFFFFFFFFFh
0x1401c498b  mov     [rsp+28A0h+var_2850], rax
0x1401c4990  xor     edx, edx; Val
0x1401c4992  mov     r8d, 2808h; Size
0x1401c4998  lea     rcx, [rsp+28A0h+var_2848]; void *
0x1401c499d  call    memset_0
0x1401c49a2  mov     [rsp+28A0h+var_2858], r13d
0x1401c49a7  mov     [rsp+28A0h+var_2880], r13d; int
0x1401c49ac  lea     r9, [rsp+28A0h+var_2880]; unsigned int *
0x1401c49b1  mov     r8d, ebx; unsigned int
0x1401c49b4  mov     rdx, rdi; unsigned int *
0x1401c49b7  lea     rcx, [rsp+28A0h+var_2870]; this
0x1401c49bc  call    ?Compress@CSimple256Compressor@inverted@@AEAAXPEBIIPEAI@Z; inverted::CSimple256Compressor::Compress(uint const *,uint,uint *)
0x1401c49c1  sub     ebx, [rsp+28A0h+var_2880]
0x1401c49c5  mov     eax, [rsp+28A0h+var_2880]
0x1401c49c9  lea     rdx, [rdi+rax*4]; unsigned int *
0x1401c49cd  mov     r8d, ebx; unsigned int
0x1401c49d0  lea     rcx, [rsp+28A0h+var_2870]; this
0x1401c49d5  call    ?CompressRemainder@CSimple256Compressor@inverted@@AEAAXPEBII@Z; inverted::CSimple256Compressor::CompressRemainder(uint const *,uint)
0x1401c49da  mov     rdx, [rsp+28A0h+var_2860]
0x1401c49df  mov     rcx, rdx
0x1401c49e2  shl     rcx, 20h
0x1401c49e6  mov     eax, [rsp+28A0h+var_2858]
0x1401c49ea  or      rcx, rax
0x1401c49ed  mov     r12, qword ptr [rsp+28A0h+var_2870]
0x1401c49f2  mov     [r12], rcx
0x1401c49f6  mov     r15d, edx
0x1401c49f9  lea     r14d, ds:0[r15*4]
0x1401c4a01  movsxd  rcx, r14d
0x1401c4a04  lea     rcx, ds:2[rcx*2]; cb
0x1401c4a0c  call    cs:__imp_CoTaskMemAlloc
0x1401c4a12  mov     rbx, rax
0x1401c4a15  test    rax, rax
0x1401c4a18  jz      loc_1401C4AB6
0x1401c4a1e  mov     edx, r13d
0x1401c4a21  mov     r9, r13
0x1401c4a24  test    r15d, r15d
0x1401c4a27  jz      short loc_1401C4A65
0x1401c4a29  cmp     edx, r14d
0x1401c4a2c  jge     short loc_1401C4A65
0x1401c4a2e  mov     r8, r13
0x1401c4a31  cmp     edx, r14d
0x1401c4a34  jge     short loc_1401C4A5D
0x1401c4a36  mov     cl, r8b
0x1401c4a39  shl     cl, 3
0x1401c4a3c  mov     r10, [r12+r9*8]
0x1401c4a40  shr     r10, cl
0x1401c4a43  test    r10w, r10w
0x1401c4a47  jz      short loc_1401C4A53
0x1401c4a49  movsxd  rax, edx
0x1401c4a4c  mov     [rbx+rax*2], r10w
0x1401c4a51  inc     edx
0x1401c4a53  add     r8, 2
0x1401c4a57  cmp     r8, 8
0x1401c4a5b  jb      short loc_1401C4A31
0x1401c4a5d  inc     r9
0x1401c4a60  cmp     r9, r15
0x1401c4a63  jb      short loc_1401C4A29
0x1401c4a65  movsxd  rcx, edx
0x1401c4a68  mov     [rbx+rcx*2], r13w
0x1401c4a6d  or      r8, 0FFFFFFFFFFFFFFFFh
0x1401c4a71  mov     rdx, rbx
0x1401c4a74  lea     rcx, [rsp+28A0h+var_2880]
0x1401c4a79  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1401c4a7e  mov     rax, qword ptr [rsp+28A0h+var_2880]
0x1401c4a83  mov     qword ptr [rsp+28A0h+var_2880], r13
0x1401c4a88  mov     [rsi], rax
0x1401c4a8b  lea     rcx, [rsp+28A0h+var_2880]
0x1401c4a90  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1401c4a95  nop
0x1401c4a96  mov     rcx, rbx; pv
0x1401c4a99  call    cs:__imp_CoTaskMemFree
0x1401c4a9f  lea     rcx, [rsp+28A0h+var_2870]
0x1401c4aa4  call    ?clear@?$vector_nothrow@_K@inverted@@QEAAXXZ; inverted::vector_nothrow<unsigned __int64>::clear(void)
0x1401c4aa9  mov     rcx, rdi; pv
0x1401c4aac  call    cs:__imp_CoTaskMemFree
0x1401c4ab2  xor     eax, eax
0x1401c4ab4  jmp     short loc_1401C4B0D
0x1401c4ab6  mov     rcx, [rbp+27A8h]; this
0x1401c4abd  mov     ebx, 8007000Eh
0x1401c4ac2  mov     r9d, ebx; char *
0x1401c4ac5  lea     r8, aOnecoreShellLi_1; "onecore\\shell\\lib\\userchoicehelpers"...
0x1401c4acc  mov     edx, 150h; void *
0x1401c4ad1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401c4ad6  lea     rcx, [rsp+28A0h+var_2870]
0x1401c4adb  call    ?clear@?$vector_nothrow@_K@inverted@@QEAAXXZ; inverted::vector_nothrow<unsigned __int64>::clear(void)
0x1401c4ae0  mov     rcx, rdi; pv
0x1401c4ae3  call    cs:__imp_CoTaskMemFree
0x1401c4ae9  jmp     short loc_1401C4B0B
0x1401c4aeb  mov     rcx, [rbp+27A8h]; this
0x1401c4af2  mov     ebx, 8007000Eh
0x1401c4af7  mov     r9d, ebx; char *
0x1401c4afa  lea     r8, aOnecoreShellLi_1; "onecore\\shell\\lib\\userchoicehelpers"...
0x1401c4b01  mov     edx, 140h; void *
0x1401c4b06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401c4b0b  mov     eax, ebx
0x1401c4b0d  mov     rcx, [rbp+27A0h+var_40]
0x1401c4b14  xor     rcx, rsp; StackCookie
0x1401c4b17  call    __security_check_cookie
0x1401c4b1c  mov     rbx, [rsp+28A0h+arg_0]
0x1401c4b24  add     rsp, 2870h
0x1401c4b2b  pop     r15
0x1401c4b2d  pop     r14
0x1401c4b2f  pop     r13
0x1401c4b31  pop     r12
0x1401c4b33  pop     rdi
0x1401c4b34  pop     rsi
0x1401c4b35  pop     rbp
0x1401c4b36  retn
```
