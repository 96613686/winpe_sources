# MvPackKeys(std::vector<uchar,std::allocator<uchar>> &,IMVKey * *,ulong)

- ea: `0x180036c7c`
- end: `0x180036e29`
- name: `?MvPackKeys@@YAXAEAV?$vector@EV?$allocator@E@std@@@std@@PEAPEAUIMVKey@@K@Z`
- size: `429`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002a4f8`

## callees

- `0x180012d80`
- `0x180036c7c`
- `0x180037274`
- `0x18003f010`

## string_xrefs

- `0x180036de6`: `onecoreuap\admin\prov\multivariant\common\src\mvprovisiondatahelper.cpp`
- `0x180036dfc`: `onecoreuap\admin\prov\multivariant\common\src\mvprovisiondatahelper.cpp`
- `0x180036e17`: `onecoreuap\admin\prov\multivariant\common\src\mvprovisiondatahelper.cpp`

## pseudocode

```c
__int64 __fastcall MvPackKeys(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 result; // rax
  __int64 i; // r15
  __int64 v8; // rcx
  int v9; // eax
  __int16 *j; // r14
  __int16 v11; // di
  int v12; // eax
  __int16 *k; // r14
  __int16 v14; // di
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+38h]
  char v17; // [rsp+70h] [rbp+50h] BYREF
  __int16 *v18; // [rsp+78h] [rbp+58h] BYREF

  if ( a3 > 0xFFFF )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1AD,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\mvprovisiondatahelper.cpp",
      (const char *)0x80070216LL,
      savedregs);
  v17 = a3;
  std::vector<unsigned char>::push_back(a1, &v17);
  v17 = BYTE1(a3);
  result = std::vector<unsigned char>::push_back(a1, &v17);
  for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
  {
    v8 = *(_QWORD *)(a2 + 8 * i);
    v18 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, __int16 **))(*(_QWORD *)v8 + 40LL))(v8, &v18);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1B4,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\mvprovisiondatahelper.cpp",
        (const char *)(unsigned int)v9,
        savedregs);
    for ( j = v18; ; ++j )
    {
      v11 = *j;
      if ( !*j )
        break;
      v17 = *j;
      std::vector<unsigned char>::push_back(a1, &v17);
      v17 = HIBYTE(v11);
      std::vector<unsigned char>::push_back(a1, &v17);
    }
    v17 = 61;
    std::vector<unsigned char>::push_back(a1, &v17);
    v17 = 0;
    std::vector<unsigned char>::push_back(a1, &v17);
    v12 = (*(__int64 (__fastcall **)(_QWORD, __int16 **))(**(_QWORD **)(a2 + 8 * i) + 48LL))(
            *(_QWORD *)(a2 + 8 * i),
            &v18);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1BE,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\mvprovisiondatahelper.cpp",
        (const char *)(unsigned int)v12,
        savedregs);
    for ( k = v18; ; ++k )
    {
      v14 = *k;
      if ( !*k )
        break;
      v17 = *k;
      std::vector<unsigned char>::push_back(a1, &v17);
      v17 = HIBYTE(v14);
      std::vector<unsigned char>::push_back(a1, &v17);
    }
    v17 = 0;
    std::vector<unsigned char>::push_back(a1, &v17);
    v17 = 0;
    result = std::vector<unsigned char>::push_back(a1, &v17);
  }
  return result;
}

