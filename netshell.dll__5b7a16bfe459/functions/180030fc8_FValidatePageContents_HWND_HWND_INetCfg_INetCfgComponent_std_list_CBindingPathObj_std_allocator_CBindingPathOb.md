# FValidatePageContents(HWND__ *,HWND__ *,INetCfg *,INetCfgComponent *,std::list<CBindingPathObj *,std::allocator<CBindingPathObj *>> *)

- ea: `0x180030fc8`
- end: `0x180031334`
- name: `?FValidatePageContents@@YAHPEAUHWND__@@0PEAUINetCfg@@PEAUINetCfgComponent@@PEAV?$list@PEAVCBindingPathObj@@V?$allocator@PEAVCBindingPathObj@@@std@@@std@@@Z`
- size: `876`
- prototype: `__int64 __usercall@<rax>(HWND hWnd@<rcx>, HWND@<rdx>, struct INetCfg *@<r8>, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002f490`

## callees

- `0x180017674`
- `0x180017b50`
- `0x180018d74`
- `0x18001bc10`
- `0x18001c34c`
- `0x18001e1e0`
- `0x18001eb7c`
- `0x18002b5e8`
- `0x18002b82c`
- `0x18002bbf0`
- `0x18002c468`
- `0x180030d04`
- `0x180030fc8`
- `0x18003191c`
- `0x18003215c`
- `0x180032ab0`
- `0x180065010`

## import_xrefs

