# CTraceController::AddHelperClassProviders(ushort const *,ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &,bool)

- ea: `0x1800233d8`
- end: `0x180023671`
- name: `?AddHelperClassProviders@CTraceController@@AEAAJPEBGAEAV?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@_N@Z`
- size: `665`
- prototype: `__int64 __fastcall(unsigned int *, __int64, __int64, char)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800233d8`
- `0x180023678`

## callees

- `0x180002030`
- `0x180006d58`
- `0x18000821c`
- `0x180008248`
- `0x180008c84`
- `0x180015960`
- `0x180023364`
- `0x1800233d8`
- `0x180023704`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800234a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800234a2`

## pseudocode

```c
__int64 __fastcall CTraceController::AddHelperClassProviders(unsigned int *a1, __int64 a2, __int64 a3, char a4)
{
  __int64 v5; // rsi
  CTraceController *v7; // r13
  unsigned int v8; // edi
  __int64 v9; // rcx
  unsigned int i; // r14d
  char *v11; // rdx
  unsigned __int64 v12; // r8
  int v13; // eax
  int v14; // edi
  unsigned int v15; // edi
  bool v16; // sf
  void *v17; // rax
  _QWORD *v18; // rcx
  _QWORD *v19; // rdx
  unsigned int v20; // r15d
  int j; // r14d
  __int64 v22; // r9
  unsigned int v24; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v25; // [rsp+28h] [rbp-70h] BYREF
  __int64 v26; // [rsp+30h] [rbp-68h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-60h] BYREF
  __int64 v28; // [rsp+40h] [rbp-58h] BYREF
  _QWORD *v29; // [rsp+48h] [rbp-50h] BYREF
  int v30; // [rsp+50h] [rbp-48h]
  int v31; // [rsp+54h] [rbp-44h]
  ATL::CAtlException *v32; // [rsp+58h] [rbp-40h] BYREF
  CTraceController *v33; // [rsp+A0h] [rbp+8h] BYREF
  __int64 v34; // [rsp+B0h] [rbp+18h]
  char v35; // [rsp+B8h] [rbp+20h]

  v35 = a4;
  v34 = a3;
  v33 = (CTraceController *)a1;
  v5 = a3;
  v7 = (CTraceController *)a1;
  v8 = a1[6];
  v9 = 0;
  v28 = 0;
  if ( !v8 )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**((_QWORD **)v7 + 2) + 24LL))(
           *((_QWORD *)v7 + 2),
           a2,
           &v28);
    v9 = v28;
  }
  pv = 0;
  v24 = 0;
  if ( !v8 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, LPVOID *, unsigned int *))(*(_QWORD *)v9 + 112LL))(v9, &pv, &v24);
    if ( !v8 )
    {
      if ( v24 )
      {
        for ( i = 0; i < v24; ++i )
        {
          v11 = (char *)pv + 32 * i;
          if ( a4 )
            v12 = *((_QWORD *)v11 + 3);
          else
            v12 = 0xE00000000000LL;
          v13 = CTraceController::AddProvider(v7, (const struct _GUID *)v11, v12, v11[16]);
          v8 = 0;
          if ( v13 >= 0 )
            v8 = v13;
        }
      }
    }
  }
  CoTaskMemFree(pv);
  pv = 0;
  if ( v8 )
    goto LABEL_42;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v26,
      a2);
    v14 = *(_DWORD *)(v5 + 8);
    if ( v14 != *(_DWORD *)(v5 + 12) )
      goto LABEL_22;
    if ( *(_DWORD *)(v5 + 12) )
    {
      v16 = (v14 & 0x40000000) != 0;
      v15 = 2 * v14;
      if ( v16 )
        goto LABEL_25;
    }
    else
    {
      v15 = 1;
    }
    if ( v15 <= 0xFFFFFFFuLL )
    {
      v17 = _recalloc(*(void **)v5, v15, 8u);
      if ( v17 )
      {
        *(_DWORD *)(v5 + 12) = v15;
        *(_QWORD *)v5 = v17;
LABEL_22:
        LODWORD(v25) = *(_DWORD *)(v5 + 8);
        v18 = (_QWORD *)(*(_QWORD *)v5 + 8LL * (int)v25);
        v29 = v18;
        if ( v18 )
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            v18,
            &v26);
        ++*(_DWORD *)(v5 + 8);
      }
    }
