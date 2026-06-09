# VsmLoadInterface

- ea: `0x18006948c`
- end: `0x1800697c5`
- name: `VsmLoadInterface`
- size: `825`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18005aca8`

## callees

- `0x18000743c`
- `0x1800693c8`
- `0x18006948c`
- `0x18009d860`

## string_xrefs

- `0x1800694ce`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x1800694ec`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
__int64 __fastcall VsmLoadInterface(__int64 a1, __int64 a2, unsigned int a3, _OWORD *a4)
{
  unsigned int v7; // ebx
  int LinkedInterfaceProvider; // eax
  unsigned int v9; // edi
  __int64 v10; // r9
  __int64 v11; // rcx
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  int v16; // ebx
  __int64 v17; // r9
  unsigned int v18; // ebx
  unsigned int v19; // ebx
  unsigned int v20; // ebx
  unsigned int v21; // ebx
  _OWORD *v22; // rax
  __int64 v23; // rcx
  __int128 v24; // xmm1
  _OWORD *v26; // [rsp+30h] [rbp-10h] BYREF
  __int64 (__fastcall *v27)(const WCHAR *, __int64, _OWORD **, _QWORD); // [rsp+38h] [rbp-8h] BYREF

  v27 = 0;
  v26 = 0;
  v7 = a1;
  LinkedInterfaceProvider = VsmGetLinkedInterfaceProvider(a1, &v27);
  v9 = LinkedInterfaceProvider;
  if ( LinkedInterfaceProvider < 0 )
  {
    v10 = 2348;
    v11 = (unsigned int)LinkedInterfaceProvider;
LABEL_3:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", v10);
    return v9;
  }
  if ( v7 > 6 )
  {
    v18 = v7 - 7;
    if ( !v18 )
    {
      v16 = v27(L"Microsoft Primitive Provider", a2, &v26, a3);
      if ( v16 < 0 )
      {
        v17 = 2117;
        goto LABEL_39;
      }
      goto LABEL_40;
    }
    v19 = v18 - 1;
    if ( !v19 )
    {
      v16 = v27(L"Microsoft Primitive Provider", a2, &v26, a3);
      if ( v16 < 0 )
      {
        v17 = 2130;
        goto LABEL_39;
      }
      goto LABEL_40;
    }
    v20 = v19 - 65529;
    if ( !v20 )
    {
      v16 = ((__int64 (__fastcall *)(const WCHAR *, _OWORD **, _QWORD))v27)(L"Microsoft Primitive Provider", &v26, a3);
      if ( v16 < 0 )
      {
        v17 = 2142;
        goto LABEL_39;
      }
      goto LABEL_40;
    }
    v21 = v20 - 1;
    if ( !v21 )
    {
      v16 = ((__int64 (__fastcall *)(const WCHAR *, _OWORD **, _QWORD))v27)(L"Microsoft Primitive Provider", &v26, a3);
      if ( v16 < 0 )
      {
        v17 = 2166;
        goto LABEL_39;
      }
      goto LABEL_40;
    }
    if ( v21 == 2 )
    {
      v16 = ((__int64 (__fastcall *)(const WCHAR *, _OWORD **, _QWORD))v27)(L"Microsoft Primitive Provider", &v26, a3);
      if ( v16 < 0 )
      {
        v17 = 2154;
        goto LABEL_39;
      }
      goto LABEL_40;
    }
    goto LABEL_28;
  }
  if ( v7 == 6 )
  {
    v16 = ((__int64 (__fastcall *)(const WCHAR *, _OWORD **, _QWORD))v27)(L"Microsoft Primitive Provider", &v26, a3);
    if ( v16 < 0 )
    {
      v17 = 2104;
      goto LABEL_39;
    }
    goto LABEL_40;
  }
  v12 = v7 - 1;
  if ( !v12 )
  {
    v16 = v27(L"Microsoft Primitive Provider", a2, &v26, a3);
    if ( v16 < 0 )
    {
      v17 = 2040;
      goto LABEL_39;
    }
    goto LABEL_40;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    v16 = v27(L"Microsoft Primitive Provider", a2, &v26, a3);
    if ( v16 < 0 )
    {
      v17 = 2053;
      goto LABEL_39;
    }
    goto LABEL_40;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    v16 = v27(L"Microsoft Primitive Provider", a2, &v26, a3);
    if ( v16 < 0 )
    {
      v17 = 2066;
      goto LABEL_39;
    }
    goto LABEL_40;
  }
  v15 = v14 - 1;
  if ( v15 )
  {
    if ( v15 == 1 )
    {
      v16 = v27(L"Microsoft Primitive Provider", a2, &v26, a3);
      if ( v16 < 0 )
      {
        v17 = 2092;
LABEL_39:
        DebugTraceError(
          (unsigned int)v16,
          "ntStatus",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
          v17);
        v9 = v16;
        goto LABEL_41;
      }
      goto LABEL_40;
    }
LABEL_28:
    v9 = -1073741637;
    v16 = -1073741637;
    DebugTraceError(3221225659LL, "ntStatus", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", 2172);
LABEL_41:
    v10 = 2361;
    v11 = (unsigned int)v16;
    goto LABEL_3;
  }
  v16 = v27(L"Microsoft Primitive Provider", a2, &v26, a3);
  if ( v16 < 0 )
  {
    v17 = 2079;
    goto LABEL_39;
  }
LABEL_40:
  v9 = v16;
  v22 = v26;
  v23 = 3;
  do
  {
    *a4 = *v22;
    a4[1] = v22[1];
    a4[2] = v22[2];
    a4[3] = v22[3];
    a4[4] = v22[4];
    a4[5] = v22[5];
    a4[6] = v22[6];
    v24 = v22[7];
    v22 += 8;
    a4[7] = v24;
    a4 += 8;
    --v23;
  }
  while ( v23 );
  *(_QWORD *)a4 = *(_QWORD *)v22;
  return v9;
}

```

## disassembly

```asm
0x18006948c  push    rbp
0x18006948e  push    rbx
0x18006948f  push    rsi
0x180069490  push    rdi
0x180069491  push    r12
0x180069493  push    r14
0x180069495  push    r15
0x180069497  mov     rbp, rsp
0x18006949a  sub     rsp, 40h
0x18006949e  mov     r12, rdx
0x1800694a1  mov     [rbp+var_8], 0
0x1800694a9  lea     rdx, [rbp+var_8]
0x1800694ad  mov     [rbp+var_10], 0
0x1800694b5  mov     r14, r9
0x1800694b8  mov     r15d, r8d
0x1800694bb  mov     ebx, ecx
0x1800694bd  call    VsmGetLinkedInterfaceProvider
0x1800694c2  mov     edi, eax
0x1800694c4  test    eax, eax
0x1800694c6  jns     short loc_1800694E8
0x1800694c8  mov     r9d, 92Ch
0x1800694ce  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800694d5  mov     ecx, eax
0x1800694d7  lea     rdx, aStatus; "Status"
0x1800694de  call    DebugTraceError
0x1800694e3  jmp     loc_1800697B3
0x1800694e8  mov     rax, [rbp+var_8]
0x1800694ec  lea     rsi, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800694f3  cmp     ebx, 6
0x1800694f6  ja      loc_180069626
0x1800694fc  jz      loc_1800695FE
0x180069502  sub     ebx, 1
0x180069505  jz      loc_1800695D3
0x18006950b  sub     ebx, 1
0x18006950e  jz      loc_1800695A8
0x180069514  sub     ebx, 1
0x180069517  jz      short loc_18006957D
0x180069519  sub     ebx, 1
0x18006951c  jz      short loc_180069552
0x18006951e  cmp     ebx, 1
0x180069521  jnz     loc_18006964A
0x180069527  mov     r9d, r15d
0x18006952a  lea     r8, [rbp+var_10]
0x18006952e  mov     rdx, r12
0x180069531  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x180069538  call    _guard_dispatch_icall
0x18006953d  mov     ebx, eax
0x18006953f  test    eax, eax
0x180069541  jns     loc_180069739
0x180069547  mov     r9d, 82Ch
0x18006954d  jmp     loc_180069724
0x180069552  mov     r9d, r15d
0x180069555  lea     r8, [rbp+var_10]
0x180069559  mov     rdx, r12
0x18006955c  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x180069563  call    _guard_dispatch_icall
0x180069568  mov     ebx, eax
0x18006956a  test    eax, eax
0x18006956c  jns     loc_180069739
0x180069572  mov     r9d, 81Fh
0x180069578  jmp     loc_180069724
0x18006957d  mov     r9d, r15d
0x180069580  lea     r8, [rbp+var_10]
0x180069584  mov     rdx, r12
0x180069587  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x18006958e  call    _guard_dispatch_icall
0x180069593  mov     ebx, eax
0x180069595  test    eax, eax
0x180069597  jns     loc_180069739
0x18006959d  mov     r9d, 812h
0x1800695a3  jmp     loc_180069724
0x1800695a8  mov     r9d, r15d
0x1800695ab  lea     r8, [rbp+var_10]
0x1800695af  mov     rdx, r12
0x1800695b2  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x1800695b9  call    _guard_dispatch_icall
0x1800695be  mov     ebx, eax
0x1800695c0  test    eax, eax
0x1800695c2  jns     loc_180069739
0x1800695c8  mov     r9d, 805h
0x1800695ce  jmp     loc_180069724
0x1800695d3  mov     r9d, r15d
0x1800695d6  lea     r8, [rbp+var_10]
0x1800695da  mov     rdx, r12
0x1800695dd  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x1800695e4  call    _guard_dispatch_icall
0x1800695e9  mov     ebx, eax
0x1800695eb  test    eax, eax
0x1800695ed  jns     loc_180069739
0x1800695f3  mov     r9d, 7F8h
0x1800695f9  jmp     loc_180069724
0x1800695fe  mov     r8d, r15d
0x180069601  lea     rdx, [rbp+var_10]
0x180069605  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x18006960c  call    _guard_dispatch_icall
0x180069611  mov     ebx, eax
0x180069613  test    eax, eax
0x180069615  jns     loc_180069739
0x18006961b  mov     r9d, 838h
0x180069621  jmp     loc_180069724
0x180069626  sub     ebx, 7
0x180069629  jz      loc_180069702
0x18006962f  sub     ebx, 1
0x180069632  jz      loc_1800696DE
0x180069638  sub     ebx, 0FFF9h
0x18006963e  jz      short loc_1800696BD
0x180069640  sub     ebx, 1
0x180069643  jz      short loc_180069698
0x180069645  cmp     ebx, 2
0x180069648  jz      short loc_180069670
0x18006964a  mov     edi, 0C00000BBh
0x18006964f  lea     rdx, aNtstatus; "ntStatus"
0x180069656  mov     r9d, 87Ch
0x18006965c  mov     r8, rsi
0x18006965f  mov     ecx, 0C00000BBh
0x180069664  mov     ebx, edi
0x180069666  call    DebugTraceError
0x18006966b  jmp     loc_18006973F
0x180069670  mov     r8d, r15d
0x180069673  lea     rdx, [rbp+var_10]
0x180069677  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x18006967e  call    _guard_dispatch_icall
0x180069683  mov     ebx, eax
0x180069685  test    eax, eax
0x180069687  jns     loc_180069739
0x18006968d  mov     r9d, 86Ah
0x180069693  jmp     loc_180069724
0x180069698  mov     r8d, r15d
0x18006969b  lea     rdx, [rbp+var_10]
0x18006969f  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x1800696a6  call    _guard_dispatch_icall
0x1800696ab  mov     ebx, eax
0x1800696ad  test    eax, eax
0x1800696af  jns     loc_180069739
0x1800696b5  mov     r9d, 876h
0x1800696bb  jmp     short loc_180069724
0x1800696bd  mov     r8d, r15d
0x1800696c0  lea     rdx, [rbp+var_10]
0x1800696c4  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x1800696cb  call    _guard_dispatch_icall
0x1800696d0  mov     ebx, eax
0x1800696d2  test    eax, eax
0x1800696d4  jns     short loc_180069739
0x1800696d6  mov     r9d, 85Eh
0x1800696dc  jmp     short loc_180069724
0x1800696de  mov     r9d, r15d
0x1800696e1  lea     r8, [rbp+var_10]
0x1800696e5  mov     rdx, r12
0x1800696e8  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x1800696ef  call    _guard_dispatch_icall
0x1800696f4  mov     ebx, eax
0x1800696f6  test    eax, eax
0x1800696f8  jns     short loc_180069739
0x1800696fa  mov     r9d, 852h
0x180069700  jmp     short loc_180069724
0x180069702  mov     r9d, r15d
0x180069705  lea     r8, [rbp+var_10]
0x180069709  mov     rdx, r12
0x18006970c  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x180069713  call    _guard_dispatch_icall
0x180069718  mov     ebx, eax
0x18006971a  test    eax, eax
0x18006971c  jns     short loc_180069739
0x18006971e  mov     r9d, 845h
0x180069724  mov     r8, rsi
0x180069727  lea     rdx, aNtstatus; "ntStatus"
0x18006972e  mov     ecx, ebx
0x180069730  call    DebugTraceError
0x180069735  mov     edi, ebx
0x180069737  jmp     short loc_18006973F
0x180069739  mov     edi, ebx
0x18006973b  test    ebx, ebx
0x18006973d  jns     short loc_18006974F
0x18006973f  mov     r9d, 939h
0x180069745  mov     r8, rsi
0x180069748  mov     ecx, ebx
0x18006974a  jmp     loc_1800694D7
0x18006974f  mov     rax, [rbp+var_10]
0x180069753  mov     ecx, 3
0x180069758  lea     edx, [rcx+7Dh]
0x18006975b  movups  xmm0, xmmword ptr [rax]
0x18006975e  movups  xmmword ptr [r14], xmm0
0x180069762  movups  xmm1, xmmword ptr [rax+10h]
0x180069766  movups  xmmword ptr [r14+10h], xmm1
0x18006976b  movups  xmm0, xmmword ptr [rax+20h]
0x18006976f  movups  xmmword ptr [r14+20h], xmm0
0x180069774  movups  xmm1, xmmword ptr [rax+30h]
0x180069778  movups  xmmword ptr [r14+30h], xmm1
0x18006977d  movups  xmm0, xmmword ptr [rax+40h]
0x180069781  movups  xmmword ptr [r14+40h], xmm0
0x180069786  movups  xmm1, xmmword ptr [rax+50h]
0x18006978a  movups  xmmword ptr [r14+50h], xmm1
0x18006978f  movups  xmm0, xmmword ptr [rax+60h]
0x180069793  movups  xmmword ptr [r14+60h], xmm0
0x180069798  movups  xmm1, xmmword ptr [rax+70h]
0x18006979c  add     rax, rdx
0x18006979f  movups  xmmword ptr [r14+70h], xmm1
0x1800697a4  add     r14, rdx
0x1800697a7  sub     rcx, 1
0x1800697ab  jnz     short loc_18006975B
0x1800697ad  mov     rax, [rax]
0x1800697b0  mov     [r14], rax
0x1800697b3  mov     eax, edi
0x1800697b5  add     rsp, 40h
0x1800697b9  pop     r15
0x1800697bb  pop     r14
0x1800697bd  pop     r12
0x1800697bf  pop     rdi
0x1800697c0  pop     rsi
0x1800697c1  pop     rbx
0x1800697c2  pop     rbp
0x1800697c3  retn
```
