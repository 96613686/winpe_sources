# ParseTimeSource(ushort *,ushort * *)

- ea: `0x180017340`
- end: `0x1800174de`
- name: `?ParseTimeSource@@YAJPEAGPEAPEAG@Z`
- size: `414`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016c38`

## callees

- `0x180014660`
- `0x180014da0`
- `0x180017340`

## import_xrefs

- `msvcrt!wcstoul` at `0x180017403`
- `msvcrt!wcstoul` at `0x180017403`

## string_xrefs

- `0x18001743e`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`
- `0x1800174b4`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`

## pseudocode

```c
__int64 __fastcall ParseTimeSource(unsigned __int16 *a1, unsigned __int16 **a2)
{
  signed int v3; // eax
  const struct _EVENT_DESCRIPTOR *v4; // rdx
  CEventLogger *v5; // rcx
  unsigned int v6; // ebx
  unsigned __int16 *v7; // rdi
  const unsigned __int16 *v8; // rbp
  const unsigned __int16 *v9; // rsi
  int v10; // r15d
  wchar_t *v11; // rcx
  const unsigned __int16 *v12; // rbx
  unsigned int v13; // r9d
  signed int v14; // eax
  const struct _EVENT_DESCRIPTOR *v15; // rdx
  CEventLogger *v16; // rcx
  signed int v17; // eax
  const struct _EVENT_DESCRIPTOR *v18; // rdx
  CEventLogger *v19; // rcx
  unsigned __int16 *v21; // [rsp+68h] [rbp+10h] BYREF

  *a2 = 0;
  v21 = 0;
  v3 = DuplicateString(a1, &v21);
  v6 = v3;
  if ( v3 >= 0 )
  {
    v7 = v21;
    v8 = 0;
    v9 = 0;
    v10 = 1;
LABEL_4:
    v11 = 0;
    v12 = 0;
    while ( v10 == 1 )
    {
      if ( v8 )
        goto LABEL_30;
      switch ( *v7 )
      {
        case 0u:
          v10 = 0;
          goto LABEL_19;
        case 0x20u:
          *v7++ = 0;
LABEL_19:
          if ( v12 )
          {
            if ( v11 && (wcstoul(v11, 0, 0) & 2) != 0 )
            {
              if ( v9 )
                v12 = v9;
              v9 = v12;
            }
            else
            {
              v8 = v12;
            }
          }
          goto LABEL_4;
        case 0x2Cu:
          if ( !v12 )
          {
            v13 = 1135;
            goto LABEL_28;
          }
          if ( v11 )
          {
            v13 = 1136;
LABEL_28:
            CEventLogger::LogError(
              (CEventLogger *)v11,
              v4,
              L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
              v13,
              L"ParseTimeSource",
              0);
            return (unsigned int)-2147467259;
          }
          *v7++ = 0;
          v11 = v7;
          break;
        default:
          if ( !v12 && !v11 )
            v12 = v7;
          ++v7;
          break;
      }
    }
    if ( v8 )
    {
LABEL_30:
      v14 = DuplicateString(v8, a2);
      v6 = v14;
      if ( v14 < 0 )
        CEventLogger::LogError(
          v16,
          v15,
          L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
          0x48Fu,
          L"ParseTimeSource",
          v14);
    }
    else if ( v9 )
    {
      v17 = DuplicateString(v9, a2);
      v6 = v17;
      if ( v17 < 0 )
        CEventLogger::LogError(
          v19,
          v18,
          L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
          0x495u,
          L"ParseTimeSource",
          v17);
    }
    else
    {
      v6 = -2147467259;
      CEventLogger::LogError(
        (CEventLogger *)v11,
        v4,
        L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
        0x499u,
        L"ParseTimeSource",
        0x80004005);
    }
  }
  else
  {
    CEventLogger::LogError(
      v5,
      v4,
      L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
      0x41Cu,
      L"ParseTimeSource",
      v3);
  }
  return v6;
}

