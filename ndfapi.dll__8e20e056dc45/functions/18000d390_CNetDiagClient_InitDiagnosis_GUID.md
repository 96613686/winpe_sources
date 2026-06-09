# CNetDiagClient::InitDiagnosis(_GUID *)

- ea: `0x18000d390`
- end: `0x18000d6ec`
- name: `?InitDiagnosis@CNetDiagClient@@IEAAJPEAU_GUID@@@Z`
- size: `860`
- prototype: `__int64 __fastcall(CNetDiagClient *__hidden this, struct _GUID *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, service_task`

## callers

- `0x180014340`
- `0x18001b564`

## callees

- `0x180007ee4`
- `0x1800086cc`
- `0x180009dac`
- `0x180009fcc`
- `0x18000d390`
- `0x18000e0c4`
- `0x18000e2d4`
- `0x18001be28`
- `0x18001f652`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000d614`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d66a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d614`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d66a`
- `KERNEL32!GetThreadLocale` at `0x18000d3da`
- `KERNEL32!GetThreadLocale` at `0x18000d5af`
- `KERNEL32!GetThreadLocale` at `0x18000d3da`
- `KERNEL32!GetThreadLocale` at `0x18000d5af`
- `ole32!CoTaskMemFree` at `0x18000d544`
- `ole32!CoTaskMemFree` at `0x18000d6c8`
- `ole32!CoTaskMemFree` at `0x18000d544`
- `ole32!CoTaskMemFree` at `0x18000d6c8`
- `wdi!WdiGetParameterCount` at `0x18000d593`
- `wdi!WdiGetParameterCount` at `0x18000d593`
- `wdi!WdiCreateInstance` at `0x18000d3ec`
- `wdi!WdiCreateInstance` at `0x18000d5c1`
- `wdi!WdiCreateInstance` at `0x18000d3ec`
- `wdi!WdiCreateInstance` at `0x18000d5c1`
- `wdi!WdiAddParameter` at `0x18000d464`
- `wdi!WdiAddParameter` at `0x18000d530`
- `wdi!WdiAddParameter` at `0x18000d579`
- `wdi!WdiAddParameter` at `0x18000d464`
- `wdi!WdiAddParameter` at `0x18000d530`
- `wdi!WdiAddParameter` at `0x18000d579`
- `wdi!WdiOpenInstance` at `0x18000d5d7`
- `wdi!WdiOpenInstance` at `0x18000d5d7`
- `wdi!WdiGetInstanceId` at `0x18000d6b7`
- `wdi!WdiGetInstanceId` at `0x18000d6b7`

## pseudocode

```c
__int64 __fastcall CNetDiagClient::InitDiagnosis(CNetDiagClient *this, struct _GUID *a2)
{
  signed int Instance; // ebx
  _QWORD *v5; // rsi
  LCID v6; // eax
  __int64 v7; // r14
  __int64 v8; // rcx
  _WORD *v9; // rax
  unsigned int v10; // eax
  unsigned int v11; // r14d
  __int64 v12; // rax
  LPVOID v13; // rbx
  unsigned int v14; // eax
  int ResultData; // eax
  LCID ThreadLocale; // eax
  char *v17; // rbx
  _QWORD *v18; // r15
  _QWORD *i; // r14
  char *v20; // rbx
  _QWORD *v21; // r15
  _QWORD *j; // r14
  _OWORD v24[9]; // [rsp+30h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+F8h] [rbp+6Fh] BYREF
  unsigned __int64 v26; // [rsp+100h] [rbp+77h] BYREF

  pv = 0;
  if ( a2 )
  {
    v5 = (_QWORD *)((char *)this + 128);
    ThreadLocale = GetThreadLocale();
    Instance = WdiCreateInstance(ThreadLocale, v5, (char *)this + 3104);
    if ( Instance < 0 )
      goto LABEL_27;
    Instance = WdiOpenInstance(*v5, a2);
    if ( Instance < 0 )
      goto LABEL_27;
    *((_DWORD *)this + 760) = 0;
    v17 = (char *)this + 96;
    v18 = *(_QWORD **)(*((_QWORD *)this + 12) + 8LL);
    for ( i = v18; !*((_BYTE *)i + 25); v18 = i )
    {
      std::_Tree<std::_Tset_traits<_GUID,GuidLessThan,std::allocator<_GUID>,0>>::_Erase((char *)this + 96, i[2]);
      i = (_QWORD *)*i;
      operator delete(v18);
    }
    *(_QWORD *)(*(_QWORD *)v17 + 8LL) = *(_QWORD *)v17;
    **(_QWORD **)v17 = *(_QWORD *)v17;
    *(_QWORD *)(*(_QWORD *)v17 + 16LL) = *(_QWORD *)v17;
    *((_QWORD *)this + 13) = 0;
    std::_Tree<std::_Tmap_traits<std::wstring,_GUID,WstringLessThan,std::allocator<std::pair<std::wstring const,_GUID>>,0>>::clear((char *)this + 64);
    v20 = (char *)this + 112;
    v21 = *(_QWORD **)(*((_QWORD *)this + 14) + 8LL);
    for ( j = v21; !*((_BYTE *)j + 25); v21 = j )
    {
      std::_Tree<std::_Tset_traits<_GUID,GuidLessThan,std::allocator<_GUID>,0>>::_Erase((char *)this + 112, j[2]);
      j = (_QWORD *)*j;
      operator delete(v21);
    }
    *(_QWORD *)(*(_QWORD *)v20 + 8LL) = *(_QWORD *)v20;
    **(_QWORD **)v20 = *(_QWORD *)v20;
    *(_QWORD *)(*(_QWORD *)v20 + 16LL) = *(_QWORD *)v20;
    *((_QWORD *)this + 15) = 0;
    Instance = CNetDiagClient::LoadInitData(this);
    if ( Instance < 0 )
      goto LABEL_27;
    ResultData = CNetDiagClient::LoadResultData(this);
LABEL_25:
    Instance = ResultData;
    if ( ResultData >= 0 )
      Instance = WdiGetInstanceId(*v5, (char *)this + 3048);
    goto LABEL_27;
  }
  Instance = CNetDiagClient::CleanupDiagnosis(this);
  if ( Instance < 0 )
    goto LABEL_27;
  v5 = (_QWORD *)((char *)this + 128);
  v6 = GetThreadLocale();
  Instance = WdiCreateInstance(v6, (char *)this + 128, (char *)this + 3104);
  if ( Instance < 0 )
    goto LABEL_27;
  v7 = *((_QWORD *)this + 3);
  if ( !v7 )
  {
    Instance = -2147024809;
    goto LABEL_27;
  }
  v8 = 0x7FFF;
  v9 = (_WORD *)*((_QWORD *)this + 3);
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v8;
  }
  while ( v8 );
  Instance = v8 == 0 ? 0x80070057 : 0;
  if ( !v8 )
    goto LABEL_27;
  v10 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>((2 * (0x7FFF - v8)) & -(__int64)(v8 != 0));
  Instance = WdiAddParameter(*v5, 0, L"HelperClassName", v10, v7);
  if ( Instance < 0 )
    goto LABEL_27;
  v11 = 0;
  if ( !*((_DWORD *)this + 8) )
  {
LABEL_14:
    Instance = WdiAddParameter(*v5, 0, L"NdfOptions", 4, (char *)this + 3044);
    if ( Instance < 0 )
      goto LABEL_27;
    ResultData = WdiGetParameterCount(*v5, (char *)this + 136);
    goto LABEL_25;
  }
  while ( 1 )
  {
    v26 = 0;
    memset_0(v24, 0, sizeof(v24));
    v12 = *((_QWORD *)this + 5);
    v24[0] = *(_OWORD *)(v12 + 144LL * v11);
    v24[1] = *(_OWORD *)(v12 + 144LL * v11 + 16);
    v24[2] = *(_OWORD *)(v12 + 144LL * v11 + 32);
    v24[3] = *(_OWORD *)(v12 + 144LL * v11 + 48);
    v24[4] = *(_OWORD *)(v12 + 144LL * v11 + 64);
    v24[5] = *(_OWORD *)(v12 + 144LL * v11 + 80);
    v24[6] = *(_OWORD *)(v12 + 144LL * v11 + 96);
    v24[7] = *(_OWORD *)(v12 + 144LL * v11 + 112);
    v24[8] = *(_OWORD *)(v12 + 144LL * v11 + 128);
    Instance = EncodeHelperAttribute(v24, &pv, &v26);
    if ( Instance < 0 )
      break;
    v13 = pv;
    v14 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v26);
    Instance = WdiAddParameter(*v5, 0, *(_QWORD *)&v24[0], v14, v13);
    if ( Instance < 0 )
      break;
    CoTaskMemFree(pv);
    pv = 0;
    if ( ++v11 >= *((_DWORD *)this + 8) )
      goto LABEL_14;
  }
