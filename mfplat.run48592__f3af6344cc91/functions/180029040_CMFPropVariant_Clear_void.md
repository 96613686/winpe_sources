# CMFPropVariant::Clear(void)

- ea: `0x180029040`
- end: `0x180029221`
- name: `?Clear@CMFPropVariant@@QEAAJXZ`
- size: `481`
- prototype: `__int64 __fastcall(PROPVARIANT *pvar)`
- caller_count: `18`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006f18`
- `0x180027ba8`
- `0x180028880`
- `0x1800289e0`
- `0x1800289f0`
- `0x18002dcc0`
- `0x18002eec4`
- `0x18002fe40`
- `0x18002ff50`
- `0x180048bbc`
- `0x18008a764`
- `0x1800de058`
- `0x1800e7408`
- `0x1800e8654`
- `0x18011e9a0`
- `0x18013ec70`
- `0x180141b40`
- `0x1801aba38`

## callees

- `0x1800214fc`
- `0x1800289e0`
- `0x180029040`
- `0x18002c050`
- `0x1801200d0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002909f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002909f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800290f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029105`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002920a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800290f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029105`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002920a`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::Clear(CMFPropVariant *pvar)
{
  unsigned int v2; // edi
  int vt; // ecx
  __int64 result; // rax
  __int64 v5; // rdx
  unsigned int k; // ebp
  unsigned __int8 *v7; // rbx
  __int64 j; // rbx
  __int64 v9; // rcx
  unsigned int i; // ebx
  CMFPropVariant v11; // [rsp+30h] [rbp-28h] BYREF

  v2 = 0;
  vt = pvar->vt;
  result = 0;
  if ( (_WORD)vt )
  {
    switch ( vt )
    {
      case 4108:
        if ( !pvar->bstrblobVal.pData )
        {
          v2 = -2147467261;
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            return v2;
          v5 = 11;
LABEL_24:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v5,
            WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
            pvar,
            -2147467261);
          goto LABEL_25;
        }
        for ( i = 0; pvar->decVal.Lo32 > i; ++i )
        {
          memset(&v11, 0, sizeof(v11));
          CMFPropVariant::GetElementDataAsVariant(pvar, i, &v11);
          CMFPropVariant::~CMFPropVariant(&v11);
        }
        break;
      case 4109:
        if ( !pvar->bstrblobVal.pData )
        {
          v2 = -2147467261;
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            return v2;
          v5 = 12;
          goto LABEL_24;
        }
        for ( j = 0; pvar->decVal.Lo32 > (unsigned int)j; j = (unsigned int)(j + 1) )
        {
          v9 = *(_QWORD *)&pvar->bstrblobVal.pData[8 * j];
          if ( v9 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        }
        break;
      case 4161:
        if ( !pvar->bstrblobVal.pData )
        {
          v2 = -2147467261;
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            return v2;
          v5 = 10;
          goto LABEL_24;
        }
        for ( k = 0; pvar->decVal.Lo32 > k; *((_QWORD *)v7 + 1) = 0 )
        {
          v7 = &pvar->bstrblobVal.pData[16 * k];
          CoTaskMemFree(*((LPVOID *)v7 + 1));
          ++k;
        }
        CoTaskMemFree(pvar->bstrblobVal.pData);
LABEL_30:
        *(_OWORD *)&pvar->vt = 0;
        pvar->bstrblobVal.pData = 0;
        return v2;
      default:
        v2 = PropVariantClear((PROPVARIANT *)pvar);
        if ( (v2 & 0x80000000) == 0 )
          return v2;
LABEL_25:
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, pvar, v2);
        return v2;
    }
    CoTaskMemFree(pvar->bstrblobVal.pData);
    goto LABEL_30;
  }
  return result;
}

```

## disassembly

