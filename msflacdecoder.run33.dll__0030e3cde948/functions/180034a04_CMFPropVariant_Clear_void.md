# CMFPropVariant::Clear(void)

- ea: `0x180034a04`
- end: `0x180034be1`
- name: `?Clear@CMFPropVariant@@QEAAJXZ`
- size: `477`
- prototype: `__int64 __fastcall(PROPVARIANT *pvar)`
- caller_count: `28`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800212c8`
- `0x1800223b8`
- `0x18002513c`
- `0x18002d69c`
- `0x180030030`
- `0x1800310e0`
- `0x1800316e0`
- `0x180034270`
- `0x180035148`
- `0x180036d48`
- `0x180037f6c`
- `0x180038b38`
- `0x18003bfb0`
- `0x18003da80`
- `0x18003f804`
- `0x180040e10`
- `0x180046384`
- `0x180046a04`
- `0x180047278`
- `0x1800475c8`
- `0x180047dcc`
- `0x18004840c`
- `0x18004ab18`
- `0x18004b7e0`
- `0x18004cc48`
- `0x180052eb0`
- `0x180054820`
- `0x180054cf0`

## callees

- `0x180001e80`
- `0x180020398`
- `0x180020484`
- `0x180034270`
- `0x180034a04`
- `0x1800382c0`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034aac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034bab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034aac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034bab`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180034a58`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180034a58`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::Clear(PROPVARIANT *pvar)
{
  unsigned int v1; // ebp
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  __int64 v6; // rdx
  unsigned int i; // r14d
  BYTE *pData; // rbx
  __int64 v9; // rdi
  __int64 j; // rbx
  __int64 v11; // rcx
  unsigned int k; // ebx
  struct tagPROPVARIANT v14; // [rsp+30h] [rbp-38h] BYREF

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
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_25;
        v6 = 10;
        goto LABEL_24;
      }
      for ( i = 0; pvar->lVal > i; *(_QWORD *)&pData[8 * v9 + 8] = 0 )
      {
        pData = pvar->bstrblobVal.pData;
        v9 = 2LL * i;
        CoTaskMemFree(*(LPVOID *)&pData[16 * i++ + 8]);
      }
    }
    else
    {
      if ( !pvar->bstrblobVal.pData )
      {
        v1 = -2147467261;
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_25;
        v6 = 12;
        goto LABEL_24;
      }
      for ( j = 0; pvar->lVal > (unsigned int)j; j = (unsigned int)(j + 1) )
      {
        v11 = *(_QWORD *)&pvar->bstrblobVal.pData[8 * j];
        if ( v11 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
    }
LABEL_29:
    CoTaskMemFree(pvar->bstrblobVal.pData);
    *(_OWORD *)&pvar->vt = 0;
    pvar->bstrblobVal.pData = 0;
    return v1;
  }
  if ( pvar->bstrblobVal.pData )
  {
    for ( k = 0; pvar->lVal > k; ++k )
    {
      memset(&v14, 0, sizeof(v14));
      CMFPropVariant::GetElementDataAsVariant((CMFPropVariant *)pvar, k, &v14);
      CMFPropVariant::~CMFPropVariant((CMFPropVariant *)&v14);
    }
    goto LABEL_29;
  }
  v1 = -2147467261;
  if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    goto LABEL_25;
  v6 = 11;
LABEL_24:
  WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, pvar, v5);
LABEL_25:
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, pvar, v1);
  return v1;
}

