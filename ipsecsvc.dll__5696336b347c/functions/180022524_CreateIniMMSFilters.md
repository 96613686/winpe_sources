# CreateIniMMSFilters

- ea: `0x180022524`
- end: `0x180022756`
- name: `CreateIniMMSFilters`
- size: `562`
- prototype: `__int64 __fastcall(__int64, int, int, int, LPVOID *)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18002163c`
- `0x18002350c`
- `0x1800240cc`

## callees

- `0x18000e510`
- `0x180016494`
- `0x180019df8`
- `0x180019e74`
- `0x180022524`
- `0x18002275c`
- `0x1800235fc`
- `0x180024e18`
- `0x180024eb0`
- `0x180026970`

## pseudocode

```c
__int64 __fastcall CreateIniMMSFilters(__int64 a1, int a2, int a3, int a4, LPVOID *a5)
{
  _DWORD *v5; // rbx
  unsigned int v10; // r14d
  unsigned int v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  unsigned int IniMirroredMMFilter; // eax
  _DWORD *v16; // [rsp+30h] [rbp-20h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-18h] BYREF
  __int64 v18; // [rsp+40h] [rbp-10h] BYREF

  v5 = 0;
  lpMem = 0;
  v16 = 0;
  v18 = 0;
  if ( !a3 )
  {
    v10 = 0;
LABEL_28:
    *a5 = 0;
    goto LABEL_33;
  }
  v11 = ApplyMMTransform(a1, a2, a3, a4, (__int64)&lpMem);
  v10 = v11;
  if ( v11 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v13 = 42;
LABEL_21:
        WPP_SF_d(v12[2], v13, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids, v11);
        goto LABEL_22;
      }
      goto LABEL_23;
    }
    goto LABEL_26;
  }
  if ( *(_DWORD *)(a1 + 36) )
  {
    IniMirroredMMFilter = CreateIniMirroredMMFilter(a1, (__int64 *)&v16);
    v10 = IniMirroredMMFilter;
    if ( IniMirroredMMFilter )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids,
          IniMirroredMMFilter);
        v5 = v16;
LABEL_22:
        v12 = WPP_GLOBAL_Control;
        goto LABEL_23;
      }
      v5 = v16;
      goto LABEL_23;
    }
    v5 = v16;
    if ( !(unsigned int)EqualAddresses(a1 + 44, v16 + 11)
      || !(unsigned int)EqualAddresses(a1 + 84, v5 + 21)
      || *(_DWORD *)(a1 + 32) != v5[8]
      || *(_DWORD *)(a1 + 36) != v5[9] )
    {
      v11 = ApplyMMTransform((_DWORD)v5, a2, a3, a4, (__int64)&v18);
      v10 = v11;
      if ( v11 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v13 = 44;
            goto LABEL_21;
          }
LABEL_23:
          if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x10) != 0 )
            WPP_SF_S_guid_D(
              v12[2],
              46,
              (unsigned int)WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids,
              *(_QWORD *)(a1 + 24),
              a1 + 4,
              v10);
        }
LABEL_26:
        if ( lpMem )
          FreeIniMMSFilterList(lpMem);
        goto LABEL_28;
      }
      AddToSpecificMMList((__int64 *)&lpMem, v18);
    }
  }
  *a5 = lpMem;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S_guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      45,
      (unsigned int)WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids,
      *(_QWORD *)(a1 + 24),
      a1 + 4);
LABEL_33:
  if ( v5 )
    FreeIniMMFilter(v5);
  return v10;
}

```

## disassembly

