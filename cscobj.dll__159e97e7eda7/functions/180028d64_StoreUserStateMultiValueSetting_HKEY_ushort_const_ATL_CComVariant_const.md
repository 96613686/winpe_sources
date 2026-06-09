# StoreUserStateMultiValueSetting(HKEY__ *,ushort const *,ATL::CComVariant const &)

- ea: `0x180028d64`
- end: `0x18002916c`
- name: `?StoreUserStateMultiValueSetting@@YAJPEAUHKEY__@@PEBGAEBVCComVariant@ATL@@@Z`
- size: `1032`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const struct ATL::CComVariant *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a840`

## callees

- `0x18000a840`
- `0x18000f5cc`
- `0x18001886c`
- `0x18001c898`
- `0x18001d74c`
- `0x18001d8e4`
- `0x18001d954`
- `0x18001d9d8`
- `0x180028d64`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180028d8a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180028d8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StoreUserStateMultiValueSetting(
        HKEY a1,
        const unsigned __int16 *a2,
        const struct ATL::CComVariant *a3)
{
  int i; // ebx
  int LowerBound; // edi
  int v6; // edi
  int v7; // edi
  int v8; // esi
  int v9; // esi
  int v10; // r15d
  __int64 v11; // r12
  int v12; // r14d
  unsigned __int16 v13; // r13
  int v14; // r14d
  int v15; // edi
  int v16; // ebx
  __int64 v17; // r9
  __int64 v18; // rdx
  unsigned int Count; // eax
  int v21; // edi
  __int64 v24; // [rsp+90h] [rbp+58h] BYREF
  __int64 v25; // [rsp+98h] [rbp+60h] BYREF

  RegDeleteKeyExW(a1, a2, 0, 0);
  ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(&v24, *((_QWORD *)a3 + 1));
  for ( i = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v24); ; ++i )
  {
    if ( i >= (int)ATL::CComSafeArray<unsigned short *,8>::GetCount(&v24) )
    {
      ATL::CComSafeArray<unsigned short *,8>::Destroy(&v24);
      return 0;
    }
    if ( !v24 )
      ATL::AtlThrowImpl(-2147467259);
    LowerBound = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v24);
    if ( i < LowerBound || i > (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v24) )
      goto LABEL_47;
    if ( *(_WORD *)(*(_QWORD *)(v24 + 16) + 24LL * (i - LowerBound)) != 8204 )
      break;
    v6 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v24);
    if ( i < v6 || i > (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v24) )
      goto LABEL_47;
    ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(
      &v25,
      *(_QWORD *)(*(_QWORD *)(v24 + 16) + 24LL * (i - v6) + 8));
    if ( (unsigned int)ATL::CComSafeArray<unsigned short *,8>::GetCount(&v25) < 2 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        Count = ATL::CComSafeArray<unsigned short *,8>::GetCount(&v25);
        v18 = 40;
        v17 = Count;
        goto LABEL_38;
      }
LABEL_39:
      v15 = -2147418113;
LABEL_40:
      ATL::CComSafeArray<unsigned short *,8>::Destroy(&v25);
      ATL::CComSafeArray<unsigned short *,8>::Destroy(&v24);
      return (unsigned int)v15;
    }
    v7 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v25);
    if ( !v25 )
      goto LABEL_34;
    v8 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v25);
    if ( v7 < v8 || v7 > (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v25) )
      goto LABEL_33;
    if ( *(_WORD *)(*(_QWORD *)(v25 + 16) + 24LL * (v7 - v8)) != 8 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        if ( !v24 )
LABEL_34:
          ATL::AtlThrowImpl(-2147467259);
        v16 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v24);
        if ( v7 < v16 || v7 > (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v24) )
LABEL_33:
          ATL::AtlThrowImpl(-2147024809);
        v17 = *(unsigned __int16 *)(*(_QWORD *)(v24 + 16) + 24LL * (v7 - v16));
        v18 = 41;
LABEL_38:
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v18, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v17);
      }
      goto LABEL_39;
    }
    v9 = v7 + 1;
    v10 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v25);
    if ( v7 + 1 < v10 || v9 > (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v25) )
      goto LABEL_33;
    if ( !v25 )
      goto LABEL_34;
    v11 = *(_QWORD *)(v25 + 16);
    v12 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v25);
    if ( v9 < v12 || v9 > (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v25) )
      goto LABEL_33;
    if ( !v25 )
      goto LABEL_34;
    v13 = *(_WORD *)(*(_QWORD *)(v25 + 16) + 24LL * (v9 - v12));
    v14 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v25);
    if ( v7 < v14 || v7 > (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v25) )
      goto LABEL_33;
    v15 = StoreUserStateSetting(
            a1,
            a2,
            *(LPCWSTR *)(*(_QWORD *)(v25 + 16) + 24LL * (v7 - v14) + 8),
            v13,
            (VARIANTARG *)(v11 + 24LL * (v9 - v10)));
    if ( v15 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          42,
          WPP_313c576492293c0704086ae70e07ed75_Traceguids,
          (unsigned int)v15);
      goto LABEL_40;
    }
    ATL::CComSafeArray<unsigned short *,8>::Destroy(&v25);
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v21 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v24);
    if ( i < v21 || i > (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v24) )
LABEL_47:
      ATL::AtlThrowImpl(-2147024809);
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      39,
      WPP_313c576492293c0704086ae70e07ed75_Traceguids,
      *(unsigned __int16 *)(*(_QWORD *)(v24 + 16) + 24LL * (i - v21)));
  }
  ATL::CComSafeArray<unsigned short *,8>::Destroy(&v24);
  return 2147549183LL;
}

```

