# MSMNotifyDiagnosticsHint

- ea: `0x18002830c`
- end: `0x1800284b3`
- name: `MSMNotifyDiagnosticsHint`
- size: `423`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x180005b00`
- `0x180009540`
- `0x180024860`
- `0x180024c40`
- `0x180025280`
- `0x180026194`

## callees

- `0x180005440`
- `0x180007f60`
- `0x18000c4c0`
- `0x1800127a0`
- `0x1800214f0`
- `0x18002830c`

## pseudocode

```c
__int64 __fastcall MSMNotifyDiagnosticsHint(__int64 a1, unsigned int a2, unsigned int a3)
{
  int v3; // ebp
  _QWORD *v7; // r10
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  const wchar_t *v11; // rcx
  unsigned int v12; // edi
  const wchar_t *v13; // rax
  unsigned int v14; // ebx
  _UNKNOWN **v15; // rcx
  unsigned __int64 v17; // [rsp+50h] [rbp+8h] BYREF

  v3 = *(_DWORD *)(a1 + 20);
  v17 = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x57u, (__int64)WPP_980772dc0b713ed2d597554bce319f4c_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  v17 = __PAIR64__(a3, a2);
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 68) & 0x10) != 0 )
  {
    if ( a3 )
    {
      v8 = a3 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( v10 )
          {
            if ( v10 == 1 )
              v11 = L"Invalid hint";
            else
              v11 = L"Unknown hint";
          }
          else
          {
            v11 = L"Hint AP timeouts";
          }
        }
        else
        {
          v11 = L"Hint backend not responsive";
        }
      }
      else
      {
        v11 = L"Hint user cancelled";
      }
    }
    else
    {
      v11 = L"Hint user not responsive";
    }
    if ( a2 )
    {
      v12 = a2 - 1;
      if ( v12 )
      {
        if ( v12 == 1 )
          v13 = L"Invalid state";
        else
          v13 = L"Unknown state";
      }
      else
      {
        v13 = L"Hint Cancelled";
      }
    }
    else
    {
      v13 = L"Hint Begin";
    }
    WPP_SF_dSS(v7[7], 88, (unsigned int)WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v3, (__int64)v13, (__int64)v11);
  }
  v14 = MSMSendOneXEventNotification(a1, 0x10004u, 8, (__int64)&v17);
  if ( !v14 )
    goto LABEL_29;
  v15 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v14;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x59u, (__int64)WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v3);
