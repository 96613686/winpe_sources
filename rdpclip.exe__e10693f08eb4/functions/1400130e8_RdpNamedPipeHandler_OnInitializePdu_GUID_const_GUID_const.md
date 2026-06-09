# RdpNamedPipeHandler::OnInitializePdu(_GUID const &,_GUID const &)

- ea: `0x1400130e8`
- end: `0x14001337a`
- name: `?OnInitializePdu@RdpNamedPipeHandler@@AEAAJAEBU_GUID@@0@Z`
- size: `658`
- prototype: `int(RdpNamedPipeHandler *__hidden this, const struct _GUID *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140012620`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x140005704`
- `0x140005750`
- `0x14000a640`
- `0x1400130e8`
- `0x14006a120`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1400132a7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1400132a7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140013154`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140013154`

## string_xrefs

- `0x140013189`: `CoCreateInstance (CLSID_UiaManagerCrossMachineStubFactory) failed`
- `0x140013224`: `IUiaManagerCrossMachineStubFactory::CreateStub failed`

## pseudocode

```c
__int64 __fastcall RdpNamedPipeHandler::OnInitializePdu(
        RdpNamedPipeHandler *this,
        const struct _GUID *a2,
        const struct _GUID *a3)
{
  __int64 v4; // rax
  HRESULT v5; // ebx
  unsigned int v6; // eax
  int v7; // edx
  const char *v8; // rcx
  LPVOID v9; // rcx
  __int64 v10; // rax
  unsigned int v11; // eax
  LPVOID v12; // rcx
  unsigned int v13; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HRESULT v16; // [rsp+28h] [rbp-31h]
  LPVOID ppv; // [rsp+30h] [rbp-29h] BYREF
  __int128 v18; // [rsp+40h] [rbp-19h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-9h] BYREF

  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&CLSID_UiaManagerCrossMachineStubFactory.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&CLSID_UiaManagerCrossMachineStubFactory.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)CLSID_UiaManagerCrossMachineStubFactory.Data4;
  if ( v4 )
  {
    if ( StringFromGUID2(a2, sz, 39) > 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          99,
          (unsigned int)&WPP_9a7fa01c864e3dc68f2a9283abe3b96f_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)sz);
      }
      return (unsigned int)-2147024809;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          98,
          &WPP_9a7fa01c864e3dc68f2a9283abe3b96f_Traceguids,
          v13,
          -2147467259);
      }
      return (unsigned int)-2147467259;
    }
  }
  else
  {
    ppv = 0;
    v5 = CoCreateInstance(
           &CLSID_UiaManagerCrossMachineStubFactory,
           0,
           4u,
           &GUID_37284c45_c0c6_4cf8_b858_c4867cdf986e,
           &ppv);
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 95;
        v8 = "CoCreateInstance (CLSID_UiaManagerCrossMachineStubFactory) failed";
LABEL_9:
        v16 = v5;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v7,
          (unsigned int)&WPP_9a7fa01c864e3dc68f2a9283abe3b96f_Traceguids,
          v6,
          (__int64)v8,
          v16);
        goto LABEL_10;
      }
      goto LABEL_10;
    }
    v10 = *(_QWORD *)ppv;
    v18 = (__int128)*a3;
    v5 = (*(__int64 (__fastcall **)(LPVOID, __int128 *))(v10 + 24))(ppv, &v18);
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 96;
        v8 = "IUiaManagerCrossMachineStubFactory::CreateStub failed";
        goto LABEL_9;
      }
LABEL_10:
      v9 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
      }
      return (unsigned int)v5;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_9a7fa01c864e3dc68f2a9283abe3b96f_Traceguids, v11);
    }
    v12 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1400130e8  mov     [rsp-8+arg_0], rbx
