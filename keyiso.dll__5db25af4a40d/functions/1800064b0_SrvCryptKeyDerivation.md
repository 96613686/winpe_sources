# SrvCryptKeyDerivation

- ea: `0x1800064b0`
- end: `0x1800066d8`
- name: `SrvCryptKeyDerivation`
- size: `552`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64, int, __int64, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x1800026e4`
- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x1800055e0`
- `0x180005f00`
- `0x180006010`
- `0x1800064b0`
- `0x180019010`

## string_xrefs

- `0x18000658a`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x1800065db`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180006627`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x1800066b2`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptKeyDerivation(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        int a8)
{
  __int64 v9; // rax
  int v10; // edx
  int v11; // r8d
  __int64 v12; // rsi
  __int64 v13; // r14
  __int64 v14; // rdi
  int v15; // edx
  int v16; // ebx
  int v17; // r8d
  int v18; // eax

  if ( a1 )
  {
    v9 = SrvLookupAndReferenceKey(a1, a3, 0);
    v12 = v9;
    if ( v9 )
    {
      if ( a7 )
      {
        v13 = *(_QWORD *)(v9 + 32);
        v14 = 0;
        if ( !a4 || (v14 = MapRPCToBufferDesc(a4)) != 0 )
        {
          v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64, int, __int64, int))(v13 + 256))(
                  *(_QWORD *)(v13 + 296),
                  *(_QWORD *)(v12 + 40),
                  v14,
                  a5,
                  a6,
                  a7,
                  a8);
          if ( v16 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v15,
                v17,
                (unsigned int)"Status",
                v16,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
                60);
            v16 = NormalizeNteStatus((unsigned int)v16);
          }
          if ( v14 )
            FreeBufferDesc(v14);
        }
        else
        {
          v16 = -2146893810;
          DebugTraceError(
            2148073486LL,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
            3880);
        }
      }
      else
      {
        v16 = -2146893785;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v10,
            v11,
            (unsigned int)"Status",
            39,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
            30);
      }
      v18 = SrvDereferenceKey(v12);
      if ( v18 < 0 && v16 >= 0 )
        return (unsigned int)v18;
    }
    else
    {
      v16 = -2146893786;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v10,
          v11,
          (unsigned int)"Status",
          38,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
          21);
    }
  }
  else
  {
    v16 = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        12);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800064b0  push    rbx
0x1800064b2  push    rbp
0x1800064b3  push    rsi
0x1800064b4  push    rdi
0x1800064b5  push    r14
0x1800064b7  sub     rsp, 40h
0x1800064bb  mov     rbx, r9
0x1800064be  mov     rax, r8
0x1800064c1  test    rcx, rcx
0x1800064c4  jz      loc_180006560
0x1800064ca  xor     r8d, r8d
0x1800064cd  mov     rdx, rax
0x1800064d0  call    SrvLookupAndReferenceKey
0x1800064d5  mov     rsi, rax
0x1800064d8  test    rax, rax
0x1800064db  jz      loc_18000667B
0x1800064e1  mov     rbp, [rsp+68h+arg_30]
0x1800064e9  test    rbp, rbp
0x1800064ec  jz      loc_1800065FD
0x1800064f2  mov     r14, [rax+20h]
0x1800064f6  xor     edi, edi
0x1800064f8  test    rbx, rbx
0x1800064fb  jnz     loc_1800065C1
0x180006501  mov     eax, [rsp+68h+arg_38]
0x180006508  mov     r8, rdi
0x18000650b  mov     r9, [rsp+68h+arg_20]
0x180006513  mov     rdx, [rsi+28h]
0x180006517  mov     rcx, [r14+128h]
0x18000651e  mov     [rsp+68h+var_38], eax
0x180006522  mov     eax, [rsp+68h+arg_28]
0x180006529  mov     [rsp+68h+var_40], rbp
0x18000652e  mov     [rsp+68h+var_48], eax
0x180006532  mov     rax, [r14+100h]
0x180006539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000653e  mov     ebx, eax
0x180006540  test    eax, eax
0x180006542  jnz     loc_180006654
0x180006548  test    rdi, rdi
0x18000654b  jnz     short loc_1800065B7
0x18000654d  mov     rcx, rsi
0x180006550  call    SrvDereferenceKey
0x180006555  test    eax, eax
0x180006557  jns     short loc_1800065AA
0x180006559  test    ebx, ebx
0x18000655b  cmovns  ebx, eax
0x18000655e  jmp     short loc_1800065AA
0x180006560  mov     ebx, 80090026h
0x180006565  mov     rcx, cs:WPP_GLOBAL_Control
0x18000656c  lea     rax, WPP_GLOBAL_Control
0x180006573  cmp     rcx, rax
0x180006576  jz      short loc_1800065AA
0x180006578  test    byte ptr [rcx+1Ch], 1
0x18000657c  jz      short loc_1800065AA
0x18000657e  mov     [rsp+68h+var_38], 0F0Ch
0x180006586  mov     rcx, [rcx+10h]
0x18000658a  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006591  mov     [rsp+68h+var_40], rax
0x180006596  lea     r9, aStatus; "Status"
0x18000659d  mov     [rsp+68h+var_48], 80090026h
0x1800065a5  call    WPP_SF_sDsd
0x1800065aa  mov     eax, ebx
0x1800065ac  add     rsp, 40h
0x1800065b0  pop     r14
0x1800065b2  pop     rdi
0x1800065b3  pop     rsi
0x1800065b4  pop     rbp
0x1800065b5  pop     rbx
0x1800065b6  retn
0x1800065b7  mov     rcx, rdi
0x1800065ba  call    _FreeBufferDesc
0x1800065bf  jmp     short loc_18000654D
0x1800065c1  mov     rcx, rbx
0x1800065c4  call    _MapRPCToBufferDesc
0x1800065c9  mov     rdi, rax
0x1800065cc  test    rax, rax
0x1800065cf  jnz     loc_180006501
0x1800065d5  mov     r9d, 0F28h
0x1800065db  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800065e2  lea     rdx, aStatus; "Status"
0x1800065e9  mov     ecx, 8009000Eh
0x1800065ee  mov     ebx, 8009000Eh
0x1800065f3  call    DebugTraceError
0x1800065f8  jmp     loc_18000654D
0x1800065fd  mov     ebx, 80090027h
0x180006602  mov     rcx, cs:WPP_GLOBAL_Control
0x180006609  lea     rax, WPP_GLOBAL_Control
0x180006610  cmp     rcx, rax
0x180006613  jz      loc_18000654D
0x180006619  test    byte ptr [rcx+1Ch], 1
0x18000661d  jz      loc_18000654D
0x180006623  mov     rcx, [rcx+10h]
0x180006627  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000662e  mov     [rsp+68h+var_38], 0F1Eh
0x180006636  lea     r9, aStatus; "Status"
0x18000663d  mov     [rsp+68h+var_40], rax
0x180006642  mov     [rsp+68h+var_48], 80090027h
0x18000664a  call    WPP_SF_sDsd
0x18000664f  jmp     loc_18000654D
0x180006654  mov     rcx, cs:WPP_GLOBAL_Control
0x18000665b  lea     rax, WPP_GLOBAL_Control
0x180006662  cmp     rcx, rax
0x180006665  jz      short loc_18000666D
0x180006667  test    byte ptr [rcx+1Ch], 1
0x18000666b  jnz     short loc_1800066AE
0x18000666d  mov     ecx, ebx
0x18000666f  call    NormalizeNteStatus
0x180006674  mov     ebx, eax
0x180006676  jmp     loc_180006548
0x18000667b  mov     ebx, 80090026h
0x180006680  mov     rcx, cs:WPP_GLOBAL_Control
0x180006687  lea     rax, WPP_GLOBAL_Control
0x18000668e  cmp     rcx, rax
0x180006691  jz      loc_1800065AA
0x180006697  test    byte ptr [rcx+1Ch], 1
0x18000669b  jz      loc_1800065AA
0x1800066a1  mov     [rsp+68h+var_38], 0F15h
0x1800066a9  jmp     loc_180006586
0x1800066ae  mov     rcx, [rcx+10h]
0x1800066b2  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800066b9  mov     [rsp+68h+var_38], 0F3Ch
0x1800066c1  lea     r9, aStatus; "Status"
0x1800066c8  mov     [rsp+68h+var_40], rax
0x1800066cd  mov     [rsp+68h+var_48], ebx
0x1800066d1  call    WPP_SF_sDsd
0x1800066d6  jmp     short loc_18000666D
```
