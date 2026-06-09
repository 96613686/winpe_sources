# LTMiscSDKGetClassObject

- ea: `0x180004470`
- end: `0x180004676`
- name: `LTMiscSDKGetClassObject`
- size: `518`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180002440`

## callees

- `0x180004470`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800044bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000453d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800045c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800044bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000453d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800045c0`

## pseudocode

```c
__int64 __fastcall LTMiscSDKGetClassObject(_QWORD *a1, __int64 a2, _QWORD *a3)
{
  __int64 v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rcx
  __int64 v9; // rax
  char *v10; // rax
  __int64 v11; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // r14
  unsigned int v14; // edi

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = clsidSLTApplicationInstances - *a1;
  if ( clsidSLTApplicationInstances == *a1 )
    v6 = 0xC3CA4D2DEB9DDDA0uLL - a1[1];
  if ( !v6 )
  {
    v7 = CoTaskMemAlloc(0x50u);
    v8 = v7;
    if ( v7 )
    {
      v7[4] = 0;
      *v7 = &CLTApplicationInstances::`vftable'{for `IClassFactory'};
      v7[5] = 0;
      v7[1] = &CLTApplicationInstances::`vftable'{for `ISimpleTableWrite'};
      v7[2] = &CLTApplicationInstances::`vftable'{for `ISimpleTableControl'};
      v7[3] = &CLTApplicationInstances::`vftable'{for `ISimpleLogicTableDispenser'};
      *((_OWORD *)v7 + 3) = 0;
      *((_OWORD *)v7 + 4) = 0;
LABEL_19:
      v13 = v8 + 1;
      if ( !v8 )
        v13 = 0;
      v14 = -2147024882;
      if ( v13 )
      {
        (*(void (__fastcall **)(_QWORD *))(*v13 + 8LL))(v13);
        v14 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v13)(v13, a2, a3);
        (*(void (__fastcall **)(_QWORD *))(*v13 + 16LL))(v13);
      }
      return v14;
    }
    goto LABEL_18;
  }
  v9 = clsidSLTEventClassesForIID - *a1;
  if ( clsidSLTEventClassesForIID == *a1 )
    v9 = 0x11AC3EF84FDF3896LL - a1[1];
  if ( !v9 )
  {
    v10 = (char *)CoTaskMemAlloc(0x58u);
    v8 = v10;
    if ( v10 )
    {
      *((_QWORD *)v10 + 4) = 0;
      *(_QWORD *)v10 = &CLTEventClassesForIID::`vftable'{for `IClassFactory'};
      *((_QWORD *)v10 + 5) = 0;
      *((_QWORD *)v10 + 1) = &CLTEventClassesForIID::`vftable'{for `ISimpleTableWrite'};
      *((_QWORD *)v10 + 6) = 0;
      *((_QWORD *)v10 + 2) = &CLTEventClassesForIID::`vftable'{for `ISimpleTableControl'};
      *((_QWORD *)v10 + 3) = &CLTEventClassesForIID::`vftable'{for `ISimpleLogicTableDispenser'};
      *(_OWORD *)(v10 + 56) = 0;
      *(_OWORD *)(v10 + 72) = 0;
      goto LABEL_19;
    }
LABEL_18:
    v8 = 0;
    goto LABEL_19;
  }
  v11 = clsidSLTFilesForImport - *a1;
  if ( clsidSLTFilesForImport == *a1 )
    v11 = 0x44C6DCDF9BDF06B3LL - a1[1];
  if ( !v11 )
  {
    v12 = CoTaskMemAlloc(0x38u);
    v8 = v12;
    if ( v12 )
    {
      v12[4] = 0;
      *v12 = &CLTFilesForImport::`vftable'{for `IClassFactory'};
      v12[1] = &CLTFilesForImport::`vftable'{for `ISimpleTableWrite'};
      v12[2] = &CLTApplicationInstances::`vftable'{for `ISimpleTableControl'};
      v12[3] = &CLTFilesForImport::`vftable'{for `ISimpleLogicTableDispenser'};
      v12[5] = 0;
      v12[6] = 0;
      goto LABEL_19;
    }
    goto LABEL_18;
  }
  return (unsigned int)-2147221231;
}

