# CMFPropVariant::Clear(void)

- ea: `0x180071524`
- end: `0x180071709`
- name: `?Clear@CMFPropVariant@@QEAAJXZ`
- size: `485`
- prototype: `__int64 __fastcall(PROPVARIANT *pvar)`
- caller_count: `21`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000fe50`
- `0x18004f524`
- `0x18004fbe0`
- `0x180050454`
- `0x1800507a8`
- `0x180050fac`
- `0x1800515ec`
- `0x1800535e0`
- `0x180055180`
- `0x180056c5c`
- `0x180058260`
- `0x180066500`
- `0x1800671c8`
- `0x18006860c`
- `0x18006c404`
- `0x18006ecc0`
- `0x18007064c`
- `0x180070b18`
- `0x180071518`
- `0x180071710`
- `0x180073f40`

## callees

- `0x1800023e0`
- `0x180020d84`
- `0x180071518`
- `0x180071524`
- `0x180074290`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800715cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800716d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800715cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800716d3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180071578`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180071578`

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
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, pvar, -2147467261);
LABEL_25:
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, pvar, v1);
  return v1;
}

```

## disassembly

```asm
0x180071524  mov     [rsp+arg_8], rbx
0x180071529  mov     [rsp+arg_10], rbp
0x18007152e  push    rsi
0x18007152f  push    rdi
0x180071530  push    r14
0x180071532  sub     rsp, 50h
0x180071536  mov     rax, cs:__security_cookie
0x18007153d  xor     rax, rsp
0x180071540  mov     [rsp+68h+var_20], rax
0x180071545  xor     ebp, ebp
0x180071547  xor     eax, eax
0x180071549  mov     rsi, rcx
0x18007154c  cmp     ax, [rcx]
0x18007154f  jz      loc_1800716E5
0x180071555  movzx   ecx, word ptr [rcx]
0x180071558  lea     rbx, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x18007155f  sub     ecx, 100Ch
0x180071565  jz      loc_180071636
0x18007156b  sub     ecx, 1
0x18007156e  jz      short loc_1800715E5
0x180071570  cmp     ecx, 34h ; '4'
0x180071573  jz      short loc_18007158D
0x180071575  mov     rcx, rsi; pvar
0x180071578  call    cs:__imp_PropVariantClear
0x18007157e  mov     ebp, eax
0x180071580  test    eax, eax
0x180071582  jns     loc_1800716E5
0x180071588  jmp     loc_18007166F
0x18007158d  cmp     [rsi+10h], rax
0x180071591  jnz     short loc_1800715B1
0x180071593  mov     eax, 80004003h
0x180071598  mov     ebp, eax
0x18007159a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800715a1  jb      loc_1800716E5
0x1800715a7  mov     edx, 0Ah
0x1800715ac  jmp     loc_180071655
0x1800715b1  xor     r14d, r14d
0x1800715b4  cmp     [rsi+8], eax
0x1800715b7  jbe     loc_1800716CF
0x1800715bd  mov     rbx, [rsi+10h]
0x1800715c1  mov     edi, r14d
0x1800715c4  add     rdi, rdi
0x1800715c7  mov     rcx, [rbx+rdi*8+8]; pv
0x1800715cc  call    cs:__imp_CoTaskMemFree
0x1800715d2  inc     r14d
0x1800715d5  mov     [rbx+rdi*8+8], rbp
0x1800715da  cmp     [rsi+8], r14d
0x1800715de  ja      short loc_1800715BD
0x1800715e0  jmp     loc_1800716CF
0x1800715e5  cmp     [rsi+10h], rax
0x1800715e9  jnz     short loc_180071606
0x1800715eb  mov     eax, 80004003h
0x1800715f0  mov     ebp, eax
0x1800715f2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800715f9  jb      loc_1800716E5
0x1800715ff  mov     edx, 0Ch
0x180071604  jmp     short loc_180071655
0x180071606  xor     ebx, ebx
0x180071608  cmp     [rsi+8], eax
0x18007160b  jbe     loc_1800716CF
0x180071611  mov     rax, [rsi+10h]
0x180071615  mov     rcx, [rax+rbx*8]
0x180071619  test    rcx, rcx
0x18007161c  jz      short loc_18007162A
0x18007161e  mov     rax, [rcx]
0x180071621  mov     rax, [rax+10h]
0x180071625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007162a  inc     ebx
0x18007162c  cmp     [rsi+8], ebx
0x18007162f  ja      short loc_180071611
0x180071631  jmp     loc_1800716CF
0x180071636  cmp     [rsi+10h], rax
0x18007163a  jnz     short loc_180071699
0x18007163c  mov     eax, 80004003h
0x180071641  mov     ebp, eax
0x180071643  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007164a  jb      loc_1800716E5
0x180071650  mov     edx, 0Bh
0x180071655  mov     rcx, cs:WPP_GLOBAL_Control
0x18007165c  mov     r9, rsi
0x18007165f  mov     r8, rbx
0x180071662  mov     [rsp+68h+var_48], eax
0x180071666  mov     rcx, [rcx+10h]
0x18007166a  call    WPP_SF_qD
0x18007166f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071676  jb      short loc_1800716E5
0x180071678  mov     rcx, cs:WPP_GLOBAL_Control
0x18007167f  mov     edx, 0Dh
0x180071684  mov     r9, rsi
0x180071687  mov     [rsp+68h+var_48], ebp
0x18007168b  mov     r8, rbx
0x18007168e  mov     rcx, [rcx+10h]
0x180071692  call    WPP_SF_qD
0x180071697  jmp     short loc_1800716E5
0x180071699  xor     ebx, ebx
0x18007169b  cmp     [rsi+8], eax
0x18007169e  jbe     short loc_1800716CF
0x1800716a0  xorps   xmm0, xmm0
0x1800716a3  lea     r8, [rsp+68h+var_38]; struct tagPROPVARIANT *
0x1800716a8  xor     eax, eax
0x1800716aa  mov     edx, ebx; unsigned int
0x1800716ac  mov     rcx, rsi; this
0x1800716af  mov     qword ptr [rsp+68h+var_38+10h], rax
0x1800716b4  movups  xmmword ptr [rsp+68h+var_38], xmm0
0x1800716b9  call    ?GetElementDataAsVariant@CMFPropVariant@@IEBAJKPEAUtagPROPVARIANT@@@Z; CMFPropVariant::GetElementDataAsVariant(ulong,tagPROPVARIANT *)
0x1800716be  lea     rcx, [rsp+68h+var_38]; this
0x1800716c3  call    ??1CMFPropVariant@@QEAA@XZ; CMFPropVariant::~CMFPropVariant(void)
0x1800716c8  inc     ebx
0x1800716ca  cmp     [rsi+8], ebx
0x1800716cd  ja      short loc_1800716A0
0x1800716cf  mov     rcx, [rsi+10h]; pv
0x1800716d3  call    cs:__imp_CoTaskMemFree
0x1800716d9  xorps   xmm0, xmm0
0x1800716dc  xor     eax, eax
0x1800716de  movups  xmmword ptr [rsi], xmm0
0x1800716e1  mov     [rsi+10h], rax
0x1800716e5  mov     eax, ebp
0x1800716e7  mov     rcx, [rsp+68h+var_20]
0x1800716ec  xor     rcx, rsp; StackCookie
0x1800716ef  call    __security_check_cookie
0x1800716f4  lea     r11, [rsp+68h+var_18]
0x1800716f9  mov     rbx, [r11+28h]
0x1800716fd  mov     rbp, [r11+30h]
0x180071701  mov     rsp, r11
0x180071704  pop     r14
0x180071706  pop     rdi
0x180071707  pop     rsi
0x180071708  retn
```
