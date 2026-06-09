# CreateIniTnSFilters

- ea: `0x1800313e4`
- end: `0x1800315e8`
- name: `CreateIniTnSFilters`
- size: `516`
- prototype: `__int64 __fastcall(__int64, int, int, int, LPVOID *)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800303b8`
- `0x1800323c4`
- `0x180032b84`

## callees

- `0x18000e510`
- `0x180019df8`
- `0x180019e74`
- `0x180030f50`
- `0x1800313e4`
- `0x180032044`
- `0x1800324b4`
- `0x180033784`
- `0x180033820`
- `0x180034980`

## pseudocode

```c
__int64 __fastcall CreateIniTnSFilters(__int64 a1, int a2, int a3, int a4, LPVOID *a5)
{
  void *v5; // rsi
  unsigned int v10; // edi
  unsigned int v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  unsigned int IniMirroredTnFilter; // eax
  void *v16; // [rsp+30h] [rbp-20h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-18h] BYREF
  __int64 v18; // [rsp+40h] [rbp-10h] BYREF

  v5 = 0;
  lpMem = 0;
  v16 = 0;
  v18 = 0;
  if ( !a3 )
  {
    v10 = 0;
LABEL_25:
    *a5 = 0;
    goto LABEL_30;
  }
  v11 = ApplyTnTransform(a1, a2, a3, a4, (__int64)&lpMem);
  v10 = v11;
  if ( v11 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v13 = 30;
LABEL_18:
        WPP_SF_d(v12[2], v13, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids, v11);
        goto LABEL_19;
      }
      goto LABEL_20;
    }
    goto LABEL_23;
  }
  if ( *(_DWORD *)(a1 + 36) )
  {
    IniMirroredTnFilter = CreateIniMirroredTnFilter(a1, (__int64 *)&v16);
    v10 = IniMirroredTnFilter;
    if ( IniMirroredTnFilter )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids,
          IniMirroredTnFilter);
        v5 = v16;
LABEL_19:
        v12 = WPP_GLOBAL_Control;
        goto LABEL_20;
      }
      v5 = v16;
      goto LABEL_20;
    }
    v5 = v16;
    if ( !(unsigned int)EqualIniTnFilterPKeys(a1, v16) )
    {
      v11 = ApplyTnTransform((_DWORD)v5, a2, a3, a4, (__int64)&v18);
      v10 = v11;
      if ( v11 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v13 = 32;
            goto LABEL_18;
          }
LABEL_20:
          if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x10) != 0 )
            WPP_SF_S_guid_D(
              v12[2],
              34,
              (unsigned int)WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids,
              *(_QWORD *)(a1 + 24),
              a1 + 4,
              v10);
        }
LABEL_23:
        if ( lpMem )
          FreeIniTnSFilterList(lpMem);
        goto LABEL_25;
      }
      AddToSpecificTnList((__int64 *)&lpMem, v18);
    }
  }
  *a5 = lpMem;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S_guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      33,
      (unsigned int)WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids,
      *(_QWORD *)(a1 + 24),
      a1 + 4);
LABEL_30:
  if ( v5 )
    FreeIniTnFilter(v5);
  return v10;
}

```

## disassembly

