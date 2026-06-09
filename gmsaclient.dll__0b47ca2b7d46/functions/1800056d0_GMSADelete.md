# GMSADelete

- ea: `0x1800056d0`
- end: `0x180005a9c`
- name: `GMSADelete`
- size: `972`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002a64`
- `0x180002b18`
- `0x18000461c`
- `0x1800056d0`
- `0x180006280`
- `0x1800062b0`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005895`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005914`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800059ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005895`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005914`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800059ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a58`
- `ntdll!RtlReleaseResource` at `0x180005802`
- `ntdll!RtlReleaseResource` at `0x1800059da`
- `ntdll!RtlReleaseResource` at `0x180005802`
- `ntdll!RtlReleaseResource` at `0x1800059da`
- `ntdll!RtlAcquireResourceExclusive` at `0x180005824`
- `ntdll!RtlAcquireResourceExclusive` at `0x180005824`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180005813`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180005813`

## pseudocode

```c
__int64 __fastcall GMSADelete(struct _UNICODE_STRING *a1, _DWORD *a2)
{
  unsigned __int16 *v3; // rdi
  int v5; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  int v8; // eax
  _QWORD *v9; // rbx
  __int64 v10; // rcx
  _QWORD *v11; // rax
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  int v17; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  HLOCAL v22; // [rsp+40h] [rbp-20h] BYREF
  HLOCAL v23; // [rsp+48h] [rbp-18h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-10h] BYREF
  int v25; // [rsp+A8h] [rbp+48h] BYREF
  HLOCAL v26; // [rsp+B0h] [rbp+50h] BYREF
  unsigned __int16 *v27; // [rsp+B8h] [rbp+58h] BYREF

  v25 = 0;
  v3 = 0;
  v26 = 0;
  v23 = 0;
  v22 = 0;
  v27 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_70b8577d707437755865c965214ce19a_Traceguids);
  *a2 = 0;
  v5 = GmsapParseAccountNamesLocally(
         0,
         a1,
         0,
         (unsigned __int16 **)&v26,
         (unsigned __int16 **)&v23,
         (unsigned __int16 **)&v22,
         &v25);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v8 = GmsapCrackDomainName(0, 0, (const unsigned __int16 *)v22, 0, &v27, 0);
    v6 = v8;
    if ( v8 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        v3 = v27;
        goto LABEL_46;
      }
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        111,
        &WPP_70b8577d707437755865c965214ce19a_Traceguids,
        (unsigned int)v8);
      v3 = v27;
      goto LABEL_45;
    }
    while ( 1 )
    {
      RtlAcquireResourceExclusive(&Resource, 1u);
      if ( !_InterlockedCompareExchange(&dword_18000B670, 0, 0) )
        break;
      RtlReleaseResource(&Resource);
      Sleep(1u);
    }
    hMem = 0;
    GmsapCheckGMSAInList(
      (const unsigned __int16 *)v26,
      (const unsigned __int16 *)v23,
      (const unsigned __int16 *)v22,
      (struct _tagGMsaListEntry **)&hMem);
    v9 = hMem;
    if ( hMem )
    {
      *a2 = 1;
      v10 = *v9;
      if ( *(_QWORD **)(*v9 + 8LL) != v9 || (v11 = (_QWORD *)v9[1], (_QWORD *)*v11 != v9) )
        __fastfail(3u);
      *v11 = v10;
      *(_QWORD *)(v10 + 8) = v11;
      v12 = (void *)v9[2];
      if ( v12 )
      {
        LocalFree(v12);
        v9[2] = 0;
      }
      v13 = (void *)v9[3];
      if ( v13 )
      {
        LocalFree(v13);
        v9[3] = 0;
      }
      v14 = (void *)v9[4];
      if ( v14 )
      {
        LocalFree(v14);
        v9[4] = 0;
      }
      v15 = (void *)v9[8];
      if ( v15 )
      {
        LocalFree(v15);
        v9[8] = 0;
        v9[9] = 0;
      }
      v16 = (void *)v9[10];
      if ( v16 )
      {
        LocalFree(v16);
        v9[10] = 0;
        v9[11] = 0;
      }
      LocalFree(v9);
      (*((void (**)(void))&xmmword_18000B5A0 + 1))();
    }
    v3 = v27;
    v17 = ((__int64 (__fastcall *)(_QWORD, HLOCAL, unsigned __int16 *))xmmword_18000B5C0)(0, v26, v27);
    v6 = v17;
    if ( v17 != -1073741772 )
    {
      if ( v17 < 0 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_44;
        v19 = 112;
        v20 = (unsigned int)v17;
        goto LABEL_35;
      }
      *a2 = 1;
    }
    v6 = ((__int64 (__fastcall *)(__int64, HLOCAL, unsigned __int16 *))xmmword_18000B5C0)(1, v26, v3);
    if ( (int)(v6 + 0x80000000) < 0 || v6 == -1073741772 )
    {
      v6 = 0;
      goto LABEL_44;
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_44;
    v19 = 113;
    v20 = v6;
LABEL_35:
    WPP_SF_D(v18[2], v19, &WPP_70b8577d707437755865c965214ce19a_Traceguids, v20);
LABEL_44:
    RtlReleaseResource(&Resource);
    goto LABEL_45;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      110,
      &WPP_70b8577d707437755865c965214ce19a_Traceguids,
      (unsigned int)v5);
LABEL_45:
    v7 = WPP_GLOBAL_Control;
  }
LABEL_46:
  if ( v25 )
  {
    if ( v26 )
    {
      LocalFree(v26);
      v7 = WPP_GLOBAL_Control;
    }
    if ( v23 )
    {
      LocalFree(v23);
      v7 = WPP_GLOBAL_Control;
    }
    if ( v22 )
    {
      LocalFree(v22);
      v7 = WPP_GLOBAL_Control;
    }
  }
  if ( v3 )
  {
    LocalFree(v3);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
    WPP_SF_D(v7[2], 114, &WPP_70b8577d707437755865c965214ce19a_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x1800056d0  push    rbp
0x1800056d2  push    rbx
0x1800056d3  push    rsi
0x1800056d4  push    rdi
0x1800056d5  push    r12
0x1800056d7  push    r13
0x1800056d9  push    r14
0x1800056db  mov     rbp, rsp
0x1800056de  sub     rsp, 60h
0x1800056e2  xor     r14d, r14d
0x1800056e5  mov     rsi, rdx
0x1800056e8  mov     [rbp+arg_8], r14d
0x1800056ec  mov     edi, r14d
0x1800056ef  mov     [rbp+arg_10], r14
0x1800056f3  mov     rbx, rcx
0x1800056f6  mov     [rbp+var_18], r14
0x1800056fa  mov     [rbp+var_20], r14
0x1800056fe  mov     [rbp+arg_18], r14
0x180005702  mov     rcx, cs:WPP_GLOBAL_Control
0x180005709  lea     r12, WPP_GLOBAL_Control
0x180005710  lea     r13, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180005717  cmp     rcx, r12
0x18000571a  jz      short loc_180005732
0x18000571c  test    byte ptr [rcx+1Ch], 8
0x180005720  jz      short loc_180005732
0x180005722  mov     rcx, [rcx+10h]
0x180005726  lea     edx, [r14+6Dh]
0x18000572a  mov     r8, r13
0x18000572d  call    WPP_SF_
0x180005732  lea     rax, [rbp+arg_8]
0x180005736  mov     [rsi], r14d
0x180005739  mov     [rsp+60h+var_30], rax; int *
0x18000573e  lea     r9, [rbp+arg_10]; unsigned __int16 **
0x180005742  lea     rax, [rbp+var_20]
0x180005746  xor     r8d, r8d; struct _UNICODE_STRING *
0x180005749  mov     [rsp+60h+var_38], rax; unsigned __int16 **
0x18000574e  mov     rdx, rbx; struct _UNICODE_STRING *
0x180005751  lea     rax, [rbp+var_18]
0x180005755  xor     ecx, ecx; struct _tagGMsaListEntry *
0x180005757  mov     [rsp+60h+var_40], rax; unsigned __int16 **
0x18000575c  call    ?GmsapParseAccountNamesLocally@@YAJPEAU_tagGMsaListEntry@@PEBU_UNICODE_STRING@@1PEAPEAG22PEAH@Z; GmsapParseAccountNamesLocally(_tagGMsaListEntry *,_UNICODE_STRING const *,_UNICODE_STRING const *,ushort * *,ushort * *,ushort * *,int *)
0x180005761  mov     ebx, eax
0x180005763  test    eax, eax
0x180005765  jns     short loc_18000579A
0x180005767  mov     rcx, cs:WPP_GLOBAL_Control
0x18000576e  cmp     rcx, r12
0x180005771  jz      loc_1800059ED
0x180005777  test    byte ptr [rcx+1Ch], 4
0x18000577b  jz      loc_1800059ED
0x180005781  mov     rcx, [rcx+10h]
0x180005785  mov     edx, 6Eh ; 'n'
0x18000578a  mov     r9d, eax
0x18000578d  mov     r8, r13
0x180005790  call    WPP_SF_D
0x180005795  jmp     loc_1800059E6
0x18000579a  mov     r8, [rbp+var_20]; unsigned __int16 *
0x18000579e  lea     rax, [rbp+arg_18]
0x1800057a2  mov     [rsp+60h+var_38], r14; unsigned __int16 **
0x1800057a7  xor     r9d, r9d; unsigned __int16 **
0x1800057aa  xor     edx, edx; int
0x1800057ac  mov     [rsp+60h+var_40], rax; unsigned __int16 **
0x1800057b1  xor     ecx, ecx; int
0x1800057b3  call    ?GmsapCrackDomainName@@YAJHHPEBGPEAPEAG11@Z; GmsapCrackDomainName(int,int,ushort const *,ushort * *,ushort * *,ushort * *)
0x1800057b8  mov     ebx, eax
0x1800057ba  test    eax, eax
0x1800057bc  jns     short loc_1800057F6
0x1800057be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057c5  cmp     rcx, r12
0x1800057c8  jz      short loc_1800057ED
0x1800057ca  test    byte ptr [rcx+1Ch], 4
0x1800057ce  jz      short loc_1800057ED
0x1800057d0  mov     rcx, [rcx+10h]
0x1800057d4  mov     edx, 6Fh ; 'o'
0x1800057d9  mov     r9d, eax
0x1800057dc  mov     r8, r13
0x1800057df  call    WPP_SF_D
0x1800057e4  mov     rdi, [rbp+arg_18]
0x1800057e8  jmp     loc_1800059E6
0x1800057ed  mov     rdi, [rbp+arg_18]
0x1800057f1  jmp     loc_1800059ED
0x1800057f6  lea     rbx, Resource
0x1800057fd  jmp     short loc_18000581F
0x1800057ff  mov     rcx, rbx; Resource
0x180005802  call    cs:__imp_RtlReleaseResource
0x180005809  nop     dword ptr [rax+rax+00h]
0x18000580e  mov     ecx, 1; dwMilliseconds
0x180005813  call    cs:__imp_Sleep
0x18000581a  nop     dword ptr [rax+rax+00h]
0x18000581f  mov     dl, 1; Wait
0x180005821  mov     rcx, rbx; Resource
0x180005824  call    cs:__imp_RtlAcquireResourceExclusive
0x18000582b  nop     dword ptr [rax+rax+00h]
0x180005830  xor     eax, eax
0x180005832  mov     ecx, r14d
0x180005835  lock cmpxchg cs:dword_18000B670, ecx
0x18000583d  jnz     short loc_1800057FF
0x18000583f  mov     r8, [rbp+var_20]; unsigned __int16 *
0x180005843  lea     r9, [rbp+hMem]; struct _tagGMsaListEntry **
0x180005847  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x18000584b  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x18000584f  mov     [rbp+hMem], r14
0x180005853  call    ?GmsapCheckGMSAInList@@YAXPEBG00PEAPEAU_tagGMsaListEntry@@@Z; GmsapCheckGMSAInList(ushort const *,ushort const *,ushort const *,_tagGMsaListEntry * *)
0x180005858  mov     rbx, [rbp+hMem]
0x18000585c  test    rbx, rbx
0x18000585f  jz      loc_18000592C
0x180005865  mov     dword ptr [rsi], 1
0x18000586b  mov     rcx, [rbx]
0x18000586e  cmp     [rcx+8], rbx
0x180005872  jnz     loc_18000597A
0x180005878  mov     rax, [rbx+8]
0x18000587c  cmp     [rax], rbx
0x18000587f  jnz     loc_18000597A
0x180005885  mov     [rax], rcx
0x180005888  mov     [rcx+8], rax
0x18000588c  mov     rcx, [rbx+10h]; hMem
0x180005890  test    rcx, rcx
0x180005893  jz      short loc_1800058A5
0x180005895  call    cs:__imp_LocalFree
0x18000589c  nop     dword ptr [rax+rax+00h]
0x1800058a1  mov     [rbx+10h], r14
0x1800058a5  mov     rcx, [rbx+18h]; hMem
0x1800058a9  test    rcx, rcx
0x1800058ac  jz      short loc_1800058BE
0x1800058ae  call    cs:__imp_LocalFree
0x1800058b5  nop     dword ptr [rax+rax+00h]
0x1800058ba  mov     [rbx+18h], r14
0x1800058be  mov     rcx, [rbx+20h]; hMem
0x1800058c2  test    rcx, rcx
0x1800058c5  jz      short loc_1800058D7
0x1800058c7  call    cs:__imp_LocalFree
0x1800058ce  nop     dword ptr [rax+rax+00h]
0x1800058d3  mov     [rbx+20h], r14
0x1800058d7  mov     rcx, [rbx+40h]; hMem
0x1800058db  test    rcx, rcx
0x1800058de  jz      short loc_1800058F4
0x1800058e0  call    cs:__imp_LocalFree
0x1800058e7  nop     dword ptr [rax+rax+00h]
0x1800058ec  mov     [rbx+40h], r14
0x1800058f0  mov     [rbx+48h], r14
0x1800058f4  mov     rcx, [rbx+50h]; hMem
0x1800058f8  test    rcx, rcx
0x1800058fb  jz      short loc_180005911
0x1800058fd  call    cs:__imp_LocalFree
0x180005904  nop     dword ptr [rax+rax+00h]
0x180005909  mov     [rbx+50h], r14
0x18000590d  mov     [rbx+58h], r14
0x180005911  mov     rcx, rbx; hMem
0x180005914  call    cs:__imp_LocalFree
0x18000591b  nop     dword ptr [rax+rax+00h]
0x180005920  mov     rax, qword ptr cs:xmmword_18000B5A0+8
0x180005927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000592c  mov     rdi, [rbp+arg_18]
0x180005930  xor     ecx, ecx
0x180005932  mov     rdx, [rbp+arg_10]
0x180005936  mov     r8, rdi
0x180005939  mov     rax, qword ptr cs:xmmword_18000B5C0
0x180005940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005945  mov     ebx, eax
0x180005947  cmp     eax, 0C0000034h
0x18000594c  jz      short loc_180005987
0x18000594e  test    eax, eax
0x180005950  jns     short loc_180005981
0x180005952  mov     rcx, cs:WPP_GLOBAL_Control
0x180005959  cmp     rcx, r12
0x18000595c  jz      short loc_1800059D3
0x18000595e  test    byte ptr [rcx+1Ch], 4
0x180005962  jz      short loc_1800059D3
0x180005964  mov     edx, 70h ; 'p'
0x180005969  mov     r9d, eax
0x18000596c  mov     rcx, [rcx+10h]
0x180005970  mov     r8, r13
0x180005973  call    WPP_SF_D
0x180005978  jmp     short loc_1800059D3
0x18000597a  mov     ecx, 3
0x18000597f  int     29h; Win8: RtlFailFast(ecx)
0x180005981  mov     dword ptr [rsi], 1
0x180005987  mov     rdx, [rbp+arg_10]
0x18000598b  mov     r8, rdi
0x18000598e  mov     rax, qword ptr cs:xmmword_18000B5C0
0x180005995  mov     ecx, 1
0x18000599a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000599f  mov     ecx, 80000000h
0x1800059a4  mov     ebx, eax
0x1800059a6  add     eax, ecx
0x1800059a8  test    ecx, eax
0x1800059aa  jnz     short loc_1800059D0
0x1800059ac  cmp     ebx, 0C0000034h
0x1800059b2  jz      short loc_1800059D0
0x1800059b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059bb  cmp     rcx, r12
0x1800059be  jz      short loc_1800059D3
0x1800059c0  test    byte ptr [rcx+1Ch], 4
0x1800059c4  jz      short loc_1800059D3
0x1800059c6  mov     edx, 71h ; 'q'
0x1800059cb  mov     r9d, ebx
0x1800059ce  jmp     short loc_18000596C
0x1800059d0  mov     ebx, r14d
0x1800059d3  lea     rcx, Resource; Resource
0x1800059da  call    cs:__imp_RtlReleaseResource
0x1800059e1  nop     dword ptr [rax+rax+00h]
0x1800059e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059ed  cmp     [rbp+arg_8], r14d
0x1800059f1  jz      short loc_180005A50
0x1800059f3  mov     rax, [rbp+arg_10]
0x1800059f7  test    rax, rax
0x1800059fa  jz      short loc_180005A12
0x1800059fc  mov     rcx, rax; hMem
0x1800059ff  call    cs:__imp_LocalFree
0x180005a06  nop     dword ptr [rax+rax+00h]
0x180005a0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a12  mov     rax, [rbp+var_18]
0x180005a16  test    rax, rax
0x180005a19  jz      short loc_180005A31
0x180005a1b  mov     rcx, rax; hMem
0x180005a1e  call    cs:__imp_LocalFree
0x180005a25  nop     dword ptr [rax+rax+00h]
0x180005a2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a31  mov     rax, [rbp+var_20]
0x180005a35  test    rax, rax
0x180005a38  jz      short loc_180005A50
0x180005a3a  mov     rcx, rax; hMem
0x180005a3d  call    cs:__imp_LocalFree
0x180005a44  nop     dword ptr [rax+rax+00h]
0x180005a49  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a50  test    rdi, rdi
0x180005a53  jz      short loc_180005A6B
0x180005a55  mov     rcx, rdi; hMem
0x180005a58  call    cs:__imp_LocalFree
0x180005a5f  nop     dword ptr [rax+rax+00h]
0x180005a64  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a6b  cmp     rcx, r12
0x180005a6e  jz      short loc_180005A8A
0x180005a70  test    byte ptr [rcx+1Ch], 8
0x180005a74  jz      short loc_180005A8A
0x180005a76  mov     rcx, [rcx+10h]
0x180005a7a  mov     edx, 72h ; 'r'
0x180005a7f  mov     r9d, ebx
0x180005a82  mov     r8, r13
0x180005a85  call    WPP_SF_D
0x180005a8a  mov     eax, ebx
0x180005a8c  add     rsp, 60h
0x180005a90  pop     r14
0x180005a92  pop     r13
0x180005a94  pop     r12
0x180005a96  pop     rdi
0x180005a97  pop     rsi
0x180005a98  pop     rbx
0x180005a99  pop     rbp
0x180005a9a  retn
```
