# SearchData

- ea: `0x1400064b0`
- end: `0x140006723`
- name: `SearchData`
- size: `627`
- prototype: `__int64 __fastcall(LPCWSTR lpString)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140005910`
- `0x140005c78`
- `0x1400061e4`

## callees

- `0x1400064b0`
- `0x14000ce50`
- `0x14000d2d0`
- `0x14000d610`
- `0x14000e050`
- `0x14000e600`
- `0x14000eecc`
- `0x14000ef5c`
- `0x14000f0c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400066e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400066ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400066e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400066ff`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000660e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000660e`

## pseudocode

```c
__int64 __fastcall SearchData(LPCWSTR lpString, int a2, unsigned int a3, __int64 a4)
{
  const WCHAR *v4; // r14
  __int64 v5; // r12
  __int64 v6; // rbp
  _WORD *v8; // rsi
  unsigned int v9; // r15d
  void *Memory; // rax
  const WCHAR *v11; // r13
  unsigned int v12; // edi
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  unsigned int v17; // ebx
  __int64 Reason; // rax
  int v19; // ebx
  const WCHAR *v20; // r12
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // r8
  int v24; // eax
  _WORD *v25; // rax
  int v26; // eax
  const WCHAR *v27; // rdx
  DWORD v28; // ecx
  void *v30; // [rsp+70h] [rbp+8h] BYREF
  __int64 v31; // [rsp+88h] [rbp+20h]

  v31 = a4;
  v4 = lpString;
  v5 = a3;
  v6 = a4;
  v30 = 0;
  v8 = 0;
  if ( !lpString || !a4 )
  {
    v28 = 87;
    goto LABEL_38;
  }
  if ( a2 == 1 || a2 == 2 )
  {
    v9 = 0;
    v11 = lpString;
    goto LABEL_8;
  }
  v9 = 2 * a3 + 12;
  Memory = AllocateMemory(2 * v9);
  v30 = Memory;
  v8 = Memory;
  if ( Memory )
  {
    v11 = (const WCHAR *)Memory;
LABEL_8:
    v12 = 1;
    v13 = a2 - 1;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        v15 = v14 - 2;
        if ( v15 && (v16 = v15 - 1) != 0 )
        {
          if ( v16 == 2 )
          {
            v19 = 0;
            StringCopyW(v8, &cwszNullString, v9);
            v20 = (const WCHAR *)((char *)v4 + v5);
            if ( v4 < v20 )
            {
              do
              {
                if ( *v4 )
                {
                  if ( v19 == 1 )
                    StringConcatW(v8, v6 + 60, v9);
                  StringConcatW(v8, v4, v9);
                  v21 = 2LL * (unsigned int)lstrlenW(v4);
                }
                else
                {
                  v19 = 1;
                  v21 = 2;
                }
                v4 = (const WCHAR *)((char *)v4 + v21);
              }
              while ( v4 < v20 );
              v6 = v31;
            }
          }
          else
          {
            StringCopyW(v8, &cwszNullString, v9);
            v17 = 0;
            if ( (_DWORD)v5 )
            {
              while ( (unsigned int)SetReason2(1, L"%02X", *((unsigned __int8 *)v4 + v17)) )
              {
                Reason = GetReason();
                StringConcatW(v8, Reason, v9);
                if ( ++v17 >= (unsigned int)v5 )
                  goto LABEL_29;
              }
              goto LABEL_33;
            }
          }
        }
        else
        {
          v22 = StringCompareW(*(PCNZWCH *)(v6 + 120), L"0x", 1, 2);
          v23 = *(unsigned int *)v4;
          if ( v22 )
            v24 = SetReason2(1, L"%d", v23);
          else
            v24 = SetReason2(1, L"0x%x", v23);
          if ( !v24 )
          {
LABEL_33:
            FreeMemory(&v30);
            v28 = 14;
LABEL_38:
            SetLastError(v28);
            return 0;
          }
          v25 = (_WORD *)GetReason();
          StringCopyW(v8, v25, v9);
        }
      }
    }