LABEL_27:
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000d390  mov     [rsp-8+arg_0], rbx
0x18000d395  mov     [rsp-8+arg_18], rsi
0x18000d39a  push    rbp
0x18000d39b  push    rdi
0x18000d39c  push    r12
0x18000d39e  push    r14
0x18000d3a0  push    r15
0x18000d3a2  lea     rbp, [rsp-37h]
0x18000d3a7  sub     rsp, 0C0h
0x18000d3ae  mov     r14, rdx
0x18000d3b1  mov     rdi, rcx
0x18000d3b4  xor     r12d, r12d
0x18000d3b7  mov     [rbp+57h+pv], r12
0x18000d3bb  test    rdx, rdx
0x18000d3be  jnz     loc_18000D5A8
0x18000d3c4  call    ?CleanupDiagnosis@CNetDiagClient@@IEAAJXZ; CNetDiagClient::CleanupDiagnosis(void)
0x18000d3c9  mov     ebx, eax
0x18000d3cb  test    eax, eax
0x18000d3cd  js      loc_18000D6BF
0x18000d3d3  lea     rsi, [rdi+80h]
0x18000d3da  call    cs:__imp_GetThreadLocale
0x18000d3e0  mov     ecx, eax
0x18000d3e2  lea     r8, [rdi+0C20h]
0x18000d3e9  mov     rdx, rsi
0x18000d3ec  call    cs:__imp_WdiCreateInstance
0x18000d3f2  mov     ebx, eax
0x18000d3f4  test    eax, eax
0x18000d3f6  js      loc_18000D6BF
0x18000d3fc  mov     r14, [rdi+18h]
0x18000d400  test    r14, r14
0x18000d403  jz      loc_18000D59E
0x18000d409  mov     edx, 7FFFh
0x18000d40e  mov     ecx, edx
0x18000d410  mov     rax, r14
0x18000d413  cmp     [rax], r12w
0x18000d417  jz      short loc_18000D423
0x18000d419  add     rax, 2
0x18000d41d  sub     rcx, 1
0x18000d421  jnz     short loc_18000D413
0x18000d423  mov     rax, rcx
0x18000d426  neg     rax
0x18000d429  sbb     ebx, ebx
0x18000d42b  not     ebx
0x18000d42d  and     ebx, 80070057h
0x18000d433  test    rcx, rcx
0x18000d436  jz      loc_18000D6BF
0x18000d43c  sub     rdx, rcx
0x18000d43f  add     rdx, rdx
0x18000d442  neg     rcx
0x18000d445  sbb     rcx, rcx
0x18000d448  and     rcx, rdx
0x18000d44b  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000d450  mov     [rsp+0E0h+var_C0], r14
0x18000d455  mov     r9d, eax
0x18000d458  lea     r8, aHelperclassnam; "HelperClassName"
0x18000d45f  xor     edx, edx
0x18000d461  mov     rcx, [rsi]
0x18000d464  call    cs:__imp_WdiAddParameter
0x18000d46a  mov     ebx, eax
0x18000d46c  test    eax, eax
0x18000d46e  js      loc_18000D6BF
0x18000d474  mov     r14d, r12d
0x18000d477  cmp     [rdi+20h], r12d
0x18000d47b  jbe     loc_18000D55B
0x18000d481  mov     [rbp+57h+arg_10], r12
0x18000d485  xor     edx, edx; Val
0x18000d487  mov     r8d, 90h; Size
0x18000d48d  lea     rcx, [rbp+57h+var_B0]; void *
0x18000d491  call    memset_0
0x18000d496  mov     eax, r14d
0x18000d499  lea     rcx, [rax+rax*8]
0x18000d49d  add     rcx, rcx
0x18000d4a0  mov     rax, [rdi+28h]
0x18000d4a4  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18000d4a8  movups  [rbp+57h+var_B0], xmm0
0x18000d4ac  movups  xmm1, xmmword ptr [rax+rcx*8+10h]
0x18000d4b1  movups  [rbp+57h+var_A0], xmm1
0x18000d4b5  movups  xmm0, xmmword ptr [rax+rcx*8+20h]
0x18000d4ba  movups  [rbp+57h+var_90], xmm0
0x18000d4be  movups  xmm1, xmmword ptr [rax+rcx*8+30h]
0x18000d4c3  movups  [rbp+57h+var_80], xmm1
0x18000d4c7  movups  xmm0, xmmword ptr [rax+rcx*8+40h]
0x18000d4cc  movups  [rbp+57h+var_70], xmm0
0x18000d4d0  movups  xmm1, xmmword ptr [rax+rcx*8+50h]
0x18000d4d5  movups  [rbp+57h+var_60], xmm1
0x18000d4d9  movups  xmm0, xmmword ptr [rax+rcx*8+60h]
0x18000d4de  movups  [rbp+57h+var_50], xmm0
0x18000d4e2  movups  xmm1, xmmword ptr [rax+rcx*8+70h]
0x18000d4e7  movups  [rbp+57h+var_40], xmm1
0x18000d4eb  movups  xmm0, xmmword ptr [rax+rcx*8+80h]
0x18000d4f3  movups  [rbp+57h+var_30], xmm0
0x18000d4f7  lea     r8, [rbp+57h+arg_10]
0x18000d4fb  lea     rdx, [rbp+57h+pv]
0x18000d4ff  lea     rcx, [rbp+57h+var_B0]
0x18000d503  call    EncodeHelperAttribute
0x18000d508  mov     ebx, eax
0x18000d50a  test    eax, eax
0x18000d50c  js      loc_18000D6BF
0x18000d512  mov     rbx, [rbp+57h+pv]
0x18000d516  mov     rcx, [rbp+57h+arg_10]
0x18000d51a  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000d51f  mov     [rsp+0E0h+var_C0], rbx
0x18000d524  mov     r9d, eax
0x18000d527  mov     r8, qword ptr [rbp+57h+var_B0]
0x18000d52b  xor     edx, edx
0x18000d52d  mov     rcx, [rsi]
0x18000d530  call    cs:__imp_WdiAddParameter
0x18000d536  mov     ebx, eax
0x18000d538  test    eax, eax
0x18000d53a  js      loc_18000D6BF
0x18000d540  mov     rcx, [rbp+57h+pv]; pv
0x18000d544  call    cs:__imp_CoTaskMemFree
0x18000d54a  mov     [rbp+57h+pv], r12
0x18000d54e  inc     r14d
0x18000d551  cmp     r14d, [rdi+20h]
0x18000d555  jb      loc_18000D481
0x18000d55b  lea     rax, [rdi+0BE4h]
0x18000d562  mov     [rsp+0E0h+var_C0], rax
0x18000d567  mov     r9d, 4
0x18000d56d  lea     r8, aNdfoptions; "NdfOptions"
0x18000d574  xor     edx, edx
0x18000d576  mov     rcx, [rsi]
0x18000d579  call    cs:__imp_WdiAddParameter
0x18000d57f  mov     ebx, eax
0x18000d581  test    eax, eax
0x18000d583  js      loc_18000D6BF
0x18000d589  lea     rdx, [rdi+88h]
0x18000d590  mov     rcx, [rsi]
0x18000d593  call    cs:__imp_WdiGetParameterCount
0x18000d599  jmp     loc_18000D6A7
0x18000d59e  mov     ebx, 80070057h
0x18000d5a3  jmp     loc_18000D6BF
0x18000d5a8  lea     rsi, [rcx+80h]
0x18000d5af  call    cs:__imp_GetThreadLocale
0x18000d5b5  mov     ecx, eax
0x18000d5b7  lea     r8, [rdi+0C20h]
0x18000d5be  mov     rdx, rsi
0x18000d5c1  call    cs:__imp_WdiCreateInstance
0x18000d5c7  mov     ebx, eax
0x18000d5c9  test    eax, eax
0x18000d5cb  js      loc_18000D6BF
0x18000d5d1  mov     rdx, r14
0x18000d5d4  mov     rcx, [rsi]
0x18000d5d7  call    cs:__imp_WdiOpenInstance
0x18000d5dd  mov     ebx, eax
0x18000d5df  test    eax, eax
0x18000d5e1  js      loc_18000D6BF
0x18000d5e7  mov     [rdi+0BE0h], r12d
0x18000d5ee  lea     rbx, [rdi+60h]
0x18000d5f2  mov     rax, [rbx]
0x18000d5f5  mov     r15, [rax+8]
0x18000d5f9  mov     r14, r15
0x18000d5fc  cmp     [r15+19h], r12b
0x18000d600  jnz     short loc_18000D623
0x18000d602  mov     rdx, [r14+10h]
0x18000d606  mov     rcx, rbx
0x18000d609  call    ?_Erase@?$_Tree@V?$_Tset_traits@U_GUID@@UGuidLessThan@@V?$allocator@U_GUID@@@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U_GUID@@PEAX@2@@Z; std::_Tree<std::_Tset_traits<_GUID,GuidLessThan,std::allocator<_GUID>,0>>::_Erase(std::_Tree_node<_GUID,void *> *)
0x18000d60e  mov     r14, [r14]
0x18000d611  mov     rcx, r15
0x18000d614  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000d61a  mov     r15, r14
0x18000d61d  cmp     [r14+19h], r12b
0x18000d621  jz      short loc_18000D602
0x18000d623  mov     rax, [rbx]
0x18000d626  mov     [rax+8], rax
0x18000d62a  mov     rax, [rbx]
0x18000d62d  mov     [rax], rax
0x18000d630  mov     rax, [rbx]
0x18000d633  mov     [rax+10h], rax
0x18000d637  mov     [rbx+8], r12
0x18000d63b  lea     rcx, [rdi+40h]
0x18000d63f  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@UWstringLessThan@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,_GUID,WstringLessThan,std::allocator<std::pair<std::wstring const,_GUID>>,0>>::clear(void)
0x18000d644  lea     rbx, [rdi+70h]
0x18000d648  mov     rax, [rbx]
0x18000d64b  mov     r15, [rax+8]
0x18000d64f  mov     r14, r15
0x18000d652  cmp     [r15+19h], r12b
0x18000d656  jnz     short loc_18000D679
0x18000d658  mov     rdx, [r14+10h]
0x18000d65c  mov     rcx, rbx
0x18000d65f  call    ?_Erase@?$_Tree@V?$_Tset_traits@U_GUID@@UGuidLessThan@@V?$allocator@U_GUID@@@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U_GUID@@PEAX@2@@Z; std::_Tree<std::_Tset_traits<_GUID,GuidLessThan,std::allocator<_GUID>,0>>::_Erase(std::_Tree_node<_GUID,void *> *)
0x18000d664  mov     r14, [r14]
0x18000d667  mov     rcx, r15
0x18000d66a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000d670  mov     r15, r14
0x18000d673  cmp     [r14+19h], r12b
0x18000d677  jz      short loc_18000D658
0x18000d679  mov     rax, [rbx]
0x18000d67c  mov     [rax+8], rax
0x18000d680  mov     rax, [rbx]
0x18000d683  mov     [rax], rax
0x18000d686  mov     rax, [rbx]
0x18000d689  mov     [rax+10h], rax
0x18000d68d  mov     [rbx+8], r12
0x18000d691  mov     rcx, rdi; this
0x18000d694  call    ?LoadInitData@CNetDiagClient@@QEAAJXZ; CNetDiagClient::LoadInitData(void)
0x18000d699  mov     ebx, eax
0x18000d69b  test    eax, eax
0x18000d69d  js      short loc_18000D6BF
0x18000d69f  mov     rcx, rdi; this
0x18000d6a2  call    ?LoadResultData@CNetDiagClient@@QEAAJXZ; CNetDiagClient::LoadResultData(void)
0x18000d6a7  test    eax, eax
0x18000d6a9  mov     ebx, eax
0x18000d6ab  js      short loc_18000D6BF
0x18000d6ad  lea     rdx, [rdi+0BE8h]
0x18000d6b4  mov     rcx, [rsi]
0x18000d6b7  call    cs:__imp_WdiGetInstanceId
0x18000d6bd  mov     ebx, eax
0x18000d6bf  mov     rcx, [rbp+57h+pv]; pv
0x18000d6c3  test    rcx, rcx
0x18000d6c6  jz      short loc_18000D6CE
0x18000d6c8  call    cs:__imp_CoTaskMemFree
0x18000d6ce  mov     eax, ebx
0x18000d6d0  lea     r11, [rsp+0E0h+var_20]
0x18000d6d8  mov     rbx, [r11+30h]
0x18000d6dc  mov     rsi, [r11+48h]
0x18000d6e0  mov     rsp, r11
0x18000d6e3  pop     r15
0x18000d6e5  pop     r14
0x18000d6e7  pop     r12
0x18000d6e9  pop     rdi
0x18000d6ea  pop     rbp
0x18000d6eb  retn
```
