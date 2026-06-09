# CContextMenuExt::_QueryAndAddItemSelectionStatus(ushort const *,ulong,CContextMenuExt::SELECTION_STATUS *)

- ea: `0x180016958`
- end: `0x180016bc9`
- name: `?_QueryAndAddItemSelectionStatus@CContextMenuExt@@AEAAJPEBGKPEAUSELECTION_STATUS@1@@Z`
- size: `625`
- prototype: `__int64 __fastcall(CContextMenuExt *__hidden this, const unsigned __int16 *, unsigned int, struct CContextMenuExt::SELECTION_STATUS *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016cbc`

## callees

- `0x180013d9c`
- `0x18001465c`
- `0x180016390`
- `0x180016444`
- `0x180016958`

## import_xrefs

- `SHLWAPI!PathIsUNCW` at `0x180016993`
- `SHLWAPI!PathIsUNCW` at `0x180016993`
- `SHLWAPI!StrChrW` at `0x1800169b3`
- `SHLWAPI!StrChrW` at `0x1800169b3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800169f9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800169f9`

## pseudocode

```c
__int64 __fastcall CContextMenuExt::_QueryAndAddItemSelectionStatus(
        WCHAR *this,
        const unsigned __int16 *a2,
        __int64 a3,
        struct CContextMenuExt::SELECTION_STATUS *a4)
{
  unsigned int IsItemParentPinned; // ecx
  const unsigned __int16 *v8; // rdi
  PWSTR v9; // rax
  __int64 v10; // r9
  int IsItemCacheable; // eax
  __int64 v12; // rcx
  int v13; // eax
  UstCommon::CImpersonator *v14; // rcx
  __int64 v15; // rdx
  int v16; // edx
  __int128 v18; // [rsp+30h] [rbp-69h]
  _OWORD v19[2]; // [rsp+40h] [rbp-59h] BYREF
  void **v20; // [rsp+60h] [rbp-39h] BYREF
  __int64 v21; // [rsp+68h] [rbp-31h]
  const unsigned __int16 *v22; // [rsp+70h] [rbp-29h]
  __int64 v23; // [rsp+78h] [rbp-21h]
  __int128 v24; // [rsp+80h] [rbp-19h]
  __int128 v25; // [rsp+90h] [rbp-9h]
  __int64 v26; // [rsp+A0h] [rbp+7h]
  __int64 v27; // [rsp+A8h] [rbp+Fh]
  __int64 v28; // [rsp+B0h] [rbp+17h]
  int v29; // [rsp+110h] [rbp+77h] BYREF

  memset(v19, 0, 28);
  v29 = 0;
  v18 = 0;
  if ( !PathIsUNCW(a2) )
    return (unsigned int)-2147024735;
  v8 = a2 + 2;
  v9 = StrChrW(a2 + 2, 0x5Cu);
  if ( v9 )
  {
    v10 = v9 - v8;
  }
  else
  {
    v10 = -1;
    do
      ++v10;
    while ( v8[v10] );
  }
  if ( CompareStringW(0x400u, 1u, a2 + 2, v10, this + 108, -1) == 2 )
  {
    return (unsigned int)-2147024735;
  }
  else
  {
    IsItemCacheable = CContextMenuExt::_IsItemCacheable((CContextMenuExt *)this, a2, &v29);
    IsItemParentPinned = IsItemCacheable;
    if ( IsItemCacheable == 1 )
      return (unsigned int)-2147467259;
    if ( IsItemCacheable < 0 )
      return IsItemParentPinned;
    if ( !v29 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) == 0 )
      {
        goto LABEL_43;
      }
      v15 = 46;
      goto LABEL_42;
    }
    v12 = *((_QWORD *)this + 13);
    v20 = &CQueryCscItemInfoTask::`vftable';
    v24 = 0;
    v25 = 0;
    v21 = 0;
    v22 = a2;
    v23 = 0;
    v26 = 0;
    v27 = 0;
    v28 = 0;
    v13 = CComTaskThread<CCscComTaskContext>::DoTask(v12, &v20);
    IsItemParentPinned = v13;
    if ( v13 == -2147024894 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0 )
      {
        goto LABEL_43;
      }
      v15 = 45;
LABEL_42:
      WPP_SF_S(*((_QWORD *)v14 + 2), v15, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids, a2);
