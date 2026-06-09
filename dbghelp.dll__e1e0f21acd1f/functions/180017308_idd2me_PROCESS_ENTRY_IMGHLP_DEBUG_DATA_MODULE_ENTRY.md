# idd2me(_PROCESS_ENTRY *,_IMGHLP_DEBUG_DATA *,_MODULE_ENTRY *)

- ea: `0x180017308`
- end: `0x18001792a`
- name: `?idd2me@@YAHPEAU_PROCESS_ENTRY@@PEAU_IMGHLP_DEBUG_DATA@@PEAU_MODULE_ENTRY@@@Z`
- size: `1570`
- prototype: `__int64 __fastcall(struct _PROCESS_ENTRY *, struct _IMGHLP_DEBUG_DATA *, struct _MODULE_ENTRY *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18000f380`

## callees

- `0x180006fe0`
- `0x180008a38`
- `0x180008ad0`
- `0x180008d0c`
- `0x18000982c`
- `0x18000dfac`
- `0x180016c04`
- `0x180017308`
- `0x180017930`
- `0x180021374`
- `0x180023704`
- `0x180169420`
- `0x18019dc80`
- `0x18019e5c4`
- `0x1801abbb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180017528`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180017528`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001738e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001738e`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800175bc`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800175bc`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180017569`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180017569`

## string_xrefs

- `0x18001735e`: `%s is already loaded at %I64x\n`

## pseudocode

