# TDataGetter<ushort *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,TNDFDeallocator<ushort * *,&FreeDependencies(ushort * *,ulong,int)>,&CopyAndAllocateDependency(ushort * *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const *)>(ushort * * *,ulong *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18000b7a0`
- end: `0x18000b904`
- name: `??$TDataGetter@PEAG$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@V?$TNDFDeallocator@PEAPEAG$1?FreeDependencies@@YAXPEAPEAGKH@Z@@$1?CopyAndAllocateDependency@@YAJPEAPEAGPEBV12@@Z@@YAJPEAPEAPEAGPEAKAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000da20`

## callees

- `0x18000b7a0`
- `0x18000c598`
- `0x18000d0bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b8ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b8dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b8ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b8dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b7e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b7e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TDataGetter<unsigned short *,std::wstring const,std::vector<std::wstring>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,TNDFDeallocator<unsigned short * *,&void FreeDependencies(unsigned short * *,unsigned long,int)>,&long CopyAndAllocateDependency(unsigned short * *,std::wstring const *)>(
        LPVOID **a1,
        _DWORD *a2,
        __int64 *a3)
{
  unsigned __int64 v4; // rdi
  __int64 v6; // rbx
  LPVOID *v7; // rax
  LPVOID *v8; // r14
  unsigned int v9; // r15d
  LPVOID *v10; // rsi
  int v11; // r12d
  int Dependency; // ebp
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 i; // rdi
  int v18; // [rsp+80h] [rbp+18h]

  v4 = (a3[1] - *a3) >> 5;
  if ( v4 )
  {
    v6 = 8 * v4;
    v7 = (LPVOID *)CoTaskMemAlloc(8 * v4);
    v8 = v7;
    if ( v7 )
    {
      for ( ; v6; --v6 )
      {
        *(_BYTE *)v7 = 0;
        v7 = (LPVOID *)((char *)v7 + 1);
      }
      v9 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v4);
      v10 = v8;
      v11 = 1;
      Dependency = 0;
      v13 = *a3;
      v14 = 0;
      v18 = 0;
      do
      {
        if ( v13 == a3[1] )
          break;
        if ( Dependency < 0 )
          goto LABEL_13;
        Dependency = CopyAndAllocateDependency((unsigned __int16 **)&v8[v14]);
        v13 += 32;
        v14 = (unsigned int)(v18 + 1);
        v18 = v14;
      }
      while ( (unsigned int)v14 < v4 );
      if ( Dependency >= 0 )
      {
        v10 = 0;
        v9 = 0;
        v11 = 0;
        *a1 = v8;
        *a2 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v4);
      }
LABEL_13:
      if ( v10 )
      {
        for ( i = 0; (unsigned int)i < v9; i = (unsigned int)(i + 1) )
        {
          CoTaskMemFree(v10[i]);
          v10[i] = 0;
        }
        if ( v11 )
          CoTaskMemFree(v10);
      }
      return (unsigned int)Dependency;
    }
    else
    {
      return 2147942414LL;
    }
  }
  else
  {
    *a2 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x18000b7a0  mov     [rsp+arg_18], rbx
0x18000b7a5  mov     [rsp+arg_8], rdx
0x18000b7aa  mov     [rsp+arg_0], rcx
0x18000b7af  push    rbp
0x18000b7b0  push    rsi
0x18000b7b1  push    rdi
0x18000b7b2  push    r12
0x18000b7b4  push    r13
0x18000b7b6  push    r14
0x18000b7b8  push    r15
0x18000b7ba  sub     rsp, 30h
0x18000b7be  mov     r13, r8
0x18000b7c1  mov     rdi, [r8+8]
0x18000b7c5  sub     rdi, [r8]
0x18000b7c8  sar     rdi, 5
0x18000b7cc  test    rdi, rdi
0x18000b7cf  jnz     short loc_18000B7DA
0x18000b7d1  mov     [rdx], edi
0x18000b7d3  xor     eax, eax
0x18000b7d5  jmp     loc_18000B8EB
0x18000b7da  lea     rbx, ds:0[rdi*8]
0x18000b7e2  mov     rcx, rbx; cb
0x18000b7e5  call    cs:__imp_CoTaskMemAlloc
0x18000b7ec  nop     dword ptr [rax+rax+00h]
0x18000b7f1  mov     r14, rax
0x18000b7f4  test    rax, rax
0x18000b7f7  jnz     short loc_18000B803
0x18000b7f9  mov     eax, 8007000Eh
0x18000b7fe  jmp     loc_18000B8EB
0x18000b803  test    rbx, rbx
0x18000b806  jz      short loc_18000B814
0x18000b808  mov     byte ptr [rax], 0
0x18000b80b  inc     rax
0x18000b80e  sub     rbx, 1
0x18000b812  jnz     short loc_18000B808
0x18000b814  mov     rcx, rdi
0x18000b817  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000b81c  mov     r15d, eax
0x18000b81f  mov     rsi, r14
0x18000b822  mov     [rsp+68h+var_48], r14
0x18000b827  mov     dword ptr [rsp+68h+var_40], eax
0x18000b82b  mov     r12d, 1
0x18000b831  mov     dword ptr [rsp+68h+var_40+4], r12d
0x18000b836  xor     ebp, ebp
0x18000b838  mov     rbx, [r13+0]
0x18000b83c  xor     eax, eax
0x18000b83e  mov     [rsp+68h+arg_10], eax
0x18000b845  test    rdi, rdi
0x18000b848  jz      short loc_18000B881
0x18000b84a  cmp     rbx, [r13+8]
0x18000b84e  jz      short loc_18000B87D
0x18000b850  test    ebp, ebp
0x18000b852  js      short loc_18000B8AA
0x18000b854  lea     rcx, [r14+rax*8]; unsigned __int16 **
0x18000b858  mov     rdx, rbx
0x18000b85b  call    ?CopyAndAllocateDependency@@YAJPEAPEAGPEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CopyAndAllocateDependency(ushort * *,std::wstring const *)
0x18000b860  mov     ebp, eax
0x18000b862  add     rbx, 20h ; ' '
0x18000b866  mov     eax, [rsp+68h+arg_10]
0x18000b86d  inc     eax
0x18000b86f  mov     [rsp+68h+arg_10], eax
0x18000b876  mov     ecx, eax
0x18000b878  cmp     rcx, rdi
0x18000b87b  jb      short loc_18000B84A
0x18000b87d  test    ebp, ebp
0x18000b87f  js      short loc_18000B8AA
0x18000b881  xor     esi, esi
0x18000b883  mov     [rsp+68h+var_48], rsi
0x18000b888  xor     r15d, r15d
0x18000b88b  mov     [rsp+68h+var_40], r15
0x18000b890  xor     r12d, r12d
0x18000b893  mov     rax, [rsp+68h+arg_0]
0x18000b898  mov     [rax], r14
0x18000b89b  mov     rcx, rdi
0x18000b89e  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000b8a3  mov     rcx, [rsp+68h+arg_8]
0x18000b8a8  mov     [rcx], eax
0x18000b8aa  test    rsi, rsi
0x18000b8ad  jz      short loc_18000B8E9
0x18000b8af  xor     edi, edi
0x18000b8b1  test    r15d, r15d
0x18000b8b4  jz      short loc_18000B8D5
0x18000b8b6  mov     rcx, [rsi+rdi*8]; pv
0x18000b8ba  call    cs:__imp_CoTaskMemFree
0x18000b8c1  nop     dword ptr [rax+rax+00h]
0x18000b8c6  mov     qword ptr [rsi+rdi*8], 0
0x18000b8ce  inc     edi
0x18000b8d0  cmp     edi, r15d
0x18000b8d3  jb      short loc_18000B8B6
0x18000b8d5  test    r12d, r12d
0x18000b8d8  jz      short loc_18000B8E9
0x18000b8da  mov     rcx, rsi; pv
0x18000b8dd  call    cs:__imp_CoTaskMemFree
0x18000b8e4  nop     dword ptr [rax+rax+00h]
0x18000b8e9  mov     eax, ebp
0x18000b8eb  mov     rbx, [rsp+68h+arg_18]
0x18000b8f3  add     rsp, 30h
0x18000b8f7  pop     r15
0x18000b8f9  pop     r14
0x18000b8fb  pop     r13
0x18000b8fd  pop     r12
0x18000b8ff  pop     rdi
0x18000b900  pop     rsi
0x18000b901  pop     rbp
0x18000b902  retn
```
