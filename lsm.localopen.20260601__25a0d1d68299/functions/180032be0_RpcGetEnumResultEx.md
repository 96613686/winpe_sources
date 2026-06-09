# RpcGetEnumResultEx

- ea: `0x180032be0`
- end: `0x1800330b4`
- name: `RpcGetEnumResultEx`
- size: `1236`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x1800077a0`
- `0x180009580`
- `0x18000bd30`
- `0x18000c684`
- `0x18000e8b0`
- `0x18000f260`
- `0x180012e04`
- `0x18001e9d0`
- `0x180022030`
- `0x180022200`
- `0x180023984`
- `0x180032be0`
- `0x18004e850`
- `0x18004f354`
- `0x18005ea70`
- `0x18005eee4`
- `0x18009959c`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032d81`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032f07`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032d81`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032f07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033088`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800330a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033088`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800330a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032f3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032f3a`

## string_xrefs

- `0x180032d41`: `Impersonate.ImpersonateRpcClient failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcGetEnumResultEx(__int64 a1, _QWORD *a2, unsigned int a3, unsigned int *a4)
{
  int v9; // ebx
  int v10; // eax
  int v11; // esi
  __int64 v12; // r13
  char *v13; // rax
  char *v14; // rdi
  unsigned int v15; // r14d
  int v16; // eax
  HLOCAL v17; // rax
  __int64 v18; // rcx
  char *v19; // rdx
  unsigned int i; // esi
  void *v21; // rcx
  _WORD v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD uBytes[3]; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v24; // [rsp+40h] [rbp-C0h] BYREF
  void *Src; // [rsp+48h] [rbp-B8h] BYREF
  char *v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v28[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v29[8]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+90h] [rbp-70h]
  __m256i v32; // [rsp+A0h] [rbp-60h]
  __int128 v33; // [rsp+C0h] [rbp-40h]
  __int128 v34; // [rsp+D0h] [rbp-30h]
  _BYTE v35[592]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v36[40]; // [rsp+330h] [rbp+230h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_EnumResultExSessionCountSync>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_EnumResultExSessionCountSync>::GetImpl'::`2'::impl) )
    return RpcGetEnumResultExImpl(a1, a2, a3, a4);
  v28[0] = 0;
  v27 = 0;
  v22[0] = 0;
  Src = 0;
  memset(uBytes, 0, sizeof(uBytes));
  memset_0(v29, 0, 0x70u);
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v35, 0, "RpcGetEnumResultEx");
  if ( !a1 )
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "hEnum", "RpcGetEnumResultEx");
LABEL_5:
    v9 = -2147024809;
    goto LABEL_6;
  }
  SmartPtr<IWinlogonNotify>::operator=(&v27, *(_QWORD *)(a1 + 1592));
  if ( !a2 || !a4 )
    goto LABEL_5;
  *a2 = 0;
  *a4 = 0;
  v10 = CImpersonate::ImpersonateRpcClient((CImpersonate *)v22);
  v9 = v10;
  if ( v10 >= 0 )
  {
    v11 = 3;
    if ( a3 <= 3 )
      v11 = a3;
    v12 = (unsigned int)CTSPerfProvider::TotalSessions;
    if ( !CTSPerfProvider::TotalSessions )
    {
      v9 = 0;
      goto LABEL_7;
    }
    v13 = (char *)LocalAlloc(0x40u, 120LL * (unsigned int)CTSPerfProvider::TotalSessions);
    v14 = v13;
    if ( v13 )
    {
      v26 = v13;
      memset_0(v13, 0, 120 * v12);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 88LL))(v27);
      v15 = 0;
      if ( (_DWORD)v12 )
      {
        while ( 1 )
        {
          SmartPtr<ITSSession>::operator=(&uBytes[1], 0);
          v16 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v27 + 80LL))(v27, &uBytes[1]);
          v9 = v16;
          if ( v16 == -2147024637 )
            break;
          if ( v16 < 0 )
          {
            _DbgPrintMessage(8, "Enum failed: 0x%x in %s", v16, "RpcGetEnumResultEx");
            v19 = v14;
            goto LABEL_44;
          }
          if ( (*(int (__fastcall **)(_QWORD, __int64))(**(_QWORD **)&uBytes[1] + 136LL))(*(_QWORD *)&uBytes[1], 1) >= 0 )
          {
            memset_0(v29, 0, 0x70u);
            v9 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**(_QWORD **)&uBytes[1] + 80LL))(
                   *(_QWORD *)&uBytes[1],
                   v29);
            v24 = 0;
            (*(void (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)&uBytes[1] + 88LL))(
              *(_QWORD *)&uBytes[1],
              &v24);
            *(_DWORD *)&v29[2] = PrivateToPublicState(v24);
            v36[0] = 0;
            Src = 0;
            uBytes[0] = 0;
            (*(void (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)&uBytes[1] + 104LL))(*(_QWORD *)&uBytes[1], v28);
            if ( v28[0] )
            {
              v9 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, void **, _DWORD *))(*(_QWORD *)v28[0] + 184LL))(
                     v28[0],
                     v36,
                     &Src,
                     uBytes);
              if ( v9 >= 0 )
              {
                v9 = StringCchCopyW(&v29[4], 0x21u, v36);
                if ( uBytes[0] )
                {
                  if ( v11 == 3 )
                  {
                    v17 = LocalAlloc(0x40u, uBytes[0]);
                    *((_QWORD *)&v34 + 1) = v17;
                    if ( v17 )
                    {
                      memcpy_0(v17, Src, uBytes[0]);
                      DWORD1(v34) = uBytes[0];
                    }
                  }
                  CoTaskMemFree(Src);
                }
              }
            }
            LODWORD(v33) = 1;
            v18 = 120LL * v15;
            *(_DWORD *)&v14[v18] = v11;
            switch ( v11 )
            {
              case 1:
                *(_OWORD *)&v14[v18 + 8] = *(_OWORD *)v29;
                *(_OWORD *)&v14[v18 + 24] = v30;
                *(_OWORD *)&v14[v18 + 40] = v31;
                *(_OWORD *)&v14[v18 + 56] = *(_OWORD *)v32.m256i_i8;
                *(_OWORD *)&v14[v18 + 68] = *(_OWORD *)((char *)&v32.m256i_u64[1] + 4);
                break;
              case 2:
                *(_OWORD *)&v14[v18 + 8] = *(_OWORD *)v29;
                *(_OWORD *)&v14[v18 + 24] = v30;
                *(_OWORD *)&v14[v18 + 40] = v31;
                *(__m256i *)&v14[v18 + 56] = v32;
                *(_OWORD *)&v14[v18 + 88] = v33;
                *(_DWORD *)&v14[v18 + 104] = v34;
                break;
              case 3:
                *(_OWORD *)&v14[v18 + 8] = *(_OWORD *)v29;
                *(_OWORD *)&v14[v18 + 24] = v30;
                *(_OWORD *)&v14[v18 + 40] = v31;
                *(__m256i *)&v14[v18 + 56] = v32;
                *(_OWORD *)&v14[v18 + 88] = v33;
                *(_OWORD *)&v14[v18 + 104] = v34;
                break;
            }
            SmartPtr<ITerminal>::operator=(v28, 0);
            ++v15;
          }
          else
          {
            v9 = 0;
          }
          if ( v15 >= (unsigned int)v12 )
            goto LABEL_42;
        }
        v9 = 0;
      }