```asm
0x180029040  mov     [rsp+arg_18], rsi
0x180029045  push    rdi
0x180029046  sub     rsp, 50h
0x18002904a  mov     rax, cs:__security_cookie
0x180029051  xor     rax, rsp
0x180029054  mov     [rsp+58h+var_10], rax
0x180029059  mov     rsi, rcx
0x18002905c  xor     edi, edi
0x18002905e  movzx   ecx, word ptr [rcx]
0x180029061  xor     eax, eax
0x180029063  cmp     ax, cx
0x180029066  jnz     short loc_180029080
0x180029068  mov     rcx, [rsp+58h+var_10]
0x18002906d  xor     rcx, rsp; StackCookie
0x180029070  call    __security_check_cookie
0x180029075  mov     rsi, [rsp+58h+arg_18]
0x18002907a  add     rsp, 50h
0x18002907e  pop     rdi
0x18002907f  retn
0x180029080  mov     eax, ecx
0x180029082  mov     [rsp+58h+arg_8], rbx
0x180029087  sub     eax, 100Ch
0x18002908c  jz      loc_180029160
0x180029092  sub     eax, 1
0x180029095  jz      short loc_180029115
0x180029097  cmp     eax, 34h ; '4'
0x18002909a  jz      short loc_1800290B8
0x18002909c  mov     rcx, rsi; pvar
0x18002909f  call    cs:__imp_PropVariantClear
0x1800290a5  mov     edi, eax
0x1800290a7  test    eax, eax
0x1800290a9  js      loc_18002919B
0x1800290af  mov     rbx, [rsp+58h+arg_8]
0x1800290b4  mov     eax, edi
0x1800290b6  jmp     short loc_180029068
0x1800290b8  cmp     [rsi+10h], rdi
0x1800290bc  jnz     short loc_1800290D6
0x1800290be  mov     edi, 80004003h
0x1800290c3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800290ca  jb      short loc_1800290AF
0x1800290cc  mov     edx, 0Ah
0x1800290d1  jmp     loc_18002917D
0x1800290d6  mov     [rsp+58h+arg_10], rbp
0x1800290db  xor     ebp, ebp
0x1800290dd  cmp     [rsi+8], edi
0x1800290e0  jbe     short loc_180029101
0x1800290e2  mov     ebx, ebp
0x1800290e4  shl     rbx, 4
0x1800290e8  add     rbx, [rsi+10h]
0x1800290ec  mov     rcx, [rbx+8]; pv
0x1800290f0  call    cs:__imp_CoTaskMemFree
0x1800290f6  inc     ebp
0x1800290f8  mov     [rbx+8], rdi
0x1800290fc  cmp     [rsi+8], ebp
0x1800290ff  ja      short loc_1800290E2
0x180029101  mov     rcx, [rsi+10h]; pv
0x180029105  call    cs:__imp_CoTaskMemFree
0x18002910b  mov     rbp, [rsp+58h+arg_10]
0x180029110  jmp     loc_180029210
0x180029115  cmp     [rsi+10h], rdi
0x180029119  jnz     short loc_180029130
0x18002911b  mov     edi, 80004003h
0x180029120  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029127  jb      short loc_1800290AF
0x180029129  mov     edx, 0Ch
0x18002912e  jmp     short loc_18002917D
0x180029130  xor     ebx, ebx
0x180029132  cmp     [rsi+8], ebx
0x180029135  jbe     loc_180029206
0x18002913b  mov     rax, [rsi+10h]
0x18002913f  mov     rcx, [rax+rbx*8]
0x180029143  test    rcx, rcx
0x180029146  jz      short loc_180029154
0x180029148  mov     rax, [rcx]
0x18002914b  mov     rax, [rax+10h]
0x18002914f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029154  inc     ebx
0x180029156  cmp     [rsi+8], ebx
0x180029159  ja      short loc_18002913B
0x18002915b  jmp     loc_180029206
0x180029160  cmp     [rsi+10h], rdi
0x180029164  jnz     short loc_1800291D0
0x180029166  mov     edi, 80004003h
0x18002916b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029172  jb      loc_1800290AF
0x180029178  mov     edx, 0Bh
0x18002917d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029184  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x18002918b  mov     r9, rsi
0x18002918e  mov     [rsp+58h+var_38], edi
0x180029192  mov     rcx, [rcx+10h]
0x180029196  call    WPP_SF_qD
0x18002919b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800291a2  jb      loc_1800290AF
0x1800291a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800291af  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x1800291b6  mov     edx, 0Dh
0x1800291bb  mov     [rsp+58h+var_38], edi
0x1800291bf  mov     r9, rsi
0x1800291c2  mov     rcx, [rcx+10h]
0x1800291c6  call    WPP_SF_qD
0x1800291cb  jmp     loc_1800290AF
0x1800291d0  xor     ebx, ebx
0x1800291d2  cmp     [rsi+8], ebx
0x1800291d5  jbe     short loc_180029206
0x1800291d7  xorps   xmm0, xmm0
0x1800291da  lea     r8, [rsp+58h+var_28]; struct tagPROPVARIANT *
0x1800291df  xor     eax, eax
0x1800291e1  mov     edx, ebx; unsigned int
0x1800291e3  mov     rcx, rsi; this
0x1800291e6  mov     qword ptr [rsp+58h+var_28.___u0+10h], rax
0x1800291eb  movups  xmmword ptr [rsp+58h+var_28.___u0], xmm0
0x1800291f0  call    ?GetElementDataAsVariant@CMFPropVariant@@IEBAJKPEAUtagPROPVARIANT@@@Z; CMFPropVariant::GetElementDataAsVariant(ulong,tagPROPVARIANT *)
0x1800291f5  lea     rcx, [rsp+58h+var_28]; this
0x1800291fa  call    ??1CMFPropVariant@@QEAA@XZ; CMFPropVariant::~CMFPropVariant(void)
0x1800291ff  inc     ebx
0x180029201  cmp     [rsi+8], ebx
0x180029204  ja      short loc_1800291D7
0x180029206  mov     rcx, [rsi+10h]; pv
0x18002920a  call    cs:__imp_CoTaskMemFree
0x180029210  xorps   xmm0, xmm0
0x180029213  xor     eax, eax
0x180029215  movups  xmmword ptr [rsi], xmm0
0x180029218  mov     [rsi+10h], rax
0x18002921c  jmp     loc_1800290AF
```
