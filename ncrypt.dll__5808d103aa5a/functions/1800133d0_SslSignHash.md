# SslSignHash

- ea: `0x1800133d0`
- end: `0x1800134ff`
- name: `SslSignHash`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x1800133d0`
- `0x180020010`

## string_xrefs

- `0x180013427`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x1800134e8`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslSignHash(
        __int64 a1,
        __int64 a2,
        NCryptKeyName **a3,
        NCryptAlgorithmName **a4,
        BYTE *a5,
        DWORD *a6,
        DWORD *a7)
{
  unsigned int v7; // ebx
  int v8; // eax

  if ( a1 && *(_DWORD *)a1 >= 0x1B0u && *(_DWORD *)(a1 + 4) == 1145324609 && !*(_DWORD *)(a1 + 12) )
  {
    if ( a2 && *(_DWORD *)a2 >= 0x20u && *(_DWORD *)(a2 + 4) == 1145324610 )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(a1 + 208))(*(_QWORD *)(a1 + 424), *(_QWORD *)(a2 + 16));
      v7 = v8;
      if ( v8 < 0 )
        DebugTraceError((unsigned int)v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 3201);
      else
        v7 = 0;
    }
    else
    {
      v7 = -2146893786;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2,
          (_DWORD)a3,
          (unsigned int)"Status",
          38,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
          110);
    }
  }
  else
  {
    v7 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        102);
  }
  return NormalizeNteStatus(v7, (NCRYPT_KEY_HANDLE *)a2, a3, a4, a5, a6, a7);
}

```

## disassembly

```asm
0x1800133d0  push    rbx
0x1800133d2  sub     rsp, 50h
0x1800133d6  mov     r10, rdx
0x1800133d9  test    rcx, rcx
0x1800133dc  jz      short loc_1800133F5
0x1800133de  cmp     dword ptr [rcx], 1B0h
0x1800133e4  jb      short loc_1800133F5
0x1800133e6  cmp     dword ptr [rcx+4], 44444441h
0x1800133ed  jnz     short loc_1800133F5
0x1800133ef  cmp     dword ptr [rcx+0Ch], 0
0x1800133f3  jz      short loc_18001344C
0x1800133f5  mov     ebx, 80090026h
0x1800133fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180013401  lea     rax, WPP_GLOBAL_Control
0x180013408  cmp     rcx, rax
0x18001340b  jz      loc_1800134D6
0x180013411  test    byte ptr [rcx+1Ch], 1
0x180013415  jz      loc_1800134D6
0x18001341b  mov     dword ptr [rsp+58h+var_28], 0C66h
0x180013423  mov     rcx, [rcx+10h]
0x180013427  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001342e  mov     [rsp+58h+var_30], rax
0x180013433  lea     r9, aStatus; "Status"
0x18001343a  mov     dword ptr [rsp+58h+var_38], 80090026h
0x180013442  call    WPP_SF_sDsd
0x180013447  jmp     loc_1800134D6
0x18001344c  test    r10, r10
0x18001344f  jz      short loc_18001345F
0x180013451  cmp     dword ptr [rdx], 20h ; ' '
0x180013454  jb      short loc_18001345F
0x180013456  cmp     dword ptr [rdx+4], 44444442h
0x18001345d  jz      short loc_180013487
0x18001345f  mov     ebx, 80090026h
0x180013464  mov     rcx, cs:WPP_GLOBAL_Control
0x18001346b  lea     rax, WPP_GLOBAL_Control
0x180013472  cmp     rcx, rax
0x180013475  jz      short loc_1800134D6
0x180013477  test    byte ptr [rcx+1Ch], 1
0x18001347b  jz      short loc_1800134D6
0x18001347d  mov     dword ptr [rsp+58h+var_28], 0C6Eh
0x180013485  jmp     short loc_180013423
0x180013487  mov     edx, [rsp+58h+arg_38]
0x18001348e  mov     rax, [rcx+0D0h]
0x180013495  mov     rcx, [rcx+1A8h]
0x18001349c  mov     [rsp+58h+var_20], edx
0x1800134a0  mov     rdx, [rsp+58h+arg_30]
0x1800134a8  mov     [rsp+58h+var_28], rdx
0x1800134ad  mov     edx, dword ptr [rsp+58h+arg_28]
0x1800134b4  mov     dword ptr [rsp+58h+var_30], edx
0x1800134b8  mov     rdx, [rsp+58h+arg_20]
0x1800134c0  mov     [rsp+58h+var_38], rdx
0x1800134c5  mov     rdx, [r10+10h]
0x1800134c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134ce  mov     ebx, eax
0x1800134d0  test    eax, eax
0x1800134d2  js      short loc_1800134E2
0x1800134d4  xor     ebx, ebx
0x1800134d6  mov     ecx, ebx
0x1800134d8  add     rsp, 50h
0x1800134dc  pop     rbx
0x1800134dd  jmp     NormalizeNteStatus
0x1800134e2  mov     r9d, 0C81h
0x1800134e8  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800134ef  lea     rdx, aStatus; "Status"
0x1800134f6  mov     ecx, eax
0x1800134f8  call    DebugTraceError
0x1800134fd  jmp     short loc_1800134D6
```
