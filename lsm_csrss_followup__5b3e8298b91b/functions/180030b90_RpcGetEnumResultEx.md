# RpcGetEnumResultEx

- ea: `0x180030b90`
- end: `0x180031045`
- name: `RpcGetEnumResultEx`
- size: `1205`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x1800074c0`
- `0x180008f64`
- `0x18000f260`
- `0x180014c00`
- `0x180014f40`
- `0x180017e00`
- `0x18001aa50`
- `0x18001ee40`
- `0x18001fd20`
- `0x18001fd70`
- `0x180021bc4`
- `0x180030b90`
- `0x18004b460`
- `0x18004bf44`
- `0x18005b080`
- `0x18005b4dc`
- `0x18009404c`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030d30`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030eb0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030d30`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030eb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031025`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003103a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031025`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003103a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030edd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030edd`

## string_xrefs

- `0x180030cf0`: `Impersonate.ImpersonateRpcClient failed: 0x%x in %s`

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
0x180030b90  push    rbp
0x180030b92  push    rbx
0x180030b93  push    rsi
0x180030b94  push    rdi
0x180030b95  push    r12
0x180030b97  push    r13
0x180030b99  push    r14
0x180030b9b  push    r15
0x180030b9d  lea     rbp, [rsp-298h]
0x180030ba5  sub     rsp, 398h
0x180030bac  mov     rax, cs:__security_cookie
0x180030bb3  xor     rax, rsp
0x180030bb6  mov     [rbp+2D0h+var_50], rax
0x180030bbd  mov     r15, r9
0x180030bc0  mov     edi, r8d
0x180030bc3  mov     r12, rdx
0x180030bc6  mov     rbx, rcx
0x180030bc9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_EnumResultExSessionCountSync@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_EnumResultExSessionCountSync@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_EnumResultExSessionCountSync> `wil::Feature<__WilFeatureTraits_Feature_BugFix_EnumResultExSessionCountSync>::GetImpl(void)'::`2'::impl
0x180030bd0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_EnumResultExSessionCountSync@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_EnumResultExSessionCountSync>::__private_IsEnabled(void)
0x180030bd5  xor     r14d, r14d
0x180030bd8  test    al, al
0x180030bda  jz      short loc_180030BF2
0x180030bdc  mov     r9, r15
0x180030bdf  mov     r8d, edi
0x180030be2  mov     rdx, r12
0x180030be5  mov     rcx, rbx
0x180030be8  call    RpcGetEnumResultExImpl
0x180030bed  jmp     loc_180030C95
0x180030bf2  mov     qword ptr [rsp+3D0h+uBytes+4], r14
0x180030bf7  mov     [rsp+3D0h+var_370], r14
0x180030bfc  mov     [rsp+3D0h+var_378], r14
0x180030c01  mov     [rsp+3D0h+var_3A0], r14w
0x180030c07  mov     [rsp+3D0h+Src], r14
0x180030c0c  mov     dword ptr [rsp+3D0h+uBytes], r14d
0x180030c11  xor     edx, edx; Val
0x180030c13  lea     r8d, [rdx+70h]; Size
0x180030c17  lea     rcx, [rsp+3D0h+var_360]; void *
0x180030c1c  call    memset_0
0x180030c21  lea     rsi, aRpcgetenumresu_1; "RpcGetEnumResultEx"
0x180030c28  mov     r8, rsi; char *
0x180030c2b  xor     edx, edx; int
0x180030c2d  lea     rcx, [rbp+2D0h+var_2F0]; this
0x180030c31  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x180030c36  test    rbx, rbx
0x180030c39  jnz     short loc_180030CB8
0x180030c3b  mov     r9, rsi
0x180030c3e  lea     r8, aHenum; "hEnum"
0x180030c45  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180030c4c  lea     ecx, [rbx+8]; int
0x180030c4f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180030c54  mov     ebx, 80070057h
0x180030c59  mov     [r12], r14
0x180030c5d  mov     [r15], r14d
0x180030c60  lea     rcx, [rbp+2D0h+var_2F0]; this
0x180030c64  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x180030c69  nop
0x180030c6a  lea     rcx, [rsp+3D0h+var_3A0]; this
0x180030c6f  call    ?StopImpersonating@CImpersonate@@QEAAJXZ; CImpersonate::StopImpersonating(void)
0x180030c74  nop
0x180030c75  lea     rcx, [rsp+3D0h+var_378]
0x180030c7a  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180030c7f  lea     rcx, [rsp+3D0h+var_370]
0x180030c84  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180030c89  lea     rcx, [rsp+3D0h+uBytes+4]
0x180030c8e  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180030c93  mov     eax, ebx
0x180030c95  mov     rcx, [rbp+2D0h+var_50]
0x180030c9c  xor     rcx, rsp; StackCookie
0x180030c9f  call    __security_check_cookie
0x180030ca4  add     rsp, 398h
0x180030cab  pop     r15
0x180030cad  pop     r14
0x180030caf  pop     r13
0x180030cb1  pop     r12
0x180030cb3  pop     rdi
0x180030cb4  pop     rsi
0x180030cb5  pop     rbx
0x180030cb6  pop     rbp
0x180030cb7  retn
0x180030cb8  mov     rdx, [rbx+638h]
0x180030cbf  lea     rcx, [rsp+3D0h+var_378]
0x180030cc4  call    ??4?$SmartPtr@VIWinlogonNotify@@@@QEAAAEAV0@PEAVIWinlogonNotify@@@Z; SmartPtr<IWinlogonNotify>::operator=(IWinlogonNotify *)
0x180030cc9  test    r12, r12
0x180030ccc  jz      short loc_180030C54
0x180030cce  test    r15, r15
0x180030cd1  jz      short loc_180030C54
0x180030cd3  mov     [r12], r14
0x180030cd7  mov     [r15], r14d
0x180030cda  lea     rcx, [rsp+3D0h+var_3A0]; this
0x180030cdf  call    ?ImpersonateRpcClient@CImpersonate@@QEAAJXZ; CImpersonate::ImpersonateRpcClient(void)
0x180030ce4  mov     ebx, eax
0x180030ce6  test    eax, eax
0x180030ce8  jns     short loc_180030D06
0x180030cea  mov     r9, rsi
0x180030ced  mov     r8d, eax
0x180030cf0  lea     rdx, aImpersonateImp_0; "Impersonate.ImpersonateRpcClient failed"...
0x180030cf7  mov     ecx, 8; int
0x180030cfc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180030d01  jmp     loc_180030C59
0x180030d06  mov     esi, 3
0x180030d0b  cmp     edi, esi
0x180030d0d  cmovbe  esi, edi
0x180030d10  mov     r13d, cs:?TotalSessions@CTSPerfProvider@@0JC; long volatile CTSPerfProvider::TotalSessions
0x180030d17  test    r13d, r13d
0x180030d1a  jnz     short loc_180030D24
0x180030d1c  mov     ebx, r14d
0x180030d1f  jmp     loc_180030C60
0x180030d24  imul    r14, r13, 78h ; 'x'
0x180030d28  mov     rdx, r14; uBytes
0x180030d2b  mov     ecx, 40h ; '@'; uFlags
0x180030d30  call    cs:__imp_LocalAlloc
0x180030d36  mov     rdi, rax
0x180030d39  test    rax, rax
0x180030d3c  jnz     short loc_180030D4B
0x180030d3e  mov     ebx, 8007000Eh
0x180030d43  xor     r14d, r14d
0x180030d46  jmp     loc_180030C59
0x180030d4b  mov     [rsp+3D0h+var_380], rdi
0x180030d50  mov     r8, r14; Size
0x180030d53  xor     edx, edx; Val
0x180030d55  mov     rcx, rdi; void *
0x180030d58  call    memset_0
0x180030d5d  mov     rcx, [rsp+3D0h+var_378]
0x180030d62  mov     rax, [rcx]
0x180030d65  mov     rax, [rax+58h]
0x180030d69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d6e  xor     r14d, r14d
0x180030d71  test    r13d, r13d
0x180030d74  jz      loc_180030FF2
0x180030d7a  xor     edx, edx
0x180030d7c  lea     rcx, [rsp+3D0h+uBytes+4]
0x180030d81  call    ??4?$SmartPtr@UITSSession@@@@QEAAAEAV0@PEAUITSSession@@@Z; SmartPtr<ITSSession>::operator=(ITSSession *)
0x180030d86  mov     rcx, [rsp+3D0h+var_378]
0x180030d8b  mov     rax, [rcx]
0x180030d8e  lea     rdx, [rsp+3D0h+uBytes+4]
0x180030d93  mov     rax, [rax+50h]
0x180030d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d9c  mov     ebx, eax
0x180030d9e  cmp     eax, 80070103h
0x180030da3  jz      loc_180030FF0
0x180030da9  test    eax, eax
0x180030dab  js      loc_180030FD0
0x180030db1  mov     rcx, qword ptr [rsp+3D0h+uBytes+4]
0x180030db6  mov     rax, [rcx]
0x180030db9  xor     r8d, r8d
0x180030dbc  lea     edx, [r8+1]
0x180030dc0  mov     rax, [rax+88h]
0x180030dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030dcc  test    eax, eax
0x180030dce  jns     short loc_180030DD7
0x180030dd0  xor     ebx, ebx
0x180030dd2  jmp     loc_180030FC5
0x180030dd7  xor     edx, edx; Val
0x180030dd9  lea     r8d, [rdx+70h]; Size
0x180030ddd  lea     rcx, [rsp+3D0h+var_360]; void *
0x180030de2  call    memset_0
0x180030de7  mov     rcx, qword ptr [rsp+3D0h+uBytes+4]
0x180030dec  mov     rax, [rcx]
0x180030def  lea     rdx, [rsp+3D0h+var_360]
0x180030df4  mov     rax, [rax+50h]
0x180030df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030dfd  mov     ebx, eax
0x180030dff  mov     [rsp+3D0h+var_390], 0
0x180030e07  mov     rcx, qword ptr [rsp+3D0h+uBytes+4]
0x180030e0c  mov     rax, [rcx]
0x180030e0f  lea     rdx, [rsp+3D0h+var_390]
0x180030e14  mov     rax, [rax+58h]
0x180030e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e1d  mov     ecx, [rsp+3D0h+var_390]
0x180030e21  call    ?PrivateToPublicState@@YAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@@Z; PrivateToPublicState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001)
0x180030e26  mov     dword ptr [rsp+3D0h+var_360+4], eax
0x180030e2a  xor     eax, eax
0x180030e2c  mov     [rbp+2D0h+var_A0], ax
0x180030e33  mov     [rsp+3D0h+Src], rax
0x180030e38  mov     dword ptr [rsp+3D0h+uBytes], eax
0x180030e3c  mov     rcx, qword ptr [rsp+3D0h+uBytes+4]
0x180030e41  mov     rax, [rcx]
0x180030e44  lea     rdx, [rsp+3D0h+var_370]
0x180030e49  mov     rax, [rax+68h]
0x180030e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e52  mov     rcx, [rsp+3D0h+var_370]
0x180030e57  test    rcx, rcx
0x180030e5a  jz      loc_180030EE3
0x180030e60  mov     rax, [rcx]
0x180030e63  lea     r9, [rsp+3D0h+uBytes]
0x180030e68  lea     r8, [rsp+3D0h+Src]
0x180030e6d  lea     rdx, [rbp+2D0h+var_A0]
0x180030e74  mov     rax, [rax+0B8h]
0x180030e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e80  mov     ebx, eax
0x180030e82  test    eax, eax
0x180030e84  js      short loc_180030EE3
0x180030e86  lea     r8, [rbp+2D0h+var_A0]; unsigned __int16 *
0x180030e8d  mov     edx, 21h ; '!'; unsigned __int64
0x180030e92  lea     rcx, [rsp+3D0h+var_360+8]; unsigned __int16 *
0x180030e97  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180030e9c  mov     ebx, eax
0x180030e9e  mov     eax, dword ptr [rsp+3D0h+uBytes]
0x180030ea2  test    eax, eax
0x180030ea4  jz      short loc_180030EE3
0x180030ea6  cmp     esi, 3
0x180030ea9  jnz     short loc_180030ED8
0x180030eab  mov     edx, eax; uBytes
0x180030ead  lea     ecx, [rsi+3Dh]; uFlags
0x180030eb0  call    cs:__imp_LocalAlloc
0x180030eb6  mov     qword ptr [rbp+2D0h+var_300+8], rax
0x180030eba  test    rax, rax
0x180030ebd  jz      short loc_180030ED8
0x180030ebf  mov     r8d, dword ptr [rsp+3D0h+uBytes]; Size
0x180030ec4  mov     rdx, [rsp+3D0h+Src]; Src
0x180030ec9  mov     rcx, rax; void *
0x180030ecc  call    memcpy_0
0x180030ed1  mov     eax, dword ptr [rsp+3D0h+uBytes]
0x180030ed5  mov     dword ptr [rbp+2D0h+var_300+4], eax
0x180030ed8  mov     rcx, [rsp+3D0h+Src]; pv
0x180030edd  call    cs:__imp_CoTaskMemFree
0x180030ee3  mov     dword ptr [rbp+2D0h+var_310], 1
0x180030eea  mov     eax, r14d
0x180030eed  imul    rcx, rax, 78h ; 'x'
0x180030ef1  mov     [rcx+rdi], esi
0x180030ef4  cmp     esi, 1
0x180030ef7  jnz     short loc_180030F2C
0x180030ef9  movaps  xmm0, xmmword ptr [rsp+3D0h+var_360]
0x180030efe  movups  xmmword ptr [rcx+rdi+8], xmm0
0x180030f03  movaps  xmm1, [rbp+2D0h+var_350]
0x180030f07  movups  xmmword ptr [rcx+rdi+18h], xmm1
0x180030f0c  movaps  xmm0, [rbp+2D0h+var_340]
0x180030f10  movups  xmmword ptr [rcx+rdi+28h], xmm0
0x180030f15  movaps  xmm1, [rbp+2D0h+var_330]
0x180030f19  movups  xmmword ptr [rcx+rdi+38h], xmm1
0x180030f1e  movups  xmm0, [rbp+2D0h+var_330+0Ch]
0x180030f22  movups  xmmword ptr [rcx+rdi+44h], xmm0
0x180030f27  jmp     loc_180030FB6
0x180030f2c  cmp     esi, 2
0x180030f2f  jnz     short loc_180030F71
0x180030f31  movaps  xmm0, xmmword ptr [rsp+3D0h+var_360]
0x180030f36  movups  xmmword ptr [rcx+rdi+8], xmm0
0x180030f3b  movaps  xmm1, [rbp+2D0h+var_350]
0x180030f3f  movups  xmmword ptr [rcx+rdi+18h], xmm1
0x180030f44  movaps  xmm0, [rbp+2D0h+var_340]
0x180030f48  movups  xmmword ptr [rcx+rdi+28h], xmm0
0x180030f4d  movaps  xmm1, [rbp+2D0h+var_330]
0x180030f51  movups  xmmword ptr [rcx+rdi+38h], xmm1
0x180030f56  movaps  xmm0, [rbp+2D0h+var_320]
0x180030f5a  movups  xmmword ptr [rcx+rdi+48h], xmm0
0x180030f5f  movaps  xmm1, [rbp+2D0h+var_310]
0x180030f63  movups  xmmword ptr [rcx+rdi+58h], xmm1
0x180030f68  mov     eax, dword ptr [rbp+2D0h+var_300]
0x180030f6b  mov     [rcx+rdi+68h], eax
0x180030f6f  jmp     short loc_180030FB6
0x180030f71  cmp     esi, 3
0x180030f74  jnz     short loc_180030FB6
0x180030f76  movaps  xmm0, xmmword ptr [rsp+3D0h+var_360]
0x180030f7b  movups  xmmword ptr [rcx+rdi+8], xmm0
0x180030f80  movaps  xmm1, [rbp+2D0h+var_350]
0x180030f84  movups  xmmword ptr [rcx+rdi+18h], xmm1
0x180030f89  movaps  xmm0, [rbp+2D0h+var_340]
0x180030f8d  movups  xmmword ptr [rcx+rdi+28h], xmm0
0x180030f92  movaps  xmm1, [rbp+2D0h+var_330]
0x180030f96  movups  xmmword ptr [rcx+rdi+38h], xmm1
0x180030f9b  movaps  xmm0, [rbp+2D0h+var_320]
0x180030f9f  movups  xmmword ptr [rcx+rdi+48h], xmm0
0x180030fa4  movaps  xmm1, [rbp+2D0h+var_310]
0x180030fa8  movups  xmmword ptr [rcx+rdi+58h], xmm1
0x180030fad  movaps  xmm0, [rbp+2D0h+var_300]
0x180030fb1  movups  xmmword ptr [rcx+rdi+68h], xmm0
0x180030fb6  xor     edx, edx
0x180030fb8  lea     rcx, [rsp+3D0h+var_370]
0x180030fbd  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x180030fc2  inc     r14d
0x180030fc5  cmp     r14d, r13d
0x180030fc8  jb      loc_180030D7A
0x180030fce  jmp     short loc_180030FF2
0x180030fd0  lea     r9, aRpcgetenumresu_1; "RpcGetEnumResultEx"
0x180030fd7  mov     r8d, eax
0x180030fda  lea     rdx, aEnumFailed0xXI; "Enum failed: 0x%x in %s"
0x180030fe1  mov     ecx, 8; int
0x180030fe6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180030feb  mov     rdx, rdi
0x180030fee  jmp     short loc_180031009
0x180030ff0  xor     ebx, ebx
0x180030ff2  mov     [r12], rdi
0x180030ff6  mov     [r15], r14d
0x180030ff9  test    ebx, ebx
0x180030ffb  jns     loc_180030C60
0x180031001  mov     rdx, rdi
0x180031004  mov     [rsp+3D0h+var_380], rdx
0x180031009  cmp     esi, 3
0x18003100c  jnz     short loc_180031037
0x18003100e  xor     esi, esi
0x180031010  test    r14d, r14d
0x180031013  jz      short loc_180031037
0x180031015  mov     eax, esi
0x180031017  imul    rcx, rax, 78h ; 'x'
0x18003101b  mov     rcx, [rcx+rdx+70h]; hMem
0x180031020  test    rcx, rcx
0x180031023  jz      short loc_180031030
0x180031025  call    cs:__imp_LocalFree
0x18003102b  mov     rdx, [rsp+3D0h+var_380]
0x180031030  inc     esi
  ... truncated ...
```
