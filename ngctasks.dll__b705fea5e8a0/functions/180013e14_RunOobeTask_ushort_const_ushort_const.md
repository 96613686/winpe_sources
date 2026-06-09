# RunOobeTask(ushort const *,ushort const *)

- ea: `0x180013e14`
- end: `0x180014142`
- name: `?RunOobeTask@@YAJPEBG0@Z`
- size: `814`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800106ac`

## callees

- `0x180008ab0`
- `0x18000cc34`
- `0x180011814`
- `0x180013e14`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013ee6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013ee6`
- `OLEAUT32!__imp_SysAllocString` at `0x180013e32`
- `OLEAUT32!__imp_SysAllocString` at `0x180013e7d`
- `OLEAUT32!__imp_SysAllocString` at `0x180013e32`
- `OLEAUT32!__imp_SysAllocString` at `0x180013e7d`
- `OLEAUT32!__imp_SysFreeString` at `0x180013f19`
- `OLEAUT32!__imp_SysFreeString` at `0x180014120`
- `OLEAUT32!__imp_SysFreeString` at `0x18001412d`
- `OLEAUT32!__imp_SysFreeString` at `0x180013f19`
- `OLEAUT32!__imp_SysFreeString` at `0x180014120`
- `OLEAUT32!__imp_SysFreeString` at `0x18001412d`

## string_xrefs

- `0x180013e59`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180013ea4`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180013ef9`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180013f8e`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180013fd3`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180014026`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x1800140b9`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall RunOobeTask(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  unsigned __int16 *v3; // rax
  unsigned int v4; // esi
  OLECHAR *v5; // rcx
  unsigned __int16 *v6; // rax
  OLECHAR *v7; // rbx
  OLECHAR *v8; // rcx
  HRESULT v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  LPVOID v17; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v19; // [rsp+50h] [rbp-B0h] BYREF
  BSTR v20; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v21[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v22[4]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v23; // [rsp+80h] [rbp-80h]
  BSTR bstrString; // [rsp+90h] [rbp-70h] BYREF
  __int128 v25; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v26; // [rsp+B0h] [rbp-50h]
  __int128 v27; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v28; // [rsp+D0h] [rbp-30h]
  __int128 v29; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v30; // [rsp+F0h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+28h]

  v20 = 0;
  v3 = SysAllocString(a1);
  ATL::CComBSTR::Attach(&v20, v3);
  if ( v20 )
  {
    bstrString = 0;
    v6 = SysAllocString(a2);
    ATL::CComBSTR::Attach(&bstrString, v6);
    v7 = bstrString;
    if ( bstrString )
    {
      v17 = 0;
      v9 = CoCreateInstance(
             &GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd,
             0,
             1u,
             &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,
             &v17);
      v4 = v9;
      if ( v9 >= 0 )
      {
        *(_OWORD *)v22 = 0;
        LOWORD(v22[0]) = 1;
        v23 = 0;
        v27 = *(_OWORD *)v22;
        v28 = 0;
        v29 = *(_OWORD *)v22;
        v30 = 0;
        v25 = *(_OWORD *)v22;
        v26 = 0;
        v10 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *))(*(_QWORD *)v17 + 80LL))(
                v17,
                &v25,
                &v29,
                &v27);
        v4 = v10;
        if ( v10 >= 0 )
        {
          v18 = 0;
          v11 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v17 + 56LL))(v17, 0, &v18);
          v4 = v11;
          if ( v11 >= 0 )
          {
            v19 = 0;
            v12 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v18 + 104LL))(v18, v20, &v19);
            v4 = v12;
            if ( v12 >= 0 )
            {
              *(_QWORD *)v22 = 8;
              *(_QWORD *)&v22[2] = v7;
              v21[0] = 0;
              v25 = *(_OWORD *)v22;
              v26 = 0;
              v13 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)v19 + 104LL))(v19, &v25, 2);
              v4 = v13;
              if ( v13 >= 0 )
              {
                ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(v21);
                ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v19);
                ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v18);
                ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>((__int64 *)&v17);
                SysFreeString(v7);
                v4 = 0;
                goto LABEL_18;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x6B2,
                (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
                (const char *)(unsigned int)v13,
                0);
              ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(v21);
              ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v19);
              ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v18);
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x6A1,
                (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
                (const char *)(unsigned int)v12,
                (int)v22);
              ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v19);
              ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v18);
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x69C,
              (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
              (const char *)(unsigned int)v11,
              (int)v22);
            ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v18);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x698,
            (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
            (const char *)(unsigned int)v10,
            (int)v22);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x690,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
          (const char *)(unsigned int)v9,
          ppva);
      }
      ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>((__int64 *)&v17);
      v8 = v7;
    }
    else
    {
      v4 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x688,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)0x8007000ELL,
        ppv);
      v8 = 0;
    }
    SysFreeString(v8);
LABEL_18:
    v5 = v20;
    goto LABEL_19;
  }
  v4 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x684,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
    (const char *)0x8007000ELL,
    ppv);
  v5 = 0;
LABEL_19:
  SysFreeString(v5);
  return v4;
}