LABEL_29:
    v26 = *(_DWORD *)(v6 + 36);
    v27 = *(const WCHAR **)(v6 + 120);
    if ( *(_DWORD *)(v6 + 40) )
    {
      if ( (unsigned int)StringCompareW(v11, v27, v26 == 0, 0) )
      {
LABEL_35:
        v12 = 0;
        SetLastError(0x490u);
      }
    }
    else if ( !(unsigned int)MatchPatternEx(v11, v27, v26 != 0 ? 2 : 258) )
    {
      goto LABEL_35;
    }
    FreeMemory(&v30);
    return v12;
  }
  return 0;
}

```

## disassembly

```asm
0x1400064b0  mov     [rsp+arg_8], rbx
0x1400064b5  mov     [rsp+arg_18], r9
0x1400064ba  push    rbp
0x1400064bb  push    rsi
0x1400064bc  push    rdi
0x1400064bd  push    r12
0x1400064bf  push    r13
0x1400064c1  push    r14
0x1400064c3  push    r15
0x1400064c5  sub     rsp, 30h
0x1400064c9  mov     r14, rcx
0x1400064cc  mov     r12d, r8d
0x1400064cf  xor     ecx, ecx
0x1400064d1  mov     rbp, r9
0x1400064d4  mov     [rsp+68h+arg_0], rcx
0x1400064d9  mov     ebx, edx
0x1400064db  mov     esi, ecx
0x1400064dd  test    r14, r14
0x1400064e0  jz      loc_1400066FA
0x1400064e6  test    r9, r9
0x1400064e9  jz      loc_1400066FA
0x1400064ef  mov     eax, edx
0x1400064f1  sub     eax, 1
0x1400064f4  jz      short loc_140006524
0x1400064f6  cmp     eax, 1
0x1400064f9  jz      short loc_140006524
0x1400064fb  lea     r15d, ds:0Ch[r12*2]
0x140006503  lea     ecx, [r15+r15]; dwBytes
0x140006507  call    AllocateMemory
0x14000650c  xor     ecx, ecx
0x14000650e  mov     [rsp+68h+arg_0], rax
0x140006513  mov     rsi, rax
0x140006516  test    rax, rax
0x140006519  jz      loc_14000670B
0x14000651f  mov     r13, rax
0x140006522  jmp     short loc_14000652A
0x140006524  mov     r15d, ecx
0x140006527  mov     r13, r14
0x14000652a  mov     edi, 1
0x14000652f  mov     [rsp+68h+var_48], r13
0x140006534  sub     ebx, edi
0x140006536  jz      loc_14000667B
0x14000653c  sub     ebx, edi
0x14000653e  jz      loc_14000667B
0x140006544  sub     ebx, 2
0x140006547  jz      loc_140006636
0x14000654d  sub     ebx, edi
0x14000654f  jz      loc_140006636
0x140006555  lea     rdx, cwszNullString
0x14000655c  mov     r8d, r15d
0x14000655f  cmp     ebx, 2
0x140006562  jz      short loc_1400065B5
0x140006564  mov     rcx, rsi
0x140006567  call    StringCopyW
0x14000656c  xor     eax, eax
0x14000656e  mov     ebx, eax
0x140006570  test    r12d, r12d
0x140006573  jz      loc_14000667B
0x140006579  mov     eax, ebx
0x14000657b  lea     rdx, a02x; "%02X"
0x140006582  mov     ecx, edi
0x140006584  movzx   r8d, byte ptr [rax+r14]
0x140006589  call    SetReason2
0x14000658e  test    eax, eax
0x140006590  jz      loc_1400066B3
0x140006596  call    GetReason
0x14000659b  mov     rdx, rax
0x14000659e  mov     r8d, r15d
0x1400065a1  mov     rcx, rsi
0x1400065a4  call    StringConcatW
0x1400065a9  add     ebx, edi
0x1400065ab  cmp     ebx, r12d
0x1400065ae  jb      short loc_140006579
0x1400065b0  jmp     loc_14000667B
0x1400065b5  mov     ebx, ecx
0x1400065b7  lea     rax, [rbp+3Ch]
0x1400065bb  mov     rcx, rsi
0x1400065be  mov     [rsp+68h+var_40], rax
0x1400065c3  call    StringCopyW
0x1400065c8  add     r12, r14
0x1400065cb  cmp     r14, r12
0x1400065ce  jnb     loc_14000667B
0x1400065d4  mov     rbp, [rsp+68h+var_40]
0x1400065d9  xor     r13d, r13d
0x1400065dc  cmp     [r14], r13w
0x1400065e0  jnz     short loc_1400065EB
0x1400065e2  mov     ebx, edi
0x1400065e4  mov     eax, 2
0x1400065e9  jmp     short loc_14000661F
0x1400065eb  cmp     ebx, edi
0x1400065ed  jnz     short loc_1400065FD
0x1400065ef  mov     r8d, r15d
0x1400065f2  mov     rdx, rbp
0x1400065f5  mov     rcx, rsi
0x1400065f8  call    StringConcatW
0x1400065fd  mov     r8d, r15d
0x140006600  mov     rdx, r14
0x140006603  mov     rcx, rsi
0x140006606  call    StringConcatW
0x14000660b  mov     rcx, r14; lpString
0x14000660e  call    cs:__imp_lstrlenW
0x140006615  nop     dword ptr [rax+rax+00h]
0x14000661a  mov     eax, eax
0x14000661c  add     rax, rax
0x14000661f  add     r14, rax
0x140006622  cmp     r14, r12
0x140006625  jb      short loc_1400065DC
0x140006627  mov     rbp, [rsp+68h+arg_18]
0x14000662f  mov     r13, [rsp+68h+var_48]
0x140006634  jmp     short loc_14000667B
0x140006636  mov     rcx, [rbp+78h]; lpString1
0x14000663a  lea     rdx, a0x; "0x"
0x140006641  mov     r9d, 2
0x140006647  mov     r8d, edi
0x14000664a  call    StringCompareW
0x14000664f  mov     r8d, [r14]
0x140006652  mov     ecx, edi
0x140006654  test    eax, eax
0x140006656  jnz     short loc_1400066AA
0x140006658  lea     rdx, a0xX; "0x%x"
0x14000665f  call    SetReason2
0x140006664  test    eax, eax
0x140006666  jz      short loc_1400066B3
0x140006668  call    GetReason
0x14000666d  mov     rdx, rax
0x140006670  mov     r8d, r15d
0x140006673  mov     rcx, rsi
0x140006676  call    StringCopyW
0x14000667b  mov     eax, [rbp+24h]
0x14000667e  xor     esi, esi
0x140006680  mov     rcx, r13; lpString1
0x140006683  mov     rdx, [rbp+78h]; lpString2
0x140006687  cmp     [rbp+28h], esi
0x14000668a  jnz     short loc_1400066C4
0x14000668c  neg     eax
0x14000668e  sbb     r8d, r8d
0x140006691  and     r8d, 0FFFFFF00h
0x140006698  add     r8d, 102h
0x14000669f  call    MatchPatternEx
0x1400066a4  test    eax, eax
0x1400066a6  jnz     short loc_1400066EC
0x1400066a8  jmp     short loc_1400066D9
0x1400066aa  lea     rdx, aD; "%d"
0x1400066b1  jmp     short loc_14000665F
0x1400066b3  lea     rcx, [rsp+68h+arg_0]
0x1400066b8  call    FreeMemory
0x1400066bd  mov     ecx, 0Eh
0x1400066c2  jmp     short loc_1400066FF
0x1400066c4  test    eax, eax
0x1400066c6  mov     r8d, esi
0x1400066c9  setz    r8b
0x1400066cd  xor     r9d, r9d
0x1400066d0  call    StringCompareW
0x1400066d5  test    eax, eax
0x1400066d7  jz      short loc_1400066EC
0x1400066d9  mov     ecx, 490h; dwErrCode
0x1400066de  mov     edi, esi
0x1400066e0  call    cs:__imp_SetLastError
0x1400066e7  nop     dword ptr [rax+rax+00h]
0x1400066ec  lea     rcx, [rsp+68h+arg_0]
0x1400066f1  call    FreeMemory
0x1400066f6  mov     eax, edi
0x1400066f8  jmp     short loc_14000670D
0x1400066fa  mov     ecx, 57h ; 'W'; dwErrCode
0x1400066ff  call    cs:__imp_SetLastError
0x140006706  nop     dword ptr [rax+rax+00h]
0x14000670b  xor     eax, eax
0x14000670d  mov     rbx, [rsp+68h+arg_8]
0x140006712  add     rsp, 30h
0x140006716  pop     r15
0x140006718  pop     r14
0x14000671a  pop     r13
0x14000671c  pop     r12
0x14000671e  pop     rdi
0x14000671f  pop     rsi
0x140006720  pop     rbp
0x140006721  retn
```
