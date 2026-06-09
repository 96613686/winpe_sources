# ??$_Sort@PEAV?$shared_ptr@VCMvExtensionKey@@@std@@_JP6AHV?$shared_ptr@$$CBVCMvExtensionKey@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCMvExtensionKey@@@0@0_JP6AHV?$shared_ptr@$$CBVCMvExtensionKey@@@0@2@_E@Z

- ea: `0x180013320`
- end: `0x1800136d3`
- name: `??$_Sort@PEAV?$shared_ptr@VCMvExtensionKey@@@std@@_JP6AHV?$shared_ptr@$$CBVCMvExtensionKey@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCMvExtensionKey@@@0@0_JP6AHV?$shared_ptr@$$CBVCMvExtensionKey@@@0@2@_E@Z`
- size: `947`
- prototype: `__int64 __fastcall(__int64 *, __int64 *, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013320`
- `0x1800145f8`

## callees

- `0x18000f84c`
- `0x180013014`
- `0x180013320`
- `0x1800136dc`
- `0x180013c98`
- `0x180013d90`
- `0x18003f010`

## pseudocode

```c
__int64 __fastcall ____Sort_PEAV__shared_ptr_VCMvExtensionKey___std___JP6AHV__shared_ptr___CBVCMvExtensionKey___2_0__E_std__YAXPEAV__shared_ptr_VCMvExtensionKey___0_0_JP6AHV__shared_ptr___CBVCMvExtensionKey___0_2__E_Z(
        __int64 *a1,
        __int64 *a2,
        __int64 a3)
{
  __int64 *v4; // r14
  __int64 *v5; // rsi
  __int64 result; // rax
  __int64 *v7; // rdi
  __int64 *v8; // r15
  __int64 v9; // rbx
  __int64 v10; // r12
  __int64 *v11; // rdx
  volatile signed __int32 *v12; // rdi
  __int64 *v13; // rdi
  __int64 *v14; // r14
  volatile signed __int32 *v15; // rbx
  __int64 *v16; // rdi
  _QWORD *v17; // rbx
  _QWORD *v18; // rax
  __int64 *v19; // r12
  __int64 *v20; // rbx
  __int64 *v21; // r13
  __int64 *i; // r12
  _QWORD *v23; // rbx
  _QWORD *v24; // rax
  volatile signed __int32 *v25; // rbx
  __int128 v26; // [rsp+30h] [rbp-59h] BYREF
  __int128 v27; // [rsp+40h] [rbp-49h] BYREF
  __int128 v28; // [rsp+50h] [rbp-39h] BYREF
  __int64 *v29; // [rsp+60h] [rbp-29h] BYREF
  __int64 *v30; // [rsp+68h] [rbp-21h]
  __int64 v31; // [rsp+70h] [rbp-19h] BYREF
  __int64 v32; // [rsp+80h] [rbp-9h] BYREF
  __int64 v33[10]; // [rsp+90h] [rbp+7h] BYREF

  v4 = a2;
  v5 = a1;
  result = ((char *)a2 - (char *)a1) >> 4;
  if ( result <= 32 )
    goto LABEL_49;
  do
  {
    if ( a3 <= 0 )
      break;
    ____Unguarded_partition_PEAV__shared_ptr_VCMvExtensionKey___std__P6AHV__shared_ptr___CBVCMvExtensionKey___2_0__E_std__YA_AU__pair_PEAV__shared_ptr_VCMvExtensionKey___std__PEAV12__0_PEAV__shared_ptr_VCMvExtensionKey___0_0P6AHV__shared_ptr___CBVCMvExtensionKey___0_1__E_Z(
      &v29,
      v5,
      v4);
    a3 = a3 / 2 / 2 + a3 / 2;
    v7 = v30;
    v8 = v29;
    if ( (__int64)(((char *)v29 - (char *)v5) & 0xFFFFFFFFFFFFFFF0uLL) >= (__int64)(((char *)v4 - (char *)v30)
                                                                                  & 0xFFFFFFFFFFFFFFF0uLL) )
    {
      ____Sort_PEAV__shared_ptr_VCMvExtensionKey___std___JP6AHV__shared_ptr___CBVCMvExtensionKey___2_0__E_std__YAXPEAV__shared_ptr_VCMvExtensionKey___0_0_JP6AHV__shared_ptr___CBVCMvExtensionKey___0_2__E_Z(
        v30,
        v4,
        a3,
        CompareExtensions);
      v4 = v8;
    }
    else
    {
      ____Sort_PEAV__shared_ptr_VCMvExtensionKey___std___JP6AHV__shared_ptr___CBVCMvExtensionKey___2_0__E_std__YAXPEAV__shared_ptr_VCMvExtensionKey___0_0_JP6AHV__shared_ptr___CBVCMvExtensionKey___0_2__E_Z(
        v5,
        v29,
        a3,
        CompareExtensions);
      v5 = v7;
    }
    result = ((char *)v4 - (char *)v5) >> 4;
  }
  while ( result > 32 );
  if ( result <= 32 )
  {
LABEL_49:
    if ( result > 1 && v5 != v4 )
    {
      v16 = v5 + 2;
      while ( v16 != v4 )
      {
        v26 = 0;
        if ( &v26 != (__int128 *)v16 )
        {
          *((_QWORD *)&v26 + 1) = v16[1];
          v16[1] = 0;
          *(_QWORD *)&v26 = *v16;
          *v16 = 0;
        }
        v17 = std::shared_ptr<CMvExtensionKey const>::shared_ptr<CMvExtensionKey const>(&v29, v5);
        v18 = std::shared_ptr<CMvExtensionKey const>::shared_ptr<CMvExtensionKey const>(&v31, (__int64 *)&v26);
        if ( (unsigned int)CompareExtensions(v18, v17) )
        {
          v19 = v16 + 2;
          v20 = v16 + 2;
          while ( v16 != v5 )
          {
            v16 -= 2;
            v20 -= 2;
            std::shared_ptr<CMvExtensionKey>::operator=(v20, v16);
          }
          result = std::shared_ptr<CMvExtensionKey>::operator=(v5, &v26);
          v16 = v19;
        }
        else
        {
          v21 = v16;
          for ( i = v16; ; v21 = i )
          {
            i -= 2;
            v23 = std::shared_ptr<CMvExtensionKey const>::shared_ptr<CMvExtensionKey const>(&v32, i);
            v24 = std::shared_ptr<CMvExtensionKey const>::shared_ptr<CMvExtensionKey const>(v33, (__int64 *)&v26);
            if ( !(unsigned int)CompareExtensions(v24, v23) )
              break;
            std::shared_ptr<CMvExtensionKey>::operator=(v21, i);
          }
          result = std::shared_ptr<CMvExtensionKey>::operator=(v21, &v26);
          v16 += 2;
        }
        v25 = (volatile signed __int32 *)*((_QWORD *)&v26 + 1);
        if ( *((_QWORD *)&v26 + 1) )
        {
          result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v26 + 1) + 8LL));
          if ( !(_DWORD)result )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
            result = (unsigned int)_InterlockedDecrement(v25 + 3);
            if ( !(_DWORD)result )
              result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
          }
        }
      }
    }
  }
  else
  {
    v9 = ((char *)v4 - (char *)v5) >> 4;
    if ( v9 <= 1 || (result = v9 / 2, v10 = v9 / 2, v9 / 2 <= 0) )
    {
      v13 = v4;
      if ( v9 <= 1 )
        return result;
    }
    else
    {
      do
      {
        --v10;
        v11 = &v5[2 * v10];
        v27 = 0;
        if ( &v27 != (__int128 *)v11 )
        {
          *((_QWORD *)&v27 + 1) = v11[1];
          v11[1] = 0;
          *(_QWORD *)&v27 = *v11;
          *v11 = 0;
        }
        ____Adjust_heap_PEAV__shared_ptr_VCMvExtensionKey___std___JV12_P6AHV__shared_ptr___CBVCMvExtensionKey___2_0__E_std__YAXPEAV__shared_ptr_VCMvExtensionKey___0__J1__QEAV10_P6AHV__shared_ptr___CBVCMvExtensionKey___0_3__E_Z(
          (__int64)v5,
          v10,
          ((char *)v4 - (char *)v5) >> 4,
          (__int64 *)&v27);
        v12 = (volatile signed __int32 *)*((_QWORD *)&v27 + 1);
        if ( *((_QWORD *)&v27 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v27 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
            if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
          }
        }
      }
      while ( v10 > 0 );
      v13 = v4;
    }
    v14 = v4 - 2;
    do
    {
      v28 = 0;
      if ( &v28 != (__int128 *)v14 )
      {
        *((_QWORD *)&v28 + 1) = v14[1];
        v14[1] = 0;
        *(_QWORD *)&v28 = *v14;
        *v14 = 0;
      }
      std::shared_ptr<CMvExtensionKey>::operator=(v14, v5);
      ____Adjust_heap_PEAV__shared_ptr_VCMvExtensionKey___std___JV12_P6AHV__shared_ptr___CBVCMvExtensionKey___2_0__E_std__YAXPEAV__shared_ptr_VCMvExtensionKey___0__J1__QEAV10_P6AHV__shared_ptr___CBVCMvExtensionKey___0_3__E_Z(
        (__int64)v5,
        0,
        ((char *)v13 - (char *)v5 - 16) >> 4,
        (__int64 *)&v28);
      v15 = (volatile signed __int32 *)*((_QWORD *)&v28 + 1);
      if ( *((_QWORD *)&v28 + 1)
        && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v28 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
      v13 -= 2;
      v14 -= 2;
      result = ((char *)v13 - (char *)v5) & 0xFFFFFFFFFFFFFFF0uLL;
    }
    while ( result > 16 );
  }
  return result;
}

```

