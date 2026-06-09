# LoadProviderEx

- ea: `0x180007df4`
- end: `0x180008199`
- name: `LoadProviderEx`
- size: `933`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180006730`
- `0x180008da0`
- `0x1800102c0`

## callees

- `0x1800077f0`
- `0x180007df4`
- `0x1800081a0`
- `0x1800081e8`
- `0x180008750`
- `0x180008a90`
- `0x18000d02c`
- `0x18000e120`
- `0x180016304`
- `0x18001f15d`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007f6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007f6b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007e33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007e33`

## string_xrefs

- `0x180007f26`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18000800d`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180008072`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18000814e`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180008165`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
__int64 __fastcall LoadProviderEx(unsigned int *a1, int a2, unsigned int a3, __int64 *a4, void *a5)
{
  __int64 v8; // rax
  int v9; // r8d
  __int64 v10; // rdi
  HMODULE v11; // r14
  int v12; // edx
  unsigned int Interface; // esi
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // r8d
  int v18; // ebx
  unsigned int v20; // eax
  int v21; // r8d
  __int64 v22; // rax
  int v23; // edx
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  __int64 v31; // r9
  __int64 v32; // rcx
  HMODULE v33; // [rsp+40h] [rbp-20h] BYREF
  __int64 v34; // [rsp+48h] [rbp-18h] BYREF
  void *Src; // [rsp+50h] [rbp-10h] BYREF

  Src = 0;
  v33 = 0;
  if ( g_fLoaderInitialized )
  {
    EnterCriticalSection(&g_csLoaderLock);
    v8 = FindInLoadedProviderList(a1);
    v34 = v8;
    v10 = v8;
    if ( v8 )
    {
      v11 = *(HMODULE *)(v8 + 8);
    }
    else
    {
      Interface = LoadImage((__int64)a1, &v33);
      if ( Interface )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v23,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
            (unsigned int)"sResult",
            Interface,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
            169);
        v11 = v33;
        goto LABEL_20;
      }
      v11 = v33;
    }
    Interface = LoadInterface(v11, a1, v9, (_WORD **)&Src);
    if ( Interface )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v12,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
          (unsigned int)"sResult",
          Interface,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
          186);
      goto LABEL_20;
    }
    if ( a3 )
      goto LABEL_11;
    v14 = *a1;
    if ( *a1 > 6 )
    {
      v27 = v14 - 7;
      if ( v27 )
      {
        v28 = v27 - 1;
        if ( !v28 )
          goto LABEL_9;
        v29 = v28 - 65529;
        if ( v29 )
        {
          v30 = v29 - 1;
          if ( v30 )
          {
            if ( v30 != 2 )
              goto LABEL_41;
            a3 = 40;
          }
          else
          {
            a3 = 392;
          }
        }
        else
        {
          a3 = 256;
        }
      }
      else
      {
        a3 = 88;
      }
    }
    else if ( v14 == 6 )
    {
      a3 = 48;
    }
    else
    {
      v15 = v14 - 1;
      if ( !v15 )
        goto LABEL_9;
      v24 = v15 - 1;
      if ( !v24 )
        goto LABEL_9;
      v25 = v24 - 1;
      if ( v25 )
      {
        v26 = v25 - 1;
        if ( v26 )
        {
          if ( v26 != 1 )
          {
LABEL_41:
            a3 = 0;
            goto LABEL_10;
          }
LABEL_9:
          a3 = 96;
          goto LABEL_10;
        }
        a3 = 104;
      }
      else
      {
        a3 = 112;
      }
    }
