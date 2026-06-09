# UpdateIniMMFilterThruIfChange

- ea: `0x180024750`
- end: `0x180024a37`
- name: `UpdateIniMMFilterThruIfChange`
- size: `743`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, installer_update`

## callers

- `0x180001710`
- `0x180007100`

## callees

- `0x180006f60`
- `0x18000e510`
- `0x180019df8`
- `0x180019e74`
- `0x180021c38`
- `0x18002350c`
- `0x180023df0`
- `0x180024064`
- `0x180024750`
- `0x180024a40`
- `0x180024e18`
- `0x180026970`
- `0x18002711c`
- `0x180027138`
- `0x180044928`

## pseudocode

```c
__int64 __fastcall UpdateIniMMFilterThruIfChange(_QWORD *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r12
  void *v4; // r14
  void *v5; // r15
  unsigned int v7; // eax
  unsigned int v8; // edi
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rcx
  unsigned int v14; // r10d
  __int64 v15; // rcx
  _QWORD *v16; // r8
  __int64 i; // rdx
  _QWORD *j; // r9
  LPVOID v19; // [rsp+30h] [rbp-30h] BYREF
  __int64 v20; // [rsp+38h] [rbp-28h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-20h] BYREF
  void *v22; // [rsp+48h] [rbp-18h] BYREF
  LPVOID v23; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v24; // [rsp+A8h] [rbp+48h] BYREF

  v3 = 0;
  v19 = 0;
  v4 = 0;
  v20 = 0;
  v5 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  lpMem = 0;
  v7 = FormIniMMSFilters(a1, a2, a3, &v19);
  v8 = v7;
  if ( v7 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v10 = 93;
LABEL_17:
        WPP_SF_d(v9[2], v10, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids, v7);
        v9 = WPP_GLOBAL_Control;
        goto LABEL_18;
      }
      goto LABEL_18;
    }
    goto LABEL_21;
  }
  v7 = AllocateMMSFilterLinks((__int64)v19, &v24, &lpMem);
  v8 = v7;
  if ( v7 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v10 = 94;
        goto LABEL_17;
      }
LABEL_18:
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 )
        WPP_SF_S_guid_D(
          v9[2],
          97,
          (unsigned int)WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids,
          a1[3],
          (__int64)a1 + 4,
          v8);
    }
LABEL_21:
    if ( v19 )
      FreeIniMMSFilterList(v19);
    if ( lpMem )
      IpsecFreeMem(lpMem);
    if ( v3 )
      AddToSpecificMMList((__int64 *)&gpIniMMSFilter, v3);
    if ( v4 )
      FreeIniMMSFilterList(v4);
    if ( v5 )
      AddToSpecificMMList((__int64 *)&gpIniMMSFilter, (__int64)v5);
    return v8;
  }
  RemoveMMSFilters(a1, &v20);
  ProcessIniMMSFilters((unsigned int)&v19, (unsigned int)&v20, (unsigned int)&v22, (unsigned int)&v23, (__int64)&v24);
  v11 = a1[21];
  v3 = v20;
  v4 = v22;
  if ( v11 )
  {
    LinkMMSpecificFiltersToAuth(v11, v20);
    LinkMMSpecificFiltersToAuth(a1[21], (__int64)v4);
  }
  v12 = a1[22];
  if ( v12 )
  {
    LinkMMSpecificFiltersToPolicy(v12, v3);
    LinkMMSpecificFiltersToPolicy(a1[22], (__int64)v4);
  }
  v5 = v23;
  v7 = LipsApiIkeFilterUpdate((__int64)v23, (__int64)v4);
  v8 = v7;
  if ( v7 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v10 = 95;
        goto LABEL_17;
      }
      goto LABEL_18;
    }
    goto LABEL_21;
  }
  v14 = v24;
  v15 = 0;
  v16 = lpMem;
  for ( i = v3; (unsigned int)v15 < v14; i = *(_QWORD *)(i + 192) )
  {
    if ( !i )
      break;
    v16[v15] = i;
    v15 = (unsigned int)(v15 + 1);
  }
  for ( j = v4; (unsigned int)v15 < v14 && j; j = (_QWORD *)j[24] )
  {
    v16[v15] = j;
    v15 = (unsigned int)(v15 + 1);
  }
  UpdateMMSFilterLinks(a1, v14, v16);
  AddToSpecificMMList((__int64 *)&gpIniMMSFilter, v3);
  AddToSpecificMMList((__int64 *)&gpIniMMSFilter, (__int64)v4);
  if ( v5 )
    FreeIniMMSFilterList(v5);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S_guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      96,
      (unsigned int)WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids,
      a1[3],
      (__int64)a1 + 4);
  return 0;
}