- `USER32!SendMessageW` at `0x180031148`
- `USER32!SendMessageW` at `0x180031190`
- `USER32!SendMessageW` at `0x1800312ae`
- `USER32!SendMessageW` at `0x180031148`
- `USER32!SendMessageW` at `0x180031190`
- `USER32!SendMessageW` at `0x1800312ae`
- `NetSetupApi!NetSetupInitialize` at `0x1800310d8`
- `NetSetupApi!NetSetupInitialize` at `0x1800310d8`
- `ole32!CoTaskMemFree` at `0x18003122d`
- `ole32!CoTaskMemFree` at `0x18003122d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FValidatePageContents(HWND hWnd, HWND a2, struct INetCfg *a3, __int64 a4)
{
  BOOL v7; // ebx
  unsigned int v8; // edi
  struct IUnknown *v9; // rsi
  int Adapter; // ebx
  int v11; // esi
  int i; // ebx
  _DWORD *v13; // rcx
  const unsigned __int16 *Ids; // rax
  __int64 v15; // r8
  __int64 v16; // r8
  _QWORD *v17; // rax
  int j; // ebx
  __int64 v19; // rcx
  LPVOID pv[2]; // [rsp+30h] [rbp-D0h] BYREF
  void **v22; // [rsp+40h] [rbp-C0h] BYREF
  void **v23; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  char v25; // [rsp+58h] [rbp-A8h]
  int lParam; // [rsp+60h] [rbp-A0h] BYREF
  int lParam_4; // [rsp+64h] [rbp-9Ch]
  int v28; // [rsp+68h] [rbp-98h]
  __int64 v29; // [rsp+88h] [rbp-78h]
  struct IUnknown *v30[5]; // [rsp+C0h] [rbp-40h] BYREF
  struct _GUID v31; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD Src[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v33; // [rsp+108h] [rbp+8h]
  unsigned __int64 v34; // [rsp+110h] [rbp+10h]

  pv[1] = a3;
  v7 = 0;
  CIterNetCfgComponent::CIterNetCfgComponent((CIterNetCfgComponent *)v30, a3, &GUID_DEVCLASS_NETTRANS);
  *(_QWORD *)&v31.Data1 = 0;
  v8 = 1;
  while ( !v7 )
  {
    if ( (unsigned int)CIEnumIter<IEnumNetCfgComponent,INetCfgComponent *>::HrNext(v30, &v31) )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)a4 + 64LL))(a4, &v31);
      v22 = &CNetSetupHelper::`vftable'{for `INetSetupHandle'};
      v23 = &CNetSetupHelper::`vftable'{for `INetSetupHelper'};
      v24 = 0;
      v25 = 0;
      NetSetupInitialize(0, &v24);
      Adapter = CNetSetupHelper::FindAdapter((CNetSetupHelper *)&v23, &v31, 0);
      CNetSetupHelper::~CNetSetupHelper((CNetSetupHelper *)&v22);
      if ( Adapter && (unsigned int)NcMsgBox(hInst, hWnd, 0x3EA5u, 0x3EA6u, 0x44u) == 6 )
        goto LABEL_37;
      break;
    }
    pv[0] = 0;
    v9 = *(struct IUnknown **)&v31.Data1;
    if ( !(***(__int64 (__fastcall ****)(_QWORD, GUID *, LPVOID *))&v31.Data1)(
            *(_QWORD *)&v31.Data1,
            &IID_INetCfgComponentBindings,
            pv) )
    {
      v7 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)pv[0] + 56LL))(pv[0], a4) == 0;
      ReleaseObj((struct IUnknown *)pv[0]);
    }
    ReleaseObj(v9);
  }
  std::wstring::wstring(Src, &c_szEmpty);
  v11 = SendMessageW(a2, 0x1004u, 0, 0);
  memset_0(&lParam, 0, 0x58u);
  for ( i = 0; i < v11; ++i )
  {
    lParam_4 = i;
    v28 = 0;
    lParam = 4;
    if ( (unsigned int)SendMessageW(a2, 0x104Bu, 0, (LPARAM)&lParam) )
    {
      if ( v29 )
      {
        v13 = *(_DWORD **)(v29 + 8);
        if ( v13 )
        {
          if ( v13[6] == 2 )
          {
            pv[0] = 0;
            if ( (*(int (__fastcall **)(_QWORD, LPVOID *))(**(_QWORD **)v13 + 24LL))(*(_QWORD *)v13, pv) >= 0 )
            {
              if ( v33 )
              {
                Ids = SzLoadIds(0x3EABu);
                v15 = -1;
                do
                  ++v15;
                while ( Ids[v15] );
                std::wstring::_Append<unsigned short>(Src);
              }
              v16 = -1;
              do
                ++v16;
              while ( *((_WORD *)pv[0] + v16) );
              std::wstring::_Append<unsigned short>(Src);
              CoTaskMemFree(pv[0]);
            }
          }
        }
      }
    }
  }
  if ( !v33 )
    goto LABEL_35;
  v17 = Src;
  if ( v34 > 7 )
    v17 = (_QWORD *)Src[0];
  if ( (unsigned int)NcMsgBox(hInst, hWnd, 0x3E88u, 0x3EA7u, 0x44u, v17) == 7 )
  {
    for ( j = 0; j < v11; ++j )
    {
      lParam_4 = j;
      v28 = 0;
      lParam = 4;
      if ( (unsigned int)SendMessageW(a2, 0x104Bu, 0, (LPARAM)&lParam) )
      {
        if ( v29 )
        {
          v19 = *(_QWORD *)(v29 + 8);
          if ( v19 )
          {
            if ( *(_DWORD *)(v19 + 32) )
              HrToggleLVItemState(a2);
          }
        }
      }
    }
    HrRefreshAll(a2);
  }
  else
  {
LABEL_35:
    v8 = 0;
  }
  std::wstring::_Tidy_deallocate((__int64)Src);
LABEL_37:
  CIterNetCfgUpperBindingPath::~CIterNetCfgUpperBindingPath(v30);
  return v8;
}