```

## disassembly

```asm
0x180004470  mov     [rsp+arg_18], rbx
0x180004475  push    rsi
0x180004476  sub     rsp, 20h
0x18000447a  mov     rbx, r8
0x18000447d  mov     rsi, rdx
0x180004480  test    r8, r8
0x180004483  jnz     short loc_18000448F
0x180004485  mov     eax, 80004003h
0x18000448a  jmp     loc_18000466B
0x18000448f  mov     [rsp+28h+arg_0], rdi
0x180004494  xor     edi, edi
0x180004496  mov     [r8], rdi
0x180004499  mov     rax, cs:clsidSLTApplicationInstances
0x1800044a0  sub     rax, [rcx]
0x1800044a3  jnz     short loc_1800044B0
0x1800044a5  mov     rax, cs:qword_180060C48
0x1800044ac  sub     rax, [rcx+8]
0x1800044b0  mov     [rsp+28h+arg_8], r14
0x1800044b5  test    rax, rax
0x1800044b8  jnz     short loc_18000451C
0x1800044ba  mov     ecx, 50h ; 'P'; cb
0x1800044bf  call    cs:__imp_CoTaskMemAlloc
0x1800044c5  mov     [rsp+28h+arg_10], rax
0x1800044ca  mov     rcx, rax
0x1800044cd  test    rax, rax
0x1800044d0  jz      loc_18000460C
0x1800044d6  lea     rax, ??_7CLTApplicationInstances@@6BIClassFactory@@@; const CLTApplicationInstances::`vftable'{for `IClassFactory'}
0x1800044dd  mov     [rcx+20h], rdi
0x1800044e1  mov     [rcx], rax
0x1800044e4  xorps   xmm0, xmm0
0x1800044e7  lea     rax, ??_7CLTApplicationInstances@@6BISimpleTableWrite@@@; const CLTApplicationInstances::`vftable'{for `ISimpleTableWrite'}
0x1800044ee  mov     [rcx+28h], rdi
0x1800044f2  mov     [rcx+8], rax
0x1800044f6  xorps   xmm1, xmm1
0x1800044f9  lea     rax, ??_7CLTApplicationInstances@@6BISimpleTableControl@@@; const CLTApplicationInstances::`vftable'{for `ISimpleTableControl'}
0x180004500  mov     [rcx+10h], rax
0x180004504  lea     rax, ??_7CLTApplicationInstances@@6BISimpleLogicTableDispenser@@@; const CLTApplicationInstances::`vftable'{for `ISimpleLogicTableDispenser'}
0x18000450b  mov     [rcx+18h], rax
0x18000450f  movups  xmmword ptr [rcx+30h], xmm0
0x180004513  movups  xmmword ptr [rcx+40h], xmm1
0x180004517  jmp     loc_18000460F
0x18000451c  mov     rax, cs:clsidSLTEventClassesForIID
0x180004523  sub     rax, [rcx]
0x180004526  jnz     short loc_180004533
0x180004528  mov     rax, cs:qword_180060C38
0x18000452f  sub     rax, [rcx+8]
0x180004533  test    rax, rax
0x180004536  jnz     short loc_18000459B
0x180004538  mov     ecx, 58h ; 'X'; cb
0x18000453d  call    cs:__imp_CoTaskMemAlloc
0x180004543  mov     [rsp+28h+arg_10], rax
0x180004548  mov     rcx, rax
0x18000454b  test    rax, rax
0x18000454e  jz      loc_18000460C
0x180004554  lea     rax, ??_7CLTEventClassesForIID@@6BIClassFactory@@@; const CLTEventClassesForIID::`vftable'{for `IClassFactory'}
0x18000455b  mov     [rcx+20h], rdi
0x18000455f  mov     [rcx], rax
0x180004562  xorps   xmm0, xmm0
0x180004565  lea     rax, ??_7CLTEventClassesForIID@@6BISimpleTableWrite@@@; const CLTEventClassesForIID::`vftable'{for `ISimpleTableWrite'}
0x18000456c  mov     [rcx+28h], rdi
0x180004570  mov     [rcx+8], rax
0x180004574  xorps   xmm1, xmm1
0x180004577  lea     rax, ??_7CLTEventClassesForIID@@6BISimpleTableControl@@@; const CLTEventClassesForIID::`vftable'{for `ISimpleTableControl'}
0x18000457e  mov     [rcx+30h], rdi
0x180004582  mov     [rcx+10h], rax
0x180004586  lea     rax, ??_7CLTEventClassesForIID@@6BISimpleLogicTableDispenser@@@; const CLTEventClassesForIID::`vftable'{for `ISimpleLogicTableDispenser'}
0x18000458d  mov     [rcx+18h], rax
0x180004591  movups  xmmword ptr [rcx+38h], xmm0
0x180004595  movups  xmmword ptr [rcx+48h], xmm1
0x180004599  jmp     short loc_18000460F
0x18000459b  mov     rax, cs:clsidSLTFilesForImport
0x1800045a2  sub     rax, [rcx]
0x1800045a5  jnz     short loc_1800045B2
0x1800045a7  mov     rax, cs:qword_180060C28
0x1800045ae  sub     rax, [rcx+8]
0x1800045b2  test    rax, rax
0x1800045b5  jnz     loc_18000465A
0x1800045bb  mov     ecx, 38h ; '8'; cb
0x1800045c0  call    cs:__imp_CoTaskMemAlloc
0x1800045c6  mov     [rsp+28h+arg_10], rax
0x1800045cb  mov     rcx, rax
0x1800045ce  test    rax, rax
0x1800045d1  jz      short loc_18000460C
0x1800045d3  lea     rax, ??_7CLTFilesForImport@@6BIClassFactory@@@; const CLTFilesForImport::`vftable'{for `IClassFactory'}
0x1800045da  mov     [rcx+20h], rdi
0x1800045de  mov     [rcx], rax
0x1800045e1  lea     rax, ??_7CLTFilesForImport@@6BISimpleTableWrite@@@; const CLTFilesForImport::`vftable'{for `ISimpleTableWrite'}
0x1800045e8  mov     [rcx+8], rax
0x1800045ec  lea     rax, ??_7CLTApplicationInstances@@6BISimpleTableControl@@@; const CLTApplicationInstances::`vftable'{for `ISimpleTableControl'}
0x1800045f3  mov     [rcx+10h], rax
0x1800045f7  lea     rax, ??_7CLTFilesForImport@@6BISimpleLogicTableDispenser@@@; const CLTFilesForImport::`vftable'{for `ISimpleLogicTableDispenser'}
0x1800045fe  mov     [rcx+18h], rax
0x180004602  mov     [rcx+28h], rdi
0x180004606  mov     [rcx+30h], rdi
0x18000460a  jmp     short loc_18000460F
0x18000460c  mov     rcx, rdi
0x18000460f  test    rcx, rcx
0x180004612  lea     r14, [rcx+8]
0x180004616  cmovz   r14, rdi
0x18000461a  mov     edi, 8007000Eh
0x18000461f  test    r14, r14
0x180004622  jz      short loc_18000465F
0x180004624  mov     rax, [r14]
0x180004627  mov     rcx, r14
0x18000462a  mov     rax, [rax+8]
0x18000462e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004633  mov     rax, [r14]
0x180004636  mov     r8, rbx
0x180004639  mov     rdx, rsi
0x18000463c  mov     rcx, r14
0x18000463f  mov     rax, [rax]
0x180004642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004647  mov     rdx, [r14]
0x18000464a  mov     edi, eax
0x18000464c  mov     rcx, r14
0x18000464f  mov     rax, [rdx+10h]
0x180004653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004658  jmp     short loc_18000465F
0x18000465a  mov     edi, 80040111h
0x18000465f  mov     r14, [rsp+28h+arg_8]
0x180004664  mov     eax, edi
0x180004666  mov     rdi, [rsp+28h+arg_0]
0x18000466b  mov     rbx, [rsp+28h+arg_18]
0x180004670  add     rsp, 20h
0x180004674  pop     rsi
0x180004675  retn
```
