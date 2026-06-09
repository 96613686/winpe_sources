# CSubscription::StoreInternal(int,int,IEventSystemTier2 *)

- ea: `0x1800130a0`
- end: `0x1800139df`
- name: `?StoreInternal@CSubscription@@AEAAJHHPEAUIEventSystemTier2@@@Z`
- size: `2367`
- prototype: `int(CSubscription *__hidden this, int, int, struct IEventSystemTier2 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180021680`

## callees

- `0x180003d54`
- `0x180008938`
- `0x1800130a0`
- `0x1800139e8`
- `0x180013cb8`
- `0x180014e70`
- `0x18001c9f0`
- `0x18003f080`
- `0x1800434ae`
- `0x1800434c6`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800137b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800137b8`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800132c1`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800132c1`
- `OLEAUT32!__imp_SysAllocString` at `0x180013241`
- `OLEAUT32!__imp_SysAllocString` at `0x180013289`
- `OLEAUT32!__imp_SysAllocString` at `0x18001385c`
- `OLEAUT32!__imp_SysAllocString` at `0x180013900`
- `OLEAUT32!__imp_SysAllocString` at `0x180013241`
- `OLEAUT32!__imp_SysAllocString` at `0x180013289`
- `OLEAUT32!__imp_SysAllocString` at `0x18001385c`
- `OLEAUT32!__imp_SysAllocString` at `0x180013900`
- `OLEAUT32!__imp_SysFreeString` at `0x1800138af`
- `OLEAUT32!__imp_SysFreeString` at `0x180044310`
- `OLEAUT32!__imp_SysFreeString` at `0x1800138af`
- `OLEAUT32!__imp_SysFreeString` at `0x180044310`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013557`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013565`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013573`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013581`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013557`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013565`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013573`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013581`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001327e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800138f5`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001395a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001327e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800138f5`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001395a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800131df`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180013683`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800131df`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180013683`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180013359`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180013359`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001329b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013549`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013912`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001399d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001329b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013549`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013912`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001399d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001382d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001382d`

## string_xrefs

- `0x1800131fb`: `com\complus\src\events\tier1\subscription.cpp`
- `0x18001373f`: `com\complus\src\events\tier1\subscription.cpp`
- `0x180013766`: `com\complus\src\events\tier1\subscription.cpp`
- `0x1800137a7`: `com\complus\src\events\tier1\subscription.cpp`
- `0x180013848`: `com\complus\src\events\tier1\subscription.cpp`
- `0x180013883`: `com\complus\src\events\tier1\subscription.cpp`
- `0x1800138cc`: `com\complus\src\events\tier1\subscription.cpp`
- `0x180013788`: `com\complus\src\events\tier1\utilities.cpp`

## pseudocode

