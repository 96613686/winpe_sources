# SetElementProperties(IXmlReader *,CDIProperties<ID2D1InkEffect> *)

- ea: `0x180228178`
- end: `0x18022842e`
- name: `?SetElementProperties@@YAJPEAUIXmlReader@@PEAV?$CDIProperties@UID2D1InkEffect@@@@@Z`
- size: `694`
- prototype: `__int64 __fastcall(__int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180228020`

## callees

- `0x18001fd58`
- `0x1800389c0`
- `0x1800acf4c`
- `0x180228178`
- `0x18025b100`
- `0x18025c93d`
- `0x1802f5370`
- `0x180307010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18022825a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180228273`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1802282db`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18022825a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180228273`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1802282db`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18022838b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1802283e3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18022838b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1802283e3`

## string_xrefs

- `0x1802282ba`: `CLSID`
- `0x180228253`: `xmlns`
- `0x18022826c`: `xmlns`

## pseudocode

```c
__int64 __fastcall SetElementProperties(__int64 *a1, __int64 *a2)
{
  int v4; // edi
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  wchar_t *v8; // rdi
  __int64 v9; // r14
  enum D2D1_PROPERTY_TYPE v10; // eax
  __int64 v11; // rcx
  enum D2D1_PROPERTY_TYPE v12; // r15d
  int v13; // eax
  int v14; // eax
  char *v15; // r9
  int v16; // eax
  int v17; // eax
  unsigned int v18; // ebx
  wchar_t *String1; // [rsp+30h] [rbp-50h] BYREF
  struct ID2D1Properties *v21; // [rsp+38h] [rbp-48h] BYREF
  int v22; // [rsp+40h] [rbp-40h] BYREF
  __int64 v23; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int16 *v24; // [rsp+50h] [rbp-30h] BYREF
  void *Block; // [rsp+58h] [rbp-28h] BYREF
  char v26; // [rsp+60h] [rbp-20h] BYREF
  __int64 v27; // [rsp+70h] [rbp-10h]

  v4 = (*(__int64 (__fastcall **)(__int64 *))(*a1 + 64))(a1);
  if ( v4 >= 0 )
  {
    while ( 1 )
    {
      if ( !(*(unsigned int (__fastcall **)(__int64 *))(*a1 + 152))(a1) )
      {
        v5 = *a1;
        v23 = 0;
        v22 = 0;
        v4 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, int *))(v5 + 120))(a1, &v23, &v22);
        if ( v4 < 0 )
          break;
        v6 = *a1;
        String1 = 0;
        v4 = (*(__int64 (__fastcall **)(__int64 *, wchar_t **, _QWORD))(v6 + 112))(a1, &String1, 0);
        if ( v4 < 0 )
          break;
        v7 = *a1;
        v24 = 0;
        v4 = (*(__int64 (__fastcall **)(__int64 *, unsigned __int16 **, _QWORD))(v7 + 128))(a1, &v24, 0);
        if ( v4 < 0 )
          break;
        if ( (unsigned int)_o__wcsicmp(L"xmlns", v23) )
        {
          if ( (unsigned int)_o__wcsicmp(L"xmlns", String1) )
          {
            v8 = String1;
            if ( wcsncmp_0(String1, L"in", 2u) )
            {
              if ( (*v8 != 105 || v8[1] != 100 || v8[2])
                && wcscmp_0(v8, L"CLSID")
                && (unsigned int)_o__wcsicmp(v8, L"name") )
              {
                v9 = (*(unsigned int (__fastcall **)(__int64 *, wchar_t *))(*a2 + 56))(a2, String1);
                v10 = (*(unsigned int (__fastcall **)(__int64 *, __int64))(*a2 + 48))(a2, v9);
                v11 = *a2;
                v12 = v10;
                v21 = 0;
                v13 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, struct ID2D1Properties **))(v11 + 104))(
                        a2,
                        (unsigned int)v9,
                        &v21);
                v4 = v13;
                if ( v13 < 0 )
                {
                  DoStackCapture(v13);
                  goto LABEL_26;
                }
                Block = 0;
                v27 = 16;
                v14 = DeserializePropertyData(v12, v21, v24, (struct CBuffer *)&Block);
                v4 = v14;
                if ( v14 < 0 )
                {
                  DoStackCapture(v14);
                  free(Block);
LABEL_26:
                  ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v21);
                  return (unsigned int)v4;
                }
                v15 = &v26;
                if ( (unsigned int)v27 > 0x10 )
                  v15 = (char *)Block;
                (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD, char *, _DWORD))(*a2 + 72))(
                  a2,
                  (unsigned int)v9,
                  0,
                  v15,
                  HIDWORD(v27));
                free(Block);
                ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v21);
              }
            }
          }
        }
      }
      v16 = (*(__int64 (__fastcall **)(__int64 *))(*a1 + 72))(a1);
      v4 = v16;
      if ( v16 < 0 )
        break;
      if ( v16 == 1 )
      {
        v17 = (*(__int64 (__fastcall **)(__int64 *))(*a1 + 88))(a1);
        v18 = v17;
        if ( v17 < 0 )
          DoStackCapture(v17);
        return v18;
      }
    }
  }
  DoStackCapture(v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180228178  mov     [rsp-28h+arg_10], rbx
0x18022817d  mov     [rsp-28h+arg_18], rsi
0x180228182  push    rbp
0x180228183  push    rdi
0x180228184  push    r12
0x180228186  push    r14
0x180228188  push    r15
0x18022818a  mov     rbp, rsp
0x18022818d  sub     rsp, 80h
0x180228194  mov     rax, cs:__security_cookie
0x18022819b  xor     rax, rsp
0x18022819e  mov     [rbp+var_8], rax
0x1802281a2  mov     rax, [rcx]
0x1802281a5  mov     rsi, rdx
0x1802281a8  mov     rbx, rcx
0x1802281ab  mov     rax, [rax+40h]
0x1802281af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802281b4  xor     r12d, r12d
0x1802281b7  mov     edi, eax
0x1802281b9  test    eax, eax
0x1802281bb  js      loc_1802283FD
0x1802281c1  mov     rax, [rbx]
0x1802281c4  mov     rcx, rbx
0x1802281c7  mov     rax, [rax+98h]
0x1802281ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802281d3  test    eax, eax
0x1802281d5  jnz     loc_18022839A
0x1802281db  mov     rax, [rbx]
0x1802281de  lea     r8, [rbp+var_40]
0x1802281e2  lea     rdx, [rbp+var_38]
0x1802281e6  mov     [rbp+var_38], r12
0x1802281ea  mov     rcx, rbx
0x1802281ed  mov     [rbp+var_40], r12d
0x1802281f1  mov     rax, [rax+78h]
0x1802281f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802281fa  mov     edi, eax
0x1802281fc  test    eax, eax
0x1802281fe  js      loc_1802283FD
0x180228204  mov     rax, [rbx]
0x180228207  lea     rdx, [rbp+String1]
0x18022820b  xor     r8d, r8d
0x18022820e  mov     [rbp+String1], r12
0x180228212  mov     rcx, rbx
0x180228215  mov     rax, [rax+70h]
0x180228219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022821e  mov     edi, eax
0x180228220  test    eax, eax
0x180228222  js      loc_1802283FD
0x180228228  mov     rax, [rbx]
0x18022822b  lea     rdx, [rbp+var_30]
0x18022822f  xor     r8d, r8d
0x180228232  mov     [rbp+var_30], r12
0x180228236  mov     rcx, rbx
0x180228239  mov     rax, [rax+80h]
0x180228240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180228245  mov     edi, eax
0x180228247  test    eax, eax
0x180228249  js      loc_1802283FD
0x18022824f  mov     rdx, [rbp+var_38]
0x180228253  lea     rcx, aXmlns; "xmlns"
0x18022825a  call    cs:__imp__o__wcsicmp
0x180228260  test    eax, eax
0x180228262  jz      loc_18022839A
0x180228268  mov     rdx, [rbp+String1]
0x18022826c  lea     rcx, aXmlns; "xmlns"
0x180228273  call    cs:__imp__o__wcsicmp
0x180228279  test    eax, eax
0x18022827b  jz      loc_18022839A
0x180228281  mov     rdi, [rbp+String1]
0x180228285  lea     rdx, aIn; "in"
0x18022828c  mov     rcx, rdi; String1
0x18022828f  mov     r8d, 2; MaxCount
0x180228295  call    wcsncmp_0
0x18022829a  test    eax, eax
0x18022829c  jz      loc_18022839A
0x1802282a2  cmp     word ptr [rdi], 69h ; 'i'
0x1802282a6  jnz     short loc_1802282BA
0x1802282a8  cmp     word ptr [rdi+2], 64h ; 'd'
0x1802282ad  jnz     short loc_1802282BA
0x1802282af  cmp     [rdi+4], r12w
0x1802282b4  jz      loc_18022839A
0x1802282ba  lea     rdx, aClsid_0; "CLSID"
0x1802282c1  mov     rcx, rdi; String1
0x1802282c4  call    wcscmp_0
0x1802282c9  test    eax, eax
0x1802282cb  jz      loc_18022839A
0x1802282d1  lea     rdx, aName_0; "name"
0x1802282d8  mov     rcx, rdi
0x1802282db  call    cs:__imp__o__wcsicmp
0x1802282e1  test    eax, eax
0x1802282e3  jz      loc_18022839A
0x1802282e9  mov     rax, [rsi]
0x1802282ec  mov     rcx, rsi
0x1802282ef  mov     rdx, [rbp+String1]
0x1802282f3  mov     rax, [rax+38h]
0x1802282f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802282fc  mov     rcx, [rsi]
0x1802282ff  mov     r14d, eax
0x180228302  mov     edx, r14d
0x180228305  mov     rax, [rcx+30h]
0x180228309  mov     rcx, rsi
0x18022830c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180228311  mov     rcx, [rsi]
0x180228314  lea     r8, [rbp+var_48]
0x180228318  mov     r15d, eax
0x18022831b  mov     [rbp+var_48], r12
0x18022831f  mov     edx, r14d
0x180228322  mov     rax, [rcx+68h]
0x180228326  mov     rcx, rsi
0x180228329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022832e  mov     edi, eax
0x180228330  test    eax, eax
0x180228332  js      loc_1802283EB
0x180228338  mov     r8, [rbp+var_30]; unsigned __int16 *
0x18022833c  lea     r9, [rbp+Block]; struct CBuffer *
0x180228340  mov     rdx, [rbp+var_48]; struct ID2D1Properties *
0x180228344  mov     ecx, r15d; enum D2D1_PROPERTY_TYPE
0x180228347  mov     [rbp+Block], r12
0x18022834b  mov     [rbp+var_10], 10h
0x180228353  call    ?DeserializePropertyData@@YAJW4D2D1_PROPERTY_TYPE@@PEAUID2D1Properties@@PEBGPEAVCBuffer@@@Z; DeserializePropertyData(D2D1_PROPERTY_TYPE,ID2D1Properties *,ushort const *,CBuffer *)
0x180228358  mov     edi, eax
0x18022835a  test    eax, eax
0x18022835c  js      short loc_1802283D8
0x18022835e  mov     ecx, dword ptr [rbp+var_10+4]
0x180228361  lea     r9, [rbp+var_20]
0x180228365  mov     rax, [rsi]
0x180228368  mov     edx, r14d
0x18022836b  cmp     dword ptr [rbp+var_10], 10h
0x18022836f  mov     [rsp+80h+var_60], ecx
0x180228373  mov     rcx, rsi
0x180228376  cmova   r9, [rbp+Block]
0x18022837b  xor     r8d, r8d
0x18022837e  mov     rax, [rax+48h]
0x180228382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180228387  mov     rcx, [rbp+Block]; Block
0x18022838b  call    cs:__imp_free
0x180228391  lea     rcx, [rbp+var_48]; void *
0x180228395  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x18022839a  mov     rax, [rbx]
0x18022839d  mov     rcx, rbx
0x1802283a0  mov     rax, [rax+48h]
0x1802283a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802283a9  mov     edi, eax
0x1802283ab  test    eax, eax
0x1802283ad  js      short loc_1802283FD
0x1802283af  cmp     eax, 1
0x1802283b2  jnz     loc_1802281C1
0x1802283b8  mov     rax, [rbx]
0x1802283bb  mov     rcx, rbx
0x1802283be  mov     rax, [rax+58h]
0x1802283c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802283c7  mov     ebx, eax
0x1802283c9  test    eax, eax
0x1802283cb  jns     short loc_1802283D4
0x1802283cd  mov     ecx, eax; int
0x1802283cf  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1802283d4  mov     eax, ebx
0x1802283d6  jmp     short loc_180228406
0x1802283d8  mov     ecx, eax; int
0x1802283da  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1802283df  mov     rcx, [rbp+Block]; Block
0x1802283e3  call    cs:__imp_free
0x1802283e9  jmp     short loc_1802283F2
0x1802283eb  mov     ecx, eax; int
0x1802283ed  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1802283f2  lea     rcx, [rbp+var_48]; void *
0x1802283f6  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1802283fb  jmp     short loc_180228404
0x1802283fd  mov     ecx, edi; int
0x1802283ff  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180228404  mov     eax, edi
0x180228406  mov     rcx, [rbp+var_8]
0x18022840a  xor     rcx, rsp; StackCookie
0x18022840d  call    __security_check_cookie
0x180228412  lea     r11, [rsp+80h+var_s0]
0x18022841a  mov     rbx, [r11+40h]
0x18022841e  mov     rsi, [r11+48h]
0x180228422  mov     rsp, r11
0x180228425  pop     r15
0x180228427  pop     r14
0x180228429  pop     r12
0x18022842b  pop     rdi
0x18022842c  pop     rbp
0x18022842d  retn
```