LABEL_25:
    ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v32) )
    {
      LODWORD(v25) = *(_DWORD *)v32;
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18002353B);
      v8 = (unsigned int)v25;
      if ( (_DWORD)v25 )
        goto LABEL_42;
      v7 = v33;
      v5 = v34;
    }
  }
  v25 = 0;
  LODWORD(v33) = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD **, CTraceController **))(*(_QWORD *)v28 + 104LL))(v28, &v25, &v33);
  if ( !v8 )
  {
    v19 = v25;
    v29 = v25;
    v30 = (int)v33;
    v31 = 1;
    v20 = 0;
    if ( (_DWORD)v33 )
    {
      while ( !v8 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          (__int64)&v26,
          v19[v20]);
        for ( j = 0; j < *(_DWORD *)(v5 + 8); ++j )
        {
          if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Compare(
                                (unsigned __int16 **)(*(_QWORD *)v5 + 8LL * j),
                                v26) )
            goto LABEL_36;
        }
        j = -1;
LABEL_36:
        ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
        if ( j == -1 )
        {
          LOBYTE(v22) = v35;
          v8 = CTraceController::AddHelperClassProviders((unsigned int *)v7, v25[v20], v5, v22);
          if ( v8 == -2147024894 )
            v8 = 0;
        }
        if ( ++v20 >= (unsigned int)v33 )
          break;
        v19 = v25;
      }
    }
    TNDFDeallocator<unsigned short * *,&void FreeDependencies(unsigned short * *,unsigned long,int)>::~TNDFDeallocator<unsigned short * *,&void FreeDependencies(unsigned short * *,unsigned long,int)>(&v29);
  }
LABEL_42:
  ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(&v28);
  return v8;
}