```

## disassembly

```asm
0x180030fc8  push    rbp
0x180030fca  push    rbx
0x180030fcb  push    rsi
0x180030fcc  push    rdi
0x180030fcd  push    r12
0x180030fcf  push    r13
0x180030fd1  push    r14
0x180030fd3  push    r15
0x180030fd5  lea     rbp, [rsp-28h]
0x180030fda  sub     rsp, 128h
0x180030fe1  mov     rax, cs:__security_cookie
0x180030fe8  xor     rax, rsp
0x180030feb  mov     [rbp+60h+var_48], rax
0x180030fef  mov     r15, r9
0x180030ff2  mov     rax, r8
0x180030ff5  mov     [rsp+160h+var_128], rax
0x180030ffa  mov     r14, rdx
0x180030ffd  mov     r12, rcx
0x180031000  mov     r13, [rbp+60h+arg_20]
0x180031007  xor     esi, esi
0x180031009  mov     ebx, esi
0x18003100b  lea     r8, GUID_DEVCLASS_NETTRANS; struct _GUID *
0x180031012  mov     rdx, rax; struct INetCfg *
0x180031015  lea     rcx, [rbp+60h+var_A0]; this
0x180031019  call    ??0CIterNetCfgComponent@@QEAA@PEAUINetCfg@@PEBU_GUID@@@Z; CIterNetCfgComponent::CIterNetCfgComponent(INetCfg *,_GUID const *)
0x18003101e  nop
0x18003101f  mov     qword ptr [rbp+60h+var_78.Data1], rsi
0x180031023  lea     edi, [rsi+1]
0x180031026  test    ebx, ebx
0x180031028  jnz     loc_180031129
0x18003102e  lea     rdx, [rbp+60h+var_78]
0x180031032  lea     rcx, [rbp+60h+var_A0]
0x180031036  call    ?HrNext@?$CIEnumIter@UIEnumNetCfgComponent@@PEAUINetCfgComponent@@@@QEAAJPEAPEAUINetCfgComponent@@@Z; CIEnumIter<IEnumNetCfgComponent,INetCfgComponent *>::HrNext(INetCfgComponent * *)
0x18003103b  test    eax, eax
0x18003103d  jnz     short loc_180031095
0x18003103f  mov     [rsp+160h+pv], rsi
0x180031044  mov     rsi, qword ptr [rbp+60h+var_78.Data1]
0x180031048  mov     rax, [rsi]
0x18003104b  lea     r8, [rsp+160h+pv]
0x180031050  lea     rdx, IID_INetCfgComponentBindings
0x180031057  mov     rcx, rsi
0x18003105a  mov     rax, [rax]
0x18003105d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031062  test    eax, eax
0x180031064  jnz     short loc_180031089
0x180031066  mov     rcx, [rsp+160h+pv]
0x18003106b  mov     rax, [rcx]
0x18003106e  mov     rdx, r15
0x180031071  mov     rax, [rax+38h]
0x180031075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003107a  test    eax, eax
0x18003107c  cmovz   ebx, edi
0x18003107f  mov     rcx, [rsp+160h+pv]; struct IUnknown *
0x180031084  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180031089  mov     rcx, rsi; struct IUnknown *
0x18003108c  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180031091  xor     esi, esi
0x180031093  jmp     short loc_180031026
0x180031095  xorps   xmm0, xmm0
0x180031098  movups  xmmword ptr [rbp+60h+var_78.Data1], xmm0
0x18003109c  mov     rax, [r15]
0x18003109f  lea     rdx, [rbp+60h+var_78]
0x1800310a3  mov     rcx, r15
0x1800310a6  mov     rax, [rax+40h]
0x1800310aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800310af  lea     rax, ??_7CNetSetupHelper@@6BINetSetupHandle@@@; const CNetSetupHelper::`vftable'{for `INetSetupHandle'}
0x1800310b6  mov     [rsp+160h+var_120], rax
0x1800310bb  lea     rax, ??_7CNetSetupHelper@@6BINetSetupHelper@@@; const CNetSetupHelper::`vftable'{for `INetSetupHelper'}
0x1800310c2  mov     [rsp+160h+var_118], rax
0x1800310c7  mov     [rsp+160h+var_110], rsi
0x1800310cc  mov     [rsp+160h+var_108], sil
0x1800310d1  lea     rdx, [rsp+160h+var_110]
0x1800310d6  xor     ecx, ecx
0x1800310d8  call    cs:__imp_NetSetupInitialize
0x1800310de  xor     r8d, r8d; struct INetCfgComponent **
0x1800310e1  lea     rdx, [rbp+60h+var_78]; struct _GUID *
0x1800310e5  lea     rcx, [rsp+160h+var_118]; this
0x1800310ea  call    ?FindAdapter@CNetSetupHelper@@UEAAJAEBU_GUID@@PEAPEAUINetCfgComponent@@@Z; CNetSetupHelper::FindAdapter(_GUID const &,INetCfgComponent * *)
0x1800310ef  mov     ebx, eax
0x1800310f1  lea     rcx, [rsp+160h+var_120]; this
0x1800310f6  call    ??1CNetSetupHelper@@AEAA@XZ; CNetSetupHelper::~CNetSetupHelper(void)
0x1800310fb  test    ebx, ebx
0x1800310fd  jz      short loc_180031129
0x1800310ff  mov     [rsp+160h+uType], 44h ; 'D'; uType
0x180031107  mov     r9d, 3EA6h; unsigned int
0x18003110d  lea     r8d, [r9-1]; unsigned int
0x180031111  mov     rdx, r12; hWnd
0x180031114  mov     rcx, cs:hInst; hModule
0x18003111b  call    ?NcMsgBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@IIIZZ; NcMsgBox(HINSTANCE__ *,HWND__ *,uint,uint,uint,...)
0x180031120  cmp     eax, 6
0x180031123  jz      loc_180031309
0x180031129  lea     rdx, ?c_szEmpty@@3QBGB; ushort const near * const c_szEmpty
0x180031130  lea     rcx, [rbp+60h+Src]
0x180031134  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180031139  nop
0x18003113a  xor     r9d, r9d; lParam
0x18003113d  xor     r8d, r8d; wParam
0x180031140  mov     edx, 1004h; Msg
0x180031145  mov     rcx, r14; hWnd
0x180031148  call    cs:__imp_SendMessageW
0x18003114e  mov     rsi, rax
0x180031151  xor     edx, edx; Val
0x180031153  lea     r8d, [rdx+58h]; Size
0x180031157  lea     rcx, [rsp+160h+lParam]; void *
0x18003115c  call    memset_0
0x180031161  xor     r9d, r9d
0x180031164  mov     ebx, r9d
0x180031167  test    esi, esi
0x180031169  jle     loc_180031240
0x18003116f  mov     dword ptr [rsp+160h+lParam+4], ebx
0x180031173  mov     [rsp+160h+var_F8], r9d
0x180031178  mov     dword ptr [rsp+160h+lParam], 4
0x180031180  lea     r9, [rsp+160h+lParam]; lParam
0x180031185  xor     r8d, r8d; wParam
0x180031188  mov     edx, 104Bh; Msg
0x18003118d  mov     rcx, r14; hWnd
0x180031190  call    cs:__imp_SendMessageW
0x180031196  xor     r9d, r9d
0x180031199  test    eax, eax
0x18003119b  jz      loc_180031236
0x1800311a1  mov     rcx, [rbp+60h+var_D8]
0x1800311a5  test    rcx, rcx
0x1800311a8  jz      loc_180031236
0x1800311ae  mov     rcx, [rcx+8]
0x1800311b2  test    rcx, rcx
0x1800311b5  jz      short loc_180031236
0x1800311b7  cmp     dword ptr [rcx+18h], 2
0x1800311bb  jnz     short loc_180031236
0x1800311bd  mov     [rsp+160h+pv], r9
0x1800311c2  mov     rcx, [rcx]
0x1800311c5  mov     rax, [rcx]
0x1800311c8  lea     rdx, [rsp+160h+pv]
0x1800311cd  mov     rax, [rax+18h]
0x1800311d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800311d6  xor     r9d, r9d
0x1800311d9  test    eax, eax
0x1800311db  js      short loc_180031236
0x1800311dd  cmp     [rbp+60h+var_58], r9
0x1800311e1  jz      short loc_18003120C
0x1800311e3  mov     ecx, 3EABh; unsigned int
0x1800311e8  call    ?SzLoadIds@@YAPEBGI@Z; SzLoadIds(uint)
0x1800311ed  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800311f1  xor     ecx, ecx
0x1800311f3  inc     r8
0x1800311f6  cmp     [rax+r8*2], cx
0x1800311fb  jnz     short loc_1800311F3
0x1800311fd  mov     rdx, rax
0x180031200  lea     rcx, [rbp+60h+Src]; Src
0x180031204  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180031209  xor     r9d, r9d
0x18003120c  mov     rdx, [rsp+160h+pv]
0x180031211  or      r8, 0FFFFFFFFFFFFFFFFh
0x180031215  inc     r8
0x180031218  cmp     [rdx+r8*2], r9w
0x18003121d  jnz     short loc_180031215
0x18003121f  lea     rcx, [rbp+60h+Src]; Src
0x180031223  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180031228  mov     rcx, [rsp+160h+pv]; pv
0x18003122d  call    cs:__imp_CoTaskMemFree
0x180031233  xor     r9d, r9d
0x180031236  add     ebx, edi
0x180031238  cmp     ebx, esi
0x18003123a  jl      loc_18003116F
0x180031240  cmp     [rbp+60h+var_58], r9
0x180031244  jz      loc_1800312FC
0x18003124a  lea     rax, [rbp+60h+Src]
0x18003124e  cmp     [rbp+60h+var_50], 7
0x180031253  cmova   rax, [rbp+60h+Src]
0x180031258  mov     [rsp+160h+var_138], rax
0x18003125d  mov     [rsp+160h+uType], 44h ; 'D'; uType
0x180031265  mov     r9d, 3EA7h; unsigned int
0x18003126b  lea     r8d, [r9-1Fh]; unsigned int
0x18003126f  mov     rdx, r12; hWnd
0x180031272  mov     rcx, cs:hInst; hModule
0x180031279  call    ?NcMsgBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@IIIZZ; NcMsgBox(HINSTANCE__ *,HWND__ *,uint,uint,uint,...)
0x18003127e  cmp     eax, 7
0x180031281  jnz     short loc_1800312F9
0x180031283  xor     r12d, r12d
0x180031286  mov     ebx, r12d
0x180031289  test    esi, esi
0x18003128b  jle     short loc_1800312E4
0x18003128d  mov     dword ptr [rsp+160h+lParam+4], ebx
0x180031291  mov     [rsp+160h+var_F8], r12d
0x180031296  mov     dword ptr [rsp+160h+lParam], 4
0x18003129e  lea     r9, [rsp+160h+lParam]; lParam
0x1800312a3  xor     r8d, r8d; wParam
0x1800312a6  mov     edx, 104Bh; Msg
0x1800312ab  mov     rcx, r14; hWnd
0x1800312ae  call    cs:__imp_SendMessageW
0x1800312b4  test    eax, eax
0x1800312b6  jz      short loc_1800312DE
0x1800312b8  mov     rax, [rbp+60h+var_D8]
0x1800312bc  test    rax, rax
0x1800312bf  jz      short loc_1800312DE
0x1800312c1  mov     rcx, [rax+8]
0x1800312c5  test    rcx, rcx
0x1800312c8  jz      short loc_1800312DE
0x1800312ca  cmp     [rcx+20h], r12d
0x1800312ce  jz      short loc_1800312DE
0x1800312d0  mov     r8d, ebx
0x1800312d3  mov     rdx, r13
0x1800312d6  mov     rcx, r14; hWnd
0x1800312d9  call    ?HrToggleLVItemState@@YAJPEAUHWND__@@PEAV?$list@PEAVCBindingPathObj@@V?$allocator@PEAVCBindingPathObj@@@std@@@std@@H@Z; HrToggleLVItemState(HWND__ *,std::list<CBindingPathObj *> *,int)
0x1800312de  add     ebx, edi
0x1800312e0  cmp     ebx, esi
0x1800312e2  jl      short loc_18003128D
0x1800312e4  mov     r9, r13
0x1800312e7  mov     r8, r15
0x1800312ea  mov     rdx, [rsp+160h+var_128]
0x1800312ef  mov     rcx, r14; hWnd
0x1800312f2  call    ?HrRefreshAll@@YAJPEAUHWND__@@PEAUINetCfg@@PEAUINetCfgComponent@@PEAV?$list@PEAVCBindingPathObj@@V?$allocator@PEAVCBindingPathObj@@@std@@@std@@@Z; HrRefreshAll(HWND__ *,INetCfg *,INetCfgComponent *,std::list<CBindingPathObj *> *)
0x1800312f7  jmp     short loc_1800312FF
0x1800312f9  xor     r9d, r9d
0x1800312fc  mov     edi, r9d
0x1800312ff  lea     rcx, [rbp+60h+Src]
0x180031303  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031308  nop
0x180031309  lea     rcx, [rbp+60h+var_A0]; this
0x18003130d  call    ??1CIterNetCfgUpperBindingPath@@QEAA@XZ; CIterNetCfgUpperBindingPath::~CIterNetCfgUpperBindingPath(void)
0x180031312  mov     eax, edi
0x180031314  mov     rcx, [rbp+60h+var_48]
0x180031318  xor     rcx, rsp; StackCookie
0x18003131b  call    __security_check_cookie
0x180031320  add     rsp, 128h
0x180031327  pop     r15
0x180031329  pop     r14
0x18003132b  pop     r13
0x18003132d  pop     r12
0x18003132f  pop     rdi
0x180031330  pop     rsi
0x180031331  pop     rbx
0x180031332  pop     rbp
0x180031333  retn
```
