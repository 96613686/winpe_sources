# UpdateIniTnFilterThruIfChange

- ea: `0x18003344c`
- end: `0x1800336a2`
- name: `UpdateIniTnFilterThruIfChange`
- size: `598`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x180030b54`

## callees

- `0x180006f60`
- `0x18000e510`
- `0x180019df8`
- `0x180019e74`
- `0x180030a60`
- `0x1800323c4`
- `0x1800329a4`
- `0x180032b1c`
- `0x18003344c`
- `0x1800336a8`
- `0x180033784`
- `0x180034980`
- `0x1800349b0`

## pseudocode

```c
__int64 __fastcall UpdateIniTnFilterThruIfChange(_QWORD *a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // eax
  unsigned int v5; // esi
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v9; // rcx
  __int64 v10; // rbx
  __int64 v11; // rsi
  unsigned int v12; // r10d
  __int64 v13; // rcx
  _QWORD *v14; // r8
  __int64 i; // rdx
  __int64 j; // r9
  int v17; // [rsp+28h] [rbp-40h]
  LPVOID v18; // [rsp+30h] [rbp-38h] BYREF
  __int64 v19; // [rsp+38h] [rbp-30h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-28h] BYREF
  __int64 v21; // [rsp+48h] [rbp-20h] BYREF
  LPVOID v22[3]; // [rsp+50h] [rbp-18h] BYREF
  unsigned int v23; // [rsp+A8h] [rbp+40h] BYREF

  v18 = 0;
  v23 = 0;
  lpMem = 0;
  v19 = 0;
  v21 = 0;
  v22[0] = 0;
  v4 = FormIniTnSFilters(a1, a2, a3, &v18);
  v5 = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v7 = 55;
LABEL_9:
        WPP_SF_d(v6[2], v7, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids, v4);
        v6 = WPP_GLOBAL_Control;
        goto LABEL_10;
      }
      goto LABEL_10;
    }
    goto LABEL_13;
  }
  v4 = AllocateTnSFilterLinks((__int64)v18, &v23, &lpMem);
  v5 = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v7 = 56;
        goto LABEL_9;
      }
LABEL_10:
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x10) != 0 )
      {
        v17 = v5;
        WPP_SF_S_guid_D(
          v6[2],
          58,
          (unsigned int)WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids,
          a1[3],
          (__int64)a1 + 4,
          v17);
      }
    }
LABEL_13:
    if ( v18 )
      FreeIniTnSFilterList(v18);
    if ( lpMem )
      IpsecFreeMem(lpMem);
    return v5;
  }
  RemoveTnSFilters(a1, &v19);
  ProcessIniTnSFilters(&v18, &v19, &v21, v22);
  v9 = a1[33];
  v10 = v19;
  v11 = v21;
  if ( v9 )
  {
    LinkTnSpecificFilters(v9, a1[37], a1[38], a1[44], v19);
    LinkTnSpecificFilters(a1[33], a1[37], a1[38], a1[44], v11);
  }
  v12 = v23;
  v13 = 0;
  v14 = lpMem;
  for ( i = v10; (unsigned int)v13 < v12; i = *(_QWORD *)(i + 336) )
  {
    if ( !i )
      break;
    v14[v13] = i;
    v13 = (unsigned int)(v13 + 1);
  }
  for ( j = v11; (unsigned int)v13 < v12 && j; j = *(_QWORD *)(j + 336) )
  {
    v14[v13] = j;
    v13 = (unsigned int)(v13 + 1);
  }
  UpdateTnSFilterLinks(a1, v12, v14);
  AddToSpecificTnList((__int64 *)&gpIniTnSFilter, v10);
  AddToSpecificTnList((__int64 *)&gpIniTnSFilter, v11);
  if ( v22[0] )
    FreeIniTnSFilterList(v22[0]);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S_guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      57,
      (unsigned int)WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids,
      a1[3],
      (__int64)a1 + 4);
  return 0;
}