```

## disassembly

```asm
0x180024750  mov     [rsp-28h+arg_0], rbx
0x180024755  mov     [rsp-28h+arg_8], rsi
0x18002475a  push    rbp
0x18002475b  push    rdi
0x18002475c  push    r12
0x18002475e  push    r14
0x180024760  push    r15
0x180024762  mov     rbp, rsp
0x180024765  sub     rsp, 60h
0x180024769  xor     r12d, r12d
0x18002476c  mov     [rbp+var_30], 0
0x180024774  xor     r14d, r14d
0x180024777  mov     [rbp+var_28], r12
0x18002477b  xor     r15d, r15d
0x18002477e  mov     [rbp+var_18], r14
0x180024782  lea     r9, [rbp+var_30]
0x180024786  mov     [rbp+var_10], r15
0x18002478a  mov     rsi, rcx
0x18002478d  mov     [rbp+arg_18], 0
0x180024794  mov     [rbp+lpMem], 0
0x18002479c  call    FormIniMMSFilters
0x1800247a1  mov     edi, eax
0x1800247a3  test    eax, eax
0x1800247a5  jz      short loc_1800247D2
0x1800247a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800247ae  lea     rbx, WPP_GLOBAL_Control
0x1800247b5  cmp     rcx, rbx
0x1800247b8  jz      loc_18002490E
0x1800247be  test    byte ptr [rcx+1Ch], 10h
0x1800247c2  jz      loc_1800248DD
0x1800247c8  lea     edx, [r12+5Dh]
0x1800247cd  jmp     loc_1800248C3
0x1800247d2  mov     rcx, [rbp+var_30]
0x1800247d6  lea     r8, [rbp+lpMem]
0x1800247da  lea     rdx, [rbp+arg_18]
0x1800247de  call    AllocateMMSFilterLinks
0x1800247e3  mov     edi, eax
0x1800247e5  test    eax, eax
0x1800247e7  jz      short loc_180024814
0x1800247e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800247f0  lea     rbx, WPP_GLOBAL_Control
0x1800247f7  cmp     rcx, rbx
0x1800247fa  jz      loc_18002490E
0x180024800  test    byte ptr [rcx+1Ch], 10h
0x180024804  jz      loc_1800248DD
0x18002480a  mov     edx, 5Eh ; '^'
0x18002480f  jmp     loc_1800248C3
0x180024814  lea     rdx, [rbp+var_28]
0x180024818  mov     rcx, rsi
0x18002481b  call    RemoveMMSFilters
0x180024820  lea     rax, [rbp+arg_18]
0x180024824  lea     r9, [rbp+var_10]
0x180024828  mov     [rsp+60h+var_40], rax
0x18002482d  lea     r8, [rbp+var_18]
0x180024831  lea     rdx, [rbp+var_28]
0x180024835  lea     rcx, [rbp+var_30]
0x180024839  call    ProcessIniMMSFilters
0x18002483e  mov     rcx, [rsi+0A8h]
0x180024845  mov     r12, [rbp+var_28]
0x180024849  mov     r14, [rbp+var_18]
0x18002484d  test    rcx, rcx
0x180024850  jz      short loc_180024869
0x180024852  mov     rdx, r12
0x180024855  call    LinkMMSpecificFiltersToAuth
0x18002485a  mov     rcx, [rsi+0A8h]
0x180024861  mov     rdx, r14
0x180024864  call    LinkMMSpecificFiltersToAuth
0x180024869  mov     rcx, [rsi+0B0h]
0x180024870  test    rcx, rcx
0x180024873  jz      short loc_18002488C
0x180024875  mov     rdx, r12
0x180024878  call    LinkMMSpecificFiltersToPolicy
0x18002487d  mov     rcx, [rsi+0B0h]
0x180024884  mov     rdx, r14
0x180024887  call    LinkMMSpecificFiltersToPolicy
0x18002488c  mov     r15, [rbp+var_10]
0x180024890  mov     rdx, r14
0x180024893  mov     rcx, r15
0x180024896  call    LipsApiIkeFilterUpdate
0x18002489b  mov     edi, eax
0x18002489d  test    eax, eax
0x18002489f  jz      loc_180024966
0x1800248a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800248ac  lea     rbx, WPP_GLOBAL_Control
0x1800248b3  cmp     rcx, rbx
0x1800248b6  jz      short loc_18002490E
0x1800248b8  test    byte ptr [rcx+1Ch], 10h
0x1800248bc  jz      short loc_1800248DD
0x1800248be  mov     edx, 5Fh ; '_'
0x1800248c3  mov     rcx, [rcx+10h]
0x1800248c7  lea     r8, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids
0x1800248ce  mov     r9d, eax
0x1800248d1  call    WPP_SF_d
0x1800248d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800248dd  cmp     rcx, rbx
0x1800248e0  jz      short loc_18002490E
0x1800248e2  test    byte ptr [rcx+1Ch], 4
0x1800248e6  jz      short loc_18002490E
0x1800248e8  mov     r9, [rsi+18h]
0x1800248ec  lea     rax, [rsi+4]
0x1800248f0  mov     rcx, [rcx+10h]
0x1800248f4  lea     r8, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids
0x1800248fb  mov     edx, 61h ; 'a'
0x180024900  mov     [rsp+60h+var_38], edi
0x180024904  mov     [rsp+60h+var_40], rax
0x180024909  call    WPP_SF_S_guid_D
0x18002490e  mov     rcx, [rbp+var_30]; lpMem
0x180024912  test    rcx, rcx
0x180024915  jz      short loc_18002491C
0x180024917  call    FreeIniMMSFilterList
0x18002491c  mov     rcx, [rbp+lpMem]; lpMem
0x180024920  test    rcx, rcx
0x180024923  jz      short loc_18002492A
0x180024925  call    IpsecFreeMem
0x18002492a  test    r12, r12
0x18002492d  jz      short loc_18002493E
0x18002492f  mov     rdx, r12
0x180024932  lea     rcx, gpIniMMSFilter
0x180024939  call    AddToSpecificMMList
0x18002493e  test    r14, r14
0x180024941  jz      short loc_18002494B
0x180024943  mov     rcx, r14; lpMem
0x180024946  call    FreeIniMMSFilterList
0x18002494b  test    r15, r15
0x18002494e  jz      short loc_18002495F
0x180024950  mov     rdx, r15
0x180024953  lea     rcx, gpIniMMSFilter
0x18002495a  call    AddToSpecificMMList
0x18002495f  mov     eax, edi
0x180024961  jmp     loc_180024A1E
0x180024966  mov     r10d, [rbp+arg_18]
0x18002496a  xor     ecx, ecx
0x18002496c  mov     r8, [rbp+lpMem]
0x180024970  mov     rdx, r12
0x180024973  test    r10d, r10d
0x180024976  jz      short loc_18002498F
0x180024978  test    rdx, rdx
0x18002497b  jz      short loc_18002498F
0x18002497d  mov     [r8+rcx*8], rdx
0x180024981  inc     ecx
0x180024983  mov     rdx, [rdx+0C0h]
0x18002498a  cmp     ecx, r10d
0x18002498d  jb      short loc_180024978
0x18002498f  mov     r9, r14
0x180024992  jmp     short loc_1800249A6
0x180024994  test    r9, r9
0x180024997  jz      short loc_1800249AB
0x180024999  mov     [r8+rcx*8], r9
0x18002499d  inc     ecx
0x18002499f  mov     r9, [r9+0C0h]
0x1800249a6  cmp     ecx, r10d
0x1800249a9  jb      short loc_180024994
0x1800249ab  mov     edx, r10d
0x1800249ae  mov     rcx, rsi
0x1800249b1  call    UpdateMMSFilterLinks
0x1800249b6  mov     rdx, r12
0x1800249b9  lea     rcx, gpIniMMSFilter
0x1800249c0  call    AddToSpecificMMList
0x1800249c5  mov     rdx, r14
0x1800249c8  lea     rcx, gpIniMMSFilter
0x1800249cf  call    AddToSpecificMMList
0x1800249d4  test    r15, r15
0x1800249d7  jz      short loc_1800249E1
0x1800249d9  mov     rcx, r15; lpMem
0x1800249dc  call    FreeIniMMSFilterList
0x1800249e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800249e8  lea     rbx, WPP_GLOBAL_Control
0x1800249ef  cmp     rcx, rbx
0x1800249f2  jz      short loc_180024A1C
0x1800249f4  test    byte ptr [rcx+1Ch], 4
0x1800249f8  jz      short loc_180024A1C
0x1800249fa  mov     r9, [rsi+18h]
0x1800249fe  lea     rax, [rsi+4]
0x180024a02  mov     rcx, [rcx+10h]
0x180024a06  lea     r8, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids
0x180024a0d  mov     edx, 60h ; '`'
0x180024a12  mov     [rsp+60h+var_40], rax
0x180024a17  call    WPP_SF_S_guid_
0x180024a1c  xor     eax, eax
0x180024a1e  lea     r11, [rsp+60h+var_s0]
0x180024a23  mov     rbx, [r11+30h]
0x180024a27  mov     rsi, [r11+38h]
0x180024a2b  mov     rsp, r11
0x180024a2e  pop     r15
0x180024a30  pop     r14
0x180024a32  pop     r12
0x180024a34  pop     rdi
0x180024a35  pop     rbp
0x180024a36  retn
```
