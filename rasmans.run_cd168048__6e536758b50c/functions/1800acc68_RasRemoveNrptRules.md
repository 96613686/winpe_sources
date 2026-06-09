# RasRemoveNrptRules

- ea: `0x1800acc68`
- end: `0x1800ace80`
- name: `RasRemoveNrptRules`
- size: `536`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180052edc`
- `0x1800d9a60`
- `0x1800db9cc`
- `0x1800de7e0`
- `0x1800e0a90`

## callees

- `0x180005bfc`
- `0x18004bcd4`
- `0x1800acc68`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800acd75`
- `msvcrt!_wcsnicmp` at `0x1800acd75`
- `DNSAPI!DnsGetNrptRuleNamesList` at `0x1800accf9`
- `DNSAPI!DnsGetNrptRuleNamesList` at `0x1800accf9`
- `DNSAPI!DnsRemoveNrptRule` at `0x1800acd9a`
- `DNSAPI!DnsRemoveNrptRule` at `0x1800acd9a`
- `DNSAPI!DnsFreeNrptRuleNamesList` at `0x1800ace25`
- `DNSAPI!DnsFreeNrptRuleNamesList` at `0x1800ace25`

## pseudocode

```c
__int64 __fastcall RasRemoveNrptRules(_QWORD *a1, unsigned int a2, unsigned int a3)
{
  struct _LIST_ENTRY *v5; // rcx
  unsigned int NrptRuleNamesList; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r9
  unsigned int v10; // edi
  _QWORD *v11; // rsi
  unsigned int v12; // ebp
  const wchar_t *v13; // rcx
  size_t v14; // r8
  __int64 v16; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v17; // [rsp+80h] [rbp+18h] BYREF

  v17 = a3;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_dc(WPP_GLOBAL_Control[1].Flink, 37, &WPP_247047d951ef37ad2b5171979a346086_Traceguids, a2, 1);
    v5 = WPP_GLOBAL_Control;
  }
  v16 = 0;
  v17 = 0;
  if ( a1 && a2 )
  {
    NrptRuleNamesList = DnsGetNrptRuleNamesList(&v16, &v17);
    v7 = NrptRuleNamesList;
    if ( !NrptRuleNamesList )
    {
      v10 = 0;
      if ( v17 )
      {
        while ( 2 )
        {
          v11 = a1;
          v12 = 0;
          while ( 1 )
          {
            if ( v12 >= a2 )
              goto LABEL_21;
            v13 = (const wchar_t *)v11[6];
            v14 = -1;
            do
              ++v14;
            while ( v13[v14] );
            if ( !_wcsnicmp(v13, *(const wchar_t **)(v16 + 8LL * v10), v14) )
              break;
            v11 = (_QWORD *)*v11;
            ++v12;
            if ( !v11 )
              goto LABEL_21;
          }
          v7 = DnsRemoveNrptRule(*(_QWORD *)(v16 + 8LL * v10));
          if ( !v7 )
          {
LABEL_21:
            if ( ++v10 < v17 )
              continue;
            goto LABEL_33;
          }
          break;
        }
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v8 = 40;
          goto LABEL_31;
        }
        goto LABEL_34;
      }
      goto LABEL_33;
    }
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
LABEL_34:
      if ( v16 )
      {
        DnsFreeNrptRuleNamesList(&v16, v17);
        v5 = WPP_GLOBAL_Control;
      }
      goto LABEL_36;
    }
    v8 = 39;
    v9 = NrptRuleNamesList;
LABEL_32:
    WPP_SF_d(v5[1].Flink, v8, &WPP_247047d951ef37ad2b5171979a346086_Traceguids, v9);
LABEL_33:
    v5 = WPP_GLOBAL_Control;
    goto LABEL_34;
  }
  v7 = 87;
  if ( v5 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v7;
  if ( (BYTE4(v5[1].Blink) & 1) != 0 && BYTE1(v5[1].Blink) >= 2u )
  {
    v8 = 38;
LABEL_31:
    v9 = v7;
    goto LABEL_32;
  }
LABEL_36:
  if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v5[1].Blink) & 1) != 0 && BYTE1(v5[1].Blink) >= 6u )
    WPP_SF_d(v5[1].Flink, 41, &WPP_247047d951ef37ad2b5171979a346086_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x1800acc68  mov     [rsp+arg_8], rbx
0x1800acc6d  mov     [rsp+arg_10], r8d
0x1800acc72  push    rbp
0x1800acc73  push    rsi
0x1800acc74  push    rdi
0x1800acc75  push    r12
0x1800acc77  push    r13
0x1800acc79  push    r14
0x1800acc7b  push    r15
0x1800acc7d  sub     rsp, 30h
0x1800acc81  mov     r14d, edx
0x1800acc84  mov     r15, rcx
0x1800acc87  mov     rcx, cs:WPP_GLOBAL_Control
0x1800acc8e  lea     rdi, WPP_GLOBAL_Control
0x1800acc95  cmp     rcx, rdi
0x1800acc98  jz      short loc_1800ACCCA
0x1800acc9a  test    byte ptr [rcx+1Ch], 1
0x1800acc9e  jz      short loc_1800ACCCA
0x1800acca0  cmp     byte ptr [rcx+19h], 6
0x1800acca4  jb      short loc_1800ACCCA
0x1800acca6  mov     rcx, [rcx+10h]
0x1800accaa  lea     r8, WPP_247047d951ef37ad2b5171979a346086_Traceguids
0x1800accb1  mov     edx, 25h ; '%'
0x1800accb6  mov     [rsp+68h+var_48], 1
0x1800accbb  mov     r9d, r14d
0x1800accbe  call    WPP_SF_dc
0x1800accc3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800accca  xor     r13d, r13d
0x1800acccd  mov     [rsp+68h+arg_0], r13
0x1800accd2  mov     [rsp+68h+arg_10], r13d
0x1800accda  test    r15, r15
0x1800accdd  jz      loc_1800ACDDF
0x1800acce3  test    r14d, r14d
0x1800acce6  jz      loc_1800ACDDF
0x1800accec  lea     rdx, [rsp+68h+arg_10]
0x1800accf4  lea     rcx, [rsp+68h+arg_0]
0x1800accf9  call    cs:__imp_DnsGetNrptRuleNamesList
0x1800acd00  nop     dword ptr [rax+rax+00h]
0x1800acd05  mov     ebx, eax
0x1800acd07  test    eax, eax
0x1800acd09  jz      short loc_1800ACD3B
0x1800acd0b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800acd12  cmp     rcx, rdi
0x1800acd15  jz      loc_1800ACE12
0x1800acd1b  test    byte ptr [rcx+1Ch], 1
0x1800acd1f  jz      loc_1800ACE12
0x1800acd25  cmp     byte ptr [rcx+19h], 2
0x1800acd29  jb      loc_1800ACE12
0x1800acd2f  lea     edx, [r13+27h]
0x1800acd33  mov     r9d, eax
0x1800acd36  jmp     loc_1800ACDFB
0x1800acd3b  mov     edi, r13d
0x1800acd3e  cmp     [rsp+68h+arg_10], r13d
0x1800acd46  jbe     loc_1800ACE0B
0x1800acd4c  mov     rsi, r15
0x1800acd4f  mov     ebp, r13d
0x1800acd52  cmp     ebp, r14d
0x1800acd55  jnb     short loc_1800ACDAC
0x1800acd57  mov     rcx, [rsi+30h]; String1
0x1800acd5b  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800acd5f  mov     r12d, edi
0x1800acd62  inc     r8; MaxCount
0x1800acd65  cmp     [rcx+r8*2], r13w
0x1800acd6a  jnz     short loc_1800ACD62
0x1800acd6c  mov     rdx, [rsp+68h+arg_0]
0x1800acd71  mov     rdx, [rdx+r12*8]; String2
0x1800acd75  call    cs:__imp__wcsnicmp
0x1800acd7c  nop     dword ptr [rax+rax+00h]
0x1800acd81  test    eax, eax
0x1800acd83  jz      short loc_1800ACD91
0x1800acd85  mov     rsi, [rsi]
0x1800acd88  inc     ebp
0x1800acd8a  test    rsi, rsi
0x1800acd8d  jnz     short loc_1800ACD52
0x1800acd8f  jmp     short loc_1800ACDAC
0x1800acd91  mov     rcx, [rsp+68h+arg_0]
0x1800acd96  mov     rcx, [rcx+r12*8]
0x1800acd9a  call    cs:__imp_DnsRemoveNrptRule
0x1800acda1  nop     dword ptr [rax+rax+00h]
0x1800acda6  mov     ebx, eax
0x1800acda8  test    eax, eax
0x1800acdaa  jnz     short loc_1800ACDB9
0x1800acdac  inc     edi
0x1800acdae  cmp     edi, [rsp+68h+arg_10]
0x1800acdb5  jb      short loc_1800ACD4C
0x1800acdb7  jmp     short loc_1800ACE0B
0x1800acdb9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800acdc0  lea     rax, WPP_GLOBAL_Control
0x1800acdc7  cmp     rcx, rax
0x1800acdca  jz      short loc_1800ACE12
0x1800acdcc  test    byte ptr [rcx+1Ch], 1
0x1800acdd0  jz      short loc_1800ACE12
0x1800acdd2  cmp     byte ptr [rcx+19h], 2
0x1800acdd6  jb      short loc_1800ACE12
0x1800acdd8  mov     edx, 28h ; '('
0x1800acddd  jmp     short loc_1800ACDF8
0x1800acddf  mov     ebx, 57h ; 'W'
0x1800acde4  cmp     rcx, rdi
0x1800acde7  jz      short loc_1800ACE68
0x1800acde9  test    byte ptr [rcx+1Ch], 1
0x1800acded  jz      short loc_1800ACE3F
0x1800acdef  cmp     byte ptr [rcx+19h], 2
0x1800acdf3  jb      short loc_1800ACE3F
0x1800acdf5  lea     edx, [rbx-31h]
0x1800acdf8  mov     r9d, ebx
0x1800acdfb  mov     rcx, [rcx+10h]
0x1800acdff  lea     r8, WPP_247047d951ef37ad2b5171979a346086_Traceguids
0x1800ace06  call    WPP_SF_d
0x1800ace0b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ace12  cmp     [rsp+68h+arg_0], r13
0x1800ace17  jz      short loc_1800ACE38
0x1800ace19  mov     edx, [rsp+68h+arg_10]
0x1800ace20  lea     rcx, [rsp+68h+arg_0]
0x1800ace25  call    cs:__imp_DnsFreeNrptRuleNamesList
0x1800ace2c  nop     dword ptr [rax+rax+00h]
0x1800ace31  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ace38  lea     rdi, WPP_GLOBAL_Control
0x1800ace3f  cmp     rcx, rdi
0x1800ace42  jz      short loc_1800ACE68
0x1800ace44  test    byte ptr [rcx+1Ch], 1
0x1800ace48  jz      short loc_1800ACE68
0x1800ace4a  cmp     byte ptr [rcx+19h], 6
0x1800ace4e  jb      short loc_1800ACE68
0x1800ace50  mov     rcx, [rcx+10h]
0x1800ace54  lea     r8, WPP_247047d951ef37ad2b5171979a346086_Traceguids
0x1800ace5b  mov     edx, 29h ; ')'
0x1800ace60  mov     r9d, ebx
0x1800ace63  call    WPP_SF_d
0x1800ace68  mov     eax, ebx
0x1800ace6a  mov     rbx, [rsp+68h+arg_8]
0x1800ace6f  add     rsp, 30h
0x1800ace73  pop     r15
0x1800ace75  pop     r14
0x1800ace77  pop     r13
0x1800ace79  pop     r12
0x1800ace7b  pop     rdi
0x1800ace7c  pop     rsi
0x1800ace7d  pop     rbp
0x1800ace7e  retn
```