## disassembly

```asm
0x180028d64  mov     [rsp-40h+lpSubKey], rdx
0x180028d69  mov     [rsp-40h+hKey], rcx
0x180028d6e  push    rbp
0x180028d6f  push    rbx
0x180028d70  push    rsi
0x180028d71  push    rdi
0x180028d72  push    r12
0x180028d74  push    r13
0x180028d76  push    r14
0x180028d78  push    r15
0x180028d7a  mov     rbp, rsp
0x180028d7d  sub     rsp, 38h
0x180028d81  mov     rbx, r8
0x180028d84  xor     r9d, r9d; Reserved
0x180028d87  xor     r8d, r8d; samDesired
0x180028d8a  call    cs:__imp_RegDeleteKeyExW
0x180028d90  mov     rdx, [rbx+8]
0x180028d94  lea     rcx, [rbp+arg_10]
0x180028d98  call    ??0?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(tagSAFEARRAY const *)
0x180028d9d  nop
0x180028d9e  lea     rcx, [rbp+arg_10]
0x180028da2  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x180028da7  mov     ebx, eax
0x180028da9  lea     rcx, [rbp+arg_10]
0x180028dad  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x180028db2  cmp     ebx, eax
0x180028db4  jge     loc_180029150
0x180028dba  cmp     [rbp+arg_10], 0
0x180028dbf  jz      loc_180029145
0x180028dc5  lea     rcx, [rbp+arg_10]
0x180028dc9  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x180028dce  mov     edi, eax
0x180028dd0  cmp     ebx, eax
0x180028dd2  jl      loc_18002913A
0x180028dd8  lea     rcx, [rbp+arg_10]
0x180028ddc  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x180028de1  cmp     ebx, eax
0x180028de3  jg      loc_18002913A
0x180028de9  mov     eax, ebx
0x180028deb  sub     eax, edi
0x180028ded  cdqe
0x180028def  lea     rdx, [rax+rax*2]
0x180028df3  mov     rax, [rbp+arg_10]
0x180028df7  mov     rcx, [rax+10h]
0x180028dfb  mov     eax, 200Ch
0x180028e00  cmp     [rcx+rdx*8], ax
0x180028e04  jnz     loc_1800290C2
0x180028e0a  lea     rcx, [rbp+arg_10]
0x180028e0e  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x180028e13  mov     edi, eax
0x180028e15  cmp     ebx, eax
0x180028e17  jl      loc_18002913A
0x180028e1d  lea     rcx, [rbp+arg_10]
0x180028e21  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x180028e26  cmp     ebx, eax
0x180028e28  jg      loc_18002913A
0x180028e2e  mov     eax, ebx
0x180028e30  sub     eax, edi
0x180028e32  cdqe
0x180028e34  lea     rcx, [rax+rax*2]
0x180028e38  mov     rax, [rbp+arg_10]
0x180028e3c  mov     rdx, [rax+10h]
0x180028e40  mov     rdx, [rdx+rcx*8+8]
0x180028e45  lea     rcx, [rbp+arg_18]
0x180028e49  call    ??0?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(tagSAFEARRAY const *)
0x180028e4e  nop
0x180028e4f  lea     rcx, [rbp+arg_18]
0x180028e53  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x180028e58  cmp     eax, 2
0x180028e5b  jb      loc_180029062
0x180028e61  lea     rcx, [rbp+arg_18]
0x180028e65  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x180028e6a  mov     edi, eax
0x180028e6c  cmp     [rbp+arg_18], 0
0x180028e71  jz      loc_180029057
0x180028e77  lea     rcx, [rbp+arg_18]
0x180028e7b  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x180028e80  mov     esi, eax
0x180028e82  cmp     edi, eax
0x180028e84  jl      loc_18002904C
0x180028e8a  lea     rcx, [rbp+arg_18]
0x180028e8e  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x180028e93  cmp     edi, eax
0x180028e95  jg      loc_18002904C
0x180028e9b  mov     eax, edi
0x180028e9d  sub     eax, esi
0x180028e9f  cdqe
0x180028ea1  lea     rdx, [rax+rax*2]
0x180028ea5  mov     rax, [rbp+arg_18]
0x180028ea9  mov     rcx, [rax+10h]
0x180028ead  cmp     word ptr [rcx+rdx*8], 8
0x180028eb2  jnz     loc_180028FEB
0x180028eb8  lea     esi, [rdi+1]
0x180028ebb  lea     rcx, [rbp+arg_18]
0x180028ebf  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x180028ec4  mov     r15d, eax
0x180028ec7  cmp     esi, eax
0x180028ec9  jl      loc_18002904C
0x180028ecf  lea     rcx, [rbp+arg_18]
0x180028ed3  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x180028ed8  cmp     esi, eax
0x180028eda  jg      loc_18002904C
0x180028ee0  mov     rcx, [rbp+arg_18]
0x180028ee4  test    rcx, rcx
0x180028ee7  jz      loc_180029057
0x180028eed  mov     r12, [rcx+10h]
0x180028ef1  lea     rcx, [rbp+arg_18]
0x180028ef5  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x180028efa  mov     r14d, eax
0x180028efd  cmp     esi, eax
0x180028eff  jl      loc_18002904C
0x180028f05  lea     rcx, [rbp+arg_18]
0x180028f09  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x180028f0e  cmp     esi, eax
0x180028f10  jg      loc_18002904C
0x180028f16  mov     rcx, [rbp+arg_18]
0x180028f1a  test    rcx, rcx
0x180028f1d  jz      loc_180029057
0x180028f23  mov     eax, esi
0x180028f25  sub     eax, r14d
0x180028f28  cdqe
0x180028f2a  lea     rdx, [rax+rax*2]
0x180028f2e  mov     rax, [rcx+10h]
0x180028f32  movzx   r13d, word ptr [rax+rdx*8]
0x180028f37  lea     rcx, [rbp+arg_18]
0x180028f3b  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x180028f40  mov     r14d, eax
0x180028f43  cmp     edi, eax
0x180028f45  jl      loc_18002904C
0x180028f4b  lea     rcx, [rbp+arg_18]
0x180028f4f  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x180028f54  cmp     edi, eax
0x180028f56  jg      loc_18002904C
0x180028f5c  sub     esi, r15d
0x180028f5f  movsxd  rcx, esi
0x180028f62  lea     rdx, [rcx+rcx*2]
0x180028f66  lea     r10, [r12+rdx*8]
0x180028f6a  sub     edi, r14d
0x180028f6d  movsxd  rax, edi
0x180028f70  lea     rcx, [rax+rax*2]
0x180028f74  mov     rax, [rbp+arg_18]
0x180028f78  mov     r8, [rax+10h]
0x180028f7c  mov     [rsp+38h+var_18], r10; struct ATL::CComVariant *
0x180028f81  movzx   r9d, r13w; unsigned __int16
0x180028f85  mov     r8, [r8+rcx*8+8]; lpValueName
0x180028f8a  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180028f8e  mov     rcx, [rbp+hKey]; hKey
0x180028f92  call    ?StoreUserStateSetting@@YAJPEAUHKEY__@@PEBG1GAEBVCComVariant@ATL@@@Z; StoreUserStateSetting(HKEY__ *,ushort const *,ushort const *,ushort,ATL::CComVariant const &)
0x180028f97  mov     edi, eax
0x180028f99  test    eax, eax
0x180028f9b  js      short loc_180028FAD
0x180028f9d  lea     rcx, [rbp+arg_18]
0x180028fa1  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x180028fa6  inc     ebx
0x180028fa8  jmp     loc_180028DA9
0x180028fad  lea     rax, WPP_GLOBAL_Control
0x180028fb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180028fbb  cmp     rcx, rax
0x180028fbe  jz      loc_1800290A8
0x180028fc4  test    byte ptr [rcx+1Ch], 1
0x180028fc8  jz      loc_1800290A8
0x180028fce  mov     edx, 2Ah ; '*'
0x180028fd3  mov     r9d, edi
0x180028fd6  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x180028fdd  mov     rcx, [rcx+10h]
0x180028fe1  call    WPP_SF_d
0x180028fe6  jmp     loc_1800290A8
0x180028feb  lea     rax, WPP_GLOBAL_Control
0x180028ff2  mov     rcx, cs:WPP_GLOBAL_Control
0x180028ff9  cmp     rcx, rax
0x180028ffc  jz      loc_1800290A3
0x180029002  test    byte ptr [rcx+1Ch], 1
0x180029006  jz      loc_1800290A3
0x18002900c  cmp     [rbp+arg_10], 0
0x180029011  jz      short loc_180029057
0x180029013  lea     rcx, [rbp+arg_10]
0x180029017  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18002901c  mov     ebx, eax
0x18002901e  cmp     edi, eax
0x180029020  jl      short loc_18002904C
0x180029022  lea     rcx, [rbp+arg_10]
0x180029026  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18002902b  cmp     edi, eax
0x18002902d  jg      short loc_18002904C
0x18002902f  sub     edi, ebx
0x180029031  movsxd  rax, edi
0x180029034  lea     rdx, [rax+rax*2]
0x180029038  mov     rax, [rbp+arg_10]
0x18002903c  mov     rcx, [rax+10h]
0x180029040  movzx   r9d, word ptr [rcx+rdx*8]
0x180029045  mov     edx, 29h ; ')'
0x18002904a  jmp     short loc_18002908C
0x18002904c  mov     ecx, 80070057h; int
0x180029051  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180029057  mov     ecx, 80004005h; int
0x18002905c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180029062  lea     rax, WPP_GLOBAL_Control
0x180029069  mov     rcx, cs:WPP_GLOBAL_Control
0x180029070  cmp     rcx, rax
0x180029073  jz      short loc_1800290A3
0x180029075  test    byte ptr [rcx+1Ch], 1
0x180029079  jz      short loc_1800290A3
0x18002907b  lea     rcx, [rbp+arg_18]
0x18002907f  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x180029084  mov     edx, 28h ; '('
0x180029089  mov     r9d, eax
0x18002908c  mov     rcx, cs:WPP_GLOBAL_Control
0x180029093  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x18002909a  mov     rcx, [rcx+10h]
0x18002909e  call    WPP_SF_d
0x1800290a3  mov     edi, 8000FFFFh
0x1800290a8  lea     rcx, [rbp+arg_18]
0x1800290ac  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x1800290b1  nop
0x1800290b2  lea     rcx, [rbp+arg_10]
0x1800290b6  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x1800290bb  mov     eax, edi
0x1800290bd  jmp     loc_18002915B
0x1800290c2  lea     rax, WPP_GLOBAL_Control
0x1800290c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800290d0  cmp     rcx, rax
0x1800290d3  jz      short loc_18002912A
0x1800290d5  test    byte ptr [rcx+1Ch], 1
0x1800290d9  jz      short loc_18002912A
0x1800290db  lea     rcx, [rbp+arg_10]
0x1800290df  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x1800290e4  mov     edi, eax
0x1800290e6  cmp     ebx, eax
0x1800290e8  jl      short loc_18002913A
0x1800290ea  lea     rcx, [rbp+arg_10]
0x1800290ee  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x1800290f3  cmp     ebx, eax
0x1800290f5  jg      short loc_18002913A
0x1800290f7  sub     ebx, edi
0x1800290f9  movsxd  rax, ebx
0x1800290fc  lea     rdx, [rax+rax*2]
0x180029100  mov     rax, [rbp+arg_10]
0x180029104  mov     rcx, [rax+10h]
0x180029108  movzx   r9d, word ptr [rcx+rdx*8]
0x18002910d  mov     edx, 27h ; '''
0x180029112  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x180029119  mov     rcx, cs:WPP_GLOBAL_Control
0x180029120  mov     rcx, [rcx+10h]
0x180029124  call    WPP_SF_d
0x180029129  nop
0x18002912a  lea     rcx, [rbp+arg_10]
0x18002912e  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x180029133  mov     eax, 8000FFFFh
0x180029138  jmp     short loc_18002915B
0x18002913a  mov     ecx, 80070057h; int
0x18002913f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180029145  mov     ecx, 80004005h; int
0x18002914a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180029150  lea     rcx, [rbp+arg_10]
0x180029154  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x180029159  xor     eax, eax
0x18002915b  add     rsp, 38h
0x18002915f  pop     r15
0x180029161  pop     r14
0x180029163  pop     r13
0x180029165  pop     r12
0x180029167  pop     rdi
0x180029168  pop     rsi
0x180029169  pop     rbx
0x18002916a  pop     rbp
0x18002916b  retn
```
