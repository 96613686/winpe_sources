# FhePathOperations::GetTargetVolumeRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18002a678`
- end: `0x18002a79f`
- name: `?GetTargetVolumeRoot@FhePathOperations@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV23@@Z`
- size: `295`
- prototype: `__int64 __fastcall(const wchar_t **, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180021240`

## callees

- `0x1800062d0`
- `0x180007818`
- `0x1800091a4`
- `0x180009920`
- `0x18000a1ec`
- `0x18000baa8`
- `0x18000bca8`
- `0x180028cdc`
- `0x18002a678`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18002a698`
- `msvcrt!_wcsnicmp` at `0x18002a698`

## pseudocode

```c
__int64 __fastcall FhePathOperations::GetTargetVolumeRoot(const wchar_t **a1, __int64 *a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  unsigned __int64 i; // r14
  __int64 v7; // r8
  char *v8; // rdx
  volatile signed __int32 *v9; // rcx
  int *v10; // rdi
  volatile signed __int32 *v11; // r14
  unsigned __int16 v12; // ax
  int v14[14]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v15; // [rsp+60h] [rbp+8h] BYREF

  v4 = 0;
  if ( _wcsnicmp(*a1, L"\\\\", 2u) )
  {
    v12 = ATL::CSimpleStringT<unsigned short,0>::operator[](a1, 0);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      (__int64)a2,
      (__int64)L"%wc:\\",
      v12);
  }
  else
  {
    v5 = 1;
    for ( i = 0; ; ++i )
    {
      v7 = (unsigned int)(v5 + 1);
      if ( i >= 2 )
        break;
      v5 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Find(
             a1,
             L"\\",
             v7);
      if ( v5 == -1 )
      {
        v4 = -2147024809;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_2bbfbd6d1cce324407bd34be6d03c45c_Traceguids,
            2147942487LL);
        return v4;
      }
    }
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v8 = (char *)*ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                      a1,
                      &v15,
                      v7);
      v9 = (volatile signed __int32 *)(v8 - 24);
      v10 = (int *)(*a2 - 24);
      if ( v8 - 24 != (char *)v10 )
      {
        if ( v10[4] >= 0 && *(_QWORD *)v9 == *(_QWORD *)v10 )
        {
          v11 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v9);
          ATL::CStringData::Release((ATL::CStringData *)v10);
          *a2 = (__int64)(v11 + 6);
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v8, *((_DWORD *)v8 - 4));
        }
      }
      ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)v14) )
      {
        LODWORD(v15) = v14[0];
        if ( v14[0] >= 0 )
        {
          v4 = v15;
          __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18002A78F);
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              WPP_2bbfbd6d1cce324407bd34be6d03c45c_Traceguids,
              (unsigned int)v14[0]);
          v4 = v15;
          __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18002A78D);
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18002a678  push    rbx
0x18002a67a  push    rsi
0x18002a67b  push    rdi
0x18002a67c  push    r14
0x18002a67e  sub     rsp, 38h
0x18002a682  mov     rsi, rdx
0x18002a685  mov     rdi, rcx
0x18002a688  xor     ebx, ebx
0x18002a68a  lea     r8d, [rbx+2]; MaxCount
0x18002a68e  lea     rdx, asc_1800389A4; "\\\\"
0x18002a695  mov     rcx, [rcx]; String1
0x18002a698  call    cs:__imp__wcsnicmp
0x18002a69e  test    eax, eax
0x18002a6a0  jnz     loc_18002A76D
0x18002a6a6  lea     eax, [rbx+1]
0x18002a6a9  xor     r14d, r14d
0x18002a6ac  lea     r8d, [rax+1]
0x18002a6b0  mov     rcx, rdi
0x18002a6b3  cmp     r14, 2
0x18002a6b7  jnb     short loc_18002A70B
0x18002a6b9  lea     rdx, asc_180037180; "\\"
0x18002a6c0  call    ?Find@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Find(ushort const *,int)
0x18002a6c5  cmp     eax, 0FFFFFFFFh
0x18002a6c8  jnz     short loc_18002A706
0x18002a6ca  mov     ebx, 80070057h
0x18002a6cf  lea     rax, WPP_GLOBAL_Control
0x18002a6d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a6dd  cmp     rcx, rax
0x18002a6e0  jz      short loc_18002A701
0x18002a6e2  test    byte ptr [rcx+1Ch], 1
0x18002a6e6  jz      short loc_18002A701
0x18002a6e8  mov     edx, 0Fh
0x18002a6ed  mov     r9d, ebx
0x18002a6f0  lea     r8, WPP_2bbfbd6d1cce324407bd34be6d03c45c_Traceguids
0x18002a6f7  mov     rcx, [rcx+10h]
0x18002a6fb  call    WPP_SF_d
0x18002a700  nop
0x18002a701  jmp     loc_18002A793
0x18002a706  inc     r14
0x18002a709  jmp     short loc_18002A6AC
0x18002a70b  lea     rdx, [rsp+58h+arg_0]
0x18002a710  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x18002a715  nop
0x18002a716  mov     rdx, [rax]
0x18002a719  lea     rcx, [rdx-18h]
0x18002a71d  mov     rdi, [rsi]
0x18002a720  add     rdi, 0FFFFFFFFFFFFFFE8h
0x18002a724  cmp     rcx, rdi
0x18002a727  jz      short loc_18002A75D
0x18002a729  cmp     dword ptr [rdi+10h], 0
0x18002a72d  jl      short loc_18002A750
0x18002a72f  mov     rax, [rdi]
0x18002a732  cmp     [rcx], rax
0x18002a735  jnz     short loc_18002A750
0x18002a737  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18002a73c  mov     r14, rax
0x18002a73f  mov     rcx, rdi; this
0x18002a742  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002a747  lea     rax, [r14+18h]
0x18002a74b  mov     [rsi], rax
0x18002a74e  jmp     short loc_18002A75D
0x18002a750  mov     r8d, [rdx-10h]
0x18002a754  mov     rcx, rsi
0x18002a757  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18002a75c  nop
0x18002a75d  mov     rcx, [rsp+58h+arg_0]
0x18002a762  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002a766  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002a76b  jmp     short loc_18002A78B
0x18002a76d  xor     edx, edx
0x18002a76f  mov     rcx, rdi
0x18002a772  call    ??A?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::operator[](int)
0x18002a777  movzx   r8d, ax
0x18002a77b  lea     rdx, aWc; "%wc:\\"
0x18002a782  mov     rcx, rsi
0x18002a785  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18002a78a  nop
0x18002a78b  jmp     short loc_18002A793
0x18002a78d  jmp     short $+2
0x18002a78f  mov     ebx, dword ptr [rsp+58h+arg_0]
0x18002a793  mov     eax, ebx
0x18002a795  add     rsp, 38h
0x18002a799  pop     r14
0x18002a79b  pop     rdi
0x18002a79c  pop     rsi
0x18002a79d  pop     rbx
0x18002a79e  retn
```