LABEL_43:
      IsItemParentPinned = 0;
      v16 = 1;
      goto LABEL_44;
    }
    if ( v13 >= 0 )
    {
      IsItemParentPinned = v21;
      if ( (int)v21 >= 0 )
      {
        if ( (_DWORD)v25 )
          DWORD2(v18) = 1;
        if ( *(_QWORD *)((char *)&v25 + 4) || HIDWORD(v25) )
          HIDWORD(v18) = 1;
        if ( (v27 & 0x1000) != 0 )
          ++DWORD1(v19[0]);
        if ( (_DWORD)v26 )
          ++DWORD2(v19[1]);
        if ( (_DWORD)v28 == 1 )
        {
          switch ( HIDWORD(v28) )
          {
            case 2:
              ++LODWORD(v19[1]);
              break;
            case 3:
              ++DWORD1(v19[1]);
              break;
            case 4:
              ++HIDWORD(v19[0]);
              break;
          }
        }
        ++LODWORD(v19[0]);
        IsItemParentPinned = CContextMenuExt::_IsItemParentPinned((CContextMenuExt *)this, a2);
        if ( IsItemParentPinned )
        {
          if ( (IsItemParentPinned & 0x80000000) != 0 )
            return IsItemParentPinned;
        }
        else
        {
          ++DWORD2(v19[0]);
        }
        v16 = 0;
LABEL_44:
        *(_DWORD *)a4 += v18;
        *((_DWORD *)a4 + 2) += DWORD2(v18);
        *((_DWORD *)a4 + 3) += HIDWORD(v18);
        *((_DWORD *)a4 + 4) += LODWORD(v19[0]);
        *((_DWORD *)a4 + 6) += DWORD2(v19[0]);
        *((_DWORD *)a4 + 7) += HIDWORD(v19[0]);
        *((_DWORD *)a4 + 8) += LODWORD(v19[1]);
        *((_DWORD *)a4 + 9) += DWORD1(v19[1]);
        *((_DWORD *)a4 + 5) += DWORD1(v19[0]);
        *((_DWORD *)a4 + 1) += v16;
        *((_DWORD *)a4 + 10) += DWORD2(v19[1]);
      }
    }
  }
  return IsItemParentPinned;
}

