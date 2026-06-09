# MSCryptEccSetKeyProperty

- ea: `0x18004aa90`
- end: `0x18004ad96`
- name: `MSCryptEccSetKeyProperty`
- size: `774`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18004a668`

## callees

- `0x18001155c`
- `0x1800123d0`
- `0x180047434`
- `0x18004aa90`
- `0x18004af70`
- `0x180081554`
- `0x180081764`
- `0x1800a4232`

## string_xrefs

- `0x18004aaa7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004ab5d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccSetKeyProperty(__int64 a1, const wchar_t *a2, _DWORD *a3, unsigned int a4, int a5)
{
  unsigned int v9; // ebx
  __int64 i; // rdx
  char *v11; // rcx
  __int64 v12; // r9
  __int64 v13; // rcx
  int Curve; // eax
  bool v15; // zf
  __int64 v16; // rax
  __int64 v17; // rdx
  _QWORD v19[9]; // [rsp+40h] [rbp-48h] BYREF
  unsigned int v20; // [rsp+90h] [rbp+8h] BYREF

  if ( !a1 )
  {
    v9 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        51);
    goto LABEL_46;
  }
  if ( *(_DWORD *)(a1 + 4) != 1297304409 )
  {
    v9 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        60);
    goto LABEL_46;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 4 )
    {
      v9 = -1073741811;
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 628);
LABEL_46:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          (_DWORD)a2,
          (_DWORD)a3,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          162);
      return v9;
    }
    v11 = byte_1800ADE78;
    if ( !a5 )
      v11 = byte_1800ADDB8;
    if ( *(_DWORD *)(a1 + 8) == *(_DWORD *)&v11[48 * i] )
      break;
  }
  if ( wcscmp_0(a2, L"ECCParameters") )
  {
    if ( !wcscmp_0(a2, L"ECCCurveName") )
    {
      v15 = *(_QWORD *)(a1 + 16) == 0;
      v19[0] = 0;
      v20 = 0;
      if ( !v15 )
      {
        v12 = 3784;
LABEL_15:
        v9 = -1073741637;
        v13 = 3221225659LL;
LABEL_16:
        DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v12);
        return v9;
      }
      Curve = ValidateCurveName(a3, a4, v19, &v20);
      v9 = Curve;
      if ( Curve >= 0 )
      {
        Curve = LoadCurve(a1 + 16, *(unsigned int *)(a1 + 8), v19[0], v20);
        v9 = Curve;
        if ( Curve >= 0 )
          return v9;
        v12 = 3799;
      }
      else
      {
        v12 = 3792;
      }
    }
    else
    {
      if ( !wcscmp_0(a2, L"KeyLength") || !wcscmp_0(a2, L"KeyStrength") )
      {
        if ( a4 != 4 || !a3 || (v16 = *(_QWORD *)(a1 + 16)) == 0 )
        {
          v9 = -1073741811;
          v12 = 3812;
          v13 = 3221225485LL;
          goto LABEL_16;
        }
        v17 = *(_QWORD *)(v16 + 8);
        if ( *(_DWORD *)(v17 + 12) == *a3 || *(_DWORD *)(v17 + 24) == *a3 )
          return 0;
        v12 = 3825;
        goto LABEL_15;
      }
      if ( (unsigned int)(*(_DWORD *)(a1 + 8) - 196615) > 3 || wcscmp_0(a2, L"PrivKeyVal") )
      {
        v12 = 3846;
        goto LABEL_15;
      }
      Curve = SetEccPrivateKeyVal(a1, a3, a4);
      v9 = Curve;
      if ( Curve >= 0 )
        return v9;
      v12 = 3839;
    }
LABEL_19:
    v13 = (unsigned int)Curve;
    goto LABEL_16;
  }
  if ( *(_QWORD *)(a1 + 16) )
  {
    v12 = 3760;
    goto LABEL_15;
  }
  Curve = AssignGenericDomainParameters((int)a1 + 16, *(_DWORD *)(a1 + 8), (_DWORD)a3, a4, 0, 0);
  v9 = Curve;
  if ( Curve < 0 )
  {
    v12 = 3767;
    goto LABEL_19;
  }
  return v9;
}

