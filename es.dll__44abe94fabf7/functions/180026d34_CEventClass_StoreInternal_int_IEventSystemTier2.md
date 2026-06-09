# CEventClass::StoreInternal(int,IEventSystemTier2 *)

- ea: `0x180026d34`
- end: `0x1800270ab`
- name: `?StoreInternal@CEventClass@@AEAAJHPEAUIEventSystemTier2@@@Z`
- size: `887`
- prototype: `__int64 __fastcall(CEventClass *__hidden this, int, struct IEventSystemTier2 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180031040`

## callees

- `0x180003d54`
- `0x180008938`
- `0x180026d34`
- `0x1800434ae`
- `0x1800434c6`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180026fbd`
- `OLEAUT32!__imp_SysAllocString` at `0x180026fbd`
- `OLEAUT32!__imp_SysFreeString` at `0x180027002`
- `OLEAUT32!__imp_SysFreeString` at `0x1800451ce`
- `OLEAUT32!__imp_SysFreeString` at `0x180027002`
- `OLEAUT32!__imp_SysFreeString` at `0x1800451ce`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180026dbc`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180026f00`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180026dbc`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180026f00`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180026e98`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180026e98`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180026f95`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180026f95`

## string_xrefs

- `0x180026dc7`: `com\complus\src\events\tier1\eventclass.cpp`
- `0x180026ea6`: `ES.DLL`

## pseudocode

```c
__int64 __fastcall CEventClass::StoreInternal(CEventClass *this, int a2, struct IEventSystemTier2 *a3)
{
  struct IEventSystemTier2 *v3; // r15
  char *v6; // r13
  HRESULT v7; // eax
  _DWORD *v8; // r14
  int v9; // ebx
  IUnknown *v10; // rcx
  const wchar_t *v11; // r9
  HRESULT v13; // eax
  OLECHAR *v14; // r15
  int v15; // r13d
  IUnknown *pProxy; // [rsp+48h] [rbp-C0h] BYREF
  struct IEventSystemTier2 *v17; // [rsp+50h] [rbp-B8h]
  OLECHAR *v18; // [rsp+58h] [rbp-B0h]
  GUID Buf2; // [rsp+60h] [rbp-A8h] BYREF
  GUID pclsid; // [rsp+70h] [rbp-98h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-88h] BYREF

  v3 = a3;
  v17 = a3;
  v6 = (char *)this + 48;
  if ( !*((_WORD *)this + 24) || !*((_WORD *)this + 36) || !*((_WORD *)this + 60) && !*((_WORD *)this + 96) )
    return 2147942487LL;
  Buf2 = GUID_NULL;
  pclsid = GUID_NULL;
  v7 = CLSIDFromString(*((LPCOLESTR *)this + 7), &pclsid);
  if ( v7 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier1\\eventclass.cpp", 0x4EAu, 0x10u, v7);
  if ( memcmp_0(&CLSID_ComServiceEvents, &pclsid, 0x10u) )
  {
    if ( *((_WORD *)this + 156) )
    {
      v13 = CLSIDFromString(*((LPCOLESTR *)this + 40), &Buf2);
      if ( v13 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\eventclass.cpp", 0x4F2u, 0x10u, v13);
    }
    else
    {
      Buf2 = GUID_NULL;
    }
    v8 = (_DWORD *)((char *)this + 480);
    if ( *((_DWORD *)this + 120) )
    {
      if ( !a2 )
        goto LABEL_36;
      if ( !memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
      {
        memset_0(sz, 0, sizeof(sz));
        Buf2 = GUID_DefaultAppPartition;
        if ( !StringFromGUID2(&Buf2, sz, 40) )
          InternalError_HR(L"com\\complus\\src\\events\\tier1\\eventclass.cpp", 0x504u, 0x10u, -2147418113);
        v14 = SysAllocString(sz);
        v18 = v14;
        if ( !v14 )
          InternalError(L"com\\complus\\src\\events\\tier1\\eventclass.cpp", 0x507u, 0xC0001204, 0x10u);
        v15 = (*(__int64 (__fastcall **)(CEventClass *, OLECHAR *))(*(_QWORD *)this + 240LL))(this, v14);
        SysFreeString(v14);
        if ( v15 < 0 )
          InternalError_HR(L"com\\complus\\src\\events\\tier1\\eventclass.cpp", 0x512u, 0x10u, v15);
        v6 = (char *)this + 48;
        v3 = v17;
      }
    }
    if ( a2 )
    {
      if ( !memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
        return 2147746317LL;
      goto LABEL_9;
    }
LABEL_36:
    if ( memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
      return 2147746318LL;
    goto LABEL_9;
  }
  v8 = (_DWORD *)((char *)this + 480);
LABEL_9:
  pProxy = 0;
  v9 = (*(__int64 (__fastcall **)(struct IEventSystemTier2 *, _QWORD, char *, _QWORD, GUID *, IUnknown **))(*(_QWORD *)v3 + 64LL))(
         v3,
         0,
         (char *)this + 484,
         0,
         &IID_IEventClassTier2,
         &pProxy);
  if ( v9 >= 0 )
  {
    v10 = pProxy;
    if ( !pProxy )
    {
      InternalError(L"com\\complus\\src\\events\\tier1\\eventclass.cpp", 0x52Au, 0x80001203, 0x10u);
      v10 = pProxy;
    }
    CoSetProxyBlanket(
      v10,
      0xFFFFFFFF,
      0xFFFFFFFF,
      (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
      0,
      3u,
      (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
      0x40u);
    v11 = L"ES.DLL";
    if ( a2 )
      v11 = 0;
    v9 = ((__int64 (__fastcall *)(IUnknown *, struct IEventSystemTier2 *, char *, const wchar_t *))pProxy->lpVtbl[1].QueryInterface)(
           pProxy,
           v3,
           v6,
           v11);
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
  }
  if ( v9 >= 0 )
    *v8 = 0;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180026d34  mov     [rsp+arg_8], rbx
0x180026d39  mov     [rsp+arg_18], rsi
0x180026d3e  push    rdi
0x180026d3f  push    r12
0x180026d41  push    r13
0x180026d43  push    r14
0x180026d45  push    r15
0x180026d47  sub     rsp, 0E0h
0x180026d4e  mov     rax, cs:__security_cookie
0x180026d55  xor     rax, rsp
0x180026d58  mov     [rsp+108h+var_38], rax
0x180026d60  mov     r15, r8
0x180026d63  mov     [rsp+108h+var_B8], r8
0x180026d68  mov     r12d, edx
0x180026d6b  mov     rbx, rcx
0x180026d6e  lea     r13, [rcx+30h]
0x180026d72  xor     r14d, r14d
0x180026d75  cmp     [r13+0], r14w
0x180026d7a  jz      loc_180027079
0x180026d80  cmp     [rcx+48h], r14w
0x180026d85  jz      loc_180027079
0x180026d8b  cmp     [rcx+78h], r14w
0x180026d90  jnz     short loc_180026DA0
0x180026d92  cmp     [rcx+0C0h], r14w
0x180026d9a  jz      loc_180027079
0x180026da0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180026da7  movdqu  xmmword ptr [rsp+108h+Buf2.Data1], xmm0
0x180026dad  movdqu  xmmword ptr [rsp+108h+pclsid.Data1], xmm0
0x180026db3  lea     rdx, [rsp+108h+pclsid]; pclsid
0x180026db8  mov     rcx, [rcx+38h]; lpsz
0x180026dbc  call    cs:__imp_CLSIDFromString
0x180026dc2  mov     edi, 10h
0x180026dc7  lea     rsi, aComComplusSrcE; "com\\complus\\src\\events\\tier1\\event"...
0x180026dce  test    eax, eax
0x180026dd0  jns     short loc_180026DE5
0x180026dd2  mov     r8d, edi; unsigned __int16
0x180026dd5  mov     r9d, eax; int
0x180026dd8  mov     edx, 4EAh; unsigned int
0x180026ddd  mov     rcx, rsi; unsigned __int16 *
0x180026de0  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180026de5  mov     r8, rdi; Size
0x180026de8  lea     rdx, [rsp+108h+pclsid]; Buf2
0x180026ded  lea     rcx, CLSID_ComServiceEvents; Buf1
0x180026df4  call    memcmp_0
0x180026df9  test    eax, eax
0x180026dfb  jnz     loc_180026EEA
0x180026e01  lea     r14, [rbx+1E0h]
0x180026e08  mov     [rsp+108h+pProxy], 0
0x180026e11  mov     rax, [r15]
0x180026e14  lea     r8, [rbx+1E4h]
0x180026e1b  lea     rcx, [rsp+108h+pProxy]
0x180026e20  mov     qword ptr [rsp+108h+dwImpLevel], rcx
0x180026e25  lea     rcx, IID_IEventClassTier2
0x180026e2c  mov     qword ptr [rsp+108h+dwAuthnLevel], rcx
0x180026e31  xor     r9d, r9d
0x180026e34  xor     edx, edx
0x180026e36  mov     rcx, r15
0x180026e39  mov     rax, [rax+40h]
0x180026e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e42  mov     ebx, eax
0x180026e44  test    eax, eax
0x180026e46  js      loc_180026ED8
0x180026e4c  mov     rcx, [rsp+108h+pProxy]
0x180026e51  test    rcx, rcx
0x180026e54  jnz     short loc_180026E71
0x180026e56  mov     r9d, edi; unsigned __int16
0x180026e59  mov     edx, 52Ah; unsigned int
0x180026e5e  mov     r8d, 80001203h; unsigned int
0x180026e64  mov     rcx, rsi; unsigned __int16 *
0x180026e67  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180026e6c  mov     rcx, [rsp+108h+pProxy]; pProxy
0x180026e71  mov     [rsp+108h+dwCapabilities], 40h ; '@'; dwCapabilities
0x180026e79  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180026e7d  mov     [rsp+108h+pAuthInfo], r9; pAuthInfo
0x180026e82  mov     [rsp+108h+dwImpLevel], 3; dwImpLevel
0x180026e8a  mov     [rsp+108h+dwAuthnLevel], 0; dwAuthnLevel
0x180026e92  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180026e95  mov     r8d, edx; dwAuthzSvc
0x180026e98  call    cs:__imp_CoSetProxyBlanket
0x180026e9e  mov     rcx, [rsp+108h+pProxy]
0x180026ea3  mov     r10, [rcx]
0x180026ea6  lea     r9, aEsDll_0; "ES.DLL"
0x180026ead  xor     eax, eax
0x180026eaf  test    r12d, r12d
0x180026eb2  cmovnz  r9, rax
0x180026eb6  mov     r8, r13
0x180026eb9  mov     rdx, r15
0x180026ebc  mov     rax, [r10+18h]
0x180026ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ec5  mov     ebx, eax
0x180026ec7  mov     rcx, [rsp+108h+pProxy]
0x180026ecc  mov     rax, [rcx]
0x180026ecf  mov     rax, [rax+10h]
0x180026ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ed8  test    ebx, ebx
0x180026eda  js      short loc_180026EE3
0x180026edc  mov     dword ptr [r14], 0
0x180026ee3  mov     eax, ebx
0x180026ee5  jmp     loc_18002707E
0x180026eea  cmp     [rbx+138h], r14w
0x180026ef2  jz      short loc_180026F1F
0x180026ef4  lea     rdx, [rsp+108h+Buf2]; pclsid
0x180026ef9  mov     rcx, [rbx+140h]; lpsz
0x180026f00  call    cs:__imp_CLSIDFromString
0x180026f06  test    eax, eax
0x180026f08  jns     short loc_180026F2C
0x180026f0a  mov     r8d, edi; unsigned __int16
0x180026f0d  mov     r9d, eax; int
0x180026f10  mov     edx, 4F2h; unsigned int
0x180026f15  mov     rcx, rsi; unsigned __int16 *
0x180026f18  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180026f1d  jmp     short loc_180026F2C
0x180026f1f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180026f26  movdqu  xmmword ptr [rsp+108h+Buf2.Data1], xmm0
0x180026f2c  lea     r14, [rbx+1E0h]
0x180026f33  cmp     dword ptr [r14], 0
0x180026f37  jz      loc_180027029
0x180026f3d  test    r12d, r12d
0x180026f40  jz      loc_180027056
0x180026f46  mov     r8, rdi; Size
0x180026f49  lea     rdx, [rsp+108h+Buf2]; Buf2
0x180026f4e  lea     rcx, GUID_NULL; Buf1
0x180026f55  call    memcmp_0
0x180026f5a  test    eax, eax
0x180026f5c  jnz     loc_180027029
0x180026f62  xor     edx, edx; Val
0x180026f64  lea     r8d, [rax+50h]; Size
0x180026f68  lea     rcx, [rsp+108h+sz]; void *
0x180026f70  call    memset_0
0x180026f75  movups  xmm0, xmmword ptr cs:GUID_DefaultAppPartition.Data1
0x180026f7c  movdqu  xmmword ptr [rsp+108h+Buf2.Data1], xmm0
0x180026f82  mov     r8d, 28h ; '('; cchMax
0x180026f88  lea     rdx, [rsp+108h+sz]; lpsz
0x180026f90  lea     rcx, [rsp+108h+Buf2]; rguid
0x180026f95  call    cs:__imp_StringFromGUID2
0x180026f9b  test    eax, eax
0x180026f9d  jnz     short loc_180026FB5
0x180026f9f  mov     r8d, edi; unsigned __int16
0x180026fa2  mov     edx, 504h; unsigned int
0x180026fa7  mov     r9d, 8000FFFFh; int
0x180026fad  mov     rcx, rsi; unsigned __int16 *
0x180026fb0  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180026fb5  lea     rcx, [rsp+108h+sz]; psz
0x180026fbd  call    cs:__imp_SysAllocString
0x180026fc3  mov     r15, rax
0x180026fc6  mov     [rsp+108h+var_B0], rax
0x180026fcb  test    rax, rax
0x180026fce  jnz     short loc_180026FE7
0x180026fd0  mov     r9d, edi; unsigned __int16
0x180026fd3  mov     edx, 507h; unsigned int
0x180026fd8  mov     r8d, 0C0001204h; unsigned int
0x180026fde  mov     rcx, rsi; unsigned __int16 *
0x180026fe1  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180026fe6  nop
0x180026fe7  mov     rax, [rbx]
0x180026fea  mov     rdx, r15
0x180026fed  mov     rcx, rbx
0x180026ff0  mov     rax, [rax+0F0h]
0x180026ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ffc  mov     r13d, eax
0x180026fff  mov     rcx, r15; bstrString
0x180027002  call    cs:__imp_SysFreeString
0x180027008  test    r13d, r13d
0x18002700b  jns     short loc_180027020
0x18002700d  mov     r8d, edi; unsigned __int16
0x180027010  mov     r9d, r13d; int
0x180027013  mov     edx, 512h; unsigned int
0x180027018  mov     rcx, rsi; unsigned __int16 *
0x18002701b  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180027020  lea     r13, [rbx+30h]
0x180027024  mov     r15, [rsp+108h+var_B8]
0x180027029  test    r12d, r12d
0x18002702c  jz      short loc_180027056
0x18002702e  mov     r8, rdi; Size
0x180027031  lea     rdx, [rsp+108h+Buf2]; Buf2
0x180027036  lea     rcx, GUID_NULL; Buf1
0x18002703d  call    memcmp_0
0x180027042  test    eax, eax
0x180027044  jnz     short loc_18002704D
0x180027046  mov     eax, 8004020Dh
0x18002704b  jmp     short loc_18002707E
0x18002704d  test    r12d, r12d
0x180027050  jnz     loc_180026E08
0x180027056  mov     r8, rdi; Size
0x180027059  lea     rdx, [rsp+108h+Buf2]; Buf2
0x18002705e  lea     rcx, GUID_NULL; Buf1
0x180027065  call    memcmp_0
0x18002706a  test    eax, eax
0x18002706c  jz      loc_180026E08
0x180027072  mov     eax, 8004020Eh
0x180027077  jmp     short loc_18002707E
0x180027079  mov     eax, 80070057h
0x18002707e  mov     rcx, [rsp+108h+var_38]
0x180027086  xor     rcx, rsp; StackCookie
0x180027089  call    __security_check_cookie
0x18002708e  lea     r11, [rsp+108h+var_28]
0x180027096  mov     rbx, [r11+38h]
0x18002709a  mov     rsi, [r11+48h]
0x18002709e  mov     rsp, r11
0x1800270a1  pop     r15
0x1800270a3  pop     r14
0x1800270a5  pop     r13
0x1800270a7  pop     r12
0x1800270a9  pop     rdi
0x1800270aa  retn
0x1800451c1  push    rbp
0x1800451c3  sub     rsp, 40h
0x1800451c7  mov     rbp, rdx
0x1800451ca  mov     rcx, [rbp+58h]; bstrString
0x1800451ce  call    cs:__imp_SysFreeString
0x1800451d4  nop
0x1800451d5  add     rsp, 40h
0x1800451d9  pop     rbp
0x1800451da  retn
```