```c
__int64 __fastcall idd2me(struct _PROCESS_ENTRY *a1, struct _IMGHLP_DEBUG_DATA *a2, struct _MODULE_ENTRY *a3)
{
  __int64 v6; // rcx
  __int64 v7; // r8
  __int16 v9; // cx
  unsigned __int16 *v10; // rax
  wchar_t *v11; // rcx
  unsigned __int16 *v12; // rax
  int *v13; // rcx
  const wchar_t *v14; // rax
  unsigned int v15; // eax
  void *v16; // rax
  __int64 v17; // r8
  void *v18; // rax
  void *v19; // rax
  __int64 v20; // rax
  void *v21; // rax
  const void **v22; // rsi
  __int64 v23; // rax
  void *v24; // rax
  int ExportSymbols; // eax
  int v26; // edx
  __int64 v27; // rax
  __int128 v28; // xmm0
  __int64 **i; // rdi
  const wchar_t *v30; // rcx
  __int64 v31; // rax
  DWORD flOldProtect; // [rsp+88h] [rbp+10h] BYREF

  flOldProtect = 0;
  *((_DWORD *)a2 + 1056) = *((_DWORD *)a3 + 4842);
  if ( !*((_QWORD *)a3 + 3) )
  {
    if ( GetModuleForDLLBase(a1, *((_QWORD *)a2 + 4)) )
    {
      if ( (unsigned int)spew() )
      {
        if ( v6 )
          _pwprint(a1, L"%s is already loaded at %I64x\n", v7 + 46, v6);
        else
          _pwprint(a1, L"No base address for %s:  Please specify\n", *((_QWORD *)a3 + 38));
      }
      SetLastError(0x1E7u);
      diaRelease(a3, *((DIA **)a2 + 527));
      *((_QWORD *)a2 + 527) = 0;
      *((_QWORD *)a3 + 2434) = 0;
      return 0;
    }
    *((_QWORD *)a3 + 3) = *((_QWORD *)a2 + 4);
  }
  if ( !*((_DWORD *)a3 + 8) )
    *((_DWORD *)a3 + 8) = *((_DWORD *)a2 + 10);
  *((_QWORD *)a3 + 2427) = *((_QWORD *)a2 + 449);
  *((_QWORD *)a3 + 2428) = *((_QWORD *)a2 + 3);
  *((_DWORD *)a3 + 10) = *((_DWORD *)a2 + 11);
  *((_DWORD *)a3 + 9) = *((_DWORD *)a2 + 12);
  v9 = *((_WORD *)a2 + 28);
  *((_WORD *)a3 + 22) = v9;
  *((_DWORD *)a3 + 6048) = *((_DWORD *)a2 + 1220);
  *((_DWORD *)a3 + 6054) = *((_DWORD *)a2 + 1221);
  *((_DWORD *)a3 + 6049) = *((_DWORD *)a2 + 1216);
  *((_DWORD *)a3 + 82) = *((_DWORD *)a2 + 826);
  *((_DWORD *)a3 + 84) = *((_DWORD *)a2 + 828);
  *((_DWORD *)a3 + 83) = *((_DWORD *)a2 + 827);
  if ( !v9 && dword_1802AF888 )
    *((_WORD *)a3 + 22) = dword_1802AF888;
  if ( *((_QWORD *)a2 + 527) )
  {
    if ( *((_DWORD *)a3 + 6041) != 8 )
    {
      v10 = StringDup((wchar_t *)a2 + 1130);
      *((_QWORD *)a3 + 40) = v10;
      if ( !v10 )
        return 0;
    }
  }
  if ( *((_QWORD *)a2 + 276) )
  {
    v11 = (wchar_t *)((char *)a2 + 1154);
  }
  else
  {
    v11 = (wchar_t *)((char *)a2 + 58);
    if ( !*((_WORD *)a2 + 29) )
    {
      v11 = (wchar_t *)((char *)a2 + 2260);
      if ( !*((_QWORD *)a2 + 527) )
        v11 = (wchar_t *)&word_18022B134;
    }
  }
  v12 = StringDup(v11);
  *((_QWORD *)a3 + 39) = v12;
  if ( !v12 )
    return 0;
  if ( *((_DWORD *)a2 + 895) )
    *((_DWORD *)a3 + 4842) |= 4u;
  if ( !*((_QWORD *)a3 + 38) )
  {
    v14 = StringDup((wchar_t *)a2 + 290);
    *((_QWORD *)a3 + 38) = v14;
    if ( !v14 )
      return 0;
    _wsplitpath_s(v14, 0, 0, 0, 0, (wchar_t *)a3 + 23, 0x40u, 0, 0);
    if ( **((_WORD **)a3 + 38) )
      *((_WORD *)a3 + 87) = 0;
  }
  *((_DWORD *)a3 + 4859) = *((_DWORD *)a2 + 1039);
  v15 = *((_DWORD *)a2 + 848);
  if ( v15 )
  {
    v16 = VirtualAlloc(0, 16LL * v15, 0x1000u, 4u);
    *((_QWORD *)a3 + 308) = v16;
    if ( v16 )
    {
      v17 = *((unsigned int *)a2 + 848);
      *((_DWORD *)a3 + 626) = v17;
      memcpy_0(v16, *((const void **)a2 + 423), 16 * v17);
      VirtualProtect(*((LPVOID *)a3 + 308), 16LL * *((unsigned int *)a3 + 626), 2u, &flOldProtect);
    }
  }
  if ( *((_QWORD *)a2 + 426) )
  {
    v18 = (void *)pMemAlloc(*((unsigned int *)a2 + 888));
    *((_QWORD *)a3 + 311) = v18;
    if ( v18 )
    {
      *((_DWORD *)a3 + 627) = *((_DWORD *)a2 + 854);
      *((_DWORD *)a3 + 629) = *((_DWORD *)a2 + 888);
      *((_DWORD *)a3 + 631) = 0;
      memcpy_0(v18, *((const void **)a2 + 426), *((unsigned int *)a2 + 888));
    }
  }
  if ( *((_QWORD *)a2 + 429) )
  {
    v19 = (void *)pMemAlloc(*((unsigned int *)a2 + 889));
    *((_QWORD *)a3 + 312) = v19;
    if ( v19 )
    {
      *((_DWORD *)a3 + 628) = *((_DWORD *)a2 + 860);
      *((_DWORD *)a3 + 630) = *((_DWORD *)a2 + 889);
      *((_DWORD *)a3 + 632) = 0;
      memcpy_0(v19, *((const void **)a2 + 429), *((unsigned int *)a2 + 889));
    }
  }
  v20 = *((unsigned int *)a2 + 884);
  *((_DWORD *)a3 + 614) = v20;
  if ( *((_BYTE *)a2 + 3520) )
  {
    v21 = (void *)pMemAlloc(40 * v20);
    *((_QWORD *)a3 + 306) = v21;
    v22 = (const void **)((char *)a2 + 3528);
    if ( v21 )
      memcpy_0(v21, *v22, 40LL * *((unsigned int *)a3 + 614));
  }
  else
  {
    v22 = (const void **)((char *)a2 + 3528);
    *((_QWORD *)a3 + 306) = *((_QWORD *)a2 + 441);
  }
  if ( *((_QWORD *)a2 + 439) )
  {
    *((_DWORD *)a3 + 4848) = *((_DWORD *)a2 + 892);
    *((_QWORD *)a3 + 2423) = *((_QWORD *)a2 + 439);
  }
  else
  {
    v23 = *((unsigned int *)a3 + 614);
    *((_DWORD *)a3 + 4848) = v23;
    v24 = (void *)pMemAlloc(40 * v23);
    *((_QWORD *)a3 + 2423) = v24;
    if ( v24 )
      memcpy_0(v24, *v22, 40LL * *((unsigned int *)a3 + 614));
  }
  if ( *((_QWORD *)a2 + 527) )
  {
    *((_DWORD *)a3 + 599) = 3;
    *((_DWORD *)a3 + 600) = 3;
    *((_DWORD *)a3 + 4952) = 1;
  }
  else
  {
    if ( *((_QWORD *)a2 + 416) )
      *((_DWORD *)a3 + 4952) = LoadCodeViewSymbols(*((void **)a3 + 2427), a3, a2);
    ExportSymbols = *((_DWORD *)a3 + 4952);
    if ( !ExportSymbols )
    {
      if ( !*((_QWORD *)a2 + 419)
        || (ExportSymbols = LoadCoffSymbols(v13, a3, a2), (*((_DWORD *)a3 + 4952) = ExportSymbols) == 0) )
      {
        if ( *((_DWORD *)a2 + 1064)
          && (ExportSymbols = LoadExportSymbols(a3, a2), (*((_DWORD *)a3 + 4952) = ExportSymbols) != 0) )
        {
          *((_DWORD *)a3 + 84) = 0;
        }
        else
        {
          ExportSymbols = 0;
        }
      }
    }
    v13 = (int *)((char *)a3 + 2396);
    if ( *((_DWORD *)a2 + 826) == 7 )
    {
      *v13 = 8;
      ExportSymbols = 1;
      *((_DWORD *)a3 + 4952) = 1;
    }
    v26 = *v13;
    *((_DWORD *)a3 + 600) = *v13;
    if ( !ExportSymbols )
    {
      *v13 = 0;
      if ( v26 == 5 )
        *((_DWORD *)a3 + 600) = 0;
    }
  }
  v27 = *((_QWORD *)a2 + 527);
  *((_QWORD *)a3 + 2434) = v27;
  if ( v27 )
  {
    *((_DWORD *)a3 + 4958) = *((_DWORD *)a2 + 1204);
    *((_DWORD *)a3 + 4957) = *((_DWORD *)a2 + 1203);
    v28 = *(_OWORD *)((char *)a2 + 4820);
  }
  else
  {
    *((_DWORD *)a3 + 4958) = *((_DWORD *)a2 + 558);
    *((_DWORD *)a3 + 4957) = *((_DWORD *)a2 + 557);
    v28 = *(_OWORD *)((char *)a2 + 2244);
  }
  *(_OWORD *)((char *)a3 + 19836) = v28;
  iddcv2me((struct _PROCESS_ENTRY *)v13, a2, a3);
  *((_DWORD *)a3 + 4967) = *((_DWORD *)a2 + 1212);
  *((_DWORD *)a3 + 4964) = *((_DWORD *)a2 + 1209);
  *((_DWORD *)a3 + 4965) = *((_DWORD *)a2 + 1210);
  *((_DWORD *)a3 + 4966) = *((_DWORD *)a2 + 1211);
  *((_DWORD *)a3 + 4967) = *((_DWORD *)a2 + 1212);
  *((_DWORD *)a3 + 4968) = *((_DWORD *)a2 + 1213);
  *((_DWORD *)a3 + 4969) = *((_DWORD *)a2 + 1214);
  *((_DWORD *)a3 + 4970) = *((_DWORD *)a2 + 1215);
  ProcessOmapForModule(a3, a2);
  *((_DWORD *)a3 + 4842) &= ~1u;
  for ( i = (__int64 **)*((_QWORD *)a2 + 609); i; i = (__int64 **)*i )
  {
    v30 = (const wchar_t *)i[1];
    v31 = -1;
    do
      ++v31;
    while ( v30[v31] );
    if ( (int)v31 >= 10 && !wmemcmp(v30, L"/remapinfo", 0xAu) )
      RegisterRemapInfoStream(a3, (const unsigned __int16 *)i[1]);
  }
  return 1;
}

```