LABEL_42:
      *a2 = v14;
      *a4 = v15;
      if ( v9 >= 0 )
        goto LABEL_7;
      v19 = v14;
      v26 = v14;
LABEL_44:
      if ( v11 == 3 )
      {
        for ( i = 0; i < v15; ++i )
        {
          v21 = *(void **)&v19[120 * i + 112];
          if ( v21 )
          {
            LocalFree(v21);
            v19 = v26;
          }
        }
      }
      LocalFree(v14);
    }
    else
    {
      v9 = -2147024882;
    }
  }
  else
  {
    _DbgPrintMessage(8, "Impersonate.ImpersonateRpcClient failed: 0x%x in %s", v10, "RpcGetEnumResultEx");
  }
LABEL_6:
  *a2 = 0;
  *a4 = 0;
LABEL_7:
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v35);
  CImpersonate::StopImpersonating((CImpersonate *)v22);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v27);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(v28);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&uBytes[1]);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180032be0  push    rbp
0x180032be2  push    rbx
0x180032be3  push    rsi
0x180032be4  push    rdi
0x180032be5  push    r12
0x180032be7  push    r13
0x180032be9  push    r14
0x180032beb  push    r15
0x180032bed  lea     rbp, [rsp-298h]
0x180032bf5  sub     rsp, 398h
0x180032bfc  mov     rax, cs:__security_cookie
0x180032c03  xor     rax, rsp
0x180032c06  mov     [rbp+2D0h+var_50], rax
0x180032c0d  mov     r15, r9
0x180032c10  mov     edi, r8d
0x180032c13  mov     r12, rdx
0x180032c16  mov     rbx, rcx
0x180032c19  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_EnumResultExSessionCountSync@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_EnumResultExSessionCountSync@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_EnumResultExSessionCountSync> `wil::Feature<__WilFeatureTraits_Feature_BugFix_EnumResultExSessionCountSync>::GetImpl(void)'::`2'::impl
0x180032c20  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_EnumResultExSessionCountSync@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_EnumResultExSessionCountSync>::__private_IsEnabled(void)
0x180032c25  xor     r14d, r14d
0x180032c28  test    al, al
0x180032c2a  jz      short loc_180032C42
0x180032c2c  mov     r9, r15
0x180032c2f  mov     r8d, edi
0x180032c32  mov     rdx, r12
0x180032c35  mov     rcx, rbx
0x180032c38  call    RpcGetEnumResultExImpl
0x180032c3d  jmp     loc_180032CE5
0x180032c42  mov     qword ptr [rsp+3D0h+uBytes+4], r14
0x180032c47  mov     [rsp+3D0h+var_370], r14
0x180032c4c  mov     [rsp+3D0h+var_378], r14
0x180032c51  mov     [rsp+3D0h+var_3A0], r14w
0x180032c57  mov     [rsp+3D0h+Src], r14
0x180032c5c  mov     dword ptr [rsp+3D0h+uBytes], r14d
0x180032c61  xor     edx, edx; Val
0x180032c63  lea     r8d, [rdx+70h]; Size
0x180032c67  lea     rcx, [rsp+3D0h+var_360]; void *
0x180032c6c  call    memset_0
0x180032c71  lea     rsi, aRpcgetenumresu_1; "RpcGetEnumResultEx"
0x180032c78  mov     r8, rsi; char *
0x180032c7b  xor     edx, edx; int
0x180032c7d  lea     rcx, [rbp+2D0h+var_2F0]; this
0x180032c81  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x180032c86  test    rbx, rbx
0x180032c89  jnz     short loc_180032D09
0x180032c8b  mov     r9, rsi
0x180032c8e  lea     r8, aHenum; "hEnum"
0x180032c95  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180032c9c  lea     ecx, [rbx+8]; int
0x180032c9f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180032ca4  mov     ebx, 80070057h
0x180032ca9  mov     [r12], r14
0x180032cad  mov     [r15], r14d
0x180032cb0  lea     rcx, [rbp+2D0h+var_2F0]; this
0x180032cb4  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x180032cb9  nop
0x180032cba  lea     rcx, [rsp+3D0h+var_3A0]; this
0x180032cbf  call    ?StopImpersonating@CImpersonate@@QEAAJXZ; CImpersonate::StopImpersonating(void)
0x180032cc4  nop
0x180032cc5  lea     rcx, [rsp+3D0h+var_378]
0x180032cca  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180032ccf  lea     rcx, [rsp+3D0h+var_370]
0x180032cd4  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180032cd9  lea     rcx, [rsp+3D0h+uBytes+4]
0x180032cde  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180032ce3  mov     eax, ebx
0x180032ce5  mov     rcx, [rbp+2D0h+var_50]
0x180032cec  xor     rcx, rsp; StackCookie
0x180032cef  call    __security_check_cookie
0x180032cf4  add     rsp, 398h
0x180032cfb  pop     r15
0x180032cfd  pop     r14
0x180032cff  pop     r13
0x180032d01  pop     r12
0x180032d03  pop     rdi
0x180032d04  pop     rsi
0x180032d05  pop     rbx
0x180032d06  pop     rbp
0x180032d07  retn
0x180032d09  mov     rdx, [rbx+638h]
0x180032d10  lea     rcx, [rsp+3D0h+var_378]
0x180032d15  call    ??4?$SmartPtr@VIWinlogonNotify@@@@QEAAAEAV0@PEAVIWinlogonNotify@@@Z; SmartPtr<IWinlogonNotify>::operator=(IWinlogonNotify *)
0x180032d1a  test    r12, r12
0x180032d1d  jz      short loc_180032CA4
0x180032d1f  test    r15, r15
0x180032d22  jz      short loc_180032CA4
0x180032d24  mov     [r12], r14
0x180032d28  mov     [r15], r14d
0x180032d2b  lea     rcx, [rsp+3D0h+var_3A0]; this
0x180032d30  call    ?ImpersonateRpcClient@CImpersonate@@QEAAJXZ; CImpersonate::ImpersonateRpcClient(void)
0x180032d35  mov     ebx, eax
0x180032d37  test    eax, eax
0x180032d39  jns     short loc_180032D57
0x180032d3b  mov     r9, rsi
0x180032d3e  mov     r8d, eax
0x180032d41  lea     rdx, aImpersonateImp_0; "Impersonate.ImpersonateRpcClient failed"...
0x180032d48  mov     ecx, 8; int
0x180032d4d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180032d52  jmp     loc_180032CA9
0x180032d57  mov     esi, 3
0x180032d5c  cmp     edi, esi
0x180032d5e  cmovbe  esi, edi
0x180032d61  mov     r13d, cs:?TotalSessions@CTSPerfProvider@@0JC; long volatile CTSPerfProvider::TotalSessions
0x180032d68  test    r13d, r13d
0x180032d6b  jnz     short loc_180032D75
0x180032d6d  mov     ebx, r14d
0x180032d70  jmp     loc_180032CB0
0x180032d75  imul    r14, r13, 78h ; 'x'
0x180032d79  mov     rdx, r14; uBytes
0x180032d7c  mov     ecx, 40h ; '@'; uFlags
0x180032d81  call    cs:__imp_LocalAlloc
0x180032d88  nop     dword ptr [rax+rax+00h]
0x180032d8d  mov     rdi, rax
0x180032d90  test    rax, rax
0x180032d93  jnz     short loc_180032DA2
0x180032d95  mov     ebx, 8007000Eh
0x180032d9a  xor     r14d, r14d
0x180032d9d  jmp     loc_180032CA9
0x180032da2  mov     [rsp+3D0h+var_380], rdi
0x180032da7  mov     r8, r14; Size
0x180032daa  xor     edx, edx; Val
0x180032dac  mov     rcx, rdi; void *
0x180032daf  call    memset_0
0x180032db4  mov     rcx, [rsp+3D0h+var_378]
0x180032db9  mov     rax, [rcx]
0x180032dbc  mov     rax, [rax+58h]
0x180032dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032dc5  xor     r14d, r14d
0x180032dc8  test    r13d, r13d
0x180032dcb  jz      loc_180033055
0x180032dd1  xor     edx, edx
0x180032dd3  lea     rcx, [rsp+3D0h+uBytes+4]
0x180032dd8  call    ??4?$SmartPtr@UITSSession@@@@QEAAAEAV0@PEAUITSSession@@@Z; SmartPtr<ITSSession>::operator=(ITSSession *)
0x180032ddd  mov     rcx, [rsp+3D0h+var_378]
0x180032de2  mov     rax, [rcx]
0x180032de5  lea     rdx, [rsp+3D0h+uBytes+4]
0x180032dea  mov     rax, [rax+50h]
0x180032dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032df3  mov     ebx, eax
0x180032df5  cmp     eax, 80070103h
0x180032dfa  jz      loc_180033053
0x180032e00  test    eax, eax
0x180032e02  js      loc_180033033
0x180032e08  mov     rcx, qword ptr [rsp+3D0h+uBytes+4]
0x180032e0d  mov     rax, [rcx]
0x180032e10  xor     r8d, r8d
0x180032e13  lea     edx, [r8+1]
0x180032e17  mov     rax, [rax+88h]
0x180032e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e23  test    eax, eax
0x180032e25  jns     short loc_180032E2E
0x180032e27  xor     ebx, ebx
0x180032e29  jmp     loc_180033028
0x180032e2e  xor     edx, edx; Val
0x180032e30  lea     r8d, [rdx+70h]; Size
0x180032e34  lea     rcx, [rsp+3D0h+var_360]; void *
0x180032e39  call    memset_0
0x180032e3e  mov     rcx, qword ptr [rsp+3D0h+uBytes+4]
0x180032e43  mov     rax, [rcx]
0x180032e46  lea     rdx, [rsp+3D0h+var_360]
0x180032e4b  mov     rax, [rax+50h]
0x180032e4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e54  mov     ebx, eax
0x180032e56  mov     [rsp+3D0h+var_390], 0
0x180032e5e  mov     rcx, qword ptr [rsp+3D0h+uBytes+4]
0x180032e63  mov     rax, [rcx]
0x180032e66  lea     rdx, [rsp+3D0h+var_390]
0x180032e6b  mov     rax, [rax+58h]
0x180032e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e74  mov     ecx, [rsp+3D0h+var_390]
0x180032e78  call    ?PrivateToPublicState@@YAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@@Z; PrivateToPublicState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001)
0x180032e7d  mov     dword ptr [rsp+3D0h+var_360+4], eax
0x180032e81  xor     eax, eax
0x180032e83  mov     [rbp+2D0h+var_A0], ax
0x180032e8a  mov     [rsp+3D0h+Src], rax
0x180032e8f  mov     dword ptr [rsp+3D0h+uBytes], eax
0x180032e93  mov     rcx, qword ptr [rsp+3D0h+uBytes+4]
0x180032e98  mov     rax, [rcx]
0x180032e9b  lea     rdx, [rsp+3D0h+var_370]
0x180032ea0  mov     rax, [rax+68h]
0x180032ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ea9  mov     rcx, [rsp+3D0h+var_370]
0x180032eae  test    rcx, rcx
0x180032eb1  jz      loc_180032F46
0x180032eb7  mov     rax, [rcx]
0x180032eba  lea     r9, [rsp+3D0h+uBytes]
0x180032ebf  lea     r8, [rsp+3D0h+Src]
0x180032ec4  lea     rdx, [rbp+2D0h+var_A0]
0x180032ecb  mov     rax, [rax+0B8h]
0x180032ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ed7  mov     ebx, eax
0x180032ed9  test    eax, eax
0x180032edb  js      short loc_180032F46
0x180032edd  lea     r8, [rbp+2D0h+var_A0]; unsigned __int16 *
0x180032ee4  mov     edx, 21h ; '!'; unsigned __int64
0x180032ee9  lea     rcx, [rsp+3D0h+var_360+8]; unsigned __int16 *
0x180032eee  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180032ef3  mov     ebx, eax
0x180032ef5  mov     eax, dword ptr [rsp+3D0h+uBytes]
0x180032ef9  test    eax, eax
0x180032efb  jz      short loc_180032F46
0x180032efd  cmp     esi, 3
0x180032f00  jnz     short loc_180032F35
0x180032f02  mov     edx, eax; uBytes
0x180032f04  lea     ecx, [rsi+3Dh]; uFlags
0x180032f07  call    cs:__imp_LocalAlloc
0x180032f0e  nop     dword ptr [rax+rax+00h]
0x180032f13  mov     qword ptr [rbp+2D0h+var_300+8], rax
0x180032f17  test    rax, rax
0x180032f1a  jz      short loc_180032F35
0x180032f1c  mov     r8d, dword ptr [rsp+3D0h+uBytes]; Size
0x180032f21  mov     rdx, [rsp+3D0h+Src]; Src
0x180032f26  mov     rcx, rax; void *
0x180032f29  call    memcpy_0
0x180032f2e  mov     eax, dword ptr [rsp+3D0h+uBytes]
0x180032f32  mov     dword ptr [rbp+2D0h+var_300+4], eax
0x180032f35  mov     rcx, [rsp+3D0h+Src]; pv
0x180032f3a  call    cs:__imp_CoTaskMemFree
0x180032f41  nop     dword ptr [rax+rax+00h]
0x180032f46  mov     dword ptr [rbp+2D0h+var_310], 1
0x180032f4d  mov     eax, r14d
0x180032f50  imul    rcx, rax, 78h ; 'x'
0x180032f54  mov     [rcx+rdi], esi
0x180032f57  cmp     esi, 1
0x180032f5a  jnz     short loc_180032F8F
0x180032f5c  movaps  xmm0, xmmword ptr [rsp+3D0h+var_360]
0x180032f61  movups  xmmword ptr [rcx+rdi+8], xmm0
0x180032f66  movaps  xmm1, [rbp+2D0h+var_350]
0x180032f6a  movups  xmmword ptr [rcx+rdi+18h], xmm1
0x180032f6f  movaps  xmm0, [rbp+2D0h+var_340]
0x180032f73  movups  xmmword ptr [rcx+rdi+28h], xmm0
0x180032f78  movaps  xmm1, [rbp+2D0h+var_330]
0x180032f7c  movups  xmmword ptr [rcx+rdi+38h], xmm1
0x180032f81  movups  xmm0, [rbp+2D0h+var_330+0Ch]
0x180032f85  movups  xmmword ptr [rcx+rdi+44h], xmm0
0x180032f8a  jmp     loc_180033019
0x180032f8f  cmp     esi, 2
0x180032f92  jnz     short loc_180032FD4
0x180032f94  movaps  xmm0, xmmword ptr [rsp+3D0h+var_360]
0x180032f99  movups  xmmword ptr [rcx+rdi+8], xmm0
0x180032f9e  movaps  xmm1, [rbp+2D0h+var_350]
0x180032fa2  movups  xmmword ptr [rcx+rdi+18h], xmm1
0x180032fa7  movaps  xmm0, [rbp+2D0h+var_340]
0x180032fab  movups  xmmword ptr [rcx+rdi+28h], xmm0
0x180032fb0  movaps  xmm1, [rbp+2D0h+var_330]
0x180032fb4  movups  xmmword ptr [rcx+rdi+38h], xmm1
0x180032fb9  movaps  xmm0, [rbp+2D0h+var_320]
0x180032fbd  movups  xmmword ptr [rcx+rdi+48h], xmm0
0x180032fc2  movaps  xmm1, [rbp+2D0h+var_310]
0x180032fc6  movups  xmmword ptr [rcx+rdi+58h], xmm1
0x180032fcb  mov     eax, dword ptr [rbp+2D0h+var_300]
0x180032fce  mov     [rcx+rdi+68h], eax
0x180032fd2  jmp     short loc_180033019
0x180032fd4  cmp     esi, 3
0x180032fd7  jnz     short loc_180033019
0x180032fd9  movaps  xmm0, xmmword ptr [rsp+3D0h+var_360]
0x180032fde  movups  xmmword ptr [rcx+rdi+8], xmm0
0x180032fe3  movaps  xmm1, [rbp+2D0h+var_350]
0x180032fe7  movups  xmmword ptr [rcx+rdi+18h], xmm1
0x180032fec  movaps  xmm0, [rbp+2D0h+var_340]
0x180032ff0  movups  xmmword ptr [rcx+rdi+28h], xmm0
0x180032ff5  movaps  xmm1, [rbp+2D0h+var_330]
0x180032ff9  movups  xmmword ptr [rcx+rdi+38h], xmm1
0x180032ffe  movaps  xmm0, [rbp+2D0h+var_320]
0x180033002  movups  xmmword ptr [rcx+rdi+48h], xmm0
0x180033007  movaps  xmm1, [rbp+2D0h+var_310]
0x18003300b  movups  xmmword ptr [rcx+rdi+58h], xmm1
0x180033010  movaps  xmm0, [rbp+2D0h+var_300]
0x180033014  movups  xmmword ptr [rcx+rdi+68h], xmm0
0x180033019  xor     edx, edx
0x18003301b  lea     rcx, [rsp+3D0h+var_370]
0x180033020  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x180033025  inc     r14d
0x180033028  cmp     r14d, r13d
0x18003302b  jb      loc_180032DD1
0x180033031  jmp     short loc_180033055
0x180033033  lea     r9, aRpcgetenumresu_1; "RpcGetEnumResultEx"
0x18003303a  mov     r8d, eax
0x18003303d  lea     rdx, aEnumFailed0xXI; "Enum failed: 0x%x in %s"
0x180033044  mov     ecx, 8; int
0x180033049  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003304e  mov     rdx, rdi
0x180033051  jmp     short loc_18003306C
0x180033053  xor     ebx, ebx
0x180033055  mov     [r12], rdi
0x180033059  mov     [r15], r14d
0x18003305c  test    ebx, ebx
0x18003305e  jns     loc_180032CB0
0x180033064  mov     rdx, rdi
0x180033067  mov     [rsp+3D0h+var_380], rdx
0x18003306c  cmp     esi, 3
0x18003306f  jnz     short loc_1800330A0
0x180033071  xor     esi, esi
0x180033073  test    r14d, r14d
0x180033076  jz      short loc_1800330A0
0x180033078  mov     eax, esi
0x18003307a  imul    rcx, rax, 78h ; 'x'
0x18003307e  mov     rcx, [rcx+rdx+70h]; hMem
0x180033083  test    rcx, rcx
0x180033086  jz      short loc_180033099
  ... truncated ...
```