```

## disassembly

```asm
0x180036c7c  mov     [rsp-38h+arg_0], rbx
0x180036c81  push    rbp
0x180036c82  push    rsi
0x180036c83  push    rdi
0x180036c84  push    r12
0x180036c86  push    r13
0x180036c88  push    r14
0x180036c8a  push    r15; int
0x180036c8c  mov     rbp, rsp
0x180036c8f  sub     rsp, 20h
0x180036c93  mov     esi, r8d
0x180036c96  mov     r12, rdx
0x180036c99  mov     rbx, rcx
0x180036c9c  cmp     r8d, 0FFFFh
0x180036ca3  ja      loc_180036DF8
0x180036ca9  lea     rdx, [rbp+arg_10]
0x180036cad  mov     [rbp+arg_10], sil
0x180036cb1  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x180036cb6  movzx   eax, si
0x180036cb9  lea     rdx, [rbp+arg_10]
0x180036cbd  shr     ax, 8
0x180036cc1  mov     rcx, rbx
0x180036cc4  mov     [rbp+arg_10], al
0x180036cc7  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x180036ccc  xor     r15d, r15d
0x180036ccf  test    esi, esi
0x180036cd1  jz      loc_180036DCE
0x180036cd7  mov     rcx, [r12+r15*8]
0x180036cdb  lea     rdx, [rbp+arg_18]
0x180036cdf  mov     [rbp+arg_18], 0
0x180036ce7  mov     rax, [rcx]
0x180036cea  mov     rax, [rax+28h]
0x180036cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036cf3  mov     rcx, [rbp+38h]; this
0x180036cf7  test    eax, eax
0x180036cf9  js      loc_180036DE3
0x180036cff  mov     r14, [rbp+arg_18]
0x180036d03  jmp     short loc_180036D26
0x180036d05  mov     [rbp+arg_10], dil
0x180036d09  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x180036d0e  shr     di, 8
0x180036d12  lea     rdx, [rbp+arg_10]
0x180036d16  mov     rcx, rbx
0x180036d19  mov     [rbp+arg_10], dil
0x180036d1d  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x180036d22  lea     r14, [r14+2]
0x180036d26  movzx   edi, word ptr [r14]
0x180036d2a  lea     rdx, [rbp+arg_10]
0x180036d2e  xor     eax, eax
0x180036d30  mov     rcx, rbx
0x180036d33  cmp     ax, di
0x180036d36  jnz     short loc_180036D05
0x180036d38  mov     [rbp+arg_10], 3Dh ; '='
0x180036d3c  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x180036d41  lea     rdx, [rbp+arg_10]
0x180036d45  mov     [rbp+arg_10], 0
0x180036d49  mov     rcx, rbx
0x180036d4c  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x180036d51  mov     rcx, [r12+r15*8]
0x180036d55  lea     rdx, [rbp+arg_18]
0x180036d59  mov     rax, [rcx]
0x180036d5c  mov     rax, [rax+30h]
0x180036d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036d65  mov     rcx, [rbp+38h]; this
0x180036d69  test    eax, eax
0x180036d6b  js      loc_180036E14
0x180036d71  mov     r14, [rbp+arg_18]
0x180036d75  jmp     short loc_180036D98
0x180036d77  mov     [rbp+arg_10], dil
0x180036d7b  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x180036d80  shr     di, 8
0x180036d84  lea     rdx, [rbp+arg_10]
0x180036d88  mov     rcx, rbx
0x180036d8b  mov     [rbp+arg_10], dil
0x180036d8f  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x180036d94  lea     r14, [r14+2]
0x180036d98  movzx   edi, word ptr [r14]
0x180036d9c  lea     rdx, [rbp+arg_10]
0x180036da0  xor     eax, eax
0x180036da2  mov     rcx, rbx
0x180036da5  cmp     ax, di
0x180036da8  jnz     short loc_180036D77
0x180036daa  mov     [rbp+arg_10], al
0x180036dad  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x180036db2  lea     rdx, [rbp+arg_10]
0x180036db6  mov     [rbp+arg_10], 0
0x180036dba  mov     rcx, rbx
0x180036dbd  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x180036dc2  inc     r15d
0x180036dc5  cmp     r15d, esi
0x180036dc8  jb      loc_180036CD7
0x180036dce  mov     rbx, [rsp+20h+arg_0]
0x180036dd3  add     rsp, 20h
0x180036dd7  pop     r15
0x180036dd9  pop     r14
0x180036ddb  pop     r13
0x180036ddd  pop     r12
0x180036ddf  pop     rdi
0x180036de0  pop     rsi
0x180036de1  pop     rbp
0x180036de2  retn
0x180036de3  mov     r9d, eax; char *
0x180036de6  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180036ded  mov     edx, 1B4h; void *
0x180036df2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036df8  mov     rcx, [rbp+38h]; this
0x180036dfc  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180036e03  mov     r9d, 80070216h; char *
0x180036e09  mov     edx, 1ADh; void *
0x180036e0e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036e14  mov     r9d, eax; char *
0x180036e17  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180036e1e  mov     edx, 1BEh; void *
0x180036e23  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