0x1400130ed  mov     [rsp-8+arg_18], rdi
0x1400130f2  push    rbp
0x1400130f3  lea     rbp, [rsp-57h]
0x1400130f8  sub     rsp, 0B0h
0x1400130ff  mov     rax, cs:__security_cookie
0x140013106  xor     rax, rsp
0x140013109  mov     [rbp+57h+var_10], rax
0x14001310d  mov     rax, [rdx]
0x140013110  mov     rdi, r8
0x140013113  sub     rax, qword ptr cs:CLSID_UiaManagerCrossMachineStubFactory.Data1
0x14001311a  mov     r9, rdx
0x14001311d  jnz     short loc_14001312A
0x14001311f  mov     rax, [rdx+8]
0x140013123  sub     rax, qword ptr cs:CLSID_UiaManagerCrossMachineStubFactory.Data4
0x14001312a  test    rax, rax
0x14001312d  jnz     loc_14001329A
0x140013133  xor     edx, edx; pUnkOuter
0x140013135  mov     [rbp+57h+var_80], rax
0x140013139  lea     rax, [rbp+57h+var_80]
0x14001313d  lea     r9, _GUID_37284c45_c0c6_4cf8_b858_c4867cdf986e; riid
0x140013144  mov     [rsp+0B0h+ppv], rax; ppv
0x140013149  lea     rcx, CLSID_UiaManagerCrossMachineStubFactory; rclsid
0x140013150  lea     r8d, [rdx+4]; dwClsContext
0x140013154  call    cs:__imp_CoCreateInstance
0x14001315a  mov     ebx, eax
0x14001315c  test    eax, eax
0x14001315e  jns     short loc_1400131D9
0x140013160  mov     rax, cs:WPP_GLOBAL_Control
0x140013167  lea     rcx, WPP_GLOBAL_Control
0x14001316e  cmp     rax, rcx
0x140013171  jz      short loc_1400131B3
0x140013173  test    byte ptr [rax+1Ch], 8
0x140013177  jz      short loc_1400131B3
0x140013179  cmp     byte ptr [rax+19h], 2
0x14001317d  jb      short loc_1400131B3
0x14001317f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140013184  mov     edx, 5Fh ; '_'
0x140013189  lea     rcx, aCocreateinstan; "CoCreateInstance (CLSID_UiaManagerCross"...
0x140013190  mov     [rsp+0B0h+var_88], ebx
0x140013194  lea     r8, WPP_9a7fa01c864e3dc68f2a9283abe3b96f_Traceguids
0x14001319b  mov     [rsp+0B0h+ppv], rcx
0x1400131a0  mov     r9d, eax
0x1400131a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400131aa  mov     rcx, [rcx+10h]
0x1400131ae  call    WPP_SF_DsD
0x1400131b3  mov     rcx, [rbp+57h+var_80]
0x1400131b7  test    rcx, rcx
0x1400131ba  jz      loc_140013357
0x1400131c0  mov     [rbp+57h+var_80], 0
0x1400131c8  mov     rax, [rcx]
0x1400131cb  mov     rax, [rax+10h]
0x1400131cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400131d4  jmp     loc_140013357
0x1400131d9  mov     rcx, [rbp+57h+var_80]
0x1400131dd  lea     rdx, [rbp+57h+var_70]
0x1400131e1  movups  xmm0, xmmword ptr [rdi]
0x1400131e4  mov     rax, [rcx]
0x1400131e7  movdqu  [rbp+57h+var_70], xmm0
0x1400131ec  mov     rax, [rax+18h]
0x1400131f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400131f5  mov     ebx, eax
0x1400131f7  test    eax, eax
0x1400131f9  jns     short loc_140013230
0x1400131fb  mov     rax, cs:WPP_GLOBAL_Control
0x140013202  lea     rcx, WPP_GLOBAL_Control
0x140013209  cmp     rax, rcx
0x14001320c  jz      short loc_1400131B3
0x14001320e  test    byte ptr [rax+1Ch], 8
0x140013212  jz      short loc_1400131B3
0x140013214  cmp     byte ptr [rax+19h], 2
0x140013218  jb      short loc_1400131B3
0x14001321a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001321f  mov     edx, 60h ; '`'
0x140013224  lea     rcx, aIuiamanagercro; "IUiaManagerCrossMachineStubFactory::Cre"...
0x14001322b  jmp     loc_140013190
0x140013230  mov     rax, cs:WPP_GLOBAL_Control
0x140013237  lea     rcx, WPP_GLOBAL_Control
0x14001323e  cmp     rax, rcx
0x140013241  jz      short loc_140013276
0x140013243  test    dword ptr [rax+1Ch], 1000h
0x14001324a  jz      short loc_140013276
0x14001324c  cmp     byte ptr [rax+19h], 4
0x140013250  jb      short loc_140013276
0x140013252  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140013257  mov     rcx, cs:WPP_GLOBAL_Control
0x14001325e  lea     r8, WPP_9a7fa01c864e3dc68f2a9283abe3b96f_Traceguids
0x140013265  mov     edx, 61h ; 'a'
0x14001326a  mov     r9d, eax
0x14001326d  mov     rcx, [rcx+10h]
0x140013271  call    WPP_SF_d
0x140013276  mov     rcx, [rbp+57h+var_80]
0x14001327a  test    rcx, rcx
0x14001327d  jz      short loc_140013293
0x14001327f  mov     [rbp+57h+var_80], 0
0x140013287  mov     rax, [rcx]
0x14001328a  mov     rax, [rax+10h]
0x14001328e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013293  xor     ebx, ebx
0x140013295  jmp     loc_140013357
0x14001329a  mov     r8d, 27h ; '''; cchMax
0x1400132a0  lea     rdx, [rbp+57h+sz]; lpsz
0x1400132a4  mov     rcx, r9; rguid
0x1400132a7  call    cs:__imp_StringFromGUID2
0x1400132ad  test    eax, eax
0x1400132af  jg      short loc_140013303
0x1400132b1  mov     rax, cs:WPP_GLOBAL_Control
0x1400132b8  lea     rcx, WPP_GLOBAL_Control
0x1400132bf  cmp     rax, rcx
0x1400132c2  jz      short loc_1400132FC
0x1400132c4  test    byte ptr [rax+1Ch], 8
0x1400132c8  jz      short loc_1400132FC
0x1400132ca  cmp     byte ptr [rax+19h], 2
0x1400132ce  jb      short loc_1400132FC
0x1400132d0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400132d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400132dc  lea     r8, WPP_9a7fa01c864e3dc68f2a9283abe3b96f_Traceguids
0x1400132e3  mov     edx, 62h ; 'b'
0x1400132e8  mov     dword ptr [rsp+0B0h+ppv], 80004005h
0x1400132f0  mov     r9d, eax
0x1400132f3  mov     rcx, [rcx+10h]
0x1400132f7  call    WPP_SF_Dd
0x1400132fc  mov     ebx, 80004005h
0x140013301  jmp     short loc_140013357
0x140013303  mov     rax, cs:WPP_GLOBAL_Control
0x14001330a  lea     rcx, WPP_GLOBAL_Control
0x140013311  cmp     rax, rcx
0x140013314  jz      short loc_140013352
0x140013316  test    dword ptr [rax+1Ch], 1000h
0x14001331d  jz      short loc_140013352
0x14001331f  cmp     byte ptr [rax+19h], 3
0x140013323  jb      short loc_140013352
0x140013325  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001332a  lea     rcx, [rbp+57h+sz]
0x14001332e  mov     edx, 63h ; 'c'
0x140013333  mov     [rsp+0B0h+ppv], rcx
0x140013338  lea     r8, WPP_9a7fa01c864e3dc68f2a9283abe3b96f_Traceguids
0x14001333f  mov     rcx, cs:WPP_GLOBAL_Control
0x140013346  mov     r9d, eax
0x140013349  mov     rcx, [rcx+10h]
0x14001334d  call    WPP_SF_DS
0x140013352  mov     ebx, 80070057h
0x140013357  mov     eax, ebx
0x140013359  mov     rcx, [rbp+57h+var_10]
0x14001335d  xor     rcx, rsp; StackCookie
0x140013360  call    __security_check_cookie
0x140013365  lea     r11, [rsp+0B0h+var_s0]
0x14001336d  mov     rbx, [r11+10h]
0x140013371  mov     rdi, [r11+28h]
0x140013375  mov     rsp, r11
0x140013378  pop     rbp
0x140013379  retn
```