```

## disassembly

```asm
0x180017340  mov     rax, rsp
0x180017343  mov     [rax+8], rbx
0x180017347  mov     [rax+18h], rbp
0x18001734b  push    rsi
0x18001734c  push    rdi
0x18001734d  push    r12
0x18001734f  push    r14
0x180017351  push    r15
0x180017353  sub     rsp, 30h
0x180017357  xor     r12d, r12d
0x18001735a  mov     r14, rdx
0x18001735d  mov     [rdx], r12
0x180017360  lea     rdx, [rax+10h]; unsigned __int16 **
0x180017364  mov     [rax+10h], r12
0x180017368  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x18001736d  mov     ebx, eax
0x18001736f  test    eax, eax
0x180017371  jns     short loc_180017382
0x180017373  mov     [rsp+58h+var_30], eax
0x180017377  mov     r9d, 41Ch
0x18001737d  jmp     loc_1800174AD
0x180017382  mov     rdi, [rsp+58h+arg_8]
0x180017387  mov     rbp, r12
0x18001738a  mov     rsi, r12
0x18001738d  mov     r15d, 1
0x180017393  mov     rcx, r12; this
0x180017396  mov     rbx, r12
0x180017399  cmp     r15d, 1
0x18001739d  jnz     loc_180017456
0x1800173a3  test    rbp, rbp
0x1800173a6  jnz     loc_18001745B
0x1800173ac  cmp     [rdi], r12w
0x1800173b0  jz      short loc_1800173F1
0x1800173b2  cmp     word ptr [rdi], 20h ; ' '
0x1800173b6  jz      short loc_1800173E7
0x1800173b8  cmp     word ptr [rdi], 2Ch ; ','
0x1800173bc  jz      short loc_1800173D0
0x1800173be  test    rbx, rbx
0x1800173c1  jnz     short loc_1800173CA
0x1800173c3  test    rcx, rcx
0x1800173c6  cmovz   rbx, rdi
0x1800173ca  add     rdi, 2
0x1800173ce  jmp     short loc_180017399
0x1800173d0  test    rbx, rbx
0x1800173d3  jz      short loc_18001742C
0x1800173d5  test    rcx, rcx
0x1800173d8  jnz     short loc_180017424
0x1800173da  mov     [rdi], r12w
0x1800173de  add     rdi, 2
0x1800173e2  mov     rcx, rdi
0x1800173e5  jmp     short loc_180017399
0x1800173e7  mov     [rdi], r12w
0x1800173eb  add     rdi, 2
0x1800173ef  jmp     short loc_1800173F4
0x1800173f1  mov     r15d, r12d
0x1800173f4  test    rbx, rbx
0x1800173f7  jz      short loc_180017393
0x1800173f9  test    rcx, rcx
0x1800173fc  jz      short loc_18001741C
0x1800173fe  xor     r8d, r8d; Radix
0x180017401  xor     edx, edx; EndPtr
0x180017403  call    cs:__imp_wcstoul
0x180017409  test    al, 2
0x18001740b  jz      short loc_18001741C
0x18001740d  test    rsi, rsi
0x180017410  cmovnz  rbx, rsi
0x180017414  mov     rsi, rbx
0x180017417  jmp     loc_180017393
0x18001741c  mov     rbp, rbx
0x18001741f  jmp     loc_180017393
0x180017424  mov     r9d, 470h
0x18001742a  jmp     short loc_180017432
0x18001742c  mov     r9d, 46Fh; unsigned int
0x180017432  lea     rax, aParsetimesourc; "ParseTimeSource"
0x180017439  mov     [rsp+58h+var_30], r12d; unsigned int
0x18001743e  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x180017445  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x18001744a  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18001744f  mov     ebx, 80004005h
0x180017454  jmp     short loc_1800174C5
0x180017456  test    rbp, rbp
0x180017459  jz      short loc_180017478
0x18001745b  mov     rdx, r14; unsigned __int16 **
0x18001745e  mov     rcx, rbp; Src
0x180017461  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x180017466  mov     ebx, eax
0x180017468  test    eax, eax
0x18001746a  jns     short loc_1800174C5
0x18001746c  mov     [rsp+58h+var_30], eax
0x180017470  mov     r9d, 48Fh
0x180017476  jmp     short loc_1800174AD
0x180017478  test    rsi, rsi
0x18001747b  jz      short loc_18001749A
0x18001747d  mov     rdx, r14; unsigned __int16 **
0x180017480  mov     rcx, rsi; Src
0x180017483  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x180017488  mov     ebx, eax
0x18001748a  test    eax, eax
0x18001748c  jns     short loc_1800174C5
0x18001748e  mov     [rsp+58h+var_30], eax
0x180017492  mov     r9d, 495h
0x180017498  jmp     short loc_1800174AD
0x18001749a  mov     ebx, 80004005h
0x18001749f  mov     [rsp+58h+var_30], 80004005h; unsigned int
0x1800174a7  mov     r9d, 499h; unsigned int
0x1800174ad  lea     rax, aParsetimesourc; "ParseTimeSource"
0x1800174b4  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x1800174bb  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x1800174c0  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1800174c5  mov     rbp, [rsp+58h+arg_10]
0x1800174ca  mov     eax, ebx
0x1800174cc  mov     rbx, [rsp+58h+arg_0]
0x1800174d1  add     rsp, 30h
0x1800174d5  pop     r15
0x1800174d7  pop     r14
0x1800174d9  pop     r12
0x1800174db  pop     rdi
0x1800174dc  pop     rsi
0x1800174dd  retn
```
