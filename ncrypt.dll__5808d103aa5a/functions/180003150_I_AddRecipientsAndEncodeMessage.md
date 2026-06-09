# I_AddRecipientsAndEncodeMessage

- ea: `0x180003150`
- end: `0x180003459`
- name: `I_AddRecipientsAndEncodeMessage`
- size: `777`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003460`
- `0x180006090`

## callees

- `0x180001550`
- `0x180001c08`
- `0x180003150`
- `0x18000382c`
- `0x180003f1c`
- `0x18000d02c`
- `0x18000e120`
- `0x1800106f0`
- `0x180020010`

## string_xrefs

- `0x1800031bf`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x18000324f`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x1800032f9`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x18000341a`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`

## pseudocode

```c
__int64 __fastcall I_AddRecipientsAndEncodeMessage(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        int a9)
{
  int v11; // edx
  unsigned int Settings; // ebx
  unsigned int i; // edi
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rax
  unsigned int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  unsigned int v20; // eax
  unsigned int v21; // eax
  __int64 v22; // r9
  __int64 v23; // rcx
  __int64 v24; // rsi
  unsigned int j; // edi
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v30; // [rsp+40h] [rbp-10h] BYREF
  __int64 v31; // [rsp+48h] [rbp-8h] BYREF

  v30 = 0;
  v31 = 0;
  Settings = KeyProtRouter_GetSettings(&v31);
  if ( Settings )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
        (unsigned int)"Status",
        Settings,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
        206);
    goto LABEL_41;
  }
  for ( i = 0; ; ++i )
  {
    v14 = *(_QWORD *)(a2 + 8);
    if ( i >= *(_DWORD *)v14 )
    {
      v24 = *(_QWORD *)(v31 + 24);
      if ( v24 )
      {
        for ( j = 0; ; ++j )
        {
          v26 = *(_QWORD *)(v24 + 8);
          if ( j >= *(_DWORD *)v26 )
            break;
          v27 = *(_QWORD *)(v26 + 8);
          v28 = 32LL * j;
          if ( *(_DWORD *)(v28 + v27) <= 1u )
          {
            v21 = NCryptProtectKey(
                    *(_QWORD *)(*(_QWORD *)(v28 + v27 + 8) + 16LL),
                    *(_QWORD *)(v28 + v27 + 8),
                    a3,
                    a4,
                    a5,
                    a6,
                    (__int64)&v30,
                    a9);
            Settings = v21;
            if ( v21 )
            {
              v22 = 1108;
              goto LABEL_39;
            }
            v21 = CMSG_AddRecipient(a1, v30);
            Settings = v21;
            if ( v21 )
            {
              v22 = 1118;
              goto LABEL_39;
            }
            if ( v30 )
            {
              (*(void (**)(void))(a5 + 16))();
              v30 = 0;
            }
          }
          else
          {
            v21 = I_CreateAndCombinerRecipient(v24, j, a3, a4, a5, a6, &v30, a9);
            Settings = v21;
            if ( v21 )
            {
              v22 = 1088;
              goto LABEL_39;
            }
          }
        }
      }
      v21 = NCryptMsgEncode(a1, a7, a8);
      Settings = v21;
      if ( !v21 )
        goto LABEL_41;
      v22 = 1143;
      goto LABEL_39;
    }
    v15 = *(_QWORD *)(v14 + 8);
    v16 = 32LL * i;
    if ( !*(_DWORD *)(v16 + v15) )
    {
      Settings = -2146893785;
      goto LABEL_41;
    }
    if ( *(_DWORD *)(v16 + v15) <= 1u )
      break;
    v17 = I_CreateAndCombinerRecipient(a2, i, a3, a4, a5, a6, &v30, a9);
    if ( v17 )
    {
      DebugTraceError(
        v17,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
        1007);
LABEL_11:
      Settings = -2146893772;
      goto LABEL_41;
    }
LABEL_15:
    v21 = CMSG_AddRecipient(a1, v30);
    Settings = v21;
    if ( v21 )
    {
      v22 = 1052;
LABEL_39:
      v23 = v21;
LABEL_40:
      DebugTraceError(
        v23,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
        v22);
      goto LABEL_41;
    }
    if ( v30 )
    {
      (*(void (**)(void))(a5 + 16))();
      v30 = 0;
    }
  }
  v18 = *(_QWORD *)(v16 + v15 + 8);
  if ( *(_DWORD *)(v18 + 24) != 1 || (v19 = *(_QWORD *)(v18 + 16)) == 0 )
  {
    Settings = -2146893805;
    v22 = 1019;
    v23 = 2148073491LL;
    goto LABEL_40;
  }
  v20 = NCryptProtectKey(v19, v18, a3, a4, a5, a6, (__int64)&v30, a9);
  Settings = v20;
  if ( !v20 )
    goto LABEL_15;
  DebugTraceError(
    v20,
    "Status",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
    1035);
  if ( (a9 & 0x80u) == 0 )
    goto LABEL_11;