## disassembly

```asm
0x180013320  push    rbp
0x180013322  push    rbx
0x180013323  push    rsi
0x180013324  push    rdi
0x180013325  push    r12
0x180013327  push    r13
0x180013329  push    r14
0x18001332b  push    r15
0x18001332d  lea     rbp, [rsp-1Fh]
0x180013332  sub     rsp, 0A8h
0x180013339  mov     rbx, r8
0x18001333c  mov     r14, rdx
0x18001333f  mov     rsi, rcx
0x180013342  mov     rax, rdx
0x180013345  sub     rax, rcx
0x180013348  sar     rax, 4
0x18001334c  xor     r13d, r13d
0x18001334f  cmp     rax, 20h ; ' '
0x180013353  jle     loc_180013578
0x180013359  test    rbx, rbx
0x18001335c  jle     loc_1800133E7
0x180013362  mov     r8, r14
0x180013365  mov     rdx, rsi
0x180013368  lea     rcx, [rbp+57h+var_80]
0x18001336c  call    ??$_Unguarded_partition@PEAV?$shared_ptr@VCMvExtensionKey@@@std@@P6AHV?$shared_ptr@$$CBVCMvExtensionKey@@@2@0@_E@std@@YA?AU?$pair@PEAV?$shared_ptr@VCMvExtensionKey@@@std@@PEAV12@@0@PEAV?$shared_ptr@VCMvExtensionKey@@@0@0P6AHV?$shared_ptr@$$CBVCMvExtensionKey@@@0@1@_E@Z
0x180013371  mov     rax, rbx
0x180013374  cqo
0x180013376  sub     rax, rdx
0x180013379  sar     rax, 1
0x18001337c  mov     rbx, rax
0x18001337f  cqo
0x180013381  sub     rax, rdx
0x180013384  sar     rax, 1
0x180013387  add     rbx, rax
0x18001338a  mov     rcx, r14
0x18001338d  mov     rdi, [rbp+57h+var_78]
0x180013391  sub     rcx, rdi
0x180013394  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180013398  mov     r15, [rbp+57h+var_80]
0x18001339c  mov     rax, r15
0x18001339f  sub     rax, rsi
0x1800133a2  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800133a6  lea     r9, ?CompareExtensions@@YAHV?$shared_ptr@$$CBVCMvExtensionKey@@@std@@0@Z; CompareExtensions(std::shared_ptr<CMvExtensionKey const>,std::shared_ptr<CMvExtensionKey const>)
0x1800133ad  mov     r8, rbx
0x1800133b0  cmp     rax, rcx
0x1800133b3  jge     short loc_1800133C5
0x1800133b5  mov     rdx, r15
0x1800133b8  mov     rcx, rsi
0x1800133bb  call    ??$_Sort@PEAV?$shared_ptr@VCMvExtensionKey@@@std@@_JP6AHV?$shared_ptr@$$CBVCMvExtensionKey@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCMvExtensionKey@@@0@0_JP6AHV?$shared_ptr@$$CBVCMvExtensionKey@@@0@2@_E@Z
0x1800133c0  mov     rsi, rdi
0x1800133c3  jmp     short loc_1800133D3
0x1800133c5  mov     rdx, r14
0x1800133c8  mov     rcx, rdi
0x1800133cb  call    ??$_Sort@PEAV?$shared_ptr@VCMvExtensionKey@@@std@@_JP6AHV?$shared_ptr@$$CBVCMvExtensionKey@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCMvExtensionKey@@@0@0_JP6AHV?$shared_ptr@$$CBVCMvExtensionKey@@@0@2@_E@Z
0x1800133d0  mov     r14, r15
0x1800133d3  mov     rax, r14
0x1800133d6  sub     rax, rsi
0x1800133d9  sar     rax, 4
0x1800133dd  cmp     rax, 20h ; ' '
0x1800133e1  jg      loc_180013359
0x1800133e7  cmp     rax, 20h ; ' '
0x1800133eb  jle     loc_180013578
0x1800133f1  mov     rbx, r14
0x1800133f4  sub     rbx, rsi
0x1800133f7  sar     rbx, 4
0x1800133fb  or      r15d, 0FFFFFFFFh
0x1800133ff  cmp     rbx, 1
0x180013403  jle     loc_1800134B6
0x180013409  mov     rax, rbx
0x18001340c  cqo
0x18001340e  sub     rax, rdx
0x180013411  sar     rax, 1
0x180013414  mov     r12, rax
0x180013417  test    rax, rax
0x18001341a  jle     loc_1800134B6
0x180013420  dec     r12
0x180013423  mov     rdx, r12
0x180013426  shl     rdx, 4
0x18001342a  add     rdx, rsi
0x18001342d  xorps   xmm0, xmm0
0x180013430  movdqu  [rbp+57h+var_A0], xmm0
0x180013435  lea     rax, [rbp+57h+var_A0]
0x180013439  cmp     rax, rdx
0x18001343c  jz      short loc_180013454
0x18001343e  mov     rax, [rdx+8]
0x180013442  mov     qword ptr [rbp+57h+var_A0+8], rax
0x180013446  mov     [rdx+8], r13
0x18001344a  mov     rax, [rdx]
0x18001344d  mov     qword ptr [rbp+57h+var_A0], rax
0x180013451  mov     [rdx], r13
0x180013454  lea     r9, [rbp+57h+var_A0]
0x180013458  mov     r8, rbx
0x18001345b  mov     rdx, r12
0x18001345e  mov     rcx, rsi
0x180013461  call    ??$_Adjust_heap@PEAV?$shared_ptr@VCMvExtensionKey@@@std@@_JV12@P6AHV?$shared_ptr@$$CBVCMvExtensionKey@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCMvExtensionKey@@@0@_J1$$QEAV10@P6AHV?$shared_ptr@$$CBVCMvExtensionKey@@@0@3@_E@Z
0x180013466  nop
0x180013467  mov     rdi, qword ptr [rbp+57h+var_A0+8]
0x18001346b  test    rdi, rdi
0x18001346e  jz      short loc_1800134A8
0x180013470  mov     eax, r15d
0x180013473  lock xadd [rdi+8], eax
0x180013478  add     eax, r15d
0x18001347b  jnz     short loc_1800134A8
0x18001347d  mov     rax, [rdi]
0x180013480  mov     rcx, rdi
0x180013483  mov     rax, [rax]
0x180013486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001348b  mov     eax, r15d
0x18001348e  lock xadd [rdi+0Ch], eax
0x180013493  add     eax, r15d
0x180013496  jnz     short loc_1800134A8
0x180013498  mov     rax, [rdi]
0x18001349b  mov     rcx, rdi
0x18001349e  mov     rax, [rax+8]
0x1800134a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134a7  nop
0x1800134a8  test    r12, r12
0x1800134ab  jg      loc_180013420
0x1800134b1  mov     rdi, r14
0x1800134b4  jmp     short loc_1800134C3
0x1800134b6  mov     rdi, r14
0x1800134b9  cmp     rbx, 1
0x1800134bd  jle     loc_1800136BF
0x1800134c3  add     r14, 0FFFFFFFFFFFFFFF0h
0x1800134c7  xorps   xmm0, xmm0
0x1800134ca  movdqu  [rbp+57h+var_90], xmm0
0x1800134cf  lea     rax, [rbp+57h+var_90]
0x1800134d3  cmp     rax, r14
0x1800134d6  jz      short loc_1800134EE
0x1800134d8  mov     rax, [r14+8]
0x1800134dc  mov     qword ptr [rbp+57h+var_90+8], rax
0x1800134e0  mov     [r14+8], r13
0x1800134e4  mov     rax, [r14]
0x1800134e7  mov     qword ptr [rbp+57h+var_90], rax
0x1800134eb  mov     [r14], r13
0x1800134ee  mov     rdx, rsi
0x1800134f1  mov     rcx, r14
0x1800134f4  call    ??4?$shared_ptr@VCMvExtensionKey@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CMvExtensionKey>::operator=(std::shared_ptr<CMvExtensionKey> &&)
0x1800134f9  mov     r8, rdi
0x1800134fc  sub     r8, rsi
0x1800134ff  sub     r8, 10h
0x180013503  sar     r8, 4
0x180013507  lea     r9, [rbp+57h+var_90]
0x18001350b  xor     edx, edx
0x18001350d  mov     rcx, rsi
0x180013510  call    ??$_Adjust_heap@PEAV?$shared_ptr@VCMvExtensionKey@@@std@@_JV12@P6AHV?$shared_ptr@$$CBVCMvExtensionKey@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCMvExtensionKey@@@0@_J1$$QEAV10@P6AHV?$shared_ptr@$$CBVCMvExtensionKey@@@0@3@_E@Z
0x180013515  nop
0x180013516  mov     rbx, qword ptr [rbp+57h+var_90+8]
0x18001351a  test    rbx, rbx
0x18001351d  jz      short loc_180013557
0x18001351f  mov     eax, r15d
0x180013522  lock xadd [rbx+8], eax
0x180013527  add     eax, r15d
0x18001352a  jnz     short loc_180013557
0x18001352c  mov     rax, [rbx]
0x18001352f  mov     rcx, rbx
0x180013532  mov     rax, [rax]
0x180013535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001353a  mov     eax, r15d
0x18001353d  lock xadd [rbx+0Ch], eax
0x180013542  add     eax, r15d
0x180013545  jnz     short loc_180013557
0x180013547  mov     rax, [rbx]
0x18001354a  mov     rcx, rbx
0x18001354d  mov     rax, [rax+8]
0x180013551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013556  nop
0x180013557  sub     rdi, 10h
0x18001355b  sub     r14, 10h
0x18001355f  mov     rax, rdi
0x180013562  sub     rax, rsi
0x180013565  and     rax, 0FFFFFFFFFFFFFFF0h
0x180013569  cmp     rax, 10h
0x18001356d  jg      loc_1800134C7
0x180013573  jmp     loc_1800136BF
0x180013578  cmp     rax, 1
0x18001357c  jle     loc_1800136BF
0x180013582  cmp     rsi, r14
0x180013585  jz      loc_1800136BF
0x18001358b  lea     rdi, [rsi+10h]
0x18001358f  cmp     rdi, r14
0x180013592  jz      loc_1800136BF
0x180013598  or      r15d, 0FFFFFFFFh
0x18001359c  xorps   xmm0, xmm0
0x18001359f  movdqu  [rbp+57h+var_B0], xmm0
0x1800135a4  lea     rax, [rbp+57h+var_B0]
0x1800135a8  cmp     rax, rdi
0x1800135ab  jz      short loc_1800135C3
0x1800135ad  mov     rax, [rdi+8]
0x1800135b1  mov     qword ptr [rbp+57h+var_B0+8], rax
0x1800135b5  mov     [rdi+8], r13
0x1800135b9  mov     rax, [rdi]
0x1800135bc  mov     qword ptr [rbp+57h+var_B0], rax
0x1800135c0  mov     [rdi], r13
0x1800135c3  mov     rdx, rsi
0x1800135c6  lea     rcx, [rbp+57h+var_80]
0x1800135ca  call    ??$?0VCMvExtensionKey@@@?$shared_ptr@$$CBVCMvExtensionKey@@@std@@QEAA@AEBV?$shared_ptr@VCMvExtensionKey@@@1@PEAPEAX@Z; std::shared_ptr<CMvExtensionKey const>::shared_ptr<CMvExtensionKey const>(std::shared_ptr<CMvExtensionKey> const &,void * *)
0x1800135cf  mov     rbx, rax
0x1800135d2  lea     rdx, [rbp+57h+var_B0]
0x1800135d6  lea     rcx, [rbp+57h+var_70]
0x1800135da  call    ??$?0VCMvExtensionKey@@@?$shared_ptr@$$CBVCMvExtensionKey@@@std@@QEAA@AEBV?$shared_ptr@VCMvExtensionKey@@@1@PEAPEAX@Z; std::shared_ptr<CMvExtensionKey const>::shared_ptr<CMvExtensionKey const>(std::shared_ptr<CMvExtensionKey> const &,void * *)
0x1800135df  mov     rdx, rbx
0x1800135e2  mov     rcx, rax
0x1800135e5  call    ?CompareExtensions@@YAHV?$shared_ptr@$$CBVCMvExtensionKey@@@std@@0@Z; CompareExtensions(std::shared_ptr<CMvExtensionKey const>,std::shared_ptr<CMvExtensionKey const>)
0x1800135ea  test    eax, eax
0x1800135ec  jz      short loc_180013620
0x1800135ee  lea     r12, [rdi+10h]
0x1800135f2  mov     rbx, r12
0x1800135f5  jmp     short loc_18001360A
0x1800135f7  sub     rdi, 10h
0x1800135fb  sub     rbx, 10h
0x1800135ff  mov     rdx, rdi
0x180013602  mov     rcx, rbx
0x180013605  call    ??4?$shared_ptr@VCMvExtensionKey@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CMvExtensionKey>::operator=(std::shared_ptr<CMvExtensionKey> &&)
0x18001360a  cmp     rdi, rsi
0x18001360d  jnz     short loc_1800135F7
0x18001360f  lea     rdx, [rbp+57h+var_B0]
0x180013613  mov     rcx, rsi
0x180013616  call    ??4?$shared_ptr@VCMvExtensionKey@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CMvExtensionKey>::operator=(std::shared_ptr<CMvExtensionKey> &&)
0x18001361b  mov     rdi, r12
0x18001361e  jmp     short loc_180013675
0x180013620  mov     r13, rdi
0x180013623  mov     r12, rdi
0x180013626  sub     r12, 10h
0x18001362a  mov     rdx, r12
0x18001362d  lea     rcx, [rbp+57h+var_60]
0x180013631  call    ??$?0VCMvExtensionKey@@@?$shared_ptr@$$CBVCMvExtensionKey@@@std@@QEAA@AEBV?$shared_ptr@VCMvExtensionKey@@@1@PEAPEAX@Z; std::shared_ptr<CMvExtensionKey const>::shared_ptr<CMvExtensionKey const>(std::shared_ptr<CMvExtensionKey> const &,void * *)
0x180013636  mov     rbx, rax
0x180013639  lea     rdx, [rbp+57h+var_B0]
0x18001363d  lea     rcx, [rbp+57h+var_50]
0x180013641  call    ??$?0VCMvExtensionKey@@@?$shared_ptr@$$CBVCMvExtensionKey@@@std@@QEAA@AEBV?$shared_ptr@VCMvExtensionKey@@@1@PEAPEAX@Z; std::shared_ptr<CMvExtensionKey const>::shared_ptr<CMvExtensionKey const>(std::shared_ptr<CMvExtensionKey> const &,void * *)
0x180013646  mov     rdx, rbx
0x180013649  mov     rcx, rax
0x18001364c  call    ?CompareExtensions@@YAHV?$shared_ptr@$$CBVCMvExtensionKey@@@std@@0@Z; CompareExtensions(std::shared_ptr<CMvExtensionKey const>,std::shared_ptr<CMvExtensionKey const>)
0x180013651  mov     rcx, r13
0x180013654  test    eax, eax
0x180013656  jz      short loc_180013665
0x180013658  mov     rdx, r12
0x18001365b  call    ??4?$shared_ptr@VCMvExtensionKey@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CMvExtensionKey>::operator=(std::shared_ptr<CMvExtensionKey> &&)
0x180013660  mov     r13, r12
0x180013663  jmp     short loc_180013626
0x180013665  lea     rdx, [rbp+57h+var_B0]
0x180013669  call    ??4?$shared_ptr@VCMvExtensionKey@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CMvExtensionKey>::operator=(std::shared_ptr<CMvExtensionKey> &&)
0x18001366e  add     rdi, 10h
0x180013672  xor     r13d, r13d
0x180013675  mov     rbx, qword ptr [rbp+57h+var_B0+8]
0x180013679  test    rbx, rbx
0x18001367c  jz      short loc_1800136B6
0x18001367e  mov     eax, r15d
0x180013681  lock xadd [rbx+8], eax
0x180013686  add     eax, r15d
0x180013689  jnz     short loc_1800136B6
0x18001368b  mov     rax, [rbx]
0x18001368e  mov     rcx, rbx
0x180013691  mov     rax, [rax]
0x180013694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013699  mov     eax, r15d
0x18001369c  lock xadd [rbx+0Ch], eax
0x1800136a1  add     eax, r15d
0x1800136a4  jnz     short loc_1800136B6
0x1800136a6  mov     rax, [rbx]
0x1800136a9  mov     rcx, rbx
0x1800136ac  mov     rax, [rax+8]
0x1800136b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136b5  nop
0x1800136b6  cmp     rdi, r14
0x1800136b9  jnz     loc_18001359C
0x1800136bf  add     rsp, 0A8h
0x1800136c6  pop     r15
0x1800136c8  pop     r14
0x1800136ca  pop     r13
0x1800136cc  pop     r12
0x1800136ce  pop     rdi
0x1800136cf  pop     rsi
0x1800136d0  pop     rbx
0x1800136d1  pop     rbp
0x1800136d2  retn
```
