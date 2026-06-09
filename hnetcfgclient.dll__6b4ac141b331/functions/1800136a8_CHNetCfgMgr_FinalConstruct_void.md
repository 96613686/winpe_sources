# CHNetCfgMgr::FinalConstruct(void)

- ea: `0x1800136a8`
- end: `0x180013998`
- name: `?FinalConstruct@CHNetCfgMgr@@QEAAJXZ`
- size: `752`
- prototype: `__int64 __fastcall(CHNetCfgMgr *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007bb4`
- `0x180007cac`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x1800136a8`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180013702`
- `OLEAUT32!__imp_SysAllocString` at `0x18001375f`
- `OLEAUT32!__imp_SysAllocString` at `0x180013702`
- `OLEAUT32!__imp_SysAllocString` at `0x18001375f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001391f`
- `OLEAUT32!__imp_SysFreeString` at `0x180013934`
- `OLEAUT32!__imp_SysFreeString` at `0x18001391f`
- `OLEAUT32!__imp_SysFreeString` at `0x180013934`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800137b9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800137b9`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800138e7`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800138e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CHNetCfgMgr::FinalConstruct(CHNetCfgMgr *this)
{
  BSTR v2; // rax
  OLECHAR *v3; // rsi
  PVOID *v4; // rcx
  __int64 v5; // rdx
  HRESULT v6; // eax
  int v7; // ebx
  unsigned int v8; // ebx
  IUnknown **v9; // rdi
  int v10; // eax
  IUnknown *v11; // rcx
  LPVOID ppv; // [rsp+90h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids);
  }
  ppv = 0;
  v2 = SysAllocString(L"WQL");
  *((_QWORD *)this + 15) = v2;
  if ( !v2 )
  {
    v3 = 0;
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_27;
    }
    v5 = 11;
    goto LABEL_10;
  }
  v3 = SysAllocString(L"\\\\.\\Root\\Microsoft\\HomeNet");
  if ( !v3 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_27;
    }
    v5 = 12;
LABEL_10:
    WPP_SF_d(v4[2], v5, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, 2147942414LL);
    v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_27:
    v8 = 0;
    v9 = (IUnknown **)((char *)this + 96);
    goto LABEL_35;
  }
  v6 = CoCreateInstance(&CLSID_WbemLocator, 0, 0x8005u, &GUID_dc12a687_737f_11cf_884d_00aa004b2e24, &ppv);
  v7 = v6;
  if ( v6 >= 0 )
    goto LABEL_21;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_27;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
      (unsigned int)v6);
LABEL_21:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 5u )
  {
    WPP_SF_d(v4[2], 14, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, (unsigned int)v7);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 < 0 )
    goto LABEL_27;
  v9 = (IUnknown **)((char *)this + 96);
  v10 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, char *))(*(_QWORD *)ppv + 24LL))(
          ppv,
          v3,
          0,
          0,
          0,
          0,
          0,
          0,
          (char *)this + 96);
  v8 = v10;
  if ( v10 >= 0 )
  {
    CoSetProxyBlanket(*v9, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 2u, 0, 0x40u);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
        (unsigned int)v10);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    v8 = 0;
  }