```c
int __fastcall CSubscription::StoreInternal(CSubscription *this, int a2, int a3, struct IEventSystemTier2 *a4)
{
  int result; // eax
  HRESULT v8; // eax
  const OLECHAR *v9; // rcx
  BSTR v10; // rax
  IUnknown *v11; // rcx
  unsigned int v12; // r9d
  struct tagPROPVARIANT *v13; // r12
  struct tagPROPVARIANT *v14; // r13
  __int64 v15; // rcx
  int v16; // eax
  BOOL v17; // edi
  LPVOID *v18; // r8
  int v19; // edi
  HRESULT v20; // eax
  bool v21; // sf
  OLECHAR *v22; // rdi
  int v23; // r12d
  int v24; // edi
  LPOLESTR lpsz; // [rsp+A8h] [rbp-178h] BYREF
  BOOL v26; // [rsp+B0h] [rbp-170h] BYREF
  int v27; // [rsp+B4h] [rbp-16Ch] BYREF
  int v28; // [rsp+BCh] [rbp-164h]
  WINBOOL IsMember; // [rsp+C0h] [rbp-160h] BYREF
  IUnknown *pProxy; // [rsp+C8h] [rbp-158h] BYREF
  struct IEventClass2 *v31; // [rsp+D0h] [rbp-150h] BYREF
  struct tagPROPVARIANT *p_pvar; // [rsp+D8h] [rbp-148h]
  int v33; // [rsp+E0h] [rbp-140h]
  LPOLESTR v34; // [rsp+E8h] [rbp-138h] BYREF
  struct tagPROPVARIANT *v35; // [rsp+F0h] [rbp-130h]
  CSubscription *v36; // [rsp+F8h] [rbp-128h]
  struct tagPROPVARIANT pvar; // [rsp+100h] [rbp-120h] BYREF
  struct tagPROPVARIANT v38; // [rsp+118h] [rbp-108h] BYREF
  struct tagPROPVARIANT v39; // [rsp+130h] [rbp-F0h] BYREF
  struct tagPROPVARIANT v40; // [rsp+148h] [rbp-D8h] BYREF
  LPVOID pv[2]; // [rsp+160h] [rbp-C0h] BYREF
  GUID Buf2; // [rsp+170h] [rbp-B0h] BYREF
  OLECHAR sz[40]; // [rsp+188h] [rbp-98h] BYREF

  v33 = a3;
  v36 = this;
  v31 = 0;
  v34 = 0;
  if ( !*((_WORD *)this + 20)
    || !*((_WORD *)this + 32)
    || !*((_WORD *)this + 56) && !*((_WORD *)this + 44) && !*((_WORD *)this + 152)
    || !*((_WORD *)this + 80) && !*((_WORD *)this + 176) && (!*((_QWORD *)this + 59) || !*((_DWORD *)this + 120)) )
  {
    return -2147024809;
  }
  Buf2 = GUID_NULL;
  if ( *((_WORD *)this + 212) )
  {
    v8 = CLSIDFromString(*((LPCOLESTR *)this + 54), &Buf2);
    if ( v8 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\subscription.cpp", 0x7BAu, 0x10u, v8);
  }
  else
  {
    Buf2 = GUID_NULL;
  }
  if ( *((_DWORD *)this + 166) )
  {
    if ( !a2 )
    {
LABEL_9:
      if ( memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
        return -2147220978;
      goto LABEL_20;
    }
    if ( !memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
    {
      memset_0(sz, 0, sizeof(sz));
      Buf2 = GUID_DefaultAppPartition;
      if ( !StringFromGUID2(&Buf2, sz, 40) )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\subscription.cpp", 0x7CCu, 0x10u, -2147418113);
      v22 = SysAllocString(sz);
      p_pvar = (struct tagPROPVARIANT *)v22;
      if ( !v22 )
        InternalError(L"com\\complus\\src\\events\\tier1\\subscription.cpp", 0x7CFu, 0xC0001204, 0x10u);
      v23 = (*(__int64 (__fastcall **)(CSubscription *, OLECHAR *))(*(_QWORD *)this + 400LL))(this, v22);
      v28 = v23;
      SysFreeString(v22);
      if ( v23 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\subscription.cpp", 0x7DAu, 0x10u, v23);
    }
  }
  if ( !a2 )
    goto LABEL_9;
  if ( !memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
    return -2147220979;
LABEL_20:
  if ( *((_WORD *)this + 188) )
  {
    *(_OWORD *)pv = 0;
    v20 = CLSIDFromString(*((LPCOLESTR *)this + 48), (LPCLSID)pv);
    if ( v20 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\subscription.cpp", 0x7F6u, 0x10u, v20);
    if ( memcmp_0(pv, &GUID_DefaultAppPartition, 0x10u) && memcmp_0(pv, &GUID_NULL, 0x10u) && memcmp_0(pv, &Buf2, 0x10u) )
      return -2147467259;
  }
  else
  {
    *((_WORD *)this + 188) = *((_WORD *)this + 212);
    v9 = (const OLECHAR *)*((_QWORD *)this + 54);
    if ( v9 )
    {
      v10 = SysAllocString(v9);
      *((_QWORD *)this + 48) = v10;
      if ( !v10 )
        InternalError(L"com\\complus\\src\\events\\tier1\\utilities.cpp", 0x12u, 0xC0001204, 0x10u);
    }
    else
    {
      *((_QWORD *)this + 48) = 0;
    }
  }
  if ( !*((_WORD *)this + 200) )
  {
    *((_WORD *)this + 200) = 8;
    lpsz = 0;
    StringFromCLSID(&GUID_NULL, &lpsz);
    *((_QWORD *)this + 51) = SysAllocString(lpsz);
    CoTaskMemFree(lpsz);
  }
  if ( !*((_WORD *)this + 224) )
  {
    *((_WORD *)this + 224) = 8;
    lpsz = 0;
    StringFromCLSID(&GUID_NULL, &lpsz);
    *((_QWORD *)this + 57) = SysAllocString(lpsz);
    CoTaskMemFree(lpsz);
  }
  IsMember = 0;
  if ( CheckTokenMembership(0, SidToCheck, &IsMember) )
    goto LABEL_57;
  result = GetLastError();
  v21 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v21 = result < 0;
  }
  if ( !v21 )
  {
LABEL_57:
    if ( !IsMember && (*((_WORD *)this + 92) != 11 || *((_WORD *)this + 96) != 0xFFFF) )
      return -2147024891;
    if ( *((_WORD *)this + 80) )
    {
      if ( !(unsigned int)CEventClass::CreateExisting(
                            a4,
                            *((unsigned __int16 **)this + 21),
                            *((unsigned __int16 **)this + 54),
                            *((unsigned __int16 **)this + 57),
                            &v31) )
        goto LABEL_86;
      result = StringFromCLSID(&GUID_NULL, &v34);
      if ( result < 0 )
        return result;
      v24 = CEventClass::CreateExisting(
              a4,
              *((unsigned __int16 **)this + 21),
              *((unsigned __int16 **)this + 54),
              v34,
              &v31);
      CoTaskMemFree(v34);
      if ( !v24 )
      {
LABEL_86:
        ((void (__fastcall *)(struct IEventClass2 *))v31->lpVtbl->Release)(v31);
        return -2146368434;
      }
    }
    pProxy = 0;
    result = (*(__int64 (__fastcall **)(struct IEventSystemTier2 *, char *, bool, IUnknown **))(*(_QWORD *)a4 + 88LL))(
               a4,
               (char *)this + 668,
               *((_QWORD *)this + 59) != 0,
               &pProxy);
    if ( result < 0 )
      return result;
    v11 = pProxy;
    if ( !pProxy )
    {
      InternalError(L"com\\complus\\src\\events\\tier1\\subscription.cpp", 0x856u, 0x80001203, 0x10u);
      v11 = pProxy;
    }
    CoSetProxyBlanket(v11, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0x40u);
    v26 = 0;
    memset(&pvar, 0, sizeof(pvar));
    memset(&v38, 0, sizeof(v38));
    memset(&v39, 0, sizeof(v39));
    memset(&v40, 0, sizeof(v40));
    v27 = 0;
    (*(void (__fastcall **)(char *, int *))(*((_QWORD *)this + 61) + 80LL))((char *)this + 488, &v27);
    if ( v27 )
    {
      p_pvar = &pvar;
      v35 = &v38;
      GetProperties((CSubscription *)((char *)this + 488), v27, &pvar, &v38);
    }
    else
    {
      p_pvar = 0;
      v35 = 0;
    }
    (*(void (__fastcall **)(char *, int *))(*((_QWORD *)this + 72) + 80LL))((char *)this + 576, &v27);
    if ( v27 )
    {
      v13 = &v39;
      v14 = &v40;
      GetProperties((CSubscription *)((char *)this + 576), v27, &v39, &v40);
    }
    else
    {
      v13 = 0;
      v14 = 0;
    }
    lpsz = 0;
    v15 = *((_QWORD *)this + 59);
    if ( !v15 )
      goto LABEL_42;
    v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, LPOLESTR *))(*(_QWORD *)v15 + 40LL))(
            v15,
            *((unsigned int *)this + 120),
            &IID_IUnknown,
            &lpsz);
    if ( v16 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\subscription.cpp", 0x88Bu, 0x11u, v16);
    if ( !g_fRunningASService )
    {
      v26 = 0;
      v17 = (int)DetermineSubscriberLocality((struct IUnknown *)lpsz, (enum Locality *)&v26) < 0
         || (unsigned int)(v26 - 1) <= 1;
    }
    else
    {
LABEL_42:
      v17 = v26;
    }
    pv[0] = 0;
    pv[1] = 0;
    v18 = 0;
    if ( lpsz )
    {
      result = MarshalIUnknownIntoBlob((struct tagBLOB *)pv, (struct IUnknown *)lpsz, 0, v12);
      if ( result < 0 )
        return result;
      v18 = pv;
    }
    v19 = ((__int64 (__fastcall *)(IUnknown *, struct IEventSystemTier2 *, char *, struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct tagPROPVARIANT *, LPVOID *, BOOL, int, int))pProxy->lpVtbl[1].QueryInterface)(
            pProxy,
            a4,
            (char *)this + 40,
            p_pvar,
            v35,
            v13,
            v14,
            v18,
            v17,
            a2,
            v33);
    v28 = v19;
    if ( lpsz )
      (*(void (__fastcall **)(LPOLESTR))(*(_QWORD *)lpsz + 16LL))(lpsz);
    if ( pv[1] )
      CoTaskMemFree(pv[1]);
    PropVariantClear((PROPVARIANT *)&pvar);
    PropVariantClear((PROPVARIANT *)&v38);
    PropVariantClear((PROPVARIANT *)&v39);
    PropVariantClear((PROPVARIANT *)&v40);
    if ( v19 >= 0 )
      *((_DWORD *)this + 166) = 0;
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    return v19;
  }
  return result;
}

```