## disassembly

```asm
0x180017308  mov     rax, rsp
0x18001730b  push    rbx
0x18001730c  push    rbp
0x18001730d  push    rsi
0x18001730e  push    rdi
0x18001730f  sub     rsp, 58h
0x180017313  xor     ebp, ebp
0x180017315  mov     rbx, r8
0x180017318  mov     [rax+10h], ebp
0x18001731b  mov     rdi, rdx
0x18001731e  mov     eax, [r8+4BA8h]
0x180017325  mov     rsi, rcx
0x180017328  mov     [rdx+1080h], eax
0x18001732e  cmp     [r8+18h], rbp
0x180017332  jnz     loc_1800173C0
0x180017338  mov     rdx, [rdx+20h]; unsigned __int64
0x18001733c  call    ?GetModuleForDLLBase@@YAPEAU_MODULE_ENTRY@@PEAU_PROCESS_ENTRY@@_K@Z; GetModuleForDLLBase(_PROCESS_ENTRY *,unsigned __int64)
0x180017341  mov     rcx, [rdi+20h]
0x180017345  mov     r8, rax
0x180017348  test    rax, rax
0x18001734b  jz      short loc_1800173BC
0x18001734d  call    ?spew@@YAHXZ; spew(void)
0x180017352  test    eax, eax
0x180017354  jz      short loc_180017389
0x180017356  test    rcx, rcx
0x180017359  jz      short loc_180017373
0x18001735b  mov     r9, rcx
0x18001735e  lea     rdx, aSIsAlreadyLoad; "%s is already loaded at %I64x\n"
0x180017365  mov     rcx, rsi; struct _PROCESS_ENTRY *
0x180017368  add     r8, 2Eh ; '.'
0x18001736c  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x180017371  jmp     short loc_180017389
0x180017373  mov     r8, [rbx+130h]
0x18001737a  lea     rdx, aNoBaseAddressF; "No base address for %s:  Please specify"...
0x180017381  mov     rcx, rsi; struct _PROCESS_ENTRY *
0x180017384  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x180017389  mov     ecx, 1E7h; dwErrCode
0x18001738e  call    cs:__imp_SetLastError
0x180017394  mov     rdx, [rdi+1078h]; void *
0x18001739b  mov     rcx, rbx; struct _MODULE_ENTRY *
0x18001739e  call    ?diaRelease@@YAXPEAU_MODULE_ENTRY@@PEAX@Z; diaRelease(_MODULE_ENTRY *,void *)
0x1800173a3  mov     [rdi+1078h], rbp
0x1800173aa  mov     [rbx+4C10h], rbp
0x1800173b1  xor     eax, eax
0x1800173b3  add     rsp, 58h
0x1800173b7  pop     rdi
0x1800173b8  pop     rsi
0x1800173b9  pop     rbp
0x1800173ba  pop     rbx
0x1800173bb  retn
0x1800173bc  mov     [rbx+18h], rcx
0x1800173c0  cmp     [rbx+20h], ebp
0x1800173c3  jnz     short loc_1800173CB
0x1800173c5  mov     eax, [rdi+28h]
0x1800173c8  mov     [rbx+20h], eax
0x1800173cb  mov     rax, [rdi+0E08h]
0x1800173d2  mov     [rbx+4BD8h], rax
0x1800173d9  mov     rax, [rdi+18h]
0x1800173dd  mov     [rbx+4BE0h], rax
0x1800173e4  mov     eax, [rdi+2Ch]
0x1800173e7  mov     [rbx+28h], eax
0x1800173ea  mov     eax, [rdi+30h]
0x1800173ed  mov     [rbx+24h], eax
0x1800173f0  movzx   ecx, word ptr [rdi+38h]
0x1800173f4  mov     [rbx+2Ch], cx
0x1800173f8  mov     eax, [rdi+1310h]
0x1800173fe  mov     [rbx+5E80h], eax
0x180017404  mov     eax, [rdi+1314h]
0x18001740a  mov     [rbx+5E98h], eax
0x180017410  mov     eax, [rdi+1300h]
0x180017416  mov     [rbx+5E84h], eax
0x18001741c  mov     eax, [rdi+0CE8h]
0x180017422  mov     [rbx+148h], eax
0x180017428  mov     eax, [rdi+0CF0h]
0x18001742e  mov     [rbx+150h], eax
0x180017434  mov     eax, [rdi+0CECh]
0x18001743a  mov     [rbx+14Ch], eax
0x180017440  test    cx, cx
0x180017443  jnz     short loc_180017453
0x180017445  mov     eax, cs:dword_1802AF888
0x18001744b  test    eax, eax
0x18001744d  jz      short loc_180017453
0x18001744f  mov     [rbx+2Ch], ax
0x180017453  cmp     [rdi+1078h], rbp
0x18001745a  jz      short loc_180017481
0x18001745c  cmp     dword ptr [rbx+5E64h], 8
0x180017463  jz      short loc_180017481
0x180017465  lea     rcx, [rdi+8D4h]; Source
0x18001746c  call    ?StringDup@@YAPEAGPEBG@Z; StringDup(ushort const *)
0x180017471  mov     [rbx+140h], rax
0x180017478  test    rax, rax
0x18001747b  jz      loc_1800173B1
0x180017481  cmp     [rdi+8A0h], rbp
0x180017488  jz      short loc_180017493
0x18001748a  lea     rcx, [rdi+482h]
0x180017491  jmp     short loc_1800174B3
0x180017493  lea     rcx, [rdi+3Ah]
0x180017497  cmp     [rcx], bp
0x18001749a  jnz     short loc_1800174B3
0x18001749c  lea     rcx, [rdi+8D4h]
0x1800174a3  cmp     [rdi+1078h], rbp
0x1800174aa  jnz     short loc_1800174B3
0x1800174ac  lea     rcx, word_18022B134; Source
0x1800174b3  call    ?StringDup@@YAPEAGPEBG@Z; StringDup(ushort const *)
0x1800174b8  mov     [rbx+138h], rax
0x1800174bf  test    rax, rax
0x1800174c2  jz      loc_1800173B1
0x1800174c8  cmp     [rdi+0DFCh], ebp
0x1800174ce  jz      short loc_1800174D7
0x1800174d0  or      dword ptr [rbx+4BA8h], 4
0x1800174d7  cmp     [rbx+130h], rbp
0x1800174de  jnz     short loc_180017541
0x1800174e0  lea     rcx, [rdi+244h]; Source
0x1800174e7  call    ?StringDup@@YAPEAGPEBG@Z; StringDup(ushort const *)
0x1800174ec  mov     [rbx+130h], rax
0x1800174f3  test    rax, rax
0x1800174f6  jz      loc_1800173B1
0x1800174fc  mov     [rsp+78h+ExtCount], rbp; ExtCount
0x180017501  lea     rcx, [rbx+2Eh]
0x180017505  mov     [rsp+78h+Ext], rbp; Ext
0x18001750a  xor     r9d, r9d; Dir
0x18001750d  mov     [rsp+78h+FilenameCount], 40h ; '@'; FilenameCount
0x180017516  xor     r8d, r8d; DriveCount
0x180017519  mov     [rsp+78h+Filename], rcx; Filename
0x18001751e  xor     edx, edx; Drive
0x180017520  mov     rcx, rax; FullPath
0x180017523  mov     [rsp+78h+DirCount], rbp; DirCount
0x180017528  call    cs:__imp__wsplitpath_s
0x18001752e  mov     rax, [rbx+130h]
0x180017535  cmp     [rax], bp
0x180017538  jz      short loc_180017541
0x18001753a  mov     [rbx+0AEh], bp
0x180017541  mov     eax, [rdi+103Ch]
0x180017547  mov     [rbx+4BECh], eax
0x18001754d  mov     eax, [rdi+0D40h]
0x180017553  test    eax, eax
0x180017555  jz      short loc_1800175C2
0x180017557  xor     ecx, ecx; lpAddress
0x180017559  mov     edx, eax
0x18001755b  shl     rdx, 4; dwSize
0x18001755f  mov     r8d, 1000h; flAllocationType
0x180017565  lea     r9d, [rcx+4]; flProtect
0x180017569  call    cs:__imp_VirtualAlloc
0x18001756f  mov     [rbx+9A0h], rax
0x180017576  test    rax, rax
0x180017579  jz      short loc_1800175C2
0x18001757b  mov     ecx, [rdi+0D40h]
0x180017581  mov     r8d, ecx
0x180017584  mov     [rbx+9C8h], ecx
0x18001758a  mov     rdx, [rdi+0D38h]; Src
0x180017591  mov     rcx, rax; void *
0x180017594  shl     r8, 4; Size
0x180017598  call    memcpy_0
0x18001759d  mov     edx, [rbx+9C8h]
0x1800175a3  lea     r9, [rsp+78h+flOldProtect]; lpflOldProtect
0x1800175ab  mov     rcx, [rbx+9A0h]; lpAddress
0x1800175b2  mov     r8d, 2; flNewProtect
0x1800175b8  shl     rdx, 4; dwSize
0x1800175bc  call    cs:__imp_VirtualProtect
0x1800175c2  cmp     [rdi+0D50h], rbp
0x1800175c9  jz      short loc_180017616
0x1800175cb  mov     ecx, [rdi+0DE0h]; dwBytes
0x1800175d1  call    pMemAlloc
0x1800175d6  mov     [rbx+9B8h], rax
0x1800175dd  test    rax, rax
0x1800175e0  jz      short loc_180017616
0x1800175e2  mov     ecx, [rdi+0D58h]
0x1800175e8  mov     [rbx+9CCh], ecx
0x1800175ee  mov     ecx, [rdi+0DE0h]
0x1800175f4  mov     [rbx+9D4h], ecx
0x1800175fa  mov     rcx, rax; void *
0x1800175fd  mov     [rbx+9DCh], ebp
0x180017603  mov     r8d, [rdi+0DE0h]; Size
0x18001760a  mov     rdx, [rdi+0D50h]; Src
0x180017611  call    memcpy_0
0x180017616  cmp     [rdi+0D68h], rbp
0x18001761d  jz      short loc_18001766A
0x18001761f  mov     ecx, [rdi+0DE4h]; dwBytes
0x180017625  call    pMemAlloc
0x18001762a  mov     [rbx+9C0h], rax
0x180017631  test    rax, rax
0x180017634  jz      short loc_18001766A
0x180017636  mov     ecx, [rdi+0D70h]
0x18001763c  mov     [rbx+9D0h], ecx
0x180017642  mov     ecx, [rdi+0DE4h]
0x180017648  mov     [rbx+9D8h], ecx
0x18001764e  mov     rcx, rax; void *
0x180017651  mov     [rbx+9E0h], ebp
0x180017657  mov     r8d, [rdi+0DE4h]; Size
0x18001765e  mov     rdx, [rdi+0D68h]; Src
0x180017665  call    memcpy_0
0x18001766a  mov     eax, [rdi+0DD0h]
0x180017670  mov     [rbx+998h], eax
0x180017676  cmp     [rdi+0DC0h], bpl
0x18001767d  jz      short loc_1800176BA
0x18001767f  lea     rcx, [rax+rax*4]
0x180017683  shl     rcx, 3; dwBytes
0x180017687  call    pMemAlloc
0x18001768c  mov     [rbx+990h], rax
0x180017693  lea     rsi, [rdi+0DC8h]
0x18001769a  test    rax, rax
0x18001769d  jz      short loc_1800176CB
0x18001769f  mov     ecx, [rbx+998h]
0x1800176a5  mov     rdx, [rsi]; Src
0x1800176a8  lea     r8, [rcx+rcx*4]
0x1800176ac  mov     rcx, rax; void *
0x1800176af  shl     r8, 3; Size
0x1800176b3  call    memcpy_0
0x1800176b8  jmp     short loc_1800176CB
0x1800176ba  lea     rsi, [rdi+0DC8h]
0x1800176c1  mov     rax, [rsi]
0x1800176c4  mov     [rbx+990h], rax
0x1800176cb  cmp     [rdi+0DB8h], rbp
0x1800176d2  jz      short loc_1800176F0
0x1800176d4  mov     eax, [rdi+0DF0h]
0x1800176da  mov     [rbx+4BC0h], eax
0x1800176e0  mov     rax, [rdi+0DB8h]
0x1800176e7  mov     [rbx+4BB8h], rax
0x1800176ee  jmp     short loc_18001772E
0x1800176f0  mov     eax, [rbx+998h]
0x1800176f6  mov     [rbx+4BC0h], eax
0x1800176fc  lea     rcx, [rax+rax*4]
0x180017700  shl     rcx, 3; dwBytes
0x180017704  call    pMemAlloc
0x180017709  mov     [rbx+4BB8h], rax
0x180017710  test    rax, rax
0x180017713  jz      short loc_18001772E
0x180017715  mov     ecx, [rbx+998h]
0x18001771b  mov     rdx, [rsi]; Src
0x18001771e  lea     r8, [rcx+rcx*4]
0x180017722  mov     rcx, rax; void *
0x180017725  shl     r8, 3; Size
0x180017729  call    memcpy_0
0x18001772e  cmp     [rdi+1078h], rbp
0x180017735  jz      short loc_180017756
0x180017737  mov     eax, 3
0x18001773c  mov     [rbx+95Ch], eax
0x180017742  mov     [rbx+960h], eax
0x180017748  lea     esi, [rax-2]
0x18001774b  mov     [rbx+4D60h], esi
0x180017751  jmp     loc_180017802
0x180017756  cmp     [rdi+0D00h], rbp
0x18001775d  jz      short loc_180017777
0x18001775f  mov     rcx, [rbx+4BD8h]; void *
0x180017766  mov     r8, rdi; struct _IMGHLP_DEBUG_DATA *
0x180017769  mov     rdx, rbx; struct _MODULE_ENTRY *
0x18001776c  call    ?LoadCodeViewSymbols@@YAHPEAXPEAU_MODULE_ENTRY@@PEAU_IMGHLP_DEBUG_DATA@@@Z; LoadCodeViewSymbols(void *,_MODULE_ENTRY *,_IMGHLP_DEBUG_DATA *)
0x180017771  mov     [rbx+4D60h], eax
0x180017777  mov     eax, [rbx+4D60h]
0x18001777d  test    eax, eax
0x18001777f  jnz     short loc_1800177C6
0x180017781  cmp     [rdi+0D18h], rbp
0x180017788  jz      short loc_18001779F
0x18001778a  mov     r8, rdi; struct _IMGHLP_DEBUG_DATA *
0x18001778d  mov     rdx, rbx; struct _MODULE_ENTRY *
0x180017790  call    ?LoadCoffSymbols@@YAHPEAXPEAU_MODULE_ENTRY@@PEAU_IMGHLP_DEBUG_DATA@@@Z; LoadCoffSymbols(void *,_MODULE_ENTRY *,_IMGHLP_DEBUG_DATA *)
0x180017795  mov     [rbx+4D60h], eax
0x18001779b  test    eax, eax
0x18001779d  jnz     short loc_1800177C6
0x18001779f  cmp     [rdi+10A0h], ebp
0x1800177a5  jz      short loc_1800177C4
0x1800177a7  mov     rdx, rdi; struct _IMGHLP_DEBUG_DATA *
0x1800177aa  mov     rcx, rbx; struct _MODULE_ENTRY *
0x1800177ad  call    ?LoadExportSymbols@@YAKPEAU_MODULE_ENTRY@@PEAU_IMGHLP_DEBUG_DATA@@@Z; LoadExportSymbols(_MODULE_ENTRY *,_IMGHLP_DEBUG_DATA *)
0x1800177b2  mov     [rbx+4D60h], eax
0x1800177b8  test    eax, eax
0x1800177ba  jz      short loc_1800177C4
0x1800177bc  mov     [rbx+150h], ebp
0x1800177c2  jmp     short loc_1800177C6
0x1800177c4  mov     eax, ebp
0x1800177c6  cmp     dword ptr [rdi+0CE8h], 7
0x1800177cd  lea     rcx, [rbx+95Ch]; struct _PROCESS_ENTRY *
0x1800177d4  mov     esi, 1
0x1800177d9  jnz     short loc_1800177E9
0x1800177db  mov     dword ptr [rcx], 8
0x1800177e1  mov     eax, esi
0x1800177e3  mov     [rbx+4D60h], esi
0x1800177e9  mov     edx, [rcx]
0x1800177eb  mov     [rbx+960h], edx
0x1800177f1  test    eax, eax
0x1800177f3  jnz     short loc_180017802
0x1800177f5  mov     [rcx], ebp
0x1800177f7  cmp     edx, 5
0x1800177fa  jnz     short loc_180017802
0x1800177fc  mov     [rbx+960h], ebp
0x180017802  mov     rax, [rdi+1078h]
0x180017809  mov     [rbx+4C10h], rax
0x180017810  test    rax, rax
0x180017813  jz      short loc_180017836
0x180017815  mov     eax, [rdi+12D0h]
0x18001781b  mov     [rbx+4D78h], eax
0x180017821  mov     eax, [rdi+12CCh]
0x180017827  mov     [rbx+4D74h], eax
0x18001782d  movups  xmm0, xmmword ptr [rdi+12D4h]
0x180017834  jmp     short loc_180017855
0x180017836  mov     eax, [rdi+8B8h]
0x18001783c  mov     [rbx+4D78h], eax
0x180017842  mov     eax, [rdi+8B4h]
0x180017848  mov     [rbx+4D74h], eax
0x18001784e  movups  xmm0, xmmword ptr [rdi+8C4h]
  ... truncated ...
```