LABEL_35:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 )
  {
    SysFreeString(v3);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 )
  {
    SysFreeString(*((BSTR *)this + 15));
    v11 = *v9;
    *((_QWORD *)this + 15) = 0;
    if ( v11 )
    {
      ((void (__fastcall *)(IUnknown *))v11->lpVtbl->Release)(v11);
      *v9 = 0;
    }
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 16, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x1800136a8  push    rbx
0x1800136aa  push    rbp
0x1800136ab  push    rsi
0x1800136ac  push    rdi
0x1800136ad  push    r12
0x1800136af  push    r13
0x1800136b1  sub     rsp, 58h
0x1800136b5  mov     rbp, rcx
0x1800136b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800136bf  lea     r12, WPP_GLOBAL_Control
0x1800136c6  lea     r13, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x1800136cd  cmp     rcx, r12
0x1800136d0  jz      short loc_1800136EF
0x1800136d2  test    byte ptr [rcx+1Ch], 8
0x1800136d6  jz      short loc_1800136EF
0x1800136d8  cmp     byte ptr [rcx+19h], 6
0x1800136dc  jb      short loc_1800136EF
0x1800136de  mov     rcx, [rcx+10h]
0x1800136e2  mov     edx, 0Ah
0x1800136e7  mov     r8, r13
0x1800136ea  call    WPP_SF_
0x1800136ef  lea     rcx, ?c_wszWQL@@3QBGB; "WQL"
0x1800136f6  mov     [rsp+88h+arg_0], 0
0x180013702  call    cs:__imp_SysAllocString
0x180013708  mov     [rbp+78h], rax
0x18001370c  test    rax, rax
0x18001370f  jnz     short loc_180013758
0x180013711  xor     esi, esi
0x180013713  mov     rcx, cs:WPP_GLOBAL_Control
0x18001371a  cmp     rcx, r12
0x18001371d  jz      loc_180013828
0x180013723  test    byte ptr [rcx+1Ch], 8
0x180013727  jz      loc_180013828
0x18001372d  cmp     byte ptr [rcx+19h], 2
0x180013731  jb      loc_180013828
0x180013737  lea     edx, [rax+0Bh]
0x18001373a  mov     rcx, [rcx+10h]
0x18001373e  mov     r9d, 8007000Eh
0x180013744  mov     r8, r13
0x180013747  call    WPP_SF_d
0x18001374c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013753  jmp     loc_180013828
0x180013758  lea     rcx, ?c_wszNamespace@@3QBGB; "\\\\.\\Root\\Microsoft\\HomeNet"
0x18001375f  call    cs:__imp_SysAllocString
0x180013765  mov     rsi, rax
0x180013768  test    rax, rax
0x18001376b  jnz     short loc_180013796
0x18001376d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013774  cmp     rcx, r12
0x180013777  jz      loc_180013828
0x18001377d  test    byte ptr [rcx+1Ch], 8
0x180013781  jz      loc_180013828
0x180013787  cmp     byte ptr [rcx+19h], 2
0x18001378b  jb      loc_180013828
0x180013791  lea     edx, [rax+0Ch]
0x180013794  jmp     short loc_18001373A
0x180013796  lea     rax, [rsp+88h+arg_0]
0x18001379e  xor     edx, edx; pUnkOuter
0x1800137a0  lea     r9, _GUID_dc12a687_737f_11cf_884d_00aa004b2e24; riid
0x1800137a7  mov     [rsp+88h+ppv], rax; ppv
0x1800137ac  mov     r8d, 8005h; dwClsContext
0x1800137b2  lea     rcx, CLSID_WbemLocator; rclsid
0x1800137b9  call    cs:__imp_CoCreateInstance
0x1800137bf  mov     ebx, eax
0x1800137c1  test    eax, eax
0x1800137c3  jns     short loc_1800137F1
0x1800137c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800137cc  cmp     rcx, r12
0x1800137cf  jz      short loc_180013828
0x1800137d1  test    byte ptr [rcx+1Ch], 8
0x1800137d5  jz      short loc_1800137F8
0x1800137d7  cmp     byte ptr [rcx+19h], 2
0x1800137db  jb      short loc_1800137F8
0x1800137dd  mov     rcx, [rcx+10h]
0x1800137e1  mov     edx, 0Dh
0x1800137e6  mov     r9d, eax
0x1800137e9  mov     r8, r13
0x1800137ec  call    WPP_SF_d
0x1800137f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800137f8  cmp     rcx, r12
0x1800137fb  jz      short loc_180013824
0x1800137fd  test    byte ptr [rcx+1Ch], 8
0x180013801  jz      short loc_180013824
0x180013803  cmp     byte ptr [rcx+19h], 5
0x180013807  jb      short loc_180013824
0x180013809  mov     rcx, [rcx+10h]
0x18001380d  mov     edx, 0Eh
0x180013812  mov     r9d, ebx
0x180013815  mov     r8, r13
0x180013818  call    WPP_SF_d
0x18001381d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013824  test    ebx, ebx
0x180013826  jns     short loc_180013833
0x180013828  xor     ebx, ebx
0x18001382a  lea     rdi, [rbp+60h]
0x18001382e  jmp     loc_1800138F4
0x180013833  mov     rcx, [rsp+88h+arg_0]
0x18001383b  lea     rdi, [rbp+60h]
0x18001383f  mov     [rsp+88h+var_48], rdi
0x180013844  xor     r9d, r9d
0x180013847  mov     qword ptr [rsp+88h+dwCapabilities], 0
0x180013850  xor     r8d, r8d
0x180013853  mov     [rsp+88h+pAuthInfo], 0
0x18001385c  mov     rdx, rsi
0x18001385f  mov     rax, [rcx]
0x180013862  mov     [rsp+88h+dwImpLevel], 0
0x18001386a  mov     [rsp+88h+ppv], 0
0x180013873  mov     rax, [rax+18h]
0x180013877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001387c  mov     ebx, eax
0x18001387e  test    eax, eax
0x180013880  jns     short loc_1800138B9
0x180013882  mov     rcx, cs:WPP_GLOBAL_Control
0x180013889  cmp     rcx, r12
0x18001388c  jz      short loc_1800138B5
0x18001388e  test    byte ptr [rcx+1Ch], 8
0x180013892  jz      short loc_1800138B5
0x180013894  cmp     byte ptr [rcx+19h], 2
0x180013898  jb      short loc_1800138B5
0x18001389a  mov     rcx, [rcx+10h]
0x18001389e  mov     edx, 0Fh
0x1800138a3  mov     r9d, eax
0x1800138a6  mov     r8, r13
0x1800138a9  call    WPP_SF_d
0x1800138ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800138b5  xor     ebx, ebx
0x1800138b7  jmp     short loc_1800138F4
0x1800138b9  mov     rcx, [rdi]; pProxy
0x1800138bc  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1800138bf  mov     [rsp+88h+dwCapabilities], 40h ; '@'; dwCapabilities
0x1800138c7  mov     r8d, edx; dwAuthzSvc
0x1800138ca  mov     [rsp+88h+pAuthInfo], 0; pAuthInfo
0x1800138d3  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800138d7  mov     [rsp+88h+dwImpLevel], 2; dwImpLevel
0x1800138df  mov     dword ptr [rsp+88h+ppv], 0; dwAuthnLevel
0x1800138e7  call    cs:__imp_CoSetProxyBlanket
0x1800138ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800138f4  mov     rdx, [rsp+88h+arg_0]
0x1800138fc  test    rdx, rdx
0x1800138ff  jz      short loc_180013917
0x180013901  mov     rax, [rdx]
0x180013904  mov     rcx, rdx
0x180013907  mov     rax, [rax+10h]
0x18001390b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013910  mov     rcx, cs:WPP_GLOBAL_Control
0x180013917  test    rsi, rsi
0x18001391a  jz      short loc_18001392C
0x18001391c  mov     rcx, rsi; bstrString
0x18001391f  call    cs:__imp_SysFreeString
0x180013925  mov     rcx, cs:WPP_GLOBAL_Control
0x18001392c  test    ebx, ebx
0x18001392e  jz      short loc_180013964
0x180013930  mov     rcx, [rbp+78h]; bstrString
0x180013934  call    cs:__imp_SysFreeString
0x18001393a  mov     rcx, [rdi]
0x18001393d  mov     qword ptr [rbp+78h], 0
0x180013945  test    rcx, rcx
0x180013948  jz      short loc_18001395D
0x18001394a  mov     rax, [rcx]
0x18001394d  mov     rax, [rax+10h]
0x180013951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013956  mov     qword ptr [rdi], 0
0x18001395d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013964  cmp     rcx, r12
0x180013967  jz      short loc_180013989
0x180013969  test    byte ptr [rcx+1Ch], 8
0x18001396d  jz      short loc_180013989
0x18001396f  cmp     byte ptr [rcx+19h], 6
0x180013973  jb      short loc_180013989
0x180013975  mov     rcx, [rcx+10h]
0x180013979  mov     edx, 10h
0x18001397e  mov     r9d, ebx
0x180013981  mov     r8, r13
0x180013984  call    WPP_SF_d
0x180013989  mov     eax, ebx
0x18001398b  add     rsp, 58h
0x18001398f  pop     r13
0x180013991  pop     r12
0x180013993  pop     rdi
0x180013994  pop     rsi
0x180013995  pop     rbp
0x180013996  pop     rbx
0x180013997  retn
```
