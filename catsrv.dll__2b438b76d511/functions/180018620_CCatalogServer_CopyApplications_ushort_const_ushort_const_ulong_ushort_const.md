# CCatalogServer::CopyApplications(ushort const *,ushort const *,ulong,ushort const * *)

- ea: `0x180018620`
- end: `0x180018952`
- name: `?CopyApplications@CCatalogServer@@UEAAJPEBG0KPEAPEBG@Z`
- size: `818`
- prototype: `__int64 __fastcall(CCatalogServer *this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180017af4`
- `0x180017b90`
- `0x18001854c`
- `0x180018620`
- `0x18001ece0`
- `0x18002f158`
- `0x180031000`
- `0x1800312b8`
- `0x180031b4c`
- `0x180031cdc`
- `0x180055502`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `comsvcs!GetObjectContext` at `0x1800188c1`
- `comsvcs!GetObjectContext` at `0x180055f50`
- `comsvcs!GetObjectContext` at `0x1800188c1`
- `comsvcs!GetObjectContext` at `0x180055f50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018889`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018897`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018889`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018897`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018788`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018818`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018788`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018818`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800186f1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800186f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCatalogServer::CopyApplications(
        CCatalogServer *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        const unsigned __int16 **a5)
{
  unsigned __int64 v5; // r14
  __int64 result; // rax
  struct _GUID *v9; // rsi
  __int64 i; // rdi
  const unsigned __int16 *v11; // rdx
  CAppCopy *v12; // rax
  CAppCopy *v13; // rdi
  int ObjectContext; // eax
  __int64 v15; // rdx
  _QWORD *v16; // rcx
  __int64 v17; // rax
  HRESULT v18; // eax
  HRESULT Instance; // [rsp+30h] [rbp-88h]
  _QWORD *v20; // [rsp+38h] [rbp-80h] BYREF
  struct ISimpleTableDispenser *ppv; // [rsp+40h] [rbp-78h] BYREF
  int v22; // [rsp+48h] [rbp-70h]
  struct _GUID v23; // [rsp+50h] [rbp-68h] BYREF
  struct _GUID Buf1; // [rsp+60h] [rbp-58h] BYREF
  struct _GUID Buf2; // [rsp+70h] [rbp-48h] BYREF

  v5 = a4;
  if ( !*((_DWORD *)this + 34) )
    return 2148598828LL;
  if ( !a2 || !a3 )
    return 2147942487LL;
  v20 = 0;
  ppv = 0;
  Buf1 = 0;
  Buf2 = 0;
  if ( !a4 )
    return 0;
  if ( !a5 )
    return 2147500035LL;
  result = TxInitialize();
  if ( (int)result >= 0 )
  {
    UTSemReadWrite::LockWrite((UTSemReadWrite *)&g_semRW);
    Instance = CoCreateInstance(&CLSID_STDispenser, 0, 0x17u, &IID_ISimpleTableDispenser, (LPVOID *)&ppv);
    if ( Instance >= 0 )
    {
      Instance = ResolvePartitionIdFromName(ppv, a2, &Buf1);
      if ( Instance >= 0 )
      {
        Instance = ResolvePartitionIdFromName(ppv, a3, &Buf2);
        if ( Instance >= 0 )
        {
          if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
          {
            Instance = -2146367477;
          }
          else
          {
            v9 = (struct _GUID *)CoTaskMemAlloc(saturated_mul(v5, 0x10u));
            v23 = 0;
            if ( !v9 )
              Instance = -2147024882;
            for ( i = 0; ; i = (unsigned int)(i + 1) )
            {
              v22 = i;
              if ( Instance < 0 || (unsigned int)i >= (unsigned int)v5 )
                break;
              v11 = a5[i];
              if ( v11 )
              {
                Instance = ResolveAppIdFromName(ppv, v11, &v9[(unsigned int)i], &v23);
                if ( Instance >= 0 && memcmp_0(&v23, &Buf1, 0x10u) )
                  Instance = -2146367477;
              }
              else
              {
                Instance = -2147467261;
              }
            }
            v12 = (CAppCopy *)CoTaskMemAlloc(0xB0u);
            if ( v12 )
              v13 = CAppCopy::CAppCopy(v12);
            else
              v13 = 0;
            if ( !v13 )
              Instance = -2147024882;
            if ( Instance >= 0 )
            {
              *(struct _GUID *)v13 = Buf1;
              *((struct _GUID *)v13 + 1) = Buf2;
              *((_DWORD *)v13 + 8) = v5;
              *((_QWORD *)v13 + 5) = v9;
              Instance = CAppCopy::CopyApplications((LPVOID *)v13);
              CAppCopy::~CAppCopy(v13);
              CoTaskMemFree(v13);
            }
            if ( v9 )
              CoTaskMemFree(v9);
          }
        }
      }
      (*(void (__fastcall **)(struct ISimpleTableDispenser *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    UTSemReadWrite::UnlockWrite((UTSemReadWrite *)&g_semRW);
    ObjectContext = GetObjectContext(&v20);
    v15 = (unsigned int)ObjectContext;
    v16 = v20;
    if ( ObjectContext >= 0 && v20 )
    {
      v17 = *v20;
      if ( Instance >= 0 )
      {
        v18 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(v17 + 32))(v20, v15);
        v16 = v20;
LABEL_44:
        Instance = v18;
        goto LABEL_45;
      }
      (*(void (__fastcall **)(_QWORD *, __int64))(v17 + 40))(v20, v15);
      v16 = v20;
    }
    else if ( ObjectContext != -2147164156 )
    {
      v18 = Instance;
      if ( Instance >= 0 )
        v18 = v15;
      goto LABEL_44;
    }
LABEL_45:
    if ( v16 )
      (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
    return (unsigned int)Instance;
  }
  return result;
}

```