LABEL_29:
    v15 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( v15 != &WPP_GLOBAL_Control && (*((_DWORD *)v15 + 17) & 0x800) != 0 )
    WPP_SF_D((__int64)v15[7], 0x5Au, (__int64)WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x18002830c  mov     [rsp+arg_8], rbx
0x180028311  mov     [rsp+arg_10], rbp
0x180028316  push    rsi
0x180028317  push    rdi
0x180028318  push    r14
0x18002831a  sub     rsp, 30h
0x18002831e  mov     ebp, [rcx+14h]
0x180028321  mov     ebx, r8d
0x180028324  mov     edi, edx
0x180028326  mov     [rsp+48h+arg_0], 0
0x18002832f  mov     rsi, rcx
0x180028332  mov     r10, cs:WPP_GLOBAL_Control
0x180028339  lea     r14, WPP_GLOBAL_Control
0x180028340  cmp     r10, r14
0x180028343  jz      short loc_18002836B
0x180028345  test    dword ptr [r10+44h], 800h
0x18002834d  jz      short loc_18002836B
0x18002834f  mov     rcx, [r10+38h]
0x180028353  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18002835a  mov     edx, 57h ; 'W'
0x18002835f  call    WPP_SF_
0x180028364  mov     r10, cs:WPP_GLOBAL_Control
0x18002836b  mov     dword ptr [rsp+48h+arg_0], edi
0x18002836f  mov     dword ptr [rsp+48h+arg_0+4], ebx
0x180028373  cmp     r10, r14
0x180028376  jz      loc_180028425
0x18002837c  test    byte ptr [r10+44h], 10h
0x180028381  jz      loc_180028425
0x180028387  test    ebx, ebx
0x180028389  jz      short loc_1800283CC
0x18002838b  sub     ebx, 1
0x18002838e  jz      short loc_1800283C3
0x180028390  sub     ebx, 1
0x180028393  jz      short loc_1800283BA
0x180028395  sub     ebx, 1
0x180028398  jz      short loc_1800283B1
0x18002839a  cmp     ebx, 1
0x18002839d  jz      short loc_1800283A8
0x18002839f  lea     rcx, aUnknownHint; "Unknown hint"
0x1800283a6  jmp     short loc_1800283D3
0x1800283a8  lea     rcx, aInvalidHint; "Invalid hint"
0x1800283af  jmp     short loc_1800283D3
0x1800283b1  lea     rcx, aHintApTimeouts; "Hint AP timeouts"
0x1800283b8  jmp     short loc_1800283D3
0x1800283ba  lea     rcx, aHintBackendNot; "Hint backend not responsive"
0x1800283c1  jmp     short loc_1800283D3
0x1800283c3  lea     rcx, aHintUserCancel; "Hint user cancelled"
0x1800283ca  jmp     short loc_1800283D3
0x1800283cc  lea     rcx, aHintUserNotRes; "Hint user not responsive"
0x1800283d3  test    edi, edi
0x1800283d5  jz      short loc_1800283FC
0x1800283d7  sub     edi, 1
0x1800283da  jz      short loc_1800283F3
0x1800283dc  cmp     edi, 1
0x1800283df  jz      short loc_1800283EA
0x1800283e1  lea     rax, aUnknownState; "Unknown state"
0x1800283e8  jmp     short loc_180028403
0x1800283ea  lea     rax, aInvalidState; "Invalid state"
0x1800283f1  jmp     short loc_180028403
0x1800283f3  lea     rax, aHintCancelled; "Hint Cancelled"
0x1800283fa  jmp     short loc_180028403
0x1800283fc  lea     rax, aHintBegin; "Hint Begin"
0x180028403  mov     [rsp+48h+var_20], rcx
0x180028408  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18002840f  mov     rcx, [r10+38h]
0x180028413  mov     edx, 58h ; 'X'
0x180028418  mov     r9d, ebp
0x18002841b  mov     [rsp+48h+var_28], rax
0x180028420  call    WPP_SF_dSS
0x180028425  lea     r9, [rsp+48h+arg_0]
0x18002842a  mov     edx, 10004h
0x18002842f  mov     r8d, 8
0x180028435  mov     rcx, rsi
0x180028438  call    MSMSendOneXEventNotification
0x18002843d  mov     ebx, eax
0x18002843f  test    eax, eax
0x180028441  jz      short loc_180028471
0x180028443  mov     rcx, cs:WPP_GLOBAL_Control
0x18002844a  cmp     rcx, r14
0x18002844d  jz      short loc_18002849E
0x18002844f  test    byte ptr [rcx+44h], 1
0x180028453  jz      short loc_180028478
0x180028455  mov     rcx, [rcx+38h]
0x180028459  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180028460  mov     edx, 59h ; 'Y'
0x180028465  mov     dword ptr [rsp+48h+var_28], eax
0x180028469  mov     r9d, ebp
0x18002846c  call    WPP_SF_dd
0x180028471  mov     rcx, cs:WPP_GLOBAL_Control
0x180028478  cmp     rcx, r14
0x18002847b  jz      short loc_18002849E
0x18002847d  test    dword ptr [rcx+44h], 800h
0x180028484  jz      short loc_18002849E
0x180028486  mov     rcx, [rcx+38h]
0x18002848a  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180028491  mov     edx, 5Ah ; 'Z'
0x180028496  mov     r9d, ebx
0x180028499  call    WPP_SF_D
0x18002849e  mov     rbp, [rsp+48h+arg_10]
0x1800284a3  mov     eax, ebx
0x1800284a5  mov     rbx, [rsp+48h+arg_8]
0x1800284aa  add     rsp, 30h
0x1800284ae  pop     r14
0x1800284b0  pop     rdi
0x1800284b1  pop     rsi
0x1800284b2  retn
```
