# RtlCompareEncodedLBlobs

- ea: `0x180008220`
- end: `0x180008493`
- name: `RtlCompareEncodedLBlobs`
- size: `627`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180005b30`

## callees

- `0x180008100`
- `0x1800081a0`
- `0x180008220`
- `0x18000a8e0`
- `0x18001f9e8`

## string_xrefs

- `0x180008261`: `RtlCompareEncodedLBlobs`
- `0x1800082a7`: `RtlCompareEncodedLBlobs`
- `0x1800083ae`: `RtlCompareEncodedLBlobs`
- `0x180008412`: `RtlCompareEncodedLBlobs`
- `0x18000845f`: `RtlCompareEncodedLBlobs`
- `0x18000846a`: `Not-null check failed: ComparisonResult`

## pseudocode

```c
__int64 __fastcall RtlCompareEncodedLBlobs(_QWORD *a1, __int64 a2, _QWORD *a3, __int64 a4, int a5, int *a6)
{
  int v8; // ecx
  __int64 v9; // rbx
  __int64 v10; // rdi
  __int64 v11; // r12
  __int64 v12; // r14
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r9
  unsigned int v17; // esi
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r9
  unsigned int v22; // r15d
  unsigned int v23; // esi
  unsigned int v24; // eax
  const char *v25; // [rsp+20h] [rbp-58h] BYREF
  const char *v26; // [rsp+28h] [rbp-50h]
  __int64 v27; // [rsp+30h] [rbp-48h]
  const char *v28; // [rsp+38h] [rbp-40h]
  _BYTE v29[16]; // [rsp+40h] [rbp-38h] BYREF

  if ( a6 )
  {
    *a6 = 0;
    if ( a1 )
    {
      if ( a3 )
      {
        v8 = 0;
        v9 = a1[2];
        v10 = a3[2];
        v11 = v10 + *a3;
        v12 = v9 + *a1;
        if ( v9 == v12 )
        {
LABEL_21:
          if ( v10 != v11 )
            v8 = -1;
          *a6 = v8;
          return 0;
        }
        else
        {
          while ( 1 )
          {
            if ( v10 == v11 )
            {
LABEL_13:
              if ( v9 == v12 )
                goto LABEL_21;
LABEL_14:
              *a6 = 1;
              return 0;
            }
            v13 = RtlDecodeUtf16LE(v29, v9, v12);
            v17 = *(_DWORD *)v13;
            v9 = *(_QWORD *)(v13 + 8);
            if ( *(_DWORD *)v13 == -1 )
              break;
            v18 = RtlDecodeUtf16LE(&v25, v10, v11);
            v22 = *(_DWORD *)v18;
            v10 = *(_QWORD *)(v18 + 8);
            if ( *(_DWORD *)v18 == -1 )
            {
              if ( (int)v10 >= 0 )
                INTERNAL_ERROR_ACTION(v20);
              v27 = 2276;
              v25 = "onecore\\base\\lstring\\lblob.cpp";
              v26 = "RtlCompareEncodedLBlobs";
              v28 = "__rv.UcsCharacter != (0xffffffff)";
              RtlReportErrorOrigination(v20, v19, (unsigned int)v10, v21);
              return (unsigned int)v10;
            }
            v23 = RtlUpcaseUCSCharacter(v17);
            v24 = RtlUpcaseUCSCharacter(v22);
            if ( v23 < v24 )
            {
              *a6 = -1;
              return 0;
            }
            if ( v23 != v24 )
              goto LABEL_14;
            v8 = 0;
            if ( v9 == v12 )
              goto LABEL_13;
          }
          if ( (int)v9 >= 0 )
            INTERNAL_ERROR_ACTION(v15);
          v27 = 2275;
          v25 = "onecore\\base\\lstring\\lblob.cpp";
          v26 = "RtlCompareEncodedLBlobs";
          v28 = "__rv.UcsCharacter != (0xffffffff)";
          RtlReportErrorOrigination(v15, v14, (unsigned int)v9, v16);
          return (unsigned int)v9;
        }
      }
      else
      {
        v27 = 2254;
        v25 = "onecore\\base\\lstring\\lblob.cpp";
        v26 = "RtlCompareEncodedLBlobs";
        v28 = "Not-null check failed: String2";
        RtlReportErrorOrigination(a1, a2, 3221225485LL, a4);
        return 3221225485LL;
      }
    }
    else
    {
      v27 = 2252;
      v25 = "onecore\\base\\lstring\\lblob.cpp";
      v26 = "RtlCompareEncodedLBlobs";
      v28 = "Not-null check failed: String1";
      RtlReportErrorOrigination(0, a2, 3221225485LL, a4);
      return 3221225485LL;
    }
  }
  else
  {
    v27 = 2251;
    v25 = "onecore\\base\\lstring\\lblob.cpp";
    v26 = "RtlCompareEncodedLBlobs";
    v28 = "Not-null check failed: ComparisonResult";
    RtlReportErrorOrigination(a1, a2, 3221225485LL, a4);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x180008220  push    rbp
0x180008222  push    r13
0x180008224  mov     rbp, rsp
0x180008227  sub     rsp, 78h
0x18000822b  mov     r13, [rbp+arg_28]
0x18000822f  mov     rax, rcx
0x180008232  test    r13, r13
0x180008235  jz      loc_180008446
0x18000823b  mov     dword ptr [r13+0], 0
0x180008243  test    rcx, rcx
0x180008246  jnz     short loc_180008289
0x180008248  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x18000824f  mov     [rbp+var_48], 8CCh
0x180008257  mov     [rbp+var_58], rax
0x18000825b  mov     r8d, 0C000000Dh
0x180008261  lea     rax, aRtlcompareenco; "RtlCompareEncodedLBlobs"
0x180008268  mov     [rbp+var_50], rax
0x18000826c  lea     rax, aNotNullCheckFa_0; "Not-null check failed: String1"
0x180008273  mov     [rbp+var_40], rax
0x180008277  call    RtlReportErrorOrigination
0x18000827c  mov     eax, 0C000000Dh
0x180008281  add     rsp, 78h
0x180008285  pop     r13
0x180008287  pop     rbp
0x180008288  retn
0x180008289  test    r8, r8
0x18000828c  jnz     short loc_1800082CF
0x18000828e  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x180008295  mov     [rbp+var_48], 8CEh
0x18000829d  mov     [rbp+var_58], rax
0x1800082a1  mov     r8d, 0C000000Dh
0x1800082a7  lea     rax, aRtlcompareenco; "RtlCompareEncodedLBlobs"
0x1800082ae  mov     [rbp+var_50], rax
0x1800082b2  lea     rax, aNotNullCheckFa_5; "Not-null check failed: String2"
0x1800082b9  mov     [rbp+var_40], rax
0x1800082bd  call    RtlReportErrorOrigination
0x1800082c2  mov     eax, 0C000000Dh
0x1800082c7  add     rsp, 78h
0x1800082cb  pop     r13
0x1800082cd  pop     rbp
0x1800082ce  retn
0x1800082cf  mov     [rsp+78h+arg_8], rbx
0x1800082d7  xor     ecx, ecx
0x1800082d9  mov     rbx, [rax+10h]
0x1800082dd  mov     [rsp+78h+var_8], rsi
0x1800082e2  mov     [rsp+78h+var_10], rdi
0x1800082e7  mov     rdi, [r8+10h]
0x1800082eb  mov     [rsp+78h+var_18], r12
0x1800082f0  mov     r12, [r8]
0x1800082f3  mov     [rsp+78h+var_20], r14
0x1800082f8  add     r12, rdi
0x1800082fb  mov     r14, [rax]
0x1800082fe  add     r14, rbx
0x180008301  mov     [rsp+78h+var_28], r15
0x180008306  cmp     rbx, r14
0x180008309  jz      loc_180008431
0x18000830f  nop
0x180008310  cmp     rdi, r12
0x180008313  jz      short loc_18000836D
0x180008315  mov     r8, r14
0x180008318  lea     rcx, [rbp+var_38]
0x18000831c  mov     rdx, rbx
0x18000831f  call    RtlDecodeUtf16LE
0x180008324  mov     esi, [rax]
0x180008326  mov     rbx, [rax+8]
0x18000832a  cmp     esi, 0FFFFFFFFh
0x18000832d  jz      loc_1800083F4
0x180008333  mov     r8, r12
0x180008336  lea     rcx, [rbp+var_58]
0x18000833a  mov     rdx, rdi
0x18000833d  call    RtlDecodeUtf16LE
0x180008342  mov     r15d, [rax]
0x180008345  mov     rdi, [rax+8]
0x180008349  cmp     r15d, 0FFFFFFFFh
0x18000834d  jz      short loc_180008390
0x18000834f  mov     ecx, esi
0x180008351  call    RtlUpcaseUCSCharacter
0x180008356  mov     ecx, r15d
0x180008359  mov     esi, eax
0x18000835b  call    RtlUpcaseUCSCharacter
0x180008360  cmp     esi, eax
0x180008362  jb      short loc_180008383
0x180008364  jnz     short loc_180008376
0x180008366  xor     ecx, ecx
0x180008368  cmp     rbx, r14
0x18000836b  jnz     short loc_180008310
0x18000836d  cmp     rbx, r14
0x180008370  jz      loc_180008431
0x180008376  mov     eax, 1
0x18000837b  mov     [r13+0], eax
0x18000837f  xor     eax, eax
0x180008381  jmp     short loc_1800083CB
0x180008383  mov     eax, 0FFFFFFFFh
0x180008388  mov     [r13+0], eax
0x18000838c  xor     eax, eax
0x18000838e  jmp     short loc_1800083CB
0x180008390  test    edi, edi
0x180008392  jns     loc_180008487
0x180008398  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x18000839f  mov     [rbp+var_48], 8E4h
0x1800083a7  mov     [rbp+var_58], rax
0x1800083ab  mov     r8d, edi
0x1800083ae  lea     rax, aRtlcompareenco; "RtlCompareEncodedLBlobs"
0x1800083b5  mov     [rbp+var_50], rax
0x1800083b9  lea     rax, aRvUcscharacter; "__rv.UcsCharacter != (0xffffffff)"
0x1800083c0  mov     [rbp+var_40], rax
0x1800083c4  call    RtlReportErrorOrigination
0x1800083c9  mov     eax, edi
0x1800083cb  mov     r14, [rsp+78h+var_20]
0x1800083d0  mov     r12, [rsp+78h+var_18]
0x1800083d5  mov     rdi, [rsp+78h+var_10]
0x1800083da  mov     rsi, [rsp+78h+var_8]
0x1800083df  mov     rbx, [rsp+78h+arg_8]
0x1800083e7  mov     r15, [rsp+78h+var_28]
0x1800083ec  add     rsp, 78h
0x1800083f0  pop     r13
0x1800083f2  pop     rbp
0x1800083f3  retn
0x1800083f4  test    ebx, ebx
0x1800083f6  jns     loc_18000848D
0x1800083fc  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x180008403  mov     [rbp+var_48], 8E3h
0x18000840b  mov     [rbp+var_58], rax
0x18000840f  mov     r8d, ebx
0x180008412  lea     rax, aRtlcompareenco; "RtlCompareEncodedLBlobs"
0x180008419  mov     [rbp+var_50], rax
0x18000841d  lea     rax, aRvUcscharacter; "__rv.UcsCharacter != (0xffffffff)"
0x180008424  mov     [rbp+var_40], rax
0x180008428  call    RtlReportErrorOrigination
0x18000842d  mov     eax, ebx
0x18000842f  jmp     short loc_1800083CB
0x180008431  cmp     rdi, r12
0x180008434  mov     eax, 0FFFFFFFFh
0x180008439  cmovnz  ecx, eax
0x18000843c  mov     eax, ecx
0x18000843e  mov     [r13+0], ecx
0x180008442  xor     eax, eax
0x180008444  jmp     short loc_1800083CB
0x180008446  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x18000844d  mov     [rbp+var_48], 8CBh
0x180008455  mov     [rbp+var_58], rax
0x180008459  mov     r8d, 0C000000Dh
0x18000845f  lea     rax, aRtlcompareenco; "RtlCompareEncodedLBlobs"
0x180008466  mov     [rbp+var_50], rax
0x18000846a  lea     rax, aNotNullCheckFa_3; "Not-null check failed: ComparisonResult"
0x180008471  mov     [rbp+var_40], rax
0x180008475  call    RtlReportErrorOrigination
0x18000847a  mov     eax, 0C000000Dh
0x18000847f  add     rsp, 78h
0x180008483  pop     r13
0x180008485  pop     rbp
0x180008486  retn
0x180008487  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x18000848d  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