```

## disassembly

```asm
0x18003344c  push    rbp
0x18003344e  push    rbx
0x18003344f  push    rsi
0x180033450  push    rdi
0x180033451  mov     rbp, rsp
0x180033454  sub     rsp, 68h
0x180033458  lea     r9, [rbp+var_38]
0x18003345c  mov     [rbp+var_38], 0
0x180033464  mov     rdi, rcx
0x180033467  mov     [rbp+arg_18], 0
0x18003346e  mov     [rbp+lpMem], 0
0x180033476  mov     [rbp+var_30], 0
0x18003347e  mov     [rbp+var_20], 0
0x180033486  mov     [rbp+var_18], 0
0x18003348e  call    FormIniTnSFilters
0x180033493  mov     esi, eax
0x180033495  test    eax, eax
0x180033497  jz      short loc_1800334BD
0x180033499  mov     rcx, cs:WPP_GLOBAL_Control
0x1800334a0  lea     rbx, WPP_GLOBAL_Control
0x1800334a7  cmp     rcx, rbx
0x1800334aa  jz      loc_180033541
0x1800334b0  test    byte ptr [rcx+1Ch], 10h
0x1800334b4  jz      short loc_180033510
0x1800334b6  mov     edx, 37h ; '7'
0x1800334bb  jmp     short loc_1800334F6
0x1800334bd  mov     rcx, [rbp+var_38]
0x1800334c1  lea     r8, [rbp+lpMem]
0x1800334c5  lea     rdx, [rbp+arg_18]
0x1800334c9  call    AllocateTnSFilterLinks
0x1800334ce  mov     esi, eax
0x1800334d0  test    eax, eax
0x1800334d2  jz      loc_180033566
0x1800334d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800334df  lea     rbx, WPP_GLOBAL_Control
0x1800334e6  cmp     rcx, rbx
0x1800334e9  jz      short loc_180033541
0x1800334eb  test    byte ptr [rcx+1Ch], 10h
0x1800334ef  jz      short loc_180033510
0x1800334f1  mov     edx, 38h ; '8'
0x1800334f6  mov     rcx, [rcx+10h]
0x1800334fa  lea     r8, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids
0x180033501  mov     r9d, eax
0x180033504  call    WPP_SF_d
0x180033509  mov     rcx, cs:WPP_GLOBAL_Control
0x180033510  cmp     rcx, rbx
0x180033513  jz      short loc_180033541
0x180033515  test    byte ptr [rcx+1Ch], 10h
0x180033519  jz      short loc_180033541
0x18003351b  mov     r9, [rdi+18h]
0x18003351f  lea     rax, [rdi+4]
0x180033523  mov     rcx, [rcx+10h]
0x180033527  lea     r8, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids
0x18003352e  mov     edx, 3Ah ; ':'
0x180033533  mov     [rsp+68h+var_40], esi
0x180033537  mov     [rsp+68h+var_48], rax
0x18003353c  call    WPP_SF_S_guid_D
0x180033541  cmp     [rbp+var_38], 0
0x180033546  jz      short loc_180033551
0x180033548  mov     rcx, [rbp+var_38]; lpMem
0x18003354c  call    FreeIniTnSFilterList
0x180033551  mov     rcx, [rbp+lpMem]; lpMem
0x180033555  test    rcx, rcx
0x180033558  jz      short loc_18003355F
0x18003355a  call    IpsecFreeMem
0x18003355f  mov     eax, esi
0x180033561  jmp     loc_180033699
0x180033566  lea     rdx, [rbp+var_30]
0x18003356a  mov     rcx, rdi
0x18003356d  call    RemoveTnSFilters
0x180033572  lea     r9, [rbp+var_18]
0x180033576  lea     r8, [rbp+var_20]
0x18003357a  lea     rdx, [rbp+var_30]
0x18003357e  lea     rcx, [rbp+var_38]
0x180033582  call    ProcessIniTnSFilters
0x180033587  mov     rcx, [rdi+108h]
0x18003358e  mov     rbx, [rbp+var_30]
0x180033592  mov     rsi, [rbp+var_20]
0x180033596  test    rcx, rcx
0x180033599  jz      short loc_1800335E0
0x18003359b  mov     r9, [rdi+160h]
0x1800335a2  mov     r8, [rdi+130h]
0x1800335a9  mov     rdx, [rdi+128h]
0x1800335b0  mov     [rsp+68h+var_48], rbx
0x1800335b5  call    LinkTnSpecificFilters
0x1800335ba  mov     r9, [rdi+160h]
0x1800335c1  mov     r8, [rdi+130h]
0x1800335c8  mov     rdx, [rdi+128h]
0x1800335cf  mov     rcx, [rdi+108h]
0x1800335d6  mov     [rsp+68h+var_48], rsi
0x1800335db  call    LinkTnSpecificFilters
0x1800335e0  mov     r10d, [rbp+arg_18]
0x1800335e4  xor     ecx, ecx
0x1800335e6  mov     r8, [rbp+lpMem]
0x1800335ea  mov     rdx, rbx
0x1800335ed  test    r10d, r10d
0x1800335f0  jz      short loc_180033609
0x1800335f2  test    rdx, rdx
0x1800335f5  jz      short loc_180033609
0x1800335f7  mov     [r8+rcx*8], rdx
0x1800335fb  inc     ecx
0x1800335fd  mov     rdx, [rdx+150h]
0x180033604  cmp     ecx, r10d
0x180033607  jb      short loc_1800335F2
0x180033609  mov     r9, rsi
0x18003360c  jmp     short loc_180033620
0x18003360e  test    r9, r9
0x180033611  jz      short loc_180033625
0x180033613  mov     [r8+rcx*8], r9
0x180033617  inc     ecx
0x180033619  mov     r9, [r9+150h]
0x180033620  cmp     ecx, r10d
0x180033623  jb      short loc_18003360E
0x180033625  mov     edx, r10d
0x180033628  mov     rcx, rdi
0x18003362b  call    UpdateTnSFilterLinks
0x180033630  mov     rdx, rbx
0x180033633  lea     rcx, gpIniTnSFilter
0x18003363a  call    AddToSpecificTnList
0x18003363f  mov     rdx, rsi
0x180033642  lea     rcx, gpIniTnSFilter
0x180033649  call    AddToSpecificTnList
0x18003364e  mov     rcx, [rbp+var_18]; lpMem
0x180033652  test    rcx, rcx
0x180033655  jz      short loc_18003365C
0x180033657  call    FreeIniTnSFilterList
0x18003365c  mov     rcx, cs:WPP_GLOBAL_Control
0x180033663  lea     rbx, WPP_GLOBAL_Control
0x18003366a  cmp     rcx, rbx
0x18003366d  jz      short loc_180033697
0x18003366f  test    byte ptr [rcx+1Ch], 4
0x180033673  jz      short loc_180033697
0x180033675  mov     r9, [rdi+18h]
0x180033679  lea     rax, [rdi+4]
0x18003367d  mov     rcx, [rcx+10h]
0x180033681  lea     r8, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids
0x180033688  mov     edx, 39h ; '9'
0x18003368d  mov     [rsp+68h+var_48], rax
0x180033692  call    WPP_SF_S_guid_
0x180033697  xor     eax, eax
0x180033699  add     rsp, 68h
0x18003369d  pop     rdi
0x18003369e  pop     rsi
0x18003369f  pop     rbx
0x1800336a0  pop     rbp
0x1800336a1  retn
```
