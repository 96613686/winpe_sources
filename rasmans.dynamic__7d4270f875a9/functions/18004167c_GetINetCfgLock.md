# GetINetCfgLock

- ea: `0x18004167c`
- end: `0x180041a57`
- name: `GetINetCfgLock`
- size: `987`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180010be0`
- `0x1800463fc`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000ec50`
- `0x18004167c`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004179c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004179c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180041758`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180041758`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800418c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004199e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800418c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004199e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180041a06`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180041a06`

## string_xrefs

- `0x180041846`: `rasmans.dll`

## pseudocode

```c
__int64 __fastcall GetINetCfgLock(LPVOID *a1, _QWORD *a2, unsigned int a3, _DWORD *a4)
{
  struct _LIST_ENTRY *v8; // rcx
  bool v9; // zf
  HRESULT v11; // eax
  unsigned int v12; // ebx
  struct _LIST_ENTRY *v13; // rcx
  __int64 v14; // rdx
  int v15; // eax
  struct _LIST_ENTRY *v16; // rcx
  __int64 v17; // [rsp+70h] [rbp+40h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp+48h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+58h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 695, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, a3);
    v8 = WPP_GLOBAL_Control;
  }
  v9 = g_RasMobileCore == 0;
  ppv = 0;
  v17 = 0;
  pv = 0;
  *a1 = 0;
  *a2 = 0;
  *a4 = 0;
  if ( !v9 )
  {
    if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v8[1].Blink) & 0x2000) != 0
      && BYTE1(v8[1].Blink) >= 6u )
    {
      WPP_SF_d(v8[1].Flink, 696, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, 1);
    }
    return 1;
  }
  v11 = CoInitializeEx(0, 4u);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( v11 != -2147417850 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_48;
      }
      v14 = 697;
LABEL_46:
      WPP_SF_d(v13[1].Flink, v14, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, (unsigned int)v11);
LABEL_47:
      v13 = WPP_GLOBAL_Control;
LABEL_48:
      if ( pv )
      {
        CoTaskMemFree(pv);
        v13 = WPP_GLOBAL_Control;
      }
      if ( v17 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        v13 = WPP_GLOBAL_Control;
        v17 = 0;
      }
      if ( ppv )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        v13 = WPP_GLOBAL_Control;
        ppv = 0;
      }
      if ( *a4 )
      {
        CoUninitialize();
        v13 = WPP_GLOBAL_Control;
      }
      if ( v13 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v13[1].Blink) & 0x2000) != 0
        && BYTE1(v13[1].Blink) >= 6u )
      {
        WPP_SF_d(v13[1].Flink, 703, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v12);
      }
      return v12;
    }
  }
  else
  {
    *a4 = 1;
  }
  v11 = CoCreateInstance(&CLSID_CNetCfg, 0, 1u, &IID_INetCfg, &ppv);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_48;
    }
    v14 = 698;
    goto LABEL_46;
  }
  v11 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_INetCfgLock, &v17);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_48;
    }
    v14 = 699;
    goto LABEL_46;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, LPVOID *))(*(_QWORD *)v17 + 24LL))(
          v17,
          a3,
          L"rasmans.dll",
          &pv);
  v12 = v15;
  if ( v15 == 1 )
  {
    v12 = -2147180508;
    goto LABEL_27;
  }
  if ( v15 < 0 )
  {
LABEL_27:
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_48;
    }
    WPP_SF_Sd(
      WPP_GLOBAL_Control[1].Flink,
      700,
      (unsigned int)WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids,
      (_DWORD)pv,
      v12);
    goto LABEL_47;
  }
  if ( pv )
    CoTaskMemFree(pv);
  *a1 = ppv;
  *a2 = v17;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 701, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
      v16 = WPP_GLOBAL_Control;
    }
    if ( v16 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v16[1].Blink) & 0x2000) != 0
      && BYTE1(v16[1].Blink) >= 6u )
    {
      WPP_SF_d(v16[1].Flink, 702, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18004167c  push    rbp
0x18004167e  push    rbx
0x18004167f  push    rsi
0x180041680  push    rdi
0x180041681  push    r12
0x180041683  push    r14
0x180041685  push    r15
0x180041687  mov     rbp, rsp
0x18004168a  sub     rsp, 30h
0x18004168e  mov     r12, r9
0x180041691  mov     r15d, r8d
0x180041694  mov     rsi, rdx
0x180041697  mov     r14, rcx
0x18004169a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800416a1  lea     rax, WPP_GLOBAL_Control
0x1800416a8  cmp     rcx, rax
0x1800416ab  jz      short loc_1800416E2
0x1800416ad  test    dword ptr [rcx+1Ch], 2000h
0x1800416b4  jz      short loc_1800416E2
0x1800416b6  cmp     byte ptr [rcx+19h], 6
0x1800416ba  jb      short loc_1800416E2
0x1800416bc  mov     rcx, [rcx+10h]
0x1800416c0  mov     r9d, r8d
0x1800416c3  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x1800416ca  mov     edx, 2B7h
0x1800416cf  call    WPP_SF_d
0x1800416d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800416db  lea     rax, WPP_GLOBAL_Control
0x1800416e2  cmp     cs:g_RasMobileCore, 0
0x1800416e9  mov     [rbp+arg_8], 0
0x1800416f1  mov     [rbp+arg_0], 0
0x1800416f9  mov     [rbp+pv], 0
0x180041701  mov     qword ptr [r14], 0
0x180041708  mov     qword ptr [rsi], 0
0x18004170f  mov     dword ptr [r12], 0
0x180041717  jz      short loc_180041751
0x180041719  mov     edi, 1
0x18004171e  cmp     rcx, rax
0x180041721  jz      short loc_18004174A
0x180041723  test    dword ptr [rcx+1Ch], 2000h
0x18004172a  jz      short loc_18004174A
0x18004172c  cmp     byte ptr [rcx+19h], 6
0x180041730  jb      short loc_18004174A
0x180041732  mov     rcx, [rcx+10h]
0x180041736  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18004173d  mov     edx, 2B8h
0x180041742  mov     r9d, edi
0x180041745  call    WPP_SF_d
0x18004174a  mov     eax, edi
0x18004174c  jmp     loc_180041A47
0x180041751  mov     edx, 4; dwCoInit
0x180041756  xor     ecx, ecx; pvReserved
0x180041758  call    cs:__imp_CoInitializeEx
0x18004175f  nop     dword ptr [rax+rax+00h]
0x180041764  mov     ebx, eax
0x180041766  mov     edi, 1
0x18004176b  test    eax, eax
0x18004176d  js      short loc_180041775
0x18004176f  mov     [r12], edi
0x180041773  jmp     short loc_180041780
0x180041775  cmp     eax, 80010106h
0x18004177a  jnz     loc_180041951
0x180041780  lea     rax, [rbp+arg_8]
0x180041784  mov     r8d, edi; dwClsContext
0x180041787  lea     r9, IID_INetCfg; riid
0x18004178e  mov     [rsp+30h+ppv], rax; ppv
0x180041793  xor     edx, edx; pUnkOuter
0x180041795  lea     rcx, CLSID_CNetCfg; rclsid
0x18004179c  call    cs:__imp_CoCreateInstance
0x1800417a3  nop     dword ptr [rax+rax+00h]
0x1800417a8  mov     ebx, eax
0x1800417aa  test    eax, eax
0x1800417ac  jns     short loc_1800417E6
0x1800417ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800417b5  lea     rdi, WPP_GLOBAL_Control
0x1800417bc  cmp     rcx, rdi
0x1800417bf  jz      loc_180041992
0x1800417c5  test    dword ptr [rcx+1Ch], 2000h
0x1800417cc  jz      loc_180041992
0x1800417d2  cmp     byte ptr [rcx+19h], 2
0x1800417d6  jb      loc_180041992
0x1800417dc  mov     edx, 2BAh
0x1800417e1  jmp     loc_180041978
0x1800417e6  mov     rcx, [rbp+arg_8]
0x1800417ea  lea     r8, [rbp+arg_0]
0x1800417ee  lea     rdx, IID_INetCfgLock
0x1800417f5  mov     rax, [rcx]
0x1800417f8  mov     rax, [rax]
0x1800417fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041800  mov     ebx, eax
0x180041802  test    eax, eax
0x180041804  jns     short loc_18004183E
0x180041806  mov     rcx, cs:WPP_GLOBAL_Control
0x18004180d  lea     rdi, WPP_GLOBAL_Control
0x180041814  cmp     rcx, rdi
0x180041817  jz      loc_180041992
0x18004181d  test    dword ptr [rcx+1Ch], 2000h
0x180041824  jz      loc_180041992
0x18004182a  cmp     byte ptr [rcx+19h], 2
0x18004182e  jb      loc_180041992
0x180041834  mov     edx, 2BBh
0x180041839  jmp     loc_180041978
0x18004183e  mov     rcx, [rbp+arg_0]
0x180041842  lea     r9, [rbp+pv]
0x180041846  lea     r8, aRasmansDll_2; "rasmans.dll"
0x18004184d  mov     edx, r15d
0x180041850  mov     rax, [rcx]
0x180041853  mov     rax, [rax+18h]
0x180041857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004185c  mov     ebx, eax
0x18004185e  cmp     eax, edi
0x180041860  jnz     short loc_180041869
0x180041862  mov     ebx, 8004A024h
0x180041867  jmp     short loc_18004186D
0x180041869  test    eax, eax
0x18004186b  jns     short loc_1800418BD
0x18004186d  mov     rcx, cs:WPP_GLOBAL_Control
0x180041874  lea     rdi, WPP_GLOBAL_Control
0x18004187b  cmp     rcx, rdi
0x18004187e  jz      loc_180041992
0x180041884  test    dword ptr [rcx+1Ch], 2000h
0x18004188b  jz      loc_180041992
0x180041891  cmp     byte ptr [rcx+19h], 2
0x180041895  jb      loc_180041992
0x18004189b  mov     r9, [rbp+pv]
0x18004189f  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x1800418a6  mov     rcx, [rcx+10h]
0x1800418aa  mov     edx, 2BCh
0x1800418af  mov     dword ptr [rsp+30h+ppv], ebx
0x1800418b3  call    WPP_SF_Sd
0x1800418b8  jmp     loc_18004198B
0x1800418bd  mov     rcx, [rbp+pv]; pv
0x1800418c1  test    rcx, rcx
0x1800418c4  jz      short loc_1800418D2
0x1800418c6  call    cs:__imp_CoTaskMemFree
0x1800418cd  nop     dword ptr [rax+rax+00h]
0x1800418d2  mov     rax, [rbp+arg_8]
0x1800418d6  mov     [r14], rax
0x1800418d9  mov     rax, [rbp+arg_0]
0x1800418dd  mov     [rsi], rax
0x1800418e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800418e7  lea     rdi, WPP_GLOBAL_Control
0x1800418ee  cmp     rcx, rdi
0x1800418f1  jz      short loc_18004194A
0x1800418f3  test    dword ptr [rcx+1Ch], 2000h
0x1800418fa  jz      short loc_18004191E
0x1800418fc  cmp     byte ptr [rcx+19h], 5
0x180041900  jb      short loc_18004191E
0x180041902  mov     rcx, [rcx+10h]
0x180041906  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18004190d  mov     edx, 2BDh
0x180041912  call    WPP_SF_
0x180041917  mov     rcx, cs:WPP_GLOBAL_Control
0x18004191e  cmp     rcx, rdi
0x180041921  jz      short loc_18004194A
0x180041923  test    dword ptr [rcx+1Ch], 2000h
0x18004192a  jz      short loc_18004194A
0x18004192c  cmp     byte ptr [rcx+19h], 6
0x180041930  jb      short loc_18004194A
0x180041932  mov     rcx, [rcx+10h]
0x180041936  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18004193d  mov     edx, 2BEh
0x180041942  xor     r9d, r9d
0x180041945  call    WPP_SF_d
0x18004194a  xor     eax, eax
0x18004194c  jmp     loc_180041A47
0x180041951  mov     rcx, cs:WPP_GLOBAL_Control
0x180041958  lea     rdi, WPP_GLOBAL_Control
0x18004195f  cmp     rcx, rdi
0x180041962  jz      short loc_180041992
0x180041964  test    dword ptr [rcx+1Ch], 2000h
0x18004196b  jz      short loc_180041992
0x18004196d  cmp     byte ptr [rcx+19h], 2
0x180041971  jb      short loc_180041992
0x180041973  mov     edx, 2B9h
0x180041978  mov     rcx, [rcx+10h]
0x18004197c  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x180041983  mov     r9d, eax
0x180041986  call    WPP_SF_d
0x18004198b  mov     rcx, cs:WPP_GLOBAL_Control
0x180041992  mov     rax, [rbp+pv]
0x180041996  test    rax, rax
0x180041999  jz      short loc_1800419B1
0x18004199b  mov     rcx, rax; pv
0x18004199e  call    cs:__imp_CoTaskMemFree
0x1800419a5  nop     dword ptr [rax+rax+00h]
0x1800419aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800419b1  mov     rdx, [rbp+arg_0]
0x1800419b5  test    rdx, rdx
0x1800419b8  jz      short loc_1800419D8
0x1800419ba  mov     rax, [rdx]
0x1800419bd  mov     rcx, rdx
0x1800419c0  mov     rax, [rax+10h]
0x1800419c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800419c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800419d0  mov     [rbp+arg_0], 0
0x1800419d8  mov     rdx, [rbp+arg_8]
0x1800419dc  test    rdx, rdx
0x1800419df  jz      short loc_1800419FF
0x1800419e1  mov     rax, [rdx]
0x1800419e4  mov     rcx, rdx
0x1800419e7  mov     rax, [rax+10h]
0x1800419eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800419f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800419f7  mov     [rbp+arg_8], 0
0x1800419ff  cmp     dword ptr [r12], 0
0x180041a04  jz      short loc_180041A19
0x180041a06  call    cs:__imp_CoUninitialize
0x180041a0d  nop     dword ptr [rax+rax+00h]
0x180041a12  mov     rcx, cs:WPP_GLOBAL_Control
0x180041a19  cmp     rcx, rdi
0x180041a1c  jz      short loc_180041A45
0x180041a1e  test    dword ptr [rcx+1Ch], 2000h
0x180041a25  jz      short loc_180041A45
0x180041a27  cmp     byte ptr [rcx+19h], 6
0x180041a2b  jb      short loc_180041A45
0x180041a2d  mov     rcx, [rcx+10h]
0x180041a31  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x180041a38  mov     edx, 2BFh
0x180041a3d  mov     r9d, ebx
0x180041a40  call    WPP_SF_d
0x180041a45  mov     eax, ebx
0x180041a47  add     rsp, 30h
0x180041a4b  pop     r15
0x180041a4d  pop     r14
0x180041a4f  pop     r12
0x180041a51  pop     rdi
0x180041a52  pop     rsi
0x180041a53  pop     rbx
0x180041a54  pop     rbp
0x180041a55  retn
```