## disassembly

```asm
0x180018620  push    rsi
0x180018622  push    rdi
0x180018623  push    r12
0x180018625  push    r14
0x180018627  push    r15
0x180018629  sub     rsp, 90h
0x180018630  mov     rax, cs:__security_cookie
0x180018637  xor     rax, rsp
0x18001863a  mov     [rsp+0B8h+var_38], rax
0x180018642  mov     r14d, r9d
0x180018645  mov     rsi, r8
0x180018648  mov     rdi, rdx
0x18001864b  mov     r15, [rsp+0B8h+arg_20]
0x180018653  cmp     dword ptr [rcx+88h], 0
0x18001865a  jnz     short loc_180018666
0x18001865c  mov     eax, 8011042Ch
0x180018661  jmp     loc_180018932
0x180018666  test    rdi, rdi
0x180018669  jz      loc_18001892D
0x18001866f  test    rsi, rsi
0x180018672  jz      loc_18001892D
0x180018678  mov     [rsp+0B8h+var_80], 0
0x180018681  mov     [rsp+0B8h+var_78], 0
0x18001868a  xorps   xmm0, xmm0
0x18001868d  movups  [rsp+0B8h+Buf1], xmm0
0x180018692  xorps   xmm1, xmm1
0x180018695  movups  [rsp+0B8h+Buf2], xmm1
0x18001869a  test    r9d, r9d
0x18001869d  jnz     short loc_1800186A6
0x18001869f  xor     eax, eax
0x1800186a1  jmp     loc_180018932
0x1800186a6  test    r15, r15
0x1800186a9  jnz     short loc_1800186B5
0x1800186ab  mov     eax, 80004003h
0x1800186b0  jmp     loc_180018932
0x1800186b5  call    ?TxInitialize@@YAJXZ; TxInitialize(void)
0x1800186ba  mov     [rsp+0B8h+var_88], eax
0x1800186be  test    eax, eax
0x1800186c0  js      loc_180018932
0x1800186c6  lea     rcx, ?g_semRW@@3VUTSemReadWrite@@A; this
0x1800186cd  call    ?LockWrite@UTSemReadWrite@@QEAAXXZ; UTSemReadWrite::LockWrite(void)
0x1800186d2  nop
0x1800186d3  lea     rax, [rsp+0B8h+var_78]
0x1800186d8  mov     [rsp+0B8h+ppv], rax; ppv
0x1800186dd  lea     r9, IID_ISimpleTableDispenser; riid
0x1800186e4  xor     edx, edx; pUnkOuter
0x1800186e6  lea     r8d, [rdx+17h]; dwClsContext
0x1800186ea  lea     rcx, CLSID_STDispenser; rclsid
0x1800186f1  call    cs:__imp_CoCreateInstance
0x1800186f7  mov     [rsp+0B8h+var_88], eax
0x1800186fb  mov     eax, [rsp+0B8h+var_88]
0x1800186ff  test    eax, eax
0x180018701  js      loc_1800188AE
0x180018707  lea     r8, [rsp+0B8h+Buf1]; struct _GUID *
0x18001870c  mov     rdx, rdi; unsigned __int16 *
0x18001870f  mov     rcx, [rsp+0B8h+var_78]; struct ISimpleTableDispenser *
0x180018714  call    ?ResolvePartitionIdFromName@@YAJPEAUISimpleTableDispenser@@PEBGPEAU_GUID@@@Z; ResolvePartitionIdFromName(ISimpleTableDispenser *,ushort const *,_GUID *)
0x180018719  mov     [rsp+0B8h+var_88], eax
0x18001871d  mov     eax, [rsp+0B8h+var_88]
0x180018721  test    eax, eax
0x180018723  js      loc_18001889D
0x180018729  lea     r8, [rsp+0B8h+Buf2]; struct _GUID *
0x18001872e  mov     rdx, rsi; unsigned __int16 *
0x180018731  mov     rcx, [rsp+0B8h+var_78]; struct ISimpleTableDispenser *
0x180018736  call    ?ResolvePartitionIdFromName@@YAJPEAUISimpleTableDispenser@@PEBGPEAU_GUID@@@Z; ResolvePartitionIdFromName(ISimpleTableDispenser *,ushort const *,_GUID *)
0x18001873b  mov     [rsp+0B8h+var_88], eax
0x18001873f  mov     eax, [rsp+0B8h+var_88]
0x180018743  test    eax, eax
0x180018745  js      loc_18001889D
0x18001874b  mov     r12d, 10h
0x180018751  mov     r8d, r12d; Size
0x180018754  lea     rdx, [rsp+0B8h+Buf2]; Buf2
0x180018759  lea     rcx, [rsp+0B8h+Buf1]; Buf1
0x18001875e  call    memcmp_0
0x180018763  test    eax, eax
0x180018765  jnz     short loc_180018774
0x180018767  mov     [rsp+0B8h+var_88], 8011080Bh
0x18001876f  jmp     loc_18001889D
0x180018774  mov     rax, r12
0x180018777  mul     r14
0x18001877a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180018781  cmovb   rax, rcx
0x180018785  mov     rcx, rax; cb
0x180018788  call    cs:__imp_CoTaskMemAlloc
0x18001878e  mov     rsi, rax
0x180018791  xorps   xmm0, xmm0
0x180018794  movups  xmmword ptr [rsp+0B8h+var_68.Data1], xmm0
0x180018799  test    rax, rax
0x18001879c  jnz     short loc_1800187A6
0x18001879e  mov     [rsp+0B8h+var_88], 8007000Eh
0x1800187a6  xor     edi, edi
0x1800187a8  mov     [rsp+0B8h+var_70], edi
0x1800187ac  mov     eax, [rsp+0B8h+var_88]
0x1800187b0  test    eax, eax
0x1800187b2  js      short loc_180018813
0x1800187b4  cmp     edi, r14d
0x1800187b7  jnb     short loc_180018813
0x1800187b9  mov     r8d, edi
0x1800187bc  mov     rdx, [r15+rdi*8]; unsigned __int16 *
0x1800187c0  test    rdx, rdx
0x1800187c3  jnz     short loc_1800187CF
0x1800187c5  mov     [rsp+0B8h+var_88], 80004003h
0x1800187cd  jmp     short loc_18001880F
0x1800187cf  shl     r8, 4
0x1800187d3  add     r8, rsi; struct _GUID *
0x1800187d6  lea     r9, [rsp+0B8h+var_68]; struct _GUID *
0x1800187db  mov     rcx, [rsp+0B8h+var_78]; struct ISimpleTableDispenser *
0x1800187e0  call    ?ResolveAppIdFromName@@YAJPEAUISimpleTableDispenser@@PEBGPEAU_GUID@@2@Z; ResolveAppIdFromName(ISimpleTableDispenser *,ushort const *,_GUID *,_GUID *)
0x1800187e5  mov     [rsp+0B8h+var_88], eax
0x1800187e9  mov     eax, [rsp+0B8h+var_88]
0x1800187ed  test    eax, eax
0x1800187ef  js      short loc_18001880F
0x1800187f1  mov     r8, r12; Size
0x1800187f4  lea     rdx, [rsp+0B8h+Buf1]; Buf2
0x1800187f9  lea     rcx, [rsp+0B8h+var_68]; Buf1
0x1800187fe  call    memcmp_0
0x180018803  test    eax, eax
0x180018805  jz      short loc_18001880F
0x180018807  mov     [rsp+0B8h+var_88], 8011080Bh
0x18001880f  inc     edi
0x180018811  jmp     short loc_1800187A8
0x180018813  mov     ecx, 0B0h; cb
0x180018818  call    cs:__imp_CoTaskMemAlloc
0x18001881e  test    rax, rax
0x180018821  jz      short loc_180018830
0x180018823  mov     rcx, rax; this
0x180018826  call    ??0CAppCopy@@QEAA@XZ; CAppCopy::CAppCopy(void)
0x18001882b  mov     rdi, rax
0x18001882e  jmp     short loc_180018832
0x180018830  xor     edi, edi
0x180018832  test    rdi, rdi
0x180018835  jnz     short loc_18001883F
0x180018837  mov     [rsp+0B8h+var_88], 8007000Eh
0x18001883f  mov     eax, [rsp+0B8h+var_88]
0x180018843  test    eax, eax
0x180018845  js      short loc_18001888F
0x180018847  movups  xmm0, [rsp+0B8h+Buf1]
0x18001884c  movdqu  xmmword ptr [rdi], xmm0
0x180018850  movups  xmm1, [rsp+0B8h+Buf2]
0x180018855  movdqu  xmmword ptr [rdi+10h], xmm1
0x18001885a  mov     [rdi+20h], r14d
0x18001885e  mov     [rdi+28h], rsi
0x180018862  mov     [rsp+0B8h+var_88], 0
0x18001886a  mov     eax, [rsp+0B8h+var_88]
0x18001886e  test    eax, eax
0x180018870  js      short loc_18001887E
0x180018872  mov     rcx, rdi; this
0x180018875  call    ?CopyApplications@CAppCopy@@QEAAJXZ; CAppCopy::CopyApplications(void)
0x18001887a  mov     [rsp+0B8h+var_88], eax
0x18001887e  mov     rcx, rdi; this
0x180018881  call    ??1CAppCopy@@QEAA@XZ; CAppCopy::~CAppCopy(void)
0x180018886  mov     rcx, rdi; pv
0x180018889  call    cs:__imp_CoTaskMemFree
0x18001888f  test    rsi, rsi
0x180018892  jz      short loc_18001889D
0x180018894  mov     rcx, rsi; pv
0x180018897  call    cs:__imp_CoTaskMemFree
0x18001889d  mov     rcx, [rsp+0B8h+var_78]
0x1800188a2  mov     rax, [rcx]
0x1800188a5  mov     rax, [rax+10h]
0x1800188a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188ae  jmp     short $+2
0x1800188b0  lea     rcx, ?g_semRW@@3VUTSemReadWrite@@A; this
0x1800188b7  call    ?UnlockWrite@UTSemReadWrite@@QEAAXXZ; UTSemReadWrite::UnlockWrite(void)
0x1800188bc  lea     rcx, [rsp+0B8h+var_80]
0x1800188c1  call    cs:__imp_GetObjectContext
0x1800188c7  mov     edx, eax
0x1800188c9  mov     rcx, [rsp+0B8h+var_80]
0x1800188ce  test    eax, eax
0x1800188d0  js      short loc_180018901
0x1800188d2  test    rcx, rcx
0x1800188d5  jz      short loc_180018901
0x1800188d7  mov     rax, [rcx]
0x1800188da  cmp     [rsp+0B8h+var_88], 0
0x1800188df  jl      short loc_1800188F1
0x1800188e1  mov     rax, [rax+20h]
0x1800188e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188ea  mov     rcx, [rsp+0B8h+var_80]
0x1800188ef  jmp     short loc_180018912
0x1800188f1  mov     rax, [rax+28h]
0x1800188f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188fa  mov     rcx, [rsp+0B8h+var_80]
0x1800188ff  jmp     short loc_180018916
0x180018901  cmp     edx, 8004E004h
0x180018907  jz      short loc_180018916
0x180018909  mov     eax, [rsp+0B8h+var_88]
0x18001890d  test    eax, eax
0x18001890f  cmovns  eax, edx
0x180018912  mov     [rsp+0B8h+var_88], eax
0x180018916  test    rcx, rcx
0x180018919  jz      short loc_180018927
0x18001891b  mov     rax, [rcx]
0x18001891e  mov     rax, [rax+10h]
0x180018922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018927  mov     eax, [rsp+0B8h+var_88]
0x18001892b  jmp     short loc_180018932
0x18001892d  mov     eax, 80070057h
0x180018932  mov     rcx, [rsp+0B8h+var_38]
0x18001893a  xor     rcx, rsp; StackCookie
0x18001893d  call    __security_check_cookie
0x180018942  add     rsp, 90h
0x180018949  pop     r15
0x18001894b  pop     r14
0x18001894d  pop     r12
0x18001894f  pop     rdi
0x180018950  pop     rsi
0x180018951  retn
0x180055f1d  push    rbp
0x180055f1f  sub     rsp, 30h
0x180055f23  mov     rbp, rdx
0x180055f26  lea     rdx, [rbp+30h]; int *
0x180055f2a  call    ?UnhandledExceptionFilter@CCatalogServer@@CAKPEAU_EXCEPTION_POINTERS@@AEAJ@Z; CCatalogServer::UnhandledExceptionFilter(_EXCEPTION_POINTERS *,long &)
0x180055f2f  nop
0x180055f30  add     rsp, 30h
0x180055f34  pop     rbp
0x180055f35  retn
0x180055f37  push    rbp
0x180055f39  sub     rsp, 30h
0x180055f3d  mov     rbp, rdx
0x180055f40  lea     rcx, ?g_semRW@@3VUTSemReadWrite@@A; this
0x180055f47  call    ?UnlockWrite@UTSemReadWrite@@QEAAXXZ; UTSemReadWrite::UnlockWrite(void)
0x180055f4c  lea     rcx, [rbp+38h]
0x180055f50  call    cs:__imp_GetObjectContext
0x180055f56  nop
0x180055f57  mov     rcx, [rbp+38h]
0x180055f5b  test    eax, eax
0x180055f5d  js      short loc_180055F80
0x180055f5f  test    rcx, rcx
0x180055f62  jz      short loc_180055F92
0x180055f64  mov     rax, [rcx]
0x180055f67  cmp     dword ptr [rbp+30h], 0
0x180055f6b  jl      short loc_180055F73
0x180055f6d  mov     rax, [rax+20h]
0x180055f71  jmp     short loc_180055F77
0x180055f73  mov     rax, [rax+28h]
0x180055f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f7c  mov     rcx, [rbp+38h]
0x180055f80  test    rcx, rcx
0x180055f83  jz      short loc_180055F92
0x180055f85  mov     rax, [rcx]
0x180055f88  mov     rax, [rax+10h]
0x180055f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f91  nop
0x180055f92  add     rsp, 30h
0x180055f96  pop     rbp
0x180055f97  retn
```