```

## disassembly

```asm
0x180034a04  mov     [rsp+arg_8], rbx
0x180034a09  mov     [rsp+arg_10], rbp
0x180034a0e  push    rsi
0x180034a0f  push    rdi
0x180034a10  push    r14
0x180034a12  sub     rsp, 50h
0x180034a16  mov     rax, cs:__security_cookie
0x180034a1d  xor     rax, rsp
0x180034a20  mov     [rsp+68h+var_20], rax
0x180034a25  xor     ebp, ebp
0x180034a27  xor     eax, eax
0x180034a29  mov     rsi, rcx
0x180034a2c  cmp     ax, [rcx]
0x180034a2f  jz      loc_180034BBD
0x180034a35  movzx   ecx, word ptr [rcx]
0x180034a38  lea     rbx, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x180034a3f  sub     ecx, 100Ch
0x180034a45  jz      loc_180034B12
0x180034a4b  sub     ecx, 1
0x180034a4e  jz      short loc_180034AC5
0x180034a50  cmp     ecx, 34h ; '4'
0x180034a53  jz      short loc_180034A6D
0x180034a55  mov     rcx, rsi; pvar
0x180034a58  call    cs:__imp_PropVariantClear
0x180034a5e  mov     ebp, eax
0x180034a60  test    eax, eax
0x180034a62  jns     loc_180034BBD
0x180034a68  jmp     loc_180034B47
0x180034a6d  cmp     [rsi+10h], rax
0x180034a71  jnz     short loc_180034A91
0x180034a73  mov     ecx, 80004003h
0x180034a78  mov     ebp, ecx
0x180034a7a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180034a7f  cmp     al, 1
0x180034a81  jb      loc_180034B47
0x180034a87  mov     edx, 0Ah
0x180034a8c  jmp     loc_180034B2D
0x180034a91  xor     r14d, r14d
0x180034a94  cmp     [rsi+8], eax
0x180034a97  jbe     loc_180034BA7
0x180034a9d  mov     rbx, [rsi+10h]
0x180034aa1  mov     edi, r14d
0x180034aa4  add     rdi, rdi
0x180034aa7  mov     rcx, [rbx+rdi*8+8]; pv
0x180034aac  call    cs:__imp_CoTaskMemFree
0x180034ab2  inc     r14d
0x180034ab5  mov     [rbx+rdi*8+8], rbp
0x180034aba  cmp     [rsi+8], r14d
0x180034abe  ja      short loc_180034A9D
0x180034ac0  jmp     loc_180034BA7
0x180034ac5  cmp     [rsi+10h], rax
0x180034ac9  jnz     short loc_180034AE2
0x180034acb  mov     ecx, 80004003h
0x180034ad0  mov     ebp, ecx
0x180034ad2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180034ad7  cmp     al, 1
0x180034ad9  jb      short loc_180034B47
0x180034adb  mov     edx, 0Ch
0x180034ae0  jmp     short loc_180034B2D
0x180034ae2  xor     ebx, ebx
0x180034ae4  cmp     [rsi+8], eax
0x180034ae7  jbe     loc_180034BA7
0x180034aed  mov     rax, [rsi+10h]
0x180034af1  mov     rcx, [rax+rbx*8]
0x180034af5  test    rcx, rcx
0x180034af8  jz      short loc_180034B06
0x180034afa  mov     rax, [rcx]
0x180034afd  mov     rax, [rax+10h]
0x180034b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b06  inc     ebx
0x180034b08  cmp     [rsi+8], ebx
0x180034b0b  ja      short loc_180034AED
0x180034b0d  jmp     loc_180034BA7
0x180034b12  cmp     [rsi+10h], rax
0x180034b16  jnz     short loc_180034B71
0x180034b18  mov     ecx, 80004003h
0x180034b1d  mov     ebp, ecx
0x180034b1f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180034b24  cmp     al, 1
0x180034b26  jb      short loc_180034B47
0x180034b28  mov     edx, 0Bh
0x180034b2d  mov     [rsp+68h+var_48], ecx
0x180034b31  mov     r9, rsi
0x180034b34  mov     rcx, cs:WPP_GLOBAL_Control
0x180034b3b  mov     r8, rbx
0x180034b3e  mov     rcx, [rcx+10h]
0x180034b42  call    WPP_SF_qd
0x180034b47  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180034b4c  cmp     al, 1
0x180034b4e  jb      short loc_180034BBD
0x180034b50  mov     rcx, cs:WPP_GLOBAL_Control
0x180034b57  mov     edx, 0Dh
0x180034b5c  mov     r9, rsi
0x180034b5f  mov     [rsp+68h+var_48], ebp
0x180034b63  mov     r8, rbx
0x180034b66  mov     rcx, [rcx+10h]
0x180034b6a  call    WPP_SF_qd
0x180034b6f  jmp     short loc_180034BBD
0x180034b71  xor     ebx, ebx
0x180034b73  cmp     [rsi+8], eax
0x180034b76  jbe     short loc_180034BA7
0x180034b78  xorps   xmm0, xmm0
0x180034b7b  lea     r8, [rsp+68h+var_38]; struct tagPROPVARIANT *
0x180034b80  xor     eax, eax
0x180034b82  mov     edx, ebx; unsigned int
0x180034b84  mov     rcx, rsi; this
0x180034b87  mov     qword ptr [rsp+68h+var_38+10h], rax
0x180034b8c  movups  xmmword ptr [rsp+68h+var_38], xmm0
0x180034b91  call    ?GetElementDataAsVariant@CMFPropVariant@@IEBAJKPEAUtagPROPVARIANT@@@Z; CMFPropVariant::GetElementDataAsVariant(ulong,tagPROPVARIANT *)
0x180034b96  lea     rcx, [rsp+68h+var_38]; this
0x180034b9b  call    ??1CMFPropVariant@@QEAA@XZ; CMFPropVariant::~CMFPropVariant(void)
0x180034ba0  inc     ebx
0x180034ba2  cmp     [rsi+8], ebx
0x180034ba5  ja      short loc_180034B78
0x180034ba7  mov     rcx, [rsi+10h]; pv
0x180034bab  call    cs:__imp_CoTaskMemFree
0x180034bb1  xorps   xmm0, xmm0
0x180034bb4  xor     eax, eax
0x180034bb6  movups  xmmword ptr [rsi], xmm0
0x180034bb9  mov     [rsi+10h], rax
0x180034bbd  mov     eax, ebp
0x180034bbf  mov     rcx, [rsp+68h+var_20]
0x180034bc4  xor     rcx, rsp; StackCookie
0x180034bc7  call    __security_check_cookie
0x180034bcc  lea     r11, [rsp+68h+var_18]
0x180034bd1  mov     rbx, [r11+28h]
0x180034bd5  mov     rbp, [r11+30h]
0x180034bd9  mov     rsp, r11
0x180034bdc  pop     r14
0x180034bde  pop     rdi
0x180034bdf  pop     rsi
0x180034be0  retn
```