```asm
0x180022524  push    rbp
0x180022526  push    rbx
0x180022527  push    rsi
0x180022528  push    rdi
0x180022529  push    r12
0x18002252b  push    r14
0x18002252d  push    r15
0x18002252f  mov     rbp, rsp
0x180022532  sub     rsp, 50h
0x180022536  xor     ebx, ebx
0x180022538  mov     [rbp+lpMem], 0
0x180022540  mov     [rbp+var_20], rbx
0x180022544  mov     r15, r9
0x180022547  mov     [rbp+var_10], rbx
0x18002254b  mov     edi, r8d
0x18002254e  mov     r12, rdx
0x180022551  mov     rsi, rcx
0x180022554  test    r8d, r8d
0x180022557  jnz     short loc_180022561
0x180022559  xor     r14d, r14d
0x18002255c  jmp     loc_1800226D7
0x180022561  lea     rax, [rbp+lpMem]
0x180022565  mov     [rsp+50h+var_30], rax
0x18002256a  call    ApplyMMTransform
0x18002256f  mov     r14d, eax
0x180022572  test    eax, eax
0x180022574  jz      short loc_1800225A1
0x180022576  mov     rcx, cs:WPP_GLOBAL_Control
0x18002257d  lea     rdi, WPP_GLOBAL_Control
0x180022584  cmp     rcx, rdi
0x180022587  jz      loc_1800226C9
0x18002258d  test    byte ptr [rcx+1Ch], 10h
0x180022591  jz      loc_180022697
0x180022597  mov     edx, 2Ah ; '*'
0x18002259c  jmp     loc_18002267D
0x1800225a1  cmp     [rsi+24h], ebx
0x1800225a4  jz      loc_1800226F1
0x1800225aa  lea     rdx, [rbp+var_20]
0x1800225ae  mov     rcx, rsi
0x1800225b1  call    CreateIniMirroredMMFilter
0x1800225b6  mov     r14d, eax
0x1800225b9  test    eax, eax
0x1800225bb  jz      short loc_180022600
0x1800225bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800225c4  lea     rdi, WPP_GLOBAL_Control
0x1800225cb  cmp     rcx, rdi
0x1800225ce  jz      short loc_1800225F7
0x1800225d0  test    byte ptr [rcx+1Ch], 10h
0x1800225d4  jz      short loc_1800225F7
0x1800225d6  mov     rcx, [rcx+10h]
0x1800225da  lea     r8, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids
0x1800225e1  mov     edx, 2Bh ; '+'
0x1800225e6  mov     r9d, eax
0x1800225e9  call    WPP_SF_d
0x1800225ee  mov     rbx, [rbp+var_20]
0x1800225f2  jmp     loc_180022690
0x1800225f7  mov     rbx, [rbp+var_20]
0x1800225fb  jmp     loc_180022697
0x180022600  mov     rbx, [rbp+var_20]
0x180022604  lea     rcx, [rsi+2Ch]
0x180022608  lea     rdx, [rbx+2Ch]
0x18002260c  call    EqualAddresses
0x180022611  test    eax, eax
0x180022613  jz      short loc_18002263A
0x180022615  lea     rdx, [rbx+54h]
0x180022619  lea     rcx, [rsi+54h]
0x18002261d  call    EqualAddresses
0x180022622  test    eax, eax
0x180022624  jz      short loc_18002263A
0x180022626  mov     eax, [rbx+20h]
0x180022629  cmp     [rsi+20h], eax
0x18002262c  jnz     short loc_18002263A
0x18002262e  mov     eax, [rbx+24h]
0x180022631  cmp     [rsi+24h], eax
0x180022634  jz      loc_1800226F1
0x18002263a  lea     rax, [rbp+var_10]
0x18002263e  mov     r9, r15
0x180022641  mov     r8d, edi
0x180022644  mov     [rsp+50h+var_30], rax
0x180022649  mov     rdx, r12
0x18002264c  mov     rcx, rbx
0x18002264f  call    ApplyMMTransform
0x180022654  mov     r14d, eax
0x180022657  test    eax, eax
0x180022659  jz      loc_1800226E4
0x18002265f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022666  lea     rdi, WPP_GLOBAL_Control
0x18002266d  cmp     rcx, rdi
0x180022670  jz      short loc_1800226C9
0x180022672  test    byte ptr [rcx+1Ch], 10h
0x180022676  jz      short loc_180022697
0x180022678  mov     edx, 2Ch ; ','
0x18002267d  mov     rcx, [rcx+10h]
0x180022681  lea     r8, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids
0x180022688  mov     r9d, eax
0x18002268b  call    WPP_SF_d
0x180022690  mov     rcx, cs:WPP_GLOBAL_Control
0x180022697  cmp     rcx, rdi
0x18002269a  jz      short loc_1800226C9
0x18002269c  test    byte ptr [rcx+1Ch], 10h
0x1800226a0  jz      short loc_1800226C9
0x1800226a2  mov     r9, [rsi+18h]
0x1800226a6  lea     rax, [rsi+4]
0x1800226aa  mov     rcx, [rcx+10h]
0x1800226ae  lea     r8, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids
0x1800226b5  mov     edx, 2Eh ; '.'
0x1800226ba  mov     [rsp+50h+var_28], r14d
0x1800226bf  mov     [rsp+50h+var_30], rax
0x1800226c4  call    WPP_SF_S_guid_D
0x1800226c9  mov     rcx, [rbp+lpMem]; lpMem
0x1800226cd  test    rcx, rcx
0x1800226d0  jz      short loc_1800226D7
0x1800226d2  call    FreeIniMMSFilterList
0x1800226d7  mov     rax, [rbp+arg_20]
0x1800226db  mov     qword ptr [rax], 0
0x1800226e2  jmp     short loc_180022737
0x1800226e4  mov     rdx, [rbp+var_10]
0x1800226e8  lea     rcx, [rbp+lpMem]
0x1800226ec  call    AddToSpecificMMList
0x1800226f1  mov     rcx, [rbp+arg_20]
0x1800226f5  mov     rax, [rbp+lpMem]
0x1800226f9  mov     [rcx], rax
0x1800226fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180022703  lea     rdi, WPP_GLOBAL_Control
0x18002270a  cmp     rcx, rdi
0x18002270d  jz      short loc_180022737
0x18002270f  test    byte ptr [rcx+1Ch], 4
0x180022713  jz      short loc_180022737
0x180022715  mov     r9, [rsi+18h]
0x180022719  lea     rax, [rsi+4]
0x18002271d  mov     rcx, [rcx+10h]
0x180022721  lea     r8, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids
0x180022728  mov     edx, 2Dh ; '-'
0x18002272d  mov     [rsp+50h+var_30], rax
0x180022732  call    WPP_SF_S_guid_
0x180022737  test    rbx, rbx
0x18002273a  jz      short loc_180022744
0x18002273c  mov     rcx, rbx; lpMem
0x18002273f  call    FreeIniMMFilter
0x180022744  mov     eax, r14d
0x180022747  add     rsp, 50h
0x18002274b  pop     r15
0x18002274d  pop     r14
0x18002274f  pop     r12
0x180022751  pop     rdi
0x180022752  pop     rsi
0x180022753  pop     rbx
0x180022754  pop     rbp
0x180022755  retn
```
