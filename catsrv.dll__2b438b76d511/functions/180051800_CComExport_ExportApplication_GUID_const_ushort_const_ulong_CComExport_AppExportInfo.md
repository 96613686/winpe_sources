# CComExport::ExportApplication(_GUID const &,ushort const *,ulong,CComExport::AppExportInfo *)

- ea: `0x180051800`
- end: `0x180051a50`
- name: `?ExportApplication@CComExport@@IEAAJAEBU_GUID@@PEBGKPEAUAppExportInfo@1@@Z`
- size: `592`
- prototype: `int(CComExport *__hidden this, const struct _GUID *, const unsigned __int16 *, unsigned int, struct CComExport::AppExportInfo *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180051a60`
- `0x180051f20`

## callees

- `0x18001ec1c`
- `0x180024c00`
- `0x180050fd8`
- `0x180051800`
- `0x1800527c8`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `CLBCatQ!DowngradeAPL` at `0x1800519e3`
- `CLBCatQ!DowngradeAPL` at `0x1800519e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800518cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800518cc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005187f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005187f`

## pseudocode

```c
__int64 __fastcall CComExport::ExportApplication(
        CComExport *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        struct CComExport::AppExportInfo *a5)
{
  CComExport *v8; // rcx
  HRESULT Instance; // edi
  _WORD *v10; // rcx
  __int64 v11; // rax
  unsigned __int64 v12; // rbx
  unsigned __int16 *v13; // rax
  __int64 v14; // rbx
  unsigned __int16 *v15; // rax
  struct ISimpleTableDispenser *ppv; // [rsp+70h] [rbp-31h] BYREF
  __int64 v18; // [rsp+78h] [rbp-29h] BYREF
  __int64 v19; // [rsp+80h] [rbp-21h] BYREF
  unsigned __int16 v20[8]; // [rsp+88h] [rbp-19h] BYREF
  _OWORD v21[2]; // [rsp+98h] [rbp-9h]

  *(_OWORD *)v20 = *(_OWORD *)L" (Application Proxy)";
  v21[0] = *(_OWORD *)L"ation Proxy)";
  v18 = 0;
  ppv = 0;
  *(_OWORD *)((char *)v21 + 10) = *(_OWORD *)L" Proxy)";
  Instance = CoCreateInstance(&clsidSTDISP, 0, 1u, &IID_ISimpleTableDispenser, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    Instance = CComExport::GetApplicationProperties(v8, a2, ppv, a4, a5);
    if ( Instance >= 0 )
    {
      if ( (a4 & 0x20) == 0 )
        goto LABEL_23;
      v10 = (_WORD *)*((_QWORD *)a5 + 2);
      v11 = -1;
      do
        ++v11;
      while ( v10[v11] );
      v12 = v11 + 22;
      v13 = (unsigned __int16 *)CoTaskMemRealloc(v10, 2 * (v11 + 22));
      if ( !v13 )
        goto LABEL_7;
      *((_QWORD *)a5 + 2) = v13;
      Instance = StringCchCatW(v13, v12, v20);
      if ( Instance >= 0 )
      {
LABEL_23:
        v19 = 0;
        Instance = ATL::CComObject<CAppExport>::CreateInstance(&v19);
        if ( Instance >= 0 )
        {
          v14 = v19;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
          Instance = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v14)(v14, &IID_IAppExport, &v18);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          if ( Instance >= 0 )
          {
            v15 = AllocString(a3);
            *((_QWORD *)a5 + 10) = v15;
            if ( !v15 )
            {
LABEL_7:
              Instance = -2147024882;
              goto LABEL_16;
            }
            Instance = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, const unsigned __int16 *, _QWORD, char *, char *, char *, char *, char *, char *, char *, char *))(*(_QWORD *)v18 + 24LL))(
                         v18,
                         a2,
                         a3,
                         a4,
                         (char *)a5 + 56,
                         (char *)a5 + 48,
                         (char *)a5 + 72,
                         (char *)a5 + 64,
                         (char *)a5 + 96,
                         (char *)a5 + 88,
                         (char *)a5 + 112,
                         (char *)a5 + 104);
            if ( Instance >= 0 )
            {
              if ( (a4 & 0x80u) == 0 || (Instance = DowngradeAPL(a3), Instance >= 0) )
                *(struct _GUID *)a5 = *a2;
            }
          }
        }
      }
    }
  }
LABEL_16:
  if ( ppv )
  {
    (*(void (__fastcall **)(struct ISimpleTableDispenser *))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180051800  mov     [rsp-8+arg_0], rbx
0x180051805  push    rbp
0x180051806  push    rsi
0x180051807  push    rdi
0x180051808  push    r12
0x18005180a  push    r13
0x18005180c  push    r14
0x18005180e  push    r15
0x180051810  lea     rbp, [rsp-1Fh]
0x180051815  sub     rsp, 0C0h
0x18005181c  mov     rax, cs:__security_cookie
0x180051823  xor     rax, rsp
0x180051826  mov     [rbp+4Fh+var_38], rax
0x18005182a  movups  xmm0, xmmword ptr cs:aApplicationPro; " (Application Proxy)"
0x180051831  mov     r14, [rbp+4Fh+arg_20]
0x180051835  xor     esi, esi
0x180051837  movups  xmm1, xmmword ptr cs:aApplicationPro+10h; "ation Proxy)"
0x18005183e  mov     r15d, r9d
0x180051841  mov     r12, r8
0x180051844  movups  xmmword ptr [rbp+4Fh+var_68], xmm0
0x180051848  mov     r13, rdx
0x18005184b  lea     rax, [rbp+4Fh+var_80]
0x18005184f  movups  xmm0, xmmword ptr cs:aApplicationPro+1Ah; " Proxy)"
0x180051856  lea     r9, IID_ISimpleTableDispenser; riid
0x18005185d  xor     edx, edx; pUnkOuter
0x18005185f  movups  xmmword ptr [rbp+4Fh+var_58], xmm1
0x180051863  lea     r8d, [rsi+1]; dwClsContext
0x180051867  mov     [rbp+4Fh+var_78], rsi
0x18005186b  lea     rcx, clsidSTDISP; rclsid
0x180051872  mov     [rbp+4Fh+var_80], rsi
0x180051876  movups  xmmword ptr [rbp+4Fh+var_58+0Ah], xmm0
0x18005187a  mov     [rsp+0F0h+ppv], rax; ppv
0x18005187f  call    cs:__imp_CoCreateInstance
0x180051885  mov     edi, eax
0x180051887  test    eax, eax
0x180051889  js      loc_1800519F9
0x18005188f  mov     r8, [rbp+4Fh+var_80]; struct ISimpleTableDispenser *
0x180051893  mov     r9d, r15d; unsigned int
0x180051896  mov     rdx, r13; struct _GUID *
0x180051899  mov     [rsp+0F0h+ppv], r14; struct CComExport::AppExportInfo *
0x18005189e  call    ?GetApplicationProperties@CComExport@@IEAAJAEBU_GUID@@PEAUISimpleTableDispenser@@KPEAUAppExportInfo@1@@Z; CComExport::GetApplicationProperties(_GUID const &,ISimpleTableDispenser *,ulong,CComExport::AppExportInfo *)
0x1800518a3  mov     edi, eax
0x1800518a5  test    eax, eax
0x1800518a7  js      loc_1800519F9
0x1800518ad  test    r15b, 20h
0x1800518b1  jz      short loc_1800518FE
0x1800518b3  mov     rcx, [r14+10h]; pv
0x1800518b7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800518bb  inc     rax
0x1800518be  cmp     [rcx+rax*2], si
0x1800518c2  jnz     short loc_1800518BB
0x1800518c4  lea     rbx, [rax+16h]
0x1800518c8  lea     rdx, [rbx+rbx]; cb
0x1800518cc  call    cs:__imp_CoTaskMemRealloc
0x1800518d2  test    rax, rax
0x1800518d5  jnz     short loc_1800518E1
0x1800518d7  mov     edi, 8007000Eh
0x1800518dc  jmp     loc_1800519F9
0x1800518e1  lea     r8, [rbp+4Fh+var_68]; unsigned __int16 *
0x1800518e5  mov     [r14+10h], rax
0x1800518e9  mov     rdx, rbx; unsigned __int64
0x1800518ec  mov     rcx, rax; unsigned __int16 *
0x1800518ef  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800518f4  mov     edi, eax
0x1800518f6  test    eax, eax
0x1800518f8  js      loc_1800519F9
0x1800518fe  lea     rcx, [rbp+4Fh+var_70]
0x180051902  mov     [rbp+4Fh+var_70], rsi
0x180051906  call    ?CreateInstance@?$CComObject@VCAppExport@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CAppExport>::CreateInstance(ATL::CComObject<CAppExport> * *)
0x18005190b  mov     edi, eax
0x18005190d  test    eax, eax
0x18005190f  js      loc_1800519F9
0x180051915  mov     rbx, [rbp+4Fh+var_70]
0x180051919  mov     rcx, rbx
0x18005191c  mov     rax, [rbx]
0x18005191f  mov     rax, [rax+8]
0x180051923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051928  mov     rax, [rbx]
0x18005192b  lea     r8, [rbp+4Fh+var_78]
0x18005192f  lea     rdx, IID_IAppExport
0x180051936  mov     rcx, rbx
0x180051939  mov     rax, [rax]
0x18005193c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051941  mov     edi, eax
0x180051943  mov     rcx, rbx
0x180051946  mov     rax, [rbx]
0x180051949  mov     rax, [rax+10h]
0x18005194d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051952  test    edi, edi
0x180051954  js      loc_1800519F9
0x18005195a  mov     rcx, r12; Src
0x18005195d  call    ?AllocString@@YAPEAGPEBG@Z; AllocString(ushort const *)
0x180051962  mov     [r14+50h], rax
0x180051966  test    rax, rax
0x180051969  jz      loc_1800518D7
0x18005196f  mov     rsi, [rbp+4Fh+var_78]
0x180051973  lea     r9, [r14+60h]
0x180051977  lea     rcx, [r14+68h]
0x18005197b  mov     [rsp+0F0h+var_98], rcx
0x180051980  lea     rdx, [r14+70h]
0x180051984  mov     [rsp+0F0h+var_A0], rdx
0x180051989  lea     r8, [r14+58h]
0x18005198d  mov     rax, [rsi]
0x180051990  lea     r10, [r14+40h]
0x180051994  mov     [rsp+0F0h+var_A8], r8
0x180051999  lea     r11, [r14+48h]
0x18005199d  mov     [rsp+0F0h+var_B0], r9
0x1800519a2  lea     rbx, [r14+30h]
0x1800519a6  mov     [rsp+0F0h+var_B8], r10
0x1800519ab  lea     rdi, [r14+38h]
0x1800519af  mov     rax, [rax+18h]
0x1800519b3  mov     r9d, r15d
0x1800519b6  mov     [rsp+0F0h+var_C0], r11
0x1800519bb  mov     r8, r12
0x1800519be  mov     [rsp+0F0h+var_C8], rbx
0x1800519c3  mov     rdx, r13
0x1800519c6  mov     rcx, rsi
0x1800519c9  mov     [rsp+0F0h+ppv], rdi
0x1800519ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800519d3  xor     esi, esi
0x1800519d5  mov     edi, eax
0x1800519d7  test    eax, eax
0x1800519d9  js      short loc_1800519F9
0x1800519db  test    r15b, r15b
0x1800519de  jns     short loc_1800519EF
0x1800519e0  mov     rcx, r12
0x1800519e3  call    cs:__imp_?DowngradeAPL@@YAJPEBG@Z; DowngradeAPL(ushort const *)
0x1800519e9  mov     edi, eax
0x1800519eb  test    eax, eax
0x1800519ed  js      short loc_1800519F9
0x1800519ef  movups  xmm0, xmmword ptr [r13+0]
0x1800519f4  movdqu  xmmword ptr [r14], xmm0
0x1800519f9  mov     rcx, [rbp+4Fh+var_80]
0x1800519fd  test    rcx, rcx
0x180051a00  jz      short loc_180051A12
0x180051a02  mov     rax, [rcx]
0x180051a05  mov     rax, [rax+10h]
0x180051a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051a0e  mov     [rbp+4Fh+var_80], rsi
0x180051a12  mov     rcx, [rbp+4Fh+var_78]
0x180051a16  test    rcx, rcx
0x180051a19  jz      short loc_180051A27
0x180051a1b  mov     rax, [rcx]
0x180051a1e  mov     rax, [rax+10h]
0x180051a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051a27  mov     eax, edi
0x180051a29  mov     rcx, [rbp+4Fh+var_38]
0x180051a2d  xor     rcx, rsp; StackCookie
0x180051a30  call    __security_check_cookie
0x180051a35  mov     rbx, [rsp+0F0h+arg_0]
0x180051a3d  add     rsp, 0C0h
0x180051a44  pop     r15
0x180051a46  pop     r14
0x180051a48  pop     r13
0x180051a4a  pop     r12
0x180051a4c  pop     rdi
0x180051a4d  pop     rsi
0x180051a4e  pop     rbp
0x180051a4f  retn
```