```asm
0x1800313e4  push    rbp
0x1800313e6  push    rbx
0x1800313e7  push    rsi
0x1800313e8  push    rdi
0x1800313e9  push    r12
0x1800313eb  push    r14
0x1800313ed  push    r15
0x1800313ef  mov     rbp, rsp
0x1800313f2  sub     rsp, 50h
0x1800313f6  xor     esi, esi
0x1800313f8  mov     [rbp+lpMem], 0
0x180031400  mov     [rbp+var_20], rsi
0x180031404  mov     r15, r9
0x180031407  mov     [rbp+var_10], rsi
0x18003140b  mov     ebx, r8d
0x18003140e  mov     r12, rdx
0x180031411  mov     r14, rcx
0x180031414  test    r8d, r8d
0x180031417  jnz     short loc_180031420
0x180031419  xor     edi, edi
0x18003141b  jmp     loc_18003156A
0x180031420  lea     rax, [rbp+lpMem]
0x180031424  mov     [rsp+50h+var_30], rax
0x180031429  call    ApplyTnTransform
0x18003142e  mov     edi, eax
0x180031430  test    eax, eax
0x180031432  jz      short loc_18003145F
0x180031434  mov     rcx, cs:WPP_GLOBAL_Control
0x18003143b  lea     rbx, WPP_GLOBAL_Control
0x180031442  cmp     rcx, rbx
0x180031445  jz      loc_18003155C
0x18003144b  test    byte ptr [rcx+1Ch], 10h
0x18003144f  jz      loc_18003152B
0x180031455  mov     edx, 1Eh
0x18003145a  jmp     loc_180031511
0x18003145f  cmp     [r14+24h], esi
0x180031463  jz      loc_180031584
0x180031469  lea     rdx, [rbp+var_20]
0x18003146d  mov     rcx, r14
0x180031470  call    CreateIniMirroredTnFilter
0x180031475  mov     edi, eax
0x180031477  test    eax, eax
0x180031479  jz      short loc_1800314B8
0x18003147b  mov     rcx, cs:WPP_GLOBAL_Control
0x180031482  lea     rbx, WPP_GLOBAL_Control
0x180031489  cmp     rcx, rbx
0x18003148c  jz      short loc_1800314B2
0x18003148e  test    byte ptr [rcx+1Ch], 10h
0x180031492  jz      short loc_1800314B2
0x180031494  mov     rcx, [rcx+10h]
0x180031498  lea     r8, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids
0x18003149f  mov     edx, 1Fh
0x1800314a4  mov     r9d, eax
0x1800314a7  call    WPP_SF_d
0x1800314ac  mov     rsi, [rbp+var_20]
0x1800314b0  jmp     short loc_180031524
0x1800314b2  mov     rsi, [rbp+var_20]
0x1800314b6  jmp     short loc_18003152B
0x1800314b8  mov     rsi, [rbp+var_20]
0x1800314bc  mov     rcx, r14
0x1800314bf  mov     rdx, rsi
0x1800314c2  call    EqualIniTnFilterPKeys
0x1800314c7  test    eax, eax
0x1800314c9  jnz     loc_180031584
0x1800314cf  lea     rax, [rbp+var_10]
0x1800314d3  mov     r9, r15
0x1800314d6  mov     r8d, ebx
0x1800314d9  mov     [rsp+50h+var_30], rax
0x1800314de  mov     rdx, r12
0x1800314e1  mov     rcx, rsi
0x1800314e4  call    ApplyTnTransform
0x1800314e9  mov     edi, eax
0x1800314eb  test    eax, eax
0x1800314ed  jz      loc_180031577
0x1800314f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800314fa  lea     rbx, WPP_GLOBAL_Control
0x180031501  cmp     rcx, rbx
0x180031504  jz      short loc_18003155C
0x180031506  test    byte ptr [rcx+1Ch], 10h
0x18003150a  jz      short loc_18003152B
0x18003150c  mov     edx, 20h ; ' '
0x180031511  mov     rcx, [rcx+10h]
0x180031515  lea     r8, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids
0x18003151c  mov     r9d, eax
0x18003151f  call    WPP_SF_d
0x180031524  mov     rcx, cs:WPP_GLOBAL_Control
0x18003152b  cmp     rcx, rbx
0x18003152e  jz      short loc_18003155C
0x180031530  test    byte ptr [rcx+1Ch], 10h
0x180031534  jz      short loc_18003155C
0x180031536  mov     r9, [r14+18h]
0x18003153a  lea     rax, [r14+4]
0x18003153e  mov     rcx, [rcx+10h]
0x180031542  lea     r8, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids
0x180031549  mov     edx, 22h ; '"'
0x18003154e  mov     [rsp+50h+var_28], edi
0x180031552  mov     [rsp+50h+var_30], rax
0x180031557  call    WPP_SF_S_guid_D
0x18003155c  mov     rcx, [rbp+lpMem]; lpMem
0x180031560  test    rcx, rcx
0x180031563  jz      short loc_18003156A
0x180031565  call    FreeIniTnSFilterList
0x18003156a  mov     rax, [rbp+arg_20]
0x18003156e  mov     qword ptr [rax], 0
0x180031575  jmp     short loc_1800315CA
0x180031577  mov     rdx, [rbp+var_10]
0x18003157b  lea     rcx, [rbp+lpMem]
0x18003157f  call    AddToSpecificTnList
0x180031584  mov     rcx, [rbp+arg_20]
0x180031588  mov     rax, [rbp+lpMem]
0x18003158c  mov     [rcx], rax
0x18003158f  mov     rcx, cs:WPP_GLOBAL_Control
0x180031596  lea     rbx, WPP_GLOBAL_Control
0x18003159d  cmp     rcx, rbx
0x1800315a0  jz      short loc_1800315CA
0x1800315a2  test    byte ptr [rcx+1Ch], 4
0x1800315a6  jz      short loc_1800315CA
0x1800315a8  mov     r9, [r14+18h]
0x1800315ac  lea     rax, [r14+4]
0x1800315b0  mov     rcx, [rcx+10h]
0x1800315b4  lea     r8, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids
0x1800315bb  mov     edx, 21h ; '!'
0x1800315c0  mov     [rsp+50h+var_30], rax
0x1800315c5  call    WPP_SF_S_guid_
0x1800315ca  test    rsi, rsi
0x1800315cd  jz      short loc_1800315D7
0x1800315cf  mov     rcx, rsi; lpMem
0x1800315d2  call    FreeIniTnFilter
0x1800315d7  mov     eax, edi
0x1800315d9  add     rsp, 50h
0x1800315dd  pop     r15
0x1800315df  pop     r14
0x1800315e1  pop     r12
0x1800315e3  pop     rdi
0x1800315e4  pop     rsi
0x1800315e5  pop     rbx
0x1800315e6  pop     rbp
0x1800315e7  retn
```
