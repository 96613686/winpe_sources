# CMFPropVariant::Clear(void)

- ea: `0x1800746f8`
- end: `0x1800748f4`
- name: `?Clear@CMFPropVariant@@QEAAJXZ`
- size: `508`
- prototype: `__int64 __fastcall(PROPVARIANT *pvar)`
- caller_count: `21`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010540`
- `0x180051754`
- `0x180051e30`
- `0x1800526dc`
- `0x180052a48`
- `0x18005328c`
- `0x180053900`
- `0x180055990`
- `0x1800575e0`
- `0x1800590f8`
- `0x18005a7d0`
- `0x180069134`
- `0x180069df0`
- `0x18006b2cc`
- `0x18006f224`
- `0x180071c50`
- `0x180073704`
- `0x180073bf8`
- `0x1800746ec`
- `0x1800748fc`
- `0x180077298`

## callees

- `0x180002400`
- `0x180021b9c`
- `0x1800746ec`
- `0x1800746f8`
- `0x180077608`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800747aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800748b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800747aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800748b7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180074750`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180074750`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::Clear(PROPVARIANT *pvar)
{
  unsigned int v1; // ebp
  int v3; // ecx
  int v4; // ecx
  __int64 v5; // rdx
  unsigned int i; // r14d
  BYTE *pData; // rbx
  __int64 v8; // rdi
  __int64 j; // rbx
  __int64 v10; // rcx
  unsigned int k; // ebx
  struct tagPROPVARIANT v13; // [rsp+30h] [rbp-38h] BYREF

  v1 = 0;
  if ( !pvar->vt )
    return v1;
  v3 = pvar->vt - 4108;
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      if ( v4 != 52 )
      {
        v1 = PropVariantClear(pvar);
        if ( (v1 & 0x80000000) == 0 )
          return v1;
        goto LABEL_25;
      }
      if ( !pvar->bstrblobVal.pData )
      {
        v1 = -2147467261;
        if ( !g_wppLevels )
          return v1;
        v5 = 10;
        goto LABEL_24;
      }
      for ( i = 0; pvar->lVal > i; *(_QWORD *)&pData[8 * v8 + 8] = 0 )
      {
        pData = pvar->bstrblobVal.pData;
        v8 = 2LL * i;
        CoTaskMemFree(*(LPVOID *)&pData[16 * i++ + 8]);
      }
LABEL_29:
      CoTaskMemFree(pvar->bstrblobVal.pData);
      *(_OWORD *)&pvar->vt = 0;
      pvar->bstrblobVal.pData = 0;
      return v1;
    }
    if ( pvar->bstrblobVal.pData )
    {
      for ( j = 0; pvar->lVal > (unsigned int)j; j = (unsigned int)(j + 1) )
      {
        v10 = *(_QWORD *)&pvar->bstrblobVal.pData[8 * j];
        if ( v10 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      goto LABEL_29;
    }
    v1 = -2147467261;
    if ( !g_wppLevels )
      return v1;
    v5 = 12;
  }
  else
  {
    if ( pvar->bstrblobVal.pData )
    {
      for ( k = 0; pvar->lVal > k; ++k )
      {
        memset(&v13, 0, sizeof(v13));
        CMFPropVariant::GetElementDataAsVariant((CMFPropVariant *)pvar, k, &v13);
        CMFPropVariant::~CMFPropVariant((CMFPropVariant *)&v13);
      }
      goto LABEL_29;
    }
    v1 = -2147467261;
    if ( !g_wppLevels )
      return v1;
    v5 = 11;
  }
LABEL_24:
  WPP_SF_qD(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v5,
    &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
    pvar,
    -2147467261);
LABEL_25:
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, pvar, v1);
  return v1;
}

```

## disassembly