LABEL_10:
    if ( !a3 )
    {
      Interface = -1073741811;
      v31 = 2500;
      v32 = 3221225485LL;
LABEL_56:
      DebugTraceError(v32, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", v31);
LABEL_20:
      v18 = 1;
      if ( !v10 && v11 )
        FreeImage(v11);
      goto LABEL_21;
    }
LABEL_11:
    memcpy_0(a5, Src, a3);
    if ( !v10 )
    {
      v20 = NewLoadedProviderHandle(a1, v11, &v34);
      Interface = v20;
      if ( !v20 )
      {
        v10 = v34;
        v22 = g_pLoadedProviderList;
        g_pLoadedProviderList = v34;
        *(_QWORD *)(v34 + 24) = v22;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          WPP_SF_qqSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            Interface + 28,
            v21,
            (_DWORD)a1,
            v10,
            *(_QWORD *)v10,
            *(_DWORD *)(v10 + 16));
        goto LABEL_16;
      }
      DebugTraceError(v20, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", 2539);
      v10 = v34;
      goto LABEL_20;
    }
    v16 = *(_DWORD *)(v10 + 16);
    v17 = v16 + 1;
    if ( v16 + 1 >= v16 )
    {
      *(_DWORD *)(v10 + 16) = v17;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_qqSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, v17, (_DWORD)a1, v10, *(_QWORD *)v10, v17);
LABEL_16:
      *a4 = v10;
LABEL_22:
      LeaveCriticalSection(&g_csLoaderLock);
      return Interface;
    }
    Interface = -1073741670;
    v31 = 2517;
    v32 = 3221225626LL;
    goto LABEL_56;
  }
  v18 = 0;
  Interface = -1073741595;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
      (unsigned int)"sResult",
      229,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
      143);
LABEL_21:
  *a4 = 0;
  if ( v18 )
    goto LABEL_22;
  return Interface;
}

