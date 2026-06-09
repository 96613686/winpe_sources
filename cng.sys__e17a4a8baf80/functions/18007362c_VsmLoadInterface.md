# VsmLoadInterface

- ea: `0x18007362c`
- end: `0x180073965`
- name: `VsmLoadInterface`
- size: `825`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180064e78`

## callees

- `0x18001155c`
- `0x180073568`
- `0x18007362c`
- `0x1800a4300`

## string_xrefs

- `0x18007366e`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18007368c`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

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
0x18007362c  push    rbp
0x18007362e  push    rbx
0x18007362f  push    rsi
0x180073630  push    rdi
0x180073631  push    r12
0x180073633  push    r14
0x180073635  push    r15
0x180073637  mov     rbp, rsp
0x18007363a  sub     rsp, 40h
0x18007363e  mov     r12, rdx
0x180073641  mov     [rbp+var_8], 0
0x180073649  lea     rdx, [rbp+var_8]
0x18007364d  mov     [rbp+var_10], 0
0x180073655  mov     r14, r9
0x180073658  mov     r15d, r8d
0x18007365b  mov     ebx, ecx
0x18007365d  call    VsmGetLinkedInterfaceProvider
0x180073662  mov     edi, eax
0x180073664  test    eax, eax
0x180073666  jns     short loc_180073688
0x180073668  mov     r9d, 92Ch
0x18007366e  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180073675  mov     ecx, eax
0x180073677  lea     rdx, aStatus; "Status"
0x18007367e  call    DebugTraceError
0x180073683  jmp     loc_180073953
0x180073688  mov     rax, [rbp+var_8]
0x18007368c  lea     rsi, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180073693  cmp     ebx, 6
0x180073696  ja      loc_1800737C6
0x18007369c  jz      loc_18007379E
0x1800736a2  sub     ebx, 1
0x1800736a5  jz      loc_180073773
0x1800736ab  sub     ebx, 1
0x1800736ae  jz      loc_180073748
0x1800736b4  sub     ebx, 1
0x1800736b7  jz      short loc_18007371D
0x1800736b9  sub     ebx, 1
0x1800736bc  jz      short loc_1800736F2
0x1800736be  cmp     ebx, 1
0x1800736c1  jnz     loc_1800737EA
0x1800736c7  mov     r9d, r15d
0x1800736ca  lea     r8, [rbp+var_10]
0x1800736ce  mov     rdx, r12
0x1800736d1  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x1800736d8  call    _guard_dispatch_icall
0x1800736dd  mov     ebx, eax
0x1800736df  test    eax, eax
0x1800736e1  jns     loc_1800738D9
0x1800736e7  mov     r9d, 82Ch
0x1800736ed  jmp     loc_1800738C4
0x1800736f2  mov     r9d, r15d
0x1800736f5  lea     r8, [rbp+var_10]
0x1800736f9  mov     rdx, r12
0x1800736fc  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x180073703  call    _guard_dispatch_icall
0x180073708  mov     ebx, eax
0x18007370a  test    eax, eax
0x18007370c  jns     loc_1800738D9
0x180073712  mov     r9d, 81Fh
0x180073718  jmp     loc_1800738C4
0x18007371d  mov     r9d, r15d
0x180073720  lea     r8, [rbp+var_10]
0x180073724  mov     rdx, r12
0x180073727  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x18007372e  call    _guard_dispatch_icall
0x180073733  mov     ebx, eax
0x180073735  test    eax, eax
0x180073737  jns     loc_1800738D9
0x18007373d  mov     r9d, 812h
0x180073743  jmp     loc_1800738C4
0x180073748  mov     r9d, r15d
0x18007374b  lea     r8, [rbp+var_10]
0x18007374f  mov     rdx, r12
0x180073752  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x180073759  call    _guard_dispatch_icall
0x18007375e  mov     ebx, eax
0x180073760  test    eax, eax
0x180073762  jns     loc_1800738D9
0x180073768  mov     r9d, 805h
0x18007376e  jmp     loc_1800738C4
0x180073773  mov     r9d, r15d
0x180073776  lea     r8, [rbp+var_10]
0x18007377a  mov     rdx, r12
0x18007377d  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x180073784  call    _guard_dispatch_icall
0x180073789  mov     ebx, eax
0x18007378b  test    eax, eax
0x18007378d  jns     loc_1800738D9
0x180073793  mov     r9d, 7F8h
0x180073799  jmp     loc_1800738C4
0x18007379e  mov     r8d, r15d
0x1800737a1  lea     rdx, [rbp+var_10]
0x1800737a5  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x1800737ac  call    _guard_dispatch_icall
0x1800737b1  mov     ebx, eax
0x1800737b3  test    eax, eax
0x1800737b5  jns     loc_1800738D9
0x1800737bb  mov     r9d, 838h
0x1800737c1  jmp     loc_1800738C4
0x1800737c6  sub     ebx, 7
0x1800737c9  jz      loc_1800738A2
0x1800737cf  sub     ebx, 1
0x1800737d2  jz      loc_18007387E
0x1800737d8  sub     ebx, 0FFF9h
0x1800737de  jz      short loc_18007385D
0x1800737e0  sub     ebx, 1
0x1800737e3  jz      short loc_180073838
0x1800737e5  cmp     ebx, 2
0x1800737e8  jz      short loc_180073810
0x1800737ea  mov     edi, 0C00000BBh
0x1800737ef  lea     rdx, aNtstatus; "ntStatus"
0x1800737f6  mov     r9d, 87Ch
0x1800737fc  mov     r8, rsi
0x1800737ff  mov     ecx, 0C00000BBh
0x180073804  mov     ebx, edi
0x180073806  call    DebugTraceError
0x18007380b  jmp     loc_1800738DF
0x180073810  mov     r8d, r15d
0x180073813  lea     rdx, [rbp+var_10]
0x180073817  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x18007381e  call    _guard_dispatch_icall
0x180073823  mov     ebx, eax
0x180073825  test    eax, eax
0x180073827  jns     loc_1800738D9
0x18007382d  mov     r9d, 86Ah
0x180073833  jmp     loc_1800738C4
0x180073838  mov     r8d, r15d
0x18007383b  lea     rdx, [rbp+var_10]
0x18007383f  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x180073846  call    _guard_dispatch_icall
0x18007384b  mov     ebx, eax
0x18007384d  test    eax, eax
0x18007384f  jns     loc_1800738D9
0x180073855  mov     r9d, 876h
0x18007385b  jmp     short loc_1800738C4
0x18007385d  mov     r8d, r15d
0x180073860  lea     rdx, [rbp+var_10]
0x180073864  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x18007386b  call    _guard_dispatch_icall
0x180073870  mov     ebx, eax
0x180073872  test    eax, eax
0x180073874  jns     short loc_1800738D9
0x180073876  mov     r9d, 85Eh
0x18007387c  jmp     short loc_1800738C4
0x18007387e  mov     r9d, r15d
0x180073881  lea     r8, [rbp+var_10]
0x180073885  mov     rdx, r12
0x180073888  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x18007388f  call    _guard_dispatch_icall
0x180073894  mov     ebx, eax
0x180073896  test    eax, eax
0x180073898  jns     short loc_1800738D9
0x18007389a  mov     r9d, 852h
0x1800738a0  jmp     short loc_1800738C4
0x1800738a2  mov     r9d, r15d
0x1800738a5  lea     r8, [rbp+var_10]
0x1800738a9  mov     rdx, r12
0x1800738ac  lea     rcx, pszProvider; "Microsoft Primitive Provider"
0x1800738b3  call    _guard_dispatch_icall
0x1800738b8  mov     ebx, eax
0x1800738ba  test    eax, eax
0x1800738bc  jns     short loc_1800738D9
0x1800738be  mov     r9d, 845h
0x1800738c4  mov     r8, rsi
0x1800738c7  lea     rdx, aNtstatus; "ntStatus"
0x1800738ce  mov     ecx, ebx
0x1800738d0  call    DebugTraceError
0x1800738d5  mov     edi, ebx
0x1800738d7  jmp     short loc_1800738DF
0x1800738d9  mov     edi, ebx
0x1800738db  test    ebx, ebx
0x1800738dd  jns     short loc_1800738EF
0x1800738df  mov     r9d, 939h
0x1800738e5  mov     r8, rsi
0x1800738e8  mov     ecx, ebx
0x1800738ea  jmp     loc_180073677
0x1800738ef  mov     rax, [rbp+var_10]
0x1800738f3  mov     ecx, 3
0x1800738f8  lea     edx, [rcx+7Dh]
0x1800738fb  movups  xmm0, xmmword ptr [rax]
0x1800738fe  movups  xmmword ptr [r14], xmm0
0x180073902  movups  xmm1, xmmword ptr [rax+10h]
0x180073906  movups  xmmword ptr [r14+10h], xmm1
0x18007390b  movups  xmm0, xmmword ptr [rax+20h]
0x18007390f  movups  xmmword ptr [r14+20h], xmm0
0x180073914  movups  xmm1, xmmword ptr [rax+30h]
0x180073918  movups  xmmword ptr [r14+30h], xmm1
0x18007391d  movups  xmm0, xmmword ptr [rax+40h]
0x180073921  movups  xmmword ptr [r14+40h], xmm0
0x180073926  movups  xmm1, xmmword ptr [rax+50h]
0x18007392a  movups  xmmword ptr [r14+50h], xmm1
0x18007392f  movups  xmm0, xmmword ptr [rax+60h]
0x180073933  movups  xmmword ptr [r14+60h], xmm0
0x180073938  movups  xmm1, xmmword ptr [rax+70h]
0x18007393c  add     rax, rdx
0x18007393f  movups  xmmword ptr [r14+70h], xmm1
0x180073944  add     r14, rdx
0x180073947  sub     rcx, 1
0x18007394b  jnz     short loc_1800738FB
0x18007394d  mov     rax, [rax]
0x180073950  mov     [r14], rax
0x180073953  mov     eax, edi
0x180073955  add     rsp, 40h
0x180073959  pop     r15
0x18007395b  pop     r14
0x18007395d  pop     r12
0x18007395f  pop     rdi
0x180073960  pop     rsi
0x180073961  pop     rbx
0x180073962  pop     rbp
0x180073963  retn
```