```asm
0x1800746f8  mov     [rsp+arg_8], rbx
0x1800746fd  mov     [rsp+arg_10], rbp
0x180074702  push    rsi
0x180074703  push    rdi
0x180074704  push    r14
0x180074706  sub     rsp, 50h
0x18007470a  mov     rax, cs:__security_cookie
0x180074711  xor     rax, rsp
0x180074714  mov     [rsp+68h+var_20], rax
0x180074719  xor     ebp, ebp
0x18007471b  xor     eax, eax
0x18007471d  mov     rsi, rcx
0x180074720  cmp     ax, [rcx]
0x180074723  jz      loc_1800748CF
0x180074729  movzx   ecx, word ptr [rcx]
0x18007472c  lea     rbx, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x180074733  sub     ecx, 100Ch
0x180074739  jz      loc_18007481A
0x18007473f  sub     ecx, 1
0x180074742  jz      loc_1800747C9
0x180074748  cmp     ecx, 34h ; '4'
0x18007474b  jz      short loc_18007476B
0x18007474d  mov     rcx, rsi; pvar
0x180074750  call    cs:__imp_PropVariantClear
0x180074757  nop     dword ptr [rax+rax+00h]
0x18007475c  mov     ebp, eax
0x18007475e  test    eax, eax
0x180074760  jns     loc_1800748CF
0x180074766  jmp     loc_180074853
0x18007476b  cmp     [rsi+10h], rax
0x18007476f  jnz     short loc_18007478F
0x180074771  mov     eax, 80004003h
0x180074776  mov     ebp, eax
0x180074778  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007477f  jb      loc_1800748CF
0x180074785  mov     edx, 0Ah
0x18007478a  jmp     loc_180074839
0x18007478f  xor     r14d, r14d
0x180074792  cmp     [rsi+8], eax
0x180074795  jbe     loc_1800748B3
0x18007479b  mov     rbx, [rsi+10h]
0x18007479f  mov     edi, r14d
0x1800747a2  add     rdi, rdi
0x1800747a5  mov     rcx, [rbx+rdi*8+8]; pv
0x1800747aa  call    cs:__imp_CoTaskMemFree
0x1800747b1  nop     dword ptr [rax+rax+00h]
0x1800747b6  inc     r14d
0x1800747b9  mov     [rbx+rdi*8+8], rbp
0x1800747be  cmp     [rsi+8], r14d
0x1800747c2  ja      short loc_18007479B
0x1800747c4  jmp     loc_1800748B3
0x1800747c9  cmp     [rsi+10h], rax
0x1800747cd  jnz     short loc_1800747EA
0x1800747cf  mov     eax, 80004003h
0x1800747d4  mov     ebp, eax
0x1800747d6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800747dd  jb      loc_1800748CF
0x1800747e3  mov     edx, 0Ch
0x1800747e8  jmp     short loc_180074839
0x1800747ea  xor     ebx, ebx
0x1800747ec  cmp     [rsi+8], eax
0x1800747ef  jbe     loc_1800748B3
0x1800747f5  mov     rax, [rsi+10h]
0x1800747f9  mov     rcx, [rax+rbx*8]
0x1800747fd  test    rcx, rcx
0x180074800  jz      short loc_18007480E
0x180074802  mov     rax, [rcx]
0x180074805  mov     rax, [rax+10h]
0x180074809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007480e  inc     ebx
0x180074810  cmp     [rsi+8], ebx
0x180074813  ja      short loc_1800747F5
0x180074815  jmp     loc_1800748B3
0x18007481a  cmp     [rsi+10h], rax
0x18007481e  jnz     short loc_18007487D
0x180074820  mov     eax, 80004003h
0x180074825  mov     ebp, eax
0x180074827  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007482e  jb      loc_1800748CF
0x180074834  mov     edx, 0Bh
0x180074839  mov     rcx, cs:WPP_GLOBAL_Control
0x180074840  mov     r9, rsi
0x180074843  mov     r8, rbx
0x180074846  mov     [rsp+68h+var_48], eax
0x18007484a  mov     rcx, [rcx+10h]
0x18007484e  call    WPP_SF_qD
0x180074853  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007485a  jb      short loc_1800748CF
0x18007485c  mov     rcx, cs:WPP_GLOBAL_Control
0x180074863  mov     edx, 0Dh
0x180074868  mov     r9, rsi
0x18007486b  mov     [rsp+68h+var_48], ebp
0x18007486f  mov     r8, rbx
0x180074872  mov     rcx, [rcx+10h]
0x180074876  call    WPP_SF_qD
0x18007487b  jmp     short loc_1800748CF
0x18007487d  xor     ebx, ebx
0x18007487f  cmp     [rsi+8], eax
0x180074882  jbe     short loc_1800748B3
0x180074884  xorps   xmm0, xmm0
0x180074887  lea     r8, [rsp+68h+var_38]; struct tagPROPVARIANT *
0x18007488c  xor     eax, eax
0x18007488e  mov     edx, ebx; unsigned int
0x180074890  mov     rcx, rsi; this
0x180074893  mov     qword ptr [rsp+68h+var_38+10h], rax
0x180074898  movups  xmmword ptr [rsp+68h+var_38], xmm0
0x18007489d  call    ?GetElementDataAsVariant@CMFPropVariant@@IEBAJKPEAUtagPROPVARIANT@@@Z; CMFPropVariant::GetElementDataAsVariant(ulong,tagPROPVARIANT *)
0x1800748a2  lea     rcx, [rsp+68h+var_38]; this
0x1800748a7  call    ??1CMFPropVariant@@QEAA@XZ; CMFPropVariant::~CMFPropVariant(void)
0x1800748ac  inc     ebx
0x1800748ae  cmp     [rsi+8], ebx
0x1800748b1  ja      short loc_180074884
0x1800748b3  mov     rcx, [rsi+10h]; pv
0x1800748b7  call    cs:__imp_CoTaskMemFree
0x1800748be  nop     dword ptr [rax+rax+00h]
0x1800748c3  xorps   xmm0, xmm0
0x1800748c6  xor     eax, eax
0x1800748c8  movups  xmmword ptr [rsi], xmm0
0x1800748cb  mov     [rsi+10h], rax
0x1800748cf  mov     eax, ebp
0x1800748d1  mov     rcx, [rsp+68h+var_20]
0x1800748d6  xor     rcx, rsp; StackCookie
0x1800748d9  call    __security_check_cookie
0x1800748de  lea     r11, [rsp+68h+var_18]
0x1800748e3  mov     rbx, [r11+28h]
0x1800748e7  mov     rbp, [r11+30h]
0x1800748eb  mov     rsp, r11
0x1800748ee  pop     r14
0x1800748f0  pop     rdi
0x1800748f1  pop     rsi
0x1800748f2  retn
```