```

## disassembly

```asm
0x180016958  mov     [rsp-8+arg_10], r8d
0x18001695d  push    rbp
0x18001695e  push    rbx
0x18001695f  push    rsi
0x180016960  push    rdi
0x180016961  push    r14
0x180016963  push    r15
0x180016965  lea     rbp, [rsp-2Fh]
0x18001696a  sub     rsp, 0C8h
0x180016971  xorps   xmm0, xmm0
0x180016974  mov     r14, rcx
0x180016977  movups  [rbp+57h+var_B0], xmm0
0x18001697b  xor     r15d, r15d
0x18001697e  mov     rcx, rdx; pszPath
0x180016981  movups  [rbp+57h+var_B0+0Ch], xmm0
0x180016985  mov     rsi, r9
0x180016988  mov     [rbp+57h+arg_10], r15d
0x18001698c  mov     rbx, rdx
0x18001698f  movups  [rbp+57h+var_C0], xmm0
0x180016993  call    cs:__imp_PathIsUNCW
0x180016999  test    eax, eax
0x18001699b  jnz     short loc_1800169A7
0x18001699d  mov     ecx, 800700A1h
0x1800169a2  jmp     loc_180016BB7
0x1800169a7  lea     rdi, [rbx+4]
0x1800169ab  mov     edx, 5Ch ; '\'; wMatch
0x1800169b0  mov     rcx, rdi; pszStart
0x1800169b3  call    cs:__imp_StrChrW
0x1800169b9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800169bd  mov     r9, rax
0x1800169c0  test    rax, rax
0x1800169c3  jz      short loc_1800169CD
0x1800169c5  sub     r9, rdi
0x1800169c8  sar     r9, 1
0x1800169cb  jmp     short loc_1800169DA
0x1800169cd  mov     r9, rcx
0x1800169d0  inc     r9; cchCount1
0x1800169d3  cmp     [rdi+r9*2], r15w
0x1800169d8  jnz     short loc_1800169D0
0x1800169da  mov     [rsp+0F0h+cchCount2], ecx; cchCount2
0x1800169de  lea     rax, [r14+0D8h]
0x1800169e5  mov     r8, rdi; lpString1
0x1800169e8  mov     [rsp+0F0h+lpString2], rax; lpString2
0x1800169ed  mov     edi, 1
0x1800169f2  mov     ecx, 400h; Locale
0x1800169f7  mov     edx, edi; dwCmpFlags
0x1800169f9  call    cs:__imp_CompareStringW
0x1800169ff  cmp     eax, 2
0x180016a02  jz      short loc_18001699D
0x180016a04  lea     r8, [rbp+57h+arg_10]; int *
0x180016a08  mov     rdx, rbx; unsigned __int16 *
0x180016a0b  mov     rcx, r14; this
0x180016a0e  call    ?_IsItemCacheable@CContextMenuExt@@AEAAJPEBGPEAH@Z; CContextMenuExt::_IsItemCacheable(ushort const *,int *)
0x180016a13  mov     ecx, eax
0x180016a15  cmp     eax, edi
0x180016a17  jnz     short loc_180016A23
0x180016a19  mov     ecx, 80004005h
0x180016a1e  jmp     loc_180016BB7
0x180016a23  test    eax, eax
0x180016a25  js      loc_180016BB7
0x180016a2b  cmp     [rbp+57h+arg_10], r15d
0x180016a2f  jz      loc_180016B3D
0x180016a35  mov     rcx, [r14+68h]
0x180016a39  lea     rax, ??_7CQueryCscItemInfoTask@@6B@; const CQueryCscItemInfoTask::`vftable'
0x180016a40  xorps   xmm0, xmm0
0x180016a43  mov     [rbp+57h+var_90], rax
0x180016a47  xorps   xmm1, xmm1
0x180016a4a  movdqa  [rbp+57h+var_70], xmm0
0x180016a4f  lea     rdx, [rbp+57h+var_90]
0x180016a53  movdqa  [rbp+57h+var_60], xmm1
0x180016a58  mov     [rbp+57h+var_88], r15
0x180016a5c  mov     [rbp+57h+var_80], rbx
0x180016a60  mov     [rbp+57h+var_78], r15
0x180016a64  mov     [rbp+57h+var_50], r15
0x180016a68  mov     [rbp+57h+var_48], r15
0x180016a6c  mov     [rbp+57h+var_40], r15
0x180016a70  call    ?DoTask@?$CComTaskThread@VCCscComTaskContext@@@@QEAAJPEAV?$CComTask@VCCscComTaskContext@@@@@Z; CComTaskThread<CCscComTaskContext>::DoTask(CComTask<CCscComTaskContext> *)
0x180016a75  mov     ecx, eax
0x180016a77  cmp     eax, 80070002h
0x180016a7c  jnz     short loc_180016AAC
0x180016a7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a85  lea     rax, WPP_GLOBAL_Control
0x180016a8c  cmp     rcx, rax
0x180016a8f  jz      loc_180016B71
0x180016a95  test    dword ptr [rcx+1Ch], 40000h
0x180016a9c  jz      loc_180016B71
0x180016aa2  mov     edx, 2Dh ; '-'
0x180016aa7  jmp     loc_180016B5E
0x180016aac  test    eax, eax
0x180016aae  js      loc_180016BB7
0x180016ab4  mov     ecx, dword ptr [rbp+57h+var_88]
0x180016ab7  test    ecx, ecx
0x180016ab9  js      loc_180016BB7
0x180016abf  mov     eax, dword ptr [rbp+57h+var_48]
0x180016ac2  and     eax, 1000h
0x180016ac7  cmp     dword ptr [rbp+57h+var_60], r15d
0x180016acb  jz      short loc_180016AD0
0x180016acd  add     dword ptr [rbp+57h+var_C0+8], edi
0x180016ad0  cmp     dword ptr [rbp+57h+var_60+4], r15d
0x180016ad4  jnz     short loc_180016AE2
0x180016ad6  cmp     dword ptr [rbp+57h+var_60+8], r15d
0x180016ada  jnz     short loc_180016AE2
0x180016adc  cmp     dword ptr [rbp+57h+var_60+0Ch], r15d
0x180016ae0  jz      short loc_180016AE5
0x180016ae2  add     dword ptr [rbp+57h+var_C0+0Ch], edi
0x180016ae5  test    eax, eax
0x180016ae7  jz      short loc_180016AEC
0x180016ae9  add     dword ptr [rbp+57h+var_B0+4], edi
0x180016aec  cmp     dword ptr [rbp+57h+var_50], r15d
0x180016af0  jz      short loc_180016AF5
0x180016af2  add     [rbp+57h+var_98], edi
0x180016af5  test    ecx, ecx
0x180016af7  js      short loc_180016B1B
0x180016af9  cmp     dword ptr [rbp+57h+var_40], edi
0x180016afc  jnz     short loc_180016B1B
0x180016afe  mov     ecx, dword ptr [rbp+57h+var_40+4]
0x180016b01  sub     ecx, 2
0x180016b04  jz      short loc_180016B18
0x180016b06  sub     ecx, edi
0x180016b08  jz      short loc_180016B13
0x180016b0a  cmp     ecx, edi
0x180016b0c  jnz     short loc_180016B1B
0x180016b0e  add     dword ptr [rbp+57h+var_B0+0Ch], edi
0x180016b11  jmp     short loc_180016B1B
0x180016b13  add     [rbp+57h+var_9C], edi
0x180016b16  jmp     short loc_180016B1B
0x180016b18  add     [rbp+57h+var_A0], edi
0x180016b1b  add     dword ptr [rbp+57h+var_B0], edi
0x180016b1e  mov     rdx, rbx; unsigned __int16 *
0x180016b21  mov     rcx, r14; this
0x180016b24  call    ?_IsItemParentPinned@CContextMenuExt@@AEAAJPEBG@Z; CContextMenuExt::_IsItemParentPinned(ushort const *)
0x180016b29  mov     ecx, eax
0x180016b2b  test    eax, eax
0x180016b2d  jnz     short loc_180016B37
0x180016b2f  add     dword ptr [rbp+57h+var_B0+8], edi
0x180016b32  mov     edx, dword ptr [rbp+57h+var_C0+4]
0x180016b35  jmp     short loc_180016B79
0x180016b37  test    ecx, ecx
0x180016b39  js      short loc_180016BB7
0x180016b3b  jmp     short loc_180016B32
0x180016b3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b44  lea     rax, WPP_GLOBAL_Control
0x180016b4b  cmp     rcx, rax
0x180016b4e  jz      short loc_180016B71
0x180016b50  test    dword ptr [rcx+1Ch], 4000000h
0x180016b57  jz      short loc_180016B71
0x180016b59  mov     edx, 2Eh ; '.'
0x180016b5e  mov     rcx, [rcx+10h]
0x180016b62  lea     r8, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids
0x180016b69  mov     r9, rbx
0x180016b6c  call    WPP_SF_S
0x180016b71  mov     edx, dword ptr [rbp+57h+var_C0+4]
0x180016b74  mov     ecx, r15d
0x180016b77  add     edx, edi
0x180016b79  mov     eax, dword ptr [rbp+57h+var_C0]
0x180016b7c  add     [rsi], eax
0x180016b7e  mov     eax, dword ptr [rbp+57h+var_C0+8]
0x180016b81  add     [rsi+8], eax
0x180016b84  mov     eax, dword ptr [rbp+57h+var_C0+0Ch]
0x180016b87  add     [rsi+0Ch], eax
0x180016b8a  mov     eax, dword ptr [rbp+57h+var_B0]
0x180016b8d  add     [rsi+10h], eax
0x180016b90  mov     eax, dword ptr [rbp+57h+var_B0+8]
0x180016b93  add     [rsi+18h], eax
0x180016b96  mov     eax, dword ptr [rbp+57h+var_B0+0Ch]
0x180016b99  add     [rsi+1Ch], eax
0x180016b9c  mov     eax, [rbp+57h+var_A0]
0x180016b9f  add     [rsi+20h], eax
0x180016ba2  mov     eax, [rbp+57h+var_9C]
0x180016ba5  add     [rsi+24h], eax
0x180016ba8  mov     eax, dword ptr [rbp+57h+var_B0+4]
0x180016bab  add     [rsi+14h], eax
0x180016bae  add     [rsi+4], edx
0x180016bb1  mov     eax, [rbp+57h+var_98]
0x180016bb4  add     [rsi+28h], eax
0x180016bb7  mov     eax, ecx
0x180016bb9  add     rsp, 0C8h
0x180016bc0  pop     r15
0x180016bc2  pop     r14
0x180016bc4  pop     rdi
0x180016bc5  pop     rsi
0x180016bc6  pop     rbx
0x180016bc7  pop     rbp
0x180016bc8  retn
```