```

## disassembly

```asm
0x1800233d8  mov     rax, rsp
0x1800233db  mov     [rax+20h], r9b
0x1800233df  mov     [rax+18h], r8
0x1800233e3  mov     [rax+8], rcx
0x1800233e7  push    rbx
0x1800233e8  push    rsi
0x1800233e9  push    rdi
0x1800233ea  push    r12
0x1800233ec  push    r13
0x1800233ee  push    r14
0x1800233f0  push    r15
0x1800233f2  sub     rsp, 60h
0x1800233f6  mov     r12b, r9b
0x1800233f9  mov     rsi, r8
0x1800233fc  mov     r15, rdx
0x1800233ff  mov     r13, rcx
0x180023402  mov     edi, [rcx+18h]
0x180023405  xor     ebx, ebx
0x180023407  mov     ecx, ebx
0x180023409  mov     [rax-58h], rbx
0x18002340d  test    edi, edi
0x18002340f  jnz     short loc_18002342D
0x180023411  mov     rcx, [r13+10h]
0x180023415  mov     rax, [rcx]
0x180023418  lea     r8, [rsp+98h+var_58]
0x18002341d  mov     rax, [rax+18h]
0x180023421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023426  mov     edi, eax
0x180023428  mov     rcx, [rsp+98h+var_58]
0x18002342d  mov     [rsp+98h+pv], rbx
0x180023432  mov     [rsp+98h+var_78], ebx
0x180023436  test    edi, edi
0x180023438  jnz     short loc_18002349D
0x18002343a  mov     rax, [rcx]
0x18002343d  lea     r8, [rsp+98h+var_78]
0x180023442  lea     rdx, [rsp+98h+pv]
0x180023447  mov     rax, [rax+70h]
0x18002344b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023450  mov     edi, eax
0x180023452  test    eax, eax
0x180023454  jnz     short loc_18002349D
0x180023456  cmp     [rsp+98h+var_78], ebx
0x18002345a  jbe     short loc_18002349D
0x18002345c  mov     r14d, ebx
0x18002345f  mov     edx, r14d
0x180023462  shl     rdx, 5
0x180023466  add     rdx, [rsp+98h+pv]; struct _GUID *
0x18002346b  test    r12b, r12b
0x18002346e  jz      short loc_180023476
0x180023470  mov     r8, [rdx+18h]
0x180023474  jmp     short loc_180023480
0x180023476  mov     r8, 0E00000000000h; unsigned __int64
0x180023480  mov     r9b, [rdx+10h]; unsigned __int8
0x180023484  mov     rcx, r13; this
0x180023487  call    ?AddProvider@CTraceController@@AEAAJAEBU_GUID@@_KE@Z; CTraceController::AddProvider(_GUID const &,unsigned __int64,uchar)
0x18002348c  mov     edi, ebx
0x18002348e  test    eax, eax
0x180023490  cmovns  edi, eax
0x180023493  inc     r14d
0x180023496  cmp     r14d, [rsp+98h+var_78]
0x18002349b  jb      short loc_18002345F
0x18002349d  mov     rcx, [rsp+98h+pv]; pv
0x1800234a2  call    cs:__imp_CoTaskMemFree
0x1800234a8  mov     [rsp+98h+pv], rbx
0x1800234ad  test    edi, edi
0x1800234af  jnz     loc_180023655
0x1800234b5  mov     rdx, r15
0x1800234b8  lea     rcx, [rsp+98h+var_68]
0x1800234bd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800234c2  nop
0x1800234c3  mov     edi, [rsi+8]
0x1800234c6  cmp     edi, [rsi+0Ch]
0x1800234c9  jnz     short loc_180023500
0x1800234cb  cmp     [rsi+0Ch], ebx
0x1800234ce  jnz     short loc_1800234D7
0x1800234d0  mov     edi, 1
0x1800234d5  jmp     short loc_1800234DB
0x1800234d7  add     edi, edi
0x1800234d9  js      short loc_18002352A
0x1800234db  mov     edx, edi; Count
0x1800234dd  cmp     rdx, 0FFFFFFFh
0x1800234e4  ja      short loc_18002352A
0x1800234e6  mov     r8d, 8; Size
0x1800234ec  mov     rcx, [rsi]; Block
0x1800234ef  call    cs:__imp__recalloc
0x1800234f5  test    rax, rax
0x1800234f8  jz      short loc_18002352A
0x1800234fa  mov     [rsi+0Ch], edi
0x1800234fd  mov     [rsi], rax
0x180023500  movsxd  rax, dword ptr [rsi+8]
0x180023504  mov     dword ptr [rsp+98h+var_70], eax
0x180023508  mov     rcx, rax
0x18002350b  mov     rax, [rsi]
0x18002350e  lea     rcx, [rax+rcx*8]
0x180023512  mov     [rsp+98h+var_50], rcx
0x180023517  test    rcx, rcx
0x18002351a  jz      short loc_180023527
0x18002351c  lea     rdx, [rsp+98h+var_68]
0x180023521  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180023526  nop
0x180023527  inc     dword ptr [rsi+8]
0x18002352a  mov     rcx, [rsp+98h+var_68]
0x18002352f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180023533  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180023538  nop
0x180023539  jmp     short loc_180023559
0x18002353b  mov     edi, dword ptr [rsp+98h+var_70]
0x18002353f  xor     ebx, ebx
0x180023541  test    edi, edi
0x180023543  jnz     loc_180023655
0x180023549  mov     r13, [rsp+98h+arg_0]
0x180023551  mov     rsi, [rsp+98h+arg_10]
0x180023559  mov     [rsp+98h+var_70], rbx
0x18002355e  mov     dword ptr [rsp+98h+arg_0], ebx
0x180023565  mov     rcx, [rsp+98h+var_58]
0x18002356a  mov     rax, [rcx]
0x18002356d  lea     r8, [rsp+98h+arg_0]
0x180023575  lea     rdx, [rsp+98h+var_70]
0x18002357a  mov     rax, [rax+68h]
0x18002357e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023583  mov     edi, eax
0x180023585  test    eax, eax
0x180023587  jnz     loc_180023655
0x18002358d  mov     rdx, [rsp+98h+var_70]
0x180023592  mov     [rsp+98h+var_50], rdx
0x180023597  mov     eax, dword ptr [rsp+98h+arg_0]
0x18002359e  mov     [rsp+98h+var_48], eax
0x1800235a2  mov     [rsp+98h+var_44], 1
0x1800235aa  mov     r15d, ebx
0x1800235ad  test    eax, eax
0x1800235af  jz      loc_18002364A
0x1800235b5  test    edi, edi
0x1800235b7  jnz     loc_18002364A
0x1800235bd  mov     r12d, r15d
0x1800235c0  mov     rdx, [rdx+r12*8]
0x1800235c4  lea     rcx, [rsp+98h+var_68]
0x1800235c9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800235ce  mov     r14d, ebx
0x1800235d1  cmp     r14d, [rsi+8]
0x1800235d5  jge     short loc_1800235F5
0x1800235d7  movsxd  rcx, r14d
0x1800235da  mov     rax, [rsi]
0x1800235dd  lea     rcx, [rax+rcx*8]
0x1800235e1  mov     rdx, [rsp+98h+var_68]
0x1800235e6  call    ?Compare@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Compare(ushort const *)
0x1800235eb  nop
0x1800235ec  test    eax, eax
0x1800235ee  jz      short loc_1800235F9
0x1800235f0  inc     r14d
0x1800235f3  jmp     short loc_1800235D1
0x1800235f5  or      r14d, 0FFFFFFFFh
0x1800235f9  mov     rcx, [rsp+98h+var_68]
0x1800235fe  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180023602  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180023607  cmp     r14d, 0FFFFFFFFh
0x18002360b  jnz     short loc_180023633
0x18002360d  mov     r9b, [rsp+98h+arg_18]
0x180023615  mov     r8, rsi
0x180023618  mov     rdx, [rsp+98h+var_70]
0x18002361d  mov     rdx, [rdx+r12*8]
0x180023621  mov     rcx, r13
0x180023624  call    ?AddHelperClassProviders@CTraceController@@AEAAJPEBGAEAV?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@_N@Z; CTraceController::AddHelperClassProviders(ushort const *,ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &,bool)
0x180023629  mov     edi, eax
0x18002362b  cmp     eax, 80070002h
0x180023630  cmovz   edi, ebx
0x180023633  inc     r15d
0x180023636  cmp     r15d, dword ptr [rsp+98h+arg_0]
0x18002363e  jnb     short loc_18002364A
0x180023640  mov     rdx, [rsp+98h+var_70]
0x180023645  jmp     loc_1800235B5
0x18002364a  lea     rcx, [rsp+98h+var_50]
0x18002364f  call    ??1?$TNDFDeallocator@PEAPEAG$1?FreeDependencies@@YAXPEAPEAGKH@Z@@QEAA@XZ; TNDFDeallocator<ushort * *,&FreeDependencies(ushort * *,ulong,int)>::~TNDFDeallocator<ushort * *,&FreeDependencies(ushort * *,ulong,int)>(void)
0x180023654  nop
0x180023655  lea     rcx, [rsp+98h+var_58]
0x18002365a  call    ??1?$CComPtrBase@UINDFHelperClass@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(void)
0x18002365f  mov     eax, edi
0x180023661  add     rsp, 60h
0x180023665  pop     r15
0x180023667  pop     r14
0x180023669  pop     r13
0x18002366b  pop     r12
0x18002366d  pop     rdi
0x18002366e  pop     rsi
0x18002366f  pop     rbx
0x180023670  retn
```