## disassembly

```asm
0x1800130a0  push    rbx
0x1800130a2  push    rsi
0x1800130a3  push    rdi
0x1800130a4  push    r12
0x1800130a6  push    r13
0x1800130a8  push    r14
0x1800130aa  push    r15
0x1800130ac  sub     rsp, 1A0h
0x1800130b3  mov     rax, cs:__security_cookie
0x1800130ba  xor     rax, rsp
0x1800130bd  mov     [rsp+1D8h+var_48], rax
0x1800130c5  mov     r15, r9
0x1800130c8  mov     [rsp+1D8h+var_140], r8d
0x1800130d0  mov     r14d, edx
0x1800130d3  mov     rbx, rcx
0x1800130d6  mov     [rsp+1D8h+var_128], rcx
0x1800130de  xor     esi, esi
0x1800130e0  mov     [rsp+1D8h+var_150], rsi
0x1800130e8  mov     [rsp+1D8h+var_138], rsi
0x1800130f0  cmp     [rcx+28h], si
0x1800130f4  jz      loc_1800131C6
0x1800130fa  cmp     [rcx+40h], si
0x1800130fe  jz      loc_1800131C6
0x180013104  cmp     [rcx+70h], si
0x180013108  jz      loc_1800137D7
0x18001310e  cmp     [rcx+0A0h], si
0x180013115  jz      loc_1800131A4
0x18001311b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180013122  movups  xmmword ptr [rsp+1D8h+Buf2.Data1], xmm0
0x18001312a  cmp     [rcx+1A8h], si
0x180013131  jnz     loc_1800131D0
0x180013137  movups  xmmword ptr [rsp+1D8h+Buf2.Data1], xmm0
0x18001313f  cmp     [rbx+298h], esi
0x180013145  jnz     short loc_18001317C
0x180013147  test    r14d, r14d
0x18001314a  jnz     loc_180013702
0x180013150  mov     r8d, 10h; Size
0x180013156  lea     rdx, [rsp+1D8h+Buf2]; Buf2
0x18001315e  lea     rcx, GUID_NULL; Buf1
0x180013165  call    memcmp_0
0x18001316a  test    eax, eax
0x18001316c  jz      loc_180013215
0x180013172  mov     eax, 8004020Eh
0x180013177  jmp     loc_1800135A7
0x18001317c  test    r14d, r14d
0x18001317f  jz      short loc_180013150
0x180013181  mov     r8d, 10h; Size
0x180013187  lea     rdx, [rsp+1D8h+Buf2]; Buf2
0x18001318f  lea     rcx, GUID_NULL; Buf1
0x180013196  call    memcmp_0
0x18001319b  test    eax, eax
0x18001319d  jnz     short loc_180013147
0x18001319f  jmp     loc_1800137F3
0x1800131a4  cmp     [rcx+160h], si
0x1800131ab  jnz     loc_18001311B
0x1800131b1  cmp     [rcx+1D8h], rsi
0x1800131b8  jz      short loc_1800131C6
0x1800131ba  cmp     [rcx+1E0h], esi
0x1800131c0  jnz     loc_18001311B
0x1800131c6  mov     eax, 80070057h
0x1800131cb  jmp     loc_1800135A7
0x1800131d0  lea     rdx, [rsp+1D8h+Buf2]; pclsid
0x1800131d8  mov     rcx, [rcx+1B0h]; lpsz
0x1800131df  call    cs:__imp_CLSIDFromString
0x1800131e5  test    eax, eax
0x1800131e7  jns     loc_18001313F
0x1800131ed  mov     r8d, 10h; unsigned __int16
0x1800131f3  mov     r9d, eax; int
0x1800131f6  mov     edx, 7BAh; unsigned int
0x1800131fb  lea     rcx, aComComplusSrcE_15; "com\\complus\\src\\events\\tier1\\subsc"...
0x180013202  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180013207  jmp     loc_18001313F
0x18001320c  test    r14d, r14d
0x18001320f  jz      loc_180013150
0x180013215  cmp     word ptr [rbx+178h], 0
0x18001321d  jnz     loc_180013669
0x180013223  movzx   eax, word ptr [rbx+1A8h]
0x18001322a  mov     [rbx+178h], ax
0x180013231  mov     rcx, [rbx+1B0h]; psz
0x180013238  test    rcx, rcx
0x18001323b  jz      loc_180013638
0x180013241  call    cs:__imp_SysAllocString
0x180013247  mov     [rbx+180h], rax
0x18001324e  test    rax, rax
0x180013251  jz      loc_180013777
0x180013257  mov     edi, 8
0x18001325c  cmp     word ptr [rbx+190h], 0
0x180013264  jnz     short loc_1800132A1
0x180013266  mov     [rbx+190h], di
0x18001326d  mov     [rsp+1D8h+lpsz], rsi
0x180013272  lea     rdx, [rsp+1D8h+lpsz]; lplpsz
0x180013277  lea     rcx, GUID_NULL; rclsid
0x18001327e  call    cs:__imp_StringFromCLSID
0x180013284  mov     rcx, [rsp+1D8h+lpsz]; psz
0x180013289  call    cs:__imp_SysAllocString
0x18001328f  mov     [rbx+198h], rax
0x180013296  mov     rcx, [rsp+1D8h+lpsz]; pv
0x18001329b  call    cs:__imp_CoTaskMemFree
0x1800132a1  cmp     word ptr [rbx+1C0h], 0
0x1800132a9  jz      loc_1800138DD
0x1800132af  mov     [rsp+1D8h+IsMember], esi
0x1800132b3  lea     r8, [rsp+1D8h+IsMember]; IsMember
0x1800132b8  mov     rdx, cs:SidToCheck; SidToCheck
0x1800132bf  xor     ecx, ecx; TokenHandle
0x1800132c1  call    cs:__imp_CheckTokenMembership
0x1800132c7  test    eax, eax
0x1800132c9  jz      loc_1800137B8
0x1800132cf  cmp     [rsp+1D8h+IsMember], 0
0x1800132d4  jz      loc_180013616
0x1800132da  cmp     word ptr [rbx+0A0h], 0
0x1800132e2  jnz     loc_18001391D
0x1800132e8  mov     [rsp+1D8h+pProxy], rsi
0x1800132f0  mov     rax, [r15]
0x1800132f3  mov     r8d, esi
0x1800132f6  cmp     [rbx+1D8h], r8
0x1800132fd  setnz   r8b
0x180013301  lea     rdx, [rbx+29Ch]
0x180013308  lea     r9, [rsp+1D8h+pProxy]
0x180013310  mov     rcx, r15
0x180013313  mov     rax, [rax+58h]
0x180013317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001331c  test    eax, eax
0x18001331e  js      loc_1800135A7
0x180013324  mov     rcx, [rsp+1D8h+pProxy]; pProxy
0x18001332c  test    rcx, rcx
0x18001332f  jz      loc_18001372E
0x180013335  mov     [rsp+1D8h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18001333d  mov     [rsp+1D8h+pAuthInfo], rsi; pAuthInfo
0x180013342  mov     [rsp+1D8h+dwImpLevel], 3; dwImpLevel
0x18001334a  mov     [rsp+1D8h+dwAuthnLevel], esi; dwAuthnLevel
0x18001334e  xor     r9d, r9d; pServerPrincName
0x180013351  mov     edx, 0FFFFFFFFh; dwAuthnSvc
0x180013356  mov     r8d, edx; dwAuthzSvc
0x180013359  call    cs:__imp_CoSetProxyBlanket
0x18001335f  mov     [rsp+1D8h+var_170], esi
0x180013363  xorps   xmm0, xmm0
0x180013366  xor     eax, eax
0x180013368  movups  xmmword ptr [rsp+1D8h+pvar], xmm0
0x180013370  mov     [rsp+1D8h+var_110], rax
0x180013378  xorps   xmm1, xmm1
0x18001337b  movups  xmmword ptr [rsp+1D8h+var_108], xmm1
0x180013383  mov     [rsp+1D8h+var_F8], rax
0x18001338b  movups  xmmword ptr [rsp+1D8h+var_F0], xmm0
0x180013393  mov     [rsp+1D8h+var_E0], rax
0x18001339b  movups  xmmword ptr [rsp+1D8h+var_D8], xmm1
0x1800133a3  mov     [rsp+1D8h+var_C8], rax
0x1800133ab  mov     [rsp+1D8h+var_16C], esi
0x1800133af  mov     rax, [rbx+1E8h]
0x1800133b6  lea     rdx, [rsp+1D8h+var_16C]
0x1800133bb  lea     rcx, [rbx+1E8h]
0x1800133c2  mov     rax, [rax+50h]
0x1800133c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133cb  mov     edx, [rsp+1D8h+var_16C]; int
0x1800133cf  test    edx, edx
0x1800133d1  jnz     loc_1800135D5
0x1800133d7  mov     [rsp+1D8h+var_148], rsi
0x1800133df  mov     [rsp+1D8h+var_130], rsi
0x1800133e7  mov     rax, [rbx+240h]
0x1800133ee  lea     rdx, [rsp+1D8h+var_16C]
0x1800133f3  lea     rcx, [rbx+240h]
0x1800133fa  mov     rax, [rax+50h]
0x1800133fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013403  mov     edx, [rsp+1D8h+var_16C]; int
0x180013407  test    edx, edx
0x180013409  jz      loc_1800135CA
0x18001340f  lea     r12, [rsp+1D8h+var_F0]
0x180013417  lea     r13, [rsp+1D8h+var_D8]
0x18001341f  lea     r9, [rsp+1D8h+var_D8]; struct tagPROPVARIANT *
0x180013427  lea     r8, [rsp+1D8h+var_F0]; struct tagPROPVARIANT *
0x18001342f  lea     rcx, [rbx+240h]; struct CPropertyBag *
0x180013436  call    ?GetProperties@@YAXAEAVCPropertyBag@@JPEAUtagPROPVARIANT@@1@Z; GetProperties(CPropertyBag &,long,tagPROPVARIANT *,tagPROPVARIANT *)
0x18001343b  mov     [rsp+1D8h+lpsz], rsi
0x180013440  mov     rcx, [rbx+1D8h]
0x180013447  test    rcx, rcx
0x18001344a  jz      short loc_18001347F
0x18001344c  mov     rax, [rcx]
0x18001344f  lea     r9, [rsp+1D8h+lpsz]
0x180013454  lea     r8, IID_IUnknown
0x18001345b  mov     edx, [rbx+1E0h]
0x180013461  mov     rax, [rax+28h]
0x180013465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001346a  test    eax, eax
0x18001346c  js      loc_180013758
0x180013472  cmp     cs:g_fRunningASService, 0
0x180013479  jz      loc_180013644
0x18001347f  mov     edi, [rsp+1D8h+var_170]
0x180013483  mov     [rsp+1D8h+pv], rsi
0x18001348b  mov     [rsp+1D8h+pv+8], rsi
0x180013493  mov     r8, rsi; unsigned int
0x180013496  mov     rdx, [rsp+1D8h+lpsz]; struct IUnknown *
0x18001349b  test    rdx, rdx
0x18001349e  jz      short loc_1800134BD
0x1800134a0  lea     rcx, [rsp+1D8h+pv]; struct tagBLOB *
0x1800134a8  call    ?MarshalIUnknownIntoBlob@@YAJAEAUtagBLOB@@PEAUIUnknown@@KK@Z; MarshalIUnknownIntoBlob(tagBLOB &,IUnknown *,ulong,ulong)
0x1800134ad  test    eax, eax
0x1800134af  js      loc_1800135A7
0x1800134b5  lea     r8, [rsp+1D8h+pv]
0x1800134bd  mov     rcx, [rsp+1D8h+pProxy]
0x1800134c5  mov     rax, [rcx]
0x1800134c8  mov     edx, [rsp+1D8h+var_140]
0x1800134cf  mov     [rsp+1D8h+var_188], edx
0x1800134d3  mov     [rsp+1D8h+var_190], r14d
0x1800134d8  mov     [rsp+1D8h+var_198], edi
0x1800134dc  mov     qword ptr [rsp+1D8h+dwCapabilities], r8
0x1800134e1  mov     [rsp+1D8h+pAuthInfo], r13
0x1800134e6  mov     qword ptr [rsp+1D8h+dwImpLevel], r12
0x1800134eb  mov     rdx, [rsp+1D8h+var_130]
0x1800134f3  mov     qword ptr [rsp+1D8h+dwAuthnLevel], rdx
0x1800134f8  mov     r9, [rsp+1D8h+var_148]
0x180013500  lea     r8, [rbx+28h]
0x180013504  mov     rdx, r15
0x180013507  mov     rax, [rax+18h]
0x18001350b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013510  mov     edi, eax
0x180013512  mov     [rsp+1D8h+var_164], eax
0x180013516  mov     rcx, [rsp+1D8h+lpsz]
0x18001351b  test    rcx, rcx
0x18001351e  jz      short loc_18001353C
0x180013520  mov     rdx, [rcx]
0x180013523  mov     rax, [rdx+10h]
0x180013527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001352c  jmp     short loc_18001353C
0x18001352e  xor     esi, esi
0x180013530  mov     edi, [rsp+1D8h+var_164]
0x180013534  mov     rbx, [rsp+1D8h+var_128]
0x18001353c  mov     rcx, [rsp+1D8h+pv+8]; pv
0x180013544  test    rcx, rcx
0x180013547  jz      short loc_18001354F
0x180013549  call    cs:__imp_CoTaskMemFree
0x18001354f  lea     rcx, [rsp+1D8h+pvar]; pvar
0x180013557  call    cs:__imp_PropVariantClear
0x18001355d  lea     rcx, [rsp+1D8h+var_108]; pvar
0x180013565  call    cs:__imp_PropVariantClear
0x18001356b  lea     rcx, [rsp+1D8h+var_F0]; pvar
0x180013573  call    cs:__imp_PropVariantClear
0x180013579  lea     rcx, [rsp+1D8h+var_D8]; pvar
0x180013581  call    cs:__imp_PropVariantClear
0x180013587  test    edi, edi
0x180013589  js      short loc_180013591
0x18001358b  mov     [rbx+298h], esi
0x180013591  mov     rcx, [rsp+1D8h+pProxy]
0x180013599  mov     rax, [rcx]
0x18001359c  mov     rax, [rax+10h]
0x1800135a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135a5  mov     eax, edi
0x1800135a7  mov     rcx, [rsp+1D8h+var_48]
0x1800135af  xor     rcx, rsp; StackCookie
0x1800135b2  call    __security_check_cookie
0x1800135b7  add     rsp, 1A0h
0x1800135be  pop     r15
0x1800135c0  pop     r14
0x1800135c2  pop     r13
0x1800135c4  pop     r12
0x1800135c6  pop     rdi
0x1800135c7  pop     rsi
0x1800135c8  pop     rbx
0x1800135c9  retn
0x1800135ca  mov     r12, rsi
0x1800135cd  mov     r13, rsi
0x1800135d0  jmp     loc_18001343B
0x1800135d5  lea     rax, [rsp+1D8h+pvar]
0x1800135dd  mov     [rsp+1D8h+var_148], rax
0x1800135e5  lea     rax, [rsp+1D8h+var_108]
0x1800135ed  mov     [rsp+1D8h+var_130], rax
0x1800135f5  lea     r9, [rsp+1D8h+var_108]; struct tagPROPVARIANT *
0x1800135fd  lea     r8, [rsp+1D8h+pvar]; struct tagPROPVARIANT *
0x180013605  lea     rcx, [rbx+1E8h]; struct CPropertyBag *
0x18001360c  call    ?GetProperties@@YAXAEAVCPropertyBag@@JPEAUtagPROPVARIANT@@1@Z; GetProperties(CPropertyBag &,long,tagPROPVARIANT *,tagPROPVARIANT *)
0x180013611  jmp     loc_1800133E7
0x180013616  cmp     word ptr [rbx+0B8h], 0Bh
0x18001361e  jnz     short loc_18001362E
0x180013620  cmp     word ptr [rbx+0C0h], 0FFFFh
0x180013628  jz      loc_1800132DA
0x18001362e  mov     eax, 80070005h
0x180013633  jmp     loc_1800135A7
0x180013638  mov     [rbx+180h], rsi
0x18001363f  jmp     loc_180013257
0x180013644  mov     [rsp+1D8h+var_170], esi
0x180013648  lea     rdx, [rsp+1D8h+var_170]; enum Locality *
0x18001364d  mov     rcx, [rsp+1D8h+lpsz]; struct IUnknown *
0x180013652  call    ?DetermineSubscriberLocality@@YAJPEAUIUnknown@@AEAW4Locality@@@Z; DetermineSubscriberLocality(IUnknown *,Locality &)
0x180013657  test    eax, eax
0x180013659  jns     loc_1800139C9
0x18001365f  mov     edi, 1
0x180013664  jmp     loc_180013483
0x180013669  xorps   xmm0, xmm0
0x18001366c  movups  xmmword ptr [rsp+1D8h+pv], xmm0
0x180013674  lea     rdx, [rsp+1D8h+pv]; pclsid
0x18001367c  mov     rcx, [rbx+180h]; lpsz
0x180013683  call    cs:__imp_CLSIDFromString
0x180013689  test    eax, eax
0x18001368b  js      loc_180013799
0x180013691  mov     r8d, 10h; Size
0x180013697  lea     rdx, GUID_DefaultAppPartition; Buf2
0x18001369e  lea     rcx, [rsp+1D8h+pv]; Buf1
0x1800136a6  call    memcmp_0
0x1800136ab  test    eax, eax
0x1800136ad  jz      loc_180013257
0x1800136b3  mov     r8d, 10h; Size
0x1800136b9  lea     rdx, GUID_NULL; Buf2
  ... truncated ...
```