```

## disassembly

```asm
0x18004aa90  push    rbx
0x18004aa92  push    rbp
0x18004aa93  push    rsi
0x18004aa94  push    rdi
0x18004aa95  push    r12
0x18004aa97  push    r14
0x18004aa99  sub     rsp, 58h
0x18004aa9d  lea     r12, WPP_GLOBAL_Control
0x18004aaa4  mov     r14d, r9d
0x18004aaa7  lea     rdi, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004aaae  mov     rbx, r8
0x18004aab1  mov     rbp, rdx
0x18004aab4  mov     rsi, rcx
0x18004aab7  test    rcx, rcx
0x18004aaba  jz      loc_18004AD13
0x18004aac0  cmp     dword ptr [rcx+4], 4D534B59h
0x18004aac7  jz      short loc_18004AAF8
0x18004aac9  mov     ebx, 0C000000Dh
0x18004aace  mov     esi, ebx
0x18004aad0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004aad7  cmp     rcx, r12
0x18004aada  jz      loc_18004AD52
0x18004aae0  mov     eax, [rcx+2Ch]
0x18004aae3  test    al, 1
0x18004aae5  jz      loc_18004AD52
0x18004aaeb  mov     [rsp+88h+var_58], 23Ch
0x18004aaf3  jmp     loc_18004AD35
0x18004aaf8  xor     edx, edx
0x18004aafa  cmp     edx, 4
0x18004aafd  jnb     loc_18004ACF0
0x18004ab03  cmp     [rsp+88h+arg_20], 0
0x18004ab0b  lea     rax, byte_1800ADDB8
0x18004ab12  lea     rcx, byte_1800ADE78
0x18004ab19  cmovz   rcx, rax
0x18004ab1d  lea     rax, [rdx+rdx*2]
0x18004ab21  add     rax, rax
0x18004ab24  mov     eax, [rcx+rax*8]
0x18004ab27  cmp     [rsi+8], eax
0x18004ab2a  jz      short loc_18004AB30
0x18004ab2c  inc     edx
0x18004ab2e  jmp     short loc_18004AAFA
0x18004ab30  lea     rdx, aEccparameters; "ECCParameters"
0x18004ab37  mov     rcx, rbp; Str1
0x18004ab3a  call    wcscmp_0
0x18004ab3f  test    eax, eax
0x18004ab41  jnz     short loc_18004ABA8
0x18004ab43  lea     rcx, [rsi+10h]
0x18004ab47  cmp     qword ptr [rcx], 0
0x18004ab4b  jz      short loc_18004AB75
0x18004ab4d  mov     r9d, 0EB0h
0x18004ab53  mov     ebx, 0C00000BBh
0x18004ab58  mov     ecx, 0C00000BBh
0x18004ab5d  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004ab64  lea     rdx, aStatus; "Status"
0x18004ab6b  call    DebugTraceError
0x18004ab70  jmp     loc_18004AD86
0x18004ab75  mov     edx, [rsi+8]
0x18004ab78  mov     r9d, r14d
0x18004ab7b  mov     dword ptr [rsp+88h+var_60], 0
0x18004ab83  mov     r8, rbx
0x18004ab86  mov     [rsp+88h+var_68], 0
0x18004ab8f  call    AssignGenericDomainParameters
0x18004ab94  mov     ebx, eax
0x18004ab96  test    eax, eax
0x18004ab98  jns     loc_18004AD86
0x18004ab9e  mov     r9d, 0EB7h
0x18004aba4  mov     ecx, eax
0x18004aba6  jmp     short loc_18004AB5D
0x18004aba8  lea     rdx, aEcccurvename; "ECCCurveName"
0x18004abaf  mov     rcx, rbp; Str1
0x18004abb2  call    wcscmp_0
0x18004abb7  test    eax, eax
0x18004abb9  jnz     short loc_18004AC31
0x18004abbb  cmp     qword ptr [rsi+10h], 0
0x18004abc0  mov     [rsp+88h+var_48], 0
0x18004abc9  mov     [rsp+88h+arg_0], eax
0x18004abd0  jz      short loc_18004ABDD
0x18004abd2  mov     r9d, 0EC8h
0x18004abd8  jmp     loc_18004AB53
0x18004abdd  lea     r9, [rsp+88h+arg_0]
0x18004abe5  mov     edx, r14d
0x18004abe8  lea     r8, [rsp+88h+var_48]
0x18004abed  mov     rcx, rbx
0x18004abf0  call    ValidateCurveName
0x18004abf5  mov     ebx, eax
0x18004abf7  test    eax, eax
0x18004abf9  jns     short loc_18004AC03
0x18004abfb  mov     r9d, 0ED0h
0x18004ac01  jmp     short loc_18004ABA4
0x18004ac03  mov     r9d, [rsp+88h+arg_0]
0x18004ac0b  lea     rcx, [rsi+10h]
0x18004ac0f  mov     r8, [rsp+88h+var_48]
0x18004ac14  mov     edx, [rsi+8]
0x18004ac17  call    LoadCurve
0x18004ac1c  mov     ebx, eax
0x18004ac1e  test    eax, eax
0x18004ac20  jns     loc_18004AD86
0x18004ac26  mov     r9d, 0ED7h
0x18004ac2c  jmp     loc_18004ABA4
0x18004ac31  lea     rdx, aKeylength; "KeyLength"
0x18004ac38  mov     rcx, rbp; Str1
0x18004ac3b  call    wcscmp_0
0x18004ac40  test    eax, eax
0x18004ac42  jz      short loc_18004ACA5
0x18004ac44  lea     rdx, aKeystrength; "KeyStrength"
0x18004ac4b  mov     rcx, rbp; Str1
0x18004ac4e  call    wcscmp_0
0x18004ac53  test    eax, eax
0x18004ac55  jz      short loc_18004ACA5
0x18004ac57  mov     eax, [rsi+8]
0x18004ac5a  sub     eax, 30007h
0x18004ac5f  cmp     eax, 3
0x18004ac62  ja      short loc_18004AC9A
0x18004ac64  lea     rdx, aPrivkeyval; "PrivKeyVal"
0x18004ac6b  mov     rcx, rbp; Str1
0x18004ac6e  call    wcscmp_0
0x18004ac73  test    eax, eax
0x18004ac75  jnz     short loc_18004AC9A
0x18004ac77  mov     r8d, r14d
0x18004ac7a  mov     rdx, rbx
0x18004ac7d  mov     rcx, rsi
0x18004ac80  call    SetEccPrivateKeyVal
0x18004ac85  mov     ebx, eax
0x18004ac87  test    eax, eax
0x18004ac89  jns     loc_18004AD86
0x18004ac8f  mov     r9d, 0EFFh
0x18004ac95  jmp     loc_18004ABA4
0x18004ac9a  mov     r9d, 0F06h
0x18004aca0  jmp     loc_18004AB53
0x18004aca5  cmp     r14d, 4
0x18004aca9  jnz     short loc_18004ACDB
0x18004acab  test    rbx, rbx
0x18004acae  jz      short loc_18004ACDB
0x18004acb0  mov     rax, [rsi+10h]
0x18004acb4  test    rax, rax
0x18004acb7  jz      short loc_18004ACDB
0x18004acb9  mov     rdx, [rax+8]
0x18004acbd  mov     ecx, [rbx]
0x18004acbf  cmp     [rdx+0Ch], ecx
0x18004acc2  jz      short loc_18004ACD4
0x18004acc4  cmp     [rdx+18h], ecx
0x18004acc7  jz      short loc_18004ACD4
0x18004acc9  mov     r9d, 0EF1h
0x18004accf  jmp     loc_18004AB53
0x18004acd4  xor     ebx, ebx
0x18004acd6  jmp     loc_18004AD86
0x18004acdb  mov     ebx, 0C000000Dh
0x18004ace0  mov     r9d, 0EE4h
0x18004ace6  mov     ecx, 0C000000Dh
0x18004aceb  jmp     loc_18004AB5D
0x18004acf0  mov     ebx, 0C000000Dh
0x18004acf5  lea     rdx, aStatus; "Status"
0x18004acfc  mov     r9d, 274h
0x18004ad02  mov     r8, rdi
0x18004ad05  mov     ecx, 0C000000Dh
0x18004ad0a  mov     esi, ebx
0x18004ad0c  call    DebugTraceError
0x18004ad11  jmp     short loc_18004AD52
0x18004ad13  mov     ebx, 0C000000Dh
0x18004ad18  mov     esi, ebx
0x18004ad1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ad21  cmp     rcx, r12
0x18004ad24  jz      short loc_18004AD52
0x18004ad26  mov     eax, [rcx+2Ch]
0x18004ad29  test    al, 1
0x18004ad2b  jz      short loc_18004AD52
0x18004ad2d  mov     [rsp+88h+var_58], 233h
0x18004ad35  mov     rcx, [rcx+18h]
0x18004ad39  lea     r9, aStatus; "Status"
0x18004ad40  mov     [rsp+88h+var_60], rdi
0x18004ad45  mov     dword ptr [rsp+88h+var_68], 0C000000Dh
0x18004ad4d  call    WPP_SF_sDsd
0x18004ad52  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ad59  cmp     rcx, r12
0x18004ad5c  jz      short loc_18004AD86
0x18004ad5e  mov     eax, [rcx+2Ch]
0x18004ad61  test    al, 1
0x18004ad63  jz      short loc_18004AD86
0x18004ad65  mov     rcx, [rcx+18h]
0x18004ad69  lea     r9, aStatus; "Status"
0x18004ad70  mov     [rsp+88h+var_58], 0EA2h
0x18004ad78  mov     [rsp+88h+var_60], rdi
0x18004ad7d  mov     dword ptr [rsp+88h+var_68], esi
0x18004ad81  call    WPP_SF_sDsd
0x18004ad86  mov     eax, ebx
0x18004ad88  add     rsp, 58h
0x18004ad8c  pop     r14
0x18004ad8e  pop     r12
0x18004ad90  pop     rdi
0x18004ad91  pop     rsi
0x18004ad92  pop     rbp
0x18004ad93  pop     rbx
0x18004ad94  retn
```