```

## disassembly

```asm
0x180013e14  push    rbp
0x180013e16  push    rbx
0x180013e17  push    rsi
0x180013e18  push    r15
0x180013e1a  lea     rbp, [rsp-8]
0x180013e1f  sub     rsp, 108h
0x180013e26  mov     rbx, rdx
0x180013e29  mov     [rsp+120h+var_C8], 0
0x180013e32  call    cs:__imp_SysAllocString
0x180013e38  mov     rdx, rax; unsigned __int16 *
0x180013e3b  lea     rcx, [rsp+120h+var_C8]; this
0x180013e40  call    ?Attach@CComBSTR@ATL@@QEAAXPEAG@Z; ATL::CComBSTR::Attach(ushort *)
0x180013e45  cmp     [rsp+120h+var_C8], 0
0x180013e4b  jnz     short loc_180013E72
0x180013e4d  mov     rcx, [rbp+28h]; this
0x180013e51  mov     esi, 8007000Eh
0x180013e56  mov     r9d, esi; char *
0x180013e59  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180013e60  mov     edx, 684h; void *
0x180013e65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013e6a  nop
0x180013e6b  xor     ecx, ecx
0x180013e6d  jmp     loc_18001412D
0x180013e72  mov     [rbp+20h+bstrString], 0
0x180013e7a  mov     rcx, rbx; psz
0x180013e7d  call    cs:__imp_SysAllocString
0x180013e83  mov     rdx, rax; unsigned __int16 *
0x180013e86  lea     rcx, [rbp+20h+bstrString]; this
0x180013e8a  call    ?Attach@CComBSTR@ATL@@QEAAXPEAG@Z; ATL::CComBSTR::Attach(ushort *)
0x180013e8f  mov     rbx, [rbp+20h+bstrString]
0x180013e93  test    rbx, rbx
0x180013e96  jnz     short loc_180013EBA
0x180013e98  mov     rcx, [rbp+28h]; this
0x180013e9c  mov     esi, 8007000Eh
0x180013ea1  mov     r9d, esi; char *
0x180013ea4  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180013eab  mov     edx, 688h; void *
0x180013eb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013eb5  nop
0x180013eb6  xor     ecx, ecx
0x180013eb8  jmp     short loc_180013F19
0x180013eba  mov     [rsp+120h+var_E0], 0
0x180013ec3  lea     rax, [rsp+120h+var_E0]
0x180013ec8  mov     [rsp+120h+ppv], rax; int
0x180013ecd  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180013ed4  mov     r15d, 1
0x180013eda  mov     r8d, r15d; dwClsContext
0x180013edd  xor     edx, edx; pUnkOuter
0x180013edf  lea     rcx, _GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd; rclsid
0x180013ee6  call    cs:__imp_CoCreateInstance
0x180013eec  mov     esi, eax
0x180013eee  test    eax, eax
0x180013ef0  jns     short loc_180013F24
0x180013ef2  mov     rcx, [rbp+28h]; this
0x180013ef6  mov     r9d, eax; char *
0x180013ef9  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180013f00  mov     edx, 690h; void *
0x180013f05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013f0a  nop
0x180013f0b  lea     rcx, [rsp+120h+var_E0]
0x180013f10  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x180013f15  nop
0x180013f16  mov     rcx, rbx; bstrString
0x180013f19  call    cs:__imp_SysFreeString
0x180013f1f  jmp     loc_180014128
0x180013f24  xorps   xmm0, xmm0
0x180013f27  xor     eax, eax
0x180013f29  movups  xmmword ptr [rsp+120h+var_B0], xmm0
0x180013f2e  mov     word ptr [rsp+120h+var_B0], r15w
0x180013f34  mov     rcx, [rsp+120h+var_E0]
0x180013f39  movups  xmm1, xmmword ptr [rsp+120h+var_B0]
0x180013f3e  movaps  xmmword ptr [rsp+120h+var_B0], xmm1
0x180013f43  mov     [rbp+20h+var_A0], rax
0x180013f47  movaps  [rbp+20h+var_60], xmm1
0x180013f4b  mov     [rbp+20h+var_50], rax
0x180013f4f  movaps  [rbp+20h+var_40], xmm1
0x180013f53  mov     [rbp+20h+var_30], rax
0x180013f57  movaps  [rbp+20h+var_80], xmm1
0x180013f5b  mov     [rbp+20h+var_70], rax
0x180013f5f  mov     rax, [rcx]
0x180013f62  lea     rdx, [rsp+120h+var_B0]
0x180013f67  mov     [rsp+120h+ppv], rdx; int
0x180013f6c  lea     r9, [rbp+20h+var_60]
0x180013f70  lea     r8, [rbp+20h+var_40]
0x180013f74  lea     rdx, [rbp+20h+var_80]
0x180013f78  mov     rax, [rax+50h]
0x180013f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f81  mov     esi, eax
0x180013f83  test    eax, eax
0x180013f85  jns     short loc_180013FA5
0x180013f87  mov     rcx, [rbp+28h]; this
0x180013f8b  mov     r9d, eax; char *
0x180013f8e  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180013f95  mov     edx, 698h; void *
0x180013f9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013f9f  nop
0x180013fa0  jmp     loc_180013F0B
0x180013fa5  mov     [rsp+120h+var_D8], 0
0x180013fae  mov     rcx, [rsp+120h+var_E0]
0x180013fb3  mov     rax, [rcx]
0x180013fb6  lea     r8, [rsp+120h+var_D8]
0x180013fbb  xor     edx, edx
0x180013fbd  mov     rax, [rax+38h]
0x180013fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fc6  mov     esi, eax
0x180013fc8  test    eax, eax
0x180013fca  jns     short loc_180013FF5
0x180013fcc  mov     rcx, [rbp+28h]; this
0x180013fd0  mov     r9d, eax; char *
0x180013fd3  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180013fda  mov     edx, 69Ch; void *
0x180013fdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013fe4  nop
0x180013fe5  lea     rcx, [rsp+120h+var_D8]
0x180013fea  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x180013fef  nop
0x180013ff0  jmp     loc_180013F0B
0x180013ff5  mov     [rsp+120h+var_D0], 0
0x180013ffe  mov     rcx, [rsp+120h+var_D8]
0x180014003  mov     rax, [rcx]
0x180014006  lea     r8, [rsp+120h+var_D0]
0x18001400b  mov     rdx, [rsp+120h+var_C8]
0x180014010  mov     rax, [rax+68h]
0x180014014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014019  mov     esi, eax
0x18001401b  test    eax, eax
0x18001401d  jns     short loc_180014053
0x18001401f  mov     rcx, [rbp+28h]; this
0x180014023  mov     r9d, eax; char *
0x180014026  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x18001402d  mov     edx, 6A1h; void *
0x180014032  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014037  nop
0x180014038  lea     rcx, [rsp+120h+var_D0]
0x18001403d  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x180014042  nop
0x180014043  lea     rcx, [rsp+120h+var_D8]
0x180014048  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x18001404d  nop
0x18001404e  jmp     loc_180013F0B
0x180014053  xorps   xmm0, xmm0
0x180014056  xor     edx, edx
0x180014058  movups  xmmword ptr [rsp+120h+var_B0], xmm0
0x18001405d  lea     eax, [rdx+8]
0x180014060  mov     word ptr [rsp+120h+var_B0], ax
0x180014065  mov     qword ptr [rsp+120h+var_B0+8], rbx
0x18001406a  mov     [rsp+120h+var_C0], rdx
0x18001406f  mov     rcx, [rsp+120h+var_D0]
0x180014074  movups  xmm0, xmmword ptr [rsp+120h+var_B0]
0x180014079  movaps  [rbp+20h+var_80], xmm0
0x18001407d  mov     [rbp+20h+var_70], rdx
0x180014081  mov     rax, [rcx]
0x180014084  lea     rdx, [rsp+120h+var_C0]
0x180014089  mov     [rsp+120h+var_F8], rdx
0x18001408e  mov     [rsp+120h+ppv], 0; int
0x180014097  or      r9d, 0FFFFFFFFh
0x18001409b  lea     r8d, [r9+3]
0x18001409f  lea     rdx, [rbp+20h+var_80]
0x1800140a3  mov     rax, [rax+68h]
0x1800140a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140ac  mov     esi, eax
0x1800140ae  test    eax, eax
0x1800140b0  jns     short loc_1800140F1
0x1800140b2  mov     rcx, [rbp+28h]; this
0x1800140b6  mov     r9d, eax; char *
0x1800140b9  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800140c0  mov     edx, 6B2h; void *
0x1800140c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800140ca  nop
0x1800140cb  lea     rcx, [rsp+120h+var_C0]
0x1800140d0  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x1800140d5  nop
0x1800140d6  lea     rcx, [rsp+120h+var_D0]
0x1800140db  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x1800140e0  nop
0x1800140e1  lea     rcx, [rsp+120h+var_D8]
0x1800140e6  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x1800140eb  nop
0x1800140ec  jmp     loc_180013F0B
0x1800140f1  lea     rcx, [rsp+120h+var_C0]
0x1800140f6  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x1800140fb  nop
0x1800140fc  lea     rcx, [rsp+120h+var_D0]
0x180014101  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x180014106  nop
0x180014107  lea     rcx, [rsp+120h+var_D8]
0x18001410c  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x180014111  nop
0x180014112  lea     rcx, [rsp+120h+var_E0]
0x180014117  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x18001411c  nop
0x18001411d  mov     rcx, rbx; bstrString
0x180014120  call    cs:__imp_SysFreeString
0x180014126  xor     esi, esi
0x180014128  mov     rcx, [rsp+120h+var_C8]; bstrString
0x18001412d  call    cs:__imp_SysFreeString
0x180014133  mov     eax, esi
0x180014135  add     rsp, 108h
0x18001413c  pop     r15
0x18001413e  pop     rsi
0x18001413f  pop     rbx
0x180014140  pop     rbp
0x180014141  retn
```
