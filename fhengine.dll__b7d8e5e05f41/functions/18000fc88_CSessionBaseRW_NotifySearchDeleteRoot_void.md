# CSessionBaseRW::NotifySearchDeleteRoot(void)

- ea: `0x18000fc88`
- end: `0x18000fde0`
- name: `?NotifySearchDeleteRoot@CSessionBaseRW@@IEAAJXZ`
- size: `344`
- prototype: `__int64 __fastcall(CSessionBaseRW *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001f92c`

## callees

- `0x180002c24`
- `0x1800062d0`
- `0x180007818`
- `0x180008cac`
- `0x18000a1ec`
- `0x18000f55c`
- `0x18000fc88`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CSessionBaseRW::NotifySearchDeleteRoot(CSessionBaseRW *this)
{
  CSessionBaseRW *v1; // rdi
  int v2; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // rdx
  int v6; // ecx
  int v7; // eax
  int v9; // [rsp+30h] [rbp-48h] BYREF
  __int64 v10; // [rsp+38h] [rbp-40h] BYREF
  _DWORD v11[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v12; // [rsp+48h] [rbp-30h]
  __int64 v13; // [rsp+50h] [rbp-28h]
  __int64 v14; // [rsp+58h] [rbp-20h]
  int v18; // [rsp+88h] [rbp+10h]
  char v19; // [rsp+90h] [rbp+18h] BYREF
  char v20; // [rsp+98h] [rbp+20h] BYREF

  v1 = this;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v10);
  v2 = CSessionBaseRW::InitializeSearch((LPVOID *)v1);
  if ( v2 >= 0 )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        (__int64)&v10,
        (__int64)L"DP://{%s}/");
      v11[1] = 0;
      v5 = *(unsigned int *)(v10 - 16);
      v6 = *(_DWORD *)(v10 - 12) - v5;
      if ( (v6 | (1 - *(_DWORD *)(v10 - 8))) < 0 )
        ((void (__fastcall *)(__int64 *, __int64, _QWORD))ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2)(
          &v10,
          v5,
          v6 | (unsigned int)(1 - *(_DWORD *)(v10 - 8)));
      v13 = v10;
      v14 = 0;
      v11[0] = 1;
      v12 = 0;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v9) )
      {
        v18 = v9;
        if ( v9 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              193,
              &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
              (unsigned int)v9);
          v2 = v18;
          __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000FD46);
          goto LABEL_15;
        }
        v1 = this;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000FD4F);
      }
    }
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, _DWORD *, char *, char *))(**((_QWORD **)v1 + 32) + 40LL))(
           *((_QWORD *)v1 + 32),
           1,
           v11,
           &v20,
           &v19);
    v2 = 0;
    if ( v7 != -2147217887 )
      v2 = v7;
    if ( v2 < 0 )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v4 = 194;
        goto LABEL_14;
      }
    }
  }
  else
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 192;
LABEL_14:
      WPP_SF_d(v3[2], v4, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, (unsigned int)v2);
    }
  }
LABEL_15:
  ATL::CStringData::Release((ATL::CStringData *)(v10 - 24));
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000fc88  mov     [rsp+arg_0], rcx
0x18000fc8d  push    rbx
0x18000fc8e  push    rdi
0x18000fc8f  sub     rsp, 68h
0x18000fc93  mov     rdi, rcx
0x18000fc96  lea     rcx, [rsp+78h+var_40]
0x18000fc9b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000fca0  nop
0x18000fca1  mov     rcx, rdi; this
0x18000fca4  call    ?InitializeSearch@CSessionBaseRW@@IEAAJXZ; CSessionBaseRW::InitializeSearch(void)
0x18000fca9  mov     ebx, eax
0x18000fcab  test    eax, eax
0x18000fcad  jns     short loc_18000FCDA
0x18000fcaf  lea     rax, WPP_GLOBAL_Control
0x18000fcb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcbd  cmp     rcx, rax
0x18000fcc0  jz      loc_18000FDC9
0x18000fcc6  test    byte ptr [rcx+1Ch], 1
0x18000fcca  jz      loc_18000FDC9
0x18000fcd0  mov     edx, 0C0h
0x18000fcd5  jmp     loc_18000FDB5
0x18000fcda  mov     r8, [rdi+108h]
0x18000fce1  lea     rdx, aDpS; "DP://{%s}/"
0x18000fce8  lea     rcx, [rsp+78h+var_40]
0x18000fced  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000fcf2  mov     [rsp+78h+var_34], 0
0x18000fcfa  mov     rax, [rsp+78h+var_40]
0x18000fcff  mov     edx, [rax-10h]
0x18000fd02  mov     r8d, 1
0x18000fd08  sub     r8d, [rax-8]
0x18000fd0c  mov     ecx, [rax-0Ch]
0x18000fd0f  sub     ecx, edx
0x18000fd11  or      r8d, ecx
0x18000fd14  jge     short loc_18000FD20
0x18000fd16  lea     rcx, [rsp+78h+var_40]
0x18000fd1b  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18000fd20  mov     rax, [rsp+78h+var_40]
0x18000fd25  mov     [rsp+78h+var_28], rax
0x18000fd2a  mov     [rsp+78h+var_20], 0
0x18000fd33  mov     [rsp+78h+var_38], 1
0x18000fd3b  mov     [rsp+78h+var_30], 0
0x18000fd44  jmp     short loc_18000FD57
0x18000fd46  mov     ebx, [rsp+78h+arg_8]
0x18000fd4d  jmp     short loc_18000FDC9
0x18000fd4f  mov     rdi, [rsp+78h+arg_0]
0x18000fd57  mov     rcx, [rdi+100h]
0x18000fd5e  mov     rax, [rcx]
0x18000fd61  lea     rdx, [rsp+78h+arg_10]
0x18000fd69  mov     [rsp+78h+var_58], rdx
0x18000fd6e  lea     r9, [rsp+78h+arg_18]
0x18000fd76  lea     r8, [rsp+78h+var_38]
0x18000fd7b  mov     edx, 1
0x18000fd80  mov     rax, [rax+28h]
0x18000fd84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd89  xor     ebx, ebx
0x18000fd8b  cmp     eax, 80040E21h
0x18000fd90  cmovnz  ebx, eax
0x18000fd93  test    ebx, ebx
0x18000fd95  jns     short loc_18000FDC9
0x18000fd97  lea     rax, WPP_GLOBAL_Control
0x18000fd9e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fda5  cmp     rcx, rax
0x18000fda8  jz      short loc_18000FDC9
0x18000fdaa  test    byte ptr [rcx+1Ch], 1
0x18000fdae  jz      short loc_18000FDC9
0x18000fdb0  mov     edx, 0C2h
0x18000fdb5  mov     r9d, ebx
0x18000fdb8  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000fdbf  mov     rcx, [rcx+10h]
0x18000fdc3  call    WPP_SF_d
0x18000fdc8  nop
0x18000fdc9  mov     rcx, [rsp+78h+var_40]
0x18000fdce  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000fdd2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000fdd7  mov     eax, ebx
0x18000fdd9  add     rsp, 68h
0x18000fddd  pop     rdi
0x18000fdde  pop     rbx
0x18000fddf  retn
```