LABEL_41:
  if ( v30 )
    (*(void (**)(void))(a5 + 16))();
  return Settings;
}

```

## disassembly

```asm
0x180003150  mov     [rsp-38h+arg_0], rbx
0x180003155  mov     [rsp-38h+arg_18], r9d
0x18000315a  mov     [rsp-38h+arg_10], r8
0x18000315f  push    rbp
0x180003160  push    rsi
0x180003161  push    rdi
0x180003162  push    r12
0x180003164  push    r13
0x180003166  push    r14
0x180003168  push    r15
0x18000316a  mov     rbp, rsp
0x18000316d  sub     rsp, 50h
0x180003171  mov     r12, rcx
0x180003174  mov     [rbp+var_10], 0
0x18000317c  lea     rcx, [rbp+var_8]
0x180003180  mov     [rbp+var_8], 0
0x180003188  mov     rsi, rdx
0x18000318b  call    KeyProtRouter_GetSettings
0x180003190  mov     r14, [rbp+arg_20]
0x180003194  mov     ebx, eax
0x180003196  test    eax, eax
0x180003198  jz      short loc_1800031E8
0x18000319a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031a1  lea     rax, WPP_GLOBAL_Control
0x1800031a8  cmp     rcx, rax
0x1800031ab  jz      loc_18000342D
0x1800031b1  test    byte ptr [rcx+1Ch], 1
0x1800031b5  jz      loc_18000342D
0x1800031bb  mov     rcx, [rcx+10h]
0x1800031bf  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800031c6  mov     dword ptr [rsp+50h+var_20], 3CEh
0x1800031ce  lea     r9, aStatus; "Status"
0x1800031d5  mov     [rsp+50h+var_28], r8
0x1800031da  mov     dword ptr [rsp+50h+var_30], ebx
0x1800031de  call    WPP_SF_sDsd
0x1800031e3  jmp     loc_18000342D
0x1800031e8  mov     r15d, [rbp+arg_40]
0x1800031ef  xor     edi, edi
0x1800031f1  mov     r13, [rbp+arg_28]
0x1800031f5  mov     rcx, [rsi+8]
0x1800031f9  cmp     edi, [rcx]
0x1800031fb  jnb     loc_18000333B
0x180003201  mov     rdx, [rcx+8]
0x180003205  mov     eax, edi
0x180003207  shl     rax, 5
0x18000320b  cmp     dword ptr [rax+rdx], 0
0x18000320f  jbe     loc_180003331
0x180003215  cmp     dword ptr [rax+rdx], 1
0x180003219  jbe     short loc_18000326E
0x18000321b  mov     r9d, [rbp+arg_18]
0x18000321f  lea     rax, [rbp+var_10]
0x180003223  mov     r8, [rbp+arg_10]
0x180003227  mov     edx, edi
0x180003229  mov     [rsp+50h+var_18], r15d
0x18000322e  mov     rcx, rsi
0x180003231  mov     [rsp+50h+var_20], rax
0x180003236  mov     [rsp+50h+var_28], r13
0x18000323b  mov     [rsp+50h+var_30], r14
0x180003240  call    I_CreateAndCombinerRecipient
0x180003245  test    eax, eax
0x180003247  jz      short loc_1800032B5
0x180003249  mov     r9d, 3EFh
0x18000324f  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003256  lea     rdx, aStatus; "Status"
0x18000325d  mov     ecx, eax
0x18000325f  call    DebugTraceError
0x180003264  mov     ebx, 80090034h
0x180003269  jmp     loc_18000342D
0x18000326e  mov     rdx, [rax+rdx+8]
0x180003273  cmp     dword ptr [rdx+18h], 1
0x180003277  jnz     loc_18000331C
0x18000327d  mov     rcx, [rdx+10h]
0x180003281  test    rcx, rcx
0x180003284  jz      loc_18000331C
0x18000328a  mov     r9d, [rbp+arg_18]
0x18000328e  lea     rax, [rbp+var_10]
0x180003292  mov     r8, [rbp+arg_10]
0x180003296  mov     [rsp+50h+var_18], r15d
0x18000329b  mov     [rsp+50h+var_20], rax
0x1800032a0  mov     [rsp+50h+var_28], r13
0x1800032a5  mov     [rsp+50h+var_30], r14
0x1800032aa  call    NCryptProtectKey
0x1800032af  mov     ebx, eax
0x1800032b1  test    eax, eax
0x1800032b3  jnz     short loc_1800032F3
0x1800032b5  mov     rdx, [rbp+var_10]
0x1800032b9  mov     rcx, r12
0x1800032bc  call    CMSG_AddRecipient
0x1800032c1  mov     ebx, eax
0x1800032c3  test    eax, eax
0x1800032c5  jnz     short loc_1800032E8
0x1800032c7  mov     rcx, [rbp+var_10]
0x1800032cb  test    rcx, rcx
0x1800032ce  jz      short loc_1800032E1
0x1800032d0  mov     rax, [r14+10h]
0x1800032d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032d9  mov     [rbp+var_10], 0
0x1800032e1  inc     edi
0x1800032e3  jmp     loc_1800031F5
0x1800032e8  mov     r9d, 41Ch
0x1800032ee  jmp     loc_180003418
0x1800032f3  mov     r9d, 40Bh
0x1800032f9  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003300  lea     rdx, aStatus; "Status"
0x180003307  mov     ecx, eax
0x180003309  call    DebugTraceError
0x18000330e  test    r15b, r15b
0x180003311  js      loc_18000342D
0x180003317  jmp     loc_180003264
0x18000331c  mov     ebx, 80090013h
0x180003321  mov     r9d, 3FBh
0x180003327  mov     ecx, 80090013h
0x18000332c  jmp     loc_18000341A
0x180003331  mov     ebx, 80090027h
0x180003336  jmp     loc_18000342D
0x18000333b  mov     rax, [rbp+var_8]
0x18000333f  mov     rsi, [rax+18h]
0x180003343  test    rsi, rsi
0x180003346  jz      loc_1800033FC
0x18000334c  xor     edi, edi
0x18000334e  mov     rax, [rsi+8]
0x180003352  cmp     edi, [rax]
0x180003354  jnb     loc_1800033FC
0x18000335a  mov     rdx, [rax+8]
0x18000335e  lea     rax, [rbp+var_10]
0x180003362  mov     r9d, [rbp+arg_18]
0x180003366  mov     r8, [rbp+arg_10]
0x18000336a  mov     [rsp+50h+var_18], r15d
0x18000336f  mov     [rsp+50h+var_20], rax
0x180003374  mov     ecx, edi
0x180003376  shl     rcx, 5
0x18000337a  mov     [rsp+50h+var_28], r13
0x18000337f  mov     [rsp+50h+var_30], r14
0x180003384  cmp     dword ptr [rcx+rdx], 1
0x180003388  jbe     short loc_1800033A2
0x18000338a  mov     edx, edi
0x18000338c  mov     rcx, rsi
0x18000338f  call    I_CreateAndCombinerRecipient
0x180003394  mov     ebx, eax
0x180003396  test    eax, eax
0x180003398  jz      short loc_1800033E5
0x18000339a  mov     r9d, 440h
0x1800033a0  jmp     short loc_180003418
0x1800033a2  mov     rcx, [rcx+rdx+8]
0x1800033a7  mov     rdx, rcx
0x1800033aa  mov     rcx, [rcx+10h]
0x1800033ae  call    NCryptProtectKey
0x1800033b3  mov     ebx, eax
0x1800033b5  test    eax, eax
0x1800033b7  jnz     short loc_1800033F4
0x1800033b9  mov     rdx, [rbp+var_10]
0x1800033bd  mov     rcx, r12
0x1800033c0  call    CMSG_AddRecipient
0x1800033c5  mov     ebx, eax
0x1800033c7  test    eax, eax
0x1800033c9  jnz     short loc_1800033EC
0x1800033cb  mov     rcx, [rbp+var_10]
0x1800033cf  test    rcx, rcx
0x1800033d2  jz      short loc_1800033E5
0x1800033d4  mov     rax, [r14+10h]
0x1800033d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033dd  mov     [rbp+var_10], 0
0x1800033e5  inc     edi
0x1800033e7  jmp     loc_18000334E
0x1800033ec  mov     r9d, 45Eh
0x1800033f2  jmp     short loc_180003418
0x1800033f4  mov     r9d, 454h
0x1800033fa  jmp     short loc_180003418
0x1800033fc  mov     r8, [rbp+arg_38]
0x180003400  mov     rcx, r12
0x180003403  mov     rdx, [rbp+arg_30]
0x180003407  call    NCryptMsgEncode
0x18000340c  mov     ebx, eax
0x18000340e  test    eax, eax
0x180003410  jz      short loc_18000342D
0x180003412  mov     r9d, 477h
0x180003418  mov     ecx, eax
0x18000341a  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003421  lea     rdx, aStatus; "Status"
0x180003428  call    DebugTraceError
0x18000342d  mov     rcx, [rbp+var_10]
0x180003431  test    rcx, rcx
0x180003434  jz      short loc_18000343F
0x180003436  mov     rax, [r14+10h]
0x18000343a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000343f  mov     eax, ebx
0x180003441  mov     rbx, [rsp+50h+arg_0]
0x180003449  add     rsp, 50h
0x18000344d  pop     r15
0x18000344f  pop     r14
0x180003451  pop     r13
0x180003453  pop     r12
0x180003455  pop     rdi
0x180003456  pop     rsi
0x180003457  pop     rbp
0x180003458  retn
```