```

## disassembly

```asm
0x180007df4  push    rbp
0x180007df6  push    rbx
0x180007df7  push    rsi
0x180007df8  push    rdi
0x180007df9  push    r12
0x180007dfb  push    r14
0x180007dfd  push    r15
0x180007dff  mov     rbp, rsp
0x180007e02  sub     rsp, 60h
0x180007e06  cmp     cs:g_fLoaderInitialized, 0
0x180007e0d  mov     r12, r9
0x180007e10  mov     ebx, r8d
0x180007e13  mov     [rbp+Src], 0
0x180007e1b  mov     r15, rcx
0x180007e1e  mov     [rbp+var_20], 0
0x180007e26  jz      loc_180007FE1
0x180007e2c  lea     rcx, g_csLoaderLock; lpCriticalSection
0x180007e33  call    cs:__imp_EnterCriticalSection
0x180007e39  mov     rcx, r15
0x180007e3c  call    _FindInLoadedProviderList
0x180007e41  mov     [rbp+var_18], rax
0x180007e45  mov     rdi, rax
0x180007e48  test    rax, rax
0x180007e4b  jz      loc_18000803A
0x180007e51  mov     r14, [rax+8]
0x180007e55  lea     r9, [rbp+Src]
0x180007e59  mov     rdx, r15
0x180007e5c  mov     rcx, r14
0x180007e5f  call    _LoadInterface
0x180007e64  mov     esi, eax
0x180007e66  test    eax, eax
0x180007e68  jnz     loc_180007F09
0x180007e6e  test    ebx, ebx
0x180007e70  jnz     short loc_180007E9A
0x180007e72  mov     eax, [r15]
0x180007e75  cmp     eax, 6
0x180007e78  ja      loc_1800080E0
0x180007e7e  jz      loc_1800080D6
0x180007e84  sub     eax, 1
0x180007e87  jnz     loc_18000809F
0x180007e8d  mov     ebx, 60h ; '`'
0x180007e92  test    ebx, ebx
0x180007e94  jz      loc_180008125
0x180007e9a  mov     rdx, [rbp+Src]; Src
0x180007e9e  mov     rcx, [rbp+arg_20]; void *
0x180007ea2  mov     r8d, ebx; Size
0x180007ea5  call    memcpy_0
0x180007eaa  test    rdi, rdi
0x180007ead  jz      loc_180007F82
0x180007eb3  mov     eax, [rdi+10h]
0x180007eb6  lea     r8d, [rax+1]
0x180007eba  cmp     r8d, eax
0x180007ebd  jb      loc_180008137
0x180007ec3  mov     [rdi+10h], r8d
0x180007ec7  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ece  lea     rax, WPP_GLOBAL_Control
0x180007ed5  cmp     rcx, rax
0x180007ed8  jz      short loc_180007F03
0x180007eda  test    byte ptr [rcx+1Ch], 20h
0x180007ede  jz      short loc_180007F03
0x180007ee0  mov     edx, 1Bh
0x180007ee5  mov     [rsp+60h+var_30], r8d
0x180007eea  mov     rax, [rdi]
0x180007eed  mov     r9, r15
0x180007ef0  mov     rcx, [rcx+10h]
0x180007ef4  mov     [rsp+60h+var_38], rax
0x180007ef9  mov     [rsp+60h+var_40], rdi
0x180007efe  call    WPP_SF_qqSD
0x180007f03  mov     [r12], rdi
0x180007f07  jmp     short loc_180007F64
0x180007f09  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f10  lea     rax, WPP_GLOBAL_Control
0x180007f17  cmp     rcx, rax
0x180007f1a  jz      short loc_180007F4A
0x180007f1c  test    byte ptr [rcx+1Ch], 1
0x180007f20  jz      short loc_180007F4A
0x180007f22  mov     rcx, [rcx+10h]
0x180007f26  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007f2d  mov     [rsp+60h+var_30], 9BAh
0x180007f35  lea     r9, aSresult; "sResult"
0x180007f3c  mov     [rsp+60h+var_38], r8
0x180007f41  mov     dword ptr [rsp+60h+var_40], esi
0x180007f45  call    WPP_SF_sDsd
0x180007f4a  mov     ebx, 1
0x180007f4f  test    rdi, rdi
0x180007f52  jz      loc_180008183
0x180007f58  mov     qword ptr [r12], 0
0x180007f60  test    ebx, ebx
0x180007f62  jz      short loc_180007F71
0x180007f64  lea     rcx, g_csLoaderLock; lpCriticalSection
0x180007f6b  call    cs:__imp_LeaveCriticalSection
0x180007f71  mov     eax, esi
0x180007f73  add     rsp, 60h
0x180007f77  pop     r15
0x180007f79  pop     r14
0x180007f7b  pop     r12
0x180007f7d  pop     rdi
0x180007f7e  pop     rsi
0x180007f7f  pop     rbx
0x180007f80  pop     rbp
0x180007f81  retn
0x180007f82  lea     r8, [rbp+var_18]
0x180007f86  mov     rdx, r14
0x180007f89  mov     rcx, r15
0x180007f8c  call    _NewLoadedProviderHandle
0x180007f91  mov     esi, eax
0x180007f93  test    eax, eax
0x180007f95  jnz     loc_18000815F
0x180007f9b  mov     rdi, [rbp+var_18]
0x180007f9f  mov     rax, cs:g_pLoadedProviderList
0x180007fa6  mov     cs:g_pLoadedProviderList, rdi
0x180007fad  mov     [rdi+18h], rax
0x180007fb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fb8  lea     rax, WPP_GLOBAL_Control
0x180007fbf  cmp     rcx, rax
0x180007fc2  jz      loc_180007F03
0x180007fc8  test    byte ptr [rcx+1Ch], 20h
0x180007fcc  jz      loc_180007F03
0x180007fd2  mov     eax, [rdi+10h]
0x180007fd5  lea     edx, [rsi+1Ch]
0x180007fd8  mov     [rsp+60h+var_30], eax
0x180007fdc  jmp     loc_180007EEA
0x180007fe1  xor     ebx, ebx
0x180007fe3  mov     esi, 0C00000E5h
0x180007fe8  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fef  lea     rax, WPP_GLOBAL_Control
0x180007ff6  cmp     rcx, rax
0x180007ff9  jz      loc_180007F58
0x180007fff  test    byte ptr [rcx+1Ch], 1
0x180008003  jz      loc_180007F58
0x180008009  mov     rcx, [rcx+10h]
0x18000800d  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008014  mov     [rsp+60h+var_30], 98Fh
0x18000801c  lea     r9, aSresult; "sResult"
0x180008023  mov     [rsp+60h+var_38], r8
0x180008028  mov     dword ptr [rsp+60h+var_40], 0C00000E5h
0x180008030  call    WPP_SF_sDsd
0x180008035  jmp     loc_180007F58
0x18000803a  lea     rdx, [rbp+var_20]
0x18000803e  mov     rcx, r15
0x180008041  call    _LoadImage
0x180008046  mov     esi, eax
0x180008048  test    eax, eax
0x18000804a  jnz     short loc_180008055
0x18000804c  mov     r14, [rbp+var_20]
0x180008050  jmp     loc_180007E55
0x180008055  mov     rcx, cs:WPP_GLOBAL_Control
0x18000805c  lea     rax, WPP_GLOBAL_Control
0x180008063  cmp     rcx, rax
0x180008066  jz      short loc_180008096
0x180008068  test    byte ptr [rcx+1Ch], 1
0x18000806c  jz      short loc_180008096
0x18000806e  mov     rcx, [rcx+10h]
0x180008072  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008079  mov     [rsp+60h+var_30], 9A9h
0x180008081  lea     r9, aSresult; "sResult"
0x180008088  mov     [rsp+60h+var_38], r8
0x18000808d  mov     dword ptr [rsp+60h+var_40], esi
0x180008091  call    WPP_SF_sDsd
0x180008096  mov     r14, [rbp+var_20]
0x18000809a  jmp     loc_180007F4A
0x18000809f  sub     eax, 1
0x1800080a2  jz      loc_180007E8D
0x1800080a8  sub     eax, 1
0x1800080ab  jz      short loc_1800080CC
0x1800080ad  sub     eax, 1
0x1800080b0  jz      short loc_1800080C2
0x1800080b2  cmp     eax, 1
0x1800080b5  jz      loc_180007E8D
0x1800080bb  xor     ebx, ebx
0x1800080bd  jmp     loc_180007E92
0x1800080c2  mov     ebx, 68h ; 'h'
0x1800080c7  jmp     loc_180007E92
0x1800080cc  mov     ebx, 70h ; 'p'
0x1800080d1  jmp     loc_180007E92
0x1800080d6  mov     ebx, 30h ; '0'
0x1800080db  jmp     loc_180007E92
0x1800080e0  sub     eax, 7
0x1800080e3  jz      short loc_18000811B
0x1800080e5  sub     eax, 1
0x1800080e8  jz      loc_180007E8D
0x1800080ee  sub     eax, 0FFF9h
0x1800080f3  jz      short loc_180008111
0x1800080f5  sub     eax, 1
0x1800080f8  jz      short loc_180008107
0x1800080fa  cmp     eax, 2
0x1800080fd  jnz     short loc_1800080BB
0x1800080ff  lea     ebx, [rax+26h]
0x180008102  jmp     loc_180007E92
0x180008107  mov     ebx, 188h
0x18000810c  jmp     loc_180007E92
0x180008111  mov     ebx, 100h
0x180008116  jmp     loc_180007E92
0x18000811b  mov     ebx, 58h ; 'X'
0x180008120  jmp     loc_180007E92
0x180008125  mov     esi, 0C000000Dh
0x18000812a  mov     r9d, 9C4h
0x180008130  mov     ecx, 0C000000Dh
0x180008135  jmp     short loc_180008147
0x180008137  mov     esi, 0C000009Ah
0x18000813c  mov     r9d, 9D5h
0x180008142  mov     ecx, 0C000009Ah
0x180008147  lea     rdx, aSresult; "sResult"
0x18000814e  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008155  call    DebugTraceError
0x18000815a  jmp     loc_180007F4A
0x18000815f  mov     r9d, 9EBh
0x180008165  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000816c  lea     rdx, aSresult; "sResult"
0x180008173  mov     ecx, eax
0x180008175  call    DebugTraceError
0x18000817a  mov     rdi, [rbp+var_18]
0x18000817e  jmp     loc_180007F4A
0x180008183  test    r14, r14
0x180008186  jz      loc_180007F58
0x18000818c  mov     rcx, r14
0x18000818f  call    _FreeImage
0x180008194  jmp     loc_180007F58
```
